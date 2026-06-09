# Dhcpv6ReadUseOfWakeUpPattern

- ea: `0x180008e50`
- end: `0x180008f79`
- name: `Dhcpv6ReadUseOfWakeUpPattern`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18001b808`

## callees

- `0x180008e50`
- `0x180009f58`
- `0x1800338c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ea9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008ea9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008ee6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008ee6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008f2f`

## string_xrefs

- `0x180008e7e`: `System\CurrentControlSet\Services\Dhcp\Parametersv6`

## pseudocode

```c
_BOOL8 __fastcall Dhcpv6ReadUseOfWakeUpPattern(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int IsWCOSSystem; // eax
  const WCHAR *v5; // rdx
  unsigned int v6; // ebx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+58h] [rbp+20h] BYREF
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  cbData = 0;
  Type = 0;
  Data = 0;
  hKey = 0;
  IsWCOSSystem = DhcpIsWCOSSystem(a1, a2, a3, a4);
  v5 = L"OSDATA\\Networking\\Dhcp\\Client6\\Parameters";
  if ( !IsWCOSSystem )
    v5 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parametersv6";
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 1u, &hKey);
  if ( !v6 )
  {
    cbData = 4;
    v6 = RegQueryValueExW(hKey, L"Dhcpv6UseWakeUpPattern", 0, &Type, (LPBYTE)&Data, &cbData);
    if ( !v6 )
    {
      if ( Type == 4 )
      {
        if ( (xmmword_1800423E0 & 0x10) != 0 )
          WPP_SF_D(1028, 103, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, Data);
      }
      else
      {
        v6 = 87;
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v6 && (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_D(1025, 104, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v6);
  return Data != 0;
}

```

## disassembly

```asm
0x180008e50  push    rbp
0x180008e52  push    rbx
0x180008e53  mov     rbp, rsp
0x180008e56  sub     rsp, 38h
0x180008e5a  mov     [rbp+cbData], 0
0x180008e61  mov     [rbp+Type], 0
0x180008e68  mov     [rbp+Data], 0
0x180008e6f  mov     [rbp+hKey], 0
0x180008e77  call    DhcpIsWCOSSystem
0x180008e7c  test    eax, eax
0x180008e7e  lea     rcx, SubKey; "System\\CurrentControlSet\\Services\\Dh"...
0x180008e85  lea     rax, [rbp+hKey]
0x180008e89  mov     r9d, 1; samDesired
0x180008e8f  lea     rdx, aOsdataNetworki_3; "OSDATA\\Networking\\Dhcp\\Client6\\Para"...
0x180008e96  mov     [rsp+38h+phkResult], rax; phkResult
0x180008e9b  cmovz   rdx, rcx; lpSubKey
0x180008e9f  xor     r8d, r8d; ulOptions
0x180008ea2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008ea9  call    cs:__imp_RegOpenKeyExW
0x180008eb0  nop     dword ptr [rax+rax+00h]
0x180008eb5  mov     ebx, eax
0x180008eb7  test    eax, eax
0x180008eb9  jnz     short loc_180008F26
0x180008ebb  mov     rcx, [rbp+hKey]; hKey
0x180008ebf  lea     rax, [rbp+cbData]
0x180008ec3  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180008ec8  lea     r9, [rbp+Type]; lpType
0x180008ecc  lea     rax, [rbp+Data]
0x180008ed0  mov     [rbp+cbData], 4
0x180008ed7  xor     r8d, r8d; lpReserved
0x180008eda  mov     [rsp+38h+phkResult], rax; lpData
0x180008edf  lea     rdx, aDhcpv6usewakeu; "Dhcpv6UseWakeUpPattern"
0x180008ee6  call    cs:__imp_RegQueryValueExW
0x180008eed  nop     dword ptr [rax+rax+00h]
0x180008ef2  mov     ebx, eax
0x180008ef4  test    eax, eax
0x180008ef6  jnz     short loc_180008F26
0x180008ef8  cmp     [rbp+Type], 4
0x180008efc  jz      short loc_180008F03
0x180008efe  lea     ebx, [rax+57h]
0x180008f01  jmp     short loc_180008F26
0x180008f03  test    byte ptr cs:xmmword_1800423E0, 10h
0x180008f0a  jz      short loc_180008F26
0x180008f0c  mov     r9d, [rbp+Data]
0x180008f10  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180008f17  mov     edx, 67h ; 'g'
0x180008f1c  mov     ecx, 404h
0x180008f21  call    WPP_SF_D
0x180008f26  mov     rcx, [rbp+hKey]; hKey
0x180008f2a  test    rcx, rcx
0x180008f2d  jz      short loc_180008F43
0x180008f2f  call    cs:__imp_RegCloseKey
0x180008f36  nop     dword ptr [rax+rax+00h]
0x180008f3b  mov     [rbp+hKey], 0
0x180008f43  test    ebx, ebx
0x180008f45  jz      short loc_180008F69
0x180008f47  test    byte ptr cs:xmmword_1800423E0, 2
0x180008f4e  jz      short loc_180008F69
0x180008f50  mov     edx, 68h ; 'h'
0x180008f55  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x180008f5c  mov     ecx, 401h
0x180008f61  mov     r9d, ebx
0x180008f64  call    WPP_SF_D
0x180008f69  xor     eax, eax
0x180008f6b  cmp     [rbp+Data], eax
0x180008f6e  setnz   al
0x180008f71  add     rsp, 38h
0x180008f75  pop     rbx
0x180008f76  pop     rbp
0x180008f77  retn
```
