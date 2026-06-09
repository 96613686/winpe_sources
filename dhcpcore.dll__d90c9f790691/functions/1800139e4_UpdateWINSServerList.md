# UpdateWINSServerList

- ea: `0x1800139e4`
- end: `0x180013b5a`
- name: `UpdateWINSServerList`
- size: `374`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180013398`

## callees

- `0x180005330`
- `0x1800057f0`
- `0x180005da4`
- `0x1800139e4`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013b1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013b1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013aaf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013aaf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013aeb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013aeb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013a26`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180013a26`

## string_xrefs

- `0x180013a6c`: `System\CurrentControlSet\Services\NetBT\Parameters\Interfaces\Tcpip_?`

## pseudocode

```c
__int64 __fastcall UpdateWINSServerList(__int64 a1, HKEY a2)
{
  HKEY v4; // rcx
  unsigned int RegistryString; // eax
  const BYTE *v6; // rsi
  unsigned int v7; // ebx
  __int64 v8; // rdx
  BYTE *lpData[2]; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp+38h] BYREF

  lpSubKey = 0;
  lpData[0] = 0;
  v4 = *(HKEY *)(a1 + 728);
  cbData = 0;
  hKey = 0;
  RegDeleteValueW(v4, L"DhcpNameServerList");
  RegistryString = GetRegistryString(a2, L"DhcpNameServerList", lpData, &cbData);
  v6 = lpData[0];
  v7 = RegistryString;
  if ( RegistryString )
  {
    if ( (xmmword_1800616A0 & 0x10) == 0 )
      goto LABEL_14;
    v8 = 95;
    goto LABEL_13;
  }
  v7 = DhcpRegExpandString(
         L"System\\CurrentControlSet\\Services\\NetBT\\Parameters\\Interfaces\\Tcpip_?",
         *(void **)(a1 + 56));
  if ( v7 )
  {
    if ( (xmmword_1800616A0 & 0x10) == 0 )
      goto LABEL_14;
    v8 = 96;
    goto LABEL_13;
  }
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xFu, &hKey);
  if ( v7 )
  {
    if ( (xmmword_1800616A0 & 0x10) == 0 )
      goto LABEL_14;
    v8 = 97;
    goto LABEL_13;
  }
  v7 = RegSetValueExW(hKey, L"DhcpNameServerList", 0, 7u, v6, cbData);
  if ( v7 && (xmmword_1800616A0 & 0x10) != 0 )
  {
    v8 = 98;
LABEL_13:
    WPP_SF_(1028, v8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
  }
LABEL_14:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( lpSubKey )
    DhcpPunycodeFree((LPVOID *)&lpSubKey);
  if ( v6 )
    DhcpPunycodeFree((LPVOID *)lpData);
  return v7;
}

```

## disassembly

```asm
0x1800139e4  mov     [rsp-18h+arg_8], rbx
0x1800139e9  push    rbp
0x1800139ea  push    rsi
0x1800139eb  push    rdi
0x1800139ec  mov     rbp, rsp
0x1800139ef  sub     rsp, 40h
0x1800139f3  mov     rbx, rdx
0x1800139f6  mov     [rbp+lpSubKey], 0
0x1800139fe  mov     rdi, rcx
0x180013a01  mov     [rbp+lpData], 0
0x180013a09  mov     rcx, [rcx+2D8h]; hKey
0x180013a10  lea     rdx, aDhcpnameserver_0; "DhcpNameServerList"
0x180013a17  mov     [rbp+arg_0], 0
0x180013a1e  mov     [rbp+hKey], 0
0x180013a26  call    cs:__imp_RegDeleteValueW
0x180013a2c  lea     r9, [rbp+arg_0]
0x180013a30  mov     rcx, rbx; hKey
0x180013a33  lea     r8, [rbp+lpData]
0x180013a37  lea     rdx, aDhcpnameserver_0; "DhcpNameServerList"
0x180013a3e  call    GetRegistryString
0x180013a43  mov     rsi, [rbp+lpData]
0x180013a47  mov     ebx, eax
0x180013a49  test    eax, eax
0x180013a4b  jz      short loc_180013A64
0x180013a4d  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013a54  jz      loc_180013B16
0x180013a5a  mov     edx, 5Fh ; '_'
0x180013a5f  jmp     loc_180013B05
0x180013a64  mov     rdx, [rdi+38h]; void *
0x180013a68  lea     r8, [rbp+lpSubKey]
0x180013a6c  lea     rcx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ne"...
0x180013a73  call    DhcpRegExpandString
0x180013a78  mov     ebx, eax
0x180013a7a  test    eax, eax
0x180013a7c  jz      short loc_180013A92
0x180013a7e  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013a85  jz      loc_180013B16
0x180013a8b  mov     edx, 60h ; '`'
0x180013a90  jmp     short loc_180013B05
0x180013a92  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180013a96  lea     rax, [rbp+hKey]
0x180013a9a  mov     r9d, 0Fh; samDesired
0x180013aa0  mov     [rsp+40h+phkResult], rax; phkResult
0x180013aa5  xor     r8d, r8d; ulOptions
0x180013aa8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013aaf  call    cs:__imp_RegOpenKeyExW
0x180013ab5  mov     ebx, eax
0x180013ab7  test    eax, eax
0x180013ab9  jz      short loc_180013ACB
0x180013abb  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013ac2  jz      short loc_180013B16
0x180013ac4  mov     edx, 61h ; 'a'
0x180013ac9  jmp     short loc_180013B05
0x180013acb  mov     eax, [rbp+arg_0]
0x180013ace  lea     rdx, aDhcpnameserver_0; "DhcpNameServerList"
0x180013ad5  mov     rcx, [rbp+hKey]; hKey
0x180013ad9  mov     r9d, 7; dwType
0x180013adf  mov     [rsp+40h+cbData], eax; cbData
0x180013ae3  xor     r8d, r8d; Reserved
0x180013ae6  mov     [rsp+40h+phkResult], rsi; lpData
0x180013aeb  call    cs:__imp_RegSetValueExW
0x180013af1  mov     ebx, eax
0x180013af3  test    eax, eax
0x180013af5  jz      short loc_180013B16
0x180013af7  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013afe  jz      short loc_180013B16
0x180013b00  mov     edx, 62h ; 'b'
0x180013b05  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180013b0c  mov     ecx, 404h
0x180013b11  call    WPP_SF_
0x180013b16  mov     rcx, [rbp+hKey]; hKey
0x180013b1a  test    rcx, rcx
0x180013b1d  jz      short loc_180013B2D
0x180013b1f  call    cs:__imp_RegCloseKey
0x180013b25  mov     [rbp+hKey], 0
0x180013b2d  cmp     [rbp+lpSubKey], 0
0x180013b32  jz      short loc_180013B3D
0x180013b34  lea     rcx, [rbp+lpSubKey]
0x180013b38  call    DhcpPunycodeFree
0x180013b3d  test    rsi, rsi
0x180013b40  jz      short loc_180013B4B
0x180013b42  lea     rcx, [rbp+lpData]
0x180013b46  call    DhcpPunycodeFree
0x180013b4b  mov     eax, ebx
0x180013b4d  mov     rbx, [rsp+40h+arg_8]
0x180013b52  add     rsp, 40h
0x180013b56  pop     rdi
0x180013b57  pop     rsi
0x180013b58  pop     rbp
0x180013b59  retn
```
