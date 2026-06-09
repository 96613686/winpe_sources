# Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(void)

- ea: `0x1800074b0`
- end: `0x1800074ea`
- name: `?StopAsync@?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@IEAAXXZ`
- size: `58`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005f10`

## callees

- `0x1800074b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800074e3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800074d4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800074d4`

## pseudocode

```c
BOOL __fastcall Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::StopAsync(
        __int64 a1)
{
  if ( ((*(_DWORD *)(a1 + 20) - 1) & 0xFFFFFFFD) != 0 )
  {
    *(_DWORD *)(a1 + 20) = 3;
    SetServiceStatus(*(SERVICE_STATUS_HANDLE *)(a1 + 8), (LPSERVICE_STATUS)(a1 + 16));
  }
  return SetEvent(*(HANDLE *)(a1 + 48));
}

```

## disassembly

```asm
0x1800074b0  push    rbx
0x1800074b2  sub     rsp, 20h
0x1800074b6  lea     rdx, [rcx+10h]; lpServiceStatus
0x1800074ba  mov     rbx, rcx
0x1800074bd  mov     eax, [rdx+4]
0x1800074c0  dec     eax
0x1800074c2  test    eax, 0FFFFFFFDh
0x1800074c7  jz      short loc_1800074DA
0x1800074c9  mov     dword ptr [rcx+14h], 3
0x1800074d0  mov     rcx, [rcx+8]; hServiceStatus
0x1800074d4  call    cs:__imp_SetServiceStatus
0x1800074da  mov     rcx, [rbx+30h]
0x1800074de  add     rsp, 20h
0x1800074e2  pop     rbx
0x1800074e3  jmp     cs:__imp_SetEvent
```
