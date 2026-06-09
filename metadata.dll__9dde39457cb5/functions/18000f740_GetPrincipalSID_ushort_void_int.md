# GetPrincipalSID(ushort *,void * *,int *)

- ea: `0x18000f740`
- end: `0x18000f94d`
- name: `?GetPrincipalSID@@YAKPEAGPEAPEAXPEAH@Z`
- size: `525`
- prototype: `unsigned int __fastcall(wchar_t *String1, PSID *pSid, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000f954`

## callees

- `0x18000f740`
- `0x1800309a6`
- `0x1800309d0`

## import_xrefs

- `msvcrt!malloc` at `0x18000f8d2`
- `msvcrt!malloc` at `0x18000f8d2`
- `ADVAPI32!LookupAccountNameW` at `0x18000f8bd`
- `ADVAPI32!LookupAccountNameW` at `0x18000f915`
- `ADVAPI32!LookupAccountNameW` at `0x18000f8bd`
- `ADVAPI32!LookupAccountNameW` at `0x18000f915`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000f864`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000f864`
- `KERNEL32!GetLastError` at `0x18000f872`
- `KERNEL32!GetLastError` at `0x18000f8c3`
- `KERNEL32!GetLastError` at `0x18000f872`
- `KERNEL32!GetLastError` at `0x18000f8c3`

## pseudocode

