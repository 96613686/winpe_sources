# CDLocateCheckSum

- ea: `0x1400261e0`
- end: `0x14002620f`
- name: `CDLocateCheckSum`
- size: `47`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e55c`
- `0x14000e66c`
- `0x14000f0a8`
- `0x14000f244`
- `0x140026f70`
- `0x1400276c0`
- `0x140029fe4`
- `0x14002a4d8`
- `0x14002ae10`
- `0x14002bc00`
- `0x14002ec90`

## callees

- `0x1400261e0`

## pseudocode

```c
__int64 __fastcall CDLocateCheckSum(int a1, _QWORD *a2)
{
  int v2; // eax
  _DWORD *v3; // r9

  v2 = cCheckSums;
  while ( v2 )
  {
    v3 = (_DWORD *)((char *)&CheckSumFns + 64 * (unsigned __int64)(unsigned int)--v2);
    if ( *v3 == a1 )
    {
      *a2 = v3;
      return 0;
    }
  }
  return 2148008770LL;
}

```

## disassembly

```asm
0x1400261e0  mov     eax, cs:cCheckSums
0x1400261e6  lea     r10, CheckSumFns
0x1400261ed  test    eax, eax
0x1400261ef  jz      short loc_140026209
0x1400261f1  dec     eax
0x1400261f3  mov     r9d, eax
0x1400261f6  shl     r9, 6
0x1400261fa  add     r9, r10
0x1400261fd  cmp     [r9], ecx
0x140026200  jnz     short loc_1400261ED
0x140026202  mov     [rdx], r9
0x140026205  xor     eax, eax
0x140026207  retn
0x140026209  mov     eax, 80080342h
0x14002620e  retn
```
