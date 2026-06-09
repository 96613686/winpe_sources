# AERemoveRegKey(ushort *)

- ea: `0x1800066b4`
- end: `0x180006805`
- name: `?AERemoveRegKey@@YAKPEAG@Z`
- size: `337`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800074b0`

## callees

- `0x1800066b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800067a4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800067a4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006741`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180006741`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800066f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800066f7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800067bb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800067d8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800067bb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800067d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800067f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006761`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006761`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800067e3`

## pseudocode

```c
__int64 __fastcall AERemoveRegKey(LPCWSTR lpSubKey)
{
  unsigned int v2; // ebx
  SIZE_T v3; // rdx
  WCHAR *v4; // rdi
  DWORD i; // ebx
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+A8h] [rbp+38h] BYREF
  DWORD cSubKeys; // [rsp+B0h] [rbp+40h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp+48h] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  hKey = 0;
  v2 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey) )
  {
    v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( !v2 )
    {
      v3 = 2LL * ++cbMaxSubKeyLen;
      v4 = (WCHAR *)LocalAlloc(0x40u, v3);
      if ( v4 )
      {
        for ( i = 0; i < cSubKeys; ++i )
        {
          cchName = cbMaxSubKeyLen;
          if ( !RegEnumKeyExW(hKey, 0, v4, &cchName, 0, 0, 0, 0) )
            RegDeleteKeyExW(hKey, v4, 0, 0);
        }
        v2 = RegDeleteKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0);
        LocalFree(v4);
      }
      else
      {
        v2 = 8;
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1800066b4  push    rbp
0x1800066b6  push    rbx
0x1800066b7  push    rsi
0x1800066b8  push    rdi
0x1800066b9  push    r14
0x1800066bb  mov     rbp, rsp
0x1800066be  sub     rsp, 70h
0x1800066c2  xor     r14d, r14d
0x1800066c5  lea     rax, [rbp+hKey]
0x1800066c9  mov     rsi, rcx
0x1800066cc  mov     [rbp+cSubKeys], r14d
0x1800066d0  mov     rdx, rcx; lpSubKey
0x1800066d3  mov     [rbp+cbMaxSubKeyLen], r14d
0x1800066d7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800066de  mov     [rbp+cchName], r14d
0x1800066e2  mov     r9d, 0F003Fh; samDesired
0x1800066e8  mov     [rbp+hKey], r14
0x1800066ec  xor     r8d, r8d; ulOptions
0x1800066ef  mov     [rsp+70h+phkResult], rax; phkResult
0x1800066f4  mov     ebx, r14d
0x1800066f7  call    cs:__imp_RegOpenKeyExW
0x1800066fd  test    eax, eax
0x1800066ff  jnz     loc_1800067E9
0x180006705  mov     rcx, [rbp+hKey]; hKey
0x180006709  lea     rax, [rbp+cbMaxSubKeyLen]
0x18000670d  mov     [rsp+70h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180006712  xor     r9d, r9d; lpReserved
0x180006715  mov     [rsp+70h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18000671a  xor     r8d, r8d; lpcchClass
0x18000671d  mov     [rsp+70h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180006722  xor     edx, edx; lpClass
0x180006724  mov     [rsp+70h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180006729  mov     [rsp+70h+lpcValues], r14; lpcValues
0x18000672e  mov     [rsp+70h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180006733  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180006738  lea     rax, [rbp+cSubKeys]
0x18000673c  mov     [rsp+70h+phkResult], rax; lpcSubKeys
0x180006741  call    cs:__imp_RegQueryInfoKeyW
0x180006747  mov     ebx, eax
0x180006749  test    eax, eax
0x18000674b  jnz     loc_1800067E9
0x180006751  mov     eax, [rbp+cbMaxSubKeyLen]
0x180006754  lea     ecx, [rbx+40h]; uFlags
0x180006757  inc     eax
0x180006759  mov     edx, eax
0x18000675b  add     rdx, rdx; uBytes
0x18000675e  mov     [rbp+cbMaxSubKeyLen], eax
0x180006761  call    cs:__imp_LocalAlloc
0x180006767  mov     rdi, rax
0x18000676a  test    rax, rax
0x18000676d  jnz     short loc_180006774
0x18000676f  lea     ebx, [rax+8]
0x180006772  jmp     short loc_1800067E9
0x180006774  mov     ebx, r14d
0x180006777  cmp     [rbp+cSubKeys], r14d
0x18000677b  jbe     short loc_1800067C8
0x18000677d  mov     eax, [rbp+cbMaxSubKeyLen]
0x180006780  lea     r9, [rbp+cchName]; lpcchName
0x180006784  mov     rcx, [rbp+hKey]; hKey
0x180006788  mov     r8, rdi; lpName
0x18000678b  mov     [rsp+70h+lpcValues], r14; lpftLastWriteTime
0x180006790  xor     edx, edx; dwIndex
0x180006792  mov     [rsp+70h+lpcbMaxClassLen], r14; lpcchClass
0x180006797  mov     [rsp+70h+lpcbMaxSubKeyLen], r14; lpClass
0x18000679c  mov     [rsp+70h+phkResult], r14; lpReserved
0x1800067a1  mov     [rbp+cchName], eax
0x1800067a4  call    cs:__imp_RegEnumKeyExW
0x1800067aa  test    eax, eax
0x1800067ac  jnz     short loc_1800067C1
0x1800067ae  mov     rcx, [rbp+hKey]; hKey
0x1800067b2  xor     r9d, r9d; Reserved
0x1800067b5  xor     r8d, r8d; samDesired
0x1800067b8  mov     rdx, rdi; lpSubKey
0x1800067bb  call    cs:__imp_RegDeleteKeyExW
0x1800067c1  inc     ebx
0x1800067c3  cmp     ebx, [rbp+cSubKeys]
0x1800067c6  jb      short loc_18000677D
0x1800067c8  xor     r9d, r9d; Reserved
0x1800067cb  xor     r8d, r8d; samDesired
0x1800067ce  mov     rdx, rsi; lpSubKey
0x1800067d1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800067d8  call    cs:__imp_RegDeleteKeyExW
0x1800067de  mov     ebx, eax
0x1800067e0  mov     rcx, rdi; hMem
0x1800067e3  call    cs:__imp_LocalFree
0x1800067e9  mov     rcx, [rbp+hKey]; hKey
0x1800067ed  test    rcx, rcx
0x1800067f0  jz      short loc_1800067F8
0x1800067f2  call    cs:__imp_RegCloseKey
0x1800067f8  mov     eax, ebx
0x1800067fa  add     rsp, 70h
0x1800067fe  pop     r14
0x180006800  pop     rdi
0x180006801  pop     rsi
0x180006802  pop     rbx
0x180006803  pop     rbp
0x180006804  retn
```
