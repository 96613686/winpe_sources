# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1800169d8`
- end: `0x180016b54`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800199e8`

## callees

- `0x1800169d8`
- `0x180016b5c`
- `0x18001bb18`

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
0x1800169d8  mov     [rsp+arg_0], rbx
0x1800169dd  push    rdi
0x1800169de  sub     rsp, 20h
0x1800169e2  xor     eax, eax
0x1800169e4  xorps   xmm0, xmm0
0x1800169e7  mov     edi, r9d
0x1800169ea  mov     r11, rdx
0x1800169ed  mov     r9, rcx
0x1800169f0  mov     r10d, r8d
0x1800169f3  movups  xmmword ptr [rcx], xmm0
0x1800169f6  mov     [rcx+10h], rax
0x1800169fa  test    r8d, r8d
0x1800169fd  jz      loc_180016B3B
0x180016a03  sub     r10d, 1
0x180016a07  jz      loc_180016B2E
0x180016a0d  sub     r10d, 1
0x180016a11  jz      loc_180016AB0
0x180016a17  sub     r10d, 1
0x180016a1b  jz      loc_180016AB0
0x180016a21  sub     r10d, 1
0x180016a25  jz      loc_180016B3B
0x180016a2b  sub     r10d, 1
0x180016a2f  jz      loc_180016B2E
0x180016a35  sub     r10d, 1
0x180016a39  jz      short loc_180016AB0
0x180016a3b  cmp     r10d, 1
0x180016a3f  jz      short loc_180016AB0
0x180016a41  lea     r10d, [r8-140h]
0x180016a48  cmp     r10d, 40h ; '@'
0x180016a4c  jge     short loc_180016A9B
0x180016a4e  mov     eax, [rdx+4]
0x180016a51  mov     ebx, r10d
0x180016a54  shl     ebx, 5
0x180016a57  mov     ecx, 10h
0x180016a5c  test    cl, al
0x180016a5e  jz      short loc_180016A74
0x180016a60  mov     edx, eax
0x180016a62  shr     edx, 5
0x180016a65  and     edx, 3Fh
0x180016a68  cmp     edx, r10d
0x180016a6b  jnz     short loc_180016A74
0x180016a6d  mov     edx, 1
0x180016a72  jmp     short loc_180016A76
0x180016a74  xor     edx, edx
0x180016a76  mov     [r9+10h], edx
0x180016a7a  mov     edx, ebx
0x180016a7c  xor     edx, eax
0x180016a7e  and     edx, 7E0h
0x180016a84  xor     edx, eax
0x180016a86  or      edx, ecx
0x180016a88  lock cmpxchg [r11+4], edx
0x180016a8e  jnz     short loc_180016A5C
0x180016a90  cmp     dword ptr [r9+10h], 0
0x180016a95  jnz     loc_180016B46
0x180016a9b  mov     [r9+8], r8d
0x180016a9f  mov     dword ptr [r9+4], 1
0x180016aa7  mov     [r9+0Ch], edi
0x180016aab  jmp     loc_180016B46
0x180016ab0  xor     ecx, ecx
0x180016ab2  sub     r8d, 2
0x180016ab6  jz      short loc_180016ADE
0x180016ab8  sub     r8d, 1
0x180016abc  jz      short loc_180016AD7
0x180016abe  sub     r8d, 3
0x180016ac2  jz      short loc_180016AD0
0x180016ac4  cmp     r8d, 1
0x180016ac8  jnz     short loc_180016AE3
0x180016aca  lea     ecx, [r8+0Fh]
0x180016ace  jmp     short loc_180016AE3
0x180016ad0  mov     ecx, 4
0x180016ad5  jmp     short loc_180016AE3
0x180016ad7  mov     ecx, 8
0x180016adc  jmp     short loc_180016AE3
0x180016ade  mov     ecx, 2
0x180016ae3  mov     edx, [rdx]
0x180016ae5  xor     eax, eax
0x180016ae7  mov     r8d, ecx
0x180016aea  or      r8d, edx
0x180016aed  cmp     r8d, edx
0x180016af0  mov     r10d, r8d
0x180016af3  setz    al
0x180016af6  or      r10d, 1
0x180016afa  cmp     r8d, edx
0x180016afd  mov     [r9+10h], eax
0x180016b01  mov     eax, edx
0x180016b03  cmovz   r10d, r8d
0x180016b07  lock cmpxchg [r11], r10d
0x180016b0c  jz      short loc_180016B12
0x180016b0e  mov     edx, eax
0x180016b10  jmp     short loc_180016AE5
0x180016b12  test    r10b, 1
0x180016b16  setnz   cl
0x180016b19  test    dl, 1
0x180016b1c  setz    al
0x180016b1f  test    al, cl
0x180016b21  mov     eax, 0
0x180016b26  setnz   al
0x180016b29  mov     [r9], eax
0x180016b2c  jmp     short loc_180016B46
0x180016b2e  mov     edx, r8d
0x180016b31  mov     rcx, r11
0x180016b34  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180016b39  jmp     short loc_180016B46
0x180016b3b  mov     edx, r8d
0x180016b3e  mov     rcx, r11
0x180016b41  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180016b46  mov     rbx, [rsp+28h+arg_0]
0x180016b4b  mov     rax, r9
0x180016b4e  add     rsp, 20h
0x180016b52  pop     rdi
0x180016b53  retn
```
