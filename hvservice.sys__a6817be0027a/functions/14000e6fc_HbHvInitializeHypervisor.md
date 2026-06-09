# HbHvInitializeHypervisor

- ea: `0x14000e6fc`
- end: `0x14000e756`
- name: `HbHvInitializeHypervisor`
- size: `90`
- prototype: `__int64 __fastcall(PVOID DeferredContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000fc48`

## callees

- `0x14000e6fc`
- `0x14000e7b8`
- `0x14000e9a4`
- `0x14000ea28`
- `0x1400115a0`

## import_xrefs

- `winhvr!WinHvSetEventLogCompletedNotificationRoutine` at `0x14000e729`
- `winhvr!WinHvSetEventLogCompletedNotificationRoutine` at `0x14000e729`
- `winhvr!WinHvReportPresentHypervisor` at `0x14000e705`
- `winhvr!WinHvReportPresentHypervisor` at `0x14000e705`

## pseudocode

```c
__int64 __fastcall HbHvInitializeHypervisor(PVOID DeferredContext)
{
  WinHvReportPresentHypervisor();
  if ( HbpIsCpuManagementPartition )
  {
    HbHvpOpenHypervisorBinaryFileHandles((__int64)DeferredContext);
    WinHvSetEventLogCompletedNotificationRoutine(HbEvtpCompletedNotificationRoutine);
    HbHvpRegisterDebuggerPowerCallback(DeferredContext);
  }
  HbHvpWithdrawMemory(DeferredContext);
  HbEvtpInitEventLog((char *)DeferredContext);
  return 0;
}

```

## disassembly

```asm
0x14000e6fc  push    rbx
0x14000e6fe  sub     rsp, 20h
0x14000e702  mov     rbx, rcx
0x14000e705  call    cs:__imp_WinHvReportPresentHypervisor
0x14000e70c  nop     dword ptr [rax+rax+00h]
0x14000e711  cmp     cs:HbpIsCpuManagementPartition, 0
0x14000e718  jz      short loc_14000E73D
0x14000e71a  mov     rcx, rbx
0x14000e71d  call    HbHvpOpenHypervisorBinaryFileHandles
0x14000e722  lea     rcx, HbEvtpCompletedNotificationRoutine
0x14000e729  call    cs:__imp_WinHvSetEventLogCompletedNotificationRoutine
0x14000e730  nop     dword ptr [rax+rax+00h]
0x14000e735  mov     rcx, rbx
0x14000e738  call    HbHvpRegisterDebuggerPowerCallback
0x14000e73d  mov     rcx, rbx; Context
0x14000e740  call    HbHvpWithdrawMemory
0x14000e745  mov     rcx, rbx; DeferredContext
0x14000e748  call    HbEvtpInitEventLog
0x14000e74d  xor     eax, eax
0x14000e74f  add     rsp, 20h
0x14000e753  pop     rbx
0x14000e754  retn
```
