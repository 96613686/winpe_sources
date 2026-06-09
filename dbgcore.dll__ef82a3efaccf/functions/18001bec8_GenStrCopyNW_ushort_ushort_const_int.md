# GenStrCopyNW(ushort *,ushort const *,int)

- ea: `0x18001bec8`
- end: `0x18001bf0a`
- name: `?GenStrCopyNW@@YAPEAGPEAGPEBGH@Z`
- size: `66`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180011e08`
- `0x1800132b0`
- `0x180014ed0`
- `0x180016d9c`
- `0x180017b8c`
- `0x18001ad48`
- `0x180023560`
- `0x180024770`
- `0x180024940`

## callees

- `0x18001bec8`

## pseudocode

```c
unsigned __int16 *__fastcall GenStrCopyNW(unsigned __int16 *a1, unsigned __int16 *a2, int a3)
{
  unsigned __int16 *v3; // rax
  unsigned __int16 v4; // r9
  unsigned __int16 *v5; // r10

  v3 = a1;
  if ( a3 <= 0 )
    return 0;
  do
  {
    v4 = *a2;
    v5 = v3;
    *v3++ = *a2;
    if ( !v4 )
      break;
    ++a2;
    --a3;
  }
  while ( a3 > 0 );
  if ( v3 <= a1 )
    return 0;
  if ( v4 )
  {
    *v5 = 0;
    return 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001bec8  xor     r11d, r11d
0x18001becb  mov     rax, rcx
0x18001bece  test    r8d, r8d
0x18001bed1  jle     short loc_18001BF03
0x18001bed3  movzx   r9d, word ptr [rdx]
0x18001bed7  mov     r10, rax
0x18001beda  mov     [rax], r9w
0x18001bede  add     rax, 2
0x18001bee2  test    r9w, r9w
0x18001bee6  jz      short loc_18001BEF4
0x18001bee8  add     rdx, 2
0x18001beec  dec     r8d
0x18001beef  test    r8d, r8d
0x18001bef2  jg      short loc_18001BED3
0x18001bef4  cmp     rax, rcx
0x18001bef7  jbe     short loc_18001BF03
0x18001bef9  test    r9w, r9w
0x18001befd  jz      short loc_18001BF06
0x18001beff  mov     [r10], r11w
0x18001bf03  xor     eax, eax
0x18001bf05  retn
0x18001bf06  mov     rax, rcx
0x18001bf09  retn
```
