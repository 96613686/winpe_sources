# ResetIPAddressPool

- ea: `0x180015498`
- end: `0x180015553`
- name: `ResetIPAddressPool`
- size: `187`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180015828`

## callees

- `0x180015498`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015540`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015540`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800154f0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800154f0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015520`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015530`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015520`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180015530`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001550a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001550a`

## pseudocode

```c
__int64 __fastcall ResetIPAddressPool(HKEY hKey)
{
  unsigned int v2; // ebx
  DWORD v4; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKeya; // [rsp+70h] [rbp+18h] BYREF

  hKeya = 0;
  v4 = 0;
  v2 = RegCreateKeyExW(hKey, L"StaticAddressPool", 0, 0, 0, 0xF003Fu, 0, &hKeya, &v4);
  if ( !v2 && (v4 != 2 || (v2 = RegDeleteTreeW(hKeya, 0)) == 0) )
  {
    RegDeleteValueW(hKey, L"IpAddress");
    RegDeleteValueW(hKey, L"IpMask");
  }
  if ( hKeya )
    RegCloseKey(hKeya);
  return v2;
}

```

## disassembly

```asm
0x180015498  mov     r11, rsp
0x18001549b  mov     [r11+8], rbx
0x18001549f  mov     [rsp+arg_8], edx
0x1800154a3  push    rdi
0x1800154a4  sub     rsp, 50h
0x1800154a8  lea     rax, [r11+10h]
0x1800154ac  mov     qword ptr [r11+18h], 0
0x1800154b4  mov     [r11-18h], rax
0x1800154b8  lea     rdx, c_szRegValStaticAddressPool; "StaticAddressPool"
0x1800154bf  lea     rax, [r11+18h]
0x1800154c3  mov     [rsp+58h+arg_8], 0
0x1800154cb  mov     [r11-20h], rax
0x1800154cf  xor     r9d, r9d; lpClass
0x1800154d2  mov     qword ptr [r11-28h], 0
0x1800154da  xor     r8d, r8d; Reserved
0x1800154dd  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1800154e5  mov     rdi, rcx
0x1800154e8  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800154f0  call    cs:__imp_RegCreateKeyExW
0x1800154f6  mov     ebx, eax
0x1800154f8  test    eax, eax
0x1800154fa  jnz     short loc_180015536
0x1800154fc  cmp     [rsp+58h+arg_8], 2
0x180015501  jnz     short loc_180015516
0x180015503  mov     rcx, [rsp+58h+hKey]; hKey
0x180015508  xor     edx, edx; lpSubKey
0x18001550a  call    cs:__imp_RegDeleteTreeW
0x180015510  mov     ebx, eax
0x180015512  test    eax, eax
0x180015514  jnz     short loc_180015536
0x180015516  lea     rdx, c_szRegValIpAddr; "IpAddress"
0x18001551d  mov     rcx, rdi; hKey
0x180015520  call    cs:__imp_RegDeleteValueW
0x180015526  lea     rdx, c_szRegValIpMask; "IpMask"
0x18001552d  mov     rcx, rdi; hKey
0x180015530  call    cs:__imp_RegDeleteValueW
0x180015536  mov     rcx, [rsp+58h+hKey]; hKey
0x18001553b  test    rcx, rcx
0x18001553e  jz      short loc_180015546
0x180015540  call    cs:__imp_RegCloseKey
0x180015546  mov     eax, ebx
0x180015548  mov     rbx, [rsp+58h+arg_0]
0x18001554d  add     rsp, 50h
0x180015551  pop     rdi
0x180015552  retn
```
