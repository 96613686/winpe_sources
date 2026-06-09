# TknGetToken(x)

- ea: `0x100b8ba0`
- end: `0x100b8f5d`
- name: `_TknGetToken@4`
- size: `957`
- prototype: ``
- caller_count: `55`
- callee_count: `2`
- tags: ``

## callers

- `0x10091469`
- `0x10091568`
- `0x10091780`
- `0x10091900`
- `0x10091b0d`
- `0x10091c60`
- `0x10091cea`
- `0x10091d60`
- `0x10091e74`
- `0x10091fd6`
- `0x100920e0`
- `0x100925bc`
- `0x100929d2`
- `0x10092a5b`
- `0x10092c7a`
- `0x10093f92`
- `0x1009406a`
- `0x1009426a`
- `0x100943e0`
- `0x10094983`
- `0x10094c23`
- `0x10094d07`
- `0x100a3607`
- `0x100b272a`
- `0x100b5b87`
- `0x100b8ac3`
- `0x100b8f63`
- `0x100b9805`
- `0x100b98cf`
- `0x100b9e74`
- `0x100cb5b5`
- `0x100cb693`
- `0x100cb7d2`
- `0x100cbb07`
- `0x100cbd20`
- `0x100cbf9d`
- `0x100cc0f5`
- `0x100cc2f1`
- `0x100cc941`
- `0x100ccc41`
- `0x100ccdd1`
- `0x100ccf31`
- `0x100cd276`
- `0x100cd4a6`
- `0x100cd533`
- `0x100cd825`
- `0x100cd967`
- `0x100cdd42`
- `0x100ce00f`
- `0x100ce338`

## callees

