# TknGetToken(x)

- ea: `0x100b8a10`
- end: `0x100b8dcd`
- name: `_TknGetToken@4`
- size: `957`
- prototype: `int __thiscall(_DWORD)`
- caller_count: `55`
- callee_count: `2`
- tags: ``

## callers

- `0x100912d9`
- `0x100913d8`
- `0x100915f0`
- `0x10091770`
- `0x1009197d`
- `0x10091ad0`
- `0x10091b5a`
- `0x10091bd0`
- `0x10091ce4`
- `0x10091e46`
- `0x10091f50`
- `0x1009242c`
- `0x10092842`
- `0x100928cb`
- `0x10092aea`
- `0x10093e02`
- `0x10093eda`
- `0x100940da`
- `0x10094250`
- `0x100947f3`
- `0x10094a93`
- `0x10094b77`
- `0x100a3477`
- `0x100b259b`
- `0x100b59f7`
- `0x100b8933`
- `0x100b8dd3`
- `0x100b9675`
- `0x100b973f`
- `0x100b9ce4`
- `0x100cb425`
- `0x100cb503`
- `0x100cb642`
- `0x100cb977`
- `0x100cbb90`
- `0x100cbe0d`
- `0x100cbf65`
- `0x100cc161`
- `0x100cc7b1`
- `0x100ccab1`
- `0x100ccc41`
- `0x100ccda1`
- `0x100cd0e6`
- `0x100cd316`
- `0x100cd3a3`
- `0x100cd695`
- `0x100cd7d7`
- `0x100cdbb2`
- `0x100cde7f`
- `0x100ce1a8`

## callees

