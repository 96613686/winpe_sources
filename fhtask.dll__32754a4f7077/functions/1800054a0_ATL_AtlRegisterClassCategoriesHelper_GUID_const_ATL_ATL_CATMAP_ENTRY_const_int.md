# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800054a0`
- end: `0x180005960`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005d30`
- `0x180005df0`

## callees

- `0x1800030b4`
- `0x1800038e8`
- `0x1800054a0`
- `0x180009a00`
- `0x18000b010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000560e`
- `msvcrt!wcscpy_s` at `0x180005784`
- `msvcrt!wcscpy_s` at `0x18000560e`
- `msvcrt!wcscpy_s` at `0x180005784`
- `msvcrt!wcscat_s` at `0x180005652`
- `msvcrt!wcscat_s` at `0x18000568e`
- `msvcrt!wcscat_s` at `0x1800057c0`
- `msvcrt!wcscat_s` at `0x1800057fc`
- `msvcrt!wcscat_s` at `0x180005652`
- `msvcrt!wcscat_s` at `0x18000568e`
- `msvcrt!wcscat_s` at `0x1800057c0`
- `msvcrt!wcscat_s` at `0x1800057fc`
- `ADVAPI32!RegCloseKey` at `0x18000574d`
- `ADVAPI32!RegCloseKey` at `0x180005862`
- `ADVAPI32!RegCloseKey` at `0x1800058b9`
- `ADVAPI32!RegCloseKey` at `0x1800058e6`
- `ADVAPI32!RegCloseKey` at `0x1800058f4`
- `ADVAPI32!RegCloseKey` at `0x18000574d`
- `ADVAPI32!RegCloseKey` at `0x180005862`
- `ADVAPI32!RegCloseKey` at `0x1800058b9`
- `ADVAPI32!RegCloseKey` at `0x1800058e6`
- `ADVAPI32!RegCloseKey` at `0x1800058f4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000573d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800058a9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000573d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800058a9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800056f6`
- `ADVAPI32!RegOpenKeyExW` at `0x180005849`
- `ADVAPI32!RegOpenKeyExW` at `0x1800056f6`
- `ADVAPI32!RegOpenKeyExW` at `0x180005849`
- `ole32!CoCreateInstance` at `0x180005547`
- `ole32!CoCreateInstance` at `0x180005547`
- `ole32!StringFromGUID2` at `0x1800055f6`
- `ole32!StringFromGUID2` at `0x1800055f6`

## string_xrefs

- `0x1800055fc`: `CLSID\`
- `0x180005772`: `CLSID\`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rdi
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // esi
  __int64 v10; // rax
  int v11; // ecx
  errno_t v12; // eax
  errno_t v13; // eax
  errno_t v14; // eax
  HKEY v15; // rdi
  HKEY v16; // rbx
  LSTATUS v17; // esi
  errno_t v18; // eax
  errno_t v19; // eax
  errno_t v20; // eax
  HKEY v21; // rbx
  LSTATUS v22; // esi
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v27[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v28; // [rsp+98h] [rbp-68h] BYREF
  wchar_t Destination[128]; // [rsp+B0h] [rbp-50h] BYREF
  OLECHAR sz[64]; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = a2;
  ppv = 0;
  v28 = 0;
  if ( !a2
    || rguid->Data1 == GUID_NULL.Data1
    && *(_DWORD *)&rguid->Data2 == *(_DWORD *)&GUID_NULL.Data2
    && *(_DWORD *)rguid->Data4 == *(_DWORD *)GUID_NULL.Data4
    && *(_DWORD *)&rguid->Data4[4] == *(_DWORD *)&GUID_NULL.Data4[4] )
  {
    return 0;
  }
  if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) < 0 )
  {
LABEL_66:
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return 0;
  }
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( a3 )
        goto LABEL_66;
      StringFromGUID2(rguid, sz, 64);
      v12 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      if ( v12 )
      {
        if ( v12 == 12 )
          goto LABEL_69;
        if ( v12 == 22 || v12 == 34 )
          goto LABEL_71;
        if ( v12 != 80 )
          goto LABEL_70;
      }
      v13 = wcscat_s(Destination, 0x80u, sz);
      if ( v13 )
      {
        if ( v13 == 12 )
          goto LABEL_69;
        if ( v13 == 22 || v13 == 34 )
          goto LABEL_71;
        if ( v13 != 80 )
          goto LABEL_70;
      }
      v14 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
      if ( v14 )
      {
        if ( v14 == 12 )
          goto LABEL_69;
        if ( v14 == 22 || v14 == 34 )
          goto LABEL_71;
        if ( v14 != 80 )
          goto LABEL_70;
      }
      v15 = HKEY_CLASSES_ROOT;
      v27[0] = 0xFFFFFFFF80000000uLL;
      v27[1] = 0;
      v27[2] = 0;
      cSubKeys = 0;
      phkResult = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &phkResult) )
      {
        v16 = phkResult;
        v17 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        if ( v16 )
          RegCloseKey(v16);
        if ( !v17 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, Destination);
          v15 = (HKEY)v27[0];
        }
      }
      v18 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
      if ( v18 )
      {
        if ( v18 == 12 )
          goto LABEL_69;
        if ( v18 == 22 || v18 == 34 )
          goto LABEL_71;
        if ( v18 != 80 )
          goto LABEL_70;
      }
      v19 = wcscat_s(Destination, 0x80u, sz);
      if ( v19 )
      {
        if ( v19 == 12 )
          goto LABEL_69;
        if ( v19 == 22 || v19 == 34 )
          goto LABEL_71;
        if ( v19 != 80 )
          goto LABEL_70;
      }
      v20 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
      if ( !v20 )
      {
LABEL_58:
        hKey = 0;
        if ( !RegOpenKeyExW(v15, Destination, 0, 0x20019u, &hKey) )
        {
          v21 = hKey;
          v22 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          if ( v21 )
            RegCloseKey(v21);
          if ( !v22 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v27, Destination);
            v15 = (HKEY)v27[0];
          }
        }
        if ( v15 )
          RegCloseKey(v15);
        goto LABEL_66;
      }
      if ( v20 != 12 )
      {
        if ( v20 != 22 && v20 != 34 )
        {
          if ( v20 == 80 )
            goto LABEL_58;
LABEL_70:
          ATL::AtlThrowImpl(-2147467259);
        }
LABEL_71:
        ATL::AtlThrowImpl(-2147024809);
      }
LABEL_69:
      ATL::AtlThrowImpl(-2147024882);
    }
    v28 = *(_OWORD *)*((_QWORD *)v4 + 1);
    if ( !a3 )
    {
      v10 = *(_QWORD *)ppv;
      if ( v11 == 1 )
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 48))(ppv, rguid, 1, &v28);
      else
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v10 + 64))(ppv, rguid, 1, &v28);
      goto LABEL_19;
    }
    v6 = *(_QWORD *)ppv;
    v7 = v11 == 1
       ? (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v28)
       : (*(unsigned __int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v28);
    v8 = v7;
    if ( v7 < 0 )
      break;
LABEL_19:
    v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v8;
}

```

