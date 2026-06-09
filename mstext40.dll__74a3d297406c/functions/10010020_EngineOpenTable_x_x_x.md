# EngineOpenTable(x,x,x)

- ea: `0x10010020`
- end: `0x10010365`
- name: `_EngineOpenTable@12`
- size: `837`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x10011060`

## callees

- `0x1000a1f0`
- `0x1000ad60`
- `0x1000bf80`
- `0x1000bfc0`
- `0x10010020`
- `0x10013b30`
- `0x10014070`
- `0x10019c30`
- `0x1001bff0`
- `0x1001c060`
- `0x1001c250`
- `0x1001eb10`
- `0x1001f140`
- `0x1001f300`
- `0x1001fcd0`
- `0x1002b81a`

## pseudocode

```c
int __stdcall EngineOpenTable(_DWORD *a1, _DWORD *a2, int a3)
{
  int v3; // ebp
  bool v4; // zf
  _DWORD *v5; // edi
  int v6; // edx
  wchar_t *v7; // ecx
  wchar_t v8; // ax
  int v9; // eax
  int result; // eax
  int v11; // edi
  int v12; // esi
  int v13; // eax
  const wchar_t *v14; // esi
  _DWORD *v15; // ecx
  int **v16; // esi
  int v17; // ebp
  int v18; // edi
  int v19; // ecx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // [esp+10h] [ebp-224h] BYREF
  int v24; // [esp+14h] [ebp-220h]
  int v25; // [esp+18h] [ebp-21Ch]
  _DWORD *v26; // [esp+1Ch] [ebp-218h]
  int **v27; // [esp+20h] [ebp-214h] BYREF
  wchar_t pszDest[262]; // [esp+24h] [ebp-210h] BYREF

  v3 = a2[1];
  v24 = 0;
  if ( *(_DWORD *)(v3 + 8) != 1 )
    GetFixedFormat(a1, 0);
  v4 = a1[3] == 1;
  v26 = a1 + 3;
  if ( v4 && a1[5] )
  {
    v5 = a2 + 3;
    TextCopySpecInfo(a2 + 3, a1 + 3);
    goto LABEL_30;
  }
  if ( *(_DWORD *)(v3 + 8) == 1 )
  {
    PathPartGet((wchar_t *)(v3 + 56), 3, pszDest, 522);
  }
  else
  {
    v6 = 261;
    v7 = pszDest;
    while ( v6 != -2147483385 )
    {
      v8 = *(wchar_t *)((char *)v7 + v3 + 56 - (_DWORD)pszDest);
      if ( !v8 )
        break;
      *v7++ = v8;
      if ( !--v6 )
      {
        --v7;
        break;
      }
    }
    *v7 = 0;
  }
  if ( a1[3] != 1 )
  {
    if ( *(_WORD *)(v3 + 36) != 1 && *(_DWORD *)(v3 + 32) != 1 )
      goto LABEL_20;
LABEL_19:
    StringCchCatW(pszDest, 0x105u, L"export.ini");
    v9 = 1;
    goto LABEL_21;
  }
  if ( !a1[5] )
    goto LABEL_19;
LABEL_20:
  StringCchCatW(pszDest, 0x105u, L"schema.ini");
  v9 = 0;
LABEL_21:
  v4 = *(_DWORD *)(v3 + 8) == 1;
  v25 = v9;
  if ( (!v4 || v9 == 1) && TextSpecAvailable((int)a1, (JET_TABLEID)pszDest, a2 + 230, 0) )
  {
    v5 = a2 + 3;
    result = TextSpecRead((int)a1, (JET_TABLEID)pszDest, (int)(a2 + 230), (int)(a2 + 3), 0);
    if ( result )
      return result;
    if ( v25 == 1 )
    {
      v11 = a2[5];
      v12 = a2[6];
      TextCopySpecInfo(a2 + 3, v26);
      a2[5] = v11;
      v5 = a2 + 3;
      a2[6] = v12;
    }
    *v5 = 2;
  }
  else
  {
    v5 = a2 + 3;
    TextCopySpecInfo(a2 + 3, a1 + 3);
    v13 = a1[216];
    if ( v13 )
      a2[12] = v13;
  }
LABEL_30:
  if ( *(_DWORD *)(v3 + 8) == 1 )
  {
    v14 = *(const wchar_t **)(v3 + 16);
    if ( !v14 )
    {
LABEL_35:
      ErrorSetExtendedInfoSz1(-8300, (STRSAFE_LPCWSTR)a2 + 460, 1);
      return -1305;
    }
    v15 = a2 + 230;
    while ( DBlstrcmpi(v15, v14 + 2) )
    {
      v14 = *(const wchar_t **)v14;
      v15 = a2 + 230;
      if ( !v14 )
        goto LABEL_35;
    }
    result = TextOpenFile(
               *(_DWORD *)(v3 + 28),
               v14 + 67,
               *((_DWORD *)v14 + 40),
               (int)v5,
               a2[227],
               (int)&v23,
               *(_DWORD *)(v3 + 8));
  }
  else
  {
    result = TextOpenFile(
               *(_DWORD *)(v3 + 28),
               (STRSAFE_LPCWSTR)a2 + 460,
               0,
               (int)v5,
               a2[227],
               (int)&v23,
               *(_DWORD *)(v3 + 8));
  }
  if ( !result )
  {
    TextFileCreationTime(v23, a2 + 214);
    TextListColumns(v23, &v27);
    ISAMDBDeleteColumns(a2);
    v16 = v27;
    v17 = 1;
    if ( v27 )
    {
      while ( v16[5] )
      {
LABEL_58:
        v16 = (int **)*v16;
        if ( !v16 )
          goto LABEL_59;
      }
      v18 = (int)v16[2];
      if ( v18 == 15 )
      {
        v18 = 10;
        v24 = 1;
      }
      else if ( v18 != 10 && v18 != 12 && v18 != 11 )
      {
        v19 = 33;
LABEL_44:
        v20 = ISAMDBAddColumn(
                a2,
                v16 + 9,
                v17,
                v18,
                v19,
                *((unsigned __int8 *)v16 + 244),
                *((unsigned __int8 *)v16 + 245));
        v21 = v20;
        if ( !v20 )
        {
          TextCloseFile(v23);
          return -1011;
        }
        if ( v18 == 10 || v18 == 12 )
        {
          if ( !v24 )
          {
            v22 = 2 * (_DWORD)v16[3];
            goto LABEL_56;
          }
          *(_DWORD *)(v20 + 20) = 510;
        }
        else if ( v18 == 9 )
        {
          v22 = (int)v16[3];
LABEL_56:
          *(_DWORD *)(v21 + 20) = v22;
        }
        ++v17;
        *(_DWORD *)(v21 + 24) = v16[1];
        goto LABEL_58;
      }
      v19 = (unsigned int)v16[6] & 0x8000 | 0x20;
      goto LABEL_44;
    }
LABEL_59:
    a2[2] = v23;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x10010020  sub     esp, 224h
0x10010026  mov     eax, ___security_cookie
0x1001002b  xor     eax, esp
0x1001002d  mov     [esp+224h+var_4], eax
0x10010034  push    ebx
0x10010035  mov     ebx, [esp+228h+arg_4]
0x1001003c  push    ebp
0x1001003d  push    esi
0x1001003e  mov     esi, [esp+230h+arg_0]
0x10010045  mov     ebp, [ebx+4]
0x10010048  push    edi
0x10010049  mov     [esp+234h+var_220], 0
0x10010051  cmp     dword ptr [ebp+8], 1
0x10010055  jz      short loc_1001005F
0x10010057  push    0
0x10010059  push    esi
0x1001005a  call    _GetFixedFormat@8; GetFixedFormat(x,x)
0x1001005f  cmp     dword ptr [esi+0Ch], 1
0x10010063  lea     eax, [esi+0Ch]
0x10010066  mov     [esp+234h+var_218], eax
0x1001006a  jnz     short loc_10010081
0x1001006c  cmp     dword ptr [esi+14h], 0
0x10010070  jz      short loc_10010081
0x10010072  push    eax
0x10010073  lea     edi, [ebx+0Ch]
0x10010076  push    edi
0x10010077  call    _TextCopySpecInfo@8; TextCopySpecInfo(x,x)
0x1001007c  jmp     loc_100101C2
0x10010081  cmp     dword ptr [ebp+8], 1
0x10010085  lea     eax, [esp+234h+pszDest]
0x10010089  jnz     short loc_1001009E
0x1001008b  push    20Ah; int
0x10010090  push    eax; pszDest
0x10010091  push    3; int
0x10010093  lea     eax, [ebp+38h]
0x10010096  push    eax; FullPath
0x10010097  call    _PathPartGet@16; PathPartGet(x,x,x,x)
0x1001009c  jmp     short loc_100100DA
0x1001009e  lea     edi, [ebp+38h]
0x100100a1  mov     edx, 105h
0x100100a6  lea     ecx, [esp+234h+pszDest]
0x100100aa  sub     edi, eax
0x100100ac  lea     esp, [esp+0]
0x100100b0  lea     eax, [edx+7FFFFEF9h]
0x100100b6  test    eax, eax
0x100100b8  jz      short loc_100100CE
0x100100ba  movzx   eax, word ptr [edi+ecx]
0x100100be  test    ax, ax
0x100100c1  jz      short loc_100100CE
0x100100c3  mov     [ecx], ax
0x100100c6  add     ecx, 2
0x100100c9  dec     edx
0x100100ca  jnz     short loc_100100B0
0x100100cc  jmp     short loc_100100D2
0x100100ce  test    edx, edx
0x100100d0  jnz     short loc_100100D5
0x100100d2  sub     ecx, 2
0x100100d5  xor     eax, eax
0x100100d7  mov     [ecx], ax
0x100100da  mov     eax, [esi+0Ch]
0x100100dd  cmp     eax, 1
0x100100e0  jnz     short loc_100100EC
0x100100e2  cmp     dword ptr [esi+14h], 0
0x100100e6  jz      short loc_10010105
0x100100e8  cmp     eax, eax
0x100100ea  jz      short loc_10010120
0x100100ec  cmp     word ptr [ebp+24h], 1
0x100100f1  jz      short loc_10010105
0x100100f3  cmp     eax, 1
0x100100f6  jz      short loc_10010120
0x100100f8  cmp     word ptr [ebp+24h], 1
0x100100fd  jz      short loc_10010120
0x100100ff  cmp     dword ptr [ebp+20h], 1
0x10010103  jnz     short loc_10010120
0x10010105  push    offset aExportIni; "export.ini"
0x1001010a  push    105h; cchDest
0x1001010f  lea     eax, [esp+23Ch+pszDest]
0x10010113  push    eax; pszDest
0x10010114  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10010119  mov     eax, 1
0x1001011e  jmp     short loc_10010136
0x10010120  push    offset aSchemaIni_0; "schema.ini"
0x10010125  push    105h; cchDest
0x1001012a  lea     eax, [esp+23Ch+pszDest]
0x1001012e  push    eax; pszDest
0x1001012f  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10010134  xor     eax, eax
0x10010136  cmp     dword ptr [ebp+8], 1
0x1001013a  mov     [esp+234h+var_21C], eax
0x1001013e  jnz     short loc_10010145
0x10010140  cmp     eax, 1
0x10010143  jnz     short loc_100101A8
0x10010145  push    0; tableid
0x10010147  lea     eax, [ebx+398h]
0x1001014d  push    eax; pvData
0x1001014e  lea     eax, [esp+23Ch+pszDest]
0x10010152  push    eax; JET_TABLEID
0x10010153  push    esi; int
0x10010154  call    _TextSpecAvailable@16; TextSpecAvailable(x,x,x,x)
0x10010159  test    eax, eax
0x1001015b  jz      short loc_100101A8
0x1001015d  push    0; JET_TABLEID
0x1001015f  lea     edi, [ebx+0Ch]
0x10010162  push    edi; int
0x10010163  lea     eax, [ebx+398h]
0x10010169  push    eax; int
0x1001016a  lea     eax, [esp+240h+pszDest]
0x1001016e  push    eax; tableid
0x1001016f  push    esi; int
0x10010170  call    _TextSpecRead@20; TextSpecRead(x,x,x,x,x)
0x10010175  test    eax, eax
0x10010177  jnz     loc_1001033A
0x1001017d  cmp     [esp+234h+var_21C], 1
0x10010182  jnz     short loc_100101A0
0x10010184  push    [esp+234h+var_218]
0x10010188  mov     edi, [ebx+14h]
0x1001018b  lea     eax, [ebx+0Ch]
0x1001018e  mov     esi, [ebx+18h]
0x10010191  push    eax
0x10010192  call    _TextCopySpecInfo@8; TextCopySpecInfo(x,x)
0x10010197  mov     [ebx+14h], edi
0x1001019a  lea     edi, [ebx+0Ch]
0x1001019d  mov     [ebx+18h], esi
0x100101a0  mov     dword ptr [edi], 2
0x100101a6  jmp     short loc_100101C2
0x100101a8  lea     eax, [esi+0Ch]
0x100101ab  push    eax
0x100101ac  lea     edi, [ebx+0Ch]
0x100101af  push    edi
0x100101b0  call    _TextCopySpecInfo@8; TextCopySpecInfo(x,x)
0x100101b5  mov     eax, [esi+360h]
0x100101bb  test    eax, eax
0x100101bd  jz      short loc_100101C2
0x100101bf  mov     [ebx+30h], eax
0x100101c2  mov     eax, [ebp+8]
0x100101c5  cmp     eax, 1
0x100101c8  jnz     short loc_1001022F
0x100101ca  mov     esi, [ebp+10h]
0x100101cd  test    esi, esi
0x100101cf  jz      short loc_100101F1
0x100101d1  lea     ecx, [ebx+398h]
0x100101d7  lea     eax, [esi+4]
0x100101da  push    eax
0x100101db  push    ecx
0x100101dc  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x100101e1  test    eax, eax
0x100101e3  jz      short loc_1001020E
0x100101e5  mov     esi, [esi]
0x100101e7  lea     ecx, [ebx+398h]
0x100101ed  test    esi, esi
0x100101ef  jnz     short loc_100101D7
0x100101f1  push    1; int
0x100101f3  lea     eax, [ebx+398h]
0x100101f9  push    eax; pszSrc
0x100101fa  push    0FFFFDF94h; int
0x100101ff  call    _ErrorSetExtendedInfoSz1@12; ErrorSetExtendedInfoSz1(x,x,x)
0x10010204  mov     eax, 0FFFFFAE7h
0x10010209  jmp     loc_1001033A
0x1001020e  test    esi, esi
0x10010210  jz      short loc_100101F1
0x10010212  push    dword ptr [ebp+8]
0x10010215  lea     eax, [esp+238h+var_224]
0x10010219  push    eax
0x1001021a  push    dword ptr [ebx+38Ch]
0x10010220  lea     eax, [esi+86h]
0x10010226  push    edi
0x10010227  push    dword ptr [esi+0A0h]
0x1001022d  jmp     short loc_10010244
0x1001022f  push    eax; int
0x10010230  lea     eax, [esp+238h+var_224]
0x10010234  push    eax; int
0x10010235  push    dword ptr [ebx+38Ch]; int
0x1001023b  lea     eax, [ebx+398h]
0x10010241  push    edi; int
0x10010242  push    0; int
0x10010244  push    eax; pszSrc
0x10010245  push    dword ptr [ebp+1Ch]; int
0x10010248  call    _TextOpenFile@28; TextOpenFile(x,x,x,x,x,x,x)
0x1001024d  test    eax, eax
0x1001024f  jnz     loc_1001033A
0x10010255  lea     eax, [ebx+358h]
0x1001025b  push    eax
0x1001025c  push    [esp+238h+var_224]
0x10010260  call    _TextFileCreationTime@8; TextFileCreationTime(x,x)
0x10010265  lea     eax, [esp+234h+var_214]
0x10010269  push    eax
0x1001026a  push    [esp+238h+var_224]
0x1001026e  call    _TextListColumns@8; TextListColumns(x,x)
0x10010273  push    ebx
0x10010274  call    _ISAMDBDeleteColumns@4; ISAMDBDeleteColumns(x)
0x10010279  mov     esi, [esp+234h+var_214]
0x1001027d  mov     ebp, 1
0x10010282  test    esi, esi
0x10010284  jz      loc_10010331
0x1001028a  lea     ebx, [ebx+0]
0x10010290  cmp     dword ptr [esi+14h], 0
0x10010294  jnz     loc_10010327
0x1001029a  mov     edi, [esi+8]
0x1001029d  cmp     edi, 0Fh
0x100102a0  jnz     short loc_100102F2
0x100102a2  mov     edi, 0Ah
0x100102a7  mov     [esp+234h+var_220], 1
0x100102af  mov     ecx, [esi+18h]
0x100102b2  and     ecx, 8000h
0x100102b8  or      ecx, 20h
0x100102bb  movzx   eax, byte ptr [esi+0F5h]
0x100102c2  push    eax
0x100102c3  movzx   eax, byte ptr [esi+0F4h]
0x100102ca  push    eax
0x100102cb  push    ecx
0x100102cc  push    edi
0x100102cd  push    ebp
0x100102ce  lea     eax, [esi+24h]
0x100102d1  push    eax
0x100102d2  push    ebx
0x100102d3  call    _ISAMDBAddColumn@28; ISAMDBAddColumn(x,x,x,x,x,x,x)
0x100102d8  mov     ecx, eax
0x100102da  test    ecx, ecx
0x100102dc  jz      short loc_10010355
0x100102de  cmp     edi, 0Ah
0x100102e1  jz      short loc_10010308
0x100102e3  cmp     edi, 0Ch
0x100102e6  jz      short loc_10010308
0x100102e8  cmp     edi, 9
0x100102eb  jnz     short loc_10010320
0x100102ed  mov     eax, [esi+0Ch]
0x100102f0  jmp     short loc_1001031D
0x100102f2  cmp     edi, 0Ah
0x100102f5  jz      short loc_100102AF
0x100102f7  cmp     edi, 0Ch
0x100102fa  jz      short loc_100102AF
0x100102fc  cmp     edi, 0Bh
0x100102ff  jz      short loc_100102AF
0x10010301  mov     ecx, 21h ; '!'
0x10010306  jmp     short loc_100102BB
0x10010308  cmp     [esp+234h+var_220], 0
0x1001030d  jz      short loc_10010318
0x1001030f  mov     dword ptr [ecx+14h], 1FEh
0x10010316  jmp     short loc_10010320
0x10010318  mov     eax, [esi+0Ch]
0x1001031b  add     eax, eax
0x1001031d  mov     [ecx+14h], eax
0x10010320  mov     eax, [esi+4]
0x10010323  inc     ebp
0x10010324  mov     [ecx+18h], eax
0x10010327  mov     esi, [esi]
0x10010329  test    esi, esi
0x1001032b  jnz     loc_10010290
0x10010331  mov     eax, [esp+234h+var_224]
0x10010335  mov     [ebx+8], eax
0x10010338  xor     eax, eax
0x1001033a  mov     ecx, [esp+234h+var_4]
0x10010341  pop     edi
0x10010342  pop     esi
0x10010343  pop     ebp
0x10010344  pop     ebx
0x10010345  xor     ecx, esp; StackCookie
0x10010347  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001034c  add     esp, 224h
0x10010352  retn    0Ch
0x10010355  push    [esp+234h+var_224]
0x10010359  call    _TextCloseFile@4; TextCloseFile(x)
0x1001035e  mov     eax, 0FFFFFC0Dh
0x10010363  jmp     short loc_1001033A
```
