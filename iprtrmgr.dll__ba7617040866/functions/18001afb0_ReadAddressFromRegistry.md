# ReadAddressFromRegistry

- ea: `0x18001afb0`
- end: `0x18001b28c`
- name: `ReadAddressFromRegistry`
- size: `732`
- prototype: `__int64 __fastcall(wchar_t *Source, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a420`

## callees

- `0x18000ac60`
- `0x18001255c`
- `0x18001abfc`
- `0x18001afb0`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `msvcrt!wcstombs` at `0x18001b0b4`
- `msvcrt!wcstombs` at `0x18001b0b4`
- `ADVAPI32!RegQueryValueExA` at `0x18001b189`
- `ADVAPI32!RegQueryValueExA` at `0x18001b189`
- `ADVAPI32!RegCloseKey` at `0x18001b1b9`
- `ADVAPI32!RegCloseKey` at `0x18001b22a`
- `ADVAPI32!RegCloseKey` at `0x18001b1b9`
- `ADVAPI32!RegCloseKey` at `0x18001b22a`
- `ADVAPI32!RegOpenKeyA` at `0x18001b100`
- `ADVAPI32!RegOpenKeyA` at `0x18001b100`

## string_xrefs

- `0x18001b034`: `ReadAddressFromRegistry`
- `0x18001b07d`: `ReadAddressFromRegistry: Reading address for %ws`
- `0x18001b0c2`: `System\CurrentControlSet\Services\TCPIP\Parameters\Interfaces`
- `0x18001b121`: `ReadAddressFromRegistry: Unable to open key %hs`
- `0x18001b19e`: `ReadAddressFromRegistry: Unable to read DHCP Enabled key`
- `0x18001b1ea`: `IPAutoconfigurationMask`
- `0x18001b1f1`: `IPAutoconfigurationAddress`
- `0x18001b245`: `ReadAddressFromRegistry: Couldnt read address for %ws. Error %d. DHCP %d`

## pseudocode

```c
__int64 __fastcall ReadAddressFromRegistry(wchar_t *Source, BYTE *a2, _QWORD *a3)
{
  unsigned int AddressAndMaskValues; // ebx
  __int64 v8; // r9
  HKEY v9; // rcx
  const CHAR *v10; // r8
  const CHAR *v11; // rdx
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPBYTE lpDataa; // [rsp+20h] [rbp-E0h]
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type[4]; // [rsp+40h] [rbp-C0h] BYREF
  char Dest[256]; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v20[2044]; // [rsp+154h] [rbp+54h] BYREF
  char pszDest[512]; // [rsp+950h] [rbp+850h] BYREF

  phkResult = 0;
  memset_0(Dest, 0, sizeof(Dest));
  *(_DWORD *)Data = 0;
  cbData = 0;
  Type[0] = 0;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v19, L"Entered: %ws", L"ReadAddressFromRegistry");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v19);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v19) = 0;
        FormatRRASErrorString(&v19, L"ReadAddressFromRegistry: Reading address for %ws", Source);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v19);
      }
    }
  }
  wcstombs(Dest, Source, 0x100u);
  *(_DWORD *)a2 = 0;
  Dest[255] = 0;
  *a3 = 0;
  StringCbPrintfA(pszDest, 0x200u, "%s\\%s", "System\\CurrentControlSet\\Services\\TCPIP\\Parameters\\Interfaces", Dest);
  AddressAndMaskValues = RegOpenKeyA(HKEY_LOCAL_MACHINE, pszDest, &phkResult);
  if ( AddressAndMaskValues )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v19) = 0;
      FormatRRASErrorString(&v19, L"ReadAddressFromRegistry: Unable to open key %hs", pszDest);
      goto LABEL_9;
    }
    return AddressAndMaskValues;
  }
  *(_DWORD *)Data = 0;
  cbData = 4;
  AddressAndMaskValues = RegQueryValueExA(phkResult, "EnableDHCP", 0, Type, Data, &cbData);
  if ( AddressAndMaskValues )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrMgrTraceError,
        L"ReadAddressFromRegistry: Unable to read DHCP Enabled key");
    RegCloseKey(phkResult);
    return AddressAndMaskValues;
  }
  v8 = (__int64)a3;
  v9 = phkResult;
  cbData = 0;
  lpData = a2;
  if ( *(_DWORD *)Data )
  {
    AddressAndMaskValues = ReadAddressAndMaskValues(
                             phkResult,
                             "IPAutoconfigurationAddress",
                             "IPAutoconfigurationMask",
                             (__int64)a3,
                             (__int64)a2);
    if ( !AddressAndMaskValues )
      goto LABEL_21;
    v9 = phkResult;
    v10 = "DhcpSubnetMask";
    lpData = a2;
    v11 = "DhcpIPAddress";
    v8 = (__int64)a3;
  }
  else
  {
    v10 = "SubnetMask";
    v11 = "IPAddress";
  }
  AddressAndMaskValues = ReadAddressAndMaskValues(v9, v11, v10, v8, (__int64)lpData);
LABEL_21:
  RegCloseKey(phkResult);
  if ( AddressAndMaskValues )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LODWORD(lpDataa) = *(_DWORD *)Data;
      LOWORD(v19) = 0;
      FormatRRASErrorString(
        &v19,
        L"ReadAddressFromRegistry: Couldnt read address for %ws. Error %d. DHCP %d",
        Source,
        AddressAndMaskValues,
        lpDataa);
LABEL_9:
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v19);
    }
    return AddressAndMaskValues;
  }
  return 0;
}

```

