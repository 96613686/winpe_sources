# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14002b334`
- end: `0x14002b4b0`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002b540`

## callees

- `0x14002b188`
- `0x14002b258`
- `0x14002b334`

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
0x14002b334  mov     [rsp+arg_0], rbx
0x14002b339  mov     [rsp+arg_8], rsi
0x14002b33e  push    rdi
0x14002b33f  sub     rsp, 20h
0x14002b343  xor     eax, eax
0x14002b345  xorps   xmm0, xmm0
0x14002b348  mov     esi, r9d
0x14002b34b  mov     r11, rdx
0x14002b34e  mov     r9, rcx
0x14002b351  mov     r10d, r8d
0x14002b354  movups  xmmword ptr [rcx], xmm0
0x14002b357  mov     [rcx+10h], rax
0x14002b35b  test    r8d, r8d
0x14002b35e  jz      loc_14002B491
0x14002b364  sub     r10d, 1
0x14002b368  jz      loc_14002B484
0x14002b36e  sub     r10d, 1
0x14002b372  jz      loc_14002B40B
0x14002b378  sub     r10d, 1
0x14002b37c  jz      loc_14002B40B
0x14002b382  sub     r10d, 1
0x14002b386  jz      loc_14002B491
0x14002b38c  sub     r10d, 1
0x14002b390  jz      loc_14002B484
0x14002b396  sub     r10d, 1
0x14002b39a  jz      short loc_14002B40B
0x14002b39c  cmp     r10d, 1
0x14002b3a0  jz      short loc_14002B40B
0x14002b3a2  lea     ebx, [r8-140h]
0x14002b3a9  lea     r10d, [rax+1]
0x14002b3ad  cmp     ebx, 40h ; '@'
0x14002b3b0  jge     short loc_14002B3FA
0x14002b3b2  mov     eax, [rdx+4]
0x14002b3b5  lea     ecx, [r10+0Fh]
0x14002b3b9  mov     edi, ebx
0x14002b3bb  shl     edi, 5
0x14002b3be  test    cl, al
0x14002b3c0  jz      short loc_14002B3D3
0x14002b3c2  mov     edx, eax
0x14002b3c4  shr     edx, 5
0x14002b3c7  and     edx, 3Fh
0x14002b3ca  cmp     edx, ebx
0x14002b3cc  jnz     short loc_14002B3D3
0x14002b3ce  mov     edx, r10d
0x14002b3d1  jmp     short loc_14002B3D5
0x14002b3d3  xor     edx, edx
0x14002b3d5  mov     [r9+10h], edx
0x14002b3d9  mov     edx, edi
0x14002b3db  xor     edx, eax
0x14002b3dd  and     edx, 7E0h
0x14002b3e3  xor     edx, eax
0x14002b3e5  or      edx, ecx
0x14002b3e7  lock cmpxchg [r11+4], edx
0x14002b3ed  jnz     short loc_14002B3BE
0x14002b3ef  cmp     dword ptr [r9+10h], 0
0x14002b3f4  jnz     loc_14002B49C
0x14002b3fa  mov     [r9+8], r8d
0x14002b3fe  mov     [r9+4], r10d
0x14002b402  mov     [r9+0Ch], esi
0x14002b406  jmp     loc_14002B49C
0x14002b40b  xor     ecx, ecx
0x14002b40d  sub     r8d, 2
0x14002b411  jz      short loc_14002B439
0x14002b413  sub     r8d, 1
0x14002b417  jz      short loc_14002B432
0x14002b419  sub     r8d, 3
0x14002b41d  jz      short loc_14002B42B
0x14002b41f  cmp     r8d, 1
0x14002b423  jnz     short loc_14002B43E
0x14002b425  lea     ecx, [r8+0Fh]
0x14002b429  jmp     short loc_14002B43E
0x14002b42b  mov     ecx, 4
0x14002b430  jmp     short loc_14002B43E
0x14002b432  mov     ecx, 8
0x14002b437  jmp     short loc_14002B43E
0x14002b439  mov     ecx, 2
0x14002b43e  mov     edx, [rdx]
0x14002b440  mov     r10d, 1
0x14002b446  xor     eax, eax
0x14002b448  mov     r8d, ecx
0x14002b44b  or      r8d, edx
0x14002b44e  cmp     r8d, edx
0x14002b451  mov     ebx, r8d
0x14002b454  setz    al
0x14002b457  or      ebx, r10d
0x14002b45a  cmp     r8d, edx
0x14002b45d  mov     [r9+10h], eax
0x14002b461  mov     eax, edx
0x14002b463  cmovz   ebx, r8d
0x14002b467  lock cmpxchg [r11], ebx
0x14002b46c  jz      short loc_14002B472
0x14002b46e  mov     edx, eax
0x14002b470  jmp     short loc_14002B446
0x14002b472  test    r10b, bl
0x14002b475  jz      short loc_14002B47C
0x14002b477  test    r10b, dl
0x14002b47a  jz      short loc_14002B47F
0x14002b47c  xor     r10d, r10d
0x14002b47f  mov     [r9], r10d
0x14002b482  jmp     short loc_14002B49C
0x14002b484  mov     edx, r8d
0x14002b487  mov     rcx, r11
0x14002b48a  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14002b48f  jmp     short loc_14002B49C
0x14002b491  mov     edx, r8d
0x14002b494  mov     rcx, r11
0x14002b497  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14002b49c  mov     rbx, [rsp+28h+arg_0]
0x14002b4a1  mov     rax, r9
0x14002b4a4  mov     rsi, [rsp+28h+arg_8]
0x14002b4a9  add     rsp, 20h
0x14002b4ad  pop     rdi
0x14002b4ae  retn
```
