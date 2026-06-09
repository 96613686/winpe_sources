# SdbOpenDatabaseEx

- ea: `0x14081f9a4`
- end: `0x14081fcc7`
- name: `SdbOpenDatabaseEx`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140824034`

## callees

- `0x1406d9d70`
- `0x1406f4880`
- `0x14081f820`
- `0x14081f9a4`
- `0x1408208b8`
- `0x140824db8`
- `0x1408266d4`
- `0x140826b74`
- `0x140827228`
- `0x14097888c`
- `0x140979890`
- `0x14097a240`
- `0x14097b68c`
- `0x14097cedc`
- `0x14097d158`
- `0x140ab538c`

## string_xrefs

- `0x14081fad5`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x14081fb00`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`
- `0x14081f9c4`: `SdbOpenDatabaseEx`
- `0x14081fae6`: `SdbOpenDatabaseEx`
- `0x14081fb12`: `SdbOpenDatabaseEx`
- `0x14081fb6b`: `SdbOpenDatabaseEx`
- `0x14081fc49`: `SdbOpenDatabaseEx`
- `0x14081fc88`: `SdbOpenDatabaseEx`
- `0x14081f9df`: `Flags:%d; DatabasePath:%ws`
- `0x14081fc3c`: `SdbpOpenCompressedDatabase failed to open compressed database.`
- `0x14081fbee`: `Failed to read database header`
- `0x14081fc7b`: `Failed to open SDB - File size too large or small.`
- `0x14081fb5e`: `Failed to create file mapping [%x]`

## pseudocode

```c
_QWORD *__fastcall SdbOpenDatabaseEx(const wchar_t *a1)
{
  const wchar_t *v2; // rax
  __int64 v3; // rcx
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  int MergeRedirectPath; // eax
  __int64 v7; // rcx
  int v8; // r14d
  int v9; // ebx
  __int64 FileNamePart; // rax
  int v11; // eax
  int v12; // eax
  const char *v13; // r9
  int v14; // r8d
  __int64 v15; // r14
  __int64 v16; // rbx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-48h]
  int v22; // [rsp+30h] [rbp-38h] BYREF
  __int64 v23; // [rsp+38h] [rbp-30h] BYREF
  _QWORD *v24; // [rsp+40h] [rbp-28h] BYREF
  __int64 v25; // [rsp+48h] [rbp-20h] BYREF
  int v26; // [rsp+50h] [rbp-18h]

  v25 = 0;
  v26 = 0;
  v22 = 0;
  v2 = a1;
  if ( !a1 )
    v2 = &cchOriginalDestLength;
  AslLogCallPrintf(3, (unsigned int)"SdbOpenDatabaseEx", 2501, (unsigned int)"Flags:%d; DatabasePath:%ws", 0, v2);
  v4 = (_QWORD *)AslAlloc(v3, 2688);
  v24 = v4;
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0xA80u);
    v23 = 0;
    MergeRedirectPath = SdbGetMergeRedirectPath(&v23, &v22, 1, a1);
    v8 = MergeRedirectPath;
    if ( MergeRedirectPath < 0 )
    {
      if ( MergeRedirectPath != -1073741772 )
      {
        LODWORD(v21) = MergeRedirectPath;
        AslLogCallPrintf(
          3,
          (unsigned int)"SdbOpenDatabaseEx",
          2527,
          (unsigned int)"SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]",
          v21);
      }
      v9 = v8;
    }
    else if ( v23 )
    {
      if ( v22 )
      {
        FileNamePart = AslPathGetFileNamePart(a1);
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbOpenDatabaseEx",
          2539,
          (unsigned int)"Handled Error: MergeSdb staged deletion feature was used to prevent sdb mismatch error. SdbName: [%ls].",
          FileNamePart);
      }
      v11 = AslFileMappingCreate((_DWORD)v5, v23, 0, 0, 0);
      v9 = v11;
      if ( v11 < 0 )
      {
        LODWORD(v21) = v11;
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbOpenDatabaseEx",
          2558,
          (unsigned int)"Failed to create file mapping for redirected SDB file [%x]",
          v21);
      }
    }
    else
    {
      v9 = -1073741772;
    }
    if ( v23 )
      AslFree(v7, v23);
    if ( v9 < 0 || !*v5 )
    {
      v12 = AslFileMappingCreate((_DWORD)v5, (_DWORD)a1, 0, 0, 0);
      if ( v12 < 0 )
      {
        v13 = "Failed to create file mapping [%x]";
        v14 = 2580;
LABEL_21:
        LODWORD(v21) = v12;
        AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", v14, (_DWORD)v13, v21);
        goto LABEL_37;
      }
    }
    v15 = *(_QWORD *)(*v5 + 24LL);
    if ( (unsigned __int64)(v15 - 42) > 0xFFFFFD5 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbOpenDatabaseEx",
        2589,
        (unsigned int)"Failed to open SDB - File size too large or small.");
    }
    else
    {
      v16 = *v5;
      LOBYTE(v17) = SdbpShouldMapSdbToKernelMemory();
      v12 = AslFileMappingEnsureMappedAsEx(v16, v18, v17);
      if ( v12 < 0 )
      {
        v13 = "Failed to map SDB [%x]";
        v14 = 2595;
        goto LABEL_21;
      }
      *((_DWORD *)v5 + 4) = 0;
      *((_DWORD *)v5 + 5) = v15;
      v5[1] = AslFileMappingGetViewBase(*v5);
      if ( !(unsigned int)SdbpReadMappedData(v5, 0, &v25, 12) )
      {
        AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", 2608, (unsigned int)"Failed to read database header");
        goto LABEL_37;
      }
      v12 = v26;
      if ( v26 != 1717724275 )
      {
        if ( v26 != 1717724282 )
        {
          v13 = "Magic does not match a valid value: 0x%lx";
          v14 = 2621;
          goto LABEL_21;
        }
        if ( !(unsigned int)SdbpOpenCompressedDatabase(&v24, 0, 0) )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbOpenDatabaseEx",
            2627,
            (unsigned int)"SdbpOpenCompressedDatabase failed to open compressed database.");
          v5 = v24;
          goto LABEL_37;
        }
        return v24;
      }
      if ( (unsigned int)SdbpValidateAndApplyCompatFlags(v5, &v25, 0) )
        return v5;
    }
