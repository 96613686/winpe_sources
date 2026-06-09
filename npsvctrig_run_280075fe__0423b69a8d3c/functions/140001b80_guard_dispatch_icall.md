# _guard_dispatch_icall

- ea: `0x140001b80`
- end: `0x140001b86`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001220`
- `0x1400017b0`
- `0x140001928`
- `0x140003010`
- `0x1400080e0`
- `0x1400085ac`
- `0x140008630`
- `0x140009230`
- `0x140009a50`

## callees

- `0x140001bb0`

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
0x140001b80  jmp     cs:__guard_dispatch_icall_fptr
```
