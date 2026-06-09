# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000ed40`
- end: `0x18000eebc`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ef40`

## callees

- `0x18000eb94`
- `0x18000ec64`
- `0x18000ed40`

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
0x18000ed40  mov     [rsp+arg_0], rbx
0x18000ed45  mov     [rsp+arg_8], rsi
0x18000ed4a  push    rdi
0x18000ed4b  sub     rsp, 20h
0x18000ed4f  xor     eax, eax
0x18000ed51  xorps   xmm0, xmm0
0x18000ed54  mov     esi, r9d
0x18000ed57  mov     r11, rdx
0x18000ed5a  mov     r9, rcx
0x18000ed5d  mov     r10d, r8d
0x18000ed60  movups  xmmword ptr [rcx], xmm0
0x18000ed63  mov     [rcx+10h], rax
0x18000ed67  test    r8d, r8d
0x18000ed6a  jz      loc_18000EE9D
0x18000ed70  sub     r10d, 1
0x18000ed74  jz      loc_18000EE90
0x18000ed7a  sub     r10d, 1
0x18000ed7e  jz      loc_18000EE17
0x18000ed84  sub     r10d, 1
0x18000ed88  jz      loc_18000EE17
0x18000ed8e  sub     r10d, 1
0x18000ed92  jz      loc_18000EE9D
0x18000ed98  sub     r10d, 1
0x18000ed9c  jz      loc_18000EE90
0x18000eda2  sub     r10d, 1
0x18000eda6  jz      short loc_18000EE17
0x18000eda8  cmp     r10d, 1
0x18000edac  jz      short loc_18000EE17
0x18000edae  lea     ebx, [r8-140h]
0x18000edb5  lea     r10d, [rax+1]
0x18000edb9  cmp     ebx, 40h ; '@'
0x18000edbc  jge     short loc_18000EE06
0x18000edbe  mov     eax, [rdx+4]
0x18000edc1  lea     ecx, [r10+0Fh]
0x18000edc5  mov     edi, ebx
0x18000edc7  shl     edi, 5
0x18000edca  test    cl, al
0x18000edcc  jz      short loc_18000EDDF
0x18000edce  mov     edx, eax
0x18000edd0  shr     edx, 5
0x18000edd3  and     edx, 3Fh
0x18000edd6  cmp     edx, ebx
0x18000edd8  jnz     short loc_18000EDDF
0x18000edda  mov     edx, r10d
0x18000eddd  jmp     short loc_18000EDE1
0x18000eddf  xor     edx, edx
0x18000ede1  mov     [r9+10h], edx
0x18000ede5  mov     edx, edi
0x18000ede7  xor     edx, eax
0x18000ede9  and     edx, 7E0h
0x18000edef  xor     edx, eax
0x18000edf1  or      edx, ecx
0x18000edf3  lock cmpxchg [r11+4], edx
0x18000edf9  jnz     short loc_18000EDCA
0x18000edfb  cmp     dword ptr [r9+10h], 0
0x18000ee00  jnz     loc_18000EEA8
0x18000ee06  mov     [r9+8], r8d
0x18000ee0a  mov     [r9+4], r10d
0x18000ee0e  mov     [r9+0Ch], esi
0x18000ee12  jmp     loc_18000EEA8
0x18000ee17  xor     ecx, ecx
0x18000ee19  sub     r8d, 2
0x18000ee1d  jz      short loc_18000EE45
0x18000ee1f  sub     r8d, 1
0x18000ee23  jz      short loc_18000EE3E
0x18000ee25  sub     r8d, 3
0x18000ee29  jz      short loc_18000EE37
0x18000ee2b  cmp     r8d, 1
0x18000ee2f  jnz     short loc_18000EE4A
0x18000ee31  lea     ecx, [r8+0Fh]
0x18000ee35  jmp     short loc_18000EE4A
0x18000ee37  mov     ecx, 4
0x18000ee3c  jmp     short loc_18000EE4A
0x18000ee3e  mov     ecx, 8
0x18000ee43  jmp     short loc_18000EE4A
0x18000ee45  mov     ecx, 2
0x18000ee4a  mov     edx, [rdx]
0x18000ee4c  mov     r10d, 1
0x18000ee52  xor     eax, eax
0x18000ee54  mov     r8d, ecx
0x18000ee57  or      r8d, edx
0x18000ee5a  cmp     r8d, edx
0x18000ee5d  mov     ebx, r8d
0x18000ee60  setz    al
0x18000ee63  or      ebx, r10d
0x18000ee66  cmp     r8d, edx
0x18000ee69  mov     [r9+10h], eax
0x18000ee6d  mov     eax, edx
0x18000ee6f  cmovz   ebx, r8d
0x18000ee73  lock cmpxchg [r11], ebx
0x18000ee78  jz      short loc_18000EE7E
0x18000ee7a  mov     edx, eax
0x18000ee7c  jmp     short loc_18000EE52
0x18000ee7e  test    r10b, bl
0x18000ee81  jz      short loc_18000EE88
0x18000ee83  test    r10b, dl
0x18000ee86  jz      short loc_18000EE8B
0x18000ee88  xor     r10d, r10d
0x18000ee8b  mov     [r9], r10d
0x18000ee8e  jmp     short loc_18000EEA8
0x18000ee90  mov     edx, r8d
0x18000ee93  mov     rcx, r11
0x18000ee96  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000ee9b  jmp     short loc_18000EEA8
0x18000ee9d  mov     edx, r8d
0x18000eea0  mov     rcx, r11
0x18000eea3  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000eea8  mov     rbx, [rsp+28h+arg_0]
0x18000eead  mov     rax, r9
0x18000eeb0  mov     rsi, [rsp+28h+arg_8]
0x18000eeb5  add     rsp, 20h
0x18000eeb9  pop     rdi
0x18000eeba  retn
```
