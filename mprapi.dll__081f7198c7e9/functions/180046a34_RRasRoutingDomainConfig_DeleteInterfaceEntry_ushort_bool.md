# RRasRoutingDomainConfig::DeleteInterfaceEntry(ushort *,bool)

- ea: `0x180046a34`
- end: `0x180046ea1`
- name: `?DeleteInterfaceEntry@RRasRoutingDomainConfig@@AEAAKPEAG_N@Z`
- size: `1133`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, wchar_t *String1, char)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180046858`
- `0x18004e468`

## callees

- `0x1800302d0`
- `0x180046a34`
- `0x18004a364`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180046d34`
- `msvcrt!_wcsicmp` at `0x180046dab`
- `msvcrt!_wcsicmp` at `0x180046d34`
- `msvcrt!_wcsicmp` at `0x180046dab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046bef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046e1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046e73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046bef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046e1e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046e73`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180046ba3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180046ba3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180046c26`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180046c26`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046cad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180046cad`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046d00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046d77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046df1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046d00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046d77`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180046df1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180046e32`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180046e32`

## string_xrefs

- `0x180046b24`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x180046c46`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x180046b12`: `Error %d occured while opening interfaces subkeys under registry key %s. #1`
- `0x180046bbc`: `Error %d occured while enumerating subkeys under registry key %s. #1`
- `0x180046c4d`: `Error %d occured while enumerating subkeys under registry key %s. #2`
- `0x180046cca`: `Error %d occured while opening registry key %s.`
- `0x180046d20`: `Error %d occured while querying value registry value name %s.`

## pseudocode

