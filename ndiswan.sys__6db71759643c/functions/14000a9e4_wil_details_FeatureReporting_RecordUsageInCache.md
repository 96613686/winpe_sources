# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x14000a9e4`
- end: `0x14000ab61`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000abf0`

## callees

- `0x14000a838`
- `0x14000a908`
- `0x14000a9e4`

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
0x14000a9e4  mov     [rsp+arg_0], rbx
0x14000a9e9  push    rdi
0x14000a9ea  sub     rsp, 20h
0x14000a9ee  xor     eax, eax
0x14000a9f0  xorps   xmm0, xmm0
0x14000a9f3  mov     edi, r9d
0x14000a9f6  mov     r11, rdx
0x14000a9f9  mov     r9, rcx
0x14000a9fc  mov     r10d, r8d
0x14000a9ff  movups  xmmword ptr [rcx], xmm0
0x14000aa02  mov     [rcx+10h], rax
0x14000aa06  test    r8d, r8d
0x14000aa09  jz      loc_14000AB47
0x14000aa0f  sub     r10d, 1
0x14000aa13  jz      loc_14000AB3A
0x14000aa19  sub     r10d, 1
0x14000aa1d  jz      loc_14000AABC
0x14000aa23  sub     r10d, 1
0x14000aa27  jz      loc_14000AABC
0x14000aa2d  sub     r10d, 1
0x14000aa31  jz      loc_14000AB47
0x14000aa37  sub     r10d, 1
0x14000aa3b  jz      loc_14000AB3A
0x14000aa41  sub     r10d, 1
0x14000aa45  jz      short loc_14000AABC
0x14000aa47  cmp     r10d, 1
0x14000aa4b  jz      short loc_14000AABC
0x14000aa4d  lea     r10d, [r8-140h]
0x14000aa54  cmp     r10d, 40h ; '@'
0x14000aa58  jge     short loc_14000AAA7
0x14000aa5a  mov     eax, [rdx+4]
0x14000aa5d  mov     ebx, r10d
0x14000aa60  shl     ebx, 5
0x14000aa63  mov     ecx, 10h
0x14000aa68  test    cl, al
0x14000aa6a  jz      short loc_14000AA80
0x14000aa6c  mov     edx, eax
0x14000aa6e  shr     edx, 5
0x14000aa71  and     edx, 3Fh
0x14000aa74  cmp     edx, r10d
0x14000aa77  jnz     short loc_14000AA80
0x14000aa79  mov     edx, 1
0x14000aa7e  jmp     short loc_14000AA82
0x14000aa80  xor     edx, edx
0x14000aa82  mov     [r9+10h], edx
0x14000aa86  mov     edx, ebx
0x14000aa88  xor     edx, eax
0x14000aa8a  and     edx, 7E0h
0x14000aa90  xor     edx, eax
0x14000aa92  or      edx, ecx
0x14000aa94  lock cmpxchg [r11+4], edx
0x14000aa9a  jnz     short loc_14000AA68
0x14000aa9c  cmp     dword ptr [r9+10h], 0
0x14000aaa1  jnz     loc_14000AB52
0x14000aaa7  mov     [r9+8], r8d
0x14000aaab  mov     dword ptr [r9+4], 1
0x14000aab3  mov     [r9+0Ch], edi
0x14000aab7  jmp     loc_14000AB52
0x14000aabc  xor     ecx, ecx
0x14000aabe  sub     r8d, 2
0x14000aac2  jz      short loc_14000AAEA
0x14000aac4  sub     r8d, 1
0x14000aac8  jz      short loc_14000AAE3
0x14000aaca  sub     r8d, 3
0x14000aace  jz      short loc_14000AADC
0x14000aad0  cmp     r8d, 1
0x14000aad4  jnz     short loc_14000AAEF
0x14000aad6  lea     ecx, [r8+0Fh]
0x14000aada  jmp     short loc_14000AAEF
0x14000aadc  mov     ecx, 4
0x14000aae1  jmp     short loc_14000AAEF
0x14000aae3  mov     ecx, 8
0x14000aae8  jmp     short loc_14000AAEF
0x14000aaea  mov     ecx, 2
0x14000aaef  mov     edx, [rdx]
0x14000aaf1  xor     eax, eax
0x14000aaf3  mov     r8d, ecx
0x14000aaf6  or      r8d, edx
0x14000aaf9  cmp     r8d, edx
0x14000aafc  mov     r10d, r8d
0x14000aaff  setz    al
0x14000ab02  or      r10d, 1
0x14000ab06  cmp     r8d, edx
0x14000ab09  mov     [r9+10h], eax
0x14000ab0d  mov     eax, edx
0x14000ab0f  cmovz   r10d, r8d
0x14000ab13  lock cmpxchg [r11], r10d
0x14000ab18  jz      short loc_14000AB1E
0x14000ab1a  mov     edx, eax
0x14000ab1c  jmp     short loc_14000AAF1
0x14000ab1e  test    r10b, 1
0x14000ab22  setnz   cl
0x14000ab25  test    dl, 1
0x14000ab28  setz    al
0x14000ab2b  test    al, cl
0x14000ab2d  mov     eax, 0
0x14000ab32  setnz   al
0x14000ab35  mov     [r9], eax
0x14000ab38  jmp     short loc_14000AB52
0x14000ab3a  mov     edx, r8d
0x14000ab3d  mov     rcx, r11
0x14000ab40  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x14000ab45  jmp     short loc_14000AB52
0x14000ab47  mov     edx, r8d
0x14000ab4a  mov     rcx, r11
0x14000ab4d  call    wil_details_FeatureReporting_IncrementUsageInCache
0x14000ab52  mov     rbx, [rsp+28h+arg_0]
0x14000ab57  mov     rax, r9
0x14000ab5a  add     rsp, 20h
0x14000ab5e  pop     rdi
0x14000ab5f  retn
```
