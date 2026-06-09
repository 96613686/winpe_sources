# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x140002adc`
- end: `0x140002c59`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `381`
- prototype: `_DWORD *__fastcall(__int64, volatile signed __int32 *, __int64, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002ce8`

## callees

- `0x140002930`
- `0x140002a00`
- `0x140002adc`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        __int64 a3,
        int a4)
{
  _DWORD *v6; // r9
  int v7; // r10d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  signed __int32 i; // edx
  signed __int32 v16; // r10d
  signed __int32 v17; // eax

  v6 = (_DWORD *)a1;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_32;
    case 1:
LABEL_31:
      wil_details_FeatureReporting_IncrementOpportunityInCache(a2, a3, a3, (_DWORD *)a1);
      return v6;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_32:
      wil_details_FeatureReporting_IncrementUsageInCache(a2, a3, a3, (_DWORD *)a1);
      return v6;
    case 5:
      goto LABEL_31;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( (int)a3 - 320 >= 64 )
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
0x140002adc  mov     [rsp+arg_0], rbx
0x140002ae1  push    rdi
0x140002ae2  sub     rsp, 20h
0x140002ae6  xor     eax, eax
0x140002ae8  xorps   xmm0, xmm0
0x140002aeb  mov     edi, r9d
0x140002aee  mov     r11, rdx
0x140002af1  mov     r9, rcx
0x140002af4  mov     r10d, r8d
0x140002af7  movups  xmmword ptr [rcx], xmm0
0x140002afa  mov     [rcx+10h], rax
0x140002afe  test    r8d, r8d
0x140002b01  jz      loc_140002C3F
0x140002b07  sub     r10d, 1
0x140002b0b  jz      loc_140002C32
0x140002b11  sub     r10d, 1
0x140002b15  jz      loc_140002BB4
0x140002b1b  sub     r10d, 1
0x140002b1f  jz      loc_140002BB4
0x140002b25  sub     r10d, 1
0x140002b29  jz      loc_140002C3F
0x140002b2f  sub     r10d, 1
0x140002b33  jz      loc_140002C32
0x140002b39  sub     r10d, 1
0x140002b3d  jz      short loc_140002BB4
0x140002b3f  cmp     r10d, 1
0x140002b43  jz      short loc_140002BB4
0x140002b45  lea     r10d, [r8-140h]
0x140002b4c  cmp     r10d, 40h ; '@'
0x140002b50  jge     short loc_140002B9F
0x140002b52  mov     eax, [rdx+4]
0x140002b55  mov     ebx, r10d
0x140002b58  shl     ebx, 5
0x140002b5b  mov     ecx, 10h
0x140002b60  test    cl, al
0x140002b62  jz      short loc_140002B78
0x140002b64  mov     edx, eax
0x140002b66  shr     edx, 5
0x140002b69  and     edx, 3Fh
0x140002b6c  cmp     edx, r10d
0x140002b6f  jnz     short loc_140002B78
0x140002b71  mov     edx, 1
0x140002b76  jmp     short loc_140002B7A
0x140002b78  xor     edx, edx
0x140002b7a  mov     [r9+10h], edx
0x140002b7e  mov     edx, ebx
0x140002b80  xor     edx, eax
0x140002b82  and     edx, 7E0h
0x140002b88  xor     edx, eax
0x140002b8a  or      edx, ecx
0x140002b8c  lock cmpxchg [r11+4], edx
0x140002b92  jnz     short loc_140002B60
0x140002b94  cmp     dword ptr [r9+10h], 0
0x140002b99  jnz     loc_140002C4A
0x140002b9f  mov     [r9+8], r8d
0x140002ba3  mov     dword ptr [r9+4], 1
0x140002bab  mov     [r9+0Ch], edi
0x140002baf  jmp     loc_140002C4A
0x140002bb4  xor     ecx, ecx
0x140002bb6  sub     r8d, 2
0x140002bba  jz      short loc_140002BE2
0x140002bbc  sub     r8d, 1
0x140002bc0  jz      short loc_140002BDB
0x140002bc2  sub     r8d, 3
0x140002bc6  jz      short loc_140002BD4
0x140002bc8  cmp     r8d, 1
0x140002bcc  jnz     short loc_140002BE7
0x140002bce  lea     ecx, [r8+0Fh]
0x140002bd2  jmp     short loc_140002BE7
0x140002bd4  mov     ecx, 4
0x140002bd9  jmp     short loc_140002BE7
0x140002bdb  mov     ecx, 8
0x140002be0  jmp     short loc_140002BE7
0x140002be2  mov     ecx, 2
0x140002be7  mov     edx, [rdx]
0x140002be9  xor     eax, eax
0x140002beb  mov     r8d, ecx
0x140002bee  or      r8d, edx
0x140002bf1  cmp     r8d, edx
0x140002bf4  mov     r10d, r8d
0x140002bf7  setz    al
0x140002bfa  or      r10d, 1
0x140002bfe  cmp     r8d, edx
0x140002c01  mov     [r9+10h], eax
0x140002c05  mov     eax, edx
0x140002c07  cmovz   r10d, r8d
0x140002c0b  lock cmpxchg [r11], r10d
0x140002c10  jz      short loc_140002C16
0x140002c12  mov     edx, eax
0x140002c14  jmp     short loc_140002BE9
0x140002c16  test    r10b, 1
0x140002c1a  setnz   cl
0x140002c1d  test    dl, 1
0x140002c20  setz    al
0x140002c23  test    al, cl
0x140002c25  mov     eax, 0
0x140002c2a  setnz   al
0x140002c2d  mov     [r9], eax
0x140002c30  jmp     short loc_140002C4A
0x140002c32  mov     edx, r8d
0x140002c35  mov     rcx, r11
0x140002c38  call    wil_details_FeatureReporting_IncrementOpportunityInCache
0x140002c3d  jmp     short loc_140002C4A
0x140002c3f  mov     edx, r8d
0x140002c42  mov     rcx, r11
0x140002c45  call    wil_details_FeatureReporting_IncrementUsageInCache
0x140002c4a  mov     rbx, [rsp+28h+arg_0]
0x140002c4f  mov     rax, r9
0x140002c52  add     rsp, 20h
0x140002c56  pop     rdi
0x140002c57  retn
```
