# RRasRoutingDomainConfig::DoesInterfaceEntryExists(ushort *,_ROUTER_INTERFACE_TYPE)

- ea: `0x18003b930`
- end: `0x18003bd53`
- name: `?DoesInterfaceEntryExists@RRasRoutingDomainConfig@@AEAA_NPEAGW4_ROUTER_INTERFACE_TYPE@@@Z`
- size: `1059`
- prototype: `char __fastcall(RRasRoutingDomainConfig *this, wchar_t *String1, enum _ROUTER_INTERFACE_TYPE)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18003a4d8`

## callees

- `0x180033e90`
- `0x18003b930`
- `0x18003eda8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003bc30`
- `msvcrt!_wcsicmp` at `0x18003bc9f`
- `msvcrt!_wcsicmp` at `0x18003bc30`
- `msvcrt!_wcsicmp` at `0x18003bc9f`
- `ADVAPI32!RegOpenKeyExW` at `0x18003bba7`
- `ADVAPI32!RegOpenKeyExW` at `0x18003bba7`
- `ADVAPI32!RegCloseKey` at `0x18003baed`
- `ADVAPI32!RegCloseKey` at `0x18003bd14`
- `ADVAPI32!RegCloseKey` at `0x18003bd23`
- `ADVAPI32!RegCloseKey` at `0x18003baed`
- `ADVAPI32!RegCloseKey` at `0x18003bd14`
- `ADVAPI32!RegCloseKey` at `0x18003bd23`
- `ADVAPI32!RegQueryValueExW` at `0x18003bbfb`
- `ADVAPI32!RegQueryValueExW` at `0x18003bc6e`
- `ADVAPI32!RegQueryValueExW` at `0x18003bcd7`
- `ADVAPI32!RegQueryValueExW` at `0x18003bbfb`
- `ADVAPI32!RegQueryValueExW` at `0x18003bc6e`
- `ADVAPI32!RegQueryValueExW` at `0x18003bcd7`
- `ADVAPI32!RegEnumKeyExW` at `0x18003bb23`
- `ADVAPI32!RegEnumKeyExW` at `0x18003bb23`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003ba9c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003ba9c`

## string_xrefs

- `0x18003ba16`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x18003bb44`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x18003bbc5`: `Error %d occured while opening registry key %s.`
- `0x18003bab6`: `Error %d occured while enumerating subkeys under registry key %s. #1`
- `0x18003bb4b`: `Error %d occured while enumerating subkeys under registry key %s. #2`
- `0x18003bc1c`: `Error %d occured while querying value registry value name %s.`
- `0x18003ba0f`: `Error %d occurred while opening interfaces key under registry key %s. #1`

## pseudocode

