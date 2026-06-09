# VfSecurityEntry

- ea: `0x14063cad0`
- end: `0x14063e201`
- name: `VfSecurityEntry`
- size: `5937`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14053fcf0`
- `0x1406dc8c0`

## string_xrefs

- `0x14063cb56`: `ZwAdjustPrivilegesToken`
- `0x14063cafc`: `ZwAccessCheckAndAuditAlarm`
- `0x14063cd6e`: `ZwDeleteValueKey`
- `0x14063ccfe`: `ZwCreateSymbolicLinkObject`
- `0x14063cd1a`: `ZwCreateTimer`
- `0x14063cd36`: `ZwDeleteBootEntry`
- `0x14063cd52`: `ZwDeleteFile`
- `0x14063cc06`: `ZwCreateFile`
- `0x14063cc22`: `ZwCreateJobObject`
- `0x14063cc3e`: `ZwCreateKey`
- `0x14063cce2`: `ZwCreateSection`
- `0x14063cbda`: `ZwCreateDirectoryObject`
- `0x14063cbf0`: `ZwCreateEvent`
- `0x14063d069`: `ZwOpenDirectoryObject`
- `0x14063cf51`: `ZwFlushInstructionCache`
- `0x14063cdde`: `ZwDuplicateToken`
- `0x14063d2b9`: `ZwOpenTimer`
- `0x14063d249`: `ZwOpenSymbolicLinkObject`
- `0x14063d265`: `ZwOpenThread`
- `0x14063d281`: `ZwOpenThreadToken`
- `0x14063d29d`: `ZwOpenThreadTokenEx`
- `0x14063d1d9`: `ZwOpenProcess`
- `0x14063d1f5`: `ZwOpenProcessToken`
- `0x14063d211`: `ZwOpenProcessTokenEx`
- `0x14063d22d`: `ZwOpenSection`
- `0x14063d085`: `ZwOpenEvent`
- `0x14063d0a1`: `ZwOpenFile`
- `0x14063d1a1`: `ZwOpenJobObject`
- `0x14063d1bd`: `ZwOpenKey`
- `0x14063d67c`: `ZwQueryInformationThread`
- `0x14063d698`: `ZwQueryInformationToken`
- `0x14063d4f0`: `ZwQueryDirectoryObject`
- `0x14063d49c`: `ZwQueryInstallUILanguage`
- `0x14063d4b8`: `ZwQueryDirectoryFile`
- `0x14063d4d4`: `ZwQueryDirectoryFileEx`
- `0x14063d794`: `ZwReadFile`
- `0x14063d7b0`: `ZwReplaceKey`
- `0x14063d724`: `ZwQuerySymbolicLinkObject`
- `0x14063d708`: `ZwQuerySecurityObject`
- `0x14063db9d`: `ZwTranslateFilePath`
- `0x14063d9e7`: `ZwSetInformationThread`
- `0x14063da03`: `ZwSetSecurityObject`
- `0x14063de3a`: `ZwRemoveIoCompletionEx`
- `0x14063de56`: `ZwCreateTransactionManager`
- `0x14063de72`: `ZwOpenTransactionManager`
- `0x14063ddca`: `ZwAlpcCreateSectionView`
- `0x14063dde6`: `ZwAlpcCreateResourceReserve`
- `0x14063dd92`: `ZwAlpcCreateSecurityContext`
- `0x14063ddae`: `ZwAlpcCreatePortSection`
- `0x14063dc29`: `ZwWriteFile`
- `0x14063dc45`: `ZwAlpcCreatePort`
- `0x14063e071`: `ZwPrepareComplete`
- `0x14063e08d`: `ZwCreateEnlistment`
- `0x14063e0a9`: `ZwOpenEnlistment`
- `0x14063e039`: `ZwCommitEnlistment`
- `0x14063e055`: `ZwRollbackEnlistment`
- `0x14063deaa`: `ZwCreateTransaction`
- `0x14063dec6`: `ZwOpenTransaction`

## pseudocode

```c

