# ServiceMain

- ea: `0x1800085d0`
- end: `0x18000864e`
- name: `ServiceMain`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000110c`
- `0x1800011bc`
- `0x180001a50`
- `0x180004284`
- `0x180006dc0`
- `0x180008508`
- `0x180008540`

## pseudocode

```c
__int64 ServiceMain()
{
  char v0; // dl
  __int128 v2; // [rsp+20h] [rbp-48h] BYREF
  _DWORD v3[8]; // [rsp+30h] [rbp-38h]
  __int64 v4; // [rsp+50h] [rbp-18h]

  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  McGenEventRegister_EventRegister();
  v3[0] = 16;
  v4 = 0;
  *(_OWORD *)&v3[3] = 0;
  v3[3] = 0;
  v2 = 0;
  *(_QWORD *)&v3[1] = 4;
  Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(
    (__int64)&v2,
    v0);
  Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::~Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>((__int64)&v2);
  McGenEventUnregister_EventUnregister();
  return TraceLoggingUnregister_EventUnregister();
}

```

## disassembly

```asm
0x1800085d0  sub     rsp, 68h
0x1800085d4  mov     rax, cs:__security_cookie
0x1800085db  xor     rax, rsp
0x1800085de  mov     [rsp+68h+var_10], rax
0x1800085e3  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800085e8  call    McGenEventRegister_EventRegister
0x1800085ed  xorps   xmm1, xmm1
0x1800085f0  lea     rcx, [rsp+68h+var_48]
0x1800085f5  movups  xmmword ptr [rsp+68h+var_38], xmm1
0x1800085fa  xor     eax, eax
0x1800085fc  mov     [rsp+68h+var_38], 10h
0x180008604  xorps   xmm0, xmm0
0x180008607  mov     [rsp+68h+var_18], rax
0x18000860c  movups  xmmword ptr [rsp+68h+var_38+0Ch], xmm1
0x180008611  mov     [rsp+68h+var_38+0Ch], eax
0x180008615  movdqu  [rsp+68h+var_48], xmm0
0x18000861b  mov     [rsp+68h+var_38+4], 4
0x180008623  call    ?RunServiceMain@?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@QEAAJE@Z; Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::RunServiceMain(uchar)
0x180008628  lea     rcx, [rsp+68h+var_48]
0x18000862d  call    ??1?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@QEAA@XZ; Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::~Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(void)
0x180008632  call    McGenEventUnregister_EventUnregister
0x180008637  call    TraceLoggingUnregister_EventUnregister
0x18000863c  mov     rcx, [rsp+68h+var_10]
0x180008641  xor     rcx, rsp; StackCookie
0x180008644  call    __security_check_cookie
0x180008649  add     rsp, 68h
0x18000864d  retn
```
