# GetServerPrefixFromRegistry

- ea: `0x180051cec`
- end: `0x180051e7f`
- name: `GetServerPrefixFromRegistry`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180051a14`

## callees

- `0x18000ac60`
- `0x180051cec`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180051d74`
- `ADVAPI32!RegOpenKeyExA` at `0x180051d74`
- `ADVAPI32!RegQueryValueExA` at `0x180051dfe`
- `ADVAPI32!RegQueryValueExA` at `0x180051dfe`
- `ADVAPI32!RegCloseKey` at `0x180051e53`
- `ADVAPI32!RegCloseKey` at `0x180051e53`

## string_xrefs

- `0x180051d66`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6\StaticPrefixPool\0`
- `0x180051d8f`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6\StaticPrefixPool\0`
- `0x180051d9b`: `GetServerPrefixFromRegistry: Failed to open %s. Error %d`
- `0x180051e25`: `GetServerPrefixFromRegistry: Failed to query %s. Size returned %d. Error %d`

## pseudocode

```c
__int64 __fastcall GetServerPrefixFromRegistry(_OWORD *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  int v10; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v11[2044]; // [rsp+54h] [rbp-ACh] BYREF

  Type = 3;
  hKey = 0;
  cbData = 16;
  v10 = 0;
  *(_OWORD *)Data = 0;
  memset_0(v11, 0, sizeof(v11));
  v2 = RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6\\StaticPrefixPool\\0",
         0,
         1u,
         &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_10;
    LOWORD(v10) = 0;
    FormatRRASErrorString(
      &v10,
      L"GetServerPrefixFromRegistry: Failed to open %s. Error %d",
      "SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6\\StaticPrefixPool\\0",
      v2);
  }
  else
  {
    v3 = RegQueryValueExA(hKey, "From", 0, &Type, Data, &cbData);
    if ( !v3 )
    {
      *a1 = *(_OWORD *)Data;
      goto LABEL_10;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      goto LABEL_10;
    LODWORD(phkResult) = v3;
    LOWORD(v10) = 0;
    FormatRRASErrorString(
      &v10,
      L"GetServerPrefixFromRegistry: Failed to query %s. Size returned %d. Error %d",
      "From",
      cbData,
      phkResult);
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v10);
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180051cec  mov     [rsp-8+arg_8], rbx
0x180051cf1  mov     [rsp-8+arg_10], rdi
0x180051cf6  push    rbp
0x180051cf7  lea     rbp, [rsp-760h]
0x180051cff  sub     rsp, 860h
0x180051d06  mov     rax, cs:__security_cookie
0x180051d0d  xor     rax, rsp
0x180051d10  mov     [rbp+760h+var_10], rax
0x180051d17  mov     rdi, rcx
0x180051d1a  mov     [rsp+860h+Type], 3
0x180051d22  xorps   xmm0, xmm0
0x180051d25  mov     [rsp+860h+hKey], 0
0x180051d2e  xor     eax, eax
0x180051d30  mov     [rsp+860h+cbData], 10h
0x180051d38  lea     rcx, [rsp+860h+var_80C]; void *
0x180051d3d  mov     [rsp+860h+var_810], eax
0x180051d41  xor     edx, edx; Val
0x180051d43  mov     r8d, 7FCh; Size
0x180051d49  movups  xmmword ptr [rsp+860h+Data], xmm0
0x180051d4e  call    memset_0
0x180051d53  lea     rax, [rsp+860h+hKey]
0x180051d58  mov     r9d, 1; samDesired
0x180051d5e  xor     r8d, r8d; ulOptions
0x180051d61  mov     [rsp+860h+phkResult], rax; phkResult
0x180051d66  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180051d6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180051d74  call    cs:__imp_RegOpenKeyExA
0x180051d7a  mov     ebx, eax
0x180051d7c  test    eax, eax
0x180051d7e  jz      short loc_180051DD6
0x180051d80  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180051d87  jge     loc_180051E49
0x180051d8d  xor     ecx, ecx
0x180051d8f  lea     r8, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180051d96  mov     word ptr [rsp+860h+var_810], cx
0x180051d9b  lea     rdx, aGetserverprefi_1; "GetServerPrefixFromRegistry: Failed to "...
0x180051da2  lea     rcx, [rsp+860h+var_810]
0x180051da7  mov     r9d, eax
0x180051daa  call    FormatRRASErrorString
0x180051daf  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180051db6  jge     loc_180051E49
0x180051dbc  lea     r8, [rsp+860h+var_810]
0x180051dc1  lea     rdx, RasRtrmgrTraceInfo
0x180051dc8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180051dcf  call    McTemplateU0z_EventWriteTransfer
0x180051dd4  jmp     short loc_180051E49
0x180051dd6  mov     rcx, [rsp+860h+hKey]; hKey
0x180051ddb  lea     rax, [rsp+860h+cbData]
0x180051de0  mov     [rsp+860h+lpcbData], rax; lpcbData
0x180051de5  lea     r9, [rsp+860h+Type]; lpType
0x180051dea  lea     rax, [rsp+860h+Data]
0x180051def  xor     r8d, r8d; lpReserved
0x180051df2  lea     rdx, aFrom; "From"
0x180051df9  mov     [rsp+860h+phkResult], rax; lpData
0x180051dfe  call    cs:__imp_RegQueryValueExA
0x180051e04  mov     ebx, eax
0x180051e06  test    eax, eax
0x180051e08  jz      short loc_180051E40
0x180051e0a  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180051e11  jge     short loc_180051E49
0x180051e13  mov     r9d, [rsp+860h+cbData]
0x180051e18  lea     r8, aFrom; "From"
0x180051e1f  xor     eax, eax
0x180051e21  mov     dword ptr [rsp+860h+phkResult], ebx
0x180051e25  lea     rdx, aGetserverprefi_0; "GetServerPrefixFromRegistry: Failed to "...
0x180051e2c  mov     word ptr [rsp+860h+var_810], ax
0x180051e31  lea     rcx, [rsp+860h+var_810]
0x180051e36  call    FormatRRASErrorString
0x180051e3b  jmp     loc_180051DAF
0x180051e40  movups  xmm0, xmmword ptr [rsp+860h+Data]
0x180051e45  movdqu  xmmword ptr [rdi], xmm0
0x180051e49  mov     rcx, [rsp+860h+hKey]; hKey
0x180051e4e  test    rcx, rcx
0x180051e51  jz      short loc_180051E59
0x180051e53  call    cs:__imp_RegCloseKey
0x180051e59  mov     eax, ebx
0x180051e5b  mov     rcx, [rbp+760h+var_10]
0x180051e62  xor     rcx, rsp; StackCookie
0x180051e65  call    __security_check_cookie
0x180051e6a  lea     r11, [rsp+860h+var_s0]
0x180051e72  mov     rbx, [r11+18h]
0x180051e76  mov     rdi, [r11+20h]
0x180051e7a  mov     rsp, r11
0x180051e7d  pop     rbp
0x180051e7e  retn
```
