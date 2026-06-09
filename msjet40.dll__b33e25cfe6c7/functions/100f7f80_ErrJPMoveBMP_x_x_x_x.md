# ErrJPMoveBMP(x,x,x,x)

- ea: `0x100f7f80`
- end: `0x100f8305`
- name: `_ErrJPMoveBMP@16`
- size: `901`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x1003e870`
- `0x10043700`
- `0x10043e90`
- `0x10044330`
- `0x10044730`
- `0x10044b90`
- `0x10050000`
- `0x100b876c`
- `0x100b884b`
- `0x100f1c70`
- `0x100f1d30`
- `0x100f7f80`
- `0x100f8378`
- `0x100fda86`
- `0x100fdb64`

## import_xrefs

- `OLEAUT32!__imp__SysFreeString@4` at `0x100f80c9`
- `OLEAUT32!__imp__SysFreeString@4` at `0x100f80c9`
- `OLEAUT32!__imp__SysStringByteLen@4` at `0x100f8054`
- `OLEAUT32!__imp__SysStringByteLen@4` at `0x100f8054`

## pseudocode

```c
int __stdcall ErrJPMoveBMP(void *a1, int a2, int a3, char a4)
{
  unsigned int v4; // ebx
  int v5; // eax
  int *v6; // ebx
  int result; // eax
  int *v8; // esi
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  wchar_t *v14; // eax
  int v15; // ecx
  int *v16; // eax
  int v17; // eax
  int v18; // ecx
  _BYTE *v19; // esi
  _BYTE *v20; // ebx
  int v21; // edx
  bool v22; // zf
  int v23; // [esp-4h] [ebp-40h]
  int v24; // [esp-4h] [ebp-40h]
  int v25[3]; // [esp+Ch] [ebp-30h] BYREF
  BSTR bstr; // [esp+18h] [ebp-24h]
  unsigned int v27; // [esp+20h] [ebp-1Ch] BYREF
  int *v28; // [esp+24h] [ebp-18h] BYREF
  int BMP; // [esp+28h] [ebp-14h]
  int v30; // [esp+2Ch] [ebp-10h]
  int v31; // [esp+30h] [ebp-Ch]
  unsigned int v32; // [esp+34h] [ebp-8h] BYREF
  unsigned int v33; // [esp+38h] [ebp-4h]

  v4 = *(_DWORD *)(a2 + 32);
  v33 = v4;
  if ( a3 != 0x80000000 )
  {
    while ( 1 )
    {
LABEL_36:
      if ( *(_DWORD *)(a2 + 68) )
      {
        v32 = (*(int (__thiscall **)(_DWORD, _DWORD, _DWORD))(*(_DWORD *)(a2 + 64) + 16))(
                *(_DWORD *)(*(_DWORD *)(a2 + 64) + 16),
                *(_DWORD *)(a2 + 68),
                *(_DWORD *)(a2 + 4 * *(_DWORD *)(v4 + 140) + 72));
        *(_DWORD *)(a2 + 4 * *(_DWORD *)(v4 + 140) + 72) = v32;
        if ( v32 == -1 )
          return -1603;
        if ( (*(_BYTE *)(a2 + 40) & 1) == 0 || *(_DWORD *)(a2 + 332) || *(_DWORD *)(a2 + 316) )
        {
          result = ErrDispGotoBookmark(a1, *(_DWORD *)(a2 + 48), &v32, 4);
          if ( result < 0 )
          {
            v22 = result == -1601;
            goto LABEL_58;
          }
          if ( (a4 & 8) == 0 )
          {
            v18 = (*(int (__thiscall **)(_DWORD, _DWORD, unsigned int))(*(_DWORD *)(a2 + 64) + 16))(
                    *(_DWORD *)(*(_DWORD *)(a2 + 64) + 16),
                    *(_DWORD *)(a2 + 68),
                    v32);
            if ( v18 != -1 )
            {
              v27 = v32;
              v28 = (int *)v18;
              ErrDispReadAhead(&v27, 2, 1);
            }
          }
        }
      }
      else
      {
        result = ErrDispMove2((int)a1, *(_DWORD *)(a2 + 48), 1, 0);
        if ( result < 0 )
          return result;
      }
LABEL_47:
      if ( *(_DWORD *)(a2 + 332) )
      {
        v19 = *(_BYTE **)(a2 + 320);
        v20 = &v19[8 * *(_DWORD *)(a2 + 324)];
        while ( v19 < v20 )
        {
          if ( (v19[4] & 1) == 0 )
          {
            result = ErrJPEvalWhere(
                       v33,
                       *(_DWORD *)((~(unsigned __int8)(*(_DWORD *)(*(_DWORD *)v19 + 92) >> 1) & 4 | 0x38)
                                 + *(_DWORD *)v19));
            if ( result < 0 )
            {
              if ( result != -1603 )
                return result;
              goto LABEL_35;
            }
          }
          v19 += 8;
        }
      }
      v21 = *(_DWORD *)(a2 + 316);
      v4 = v33;
      if ( !v21 || (result = ErrJPEvalWhere(v33, v21), result >= 0) )
      {
        if ( *(_DWORD *)(a2 + 68)
          || (v28 = 0, result = ErrDispGetBookmark(a1, *(_DWORD *)(a2 + 48), a2 + 72, 4, &v28), result >= 0) )
        {
          *(_DWORD *)(a2 + 4 * *(_DWORD *)(v4 + 140) + 192) = 2;
          return 0;
        }
        return result;
      }
      v22 = result == -1603;
LABEL_58:
      if ( !v22 )
        return result;
    }
  }
  v5 = *(_DWORD *)(a2 + 312);
  v6 = (int *)(a2 + 68);
  *(_DWORD *)(a2 + 68) = 0;
  if ( v5 )
  {
    result = ErrBMPEvalQte(v5, a2 + 68);
    if ( result < 0 )
      return result;
  }
  v8 = *(int **)(a2 + 320);
  if ( v8 )
  {
    v28 = &v8[2 * *(_DWORD *)(a2 + 324)];
    while ( v8 < v28 )
    {
      v9 = *v8;
      BMP = v9;
      if ( (*(_BYTE *)(v9 + 92) & 8) != 0 )
      {
        v10 = *(_DWORD *)(v9 + 56);
        v30 = v10;
        v31 = *(_DWORD *)(v10 + 8);
        *(_DWORD *)(v10 + 8) = *(_DWORD *)(v31 + 12);
        v11 = ErrQJETEvalHtte(v33, v10, v25);
        v12 = v11;
        if ( v11 )
        {
          if ( v11 > 0 || v11 < -32760 )
          {
            if ( v11 == 13 )
              v11 = 0;
            v24 = v11;
            v17 = -8239;
            if ( v12 != 13 )
              v17 = -8084;
            UtilSetErrorInfoReal((int)a1, 0, 0, 0, v17, 0, 0, v24);
            return -3030;
          }
          return v12;
        }
        *(_DWORD *)(v30 + 8) = v31;
        v13 = v25[0] & 0x7FFF;
        switch ( v13 )
        {
          case 1:
            return -1603;
          case 8:
            if ( SysStringByteLen(bstr) )
            {
              v14 = (wchar_t *)&wszPatternAnsi;
              if ( *(_BYTE *)(v31 + 5) != 16 )
                v14 = (wchar_t *)L"*?#[";
              if ( !(unsigned __int16)FPatternChar(v14) )
              {
                v15 = BMPAllocBitmap(1);
                v16 = *(int **)(a2 + 64);
                v30 = v15;
                BMP = ErrJPRangeGetBMP(a1, BMP, v15, *v6, *v16);
                v23 = *v6;
                if ( BMP < 0 )
                {
                  (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)(a2 + 64) + 32))(
                    *(_DWORD *)(*(_DWORD *)(a2 + 64) + 32),
                    v23);
                  result = BMP;
                  *v6 = 0;
                  return result;
                }
                BMPFreeBitmap(v23);
                *v6 = v30;
                v8[1] |= 1u;
                --*(_DWORD *)(a2 + 332);
              }
            }
LABEL_19:
            if ( bstr )
              SysFreeString(bstr);
            break;
          case 14:
          case 12:
            goto LABEL_19;
        }
      }
      v8 += 2;
    }
  }
  result = ErrDispSetCurrentIndex(a1, *(_DWORD *)(*(_DWORD *)(a2 + 44) + 40), 0);
  if ( result >= 0 )
  {
    if ( *v6 )
    {
LABEL_35:
      v4 = v33;
      goto LABEL_36;
    }
    result = ErrDispMove2((int)a1, *(_DWORD *)(a2 + 48), 0x80000000, 0);
    if ( result >= 0 )
      goto LABEL_47;
  }
  return result;
}

