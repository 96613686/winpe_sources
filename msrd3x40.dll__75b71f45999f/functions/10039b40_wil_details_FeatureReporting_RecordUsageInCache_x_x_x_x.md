# wil_details_FeatureReporting_RecordUsageInCache(x,x,x,x)

- ea: `0x10039b40`
- end: `0x10039deb`
- name: `_wil_details_FeatureReporting_RecordUsageInCache@16`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1003a060`

## callees

- `0x10039b40`

## pseudocode

```c
_DWORD *__fastcall wil_details_FeatureReporting_RecordUsageInCache(
        volatile signed __int32 *a1,
        int a2,
        int a3,
        int a4,
        int a5)
{
  _DWORD *v5; // edi
  int v6; // ebx
  int v7; // ebx
  int v8; // edx
  signed __int32 j; // ecx
  signed __int32 v10; // ebx
  signed __int32 v11; // eax
  _DWORD *result; // eax
  signed __int32 i; // edx
  unsigned int v14; // ecx
  int v15; // eax
  int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // esi
  signed __int32 v19; // eax
  unsigned int v20; // ecx
  int v21; // eax
  unsigned int v22; // esi
  unsigned int v23; // eax
  signed __int32 v24; // eax
  int v25; // esi
  unsigned __int32 v26; // edx
  unsigned __int16 v27; // bx
  BOOL v28; // eax
  signed __int32 v29; // eax
  int v30; // [esp+Ch] [ebp-Ch]

  v5 = (_DWORD *)a3;
  v6 = a2;
  *(_OWORD *)a3 = 0;
  *(_QWORD *)(a3 + 16) = 0;
  switch ( a2 )
  {
    case 0:
    case 4:
      for ( i = *a1; ; i = v19 )
      {
        *(_DWORD *)(a3 + 4) = 0;
        v14 = i | 1;
        if ( (((i | 1u) >> 14) & 1) != (v6 == 4) )
        {
          if ( ((v14 >> 5) & 0x1FF) != 0 )
          {
            v15 = 0;
            *(_DWORD *)(a3 + 4) = (v14 >> 5) & 0x1FF;
            if ( !v6 )
              v15 = 4;
            v14 = i & 0xFFFFC01E | 1;
            *(_DWORD *)(a3 + 8) = v15;
          }
          v16 = 0;
          if ( v6 == 4 )
            v16 = 0x4000;
          v14 = v16 | v14 & 0xFFFFBFFF;
        }
        v17 = (v14 >> 5) & 0x1FF;
        v18 = v17 + 1;
        if ( v17 + 1 > 0x1FF || v18 < v17 )
        {
          LOWORD(v18) = 1;
          *(_DWORD *)(a3 + 8) = v6;
          *(_DWORD *)(a3 + 4) = v17;
        }
        v19 = _InterlockedCompareExchange(a1, ((unsigned __int16)v14 ^ (unsigned __int16)(32 * v18)) & 0x3FE0 ^ v14, i);
        if ( v19 == i )
          break;
      }
      goto LABEL_30;
    case 1:
    case 5:
      for ( i = *a1; ; i = v24 )
      {
        *(_DWORD *)(a3 + 4) = 0;
        v20 = i | 1;
        if ( (((i | 1u) >> 22) & 1) != (v6 == 5) )
        {
          if ( ((v20 >> 15) & 0x7F) != 0 )
          {
            *(_DWORD *)(a3 + 4) = (v20 >> 15) & 0x7F;
            v20 = i & 0xFFC07FFE | 1;
            *(_DWORD *)(a3 + 8) = 4 * (v6 == 1) + 1;
          }
          v21 = 0;
          if ( v6 == 5 )
            v21 = 0x400000;
          v20 = v21 | v20 & 0xFFBFFFFF;
        }
        v22 = (v20 >> 15) & 0x7F;
        v23 = v22 + 1;
        if ( v22 + 1 > 0x7F || v23 < v22 )
        {
          v23 = 1;
          *(_DWORD *)(a3 + 8) = v6;
          *(_DWORD *)(a3 + 4) = v22;
        }
        v24 = _InterlockedCompareExchange(a1, (v20 ^ (v23 << 15)) & 0x3F8000 ^ v20, i);
        if ( v24 == i )
          break;
      }
LABEL_30:
      *(_DWORD *)(a3 + 16) = 0;
      result = (_DWORD *)a3;
      *(_DWORD *)a3 = (i & 1) == 0;
      break;
    case 2:
    case 3:
    case 6:
    case 7:
      v7 = a2 - 2;
      v8 = 0;
      switch ( v7 )
      {
        case 0:
          v8 = 2;
          break;
        case 1:
          v8 = 8;
          break;
        case 4:
          v8 = 4;
          break;
        case 5:
          v8 = 16;
          break;
        default:
          break;
      }
      for ( j = *a1; ; j = v11 )
      {
        v5[4] = (j | v8) == j;
        v10 = j | v8 | 1;
        if ( (j | v8) == j )
          v10 = j | v8;
        v11 = _InterlockedCompareExchange(a1, v10, j);
        v5 = (_DWORD *)a3;
        if ( v11 == j )
          break;
      }
      if ( (v10 & 1) == 0 || (j & 1) != 0 )
      {
        *(_DWORD *)a3 = 0;
        result = (_DWORD *)a3;
      }
      else
      {
        *(_DWORD *)a3 = 1;
        result = (_DWORD *)a3;
      }
      break;
    default:
      v25 = a2 - 320;
      v30 = a2 - 320;
      if ( a2 - 320 >= 64 )
        goto LABEL_52;
      v26 = *((_DWORD *)a1 + 1);
      v27 = 32 * v25;
      while ( 1 )
      {
        v28 = (v26 & 0x10) != 0 && ((v26 >> 5) & 0x3F) == v25;
        v5[4] = v28;
        v29 = _InterlockedCompareExchange(a1 + 1, v26 ^ ((unsigned __int16)v26 ^ v27) & 0x7E0 | 0x10, v26);
        v5 = (_DWORD *)a3;
        v25 = v30;
        if ( v29 == v26 )
          break;
        v26 = v29;
      }
      v6 = a2;
      if ( !*(_DWORD *)(a3 + 16) )
      {
LABEL_52:
        v5[2] = v6;
        v5[1] = 1;
        v5[3] = 0;
      }
      result = v5;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x10039b40  mov     edi, edi
0x10039b42  push    ebp
0x10039b43  mov     ebp, esp
0x10039b45  sub     esp, 0Ch
0x10039b48  push    ebx
0x10039b49  push    esi
0x10039b4a  push    edi
0x10039b4b  mov     edi, [ebp+arg_0]
0x10039b4e  mov     ebx, edx
0x10039b50  mov     [ebp+var_8], ebx
0x10039b53  xorps   xmm0, xmm0
0x10039b56  mov     eax, ecx
0x10039b58  mov     [ebp+var_4], eax
0x10039b5b  movups  xmmword ptr [edi], xmm0
0x10039b5e  movq    qword ptr [edi+10h], xmm0
0x10039b63  cmp     ebx, 7; switch 8 cases
0x10039b66  ja      def_10039B6C; jumptable 10039B6C default case
0x10039b6c  jmp     ds:jpt_10039B6C[ebx*4]; switch jump
0x10039b73  add     ebx, 0FFFFFFFEh; jumptable 10039B6C cases 2,3,6,7
0x10039b76  xor     edx, edx
0x10039b78  cmp     ebx, 5
0x10039b7b  ja      short def_10039B7D; jumptable 10039B7D default case, cases 4,5
0x10039b7d  jmp     ds:jpt_10039B7D[ebx*4]; switch jump
0x10039b84  mov     edx, 2; jumptable 10039B7D case 2
0x10039b89  jmp     short def_10039B7D; jumptable 10039B7D default case, cases 4,5
0x10039b8b  mov     edx, 8; jumptable 10039B7D case 3
0x10039b90  jmp     short def_10039B7D; jumptable 10039B7D default case, cases 4,5
0x10039b92  mov     edx, 4; jumptable 10039B7D case 6
0x10039b97  jmp     short def_10039B7D; jumptable 10039B7D default case, cases 4,5
0x10039b99  mov     edx, 10h; jumptable 10039B7D case 7
0x10039b9e  mov     ecx, [eax]; jumptable 10039B7D default case, cases 4,5
0x10039ba0  xor     ebx, ebx
0x10039ba2  mov     eax, edx
0x10039ba4  or      eax, ecx
0x10039ba6  cmp     eax, ecx
0x10039ba8  setz    bl
0x10039bab  mov     [edi+10h], ebx
0x10039bae  mov     ebx, eax
0x10039bb0  mov     edi, [ebp+var_4]
0x10039bb3  or      ebx, 1
0x10039bb6  cmp     eax, ecx
0x10039bb8  cmovz   ebx, eax
0x10039bbb  mov     eax, ecx
0x10039bbd  mov     esi, ebx
0x10039bbf  lock cmpxchg [edi], esi
0x10039bc3  mov     edi, [ebp+arg_0]
0x10039bc6  cmp     eax, ecx
0x10039bc8  jz      short loc_10039BCE
0x10039bca  mov     ecx, eax
0x10039bcc  jmp     short loc_10039BA0
0x10039bce  test    bl, 1
0x10039bd1  jz      short loc_10039BEA
0x10039bd3  test    cl, 1
0x10039bd6  jnz     short loc_10039BEA
0x10039bd8  mov     eax, 1
0x10039bdd  mov     [edi], eax
0x10039bdf  mov     eax, edi
0x10039be1  pop     edi
0x10039be2  pop     esi
0x10039be3  pop     ebx
0x10039be4  mov     esp, ebp
0x10039be6  pop     ebp
0x10039be7  retn    0Ch
0x10039bea  xor     eax, eax
0x10039bec  mov     [edi], eax
0x10039bee  mov     eax, edi
0x10039bf0  pop     edi
0x10039bf1  pop     esi
0x10039bf2  pop     ebx
0x10039bf3  mov     esp, ebp
0x10039bf5  pop     ebp
0x10039bf6  retn    0Ch
0x10039bf9  mov     edx, [eax]; jumptable 10039B6C cases 0,4
0x10039bfb  xor     eax, eax
0x10039bfd  cmp     ebx, 4
0x10039c00  mov     [ebp+var_C], 4
0x10039c07  setz    al
0x10039c0a  mov     [ebp+var_8], eax
0x10039c0d  nop     dword ptr [eax]
0x10039c10  mov     ecx, edx
0x10039c12  mov     dword ptr [edi+4], 0
0x10039c19  or      ecx, 1
0x10039c1c  mov     eax, ecx
0x10039c1e  shr     eax, 0Eh
0x10039c21  and     eax, 1
0x10039c24  cmp     eax, [ebp+var_8]
0x10039c27  jz      short loc_10039C5F
0x10039c29  mov     esi, ecx
0x10039c2b  shr     esi, 5
0x10039c2e  and     esi, 1FFh
0x10039c34  jbe     short loc_10039C4A
0x10039c36  xor     eax, eax
0x10039c38  mov     [edi+4], esi
0x10039c3b  test    ebx, ebx
0x10039c3d  cmovz   eax, [ebp+var_C]
0x10039c41  and     ecx, 0FFFFC01Fh
0x10039c47  mov     [edi+8], eax
0x10039c4a  xor     eax, eax
0x10039c4c  mov     esi, 4000h
0x10039c51  cmp     ebx, 4
0x10039c54  cmovz   eax, esi
0x10039c57  and     ecx, 0FFFFBFFFh
0x10039c5d  or      ecx, eax
0x10039c5f  mov     eax, ecx
0x10039c61  shr     eax, 5
0x10039c64  and     eax, 1FFh
0x10039c69  lea     esi, [eax+1]
0x10039c6c  cmp     esi, 1FFh
0x10039c72  ja      short loc_10039C78
0x10039c74  cmp     esi, eax
0x10039c76  jnb     short loc_10039C83
0x10039c78  mov     esi, 1
0x10039c7d  mov     [edi+8], ebx
0x10039c80  mov     [edi+4], eax
0x10039c83  shl     esi, 5
0x10039c86  mov     eax, edx
0x10039c88  xor     esi, ecx
0x10039c8a  and     esi, 3FE0h
0x10039c90  xor     ecx, esi
0x10039c92  mov     esi, [ebp+var_4]
0x10039c95  lock cmpxchg [esi], ecx
0x10039c99  cmp     eax, edx
0x10039c9b  jz      short loc_10039CA4
0x10039c9d  mov     edx, eax
0x10039c9f  jmp     loc_10039C10
0x10039ca4  not     edx
0x10039ca6  mov     dword ptr [edi+10h], 0
0x10039cad  and     edx, 1
0x10039cb0  mov     eax, edi
0x10039cb2  mov     [edi], edx
0x10039cb4  pop     edi
0x10039cb5  pop     esi
0x10039cb6  pop     ebx
0x10039cb7  mov     esp, ebp
0x10039cb9  pop     ebp
0x10039cba  retn    0Ch
0x10039cbd  mov     edx, [eax]; jumptable 10039B6C cases 1,5
0x10039cbf  xor     eax, eax
0x10039cc1  cmp     ebx, 5
0x10039cc4  setz    al
0x10039cc7  mov     [ebp+var_C], eax
0x10039cca  nop     word ptr [eax+eax+00h]
0x10039cd0  mov     ecx, edx
0x10039cd2  mov     dword ptr [edi+4], 0
0x10039cd9  or      ecx, 1
0x10039cdc  mov     eax, ecx
0x10039cde  shr     eax, 16h
0x10039ce1  and     eax, 1
0x10039ce4  cmp     eax, [ebp+var_C]
0x10039ce7  jz      short loc_10039D23
0x10039ce9  mov     esi, ecx
0x10039ceb  shr     esi, 0Fh
0x10039cee  and     esi, 7Fh
0x10039cf1  jbe     short loc_10039D0E
0x10039cf3  xor     eax, eax
0x10039cf5  mov     [edi+4], esi
0x10039cf8  cmp     ebx, 1
0x10039cfb  setz    al
0x10039cfe  and     ecx, 0FFC07FFFh
0x10039d04  lea     eax, ds:1[eax*4]
0x10039d0b  mov     [edi+8], eax
0x10039d0e  xor     eax, eax
0x10039d10  mov     esi, 400000h
0x10039d15  cmp     ebx, 5
0x10039d18  cmovz   eax, esi
0x10039d1b  and     ecx, 0FFBFFFFFh
0x10039d21  or      ecx, eax
0x10039d23  mov     esi, ecx
0x10039d25  shr     esi, 0Fh
0x10039d28  and     esi, 7Fh
0x10039d2b  lea     eax, [esi+1]
0x10039d2e  cmp     eax, 7Fh
0x10039d31  ja      short loc_10039D37
0x10039d33  cmp     eax, esi
0x10039d35  jnb     short loc_10039D42
0x10039d37  mov     eax, 1
0x10039d3c  mov     [edi+8], ebx
0x10039d3f  mov     [edi+4], esi
0x10039d42  mov     esi, [ebp+var_4]
0x10039d45  shl     eax, 0Fh
0x10039d48  xor     eax, ecx
0x10039d4a  and     eax, 3F8000h
0x10039d4f  xor     ecx, eax
0x10039d51  mov     eax, edx
0x10039d53  lock cmpxchg [esi], ecx
0x10039d57  cmp     eax, edx
0x10039d59  jz      loc_10039CA4
0x10039d5f  mov     edx, eax
0x10039d61  jmp     loc_10039CD0
0x10039d66  lea     esi, [ebx-140h]; jumptable 10039B6C default case
0x10039d6c  mov     [ebp+var_C], esi
0x10039d6f  cmp     esi, 40h ; '@'
0x10039d72  jge     short loc_10039DCF
0x10039d74  mov     edx, [eax+4]
0x10039d77  mov     ebx, esi
0x10039d79  shl     ebx, 5
0x10039d7c  nop     dword ptr [eax+00h]
0x10039d80  test    dl, 10h
0x10039d83  jz      short loc_10039D98
0x10039d85  mov     eax, edx
0x10039d87  shr     eax, 5
0x10039d8a  and     eax, 3Fh
0x10039d8d  cmp     eax, esi
0x10039d8f  jnz     short loc_10039D98
0x10039d91  mov     eax, 1
0x10039d96  jmp     short loc_10039D9A
0x10039d98  xor     eax, eax
0x10039d9a  mov     ecx, ebx
0x10039d9c  mov     [edi+10h], eax
0x10039d9f  mov     edi, [ebp+var_4]
0x10039da2  xor     ecx, edx
0x10039da4  and     ecx, 7E0h
0x10039daa  mov     eax, edx
0x10039dac  xor     ecx, edx
0x10039dae  add     edi, 4
0x10039db1  or      ecx, 10h
0x10039db4  lock cmpxchg [edi], ecx
0x10039db8  mov     edi, [ebp+arg_0]
0x10039dbb  mov     esi, [ebp+var_C]
0x10039dbe  cmp     eax, edx
0x10039dc0  jz      short loc_10039DC6
0x10039dc2  mov     edx, eax
0x10039dc4  jmp     short loc_10039D80
0x10039dc6  cmp     dword ptr [edi+10h], 0
0x10039dca  mov     ebx, [ebp+var_8]
0x10039dcd  jnz     short loc_10039DE0
0x10039dcf  mov     [edi+8], ebx
0x10039dd2  mov     dword ptr [edi+4], 1
0x10039dd9  mov     dword ptr [edi+0Ch], 0
0x10039de0  mov     eax, edi
0x10039de2  pop     edi
0x10039de3  pop     esi
0x10039de4  pop     ebx
0x10039de5  mov     esp, ebp
0x10039de7  pop     ebp
0x10039de8  retn    0Ch
```
