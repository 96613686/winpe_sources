# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180022be4`
- end: `0x180022d61`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022df0`

## callees

- `0x180022a38`
- `0x180022b08`
- `0x180022be4`

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
0x180022be4  mov     [rsp+arg_0], rbx
0x180022be9  push    rdi
0x180022bea  sub     rsp, 20h
0x180022bee  xor     eax, eax
0x180022bf0  xorps   xmm0, xmm0
0x180022bf3  mov     edi, r9d
0x180022bf6  mov     r11, rdx
0x180022bf9  mov     r9, rcx
0x180022bfc  mov     r10d, r8d
0x180022bff  movups  xmmword ptr [rcx], xmm0
0x180022c02  mov     [rcx+10h], rax
0x180022c06  test    r8d, r8d
0x180022c09  jz      loc_180022D47
0x180022c0f  sub     r10d, 1
0x180022c13  jz      loc_180022D3A
0x180022c19  sub     r10d, 1
0x180022c1d  jz      loc_180022CBC
0x180022c23  sub     r10d, 1
0x180022c27  jz      loc_180022CBC
0x180022c2d  sub     r10d, 1
0x180022c31  jz      loc_180022D47
0x180022c37  sub     r10d, 1
0x180022c3b  jz      loc_180022D3A
0x180022c41  sub     r10d, 1
0x180022c45  jz      short loc_180022CBC
0x180022c47  cmp     r10d, 1
0x180022c4b  jz      short loc_180022CBC
0x180022c4d  lea     r10d, [r8-140h]
0x180022c54  cmp     r10d, 40h ; '@'
0x180022c58  jge     short loc_180022CA7
0x180022c5a  mov     eax, [rdx+4]
0x180022c5d  mov     ebx, r10d
0x180022c60  shl     ebx, 5
0x180022c63  mov     ecx, 10h
0x180022c68  test    cl, al
0x180022c6a  jz      short loc_180022C80
0x180022c6c  mov     edx, eax
0x180022c6e  shr     edx, 5
0x180022c71  and     edx, 3Fh
0x180022c74  cmp     edx, r10d
0x180022c77  jnz     short loc_180022C80
0x180022c79  mov     edx, 1
0x180022c7e  jmp     short loc_180022C82
0x180022c80  xor     edx, edx
0x180022c82  mov     [r9+10h], edx
0x180022c86  mov     edx, ebx
0x180022c88  xor     edx, eax
0x180022c8a  and     edx, 7E0h
0x180022c90  xor     edx, eax
0x180022c92  or      edx, ecx
0x180022c94  lock cmpxchg [r11+4], edx
0x180022c9a  jnz     short loc_180022C68
0x180022c9c  cmp     dword ptr [r9+10h], 0
0x180022ca1  jnz     loc_180022D52
0x180022ca7  mov     [r9+8], r8d
0x180022cab  mov     dword ptr [r9+4], 1
0x180022cb3  mov     [r9+0Ch], edi
0x180022cb7  jmp     loc_180022D52
0x180022cbc  xor     ecx, ecx
0x180022cbe  sub     r8d, 2
0x180022cc2  jz      short loc_180022CEA
0x180022cc4  sub     r8d, 1
0x180022cc8  jz      short loc_180022CE3
0x180022cca  sub     r8d, 3
0x180022cce  jz      short loc_180022CDC
0x180022cd0  cmp     r8d, 1
0x180022cd4  jnz     short loc_180022CEF
0x180022cd6  lea     ecx, [r8+0Fh]
0x180022cda  jmp     short loc_180022CEF
0x180022cdc  mov     ecx, 4
0x180022ce1  jmp     short loc_180022CEF
0x180022ce3  mov     ecx, 8
0x180022ce8  jmp     short loc_180022CEF
0x180022cea  mov     ecx, 2
0x180022cef  mov     edx, [rdx]
0x180022cf1  xor     eax, eax
0x180022cf3  mov     r8d, ecx
0x180022cf6  or      r8d, edx
0x180022cf9  cmp     r8d, edx
0x180022cfc  mov     r10d, r8d
0x180022cff  setz    al
0x180022d02  or      r10d, 1
0x180022d06  cmp     r8d, edx
0x180022d09  mov     [r9+10h], eax
0x180022d0d  mov     eax, edx
0x180022d0f  cmovz   r10d, r8d
0x180022d13  lock cmpxchg [r11], r10d
0x180022d18  jz      short loc_180022D1E
0x180022d1a  mov     edx, eax
0x180022d1c  jmp     short loc_180022CF1
0x180022d1e  test    r10b, 1
0x180022d22  setnz   cl
0x180022d25  test    dl, 1
0x180022d28  setz    al
0x180022d2b  test    al, cl
0x180022d2d  mov     eax, 0
0x180022d32  setnz   al
0x180022d35  mov     [r9], eax
0x180022d38  jmp     short loc_180022D52
0x180022d3a  mov     edx, r8d
0x180022d3d  mov     rcx, r11
0x180022d40  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x180022d45  jmp     short loc_180022D52
0x180022d47  mov     edx, r8d
0x180022d4a  mov     rcx, r11
0x180022d4d  call    wil_details_FeatureReporting_IncrementUsageInCache
0x180022d52  mov     rbx, [rsp+28h+arg_0]
0x180022d57  mov     rax, r9
0x180022d5a  add     rsp, 20h
0x180022d5e  pop     rdi
0x180022d5f  retn
```
