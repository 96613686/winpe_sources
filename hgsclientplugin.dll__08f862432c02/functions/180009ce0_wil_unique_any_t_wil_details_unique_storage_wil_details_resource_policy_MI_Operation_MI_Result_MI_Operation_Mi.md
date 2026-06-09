# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Operation *,_MI_Result (*)(_MI_Operation *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *),wistd::integral_constant<unsigned __int64,0>,_MI_Operation *,_MI_Operation *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Operation *,_MI_Result (*)(_MI_Operation *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *),wistd::integral_constant<unsigned __int64,0>,_MI_Operation *,_MI_Operation *,0,std::nullptr_t>>>(void)

- ea: `0x180009ce0`
- end: `0x180009cf6`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Operation@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Operation_Close_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: `enum _MI_Result __fastcall(Microsoft::HostGuardian::Client::Plugin::CimUtilities **, struct _MI_Operation *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b113`

## callees

- `0x180009ce0`
- `0x18000a3a0`

## pseudocode

```c
enum _MI_Result __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Operation *,enum _MI_Result (*)(_MI_Operation *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *),wistd::integral_constant<unsigned __int64,0>,_MI_Operation *,_MI_Operation *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Operation *,enum _MI_Result (*)(_MI_Operation *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *),wistd::integral_constant<unsigned __int64,0>,_MI_Operation *,_MI_Operation *,0,std::nullptr_t>>>(
        Microsoft::HostGuardian::Client::Plugin::CimUtilities **a1,
        struct _MI_Operation *a2)
{
  Microsoft::HostGuardian::Client::Plugin::CimUtilities *v2; // rcx
  enum _MI_Result result; // eax

  v2 = *a1;
  if ( v2 )
    return Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(v2, a2);
  return result;
}

```

## disassembly

```asm
0x180009ce0  sub     rsp, 28h
0x180009ce4  mov     rcx, [rcx]; this
0x180009ce7  test    rcx, rcx
0x180009cea  jz      short loc_180009CF1
0x180009cec  call    ?MI_Operation_Close_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW4_MI_Result@@PEAU_MI_Operation@@@Z; Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Operation_Close_Private(_MI_Operation *)
0x180009cf1  add     rsp, 28h
0x180009cf5  retn
```
