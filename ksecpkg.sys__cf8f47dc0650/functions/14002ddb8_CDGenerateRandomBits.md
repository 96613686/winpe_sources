# CDGenerateRandomBits

- ea: `0x14002ddb8`
- end: `0x14002ddde`
- name: `CDGenerateRandomBits`
- size: `38`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e93c`
- `0x14000f318`
- `0x140027324`
- `0x1400276c0`
- `0x14002a4d8`
- `0x14002d4c0`
- `0x14002e7b0`
- `0x14002eb70`
- `0x14002eea0`

## callees

- `0x140010240`

## pseudocode

```c
__int64 CDGenerateRandomBits()
{
  return qword_1400197F0[3 * (unsigned int)(cRngs - 1)]();
}

```

## disassembly

```asm
0x14002ddb8  sub     rsp, 28h
0x14002ddbc  mov     eax, cs:cRngs
0x14002ddc2  lea     r8, qword_1400197F0
0x14002ddc9  dec     eax
0x14002ddcb  lea     rax, [rax+rax*2]
0x14002ddcf  mov     rax, [r8+rax*8]
0x14002ddd3  call    _guard_dispatch_icall
0x14002ddd8  add     rsp, 28h
0x14002dddc  retn
```