## disassembly

```asm
0x1800054a0  mov     [rsp-8+arg_10], rbx
0x1800054a5  mov     [rsp-8+arg_18], rsi
0x1800054aa  push    rbp
0x1800054ab  push    rdi
0x1800054ac  push    r12
0x1800054ae  push    r14
0x1800054b0  push    r15
0x1800054b2  lea     rbp, [rsp-140h]
0x1800054ba  sub     rsp, 240h
0x1800054c1  mov     rax, cs:__security_cookie
0x1800054c8  xor     rax, rsp
0x1800054cb  mov     [rbp+160h+var_30], rax
0x1800054d2  mov     r14d, r8d
0x1800054d5  mov     rdi, rdx
0x1800054d8  mov     rbx, rcx
0x1800054db  xor     r15d, r15d
0x1800054de  mov     [rsp+260h+var_1F8], r15
0x1800054e3  xorps   xmm0, xmm0
0x1800054e6  movups  [rbp+160h+var_1C8], xmm0
0x1800054ea  test    rdx, rdx
0x1800054ed  jnz     short loc_1800054F4
0x1800054ef  jmp     loc_180005912
0x1800054f4  mov     eax, cs:GUID_NULL.Data1
0x1800054fa  cmp     [rcx], eax
0x1800054fc  jnz     short loc_180005524
0x1800054fe  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180005504  cmp     [rcx+4], eax
0x180005507  jnz     short loc_180005524
0x180005509  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000550f  cmp     [rcx+8], eax
0x180005512  jnz     short loc_180005524
0x180005514  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000551a  cmp     [rcx+0Ch], eax
0x18000551d  jnz     short loc_180005524
0x18000551f  jmp     loc_180005912
0x180005524  lea     rax, [rsp+260h+var_1F8]
0x180005529  mov     [rsp+260h+ppv], rax; ppv
0x18000552e  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180005535  mov     r12d, 1
0x18000553b  mov     r8d, r12d; dwClsContext
0x18000553e  xor     edx, edx; pUnkOuter
0x180005540  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180005547  call    cs:__imp_CoCreateInstance
0x18000554d  test    eax, eax
0x18000554f  jns     loc_1800055D5
0x180005555  jmp     loc_1800058FB
0x18000555a  mov     rax, [rdi+8]
0x18000555e  movups  xmm0, xmmword ptr [rax]
0x180005561  movdqu  [rbp+160h+var_1C8], xmm0
0x180005566  lea     r9, [rbp+160h+var_1C8]
0x18000556a  mov     r8d, r12d
0x18000556d  mov     rdx, rbx
0x180005570  test    r14d, r14d
0x180005573  jz      short loc_1800055B5
0x180005575  cmp     ecx, r12d
0x180005578  mov     rcx, [rsp+260h+var_1F8]
0x18000557d  mov     rax, [rcx]
0x180005580  jnz     short loc_180005588
0x180005582  mov     rax, [rax+28h]
0x180005586  jmp     short loc_18000558C
0x180005588  mov     rax, [rax+38h]
0x18000558c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005591  mov     esi, eax
0x180005593  test    eax, eax
0x180005595  jns     short loc_1800055D1
0x180005597  mov     rcx, [rsp+260h+var_1F8]
0x18000559c  test    rcx, rcx
0x18000559f  jz      short loc_1800055AE
0x1800055a1  mov     rax, [rcx]
0x1800055a4  mov     rax, [rax+10h]
0x1800055a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ad  nop
0x1800055ae  mov     eax, esi
0x1800055b0  jmp     loc_180005914
0x1800055b5  cmp     ecx, r12d
0x1800055b8  mov     rcx, [rsp+260h+var_1F8]
0x1800055bd  mov     rax, [rcx]
0x1800055c0  jnz     short loc_1800055C8
0x1800055c2  mov     rax, [rax+30h]
0x1800055c6  jmp     short loc_1800055CC
0x1800055c8  mov     rax, [rax+40h]
0x1800055cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055d1  add     rdi, 10h
0x1800055d5  mov     ecx, [rdi]
0x1800055d7  test    ecx, ecx
0x1800055d9  jnz     loc_18000555A
0x1800055df  test    r14d, r14d
0x1800055e2  jnz     loc_1800058FB
0x1800055e8  lea     r8d, [rcx+40h]; cchMax
0x1800055ec  lea     rdx, [rbp+160h+sz]; lpsz
0x1800055f3  mov     rcx, rbx; rguid
0x1800055f6  call    cs:__imp_StringFromGUID2
0x1800055fc  lea     r8, aClsid; "CLSID\\"
0x180005603  mov     ebx, 80h
0x180005608  mov     edx, ebx; SizeInWords
0x18000560a  lea     rcx, [rbp+160h+Destination]; Destination
0x18000560e  call    cs:__imp_wcscpy_s
0x180005614  lea     r14d, [rbx-74h]
0x180005618  lea     r12d, [rbx-30h]
0x18000561c  test    eax, eax
0x18000561e  jz      short loc_180005644
0x180005620  cmp     eax, r14d
0x180005623  jz      loc_18000593F
0x180005629  cmp     eax, 16h
0x18000562c  jz      loc_180005955
0x180005632  cmp     eax, 22h ; '"'
0x180005635  jz      loc_180005955
0x18000563b  cmp     eax, r12d
0x18000563e  jnz     loc_18000594A
0x180005644  lea     r8, [rbp+160h+sz]; Source
0x18000564b  mov     rdx, rbx; SizeInWords
0x18000564e  lea     rcx, [rbp+160h+Destination]; Destination
0x180005652  call    cs:__imp_wcscat_s
0x180005658  test    eax, eax
0x18000565a  jz      short loc_180005680
0x18000565c  cmp     eax, r14d
0x18000565f  jz      loc_18000593F
0x180005665  cmp     eax, 16h
0x180005668  jz      loc_180005955
0x18000566e  cmp     eax, 22h ; '"'
0x180005671  jz      loc_180005955
0x180005677  cmp     eax, r12d
0x18000567a  jnz     loc_18000594A
0x180005680  lea     r8, aRequiredCatego; "\\Required Categories"
0x180005687  mov     rdx, rbx; SizeInWords
0x18000568a  lea     rcx, [rbp+160h+Destination]; Destination
0x18000568e  call    cs:__imp_wcscat_s
0x180005694  test    eax, eax
0x180005696  jz      short loc_1800056BC
0x180005698  cmp     eax, r14d
0x18000569b  jz      loc_18000593F
0x1800056a1  cmp     eax, 16h
0x1800056a4  jz      loc_180005955
0x1800056aa  cmp     eax, 22h ; '"'
0x1800056ad  jz      loc_180005955
0x1800056b3  cmp     eax, r12d
0x1800056b6  jnz     loc_18000594A
0x1800056bc  mov     rdi, 0FFFFFFFF80000000h
0x1800056c3  mov     [rbp+160h+var_1E0], rdi
0x1800056c7  mov     [rbp+160h+var_1D8], r15
0x1800056cb  mov     [rbp+160h+var_1D0], r15
0x1800056cf  mov     rbx, r15
0x1800056d2  mov     [rsp+260h+cSubKeys], r15d
0x1800056d7  mov     [rsp+260h+phkResult], r15
0x1800056dc  lea     rax, [rsp+260h+phkResult]
0x1800056e1  mov     [rsp+260h+ppv], rax; phkResult
0x1800056e6  mov     r9d, 20019h; samDesired
0x1800056ec  xor     r8d, r8d; ulOptions
0x1800056ef  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x1800056f3  mov     rcx, rdi; hKey
0x1800056f6  call    cs:__imp_RegOpenKeyExW
0x1800056fc  test    eax, eax
0x1800056fe  jnz     short loc_180005772
0x180005700  mov     rbx, [rsp+260h+phkResult]
0x180005705  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000570a  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000570f  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180005714  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180005719  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000571e  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180005723  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180005728  lea     rax, [rsp+260h+cSubKeys]
0x18000572d  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180005732  xor     r9d, r9d; lpReserved
0x180005735  xor     r8d, r8d; lpcchClass
0x180005738  xor     edx, edx; lpClass
0x18000573a  mov     rcx, rbx; hKey
0x18000573d  call    cs:__imp_RegQueryInfoKeyW
0x180005743  mov     esi, eax
0x180005745  test    rbx, rbx
0x180005748  jz      short loc_180005756
0x18000574a  mov     rcx, rbx; hKey
0x18000574d  call    cs:__imp_RegCloseKey
0x180005753  mov     rbx, r15
0x180005756  test    esi, esi
0x180005758  jnz     short loc_180005772
0x18000575a  cmp     [rsp+260h+cSubKeys], r15d
0x18000575f  jnz     short loc_180005772
0x180005761  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180005765  lea     rcx, [rbp+160h+var_1E0]; this
0x180005769  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18000576e  mov     rdi, [rbp+160h+var_1E0]
0x180005772  lea     r8, aClsid; "CLSID\\"
0x180005779  mov     esi, 80h
0x18000577e  mov     edx, esi; SizeInWords
0x180005780  lea     rcx, [rbp+160h+Destination]; Destination
0x180005784  call    cs:__imp_wcscpy_s
0x18000578a  test    eax, eax
0x18000578c  jz      short loc_1800057B2
0x18000578e  cmp     eax, r14d
0x180005791  jz      loc_18000593F
0x180005797  cmp     eax, 16h
0x18000579a  jz      loc_180005955
0x1800057a0  cmp     eax, 22h ; '"'
0x1800057a3  jz      loc_180005955
0x1800057a9  cmp     eax, r12d
0x1800057ac  jnz     loc_18000594A
0x1800057b2  lea     r8, [rbp+160h+sz]; Source
0x1800057b9  mov     rdx, rsi; SizeInWords
0x1800057bc  lea     rcx, [rbp+160h+Destination]; Destination
0x1800057c0  call    cs:__imp_wcscat_s
0x1800057c6  test    eax, eax
0x1800057c8  jz      short loc_1800057EE
0x1800057ca  cmp     eax, r14d
0x1800057cd  jz      loc_18000593F
0x1800057d3  cmp     eax, 16h
0x1800057d6  jz      loc_180005955
0x1800057dc  cmp     eax, 22h ; '"'
0x1800057df  jz      loc_180005955
0x1800057e5  cmp     eax, r12d
0x1800057e8  jnz     loc_18000594A
0x1800057ee  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800057f5  mov     rdx, rsi; SizeInWords
0x1800057f8  lea     rcx, [rbp+160h+Destination]; Destination
0x1800057fc  call    cs:__imp_wcscat_s
0x180005802  test    eax, eax
0x180005804  jz      short loc_18000582A
0x180005806  cmp     eax, r14d
0x180005809  jz      loc_18000593F
0x18000580f  cmp     eax, 16h
0x180005812  jz      loc_180005955
0x180005818  cmp     eax, 22h ; '"'
0x18000581b  jz      loc_180005955
0x180005821  cmp     eax, r12d
0x180005824  jnz     loc_18000594A
0x18000582a  mov     [rsp+260h+hKey], r15
0x18000582f  lea     rax, [rsp+260h+hKey]
0x180005834  mov     [rsp+260h+ppv], rax; phkResult
0x180005839  mov     r9d, 20019h; samDesired
0x18000583f  xor     r8d, r8d; ulOptions
0x180005842  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180005846  mov     rcx, rdi; hKey
0x180005849  call    cs:__imp_RegOpenKeyExW
0x18000584f  test    eax, eax
0x180005851  jnz     loc_1800058DE
0x180005857  mov     eax, r15d
0x18000585a  test    rbx, rbx
0x18000585d  jz      short loc_180005868
0x18000585f  mov     rcx, rbx; hKey
0x180005862  call    cs:__imp_RegCloseKey
0x180005868  mov     rbx, [rsp+260h+hKey]
0x18000586d  test    eax, eax
0x18000586f  jnz     short loc_1800058DE
0x180005871  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180005876  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000587b  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180005880  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180005885  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000588a  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000588f  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180005894  lea     rax, [rsp+260h+cSubKeys]
0x180005899  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000589e  xor     r9d, r9d; lpReserved
0x1800058a1  xor     r8d, r8d; lpcchClass
0x1800058a4  xor     edx, edx; lpClass
0x1800058a6  mov     rcx, rbx; hKey
0x1800058a9  call    cs:__imp_RegQueryInfoKeyW
0x1800058af  mov     esi, eax
0x1800058b1  test    rbx, rbx
0x1800058b4  jz      short loc_1800058C2
0x1800058b6  mov     rcx, rbx; hKey
0x1800058b9  call    cs:__imp_RegCloseKey
0x1800058bf  mov     rbx, r15
0x1800058c2  test    esi, esi
0x1800058c4  jnz     short loc_1800058EC
0x1800058c6  cmp     [rsp+260h+cSubKeys], r15d
0x1800058cb  jnz     short loc_1800058DE
0x1800058cd  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800058d1  lea     rcx, [rbp+160h+var_1E0]; this
0x1800058d5  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800058da  mov     rdi, [rbp+160h+var_1E0]
0x1800058de  test    rbx, rbx
0x1800058e1  jz      short loc_1800058EC
0x1800058e3  mov     rcx, rbx; hKey
0x1800058e6  call    cs:__imp_RegCloseKey
0x1800058ec  test    rdi, rdi
0x1800058ef  jz      short loc_1800058FB
0x1800058f1  mov     rcx, rdi; hKey
0x1800058f4  call    cs:__imp_RegCloseKey
0x1800058fa  nop
0x1800058fb  mov     rcx, [rsp+260h+var_1F8]
0x180005900  test    rcx, rcx
0x180005903  jz      short loc_180005912
0x180005905  mov     rax, [rcx]
0x180005908  mov     rax, [rax+10h]
0x18000590c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005911  nop
0x180005912  xor     eax, eax
0x180005914  mov     rcx, [rbp+160h+var_30]
0x18000591b  xor     rcx, rsp; StackCookie
0x18000591e  call    __security_check_cookie
0x180005923  lea     r11, [rsp+260h+var_20]
0x18000592b  mov     rbx, [r11+40h]
0x18000592f  mov     rsi, [r11+48h]
0x180005933  mov     rsp, r11
0x180005936  pop     r15
0x180005938  pop     r14
0x18000593a  pop     r12
0x18000593c  pop     rdi
0x18000593d  pop     rbp
  ... truncated ...
```
