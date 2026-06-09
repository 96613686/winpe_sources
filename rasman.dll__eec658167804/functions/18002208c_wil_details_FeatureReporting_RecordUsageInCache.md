# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18002208c`
- end: `0x180022208`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: `_DWORD *__fastcall(__int64, volatile signed __int32 *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002233c`

## callees

- `0x180021ee0`
- `0x180021fb0`
- `0x18002208c`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        __int64 a3,
        int a4)
{
  _DWORD *v6; // r9
  int v7; // r10d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  signed __int32 i; // edx
  signed __int32 v16; // r10d
  signed __int32 v17; // eax

  v6 = (_DWORD *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a3, (_DWORD *)a1);
      return v6;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3, a3, (_DWORD *)a1);
      return v6;
    case 5:
      goto LABEL_31;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
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
0x18002208c  mov     [rsp+arg_0], rbx
0x180022091  push    rdi
0x180022092  sub     rsp, 20h
0x180022096  xor     eax, eax
0x180022098  xorps   xmm0, xmm0
0x18002209b  mov     edi, r9d
0x18002209e  mov     r11, rdx
0x1800220a1  mov     r9, rcx
0x1800220a4  mov     r10d, r8d
0x1800220a7  movups  xmmword ptr [rcx], xmm0
0x1800220aa  mov     [rcx+10h], rax
0x1800220ae  test    r8d, r8d
0x1800220b1  jz      loc_1800221EF
0x1800220b7  sub     r10d, 1
0x1800220bb  jz      loc_1800221E2
0x1800220c1  sub     r10d, 1
0x1800220c5  jz      loc_180022164
0x1800220cb  sub     r10d, 1
0x1800220cf  jz      loc_180022164
0x1800220d5  sub     r10d, 1
0x1800220d9  jz      loc_1800221EF
0x1800220df  sub     r10d, 1
0x1800220e3  jz      loc_1800221E2
0x1800220e9  sub     r10d, 1
0x1800220ed  jz      short loc_180022164
0x1800220ef  cmp     r10d, 1
0x1800220f3  jz      short loc_180022164
0x1800220f5  lea     r10d, [r8-140h]
0x1800220fc  cmp     r10d, 40h ; '@'
0x180022100  jge     short loc_18002214F
0x180022102  mov     eax, [rdx+4]
0x180022105  mov     ebx, r10d
0x180022108  shl     ebx, 5
0x18002210b  mov     ecx, 10h
0x180022110  test    cl, al
0x180022112  jz      short loc_180022128
0x180022114  mov     edx, eax
0x180022116  shr     edx, 5
0x180022119  and     edx, 3Fh
0x18002211c  cmp     edx, r10d
0x18002211f  jnz     short loc_180022128
0x180022121  mov     edx, 1
0x180022126  jmp     short loc_18002212A
0x180022128  xor     edx, edx
0x18002212a  mov     [r9+10h], edx
0x18002212e  mov     edx, ebx
0x180022130  xor     edx, eax
0x180022132  and     edx, 7E0h
0x180022138  xor     edx, eax
0x18002213a  or      edx, ecx
0x18002213c  lock cmpxchg [r11+4], edx
0x180022142  jnz     short loc_180022110
0x180022144  cmp     dword ptr [r9+10h], 0
0x180022149  jnz     loc_1800221FA
0x18002214f  mov     [r9+8], r8d
0x180022153  mov     dword ptr [r9+4], 1
0x18002215b  mov     [r9+0Ch], edi
0x18002215f  jmp     loc_1800221FA
0x180022164  xor     ecx, ecx
0x180022166  sub     r8d, 2
0x18002216a  jz      short loc_180022192
0x18002216c  sub     r8d, 1
0x180022170  jz      short loc_18002218B
0x180022172  sub     r8d, 3
0x180022176  jz      short loc_180022184
0x180022178  cmp     r8d, 1
0x18002217c  jnz     short loc_180022197
0x18002217e  lea     ecx, [r8+0Fh]
0x180022182  jmp     short loc_180022197
0x180022184  mov     ecx, 4
0x180022189  jmp     short loc_180022197
0x18002218b  mov     ecx, 8
0x180022190  jmp     short loc_180022197
0x180022192  mov     ecx, 2
0x180022197  mov     edx, [rdx]
0x180022199  xor     eax, eax
0x18002219b  mov     r8d, ecx
0x18002219e  or      r8d, edx
0x1800221a1  cmp     r8d, edx
0x1800221a4  mov     r10d, r8d
0x1800221a7  setz    al
0x1800221aa  or      r10d, 1
0x1800221ae  cmp     r8d, edx
0x1800221b1  mov     [r9+10h], eax
0x1800221b5  mov     eax, edx
0x1800221b7  cmovz   r10d, r8d
0x1800221bb  lock cmpxchg [r11], r10d
0x1800221c0  jz      short loc_1800221C6
0x1800221c2  mov     edx, eax
0x1800221c4  jmp     short loc_180022199
0x1800221c6  test    r10b, 1
0x1800221ca  setnz   cl
0x1800221cd  test    dl, 1
0x1800221d0  setz    al
0x1800221d3  test    al, cl
0x1800221d5  mov     eax, 0
0x1800221da  setnz   al
0x1800221dd  mov     [r9], eax
0x1800221e0  jmp     short loc_1800221FA
0x1800221e2  mov     edx, r8d
0x1800221e5  mov     rcx, r11
0x1800221e8  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800221ed  jmp     short loc_1800221FA
0x1800221ef  mov     edx, r8d
0x1800221f2  mov     rcx, r11
0x1800221f5  call    wil_details_FeatureReporting_IncrementUsageInCache
0x1800221fa  mov     rbx, [rsp+28h+arg_0]
0x1800221ff  mov     rax, r9
0x180022202  add     rsp, 20h
0x180022206  pop     rdi
0x180022207  retn
```
