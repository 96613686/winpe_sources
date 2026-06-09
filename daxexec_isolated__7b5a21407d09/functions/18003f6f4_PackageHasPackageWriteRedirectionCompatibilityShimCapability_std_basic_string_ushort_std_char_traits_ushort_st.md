# PackageHasPackageWriteRedirectionCompatibilityShimCapability(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003f6f4`
- end: `0x18003f8a2`
- name: `?PackageHasPackageWriteRedirectionCompatibilityShimCapability@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007161c`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x1800125f4`
- `0x180021118`
- `0x18003aa40`
- `0x18003f6f4`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003f7fb`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003f7fb`
- `ntdll!RtlInitUnicodeString` at `0x18003f7c1`
- `ntdll!RtlInitUnicodeString` at `0x18003f7c1`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003f825`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003f825`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18003f781`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18003f781`

## string_xrefs

- `0x18003f7b5`: `packageWriteRedirectionCompatibilityShim`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall PackageHasPackageWriteRedirectionCompatibilityShimCapability(_QWORD *a1)
{
  int v1; // eax
  int v2; // eax
  __int64 v3; // rbx
  __int64 v5; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v6; // [rsp+58h] [rbp-A8h]
  __int64 *v7; // [rsp+60h] [rbp-A0h]
  unsigned int v8; // [rsp+68h] [rbp-98h] BYREF
  char v9; // [rsp+6Ch] [rbp-94h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pSid2[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v12[80]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v5 = 0;
  v6 = 0;
  v7 = &v5;
  v8 = 0;
  v9 = 1;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v1 = QueryApplicationCapabilities(a1, &v5, &v8, 0);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)v1,
      0);
  if ( v9 )
    v7[1] = v8;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"packageWriteRedirectionCompatibilityShim");
  memset_0(pSid2, 0, 0x44u);
  memset_0(v12, 0, 0x44u);
  v2 = RtlDeriveCapabilitySidsFromName(&DestinationString, v12, pSid2);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x2E1,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)v2,
      0);
  v3 = 0;
  if ( v6 )
  {
    while ( !EqualSid(*(PSID *)(v5 + 8 * v3), pSid2) )
    {
      v3 = (unsigned int)(v3 + 1);
      if ( (unsigned int)v3 >= v6 )
        goto LABEL_10;
    }
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(&v5);
    return 1;
  }
  else
  {
LABEL_10:
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(&v5);
    return 0;
  }
}

```

## disassembly

```asm
0x18003f6f4  mov     [rsp-8+arg_8], rbx
0x18003f6f9  push    rbp
0x18003f6fa  lea     rbp, [rsp-30h]
0x18003f6ff  sub     rsp, 130h
0x18003f706  mov     rax, cs:__security_cookie
0x18003f70d  xor     rax, rsp
0x18003f710  mov     [rbp+30h+var_10], rax
0x18003f714  mov     [rsp+130h+var_E0], 0
0x18003f71d  mov     [rsp+130h+var_D8], 0
0x18003f726  lea     rax, [rsp+130h+var_E0]
0x18003f72b  mov     [rsp+130h+var_D0], rax
0x18003f730  mov     [rsp+130h+var_C8], 0
0x18003f738  mov     [rsp+130h+var_C4], 1
0x18003f73d  cmp     qword ptr [rcx+18h], 7
0x18003f742  jbe     short loc_18003F747
0x18003f744  mov     rcx, [rcx]
0x18003f747  mov     [rsp+130h+var_F0], 0
0x18003f750  mov     [rsp+130h+var_F8], 0
0x18003f759  mov     [rsp+130h+var_100], 0
0x18003f762  mov     [rsp+130h+var_108], 0
0x18003f76b  mov     qword ptr [rsp+130h+var_110], 0; int
0x18003f774  xor     r9d, r9d
0x18003f777  lea     r8, [rsp+130h+var_C8]
0x18003f77c  lea     rdx, [rsp+130h+var_E0]
0x18003f781  call    cs:__imp_QueryApplicationCapabilities
0x18003f788  nop     dword ptr [rax+rax+00h]
0x18003f78d  mov     rcx, [rbp+38h]; this
0x18003f791  test    eax, eax
0x18003f793  js      loc_18003F88D
0x18003f799  cmp     [rsp+130h+var_C4], 0
0x18003f79e  jz      short loc_18003F7AD
0x18003f7a0  mov     ecx, [rsp+130h+var_C8]
0x18003f7a4  mov     rax, [rsp+130h+var_D0]
0x18003f7a9  mov     [rax+8], rcx
0x18003f7ad  xorps   xmm0, xmm0
0x18003f7b0  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x18003f7b5  lea     rdx, SourceString; "packageWriteRedirectionCompatibilityShi"...
0x18003f7bc  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18003f7c1  call    cs:__imp_RtlInitUnicodeString
0x18003f7c8  nop     dword ptr [rax+rax+00h]
0x18003f7cd  mov     ebx, 44h ; 'D'
0x18003f7d2  mov     r8d, ebx; Size
0x18003f7d5  xor     edx, edx; Val
0x18003f7d7  lea     rcx, [rbp+30h+pSid2]; void *
0x18003f7db  call    memset_0
0x18003f7e0  mov     r8d, ebx; Size
0x18003f7e3  xor     edx, edx; Val
0x18003f7e5  lea     rcx, [rbp+30h+var_60]; void *
0x18003f7e9  call    memset_0
0x18003f7ee  lea     r8, [rbp+30h+pSid2]
0x18003f7f2  lea     rdx, [rbp+30h+var_60]
0x18003f7f6  lea     rcx, [rsp+130h+DestinationString]
0x18003f7fb  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18003f802  nop     dword ptr [rax+rax+00h]
0x18003f807  mov     rcx, [rbp+38h]; this
0x18003f80b  test    eax, eax
0x18003f80d  js      short loc_18003F878
0x18003f80f  xor     ebx, ebx
0x18003f811  cmp     [rsp+130h+var_D8], rbx
0x18003f816  jbe     short loc_18003F840
0x18003f818  lea     rdx, [rbp+30h+pSid2]; pSid2
0x18003f81c  mov     rcx, [rsp+130h+var_E0]
0x18003f821  mov     rcx, [rcx+rbx*8]; pSid1
0x18003f825  call    cs:__imp_EqualSid
0x18003f82c  nop     dword ptr [rax+rax+00h]
0x18003f831  test    eax, eax
0x18003f833  jnz     short loc_18003F86A
0x18003f835  inc     ebx
0x18003f837  mov     eax, ebx
0x18003f839  cmp     rax, [rsp+130h+var_D8]
0x18003f83e  jb      short loc_18003F818
0x18003f840  lea     rcx, [rsp+130h+var_E0]
0x18003f845  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x18003f84a  xor     al, al
0x18003f84c  mov     rcx, [rbp+30h+var_10]
0x18003f850  xor     rcx, rsp; StackCookie
0x18003f853  call    __security_check_cookie
0x18003f858  mov     rbx, [rsp+130h+arg_8]
0x18003f860  add     rsp, 130h
0x18003f867  pop     rbp
0x18003f868  retn
0x18003f86a  lea     rcx, [rsp+130h+var_E0]
0x18003f86f  call    ??1?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x18003f874  mov     al, 1
0x18003f876  jmp     short loc_18003F84C
0x18003f878  mov     r9d, eax; char *
0x18003f87b  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003f882  mov     edx, 2E1h; void *
0x18003f887  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18003f88d  mov     r9d, eax; char *
0x18003f890  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003f897  mov     edx, 2D5h; void *
0x18003f89c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
