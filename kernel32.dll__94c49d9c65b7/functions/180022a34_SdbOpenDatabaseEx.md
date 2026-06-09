# SdbOpenDatabaseEx

- ea: `0x180022a34`
- end: `0x180022d9b`
- name: `SdbOpenDatabaseEx`
- size: `871`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800222e0`
- `0x180075148`

## callees

- `0x180021144`
- `0x1800211bc`
- `0x1800212e4`
- `0x1800218bc`
- `0x180022a34`
- `0x180022da4`
- `0x180024068`
- `0x1800243c4`
- `0x180041f80`
- `0x18004b768`
- `0x180071850`
- `0x1800797d0`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180022abf`
- `ntdll!RtlAllocateHeap` at `0x180022abf`

## string_xrefs

- `0x180022a5e`: `Flags:%d; DatabasePath:%ws`
- `0x180022a79`: `SdbOpenDatabaseEx`
- `0x180022ade`: `SdbOpenDatabaseEx`
- `0x180022b73`: `SdbOpenDatabaseEx`
- `0x180022bb0`: `SdbOpenDatabaseEx`
- `0x180022bdc`: `SdbOpenDatabaseEx`
- `0x180022c33`: `SdbOpenDatabaseEx`
- `0x180022d05`: `SdbOpenDatabaseEx`
- `0x180022d44`: `SdbOpenDatabaseEx`
- `0x180022b9f`: `Failed to create file mapping for redirected SDB file [%x]`
- `0x180022bca`: `SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]`
- `0x180022ca7`: `Failed to read database header`
- `0x180022c26`: `Failed to create file mapping [%x]`
- `0x180022d37`: `Failed to open SDB - File size too large or small.`
- `0x180022cf8`: `SdbpOpenCompressedDatabase failed to open compressed database.`

## pseudocode

```c
_QWORD *__fastcall SdbOpenDatabaseEx(const WCHAR *a1, __int64 a2, unsigned int a3)
{
  const WCHAR *v5; // rax
  _QWORD *Heap; // rax
  _QWORD *v7; // rbx
  int MergeRedirectPath; // r14d
  int v9; // esi
  const char *v10; // r9
  int v11; // r8d
  __int64 v12; // rsi
  __int64 v13; // rdx
  const WCHAR *v16; // [rsp+28h] [rbp-38h]
  int v17; // [rsp+30h] [rbp-30h] BYREF
  __int64 v18; // [rsp+38h] [rbp-28h] BYREF
  _QWORD *v19; // [rsp+40h] [rbp-20h] BYREF
  __int64 v20; // [rsp+48h] [rbp-18h] BYREF
  int v21; // [rsp+50h] [rbp-10h]

  v20 = 0;
  v21 = 0;
  v17 = 0;
  v5 = a1;
  if ( !a1 )
    v5 = &word_180086D5C;
  v16 = v5;
  AslLogCallPrintf(3, (unsigned int)"SdbOpenDatabaseEx", 2501, (unsigned int)"Flags:%d; DatabasePath:%ws");
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xA80u);
  v19 = Heap;
  v7 = Heap;
  if ( Heap )
  {
    memset_0(Heap, 0, 0xA80u);
    v18 = 0;
    if ( (a3 & 0x10) != 0 )
      goto LABEL_23;
    MergeRedirectPath = SdbGetMergeRedirectPath(&v18, &v17, (a3 & 0x20) == 0, a1, a3, v16);
    if ( MergeRedirectPath < 0 )
    {
      if ( MergeRedirectPath != -1073741772 )
        AslLogCallPrintf(
          3,
          (unsigned int)"SdbOpenDatabaseEx",
          2527,
          (unsigned int)"SdbGetMergeRedirectPath failed to check for sdb merge redirect [%x]");
      v9 = MergeRedirectPath;
    }
    else if ( v18 )
    {
      if ( (a3 & 0x20) != 0 )
      {
        if ( !v17 )
          *((_DWORD *)v7 + 6) |= 0x20u;
      }
      else if ( v17 )
      {
        AslPathGetFileNamePart(a1);
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbOpenDatabaseEx",
          2539,
          (unsigned int)"Handled Error: MergeSdb staged deletion feature was used to prevent sdb mismatch error. SdbName: [%ls].");
      }
      v9 = AslFileMappingCreate(v7, v18);
      if ( v9 < 0 )
        AslLogCallPrintf(
          1,
          (unsigned int)"SdbOpenDatabaseEx",
          2558,
          (unsigned int)"Failed to create file mapping for redirected SDB file [%x]");
    }
    else
    {
      v9 = -1073741772;
    }
    if ( v18 )
      AslFree(NtCurrentPeb()->ProcessHeap, v18);
    if ( v9 < 0 || !*v7 )
    {
LABEL_23:
      if ( (int)AslFileMappingCreate(v7, a1) < 0 )
      {
        v10 = "Failed to create file mapping [%x]";
        v11 = 2580;
LABEL_41:
        AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", v11, (_DWORD)v10);
LABEL_42:
        if ( v7 )
        {
          AslFileMappingDelete(*v7);
          AslFree(NtCurrentPeb()->ProcessHeap, v7);
        }
        return 0;
      }
    }
    v12 = *(_QWORD *)(*v7 + 24LL);
    if ( (unsigned __int64)(v12 - 42) > 0xFFFFFD5 )
    {
      v10 = "Failed to open SDB - File size too large or small.";
      v11 = 2589;
      goto LABEL_41;
    }
    if ( (int)AslFileMappingEnsureMappedAsEx() < 0 )
    {
      v10 = "Failed to map SDB [%x]";
      v11 = 2595;
      goto LABEL_41;
    }
    *((_DWORD *)v7 + 4) = 0;
    *((_DWORD *)v7 + 5) = v12;
    v7[1] = AslFileMappingGetViewBase(*v7);
    if ( !(unsigned int)SdbpReadMappedData(v7, 0, &v20, 12) )
    {
      v10 = "Failed to read database header";
      v11 = 2608;
      goto LABEL_41;
    }
    if ( v21 != 1717724275 )
    {
      if ( v21 == 1717724282 )
      {
        if ( !(unsigned int)SdbpOpenCompressedDatabase(&v19, v13, a3) )
        {
          AslLogCallPrintf(
            1,
            (unsigned int)"SdbOpenDatabaseEx",
            2627,
            (unsigned int)"SdbpOpenCompressedDatabase failed to open compressed database.");
          v7 = v19;
          goto LABEL_42;
        }
        return v19;
      }
      if ( (a3 & 2) == 0 )
      {
        v10 = "Magic does not match a valid value: 0x%lx";
        v11 = 2621;
        goto LABEL_41;
      }
    }
    if ( !(unsigned int)SdbpValidateAndApplyCompatFlags(v7, &v20, a3) )
      goto LABEL_42;
    return v7;
  }
  AslLogCallPrintf(1, (unsigned int)"SdbOpenDatabaseEx", 2509, (unsigned int)"Failed to allocate DB structure");
  return 0;
}

```

