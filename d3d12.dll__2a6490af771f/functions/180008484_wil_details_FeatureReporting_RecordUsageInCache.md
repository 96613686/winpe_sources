# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180008484`
- end: `0x1800085fa`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008374`

## callees

- `0x180008484`
- `0x180008600`
- `0x18000f44c`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r9d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 i; // edx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_31;
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
  for ( i = *a2; ; i = v15 )
  {
    v14 = i | v9 | 1;
    *(_DWORD *)(a1 + 16) = (i | v9) == i;
    if ( (i | v9) == i )
      v14 = i | v9;
    v15 = _InterlockedCompareExchange(a2, v14, i);
    if ( i == v15 )
      break;
  }
  *(_DWORD *)a1 = (v14 & 1) != 0 && (i & 1) == 0;
  return a1;
}

```

## disassembly

```asm
0x180008484  push    rbx
0x180008486  sub     rsp, 20h
0x18000848a  xor     eax, eax
0x18000848c  xorps   xmm0, xmm0
0x18000848f  mov     r10, rdx
0x180008492  mov     rbx, rcx
0x180008495  mov     r9d, r8d
0x180008498  movups  xmmword ptr [rcx], xmm0
0x18000849b  mov     [rcx+10h], rax
0x18000849f  test    r8d, r8d
0x1800084a2  jz      loc_1800085E3
0x1800084a8  sub     r9d, 1
0x1800084ac  jz      loc_1800085D3
0x1800084b2  sub     r9d, 1
0x1800084b6  jz      loc_180008557
0x1800084bc  sub     r9d, 1
0x1800084c0  jz      loc_180008557
0x1800084c6  sub     r9d, 1
0x1800084ca  jz      loc_1800085E3
0x1800084d0  sub     r9d, 1
0x1800084d4  jz      loc_1800085D3
0x1800084da  sub     r9d, 1
0x1800084de  jz      short loc_180008557
0x1800084e0  cmp     r9d, 1
0x1800084e4  jz      short loc_180008557
0x1800084e6  lea     r9d, [r8-140h]
0x1800084ed  cmp     r9d, 40h ; '@'
0x1800084f1  jge     short loc_180008540
0x1800084f3  mov     eax, [rdx+4]
0x1800084f6  mov     r11d, r9d
0x1800084f9  shl     r11d, 5
0x1800084fd  mov     ecx, 10h
0x180008502  test    cl, al
0x180008504  jz      short loc_18000851A
0x180008506  mov     edx, eax
0x180008508  shr     edx, 5
0x18000850b  and     edx, 3Fh
0x18000850e  cmp     edx, r9d
0x180008511  jnz     short loc_18000851A
0x180008513  mov     edx, 1
0x180008518  jmp     short loc_18000851C
0x18000851a  xor     edx, edx
0x18000851c  mov     [rbx+10h], edx
0x18000851f  mov     edx, r11d
0x180008522  xor     edx, eax
0x180008524  and     edx, 7E0h
0x18000852a  xor     edx, eax
0x18000852c  or      edx, ecx
0x18000852e  lock cmpxchg [r10+4], edx
0x180008534  jnz     short loc_180008502
0x180008536  cmp     dword ptr [rbx+10h], 0
0x18000853a  jnz     loc_1800085F1
0x180008540  mov     [rbx+8], r8d
0x180008544  mov     dword ptr [rbx+4], 1
0x18000854b  mov     dword ptr [rbx+0Ch], 0
0x180008552  jmp     loc_1800085F1
0x180008557  xor     ecx, ecx
0x180008559  sub     r8d, 2
0x18000855d  jz      short loc_180008585
0x18000855f  sub     r8d, 1
0x180008563  jz      short loc_18000857E
0x180008565  sub     r8d, 3
0x180008569  jz      short loc_180008577
0x18000856b  cmp     r8d, 1
0x18000856f  jnz     short loc_18000858A
0x180008571  lea     ecx, [r8+0Fh]
0x180008575  jmp     short loc_18000858A
0x180008577  mov     ecx, 4
0x18000857c  jmp     short loc_18000858A
0x18000857e  mov     ecx, 8
0x180008583  jmp     short loc_18000858A
0x180008585  mov     ecx, 2
0x18000858a  mov     edx, [rdx]
0x18000858c  xor     eax, eax
0x18000858e  mov     r8d, ecx
0x180008591  or      r8d, edx
0x180008594  cmp     r8d, edx
0x180008597  mov     r9d, r8d
0x18000859a  setz    al
0x18000859d  or      r9d, 1
0x1800085a1  cmp     r8d, edx
0x1800085a4  mov     [rbx+10h], eax
0x1800085a7  mov     eax, edx
0x1800085a9  cmovz   r9d, r8d
0x1800085ad  lock cmpxchg [r10], r9d
0x1800085b2  jz      short loc_1800085B8
0x1800085b4  mov     edx, eax
0x1800085b6  jmp     short loc_18000858C
0x1800085b8  test    r9b, 1
0x1800085bc  setnz   cl
0x1800085bf  test    dl, 1
0x1800085c2  setz    al
0x1800085c5  test    al, cl
0x1800085c7  mov     eax, 0
0x1800085cc  setnz   al
0x1800085cf  mov     [rbx], eax
0x1800085d1  jmp     short loc_1800085F1
0x1800085d3  mov     r9, rbx
0x1800085d6  mov     edx, r8d
0x1800085d9  mov     rcx, r10
0x1800085dc  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800085e1  jmp     short loc_1800085F1
0x1800085e3  mov     r9, rbx
0x1800085e6  mov     edx, r8d
0x1800085e9  mov     rcx, r10
0x1800085ec  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1800085f1  mov     rax, rbx
0x1800085f4  add     rsp, 20h
0x1800085f8  pop     rbx
0x1800085f9  retn
```
