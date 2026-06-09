# MupiTryStartUncHardeningRegistryWatcher

- ea: `0x14001e990`
- end: `0x14001e9c3`
- name: `MupiTryStartUncHardeningRegistryWatcher`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140014e38`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14001e9ac`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14001e9ac`

## pseudocode

```c
bool MupiTryStartUncHardeningRegistryWatcher()
{
  return RtlRunOnceExecuteOnce(
           &RunOnce,
           (PRTL_RUN_ONCE_INIT_FN)MupAttemptToLoadRegistryConfigurationRunOnce,
           &qword_14000A230,
           0) >= 0;
}

```

## disassembly

```asm
0x14001e990  sub     rsp, 28h
0x14001e994  xor     r9d, r9d; Context
0x14001e997  lea     r8, qword_14000A230; Parameter
0x14001e99e  lea     rdx, MupAttemptToLoadRegistryConfigurationRunOnce; InitFn
0x14001e9a5  lea     rcx, RunOnce; RunOnce
0x14001e9ac  call    cs:__imp_RtlRunOnceExecuteOnce
0x14001e9b3  nop     dword ptr [rax+rax+00h]
0x14001e9b8  shr     eax, 1Fh
0x14001e9bb  xor     al, 1
0x14001e9bd  add     rsp, 28h
0x14001e9c1  retn
```
