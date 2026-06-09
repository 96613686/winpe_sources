# PackageHasPackageWriteRedirectionCompatibilityShimCapability(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003d978`
- end: `0x18003db20`
- name: `?PackageHasPackageWriteRedirectionCompatibilityShimCapability@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `424`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006fabc`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x180010a84`
- `0x180020338`
- `0x18003d978`
- `0x18003fbb8`

## import_xrefs

- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003da77`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18003da77`
- `ntdll!RtlInitUnicodeString` at `0x18003da3d`
- `ntdll!RtlInitUnicodeString` at `0x18003da3d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003daa3`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003daa3`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18003d9fd`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18003d9fd`

## string_xrefs

- `0x18003da31`: `packageWriteRedirectionCompatibilityShim`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall PackageHasPackageWriteRedirectionCompatibilityShimCapability(_QWORD *a1)
{
  int v2; // eax
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rax
  __int64 v7; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v8; // [rsp+58h] [rbp-A8h]
  __int64 *v9; // [rsp+60h] [rbp-A0h]
  unsigned int v10; // [rsp+68h] [rbp-98h] BYREF
  char v11; // [rsp+6Ch] [rbp-94h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pSid2[80]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v14[80]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v7 = 0;
  v8 = 0;
  v9 = &v7;
  v10 = 0;
  v11 = 1;
  wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v7);
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v2 = QueryApplicationCapabilities(a1, &v7, &v10, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)v2,
      0);
  if ( v11 )
    v9[1] = v10;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"packageWriteRedirectionCompatibilityShim");
  memset_0(pSid2, 0, 0x44u);
  memset_0(v14, 0, 0x44u);
  v3 = RtlDeriveCapabilitySidsFromName(&DestinationString, v14, pSid2);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x2E1,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)v3,
      0);
  v4 = 0;
  if ( v8 )
  {
    v5 = 0;
    while ( !EqualSid(*(PSID *)(v7 + 8 * v5), pSid2) )
    {
      v5 = ++v4;
      if ( v4 >= v8 )
        goto LABEL_11;
    }
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v7);
    return 1;
  }
  else
  {
LABEL_11:
    wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v7);
    return 0;
  }
}

