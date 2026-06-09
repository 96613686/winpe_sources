# CGPMachineStartupConnectivity::GetWaitTimeoutValue(ulong *)

- ea: `0x180091bf0`
- end: `0x180091d9c`
- name: `?GetWaitTimeoutValue@CGPMachineStartupConnectivity@@QEAAKPEAK@Z`
- size: `428`
- prototype: `unsigned int __fastcall(CGPMachineStartupConnectivity *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18008ab80`
- `0x180091eec`

## callees

- `0x180091988`
- `0x180091bf0`
- `0x1800b431c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091cec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091d50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091cec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180091d50`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091c51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091cb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091d18`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091c51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091cb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180091d18`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180091c7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180091ce2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180091d46`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180091c7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180091ce2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180091d46`

## pseudocode

```c
__int64 __fastcall CGPMachineStartupConnectivity::GetWaitTimeoutValue(
        CGPMachineStartupConnectivity *this,
        unsigned int *a2)
{
  unsigned int v4; // ebx
  int v5; // eax
  int v6; // ecx
  DWORD Type; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+38h] BYREF

  Data = 0;
  cbData = 4;
  Type = 4;
  hKey = 0;
  if ( CheckIfDirectAccessIsInstalled() )
  {
    Data = 60;
    v4 = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\System", 0, 0x20019u, &hKey) )
    {
      if ( !RegQueryValueExW(hKey, L"CorpConnStartTimeoutPolicyValue", 0, &Type, (LPBYTE)&Data, &cbData) )
        *((_DWORD *)this + 2) = 1;
      RegCloseKey(hKey);
    }
    v5 = 1000 * Data;
  }
  else
  {
    Data = -1;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
            0,
            0x20019u,
            &hKey) )
    {
      RegQueryValueExW(hKey, L"GpNetworkStartTimeoutPolicyValue", 0, &Type, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey);
    }
    cbData = 4;
    Type = 4;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Policies\\Microsoft\\Windows\\System", 0, 0x20019u, &hKey) )
    {
      RegQueryValueExW(hKey, L"GpNetworkStartTimeoutPolicyValue", 0, &Type, (LPBYTE)&Data, &cbData);
      RegCloseKey(hKey);
    }
    v6 = Data;
    if ( Data == -1 )
      return (unsigned int)CGPMachineStartupConnectivity::CalculateWaitTimeoutFromHistory(this, a2);
    v4 = 0;
    if ( (unsigned int)(Data - 1) > 0x257 )
      v6 = 600;
    *((_DWORD *)this + 2) = 1;
    v5 = 1000 * v6;
  }
  *a2 = v5;
  return v4;
}

```

## disassembly

