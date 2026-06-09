# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Session *,_MI_Result (*)(_MI_Session *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Session_Close_Private(_MI_Session *),wistd::integral_constant<unsigned __int64,0>,_MI_Session *,_MI_Session *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Session *,_MI_Result (*)(_MI_Session *),&Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Session_Close_Private(_MI_Session *),wistd::integral_constant<unsigned __int64,0>,_MI_Session *,_MI_Session *,0,std::nullptr_t>>>(void)

- ea: `0x180009040`
- end: `0x180009068`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_MI_Session@@P6A?AW4_MI_Result@@PEAU1@@Z$1?MI_Session_Close_Private@CimUtilities@Plugin@Client@HostGuardian@Microsoft@@YA?AW42@0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b071`
- `0x18000b0a7`
- `0x18000b0dd`

## callees

- `0x180009040`
- `0x18000c010`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Session *,enum _MI_Result (*)(_MI_Session *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Session_Close_Private(_MI_Session *),wistd::integral_constant<unsigned __int64,0>,_MI_Session *,_MI_Session *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_MI_Session *,enum _MI_Result (*)(_MI_Session *),&enum _MI_Result Microsoft::HostGuardian::Client::Plugin::CimUtilities::MI_Session_Close_Private(_MI_Session *),wistd::integral_constant<unsigned __int64,0>,_MI_Session *,_MI_Session *,0,std::nullptr_t>>>(
        __int64 *a1)
{
  __int64 v1; // rcx
  void (__fastcall **v2)(__int64, _QWORD, _QWORD); // rax

  v1 = *a1;
  if ( v1 )
  {
    v2 = *(void (__fastcall ***)(__int64, _QWORD, _QWORD))(v1 + 16);
    if ( v2 )
      (*v2)(v1, 0, 0);
  }
}

```

## disassembly

```asm
0x180009040  sub     rsp, 28h
0x180009044  mov     rcx, [rcx]
0x180009047  test    rcx, rcx
0x18000904a  jz      short loc_180009063
0x18000904c  mov     rax, [rcx+10h]
0x180009050  test    rax, rax
0x180009053  jz      short loc_180009063
0x180009055  xor     r8d, r8d
0x180009058  xor     edx, edx
0x18000905a  mov     rax, [rax]
0x18000905d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009062  nop
0x180009063  add     rsp, 28h
0x180009067  retn
```
