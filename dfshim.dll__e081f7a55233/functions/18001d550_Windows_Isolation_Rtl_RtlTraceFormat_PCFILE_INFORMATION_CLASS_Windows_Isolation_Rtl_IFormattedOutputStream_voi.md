# Windows::Isolation::Rtl::RtlTraceFormat_PCFILE_INFORMATION_CLASS(Windows::Isolation::Rtl::_IFormattedOutputStream *,void const *)

- ea: `0x18001d550`
- end: `0x18001d8bc`
- name: `?RtlTraceFormat_PCFILE_INFORMATION_CLASS@Rtl@Isolation@Windows@@YAXPEAU_IFormattedOutputStream@123@PEBX@Z`
- size: `876`
- prototype: `void __fastcall(Windows::Isolation::Rtl *__hidden this, struct Windows::Isolation::Rtl::_IFormattedOutputStream *, const void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x18001d550`
- `0x18012a020`

## string_xrefs

- `0x18001d5e7`: `FileDirectoryInformation`
- `0x18001d5db`: `FileFullDirectoryInformation`
- `0x18001d5cf`: `FileBothDirectoryInformation`
- `0x18001d642`: `FileAccessInformation`
- `0x18001d62a`: `FileRenameInformation`
- `0x18001d61e`: `FileLinkInformation`
- `0x18001d75f`: `FileCompressionInformation`
- `0x18001d7f6`: `FileCompletionInformation`
- `0x18001d7ea`: `FileMoveClusterInformation`
- `0x18001d7d2`: `FileReparsePointInformation`
- `0x18001d7c6`: `FileNetworkOpenInformation`
- `0x18001d84b`: `FileIdBothDirectoryInformation`
- `0x18001d842`: `FileIdFullDirectoryInformation`
- `0x18001d8a6`: `FileIoCompletionNotificationInformation`

## pseudocode

