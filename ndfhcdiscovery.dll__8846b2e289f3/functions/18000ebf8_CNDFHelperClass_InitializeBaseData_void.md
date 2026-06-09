# CNDFHelperClass::InitializeBaseData(void)

- ea: `0x18000ebf8`
- end: `0x18000f5d1`
- name: `?InitializeBaseData@CNDFHelperClass@@AEAAJXZ`
- size: `2521`
- prototype: `__int64 __fastcall(CNDFHelperClass *__hidden this)`
- caller_count: `8`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d8c0`
- `0x18000d990`
- `0x18000dac0`
- `0x18000db50`
- `0x18000dcf0`
- `0x18000dd80`
- `0x18000e200`
- `0x18000fff8`

## callees

- `0x180003414`
- `0x18000b0cc`
- `0x18000ebf8`
- `0x180011920`
- `0x180011cb4`
- `0x180013686`
- `0x1800136b0`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x18000ec89`
- `KERNEL32!lstrcmpW` at `0x18000eca9`
- `KERNEL32!lstrcmpW` at `0x18000ec89`
- `KERNEL32!lstrcmpW` at `0x18000eca9`
- `ADVAPI32!RegCloseKey` at `0x18000ed09`
- `ADVAPI32!RegCloseKey` at `0x18000ed59`
- `ADVAPI32!RegCloseKey` at `0x18000ed93`
- `ADVAPI32!RegCloseKey` at `0x18000f0be`
- `ADVAPI32!RegCloseKey` at `0x18000f475`
- `ADVAPI32!RegCloseKey` at `0x18000ed09`
- `ADVAPI32!RegCloseKey` at `0x18000ed59`
- `ADVAPI32!RegCloseKey` at `0x18000ed93`
- `ADVAPI32!RegCloseKey` at `0x18000f0be`
- `ADVAPI32!RegCloseKey` at `0x18000f475`
- `ADVAPI32!RegQueryValueExW` at `0x18000f02d`
- `ADVAPI32!RegQueryValueExW` at `0x18000f1ae`
- `ADVAPI32!RegQueryValueExW` at `0x18000f2b2`
- `ADVAPI32!RegQueryValueExW` at `0x18000f3ad`
- `ADVAPI32!RegQueryValueExW` at `0x18000f02d`
- `ADVAPI32!RegQueryValueExW` at `0x18000f1ae`
- `ADVAPI32!RegQueryValueExW` at `0x18000f2b2`
- `ADVAPI32!RegQueryValueExW` at `0x18000f3ad`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ec5d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ed3d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ec5d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ed3d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ef7c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ef7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f420`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f448`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f45c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ef9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f420`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f434`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f448`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f45c`

## string_xrefs

- `0x18000ef3e`: `CLSID`
- `0x18000efa8`: `CLSID`
- `0x18000edac`: `Component`
- `0x18000f29b`: `Impersonation`
- `0x18000f2f3`: `Impersonation`
- `0x18000f347`: `Impersonation`

## pseudocode

