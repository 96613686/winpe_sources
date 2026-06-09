# Microsoft.Crm.ObjectModel.SharePointErrorHandler::HandleSharePointException_1

- ea: `0x17c3e0`
- end: `0x17c8af`
- name: `Microsoft.Crm.ObjectModel.SharePointErrorHandler::HandleSharePointException_1`
- size: `1231`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x17c3a0`
- `0x17c3c0`

## callees

- `0x17c3e0`
- `0x17c910`

## string_xrefs

- `0x17c5d9`: `File already checked out`
- `0x17c649`: `Field is read-only`
- `0x17c65b`: `List item was modified on the server so changes cannot be committed`
- `0x17c6b8`: `Folder renamed`
- `0x17c779`: `The list item could not be updated because invalid lookup values were found for one or more fields in the list`
- `0x17c7af`: `File Already Exists`
- `0x17c7c1`: `Item is deleted`
- `0x17c85c`: `The folder name contains invalid characters. Please use a different name. Common invalid characters include: # % * : < > ? /  |\n\n`

## pseudocode

```c

```

## disassembly

```asm
0x17c3e0  ldarg.1
0x17c3e1  brtrue.s loc_17C3EA
0x17c3e3  ldsfld   string [mscorlib]System.String::Empty
0x17c3e8  starg.s  1
0x17c3ea  ldarg.2
0x17c3eb  brtrue.s loc_17C3F4
0x17c3ed  ldsfld   string [mscorlib]System.String::Empty
0x17c3f2  starg.s  2
0x17c3f4  ldc.i4.0
0x17c3f5  stloc.0
0x17c3f6  ldarg.0
0x17c3f7  ldc.i4   0x80071772
0x17c3fc  bgt      loc_17C4F1
0x17c401  ldarg.0
0x17c402  ldc.i4   0x80070002
0x17c407  bgt      loc_17C49D
0x17c40c  ldarg.0
0x17c40d  ldc.i4   0x80060738
0x17c412  bgt.s    loc_17C477
0x17c414  ldarg.0
0x17c415  ldc.i4   0x80004003
0x17c41a  beq      loc_17C79D
0x17c41f  ldarg.0
0x17c420  ldc.i4   0x80020005
0x17c425  beq      loc_17C649
0x17c42a  ldarg.0
0x17c42b  ldc.i4   0x8006072A
0x17c430  sub
0x17c431  switch   loc_17C80E, loc_17C816, loc_17C81E, loc_17C826, loc_17C82E, loc_17C836, loc_17C871, loc_17C871, loc_17C871, loc_17C871, loc_17C83E, loc_17C871, loc_17C871, loc_17C871, loc_17C846
0x17c472  br       loc_17C871
0x17c477  ldarg.0
0x17c478  ldc.i4   0x800608B4
0x17c47d  beq      loc_17C7E5
0x17c482  ldarg.0
0x17c483  ldc.i4   0x800608B5
0x17c488  beq      loc_17C7F7
0x17c48d  ldarg.0
0x17c48e  ldc.i4   0x80070002
0x17c493  beq      loc_17C6B5
0x17c498  br       loc_17C871
0x17c49d  ldarg.0
0x17c49e  ldc.i4   0x8007009E
0x17c4a3  bgt.s    loc_17C4CB
0x17c4a5  ldarg.0
0x17c4a6  ldc.i4   0x80070024
0x17c4ab  beq      loc_17C6A3
0x17c4b0  ldarg.0
0x17c4b1  ldc.i4   0x80070057
0x17c4b6  beq      loc_17C5B2
0x17c4bb  ldarg.0
0x17c4bc  ldc.i4   0x8007009E
0x17c4c1  beq      loc_17C625
0x17c4c6  br       loc_17C871
0x17c4cb  ldarg.0
0x17c4cc  ldc.i4   0x800700A7
0x17c4d1  beq      loc_17C767
0x17c4d6  ldarg.0
0x17c4d7  ldc.i4   0x800705B4
0x17c4dc  beq      loc_17C5FD
0x17c4e1  ldarg.0
0x17c4e2  ldc.i4   0x80071772
0x17c4e7  beq      loc_17C70B
0x17c4ec  br       loc_17C871
0x17c4f1  ldarg.0
0x17c4f2  ldc.i4   0x81020037
0x17c4f7  bgt.s    loc_17C54D
0x17c4f9  ldarg.0
0x17c4fa  ldc.i4   0x80131600
0x17c4ff  bgt.s    loc_17C527
0x17c501  ldarg.0
0x17c502  ldc.i4   0x80071779
0x17c507  beq      loc_17C6F9
0x17c50c  ldarg.0
0x17c50d  ldc.i4   0x80131502
0x17c512  beq      loc_17C78B
0x17c517  ldarg.0
0x17c518  ldc.i4   0x80131600
0x17c51d  beq      loc_17C71D
0x17c522  br       loc_17C871
0x17c527  ldarg.0
0x17c528  ldc.i4   0x81020016
0x17c52d  beq      loc_17C7C1
0x17c532  ldarg.0
0x17c533  ldc.i4   0x81020036
0x17c538  beq      loc_17C5D5
0x17c53d  ldarg.0
0x17c53e  ldc.i4   0x81020037
0x17c543  beq      loc_17C65B
0x17c548  br       loc_17C871
0x17c54d  ldarg.0
0x17c54e  ldc.i4   0x810200C9
0x17c553  bgt.s    loc_17C590
0x17c555  ldarg.0
0x17c556  ldc.i4   0x81020067
0x17c55b  beq      loc_17C7AF
0x17c560  ldarg.0
0x17c561  ldc.i4   0x810200BF
0x17c566  beq      loc_17C637
0x17c56b  ldarg.0
0x17c56c  ldc.i4   0x810200C5
0x17c571  sub
0x17c572  switch   loc_17C66D, loc_17C67F, loc_17C691, loc_17C871, loc_17C779
0x17c58b  br       loc_17C871
0x17c590  ldarg.0
0x17c591  ldc.i4   0x810200E4
0x17c596  beq      loc_17C806
0x17c59b  ldarg.0
0x17c59c  ldc.i4   0x81070203
0x17c5a1  beq      loc_17C85C
0x17c5a6  ldarg.0
0x17c5a7  ldc.i4.m1
0x17c5a8  beq      loc_17C7D3
0x17c5ad  br       loc_17C871
0x17c5b2  ldarg.3
0x17c5b3  ldc.i4.6
0x17c5b4  beq.s    loc_17C5BA
0x17c5b6  ldarg.3
0x17c5b7  ldc.i4.8
0x17c5b8  bne.un.s loc_17C5C3
0x17c5ba  ldstr    aInvalidUrl// "invalid URL"
0x17c5bf  starg.s  1
0x17c5c1  br.s     loc_17C5CA
0x17c5c3  ldstr    aListItemDoesNo// "List item does not exist"
0x17c5c8  starg.s  1
0x17c5ca  ldc.i4   0x80060717
0x17c5cf  stloc.0
0x17c5d0  br       loc_17C885
0x17c5d5  ldarg.3
0x17c5d6  ldc.i4.5
0x17c5d7  beq.s    loc_17C5E0
0x17c5d9  ldstr    aFileAlreadyChe// "File already checked out"
0x17c5de  br.s     loc_17C5E5
0x17c5e0  ldstr    aFileIsCheckedO// "File is checked out by other user"
0x17c5e5  starg.s  1
0x17c5e7  ldarg.3
0x17c5e8  ldc.i4.5
0x17c5e9  beq.s    loc_17C5F2
0x17c5eb  ldc.i4   0x80060702
0x17c5f0  br.s     loc_17C5F7
0x17c5f2  ldc.i4   0x80060728
0x17c5f7  stloc.0
0x17c5f8  br       loc_17C885
0x17c5fd  ldarg.3
0x17c5fe  ldc.i4.6
0x17c5ff  beq.s    loc_17C608
0x17c601  ldstr    aCheckoutArgume// "checkout arguments not valid"
0x17c606  br.s     loc_17C60D
0x17c608  ldstr    aTheFileInTheCo// "The file in the collection has bad lock"...
0x17c60d  starg.s  1
0x17c60f  ldarg.3
0x17c610  ldc.i4.6
0x17c611  beq.s    loc_17C61A
0x17c613  ldc.i4   0x80060703
0x17c618  br.s     loc_17C61F
0x17c61a  ldc.i4   0x8006070A
0x17c61f  stloc.0
0x17c620  br       loc_17C885
0x17c625  ldstr    aFileNotChecked// "File not checked out"
0x17c62a  starg.s  1
0x17c62c  ldc.i4   0x80060700
0x17c631  stloc.0
0x17c632  br       loc_17C885
0x17c637  ldstr    aDuplicateValue// "Duplicate value was found"
0x17c63c  starg.s  1
0x17c63e  ldc.i4   0x80060708
0x17c643  stloc.0
0x17c644  br       loc_17C885
0x17c649  ldstr    aFieldIsReadOnl// "Field is read-only"
0x17c64e  starg.s  1
0x17c650  ldc.i4   0x8006070F
0x17c655  stloc.0
0x17c656  br       loc_17C885
0x17c65b  ldstr    aListItemWasMod// "List item was modified on the server so"...
0x17c660  starg.s  1
0x17c662  ldc.i4   0x80060710
0x17c667  stloc.0
0x17c668  br       loc_17C885
0x17c66d  ldstr    aDataValidation// "Data validation has failed on the field"
0x17c672  starg.s  1
0x17c674  ldc.i4   0x80060711
0x17c679  stloc.0
0x17c67a  br       loc_17C885
0x17c67f  ldstr    aDataValidation_0// "Data validation has failed on the list"
0x17c684  starg.s  1
0x17c686  ldc.i4   0x80060712
0x17c68b  stloc.0
0x17c68c  br       loc_17C885
0x17c691  ldstr    aDataValidation_1// "Data validation has failed on the field"...
0x17c696  starg.s  1
0x17c698  ldc.i4   0x80060713
0x17c69d  stloc.0
0x17c69e  br       loc_17C885
0x17c6a3  ldstr    aThrottlingLimi_1// "Throttling limit is exceeded by the ope"...
0x17c6a8  starg.s  1
0x17c6aa  ldc.i4   0x80060714
0x17c6af  stloc.0
0x17c6b0  br       loc_17C885
0x17c6b5  ldarg.3
0x17c6b6  brtrue.s loc_17C6CA
0x17c6b8  ldstr    aFolderRenamed// "Folder renamed"
0x17c6bd  starg.s  1
0x17c6bf  ldc.i4   0x80060729
0x17c6c4  stloc.0
0x17c6c5  br       loc_17C885
0x17c6ca  ldarg.3
0x17c6cb  ldc.i4.6
0x17c6cc  beq.s    loc_17C6E0
0x17c6ce  ldstr    aFileNotFound// "File Not Found"
0x17c6d3  starg.s  1
0x17c6d5  ldc.i4   0x80060706
0x17c6da  stloc.0
0x17c6db  br       loc_17C885
0x17c6e0  ldstr    aDefault_1// "Default:"
0x17c6e5  ldarg.1
0x17c6e6  ldarg.2
0x17c6e7  call     string [mscorlib]System.String::Concat(string, string, string)
0x17c6ec  starg.s  1
0x17c6ee  ldc.i4   0x80060706
0x17c6f3  stloc.0
0x17c6f4  br       loc_17C885
0x17c6f9  ldstr    aExclusiveLockO// "Exclusive lock on the file"
0x17c6fe  starg.s  1
0x17c700  ldc.i4   0x80060705
0x17c705  stloc.0
0x17c706  br       loc_17C885
0x17c70b  ldstr    aSharedLockOnTh// "Shared lock on the file"
0x17c710  starg.s  1
0x17c712  ldc.i4   0x80060704
0x17c717  stloc.0
0x17c718  br       loc_17C885
0x17c71d  ldarg.3
0x17c71e  ldc.i4.4
0x17c71f  bne.un.s loc_17C739
0x17c721  ldstr    aListItemIsAnIn// "list item is an instance of a recurring"...
0x17c726  ldarg.1
0x17c727  call     string [mscorlib]System.String::Concat(string, string)
0x17c72c  starg.s  1
0x17c72e  ldc.i4   0x80060716
0x17c733  stloc.0
0x17c734  br       loc_17C885
0x17c739  ldarg.3
0x17c73a  ldc.i4.1
0x17c73b  bne.un.s loc_17C755
0x17c73d  ldstr    aRequiredColumn// "Required Columns are set at sharepoint "...
0x17c742  ldarg.1
0x17c743  call     string [mscorlib]System.String::Concat(string, string)
0x17c748  starg.s  1
0x17c74a  ldc.i4   0x80060725
0x17c74f  stloc.0
0x17c750  br       loc_17C885
0x17c755  ldstr    aVirusCheckingI// "Virus checking indicates the file is in"...
0x17c75a  starg.s  1
0x17c75c  ldc.i4   0x80060709
0x17c761  stloc.0
0x17c762  br       loc_17C885
0x17c767  ldstr    aTheFileInTheCo_0// "The file in the collection is not locke"...
0x17c76c  starg.s  1
0x17c76e  ldc.i4   0x80060707
0x17c773  stloc.0
0x17c774  br       loc_17C885
0x17c779  ldstr    aTheListItemCou// "The list item could not be updated beca"...
0x17c77e  starg.s  1
0x17c780  ldc.i4   0x8006070B
0x17c785  stloc.0
0x17c786  br       loc_17C885
0x17c78b  ldstr    aThereIsAMismat// "There is a mismatch between the size of"...
0x17c790  starg.s  1
0x17c792  ldc.i4   0x8006070E
0x17c797  stloc.0
0x17c798  br       loc_17C885
0x17c79d  ldstr    aContentOfTheFi// "Content of the file creation informatio"...
0x17c7a2  starg.s  1
0x17c7a4  ldc.i4   0x8006070D
0x17c7a9  stloc.0
0x17c7aa  br       loc_17C885
0x17c7af  ldstr    aFileAlreadyExi// "File Already Exists"
0x17c7b4  starg.s  1
0x17c7b6  ldc.i4   0x80060708
0x17c7bb  stloc.0
0x17c7bc  br       loc_17C885
0x17c7c1  ldstr    aItemIsDeleted// "Item is deleted"
0x17c7c6  starg.s  1
0x17c7c8  ldc.i4   0x80060717
0x17c7cd  stloc.0
0x17c7ce  br       loc_17C885
0x17c7d3  ldstr    aListDoesNotSup// "List does not support this operation"
0x17c7d8  starg.s  1
0x17c7da  ldc.i4   0x80060715
0x17c7df  stloc.0
0x17c7e0  br       loc_17C885
0x17c7e5  ldstr    aTheRemoteServe// "The remote server returned 401 unauthor"...
0x17c7ea  starg.s  1
0x17c7ec  ldc.i4   0x800608B4
0x17c7f1  stloc.0
0x17c7f2  br       loc_17C885
0x17c7f7  ldstr    aConnectionToTh// "Connection to the server failed. Please"...
0x17c7fc  starg.s  1
0x17c7fe  ldc.i4   0x800608B5
0x17c803  stloc.0
0x17c804  br.s     loc_17C885
  ... truncated ...
```
