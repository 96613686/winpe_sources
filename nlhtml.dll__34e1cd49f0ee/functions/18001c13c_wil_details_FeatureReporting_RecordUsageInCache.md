# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18001c13c`
- end: `0x18001c2b3`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001bdcc`

## callees

- `0x18001bf90`
- `0x18001c060`
- `0x18001c13c`

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
0x18001c13c  mov     [rsp+arg_0], rbx
0x18001c141  push    rdi
0x18001c142  sub     rsp, 20h
0x18001c146  xor     eax, eax
0x18001c148  xorps   xmm0, xmm0
0x18001c14b  mov     r10, rdx
0x18001c14e  mov     rbx, rcx
0x18001c151  mov     r9d, r8d
0x18001c154  movups  xmmword ptr [rcx], xmm0
0x18001c157  mov     [rcx+10h], rax
0x18001c15b  test    r8d, r8d
0x18001c15e  jz      loc_18001C297
0x18001c164  sub     r9d, 1
0x18001c168  jz      loc_18001C287
0x18001c16e  sub     r9d, 1
0x18001c172  jz      loc_18001C20F
0x18001c178  sub     r9d, 1
0x18001c17c  jz      loc_18001C20F
0x18001c182  sub     r9d, 1
0x18001c186  jz      loc_18001C297
0x18001c18c  sub     r9d, 1
0x18001c190  jz      loc_18001C287
0x18001c196  sub     r9d, 1
0x18001c19a  jz      short loc_18001C20F
0x18001c19c  cmp     r9d, 1
0x18001c1a0  jz      short loc_18001C20F
0x18001c1a2  lea     r11d, [r8-140h]
0x18001c1a9  lea     r9d, [rax+1]
0x18001c1ad  cmp     r11d, 40h ; '@'
0x18001c1b1  jge     short loc_18001C1FB
0x18001c1b3  mov     eax, [rdx+4]
0x18001c1b6  lea     ecx, [r9+0Fh]
0x18001c1ba  mov     edi, r11d
0x18001c1bd  shl     edi, 5
0x18001c1c0  test    cl, al
0x18001c1c2  jz      short loc_18001C1D6
0x18001c1c4  mov     edx, eax
0x18001c1c6  shr     edx, 5
0x18001c1c9  and     edx, 3Fh
0x18001c1cc  cmp     edx, r11d
0x18001c1cf  jnz     short loc_18001C1D6
0x18001c1d1  mov     edx, r9d
0x18001c1d4  jmp     short loc_18001C1D8
0x18001c1d6  xor     edx, edx
0x18001c1d8  mov     [rbx+10h], edx
0x18001c1db  mov     edx, edi
0x18001c1dd  xor     edx, eax
0x18001c1df  and     edx, 7E0h
0x18001c1e5  xor     edx, eax
0x18001c1e7  or      edx, ecx
0x18001c1e9  lock cmpxchg [r10+4], edx
0x18001c1ef  jnz     short loc_18001C1C0
0x18001c1f1  cmp     dword ptr [rbx+10h], 0
0x18001c1f5  jnz     loc_18001C2A5
0x18001c1fb  mov     [rbx+8], r8d
0x18001c1ff  mov     [rbx+4], r9d
0x18001c203  mov     dword ptr [rbx+0Ch], 0
0x18001c20a  jmp     loc_18001C2A5
0x18001c20f  xor     ecx, ecx
0x18001c211  sub     r8d, 2
0x18001c215  jz      short loc_18001C23D
0x18001c217  sub     r8d, 1
0x18001c21b  jz      short loc_18001C236
0x18001c21d  sub     r8d, 3
0x18001c221  jz      short loc_18001C22F
0x18001c223  cmp     r8d, 1
0x18001c227  jnz     short loc_18001C242
0x18001c229  lea     ecx, [r8+0Fh]
0x18001c22d  jmp     short loc_18001C242
0x18001c22f  mov     ecx, 4
0x18001c234  jmp     short loc_18001C242
0x18001c236  mov     ecx, 8
0x18001c23b  jmp     short loc_18001C242
0x18001c23d  mov     ecx, 2
0x18001c242  mov     edx, [rdx]
0x18001c244  mov     r9d, 1
0x18001c24a  xor     eax, eax
0x18001c24c  mov     r8d, ecx
0x18001c24f  or      r8d, edx
0x18001c252  cmp     r8d, edx
0x18001c255  mov     r11d, r8d
0x18001c258  setz    al
0x18001c25b  or      r11d, r9d
0x18001c25e  cmp     r8d, edx
0x18001c261  mov     [rbx+10h], eax
0x18001c264  mov     eax, edx
0x18001c266  cmovz   r11d, r8d
0x18001c26a  lock cmpxchg [r10], r11d
0x18001c26f  jz      short loc_18001C275
0x18001c271  mov     edx, eax
0x18001c273  jmp     short loc_18001C24A
0x18001c275  test    r9b, r11b
0x18001c278  jz      short loc_18001C27F
0x18001c27a  test    r9b, dl
0x18001c27d  jz      short loc_18001C282
0x18001c27f  xor     r9d, r9d
0x18001c282  mov     [rbx], r9d
0x18001c285  jmp     short loc_18001C2A5
0x18001c287  mov     r9, rbx
0x18001c28a  mov     edx, r8d
0x18001c28d  mov     rcx, r10
0x18001c290  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18001c295  jmp     short loc_18001C2A5
0x18001c297  mov     r9, rbx
0x18001c29a  mov     edx, r8d
0x18001c29d  mov     rcx, r10
0x18001c2a0  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18001c2a5  mov     rax, rbx
0x18001c2a8  mov     rbx, [rsp+28h+arg_0]
0x18001c2ad  add     rsp, 20h
0x18001c2b1  pop     rdi
0x18001c2b2  retn
```
