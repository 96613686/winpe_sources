# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000df9c`
- end: `0x14000e119`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000e1a0`

## callees

- `0x14000ddf0`
- `0x14000dec0`
- `0x14000df9c`

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
0x14000df9c  mov     [rsp+arg_0], rbx
0x14000dfa1  push    rdi
0x14000dfa2  sub     rsp, 20h
0x14000dfa6  xor     eax, eax
0x14000dfa8  xorps   xmm0, xmm0
0x14000dfab  mov     edi, r9d
0x14000dfae  mov     r11, rdx
0x14000dfb1  mov     r9, rcx
0x14000dfb4  mov     r10d, r8d
0x14000dfb7  movups  xmmword ptr [rcx], xmm0
0x14000dfba  mov     [rcx+10h], rax
0x14000dfbe  test    r8d, r8d
0x14000dfc1  jz      loc_14000E0FF
0x14000dfc7  sub     r10d, 1
0x14000dfcb  jz      loc_14000E0F2
0x14000dfd1  sub     r10d, 1
0x14000dfd5  jz      loc_14000E074
0x14000dfdb  sub     r10d, 1
0x14000dfdf  jz      loc_14000E074
0x14000dfe5  sub     r10d, 1
0x14000dfe9  jz      loc_14000E0FF
0x14000dfef  sub     r10d, 1
0x14000dff3  jz      loc_14000E0F2
0x14000dff9  sub     r10d, 1
0x14000dffd  jz      short loc_14000E074
0x14000dfff  cmp     r10d, 1
0x14000e003  jz      short loc_14000E074
0x14000e005  lea     r10d, [r8-140h]
0x14000e00c  cmp     r10d, 40h ; '@'
0x14000e010  jge     short loc_14000E05F
0x14000e012  mov     eax, [rdx+4]
0x14000e015  mov     ebx, r10d
0x14000e018  shl     ebx, 5
0x14000e01b  mov     ecx, 10h
0x14000e020  test    cl, al
0x14000e022  jz      short loc_14000E038
0x14000e024  mov     edx, eax
0x14000e026  shr     edx, 5
0x14000e029  and     edx, 3Fh
0x14000e02c  cmp     edx, r10d
0x14000e02f  jnz     short loc_14000E038
0x14000e031  mov     edx, 1
0x14000e036  jmp     short loc_14000E03A
0x14000e038  xor     edx, edx
0x14000e03a  mov     [r9+10h], edx
0x14000e03e  mov     edx, ebx
0x14000e040  xor     edx, eax
0x14000e042  and     edx, 7E0h
0x14000e048  xor     edx, eax
0x14000e04a  or      edx, ecx
0x14000e04c  lock cmpxchg [r11+4], edx
0x14000e052  jnz     short loc_14000E020
0x14000e054  cmp     dword ptr [r9+10h], 0
0x14000e059  jnz     loc_14000E10A
0x14000e05f  mov     [r9+8], r8d
0x14000e063  mov     dword ptr [r9+4], 1
0x14000e06b  mov     [r9+0Ch], edi
0x14000e06f  jmp     loc_14000E10A
0x14000e074  xor     ecx, ecx
0x14000e076  sub     r8d, 2
0x14000e07a  jz      short loc_14000E0A2
0x14000e07c  sub     r8d, 1
0x14000e080  jz      short loc_14000E09B
0x14000e082  sub     r8d, 3
0x14000e086  jz      short loc_14000E094
0x14000e088  cmp     r8d, 1
0x14000e08c  jnz     short loc_14000E0A7
0x14000e08e  lea     ecx, [r8+0Fh]
0x14000e092  jmp     short loc_14000E0A7
0x14000e094  mov     ecx, 4
0x14000e099  jmp     short loc_14000E0A7
0x14000e09b  mov     ecx, 8
0x14000e0a0  jmp     short loc_14000E0A7
0x14000e0a2  mov     ecx, 2
0x14000e0a7  mov     edx, [rdx]
0x14000e0a9  xor     eax, eax
0x14000e0ab  mov     r8d, ecx
0x14000e0ae  or      r8d, edx
0x14000e0b1  cmp     r8d, edx
0x14000e0b4  mov     r10d, r8d
0x14000e0b7  setz    al
0x14000e0ba  or      r10d, 1
0x14000e0be  cmp     r8d, edx
0x14000e0c1  mov     [r9+10h], eax
0x14000e0c5  mov     eax, edx
0x14000e0c7  cmovz   r10d, r8d
0x14000e0cb  lock cmpxchg [r11], r10d
0x14000e0d0  jz      short loc_14000E0D6
0x14000e0d2  mov     edx, eax
0x14000e0d4  jmp     short loc_14000E0A9
0x14000e0d6  test    r10b, 1
0x14000e0da  setnz   cl
0x14000e0dd  test    dl, 1
0x14000e0e0  setz    al
0x14000e0e3  test    al, cl
0x14000e0e5  mov     eax, 0
0x14000e0ea  setnz   al
0x14000e0ed  mov     [r9], eax
0x14000e0f0  jmp     short loc_14000E10A
0x14000e0f2  mov     edx, r8d
0x14000e0f5  mov     rcx, r11
0x14000e0f8  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14000e0fd  jmp     short loc_14000E10A
0x14000e0ff  mov     edx, r8d
0x14000e102  mov     rcx, r11
0x14000e105  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14000e10a  mov     rbx, [rsp+28h+arg_0]
0x14000e10f  mov     rax, r9
0x14000e112  add     rsp, 20h
0x14000e116  pop     rdi
0x14000e117  retn
```
