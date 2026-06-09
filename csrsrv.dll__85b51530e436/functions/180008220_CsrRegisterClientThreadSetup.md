# CsrRegisterClientThreadSetup

- ea: `0x180008220`
- end: `0x18000822a`
- name: `CsrRegisterClientThreadSetup`
- size: `10`
- prototype: `char __fastcall(__int64 (*)(void))`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
char __fastcall CsrRegisterClientThreadSetup(__int64 (*a1)(void))
{
  ClientThreadSetupRoutine = a1;
  return 1;
}

```

## disassembly

```asm
0x180008220  mov     cs:ClientThreadSetupRoutine, rcx
0x180008227  mov     al, 1
0x180008229  retn
```
