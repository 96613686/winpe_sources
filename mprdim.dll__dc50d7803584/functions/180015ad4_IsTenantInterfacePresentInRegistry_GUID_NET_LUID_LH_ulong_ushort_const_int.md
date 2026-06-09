# IsTenantInterfacePresentInRegistry(_GUID *,_NET_LUID_LH,ulong,ushort const *,int *)

- ea: `0x180015ad4`
- end: `0x1800161af`
- name: `?IsTenantInterfacePresentInRegistry@@YAKPEAU_GUID@@T_NET_LUID_LH@@KPEBGPEAH@Z`
- size: `1755`
- prototype: `unsigned int __fastcall(struct _GUID *, union _NET_LUID_LH, unsigned int, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015490`

## callees

- `0x180009bf8`
- `0x18000df70`
- `0x180015ad4`
- `0x180016eb8`
- `0x180033e90`
- `0x180036a40`
- `0x180037e0c`
- `0x180045d40`
- `0x180046e06`
- `0x180046e2a`
- `0x180046e70`
- `0x180046f00`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180015fe9`
- `msvcrt!_wcsicmp` at `0x180015fe9`
- `ADVAPI32!RegOpenKeyExW` at `0x180015c37`
- `ADVAPI32!RegOpenKeyExW` at `0x180015da3`
- `ADVAPI32!RegOpenKeyExW` at `0x180015c37`
- `ADVAPI32!RegOpenKeyExW` at `0x180015da3`
- `ADVAPI32!RegSetValueExW` at `0x18001602a`
- `ADVAPI32!RegSetValueExW` at `0x18001602a`
- `ADVAPI32!RegCloseKey` at `0x180015e24`
- `ADVAPI32!RegCloseKey` at `0x18001616d`
- `ADVAPI32!RegCloseKey` at `0x18001617d`
- `ADVAPI32!RegCloseKey` at `0x180015e24`
- `ADVAPI32!RegCloseKey` at `0x18001616d`
- `ADVAPI32!RegCloseKey` at `0x18001617d`
- `ADVAPI32!RegQueryValueExW` at `0x180015fbe`
- `ADVAPI32!RegQueryValueExW` at `0x180015fbe`
- `ADVAPI32!RegEnumKeyExW` at `0x180015d6e`
- `ADVAPI32!RegEnumKeyExW` at `0x180015d6e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180015d06`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180015d06`

## string_xrefs

- `0x180015c5a`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x180015be4`: `System\CurrentControlSet\Services\RemoteAccess\RoutingDomains\%ws\Interfaces`
- `0x180015c53`: `IsTenantInterfacePresentInRegistry: Error %d occured while opening registry key %s.`
- `0x180015d26`: `IsTenantInterfacePresentInRegistry:Error %d occured while enumerating subkeys under registry key %s. #1`
- `0x180015e5b`: `IsTenantInterfacePresentInRegistry:Error %d occured while enumerating subkeys under registry key %s. #2`
- `0x18001614a`: `IsTenantInterfacePresentInRegistry:Error %d occured while opening registry key %ws.`
- `0x180016117`: `IsTenantInterfacePresentInRegistry:ReadInterfaceExtraInfo failed with error %d `
- `0x180015e8c`: `IsTenantInterfacePresentInRegistry: Matching Interface (%ws) found in the registry`
- `0x180015eff`: `IsTenantInterfacePresentInRegistry: Matching Interface (%ws) found in the registry with same VSID but differnet LUID`
- `0x18001605b`: `IsTenantInterfacePresentInRegistry: Updated InterfaceName from '%ws' to '%ws'`
- `0x1800160a3`: `IsTenantInterfacePresentInRegistry: Failed to update InterfaceName from '%ws' to '%ws' (error=%d)`

## pseudocode