- `0x100129b0`
- `0x100b8a10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8aa2`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8ad0`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8c30`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8c5f`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8c83`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8aa2`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8ad0`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8c30`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8c5f`
- `api-ms-win-crt-private-l1-1-0!_o_iswctype` at `0x100b8c83`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x100b8b96`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x100b8b96`

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
    for ( i = wszBlanks; i < (const wchar_t *)&word_1000D31A; ++i )
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
0x100b8a10  mov     edi, edi
0x100b8a12  push    ebp
0x100b8a13  mov     ebp, esp
0x100b8a15  sub     esp, 18h
0x100b8a18  push    ebx
0x100b8a19  push    esi
0x100b8a1a  mov     esi, ecx
0x100b8a1c  push    edi
0x100b8a1d  mov     [ebp+var_14], esi
0x100b8a20  mov     eax, [esi+14h]
0x100b8a23  mov     edx, [esi+0Ch]
0x100b8a26  mov     edi, [esi+10h]
0x100b8a29  mov     [esi+18h], eax
0x100b8a2c  mov     eax, [esi+1Ch]
0x100b8a2f  mov     [esi+20h], eax
0x100b8a32  mov     [ebp+var_8], edx
0x100b8a35  cmp     edx, edi
0x100b8a37  jnb     short loc_100B8A5D
0x100b8a39  mov     ecx, offset _wszBlanks; " \t\n\r"
0x100b8a3e  cmp     ecx, offset word_1000D31A
0x100b8a44  jnb     short loc_100B8A5A
0x100b8a46  mov     ax, [ecx]
0x100b8a49  cmp     ax, [edx]
0x100b8a4c  jz      short loc_100B8A53
0x100b8a4e  add     ecx, 2
0x100b8a51  jmp     short loc_100B8A3E
0x100b8a53  add     edx, 2
0x100b8a56  cmp     edx, edi
0x100b8a58  jb      short loc_100B8A39
0x100b8a5a  mov     [ebp+var_8], edx
0x100b8a5d  mov     [esi+0Ch], edx
0x100b8a60  cmp     edx, edi
0x100b8a62  jnb     loc_100B8DB8
0x100b8a68  movzx   eax, word ptr [edx]
0x100b8a6b  test    ax, ax
0x100b8a6e  jz      loc_100B8DB8
0x100b8a74  mov     ebx, eax
0x100b8a76  cmp     ebx, 27h ; '''
0x100b8a79  jz      loc_100B8D61
0x100b8a7f  cmp     ebx, 22h ; '"'
0x100b8a82  jz      loc_100B8D61
0x100b8a88  push    60h ; '`'
0x100b8a8a  pop     eax
0x100b8a8b  cmp     bx, ax
0x100b8a8e  jz      loc_100B8D09
0x100b8a94  cmp     ebx, 5Bh ; '['
0x100b8a97  jz      loc_100B8D09
0x100b8a9d  push    4
0x100b8a9f  pop     edi
0x100b8aa0  push    edi; Type
0x100b8aa1  push    ebx; C
0x100b8aa2  call    ds:__imp__iswctype
0x100b8aa8  pop     ecx
0x100b8aa9  pop     ecx
0x100b8aaa  push    2Eh ; '.'
0x100b8aac  pop     ecx
0x100b8aad  test    eax, eax
0x100b8aaf  jnz     loc_100B8C2E
0x100b8ab5  push    2Bh ; '+'
0x100b8ab7  pop     eax
0x100b8ab8  cmp     ebx, 2Dh ; '-'
0x100b8abb  jz      short loc_100B8AC7
0x100b8abd  cmp     bx, ax
0x100b8ac0  jz      short loc_100B8AC7
0x100b8ac2  cmp     bx, cx
0x100b8ac5  jnz     short loc_100B8AE0
0x100b8ac7  mov     eax, [esi+0Ch]
0x100b8aca  push    edi; Type
0x100b8acb  movzx   eax, word ptr [eax+2]
0x100b8acf  push    eax; C
0x100b8ad0  call    ds:__imp__iswctype
0x100b8ad6  pop     ecx
0x100b8ad7  pop     ecx
0x100b8ad8  test    eax, eax
0x100b8ada  jnz     loc_100B8C2E
0x100b8ae0  movzx   edx, bl
0x100b8ae3  xor     edi, edi
0x100b8ae5  inc     edi
0x100b8ae6  mov     ecx, edx
0x100b8ae8  and     ecx, 7
0x100b8aeb  shr     edx, 3
0x100b8aee  mov     eax, edi
0x100b8af0  shl     eax, cl
0x100b8af2  lea     ecx, [edi+7Fh]
0x100b8af5  test    ds:_mpbfValidName[edx], al
0x100b8afb  jnz     short loc_100B8B25
0x100b8afd  cmp     bx, cx
0x100b8b00  jnb     short loc_100B8B25
0x100b8b02  cmp     ebx, 40h ; '@'
0x100b8b05  jz      short loc_100B8B25
0x100b8b07  cmp     ebx, 3Ah ; ':'
0x100b8b0a  jz      short loc_100B8B25
0x100b8b0c  mov     eax, [esi+0Ch]
0x100b8b0f  mov     [esi+14h], eax
0x100b8b12  mov     [esi+1Ch], edi
0x100b8b15  movzx   ecx, word ptr [eax]
0x100b8b18  add     eax, 2
0x100b8b1b  mov     [esi+0Ch], eax
0x100b8b1e  mov     eax, ecx
0x100b8b20  jmp     loc_100B8DC8
0x100b8b25  mov     ecx, [esi+0Ch]
0x100b8b28  mov     ebx, edi
0x100b8b2a  mov     [ebp+var_C], ecx
0x100b8b2d  mov     [ebp+var_8], ebx
0x100b8b30  lea     edi, [ecx+2]
0x100b8b33  mov     [esi+0Ch], edi
0x100b8b36  cmp     edi, [esi+10h]
0x100b8b39  jnb     short loc_100B8B6F
0x100b8b3b  movzx   edx, byte ptr [edi]
0x100b8b3e  xor     eax, eax
0x100b8b40  mov     ecx, edx
0x100b8b42  inc     eax
0x100b8b43  and     ecx, 7
0x100b8b46  shr     edx, 3
0x100b8b49  shl     eax, cl
0x100b8b4b  test    ds:_mpbfValidName[edx], al
0x100b8b51  jnz     short loc_100B8B5D
0x100b8b53  mov     eax, 80h
0x100b8b58  cmp     [edi], ax
0x100b8b5b  jb      short loc_100B8B69
0x100b8b5d  add     edi, 2
0x100b8b60  inc     ebx
0x100b8b61  mov     [esi+0Ch], edi
0x100b8b64  cmp     edi, [esi+10h]
0x100b8b67  jb      short loc_100B8B3B
0x100b8b69  mov     ecx, [ebp+var_C]
0x100b8b6c  mov     [ebp+var_8], ebx
0x100b8b6f  push    4
0x100b8b71  pop     eax
0x100b8b72  cmp     ebx, eax
0x100b8b74  mov     [esi+14h], ecx
0x100b8b77  mov     [esi+1Ch], ebx
0x100b8b7a  mov     edi, ecx
0x100b8b7c  cmovb   eax, ebx
0x100b8b7f  lea     edx, [ecx+eax*2]
0x100b8b82  xor     eax, eax
0x100b8b84  mov     [ebp+var_10], edx
0x100b8b87  mov     [ebp+var_18], eax
0x100b8b8a  cmp     ecx, edx
0x100b8b8c  jnb     short loc_100B8BB2
0x100b8b8e  mov     esi, eax
0x100b8b90  mov     ebx, edx
0x100b8b92  movzx   eax, byte ptr [edi]
0x100b8b95  push    eax; C
0x100b8b96  call    ds:__imp__toupper
0x100b8b9c  add     edi, 2
0x100b8b9f  add     esi, eax
0x100b8ba1  pop     ecx
0x100b8ba2  cmp     edi, ebx
0x100b8ba4  jb      short loc_100B8B92
0x100b8ba6  mov     ebx, [ebp+var_8]
0x100b8ba9  mov     [ebp+var_4], esi
0x100b8bac  mov     esi, [ebp+var_14]
0x100b8baf  mov     eax, [ebp+var_4]
0x100b8bb2  lea     eax, [eax+ebx*2]
0x100b8bb5  push    2Bh ; '+'
0x100b8bb7  cdq
0x100b8bb8  pop     ecx
0x100b8bb9  idiv    ecx
0x100b8bbb  mov     edi, ds:_rgprsvdwd[edx*4]
0x100b8bc2  jmp     short loc_100B8C25
0x100b8bc4  mov     ecx, [edi]
0x100b8bc6  lea     edx, [ecx+2]
0x100b8bc9  mov     ax, [ecx]
0x100b8bcc  add     ecx, 2
0x100b8bcf  cmp     ax, word ptr [ebp+var_18]
0x100b8bd3  jnz     short loc_100B8BC9
0x100b8bd5  sub     ecx, edx
0x100b8bd7  sar     ecx, 1
0x100b8bd9  cmp     ebx, ecx
0x100b8bdb  jnz     short loc_100B8C22
0x100b8bdd  mov     edx, [edi]
0x100b8bdf  mov     ecx, [ebp+var_C]
0x100b8be2  push    ebx
0x100b8be3  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100b8be8  test    eax, eax
0x100b8bea  jnz     short loc_100B8C22
0x100b8bec  mov     eax, [esi+24h]
0x100b8bef  cmp     eax, 5Ch ; '\'
0x100b8bf2  jnb     short loc_100B8C16
0x100b8bf4  cmp     [edi+10h], eax
0x100b8bf7  ja      short loc_100B8C22
0x100b8bf9  mov     eax, [esi+4]
0x100b8bfc  test    al, 2
0x100b8bfe  jnz     short loc_100B8C16
0x100b8c00  test    byte ptr [edi+0Ch], 2
0x100b8c04  jnz     short loc_100B8C16
0x100b8c06  shl     eax, 1Fh
0x100b8c09  sar     eax, 1Fh
0x100b8c0c  test    byte ptr [edi+0Ch], 1
0x100b8c10  jz      short loc_100B8C1E
0x100b8c12  test    eax, eax
0x100b8c14  jz      short loc_100B8C22
0x100b8c16  mov     eax, [edi+4]
0x100b8c19  jmp     loc_100B8DC8
0x100b8c1e  test    eax, eax
0x100b8c20  jz      short loc_100B8C16
0x100b8c22  mov     edi, [edi+8]
0x100b8c25  test    edi, edi
0x100b8c27  jnz     short loc_100B8BC4
0x100b8c29  jmp     loc_100B8DB1
0x100b8c2e  push    edi; Type
0x100b8c2f  push    ebx; C
0x100b8c30  call    ds:__imp__iswctype
0x100b8c36  pop     ecx
0x100b8c37  neg     eax
0x100b8c39  pop     ecx
0x100b8c3a  mov     ecx, [esi+0Ch]
0x100b8c3d  sbb     ebx, ebx
0x100b8c3f  xor     eax, eax
0x100b8c41  mov     [ebp+var_18], ecx
0x100b8c44  inc     eax
0x100b8c45  neg     ebx
0x100b8c47  mov     [ebp+var_4], eax
0x100b8c4a  lea     edi, [ecx+2]
0x100b8c4d  mov     [esi+0Ch], edi
0x100b8c50  cmp     edi, [esi+10h]
0x100b8c53  jnb     loc_100B8CE4
0x100b8c59  movzx   eax, word ptr [edi]
0x100b8c5c  push    4; Type
0x100b8c5e  push    eax; C
0x100b8c5f  call    ds:__imp__iswctype
0x100b8c65  pop     ecx
0x100b8c66  pop     ecx
0x100b8c67  test    eax, eax
0x100b8c69  jnz     short loc_100B8C76
0x100b8c6b  mov     edi, [esi+0Ch]
0x100b8c6e  push    2Eh ; '.'
0x100b8c70  pop     eax
0x100b8c71  cmp     [edi], ax
0x100b8c74  jnz     short loc_100B8CA7
0x100b8c76  test    ebx, ebx
0x100b8c78  jz      short loc_100B8C94
0x100b8c7a  mov     eax, [esi+0Ch]
0x100b8c7d  push    4; Type
0x100b8c7f  movzx   eax, word ptr [eax]
0x100b8c82  push    eax; C
0x100b8c83  call    ds:__imp__iswctype
0x100b8c89  pop     ecx
0x100b8c8a  pop     ecx
0x100b8c8b  test    eax, eax
0x100b8c8d  jz      short loc_100B8C94
0x100b8c8f  xor     ebx, ebx
0x100b8c91  inc     ebx
0x100b8c92  jmp     short loc_100B8C96
0x100b8c94  xor     ebx, ebx
0x100b8c96  mov     edi, [esi+0Ch]
0x100b8c99  inc     [ebp+var_4]
0x100b8c9c  add     edi, 2
0x100b8c9f  mov     [esi+0Ch], edi
0x100b8ca2  cmp     edi, [esi+10h]
0x100b8ca5  jb      short loc_100B8C59
0x100b8ca7  mov     eax, [ebp+var_4]
0x100b8caa  cmp     edi, [esi+10h]
0x100b8cad  jnb     short loc_100B8CE4
0x100b8caf  movzx   edx, byte ptr [edi]
0x100b8cb2  xor     eax, eax
0x100b8cb4  mov     ecx, edx
0x100b8cb6  inc     eax
0x100b8cb7  and     ecx, 7
0x100b8cba  shr     edx, 3
0x100b8cbd  shl     eax, cl
0x100b8cbf  test    ds:_mpbfValidName[edx], al
0x100b8cc5  jnz     short loc_100B8CD1
0x100b8cc7  mov     eax, 80h
0x100b8ccc  cmp     [edi], ax
0x100b8ccf  jb      short loc_100B8CE1
0x100b8cd1  xor     ebx, ebx
0x100b8cd3  add     edi, 2
0x100b8cd6  inc     [ebp+var_4]
0x100b8cd9  mov     [esi+0Ch], edi
0x100b8cdc  cmp     edi, [esi+10h]
0x100b8cdf  jb      short loc_100B8CAF
0x100b8ce1  mov     eax, [ebp+var_4]
0x100b8ce4  mov     ecx, [ebp+var_18]
0x100b8ce7  mov     [esi+14h], ecx
0x100b8cea  mov     [esi+1Ch], eax
0x100b8ced  test    ebx, ebx
0x100b8cef  jz      loc_100B8DB1
0x100b8cf5  test    byte ptr [esi+4], 8
0x100b8cf9  mov     eax, 101h
0x100b8cfe  jnz     loc_100B8DC8
0x100b8d04  jmp     loc_100B8DB1
0x100b8d09  push    60h ; '`'
0x100b8d0b  lea     ecx, [edx+2]
0x100b8d0e  mov     [ebp+var_18], 5Dh ; ']'
0x100b8d15  pop     ebx
0x100b8d16  jmp     short loc_100B8D29
0x100b8d18  movzx   eax, word ptr [ecx]
0x100b8d1b  cmp     ax, bx
0x100b8d1e  jz      short loc_100B8D32
0x100b8d20  cmp     ax, word ptr [ebp+var_18]
0x100b8d24  jz      short loc_100B8D32
0x100b8d26  add     ecx, 2
0x100b8d29  mov     [esi+0Ch], ecx
0x100b8d2c  cmp     ecx, edi
0x100b8d2e  jb      short loc_100B8D18
0x100b8d30  jmp     short loc_100B8D38
0x100b8d32  add     ecx, 2
0x100b8d35  mov     [esi+0Ch], ecx
  ... truncated ...
```
