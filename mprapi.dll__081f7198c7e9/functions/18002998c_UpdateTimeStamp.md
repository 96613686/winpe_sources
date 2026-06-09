# UpdateTimeStamp

- ea: `0x18002998c`
- end: `0x180029a2c`
- name: `UpdateTimeStamp`
- size: `160`
- prototype: `__int64 __fastcall(HKEY hKey, PFILETIME lpftLastWriteTime)`
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18002201c`
- `0x180022324`
- `0x180022b50`
- `0x180022be8`
- `0x180023210`
- `0x1800236e0`
- `0x180023e40`
- `0x1800255a0`
- `0x180025cb0`
- `0x180027da0`
- `0x180028100`

## callees

- `0x18002998c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180029a1b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180029a1b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800299c2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800299c2`

## pseudocode

```c
LSTATUS __fastcall UpdateTimeStamp(HKEY hKey, PFILETIME lpftLastWriteTime)
{
  LSTATUS result; // eax
  int lpData; // [rsp+80h] [rbp+18h] BYREF

  lpData = 0;
  result = RegSetValueExW(hKey, L"Stamp", 0, 4u, (const BYTE *)&lpData, 4u);
  if ( !result )
    return RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, lpftLastWriteTime);
  return result;
}

```

## disassembly

```asm
0x18002998c  mov     rax, rsp
0x18002998f  mov     [rax+8], rbx
0x180029993  push    rdi
0x180029994  sub     rsp, 60h
0x180029998  mov     r9d, 4; dwType
0x18002999e  mov     dword ptr [rax+18h], 0
0x1800299a5  mov     [rax-40h], r9d
0x1800299a9  lea     rax, [rax+18h]
0x1800299ad  mov     rdi, rdx
0x1800299b0  mov     [rsp+68h+lpData], rax; lpData
0x1800299b5  xor     r8d, r8d; Reserved
0x1800299b8  lea     rdx, c_szStamp; "Stamp"
0x1800299bf  mov     rbx, rcx
0x1800299c2  call    cs:__imp_RegSetValueExW
0x1800299c8  test    eax, eax
0x1800299ca  jnz     short loc_180029A21
0x1800299cc  mov     [rsp+68h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800299d1  xor     r9d, r9d; lpReserved
0x1800299d4  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800299dd  xor     r8d, r8d; lpcchClass
0x1800299e0  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x1800299e9  xor     edx, edx; lpClass
0x1800299eb  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x1800299f4  mov     rcx, rbx; hKey
0x1800299f7  mov     [rsp+68h+lpcValues], 0; lpcValues
0x180029a00  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180029a09  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180029a12  mov     [rsp+68h+lpData], 0; lpcSubKeys
0x180029a1b  call    cs:__imp_RegQueryInfoKeyW
0x180029a21  mov     rbx, [rsp+68h+arg_0]
0x180029a26  add     rsp, 60h
0x180029a2a  pop     rdi
0x180029a2b  retn
```
