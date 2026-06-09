# IsHardwareAddressRandomized

- ea: `0x18000ee8c`
- end: `0x18000f037`
- name: `IsHardwareAddressRandomized`
- size: `427`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800152b8`

## callees

- `0x180009f58`
- `0x18000ee8c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000eee1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000efc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000eee1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ef0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000efc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000effe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000ef4b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000effe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f01a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ef76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f01a`

## string_xrefs

- `0x18000ef99`: `System\CurrentControlSet\Services\Dhcp`

## pseudocode

```c
_BOOL8 __fastcall IsHardwareAddressRandomized(_BYTE *a1, const WCHAR *a2)
{
  BOOL v2; // ebx
  int IsWCOSSystem; // eax
  const WCHAR *v5; // rdx
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+68h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+38h] BYREF

  v2 = 0;
  if ( a2 )
  {
    if ( a1 )
    {
      if ( (*a1 & 2) != 0 )
      {
        hKey[0] = 0;
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\WlanSvc\\Interfaces", 0, 1u, hKey) )
        {
          phkResult = 0;
          if ( !RegOpenKeyExW(hKey[0], a2, 0, 1u, &phkResult) )
          {
            Data = 0;
            cbData = 4;
            if ( !RegQueryValueExW(phkResult, L"RandomMacState", 0, 0, (LPBYTE)&Data, &cbData) )
              v2 = Data != 0;
            RegCloseKey(phkResult);
          }
          RegCloseKey(hKey[0]);
          if ( v2 )
          {
            hKey[0] = 0;
            IsWCOSSystem = DhcpIsWCOSSystem();
            v5 = L"OSDATA\\Networking\\Dhcp\\PDC";
            if ( !IsWCOSSystem )
              v5 = L"System\\CurrentControlSet\\Services\\Dhcp";
            if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 1u, hKey) )
            {
              Data = 0;
              LODWORD(phkResult) = 0;
              cbData = 4;
              if ( !RegQueryValueExW(hKey[0], L"PrivacyDisabled", 0, (LPDWORD)&phkResult, (LPBYTE)&Data, &cbData)
                && Data )
              {
                v2 = 0;
              }
              RegCloseKey(hKey[0]);
            }
          }
        }
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000ee8c  mov     [rsp-18h+arg_0], rbx
0x18000ee91  push    rbp
0x18000ee92  push    rdi
0x18000ee93  push    r14
0x18000ee95  mov     rbp, rsp
0x18000ee98  sub     rsp, 40h
0x18000ee9c  xor     ebx, ebx
0x18000ee9e  mov     rdi, rdx
0x18000eea1  test    rdx, rdx
0x18000eea4  jz      loc_18000F026
0x18000eeaa  test    rcx, rcx
0x18000eead  jz      loc_18000F026
0x18000eeb3  test    byte ptr [rcx], 2
0x18000eeb6  jz      loc_18000F026
0x18000eebc  lea     rax, [rbp+hKey]
0x18000eec0  mov     [rbp+hKey], rbx
0x18000eec4  lea     r14d, [rbx+1]
0x18000eec8  mov     [rsp+40h+phkResult], rax; phkResult
0x18000eecd  mov     r9d, r14d; samDesired
0x18000eed0  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\WlanSvc\\Interface"...
0x18000eed7  xor     r8d, r8d; ulOptions
0x18000eeda  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000eee1  call    cs:__imp_RegOpenKeyExW
0x18000eee8  nop     dword ptr [rax+rax+00h]
0x18000eeed  test    eax, eax
0x18000eeef  jnz     loc_18000F026
0x18000eef5  mov     rcx, [rbp+hKey]; hKey
0x18000eef9  lea     rax, [rbp+arg_18]
0x18000eefd  mov     r9d, r14d; samDesired
0x18000ef00  mov     [rsp+40h+phkResult], rax; phkResult
0x18000ef05  xor     r8d, r8d; ulOptions
0x18000ef08  mov     [rbp+arg_18], rbx
0x18000ef0c  mov     rdx, rdi; lpSubKey
0x18000ef0f  call    cs:__imp_RegOpenKeyExW
0x18000ef16  nop     dword ptr [rax+rax+00h]
0x18000ef1b  lea     edi, [rbx+4]
0x18000ef1e  test    eax, eax
0x18000ef20  jnz     short loc_18000EF72
0x18000ef22  mov     rcx, [rbp+arg_18]; hKey
0x18000ef26  lea     rax, [rbp+cbData]
0x18000ef2a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000ef2f  lea     rdx, aRandommacstate; "RandomMacState"
0x18000ef36  lea     rax, [rbp+Data]
0x18000ef3a  mov     [rbp+Data], ebx
0x18000ef3d  xor     r9d, r9d; lpType
0x18000ef40  mov     [rsp+40h+phkResult], rax; lpData
0x18000ef45  xor     r8d, r8d; lpReserved
0x18000ef48  mov     [rbp+cbData], edi
0x18000ef4b  call    cs:__imp_RegQueryValueExW
0x18000ef52  nop     dword ptr [rax+rax+00h]
0x18000ef57  test    eax, eax
0x18000ef59  jnz     short loc_18000EF62
0x18000ef5b  cmp     [rbp+Data], ebx
0x18000ef5e  cmovnz  ebx, r14d
0x18000ef62  mov     rcx, [rbp+arg_18]; hKey
0x18000ef66  call    cs:__imp_RegCloseKey
0x18000ef6d  nop     dword ptr [rax+rax+00h]
0x18000ef72  mov     rcx, [rbp+hKey]; hKey
0x18000ef76  call    cs:__imp_RegCloseKey
0x18000ef7d  nop     dword ptr [rax+rax+00h]
0x18000ef82  test    ebx, ebx
0x18000ef84  jz      loc_18000F026
0x18000ef8a  mov     [rbp+hKey], 0
0x18000ef92  call    DhcpIsWCOSSystem
0x18000ef97  test    eax, eax
0x18000ef99  lea     r8, aSystemCurrentc_12; "System\\CurrentControlSet\\Services\\Dh"...
0x18000efa0  lea     rax, [rbp+hKey]
0x18000efa4  mov     r9d, r14d; samDesired
0x18000efa7  lea     rdx, aOsdataNetworki_4; "OSDATA\\Networking\\Dhcp\\PDC"
0x18000efae  mov     [rsp+40h+phkResult], rax; phkResult
0x18000efb3  cmovz   rdx, r8; lpSubKey
0x18000efb7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000efbe  xor     r8d, r8d; ulOptions
0x18000efc1  call    cs:__imp_RegOpenKeyExW
0x18000efc8  nop     dword ptr [rax+rax+00h]
0x18000efcd  test    eax, eax
0x18000efcf  jnz     short loc_18000F026
0x18000efd1  mov     rcx, [rbp+hKey]; hKey
0x18000efd5  lea     r9, [rbp+arg_18]; lpType
0x18000efd9  mov     [rbp+Data], eax
0x18000efdc  lea     rdx, aPrivacydisable; "PrivacyDisabled"
0x18000efe3  mov     dword ptr [rbp+arg_18], eax
0x18000efe6  xor     r8d, r8d; lpReserved
0x18000efe9  lea     rax, [rbp+cbData]
0x18000efed  mov     [rbp+cbData], edi
0x18000eff0  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18000eff5  lea     rax, [rbp+Data]
0x18000eff9  mov     [rsp+40h+phkResult], rax; lpData
0x18000effe  call    cs:__imp_RegQueryValueExW
0x18000f005  nop     dword ptr [rax+rax+00h]
0x18000f00a  test    eax, eax
0x18000f00c  jnz     short loc_18000F016
0x18000f00e  xor     ecx, ecx
0x18000f010  cmp     [rbp+Data], ecx
0x18000f013  cmovnz  ebx, ecx
0x18000f016  mov     rcx, [rbp+hKey]; hKey
0x18000f01a  call    cs:__imp_RegCloseKey
0x18000f021  nop     dword ptr [rax+rax+00h]
0x18000f026  mov     eax, ebx
0x18000f028  mov     rbx, [rsp+40h+arg_0]
0x18000f02d  add     rsp, 40h
0x18000f031  pop     r14
0x18000f033  pop     rdi
0x18000f034  pop     rbp
0x18000f035  retn
```
