# IsatapDeleteOrphanedInterfaceKeys

- ea: `0x180059cb8`
- end: `0x180059e6f`
- name: `IsatapDeleteOrphanedInterfaceKeys`
- size: `439`
- prototype: `LSTATUS()`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180032e70`

## callees

- `0x18000d7c0`
- `0x1800190f0`
- `0x180046fec`
- `0x18004b5f0`
- `0x18004c188`
- `0x18004e06c`
- `0x180059cb8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180059dd9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180059dd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059e42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180059e42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059d7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180059d7a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180059e19`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180059e19`
- `IPHLPAPI!ConvertStringToGuidW` at `0x180059df7`
- `IPHLPAPI!ConvertStringToGuidW` at `0x180059df7`

## string_xrefs

- `0x180059e2c`: `RegDeleteTree returned error %d`
- `0x180059d42`: `Failed to get protocol key name for ISATAP: 0x%x`
- `0x180059d8a`: `IsatapDeleteOrphanedInterfaceKeys failed to open regkey for protocol: %d`

## pseudocode

```c
LSTATUS IsatapDeleteOrphanedInterfaceKeys()
{
  __int64 v0; // rcx
  const wchar_t *v1; // rdx
  __int64 v2; // rcx
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
  if ( (unsigned int)GenerateProtocolKeyName(v0, TransitionKeyNameTable[0], SubKey) )
  {
    v1 = L"Failed to get protocol key name for ISATAP: 0x%x";
    v2 = 0x2000000;
    return EventWriteError0(v2, v1);
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x3001Fu, &hKey) )
  {
    v1 = L"IsatapDeleteOrphanedInterfaceKeys failed to open regkey for protocol: %d";
    v2 = 0x800000;
    return EventWriteError0(v2, v1);
  }
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
0x180059cb8  mov     [rsp-8+arg_0], rbx
0x180059cbd  push    rbp
0x180059cbe  lea     rbp, [rsp-390h]
0x180059cc6  sub     rsp, 490h
0x180059ccd  mov     rax, cs:__security_cookie
0x180059cd4  xor     rax, rsp
0x180059cd7  mov     [rbp+390h+var_10], rax
0x180059cde  mov     ebx, 20Ah
0x180059ce3  lea     rcx, [rbp+390h+Name]; void *
0x180059cea  mov     r8d, ebx; Size
0x180059ced  xor     edx, edx; Val
0x180059cef  call    memset_0
0x180059cf4  mov     r8d, ebx; Size
0x180059cf7  mov     [rsp+490h+cchName], 105h
0x180059cff  xor     edx, edx; Val
0x180059d01  lea     rcx, [rsp+490h+SubKey]; void *
0x180059d06  call    memset_0
0x180059d0b  xorps   xmm0, xmm0
0x180059d0e  mov     [rsp+490h+hKey], 0
0x180059d17  lea     rdx, aDeletingOrphan; "Deleting orphan interfaces and reg keys"...
0x180059d1e  mov     ecx, 2000000h
0x180059d23  movups  [rsp+490h+var_440], xmm0
0x180059d28  call    EventWrite0
0x180059d2d  mov     rdx, cs:TransitionKeyNameTable
0x180059d34  lea     r8, [rsp+490h+SubKey]
0x180059d39  call    GenerateProtocolKeyName
0x180059d3e  test    eax, eax
0x180059d40  jz      short loc_180059D5B
0x180059d42  lea     rdx, aFailedToGetPro_0; "Failed to get protocol key name for ISA"...
0x180059d49  mov     ecx, 2000000h
0x180059d4e  mov     r8d, eax
0x180059d51  call    EventWriteError0
0x180059d56  jmp     loc_180059E4E
0x180059d5b  lea     rax, [rsp+490h+hKey]
0x180059d60  mov     r9d, 3001Fh; samDesired
0x180059d66  xor     r8d, r8d; ulOptions
0x180059d69  mov     [rsp+490h+phkResult], rax; phkResult
0x180059d6e  lea     rdx, [rsp+490h+SubKey]; lpSubKey
0x180059d73  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180059d7a  call    cs:__imp_RegOpenKeyExW
0x180059d81  nop     dword ptr [rax+rax+00h]
0x180059d86  test    eax, eax
0x180059d88  jz      short loc_180059D98
0x180059d8a  lea     rdx, aIsatapdeleteor; "IsatapDeleteOrphanedInterfaceKeys faile"...
0x180059d91  mov     ecx, 800000h
0x180059d96  jmp     short loc_180059D4E
0x180059d98  xor     ebx, ebx
0x180059d9a  mov     rcx, [rsp+490h+hKey]; hKey
0x180059d9f  lea     r9, [rsp+490h+cchName]; lpcchName
0x180059da4  mov     [rsp+490h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180059dad  lea     r8, [rbp+390h+Name]; lpName
0x180059db4  mov     [rsp+490h+lpcchClass], 0; lpcchClass
0x180059dbd  mov     edx, ebx; dwIndex
0x180059dbf  mov     [rsp+490h+lpClass], 0; lpClass
0x180059dc8  mov     [rsp+490h+phkResult], 0; lpReserved
0x180059dd1  mov     [rsp+490h+cchName], 105h
0x180059dd9  call    cs:__imp_RegEnumKeyExW
0x180059de0  nop     dword ptr [rax+rax+00h]
0x180059de5  test    eax, eax
0x180059de7  jnz     short loc_180059E0F
0x180059de9  lea     rdx, [rsp+490h+var_440]
0x180059dee  inc     ebx
0x180059df0  lea     rcx, [rbp+390h+Name]
0x180059df7  call    cs:__imp_ConvertStringToGuidW
0x180059dfe  nop     dword ptr [rax+rax+00h]
0x180059e03  lea     rcx, [rsp+490h+var_440]
0x180059e08  call    UninstallTunnelInterface
0x180059e0d  jmp     short loc_180059D9A
0x180059e0f  mov     rcx, [rsp+490h+hKey]; hKey
0x180059e14  lea     rdx, [rsp+490h+SubKey]; lpSubKey
0x180059e19  call    cs:__imp_RegDeleteTreeW
0x180059e20  nop     dword ptr [rax+rax+00h]
0x180059e25  test    eax, eax
0x180059e27  jz      short loc_180059E3D
0x180059e29  mov     r8d, eax
0x180059e2c  lea     rdx, aRegdeletetreeR; "RegDeleteTree returned error %d"
0x180059e33  mov     ecx, 2000000h
0x180059e38  call    EventWriteError0
0x180059e3d  mov     rcx, [rsp+490h+hKey]; hKey
0x180059e42  call    cs:__imp_RegCloseKey
0x180059e49  nop     dword ptr [rax+rax+00h]
0x180059e4e  mov     rcx, [rbp+390h+var_10]
0x180059e55  xor     rcx, rsp; StackCookie
0x180059e58  call    __security_check_cookie
0x180059e5d  mov     rbx, [rsp+490h+arg_0]
0x180059e65  add     rsp, 490h
0x180059e6c  pop     rbp
0x180059e6d  retn
```
