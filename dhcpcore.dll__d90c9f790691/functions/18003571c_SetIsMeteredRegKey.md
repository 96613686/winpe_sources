# SetIsMeteredRegKey

- ea: `0x18003571c`
- end: `0x1800357e6`
- name: `SetIsMeteredRegKey`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001e870`

## callees

- `0x18003571c`
- `0x18004d1a0`
- `0x18004d4c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800357b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800357b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035771`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035771`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800357a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800357a1`

## pseudocode

```c
LSTATUS __fastcall SetIsMeteredRegKey(__int64 a1)
{
  LSTATUS result; // eax
  unsigned int v3; // edi
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  hKey = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 249, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, *(_QWORD *)(a1 + 24));
  result = RegOpenKeyExW(*(HKEY *)(a1 + 728), 0, 0, 0xFu, &hKey);
  v3 = result;
  if ( !result )
  {
    result = RegSetValueExW(hKey, L"DhcpIsMeteredDetected", 0, 4u, (const BYTE *)(a1 + 580), 4u);
    v3 = result;
  }
  if ( hKey )
    result = RegCloseKey(hKey);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    return WPP_SF_D(1028, 250, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids, v3);
  return result;
}

```

## disassembly

```asm
0x18003571c  mov     [rsp+arg_8], rbx
0x180035721  push    rdi
0x180035722  sub     rsp, 30h
0x180035726  mov     rbx, rcx
0x180035729  mov     [rsp+38h+hKey], 0
0x180035732  test    byte ptr cs:xmmword_1800616A0, 10h
0x180035739  jz      short loc_180035755
0x18003573b  mov     r9, [rbx+18h]
0x18003573f  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x180035746  mov     edx, 0F9h
0x18003574b  mov     ecx, 404h
0x180035750  call    WPP_SF_q
0x180035755  mov     rcx, [rbx+2D8h]; hKey
0x18003575c  lea     rax, [rsp+38h+hKey]
0x180035761  mov     r9d, 0Fh; samDesired
0x180035767  mov     [rsp+38h+phkResult], rax; phkResult
0x18003576c  xor     r8d, r8d; ulOptions
0x18003576f  xor     edx, edx; lpSubKey
0x180035771  call    cs:__imp_RegOpenKeyExW
0x180035777  mov     edi, eax
0x180035779  test    eax, eax
0x18003577b  jnz     short loc_1800357A9
0x18003577d  mov     rcx, [rsp+38h+hKey]; hKey
0x180035782  lea     r9d, [rdi+4]; dwType
0x180035786  lea     rax, [rbx+244h]
0x18003578d  mov     [rsp+38h+cbData], r9d; cbData
0x180035792  xor     r8d, r8d; Reserved
0x180035795  mov     [rsp+38h+phkResult], rax; lpData
0x18003579a  lea     rdx, aDhcpismeteredd; "DhcpIsMeteredDetected"
0x1800357a1  call    cs:__imp_RegSetValueExW
0x1800357a7  mov     edi, eax
0x1800357a9  mov     rcx, [rsp+38h+hKey]; hKey
0x1800357ae  test    rcx, rcx
0x1800357b1  jz      short loc_1800357B9
0x1800357b3  call    cs:__imp_RegCloseKey
0x1800357b9  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800357c0  jz      short loc_1800357DB
0x1800357c2  mov     edx, 0FAh
0x1800357c7  lea     r8, WPP_10d83c82f39f3ab0ef793de6931aab9d_Traceguids
0x1800357ce  mov     ecx, 404h
0x1800357d3  mov     r9d, edi
0x1800357d6  call    WPP_SF_D
0x1800357db  mov     rbx, [rsp+38h+arg_8]
0x1800357e0  add     rsp, 30h
0x1800357e4  pop     rdi
0x1800357e5  retn
```
