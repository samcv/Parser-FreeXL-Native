NAME
====

Parser::FreeXL::Native - wrapper for freexl parsing .xls files

SYNOPSIS
========

    use Parser::FreeXL::Native;

    my Parser::FreeXL::Native $parser .= new;
    $parser.open('file.xls');

    my $worksheet_count = $parser.get_worksheet_count;

    $parser.select_worksheet(1);

    my ($max_row, $max_col) = $parser.worksheet_dimensions;

    for ^$max_row -> $row {
        for ^$max_col -> $col {
            my $cell  = $parser.get_cell($row, $col);
            # types: <int double text date datetime time>, Nil
            my $type  = $cell.type;
            my $value = $cell.value;

            # do something with type and value
        }
    }

DESCRIPTION
===========

Parser::FreeXL::Native is a parser for xls using the freexl c library

AUTHOR
======

spebern <bernhard@specht.net>

COPYRIGHT AND LICENSE
=====================

Copyright 2016 spebern

This library is free software; you can redistribute it and/or modify it under the Artistic License 2.0.