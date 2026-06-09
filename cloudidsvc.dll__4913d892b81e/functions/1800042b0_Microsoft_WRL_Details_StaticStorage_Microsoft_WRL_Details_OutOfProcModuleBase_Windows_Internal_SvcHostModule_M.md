# Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::~StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>(void)

- ea: `0x1800042b0`
- end: `0x1800042d6`
- name: `??1?$StaticStorage@V?$MethodReleaseNotifier@V?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@$02VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011500`
- `0x180011520`

## callees

- `0x1800042b0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>::~StaticStorage<Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>,3,Windows::Internal::SvcHostModule>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 32) )
  {
    result = (**(__int64 (__fastcall ***)(__int64, _QWORD))a1)(a1, 0);
    *(_BYTE *)(a1 + 32) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800042b0  push    rbx
0x1800042b2  sub     rsp, 20h
0x1800042b6  cmp     byte ptr [rcx+20h], 0
0x1800042ba  mov     rbx, rcx
0x1800042bd  jz      short loc_1800042D0
0x1800042bf  mov     rax, [rcx]
0x1800042c2  xor     edx, edx
0x1800042c4  mov     rax, [rax]
0x1800042c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042cc  mov     byte ptr [rbx+20h], 0
0x1800042d0  add     rsp, 20h
0x1800042d4  pop     rbx
0x1800042d5  retn
```
