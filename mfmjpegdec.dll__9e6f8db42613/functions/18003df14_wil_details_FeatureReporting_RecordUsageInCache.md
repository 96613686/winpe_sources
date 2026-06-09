# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x18003df14`
- end: `0x18003e08a`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `374`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003d114`

## callees

- `0x18003dd68`
- `0x18003de38`
- `0x18003df14`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(__int64 a1, volatile signed __int32 *a2, __int64 a3)
{
  int v5; // r9d
  unsigned __int32 v6; // eax
  BOOL v7; // edx
  unsigned __int32 v8; // ett
  int v9; // ecx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  signed __int32 i; // edx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, (unsigned int)a3, a3, a1);
      return a1;
    case 5:
      goto LABEL_31;
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
  for ( i = *a2; ; i = v15 )
  {
    v14 = i | v9 | 1;
    *(_DWORD *)(a1 + 16) = (i | v9) == i;
    if ( (i | v9) == i )
      v14 = i | v9;
    v15 = _InterlockedCompareExchange(a2, v14, i);
    if ( i == v15 )
      break;
  }
  *(_DWORD *)a1 = (v14 & 1) != 0 && (i & 1) == 0;
  return a1;
}

```

## disassembly

```asm
0x18003df14  push    rbx
0x18003df16  sub     rsp, 20h
0x18003df1a  xor     eax, eax
0x18003df1c  xorps   xmm0, xmm0
0x18003df1f  mov     r10, rdx
0x18003df22  mov     rbx, rcx
0x18003df25  mov     r9d, r8d
0x18003df28  movups  xmmword ptr [rcx], xmm0
0x18003df2b  mov     [rcx+10h], rax
0x18003df2f  test    r8d, r8d
0x18003df32  jz      loc_18003E073
0x18003df38  sub     r9d, 1
0x18003df3c  jz      loc_18003E063
0x18003df42  sub     r9d, 1
0x18003df46  jz      loc_18003DFE7
0x18003df4c  sub     r9d, 1
0x18003df50  jz      loc_18003DFE7
0x18003df56  sub     r9d, 1
0x18003df5a  jz      loc_18003E073
0x18003df60  sub     r9d, 1
0x18003df64  jz      loc_18003E063
0x18003df6a  sub     r9d, 1
0x18003df6e  jz      short loc_18003DFE7
0x18003df70  cmp     r9d, 1
0x18003df74  jz      short loc_18003DFE7
0x18003df76  lea     r9d, [r8-140h]
0x18003df7d  cmp     r9d, 40h ; '@'
0x18003df81  jge     short loc_18003DFD0
0x18003df83  mov     eax, [rdx+4]
0x18003df86  mov     r11d, r9d
0x18003df89  shl     r11d, 5
0x18003df8d  mov     ecx, 10h
0x18003df92  test    cl, al
0x18003df94  jz      short loc_18003DFAA
0x18003df96  mov     edx, eax
0x18003df98  shr     edx, 5
0x18003df9b  and     edx, 3Fh
0x18003df9e  cmp     edx, r9d
0x18003dfa1  jnz     short loc_18003DFAA
0x18003dfa3  mov     edx, 1
0x18003dfa8  jmp     short loc_18003DFAC
0x18003dfaa  xor     edx, edx
0x18003dfac  mov     [rbx+10h], edx
0x18003dfaf  mov     edx, r11d
0x18003dfb2  xor     edx, eax
0x18003dfb4  and     edx, 7E0h
0x18003dfba  xor     edx, eax
0x18003dfbc  or      edx, ecx
0x18003dfbe  lock cmpxchg [r10+4], edx
0x18003dfc4  jnz     short loc_18003DF92
0x18003dfc6  cmp     dword ptr [rbx+10h], 0
0x18003dfca  jnz     loc_18003E081
0x18003dfd0  mov     [rbx+8], r8d
0x18003dfd4  mov     dword ptr [rbx+4], 1
0x18003dfdb  mov     dword ptr [rbx+0Ch], 0
0x18003dfe2  jmp     loc_18003E081
0x18003dfe7  xor     ecx, ecx
0x18003dfe9  sub     r8d, 2
0x18003dfed  jz      short loc_18003E015
0x18003dfef  sub     r8d, 1
0x18003dff3  jz      short loc_18003E00E
0x18003dff5  sub     r8d, 3
0x18003dff9  jz      short loc_18003E007
0x18003dffb  cmp     r8d, 1
0x18003dfff  jnz     short loc_18003E01A
0x18003e001  lea     ecx, [r8+0Fh]
0x18003e005  jmp     short loc_18003E01A
0x18003e007  mov     ecx, 4
0x18003e00c  jmp     short loc_18003E01A
0x18003e00e  mov     ecx, 8
0x18003e013  jmp     short loc_18003E01A
0x18003e015  mov     ecx, 2
0x18003e01a  mov     edx, [rdx]
0x18003e01c  xor     eax, eax
0x18003e01e  mov     r8d, ecx
0x18003e021  or      r8d, edx
0x18003e024  cmp     r8d, edx
0x18003e027  mov     r9d, r8d
0x18003e02a  setz    al
0x18003e02d  or      r9d, 1
0x18003e031  cmp     r8d, edx
0x18003e034  mov     [rbx+10h], eax
0x18003e037  mov     eax, edx
0x18003e039  cmovz   r9d, r8d
0x18003e03d  lock cmpxchg [r10], r9d
0x18003e042  jz      short loc_18003E048
0x18003e044  mov     edx, eax
0x18003e046  jmp     short loc_18003E01C
0x18003e048  test    r9b, 1
0x18003e04c  setnz   cl
0x18003e04f  test    dl, 1
0x18003e052  setz    al
0x18003e055  test    al, cl
0x18003e057  mov     eax, 0
0x18003e05c  setnz   al
0x18003e05f  mov     [rbx], eax
0x18003e061  jmp     short loc_18003E081
0x18003e063  mov     r9, rbx
0x18003e066  mov     edx, r8d
0x18003e069  mov     rcx, r10
0x18003e06c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x18003e071  jmp     short loc_18003E081
0x18003e073  mov     r9, rbx
0x18003e076  mov     edx, r8d
0x18003e079  mov     rcx, r10
0x18003e07c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x18003e081  mov     rax, rbx
0x18003e084  add     rsp, 20h
0x18003e088  pop     rbx
0x18003e089  retn
```
