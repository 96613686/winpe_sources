# std::any_of_AceEnumerable::AceEnumerator__lambda_d72051e8c7293564db28714679aad473___

- ea: `0x18009eef4`
- end: `0x18009f0e0`
- name: `std::any_of_AceEnumerable::AceEnumerator__lambda_d72051e8c7293564db28714679aad473___`
- size: `492`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009f1e0`

## callees

- `0x180014e74`
- `0x1800210fc`
- `0x18009eef4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009f04e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009f04e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f014`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f07c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f014`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f07c`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009ef34`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18009ef34`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009ef62`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18009ef62`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009ef8c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009ef8c`
- `api-ms-win-security-sddlparsecond-l1-1-0!LocalGetStringForCondition` at `0x18009efe4`
- `api-ms-win-security-sddlparsecond-l1-1-0!LocalGetStringForCondition` at `0x18009efe4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall std::any_of_AceEnumerable::AceEnumerator__lambda_d72051e8c7293564db28714679aad473___(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  struct _ACL *v4; // r12
  DWORD v5; // esi
  int v6; // r15d
  const char *v7; // r9
  _DWORD *v8; // rdi
  DWORD LengthSid; // eax
  DWORD v10; // edx
  unsigned int StringForCondition; // eax
  WCHAR *v12; // rcx
  __int64 v13; // rdi
  const WCHAR *v14; // r8
  char v15; // di
  WCHAR *v16; // rcx
  const WCHAR *v18; // [rsp+48h] [rbp-18h] BYREF
  char v19; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  LPVOID pAce; // [rsp+90h] [rbp+30h] BYREF
  LPCWCH lpString1; // [rsp+98h] [rbp+38h]

  v4 = *(struct _ACL **)a1;
  v5 = *(_DWORD *)(a1 + 8);
  v6 = *(_DWORD *)(a2 + 8);
  while ( v5 != v6 )
  {
    pAce = 0;
    if ( !GetAce(v4, v5, &pAce) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\packageinformation.cpp",
        v7);
    v8 = pAce;
    if ( *(_BYTE *)pAce == 9 && IsWellKnownSid((char *)pAce + 8, WinBuiltinUsersSid) && (v8[1] & 0x1200A0) == 0x1200A0 )
    {
      LengthSid = GetLengthSid(v8 + 2);
      v10 = *((unsigned __int16 *)v8 + 1) - LengthSid;
      lpString1 = 0;
      v18 = 0;
      v19 = 1;
      StringForCondition = LocalGetStringForCondition((char *)v8 + LengthSid + 8, v10 - 8, &v18, 0);
      if ( StringForCondition )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xB8,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\packageinformation.cpp",
          (const char *)StringForCondition,
          0);
      if ( v19 )
      {
        v12 = (WCHAR *)lpString1;
        lpString1 = v18;
        if ( v12 )
          LocalFree(v12);
      }
      v13 = a3;
      while ( 1 )
      {
        v14 = *(_QWORD *)(v13 + 24) <= 7u ? (const WCHAR *)v13 : *(const WCHAR **)v13;
        if ( CompareStringOrdinal(lpString1, -1, v14, *(_DWORD *)(v13 + 16), 1) == 2 )
          break;
        v13 += 32;
        if ( v13 == a3 + 32 )
        {
          v15 = 0;
          goto LABEL_18;
        }
      }
      v15 = 1;
LABEL_18:
      v16 = (WCHAR *)lpString1;
      lpString1 = 0;
      if ( v16 )
        LocalFree(v16);
      if ( v15 )
        return 1;
    }
    ++v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18009eef4  mov     [rsp-28h+arg_10], rbx
0x18009eef9  mov     [rsp-28h+arg_18], rsi
0x18009eefe  push    rbp
0x18009eeff  push    rdi
0x18009ef00  push    r12
0x18009ef02  push    r14
0x18009ef04  push    r15
0x18009ef06  mov     rbp, rsp
0x18009ef09  sub     rsp, 60h
0x18009ef0d  mov     rbx, r8
0x18009ef10  mov     r12, [rcx]
0x18009ef13  mov     esi, [rcx+8]
0x18009ef16  mov     r15d, [rdx+8]
0x18009ef1a  cmp     esi, r15d
0x18009ef1d  jz      loc_18009F09D
0x18009ef23  mov     [rbp+pAce], 0
0x18009ef2b  lea     r8, [rbp+pAce]; pAce
0x18009ef2f  mov     edx, esi; dwAceIndex
0x18009ef31  mov     rcx, r12; pAcl
0x18009ef34  call    cs:__imp_GetAce
0x18009ef3b  nop     dword ptr [rax+rax+00h]
0x18009ef40  mov     rcx, [rbp+28h]; this
0x18009ef44  test    eax, eax
0x18009ef46  jz      loc_18009F0B9
0x18009ef4c  mov     rdi, [rbp+pAce]
0x18009ef50  cmp     byte ptr [rdi], 9
0x18009ef53  jnz     loc_18009F08D
0x18009ef59  mov     edx, 1Bh; WellKnownSidType
0x18009ef5e  lea     rcx, [rdi+8]; pSid
0x18009ef62  call    cs:__imp_IsWellKnownSid
0x18009ef69  nop     dword ptr [rax+rax+00h]
0x18009ef6e  test    eax, eax
0x18009ef70  jz      loc_18009F08D
0x18009ef76  mov     eax, [rdi+4]
0x18009ef79  mov     ecx, 1200A0h
0x18009ef7e  and     eax, ecx
0x18009ef80  cmp     eax, ecx
0x18009ef82  jnz     loc_18009F08D
0x18009ef88  lea     rcx, [rdi+8]; pSid
0x18009ef8c  call    cs:__imp_GetLengthSid
0x18009ef93  nop     dword ptr [rax+rax+00h]
0x18009ef98  movzx   edx, word ptr [rdi+2]
0x18009ef9c  sub     edx, eax
0x18009ef9e  mov     ecx, eax
0x18009efa0  add     rcx, 8
0x18009efa4  add     rcx, rdi
0x18009efa7  mov     [rbp+lpString1], 0
0x18009efaf  lea     rax, [rbp+lpString1]
0x18009efb3  mov     [rbp+var_20], rax
0x18009efb7  mov     [rbp+var_18], 0
0x18009efbf  mov     [rbp+var_10], 1
0x18009efc3  add     edx, 0FFFFFFF8h
0x18009efc6  mov     [rsp+60h+var_30], 0
0x18009efcb  mov     [rsp+60h+var_38], 0
0x18009efd4  mov     qword ptr [rsp+60h+bIgnoreCase], 0; unsigned int
0x18009efdd  xor     r9d, r9d
0x18009efe0  lea     r8, [rbp+var_18]
0x18009efe4  call    cs:__imp_LocalGetStringForCondition
0x18009efeb  nop     dword ptr [rax+rax+00h]
0x18009eff0  mov     rcx, [rbp+28h]; this
0x18009eff4  test    eax, eax
0x18009eff6  jnz     loc_18009F0CB
0x18009effc  cmp     [rbp+var_10], al
0x18009efff  jz      short loc_18009F020
0x18009f001  mov     rdx, [rbp+var_20]
0x18009f005  mov     rcx, [rdx]; hMem
0x18009f008  mov     rax, [rbp+var_18]
0x18009f00c  mov     [rdx], rax
0x18009f00f  test    rcx, rcx
0x18009f012  jz      short loc_18009F020
0x18009f014  call    cs:__imp_LocalFree
0x18009f01b  nop     dword ptr [rax+rax+00h]
0x18009f020  mov     rdi, rbx
0x18009f023  lea     r14, [rbx+20h]
0x18009f027  cmp     rbx, r14
0x18009f02a  jz      short loc_18009F068
0x18009f02c  cmp     qword ptr [rdi+18h], 7
0x18009f031  jbe     short loc_18009F038
0x18009f033  mov     r8, [rdi]
0x18009f036  jmp     short loc_18009F03B
0x18009f038  mov     r8, rdi; lpString2
0x18009f03b  mov     [rsp+60h+bIgnoreCase], 1; bIgnoreCase
0x18009f043  mov     r9d, [rdi+10h]; cchCount2
0x18009f047  or      edx, 0FFFFFFFFh; cchCount1
0x18009f04a  mov     rcx, [rbp+lpString1]; lpString1
0x18009f04e  call    cs:__imp_CompareStringOrdinal
0x18009f055  nop     dword ptr [rax+rax+00h]
0x18009f05a  cmp     eax, 2
0x18009f05d  jz      short loc_18009F094
0x18009f05f  add     rdi, 20h ; ' '
0x18009f063  cmp     rdi, r14
0x18009f066  jnz     short loc_18009F02C
0x18009f068  xor     dil, dil
0x18009f06b  mov     rcx, [rbp+lpString1]; hMem
0x18009f06f  mov     [rbp+lpString1], 0
0x18009f077  test    rcx, rcx
0x18009f07a  jz      short loc_18009F088
0x18009f07c  call    cs:__imp_LocalFree
0x18009f083  nop     dword ptr [rax+rax+00h]
0x18009f088  test    dil, dil
0x18009f08b  jnz     short loc_18009F099
0x18009f08d  inc     esi
0x18009f08f  jmp     loc_18009EF1A
0x18009f094  mov     dil, 1
0x18009f097  jmp     short loc_18009F06B
0x18009f099  mov     al, 1
0x18009f09b  jmp     short loc_18009F09F
0x18009f09d  xor     al, al
0x18009f09f  lea     r11, [rsp+60h+var_s0]
0x18009f0a4  mov     rbx, [r11+40h]
0x18009f0a8  mov     rsi, [r11+48h]
0x18009f0ac  mov     rsp, r11
0x18009f0af  pop     r15
0x18009f0b1  pop     r14
0x18009f0b3  pop     r12
0x18009f0b5  pop     rdi
0x18009f0b6  pop     rbp
0x18009f0b7  retn
0x18009f0b9  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009f0c0  mov     edx, 2Ah ; '*'; void *
0x18009f0c5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18009f0cb  mov     r9d, eax; char *
0x18009f0ce  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009f0d5  mov     edx, 0B8h; void *
0x18009f0da  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
