# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001b338`
- end: `0x18001b4af`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019e8c`

## callees

- `0x18001b18c`
- `0x18001b25c`
- `0x18001b338`

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
0x18001b338  mov     [rsp+arg_0], rbx
0x18001b33d  push    rdi
0x18001b33e  sub     rsp, 20h
0x18001b342  xor     eax, eax
0x18001b344  xorps   xmm0, xmm0
0x18001b347  mov     r10, rdx
0x18001b34a  mov     rbx, rcx
0x18001b34d  mov     r9d, r8d
0x18001b350  movups  xmmword ptr [rcx], xmm0
0x18001b353  mov     [rcx+10h], rax
0x18001b357  test    r8d, r8d
0x18001b35a  jz      loc_18001B493
0x18001b360  sub     r9d, 1
0x18001b364  jz      loc_18001B483
0x18001b36a  sub     r9d, 1
0x18001b36e  jz      loc_18001B40B
0x18001b374  sub     r9d, 1
0x18001b378  jz      loc_18001B40B
0x18001b37e  sub     r9d, 1
0x18001b382  jz      loc_18001B493
0x18001b388  sub     r9d, 1
0x18001b38c  jz      loc_18001B483
0x18001b392  sub     r9d, 1
0x18001b396  jz      short loc_18001B40B
0x18001b398  cmp     r9d, 1
0x18001b39c  jz      short loc_18001B40B
0x18001b39e  lea     r11d, [r8-140h]
0x18001b3a5  lea     r9d, [rax+1]
0x18001b3a9  cmp     r11d, 40h ; '@'
0x18001b3ad  jge     short loc_18001B3F7
0x18001b3af  mov     eax, [rdx+4]
0x18001b3b2  lea     ecx, [r9+0Fh]
0x18001b3b6  mov     edi, r11d
0x18001b3b9  shl     edi, 5
0x18001b3bc  test    cl, al
0x18001b3be  jz      short loc_18001B3D2
0x18001b3c0  mov     edx, eax
0x18001b3c2  shr     edx, 5
0x18001b3c5  and     edx, 3Fh
0x18001b3c8  cmp     edx, r11d
0x18001b3cb  jnz     short loc_18001B3D2
0x18001b3cd  mov     edx, r9d
0x18001b3d0  jmp     short loc_18001B3D4
0x18001b3d2  xor     edx, edx
0x18001b3d4  mov     [rbx+10h], edx
0x18001b3d7  mov     edx, edi
0x18001b3d9  xor     edx, eax
0x18001b3db  and     edx, 7E0h
0x18001b3e1  xor     edx, eax
0x18001b3e3  or      edx, ecx
0x18001b3e5  lock cmpxchg [r10+4], edx
0x18001b3eb  jnz     short loc_18001B3BC
0x18001b3ed  cmp     dword ptr [rbx+10h], 0
0x18001b3f1  jnz     loc_18001B4A1
0x18001b3f7  mov     [rbx+8], r8d
0x18001b3fb  mov     [rbx+4], r9d
0x18001b3ff  mov     dword ptr [rbx+0Ch], 0
0x18001b406  jmp     loc_18001B4A1
0x18001b40b  xor     ecx, ecx
0x18001b40d  sub     r8d, 2
0x18001b411  jz      short loc_18001B439
0x18001b413  sub     r8d, 1
0x18001b417  jz      short loc_18001B432
0x18001b419  sub     r8d, 3
0x18001b41d  jz      short loc_18001B42B
0x18001b41f  cmp     r8d, 1
0x18001b423  jnz     short loc_18001B43E
0x18001b425  lea     ecx, [r8+0Fh]
0x18001b429  jmp     short loc_18001B43E
0x18001b42b  mov     ecx, 4
0x18001b430  jmp     short loc_18001B43E
0x18001b432  mov     ecx, 8
0x18001b437  jmp     short loc_18001B43E
0x18001b439  mov     ecx, 2
0x18001b43e  mov     edx, [rdx]
0x18001b440  mov     r9d, 1
0x18001b446  xor     eax, eax
0x18001b448  mov     r8d, ecx
0x18001b44b  or      r8d, edx
0x18001b44e  cmp     r8d, edx
0x18001b451  mov     r11d, r8d
0x18001b454  setz    al
0x18001b457  or      r11d, r9d
0x18001b45a  cmp     r8d, edx
0x18001b45d  mov     [rbx+10h], eax
0x18001b460  mov     eax, edx
0x18001b462  cmovz   r11d, r8d
0x18001b466  lock cmpxchg [r10], r11d
0x18001b46b  jz      short loc_18001B471
0x18001b46d  mov     edx, eax
0x18001b46f  jmp     short loc_18001B446
0x18001b471  test    r9b, r11b
0x18001b474  jz      short loc_18001B47B
0x18001b476  test    r9b, dl
0x18001b479  jz      short loc_18001B47E
0x18001b47b  xor     r9d, r9d
0x18001b47e  mov     [rbx], r9d
0x18001b481  jmp     short loc_18001B4A1
0x18001b483  mov     r9, rbx
0x18001b486  mov     edx, r8d
0x18001b489  mov     rcx, r10
0x18001b48c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18001b491  jmp     short loc_18001B4A1
0x18001b493  mov     r9, rbx
0x18001b496  mov     edx, r8d
0x18001b499  mov     rcx, r10
0x18001b49c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18001b4a1  mov     rax, rbx
0x18001b4a4  mov     rbx, [rsp+28h+arg_0]
0x18001b4a9  add     rsp, 20h
0x18001b4ad  pop     rdi
0x18001b4ae  retn
```
