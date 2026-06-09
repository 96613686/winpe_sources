# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180004fdc`
- end: `0x18000549c`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006b24`
- `0x1800077d0`

## callees

- `0x180004fdc`
- `0x180005688`
- `0x1800057a4`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000514a`
- `msvcrt!wcscpy_s` at `0x1800052c0`
- `msvcrt!wcscpy_s` at `0x18000514a`
- `msvcrt!wcscpy_s` at `0x1800052c0`
- `msvcrt!wcscat_s` at `0x18000518e`
- `msvcrt!wcscat_s` at `0x1800051ca`
- `msvcrt!wcscat_s` at `0x1800052fc`
- `msvcrt!wcscat_s` at `0x180005338`
- `msvcrt!wcscat_s` at `0x18000518e`
- `msvcrt!wcscat_s` at `0x1800051ca`
- `msvcrt!wcscat_s` at `0x1800052fc`
- `msvcrt!wcscat_s` at `0x180005338`
- `ADVAPI32!RegOpenKeyExW` at `0x180005232`
- `ADVAPI32!RegOpenKeyExW` at `0x180005385`
- `ADVAPI32!RegOpenKeyExW` at `0x180005232`
- `ADVAPI32!RegOpenKeyExW` at `0x180005385`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005279`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800053e5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180005279`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800053e5`
- `ADVAPI32!RegCloseKey` at `0x180005289`
- `ADVAPI32!RegCloseKey` at `0x18000539e`
- `ADVAPI32!RegCloseKey` at `0x1800053f5`
- `ADVAPI32!RegCloseKey` at `0x180005422`
- `ADVAPI32!RegCloseKey` at `0x180005430`
- `ADVAPI32!RegCloseKey` at `0x180005289`
- `ADVAPI32!RegCloseKey` at `0x18000539e`
- `ADVAPI32!RegCloseKey` at `0x1800053f5`
- `ADVAPI32!RegCloseKey` at `0x180005422`
- `ADVAPI32!RegCloseKey` at `0x180005430`
- `ole32!StringFromGUID2` at `0x180005132`
- `ole32!StringFromGUID2` at `0x180005132`
- `ole32!CoCreateInstance` at `0x180005083`
- `ole32!CoCreateInstance` at `0x180005083`

## string_xrefs

- `0x180005138`: `CLSID\`
- `0x1800052ae`: `CLSID\`

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
0x180004fdc  mov     [rsp-8+arg_10], rbx
0x180004fe1  mov     [rsp-8+arg_18], rsi
0x180004fe6  push    rbp
0x180004fe7  push    rdi
0x180004fe8  push    r12
0x180004fea  push    r14
0x180004fec  push    r15
0x180004fee  lea     rbp, [rsp-140h]
0x180004ff6  sub     rsp, 240h
0x180004ffd  mov     rax, cs:__security_cookie
0x180005004  xor     rax, rsp
0x180005007  mov     [rbp+160h+var_30], rax
0x18000500e  mov     r14d, r8d
0x180005011  mov     rdi, rdx
0x180005014  mov     rbx, rcx
0x180005017  xor     r15d, r15d
0x18000501a  mov     [rsp+260h+var_1F8], r15
0x18000501f  xorps   xmm0, xmm0
0x180005022  movups  [rbp+160h+var_1C8], xmm0
0x180005026  test    rdx, rdx
0x180005029  jnz     short loc_180005030
0x18000502b  jmp     loc_18000544E
0x180005030  mov     eax, cs:GUID_NULL.Data1
0x180005036  cmp     [rcx], eax
0x180005038  jnz     short loc_180005060
0x18000503a  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180005040  cmp     [rcx+4], eax
0x180005043  jnz     short loc_180005060
0x180005045  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000504b  cmp     [rcx+8], eax
0x18000504e  jnz     short loc_180005060
0x180005050  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180005056  cmp     [rcx+0Ch], eax
0x180005059  jnz     short loc_180005060
0x18000505b  jmp     loc_18000544E
0x180005060  lea     rax, [rsp+260h+var_1F8]
0x180005065  mov     [rsp+260h+ppv], rax; ppv
0x18000506a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180005071  mov     r12d, 1
0x180005077  mov     r8d, r12d; dwClsContext
0x18000507a  xor     edx, edx; pUnkOuter
0x18000507c  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180005083  call    cs:__imp_CoCreateInstance
0x180005089  test    eax, eax
0x18000508b  jns     loc_180005111
0x180005091  jmp     loc_180005437
0x180005096  mov     rax, [rdi+8]
0x18000509a  movups  xmm0, xmmword ptr [rax]
0x18000509d  movdqu  [rbp+160h+var_1C8], xmm0
0x1800050a2  lea     r9, [rbp+160h+var_1C8]
0x1800050a6  mov     r8d, r12d
0x1800050a9  mov     rdx, rbx
0x1800050ac  test    r14d, r14d
0x1800050af  jz      short loc_1800050F1
0x1800050b1  cmp     ecx, r12d
0x1800050b4  mov     rcx, [rsp+260h+var_1F8]
0x1800050b9  mov     rax, [rcx]
0x1800050bc  jnz     short loc_1800050C4
0x1800050be  mov     rax, [rax+28h]
0x1800050c2  jmp     short loc_1800050C8
0x1800050c4  mov     rax, [rax+38h]
0x1800050c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050cd  mov     esi, eax
0x1800050cf  test    eax, eax
0x1800050d1  jns     short loc_18000510D
0x1800050d3  mov     rcx, [rsp+260h+var_1F8]
0x1800050d8  test    rcx, rcx
0x1800050db  jz      short loc_1800050EA
0x1800050dd  mov     rax, [rcx]
0x1800050e0  mov     rax, [rax+10h]
0x1800050e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e9  nop
0x1800050ea  mov     eax, esi
0x1800050ec  jmp     loc_180005450
0x1800050f1  cmp     ecx, r12d
0x1800050f4  mov     rcx, [rsp+260h+var_1F8]
0x1800050f9  mov     rax, [rcx]
0x1800050fc  jnz     short loc_180005104
0x1800050fe  mov     rax, [rax+30h]
0x180005102  jmp     short loc_180005108
0x180005104  mov     rax, [rax+40h]
0x180005108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000510d  add     rdi, 10h
0x180005111  mov     ecx, [rdi]
0x180005113  test    ecx, ecx
0x180005115  jnz     loc_180005096
0x18000511b  test    r14d, r14d
0x18000511e  jnz     loc_180005437
0x180005124  lea     r8d, [rcx+40h]; cchMax
0x180005128  lea     rdx, [rbp+160h+sz]; lpsz
0x18000512f  mov     rcx, rbx; rguid
0x180005132  call    cs:__imp_StringFromGUID2
0x180005138  lea     r8, aClsid; "CLSID\\"
0x18000513f  mov     ebx, 80h
0x180005144  mov     edx, ebx; SizeInWords
0x180005146  lea     rcx, [rbp+160h+Destination]; Destination
0x18000514a  call    cs:__imp_wcscpy_s
0x180005150  lea     r14d, [rbx-74h]
0x180005154  lea     r12d, [rbx-30h]
0x180005158  test    eax, eax
0x18000515a  jz      short loc_180005180
0x18000515c  cmp     eax, r14d
0x18000515f  jz      loc_18000547B
0x180005165  cmp     eax, 16h
0x180005168  jz      loc_180005491
0x18000516e  cmp     eax, 22h ; '"'
0x180005171  jz      loc_180005491
0x180005177  cmp     eax, r12d
0x18000517a  jnz     loc_180005486
0x180005180  lea     r8, [rbp+160h+sz]; Source
0x180005187  mov     rdx, rbx; SizeInWords
0x18000518a  lea     rcx, [rbp+160h+Destination]; Destination
0x18000518e  call    cs:__imp_wcscat_s
0x180005194  test    eax, eax
0x180005196  jz      short loc_1800051BC
0x180005198  cmp     eax, r14d
0x18000519b  jz      loc_18000547B
0x1800051a1  cmp     eax, 16h
0x1800051a4  jz      loc_180005491
0x1800051aa  cmp     eax, 22h ; '"'
0x1800051ad  jz      loc_180005491
0x1800051b3  cmp     eax, r12d
0x1800051b6  jnz     loc_180005486
0x1800051bc  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800051c3  mov     rdx, rbx; SizeInWords
0x1800051c6  lea     rcx, [rbp+160h+Destination]; Destination
0x1800051ca  call    cs:__imp_wcscat_s
0x1800051d0  test    eax, eax
0x1800051d2  jz      short loc_1800051F8
0x1800051d4  cmp     eax, r14d
0x1800051d7  jz      loc_18000547B
0x1800051dd  cmp     eax, 16h
0x1800051e0  jz      loc_180005491
0x1800051e6  cmp     eax, 22h ; '"'
0x1800051e9  jz      loc_180005491
0x1800051ef  cmp     eax, r12d
0x1800051f2  jnz     loc_180005486
0x1800051f8  mov     rdi, 0FFFFFFFF80000000h
0x1800051ff  mov     [rbp+160h+var_1E0], rdi
0x180005203  mov     [rbp+160h+var_1D8], r15
0x180005207  mov     [rbp+160h+var_1D0], r15
0x18000520b  mov     rbx, r15
0x18000520e  mov     [rsp+260h+cSubKeys], r15d
0x180005213  mov     [rsp+260h+phkResult], r15
0x180005218  lea     rax, [rsp+260h+phkResult]
0x18000521d  mov     [rsp+260h+ppv], rax; phkResult
0x180005222  mov     r9d, 20019h; samDesired
0x180005228  xor     r8d, r8d; ulOptions
0x18000522b  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x18000522f  mov     rcx, rdi; hKey
0x180005232  call    cs:__imp_RegOpenKeyExW
0x180005238  test    eax, eax
0x18000523a  jnz     short loc_1800052AE
0x18000523c  mov     rbx, [rsp+260h+phkResult]
0x180005241  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180005246  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000524b  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180005250  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180005255  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000525a  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000525f  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180005264  lea     rax, [rsp+260h+cSubKeys]
0x180005269  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000526e  xor     r9d, r9d; lpReserved
0x180005271  xor     r8d, r8d; lpcchClass
0x180005274  xor     edx, edx; lpClass
0x180005276  mov     rcx, rbx; hKey
0x180005279  call    cs:__imp_RegQueryInfoKeyW
0x18000527f  mov     esi, eax
0x180005281  test    rbx, rbx
0x180005284  jz      short loc_180005292
0x180005286  mov     rcx, rbx; hKey
0x180005289  call    cs:__imp_RegCloseKey
0x18000528f  mov     rbx, r15
0x180005292  test    esi, esi
0x180005294  jnz     short loc_1800052AE
0x180005296  cmp     [rsp+260h+cSubKeys], r15d
0x18000529b  jnz     short loc_1800052AE
0x18000529d  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800052a1  lea     rcx, [rbp+160h+var_1E0]; this
0x1800052a5  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800052aa  mov     rdi, [rbp+160h+var_1E0]
0x1800052ae  lea     r8, aClsid; "CLSID\\"
0x1800052b5  mov     esi, 80h
0x1800052ba  mov     edx, esi; SizeInWords
0x1800052bc  lea     rcx, [rbp+160h+Destination]; Destination
0x1800052c0  call    cs:__imp_wcscpy_s
0x1800052c6  test    eax, eax
0x1800052c8  jz      short loc_1800052EE
0x1800052ca  cmp     eax, r14d
0x1800052cd  jz      loc_18000547B
0x1800052d3  cmp     eax, 16h
0x1800052d6  jz      loc_180005491
0x1800052dc  cmp     eax, 22h ; '"'
0x1800052df  jz      loc_180005491
0x1800052e5  cmp     eax, r12d
0x1800052e8  jnz     loc_180005486
0x1800052ee  lea     r8, [rbp+160h+sz]; Source
0x1800052f5  mov     rdx, rsi; SizeInWords
0x1800052f8  lea     rcx, [rbp+160h+Destination]; Destination
0x1800052fc  call    cs:__imp_wcscat_s
0x180005302  test    eax, eax
0x180005304  jz      short loc_18000532A
0x180005306  cmp     eax, r14d
0x180005309  jz      loc_18000547B
0x18000530f  cmp     eax, 16h
0x180005312  jz      loc_180005491
0x180005318  cmp     eax, 22h ; '"'
0x18000531b  jz      loc_180005491
0x180005321  cmp     eax, r12d
0x180005324  jnz     loc_180005486
0x18000532a  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180005331  mov     rdx, rsi; SizeInWords
0x180005334  lea     rcx, [rbp+160h+Destination]; Destination
0x180005338  call    cs:__imp_wcscat_s
0x18000533e  test    eax, eax
0x180005340  jz      short loc_180005366
0x180005342  cmp     eax, r14d
0x180005345  jz      loc_18000547B
0x18000534b  cmp     eax, 16h
0x18000534e  jz      loc_180005491
0x180005354  cmp     eax, 22h ; '"'
0x180005357  jz      loc_180005491
0x18000535d  cmp     eax, r12d
0x180005360  jnz     loc_180005486
0x180005366  mov     [rsp+260h+hKey], r15
0x18000536b  lea     rax, [rsp+260h+hKey]
0x180005370  mov     [rsp+260h+ppv], rax; phkResult
0x180005375  mov     r9d, 20019h; samDesired
0x18000537b  xor     r8d, r8d; ulOptions
0x18000537e  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180005382  mov     rcx, rdi; hKey
0x180005385  call    cs:__imp_RegOpenKeyExW
0x18000538b  test    eax, eax
0x18000538d  jnz     loc_18000541A
0x180005393  mov     eax, r15d
0x180005396  test    rbx, rbx
0x180005399  jz      short loc_1800053A4
0x18000539b  mov     rcx, rbx; hKey
0x18000539e  call    cs:__imp_RegCloseKey
0x1800053a4  mov     rbx, [rsp+260h+hKey]
0x1800053a9  test    eax, eax
0x1800053ab  jnz     short loc_18000541A
0x1800053ad  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800053b2  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800053b7  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800053bc  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800053c1  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800053c6  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800053cb  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800053d0  lea     rax, [rsp+260h+cSubKeys]
0x1800053d5  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800053da  xor     r9d, r9d; lpReserved
0x1800053dd  xor     r8d, r8d; lpcchClass
0x1800053e0  xor     edx, edx; lpClass
0x1800053e2  mov     rcx, rbx; hKey
0x1800053e5  call    cs:__imp_RegQueryInfoKeyW
0x1800053eb  mov     esi, eax
0x1800053ed  test    rbx, rbx
0x1800053f0  jz      short loc_1800053FE
0x1800053f2  mov     rcx, rbx; hKey
0x1800053f5  call    cs:__imp_RegCloseKey
0x1800053fb  mov     rbx, r15
0x1800053fe  test    esi, esi
0x180005400  jnz     short loc_180005428
0x180005402  cmp     [rsp+260h+cSubKeys], r15d
0x180005407  jnz     short loc_18000541A
0x180005409  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x18000540d  lea     rcx, [rbp+160h+var_1E0]; this
0x180005411  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180005416  mov     rdi, [rbp+160h+var_1E0]
0x18000541a  test    rbx, rbx
0x18000541d  jz      short loc_180005428
0x18000541f  mov     rcx, rbx; hKey
0x180005422  call    cs:__imp_RegCloseKey
0x180005428  test    rdi, rdi
0x18000542b  jz      short loc_180005437
0x18000542d  mov     rcx, rdi; hKey
0x180005430  call    cs:__imp_RegCloseKey
0x180005436  nop
0x180005437  mov     rcx, [rsp+260h+var_1F8]
0x18000543c  test    rcx, rcx
0x18000543f  jz      short loc_18000544E
0x180005441  mov     rax, [rcx]
0x180005444  mov     rax, [rax+10h]
0x180005448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000544d  nop
0x18000544e  xor     eax, eax
0x180005450  mov     rcx, [rbp+160h+var_30]
0x180005457  xor     rcx, rsp; StackCookie
0x18000545a  call    __security_check_cookie
0x18000545f  lea     r11, [rsp+260h+var_20]
0x180005467  mov     rbx, [r11+40h]
0x18000546b  mov     rsi, [r11+48h]
0x18000546f  mov     rsp, r11
0x180005472  pop     r15
0x180005474  pop     r14
0x180005476  pop     r12
0x180005478  pop     rdi
0x180005479  pop     rbp
  ... truncated ...
```
