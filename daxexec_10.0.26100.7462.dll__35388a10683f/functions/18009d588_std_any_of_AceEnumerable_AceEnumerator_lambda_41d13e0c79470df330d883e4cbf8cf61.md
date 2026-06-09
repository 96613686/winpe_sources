# std::any_of_AceEnumerable::AceEnumerator__lambda_41d13e0c79470df330d883e4cbf8cf61___

- ea: `0x18009d588`
- end: `0x18009d756`
- name: `std::any_of_AceEnumerable::AceEnumerator__lambda_41d13e0c79470df330d883e4cbf8cf61___`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009d890`

## callees

- `0x180013100`
- `0x18002031c`
- `0x18009d588`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009d6d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009d6d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d69d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d6ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d69d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009d6ff`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009d5c7`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009d5c7`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009d5f5`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009d5f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009d620`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009d620`
- `api-ms-win-security-sddlparsecond-l1-1-0!LocalGetStringForCondition` at `0x18009d66d`
- `api-ms-win-security-sddlparsecond-l1-1-0!LocalGetStringForCondition` at `0x18009d66d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall std::any_of_AceEnumerable::AceEnumerator__lambda_41d13e0c79470df330d883e4cbf8cf61___(
        __int64 a1,
        __int128 *a2,
        __int64 a3)
{
  DWORD i; // esi
  const char *v5; // r9
  _DWORD *v6; // rbx
  DWORD LengthSid; // eax
  __int64 v8; // rdx
  unsigned int StringForCondition; // eax
  __int64 v10; // rbx
  const WCHAR *v11; // r8
  char v12; // bl
  PACL pAcl[2]; // [rsp+40h] [rbp-40h]
  __int128 v15; // [rsp+50h] [rbp-30h]
  WCHAR *v16; // [rsp+68h] [rbp-18h] BYREF
  char v17; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  WCHAR *lpString1; // [rsp+B0h] [rbp+30h]
  LPVOID pAce; // [rsp+B8h] [rbp+38h] BYREF

  *(_OWORD *)pAcl = *(_OWORD *)a1;
  v15 = *a2;
  for ( i = *(_QWORD *)(a1 + 8); i != DWORD2(v15); ++i )
  {
    pAce = 0;
    if ( !GetAce(pAcl[0], i, &pAce) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\packageinformation.cpp",
        v5);
    v6 = pAce;
    if ( *(_BYTE *)pAce == 9 && IsWellKnownSid((char *)pAce + 8, WinBuiltinUsersSid) && (v6[1] & 0x1200A0) == 0x1200A0 )
    {
      LengthSid = GetLengthSid(v6 + 2);
      v8 = *((unsigned __int16 *)v6 + 1) - LengthSid - 8LL;
      lpString1 = 0;
      v16 = 0;
      v17 = 1;
      StringForCondition = LocalGetStringForCondition((char *)v6 + LengthSid + 8, v8, &v16, 0);
      if ( StringForCondition )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\packageinformation.cpp",
          (const char *)StringForCondition,
          0);
      if ( v17 )
        lpString1 = v16;
      v10 = a3;
      while ( 1 )
      {
        v11 = (const WCHAR *)v10;
        if ( *(_QWORD *)(v10 + 24) > 7u )
          v11 = *(const WCHAR **)v10;
        if ( CompareStringOrdinal(lpString1, -1, v11, *(_DWORD *)(v10 + 16), 1) == 2 )
          break;
        v10 += 32;
        if ( v10 == a3 + 32 )
        {
          v12 = 0;
          goto LABEL_16;
        }
      }
      v12 = 1;
LABEL_16:
      if ( lpString1 )
        LocalFree(lpString1);
      if ( v12 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18009d588  push    rbp
0x18009d58a  push    rbx
0x18009d58b  push    rsi
0x18009d58c  push    rdi
0x18009d58d  push    r14
0x18009d58f  mov     rbp, rsp
0x18009d592  sub     rsp, 80h
0x18009d599  mov     rdi, r8
0x18009d59c  movups  xmm0, xmmword ptr [rcx]
0x18009d59f  movdqu  xmmword ptr [rbp+pAcl], xmm0
0x18009d5a4  movups  xmm1, xmmword ptr [rdx]
0x18009d5a7  movdqu  [rbp+var_30], xmm1
0x18009d5ac  mov     esi, dword ptr [rbp+pAcl+8]
0x18009d5af  cmp     esi, dword ptr [rbp+var_30+8]
0x18009d5b2  jz      loc_18009D71E
0x18009d5b8  and     [rbp+pAce], 0
0x18009d5bd  lea     r8, [rbp+pAce]; pAce
0x18009d5c1  mov     edx, esi; dwAceIndex
0x18009d5c3  mov     rcx, [rbp+pAcl]; pAcl
0x18009d5c7  call    cs:__imp_GetAce
0x18009d5ce  nop     dword ptr [rax+rax+00h]
0x18009d5d3  mov     rcx, [rbp+28h]; this
0x18009d5d7  test    eax, eax
0x18009d5d9  jz      loc_18009D72F
0x18009d5df  mov     rbx, [rbp+pAce]
0x18009d5e3  cmp     byte ptr [rbx], 9
0x18009d5e6  jnz     loc_18009D70F
0x18009d5ec  mov     edx, 1Bh; WellKnownSidType
0x18009d5f1  lea     rcx, [rbx+8]; pSid
0x18009d5f5  call    cs:__imp_IsWellKnownSid
0x18009d5fc  nop     dword ptr [rax+rax+00h]
0x18009d601  test    eax, eax
0x18009d603  jz      loc_18009D70F
0x18009d609  mov     eax, [rbx+4]
0x18009d60c  and     eax, 1200A0h
0x18009d611  cmp     eax, 1200A0h
0x18009d616  jnz     loc_18009D70F
0x18009d61c  lea     rcx, [rbx+8]; pSid
0x18009d620  call    cs:__imp_GetLengthSid
0x18009d627  nop     dword ptr [rax+rax+00h]
0x18009d62c  movzx   edx, word ptr [rbx+2]
0x18009d630  sub     edx, eax
0x18009d632  sub     rdx, 8
0x18009d636  mov     ecx, eax
0x18009d638  add     rcx, 8
0x18009d63c  add     rcx, rbx
0x18009d63f  and     [rbp+lpString1], 0
0x18009d644  lea     rax, [rbp+lpString1]
0x18009d648  mov     [rbp+var_20], rax
0x18009d64c  and     [rbp+var_18], 0
0x18009d651  mov     [rbp+var_10], 1
0x18009d655  mov     [rsp+80h+var_50], 0
0x18009d65a  and     [rsp+80h+var_58], 0
0x18009d660  and     qword ptr [rsp+80h+bIgnoreCase], 0
0x18009d666  xor     r9d, r9d
0x18009d669  lea     r8, [rbp+var_18]
0x18009d66d  call    cs:__imp_LocalGetStringForCondition
0x18009d674  nop     dword ptr [rax+rax+00h]
0x18009d679  mov     rcx, [rbp+28h]; this
0x18009d67d  test    eax, eax
0x18009d67f  jnz     loc_18009D741
0x18009d685  cmp     [rbp+var_10], al
0x18009d688  jz      short loc_18009D6A9
0x18009d68a  mov     rdx, [rbp+var_20]
0x18009d68e  mov     rcx, [rdx]; hMem
0x18009d691  mov     rax, [rbp+var_18]
0x18009d695  mov     [rdx], rax
0x18009d698  test    rcx, rcx
0x18009d69b  jz      short loc_18009D6A9
0x18009d69d  call    cs:__imp_LocalFree
0x18009d6a4  nop     dword ptr [rax+rax+00h]
0x18009d6a9  lea     r14, [rdi+20h]
0x18009d6ad  mov     rbx, rdi
0x18009d6b0  cmp     rdi, r14
0x18009d6b3  jz      short loc_18009D6EF
0x18009d6b5  mov     r8, rbx
0x18009d6b8  cmp     qword ptr [rbx+18h], 7
0x18009d6bd  jbe     short loc_18009D6C2
0x18009d6bf  mov     r8, [rbx]; lpString2
0x18009d6c2  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x18009d6ca  mov     r9d, [rbx+10h]; cchCount2
0x18009d6ce  or      edx, 0FFFFFFFFh; cchCount1
0x18009d6d1  mov     rcx, [rbp+lpString1]; lpString1
0x18009d6d5  call    cs:__imp_CompareStringOrdinal
0x18009d6dc  nop     dword ptr [rax+rax+00h]
0x18009d6e1  cmp     eax, 2
0x18009d6e4  jz      short loc_18009D716
0x18009d6e6  add     rbx, 20h ; ' '
0x18009d6ea  cmp     rbx, r14
0x18009d6ed  jnz     short loc_18009D6B5
0x18009d6ef  xor     bl, bl
0x18009d6f1  mov     rcx, [rbp+lpString1]; hMem
0x18009d6f5  and     [rbp+lpString1], 0
0x18009d6fa  test    rcx, rcx
0x18009d6fd  jz      short loc_18009D70B
0x18009d6ff  call    cs:__imp_LocalFree
0x18009d706  nop     dword ptr [rax+rax+00h]
0x18009d70b  test    bl, bl
0x18009d70d  jnz     short loc_18009D71A
0x18009d70f  inc     esi
0x18009d711  jmp     loc_18009D5AF
0x18009d716  mov     bl, 1
0x18009d718  jmp     short loc_18009D6F1
0x18009d71a  mov     al, 1
0x18009d71c  jmp     short loc_18009D720
0x18009d71e  xor     al, al
0x18009d720  add     rsp, 80h
0x18009d727  pop     r14
0x18009d729  pop     rdi
0x18009d72a  pop     rsi
0x18009d72b  pop     rbx
0x18009d72c  pop     rbp
0x18009d72d  retn
0x18009d72f  lea     r8, aOnecoreBaseApp_47; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009d736  mov     edx, 2Ah ; '*'; void *
0x18009d73b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009d741  mov     r9d, eax; char *
0x18009d744  lea     r8, aOnecoreBaseApp_47; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009d74b  mov     edx, 0B8h; void *
0x18009d750  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
