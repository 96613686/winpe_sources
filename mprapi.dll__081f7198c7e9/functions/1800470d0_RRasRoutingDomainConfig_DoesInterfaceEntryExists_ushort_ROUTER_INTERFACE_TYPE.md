# RRasRoutingDomainConfig::DoesInterfaceEntryExists(ushort *,_ROUTER_INTERFACE_TYPE)

- ea: `0x1800470d0`
- end: `0x180047501`
- name: `?DoesInterfaceEntryExists@RRasRoutingDomainConfig@@AEAA_NPEAGW4_ROUTER_INTERFACE_TYPE@@@Z`
- size: `1073`
- prototype: `char __fastcall(RRasRoutingDomainConfig *this, wchar_t *String1, enum _ROUTER_INTERFACE_TYPE)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180045e68`

## callees

- `0x1800302d0`
- `0x1800470d0`
- `0x18004a364`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800473d6`
- `msvcrt!_wcsicmp` at `0x180047445`
- `msvcrt!_wcsicmp` at `0x1800473d6`
- `msvcrt!_wcsicmp` at `0x180047445`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047291`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800474c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800474d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047291`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800474c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800474d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004723f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004723f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800472c8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800472c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004734d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004734d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800473a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047414`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004747d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800473a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047414`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004747d`

## string_xrefs

- `0x1800471b8`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x1800472e9`: `System\CurrentControlSet\Services\RemoteAccess\Interfaces`
- `0x180047259`: `Error %d occured while enumerating subkeys under registry key %s. #1`
- `0x1800472f0`: `Error %d occured while enumerating subkeys under registry key %s. #2`
- `0x18004736b`: `Error %d occured while opening registry key %s.`
- `0x1800473c2`: `Error %d occured while querying value registry value name %s.`
- `0x1800471b1`: `Error %d occurred while opening interfaces key under registry key %s. #1`

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
  DWORD v10; // ebx
  unsigned int v11; // eax
  __int64 v12; // r8
  WCHAR *v13; // r9
  const wchar_t *v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  BYTE v24[4]; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueLen; // [rsp+80h] [rbp-80h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD cValues; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[56]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Data[40]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t String1a[40]; // [rsp+150h] [rbp+50h] BYREF
  int v32; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v33[2044]; // [rsp+1A4h] [rbp+A4h] BYREF
  wchar_t v34[257]; // [rsp+9A0h] [rbp+8A0h] BYREF
  __int16 v35; // [rsp+BA2h] [rbp+AA2h]

  phkResult = 0;
  cbMaxValueLen = 0;
  cbMaxValueNameLen = 0;
  cValues = 0;
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
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_35;
    v8 = L"Error %d occurred while opening interfaces key under registry key %s. #1";
    goto LABEL_4;
  }
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  v7 = v9;
  if ( v9 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_35;
    v8 = L"Error %d occured while enumerating subkeys under registry key %s. #1";
LABEL_4:
    LOWORD(v32) = 0;
    FormatRRASErrorString(&v32, v8, v7, L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces");
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
      gCfgStoreEtwContext,
      xmmword_180078C50,
      &v32);
    goto LABEL_35;
  }
  v10 = 0;
  if ( !cSubKeys )
    goto LABEL_35;
  while ( 1 )
  {
    memset_0(Data, 0, sizeof(Data));
    *(_DWORD *)v24 = 0;
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      phkResult = 0;
    }
    cchName = 50;
    v11 = RegEnumKeyExW(hKey, v10, Name, &cchName, 0, 0, 0, 0);
    v12 = v11;
    if ( !v11 || v11 == 234 )
      break;
    if ( (_QWORD)xmmword_180078C50 )
    {
      v13 = (WCHAR *)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Interfaces";
      v14 = L"Error %d occured while enumerating subkeys under registry key %s. #2";
LABEL_15:
      LOWORD(v32) = 0;
      FormatRRASErrorString(&v32, v14, v12, v13);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gCfgStoreTemplateFunc)(
        gCfgStoreEtwContext,
        xmmword_180078C50,
        &v32);
    }
