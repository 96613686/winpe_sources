# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000fd88`
- end: `0x18000ff04`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ff88`
- `0x1800151a4`

## callees

- `0x18000fbdc`
- `0x18000fcac`
- `0x18000fd88`

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
0x18000fd88  mov     [rsp+arg_0], rbx
0x18000fd8d  push    rdi
0x18000fd8e  sub     rsp, 20h
0x18000fd92  xor     eax, eax
0x18000fd94  xorps   xmm0, xmm0
0x18000fd97  mov     edi, r9d
0x18000fd9a  mov     r11, rdx
0x18000fd9d  mov     r9, rcx
0x18000fda0  mov     r10d, r8d
0x18000fda3  movups  xmmword ptr [rcx], xmm0
0x18000fda6  mov     [rcx+10h], rax
0x18000fdaa  test    r8d, r8d
0x18000fdad  jz      loc_18000FEEB
0x18000fdb3  sub     r10d, 1
0x18000fdb7  jz      loc_18000FEDE
0x18000fdbd  sub     r10d, 1
0x18000fdc1  jz      loc_18000FE60
0x18000fdc7  sub     r10d, 1
0x18000fdcb  jz      loc_18000FE60
0x18000fdd1  sub     r10d, 1
0x18000fdd5  jz      loc_18000FEEB
0x18000fddb  sub     r10d, 1
0x18000fddf  jz      loc_18000FEDE
0x18000fde5  sub     r10d, 1
0x18000fde9  jz      short loc_18000FE60
0x18000fdeb  cmp     r10d, 1
0x18000fdef  jz      short loc_18000FE60
0x18000fdf1  lea     r10d, [r8-140h]
0x18000fdf8  cmp     r10d, 40h ; '@'
0x18000fdfc  jge     short loc_18000FE4B
0x18000fdfe  mov     eax, [rdx+4]
0x18000fe01  mov     ebx, r10d
0x18000fe04  shl     ebx, 5
0x18000fe07  mov     ecx, 10h
0x18000fe0c  test    cl, al
0x18000fe0e  jz      short loc_18000FE24
0x18000fe10  mov     edx, eax
0x18000fe12  shr     edx, 5
0x18000fe15  and     edx, 3Fh
0x18000fe18  cmp     edx, r10d
0x18000fe1b  jnz     short loc_18000FE24
0x18000fe1d  mov     edx, 1
0x18000fe22  jmp     short loc_18000FE26
0x18000fe24  xor     edx, edx
0x18000fe26  mov     [r9+10h], edx
0x18000fe2a  mov     edx, ebx
0x18000fe2c  xor     edx, eax
0x18000fe2e  and     edx, 7E0h
0x18000fe34  xor     edx, eax
0x18000fe36  or      edx, ecx
0x18000fe38  lock cmpxchg [r11+4], edx
0x18000fe3e  jnz     short loc_18000FE0C
0x18000fe40  cmp     dword ptr [r9+10h], 0
0x18000fe45  jnz     loc_18000FEF6
0x18000fe4b  mov     [r9+8], r8d
0x18000fe4f  mov     dword ptr [r9+4], 1
0x18000fe57  mov     [r9+0Ch], edi
0x18000fe5b  jmp     loc_18000FEF6
0x18000fe60  xor     ecx, ecx
0x18000fe62  sub     r8d, 2
0x18000fe66  jz      short loc_18000FE8E
0x18000fe68  sub     r8d, 1
0x18000fe6c  jz      short loc_18000FE87
0x18000fe6e  sub     r8d, 3
0x18000fe72  jz      short loc_18000FE80
0x18000fe74  cmp     r8d, 1
0x18000fe78  jnz     short loc_18000FE93
0x18000fe7a  lea     ecx, [r8+0Fh]
0x18000fe7e  jmp     short loc_18000FE93
0x18000fe80  mov     ecx, 4
0x18000fe85  jmp     short loc_18000FE93
0x18000fe87  mov     ecx, 8
0x18000fe8c  jmp     short loc_18000FE93
0x18000fe8e  mov     ecx, 2
0x18000fe93  mov     edx, [rdx]
0x18000fe95  xor     eax, eax
0x18000fe97  mov     r8d, ecx
0x18000fe9a  or      r8d, edx
0x18000fe9d  cmp     r8d, edx
0x18000fea0  mov     r10d, r8d
0x18000fea3  setz    al
0x18000fea6  or      r10d, 1
0x18000feaa  cmp     r8d, edx
0x18000fead  mov     [r9+10h], eax
0x18000feb1  mov     eax, edx
0x18000feb3  cmovz   r10d, r8d
0x18000feb7  lock cmpxchg [r11], r10d
0x18000febc  jz      short loc_18000FEC2
0x18000febe  mov     edx, eax
0x18000fec0  jmp     short loc_18000FE95
0x18000fec2  test    r10b, 1
0x18000fec6  setnz   cl
0x18000fec9  test    dl, 1
0x18000fecc  setz    al
0x18000fecf  test    al, cl
0x18000fed1  mov     eax, 0
0x18000fed6  setnz   al
0x18000fed9  mov     [r9], eax
0x18000fedc  jmp     short loc_18000FEF6
0x18000fede  mov     edx, r8d
0x18000fee1  mov     rcx, r11
0x18000fee4  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000fee9  jmp     short loc_18000FEF6
0x18000feeb  mov     edx, r8d
0x18000feee  mov     rcx, r11
0x18000fef1  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000fef6  mov     rbx, [rsp+28h+arg_0]
0x18000fefb  mov     rax, r9
0x18000fefe  add     rsp, 20h
0x18000ff02  pop     rdi
0x18000ff03  retn
```
