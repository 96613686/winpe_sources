# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x1400060e4`
- end: `0x140006260`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400062e4`

## callees

- `0x140005f38`
- `0x140006008`
- `0x1400060e4`

## pseudocode

```c
int *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        unsigned int a3,
        int a4)
{
  int *v6; // r9
  unsigned int v7; // ebx
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  unsigned int v12; // r8d
  unsigned int v13; // r8d
  unsigned int v14; // r8d
  signed __int32 v15; // edx
  int v16; // r10d
  signed __int32 v17; // ebx
  signed __int32 v18; // eax

  v6 = (int *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0u:
      goto LABEL_35;
    case 1u:
LABEL_34:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3);
      return v6;
    case 2u:
    case 3u:
      goto LABEL_17;
    case 4u:
LABEL_35:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3);
      return v6;
    case 5u:
      goto LABEL_34;
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
  v15 = *a2;
  v16 = 1;
  while ( 1 )
  {
    v17 = v15 | v11 | 1;
    v6[4] = (v15 | v11) == v15;
    if ( (v15 | v11) == v15 )
      v17 = v15 | v11;
    v18 = _InterlockedCompareExchange(a2, v17, v15);
    if ( v15 == v18 )
      break;
    v15 = v18;
  }
  if ( (v17 & 1) == 0 || (v15 & 1) != 0 )
    v16 = 0;
  *v6 = v16;
  return v6;
}

```

## disassembly

```asm
0x1400060e4  mov     [rsp+arg_0], rbx
0x1400060e9  mov     [rsp+arg_8], rsi
0x1400060ee  push    rdi
0x1400060ef  sub     rsp, 20h
0x1400060f3  xor     eax, eax
0x1400060f5  xorps   xmm0, xmm0
0x1400060f8  mov     esi, r9d
0x1400060fb  mov     r11, rdx
0x1400060fe  mov     r9, rcx
0x140006101  mov     r10d, r8d
0x140006104  movups  xmmword ptr [rcx], xmm0
0x140006107  mov     [rcx+10h], rax
0x14000610b  test    r8d, r8d
0x14000610e  jz      loc_140006241
0x140006114  sub     r10d, 1
0x140006118  jz      loc_140006234
0x14000611e  sub     r10d, 1
0x140006122  jz      loc_1400061BB
0x140006128  sub     r10d, 1
0x14000612c  jz      loc_1400061BB
0x140006132  sub     r10d, 1
0x140006136  jz      loc_140006241
0x14000613c  sub     r10d, 1
0x140006140  jz      loc_140006234
0x140006146  sub     r10d, 1
0x14000614a  jz      short loc_1400061BB
0x14000614c  cmp     r10d, 1
0x140006150  jz      short loc_1400061BB
0x140006152  lea     ebx, [r8-140h]
0x140006159  lea     r10d, [rax+1]
0x14000615d  cmp     ebx, 40h ; '@'
0x140006160  jge     short loc_1400061AA
0x140006162  mov     eax, [rdx+4]
0x140006165  lea     ecx, [r10+0Fh]
0x140006169  mov     edi, ebx
0x14000616b  shl     edi, 5
0x14000616e  test    cl, al
0x140006170  jz      short loc_140006183
0x140006172  mov     edx, eax
0x140006174  shr     edx, 5
0x140006177  and     edx, 3Fh
0x14000617a  cmp     edx, ebx
0x14000617c  jnz     short loc_140006183
0x14000617e  mov     edx, r10d
0x140006181  jmp     short loc_140006185
0x140006183  xor     edx, edx
0x140006185  mov     [r9+10h], edx
0x140006189  mov     edx, edi
0x14000618b  xor     edx, eax
0x14000618d  and     edx, 7E0h
0x140006193  xor     edx, eax
0x140006195  or      edx, ecx
0x140006197  lock cmpxchg [r11+4], edx
0x14000619d  jnz     short loc_14000616E
0x14000619f  cmp     dword ptr [r9+10h], 0
0x1400061a4  jnz     loc_14000624C
0x1400061aa  mov     [r9+8], r8d
0x1400061ae  mov     [r9+4], r10d
0x1400061b2  mov     [r9+0Ch], esi
0x1400061b6  jmp     loc_14000624C
0x1400061bb  xor     ecx, ecx
0x1400061bd  sub     r8d, 2
0x1400061c1  jz      short loc_1400061E9
0x1400061c3  sub     r8d, 1
0x1400061c7  jz      short loc_1400061E2
0x1400061c9  sub     r8d, 3
0x1400061cd  jz      short loc_1400061DB
0x1400061cf  cmp     r8d, 1
0x1400061d3  jnz     short loc_1400061EE
0x1400061d5  lea     ecx, [r8+0Fh]
0x1400061d9  jmp     short loc_1400061EE
0x1400061db  mov     ecx, 4
0x1400061e0  jmp     short loc_1400061EE
0x1400061e2  mov     ecx, 8
0x1400061e7  jmp     short loc_1400061EE
0x1400061e9  mov     ecx, 2
0x1400061ee  mov     edx, [rdx]
0x1400061f0  mov     r10d, 1
0x1400061f6  xor     eax, eax
0x1400061f8  mov     r8d, ecx
0x1400061fb  or      r8d, edx
0x1400061fe  cmp     r8d, edx
0x140006201  mov     ebx, r8d
0x140006204  setz    al
0x140006207  or      ebx, r10d
0x14000620a  cmp     r8d, edx
0x14000620d  mov     [r9+10h], eax
0x140006211  mov     eax, edx
0x140006213  cmovz   ebx, r8d
0x140006217  lock cmpxchg [r11], ebx
0x14000621c  jz      short loc_140006222
0x14000621e  mov     edx, eax
0x140006220  jmp     short loc_1400061F6
0x140006222  test    r10b, bl
0x140006225  jz      short loc_14000622C
0x140006227  test    r10b, dl
0x14000622a  jz      short loc_14000622F
0x14000622c  xor     r10d, r10d
0x14000622f  mov     [r9], r10d
0x140006232  jmp     short loc_14000624C
0x140006234  mov     edx, r8d
0x140006237  mov     rcx, r11
0x14000623a  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14000623f  jmp     short loc_14000624C
0x140006241  mov     edx, r8d
0x140006244  mov     rcx, r11
0x140006247  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14000624c  mov     rbx, [rsp+28h+arg_0]
0x140006251  mov     rax, r9
0x140006254  mov     rsi, [rsp+28h+arg_8]
0x140006259  add     rsp, 20h
0x14000625d  pop     rdi
0x14000625e  retn
```