```

## disassembly

```asm
0x100f7f80  mov     edi, edi
0x100f7f82  push    ebp
0x100f7f83  mov     ebp, esp
0x100f7f85  sub     esp, 30h
0x100f7f88  cmp     [ebp+arg_8], 80000000h
0x100f7f8f  push    ebx
0x100f7f90  push    esi
0x100f7f91  push    edi; unsigned int
0x100f7f92  mov     edi, [ebp+arg_4]
0x100f7f95  mov     ebx, [edi+20h]
0x100f7f98  mov     [ebp+var_4], ebx
0x100f7f9b  jnz     loc_100F8179
0x100f7fa1  mov     eax, [edi+138h]
0x100f7fa7  lea     ebx, [edi+44h]
0x100f7faa  mov     dword ptr [ebx], 0
0x100f7fb0  test    eax, eax
0x100f7fb2  jz      short loc_100F7FC8
0x100f7fb4  mov     ecx, [ebp+var_4]
0x100f7fb7  mov     edx, edi
0x100f7fb9  push    ebx
0x100f7fba  push    eax
0x100f7fbb  call    _ErrBMPEvalQte@16; ErrBMPEvalQte(x,x,x,x)
0x100f7fc0  test    eax, eax
0x100f7fc2  js      loc_100F82FE
0x100f7fc8  mov     esi, [edi+140h]
0x100f7fce  test    esi, esi
0x100f7fd0  jz      loc_100F80DB
0x100f7fd6  mov     eax, [edi+144h]
0x100f7fdc  lea     eax, [esi+eax*8]
0x100f7fdf  mov     [ebp+var_18], eax
0x100f7fe2  cmp     esi, eax
0x100f7fe4  jnb     loc_100F80DB
0x100f7fea  mov     eax, [esi]
0x100f7fec  mov     [ebp+var_14], eax
0x100f7fef  test    byte ptr [eax+5Ch], 8
0x100f7ff3  jz      loc_100F80CF
0x100f7ff9  mov     ecx, [eax+38h]
0x100f7ffc  mov     [ebp+var_10], ecx
0x100f7fff  mov     eax, [ecx+8]
0x100f8002  mov     [ebp+var_C], eax
0x100f8005  mov     eax, [eax+0Ch]
0x100f8008  mov     [ecx+8], eax
0x100f800b  lea     eax, [ebp+var_30]
0x100f800e  push    eax
0x100f800f  push    ecx
0x100f8010  push    [ebp+var_4]
0x100f8013  call    _ErrQJETEvalHtte@12; ErrQJETEvalHtte(x,x,x)
0x100f8018  mov     ecx, eax
0x100f801a  test    ecx, ecx
0x100f801c  jnz     loc_100F8135
0x100f8022  mov     eax, [ebp+var_10]
0x100f8025  mov     ecx, [ebp+var_C]
0x100f8028  mov     [eax+8], ecx
0x100f802b  mov     eax, [ebp+var_30]
0x100f802e  and     eax, 7FFFh
0x100f8033  cmp     eax, 1
0x100f8036  jz      loc_100F82F9
0x100f803c  cmp     eax, 8
0x100f803f  jz      short loc_100F8051
0x100f8041  cmp     eax, 0Eh
0x100f8044  jz      short loc_100F80C0
0x100f8046  cmp     eax, 0Ch
0x100f8049  jnz     loc_100F80CF
0x100f804f  jmp     short loc_100F80C0
0x100f8051  push    [ebp+bstr]; bstr
0x100f8054  call    ds:__imp__SysStringByteLen@4; SysStringByteLen(x)
0x100f805a  test    eax, eax
0x100f805c  jz      short loc_100F80C0
0x100f805e  mov     ecx, [ebp+var_C]
0x100f8061  mov     edx, offset _wszPatternJet; "*?#["
0x100f8066  mov     eax, offset _wszPatternAnsi
0x100f806b  cmp     byte ptr [ecx+5], 10h
0x100f806f  mov     ecx, [ebp+bstr]
0x100f8072  cmovnz  eax, edx
0x100f8075  xor     edx, edx
0x100f8077  push    eax; Str
0x100f8078  inc     edx
0x100f8079  call    _FPatternChar@12; FPatternChar(x,x,x)
0x100f807e  test    ax, ax
0x100f8081  jnz     short loc_100F80C0
0x100f8083  xor     ecx, ecx
0x100f8085  inc     ecx
0x100f8086  call    _BMPAllocBitmap@4; BMPAllocBitmap(x)
0x100f808b  mov     edx, [ebp+var_14]; int
0x100f808e  mov     ecx, eax
0x100f8090  mov     eax, [edi+40h]
0x100f8093  mov     [ebp+var_10], ecx
0x100f8096  push    dword ptr [eax]; int
0x100f8098  push    dword ptr [ebx]; int
0x100f809a  push    ecx; int
0x100f809b  mov     ecx, [ebp+arg_0]; void *
0x100f809e  call    _ErrJPRangeGetBMP@20; ErrJPRangeGetBMP(x,x,x,x,x)
0x100f80a3  mov     [ebp+var_14], eax
0x100f80a6  push    dword ptr [ebx]; void *
0x100f80a8  test    eax, eax
0x100f80aa  js      short loc_100F8117
0x100f80ac  call    _BMPFreeBitmap@4; BMPFreeBitmap(x)
0x100f80b1  mov     eax, [ebp+var_10]
0x100f80b4  mov     [ebx], eax
0x100f80b6  or      dword ptr [esi+4], 1
0x100f80ba  dec     dword ptr [edi+14Ch]
0x100f80c0  cmp     [ebp+bstr], 0
0x100f80c4  jz      short loc_100F80CF
0x100f80c6  push    [ebp+bstr]; bstrString
0x100f80c9  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x100f80cf  add     esi, 8
0x100f80d2  cmp     esi, [ebp+var_18]
0x100f80d5  jb      loc_100F7FEA
0x100f80db  mov     eax, [edi+2Ch]
0x100f80de  push    0
0x100f80e0  push    dword ptr [eax+28h]
0x100f80e3  push    [ebp+arg_0]
0x100f80e6  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x100f80eb  test    eax, eax
0x100f80ed  js      loc_100F82FE
0x100f80f3  cmp     dword ptr [ebx], 0
0x100f80f6  jnz     short loc_100F8176
0x100f80f8  push    0
0x100f80fa  push    80000000h
0x100f80ff  push    dword ptr [edi+30h]
0x100f8102  push    [ebp+arg_0]
0x100f8105  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x100f810a  test    eax, eax
0x100f810c  jns     loc_100F8241
0x100f8112  jmp     loc_100F82FE
0x100f8117  mov     eax, [edi+40h]
0x100f811a  mov     esi, [eax+20h]
0x100f811d  mov     ecx, esi
0x100f811f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f8125  call    esi
0x100f8127  mov     eax, [ebp+var_14]
0x100f812a  mov     dword ptr [ebx], 0
0x100f8130  jmp     loc_100F82FE
0x100f8135  jg      short loc_100F813F
0x100f8137  cmp     ecx, 0FFFF8008h
0x100f813d  jge     short loc_100F816F
0x100f813f  xor     edx, edx
0x100f8141  mov     eax, ecx
0x100f8143  cmp     ecx, 0Dh
0x100f8146  cmovz   eax, edx
0x100f8149  xor     ebx, ebx
0x100f814b  push    eax; int
0x100f814c  push    ebx; int
0x100f814d  push    ebx; int
0x100f814e  cmp     ecx, 0Dh
0x100f8151  mov     edx, 0FFFFE06Ch
0x100f8156  mov     eax, 0FFFFDFD1h
0x100f815b  cmovnz  eax, edx
0x100f815e  push    eax; int
0x100f815f  push    ebx; void *
0x100f8160  push    ebx; void *
0x100f8161  push    ebx; Src
0x100f8162  push    [ebp+arg_0]; int
0x100f8165  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100f816a  mov     ecx, 0FFFFF42Ah
0x100f816f  mov     eax, ecx
0x100f8171  jmp     loc_100F82FE
0x100f8176  mov     ebx, [ebp+var_4]
0x100f8179  cmp     dword ptr [edi+44h], 0
0x100f817d  jnz     short loc_100F819B
0x100f817f  push    0
0x100f8181  push    1
0x100f8183  push    dword ptr [edi+30h]
0x100f8186  push    [ebp+arg_0]
0x100f8189  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x100f818e  test    eax, eax
0x100f8190  js      loc_100F82FE
0x100f8196  jmp     loc_100F8241
0x100f819b  mov     eax, [ebx+8Ch]
0x100f81a1  mov     ecx, [edi+40h]
0x100f81a4  push    dword ptr [edi+eax*4+48h]; unsigned int
0x100f81a8  mov     esi, [ecx+10h]
0x100f81ab  mov     ecx, esi
0x100f81ad  push    dword ptr [edi+44h]; void *
0x100f81b0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f81b6  call    esi
0x100f81b8  mov     ecx, eax
0x100f81ba  mov     [ebp+var_8], ecx
0x100f81bd  mov     eax, [ebx+8Ch]
0x100f81c3  mov     [edi+eax*4+48h], ecx
0x100f81c7  cmp     [ebp+var_8], 0FFFFFFFFh
0x100f81cb  jz      loc_100F82F9
0x100f81d1  test    byte ptr [edi+28h], 1
0x100f81d5  jz      short loc_100F81E9
0x100f81d7  cmp     dword ptr [edi+14Ch], 0
0x100f81de  jnz     short loc_100F81E9
0x100f81e0  cmp     dword ptr [edi+13Ch], 0
0x100f81e7  jz      short loc_100F8241
0x100f81e9  push    4
0x100f81eb  lea     eax, [ebp+var_8]
0x100f81ee  push    eax
0x100f81ef  push    dword ptr [edi+30h]
0x100f81f2  push    [ebp+arg_0]
0x100f81f5  call    _ErrDispGotoBookmark@16; ErrDispGotoBookmark(x,x,x,x)
0x100f81fa  test    eax, eax
0x100f81fc  js      loc_100F82B7
0x100f8202  test    [ebp+arg_C], 8
0x100f8206  jnz     short loc_100F8241
0x100f8208  mov     eax, [edi+40h]
0x100f820b  push    [ebp+var_8]; unsigned int
0x100f820e  push    dword ptr [edi+44h]; void *
0x100f8211  mov     esi, [eax+10h]
0x100f8214  mov     ecx, esi
0x100f8216  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f821c  call    esi
0x100f821e  mov     ecx, eax
0x100f8220  cmp     ecx, 0FFFFFFFFh
0x100f8223  jz      short loc_100F8241
0x100f8225  mov     eax, [ebp+var_8]
0x100f8228  mov     edx, [edi+30h]
0x100f822b  push    1
0x100f822d  mov     [ebp+var_1C], eax
0x100f8230  lea     eax, [ebp+var_1C]
0x100f8233  push    2
0x100f8235  mov     [ebp+var_18], ecx
0x100f8238  mov     ecx, [ebp+arg_0]
0x100f823b  push    eax
0x100f823c  call    _ErrDispReadAhead@20; ErrDispReadAhead(x,x,x,x,x)
0x100f8241  cmp     dword ptr [edi+14Ch], 0
0x100f8248  jz      short loc_100F8292
0x100f824a  mov     esi, [edi+140h]
0x100f8250  mov     eax, [edi+144h]
0x100f8256  lea     ebx, [esi+eax*8]
0x100f8259  cmp     esi, ebx
0x100f825b  jnb     short loc_100F8292
0x100f825d  test    byte ptr [esi+4], 1
0x100f8261  jnz     short loc_100F8281
0x100f8263  mov     eax, [esi]
0x100f8265  mov     ecx, [ebp+var_4]
0x100f8268  mov     edx, [eax+5Ch]
0x100f826b  shr     edx, 1
0x100f826d  not     edx
0x100f826f  and     edx, 4
0x100f8272  or      edx, 38h
0x100f8275  mov     edx, [edx+eax]
0x100f8278  call    _ErrJPEvalWhere@8; ErrJPEvalWhere(x,x)
0x100f827d  test    eax, eax
0x100f827f  js      short loc_100F8286
0x100f8281  add     esi, 8
0x100f8284  jmp     short loc_100F8259
0x100f8286  cmp     eax, 0FFFFF9BDh
0x100f828b  jnz     short loc_100F82FE
0x100f828d  jmp     loc_100F8176
0x100f8292  mov     edx, [edi+13Ch]
0x100f8298  mov     ebx, [ebp+var_4]
0x100f829b  test    edx, edx
0x100f829d  jz      short loc_100F82BE
0x100f829f  mov     ecx, ebx
0x100f82a1  call    _ErrJPEvalWhere@8; ErrJPEvalWhere(x,x)
0x100f82a6  test    eax, eax
0x100f82a8  jns     short loc_100F82BE
0x100f82aa  cmp     eax, 0FFFFF9BDh
0x100f82af  jz      loc_100F8179
0x100f82b5  jmp     short loc_100F82FE
0x100f82b7  cmp     eax, 0FFFFF9BFh
0x100f82bc  jmp     short loc_100F82AF
0x100f82be  cmp     dword ptr [edi+44h], 0
0x100f82c2  jnz     short loc_100F82E4
0x100f82c4  lea     eax, [ebp+var_18]
0x100f82c7  mov     [ebp+var_18], 0
0x100f82ce  push    eax
0x100f82cf  push    4
0x100f82d1  lea     eax, [edi+48h]
0x100f82d4  push    eax
0x100f82d5  push    dword ptr [edi+30h]
0x100f82d8  push    [ebp+arg_0]
0x100f82db  call    _ErrDispGetBookmark@20; ErrDispGetBookmark(x,x,x,x,x)
0x100f82e0  test    eax, eax
0x100f82e2  js      short loc_100F82FE
0x100f82e4  mov     eax, [ebx+8Ch]
0x100f82ea  mov     dword ptr [edi+eax*4+0C0h], 2
0x100f82f5  xor     eax, eax
0x100f82f7  jmp     short loc_100F82FE
0x100f82f9  mov     eax, 0FFFFF9BDh
0x100f82fe  pop     edi
0x100f82ff  pop     esi
0x100f8300  pop     ebx
0x100f8301  leave
0x100f8302  retn    10h
```
