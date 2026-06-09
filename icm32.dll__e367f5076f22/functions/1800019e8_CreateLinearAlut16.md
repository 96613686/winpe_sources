# CreateLinearAlut16

- ea: `0x1800019e8`
- end: `0x180001a1a`
- name: `CreateLinearAlut16`
- size: `50`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a4`
- `0x18000464c`
- `0x18001bb30`
- `0x180020984`

## callees

- `0x1800019e8`

## pseudocode

```c
void __fastcall CreateLinearAlut16(__int64 a1)
{
  __int64 v1; // r8
  int v2; // edx

  v1 = 0;
  do
  {
    v2 = (262396 * (int)v1 + 2047) >> 12;
    if ( v2 > 0xFFFF )
      LOWORD(v2) = -1;
    *(_WORD *)(a1 + 2 * v1) = v2;
    v1 = (unsigned int)(v1 + 1);
  }
  while ( (int)v1 < 1024 );
}

```

## disassembly

```asm
0x1800019e8  xor     r8d, r8d
0x1800019eb  mov     r9d, 0FFFFh
0x1800019f1  imul    edx, r8d, 400FCh
0x1800019f8  add     edx, 7FFh
0x1800019fe  sar     edx, 0Ch
0x180001a01  cmp     edx, r9d
0x180001a04  cmovg   edx, r9d
0x180001a08  mov     [rcx+r8*2], dx
0x180001a0d  inc     r8d
0x180001a10  cmp     r8d, 400h
0x180001a17  jl      short loc_1800019F1
0x180001a19  retn
```
