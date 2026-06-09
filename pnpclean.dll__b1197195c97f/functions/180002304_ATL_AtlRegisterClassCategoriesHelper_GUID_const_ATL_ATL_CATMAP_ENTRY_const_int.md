# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x180002304`
- end: `0x1800027b8`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1204`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002b60`
- `0x180002c20`

## callees

- `0x180002304`
- `0x1800027c0`
- `0x1800027e8`
- `0x180008e30`
- `0x18000a010`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800024ac`
- `msvcrt!wcscat_s` at `0x1800024e8`
- `msvcrt!wcscat_s` at `0x18000261a`
- `msvcrt!wcscat_s` at `0x180002656`
- `msvcrt!wcscat_s` at `0x1800024ac`
- `msvcrt!wcscat_s` at `0x1800024e8`
- `msvcrt!wcscat_s` at `0x18000261a`
- `msvcrt!wcscat_s` at `0x180002656`
- `msvcrt!wcscpy_s` at `0x180002468`
- `msvcrt!wcscpy_s` at `0x1800025de`
- `msvcrt!wcscpy_s` at `0x180002468`
- `msvcrt!wcscpy_s` at `0x1800025de`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002597`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002703`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002597`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180002703`
- `ADVAPI32!RegOpenKeyExW` at `0x180002550`
- `ADVAPI32!RegOpenKeyExW` at `0x1800026a3`
- `ADVAPI32!RegOpenKeyExW` at `0x180002550`
- `ADVAPI32!RegOpenKeyExW` at `0x1800026a3`
- `ADVAPI32!RegCloseKey` at `0x1800025a7`
- `ADVAPI32!RegCloseKey` at `0x1800026bc`
- `ADVAPI32!RegCloseKey` at `0x180002713`
- `ADVAPI32!RegCloseKey` at `0x180002740`
- `ADVAPI32!RegCloseKey` at `0x18000274e`
- `ADVAPI32!RegCloseKey` at `0x1800025a7`
- `ADVAPI32!RegCloseKey` at `0x1800026bc`
- `ADVAPI32!RegCloseKey` at `0x180002713`
- `ADVAPI32!RegCloseKey` at `0x180002740`
- `ADVAPI32!RegCloseKey` at `0x18000274e`
- `ole32!CoCreateInstance` at `0x1800023a9`
- `ole32!CoCreateInstance` at `0x1800023a9`
- `ole32!StringFromGUID2` at `0x180002450`
- `ole32!StringFromGUID2` at `0x180002450`

## string_xrefs

- `0x18000245b`: `CLSID\`
- `0x1800025d1`: `CLSID\`

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
0x180002304  mov     [rsp-8+arg_10], rbx
0x180002309  mov     [rsp-8+arg_18], rsi
0x18000230e  push    rbp
0x18000230f  push    rdi
0x180002310  push    r12
0x180002312  push    r14
0x180002314  push    r15
0x180002316  lea     rbp, [rsp-140h]
0x18000231e  sub     rsp, 240h
0x180002325  mov     rax, cs:__security_cookie
0x18000232c  xor     rax, rsp
0x18000232f  mov     [rbp+160h+var_30], rax
0x180002336  xor     r15d, r15d
0x180002339  xorps   xmm0, xmm0
0x18000233c  mov     [rsp+260h+var_1F8], r15
0x180002341  mov     r14d, r8d
0x180002344  mov     rdi, rdx
0x180002347  mov     rbx, rcx
0x18000234a  movups  [rbp+160h+var_1C8], xmm0
0x18000234e  test    rdx, rdx
0x180002351  jz      loc_18000276A
0x180002357  mov     eax, cs:GUID_NULL.Data1
0x18000235d  cmp     [rcx], eax
0x18000235f  jnz     short loc_180002386
0x180002361  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180002367  cmp     [rcx+4], eax
0x18000236a  jnz     short loc_180002386
0x18000236c  mov     eax, dword ptr cs:GUID_NULL.Data4
0x180002372  cmp     [rcx+8], eax
0x180002375  jnz     short loc_180002386
0x180002377  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x18000237d  cmp     [rcx+0Ch], eax
0x180002380  jz      loc_18000276A
0x180002386  lea     rax, [rsp+260h+var_1F8]
0x18000238b  mov     r12d, 1
0x180002391  mov     r8d, r12d; dwClsContext
0x180002394  mov     [rsp+260h+ppv], rax; ppv
0x180002399  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1800023a0  xor     edx, edx; pUnkOuter
0x1800023a2  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1800023a9  call    cs:__imp_CoCreateInstance
0x1800023af  test    eax, eax
0x1800023b1  js      loc_180002754
0x1800023b7  jmp     short loc_180002433
0x1800023b9  mov     rax, [rdi+8]
0x1800023bd  lea     r9, [rbp+160h+var_1C8]
0x1800023c1  mov     r8d, r12d
0x1800023c4  mov     rdx, rbx
0x1800023c7  movups  xmm0, xmmword ptr [rax]
0x1800023ca  movdqu  [rbp+160h+var_1C8], xmm0
0x1800023cf  test    r14d, r14d
0x1800023d2  jz      short loc_180002413
0x1800023d4  cmp     ecx, r12d
0x1800023d7  mov     rcx, [rsp+260h+var_1F8]
0x1800023dc  mov     rax, [rcx]
0x1800023df  jnz     short loc_1800023E7
0x1800023e1  mov     rax, [rax+28h]
0x1800023e5  jmp     short loc_1800023EB
0x1800023e7  mov     rax, [rax+38h]
0x1800023eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023f0  mov     esi, eax
0x1800023f2  test    eax, eax
0x1800023f4  jns     short loc_18000242F
0x1800023f6  mov     rcx, [rsp+260h+var_1F8]
0x1800023fb  test    rcx, rcx
0x1800023fe  jz      short loc_18000240C
0x180002400  mov     rax, [rcx]
0x180002403  mov     rax, [rax+10h]
0x180002407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000240c  mov     eax, esi
0x18000240e  jmp     loc_18000276C
0x180002413  cmp     ecx, r12d
0x180002416  mov     rcx, [rsp+260h+var_1F8]
0x18000241b  mov     rax, [rcx]
0x18000241e  jnz     short loc_180002426
0x180002420  mov     rax, [rax+30h]
0x180002424  jmp     short loc_18000242A
0x180002426  mov     rax, [rax+40h]
0x18000242a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000242f  add     rdi, 10h
0x180002433  mov     ecx, [rdi]
0x180002435  test    ecx, ecx
0x180002437  jnz     short loc_1800023B9
0x180002439  test    r14d, r14d
0x18000243c  jnz     loc_180002754
0x180002442  lea     r8d, [rcx+40h]; cchMax
0x180002446  mov     rcx, rbx; rguid
0x180002449  lea     rdx, [rbp+160h+sz]; lpsz
0x180002450  call    cs:__imp_StringFromGUID2
0x180002456  mov     ebx, 80h
0x18000245b  lea     r8, aClsid; "CLSID\\"
0x180002462  mov     edx, ebx; SizeInWords
0x180002464  lea     rcx, [rbp+160h+Destination]; Destination
0x180002468  call    cs:__imp_wcscpy_s
0x18000246e  lea     r14d, [rbx-74h]
0x180002472  lea     r12d, [rbx-30h]
0x180002476  test    eax, eax
0x180002478  jz      short loc_18000249E
0x18000247a  cmp     eax, r14d
0x18000247d  jz      loc_180002797
0x180002483  cmp     eax, 16h
0x180002486  jz      loc_1800027AD
0x18000248c  cmp     eax, 22h ; '"'
0x18000248f  jz      loc_1800027AD
0x180002495  cmp     eax, r12d
0x180002498  jnz     loc_1800027A2
0x18000249e  lea     r8, [rbp+160h+sz]; Source
0x1800024a5  mov     rdx, rbx; SizeInWords
0x1800024a8  lea     rcx, [rbp+160h+Destination]; Destination
0x1800024ac  call    cs:__imp_wcscat_s
0x1800024b2  test    eax, eax
0x1800024b4  jz      short loc_1800024DA
0x1800024b6  cmp     eax, r14d
0x1800024b9  jz      loc_180002797
0x1800024bf  cmp     eax, 16h
0x1800024c2  jz      loc_1800027AD
0x1800024c8  cmp     eax, 22h ; '"'
0x1800024cb  jz      loc_1800027AD
0x1800024d1  cmp     eax, r12d
0x1800024d4  jnz     loc_1800027A2
0x1800024da  lea     r8, aRequiredCatego; "\\Required Categories"
0x1800024e1  mov     rdx, rbx; SizeInWords
0x1800024e4  lea     rcx, [rbp+160h+Destination]; Destination
0x1800024e8  call    cs:__imp_wcscat_s
0x1800024ee  test    eax, eax
0x1800024f0  jz      short loc_180002516
0x1800024f2  cmp     eax, r14d
0x1800024f5  jz      loc_180002797
0x1800024fb  cmp     eax, 16h
0x1800024fe  jz      loc_1800027AD
0x180002504  cmp     eax, 22h ; '"'
0x180002507  jz      loc_1800027AD
0x18000250d  cmp     eax, r12d
0x180002510  jnz     loc_1800027A2
0x180002516  mov     rdi, 0FFFFFFFF80000000h
0x18000251d  mov     [rbp+160h+var_1D8], r15
0x180002521  lea     rax, [rsp+260h+phkResult]
0x180002526  mov     [rbp+160h+var_1E0], rdi
0x18000252a  mov     rcx, rdi; hKey
0x18000252d  mov     [rbp+160h+var_1D0], r15
0x180002531  mov     r9d, 20019h; samDesired
0x180002537  mov     [rsp+260h+cSubKeys], r15d
0x18000253c  xor     r8d, r8d; ulOptions
0x18000253f  mov     [rsp+260h+phkResult], r15
0x180002544  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180002548  mov     [rsp+260h+ppv], rax; phkResult
0x18000254d  mov     rbx, r15
0x180002550  call    cs:__imp_RegOpenKeyExW
0x180002556  test    eax, eax
0x180002558  jnz     short loc_1800025CC
0x18000255a  mov     rbx, [rsp+260h+phkResult]
0x18000255f  lea     rax, [rsp+260h+cSubKeys]
0x180002564  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180002569  xor     r9d, r9d; lpReserved
0x18000256c  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180002571  xor     r8d, r8d; lpcchClass
0x180002574  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180002579  xor     edx, edx; lpClass
0x18000257b  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180002580  mov     rcx, rbx; hKey
0x180002583  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180002588  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18000258d  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180002592  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180002597  call    cs:__imp_RegQueryInfoKeyW
0x18000259d  mov     esi, eax
0x18000259f  test    rbx, rbx
0x1800025a2  jz      short loc_1800025B0
0x1800025a4  mov     rcx, rbx; hKey
0x1800025a7  call    cs:__imp_RegCloseKey
0x1800025ad  mov     rbx, r15
0x1800025b0  test    esi, esi
0x1800025b2  jnz     short loc_1800025CC
0x1800025b4  cmp     [rsp+260h+cSubKeys], r15d
0x1800025b9  jnz     short loc_1800025CC
0x1800025bb  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800025bf  lea     rcx, [rbp+160h+var_1E0]; this
0x1800025c3  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800025c8  mov     rdi, [rbp+160h+var_1E0]
0x1800025cc  mov     esi, 80h
0x1800025d1  lea     r8, aClsid; "CLSID\\"
0x1800025d8  mov     edx, esi; SizeInWords
0x1800025da  lea     rcx, [rbp+160h+Destination]; Destination
0x1800025de  call    cs:__imp_wcscpy_s
0x1800025e4  test    eax, eax
0x1800025e6  jz      short loc_18000260C
0x1800025e8  cmp     eax, r14d
0x1800025eb  jz      loc_180002797
0x1800025f1  cmp     eax, 16h
0x1800025f4  jz      loc_1800027AD
0x1800025fa  cmp     eax, 22h ; '"'
0x1800025fd  jz      loc_1800027AD
0x180002603  cmp     eax, r12d
0x180002606  jnz     loc_1800027A2
0x18000260c  lea     r8, [rbp+160h+sz]; Source
0x180002613  mov     rdx, rsi; SizeInWords
0x180002616  lea     rcx, [rbp+160h+Destination]; Destination
0x18000261a  call    cs:__imp_wcscat_s
0x180002620  test    eax, eax
0x180002622  jz      short loc_180002648
0x180002624  cmp     eax, r14d
0x180002627  jz      loc_180002797
0x18000262d  cmp     eax, 16h
0x180002630  jz      loc_1800027AD
0x180002636  cmp     eax, 22h ; '"'
0x180002639  jz      loc_1800027AD
0x18000263f  cmp     eax, r12d
0x180002642  jnz     loc_1800027A2
0x180002648  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000264f  mov     rdx, rsi; SizeInWords
0x180002652  lea     rcx, [rbp+160h+Destination]; Destination
0x180002656  call    cs:__imp_wcscat_s
0x18000265c  test    eax, eax
0x18000265e  jz      short loc_180002684
0x180002660  cmp     eax, r14d
0x180002663  jz      loc_180002797
0x180002669  cmp     eax, 16h
0x18000266c  jz      loc_1800027AD
0x180002672  cmp     eax, 22h ; '"'
0x180002675  jz      loc_1800027AD
0x18000267b  cmp     eax, r12d
0x18000267e  jnz     loc_1800027A2
0x180002684  lea     rax, [rsp+260h+hKey]
0x180002689  mov     [rsp+260h+hKey], r15
0x18000268e  mov     r9d, 20019h; samDesired
0x180002694  mov     [rsp+260h+ppv], rax; phkResult
0x180002699  xor     r8d, r8d; ulOptions
0x18000269c  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x1800026a0  mov     rcx, rdi; hKey
0x1800026a3  call    cs:__imp_RegOpenKeyExW
0x1800026a9  test    eax, eax
0x1800026ab  jnz     loc_180002738
0x1800026b1  mov     eax, r15d
0x1800026b4  test    rbx, rbx
0x1800026b7  jz      short loc_1800026C2
0x1800026b9  mov     rcx, rbx; hKey
0x1800026bc  call    cs:__imp_RegCloseKey
0x1800026c2  mov     rbx, [rsp+260h+hKey]
0x1800026c7  test    eax, eax
0x1800026c9  jnz     short loc_180002738
0x1800026cb  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800026d0  lea     rax, [rsp+260h+cSubKeys]
0x1800026d5  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800026da  xor     r9d, r9d; lpReserved
0x1800026dd  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800026e2  xor     r8d, r8d; lpcchClass
0x1800026e5  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800026ea  xor     edx, edx; lpClass
0x1800026ec  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800026f1  mov     rcx, rbx; hKey
0x1800026f4  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800026f9  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800026fe  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180002703  call    cs:__imp_RegQueryInfoKeyW
0x180002709  mov     esi, eax
0x18000270b  test    rbx, rbx
0x18000270e  jz      short loc_18000271C
0x180002710  mov     rcx, rbx; hKey
0x180002713  call    cs:__imp_RegCloseKey
0x180002719  mov     rbx, r15
0x18000271c  test    esi, esi
0x18000271e  jnz     short loc_180002746
0x180002720  cmp     [rsp+260h+cSubKeys], r15d
0x180002725  jnz     short loc_180002738
0x180002727  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x18000272b  lea     rcx, [rbp+160h+var_1E0]; this
0x18000272f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180002734  mov     rdi, [rbp+160h+var_1E0]
0x180002738  test    rbx, rbx
0x18000273b  jz      short loc_180002746
0x18000273d  mov     rcx, rbx; hKey
0x180002740  call    cs:__imp_RegCloseKey
0x180002746  test    rdi, rdi
0x180002749  jz      short loc_180002754
0x18000274b  mov     rcx, rdi; hKey
0x18000274e  call    cs:__imp_RegCloseKey
0x180002754  mov     rcx, [rsp+260h+var_1F8]
0x180002759  test    rcx, rcx
0x18000275c  jz      short loc_18000276A
0x18000275e  mov     rax, [rcx]
0x180002761  mov     rax, [rax+10h]
0x180002765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000276a  xor     eax, eax
0x18000276c  mov     rcx, [rbp+160h+var_30]
0x180002773  xor     rcx, rsp; StackCookie
0x180002776  call    __security_check_cookie
0x18000277b  lea     r11, [rsp+260h+var_20]
0x180002783  mov     rbx, [r11+40h]
0x180002787  mov     rsi, [r11+48h]
0x18000278b  mov     rsp, r11
0x18000278e  pop     r15
0x180002790  pop     r14
0x180002792  pop     r12
0x180002794  pop     rdi
0x180002795  pop     rbp
0x180002796  retn
0x180002797  mov     ecx, 8007000Eh; int
0x18000279c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800027a2  mov     ecx, 80004005h; int
0x1800027a7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
  ... truncated ...
```
