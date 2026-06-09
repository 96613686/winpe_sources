# wil_details_FeatureReporting_RecordUsageInCache

- ea: `0x180015b44`
- end: `0x180015e16`
- name: `wil_details_FeatureReporting_RecordUsageInCache`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015f58`

## callees

- `0x180015b44`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureReporting_RecordUsageInCache(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  int v7; // r8d
  unsigned __int32 v8; // eax
  BOOL v9; // edx
  unsigned __int32 v10; // ett
  int v11; // ecx
  signed __int32 v12; // edx
  int v13; // ebx
  signed __int32 v14; // r9d
  signed __int32 v15; // eax
  signed __int32 v16; // ecx
  BOOL v17; // r9d
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // edx
  unsigned int v22; // r8d
  signed __int32 v23; // eax
  signed __int32 v24; // edx
  BOOL v25; // ebp
  unsigned int v26; // eax
  int v27; // r9d
  unsigned int v28; // r8d
  unsigned int v29; // r9d
  signed __int32 v30; // eax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  switch ( a3 )
  {
    case 0:
      goto LABEL_49;
    case 1:
      goto LABEL_34;
    case 2:
    case 3:
      goto LABEL_17;
    case 4:
LABEL_49:
      v24 = *a2;
      v25 = a3 == 4;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v26 = v24 | 1;
        if ( (((v24 | 1u) >> 14) & 1) != v25 )
        {
          if ( ((v26 >> 5) & 0x1FF) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v26 >> 5) & 0x1FF;
            *(_DWORD *)(a1 + 8) = a3 == 0 ? 4 : 0;
            v26 = v24 & 0xFFFFC01E | 1;
          }
          v27 = 0;
          if ( a3 == 4 )
            v27 = 0x4000;
          v26 = v26 & 0xFFFFBFFF | v27;
        }
        v28 = (v26 >> 5) & 0x1FF;
        v29 = v28 + 1;
        if ( v28 + 1 > 0x1FF || v29 < v28 )
        {
          LOWORD(v29) = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v28;
        }
        v30 = _InterlockedCompareExchange(
                a2,
                v26 ^ ((unsigned __int16)v26 ^ (unsigned __int16)(32 * v29)) & 0x3FE0,
                v24);
        if ( v24 == v30 )
          break;
        v24 = v30;
      }
      *(_DWORD *)a1 = (v24 & 1) == 0;
      goto LABEL_62;
    case 5:
LABEL_34:
      v16 = *a2;
      v17 = a3 == 5;
      while ( 1 )
      {
        *(_DWORD *)(a1 + 4) = 0;
        v18 = v16 | 1;
        if ( (((v16 | 1u) >> 22) & 1) != v17 )
        {
          if ( ((v18 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a1 + 4) = (v18 >> 15) & 0x7F;
            v19 = 5;
            if ( a3 != 1 )
              v19 = 1;
            v18 = v16 & 0xFFC07FFE | 1;
            *(_DWORD *)(a1 + 8) = v19;
          }
          v20 = 0;
          if ( a3 == 5 )
            v20 = 0x400000;
          v18 = v18 & 0xFFBFFFFF | v20;
        }
        v21 = (v18 >> 15) & 0x7F;
        v22 = v21 + 1;
        if ( v21 + 1 > 0x7F || v22 < v21 )
        {
          v22 = 1;
          *(_DWORD *)(a1 + 8) = a3;
          *(_DWORD *)(a1 + 4) = v21;
        }
        v23 = _InterlockedCompareExchange(a2, v18 ^ (v18 ^ (v22 << 15)) & 0x3F8000, v16);
        if ( v16 == v23 )
          break;
        v16 = v23;
      }
      *(_DWORD *)a1 = (v16 & 1) == 0;
LABEL_62:
      *(_DWORD *)(a1 + 16) = 0;
      return a1;
  }
  if ( (unsigned int)(a3 - 6) >= 2 )
  {
    v7 = a3 - 320;
    if ( v7 >= 64 )
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
    return a1;
  }
LABEL_17:
  v11 = 0;
  switch ( a3 )
  {
    case 2:
      v11 = 2;
      break;
    case 3:
      v11 = 8;
      break;
    case 6:
      v11 = 4;
      break;
    case 7:
      v11 = 16;
      break;
  }
  v12 = *a2;
  v13 = 1;
  while ( 1 )
  {
    v14 = v12 | v11 | 1;
    *(_DWORD *)(a1 + 16) = (v12 | v11) == v12;
    if ( (v12 | v11) == v12 )
      v14 = v12 | v11;
    v15 = _InterlockedCompareExchange(a2, v14, v12);
    if ( v12 == v15 )
      break;
    v12 = v15;
  }
  if ( (v14 & 1) == 0 || (v12 & 1) != 0 )
    v13 = 0;
  *(_DWORD *)a1 = v13;
  return a1;
}

```

## disassembly