## disassembly

```asm
0x18001afb0  push    rbp
0x18001afb2  push    rbx
0x18001afb3  push    rsi
0x18001afb4  push    rdi
0x18001afb5  push    r12
0x18001afb7  push    r14
0x18001afb9  push    r15
0x18001afbb  lea     rbp, [rsp-0A60h]
0x18001afc3  sub     rsp, 0B60h
0x18001afca  mov     rax, cs:__security_cookie
0x18001afd1  xor     rax, rsp
0x18001afd4  mov     [rbp+0A90h+var_40], rax
0x18001afdb  mov     rsi, r8
0x18001afde  mov     rdi, rdx
0x18001afe1  mov     r14, rcx
0x18001afe4  mov     ebx, 100h
0x18001afe9  xor     r15d, r15d
0x18001afec  lea     rcx, [rsp+0B90h+Dest]; void *
0x18001aff1  mov     r8d, ebx; Size
0x18001aff4  mov     [rsp+0B90h+phkResult], r15
0x18001aff9  xor     edx, edx; Val
0x18001affb  call    memset_0
0x18001b000  xor     edx, edx; Val
0x18001b002  mov     dword ptr [rsp+0B90h+Data], r15d
0x18001b007  mov     r8d, 7FCh; Size
0x18001b00d  mov     [rsp+0B90h+cbData], r15d
0x18001b012  lea     rcx, [rbp+0A90h+var_A3C]; void *
0x18001b016  mov     [rsp+0B90h+Type], r15d
0x18001b01b  mov     [rbp+0A90h+var_A40], r15d
0x18001b01f  call    memset_0
0x18001b024  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001b02b  lea     r12, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001b032  jge     short loc_18001B0A9
0x18001b034  lea     r8, aReadaddressfro_1; "ReadAddressFromRegistry"
0x18001b03b  mov     word ptr [rbp+0A90h+var_A40], r15w
0x18001b040  lea     rdx, aEnteredWs; "Entered: %ws"
0x18001b047  lea     rcx, [rbp+0A90h+var_A40]
0x18001b04b  call    FormatRRASErrorString
0x18001b050  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001b057  jge     short loc_18001B0A9
0x18001b059  lea     r8, [rbp+0A90h+var_A40]
0x18001b05d  mov     rcx, r12
0x18001b060  lea     rdx, RasRtrmgrTraceInfo
0x18001b067  call    McTemplateU0z_EventWriteTransfer
0x18001b06c  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001b073  jge     short loc_18001B0A9
0x18001b075  mov     r8, r14
0x18001b078  mov     word ptr [rbp+0A90h+var_A40], r15w
0x18001b07d  lea     rdx, aReadaddressfro; "ReadAddressFromRegistry: Reading addres"...
0x18001b084  lea     rcx, [rbp+0A90h+var_A40]
0x18001b088  call    FormatRRASErrorString
0x18001b08d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001b094  jge     short loc_18001B0A9
0x18001b096  lea     r8, [rbp+0A90h+var_A40]
0x18001b09a  mov     rcx, r12
0x18001b09d  lea     rdx, RasRtrmgrTraceInfo
0x18001b0a4  call    McTemplateU0z_EventWriteTransfer
0x18001b0a9  mov     r8, rbx; MaxCount
0x18001b0ac  lea     rcx, [rsp+0B90h+Dest]; Dest
0x18001b0b1  mov     rdx, r14; Source
0x18001b0b4  call    cs:__imp_wcstombs
0x18001b0ba  lea     rax, [rsp+0B90h+Dest]
0x18001b0bf  mov     [rdi], r15d
0x18001b0c2  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\TC"...
0x18001b0c9  mov     [rsp+0B90h+lpData], rax
0x18001b0ce  lea     r8, aSS_3; "%s\\%s"
0x18001b0d5  mov     [rbp+0A90h+var_A41], r15b
0x18001b0d9  mov     edx, 200h; cbDest
0x18001b0de  mov     [rsi], r15
0x18001b0e1  lea     rcx, [rbp+0A90h+pszDest]; pszDest
0x18001b0e8  call    StringCbPrintfA
0x18001b0ed  lea     r8, [rsp+0B90h+phkResult]; phkResult
0x18001b0f2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b0f9  lea     rdx, [rbp+0A90h+pszDest]; lpSubKey
0x18001b100  call    cs:__imp_RegOpenKeyA
0x18001b106  mov     ebx, eax
0x18001b108  test    eax, eax
0x18001b10a  jz      short loc_18001B154
0x18001b10c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b113  jz      short loc_18001B14D
0x18001b115  lea     r8, [rbp+0A90h+pszDest]
0x18001b11c  mov     word ptr [rbp+0A90h+var_A40], r15w
0x18001b121  lea     rdx, aReadaddressfro_2; "ReadAddressFromRegistry: Unable to open"...
0x18001b128  lea     rcx, [rbp+0A90h+var_A40]
0x18001b12c  call    FormatRRASErrorString
0x18001b131  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b138  jz      short loc_18001B14D
0x18001b13a  lea     r8, [rbp+0A90h+var_A40]
0x18001b13e  mov     rcx, r12
0x18001b141  lea     rdx, RasRtrMgrTraceError
0x18001b148  call    McTemplateU0z_EventWriteTransfer
0x18001b14d  mov     eax, ebx
0x18001b14f  jmp     loc_18001B26B
0x18001b154  mov     rcx, [rsp+0B90h+phkResult]; hKey
0x18001b159  lea     rax, [rsp+0B90h+cbData]
0x18001b15e  mov     [rsp+0B90h+lpcbData], rax; lpcbData
0x18001b163  lea     r9, [rsp+0B90h+Type]; lpType
0x18001b168  lea     rax, [rsp+0B90h+Data]
0x18001b16d  mov     dword ptr [rsp+0B90h+Data], r15d
0x18001b172  xor     r8d, r8d; lpReserved
0x18001b175  mov     [rsp+0B90h+lpData], rax; lpData
0x18001b17a  lea     rdx, aEnabledhcp; "EnableDHCP"
0x18001b181  mov     [rsp+0B90h+cbData], 4
0x18001b189  call    cs:__imp_RegQueryValueExA
0x18001b18f  mov     ebx, eax
0x18001b191  test    eax, eax
0x18001b193  jz      short loc_18001B1C1
0x18001b195  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b19c  jz      short loc_18001B1B4
0x18001b19e  lea     r8, aReadaddressfro_0; "ReadAddressFromRegistry: Unable to read"...
0x18001b1a5  mov     rcx, r12
0x18001b1a8  lea     rdx, RasRtrMgrTraceError
0x18001b1af  call    McTemplateU0z_EventWriteTransfer
0x18001b1b4  mov     rcx, [rsp+0B90h+phkResult]; hKey
0x18001b1b9  call    cs:__imp_RegCloseKey
0x18001b1bf  jmp     short loc_18001B14D
0x18001b1c1  mov     r9, rsi; __int64
0x18001b1c4  mov     rcx, [rsp+0B90h+phkResult]; hKey
0x18001b1c9  mov     [rsp+0B90h+cbData], r15d
0x18001b1ce  mov     [rsp+0B90h+lpData], rdi; __int64
0x18001b1d3  cmp     dword ptr [rsp+0B90h+Data], r15d
0x18001b1d8  jnz     short loc_18001B1EA
0x18001b1da  lea     r8, aSubnetmask; "SubnetMask"
0x18001b1e1  lea     rdx, aIpaddress; "IPAddress"
0x18001b1e8  jmp     short loc_18001B21E
0x18001b1ea  lea     r8, aIpautoconfigur_0; "IPAutoconfigurationMask"
0x18001b1f1  lea     rdx, aIpautoconfigur; "IPAutoconfigurationAddress"
0x18001b1f8  call    ReadAddressAndMaskValues
0x18001b1fd  mov     ebx, eax
0x18001b1ff  test    eax, eax
0x18001b201  jz      short loc_18001B225
0x18001b203  mov     rcx, [rsp+0B90h+phkResult]; hKey
0x18001b208  lea     r8, aDhcpsubnetmask; "DhcpSubnetMask"
0x18001b20f  mov     [rsp+0B90h+lpData], rdi; __int64
0x18001b214  lea     rdx, aDhcpipaddress; "DhcpIPAddress"
0x18001b21b  mov     r9, rsi; __int64
0x18001b21e  call    ReadAddressAndMaskValues
0x18001b223  mov     ebx, eax
0x18001b225  mov     rcx, [rsp+0B90h+phkResult]; hKey
0x18001b22a  call    cs:__imp_RegCloseKey
0x18001b230  test    ebx, ebx
0x18001b232  jz      short loc_18001B269
0x18001b234  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001b23b  jz      loc_18001B14D
0x18001b241  mov     eax, dword ptr [rsp+0B90h+Data]
0x18001b245  lea     rdx, aReadaddressfro_3; "ReadAddressFromRegistry: Couldnt read a"...
0x18001b24c  mov     r9d, ebx
0x18001b24f  mov     dword ptr [rsp+0B90h+lpData], eax
0x18001b253  mov     r8, r14
0x18001b256  mov     word ptr [rbp+0A90h+var_A40], r15w
0x18001b25b  lea     rcx, [rbp+0A90h+var_A40]
0x18001b25f  call    FormatRRASErrorString
0x18001b264  jmp     loc_18001B131
0x18001b269  xor     eax, eax
0x18001b26b  mov     rcx, [rbp+0A90h+var_40]
0x18001b272  xor     rcx, rsp; StackCookie
0x18001b275  call    __security_check_cookie
0x18001b27a  add     rsp, 0B60h
0x18001b281  pop     r15
0x18001b283  pop     r14
0x18001b285  pop     r12
0x18001b287  pop     rdi
0x18001b288  pop     rsi
0x18001b289  pop     rbx
0x18001b28a  pop     rbp
0x18001b28b  retn
```
