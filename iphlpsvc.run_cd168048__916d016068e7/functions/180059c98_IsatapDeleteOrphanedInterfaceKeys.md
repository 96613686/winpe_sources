# IsatapDeleteOrphanedInterfaceKeys

- ea: `0x180059c98`
- end: `0x180059e4f`
- name: `IsatapDeleteOrphanedInterfaceKeys`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180032e60`

## callees

- `0x18000d7b0`
- `0x1800190e0`
- `0x18004702c`
- `0x18004b630`
- `0x18004c1c8`
- `0x18004e0ac`
- `0x180059c98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180059db9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180059db9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059e22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059e22`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059d5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059d5a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180059df9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180059df9`
- `IPHLPAPI!ConvertStringToGuidW` at `0x180059dd7`
- `IPHLPAPI!ConvertStringToGuidW` at `0x180059dd7`

## string_xrefs

- `0x180059e0c`: `RegDeleteTree returned error %d`
- `0x180059d22`: `Failed to get protocol key name for ISATAP: 0x%x`
- `0x180059d6a`: `IsatapDeleteOrphanedInterfaceKeys failed to open regkey for protocol: %d`

## pseudocode

```c
LSTATUS IsatapDeleteOrphanedInterfaceKeys()
{
  __int64 v0; // rcx
  unsigned int ProtocolKeyName; // eax
  unsigned int v3; // eax
  DWORD i; // ebx
  unsigned int v5; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v8; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+270h] [rbp+170h] BYREF

  memset_0(Name, 0, 0x20Au);
  cchName = 261;
  memset_0(SubKey, 0, 0x20Au);
  hKey = 0;
  v8 = 0;
  EventWrite0(0x2000000, L"Deleting orphan interfaces and reg keys...");
  ProtocolKeyName = GenerateProtocolKeyName(v0, TransitionKeyNameTable[0], SubKey);
  if ( ProtocolKeyName )
    return EventWriteError0(0x2000000, L"Failed to get protocol key name for ISATAP: 0x%x", ProtocolKeyName);
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x3001Fu, &hKey);
  if ( v3 )
    return EventWriteError0(0x800000, L"IsatapDeleteOrphanedInterfaceKeys failed to open regkey for protocol: %d", v3);
  for ( i = 0; ; ++i )
  {
    cchName = 261;
    if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
      break;
    ConvertStringToGuidW(Name, &v8);
    UninstallTunnelInterface(&v8);
  }
  v5 = RegDeleteTreeW(hKey, SubKey);
  if ( v5 )
    EventWriteError0(0x2000000, L"RegDeleteTree returned error %d", v5);
  return RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180059c98  mov     [rsp-8+arg_0], rbx
0x180059c9d  push    rbp
0x180059c9e  lea     rbp, [rsp-390h]
0x180059ca6  sub     rsp, 490h
0x180059cad  mov     rax, cs:__security_cookie
0x180059cb4  xor     rax, rsp
0x180059cb7  mov     [rbp+390h+var_10], rax
0x180059cbe  mov     ebx, 20Ah
0x180059cc3  lea     rcx, [rbp+390h+Name]; void *
0x180059cca  mov     r8d, ebx; Size
0x180059ccd  xor     edx, edx; Val
0x180059ccf  call    memset_0
0x180059cd4  mov     r8d, ebx; Size
0x180059cd7  mov     [rsp+490h+cchName], 105h
0x180059cdf  xor     edx, edx; Val
0x180059ce1  lea     rcx, [rsp+490h+SubKey]; void *
0x180059ce6  call    memset_0
0x180059ceb  xorps   xmm0, xmm0
0x180059cee  mov     [rsp+490h+hKey], 0
0x180059cf7  lea     rdx, aDeletingOrphan; "Deleting orphan interfaces and reg keys"...
0x180059cfe  mov     ecx, 2000000h
0x180059d03  movups  [rsp+490h+var_440], xmm0
0x180059d08  call    EventWrite0
0x180059d0d  mov     rdx, cs:TransitionKeyNameTable
0x180059d14  lea     r8, [rsp+490h+SubKey]
0x180059d19  call    GenerateProtocolKeyName
0x180059d1e  test    eax, eax
0x180059d20  jz      short loc_180059D3B
0x180059d22  lea     rdx, aFailedToGetPro_0; "Failed to get protocol key name for ISA"...
0x180059d29  mov     ecx, 2000000h
0x180059d2e  mov     r8d, eax
0x180059d31  call    EventWriteError0
0x180059d36  jmp     loc_180059E2E
0x180059d3b  lea     rax, [rsp+490h+hKey]
0x180059d40  mov     r9d, 3001Fh; samDesired
0x180059d46  xor     r8d, r8d; ulOptions
0x180059d49  mov     [rsp+490h+phkResult], rax; phkResult
0x180059d4e  lea     rdx, [rsp+490h+SubKey]; lpSubKey
0x180059d53  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180059d5a  call    cs:__imp_RegOpenKeyExW
0x180059d61  nop     dword ptr [rax+rax+00h]
0x180059d66  test    eax, eax
0x180059d68  jz      short loc_180059D78
0x180059d6a  lea     rdx, aIsatapdeleteor; "IsatapDeleteOrphanedInterfaceKeys faile"...
0x180059d71  mov     ecx, 800000h
0x180059d76  jmp     short loc_180059D2E
0x180059d78  xor     ebx, ebx
0x180059d7a  mov     rcx, [rsp+490h+hKey]; hKey
0x180059d7f  lea     r9, [rsp+490h+cchName]; lpcchName
0x180059d84  mov     [rsp+490h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180059d8d  lea     r8, [rbp+390h+Name]; lpName
0x180059d94  mov     [rsp+490h+lpcchClass], 0; lpcchClass
0x180059d9d  mov     edx, ebx; dwIndex
0x180059d9f  mov     [rsp+490h+lpClass], 0; lpClass
0x180059da8  mov     [rsp+490h+phkResult], 0; lpReserved
0x180059db1  mov     [rsp+490h+cchName], 105h
0x180059db9  call    cs:__imp_RegEnumKeyExW
0x180059dc0  nop     dword ptr [rax+rax+00h]
0x180059dc5  test    eax, eax
0x180059dc7  jnz     short loc_180059DEF
0x180059dc9  lea     rdx, [rsp+490h+var_440]
0x180059dce  inc     ebx
0x180059dd0  lea     rcx, [rbp+390h+Name]
0x180059dd7  call    cs:__imp_ConvertStringToGuidW
0x180059dde  nop     dword ptr [rax+rax+00h]
0x180059de3  lea     rcx, [rsp+490h+var_440]
0x180059de8  call    UninstallTunnelInterface
0x180059ded  jmp     short loc_180059D7A
0x180059def  mov     rcx, [rsp+490h+hKey]; hKey
0x180059df4  lea     rdx, [rsp+490h+SubKey]; lpSubKey
0x180059df9  call    cs:__imp_RegDeleteTreeW
0x180059e00  nop     dword ptr [rax+rax+00h]
0x180059e05  test    eax, eax
0x180059e07  jz      short loc_180059E1D
0x180059e09  mov     r8d, eax
0x180059e0c  lea     rdx, aRegdeletetreeR; "RegDeleteTree returned error %d"
0x180059e13  mov     ecx, 2000000h
0x180059e18  call    EventWriteError0
0x180059e1d  mov     rcx, [rsp+490h+hKey]; hKey
0x180059e22  call    cs:__imp_RegCloseKey
0x180059e29  nop     dword ptr [rax+rax+00h]
0x180059e2e  mov     rcx, [rbp+390h+var_10]
0x180059e35  xor     rcx, rsp; StackCookie
0x180059e38  call    __security_check_cookie
0x180059e3d  mov     rbx, [rsp+490h+arg_0]
0x180059e45  add     rsp, 490h
0x180059e4c  pop     rbp
0x180059e4d  retn
```
