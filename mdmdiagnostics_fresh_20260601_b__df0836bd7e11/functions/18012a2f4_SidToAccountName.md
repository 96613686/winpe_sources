# SidToAccountName

- ea: `0x18012a2f4`
- end: `0x18012a4f5`
- name: `SidToAccountName`
- size: `513`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180129b8c`

## callees

- `0x180019508`
- `0x180019514`
- `0x1800ece3c`
- `0x1800ed5fc`
- `0x1800ed6e4`
- `0x1800f9558`
- `0x18012a2f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012a37a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18012a36c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18012a408`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18012a36c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18012a408`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18012a319`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18012a319`

## string_xrefs

- `0x18012a327`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\html\common.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SidToAccountName(const WCHAR *a1, unsigned __int16 **a2)
{
  unsigned int LastError; // ebx
  const char *v4; // r9
  void *ReferencedDomainName; // rax
  LPWSTR v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-40h] BYREF
  LPWSTR Name; // [rsp+48h] [rbp-38h] BYREF
  void *Block; // [rsp+50h] [rbp-30h] BYREF
  PSID Sid[3]; // [rsp+58h] [rbp-28h] BYREF
  char v16; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  DWORD cchReferencedDomainName; // [rsp+B0h] [rbp+30h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp+38h] BYREF

  LastError = 0;
  Sid[0] = 0;
  if ( !ConvertStringSidToSidW(a1, Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x3B8,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\common.cpp",
                  v4);
LABEL_15:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Sid);
    return LastError;
  }
  peUse = 0;
  cchName = 0;
  cchReferencedDomainName = 0;
  if ( LookupAccountSidW(0, Sid[0], 0, &cchName, 0, &cchReferencedDomainName, &peUse) || GetLastError() != 122 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Sid);
    return 0;
  }
  Name = (LPWSTR)operator new[](saturated_mul(cchName, 2u));
  ReferencedDomainName = operator new[](saturated_mul(cchReferencedDomainName, 2u));
  Block = ReferencedDomainName;
  Sid[1] = &Name;
  Sid[2] = &Block;
  v16 = 1;
  v6 = Name;
  if ( !Name )
  {
LABEL_14:
    operator delete(v6);
    operator delete(Block);
    goto LABEL_15;
  }
  if ( !LookupAccountSidW(0, Sid[0], Name, &cchName, (LPWSTR)ReferencedDomainName, &cchReferencedDomainName, &peUse)
    || (unsigned int)(peUse - 1) > 1 )
  {
    v6 = Name;
    goto LABEL_14;
  }
  v7 = -1;
  do
    ++v7;
  while ( Name[v7] );
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)Block + v8) );
  v9 = v8 + v7 + 2;
  v10 = (unsigned __int16 *)operator new[](saturated_mul(v9, 2u));
  *a2 = v10;
  StringCchCopyW(v10, v9, (const unsigned __int16 *)Block);
  StringCchCatW(*a2, v9, L"\\");
  StringCchCatW(*a2, v9, Name);
  operator delete(Name);
  operator delete(Block);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Sid);
  return 1;
}

