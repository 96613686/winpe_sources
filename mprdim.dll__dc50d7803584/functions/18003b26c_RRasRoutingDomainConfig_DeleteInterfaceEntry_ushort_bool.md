# RRasRoutingDomainConfig::DeleteInterfaceEntry(ushort *,bool)

- ea: `0x18003b26c`
- end: `0x18003b6ce`
- name: `?DeleteInterfaceEntry@RRasRoutingDomainConfig@@AEAAKPEAG_N@Z`
- size: `1122`
- prototype: `__int64 __fastcall(RRasRoutingDomainConfig *this, wchar_t *String1, char)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18003b090`
- `0x1800431d8`

## callees

- `0x180033e90`
- `0x18003b26c`
- `0x18003eda8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003b59e`
- `msvcrt!_wcsicmp` at `0x18003b615`
- `msvcrt!_wcsicmp` at `0x18003b59e`
- `msvcrt!_wcsicmp` at `0x18003b615`
- `ADVAPI32!RegOpenKeyExW` at `0x18003b517`
- `ADVAPI32!RegOpenKeyExW` at `0x18003b517`
- `ADVAPI32!RegCloseKey` at `0x18003b39a`
- `ADVAPI32!RegCloseKey` at `0x18003b459`
- `ADVAPI32!RegCloseKey` at `0x18003b688`
- `ADVAPI32!RegCloseKey` at `0x18003b39a`
- `ADVAPI32!RegCloseKey` at `0x18003b459`
- `ADVAPI32!RegCloseKey` at `0x18003b688`
- `ADVAPI32!RegQueryValueExW` at `0x18003b56a`
- `ADVAPI32!RegQueryValueExW` at `0x18003b5e1`
- `ADVAPI32!RegQueryValueExW` at `0x18003b65b`
- `ADVAPI32!RegQueryValueExW` at `0x18003b56a`
- `ADVAPI32!RegQueryValueExW` at `0x18003b5e1`
- `ADVAPI32!RegQueryValueExW` at `0x18003b65b`
- `ADVAPI32!RegEnumKeyExW` at `0x18003b490`
- `ADVAPI32!RegEnumKeyExW` at `0x18003b490`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003b40e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003b40e`
- `ADVAPI32!RegDeleteTreeW` at `0x18003b69c`
- `ADVAPI32!RegDeleteTreeW` at `0x18003b69c`

## string_xrefs

- `0x18003b35c`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x18003b4b0`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x18003b534`: `Error %d occured while opening registry key %s.`
- `0x18003b427`: `Error %d occured while enumerating subkeys under registry key %s. #1`
- `0x18003b4b7`: `Error %d occured while enumerating subkeys under registry key %s. #2`
- `0x18003b34a`: `Error %d occured while opening interfaces subkeys under registry key %s. #1`
- `0x18003b58a`: `Error %d occured while querying value registry value name %s.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RRasRoutingDomainConfig::DeleteInterfaceEntry(
        RRasRoutingDomainConfig *this,
        wchar_t *String1,
        char a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  const wchar_t *v8; // rdx
  DWORD i; // edi
  unsigned int v11; // eax
  WCHAR *v12; // r9
  const wchar_t *v13; // rdx
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
    if ( !(_QWORD)xmmword_180071090 )
      goto LABEL_5;
    v8 = L"Error %d occured while opening interfaces subkeys under registry key %s. #1";
    goto LABEL_4;
  }
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v7 = v6;
  if ( !v6 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= cSubKeys )
        goto LABEL_5;
      memset_0(Data, 0, sizeof(Data));
      if ( phkResult )
      {
        RegCloseKey(phkResult);
        phkResult = 0;
      }
      cchName = 50;
      v11 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      v7 = v11;
      if ( v11 && v11 != 234 )
      {
        if ( !(_QWORD)xmmword_180071090 )
          continue;
        v12 = (WCHAR *)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
        v13 = L"Error %d occured while enumerating subkeys under registry key %s. #2";
        goto LABEL_19;
      }
      v11 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
      v7 = v11;
      if ( v11 )
      {
        if ( (_QWORD)xmmword_180071090 )
        {
          v12 = Name;
          v13 = L"Error %d occured while opening registry key %s.";
          goto LABEL_19;
        }
      }
      else
      {
        cbData = 80;
        v11 = RegQueryValueExW(phkResult, L"RoutingDomainId", 0, 0, (LPBYTE)Data, &cbData);
        v7 = v11;
        if ( v11 )
        {
          if ( (_QWORD)xmmword_180071090 )
          {
            v12 = (WCHAR *)L"RoutingDomainId";
            goto LABEL_26;
          }
          continue;
        }
        if ( _wcsicmp(String1a, Data) )
          continue;
        if ( String1 )
        {
          cbData = 514;
          v11 = RegQueryValueExW(phkResult, L"InterfaceName", 0, 0, (LPBYTE)v28, &cbData);
          v7 = v11;
          if ( v11 )
          {
            if ( (_QWORD)xmmword_180071090 )
            {
              v12 = (WCHAR *)L"InterfaceName";
              goto LABEL_26;
            }
            continue;
          }
          v29 = 0;
          if ( _wcsicmp(String1, v28) )
            continue;
        }
        if ( !a3 )
          goto LABEL_38;
        *(_DWORD *)v19 = 0;
        cbData = 4;
        v11 = RegQueryValueExW(phkResult, L"Type", 0, 0, v19, &cbData);
        v7 = v11;
        if ( !v11 )
        {
          if ( *(_DWORD *)v19 != 2 )
            continue;
LABEL_38:
          RegCloseKey(phkResult);
          phkResult = 0;
          v11 = RegDeleteTreeW(hKey, Name);
          v7 = v11;
          if ( v11 )
          {
            if ( (_QWORD)xmmword_180071090 )
            {
              v12 = Name;
              v13 = L"Error %d occured while deleting interface key %s.";
              goto LABEL_19;
            }
          }
          else
          {
            --i;
            --cSubKeys;
          }
          continue;
        }
        if ( (_QWORD)xmmword_180071090 )
        {
          v12 = (WCHAR *)L"Type";
LABEL_26:
          v13 = L"Error %d occured while querying value registry value name %s.";
LABEL_19:
          LOWORD(v26) = 0;
          FormatRRASErrorString(&v26, v13, v11, v12);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
            gCfgStoreEtwContext,
            xmmword_180071090,
            &v26);
          continue;
        }
      }
    }
  }
  if ( (_QWORD)xmmword_180071090 )
  {
    v8 = L"Error %d occured while enumerating subkeys under registry key %s. #1";
LABEL_4:
    LOWORD(v26) = 0;
    FormatRRASErrorString(&v26, v8, v6, L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces");
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180071090,
      &v26);
  }
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x18003b26c  mov     [rsp-8+arg_10], rbx
0x18003b271  push    rbp
0x18003b272  push    rsi
0x18003b273  push    rdi
0x18003b274  push    r14
0x18003b276  push    r15
0x18003b278  lea     rbp, [rsp-0AC0h]
0x18003b280  sub     rsp, 0BC0h
0x18003b287  mov     rax, cs:__security_cookie
0x18003b28e  xor     rax, rsp
0x18003b291  mov     [rbp+0AE0h+var_30], rax
0x18003b298  xor     r15d, r15d
0x18003b29b  mov     r14b, r8b
0x18003b29e  mov     rsi, rdx
0x18003b2a1  mov     [rsp+0BE0h+phkResult], r15
0x18003b2a6  mov     rbx, rcx
0x18003b2a9  mov     [rbp+0AE0h+cbMaxValueLen], r15d
0x18003b2ad  xor     edx, edx; Val
0x18003b2af  mov     [rbp+0AE0h+cbMaxValueNameLen], r15d
0x18003b2b3  lea     r8d, [r15+64h]; Size
0x18003b2b7  mov     [rbp+0AE0h+cValues], r15d
0x18003b2bb  lea     rcx, [rbp+0AE0h+Name]; void *
0x18003b2bf  mov     [rsp+0BE0h+cSubKeys], r15d
0x18003b2c4  call    memset_0
0x18003b2c9  xor     edx, edx; Val
0x18003b2cb  mov     [rsp+0BE0h+cchName], r15d
0x18003b2d0  mov     r8d, 204h; Size
0x18003b2d6  lea     rcx, [rbp+0AE0h+var_240]; void *
0x18003b2dd  call    memset_0
0x18003b2e2  xor     edx, edx; Val
0x18003b2e4  mov     [rsp+0BE0h+cbData], r15d
0x18003b2e9  lea     r8d, [r15+50h]; Size
0x18003b2ed  lea     rcx, [rbp+0AE0h+String1]; void *
0x18003b2f1  call    memset_0
0x18003b2f6  xor     edx, edx; Val
0x18003b2f8  mov     [rsp+0BE0h+hKey], r15
0x18003b2fd  mov     r8d, 7FCh; Size
0x18003b303  mov     [rbp+0AE0h+var_A40], r15d
0x18003b30a  lea     rcx, [rbp+0AE0h+var_A3C]; void *
0x18003b311  call    memset_0
0x18003b316  lea     rcx, [rbx+204h]
0x18003b31d  lea     r8, [rbp+0AE0h+String1]
0x18003b321  lea     edx, [r15+28h]
0x18003b325  call    MprConvertGuidToString
0x18003b32a  lea     rdx, [rsp+0BE0h+hKey]; HKEY *
0x18003b32f  mov     rcx, rbx; this
0x18003b332  call    ?OpenInterfacesKey@RRasRoutingDomainConfig@@QEAAKPEAPEAUHKEY__@@@Z; RRasRoutingDomainConfig::OpenInterfacesKey(HKEY__ * *)
0x18003b337  mov     ebx, eax
0x18003b339  test    eax, eax
0x18003b33b  jz      loc_18003B3C8
0x18003b341  cmp     qword ptr cs:xmmword_180071090, r15
0x18003b348  jz      short loc_18003B390
0x18003b34a  lea     rdx, aErrorDOccuredW_3; "Error %d occured while opening interfac"...
0x18003b351  mov     r8d, eax
0x18003b354  mov     word ptr [rbp+0AE0h+var_A40], r15w
0x18003b35c  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x18003b363  lea     rcx, [rbp+0AE0h+var_A40]
0x18003b36a  call    FormatRRASErrorString
0x18003b36f  mov     rdx, qword ptr cs:xmmword_180071090
0x18003b376  lea     r8, [rbp+0AE0h+var_A40]
0x18003b37d  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003b384  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003b38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b390  mov     rcx, [rsp+0BE0h+hKey]; hKey
0x18003b395  test    rcx, rcx
0x18003b398  jz      short loc_18003B3A0
0x18003b39a  call    cs:__imp_RegCloseKey
0x18003b3a0  mov     eax, ebx
0x18003b3a2  mov     rcx, [rbp+0AE0h+var_30]
0x18003b3a9  xor     rcx, rsp; StackCookie
0x18003b3ac  call    __security_check_cookie
0x18003b3b1  mov     rbx, [rsp+0BE0h+arg_10]
0x18003b3b9  add     rsp, 0BC0h
0x18003b3c0  pop     r15
0x18003b3c2  pop     r14
0x18003b3c4  pop     rdi
0x18003b3c5  pop     rsi
0x18003b3c6  pop     rbp
0x18003b3c7  retn
0x18003b3c8  mov     rcx, [rsp+0BE0h+hKey]; hKey
0x18003b3cd  lea     rax, [rbp+0AE0h+cbMaxValueLen]
0x18003b3d1  mov     [rsp+0BE0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18003b3d6  xor     r9d, r9d; lpReserved
0x18003b3d9  mov     [rsp+0BE0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18003b3de  xor     r8d, r8d; lpcchClass
0x18003b3e1  mov     [rsp+0BE0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18003b3e6  xor     edx, edx; lpClass
0x18003b3e8  lea     rax, [rbp+0AE0h+cbMaxValueNameLen]
0x18003b3ec  mov     [rsp+0BE0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18003b3f1  lea     rax, [rbp+0AE0h+cValues]
0x18003b3f5  mov     [rsp+0BE0h+lpcValues], rax; lpcValues
0x18003b3fa  lea     rax, [rsp+0BE0h+cSubKeys]
0x18003b3ff  mov     [rsp+0BE0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18003b404  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x18003b409  mov     [rsp+0BE0h+lpcSubKeys], rax; lpcSubKeys
0x18003b40e  call    cs:__imp_RegQueryInfoKeyW
0x18003b414  mov     ebx, eax
0x18003b416  test    eax, eax
0x18003b418  jz      short loc_18003B433
0x18003b41a  cmp     qword ptr cs:xmmword_180071090, r15
0x18003b421  jz      loc_18003B390
0x18003b427  lea     rdx, aErrorDOccuredW_5; "Error %d occured while enumerating subk"...
0x18003b42e  jmp     loc_18003B351
0x18003b433  mov     edi, r15d
0x18003b436  cmp     edi, [rsp+0BE0h+cSubKeys]
0x18003b43a  jnb     loc_18003B390
0x18003b440  xor     edx, edx; Val
0x18003b442  lea     rcx, [rbp+0AE0h+Data]; void *
0x18003b446  lea     r8d, [rdx+50h]; Size
0x18003b44a  call    memset_0
0x18003b44f  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x18003b454  test    rcx, rcx
0x18003b457  jz      short loc_18003B464
0x18003b459  call    cs:__imp_RegCloseKey
0x18003b45f  mov     [rsp+0BE0h+phkResult], r15
0x18003b464  mov     rcx, [rsp+0BE0h+hKey]; hKey
0x18003b469  lea     r9, [rsp+0BE0h+cchName]; lpcchName
0x18003b46e  mov     [rsp+0BE0h+lpcValues], r15; lpftLastWriteTime
0x18003b473  lea     r8, [rbp+0AE0h+Name]; lpName
0x18003b477  mov     [rsp+0BE0h+lpcbMaxClassLen], r15; lpcchClass
0x18003b47c  mov     edx, edi; dwIndex
0x18003b47e  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], r15; lpClass
0x18003b483  mov     [rsp+0BE0h+lpcSubKeys], r15; lpReserved
0x18003b488  mov     [rsp+0BE0h+cchName], 32h ; '2'
0x18003b490  call    cs:__imp_RegEnumKeyExW
0x18003b496  mov     ebx, eax
0x18003b498  test    eax, eax
0x18003b49a  jz      short loc_18003B4FB
0x18003b49c  cmp     eax, 0EAh
0x18003b4a1  jz      short loc_18003B4FB
0x18003b4a3  cmp     qword ptr cs:xmmword_180071090, r15
0x18003b4aa  jz      loc_18003B6C7
0x18003b4b0  lea     r9, SubKey; "System\\CurrentControlSet\\Services\\Re"...
0x18003b4b7  lea     rdx, aErrorDOccuredW_4; "Error %d occured while enumerating subk"...
0x18003b4be  mov     r8d, eax
0x18003b4c1  mov     word ptr [rbp+0AE0h+var_A40], r15w
0x18003b4c9  lea     rcx, [rbp+0AE0h+var_A40]
0x18003b4d0  call    FormatRRASErrorString
0x18003b4d5  mov     rdx, qword ptr cs:xmmword_180071090
0x18003b4dc  lea     r8, [rbp+0AE0h+var_A40]
0x18003b4e3  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003b4ea  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003b4f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4f6  jmp     loc_18003B6C7
0x18003b4fb  mov     rcx, [rsp+0BE0h+hKey]; hKey
0x18003b500  lea     rax, [rsp+0BE0h+phkResult]
0x18003b505  mov     r9d, 20019h; samDesired
0x18003b50b  mov     [rsp+0BE0h+lpcSubKeys], rax; phkResult
0x18003b510  xor     r8d, r8d; ulOptions
0x18003b513  lea     rdx, [rbp+0AE0h+Name]; lpSubKey
0x18003b517  call    cs:__imp_RegOpenKeyExW
0x18003b51d  mov     ebx, eax
0x18003b51f  test    eax, eax
0x18003b521  jz      short loc_18003B53D
0x18003b523  cmp     qword ptr cs:xmmword_180071090, r15
0x18003b52a  jz      loc_18003B6C7
0x18003b530  lea     r9, [rbp+0AE0h+Name]
0x18003b534  lea     rdx, aErrorDOccuredW; "Error %d occured while opening registry"...
0x18003b53b  jmp     short loc_18003B4BE
0x18003b53d  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x18003b542  lea     rax, [rsp+0BE0h+cbData]
0x18003b547  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18003b54c  lea     rdx, aRoutingdomaini; "RoutingDomainId"
0x18003b553  lea     rax, [rbp+0AE0h+Data]
0x18003b557  mov     [rsp+0BE0h+cbData], 50h ; 'P'
0x18003b55f  xor     r9d, r9d; lpType
0x18003b562  mov     [rsp+0BE0h+lpcSubKeys], rax; lpData
0x18003b567  xor     r8d, r8d; lpReserved
0x18003b56a  call    cs:__imp_RegQueryValueExW
0x18003b570  mov     ebx, eax
0x18003b572  test    eax, eax
0x18003b574  jz      short loc_18003B596
0x18003b576  cmp     qword ptr cs:xmmword_180071090, r15
0x18003b57d  jz      loc_18003B6C7
0x18003b583  lea     r9, aRoutingdomaini; "RoutingDomainId"
0x18003b58a  lea     rdx, aErrorDOccuredW_8; "Error %d occured while querying value r"...
0x18003b591  jmp     loc_18003B4BE
0x18003b596  lea     rdx, [rbp+0AE0h+Data]; String2
0x18003b59a  lea     rcx, [rbp+0AE0h+String1]; String1
0x18003b59e  call    cs:__imp__wcsicmp
0x18003b5a4  test    eax, eax
0x18003b5a6  jnz     loc_18003B6C7
0x18003b5ac  test    rsi, rsi
0x18003b5af  jz      short loc_18003B623
0x18003b5b1  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x18003b5b6  lea     rax, [rsp+0BE0h+cbData]
0x18003b5bb  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18003b5c0  lea     rdx, ValueName; "InterfaceName"
0x18003b5c7  lea     rax, [rbp+0AE0h+var_240]
0x18003b5ce  mov     [rsp+0BE0h+cbData], 202h
0x18003b5d6  xor     r9d, r9d; lpType
0x18003b5d9  mov     [rsp+0BE0h+lpcSubKeys], rax; lpData
0x18003b5de  xor     r8d, r8d; lpReserved
0x18003b5e1  call    cs:__imp_RegQueryValueExW
0x18003b5e7  mov     ebx, eax
0x18003b5e9  test    eax, eax
0x18003b5eb  jz      short loc_18003B603
0x18003b5ed  cmp     qword ptr cs:xmmword_180071090, r15
0x18003b5f4  jz      loc_18003B6C7
0x18003b5fa  lea     r9, ValueName; "InterfaceName"
0x18003b601  jmp     short loc_18003B58A
0x18003b603  lea     rdx, [rbp+0AE0h+var_240]; String2
0x18003b60a  mov     [rbp+0AE0h+var_3E], r15w
0x18003b612  mov     rcx, rsi; String1
0x18003b615  call    cs:__imp__wcsicmp
0x18003b61b  test    eax, eax
0x18003b61d  jnz     loc_18003B6C7
0x18003b623  test    r14b, r14b
0x18003b626  jz      short loc_18003B683
0x18003b628  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x18003b62d  lea     rax, [rsp+0BE0h+cbData]
0x18003b632  mov     [rsp+0BE0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18003b637  lea     rdx, aType; "Type"
0x18003b63e  lea     rax, [rsp+0BE0h+var_B64]
0x18003b643  mov     dword ptr [rsp+0BE0h+var_B64], r15d
0x18003b648  xor     r9d, r9d; lpType
0x18003b64b  mov     [rsp+0BE0h+lpcSubKeys], rax; lpData
0x18003b650  xor     r8d, r8d; lpReserved
0x18003b653  mov     [rsp+0BE0h+cbData], 4
0x18003b65b  call    cs:__imp_RegQueryValueExW
0x18003b661  mov     ebx, eax
0x18003b663  test    eax, eax
0x18003b665  jz      short loc_18003B67C
0x18003b667  cmp     qword ptr cs:xmmword_180071090, r15
0x18003b66e  jz      short loc_18003B6C7
0x18003b670  lea     r9, aType; "Type"
0x18003b677  jmp     loc_18003B58A
0x18003b67c  cmp     dword ptr [rsp+0BE0h+var_B64], 2
0x18003b681  jnz     short loc_18003B6C7
0x18003b683  mov     rcx, [rsp+0BE0h+phkResult]; hKey
0x18003b688  call    cs:__imp_RegCloseKey
0x18003b68e  mov     rcx, [rsp+0BE0h+hKey]; hKey
0x18003b693  lea     rdx, [rbp+0AE0h+Name]; lpSubKey
0x18003b697  mov     [rsp+0BE0h+phkResult], r15
0x18003b69c  call    cs:__imp_RegDeleteTreeW
0x18003b6a2  mov     ebx, eax
0x18003b6a4  test    eax, eax
0x18003b6a6  jz      short loc_18003B6C1
0x18003b6a8  cmp     qword ptr cs:xmmword_180071090, r15
0x18003b6af  jz      short loc_18003B6C7
0x18003b6b1  lea     r9, [rbp+0AE0h+Name]
0x18003b6b5  lea     rdx, aErrorDOccuredW_1; "Error %d occured while deleting interfa"...
0x18003b6bc  jmp     loc_18003B4BE
0x18003b6c1  dec     edi
0x18003b6c3  dec     [rsp+0BE0h+cSubKeys]
0x18003b6c7  inc     edi
0x18003b6c9  jmp     loc_18003B436
```
