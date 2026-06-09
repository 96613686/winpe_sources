# RegDeleteKeyRecursive

- ea: `0x14000c348`
- end: `0x14000c4f8`
- name: `RegDeleteKeyRecursive`
- size: `432`
- prototype: `LSTATUS __fastcall(HKEY, const WCHAR *, REGSAM)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000a7d8`
- `0x14000c348`

## callees

- `0x14000c348`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c3ad`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000c3ad`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000c483`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000c483`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c44a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c4c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c44a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000c4c4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14000c4d6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14000c4d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000c410`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14000c410`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c4ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c4ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c435`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000c435`

## pseudocode

```c
LSTATUS __fastcall RegDeleteKeyRecursive(HKEY a1, const WCHAR *a2, REGSAM a3)
{
  LSTATUS v6; // eax
  int v7; // ebx
  WCHAR *v8; // rdi
  DWORD v10; // ebx
  LSTATUS v11; // ecx
  DWORD v12; // eax
  HKEY hKey; // [rsp+60h] [rbp+7h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+68h] [rbp+Fh] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp+13h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+70h] [rbp+17h] BYREF
  DWORD cValues; // [rsp+74h] [rbp+1Bh] BYREF
  DWORD cbMaxClassLen; // [rsp+78h] [rbp+1Fh] BYREF
  DWORD cchClass; // [rsp+7Ch] [rbp+23h] BYREF
  DWORD cchName; // [rsp+80h] [rbp+27h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+88h] [rbp+2Fh] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+D0h] [rbp+77h] BYREF
  DWORD cSubKeys; // [rsp+D8h] [rbp+7Fh] BYREF

  hKey = 0;
  cchClass = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cbMaxClassLen = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cbSecurityDescriptor = 0;
  ftLastWriteTime = 0;
  if ( !RegOpenKeyExW(a1, a2, 0, a3 | 9, &hKey) )
  {
    v6 = RegQueryInfoKeyW(
           hKey,
           0,
           &cchClass,
           0,
           &cSubKeys,
           &cbMaxSubKeyLen,
           &cbMaxClassLen,
           &cValues,
           &cbMaxValueNameLen,
           &cbMaxValueLen,
           &cbSecurityDescriptor,
           &ftLastWriteTime);
    v7 = v6;
    if ( v6 && v6 != 234 && v6 != 122 )
      goto LABEL_7;
    v8 = (WCHAR *)LocalAlloc(0x40u, 2LL * (cbMaxSubKeyLen + 1));
    if ( !v8 )
    {
      v7 = 8;
LABEL_7:
      RegCloseKey(hKey);
      return v7;
    }
    v10 = 0;
    do
    {
      cchName = cbMaxSubKeyLen + 1;
      v11 = RegEnumKeyExW(hKey, v10, v8, &cchName, 0, 0, 0, 0);
      if ( !v11 )
        v11 = RegDeleteKeyRecursive(hKey, v8, a3);
      v12 = v10 + 1;
      if ( !v11 )
        v12 = v10;
      v10 = v12;
    }
    while ( v11 != 259 && v12 < cSubKeys );
    LocalFree(v8);
    RegCloseKey(hKey);
  }
  return RegDeleteKeyExW(a1, a2, a3, 0);
}

```

## disassembly

