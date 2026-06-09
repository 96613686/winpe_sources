# ReportFault

- ea: `0x18000e6d0`
- end: `0x18000e713`
- name: `ReportFault`
- size: `67`
- prototype: `EFaultRepRetVal __stdcall(LPEXCEPTION_POINTERS pep, DWORD dwOpt)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800425b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e6d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e6d9`
- `ntdll!DbgPrintEx` at `0x18000e6fb`
- `ntdll!DbgPrintEx` at `0x18000e6fb`

## pseudocode

```c
EFaultRepRetVal __stdcall ReportFault(LPEXCEPTION_POINTERS pep, DWORD dwOpt)
{
  DWORD CurrentProcessId; // eax

  CurrentProcessId = GetCurrentProcessId();
  DbgPrintEx(0x96u, 3u, "WER/CrashExp/%u:%u: INFO ReportFault called\n", CurrentProcessId, 784);
  return (unsigned int)WerpReportFault(pep, 2);
}

```

## disassembly

```asm
0x18000e6d0  push    rbx
0x18000e6d2  sub     rsp, 30h
0x18000e6d6  mov     rbx, rcx
0x18000e6d9  call    cs:__imp_GetCurrentProcessId
0x18000e6df  lea     r8, aWerCrashexpUUI; "WER/CrashExp/%u:%u: INFO ReportFault ca"...
0x18000e6e6  mov     [rsp+38h+var_18], 310h
0x18000e6ee  mov     r9d, eax
0x18000e6f1  mov     edx, 3; Level
0x18000e6f6  mov     ecx, 96h; ComponentId
0x18000e6fb  call    cs:__imp_DbgPrintEx
0x18000e701  mov     edx, 2
0x18000e706  mov     rcx, rbx
0x18000e709  add     rsp, 30h
0x18000e70d  pop     rbx
0x18000e70e  jmp     WerpReportFault
```