```

## disassembly

```asm
0x18012a2f4  mov     [rsp-18h+arg_0], rbx
0x18012a2f9  mov     [rsp-18h+arg_8], rsi
0x18012a2fe  push    rbp
0x18012a2ff  push    rdi
0x18012a300  push    r14
0x18012a302  mov     rbp, rsp
0x18012a305  sub     rsp, 80h
0x18012a30c  mov     rdi, rdx
0x18012a30f  xor     ebx, ebx
0x18012a311  mov     [rbp+Sid], rbx
0x18012a315  lea     rdx, [rbp+Sid]; Sid
0x18012a319  call    cs:__imp_ConvertStringSidToSidW
0x18012a31f  test    eax, eax
0x18012a321  jnz     short loc_18012A33F
0x18012a323  mov     rcx, [rbp+18h]; this
0x18012a327  lea     r8, aOnecoreuapAdmi_23; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18012a32e  mov     edx, 3B8h; void *
0x18012a333  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18012a338  mov     ebx, eax
0x18012a33a  jmp     loc_18012A4C5
0x18012a33f  mov     [rbp+var_40], ebx
0x18012a342  mov     [rbp+cchName], ebx
0x18012a345  mov     [rbp+arg_10], ebx
0x18012a348  lea     rax, [rbp+var_40]
0x18012a34c  mov     [rsp+80h+peUse], rax; peUse
0x18012a351  lea     rax, [rbp+arg_10]
0x18012a355  mov     [rsp+80h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18012a35a  mov     [rsp+80h+ReferencedDomainName], rbx; ReferencedDomainName
0x18012a35f  lea     r9, [rbp+cchName]; cchName
0x18012a363  xor     r8d, r8d; Name
0x18012a366  mov     rdx, [rbp+Sid]; Sid
0x18012a36a  xor     ecx, ecx; lpSystemName
0x18012a36c  call    cs:__imp_LookupAccountSidW
0x18012a372  test    eax, eax
0x18012a374  jnz     loc_18012A4D2
0x18012a37a  call    cs:__imp_GetLastError
0x18012a380  cmp     eax, 7Ah ; 'z'
0x18012a383  jnz     loc_18012A4D2
0x18012a389  mov     ecx, [rbp+cchName]
0x18012a38c  lea     r14d, [rax-78h]
0x18012a390  mov     eax, r14d
0x18012a393  mul     rcx
0x18012a396  lea     rsi, [r14-3]
0x18012a39a  cmovb   rax, rsi
0x18012a39e  mov     rcx, rax; unsigned __int64
0x18012a3a1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18012a3a6  mov     [rbp+Name], rax
0x18012a3aa  mov     ecx, [rbp+arg_10]
0x18012a3ad  mov     eax, r14d
0x18012a3b0  mul     rcx
0x18012a3b3  cmovb   rax, rsi
0x18012a3b7  mov     rcx, rax; unsigned __int64
0x18012a3ba  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18012a3bf  mov     [rbp+Block], rax
0x18012a3c3  lea     rcx, [rbp+Name]
0x18012a3c7  mov     [rbp+var_20], rcx
0x18012a3cb  lea     rcx, [rbp+Block]
0x18012a3cf  mov     [rbp+var_18], rcx
0x18012a3d3  mov     [rbp+var_10], 1
0x18012a3d7  mov     rcx, [rbp+Name]; Block
0x18012a3db  test    rcx, rcx
0x18012a3de  jz      loc_18012A4B6
0x18012a3e4  lea     rdx, [rbp+var_40]
0x18012a3e8  mov     [rsp+80h+peUse], rdx; peUse
0x18012a3ed  lea     rdx, [rbp+arg_10]
0x18012a3f1  mov     [rsp+80h+cchReferencedDomainName], rdx; cchReferencedDomainName
0x18012a3f6  mov     [rsp+80h+ReferencedDomainName], rax; ReferencedDomainName
0x18012a3fb  lea     r9, [rbp+cchName]; cchName
0x18012a3ff  mov     r8, rcx; Name
0x18012a402  mov     rdx, [rbp+Sid]; Sid
0x18012a406  xor     ecx, ecx; lpSystemName
0x18012a408  call    cs:__imp_LookupAccountSidW
0x18012a40e  test    eax, eax
0x18012a410  jnz     short loc_18012A41B
0x18012a412  mov     rcx, [rbp+Name]
0x18012a416  jmp     loc_18012A4B6
0x18012a41b  mov     eax, [rbp+var_40]
0x18012a41e  dec     eax
0x18012a420  cmp     eax, 1
0x18012a423  ja      short loc_18012A412
0x18012a425  mov     rax, [rbp+Name]
0x18012a429  mov     rcx, rsi
0x18012a42c  inc     rcx
0x18012a42f  cmp     [rax+rcx*2], bx
0x18012a433  jnz     short loc_18012A42C
0x18012a435  mov     r8, [rbp+Block]
0x18012a439  mov     rdx, rsi
0x18012a43c  inc     rdx
0x18012a43f  cmp     [r8+rdx*2], bx
0x18012a444  jnz     short loc_18012A43C
0x18012a446  lea     rbx, [rcx+2]
0x18012a44a  add     rbx, rdx
0x18012a44d  mov     rax, r14
0x18012a450  mul     rbx
0x18012a453  cmovb   rax, rsi
0x18012a457  mov     rcx, rax; unsigned __int64
0x18012a45a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18012a45f  mov     [rdi], rax
0x18012a462  mov     r8, [rbp+Block]; unsigned __int16 *
0x18012a466  mov     rdx, rbx; unsigned __int64
0x18012a469  mov     rcx, rax; unsigned __int16 *
0x18012a46c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18012a471  lea     r8, psz; "\\"
0x18012a478  mov     rdx, rbx; unsigned __int64
0x18012a47b  mov     rcx, [rdi]; unsigned __int16 *
0x18012a47e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18012a483  mov     r8, [rbp+Name]; unsigned __int16 *
0x18012a487  mov     rdx, rbx; unsigned __int64
0x18012a48a  mov     rcx, [rdi]; unsigned __int16 *
0x18012a48d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18012a492  nop
0x18012a493  mov     rcx, [rbp+Name]; Block
0x18012a497  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012a49c  mov     rcx, [rbp+Block]; Block
0x18012a4a0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012a4a5  nop
0x18012a4a6  lea     rcx, [rbp+Sid]
0x18012a4aa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18012a4af  mov     eax, 1
0x18012a4b4  jmp     short loc_18012A4DD
0x18012a4b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012a4bb  mov     rcx, [rbp+Block]; Block
0x18012a4bf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18012a4c4  nop
0x18012a4c5  lea     rcx, [rbp+Sid]
0x18012a4c9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18012a4ce  mov     eax, ebx
0x18012a4d0  jmp     short loc_18012A4DD
0x18012a4d2  lea     rcx, [rbp+Sid]
0x18012a4d6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18012a4db  xor     eax, eax
0x18012a4dd  lea     r11, [rsp+80h+var_s0]
0x18012a4e5  mov     rbx, [r11+20h]
0x18012a4e9  mov     rsi, [r11+28h]
0x18012a4ed  mov     rsp, r11
0x18012a4f0  pop     r14
0x18012a4f2  pop     rdi
0x18012a4f3  pop     rbp
0x18012a4f4  retn
```
