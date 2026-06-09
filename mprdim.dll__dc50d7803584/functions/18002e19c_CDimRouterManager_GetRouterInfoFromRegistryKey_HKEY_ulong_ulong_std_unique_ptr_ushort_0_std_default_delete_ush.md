# CDimRouterManager::GetRouterInfoFromRegistryKey(HKEY__ *,ulong,ulong &,std::unique_ptr<ushort [0],std::default_delete<ushort [0]>> &,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &,ulong &,std::unique_ptr<uchar [0],std::default_delete<uchar [0]>> &,ulong &)

- ea: `0x18002e19c`
- end: `0x18002e65e`
- name: `?GetRouterInfoFromRegistryKey@CDimRouterManager@@AEAAKPEAUHKEY__@@KAEAKAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@4@131@Z`
- size: `1218`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002eb5c`

## callees

- `0x18000b654`
- `0x18000def0`
- `0x18001abd0`
- `0x180023384`
- `0x18002e19c`
- `0x18002eb44`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002e348`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002e37d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002e3a7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002e348`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002e37d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002e3a7`
- `ADVAPI32!RegOpenKeyExW` at `0x18002e2a8`
- `ADVAPI32!RegOpenKeyExW` at `0x18002e2a8`
- `ADVAPI32!RegCloseKey` at `0x18002e62c`
- `ADVAPI32!RegCloseKey` at `0x18002e62c`
- `ADVAPI32!RegQueryValueExW` at `0x18002e3d4`
- `ADVAPI32!RegQueryValueExW` at `0x18002e456`
- `ADVAPI32!RegQueryValueExW` at `0x18002e4b2`
- `ADVAPI32!RegQueryValueExW` at `0x18002e52c`
- `ADVAPI32!RegQueryValueExW` at `0x18002e3d4`
- `ADVAPI32!RegQueryValueExW` at `0x18002e456`
- `ADVAPI32!RegQueryValueExW` at `0x18002e4b2`
- `ADVAPI32!RegQueryValueExW` at `0x18002e52c`
- `ADVAPI32!RegEnumKeyExW` at `0x18002e275`
- `ADVAPI32!RegEnumKeyExW` at `0x18002e275`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002e2fc`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18002e2fc`

## string_xrefs

- `0x18002e3ba`: `ProtocolId`
- `0x18002e3ed`: `GetRouterInfoFromRegistryKey:: RegQueryValueEx failed for ProtocolId with error %d`
- `0x18002e609`: `GetRouterInfoFromRegistryKey:: ProtocolId is not of type REG_DWORD`
- `0x18002e447`: `DLLPath`
- `0x18002e46f`: `GetRouterInfoFromRegistryKey:: RegQueryValueEx failed for DllPath with error %d`
- `0x18002e5f2`: `GetRouterInfoFromRegistryKey:: DllPath is not of type REG_EXPAND_SZ`
- `0x18002e4d0`: `GetRouterInfoFromRegistryKey:: RegQueryValueEx failed for GlobalInfo with error %d`
- `0x18002e4ec`: `GetRouterInfoFromRegistryKey:: GlobalInfo is not of type REG_BINARY`
- `0x18002e54a`: `GetRouterInfoFromRegistryKey:: RegQueryValueEx failed for GlobalInterfaceInfo with error %d`
- `0x18002e56a`: `GetRouterInfoFromRegistryKey:: GlobalInterfaceInfo is not of type REG_BINARY`
- `0x18002e5a6`: `GetRouterInfoFromRegistryKey:: ProtocolId %d is not supported`

## pseudocode

