# CMVEngine::RetrieveHandlers(int *)

- ea: `0x18001d25c`
- end: `0x18001d91c`
- name: `?RetrieveHandlers@CMVEngine@@AEAAJPEAH@Z`
- size: `1728`
- prototype: `__int64 __fastcall(LPCWSTR *this, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800141f0`
- `0x180014810`

## callees

- `0x1800010c8`
- `0x1800018ec`
- `0x180001994`
- `0x180002f0c`
- `0x1800098dc`
- `0x18000aef0`
- `0x18001d25c`
- `0x180021904`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!qsort_s` at `0x18001d524`
- `msvcrt!qsort_s` at `0x18001d524`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d6ff`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d708`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d835`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d83e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d878`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d89e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d6ff`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d708`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d835`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d83e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d878`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d89e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001d475`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001d475`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d4d2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d4d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d2b1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d2b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d717`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d84d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d8ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d8e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d717`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d84d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d8ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d8e7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001d35a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001d35a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d568`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d568`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d493`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18001d493`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMVEngine::RetrieveHandlers(LPCWSTR *this, int *a2)
{
  LSTATUS v4; // eax
  int v5; // r9d
  signed int v6; // ebx
  __int64 v7; // rdx
  LSTATUS v8; // eax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rax
  void *v11; // rbx
  unsigned __int64 v12; // rax
  char *v13; // rdi
  DWORD v14; // r15d
  DWORD v15; // eax
  LSTATUS v16; // eax
  int v17; // esi
  LSTATUS ValueW; // eax
  __int64 v19; // rcx
  int v20; // r15d
  HRESULT v21; // eax
  int v22; // r8d
  int v23; // r9d
  int v24; // r14d
  int v25; // ecx
  LPVOID v26; // rcx
  __int64 v27; // rdx
  int v29; // eax
  int v30; // r8d
  int v31; // r9d
  _QWORD *v32; // rsi
  LPCWSTR v33; // r9
  LPCWSTR v34; // rdx
  __int64 v35; // rdx
  unsigned __int64 v36; // rdx
  unsigned __int64 v37; // r9
  unsigned __int64 v38; // r8
  LPVOID *v39; // rcx
  int phkResult; // [rsp+20h] [rbp-99h]
  int phkResulta; // [rsp+20h] [rbp-99h]
  DWORD cSubKeys; // [rsp+60h] [rbp-59h] BYREF
  signed int pvData; // [rsp+64h] [rbp-55h] BYREF
  LPCWSTR v44; // [rsp+68h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-49h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+78h] [rbp-41h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-39h] BYREF
  DWORD pcbData[2]; // [rsp+88h] [rbp-31h] BYREF
  DWORD cchName; // [rsp+90h] [rbp-29h] BYREF
  GUID pclsid; // [rsp+98h] [rbp-21h] BYREF
  _BYTE v51[32]; // [rsp+A8h] [rbp-11h] BYREF
  _QWORD *p_pvData; // [rsp+C8h] [rbp+Fh]
  __int64 v53; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  *a2 = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, this[5], 0, 0x20019u, &hKey);
  v6 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v6 = (unsigned __int16)v4 | 0x80070000;
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      pvData = v6;
      v44 = this[5];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18005A000,
        (unsigned int)&dword_18004EAAC,
        0,
        v5,
        (__int64)&v44,
        (__int64)&pvData);
    }
    if ( v6 >= 0 )
      goto LABEL_83;
    v7 = 460;
LABEL_82:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)(unsigned int)v6,
      phkResult);
LABEL_83:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  v6 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      pvData = v6;
      p_pvData = &pvData;
      v53 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &dword_18004EC2C, 0, 0, 3, v51);
    }
    if ( v6 >= 0 )
      goto LABEL_83;
    v7 = 475;
    goto LABEL_82;
  }
  v9 = cbMaxSubKeyLen + 1;
  if ( (unsigned int)v9 < cbMaxSubKeyLen )
  {
    cbMaxSubKeyLen = -1;
    v6 = -2147024362;
    v7 = 478;
    goto LABEL_82;
  }
  ++cbMaxSubKeyLen;
  v10 = 2 * v9;
  if ( !is_mul_ok(v9, 2u) )
    v10 = -1;
  v11 = operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)0x8007000ELL,
      phkResult);
    goto LABEL_78;
  }
  v12 = 20LL * cSubKeys;
  if ( !is_mul_ok(cSubKeys, 0x14u) )
    v12 = -1;
  v13 = (char *)operator new[](v12, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v13 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)0x8007000ELL,
      phkResult);
    operator delete[](0);
LABEL_78:
    operator delete[](v11);
    if ( hKey )
      RegCloseKey(hKey);
    return 2147942414LL;
  }
  v14 = 0;
  v15 = cSubKeys;
  if ( !cSubKeys )
  {
LABEL_27:
    qsort_s(v13, v15, 0x14u, HandlerKeyComparer, 0);
    v20 = 0;
    if ( !cSubKeys )
    {
LABEL_73:
      operator delete[](v13);
      operator delete[](v11);
      if ( hKey )
        RegCloseKey(hKey);
      return 0;
    }
    while ( 1 )
    {
      if ( *a2 )
        goto LABEL_73;
      ppv = 0;
      v21 = CoCreateInstance((const IID *const)&v13[20 * v20], 0, 1u, &GUID_df77240f_30f9_418f_a12d_26a18c50f54f, &ppv);
      v24 = v21;
      v25 = dword_18005A000;
      if ( (unsigned int)dword_18005A000 > 5 )
      {
        LODWORD(v44) = v21;
        *(_QWORD *)pcbData = &v13[20 * v20];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          dword_18005A000,
          (unsigned int)&dword_18004EF24,
          v22,
          v23,
          (__int64)pcbData,
          (__int64)&v44);
      }
      if ( v24 >= 0 )
      {
        v29 = (*(__int64 (__fastcall **)(LPVOID, LPCWSTR *, int *))(*(_QWORD *)ppv + 24LL))(ppv, this, a2);
        if ( v29 >= 0 )
        {
          v32 = this + 7;
          v33 = this[9];
          v34 = this[8];
          if ( v34 == v33 && !(((char *)v33 - (char *)v34) >> 3) )
          {
            v35 = ((__int64)v34 - *v32) >> 3;
            if ( v35 == 0x1FFFFFFFFFFFFFFFLL )
              std::vector<ProvSource *>::_Xlen();
            v36 = v35 + 1;
            v37 = ((__int64)v33 - *v32) >> 3;
            v38 = 0;
            if ( 0x1FFFFFFFFFFFFFFFLL - (v37 >> 1) >= v37 )
              v38 = v37 + (v37 >> 1);
            if ( v38 >= v36 )
              v36 = v38;
            std::vector<Microsoft::WRL::ComPtr<IMVHandler>>::_Reallocate(this + 7, v36);
          }
          v39 = (LPVOID *)this[8];
          *v39 = 0;
          if ( v39 == &ppv )
          {
            v26 = ppv;
          }
          else
          {
            *v39 = ppv;
            v26 = 0;
          }
          this[8] += 4;
          goto LABEL_70;
        }
        if ( (unsigned int)dword_18005A000 > 2 )
        {
          LODWORD(v44) = v29;
          *(_QWORD *)pcbData = &v13[20 * v20];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            dword_18005A000,
            (unsigned int)&byte_18004EA37,
            v30,
            v31,
            (__int64)pcbData,
            (__int64)&v44);
        }
      }
      else if ( (unsigned int)dword_18005A000 > 2 )
      {
        LODWORD(v44) = v24;
        *(_QWORD *)pcbData = &v13[20 * v20];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)byte_18004E5D5,
          v22,
          v23,
          (__int64)pcbData,
          (__int64)&v44);
      }
      v26 = ppv;
LABEL_70:
      if ( v26 )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
      }
      if ( ++v20 >= cSubKeys )
        goto LABEL_73;
    }
  }
  while ( 1 )
  {
    cchName = cbMaxSubKeyLen;
    pvData = 0;
    pcbData[0] = 4;
    v16 = RegEnumKeyExW(hKey, v14, (LPWSTR)v11, &cchName, 0, 0, 0, 0);
    v17 = v16;
    if ( v16 )
      break;
    pclsid = 0;
    v17 = CLSIDFromString((LPCOLESTR)v11, &pclsid);
    if ( v17 < 0 )
    {
      if ( (unsigned int)dword_18005A000 > 2 )
      {
        LODWORD(v44) = v17;
        p_pvData = &v44;
        v53 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004E993, 0, 0, 3, v51);
      }
      v27 = 513;
      goto LABEL_50;
    }
    ValueW = RegGetValueW(hKey, (LPCWSTR)v11, L"KeyOrder", 0x18u, 0, &pvData, pcbData);
    v17 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v17 = (unsigned __int16)ValueW | 0x80070000;
      if ( (unsigned int)dword_18005A000 > 2 )
      {
        LODWORD(v44) = v17;
        p_pvData = &v44;
        v53 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &dword_18004E63C, 0, 0, 3, v51);
      }
      if ( v17 < 0 )
      {
        v27 = 531;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v27,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
          (const char *)(unsigned int)v17,
          phkResulta);
        goto LABEL_51;
      }
      goto LABEL_51;
    }
    v19 = 5LL * v14;
    *(GUID *)&v13[4 * v19] = pclsid;
    *(_DWORD *)&v13[4 * v19 + 16] = pvData;
    ++v14;
    v15 = cSubKeys;
    if ( v14 >= cSubKeys )
      goto LABEL_27;
  }
  if ( v16 > 0 )
    v17 = (unsigned __int16)v16 | 0x80070000;
  if ( (unsigned int)dword_18005A000 > 2 )
  {
    LODWORD(v44) = v17;
    p_pvData = &v44;
    v53 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &byte_18004EAE7, 0, 0, 3, v51);
  }
  if ( v17 < 0 )
  {
    v27 = 502;
    goto LABEL_50;
  }
LABEL_51:
  operator delete[](v13);
  operator delete[](v11);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18001d25c  mov     [rsp-8+arg_10], rbx
0x18001d261  push    rbp
0x18001d262  push    rsi
0x18001d263  push    rdi
0x18001d264  push    r12
0x18001d266  push    r13
0x18001d268  push    r14
0x18001d26a  push    r15
0x18001d26c  lea     rbp, [rsp-27h]
0x18001d271  sub     rsp, 0E0h
0x18001d278  mov     rax, cs:__security_cookie
0x18001d27f  xor     rax, rsp
0x18001d282  mov     [rbp+57h+var_38], rax
0x18001d286  mov     r12, rdx
0x18001d289  mov     r13, rcx
0x18001d28c  xor     esi, esi
0x18001d28e  mov     [rdx], esi
0x18001d290  mov     [rbp+57h+hKey], rsi
0x18001d294  lea     rax, [rbp+57h+hKey]
0x18001d298  mov     [rsp+110h+phkResult], rax; phkResult
0x18001d29d  mov     r9d, 20019h; samDesired
0x18001d2a3  xor     r8d, r8d; ulOptions
0x18001d2a6  mov     rdx, [rcx+28h]; lpSubKey
0x18001d2aa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d2b1  call    cs:__imp_RegOpenKeyExW
0x18001d2b7  mov     ebx, eax
0x18001d2b9  test    eax, eax
0x18001d2bb  jz      short loc_18001D318
0x18001d2bd  jle     short loc_18001D2C8
0x18001d2bf  movzx   ebx, ax
0x18001d2c2  or      ebx, 80070000h
0x18001d2c8  mov     eax, cs:dword_18005A000
0x18001d2ce  cmp     eax, 2
0x18001d2d1  jbe     short loc_18001D306
0x18001d2d3  mov     [rbp+57h+pvData], ebx
0x18001d2d6  mov     rax, [r13+28h]
0x18001d2da  mov     [rbp+57h+var_A8], rax
0x18001d2de  lea     rax, [rbp+57h+pvData]
0x18001d2e2  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x18001d2e7  lea     rax, [rbp+57h+var_A8]
0x18001d2eb  mov     [rsp+110h+phkResult], rax
0x18001d2f0  xor     r8d, r8d
0x18001d2f3  lea     rdx, dword_18004EAAC
0x18001d2fa  lea     rcx, dword_18005A000
0x18001d301  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001d306  test    ebx, ebx
0x18001d308  jns     loc_18001D8DE
0x18001d30e  mov     edx, 1CCh
0x18001d313  jmp     loc_18001D8CB
0x18001d318  mov     [rbp+57h+cSubKeys], esi
0x18001d31b  mov     [rbp+57h+cbMaxSubKeyLen], esi
0x18001d31e  mov     [rsp+110h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18001d323  mov     [rsp+110h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18001d328  mov     [rsp+110h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18001d32d  mov     [rsp+110h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18001d332  mov     [rsp+110h+lpcValues], rsi; lpcValues
0x18001d337  mov     [rsp+110h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18001d33c  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18001d340  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001d345  lea     rax, [rbp+57h+cSubKeys]
0x18001d349  mov     [rsp+110h+phkResult], rax; int
0x18001d34e  xor     r9d, r9d; lpReserved
0x18001d351  xor     r8d, r8d; lpcchClass
0x18001d354  xor     edx, edx; lpClass
0x18001d356  mov     rcx, [rbp+57h+hKey]; hKey
0x18001d35a  call    cs:__imp_RegQueryInfoKeyW
0x18001d360  mov     ebx, eax
0x18001d362  test    eax, eax
0x18001d364  jz      short loc_18001D3CB
0x18001d366  jle     short loc_18001D371
0x18001d368  movzx   ebx, ax
0x18001d36b  or      ebx, 80070000h
0x18001d371  mov     eax, cs:dword_18005A000
0x18001d377  cmp     eax, 2
0x18001d37a  jbe     short loc_18001D3B9
0x18001d37c  mov     [rbp+57h+pvData], ebx
0x18001d37f  lea     rax, [rbp+57h+pvData]
0x18001d383  mov     [rbp+57h+var_48], rax
0x18001d387  mov     [rbp+57h+var_40], 4
0x18001d38f  lea     rax, [rbp+57h+var_68]
0x18001d393  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x18001d398  mov     dword ptr [rsp+110h+phkResult], 3
0x18001d3a0  xor     r9d, r9d
0x18001d3a3  xor     r8d, r8d
0x18001d3a6  lea     rdx, dword_18004EC2C
0x18001d3ad  lea     rcx, dword_18005A000
0x18001d3b4  call    _tlgWriteTransfer_EventWriteTransfer
0x18001d3b9  test    ebx, ebx
0x18001d3bb  jns     loc_18001D8DE
0x18001d3c1  mov     edx, 1DBh
0x18001d3c6  jmp     loc_18001D8CB
0x18001d3cb  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18001d3ce  lea     ecx, [rax+1]
0x18001d3d1  cmp     ecx, eax
0x18001d3d3  jb      loc_18001D8BA
0x18001d3d9  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x18001d3dc  mov     eax, 2
0x18001d3e1  mul     rcx
0x18001d3e4  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001d3eb  cmovb   rax, rdi
0x18001d3ef  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d3f6  mov     rcx, rax; unsigned __int64
0x18001d3f9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d3fe  mov     rbx, rax
0x18001d401  test    rax, rax
0x18001d404  jz      loc_18001D880
0x18001d40a  mov     ecx, [rbp+57h+cSubKeys]
0x18001d40d  lea     eax, [rdi+15h]
0x18001d410  mul     rcx
0x18001d413  cmovb   rax, rdi
0x18001d417  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d41e  mov     rcx, rax; unsigned __int64
0x18001d421  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d426  mov     rdi, rax
0x18001d429  test    rax, rax
0x18001d42c  jz      loc_18001D85A
0x18001d432  mov     r15d, esi
0x18001d435  mov     eax, [rbp+57h+cSubKeys]
0x18001d438  test    eax, eax
0x18001d43a  jz      loc_18001D50D
0x18001d440  mov     r14d, 4
0x18001d446  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18001d449  mov     [rbp+57h+cchName], eax
0x18001d44c  mov     [rbp+57h+pvData], esi
0x18001d44f  mov     [rbp+57h+pcbData], r14d
0x18001d453  mov     [rsp+110h+lpcValues], rsi; lpftLastWriteTime
0x18001d458  mov     [rsp+110h+lpcbMaxClassLen], rsi; lpcchClass
0x18001d45d  mov     [rsp+110h+lpcbMaxSubKeyLen], rsi; lpClass
0x18001d462  mov     [rsp+110h+phkResult], rsi; lpReserved
0x18001d467  lea     r9, [rbp+57h+cchName]; lpcchName
0x18001d46b  mov     r8, rbx; lpName
0x18001d46e  mov     edx, r15d; dwIndex
0x18001d471  mov     rcx, [rbp+57h+hKey]; hKey
0x18001d475  call    cs:__imp_RegEnumKeyExW
0x18001d47b  mov     esi, eax
0x18001d47d  test    eax, eax
0x18001d47f  jnz     loc_18001D691
0x18001d485  xorps   xmm0, xmm0
0x18001d488  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18001d48c  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18001d490  mov     rcx, rbx; lpsz
0x18001d493  call    cs:__imp_CLSIDFromString
0x18001d499  mov     esi, eax
0x18001d49b  test    eax, eax
0x18001d49d  js      loc_18001D646
0x18001d4a3  lea     rax, [rbp+57h+pcbData]
0x18001d4a7  mov     [rsp+110h+lpcbMaxClassLen], rax; pcbData
0x18001d4ac  lea     rax, [rbp+57h+pvData]
0x18001d4b0  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; pvData
0x18001d4b5  mov     [rsp+110h+phkResult], 0; pdwType
0x18001d4be  mov     r9d, 18h; dwFlags
0x18001d4c4  lea     r8, ?gc_wszKeyOrder@@3QBGB; "KeyOrder"
0x18001d4cb  mov     rdx, rbx; lpSubKey
0x18001d4ce  mov     rcx, [rbp+57h+hKey]; hkey
0x18001d4d2  call    cs:__imp_RegGetValueW
0x18001d4d8  mov     esi, eax
0x18001d4da  test    eax, eax
0x18001d4dc  jnz     loc_18001D5E5
0x18001d4e2  movups  xmm0, xmmword ptr [rbp+57h+pclsid.Data1]
0x18001d4e6  mov     eax, r15d
0x18001d4e9  lea     rcx, [rax+rax*4]
0x18001d4ed  movdqu  xmmword ptr [rdi+rcx*4], xmm0
0x18001d4f2  mov     eax, [rbp+57h+pvData]
0x18001d4f5  mov     [rdi+rcx*4+10h], eax
0x18001d4f9  inc     r15d
0x18001d4fc  mov     eax, [rbp+57h+cSubKeys]
0x18001d4ff  cmp     r15d, eax
0x18001d502  mov     esi, 0
0x18001d507  jb      loc_18001D446
0x18001d50d  mov     edx, eax; NumOfElements
0x18001d50f  mov     [rsp+110h+phkResult], rsi; Context
0x18001d514  lea     r9, HandlerKeyComparer; CompareFunction
0x18001d51b  mov     r8d, 14h; SizeOfElements
0x18001d521  mov     rcx, rdi; Base
0x18001d524  call    cs:__imp_qsort_s
0x18001d52a  mov     r15d, esi
0x18001d52d  cmp     [rbp+57h+cSubKeys], esi
0x18001d530  jbe     loc_18001D832
0x18001d536  cmp     [r12], esi
0x18001d53a  jnz     loc_18001D832
0x18001d540  mov     [rbp+57h+ppv], rsi
0x18001d544  mov     eax, r15d
0x18001d547  lea     rcx, [rax+rax*4]
0x18001d54b  lea     rsi, [rdi+rcx*4]
0x18001d54f  lea     rax, [rbp+57h+ppv]
0x18001d553  mov     [rsp+110h+phkResult], rax; ppv
0x18001d558  lea     r9, _GUID_df77240f_30f9_418f_a12d_26a18c50f54f; riid
0x18001d55f  xor     edx, edx; pUnkOuter
0x18001d561  lea     r8d, [rdx+1]; dwClsContext
0x18001d565  mov     rcx, rsi; rclsid
0x18001d568  call    cs:__imp_CoCreateInstance
0x18001d56e  mov     r14d, eax
0x18001d571  mov     ecx, cs:dword_18005A000
0x18001d577  cmp     ecx, 5
0x18001d57a  jbe     short loc_18001D5A1
0x18001d57c  mov     dword ptr [rbp+57h+var_A8], eax
0x18001d57f  mov     qword ptr [rbp+57h+pcbData], rsi
0x18001d583  lea     rax, [rbp+57h+var_A8]
0x18001d587  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x18001d58c  lea     rax, [rbp+57h+pcbData]
0x18001d590  mov     [rsp+110h+phkResult], rax
0x18001d595  lea     rdx, dword_18004EF24
0x18001d59c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18001d5a1  test    r14d, r14d
0x18001d5a4  jns     loc_18001D724
0x18001d5aa  mov     eax, cs:dword_18005A000
0x18001d5b0  cmp     eax, 2
0x18001d5b3  jbe     short loc_18001D5DC
0x18001d5b5  mov     dword ptr [rbp+57h+var_A8], r14d
0x18001d5b9  mov     qword ptr [rbp+57h+pcbData], rsi
0x18001d5bd  lea     rax, [rbp+57h+var_A8]
0x18001d5c1  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x18001d5c6  lea     rax, [rbp+57h+pcbData]
0x18001d5ca  mov     [rsp+110h+phkResult], rax
0x18001d5cf  lea     rdx, byte_18004E5D5
0x18001d5d6  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18001d5db  nop
0x18001d5dc  mov     rcx, [rbp+57h+ppv]
0x18001d5e0  jmp     loc_18001D80D
0x18001d5e5  jle     short loc_18001D5F0
0x18001d5e7  movzx   esi, ax
0x18001d5ea  or      esi, 80070000h
0x18001d5f0  mov     eax, cs:dword_18005A000
0x18001d5f6  cmp     eax, 2
0x18001d5f9  jbe     short loc_18001D634
0x18001d5fb  mov     dword ptr [rbp+57h+var_A8], esi
0x18001d5fe  lea     rax, [rbp+57h+var_A8]
0x18001d602  mov     [rbp+57h+var_48], rax
0x18001d606  mov     [rbp+57h+var_40], r14
0x18001d60a  lea     rax, [rbp+57h+var_68]
0x18001d60e  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x18001d613  mov     dword ptr [rsp+110h+phkResult], 3
0x18001d61b  xor     r9d, r9d
0x18001d61e  xor     r8d, r8d
0x18001d621  lea     rdx, dword_18004E63C
0x18001d628  lea     rcx, dword_18005A000
0x18001d62f  call    _tlgWriteTransfer_EventWriteTransfer
0x18001d634  test    esi, esi
0x18001d636  jns     loc_18001D6FC
0x18001d63c  mov     edx, 213h
0x18001d641  jmp     loc_18001D6E9
0x18001d646  mov     eax, cs:dword_18005A000
0x18001d64c  cmp     eax, 2
0x18001d64f  jbe     short loc_18001D68A
0x18001d651  mov     dword ptr [rbp+57h+var_A8], esi
0x18001d654  lea     rax, [rbp+57h+var_A8]
0x18001d658  mov     [rbp+57h+var_48], rax
0x18001d65c  mov     [rbp+57h+var_40], r14
0x18001d660  lea     rax, [rbp+57h+var_68]
0x18001d664  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x18001d669  mov     dword ptr [rsp+110h+phkResult], 3
0x18001d671  xor     r9d, r9d
0x18001d674  xor     r8d, r8d
0x18001d677  lea     rdx, byte_18004E993
0x18001d67e  lea     rcx, dword_18005A000
0x18001d685  call    _tlgWriteTransfer_EventWriteTransfer
0x18001d68a  mov     edx, 201h
0x18001d68f  jmp     short loc_18001D6E9
0x18001d691  jle     short loc_18001D69C
0x18001d693  movzx   esi, ax
0x18001d696  or      esi, 80070000h
0x18001d69c  mov     eax, cs:dword_18005A000
0x18001d6a2  cmp     eax, 2
0x18001d6a5  jbe     short loc_18001D6E0
0x18001d6a7  mov     dword ptr [rbp+57h+var_A8], esi
0x18001d6aa  lea     rax, [rbp+57h+var_A8]
0x18001d6ae  mov     [rbp+57h+var_48], rax
0x18001d6b2  mov     [rbp+57h+var_40], r14
0x18001d6b6  lea     rax, [rbp+57h+var_68]
0x18001d6ba  mov     [rsp+110h+lpcbMaxSubKeyLen], rax
0x18001d6bf  mov     dword ptr [rsp+110h+phkResult], 3; int
0x18001d6c7  xor     r9d, r9d
0x18001d6ca  xor     r8d, r8d
0x18001d6cd  lea     rdx, byte_18004EAE7
0x18001d6d4  lea     rcx, dword_18005A000
0x18001d6db  call    _tlgWriteTransfer_EventWriteTransfer
0x18001d6e0  test    esi, esi
0x18001d6e2  jns     short loc_18001D6FC
0x18001d6e4  mov     edx, 1F6h; void *
0x18001d6e9  mov     rcx, [rbp+5Fh]; this
0x18001d6ed  mov     r9d, esi; char *
0x18001d6f0  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001d6f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d6fc  mov     rcx, rdi
0x18001d6ff  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001d705  mov     rcx, rbx
0x18001d708  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001d70e  mov     rcx, [rbp+57h+hKey]; hKey
0x18001d712  test    rcx, rcx
0x18001d715  jz      short loc_18001D71D
0x18001d717  call    cs:__imp_RegCloseKey
0x18001d71d  mov     eax, esi
0x18001d71f  jmp     loc_18001D8EF
0x18001d724  mov     rcx, [rbp+57h+ppv]
0x18001d728  mov     rax, [rcx]
0x18001d72b  mov     r8, r12
0x18001d72e  mov     rdx, r13
0x18001d731  mov     rax, [rax+18h]
0x18001d735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d73a  test    eax, eax
  ... truncated ...
```
