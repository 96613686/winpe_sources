# ConfigureRetailDemoInternal::IsBuiltInUser(ushort const *)

- ea: `0x18004d7f4`
- end: `0x18004d8e4`
- name: `?IsBuiltInUser@ConfigureRetailDemoInternal@@IEAAHPEBG@Z`
- size: `240`
- prototype: `int(ConfigureRetailDemoInternal *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e110`

## callees

- `0x180003470`
- `0x18001e9a4`
- `0x18004d7f4`
- `0x18004e87c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18004d898`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18004d898`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18004d868`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18004d868`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d827`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d827`

## string_xrefs

- `0x18004d87a`: `shell\oobe\machine\plugins\retaildemo\retaildemoplugin.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ConfigureRetailDemoInternal::IsBuiltInUser(
        ConfigureRetailDemoInternal *this,
        const unsigned __int16 *a2)
{
  void *v3; // rbx
  const char *v4; // r9
  WELL_KNOWN_SID_TYPE i; // edi
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-138h] BYREF
  DWORD cchReferencedDomainName; // [rsp+44h] [rbp-134h] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-130h] BYREF
  _QWORD v10[2]; // [rsp+50h] [rbp-128h] BYREF
  WCHAR ReferencedDomainName[128]; // [rsp+60h] [rbp-118h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  peUse = 0;
  cbSid = 68;
  v3 = CoTaskMemAlloc(0x44u);
  v10[0] = v3;
  cchReferencedDomainName = 128;
  if ( !LookupAccountNameW(0, a2, v3, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xE5,
      (unsigned int)"shell\\oobe\\machine\\plugins\\retaildemo\\retaildemoplugin.cpp",
      v4);
  for ( i = WinNullSid; (unsigned int)i <= (WinBuiltinRemoteManagementUsersSid|WinSelfSid); ++i )
  {
    if ( IsWellKnownSid(v3, i) )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v10);
      return 1;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v10);
  return 0;
}

```

## disassembly

```asm
0x18004d7f4  mov     [rsp+arg_0], rbx
0x18004d7f9  push    rdi
0x18004d7fa  sub     rsp, 170h
0x18004d801  mov     rax, cs:__security_cookie
0x18004d808  xor     rax, rsp
0x18004d80b  mov     [rsp+178h+var_18], rax
0x18004d813  mov     rdi, rdx
0x18004d816  mov     [rsp+178h+var_138], 0
0x18004d81e  mov     ecx, 44h ; 'D'; cb
0x18004d823  mov     [rsp+178h+cbSid], ecx
0x18004d827  call    cs:__imp_CoTaskMemAlloc
0x18004d82d  mov     rbx, rax
0x18004d830  mov     [rsp+178h+var_128], rax
0x18004d835  mov     [rsp+178h+var_134], 80h
0x18004d83d  lea     rax, [rsp+178h+var_138]
0x18004d842  mov     [rsp+178h+peUse], rax; peUse
0x18004d847  lea     rax, [rsp+178h+var_134]
0x18004d84c  mov     [rsp+178h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18004d851  lea     rax, [rsp+178h+var_118]
0x18004d856  mov     [rsp+178h+ReferencedDomainName], rax; ReferencedDomainName
0x18004d85b  lea     r9, [rsp+178h+cbSid]; cbSid
0x18004d860  mov     r8, rbx; Sid
0x18004d863  mov     rdx, rdi; lpAccountName
0x18004d866  xor     ecx, ecx; lpSystemName
0x18004d868  call    cs:__imp_LookupAccountNameW
0x18004d86e  mov     rcx, [rsp+178h]; this
0x18004d876  test    eax, eax
0x18004d878  jnz     short loc_18004D88C
0x18004d87a  lea     r8, aShellOobeMachi_50; "shell\\oobe\\machine\\plugins\\retailde"...
0x18004d881  mov     edx, 0E5h; void *
0x18004d886  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004d88c  xor     edi, edi
0x18004d88e  cmp     edi, 76h ; 'v'
0x18004d891  ja      short loc_18004D8B7
0x18004d893  mov     edx, edi; WellKnownSidType
0x18004d895  mov     rcx, rbx; pSid
0x18004d898  call    cs:__imp_IsWellKnownSid
0x18004d89e  test    eax, eax
0x18004d8a0  jnz     short loc_18004D8A6
0x18004d8a2  inc     edi
0x18004d8a4  jmp     short loc_18004D88E
0x18004d8a6  lea     rcx, [rsp+178h+var_128]
0x18004d8ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004d8b0  mov     eax, 1
0x18004d8b5  jmp     short loc_18004D8C3
0x18004d8b7  lea     rcx, [rsp+178h+var_128]
0x18004d8bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004d8c1  xor     eax, eax
0x18004d8c3  mov     rcx, [rsp+178h+var_18]
0x18004d8cb  xor     rcx, rsp; StackCookie
0x18004d8ce  call    __security_check_cookie
0x18004d8d3  mov     rbx, [rsp+178h+arg_0]
0x18004d8db  add     rsp, 170h
0x18004d8e2  pop     rdi
0x18004d8e3  retn
```
