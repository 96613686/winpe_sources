# _guard_dispatch_icall

- ea: `0x140007170`
- end: `0x140007176`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `33`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002130`
- `0x140002240`
- `0x140002d80`
- `0x140002eb0`
- `0x140003a10`
- `0x140004000`
- `0x140004130`
- `0x140004c20`
- `0x140004e50`
- `0x1400051c0`
- `0x1400052a0`
- `0x140005490`
- `0x140005580`
- `0x140005a0c`
- `0x140005acc`
- `0x140005ba8`
- `0x140005c9c`
- `0x140005d88`
- `0x140006268`
- `0x1400062e4`
- `0x1400068bc`
- `0x140006978`
- `0x140006a74`
- `0x140006b70`
- `0x140006c6c`
- `0x140006e30`
- `0x140008010`
- `0x14000f118`
- `0x14000f1cc`
- `0x14000f320`
- `0x140010cf0`
- `0x14001130c`
- `0x140011660`

## callees

- `0x1400071a0`

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
0x140007170  jmp     cs:__guard_dispatch_icall_fptr
```
