# SETUP_HELPER::ReadBreadcrumb(ushort const *,ulong *)

- ea: `0x18002e368`
- end: `0x18002e420`
- name: `?ReadBreadcrumb@SETUP_HELPER@@CAKPEBGPEAK@Z`
- size: `184`
- prototype: `static unsigned int(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002e1d0`

## callees

- `0x18002e368`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e3bb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e3bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e406`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e406`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e3ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002e3ee`

## string_xrefs

- `0x18002e39f`: `System\CurrentControlSet\Services\WAS\Parameters`

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
0x18002e368  mov     rax, rsp
0x18002e36b  mov     [rax+18h], rbx
0x18002e36f  mov     [rax+8], rcx
0x18002e373  push    rdi
0x18002e374  sub     rsp, 30h
0x18002e378  mov     dword ptr [rax+8], 4
0x18002e37f  mov     rdi, rdx
0x18002e382  mov     qword ptr [rax+10h], 0
0x18002e38a  test    rdx, rdx
0x18002e38d  jnz     short loc_18002E394
0x18002e38f  lea     ebx, [rdx+57h]
0x18002e392  jmp     short loc_18002E412
0x18002e394  mov     dword ptr [rdx], 0
0x18002e39a  lea     rax, [rsp+38h+hKey]
0x18002e39f  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\WA"...
0x18002e3a6  mov     [rsp+38h+phkResult], rax; phkResult
0x18002e3ab  mov     r9d, 20019h; samDesired
0x18002e3b1  xor     r8d, r8d; ulOptions
0x18002e3b4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e3bb  call    cs:__imp_RegOpenKeyExW
0x18002e3c2  nop     dword ptr [rax+rax+00h]
0x18002e3c7  mov     ebx, eax
0x18002e3c9  test    eax, eax
0x18002e3cb  jnz     short loc_18002E412
0x18002e3cd  mov     rcx, [rsp+38h+hKey]; hKey
0x18002e3d2  lea     rax, [rsp+38h+cbData]
0x18002e3d7  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002e3dc  lea     rdx, aGeneratekeys; "GenerateKeys"
0x18002e3e3  xor     r9d, r9d; lpType
0x18002e3e6  mov     [rsp+38h+phkResult], rdi; lpData
0x18002e3eb  xor     r8d, r8d; lpReserved
0x18002e3ee  call    cs:__imp_RegQueryValueExW
0x18002e3f5  nop     dword ptr [rax+rax+00h]
0x18002e3fa  mov     ebx, eax
0x18002e3fc  mov     rcx, [rsp+38h+hKey]; hKey
0x18002e401  test    rcx, rcx
0x18002e404  jz      short loc_18002E412
0x18002e406  call    cs:__imp_RegCloseKey
0x18002e40d  nop     dword ptr [rax+rax+00h]
0x18002e412  mov     eax, ebx
0x18002e414  mov     rbx, [rsp+38h+arg_10]
0x18002e419  add     rsp, 30h
0x18002e41d  pop     rdi
0x18002e41e  retn
```
