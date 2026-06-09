# pcmReadSample_M16M08

- ea: `0x180012340`
- end: `0x180012359`
- name: `pcmReadSample_M16M08`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001010`

## pseudocode

```c
unsigned __int8 *__fastcall pcmReadSample_M16M08(unsigned __int8 *a1, _WORD *a2)
{
  *a2 = (*a1 ^ 0xFF80) << 8;
  return a1 + 1;
}

```

## disassembly

```asm
0x180012340  movzx   eax, byte ptr [rcx]
0x180012343  mov     r8d, 0FF80h
0x180012349  xor     ax, r8w
0x18001234d  shl     ax, 8
0x180012351  mov     [rdx], ax
0x180012354  lea     rax, [rcx+1]
0x180012358  retn
```
