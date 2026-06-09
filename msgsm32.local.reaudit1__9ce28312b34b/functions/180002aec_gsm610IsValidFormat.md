# gsm610IsValidFormat

- ea: `0x180002aec`
- end: `0x180002b4e`
- name: `gsm610IsValidFormat`
- size: `98`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002488`
- `0x1800025bc`
- `0x180002834`

## callees

- `0x180002aec`

## pseudocode

```c
_BOOL8 __fastcall gsm610IsValidFormat(__int64 a1)
{
  return a1
      && *(_WORD *)a1 == 49
      && *(_WORD *)(a1 + 2) == 1
      && *(_WORD *)(a1 + 12) == 65
      && 65 * *(_DWORD *)(a1 + 4) / 0x140u == *(_DWORD *)(a1 + 8)
      && !*(_WORD *)(a1 + 14)
      && *(_WORD *)(a1 + 16) == 2
      && *(_WORD *)(a1 + 18) == 320;
}

```

## disassembly

```asm
0x180002aec  mov     r8, rcx
0x180002aef  test    rcx, rcx
0x180002af2  jz      short loc_180002B4B
0x180002af4  mov     eax, 31h ; '1'
0x180002af9  cmp     ax, [rcx]
0x180002afc  jnz     short loc_180002B4B
0x180002afe  lea     r9d, [rax-30h]
0x180002b02  cmp     [rcx+2], r9w
0x180002b07  jnz     short loc_180002B4B
0x180002b09  lea     eax, [r9+40h]
0x180002b0d  cmp     ax, [rcx+0Ch]
0x180002b11  jnz     short loc_180002B4B
0x180002b13  imul    ecx, [rcx+4], 41h ; 'A'
0x180002b17  mov     eax, 0CCCCCCCDh
0x180002b1c  mul     ecx
0x180002b1e  shr     edx, 8
0x180002b21  cmp     edx, [r8+8]
0x180002b25  jnz     short loc_180002B4B
0x180002b27  xor     ecx, ecx
0x180002b29  cmp     cx, [r8+0Eh]
0x180002b2e  jnz     short loc_180002B4B
0x180002b30  lea     ecx, [r9+1]
0x180002b34  cmp     cx, [r8+10h]
0x180002b39  jnz     short loc_180002B4B
0x180002b3b  mov     ecx, 140h
0x180002b40  cmp     cx, [r8+12h]
0x180002b45  jnz     short loc_180002B4B
0x180002b47  mov     eax, r9d
0x180002b4a  retn
0x180002b4b  xor     eax, eax
0x180002b4d  retn
```
