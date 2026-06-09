# CDLocateCheckSum

- ea: `0x1800030d0`
- end: `0x180003100`
- name: `CDLocateCheckSum`
- size: `48`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005934`
- `0x180006f00`
- `0x180007384`
- `0x180007990`

## callees

- `0x1800030d0`

## pseudocode

```c
__int64 __fastcall CDLocateCheckSum(int a1, __int64 **a2)
{
  int v2; // eax
  __int64 *v4; // rcx

  v2 = cCheckSums;
  while ( v2 )
  {
    v4 = &CheckSumFns[8 * (unsigned __int64)(unsigned int)--v2];
    if ( *(_DWORD *)v4 == a1 )
    {
      *a2 = v4;
      return 0;
    }
  }
  return 2148008770LL;
}

```

## disassembly

```asm
0x1800030d0  mov     eax, cs:cCheckSums
0x1800030d6  lea     r10, CheckSumFns
0x1800030dd  mov     r9d, ecx
0x1800030e0  test    eax, eax
0x1800030e2  jz      short loc_1800030FA
0x1800030e4  dec     eax
0x1800030e6  mov     ecx, eax
0x1800030e8  shl     rcx, 6
0x1800030ec  add     rcx, r10
0x1800030ef  cmp     [rcx], r9d
0x1800030f2  jnz     short loc_1800030E0
0x1800030f4  mov     [rdx], rcx
0x1800030f7  xor     eax, eax
0x1800030f9  retn
0x1800030fa  mov     eax, 80080342h
0x1800030ff  retn
```
