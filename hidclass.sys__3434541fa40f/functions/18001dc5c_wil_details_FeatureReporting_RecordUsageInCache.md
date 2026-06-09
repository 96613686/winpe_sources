# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001dc5c`
- end: `0x18001ddd9`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001de68`

## callees

- `0x18001dab0`
- `0x18001db80`
- `0x18001dc5c`

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
0x18001dc5c  mov     [rsp+arg_0], rbx
0x18001dc61  push    rdi
0x18001dc62  sub     rsp, 20h
0x18001dc66  xor     eax, eax
0x18001dc68  xorps   xmm0, xmm0
0x18001dc6b  mov     edi, r9d
0x18001dc6e  mov     r11, rdx
0x18001dc71  mov     r9, rcx
0x18001dc74  mov     r10d, r8d
0x18001dc77  movups  xmmword ptr [rcx], xmm0
0x18001dc7a  mov     [rcx+10h], rax
0x18001dc7e  test    r8d, r8d
0x18001dc81  jz      loc_18001DDBF
0x18001dc87  sub     r10d, 1
0x18001dc8b  jz      loc_18001DDB2
0x18001dc91  sub     r10d, 1
0x18001dc95  jz      loc_18001DD34
0x18001dc9b  sub     r10d, 1
0x18001dc9f  jz      loc_18001DD34
0x18001dca5  sub     r10d, 1
0x18001dca9  jz      loc_18001DDBF
0x18001dcaf  sub     r10d, 1
0x18001dcb3  jz      loc_18001DDB2
0x18001dcb9  sub     r10d, 1
0x18001dcbd  jz      short loc_18001DD34
0x18001dcbf  cmp     r10d, 1
0x18001dcc3  jz      short loc_18001DD34
0x18001dcc5  lea     r10d, [r8-140h]
0x18001dccc  cmp     r10d, 40h ; '@'
0x18001dcd0  jge     short loc_18001DD1F
0x18001dcd2  mov     eax, [rdx+4]
0x18001dcd5  mov     ebx, r10d
0x18001dcd8  shl     ebx, 5
0x18001dcdb  mov     ecx, 10h
0x18001dce0  test    cl, al
0x18001dce2  jz      short loc_18001DCF8
0x18001dce4  mov     edx, eax
0x18001dce6  shr     edx, 5
0x18001dce9  and     edx, 3Fh
0x18001dcec  cmp     edx, r10d
0x18001dcef  jnz     short loc_18001DCF8
0x18001dcf1  mov     edx, 1
0x18001dcf6  jmp     short loc_18001DCFA
0x18001dcf8  xor     edx, edx
0x18001dcfa  mov     [r9+10h], edx
0x18001dcfe  mov     edx, ebx
0x18001dd00  xor     edx, eax
0x18001dd02  and     edx, 7E0h
0x18001dd08  xor     edx, eax
0x18001dd0a  or      edx, ecx
0x18001dd0c  lock cmpxchg [r11+4], edx
0x18001dd12  jnz     short loc_18001DCE0
0x18001dd14  cmp     dword ptr [r9+10h], 0
0x18001dd19  jnz     loc_18001DDCA
0x18001dd1f  mov     [r9+8], r8d
0x18001dd23  mov     dword ptr [r9+4], 1
0x18001dd2b  mov     [r9+0Ch], edi
0x18001dd2f  jmp     loc_18001DDCA
0x18001dd34  xor     ecx, ecx
0x18001dd36  sub     r8d, 2
0x18001dd3a  jz      short loc_18001DD62
0x18001dd3c  sub     r8d, 1
0x18001dd40  jz      short loc_18001DD5B
0x18001dd42  sub     r8d, 3
0x18001dd46  jz      short loc_18001DD54
0x18001dd48  cmp     r8d, 1
0x18001dd4c  jnz     short loc_18001DD67
0x18001dd4e  lea     ecx, [r8+0Fh]
0x18001dd52  jmp     short loc_18001DD67
0x18001dd54  mov     ecx, 4
0x18001dd59  jmp     short loc_18001DD67
0x18001dd5b  mov     ecx, 8
0x18001dd60  jmp     short loc_18001DD67
0x18001dd62  mov     ecx, 2
0x18001dd67  mov     edx, [rdx]
0x18001dd69  xor     eax, eax
0x18001dd6b  mov     r8d, ecx
0x18001dd6e  or      r8d, edx
0x18001dd71  cmp     r8d, edx
0x18001dd74  mov     r10d, r8d
0x18001dd77  setz    al
0x18001dd7a  or      r10d, 1
0x18001dd7e  cmp     r8d, edx
0x18001dd81  mov     [r9+10h], eax
0x18001dd85  mov     eax, edx
0x18001dd87  cmovz   r10d, r8d
0x18001dd8b  lock cmpxchg [r11], r10d
0x18001dd90  jz      short loc_18001DD96
0x18001dd92  mov     edx, eax
0x18001dd94  jmp     short loc_18001DD69
0x18001dd96  test    r10b, 1
0x18001dd9a  setnz   cl
0x18001dd9d  test    dl, 1
0x18001dda0  setz    al
0x18001dda3  test    al, cl
0x18001dda5  mov     eax, 0
0x18001ddaa  setnz   al
0x18001ddad  mov     [r9], eax
0x18001ddb0  jmp     short loc_18001DDCA
0x18001ddb2  mov     edx, r8d
0x18001ddb5  mov     rcx, r11
0x18001ddb8  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18001ddbd  jmp     short loc_18001DDCA
0x18001ddbf  mov     edx, r8d
0x18001ddc2  mov     rcx, r11
0x18001ddc5  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18001ddca  mov     rbx, [rsp+28h+arg_0]
0x18001ddcf  mov     rax, r9
0x18001ddd2  add     rsp, 20h
0x18001ddd6  pop     rdi
0x18001ddd7  retn
```
