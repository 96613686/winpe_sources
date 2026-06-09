# SetRegistryClassIdBin

- ea: `0x18000ece4`
- end: `0x18000ed7f`
- name: `SetRegistryClassIdBin`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18000eb30`

## callees

- `0x180002c00`
- `0x18000ece4`
- `0x18000fc0c`
- `0x18001259c`
- `0x180012a00`

## string_xrefs

- `0x18000ed2c`: `System\CurrentControlSet\Services\Dhcp\Parameters\DhcpClientClassLocation`

## pseudocode

```c
__int64 __fastcall SetRegistryClassIdBin(__int64 a1, const BYTE *a2, DWORD a3)
{
  int v5; // esi
  int IsWCOSSystem; // eax
  wchar_t *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // ebx

  v5 = a1;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_Sqd(a1, 14, (unsigned int)WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, a1, (char)a2, a3);
  IsWCOSSystem = DhcpIsWCOSSystem(a1);
  v7 = L"OSDATA\\Networking\\Dhcp\\Client4\\DhcpClientClassLocation";
  if ( !IsWCOSSystem )
    v7 = L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\DhcpClientClassLocation";
  v8 = SetClassIdForLocation(
         v7,
         (__int64)L"System\\CurrentControlSet\\Services\\Dhcp\\Parameters\\DhcpClientClassLocation",
         v5,
         a2,
         a3);
  v9 = v8;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 15, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids, v8);
  return v9;
}

```

## disassembly

```asm
0x18000ece4  mov     rax, rsp
0x18000ece7  mov     [rax+8], rbx
0x18000eceb  mov     [rax+10h], rsi
0x18000ecef  push    rdi
0x18000ecf0  sub     rsp, 30h
0x18000ecf4  mov     ebx, r8d
0x18000ecf7  mov     rdi, rdx
0x18000ecfa  mov     rsi, rcx
0x18000ecfd  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000ed04  jz      short loc_18000ED21
0x18000ed06  mov     [rax-10h], ebx
0x18000ed09  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x18000ed10  mov     edx, 0Eh
0x18000ed15  mov     [rax-18h], rdi
0x18000ed19  mov     r9, rcx
0x18000ed1c  call    WPP_SF_Sqd
0x18000ed21  call    DhcpIsWCOSSystem
0x18000ed26  test    eax, eax
0x18000ed28  mov     [rsp+38h+var_18], ebx; DWORD
0x18000ed2c  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\Dh"...
0x18000ed33  mov     r9, rdi
0x18000ed36  lea     rcx, aOsdataNetworki_0; "OSDATA\\Networking\\Dhcp\\Client4\\Dhcp"...
0x18000ed3d  mov     r8, rsi
0x18000ed40  cmovz   rcx, rdx; Src
0x18000ed44  call    SetClassIdForLocation
0x18000ed49  mov     ebx, eax
0x18000ed4b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000ed52  jz      short loc_18000ED6D
0x18000ed54  mov     edx, 0Fh
0x18000ed59  lea     r8, WPP_951d1d083d403a6b63dfdf4ae01534a1_Traceguids
0x18000ed60  mov     ecx, 404h
0x18000ed65  mov     r9d, eax
0x18000ed68  call    WPP_SF_d
0x18000ed6d  mov     rsi, [rsp+38h+arg_8]
0x18000ed72  mov     eax, ebx
0x18000ed74  mov     rbx, [rsp+38h+arg_0]
0x18000ed79  add     rsp, 30h
0x18000ed7d  pop     rdi
0x18000ed7e  retn
```