```c
LSTATUS __fastcall CNDFHelperClass::InitializeBaseData(CNDFHelperClass *this)
{
  const WCHAR *v1; // rdx
  HKEY v3; // rcx
  LSTATUS result; // eax
  const WCHAR *v5; // rbx
  HKEY v6; // rsi
  BOOL v7; // r14d
  signed int v8; // ebx
  HKEY v9; // rdi
  LSTATUS v10; // eax
  unsigned int Data1; // ecx
  int v12; // ecx
  int StringWithAlloc; // r12d
  void *v14; // r15
  int v15; // ecx
  void *v16; // r14
  int v17; // ecx
  void *v18; // rsi
  int v19; // ecx
  void *v20; // rdi
  CLSID v21; // xmm6
  int v22; // ecx
  void *v23; // rbx
  const OLECHAR *v24; // rcx
  int v25; // ebx
  LSTATUS Value; // eax
  int v27; // ecx
  const WCHAR *v28; // rdx
  int v29; // r9d
  LSTATUS v30; // eax
  LSTATUS v31; // eax
  LSTATUS v32; // eax
  __int64 v33; // rax
  int v34; // ecx
  BYTE Data[8]; // [rsp+38h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  int v37; // [rsp+48h] [rbp-C0h]
  BOOL v38; // [rsp+4Ch] [rbp-BCh]
  _QWORD v39[3]; // [rsp+50h] [rbp-B8h] BYREF
  CLSID phkResult; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+78h] [rbp-90h] BYREF

  v1 = (const WCHAR *)*((_QWORD *)this + 3);
  v39[1] = 0;
  v3 = (HKEY)*((_QWORD *)this + 4);
  v39[2] = 0;
  hKey = 0;
  result = RegOpenKeyExW(v3, v1, 0, 0x20019u, &hKey);
  if ( result )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    v5 = (const WCHAR *)*((_QWORD *)this + 2);
    v6 = hKey;
    v39[0] = hKey;
    if ( lstrcmpW(v5, L"Microsoft") )
      v7 = lstrcmpW(v5, L"Microsoft.Edison") == 0;
    else
      v7 = 1;
    v38 = v7;
    memset_0(SubKey, 0, 0x208u);
    v8 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", *((_QWORD *)this + 3), L"MatchAttributes");
    if ( v8 < 0 )
    {
LABEL_6:
      if ( v6 )
        RegCloseKey(v6);
      return v8;
    }
    v9 = (HKEY)*((_QWORD *)this + 4);
    *(_QWORD *)&phkResult.Data1 = 0;
    v10 = RegOpenKeyExW(v9, SubKey, 0, 0x20019u, (PHKEY)&phkResult);
    v8 = v10;
    if ( v10 )
    {
      if ( v10 == 2 )
      {
        v8 = 1;
      }
      else if ( v10 > 0 )
      {
        v8 = (unsigned __int16)v10 | 0x80070000;
      }
    }
    else
    {
      Data1 = phkResult.Data1;
      if ( *(_QWORD *)&phkResult.Data1 )
        RegCloseKey(*(HKEY *)&phkResult.Data1);
      v8 = 0;
    }
    if ( v9 )
      RegCloseKey(v9);
    if ( !v8 )
    {
      v37 = 1;
      goto LABEL_21;
    }
    if ( v8 != 1 || v7 )
    {
      v37 = 0;
      if ( v8 < 0 )
      {
        if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
          McTemplateU0qqzz_EventWriteTransfer(
            Data1,
            (unsigned int)RegistryError,
            v8,
            250,
            *((_QWORD *)this + 1),
            (__int64)L"MatchAttributes");
        goto LABEL_6;
      }
LABEL_21:
      *(_QWORD *)&phkResult.Data1 = 0;
      StringWithAlloc = RegUtilLoadStringWithAlloc(
                          (unsigned __int16 **)&phkResult,
                          (struct ATL::CRegKey *)v39,
                          L"Component");
      if ( StringWithAlloc == -2147024894 )
      {
        if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
          McTemplateU0qqzz_EventWriteTransfer(
            v12,
            (unsigned int)RegistryWarning,
            -2147024894,
            261,
            *((_QWORD *)this + 1),
            (__int64)L"Component");
        StringWithAlloc = 0;
      }
      v14 = *(void **)&phkResult.Data1;
      *(_QWORD *)&phkResult.Data1 = 0;
      if ( StringWithAlloc >= 0 )
      {
        StringWithAlloc = RegUtilLoadStringWithAlloc(
                            (unsigned __int16 **)&phkResult,
                            (struct ATL::CRegKey *)v39,
                            L"Description");
        if ( StringWithAlloc == -2147024894 )
        {
          if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
            McTemplateU0qqzz_EventWriteTransfer(
              v15,
              (unsigned int)RegistryWarning,
              -2147024894,
              274,
              *((_QWORD *)this + 1),
              (__int64)L"Description");
          StringWithAlloc = 0;
        }
      }
      v16 = *(void **)&phkResult.Data1;
      *(_QWORD *)&phkResult.Data1 = 0;
      if ( StringWithAlloc >= 0 )
      {
        StringWithAlloc = RegUtilLoadStringWithAlloc(
                            (unsigned __int16 **)&phkResult,
                            (struct ATL::CRegKey *)v39,
                            L"ProgressDescription");
        if ( StringWithAlloc == -2147024894 )
        {
          if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
            McTemplateU0qqzz_EventWriteTransfer(
              v17,
              (unsigned int)RegistryWarning,
              -2147024894,
              287,
              *((_QWORD *)this + 1),
              (__int64)L"ProgressDescription");
          StringWithAlloc = 0;
        }
      }
      v18 = *(void **)&phkResult.Data1;
      *(_QWORD *)&phkResult.Data1 = 0;
      if ( StringWithAlloc >= 0 )
      {
        StringWithAlloc = RegUtilLoadStringWithAlloc(
                            (unsigned __int16 **)&phkResult,
                            (struct ATL::CRegKey *)v39,
                            L"Version");
        if ( StringWithAlloc < 0 && (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
          McTemplateU0qqzz_EventWriteTransfer(
            v19,
            (unsigned int)RegistryError,
            StringWithAlloc,
            302,
            *((_QWORD *)this + 1),
            (__int64)L"Version");
      }
      v20 = *(void **)&phkResult.Data1;
      v21 = 0;
      if ( StringWithAlloc >= 0 )
      {
        *(_QWORD *)&phkResult.Data1 = 0;
        StringWithAlloc = RegUtilLoadStringWithAlloc(
                            (unsigned __int16 **)&phkResult,
                            (struct ATL::CRegKey *)v39,
                            L"CLSID");
        if ( StringWithAlloc >= 0 )
        {
          v23 = *(void **)&phkResult.Data1;
          v24 = *(const OLECHAR **)&phkResult.Data1;
          phkResult = 0;
          StringWithAlloc = CLSIDFromString(v24, &phkResult);
          if ( StringWithAlloc >= 0 )
            v21 = phkResult;
          if ( v23 )
            CoTaskMemFree(v23);
        }
        if ( StringWithAlloc == -2147024894 )
        {
          if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
            McTemplateU0qqzz_EventWriteTransfer(
              v22,
              (unsigned int)RegistryWarning,
              -2147024894,
              314,
              *((_QWORD *)this + 1),
              (__int64)L"CLSID");
          StringWithAlloc = 0;
        }
      }
      v25 = 0;
      *(_DWORD *)Data = 0;
      if ( StringWithAlloc < 0 )
        goto LABEL_109;
      *(_DWORD *)&Data[4] = 0;
      phkResult.Data1 = 4;
      Value = RegQueryValueExW(hKey, L"Published", 0, (LPDWORD)&Data[4], Data, &phkResult.Data1);
      if ( Value )
      {
        if ( Value != 2 )
        {
          if ( Value <= 0 )
          {
            StringWithAlloc = Value;
LABEL_54:
            if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
            {
              v28 = L"Published";
              v29 = 345;
LABEL_108:
              McTemplateU0qqzz_EventWriteTransfer(
                v27,
                (unsigned int)RegistryError,
                StringWithAlloc,
                v29,
                *((_QWORD *)this + 1),
                (__int64)v28);
              goto LABEL_109;
            }
            goto LABEL_129;
          }
LABEL_53:
          StringWithAlloc = (unsigned __int16)Value | 0x80070000;
          goto LABEL_54;
        }
      }
      else
      {
        if ( *(_DWORD *)&Data[4] != 4 )
        {
          LOWORD(Value) = 13;
          goto LABEL_53;
        }
        Value = 0;
      }
      if ( *(_DWORD *)Data )
        v25 = 1;
      if ( Value && (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
        McTemplateU0qqzz_EventWriteTransfer(
          *((_QWORD *)this + 1),
          (unsigned int)RegistryWarning,
          (unsigned __int16)Value | 0x80070000,
          336,
          *((_QWORD *)this + 1),
          (__int64)L"Published");
      memset(Data, 0, sizeof(Data));
      phkResult.Data1 = 4;
      v30 = RegQueryValueExW(hKey, L"Extensible", 0, (LPDWORD)&Data[4], Data, &phkResult.Data1);
      if ( v30 )
      {
        if ( v30 != 2 )
        {
          if ( v30 <= 0 )
          {
            StringWithAlloc = v30;
LABEL_76:
            if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
            {
              v28 = L"Extensible";
              v29 = 372;
              goto LABEL_108;
            }
            goto LABEL_129;
          }
LABEL_75:
          StringWithAlloc = (unsigned __int16)v30 | 0x80070000;
          goto LABEL_76;
        }
      }
      else
      {
        if ( *(_DWORD *)&Data[4] != 4 )
        {
          LOWORD(v30) = 13;
          goto LABEL_75;
        }
        v30 = 0;
      }
      if ( *(_DWORD *)Data )
        v25 |= 2u;
      if ( v30 && (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
        McTemplateU0qqzz_EventWriteTransfer(
          *((_QWORD *)this + 1),
          (unsigned int)RegistryWarning,
          (unsigned __int16)v30 | 0x80070000,
          364,
          *((_QWORD *)this + 1),
          (__int64)L"Extensible");
      memset(Data, 0, sizeof(Data));
      phkResult.Data1 = 4;
      v31 = RegQueryValueExW(hKey, L"Impersonation", 0, (LPDWORD)&Data[4], Data, &phkResult.Data1);
      if ( v31 )
      {
        if ( v31 != 2 )
        {
          if ( v31 <= 0 )
          {
            StringWithAlloc = v31;
LABEL_91:
            if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
            {
              v28 = L"Impersonation";
              v29 = 399;
              goto LABEL_108;
            }
            goto LABEL_129;
          }
LABEL_90:
          StringWithAlloc = (unsigned __int16)v31 | 0x80070000;
          goto LABEL_91;
        }
      }
      else
      {
        if ( *(_DWORD *)&Data[4] != 4 )
        {
          LOWORD(v31) = 13;
          goto LABEL_90;
        }
        v31 = 0;
      }
      if ( *(_DWORD *)Data )
        v25 |= 4u;
      if ( v31 && (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
        McTemplateU0qqzz_EventWriteTransfer(
          *((_QWORD *)this + 1),
          (unsigned int)RegistryWarning,
          (unsigned __int16)v31 | 0x80070000,
          391,
          *((_QWORD *)this + 1),
          (__int64)L"Impersonation");
      memset(Data, 0, sizeof(Data));
      phkResult.Data1 = 4;
      v32 = RegQueryValueExW(hKey, L"TraceOnlySupport", 0, (LPDWORD)&Data[4], Data, &phkResult.Data1);
      if ( v32 )
      {
        if ( v32 != 2 )
        {
          if ( v32 <= 0 )
          {
            StringWithAlloc = v32;
LABEL_106:
            if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
            {
              v28 = L"TraceOnlySupport";
              v29 = 426;
              goto LABEL_108;
            }
LABEL_109:
            if ( v20 )
              CoTaskMemFree(v20);
            if ( v18 )
              CoTaskMemFree(v18);
            if ( v16 )
              CoTaskMemFree(v16);
            if ( v14 )
              CoTaskMemFree(v14);
            goto LABEL_117;
          }
LABEL_105:
          StringWithAlloc = (unsigned __int16)v32 | 0x80070000;
          goto LABEL_106;
        }
      }
      else
      {
        if ( *(_DWORD *)&Data[4] != 4 )
        {
          LOWORD(v32) = 13;
          goto LABEL_105;
        }
        v32 = 0;
      }
      if ( *(_DWORD *)Data )
        v25 |= 8u;
      if ( v32 && (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 2) != 0 )
        McTemplateU0qqzz_EventWriteTransfer(
          *((_QWORD *)this + 1),
          (unsigned int)RegistryWarning,
          (unsigned __int16)v32 | 0x80070000,
          418,
          *((_QWORD *)this + 1),
          (__int64)L"TraceOnlySupport");
LABEL_129:
      if ( StringWithAlloc >= 0 )
      {
        v33 = 0;
        if ( v37 )
        {
          if ( v38 )
            v25 |= 0x10u;
          else
            v25 |= 0x20u;
          *(_QWORD *)&phkResult.Data1 = 0;
          StringWithAlloc = RegUtilLoadStringWithAlloc(
                              (unsigned __int16 **)&phkResult,
                              (struct ATL::CRegKey *)v39,
                              L"Parent");
          if ( StringWithAlloc < 0 )
          {
            if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
              McTemplateU0qqzz_EventWriteTransfer(
                v34,
                (unsigned int)RegistryError,
                StringWithAlloc,
                460,
                *((_QWORD *)this + 1),
                (__int64)L"Parent");
            goto LABEL_109;
          }
          v33 = *(_QWORD *)&phkResult.Data1;
        }
        *((_QWORD *)this + 5) = v14;
        *((_QWORD *)this + 6) = v16;
        *((_QWORD *)this + 9) = v18;
        *((_QWORD *)this + 8) = v20;
        *((_QWORD *)this + 7) = v33;
        *((CLSID *)this + 5) = v21;
        *((_DWORD *)this + 24) = v25;
        *((_DWORD *)this + 25) = 1;
LABEL_117:
        if ( hKey )
          RegCloseKey(hKey);
        return StringWithAlloc;
      }
      goto LABEL_109;
    }
    if ( (Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits & 1) != 0 )
      McTemplateU0qqz_EventWriteTransfer(
        Data1,
        (unsigned int)ThirdPartyNonExtensionHC,
        -2147024891,
        244,
        *((_QWORD *)this + 1));
    if ( v6 )
      RegCloseKey(v6);
    return -2147024891;
  }
  return result;
}

```

