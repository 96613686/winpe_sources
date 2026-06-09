# Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::~Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(void)

- ea: `0x180004284`
- end: `0x1800042aa`
- name: `??1?$Service@VCloudIdSvcModule@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@QEAA@XZ`
- size: `38`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800085d0`

## callees

- `0x180004284`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004296`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004296`

## pseudocode

```c
BOOL __fastcall Windows::Internal::Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>::~Service<CloudIdSvcModule,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>(
        __int64 a1)
{
  void *v2; // rcx
  BOOL result; // eax

  v2 = *(void **)(a1 + 48);
  if ( v2 )
  {
    result = CloseHandle(v2);
    *(_QWORD *)(a1 + 48) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004284  push    rbx
0x180004286  sub     rsp, 20h
0x18000428a  mov     rbx, rcx
0x18000428d  mov     rcx, [rcx+30h]; hObject
0x180004291  test    rcx, rcx
0x180004294  jz      short loc_1800042A4
0x180004296  call    cs:__imp_CloseHandle
0x18000429c  mov     qword ptr [rbx+30h], 0
0x1800042a4  add     rsp, 20h
0x1800042a8  pop     rbx
0x1800042a9  retn
```
