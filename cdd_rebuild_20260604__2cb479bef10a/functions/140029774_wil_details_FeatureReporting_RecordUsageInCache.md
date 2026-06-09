# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140029774`
- end: `0x1400298f1`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140029980`

## callees

- `0x1400295c8`
- `0x140029698`
- `0x140029774`

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
0x140029774  mov     [rsp+arg_0], rbx
0x140029779  push    rdi
0x14002977a  sub     rsp, 20h
0x14002977e  xor     eax, eax
0x140029780  xorps   xmm0, xmm0
0x140029783  mov     edi, r9d
0x140029786  mov     r11, rdx
0x140029789  mov     r9, rcx
0x14002978c  mov     r10d, r8d
0x14002978f  movups  xmmword ptr [rcx], xmm0
0x140029792  mov     [rcx+10h], rax
0x140029796  test    r8d, r8d
0x140029799  jz      loc_1400298D7
0x14002979f  sub     r10d, 1
0x1400297a3  jz      loc_1400298CA
0x1400297a9  sub     r10d, 1
0x1400297ad  jz      loc_14002984C
0x1400297b3  sub     r10d, 1
0x1400297b7  jz      loc_14002984C
0x1400297bd  sub     r10d, 1
0x1400297c1  jz      loc_1400298D7
0x1400297c7  sub     r10d, 1
0x1400297cb  jz      loc_1400298CA
0x1400297d1  sub     r10d, 1
0x1400297d5  jz      short loc_14002984C
0x1400297d7  cmp     r10d, 1
0x1400297db  jz      short loc_14002984C
0x1400297dd  lea     r10d, [r8-140h]
0x1400297e4  cmp     r10d, 40h ; '@'
0x1400297e8  jge     short loc_140029837
0x1400297ea  mov     eax, [rdx+4]
0x1400297ed  mov     ebx, r10d
0x1400297f0  shl     ebx, 5
0x1400297f3  mov     ecx, 10h
0x1400297f8  test    cl, al
0x1400297fa  jz      short loc_140029810
0x1400297fc  mov     edx, eax
0x1400297fe  shr     edx, 5
0x140029801  and     edx, 3Fh
0x140029804  cmp     edx, r10d
0x140029807  jnz     short loc_140029810
0x140029809  mov     edx, 1
0x14002980e  jmp     short loc_140029812
0x140029810  xor     edx, edx
0x140029812  mov     [r9+10h], edx
0x140029816  mov     edx, ebx
0x140029818  xor     edx, eax
0x14002981a  and     edx, 7E0h
0x140029820  xor     edx, eax
0x140029822  or      edx, ecx
0x140029824  lock cmpxchg [r11+4], edx
0x14002982a  jnz     short loc_1400297F8
0x14002982c  cmp     dword ptr [r9+10h], 0
0x140029831  jnz     loc_1400298E2
0x140029837  mov     [r9+8], r8d
0x14002983b  mov     dword ptr [r9+4], 1
0x140029843  mov     [r9+0Ch], edi
0x140029847  jmp     loc_1400298E2
0x14002984c  xor     ecx, ecx
0x14002984e  sub     r8d, 2
0x140029852  jz      short loc_14002987A
0x140029854  sub     r8d, 1
0x140029858  jz      short loc_140029873
0x14002985a  sub     r8d, 3
0x14002985e  jz      short loc_14002986C
0x140029860  cmp     r8d, 1
0x140029864  jnz     short loc_14002987F
0x140029866  lea     ecx, [r8+0Fh]
0x14002986a  jmp     short loc_14002987F
0x14002986c  mov     ecx, 4
0x140029871  jmp     short loc_14002987F
0x140029873  mov     ecx, 8
0x140029878  jmp     short loc_14002987F
0x14002987a  mov     ecx, 2
0x14002987f  mov     edx, [rdx]
0x140029881  xor     eax, eax
0x140029883  mov     r8d, ecx
0x140029886  or      r8d, edx
0x140029889  cmp     r8d, edx
0x14002988c  mov     r10d, r8d
0x14002988f  setz    al
0x140029892  or      r10d, 1
0x140029896  cmp     r8d, edx
0x140029899  mov     [r9+10h], eax
0x14002989d  mov     eax, edx
0x14002989f  cmovz   r10d, r8d
0x1400298a3  lock cmpxchg [r11], r10d
0x1400298a8  jz      short loc_1400298AE
0x1400298aa  mov     edx, eax
0x1400298ac  jmp     short loc_140029881
0x1400298ae  test    r10b, 1
0x1400298b2  setnz   cl
0x1400298b5  test    dl, 1
0x1400298b8  setz    al
0x1400298bb  test    al, cl
0x1400298bd  mov     eax, 0
0x1400298c2  setnz   al
0x1400298c5  mov     [r9], eax
0x1400298c8  jmp     short loc_1400298E2
0x1400298ca  mov     edx, r8d
0x1400298cd  mov     rcx, r11
0x1400298d0  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1400298d5  jmp     short loc_1400298E2
0x1400298d7  mov     edx, r8d
0x1400298da  mov     rcx, r11
0x1400298dd  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1400298e2  mov     rbx, [rsp+28h+arg_0]
0x1400298e7  mov     rax, r9
0x1400298ea  add     rsp, 20h
0x1400298ee  pop     rdi
0x1400298ef  retn
```
