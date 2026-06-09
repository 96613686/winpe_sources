# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180012560`
- end: `0x180012a87`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1319`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180012d20`
- `0x180012e40`

## callees

- `0x1800068ec`
- `0x180006f3c`
- `0x180012560`
- `0x1800136b0`
- `0x180015010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180012724`
- `msvcrt!wcscat_s` at `0x180012766`
- `msvcrt!wcscat_s` at `0x1800128b6`
- `msvcrt!wcscat_s` at `0x1800128f8`
- `msvcrt!wcscat_s` at `0x180012724`
- `msvcrt!wcscat_s` at `0x180012766`
- `msvcrt!wcscat_s` at `0x1800128b6`
- `msvcrt!wcscat_s` at `0x1800128f8`
- `msvcrt!wcscpy_s` at `0x1800126da`
- `msvcrt!wcscpy_s` at `0x180012874`
- `msvcrt!wcscpy_s` at `0x1800126da`
- `msvcrt!wcscpy_s` at `0x180012874`
- `ADVAPI32!RegCloseKey` at `0x180012837`
- `ADVAPI32!RegCloseKey` at `0x18001296a`
- `ADVAPI32!RegCloseKey` at `0x1800129cd`
- `ADVAPI32!RegCloseKey` at `0x180012a00`
- `ADVAPI32!RegCloseKey` at `0x180012a14`
- `ADVAPI32!RegCloseKey` at `0x180012837`
- `ADVAPI32!RegCloseKey` at `0x18001296a`
- `ADVAPI32!RegCloseKey` at `0x1800129cd`
- `ADVAPI32!RegCloseKey` at `0x180012a00`
- `ADVAPI32!RegCloseKey` at `0x180012a14`
- `ADVAPI32!RegOpenKeyExW` at `0x1800127d4`
- `ADVAPI32!RegOpenKeyExW` at `0x18001294b`
- `ADVAPI32!RegOpenKeyExW` at `0x1800127d4`
- `ADVAPI32!RegOpenKeyExW` at `0x18001294b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180012821`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800129b7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180012821`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800129b7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800126bc`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800126bc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012607`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180012607`

## string_xrefs