- `0x10012af0`
- `0x100b8ba0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8c32`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8c60`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8dc0`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8def`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8e13`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8c32`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8c60`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8dc0`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8def`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8e13`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x100b8d26`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x100b8d26`

## pseudocode

```c
int __thiscall TknGetToken(_DWORD *this)
{
  _DWORD *v1; // esi
  _WORD *v2; // edx
  unsigned int v3; // edi
  const wchar_t *i; // ecx
  int v5; // eax
  int v6; // ebx
  unsigned __int16 *v7; // eax
  int v8; // ecx
  int result; // eax
  unsigned __int8 *v10; // ecx
  unsigned int v11; // ebx
  _BYTE *v12; // edi
  int v13; // eax
  unsigned __int8 *v14; // edi
  unsigned __int8 *v15; // edx
  int v16; // eax
  int v17; // esi
  unsigned int v18; // ebx
  int v19; // eax
  wchar_t *m; // edi
  _WORD *v21; // ecx
  unsigned int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // ebx
  int v27; // eax
  int v28; // ebx
  wint_t *v29; // edi
  _WORD *k; // ecx
  __int16 v31; // cx
  __int16 *v32; // ecx
  int j; // edx
  __int16 *v34; // eax
  __int16 v35; // ax
  __int16 *v36; // ecx
  int v37; // [esp+Ch] [ebp-18h]
  __int16 *v39; // [esp+18h] [ebp-Ch]
  _WORD *v40; // [esp+1Ch] [ebp-8h]
  int v41; // [esp+1Ch] [ebp-8h]
  int v42; // [esp+20h] [ebp-4h]
  int v43; // [esp+20h] [ebp-4h]

  v1 = this;
  v2 = (_WORD *)this[3];
  v3 = this[4];
  this[6] = this[5];
  this[8] = this[7];
  v40 = v2;
  if ( (unsigned int)v2 < v3 )
  {
LABEL_2:
    for ( i = wszBlanks; i < (const wchar_t *)&word_1000D40A; ++i )
    {
      if ( *i == *v2 )
      {
        if ( (unsigned int)++v2 < v3 )
          goto LABEL_2;
        break;
      }
    }
    v40 = v2;
  }
  v1[3] = v2;
  if ( (unsigned int)v2 < v3 && (v5 = (unsigned __int16)*v2, (_WORD)v5) )
  {
    v6 = (unsigned __int16)*v2;
    if ( v5 == 39 || v5 == 34 )
    {
      v32 = v2 + 1;
      for ( j = 2; ; j += 2 )
      {
        v1[3] = v32;
        if ( (unsigned int)v32 >= v3 )
          break;
        v34 = v32;
        v39 = v32;
        do
        {
          v35 = *v34;
          v36 = v39 + 1;
          v1[3] = v39 + 1;
          if ( v35 == (_WORD)v6 )
            break;
          ++j;
          ++v39;
          v34 = v36;
        }
        while ( (unsigned int)v36 < v3 );
        if ( (unsigned int)v36 >= v3 || *v36 != (_WORD)v6 )
          break;
        v32 = v36 + 1;
      }
      v1[5] = v40;
      v1[7] = j;
      return 256;
    }
    if ( (_WORD)v6 == 96 || v6 == 91 )
    {
      for ( k = v2 + 1; ; ++k )
      {
        v1[3] = k;
        if ( (unsigned int)k >= v3 )
          break;
        if ( *k == 96 || *k == 93 )
        {
          v1[3] = ++k;
          break;
        }
      }
      v1[5] = v2;
      v1[7] = k - v2;
      v31 = *(k - 1);
      if ( v31 == 96 )
        return 256;
      result = 256;
      if ( v31 != 93 )
        return 0;
    }
    else
    {
      if ( !_iswctype(v6, 4u)
        && (v6 != 45 && (_WORD)v6 != 43 && (_WORD)v6 != 46 || !_iswctype(*(_WORD *)(v1[3] + 2), 4u)) )
      {
        if ( ((unsigned __int8)(1 << (v6 & 7)) & (unsigned __int8)mpbfValidName[(unsigned __int8)v6 >> 3]) == 0
          && (unsigned __int16)v6 < 0x80u
          && v6 != 64
          && v6 != 58 )
        {
          v7 = (unsigned __int16 *)v1[3];
          v1[5] = v7;
          v1[7] = 1;
          v8 = *v7;
          v1[3] = v7 + 1;
          return v8;
        }
        v10 = (unsigned __int8 *)v1[3];
        v11 = 1;
        v41 = 1;
        v12 = v10 + 2;
        v1[3] = v10 + 2;
        if ( (unsigned int)(v10 + 2) < v1[4] )
        {
          do
          {
            if ( ((unsigned __int8)(1 << (*v12 & 7)) & (unsigned __int8)mpbfValidName[(unsigned __int8)*v12 >> 3]) == 0
              && *(_WORD *)v12 < 0x80u )
            {
              break;
            }
            v12 += 2;
            ++v11;
            v1[3] = v12;
          }
          while ( (unsigned int)v12 < v1[4] );
          v41 = v11;
        }
        v13 = 4;
        v1[5] = v10;
        v1[7] = v11;
        v14 = v10;
        if ( v11 < 4 )
          v13 = v11;
        v15 = &v10[2 * v13];
        v16 = 0;
        if ( v10 < v15 )
        {
          v17 = 0;
          v18 = (unsigned int)v15;
          do
          {
            v19 = _toupper(*v14);
            v14 += 2;
            v17 += v19;
          }
          while ( (unsigned int)v14 < v18 );
          v11 = v41;
          v42 = v17;
          v1 = this;
          v16 = v42;
        }
        for ( m = rgprsvdwd[(int)(v16 + 2 * v11) % 43]; m; m = (wchar_t *)*((_DWORD *)m + 2) )
        {
          v21 = *(_WORD **)m;
          while ( *v21++ )
            ;
          if ( v11 == ((int)v21 - *(_DWORD *)m - 2) >> 1 && !WCSNICMP(v11) )
          {
            v23 = v1[9];
            if ( v23 >= 0x5C )
              return *((_DWORD *)m + 1);
            if ( *((_DWORD *)m + 4) <= v23 )
            {
              v24 = v1[1];
              if ( (v24 & 2) != 0 || (m[6] & 2) != 0 )
                return *((_DWORD *)m + 1);
              v25 = v24 << 31 >> 31;
              if ( (m[6] & 1) != 0 )
              {
                if ( v25 )
                  return *((_DWORD *)m + 1);
              }
              else if ( !v25 )
              {
                return *((_DWORD *)m + 1);
              }
            }
          }
        }
        return 256;
      }
      v26 = -(_iswctype(v6, 4u) != 0);
      v37 = v1[3];
      v27 = 1;
      v28 = -v26;
      v43 = 1;
      v29 = (wint_t *)(v37 + 2);
      v1[3] = v37 + 2;
      if ( (unsigned int)(v37 + 2) < v1[4] )
      {
        do
        {
          if ( !_iswctype(*v29, 4u) )
          {
            v29 = (wint_t *)v1[3];
            if ( *v29 != 46 )
              break;
          }
          v28 = v28 && _iswctype(*(_WORD *)v1[3], 4u);
          ++v43;
          v29 = (wint_t *)(v1[3] + 2);
          v1[3] = v29;
        }
        while ( (unsigned int)v29 < v1[4] );
        v27 = v43;
        if ( (unsigned int)v29 < v1[4] )
        {
          do
          {
            if ( ((unsigned __int8)(1 << (*(_BYTE *)v29 & 7))
                & (unsigned __int8)mpbfValidName[*(unsigned __int8 *)v29 >> 3]) == 0
              && *v29 < 0x80u )
            {
              break;
            }
            v28 = 0;
            ++v29;
            ++v43;
            v1[3] = v29;
          }
          while ( (unsigned int)v29 < v1[4] );
          v27 = v43;
        }
      }
      v1[5] = v37;
      v1[7] = v27;
      if ( !v28 )
        return 256;
      result = 257;
      if ( (v1[1] & 8) == 0 )
        return 256;
    }
  }
  else
  {
    v1[3] = v3;
    v1[5] = v3;
    v1[7] = 0;
    return 22;
  }
  return result;
}