```c
void __fastcall Windows::Isolation::Rtl::RtlTraceFormat_PCFILE_INFORMATION_CLASS(
        Windows::Isolation::Rtl *this,
        struct Windows::Isolation::Rtl::_IFormattedOutputStream *a2,
        const void *a3)
{
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  const char *v8; // rdx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // edx
  int v24; // edx
  int v25; // edx
  int v26; // edx
  int v27; // edx
  int v28; // edx
  int v29; // edx
  int v30; // edx
  int v31; // edx
  int v32; // edx
  int v33; // edx
  int v34; // edx

  if ( !a2 )
  {
    (*(void (__fastcall **)(Windows::Isolation::Rtl *, __int64, const char *))(*(_QWORD *)this + 200LL))(
      this,
      6,
      "(null)");
    return;
  }
  if ( *(int *)a2 > 23 )
  {
    if ( *(int *)a2 > 35 )
    {
      if ( *(int *)a2 > 41 )
      {
        v32 = *(_DWORD *)a2 - 42;
        if ( !v32 )
        {
          v8 = "FileIoCompletionNotificationInformation";
          goto LABEL_101;
        }
        v33 = v32 - 1;
        if ( !v33 )
        {
          v8 = "FileIoStatusBlockRangeInformation";
          goto LABEL_101;
        }
        v34 = v33 - 1;
        if ( !v34 )
        {
          v8 = "FileSfioReserveInformation";
          goto LABEL_101;
        }
        if ( v34 == 1 )
        {
          v8 = "FileSfioPriorityHintInformation";
          goto LABEL_101;
        }
      }
      else
      {
        if ( *(_DWORD *)a2 == 41 )
        {
          v8 = "FileAvioInformation";
          goto LABEL_101;
        }
        v28 = *(_DWORD *)a2 - 36;
        if ( !v28 )
        {
          v8 = "FileTrackingInformation";
          goto LABEL_101;
        }
        v29 = v28 - 1;
        if ( !v29 )
        {
          v8 = "FileIdBothDirectoryInformation";
          goto LABEL_101;
        }
        v30 = v29 - 1;
        if ( !v30 )
        {
          v8 = "FileIdFullDirectoryInformation";
          goto LABEL_101;
        }
        v31 = v30 - 1;
        if ( !v31 )
        {
          v8 = "FileValidDataLengthInformation";
          goto LABEL_101;
        }
        if ( v31 == 1 )
        {
          v8 = "FileShortNameInformation";
          goto LABEL_101;
        }
      }
    }
    else
    {
      if ( *(_DWORD *)a2 == 35 )
      {
        v8 = "FileAttributeTagInformation";
        goto LABEL_101;
      }
      if ( *(int *)a2 > 29 )
      {
        v24 = *(_DWORD *)a2 - 30;
        if ( !v24 )
        {
          v8 = "FileCompletionInformation";
          goto LABEL_101;
        }
        v25 = v24 - 1;
        if ( !v25 )
        {
          v8 = "FileMoveClusterInformation";
          goto LABEL_101;
        }
        v26 = v25 - 1;
        if ( !v26 )
        {
          v8 = "FileQuotaInformation";
          goto LABEL_101;
        }
        v27 = v26 - 1;
        if ( !v27 )
        {
          v8 = "FileReparsePointInformation";
          goto LABEL_101;
        }
        if ( v27 == 1 )
        {
          v8 = "FileNetworkOpenInformation";
          goto LABEL_101;
        }
      }
      else
      {
        if ( *(_DWORD *)a2 == 29 )
        {
          v8 = "FileObjectIdInformation";
          goto LABEL_101;
        }
        v20 = *(_DWORD *)a2 - 24;
        if ( !v20 )
        {
          v8 = "FilePipeLocalInformation";
          goto LABEL_101;
        }
        v21 = v20 - 1;
        if ( !v21 )
        {
          v8 = "FilePipeRemoteInformation";
          goto LABEL_101;
        }
        v22 = v21 - 1;
        if ( !v22 )
        {
          v8 = "FileMailslotQueryInformation";
          goto LABEL_101;
        }
        v23 = v22 - 1;
        if ( !v23 )
        {
          v8 = "FileMailslotSetInformation";
          goto LABEL_101;
        }
        if ( v23 == 1 )
        {
          v8 = "FileCompressionInformation";
          goto LABEL_101;
        }
      }
    }
    goto LABEL_96;
  }
  if ( *(_DWORD *)a2 == 23 )
  {
    v8 = "FilePipeInformation";
    goto LABEL_101;
  }
  if ( *(int *)a2 > 12 )
  {
    if ( *(int *)a2 > 18 )
    {
      v17 = *(_DWORD *)a2 - 19;
      if ( !v17 )
      {
        v8 = "FileAllocationInformation";
        goto LABEL_101;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        v8 = "FileEndOfFileInformation";
        goto LABEL_101;
      }
      v19 = v18 - 1;
      if ( !v19 )
      {
        v8 = "FileAlternateNameInformation";
        goto LABEL_101;
      }
      if ( v19 == 1 )
      {
        v8 = "FileStreamInformation";
        goto LABEL_101;
      }
    }
    else
    {
      if ( *(_DWORD *)a2 == 18 )
      {
        v8 = "FileAllInformation";
        goto LABEL_101;
      }
      v13 = *(_DWORD *)a2 - 13;
      if ( !v13 )
      {
        v8 = "FileDispositionInformation";
        goto LABEL_101;
      }
      v14 = v13 - 1;
      if ( !v14 )
      {
        v8 = "FilePositionInformation";
        goto LABEL_101;
      }
      v15 = v14 - 1;
      if ( !v15 )
      {
        v8 = "FileFullEaInformation";
        goto LABEL_101;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        v8 = "FileModeInformation";
        goto LABEL_101;
      }
      if ( v16 == 1 )
      {
        v8 = "FileAlignmentInformation";
        goto LABEL_101;
      }
    }
    goto LABEL_96;
  }
  if ( *(_DWORD *)a2 == 12 )
  {
    v8 = "FileNamesInformation";
    goto LABEL_101;
  }
  if ( *(int *)a2 > 6 )
  {
    v9 = *(_DWORD *)a2 - 7;
    if ( !v9 )
    {
      v8 = "FileEaInformation";
      goto LABEL_101;
    }
    v10 = v9 - 1;
    if ( !v10 )
    {
      v8 = "FileAccessInformation";
      goto LABEL_101;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v8 = "FileNameInformation";
      goto LABEL_101;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v8 = "FileRenameInformation";
      goto LABEL_101;
    }
    if ( v12 == 1 )
    {
      v8 = "FileLinkInformation";
      goto LABEL_101;
    }
    goto LABEL_96;
  }
  if ( *(_DWORD *)a2 == 6 )
  {
    v8 = "FileInternalInformation";
    goto LABEL_101;
  }
  v4 = *(_DWORD *)a2 - 1;
  if ( !v4 )
  {
    v8 = "FileDirectoryInformation";
    goto LABEL_101;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v8 = "FileFullDirectoryInformation";
    goto LABEL_101;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v8 = "FileBothDirectoryInformation";
    goto LABEL_101;
  }
  v7 = v6 - 1;
  if ( !v7 )
  {
    v8 = "FileBasicInformation";
    goto LABEL_101;
  }
  if ( v7 != 1 )
  {
LABEL_96:
    (*(void (__fastcall **)(Windows::Isolation::Rtl *, _QWORD))(*(_QWORD *)this + 56LL))(this, *(unsigned int *)a2);
    return;
  }
  v8 = "FileStandardInformation";
LABEL_101:
  (*(void (__fastcall **)(Windows::Isolation::Rtl *, const char *, struct Windows::Isolation::Rtl::_IFormattedOutputStream *))(*(_QWORD *)this + 168LL))(
    this,
    v8,
    a2);
}

```

