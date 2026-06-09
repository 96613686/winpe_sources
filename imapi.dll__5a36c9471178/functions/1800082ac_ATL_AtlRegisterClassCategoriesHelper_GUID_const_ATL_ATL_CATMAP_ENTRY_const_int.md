# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800082ac`
- end: `0x180008760`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1204`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009e00`
- `0x180009f20`

## callees

- `0x180002ac4`
- `0x180002e78`
- `0x1800082ac`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180008454`
- `msvcrt!wcscat_s` at `0x180008490`
- `msvcrt!wcscat_s` at `0x1800085c2`
- `msvcrt!wcscat_s` at `0x1800085fe`
- `msvcrt!wcscat_s` at `0x180008454`
- `msvcrt!wcscat_s` at `0x180008490`
- `msvcrt!wcscat_s` at `0x1800085c2`
- `msvcrt!wcscat_s` at `0x1800085fe`
- `msvcrt!wcscpy_s` at `0x180008410`
- `msvcrt!wcscpy_s` at `0x180008586`
- `msvcrt!wcscpy_s` at `0x180008410`
- `msvcrt!wcscpy_s` at `0x180008586`
- `ADVAPI32!RegCloseKey` at `0x18000854f`
- `ADVAPI32!RegCloseKey` at `0x180008664`
- `ADVAPI32!RegCloseKey` at `0x1800086bb`
- `ADVAPI32!RegCloseKey` at `0x1800086e8`
- `ADVAPI32!RegCloseKey` at `0x1800086f6`
- `ADVAPI32!RegCloseKey` at `0x18000854f`
- `ADVAPI32!RegCloseKey` at `0x180008664`
- `ADVAPI32!RegCloseKey` at `0x1800086bb`
- `ADVAPI32!RegCloseKey` at `0x1800086e8`
- `ADVAPI32!RegCloseKey` at `0x1800086f6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000853f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800086ab`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000853f`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800086ab`
- `ADVAPI32!RegOpenKeyExW` at `0x1800084f8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000864b`
- `ADVAPI32!RegOpenKeyExW` at `0x1800084f8`
- `ADVAPI32!RegOpenKeyExW` at `0x18000864b`
- `ole32!StringFromGUID2` at `0x1800083f8`
- `ole32!StringFromGUID2` at `0x1800083f8`
- `ole32!CoCreateInstance` at `0x180008351`
- `ole32!CoCreateInstance` at `0x180008351`

## string_xrefs

- `0x180008403`: `CLSID\`
- `0x180008579`: `CLSID\`

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
0x1800082ac  mov     [rsp-8+arg_10], rbx
0x1800082b1  mov     [rsp-8+arg_18], rsi
0x1800082b6  push    rbp
0x1800082b7  push    rdi
0x1800082b8  push    r12
0x1800082ba  push    r14
0x1800082bc  push    r15
0x1800082be  lea     rbp, [rsp-140h]
0x1800082c6  sub     rsp, 240h
0x1800082cd  mov     rax, cs:__security_cookie
0x1800082d4  xor     rax, rsp
0x1800082d7  mov     [rbp+160h+var_30], rax
0x1800082de  xor     r15d, r15d
0x1800082e1  xorps   xmm0, xmm0
0x1800082e4  mov     [rsp+260h+var_1F8], r15
0x1800082e9  mov     r14d, r8d
0x1800082ec  mov     rdi, rdx
0x1800082ef  mov     rbx, rcx
0x1800082f2  movups  [rbp+160h+var_1C8], xmm0
0x1800082f6  test    rdx, rdx
0x1800082f9  jz      loc_180008712
0x1800082ff  mov     eax, cs:GUID_NULL.Data1
0x180008305  cmp     [rcx], eax
0x180008307  jnz     short loc_18000832E
0x180008309  mov     eax, dword ptr cs:GUID_NULL.Data2
0x18000830f  cmp     [rcx+4], eax
0x180008312  jnz     short loc_18000832E
0x180008314  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000831a  cmp     [rcx+8], eax
0x18000831d  jnz     short loc_18000832E
0x18000831f  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180008325  cmp     [rcx+0Ch], eax
0x180008328  jz      loc_180008712
0x18000832e  lea     rax, [rsp+260h+var_1F8]
0x180008333  mov     r12d, 1
0x180008339  mov     r8d, r12d; dwClsContext
0x18000833c  mov     [rsp+260h+ppv], rax; ppv
0x180008341  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180008348  xor     edx, edx; pUnkOuter
0x18000834a  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180008351  call    cs:__imp_CoCreateInstance
0x180008357  test    eax, eax
0x180008359  js      loc_1800086FC
0x18000835f  jmp     short loc_1800083DB
0x180008361  mov     rax, [rdi+8]
0x180008365  lea     r9, [rbp+160h+var_1C8]
0x180008369  mov     r8d, r12d
0x18000836c  mov     rdx, rbx
0x18000836f  movups  xmm0, xmmword ptr [rax]
0x180008372  movdqu  [rbp+160h+var_1C8], xmm0
0x180008377  test    r14d, r14d
0x18000837a  jz      short loc_1800083BB
0x18000837c  cmp     ecx, r12d
0x18000837f  mov     rcx, [rsp+260h+var_1F8]
0x180008384  mov     rax, [rcx]
0x180008387  jnz     short loc_18000838F
0x180008389  mov     rax, [rax+28h]
0x18000838d  jmp     short loc_180008393
0x18000838f  mov     rax, [rax+38h]
0x180008393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008398  mov     esi, eax
0x18000839a  test    eax, eax
0x18000839c  jns     short loc_1800083D7
0x18000839e  mov     rcx, [rsp+260h+var_1F8]
0x1800083a3  test    rcx, rcx
0x1800083a6  jz      short loc_1800083B4
0x1800083a8  mov     rax, [rcx]
0x1800083ab  mov     rax, [rax+10h]
0x1800083af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083b4  mov     eax, esi
0x1800083b6  jmp     loc_180008714
0x1800083bb  cmp     ecx, r12d
0x1800083be  mov     rcx, [rsp+260h+var_1F8]
0x1800083c3  mov     rax, [rcx]
0x1800083c6  jnz     short loc_1800083CE
0x1800083c8  mov     rax, [rax+30h]
0x1800083cc  jmp     short loc_1800083D2
0x1800083ce  mov     rax, [rax+40h]
0x1800083d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d7  add     rdi, 10h
0x1800083db  mov     ecx, [rdi]
0x1800083dd  test    ecx, ecx
0x1800083df  jnz     short loc_180008361
0x1800083e1  test    r14d, r14d
0x1800083e4  jnz     loc_1800086FC
0x1800083ea  lea     r8d, [rcx+40h]; cchMax
0x1800083ee  mov     rcx, rbx; rguid
0x1800083f1  lea     rdx, [rbp+160h+sz]; lpsz
0x1800083f8  call    cs:__imp_StringFromGUID2
0x1800083fe  mov     ebx, 80h
0x180008403  lea     r8, aClsid; "CLSID\\"
0x18000840a  mov     edx, ebx; SizeInWords
0x18000840c  lea     rcx, [rbp+160h+Destination]; Destination
0x180008410  call    cs:__imp_wcscpy_s
0x180008416  lea     r14d, [rbx-74h]
0x18000841a  lea     r12d, [rbx-30h]
0x18000841e  test    eax, eax
0x180008420  jz      short loc_180008446
0x180008422  cmp     eax, r14d
0x180008425  jz      loc_18000873F
0x18000842b  cmp     eax, 16h
0x18000842e  jz      loc_180008755
0x180008434  cmp     eax, 22h ; '"'
0x180008437  jz      loc_180008755
0x18000843d  cmp     eax, r12d
0x180008440  jnz     loc_18000874A
0x180008446  lea     r8, [rbp+160h+sz]; Source
0x18000844d  mov     rdx, rbx; SizeInWords
0x180008450  lea     rcx, [rbp+160h+Destination]; Destination
0x180008454  call    cs:__imp_wcscat_s
0x18000845a  test    eax, eax
0x18000845c  jz      short loc_180008482
0x18000845e  cmp     eax, r14d
0x180008461  jz      loc_18000873F
0x180008467  cmp     eax, 16h
0x18000846a  jz      loc_180008755
0x180008470  cmp     eax, 22h ; '"'
0x180008473  jz      loc_180008755
0x180008479  cmp     eax, r12d
0x18000847c  jnz     loc_18000874A
0x180008482  lea     r8, aRequiredCatego; "\\Required Categories"
0x180008489  mov     rdx, rbx; SizeInWords
0x18000848c  lea     rcx, [rbp+160h+Destination]; Destination
0x180008490  call    cs:__imp_wcscat_s
0x180008496  test    eax, eax
0x180008498  jz      short loc_1800084BE
0x18000849a  cmp     eax, r14d
0x18000849d  jz      loc_18000873F
0x1800084a3  cmp     eax, 16h
0x1800084a6  jz      loc_180008755
0x1800084ac  cmp     eax, 22h ; '"'
0x1800084af  jz      loc_180008755
0x1800084b5  cmp     eax, r12d
0x1800084b8  jnz     loc_18000874A
0x1800084be  mov     rdi, 0FFFFFFFF80000000h
0x1800084c5  mov     [rbp+160h+var_1D8], r15
0x1800084c9  lea     rax, [rsp+260h+phkResult]
0x1800084ce  mov     [rbp+160h+var_1E0], rdi
0x1800084d2  mov     rcx, rdi; hKey
0x1800084d5  mov     [rbp+160h+var_1D0], r15
0x1800084d9  mov     r9d, 20019h; samDesired
0x1800084df  mov     [rsp+260h+cSubKeys], r15d
0x1800084e4  xor     r8d, r8d; ulOptions
0x1800084e7  mov     [rsp+260h+phkResult], r15
0x1800084ec  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x1800084f0  mov     [rsp+260h+ppv], rax; phkResult
0x1800084f5  mov     rbx, r15
0x1800084f8  call    cs:__imp_RegOpenKeyExW
0x1800084fe  test    eax, eax
0x180008500  jnz     short loc_180008574
0x180008502  mov     rbx, [rsp+260h+phkResult]
0x180008507  lea     rax, [rsp+260h+cSubKeys]
0x18000850c  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180008511  xor     r9d, r9d; lpReserved
0x180008514  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180008519  xor     r8d, r8d; lpcchClass
0x18000851c  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180008521  xor     edx, edx; lpClass
0x180008523  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180008528  mov     rcx, rbx; hKey
0x18000852b  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180008530  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180008535  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000853a  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x18000853f  call    cs:__imp_RegQueryInfoKeyW
0x180008545  mov     esi, eax
0x180008547  test    rbx, rbx
0x18000854a  jz      short loc_180008558
0x18000854c  mov     rcx, rbx; hKey
0x18000854f  call    cs:__imp_RegCloseKey
0x180008555  mov     rbx, r15
0x180008558  test    esi, esi
0x18000855a  jnz     short loc_180008574
0x18000855c  cmp     [rsp+260h+cSubKeys], r15d
0x180008561  jnz     short loc_180008574
0x180008563  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x180008567  lea     rcx, [rbp+160h+var_1E0]; this
0x18000856b  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180008570  mov     rdi, [rbp+160h+var_1E0]
0x180008574  mov     esi, 80h
0x180008579  lea     r8, aClsid; "CLSID\\"
0x180008580  mov     edx, esi; SizeInWords
0x180008582  lea     rcx, [rbp+160h+Destination]; Destination
0x180008586  call    cs:__imp_wcscpy_s
0x18000858c  test    eax, eax
0x18000858e  jz      short loc_1800085B4
0x180008590  cmp     eax, r14d
0x180008593  jz      loc_18000873F
0x180008599  cmp     eax, 16h
0x18000859c  jz      loc_180008755
0x1800085a2  cmp     eax, 22h ; '"'
0x1800085a5  jz      loc_180008755
0x1800085ab  cmp     eax, r12d
0x1800085ae  jnz     loc_18000874A
0x1800085b4  lea     r8, [rbp+160h+sz]; Source
0x1800085bb  mov     rdx, rsi; SizeInWords
0x1800085be  lea     rcx, [rbp+160h+Destination]; Destination
0x1800085c2  call    cs:__imp_wcscat_s
0x1800085c8  test    eax, eax
0x1800085ca  jz      short loc_1800085F0
0x1800085cc  cmp     eax, r14d
0x1800085cf  jz      loc_18000873F
0x1800085d5  cmp     eax, 16h
0x1800085d8  jz      loc_180008755
0x1800085de  cmp     eax, 22h ; '"'
0x1800085e1  jz      loc_180008755
0x1800085e7  cmp     eax, r12d
0x1800085ea  jnz     loc_18000874A
0x1800085f0  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1800085f7  mov     rdx, rsi; SizeInWords
0x1800085fa  lea     rcx, [rbp+160h+Destination]; Destination
0x1800085fe  call    cs:__imp_wcscat_s
0x180008604  test    eax, eax
0x180008606  jz      short loc_18000862C
0x180008608  cmp     eax, r14d
0x18000860b  jz      loc_18000873F
0x180008611  cmp     eax, 16h
0x180008614  jz      loc_180008755
0x18000861a  cmp     eax, 22h ; '"'
0x18000861d  jz      loc_180008755
0x180008623  cmp     eax, r12d
0x180008626  jnz     loc_18000874A
0x18000862c  lea     rax, [rsp+260h+hKey]
0x180008631  mov     [rsp+260h+hKey], r15
0x180008636  mov     r9d, 20019h; samDesired
0x18000863c  mov     [rsp+260h+ppv], rax; phkResult
0x180008641  xor     r8d, r8d; ulOptions
0x180008644  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180008648  mov     rcx, rdi; hKey
0x18000864b  call    cs:__imp_RegOpenKeyExW
0x180008651  test    eax, eax
0x180008653  jnz     loc_1800086E0
0x180008659  mov     eax, r15d
0x18000865c  test    rbx, rbx
0x18000865f  jz      short loc_18000866A
0x180008661  mov     rcx, rbx; hKey
0x180008664  call    cs:__imp_RegCloseKey
0x18000866a  mov     rbx, [rsp+260h+hKey]
0x18000866f  test    eax, eax
0x180008671  jnz     short loc_1800086E0
0x180008673  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180008678  lea     rax, [rsp+260h+cSubKeys]
0x18000867d  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180008682  xor     r9d, r9d; lpReserved
0x180008685  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000868a  xor     r8d, r8d; lpcchClass
0x18000868d  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180008692  xor     edx, edx; lpClass
0x180008694  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180008699  mov     rcx, rbx; hKey
0x18000869c  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800086a1  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800086a6  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800086ab  call    cs:__imp_RegQueryInfoKeyW
0x1800086b1  mov     esi, eax
0x1800086b3  test    rbx, rbx
0x1800086b6  jz      short loc_1800086C4
0x1800086b8  mov     rcx, rbx; hKey
0x1800086bb  call    cs:__imp_RegCloseKey
0x1800086c1  mov     rbx, r15
0x1800086c4  test    esi, esi
0x1800086c6  jnz     short loc_1800086EE
0x1800086c8  cmp     [rsp+260h+cSubKeys], r15d
0x1800086cd  jnz     short loc_1800086E0
0x1800086cf  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800086d3  lea     rcx, [rbp+160h+var_1E0]; this
0x1800086d7  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800086dc  mov     rdi, [rbp+160h+var_1E0]
0x1800086e0  test    rbx, rbx
0x1800086e3  jz      short loc_1800086EE
0x1800086e5  mov     rcx, rbx; hKey
0x1800086e8  call    cs:__imp_RegCloseKey
0x1800086ee  test    rdi, rdi
0x1800086f1  jz      short loc_1800086FC
0x1800086f3  mov     rcx, rdi; hKey
0x1800086f6  call    cs:__imp_RegCloseKey
0x1800086fc  mov     rcx, [rsp+260h+var_1F8]
0x180008701  test    rcx, rcx
0x180008704  jz      short loc_180008712
0x180008706  mov     rax, [rcx]
0x180008709  mov     rax, [rax+10h]
0x18000870d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008712  xor     eax, eax
0x180008714  mov     rcx, [rbp+160h+var_30]
0x18000871b  xor     rcx, rsp; StackCookie
0x18000871e  call    __security_check_cookie
0x180008723  lea     r11, [rsp+260h+var_20]
0x18000872b  mov     rbx, [r11+40h]
0x18000872f  mov     rsi, [r11+48h]
0x180008733  mov     rsp, r11
0x180008736  pop     r15
0x180008738  pop     r14
0x18000873a  pop     r12
0x18000873c  pop     rdi
0x18000873d  pop     rbp
0x18000873e  retn
0x18000873f  mov     ecx, 8007000Eh; int
0x180008744  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000874a  mov     ecx, 80004005h; int
0x18000874f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
  ... truncated ...
```
