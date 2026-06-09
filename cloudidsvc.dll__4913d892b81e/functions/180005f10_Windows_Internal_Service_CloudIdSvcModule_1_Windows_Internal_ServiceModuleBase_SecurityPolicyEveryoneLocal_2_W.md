# Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic(ulong,ulong,void *,void *)

- ea: `0x180005f10`
- end: `0x180005f34`
- name: `?HandlerExStatic@?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@CAKKKPEAX0@Z`
- size: `36`
- prototype: `__int64 __fastcall(DWORD dwControl, __int64 dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005f10`
- `0x1800074b0`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::HandlerExStatic(
        DWORD dwControl,
        __int64 dwEventType,
        LPVOID lpEventData,
        LPVOID lpContext)
{
  if ( dwControl == 1 )
  {
    Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(
      lpContext,
      dwEventType,
      lpEventData);
    return 0;
  }
  if ( dwControl == 4 )
    return 0;
  return 120;
}

```

## disassembly

```asm
0x180005f10  sub     rsp, 28h
0x180005f14  cmp     ecx, 1
0x180005f17  jnz     short loc_180005F28
0x180005f19  mov     rcx, r9
0x180005f1c  call    ?StopAsync@?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXXZ; Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(void)
0x180005f21  xor     eax, eax
0x180005f23  add     rsp, 28h
0x180005f27  retn
0x180005f28  cmp     ecx, 4
0x180005f2b  jz      short loc_180005F21
0x180005f2d  mov     eax, 78h ; 'x'
0x180005f32  jmp     short loc_180005F23
```
