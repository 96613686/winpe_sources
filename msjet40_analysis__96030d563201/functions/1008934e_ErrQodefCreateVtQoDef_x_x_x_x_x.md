# ErrQodefCreateVtQoDef(x,x,x,x,x)

- ea: `0x1008934e`
- end: `0x100897f6`
- name: `_ErrQodefCreateVtQoDef@20`
- size: `1192`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1008b960`

## callees

- `0x1002a670`
- `0x100364a0`
- `0x10042b90`
- `0x10043090`
- `0x10043660`
- `0x10043840`
- `0x10043da0`
- `0x10044b90`
- `0x10044c00`
- `0x10044e00`
- `0x10044f50`
- `0x100451a0`
- `0x10045320`
- `0x10088599`
- `0x100891ee`
- `0x1008934e`
- `0x1008a9f8`
- `0x1008aa70`
- `0x1008b7ad`
- `0x1008b833`
- `0x100c9832`
- `0x100c9899`
- `0x100c990a`
- `0x10116991`
- `0x10122f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100894d2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x100894d2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10089497`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10089497`

## pseudocode

```c
int __fastcall ErrQodefCreateVtQoDef(Session *a1, int a2, _WORD *a3, _DWORD *a4, int a5)
{
  Session *v5; // edi
  int result; // eax
  int Object; // esi
  _DWORD *v8; // ebx
  int v9; // eax
  int v10; // eax
  Session *v11; // eax
  int *v12; // edx
  int v13; // eax
  int *i; // ecx
  int v15; // eax
  void *v16; // eax
  __int16 v17; // ax
  int v18; // ecx
  bool v19; // zf
  int v20; // [esp+0h] [ebp-ACh]
  Session *v21; // [esp+Ch] [ebp-A0h] BYREF
  _DWORD *v22; // [esp+10h] [ebp-9Ch]
  _WORD *v23; // [esp+14h] [ebp-98h]
  int v24; // [esp+18h] [ebp-94h] BYREF
  int v25; // [esp+1Ch] [ebp-90h]
  int v26; // [esp+20h] [ebp-8Ch] BYREF
  __int16 v27[3]; // [esp+24h] [ebp-88h] BYREF
  char v28; // [esp+2Bh] [ebp-81h] BYREF
  Session *v29; // [esp+2Ch] [ebp-80h]
  int v30[29]; // [esp+30h] [ebp-7Ch] BYREF

  v5 = a1;
  v23 = a3;
  v25 = a2;
  v29 = a1;
  v22 = a4;
  result = ErrAllocateTableidForVSesid(a1, a4, 0, 0);
  if ( result >= 0 )
  {
    Object = ErrQodefAllocQodefvt(&v26);
    if ( Object < 0 )
    {
LABEL_54:
      ReleaseTableid(*v22);
      return Object;
    }
    v8 = (_DWORD *)v26;
    v9 = v25;
    *(_DWORD *)v26 = v5;
    v8[1] = v9;
    v8[22] = 0;
    v8[23] = a5;
    v8[24] = a5;
    Object = ErrQjetBeginTransaction(v5, 0);
    if ( Object < 0 )
    {
LABEL_53:
      QodefReleaseQodefvt(v20);
      goto LABEL_54;
    }
    if ( v23 && *v23 )
    {
      v10 = 0;
      v26 = 0;
    }
    else
    {
      v10 = 1;
      v26 = 1;
    }
    if ( v10 )
    {
      qmemcpy(v30, rgsinfoTempQo, 0x70u);
      v5 = v29;
      Object = ErrOldOpenTempTable((int)v29, 7, (int)v30, 0, 13);
      if ( Object < 0 )
        goto LABEL_52;
      v11 = v21;
      v8[4] = v21;
      v29 = v11;
      v12 = &v30[8];
      v13 = v30[7];
      v8[2] = 0;
      v8[7] = v13;
      v8[8] = v30[3];
      for ( i = v8 + 9; i < v8 + 14; ++i )
      {
        v15 = v12[3];
        v12 += 4;
        *i = v15;
      }
    }
    else
    {
      Object = ErrDispCreateObject(v5, v25, 251658241, v23, 5);
      if ( Object < 0 )
        goto LABEL_52;
      v16 = _malloc(8u);
      v8[2] = v16;
      if ( !v16 )
        goto LABEL_52;
      Object = ErrGetObjInfoId(5, v23, v16, v8 + 20);
      if ( Object < 0 )
      {
        if ( v8[2] )
          _free((void *)v8[2]);
        v8[2] = 0;
        goto LABEL_52;
      }
      *(_DWORD *)(v8[2] + 4) = 1;
      Object = ErrDispOpenTable(v5, v25, v8 + 4, L"MSysQueries", 0x80000000);
      if ( Object < 0 )
      {
        SetLockErrorInfo(L"MSysQueries");
LABEL_51:
        CloseSysObjCursor(v5, v8 + 2);
        goto LABEL_52;
      }
      v29 = (Session *)v8[4];
      Object = ErrQodefGetColumnidsSq(v8);
      if ( Object < 0 )
        goto LABEL_50;
      Object = ErrDispSetCurrentIndex(v5, v29, L"ObjectIdAttribute");
      if ( Object < 0 )
        goto LABEL_50;
    }
    Object = ErrDispPrepareUpdate2(v5, v29, 0);
    if ( Object < 0 || !v26 && (Object = ErrDispSetColumn(v5, v29, v8[6], v8 + 20, 4, 0, 0), Object < 0) )
    {
LABEL_50:
      ErrDispCloseTable(v5, v29);
      if ( !v26 )
        goto LABEL_51;
LABEL_52:
      ErrQjetRollback(v5, 0);
      goto LABEL_53;
    }
    v28 = 0;
    if ( (a5 & 0x10000000) != 0 )
    {
      v17 = 1;
    }
    else
    {
      if ( (a5 & 0x8000000) != 0 )
      {
        v27[0] = 2;
        goto LABEL_33;
      }
      v17 = 0;
    }
    v27[0] = v17;
LABEL_33:
    Object = ErrDispSetColumn(v5, v29, v8[8], &v28, 1, 0, 0);
    if ( Object >= 0 )
    {
      Object = ErrDispSetColumn(v5, v29, v8[12], v27, 2, 0, 0);
      if ( Object >= 0 )
      {
        Object = ErrDispSetColumn(v5, v29, v8[7], &dword_1000BFD4, 4, 0, 0);
        if ( Object >= 0 )
        {
          Object = ErrDispUpdate(v5, v29, 0, 0, 0);
          if ( Object >= 0 )
          {
            Object = ErrDispPrepareUpdate2(v5, v29, 0);
            if ( Object >= 0 )
            {
              if ( v26 || (Object = ErrDispSetColumn(v5, v29, v8[6], v8 + 20, 4, 0, 0), Object >= 0) )
              {
                v28 = -1;
                Object = ErrDispSetColumn(v5, v29, v8[8], &v28, 1, 0, 0);
                if ( Object >= 0 )
                {
                  Object = ErrDispSetColumn(v5, v29, v8[7], &dword_1000BFD4, 4, 0, 0);
                  if ( Object >= 0 )
                  {
                    Object = ErrDispUpdate(v5, v29, 0, 0, 0);
                    if ( Object >= 0 )
                    {
                      Object = ErrQodefSeekSq(0, &dword_1000BFD4, v18, 1, 0);
                      if ( Object >= 0 )
                      {
                        Object = ErrREPOpenQuery(v23, *v22, &v21);
                        if ( Object >= 0 )
                        {
                          ErrUpdateTableid(*v22, v8, &vtfndefQodef);
                          Object = ErrDispDupCursor(*v8, v8[4], &v24, 0);
                          if ( Object >= 0 )
                          {
                            v19 = v26 == 0;
                            v8[5] = v24;
                            if ( !v19 || (Object = ErrDispSetCurrentIndex(*v8, v24, L"ObjectIdAttribute"), Object >= 0) )
                            {
                              Object = ErrQjetCommitTransaction(0);
                              if ( Object >= 0 )
                                return 0;
                            }
                            ErrDispCloseTable(v5, v24);
                            v24 = -1;
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
    goto LABEL_50;
  }
  return result;
}

```

