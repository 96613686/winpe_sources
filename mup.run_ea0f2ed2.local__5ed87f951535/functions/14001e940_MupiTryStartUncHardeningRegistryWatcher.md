# MupiTryStartUncHardeningRegistryWatcher

- ea: `0x14001e940`
- end: `0x14001e973`
- name: `MupiTryStartUncHardeningRegistryWatcher`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140014de8`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14001e95c`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x14001e95c`

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
0x14001e940  sub     rsp, 28h
0x14001e944  xor     r9d, r9d; Context
0x14001e947  lea     r8, qword_14000A230; Parameter
0x14001e94e  lea     rdx, MupAttemptToLoadRegistryConfigurationRunOnce; InitFn
0x14001e955  lea     rcx, RunOnce; RunOnce
0x14001e95c  call    cs:__imp_RtlRunOnceExecuteOnce
0x14001e963  nop     dword ptr [rax+rax+00h]
0x14001e968  shr     eax, 1Fh
0x14001e96b  xor     al, 1
0x14001e96d  add     rsp, 28h
0x14001e971  retn
```
