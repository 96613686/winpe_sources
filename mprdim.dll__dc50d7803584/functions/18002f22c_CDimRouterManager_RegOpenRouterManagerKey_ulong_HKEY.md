# CDimRouterManager::RegOpenRouterManagerKey(ulong,HKEY__ * &)

- ea: `0x18002f22c`
- end: `0x18002f598`
- name: `?RegOpenRouterManagerKey@CDimRouterManager@@SAKKAEAPEAUHKEY__@@@Z`
- size: `876`
- prototype: `static unsigned int(unsigned int, HKEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017400`

## callees

- `0x18000def0`
- `0x18002f140`
- `0x18002f22c`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002f387`
- `msvcrt!_wcsicmp` at `0x18002f387`
- `rtutils!RouterLogEventW` at `0x18002f2d9`
- `rtutils!RouterLogEventW` at `0x18002f44f`
- `rtutils!RouterLogEventW` at `0x18002f4a0`
- `rtutils!RouterLogEventW` at `0x18002f4f3`
- `rtutils!RouterLogEventW` at `0x18002f2d9`
- `rtutils!RouterLogEventW` at `0x18002f44f`
- `rtutils!RouterLogEventW` at `0x18002f4a0`
- `rtutils!RouterLogEventW` at `0x18002f4f3`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f3a9`
- `ADVAPI32!RegOpenKeyExW` at `0x18002f3a9`
- `ADVAPI32!RegCloseKey` at `0x18002f3f9`
- `ADVAPI32!RegCloseKey` at `0x18002f54d`
- `ADVAPI32!RegCloseKey` at `0x18002f55f`
- `ADVAPI32!RegCloseKey` at `0x18002f3f9`
- `ADVAPI32!RegCloseKey` at `0x18002f54d`
- `ADVAPI32!RegCloseKey` at `0x18002f55f`
- `ADVAPI32!RegQueryValueExW` at `0x18002f3db`
- `ADVAPI32!RegQueryValueExW` at `0x18002f3db`
- `ADVAPI32!RegEnumKeyExW` at `0x18002f35c`
- `ADVAPI32!RegEnumKeyExW` at `0x18002f35c`

## string_xrefs

- `0x18002f2f8`: `ProtocolId`
- `0x18002f2ab`: `System\CurrentControlSet\Services\RemoteAccess\RouterManagers`
- `0x18002f421`: `System\CurrentControlSet\Services\RemoteAccess\RouterManagers`
- `0x18002f506`: `Cannot access the Registry key %ws.`
- `0x18002f466`: `Cannot enumerate keys of Registry key %ws.`
- `0x18002f4b7`: `Cannot access the Registry value for %ws.`

## pseudocode

```c
__int64 __fastcall CDimRouterManager::RegOpenRouterManagerKey(int a1, HKEY *a2)
{
  unsigned int dwErrorCode; // edi
  LPWSTR *p_plpszSubStringArray; // r8
  DWORD i; // r14d
  LSTATUS v7; // eax
  LSTATUS Value; // eax
  const wchar_t *v9; // rdx
  LPWSTR v11; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v12; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData[3]; // [rsp+64h] [rbp-9Ch] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  int v19; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v20[2044]; // [rsp+284h] [rbp+184h] BYREF

  v12 = 0;
  hKey = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  *a2 = 0;
  dwErrorCode = CDimRouterManager::RegOpenRouterManagerKey(&hKey, &v12);
  if ( dwErrorCode )
  {
    plpszSubStringArray = (LPWSTR)L"System\\CurrentControlSet\\Services\\RemoteAccess\\RouterManagers";
    if ( dword_180070F40 )
      RouterLogEventW(hLogHandle, 1u, 0x4E84u, 1u, &plpszSubStringArray, dwErrorCode);
    if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
    {
      p_plpszSubStringArray = &plpszSubStringArray;
LABEL_30:
      v9 = L"Cannot access the Registry key %ws.";
LABEL_31:
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, v9, p_plpszSubStringArray);
      if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceAdminError, &v19);
    }
  }
  else
  {
    for ( i = 0; i < v12; ++i )
    {
      memset_0(Name, 0, 0x202u);
      cchName = 257;
      *(_DWORD *)Data = 0;
      cbData[0] = 4;
      LODWORD(plpszSubStringArray) = 0;
      v7 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      dwErrorCode = v7;
      if ( v7 && v7 != 234 )
      {
        if ( v7 == 259 )
        {
          dwErrorCode = 0;
          break;
        }
        v11 = (LPWSTR)L"System\\CurrentControlSet\\Services\\RemoteAccess\\RouterManagers";
        if ( dword_180070F40 )
          RouterLogEventW(hLogHandle, 1u, 0x4E86u, 1u, &v11, v7);
        if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
        {
          p_plpszSubStringArray = &v11;
          v9 = L"Cannot enumerate keys of Registry key %ws.";
          goto LABEL_31;
        }
        break;
      }
      Name[256] = 0;
      if ( _wcsicmp(Name, L"IKEv2CustomPolicy") )
      {
        dwErrorCode = RegOpenKeyExW(hKey, Name, 0, 0x2001Fu, a2);
        if ( dwErrorCode )
        {
          v11 = Name;
          if ( dword_180070F40 )
            RouterLogEventW(hLogHandle, 1u, 0x4E84u, 1u, &v11, dwErrorCode);
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            p_plpszSubStringArray = &v11;
            goto LABEL_30;
          }
          break;
        }
        Value = RegQueryValueExW(*a2, L"ProtocolId", 0, (LPDWORD)&plpszSubStringArray, Data, cbData);
        dwErrorCode = Value;
        if ( Value )
        {
          v11 = (LPWSTR)L"ProtocolId";
          if ( dword_180070F40 )
            RouterLogEventW(hLogHandle, 1u, 0x4E83u, 1u, &v11, Value);
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            p_plpszSubStringArray = &v11;
            v9 = L"Cannot access the Registry value for %ws.";
            goto LABEL_31;
          }
          break;
        }
        if ( *(_DWORD *)Data == a1 )
          break;
        RegCloseKey(*a2);
        *a2 = 0;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( dwErrorCode && *a2 )
  {
    RegCloseKey(*a2);
    *a2 = 0;
  }
  if ( !*a2 )
    return 902;
  return dwErrorCode;
}

```

