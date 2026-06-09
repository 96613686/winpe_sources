# l3audioIsValidFormat

- ea: `0x180003588`
- end: `0x1800035e0`
- name: `l3audioIsValidFormat`
- size: `88`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002da4`
- `0x180002f10`
- `0x180003218`

## callees

- `0x180003588`

## pseudocode

```c
_BOOL8 __fastcall l3audioIsValidFormat(__int64 a1)
{
  return a1
      && *(_WORD *)a1 == 85
      && (unsigned __int16)(*(_WORD *)(a1 + 2) - 1) <= 1u
      && *(_WORD *)(a1 + 16) == 12
      && !*(_WORD *)(a1 + 14)
      && (unsigned __int16)(*(_WORD *)(a1 + 18) - 1) <= 1u
      && (*(_BYTE *)(a1 + 20) & 3) != 3;
}

```

## disassembly

```asm
0x180003588  mov     rdx, rcx
0x18000358b  test    rcx, rcx
0x18000358e  jz      short loc_1800035DD
0x180003590  mov     eax, 55h ; 'U'
0x180003595  cmp     ax, [rcx]
0x180003598  jnz     short loc_1800035DD
0x18000359a  movzx   eax, word ptr [rcx+2]
0x18000359e  mov     r8d, 1
0x1800035a4  sub     ax, r8w
0x1800035a8  cmp     ax, r8w
0x1800035ac  ja      short loc_1800035DD
0x1800035ae  lea     eax, [r8+0Bh]
0x1800035b2  cmp     ax, [rcx+10h]
0x1800035b6  jnz     short loc_1800035DD
0x1800035b8  xor     ecx, ecx
0x1800035ba  cmp     cx, [rdx+0Eh]
0x1800035be  jnz     short loc_1800035DD
0x1800035c0  movzx   ecx, word ptr [rdx+12h]
0x1800035c4  sub     cx, r8w
0x1800035c8  cmp     cx, r8w
0x1800035cc  ja      short loc_1800035DD
0x1800035ce  mov     cl, [rdx+14h]
0x1800035d1  and     cl, 3
0x1800035d4  cmp     cl, 2
0x1800035d7  ja      short loc_1800035DD
0x1800035d9  mov     eax, r8d
0x1800035dc  retn
0x1800035dd  xor     eax, eax
0x1800035df  retn
```
