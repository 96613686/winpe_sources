# ErrRmtCreateLink(x,x,x,x,x,x,x,x)

- ea: `0x10099389`
- end: `0x10099845`
- name: `_ErrRmtCreateLink@32`
- size: `1212`
- prototype: `int __thiscall(int, int, int, int, int, int, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1002b290`
- `0x1002d010`

## callees

- `0x10012af0`
- `0x10017010`
- `0x1001bdd0`
- `0x1002a840`
- `0x1002a9c0`
- `0x100436d0`
- `0x100437f0`
- `0x100439d0`
- `0x10044f80`
- `0x1009600d`
- `0x10096b5f`
- `0x10096c58`
- `0x10097481`
- `0x10099389`
- `0x1009984b`
- `0x10099e6a`
- `0x1009aa05`
- `0x1009b98e`
- `0x100c99c2`
- `0x100c9a29`
- `0x100c9a9a`
- `0x100d74ab`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1009950d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1009950d`

## pseudocode

```c
int __fastcall ErrRmtCreateLink(Session *a1, _DWORD **a2, int a3, int a4, int a5, void *a6, int a7, int a8)
{
  int v8; // ebx
  char *v10; // ecx
  unsigned int v11; // esi
  __int16 v12; // ax
  char *v13; // ecx
  __int16 v14; // ax
  int result; // eax
  int Table; // eax
  int Timestamp; // esi
  wchar_t *v18; // eax
  int ObjInfoId; // eax
  int v20; // ecx
  char *v21; // eax
  __int16 *v22; // esi
  __int16 *v23; // ecx
  __int16 v24; // ax
  char *v25; // esi
  int v26; // ecx
  unsigned int v27; // eax
  char *v28; // ecx
  __int16 v29; // ax
  _DWORD **v30; // [esp+Ch] [ebp-794h] BYREF
  char *v31; // [esp+10h] [ebp-790h] BYREF
  void *Src; // [esp+14h] [ebp-78Ch]
  int v33; // [esp+18h] [ebp-788h]
  int v34; // [esp+1Ch] [ebp-784h] BYREF
  int v35; // [esp+20h] [ebp-780h]
  _DWORD *v36; // [esp+24h] [ebp-77Ch]
  int v37; // [esp+28h] [ebp-778h] BYREF
  int v38; // [esp+2Ch] [ebp-774h]
  _DWORD **v39; // [esp+30h] [ebp-770h] BYREF
  wchar_t *v40; // [esp+34h] [ebp-76Ch]
  wchar_t *v41; // [esp+38h] [ebp-768h]
  __int16 v42; // [esp+3Ch] [ebp-764h]
  int v43; // [esp+40h] [ebp-760h]
  int v44; // [esp+44h] [ebp-75Ch]
  int v45; // [esp+48h] [ebp-758h]
  char v46; // [esp+4Ch] [ebp-754h] BYREF
  int v47; // [esp+D4h] [ebp-6CCh]
  int v48; // [esp+D8h] [ebp-6C8h]
  _BYTE v49[52]; // [esp+15Ch] [ebp-644h] BYREF
  wchar_t Str[256]; // [esp+190h] [ebp-610h] BYREF
  char v51; // [esp+390h] [ebp-410h] BYREF
  char v52; // [esp+39Ah] [ebp-406h] BYREF

  v35 = a4;
  Src = a6;
  v38 = a7;
  v8 = -1;
  v30 = a2;
  v33 = 0;
  v48 = 0;
  v34 = -1;
  v43 = -1;
  ErrVdbidOfDbid(&v30);
  v10 = (char *)v35;
  v11 = a8 & 0xBFFFFFFF;
  v36 = v30[157];
  a8 &= ~0x40000000u;
  v31 = (char *)(v35 + 2);
  do
  {
    v12 = *(_WORD *)v10;
    v10 += 2;
  }
  while ( v12 != (_WORD)v33 );
  if ( !((v10 - v31) >> 1) )
    return -1003;
  v13 = (char *)Src;
  v31 = (char *)Src + 2;
  do
  {
    v14 = *(_WORD *)v13;
    v13 += 2;
  }
  while ( v14 != (_WORD)v33 );
  if ( !((v13 - v31) >> 1) || (v11 & 0xDFFFFFFF) != 0 )
    return -1003;
  if ( !**v30 )
  {
    result = ErrReviveConn(a1);
    if ( result < 0 )
      return result;
    v11 = a8;
  }
  a8 = v11 | 0x100000;
  result = ErrQjetBeginTransaction(a1, 0);
  if ( result >= 0 )
  {
    Table = JetCreateTable((int)a1, a5, Src, 4, 90, (int)&v37);
    Timestamp = Table;
    if ( Table == -1303 )
    {
      Timestamp = -1314;
    }
    else if ( Table >= 0 )
    {
      v43 = v37;
      WCSCPY2(256);
      v18 = _wcschr(Str, 0x2Eu);
      if ( v18 )
      {
        v41 = Str;
        v42 = v18 - Str;
        v40 = v18 + 1;
      }
      else
      {
        v41 = 0;
        v40 = Str;
        v42 = 0;
      }
      v39 = v30;
      Timestamp = ErrRmtGetTimestamp(&v39);
      if ( Timestamp >= 0 )
      {
        Timestamp = ErrRmtMirrorColumns(&v39, Src, a5);
        if ( Timestamp >= 0 )
        {
          Timestamp = ErrRmtMirrorStatistics(a1, v36, &v39);
          if ( Timestamp >= 0 )
          {
            Timestamp = ErrRmtGetCapabilities(v49);
            if ( Timestamp >= 0 )
            {
              ObjInfoId = ErrGetObjInfoId(1, Src, &v34, 0);
              v8 = v34;
              Timestamp = ObjInfoId;
              if ( ObjInfoId >= 0 )
              {
                Timestamp = ErrDispPrepareUpdate2(a1, v34, 2);
                if ( Timestamp >= 0 )
                {
                  v21 = &v46;
                  if ( v47 )
                    v21 = 0;
                  Timestamp = ErrRMTSetSoInfo(v44, v45, v21, v49, v20);
                  if ( Timestamp >= 0 )
                  {
                    Timestamp = ErrSetSysField(L"RmtInfoLong", v30[3], 6 * *((__int16 *)v30 + 8));
                    if ( Timestamp >= 0 )
                    {
                      v22 = (__int16 *)v38;
                      if ( v38 && !WCSNICMP(5) )
                      {
                        v23 = v22;
                        do
                          v24 = *v23++;
                        while ( v24 != (_WORD)v33 );
                      }
                      WCSCPY2(513);
                      v25 = &v51;
                      if ( !WCSNICMP(5) )
                        v25 = &v52;
                      v26 = *(_DWORD *)(PconnOfHdbc(**v30) + 4);
                      v27 = a8;
                      if ( (a8 & 0x20000000) != 0 && (v26 & 8) != 0 )
                      {
                        v27 = a8 & 0xDFFFFFFF;
                        a8 &= ~0x20000000u;
                      }
                      if ( (v27 & 0x20000000) == 0 )
                      {
                        RemoveField(v25, L"UID=");
                        RemoveField(v25, L"PWD=");
                      }
                      v28 = v25;
                      do
                      {
                        v29 = *(_WORD *)v28;
                        v28 += 2;
                      }
                      while ( v29 != (_WORD)v33 );
                      Timestamp = ErrSetSysField(L"Connect", v25, 2 * ((v28 - (v25 + 2)) >> 1));
                      if ( Timestamp >= 0 )
                      {
                        Timestamp = ErrSetSysField(L"ForeignName", Str, 2 * wcslen(Str));
                        if ( Timestamp >= 0 )
                        {
                          LOWORD(v31) = 4;
                          Timestamp = ErrSetSysField(L"Type", &v31, 2);
                          if ( Timestamp >= 0 )
                          {
                            Timestamp = ErrSetSysField(L"Flags", &a8, 4);
                            if ( Timestamp >= 0 )
                            {
                              Timestamp = ErrDispUpdate(a1, v8, 0, 0, 0);
                              if ( Timestamp >= 0 )
                              {
                                Timestamp = ErrQjetCommitTransaction(0);
                                if ( Timestamp >= 0 )
                                {
                                  ErrDispCloseTable(a1, v43);
                                  v43 = -1;
                                  ErrDispCloseTable(a1, v8);
                                  RmtStartIdle(**v30);
                                  return 0;
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( v43 != -1 )
    {
      ErrDispCloseTable(a1, v43);
      v43 = -1;
    }
    if ( v8 != -1 )
      ErrDispCloseTable(a1, v8);
    ErrQjetRollback(a1, 0);
    return Timestamp;
  }
  return result;
}

```

## disassembly

```asm
0x10099389  mov     edi, edi
0x1009938b  push    ebp
0x1009938c  mov     ebp, esp
0x1009938e  and     esp, 0FFFFFFF8h
0x10099391  sub     esp, 794h
0x10099397  mov     eax, ___security_cookie
0x1009939c  xor     eax, esp
0x1009939e  mov     [esp+794h+var_4], eax
0x100993a5  mov     eax, [ebp+arg_4]
0x100993a8  mov     [esp+794h+var_780], eax
0x100993ac  mov     eax, [ebp+arg_C]
0x100993af  mov     [esp+794h+Src], eax
0x100993b3  mov     eax, [ebp+arg_10]
0x100993b6  push    ebx
0x100993b7  mov     [esp+798h+var_774], eax
0x100993bb  or      ebx, 0FFFFFFFFh
0x100993be  xor     eax, eax
0x100993c0  mov     [esp+798h+var_794], edx
0x100993c4  push    esi
0x100993c5  push    edi
0x100993c6  mov     [esp+7A0h+var_788], eax
0x100993ca  mov     edi, ecx
0x100993cc  mov     [esp+7A0h+var_6C8], eax
0x100993d3  lea     eax, [esp+7A0h+var_794]
0x100993d7  push    eax
0x100993d8  mov     [esp+7A4h+var_784], ebx
0x100993dc  mov     [esp+7A4h+var_760], 0FFFFFFFFh
0x100993e4  call    _ErrVdbidOfDbid@12; ErrVdbidOfDbid(x,x,x)
0x100993e9  mov     edx, [esp+7A0h+var_794]
0x100993ed  mov     ecx, [esp+7A0h+var_780]
0x100993f1  mov     esi, [ebp+arg_14]
0x100993f4  and     esi, 0BFFFFFFFh
0x100993fa  mov     eax, [edx+274h]
0x10099400  mov     [esp+7A0h+var_77C], eax
0x10099404  lea     eax, [ecx+2]
0x10099407  mov     [ebp+arg_14], esi
0x1009940a  mov     [esp+7A0h+var_790], eax
0x1009940e  mov     ax, [ecx]
0x10099411  add     ecx, 2
0x10099414  cmp     ax, word ptr [esp+7A0h+var_788]
0x10099419  jnz     short loc_1009940E
0x1009941b  sub     ecx, [esp+7A0h+var_790]
0x1009941f  sar     ecx, 1
0x10099421  jz      loc_10099829
0x10099427  mov     ecx, [esp+7A0h+Src]
0x1009942b  lea     eax, [ecx+2]
0x1009942e  mov     [esp+7A0h+var_790], eax
0x10099432  mov     ax, [ecx]
0x10099435  add     ecx, 2
0x10099438  cmp     ax, word ptr [esp+7A0h+var_788]
0x1009943d  jnz     short loc_10099432
0x1009943f  sub     ecx, [esp+7A0h+var_790]
0x10099443  sar     ecx, 1
0x10099445  jz      loc_10099829
0x1009944b  test    esi, 0DFFFFFFFh
0x10099451  jnz     loc_10099829
0x10099457  mov     edx, [edx]
0x10099459  cmp     dword ptr [edx], 0
0x1009945c  jnz     short loc_10099470
0x1009945e  mov     ecx, edi
0x10099460  call    _ErrReviveConn@8; ErrReviveConn(x,x)
0x10099465  test    eax, eax
0x10099467  js      loc_1009982E
0x1009946d  mov     esi, [ebp+arg_14]
0x10099470  or      esi, 100000h
0x10099476  xor     edx, edx
0x10099478  mov     ecx, edi
0x1009947a  mov     [ebp+arg_14], esi
0x1009947d  call    _ErrQjetBeginTransaction@8; ErrQjetBeginTransaction(x,x)
0x10099482  test    eax, eax
0x10099484  js      loc_1009982E
0x1009948a  lea     eax, [esp+7A0h+var_778]
0x1009948e  push    eax; int
0x1009948f  push    5Ah ; 'Z'; int
0x10099491  push    4; int
0x10099493  push    [esp+7ACh+Src]; Src
0x10099497  push    [ebp+arg_8]; int
0x1009949a  push    edi; int
0x1009949b  call    _JetCreateTable@24; JetCreateTable(x,x,x,x,x,x)
0x100994a0  mov     esi, eax
0x100994a2  cmp     esi, 0FFFFFAE9h
0x100994a8  jnz     short loc_100994E2
0x100994aa  add     esi, 0FFFFFFF5h
0x100994ad  cmp     [esp+7A0h+var_760], 0FFFFFFFFh
0x100994b2  jz      short loc_100994C6
0x100994b4  push    [esp+7A0h+var_760]
0x100994b8  push    edi
0x100994b9  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x100994be  mov     [esp+7A0h+var_760], 0FFFFFFFFh
0x100994c6  cmp     ebx, 0FFFFFFFFh
0x100994c9  jz      short loc_100994D2
0x100994cb  push    ebx
0x100994cc  push    edi
0x100994cd  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x100994d2  push    0; int
0x100994d4  mov     ecx, edi; Session *
0x100994d6  call    _ErrQjetRollback@12; ErrQjetRollback(x,x,x)
0x100994db  mov     eax, esi
0x100994dd  jmp     loc_1009982E
0x100994e2  test    esi, esi
0x100994e4  js      short loc_100994AD
0x100994e6  mov     eax, [esp+7A0h+var_778]
0x100994ea  lea     ecx, [esp+7A0h+Str]
0x100994f1  mov     edx, [esp+7A0h+var_780]
0x100994f5  push    100h
0x100994fa  mov     [esp+7A4h+var_760], eax
0x100994fe  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10099503  lea     eax, [esp+7A0h+Str]
0x1009950a  push    2Eh ; '.'; Ch
0x1009950c  push    eax; Str
0x1009950d  call    ds:__imp__wcschr
0x10099513  pop     ecx
0x10099514  pop     ecx
0x10099515  test    eax, eax
0x10099517  jz      short loc_1009953F
0x10099519  lea     ecx, [esp+7A0h+Str]
0x10099520  mov     [esp+7A0h+var_768], ecx
0x10099524  lea     edx, [esp+7A0h+Str]
0x1009952b  mov     ecx, eax
0x1009952d  sub     ecx, edx
0x1009952f  sar     ecx, 1
0x10099531  add     eax, 2
0x10099534  mov     [esp+7A0h+var_764], cx
0x10099539  mov     [esp+7A0h+var_76C], eax
0x1009953d  jmp     short loc_10099559
0x1009953f  lea     eax, [esp+7A0h+Str]
0x10099546  mov     [esp+7A0h+var_768], 0
0x1009954e  mov     [esp+7A0h+var_76C], eax
0x10099552  xor     eax, eax
0x10099554  mov     [esp+7A0h+var_764], ax
0x10099559  mov     eax, [esp+7A0h+var_794]
0x1009955d  mov     ecx, edi
0x1009955f  mov     [esp+7A0h+var_770], eax
0x10099563  lea     eax, [esp+7A0h+var_770]
0x10099567  push    eax
0x10099568  call    ErrRmtGetTimestamp
0x1009956d  mov     esi, eax
0x1009956f  test    esi, esi
0x10099571  js      loc_100994AD
0x10099577  push    [ebp+arg_8]
0x1009957a  mov     edx, [esp+7A4h+var_77C]
0x1009957e  lea     eax, [esp+7A4h+var_770]
0x10099582  push    [esp+7A4h+Src]
0x10099586  mov     ecx, edi
0x10099588  push    eax
0x10099589  call    ErrRmtMirrorColumns
0x1009958e  mov     esi, eax
0x10099590  test    esi, esi
0x10099592  js      loc_100994AD
0x10099598  mov     edx, [esp+7A0h+var_77C]
0x1009959c  lea     eax, [esp+7A0h+var_770]
0x100995a0  push    eax
0x100995a1  mov     ecx, edi
0x100995a3  call    ErrRmtMirrorStatistics
0x100995a8  mov     esi, eax
0x100995aa  test    esi, esi
0x100995ac  js      loc_100994AD
0x100995b2  mov     edx, [esp+7A0h+var_794]
0x100995b6  lea     eax, [esp+7A0h+var_644]
0x100995bd  push    eax
0x100995be  mov     ecx, edi
0x100995c0  call    _ErrRmtGetCapabilities@12; ErrRmtGetCapabilities(x,x,x)
0x100995c5  mov     esi, eax
0x100995c7  test    esi, esi
0x100995c9  js      loc_100994AD
0x100995cf  mov     edx, [ebp+arg_8]
0x100995d2  lea     eax, [esp+7A0h+var_784]
0x100995d6  push    0
0x100995d8  push    eax
0x100995d9  push    [esp+7A8h+Src]
0x100995dd  mov     ecx, edi
0x100995df  push    1
0x100995e1  call    _ErrGetObjInfoId@24; ErrGetObjInfoId(x,x,x,x,x,x)
0x100995e6  mov     ebx, [esp+7A0h+var_784]
0x100995ea  mov     esi, eax
0x100995ec  test    esi, esi
0x100995ee  js      loc_100994AD
0x100995f4  push    2
0x100995f6  push    ebx
0x100995f7  push    edi
0x100995f8  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100995fd  mov     esi, eax
0x100995ff  test    esi, esi
0x10099601  js      loc_100994AD
0x10099607  push    ecx
0x10099608  xor     ecx, ecx
0x1009960a  lea     eax, [esp+7A4h+var_644]
0x10099611  cmp     [esp+7A4h+var_6CC], ecx
0x10099618  mov     edx, ebx
0x1009961a  push    eax
0x1009961b  lea     eax, [esp+7A8h+var_754]
0x1009961f  cmovnz  eax, ecx
0x10099622  mov     ecx, edi
0x10099624  push    eax
0x10099625  push    [esp+7ACh+var_758]
0x10099629  push    [esp+7B0h+var_75C]
0x1009962d  call    _ErrRMTSetSoInfo@28; ErrRMTSetSoInfo(x,x,x,x,x,x,x)
0x10099632  mov     esi, eax
0x10099634  test    esi, esi
0x10099636  js      loc_100994AD
0x1009963c  mov     ecx, [esp+7A0h+var_794]
0x10099640  mov     edx, ebx
0x10099642  movsx   eax, word ptr [ecx+10h]
0x10099646  imul    eax, 6
0x10099649  push    eax
0x1009964a  push    dword ptr [ecx+0Ch]
0x1009964d  mov     ecx, edi
0x1009964f  push    offset _wszSoRmtInfoLong; "RmtInfoLong"
0x10099654  call    _ErrSetSysField@20; ErrSetSysField(x,x,x,x,x)
0x10099659  mov     esi, eax
0x1009965b  test    esi, esi
0x1009965d  js      loc_100994AD
0x10099663  mov     esi, [esp+7A0h+var_774]
0x10099667  test    esi, esi
0x10099669  jz      short loc_10099698
0x1009966b  push    5
0x1009966d  mov     edx, offset _wszODBC; "ODBC;"
0x10099672  mov     ecx, esi
0x10099674  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10099679  test    eax, eax
0x1009967b  jnz     short loc_1009969F
0x1009967d  mov     ecx, esi
0x1009967f  lea     edx, [ecx+2]
0x10099682  mov     ax, [ecx]
0x10099685  add     ecx, 2
0x10099688  cmp     ax, word ptr [esp+7A0h+var_788]
0x1009968d  jnz     short loc_10099682
0x1009968f  sub     ecx, edx
0x10099691  sar     ecx, 1
0x10099693  cmp     ecx, 5
0x10099696  jnz     short loc_1009969F
0x10099698  mov     eax, [esp+7A0h+var_794]
0x1009969c  mov     esi, [eax+4]
0x1009969f  push    201h
0x100996a4  mov     edx, esi
0x100996a6  lea     ecx, [esp+7A4h+var_410]
0x100996ad  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100996b2  push    5
0x100996b4  mov     edx, offset _wszODBC; "ODBC;"
0x100996b9  lea     ecx, [esp+7A4h+var_410]
0x100996c0  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100996c5  test    eax, eax
0x100996c7  lea     ecx, [esp+7A0h+var_406]
0x100996ce  mov     eax, [esp+7A0h+var_794]
0x100996d2  lea     esi, [esp+7A0h+var_410]
0x100996d9  cmovz   esi, ecx
0x100996dc  mov     ecx, [eax]
0x100996de  mov     ecx, [ecx]
0x100996e0  call    PconnOfHdbc
0x100996e5  mov     ecx, [eax+4]
0x100996e8  mov     eax, [ebp+arg_14]
0x100996eb  bt      eax, 1Dh
0x100996ef  jnb     short loc_100996FE
0x100996f1  test    cl, 8
0x100996f4  jz      short loc_100996FE
0x100996f6  and     eax, 0DFFFFFFFh
0x100996fb  mov     [ebp+arg_14], eax
0x100996fe  bt      eax, 1Dh
0x10099702  jb      short loc_1009971C
0x10099704  mov     edx, offset SubStr; "UID="
0x10099709  mov     ecx, esi
0x1009970b  call    _RemoveField@8; RemoveField(x,x)
0x10099710  mov     edx, offset _wszPwdEq; "PWD="
0x10099715  mov     ecx, esi
0x10099717  call    _RemoveField@8; RemoveField(x,x)
0x1009971c  mov     ecx, esi
0x1009971e  lea     edx, [ecx+2]
0x10099721  mov     ax, [ecx]
0x10099724  add     ecx, 2
0x10099727  cmp     ax, word ptr [esp+7A0h+var_788]
0x1009972c  jnz     short loc_10099721
0x1009972e  sub     ecx, edx
0x10099730  mov     edx, ebx
0x10099732  sar     ecx, 1
0x10099734  lea     eax, [ecx+ecx]
0x10099737  mov     ecx, edi
0x10099739  push    eax
0x1009973a  push    esi
0x1009973b  push    offset _wszSoConnectColumn; "Connect"
0x10099740  call    _ErrSetSysField@20; ErrSetSysField(x,x,x,x,x)
0x10099745  mov     esi, eax
0x10099747  test    esi, esi
0x10099749  js      loc_100994AD
0x1009974f  lea     ecx, [esp+7A0h+Str]
0x10099756  xor     esi, esi
0x10099758  lea     edx, [ecx+2]
0x1009975b  mov     ax, [ecx]
0x1009975e  add     ecx, 2
0x10099761  cmp     ax, si
0x10099764  jnz     short loc_1009975B
0x10099766  sub     ecx, edx
0x10099768  mov     edx, ebx
0x1009976a  sar     ecx, 1
0x1009976c  lea     eax, [ecx+ecx]
0x1009976f  mov     ecx, edi
0x10099771  push    eax
0x10099772  lea     eax, [esp+7A4h+Str]
0x10099779  push    eax
0x1009977a  push    offset _wszSoForeignNameColumn; "ForeignName"
0x1009977f  call    _ErrSetSysField@20; ErrSetSysField(x,x,x,x,x)
  ... truncated ...
```
