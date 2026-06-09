# _wil::make_unique_string_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_wchar_t___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__wchar_t___wchar_t___0_std::nullptr_t________::_1_::dtor$0

- ea: `0x18000ad86`
- end: `0x18000adac`
- name: `_wil::make_unique_string_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_wchar_t___void_(__cdecl_)(void__)_&CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__wchar_t___wchar_t___0_std::nullptr_t________::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180007798`
- `0x18000ad86`

## pseudocode

```c
void __fastcall wil::make_unique_string_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_wchar_t___void____cdecl___void_____CoTaskMemFree_wistd::integral_constant_unsigned___int64_0__wchar_t___wchar_t___0_std::nullptr_t________::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>(*(void ***)(a2 + 96));
  }
}

```

## disassembly

```asm
0x18000ad86  push    rbp
0x18000ad88  sub     rsp, 20h
0x18000ad8c  mov     rbp, rdx
0x18000ad8f  mov     eax, [rbp+20h]
0x18000ad92  and     eax, 1
0x18000ad95  test    eax, eax
0x18000ad97  jz      short loc_18000ADA6
0x18000ad99  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000ad9d  mov     rcx, [rbp+60h]
0x18000ada1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>(void)
0x18000ada6  add     rsp, 20h
0x18000adaa  pop     rbp
0x18000adab  retn
```
