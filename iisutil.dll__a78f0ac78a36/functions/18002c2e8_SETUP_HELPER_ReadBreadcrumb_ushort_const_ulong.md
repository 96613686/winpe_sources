# SETUP_HELPER::ReadBreadcrumb(ushort const *,ulong *)

- ea: `0x18002c2e8`
- end: `0x18002c38d`
- name: `?ReadBreadcrumb@SETUP_HELPER@@CAKPEBGPEAK@Z`
- size: `165`
- prototype: `static unsigned int(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002c180`

## callees

- `0x18002c2e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c33b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c33b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c37a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c37a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c368`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c368`

## string_xrefs

- `0x18002c31f`: `System\CurrentControlSet\Services\WAS\Parameters`

## pseudocode

```c
__int64 __fastcall SETUP_HELPER::ReadBreadcrumb(const unsigned __int16 *a1, BYTE *a2)
{
  unsigned int v3; // ebx
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int v6; // [rsp+44h] [rbp+Ch]
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v6 = HIDWORD(a1);
  cbData = 4;
  hKey = 0;
  if ( a2 )
  {
    *(_DWORD *)a2 = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\WAS\\Parameters", 0, 0x20019u, &hKey);
    if ( !v3 )
    {
      v3 = RegQueryValueExW(hKey, L"GenerateKeys", 0, 0, a2, &cbData);
      if ( hKey )
        RegCloseKey(hKey);
    }
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x18002c2e8  mov     rax, rsp
0x18002c2eb  mov     [rax+18h], rbx
0x18002c2ef  mov     [rax+8], rcx
0x18002c2f3  push    rdi
0x18002c2f4  sub     rsp, 30h
0x18002c2f8  mov     dword ptr [rax+8], 4
0x18002c2ff  mov     rdi, rdx
0x18002c302  mov     qword ptr [rax+10h], 0
0x18002c30a  test    rdx, rdx
0x18002c30d  jnz     short loc_18002C314
0x18002c30f  lea     ebx, [rdx+57h]
0x18002c312  jmp     short loc_18002C380
0x18002c314  mov     dword ptr [rdx], 0
0x18002c31a  lea     rax, [rsp+38h+hKey]
0x18002c31f  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\WA"...
0x18002c326  mov     [rsp+38h+phkResult], rax; phkResult
0x18002c32b  mov     r9d, 20019h; samDesired
0x18002c331  xor     r8d, r8d; ulOptions
0x18002c334  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c33b  call    cs:__imp_RegOpenKeyExW
0x18002c341  mov     ebx, eax
0x18002c343  test    eax, eax
0x18002c345  jnz     short loc_18002C380
0x18002c347  mov     rcx, [rsp+38h+hKey]; hKey
0x18002c34c  lea     rax, [rsp+38h+cbData]
0x18002c351  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002c356  lea     rdx, aGeneratekeys; "GenerateKeys"
0x18002c35d  xor     r9d, r9d; lpType
0x18002c360  mov     [rsp+38h+phkResult], rdi; lpData
0x18002c365  xor     r8d, r8d; lpReserved
0x18002c368  call    cs:__imp_RegQueryValueExW
0x18002c36e  mov     ebx, eax
0x18002c370  mov     rcx, [rsp+38h+hKey]; hKey
0x18002c375  test    rcx, rcx
0x18002c378  jz      short loc_18002C380
0x18002c37a  call    cs:__imp_RegCloseKey
0x18002c380  mov     eax, ebx
0x18002c382  mov     rbx, [rsp+38h+arg_10]
0x18002c387  add     rsp, 30h
0x18002c38b  pop     rdi
0x18002c38c  retn
```
