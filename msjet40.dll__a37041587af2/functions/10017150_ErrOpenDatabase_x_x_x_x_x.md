# ErrOpenDatabase(x,x,x,x,x)

- ea: `0x10017150`
- end: `0x1001780b`
- name: `_ErrOpenDatabase@20`
- size: `1723`
- prototype: ``
- caller_count: `8`
- callee_count: `22`
- tags: `authz_impersonation, service_task`

## callers

- `0x1001b8a0`
- `0x1001e380`
- `0x1001ecc0`
- `0x10025c70`
- `0x1002c160`
- `0x1002c7b0`
- `0x10032920`
- `0x10033bb0`

## callees

- `0x100170c0`
- `0x10017150`
- `0x10017820`
- `0x10029910`
- `0x1002a1c0`
- `0x1002a700`
- `0x1003a970`
- `0x1003c8e0`
- `0x1003e7e0`
- `0x1003e830`
- `0x1003e860`
- `0x1003e9b0`
- `0x1003ea00`
- `0x1003f080`
- `0x1003f0d0`
- `0x10042b60`
- `0x10043060`
- `0x1004901b`
- `0x100982ca`
- `0x10117340`
- `0x10121d80`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10017506`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10017506`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10017385`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1001739c`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x10017385`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1001739c`

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
  char v48[4]; // [esp+3Ch] [ebp-21Ch] BYREF
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
  for ( i = a2; v7 != -1; v7 = dword_1016EB88[26 * v7] )
  {
    if ( rgsib[26 * v7] == a1 )
      break;
  }
  if ( v7 >= 0 )
  {
    _mm_lfence();
    v39 = dword_1016EB44[26 * v7];
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
      v14 = dword_1016EB98[26 * UtilGetIsibOfSesid(a1)];
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
    v19 = dword_1016EB98[26 * UtilGetIsibOfSesid(a1)];
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
    v22 = dword_1016EB50[26 * UtilGetIsibOfSesidIscb(v40)];
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
0x10017150  mov     edi, edi
0x10017152  push    ebp
0x10017153  mov     ebp, esp
0x10017155  and     esp, 0FFFFFFF8h
0x10017158  sub     esp, 24Ch
0x1001715e  mov     eax, ___security_cookie
0x10017163  xor     eax, esp
0x10017165  mov     [esp+24Ch+var_4], eax
0x1001716c  mov     eax, [ebp+arg_C]
0x1001716f  push    ebx
0x10017170  mov     ebx, [ebp+arg_0]
0x10017173  push    esi
0x10017174  mov     esi, [ebp+arg_8]
0x10017177  mov     [esp+254h+var_228], eax
0x1001717b  mov     eax, _isibHead
0x10017180  mov     [esp+254h+Block], esi
0x10017184  mov     [esp+254h+var_23C], ebx
0x10017188  mov     [esp+254h+var_224], 0
0x10017190  mov     [esp+254h+var_234], 0FFFFFFFFh
0x10017198  push    edi
0x10017199  mov     edi, [ebp+arg_4]
0x1001719c  mov     [esp+258h+Str], edi
0x100171a0  mov     [esp+258h+var_248], edi
0x100171a4  cmp     eax, 0FFFFFFFFh
0x100171a7  jz      short loc_100171C6
0x100171a9  nop     dword ptr [eax+00000000h]
0x100171b0  imul    ecx, eax, 68h ; 'h'
0x100171b3  cmp     _rgsib[ecx], ebx
0x100171b9  jz      short loc_100171C6
0x100171bb  mov     eax, dword_1016EB88[ecx]
0x100171c1  cmp     eax, 0FFFFFFFFh
0x100171c4  jnz     short loc_100171B0
0x100171c6  test    eax, eax
0x100171c8  jns     short loc_100171D4
0x100171ca  mov     [esp+258h+var_240], 0FFFFFFFFh
0x100171d2  jmp     short loc_100171E4
0x100171d4  imul    eax, 68h ; 'h'
0x100171d7  lfence
0x100171da  mov     eax, dword_1016EB44[eax]
0x100171e0  mov     [esp+258h+var_240], eax
0x100171e4  xor     eax, eax
0x100171e6  push    ebx
0x100171e7  mov     [esp+25Ch+var_220], eax
0x100171eb  call    _FValidSesid@4; FValidSesid(x)
0x100171f0  test    eax, eax
0x100171f2  jnz     short loc_10017210
0x100171f4  mov     eax, 0FFFFFBB0h
0x100171f9  pop     edi
0x100171fa  pop     esi
0x100171fb  pop     ebx
0x100171fc  mov     ecx, [esp+24Ch+var_4]
0x10017203  xor     ecx, esp; StackCookie
0x10017205  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001720a  mov     esp, ebp
0x1001720c  pop     ebp
0x1001720d  retn    14h
0x10017210  test    edi, edi
0x10017212  jz      short loc_10017224
0x10017214  xor     eax, eax
0x10017216  cmp     [edi], ax
0x10017219  cmovz   edi, eax
0x1001721c  mov     [esp+258h+Str], edi
0x10017220  mov     [esp+258h+var_248], edi
0x10017224  test    esi, esi
0x10017226  jz      short loc_10017236
0x10017228  xor     eax, eax
0x1001722a  cmp     [esi], ax
0x1001722d  cmovnz  eax, esi
0x10017230  mov     esi, eax
0x10017232  mov     [esp+258h+Block], eax
0x10017236  mov     ecx, [esp+258h+var_240]
0x1001723a  lea     eax, [esp+258h+var_22C]
0x1001723e  push    eax
0x1001723f  mov     edx, esi
0x10017241  call    _ErrGetIsamType@12; ErrGetIsamType(x,x,x)
0x10017246  mov     esi, eax
0x10017248  test    esi, esi
0x1001724a  js      loc_100177D6
0x10017250  mov     edi, [esp+258h+var_22C]
0x10017254  cmp     edi, 0FFFFh
0x1001725a  jz      loc_10017327
0x10017260  cmp     edi, 0FFFEh
0x10017266  jz      short loc_10017289
0x10017268  mov     ecx, [esp+258h+var_240]
0x1001726c  mov     edx, edi
0x1001726e  call    _UtilGetPiicbtaskOfItib@8; UtilGetPiicbtaskOfItib(x,x)
0x10017273  mov     eax, [eax]
0x10017275  test    dword ptr [eax], 1
0x1001727b  jnz     loc_10017327
0x10017281  cmp     edi, 0FFFEh
0x10017287  jnz     short loc_100172B3
0x10017289  push    [ebp+arg_10]; int
0x1001728c  mov     ecx, [esp+25Ch+var_228]
0x10017290  push    ecx; int
0x10017291  push    [esp+260h+Block]; int
0x10017295  mov     ecx, ebx; int
0x10017297  call    _ErrRdbOpenDatabase@20; ErrRdbOpenDatabase(x,x,x,x,x)
0x1001729c  mov     ecx, ebx
0x1001729e  mov     esi, eax
0x100172a0  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100172a5  imul    eax, 68h ; 'h'
0x100172a8  mov     ecx, dword_1016EB98[eax]
0x100172ae  jmp     loc_10017640
0x100172b3  mov     esi, [esp+258h+Block]
0x100172b7  lea     eax, [esp+258h+var_230]
0x100172bb  push    eax
0x100172bc  lea     eax, [esp+25Ch+var_23C]
0x100172c0  mov     edx, esi
0x100172c2  push    eax
0x100172c3  lea     eax, [esp+260h+var_234]
0x100172c7  mov     ecx, ebx
0x100172c9  push    eax
0x100172ca  lea     eax, [esp+264h+var_22C]
0x100172ce  push    eax
0x100172cf  call    _ErrStartIsam@24; ErrStartIsam(x,x,x,x,x,x)
0x100172d4  test    eax, eax
0x100172d6  js      loc_100177F4
0x100172dc  mov     eax, [esp+258h+Str]
0x100172e0  test    eax, eax
0x100172e2  jnz     short loc_10017305
0x100172e4  push    ecx; int
0x100172e5  lea     eax, [esp+25Ch+Destination]
0x100172e9  mov     ecx, esi
0x100172eb  push    eax; Destination
0x100172ec  lea     edx, [esp+260h+var_248]
0x100172f0  call    _ErrFilterDbName@16; ErrFilterDbName(x,x,x,x)
0x100172f5  test    eax, eax
0x100172f7  js      loc_100177F4
0x100172fd  mov     eax, [esp+258h+var_248]
0x10017301  test    eax, eax
0x10017303  jz      short loc_10017366
0x10017305  push    [ebp+arg_10]
0x10017308  mov     ecx, [esp+25Ch+var_228]
0x1001730c  mov     edi, [esp+25Ch+var_22C]
0x10017310  mov     edx, edi
0x10017312  push    ecx
0x10017313  push    esi
0x10017314  push    eax
0x10017315  mov     ecx, ebx
0x10017317  call    _ErrOpenForeignDatabase@24; ErrOpenForeignDatabase(x,x,x,x,x,x)
0x1001731c  mov     ecx, [esp+258h+var_234]
0x10017320  mov     esi, eax
0x10017322  jmp     loc_10017640
0x10017327  mov     eax, [esp+258h+Str]
0x1001732b  mov     [esp+258h+var_240], 0
0x10017333  test    eax, eax
0x10017335  jnz     short loc_10017382
0x10017337  mov     eax, [esp+258h+Block]
0x1001733b  test    eax, eax
0x1001733d  jz      short loc_10017366
0x1001733f  push    ecx; int
0x10017340  lea     ecx, [esp+25Ch+Destination]
0x10017344  push    ecx; Destination
0x10017345  lea     edx, [esp+260h+var_248]
0x10017349  mov     ecx, eax
0x1001734b  call    _ErrFilterDbName@16; ErrFilterDbName(x,x,x,x)
0x10017350  mov     esi, eax
0x10017352  test    esi, esi
0x10017354  js      loc_100177D6
0x1001735a  mov     eax, [esp+258h+var_248]
0x1001735e  mov     [esp+258h+Str], eax
0x10017362  test    eax, eax
0x10017364  jnz     short loc_10017382
0x10017366  mov     eax, 0FFFFFC15h
0x1001736b  pop     edi
0x1001736c  pop     esi
0x1001736d  pop     ebx
0x1001736e  mov     ecx, [esp+24Ch+var_4]
0x10017375  xor     ecx, esp; StackCookie
0x10017377  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001737c  mov     esp, ebp
0x1001737e  pop     ebp
0x1001737f  retn    14h
0x10017382  push    2Ah ; '*'; Ch
0x10017384  push    eax; Str
0x10017385  call    ds:__imp__wcschr
0x1001738b  add     esp, 8
0x1001738e  test    eax, eax
0x10017390  jnz     loc_100177EF
0x10017396  push    3Fh ; '?'; Ch
0x10017398  push    [esp+25Ch+Str]; Str
0x1001739c  call    ds:__imp__wcschr
0x100173a2  add     esp, 8
0x100173a5  test    eax, eax
0x100173a7  jnz     loc_100177EF
0x100173ad  cmp     edi, 0FFFFh
0x100173b3  jnz     short loc_10017404
0x100173b5  push    [ebp+arg_10]
0x100173b8  mov     edx, [esp+25Ch+Str]
0x100173bc  lea     eax, [esp+25Ch+var_240]
0x100173c0  push    eax
0x100173c1  push    [esp+260h+Block]
0x100173c5  mov     ecx, ebx
0x100173c7  call    _ErrIsamOpenDatabase@20; ErrIsamOpenDatabase(x,x,x,x,x)
0x100173cc  mov     ecx, ebx
0x100173ce  mov     esi, eax
0x100173d0  call    _UtilGetIsibOfSesid@4; UtilGetIsibOfSesid(x)
0x100173d5  imul    eax, 68h ; 'h'
0x100173d8  mov     edi, dword_1016EB98[eax]
0x100173de  mov     [esp+258h+var_248], edi
0x100173e2  mov     [esp+258h+var_234], edi
0x100173e6  cmp     esi, 0FFFFFC00h
0x100173ec  jz      short loc_10017404
0x100173ee  cmp     esi, 0FFFFFC05h
0x100173f4  jnz     loc_1001756C
0x100173fa  test    byte ptr [ebp+arg_10], 80h
0x100173fe  jnz     loc_100175BB
0x10017404  mov     edi, [esp+258h+Block]
0x10017408  or      ebx, 0FFFFFFFFh
0x1001740b  mov     [esp+258h+var_248], edi
0x1001740f  mov     [esp+258h+var_230], esi
0x10017413  cmp     [esp+258h+var_22C], 0FFFFh
0x1001741b  jz      short loc_10017428
0x1001741d  cmp     ebx, 0FFFFFFFFh
0x10017420  jz      loc_100174A6
0x10017426  jmp     short loc_10017430
0x10017428  xor     eax, eax
0x1001742a  cmp     ebx, 0FFFFFFFFh
0x1001742d  cmovz   ebx, eax
0x10017430  mov     ecx, [esp+258h+var_23C]
0x10017434  call    _UtilGetIsibOfSesidIscb@4; UtilGetIsibOfSesidIscb(x)
0x10017439  imul    eax, 68h ; 'h'
0x1001743c  mov     eax, dword_1016EB50[eax]
0x10017442  cmp     eax, 0FFFFDDA0h
0x10017447  jnz     short loc_10017464
0x10017449  push    ecx
0x1001744a  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x1001744f  mov     ecx, [esp+258h+Block]
0x10017453  lea     eax, [esp+258h+var_248]
0x10017457  push    eax
0x10017458  mov     edx, offset aJet2X; "Jet 2.x"
0x1001745d  call    _ErrGenIISAMConnectString@12; ErrGenIISAMConnectString(x,x,x)
0x10017462  jmp     short loc_100174A0
0x10017464  cmp     eax, 0FFFFDD9Fh
0x10017469  jnz     short loc_10017486
0x1001746b  push    ecx
0x1001746c  call    _ClearErrorInfo@4; ClearErrorInfo(x)
0x10017471  mov     ecx, [esp+258h+Block]
0x10017475  lea     eax, [esp+258h+var_248]
0x10017479  push    eax
0x1001747a  mov     edx, offset aJet3X; "Jet 3.x"
0x1001747f  call    _ErrGenIISAMConnectString@12; ErrGenIISAMConnectString(x,x,x)
0x10017484  jmp     short loc_100174A0
0x10017486  mov     edx, ds:_rgIISAM[ebx*4]
0x1001748d  test    edx, edx
0x1001748f  jz      short loc_100174AA
0x10017491  mov     ecx, [esp+258h+Block]
0x10017495  lea     eax, [esp+258h+var_248]
0x10017499  push    eax
0x1001749a  call    _ErrGenIISAMConnectString@12; ErrGenIISAMConnectString(x,x,x)
0x1001749f  inc     ebx
0x100174a0  mov     edi, [esp+258h+var_248]
0x100174a4  mov     esi, eax
0x100174a6  mov     ecx, [esp+258h+var_23C]
0x100174aa  test    esi, esi
0x100174ac  jnz     short loc_100174DD
0x100174ae  lea     eax, [esp+258h+var_224]
0x100174b2  mov     edx, edi
0x100174b4  push    eax
0x100174b5  lea     eax, [esp+25Ch+var_21C]
0x100174b9  push    eax
0x100174ba  lea     eax, [esp+260h+var_234]
0x100174be  push    eax
0x100174bf  lea     eax, [esp+264h+var_22C]
0x100174c3  push    eax
0x100174c4  call    _ErrStartIsam@24; ErrStartIsam(x,x,x,x,x,x)
0x100174c9  mov     esi, eax
0x100174cb  test    esi, esi
0x100174cd  jns     short loc_100174DF
0x100174cf  cmp     esi, 0FFFFFBE0h
0x100174d5  jnz     short loc_100174FB
0x100174d7  mov     esi, [esp+258h+var_230]
0x100174db  test    esi, esi
0x100174dd  js      short loc_100174FB
0x100174df  push    [ebp+arg_10]
0x100174e2  mov     edx, [esp+25Ch+var_22C]
0x100174e6  lea     eax, [esp+25Ch+var_240]
0x100174ea  mov     ecx, [esp+25Ch+var_23C]
0x100174ee  push    eax
0x100174ef  push    edi
0x100174f0  push    [esp+264h+Str]
0x100174f4  call    _ErrOpenForeignDatabase@24; ErrOpenForeignDatabase(x,x,x,x,x,x)
0x100174f9  mov     esi, eax
0x100174fb  cmp     edi, [esp+258h+Block]
0x100174ff  jz      short loc_10017515
0x10017501  test    edi, edi
0x10017503  jz      short loc_1001750F
0x10017505  push    edi; Block
0x10017506  call    ds:__imp__free
0x1001750c  add     esp, 4
0x1001750f  xor     edi, edi
0x10017511  mov     [esp+258h+var_248], edi
0x10017515  test    esi, esi
0x10017517  jns     short loc_10017564
0x10017519  cmp     esi, 0FFFFF88Fh
0x1001751f  jz      loc_100175B1
0x10017525  cmp     esi, 0FFFFFB4Eh
0x1001752b  jz      loc_100175B1
0x10017531  cmp     esi, 0FFFFDFFEh
0x10017537  jz      short loc_100175B1
  ... truncated ...
```
