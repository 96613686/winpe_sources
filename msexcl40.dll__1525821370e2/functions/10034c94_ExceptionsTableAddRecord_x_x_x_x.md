# ExceptionsTableAddRecord(x,x,x,x)

- ea: `0x10034c94`
- end: `0x10035003`
- name: `_ExceptionsTableAddRecord@16`
- size: `879`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1002c742`
- `0x10035010`

## callees

- `0x10006400`
- `0x10018b80`
- `0x100243dc`
- `0x10034880`
- `0x10034c1b`
- `0x10034c94`
- `0x10035510`

## import_xrefs

- `msjet40!__imp__JetAddColumn@28` at `0x10034ea0`
- `msjet40!__imp__JetAddColumn@28` at `0x10034ec4`
- `msjet40!__imp__JetAddColumn@28` at `0x10034ef7`
- `msjet40!__imp__JetAddColumn@28` at `0x10034ea0`
- `msjet40!__imp__JetAddColumn@28` at `0x10034ec4`
- `msjet40!__imp__JetAddColumn@28` at `0x10034ef7`
- `msjet40!__imp__JetCreateTable@24` at `0x10034d54`
- `msjet40!__imp__JetCreateTable@24` at `0x10034e1a`
- `msjet40!__imp__JetCreateTable@24` at `0x10034d54`
- `msjet40!__imp__JetCreateTable@24` at `0x10034e1a`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10034e58`
- `msjet40!__imp__JetGetDatabaseInfo@20` at `0x10034e58`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10034f14`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10034f7c`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10034f14`
- `msjet40!__imp__JetPrepareUpdate@12` at `0x10034f7c`
- `msjet40!__imp__JetSetColumn@28` at `0x10034f6c`
- `msjet40!__imp__JetSetColumn@28` at `0x10034fb2`
- `msjet40!__imp__JetSetColumn@28` at `0x10034fcd`
- `msjet40!__imp__JetSetColumn@28` at `0x10034f6c`
- `msjet40!__imp__JetSetColumn@28` at `0x10034fb2`
- `msjet40!__imp__JetSetColumn@28` at `0x10034fcd`
- `msjet40!__imp__JetUpdate@20` at `0x10034fe6`
- `msjet40!__imp__JetUpdate@20` at `0x10034fe6`

## pseudocode

```c
int __fastcall ExceptionsTableAddRecord(JET_SESID *a1, char *a2, char *a3, char a4)
{
  JET_TABLEID *v5; // ebx
  int v6; // edx
  int Table; // eax
  _WORD *v8; // edx
  int v9; // ecx
  int v10; // eax
  JET_COLUMNID *v11; // edi
  char *v13; // edx
  char *v14; // ecx
  __int16 v15; // ax
  char *v16; // ecx
  __int16 v17; // ax
  JET_ERR v18; // eax
  JET_TABLEID v19; // ecx
  JET_SESID v20; // edx
  int v21; // [esp+10h] [ebp-1C0h] BYREF
  int v22; // [esp+14h] [ebp-1BCh]
  char *v23; // [esp+18h] [ebp-1B8h]
  int v24; // [esp+1Ch] [ebp-1B4h]
  _DWORD v25[6]; // [esp+20h] [ebp-1B0h] BYREF
  unsigned __int16 v26[64]; // [esp+38h] [ebp-198h] BYREF
  __int16 v27; // [esp+B8h] [ebp-118h]
  WCHAR cchMax[70]; // [esp+140h] [ebp-90h] BYREF

  v23 = a2;
  if ( a1 )
  {
    v5 = a1 + 2;
    v22 = 0;
    if ( a1[2] )
    {
      v11 = a1 + 3;
    }
    else
    {
      GetLocalizedNames();
      WCSCPY2(v26, (_WORD *)a1 + 14, 0x82u);
      WCSCAT2(v26, L"_", 0x82u);
      v6 = 158;
      if ( a1[6] != 1 )
        v6 = 288;
      WCSCAT2(v26, (JET_SESID *)((char *)a1 + v6), 0x82u);
      v27 = 0;
      MakeValidJetName(v26, cchMax, 65, 0);
      Table = JetCreateTable(*a1, a1[1], cchMax, 0, 0, a1 + 2);
      if ( Table )
      {
        if ( Table != -1303 )
          return -5407;
        v24 = 1;
        while ( 1 )
        {
          WCSCPY2(v26, (_WORD *)a1 + 14, 0x82u);
          WCSCAT2(v26, L"_", 0x82u);
          v8 = a1 + 72;
          if ( a1[6] == 1 )
            v8 = (_WORD *)a1 + 79;
          WCSCAT2(v26, v8, 0x82u);
          v27 = 0;
          MakeValidJetName(v26, cchMax, 65, 0);
          AppendSuffix((size_t)cchMax, v9);
          ++v24;
          v10 = JetCreateTable(*a1, a1[1], cchMax, 0, 0, a1 + 2);
          if ( !v10 )
            break;
          if ( v10 != -1303 )
            return -5407;
        }
      }
      else
      {
        v24 = 1;
      }
      memset(v25, 0, sizeof(v25));
      v25[0] = 24;
      if ( JetGetDatabaseInfo(*a1, a1[1], &v21, 4, 18) )
        return -5407;
      v11 = a1 + 3;
      v25[3] = v21;
      v25[2] = 10;
      v25[4] = 510;
      if ( JetAddColumn(*a1, *v5, (char *)a1 + 418, v25, 0, 0, a1 + 3) )
        return -5407;
      if ( JetAddColumn(*a1, *v5, a1 + 137, v25, 0, 0, a1 + 4) )
        return -5407;
      v25[2] = 4;
      v25[4] = 4;
      if ( JetAddColumn(*a1, *v5, (char *)a1 + 678, v25, 0, 0, a1 + 5) )
        return -5407;
    }
    if ( JetPrepareUpdate(*a1, *v5, 0) )
      return -5408;
    v13 = (char *)a1 + 130 * (_DWORD)v23 + 808;
    v14 = v13;
    v23 = v13 + 2;
    do
    {
      v15 = *(_WORD *)v14;
      v14 += 2;
    }
    while ( v15 != (_WORD)v22 );
    if ( JetSetColumn(*a1, a1[2], *v11, v13, 2 * ((v14 - v23) >> 1), 0, 0) )
      goto LABEL_25;
    v16 = a3;
    do
    {
      v17 = *(_WORD *)v16;
      v16 += 2;
    }
    while ( v17 != (_WORD)v22 );
    if ( JetSetColumn(*a1, *v5, a1[4], a3, 2 * ((v16 - (a3 + 2)) >> 1), 0, 0) )
      goto LABEL_25;
    v18 = JetSetColumn(*a1, *v5, a1[5], &a4, 4u, 0, 0);
    v19 = *v5;
    v20 = *a1;
    if ( v18 )
    {
      JetPrepareUpdate(v20, v19, 3u);
      return -5408;
    }
    if ( JetUpdate(v20, v19, 0, 0, 0) )
    {
LABEL_25:
      JetPrepareUpdate(*a1, *v5, 3u);
      return -5408;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x10034c94  mov     edi, edi
0x10034c96  push    ebp
0x10034c97  mov     ebp, esp
0x10034c99  sub     esp, 1C4h
0x10034c9f  mov     eax, ___security_cookie
0x10034ca4  xor     eax, ebp
0x10034ca6  mov     [ebp+var_4], eax
0x10034ca9  mov     eax, [ebp+arg_0]
0x10034cac  push    ebx
0x10034cad  push    esi
0x10034cae  mov     esi, ecx
0x10034cb0  mov     [ebp+var_1B8], edx
0x10034cb6  mov     [ebp+pvData], eax
0x10034cbc  push    edi
0x10034cbd  test    esi, esi
0x10034cbf  jz      loc_10034FF0
0x10034cc5  xor     edi, edi
0x10034cc7  lea     ebx, [esi+8]
0x10034cca  mov     [ebp+var_1BC], edi
0x10034cd0  cmp     [ebx], edi
0x10034cd2  jnz     loc_10034F0B
0x10034cd8  call    GetLocalizedNames
0x10034cdd  lea     edx, [esi+1Ch]
0x10034ce0  push    82h
0x10034ce5  lea     ecx, [ebp+var_198]
0x10034ceb  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10034cf0  push    82h
0x10034cf5  mov     edx, offset asc_10005B98; "_"
0x10034cfa  lea     ecx, [ebp+var_198]
0x10034d00  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10034d05  cmp     dword ptr [esi+18h], 1
0x10034d09  lea     ecx, [ebp+var_198]
0x10034d0f  mov     eax, 120h
0x10034d14  mov     edx, 9Eh
0x10034d19  cmovnz  edx, eax
0x10034d1c  push    82h
0x10034d21  add     edx, esi
0x10034d23  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10034d28  push    edi
0x10034d29  xor     eax, eax
0x10034d2b  lea     edx, [ebp+cchMax]
0x10034d31  push    41h ; 'A'
0x10034d33  lea     ecx, [ebp+var_198]
0x10034d39  mov     [ebp+var_118], ax
0x10034d40  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x10034d45  push    ebx
0x10034d46  push    edi
0x10034d47  push    edi
0x10034d48  lea     eax, [ebp+cchMax]
0x10034d4e  push    eax
0x10034d4f  push    dword ptr [esi+4]
0x10034d52  push    dword ptr [esi]
0x10034d54  call    ds:__imp__JetCreateTable@24; JetCreateTable(x,x,x,x,x,x)
0x10034d5a  mov     edi, 0FFFFFAE9h
0x10034d5f  test    eax, eax
0x10034d61  jz      short loc_10034D77
0x10034d63  cmp     eax, edi
0x10034d65  jnz     loc_10034F01
0x10034d6b  mov     [ebp+var_1B4], 1
0x10034d75  jmp     short loc_10034D89
0x10034d77  mov     [ebp+var_1B4], 1
0x10034d81  cmp     eax, edi
0x10034d83  jnz     loc_10034E31
0x10034d89  push    82h
0x10034d8e  lea     edx, [esi+1Ch]
0x10034d91  lea     ecx, [ebp+var_198]
0x10034d97  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10034d9c  push    82h
0x10034da1  mov     edx, offset asc_10005B98; "_"
0x10034da6  lea     ecx, [ebp+var_198]
0x10034dac  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10034db1  cmp     dword ptr [esi+18h], 1
0x10034db5  lea     eax, [esi+9Eh]
0x10034dbb  lea     edx, [esi+120h]
0x10034dc1  cmovz   edx, eax
0x10034dc4  lea     ecx, [ebp+var_198]
0x10034dca  push    82h
0x10034dcf  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10034dd4  xor     eax, eax
0x10034dd6  lea     edx, [ebp+cchMax]
0x10034ddc  push    eax
0x10034ddd  push    41h ; 'A'
0x10034ddf  lea     ecx, [ebp+var_198]
0x10034de5  mov     [ebp+var_118], ax
0x10034dec  call    _MakeValidJetName@16; MakeValidJetName(x,x,x,x)
0x10034df1  mov     edx, [ebp+var_1B4]
0x10034df7  push    ecx; int
0x10034df8  lea     ecx, [ebp+cchMax]; cchMax
0x10034dfe  call    AppendSuffix
0x10034e03  inc     [ebp+var_1B4]
0x10034e09  xor     eax, eax
0x10034e0b  push    ebx
0x10034e0c  push    eax
0x10034e0d  push    eax
0x10034e0e  lea     eax, [ebp+cchMax]
0x10034e14  push    eax
0x10034e15  push    dword ptr [esi+4]
0x10034e18  push    dword ptr [esi]
0x10034e1a  call    ds:__imp__JetCreateTable@24; JetCreateTable(x,x,x,x,x,x)
0x10034e20  test    eax, eax
0x10034e22  jz      short loc_10034E31
0x10034e24  cmp     eax, edi
0x10034e26  jz      loc_10034D89
0x10034e2c  jmp     loc_10034F01
0x10034e31  push    6
0x10034e33  pop     ecx
0x10034e34  push    12h
0x10034e36  xor     eax, eax
0x10034e38  lea     edi, [ebp+var_1B0]
0x10034e3e  rep stosd
0x10034e40  push    4
0x10034e42  lea     eax, [ebp+var_1C0]
0x10034e48  mov     [ebp+var_1B0], 18h
0x10034e52  push    eax
0x10034e53  push    dword ptr [esi+4]
0x10034e56  push    dword ptr [esi]
0x10034e58  call    ds:__imp__JetGetDatabaseInfo@20; JetGetDatabaseInfo(x,x,x,x,x)
0x10034e5e  test    eax, eax
0x10034e60  jnz     loc_10034F01
0x10034e66  mov     eax, [ebp+var_1C0]
0x10034e6c  lea     edi, [esi+0Ch]
0x10034e6f  push    edi
0x10034e70  mov     [ebp+var_1A4], eax
0x10034e76  xor     eax, eax
0x10034e78  push    eax
0x10034e79  push    eax
0x10034e7a  lea     eax, [ebp+var_1B0]
0x10034e80  mov     [ebp+var_1A8], 0Ah
0x10034e8a  push    eax
0x10034e8b  lea     eax, [esi+1A2h]
0x10034e91  mov     [ebp+var_1A0], 1FEh
0x10034e9b  push    eax
0x10034e9c  push    dword ptr [ebx]
0x10034e9e  push    dword ptr [esi]
0x10034ea0  call    ds:__imp__JetAddColumn@28; JetAddColumn(x,x,x,x,x,x,x)
0x10034ea6  test    eax, eax
0x10034ea8  jnz     short loc_10034F01
0x10034eaa  lea     eax, [esi+10h]
0x10034ead  push    eax
0x10034eae  xor     eax, eax
0x10034eb0  push    eax
0x10034eb1  push    eax
0x10034eb2  lea     eax, [ebp+var_1B0]
0x10034eb8  push    eax
0x10034eb9  lea     eax, [esi+224h]
0x10034ebf  push    eax
0x10034ec0  push    dword ptr [ebx]
0x10034ec2  push    dword ptr [esi]
0x10034ec4  call    ds:__imp__JetAddColumn@28; JetAddColumn(x,x,x,x,x,x,x)
0x10034eca  test    eax, eax
0x10034ecc  jnz     short loc_10034F01
0x10034ece  push    4
0x10034ed0  pop     eax
0x10034ed1  mov     [ebp+var_1A8], eax
0x10034ed7  mov     [ebp+var_1A0], eax
0x10034edd  lea     eax, [esi+14h]
0x10034ee0  push    eax
0x10034ee1  xor     eax, eax
0x10034ee3  push    eax
0x10034ee4  push    eax
0x10034ee5  lea     eax, [ebp+var_1B0]
0x10034eeb  push    eax
0x10034eec  lea     eax, [esi+2A6h]
0x10034ef2  push    eax
0x10034ef3  push    dword ptr [ebx]
0x10034ef5  push    dword ptr [esi]
0x10034ef7  call    ds:__imp__JetAddColumn@28; JetAddColumn(x,x,x,x,x,x,x)
0x10034efd  test    eax, eax
0x10034eff  jz      short loc_10034F0E
0x10034f01  mov     eax, 0FFFFEAE1h
0x10034f06  jmp     loc_10034FF2
0x10034f0b  lea     edi, [esi+0Ch]
0x10034f0e  push    0; prep
0x10034f10  push    dword ptr [ebx]; tableid
0x10034f12  push    dword ptr [esi]; sesid
0x10034f14  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x10034f1a  test    eax, eax
0x10034f1c  jz      short loc_10034F28
0x10034f1e  mov     eax, 0FFFFEAE0h
0x10034f23  jmp     loc_10034FF2
0x10034f28  imul    edx, [ebp+var_1B8], 82h
0x10034f32  add     edx, 328h
0x10034f38  add     edx, esi
0x10034f3a  mov     ecx, edx
0x10034f3c  lea     eax, [ecx+2]
0x10034f3f  mov     [ebp+var_1B8], eax
0x10034f45  mov     ax, [ecx]
0x10034f48  add     ecx, 2
0x10034f4b  cmp     ax, word ptr [ebp+var_1BC]
0x10034f52  jnz     short loc_10034F45
0x10034f54  sub     ecx, [ebp+var_1B8]
0x10034f5a  xor     eax, eax
0x10034f5c  push    eax; psetinfo
0x10034f5d  push    eax; grbit
0x10034f5e  sar     ecx, 1
0x10034f60  lea     eax, [ecx+ecx]
0x10034f63  push    eax; cbData
0x10034f64  push    edx; pvData
0x10034f65  push    dword ptr [edi]; columnid
0x10034f67  push    dword ptr [esi+8]; tableid
0x10034f6a  push    dword ptr [esi]; sesid
0x10034f6c  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10034f72  test    eax, eax
0x10034f74  jz      short loc_10034F84
0x10034f76  push    3; prep
0x10034f78  push    dword ptr [ebx]; tableid
0x10034f7a  push    dword ptr [esi]; sesid
0x10034f7c  call    ds:__imp__JetPrepareUpdate@12; JetPrepareUpdate(x,x,x)
0x10034f82  jmp     short loc_10034F1E
0x10034f84  mov     edi, [ebp+pvData]
0x10034f8a  mov     ecx, edi
0x10034f8c  lea     edx, [ecx+2]
0x10034f8f  mov     ax, [ecx]
0x10034f92  add     ecx, 2
0x10034f95  cmp     ax, word ptr [ebp+var_1BC]
0x10034f9c  jnz     short loc_10034F8F
0x10034f9e  sub     ecx, edx
0x10034fa0  xor     eax, eax
0x10034fa2  push    eax; psetinfo
0x10034fa3  push    eax; grbit
0x10034fa4  sar     ecx, 1
0x10034fa6  lea     eax, [ecx+ecx]
0x10034fa9  push    eax; cbData
0x10034faa  push    edi; pvData
0x10034fab  push    dword ptr [esi+10h]; columnid
0x10034fae  push    dword ptr [ebx]; tableid
0x10034fb0  push    dword ptr [esi]; sesid
0x10034fb2  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10034fb8  test    eax, eax
0x10034fba  jnz     short loc_10034F76
0x10034fbc  xor     edi, edi
0x10034fbe  lea     eax, [ebp+arg_4]
0x10034fc1  push    edi; psetinfo
0x10034fc2  push    edi; grbit
0x10034fc3  push    4; cbData
0x10034fc5  push    eax; pvData
0x10034fc6  push    dword ptr [esi+14h]; columnid
0x10034fc9  push    dword ptr [ebx]; tableid
0x10034fcb  push    dword ptr [esi]; sesid
0x10034fcd  call    ds:__imp__JetSetColumn@28; JetSetColumn(x,x,x,x,x,x,x)
0x10034fd3  mov     ecx, [ebx]
0x10034fd5  mov     edx, [esi]
0x10034fd7  test    eax, eax
0x10034fd9  jz      short loc_10034FE1
0x10034fdb  push    3
0x10034fdd  push    ecx
0x10034fde  push    edx
0x10034fdf  jmp     short loc_10034F7C
0x10034fe1  push    edi; pcbActual
0x10034fe2  push    edi; cbBookmark
0x10034fe3  push    edi; pvBookmark
0x10034fe4  push    ecx; tableid
0x10034fe5  push    edx; sesid
0x10034fe6  call    ds:__imp__JetUpdate@20; JetUpdate(x,x,x,x,x)
0x10034fec  test    eax, eax
0x10034fee  jnz     short loc_10034F76
0x10034ff0  xor     eax, eax
0x10034ff2  mov     ecx, [ebp+var_4]
0x10034ff5  pop     edi
0x10034ff6  pop     esi
0x10034ff7  xor     ecx, ebp; StackCookie
0x10034ff9  pop     ebx
0x10034ffa  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10034fff  leave
0x10035000  retn    8
```
