# adpcmIsMagicFormat

- ea: `0x1800028b8`
- end: `0x180002909`
- name: `adpcmIsMagicFormat`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fe4`
- `0x1800021b8`
- `0x1800025a0`

## callees

- `0x1800028b8`

## pseudocode

```c
__int64 __fastcall adpcmIsMagicFormat(__int64 a1)
{
  __int64 v1; // r8
  __int64 result; // rax

  if ( *(_WORD *)(a1 + 16) >= 0x20u && *(_WORD *)(a1 + 20) == 7 )
  {
    v1 = 0;
    result = 1;
    while ( *(__int16 *)(a1 + 4 * v1 + 22) == gaiCoef1[v1] && *(__int16 *)(a1 + 4 * v1 + 24) == gaiCoef2[v1] )
    {
      v1 = (unsigned int)(v1 + 1);
      if ( (unsigned int)v1 >= 7 )
        return result;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800028b8  cmp     word ptr [rcx+10h], 20h ; ' '
0x1800028bd  mov     rdx, rcx
0x1800028c0  jb      short loc_180002906
0x1800028c2  mov     r10d, 7
0x1800028c8  cmp     [rcx+14h], r10w
0x1800028cd  jnz     short loc_180002906
0x1800028cf  xor     r8d, r8d
0x1800028d2  lea     r11, cs:180000000h
0x1800028d9  lea     eax, [r10-6]
0x1800028dd  movsx   ecx, word ptr [rdx+r8*4+16h]
0x1800028e3  cmp     ecx, ds:rva gaiCoef1[r11+r8*4]
0x1800028eb  jnz     short loc_180002906
0x1800028ed  movsx   ecx, word ptr [rdx+r8*4+18h]
0x1800028f3  cmp     ecx, ds:rva gaiCoef2[r11+r8*4]
0x1800028fb  jnz     short loc_180002906
0x1800028fd  add     r8d, eax
0x180002900  cmp     r8d, r10d
0x180002903  jb      short loc_1800028DD
0x180002905  retn
0x180002906  xor     eax, eax
0x180002908  retn
```
