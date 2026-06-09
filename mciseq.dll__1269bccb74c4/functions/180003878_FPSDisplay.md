# FPSDisplay

- ea: `0x180003878`
- end: `0x1800038a4`
- name: `FPSDisplay`
- size: `44`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003520`
- `0x1800036e0`
- `0x1800038ac`

## callees

- `0x180003878`

## pseudocode

```c
__int64 __fastcall FPSDisplay(int a1)
{
  int v1; // ecx
  int v2; // ecx

  v1 = a1 - 4;
  if ( !v1 )
    return 24;
  v2 = v1 - 1;
  if ( !v2 )
    return 25;
  if ( (unsigned int)(v2 - 1) < 2 )
    return 30;
  return 1;
}

```

## disassembly

```asm
0x180003878  sub     ecx, 4
0x18000387b  jz      short loc_18000389E
0x18000387d  sub     ecx, 1
0x180003880  jz      short loc_180003898
0x180003882  sub     ecx, 1
0x180003885  jz      short loc_180003892
0x180003887  cmp     ecx, 1
0x18000388a  jz      short loc_180003892
0x18000388c  mov     eax, 1
0x180003891  retn
0x180003892  mov     eax, 1Eh
0x180003897  retn
0x180003898  mov     eax, 19h
0x18000389d  retn
0x18000389e  mov     eax, 18h
0x1800038a3  retn
```
