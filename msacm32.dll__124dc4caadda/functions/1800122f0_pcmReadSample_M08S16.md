# pcmReadSample_M08S16

- ea: `0x1800122f0`
- end: `0x18001232b`
- name: `pcmReadSample_M08S16`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x1800122f0`

## pseudocode

```c
__int16 *__fastcall pcmReadSample_M08S16(__int16 *a1, char *a2)
{
  int v2; // r9d
  char v3; // r9

  v2 = *a1 + (__int16)HIWORD(*(_DWORD *)a1);
  if ( v2 <= 0x7FFF )
  {
    if ( v2 >= -32768 )
      v3 = BYTE1(v2) ^ 0x80;
    else
      v3 = 0;
  }
  else
  {
    v3 = -1;
  }
  *a2 = v3;
  return a1 + 2;
}

```

## disassembly

```asm
0x1800122f0  mov     eax, [rcx]
0x1800122f2  shr     eax, 10h
0x1800122f5  movsx   r9d, ax
0x1800122f9  movsx   eax, word ptr [rcx]
0x1800122fc  add     r9d, eax
0x1800122ff  cmp     r9d, 7FFFh
0x180012306  jle     short loc_18001230D
0x180012308  mov     r9b, 0FFh
0x18001230b  jmp     short loc_180012323
0x18001230d  cmp     r9d, 0FFFF8000h
0x180012314  jge     short loc_18001231B
0x180012316  xor     r9b, r9b
0x180012319  jmp     short loc_180012323
0x18001231b  sar     r9d, 8
0x18001231f  xor     r9b, 80h
0x180012323  mov     [rdx], r9b
0x180012326  lea     rax, [rcx+4]
0x18001232a  retn
```
