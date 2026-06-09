# SdbOpenDatabaseEx

- ea: `0x140821914`
- end: `0x140821c37`
- name: `SdbOpenDatabaseEx`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140825fa4`

## callees

- `0x1406dc8c0`
- `0x1406f7380`
- `0x140821790`
- `0x140821914`
- `0x140822828`
- `0x140826d28`
- `0x140828644`
- `0x140828ae4`
- `0x140829198`
- `0x1408be654`
- `0x1408bf658`
- `0x1408c0070`
- `0x1408c14bc`
- `0x1408c2d0c`
- `0x1408c2f88`
- `0x140aba90c`

## string_xrefs

- `0x140821b5e`: `Failed to read database header`
- `0x140821bac`: `SdbpOpenCompressedDatabase failed to open compressed database.`
- `0x140821a45`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x140821beb`: `Failed to open SDB - File size too large or small.`
- `0x140821ace`: `Failed to create file mapping [%x]`
- `0x140821934`: `SdbOpenDatabaseEx`
- `0x140821a56`: `SdbOpenDatabaseEx`
- `0x140821a82`: `SdbOpenDatabaseEx`
- `0x140821adb`: `SdbOpenDatabaseEx`
- `0x140821bb9`: `SdbOpenDatabaseEx`
- `0x140821bf8`: `SdbOpenDatabaseEx`
- `0x14082194f`: `Flags:%d; DatabasePath:%ws`
- `0x140821a70`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`

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
  AslLogCallPrintf(3, (unsigned int)"SdbOpenDatabaseEx", 2499, (unsigned int)"Flags:%d; DatabasePath:%ws", 0, v2);
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
          2525,
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
          2537,
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
          2556,
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
        v14 = 2578;
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
        2587,
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
        v14 = 2593;
        goto LABEL_21;
      }
      *((_DWORD *)v5 + 4) = 0;
      *((_DWORD *)v5 + 5) = v15;
      v5[1] = AslFileMappingGetViewBase(*v5);
      if ( !(unsigned int)SdbpReadMappedData(v5, 0, &v25, 12) )
      {
        AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", 2606, (unsigned int)"Failed to read database header");
        goto LABEL_37;
      }
      v12 = v26;
      if ( v26 != 1717724275 )
      {
        if ( v26 != 1717724282 )
        {
          v13 = "Magic does not match a valid value: 0x%lx";
          v14 = 2619;
          goto LABEL_21;
        }
        if ( !(unsigned int)SdbpOpenCompressedDatabase(&v24, 0, 0) )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbOpenDatabaseEx",
            2625,
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
  AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", 2507, (unsigned int)"Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x140821914  push    rbp
0x140821916  push    rbx
0x140821917  push    rsi
0x140821918  push    rdi
0x140821919  push    r12
0x14082191b  push    r14
0x14082191d  mov     rbp, rsp
0x140821920  sub     rsp, 68h
0x140821924  mov     rax, cs:__security_cookie
0x14082192b  xor     rax, rsp
0x14082192e  mov     [rbp+var_10], rax
0x140821932  xor     eax, eax
0x140821934  lea     rbx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x14082193b  mov     r12, rcx
0x14082193e  mov     [rbp+var_20], rax
0x140821942  mov     [rbp+var_18], eax
0x140821945  lea     rcx, cchOriginalDestLength
0x14082194c  mov     [rbp+var_38], eax
0x14082194f  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x140821956  test    r12, r12
0x140821959  mov     rax, r12
0x14082195c  mov     r8d, 9C3h
0x140821962  mov     rdx, rbx
0x140821965  cmovz   rax, rcx
0x140821969  mov     ecx, 3
0x14082196e  mov     [rsp+68h+var_40], rax
0x140821973  mov     dword ptr [rsp+68h+var_48], 0
0x14082197b  call    AslLogCallPrintf
0x140821980  mov     esi, 0A80h
0x140821985  mov     edx, esi
0x140821987  call    AslAlloc
0x14082198c  mov     [rbp+var_28], rax
0x140821990  mov     rdi, rax
0x140821993  test    rax, rax
0x140821996  jnz     short loc_1408219B5
0x140821998  lea     r9, aFailedToAlloca_9; "Failed to allocate DB structure"
0x14082199f  mov     r8d, 9CBh
0x1408219a5  mov     rdx, rbx
0x1408219a8  lea     ecx, [rax+1]
0x1408219ab  call    AslLogCallPrintf
0x1408219b0  jmp     loc_140821C1B
0x1408219b5  mov     r8, rsi; Size
0x1408219b8  xor     edx, edx; Val
0x1408219ba  mov     rcx, rdi; void *
0x1408219bd  call    memset_0
0x1408219c2  mov     esi, 1
0x1408219c7  mov     [rbp+var_30], 0
0x1408219cf  mov     r8d, esi
0x1408219d2  lea     rdx, [rbp+var_38]
0x1408219d6  mov     r9, r12
0x1408219d9  lea     rcx, [rbp+var_30]
0x1408219dd  call    SdbGetMergeRedirectPath
0x1408219e2  mov     r14d, eax
0x1408219e5  test    eax, eax
0x1408219e7  js      short loc_140821A66
0x1408219e9  cmp     [rbp+var_30], 0
0x1408219ee  jnz     short loc_1408219FA
0x1408219f0  mov     ebx, 0C0000034h
0x1408219f5  jmp     loc_140821A96
0x1408219fa  cmp     [rbp+var_38], 0
0x1408219fe  jz      short loc_140821A24
0x140821a00  mov     rcx, r12
0x140821a03  call    AslPathGetFileNamePart
0x140821a08  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x140821a0f  mov     [rsp+68h+var_48], rax
0x140821a14  mov     r8d, 9E9h
0x140821a1a  mov     rdx, rbx
0x140821a1d  mov     ecx, esi
0x140821a1f  call    AslLogCallPrintf
0x140821a24  mov     rdx, [rbp+var_30]
0x140821a28  xor     r9d, r9d
0x140821a2b  xor     r8d, r8d
0x140821a2e  mov     [rsp+68h+var_48], 0
0x140821a37  mov     rcx, rdi
0x140821a3a  call    AslFileMappingCreate
0x140821a3f  mov     ebx, eax
0x140821a41  test    eax, eax
0x140821a43  jns     short loc_140821A96
0x140821a45  lea     r9, aFailedToCreate_0; "Failed to create file mapping for redir"...
0x140821a4c  mov     dword ptr [rsp+68h+var_48], eax
0x140821a50  mov     r8d, 9FCh
0x140821a56  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140821a5d  mov     ecx, esi
0x140821a5f  call    AslLogCallPrintf
0x140821a64  jmp     short loc_140821A96
0x140821a66  mov     ebx, 0C0000034h
0x140821a6b  cmp     r14d, ebx
0x140821a6e  jz      short loc_140821A93
0x140821a70  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x140821a77  mov     dword ptr [rsp+68h+var_48], r14d
0x140821a7c  mov     r8d, 9DDh
0x140821a82  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140821a89  mov     ecx, 3
0x140821a8e  call    AslLogCallPrintf
0x140821a93  mov     ebx, r14d
0x140821a96  cmp     [rbp+var_30], 0
0x140821a9b  jz      short loc_140821AA6
0x140821a9d  mov     rdx, [rbp+var_30]
0x140821aa1  call    AslFree
0x140821aa6  test    ebx, ebx
0x140821aa8  js      short loc_140821AB0
0x140821aaa  cmp     qword ptr [rdi], 0
0x140821aae  jnz     short loc_140821AF2
0x140821ab0  xor     r9d, r9d
0x140821ab3  mov     [rsp+68h+var_48], 0
0x140821abc  xor     r8d, r8d
0x140821abf  mov     rdx, r12
0x140821ac2  mov     rcx, rdi
0x140821ac5  call    AslFileMappingCreate
0x140821aca  test    eax, eax
0x140821acc  jns     short loc_140821AF2
0x140821ace  lea     r9, aFailedToCreate; "Failed to create file mapping [%x]"
0x140821ad5  mov     r8d, 0A12h
0x140821adb  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140821ae2  mov     dword ptr [rsp+68h+var_48], eax
0x140821ae6  mov     ecx, esi
0x140821ae8  call    AslLogCallPrintf
0x140821aed  jmp     loc_140821C06
0x140821af2  mov     rax, [rdi]
0x140821af5  mov     r14, [rax+18h]
0x140821af9  lea     rax, [r14-2Ah]
0x140821afd  cmp     rax, 0FFFFFD5h
0x140821b03  ja      loc_140821BEB
0x140821b09  mov     rbx, [rdi]
0x140821b0c  call    SdbpShouldMapSdbToKernelMemory
0x140821b11  mov     r8b, al
0x140821b14  mov     rcx, rbx
0x140821b17  call    AslFileMappingEnsureMappedAsEx
0x140821b1c  test    eax, eax
0x140821b1e  jns     short loc_140821B2F
0x140821b20  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x140821b27  mov     r8d, 0A21h
0x140821b2d  jmp     short loc_140821ADB
0x140821b2f  mov     dword ptr [rdi+10h], 0
0x140821b36  mov     [rdi+14h], r14d
0x140821b3a  mov     rcx, [rdi]
0x140821b3d  call    AslFileMappingGetViewBase
0x140821b42  mov     r9d, 0Ch
0x140821b48  mov     [rdi+8], rax
0x140821b4c  lea     r8, [rbp+var_20]
0x140821b50  xor     edx, edx
0x140821b52  mov     rcx, rdi
0x140821b55  call    SdbpReadMappedData
0x140821b5a  test    eax, eax
0x140821b5c  jnz     short loc_140821B70
0x140821b5e  lea     r9, aFailedToReadDa_0; "Failed to read database header"
0x140821b65  mov     r8d, 0A2Eh
0x140821b6b  jmp     loc_140821BF8
0x140821b70  mov     eax, [rbp+var_18]
0x140821b73  cmp     eax, 66626473h
0x140821b78  jz      short loc_140821B93
0x140821b7a  cmp     eax, 6662647Ah
0x140821b7f  jz      short loc_140821B9A
0x140821b81  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x140821b88  mov     r8d, 0A3Bh
0x140821b8e  jmp     loc_140821ADB
0x140821b93  cmp     eax, 6662647Ah
0x140821b98  jnz     short loc_140821BD3
0x140821b9a  xor     r8d, r8d
0x140821b9d  lea     rcx, [rbp+var_28]
0x140821ba1  xor     edx, edx
0x140821ba3  call    SdbpOpenCompressedDatabase
0x140821ba8  test    eax, eax
0x140821baa  jnz     short loc_140821BCD
0x140821bac  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x140821bb3  mov     r8d, 0A41h
0x140821bb9  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140821bc0  mov     ecx, esi
0x140821bc2  call    AslLogCallPrintf
0x140821bc7  mov     rdi, [rbp+var_28]
0x140821bcb  jmp     short loc_140821C06
0x140821bcd  mov     rdi, [rbp+var_28]
0x140821bd1  jmp     short loc_140821BE6
0x140821bd3  xor     r8d, r8d
0x140821bd6  lea     rdx, [rbp+var_20]
0x140821bda  mov     rcx, rdi
0x140821bdd  call    SdbpValidateAndApplyCompatFlags
0x140821be2  test    eax, eax
0x140821be4  jz      short loc_140821C06
0x140821be6  mov     rax, rdi
0x140821be9  jmp     short loc_140821C1D
0x140821beb  lea     r9, aFailedToOpenSd; "Failed to open SDB - File size too larg"...
0x140821bf2  mov     r8d, 0A1Bh
0x140821bf8  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x140821bff  mov     ecx, esi
0x140821c01  call    AslLogCallPrintf
0x140821c06  test    rdi, rdi
0x140821c09  jz      short loc_140821C1B
0x140821c0b  mov     rcx, [rdi]
0x140821c0e  call    AslFileMappingDelete
0x140821c13  mov     rdx, rdi
0x140821c16  call    AslFree
0x140821c1b  xor     eax, eax
0x140821c1d  mov     rcx, [rbp+var_10]
0x140821c21  xor     rcx, rsp; StackCookie
0x140821c24  call    __security_check_cookie
0x140821c29  add     rsp, 68h
0x140821c2d  pop     r14
0x140821c2f  pop     r12
0x140821c31  pop     rdi
0x140821c32  pop     rsi
0x140821c33  pop     rbx
0x140821c34  pop     rbp
0x140821c35  retn
```
