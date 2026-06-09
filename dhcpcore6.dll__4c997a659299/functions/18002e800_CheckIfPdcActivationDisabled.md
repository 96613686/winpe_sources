# CheckIfPdcActivationDisabled

- ea: `0x18002e800`
- end: `0x18002e915`
- name: `CheckIfPdcActivationDisabled`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18002ecb0`

## callees

- `0x180009f58`
- `0x18002e800`
- `0x180033900`
- `0x180033de4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e877`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e877`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e8ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e8ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e8ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e8ce`

## string_xrefs

- `0x18002e84c`: `System\CurrentControlSet\Services\Dhcp`

## pseudocode

```c
__int64 __fastcall CheckIfPdcActivationDisabled(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int IsWCOSSystem; // eax
  const WCHAR *v5; // rdx
  int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 10, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids);
  IsWCOSSystem = DhcpIsWCOSSystem(a1, a2, a3, a4);
  v5 = L"OSDATA\\Networking\\Dhcp\\PDC";
  if ( !IsWCOSSystem )
    v5 = L"System\\CurrentControlSet\\Services\\Dhcp";
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 1u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"PdcActivationDisabled", 0, &Type, (LPBYTE)&Data, &cbData) && Data )
      g_PdcActivationDisabled = 1;
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_d(1028, 11, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids, (unsigned int)g_PdcActivationDisabled);
  return (unsigned int)g_PdcActivationDisabled;
}

```

## disassembly

```asm
0x18002e800  push    rbp
0x18002e802  mov     rbp, rsp
0x18002e805  sub     rsp, 30h
0x18002e809  mov     [rbp+hKey], 0
0x18002e811  mov     [rbp+Data], 0
0x18002e818  mov     [rbp+cbData], 4
0x18002e81f  mov     [rbp+Type], 0
0x18002e826  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e82d  jz      short loc_18002E845
0x18002e82f  mov     edx, 0Ah
0x18002e834  lea     r8, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids
0x18002e83b  mov     ecx, 404h
0x18002e840  call    WPP_SF_
0x18002e845  call    DhcpIsWCOSSystem
0x18002e84a  test    eax, eax
0x18002e84c  lea     rcx, aSystemCurrentc_12; "System\\CurrentControlSet\\Services\\Dh"...
0x18002e853  lea     rax, [rbp+hKey]
0x18002e857  mov     r9d, 1; samDesired
0x18002e85d  lea     rdx, aOsdataNetworki_4; "OSDATA\\Networking\\Dhcp\\PDC"
0x18002e864  mov     [rsp+30h+phkResult], rax; phkResult
0x18002e869  cmovz   rdx, rcx; lpSubKey
0x18002e86d  xor     r8d, r8d; ulOptions
0x18002e870  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e877  call    cs:__imp_RegOpenKeyExW
0x18002e87e  nop     dword ptr [rax+rax+00h]
0x18002e883  test    eax, eax
0x18002e885  jnz     short loc_18002E8E2
0x18002e887  mov     rcx, [rbp+hKey]; hKey
0x18002e88b  lea     rax, [rbp+cbData]
0x18002e88f  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002e894  lea     r9, [rbp+Type]; lpType
0x18002e898  lea     rax, [rbp+Data]
0x18002e89c  xor     r8d, r8d; lpReserved
0x18002e89f  lea     rdx, aPdcactivationd; "PdcActivationDisabled"
0x18002e8a6  mov     [rsp+30h+phkResult], rax; lpData
0x18002e8ab  call    cs:__imp_RegQueryValueExW
0x18002e8b2  nop     dword ptr [rax+rax+00h]
0x18002e8b7  test    eax, eax
0x18002e8b9  jnz     short loc_18002E8CA
0x18002e8bb  cmp     [rbp+Data], eax
0x18002e8be  jz      short loc_18002E8CA
0x18002e8c0  mov     cs:g_PdcActivationDisabled, 1
0x18002e8ca  mov     rcx, [rbp+hKey]; hKey
0x18002e8ce  call    cs:__imp_RegCloseKey
0x18002e8d5  nop     dword ptr [rax+rax+00h]
0x18002e8da  mov     [rbp+hKey], 0
0x18002e8e2  test    byte ptr cs:xmmword_1800423E0, 10h
0x18002e8e9  jz      short loc_18002E908
0x18002e8eb  mov     r9d, cs:g_PdcActivationDisabled
0x18002e8f2  lea     r8, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids
0x18002e8f9  mov     edx, 0Bh
0x18002e8fe  mov     ecx, 404h
0x18002e903  call    WPP_SF_d
0x18002e908  mov     eax, cs:g_PdcActivationDisabled
0x18002e90e  add     rsp, 30h
0x18002e912  pop     rbp
0x18002e913  retn
```
