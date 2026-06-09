# QosLineUpdateTotalWeight

- ea: `0x140014328`
- end: `0x14001437b`
- name: `QosLineUpdateTotalWeight`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400141c0`

## callees

- `0x140014328`

## pseudocode

```c
__int64 __fastcall QosLineUpdateTotalWeight(unsigned int *a1, int a2, int a3, int a4, unsigned int a5)
{
  __int64 v6; // r11
  __int64 v7; // r8
  unsigned int v8; // eax
  unsigned __int64 v9; // rcx
  __int64 result; // rax

  a1[27] += a2;
  v6 = a1[27];
  v7 = a1[26] + (__int64)a3;
  v8 = a1[28];
  if ( v7 >= 0xFFFFFFFFLL )
    LODWORD(v7) = -1;
  a1[26] = v7;
  if ( v8 == a4 || v8 <= a5 )
    v8 = a5;
  a1[28] = v8;
  v9 = 2 * v6 * a1[51];
  if ( v9 >= 0xFFFFFFFF )
    LODWORD(v9) = -1;
  result = 0;
  a1[31] = v9;
  return result;
}

```

## disassembly

```asm
0x140014328  add     [rcx+6Ch], edx
0x14001432b  mov     r10, rcx
0x14001432e  mov     eax, [rcx+68h]
0x140014331  mov     edx, 0FFFFFFFFh
0x140014336  mov     r11d, [rcx+6Ch]
0x14001433a  movsxd  r8, r8d
0x14001433d  add     r8, rax
0x140014340  mov     eax, [rcx+70h]
0x140014343  cmp     r8, rdx
0x140014346  cmovge  r8, rdx
0x14001434a  mov     [rcx+68h], r8d
0x14001434e  cmp     eax, r9d
0x140014351  jz      short loc_140014359
0x140014353  cmp     eax, [rsp+arg_20]
0x140014357  ja      short loc_14001435D
0x140014359  mov     eax, [rsp+arg_20]
0x14001435d  mov     [rcx+70h], eax
0x140014360  mov     ecx, [rcx+0CCh]
0x140014366  imul    rcx, r11
0x14001436a  add     rcx, rcx
0x14001436d  cmp     rcx, rdx
0x140014370  cmovnb  rcx, rdx
0x140014374  xor     eax, eax
0x140014376  mov     [r10+7Ch], ecx
0x14001437a  retn
```
