# MupiTryStartPoliciesKeyRegistryWatcher

- ea: `0x140016fd8`
- end: `0x140017007`
- name: `MupiTryStartPoliciesKeyRegistryWatcher`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140010f18`
- `0x14001a128`

## import_xrefs

- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140016ff0`
- `ntoskrnl!RtlRunOnceExecuteOnce` at `0x140016ff0`

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
0x140016fd8  sub     rsp, 28h
0x140016fdc  lea     rcx, MupiPoliciesKeyRegistryWatcher; RunOnce
0x140016fe3  xor     r9d, r9d; Context
0x140016fe6  mov     r8, rcx; Parameter
0x140016fe9  lea     rdx, MupAttempttoLoadRegistryPoliciesKeyRunOnce; InitFn
0x140016ff0  call    cs:__imp_RtlRunOnceExecuteOnce
0x140016ff7  nop     dword ptr [rax+rax+00h]
0x140016ffc  shr     eax, 1Fh
0x140016fff  xor     al, 1
0x140017001  add     rsp, 28h
0x140017005  retn
```
