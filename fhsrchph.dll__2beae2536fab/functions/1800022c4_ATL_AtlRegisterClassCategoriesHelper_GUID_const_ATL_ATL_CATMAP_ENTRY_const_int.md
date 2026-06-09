# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800022c4`
- end: `0x180002784`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1216`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002c70`
- `0x180002d30`

## callees

- `0x1800022c4`
- `0x18000278c`
- `0x1800027b4`
- `0x18000ab60`
- `0x18000c010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180002476`
- `msvcrt!wcscat_s` at `0x1800024b2`
- `msvcrt!wcscat_s` at `0x1800025e4`
- `msvcrt!wcscat_s` at `0x180002620`
- `msvcrt!wcscat_s` at `0x180002476`
- `msvcrt!wcscat_s` at `0x1800024b2`
- `msvcrt!wcscat_s` at `0x1800025e4`
- `msvcrt!wcscat_s` at `0x180002620`
- `msvcrt!wcscpy_s` at `0x180002432`
- `msvcrt!wcscpy_s` at `0x1800025a8`
- `msvcrt!wcscpy_s` at `0x180002432`
- `msvcrt!wcscpy_s` at `0x1800025a8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000251a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000266d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000251a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000266d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002561`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800026cd`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002561`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800026cd`
- `ADVAPI32!RegCloseKey` at `0x180002571`
- `ADVAPI32!RegCloseKey` at `0x180002686`
- `ADVAPI32!RegCloseKey` at `0x1800026dd`
- `ADVAPI32!RegCloseKey` at `0x18000270a`
- `ADVAPI32!RegCloseKey` at `0x180002718`
- `ADVAPI32!RegCloseKey` at `0x180002571`
- `ADVAPI32!RegCloseKey` at `0x180002686`
- `ADVAPI32!RegCloseKey` at `0x1800026dd`
- `ADVAPI32!RegCloseKey` at `0x18000270a`
- `ADVAPI32!RegCloseKey` at `0x180002718`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000236b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000236b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000241a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000241a`

## string_xrefs

