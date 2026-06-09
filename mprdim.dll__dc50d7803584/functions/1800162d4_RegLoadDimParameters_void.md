# RegLoadDimParameters(void)

- ea: `0x1800162d4`
- end: `0x1800165c4`
- name: `?RegLoadDimParameters@@YAKXZ`
- size: `752`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011eb0`

## callees

- `0x18000def0`
- `0x1800162d4`
- `0x180030164`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `rtutils!RouterLogEventW` at `0x1800163e8`
- `rtutils!RouterLogEventW` at `0x1800164f4`
- `rtutils!RouterLogEventW` at `0x180016583`
- `rtutils!RouterLogEventW` at `0x1800163e8`
- `rtutils!RouterLogEventW` at `0x1800164f4`
- `rtutils!RouterLogEventW` at `0x180016583`
- `ADVAPI32!RegOpenKeyExW` at `0x18001635b`
- `ADVAPI32!RegOpenKeyExW` at `0x18001635b`
- `ADVAPI32!RegCloseKey` at `0x18001658e`
- `ADVAPI32!RegCloseKey` at `0x18001658e`
- `ADVAPI32!RegQueryValueExW` at `0x18001643a`
- `ADVAPI32!RegQueryValueExW` at `0x18001643a`

## string_xrefs

- `0x180016342`: `System\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18001637f`: `Error %d occured while opening registry key %s.`
- `0x180016521`: `Error %d occured while querying registry value %ws.`

## pseudocode

```c
__int64 RegLoadDimParameters(void)
{
  unsigned int v0; // eax
  DWORD dwErrorCode; // edi
  unsigned int i; // r14d
  __int64 v3; // rsi
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  unsigned int *v6; // r8
  unsigned int v7; // ecx
  CDimSqm *v8; // rcx
  BYTE *phkResult; // [rsp+20h] [rbp-E0h]
  LPWSTR plpszSubStringArray; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v16[2044]; // [rsp+54h] [rbp-ACh] BYREF

  hKey = 0;
  v15 = 0;
  cbData = 0;
  Type = 0;
  plpszSubStringArray = 0;
  memset_0(v16, 0, sizeof(v16));
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
         0,
         0x20019u,
         &hKey);
  dwErrorCode = v0;
  if ( v0 )
  {
    plpszSubStringArray = (LPWSTR)L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters";
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
    {
      LOWORD(v15) = 0;
      FormatRRASErrorString(
        &v15,
        L"Error %d occured while opening registry key %s.",
        v0,
        L"System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters");
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceAdminError, &v15);
    }
    if ( dword_180070F40 )
      RouterLogEventW(hLogHandle, 1u, 0x4E84u, 1u, &plpszSubStringArray, dwErrorCode);
    return dwErrorCode;
  }
  for ( i = 0; ; ++i )
  {
    v3 = 32LL * i;
    v4 = *(const WCHAR **)((char *)&DIMRegParams + v3);
    if ( !v4 )
      break;
    phkResult = *(BYTE **)((char *)&DIMRegParams + v3 + 8);
    cbData = 4;
    v5 = RegQueryValueExW(hKey, v4, 0, &Type, phkResult, &cbData);
    dwErrorCode = v5;
    if ( v5 )
    {
      if ( v5 != 2 )
      {
        plpszSubStringArray = *(LPWSTR *)((char *)&DIMRegParams + v3);
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          LOWORD(v15) = 0;
          FormatRRASErrorString(&v15, L"Error %d occured while querying registry value %ws.", v5);
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceAdminError, &v15);
        }
        if ( dword_180070F40 )
          RouterLogEventW(hLogHandle, 1u, 0x4E83u, 1u, &plpszSubStringArray, dwErrorCode);
        break;
      }
      dwErrorCode = 0;
      goto LABEL_20;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
    {
      v6 = *(unsigned int **)((char *)&DIMRegParams + v3 + 8);
      LOWORD(v15) = 0;
      FormatRRASErrorString(&v15, L"RouterType Value is %d", *v6);
      if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v15);
    }
    if ( Type == 4 )
    {
      v7 = **(_DWORD **)((char *)&DIMRegParams + v3 + 8);
      if ( v7 <= *(_DWORD *)((char *)&DIMRegParams + v3 + 24) && v7 >= *(_DWORD *)((char *)&DIMRegParams + v3 + 20) )
        continue;
    }
    plpszSubStringArray = *(LPWSTR *)((char *)&DIMRegParams + v3);
    if ( (unsigned int)dword_180070F40 > 1 )
      RouterLogEventW(hLogHandle, 2u, 0x4E85u, 1u, &plpszSubStringArray, 0);
LABEL_20:
    **(_DWORD **)((char *)&DIMRegParams + v3 + 8) = *(_DWORD *)((char *)&DIMRegParams + v3 + 16);
    continue;
  }
  RegCloseKey(hKey);
  if ( !dwErrorCode )
    CDimSqm::UpdateTelemetry(v8, gblDIMConfigInfo);
  return dwErrorCode;
}

