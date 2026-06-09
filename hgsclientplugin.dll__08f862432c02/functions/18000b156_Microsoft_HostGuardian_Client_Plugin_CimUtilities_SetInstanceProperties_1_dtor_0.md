# _Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties_::_1_::dtor$0

- ea: `0x18000b156`
- end: `0x18000b17c`
- name: `_Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties_::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000776c`
- `0x18000b156`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::CimUtilities::SetInstanceProperties_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,enum _MI_Result (*)(_MI_Instance *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,enum _MI_Result (*)(_MI_Instance *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>(*(__int64 **)(a2 + 96));
  }
}

```

## disassembly

```asm
0x18000b156  push    rbp
0x18000b158  sub     rsp, 20h
0x18000b15c  mov     rbp, rdx
0x18000b15f  mov     eax, [rbp+30h]
0x18000b162  and     eax, 1
0x18000b165  test    eax, eax
0x18000b167  jz      short loc_18000B176
0x18000b169  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18000b16d  mov     rcx, [rbp+60h]
0x18000b171  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,_MI_Result (*)(_MI_Instance *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,_MI_Result (*)(_MI_Instance *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>(void)
0x18000b176  add     rsp, 20h
0x18000b17a  pop     rbp
0x18000b17b  retn
```
