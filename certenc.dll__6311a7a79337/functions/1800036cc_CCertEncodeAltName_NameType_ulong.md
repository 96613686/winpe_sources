# CCertEncodeAltName::_NameType(ulong)

- ea: `0x1800036cc`
- end: `0x180003707`
- name: `?_NameType@CCertEncodeAltName@@AEAA?AW4_enumNameType@1@K@Z`
- size: `59`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002d00`
- `0x180002f20`
- `0x1800030b0`
- `0x1800032e0`
- `0x1800035e0`

## callees

- `0x1800036cc`

## pseudocode

```c
__int64 __fastcall CCertEncodeAltName::_NameType(__int64 a1, int a2)
{
  __int64 result; // rax
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx

  result = 0;
  v3 = a2 - 1;
  if ( !v3 )
    return 4;
  v4 = v3 - 1;
  if ( !v4 )
    return 1;
  v5 = v4 - 1;
  if ( !v5 )
    return 1;
  v6 = v5 - 2;
  if ( !v6 )
    return 3;
  v7 = v6 - 2;
  if ( !v7 )
    return 1;
  v8 = v7 - 1;
  if ( !v8 )
    return 3;
  if ( v8 == 1 )
    return 2;
  return result;
}

```

## disassembly

```asm
0x1800036cc  xor     eax, eax
0x1800036ce  sub     edx, 1
0x1800036d1  jz      short loc_180003701
0x1800036d3  sub     edx, 1
0x1800036d6  jz      short loc_1800036FB
0x1800036d8  sub     edx, 1
0x1800036db  jz      short loc_1800036FB
0x1800036dd  sub     edx, 2
0x1800036e0  jz      short loc_1800036F5
0x1800036e2  sub     edx, 2
0x1800036e5  jz      short loc_1800036FB
0x1800036e7  sub     edx, 1
0x1800036ea  jz      short loc_1800036F5
0x1800036ec  cmp     edx, 1
0x1800036ef  jnz     short locret_180003706
0x1800036f1  lea     eax, [rdx+1]
0x1800036f4  retn
0x1800036f5  mov     eax, 3
0x1800036fa  retn
0x1800036fb  mov     eax, 1
0x180003700  retn
0x180003701  mov     eax, 4
0x180003706  retn
```
