# _guard_dispatch_icall

- ea: `0x140013150`
- end: `0x140013156`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140007260`
- `0x140009860`
- `0x14000a380`
- `0x14000c42c`
- `0x14000eb54`
- `0x14000f48c`
- `0x14000f4bc`
- `0x14000f508`
- `0x14000fe04`
- `0x14001144c`
- `0x140014010`
- `0x14001e808`
- `0x14001e88c`
- `0x14001e920`
- `0x14001ea70`

## callees

- `0x140013180`

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
0x140013150  jmp     cs:__guard_dispatch_icall_fptr
```