- `0x180002420`: `CLSID\`
- `0x180002596`: `CLSID\`

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
0x1800022c4  mov     [rsp-8+arg_10], rbx
0x1800022c9  mov     [rsp-8+arg_18], rsi
0x1800022ce  push    rbp
0x1800022cf  push    rdi
0x1800022d0  push    r12
0x1800022d2  push    r14
0x1800022d4  push    r15
0x1800022d6  lea     rbp, [rsp-140h]
0x1800022de  sub     rsp, 240h
0x1800022e5  mov     rax, cs:__security_cookie
0x1800022ec  xor     rax, rsp
0x1800022ef  mov     [rbp+160h+var_30], rax
0x1800022f6  mov     r14d, r8d
0x1800022f9  mov     rdi, rdx
0x1800022fc  mov     rbx, rcx
0x1800022ff  xor     r15d, r15d
0x180002302  mov     [rsp+260h+var_1F8], r15
0x180002307  xorps   xmm0, xmm0
0x18000230a  movups  [rbp+160h+var_1C8], xmm0
0x18000230e  test    rdx, rdx
0x180002311  jnz     short loc_180002318
0x180002313  jmp     loc_180002736
0x180002318  mov     eax, cs:GUID_NULL.Data1
0x18000231e  cmp     [rcx], eax
0x180002320  jnz     short loc_180002348
0x180002322  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180002328  cmp     [rcx+4], eax
0x18000232b  jnz     short loc_180002348
0x18000232d  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180002333  cmp     [rcx+8], eax
0x180002336  jnz     short loc_180002348
0x180002338  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000233e  cmp     [rcx+0Ch], eax
0x180002341  jnz     short loc_180002348
0x180002343  jmp     loc_180002736
0x180002348  lea     rax, [rsp+260h+var_1F8]
0x18000234d  mov     [rsp+260h+ppv], rax; ppv
0x180002352  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180002359  mov     r12d, 1
0x18000235f  mov     r8d, r12d; dwClsContext
0x180002362  xor     edx, edx; pUnkOuter
0x180002364  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x18000236b  call    cs:__imp_CoCreateInstance
0x180002371  test    eax, eax
0x180002373  jns     loc_1800023F9
0x180002379  jmp     loc_18000271F
0x18000237e  mov     rax, [rdi+8]
0x180002382  movups  xmm0, xmmword ptr [rax]
0x180002385  movdqu  [rbp+160h+var_1C8], xmm0
0x18000238a  lea     r9, [rbp+160h+var_1C8]
0x18000238e  mov     r8d, r12d
0x180002391  mov     rdx, rbx
0x180002394  test    r14d, r14d
0x180002397  jz      short loc_1800023D9
0x180002399  cmp     ecx, r12d
0x18000239c  mov     rcx, [rsp+260h+var_1F8]
0x1800023a1  mov     rax, [rcx]
0x1800023a4  jnz     short loc_1800023AC
0x1800023a6  mov     rax, [rax+28h]
0x1800023aa  jmp     short loc_1800023B0
0x1800023ac  mov     rax, [rax+38h]
0x1800023b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023b5  mov     esi, eax
0x1800023b7  test    eax, eax
0x1800023b9  jns     short loc_1800023F5
0x1800023bb  mov     rcx, [rsp+260h+var_1F8]
0x1800023c0  test    rcx, rcx
0x1800023c3  jz      short loc_1800023D2
0x1800023c5  mov     rax, [rcx]
0x1800023c8  mov     rax, [rax+10h]
0x1800023cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023d1  nop
0x1800023d2  mov     eax, esi
0x1800023d4  jmp     loc_180002738
0x1800023d9  cmp     ecx, r12d
0x1800023dc  mov     rcx, [rsp+260h+var_1F8]
0x1800023e1  mov     rax, [rcx]
0x1800023e4  jnz     short loc_1800023EC
0x1800023e6  mov     rax, [rax+30h]
0x1800023ea  jmp     short loc_1800023F0
0x1800023ec  mov     rax, [rax+40h]
0x1800023f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f5  add     rdi, 10h
0x1800023f9  mov     ecx, [rdi]
0x1800023fb  test    ecx, ecx
0x1800023fd  jnz     loc_18000237E
0x180002403  test    r14d, r14d
0x180002406  jnz     loc_18000271F
0x18000240c  lea     r8d, [rcx+40h]; cchMax
0x180002410  lea     rdx, [rbp+160h+sz]; lpsz
0x180002417  mov     rcx, rbx; rguid
0x18000241a  call    cs:__imp_StringFromGUID2
0x180002420  lea     r8, aClsid; "CLSID\\"
0x180002427  mov     ebx, 80h
0x18000242c  mov     edx, ebx; SizeInWords
0x18000242e  lea     rcx, [rbp+160h+Destination]; Destination
0x180002432  call    cs:__imp_wcscpy_s
0x180002438  lea     r14d, [rbx-74h]
0x18000243c  lea     r12d, [rbx-30h]
0x180002440  test    eax, eax
0x180002442  jz      short loc_180002468
0x180002444  cmp     eax, r14d
0x180002447  jz      loc_180002763
0x18000244d  cmp     eax, 16h
0x180002450  jz      loc_180002779
0x180002456  cmp     eax, 22h ; '"'
0x180002459  jz      loc_180002779
0x18000245f  cmp     eax, r12d
0x180002462  jnz     loc_18000276E
0x180002468  lea     r8, [rbp+160h+sz]; Source
0x18000246f  mov     rdx, rbx; SizeInWords
0x180002472  lea     rcx, [rbp+160h+Destination]; Destination
0x180002476  call    cs:__imp_wcscat_s
0x18000247c  test    eax, eax
0x18000247e  jz      short loc_1800024A4
0x180002480  cmp     eax, r14d
0x180002483  jz      loc_180002763
0x180002489  cmp     eax, 16h
0x18000248c  jz      loc_180002779
0x180002492  cmp     eax, 22h ; '"'
0x180002495  jz      loc_180002779
0x18000249b  cmp     eax, r12d
0x18000249e  jnz     loc_18000276E
0x1800024a4  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800024ab  mov     rdx, rbx; SizeInWords
0x1800024ae  lea     rcx, [rbp+160h+Destination]; Destination
0x1800024b2  call    cs:__imp_wcscat_s
0x1800024b8  test    eax, eax
0x1800024ba  jz      short loc_1800024E0
0x1800024bc  cmp     eax, r14d
0x1800024bf  jz      loc_180002763
0x1800024c5  cmp     eax, 16h
0x1800024c8  jz      loc_180002779
0x1800024ce  cmp     eax, 22h ; '"'
0x1800024d1  jz      loc_180002779
0x1800024d7  cmp     eax, r12d
0x1800024da  jnz     loc_18000276E
0x1800024e0  mov     rdi, 0FFFFFFFF80000000h
0x1800024e7  mov     [rbp+160h+var_1E0], rdi
0x1800024eb  mov     [rbp+160h+var_1D8], r15
0x1800024ef  mov     [rbp+160h+var_1D0], r15
0x1800024f3  mov     rbx, r15
0x1800024f6  mov     [rsp+260h+cSubKeys], r15d
0x1800024fb  mov     [rsp+260h+phkResult], r15
0x180002500  lea     rax, [rsp+260h+phkResult]
0x180002505  mov     [rsp+260h+ppv], rax; phkResult
0x18000250a  mov     r9d, 20019h; samDesired
0x180002510  xor     r8d, r8d; ulOptions
0x180002513  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180002517  mov     rcx, rdi; hKey
0x18000251a  call    cs:__imp_RegOpenKeyExW
0x180002520  test    eax, eax
0x180002522  jnz     short loc_180002596
0x180002524  mov     rbx, [rsp+260h+phkResult]
0x180002529  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000252e  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180002533  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180002538  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000253d  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180002542  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180002547  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000254c  lea     rax, [rsp+260h+cSubKeys]
0x180002551  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180002556  xor     r9d, r9d; lpReserved
0x180002559  xor     r8d, r8d; lpcchClass
0x18000255c  xor     edx, edx; lpClass
0x18000255e  mov     rcx, rbx; hKey
0x180002561  call    cs:__imp_RegQueryInfoKeyW
0x180002567  mov     esi, eax
0x180002569  test    rbx, rbx
0x18000256c  jz      short loc_18000257A
0x18000256e  mov     rcx, rbx; hKey
0x180002571  call    cs:__imp_RegCloseKey
0x180002577  mov     rbx, r15
0x18000257a  test    esi, esi
0x18000257c  jnz     short loc_180002596
0x18000257e  cmp     [rsp+260h+cSubKeys], r15d
0x180002583  jnz     short loc_180002596
0x180002585  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180002589  lea     rcx, [rbp+160h+var_1E0]; this
0x18000258d  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180002592  mov     rdi, [rbp+160h+var_1E0]
0x180002596  lea     r8, aClsid; "CLSID\\"
0x18000259d  mov     esi, 80h
0x1800025a2  mov     edx, esi; SizeInWords
0x1800025a4  lea     rcx, [rbp+160h+Destination]; Destination
0x1800025a8  call    cs:__imp_wcscpy_s
0x1800025ae  test    eax, eax
0x1800025b0  jz      short loc_1800025D6
0x1800025b2  cmp     eax, r14d
0x1800025b5  jz      loc_180002763
0x1800025bb  cmp     eax, 16h
0x1800025be  jz      loc_180002779
0x1800025c4  cmp     eax, 22h ; '"'
0x1800025c7  jz      loc_180002779
0x1800025cd  cmp     eax, r12d
0x1800025d0  jnz     loc_18000276E
0x1800025d6  lea     r8, [rbp+160h+sz]; Source
0x1800025dd  mov     rdx, rsi; SizeInWords
0x1800025e0  lea     rcx, [rbp+160h+Destination]; Destination
0x1800025e4  call    cs:__imp_wcscat_s
0x1800025ea  test    eax, eax
0x1800025ec  jz      short loc_180002612
0x1800025ee  cmp     eax, r14d
0x1800025f1  jz      loc_180002763
0x1800025f7  cmp     eax, 16h
0x1800025fa  jz      loc_180002779
0x180002600  cmp     eax, 22h ; '"'
0x180002603  jz      loc_180002779
0x180002609  cmp     eax, r12d
0x18000260c  jnz     loc_18000276E
0x180002612  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180002619  mov     rdx, rsi; SizeInWords
0x18000261c  lea     rcx, [rbp+160h+Destination]; Destination
0x180002620  call    cs:__imp_wcscat_s
0x180002626  test    eax, eax
0x180002628  jz      short loc_18000264E
0x18000262a  cmp     eax, r14d
0x18000262d  jz      loc_180002763
0x180002633  cmp     eax, 16h
0x180002636  jz      loc_180002779
0x18000263c  cmp     eax, 22h ; '"'
0x18000263f  jz      loc_180002779
0x180002645  cmp     eax, r12d
0x180002648  jnz     loc_18000276E
0x18000264e  mov     [rsp+260h+hKey], r15
0x180002653  lea     rax, [rsp+260h+hKey]
0x180002658  mov     [rsp+260h+ppv], rax; phkResult
0x18000265d  mov     r9d, 20019h; samDesired
0x180002663  xor     r8d, r8d; ulOptions
0x180002666  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x18000266a  mov     rcx, rdi; hKey
0x18000266d  call    cs:__imp_RegOpenKeyExW
0x180002673  test    eax, eax
0x180002675  jnz     loc_180002702
0x18000267b  mov     eax, r15d
0x18000267e  test    rbx, rbx
0x180002681  jz      short loc_18000268C
0x180002683  mov     rcx, rbx; hKey
0x180002686  call    cs:__imp_RegCloseKey
0x18000268c  mov     rbx, [rsp+260h+hKey]
0x180002691  test    eax, eax
0x180002693  jnz     short loc_180002702
0x180002695  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000269a  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000269f  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800026a4  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800026a9  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800026ae  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800026b3  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800026b8  lea     rax, [rsp+260h+cSubKeys]
0x1800026bd  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800026c2  xor     r9d, r9d; lpReserved
0x1800026c5  xor     r8d, r8d; lpcchClass
0x1800026c8  xor     edx, edx; lpClass
0x1800026ca  mov     rcx, rbx; hKey
0x1800026cd  call    cs:__imp_RegQueryInfoKeyW
0x1800026d3  mov     esi, eax
0x1800026d5  test    rbx, rbx
0x1800026d8  jz      short loc_1800026E6
0x1800026da  mov     rcx, rbx; hKey
0x1800026dd  call    cs:__imp_RegCloseKey
0x1800026e3  mov     rbx, r15
0x1800026e6  test    esi, esi
0x1800026e8  jnz     short loc_180002710
0x1800026ea  cmp     [rsp+260h+cSubKeys], r15d
0x1800026ef  jnz     short loc_180002702
0x1800026f1  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800026f5  lea     rcx, [rbp+160h+var_1E0]; this
0x1800026f9  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800026fe  mov     rdi, [rbp+160h+var_1E0]
0x180002702  test    rbx, rbx
0x180002705  jz      short loc_180002710
0x180002707  mov     rcx, rbx; hKey
0x18000270a  call    cs:__imp_RegCloseKey
0x180002710  test    rdi, rdi
0x180002713  jz      short loc_18000271F
0x180002715  mov     rcx, rdi; hKey
0x180002718  call    cs:__imp_RegCloseKey
0x18000271e  nop
0x18000271f  mov     rcx, [rsp+260h+var_1F8]
0x180002724  test    rcx, rcx
0x180002727  jz      short loc_180002736
0x180002729  mov     rax, [rcx]
0x18000272c  mov     rax, [rax+10h]
0x180002730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002735  nop
0x180002736  xor     eax, eax
0x180002738  mov     rcx, [rbp+160h+var_30]
0x18000273f  xor     rcx, rsp; StackCookie
0x180002742  call    __security_check_cookie
0x180002747  lea     r11, [rsp+260h+var_20]
0x18000274f  mov     rbx, [r11+40h]
0x180002753  mov     rsi, [r11+48h]
0x180002757  mov     rsp, r11
0x18000275a  pop     r15
0x18000275c  pop     r14
0x18000275e  pop     r12
0x180002760  pop     rdi
0x180002761  pop     rbp
  ... truncated ...
```
