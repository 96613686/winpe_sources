# pcmReadSample_M16S16

- ea: `0x180006e90`
- end: `0x180006ecc`
- name: `pcmReadSample_M16S16`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180006e90`

## pseudocode

```c
_DWORD *__fastcall pcmReadSample_M16S16(_DWORD *a1, __int16 *a2)
{
  int v2; // eax
  __int16 v3; // r8

  v2 = (__int16)HIWORD(*a1) + (__int16)*a1;
  v3 = 0x7FFF;
  if ( v2 <= 0x7FFF )
  {
    if ( v2 < -32768 )
      LOWORD(v2) = 0x8000;
    v3 = v2;
  }
  *a2 = v3;
  return a1 + 1;
}

```

## disassembly

```asm
0x180006e90  mov     r9d, [rcx]
0x180006e93  mov     eax, r9d
0x180006e96  shr     eax, 10h
0x180006e99  movsx   r8d, ax
0x180006e9d  movsx   eax, r9w
0x180006ea1  add     eax, r8d
0x180006ea4  mov     r8d, 7FFFh
0x180006eaa  cmp     eax, r8d
0x180006ead  jg      short loc_180006EC3
0x180006eaf  mov     r8d, 8000h
0x180006eb5  cmp     eax, 0FFFF8000h
0x180006eba  cmovl   ax, r8w
0x180006ebf  movzx   r8d, ax
0x180006ec3  mov     [rdx], r8w
0x180006ec7  lea     rax, [rcx+4]
0x180006ecb  retn
```