LABEL_32:
    if ( ++v10 >= cSubKeys )
      goto LABEL_35;
  }
  v15 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
  v12 = v15;
  if ( v15 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_32;
    v13 = Name;
    v14 = L"Error %d occured while opening registry key %s.";
    goto LABEL_15;
  }
  cbData = 80;
  v16 = RegQueryValueExW(phkResult, L"RoutingDomainId", 0, 0, (LPBYTE)Data, &cbData);
  v12 = v16;
  if ( v16 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_32;
    v13 = (WCHAR *)L"RoutingDomainId";
    goto LABEL_22;
  }
  if ( _wcsicmp(String1a, Data) )
    goto LABEL_32;
  cbData = 514;
  v17 = RegQueryValueExW(phkResult, L"InterfaceName", 0, 0, (LPBYTE)v34, &cbData);
  v12 = v17;
  if ( v17 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_32;
    v13 = (WCHAR *)L"InterfaceName";
    goto LABEL_22;
  }
  v35 = 0;
  if ( _wcsicmp(String1, v34) )
    goto LABEL_32;
  cbData = 4;
  v18 = RegQueryValueExW(phkResult, L"Type", 0, 0, v24, &cbData);
  v12 = v18;
  if ( v18 )
  {
    if ( !(_QWORD)xmmword_180078C50 )
      goto LABEL_32;
    v13 = (WCHAR *)L"Type";
LABEL_22:
    v14 = L"Error %d occured while querying value registry value name %s.";
    goto LABEL_15;
  }
  if ( *(_DWORD *)v24 != 4 )
    goto LABEL_32;
  v5 = 1;
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
0x1800470d0  mov     [rsp-8+arg_10], rbx
0x1800470d5  mov     [rsp-8+arg_18], rsi
0x1800470da  push    rbp
0x1800470db  push    rdi
0x1800470dc  push    r14
0x1800470de  lea     rbp, [rsp-0AC0h]
0x1800470e6  sub     rsp, 0BC0h
0x1800470ed  mov     rax, cs:__security_cookie
0x1800470f4  xor     rax, rsp
0x1800470f7  mov     [rbp+0AD0h+var_20], rax
0x1800470fe  xor     r14d, r14d
0x180047101  mov     rsi, rdx
0x180047104  mov     rbx, rcx
0x180047107  mov     [rsp+0BD0h+phkResult], r14
0x18004710c  xor     edx, edx; Val
0x18004710e  mov     [rbp+0AD0h+cbMaxValueLen], r14d
0x180047112  lea     rcx, [rbp+0AD0h+Name]; void *
0x180047116  mov     [rbp+0AD0h+cbMaxValueNameLen], r14d
0x18004711a  lea     r8d, [r14+64h]; Size
0x18004711e  mov     [rbp+0AD0h+cValues], r14d
0x180047122  mov     [rsp+0BD0h+cSubKeys], r14d
0x180047127  call    memset_0
0x18004712c  xor     edx, edx; Val
0x18004712e  mov     [rsp+0BD0h+cchName], r14d
0x180047133  mov     r8d, 204h; Size
0x180047139  lea     rcx, [rbp+0AD0h+var_230]; void *
0x180047140  call    memset_0
0x180047145  xor     edx, edx; Val
0x180047147  mov     [rsp+0BD0h+cbData], r14d
0x18004714c  lea     r8d, [r14+50h]; Size
0x180047150  lea     rcx, [rbp+0AD0h+String1]; void *
0x180047154  call    memset_0
0x180047159  xor     edx, edx; Val
0x18004715b  mov     [rsp+0BD0h+hKey], r14
0x180047160  mov     r8d, 7FCh; Size
0x180047166  mov     [rbp+0AD0h+var_A30], r14d
0x18004716d  lea     rcx, [rbp+0AD0h+var_A2C]; void *
0x180047174  mov     dil, r14b
0x180047177  call    memset_0
0x18004717c  lea     rcx, [rbx+204h]
0x180047183  lea     r8, [rbp+0AD0h+String1]
0x180047187  lea     edx, [r14+28h]
0x18004718b  call    MprConvertGuidToString
0x180047190  lea     rdx, [rsp+0BD0h+hKey]; HKEY *
0x180047195  mov     rcx, rbx; this
0x180047198  call    ?OpenInterfacesKey@RRasRoutingDomainConfig@@QEAAKPEAPEAUHKEY__@@@Z; RRasRoutingDomainConfig::OpenInterfacesKey(HKEY__ * *)
0x18004719d  mov     r8d, eax
0x1800471a0  test    eax, eax
0x1800471a2  jz      short loc_1800471F9
0x1800471a4  cmp     qword ptr cs:xmmword_180078C50, r14
0x1800471ab  jz      loc_1800474B7
0x1800471b1  lea     rdx, aErrorDOccurred; "Error %d occurred while opening interfa"...
0x1800471b8  lea     r9, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Re"...
0x1800471bf  mov     word ptr [rbp+0AD0h+var_A30], r14w
0x1800471c7  lea     rcx, [rbp+0AD0h+var_A30]
0x1800471ce  call    FormatRRASErrorString
0x1800471d3  mov     rdx, qword ptr cs:xmmword_180078C50
0x1800471da  lea     r8, [rbp+0AD0h+var_A30]
0x1800471e1  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x1800471e8  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800471ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800471f4  jmp     loc_1800474B7
0x1800471f9  mov     rcx, [rsp+0BD0h+hKey]; hKey
0x1800471fe  lea     rax, [rbp+0AD0h+cbMaxValueLen]
0x180047202  mov     [rsp+0BD0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180047207  xor     r9d, r9d; lpReserved
0x18004720a  mov     [rsp+0BD0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18004720f  xor     r8d, r8d; lpcchClass
0x180047212  mov     [rsp+0BD0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180047217  xor     edx, edx; lpClass
0x180047219  lea     rax, [rbp+0AD0h+cbMaxValueNameLen]
0x18004721d  mov     [rsp+0BD0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180047222  lea     rax, [rbp+0AD0h+cValues]
0x180047226  mov     [rsp+0BD0h+lpcValues], rax; lpcValues
0x18004722b  lea     rax, [rsp+0BD0h+cSubKeys]
0x180047230  mov     [rsp+0BD0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180047235  mov     [rsp+0BD0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18004723a  mov     [rsp+0BD0h+lpcSubKeys], rax; lpcSubKeys
0x18004723f  call    cs:__imp_RegQueryInfoKeyW
0x180047245  mov     r8d, eax
0x180047248  test    eax, eax
0x18004724a  jz      short loc_180047265
0x18004724c  cmp     qword ptr cs:xmmword_180078C50, r14
0x180047253  jz      loc_1800474B7
0x180047259  lea     rdx, aErrorDOccuredW_3; "Error %d occured while enumerating subk"...
0x180047260  jmp     loc_1800471B8
0x180047265  mov     ebx, r14d
0x180047268  cmp     [rsp+0BD0h+cSubKeys], r14d
0x18004726d  jbe     loc_1800474B7
0x180047273  xor     edx, edx; Val
0x180047275  lea     rcx, [rbp+0AD0h+Data]; void *
0x180047279  lea     r8d, [rdx+50h]; Size
0x18004727d  call    memset_0
0x180047282  mov     rcx, [rsp+0BD0h+phkResult]; hKey
0x180047287  mov     dword ptr [rsp+0BD0h+var_B5C], r14d
0x18004728c  test    rcx, rcx
0x18004728f  jz      short loc_18004729C
0x180047291  call    cs:__imp_RegCloseKey
0x180047297  mov     [rsp+0BD0h+phkResult], r14
0x18004729c  mov     rcx, [rsp+0BD0h+hKey]; hKey
0x1800472a1  lea     r9, [rsp+0BD0h+cchName]; lpcchName
0x1800472a6  mov     [rsp+0BD0h+lpcValues], r14; lpftLastWriteTime
0x1800472ab  lea     r8, [rbp+0AD0h+Name]; lpName
0x1800472af  mov     [rsp+0BD0h+lpcbMaxClassLen], r14; lpcchClass
0x1800472b4  mov     edx, ebx; dwIndex
0x1800472b6  mov     [rsp+0BD0h+lpcbMaxSubKeyLen], r14; lpClass
0x1800472bb  mov     [rsp+0BD0h+lpcSubKeys], r14; lpReserved
0x1800472c0  mov     [rsp+0BD0h+cchName], 32h ; '2'
0x1800472c8  call    cs:__imp_RegEnumKeyExW
0x1800472ce  mov     r8d, eax
0x1800472d1  test    eax, eax
0x1800472d3  jz      short loc_180047331
0x1800472d5  cmp     eax, 0EAh
0x1800472da  jz      short loc_180047331
0x1800472dc  cmp     qword ptr cs:xmmword_180078C50, r14
0x1800472e3  jz      loc_1800474A6
0x1800472e9  lea     r9, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Re"...
0x1800472f0  lea     rdx, aErrorDOccuredW_2; "Error %d occured while enumerating subk"...
0x1800472f7  lea     rcx, [rbp+0AD0h+var_A30]
0x1800472fe  mov     word ptr [rbp+0AD0h+var_A30], r14w
0x180047306  call    FormatRRASErrorString
0x18004730b  mov     rdx, qword ptr cs:xmmword_180078C50
0x180047312  lea     r8, [rbp+0AD0h+var_A30]
0x180047319  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180047320  mov     rax, cs:?gCfgStoreTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gCfgStoreTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180047327  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004732c  jmp     loc_1800474A6
0x180047331  mov     rcx, [rsp+0BD0h+hKey]; hKey
0x180047336  lea     rax, [rsp+0BD0h+phkResult]
0x18004733b  mov     r9d, 20019h; samDesired
0x180047341  mov     [rsp+0BD0h+lpcSubKeys], rax; phkResult
0x180047346  xor     r8d, r8d; ulOptions
0x180047349  lea     rdx, [rbp+0AD0h+Name]; lpSubKey
0x18004734d  call    cs:__imp_RegOpenKeyExW
0x180047353  mov     r8d, eax
0x180047356  test    eax, eax
0x180047358  jz      short loc_180047374
0x18004735a  cmp     qword ptr cs:xmmword_180078C50, r14
0x180047361  jz      loc_1800474A6
0x180047367  lea     r9, [rbp+0AD0h+Name]
0x18004736b  lea     rdx, aErrorDOccuredW; "Error %d occured while opening registry"...
0x180047372  jmp     short loc_1800472F7
0x180047374  mov     rcx, [rsp+0BD0h+phkResult]; hKey
0x180047379  lea     rax, [rsp+0BD0h+cbData]
0x18004737e  mov     [rsp+0BD0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180047383  lea     rdx, aRoutingdomaini; "RoutingDomainId"
0x18004738a  lea     rax, [rbp+0AD0h+Data]
0x18004738e  mov     [rsp+0BD0h+cbData], 50h ; 'P'
0x180047396  xor     r9d, r9d; lpType
0x180047399  mov     [rsp+0BD0h+lpcSubKeys], rax; lpData
0x18004739e  xor     r8d, r8d; lpReserved
0x1800473a1  call    cs:__imp_RegQueryValueExW
0x1800473a7  mov     r8d, eax
0x1800473aa  test    eax, eax
0x1800473ac  jz      short loc_1800473CE
0x1800473ae  cmp     qword ptr cs:xmmword_180078C50, r14
0x1800473b5  jz      loc_1800474A6
0x1800473bb  lea     r9, aRoutingdomaini; "RoutingDomainId"
0x1800473c2  lea     rdx, aErrorDOccuredW_4; "Error %d occured while querying value r"...
0x1800473c9  jmp     loc_1800472F7
0x1800473ce  lea     rdx, [rbp+0AD0h+Data]; String2
0x1800473d2  lea     rcx, [rbp+0AD0h+String1]; String1
0x1800473d6  call    cs:__imp__wcsicmp
0x1800473dc  test    eax, eax
0x1800473de  jnz     loc_1800474A6
0x1800473e4  mov     rcx, [rsp+0BD0h+phkResult]; hKey
0x1800473e9  lea     rax, [rsp+0BD0h+cbData]
0x1800473ee  mov     [rsp+0BD0h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800473f3  lea     rdx, aInterfacename; "InterfaceName"
0x1800473fa  lea     rax, [rbp+0AD0h+var_230]
0x180047401  mov     [rsp+0BD0h+cbData], 202h
0x180047409  xor     r9d, r9d; lpType
0x18004740c  mov     [rsp+0BD0h+lpcSubKeys], rax; lpData
0x180047411  xor     r8d, r8d; lpReserved
0x180047414  call    cs:__imp_RegQueryValueExW
0x18004741a  mov     r8d, eax
0x18004741d  test    eax, eax
0x18004741f  jz      short loc_180047433
0x180047421  cmp     qword ptr cs:xmmword_180078C50, r14
0x180047428  jz      short loc_1800474A6
0x18004742a  lea     r9, aInterfacename; "InterfaceName"
0x180047431  jmp     short loc_1800473C2
0x180047433  lea     rdx, [rbp+0AD0h+var_230]; String2
0x18004743a  mov     [rbp+0AD0h+var_2E], r14w
0x180047442  mov     rcx, rsi; String1
0x180047445  call    cs:__imp__wcsicmp
0x18004744b  test    eax, eax
0x18004744d  jnz     short loc_1800474A6
0x18004744f  mov     rcx, [rsp+0BD0h+phkResult]; hKey
0x180047454  lea     rax, [rsp+0BD0h+cbData]
0x180047459  mov     [rsp+0BD0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18004745e  lea     rdx, aType; "Type"
0x180047465  lea     rax, [rsp+0BD0h+var_B5C]
0x18004746a  mov     [rsp+0BD0h+cbData], 4
0x180047472  xor     r9d, r9d; lpType
0x180047475  mov     [rsp+0BD0h+lpcSubKeys], rax; lpData
0x18004747a  xor     r8d, r8d; lpReserved
0x18004747d  call    cs:__imp_RegQueryValueExW
0x180047483  mov     r8d, eax
0x180047486  test    eax, eax
0x180047488  jz      short loc_18004749F
0x18004748a  cmp     qword ptr cs:xmmword_180078C50, r14
0x180047491  jz      short loc_1800474A6
0x180047493  lea     r9, aType; "Type"
0x18004749a  jmp     loc_1800473C2
0x18004749f  cmp     dword ptr [rsp+0BD0h+var_B5C], 4
0x1800474a4  jz      short loc_1800474B4
0x1800474a6  inc     ebx
0x1800474a8  cmp     ebx, [rsp+0BD0h+cSubKeys]
0x1800474ac  jb      loc_180047273
0x1800474b2  jmp     short loc_1800474B7
0x1800474b4  mov     dil, 1
0x1800474b7  mov     rcx, [rsp+0BD0h+phkResult]; hKey
0x1800474bc  test    rcx, rcx
0x1800474bf  jz      short loc_1800474C7
0x1800474c1  call    cs:__imp_RegCloseKey
0x1800474c7  mov     rcx, [rsp+0BD0h+hKey]; hKey
0x1800474cc  test    rcx, rcx
0x1800474cf  jz      short loc_1800474D7
0x1800474d1  call    cs:__imp_RegCloseKey
0x1800474d7  mov     al, dil
0x1800474da  mov     rcx, [rbp+0AD0h+var_20]
0x1800474e1  xor     rcx, rsp; StackCookie
0x1800474e4  call    __security_check_cookie
0x1800474e9  lea     r11, [rsp+0BD0h+var_10]
0x1800474f1  mov     rbx, [r11+30h]
0x1800474f5  mov     rsi, [r11+38h]
0x1800474f9  mov     rsp, r11
0x1800474fc  pop     r14
0x1800474fe  pop     rdi
0x1800474ff  pop     rbp
0x180047500  retn
```
