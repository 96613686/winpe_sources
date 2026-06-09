# GatherAdjacentFreeDataNodes

- ea: `0x180001768`
- end: `0x180001805`
- name: `GatherAdjacentFreeDataNodes`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001fa4`
- `0x180002150`

## callees

- `0x180001768`

## pseudocode

```c
__int64 __fastcall GatherAdjacentFreeDataNodes(__int64 a1, _DWORD *a2, int a3, unsigned int a4)
{
  unsigned int i; // eax
  _DWORD *v6; // rdi
  int v7; // r10d
  _DWORD *v8; // r8
  __int64 result; // rax

  for ( i = a2[2] - a3; i < a4; i = a2[2] - a3 )
  {
    v6 = *(_DWORD **)(a1 + 104);
    v7 = 0;
    v8 = v6;
    if ( !*(_DWORD *)(a1 + 128) )
      break;
    while ( v8[1] != -1 || !v8[2] || (*v8 & 0x7FFFFFFF) != a2[2] + (*a2 & 0x7FFFFFFF) )
    {
      v8 += 4;
      if ( (unsigned int)++v7 >= *(_DWORD *)(a1 + 128) )
        goto LABEL_11;
    }
    if ( v7 == -1 )
      break;
    a2[2] += v6[4 * v7 + 2];
    v6[4 * v7 + 2] = 0;
  }
LABEL_11:
  result = (unsigned int)(a2[2] - a3);
  if ( a4 < (unsigned int)result )
    return a4;
  return result;
}

```

## disassembly

```asm
0x180001768  mov     [rsp+arg_0], rsi
0x18000176d  mov     [rsp+arg_8], rdi
0x180001772  mov     eax, [rdx+8]
0x180001775  mov     r11d, r8d
0x180001778  sub     eax, r8d
0x18000177b  mov     rsi, rcx
0x18000177e  jmp     short loc_1800017E8
0x180001780  mov     rdi, [rsi+68h]
0x180001784  xor     r10d, r10d
0x180001787  mov     r8, rdi
0x18000178a  cmp     [rsi+80h], r10d
0x180001791  jbe     short loc_1800017ED
0x180001793  cmp     dword ptr [r8+4], 0FFFFFFFFh
0x180001798  jnz     short loc_1800017B5
0x18000179a  cmp     dword ptr [r8+8], 0
0x18000179f  jz      short loc_1800017B5
0x1800017a1  mov     ecx, [rdx]
0x1800017a3  mov     eax, [r8]
0x1800017a6  btr     ecx, 1Fh
0x1800017aa  add     ecx, [rdx+8]
0x1800017ad  btr     eax, 1Fh
0x1800017b1  cmp     eax, ecx
0x1800017b3  jz      short loc_1800017C7
0x1800017b5  add     r8, 10h
0x1800017b9  inc     r10d
0x1800017bc  cmp     r10d, [rsi+80h]
0x1800017c3  jb      short loc_180001793
0x1800017c5  jmp     short loc_1800017ED
0x1800017c7  cmp     r10d, 0FFFFFFFFh
0x1800017cb  jz      short loc_1800017ED
0x1800017cd  mov     ecx, r10d
0x1800017d0  add     rcx, rcx
0x1800017d3  mov     eax, [rdi+rcx*8+8]
0x1800017d7  add     [rdx+8], eax
0x1800017da  mov     dword ptr [rdi+rcx*8+8], 0
0x1800017e2  mov     eax, [rdx+8]
0x1800017e5  sub     eax, r11d
0x1800017e8  cmp     eax, r9d
0x1800017eb  jb      short loc_180001780
0x1800017ed  mov     eax, [rdx+8]
0x1800017f0  mov     rsi, [rsp+arg_0]
0x1800017f5  sub     eax, r11d
0x1800017f8  mov     rdi, [rsp+arg_8]
0x1800017fd  cmp     r9d, eax
0x180001800  cmovb   eax, r9d
0x180001804  retn
```
