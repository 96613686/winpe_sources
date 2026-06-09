# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800034c0`
- end: `0x180003974`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `1204`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180005d50`
- `0x180005e70`

## callees

- `0x1800034c0`
- `0x18000397c`
- `0x180003d68`
- `0x180006030`
- `0x180007010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180003624`
- `msvcrt!wcscpy_s` at `0x18000379a`
- `msvcrt!wcscpy_s` at `0x180003624`
- `msvcrt!wcscpy_s` at `0x18000379a`
- `msvcrt!wcscat_s` at `0x180003668`
- `msvcrt!wcscat_s` at `0x1800036a4`
- `msvcrt!wcscat_s` at `0x1800037d6`
- `msvcrt!wcscat_s` at `0x180003812`
- `msvcrt!wcscat_s` at `0x180003668`
- `msvcrt!wcscat_s` at `0x1800036a4`
- `msvcrt!wcscat_s` at `0x1800037d6`
- `msvcrt!wcscat_s` at `0x180003812`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003565`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003565`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000360c`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000360c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000370c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000385f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000370c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000385f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003753`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800038bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180003753`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800038bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003763`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003878`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800038cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800038fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000390a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003763`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003878`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800038cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800038fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000390a`

## string_xrefs

- `0x180003617`: `CLSID\`
- `0x18000378d`: `CLSID\`

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
0x1800034c0  mov     [rsp-8+arg_10], rbx
0x1800034c5  mov     [rsp-8+arg_18], rsi
0x1800034ca  push    rbp
0x1800034cb  push    rdi
0x1800034cc  push    r12
0x1800034ce  push    r14
0x1800034d0  push    r15
0x1800034d2  lea     rbp, [rsp-140h]
0x1800034da  sub     rsp, 240h
0x1800034e1  mov     rax, cs:__security_cookie
0x1800034e8  xor     rax, rsp
0x1800034eb  mov     [rbp+160h+var_30], rax
0x1800034f2  xor     r15d, r15d
0x1800034f5  xorps   xmm0, xmm0
0x1800034f8  mov     [rsp+260h+var_1F8], r15
0x1800034fd  mov     r14d, r8d
0x180003500  mov     rdi, rdx
0x180003503  mov     rbx, rcx
0x180003506  movups  [rbp+160h+var_1C8], xmm0
0x18000350a  test    rdx, rdx
0x18000350d  jz      loc_180003926
0x180003513  mov     eax, cs:GUID_NULL.Data1
0x180003519  cmp     [rcx], eax
0x18000351b  jnz     short loc_180003542
0x18000351d  mov     eax, dword ptr cs:GUID_NULL.Data2
0x180003523  cmp     [rcx+4], eax
0x180003526  jnz     short loc_180003542
0x180003528  mov     eax, dword ptr cs:GUID_NULL.Data4
0x18000352e  cmp     [rcx+8], eax
0x180003531  jnz     short loc_180003542
0x180003533  mov     eax, dword ptr cs:GUID_NULL.Data4+4
0x180003539  cmp     [rcx+0Ch], eax
0x18000353c  jz      loc_180003926
0x180003542  lea     rax, [rsp+260h+var_1F8]
0x180003547  mov     r12d, 1
0x18000354d  mov     r8d, r12d; dwClsContext
0x180003550  mov     [rsp+260h+ppv], rax; ppv
0x180003555  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x18000355c  xor     edx, edx; pUnkOuter
0x18000355e  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180003565  call    cs:__imp_CoCreateInstance
0x18000356b  test    eax, eax
0x18000356d  js      loc_180003910
0x180003573  jmp     short loc_1800035EF
0x180003575  mov     rax, [rdi+8]
0x180003579  lea     r9, [rbp+160h+var_1C8]
0x18000357d  mov     r8d, r12d
0x180003580  mov     rdx, rbx
0x180003583  movups  xmm0, xmmword ptr [rax]
0x180003586  movdqu  [rbp+160h+var_1C8], xmm0
0x18000358b  test    r14d, r14d
0x18000358e  jz      short loc_1800035CF
0x180003590  cmp     ecx, r12d
0x180003593  mov     rcx, [rsp+260h+var_1F8]
0x180003598  mov     rax, [rcx]
0x18000359b  jnz     short loc_1800035A3
0x18000359d  mov     rax, [rax+28h]
0x1800035a1  jmp     short loc_1800035A7
0x1800035a3  mov     rax, [rax+38h]
0x1800035a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ac  mov     esi, eax
0x1800035ae  test    eax, eax
0x1800035b0  jns     short loc_1800035EB
0x1800035b2  mov     rcx, [rsp+260h+var_1F8]
0x1800035b7  test    rcx, rcx
0x1800035ba  jz      short loc_1800035C8
0x1800035bc  mov     rax, [rcx]
0x1800035bf  mov     rax, [rax+10h]
0x1800035c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035c8  mov     eax, esi
0x1800035ca  jmp     loc_180003928
0x1800035cf  cmp     ecx, r12d
0x1800035d2  mov     rcx, [rsp+260h+var_1F8]
0x1800035d7  mov     rax, [rcx]
0x1800035da  jnz     short loc_1800035E2
0x1800035dc  mov     rax, [rax+30h]
0x1800035e0  jmp     short loc_1800035E6
0x1800035e2  mov     rax, [rax+40h]
0x1800035e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035eb  add     rdi, 10h
0x1800035ef  mov     ecx, [rdi]
0x1800035f1  test    ecx, ecx
0x1800035f3  jnz     short loc_180003575
0x1800035f5  test    r14d, r14d
0x1800035f8  jnz     loc_180003910
0x1800035fe  lea     r8d, [rcx+40h]; cchMax
0x180003602  mov     rcx, rbx; rguid
0x180003605  lea     rdx, [rbp+160h+sz]; lpsz
0x18000360c  call    cs:__imp_StringFromGUID2
0x180003612  mov     ebx, 80h
0x180003617  lea     r8, aClsid; "CLSID\\"
0x18000361e  mov     edx, ebx; SizeInWords
0x180003620  lea     rcx, [rbp+160h+Destination]; Destination
0x180003624  call    cs:__imp_wcscpy_s
0x18000362a  lea     r14d, [rbx-74h]
0x18000362e  lea     r12d, [rbx-30h]
0x180003632  test    eax, eax
0x180003634  jz      short loc_18000365A
0x180003636  cmp     eax, r14d
0x180003639  jz      loc_180003953
0x18000363f  cmp     eax, 16h
0x180003642  jz      loc_180003969
0x180003648  cmp     eax, 22h ; '"'
0x18000364b  jz      loc_180003969
0x180003651  cmp     eax, r12d
0x180003654  jnz     loc_18000395E
0x18000365a  lea     r8, [rbp+160h+sz]; Source
0x180003661  mov     rdx, rbx; SizeInWords
0x180003664  lea     rcx, [rbp+160h+Destination]; Destination
0x180003668  call    cs:__imp_wcscat_s
0x18000366e  test    eax, eax
0x180003670  jz      short loc_180003696
0x180003672  cmp     eax, r14d
0x180003675  jz      loc_180003953
0x18000367b  cmp     eax, 16h
0x18000367e  jz      loc_180003969
0x180003684  cmp     eax, 22h ; '"'
0x180003687  jz      loc_180003969
0x18000368d  cmp     eax, r12d
0x180003690  jnz     loc_18000395E
0x180003696  lea     r8, aRequiredCatego; "\\Required Categories"
0x18000369d  mov     rdx, rbx; SizeInWords
0x1800036a0  lea     rcx, [rbp+160h+Destination]; Destination
0x1800036a4  call    cs:__imp_wcscat_s
0x1800036aa  test    eax, eax
0x1800036ac  jz      short loc_1800036D2
0x1800036ae  cmp     eax, r14d
0x1800036b1  jz      loc_180003953
0x1800036b7  cmp     eax, 16h
0x1800036ba  jz      loc_180003969
0x1800036c0  cmp     eax, 22h ; '"'
0x1800036c3  jz      loc_180003969
0x1800036c9  cmp     eax, r12d
0x1800036cc  jnz     loc_18000395E
0x1800036d2  mov     rdi, 0FFFFFFFF80000000h
0x1800036d9  mov     [rbp+160h+var_1D8], r15
0x1800036dd  lea     rax, [rsp+260h+phkResult]
0x1800036e2  mov     [rbp+160h+var_1E0], rdi
0x1800036e6  mov     rcx, rdi; hKey
0x1800036e9  mov     [rbp+160h+var_1D0], r15
0x1800036ed  mov     r9d, 20019h; samDesired
0x1800036f3  mov     [rsp+260h+cSubKeys], r15d
0x1800036f8  xor     r8d, r8d; ulOptions
0x1800036fb  mov     [rsp+260h+phkResult], r15
0x180003700  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x180003704  mov     [rsp+260h+ppv], rax; phkResult
0x180003709  mov     rbx, r15
0x18000370c  call    cs:__imp_RegOpenKeyExW
0x180003712  test    eax, eax
0x180003714  jnz     short loc_180003788
0x180003716  mov     rbx, [rsp+260h+phkResult]
0x18000371b  lea     rax, [rsp+260h+cSubKeys]
0x180003720  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180003725  xor     r9d, r9d; lpReserved
0x180003728  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000372d  xor     r8d, r8d; lpcchClass
0x180003730  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180003735  xor     edx, edx; lpClass
0x180003737  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x18000373c  mov     rcx, rbx; hKey
0x18000373f  mov     [rsp+260h+lpcValues], r15; lpcValues
0x180003744  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180003749  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18000374e  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x180003753  call    cs:__imp_RegQueryInfoKeyW
0x180003759  mov     esi, eax
0x18000375b  test    rbx, rbx
0x18000375e  jz      short loc_18000376C
0x180003760  mov     rcx, rbx; hKey
0x180003763  call    cs:__imp_RegCloseKey
0x180003769  mov     rbx, r15
0x18000376c  test    esi, esi
0x18000376e  jnz     short loc_180003788
0x180003770  cmp     [rsp+260h+cSubKeys], r15d
0x180003775  jnz     short loc_180003788
0x180003777  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x18000377b  lea     rcx, [rbp+160h+var_1E0]; this
0x18000377f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180003784  mov     rdi, [rbp+160h+var_1E0]
0x180003788  mov     esi, 80h
0x18000378d  lea     r8, aClsid; "CLSID\\"
0x180003794  mov     edx, esi; SizeInWords
0x180003796  lea     rcx, [rbp+160h+Destination]; Destination
0x18000379a  call    cs:__imp_wcscpy_s
0x1800037a0  test    eax, eax
0x1800037a2  jz      short loc_1800037C8
0x1800037a4  cmp     eax, r14d
0x1800037a7  jz      loc_180003953
0x1800037ad  cmp     eax, 16h
0x1800037b0  jz      loc_180003969
0x1800037b6  cmp     eax, 22h ; '"'
0x1800037b9  jz      loc_180003969
0x1800037bf  cmp     eax, r12d
0x1800037c2  jnz     loc_18000395E
0x1800037c8  lea     r8, [rbp+160h+sz]; Source
0x1800037cf  mov     rdx, rsi; SizeInWords
0x1800037d2  lea     rcx, [rbp+160h+Destination]; Destination
0x1800037d6  call    cs:__imp_wcscat_s
0x1800037dc  test    eax, eax
0x1800037de  jz      short loc_180003804
0x1800037e0  cmp     eax, r14d
0x1800037e3  jz      loc_180003953
0x1800037e9  cmp     eax, 16h
0x1800037ec  jz      loc_180003969
0x1800037f2  cmp     eax, 22h ; '"'
0x1800037f5  jz      loc_180003969
0x1800037fb  cmp     eax, r12d
0x1800037fe  jnz     loc_18000395E
0x180003804  lea     r8, aImplementedCat; "\\Implemented Categories"
0x18000380b  mov     rdx, rsi; SizeInWords
0x18000380e  lea     rcx, [rbp+160h+Destination]; Destination
0x180003812  call    cs:__imp_wcscat_s
0x180003818  test    eax, eax
0x18000381a  jz      short loc_180003840
0x18000381c  cmp     eax, r14d
0x18000381f  jz      loc_180003953
0x180003825  cmp     eax, 16h
0x180003828  jz      loc_180003969
0x18000382e  cmp     eax, 22h ; '"'
0x180003831  jz      loc_180003969
0x180003837  cmp     eax, r12d
0x18000383a  jnz     loc_18000395E
0x180003840  lea     rax, [rsp+260h+hKey]
0x180003845  mov     [rsp+260h+hKey], r15
0x18000384a  mov     r9d, 20019h; samDesired
0x180003850  mov     [rsp+260h+ppv], rax; phkResult
0x180003855  xor     r8d, r8d; ulOptions
0x180003858  lea     rdx, [rbp+160h+Destination]; lpSubKey
0x18000385c  mov     rcx, rdi; hKey
0x18000385f  call    cs:__imp_RegOpenKeyExW
0x180003865  test    eax, eax
0x180003867  jnz     loc_1800038F4
0x18000386d  mov     eax, r15d
0x180003870  test    rbx, rbx
0x180003873  jz      short loc_18000387E
0x180003875  mov     rcx, rbx; hKey
0x180003878  call    cs:__imp_RegCloseKey
0x18000387e  mov     rbx, [rsp+260h+hKey]
0x180003883  test    eax, eax
0x180003885  jnz     short loc_1800038F4
0x180003887  mov     [rsp+260h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000388c  lea     rax, [rsp+260h+cSubKeys]
0x180003891  mov     [rsp+260h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180003896  xor     r9d, r9d; lpReserved
0x180003899  mov     [rsp+260h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000389e  xor     r8d, r8d; lpcchClass
0x1800038a1  mov     [rsp+260h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800038a6  xor     edx, edx; lpClass
0x1800038a8  mov     [rsp+260h+lpcValues], r15; lpcValues
0x1800038ad  mov     rcx, rbx; hKey
0x1800038b0  mov     [rsp+260h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800038b5  mov     [rsp+260h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800038ba  mov     [rsp+260h+ppv], rax; lpcSubKeys
0x1800038bf  call    cs:__imp_RegQueryInfoKeyW
0x1800038c5  mov     esi, eax
0x1800038c7  test    rbx, rbx
0x1800038ca  jz      short loc_1800038D8
0x1800038cc  mov     rcx, rbx; hKey
0x1800038cf  call    cs:__imp_RegCloseKey
0x1800038d5  mov     rbx, r15
0x1800038d8  test    esi, esi
0x1800038da  jnz     short loc_180003902
0x1800038dc  cmp     [rsp+260h+cSubKeys], r15d
0x1800038e1  jnz     short loc_1800038F4
0x1800038e3  lea     rdx, [rbp+160h+Destination]; unsigned __int16 *
0x1800038e7  lea     rcx, [rbp+160h+var_1E0]; this
0x1800038eb  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800038f0  mov     rdi, [rbp+160h+var_1E0]
0x1800038f4  test    rbx, rbx
0x1800038f7  jz      short loc_180003902
0x1800038f9  mov     rcx, rbx; hKey
0x1800038fc  call    cs:__imp_RegCloseKey
0x180003902  test    rdi, rdi
0x180003905  jz      short loc_180003910
0x180003907  mov     rcx, rdi; hKey
0x18000390a  call    cs:__imp_RegCloseKey
0x180003910  mov     rcx, [rsp+260h+var_1F8]
0x180003915  test    rcx, rcx
0x180003918  jz      short loc_180003926
0x18000391a  mov     rax, [rcx]
0x18000391d  mov     rax, [rax+10h]
0x180003921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003926  xor     eax, eax
0x180003928  mov     rcx, [rbp+160h+var_30]
0x18000392f  xor     rcx, rsp; StackCookie
0x180003932  call    __security_check_cookie
0x180003937  lea     r11, [rsp+260h+var_20]
0x18000393f  mov     rbx, [r11+40h]
0x180003943  mov     rsi, [r11+48h]
0x180003947  mov     rsp, r11
0x18000394a  pop     r15
0x18000394c  pop     r14
0x18000394e  pop     r12
0x180003950  pop     rdi
0x180003951  pop     rbp
0x180003952  retn
0x180003953  mov     ecx, 8007000Eh; int
0x180003958  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000395e  mov     ecx, 80004005h; int
0x180003963  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
  ... truncated ...
```
