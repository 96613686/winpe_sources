# pcmReadSample_M16S08

- ea: `0x180012360`
- end: `0x1800123a1`
- name: `pcmReadSample_M16S08`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`

## callees

- `0x180012360`

## pseudocode

```c
_WORD *__fastcall pcmReadSample_M16S08(_WORD *a1, __int16 *a2)
{
  signed int v2; // r9d
  __int16 v3; // ax

  v2 = (__int16)((*a1 ^ 0x8080) << 8) + ((__int16)(*a1 ^ 0x8080) & 0xFFFFFF00);
  v3 = 0x7FFF;
  if ( v2 <= 0x7FFF )
  {
    if ( v2 >= -32768 )
      v3 = ((*a1 ^ 0x8080) << 8) + ((*a1 ^ 0x8080) & 0xFF00);
    else
      v3 = 0x8000;
  }
  *a2 = v3;
  return a1 + 1;
}

```

## disassembly

```asm
0x180012360  mov     eax, 8080h
0x180012365  xor     ax, [rcx]
0x180012368  movsx   r9d, ax
0x18001236c  shl     ax, 8
0x180012370  and     r9d, 0FFFFFF00h
0x180012377  cwde
0x180012378  add     r9d, eax
0x18001237b  mov     eax, 7FFFh
0x180012380  cmp     r9d, eax
0x180012383  jg      short loc_180012399
0x180012385  cmp     r9d, 0FFFF8000h
0x18001238c  jge     short loc_180012395
0x18001238e  mov     eax, 8000h
0x180012393  jmp     short loc_180012399
0x180012395  movzx   eax, r9w
0x180012399  mov     [rdx], ax
0x18001239c  lea     rax, [rcx+2]
0x1800123a0  retn
```
