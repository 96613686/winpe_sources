# ErrOpenDatabase(x,x,x,x,x)

- ea: `0x10017010`
- end: `0x100176cb`
- name: `_ErrOpenDatabase@20`
- size: `1723`
- prototype: ``
- caller_count: `8`
- callee_count: `22`
- tags: `authz_impersonation, service_task`

## callers

- `0x1001b750`
- `0x1001e230`
- `0x1001eb70`
- `0x10025b10`
- `0x1002bfa0`
- `0x1002c5f0`
- `0x10032780`
- `0x10033a10`

## callees

- `0x10016f80`
- `0x10017010`
- `0x100176e0`
- `0x10029740`
- `0x10029ff0`
- `0x1002a530`
- `0x1003a7f0`
- `0x1003c760`
- `0x1003e650`
- `0x1003e6a0`
- `0x1003e6d0`
- `0x1003e820`
- `0x1003e870`
- `0x1003eef0`
- `0x1003ef40`
- `0x100429d0`
- `0x10042ed0`
- `0x10048e9b`
- `0x1009813a`
- `0x10117190`
- `0x10121bd0`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100173c6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100173c6`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10017245`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1001725c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10017245`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1001725c`

## pseudocode

```c
int __stdcall ErrOpenDatabase(int a1, wchar_t *a2, unsigned __int16 *a3, int a4, int a5)
{
  Session *v5; // ebx
  unsigned __int16 *v6; // esi
  int v7; // eax
  wchar_t *v8; // edi
  int result; // eax
  unsigned __int16 *v10; // eax
  int v11; // ecx
  int IsamType; // esi
  int v13; // edi
  int v14; // ecx
  int v15; // ecx
  wchar_t *v16; // eax
  int v17; // eax
  wchar_t *v18; // eax
  int v19; // edi
  void *v20; // edi
  int v21; // ebx
  int v22; // eax
  int v23; // ecx
  int v24; // eax
  bool v25; // sf
  int started; // eax
  int ItibOfSesid; // eax
  int v28; // eax
  _DWORD *v29; // edi
  int v30; // ecx
  int v31; // ecx
  bool v32; // zf
  int v33; // [esp-14h] [ebp-26Ch]
  unsigned int v34; // [esp-10h] [ebp-268h]
  int v35; // [esp-10h] [ebp-268h]
  int v36; // [esp-4h] [ebp-25Ch]
  wchar_t *i; // [esp+10h] [ebp-248h] BYREF
  void *Block; // [esp+14h] [ebp-244h] BYREF
  unsigned int v39; // [esp+18h] [ebp-240h] BYREF
  int v40; // [esp+1Ch] [ebp-23Ch] BYREF
  wchar_t *Str; // [esp+20h] [ebp-238h]
  int v42; // [esp+24h] [ebp-234h] BYREF
  int v43; // [esp+28h] [ebp-230h] BYREF
  int v44; // [esp+2Ch] [ebp-22Ch] BYREF
  int v45; // [esp+30h] [ebp-228h]
  BOOL v46; // [esp+34h] [ebp-224h] BYREF
  int v47; // [esp+38h] [ebp-220h]
  _BYTE v48[4]; // [esp+3Ch] [ebp-21Ch] BYREF
  wchar_t Destination[266]; // [esp+40h] [ebp-218h] BYREF

  v5 = (Session *)a1;
  v6 = a3;
  v45 = a4;
  v7 = isibHead;
  Block = a3;
  v40 = a1;
  v46 = 0;
  v42 = -1;
  v8 = a2;
  Str = a2;
  for ( i = a2; v7 != -1; v7 = dword_1016EAE8[26 * v7] )
  {
    if ( rgsib[26 * v7] == a1 )
      break;
  }
  if ( v7 >= 0 )
  {
    _mm_lfence();
    v39 = dword_1016EAA4[26 * v7];
  }
  else
  {
    v39 = -1;
  }
  v47 = 0;
  if ( !FValidSesid(a1) )
    return -1104;
  if ( a2 )
  {
    if ( !*a2 )
      v8 = 0;
    Str = v8;
    i = v8;
  }
  if ( a3 )
  {
    v10 = 0;
    if ( *a3 )
      v10 = a3;
    v6 = v10;
    Block = v10;
  }
  IsamType = ErrGetIsamType(v39, v6, &v44);
  if ( IsamType < 0 )
    return IsamType;
  v13 = v44;
  if ( v44 != 0xFFFF )
  {
    if ( v44 == 65534 )
    {
LABEL_22:
      IsamType = ErrRdbOpenDatabase(a1, (int)Block, v45, a5);
      v14 = dword_1016EAF8[26 * UtilGetIsibOfSesid(a1)];
      goto LABEL_84;
    }
    if ( (**(_DWORD **)UtilGetPiicbtaskOfItib(v39, v44) & 1) == 0 )
    {
      if ( v13 == 65534 )
        goto LABEL_22;
      result = ErrStartIsam(&v44, &v42, &v40, &v43);
      if ( result < 0 )
        return result;
      v16 = Str;
      if ( Str )
        goto LABEL_27;
      result = ErrFilterDbName(Destination, v15);
      if ( result < 0 )
        return result;
      v16 = i;
      if ( i )
      {
LABEL_27:
        v13 = v44;
        v17 = ErrOpenForeignDatabase((unsigned int)v16, Block, v45, a5);
        v14 = v42;
        IsamType = v17;
        goto LABEL_84;
      }
      return -1003;
    }
  }
  v18 = Str;
  v39 = 0;
  if ( !Str )
  {
    if ( !Block )
      return -1003;
    IsamType = ErrFilterDbName(Destination, v11);
    if ( IsamType < 0 )
      return IsamType;
    v18 = i;
    Str = i;
    if ( !i )
      return -1003;
  }
  if ( _wcschr(v18, 0x2Au) || _wcschr(Str, 0x3Fu) )
    return -1022;
  if ( v13 == 0xFFFF )
  {
    IsamType = ErrIsamOpenDatabase(Block, &v39, a5);
    v19 = dword_1016EAF8[26 * UtilGetIsibOfSesid(a1)];
    i = (wchar_t *)v19;
    v42 = v19;
    if ( IsamType != -1024 )
    {
      if ( IsamType != -1019 )
      {
LABEL_71:
        if ( IsamType != 1208 )
          goto LABEL_72;
        goto LABEL_75;
      }
      if ( (a5 & 0x80u) != 0 )
        goto LABEL_75;
    }
  }
  v20 = Block;
  v21 = -1;
  i = (wchar_t *)Block;
  v43 = IsamType;
  while ( 1 )
  {
    if ( v44 == 0xFFFF )
    {
      if ( v21 == -1 )
        v21 = 0;
    }
    else if ( v21 == -1 )
    {
      goto LABEL_51;
    }
    v22 = dword_1016EAB0[26 * UtilGetIsibOfSesidIscb(v40)];
    if ( v22 == -8800 || v22 == -8801 )
    {
      ClearErrorInfo(v23);
      v24 = ErrGenIISAMConnectString(&i);
    }
    else
    {
      if ( !rgIISAM[v21] )
        goto LABEL_51;
      v24 = ErrGenIISAMConnectString(&i);
      ++v21;
    }
    v20 = i;
    IsamType = v24;
LABEL_51:
    v25 = IsamType < 0;
    if ( IsamType )
      goto LABEL_55;
    started = ErrStartIsam(&v44, &v42, v48, &v46);
    IsamType = started;
    if ( started < 0 )
    {
      if ( started != -1056 )
        goto LABEL_57;
      IsamType = v43;
      v25 = v43 < 0;
LABEL_55:
      if ( v25 )
        goto LABEL_57;
    }
    IsamType = ErrOpenForeignDatabase((unsigned int)Str, v20, &v39, a5);
LABEL_57:
    if ( v20 != Block )
    {
      if ( v20 )
        _free(v20);
      v20 = 0;
      i = 0;
    }
    if ( IsamType >= 0 )
    {
LABEL_70:
      v19 = v42;
      i = (wchar_t *)v42;
      goto LABEL_71;
    }
    if ( IsamType == -1905
      || IsamType == -1202
      || IsamType == -8194
      || IsamType == -8850
      || IsamType == -1031
      || IsamType == -1206
      || v21 == -1 )
    {
      break;
    }
    if ( !rgIISAM[v21] )
      goto LABEL_70;
  }
  v19 = v42;
  i = (wchar_t *)v42;
LABEL_72:
  if ( IsamType == -1023 )
  {
    UtilSetErrorInfoReal(v40, Str, 0, 0, -8161, 0, 0, 0);
    return -1023;
  }
LABEL_75:
  v46 = IsamType == 1208;
  if ( IsamType == 3811 || IsamType == 3812 )
    v47 = IsamType;
  v5 = (Session *)v40;
  if ( IsamType < 0 )
    goto LABEL_83;
  v34 = v39;
  v33 = v40;
  v43 = 0;
  mpdbidiiscb[v39] = v19;
  if ( (int)ErrDispGetDatabaseInfo(v33, v34, &v42, 4, 18) >= 0 )
  {
    ItibOfSesid = UtilGetItibOfSesid(v5);
    if ( ErrSetCollateSeqC(ItibOfSesid, v42, &v42) )
    {
      IsamType = -5026;
      goto LABEL_82;
    }
  }
  IsamType = ErrDispGetDatabaseInfo(v5, v39, &v43, 4, 8);
  if ( IsamType < 0 )
  {
LABEL_82:
    ErrDispCloseDatabase(v5, v39, 0);
    goto LABEL_83;
  }
  if ( v43 < 0x20000 )
    goto LABEL_100;
  if ( !*(&Src + 5 * v19) )
    goto LABEL_100;
  LOWORD(Block) = 770;
  if ( SecIndexOfTokenSid(2) != -1 )
    goto LABEL_100;
  IsamType = ErrSecValidateAccess(L"Databases", L"MSysDb", 0, 0, 2, v30);
  if ( IsamType == -1907 )
  {
    LOWORD(Block) = 258;
    IsamType = ErrSecValidateAccess(L"Databases", L"MSysDb", &Block, 2, 2, v31);
  }
  if ( IsamType < 0 )
  {
LABEL_97:
    if ( IsamType == -1907 )
    {
      UtilSetErrorInfoReal((int)v5, Str, 0, 0, -8170, 0, 0, 0);
    }
    else if ( IsamType >= 0 )
    {
      goto LABEL_100;
    }
    goto LABEL_82;
  }
  if ( (a5 & 0xA) != 0 && (a5 & 0x40) == 0 )
  {
    IsamType = ErrSecValidateAccess(L"Databases", L"MSysDb", 0, 0, 4, v31);
    goto LABEL_97;
  }
LABEL_100:
  *(_DWORD *)v45 = v39;
LABEL_83:
  v13 = v44;
  v14 = (int)i;
LABEL_84:
  if ( IsamType >= 0 )
  {
    v36 = v46;
    v43 = IsamType;
    v35 = *(_DWORD *)v45;
    mpdbidiiscb[v35] = v14;
    v28 = ErrREPOpenDatabase(v5, v35, a5, v13, v36);
    IsamType = v28;
    if ( v28 >= 0 )
    {
      if ( !v28 )
        IsamType = v43;
    }
    else
    {
      v29 = (_DWORD *)v45;
      ErrDispCloseDatabase(v5, *(_DWORD *)v45, 0);
      *v29 = -1;
    }
  }
  if ( v46 )
  {
    v32 = IsamType == 0;
    if ( IsamType >= 0 )
      return 1208;
  }
  else
  {
    v32 = IsamType == 0;
  }
  if ( v32 )
  {
    if ( v47 )
      return v47;
  }
  return IsamType;
}

```

