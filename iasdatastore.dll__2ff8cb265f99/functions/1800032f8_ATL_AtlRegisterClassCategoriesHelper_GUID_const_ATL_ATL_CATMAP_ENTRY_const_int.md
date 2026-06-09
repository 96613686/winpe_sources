# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800032f8`
- end: `0x1800037b8`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800064c0`
- `0x180006610`

## callees

- `0x1800032f8`
- `0x1800039a4`
- `0x1800040c8`
- `0x18000dd10`
- `0x180010010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180003466`
- `msvcrt!wcscpy_s` at `0x1800035dc`
- `msvcrt!wcscpy_s` at `0x180003466`
- `msvcrt!wcscpy_s` at `0x1800035dc`
- `msvcrt!wcscat_s` at `0x1800034aa`
- `msvcrt!wcscat_s` at `0x1800034e6`
- `msvcrt!wcscat_s` at `0x180003618`
- `msvcrt!wcscat_s` at `0x180003654`
- `msvcrt!wcscat_s` at `0x1800034aa`
- `msvcrt!wcscat_s` at `0x1800034e6`
- `msvcrt!wcscat_s` at `0x180003618`
- `msvcrt!wcscat_s` at `0x180003654`
- `ADVAPI32!RegOpenKeyExW` at `0x18000354e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800036a1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000354e`
- `ADVAPI32!RegOpenKeyExW` at `0x1800036a1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003595`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003701`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003595`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180003701`
- `ADVAPI32!RegCloseKey` at `0x1800035a5`
- `ADVAPI32!RegCloseKey` at `0x1800036ba`
- `ADVAPI32!RegCloseKey` at `0x180003711`
- `ADVAPI32!RegCloseKey` at `0x18000373e`
- `ADVAPI32!RegCloseKey` at `0x18000374c`
- `ADVAPI32!RegCloseKey` at `0x1800035a5`
- `ADVAPI32!RegCloseKey` at `0x1800036ba`
- `ADVAPI32!RegCloseKey` at `0x180003711`
- `ADVAPI32!RegCloseKey` at `0x18000373e`
- `ADVAPI32!RegCloseKey` at `0x18000374c`
- `ole32!StringFromGUID2` at `0x18000344e`
- `ole32!StringFromGUID2` at `0x18000344e`
- `ole32!CoCreateInstance` at `0x18000339f`
- `ole32!CoCreateInstance` at `0x18000339f`

## string_xrefs