```c
__int64 __fastcall CDimRouterManager::GetRouterInfoFromRegistryKey(
        __int64 a1,
        HKEY a2,
        DWORD a3,
        BYTE *a4,
        __int64 *a5,
        void **a6,
        LPDWORD a7,
        void **a8,
        LPDWORD lpcbData)
{
  LSTATUS v12; // eax
  unsigned int v13; // ebx
  LSTATUS v14; // eax
  void *v15; // rax
  LPBYTE *v16; // r14
  unsigned __int64 v17; // rcx
  HKEY v18; // rcx
  const wchar_t *v19; // rdx
  const wchar_t *v20; // r8
  LSTATUS v21; // eax
  LSTATUS v22; // eax
  unsigned int v23; // ecx
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  void *v26; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueLen; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD v29; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbData; // [rsp+88h] [rbp-78h] BYREF
  DWORD cchName; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD cValues; // [rsp+90h] [rbp-70h] BYREF
  void **v34; // [rsp+98h] [rbp-68h]
  int v35; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v36[2044]; // [rsp+A4h] [rbp-5Ch] BYREF
  WCHAR Name[264]; // [rsp+8A0h] [rbp+7A0h] BYREF

  v34 = a6;
  memset_0(Name, 0, 0x202u);
  cbData = 4;
  phkResult = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  Type = 0;
  v29 = 0;
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  cchName = 257;
  *a7 = 0;
  *lpcbData = 0;
  v12 = RegEnumKeyExW(a2, a3, Name, &cchName, 0, 0, 0, 0);
  v13 = v12;
  if ( v12 && v12 != 234 )
    goto LABEL_44;
  v13 = RegOpenKeyExW(a2, Name, 0, 0x20019u, &phkResult);
  if ( v13 )
    goto LABEL_44;
  v14 = RegQueryInfoKeyW(phkResult, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  ++cbMaxValueNameLen;
  v13 = v14;
  if ( v14 )
    goto LABEL_44;
  v26 = operator new[](saturated_mul(cbMaxValueLen + 2LL, 2u));
  std::unique_ptr<unsigned short [0]>::operator=(a5, (__int64 *)&v26);
  operator delete[](v26);
  v29 = 2 * cbMaxValueLen + 4;
  v15 = operator new[](cbMaxValueLen);
  v16 = (LPBYTE *)v34;
  v26 = v15;
  std::unique_ptr<unsigned char [0]>::operator=(v34, &v26);
  operator delete[](v26);
  v17 = cbMaxValueLen;
  *a7 = cbMaxValueLen;
  v26 = operator new[](v17);
  std::unique_ptr<unsigned char [0]>::operator=(a8, &v26);
  operator delete[](v26);
  v18 = phkResult;
  *lpcbData = cbMaxValueLen;
  v13 = RegQueryValueExW(v18, L"ProtocolId", 0, &Type, a4, &cbData);
  if ( v13 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_44;
    v19 = L"GetRouterInfoFromRegistryKey:: RegQueryValueEx failed for ProtocolId with error %d";
LABEL_8:
    LOWORD(v35) = 0;
    FormatRRASErrorString(&v35, v19, v13);
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_44;
    v20 = (const wchar_t *)&v35;
LABEL_43:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, v20);
    goto LABEL_44;
  }
  if ( !cbData || Type != 4 )
  {
    v13 = 1015;
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_44;
    v20 = L"GetRouterInfoFromRegistryKey:: ProtocolId is not of type REG_DWORD";
    goto LABEL_43;
  }
  v13 = RegQueryValueExW(phkResult, L"DLLPath", 0, &Type, (LPBYTE)*a5, &v29);
  if ( v13 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_44;
    v19 = L"GetRouterInfoFromRegistryKey:: RegQueryValueEx failed for DllPath with error %d";
    goto LABEL_8;
  }
  if ( !v29 || Type != 2 )
  {
    v13 = 1015;
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_44;
    v20 = L"GetRouterInfoFromRegistryKey:: DllPath is not of type REG_EXPAND_SZ";
    goto LABEL_43;
  }
  v21 = RegQueryValueExW(phkResult, L"GlobalInfo", 0, &Type, (LPBYTE)*a8, lpcbData);
  v13 = v21;
  if ( v21 )
  {
    if ( v21 != 2 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_44;
      v19 = L"GetRouterInfoFromRegistryKey:: RegQueryValueEx failed for GlobalInfo with error %d";
      goto LABEL_8;
    }
  }
  else
  {
    if ( Type == 3 )
      goto LABEL_25;
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasDimTraceInfo,
        L"GetRouterInfoFromRegistryKey:: GlobalInfo is not of type REG_BINARY");
  }
  *lpcbData = 0;
LABEL_25:
  v22 = RegQueryValueExW(phkResult, L"GlobalInterfaceInfo", 0, &Type, *v16, a7);
  v13 = v22;
  if ( v22 )
  {
    if ( v22 != 2 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_44;
      v19 = L"GetRouterInfoFromRegistryKey:: RegQueryValueEx failed for GlobalInterfaceInfo with error %d";
      goto LABEL_8;
    }
    v13 = 0;
  }
  else
  {
    if ( Type == 3 )
      goto LABEL_34;
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasDimTraceInfo,
        L"GetRouterInfoFromRegistryKey:: GlobalInterfaceInfo is not of type REG_BINARY");
  }
  *a7 = 0;
LABEL_34:
  if ( !CDimRouterManager::IsTransportSupported(*(_DWORD *)a4) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v35) = 0;
      FormatRRASErrorString(&v35, L"GetRouterInfoFromRegistryKey:: ProtocolId %d is not supported", v23);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v35);
    }
    v13 = 50;
  }
LABEL_44:
  if ( phkResult )
    RegCloseKey(phkResult);
  return v13;
}

```

