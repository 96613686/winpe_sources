# _guard_dispatch_icall_nop

- ea: `0x18001ed60`
- end: `0x18001ed62`
- name: `_guard_dispatch_icall_nop`
- size: `2`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18000f260`
- `0x18000f4d4`
- `0x18000f6f4`
- `0x18001ed90`
- `0x18001ee20`

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
0x18001ed60  jmp     rax
```