## disassembly

```asm
0x180022a34  mov     r11, rsp
0x180022a37  mov     [r11+10h], rbx
0x180022a3b  mov     [r11+20h], rsi
0x180022a3f  push    rbp
0x180022a40  push    rdi
0x180022a41  push    r12
0x180022a43  push    r13
0x180022a45  push    r14
0x180022a47  mov     rbp, rsp
0x180022a4a  sub     rsp, 60h
0x180022a4e  mov     rax, cs:__security_cookie
0x180022a55  xor     rax, rsp
0x180022a58  mov     [rbp+var_8], rax
0x180022a5c  xor     eax, eax
0x180022a5e  lea     r9, aFlagsDDatabase; "Flags:%d; DatabasePath:%ws"
0x180022a65  mov     r13, rcx
0x180022a68  mov     [rbp+var_18], rax
0x180022a6c  mov     [rbp+var_10], eax
0x180022a6f  lea     rcx, word_180086D5C
0x180022a76  mov     [rbp+var_30], eax
0x180022a79  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180022a80  mov     r12d, r8d
0x180022a83  test    r13, r13
0x180022a86  mov     rax, r13
0x180022a89  cmovz   rax, rcx
0x180022a8d  mov     ecx, 3
0x180022a92  mov     [r11-60h], rax
0x180022a96  mov     [r11-68h], r8d
0x180022a9a  mov     r8d, 9C5h
0x180022aa0  call    AslLogCallPrintf
0x180022aa5  mov     rcx, gs:60h
0x180022aae  mov     edi, 0A80h
0x180022ab3  mov     r8d, edi; Size
0x180022ab6  mov     edx, 8; Flags
0x180022abb  mov     rcx, [rcx+30h]; HeapHandle
0x180022abf  call    cs:__imp_RtlAllocateHeap
0x180022ac5  mov     [rbp+var_20], rax
0x180022ac9  mov     rbx, rax
0x180022acc  test    rax, rax
0x180022acf  jnz     short loc_180022AF2
0x180022ad1  lea     r9, aFailedToAlloca_10; "Failed to allocate DB structure"
0x180022ad8  mov     r8d, 9CDh
0x180022ade  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180022ae5  lea     ecx, [rax+1]
0x180022ae8  call    AslLogCallPrintf
0x180022aed  jmp     loc_180022D74
0x180022af2  mov     r8, rdi; Size
0x180022af5  xor     edx, edx; Val
0x180022af7  mov     rcx, rbx; void *
0x180022afa  call    memset_0
0x180022aff  mov     [rbp+var_28], 0
0x180022b07  mov     edi, 1
0x180022b0c  test    r12b, 10h
0x180022b10  jnz     loc_180022C17
0x180022b16  lea     r8d, [rdi-1]
0x180022b1a  mov     esi, r12d
0x180022b1d  and     esi, 20h
0x180022b20  lea     rdx, [rbp+var_30]
0x180022b24  mov     r9, r13
0x180022b27  lea     rcx, [rbp+var_28]
0x180022b2b  setz    r8b
0x180022b2f  call    SdbGetMergeRedirectPath
0x180022b34  mov     r14d, eax
0x180022b37  test    eax, eax
0x180022b39  js      loc_180022BC0
0x180022b3f  cmp     [rbp+var_28], 0
0x180022b44  jnz     short loc_180022B50
0x180022b46  mov     esi, 0C0000034h
0x180022b4b  jmp     loc_180022BF0
0x180022b50  test    esi, esi
0x180022b52  jnz     short loc_180022B83
0x180022b54  cmp     [rbp+var_30], esi
0x180022b57  jz      short loc_180022B8D
0x180022b59  mov     rcx, r13
0x180022b5c  call    AslPathGetFileNamePart
0x180022b61  lea     r9, aHandledErrorMe; "Handled Error: MergeSdb staged deletion"...
0x180022b68  mov     [rsp+60h+var_40], rax
0x180022b6d  mov     r8d, 9EBh
0x180022b73  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180022b7a  mov     ecx, edi
0x180022b7c  call    AslLogCallPrintf
0x180022b81  jmp     short loc_180022B8D
0x180022b83  cmp     [rbp+var_30], 0
0x180022b87  jnz     short loc_180022B8D
0x180022b89  or      dword ptr [rbx+18h], 20h
0x180022b8d  mov     rdx, [rbp+var_28]
0x180022b91  mov     rcx, rbx
0x180022b94  call    AslFileMappingCreate
0x180022b99  mov     esi, eax
0x180022b9b  test    eax, eax
0x180022b9d  jns     short loc_180022BF0
0x180022b9f  lea     r9, aFailedToCreate_0; "Failed to create file mapping for redir"...
0x180022ba6  mov     dword ptr [rsp+60h+var_40], eax
0x180022baa  mov     r8d, 9FEh
0x180022bb0  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180022bb7  mov     ecx, edi
0x180022bb9  call    AslLogCallPrintf
0x180022bbe  jmp     short loc_180022BF0
0x180022bc0  mov     esi, 0C0000034h
0x180022bc5  cmp     r14d, esi
0x180022bc8  jz      short loc_180022BED
0x180022bca  lea     r9, aSdbgetmergered; "SdbGetMergeRedirectPath failed to check"...
0x180022bd1  mov     dword ptr [rsp+60h+var_40], r14d
0x180022bd6  mov     r8d, 9DFh
0x180022bdc  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180022be3  mov     ecx, 3
0x180022be8  call    AslLogCallPrintf
0x180022bed  mov     esi, r14d
0x180022bf0  cmp     [rbp+var_28], 0
0x180022bf5  jz      short loc_180022C0D
0x180022bf7  mov     rcx, gs:60h
0x180022c00  mov     rdx, [rbp+var_28]
0x180022c04  mov     rcx, [rcx+30h]
0x180022c08  call    AslFree
0x180022c0d  test    esi, esi
0x180022c0f  js      short loc_180022C17
0x180022c11  cmp     qword ptr [rbx], 0
0x180022c15  jnz     short loc_180022C4A
0x180022c17  mov     rdx, r13
0x180022c1a  mov     rcx, rbx
0x180022c1d  call    AslFileMappingCreate
0x180022c22  test    eax, eax
0x180022c24  jns     short loc_180022C4A
0x180022c26  lea     r9, aFailedToCreate; "Failed to create file mapping [%x]"
0x180022c2d  mov     r8d, 0A14h
0x180022c33  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180022c3a  mov     dword ptr [rsp+60h+var_40], eax
0x180022c3e  mov     ecx, edi
0x180022c40  call    AslLogCallPrintf
0x180022c45  jmp     loc_180022D52
0x180022c4a  mov     rcx, [rbx]
0x180022c4d  mov     rsi, [rcx+18h]
0x180022c51  lea     rax, [rsi-2Ah]
0x180022c55  cmp     rax, 0FFFFFD5h
0x180022c5b  ja      loc_180022D37
0x180022c61  call    AslFileMappingEnsureMappedAsEx
0x180022c66  test    eax, eax
0x180022c68  jns     short loc_180022C79
0x180022c6a  lea     r9, aFailedToMapSdb; "Failed to map SDB [%x]"
0x180022c71  mov     r8d, 0A23h
0x180022c77  jmp     short loc_180022C33
0x180022c79  mov     dword ptr [rbx+10h], 0
0x180022c80  mov     [rbx+14h], esi
0x180022c83  mov     rcx, [rbx]
0x180022c86  call    AslFileMappingGetViewBase
0x180022c8b  mov     r9d, 0Ch
0x180022c91  mov     [rbx+8], rax
0x180022c95  lea     r8, [rbp+var_18]
0x180022c99  xor     edx, edx
0x180022c9b  mov     rcx, rbx
0x180022c9e  call    SdbpReadMappedData
0x180022ca3  test    eax, eax
0x180022ca5  jnz     short loc_180022CB9
0x180022ca7  lea     r9, aFailedToReadDa_0; "Failed to read database header"
0x180022cae  mov     r8d, 0A30h
0x180022cb4  jmp     loc_180022D44
0x180022cb9  mov     eax, [rbp+var_10]
0x180022cbc  mov     ecx, 6662647Ah
0x180022cc1  cmp     eax, 66626473h
0x180022cc6  jz      short loc_180022CE4
0x180022cc8  cmp     eax, ecx
0x180022cca  jz      short loc_180022CE8
0x180022ccc  test    r12b, 2
0x180022cd0  jnz     short loc_180022CE4
0x180022cd2  lea     r9, aMagicDoesNotMa_0; "Magic does not match a valid value: 0x%"...
0x180022cd9  mov     r8d, 0A3Dh
0x180022cdf  jmp     loc_180022C33
0x180022ce4  cmp     eax, ecx
0x180022ce6  jnz     short loc_180022D1F
0x180022ce8  mov     r8d, r12d
0x180022ceb  lea     rcx, [rbp+var_20]
0x180022cef  call    SdbpOpenCompressedDatabase
0x180022cf4  test    eax, eax
0x180022cf6  jnz     short loc_180022D19
0x180022cf8  lea     r9, aSdbpopencompre; "SdbpOpenCompressedDatabase failed to op"...
0x180022cff  mov     r8d, 0A43h
0x180022d05  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180022d0c  mov     ecx, edi
0x180022d0e  call    AslLogCallPrintf
0x180022d13  mov     rbx, [rbp+var_20]
0x180022d17  jmp     short loc_180022D52
0x180022d19  mov     rbx, [rbp+var_20]
0x180022d1d  jmp     short loc_180022D32
0x180022d1f  mov     r8d, r12d
0x180022d22  lea     rdx, [rbp+var_18]
0x180022d26  mov     rcx, rbx
0x180022d29  call    SdbpValidateAndApplyCompatFlags
0x180022d2e  test    eax, eax
0x180022d30  jz      short loc_180022D52
0x180022d32  mov     rax, rbx
0x180022d35  jmp     short loc_180022D76
0x180022d37  lea     r9, aFailedToOpenSd; "Failed to open SDB - File size too larg"...
0x180022d3e  mov     r8d, 0A1Dh
0x180022d44  lea     rdx, aSdbopendatabas; "SdbOpenDatabaseEx"
0x180022d4b  mov     ecx, edi
0x180022d4d  call    AslLogCallPrintf
0x180022d52  test    rbx, rbx
0x180022d55  jz      short loc_180022D74
0x180022d57  mov     rcx, [rbx]
0x180022d5a  call    AslFileMappingDelete
0x180022d5f  mov     rcx, gs:60h
0x180022d68  mov     rdx, rbx
0x180022d6b  mov     rcx, [rcx+30h]
0x180022d6f  call    AslFree
0x180022d74  xor     eax, eax
0x180022d76  mov     rcx, [rbp+var_8]
0x180022d7a  xor     rcx, rsp; StackCookie
0x180022d7d  call    __security_check_cookie
0x180022d82  lea     r11, [rsp+60h+var_s0]
0x180022d87  mov     rbx, [r11+38h]
0x180022d8b  mov     rsi, [r11+48h]
0x180022d8f  mov     rsp, r11
0x180022d92  pop     r14
0x180022d94  pop     r13
0x180022d96  pop     r12
0x180022d98  pop     rdi
0x180022d99  pop     rbp
0x180022d9a  retn
```
