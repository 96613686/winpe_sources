# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000ade8`
- end: `0x14000af64`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000afe8`

## callees

- `0x14000ac3c`
- `0x14000ad0c`
- `0x14000ade8`

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
0x14000ade8  mov     [rsp+arg_0], rbx
0x14000aded  mov     [rsp+arg_8], rsi
0x14000adf2  push    rdi
0x14000adf3  sub     rsp, 20h
0x14000adf7  xor     eax, eax
0x14000adf9  xorps   xmm0, xmm0
0x14000adfc  mov     esi, r9d
0x14000adff  mov     r11, rdx
0x14000ae02  mov     r9, rcx
0x14000ae05  mov     r10d, r8d
0x14000ae08  movups  xmmword ptr [rcx], xmm0
0x14000ae0b  mov     [rcx+10h], rax
0x14000ae0f  test    r8d, r8d
0x14000ae12  jz      loc_14000AF45
0x14000ae18  sub     r10d, 1
0x14000ae1c  jz      loc_14000AF38
0x14000ae22  sub     r10d, 1
0x14000ae26  jz      loc_14000AEBF
0x14000ae2c  sub     r10d, 1
0x14000ae30  jz      loc_14000AEBF
0x14000ae36  sub     r10d, 1
0x14000ae3a  jz      loc_14000AF45
0x14000ae40  sub     r10d, 1
0x14000ae44  jz      loc_14000AF38
0x14000ae4a  sub     r10d, 1
0x14000ae4e  jz      short loc_14000AEBF
0x14000ae50  cmp     r10d, 1
0x14000ae54  jz      short loc_14000AEBF
0x14000ae56  lea     ebx, [r8-140h]
0x14000ae5d  lea     r10d, [rax+1]
0x14000ae61  cmp     ebx, 40h ; '@'
0x14000ae64  jge     short loc_14000AEAE
0x14000ae66  mov     eax, [rdx+4]
0x14000ae69  lea     ecx, [r10+0Fh]
0x14000ae6d  mov     edi, ebx
0x14000ae6f  shl     edi, 5
0x14000ae72  test    cl, al
0x14000ae74  jz      short loc_14000AE87
0x14000ae76  mov     edx, eax
0x14000ae78  shr     edx, 5
0x14000ae7b  and     edx, 3Fh
0x14000ae7e  cmp     edx, ebx
0x14000ae80  jnz     short loc_14000AE87
0x14000ae82  mov     edx, r10d
0x14000ae85  jmp     short loc_14000AE89
0x14000ae87  xor     edx, edx
0x14000ae89  mov     [r9+10h], edx
0x14000ae8d  mov     edx, edi
0x14000ae8f  xor     edx, eax
0x14000ae91  and     edx, 7E0h
0x14000ae97  xor     edx, eax
0x14000ae99  or      edx, ecx
0x14000ae9b  lock cmpxchg [r11+4], edx
0x14000aea1  jnz     short loc_14000AE72
0x14000aea3  cmp     dword ptr [r9+10h], 0
0x14000aea8  jnz     loc_14000AF50
0x14000aeae  mov     [r9+8], r8d
0x14000aeb2  mov     [r9+4], r10d
0x14000aeb6  mov     [r9+0Ch], esi
0x14000aeba  jmp     loc_14000AF50
0x14000aebf  xor     ecx, ecx
0x14000aec1  sub     r8d, 2
0x14000aec5  jz      short loc_14000AEED
0x14000aec7  sub     r8d, 1
0x14000aecb  jz      short loc_14000AEE6
0x14000aecd  sub     r8d, 3
0x14000aed1  jz      short loc_14000AEDF
0x14000aed3  cmp     r8d, 1
0x14000aed7  jnz     short loc_14000AEF2
0x14000aed9  lea     ecx, [r8+0Fh]
0x14000aedd  jmp     short loc_14000AEF2
0x14000aedf  mov     ecx, 4
0x14000aee4  jmp     short loc_14000AEF2
0x14000aee6  mov     ecx, 8
0x14000aeeb  jmp     short loc_14000AEF2
0x14000aeed  mov     ecx, 2
0x14000aef2  mov     edx, [rdx]
0x14000aef4  mov     r10d, 1
0x14000aefa  xor     eax, eax
0x14000aefc  mov     r8d, ecx
0x14000aeff  or      r8d, edx
0x14000af02  cmp     r8d, edx
0x14000af05  mov     ebx, r8d
0x14000af08  setz    al
0x14000af0b  or      ebx, r10d
0x14000af0e  cmp     r8d, edx
0x14000af11  mov     [r9+10h], eax
0x14000af15  mov     eax, edx
0x14000af17  cmovz   ebx, r8d
0x14000af1b  lock cmpxchg [r11], ebx
0x14000af20  jz      short loc_14000AF26
0x14000af22  mov     edx, eax
0x14000af24  jmp     short loc_14000AEFA
0x14000af26  test    r10b, bl
0x14000af29  jz      short loc_14000AF30
0x14000af2b  test    r10b, dl
0x14000af2e  jz      short loc_14000AF33
0x14000af30  xor     r10d, r10d
0x14000af33  mov     [r9], r10d
0x14000af36  jmp     short loc_14000AF50
0x14000af38  mov     edx, r8d
0x14000af3b  mov     rcx, r11
0x14000af3e  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14000af43  jmp     short loc_14000AF50
0x14000af45  mov     edx, r8d
0x14000af48  mov     rcx, r11
0x14000af4b  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14000af50  mov     rbx, [rsp+28h+arg_0]
0x14000af55  mov     rax, r9
0x14000af58  mov     rsi, [rsp+28h+arg_8]
0x14000af5d  add     rsp, 20h
0x14000af61  pop     rdi
0x14000af62  retn
```
