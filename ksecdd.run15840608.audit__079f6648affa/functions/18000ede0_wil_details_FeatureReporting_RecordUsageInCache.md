# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18000ede0`
- end: `0x18000ef5c`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000efe0`

## callees

- `0x18000ec34`
- `0x18000ed04`
- `0x18000ede0`

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
0x18000ede0  mov     [rsp+arg_0], rbx
0x18000ede5  mov     [rsp+arg_8], rsi
0x18000edea  push    rdi
0x18000edeb  sub     rsp, 20h
0x18000edef  xor     eax, eax
0x18000edf1  xorps   xmm0, xmm0
0x18000edf4  mov     esi, r9d
0x18000edf7  mov     r11, rdx
0x18000edfa  mov     r9, rcx
0x18000edfd  mov     r10d, r8d
0x18000ee00  movups  xmmword ptr [rcx], xmm0
0x18000ee03  mov     [rcx+10h], rax
0x18000ee07  test    r8d, r8d
0x18000ee0a  jz      loc_18000EF3D
0x18000ee10  sub     r10d, 1
0x18000ee14  jz      loc_18000EF30
0x18000ee1a  sub     r10d, 1
0x18000ee1e  jz      loc_18000EEB7
0x18000ee24  sub     r10d, 1
0x18000ee28  jz      loc_18000EEB7
0x18000ee2e  sub     r10d, 1
0x18000ee32  jz      loc_18000EF3D
0x18000ee38  sub     r10d, 1
0x18000ee3c  jz      loc_18000EF30
0x18000ee42  sub     r10d, 1
0x18000ee46  jz      short loc_18000EEB7
0x18000ee48  cmp     r10d, 1
0x18000ee4c  jz      short loc_18000EEB7
0x18000ee4e  lea     ebx, [r8-140h]
0x18000ee55  lea     r10d, [rax+1]
0x18000ee59  cmp     ebx, 40h ; '@'
0x18000ee5c  jge     short loc_18000EEA6
0x18000ee5e  mov     eax, [rdx+4]
0x18000ee61  lea     ecx, [r10+0Fh]
0x18000ee65  mov     edi, ebx
0x18000ee67  shl     edi, 5
0x18000ee6a  test    cl, al
0x18000ee6c  jz      short loc_18000EE7F
0x18000ee6e  mov     edx, eax
0x18000ee70  shr     edx, 5
0x18000ee73  and     edx, 3Fh
0x18000ee76  cmp     edx, ebx
0x18000ee78  jnz     short loc_18000EE7F
0x18000ee7a  mov     edx, r10d
0x18000ee7d  jmp     short loc_18000EE81
0x18000ee7f  xor     edx, edx
0x18000ee81  mov     [r9+10h], edx
0x18000ee85  mov     edx, edi
0x18000ee87  xor     edx, eax
0x18000ee89  and     edx, 7E0h
0x18000ee8f  xor     edx, eax
0x18000ee91  or      edx, ecx
0x18000ee93  lock cmpxchg [r11+4], edx
0x18000ee99  jnz     short loc_18000EE6A
0x18000ee9b  cmp     dword ptr [r9+10h], 0
0x18000eea0  jnz     loc_18000EF48
0x18000eea6  mov     [r9+8], r8d
0x18000eeaa  mov     [r9+4], r10d
0x18000eeae  mov     [r9+0Ch], esi
0x18000eeb2  jmp     loc_18000EF48
0x18000eeb7  xor     ecx, ecx
0x18000eeb9  sub     r8d, 2
0x18000eebd  jz      short loc_18000EEE5
0x18000eebf  sub     r8d, 1
0x18000eec3  jz      short loc_18000EEDE
0x18000eec5  sub     r8d, 3
0x18000eec9  jz      short loc_18000EED7
0x18000eecb  cmp     r8d, 1
0x18000eecf  jnz     short loc_18000EEEA
0x18000eed1  lea     ecx, [r8+0Fh]
0x18000eed5  jmp     short loc_18000EEEA
0x18000eed7  mov     ecx, 4
0x18000eedc  jmp     short loc_18000EEEA
0x18000eede  mov     ecx, 8
0x18000eee3  jmp     short loc_18000EEEA
0x18000eee5  mov     ecx, 2
0x18000eeea  mov     edx, [rdx]
0x18000eeec  mov     r10d, 1
0x18000eef2  xor     eax, eax
0x18000eef4  mov     r8d, ecx
0x18000eef7  or      r8d, edx
0x18000eefa  cmp     r8d, edx
0x18000eefd  mov     ebx, r8d
0x18000ef00  setz    al
0x18000ef03  or      ebx, r10d
0x18000ef06  cmp     r8d, edx
0x18000ef09  mov     [r9+10h], eax
0x18000ef0d  mov     eax, edx
0x18000ef0f  cmovz   ebx, r8d
0x18000ef13  lock cmpxchg [r11], ebx
0x18000ef18  jz      short loc_18000EF1E
0x18000ef1a  mov     edx, eax
0x18000ef1c  jmp     short loc_18000EEF2
0x18000ef1e  test    r10b, bl
0x18000ef21  jz      short loc_18000EF28
0x18000ef23  test    r10b, dl
0x18000ef26  jz      short loc_18000EF2B
0x18000ef28  xor     r10d, r10d
0x18000ef2b  mov     [r9], r10d
0x18000ef2e  jmp     short loc_18000EF48
0x18000ef30  mov     edx, r8d
0x18000ef33  mov     rcx, r11
0x18000ef36  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18000ef3b  jmp     short loc_18000EF48
0x18000ef3d  mov     edx, r8d
0x18000ef40  mov     rcx, r11
0x18000ef43  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18000ef48  mov     rbx, [rsp+28h+arg_0]
0x18000ef4d  mov     rax, r9
0x18000ef50  mov     rsi, [rsp+28h+arg_8]
0x18000ef55  add     rsp, 20h
0x18000ef59  pop     rdi
0x18000ef5a  retn
```
