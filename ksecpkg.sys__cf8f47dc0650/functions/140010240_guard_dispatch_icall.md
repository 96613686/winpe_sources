# _guard_dispatch_icall

- ea: `0x140010240`
- end: `0x140010246`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `85`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140002dc0`
- `0x1400043a0`
- `0x1400045b0`
- `0x140004730`
- `0x140004da0`
- `0x1400055f0`
- `0x14000561c`
- `0x140005bc4`
- `0x140007330`
- `0x1400073f0`
- `0x140007600`
- `0x1400078f8`
- `0x140007ef8`
- `0x140007f68`
- `0x1400081a4`
- `0x140008248`
- `0x140008320`
- `0x1400083d8`
- `0x140008740`
- `0x14000a6f0`
- `0x14000b07c`
- `0x14000bd34`
- `0x14000d910`
- `0x14000e120`
- `0x14000e1a0`
- `0x14000e344`
- `0x14000e55c`
- `0x14000f0a8`
- `0x14000f244`
- `0x140011020`
- `0x140020b90`
- `0x140020c10`
- `0x140020d50`
- `0x140021020`
- `0x140021160`
- `0x1400214a0`
- `0x140021590`
- `0x140021c10`
- `0x1400220c0`
- `0x140022280`
- `0x140022510`
- `0x140022b00`
- `0x1400230a0`
- `0x140023500`
- `0x140023580`
- `0x140023db0`
- `0x140024008`
- `0x14002510c`
- `0x140025504`
- `0x140025df0`

## callees

- `0x1400101e0`

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
0x140010240  jmp     cs:__guard_dispatch_icall_fptr
```