## disassembly

```asm
0x18002e19c  mov     [rsp-8+arg_0], rbx
0x18002e1a1  push    rbp
0x18002e1a2  push    rsi
0x18002e1a3  push    rdi
0x18002e1a4  push    r12
0x18002e1a6  push    r13
0x18002e1a8  push    r14
0x18002e1aa  push    r15
0x18002e1ac  lea     rbp, [rsp-9C0h]
0x18002e1b4  sub     rsp, 0AC0h
0x18002e1bb  mov     rax, cs:__security_cookie
0x18002e1c2  xor     rax, rsp
0x18002e1c5  mov     [rbp+9F0h+var_40], rax
0x18002e1cc  mov     rax, [rbp+9F0h+arg_28]
0x18002e1d3  lea     rcx, [rbp+9F0h+Name]; void *
0x18002e1da  mov     r15, [rbp+9F0h+arg_20]
0x18002e1e1  mov     ebx, r8d
0x18002e1e4  mov     rdi, [rbp+9F0h+arg_30]
0x18002e1eb  mov     r14, rdx
0x18002e1ee  mov     r12, [rbp+9F0h+arg_38]
0x18002e1f5  xor     edx, edx; Val
0x18002e1f7  mov     rsi, [rbp+9F0h+lpcbData]
0x18002e1fe  mov     r8d, 202h; Size
0x18002e204  mov     [rbp+9F0h+var_A58], rax
0x18002e208  mov     r13, r9
0x18002e20b  call    memset_0
0x18002e210  xor     ecx, ecx
0x18002e212  mov     [rbp+9F0h+cbData], 4
0x18002e219  mov     [rbp+9F0h+phkResult], rcx
0x18002e21d  xor     edx, edx; Val
0x18002e21f  mov     [rbp+9F0h+cValues], ecx
0x18002e222  mov     r8d, 7FCh; Size
0x18002e228  mov     [rsp+0AF0h+cbMaxValueNameLen], ecx
0x18002e22c  mov     [rsp+0AF0h+cbMaxValueLen], ecx
0x18002e230  mov     [rsp+0AF0h+Type], ecx
0x18002e234  mov     [rsp+0AF0h+var_A78], ecx
0x18002e238  mov     [rbp+9F0h+var_A50], ecx
0x18002e23b  lea     rcx, [rbp+9F0h+var_A4C]; void *
0x18002e23f  call    memset_0
0x18002e244  xor     eax, eax
0x18002e246  mov     [rbp+9F0h+cchName], 101h
0x18002e24d  mov     [rsp+0AF0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18002e252  lea     r9, [rbp+9F0h+cchName]; lpcchName
0x18002e256  mov     [rsp+0AF0h+lpcchClass], rax; lpcchClass
0x18002e25b  lea     r8, [rbp+9F0h+Name]; lpName
0x18002e262  mov     [rsp+0AF0h+lpClass], rax; lpClass
0x18002e267  mov     edx, ebx; dwIndex
0x18002e269  mov     [rdi], eax
0x18002e26b  mov     rcx, r14; hKey
0x18002e26e  mov     [rsp+0AF0h+lpReserved], rax; lpReserved
0x18002e273  mov     [rsi], eax
0x18002e275  call    cs:__imp_RegEnumKeyExW
0x18002e27b  mov     ebx, eax
0x18002e27d  test    eax, eax
0x18002e27f  jz      short loc_18002E28C
0x18002e281  cmp     eax, 0EAh
0x18002e286  jnz     loc_18002E623
0x18002e28c  lea     rax, [rbp+9F0h+phkResult]
0x18002e290  mov     r9d, 20019h; samDesired
0x18002e296  xor     r8d, r8d; ulOptions
0x18002e299  mov     [rsp+0AF0h+lpReserved], rax; phkResult
0x18002e29e  lea     rdx, [rbp+9F0h+Name]; lpSubKey
0x18002e2a5  mov     rcx, r14; hKey
0x18002e2a8  call    cs:__imp_RegOpenKeyExW
0x18002e2ae  xor     ecx, ecx
0x18002e2b0  mov     ebx, eax
0x18002e2b2  test    eax, eax
0x18002e2b4  jnz     loc_18002E623
0x18002e2ba  mov     [rsp+0AF0h+var_A98], rcx; lpftLastWriteTime
0x18002e2bf  lea     rax, [rsp+0AF0h+cbMaxValueLen]
0x18002e2c4  mov     [rsp+0AF0h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x18002e2c9  xor     r9d, r9d; lpReserved
0x18002e2cc  mov     [rsp+0AF0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18002e2d1  xor     r8d, r8d; lpcchClass
0x18002e2d4  lea     rax, [rsp+0AF0h+cbMaxValueNameLen]
0x18002e2d9  xor     edx, edx; lpClass
0x18002e2db  mov     [rsp+0AF0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18002e2e0  lea     rax, [rbp+9F0h+cValues]
0x18002e2e4  mov     [rsp+0AF0h+lpftLastWriteTime], rax; lpcValues
0x18002e2e9  mov     [rsp+0AF0h+lpcchClass], rcx; lpcbMaxClassLen
0x18002e2ee  mov     [rsp+0AF0h+lpClass], rcx; lpcbMaxSubKeyLen
0x18002e2f3  mov     [rsp+0AF0h+lpReserved], rcx; lpcSubKeys
0x18002e2f8  mov     rcx, [rbp+9F0h+phkResult]; hKey
0x18002e2fc  call    cs:__imp_RegQueryInfoKeyW
0x18002e302  inc     [rsp+0AF0h+cbMaxValueNameLen]
0x18002e306  mov     ebx, eax
0x18002e308  test    eax, eax
0x18002e30a  jnz     loc_18002E623
0x18002e310  mov     ecx, [rsp+0AF0h+cbMaxValueLen]
0x18002e314  lea     eax, [rbx+2]
0x18002e317  add     rcx, 2
0x18002e31b  mul     rcx
0x18002e31e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002e325  cmovb   rax, rcx
0x18002e329  mov     rcx, rax; unsigned __int64
0x18002e32c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002e331  lea     rdx, [rsp+0AF0h+var_A88]
0x18002e336  mov     [rsp+0AF0h+var_A88], rax
0x18002e33b  mov     rcx, r15
0x18002e33e  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<ushort [0]>::operator=(std::unique_ptr<ushort [0]> &&)
0x18002e343  mov     rcx, [rsp+0AF0h+var_A88]
0x18002e348  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002e34e  mov     ecx, [rsp+0AF0h+cbMaxValueLen]; unsigned __int64
0x18002e352  lea     eax, ds:4[rcx*2]
0x18002e359  mov     [rsp+0AF0h+var_A78], eax
0x18002e35d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002e362  mov     r14, [rbp+9F0h+var_A58]
0x18002e366  lea     rdx, [rsp+0AF0h+var_A88]
0x18002e36b  mov     rcx, r14
0x18002e36e  mov     [rsp+0AF0h+var_A88], rax
0x18002e373  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=(std::unique_ptr<uchar [0]> &&)
0x18002e378  mov     rcx, [rsp+0AF0h+var_A88]
0x18002e37d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002e383  mov     eax, [rsp+0AF0h+cbMaxValueLen]
0x18002e387  mov     ecx, eax; unsigned __int64
0x18002e389  mov     [rdi], eax
0x18002e38b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002e390  lea     rdx, [rsp+0AF0h+var_A88]
0x18002e395  mov     [rsp+0AF0h+var_A88], rax
0x18002e39a  mov     rcx, r12
0x18002e39d  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=(std::unique_ptr<uchar [0]> &&)
0x18002e3a2  mov     rcx, [rsp+0AF0h+var_A88]
0x18002e3a7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002e3ad  mov     eax, [rsp+0AF0h+cbMaxValueLen]
0x18002e3b1  lea     r9, [rsp+0AF0h+Type]; lpType
0x18002e3b6  mov     rcx, [rbp+9F0h+phkResult]; hKey
0x18002e3ba  lea     rdx, aProtocolid; "ProtocolId"
0x18002e3c1  mov     [rsi], eax
0x18002e3c3  xor     r8d, r8d; lpReserved
0x18002e3c6  lea     rax, [rbp+9F0h+cbData]
0x18002e3ca  mov     [rsp+0AF0h+lpClass], rax; lpcbData
0x18002e3cf  mov     [rsp+0AF0h+lpReserved], r13; lpData
0x18002e3d4  call    cs:__imp_RegQueryValueExW
0x18002e3da  mov     ebx, eax
0x18002e3dc  test    eax, eax
0x18002e3de  jz      short loc_18002E41C
0x18002e3e0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002e3e7  jz      loc_18002E623
0x18002e3ed  lea     rdx, aGetrouterinfof; "GetRouterInfoFromRegistryKey:: RegQuery"...
0x18002e3f4  xor     eax, eax
0x18002e3f6  lea     rcx, [rbp+9F0h+var_A50]
0x18002e3fa  mov     r8d, ebx
0x18002e3fd  mov     word ptr [rbp+9F0h+var_A50], ax
0x18002e401  call    FormatRRASErrorString
0x18002e406  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002e40d  jz      loc_18002E623
0x18002e413  lea     r8, [rbp+9F0h+var_A50]
0x18002e417  jmp     loc_18002E610
0x18002e41c  cmp     [rbp+9F0h+cbData], 0
0x18002e420  jz      loc_18002E5FB
0x18002e426  cmp     [rsp+0AF0h+Type], 4
0x18002e42b  jnz     loc_18002E5FB
0x18002e431  mov     rcx, [rbp+9F0h+phkResult]; hKey
0x18002e435  lea     rax, [rsp+0AF0h+var_A78]
0x18002e43a  mov     [rsp+0AF0h+lpClass], rax; lpcbData
0x18002e43f  lea     r9, [rsp+0AF0h+Type]; lpType
0x18002e444  mov     rax, [r15]
0x18002e447  lea     rdx, aDllpath; "DLLPath"
0x18002e44e  xor     r8d, r8d; lpReserved
0x18002e451  mov     [rsp+0AF0h+lpReserved], rax; lpData
0x18002e456  call    cs:__imp_RegQueryValueExW
0x18002e45c  mov     ebx, eax
0x18002e45e  test    eax, eax
0x18002e460  jz      short loc_18002E47B
0x18002e462  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002e469  jz      loc_18002E623
0x18002e46f  lea     rdx, aGetrouterinfof_2; "GetRouterInfoFromRegistryKey:: RegQuery"...
0x18002e476  jmp     loc_18002E3F4
0x18002e47b  cmp     [rsp+0AF0h+var_A78], 0
0x18002e480  jz      loc_18002E5E4
0x18002e486  cmp     [rsp+0AF0h+Type], 2
0x18002e48b  jnz     loc_18002E5E4
0x18002e491  mov     rax, [r12]
0x18002e495  lea     r9, [rsp+0AF0h+Type]; lpType
0x18002e49a  mov     rcx, [rbp+9F0h+phkResult]; hKey
0x18002e49e  lea     rdx, aGlobalinfo; "GlobalInfo"
0x18002e4a5  mov     [rsp+0AF0h+lpClass], rsi; lpcbData
0x18002e4aa  xor     r8d, r8d; lpReserved
0x18002e4ad  mov     [rsp+0AF0h+lpReserved], rax; lpData
0x18002e4b2  call    cs:__imp_RegQueryValueExW
0x18002e4b8  mov     ebx, eax
0x18002e4ba  test    eax, eax
0x18002e4bc  jz      short loc_18002E4DC
0x18002e4be  cmp     eax, 2
0x18002e4c1  jz      short loc_18002E506
0x18002e4c3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002e4ca  jz      loc_18002E623
0x18002e4d0  lea     rdx, aGetrouterinfof_3; "GetRouterInfoFromRegistryKey:: RegQuery"...
0x18002e4d7  jmp     loc_18002E3F4
0x18002e4dc  cmp     [rsp+0AF0h+Type], 3
0x18002e4e1  jz      short loc_18002E50C
0x18002e4e3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18002e4ea  jz      short loc_18002E506
0x18002e4ec  lea     r8, aGetrouterinfof_7; "GetRouterInfoFromRegistryKey:: GlobalIn"...
0x18002e4f3  lea     rdx, RasDimTraceInfo
0x18002e4fa  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e501  call    McTemplateU0z_EventWriteTransfer
0x18002e506  mov     dword ptr [rsi], 0
0x18002e50c  mov     rax, [r14]
0x18002e50f  lea     r9, [rsp+0AF0h+Type]; lpType
0x18002e514  mov     rcx, [rbp+9F0h+phkResult]; hKey
0x18002e518  lea     rdx, aGlobalinterfac; "GlobalInterfaceInfo"
0x18002e51f  mov     [rsp+0AF0h+lpClass], rdi; lpcbData
0x18002e524  xor     r8d, r8d; lpReserved
0x18002e527  mov     [rsp+0AF0h+lpReserved], rax; lpData
0x18002e52c  call    cs:__imp_RegQueryValueExW
0x18002e532  mov     ebx, eax
0x18002e534  test    eax, eax
0x18002e536  jz      short loc_18002E55A
0x18002e538  cmp     eax, 2
0x18002e53b  jz      short loc_18002E556
0x18002e53d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002e544  jz      loc_18002E623
0x18002e54a  lea     rdx, aGetrouterinfof_4; "GetRouterInfoFromRegistryKey:: RegQuery"...
0x18002e551  jmp     loc_18002E3F4
0x18002e556  xor     ebx, ebx
0x18002e558  jmp     short loc_18002E584
0x18002e55a  cmp     [rsp+0AF0h+Type], 3
0x18002e55f  jz      short loc_18002E58A
0x18002e561  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18002e568  jz      short loc_18002E584
0x18002e56a  lea     r8, aGetrouterinfof_1; "GetRouterInfoFromRegistryKey:: GlobalIn"...
0x18002e571  lea     rdx, RasDimTraceInfo
0x18002e578  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e57f  call    McTemplateU0z_EventWriteTransfer
0x18002e584  mov     dword ptr [rdi], 0
0x18002e58a  mov     ecx, [r13+0]; unsigned int
0x18002e58e  call    ?IsTransportSupported@CDimRouterManager@@SA_NK@Z; CDimRouterManager::IsTransportSupported(ulong)
0x18002e593  test    al, al
0x18002e595  jnz     loc_18002E623
0x18002e59b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002e5a2  jz      short loc_18002E5DD
0x18002e5a4  xor     eax, eax
0x18002e5a6  lea     rdx, aGetrouterinfof_0; "GetRouterInfoFromRegistryKey:: Protocol"...
0x18002e5ad  mov     r8d, ecx
0x18002e5b0  mov     word ptr [rbp+9F0h+var_A50], ax
0x18002e5b4  lea     rcx, [rbp+9F0h+var_A50]
0x18002e5b8  call    FormatRRASErrorString
0x18002e5bd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002e5c4  jz      short loc_18002E5DD
0x18002e5c6  lea     r8, [rbp+9F0h+var_A50]
0x18002e5ca  lea     rdx, RasDimTraceError
0x18002e5d1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e5d8  call    McTemplateU0z_EventWriteTransfer
0x18002e5dd  mov     ebx, 32h ; '2'
0x18002e5e2  jmp     short loc_18002E623
0x18002e5e4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002e5eb  mov     ebx, 3F7h
0x18002e5f0  jz      short loc_18002E623
0x18002e5f2  lea     r8, aGetrouterinfof_5; "GetRouterInfoFromRegistryKey:: DllPath "...
0x18002e5f9  jmp     short loc_18002E610
0x18002e5fb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002e602  mov     ebx, 3F7h
0x18002e607  jz      short loc_18002E623
0x18002e609  lea     r8, aGetrouterinfof_6; "GetRouterInfoFromRegistryKey:: Protocol"...
0x18002e610  lea     rdx, RasDimTraceError
0x18002e617  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002e61e  call    McTemplateU0z_EventWriteTransfer
0x18002e623  mov     rcx, [rbp+9F0h+phkResult]; hKey
0x18002e627  test    rcx, rcx
0x18002e62a  jz      short loc_18002E632
0x18002e62c  call    cs:__imp_RegCloseKey
0x18002e632  mov     eax, ebx
0x18002e634  mov     rcx, [rbp+9F0h+var_40]
0x18002e63b  xor     rcx, rsp; StackCookie
0x18002e63e  call    __security_check_cookie
0x18002e643  mov     rbx, [rsp+0AF0h+arg_0]
0x18002e64b  add     rsp, 0AC0h
0x18002e652  pop     r15
0x18002e654  pop     r14
0x18002e656  pop     r13
0x18002e658  pop     r12
0x18002e65a  pop     rdi
0x18002e65b  pop     rsi
0x18002e65c  pop     rbp
0x18002e65d  retn
```