```asm
0x180091bf0  mov     [rsp-18h+arg_0], rbx
0x180091bf5  push    rbp
0x180091bf6  push    rsi
0x180091bf7  push    rdi
0x180091bf8  mov     rbp, rsp
0x180091bfb  sub     rsp, 40h
0x180091bff  mov     ebx, 4
0x180091c04  mov     [rbp+Data], 0
0x180091c0b  mov     [rbp+cbData], ebx
0x180091c0e  mov     rdi, rdx
0x180091c11  mov     [rbp+Type], ebx
0x180091c14  mov     rsi, rcx
0x180091c17  mov     [rbp+hKey], 0
0x180091c1f  call    ?CheckIfDirectAccessIsInstalled@@YAHXZ; CheckIfDirectAccessIsInstalled(void)
0x180091c24  xor     r8d, r8d; ulOptions
0x180091c27  mov     r9d, 20019h; samDesired
0x180091c2d  test    eax, eax
0x180091c2f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180091c36  lea     rax, [rbp+hKey]
0x180091c3a  mov     [rsp+40h+phkResult], rax; phkResult
0x180091c3f  jz      short loc_180091CA6
0x180091c41  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180091c48  mov     [rbp+Data], 3Ch ; '<'
0x180091c4f  xor     ebx, ebx
0x180091c51  call    cs:__imp_RegOpenKeyExW
0x180091c57  test    eax, eax
0x180091c59  jnz     short loc_180091C9A
0x180091c5b  mov     rcx, [rbp+hKey]; hKey
0x180091c5f  lea     rax, [rbp+cbData]
0x180091c63  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180091c68  lea     r9, [rbp+Type]; lpType
0x180091c6c  lea     rax, [rbp+Data]
0x180091c70  xor     r8d, r8d; lpReserved
0x180091c73  lea     rdx, aCorpconnstartt; "CorpConnStartTimeoutPolicyValue"
0x180091c7a  mov     [rsp+40h+phkResult], rax; lpData
0x180091c7f  call    cs:__imp_RegQueryValueExW
0x180091c85  test    eax, eax
0x180091c87  jnz     short loc_180091C90
0x180091c89  mov     dword ptr [rsi+8], 1
0x180091c90  mov     rcx, [rbp+hKey]; hKey
0x180091c94  call    cs:__imp_RegCloseKey
0x180091c9a  imul    eax, [rbp+Data], 3E8h
0x180091ca1  jmp     loc_180091D7C
0x180091ca6  lea     rdx, aSoftwareMicros_39; "Software\\Microsoft\\Windows NT\\Curren"...
0x180091cad  mov     [rbp+Data], 0FFFFFFFFh
0x180091cb4  call    cs:__imp_RegOpenKeyExW
0x180091cba  test    eax, eax
0x180091cbc  jnz     short loc_180091CF2
0x180091cbe  mov     rcx, [rbp+hKey]; hKey
0x180091cc2  lea     rax, [rbp+cbData]
0x180091cc6  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180091ccb  lea     r9, [rbp+Type]; lpType
0x180091ccf  lea     rax, [rbp+Data]
0x180091cd3  xor     r8d, r8d; lpReserved
0x180091cd6  lea     rdx, aGpnetworkstart; "GpNetworkStartTimeoutPolicyValue"
0x180091cdd  mov     [rsp+40h+phkResult], rax; lpData
0x180091ce2  call    cs:__imp_RegQueryValueExW
0x180091ce8  mov     rcx, [rbp+hKey]; hKey
0x180091cec  call    cs:__imp_RegCloseKey
0x180091cf2  lea     rax, [rbp+hKey]
0x180091cf6  mov     [rbp+cbData], ebx
0x180091cf9  mov     r9d, 20019h; samDesired
0x180091cff  mov     [rsp+40h+phkResult], rax; phkResult
0x180091d04  xor     r8d, r8d; ulOptions
0x180091d07  mov     [rbp+Type], ebx
0x180091d0a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180091d11  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180091d18  call    cs:__imp_RegOpenKeyExW
0x180091d1e  test    eax, eax
0x180091d20  jnz     short loc_180091D56
0x180091d22  mov     rcx, [rbp+hKey]; hKey
0x180091d26  lea     rax, [rbp+cbData]
0x180091d2a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180091d2f  lea     r9, [rbp+Type]; lpType
0x180091d33  lea     rax, [rbp+Data]
0x180091d37  xor     r8d, r8d; lpReserved
0x180091d3a  lea     rdx, aGpnetworkstart; "GpNetworkStartTimeoutPolicyValue"
0x180091d41  mov     [rsp+40h+phkResult], rax; lpData
0x180091d46  call    cs:__imp_RegQueryValueExW
0x180091d4c  mov     rcx, [rbp+hKey]; hKey
0x180091d50  call    cs:__imp_RegCloseKey
0x180091d56  mov     ecx, [rbp+Data]
0x180091d59  cmp     ecx, 0FFFFFFFFh
0x180091d5c  jz      short loc_180091D80
0x180091d5e  xor     ebx, ebx
0x180091d60  lea     eax, [rcx-1]
0x180091d63  cmp     eax, 257h
0x180091d68  jbe     short loc_180091D6F
0x180091d6a  mov     ecx, 258h
0x180091d6f  mov     dword ptr [rsi+8], 1
0x180091d76  imul    eax, ecx, 3E8h
0x180091d7c  mov     [rdi], eax
0x180091d7e  jmp     short loc_180091D8D
0x180091d80  mov     rdx, rdi; unsigned int *
0x180091d83  mov     rcx, rsi; this
0x180091d86  call    ?CalculateWaitTimeoutFromHistory@CGPMachineStartupConnectivity@@AEAAKPEAK@Z; CGPMachineStartupConnectivity::CalculateWaitTimeoutFromHistory(ulong *)
0x180091d8b  mov     ebx, eax
0x180091d8d  mov     eax, ebx
0x180091d8f  mov     rbx, [rsp+40h+arg_0]
0x180091d94  add     rsp, 40h
0x180091d98  pop     rdi
0x180091d99  pop     rsi
0x180091d9a  pop     rbp
0x180091d9b  retn
```
