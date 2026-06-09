# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180008798`
- end: `0x180008914`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008a48`

## callees

- `0x1800085ec`
- `0x1800086bc`
- `0x180008798`

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
0x180008798  mov     [rsp+arg_0], rbx
0x18000879d  push    rdi
0x18000879e  sub     rsp, 20h
0x1800087a2  xor     eax, eax
0x1800087a4  xorps   xmm0, xmm0
0x1800087a7  mov     edi, r9d
0x1800087aa  mov     r11, rdx
0x1800087ad  mov     r9, rcx
0x1800087b0  mov     r10d, r8d
0x1800087b3  movups  xmmword ptr [rcx], xmm0
0x1800087b6  mov     [rcx+10h], rax
0x1800087ba  test    r8d, r8d
0x1800087bd  jz      loc_1800088FB
0x1800087c3  sub     r10d, 1
0x1800087c7  jz      loc_1800088EE
0x1800087cd  sub     r10d, 1
0x1800087d1  jz      loc_180008870
0x1800087d7  sub     r10d, 1
0x1800087db  jz      loc_180008870
0x1800087e1  sub     r10d, 1
0x1800087e5  jz      loc_1800088FB
0x1800087eb  sub     r10d, 1
0x1800087ef  jz      loc_1800088EE
0x1800087f5  sub     r10d, 1
0x1800087f9  jz      short loc_180008870
0x1800087fb  cmp     r10d, 1
0x1800087ff  jz      short loc_180008870
0x180008801  lea     r10d, [r8-140h]
0x180008808  cmp     r10d, 40h ; '@'
0x18000880c  jge     short loc_18000885B
0x18000880e  mov     eax, [rdx+4]
0x180008811  mov     ebx, r10d
0x180008814  shl     ebx, 5
0x180008817  mov     ecx, 10h
0x18000881c  test    cl, al
0x18000881e  jz      short loc_180008834
0x180008820  mov     edx, eax
0x180008822  shr     edx, 5
0x180008825  and     edx, 3Fh
0x180008828  cmp     edx, r10d
0x18000882b  jnz     short loc_180008834
0x18000882d  mov     edx, 1
0x180008832  jmp     short loc_180008836
0x180008834  xor     edx, edx
0x180008836  mov     [r9+10h], edx
0x18000883a  mov     edx, ebx
0x18000883c  xor     edx, eax
0x18000883e  and     edx, 7E0h
0x180008844  xor     edx, eax
0x180008846  or      edx, ecx
0x180008848  lock cmpxchg [r11+4], edx
0x18000884e  jnz     short loc_18000881C
0x180008850  cmp     dword ptr [r9+10h], 0
0x180008855  jnz     loc_180008906
0x18000885b  mov     [r9+8], r8d
0x18000885f  mov     dword ptr [r9+4], 1
0x180008867  mov     [r9+0Ch], edi
0x18000886b  jmp     loc_180008906
0x180008870  xor     ecx, ecx
0x180008872  sub     r8d, 2
0x180008876  jz      short loc_18000889E
0x180008878  sub     r8d, 1
0x18000887c  jz      short loc_180008897
0x18000887e  sub     r8d, 3
0x180008882  jz      short loc_180008890
0x180008884  cmp     r8d, 1
0x180008888  jnz     short loc_1800088A3
0x18000888a  lea     ecx, [r8+0Fh]
0x18000888e  jmp     short loc_1800088A3
0x180008890  mov     ecx, 4
0x180008895  jmp     short loc_1800088A3
0x180008897  mov     ecx, 8
0x18000889c  jmp     short loc_1800088A3
0x18000889e  mov     ecx, 2
0x1800088a3  mov     edx, [rdx]
0x1800088a5  xor     eax, eax
0x1800088a7  mov     r8d, ecx
0x1800088aa  or      r8d, edx
0x1800088ad  cmp     r8d, edx
0x1800088b0  mov     r10d, r8d
0x1800088b3  setz    al
0x1800088b6  or      r10d, 1
0x1800088ba  cmp     r8d, edx
0x1800088bd  mov     [r9+10h], eax
0x1800088c1  mov     eax, edx
0x1800088c3  cmovz   r10d, r8d
0x1800088c7  lock cmpxchg [r11], r10d
0x1800088cc  jz      short loc_1800088D2
0x1800088ce  mov     edx, eax
0x1800088d0  jmp     short loc_1800088A5
0x1800088d2  test    r10b, 1
0x1800088d6  setnz   cl
0x1800088d9  test    dl, 1
0x1800088dc  setz    al
0x1800088df  test    al, cl
0x1800088e1  mov     eax, 0
0x1800088e6  setnz   al
0x1800088e9  mov     [r9], eax
0x1800088ec  jmp     short loc_180008906
0x1800088ee  mov     edx, r8d
0x1800088f1  mov     rcx, r11
0x1800088f4  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x1800088f9  jmp     short loc_180008906
0x1800088fb  mov     edx, r8d
0x1800088fe  mov     rcx, r11
0x180008901  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180008906  mov     rbx, [rsp+28h+arg_0]
0x18000890b  mov     rax, r9
0x18000890e  add     rsp, 20h
0x180008912  pop     rdi
0x180008913  retn
```