- `0x180003454`: `CLSID\`
- `0x1800035ca`: `CLSID\`

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
0x1800032f8  mov     [rsp-8+arg_10], rbx
0x1800032fd  mov     [rsp-8+arg_18], rsi
0x180003302  push    rbp
0x180003303  push    rdi
0x180003304  push    r12
0x180003306  push    r14
0x180003308  push    r15
0x18000330a  lea     rbp, [rsp-140h]
0x180003312  sub     rsp, 240h
0x180003319  mov     rax, cs:__security_cookie
0x180003320  xor     rax, rsp
0x180003323  mov     [rbp+160h+var_30], rax
0x18000332a  mov     r14d, r8d
0x18000332d  mov     rdi, rdx
0x180003330  mov     rbx, rcx
0x180003333  xor     r15d, r15d
0x180003336  mov     [rsp+260h+var_1F8], r15
0x18000333b  xorps   xmm0, xmm0
0x18000333e  movups  [rbp+160h+var_1C8], xmm0
0x180003342  test    rdx, rdx
0x180003345  jnz     short loc_18000334C
0x180003347  jmp     loc_18000376A
0x18000334c  mov     eax, cs:GUID_NULL.Data1
0x180003352  cmp     [rcx], eax
0x180003354  jnz     short loc_18000337C
0x180003356  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000335c  cmp     [rcx+4], eax
0x18000335f  jnz     short loc_18000337C
0x180003361  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180003367  cmp     [rcx+8], eax
0x18000336a  jnz     short loc_18000337C
0x18000336c  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180003372  cmp     [rcx+0Ch], eax
0x180003375  jnz     short loc_18000337C
0x180003377  jmp     loc_18000376A
0x18000337c  lea     rax, [rsp+260h+var_1F8]
0x180003381  mov     [rsp+260h+ppv], rax; ppv
0x180003386  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000338d  mov     r12d, 1
0x180003393  mov     r8d, r12d; dwClsContext
0x180003396  xor     edx, edx; pUnkOuter
0x180003398  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000339f  call    cs:__imp_CoCreateInstance
0x1800033a5  test    eax, eax
0x1800033a7  jns     loc_18000342D
0x1800033ad  jmp     loc_180003753
0x1800033b2  mov     rax, [rdi+8]
0x1800033b6  movups  xmm0, xmmword ptr [rax]
0x1800033b9  movdqu  [rbp+160h+var_1C8], xmm0
0x1800033be  lea     r9, [rbp+160h+var_1C8]
0x1800033c2  mov     r8d, r12d
0x1800033c5  mov     rdx, rbx
0x1800033c8  test    r14d, r14d
0x1800033cb  jz      short loc_18000340D
0x1800033cd  cmp     ecx, r12d
0x1800033d0  mov     rcx, [rsp+260h+var_1F8]
0x1800033d5  mov     rax, [rcx]
0x1800033d8  jnz     short loc_1800033E0
0x1800033da  mov     rax, [rax+28h]
0x1800033de  jmp     short loc_1800033E4
0x1800033e0  mov     rax, [rax+38h]
0x1800033e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033e9  mov     esi, eax
0x1800033eb  test    eax, eax
0x1800033ed  jns     short loc_180003429
0x1800033ef  mov     rcx, [rsp+260h+var_1F8]
0x1800033f4  test    rcx, rcx
0x1800033f7  jz      short loc_180003406
0x1800033f9  mov     rax, [rcx]
0x1800033fc  mov     rax, [rax+10h]
0x180003400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003405  nop
0x180003406  mov     eax, esi
0x180003408  jmp     loc_18000376C
0x18000340d  cmp     ecx, r12d
0x180003410  mov     rcx, [rsp+260h+var_1F8]
0x180003415  mov     rax, [rcx]
0x180003418  jnz     short loc_180003420
0x18000341a  mov     rax, [rax+30h]
0x18000341e  jmp     short loc_180003424
0x180003420  mov     rax, [rax+40h]
0x180003424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003429  add     rdi, 10h
0x18000342d  mov     ecx, [rdi]
0x18000342f  test    ecx, ecx
0x180003431  jnz     loc_1800033B2
0x180003437  test    r14d, r14d
0x18000343a  jnz     loc_180003753
0x180003440  lea     r8d, [rcx+40h]; cchMax
0x180003444  lea     rdx, [rbp+160h+sz]; lpsz
0x18000344b  mov     rcx, rbx; rguid
0x18000344e  call    cs:__imp_StringFromGUID2
0x180003454  lea     r8, aClsid; "CLSID\\"
0x18000345b  mov     ebx, 80h
0x180003460  mov     edx, ebx; SizeInWords
0x180003462  lea     rcx, [rbp+160h+Destination]; Destination
0x180003466  call    cs:__imp_wcscpy_s
0x18000346c  lea     r14d, [rbx-74h]
0x180003470  lea     r12d, [rbx-30h]
0x180003474  test    eax, eax
0x180003476  jz      short loc_18000349C
0x180003478  cmp     eax, r14d
0x18000347b  jz      loc_180003797
0x180003481  cmp     eax, 16h
0x180003484  jz      loc_1800037AD
0x18000348a  cmp     eax, 22h ; '"'
0x18000348d  jz      loc_1800037AD
0x180003493  cmp     eax, r12d
0x180003496  jnz     loc_1800037A2
0x18000349c  lea     r8, [rbp+160h+sz]; Source
0x1800034a3  mov     rdx, rbx; SizeInWords
0x1800034a6  lea     rcx, [rbp+160h+Destination]; Destination
0x1800034aa  call    cs:__imp_wcscat_s
0x1800034b0  test    eax, eax
0x1800034b2  jz      short loc_1800034D8
0x1800034b4  cmp     eax, r14d
0x1800034b7  jz      loc_180003797
0x1800034bd  cmp     eax, 16h
0x1800034c0  jz      loc_1800037AD
0x1800034c6  cmp     eax, 22h ; '"'
0x1800034c9  jz      loc_1800037AD
0x1800034cf  cmp     eax, r12d
0x1800034d2  jnz     loc_1800037A2
0x1800034d8  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800034df  mov     rdx, rbx; SizeInWords
0x1800034e2  lea     rcx, [rbp+160h+Destination]; Destination
0x1800034e6  call    cs:__imp_wcscat_s
0x1800034ec  test    eax, eax
0x1800034ee  jz      short loc_180003514
0x1800034f0  cmp     eax, r14d
0x1800034f3  jz      loc_180003797
0x1800034f9  cmp     eax, 16h
0x1800034fc  jz      loc_1800037AD
0x180003502  cmp     eax, 22h ; '"'
0x180003505  jz      loc_1800037AD
0x18000350b  cmp     eax, r12d
0x18000350e  jnz     loc_1800037A2
0x180003514  mov     rdi, 0FFFFFFFF80000000h
0x18000351b  mov     [rbp+160h+var_1E0], rdi
0x18000351f  mov     [rbp+160h+var_1D8], r15
0x180003523  mov     [rbp+160h+var_1D0], r15
0x180003527  mov     rbx, r15
0x18000352a  mov     [rsp+260h+cSubKeys], r15d
0x18000352f  mov     [rsp+260h+phkResult], r15
0x180003534  lea     rax, [rsp+260h+phkResult]
0x180003539  mov     [rsp+260h+ppv], rax; phkResult
0x18000353e  mov     r9d, 20019h; samDesired
0x180003544  xor     r8d, r8d; ulOptions
0x180003547  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x18000354b  mov     rcx, rdi; hKey
0x18000354e  call    cs:__imp_RegOpenKeyExW
0x180003554  test    eax, eax
0x180003556  jnz     short loc_1800035CA
0x180003558  mov     rbx, [rsp+260h+phkResult]
0x18000355d  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003562  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003567  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000356c  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180003571  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180003576  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000357b  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180003580  lea     rax, [rsp+260h+cSubKeys]
0x180003585  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000358a  xor     r9d, r9d; lpReserved
0x18000358d  xor     r8d, r8d; lpcchClass
0x180003590  xor     edx, edx; lpClass
0x180003592  mov     rcx, rbx; hKey
0x180003595  call    cs:__imp_RegQueryInfoKeyW
0x18000359b  mov     esi, eax
0x18000359d  test    rbx, rbx
0x1800035a0  jz      short loc_1800035AE
0x1800035a2  mov     rcx, rbx; hKey
0x1800035a5  call    cs:__imp_RegCloseKey
0x1800035ab  mov     rbx, r15
0x1800035ae  test    esi, esi
0x1800035b0  jnz     short loc_1800035CA
0x1800035b2  cmp     [rsp+260h+cSubKeys], r15d
0x1800035b7  jnz     short loc_1800035CA
0x1800035b9  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800035bd  lea     rcx, [rbp+160h+var_1E0]; this
0x1800035c1  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800035c6  mov     rdi, [rbp+160h+var_1E0]
0x1800035ca  lea     r8, aClsid; "CLSID\\"
0x1800035d1  mov     esi, 80h
0x1800035d6  mov     edx, esi; SizeInWords
0x1800035d8  lea     rcx, [rbp+160h+Destination]; Destination
0x1800035dc  call    cs:__imp_wcscpy_s
0x1800035e2  test    eax, eax
0x1800035e4  jz      short loc_18000360A
0x1800035e6  cmp     eax, r14d
0x1800035e9  jz      loc_180003797
0x1800035ef  cmp     eax, 16h
0x1800035f2  jz      loc_1800037AD
0x1800035f8  cmp     eax, 22h ; '"'
0x1800035fb  jz      loc_1800037AD
0x180003601  cmp     eax, r12d
0x180003604  jnz     loc_1800037A2
0x18000360a  lea     r8, [rbp+160h+sz]; Source
0x180003611  mov     rdx, rsi; SizeInWords
0x180003614  lea     rcx, [rbp+160h+Destination]; Destination
0x180003618  call    cs:__imp_wcscat_s
0x18000361e  test    eax, eax
0x180003620  jz      short loc_180003646
0x180003622  cmp     eax, r14d
0x180003625  jz      loc_180003797
0x18000362b  cmp     eax, 16h
0x18000362e  jz      loc_1800037AD
0x180003634  cmp     eax, 22h ; '"'
0x180003637  jz      loc_1800037AD
0x18000363d  cmp     eax, r12d
0x180003640  jnz     loc_1800037A2
0x180003646  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000364d  mov     rdx, rsi; SizeInWords
0x180003650  lea     rcx, [rbp+160h+Destination]; Destination
0x180003654  call    cs:__imp_wcscat_s
0x18000365a  test    eax, eax
0x18000365c  jz      short loc_180003682
0x18000365e  cmp     eax, r14d
0x180003661  jz      loc_180003797
0x180003667  cmp     eax, 16h
0x18000366a  jz      loc_1800037AD
0x180003670  cmp     eax, 22h ; '"'
0x180003673  jz      loc_1800037AD
0x180003679  cmp     eax, r12d
0x18000367c  jnz     loc_1800037A2
0x180003682  mov     [rsp+260h+hKey], r15
0x180003687  lea     rax, [rsp+260h+hKey]
0x18000368c  mov     [rsp+260h+ppv], rax; phkResult
0x180003691  mov     r9d, 20019h; samDesired
0x180003697  xor     r8d, r8d; ulOptions
0x18000369a  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x18000369e  mov     rcx, rdi; hKey
0x1800036a1  call    cs:__imp_RegOpenKeyExW
0x1800036a7  test    eax, eax
0x1800036a9  jnz     loc_180003736
0x1800036af  mov     eax, r15d
0x1800036b2  test    rbx, rbx
0x1800036b5  jz      short loc_1800036C0
0x1800036b7  mov     rcx, rbx; hKey
0x1800036ba  call    cs:__imp_RegCloseKey
0x1800036c0  mov     rbx, [rsp+260h+hKey]
0x1800036c5  test    eax, eax
0x1800036c7  jnz     short loc_180003736
0x1800036c9  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800036ce  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800036d3  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800036d8  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800036dd  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800036e2  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800036e7  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800036ec  lea     rax, [rsp+260h+cSubKeys]
0x1800036f1  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800036f6  xor     r9d, r9d; lpReserved
0x1800036f9  xor     r8d, r8d; lpcchClass
0x1800036fc  xor     edx, edx; lpClass
0x1800036fe  mov     rcx, rbx; hKey
0x180003701  call    cs:__imp_RegQueryInfoKeyW
0x180003707  mov     esi, eax
0x180003709  test    rbx, rbx
0x18000370c  jz      short loc_18000371A
0x18000370e  mov     rcx, rbx; hKey
0x180003711  call    cs:__imp_RegCloseKey
0x180003717  mov     rbx, r15
0x18000371a  test    esi, esi
0x18000371c  jnz     short loc_180003744
0x18000371e  cmp     [rsp+260h+cSubKeys], r15d
0x180003723  jnz     short loc_180003736
0x180003725  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180003729  lea     rcx, [rbp+160h+var_1E0]; this
0x18000372d  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003732  mov     rdi, [rbp+160h+var_1E0]
0x180003736  test    rbx, rbx
0x180003739  jz      short loc_180003744
0x18000373b  mov     rcx, rbx; hKey
0x18000373e  call    cs:__imp_RegCloseKey
0x180003744  test    rdi, rdi
0x180003747  jz      short loc_180003753
0x180003749  mov     rcx, rdi; hKey
0x18000374c  call    cs:__imp_RegCloseKey
0x180003752  nop
0x180003753  mov     rcx, [rsp+260h+var_1F8]
0x180003758  test    rcx, rcx
0x18000375b  jz      short loc_18000376A
0x18000375d  mov     rax, [rcx]
0x180003760  mov     rax, [rax+10h]
0x180003764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003769  nop
0x18000376a  xor     eax, eax
0x18000376c  mov     rcx, [rbp+160h+var_30]
0x180003773  xor     rcx, rsp; StackCookie
0x180003776  call    __security_check_cookie
0x18000377b  lea     r11, [rsp+260h+var_20]
0x180003783  mov     rbx, [r11+40h]
0x180003787  mov     rsi, [r11+48h]
0x18000378b  mov     rsp, r11
0x18000378e  pop     r15
0x180003790  pop     r14
0x180003792  pop     r12
0x180003794  pop     rdi
0x180003795  pop     rbp
  ... truncated ...
```