```

## disassembly

```asm
0x18003d978  mov     [rsp-8+arg_8], rbx
0x18003d97d  push    rbp
0x18003d97e  lea     rbp, [rsp-30h]
0x18003d983  sub     rsp, 130h
0x18003d98a  mov     rax, cs:__security_cookie
0x18003d991  xor     rax, rsp
0x18003d994  mov     [rbp+30h+var_10], rax
0x18003d998  mov     rbx, rcx
0x18003d99b  and     [rsp+130h+var_E0], 0
0x18003d9a1  and     [rsp+130h+var_D8], 0
0x18003d9a7  lea     rax, [rsp+130h+var_E0]
0x18003d9ac  mov     [rsp+130h+var_D0], rax
0x18003d9b1  and     [rsp+130h+var_C8], 0
0x18003d9b6  mov     [rsp+130h+var_C4], 1
0x18003d9bb  lea     rcx, [rsp+130h+var_E0]
0x18003d9c0  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18003d9c5  cmp     qword ptr [rbx+18h], 7
0x18003d9ca  jbe     short loc_18003D9CF
0x18003d9cc  mov     rbx, [rbx]
0x18003d9cf  and     [rsp+130h+var_F0], 0
0x18003d9d5  and     [rsp+130h+var_F8], 0
0x18003d9db  and     [rsp+130h+var_100], 0
0x18003d9e1  and     [rsp+130h+var_108], 0
0x18003d9e7  and     [rsp+130h+var_110], 0
0x18003d9ed  xor     r9d, r9d
0x18003d9f0  lea     r8, [rsp+130h+var_C8]
0x18003d9f5  lea     rdx, [rsp+130h+var_E0]
0x18003d9fa  mov     rcx, rbx
0x18003d9fd  call    cs:__imp_QueryApplicationCapabilities
0x18003da04  nop     dword ptr [rax+rax+00h]
0x18003da09  mov     rcx, [rbp+38h]; this
0x18003da0d  test    eax, eax
0x18003da0f  js      loc_18003DB0B
0x18003da15  cmp     [rsp+130h+var_C4], 0
0x18003da1a  jz      short loc_18003DA29
0x18003da1c  mov     ecx, [rsp+130h+var_C8]
0x18003da20  mov     rax, [rsp+130h+var_D0]
0x18003da25  mov     [rax+8], rcx
0x18003da29  xorps   xmm0, xmm0
0x18003da2c  movups  xmmword ptr [rsp+130h+DestinationString.Length], xmm0
0x18003da31  lea     rdx, SourceString; "packageWriteRedirectionCompatibilityShi"...
0x18003da38  lea     rcx, [rsp+130h+DestinationString]; DestinationString
0x18003da3d  call    cs:__imp_RtlInitUnicodeString
0x18003da44  nop     dword ptr [rax+rax+00h]
0x18003da49  mov     ebx, 44h ; 'D'
0x18003da4e  mov     r8d, ebx; Size
0x18003da51  xor     edx, edx; Val
0x18003da53  lea     rcx, [rbp+30h+pSid2]; void *
0x18003da57  call    memset_0
0x18003da5c  mov     r8d, ebx; Size
0x18003da5f  xor     edx, edx; Val
0x18003da61  lea     rcx, [rbp+30h+var_60]; void *
0x18003da65  call    memset_0
0x18003da6a  lea     r8, [rbp+30h+pSid2]
0x18003da6e  lea     rdx, [rbp+30h+var_60]
0x18003da72  lea     rcx, [rsp+130h+DestinationString]
0x18003da77  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x18003da7e  nop     dword ptr [rax+rax+00h]
0x18003da83  mov     rcx, [rbp+38h]; this
0x18003da87  test    eax, eax
0x18003da89  js      short loc_18003DAF6
0x18003da8b  xor     ebx, ebx
0x18003da8d  cmp     [rsp+130h+var_D8], rbx
0x18003da92  jbe     short loc_18003DABE
0x18003da94  xor     eax, eax
0x18003da96  lea     rdx, [rbp+30h+pSid2]; pSid2
0x18003da9a  mov     rcx, [rsp+130h+var_E0]
0x18003da9f  mov     rcx, [rcx+rax*8]; pSid1
0x18003daa3  call    cs:__imp_EqualSid
0x18003daaa  nop     dword ptr [rax+rax+00h]
0x18003daaf  test    eax, eax
0x18003dab1  jnz     short loc_18003DAE8
0x18003dab3  inc     ebx
0x18003dab5  mov     eax, ebx
0x18003dab7  cmp     rax, [rsp+130h+var_D8]
0x18003dabc  jb      short loc_18003DA96
0x18003dabe  lea     rcx, [rsp+130h+var_E0]
0x18003dac3  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18003dac8  xor     al, al
0x18003daca  mov     rcx, [rbp+30h+var_10]
0x18003dace  xor     rcx, rsp; StackCookie
0x18003dad1  call    __security_check_cookie
0x18003dad6  mov     rbx, [rsp+130h+arg_8]
0x18003dade  add     rsp, 130h
0x18003dae5  pop     rbp
0x18003dae6  retn
0x18003dae8  lea     rcx, [rsp+130h+var_E0]
0x18003daed  call    ?reset@?$unique_any_array_ptr@PEAXU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<void *,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18003daf2  mov     al, 1
0x18003daf4  jmp     short loc_18003DACA
0x18003daf6  mov     r9d, eax; char *
0x18003daf9  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003db00  mov     edx, 2E1h; void *
0x18003db05  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x18003db0b  mov     r9d, eax; char *
0x18003db0e  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003db15  mov     edx, 2D5h; void *
0x18003db1a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
