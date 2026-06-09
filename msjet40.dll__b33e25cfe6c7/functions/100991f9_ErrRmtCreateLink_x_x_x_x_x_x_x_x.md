# ErrRmtCreateLink(x,x,x,x,x,x,x,x)

- ea: `0x100991f9`
- end: `0x100996b5`
- name: `_ErrRmtCreateLink@32`
- size: `1212`
- prototype: `int __fastcall(void *, int **, int, int, unsigned int, void *, int, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1002b0d0`
- `0x1002ce50`

## callees

- `0x100129b0`
- `0x10016ed0`
- `0x1001bc80`
- `0x1002a670`
- `0x1002a7f0`
- `0x10043540`
- `0x10043660`
- `0x10043840`
- `0x10044e00`
- `0x10095e7d`
- `0x100969cf`
- `0x10096ac8`
- `0x100972f1`
- `0x100991f9`
- `0x100996bb`
- `0x10099cda`
- `0x1009a875`
- `0x1009b7fe`
- `0x100c9832`
- `0x100c9899`
- `0x100c990a`
- `0x100d731b`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1009937d`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1009937d`

## pseudocode

```c
int __fastcall ErrRmtCreateLink(void *a1, int **a2, int a3, int a4, unsigned int a5, void *a6, int a7, int a8)
{
  int v8; // ebx
  char *v10; // ecx
  unsigned int v11; // esi
  __int16 v12; // ax
  char *v13; // ecx
  __int16 v14; // ax
  int result; // eax
  int v16; // eax
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
  int **v30; // [esp+Ch] [ebp-794h] BYREF
  char *v31; // [esp+10h] [ebp-790h] BYREF
  void *Src; // [esp+14h] [ebp-78Ch]
  int v33; // [esp+18h] [ebp-788h]
  int v34; // [esp+1Ch] [ebp-784h] BYREF
  int v35; // [esp+20h] [ebp-780h]
  int *v36; // [esp+24h] [ebp-77Ch]
  int v37; // [esp+28h] [ebp-778h] BYREF
  int v38; // [esp+2Ch] [ebp-774h]
  int **v39; // [esp+30h] [ebp-770h] BYREF
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
    v16 = JetCreateTable((int)a1, a5, Src, 4, 90, &v37);
    Timestamp = v16;
    if ( v16 == -1303 )
    {
      Timestamp = -1314;
    }
    else if ( v16 >= 0 )
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
      Timestamp = ErrRmtGetTimestamp(a1, (int)&v39);
      if ( Timestamp >= 0 )
      {
        Timestamp = ErrRmtMirrorColumns(&v39, Src, a5);
        if ( Timestamp >= 0 )
        {
          Timestamp = ErrRmtMirrorStatistics(a1, v36, &v39);
          if ( Timestamp >= 0 )
          {
            Timestamp = ErrRmtGetCapabilities((int)a1, v30, (int)v49);
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
    ErrQjetRollback((Session *)a1, 0);
    return Timestamp;
  }
  return result;
}

```

## disassembly

