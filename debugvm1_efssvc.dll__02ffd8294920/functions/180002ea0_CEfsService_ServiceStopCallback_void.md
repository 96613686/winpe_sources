# CEfsService::ServiceStopCallback(void *)

- ea: `0x180002ea0`
- end: `0x180002eda`
- name: `?ServiceStopCallback@CEfsService@@CAJPEAX@Z`
- size: `58`
- prototype: `__int64 __fastcall(LPSERVICE_STATUS lpServiceStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002c60`
- `0x180002ea0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002ec4`
- `ntdll!RtlNtStatusToDosError` at `0x180002ec4`
- `ntdll!NtClearEvent` at `0x180002ebc`
- `ntdll!NtClearEvent` at `0x180002ebc`

## pseudocode

```c
__int64 __fastcall CEfsService::ServiceStopCallback(LPSERVICE_STATUS lpServiceStatus)
{
  __int64 result; // rax
  void *v3; // rcx

  result = 3221225485LL;
  if ( lpServiceStatus )
  {
    v3 = *(void **)&lpServiceStatus[1].dwCheckPoint;
    if ( v3 )
      LODWORD(result) = NtClearEvent(v3);
    RtlNtStatusToDosError(result);
    CEfsService::CleanupService(lpServiceStatus);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002ea0  push    rbx
0x180002ea2  sub     rsp, 20h
0x180002ea6  mov     rbx, rcx
0x180002ea9  mov     eax, 0C000000Dh
0x180002eae  test    rcx, rcx
0x180002eb1  jz      short loc_180002ED4
0x180002eb3  mov     rcx, [rcx+30h]; EventHandle
0x180002eb7  test    rcx, rcx
0x180002eba  jz      short loc_180002EC2
0x180002ebc  call    cs:__imp_NtClearEvent
0x180002ec2  mov     ecx, eax; Status
0x180002ec4  call    cs:__imp_RtlNtStatusToDosError
0x180002eca  mov     rcx, rbx; lpServiceStatus
0x180002ecd  call    ?CleanupService@CEfsService@@QEAAXXZ; CEfsService::CleanupService(void)
0x180002ed2  xor     eax, eax
0x180002ed4  add     rsp, 20h
0x180002ed8  pop     rbx
0x180002ed9  retn
```