```asm
0x14000c348  mov     [rsp-8+arg_0], rbx
0x14000c34d  mov     [rsp-8+arg_8], rsi
0x14000c352  push    rbp
0x14000c353  push    rdi
0x14000c354  push    r12
0x14000c356  push    r14
0x14000c358  push    r15
0x14000c35a  lea     rbp, [rsp-37h]
0x14000c35f  sub     rsp, 90h
0x14000c366  xor     r12d, r12d
0x14000c369  lea     rax, [rbp+57h+hKey]
0x14000c36d  mov     r9d, r8d
0x14000c370  mov     [rbp+57h+hKey], r12
0x14000c374  mov     esi, r8d
0x14000c377  mov     [rbp+57h+cchClass], r12d
0x14000c37b  or      r9d, 9; samDesired
0x14000c37f  mov     [rbp+57h+cSubKeys], r12d
0x14000c383  xor     r8d, r8d; ulOptions
0x14000c386  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x14000c38a  mov     r14, rdx
0x14000c38d  mov     [rbp+57h+cbMaxClassLen], r12d
0x14000c391  mov     r15, rcx
0x14000c394  mov     [rbp+57h+cValues], r12d
0x14000c398  mov     [rbp+57h+cbMaxValueNameLen], r12d
0x14000c39c  mov     [rbp+57h+cbMaxValueLen], r12d
0x14000c3a0  mov     [rbp+57h+cbSecurityDescriptor], r12d
0x14000c3a4  mov     qword ptr [rbp+57h+ftLastWriteTime.dwLowDateTime], r12
0x14000c3a8  mov     [rsp+0B0h+phkResult], rax; phkResult
0x14000c3ad  call    cs:__imp_RegOpenKeyExW
0x14000c3b3  test    eax, eax
0x14000c3b5  jnz     loc_14000C4CA
0x14000c3bb  mov     rcx, [rbp+57h+hKey]; hKey
0x14000c3bf  lea     rax, [rbp+57h+ftLastWriteTime]
0x14000c3c3  mov     [rsp+0B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14000c3c8  lea     r8, [rbp+57h+cchClass]; lpcchClass
0x14000c3cc  lea     rax, [rbp+57h+cbSecurityDescriptor]
0x14000c3d0  xor     r9d, r9d; lpReserved
0x14000c3d3  mov     [rsp+0B0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x14000c3d8  xor     edx, edx; lpClass
0x14000c3da  lea     rax, [rbp+57h+cbMaxValueLen]
0x14000c3de  mov     [rsp+0B0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x14000c3e3  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x14000c3e7  mov     [rsp+0B0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x14000c3ec  lea     rax, [rbp+57h+cValues]
0x14000c3f0  mov     [rsp+0B0h+lpcValues], rax; lpcValues
0x14000c3f5  lea     rax, [rbp+57h+cbMaxClassLen]
0x14000c3f9  mov     [rsp+0B0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x14000c3fe  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14000c402  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14000c407  lea     rax, [rbp+57h+cSubKeys]
0x14000c40b  mov     [rsp+0B0h+phkResult], rax; lpcSubKeys
0x14000c410  call    cs:__imp_RegQueryInfoKeyW
0x14000c416  mov     ebx, eax
0x14000c418  test    eax, eax
0x14000c41a  jz      short loc_14000C428
0x14000c41c  cmp     eax, 0EAh
0x14000c421  jz      short loc_14000C428
0x14000c423  cmp     eax, 7Ah ; 'z'
0x14000c426  jnz     short loc_14000C446
0x14000c428  mov     edx, [rbp+57h+cbMaxSubKeyLen]
0x14000c42b  mov     ecx, 40h ; '@'; uFlags
0x14000c430  inc     edx
0x14000c432  add     rdx, rdx; uBytes
0x14000c435  call    cs:__imp_LocalAlloc
0x14000c43b  mov     rdi, rax
0x14000c43e  test    rax, rax
0x14000c441  jnz     short loc_14000C457
0x14000c443  lea     ebx, [rax+8]
0x14000c446  mov     rcx, [rbp+57h+hKey]; hKey
0x14000c44a  call    cs:__imp_RegCloseKey
0x14000c450  mov     eax, ebx
0x14000c452  jmp     loc_14000C4DC
0x14000c457  mov     ebx, r12d
0x14000c45a  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x14000c45d  lea     r9, [rbp+57h+cchName]; lpcchName
0x14000c461  mov     rcx, [rbp+57h+hKey]; hKey
0x14000c465  inc     eax
0x14000c467  mov     [rsp+0B0h+lpcValues], r12; lpftLastWriteTime
0x14000c46c  mov     r8, rdi; lpName
0x14000c46f  mov     [rsp+0B0h+lpcbMaxClassLen], r12; lpcchClass
0x14000c474  mov     edx, ebx; dwIndex
0x14000c476  mov     [rsp+0B0h+lpcbMaxSubKeyLen], r12; lpClass
0x14000c47b  mov     [rbp+57h+cchName], eax
0x14000c47e  mov     [rsp+0B0h+phkResult], r12; lpReserved
0x14000c483  call    cs:__imp_RegEnumKeyExW
0x14000c489  mov     ecx, eax
0x14000c48b  test    eax, eax
0x14000c48d  jnz     short loc_14000C4A0
0x14000c48f  mov     rcx, [rbp+57h+hKey]
0x14000c493  mov     r8d, esi
0x14000c496  mov     rdx, rdi
0x14000c499  call    RegDeleteKeyRecursive
0x14000c49e  mov     ecx, eax
0x14000c4a0  test    ecx, ecx
0x14000c4a2  lea     eax, [rbx+1]
0x14000c4a5  cmovz   eax, ebx
0x14000c4a8  mov     ebx, eax
0x14000c4aa  cmp     ecx, 103h
0x14000c4b0  jz      short loc_14000C4B7
0x14000c4b2  cmp     eax, [rbp+57h+cSubKeys]
0x14000c4b5  jb      short loc_14000C45A
0x14000c4b7  mov     rcx, rdi; hMem
0x14000c4ba  call    cs:__imp_LocalFree
0x14000c4c0  mov     rcx, [rbp+57h+hKey]; hKey
0x14000c4c4  call    cs:__imp_RegCloseKey
0x14000c4ca  xor     r9d, r9d; Reserved
0x14000c4cd  mov     r8d, esi; samDesired
0x14000c4d0  mov     rdx, r14; lpSubKey
0x14000c4d3  mov     rcx, r15; hKey
0x14000c4d6  call    cs:__imp_RegDeleteKeyExW
0x14000c4dc  lea     r11, [rsp+0B0h+var_20]
0x14000c4e4  mov     rbx, [r11+30h]
0x14000c4e8  mov     rsi, [r11+38h]
0x14000c4ec  mov     rsp, r11
0x14000c4ef  pop     r15
0x14000c4f1  pop     r14
0x14000c4f3  pop     r12
0x14000c4f5  pop     rdi
0x14000c4f6  pop     rbp
0x14000c4f7  retn
```