```c
__int64 __fastcall RRasRoutingDomainConfig::DeleteInterfaceEntry(
        RRasRoutingDomainConfig *this,
        wchar_t *String1,
        char a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  const wchar_t *v8; // rdx
  DWORD v9; // edi
  unsigned int v10; // eax
  WCHAR *v11; // r9
  const wchar_t *v12; // rdx
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  BYTE v19[4]; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cbMaxValueLen; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cValues; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[56]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Data[40]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t String1a[40]; // [rsp+150h] [rbp+50h] BYREF
  int v26; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v27[2044]; // [rsp+1A4h] [rbp+A4h] BYREF
  wchar_t v28[257]; // [rsp+9A0h] [rbp+8A0h] BYREF
  __int16 v29; // [rsp+BA2h] [rbp+AA2h]

  phkResult = 0;
  cbMaxValueLen = 0;
  cbMaxValueNameLen = 0;
  cValues = 0;
  cSubKeys = 0;
  memset_0(Name, 0, 0x64u);
  cchName = 0;
  memset_0(v28, 0, 0x204u);
  cbData = 0;
  memset_0(String1a, 0, sizeof(String1a));
  hKey = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  MprConvertGuidToString((char *)this + 516, 40, String1a);
  v6 = RRasRoutingDomainConfig::OpenInterfacesKey(this, &hKey);
  v7 = v6;
  if ( v6 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_39;
    v8 = L"Error %d occured while opening interfaces subkeys under registry key %s. #1";
    goto LABEL_4;
  }
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v7 = v6;
  if ( !v6 )
  {
    v9 = 0;
    if ( !cSubKeys )
      goto LABEL_39;
    while ( 1 )
    {
      memset_0(Data, 0, sizeof(Data));
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      cchName = 50;
      v10 = RegEnumKeyExW(hKey, v9, Name, &cchName, 0, 0, 0, 0);
      v7 = v10;
      if ( !v10 || v10 == 234 )
      {
        v10 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
        v7 = v10;
        if ( v10 )
        {
          if ( !(_QWORD)xmmword_180078C50 )
            goto LABEL_38;
          v11 = Name;
          v12 = L"Error %d occured while opening registry key %s.";
          goto LABEL_15;
        }
        cbData = 80;
        v10 = RegQueryValueExW(phkResult, L"RoutingDomainId", 0, 0, (LPBYTE)Data, &cbData);
        v7 = v10;
        if ( v10 )
        {
          if ( !(_QWORD)xmmword_180078C50 )
            goto LABEL_38;
          v11 = (WCHAR *)L"RoutingDomainId";
LABEL_22:
          v12 = L"Error %d occured while querying value registry value name %s.";
LABEL_15:
          LOWORD(v26) = 0;
          FormatRRASErrorString(&v26, v12, v10, v11);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180078C50,
            &v26);
          goto LABEL_38;
        }
        if ( _wcsicmp(String1a, Data) )
          goto LABEL_38;
        if ( String1 )
        {
          cbData = 514;
          v10 = RegQueryValueExW(phkResult, L"InterfaceName", 0, 0, (LPBYTE)v28, &cbData);
          v7 = v10;
          if ( v10 )
          {
            if ( !(_QWORD)xmmword_180078C50 )
              goto LABEL_38;
            v11 = (WCHAR *)L"InterfaceName";
            goto LABEL_22;
          }
          v29 = 0;
          if ( _wcsicmp(String1, v28) )
            goto LABEL_38;
        }
        if ( a3 )
        {
          *(_DWORD *)v19 = 0;
          cbData = 4;
          v10 = RegQueryValueExW(phkResult, L"Type", 0, 0, v19, &cbData);
          v7 = v10;
          if ( v10 )
          {
            if ( !(_QWORD)xmmword_180078C50 )
              goto LABEL_38;
            v11 = (WCHAR *)L"Type";
            goto LABEL_22;
          }
          if ( *(_DWORD *)v19 != 2 )
            goto LABEL_38;
        }
        RegCloseKey(phkResult);
        phkResult = 0;
        v10 = RegDeleteTreeW(hKey, Name);
        v7 = v10;
        if ( !v10 )
        {
          --v9;
          --cSubKeys;
          goto LABEL_38;
        }
        if ( (_QWORD)xmmword_180078C50 )
        {
          v11 = Name;
          v12 = L"Error %d occured while deleting interface key %s.";
          goto LABEL_15;
        }
      }
      else if ( (_QWORD)xmmword_180078C50 )
      {
        v11 = (WCHAR *)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
        v12 = L"Error %d occured while enumerating subkeys under registry key %s. #2";
        goto LABEL_15;
      }
LABEL_38:
      if ( ++v9 >= cSubKeys )
        goto LABEL_39;
    }
  }
  if ( (_QWORD)xmmword_180078C50 )
  {
    v8 = L"Error %d occured while enumerating subkeys under registry key %s. #1";
LABEL_4:
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, v8, v6, L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces");
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v26);
  }
LABEL_39:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180046a34  mov     [rsp-8+arg_10], rbx
0x180046a39  push    rbp
0x180046a3a  push    rsi
0x180046a3b  push    rdi
0x180046a3c  push    r14
0x180046a3e  push    r15
0x180046a40  lea     rbp, [rsp-0AC0h]
0x180046a48  sub     rsp, 0BC0h
0x180046a4f  mov     rax, cs:__security_cookie
0x180046a56  xor     rax, rsp
0x180046a59  mov     [rbp+0AE0h+var_30], rax
0x180046a60  xor     r15d, r15d
0x180046a63  mov     r14b, r8b
0x180046a66  mov     rsi, rdx
0x180046a69  mov     [rsp+0BE0h+phkResult], r15
0x180046a6e  mov     rbx, rcx
0x180046a71  mov     [rbp+0AE0h+cbMaxValueLen], r15d
0x180046a75  xor     edx, edx; Val
0x180046a77  mov     [rbp+0AE0h+cbMaxValueNameLen], r15d
0x180046a7b  lea     r8d, [r15+64h]; Size
0x180046a7f  mov     [rbp+0AE0h+cValues], r15d
0x180046a83  lea     rcx, [rbp+0AE0h+Name]; void *
0x180046a87  mov     [rsp+0BE0h+cSubKeys], r15d
0x180046a8c  call    memset_0
0x180046a91  xor     edx, edx; Val
0x180046a93  mov     [rsp+0BE0h+cchName], r15d
0x180046a98  mov     r8d, 204h; Size
0x180046a9e  lea     rcx, [rbp+0AE0h+var_240]; void *
0x180046aa5  call    memset_0
0x180046aaa  xor     edx, edx; Val
0x180046aac  mov     [rsp+0BE0h+cbData], r15d
0x180046ab1  lea     r8d, [r15+50h]; Size
0x180046ab5  lea     rcx, [rbp+0AE0h+String1]; void *
0x180046ab9  call    memset_0
0x180046abe  xor     edx, edx; Val
0x180046ac0  mov     [rsp+0BE0h+hKey], r15
0x180046ac5  mov     r8d, 7FCh; Size
0x180046acb  mov     [rbp+0AE0h+var_A40], r15d
0x180046ad2  lea     rcx, [rbp+0AE0h+var_A3C]; void *
0x180046ad9  call    memset_0
0x180046ade  lea     rcx, [rbx+204h]
0x180046ae5  lea     r8, [rbp+0AE0h+String1]
0x180046ae9  lea     edx, [r15+28h]
0x180046aed  call    MprConvertGuidToString
0x180046af2  lea     rdx, [rsp+0BE0h+hKey]; HKEY *
0x180046af7  mov     rcx, rbx; this
0x180046afa  call    ?OpenInterfacesKey@RRasRoutingDomainConfig@@QEAAKPEAPEAUHKEY__@@@Z; RRasRoutingDomainConfig::OpenInterfacesKey(HKEY__ * *)
0x180046aff  mov     ebx, eax
0x180046b01  test    eax, eax
0x180046b03  jz      short loc_180046B5D
0x180046b05  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046b0c  jz      loc_180046E69
0x180046b12  lea     rdx, aErrorDOccuredW_1; "Error %d occured while opening interfac"...
0x180046b19  mov     r8d, eax
0x180046b1c  mov     word ptr [rbp+0AE0h+var_A40], r15w
0x180046b24  lea     r9, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Re"...
0x180046b2b  lea     rcx, [rbp+0AE0h+var_A40]
0x180046b32  call    FormatRRASErrorString
0x180046b37  mov     rdx, qword ptr cs:xmmword_180078C50
0x180046b3e  lea     r8, [rbp+0AE0h+var_A40]
0x180046b45  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180046b4c  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180046b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046b58  jmp     loc_180046E69
0x180046b5d  mov     rcx, [rsp+0BE0h+hKey]; hKey
0x180046b62  lea     rax, [rbp+0AE0h+cbMaxValueLen]
0x180046b66  mov     [rsp+0BE0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180046b6b  xor     r9d, r9d; lpReserved
0x180046b6e  mov     [rsp+0BE0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180046b73  xor     r8d, r8d; lpcchClass
0x180046b76  mov     [rsp+0BE0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180046b7b  xor     edx, edx; lpClass
0x180046b7d  lea     rax, [rbp+0AE0h+cbMaxValueNameLen]
0x180046b81  mov     [rsp+0BE0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180046b86  lea     rax, [rbp+0AE0h+cValues]
0x180046b8a  mov     [rsp+0BE0h+lpcValues], rax; lpcValues
0x180046b8f  lea     rax, [rsp+0BE0h+cSubKeys]
0x180046b94  mov     [rsp+0BE0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180046b99  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180046b9e  mov     [rsp+0BE0h+lpcSubKeys], rax; lpcSubKeys
0x180046ba3  call    cs:__imp_RegQueryInfoKeyW
0x180046ba9  mov     ebx, eax
0x180046bab  test    eax, eax
0x180046bad  jz      short loc_180046BC8
0x180046baf  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046bb6  jz      loc_180046E69
0x180046bbc  lea     rdx, aErrorDOccuredW_3; "Error %d occured while enumerating subk"...
0x180046bc3  jmp     loc_180046B19
0x180046bc8  mov     edi, r15d
0x180046bcb  cmp     [rsp+0BE0h+cSubKeys], r15d
0x180046bd0  jbe     loc_180046E69
0x180046bd6  xor     edx, edx; Val
0x180046bd8  lea     rcx, [rbp+0AE0h+Data]; void *
0x180046bdc  lea     r8d, [rdx+50h]; Size
0x180046be0  call    memset_0
0x180046be5  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x180046bea  test    rcx, rcx
0x180046bed  jz      short loc_180046BFA
0x180046bef  call    cs:__imp_RegCloseKey
0x180046bf5  mov     [rsp+0BE0h+phkResult], r15
0x180046bfa  mov     rcx, [rsp+0BE0h+hKey]; hKey
0x180046bff  lea     r9, [rsp+0BE0h+cchName]; lpcchName
0x180046c04  mov     [rsp+0BE0h+lpcValues], r15; lpftLastWriteTime
0x180046c09  lea     r8, [rbp+0AE0h+Name]; lpName
0x180046c0d  mov     [rsp+0BE0h+lpcbMaxClassLen], r15; lpcchClass
0x180046c12  mov     edx, edi; dwIndex
0x180046c14  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], r15; lpClass
0x180046c19  mov     [rsp+0BE0h+lpcSubKeys], r15; lpReserved
0x180046c1e  mov     [rsp+0BE0h+cchName], 32h ; '2'
0x180046c26  call    cs:__imp_RegEnumKeyExW
0x180046c2c  mov     ebx, eax
0x180046c2e  test    eax, eax
0x180046c30  jz      short loc_180046C91
0x180046c32  cmp     eax, 0EAh
0x180046c37  jz      short loc_180046C91
0x180046c39  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046c40  jz      loc_180046E5D
0x180046c46  lea     r9, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Re"...
0x180046c4d  lea     rdx, aErrorDOccuredW_2; "Error %d occured while enumerating subk"...
0x180046c54  mov     r8d, eax
0x180046c57  mov     word ptr [rbp+0AE0h+var_A40], r15w
0x180046c5f  lea     rcx, [rbp+0AE0h+var_A40]
0x180046c66  call    FormatRRASErrorString
0x180046c6b  mov     rdx, qword ptr cs:xmmword_180078C50
0x180046c72  lea     r8, [rbp+0AE0h+var_A40]
0x180046c79  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180046c80  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180046c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046c8c  jmp     loc_180046E5D
0x180046c91  mov     rcx, [rsp+0BE0h+hKey]; hKey
0x180046c96  lea     rax, [rsp+0BE0h+phkResult]
0x180046c9b  mov     r9d, 20019h; samDesired
0x180046ca1  mov     [rsp+0BE0h+lpcSubKeys], rax; phkResult
0x180046ca6  xor     r8d, r8d; ulOptions
0x180046ca9  lea     rdx, [rbp+0AE0h+Name]; lpSubKey
0x180046cad  call    cs:__imp_RegOpenKeyExW
0x180046cb3  mov     ebx, eax
0x180046cb5  test    eax, eax
0x180046cb7  jz      short loc_180046CD3
0x180046cb9  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046cc0  jz      loc_180046E5D
0x180046cc6  lea     r9, [rbp+0AE0h+Name]
0x180046cca  lea     rdx, aErrorDOccuredW; "Error %d occured while opening registry"...
0x180046cd1  jmp     short loc_180046C54
0x180046cd3  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x180046cd8  lea     rax, [rsp+0BE0h+cbData]
0x180046cdd  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180046ce2  lea     rdx, aRoutingdomaini; "RoutingDomainId"
0x180046ce9  lea     rax, [rbp+0AE0h+Data]
0x180046ced  mov     [rsp+0BE0h+cbData], 50h ; 'P'
0x180046cf5  xor     r9d, r9d; lpType
0x180046cf8  mov     [rsp+0BE0h+lpcSubKeys], rax; lpData
0x180046cfd  xor     r8d, r8d; lpReserved
0x180046d00  call    cs:__imp_RegQueryValueExW
0x180046d06  mov     ebx, eax
0x180046d08  test    eax, eax
0x180046d0a  jz      short loc_180046D2C
0x180046d0c  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046d13  jz      loc_180046E5D
0x180046d19  lea     r9, aRoutingdomaini; "RoutingDomainId"
0x180046d20  lea     rdx, aErrorDOccuredW_4; "Error %d occured while querying value r"...
0x180046d27  jmp     loc_180046C54
0x180046d2c  lea     rdx, [rbp+0AE0h+Data]; String2
0x180046d30  lea     rcx, [rbp+0AE0h+String1]; String1
0x180046d34  call    cs:__imp__wcsicmp
0x180046d3a  test    eax, eax
0x180046d3c  jnz     loc_180046E5D
0x180046d42  test    rsi, rsi
0x180046d45  jz      short loc_180046DB9
0x180046d47  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x180046d4c  lea     rax, [rsp+0BE0h+cbData]
0x180046d51  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180046d56  lea     rdx, aInterfacename; "InterfaceName"
0x180046d5d  lea     rax, [rbp+0AE0h+var_240]
0x180046d64  mov     [rsp+0BE0h+cbData], 202h
0x180046d6c  xor     r9d, r9d; lpType
0x180046d6f  mov     [rsp+0BE0h+lpcSubKeys], rax; lpData
0x180046d74  xor     r8d, r8d; lpReserved
0x180046d77  call    cs:__imp_RegQueryValueExW
0x180046d7d  mov     ebx, eax
0x180046d7f  test    eax, eax
0x180046d81  jz      short loc_180046D99
0x180046d83  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046d8a  jz      loc_180046E5D
0x180046d90  lea     r9, aInterfacename; "InterfaceName"
0x180046d97  jmp     short loc_180046D20
0x180046d99  lea     rdx, [rbp+0AE0h+var_240]; String2
0x180046da0  mov     [rbp+0AE0h+var_3E], r15w
0x180046da8  mov     rcx, rsi; String1
0x180046dab  call    cs:__imp__wcsicmp
0x180046db1  test    eax, eax
0x180046db3  jnz     loc_180046E5D
0x180046db9  test    r14b, r14b
0x180046dbc  jz      short loc_180046E19
0x180046dbe  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x180046dc3  lea     rax, [rsp+0BE0h+cbData]
0x180046dc8  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180046dcd  lea     rdx, aType; "Type"
0x180046dd4  lea     rax, [rsp+0BE0h+var_B64]
0x180046dd9  mov     dword ptr [rsp+0BE0h+var_B64], r15d
0x180046dde  xor     r9d, r9d; lpType
0x180046de1  mov     [rsp+0BE0h+lpcSubKeys], rax; lpData
0x180046de6  xor     r8d, r8d; lpReserved
0x180046de9  mov     [rsp+0BE0h+cbData], 4
0x180046df1  call    cs:__imp_RegQueryValueExW
0x180046df7  mov     ebx, eax
0x180046df9  test    eax, eax
0x180046dfb  jz      short loc_180046E12
0x180046dfd  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046e04  jz      short loc_180046E5D
0x180046e06  lea     r9, aType; "Type"
0x180046e0d  jmp     loc_180046D20
0x180046e12  cmp     dword ptr [rsp+0BE0h+var_B64], 2
0x180046e17  jnz     short loc_180046E5D
0x180046e19  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x180046e1e  call    cs:__imp_RegCloseKey
0x180046e24  mov     rcx, [rsp+0BE0h+hKey]; hKey
0x180046e29  lea     rdx, [rbp+0AE0h+Name]; lpSubKey
0x180046e2d  mov     [rsp+0BE0h+phkResult], r15
0x180046e32  call    cs:__imp_RegDeleteTreeW
0x180046e38  mov     ebx, eax
0x180046e3a  test    eax, eax
0x180046e3c  jz      short loc_180046E57
0x180046e3e  cmp     qword ptr cs:xmmword_180078C50, r15
0x180046e45  jz      short loc_180046E5D
0x180046e47  lea     r9, [rbp+0AE0h+Name]
0x180046e4b  lea     rdx, aErrorDOccuredW_0; "Error %d occured while deleting interfa"...
0x180046e52  jmp     loc_180046C54
0x180046e57  dec     edi
0x180046e59  dec     [rsp+0BE0h+cSubKeys]
0x180046e5d  inc     edi
0x180046e5f  cmp     edi, [rsp+0BE0h+cSubKeys]
0x180046e63  jb      loc_180046BD6
0x180046e69  mov     rcx, [rsp+0BE0h+hKey]; hKey
0x180046e6e  test    rcx, rcx
0x180046e71  jz      short loc_180046E79
0x180046e73  call    cs:__imp_RegCloseKey
0x180046e79  mov     eax, ebx
0x180046e7b  mov     rcx, [rbp+0AE0h+var_30]
0x180046e82  xor     rcx, rsp; StackCookie
0x180046e85  call    __security_check_cookie
0x180046e8a  mov     rbx, [rsp+0BE0h+arg_10]
0x180046e92  add     rsp, 0BC0h
0x180046e99  pop     r15
0x180046e9b  pop     r14
0x180046e9d  pop     rdi
0x180046e9e  pop     rsi
0x180046e9f  pop     rbp
0x180046ea0  retn
```
