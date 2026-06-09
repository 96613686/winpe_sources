# SETUP_HELPER::DeleteBreadcrumb(ushort const *)

- ea: `0x18002c104`
- end: `0x18002c175`
- name: `?DeleteBreadcrumb@SETUP_HELPER@@CAKPEBG@Z`
- size: `113`
- prototype: `unsigned int __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002c180`
- `0x18002c2c0`

## callees

- `0x18002c104`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c13a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c13a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c162`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c162`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002c150`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18002c150`

## string_xrefs

- `0x18002c133`: `System\CurrentControlSet\Services\WAS\Parameters`

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
0x18002c104  mov     r11, rsp
0x18002c107  mov     [r11+8], rbx
0x18002c10b  push    rdi
0x18002c10c  sub     rsp, 30h
0x18002c110  mov     rdi, rcx
0x18002c113  mov     qword ptr [r11+10h], 0
0x18002c11b  lea     rax, [r11+10h]
0x18002c11f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c126  mov     r9d, 2; samDesired
0x18002c12c  mov     [r11-18h], rax
0x18002c130  xor     r8d, r8d; ulOptions
0x18002c133  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\WA"...
0x18002c13a  call    cs:__imp_RegOpenKeyExW
0x18002c140  mov     ebx, eax
0x18002c142  test    eax, eax
0x18002c144  jnz     short loc_18002C168
0x18002c146  mov     rcx, [rsp+38h+hKey]; hKey
0x18002c14b  mov     r8, rdi; lpValueName
0x18002c14e  xor     edx, edx; lpSubKey
0x18002c150  call    cs:__imp_RegDeleteKeyValueW
0x18002c156  mov     ebx, eax
0x18002c158  mov     rcx, [rsp+38h+hKey]; hKey
0x18002c15d  test    rcx, rcx
0x18002c160  jz      short loc_18002C168
0x18002c162  call    cs:__imp_RegCloseKey
0x18002c168  mov     eax, ebx
0x18002c16a  mov     rbx, [rsp+38h+arg_0]
0x18002c16f  add     rsp, 30h
0x18002c173  pop     rdi
0x18002c174  retn
```
