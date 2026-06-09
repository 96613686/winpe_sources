# SetDomainSearchListRegKey

- ea: `0x180035504`
- end: `0x1800355d5`
- name: `SetDomainSearchListRegKey`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e870`

## callees

- `0x180035504`
- `0x18004d1a0`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800355a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800355a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035559`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035559`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18003558e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x18003558e`

## pseudocode

```c
__int64 __fastcall SetDomainSearchListRegKey(__int64 a1)
{
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 251, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, *(_QWORD *)(a1 + 24));
  v2 = RegOpenKeyExW(*(HKEY *)(a1 + 728), 0, 0, 0xFu, &hKey);
  if ( !v2 )
    v2 = RegSetValueExA(hKey, "DhcpDomainSearchList", 0, 1u, *(const BYTE **)(a1 + 2032), *(_DWORD *)(a1 + 2040));
  if ( hKey )
    RegCloseKey(hKey);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 252, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180035504  mov     [rsp+arg_8], rbx
0x180035509  push    rdi
0x18003550a  sub     rsp, 30h
0x18003550e  mov     rdi, rcx
0x180035511  mov     [rsp+38h+hKey], 0
0x18003551a  test    byte ptr cs:xmmword_1800616A0, 10h
0x180035521  jz      short loc_18003553D
0x180035523  mov     r9, [rdi+18h]
0x180035527  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x18003552e  mov     edx, 0FBh
0x180035533  mov     ecx, 404h
0x180035538  call    WPP_SF_q
0x18003553d  mov     rcx, [rdi+2D8h]; hKey
0x180035544  lea     rax, [rsp+38h+hKey]
0x180035549  mov     r9d, 0Fh; samDesired
0x18003554f  mov     [rsp+38h+phkResult], rax; phkResult
0x180035554  xor     r8d, r8d; ulOptions
0x180035557  xor     edx, edx; lpSubKey
0x180035559  call    cs:__imp_RegOpenKeyExW
0x18003555f  mov     ebx, eax
0x180035561  test    eax, eax
0x180035563  jnz     short loc_180035596
0x180035565  mov     eax, [rdi+7F8h]
0x18003556b  lea     r9d, [rbx+1]; dwType
0x18003556f  mov     rcx, [rsp+38h+hKey]; hKey
0x180035574  lea     rdx, aDhcpdomainsear; "DhcpDomainSearchList"
0x18003557b  mov     [rsp+38h+cbData], eax; cbData
0x18003557f  xor     r8d, r8d; Reserved
0x180035582  mov     rax, [rdi+7F0h]
0x180035589  mov     [rsp+38h+phkResult], rax; lpData
0x18003558e  call    cs:__imp_RegSetValueExA
0x180035594  mov     ebx, eax
0x180035596  mov     rcx, [rsp+38h+hKey]; hKey
0x18003559b  test    rcx, rcx
0x18003559e  jz      short loc_1800355A6
0x1800355a0  call    cs:__imp_RegCloseKey
0x1800355a6  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800355ad  jz      short loc_1800355C8
0x1800355af  mov     edx, 0FCh
0x1800355b4  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x1800355bb  mov     ecx, 404h
0x1800355c0  mov     r9d, ebx
0x1800355c3  call    WPP_SF_D
0x1800355c8  mov     eax, ebx
0x1800355ca  mov     rbx, [rsp+38h+arg_8]
0x1800355cf  add     rsp, 30h
0x1800355d3  pop     rdi
0x1800355d4  retn
```