```c
unsigned int __fastcall GetPrincipalSID(wchar_t *String1, PSID *pSid, int *a3)
{
  BYTE v4; // bl
  struct _SID_IDENTIFIER_AUTHORITY *p_pIdentifierAuthority; // rcx
  DWORD v8; // r8d
  BOOL v9; // eax
  unsigned int result; // eax
  PSID v11; // r8
  void *v12; // rax
  DWORD cchReferencedDomainName; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cbSid; // [rsp+6Ch] [rbp-9Ch] BYREF
  enum _SID_NAME_USE nSubAuthority1; // [rsp+70h] [rbp-98h] BYREF
  DWORD nSubAuthority1_8[4]; // [rsp+78h] [rbp-90h]
  int v17; // [rsp+98h] [rbp-70h] BYREF
  __int16 v18; // [rsp+9Ch] [rbp-6Ch]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp-68h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+A8h] [rbp-60h] BYREF

  v18 = 1280;
  v17 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  v4 = 1;
  *a3 = 1;
  *(_OWORD *)nSubAuthority1_8 = 0;
  if ( !wcscmp_0(String1, L"Administrators") )
  {
    p_pIdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v17;
    nSubAuthority1_8[1] = 544;
    v4 = 2;
    v8 = 32;
LABEL_9:
    v9 = AllocateAndInitializeSid(
           p_pIdentifierAuthority,
           v4,
           v8,
           nSubAuthority1_8[1],
           nSubAuthority1_8[2],
           nSubAuthority1_8[3],
           0,
           _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 4)),
           _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)),
           _mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 12)),
           pSid);
    goto LABEL_10;
  }
  if ( !wcscmp_0(String1, L"System") )
  {
    p_pIdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v17;
    v8 = 18;
    goto LABEL_9;
  }
  if ( !wcscmp_0(String1, L"Interactive") )
  {
    p_pIdentifierAuthority = (struct _SID_IDENTIFIER_AUTHORITY *)&v17;
    v8 = 4;
    goto LABEL_9;
  }
  if ( !wcscmp_0(String1, L"Everyone") )
  {
    p_pIdentifierAuthority = &pIdentifierAuthority;
    v8 = 0;
    goto LABEL_9;
  }
  *a3 = 0;
  v11 = *pSid;
  nSubAuthority1 = 0;
  cbSid = 0;
  cchReferencedDomainName = 255;
  LookupAccountNameW(0, String1, v11, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &nSubAuthority1);
  result = GetLastError();
  if ( result != 122 )
    return result;
  v12 = malloc(cbSid);
  *pSid = v12;
  cchReferencedDomainName = 255;
  if ( !v12 )
    return 8;
  v9 = LookupAccountNameW(0, String1, v12, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &nSubAuthority1);
LABEL_10:
  if ( v9 )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18000f740  mov     rax, rsp
0x18000f743  mov     [rax+20h], rbx
0x18000f747  push    rbp
0x18000f748  push    rsi
0x18000f749  push    rdi
0x18000f74a  push    r14
0x18000f74c  push    r15
0x18000f74e  lea     rbp, [rax-1E8h]
0x18000f755  sub     rsp, 2C0h
0x18000f75c  movaps  xmmword ptr [rax-38h], xmm6
0x18000f760  mov     rax, cs:__security_cookie
0x18000f767  xor     rax, rsp
0x18000f76a  mov     [rbp+1E0h+var_40], rax
0x18000f771  xor     r15d, r15d
0x18000f774  mov     [rbp+1E0h+var_24C], 500h
0x18000f77a  mov     rsi, rdx
0x18000f77d  mov     [rbp+1E0h+var_250], r15d
0x18000f781  xorps   xmm6, xmm6
0x18000f784  mov     dword ptr [rbp+1E0h+pIdentifierAuthority.Value], r15d
0x18000f788  lea     rdx, aAdministrators; "Administrators"
0x18000f78f  mov     word ptr [rbp+1E0h+pIdentifierAuthority.Value+4], 100h
0x18000f795  lea     ebx, [r15+1]
0x18000f799  mov     r14, r8
0x18000f79c  mov     [r8], ebx
0x18000f79f  mov     rdi, rcx
0x18000f7a2  movups  xmmword ptr [rsp+2E0h+nSubAuthority1+8], xmm6
0x18000f7a7  call    wcscmp_0
0x18000f7ac  test    eax, eax
0x18000f7ae  jnz     short loc_18000F7C4
0x18000f7b0  lea     rcx, [rbp+1E0h+var_250]
0x18000f7b4  mov     [rsp+2E0h+nSubAuthority1+0Ch], 220h
0x18000f7bc  mov     bl, 2
0x18000f7be  lea     r8d, [r15+20h]
0x18000f7c2  jmp     short loc_18000F818
0x18000f7c4  lea     rdx, aSystem; "System"
0x18000f7cb  mov     rcx, rdi; String1
0x18000f7ce  call    wcscmp_0
0x18000f7d3  test    eax, eax
0x18000f7d5  jnz     short loc_18000F7E1
0x18000f7d7  lea     rcx, [rbp+1E0h+var_250]
0x18000f7db  lea     r8d, [rax+12h]
0x18000f7df  jmp     short loc_18000F818
0x18000f7e1  lea     rdx, aInteractive; "Interactive"
0x18000f7e8  mov     rcx, rdi; String1
0x18000f7eb  call    wcscmp_0
0x18000f7f0  test    eax, eax
0x18000f7f2  jnz     short loc_18000F7FE
0x18000f7f4  lea     rcx, [rbp+1E0h+var_250]
0x18000f7f8  lea     r8d, [rax+4]
0x18000f7fc  jmp     short loc_18000F818
0x18000f7fe  lea     rdx, aEveryone; "Everyone"
0x18000f805  mov     rcx, rdi; String1
0x18000f808  call    wcscmp_0
0x18000f80d  test    eax, eax
0x18000f80f  jnz     short loc_18000F87D
0x18000f811  lea     rcx, [rbp+1E0h+pIdentifierAuthority]; pIdentifierAuthority
0x18000f815  mov     r8d, r15d; nSubAuthority0
0x18000f818  mov     eax, [rsp+2E0h+var_264]
0x18000f81c  xorps   xmm0, xmm0
0x18000f81f  mov     r9d, [rsp+2E0h+nSubAuthority1+0Ch]; nSubAuthority1
0x18000f824  xorps   xmm1, xmm1
0x18000f827  mov     [rsp+2E0h+pSid], rsi; pSid
0x18000f82c  mov     dl, bl; nSubAuthorityCount
0x18000f82e  psrldq  xmm0, 0Ch
0x18000f833  movd    [rsp+2E0h+nSubAuthority7], xmm0; nSubAuthority7
0x18000f839  xorps   xmm0, xmm0
0x18000f83c  psrldq  xmm1, 8
0x18000f841  movd    [rsp+2E0h+nSubAuthority6], xmm1; nSubAuthority6
0x18000f847  psrldq  xmm0, 4
0x18000f84c  movd    [rsp+2E0h+nSubAuthority5], xmm0; nSubAuthority5
0x18000f852  movss   [rsp+2E0h+nSubAuthority4], xmm6; nSubAuthority4
0x18000f858  mov     [rsp+2E0h+nSubAuthority3], eax; nSubAuthority3
0x18000f85c  mov     eax, [rsp+2E0h+var_268]
0x18000f860  mov     [rsp+2E0h+nSubAuthority2], eax; nSubAuthority2
0x18000f864  call    cs:__imp_AllocateAndInitializeSid
0x18000f86a  test    eax, eax
0x18000f86c  jnz     loc_18000F920
0x18000f872  call    cs:__imp_GetLastError
0x18000f878  jmp     loc_18000F922
0x18000f87d  lea     rax, [rsp+2E0h+nSubAuthority1]
0x18000f882  mov     [r14], r15d
0x18000f885  mov     r8, [rsi]; Sid
0x18000f888  lea     r9, [rsp+2E0h+cbSid]; cbSid
0x18000f88d  mov     qword ptr [rsp+2E0h+nSubAuthority4], rax; peUse
0x18000f892  mov     ebx, 0FFh
0x18000f897  lea     rax, [rsp+2E0h+cchReferencedDomainName]
0x18000f89c  mov     [rsp+2E0h+nSubAuthority1], r15d
0x18000f8a1  mov     qword ptr [rsp+2E0h+nSubAuthority3], rax; cchReferencedDomainName
0x18000f8a6  mov     rdx, rdi; lpAccountName
0x18000f8a9  lea     rax, [rbp+1E0h+ReferencedDomainName]
0x18000f8ad  mov     [rsp+2E0h+cbSid], r15d
0x18000f8b2  xor     ecx, ecx; lpSystemName
0x18000f8b4  mov     qword ptr [rsp+2E0h+nSubAuthority2], rax; ReferencedDomainName
0x18000f8b9  mov     [rsp+2E0h+cchReferencedDomainName], ebx
0x18000f8bd  call    cs:__imp_LookupAccountNameW
0x18000f8c3  call    cs:__imp_GetLastError
0x18000f8c9  cmp     eax, 7Ah ; 'z'
0x18000f8cc  jnz     short loc_18000F922
0x18000f8ce  mov     ecx, [rsp+2E0h+cbSid]; Size
0x18000f8d2  call    cs:__imp_malloc
0x18000f8d8  mov     [rsi], rax
0x18000f8db  mov     [rsp+2E0h+cchReferencedDomainName], ebx
0x18000f8df  test    rax, rax
0x18000f8e2  jnz     short loc_18000F8EB
0x18000f8e4  mov     eax, 8
0x18000f8e9  jmp     short loc_18000F922
0x18000f8eb  lea     rcx, [rsp+2E0h+nSubAuthority1]
0x18000f8f0  mov     r8, rax; Sid
0x18000f8f3  mov     qword ptr [rsp+2E0h+nSubAuthority4], rcx; peUse
0x18000f8f8  lea     r9, [rsp+2E0h+cbSid]; cbSid
0x18000f8fd  lea     rcx, [rsp+2E0h+cchReferencedDomainName]
0x18000f902  mov     rdx, rdi; lpAccountName
0x18000f905  mov     qword ptr [rsp+2E0h+nSubAuthority3], rcx; cchReferencedDomainName
0x18000f90a  lea     rcx, [rbp+1E0h+ReferencedDomainName]
0x18000f90e  mov     qword ptr [rsp+2E0h+nSubAuthority2], rcx; ReferencedDomainName
0x18000f913  xor     ecx, ecx; lpSystemName
0x18000f915  call    cs:__imp_LookupAccountNameW
0x18000f91b  jmp     loc_18000F86A
0x18000f920  xor     eax, eax
0x18000f922  mov     rcx, [rbp+1E0h+var_40]
0x18000f929  xor     rcx, rsp; StackCookie
0x18000f92c  call    __security_check_cookie
0x18000f931  lea     r11, [rsp+2E0h+var_20]
0x18000f939  mov     rbx, [r11+48h]
0x18000f93d  movaps  xmm6, xmmword ptr [r11-10h]
0x18000f942  mov     rsp, r11
0x18000f945  pop     r15
0x18000f947  pop     r14
0x18000f949  pop     rdi
0x18000f94a  pop     rsi
0x18000f94b  pop     rbp
0x18000f94c  retn
```
