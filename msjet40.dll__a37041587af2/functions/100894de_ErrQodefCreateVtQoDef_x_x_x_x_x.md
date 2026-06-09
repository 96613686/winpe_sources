# ErrQodefCreateVtQoDef(x,x,x,x,x)

- ea: `0x100894de`
- end: `0x10089986`
- name: `_ErrQodefCreateVtQoDef@20`
- size: `1192`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1008baf0`

## callees

- `0x1002a840`
- `0x10036630`
- `0x10042d20`
- `0x10043220`
- `0x100437f0`
- `0x100439d0`
- `0x10043f30`
- `0x10044d10`
- `0x10044d80`
- `0x10044f80`
- `0x100450d0`
- `0x10045320`
- `0x100454a0`
- `0x10088729`
- `0x1008937e`
- `0x100894de`
- `0x1008ab88`
- `0x1008ac00`
- `0x1008b93d`
- `0x1008b9c3`
- `0x100c99c2`
- `0x100c9a29`
- `0x100c9a9a`
- `0x10116b41`
- `0x10123110`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10089662`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x10089662`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10089627`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x10089627`

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
        Object = ErrDispSetColumn(v5, v29, v8[7], &dword_1000C084, 4, 0, 0);
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
                  Object = ErrDispSetColumn(v5, v29, v8[7], &dword_1000C084, 4, 0, 0);
                  if ( Object >= 0 )
                  {
                    Object = ErrDispUpdate(v5, v29, 0, 0, 0);
                    if ( Object >= 0 )
                    {
                      Object = ErrQodefSeekSq(0, &dword_1000C084, v18, 1, 0);
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
0x100894de  mov     edi, edi
0x100894e0  push    ebp
0x100894e1  mov     ebp, esp
0x100894e3  sub     esp, 0A0h
0x100894e9  mov     eax, ___security_cookie
0x100894ee  xor     eax, ebp
0x100894f0  mov     [ebp+var_8], eax
0x100894f3  mov     eax, [ebp+arg_0]
0x100894f6  push    ebx
0x100894f7  push    esi
0x100894f8  push    edi
0x100894f9  mov     edi, ecx
0x100894fb  mov     [ebp+var_98], eax
0x10089501  mov     eax, [ebp+arg_4]
0x10089504  xor     ecx, ecx
0x10089506  push    ecx
0x10089507  push    ecx
0x10089508  push    eax
0x10089509  push    edi
0x1008950a  mov     [ebp+var_90], edx
0x10089510  mov     [ebp+var_80], edi
0x10089513  mov     [ebp+var_9C], eax
0x10089519  call    _ErrAllocateTableidForVSesid@16; ErrAllocateTableidForVSesid(x,x,x,x)
0x1008951e  test    eax, eax
0x10089520  js      loc_10089971
0x10089526  lea     ecx, [ebp+var_8C]
0x1008952c  call    _ErrQodefAllocQodefvt@4; ErrQodefAllocQodefvt(x)
0x10089531  mov     esi, eax
0x10089533  test    esi, esi
0x10089535  js      loc_10089962
0x1008953b  mov     ebx, [ebp+var_8C]
0x10089541  xor     edx, edx
0x10089543  mov     eax, [ebp+var_90]
0x10089549  mov     ecx, edi
0x1008954b  mov     [ebx], edi
0x1008954d  mov     [ebx+4], eax
0x10089550  mov     eax, [ebp+arg_8]
0x10089553  mov     dword ptr [ebx+58h], 0
0x1008955a  mov     [ebx+5Ch], eax
0x1008955d  mov     [ebx+60h], eax
0x10089560  call    _ErrQjetBeginTransaction@8; ErrQjetBeginTransaction(x,x)
0x10089565  mov     esi, eax
0x10089567  test    esi, esi
0x10089569  js      loc_1008995B
0x1008956f  mov     ecx, [ebp+var_98]
0x10089575  xor     edx, edx
0x10089577  test    ecx, ecx
0x10089579  jz      short loc_1008958A
0x1008957b  cmp     [ecx], dx
0x1008957e  jz      short loc_1008958A
0x10089580  mov     eax, edx
0x10089582  mov     [ebp+var_8C], edx
0x10089588  jmp     short loc_10089593
0x1008958a  xor     eax, eax
0x1008958c  inc     eax
0x1008958d  mov     [ebp+var_8C], eax
0x10089593  test    eax, eax
0x10089595  jz      short loc_10089607
0x10089597  push    1Ch
0x10089599  pop     ecx
0x1008959a  push    0Dh; int
0x1008959c  push    edx; int
0x1008959d  mov     esi, offset _rgsinfoTempQo
0x100895a2  lea     edi, [ebp+var_7C]
0x100895a5  rep movsd
0x100895a7  mov     edi, [ebp+var_80]
0x100895aa  lea     eax, [ebp+var_7C]
0x100895ad  push    eax; int
0x100895ae  push    7; int
0x100895b0  lea     edx, [ebp+var_A0]
0x100895b6  mov     ecx, edi; int
0x100895b8  call    _ErrOldOpenTempTable@24; ErrOldOpenTempTable(x,x,x,x,x,x)
0x100895bd  mov     esi, eax
0x100895bf  test    esi, esi
0x100895c1  js      loc_10089952
0x100895c7  mov     eax, [ebp+var_A0]
0x100895cd  lea     ecx, [ebx+1Ch]
0x100895d0  mov     [ebx+10h], eax
0x100895d3  lea     esi, [ecx+1Ch]
0x100895d6  mov     [ebp+var_80], eax
0x100895d9  lea     edx, [ebp+var_5C]
0x100895dc  mov     eax, [ebp+var_60]
0x100895df  mov     dword ptr [ebx+8], 0
0x100895e6  mov     [ecx], eax
0x100895e8  mov     eax, [ebp+var_70]
0x100895eb  mov     [ecx+4], eax
0x100895ee  add     ecx, 8
0x100895f1  jmp     short loc_100895FE
0x100895f3  mov     eax, [edx+0Ch]
0x100895f6  lea     edx, [edx+10h]
0x100895f9  mov     [ecx], eax
0x100895fb  add     ecx, 4
0x100895fe  cmp     ecx, esi
0x10089600  jb      short loc_100895F3
0x10089602  jmp     loc_100896E1
0x10089607  push    5
0x10089609  push    ecx
0x1008960a  push    0F000001h
0x1008960f  push    [ebp+var_90]
0x10089615  push    edi
0x10089616  call    _ErrDispCreateObject@20; ErrDispCreateObject(x,x,x,x,x)
0x1008961b  mov     esi, eax
0x1008961d  test    esi, esi
0x1008961f  js      loc_10089952
0x10089625  push    8; Size
0x10089627  call    ds:__imp__malloc
0x1008962d  mov     [ebx+8], eax
0x10089630  pop     ecx
0x10089631  test    eax, eax
0x10089633  jz      loc_10089952
0x10089639  mov     edx, [ebp+var_90]
0x1008963f  lea     ecx, [ebx+50h]
0x10089642  push    ecx
0x10089643  push    eax
0x10089644  push    [ebp+var_98]
0x1008964a  mov     ecx, edi
0x1008964c  push    5
0x1008964e  call    _ErrGetObjInfoId@24; ErrGetObjInfoId(x,x,x,x,x,x)
0x10089653  mov     esi, eax
0x10089655  test    esi, esi
0x10089657  jns     short loc_10089675
0x10089659  cmp     dword ptr [ebx+8], 0
0x1008965d  jz      short loc_10089669
0x1008965f  push    dword ptr [ebx+8]; Block
0x10089662  call    ds:__imp__free
0x10089668  pop     ecx
0x10089669  mov     dword ptr [ebx+8], 0
0x10089670  jmp     loc_10089952
0x10089675  mov     eax, [ebx+8]
0x10089678  push    80000000h
0x1008967d  push    offset _wszSqTable; "MSysQueries"
0x10089682  mov     dword ptr [eax+4], 1
0x10089689  lea     eax, [ebx+10h]
0x1008968c  push    eax
0x1008968d  push    [ebp+var_90]
0x10089693  push    edi
0x10089694  call    _ErrDispOpenTable@20; ErrDispOpenTable(x,x,x,x,x)
0x10089699  mov     esi, eax
0x1008969b  test    esi, esi
0x1008969d  jns     short loc_100896B2
0x1008969f  push    offset _wszSqTable; "MSysQueries"
0x100896a4  mov     edx, esi
0x100896a6  mov     ecx, edi
0x100896a8  call    _SetLockErrorInfo@12; SetLockErrorInfo(x,x,x)
0x100896ad  jmp     loc_10089948
0x100896b2  mov     eax, [ebx+10h]
0x100896b5  mov     ecx, ebx
0x100896b7  mov     [ebp+var_80], eax
0x100896ba  call    _ErrQodefGetColumnidsSq@4; ErrQodefGetColumnidsSq(x)
0x100896bf  mov     esi, eax
0x100896c1  test    esi, esi
0x100896c3  js      loc_10089936
0x100896c9  push    offset _wszSqAttributeIndex; "ObjectIdAttribute"
0x100896ce  push    [ebp+var_80]
0x100896d1  push    edi
0x100896d2  call    _ErrDispSetCurrentIndex@12; ErrDispSetCurrentIndex(x,x,x)
0x100896d7  mov     esi, eax
0x100896d9  test    esi, esi
0x100896db  js      loc_10089936
0x100896e1  push    0
0x100896e3  push    [ebp+var_80]
0x100896e6  push    edi
0x100896e7  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100896ec  mov     esi, eax
0x100896ee  test    esi, esi
0x100896f0  js      loc_10089936
0x100896f6  cmp     [ebp+var_8C], 0
0x100896fd  jnz     short loc_1008971F
0x100896ff  xor     eax, eax
0x10089701  push    eax
0x10089702  push    eax
0x10089703  push    4
0x10089705  lea     eax, [ebx+50h]
0x10089708  push    eax
0x10089709  push    dword ptr [ebx+18h]
0x1008970c  push    [ebp+var_80]
0x1008970f  push    edi
0x10089710  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x10089715  mov     esi, eax
0x10089717  test    esi, esi
0x10089719  js      loc_10089936
0x1008971f  mov     eax, [ebp+arg_8]
0x10089722  xor     ecx, ecx
0x10089724  mov     [ebp+var_81], cl
0x1008972a  push    2
0x1008972c  pop     edx
0x1008972d  test    eax, 10000000h
0x10089732  jz      short loc_10089739
0x10089734  xor     eax, eax
0x10089736  inc     eax
0x10089737  jmp     short loc_1008974B
0x10089739  test    eax, 8000000h
0x1008973e  jz      short loc_10089749
0x10089740  mov     [ebp+var_88], dx
0x10089747  jmp     short loc_10089752
0x10089749  xor     eax, eax
0x1008974b  mov     [ebp+var_88], ax
0x10089752  push    ecx
0x10089753  push    ecx
0x10089754  push    1
0x10089756  lea     eax, [ebp+var_81]
0x1008975c  push    eax
0x1008975d  push    dword ptr [ebx+20h]
0x10089760  push    [ebp+var_80]
0x10089763  push    edi
0x10089764  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x10089769  mov     esi, eax
0x1008976b  test    esi, esi
0x1008976d  js      loc_10089936
0x10089773  xor     eax, eax
0x10089775  push    eax
0x10089776  push    eax
0x10089777  push    2
0x10089779  lea     eax, [ebp+var_88]
0x1008977f  push    eax
0x10089780  push    dword ptr [ebx+30h]
0x10089783  push    [ebp+var_80]
0x10089786  push    edi
0x10089787  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x1008978c  mov     esi, eax
0x1008978e  test    esi, esi
0x10089790  js      loc_10089936
0x10089796  xor     eax, eax
0x10089798  push    eax
0x10089799  push    eax
0x1008979a  push    4
0x1008979c  push    offset dword_1000C084
0x100897a1  push    dword ptr [ebx+1Ch]
0x100897a4  push    [ebp+var_80]
0x100897a7  push    edi
0x100897a8  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x100897ad  mov     esi, eax
0x100897af  test    esi, esi
0x100897b1  js      loc_10089936
0x100897b7  xor     eax, eax
0x100897b9  push    eax
0x100897ba  push    eax
0x100897bb  push    eax
0x100897bc  push    [ebp+var_80]
0x100897bf  push    edi
0x100897c0  call    _ErrDispUpdate@20; ErrDispUpdate(x,x,x,x,x)
0x100897c5  mov     esi, eax
0x100897c7  test    esi, esi
0x100897c9  js      loc_10089936
0x100897cf  push    0
0x100897d1  push    [ebp+var_80]
0x100897d4  push    edi
0x100897d5  call    _ErrDispPrepareUpdate2@12; ErrDispPrepareUpdate2(x,x,x)
0x100897da  mov     esi, eax
0x100897dc  test    esi, esi
0x100897de  js      loc_10089936
0x100897e4  cmp     [ebp+var_8C], 0
0x100897eb  jnz     short loc_1008980D
0x100897ed  xor     eax, eax
0x100897ef  push    eax
0x100897f0  push    eax
0x100897f1  push    4
0x100897f3  lea     eax, [ebx+50h]
0x100897f6  push    eax
0x100897f7  push    dword ptr [ebx+18h]
0x100897fa  push    [ebp+var_80]
0x100897fd  push    edi
0x100897fe  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x10089803  mov     esi, eax
0x10089805  test    esi, esi
0x10089807  js      loc_10089936
0x1008980d  xor     eax, eax
0x1008980f  mov     [ebp+var_81], 0FFh
0x10089816  push    eax
0x10089817  push    eax
0x10089818  push    1
0x1008981a  lea     eax, [ebp+var_81]
0x10089820  push    eax
0x10089821  push    dword ptr [ebx+20h]
0x10089824  push    [ebp+var_80]
0x10089827  push    edi
0x10089828  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x1008982d  mov     esi, eax
0x1008982f  test    esi, esi
0x10089831  js      loc_10089936
0x10089837  xor     eax, eax
0x10089839  push    eax
0x1008983a  push    eax
0x1008983b  push    4
0x1008983d  push    offset dword_1000C084
0x10089842  push    dword ptr [ebx+1Ch]
0x10089845  push    [ebp+var_80]
0x10089848  push    edi
0x10089849  call    _ErrDispSetColumn@28; ErrDispSetColumn(x,x,x,x,x,x,x)
0x1008984e  mov     esi, eax
0x10089850  test    esi, esi
0x10089852  js      loc_10089936
0x10089858  xor     eax, eax
0x1008985a  push    eax
0x1008985b  push    eax
0x1008985c  push    eax
0x1008985d  push    [ebp+var_80]
0x10089860  push    edi
0x10089861  call    _ErrDispUpdate@20; ErrDispUpdate(x,x,x,x,x)
0x10089866  mov     esi, eax
  ... truncated ...
```
