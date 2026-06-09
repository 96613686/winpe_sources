# TXISAMInit(x)

- ea: `0x100148d0`
- end: `0x10014e8e`
- name: `_TXISAMInit@4`
- size: `1470`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x10009010`
- `0x10009fc0`
- `0x1000a010`
- `0x1000ad60`
- `0x1000bf60`
- `0x10013f40`
- `0x10014690`
- `0x100146b0`
- `0x100148d0`
- `0x10015240`
- `0x100198d0`
- `0x10019a50`
- `0x1001b5d0`
- `0x1001f0e0`
- `0x1002b080`
- `0x1002b140`
- `0x1002b81a`
- `0x1002c9ed`
- `0x1002cd0b`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x10014916`
- `KERNEL32!LoadLibraryExA` at `0x10014916`
- `KERNEL32!GetProcAddress` at `0x1001492b`
- `KERNEL32!GetProcAddress` at `0x1001492b`
- `ADVAPI32!RegCloseKey` at `0x10014d8a`
- `ADVAPI32!RegCloseKey` at `0x10014e03`
- `ADVAPI32!RegCloseKey` at `0x10014d39`

## string_xrefs

- `0x10014911`: `mlang.dll`
- `0x10014925`: `DllGetClassObject`

## pseudocode

```c
int __stdcall TXISAMInit(int a1)
{
  HMODULE Library; // eax
  HRESULT (__stdcall *DllGetClassObject)(const IID *const, const IID *const, LPVOID *); // eax
  wchar_t *v3; // ecx
  int v4; // edx
  wchar_t v5; // ax
  int v6; // edx
  wchar_t *v7; // ecx
  wchar_t v8; // ax
  int v9; // edx
  int *v10; // ecx
  __int16 v11; // ax
  int v12; // edx
  int *v13; // ecx
  __int16 v14; // ax
  int v15; // edx
  wchar_t *v16; // ecx
  wchar_t v17; // ax
  int v18; // eax
  int v19; // edi
  int RegSpec; // esi
  int result; // eax
  wchar_t *v22; // eax
  int v23; // ecx
  wchar_t *v24; // ebx
  wchar_t *v25; // ebp
  int v26; // edi
  int v27; // esi
  int v28; // edx
  wchar_t *v29; // ecx
  wchar_t v30; // ax
  int v31; // esi
  int v32; // eax
  int v33; // edi
  wchar_t *v34; // esi
  int v35; // esi
  unsigned int v36; // esi
  int v37; // eax
  int v38; // ecx
  DWORD v39; // esi
  _DWORD *v40; // ecx
  _DWORD *v41; // eax
  wchar_t **v42; // [esp+30h] [ebp-730h]
  wchar_t **v43; // [esp+30h] [ebp-730h]
  wchar_t **v44; // [esp+30h] [ebp-730h]
  HKEY hKey; // [esp+40h] [ebp-720h] BYREF
  int v46; // [esp+44h] [ebp-71Ch]
  int v47; // [esp+48h] [ebp-718h]
  int v48; // [esp+4Ch] [ebp-714h] BYREF
  DWORD cbData; // [esp+50h] [ebp-710h] BYREF
  wchar_t pszDest[112]; // [esp+54h] [ebp-70Ch] BYREF
  int v51; // [esp+134h] [ebp-62Ch]
  _DWORD v52[255]; // [esp+138h] [ebp-628h] BYREF
  int v53; // [esp+534h] [ebp-22Ch]
  int v54; // [esp+538h] [ebp-228h]
  wchar_t String[10]; // [esp+53Ch] [ebp-224h] BYREF
  int v56[131]; // [esp+550h] [ebp-210h] BYREF

  v48 = 0;
  cbData = 20;
  v47 = 12288;
  if ( dword_10040FC0 )
    goto LABEL_75;
  Library = LoadLibraryExA("mlang.dll", 0, 8u);
  dword_10040FD4 = Library;
  if ( Library )
  {
    DllGetClassObject = (HRESULT (__stdcall *)(const IID *const, const IID *const, LPVOID *))GetProcAddress(
                                                                                               Library,
                                                                                               "DllGetClassObject");
    dword_10040FDC = (int)DllGetClassObject;
    if ( DllGetClassObject )
    {
      DllGetClassObject(&CLSID_CMultiLanguage, &IID_IClassFactory, (LPVOID *)&dword_10040FD8);
      if ( dword_10040FD8 )
      {
        if ( !(*(int (__stdcall **)(int, _DWORD, GUID *, int *))(*(_DWORD *)dword_10040FD8 + 12))(
                dword_10040FD8,
                0,
                &IID_IMultiLanguage,
                &dword_10040FCC) )
          (**(void (__stdcall ***)(int, GUID *, int *))dword_10040FCC)(dword_10040FCC, &IID_IMultiLanguage2, &pML2);
      }
    }
  }
  if ( (*(int (__stdcall **)(int, _DWORD, int, int *, int *, int))(dword_10040FC4 + 128))(a1, 0, 55, &v48, v56, 522) )
    LOWORD(v56[0]) = 0;
  v3 = &::String;
  ISAMDefaults = 1;
  v4 = 64;
  while ( v4 != -2147483582 )
  {
    v5 = *(wchar_t *)((char *)v3 + (char *)L"txt,csv,tab,asc" - (char *)&::String);
    if ( !v5 )
      break;
    *v3++ = v5;
    if ( !--v4 )
    {
      --v3;
      break;
    }
  }
  *v3 = 0;
  v6 = 1026;
  v7 = &DefaultSecureExtensions;
  while ( v6 != -2147482620 )
  {
    v8 = *(wchar_t *)((char *)v7 + (char *)L"!txt,csv,tab,asc,tmp,htm,html" - (char *)&DefaultSecureExtensions);
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
  v9 = 1026;
  v10 = dword_10041068;
  while ( v9 != -2147482620 )
  {
    v11 = *(_WORD *)((char *)v10 + (char *)L"CSVDelimited" - (char *)dword_10041068);
    if ( !v11 )
      break;
    *(_WORD *)v10 = v11;
    v10 = (int *)((char *)v10 + 2);
    if ( !--v9 )
    {
      v10 = (int *)((char *)v10 - 2);
      break;
    }
  }
  *(_WORD *)v10 = 0;
  v12 = 1026;
  v13 = DefaultImportFixedFormat;
  while ( v12 != -2147482620 )
  {
    v14 = *(_WORD *)((char *)v13 + (char *)L"RaggedEdge" - (char *)DefaultImportFixedFormat);
    if ( !v14 )
      break;
    *(_WORD *)v13 = v14;
    v13 = (int *)((char *)v13 + 2);
    if ( !--v12 )
    {
      v13 = (int *)((char *)v13 - 2);
      break;
    }
  }
  *(_WORD *)v13 = 0;
  v15 = 1026;
  v16 = &DefaultCharacterSet;
  while ( v15 != -2147482620 )
  {
    v17 = *(wchar_t *)((char *)v16 + (char *)L"ANSI" - (char *)&DefaultCharacterSet);
    if ( !v17 )
      break;
    *v16++ = v17;
    if ( !--v15 )
    {
      --v16;
      break;
    }
  }
  *v16 = 0;
  InitializeSpec(&DefaultFileSpec);
  v18 = SetupConfigurationSpec(0);
  v19 = v18;
  if ( v18 )
  {
    RegSpec = ConfigReadRegSpec(L"Text", (int)L"Software\\Microsoft\\Jet\\4.0", v48, (int)v56, v18);
    ConfigRelease(v19);
    if ( RegSpec )
      return -5033;
  }
  if ( !DecodeCharacterSet(&DefaultCharacterSet, (int)&dword_10046A24, 1) )
    return -5033;
  if ( !DecodeFormat(dword_10041068, &dword_10046A34, dword_10046A38) )
    return -5033;
  DefaultFileSpec = 0;
  v22 = pszDest;
  v51 = 0;
  v23 = 16;
  do
  {
    v22 += 7;
    *(v22 - 7) = 0;
    --v23;
  }
  while ( v23 );
  v46 = 0;
  v24 = wcstok(&::String, L",", v42);
  if ( !v24 )
    return -5033;
  v25 = pszDest;
  v26 = (char *)L"*." - (char *)pszDest;
  do
  {
    v27 = wcslen(v24);
    if ( ascii_wcsicmp(v24, L"None") && (unsigned int)(v27 - 1) > 2 )
      return -5033;
    if ( v46 < 16 )
    {
      v28 = 7;
      v29 = v25;
      while ( v28 != -2147483639 )
      {
        v30 = *(wchar_t *)((char *)v29 + v26);
        if ( !v30 )
          break;
        *v29++ = v30;
        if ( !--v28 )
        {
          --v29;
          break;
        }
      }
      *v29 = 0;
      if ( v27 <= 3 )
        StringCchCatW(v25, 7u, v24);
    }
    v25 += 7;
    v31 = v46 + 1;
    v26 -= 14;
    ++v46;
    v32 = (int)wcstok(0, L",", v43);
    v24 = (wchar_t *)v32;
  }
  while ( v32 );
  if ( !v31 )
    return -5033;
  v51 = v31;
  v53 = 0;
  v54 = 0;
  if ( DefaultSecureExtensions == 33 )
  {
    v54 = 1;
    v32 = 1;
  }
  memset32(v52, v32, 0xFFu);
  v33 = 0;
  v34 = wcstok(&DefaultSecureExtensions + v32, L",", v43);
  if ( v34 )
  {
    while ( ascii_wcsicmp(v34, L"None") )
    {
      if ( v33 < 255 )
      {
        v35 = v34 - &DefaultSecureExtensions;
        goto LABEL_62;
      }
LABEL_63:
      ++v33;
      v34 = wcstok(0, L",", v44);
      if ( !v34 )
        goto LABEL_64;
    }
    v35 = v34 - &DefaultSecureExtensions + 4;
LABEL_62:
    v52[v33] = v35;
    goto LABEL_63;
  }
LABEL_64:
  v53 = v33;
  if ( JetRegOpenKeyW(HKEY_CURRENT_USER, L"Control Panel\\International\\Calendars\\TwoDigitYearMax", &hKey) )
  {
    v36 = 2029;
  }
  else
  {
    v36 = JetRegQueryValueExW(hKey, L"1", 0, 0, (LPBYTE)String, &cbData) ? 2029 : _wtoi(String);
    RegCloseKey(hKey);
  }
  dword_100459A4 = v36 % 0x64;
  dword_100459A8 = v36 - v36 % 0x64;
  dword_100459AC = dword_100459A8 - 100;
  if ( !JetRegOpenKeyW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Jet\\4.0\\Engines\\Text", &hKey) )
  {
    v37 = JetRegQueryValueExW(hKey, L"StartDoubleWidthUnicodeCharacters", 0, 0, (LPBYTE)String, &cbData);
    v38 = *(_DWORD *)String;
    if ( v37 )
      v38 = 12288;
    v47 = v38;
    RegCloseKey(hKey);
  }
  dword_100459B8 = v47;
  ISAMDBInitialize();
  result = TextDriverInitialize(pszDest, v52);
  if ( !result )
  {
LABEL_75:
    v39 = CurrentTaskHandle();
    v40 = (_DWORD *)ISAMDBFindTask(v39);
    if ( !v40 )
    {
      v41 = (_DWORD *)ISAMDBAddTask(v39);
      v40 = v41;
      if ( !v41 )
        return -1011;
      v41[7] = dword_10040FC4;
      v41[3] = 0;
      v41[8] = a1;
    }
    ++v40[3];
    ++dword_10040FC0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x100148d0  sub     esp, 720h
0x100148d6  mov     eax, ___security_cookie
0x100148db  xor     eax, esp
0x100148dd  mov     [esp+720h+var_4], eax
0x100148e4  cmp     dword_10040FC0, 0
0x100148eb  push    ebx
0x100148ec  push    ebp
0x100148ed  push    esi
0x100148ee  push    edi; Context
0x100148ef  mov     [esp+730h+var_714], 0
0x100148f7  mov     [esp+730h+cbData], 14h
0x100148ff  mov     [esp+730h+var_718], 3000h
0x10014907  jnz     loc_10014E29
0x1001490d  push    8; dwFlags
0x1001490f  push    0; hFile
0x10014911  push    offset LibFileName; "mlang.dll"
0x10014916  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x1001491c  mov     dword_10040FD4, eax
0x10014921  test    eax, eax
0x10014923  jz      short loc_10014983
0x10014925  push    offset aDllgetclassobj; "DllGetClassObject"
0x1001492a  push    eax; hModule
0x1001492b  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x10014931  mov     dword_10040FDC, eax
0x10014936  test    eax, eax
0x10014938  jz      short loc_10014983
0x1001493a  push    offset dword_10040FD8
0x1001493f  push    offset _IID_IClassFactory
0x10014944  push    offset _CLSID_CMultiLanguage
0x10014949  call    eax
0x1001494b  mov     ecx, dword_10040FD8
0x10014951  test    ecx, ecx
0x10014953  jz      short loc_10014983
0x10014955  mov     eax, [ecx]
0x10014957  push    offset dword_10040FCC
0x1001495c  push    offset _IID_IMultiLanguage
0x10014961  push    0
0x10014963  mov     eax, [eax+0Ch]
0x10014966  push    ecx
0x10014967  call    eax
0x10014969  test    eax, eax
0x1001496b  jnz     short loc_10014983
0x1001496d  mov     eax, dword_10040FCC
0x10014972  push    offset _pML2
0x10014977  push    offset _IID_IMultiLanguage2
0x1001497c  push    eax
0x1001497d  mov     ecx, [eax]
0x1001497f  mov     eax, [ecx]
0x10014981  call    eax
0x10014983  push    20Ah
0x10014988  lea     eax, [esp+734h+var_210]
0x1001498f  push    eax
0x10014990  lea     eax, [esp+738h+var_714]
0x10014994  push    eax
0x10014995  mov     eax, dword_10040FC4
0x1001499a  push    37h ; '7'
0x1001499c  push    0
0x1001499e  push    [esp+744h+arg_0]
0x100149a5  mov     eax, [eax+80h]
0x100149ab  call    eax
0x100149ad  test    eax, eax
0x100149af  jz      short loc_100149BB
0x100149b1  xor     eax, eax
0x100149b3  mov     word ptr [esp+730h+var_210], ax
0x100149bb  mov     ecx, offset String
0x100149c0  mov     _ISAMDefaults, 1
0x100149ca  mov     esi, offset aTxtCsvTabAsc; "txt,csv,tab,asc"
0x100149cf  mov     edx, 40h ; '@'
0x100149d4  sub     esi, ecx
0x100149d6  lea     eax, [edx+7FFFFFBEh]
0x100149dc  test    eax, eax
0x100149de  jz      short loc_100149F4
0x100149e0  movzx   eax, word ptr [esi+ecx]
0x100149e4  test    ax, ax
0x100149e7  jz      short loc_100149F4
0x100149e9  mov     [ecx], ax
0x100149ec  add     ecx, 2
0x100149ef  dec     edx
0x100149f0  jnz     short loc_100149D6
0x100149f2  jmp     short loc_100149F8
0x100149f4  test    edx, edx
0x100149f6  jnz     short loc_100149FB
0x100149f8  sub     ecx, 2
0x100149fb  xor     eax, eax
0x100149fd  mov     esi, offset aTxtCsvTabAscTm; "!txt,csv,tab,asc,tmp,htm,html"
0x10014a02  mov     [ecx], ax
0x10014a05  mov     edx, 402h
0x10014a0a  mov     ecx, offset _DefaultSecureExtensions
0x10014a0f  sub     esi, ecx
0x10014a11  lea     eax, [edx+7FFFFBFCh]
0x10014a17  test    eax, eax
0x10014a19  jz      short loc_10014A2F
0x10014a1b  movzx   eax, word ptr [esi+ecx]
0x10014a1f  test    ax, ax
0x10014a22  jz      short loc_10014A2F
0x10014a24  mov     [ecx], ax
0x10014a27  add     ecx, 2
0x10014a2a  dec     edx
0x10014a2b  jnz     short loc_10014A11
0x10014a2d  jmp     short loc_10014A33
0x10014a2f  test    edx, edx
0x10014a31  jnz     short loc_10014A36
0x10014a33  sub     ecx, 2
0x10014a36  xor     eax, eax
0x10014a38  mov     esi, offset aCsvdelimited; "CSVDelimited"
0x10014a3d  mov     [ecx], ax
0x10014a40  mov     edx, 402h
0x10014a45  mov     ecx, offset dword_10041068
0x10014a4a  sub     esi, ecx
0x10014a4c  lea     esp, [esp+0]
0x10014a50  lea     eax, [edx+7FFFFBFCh]
0x10014a56  test    eax, eax
0x10014a58  jz      short loc_10014A6E
0x10014a5a  movzx   eax, word ptr [esi+ecx]
0x10014a5e  test    ax, ax
0x10014a61  jz      short loc_10014A6E
0x10014a63  mov     [ecx], ax
0x10014a66  add     ecx, 2
0x10014a69  dec     edx
0x10014a6a  jnz     short loc_10014A50
0x10014a6c  jmp     short loc_10014A72
0x10014a6e  test    edx, edx
0x10014a70  jnz     short loc_10014A75
0x10014a72  sub     ecx, 2
0x10014a75  xor     eax, eax
0x10014a77  mov     esi, offset aRaggededge; "RaggedEdge"
0x10014a7c  mov     [ecx], ax
0x10014a7f  mov     edx, 402h
0x10014a84  mov     ecx, offset _DefaultImportFixedFormat
0x10014a89  sub     esi, ecx
0x10014a8b  jmp     short loc_10014A90
0x10014a90  lea     eax, [edx+7FFFFBFCh]
0x10014a96  test    eax, eax
0x10014a98  jz      short loc_10014AAE
0x10014a9a  movzx   eax, word ptr [esi+ecx]
0x10014a9e  test    ax, ax
0x10014aa1  jz      short loc_10014AAE
0x10014aa3  mov     [ecx], ax
0x10014aa6  add     ecx, 2
0x10014aa9  dec     edx
0x10014aaa  jnz     short loc_10014A90
0x10014aac  jmp     short loc_10014AB2
0x10014aae  test    edx, edx
0x10014ab0  jnz     short loc_10014AB5
0x10014ab2  sub     ecx, 2
0x10014ab5  xor     eax, eax
0x10014ab7  mov     esi, offset aAnsi; "ANSI"
0x10014abc  mov     [ecx], ax
0x10014abf  mov     edx, 402h
0x10014ac4  mov     ecx, offset _DefaultCharacterSet
0x10014ac9  sub     esi, ecx
0x10014acb  jmp     short loc_10014AD0
0x10014ad0  lea     eax, [edx+7FFFFBFCh]
0x10014ad6  test    eax, eax
0x10014ad8  jz      short loc_10014AEE
0x10014ada  movzx   eax, word ptr [ecx+esi]
0x10014ade  test    ax, ax
0x10014ae1  jz      short loc_10014AEE
0x10014ae3  mov     [ecx], ax
0x10014ae6  add     ecx, 2
0x10014ae9  dec     edx
0x10014aea  jnz     short loc_10014AD0
0x10014aec  jmp     short loc_10014AF2
0x10014aee  test    edx, edx
0x10014af0  jnz     short loc_10014AF5
0x10014af2  sub     ecx, 2
0x10014af5  xor     eax, eax
0x10014af7  push    offset _DefaultFileSpec
0x10014afc  mov     [ecx], ax
0x10014aff  call    _InitializeSpec@4; InitializeSpec(x)
0x10014b04  push    0
0x10014b06  call    SetupConfigurationSpec
0x10014b0b  mov     edi, eax
0x10014b0d  test    edi, edi
0x10014b0f  jz      short loc_10014B43
0x10014b11  push    edi; int
0x10014b12  lea     eax, [esp+734h+var_210]
0x10014b19  push    eax; int
0x10014b1a  push    [esp+738h+var_714]; int
0x10014b1e  push    offset aSoftwareMicros_0; "Software\\Microsoft\\Jet\\4.0"
0x10014b23  push    offset aText; "Text"
0x10014b28  call    _ConfigReadRegSpec@20; ConfigReadRegSpec(x,x,x,x,x)
0x10014b2d  push    edi
0x10014b2e  mov     esi, eax
0x10014b30  call    _ConfigRelease@4; ConfigRelease(x)
0x10014b35  test    esi, esi
0x10014b37  jz      short loc_10014B43
0x10014b39  mov     eax, 0FFFFEC57h
0x10014b3e  jmp     loc_10014E73
0x10014b43  push    1; int
0x10014b45  push    offset dword_10046A24; int
0x10014b4a  push    offset _DefaultCharacterSet; String
0x10014b4f  call    _DecodeCharacterSet@12; DecodeCharacterSet(x,x,x)
0x10014b54  test    eax, eax
0x10014b56  jz      short loc_10014B39
0x10014b58  push    offset dword_10046A38
0x10014b5d  push    offset dword_10046A34
0x10014b62  push    offset dword_10041068
0x10014b67  call    _DecodeFormat@12; DecodeFormat(x,x,x)
0x10014b6c  test    eax, eax
0x10014b6e  jz      short loc_10014B39
0x10014b70  mov     _DefaultFileSpec, 0
0x10014b7a  lea     eax, [esp+730h+pszDest]
0x10014b7e  mov     [esp+730h+var_62C], 0
0x10014b89  mov     ecx, 10h
0x10014b8e  mov     edi, edi
0x10014b90  xor     edx, edx
0x10014b92  lea     eax, [eax+0Eh]
0x10014b95  mov     [eax-0Eh], dx
0x10014b99  dec     ecx
0x10014b9a  jnz     short loc_10014B90
0x10014b9c  push    offset Delimiter; ","
0x10014ba1  push    offset String; String
0x10014ba6  mov     [esp+738h+var_71C], edx
0x10014baa  call    _wcstok
0x10014baf  mov     ebx, eax
0x10014bb1  add     esp, 8
0x10014bb4  test    ebx, ebx
0x10014bb6  jz      short loc_10014B39
0x10014bb8  lea     ebp, [esp+730h+pszDest]
0x10014bbc  mov     edi, offset asc_1000190C; "*."
0x10014bc1  mov     eax, ebp
0x10014bc3  sub     edi, eax
0x10014bc5  mov     esi, ebx
0x10014bc7  lea     ecx, [esi+2]
0x10014bca  lea     ebx, [ebx+0]
0x10014bd0  mov     ax, [esi]
0x10014bd3  add     esi, 2
0x10014bd6  test    ax, ax
0x10014bd9  jnz     short loc_10014BD0
0x10014bdb  sub     esi, ecx
0x10014bdd  push    offset aNone; "None"
0x10014be2  push    ebx
0x10014be3  sar     esi, 1
0x10014be5  call    _ascii_wcsicmp
0x10014bea  add     esp, 8
0x10014bed  test    eax, eax
0x10014bef  jz      short loc_10014BFD
0x10014bf1  lea     eax, [esi-1]
0x10014bf4  cmp     eax, 2
0x10014bf7  ja      loc_10014B39
0x10014bfd  cmp     [esp+730h+var_71C], 10h
0x10014c02  jge     short loc_10014C48
0x10014c04  mov     edx, 7
0x10014c09  mov     ecx, ebp
0x10014c0b  jmp     short loc_10014C10
0x10014c10  lea     eax, [edx+7FFFFFF7h]
0x10014c16  test    eax, eax
0x10014c18  jz      short loc_10014C2E
0x10014c1a  movzx   eax, word ptr [ecx+edi]
0x10014c1e  test    ax, ax
0x10014c21  jz      short loc_10014C2E
0x10014c23  mov     [ecx], ax
0x10014c26  add     ecx, 2
0x10014c29  dec     edx
0x10014c2a  jnz     short loc_10014C10
0x10014c2c  jmp     short loc_10014C32
0x10014c2e  test    edx, edx
0x10014c30  jnz     short loc_10014C35
0x10014c32  sub     ecx, 2
0x10014c35  xor     eax, eax
0x10014c37  mov     [ecx], ax
0x10014c3a  cmp     esi, 3
0x10014c3d  jg      short loc_10014C48
0x10014c3f  push    ebx; pszSrc
0x10014c40  push    7; cchDest
0x10014c42  push    ebp; pszDest
0x10014c43  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x10014c48  mov     esi, [esp+730h+var_71C]
0x10014c4c  add     ebp, 0Eh
0x10014c4f  push    offset Delimiter; ","
0x10014c54  inc     esi
0x10014c55  sub     edi, 0Eh
0x10014c58  push    0; String
0x10014c5a  mov     [esp+738h+var_71C], esi
0x10014c5e  call    _wcstok
0x10014c63  mov     ebx, eax
0x10014c65  add     esp, 8
0x10014c68  test    ebx, ebx
0x10014c6a  jnz     loc_10014BC5
0x10014c70  test    esi, esi
0x10014c72  jz      loc_10014B39
0x10014c78  cmp     _DefaultSecureExtensions, 21h ; '!'
0x10014c80  mov     [esp+730h+var_62C], esi
0x10014c87  mov     [esp+730h+var_22C], eax
0x10014c8e  mov     [esp+730h+var_228], eax
0x10014c95  jnz     short loc_10014CA7
0x10014c97  mov     [esp+730h+var_228], 1
0x10014ca2  mov     eax, 1
0x10014ca7  mov     ecx, 0FFh
0x10014cac  lea     edi, [esp+730h+var_628]
0x10014cb3  rep stosd
0x10014cb5  lea     eax, _DefaultSecureExtensions[eax*2]
0x10014cbc  xor     edi, edi
0x10014cbe  push    offset Delimiter; ","
0x10014cc3  push    eax; String
0x10014cc4  call    _wcstok
0x10014cc9  mov     esi, eax
0x10014ccb  add     esp, 8
0x10014cce  test    esi, esi
  ... truncated ...
```