## disassembly

```asm
0x18002f22c  push    rbp
0x18002f22e  push    rbx
0x18002f22f  push    rsi
0x18002f230  push    rdi
0x18002f231  push    r12
0x18002f233  push    r13
0x18002f235  push    r14
0x18002f237  push    r15
0x18002f239  lea     rbp, [rsp-998h]
0x18002f241  sub     rsp, 0A98h
0x18002f248  mov     rax, cs:__security_cookie
0x18002f24f  xor     rax, rsp
0x18002f252  mov     [rbp+9D0h+var_50], rax
0x18002f259  xor     r12d, r12d
0x18002f25c  mov     rsi, rdx
0x18002f25f  mov     r15d, ecx
0x18002f262  mov     [rsp+0AD0h+var_A88], r12d
0x18002f267  xor     edx, edx; Val
0x18002f269  mov     [rsp+0AD0h+hKey], r12
0x18002f26e  lea     rcx, [rbp+9D0h+var_84C]; void *
0x18002f275  mov     [rbp+9D0h+var_850], r12d
0x18002f27c  mov     r8d, 7FCh; Size
0x18002f282  call    memset_0
0x18002f287  lea     rdx, [rsp+0AD0h+var_A88]; unsigned int *
0x18002f28c  mov     [rsi], r12
0x18002f28f  lea     rcx, [rsp+0AD0h+hKey]; HKEY *
0x18002f294  call    ?RegOpenRouterManagerKey@CDimRouterManager@@CAKAEAPEAUHKEY__@@AEAK@Z; CDimRouterManager::RegOpenRouterManagerKey(HKEY__ * &,ulong &)
0x18002f299  lea     ebx, [r12+1]
0x18002f29e  mov     edi, eax
0x18002f2a0  test    eax, eax
0x18002f2a2  jz      short loc_18002F2F5
0x18002f2a4  cmp     cs:dword_180070F40, r12d
0x18002f2ab  lea     rax, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Re"...
0x18002f2b2  mov     [rsp+0AD0h+var_A80], rax
0x18002f2b7  jbe     short loc_18002F2DF
0x18002f2b9  mov     rcx, cs:hLogHandle; hLogHandle
0x18002f2c0  lea     rax, [rsp+0AD0h+var_A80]
0x18002f2c5  mov     [rsp+0AD0h+dwErrorCode], edi; dwErrorCode
0x18002f2c9  mov     r9d, ebx; dwSubStringCount
0x18002f2cc  mov     r8d, 4E84h; dwMessageId
0x18002f2d2  mov     [rsp+0AD0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002f2d7  mov     edx, ebx; dwEventType
0x18002f2d9  call    cs:__imp_RouterLogEventW
0x18002f2df  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18002f2e5  jz      loc_18002F543
0x18002f2eb  lea     r8, [rsp+0AD0h+var_A80]
0x18002f2f0  jmp     loc_18002F506
0x18002f2f5  mov     r14d, r12d
0x18002f2f8  lea     r13, aProtocolid; "ProtocolId"
0x18002f2ff  cmp     r14d, [rsp+0AD0h+var_A88]
0x18002f304  jnb     loc_18002F543
0x18002f30a  xor     edx, edx; Val
0x18002f30c  lea     rcx, [rsp+0AD0h+Name]; void *
0x18002f311  mov     r8d, 202h; Size
0x18002f317  call    memset_0
0x18002f31c  mov     rcx, [rsp+0AD0h+hKey]; hKey
0x18002f321  lea     r9, [rsp+0AD0h+cchName]; lpcchName
0x18002f326  mov     [rsp+0AD0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18002f32b  lea     r8, [rsp+0AD0h+Name]; lpName
0x18002f330  mov     [rsp+0AD0h+lpcchClass], r12; lpcchClass
0x18002f335  mov     edx, r14d; dwIndex
0x18002f338  mov     qword ptr [rsp+0AD0h+dwErrorCode], r12; lpClass
0x18002f33d  mov     [rsp+0AD0h+plpszSubStringArray], r12; lpReserved
0x18002f342  mov     [rsp+0AD0h+cchName], 101h
0x18002f34a  mov     dword ptr [rsp+0AD0h+Data], r12d
0x18002f34f  mov     [rsp+0AD0h+cbData], 4
0x18002f357  mov     dword ptr [rsp+0AD0h+var_A80], r12d
0x18002f35c  call    cs:__imp_RegEnumKeyExW
0x18002f362  mov     edi, eax
0x18002f364  test    eax, eax
0x18002f366  jz      short loc_18002F373
0x18002f368  cmp     eax, 0EAh
0x18002f36d  jnz     loc_18002F40A
0x18002f373  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x18002f37a  mov     [rbp+9D0h+var_860], r12w
0x18002f382  lea     rcx, [rsp+0AD0h+Name]; String1
0x18002f387  call    cs:__imp__wcsicmp
0x18002f38d  test    eax, eax
0x18002f38f  jz      short loc_18002F402
0x18002f391  mov     rcx, [rsp+0AD0h+hKey]; hKey
0x18002f396  lea     rdx, [rsp+0AD0h+Name]; lpSubKey
0x18002f39b  mov     r9d, 2001Fh; samDesired
0x18002f3a1  mov     [rsp+0AD0h+plpszSubStringArray], rsi; phkResult
0x18002f3a6  xor     r8d, r8d; ulOptions
0x18002f3a9  call    cs:__imp_RegOpenKeyExW
0x18002f3af  mov     edi, eax
0x18002f3b1  test    eax, eax
0x18002f3b3  jnz     loc_18002F4C0
0x18002f3b9  mov     rcx, [rsi]; hKey
0x18002f3bc  lea     rax, [rsp+0AD0h+cbData]
0x18002f3c1  mov     qword ptr [rsp+0AD0h+dwErrorCode], rax; lpcbData
0x18002f3c6  lea     r9, [rsp+0AD0h+var_A80]; lpType
0x18002f3cb  lea     rax, [rsp+0AD0h+Data]
0x18002f3d0  xor     r8d, r8d; lpReserved
0x18002f3d3  mov     rdx, r13; lpValueName
0x18002f3d6  mov     [rsp+0AD0h+plpszSubStringArray], rax; lpData
0x18002f3db  call    cs:__imp_RegQueryValueExW
0x18002f3e1  mov     edi, eax
0x18002f3e3  test    eax, eax
0x18002f3e5  jnz     loc_18002F472
0x18002f3eb  cmp     dword ptr [rsp+0AD0h+Data], r15d
0x18002f3f0  jz      loc_18002F543
0x18002f3f6  mov     rcx, [rsi]; hKey
0x18002f3f9  call    cs:__imp_RegCloseKey
0x18002f3ff  mov     [rsi], r12
0x18002f402  add     r14d, ebx
0x18002f405  jmp     loc_18002F2FF
0x18002f40a  cmp     edi, 103h
0x18002f410  jnz     short loc_18002F41A
0x18002f412  mov     edi, r12d
0x18002f415  jmp     loc_18002F543
0x18002f41a  cmp     cs:dword_180070F40, r12d
0x18002f421  lea     rax, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Re"...
0x18002f428  mov     [rsp+0AD0h+var_A90], rax
0x18002f42d  jbe     short loc_18002F455
0x18002f42f  mov     rcx, cs:hLogHandle; hLogHandle
0x18002f436  lea     rax, [rsp+0AD0h+var_A90]
0x18002f43b  mov     [rsp+0AD0h+dwErrorCode], edi; dwErrorCode
0x18002f43f  mov     r9d, ebx; dwSubStringCount
0x18002f442  mov     r8d, 4E86h; dwMessageId
0x18002f448  mov     [rsp+0AD0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002f44d  mov     edx, ebx; dwEventType
0x18002f44f  call    cs:__imp_RouterLogEventW
0x18002f455  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18002f45b  jz      loc_18002F543
0x18002f461  lea     r8, [rsp+0AD0h+var_A90]
0x18002f466  lea     rdx, aCannotEnumerat; "Cannot enumerate keys of Registry key %"...
0x18002f46d  jmp     loc_18002F50D
0x18002f472  cmp     cs:dword_180070F40, r12d
0x18002f479  mov     [rsp+0AD0h+var_A90], r13
0x18002f47e  jbe     short loc_18002F4A6
0x18002f480  mov     rcx, cs:hLogHandle; hLogHandle
0x18002f487  mov     r9d, ebx; dwSubStringCount
0x18002f48a  mov     [rsp+0AD0h+dwErrorCode], eax; dwErrorCode
0x18002f48e  mov     r8d, 4E83h; dwMessageId
0x18002f494  lea     rax, [rsp+0AD0h+var_A90]
0x18002f499  mov     edx, ebx; dwEventType
0x18002f49b  mov     [rsp+0AD0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002f4a0  call    cs:__imp_RouterLogEventW
0x18002f4a6  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18002f4ac  jz      loc_18002F543
0x18002f4b2  lea     r8, [rsp+0AD0h+var_A90]
0x18002f4b7  lea     rdx, aCannotAccessTh_2; "Cannot access the Registry value for %w"...
0x18002f4be  jmp     short loc_18002F50D
0x18002f4c0  cmp     cs:dword_180070F40, r12d
0x18002f4c7  lea     rax, [rsp+0AD0h+Name]
0x18002f4cc  mov     [rsp+0AD0h+var_A90], rax
0x18002f4d1  jbe     short loc_18002F4F9
0x18002f4d3  mov     rcx, cs:hLogHandle; hLogHandle
0x18002f4da  lea     rax, [rsp+0AD0h+var_A90]
0x18002f4df  mov     [rsp+0AD0h+dwErrorCode], edi; dwErrorCode
0x18002f4e3  mov     r9d, ebx; dwSubStringCount
0x18002f4e6  mov     r8d, 4E84h; dwMessageId
0x18002f4ec  mov     [rsp+0AD0h+plpszSubStringArray], rax; plpszSubStringArray
0x18002f4f1  mov     edx, ebx; dwEventType
0x18002f4f3  call    cs:__imp_RouterLogEventW
0x18002f4f9  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18002f4ff  jz      short loc_18002F543
0x18002f501  lea     r8, [rsp+0AD0h+var_A90]
0x18002f506  lea     rdx, aCannotAccessTh_0; "Cannot access the Registry key %ws."
0x18002f50d  lea     rcx, [rbp+9D0h+var_850]
0x18002f514  mov     word ptr [rbp+9D0h+var_850], r12w
0x18002f51c  call    FormatRRASErrorString
0x18002f521  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x18002f527  jz      short loc_18002F543
0x18002f529  lea     r8, [rbp+9D0h+var_850]
0x18002f530  lea     rdx, RasDimTraceAdminError
0x18002f537  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002f53e  call    McTemplateU0z_EventWriteTransfer
0x18002f543  mov     rcx, [rsp+0AD0h+hKey]; hKey
0x18002f548  test    rcx, rcx
0x18002f54b  jz      short loc_18002F553
0x18002f54d  call    cs:__imp_RegCloseKey
0x18002f553  test    edi, edi
0x18002f555  jz      short loc_18002F568
0x18002f557  mov     rcx, [rsi]; hKey
0x18002f55a  test    rcx, rcx
0x18002f55d  jz      short loc_18002F568
0x18002f55f  call    cs:__imp_RegCloseKey
0x18002f565  mov     [rsi], r12
0x18002f568  cmp     [rsi], r12
0x18002f56b  mov     eax, 386h
0x18002f570  cmovz   edi, eax
0x18002f573  mov     eax, edi
0x18002f575  mov     rcx, [rbp+9D0h+var_50]
0x18002f57c  xor     rcx, rsp; StackCookie
0x18002f57f  call    __security_check_cookie
0x18002f584  add     rsp, 0A98h
0x18002f58b  pop     r15
0x18002f58d  pop     r14
0x18002f58f  pop     r13
0x18002f591  pop     r12
0x18002f593  pop     rdi
0x18002f594  pop     rsi
0x18002f595  pop     rbx
0x18002f596  pop     rbp
0x18002f597  retn
```
