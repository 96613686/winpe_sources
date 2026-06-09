# _guard_dispatch_icall_nop

- ea: `0x180088750`
- end: `0x180088752`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `229`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x180009930`
- `0x180009be0`
- `0x18000a990`
- `0x18000aed0`
- `0x18000b050`
- `0x18000b5e0`
- `0x18000b690`
- `0x18000bd10`
- `0x18000bd50`
- `0x18000c5d0`
- `0x18000d2f0`
- `0x18000d4b0`
- `0x18000d580`
- `0x18000dbb0`
- `0x18000dcc0`
- `0x18000de70`
- `0x18000e640`
- `0x18000eb60`
- `0x18000f9f0`
- `0x1800110a0`
- `0x180011200`
- `0x1800115c0`
- `0x180011650`
- `0x180011670`
- `0x180011860`
- `0x180012bf0`
- `0x180012d70`
- `0x180013110`
- `0x180013320`
- `0x1800134a0`
- `0x180013720`
- `0x1800137d0`
- `0x180013b20`
- `0x180013ba0`
- `0x180015a40`
- `0x1800168e0`
- `0x1800177a0`
- `0x180017950`
- `0x180018650`
- `0x1800186c0`
- `0x1800187b0`
- `0x18001a6b0`
- `0x18001ab80`
- `0x18001b1d0`
- `0x18001b610`
- `0x18001bb60`
- `0x18001d6e0`
- `0x18001e5a0`
- `0x18001e6e0`
- `0x18001ebc0`

## pseudocode

```c
__int64 __fastcall guard_dispatch_icall_nop()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x180088750  jmp     rax
```