## disassembly

```asm
0x18000ebf8  mov     rax, rsp
0x18000ebfb  push    rbp
0x18000ebfc  push    rbx
0x18000ebfd  push    rsi
0x18000ebfe  push    rdi
0x18000ebff  push    r12
0x18000ec01  push    r13
0x18000ec03  push    r14
0x18000ec05  push    r15
0x18000ec07  lea     rbp, [rax-1E8h]
0x18000ec0e  sub     rsp, 2A8h
0x18000ec15  movaps  xmmword ptr [rax-58h], xmm6
0x18000ec19  mov     rax, cs:__security_cookie
0x18000ec20  xor     rax, rsp
0x18000ec23  mov     [rbp+1E0h+var_60], rax
0x18000ec2a  mov     rdx, [rcx+18h]; lpSubKey
0x18000ec2e  lea     rax, [rsp+2E0h+hKey]
0x18000ec33  xor     r15d, r15d
0x18000ec36  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000ec3b  mov     r13, rcx
0x18000ec3e  mov     [rsp+2E0h+var_290], r15
0x18000ec43  mov     rcx, [rcx+20h]; hKey
0x18000ec47  mov     r12d, 20019h
0x18000ec4d  mov     r9d, r12d; samDesired
0x18000ec50  mov     [rsp+2E0h+var_288], r15
0x18000ec55  xor     r8d, r8d; ulOptions
0x18000ec58  mov     [rsp+2E0h+hKey], r15
0x18000ec5d  call    cs:__imp_RegOpenKeyExW
0x18000ec64  nop     dword ptr [rax+rax+00h]
0x18000ec69  test    eax, eax
0x18000ec6b  jnz     loc_18000F59B
0x18000ec71  mov     rbx, [r13+10h]
0x18000ec75  lea     rdx, aMicrosoft; "Microsoft"
0x18000ec7c  mov     rsi, [rsp+2E0h+hKey]
0x18000ec81  mov     rcx, rbx; lpString1
0x18000ec84  mov     [rsp+2E0h+var_298], rsi
0x18000ec89  call    cs:__imp_lstrcmpW
0x18000ec90  nop     dword ptr [rax+rax+00h]
0x18000ec95  test    eax, eax
0x18000ec97  jnz     short loc_18000EC9F
0x18000ec99  lea     r14d, [r15+1]
0x18000ec9d  jmp     short loc_18000ECBE
0x18000ec9f  lea     rdx, aMicrosoftEdiso; "Microsoft.Edison"
0x18000eca6  mov     rcx, rbx; lpString1
0x18000eca9  call    cs:__imp_lstrcmpW
0x18000ecb0  nop     dword ptr [rax+rax+00h]
0x18000ecb5  test    eax, eax
0x18000ecb7  mov     r14d, r15d
0x18000ecba  setz    r14b
0x18000ecbe  xor     edx, edx; Val
0x18000ecc0  mov     dword ptr [rsp+2E0h+var_2A0+4], r14d
0x18000ecc5  mov     r8d, 208h; Size
0x18000eccb  lea     rcx, [rsp+2E0h+SubKey]; void *
0x18000ecd0  call    memset_0
0x18000ecd5  mov     r9, [r13+18h]
0x18000ecd9  lea     rax, aMatchattribute; "MatchAttributes"
0x18000ece0  lea     r8, aSS; "%s\\%s"
0x18000ece7  mov     [rsp+2E0h+phkResult], rax
0x18000ecec  mov     edx, 104h; unsigned __int64
0x18000ecf1  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18000ecf6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ecfb  mov     ebx, eax
0x18000ecfd  test    eax, eax
0x18000ecff  jns     short loc_18000ED1C
0x18000ed01  test    rsi, rsi
0x18000ed04  jz      short loc_18000ED15
0x18000ed06  mov     rcx, rsi; hKey
0x18000ed09  call    cs:__imp_RegCloseKey
0x18000ed10  nop     dword ptr [rax+rax+00h]
0x18000ed15  mov     eax, ebx
0x18000ed17  jmp     loc_18000F5A5
0x18000ed1c  mov     rdi, [r13+20h]
0x18000ed20  lea     rax, [rsp+2E0h+var_288+8]
0x18000ed25  mov     rcx, rdi; hKey
0x18000ed28  mov     [rsp+2E0h+var_288+8], r15
0x18000ed2d  mov     r9d, r12d; samDesired
0x18000ed30  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000ed35  xor     r8d, r8d; ulOptions
0x18000ed38  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x18000ed3d  call    cs:__imp_RegOpenKeyExW
0x18000ed44  nop     dword ptr [rax+rax+00h]
0x18000ed49  mov     ebx, eax
0x18000ed4b  test    eax, eax
0x18000ed4d  jnz     short loc_18000ED6A
0x18000ed4f  mov     rcx, [rsp+2E0h+var_288+8]; hKey
0x18000ed54  test    rcx, rcx
0x18000ed57  jz      short loc_18000ED65
0x18000ed59  call    cs:__imp_RegCloseKey
0x18000ed60  nop     dword ptr [rax+rax+00h]
0x18000ed65  mov     ebx, r15d
0x18000ed68  jmp     short loc_18000ED85
0x18000ed6a  cmp     eax, 2
0x18000ed6d  jnz     short loc_18000ED78
0x18000ed6f  lea     r12d, [rax-1]
0x18000ed73  mov     ebx, r12d
0x18000ed76  jmp     short loc_18000ED8B
0x18000ed78  test    eax, eax
0x18000ed7a  jle     short loc_18000ED85
0x18000ed7c  movzx   ebx, ax
0x18000ed7f  or      ebx, 80070000h
0x18000ed85  mov     r12d, 1
0x18000ed8b  test    rdi, rdi
0x18000ed8e  jz      short loc_18000ED9F
0x18000ed90  mov     rcx, rdi; hKey
0x18000ed93  call    cs:__imp_RegCloseKey
0x18000ed9a  nop     dword ptr [rax+rax+00h]
0x18000ed9f  test    ebx, ebx
0x18000eda1  jnz     loc_18000F082
0x18000eda7  mov     dword ptr [rsp+2E0h+var_2A0], r12d
0x18000edac  lea     rbx, aComponent; "Component"
0x18000edb3  mov     [rsp+2E0h+var_288+8], r15
0x18000edb8  mov     r8, rbx; unsigned __int16 *
0x18000edbb  lea     rdx, [rsp+2E0h+var_298]; struct ATL::CRegKey *
0x18000edc0  lea     rcx, [rsp+2E0h+var_288+8]; unsigned __int16 **
0x18000edc5  call    ?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z; RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)
0x18000edca  mov     edi, 80070002h
0x18000edcf  mov     r12d, eax
0x18000edd2  mov     esi, 80070002h
0x18000edd7  cmp     eax, edi
0x18000edd9  jnz     short loc_18000EE0A
0x18000eddb  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 2
0x18000ede2  jz      short loc_18000EE07
0x18000ede4  mov     rax, [r13+8]
0x18000ede8  lea     rdx, RegistryWarning
0x18000edef  mov     [rsp+2E0h+lpcbData], rbx
0x18000edf4  mov     r9d, 105h
0x18000edfa  mov     r8d, esi
0x18000edfd  mov     [rsp+2E0h+phkResult], rax
0x18000ee02  call    McTemplateU0qqzz_EventWriteTransfer
0x18000ee07  mov     r12d, r15d
0x18000ee0a  mov     r15, [rsp+2E0h+var_288+8]
0x18000ee0f  mov     [rsp+2E0h+var_288+8], 0
0x18000ee18  test    r12d, r12d
0x18000ee1b  js      short loc_18000EE6C
0x18000ee1d  lea     rbx, aDescription; "Description"
0x18000ee24  mov     r8, rbx; unsigned __int16 *
0x18000ee27  lea     rdx, [rsp+2E0h+var_298]; struct ATL::CRegKey *
0x18000ee2c  lea     rcx, [rsp+2E0h+var_288+8]; unsigned __int16 **
0x18000ee31  call    ?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z; RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)
0x18000ee36  mov     r12d, eax
0x18000ee39  cmp     eax, edi
0x18000ee3b  jnz     short loc_18000EE6C
0x18000ee3d  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 2
0x18000ee44  jz      short loc_18000EE69
0x18000ee46  mov     rax, [r13+8]
0x18000ee4a  lea     rdx, RegistryWarning
0x18000ee51  mov     [rsp+2E0h+lpcbData], rbx
0x18000ee56  mov     r9d, 112h
0x18000ee5c  mov     r8d, esi
0x18000ee5f  mov     [rsp+2E0h+phkResult], rax
0x18000ee64  call    McTemplateU0qqzz_EventWriteTransfer
0x18000ee69  xor     r12d, r12d
0x18000ee6c  mov     r14, [rsp+2E0h+var_288+8]
0x18000ee71  mov     [rsp+2E0h+var_288+8], 0
0x18000ee7a  test    r12d, r12d
0x18000ee7d  js      short loc_18000EECE
0x18000ee7f  lea     rbx, aProgressdescri; "ProgressDescription"
0x18000ee86  mov     r8, rbx; unsigned __int16 *
0x18000ee89  lea     rdx, [rsp+2E0h+var_298]; struct ATL::CRegKey *
0x18000ee8e  lea     rcx, [rsp+2E0h+var_288+8]; unsigned __int16 **
0x18000ee93  call    ?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z; RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)
0x18000ee98  mov     r12d, eax
0x18000ee9b  cmp     eax, edi
0x18000ee9d  jnz     short loc_18000EECE
0x18000ee9f  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 2
0x18000eea6  jz      short loc_18000EECB
0x18000eea8  mov     rax, [r13+8]
0x18000eeac  lea     rdx, RegistryWarning
0x18000eeb3  mov     [rsp+2E0h+lpcbData], rbx
0x18000eeb8  mov     r9d, 11Fh
0x18000eebe  mov     r8d, esi
0x18000eec1  mov     [rsp+2E0h+phkResult], rax
0x18000eec6  call    McTemplateU0qqzz_EventWriteTransfer
0x18000eecb  xor     r12d, r12d
0x18000eece  mov     rsi, [rsp+2E0h+var_288+8]
0x18000eed3  mov     [rsp+2E0h+var_288+8], 0
0x18000eedc  test    r12d, r12d
0x18000eedf  js      short loc_18000EF2D
0x18000eee1  lea     rbx, aVersion; "Version"
0x18000eee8  mov     r8, rbx; unsigned __int16 *
0x18000eeeb  lea     rdx, [rsp+2E0h+var_298]; struct ATL::CRegKey *
0x18000eef0  lea     rcx, [rsp+2E0h+var_288+8]; unsigned __int16 **
0x18000eef5  call    ?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z; RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)
0x18000eefa  mov     r12d, eax
0x18000eefd  test    eax, eax
0x18000eeff  jns     short loc_18000EF2D
0x18000ef01  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000ef08  jz      short loc_18000EF2D
0x18000ef0a  mov     rax, [r13+8]
0x18000ef0e  lea     rdx, RegistryError
0x18000ef15  mov     [rsp+2E0h+lpcbData], rbx
0x18000ef1a  mov     r9d, 12Eh
0x18000ef20  mov     r8d, r12d
0x18000ef23  mov     [rsp+2E0h+phkResult], rax
0x18000ef28  call    McTemplateU0qqzz_EventWriteTransfer
0x18000ef2d  mov     rdi, [rsp+2E0h+var_288+8]
0x18000ef32  xorps   xmm6, xmm6
0x18000ef35  test    r12d, r12d
0x18000ef38  js      loc_18000EFEA
0x18000ef3e  lea     rbx, aClsid_0; "CLSID"
0x18000ef45  mov     [rsp+2E0h+var_288+8], 0
0x18000ef4e  mov     r8, rbx; unsigned __int16 *
0x18000ef51  lea     rdx, [rsp+2E0h+var_298]; struct ATL::CRegKey *
0x18000ef56  lea     rcx, [rsp+2E0h+var_288+8]; unsigned __int16 **
0x18000ef5b  call    ?RegUtilLoadStringWithAlloc@@YAJPEAPEAGAEAVCRegKey@ATL@@PEBG@Z; RegUtilLoadStringWithAlloc(ushort * *,ATL::CRegKey &,ushort const *)
0x18000ef60  mov     r12d, eax
0x18000ef63  test    eax, eax
0x18000ef65  js      short loc_18000EFAF
0x18000ef67  mov     rbx, [rsp+2E0h+var_288+8]
0x18000ef6c  lea     rdx, [rsp+2E0h+var_288+8]; pclsid
0x18000ef71  xorps   xmm0, xmm0
0x18000ef74  mov     rcx, rbx; lpsz
0x18000ef77  movups  xmmword ptr [rsp+2E0h+var_288+8], xmm0
0x18000ef7c  call    cs:__imp_CLSIDFromString
0x18000ef83  nop     dword ptr [rax+rax+00h]
0x18000ef88  mov     r12d, eax
0x18000ef8b  test    eax, eax
0x18000ef8d  js      short loc_18000EF94
0x18000ef8f  movaps  xmm6, xmmword ptr [rsp+2E0h+var_288+8]
0x18000ef94  test    rbx, rbx
0x18000ef97  jz      short loc_18000EFA8
0x18000ef99  mov     rcx, rbx; pv
0x18000ef9c  call    cs:__imp_CoTaskMemFree
0x18000efa3  nop     dword ptr [rax+rax+00h]
0x18000efa8  lea     rbx, aClsid_0; "CLSID"
0x18000efaf  cmp     r12d, 80070002h
0x18000efb6  jnz     short loc_18000EFEA
0x18000efb8  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 2
0x18000efbf  jz      short loc_18000EFE7
0x18000efc1  mov     rax, [r13+8]
0x18000efc5  lea     rdx, RegistryWarning
0x18000efcc  mov     [rsp+2E0h+lpcbData], rbx
0x18000efd1  mov     r9d, 13Ah
0x18000efd7  mov     r8d, 80070002h
0x18000efdd  mov     [rsp+2E0h+phkResult], rax
0x18000efe2  call    McTemplateU0qqzz_EventWriteTransfer
0x18000efe7  xor     r12d, r12d
0x18000efea  xor     ebx, ebx
0x18000efec  mov     dword ptr [rsp+2E0h+Data], ebx
0x18000eff0  test    r12d, r12d
0x18000eff3  js      loc_18000F418
0x18000eff9  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000effe  lea     rax, [rsp+2E0h+var_288+8]
0x18000f003  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18000f008  lea     r9, [rsp+2E0h+Data+4]; lpType
0x18000f00d  lea     rax, [rsp+2E0h+Data]
0x18000f012  mov     dword ptr [rsp+2E0h+Data+4], ebx
0x18000f016  xor     r8d, r8d; lpReserved
0x18000f019  mov     [rsp+2E0h+phkResult], rax; lpData
0x18000f01e  lea     rdx, aPublished; "Published"
0x18000f025  mov     dword ptr [rsp+2E0h+var_288+8], 4
0x18000f02d  call    cs:__imp_RegQueryValueExW
0x18000f034  nop     dword ptr [rax+rax+00h]
0x18000f039  test    eax, eax
0x18000f03b  jnz     loc_18000F201
0x18000f041  cmp     dword ptr [rsp+2E0h+Data+4], 4
0x18000f046  jz      loc_18000F11D
0x18000f04c  lea     eax, [rbx+0Dh]
0x18000f04f  movzx   r12d, ax
0x18000f053  or      r12d, 80070000h
0x18000f05a  test    r12d, r12d
0x18000f05d  jns     loc_18000F16E
0x18000f063  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, 1
0x18000f06a  jz      loc_18000F4F1
0x18000f070  lea     rdx, aPublished; "Published"
0x18000f077  mov     r9d, 159h
0x18000f07d  jmp     loc_18000F3FB
0x18000f082  cmp     ebx, r12d
0x18000f085  jnz     short loc_18000F0D4
0x18000f087  test    r14d, r14d
0x18000f08a  jnz     short loc_18000F0D4
0x18000f08c  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, r12b
0x18000f093  jz      short loc_18000F0B6
0x18000f095  mov     rax, [r13+8]
0x18000f099  lea     rdx, ThirdPartyNonExtensionHC
0x18000f0a0  mov     r9d, 0F4h
0x18000f0a6  mov     [rsp+2E0h+phkResult], rax
0x18000f0ab  mov     r8d, 80070005h
0x18000f0b1  call    McTemplateU0qqz_EventWriteTransfer
0x18000f0b6  test    rsi, rsi
0x18000f0b9  jz      short loc_18000F0CA
0x18000f0bb  mov     rcx, rsi; hKey
0x18000f0be  call    cs:__imp_RegCloseKey
0x18000f0c5  nop     dword ptr [rax+rax+00h]
0x18000f0ca  mov     eax, 80070005h
0x18000f0cf  jmp     loc_18000F5A5
0x18000f0d4  mov     dword ptr [rsp+2E0h+var_2A0], r15d
0x18000f0d9  test    ebx, ebx
0x18000f0db  jns     loc_18000EDAC
0x18000f0e1  test    cs:Microsoft_Windows_NDF_HelperClassDiscoveryEnableBits, r12b
0x18000f0e8  jz      loc_18000ED01
0x18000f0ee  lea     rax, aMatchattribute; "MatchAttributes"
0x18000f0f5  mov     r9d, 0FAh
0x18000f0fb  mov     [rsp+2E0h+lpcbData], rax
0x18000f100  lea     rdx, RegistryError
0x18000f107  mov     rax, [r13+8]
0x18000f10b  mov     r8d, ebx
0x18000f10e  mov     [rsp+2E0h+phkResult], rax
0x18000f113  call    McTemplateU0qqzz_EventWriteTransfer
0x18000f118  jmp     loc_18000ED01
  ... truncated ...
```
