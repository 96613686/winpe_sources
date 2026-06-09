# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000b0b8`
- end: `0x14000b22f`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140009328`

## callees

- `0x14000af0c`
- `0x14000afdc`
- `0x14000b0b8`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r11d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 v13; // edx
  int v14; // r9d
  signed __int32 v15; // r11d
  signed __int32 v16; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_35;
    case 1:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a3, (_DWORD *)a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3, a3, (_DWORD *)a1);
      return a1;
    case 5:
      goto LABEL_34;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v5 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
      goto LABEL_16;
    v6 = *((_DWORD *)a2 + 1);
    do
    {
      v7 = (v6 & 0x10) != 0 && ((v6 >> 5) & 0x3F) == v5;
      *(_DWORD *)(a1 + 16) = v7;
      v8 = v6;
      v6 = _InterlockedCompareExchange(
             a2 + 1,
             v6 ^ ((unsigned __int16)v6 ^ (unsigned __int16)(32 * v5)) & 0x7E0 | 0x10,
             v6);
    }
    while ( v8 != v6 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = 0;
    }
    return a1;
  }
LABEL_17:
  v9 = 0;
  v10 = a3 - 2;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 3;
      if ( v12 )
      {
        if ( v12 == 1 )
          v9 = 16;
      }
      else
      {
        v9 = 4;
      }
    }
    else
    {
      v9 = 8;
    }
  }
  else
  {
    v9 = 2;
  }
  v13 = *a2;
  v14 = 1;
  while ( 1 )
  {
    v15 = v13 | v9 | 1;
    *(_DWORD *)(a1 + 16) = (v13 | v9) == v13;
    if ( (v13 | v9) == v13 )
      v15 = v13 | v9;
    v16 = _InterlockedCompareExchange(a2, v15, v13);
    if ( v13 == v16 )
      break;
    v13 = v16;
  }
  if ( (v15 & 1) == 0 || (v13 & 1) != 0 )
    v14 = 0;
  *(_DWORD *)a1 = v14;
  return a1;
}

```

## disassembly

```asm
0x14000b0b8  mov     [rsp+arg_0], rbx
0x14000b0bd  push    rdi
0x14000b0be  sub     rsp, 20h
0x14000b0c2  xor     eax, eax
0x14000b0c4  xorps   xmm0, xmm0
0x14000b0c7  mov     r10, rdx
0x14000b0ca  mov     rbx, rcx
0x14000b0cd  mov     r9d, r8d
0x14000b0d0  movups  xmmword ptr [rcx], xmm0
0x14000b0d3  mov     [rcx+10h], rax
0x14000b0d7  test    r8d, r8d
0x14000b0da  jz      loc_14000B213
0x14000b0e0  sub     r9d, 1
0x14000b0e4  jz      loc_14000B203
0x14000b0ea  sub     r9d, 1
0x14000b0ee  jz      loc_14000B18B
0x14000b0f4  sub     r9d, 1
0x14000b0f8  jz      loc_14000B18B
0x14000b0fe  sub     r9d, 1
0x14000b102  jz      loc_14000B213
0x14000b108  sub     r9d, 1
0x14000b10c  jz      loc_14000B203
0x14000b112  sub     r9d, 1
0x14000b116  jz      short loc_14000B18B
0x14000b118  cmp     r9d, 1
0x14000b11c  jz      short loc_14000B18B
0x14000b11e  lea     r11d, [r8-140h]
0x14000b125  lea     r9d, [rax+1]
0x14000b129  cmp     r11d, 40h ; '@'
0x14000b12d  jge     short loc_14000B177
0x14000b12f  mov     eax, [rdx+4]
0x14000b132  lea     ecx, [r9+0Fh]
0x14000b136  mov     edi, r11d
0x14000b139  shl     edi, 5
0x14000b13c  test    cl, al
0x14000b13e  jz      short loc_14000B152
0x14000b140  mov     edx, eax
0x14000b142  shr     edx, 5
0x14000b145  and     edx, 3Fh
0x14000b148  cmp     edx, r11d
0x14000b14b  jnz     short loc_14000B152
0x14000b14d  mov     edx, r9d
0x14000b150  jmp     short loc_14000B154
0x14000b152  xor     edx, edx
0x14000b154  mov     [rbx+10h], edx
0x14000b157  mov     edx, edi
0x14000b159  xor     edx, eax
0x14000b15b  and     edx, 7E0h
0x14000b161  xor     edx, eax
0x14000b163  or      edx, ecx
0x14000b165  lock cmpxchg [r10+4], edx
0x14000b16b  jnz     short loc_14000B13C
0x14000b16d  cmp     dword ptr [rbx+10h], 0
0x14000b171  jnz     loc_14000B221
0x14000b177  mov     [rbx+8], r8d
0x14000b17b  mov     [rbx+4], r9d
0x14000b17f  mov     dword ptr [rbx+0Ch], 0
0x14000b186  jmp     loc_14000B221
0x14000b18b  xor     ecx, ecx
0x14000b18d  sub     r8d, 2
0x14000b191  jz      short loc_14000B1B9
0x14000b193  sub     r8d, 1
0x14000b197  jz      short loc_14000B1B2
0x14000b199  sub     r8d, 3
0x14000b19d  jz      short loc_14000B1AB
0x14000b19f  cmp     r8d, 1
0x14000b1a3  jnz     short loc_14000B1BE
0x14000b1a5  lea     ecx, [r8+0Fh]
0x14000b1a9  jmp     short loc_14000B1BE
0x14000b1ab  mov     ecx, 4
0x14000b1b0  jmp     short loc_14000B1BE
0x14000b1b2  mov     ecx, 8
0x14000b1b7  jmp     short loc_14000B1BE
0x14000b1b9  mov     ecx, 2
0x14000b1be  mov     edx, [rdx]
0x14000b1c0  mov     r9d, 1
0x14000b1c6  xor     eax, eax
0x14000b1c8  mov     r8d, ecx
0x14000b1cb  or      r8d, edx
0x14000b1ce  cmp     r8d, edx
0x14000b1d1  mov     r11d, r8d
0x14000b1d4  setz    al
0x14000b1d7  or      r11d, r9d
0x14000b1da  cmp     r8d, edx
0x14000b1dd  mov     [rbx+10h], eax
0x14000b1e0  mov     eax, edx
0x14000b1e2  cmovz   r11d, r8d
0x14000b1e6  lock cmpxchg [r10], r11d
0x14000b1eb  jz      short loc_14000B1F1
0x14000b1ed  mov     edx, eax
0x14000b1ef  jmp     short loc_14000B1C6
0x14000b1f1  test    r9b, r11b
0x14000b1f4  jz      short loc_14000B1FB
0x14000b1f6  test    r9b, dl
0x14000b1f9  jz      short loc_14000B1FE
0x14000b1fb  xor     r9d, r9d
0x14000b1fe  mov     [rbx], r9d
0x14000b201  jmp     short loc_14000B221
0x14000b203  mov     r9, rbx
0x14000b206  mov     edx, r8d
0x14000b209  mov     rcx, r10
0x14000b20c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14000b211  jmp     short loc_14000B221
0x14000b213  mov     r9, rbx
0x14000b216  mov     edx, r8d
0x14000b219  mov     rcx, r10
0x14000b21c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14000b221  mov     rax, rbx
0x14000b224  mov     rbx, [rsp+28h+arg_0]
0x14000b229  add     rsp, 20h
0x14000b22d  pop     rdi
0x14000b22e  retn
```
