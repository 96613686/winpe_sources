# Dhcpv6GenerateAndStoreInterfaceIaid

- ea: `0x18000fca0`
- end: `0x18000fd54`
- name: `Dhcpv6GenerateAndStoreInterfaceIaid`
- size: `180`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014e18`

## callees

- `0x18000fca0`
- `0x1800179c8`
- `0x180031040`
- `0x1800311c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fcdf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000fcdf`

## pseudocode

```c
__int64 __fastcall Dhcpv6GenerateAndStoreInterfaceIaid(__int64 a1)
{
  int v2; // edx
  unsigned int v3; // ebx
  int v4; // r8d
  char v5; // al

  InitializeInterfaceIaid(a1);
  v3 = RegSetValueExW(*(HKEY *)(a1 + 648), L"Dhcpv6Iaid", 0, 4u, (const BYTE *)(a1 + 136), 4u);
  v5 = xmmword_1800423E0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_lSJ(*(_QWORD *)(a1 + 56), v2, v4, *(_DWORD *)(a1 + 136), *(_QWORD *)(a1 + 56), *(_QWORD *)(a1 + 24));
    v5 = xmmword_1800423E0;
  }
  if ( v3 && (v5 & 0x10) != 0 )
    WPP_SF_dJ(1028, 25, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids, v3, *(_QWORD *)(a1 + 24));
  return v3;
}

```

## disassembly

```asm
0x18000fca0  mov     [rsp+arg_0], rbx
0x18000fca5  mov     [rsp+arg_8], rsi
0x18000fcaa  push    rdi
0x18000fcab  sub     rsp, 30h
0x18000fcaf  mov     rdi, rcx
0x18000fcb2  call    InitializeInterfaceIaid
0x18000fcb7  mov     rcx, [rdi+288h]; hKey
0x18000fcbe  lea     rsi, [rdi+88h]
0x18000fcc5  mov     r9d, 4; dwType
0x18000fccb  lea     rdx, aDhcpv6iaid; "Dhcpv6Iaid"
0x18000fcd2  mov     [rsp+38h+cbData], r9d; cbData
0x18000fcd7  xor     r8d, r8d; Reserved
0x18000fcda  mov     [rsp+38h+lpData], rsi; lpData
0x18000fcdf  call    cs:__imp_RegSetValueExW
0x18000fce6  nop     dword ptr [rax+rax+00h]
0x18000fceb  mov     ebx, eax
0x18000fced  mov     al, byte ptr cs:xmmword_1800423E0
0x18000fcf3  test    al, 10h
0x18000fcf5  jz      short loc_18000FD17
0x18000fcf7  mov     rcx, [rdi+18h]
0x18000fcfb  mov     r9d, [rsi]
0x18000fcfe  mov     qword ptr [rsp+38h+cbData], rcx
0x18000fd03  mov     rcx, [rdi+38h]
0x18000fd07  mov     [rsp+38h+lpData], rcx
0x18000fd0c  call    WPP_SF_lSJ
0x18000fd11  mov     al, byte ptr cs:xmmword_1800423E0
0x18000fd17  test    ebx, ebx
0x18000fd19  jz      short loc_18000FD41
0x18000fd1b  test    al, 10h
0x18000fd1d  jz      short loc_18000FD41
0x18000fd1f  mov     rax, [rdi+18h]
0x18000fd23  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000fd2a  mov     edx, 19h
0x18000fd2f  mov     [rsp+38h+lpData], rax
0x18000fd34  mov     ecx, 404h
0x18000fd39  mov     r9d, ebx
0x18000fd3c  call    WPP_SF_dJ
0x18000fd41  mov     rsi, [rsp+38h+arg_8]
0x18000fd46  mov     eax, ebx
0x18000fd48  mov     rbx, [rsp+38h+arg_0]
0x18000fd4d  add     rsp, 30h
0x18000fd51  pop     rdi
0x18000fd52  retn
```