```

## disassembly

```asm
0x14063cad0  push    rbp
0x14063cad2  lea     rbp, [rsp-0FD0h]
0x14063cada  sub     rsp, 10D0h
0x14063cae1  mov     rax, cs:__security_cookie
0x14063cae8  xor     rax, rsp
0x14063caeb  mov     [rbp+0FD0h+var_10], rax
0x14063caf2  xor     ecx, ecx
0x14063caf4  mov     [rsp+10D0h+var_10A8], 94h
0x14063cafc  lea     rax, aZwaccesschecka; "ZwAccessCheckAndAuditAlarm"
0x14063cb03  mov     [rsp+10D0h+var_1098], rcx
0x14063cb08  mov     [rsp+10D0h+var_10B0], rax
0x14063cb0d  mov     edx, 85h
0x14063cb12  lea     rax, VfZwAccessCheckAndAuditAlarm_Entry
0x14063cb19  mov     [rsp+10D0h+var_1088], 93h
0x14063cb21  mov     [rsp+10D0h+var_10A0], rax
0x14063cb26  lea     rax, aZwaddbootentry; "ZwAddBootEntry"
0x14063cb2d  mov     [rsp+10D0h+var_1090], rax
0x14063cb32  lea     rax, VfZwQueryDriverEntryOrder_Entry
0x14063cb39  mov     [rsp+10D0h+var_1080], rax
0x14063cb3e  lea     rax, aZwadddriverent; "ZwAddDriverEntry"
0x14063cb45  mov     [rsp+10D0h+var_1070], rax
0x14063cb4a  lea     rax, VfZwQueryDriverEntryOrder_Entry
0x14063cb51  mov     [rsp+10D0h+var_1060], rax
0x14063cb56  lea     rax, aZwadjustprivil; "ZwAdjustPrivilegesToken"
0x14063cb5d  mov     [rbp+0FD0h+var_1050], rax
0x14063cb61  lea     rax, VfZwTranslateFilePath_Entry
0x14063cb68  mov     [rbp+0FD0h+var_1040], rax
0x14063cb6c  lea     rax, aZwallocatevirt_1; "ZwAllocateVirtualMemory"
0x14063cb73  mov     [rbp+0FD0h+var_1030], rax
0x14063cb77  lea     rax, VfZwPowerInformation_Entry
0x14063cb7e  mov     [rbp+0FD0h+var_1020], rax
0x14063cb82  lea     rax, aZwcanceliofile_0; "ZwCancelIoFile"
0x14063cb89  mov     [rbp+0FD0h+var_1010], rax
0x14063cb8d  lea     rax, VfZwAlpcCreateSecurityContext_Entry
0x14063cb94  mov     [rbp+0FD0h+var_1000], rax
0x14063cb98  lea     rax, aZwcanceltimer; "ZwCancelTimer"
0x14063cb9f  mov     [rbp+0FD0h+var_FF0], rax
0x14063cba3  lea     rax, VfZwAlpcCreateSecurityContext_Entry
0x14063cbaa  mov     [rbp+0FD0h+var_FE0], rax
0x14063cbae  lea     rax, aZwcloseobjecta_0; "ZwCloseObjectAuditAlarm"
0x14063cbb5  mov     [rbp+0FD0h+var_FD0], rax
0x14063cbb9  lea     rax, VfZwCloseObjectAuditAlarm_Entry
0x14063cbc0  mov     [rbp+0FD0h+var_FC0], rax
0x14063cbc4  lea     rax, aZwconnectport_0; "ZwConnectPort"
0x14063cbcb  mov     [rbp+0FD0h+var_FB0], rax
0x14063cbcf  lea     rax, VfZwConnectPort_Entry
0x14063cbd6  mov     [rbp+0FD0h+var_FA0], rax
0x14063cbda  lea     rax, aZwcreatedirect; "ZwCreateDirectoryObject"
0x14063cbe1  mov     [rbp+0FD0h+var_F90], rax
0x14063cbe5  lea     rax, VfZwOpenKey_Entry
0x14063cbec  mov     [rbp+0FD0h+var_F80], rax
0x14063cbf0  lea     rax, aZwcreateevent_0; "ZwCreateEvent"
0x14063cbf7  mov     [rbp+0FD0h+var_F70], rax
0x14063cbfb  lea     rax, VfZwCreateTimer_Entry
0x14063cc02  mov     [rbp+0FD0h+var_F60], rax
0x14063cc06  lea     rax, aZwcreatefile; "ZwCreateFile"
0x14063cc0d  mov     [rbp+0FD0h+var_F50], rax
0x14063cc14  lea     rax, VfZwCreateFile_Entry
0x14063cc1b  mov     [rbp+0FD0h+var_F40], rax
0x14063cc22  lea     rax, aZwcreatejobobj; "ZwCreateJobObject"
0x14063cc29  mov     [rbp+0FD0h+var_F30], rax
0x14063cc30  lea     rax, VfZwOpenKey_Entry
0x14063cc37  mov     [rbp+0FD0h+var_F20], rax
0x14063cc3e  lea     rax, aZwcreatekey; "ZwCreateKey"
0x14063cc45  mov     [rsp+10D0h+var_1078], rcx
0x14063cc4a  mov     [rsp+10D0h+var_1068], 92h
0x14063cc52  mov     [rsp+10D0h+var_1058], rcx
0x14063cc57  mov     [rbp+0FD0h+var_1048], 91h
0x14063cc5e  mov     [rbp+0FD0h+var_1038], rcx
0x14063cc62  mov     [rbp+0FD0h+var_1028], 90h
0x14063cc69  mov     [rbp+0FD0h+var_1018], rcx
0x14063cc6d  mov     [rbp+0FD0h+var_1008], edx
0x14063cc70  mov     [rbp+0FD0h+var_FF8], rcx
0x14063cc74  mov     [rbp+0FD0h+var_FE8], 84h
0x14063cc7b  mov     [rbp+0FD0h+var_FD8], rcx
0x14063cc7f  mov     [rbp+0FD0h+var_FC8], 82h
0x14063cc86  mov     [rbp+0FD0h+var_FB8], rcx
0x14063cc8a  mov     [rbp+0FD0h+var_FA8], 80h
0x14063cc91  mov     [rbp+0FD0h+var_F98], rcx
0x14063cc95  mov     [rbp+0FD0h+var_F88], 7Fh
0x14063cc9c  mov     [rbp+0FD0h+var_F78], rcx
0x14063cca0  mov     [rbp+0FD0h+var_F68], 7Dh ; '}'
0x14063cca7  mov     [rbp+0FD0h+var_F58], rcx
0x14063ccab  mov     [rbp+0FD0h+var_F48], 7Ch ; '|'
0x14063ccb5  mov     [rbp+0FD0h+var_F38], rcx
0x14063ccbc  mov     [rbp+0FD0h+var_F28], 7Bh ; '{'
0x14063ccc6  mov     [rbp+0FD0h+var_F18], rcx
0x14063cccd  mov     [rbp+0FD0h+var_F10], rax
0x14063ccd4  lea     rax, VfZwCreateKey_Entry
0x14063ccdb  mov     [rbp+0FD0h+var_F00], rax
0x14063cce2  lea     rax, aZwcreatesectio; "ZwCreateSection"
0x14063cce9  mov     [rbp+0FD0h+var_EF0], rax
0x14063ccf0  lea     rax, VfZwCreateSection_Entry
0x14063ccf7  mov     [rbp+0FD0h+var_EE0], rax
0x14063ccfe  lea     rax, aZwcreatesymbol_0; "ZwCreateSymbolicLinkObject"
0x14063cd05  mov     [rbp+0FD0h+var_ED0], rax
0x14063cd0c  lea     rax, VfZwCreateSymbolicLinkObject_Entry
0x14063cd13  mov     [rbp+0FD0h+var_EC0], rax
0x14063cd1a  lea     rax, aZwcreatetimer; "ZwCreateTimer"
0x14063cd21  mov     [rbp+0FD0h+var_EB0], rax
0x14063cd28  lea     rax, VfZwCreateTimer_Entry
0x14063cd2f  mov     [rbp+0FD0h+var_EA0], rax
0x14063cd36  lea     rax, aZwdeletebooten_0; "ZwDeleteBootEntry"
0x14063cd3d  mov     [rbp+0FD0h+var_E90], rax
0x14063cd44  lea     rax, ViSpIoAllocateIrp_Exit
0x14063cd4b  mov     [rbp+0FD0h+var_E80], rax
0x14063cd52  lea     rax, aZwdeletefile; "ZwDeleteFile"
0x14063cd59  mov     [rbp+0FD0h+var_E70], rax
0x14063cd60  lea     rax, VfZwDeleteFile_Entry
0x14063cd67  mov     [rbp+0FD0h+var_E60], rax
0x14063cd6e  lea     rax, aZwdeletevaluek; "ZwDeleteValueKey"
0x14063cd75  mov     [rbp+0FD0h+var_E50], rax
0x14063cd7c  lea     rax, VfZwDeleteValueKey_Entry
0x14063cd83  mov     [rbp+0FD0h+var_E40], rax
0x14063cd8a  lea     rax, aZwdeviceiocont_0; "ZwDeviceIoControlFile"
0x14063cd91  mov     [rbp+0FD0h+var_E30], rax
0x14063cd98  lea     rax, VfZwDeviceIoControlFile_Entry
0x14063cd9f  mov     [rbp+0FD0h+var_E20], rax
0x14063cda6  lea     rax, aZwdisplaystrin_0; "ZwDisplayString"
0x14063cdad  mov     [rbp+0FD0h+var_E10], rax
0x14063cdb4  lea     rax, VfZwDeleteValueKey_Entry
0x14063cdbb  mov     [rbp+0FD0h+var_E00], rax
0x14063cdc2  lea     rax, aZwduplicateobj; "ZwDuplicateObject"
0x14063cdc9  mov     [rbp+0FD0h+var_DF0], rax
0x14063cdd0  lea     rax, VfZwDuplicateObject_Entry
0x14063cdd7  mov     [rbp+0FD0h+var_DE0], rax
0x14063cdde  lea     rax, aZwduplicatetok_0; "ZwDuplicateToken"
0x14063cde5  mov     [rbp+0FD0h+var_DD0], rax
0x14063cdec  lea     rax, VfZwDuplicateToken_Entry
0x14063cdf3  mov     [rbp+0FD0h+var_DC0], rax
0x14063cdfa  lea     rax, aZwenumerateboo_0; "ZwEnumerateBootEntries"
0x14063ce01  mov     [rbp+0FD0h+var_DB0], rax
0x14063ce08  lea     rax, VfZwQueryDriverEntryOrder_Entry
0x14063ce0f  mov     [rbp+0FD0h+var_DA0], rax
0x14063ce16  lea     rax, aZwenumeratedri_0; "ZwEnumerateDriverEntries"
0x14063ce1d  mov     [rbp+0FD0h+var_D90], rax
0x14063ce24  lea     rax, VfZwQueryDriverEntryOrder_Entry
0x14063ce2b  mov     [rbp+0FD0h+var_D80], rax
0x14063ce32  lea     rax, aZwenumeratekey; "ZwEnumerateKey"
0x14063ce39  mov     [rbp+0FD0h+var_D70], rax
0x14063ce40  lea     rax, VfZwQueryObject_Entry
0x14063ce47  mov     [rbp+0FD0h+var_F08], 7Ah ; 'z'
0x14063ce51  mov     [rbp+0FD0h+var_EF8], rcx
0x14063ce58  mov     [rbp+0FD0h+var_EE8], 77h ; 'w'
0x14063ce62  mov     [rbp+0FD0h+var_ED8], rcx
0x14063ce69  mov     [rbp+0FD0h+var_EC8], 76h ; 'v'
0x14063ce73  mov     [rbp+0FD0h+var_EB8], rcx
0x14063ce7a  mov     [rbp+0FD0h+var_EA8], 75h ; 'u'
0x14063ce84  mov     [rbp+0FD0h+var_E98], rcx
0x14063ce8b  mov     [rbp+0FD0h+var_E88], 72h ; 'r'
0x14063ce95  mov     [rbp+0FD0h+var_E78], rcx
0x14063ce9c  mov     [rbp+0FD0h+var_E68], 71h ; 'q'
0x14063cea6  mov     [rbp+0FD0h+var_E58], rcx
0x14063cead  mov     [rbp+0FD0h+var_E48], 6Fh ; 'o'
0x14063ceb7  mov     [rbp+0FD0h+var_E38], rcx
0x14063cebe  mov     [rbp+0FD0h+var_E28], 6Eh ; 'n'
0x14063cec8  mov     [rbp+0FD0h+var_E18], rcx
0x14063cecf  mov     [rbp+0FD0h+var_E08], 6Dh ; 'm'
0x14063ced9  mov     [rbp+0FD0h+var_DF8], rcx
0x14063cee0  mov     [rbp+0FD0h+var_DE8], 6Ch ; 'l'
0x14063ceea  mov     [rbp+0FD0h+var_DD8], rcx
0x14063cef1  mov     [rbp+0FD0h+var_DC8], 6Bh ; 'k'
0x14063cefb  mov     [rbp+0FD0h+var_DB8], rcx
0x14063cf02  mov     [rbp+0FD0h+var_DA8], 6Ah ; 'j'
0x14063cf0c  mov     [rbp+0FD0h+var_D98], rcx
0x14063cf13  mov     [rbp+0FD0h+var_D88], 69h ; 'i'
0x14063cf1d  mov     [rbp+0FD0h+var_D78], rcx
0x14063cf24  mov     [rbp+0FD0h+var_D68], 68h ; 'h'
0x14063cf2e  mov     [rbp+0FD0h+var_D60], rax
0x14063cf35  lea     rax, aZwenumerateval; "ZwEnumerateValueKey"
0x14063cf3c  mov     [rbp+0FD0h+var_D50], rax
0x14063cf43  lea     rax, VfZwQueryObject_Entry
0x14063cf4a  mov     [rbp+0FD0h+var_D40], rax
0x14063cf51  lea     rax, aZwflushinstruc_0; "ZwFlushInstructionCache"
0x14063cf58  mov     [rbp+0FD0h+var_D30], rax
0x14063cf5f  lea     rax, VfZwSetDriverEntryOrder_Entry
0x14063cf66  mov     [rbp+0FD0h+var_D20], rax
0x14063cf6d  lea     rax, aZwflushvirtual; "ZwFlushVirtualMemory"
0x14063cf74  mov     [rbp+0FD0h+var_D10], rax
0x14063cf7b  lea     rax, VfZwFlushVirtualMemory_Entry
0x14063cf82  mov     [rbp+0FD0h+var_D00], rax
0x14063cf89  lea     rax, aZwfreevirtualm_0; "ZwFreeVirtualMemory"
0x14063cf90  mov     [rbp+0FD0h+var_CF0], rax
0x14063cf97  lea     rax, VfZwFreeVirtualMemory_Entry
0x14063cf9e  mov     [rbp+0FD0h+var_CE0], rax
0x14063cfa5  lea     rax, aZwfscontrolfil; "ZwFsControlFile"
0x14063cfac  mov     [rbp+0FD0h+var_CD0], rax
0x14063cfb3  lea     rax, VfZwDeviceIoControlFile_Entry
0x14063cfba  mov     [rbp+0FD0h+var_CC0], rax
0x14063cfc1  lea     rax, aZwloaddriver_0; "ZwLoadDriver"
0x14063cfc8  mov     [rbp+0FD0h+var_CB0], rax
0x14063cfcf  lea     rax, VfZwDeleteValueKey_Entry
0x14063cfd6  mov     [rbp+0FD0h+var_CA0], rax
0x14063cfdd  lea     rax, aZwloadkey; "ZwLoadKey"
0x14063cfe4  mov     [rbp+0FD0h+var_C90], rax
0x14063cfeb  lea     rax, VfZwLoadKey_Entry
0x14063cff2  mov     [rbp+0FD0h+var_C80], rax
0x14063cff9  lea     rax, aZwmapviewofsec; "ZwMapViewOfSection"
0x14063d000  mov     [rbp+0FD0h+var_C70], rax
0x14063d007  lea     rax, VfZwMapViewOfSection_Entry
0x14063d00e  mov     [rbp+0FD0h+var_C60], rax
0x14063d015  lea     rax, aZwmodifybooten; "ZwModifyBootEntry"
0x14063d01c  mov     [rbp+0FD0h+var_C50], rax
0x14063d023  lea     rax, VfZwAlpcCreateSecurityContext_Entry
0x14063d02a  mov     [rbp+0FD0h+var_C40], rax
0x14063d031  lea     rax, aZwmodifydriver_0; "ZwModifyDriverEntry"
0x14063d038  mov     [rbp+0FD0h+var_C30], rax
0x14063d03f  lea     rax, VfZwAlpcCreateSecurityContext_Entry
0x14063d046  mov     [rbp+0FD0h+var_C20], rax
0x14063d04d  lea     rax, aZwnotifychange_3; "ZwNotifyChangeKey"
0x14063d054  mov     [rbp+0FD0h+var_C10], rax
0x14063d05b  lea     rax, VfZwNotifyChangeKey_Entry
0x14063d062  mov     [rbp+0FD0h+var_C00], rax
0x14063d069  lea     rax, aZwopendirector_0; "ZwOpenDirectoryObject"
0x14063d070  mov     [rbp+0FD0h+var_BF0], rax
0x14063d077  lea     rax, VfZwOpenKey_Entry
0x14063d07e  mov     [rbp+0FD0h+var_BE0], rax
0x14063d085  lea     rax, aZwopenevent; "ZwOpenEvent"
0x14063d08c  mov     [rbp+0FD0h+var_BD0], rax
0x14063d093  lea     rax, VfZwOpenKey_Entry
0x14063d09a  mov     [rbp+0FD0h+var_BC0], rax
0x14063d0a1  lea     rax, aZwopenfile; "ZwOpenFile"
0x14063d0a8  mov     [rbp+0FD0h+var_D58], rcx
0x14063d0af  mov     [rbp+0FD0h+var_D48], 67h ; 'g'
0x14063d0b9  mov     [rbp+0FD0h+var_D38], rcx
0x14063d0c0  mov     [rbp+0FD0h+var_D28], 64h ; 'd'
0x14063d0ca  mov     [rbp+0FD0h+var_D18], rcx
0x14063d0d1  mov     [rbp+0FD0h+var_D08], 62h ; 'b'
0x14063d0db  mov     [rbp+0FD0h+var_CF8], rcx
0x14063d0e2  mov     [rbp+0FD0h+var_CE8], 61h ; 'a'
0x14063d0ec  mov     [rbp+0FD0h+var_CD8], rcx
0x14063d0f3  mov     [rbp+0FD0h+var_CC8], 60h ; '`'
0x14063d0fd  mov     [rbp+0FD0h+var_CB8], rcx
0x14063d104  mov     [rbp+0FD0h+var_CA8], 5Eh ; '^'
0x14063d10e  mov     [rbp+0FD0h+var_C98], rcx
0x14063d115  mov     [rbp+0FD0h+var_C88], 5Dh ; ']'
0x14063d11f  mov     [rbp+0FD0h+var_C78], rcx
0x14063d126  mov     [rbp+0FD0h+var_C68], 5Ch ; '\'
0x14063d130  mov     [rbp+0FD0h+var_C58], rcx
0x14063d137  mov     [rbp+0FD0h+var_C48], 5Bh ; '['
0x14063d141  mov     [rbp+0FD0h+var_C38], rcx
0x14063d148  mov     [rbp+0FD0h+var_C28], 5Ah ; 'Z'
0x14063d152  mov     [rbp+0FD0h+var_C18], rcx
0x14063d159  mov     [rbp+0FD0h+var_C08], 59h ; 'Y'
0x14063d163  mov     [rbp+0FD0h+var_BF8], rcx
0x14063d16a  mov     [rbp+0FD0h+var_BE8], 58h ; 'X'
0x14063d174  mov     [rbp+0FD0h+var_BD8], rcx
0x14063d17b  mov     [rbp+0FD0h+var_BC8], 56h ; 'V'
0x14063d185  mov     [rbp+0FD0h+var_BB8], rcx
0x14063d18c  mov     [rbp+0FD0h+var_BB0], rax
0x14063d193  lea     rax, VfZwOpenFile_Entry
0x14063d19a  mov     [rbp+0FD0h+var_BA0], rax
0x14063d1a1  lea     rax, aZwopenjobobjec; "ZwOpenJobObject"
0x14063d1a8  mov     [rbp+0FD0h+var_B90], rax
0x14063d1af  lea     rax, VfZwOpenKey_Entry
0x14063d1b6  mov     [rbp+0FD0h+var_B80], rax
0x14063d1bd  lea     rax, aZwopenkey; "ZwOpenKey"
0x14063d1c4  mov     [rbp+0FD0h+var_B70], rax
0x14063d1cb  lea     rax, VfZwOpenKey_Entry
0x14063d1d2  mov     [rbp+0FD0h+var_B60], rax
0x14063d1d9  lea     rax, aZwopenprocess_0; "ZwOpenProcess"
0x14063d1e0  mov     [rbp+0FD0h+var_B50], rax
0x14063d1e7  lea     rax, VfZwOpenThread_Entry
0x14063d1ee  mov     [rbp+0FD0h+var_B40], rax
0x14063d1f5  lea     rax, aZwopenprocesst; "ZwOpenProcessToken"
0x14063d1fc  mov     [rbp+0FD0h+var_B30], rax
0x14063d203  lea     rax, VfZwAlpcCreateSecurityContext_Entry
0x14063d20a  mov     [rbp+0FD0h+var_B20], rax
0x14063d211  lea     rax, aZwopenprocesst_1; "ZwOpenProcessTokenEx"
0x14063d218  mov     [rbp+0FD0h+var_B10], rax
0x14063d21f  lea     rax, VfZwAlpcCreateSecurityContext_Entry
0x14063d226  mov     [rbp+0FD0h+var_B00], rax
0x14063d22d  lea     rax, aZwopensection; "ZwOpenSection"
0x14063d234  mov     [rbp+0FD0h+var_AF0], rax
0x14063d23b  lea     rax, VfZwOpenKey_Entry
0x14063d242  mov     [rbp+0FD0h+var_AE0], rax
0x14063d249  lea     rax, aZwopensymbolic_0; "ZwOpenSymbolicLinkObject"
0x14063d250  mov     [rbp+0FD0h+var_AD0], rax
0x14063d257  lea     rax, VfZwOpenKey_Entry
0x14063d25e  mov     [rbp+0FD0h+var_AC0], rax
0x14063d265  lea     rax, aZwopenthread_0; "ZwOpenThread"
0x14063d26c  mov     [rbp+0FD0h+var_AB0], rax
0x14063d273  lea     rax, VfZwOpenThread_Entry
0x14063d27a  mov     [rbp+0FD0h+var_AA0], rax
0x14063d281  lea     rax, aZwopenthreadto_1; "ZwOpenThreadToken"
0x14063d288  mov     [rbp+0FD0h+var_A90], rax
0x14063d28f  lea     rax, VfZwAlpcCreateSecurityContext_Entry
0x14063d296  mov     [rbp+0FD0h+var_A80], rax
0x14063d29d  lea     rax, aZwopenthreadto; "ZwOpenThreadTokenEx"
0x14063d2a4  mov     [rbp+0FD0h+var_A70], rax
0x14063d2ab  lea     rax, VfZwAlpcCreateSecurityContext_Entry
0x14063d2b2  mov     [rbp+0FD0h+var_A60], rax
0x14063d2b9  lea     rax, aZwopentimer_0; "ZwOpenTimer"
0x14063d2c0  mov     [rbp+0FD0h+var_A50], rax
0x14063d2c7  lea     rax, VfZwOpenKey_Entry
0x14063d2ce  mov     [rbp+0FD0h+var_A40], rax
0x14063d2d5  lea     rax, aZwpowerinforma; "ZwPowerInformation"
0x14063d2dc  mov     [rbp+0FD0h+var_A30], rax
0x14063d2e3  lea     rax, VfZwPowerInformation_Entry
0x14063d2ea  mov     [rbp+0FD0h+var_A20], rax
  ... truncated ...
```