LABEL_37:
    if ( v5 )
    {
      AslFileMappingDelete(*v5);
      AslFree(v20, v5);
    }
    return 0;
  }
  AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", 2509, (unsigned int)"Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x14081f9a4  push    rbp
0x14081f9a6  push    rbx
0x14081f9a7  push    rsi
0x14081f9a8  push    rdi
0x14081f9a9  push    r12
0x14081f9ab  push    r14
0x14081f9ad  mov     rbp, rsp
0x14081f9b0  sub     rsp, 68h
0x14081f9b4  mov     rax, cs:__security_cookie
0x14081f9bb  xor     rax, rsp
0x14081f9be  mov     [rbp+var_10], rax
0x14081f9c2  xor     eax, eax
0x14081f9c4  lea     rbx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x14081f9cb  mov     r12, rcx
0x14081f9ce  mov     [rbp+var_20], rax
0x14081f9d2  mov     [rbp+var_18], eax
0x14081f9d5  lea     rcx, cchOriginalDestLength
0x14081f9dc  mov     [rbp+var_38], eax
0x14081f9df  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x14081f9e6  test    r12, r12
0x14081f9e9  mov     rax, r12
0x14081f9ec  mov     r8d, 9C5h
0x14081f9f2  mov     rdx, rbx
0x14081f9f5  cmovz   rax, rcx
0x14081f9f9  mov     ecx, 3
0x14081f9fe  mov     [rsp+68h+var_40], rax
0x14081fa03  mov     dword ptr [rsp+68h+var_48], 0
0x14081fa0b  call    AslLogCallPrintf
0x14081fa10  mov     esi, 0A80h
0x14081fa15  mov     edx, esi
0x14081fa17  call    AslAlloc
0x14081fa1c  mov     [rbp+var_28], rax
0x14081fa20  mov     rdi, rax
0x14081fa23  test    rax, rax
0x14081fa26  jnz     short loc_14081FA45
0x14081fa28  lea     r9, aFailedToAlloca_9; "Failed to allocate DB structure"
0x14081fa2f  mov     r8d, 9CDh
0x14081fa35  mov     rdx, rbx
0x14081fa38  lea     ecx, [rax+1]
0x14081fa3b  call    AslLogCallPrintf
0x14081fa40  jmp     loc_14081FCAB
0x14081fa45  mov     r8, rsi; Size
0x14081fa48  xor     edx, edx; Val
0x14081fa4a  mov     rcx, rdi; void *
0x14081fa4d  call    memset_0
0x14081fa52  mov     esi, 1
0x14081fa57  mov     [rbp+var_30], 0
0x14081fa5f  mov     r8d, esi
0x14081fa62  lea     rdx, [rbp+var_38]
0x14081fa66  mov     r9, r12
0x14081fa69  lea     rcx, [rbp+var_30]
0x14081fa6d  call    SdbGetMergeRedirectPath
0x14081fa72  mov     r14d, eax
0x14081fa75  test    eax, eax
0x14081fa77  js      short loc_14081FAF6
0x14081fa79  cmp     [rbp+var_30], 0
0x14081fa7e  jnz     short loc_14081FA8A
0x14081fa80  mov     ebx, 0C0000034h
0x14081fa85  jmp     loc_14081FB26
0x14081fa8a  cmp     [rbp+var_38], 0
0x14081fa8e  jz      short loc_14081FAB4
0x14081fa90  mov     rcx, r12
0x14081fa93  call    AslPathGetFileNamePart
0x14081fa98  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x14081fa9f  mov     [rsp+68h+var_48], rax
0x14081faa4  mov     r8d, 9EBh
0x14081faaa  mov     rdx, rbx
0x14081faad  mov     ecx, esi
0x14081faaf  call    AslLogCallPrintf
0x14081fab4  mov     rdx, [rbp+var_30]
0x14081fab8  xor     r9d, r9d
0x14081fabb  xor     r8d, r8d
0x14081fabe  mov     [rsp+68h+var_48], 0
0x14081fac7  mov     rcx, rdi
0x14081faca  call    AslFileMappingCreate
0x14081facf  mov     ebx, eax
0x14081fad1  test    eax, eax
0x14081fad3  jns     short loc_14081FB26
0x14081fad5  lea     r9, aFailedToCreate_0; "Failed to create file mapping for redir"...
0x14081fadc  mov     dword ptr [rsp+68h+var_48], eax
0x14081fae0  mov     r8d, 9FEh
0x14081fae6  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x14081faed  mov     ecx, esi
0x14081faef  call    AslLogCallPrintf
0x14081faf4  jmp     short loc_14081FB26
0x14081faf6  mov     ebx, 0C0000034h
0x14081fafb  cmp     r14d, ebx
0x14081fafe  jz      short loc_14081FB23
0x14081fb00  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x14081fb07  mov     dword ptr [rsp+68h+var_48], r14d
0x14081fb0c  mov     r8d, 9DFh
0x14081fb12  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x14081fb19  mov     ecx, 3
0x14081fb1e  call    AslLogCallPrintf
0x14081fb23  mov     ebx, r14d
0x14081fb26  cmp     [rbp+var_30], 0
0x14081fb2b  jz      short loc_14081FB36
0x14081fb2d  mov     rdx, [rbp+var_30]
0x14081fb31  call    AslFree
0x14081fb36  test    ebx, ebx
0x14081fb38  js      short loc_14081FB40
0x14081fb3a  cmp     qword ptr [rdi], 0
0x14081fb3e  jnz     short loc_14081FB82
0x14081fb40  xor     r9d, r9d
0x14081fb43  mov     [rsp+68h+var_48], 0
0x14081fb4c  xor     r8d, r8d
0x14081fb4f  mov     rdx, r12
0x14081fb52  mov     rcx, rdi
0x14081fb55  call    AslFileMappingCreate
0x14081fb5a  test    eax, eax
0x14081fb5c  jns     short loc_14081FB82
0x14081fb5e  lea     r9, aFailedToCreate; "Failed to create file mapping [%x]"
0x14081fb65  mov     r8d, 0A14h
0x14081fb6b  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x14081fb72  mov     dword ptr [rsp+68h+var_48], eax
0x14081fb76  mov     ecx, esi
0x14081fb78  call    AslLogCallPrintf
0x14081fb7d  jmp     loc_14081FC96
0x14081fb82  mov     rax, [rdi]
0x14081fb85  mov     r14, [rax+18h]
0x14081fb89  lea     rax, [r14-2Ah]
0x14081fb8d  cmp     rax, 0FFFFFD5h
0x14081fb93  ja      loc_14081FC7B
0x14081fb99  mov     rbx, [rdi]
0x14081fb9c  call    SdbpShouldMapSdbToKernelMemory
0x14081fba1  mov     r8b, al
0x14081fba4  mov     rcx, rbx
0x14081fba7  call    AslFileMappingEnsureMappedAsEx
0x14081fbac  test    eax, eax
0x14081fbae  jns     short loc_14081FBBF
0x14081fbb0  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x14081fbb7  mov     r8d, 0A23h
0x14081fbbd  jmp     short loc_14081FB6B
0x14081fbbf  mov     dword ptr [rdi+10h], 0
0x14081fbc6  mov     [rdi+14h], r14d
0x14081fbca  mov     rcx, [rdi]
0x14081fbcd  call    AslFileMappingGetViewBase
0x14081fbd2  mov     r9d, 0Ch
0x14081fbd8  mov     [rdi+8], rax
0x14081fbdc  lea     r8, [rbp+var_20]
0x14081fbe0  xor     edx, edx
0x14081fbe2  mov     rcx, rdi
0x14081fbe5  call    SdbpReadMappedData
0x14081fbea  test    eax, eax
0x14081fbec  jnz     short loc_14081FC00
0x14081fbee  lea     r9, aFailedToReadDa_0; "Failed to read database header"
0x14081fbf5  mov     r8d, 0A30h
0x14081fbfb  jmp     loc_14081FC88
0x14081fc00  mov     eax, [rbp+var_18]
0x14081fc03  cmp     eax, 66626473h
0x14081fc08  jz      short loc_14081FC23
0x14081fc0a  cmp     eax, 6662647Ah
0x14081fc0f  jz      short loc_14081FC2A
0x14081fc11  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x14081fc18  mov     r8d, 0A3Dh
0x14081fc1e  jmp     loc_14081FB6B
0x14081fc23  cmp     eax, 6662647Ah
0x14081fc28  jnz     short loc_14081FC63
0x14081fc2a  xor     r8d, r8d
0x14081fc2d  lea     rcx, [rbp+var_28]
0x14081fc31  xor     edx, edx
0x14081fc33  call    SdbpOpenCompressedDatabase
0x14081fc38  test    eax, eax
0x14081fc3a  jnz     short loc_14081FC5D
0x14081fc3c  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x14081fc43  mov     r8d, 0A43h
0x14081fc49  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x14081fc50  mov     ecx, esi
0x14081fc52  call    AslLogCallPrintf
0x14081fc57  mov     rdi, [rbp+var_28]
0x14081fc5b  jmp     short loc_14081FC96
0x14081fc5d  mov     rdi, [rbp+var_28]
0x14081fc61  jmp     short loc_14081FC76
0x14081fc63  xor     r8d, r8d
0x14081fc66  lea     rdx, [rbp+var_20]
0x14081fc6a  mov     rcx, rdi
0x14081fc6d  call    SdbpValidateAndApplyCompatFlags
0x14081fc72  test    eax, eax
0x14081fc74  jz      short loc_14081FC96
0x14081fc76  mov     rax, rdi
0x14081fc79  jmp     short loc_14081FCAD
0x14081fc7b  lea     r9, aFailedToOpenSd; "Failed to open SDB - File size too larg"...
0x14081fc82  mov     r8d, 0A1Dh
0x14081fc88  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x14081fc8f  mov     ecx, esi
0x14081fc91  call    AslLogCallPrintf
0x14081fc96  test    rdi, rdi
0x14081fc99  jz      short loc_14081FCAB
0x14081fc9b  mov     rcx, [rdi]
0x14081fc9e  call    AslFileMappingDelete
0x14081fca3  mov     rdx, rdi
0x14081fca6  call    AslFree
0x14081fcab  xor     eax, eax
0x14081fcad  mov     rcx, [rbp+var_10]
0x14081fcb1  xor     rcx, rsp; StackCookie
0x14081fcb4  call    __security_check_cookie
0x14081fcb9  add     rsp, 68h
0x14081fcbd  pop     r14
0x14081fcbf  pop     r12
0x14081fcc1  pop     rdi
0x14081fcc2  pop     rsi
0x14081fcc3  pop     rbx
0x14081fcc4  pop     rbp
0x14081fcc5  retn
```
