# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,_MI_Result (*)(_MI_Instance *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,_MI_Result (*)(_MI_Instance *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>(void)

- ea: `0x18000776c`
- end: `0x18000778f`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Instance@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Instance_Delete_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b083`
- `0x18000b095`
- `0x18000b0b9`
- `0x18000b0cb`
- `0x18000b0ef`
- `0x18000b101`
- `0x18000b156`

## callees

- `0x18000776c`
- `0x18000c010`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,enum _MI_Result (*)(_MI_Instance *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Instance *,enum _MI_Result (*)(_MI_Instance *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Instance_Delete_Private(_MI_Instance *),wistd::integral_constant<unsigned __int64,0>,_MI_Instance *,_MI_Instance *,0,std::nullptr_t>>>(
        __int64 *a1)
{
  __int64 v1; // rcx

  v1 = *a1;
  if ( v1 )
  {
    if ( *(_QWORD *)v1 )
      (*(void (**)(void))(*(_QWORD *)v1 + 16LL))();
  }
}

```

## disassembly

```asm
0x18000776c  sub     rsp, 28h
0x180007770  mov     rcx, [rcx]
0x180007773  test    rcx, rcx
0x180007776  jz      short loc_18000778A
0x180007778  mov     rax, [rcx]
0x18000777b  test    rax, rax
0x18000777e  jz      short loc_18000778A
0x180007780  mov     rax, [rax+10h]
0x180007784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007789  nop
0x18000778a  add     rsp, 28h
0x18000778e  retn
```
