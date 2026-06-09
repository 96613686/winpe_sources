# CDimInterface::GetInfoFromRegistryKey(HKEY__ *,ulong,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &,ulong &,ulong &)

- ea: `0x18001c418`
- end: `0x18001c9a4`
- name: `?GetInfoFromRegistryKey@CDimInterface@@AEAAKPEAUHKEY__@@KAEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@AEAK2@Z`
- size: `1420`
- prototype: `__int64 __fastcall(WCHAR *, HKEY, DWORD, void **, LPDWORD lpcbData, BYTE *lpData)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001b4b0`

## callees

- `0x18000b654`
- `0x18000df70`
- `0x18001abd0`
- `0x18001c418`
- `0x18002eb44`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c7ee`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001c7ee`
- `msvcrt!_wcsicmp` at `0x18001c633`
- `msvcrt!_wcsicmp` at `0x18001c650`
- `msvcrt!_wcsicmp` at `0x18001c633`
- `msvcrt!_wcsicmp` at `0x18001c650`
- `rtutils!RouterLogEventW` at `0x18001c619`
- `rtutils!RouterLogEventW` at `0x18001c619`
- `ADVAPI32!RegOpenKeyExW` at `0x18001c67f`
- `ADVAPI32!RegOpenKeyExW` at `0x18001c67f`
- `ADVAPI32!RegCloseKey` at `0x18001c977`
- `ADVAPI32!RegCloseKey` at `0x18001c977`
- `ADVAPI32!RegQueryValueExW` at `0x18001c824`
- `ADVAPI32!RegQueryValueExW` at `0x18001c884`
- `ADVAPI32!RegQueryValueExW` at `0x18001c824`
- `ADVAPI32!RegQueryValueExW` at `0x18001c884`
- `ADVAPI32!RegEnumKeyExW` at `0x18001c520`
- `ADVAPI32!RegEnumKeyExW` at `0x18001c520`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001c7a0`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001c7a0`

## string_xrefs

- `0x18001c578`: `Cannot enumerate keys of Registry key Error: %d.`
- `0x18001c6ce`: `Cannot access the Registry key Error: %d.`
- `0x18001c812`: `ProtocolId`
- `0x18001c8dc`: `Cannot access Registry value for %s.`

## pseudocode

