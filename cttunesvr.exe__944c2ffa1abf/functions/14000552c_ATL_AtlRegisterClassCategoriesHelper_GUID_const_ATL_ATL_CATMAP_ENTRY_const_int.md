# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x14000552c`
- end: `0x1400059e0`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1204`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140005ce4`
- `0x1400061fc`

## callees

- `0x140002c14`
- `0x140003018`
- `0x14000552c`
- `0x1400065f0`
- `0x140007010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400057cf`
- `ADVAPI32!RegCloseKey` at `0x1400058e4`
- `ADVAPI32!RegCloseKey` at `0x14000593b`
- `ADVAPI32!RegCloseKey` at `0x140005968`
- `ADVAPI32!RegCloseKey` at `0x140005976`
- `ADVAPI32!RegCloseKey` at `0x1400057cf`
- `ADVAPI32!RegCloseKey` at `0x1400058e4`
- `ADVAPI32!RegCloseKey` at `0x14000593b`
- `ADVAPI32!RegCloseKey` at `0x140005968`
- `ADVAPI32!RegCloseKey` at `0x140005976`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400057bf`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000592b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1400057bf`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14000592b`
- `ADVAPI32!RegOpenKeyExW` at `0x140005778`
- `ADVAPI32!RegOpenKeyExW` at `0x1400058cb`
- `ADVAPI32!RegOpenKeyExW` at `0x140005778`
- `ADVAPI32!RegOpenKeyExW` at `0x1400058cb`
- `msvcrt!wcscat_s` at `0x1400056d4`
- `msvcrt!wcscat_s` at `0x140005710`
- `msvcrt!wcscat_s` at `0x140005842`
- `msvcrt!wcscat_s` at `0x14000587e`
- `msvcrt!wcscat_s` at `0x1400056d4`
- `msvcrt!wcscat_s` at `0x140005710`
- `msvcrt!wcscat_s` at `0x140005842`
- `msvcrt!wcscat_s` at `0x14000587e`
- `msvcrt!wcscpy_s` at `0x140005690`
- `msvcrt!wcscpy_s` at `0x140005806`
- `msvcrt!wcscpy_s` at `0x140005690`
- `msvcrt!wcscpy_s` at `0x140005806`
- `ole32!CoCreateInstance` at `0x1400055d1`
- `ole32!CoCreateInstance` at `0x1400055d1`
- `ole32!StringFromGUID2` at `0x140005678`
- `ole32!StringFromGUID2` at `0x140005678`

## string_xrefs

- `0x140005683`: `CLSID\`
- `0x1400057f9`: `CLSID\`

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

  ppv = 0;
  v4 = a2;
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
    goto LABEL_66;
  while ( 1 )
  {
    v11 = *(_DWORD *)v4;
    if ( !*(_DWORD *)v4 )
    {
      if ( !a3 )
      {
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
        v27[1] = 0;
        v27[0] = 0xFFFFFFFF80000000uLL;
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
LABEL_66:
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return 0;
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
0x14000552c  mov     [rsp-8+arg_10], rbx
0x140005531  mov     [rsp-8+arg_18], rsi
0x140005536  push    rbp
0x140005537  push    rdi
0x140005538  push    r12
0x14000553a  push    r14
0x14000553c  push    r15
0x14000553e  lea     rbp, [rsp-140h]
0x140005546  sub     rsp, 240h
0x14000554d  mov     rax, cs:__security_cookie
0x140005554  xor     rax, rsp
0x140005557  mov     [rbp+160h+var_30], rax
0x14000555e  xor     r15d, r15d
0x140005561  xorps   xmm0, xmm0
0x140005564  mov     [rsp+260h+var_1F8], r15
0x140005569  mov     r14d, r8d
0x14000556c  mov     rdi, rdx
0x14000556f  mov     rbx, rcx
0x140005572  movups  [rbp+160h+var_1C8], xmm0
0x140005576  test    rdx, rdx
0x140005579  jz      loc_140005992
0x14000557f  mov     eax, cs:GUID_NULL.Data1
0x140005585  cmp     [rcx], eax
0x140005587  jnz     short loc_1400055AE
0x140005589  mov     eax, dword ptr cs:GUID_NULL.Data2
0x14000558f  cmp     [rcx+4], eax
0x140005592  jnz     short loc_1400055AE
0x140005594  mov     eax, dword ptr cs:GUID_NULL.Data4
0x14000559a  cmp     [rcx+8], eax
0x14000559d  jnz     short loc_1400055AE
0x14000559f  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x1400055a5  cmp     [rcx+0Ch], eax
0x1400055a8  jz      loc_140005992
0x1400055ae  lea     rax, [rsp+260h+var_1F8]
0x1400055b3  mov     r12d, 1
0x1400055b9  mov     r8d, r12d; dwClsContext
0x1400055bc  mov     [rsp+260h+ppv], rax; ppv
0x1400055c1  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1400055c8  xor     edx, edx; pUnkOuter
0x1400055ca  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1400055d1  call    cs:__imp_CoCreateInstance
0x1400055d7  test    eax, eax
0x1400055d9  js      loc_14000597C
0x1400055df  jmp     short loc_14000565B
0x1400055e1  mov     rax, [rdi+8]
0x1400055e5  lea     r9, [rbp+160h+var_1C8]
0x1400055e9  mov     r8d, r12d
0x1400055ec  mov     rdx, rbx
0x1400055ef  movups  xmm0, xmmword ptr [rax]
0x1400055f2  movdqu  [rbp+160h+var_1C8], xmm0
0x1400055f7  test    r14d, r14d
0x1400055fa  jz      short loc_14000563B
0x1400055fc  cmp     ecx, r12d
0x1400055ff  mov     rcx, [rsp+260h+var_1F8]
0x140005604  mov     rax, [rcx]
0x140005607  jnz     short loc_14000560F
0x140005609  mov     rax, [rax+28h]
0x14000560d  jmp     short loc_140005613
0x14000560f  mov     rax, [rax+38h]
0x140005613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005618  mov     esi, eax
0x14000561a  test    eax, eax
0x14000561c  jns     short loc_140005657
0x14000561e  mov     rcx, [rsp+260h+var_1F8]
0x140005623  test    rcx, rcx
0x140005626  jz      short loc_140005634
0x140005628  mov     rax, [rcx]
0x14000562b  mov     rax, [rax+10h]
0x14000562f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005634  mov     eax, esi
0x140005636  jmp     loc_140005994
0x14000563b  cmp     ecx, r12d
0x14000563e  mov     rcx, [rsp+260h+var_1F8]
0x140005643  mov     rax, [rcx]
0x140005646  jnz     short loc_14000564E
0x140005648  mov     rax, [rax+30h]
0x14000564c  jmp     short loc_140005652
0x14000564e  mov     rax, [rax+40h]
0x140005652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005657  add     rdi, 10h
0x14000565b  mov     ecx, [rdi]
0x14000565d  test    ecx, ecx
0x14000565f  jnz     short loc_1400055E1
0x140005661  test    r14d, r14d
0x140005664  jnz     loc_14000597C
0x14000566a  lea     r8d, [rcx+40h]; cchMax
0x14000566e  mov     rcx, rbx; rguid
0x140005671  lea     rdx, [rbp+160h+sz]; lpsz
0x140005678  call    cs:__imp_StringFromGUID2
0x14000567e  mov     ebx, 80h
0x140005683  lea     r8, aClsid; "CLSID\\"
0x14000568a  mov     edx, ebx; SizeInWords
0x14000568c  lea     rcx, [rbp+160h+Destination]; Destination
0x140005690  call    cs:__imp_wcscpy_s
0x140005696  lea     r14d, [rbx-74h]
0x14000569a  lea     r12d, [rbx-30h]
0x14000569e  test    eax, eax
0x1400056a0  jz      short loc_1400056C6
0x1400056a2  cmp     eax, r14d
0x1400056a5  jz      loc_1400059BF
0x1400056ab  cmp     eax, 16h
0x1400056ae  jz      loc_1400059D5
0x1400056b4  cmp     eax, 22h ; '"'
0x1400056b7  jz      loc_1400059D5
0x1400056bd  cmp     eax, r12d
0x1400056c0  jnz     loc_1400059CA
0x1400056c6  lea     r8, [rbp+160h+sz]; Source
0x1400056cd  mov     rdx, rbx; SizeInWords
0x1400056d0  lea     rcx, [rbp+160h+Destination]; Destination
0x1400056d4  call    cs:__imp_wcscat_s
0x1400056da  test    eax, eax
0x1400056dc  jz      short loc_140005702
0x1400056de  cmp     eax, r14d
0x1400056e1  jz      loc_1400059BF
0x1400056e7  cmp     eax, 16h
0x1400056ea  jz      loc_1400059D5
0x1400056f0  cmp     eax, 22h ; '"'
0x1400056f3  jz      loc_1400059D5
0x1400056f9  cmp     eax, r12d
0x1400056fc  jnz     loc_1400059CA
0x140005702  lea     r8, aRequiredCatego; "\\Required Categories"
0x140005709  mov     rdx, rbx; SizeInWords
0x14000570c  lea     rcx, [rbp+160h+Destination]; Destination
0x140005710  call    cs:__imp_wcscat_s
0x140005716  test    eax, eax
0x140005718  jz      short loc_14000573E
0x14000571a  cmp     eax, r14d
0x14000571d  jz      loc_1400059BF
0x140005723  cmp     eax, 16h
0x140005726  jz      loc_1400059D5
0x14000572c  cmp     eax, 22h ; '"'
0x14000572f  jz      loc_1400059D5
0x140005735  cmp     eax, r12d
0x140005738  jnz     loc_1400059CA
0x14000573e  mov     rdi, 0FFFFFFFF80000000h
0x140005745  mov     [rbp+160h+var_1D8], r15
0x140005749  lea     rax, [rsp+260h+phkResult]
0x14000574e  mov     [rbp+160h+var_1E0], rdi
0x140005752  mov     rcx, rdi; hKey
0x140005755  mov     [rbp+160h+var_1D0], r15
0x140005759  mov     r9d, 20019h; samDesired
0x14000575f  mov     [rsp+260h+cSubKeys], r15d
0x140005764  xor     r8d, r8d; ulOptions
0x140005767  mov     [rsp+260h+phkResult], r15
0x14000576c  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x140005770  mov     [rsp+260h+ppv], rax; phkResult
0x140005775  mov     rbx, r15
0x140005778  call    cs:__imp_RegOpenKeyExW
0x14000577e  test    eax, eax
0x140005780  jnz     short loc_1400057F4
0x140005782  mov     rbx, [rsp+260h+phkResult]
0x140005787  lea     rax, [rsp+260h+cSubKeys]
0x14000578c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x140005791  xor     r9d, r9d; lpReserved
0x140005794  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x140005799  xor     r8d, r8d; lpcchClass
0x14000579c  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1400057a1  xor     edx, edx; lpClass
0x1400057a3  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1400057a8  mov     rcx, rbx; hKey
0x1400057ab  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1400057b0  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1400057b5  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1400057ba  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1400057bf  call    cs:__imp_RegQueryInfoKeyW
0x1400057c5  mov     esi, eax
0x1400057c7  test    rbx, rbx
0x1400057ca  jz      short loc_1400057D8
0x1400057cc  mov     rcx, rbx; hKey
0x1400057cf  call    cs:__imp_RegCloseKey
0x1400057d5  mov     rbx, r15
0x1400057d8  test    esi, esi
0x1400057da  jnz     short loc_1400057F4
0x1400057dc  cmp     [rsp+260h+cSubKeys], r15d
0x1400057e1  jnz     short loc_1400057F4
0x1400057e3  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1400057e7  lea     rcx, [rbp+160h+var_1E0]; this
0x1400057eb  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1400057f0  mov     rdi, [rbp+160h+var_1E0]
0x1400057f4  mov     esi, 80h
0x1400057f9  lea     r8, aClsid; "CLSID\\"
0x140005800  mov     edx, esi; SizeInWords
0x140005802  lea     rcx, [rbp+160h+Destination]; Destination
0x140005806  call    cs:__imp_wcscpy_s
0x14000580c  test    eax, eax
0x14000580e  jz      short loc_140005834
0x140005810  cmp     eax, r14d
0x140005813  jz      loc_1400059BF
0x140005819  cmp     eax, 16h
0x14000581c  jz      loc_1400059D5
0x140005822  cmp     eax, 22h ; '"'
0x140005825  jz      loc_1400059D5
0x14000582b  cmp     eax, r12d
0x14000582e  jnz     loc_1400059CA
0x140005834  lea     r8, [rbp+160h+sz]; Source
0x14000583b  mov     rdx, rsi; SizeInWords
0x14000583e  lea     rcx, [rbp+160h+Destination]; Destination
0x140005842  call    cs:__imp_wcscat_s
0x140005848  test    eax, eax
0x14000584a  jz      short loc_140005870
0x14000584c  cmp     eax, r14d
0x14000584f  jz      loc_1400059BF
0x140005855  cmp     eax, 16h
0x140005858  jz      loc_1400059D5
0x14000585e  cmp     eax, 22h ; '"'
0x140005861  jz      loc_1400059D5
0x140005867  cmp     eax, r12d
0x14000586a  jnz     loc_1400059CA
0x140005870  lea     r8, aImplementedCat; "\\Implemented Categories"
0x140005877  mov     rdx, rsi; SizeInWords
0x14000587a  lea     rcx, [rbp+160h+Destination]; Destination
0x14000587e  call    cs:__imp_wcscat_s
0x140005884  test    eax, eax
0x140005886  jz      short loc_1400058AC
0x140005888  cmp     eax, r14d
0x14000588b  jz      loc_1400059BF
0x140005891  cmp     eax, 16h
0x140005894  jz      loc_1400059D5
0x14000589a  cmp     eax, 22h ; '"'
0x14000589d  jz      loc_1400059D5
0x1400058a3  cmp     eax, r12d
0x1400058a6  jnz     loc_1400059CA
0x1400058ac  lea     rax, [rsp+260h+hKey]
0x1400058b1  mov     [rsp+260h+hKey], r15
0x1400058b6  mov     r9d, 20019h; samDesired
0x1400058bc  mov     [rsp+260h+ppv], rax; phkResult
0x1400058c1  xor     r8d, r8d; ulOptions
0x1400058c4  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x1400058c8  mov     rcx, rdi; hKey
0x1400058cb  call    cs:__imp_RegOpenKeyExW
0x1400058d1  test    eax, eax
0x1400058d3  jnz     loc_140005960
0x1400058d9  mov     eax, r15d
0x1400058dc  test    rbx, rbx
0x1400058df  jz      short loc_1400058EA
0x1400058e1  mov     rcx, rbx; hKey
0x1400058e4  call    cs:__imp_RegCloseKey
0x1400058ea  mov     rbx, [rsp+260h+hKey]
0x1400058ef  test    eax, eax
0x1400058f1  jnz     short loc_140005960
0x1400058f3  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1400058f8  lea     rax, [rsp+260h+cSubKeys]
0x1400058fd  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x140005902  xor     r9d, r9d; lpReserved
0x140005905  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x14000590a  xor     r8d, r8d; lpcchClass
0x14000590d  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x140005912  xor     edx, edx; lpClass
0x140005914  mov     [rsp+260h+lpcValues], r15; lpcValues
0x140005919  mov     rcx, rbx; hKey
0x14000591c  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x140005921  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x140005926  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x14000592b  call    cs:__imp_RegQueryInfoKeyW
0x140005931  mov     esi, eax
0x140005933  test    rbx, rbx
0x140005936  jz      short loc_140005944
0x140005938  mov     rcx, rbx; hKey
0x14000593b  call    cs:__imp_RegCloseKey
0x140005941  mov     rbx, r15
0x140005944  test    esi, esi
0x140005946  jnz     short loc_14000596E
0x140005948  cmp     [rsp+260h+cSubKeys], r15d
0x14000594d  jnz     short loc_140005960
0x14000594f  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x140005953  lea     rcx, [rbp+160h+var_1E0]; this
0x140005957  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x14000595c  mov     rdi, [rbp+160h+var_1E0]
0x140005960  test    rbx, rbx
0x140005963  jz      short loc_14000596E
0x140005965  mov     rcx, rbx; hKey
0x140005968  call    cs:__imp_RegCloseKey
0x14000596e  test    rdi, rdi
0x140005971  jz      short loc_14000597C
0x140005973  mov     rcx, rdi; hKey
0x140005976  call    cs:__imp_RegCloseKey
0x14000597c  mov     rcx, [rsp+260h+var_1F8]
0x140005981  test    rcx, rcx
0x140005984  jz      short loc_140005992
0x140005986  mov     rax, [rcx]
0x140005989  mov     rax, [rax+10h]
0x14000598d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005992  xor     eax, eax
0x140005994  mov     rcx, [rbp+160h+var_30]
0x14000599b  xor     rcx, rsp; StackCookie
0x14000599e  call    __security_check_cookie
0x1400059a3  lea     r11, [rsp+260h+var_20]
0x1400059ab  mov     rbx, [r11+40h]
0x1400059af  mov     rsi, [r11+48h]
0x1400059b3  mov     rsp, r11
0x1400059b6  pop     r15
0x1400059b8  pop     r14
0x1400059ba  pop     r12
0x1400059bc  pop     rdi
0x1400059bd  pop     rbp
0x1400059be  retn
0x1400059bf  mov     ecx, 8007000Eh; int
0x1400059c4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400059ca  mov     ecx, 80004005h; int
0x1400059cf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
  ... truncated ...
```
