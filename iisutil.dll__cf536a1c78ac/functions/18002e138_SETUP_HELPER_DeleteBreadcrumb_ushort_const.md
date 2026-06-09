# SETUP_HELPER::DeleteBreadcrumb(ushort const *)

- ea: `0x18002e138`
- end: `0x18002e1bc`
- name: `?DeleteBreadcrumb@SETUP_HELPER@@CAKPEBG@Z`
- size: `132`
- prototype: `unsigned int __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002e1d0`
- `0x18002e340`

## callees

- `0x18002e138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e16e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e16e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e1a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e1a2`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002e18a`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002e18a`

## string_xrefs

- `0x18002e167`: `System\CurrentControlSet\Services\WAS\Parameters`

## pseudocode

```c
__int64 __fastcall SETUP_HELPER::DeleteBreadcrumb(LPCWSTR lpValueName)
{
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\WAS\\Parameters", 0, 2u, &hKey);
  if ( !v2 )
  {
    v2 = RegDeleteKeyValueW(hKey, 0, lpValueName);
    if ( hKey )
      RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x18002e138  mov     r11, rsp
0x18002e13b  mov     [r11+8], rbx
0x18002e13f  push    rdi
0x18002e140  sub     rsp, 30h
0x18002e144  mov     rdi, rcx
0x18002e147  mov     qword ptr [r11+10h], 0
0x18002e14f  lea     rax, [r11+10h]
0x18002e153  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e15a  mov     r9d, 2; samDesired
0x18002e160  mov     [r11-18h], rax
0x18002e164  xor     r8d, r8d; ulOptions
0x18002e167  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\WA"...
0x18002e16e  call    cs:__imp_RegOpenKeyExW
0x18002e175  nop     dword ptr [rax+rax+00h]
0x18002e17a  mov     ebx, eax
0x18002e17c  test    eax, eax
0x18002e17e  jnz     short loc_18002E1AE
0x18002e180  mov     rcx, [rsp+38h+hKey]; hKey
0x18002e185  mov     r8, rdi; lpValueName
0x18002e188  xor     edx, edx; lpSubKey
0x18002e18a  call    cs:__imp_RegDeleteKeyValueW
0x18002e191  nop     dword ptr [rax+rax+00h]
0x18002e196  mov     ebx, eax
0x18002e198  mov     rcx, [rsp+38h+hKey]; hKey
0x18002e19d  test    rcx, rcx
0x18002e1a0  jz      short loc_18002E1AE
0x18002e1a2  call    cs:__imp_RegCloseKey
0x18002e1a9  nop     dword ptr [rax+rax+00h]
0x18002e1ae  mov     eax, ebx
0x18002e1b0  mov     rbx, [rsp+38h+arg_0]
0x18002e1b5  add     rsp, 30h
0x18002e1b9  pop     rdi
0x18002e1ba  retn
```
