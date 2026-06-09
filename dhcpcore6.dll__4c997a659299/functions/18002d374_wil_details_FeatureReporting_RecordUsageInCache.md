# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18002d374`
- end: `0x18002d4f1`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002d580`

## callees

- `0x18002d1c8`
- `0x18002d298`
- `0x18002d374`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  _DWORD *v6; // r9
  unsigned int v7; // r10d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 i; // edx
  signed __int32 v16; // r10d
  signed __int32 v17; // eax

  v6 = (_DWORD *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_32;
    case 1u:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_31;
  }
  if ( a3 - 6 >= 2 )
  {
    v7 = a3 - 320;
    if ( (int)(a3 - 320) >= 64 )
      goto LABEL_16;
    v8 = *((_DWORD *)a2 + 1);
    do
    {
      v9 = (v8 & 0x10) != 0 && ((v8 >> 5) & 0x3F) == v7;
      *(_DWORD *)(a1 + 16) = v9;
      v10 = v8;
      v8 = _InterlockedCompareExchange(
             a2 + 1,
             v8 ^ ((unsigned __int16)v8 ^ (unsigned __int16)(32 * v7)) & 0x7E0 | 0x10,
             v8);
    }
    while ( v10 != v8 );
    if ( !*(_DWORD *)(a1 + 16) )
    {
LABEL_16:
      *(_DWORD *)(a1 + 8) = a3;
      *(_DWORD *)(a1 + 4) = 1;
      *(_DWORD *)(a1 + 12) = a4;
    }
    return v6;
  }
LABEL_17:
  v11 = 0;
  v12 = a3 - 2;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 3;
      if ( v14 )
      {
        if ( v14 == 1 )
          v11 = 16;
      }
      else
      {
        v11 = 4;
      }
    }
    else
    {
      v11 = 8;
    }
  }
  else
  {
    v11 = 2;
  }
  for ( i = *a2; ; i = v17 )
  {
    v16 = i | v11 | 1;
    v6[4] = (i | v11) == i;
    if ( (i | v11) == i )
      v16 = i | v11;
    v17 = _InterlockedCompareExchange(a2, v16, i);
    if ( i == v17 )
      break;
  }
  *v6 = (v16 & 1) != 0 && (i & 1) == 0;
  return v6;
}

```

## disassembly

```asm
0x18002d374  mov     [rsp+arg_0], rbx
0x18002d379  push    rdi
0x18002d37a  sub     rsp, 20h
0x18002d37e  xor     eax, eax
0x18002d380  xorps   xmm0, xmm0
0x18002d383  mov     edi, r9d
0x18002d386  mov     r11, rdx
0x18002d389  mov     r9, rcx
0x18002d38c  mov     r10d, r8d
0x18002d38f  movups  xmmword ptr [rcx], xmm0
0x18002d392  mov     [rcx+10h], rax
0x18002d396  test    r8d, r8d
0x18002d399  jz      loc_18002D4D7
0x18002d39f  sub     r10d, 1
0x18002d3a3  jz      loc_18002D4CA
0x18002d3a9  sub     r10d, 1
0x18002d3ad  jz      loc_18002D44C
0x18002d3b3  sub     r10d, 1
0x18002d3b7  jz      loc_18002D44C
0x18002d3bd  sub     r10d, 1
0x18002d3c1  jz      loc_18002D4D7
0x18002d3c7  sub     r10d, 1
0x18002d3cb  jz      loc_18002D4CA
0x18002d3d1  sub     r10d, 1
0x18002d3d5  jz      short loc_18002D44C
0x18002d3d7  cmp     r10d, 1
0x18002d3db  jz      short loc_18002D44C
0x18002d3dd  lea     r10d, [r8-140h]
0x18002d3e4  cmp     r10d, 40h ; '@'
0x18002d3e8  jge     short loc_18002D437
0x18002d3ea  mov     eax, [rdx+4]
0x18002d3ed  mov     ebx, r10d
0x18002d3f0  shl     ebx, 5
0x18002d3f3  mov     ecx, 10h
0x18002d3f8  test    cl, al
0x18002d3fa  jz      short loc_18002D410
0x18002d3fc  mov     edx, eax
0x18002d3fe  shr     edx, 5
0x18002d401  and     edx, 3Fh
0x18002d404  cmp     edx, r10d
0x18002d407  jnz     short loc_18002D410
0x18002d409  mov     edx, 1
0x18002d40e  jmp     short loc_18002D412
0x18002d410  xor     edx, edx
0x18002d412  mov     [r9+10h], edx
0x18002d416  mov     edx, ebx
0x18002d418  xor     edx, eax
0x18002d41a  and     edx, 7E0h
0x18002d420  xor     edx, eax
0x18002d422  or      edx, ecx
0x18002d424  lock cmpxchg [r11+4], edx
0x18002d42a  jnz     short loc_18002D3F8
0x18002d42c  cmp     dword ptr [r9+10h], 0
0x18002d431  jnz     loc_18002D4E2
0x18002d437  mov     [r9+8], r8d
0x18002d43b  mov     dword ptr [r9+4], 1
0x18002d443  mov     [r9+0Ch], edi
0x18002d447  jmp     loc_18002D4E2
0x18002d44c  xor     ecx, ecx
0x18002d44e  sub     r8d, 2
0x18002d452  jz      short loc_18002D47A
0x18002d454  sub     r8d, 1
0x18002d458  jz      short loc_18002D473
0x18002d45a  sub     r8d, 3
0x18002d45e  jz      short loc_18002D46C
0x18002d460  cmp     r8d, 1
0x18002d464  jnz     short loc_18002D47F
0x18002d466  lea     ecx, [r8+0Fh]
0x18002d46a  jmp     short loc_18002D47F
0x18002d46c  mov     ecx, 4
0x18002d471  jmp     short loc_18002D47F
0x18002d473  mov     ecx, 8
0x18002d478  jmp     short loc_18002D47F
0x18002d47a  mov     ecx, 2
0x18002d47f  mov     edx, [rdx]
0x18002d481  xor     eax, eax
0x18002d483  mov     r8d, ecx
0x18002d486  or      r8d, edx
0x18002d489  cmp     r8d, edx
0x18002d48c  mov     r10d, r8d
0x18002d48f  setz    al
0x18002d492  or      r10d, 1
0x18002d496  cmp     r8d, edx
0x18002d499  mov     [r9+10h], eax
0x18002d49d  mov     eax, edx
0x18002d49f  cmovz   r10d, r8d
0x18002d4a3  lock cmpxchg [r11], r10d
0x18002d4a8  jz      short loc_18002D4AE
0x18002d4aa  mov     edx, eax
0x18002d4ac  jmp     short loc_18002D481
0x18002d4ae  test    r10b, 1
0x18002d4b2  setnz   cl
0x18002d4b5  test    dl, 1
0x18002d4b8  setz    al
0x18002d4bb  test    al, cl
0x18002d4bd  mov     eax, 0
0x18002d4c2  setnz   al
0x18002d4c5  mov     [r9], eax
0x18002d4c8  jmp     short loc_18002D4E2
0x18002d4ca  mov     edx, r8d
0x18002d4cd  mov     rcx, r11
0x18002d4d0  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18002d4d5  jmp     short loc_18002D4E2
0x18002d4d7  mov     edx, r8d
0x18002d4da  mov     rcx, r11
0x18002d4dd  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18002d4e2  mov     rbx, [rsp+28h+arg_0]
0x18002d4e7  mov     rax, r9
0x18002d4ea  add     rsp, 20h
0x18002d4ee  pop     rdi
0x18002d4ef  retn
```
