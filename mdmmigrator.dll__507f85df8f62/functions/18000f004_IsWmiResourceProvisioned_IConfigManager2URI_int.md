# IsWmiResourceProvisioned(IConfigManager2URI *,int *)

- ea: `0x18000f004`
- end: `0x18000f5be`
- name: `?IsWmiResourceProvisioned@@YAJPEAUIConfigManager2URI@@PEAH@Z`
- size: `1466`
- prototype: `__int64 __fastcall(struct IConfigManager2URI *, int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010170`
- `0x180010610`
- `0x180010864`

## callees

- `0x1800022e0`
- `0x1800026b0`
- `0x180002cbc`
- `0x1800034f0`
- `0x18000f004`
- `0x180020010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f329`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f0c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f0c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f08d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f129`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4db`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f08d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f129`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f4db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f09e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f0c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f13a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f3a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f3f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f452`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f4a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f4b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f4ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f4ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f52a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f54e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f576`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f09e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f0c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f13a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f3a4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f3f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f452`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f4a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f4b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f4ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f4ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f52a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f54e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f576`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f108`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f1b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f22c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f277`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f108`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f1b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f22c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f277`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f17b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f1f3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f3ce`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f421`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f47c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f17b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f1f3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f3ce`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f421`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000f47c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000f311`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000f37a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000f311`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000f37a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000f0d4`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18000f0d4`

## pseudocode

```c
__int64 __fastcall IsWmiResourceProvisioned(struct IConfigManager2URI *a1, int *a2)
{
  DWORD v3; // r14d
  __int64 v4; // rdx
  __int64 v5; // rcx
  int v6; // r12d
  DWORD LastError; // ebx
  char IsStateSeparationEnabled; // al
  const WCHAR *v10; // rdx
  LSTATUS v11; // eax
  int v12; // ebx
  int v13; // ebx
  DWORD v14; // edi
  LSTATUS i; // eax
  LSTATUS v16; // eax
  DWORD v17; // r13d
  LSTATUS v18; // eax
  DWORD v19; // esi
  DWORD v20; // edx
  LSTATUS v21; // eax
  DWORD j; // edx
  size_t v23; // rbx
  void *v24; // rdi
  LSTATUS v25; // eax
  const struct std::nothrow_t *v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v33; // [rsp+68h] [rbp-98h] BYREF
  HKEY v34; // [rsp+70h] [rbp-90h] BYREF
  DWORD v35; // [rsp+78h] [rbp-88h]
  WCHAR ValueName[12]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v37[12]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR Name[56]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[264]; // [rsp+120h] [rbp+20h] BYREF

  v3 = 0;
  hKey = 0;
  cchName = 260;
  cbData = 0;
  if ( !a1 || !a2 )
    return 2147942487LL;
  *a2 = 0;
  bstrString = 0;
  v6 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, _QWORD, BSTR *))(*(_QWORD *)a1 + 64LL))(
         a1,
         0,
         0,
         &bstrString);
  if ( v6 < 0 )
  {
LABEL_4:
    if ( bstrString )
      SysFreeString(bstrString);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(hKey);
    SetLastError(LastError);
  }
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled(v5, v4);
  v10 = L"OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
  if ( !IsStateSeparationEnabled )
    v10 = L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v10, 0, 0x20019u, &hKey);
  v12 = v11;
  if ( !v11 )
  {
    v14 = 0;
    v35 = 0;
    cchName = 50;
    for ( i = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0); ; i = RegEnumKeyExW(
                                                                          hKey,
                                                                          v14,
                                                                          Name,
                                                                          &cchName,
                                                                          0,
                                                                          0,
                                                                          0,
                                                                          0) )
    {
      v12 = i;
      if ( i == 259 )
        goto LABEL_4;
      if ( i )
        break;
      phkResult = 0;
      v16 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
      v12 = v16;
      if ( v16 )
      {
        if ( v16 > 0 )
        {
          v12 = (unsigned __int16)v16;
          goto LABEL_82;
        }
LABEL_83:
        if ( phkResult )
          RegCloseKey(phkResult);
        goto LABEL_17;
      }
      v17 = 0;
      cchName = 260;
      v12 = RegEnumKeyExW(phkResult, 0, SubKey, &cchName, 0, 0, 0, 0);
      if ( v12 != 259 )
      {
        while ( !v12 )
        {
          v33 = 0;
          v18 = RegOpenKeyExW(phkResult, SubKey, 0, 0x20019u, &v33);
          v12 = v18;
          if ( v18 )
          {
            if ( v18 <= 0 )
              goto LABEL_76;
            v12 = (unsigned __int16)v18;
            goto LABEL_75;
          }
          v19 = 0;
          cchName = 260;
          v20 = 0;
LABEL_40:
          v12 = RegEnumKeyExW(v33, v20, v37, &cchName, 0, 0, 0, 0);
          if ( v12 != 259 )
          {
            if ( !v12 )
            {
              v34 = 0;
              v21 = RegOpenKeyExW(v33, v37, 0, 0x20019u, &v34);
              v12 = v21;
              if ( v21 )
              {
                if ( v21 > 0 )
                {
                  v12 = (unsigned __int16)v21;
                  goto LABEL_68;
                }
              }
              else
              {
                cchName = 10;
                cbData = 0;
                for ( j = 0; ; j = v3 )
                {
                  v12 = RegEnumValueW(v34, j, ValueName, &cchName, 0, 0, 0, &cbData);
                  if ( v12 == 259 )
                  {
                    cchName = 260;
                    ++v19;
                    v3 = 0;
                    if ( v34 )
                      RegCloseKey(v34);
                    v20 = v19;
                    goto LABEL_40;
                  }
                  if ( v12 )
                    break;
                  v23 = saturated_mul((unsigned __int64)cbData >> 1, 2u);
                  v24 = operator new[](v23);
                  memset_0(v24, 0, v23);
                  cchName = 10;
                  v25 = RegEnumValueW(v34, v3, ValueName, &cchName, 0, 0, (LPBYTE)v24, &cbData);
                  v12 = v25;
                  if ( v25 )
                  {
                    if ( v25 > 0 )
                      v12 = (unsigned __int16)v25 | 0x80070000;
                    operator delete(v24, v26);
                    goto LABEL_69;
                  }
                  if ( !(unsigned int)_o__wcsicmp(v24, bstrString) )
                  {
                    *a2 = 1;
                    operator delete(v24, v27);
                    if ( v34 )
                      RegCloseKey(v34);
                    if ( v33 )
                      RegCloseKey(v33);
                    if ( phkResult )
                      RegCloseKey(phkResult);
                    if ( bstrString )
                      SysFreeString(bstrString);
                    if ( hKey )
                      RegCloseKey(hKey);
                    return 0;
                  }
                  cchName = 260;
                  cbData = 0;
                  ++v3;
                  operator delete(v24, v27);
                }
                if ( v12 <= 0 )
                  goto LABEL_69;
                v12 = (unsigned __int16)v12;
LABEL_68:
                v12 |= 0x80070000;
              }
LABEL_69:
              if ( v34 )
                RegCloseKey(v34);
LABEL_76:
              if ( v33 )
                RegCloseKey(v33);
              goto LABEL_83;
            }
            if ( v12 <= 0 )
              goto LABEL_76;
            v12 = (unsigned __int16)v12;
LABEL_75:
            v12 |= 0x80070000;
            goto LABEL_76;
          }
          cchName = 260;
          ++v17;
          if ( v33 )
            RegCloseKey(v33);
          v12 = RegEnumKeyExW(phkResult, v17, SubKey, &cchName, 0, 0, 0, 0);
          if ( v12 == 259 )
          {
            v14 = v35;
            goto LABEL_45;
          }
        }
        if ( v12 <= 0 )
          goto LABEL_83;
        v12 = (unsigned __int16)v12;
LABEL_82:
        v12 |= 0x80070000;
        goto LABEL_83;
      }
LABEL_45:
      cchName = 50;
      v35 = ++v14;
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    if ( i <= 0 )
      goto LABEL_17;
    v13 = (unsigned __int16)i;
    goto LABEL_16;
  }
  if ( v11 > 0 )
  {
    v13 = (unsigned __int16)v11;
LABEL_16:
    v12 = v13 | 0x80070000;
  }