```c
char __fastcall RRasRoutingDomainConfig::DoesInterfaceEntryExists(
        RRasRoutingDomainConfig *this,
        wchar_t *String1,
        enum _ROUTER_INTERFACE_TYPE a3)
{
  char v5; // di
  unsigned int v6; // eax
  __int64 v7; // r8
  const wchar_t *v8; // rdx
  unsigned int v9; // eax
  DWORD i; // ebx
  unsigned int v11; // eax
  __int64 v12; // r8
  WCHAR *v13; // r9
  const wchar_t *v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  BYTE v24[8]; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxValueLen; // [rsp+88h] [rbp-78h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD cValues[4]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Name[56]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t Data[40]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t String1a[40]; // [rsp+160h] [rbp+60h] BYREF
  int v32; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v33[2044]; // [rsp+1B4h] [rbp+B4h] BYREF
  wchar_t v34[257]; // [rsp+9B0h] [rbp+8B0h] BYREF
  __int16 v35; // [rsp+BB2h] [rbp+AB2h]

  phkResult = 0;
  cbMaxValueLen = 0;
  cbMaxValueNameLen = 0;
  cValues[0] = 0;
  cSubKeys = 0;
  memset_0(Name, 0, 0x64u);
  cchName = 0;
  memset_0(v34, 0, 0x204u);
  cbData = 0;
  memset_0(String1a, 0, sizeof(String1a));
  hKey = 0;
  v32 = 0;
  v5 = 0;
  memset_0(v33, 0, sizeof(v33));
  MprConvertGuidToString((char *)this + 516, 40, String1a);
  v6 = RRasRoutingDomainConfig::OpenInterfacesKey(this, &hKey);
  v7 = v6;
  if ( v6 )
  {
    if ( !(_QWORD)xmmword_180071090 )
      goto LABEL_35;
    v8 = L"Error %d occurred while opening interfaces key under registry key %s. #1";
    goto LABEL_4;
  }
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v7 = v9;
  if ( !v9 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= cSubKeys )
        goto LABEL_35;
      memset_0(Data, 0, sizeof(Data));
      *(_DWORD *)v24 = 0;
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      cchName = 50;
      v11 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      v12 = v11;
      if ( v11 && v11 != 234 )
      {
        if ( !(_QWORD)xmmword_180071090 )
          continue;
        v13 = (WCHAR *)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
        v14 = L"Error %d occured while enumerating subkeys under registry key %s. #2";
        goto LABEL_16;
      }
      v15 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
      v12 = v15;
      if ( v15 )
      {
        if ( (_QWORD)xmmword_180071090 )
        {
          v13 = Name;
          v14 = L"Error %d occured while opening registry key %s.";
          goto LABEL_16;
        }
      }
      else
      {
        cbData = 80;
        v16 = RegQueryValueExW(phkResult, L"RoutingDomainId", 0, 0, (LPBYTE)Data, &cbData);
        v12 = v16;
        if ( v16 )
        {
          if ( (_QWORD)xmmword_180071090 )
          {
            v13 = (WCHAR *)L"RoutingDomainId";
            goto LABEL_23;
          }
        }
        else if ( !_wcsicmp(String1a, Data) )
        {
          cbData = 514;
          v17 = RegQueryValueExW(phkResult, L"InterfaceName", 0, 0, (LPBYTE)v34, &cbData);
          v12 = v17;
          if ( v17 )
          {
            if ( (_QWORD)xmmword_180071090 )
            {
              v13 = (WCHAR *)L"InterfaceName";
              goto LABEL_23;
            }
          }
          else
          {
            v35 = 0;
            if ( !_wcsicmp(String1, v34) )
            {
              cbData = 4;
              v18 = RegQueryValueExW(phkResult, L"Type", 0, 0, v24, &cbData);
              v12 = v18;
              if ( v18 )
              {
                if ( (_QWORD)xmmword_180071090 )
                {
                  v13 = (WCHAR *)L"Type";
LABEL_23:
                  v14 = L"Error %d occured while querying value registry value name %s.";
LABEL_16:
                  LOWORD(v32) = 0;
                  FormatRRASErrorString(&v32, v14, v12, v13);
                  ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
                    gCfgStoreEtwContext,
                    xmmword_180071090,
                    &v32);
                  continue;
                }
              }
              else if ( *(_DWORD *)v24 == 4 )
              {
                v5 = 1;
                goto LABEL_35;
              }
            }
          }
        }
      }
    }
  }
  if ( (_QWORD)xmmword_180071090 )
  {
    v8 = L"Error %d occured while enumerating subkeys under registry key %s. #1";
LABEL_4:
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v32, v8, v7, L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces");
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v32);
  }
LABEL_35:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18003b930  mov     [rsp-8+arg_10], rbx
0x18003b935  mov     [rsp-8+arg_18], rsi
0x18003b93a  push    rbp
0x18003b93b  push    rdi
0x18003b93c  push    r14
0x18003b93e  lea     rbp, [rsp-0AD0h]
0x18003b946  sub     rsp, 0BD0h
0x18003b94d  mov     rax, cs:__security_cookie
0x18003b954  xor     rax, rsp
0x18003b957  mov     [rbp+0AE0h+var_20], rax
0x18003b95e  xor     r14d, r14d
0x18003b961  mov     rsi, rdx
0x18003b964  mov     rbx, rcx
0x18003b967  mov     [rsp+0BE0h+phkResult], r14
0x18003b96c  xor     edx, edx; Val
0x18003b96e  mov     [rbp+0AE0h+cbMaxValueLen], r14d
0x18003b972  lea     rcx, [rbp+0AE0h+Name]; void *
0x18003b976  mov     [rbp+0AE0h+cbMaxValueNameLen], r14d
0x18003b97a  lea     r8d, [r14+64h]; Size
0x18003b97e  mov     [rbp+0AE0h+cValues], r14d
0x18003b982  mov     [rsp+0BE0h+cSubKeys], r14d
0x18003b987  call    memset_0
0x18003b98c  xor     edx, edx; Val
0x18003b98e  mov     [rsp+0BE0h+cchName], r14d
0x18003b993  mov     r8d, 204h; Size
0x18003b999  lea     rcx, [rbp+0AE0h+var_230]; void *
0x18003b9a0  call    memset_0
0x18003b9a5  xor     edx, edx; Val
0x18003b9a7  mov     [rsp+0BE0h+cbData], r14d
0x18003b9ac  lea     r8d, [r14+50h]; Size
0x18003b9b0  lea     rcx, [rbp+0AE0h+String1]; void *
0x18003b9b4  call    memset_0
0x18003b9b9  xor     edx, edx; Val
0x18003b9bb  mov     [rbp+0AE0h+hKey], r14
0x18003b9bf  mov     r8d, 7FCh; Size
0x18003b9c5  mov     [rbp+0AE0h+var_A30], r14d
0x18003b9cc  lea     rcx, [rbp+0AE0h+var_A2C]; void *
0x18003b9d3  mov     dil, r14b
0x18003b9d6  call    memset_0
0x18003b9db  lea     rcx, [rbx+204h]
0x18003b9e2  lea     r8, [rbp+0AE0h+String1]
0x18003b9e6  lea     edx, [r14+28h]
0x18003b9ea  call    MprConvertGuidToString
0x18003b9ef  lea     rdx, [rbp+0AE0h+hKey]; HKEY *
0x18003b9f3  mov     rcx, rbx; this
0x18003b9f6  call    ?OpenInterfacesKey@RRasRoutingDomainConfig@@QEAAKPEAPEAUHKEY__@@@Z; RRasRoutingDomainConfig::OpenInterfacesKey(HKEY__ * *)
0x18003b9fb  mov     r8d, eax
0x18003b9fe  test    eax, eax
0x18003ba00  jz      short loc_18003BA57
0x18003ba02  cmp     qword ptr cs:xmmword_180071090, r14
0x18003ba09  jz      loc_18003BD0A
0x18003ba0f  lea     rdx, aErrorDOccurred; "Error %d occurred while opening interfa"...
0x18003ba16  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x18003ba1d  mov     word ptr [rbp+0AE0h+var_A30], r14w
0x18003ba25  lea     rcx, [rbp+0AE0h+var_A30]
0x18003ba2c  call    FormatRRASErrorString
0x18003ba31  mov     rdx, qword ptr cs:xmmword_180071090
0x18003ba38  lea     r8, [rbp+0AE0h+var_A30]
0x18003ba3f  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003ba46  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003ba4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ba52  jmp     loc_18003BD0A
0x18003ba57  mov     rcx, [rbp+0AE0h+hKey]; hKey
0x18003ba5b  lea     rax, [rbp+0AE0h+cbMaxValueLen]
0x18003ba5f  mov     [rsp+0BE0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18003ba64  xor     r9d, r9d; lpReserved
0x18003ba67  mov     [rsp+0BE0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18003ba6c  xor     r8d, r8d; lpcchClass
0x18003ba6f  mov     [rsp+0BE0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18003ba74  xor     edx, edx; lpClass
0x18003ba76  lea     rax, [rbp+0AE0h+cbMaxValueNameLen]
0x18003ba7a  mov     [rsp+0BE0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18003ba7f  lea     rax, [rbp+0AE0h+cValues]
0x18003ba83  mov     [rsp+0BE0h+lpcValues], rax; lpcValues
0x18003ba88  lea     rax, [rsp+0BE0h+cSubKeys]
0x18003ba8d  mov     [rsp+0BE0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18003ba92  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18003ba97  mov     [rsp+0BE0h+lpcSubKeys], rax; lpcSubKeys
0x18003ba9c  call    cs:__imp_RegQueryInfoKeyW
0x18003baa2  mov     r8d, eax
0x18003baa5  test    eax, eax
0x18003baa7  jz      short loc_18003BAC2
0x18003baa9  cmp     qword ptr cs:xmmword_180071090, r14
0x18003bab0  jz      loc_18003BD0A
0x18003bab6  lea     rdx, aErrorDOccuredW_5; "Error %d occured while enumerating subk"...
0x18003babd  jmp     loc_18003BA16
0x18003bac2  mov     ebx, r14d
0x18003bac5  cmp     ebx, [rsp+0BE0h+cSubKeys]
0x18003bac9  jnb     loc_18003BD0A
0x18003bacf  xor     edx, edx; Val
0x18003bad1  lea     rcx, [rbp+0AE0h+Data]; void *
0x18003bad5  lea     r8d, [rdx+50h]; Size
0x18003bad9  call    memset_0
0x18003bade  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x18003bae3  mov     dword ptr [rsp+0BE0h+var_B68], r14d
0x18003bae8  test    rcx, rcx
0x18003baeb  jz      short loc_18003BAF8
0x18003baed  call    cs:__imp_RegCloseKey
0x18003baf3  mov     [rsp+0BE0h+phkResult], r14
0x18003baf8  mov     rcx, [rbp+0AE0h+hKey]; hKey
0x18003bafc  lea     r9, [rsp+0BE0h+cchName]; lpcchName
0x18003bb01  mov     [rsp+0BE0h+lpcValues], r14; lpftLastWriteTime
0x18003bb06  lea     r8, [rbp+0AE0h+Name]; lpName
0x18003bb0a  mov     [rsp+0BE0h+lpcbMaxClassLen], r14; lpcchClass
0x18003bb0f  mov     edx, ebx; dwIndex
0x18003bb11  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], r14; lpClass
0x18003bb16  mov     [rsp+0BE0h+lpcSubKeys], r14; lpReserved
0x18003bb1b  mov     [rsp+0BE0h+cchName], 32h ; '2'
0x18003bb23  call    cs:__imp_RegEnumKeyExW
0x18003bb29  mov     r8d, eax
0x18003bb2c  test    eax, eax
0x18003bb2e  jz      short loc_18003BB8C
0x18003bb30  cmp     eax, 0EAh
0x18003bb35  jz      short loc_18003BB8C
0x18003bb37  cmp     qword ptr cs:xmmword_180071090, r14
0x18003bb3e  jz      loc_18003BD00
0x18003bb44  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x18003bb4b  lea     rdx, aErrorDOccuredW_4; "Error %d occured while enumerating subk"...
0x18003bb52  lea     rcx, [rbp+0AE0h+var_A30]
0x18003bb59  mov     word ptr [rbp+0AE0h+var_A30], r14w
0x18003bb61  call    FormatRRASErrorString
0x18003bb66  mov     rdx, qword ptr cs:xmmword_180071090
0x18003bb6d  lea     r8, [rbp+0AE0h+var_A30]
0x18003bb74  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003bb7b  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003bb82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb87  jmp     loc_18003BD00
0x18003bb8c  mov     rcx, [rbp+0AE0h+hKey]; hKey
0x18003bb90  lea     rax, [rsp+0BE0h+phkResult]
0x18003bb95  mov     r9d, 20019h; samDesired
0x18003bb9b  mov     [rsp+0BE0h+lpcSubKeys], rax; phkResult
0x18003bba0  xor     r8d, r8d; ulOptions
0x18003bba3  lea     rdx, [rbp+0AE0h+Name]; lpSubKey
0x18003bba7  call    cs:__imp_RegOpenKeyExW
0x18003bbad  mov     r8d, eax
0x18003bbb0  test    eax, eax
0x18003bbb2  jz      short loc_18003BBCE
0x18003bbb4  cmp     qword ptr cs:xmmword_180071090, r14
0x18003bbbb  jz      loc_18003BD00
0x18003bbc1  lea     r9, [rbp+0AE0h+Name]
0x18003bbc5  lea     rdx, aErrorDOccuredW; "Error %d occured while opening registry"...
0x18003bbcc  jmp     short loc_18003BB52
0x18003bbce  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x18003bbd3  lea     rax, [rsp+0BE0h+cbData]
0x18003bbd8  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18003bbdd  lea     rdx, aRoutingdomaini; "RoutingDomainId"
0x18003bbe4  lea     rax, [rbp+0AE0h+Data]
0x18003bbe8  mov     [rsp+0BE0h+cbData], 50h ; 'P'
0x18003bbf0  xor     r9d, r9d; lpType
0x18003bbf3  mov     [rsp+0BE0h+lpcSubKeys], rax; lpData
0x18003bbf8  xor     r8d, r8d; lpReserved
0x18003bbfb  call    cs:__imp_RegQueryValueExW
0x18003bc01  mov     r8d, eax
0x18003bc04  test    eax, eax
0x18003bc06  jz      short loc_18003BC28
0x18003bc08  cmp     qword ptr cs:xmmword_180071090, r14
0x18003bc0f  jz      loc_18003BD00
0x18003bc15  lea     r9, aRoutingdomaini; "RoutingDomainId"
0x18003bc1c  lea     rdx, aErrorDOccuredW_8; "Error %d occured while querying value r"...
0x18003bc23  jmp     loc_18003BB52
0x18003bc28  lea     rdx, [rbp+0AE0h+Data]; String2
0x18003bc2c  lea     rcx, [rbp+0AE0h+String1]; String1
0x18003bc30  call    cs:__imp__wcsicmp
0x18003bc36  test    eax, eax
0x18003bc38  jnz     loc_18003BD00
0x18003bc3e  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x18003bc43  lea     rax, [rsp+0BE0h+cbData]
0x18003bc48  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18003bc4d  lea     rdx, ValueName; "InterfaceName"
0x18003bc54  lea     rax, [rbp+0AE0h+var_230]
0x18003bc5b  mov     [rsp+0BE0h+cbData], 202h
0x18003bc63  xor     r9d, r9d; lpType
0x18003bc66  mov     [rsp+0BE0h+lpcSubKeys], rax; lpData
0x18003bc6b  xor     r8d, r8d; lpReserved
0x18003bc6e  call    cs:__imp_RegQueryValueExW
0x18003bc74  mov     r8d, eax
0x18003bc77  test    eax, eax
0x18003bc79  jz      short loc_18003BC8D
0x18003bc7b  cmp     qword ptr cs:xmmword_180071090, r14
0x18003bc82  jz      short loc_18003BD00
0x18003bc84  lea     r9, ValueName; "InterfaceName"
0x18003bc8b  jmp     short loc_18003BC1C
0x18003bc8d  lea     rdx, [rbp+0AE0h+var_230]; String2
0x18003bc94  mov     [rbp+0AE0h+var_2E], r14w
0x18003bc9c  mov     rcx, rsi; String1
0x18003bc9f  call    cs:__imp__wcsicmp
0x18003bca5  test    eax, eax
0x18003bca7  jnz     short loc_18003BD00
0x18003bca9  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x18003bcae  lea     rax, [rsp+0BE0h+cbData]
0x18003bcb3  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18003bcb8  lea     rdx, aType; "Type"
0x18003bcbf  lea     rax, [rsp+0BE0h+var_B68]
0x18003bcc4  mov     [rsp+0BE0h+cbData], 4
0x18003bccc  xor     r9d, r9d; lpType
0x18003bccf  mov     [rsp+0BE0h+lpcSubKeys], rax; lpData
0x18003bcd4  xor     r8d, r8d; lpReserved
0x18003bcd7  call    cs:__imp_RegQueryValueExW
0x18003bcdd  mov     r8d, eax
0x18003bce0  test    eax, eax
0x18003bce2  jz      short loc_18003BCF9
0x18003bce4  cmp     qword ptr cs:xmmword_180071090, r14
0x18003bceb  jz      short loc_18003BD00
0x18003bced  lea     r9, aType; "Type"
0x18003bcf4  jmp     loc_18003BC1C
0x18003bcf9  cmp     dword ptr [rsp+0BE0h+var_B68], 4
0x18003bcfe  jz      short loc_18003BD07
0x18003bd00  inc     ebx
0x18003bd02  jmp     loc_18003BAC5
0x18003bd07  mov     dil, 1
0x18003bd0a  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x18003bd0f  test    rcx, rcx
0x18003bd12  jz      short loc_18003BD1A
0x18003bd14  call    cs:__imp_RegCloseKey
0x18003bd1a  mov     rcx, [rbp+0AE0h+hKey]; hKey
0x18003bd1e  test    rcx, rcx
0x18003bd21  jz      short loc_18003BD29
0x18003bd23  call    cs:__imp_RegCloseKey
0x18003bd29  mov     al, dil
0x18003bd2c  mov     rcx, [rbp+0AE0h+var_20]
0x18003bd33  xor     rcx, rsp; StackCookie
0x18003bd36  call    __security_check_cookie
0x18003bd3b  lea     r11, [rsp+0BE0h+var_10]
0x18003bd43  mov     rbx, [r11+30h]
0x18003bd47  mov     rsi, [r11+38h]
0x18003bd4b  mov     rsp, r11
0x18003bd4e  pop     r14
0x18003bd50  pop     rdi
0x18003bd51  pop     rbp
0x18003bd52  retn
```
