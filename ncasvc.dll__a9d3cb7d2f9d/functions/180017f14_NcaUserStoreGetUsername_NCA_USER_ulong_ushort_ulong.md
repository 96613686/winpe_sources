# NcaUserStoreGetUsername(NCA_USER_ *,ulong,ushort *,ulong *)

- ea: `0x180017f14`
- end: `0x18001807b`
- name: `?NcaUserStoreGetUsername@@YAKPEAUNCA_USER_@@KPEAGPEAK@Z`
- size: `359`
- prototype: `__int64 __fastcall(struct NCA_USER_ *, unsigned int, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009998`

## callees

- `0x180004f34`
- `0x180017f14`
- `0x18001cc32`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017f91`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180017f81`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180017f81`

## pseudocode

```c
__int64 __fastcall NcaUserStoreGetUsername(
        struct NCA_USER_ *a1,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int *a4)
{
  void *v4; // rcx
  DWORD LastError; // eax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v12; // rbx
  DWORD cchName; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchReferencedDomainName; // [rsp+34h] [rbp-CCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[256]; // [rsp+240h] [rbp+140h] BYREF

  v4 = (void *)*((_QWORD *)a1 + 3);
  cchReferencedDomainName = 256;
  cchName = 256;
  peUse = 0;
  if ( LookupAccountSidLocalW(v4, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( ReferencedDomainName[v10] );
    cchReferencedDomainName = v10;
    do
      ++v9;
    while ( Name[v9] );
    cchName = v9;
    if ( (int)v10 + (int)v9 + 1 > a2 )
      return 14;
    v12 = (unsigned int)v10;
    memcpy_0(a3, ReferencedDomainName, v12 * 2);
    a3[v12] = 92;
    memcpy_0(&a3[v12 + 1], Name, 2LL * cchName);
    *a4 = cchName + cchReferencedDomainName + 1;
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_f6fba97516d23319eaec26e747470e80_Traceguids, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x180017f14  push    rbp
0x180017f16  push    rbx
0x180017f17  push    rsi
0x180017f18  push    rdi
0x180017f19  push    r14
0x180017f1b  lea     rbp, [rsp-350h]
0x180017f23  sub     rsp, 450h
0x180017f2a  mov     rax, cs:__security_cookie
0x180017f31  xor     rax, rsp
0x180017f34  mov     [rbp+370h+var_30], rax
0x180017f3b  mov     rcx, [rcx+18h]; Sid
0x180017f3f  mov     eax, 100h
0x180017f44  mov     [rsp+470h+var_43C], eax
0x180017f48  mov     rsi, r9
0x180017f4b  mov     [rsp+470h+cchName], eax
0x180017f4f  lea     r9, [rsp+470h+ReferencedDomainName]; ReferencedDomainName
0x180017f54  lea     rax, [rsp+470h+var_438]
0x180017f59  mov     rdi, r8
0x180017f5c  mov     [rsp+470h+peUse], rax; peUse
0x180017f61  lea     r8, [rsp+470h+cchName]; cchName
0x180017f66  lea     rax, [rsp+470h+var_43C]
0x180017f6b  mov     ebx, edx
0x180017f6d  xor     r14d, r14d
0x180017f70  mov     [rsp+470h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180017f75  lea     rdx, [rbp+370h+Name]; Name
0x180017f7c  mov     [rsp+470h+var_438], r14d
0x180017f81  call    cs:__imp_LookupAccountSidLocalW
0x180017f88  nop     dword ptr [rax+rax+00h]
0x180017f8d  test    eax, eax
0x180017f8f  jnz     short loc_180017FDA
0x180017f91  call    cs:__imp_GetLastError
0x180017f98  nop     dword ptr [rax+rax+00h]
0x180017f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017fa4  lea     rdx, WPP_GLOBAL_Control
0x180017fab  cmp     rcx, rdx
0x180017fae  jz      loc_18001805B
0x180017fb4  test    byte ptr [rcx+1Ch], 1
0x180017fb8  jz      loc_18001805B
0x180017fbe  mov     rcx, [rcx+10h]
0x180017fc2  lea     edx, [r14+0Bh]
0x180017fc6  mov     r9d, eax
0x180017fc9  lea     r8, WPP_f6fba97516d23319eaec26e747470e80_Traceguids
0x180017fd0  call    WPP_SF_d
0x180017fd5  jmp     loc_18001805B
0x180017fda  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017fde  lea     rdx, [rsp+470h+ReferencedDomainName]
0x180017fe3  mov     rcx, rax
0x180017fe6  inc     rcx
0x180017fe9  cmp     [rdx+rcx*2], r14w
0x180017fee  jnz     short loc_180017FE6
0x180017ff0  mov     [rsp+470h+var_43C], ecx
0x180017ff4  lea     rdx, [rbp+370h+Name]
0x180017ffb  inc     rax
0x180017ffe  cmp     [rdx+rax*2], r14w
0x180018003  jnz     short loc_180017FFB
0x180018005  mov     [rsp+470h+cchName], eax
0x180018009  inc     eax
0x18001800b  add     eax, ecx
0x18001800d  cmp     eax, ebx
0x18001800f  jbe     short loc_180018018
0x180018011  mov     eax, 0Eh
0x180018016  jmp     short loc_18001805D
0x180018018  mov     eax, ecx
0x18001801a  lea     rdx, [rsp+470h+ReferencedDomainName]; Src
0x18001801f  mov     rcx, rdi; void *
0x180018022  lea     rbx, [rax+rax]
0x180018026  mov     r8, rbx; Size
0x180018029  call    memcpy_0
0x18001802e  mov     word ptr [rbx+rdi], 5Ch ; '\'
0x180018034  lea     rcx, [rdi+2]
0x180018038  mov     r8d, [rsp+470h+cchName]
0x18001803d  lea     rdx, [rbp+370h+Name]; Src
0x180018044  add     r8, r8; Size
0x180018047  add     rcx, rbx; void *
0x18001804a  call    memcpy_0
0x18001804f  mov     ecx, [rsp+470h+var_43C]
0x180018053  inc     ecx
0x180018055  add     ecx, [rsp+470h+cchName]
0x180018059  mov     [rsi], ecx
0x18001805b  xor     eax, eax
0x18001805d  mov     rcx, [rbp+370h+var_30]
0x180018064  xor     rcx, rsp; StackCookie
0x180018067  call    __security_check_cookie
0x18001806c  add     rsp, 450h
0x180018073  pop     r14
0x180018075  pop     rdi
0x180018076  pop     rsi
0x180018077  pop     rbx
0x180018078  pop     rbp
0x180018079  retn
```
