# DhcpRegReadDWORD

- ea: `0x180036684`
- end: `0x1800366f4`
- name: `DhcpRegReadDWORD`
- size: `112`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001abb0`

## callees

- `0x1800153dc`
- `0x180036684`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800366e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800366e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800366ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800366ba`

## string_xrefs

- `0x1800366cb`: `Rfc3442Compliance`

## pseudocode

```c
__int64 __fastcall DhcpRegReadDWORD(LPCWSTR lpSubKey, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int DWORDWithKey; // ebx
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  DWORDWithKey = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, &hKey);
  if ( !DWORDWithKey )
  {
    DWORDWithKey = DhcpRegReadDWORDWithKey(hKey, L"Rfc3442Compliance", a4);
    RegCloseKey(hKey);
  }
  return DWORDWithKey;
}

```

## disassembly

```asm
0x180036684  mov     r11, rsp
0x180036687  mov     [r11+8], rbx
0x18003668b  mov     [r11+18h], r8
0x18003668f  push    rdi
0x180036690  sub     rsp, 30h
0x180036694  mov     rdi, r9
0x180036697  mov     qword ptr [r11+18h], 0
0x18003669f  lea     rax, [r11+18h]
0x1800366a3  mov     rdx, rcx; lpSubKey
0x1800366a6  mov     r9d, 1; samDesired
0x1800366ac  mov     [r11-18h], rax
0x1800366b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800366b7  xor     r8d, r8d; ulOptions
0x1800366ba  call    cs:__imp_RegOpenKeyExW
0x1800366c0  mov     ebx, eax
0x1800366c2  test    eax, eax
0x1800366c4  jnz     short loc_1800366E7
0x1800366c6  mov     rcx, [rsp+38h+hKey]
0x1800366cb  lea     rdx, aRfc3442complia; "Rfc3442Compliance"
0x1800366d2  mov     r8, rdi
0x1800366d5  call    DhcpRegReadDWORDWithKey
0x1800366da  mov     ebx, eax
0x1800366dc  mov     rcx, [rsp+38h+hKey]; hKey
0x1800366e1  call    cs:__imp_RegCloseKey
0x1800366e7  mov     eax, ebx
0x1800366e9  mov     rbx, [rsp+38h+arg_0]
0x1800366ee  add     rsp, 30h
0x1800366f2  pop     rdi
0x1800366f3  retn
```
