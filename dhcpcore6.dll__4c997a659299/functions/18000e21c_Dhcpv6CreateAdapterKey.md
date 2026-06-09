# Dhcpv6CreateAdapterKey

- ea: `0x18000e21c`
- end: `0x18000e31d`
- name: `Dhcpv6CreateAdapterKey`
- size: `257`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800152b8`

## callees

- `0x18000e21c`
- `0x1800337d0`
- `0x1800338c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e28e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000e28e`

## pseudocode

```c
__int64 __fastcall Dhcpv6CreateAdapterKey(LPCWSTR lpSubKey, PHKEY phkResult)
{
  unsigned int v4; // eax
  unsigned int v5; // edi
  DWORD dwDisposition; // [rsp+70h] [rbp+18h] BYREF

  dwDisposition = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 30, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, lpSubKey);
  v4 = RegCreateKeyExW(Dhcpv6GlobalInterfacesKey, lpSubKey, 0, 0, 0, 0xFu, 0, phkResult, &dwDisposition);
  v5 = v4;
  if ( v4 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_D(1025, 33, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v4);
  }
  else
  {
    if ( dwDisposition == 2 )
    {
      if ( (xmmword_1800423E0 & 0x10) == 0 )
        return v5;
      WPP_SF_S(1028, 31, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, lpSubKey);
    }
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_S(1028, 32, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, lpSubKey);
  }
  return v5;
}

```

## disassembly

```asm
0x18000e21c  mov     [rsp+arg_0], rbx
0x18000e221  push    rdi
0x18000e222  sub     rsp, 50h
0x18000e226  mov     rdi, rdx
0x18000e229  mov     [rsp+58h+dwDisposition], 0
0x18000e231  mov     rbx, rcx
0x18000e234  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000e23b  jz      short loc_18000E256
0x18000e23d  mov     edx, 1Eh
0x18000e242  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000e249  mov     ecx, 404h
0x18000e24e  mov     r9, rbx
0x18000e251  call    WPP_SF_S
0x18000e256  mov     rcx, cs:Dhcpv6GlobalInterfacesKey; hKey
0x18000e25d  lea     rax, [rsp+58h+dwDisposition]
0x18000e262  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18000e267  xor     r9d, r9d; lpClass
0x18000e26a  mov     [rsp+58h+phkResult], rdi; phkResult
0x18000e26f  xor     r8d, r8d; Reserved
0x18000e272  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000e27b  mov     rdx, rbx; lpSubKey
0x18000e27e  mov     [rsp+58h+samDesired], 0Fh; samDesired
0x18000e286  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18000e28e  call    cs:__imp_RegCreateKeyExW
0x18000e295  nop     dword ptr [rax+rax+00h]
0x18000e29a  mov     edi, eax
0x18000e29c  test    eax, eax
0x18000e29e  jnz     short loc_18000E2F9
0x18000e2a0  cmp     [rsp+58h+dwDisposition], 2
0x18000e2a5  jnz     short loc_18000E2C7
0x18000e2a7  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000e2ae  jz      short loc_18000E2D0
0x18000e2b0  lea     edx, [rax+1Fh]
0x18000e2b3  mov     ecx, 404h
0x18000e2b8  mov     r9, rbx
0x18000e2bb  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000e2c2  call    WPP_SF_S
0x18000e2c7  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000e2ce  jnz     short loc_18000E2DE
0x18000e2d0  mov     rbx, [rsp+58h+arg_0]
0x18000e2d5  mov     eax, edi
0x18000e2d7  add     rsp, 50h
0x18000e2db  pop     rdi
0x18000e2dc  retn
0x18000e2de  mov     edx, 20h ; ' '
0x18000e2e3  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000e2ea  mov     ecx, 404h
0x18000e2ef  mov     r9, rbx
0x18000e2f2  call    WPP_SF_S
0x18000e2f7  jmp     short loc_18000E2D0
0x18000e2f9  test    byte ptr cs:xmmword_1800423E0, 2
0x18000e300  jz      short loc_18000E2D0
0x18000e302  mov     edx, 21h ; '!'
0x18000e307  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000e30e  mov     ecx, 401h
0x18000e313  mov     r9d, edi
0x18000e316  call    WPP_SF_D
0x18000e31b  jmp     short loc_18000E2D0
```
