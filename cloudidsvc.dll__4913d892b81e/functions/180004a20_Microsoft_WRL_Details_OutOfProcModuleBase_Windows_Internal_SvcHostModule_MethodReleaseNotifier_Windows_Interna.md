# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`scalar deleting destructor'(uint)

- ea: `0x180004a20`
- end: `0x180004a4b`
- name: `??_G?$MethodReleaseNotifier@V?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180001a74`
- `0x180004a20`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::`scalar deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180004a20  push    rbx
0x180004a22  sub     rsp, 20h
0x180004a26  lea     rax, ??_7ReleaseNotifier@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::ReleaseNotifier::`vftable'
0x180004a2d  mov     rbx, rcx
0x180004a30  mov     [rcx], rax
0x180004a33  test    dl, 1
0x180004a36  jz      short loc_180004A42
0x180004a38  mov     edx, 20h ; ' '; unsigned __int64
0x180004a3d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004a42  mov     rax, rbx
0x180004a45  add     rsp, 20h
0x180004a49  pop     rbx
0x180004a4a  retn
```
