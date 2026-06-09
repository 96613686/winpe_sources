# Dhcpv6CopyToCurrentContext

- ea: `0x18000e848`
- end: `0x18000e94a`
- name: `Dhcpv6CopyToCurrentContext`
- size: `258`
- prototype: `__int64 __fastcall(__int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011e04`

## callees

- `0x18000e848`
- `0x18000e950`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e890`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e890`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000e905`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000e905`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e8e0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e8e0`

## pseudocode

```c
__int64 __fastcall Dhcpv6CopyToCurrentContext(__int64 a1, const WCHAR *a2)
{
  unsigned int v4; // ebx
  HKEY v6; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( a1 && a2 )
  {
    v4 = RegOpenKeyExW(*(HKEY *)(a1 + 648), a2, 0, 0xFu, &hKey);
    if ( v4 )
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(1028, 100, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
    }
    else if ( hKey )
    {
      DhcpRegCopy(hKey, *(HKEY *)(a1 + 648));
      RegCloseKey(hKey);
      v6 = *(HKEY *)(a1 + 648);
      hKey = 0;
      return (unsigned int)RegDeleteKeyExW(v6, a2, 0, 0);
    }
    return v4;
  }
  else
  {
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_(1028, 99, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
    return 87;
  }
}

```

## disassembly

```asm
0x18000e848  mov     r11, rsp
0x18000e84b  mov     [r11+10h], rbx
0x18000e84f  mov     [r11+18h], rsi
0x18000e853  push    rdi
0x18000e854  sub     rsp, 30h
0x18000e858  mov     qword ptr [r11+8], 0
0x18000e860  mov     rsi, rdx
0x18000e863  mov     rdi, rcx
0x18000e866  test    rcx, rcx
0x18000e869  jz      loc_18000E915
0x18000e86f  test    rdx, rdx
0x18000e872  jz      loc_18000E915
0x18000e878  mov     rcx, [rcx+288h]; hKey
0x18000e87f  lea     rax, [r11+8]
0x18000e883  mov     r9d, 0Fh; samDesired
0x18000e889  mov     [r11-18h], rax
0x18000e88d  xor     r8d, r8d; ulOptions
0x18000e890  call    cs:__imp_RegOpenKeyExW
0x18000e897  nop     dword ptr [rax+rax+00h]
0x18000e89c  mov     ebx, eax
0x18000e89e  test    eax, eax
0x18000e8a0  jz      short loc_18000E8C5
0x18000e8a2  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000e8a9  jz      short loc_18000E8C1
0x18000e8ab  mov     edx, 64h ; 'd'
0x18000e8b0  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000e8b7  mov     ecx, 404h
0x18000e8bc  call    WPP_SF_
0x18000e8c1  mov     eax, ebx
0x18000e8c3  jmp     short loc_18000E939
0x18000e8c5  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e8ca  test    rcx, rcx
0x18000e8cd  jz      short loc_18000E8C1
0x18000e8cf  mov     rdx, [rdi+288h]; HKEY
0x18000e8d6  call    DhcpRegCopy
0x18000e8db  mov     rcx, [rsp+38h+hKey]; hKey
0x18000e8e0  call    cs:__imp_RegCloseKey
0x18000e8e7  nop     dword ptr [rax+rax+00h]
0x18000e8ec  mov     rcx, [rdi+288h]; hKey
0x18000e8f3  xor     r9d, r9d; Reserved
0x18000e8f6  xor     r8d, r8d; samDesired
0x18000e8f9  mov     [rsp+38h+hKey], 0
0x18000e902  mov     rdx, rsi; lpSubKey
0x18000e905  call    cs:__imp_RegDeleteKeyExW
0x18000e90c  nop     dword ptr [rax+rax+00h]
0x18000e911  mov     ebx, eax
0x18000e913  jmp     short loc_18000E8C1
0x18000e915  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000e91c  jz      short loc_18000E934
0x18000e91e  mov     edx, 63h ; 'c'
0x18000e923  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000e92a  mov     ecx, 404h
0x18000e92f  call    WPP_SF_
0x18000e934  mov     eax, 57h ; 'W'
0x18000e939  mov     rbx, [rsp+38h+arg_8]
0x18000e93e  mov     rsi, [rsp+38h+arg_10]
0x18000e943  add     rsp, 30h
0x18000e947  pop     rdi
0x18000e948  retn
```