## disassembly

```asm
0x18001d550  mov     r8, rdx
0x18001d553  test    rdx, rdx
0x18001d556  jnz     short loc_18001D573
0x18001d558  mov     rax, [rcx]
0x18001d55b  lea     r8, aNull; "(null)"
0x18001d562  mov     edx, 6
0x18001d567  mov     rax, [rax+0C8h]
0x18001d56e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18001d573  cmp     dword ptr [rdx], 17h
0x18001d576  jg      loc_18001D72A
0x18001d57c  jz      loc_18001D71E
0x18001d582  cmp     dword ptr [rdx], 0Ch
0x18001d585  jg      loc_18001D666
0x18001d58b  jz      loc_18001D65A
0x18001d591  cmp     dword ptr [rdx], 6
0x18001d594  jg      short loc_18001D5FF
0x18001d596  jz      short loc_18001D5F3
0x18001d598  mov     edx, [rdx]
0x18001d59a  sub     edx, 1
0x18001d59d  jz      short loc_18001D5E7
0x18001d59f  sub     edx, 1
0x18001d5a2  jz      short loc_18001D5DB
0x18001d5a4  sub     edx, 1
0x18001d5a7  jz      short loc_18001D5CF
0x18001d5a9  sub     edx, 1
0x18001d5ac  jz      short loc_18001D5C3
0x18001d5ae  cmp     edx, 1
0x18001d5b1  jnz     loc_18001D87C
0x18001d5b7  lea     rdx, aFilestandardin; "FileStandardInformation"
0x18001d5be  jmp     loc_18001D8AD
0x18001d5c3  lea     rdx, aFilebasicinfor; "FileBasicInformation"
0x18001d5ca  jmp     loc_18001D8AD
0x18001d5cf  lea     rdx, aFilebothdirect; "FileBothDirectoryInformation"
0x18001d5d6  jmp     loc_18001D8AD
0x18001d5db  lea     rdx, aFilefulldirect; "FileFullDirectoryInformation"
0x18001d5e2  jmp     loc_18001D8AD
0x18001d5e7  lea     rdx, aFiledirectoryi; "FileDirectoryInformation"
0x18001d5ee  jmp     loc_18001D8AD
0x18001d5f3  lea     rdx, aFileinternalin; "FileInternalInformation"
0x18001d5fa  jmp     loc_18001D8AD
0x18001d5ff  mov     edx, [rdx]
0x18001d601  sub     edx, 7
0x18001d604  jz      short loc_18001D64E
0x18001d606  sub     edx, 1
0x18001d609  jz      short loc_18001D642
0x18001d60b  sub     edx, 1
0x18001d60e  jz      short loc_18001D636
0x18001d610  sub     edx, 1
0x18001d613  jz      short loc_18001D62A
0x18001d615  cmp     edx, 1
0x18001d618  jnz     loc_18001D87C
0x18001d61e  lea     rdx, aFilelinkinform; "FileLinkInformation"
0x18001d625  jmp     loc_18001D8AD
0x18001d62a  lea     rdx, aFilerenameinfo; "FileRenameInformation"
0x18001d631  jmp     loc_18001D8AD
0x18001d636  lea     rdx, aFilenameinform; "FileNameInformation"
0x18001d63d  jmp     loc_18001D8AD
0x18001d642  lea     rdx, aFileaccessinfo; "FileAccessInformation"
0x18001d649  jmp     loc_18001D8AD
0x18001d64e  lea     rdx, aFileeainformat; "FileEaInformation"
0x18001d655  jmp     loc_18001D8AD
0x18001d65a  lea     rdx, aFilenamesinfor; "FileNamesInformation"
0x18001d661  jmp     loc_18001D8AD
0x18001d666  cmp     dword ptr [rdx], 12h
0x18001d669  jg      short loc_18001D6D4
0x18001d66b  jz      short loc_18001D6C8
0x18001d66d  mov     edx, [rdx]
0x18001d66f  sub     edx, 0Dh
0x18001d672  jz      short loc_18001D6BC
0x18001d674  sub     edx, 1
0x18001d677  jz      short loc_18001D6B0
0x18001d679  sub     edx, 1
0x18001d67c  jz      short loc_18001D6A4
0x18001d67e  sub     edx, 1
0x18001d681  jz      short loc_18001D698
0x18001d683  cmp     edx, 1
0x18001d686  jnz     loc_18001D87C
0x18001d68c  lea     rdx, aFilealignmenti; "FileAlignmentInformation"
0x18001d693  jmp     loc_18001D8AD
0x18001d698  lea     rdx, aFilemodeinform; "FileModeInformation"
0x18001d69f  jmp     loc_18001D8AD
0x18001d6a4  lea     rdx, aFilefulleainfo; "FileFullEaInformation"
0x18001d6ab  jmp     loc_18001D8AD
0x18001d6b0  lea     rdx, aFilepositionin; "FilePositionInformation"
0x18001d6b7  jmp     loc_18001D8AD
0x18001d6bc  lea     rdx, aFiledispositio; "FileDispositionInformation"
0x18001d6c3  jmp     loc_18001D8AD
0x18001d6c8  lea     rdx, aFileallinforma; "FileAllInformation"
0x18001d6cf  jmp     loc_18001D8AD
0x18001d6d4  mov     edx, [rdx]
0x18001d6d6  sub     edx, 13h
0x18001d6d9  jz      short loc_18001D712
0x18001d6db  sub     edx, 1
0x18001d6de  jz      short loc_18001D706
0x18001d6e0  sub     edx, 1
0x18001d6e3  jz      short loc_18001D6FA
0x18001d6e5  cmp     edx, 1
0x18001d6e8  jnz     loc_18001D87C
0x18001d6ee  lea     rdx, aFilestreaminfo; "FileStreamInformation"
0x18001d6f5  jmp     loc_18001D8AD
0x18001d6fa  lea     rdx, aFilealternaten; "FileAlternateNameInformation"
0x18001d701  jmp     loc_18001D8AD
0x18001d706  lea     rdx, aFileendoffilei; "FileEndOfFileInformation"
0x18001d70d  jmp     loc_18001D8AD
0x18001d712  lea     rdx, aFileallocation; "FileAllocationInformation"
0x18001d719  jmp     loc_18001D8AD
0x18001d71e  lea     rdx, aFilepipeinform; "FilePipeInformation"
0x18001d725  jmp     loc_18001D8AD
0x18001d72a  cmp     dword ptr [rdx], 23h ; '#'
0x18001d72d  jg      loc_18001D80E
0x18001d733  jz      loc_18001D802
0x18001d739  cmp     dword ptr [rdx], 1Dh
0x18001d73c  jg      short loc_18001D7A7
0x18001d73e  jz      short loc_18001D79B
0x18001d740  mov     edx, [rdx]
0x18001d742  sub     edx, 18h
0x18001d745  jz      short loc_18001D78F
0x18001d747  sub     edx, 1
0x18001d74a  jz      short loc_18001D783
0x18001d74c  sub     edx, 1
0x18001d74f  jz      short loc_18001D777
0x18001d751  sub     edx, 1
0x18001d754  jz      short loc_18001D76B
0x18001d756  cmp     edx, 1
0x18001d759  jnz     loc_18001D87C
0x18001d75f  lea     rdx, aFilecompressio; "FileCompressionInformation"
0x18001d766  jmp     loc_18001D8AD
0x18001d76b  lea     rdx, aFilemailslotse; "FileMailslotSetInformation"
0x18001d772  jmp     loc_18001D8AD
0x18001d777  lea     rdx, aFilemailslotqu; "FileMailslotQueryInformation"
0x18001d77e  jmp     loc_18001D8AD
0x18001d783  lea     rdx, aFilepiperemote; "FilePipeRemoteInformation"
0x18001d78a  jmp     loc_18001D8AD
0x18001d78f  lea     rdx, aFilepipelocali; "FilePipeLocalInformation"
0x18001d796  jmp     loc_18001D8AD
0x18001d79b  lea     rdx, aFileobjectidin; "FileObjectIdInformation"
0x18001d7a2  jmp     loc_18001D8AD
0x18001d7a7  mov     edx, [rdx]
0x18001d7a9  sub     edx, 1Eh
0x18001d7ac  jz      short loc_18001D7F6
0x18001d7ae  sub     edx, 1
0x18001d7b1  jz      short loc_18001D7EA
0x18001d7b3  sub     edx, 1
0x18001d7b6  jz      short loc_18001D7DE
0x18001d7b8  sub     edx, 1
0x18001d7bb  jz      short loc_18001D7D2
0x18001d7bd  cmp     edx, 1
0x18001d7c0  jnz     loc_18001D87C
0x18001d7c6  lea     rdx, aFilenetworkope; "FileNetworkOpenInformation"
0x18001d7cd  jmp     loc_18001D8AD
0x18001d7d2  lea     rdx, aFilereparsepoi; "FileReparsePointInformation"
0x18001d7d9  jmp     loc_18001D8AD
0x18001d7de  lea     rdx, aFilequotainfor; "FileQuotaInformation"
0x18001d7e5  jmp     loc_18001D8AD
0x18001d7ea  lea     rdx, aFilemovecluste; "FileMoveClusterInformation"
0x18001d7f1  jmp     loc_18001D8AD
0x18001d7f6  lea     rdx, aFilecompletion; "FileCompletionInformation"
0x18001d7fd  jmp     loc_18001D8AD
0x18001d802  lea     rdx, aFileattributet; "FileAttributeTagInformation"
0x18001d809  jmp     loc_18001D8AD
0x18001d80e  cmp     dword ptr [rdx], 29h ; ')'
0x18001d811  jg      short loc_18001D866
0x18001d813  jz      short loc_18001D85D
0x18001d815  mov     edx, [rdx]
0x18001d817  sub     edx, 24h ; '$'
0x18001d81a  jz      short loc_18001D854
0x18001d81c  sub     edx, 1
0x18001d81f  jz      short loc_18001D84B
0x18001d821  sub     edx, 1
0x18001d824  jz      short loc_18001D842
0x18001d826  sub     edx, 1
0x18001d829  jz      short loc_18001D839
0x18001d82b  cmp     edx, 1
0x18001d82e  jnz     short loc_18001D87C
0x18001d830  lea     rdx, aFileshortnamei; "FileShortNameInformation"
0x18001d837  jmp     short loc_18001D8AD
0x18001d839  lea     rdx, aFilevaliddatal; "FileValidDataLengthInformation"
0x18001d840  jmp     short loc_18001D8AD
0x18001d842  lea     rdx, aFileidfulldire; "FileIdFullDirectoryInformation"
0x18001d849  jmp     short loc_18001D8AD
0x18001d84b  lea     rdx, aFileidbothdire; "FileIdBothDirectoryInformation"
0x18001d852  jmp     short loc_18001D8AD
0x18001d854  lea     rdx, aFiletrackingin; "FileTrackingInformation"
0x18001d85b  jmp     short loc_18001D8AD
0x18001d85d  lea     rdx, aFileavioinform; "FileAvioInformation"
0x18001d864  jmp     short loc_18001D8AD
0x18001d866  mov     edx, [rdx]
0x18001d868  sub     edx, 2Ah ; '*'
0x18001d86b  jz      short loc_18001D8A6
0x18001d86d  sub     edx, 1
0x18001d870  jz      short loc_18001D89D
0x18001d872  sub     edx, 1
0x18001d875  jz      short loc_18001D894
0x18001d877  cmp     edx, 1
0x18001d87a  jz      short loc_18001D88B
0x18001d87c  mov     rax, [rcx]
0x18001d87f  mov     edx, [r8]
0x18001d882  mov     rax, [rax+38h]
0x18001d886  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x18001d88b  lea     rdx, aFilesfiopriori; "FileSfioPriorityHintInformation"
0x18001d892  jmp     short loc_18001D8AD
0x18001d894  lea     rdx, aFilesfioreserv; "FileSfioReserveInformation"
0x18001d89b  jmp     short loc_18001D8AD
0x18001d89d  lea     rdx, aFileiostatusbl; "FileIoStatusBlockRangeInformation"
0x18001d8a4  jmp     short loc_18001D8AD
0x18001d8a6  lea     rdx, aFileiocompleti; "FileIoCompletionNotificationInformation"
0x18001d8ad  mov     rax, [rcx]
0x18001d8b0  mov     rax, [rax+0A8h]
0x18001d8b7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
