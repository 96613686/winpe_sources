# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800130f8`
- end: `0x18001326f`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011ccc`

## callees

- `0x180012f4c`
- `0x18001301c`
- `0x1800130f8`

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
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
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
0x1800130f8  mov     [rsp+arg_0], rbx
0x1800130fd  push    rdi
0x1800130fe  sub     rsp, 20h
0x180013102  xor     eax, eax
0x180013104  xorps   xmm0, xmm0
0x180013107  mov     r10, rdx
0x18001310a  mov     rbx, rcx
0x18001310d  mov     r9d, r8d
0x180013110  movups  xmmword ptr [rcx], xmm0
0x180013113  mov     [rcx+10h], rax
0x180013117  test    r8d, r8d
0x18001311a  jz      loc_180013253
0x180013120  sub     r9d, 1
0x180013124  jz      loc_180013243
0x18001312a  sub     r9d, 1
0x18001312e  jz      loc_1800131CB
0x180013134  sub     r9d, 1
0x180013138  jz      loc_1800131CB
0x18001313e  sub     r9d, 1
0x180013142  jz      loc_180013253
0x180013148  sub     r9d, 1
0x18001314c  jz      loc_180013243
0x180013152  sub     r9d, 1
0x180013156  jz      short loc_1800131CB
0x180013158  cmp     r9d, 1
0x18001315c  jz      short loc_1800131CB
0x18001315e  lea     r11d, [r8-140h]
0x180013165  lea     r9d, [rax+1]
0x180013169  cmp     r11d, 40h ; '@'
0x18001316d  jge     short loc_1800131B7
0x18001316f  mov     eax, [rdx+4]
0x180013172  lea     ecx, [r9+0Fh]
0x180013176  mov     edi, r11d
0x180013179  shl     edi, 5
0x18001317c  test    cl, al
0x18001317e  jz      short loc_180013192
0x180013180  mov     edx, eax
0x180013182  shr     edx, 5
0x180013185  and     edx, 3Fh
0x180013188  cmp     edx, r11d
0x18001318b  jnz     short loc_180013192
0x18001318d  mov     edx, r9d
0x180013190  jmp     short loc_180013194
0x180013192  xor     edx, edx
0x180013194  mov     [rbx+10h], edx
0x180013197  mov     edx, edi
0x180013199  xor     edx, eax
0x18001319b  and     edx, 7E0h
0x1800131a1  xor     edx, eax
0x1800131a3  or      edx, ecx
0x1800131a5  lock cmpxchg [r10+4], edx
0x1800131ab  jnz     short loc_18001317C
0x1800131ad  cmp     dword ptr [rbx+10h], 0
0x1800131b1  jnz     loc_180013261
0x1800131b7  mov     [rbx+8], r8d
0x1800131bb  mov     [rbx+4], r9d
0x1800131bf  mov     dword ptr [rbx+0Ch], 0
0x1800131c6  jmp     loc_180013261
0x1800131cb  xor     ecx, ecx
0x1800131cd  sub     r8d, 2
0x1800131d1  jz      short loc_1800131F9
0x1800131d3  sub     r8d, 1
0x1800131d7  jz      short loc_1800131F2
0x1800131d9  sub     r8d, 3
0x1800131dd  jz      short loc_1800131EB
0x1800131df  cmp     r8d, 1
0x1800131e3  jnz     short loc_1800131FE
0x1800131e5  lea     ecx, [r8+0Fh]
0x1800131e9  jmp     short loc_1800131FE
0x1800131eb  mov     ecx, 4
0x1800131f0  jmp     short loc_1800131FE
0x1800131f2  mov     ecx, 8
0x1800131f7  jmp     short loc_1800131FE
0x1800131f9  mov     ecx, 2
0x1800131fe  mov     edx, [rdx]
0x180013200  mov     r9d, 1
0x180013206  xor     eax, eax
0x180013208  mov     r8d, ecx
0x18001320b  or      r8d, edx
0x18001320e  cmp     r8d, edx
0x180013211  mov     r11d, r8d
0x180013214  setz    al
0x180013217  or      r11d, r9d
0x18001321a  cmp     r8d, edx
0x18001321d  mov     [rbx+10h], eax
0x180013220  mov     eax, edx
0x180013222  cmovz   r11d, r8d
0x180013226  lock cmpxchg [r10], r11d
0x18001322b  jz      short loc_180013231
0x18001322d  mov     edx, eax
0x18001322f  jmp     short loc_180013206
0x180013231  test    r9b, r11b
0x180013234  jz      short loc_18001323B
0x180013236  test    r9b, dl
0x180013239  jz      short loc_18001323E
0x18001323b  xor     r9d, r9d
0x18001323e  mov     [rbx], r9d
0x180013241  jmp     short loc_180013261
0x180013243  mov     r9, rbx
0x180013246  mov     edx, r8d
0x180013249  mov     rcx, r10
0x18001324c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180013251  jmp     short loc_180013261
0x180013253  mov     r9, rbx
0x180013256  mov     edx, r8d
0x180013259  mov     rcx, r10
0x18001325c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180013261  mov     rax, rbx
0x180013264  mov     rbx, [rsp+28h+arg_0]
0x180013269  add     rsp, 20h
0x18001326d  pop     rdi
0x18001326e  retn
```
