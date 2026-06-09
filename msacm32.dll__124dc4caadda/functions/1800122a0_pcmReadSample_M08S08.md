# pcmReadSample_M08S08

- ea: `0x1800122a0`
- end: `0x1800122df`
- name: `pcmReadSample_M08S08`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x1800122a0`

## pseudocode

```c
_WORD *__fastcall pcmReadSample_M08S08(_WORD *a1, char *a2)
{
  int v2; // r9d
  char v3; // r9

  v2 = (char)((unsigned __int16)(*a1 ^ 0x8080) >> 8) + (char)(*(_BYTE *)a1 ^ 0x80);
  if ( v2 <= 127 )
  {
    if ( v2 >= -128 )
      v3 = v2 ^ 0x80;
    else
      v3 = 0;
  }
  else
  {
    v3 = -1;
  }
  *a2 = v3;
  return a1 + 1;
}

```

## disassembly

```asm
0x1800122a0  mov     r9d, 8080h
0x1800122a6  xor     r9w, [rcx]
0x1800122aa  movzx   eax, r9w
0x1800122ae  movsx   r9d, r9b
0x1800122b2  shr     ax, 8
0x1800122b6  movsx   r8d, al
0x1800122ba  add     r9d, r8d
0x1800122bd  cmp     r9d, 7Fh
0x1800122c1  jle     short loc_1800122C8
0x1800122c3  mov     r9b, 0FFh
0x1800122c6  jmp     short loc_1800122D7
0x1800122c8  cmp     r9d, 0FFFFFF80h
0x1800122cc  jge     short loc_1800122D3
0x1800122ce  xor     r9b, r9b
0x1800122d1  jmp     short loc_1800122D7
0x1800122d3  xor     r9b, 80h
0x1800122d7  mov     [rdx], r9b
0x1800122da  lea     rax, [rcx+2]
0x1800122de  retn
```
