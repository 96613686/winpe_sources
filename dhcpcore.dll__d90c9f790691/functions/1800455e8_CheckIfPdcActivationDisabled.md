# CheckIfPdcActivationDisabled

- ea: `0x1800455e8`
- end: `0x1800456ea`
- name: `CheckIfPdcActivationDisabled`
- size: `258`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180045a18`

## callees

- `0x1800069d0`
- `0x1800455e8`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800456aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800456aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004565f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004565f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004568d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004568d`

## string_xrefs

- `0x180045634`: `System\CurrentControlSet\Services\Dhcp`

## pseudocode

```c
__int64 CheckIfPdcActivationDisabled()
{
  int IsWCOSSystem; // eax
  const WCHAR *v1; // rdx
  int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Data = 0;
  cbData = 4;
  Type = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 10, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids);
  IsWCOSSystem = DhcpIsWCOSSystem();
  v1 = L"OSDATA\\Networking\\Dhcp\\PDC";
  if ( !IsWCOSSystem )
    v1 = L"System\\CurrentControlSet\\Services\\Dhcp";
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 1u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"PdcActivationDisabled", 0, &Type, (LPBYTE)&Data, &cbData) && Data )
      g_PdcActivationDisabled = 1;
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_d(1028, 11, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids, (unsigned int)g_PdcActivationDisabled);
  return (unsigned int)g_PdcActivationDisabled;
}

```

## disassembly

```asm
0x1800455e8  push    rbp
0x1800455ea  mov     rbp, rsp
0x1800455ed  sub     rsp, 30h
0x1800455f1  mov     [rbp+hKey], 0
0x1800455f9  mov     [rbp+Data], 0
0x180045600  mov     [rbp+cbData], 4
0x180045607  mov     [rbp+Type], 0
0x18004560e  test    byte ptr cs:xmmword_1800616A0, 10h
0x180045615  jz      short loc_18004562D
0x180045617  mov     edx, 0Ah
0x18004561c  lea     r8, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids
0x180045623  mov     ecx, 404h
0x180045628  call    WPP_SF_
0x18004562d  call    DhcpIsWCOSSystem
0x180045632  test    eax, eax
0x180045634  lea     rcx, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\Dh"...
0x18004563b  lea     rax, [rbp+hKey]
0x18004563f  mov     r9d, 1; samDesired
0x180045645  lea     rdx, aOsdataNetworki_6; "OSDATA\\Networking\\Dhcp\\PDC"
0x18004564c  mov     [rsp+30h+phkResult], rax; phkResult
0x180045651  cmovz   rdx, rcx; lpSubKey
0x180045655  xor     r8d, r8d; ulOptions
0x180045658  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004565f  call    cs:__imp_RegOpenKeyExW
0x180045665  test    eax, eax
0x180045667  jnz     short loc_1800456B8
0x180045669  mov     rcx, [rbp+hKey]; hKey
0x18004566d  lea     rax, [rbp+cbData]
0x180045671  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180045676  lea     r9, [rbp+Type]; lpType
0x18004567a  lea     rax, [rbp+Data]
0x18004567e  xor     r8d, r8d; lpReserved
0x180045681  lea     rdx, aPdcactivationd; "PdcActivationDisabled"
0x180045688  mov     [rsp+30h+phkResult], rax; lpData
0x18004568d  call    cs:__imp_RegQueryValueExW
0x180045693  test    eax, eax
0x180045695  jnz     short loc_1800456A6
0x180045697  cmp     [rbp+Data], eax
0x18004569a  jz      short loc_1800456A6
0x18004569c  mov     cs:g_PdcActivationDisabled, 1
0x1800456a6  mov     rcx, [rbp+hKey]; hKey
0x1800456aa  call    cs:__imp_RegCloseKey
0x1800456b0  mov     [rbp+hKey], 0
0x1800456b8  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800456bf  jz      short loc_1800456DE
0x1800456c1  mov     r9d, cs:g_PdcActivationDisabled
0x1800456c8  lea     r8, WPP_3a6d8de5f5ca3c9cb70177d699ebe6ea_Traceguids
0x1800456cf  mov     edx, 0Bh
0x1800456d4  mov     ecx, 404h
0x1800456d9  call    WPP_SF_d
0x1800456de  mov     eax, cs:g_PdcActivationDisabled
0x1800456e4  add     rsp, 30h
0x1800456e8  pop     rbp
0x1800456e9  retn
```