```

## disassembly

```asm
0x100b8ba0  mov     edi, edi
0x100b8ba2  push    ebp
0x100b8ba3  mov     ebp, esp
0x100b8ba5  sub     esp, 18h
0x100b8ba8  push    ebx
0x100b8ba9  push    esi
0x100b8baa  mov     esi, ecx
0x100b8bac  push    edi
0x100b8bad  mov     [ebp+var_14], esi
0x100b8bb0  mov     eax, [esi+14h]
0x100b8bb3  mov     edx, [esi+0Ch]
0x100b8bb6  mov     edi, [esi+10h]
0x100b8bb9  mov     [esi+18h], eax
0x100b8bbc  mov     eax, [esi+1Ch]
0x100b8bbf  mov     [esi+20h], eax
0x100b8bc2  mov     [ebp+var_8], edx
0x100b8bc5  cmp     edx, edi
0x100b8bc7  jnb     short loc_100B8BED
0x100b8bc9  mov     ecx, offset _wszBlanks; " \t\n\r"
0x100b8bce  cmp     ecx, offset word_1000D40A
0x100b8bd4  jnb     short loc_100B8BEA
0x100b8bd6  mov     ax, [ecx]
0x100b8bd9  cmp     ax, [edx]
0x100b8bdc  jz      short loc_100B8BE3
0x100b8bde  add     ecx, 2
0x100b8be1  jmp     short loc_100B8BCE
0x100b8be3  add     edx, 2
0x100b8be6  cmp     edx, edi
0x100b8be8  jb      short loc_100B8BC9
0x100b8bea  mov     [ebp+var_8], edx
0x100b8bed  mov     [esi+0Ch], edx
0x100b8bf0  cmp     edx, edi
0x100b8bf2  jnb     loc_100B8F48
0x100b8bf8  movzx   eax, word ptr [edx]
0x100b8bfb  test    ax, ax
0x100b8bfe  jz      loc_100B8F48
0x100b8c04  mov     ebx, eax
0x100b8c06  cmp     ebx, 27h ; '''
0x100b8c09  jz      loc_100B8EF1
0x100b8c0f  cmp     ebx, 22h ; '"'
0x100b8c12  jz      loc_100B8EF1
0x100b8c18  push    60h ; '`'
0x100b8c1a  pop     eax
0x100b8c1b  cmp     bx, ax
0x100b8c1e  jz      loc_100B8E99
0x100b8c24  cmp     ebx, 5Bh ; '['
0x100b8c27  jz      loc_100B8E99
0x100b8c2d  push    4
0x100b8c2f  pop     edi
0x100b8c30  push    edi; Type
0x100b8c31  push    ebx; C
0x100b8c32  call    ds:__imp__iswctype
0x100b8c38  pop     ecx
0x100b8c39  pop     ecx
0x100b8c3a  push    2Eh ; '.'
0x100b8c3c  pop     ecx
0x100b8c3d  test    eax, eax
0x100b8c3f  jnz     loc_100B8DBE
0x100b8c45  push    2Bh ; '+'
0x100b8c47  pop     eax
0x100b8c48  cmp     ebx, 2Dh ; '-'
0x100b8c4b  jz      short loc_100B8C57
0x100b8c4d  cmp     bx, ax
0x100b8c50  jz      short loc_100B8C57
0x100b8c52  cmp     bx, cx
0x100b8c55  jnz     short loc_100B8C70
0x100b8c57  mov     eax, [esi+0Ch]
0x100b8c5a  push    edi; Type
0x100b8c5b  movzx   eax, word ptr [eax+2]
0x100b8c5f  push    eax; C
0x100b8c60  call    ds:__imp__iswctype
0x100b8c66  pop     ecx
0x100b8c67  pop     ecx
0x100b8c68  test    eax, eax
0x100b8c6a  jnz     loc_100B8DBE
0x100b8c70  movzx   edx, bl
0x100b8c73  xor     edi, edi
0x100b8c75  inc     edi
0x100b8c76  mov     ecx, edx
0x100b8c78  and     ecx, 7
0x100b8c7b  shr     edx, 3
0x100b8c7e  mov     eax, edi
0x100b8c80  shl     eax, cl
0x100b8c82  lea     ecx, [edi+7Fh]
0x100b8c85  test    ds:_mpbfValidName[edx], al
0x100b8c8b  jnz     short loc_100B8CB5
0x100b8c8d  cmp     bx, cx
0x100b8c90  jnb     short loc_100B8CB5
0x100b8c92  cmp     ebx, 40h ; '@'
0x100b8c95  jz      short loc_100B8CB5
0x100b8c97  cmp     ebx, 3Ah ; ':'
0x100b8c9a  jz      short loc_100B8CB5
0x100b8c9c  mov     eax, [esi+0Ch]
0x100b8c9f  mov     [esi+14h], eax
0x100b8ca2  mov     [esi+1Ch], edi
0x100b8ca5  movzx   ecx, word ptr [eax]
0x100b8ca8  add     eax, 2
0x100b8cab  mov     [esi+0Ch], eax
0x100b8cae  mov     eax, ecx
0x100b8cb0  jmp     loc_100B8F58
0x100b8cb5  mov     ecx, [esi+0Ch]
0x100b8cb8  mov     ebx, edi
0x100b8cba  mov     [ebp+var_C], ecx
0x100b8cbd  mov     [ebp+var_8], ebx
0x100b8cc0  lea     edi, [ecx+2]
0x100b8cc3  mov     [esi+0Ch], edi
0x100b8cc6  cmp     edi, [esi+10h]
0x100b8cc9  jnb     short loc_100B8CFF
0x100b8ccb  movzx   edx, byte ptr [edi]
0x100b8cce  xor     eax, eax
0x100b8cd0  mov     ecx, edx
0x100b8cd2  inc     eax
0x100b8cd3  and     ecx, 7
0x100b8cd6  shr     edx, 3
0x100b8cd9  shl     eax, cl
0x100b8cdb  test    ds:_mpbfValidName[edx], al
0x100b8ce1  jnz     short loc_100B8CED
0x100b8ce3  mov     eax, 80h
0x100b8ce8  cmp     [edi], ax
0x100b8ceb  jb      short loc_100B8CF9
0x100b8ced  add     edi, 2
0x100b8cf0  inc     ebx
0x100b8cf1  mov     [esi+0Ch], edi
0x100b8cf4  cmp     edi, [esi+10h]
0x100b8cf7  jb      short loc_100B8CCB
0x100b8cf9  mov     ecx, [ebp+var_C]
0x100b8cfc  mov     [ebp+var_8], ebx
0x100b8cff  push    4
0x100b8d01  pop     eax
0x100b8d02  cmp     ebx, eax
0x100b8d04  mov     [esi+14h], ecx
0x100b8d07  mov     [esi+1Ch], ebx
0x100b8d0a  mov     edi, ecx
0x100b8d0c  cmovb   eax, ebx
0x100b8d0f  lea     edx, [ecx+eax*2]
0x100b8d12  xor     eax, eax
0x100b8d14  mov     [ebp+var_10], edx
0x100b8d17  mov     [ebp+var_18], eax
0x100b8d1a  cmp     ecx, edx
0x100b8d1c  jnb     short loc_100B8D42
0x100b8d1e  mov     esi, eax
0x100b8d20  mov     ebx, edx
0x100b8d22  movzx   eax, byte ptr [edi]
0x100b8d25  push    eax; C
0x100b8d26  call    ds:__imp__toupper
0x100b8d2c  add     edi, 2
0x100b8d2f  add     esi, eax
0x100b8d31  pop     ecx
0x100b8d32  cmp     edi, ebx
0x100b8d34  jb      short loc_100B8D22
0x100b8d36  mov     ebx, [ebp+var_8]
0x100b8d39  mov     [ebp+var_4], esi
0x100b8d3c  mov     esi, [ebp+var_14]
0x100b8d3f  mov     eax, [ebp+var_4]
0x100b8d42  lea     eax, [eax+ebx*2]
0x100b8d45  push    2Bh ; '+'
0x100b8d47  cdq
0x100b8d48  pop     ecx
0x100b8d49  idiv    ecx
0x100b8d4b  mov     edi, ds:_rgprsvdwd[edx*4]
0x100b8d52  jmp     short loc_100B8DB5
0x100b8d54  mov     ecx, [edi]
0x100b8d56  lea     edx, [ecx+2]
0x100b8d59  mov     ax, [ecx]
0x100b8d5c  add     ecx, 2
0x100b8d5f  cmp     ax, word ptr [ebp+var_18]
0x100b8d63  jnz     short loc_100B8D59
0x100b8d65  sub     ecx, edx
0x100b8d67  sar     ecx, 1
0x100b8d69  cmp     ebx, ecx
0x100b8d6b  jnz     short loc_100B8DB2
0x100b8d6d  mov     edx, [edi]
0x100b8d6f  mov     ecx, [ebp+var_C]
0x100b8d72  push    ebx
0x100b8d73  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100b8d78  test    eax, eax
0x100b8d7a  jnz     short loc_100B8DB2
0x100b8d7c  mov     eax, [esi+24h]
0x100b8d7f  cmp     eax, 5Ch ; '\'
0x100b8d82  jnb     short loc_100B8DA6
0x100b8d84  cmp     [edi+10h], eax
0x100b8d87  ja      short loc_100B8DB2
0x100b8d89  mov     eax, [esi+4]
0x100b8d8c  test    al, 2
0x100b8d8e  jnz     short loc_100B8DA6
0x100b8d90  test    byte ptr [edi+0Ch], 2
0x100b8d94  jnz     short loc_100B8DA6
0x100b8d96  shl     eax, 1Fh
0x100b8d99  sar     eax, 1Fh
0x100b8d9c  test    byte ptr [edi+0Ch], 1
0x100b8da0  jz      short loc_100B8DAE
0x100b8da2  test    eax, eax
0x100b8da4  jz      short loc_100B8DB2
0x100b8da6  mov     eax, [edi+4]
0x100b8da9  jmp     loc_100B8F58
0x100b8dae  test    eax, eax
0x100b8db0  jz      short loc_100B8DA6
0x100b8db2  mov     edi, [edi+8]
0x100b8db5  test    edi, edi
0x100b8db7  jnz     short loc_100B8D54
0x100b8db9  jmp     loc_100B8F41
0x100b8dbe  push    edi; Type
0x100b8dbf  push    ebx; C
0x100b8dc0  call    ds:__imp__iswctype
0x100b8dc6  pop     ecx
0x100b8dc7  neg     eax
0x100b8dc9  pop     ecx
0x100b8dca  mov     ecx, [esi+0Ch]
0x100b8dcd  sbb     ebx, ebx
0x100b8dcf  xor     eax, eax
0x100b8dd1  mov     [ebp+var_18], ecx
0x100b8dd4  inc     eax
0x100b8dd5  neg     ebx
0x100b8dd7  mov     [ebp+var_4], eax
0x100b8dda  lea     edi, [ecx+2]
0x100b8ddd  mov     [esi+0Ch], edi
0x100b8de0  cmp     edi, [esi+10h]
0x100b8de3  jnb     loc_100B8E74
0x100b8de9  movzx   eax, word ptr [edi]
0x100b8dec  push    4; Type
0x100b8dee  push    eax; C
0x100b8def  call    ds:__imp__iswctype
0x100b8df5  pop     ecx
0x100b8df6  pop     ecx
0x100b8df7  test    eax, eax
0x100b8df9  jnz     short loc_100B8E06
0x100b8dfb  mov     edi, [esi+0Ch]
0x100b8dfe  push    2Eh ; '.'
0x100b8e00  pop     eax
0x100b8e01  cmp     [edi], ax
0x100b8e04  jnz     short loc_100B8E37
0x100b8e06  test    ebx, ebx
0x100b8e08  jz      short loc_100B8E24
0x100b8e0a  mov     eax, [esi+0Ch]
0x100b8e0d  push    4; Type
0x100b8e0f  movzx   eax, word ptr [eax]
0x100b8e12  push    eax; C
0x100b8e13  call    ds:__imp__iswctype
0x100b8e19  pop     ecx
0x100b8e1a  pop     ecx
0x100b8e1b  test    eax, eax
0x100b8e1d  jz      short loc_100B8E24
0x100b8e1f  xor     ebx, ebx
0x100b8e21  inc     ebx
0x100b8e22  jmp     short loc_100B8E26
0x100b8e24  xor     ebx, ebx
0x100b8e26  mov     edi, [esi+0Ch]
0x100b8e29  inc     [ebp+var_4]
0x100b8e2c  add     edi, 2
0x100b8e2f  mov     [esi+0Ch], edi
0x100b8e32  cmp     edi, [esi+10h]
0x100b8e35  jb      short loc_100B8DE9
0x100b8e37  mov     eax, [ebp+var_4]
0x100b8e3a  cmp     edi, [esi+10h]
0x100b8e3d  jnb     short loc_100B8E74
0x100b8e3f  movzx   edx, byte ptr [edi]
0x100b8e42  xor     eax, eax
0x100b8e44  mov     ecx, edx
0x100b8e46  inc     eax
0x100b8e47  and     ecx, 7
0x100b8e4a  shr     edx, 3
0x100b8e4d  shl     eax, cl
0x100b8e4f  test    ds:_mpbfValidName[edx], al
0x100b8e55  jnz     short loc_100B8E61
0x100b8e57  mov     eax, 80h
0x100b8e5c  cmp     [edi], ax
0x100b8e5f  jb      short loc_100B8E71
0x100b8e61  xor     ebx, ebx
0x100b8e63  add     edi, 2
0x100b8e66  inc     [ebp+var_4]
0x100b8e69  mov     [esi+0Ch], edi
0x100b8e6c  cmp     edi, [esi+10h]
0x100b8e6f  jb      short loc_100B8E3F
0x100b8e71  mov     eax, [ebp+var_4]
0x100b8e74  mov     ecx, [ebp+var_18]
0x100b8e77  mov     [esi+14h], ecx
0x100b8e7a  mov     [esi+1Ch], eax
0x100b8e7d  test    ebx, ebx
0x100b8e7f  jz      loc_100B8F41
0x100b8e85  test    byte ptr [esi+4], 8
0x100b8e89  mov     eax, 101h
0x100b8e8e  jnz     loc_100B8F58
0x100b8e94  jmp     loc_100B8F41
0x100b8e99  push    60h ; '`'
0x100b8e9b  lea     ecx, [edx+2]
0x100b8e9e  mov     [ebp+var_18], 5Dh ; ']'
0x100b8ea5  pop     ebx
0x100b8ea6  jmp     short loc_100B8EB9
0x100b8ea8  movzx   eax, word ptr [ecx]
0x100b8eab  cmp     ax, bx
0x100b8eae  jz      short loc_100B8EC2
0x100b8eb0  cmp     ax, word ptr [ebp+var_18]
0x100b8eb4  jz      short loc_100B8EC2
0x100b8eb6  add     ecx, 2
0x100b8eb9  mov     [esi+0Ch], ecx
0x100b8ebc  cmp     ecx, edi
0x100b8ebe  jb      short loc_100B8EA8
0x100b8ec0  jmp     short loc_100B8EC8
0x100b8ec2  add     ecx, 2
0x100b8ec5  mov     [esi+0Ch], ecx
  ... truncated ...
```
