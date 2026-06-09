# MupiTryStartPoliciesKeyRegistryWatcher

- ea: `0x140016f88`
- end: `0x140016fb7`
- name: `MupiTryStartPoliciesKeyRegistryWatcher`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140010f18`
- `0x14001a0d8`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140016fa0`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140016fa0`

## pseudocode

```c
bool MupiTryStartPoliciesKeyRegistryWatcher()
{
  return RtlRunOnceExecuteOnce(
           &MupiPoliciesKeyRegistryWatcher,
           (PRTL_RUN_ONCE_INIT_FN)MupAttempttoLoadRegistryPoliciesKeyRunOnce,
           &MupiPoliciesKeyRegistryWatcher,
           0) >= 0;
}

```

## disassembly

```asm
0x140016f88  sub     rsp, 28h
0x140016f8c  lea     rcx, MupiPoliciesKeyRegistryWatcher; RunOnce
0x140016f93  xor     r9d, r9d; Context
0x140016f96  mov     r8, rcx; Parameter
0x140016f99  lea     rdx, MupAttempttoLoadRegistryPoliciesKeyRunOnce; InitFn
0x140016fa0  call    cs:__imp_RtlRunOnceExecuteOnce
0x140016fa7  nop     dword ptr [rax+rax+00h]
0x140016fac  shr     eax, 1Fh
0x140016faf  xor     al, 1
0x140016fb1  add     rsp, 28h
0x140016fb5  retn
```