```c
__int64 __fastcall IsTenantInterfacePresentInRegistry(
        struct _GUID *a1,
        union _NET_LUID_LH a2,
        DWORD a3,
        const unsigned __int16 *a4,
        int *a5)
{
  int v5; // r12d
  unsigned int v9; // eax
  unsigned int v10; // esi
  const wchar_t *v11; // rdx
  WCHAR *v12; // r9
  DWORD v13; // edi
  unsigned int InterfaceExtraInfo; // eax
  __int64 v15; // rax
  LSTATUS v16; // eax
  __int64 *v17; // rdx
  DWORD dwFlags[2]; // [rsp+20h] [rbp-E0h]
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+70h] [rbp-90h] BYREF
  DWORD cSubKeys; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxValueLen; // [rsp+88h] [rbp-78h] BYREF
  DWORD cValues; // [rsp+8Ch] [rbp-74h] BYREF
  size_t pcbRemaining; // [rsp+90h] [rbp-70h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+98h] [rbp-68h] BYREF
  __int128 v30; // [rsp+A0h] [rbp-60h]
  struct in_addr v31; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v32[24]; // [rsp+B4h] [rbp-4Ch] BYREF
  _QWORD Buf1[2]; // [rsp+CCh] [rbp-34h] BYREF
  int v34; // [rsp+DCh] [rbp-24h]
  union _NET_LUID_LH v35; // [rsp+E0h] [rbp-20h]
  int v36; // [rsp+380h] [rbp+280h] BYREF
  __int128 v37; // [rsp+384h] [rbp+284h]
  __int128 v38; // [rsp+394h] [rbp+294h]
  int v39; // [rsp+3A4h] [rbp+2A4h]
  WCHAR Name[56]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _BYTE v41[80]; // [rsp+420h] [rbp+320h] BYREF
  int v42; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v43[2044]; // [rsp+474h] [rbp+374h] BYREF
  wchar_t Data[256]; // [rsp+C70h] [rbp+B70h] BYREF
  __int16 v45; // [rsp+E70h] [rbp+D70h]
  wchar_t pszDest[256]; // [rsp+E80h] [rbp+D80h] BYREF

  v5 = 0;
  Type = a3;
  phkResult = 0;
  cbMaxValueNameLen = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  cSubKeys = 0;
  cchName = 0;
  hKey = 0;
  memset_0(v41, 0, sizeof(v41));
  memset_0(pszDest, 0, sizeof(pszDest));
  v31 = 0;
  memset_0(v32, 0, 0x2C4u);
  v42 = 0;
  memset_0(v43, 0, sizeof(v43));
  v36 = 0;
  v39 = 0;
  v37 = 0;
  v38 = 0;
  v30 = 0;
  MprConvertGuidToString(a1, 40, v41);
  StringCbPrintfExW(
    pszDest,
    0x100u,
    &ppszDestEnd,
    &pcbRemaining,
    0,
    L"System\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains\\%ws\\Interfaces",
    v41);
  if ( !a1 || !a5 )
  {
    v10 = 87;
    goto LABEL_58;
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &phkResult);
  v10 = v9;
  if ( v9 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_58;
    v11 = L"IsTenantInterfacePresentInRegistry: Error %d occured while opening registry key %s.";
  }
  else
  {
    v9 = RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
    ++cbMaxValueNameLen;
    v10 = v9;
    if ( !v9 )
    {
      v13 = 0;
      if ( !cSubKeys )
      {
LABEL_52:
        *a5 = v5;
        goto LABEL_58;
      }
      while ( 1 )
      {
        cchName = 50;
        v9 = RegEnumKeyExW(phkResult, v13, Name, &cchName, 0, 0, 0, 0);
        v10 = v9;
        if ( v9 && v9 != 234 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
            goto LABEL_58;
          v11 = L"IsTenantInterfacePresentInRegistry:Error %d occured while enumerating subkeys under registry key %s. #2";
          goto LABEL_6;
        }
        v9 = RegOpenKeyExW(phkResult, Name, 0, 0x2001Fu, &hKey);
        v10 = v9;
        if ( v9 )
          break;
        InterfaceExtraInfo = ReadInterfaceExtraInfo(hKey);
        v10 = InterfaceExtraInfo;
        if ( InterfaceExtraInfo )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
            goto LABEL_58;
          LOWORD(v42) = 0;
          LOWORD(v36) = 0;
          FormatRRASErrorString(
            &v42,
            L"IsTenantInterfacePresentInRegistry:ReadInterfaceExtraInfo failed with error %d ",
            InterfaceExtraInfo);
          goto LABEL_8;
        }
        if ( v34 == Type
          && (!memcmp_0(Buf1, &GUID_NULL, InterfaceExtraInfo + 16)
           && *(_QWORD *)&a1->Data1 == *(_QWORD *)&GUID_NULL.Data1
           && *(_QWORD *)a1->Data4 == *(_QWORD *)GUID_NULL.Data4
           || Buf1[0] == *(_QWORD *)&a1->Data1 && Buf1[1] == *(_QWORD *)a1->Data4) )
        {
          if ( v35.Value == a2.Value )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              LOWORD(v42) = 0;
              LOWORD(v36) = 0;
              FormatRRASErrorString(
                &v42,
                L"IsTenantInterfacePresentInRegistry: Matching Interface (%ws) found in the registry",
                Name);
              if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasDimParamTraceError,
                  (unsigned int)&v42,
                  (_DWORD)a1,
                  0,
                  (__int64)&v36);
            }
          }
          else
          {
            if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
            {
              LOWORD(v42) = 0;
              LOWORD(v36) = 0;
              FormatRRASErrorString(
                &v42,
                L"IsTenantInterfacePresentInRegistry: Matching Interface (%ws) found in the registry with same VSID but differnet LUID",
                Name);
              if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
                McTemplateU0zjzz_EventWriteTransfer(
                  (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                  (unsigned int)RasDimParamTraceError,
                  (unsigned int)&v42,
                  (_DWORD)a1,
                  0,
                  (__int64)&v36);
            }
            v35.Value = a2.Value;
            WriteInterfaceExtraInfo(hKey, 3, 1, &v31);
          }
          if ( a4 )
          {
            memset_0(Data, 0, 0x202u);
            LODWORD(pcbRemaining) = 512;
            Type = 0;
            if ( !RegQueryValueExW(hKey, L"InterfaceName", 0, &Type, (LPBYTE)Data, (LPDWORD)&pcbRemaining) && Type == 1 )
            {
              v45 = 0;
              if ( _wcsicmp(Data, a4) )
              {
                v15 = -1;
                do
                  ++v15;
                while ( a4[v15] );
                v16 = RegSetValueExW(hKey, L"InterfaceName", 0, 1u, (const BYTE *)a4, 2 * v15 + 2);
                if ( v16 )
                {
                  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
                  {
                    LOWORD(v42) = 0;
                    LOWORD(v36) = 0;
                    dwFlags[0] = v16;
                    FormatRRASErrorString(
                      &v42,
                      L"IsTenantInterfacePresentInRegistry: Failed to update InterfaceName from '%ws' to '%ws' (error=%d)",
                      Data,
                      a4,
                      *(_QWORD *)dwFlags);
                    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
                    {
                      v17 = RasDimParamTraceError;
LABEL_49:
                      McTemplateU0zjzz_EventWriteTransfer(
                        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                        (_DWORD)v17,
                        (unsigned int)&v42,
                        (_DWORD)a1,
                        0,
                        (__int64)&v36);
                    }
                  }
                }
                else if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
                {
                  LOWORD(v42) = 0;
                  LOWORD(v36) = 0;
                  FormatRRASErrorString(
                    &v42,
                    L"IsTenantInterfacePresentInRegistry: Updated InterfaceName from '%ws' to '%ws'",
                    Data,
                    a4);
                  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
                  {
                    v17 = RasDimParamTraceInfo;
                    goto LABEL_49;
                  }
                }
              }
            }
            v10 = 0;
          }
          v5 = 1;
          goto LABEL_52;
        }
        RegCloseKey(hKey);
        hKey = 0;
        FreeInterfaceExtraInfo(&v31);
        if ( ++v13 >= cSubKeys )
          goto LABEL_52;
      }
      if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_58;
      v12 = Name;
      v11 = L"IsTenantInterfacePresentInRegistry:Error %d occured while opening registry key %ws.";
      goto LABEL_7;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_58;
    v11 = L"IsTenantInterfacePresentInRegistry:Error %d occured while enumerating subkeys under registry key %s. #1";
  }
LABEL_6:
  v12 = (WCHAR *)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
LABEL_7:
  LOWORD(v36) = 0;
  LOWORD(v42) = 0;
  FormatRRASErrorString(&v42, v11, v9, v12);
LABEL_8:
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasDimParamTraceError,
      (unsigned int)&v42,
      (_DWORD)a1,
      0,
      (__int64)&v36);
LABEL_58:
  FreeInterfaceExtraInfo(&v31);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x180015ad4  mov     [rsp-8+arg_10], rbx
0x180015ad9  push    rbp
0x180015ada  push    rsi
0x180015adb  push    rdi
0x180015adc  push    r12
0x180015ade  push    r13
0x180015ae0  push    r14
0x180015ae2  push    r15
0x180015ae4  lea     rbp, [rsp-0F90h]
0x180015aec  mov     eax, 1090h
0x180015af1  call    _alloca_probe
0x180015af6  sub     rsp, rax
0x180015af9  mov     rax, cs:__security_cookie
0x180015b00  xor     rax, rsp
0x180015b03  mov     [rbp+0FC0h+var_40], rax
0x180015b0a  mov     r13, [rbp+0FC0h+arg_20]
0x180015b11  xor     r12d, r12d
0x180015b14  mov     [rsp+10C0h+Type], r8d
0x180015b19  mov     rbx, rdx
0x180015b1c  mov     r14, rcx
0x180015b1f  mov     [rbp+0FC0h+phkResult], r12
0x180015b23  xor     edx, edx; Val
0x180015b25  mov     [rsp+10C0h+cbMaxValueNameLen], r12d
0x180015b2a  lea     r8d, [r12+50h]; Size
0x180015b2f  mov     [rbp+0FC0h+cValues], r12d
0x180015b33  lea     rcx, [rbp+0FC0h+var_CA0]; void *
0x180015b3a  mov     [rbp+0FC0h+cbMaxValueLen], r12d
0x180015b3e  mov     r15, r9
0x180015b41  mov     [rsp+10C0h+cSubKeys], r12d
0x180015b46  mov     [rsp+10C0h+cchName], r12d
0x180015b4b  mov     [rsp+10C0h+hKey], r12
0x180015b50  call    memset_0
0x180015b55  xor     edx, edx; Val
0x180015b57  lea     rcx, [rbp+0FC0h+pszDest]; void *
0x180015b5e  mov     r8d, 200h; Size
0x180015b64  call    memset_0
0x180015b69  xor     edx, edx; Val
0x180015b6b  mov     [rbp+0FC0h+var_1010], r12d
0x180015b6f  mov     r8d, 2C4h; Size
0x180015b75  lea     rcx, [rbp+0FC0h+var_100C]; void *
0x180015b79  call    memset_0
0x180015b7e  xor     edx, edx; Val
0x180015b80  mov     [rbp+0FC0h+var_C50], r12d
0x180015b87  mov     r8d, 7FCh; Size
0x180015b8d  lea     rcx, [rbp+0FC0h+var_C4C]; void *
0x180015b94  call    memset_0
0x180015b99  xorps   xmm0, xmm0
0x180015b9c  mov     [rbp+0FC0h+var_D40], r12d
0x180015ba3  xor     eax, eax
0x180015ba5  lea     r8, [rbp+0FC0h+var_CA0]
0x180015bac  mov     rcx, r14
0x180015baf  mov     [rbp+0FC0h+var_D1C], eax
0x180015bb5  movups  [rbp+0FC0h+var_D3C], xmm0
0x180015bbc  lea     edx, [rax+28h]
0x180015bbf  movups  [rbp+0FC0h+var_D2C], xmm0
0x180015bc6  movups  [rbp+0FC0h+var_1020], xmm0
0x180015bca  call    MprConvertGuidToString
0x180015bcf  lea     rax, [rbp+0FC0h+var_CA0]
0x180015bd6  mov     edx, 100h; cbDest
0x180015bdb  mov     [rsp+10C0h+lpcbMaxClassLen], rax
0x180015be0  lea     r9, [rbp+0FC0h+pcbRemaining]; pcbRemaining
0x180015be4  lea     rax, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Re"...
0x180015beb  mov     [rsp+10C0h+pszFormat], rax; pszFormat
0x180015bf0  lea     r8, [rbp+0FC0h+ppszDestEnd]; ppszDestEnd
0x180015bf4  lea     rcx, [rbp+0FC0h+pszDest]; pszDest
0x180015bfb  mov     qword ptr [rsp+10C0h+dwFlags], r12; dwFlags
0x180015c00  call    StringCbPrintfExW
0x180015c05  test    r14, r14
0x180015c08  jz      loc_180016156
0x180015c0e  test    r13, r13
0x180015c11  jz      loc_180016156
0x180015c17  lea     rax, [rbp+0FC0h+phkResult]
0x180015c1b  mov     r9d, 20019h; samDesired
0x180015c21  xor     r8d, r8d; ulOptions
0x180015c24  mov     qword ptr [rsp+10C0h+dwFlags], rax; phkResult
0x180015c29  lea     rdx, [rbp+0FC0h+pszDest]; lpSubKey
0x180015c30  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015c37  call    cs:__imp_RegOpenKeyExW
0x180015c3d  mov     esi, eax
0x180015c3f  test    eax, eax
0x180015c41  jz      short loc_180015CC0
0x180015c43  mov     dil, 4
0x180015c46  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180015c4d  jz      loc_18001615B
0x180015c53  lea     rdx, aIstenantinterf; "IsTenantInterfacePresentInRegistry: Err"...
0x180015c5a  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x180015c61  mov     r8d, eax
0x180015c64  mov     word ptr [rbp+0FC0h+var_D40], r12w
0x180015c6c  lea     rcx, [rbp+0FC0h+var_C50]
0x180015c73  mov     word ptr [rbp+0FC0h+var_C50], r12w
0x180015c7b  call    FormatRRASErrorString
0x180015c80  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180015c87  jz      loc_18001615B
0x180015c8d  lea     rax, [rbp+0FC0h+var_D40]
0x180015c94  mov     r9, r14
0x180015c97  mov     [rsp+10C0h+pszFormat], rax
0x180015c9c  lea     r8, [rbp+0FC0h+var_C50]
0x180015ca3  lea     rdx, RasDimParamTraceError
0x180015caa  mov     qword ptr [rsp+10C0h+dwFlags], r12
0x180015caf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015cb6  call    McTemplateU0zjzz_EventWriteTransfer
0x180015cbb  jmp     loc_18001615B
0x180015cc0  mov     rcx, [rbp+0FC0h+phkResult]; hKey
0x180015cc4  lea     rax, [rbp+0FC0h+cbMaxValueLen]
0x180015cc8  mov     [rsp+10C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180015ccd  xor     r9d, r9d; lpReserved
0x180015cd0  mov     [rsp+10C0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180015cd5  xor     r8d, r8d; lpcchClass
0x180015cd8  mov     [rsp+10C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180015cdd  xor     edx, edx; lpClass
0x180015cdf  lea     rax, [rsp+10C0h+cbMaxValueNameLen]
0x180015ce4  mov     [rsp+10C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180015ce9  lea     rax, [rbp+0FC0h+cValues]
0x180015ced  mov     [rsp+10C0h+lpcValues], rax; lpcValues
0x180015cf2  lea     rax, [rsp+10C0h+cSubKeys]
0x180015cf7  mov     [rsp+10C0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180015cfc  mov     [rsp+10C0h+pszFormat], r12; lpcbMaxSubKeyLen
0x180015d01  mov     qword ptr [rsp+10C0h+dwFlags], rax; lpcSubKeys
0x180015d06  call    cs:__imp_RegQueryInfoKeyW
0x180015d0c  inc     [rsp+10C0h+cbMaxValueNameLen]
0x180015d10  mov     esi, eax
0x180015d12  test    eax, eax
0x180015d14  jz      short loc_180015D32
0x180015d16  mov     dil, 4
0x180015d19  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180015d20  jz      loc_18001615B
0x180015d26  lea     rdx, aIstenantinterf_6; "IsTenantInterfacePresentInRegistry:Erro"...
0x180015d2d  jmp     loc_180015C5A
0x180015d32  xor     eax, eax
0x180015d34  mov     edi, eax
0x180015d36  cmp     [rsp+10C0h+cSubKeys], eax
0x180015d3a  jbe     loc_1800160FA
0x180015d40  mov     rcx, [rbp+0FC0h+phkResult]; hKey
0x180015d44  lea     r9, [rsp+10C0h+cchName]; lpcchName
0x180015d49  mov     [rsp+10C0h+lpcValues], rax; lpftLastWriteTime
0x180015d4e  lea     r8, [rbp+0FC0h+Name]; lpName
0x180015d55  mov     [rsp+10C0h+lpcbMaxClassLen], rax; lpcchClass
0x180015d5a  mov     edx, edi; dwIndex
0x180015d5c  mov     [rsp+10C0h+pszFormat], rax; lpClass
0x180015d61  mov     qword ptr [rsp+10C0h+dwFlags], rax; lpReserved
0x180015d66  mov     [rsp+10C0h+cchName], 32h ; '2'
0x180015d6e  call    cs:__imp_RegEnumKeyExW
0x180015d74  mov     esi, eax
0x180015d76  test    eax, eax
0x180015d78  jz      short loc_180015D85
0x180015d7a  cmp     eax, 0EAh
0x180015d7f  jnz     loc_180015E4B
0x180015d85  mov     rcx, [rbp+0FC0h+phkResult]; hKey
0x180015d89  lea     rax, [rsp+10C0h+hKey]
0x180015d8e  mov     r9d, 2001Fh; samDesired
0x180015d94  mov     qword ptr [rsp+10C0h+dwFlags], rax; phkResult
0x180015d99  xor     r8d, r8d; ulOptions
0x180015d9c  lea     rdx, [rbp+0FC0h+Name]; lpSubKey
0x180015da3  call    cs:__imp_RegOpenKeyExW
0x180015da9  mov     esi, eax
0x180015dab  test    eax, eax
0x180015dad  jnz     loc_180016137
0x180015db3  mov     rcx, [rsp+10C0h+hKey]; hKey
0x180015db8  lea     r9, [rbp+0FC0h+var_1010]
0x180015dbc  lea     edx, [rax+3]
0x180015dbf  lea     r8d, [rax+1]
0x180015dc3  call    ReadInterfaceExtraInfo
0x180015dc8  mov     esi, eax
0x180015dca  test    eax, eax
0x180015dcc  jnz     loc_180016100
0x180015dd2  mov     eax, [rsp+10C0h+Type]
0x180015dd6  cmp     [rbp+0FC0h+var_FE4], eax
0x180015dd9  jnz     short loc_180015E1F
0x180015ddb  lea     r8d, [rsi+10h]; Size
0x180015ddf  lea     rdx, GUID_NULL; Buf2
0x180015de6  lea     rcx, [rbp+0FC0h+Buf1]; Buf1
0x180015dea  call    memcmp_0
0x180015def  test    eax, eax
0x180015df1  jnz     short loc_180015E0C
0x180015df3  mov     rax, [r14]
0x180015df6  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x180015dfd  jnz     short loc_180015E0C
0x180015dff  mov     rax, [r14+8]
0x180015e03  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x180015e0a  jz      short loc_180015E67
0x180015e0c  mov     rax, [rbp+0FC0h+Buf1]
0x180015e10  cmp     rax, [r14]
0x180015e13  jnz     short loc_180015E1F
0x180015e15  mov     rax, [rbp+0FC0h+var_FEC]
0x180015e19  cmp     rax, [r14+8]
0x180015e1d  jz      short loc_180015E67
0x180015e1f  mov     rcx, [rsp+10C0h+hKey]; hKey
0x180015e24  call    cs:__imp_RegCloseKey
0x180015e2a  lea     rcx, [rbp+0FC0h+var_1010]
0x180015e2e  mov     [rsp+10C0h+hKey], r12
0x180015e33  call    FreeInterfaceExtraInfo
0x180015e38  inc     edi
0x180015e3a  cmp     edi, [rsp+10C0h+cSubKeys]
0x180015e3e  jnb     loc_1800160FA
0x180015e44  xor     eax, eax
0x180015e46  jmp     loc_180015D40
0x180015e4b  mov     dil, 4
0x180015e4e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180015e55  jz      loc_18001615B
0x180015e5b  lea     rdx, aIstenantinterf_3; "IsTenantInterfacePresentInRegistry:Erro"...
0x180015e62  jmp     loc_180015C5A
0x180015e67  mov     dil, 4
0x180015e6a  cmp     [rbp+0FC0h+var_FE0], rbx
0x180015e6e  jnz     short loc_180015EE7
0x180015e70  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180015e77  jz      loc_180015F6C
0x180015e7d  lea     r8, [rbp+0FC0h+Name]
0x180015e84  mov     word ptr [rbp+0FC0h+var_C50], r12w
0x180015e8c  lea     rdx, aIstenantinterf_5; "IsTenantInterfacePresentInRegistry: Mat"...
0x180015e93  mov     word ptr [rbp+0FC0h+var_D40], r12w
0x180015e9b  lea     rcx, [rbp+0FC0h+var_C50]
0x180015ea2  call    FormatRRASErrorString
0x180015ea7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180015eae  jz      loc_180015F6C
0x180015eb4  lea     rax, [rbp+0FC0h+var_D40]
0x180015ebb  mov     r9, r14
0x180015ebe  mov     [rsp+10C0h+pszFormat], rax
0x180015ec3  lea     r8, [rbp+0FC0h+var_C50]
0x180015eca  lea     rdx, RasDimParamTraceError
0x180015ed1  mov     qword ptr [rsp+10C0h+dwFlags], r12
0x180015ed6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015edd  call    McTemplateU0zjzz_EventWriteTransfer
0x180015ee2  jmp     loc_180015F6C
0x180015ee7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180015eee  jz      short loc_180015F51
0x180015ef0  lea     r8, [rbp+0FC0h+Name]
0x180015ef7  mov     word ptr [rbp+0FC0h+var_C50], r12w
0x180015eff  lea     rdx, aIstenantinterf_0; "IsTenantInterfacePresentInRegistry: Mat"...
0x180015f06  mov     word ptr [rbp+0FC0h+var_D40], r12w
0x180015f0e  lea     rcx, [rbp+0FC0h+var_C50]
0x180015f15  call    FormatRRASErrorString
0x180015f1a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180015f21  jz      short loc_180015F51
0x180015f23  lea     rax, [rbp+0FC0h+var_D40]
0x180015f2a  mov     r9, r14
0x180015f2d  mov     [rsp+10C0h+pszFormat], rax
0x180015f32  lea     r8, [rbp+0FC0h+var_C50]
0x180015f39  lea     rdx, RasDimParamTraceError
0x180015f40  mov     qword ptr [rsp+10C0h+dwFlags], r12
0x180015f45  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180015f4c  call    McTemplateU0zjzz_EventWriteTransfer
0x180015f51  mov     rcx, [rsp+10C0h+hKey]; hKey
0x180015f56  lea     r9, [rbp+0FC0h+var_1010]
0x180015f5a  mov     edx, 3
0x180015f5f  mov     [rbp+0FC0h+var_FE0], rbx
0x180015f63  lea     r8d, [rdx-2]
0x180015f67  call    WriteInterfaceExtraInfo
0x180015f6c  test    r15, r15
0x180015f6f  jz      loc_1800160F4
0x180015f75  xor     edx, edx; Val
0x180015f77  lea     rcx, [rbp+0FC0h+Data]; void *
0x180015f7e  mov     r8d, 202h; Size
0x180015f84  call    memset_0
0x180015f89  mov     rcx, [rsp+10C0h+hKey]; hKey
0x180015f8e  lea     rax, [rbp+0FC0h+pcbRemaining]
0x180015f92  mov     [rsp+10C0h+pszFormat], rax; lpcbData
0x180015f97  lea     r9, [rsp+10C0h+Type]; lpType
0x180015f9c  lea     rax, [rbp+0FC0h+Data]
0x180015fa3  mov     dword ptr [rbp+0FC0h+pcbRemaining], 200h
0x180015faa  xor     r8d, r8d; lpReserved
0x180015fad  mov     qword ptr [rsp+10C0h+dwFlags], rax; lpData
0x180015fb2  lea     rdx, ValueName; "InterfaceName"
0x180015fb9  mov     [rsp+10C0h+Type], r12d
0x180015fbe  call    cs:__imp_RegQueryValueExW
0x180015fc4  test    eax, eax
0x180015fc6  jnz     loc_1800160F1
0x180015fcc  cmp     [rsp+10C0h+Type], 1
0x180015fd1  jnz     loc_1800160F1
0x180015fd7  mov     rdx, r15; String2
0x180015fda  mov     [rbp+0FC0h+var_250], r12w
0x180015fe2  lea     rcx, [rbp+0FC0h+Data]; String1
0x180015fe9  call    cs:__imp__wcsicmp
0x180015fef  test    eax, eax
0x180015ff1  jz      loc_1800160F1
0x180015ff7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015ffb  inc     rax
0x180015ffe  cmp     [r15+rax*2], r12w
0x180016003  jnz     short loc_180015FFB
0x180016005  mov     rcx, [rsp+10C0h+hKey]; hKey
0x18001600a  lea     eax, ds:2[rax*2]
0x180016011  mov     dword ptr [rsp+10C0h+pszFormat], eax; cbData
0x180016015  lea     rdx, ValueName; "InterfaceName"
0x18001601c  mov     r9d, 1; dwType
0x180016022  mov     qword ptr [rsp+10C0h+dwFlags], r15; lpData
0x180016027  xor     r8d, r8d; Reserved
0x18001602a  call    cs:__imp_RegSetValueExW
0x180016030  test    eax, eax
0x180016032  jnz     short loc_180016080
0x180016034  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001603b  jz      loc_1800160F1
0x180016041  mov     r9, r15
0x180016044  mov     word ptr [rbp+0FC0h+var_C50], r12w
0x18001604c  lea     r8, [rbp+0FC0h+Data]
0x180016053  mov     word ptr [rbp+0FC0h+var_D40], r12w
0x18001605b  lea     rdx, aIstenantinterf_4; "IsTenantInterfacePresentInRegistry: Upd"...
0x180016062  lea     rcx, [rbp+0FC0h+var_C50]
0x180016069  call    FormatRRASErrorString
0x18001606e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180016075  jz      short loc_1800160F1
0x180016077  lea     rdx, RasDimParamTraceInfo
  ... truncated ...
```
