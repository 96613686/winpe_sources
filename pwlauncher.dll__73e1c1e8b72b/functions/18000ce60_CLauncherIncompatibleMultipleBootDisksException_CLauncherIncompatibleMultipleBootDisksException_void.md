# CLauncherIncompatibleMultipleBootDisksException::CLauncherIncompatibleMultipleBootDisksException(void)

- ea: `0x18000ce60`
- end: `0x18000ce6a`
- name: `??0CLauncherIncompatibleMultipleBootDisksException@@QEAA@XZ`
- size: `10`
- prototype: `CLauncherIncompatibleMultipleBootDisksException *__fastcall(CLauncherIncompatibleMultipleBootDisksException *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000d3d0`

## pseudocode

```c
CLauncherIncompatibleMultipleBootDisksException *__fastcall CLauncherIncompatibleMultipleBootDisksException::CLauncherIncompatibleMultipleBootDisksException(
        CLauncherIncompatibleMultipleBootDisksException *this)
{
  *(_DWORD *)this = -2147220992;
  return this;
}

```

## disassembly

```asm
0x18000ce60  mov     dword ptr [rcx], 80040200h
0x18000ce66  mov     rax, rcx
0x18000ce69  retn
```
