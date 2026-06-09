# DhcpCreateAdapterKey

- ea: `0x180035ef4`
- end: `0x180036000`
- name: `DhcpCreateAdapterKey`
- size: `268`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001f148`
- `0x1800227ac`

## callees

- `0x180035ef4`
- `0x18004d200`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fe8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035fe8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180035f78`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180035f78`

## pseudocode

```c
__int64 __fastcall DhcpCreateAdapterKey(LPCWSTR lpSubKey, HKEY *a2)
{
  unsigned int v4; // edi
  bool v5; // zf
  DWORD dwDisposition; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  dwDisposition = 0;
  hKey = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_S(1028, 34, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, lpSubKey);
  v4 = RegCreateKeyExW(DhcpGlobalInterfacesKey, lpSubKey, 0, 0, 0, 0xFu, 0, &hKey, &dwDisposition);
  if ( !v4 )
  {
    v5 = dwDisposition == 2;
    *a2 = hKey;
    hKey = 0;
    if ( v5 )
    {
      if ( (xmmword_1800616A0 & 0x10) == 0 )
        goto LABEL_9;
      WPP_SF_S(1028, 35, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, lpSubKey);
    }
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_S(1028, 36, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, lpSubKey);
  }
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x180035ef4  mov     rax, rsp
0x180035ef7  mov     [rax+8], rbx
0x180035efb  mov     [rax+10h], rsi
0x180035eff  push    rdi
0x180035f00  sub     rsp, 50h
0x180035f04  mov     rsi, rdx
0x180035f07  mov     dword ptr [rax+18h], 0
0x180035f0e  mov     rbx, rcx
0x180035f11  mov     qword ptr [rax+20h], 0
0x180035f19  test    byte ptr cs:xmmword_1800616A0, 10h
0x180035f20  jz      short loc_180035F3B
0x180035f22  mov     edx, 22h ; '"'
0x180035f27  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180035f2e  mov     ecx, 404h
0x180035f33  mov     r9, rbx
0x180035f36  call    WPP_SF_S
0x180035f3b  mov     rcx, cs:DhcpGlobalInterfacesKey; hKey
0x180035f42  lea     rax, [rsp+58h+dwDisposition]
0x180035f47  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x180035f4c  xor     r9d, r9d; lpClass
0x180035f4f  lea     rax, [rsp+58h+hKey]
0x180035f54  xor     r8d, r8d; Reserved
0x180035f57  mov     [rsp+58h+phkResult], rax; phkResult
0x180035f5c  mov     rdx, rbx; lpSubKey
0x180035f5f  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180035f68  mov     [rsp+58h+samDesired], 0Fh; samDesired
0x180035f70  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180035f78  call    cs:__imp_RegCreateKeyExW
0x180035f7e  mov     edi, eax
0x180035f80  test    eax, eax
0x180035f82  jnz     short loc_180035FDE
0x180035f84  cmp     [rsp+58h+dwDisposition], 2
0x180035f89  mov     rcx, [rsp+58h+hKey]
0x180035f8e  mov     [rsi], rcx
0x180035f91  mov     [rsp+58h+hKey], 0
0x180035f9a  jnz     short loc_180035FBC
0x180035f9c  test    byte ptr cs:xmmword_1800616A0, 10h
0x180035fa3  jz      short loc_180035FDE
0x180035fa5  lea     edx, [rax+23h]
0x180035fa8  mov     ecx, 404h
0x180035fad  mov     r9, rbx
0x180035fb0  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180035fb7  call    WPP_SF_S
0x180035fbc  test    byte ptr cs:xmmword_1800616A0, 10h
0x180035fc3  jz      short loc_180035FDE
0x180035fc5  mov     edx, 24h ; '$'
0x180035fca  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180035fd1  mov     ecx, 404h
0x180035fd6  mov     r9, rbx
0x180035fd9  call    WPP_SF_S
0x180035fde  mov     rcx, [rsp+58h+hKey]; hKey
0x180035fe3  test    rcx, rcx
0x180035fe6  jz      short loc_180035FEE
0x180035fe8  call    cs:__imp_RegCloseKey
0x180035fee  mov     rbx, [rsp+58h+arg_0]
0x180035ff3  mov     eax, edi
0x180035ff5  mov     rsi, [rsp+58h+arg_8]
0x180035ffa  add     rsp, 50h
0x180035ffe  pop     rdi
0x180035fff  retn
```
