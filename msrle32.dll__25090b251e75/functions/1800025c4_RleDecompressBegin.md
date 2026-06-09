# RleDecompressBegin

- ea: `0x1800025c4`
- end: `0x180002678`
- name: `RleDecompressBegin`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cd0`

## callees

- `0x1800025c4`
- `0x180002780`

## pseudocode

```c
__int64 __fastcall RleDecompressBegin(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  unsigned __int64 v6; // rcx
  unsigned int v7; // eax
  bool v8; // zf
  unsigned int v9; // ecx
  __int64 v10; // rdx
  unsigned __int64 v11; // rdx

  result = RleDecompressQuery(a1, a2, a3);
  if ( !(_DWORD)result )
  {
    if ( a1 )
    {
      *(_DWORD *)(a1 + 48) = 1;
      if ( *(_DWORD *)(a3 + 8) == 0x80000000 )
        return 4294967289LL;
      if ( *(int *)(a3 + 4) < 0 )
        return 4294967289LL;
      if ( !*(_WORD *)(a3 + 14) )
        return 4294967289LL;
      v6 = *(unsigned int *)(a3 + 4) * (unsigned __int64)*(unsigned __int16 *)(a3 + 14);
      if ( v6 > 0xFFFFFFFF )
        return 4294967289LL;
      v7 = (unsigned int)v6 >> 3;
      v8 = (v6 & 7) == 0;
      v9 = ((unsigned int)v6 >> 3) + 1;
      if ( v8 )
        v9 = v7;
      if ( (v9 & 3) != 0 )
        v9 = v9 - (v9 & 3) + 4;
      v10 = (unsigned int)-*(_DWORD *)(a3 + 8);
      if ( *(int *)(a3 + 8) > 0 )
        v10 = *(unsigned int *)(a3 + 8);
      v11 = v9 * v10;
      if ( v11 > 0xFFFFFFFF )
      {
        return 4294967289LL;
      }
      else if ( *(_DWORD *)(a3 + 20) )
      {
        return *(_DWORD *)(a3 + 20) < (unsigned int)v11 ? 0xFFFFFFF9 : 0;
      }
      else
      {
        *(_DWORD *)(a3 + 20) = v11;
        return 0;
      }
    }
    else
    {
      return 4294967288LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800025c4  mov     [rsp+arg_0], rbx
0x1800025c9  push    rdi
0x1800025ca  sub     rsp, 20h
0x1800025ce  mov     rbx, r8
0x1800025d1  mov     rdi, rcx
0x1800025d4  call    RleDecompressQuery
0x1800025d9  xor     r8d, r8d
0x1800025dc  test    eax, eax
0x1800025de  jnz     loc_18000266D
0x1800025e4  test    rdi, rdi
0x1800025e7  jnz     short loc_1800025F0
0x1800025e9  mov     eax, 0FFFFFFF8h
0x1800025ee  jmp     short loc_18000266D
0x1800025f0  mov     dword ptr [rdi+30h], 1
0x1800025f7  cmp     dword ptr [rbx+8], 80000000h
0x1800025fe  jz      short loc_180002668
0x180002600  cmp     [rbx+4], r8d
0x180002604  jl      short loc_180002668
0x180002606  cmp     [rbx+0Eh], r8w
0x18000260b  jbe     short loc_180002668
0x18000260d  movzx   ecx, word ptr [rbx+0Eh]
0x180002611  mov     r9d, 0FFFFFFFFh
0x180002617  mov     eax, [rbx+4]
0x18000261a  imul    rcx, rax
0x18000261e  cmp     rcx, r9
0x180002621  ja      short loc_180002668
0x180002623  mov     eax, ecx
0x180002625  shr     eax, 3
0x180002628  test    cl, 7
0x18000262b  lea     ecx, [rax+1]
0x18000262e  cmovz   ecx, eax
0x180002631  mov     eax, ecx
0x180002633  and     eax, 3
0x180002636  jz      short loc_18000263D
0x180002638  sub     ecx, eax
0x18000263a  add     ecx, 4
0x18000263d  mov     edx, [rbx+8]
0x180002640  neg     edx
0x180002642  mov     eax, ecx
0x180002644  cmovs   edx, [rbx+8]
0x180002648  imul    rdx, rax
0x18000264c  cmp     rdx, r9
0x18000264f  ja      short loc_180002668
0x180002651  cmp     [rbx+14h], r8d
0x180002655  jnz     short loc_18000265E
0x180002657  mov     [rbx+14h], edx
0x18000265a  xor     eax, eax
0x18000265c  jmp     short loc_18000266D
0x18000265e  cmp     [rbx+14h], edx
0x180002661  sbb     eax, eax
0x180002663  and     eax, 0FFFFFFF9h
0x180002666  jmp     short loc_18000266D
0x180002668  mov     eax, 0FFFFFFF9h
0x18000266d  mov     rbx, [rsp+28h+arg_0]
0x180002672  add     rsp, 20h
0x180002676  pop     rdi
0x180002677  retn
```