## disassembly

```asm
0x10017010  mov     edi, edi
0x10017012  push    ebp
0x10017013  mov     ebp, esp
0x10017015  and     esp, 0FFFFFFF8h
0x10017018  sub     esp, 24Ch
0x1001701e  mov     eax, ___security_cookie
0x10017023  xor     eax, esp
0x10017025  mov     [esp+24Ch+var_4], eax
0x1001702c  mov     eax, [ebp+arg_C]
0x1001702f  push    ebx
0x10017030  mov     ebx, [ebp+arg_0]
0x10017033  push    esi
0x10017034  mov     esi, [ebp+arg_8]
0x10017037  mov     [esp+254h+var_228], eax
0x1001703b  mov     eax, _isibHead
0x10017040  mov     [esp+254h+Block], esi
0x10017044  mov     [esp+254h+var_23C], ebx
0x10017048  mov     [esp+254h+var_224], 0
0x10017050  mov     [esp+254h+var_234], 0FFFFFFFFh
0x10017058  push    edi
0x10017059  mov     edi, [ebp+arg_4]
0x1001705c  mov     [esp+258h+Str], edi
0x10017060  mov     [esp+258h+var_248], edi
0x10017064  cmp     eax, 0FFFFFFFFh
0x10017067  jz      short loc_10017086
0x10017069  nop     dword ptr [eax+00000000h]
0x10017070  imul    ecx, eax, 68h ; 'h'
0x10017073  cmp     _rgsib[ecx], ebx
0x10017079  jz      short loc_10017086
0x1001707b  mov     eax, dword_1016EAE8[ecx]
0x10017081  cmp     eax, 0FFFFFFFFh
0x10017084  jnz     short loc_10017070
0x10017086  test    eax, eax
0x10017088  jns     short loc_10017094
0x1001708a  mov     [esp+258h+var_240], 0FFFFFFFFh
0x10017092  jmp     short loc_100170A4
0x10017094  imul    eax, 68h ; 'h'
0x10017097  lfence
0x1001709a  mov     eax, dword_1016EAA4[eax]
0x100170a0  mov     [esp+258h+var_240], eax
0x100170a4  xor     eax, eax
0x100170a6  push    ebx
0x100170a7  mov     [esp+25Ch+var_220], eax
0x100170ab  call    _FValidSesid@4; FValidSesid(x)
0x100170b0  test    eax, eax
0x100170b2  jnz     short loc_100170D0
0x100170b4  mov     eax, 0FFFFFBB0h
0x100170b9  pop     edi
0x100170ba  pop     esi
0x100170bb  pop     ebx
0x100170bc  mov     ecx, [esp+24Ch+var_4]
0x100170c3  xor     ecx, esp; StackCookie
0x100170c5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100170ca  mov     esp, ebp
0x100170cc  pop     ebp
0x100170cd  retn    14h
0x100170d0  test    edi, edi
0x100170d2  jz      short loc_100170E4
0x100170d4  xor     eax, eax
0x100170d6  cmp     [edi], ax
0x100170d9  cmovz   edi, eax
0x100170dc  mov     [esp+258h+Str], edi
0x100170e0  mov     [esp+258h+var_248], edi
0x100170e4  test    esi, esi
0x100170e6  jz      short loc_100170F6
0x100170e8  xor     eax, eax
0x100170ea  cmp     [esi], ax
0x100170ed  cmovnz  eax, esi
0x100170f0  mov     esi, eax
0x100170f2  mov     [esp+258h+Block], eax
0x100170f6  mov     ecx, [esp+258h+var_240]
0x100170fa  lea     eax, [esp+258h+var_22C]
0x100170fe  push    eax
0x100170ff  mov     edx, esi
0x10017101  call    _ErrGetIsamType@12; ErrGetIsamType(x,x,x)
0x10017106  mov     esi, eax
0x10017108  test    esi, esi
0x1001710a  js      loc_10017696
0x10017110  mov     edi, [esp+258h+var_22C]
0x10017114  cmp     edi, 0FFFFh
0x1001711a  jz      loc_100171E7
0x10017120  cmp     edi, 0FFFEh
0x10017126  jz      short loc_10017149
0x10017128  mov     ecx, [esp+258h+var_240]
0x1001712c  mov     edx, edi
0x1001712e  call    _UtilGetPiicbtaskOfItib@8; UtilGetPiicbtaskOfItib(x,x)
0x10017133  mov     eax, [eax]
0x10017135  test    dword ptr [eax], 1
0x1001713b  jnz     loc_100171E7
0x10017141  cmp     edi, 0FFFEh
0x10017147  jnz     short loc_10017173
0x10017149  push    [ebp+arg_10]; int
0x1001714c  mov     ecx, [esp+25Ch+var_228]
0x10017150  push    ecx; int
0x10017151  push    [esp+260h+Block]; int
0x10017155  mov     ecx, ebx; int
0x10017157  call    _ErrRdbOpenDatabase@20; ErrRdbOpenDatabase(x,x,x,x,x)
0x1001715c  mov     ecx, ebx
0x1001715e  mov     esi, eax
0x10017160  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10017165  imul    eax, 68h ; 'h'
0x10017168  mov     ecx, dword_1016EAF8[eax]
0x1001716e  jmp     loc_10017500
0x10017173  mov     esi, [esp+258h+Block]
0x10017177  lea     eax, [esp+258h+var_230]
0x1001717b  push    eax
0x1001717c  lea     eax, [esp+25Ch+var_23C]
0x10017180  mov     edx, esi
0x10017182  push    eax
0x10017183  lea     eax, [esp+260h+var_234]
0x10017187  mov     ecx, ebx
0x10017189  push    eax
0x1001718a  lea     eax, [esp+264h+var_22C]
0x1001718e  push    eax
0x1001718f  call    _ErrStartIsam@24; ErrStartIsam(x,x,x,x,x,x)
0x10017194  test    eax, eax
0x10017196  js      loc_100176B4
0x1001719c  mov     eax, [esp+258h+Str]
0x100171a0  test    eax, eax
0x100171a2  jnz     short loc_100171C5
0x100171a4  push    ecx; int
0x100171a5  lea     eax, [esp+25Ch+Destination]
0x100171a9  mov     ecx, esi
0x100171ab  push    eax; Destination
0x100171ac  lea     edx, [esp+260h+var_248]
0x100171b0  call    _ErrFilterDbName@16; ErrFilterDbName(x,x,x,x)
0x100171b5  test    eax, eax
0x100171b7  js      loc_100176B4
0x100171bd  mov     eax, [esp+258h+var_248]
0x100171c1  test    eax, eax
0x100171c3  jz      short loc_10017226
0x100171c5  push    [ebp+arg_10]
0x100171c8  mov     ecx, [esp+25Ch+var_228]
0x100171cc  mov     edi, [esp+25Ch+var_22C]
0x100171d0  mov     edx, edi
0x100171d2  push    ecx
0x100171d3  push    esi
0x100171d4  push    eax
0x100171d5  mov     ecx, ebx
0x100171d7  call    _ErrOpenForeignDatabase@24; ErrOpenForeignDatabase(x,x,x,x,x,x)
0x100171dc  mov     ecx, [esp+258h+var_234]
0x100171e0  mov     esi, eax
0x100171e2  jmp     loc_10017500
0x100171e7  mov     eax, [esp+258h+Str]
0x100171eb  mov     [esp+258h+var_240], 0
0x100171f3  test    eax, eax
0x100171f5  jnz     short loc_10017242
0x100171f7  mov     eax, [esp+258h+Block]
0x100171fb  test    eax, eax
0x100171fd  jz      short loc_10017226
0x100171ff  push    ecx; int
0x10017200  lea     ecx, [esp+25Ch+Destination]
0x10017204  push    ecx; Destination
0x10017205  lea     edx, [esp+260h+var_248]
0x10017209  mov     ecx, eax
0x1001720b  call    _ErrFilterDbName@16; ErrFilterDbName(x,x,x,x)
0x10017210  mov     esi, eax
0x10017212  test    esi, esi
0x10017214  js      loc_10017696
0x1001721a  mov     eax, [esp+258h+var_248]
0x1001721e  mov     [esp+258h+Str], eax
0x10017222  test    eax, eax
0x10017224  jnz     short loc_10017242
0x10017226  mov     eax, 0FFFFFC15h
0x1001722b  pop     edi
0x1001722c  pop     esi
0x1001722d  pop     ebx
0x1001722e  mov     ecx, [esp+24Ch+var_4]
0x10017235  xor     ecx, esp; StackCookie
0x10017237  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001723c  mov     esp, ebp
0x1001723e  pop     ebp
0x1001723f  retn    14h
0x10017242  push    2Ah ; '*'; Ch
0x10017244  push    eax; Str
0x10017245  call    ds:__imp__wcschr
0x1001724b  add     esp, 8
0x1001724e  test    eax, eax
0x10017250  jnz     loc_100176AF
0x10017256  push    3Fh ; '?'; Ch
0x10017258  push    [esp+25Ch+Str]; Str
0x1001725c  call    ds:__imp__wcschr
0x10017262  add     esp, 8
0x10017265  test    eax, eax
0x10017267  jnz     loc_100176AF
0x1001726d  cmp     edi, 0FFFFh
0x10017273  jnz     short loc_100172C4
0x10017275  push    [ebp+arg_10]
0x10017278  mov     edx, [esp+25Ch+Str]
0x1001727c  lea     eax, [esp+25Ch+var_240]
0x10017280  push    eax
0x10017281  push    [esp+260h+Block]
0x10017285  mov     ecx, ebx
0x10017287  call    _ErrIsamOpenDatabase@20; ErrIsamOpenDatabase(x,x,x,x,x)
0x1001728c  mov     ecx, ebx
0x1001728e  mov     esi, eax
0x10017290  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x10017295  imul    eax, 68h ; 'h'
0x10017298  mov     edi, dword_1016EAF8[eax]
0x1001729e  mov     [esp+258h+var_248], edi
0x100172a2  mov     [esp+258h+var_234], edi
0x100172a6  cmp     esi, 0FFFFFC00h
0x100172ac  jz      short loc_100172C4
0x100172ae  cmp     esi, 0FFFFFC05h
0x100172b4  jnz     loc_1001742C
0x100172ba  test    byte ptr [ebp+arg_10], 80h
0x100172be  jnz     loc_1001747B
0x100172c4  mov     edi, [esp+258h+Block]
0x100172c8  or      ebx, 0FFFFFFFFh
0x100172cb  mov     [esp+258h+var_248], edi
0x100172cf  mov     [esp+258h+var_230], esi
0x100172d3  cmp     [esp+258h+var_22C], 0FFFFh
0x100172db  jz      short loc_100172E8
0x100172dd  cmp     ebx, 0FFFFFFFFh
0x100172e0  jz      loc_10017366
0x100172e6  jmp     short loc_100172F0
0x100172e8  xor     eax, eax
0x100172ea  cmp     ebx, 0FFFFFFFFh
0x100172ed  cmovz   ebx, eax
0x100172f0  mov     ecx, [esp+258h+var_23C]
0x100172f4  call    _UtilGetIsibOfSesidIscb@4; UtilGetIsibOfSesidIscb(x)
0x100172f9  imul    eax, 68h ; 'h'
0x100172fc  mov     eax, dword_1016EAB0[eax]
0x10017302  cmp     eax, 0FFFFDDA0h
0x10017307  jnz     short loc_10017324
0x10017309  push    ecx
0x1001730a  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001730f  mov     ecx, [esp+258h+Block]
0x10017313  lea     eax, [esp+258h+var_248]
0x10017317  push    eax
0x10017318  mov     edx, offset aJet2X; "Jet 2.x"
0x1001731d  call    _ErrGenIISAMConnectString@12; ErrGenIISAMConnectString(x,x,x)
0x10017322  jmp     short loc_10017360
0x10017324  cmp     eax, 0FFFFDD9Fh
0x10017329  jnz     short loc_10017346
0x1001732b  push    ecx
0x1001732c  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017331  mov     ecx, [esp+258h+Block]
0x10017335  lea     eax, [esp+258h+var_248]
0x10017339  push    eax
0x1001733a  mov     edx, offset aJet3X; "Jet 3.x"
0x1001733f  call    _ErrGenIISAMConnectString@12; ErrGenIISAMConnectString(x,x,x)
0x10017344  jmp     short loc_10017360
0x10017346  mov     edx, ds:_rgIISAM[ebx*4]
0x1001734d  test    edx, edx
0x1001734f  jz      short loc_1001736A
0x10017351  mov     ecx, [esp+258h+Block]
0x10017355  lea     eax, [esp+258h+var_248]
0x10017359  push    eax
0x1001735a  call    _ErrGenIISAMConnectString@12; ErrGenIISAMConnectString(x,x,x)
0x1001735f  inc     ebx
0x10017360  mov     edi, [esp+258h+var_248]
0x10017364  mov     esi, eax
0x10017366  mov     ecx, [esp+258h+var_23C]
0x1001736a  test    esi, esi
0x1001736c  jnz     short loc_1001739D
0x1001736e  lea     eax, [esp+258h+var_224]
0x10017372  mov     edx, edi
0x10017374  push    eax
0x10017375  lea     eax, [esp+25Ch+var_21C]
0x10017379  push    eax
0x1001737a  lea     eax, [esp+260h+var_234]
0x1001737e  push    eax
0x1001737f  lea     eax, [esp+264h+var_22C]
0x10017383  push    eax
0x10017384  call    _ErrStartIsam@24; ErrStartIsam(x,x,x,x,x,x)
0x10017389  mov     esi, eax
0x1001738b  test    esi, esi
0x1001738d  jns     short loc_1001739F
0x1001738f  cmp     esi, 0FFFFFBE0h
0x10017395  jnz     short loc_100173BB
0x10017397  mov     esi, [esp+258h+var_230]
0x1001739b  test    esi, esi
0x1001739d  js      short loc_100173BB
0x1001739f  push    [ebp+arg_10]
0x100173a2  mov     edx, [esp+25Ch+var_22C]
0x100173a6  lea     eax, [esp+25Ch+var_240]
0x100173aa  mov     ecx, [esp+25Ch+var_23C]
0x100173ae  push    eax
0x100173af  push    edi
0x100173b0  push    [esp+264h+Str]
0x100173b4  call    _ErrOpenForeignDatabase@24; ErrOpenForeignDatabase(x,x,x,x,x,x)
0x100173b9  mov     esi, eax
0x100173bb  cmp     edi, [esp+258h+Block]
0x100173bf  jz      short loc_100173D5
0x100173c1  test    edi, edi
0x100173c3  jz      short loc_100173CF
0x100173c5  push    edi; Block
0x100173c6  call    ds:__imp__free
0x100173cc  add     esp, 4
0x100173cf  xor     edi, edi
0x100173d1  mov     [esp+258h+var_248], edi
0x100173d5  test    esi, esi
0x100173d7  jns     short loc_10017424
0x100173d9  cmp     esi, 0FFFFF88Fh
0x100173df  jz      loc_10017471
0x100173e5  cmp     esi, 0FFFFFB4Eh
0x100173eb  jz      loc_10017471
0x100173f1  cmp     esi, 0FFFFDFFEh
0x100173f7  jz      short loc_10017471
  ... truncated ...
```