## disassembly

```asm
0x1008934e  mov     edi, edi
0x10089350  push    ebp
0x10089351  mov     ebp, esp
0x10089353  sub     esp, 0A0h
0x10089359  mov     eax, ___security_cookie
0x1008935e  xor     eax, ebp
0x10089360  mov     [ebp+var_8], eax
0x10089363  mov     eax, [ebp+arg_0]
0x10089366  push    ebx
0x10089367  push    esi
0x10089368  push    edi
0x10089369  mov     edi, ecx
0x1008936b  mov     [ebp+var_98], eax
0x10089371  mov     eax, [ebp+arg_4]
0x10089374  xor     ecx, ecx
0x10089376  push    ecx
0x10089377  push    ecx
0x10089378  push    eax
0x10089379  push    edi
0x1008937a  mov     [ebp+var_90], edx
0x10089380  mov     [ebp+var_80], edi
0x10089383  mov     [ebp+var_9C], eax
0x10089389  call    _ErrAllocateTableidForVSesid@16; ErrAllocateTableidForVSesid(x,x,x,x)
0x1008938e  test    eax, eax
0x10089390  js      loc_100897E1
0x10089396  lea     ecx, [ebp+var_8C]
0x1008939c  call    _ErrQodefAllocQodefvt@4; ErrQodefAllocQodefvt(x)
0x100893a1  mov     esi, eax
0x100893a3  test    esi, esi
0x100893a5  js      loc_100897D2
0x100893ab  mov     ebx, [ebp+var_8C]
0x100893b1  xor     edx, edx
0x100893b3  mov     eax, [ebp+var_90]
0x100893b9  mov     ecx, edi
0x100893bb  mov     [ebx], edi
0x100893bd  mov     [ebx+4], eax
0x100893c0  mov     eax, [ebp+arg_8]
0x100893c3  mov     dword ptr [ebx+58h], 0
0x100893ca  mov     [ebx+5Ch], eax
0x100893cd  mov     [ebx+60h], eax
0x100893d0  call    _ErrQjetBeginTransaction@8; ErrQjetBeginTransaction(x,x)
0x100893d5  mov     esi, eax
0x100893d7  test    esi, esi
0x100893d9  js      loc_100897CB
0x100893df  mov     ecx, [ebp+var_98]
0x100893e5  xor     edx, edx
0x100893e7  test    ecx, ecx
0x100893e9  jz      short loc_100893FA
0x100893eb  cmp     [ecx], dx
0x100893ee  jz      short loc_100893FA
0x100893f0  mov     eax, edx
0x100893f2  mov     [ebp+var_8C], edx
0x100893f8  jmp     short loc_10089403
0x100893fa  xor     eax, eax
0x100893fc  inc     eax
0x100893fd  mov     [ebp+var_8C], eax
0x10089403  test    eax, eax
0x10089405  jz      short loc_10089477
0x10089407  push    1Ch
0x10089409  pop     ecx
0x1008940a  push    0Dh; int
0x1008940c  push    edx; int
0x1008940d  mov     esi, offset _rgsinfoTempQo
0x10089412  lea     edi, [ebp+var_7C]
0x10089415  rep movsd
0x10089417  mov     edi, [ebp+var_80]
0x1008941a  lea     eax, [ebp+var_7C]
0x1008941d  push    eax; int
0x1008941e  push    7; int
0x10089420  lea     edx, [ebp+var_A0]
0x10089426  mov     ecx, edi; int
0x10089428  call    _ErrOldOpenTempTable@24; ErrOldOpenTempTable(x,x,x,x,x,x)
0x1008942d  mov     esi, eax
0x1008942f  test    esi, esi
0x10089431  js      loc_100897C2
0x10089437  mov     eax, [ebp+var_A0]
0x1008943d  lea     ecx, [ebx+1Ch]
0x10089440  mov     [ebx+10h], eax
0x10089443  lea     esi, [ecx+1Ch]
0x10089446  mov     [ebp+var_80], eax
0x10089449  lea     edx, [ebp+var_5C]
0x1008944c  mov     eax, [ebp+var_60]
0x1008944f  mov     dword ptr [ebx+8], 0
0x10089456  mov     [ecx], eax
0x10089458  mov     eax, [ebp+var_70]
0x1008945b  mov     [ecx+4], eax
0x1008945e  add     ecx, 8
0x10089461  jmp     short loc_1008946E
0x10089463  mov     eax, [edx+0Ch]
0x10089466  lea     edx, [edx+10h]
0x10089469  mov     [ecx], eax
0x1008946b  add     ecx, 4
0x1008946e  cmp     ecx, esi
0x10089470  jb      short loc_10089463
0x10089472  jmp     loc_10089551
0x10089477  push    5
0x10089479  push    ecx
0x1008947a  push    0F000001h
0x1008947f  push    [ebp+var_90]
0x10089485  push    edi
0x10089486  call    _ErrDispCreateObject@20; ErrDispCreateObject(x,x,x,x,x)
0x1008948b  mov     esi, eax
0x1008948d  test    esi, esi
0x1008948f  js      loc_100897C2
0x10089495  push    8; Size
0x10089497  call    ds:__imp__malloc
0x1008949d  mov     [ebx+8], eax
0x100894a0  pop     ecx
0x100894a1  test    eax, eax
0x100894a3  jz      loc_100897C2
0x100894a9  mov     edx, [ebp+var_90]
0x100894af  lea     ecx, [ebx+50h]
0x100894b2  push    ecx
0x100894b3  push    eax
0x100894b4  push    [ebp+var_98]
0x100894ba  mov     ecx, edi
0x100894bc  push    5
0x100894be  call    _ErrGetObjInfoId@24; ErrGetObjInfoId(x,x,x,x,x,x)
0x100894c3  mov     esi, eax
0x100894c5  test    esi, esi
0x100894c7  jns     short loc_100894E5
0x100894c9  cmp     dword ptr [ebx+8], 0
0x100894cd  jz      short loc_100894D9
0x100894cf  push    dword ptr [ebx+8]; Block
0x100894d2  call    ds:__imp__free
0x100894d8  pop     ecx
0x100894d9  mov     dword ptr [ebx+8], 0
0x100894e0  jmp     loc_100897C2
0x100894e5  mov     eax, [ebx+8]
0x100894e8  push    80000000h
0x100894ed  push    offset _wszSqTable; "MSysQueries"
0x100894f2  mov     dword ptr [eax+4], 1
0x100894f9  lea     eax, [ebx+10h]
0x100894fc  push    eax
0x100894fd  push    [ebp+var_90]
0x10089503  push    edi
0x10089504  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10089509  mov     esi, eax
0x1008950b  test    esi, esi
0x1008950d  jns     short loc_10089522
0x1008950f  push    offset _wszSqTable; "MSysQueries"
0x10089514  mov     edx, esi
0x10089516  mov     ecx, edi
0x10089518  call    _SetLockErrorInfo@12; SetLockErrorInfo(x,x,x)
0x1008951d  jmp     loc_100897B8
0x10089522  mov     eax, [ebx+10h]
0x10089525  mov     ecx, ebx
0x10089527  mov     [ebp+var_80], eax
0x1008952a  call    _ErrQodefGetColumnidsSq@4; ErrQodefGetColumnidsSq(x)
0x1008952f  mov     esi, eax
0x10089531  test    esi, esi
0x10089533  js      loc_100897A6
0x10089539  push    offset _wszSqAttributeIndex; "ObjectIdAttribute"
0x1008953e  push    [ebp+var_80]
0x10089541  push    edi
0x10089542  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x10089547  mov     esi, eax
0x10089549  test    esi, esi
0x1008954b  js      loc_100897A6
0x10089551  push    0
0x10089553  push    [ebp+var_80]
0x10089556  push    edi
0x10089557  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x1008955c  mov     esi, eax
0x1008955e  test    esi, esi
0x10089560  js      loc_100897A6
0x10089566  cmp     [ebp+var_8C], 0
0x1008956d  jnz     short loc_1008958F
0x1008956f  xor     eax, eax
0x10089571  push    eax
0x10089572  push    eax
0x10089573  push    4
0x10089575  lea     eax, [ebx+50h]
0x10089578  push    eax
0x10089579  push    dword ptr [ebx+18h]
0x1008957c  push    [ebp+var_80]
0x1008957f  push    edi
0x10089580  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x10089585  mov     esi, eax
0x10089587  test    esi, esi
0x10089589  js      loc_100897A6
0x1008958f  mov     eax, [ebp+arg_8]
0x10089592  xor     ecx, ecx
0x10089594  mov     [ebp+var_81], cl
0x1008959a  push    2
0x1008959c  pop     edx
0x1008959d  test    eax, 10000000h
0x100895a2  jz      short loc_100895A9
0x100895a4  xor     eax, eax
0x100895a6  inc     eax
0x100895a7  jmp     short loc_100895BB
0x100895a9  test    eax, 8000000h
0x100895ae  jz      short loc_100895B9
0x100895b0  mov     [ebp+var_88], dx
0x100895b7  jmp     short loc_100895C2
0x100895b9  xor     eax, eax
0x100895bb  mov     [ebp+var_88], ax
0x100895c2  push    ecx
0x100895c3  push    ecx
0x100895c4  push    1
0x100895c6  lea     eax, [ebp+var_81]
0x100895cc  push    eax
0x100895cd  push    dword ptr [ebx+20h]
0x100895d0  push    [ebp+var_80]
0x100895d3  push    edi
0x100895d4  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100895d9  mov     esi, eax
0x100895db  test    esi, esi
0x100895dd  js      loc_100897A6
0x100895e3  xor     eax, eax
0x100895e5  push    eax
0x100895e6  push    eax
0x100895e7  push    2
0x100895e9  lea     eax, [ebp+var_88]
0x100895ef  push    eax
0x100895f0  push    dword ptr [ebx+30h]
0x100895f3  push    [ebp+var_80]
0x100895f6  push    edi
0x100895f7  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100895fc  mov     esi, eax
0x100895fe  test    esi, esi
0x10089600  js      loc_100897A6
0x10089606  xor     eax, eax
0x10089608  push    eax
0x10089609  push    eax
0x1008960a  push    4
0x1008960c  push    offset dword_1000BFD4
0x10089611  push    dword ptr [ebx+1Ch]
0x10089614  push    [ebp+var_80]
0x10089617  push    edi
0x10089618  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x1008961d  mov     esi, eax
0x1008961f  test    esi, esi
0x10089621  js      loc_100897A6
0x10089627  xor     eax, eax
0x10089629  push    eax
0x1008962a  push    eax
0x1008962b  push    eax
0x1008962c  push    [ebp+var_80]
0x1008962f  push    edi
0x10089630  call    _ErrDispUpdate@20; ErrDispUpdate(x,x,x,x,x)
0x10089635  mov     esi, eax
0x10089637  test    esi, esi
0x10089639  js      loc_100897A6
0x1008963f  push    0
0x10089641  push    [ebp+var_80]
0x10089644  push    edi
0x10089645  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x1008964a  mov     esi, eax
0x1008964c  test    esi, esi
0x1008964e  js      loc_100897A6
0x10089654  cmp     [ebp+var_8C], 0
0x1008965b  jnz     short loc_1008967D
0x1008965d  xor     eax, eax
0x1008965f  push    eax
0x10089660  push    eax
0x10089661  push    4
0x10089663  lea     eax, [ebx+50h]
0x10089666  push    eax
0x10089667  push    dword ptr [ebx+18h]
0x1008966a  push    [ebp+var_80]
0x1008966d  push    edi
0x1008966e  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x10089673  mov     esi, eax
0x10089675  test    esi, esi
0x10089677  js      loc_100897A6
0x1008967d  xor     eax, eax
0x1008967f  mov     [ebp+var_81], 0FFh
0x10089686  push    eax
0x10089687  push    eax
0x10089688  push    1
0x1008968a  lea     eax, [ebp+var_81]
0x10089690  push    eax
0x10089691  push    dword ptr [ebx+20h]
0x10089694  push    [ebp+var_80]
0x10089697  push    edi
0x10089698  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x1008969d  mov     esi, eax
0x1008969f  test    esi, esi
0x100896a1  js      loc_100897A6
0x100896a7  xor     eax, eax
0x100896a9  push    eax
0x100896aa  push    eax
0x100896ab  push    4
0x100896ad  push    offset dword_1000BFD4
0x100896b2  push    dword ptr [ebx+1Ch]
0x100896b5  push    [ebp+var_80]
0x100896b8  push    edi
0x100896b9  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100896be  mov     esi, eax
0x100896c0  test    esi, esi
0x100896c2  js      loc_100897A6
0x100896c8  xor     eax, eax
0x100896ca  push    eax
0x100896cb  push    eax
0x100896cc  push    eax
0x100896cd  push    [ebp+var_80]
0x100896d0  push    edi
0x100896d1  call    _ErrDispUpdate@20; ErrDispUpdate(x,x,x,x,x)
0x100896d6  mov     esi, eax
  ... truncated ...
```
