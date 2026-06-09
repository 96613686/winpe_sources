# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180016008`
- end: `0x18001617f`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000beac`

## callees

- `0x180015e5c`
- `0x180015f2c`
- `0x180016008`

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
0x180016008  mov     [rsp+arg_0], rbx
0x18001600d  push    rdi
0x18001600e  sub     rsp, 20h
0x180016012  xor     eax, eax
0x180016014  xorps   xmm0, xmm0
0x180016017  mov     r10, rdx
0x18001601a  mov     rbx, rcx
0x18001601d  mov     r9d, r8d
0x180016020  movups  xmmword ptr [rcx], xmm0
0x180016023  mov     [rcx+10h], rax
0x180016027  test    r8d, r8d
0x18001602a  jz      loc_180016163
0x180016030  sub     r9d, 1
0x180016034  jz      loc_180016153
0x18001603a  sub     r9d, 1
0x18001603e  jz      loc_1800160DB
0x180016044  sub     r9d, 1
0x180016048  jz      loc_1800160DB
0x18001604e  sub     r9d, 1
0x180016052  jz      loc_180016163
0x180016058  sub     r9d, 1
0x18001605c  jz      loc_180016153
0x180016062  sub     r9d, 1
0x180016066  jz      short loc_1800160DB
0x180016068  cmp     r9d, 1
0x18001606c  jz      short loc_1800160DB
0x18001606e  lea     r11d, [r8-140h]
0x180016075  lea     r9d, [rax+1]
0x180016079  cmp     r11d, 40h ; '@'
0x18001607d  jge     short loc_1800160C7
0x18001607f  mov     eax, [rdx+4]
0x180016082  lea     ecx, [r9+0Fh]
0x180016086  mov     edi, r11d
0x180016089  shl     edi, 5
0x18001608c  test    cl, al
0x18001608e  jz      short loc_1800160A2
0x180016090  mov     edx, eax
0x180016092  shr     edx, 5
0x180016095  and     edx, 3Fh
0x180016098  cmp     edx, r11d
0x18001609b  jnz     short loc_1800160A2
0x18001609d  mov     edx, r9d
0x1800160a0  jmp     short loc_1800160A4
0x1800160a2  xor     edx, edx
0x1800160a4  mov     [rbx+10h], edx
0x1800160a7  mov     edx, edi
0x1800160a9  xor     edx, eax
0x1800160ab  and     edx, 7E0h
0x1800160b1  xor     edx, eax
0x1800160b3  or      edx, ecx
0x1800160b5  lock cmpxchg [r10+4], edx
0x1800160bb  jnz     short loc_18001608C
0x1800160bd  cmp     dword ptr [rbx+10h], 0
0x1800160c1  jnz     loc_180016171
0x1800160c7  mov     [rbx+8], r8d
0x1800160cb  mov     [rbx+4], r9d
0x1800160cf  mov     dword ptr [rbx+0Ch], 0
0x1800160d6  jmp     loc_180016171
0x1800160db  xor     ecx, ecx
0x1800160dd  sub     r8d, 2
0x1800160e1  jz      short loc_180016109
0x1800160e3  sub     r8d, 1
0x1800160e7  jz      short loc_180016102
0x1800160e9  sub     r8d, 3
0x1800160ed  jz      short loc_1800160FB
0x1800160ef  cmp     r8d, 1
0x1800160f3  jnz     short loc_18001610E
0x1800160f5  lea     ecx, [r8+0Fh]
0x1800160f9  jmp     short loc_18001610E
0x1800160fb  mov     ecx, 4
0x180016100  jmp     short loc_18001610E
0x180016102  mov     ecx, 8
0x180016107  jmp     short loc_18001610E
0x180016109  mov     ecx, 2
0x18001610e  mov     edx, [rdx]
0x180016110  mov     r9d, 1
0x180016116  xor     eax, eax
0x180016118  mov     r8d, ecx
0x18001611b  or      r8d, edx
0x18001611e  cmp     r8d, edx
0x180016121  mov     r11d, r8d
0x180016124  setz    al
0x180016127  or      r11d, r9d
0x18001612a  cmp     r8d, edx
0x18001612d  mov     [rbx+10h], eax
0x180016130  mov     eax, edx
0x180016132  cmovz   r11d, r8d
0x180016136  lock cmpxchg [r10], r11d
0x18001613b  jz      short loc_180016141
0x18001613d  mov     edx, eax
0x18001613f  jmp     short loc_180016116
0x180016141  test    r9b, r11b
0x180016144  jz      short loc_18001614B
0x180016146  test    r9b, dl
0x180016149  jz      short loc_18001614E
0x18001614b  xor     r9d, r9d
0x18001614e  mov     [rbx], r9d
0x180016151  jmp     short loc_180016171
0x180016153  mov     r9, rbx
0x180016156  mov     edx, r8d
0x180016159  mov     rcx, r10
0x18001615c  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180016161  jmp     short loc_180016171
0x180016163  mov     r9, rbx
0x180016166  mov     edx, r8d
0x180016169  mov     rcx, r10
0x18001616c  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180016171  mov     rax, rbx
0x180016174  mov     rbx, [rsp+28h+arg_0]
0x180016179  add     rsp, 20h
0x18001617d  pop     rdi
0x18001617e  retn
```