- `0x1800126c8`: `CLSID\`
- `0x180012862`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180012560  mov     [rsp-8+arg_10], rbx
0x180012565  mov     [rsp-8+arg_18], rsi
0x18001256a  push    rbp
0x18001256b  push    rdi
0x18001256c  push    r12
0x18001256e  push    r14
0x180012570  push    r15
0x180012572  lea     rbp, [rsp-140h]
0x18001257a  sub     rsp, 240h
0x180012581  mov     rax, cs:__security_cookie
0x180012588  xor     rax, rsp
0x18001258b  mov     [rbp+160h+var_30], rax
0x180012592  mov     r14d, r8d
0x180012595  mov     rdi, rdx
0x180012598  mov     rbx, rcx
0x18001259b  xor     r15d, r15d
0x18001259e  mov     [rsp+260h+var_1F8], r15
0x1800125a3  xorps   xmm0, xmm0
0x1800125a6  movups  [rbp+160h+var_1C8], xmm0
0x1800125aa  test    rdx, rdx
0x1800125ad  jnz     short loc_1800125B4
0x1800125af  jmp     loc_180012A38
0x1800125b4  mov     eax, cs:GUID_NULL.Data1
0x1800125ba  cmp     [rcx], eax
0x1800125bc  jnz     short loc_1800125E4
0x1800125be  mov     eax, dword ptr cs:GUID_NULL.Data2
0x1800125c4  cmp     [rcx+4], eax
0x1800125c7  jnz     short loc_1800125E4
0x1800125c9  mov     eax, dword ptr cs:GUID_NULL.Data4
0x1800125cf  cmp     [rcx+8], eax
0x1800125d2  jnz     short loc_1800125E4
0x1800125d4  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x1800125da  cmp     [rcx+0Ch], eax
0x1800125dd  jnz     short loc_1800125E4
0x1800125df  jmp     loc_180012A38
0x1800125e4  lea     rax, [rsp+260h+var_1F8]
0x1800125e9  mov     [rsp+260h+ppv], rax; ppv
0x1800125ee  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800125f5  mov     r12d, 1
0x1800125fb  mov     r8d, r12d; dwClsContext
0x1800125fe  xor     edx, edx; pUnkOuter
0x180012600  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180012607  call    cs:__imp_CoCreateInstance
0x18001260e  nop     dword ptr [rax+rax+00h]
0x180012613  test    eax, eax
0x180012615  jns     loc_18001269B
0x18001261b  jmp     loc_180012A21
0x180012620  mov     rax, [rdi+8]
0x180012624  movups  xmm0, xmmword ptr [rax]
0x180012627  movdqu  [rbp+160h+var_1C8], xmm0
0x18001262c  lea     r9, [rbp+160h+var_1C8]
0x180012630  mov     r8d, r12d
0x180012633  mov     rdx, rbx
0x180012636  test    r14d, r14d
0x180012639  jz      short loc_18001267B
0x18001263b  cmp     ecx, r12d
0x18001263e  mov     rcx, [rsp+260h+var_1F8]
0x180012643  mov     rax, [rcx]
0x180012646  jnz     short loc_18001264E
0x180012648  mov     rax, [rax+28h]
0x18001264c  jmp     short loc_180012652
0x18001264e  mov     rax, [rax+38h]
0x180012652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012657  mov     esi, eax
0x180012659  test    eax, eax
0x18001265b  jns     short loc_180012697
0x18001265d  mov     rcx, [rsp+260h+var_1F8]
0x180012662  test    rcx, rcx
0x180012665  jz      short loc_180012674
0x180012667  mov     rax, [rcx]
0x18001266a  mov     rax, [rax+10h]
0x18001266e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012673  nop
0x180012674  mov     eax, esi
0x180012676  jmp     loc_180012A3A
0x18001267b  cmp     ecx, r12d
0x18001267e  mov     rcx, [rsp+260h+var_1F8]
0x180012683  mov     rax, [rcx]
0x180012686  jnz     short loc_18001268E
0x180012688  mov     rax, [rax+30h]
0x18001268c  jmp     short loc_180012692
0x18001268e  mov     rax, [rax+40h]
0x180012692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012697  add     rdi, 10h
0x18001269b  mov     ecx, [rdi]
0x18001269d  test    ecx, ecx
0x18001269f  jnz     loc_180012620
0x1800126a5  test    r14d, r14d
0x1800126a8  jnz     loc_180012A21
0x1800126ae  lea     r8d, [rcx+40h]; cchMax
0x1800126b2  lea     rdx, [rbp+160h+sz]; lpsz
0x1800126b9  mov     rcx, rbx; rguid
0x1800126bc  call    cs:__imp_StringFromGUID2
0x1800126c3  nop     dword ptr [rax+rax+00h]
0x1800126c8  lea     r8, aClsid; "CLSID\\"
0x1800126cf  mov     ebx, 80h
0x1800126d4  mov     edx, ebx; SizeInWords
0x1800126d6  lea     rcx, [rbp+160h+Destination]; Destination
0x1800126da  call    cs:__imp_wcscpy_s
0x1800126e1  nop     dword ptr [rax+rax+00h]
0x1800126e6  lea     r14d, [rbx-74h]
0x1800126ea  lea     r12d, [rbx-30h]
0x1800126ee  test    eax, eax
0x1800126f0  jz      short loc_180012716
0x1800126f2  cmp     eax, r14d
0x1800126f5  jz      loc_180012A66
0x1800126fb  cmp     eax, 16h
0x1800126fe  jz      loc_180012A7C
0x180012704  cmp     eax, 22h ; '"'
0x180012707  jz      loc_180012A7C
0x18001270d  cmp     eax, r12d
0x180012710  jnz     loc_180012A71
0x180012716  lea     r8, [rbp+160h+sz]; Source
0x18001271d  mov     rdx, rbx; SizeInWords
0x180012720  lea     rcx, [rbp+160h+Destination]; Destination
0x180012724  call    cs:__imp_wcscat_s
0x18001272b  nop     dword ptr [rax+rax+00h]
0x180012730  test    eax, eax
0x180012732  jz      short loc_180012758
0x180012734  cmp     eax, r14d
0x180012737  jz      loc_180012A66
0x18001273d  cmp     eax, 16h
0x180012740  jz      loc_180012A7C
0x180012746  cmp     eax, 22h ; '"'
0x180012749  jz      loc_180012A7C
0x18001274f  cmp     eax, r12d
0x180012752  jnz     loc_180012A71
0x180012758  lea     r8, aRequiredCatego; "\\Required Categories"
0x18001275f  mov     rdx, rbx; SizeInWords
0x180012762  lea     rcx, [rbp+160h+Destination]; Destination
0x180012766  call    cs:__imp_wcscat_s
0x18001276d  nop     dword ptr [rax+rax+00h]
0x180012772  test    eax, eax
0x180012774  jz      short loc_18001279A
0x180012776  cmp     eax, r14d
0x180012779  jz      loc_180012A66
0x18001277f  cmp     eax, 16h
0x180012782  jz      loc_180012A7C
0x180012788  cmp     eax, 22h ; '"'
0x18001278b  jz      loc_180012A7C
0x180012791  cmp     eax, r12d
0x180012794  jnz     loc_180012A71
0x18001279a  mov     rdi, 0FFFFFFFF80000000h
0x1800127a1  mov     [rbp+160h+var_1E0], rdi
0x1800127a5  mov     [rbp+160h+var_1D8], r15
0x1800127a9  mov     [rbp+160h+var_1D0], r15
0x1800127ad  mov     rbx, r15
0x1800127b0  mov     [rsp+260h+cSubKeys], r15d
0x1800127b5  mov     [rsp+260h+phkResult], r15
0x1800127ba  lea     rax, [rsp+260h+phkResult]
0x1800127bf  mov     [rsp+260h+ppv], rax; phkResult
0x1800127c4  mov     r9d, 20019h; samDesired
0x1800127ca  xor     r8d, r8d; ulOptions
0x1800127cd  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x1800127d1  mov     rcx, rdi; hKey
0x1800127d4  call    cs:__imp_RegOpenKeyExW
0x1800127db  nop     dword ptr [rax+rax+00h]
0x1800127e0  test    eax, eax
0x1800127e2  jnz     short loc_180012862
0x1800127e4  mov     rbx, [rsp+260h+phkResult]
0x1800127e9  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800127ee  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800127f3  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800127f8  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800127fd  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180012802  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180012807  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18001280c  lea     rax, [rsp+260h+cSubKeys]
0x180012811  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180012816  xor     r9d, r9d; lpReserved
0x180012819  xor     r8d, r8d; lpcchClass
0x18001281c  xor     edx, edx; lpClass
0x18001281e  mov     rcx, rbx; hKey
0x180012821  call    cs:__imp_RegQueryInfoKeyW
0x180012828  nop     dword ptr [rax+rax+00h]
0x18001282d  mov     esi, eax
0x18001282f  test    rbx, rbx
0x180012832  jz      short loc_180012846
0x180012834  mov     rcx, rbx; hKey
0x180012837  call    cs:__imp_RegCloseKey
0x18001283e  nop     dword ptr [rax+rax+00h]
0x180012843  mov     rbx, r15
0x180012846  test    esi, esi
0x180012848  jnz     short loc_180012862
0x18001284a  cmp     [rsp+260h+cSubKeys], r15d
0x18001284f  jnz     short loc_180012862
0x180012851  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180012855  lea     rcx, [rbp+160h+var_1E0]; this
0x180012859  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x18001285e  mov     rdi, [rbp+160h+var_1E0]
0x180012862  lea     r8, aClsid; "CLSID\\"
0x180012869  mov     esi, 80h
0x18001286e  mov     edx, esi; SizeInWords
0x180012870  lea     rcx, [rbp+160h+Destination]; Destination
0x180012874  call    cs:__imp_wcscpy_s
0x18001287b  nop     dword ptr [rax+rax+00h]
0x180012880  test    eax, eax
0x180012882  jz      short loc_1800128A8
0x180012884  cmp     eax, r14d
0x180012887  jz      loc_180012A66
0x18001288d  cmp     eax, 16h
0x180012890  jz      loc_180012A7C
0x180012896  cmp     eax, 22h ; '"'
0x180012899  jz      loc_180012A7C
0x18001289f  cmp     eax, r12d
0x1800128a2  jnz     loc_180012A71
0x1800128a8  lea     r8, [rbp+160h+sz]; Source
0x1800128af  mov     rdx, rsi; SizeInWords
0x1800128b2  lea     rcx, [rbp+160h+Destination]; Destination
0x1800128b6  call    cs:__imp_wcscat_s
0x1800128bd  nop     dword ptr [rax+rax+00h]
0x1800128c2  test    eax, eax
0x1800128c4  jz      short loc_1800128EA
0x1800128c6  cmp     eax, r14d
0x1800128c9  jz      loc_180012A66
0x1800128cf  cmp     eax, 16h
0x1800128d2  jz      loc_180012A7C
0x1800128d8  cmp     eax, 22h ; '"'
0x1800128db  jz      loc_180012A7C
0x1800128e1  cmp     eax, r12d
0x1800128e4  jnz     loc_180012A71
0x1800128ea  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800128f1  mov     rdx, rsi; SizeInWords
0x1800128f4  lea     rcx, [rbp+160h+Destination]; Destination
0x1800128f8  call    cs:__imp_wcscat_s
0x1800128ff  nop     dword ptr [rax+rax+00h]
0x180012904  test    eax, eax
0x180012906  jz      short loc_18001292C
0x180012908  cmp     eax, r14d
0x18001290b  jz      loc_180012A66
0x180012911  cmp     eax, 16h
0x180012914  jz      loc_180012A7C
0x18001291a  cmp     eax, 22h ; '"'
0x18001291d  jz      loc_180012A7C
0x180012923  cmp     eax, r12d
0x180012926  jnz     loc_180012A71
0x18001292c  mov     [rsp+260h+hKey], r15
0x180012931  lea     rax, [rsp+260h+hKey]
0x180012936  mov     [rsp+260h+ppv], rax; phkResult
0x18001293b  mov     r9d, 20019h; samDesired
0x180012941  xor     r8d, r8d; ulOptions
0x180012944  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180012948  mov     rcx, rdi; hKey
0x18001294b  call    cs:__imp_RegOpenKeyExW
0x180012952  nop     dword ptr [rax+rax+00h]
0x180012957  test    eax, eax
0x180012959  jnz     loc_1800129F8
0x18001295f  mov     eax, r15d
0x180012962  test    rbx, rbx
0x180012965  jz      short loc_180012976
0x180012967  mov     rcx, rbx; hKey
0x18001296a  call    cs:__imp_RegCloseKey
0x180012971  nop     dword ptr [rax+rax+00h]
0x180012976  mov     rbx, [rsp+260h+hKey]
0x18001297b  test    eax, eax
0x18001297d  jnz     short loc_1800129F8
0x18001297f  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180012984  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180012989  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18001298e  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180012993  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180012998  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18001299d  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800129a2  lea     rax, [rsp+260h+cSubKeys]
0x1800129a7  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800129ac  xor     r9d, r9d; lpReserved
0x1800129af  xor     r8d, r8d; lpcchClass
0x1800129b2  xor     edx, edx; lpClass
0x1800129b4  mov     rcx, rbx; hKey
0x1800129b7  call    cs:__imp_RegQueryInfoKeyW
0x1800129be  nop     dword ptr [rax+rax+00h]
0x1800129c3  mov     esi, eax
0x1800129c5  test    rbx, rbx
0x1800129c8  jz      short loc_1800129DC
0x1800129ca  mov     rcx, rbx; hKey
0x1800129cd  call    cs:__imp_RegCloseKey
0x1800129d4  nop     dword ptr [rax+rax+00h]
0x1800129d9  mov     rbx, r15
0x1800129dc  test    esi, esi
0x1800129de  jnz     short loc_180012A0C
0x1800129e0  cmp     [rsp+260h+cSubKeys], r15d
0x1800129e5  jnz     short loc_1800129F8
0x1800129e7  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800129eb  lea     rcx, [rbp+160h+var_1E0]; this
0x1800129ef  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800129f4  mov     rdi, [rbp+160h+var_1E0]
0x1800129f8  test    rbx, rbx
0x1800129fb  jz      short loc_180012A0C
0x1800129fd  mov     rcx, rbx; hKey
0x180012a00  call    cs:__imp_RegCloseKey
0x180012a07  nop     dword ptr [rax+rax+00h]
0x180012a0c  test    rdi, rdi
0x180012a0f  jz      short loc_180012A21
0x180012a11  mov     rcx, rdi; hKey
0x180012a14  call    cs:__imp_RegCloseKey
0x180012a1b  nop     dword ptr [rax+rax+00h]
0x180012a20  nop
0x180012a21  mov     rcx, [rsp+260h+var_1F8]
0x180012a26  test    rcx, rcx
0x180012a29  jz      short loc_180012A38
  ... truncated ...
```
