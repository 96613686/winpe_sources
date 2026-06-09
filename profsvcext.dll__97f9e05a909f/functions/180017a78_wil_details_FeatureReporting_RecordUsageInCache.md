# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180017a78`
- end: `0x180017bef`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `375`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001501c`

## callees

- `0x1800178cc`
- `0x18001799c`
- `0x180017a78`

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
0x180017a78  mov     [rsp+arg_0], rbx
0x180017a7d  push    rdi
0x180017a7e  sub     rsp, 20h
0x180017a82  xor     eax, eax
0x180017a84  xorps   xmm0, xmm0
0x180017a87  mov     r10, rdx
0x180017a8a  mov     rbx, rcx
0x180017a8d  mov     r9d, r8d
0x180017a90  movups  xmmword ptr [rcx], xmm0
0x180017a93  mov     [rcx+10h], rax
0x180017a97  test    r8d, r8d
0x180017a9a  jz      loc_180017BD3
0x180017aa0  sub     r9d, 1
0x180017aa4  jz      loc_180017BC3
0x180017aaa  sub     r9d, 1
0x180017aae  jz      loc_180017B4B
0x180017ab4  sub     r9d, 1
0x180017ab8  jz      loc_180017B4B
0x180017abe  sub     r9d, 1
0x180017ac2  jz      loc_180017BD3
0x180017ac8  sub     r9d, 1
0x180017acc  jz      loc_180017BC3
0x180017ad2  sub     r9d, 1
0x180017ad6  jz      short loc_180017B4B
0x180017ad8  cmp     r9d, 1
0x180017adc  jz      short loc_180017B4B
0x180017ade  lea     r11d, [r8-140h]
0x180017ae5  lea     r9d, [rax+1]
0x180017ae9  cmp     r11d, 40h ; '@'
0x180017aed  jge     short loc_180017B37
0x180017aef  mov     eax, [rdx+4]
0x180017af2  lea     ecx, [r9+0Fh]
0x180017af6  mov     edi, r11d
0x180017af9  shl     edi, 5
0x180017afc  test    cl, al
0x180017afe  jz      short loc_180017B12
0x180017b00  mov     edx, eax
0x180017b02  shr     edx, 5
0x180017b05  and     edx, 3Fh
0x180017b08  cmp     edx, r11d
0x180017b0b  jnz     short loc_180017B12
0x180017b0d  mov     edx, r9d
0x180017b10  jmp     short loc_180017B14
0x180017b12  xor     edx, edx
0x180017b14  mov     [rbx+10h], edx
0x180017b17  mov     edx, edi
0x180017b19  xor     edx, eax
0x180017b1b  and     edx, 7E0h
0x180017b21  xor     edx, eax
0x180017b23  or      edx, ecx
0x180017b25  lock cmpxchg [r10+4], edx
0x180017b2b  jnz     short loc_180017AFC
0x180017b2d  cmp     dword ptr [rbx+10h], 0
0x180017b31  jnz     loc_180017BE1
0x180017b37  mov     [rbx+8], r8d
0x180017b3b  mov     [rbx+4], r9d
0x180017b3f  mov     dword ptr [rbx+0Ch], 0
0x180017b46  jmp     loc_180017BE1
0x180017b4b  xor     ecx, ecx
0x180017b4d  sub     r8d, 2
0x180017b51  jz      short loc_180017B79
0x180017b53  sub     r8d, 1
0x180017b57  jz      short loc_180017B72
0x180017b59  sub     r8d, 3
0x180017b5d  jz      short loc_180017B6B
0x180017b5f  cmp     r8d, 1
0x180017b63  jnz     short loc_180017B7E
0x180017b65  lea     ecx, [r8+0Fh]
0x180017b69  jmp     short loc_180017B7E
0x180017b6b  mov     ecx, 4
0x180017b70  jmp     short loc_180017B7E
0x180017b72  mov     ecx, 8
0x180017b77  jmp     short loc_180017B7E
0x180017b79  mov     ecx, 2
0x180017b7e  mov     edx, [rdx]
0x180017b80  mov     r9d, 1
0x180017b86  xor     eax, eax
0x180017b88  mov     r8d, ecx
0x180017b8b  or      r8d, edx
0x180017b8e  cmp     r8d, edx
0x180017b91  mov     r11d, r8d
0x180017b94  setz    al
0x180017b97  or      r11d, r9d
0x180017b9a  cmp     r8d, edx
0x180017b9d  mov     [rbx+10h], eax
0x180017ba0  mov     eax, edx
0x180017ba2  cmovz   r11d, r8d
0x180017ba6  lock cmpxchg [r10], r11d
0x180017bab  jz      short loc_180017BB1
0x180017bad  mov     edx, eax
0x180017baf  jmp     short loc_180017B86
0x180017bb1  test    r9b, r11b
0x180017bb4  jz      short loc_180017BBB
0x180017bb6  test    r9b, dl
0x180017bb9  jz      short loc_180017BBE
0x180017bbb  xor     r9d, r9d
0x180017bbe  mov     [rbx], r9d
0x180017bc1  jmp     short loc_180017BE1
0x180017bc3  mov     r9, rbx
0x180017bc6  mov     edx, r8d
0x180017bc9  mov     rcx, r10
0x180017bcc  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180017bd1  jmp     short loc_180017BE1
0x180017bd3  mov     r9, rbx
0x180017bd6  mov     edx, r8d
0x180017bd9  mov     rcx, r10
0x180017bdc  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180017be1  mov     rax, rbx
0x180017be4  mov     rbx, [rsp+28h+arg_0]
0x180017be9  add     rsp, 20h
0x180017bed  pop     rdi
0x180017bee  retn
```
