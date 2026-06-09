# SetBit

- ea: `0x180004de8`
- end: `0x180004e18`
- name: `SetBit`
- size: `48`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042b0`
- `0x180004b30`
- `0x180004ef0`
- `0x180005270`

## callees

- `0x180004de8`

## pseudocode

```c
void __fastcall SetBit(__int64 a1, unsigned int a2, int a3)
{
  __int64 v3; // r10
  int v4; // eax

  v3 = a2 >> 4;
  if ( (unsigned int)v3 < 8 )
  {
    v4 = 1 << (a2 & 0xF);
    if ( a3 )
      *(_WORD *)(a1 + 2 * v3) |= v4;
    else
      *(_WORD *)(a1 + 2 * v3) &= ~(_WORD)v4;
  }
}

```

## disassembly

```asm
0x180004de8  mov     r10d, edx
0x180004deb  mov     r9, rcx
0x180004dee  shr     r10d, 4
0x180004df2  cmp     r10d, 8
0x180004df6  jnb     short locret_180004E17
0x180004df8  and     edx, 0Fh
0x180004dfb  mov     eax, 1
0x180004e00  mov     cl, dl
0x180004e02  shl     eax, cl
0x180004e04  test    r8d, r8d
0x180004e07  jz      short loc_180004E0F
0x180004e09  or      [r9+r10*2], ax
0x180004e0e  retn
0x180004e0f  not     ax
0x180004e12  and     [r9+r10*2], ax
0x180004e17  retn
```