```asm
0x180015b44  push    rbx
0x180015b46  push    rbp
0x180015b47  push    rsi
0x180015b48  push    rdi
0x180015b49  xor     eax, eax
0x180015b4b  xorps   xmm0, xmm0
0x180015b4e  mov     r10, rcx
0x180015b51  mov     edi, r9d
0x180015b54  mov     r11d, r8d
0x180015b57  mov     rsi, rdx
0x180015b5a  movups  xmmword ptr [rcx], xmm0
0x180015b5d  mov     [rcx+10h], rax
0x180015b61  mov     ecx, r8d
0x180015b64  test    r8d, r8d
0x180015b67  jz      loc_180015D40
0x180015b6d  sub     ecx, 1
0x180015b70  jz      loc_180015C87
0x180015b76  sub     ecx, 1
0x180015b79  jz      loc_180015C0E
0x180015b7f  sub     ecx, 1
0x180015b82  jz      loc_180015C0E
0x180015b88  sub     ecx, 1
0x180015b8b  jz      loc_180015D40
0x180015b91  sub     ecx, 1
0x180015b94  jz      loc_180015C87
0x180015b9a  sub     ecx, 1
0x180015b9d  jz      short loc_180015C0E
0x180015b9f  cmp     ecx, 1
0x180015ba2  jz      short loc_180015C0E
0x180015ba4  add     r8d, 0FFFFFEC0h
0x180015bab  lea     ebx, [rax+1]
0x180015bae  cmp     r8d, 40h ; '@'
0x180015bb2  jge     short loc_180015BFD
0x180015bb4  mov     eax, [rdx+4]
0x180015bb7  lea     ecx, [rbx+0Fh]
0x180015bba  mov     r9d, r8d
0x180015bbd  shl     r9d, 5
0x180015bc1  test    cl, al
0x180015bc3  jz      short loc_180015BD6
0x180015bc5  mov     edx, eax
0x180015bc7  shr     edx, 5
0x180015bca  and     edx, 3Fh
0x180015bcd  cmp     edx, r8d
0x180015bd0  jnz     short loc_180015BD6
0x180015bd2  mov     edx, ebx
0x180015bd4  jmp     short loc_180015BD8
0x180015bd6  xor     edx, edx
0x180015bd8  mov     [r10+10h], edx
0x180015bdc  mov     edx, r9d
0x180015bdf  xor     edx, eax
0x180015be1  and     edx, 7E0h
0x180015be7  xor     edx, eax
0x180015be9  or      edx, ecx
0x180015beb  lock cmpxchg [rsi+4], edx
0x180015bf0  jnz     short loc_180015BC1
0x180015bf2  cmp     dword ptr [r10+10h], 0
0x180015bf7  jnz     loc_180015E0E
0x180015bfd  mov     [r10+8], r11d
0x180015c01  mov     [r10+4], ebx
0x180015c05  mov     [r10+0Ch], edi
0x180015c09  jmp     loc_180015E0E
0x180015c0e  xor     ecx, ecx
0x180015c10  sub     r11d, 2
0x180015c14  jz      short loc_180015C3C
0x180015c16  sub     r11d, 1
0x180015c1a  jz      short loc_180015C35
0x180015c1c  sub     r11d, 3
0x180015c20  jz      short loc_180015C2E
0x180015c22  cmp     r11d, 1
0x180015c26  jnz     short loc_180015C41
0x180015c28  lea     ecx, [r11+0Fh]
0x180015c2c  jmp     short loc_180015C41
0x180015c2e  mov     ecx, 4
0x180015c33  jmp     short loc_180015C41
0x180015c35  mov     ecx, 8
0x180015c3a  jmp     short loc_180015C41
0x180015c3c  mov     ecx, 2
0x180015c41  mov     edx, [rdx]
0x180015c43  mov     ebx, 1
0x180015c48  xor     eax, eax
0x180015c4a  mov     r8d, ecx
0x180015c4d  or      r8d, edx
0x180015c50  cmp     r8d, edx
0x180015c53  mov     r9d, r8d
0x180015c56  setz    al
0x180015c59  or      r9d, ebx
0x180015c5c  cmp     r8d, edx
0x180015c5f  mov     [r10+10h], eax
0x180015c63  mov     eax, edx
0x180015c65  cmovz   r9d, r8d
0x180015c69  lock cmpxchg [rsi], r9d
0x180015c6e  jz      short loc_180015C74
0x180015c70  mov     edx, eax
0x180015c72  jmp     short loc_180015C48
0x180015c74  test    bl, r9b
0x180015c77  jz      short loc_180015C7D
0x180015c79  test    bl, dl
0x180015c7b  jz      short loc_180015C7F
0x180015c7d  xor     ebx, ebx
0x180015c7f  mov     [r10], ebx
0x180015c82  jmp     loc_180015E0E
0x180015c87  mov     ecx, [rdx]
0x180015c89  xor     r9d, r9d
0x180015c8c  cmp     r11d, 5
0x180015c90  mov     ebx, 1
0x180015c95  setz    r9b
0x180015c99  mov     eax, ecx
0x180015c9b  mov     dword ptr [r10+4], 0
0x180015ca3  or      eax, ebx
0x180015ca5  mov     edx, eax
0x180015ca7  shr     edx, 16h
0x180015caa  and     edx, ebx
0x180015cac  cmp     edx, r9d
0x180015caf  jz      short loc_180015CF1
0x180015cb1  mov     r8d, eax
0x180015cb4  shr     r8d, 0Fh
0x180015cb8  and     r8d, 7Fh
0x180015cbc  jbe     short loc_180015CD6
0x180015cbe  cmp     r11d, ebx
0x180015cc1  mov     [r10+4], r8d
0x180015cc5  mov     edx, 5
0x180015cca  cmovnz  edx, ebx
0x180015ccd  and     eax, 0FFC07FFFh
0x180015cd2  mov     [r10+8], edx
0x180015cd6  xor     r8d, r8d
0x180015cd9  mov     edx, 400000h
0x180015cde  cmp     r11d, 5
0x180015ce2  cmovz   r8d, edx
0x180015ce6  mov     edx, eax
0x180015ce8  btr     edx, 16h
0x180015cec  mov     eax, r8d
0x180015cef  or      eax, edx
0x180015cf1  mov     edx, eax
0x180015cf3  shr     edx, 0Fh
0x180015cf6  and     edx, 7Fh
0x180015cf9  lea     r8d, [rdx+1]
0x180015cfd  cmp     r8d, 7Fh
0x180015d01  ja      short loc_180015D08
0x180015d03  cmp     r8d, edx
0x180015d06  jnb     short loc_180015D13
0x180015d08  mov     r8d, ebx
0x180015d0b  mov     [r10+8], r11d
0x180015d0f  mov     [r10+4], edx
0x180015d13  shl     r8d, 0Fh
0x180015d17  xor     r8d, eax
0x180015d1a  and     r8d, 3F8000h
0x180015d21  xor     r8d, eax
0x180015d24  mov     eax, ecx
0x180015d26  lock cmpxchg [rsi], r8d
0x180015d2b  jz      short loc_180015D34
0x180015d2d  mov     ecx, eax
0x180015d2f  jmp     loc_180015C99
0x180015d34  not     ecx
0x180015d36  and     ecx, ebx
0x180015d38  mov     [r10], ecx
0x180015d3b  jmp     loc_180015E06
0x180015d40  mov     edx, [rdx]
0x180015d42  xor     ebp, ebp
0x180015d44  lea     ecx, [rbp+4]
0x180015d47  cmp     r11d, ecx
0x180015d4a  lea     ebx, [rcx-3]
0x180015d4d  setz    bpl
0x180015d51  mov     eax, edx
0x180015d53  mov     dword ptr [r10+4], 0
0x180015d5b  or      eax, ebx
0x180015d5d  mov     r8d, eax
0x180015d60  shr     r8d, 0Eh
0x180015d64  and     r8d, ebx
0x180015d67  cmp     r8d, ebp
0x180015d6a  jz      short loc_180015DB3
0x180015d6c  mov     edi, eax
0x180015d6e  shr     edi, 5
0x180015d71  and     edi, 1FFh
0x180015d77  jbe     short loc_180015D95
0x180015d79  mov     r8d, r11d
0x180015d7c  mov     [r10+4], edi
0x180015d80  neg     r8d
0x180015d83  sbb     r9d, r9d
0x180015d86  not     r9d
0x180015d89  and     r9d, ecx
0x180015d8c  mov     [r10+8], r9d
0x180015d90  and     eax, 0FFFFC01Fh
0x180015d95  xor     r9d, r9d
0x180015d98  mov     r8d, 4000h
0x180015d9e  cmp     r11d, ecx
0x180015da1  cmovz   r9d, r8d
0x180015da5  mov     r8d, eax
0x180015da8  btr     r8d, 0Eh
0x180015dad  mov     eax, r9d
0x180015db0  or      eax, r8d
0x180015db3  mov     r8d, eax
0x180015db6  shr     r8d, 5
0x180015dba  and     r8d, 1FFh
0x180015dc1  lea     r9d, [r8+1]
0x180015dc5  cmp     r9d, 1FFh
0x180015dcc  ja      short loc_180015DD3
0x180015dce  cmp     r9d, r8d
0x180015dd1  jnb     short loc_180015DDE
0x180015dd3  mov     r9d, ebx
0x180015dd6  mov     [r10+8], r11d
0x180015dda  mov     [r10+4], r8d
0x180015dde  shl     r9d, 5
0x180015de2  xor     r9d, eax
0x180015de5  and     r9d, 3FE0h
0x180015dec  xor     r9d, eax
0x180015def  mov     eax, edx
0x180015df1  lock cmpxchg [rsi], r9d
0x180015df6  jz      short loc_180015DFF
0x180015df8  mov     edx, eax
0x180015dfa  jmp     loc_180015D51
0x180015dff  not     edx
0x180015e01  and     edx, ebx
0x180015e03  mov     [r10], edx
0x180015e06  mov     dword ptr [r10+10h], 0
0x180015e0e  mov     rax, r10
0x180015e11  pop     rdi
0x180015e12  pop     rsi
0x180015e13  pop     rbp
0x180015e14  pop     rbx
0x180015e15  retn
```
