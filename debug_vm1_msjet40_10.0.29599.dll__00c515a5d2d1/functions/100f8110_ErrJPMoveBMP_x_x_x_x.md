# ErrJPMoveBMP(x,x,x,x)

- ea: `0x100f8110`
- end: `0x100f8495`
- name: `_ErrJPMoveBMP@16`
- size: `901`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x1003ea00`
- `0x10043890`
- `0x10044020`
- `0x100444b0`
- `0x100448b0`
- `0x10044d10`
- `0x10050190`
- `0x100b88fc`
- `0x100b89db`
- `0x100f1e00`
- `0x100f1ec0`
- `0x100f8110`
- `0x100f8508`
- `0x100fdc26`
- `0x100fdd04`

## import_xrefs

- `OLEAUT32!__imp__SysFreeString@4` at `0x100f8259`
- `OLEAUT32!__imp__SysFreeString@4` at `0x100f8259`
- `OLEAUT32!__imp__SysStringByteLen@4` at `0x100f81e4`
- `OLEAUT32!__imp__SysStringByteLen@4` at `0x100f81e4`

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
0x100f8110  mov     edi, edi
0x100f8112  push    ebp
0x100f8113  mov     ebp, esp
0x100f8115  sub     esp, 30h
0x100f8118  cmp     [ebp+arg_8], 80000000h
0x100f811f  push    ebx
0x100f8120  push    esi
0x100f8121  push    edi; unsigned int
0x100f8122  mov     edi, [ebp+arg_4]
0x100f8125  mov     ebx, [edi+20h]
0x100f8128  mov     [ebp+var_4], ebx
0x100f812b  jnz     loc_100F8309
0x100f8131  mov     eax, [edi+138h]
0x100f8137  lea     ebx, [edi+44h]
0x100f813a  mov     dword ptr [ebx], 0
0x100f8140  test    eax, eax
0x100f8142  jz      short loc_100F8158
0x100f8144  mov     ecx, [ebp+var_4]
0x100f8147  mov     edx, edi
0x100f8149  push    ebx
0x100f814a  push    eax
0x100f814b  call    _ErrBMPEvalQte@16; ErrBMPEvalQte(x,x,x,x)
0x100f8150  test    eax, eax
0x100f8152  js      loc_100F848E
0x100f8158  mov     esi, [edi+140h]
0x100f815e  test    esi, esi
0x100f8160  jz      loc_100F826B
0x100f8166  mov     eax, [edi+144h]
0x100f816c  lea     eax, [esi+eax*8]
0x100f816f  mov     [ebp+var_18], eax
0x100f8172  cmp     esi, eax
0x100f8174  jnb     loc_100F826B
0x100f817a  mov     eax, [esi]
0x100f817c  mov     [ebp+var_14], eax
0x100f817f  test    byte ptr [eax+5Ch], 8
0x100f8183  jz      loc_100F825F
0x100f8189  mov     ecx, [eax+38h]
0x100f818c  mov     [ebp+var_10], ecx
0x100f818f  mov     eax, [ecx+8]
0x100f8192  mov     [ebp+var_C], eax
0x100f8195  mov     eax, [eax+0Ch]
0x100f8198  mov     [ecx+8], eax
0x100f819b  lea     eax, [ebp+var_30]
0x100f819e  push    eax
0x100f819f  push    ecx
0x100f81a0  push    [ebp+var_4]
0x100f81a3  call    _ErrQJETEvalHtte@12; ErrQJETEvalHtte(x,x,x)
0x100f81a8  mov     ecx, eax
0x100f81aa  test    ecx, ecx
0x100f81ac  jnz     loc_100F82C5
0x100f81b2  mov     eax, [ebp+var_10]
0x100f81b5  mov     ecx, [ebp+var_C]
0x100f81b8  mov     [eax+8], ecx
0x100f81bb  mov     eax, [ebp+var_30]
0x100f81be  and     eax, 7FFFh
0x100f81c3  cmp     eax, 1
0x100f81c6  jz      loc_100F8489
0x100f81cc  cmp     eax, 8
0x100f81cf  jz      short loc_100F81E1
0x100f81d1  cmp     eax, 0Eh
0x100f81d4  jz      short loc_100F8250
0x100f81d6  cmp     eax, 0Ch
0x100f81d9  jnz     loc_100F825F
0x100f81df  jmp     short loc_100F8250
0x100f81e1  push    [ebp+bstr]; bstr
0x100f81e4  call    ds:__imp__SysStringByteLen@4; SysStringByteLen(x)
0x100f81ea  test    eax, eax
0x100f81ec  jz      short loc_100F8250
0x100f81ee  mov     ecx, [ebp+var_C]
0x100f81f1  mov     edx, offset _wszPatternJet; "*?#["
0x100f81f6  mov     eax, offset _wszPatternAnsi
0x100f81fb  cmp     byte ptr [ecx+5], 10h
0x100f81ff  mov     ecx, [ebp+bstr]
0x100f8202  cmovnz  eax, edx
0x100f8205  xor     edx, edx
0x100f8207  push    eax; Str
0x100f8208  inc     edx
0x100f8209  call    _FPatternChar@12; FPatternChar(x,x,x)
0x100f820e  test    ax, ax
0x100f8211  jnz     short loc_100F8250
0x100f8213  xor     ecx, ecx
0x100f8215  inc     ecx
0x100f8216  call    _BMPAllocBitmap@4; BMPAllocBitmap(x)
0x100f821b  mov     edx, [ebp+var_14]; int
0x100f821e  mov     ecx, eax
0x100f8220  mov     eax, [edi+40h]
0x100f8223  mov     [ebp+var_10], ecx
0x100f8226  push    dword ptr [eax]; int
0x100f8228  push    dword ptr [ebx]; int
0x100f822a  push    ecx; int
0x100f822b  mov     ecx, [ebp+arg_0]; void *
0x100f822e  call    _ErrJPRangeGetBMP@20; ErrJPRangeGetBMP(x,x,x,x,x)
0x100f8233  mov     [ebp+var_14], eax
0x100f8236  push    dword ptr [ebx]; void *
0x100f8238  test    eax, eax
0x100f823a  js      short loc_100F82A7
0x100f823c  call    _BMPFreeBitmap@4; BMPFreeBitmap(x)
0x100f8241  mov     eax, [ebp+var_10]
0x100f8244  mov     [ebx], eax
0x100f8246  or      dword ptr [esi+4], 1
0x100f824a  dec     dword ptr [edi+14Ch]
0x100f8250  cmp     [ebp+bstr], 0
0x100f8254  jz      short loc_100F825F
0x100f8256  push    [ebp+bstr]; bstrString
0x100f8259  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x100f825f  add     esi, 8
0x100f8262  cmp     esi, [ebp+var_18]
0x100f8265  jb      loc_100F817A
0x100f826b  mov     eax, [edi+2Ch]
0x100f826e  push    0
0x100f8270  push    dword ptr [eax+28h]
0x100f8273  push    [ebp+arg_0]
0x100f8276  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x100f827b  test    eax, eax
0x100f827d  js      loc_100F848E
0x100f8283  cmp     dword ptr [ebx], 0
0x100f8286  jnz     short loc_100F8306
0x100f8288  push    0
0x100f828a  push    80000000h
0x100f828f  push    dword ptr [edi+30h]
0x100f8292  push    [ebp+arg_0]
0x100f8295  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x100f829a  test    eax, eax
0x100f829c  jns     loc_100F83D1
0x100f82a2  jmp     loc_100F848E
0x100f82a7  mov     eax, [edi+40h]
0x100f82aa  mov     esi, [eax+20h]
0x100f82ad  mov     ecx, esi
0x100f82af  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f82b5  call    esi
0x100f82b7  mov     eax, [ebp+var_14]
0x100f82ba  mov     dword ptr [ebx], 0
0x100f82c0  jmp     loc_100F848E
0x100f82c5  jg      short loc_100F82CF
0x100f82c7  cmp     ecx, 0FFFF8008h
0x100f82cd  jge     short loc_100F82FF
0x100f82cf  xor     edx, edx
0x100f82d1  mov     eax, ecx
0x100f82d3  cmp     ecx, 0Dh
0x100f82d6  cmovz   eax, edx
0x100f82d9  xor     ebx, ebx
0x100f82db  push    eax; int
0x100f82dc  push    ebx; int
0x100f82dd  push    ebx; int
0x100f82de  cmp     ecx, 0Dh
0x100f82e1  mov     edx, 0FFFFE06Ch
0x100f82e6  mov     eax, 0FFFFDFD1h
0x100f82eb  cmovnz  eax, edx
0x100f82ee  push    eax; int
0x100f82ef  push    ebx; void *
0x100f82f0  push    ebx; void *
0x100f82f1  push    ebx; Src
0x100f82f2  push    [ebp+arg_0]; int
0x100f82f5  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100f82fa  mov     ecx, 0FFFFF42Ah
0x100f82ff  mov     eax, ecx
0x100f8301  jmp     loc_100F848E
0x100f8306  mov     ebx, [ebp+var_4]
0x100f8309  cmp     dword ptr [edi+44h], 0
0x100f830d  jnz     short loc_100F832B
0x100f830f  push    0
0x100f8311  push    1
0x100f8313  push    dword ptr [edi+30h]
0x100f8316  push    [ebp+arg_0]
0x100f8319  call    _ErrDispMove2@16; ErrDispMove2(x,x,x,x)
0x100f831e  test    eax, eax
0x100f8320  js      loc_100F848E
0x100f8326  jmp     loc_100F83D1
0x100f832b  mov     eax, [ebx+8Ch]
0x100f8331  mov     ecx, [edi+40h]
0x100f8334  push    dword ptr [edi+eax*4+48h]; unsigned int
0x100f8338  mov     esi, [ecx+10h]
0x100f833b  mov     ecx, esi
0x100f833d  push    dword ptr [edi+44h]; void *
0x100f8340  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f8346  call    esi
0x100f8348  mov     ecx, eax
0x100f834a  mov     [ebp+var_8], ecx
0x100f834d  mov     eax, [ebx+8Ch]
0x100f8353  mov     [edi+eax*4+48h], ecx
0x100f8357  cmp     [ebp+var_8], 0FFFFFFFFh
0x100f835b  jz      loc_100F8489
0x100f8361  test    byte ptr [edi+28h], 1
0x100f8365  jz      short loc_100F8379
0x100f8367  cmp     dword ptr [edi+14Ch], 0
0x100f836e  jnz     short loc_100F8379
0x100f8370  cmp     dword ptr [edi+13Ch], 0
0x100f8377  jz      short loc_100F83D1
0x100f8379  push    4
0x100f837b  lea     eax, [ebp+var_8]
0x100f837e  push    eax
0x100f837f  push    dword ptr [edi+30h]
0x100f8382  push    [ebp+arg_0]
0x100f8385  call    _ErrDispGotoBookmark@16; ErrDispGotoBookmark(x,x,x,x)
0x100f838a  test    eax, eax
0x100f838c  js      loc_100F8447
0x100f8392  test    [ebp+arg_C], 8
0x100f8396  jnz     short loc_100F83D1
0x100f8398  mov     eax, [edi+40h]
0x100f839b  push    [ebp+var_8]; unsigned int
0x100f839e  push    dword ptr [edi+44h]; void *
0x100f83a1  mov     esi, [eax+10h]
0x100f83a4  mov     ecx, esi
0x100f83a6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100f83ac  call    esi
0x100f83ae  mov     ecx, eax
0x100f83b0  cmp     ecx, 0FFFFFFFFh
0x100f83b3  jz      short loc_100F83D1
0x100f83b5  mov     eax, [ebp+var_8]
0x100f83b8  mov     edx, [edi+30h]
0x100f83bb  push    1
0x100f83bd  mov     [ebp+var_1C], eax
0x100f83c0  lea     eax, [ebp+var_1C]
0x100f83c3  push    2
0x100f83c5  mov     [ebp+var_18], ecx
0x100f83c8  mov     ecx, [ebp+arg_0]
0x100f83cb  push    eax
0x100f83cc  call    _ErrDispReadAhead@20; ErrDispReadAhead(x,x,x,x,x)
0x100f83d1  cmp     dword ptr [edi+14Ch], 0
0x100f83d8  jz      short loc_100F8422
0x100f83da  mov     esi, [edi+140h]
0x100f83e0  mov     eax, [edi+144h]
0x100f83e6  lea     ebx, [esi+eax*8]
0x100f83e9  cmp     esi, ebx
0x100f83eb  jnb     short loc_100F8422
0x100f83ed  test    byte ptr [esi+4], 1
0x100f83f1  jnz     short loc_100F8411
0x100f83f3  mov     eax, [esi]
0x100f83f5  mov     ecx, [ebp+var_4]
0x100f83f8  mov     edx, [eax+5Ch]
0x100f83fb  shr     edx, 1
0x100f83fd  not     edx
0x100f83ff  and     edx, 4
0x100f8402  or      edx, 38h
0x100f8405  mov     edx, [edx+eax]
0x100f8408  call    _ErrJPEvalWhere@8; ErrJPEvalWhere(x,x)
0x100f840d  test    eax, eax
0x100f840f  js      short loc_100F8416
0x100f8411  add     esi, 8
0x100f8414  jmp     short loc_100F83E9
0x100f8416  cmp     eax, 0FFFFF9BDh
0x100f841b  jnz     short loc_100F848E
0x100f841d  jmp     loc_100F8306
0x100f8422  mov     edx, [edi+13Ch]
0x100f8428  mov     ebx, [ebp+var_4]
0x100f842b  test    edx, edx
0x100f842d  jz      short loc_100F844E
0x100f842f  mov     ecx, ebx
0x100f8431  call    _ErrJPEvalWhere@8; ErrJPEvalWhere(x,x)
0x100f8436  test    eax, eax
0x100f8438  jns     short loc_100F844E
0x100f843a  cmp     eax, 0FFFFF9BDh
0x100f843f  jz      loc_100F8309
0x100f8445  jmp     short loc_100F848E
0x100f8447  cmp     eax, 0FFFFF9BFh
0x100f844c  jmp     short loc_100F843F
0x100f844e  cmp     dword ptr [edi+44h], 0
0x100f8452  jnz     short loc_100F8474
0x100f8454  lea     eax, [ebp+var_18]
0x100f8457  mov     [ebp+var_18], 0
0x100f845e  push    eax
0x100f845f  push    4
0x100f8461  lea     eax, [edi+48h]
0x100f8464  push    eax
0x100f8465  push    dword ptr [edi+30h]
0x100f8468  push    [ebp+arg_0]
0x100f846b  call    _ErrDispGetBookmark@20; ErrDispGetBookmark(x,x,x,x,x)
0x100f8470  test    eax, eax
0x100f8472  js      short loc_100F848E
0x100f8474  mov     eax, [ebx+8Ch]
0x100f847a  mov     dword ptr [edi+eax*4+0C0h], 2
0x100f8485  xor     eax, eax
0x100f8487  jmp     short loc_100F848E
0x100f8489  mov     eax, 0FFFFF9BDh
0x100f848e  pop     edi
0x100f848f  pop     esi
0x100f8490  pop     ebx
0x100f8491  leave
0x100f8492  retn    10h
```
