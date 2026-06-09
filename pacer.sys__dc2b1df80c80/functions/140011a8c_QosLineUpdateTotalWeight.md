# QosLineUpdateTotalWeight

- ea: `0x140011a8c`
- end: `0x140011adf`
- name: `QosLineUpdateTotalWeight`
- size: `83`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001d40`
- `0x140001fec`
- `0x1400020f0`
- `0x140003ab0`

## callees

- `0x140011a8c`

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
0x140011a8c  add     [rcx+6Ch], edx
0x140011a8f  mov     r10, rcx
0x140011a92  mov     eax, [rcx+68h]
0x140011a95  mov     edx, 0FFFFFFFFh
0x140011a9a  mov     r11d, [rcx+6Ch]
0x140011a9e  movsxd  r8, r8d
0x140011aa1  add     r8, rax
0x140011aa4  mov     eax, [rcx+70h]
0x140011aa7  cmp     r8, rdx
0x140011aaa  cmovge  r8, rdx
0x140011aae  mov     [rcx+68h], r8d
0x140011ab2  cmp     eax, r9d
0x140011ab5  jz      short loc_140011ABD
0x140011ab7  cmp     eax, [rsp+arg_20]
0x140011abb  ja      short loc_140011AC1
0x140011abd  mov     eax, [rsp+arg_20]
0x140011ac1  mov     [rcx+70h], eax
0x140011ac4  mov     ecx, [rcx+0CCh]
0x140011aca  imul    rcx, r11
0x140011ace  add     rcx, rcx
0x140011ad1  cmp     rcx, rdx
0x140011ad4  cmovnb  rcx, rdx
0x140011ad8  xor     eax, eax
0x140011ada  mov     [r10+7Ch], ecx
0x140011ade  retn
```
