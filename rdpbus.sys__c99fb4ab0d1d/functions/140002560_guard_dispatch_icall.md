# _guard_dispatch_icall

- ea: `0x140002560`
- end: `0x140002566`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400020b4`
- `0x1400020e4`
- `0x140002128`
- `0x140002180`
- `0x1400021f4`
- `0x140002278`
- `0x140002304`
- `0x140003010`
- `0x140008074`
- `0x1400080f8`
- `0x14000818c`
- `0x1400082e0`
- `0x140009120`
- `0x140009c14`

## callees

- `0x140002590`

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
0x140002560  jmp     cs:__guard_dispatch_icall_fptr
```