```asm
0x100991f9  mov     edi, edi
0x100991fb  push    ebp
0x100991fc  mov     ebp, esp
0x100991fe  and     esp, 0FFFFFFF8h
0x10099201  sub     esp, 794h
0x10099207  mov     eax, ___security_cookie
0x1009920c  xor     eax, esp
0x1009920e  mov     [esp+794h+var_4], eax
0x10099215  mov     eax, [ebp+arg_4]
0x10099218  mov     [esp+794h+var_780], eax
0x1009921c  mov     eax, [ebp+arg_C]
0x1009921f  mov     [esp+794h+Src], eax
0x10099223  mov     eax, [ebp+arg_10]
0x10099226  push    ebx
0x10099227  mov     [esp+798h+var_774], eax
0x1009922b  or      ebx, 0FFFFFFFFh
0x1009922e  xor     eax, eax
0x10099230  mov     [esp+798h+var_794], edx
0x10099234  push    esi
0x10099235  push    edi
0x10099236  mov     [esp+7A0h+var_788], eax
0x1009923a  mov     edi, ecx
0x1009923c  mov     [esp+7A0h+var_6C8], eax
0x10099243  lea     eax, [esp+7A0h+var_794]
0x10099247  push    eax
0x10099248  mov     [esp+7A4h+var_784], ebx
0x1009924c  mov     [esp+7A4h+var_760], 0FFFFFFFFh
0x10099254  call    _ErrVdbidOfDbid@12; ErrVdbidOfDbid(x,x,x)
0x10099259  mov     edx, [esp+7A0h+var_794]
0x1009925d  mov     ecx, [esp+7A0h+var_780]
0x10099261  mov     esi, [ebp+arg_14]
0x10099264  and     esi, 0BFFFFFFFh
0x1009926a  mov     eax, [edx+274h]
0x10099270  mov     [esp+7A0h+var_77C], eax
0x10099274  lea     eax, [ecx+2]
0x10099277  mov     [ebp+arg_14], esi
0x1009927a  mov     [esp+7A0h+var_790], eax
0x1009927e  mov     ax, [ecx]
0x10099281  add     ecx, 2
0x10099284  cmp     ax, word ptr [esp+7A0h+var_788]
0x10099289  jnz     short loc_1009927E
0x1009928b  sub     ecx, [esp+7A0h+var_790]
0x1009928f  sar     ecx, 1
0x10099291  jz      loc_10099699
0x10099297  mov     ecx, [esp+7A0h+Src]
0x1009929b  lea     eax, [ecx+2]
0x1009929e  mov     [esp+7A0h+var_790], eax
0x100992a2  mov     ax, [ecx]
0x100992a5  add     ecx, 2
0x100992a8  cmp     ax, word ptr [esp+7A0h+var_788]
0x100992ad  jnz     short loc_100992A2
0x100992af  sub     ecx, [esp+7A0h+var_790]
0x100992b3  sar     ecx, 1
0x100992b5  jz      loc_10099699
0x100992bb  test    esi, 0DFFFFFFFh
0x100992c1  jnz     loc_10099699
0x100992c7  mov     edx, [edx]
0x100992c9  cmp     dword ptr [edx], 0
0x100992cc  jnz     short loc_100992E0
0x100992ce  mov     ecx, edi
0x100992d0  call    _ErrReviveConn@8; ErrReviveConn(x,x)
0x100992d5  test    eax, eax
0x100992d7  js      loc_1009969E
0x100992dd  mov     esi, [ebp+arg_14]
0x100992e0  or      esi, 100000h
0x100992e6  xor     edx, edx
0x100992e8  mov     ecx, edi
0x100992ea  mov     [ebp+arg_14], esi
0x100992ed  call    _ErrQjetBeginTransaction@8; ErrQjetBeginTransaction(x,x)
0x100992f2  test    eax, eax
0x100992f4  js      loc_1009969E
0x100992fa  lea     eax, [esp+7A0h+var_778]
0x100992fe  push    eax; int
0x100992ff  push    5Ah ; 'Z'; int
0x10099301  push    4; int
0x10099303  push    [esp+7ACh+Src]; Src
0x10099307  push    [ebp+arg_8]; int
0x1009930a  push    edi; int
0x1009930b  call    _JetCreateTable@24; JetCreateTable(x,x,x,x,x,x)
0x10099310  mov     esi, eax
0x10099312  cmp     esi, 0FFFFFAE9h
0x10099318  jnz     short loc_10099352
0x1009931a  add     esi, 0FFFFFFF5h
0x1009931d  cmp     [esp+7A0h+var_760], 0FFFFFFFFh
0x10099322  jz      short loc_10099336
0x10099324  push    [esp+7A0h+var_760]
0x10099328  push    edi
0x10099329  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x1009932e  mov     [esp+7A0h+var_760], 0FFFFFFFFh
0x10099336  cmp     ebx, 0FFFFFFFFh
0x10099339  jz      short loc_10099342
0x1009933b  push    ebx
0x1009933c  push    edi
0x1009933d  call    _ErrDispCloseTable@8; ErrDispCloseTable(x,x)
0x10099342  push    0; int
0x10099344  mov     ecx, edi; Session *
0x10099346  call    _ErrQjetRollback@12; ErrQjetRollback(x,x,x)
0x1009934b  mov     eax, esi
0x1009934d  jmp     loc_1009969E
0x10099352  test    esi, esi
0x10099354  js      short loc_1009931D
0x10099356  mov     eax, [esp+7A0h+var_778]
0x1009935a  lea     ecx, [esp+7A0h+Str]
0x10099361  mov     edx, [esp+7A0h+var_780]
0x10099365  push    100h
0x1009936a  mov     [esp+7A4h+var_760], eax
0x1009936e  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10099373  lea     eax, [esp+7A0h+Str]
0x1009937a  push    2Eh ; '.'; Ch
0x1009937c  push    eax; Str
0x1009937d  call    ds:__imp__wcschr
0x10099383  pop     ecx
0x10099384  pop     ecx
0x10099385  test    eax, eax
0x10099387  jz      short loc_100993AF
0x10099389  lea     ecx, [esp+7A0h+Str]
0x10099390  mov     [esp+7A0h+var_768], ecx
0x10099394  lea     edx, [esp+7A0h+Str]
0x1009939b  mov     ecx, eax
0x1009939d  sub     ecx, edx
0x1009939f  sar     ecx, 1
0x100993a1  add     eax, 2
0x100993a4  mov     [esp+7A0h+var_764], cx
0x100993a9  mov     [esp+7A0h+var_76C], eax
0x100993ad  jmp     short loc_100993C9
0x100993af  lea     eax, [esp+7A0h+Str]
0x100993b6  mov     [esp+7A0h+var_768], 0
0x100993be  mov     [esp+7A0h+var_76C], eax
0x100993c2  xor     eax, eax
0x100993c4  mov     [esp+7A0h+var_764], ax
0x100993c9  mov     eax, [esp+7A0h+var_794]
0x100993cd  mov     ecx, edi
0x100993cf  mov     [esp+7A0h+var_770], eax
0x100993d3  lea     eax, [esp+7A0h+var_770]
0x100993d7  push    eax
0x100993d8  call    ErrRmtGetTimestamp
0x100993dd  mov     esi, eax
0x100993df  test    esi, esi
0x100993e1  js      loc_1009931D
0x100993e7  push    [ebp+arg_8]
0x100993ea  mov     edx, [esp+7A4h+var_77C]
0x100993ee  lea     eax, [esp+7A4h+var_770]
0x100993f2  push    [esp+7A4h+Src]
0x100993f6  mov     ecx, edi
0x100993f8  push    eax
0x100993f9  call    ErrRmtMirrorColumns
0x100993fe  mov     esi, eax
0x10099400  test    esi, esi
0x10099402  js      loc_1009931D
0x10099408  mov     edx, [esp+7A0h+var_77C]
0x1009940c  lea     eax, [esp+7A0h+var_770]
0x10099410  push    eax
0x10099411  mov     ecx, edi
0x10099413  call    ErrRmtMirrorStatistics
0x10099418  mov     esi, eax
0x1009941a  test    esi, esi
0x1009941c  js      loc_1009931D
0x10099422  mov     edx, [esp+7A0h+var_794]
0x10099426  lea     eax, [esp+7A0h+var_644]
0x1009942d  push    eax
0x1009942e  mov     ecx, edi
0x10099430  call    _ErrRmtGetCapabilities@12; ErrRmtGetCapabilities(x,x,x)
0x10099435  mov     esi, eax
0x10099437  test    esi, esi
0x10099439  js      loc_1009931D
0x1009943f  mov     edx, [ebp+arg_8]
0x10099442  lea     eax, [esp+7A0h+var_784]
0x10099446  push    0
0x10099448  push    eax
0x10099449  push    [esp+7A8h+Src]
0x1009944d  mov     ecx, edi
0x1009944f  push    1
0x10099451  call    _ErrGetObjInfoId@24; ErrGetObjInfoId(x,x,x,x,x,x)
0x10099456  mov     ebx, [esp+7A0h+var_784]
0x1009945a  mov     esi, eax
0x1009945c  test    esi, esi
0x1009945e  js      loc_1009931D
0x10099464  push    2
0x10099466  push    ebx
0x10099467  push    edi
0x10099468  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x1009946d  mov     esi, eax
0x1009946f  test    esi, esi
0x10099471  js      loc_1009931D
0x10099477  push    ecx
0x10099478  xor     ecx, ecx
0x1009947a  lea     eax, [esp+7A4h+var_644]
0x10099481  cmp     [esp+7A4h+var_6CC], ecx
0x10099488  mov     edx, ebx
0x1009948a  push    eax
0x1009948b  lea     eax, [esp+7A8h+var_754]
0x1009948f  cmovnz  eax, ecx
0x10099492  mov     ecx, edi
0x10099494  push    eax
0x10099495  push    [esp+7ACh+var_758]
0x10099499  push    [esp+7B0h+var_75C]
0x1009949d  call    _ErrRMTSetSoInfo@28; ErrRMTSetSoInfo(x,x,x,x,x,x,x)
0x100994a2  mov     esi, eax
0x100994a4  test    esi, esi
0x100994a6  js      loc_1009931D
0x100994ac  mov     ecx, [esp+7A0h+var_794]
0x100994b0  mov     edx, ebx
0x100994b2  movsx   eax, word ptr [ecx+10h]
0x100994b6  imul    eax, 6
0x100994b9  push    eax
0x100994ba  push    dword ptr [ecx+0Ch]
0x100994bd  mov     ecx, edi
0x100994bf  push    offset _wszSoRmtInfoLong; "RmtInfoLong"
0x100994c4  call    _ErrSetSysField@20; ErrSetSysField(x,x,x,x,x)
0x100994c9  mov     esi, eax
0x100994cb  test    esi, esi
0x100994cd  js      loc_1009931D
0x100994d3  mov     esi, [esp+7A0h+var_774]
0x100994d7  test    esi, esi
0x100994d9  jz      short loc_10099508
0x100994db  push    5
0x100994dd  mov     edx, offset _wszODBC; "ODBC;"
0x100994e2  mov     ecx, esi
0x100994e4  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x100994e9  test    eax, eax
0x100994eb  jnz     short loc_1009950F
0x100994ed  mov     ecx, esi
0x100994ef  lea     edx, [ecx+2]
0x100994f2  mov     ax, [ecx]
0x100994f5  add     ecx, 2
0x100994f8  cmp     ax, word ptr [esp+7A0h+var_788]
0x100994fd  jnz     short loc_100994F2
0x100994ff  sub     ecx, edx
0x10099501  sar     ecx, 1
0x10099503  cmp     ecx, 5
0x10099506  jnz     short loc_1009950F
0x10099508  mov     eax, [esp+7A0h+var_794]
0x1009950c  mov     esi, [eax+4]
0x1009950f  push    201h
0x10099514  mov     edx, esi
0x10099516  lea     ecx, [esp+7A4h+var_410]
0x1009951d  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10099522  push    5
0x10099524  mov     edx, offset _wszODBC; "ODBC;"
0x10099529  lea     ecx, [esp+7A4h+var_410]
0x10099530  call    _WCSNICMP@12; WCSNICMP(x,x,x)
0x10099535  test    eax, eax
0x10099537  lea     ecx, [esp+7A0h+var_406]
0x1009953e  mov     eax, [esp+7A0h+var_794]
0x10099542  lea     esi, [esp+7A0h+var_410]
0x10099549  cmovz   esi, ecx
0x1009954c  mov     ecx, [eax]
0x1009954e  mov     ecx, [ecx]
0x10099550  call    PconnOfHdbc
0x10099555  mov     ecx, [eax+4]
0x10099558  mov     eax, [ebp+arg_14]
0x1009955b  bt      eax, 1Dh
0x1009955f  jnb     short loc_1009956E
0x10099561  test    cl, 8
0x10099564  jz      short loc_1009956E
0x10099566  and     eax, 0DFFFFFFFh
0x1009956b  mov     [ebp+arg_14], eax
0x1009956e  bt      eax, 1Dh
0x10099572  jb      short loc_1009958C
0x10099574  mov     edx, offset SubStr; "UID="
0x10099579  mov     ecx, esi
0x1009957b  call    _RemoveField@8; RemoveField(x,x)
0x10099580  mov     edx, offset _wszPwdEq; "PWD="
0x10099585  mov     ecx, esi
0x10099587  call    _RemoveField@8; RemoveField(x,x)
0x1009958c  mov     ecx, esi
0x1009958e  lea     edx, [ecx+2]
0x10099591  mov     ax, [ecx]
0x10099594  add     ecx, 2
0x10099597  cmp     ax, word ptr [esp+7A0h+var_788]
0x1009959c  jnz     short loc_10099591
0x1009959e  sub     ecx, edx
0x100995a0  mov     edx, ebx
0x100995a2  sar     ecx, 1
0x100995a4  lea     eax, [ecx+ecx]
0x100995a7  mov     ecx, edi
0x100995a9  push    eax
0x100995aa  push    esi
0x100995ab  push    offset _wszSoConnectColumn; "Connect"
0x100995b0  call    _ErrSetSysField@20; ErrSetSysField(x,x,x,x,x)
0x100995b5  mov     esi, eax
0x100995b7  test    esi, esi
0x100995b9  js      loc_1009931D
0x100995bf  lea     ecx, [esp+7A0h+Str]
0x100995c6  xor     esi, esi
0x100995c8  lea     edx, [ecx+2]
0x100995cb  mov     ax, [ecx]
0x100995ce  add     ecx, 2
0x100995d1  cmp     ax, si
0x100995d4  jnz     short loc_100995CB
0x100995d6  sub     ecx, edx
0x100995d8  mov     edx, ebx
0x100995da  sar     ecx, 1
0x100995dc  lea     eax, [ecx+ecx]
0x100995df  mov     ecx, edi
0x100995e1  push    eax
0x100995e2  lea     eax, [esp+7A4h+Str]
0x100995e9  push    eax
0x100995ea  push    offset _wszSoForeignNameColumn; "ForeignName"
0x100995ef  call    _ErrSetSysField@20; ErrSetSysField(x,x,x,x,x)
  ... truncated ...
```