```

## disassembly

```asm
0x1800162d4  push    rbp
0x1800162d6  push    rbx
0x1800162d7  push    rsi
0x1800162d8  push    rdi
0x1800162d9  push    r12
0x1800162db  push    r14
0x1800162dd  lea     rbp, [rsp-768h]
0x1800162e5  sub     rsp, 868h
0x1800162ec  mov     rax, cs:__security_cookie
0x1800162f3  xor     rax, rsp
0x1800162f6  mov     [rbp+790h+var_40], rax
0x1800162fd  xor     eax, eax
0x1800162ff  mov     [rsp+890h+hKey], 0
0x180016308  xor     edx, edx; Val
0x18001630a  mov     [rsp+890h+var_840], eax
0x18001630e  mov     r8d, 7FCh; Size
0x180016314  mov     [rsp+890h+cbData], 0
0x18001631c  lea     rcx, [rsp+890h+var_83C]; void *
0x180016321  mov     [rsp+890h+Type], 0
0x180016329  mov     [rsp+890h+plpszSubStringArray], 0
0x180016332  call    memset_0
0x180016337  lea     rax, [rsp+890h+hKey]
0x18001633c  mov     r9d, 20019h; samDesired
0x180016342  lea     rsi, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Re"...
0x180016349  mov     [rsp+890h+phkResult], rax; phkResult
0x18001634e  mov     rdx, rsi; lpSubKey
0x180016351  xor     r8d, r8d; ulOptions
0x180016354  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001635b  call    cs:__imp_RegOpenKeyExW
0x180016361  mov     edi, eax
0x180016363  mov     ebx, 1
0x180016368  test    eax, eax
0x18001636a  jz      loc_1800163F3
0x180016370  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180016376  mov     [rsp+890h+plpszSubStringArray], rsi
0x18001637b  jz      short loc_1800163BB
0x18001637d  xor     ecx, ecx
0x18001637f  lea     rdx, aErrorDOccuredW; "Error %d occured while opening registry"...
0x180016386  mov     word ptr [rsp+890h+var_840], cx
0x18001638b  mov     r9, rsi
0x18001638e  lea     rcx, [rsp+890h+var_840]
0x180016393  mov     r8d, eax
0x180016396  call    FormatRRASErrorString
0x18001639b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x1800163a1  jz      short loc_1800163BB
0x1800163a3  lea     r8, [rsp+890h+var_840]
0x1800163a8  lea     rdx, RasDimTraceAdminError
0x1800163af  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800163b6  call    McTemplateU0z_EventWriteTransfer
0x1800163bb  cmp     cs:dword_180070F40, 0
0x1800163c2  jbe     loc_1800165A3
0x1800163c8  mov     rcx, cs:hLogHandle; hLogHandle
0x1800163cf  lea     rax, [rsp+890h+plpszSubStringArray]
0x1800163d4  mov     [rsp+890h+dwErrorCode], edi; dwErrorCode
0x1800163d8  mov     r9d, ebx; dwSubStringCount
0x1800163db  mov     r8d, 4E84h; dwMessageId
0x1800163e1  mov     [rsp+890h+phkResult], rax; plpszSubStringArray
0x1800163e6  mov     edx, ebx; dwEventType
0x1800163e8  call    cs:__imp_RouterLogEventW
0x1800163ee  jmp     loc_1800165A3
0x1800163f3  xor     r14d, r14d
0x1800163f6  lea     r12, ?DIMRegParams@@3PAU_DIM_REGISTRY_PARAMS@@A; _DIM_REGISTRY_PARAMS near * DIMRegParams
0x1800163fd  mov     esi, r14d
0x180016400  shl     rsi, 5
0x180016404  mov     rdx, [rsi+r12]; lpValueName
0x180016408  test    rdx, rdx
0x18001640b  jz      loc_180016589
0x180016411  mov     rcx, [rsp+890h+hKey]; hKey
0x180016416  lea     rax, [rsp+890h+cbData]
0x18001641b  mov     qword ptr [rsp+890h+dwErrorCode], rax; lpcbData
0x180016420  lea     r9, [rsp+890h+Type]; lpType
0x180016425  mov     rax, [rsi+r12+8]
0x18001642a  xor     r8d, r8d; lpReserved
0x18001642d  mov     [rsp+890h+phkResult], rax; lpData
0x180016432  mov     [rsp+890h+cbData], 4
0x18001643a  call    cs:__imp_RegQueryValueExW
0x180016440  mov     edi, eax
0x180016442  test    eax, eax
0x180016444  jz      short loc_180016456
0x180016446  cmp     eax, 2
0x180016449  jnz     loc_18001650E
0x18001644f  xor     edi, edi
0x180016451  jmp     loc_1800164FA
0x180016456  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x18001645d  jz      short loc_1800164A0
0x18001645f  mov     r8, [rsi+r12+8]
0x180016464  lea     rdx, aRoutertypeValu; "RouterType Value is %d"
0x18001646b  xor     eax, eax
0x18001646d  lea     rcx, [rsp+890h+var_840]
0x180016472  mov     word ptr [rsp+890h+var_840], ax
0x180016477  mov     r8d, [r8]
0x18001647a  call    FormatRRASErrorString
0x18001647f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180016486  jz      short loc_1800164A0
0x180016488  lea     r8, [rsp+890h+var_840]
0x18001648d  lea     rdx, RasDimTraceInfo
0x180016494  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001649b  call    McTemplateU0z_EventWriteTransfer
0x1800164a0  cmp     [rsp+890h+Type], 4
0x1800164a5  jnz     short loc_1800164BC
0x1800164a7  mov     rax, [rsi+r12+8]
0x1800164ac  mov     ecx, [rax]
0x1800164ae  cmp     ecx, [rsi+r12+18h]
0x1800164b3  ja      short loc_1800164BC
0x1800164b5  cmp     ecx, [rsi+r12+14h]
0x1800164ba  jnb     short loc_180016506
0x1800164bc  cmp     cs:dword_180070F40, ebx
0x1800164c2  mov     rax, [rsi+r12]
0x1800164c6  mov     [rsp+890h+plpszSubStringArray], rax
0x1800164cb  jbe     short loc_1800164FA
0x1800164cd  mov     rcx, cs:hLogHandle; hLogHandle
0x1800164d4  lea     rax, [rsp+890h+plpszSubStringArray]
0x1800164d9  mov     [rsp+890h+dwErrorCode], 0; dwErrorCode
0x1800164e1  mov     r9d, ebx; dwSubStringCount
0x1800164e4  mov     edx, 2; dwEventType
0x1800164e9  mov     [rsp+890h+phkResult], rax; plpszSubStringArray
0x1800164ee  mov     r8d, 4E85h; dwMessageId
0x1800164f4  call    cs:__imp_RouterLogEventW
0x1800164fa  mov     rcx, [rsi+r12+8]
0x1800164ff  mov     eax, [rsi+r12+10h]
0x180016504  mov     [rcx], eax
0x180016506  add     r14d, ebx
0x180016509  jmp     loc_1800163FD
0x18001650e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180016514  mov     r9, [rsi+r12]
0x180016518  mov     [rsp+890h+plpszSubStringArray], r9
0x18001651d  jz      short loc_18001655A
0x18001651f  xor     eax, eax
0x180016521  lea     rdx, aErrorDOccuredW_6; "Error %d occured while querying registr"...
0x180016528  mov     r8d, edi
0x18001652b  mov     word ptr [rsp+890h+var_840], ax
0x180016530  lea     rcx, [rsp+890h+var_840]
0x180016535  call    FormatRRASErrorString
0x18001653a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180016540  jz      short loc_18001655A
0x180016542  lea     r8, [rsp+890h+var_840]
0x180016547  lea     rdx, RasDimTraceAdminError
0x18001654e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016555  call    McTemplateU0z_EventWriteTransfer
0x18001655a  cmp     cs:dword_180070F40, 0
0x180016561  jbe     short loc_180016589
0x180016563  mov     rcx, cs:hLogHandle; hLogHandle
0x18001656a  lea     rax, [rsp+890h+plpszSubStringArray]
0x18001656f  mov     [rsp+890h+dwErrorCode], edi; dwErrorCode
0x180016573  mov     r9d, ebx; dwSubStringCount
0x180016576  mov     r8d, 4E83h; dwMessageId
0x18001657c  mov     [rsp+890h+phkResult], rax; plpszSubStringArray
0x180016581  mov     edx, ebx; dwEventType
0x180016583  call    cs:__imp_RouterLogEventW
0x180016589  mov     rcx, [rsp+890h+hKey]; hKey
0x18001658e  call    cs:__imp_RegCloseKey
0x180016594  test    edi, edi
0x180016596  jnz     short loc_1800165A3
0x180016598  mov     edx, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; unsigned int
0x18001659e  call    ?UpdateTelemetry@CDimSqm@@QEAAXK@Z; CDimSqm::UpdateTelemetry(ulong)
0x1800165a3  mov     eax, edi
0x1800165a5  mov     rcx, [rbp+790h+var_40]
0x1800165ac  xor     rcx, rsp; StackCookie
0x1800165af  call    __security_check_cookie
0x1800165b4  add     rsp, 868h
0x1800165bb  pop     r14
0x1800165bd  pop     r12
0x1800165bf  pop     rdi
0x1800165c0  pop     rsi
0x1800165c1  pop     rbx
0x1800165c2  pop     rbp
0x1800165c3  retn
```