```c
__int64 __fastcall CDimInterface::GetInfoFromRegistryKey(
        WCHAR *a1,
        HKEY a2,
        DWORD a3,
        void **a4,
        LPDWORD lpcbData,
        BYTE *lpData)
{
  LSTATUS v10; // eax
  __int64 v11; // rax
  __int128 *v12; // r9
  DWORD v13; // r8d
  WCHAR *v14; // rax
  __int64 v15; // rax
  __int128 *v16; // r9
  LSTATUS v17; // eax
  __int64 v18; // rax
  __int128 *v19; // r9
  LPWSTR v21; // rbx
  __int64 v22; // rax
  __int128 *v23; // r9
  DWORD dwErrorCode; // [rsp+60h] [rbp-AC8h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+68h] [rbp-AC0h] BYREF
  DWORD Type; // [rsp+70h] [rbp-AB8h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+74h] [rbp-AB4h] BYREF
  DWORD cbMaxValueLen; // [rsp+78h] [rbp-AB0h] BYREF
  DWORD cbData; // [rsp+7Ch] [rbp-AACh] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-AA8h] BYREF
  DWORD cchName; // [rsp+88h] [rbp-AA0h] BYREF
  DWORD cValues; // [rsp+8Ch] [rbp-A9Ch] BYREF
  __int64 v33; // [rsp+90h] [rbp-A98h] BYREF
  __int128 v34; // [rsp+98h] [rbp-A90h] BYREF
  int v35; // [rsp+A8h] [rbp-A80h] BYREF
  __int128 v36; // [rsp+ACh] [rbp-A7Ch]
  __int128 v37; // [rsp+BCh] [rbp-A6Ch]
  int v38; // [rsp+CCh] [rbp-A5Ch]
  int v39; // [rsp+D0h] [rbp-A58h] BYREF
  _BYTE v40[2044]; // [rsp+D4h] [rbp-A54h] BYREF
  WCHAR Name[264]; // [rsp+8D0h] [rbp-258h] BYREF

  v33 = (__int64)a1;
  memset_0(Name, 0, 0x202u);
  cchName = 257;
  phkResult = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  Type = 0;
  cbData = 4;
  v34 = 0;
  v39 = 0;
  memset_0(v40, 0, sizeof(v40));
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  *lpcbData = 0;
  v10 = RegEnumKeyExW(a2, a3, Name, &cchName, 0, 0, 0, 0);
  dwErrorCode = v10;
  if ( v10 )
  {
    if ( v10 != 259 )
    {
      plpszSubStringArray = (LPWSTR)(*(__int64 (__fastcall **)(WCHAR *))(*(_QWORD *)a1 + 280LL))(a1);
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        LOWORD(v39) = 0;
        LOWORD(v35) = 0;
        FormatRRASErrorString(&v39, L"Cannot enumerate keys of Registry key Error: %d.", dwErrorCode);
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          v11 = (*(__int64 (__fastcall **)(WCHAR *))(*(_QWORD *)a1 + 280LL))(a1);
          v12 = &v34;
          if ( a1 != (WCHAR *)-3104LL )
            LODWORD(v12) = (_DWORD)a1 + 3104;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasDimParamTraceAdminError,
            (unsigned int)&v39,
            (_DWORD)v12,
            v11,
            (__int64)&v35);
        }
      }
      if ( dword_180070F40 )
      {
        v13 = 20102;
LABEL_10:
        RouterLogEventW(hLogHandle, 1u, v13, 1u, &plpszSubStringArray, dwErrorCode);
        goto LABEL_43;
      }
    }
    goto LABEL_43;
  }
  if ( !_wcsicmp(Name, L"IKEv2CustomPolicy") || !_wcsicmp(Name, L"TrafficSelectors") )
  {
    dwErrorCode = 1246;
    goto LABEL_43;
  }
  dwErrorCode = RegOpenKeyExW(a2, Name, 0, 0x20019u, &phkResult);
  if ( !dwErrorCode )
  {
    v17 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
    ++cbMaxValueNameLen;
    dwErrorCode = v17;
    if ( v17 )
    {
      v14 = (WCHAR *)(*(__int64 (__fastcall **)(WCHAR *))(*(_QWORD *)a1 + 280LL))(a1);
      goto LABEL_15;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      plpszSubStringArray = (LPWSTR)operator new[](cbMaxValueLen);
      std::unique_ptr<unsigned char [0]>::operator=(a4, (void **)&plpszSubStringArray);
      operator delete[](plpszSubStringArray);
      *lpcbData = cbMaxValueLen;
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        dwErrorCode = 8;
        v21 = (LPWSTR)v33;
        v33 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 280LL))(v33);
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          LOWORD(v39) = 0;
          LOWORD(v35) = 0;
          FormatRRASErrorString(&v39, L"Cannot access Registry value for Error: %d.", &dwErrorCode);
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            v22 = (*(__int64 (__fastcall **)(LPWSTR))(*(_QWORD *)v21 + 280LL))(v21);
            LODWORD(v23) = (_DWORD)v21 + 3104;
            if ( v21 == (LPWSTR)-3104LL )
              v23 = &v34;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasDimParamTraceAdminError,
              (unsigned int)&v39,
              (_DWORD)v23,
              v22,
              (__int64)&v35);
          }
        }
        if ( dword_180070F40 )
          RouterLogEventW(hLogHandle, 1u, 0x4E83u, 1u, (LPWSTR *)&v33, dwErrorCode);
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001C960);
        goto LABEL_43;
      }
    }
    dwErrorCode = RegQueryValueExW(phkResult, L"ProtocolId", 0, &Type, lpData, &cbData);
    if ( dwErrorCode )
    {
      plpszSubStringArray = (LPWSTR)L"ProtocolId";
    }
    else
    {
      if ( !cbData || Type != 4 )
        goto LABEL_32;
      if ( !CDimRouterManager::IsTransportSupported(*(_DWORD *)lpData) )
      {
        dwErrorCode = 50;
        goto LABEL_43;
      }
      dwErrorCode = RegQueryValueExW(phkResult, L"InterfaceInfo", 0, &Type, (LPBYTE)*a4, lpcbData);
      if ( !dwErrorCode )
      {
        if ( *lpcbData && Type == 3 )
          goto LABEL_43;
LABEL_32:
        dwErrorCode = 1015;
        goto LABEL_43;
      }
      plpszSubStringArray = (LPWSTR)L"InterfaceInfo";
    }
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
    {
      LOWORD(v39) = 0;
      LOWORD(v35) = 0;
      FormatRRASErrorString(&v39, L"Cannot access Registry value for %s.", &plpszSubStringArray);
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
      {
        v18 = (*(__int64 (__fastcall **)(WCHAR *))(*(_QWORD *)a1 + 280LL))(a1);
        v19 = &v34;
        if ( a1 != (WCHAR *)-3104LL )
          LODWORD(v19) = (_DWORD)a1 + 3104;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasDimParamTraceAdminError,
          (unsigned int)&v39,
          (_DWORD)v19,
          v18,
          (__int64)&v35);
      }
    }
    if ( dword_180070F40 )
    {
      v13 = 20099;
      goto LABEL_10;
    }
    goto LABEL_43;
  }
  v14 = (WCHAR *)(*(__int64 (__fastcall **)(WCHAR *))(*(_QWORD *)a1 + 280LL))(a1);
LABEL_15:
  plpszSubStringArray = v14;
  if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
  {
    LOWORD(v39) = 0;
    LOWORD(v35) = 0;
    FormatRRASErrorString(&v39, L"Cannot access the Registry key Error: %d.", dwErrorCode);
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
    {
      v15 = (*(__int64 (__fastcall **)(WCHAR *))(*(_QWORD *)a1 + 280LL))(a1);
      v16 = &v34;
      if ( a1 != (WCHAR *)-3104LL )
        LODWORD(v16) = (_DWORD)a1 + 3104;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceAdminError,
        (unsigned int)&v39,
        (_DWORD)v16,
        v15,
        (__int64)&v35);
    }
  }
  if ( dword_180070F40 )
  {
    v13 = 20100;
    goto LABEL_10;
  }
LABEL_43:
  if ( phkResult )
    RegCloseKey(phkResult);
  return dwErrorCode;
}

```

