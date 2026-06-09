# _guard_dispatch_icall

- ea: `0x140010f60`
- end: `0x140010f66`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `18`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400021c0`
- `0x140002550`
- `0x140002730`
- `0x140002980`
- `0x1400029b0`
- `0x140003530`
- `0x140004d20`
- `0x14000510c`
- `0x1400051c0`
- `0x140005950`
- `0x140009880`
- `0x14000b700`
- `0x14000f0f8`
- `0x14000f264`
- `0x14000f98c`
- `0x14000fa54`
- `0x140012010`
- `0x1400265c0`

## callees

- `0x140010f90`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x140010f60  jmp     cs:__guard_dispatch_icall_fptr
```
