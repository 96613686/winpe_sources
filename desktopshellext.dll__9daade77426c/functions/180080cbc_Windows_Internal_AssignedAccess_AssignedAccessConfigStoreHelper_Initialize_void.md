# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::Initialize(void)

- ea: `0x180080cbc`
- end: `0x180080d5d`
- name: `?Initialize@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAA_NXZ`
- size: `161`
- prototype: `bool __fastcall(Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007ff68`

## callees

- `0x18000c444`
- `0x180080aec`
- `0x180080bec`
- `0x180080cbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080d25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080d25`

## string_xrefs

- `0x180080cde`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration`
- `0x180080cd7`: `AssignedAccessConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::Initialize(LPVOID *this)
{
  void *v3; // rdi
  void *v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  if ( (int)Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(
              L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration",
              L"AssignedAccessConfiguration",
              &v4) >= 0
    && (v3 = v4) != 0 )
  {
    v4 = 0;
    if ( *this )
      CoTaskMemFree(*this);
    *this = v3;
    this[2] = (LPVOID)-1LL;
    this[1] = (LPVOID)-1LL;
    *((_DWORD *)this + 6) = Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion((Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper *)this);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v4);
    return 1;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v4);
    return 0;
  }
}

```

## disassembly

```asm
0x180080cbc  mov     [rsp+arg_0], rbx
0x180080cc1  push    rdi
0x180080cc2  sub     rsp, 20h
0x180080cc6  mov     rbx, rcx
0x180080cc9  mov     [rsp+28h+arg_8], 0
0x180080cd2  lea     r8, [rsp+28h+arg_8]
0x180080cd7  lea     rdx, aAssignedaccess; "AssignedAccessConfiguration"
0x180080cde  lea     rcx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x180080ce5  call    ?GetRedirectedPathIfNeeded@PersistentLocationHelper@AssignedAccess@Internal@Windows@@SAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::AssignedAccess::PersistentLocationHelper::GetRedirectedPathIfNeeded(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180080cea  test    eax, eax
0x180080cec  jns     short loc_180080CFD
0x180080cee  lea     rcx, [rsp+28h+arg_8]
0x180080cf3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180080cf8  nop
0x180080cf9  xor     al, al
0x180080cfb  jmp     short loc_180080D52
0x180080cfd  mov     rdi, [rsp+28h+arg_8]
0x180080d02  test    rdi, rdi
0x180080d05  jnz     short loc_180080D14
0x180080d07  lea     rcx, [rsp+28h+arg_8]
0x180080d0c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180080d11  nop
0x180080d12  jmp     short loc_180080CF9
0x180080d14  mov     [rsp+28h+arg_8], 0
0x180080d1d  mov     rcx, [rbx]; pv
0x180080d20  test    rcx, rcx
0x180080d23  jz      short loc_180080D2B
0x180080d25  call    cs:__imp_CoTaskMemFree
0x180080d2b  mov     [rbx], rdi
0x180080d2e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180080d32  mov     [rbx+10h], rax
0x180080d36  mov     [rbx+8], rax
0x180080d3a  mov     rcx, rbx; this
0x180080d3d  call    ?GetStoreVersion@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAAKXZ; Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion(void)
0x180080d42  mov     [rbx+18h], eax
0x180080d45  lea     rcx, [rsp+28h+arg_8]
0x180080d4a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180080d4f  nop
0x180080d50  mov     al, 1
0x180080d52  mov     rbx, [rsp+28h+arg_0]
0x180080d57  add     rsp, 20h
0x180080d5b  pop     rdi
0x180080d5c  retn
```
