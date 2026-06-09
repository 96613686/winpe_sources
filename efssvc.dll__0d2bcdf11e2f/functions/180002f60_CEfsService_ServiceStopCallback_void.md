# CEfsService::ServiceStopCallback(void *)

- ea: `0x180002f60`
- end: `0x180002fa7`
- name: `?ServiceStopCallback@CEfsService@@CAJPEAX@Z`
- size: `71`
- prototype: `__int64 __fastcall(LPSERVICE_STATUS lpServiceStatus)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002cd4`
- `0x180002f60`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180002f8a`
- `ntdll!RtlNtStatusToDosError` at `0x180002f8a`
- `ntdll!NtClearEvent` at `0x180002f7c`
- `ntdll!NtClearEvent` at `0x180002f7c`

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
0x180002f60  push    rbx
0x180002f62  sub     rsp, 20h
0x180002f66  mov     rbx, rcx
0x180002f69  mov     eax, 0C000000Dh
0x180002f6e  test    rcx, rcx
0x180002f71  jz      short loc_180002FA0
0x180002f73  mov     rcx, [rcx+30h]; EventHandle
0x180002f77  test    rcx, rcx
0x180002f7a  jz      short loc_180002F88
0x180002f7c  call    cs:__imp_NtClearEvent
0x180002f83  nop     dword ptr [rax+rax+00h]
0x180002f88  mov     ecx, eax; Status
0x180002f8a  call    cs:__imp_RtlNtStatusToDosError
0x180002f91  nop     dword ptr [rax+rax+00h]
0x180002f96  mov     rcx, rbx; lpServiceStatus
0x180002f99  call    ?CleanupService@CEfsService@@QEAAXXZ; CEfsService::CleanupService(void)
0x180002f9e  xor     eax, eax
0x180002fa0  add     rsp, 20h
0x180002fa4  pop     rbx
0x180002fa5  retn
```