LABEL_17:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000f004  mov     [rsp-8+arg_10], rbx
0x18000f009  push    rbp
0x18000f00a  push    rsi
0x18000f00b  push    rdi
0x18000f00c  push    r12
0x18000f00e  push    r13
0x18000f010  push    r14
0x18000f012  push    r15
0x18000f014  lea     rbp, [rsp-240h]
0x18000f01c  sub     rsp, 340h
0x18000f023  mov     rax, cs:__security_cookie
0x18000f02a  xor     rax, rsp
0x18000f02d  mov     [rbp+270h+var_40], rax
0x18000f034  mov     r15, rdx
0x18000f037  xor     r14d, r14d
0x18000f03a  mov     [rsp+370h+hKey], r14
0x18000f03f  mov     [rsp+370h+cchName], 104h
0x18000f047  mov     [rsp+370h+cbData], r14d
0x18000f04c  test    rcx, rcx
0x18000f04f  jz      loc_18000F58F
0x18000f055  test    rdx, rdx
0x18000f058  jz      loc_18000F58F
0x18000f05e  mov     [rdx], r14d
0x18000f061  mov     [rsp+370h+bstrString], r14
0x18000f066  mov     rax, [rcx]
0x18000f069  lea     r9, [rsp+370h+bstrString]
0x18000f06e  xor     r8d, r8d
0x18000f071  xor     edx, edx
0x18000f073  mov     rax, [rax+40h]
0x18000f077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f07c  mov     r12d, eax
0x18000f07f  test    eax, eax
0x18000f081  jns     short loc_18000F0AC
0x18000f083  mov     rcx, [rsp+370h+bstrString]; bstrString
0x18000f088  test    rcx, rcx
0x18000f08b  jz      short loc_18000F094
0x18000f08d  call    cs:__imp_SysFreeString
0x18000f093  nop
0x18000f094  mov     rcx, [rsp+370h+hKey]; hKey
0x18000f099  test    rcx, rcx
0x18000f09c  jz      short loc_18000F0A4
0x18000f09e  call    cs:__imp_RegCloseKey
0x18000f0a4  mov     eax, r12d
0x18000f0a7  jmp     loc_18000F594
0x18000f0ac  mov     rdi, [rsp+370h+hKey]
0x18000f0b1  test    rdi, rdi
0x18000f0b4  jz      short loc_18000F0CF
0x18000f0b6  call    cs:__imp_GetLastError
0x18000f0bc  mov     ebx, eax
0x18000f0be  mov     rcx, rdi; hKey
0x18000f0c1  call    cs:__imp_RegCloseKey
0x18000f0c7  mov     ecx, ebx; dwErrCode
0x18000f0c9  call    cs:__imp_SetLastError
0x18000f0cf  mov     [rsp+370h+hKey], r14
0x18000f0d4  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000f0da  lea     rcx, aSoftwareMicros_4; "Software\\Microsoft\\EnterpriseResource"...
0x18000f0e1  lea     rdx, aOsdataSoftware_2; "OSData\\Software\\Microsoft\\Enterprise"...
0x18000f0e8  test    al, al
0x18000f0ea  cmovz   rdx, rcx; lpSubKey
0x18000f0ee  lea     rax, [rsp+370h+hKey]
0x18000f0f3  mov     [rsp+370h+phkResult], rax; phkResult
0x18000f0f8  mov     r9d, 20019h; samDesired
0x18000f0fe  xor     r8d, r8d; ulOptions
0x18000f101  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f108  call    cs:__imp_RegOpenKeyExW
0x18000f10e  mov     ebx, eax
0x18000f110  test    eax, eax
0x18000f112  jz      short loc_18000F147
0x18000f114  jle     short loc_18000F11F
0x18000f116  movzx   ebx, ax
0x18000f119  or      ebx, 80070000h
0x18000f11f  mov     rcx, [rsp+370h+bstrString]; bstrString
0x18000f124  test    rcx, rcx
0x18000f127  jz      short loc_18000F130
0x18000f129  call    cs:__imp_SysFreeString
0x18000f12f  nop
0x18000f130  mov     rcx, [rsp+370h+hKey]; hKey
0x18000f135  test    rcx, rcx
0x18000f138  jz      short loc_18000F140
0x18000f13a  call    cs:__imp_RegCloseKey
0x18000f140  mov     eax, ebx
0x18000f142  jmp     loc_18000F594
0x18000f147  mov     edi, r14d
0x18000f14a  mov     [rsp+370h+var_2F8], r14d
0x18000f14f  mov     [rsp+370h+cchName], 32h ; '2'
0x18000f157  mov     [rsp+370h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000f15c  mov     [rsp+370h+lpcchClass], r14; lpcchClass
0x18000f161  mov     [rsp+370h+lpClass], r14; lpClass
0x18000f166  mov     [rsp+370h+phkResult], r14; lpReserved
0x18000f16b  lea     r9, [rsp+370h+cchName]; lpcchName
0x18000f170  lea     r8, [rbp+270h+Name]; lpName
0x18000f174  xor     edx, edx; dwIndex
0x18000f176  mov     rcx, [rsp+370h+hKey]; hKey
0x18000f17b  call    cs:__imp_RegEnumKeyExW
0x18000f181  mov     esi, 103h
0x18000f186  jmp     loc_18000F482
0x18000f18b  test    ebx, ebx
0x18000f18d  jnz     loc_18000F581
0x18000f193  mov     [rsp+370h+var_310], r14
0x18000f198  lea     rax, [rsp+370h+var_310]
0x18000f19d  mov     [rsp+370h+phkResult], rax; phkResult
0x18000f1a2  mov     r9d, 20019h; samDesired
0x18000f1a8  xor     r8d, r8d; ulOptions
0x18000f1ab  lea     rdx, [rbp+270h+Name]; lpSubKey
0x18000f1af  mov     rcx, [rsp+370h+hKey]; hKey
0x18000f1b4  call    cs:__imp_RegOpenKeyExW
0x18000f1ba  mov     ebx, eax
0x18000f1bc  test    eax, eax
0x18000f1be  jnz     loc_18000F55D
0x18000f1c4  mov     r13d, r14d
0x18000f1c7  mov     [rsp+370h+cchName], 104h
0x18000f1cf  mov     [rsp+370h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000f1d4  mov     [rsp+370h+lpcchClass], r14; lpcchClass
0x18000f1d9  mov     [rsp+370h+lpClass], r14; lpClass
0x18000f1de  mov     [rsp+370h+phkResult], r14; lpReserved
0x18000f1e3  lea     r9, [rsp+370h+cchName]; lpcchName
0x18000f1e8  lea     r8, [rbp+270h+SubKey]; lpName
0x18000f1ec  xor     edx, edx; dwIndex
0x18000f1ee  mov     rcx, [rsp+370h+var_310]; hKey
0x18000f1f3  call    cs:__imp_RegEnumKeyExW
0x18000f1f9  mov     ebx, eax
0x18000f1fb  cmp     eax, esi
0x18000f1fd  jz      loc_18000F43A
0x18000f203  test    ebx, ebx
0x18000f205  jnz     loc_18000F556
0x18000f20b  mov     [rsp+370h+var_308], r14
0x18000f210  lea     rax, [rsp+370h+var_308]
0x18000f215  mov     [rsp+370h+phkResult], rax; phkResult
0x18000f21a  mov     r9d, 20019h; samDesired
0x18000f220  xor     r8d, r8d; ulOptions
0x18000f223  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x18000f227  mov     rcx, [rsp+370h+var_310]; hKey
0x18000f22c  call    cs:__imp_RegOpenKeyExW
0x18000f232  mov     ebx, eax
0x18000f234  test    eax, eax
0x18000f236  jnz     loc_18000F539
0x18000f23c  mov     esi, r14d
0x18000f23f  mov     [rsp+370h+cchName], 104h
0x18000f247  xor     edx, edx
0x18000f249  jmp     loc_18000F3AC
0x18000f24e  test    ebx, ebx
0x18000f250  jnz     loc_18000F532
0x18000f256  mov     [rsp+370h+var_300], r14
0x18000f25b  lea     rax, [rsp+370h+var_300]
0x18000f260  mov     [rsp+370h+phkResult], rax; phkResult
0x18000f265  mov     r9d, 20019h; samDesired
0x18000f26b  xor     r8d, r8d; ulOptions
0x18000f26e  lea     rdx, [rbp+270h+var_2D8]; lpSubKey
0x18000f272  mov     rcx, [rsp+370h+var_308]; hKey
0x18000f277  call    cs:__imp_RegOpenKeyExW
0x18000f27d  mov     ebx, eax
0x18000f27f  test    eax, eax
0x18000f281  jnz     loc_18000F515
0x18000f287  mov     [rsp+370h+cchName], 0Ah
0x18000f28f  xor     edi, edi
0x18000f291  mov     [rsp+370h+cbData], edi
0x18000f295  xor     edx, edx
0x18000f297  jmp     loc_18000F353
0x18000f29c  test    ebx, ebx
0x18000f29e  jnz     loc_18000F50E
0x18000f2a4  mov     ecx, [rsp+370h+cbData]
0x18000f2a8  shr     rcx, 1
0x18000f2ab  lea     eax, [rbx+2]
0x18000f2ae  mul     rcx
0x18000f2b1  mov     rbx, rax
0x18000f2b4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f2bb  cmovb   rbx, rax
0x18000f2bf  mov     rcx, rbx; unsigned __int64
0x18000f2c2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f2c7  mov     rdi, rax
0x18000f2ca  mov     r8, rbx; Size
0x18000f2cd  xor     edx, edx; Val
0x18000f2cf  mov     rcx, rax; void *
0x18000f2d2  call    memset_0
0x18000f2d7  mov     [rsp+370h+cchName], 0Ah
0x18000f2df  lea     rax, [rsp+370h+cbData]
0x18000f2e4  mov     [rsp+370h+lpftLastWriteTime], rax; lpcbData
0x18000f2e9  mov     [rsp+370h+lpcchClass], rdi; lpData
0x18000f2ee  mov     [rsp+370h+lpClass], 0; lpType
0x18000f2f7  mov     [rsp+370h+phkResult], 0; lpReserved
0x18000f300  lea     r9, [rsp+370h+cchName]; lpcchValueName
0x18000f305  lea     r8, [rbp+270h+ValueName]; lpValueName
0x18000f309  mov     edx, r14d; dwIndex
0x18000f30c  mov     rcx, [rsp+370h+var_300]; hKey
0x18000f311  call    cs:__imp_RegEnumValueW
0x18000f317  mov     ebx, eax
0x18000f319  test    eax, eax
0x18000f31b  jnz     loc_18000F4F9
0x18000f321  mov     rdx, [rsp+370h+bstrString]
0x18000f326  mov     rcx, rdi
0x18000f329  call    cs:__imp__o__wcsicmp
0x18000f32f  mov     rcx, rdi; void *
0x18000f332  test    eax, eax
0x18000f334  jz      loc_18000F491
0x18000f33a  mov     [rsp+370h+cchName], 104h
0x18000f342  mov     [rsp+370h+cbData], ebx
0x18000f346  inc     r14d
0x18000f349  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f34e  xor     edi, edi
0x18000f350  mov     edx, r14d; dwIndex
0x18000f353  lea     rax, [rsp+370h+cbData]
0x18000f358  mov     [rsp+370h+lpftLastWriteTime], rax; lpcbData
0x18000f35d  mov     [rsp+370h+lpcchClass], rdi; lpData
0x18000f362  mov     [rsp+370h+lpClass], rdi; lpType
0x18000f367  mov     [rsp+370h+phkResult], rdi; lpReserved
0x18000f36c  lea     r9, [rsp+370h+cchName]; lpcchValueName
0x18000f371  lea     r8, [rbp+270h+ValueName]; lpValueName
0x18000f375  mov     rcx, [rsp+370h+var_300]; hKey
0x18000f37a  call    cs:__imp_RegEnumValueW
0x18000f380  cmp     eax, 103h
0x18000f385  mov     ebx, eax
0x18000f387  jnz     loc_18000F29C
0x18000f38d  mov     [rsp+370h+cchName], 104h
0x18000f395  inc     esi
0x18000f397  mov     rcx, [rsp+370h+var_300]; hKey
0x18000f39c  xor     r14d, r14d
0x18000f39f  test    rcx, rcx
0x18000f3a2  jz      short loc_18000F3AA
0x18000f3a4  call    cs:__imp_RegCloseKey
0x18000f3aa  mov     edx, esi; dwIndex
0x18000f3ac  mov     [rsp+370h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000f3b1  mov     [rsp+370h+lpcchClass], r14; lpcchClass
0x18000f3b6  mov     [rsp+370h+lpClass], r14; lpClass
0x18000f3bb  mov     [rsp+370h+phkResult], r14; lpReserved
0x18000f3c0  lea     r9, [rsp+370h+cchName]; lpcchName
0x18000f3c5  lea     r8, [rbp+270h+var_2D8]; lpName
0x18000f3c9  mov     rcx, [rsp+370h+var_308]; hKey
0x18000f3ce  call    cs:__imp_RegEnumKeyExW
0x18000f3d4  cmp     eax, 103h
0x18000f3d9  mov     ebx, eax
0x18000f3db  jnz     loc_18000F24E
0x18000f3e1  mov     [rsp+370h+cchName], 104h
0x18000f3e9  inc     r13d
0x18000f3ec  mov     rcx, [rsp+370h+var_308]; hKey
0x18000f3f1  test    rcx, rcx
0x18000f3f4  jz      short loc_18000F3FC
0x18000f3f6  call    cs:__imp_RegCloseKey
0x18000f3fc  mov     [rsp+370h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000f401  mov     [rsp+370h+lpcchClass], r14; lpcchClass
0x18000f406  mov     [rsp+370h+lpClass], r14; lpClass
0x18000f40b  mov     [rsp+370h+phkResult], r14; lpReserved
0x18000f410  lea     r9, [rsp+370h+cchName]; lpcchName
0x18000f415  lea     r8, [rbp+270h+SubKey]; lpName
0x18000f419  mov     edx, r13d; dwIndex
0x18000f41c  mov     rcx, [rsp+370h+var_310]; hKey
0x18000f421  call    cs:__imp_RegEnumKeyExW
0x18000f427  mov     ebx, eax
0x18000f429  mov     esi, 103h
0x18000f42e  cmp     eax, esi
0x18000f430  jnz     loc_18000F203
0x18000f436  mov     edi, [rsp+370h+var_2F8]
0x18000f43a  mov     [rsp+370h+cchName], 32h ; '2'
0x18000f442  inc     edi
0x18000f444  mov     [rsp+370h+var_2F8], edi
0x18000f448  mov     rcx, [rsp+370h+var_310]; hKey
0x18000f44d  test    rcx, rcx
0x18000f450  jz      short loc_18000F458
0x18000f452  call    cs:__imp_RegCloseKey
0x18000f458  mov     [rsp+370h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000f45d  mov     [rsp+370h+lpcchClass], r14; lpcchClass
0x18000f462  mov     [rsp+370h+lpClass], r14; lpClass
0x18000f467  mov     [rsp+370h+phkResult], r14; lpReserved
0x18000f46c  lea     r9, [rsp+370h+cchName]; lpcchName
0x18000f471  lea     r8, [rbp+270h+Name]; lpName
0x18000f475  mov     edx, edi; dwIndex
0x18000f477  mov     rcx, [rsp+370h+hKey]; hKey
0x18000f47c  call    cs:__imp_RegEnumKeyExW
0x18000f482  cmp     eax, esi
0x18000f484  mov     ebx, eax
0x18000f486  jnz     loc_18000F18B
0x18000f48c  jmp     loc_18000F083
0x18000f491  mov     dword ptr [r15], 1
0x18000f498  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f49d  nop
0x18000f49e  mov     rcx, [rsp+370h+var_300]; hKey
0x18000f4a3  test    rcx, rcx
0x18000f4a6  jz      short loc_18000F4AF
0x18000f4a8  call    cs:__imp_RegCloseKey
0x18000f4ae  nop
0x18000f4af  mov     rcx, [rsp+370h+var_308]; hKey
0x18000f4b4  test    rcx, rcx
0x18000f4b7  jz      short loc_18000F4C0
0x18000f4b9  call    cs:__imp_RegCloseKey
0x18000f4bf  nop
0x18000f4c0  mov     rcx, [rsp+370h+var_310]; hKey
0x18000f4c5  test    rcx, rcx
0x18000f4c8  jz      short loc_18000F4D1
0x18000f4ca  call    cs:__imp_RegCloseKey
0x18000f4d0  nop
0x18000f4d1  mov     rcx, [rsp+370h+bstrString]; bstrString
0x18000f4d6  test    rcx, rcx
0x18000f4d9  jz      short loc_18000F4E2
0x18000f4db  call    cs:__imp_SysFreeString
0x18000f4e1  nop
0x18000f4e2  mov     rcx, [rsp+370h+hKey]; hKey
0x18000f4e7  test    rcx, rcx
0x18000f4ea  jz      short loc_18000F4F2
0x18000f4ec  call    cs:__imp_RegCloseKey
0x18000f4f2  xor     eax, eax
0x18000f4f4  jmp     loc_18000F594
  ... truncated ...
```