## disassembly

```asm
0x18001c418  push    rbx
0x18001c41a  push    rsi
0x18001c41b  push    rdi
0x18001c41c  push    r12
0x18001c41e  push    r13
0x18001c420  push    r14
0x18001c422  push    r15
0x18001c424  sub     rsp, 0AF0h
0x18001c42b  mov     rax, cs:__security_cookie
0x18001c432  xor     rax, rsp
0x18001c435  mov     [rsp+0B28h+var_48], rax
0x18001c43d  mov     r12, r9
0x18001c440  mov     ebx, r8d
0x18001c443  mov     r13, rdx
0x18001c446  mov     rsi, rcx
0x18001c449  mov     [rsp+0B28h+var_A98], rcx
0x18001c451  mov     r14, [rsp+0B28h+lpcbData]
0x18001c459  mov     r15, [rsp+0B28h+lpData]
0x18001c461  xor     edi, edi
0x18001c463  mov     [rsp+0B28h+dwErrorCode], edi
0x18001c467  xor     edx, edx; Val
0x18001c469  mov     r8d, 202h; Size
0x18001c46f  lea     rcx, [rsp+0B28h+Name]; void *
0x18001c477  call    memset_0
0x18001c47c  mov     [rsp+0B28h+cchName], 101h
0x18001c487  mov     [rsp+0B28h+phkResult], rdi
0x18001c48f  mov     [rsp+0B28h+cValues], edi
0x18001c496  mov     [rsp+0B28h+cbMaxValueNameLen], edi
0x18001c49a  mov     [rsp+0B28h+cbMaxValueLen], edi
0x18001c49e  mov     [rsp+0B28h+Type], edi
0x18001c4a2  mov     [rsp+0B28h+cbData], 4
0x18001c4aa  xorps   xmm0, xmm0
0x18001c4ad  movups  [rsp+0B28h+var_A90], xmm0
0x18001c4b5  mov     [rsp+0B28h+var_A58], edi
0x18001c4bc  xor     edx, edx; Val
0x18001c4be  mov     r8d, 7FCh; Size
0x18001c4c4  lea     rcx, [rsp+0B28h+var_A54]; void *
0x18001c4cc  call    memset_0
0x18001c4d1  mov     [rsp+0B28h+var_A80], edi
0x18001c4d8  xorps   xmm0, xmm0
0x18001c4db  xor     eax, eax
0x18001c4dd  movups  [rsp+0B28h+var_A7C], xmm0
0x18001c4e5  movups  [rsp+0B28h+var_A6C], xmm0
0x18001c4ed  mov     [rsp+0B28h+var_A5C], eax
0x18001c4f4  mov     [r14], edi
0x18001c4f7  mov     [rsp+0B28h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18001c4fc  mov     [rsp+0B28h+lpcchClass], rdi; lpcchClass
0x18001c501  mov     [rsp+0B28h+lpClass], rdi; lpClass
0x18001c506  mov     [rsp+0B28h+lpReserved], rdi; lpReserved
0x18001c50b  lea     r9, [rsp+0B28h+cchName]; lpcchName
0x18001c513  lea     r8, [rsp+0B28h+Name]; lpName
0x18001c51b  mov     edx, ebx; dwIndex
0x18001c51d  mov     rcx, r13; hKey
0x18001c520  call    cs:__imp_RegEnumKeyExW
0x18001c526  mov     [rsp+0B28h+dwErrorCode], eax
0x18001c52a  test    eax, eax
0x18001c52c  jz      loc_18001C624
0x18001c532  cmp     eax, 103h
0x18001c537  jz      loc_18001C96A
0x18001c53d  mov     rax, [rsi]
0x18001c540  mov     rcx, rsi
0x18001c543  mov     rax, [rax+118h]
0x18001c54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c54f  mov     [rsp+0B28h+plpszSubStringArray], rax
0x18001c554  lea     ebx, [rdi+1]
0x18001c557  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001c55d  jz      loc_18001C5E9
0x18001c563  mov     word ptr [rsp+0B28h+var_A58], di
0x18001c56b  mov     word ptr [rsp+0B28h+var_A80], di
0x18001c573  mov     r8d, [rsp+0B28h+dwErrorCode]
0x18001c578  lea     rdx, aCannotEnumerat_0; "Cannot enumerate keys of Registry key E"...
0x18001c57f  lea     rcx, [rsp+0B28h+var_A58]
0x18001c587  call    FormatRRASErrorString
0x18001c58c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001c592  jz      short loc_18001C5E9
0x18001c594  mov     rax, [rsi]
0x18001c597  mov     rcx, rsi
0x18001c59a  mov     rax, [rax+118h]
0x18001c5a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5a6  lea     rcx, [rsi+0C20h]
0x18001c5ad  lea     r9, [rsp+0B28h+var_A90]
0x18001c5b5  test    rcx, rcx
0x18001c5b8  cmovnz  r9, rcx
0x18001c5bc  lea     rcx, [rsp+0B28h+var_A80]
0x18001c5c4  mov     [rsp+0B28h+lpClass], rcx
0x18001c5c9  mov     [rsp+0B28h+lpReserved], rax
0x18001c5ce  lea     r8, [rsp+0B28h+var_A58]
0x18001c5d6  lea     rdx, RasDimParamTraceAdminError
0x18001c5dd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001c5e4  call    McTemplateU0zjzz_EventWriteTransfer
0x18001c5e9  cmp     cs:dword_180070F40, edi
0x18001c5ef  jbe     loc_18001C96A
0x18001c5f5  mov     r8d, 4E86h; dwMessageId
0x18001c5fb  mov     eax, [rsp+0B28h+dwErrorCode]
0x18001c5ff  mov     dword ptr [rsp+0B28h+lpClass], eax; dwErrorCode
0x18001c603  lea     rax, [rsp+0B28h+plpszSubStringArray]
0x18001c608  mov     [rsp+0B28h+lpReserved], rax; plpszSubStringArray
0x18001c60d  mov     r9d, ebx; dwSubStringCount
0x18001c610  mov     edx, ebx; dwEventType
0x18001c612  mov     rcx, cs:hLogHandle; hLogHandle
0x18001c619  call    cs:__imp_RouterLogEventW
0x18001c61f  jmp     loc_18001C96A
0x18001c624  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x18001c62b  lea     rcx, [rsp+0B28h+Name]; String1
0x18001c633  call    cs:__imp__wcsicmp
0x18001c639  test    eax, eax
0x18001c63b  jz      loc_18001C962
0x18001c641  lea     rdx, aTrafficselecto; "TrafficSelectors"
0x18001c648  lea     rcx, [rsp+0B28h+Name]; String1
0x18001c650  call    cs:__imp__wcsicmp
0x18001c656  test    eax, eax
0x18001c658  jz      loc_18001C962
0x18001c65e  lea     rax, [rsp+0B28h+phkResult]
0x18001c666  mov     [rsp+0B28h+lpReserved], rax; phkResult
0x18001c66b  mov     r9d, 20019h; samDesired
0x18001c671  xor     r8d, r8d; ulOptions
0x18001c674  lea     rdx, [rsp+0B28h+Name]; lpSubKey
0x18001c67c  mov     rcx, r13; hKey
0x18001c67f  call    cs:__imp_RegOpenKeyExW
0x18001c685  mov     [rsp+0B28h+dwErrorCode], eax
0x18001c689  test    eax, eax
0x18001c68b  jz      loc_18001C756
0x18001c691  mov     rax, [rsi]
0x18001c694  mov     rcx, rsi
0x18001c697  mov     rax, [rax+118h]
0x18001c69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6a3  mov     ebx, 1
0x18001c6a8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001c6ae  mov     [rsp+0B28h+plpszSubStringArray], rax
0x18001c6b3  jz      loc_18001C73F
0x18001c6b9  mov     word ptr [rsp+0B28h+var_A58], di
0x18001c6c1  mov     word ptr [rsp+0B28h+var_A80], di
0x18001c6c9  mov     r8d, [rsp+0B28h+dwErrorCode]
0x18001c6ce  lea     rdx, aCannotAccessTh; "Cannot access the Registry key Error: %"...
0x18001c6d5  lea     rcx, [rsp+0B28h+var_A58]
0x18001c6dd  call    FormatRRASErrorString
0x18001c6e2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001c6e8  jz      short loc_18001C73F
0x18001c6ea  mov     rax, [rsi]
0x18001c6ed  mov     rcx, rsi
0x18001c6f0  mov     rax, [rax+118h]
0x18001c6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6fc  lea     rcx, [rsi+0C20h]
0x18001c703  lea     r9, [rsp+0B28h+var_A90]
0x18001c70b  test    rcx, rcx
0x18001c70e  cmovnz  r9, rcx
0x18001c712  lea     rcx, [rsp+0B28h+var_A80]
0x18001c71a  mov     [rsp+0B28h+lpClass], rcx
0x18001c71f  mov     [rsp+0B28h+lpReserved], rax
0x18001c724  lea     r8, [rsp+0B28h+var_A58]
0x18001c72c  lea     rdx, RasDimParamTraceAdminError
0x18001c733  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001c73a  call    McTemplateU0zjzz_EventWriteTransfer
0x18001c73f  cmp     cs:dword_180070F40, edi
0x18001c745  jbe     loc_18001C96A
0x18001c74b  mov     r8d, 4E84h
0x18001c751  jmp     loc_18001C5FB
0x18001c756  mov     [rsp+0B28h+var_AD0], rdi; lpftLastWriteTime
0x18001c75b  mov     [rsp+0B28h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18001c760  lea     rax, [rsp+0B28h+cbMaxValueLen]
0x18001c765  mov     [rsp+0B28h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18001c76a  lea     rax, [rsp+0B28h+cbMaxValueNameLen]
0x18001c76f  mov     [rsp+0B28h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18001c774  lea     rax, [rsp+0B28h+cValues]
0x18001c77c  mov     [rsp+0B28h+lpftLastWriteTime], rax; lpcValues
0x18001c781  mov     [rsp+0B28h+lpcchClass], rdi; lpcbMaxClassLen
0x18001c786  mov     [rsp+0B28h+lpClass], rdi; lpcbMaxSubKeyLen
0x18001c78b  mov     [rsp+0B28h+lpReserved], rdi; lpcSubKeys
0x18001c790  xor     r9d, r9d; lpReserved
0x18001c793  xor     r8d, r8d; lpcchClass
0x18001c796  xor     edx, edx; lpClass
0x18001c798  mov     rcx, [rsp+0B28h+phkResult]; hKey
0x18001c7a0  call    cs:__imp_RegQueryInfoKeyW
0x18001c7a6  mov     ebx, 1
0x18001c7ab  add     [rsp+0B28h+cbMaxValueNameLen], ebx
0x18001c7af  mov     [rsp+0B28h+dwErrorCode], eax
0x18001c7b3  test    eax, eax
0x18001c7b5  jz      short loc_18001C7CE
0x18001c7b7  mov     rax, [rsi]
0x18001c7ba  mov     rcx, rsi
0x18001c7bd  mov     rax, [rax+118h]
0x18001c7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7c9  jmp     loc_18001C6A8
0x18001c7ce  mov     ecx, [rsp+0B28h+cbMaxValueLen]; unsigned __int64
0x18001c7d2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001c7d7  mov     [rsp+0B28h+plpszSubStringArray], rax
0x18001c7dc  lea     rdx, [rsp+0B28h+plpszSubStringArray]
0x18001c7e1  mov     rcx, r12
0x18001c7e4  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=(std::unique_ptr<uchar [0]> &&)
0x18001c7e9  mov     rcx, [rsp+0B28h+plpszSubStringArray]
0x18001c7ee  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001c7f4  mov     eax, [rsp+0B28h+cbMaxValueLen]
0x18001c7f8  mov     [r14], eax
0x18001c7fb  lea     rax, [rsp+0B28h+cbData]
0x18001c800  mov     [rsp+0B28h+lpClass], rax; lpcbData
0x18001c805  mov     [rsp+0B28h+lpReserved], r15; lpData
0x18001c80a  lea     r9, [rsp+0B28h+Type]; lpType
0x18001c80f  xor     r8d, r8d; lpReserved
0x18001c812  lea     r13, aProtocolid; "ProtocolId"
0x18001c819  mov     rdx, r13; lpValueName
0x18001c81c  mov     rcx, [rsp+0B28h+phkResult]; hKey
0x18001c824  call    cs:__imp_RegQueryValueExW
0x18001c82a  mov     [rsp+0B28h+dwErrorCode], eax
0x18001c82e  test    eax, eax
0x18001c830  jnz     loc_18001C8B6
0x18001c836  cmp     [rsp+0B28h+cbData], edi
0x18001c83a  jz      short loc_18001C8A2
0x18001c83c  cmp     [rsp+0B28h+Type], 4
0x18001c841  jnz     short loc_18001C8A2
0x18001c843  mov     ecx, [r15]; unsigned int
0x18001c846  call    ?IsTransportSupported@CDimRouterManager@@SA_NK@Z; CDimRouterManager::IsTransportSupported(ulong)
0x18001c84b  test    al, al
0x18001c84d  jnz     short loc_18001C85C
0x18001c84f  mov     [rsp+0B28h+dwErrorCode], 32h ; '2'
0x18001c857  jmp     loc_18001C96A
0x18001c85c  mov     [rsp+0B28h+lpClass], r14; lpcbData
0x18001c861  mov     rax, [r12]
0x18001c865  mov     [rsp+0B28h+lpReserved], rax; lpData
0x18001c86a  lea     r9, [rsp+0B28h+Type]; lpType
0x18001c86f  xor     r8d, r8d; lpReserved
0x18001c872  lea     r15, aInterfaceinfo; "InterfaceInfo"
0x18001c879  mov     rdx, r15; lpValueName
0x18001c87c  mov     rcx, [rsp+0B28h+phkResult]; hKey
0x18001c884  call    cs:__imp_RegQueryValueExW
0x18001c88a  mov     [rsp+0B28h+dwErrorCode], eax
0x18001c88e  test    eax, eax
0x18001c890  jnz     short loc_18001C8AF
0x18001c892  cmp     [r14], edi
0x18001c895  jz      short loc_18001C8A2
0x18001c897  cmp     [rsp+0B28h+Type], 3
0x18001c89c  jz      loc_18001C96A
0x18001c8a2  mov     [rsp+0B28h+dwErrorCode], 3F7h
0x18001c8aa  jmp     loc_18001C96A
0x18001c8af  mov     [rsp+0B28h+plpszSubStringArray], r15
0x18001c8b4  jmp     short loc_18001C8BB
0x18001c8b6  mov     [rsp+0B28h+plpszSubStringArray], r13
0x18001c8bb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001c8c1  jz      loc_18001C94D
0x18001c8c7  mov     word ptr [rsp+0B28h+var_A58], di
0x18001c8cf  mov     word ptr [rsp+0B28h+var_A80], di
0x18001c8d7  lea     r8, [rsp+0B28h+plpszSubStringArray]
0x18001c8dc  lea     rdx, aCannotAccessRe; "Cannot access Registry value for %s."
0x18001c8e3  lea     rcx, [rsp+0B28h+var_A58]
0x18001c8eb  call    FormatRRASErrorString
0x18001c8f0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18001c8f6  jz      short loc_18001C94D
0x18001c8f8  mov     rax, [rsi]
0x18001c8fb  mov     rcx, rsi
0x18001c8fe  mov     rax, [rax+118h]
0x18001c905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c90a  lea     rcx, [rsi+0C20h]
0x18001c911  lea     r9, [rsp+0B28h+var_A90]
0x18001c919  test    rcx, rcx
0x18001c91c  cmovnz  r9, rcx
0x18001c920  lea     rcx, [rsp+0B28h+var_A80]
0x18001c928  mov     [rsp+0B28h+lpClass], rcx
0x18001c92d  mov     [rsp+0B28h+lpReserved], rax
0x18001c932  lea     r8, [rsp+0B28h+var_A58]
0x18001c93a  lea     rdx, RasDimParamTraceAdminError
0x18001c941  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001c948  call    McTemplateU0zjzz_EventWriteTransfer
0x18001c94d  cmp     cs:dword_180070F40, edi
0x18001c953  jbe     short loc_18001C96A
0x18001c955  mov     r8d, 4E83h
0x18001c95b  jmp     loc_18001C5FB
0x18001c960  jmp     short loc_18001C96A
0x18001c962  mov     [rsp+0B28h+dwErrorCode], 4DEh
0x18001c96a  mov     rcx, [rsp+0B28h+phkResult]; hKey
0x18001c972  test    rcx, rcx
0x18001c975  jz      short loc_18001C97D
0x18001c977  call    cs:__imp_RegCloseKey
0x18001c97d  mov     eax, [rsp+0B28h+dwErrorCode]
0x18001c981  mov     rcx, [rsp+0B28h+var_48]
0x18001c989  xor     rcx, rsp; StackCookie
0x18001c98c  call    __security_check_cookie
0x18001c991  add     rsp, 0AF0h
0x18001c998  pop     r15
0x18001c99a  pop     r14
0x18001c99c  pop     r13
0x18001c99e  pop     r12
0x18001c9a0  pop     rdi
0x18001c9a1  pop     rsi
0x18001c9a2  pop     rbx
0x18001c9a3  retn
```
