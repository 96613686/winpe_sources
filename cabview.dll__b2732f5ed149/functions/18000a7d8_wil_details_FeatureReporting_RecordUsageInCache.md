# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000a7d8`
- end: `0x18000a94f`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800082a8`

## callees

- `0x18000a62c`
- `0x18000a6fc`
- `0x18000a7d8`

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
0x18000a7d8  mov     [rsp+arg_0], rbx
0x18000a7dd  push    rdi
0x18000a7de  sub     rsp, 20h
0x18000a7e2  xor     eax, eax
0x18000a7e4  xorps   xmm0, xmm0
0x18000a7e7  mov     r10, rdx
0x18000a7ea  mov     rbx, rcx
0x18000a7ed  mov     r9d, r8d
0x18000a7f0  movups  xmmword ptr [rcx], xmm0
0x18000a7f3  mov     [rcx+10h], rax
0x18000a7f7  test    r8d, r8d
0x18000a7fa  jz      loc_18000A933
0x18000a800  sub     r9d, 1
0x18000a804  jz      loc_18000A923
0x18000a80a  sub     r9d, 1
0x18000a80e  jz      loc_18000A8AB
0x18000a814  sub     r9d, 1
0x18000a818  jz      loc_18000A8AB
0x18000a81e  sub     r9d, 1
0x18000a822  jz      loc_18000A933
0x18000a828  sub     r9d, 1
0x18000a82c  jz      loc_18000A923
0x18000a832  sub     r9d, 1
0x18000a836  jz      short loc_18000A8AB
0x18000a838  cmp     r9d, 1
0x18000a83c  jz      short loc_18000A8AB
0x18000a83e  lea     r11d, [r8-140h]
0x18000a845  lea     r9d, [rax+1]
0x18000a849  cmp     r11d, 40h ; '@'
0x18000a84d  jge     short loc_18000A897
0x18000a84f  mov     eax, [rdx+4]
0x18000a852  lea     ecx, [r9+0Fh]
0x18000a856  mov     edi, r11d
0x18000a859  shl     edi, 5
0x18000a85c  test    cl, al
0x18000a85e  jz      short loc_18000A872
0x18000a860  mov     edx, eax
0x18000a862  shr     edx, 5
0x18000a865  and     edx, 3Fh
0x18000a868  cmp     edx, r11d
0x18000a86b  jnz     short loc_18000A872
0x18000a86d  mov     edx, r9d
0x18000a870  jmp     short loc_18000A874
0x18000a872  xor     edx, edx
0x18000a874  mov     [rbx+10h], edx
0x18000a877  mov     edx, edi
0x18000a879  xor     edx, eax
0x18000a87b  and     edx, 7E0h
0x18000a881  xor     edx, eax
0x18000a883  or      edx, ecx
0x18000a885  lock cmpxchg [r10+4], edx
0x18000a88b  jnz     short loc_18000A85C
0x18000a88d  cmp     dword ptr [rbx+10h], 0
0x18000a891  jnz     loc_18000A941
0x18000a897  mov     [rbx+8], r8d
0x18000a89b  mov     [rbx+4], r9d
0x18000a89f  mov     dword ptr [rbx+0Ch], 0
0x18000a8a6  jmp     loc_18000A941
0x18000a8ab  xor     ecx, ecx
0x18000a8ad  sub     r8d, 2
0x18000a8b1  jz      short loc_18000A8D9
0x18000a8b3  sub     r8d, 1
0x18000a8b7  jz      short loc_18000A8D2
0x18000a8b9  sub     r8d, 3
0x18000a8bd  jz      short loc_18000A8CB
0x18000a8bf  cmp     r8d, 1
0x18000a8c3  jnz     short loc_18000A8DE
0x18000a8c5  lea     ecx, [r8+0Fh]
0x18000a8c9  jmp     short loc_18000A8DE
0x18000a8cb  mov     ecx, 4
0x18000a8d0  jmp     short loc_18000A8DE
0x18000a8d2  mov     ecx, 8
0x18000a8d7  jmp     short loc_18000A8DE
0x18000a8d9  mov     ecx, 2
0x18000a8de  mov     edx, [rdx]
0x18000a8e0  mov     r9d, 1
0x18000a8e6  xor     eax, eax
0x18000a8e8  mov     r8d, ecx
0x18000a8eb  or      r8d, edx
0x18000a8ee  cmp     r8d, edx
0x18000a8f1  mov     r11d, r8d
0x18000a8f4  setz    al
0x18000a8f7  or      r11d, r9d
0x18000a8fa  cmp     r8d, edx
0x18000a8fd  mov     [rbx+10h], eax
0x18000a900  mov     eax, edx
0x18000a902  cmovz   r11d, r8d
0x18000a906  lock cmpxchg [r10], r11d
0x18000a90b  jz      short loc_18000A911
0x18000a90d  mov     edx, eax
0x18000a90f  jmp     short loc_18000A8E6
0x18000a911  test    r9b, r11b
0x18000a914  jz      short loc_18000A91B
0x18000a916  test    r9b, dl
0x18000a919  jz      short loc_18000A91E
0x18000a91b  xor     r9d, r9d
0x18000a91e  mov     [rbx], r9d
0x18000a921  jmp     short loc_18000A941
0x18000a923  mov     r9, rbx
0x18000a926  mov     edx, r8d
0x18000a929  mov     rcx, r10
0x18000a92c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000a931  jmp     short loc_18000A941
0x18000a933  mov     r9, rbx
0x18000a936  mov     edx, r8d
0x18000a939  mov     rcx, r10
0x18000a93c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000a941  mov     rax, rbx
0x18000a944  mov     rbx, [rsp+28h+arg_0]
0x18000a949  add     rsp, 20h
0x18000a94d  pop     rdi
0x18000a94e  retn
```
