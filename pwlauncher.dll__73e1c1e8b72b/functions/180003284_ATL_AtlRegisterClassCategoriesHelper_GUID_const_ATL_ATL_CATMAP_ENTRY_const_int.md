# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180003284`
- end: `0x180003744`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800052b0`
- `0x1800053e0`

## callees

- `0x180003284`
- `0x18000374c`
- `0x180003874`
- `0x18000fe10`
- `0x180011010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180003436`
- `msvcrt!wcscat_s` at `0x180003472`
- `msvcrt!wcscat_s` at `0x1800035a4`
- `msvcrt!wcscat_s` at `0x1800035e0`
- `msvcrt!wcscat_s` at `0x180003436`
- `msvcrt!wcscat_s` at `0x180003472`
- `msvcrt!wcscat_s` at `0x1800035a4`
- `msvcrt!wcscat_s` at `0x1800035e0`
- `msvcrt!wcscpy_s` at `0x1800033f2`
- `msvcrt!wcscpy_s` at `0x180003568`
- `msvcrt!wcscpy_s` at `0x1800033f2`
- `msvcrt!wcscpy_s` at `0x180003568`
- `ADVAPI32!RegCloseKey` at `0x180003531`
- `ADVAPI32!RegCloseKey` at `0x180003646`
- `ADVAPI32!RegCloseKey` at `0x18000369d`
- `ADVAPI32!RegCloseKey` at `0x1800036ca`
- `ADVAPI32!RegCloseKey` at `0x1800036d8`
- `ADVAPI32!RegCloseKey` at `0x180003531`
- `ADVAPI32!RegCloseKey` at `0x180003646`
- `ADVAPI32!RegCloseKey` at `0x18000369d`
- `ADVAPI32!RegCloseKey` at `0x1800036ca`
- `ADVAPI32!RegCloseKey` at `0x1800036d8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003521`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000368d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003521`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000368d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800034da`
- `ADVAPI32!RegOpenKeyExW` at `0x18000362d`
- `ADVAPI32!RegOpenKeyExW` at `0x1800034da`
- `ADVAPI32!RegOpenKeyExW` at `0x18000362d`
- `ole32!StringFromGUID2` at `0x1800033da`
- `ole32!StringFromGUID2` at `0x1800033da`
- `ole32!CoCreateInstance` at `0x18000332b`
- `ole32!CoCreateInstance` at `0x18000332b`

## string_xrefs

- `0x1800033e0`: `CLSID\`
- `0x180003556`: `CLSID\`

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
0x180003284  mov     [rsp-8+arg_10], rbx
0x180003289  mov     [rsp-8+arg_18], rsi
0x18000328e  push    rbp
0x18000328f  push    rdi
0x180003290  push    r12
0x180003292  push    r14
0x180003294  push    r15
0x180003296  lea     rbp, [rsp-140h]
0x18000329e  sub     rsp, 240h
0x1800032a5  mov     rax, cs:__security_cookie
0x1800032ac  xor     rax, rsp
0x1800032af  mov     [rbp+160h+var_30], rax
0x1800032b6  mov     r14d, r8d
0x1800032b9  mov     rdi, rdx
0x1800032bc  mov     rbx, rcx
0x1800032bf  xor     r15d, r15d
0x1800032c2  mov     [rsp+260h+var_1F8], r15
0x1800032c7  xorps   xmm0, xmm0
0x1800032ca  movups  [rbp+160h+var_1C8], xmm0
0x1800032ce  test    rdx, rdx
0x1800032d1  jnz     short loc_1800032D8
0x1800032d3  jmp     loc_1800036F6
0x1800032d8  mov     eax, cs:GUID_NULL.Data1
0x1800032de  cmp     [rcx], eax
0x1800032e0  jnz     short loc_180003308
0x1800032e2  mov     eax, dword ptr cs:GUID_NULL.Data2
0x1800032e8  cmp     [rcx+4], eax
0x1800032eb  jnz     short loc_180003308
0x1800032ed  mov     eax, dword ptr cs:GUID_NULL.Data4
0x1800032f3  cmp     [rcx+8], eax
0x1800032f6  jnz     short loc_180003308
0x1800032f8  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x1800032fe  cmp     [rcx+0Ch], eax
0x180003301  jnz     short loc_180003308
0x180003303  jmp     loc_1800036F6
0x180003308  lea     rax, [rsp+260h+var_1F8]
0x18000330d  mov     [rsp+260h+ppv], rax; ppv
0x180003312  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180003319  mov     r12d, 1
0x18000331f  mov     r8d, r12d; dwClsContext
0x180003322  xor     edx, edx; pUnkOuter
0x180003324  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000332b  call    cs:__imp_CoCreateInstance
0x180003331  test    eax, eax
0x180003333  jns     loc_1800033B9
0x180003339  jmp     loc_1800036DF
0x18000333e  mov     rax, [rdi+8]
0x180003342  movups  xmm0, xmmword ptr [rax]
0x180003345  movdqu  [rbp+160h+var_1C8], xmm0
0x18000334a  lea     r9, [rbp+160h+var_1C8]
0x18000334e  mov     r8d, r12d
0x180003351  mov     rdx, rbx
0x180003354  test    r14d, r14d
0x180003357  jz      short loc_180003399
0x180003359  cmp     ecx, r12d
0x18000335c  mov     rcx, [rsp+260h+var_1F8]
0x180003361  mov     rax, [rcx]
0x180003364  jnz     short loc_18000336C
0x180003366  mov     rax, [rax+28h]
0x18000336a  jmp     short loc_180003370
0x18000336c  mov     rax, [rax+38h]
0x180003370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003375  mov     esi, eax
0x180003377  test    eax, eax
0x180003379  jns     short loc_1800033B5
0x18000337b  mov     rcx, [rsp+260h+var_1F8]
0x180003380  test    rcx, rcx
0x180003383  jz      short loc_180003392
0x180003385  mov     rax, [rcx]
0x180003388  mov     rax, [rax+10h]
0x18000338c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003391  nop
0x180003392  mov     eax, esi
0x180003394  jmp     loc_1800036F8
0x180003399  cmp     ecx, r12d
0x18000339c  mov     rcx, [rsp+260h+var_1F8]
0x1800033a1  mov     rax, [rcx]
0x1800033a4  jnz     short loc_1800033AC
0x1800033a6  mov     rax, [rax+30h]
0x1800033aa  jmp     short loc_1800033B0
0x1800033ac  mov     rax, [rax+40h]
0x1800033b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033b5  add     rdi, 10h
0x1800033b9  mov     ecx, [rdi]
0x1800033bb  test    ecx, ecx
0x1800033bd  jnz     loc_18000333E
0x1800033c3  test    r14d, r14d
0x1800033c6  jnz     loc_1800036DF
0x1800033cc  lea     r8d, [rcx+40h]; cchMax
0x1800033d0  lea     rdx, [rbp+160h+sz]; lpsz
0x1800033d7  mov     rcx, rbx; rguid
0x1800033da  call    cs:__imp_StringFromGUID2
0x1800033e0  lea     r8, aClsid; "CLSID\\"
0x1800033e7  mov     ebx, 80h
0x1800033ec  mov     edx, ebx; SizeInWords
0x1800033ee  lea     rcx, [rbp+160h+Destination]; Destination
0x1800033f2  call    cs:__imp_wcscpy_s
0x1800033f8  lea     r14d, [rbx-74h]
0x1800033fc  lea     r12d, [rbx-30h]
0x180003400  test    eax, eax
0x180003402  jz      short loc_180003428
0x180003404  cmp     eax, r14d
0x180003407  jz      loc_180003723
0x18000340d  cmp     eax, 16h
0x180003410  jz      loc_180003739
0x180003416  cmp     eax, 22h ; '"'
0x180003419  jz      loc_180003739
0x18000341f  cmp     eax, r12d
0x180003422  jnz     loc_18000372E
0x180003428  lea     r8, [rbp+160h+sz]; Source
0x18000342f  mov     rdx, rbx; SizeInWords
0x180003432  lea     rcx, [rbp+160h+Destination]; Destination
0x180003436  call    cs:__imp_wcscat_s
0x18000343c  test    eax, eax
0x18000343e  jz      short loc_180003464
0x180003440  cmp     eax, r14d
0x180003443  jz      loc_180003723
0x180003449  cmp     eax, 16h
0x18000344c  jz      loc_180003739
0x180003452  cmp     eax, 22h ; '"'
0x180003455  jz      loc_180003739
0x18000345b  cmp     eax, r12d
0x18000345e  jnz     loc_18000372E
0x180003464  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000346b  mov     rdx, rbx; SizeInWords
0x18000346e  lea     rcx, [rbp+160h+Destination]; Destination
0x180003472  call    cs:__imp_wcscat_s
0x180003478  test    eax, eax
0x18000347a  jz      short loc_1800034A0
0x18000347c  cmp     eax, r14d
0x18000347f  jz      loc_180003723
0x180003485  cmp     eax, 16h
0x180003488  jz      loc_180003739
0x18000348e  cmp     eax, 22h ; '"'
0x180003491  jz      loc_180003739
0x180003497  cmp     eax, r12d
0x18000349a  jnz     loc_18000372E
0x1800034a0  mov     rdi, 0FFFFFFFF80000000h
0x1800034a7  mov     [rbp+160h+var_1E0], rdi
0x1800034ab  mov     [rbp+160h+var_1D8], r15
0x1800034af  mov     [rbp+160h+var_1D0], r15
0x1800034b3  mov     rbx, r15
0x1800034b6  mov     [rsp+260h+cSubKeys], r15d
0x1800034bb  mov     [rsp+260h+phkResult], r15
0x1800034c0  lea     rax, [rsp+260h+phkResult]
0x1800034c5  mov     [rsp+260h+ppv], rax; phkResult
0x1800034ca  mov     r9d, 20019h; samDesired
0x1800034d0  xor     r8d, r8d; ulOptions
0x1800034d3  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x1800034d7  mov     rcx, rdi; hKey
0x1800034da  call    cs:__imp_RegOpenKeyExW
0x1800034e0  test    eax, eax
0x1800034e2  jnz     short loc_180003556
0x1800034e4  mov     rbx, [rsp+260h+phkResult]
0x1800034e9  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800034ee  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800034f3  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800034f8  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800034fd  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180003502  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003507  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000350c  lea     rax, [rsp+260h+cSubKeys]
0x180003511  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180003516  xor     r9d, r9d; lpReserved
0x180003519  xor     r8d, r8d; lpcchClass
0x18000351c  xor     edx, edx; lpClass
0x18000351e  mov     rcx, rbx; hKey
0x180003521  call    cs:__imp_RegQueryInfoKeyW
0x180003527  mov     esi, eax
0x180003529  test    rbx, rbx
0x18000352c  jz      short loc_18000353A
0x18000352e  mov     rcx, rbx; hKey
0x180003531  call    cs:__imp_RegCloseKey
0x180003537  mov     rbx, r15
0x18000353a  test    esi, esi
0x18000353c  jnz     short loc_180003556
0x18000353e  cmp     [rsp+260h+cSubKeys], r15d
0x180003543  jnz     short loc_180003556
0x180003545  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180003549  lea     rcx, [rbp+160h+var_1E0]; this
0x18000354d  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003552  mov     rdi, [rbp+160h+var_1E0]
0x180003556  lea     r8, aClsid; "CLSID\\"
0x18000355d  mov     esi, 80h
0x180003562  mov     edx, esi; SizeInWords
0x180003564  lea     rcx, [rbp+160h+Destination]; Destination
0x180003568  call    cs:__imp_wcscpy_s
0x18000356e  test    eax, eax
0x180003570  jz      short loc_180003596
0x180003572  cmp     eax, r14d
0x180003575  jz      loc_180003723
0x18000357b  cmp     eax, 16h
0x18000357e  jz      loc_180003739
0x180003584  cmp     eax, 22h ; '"'
0x180003587  jz      loc_180003739
0x18000358d  cmp     eax, r12d
0x180003590  jnz     loc_18000372E
0x180003596  lea     r8, [rbp+160h+sz]; Source
0x18000359d  mov     rdx, rsi; SizeInWords
0x1800035a0  lea     rcx, [rbp+160h+Destination]; Destination
0x1800035a4  call    cs:__imp_wcscat_s
0x1800035aa  test    eax, eax
0x1800035ac  jz      short loc_1800035D2
0x1800035ae  cmp     eax, r14d
0x1800035b1  jz      loc_180003723
0x1800035b7  cmp     eax, 16h
0x1800035ba  jz      loc_180003739
0x1800035c0  cmp     eax, 22h ; '"'
0x1800035c3  jz      loc_180003739
0x1800035c9  cmp     eax, r12d
0x1800035cc  jnz     loc_18000372E
0x1800035d2  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800035d9  mov     rdx, rsi; SizeInWords
0x1800035dc  lea     rcx, [rbp+160h+Destination]; Destination
0x1800035e0  call    cs:__imp_wcscat_s
0x1800035e6  test    eax, eax
0x1800035e8  jz      short loc_18000360E
0x1800035ea  cmp     eax, r14d
0x1800035ed  jz      loc_180003723
0x1800035f3  cmp     eax, 16h
0x1800035f6  jz      loc_180003739
0x1800035fc  cmp     eax, 22h ; '"'
0x1800035ff  jz      loc_180003739
0x180003605  cmp     eax, r12d
0x180003608  jnz     loc_18000372E
0x18000360e  mov     [rsp+260h+hKey], r15
0x180003613  lea     rax, [rsp+260h+hKey]
0x180003618  mov     [rsp+260h+ppv], rax; phkResult
0x18000361d  mov     r9d, 20019h; samDesired
0x180003623  xor     r8d, r8d; ulOptions
0x180003626  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x18000362a  mov     rcx, rdi; hKey
0x18000362d  call    cs:__imp_RegOpenKeyExW
0x180003633  test    eax, eax
0x180003635  jnz     loc_1800036C2
0x18000363b  mov     eax, r15d
0x18000363e  test    rbx, rbx
0x180003641  jz      short loc_18000364C
0x180003643  mov     rcx, rbx; hKey
0x180003646  call    cs:__imp_RegCloseKey
0x18000364c  mov     rbx, [rsp+260h+hKey]
0x180003651  test    eax, eax
0x180003653  jnz     short loc_1800036C2
0x180003655  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000365a  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000365f  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003664  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003669  mov     [rsp+260h+lpcValues], r15; lpcValues
0x18000366e  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003673  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003678  lea     rax, [rsp+260h+cSubKeys]
0x18000367d  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180003682  xor     r9d, r9d; lpReserved
0x180003685  xor     r8d, r8d; lpcchClass
0x180003688  xor     edx, edx; lpClass
0x18000368a  mov     rcx, rbx; hKey
0x18000368d  call    cs:__imp_RegQueryInfoKeyW
0x180003693  mov     esi, eax
0x180003695  test    rbx, rbx
0x180003698  jz      short loc_1800036A6
0x18000369a  mov     rcx, rbx; hKey
0x18000369d  call    cs:__imp_RegCloseKey
0x1800036a3  mov     rbx, r15
0x1800036a6  test    esi, esi
0x1800036a8  jnz     short loc_1800036D0
0x1800036aa  cmp     [rsp+260h+cSubKeys], r15d
0x1800036af  jnz     short loc_1800036C2
0x1800036b1  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800036b5  lea     rcx, [rbp+160h+var_1E0]; this
0x1800036b9  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800036be  mov     rdi, [rbp+160h+var_1E0]
0x1800036c2  test    rbx, rbx
0x1800036c5  jz      short loc_1800036D0
0x1800036c7  mov     rcx, rbx; hKey
0x1800036ca  call    cs:__imp_RegCloseKey
0x1800036d0  test    rdi, rdi
0x1800036d3  jz      short loc_1800036DF
0x1800036d5  mov     rcx, rdi; hKey
0x1800036d8  call    cs:__imp_RegCloseKey
0x1800036de  nop
0x1800036df  mov     rcx, [rsp+260h+var_1F8]
0x1800036e4  test    rcx, rcx
0x1800036e7  jz      short loc_1800036F6
0x1800036e9  mov     rax, [rcx]
0x1800036ec  mov     rax, [rax+10h]
0x1800036f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f5  nop
0x1800036f6  xor     eax, eax
0x1800036f8  mov     rcx, [rbp+160h+var_30]
0x1800036ff  xor     rcx, rsp; StackCookie
0x180003702  call    __security_check_cookie
0x180003707  lea     r11, [rsp+260h+var_20]
0x18000370f  mov     rbx, [r11+40h]
0x180003713  mov     rsi, [r11+48h]
0x180003717  mov     rsp, r11
0x18000371a  pop     r15
0x18000371c  pop     r14
0x18000371e  pop     r12
0x180003720  pop     rdi
0x180003721  pop     rbp
  ... truncated ...
```
