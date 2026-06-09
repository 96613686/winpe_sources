# PortEnumRegistrySubKeys

- ea: `0x180016d4c`
- end: `0x180016eea`
- name: `PortEnumRegistrySubKeys`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016cd0`

## callees

- `0x180016d4c`
- `0x180016ef0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016e1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180016e1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ed3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016ed3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ea6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ec5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ea6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016ec5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016dfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180016dfc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180016e60`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180016e60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016da7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016e85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016da7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016e85`

## pseudocode

```c
__int64 __fastcall PortEnumRegistrySubKeys(__int64 a1, const WCHAR *a2, __int64 a3, __int64 a4)
{
  WCHAR *v5; // rdi
  HKEY v6; // rcx
  int v7; // r14d
  unsigned int ConfigKey; // ebx
  DWORD i; // esi
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-8h] BYREF
  DWORD cSubKeys; // [rsp+B0h] [rbp+40h] BYREF
  int v14; // [rsp+B4h] [rbp+44h]
  DWORD cchName; // [rsp+B8h] [rbp+48h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+C0h] [rbp+50h] BYREF
  int v17; // [rsp+C4h] [rbp+54h]

  v17 = HIDWORD(a3);
  v14 = HIDWORD(a1);
  cbMaxSubKeyLen = 0;
  v5 = 0;
  cchName = 0;
  v6 = HKEY_LOCAL_MACHINE;
  cSubKeys = 0;
  hKey = 0;
  phkResult = 0;
  if ( a2 )
  {
    v7 = 1;
    ConfigKey = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0xF003Fu, &hKey);
    if ( ConfigKey )
      goto LABEL_13;
    v6 = hKey;
  }
  else
  {
    v7 = 0;
    hKey = HKEY_LOCAL_MACHINE;
  }
  ConfigKey = RegQueryInfoKeyW(v6, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( !ConfigKey )
  {
    ++cbMaxSubKeyLen;
    v5 = (WCHAR *)LocalAlloc(0x40u, 2 * cbMaxSubKeyLen);
    if ( v5 )
    {
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = cbMaxSubKeyLen;
        ConfigKey = RegEnumKeyExW(hKey, i, v5, &cchName, 0, 0, 0, 0);
        if ( !ConfigKey )
        {
          ConfigKey = RegOpenKeyExW(hKey, v5, 0, 0xF003Fu, &phkResult);
          if ( !ConfigKey )
          {
            ConfigKey = PortGetConfigKey(v5, phkResult, a4);
            RegCloseKey(phkResult);
            if ( ConfigKey )
              break;
          }
        }
      }
    }
    else
    {
      ConfigKey = 8;
    }
  }
LABEL_13:
  if ( hKey && v7 )
    RegCloseKey(hKey);
  if ( v5 )
    LocalFree(v5);
  return ConfigKey;
}

```

## disassembly

```asm
0x180016d4c  mov     qword ptr [rsp-38h+cbMaxSubKeyLen], r8
0x180016d51  mov     qword ptr [rsp-38h+cSubKeys], rcx
0x180016d56  push    rbp
0x180016d57  push    rbx
0x180016d58  push    rsi
0x180016d59  push    rdi
0x180016d5a  push    r12
0x180016d5c  push    r14
0x180016d5e  push    r15
0x180016d60  mov     rbp, rsp
0x180016d63  sub     rsp, 70h
0x180016d67  xor     r12d, r12d
0x180016d6a  mov     r15, r9
0x180016d6d  mov     [rbp+cbMaxSubKeyLen], r12d
0x180016d71  mov     edi, r12d
0x180016d74  mov     [rbp+cchName], r12d
0x180016d78  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016d7f  mov     [rbp+cSubKeys], r12d
0x180016d83  mov     [rbp+hKey], r12
0x180016d87  mov     [rbp+var_8], r12
0x180016d8b  test    rdx, rdx
0x180016d8e  jz      short loc_180016DBD
0x180016d90  lea     rax, [rbp+hKey]
0x180016d94  mov     r9d, 0F003Fh; samDesired
0x180016d9a  xor     r8d, r8d; ulOptions
0x180016d9d  mov     [rsp+70h+phkResult], rax; phkResult
0x180016da2  lea     r14d, [r12+1]
0x180016da7  call    cs:__imp_RegOpenKeyExW
0x180016dad  mov     ebx, eax
0x180016daf  test    eax, eax
0x180016db1  jnz     loc_180016EB7
0x180016db7  mov     rcx, [rbp+hKey]
0x180016dbb  jmp     short loc_180016DC4
0x180016dbd  mov     r14d, r12d
0x180016dc0  mov     [rbp+hKey], rcx
0x180016dc4  mov     [rsp+70h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180016dc9  lea     rax, [rbp+cbMaxSubKeyLen]
0x180016dcd  mov     [rsp+70h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180016dd2  xor     r9d, r9d; lpReserved
0x180016dd5  mov     [rsp+70h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180016dda  xor     r8d, r8d; lpcchClass
0x180016ddd  mov     [rsp+70h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180016de2  xor     edx, edx; lpClass
0x180016de4  mov     [rsp+70h+lpcValues], r12; lpcValues
0x180016de9  mov     [rsp+70h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180016dee  mov     [rsp+70h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180016df3  lea     rax, [rbp+cSubKeys]
0x180016df7  mov     [rsp+70h+phkResult], rax; lpcSubKeys
0x180016dfc  call    cs:__imp_RegQueryInfoKeyW
0x180016e02  mov     ebx, eax
0x180016e04  test    eax, eax
0x180016e06  jnz     loc_180016EB7
0x180016e0c  mov     eax, [rbp+cbMaxSubKeyLen]
0x180016e0f  lea     ecx, [rbx+40h]; uFlags
0x180016e12  inc     eax
0x180016e14  mov     [rbp+cbMaxSubKeyLen], eax
0x180016e17  lea     edx, [rax+rax]; uBytes
0x180016e1a  call    cs:__imp_LocalAlloc
0x180016e20  mov     rdi, rax
0x180016e23  test    rax, rax
0x180016e26  jnz     short loc_180016E30
0x180016e28  lea     ebx, [rax+8]
0x180016e2b  jmp     loc_180016EB7
0x180016e30  mov     esi, r12d
0x180016e33  cmp     [rbp+cSubKeys], r12d
0x180016e37  jbe     short loc_180016EB7
0x180016e39  mov     eax, [rbp+cbMaxSubKeyLen]
0x180016e3c  lea     r9, [rbp+cchName]; lpcchName
0x180016e40  mov     rcx, [rbp+hKey]; hKey
0x180016e44  mov     r8, rdi; lpName
0x180016e47  mov     [rsp+70h+lpcValues], r12; lpftLastWriteTime
0x180016e4c  mov     edx, esi; dwIndex
0x180016e4e  mov     [rsp+70h+lpcbMaxClassLen], r12; lpcchClass
0x180016e53  mov     [rsp+70h+lpcbMaxSubKeyLen], r12; lpClass
0x180016e58  mov     [rsp+70h+phkResult], r12; lpReserved
0x180016e5d  mov     [rbp+cchName], eax
0x180016e60  call    cs:__imp_RegEnumKeyExW
0x180016e66  mov     ebx, eax
0x180016e68  test    eax, eax
0x180016e6a  jnz     short loc_180016EB0
0x180016e6c  mov     rcx, [rbp+hKey]; hKey
0x180016e70  lea     rax, [rbp+var_8]
0x180016e74  mov     r9d, 0F003Fh; samDesired
0x180016e7a  mov     [rsp+70h+phkResult], rax; phkResult
0x180016e7f  xor     r8d, r8d; ulOptions
0x180016e82  mov     rdx, rdi; lpSubKey
0x180016e85  call    cs:__imp_RegOpenKeyExW
0x180016e8b  mov     ebx, eax
0x180016e8d  test    eax, eax
0x180016e8f  jnz     short loc_180016EB0
0x180016e91  mov     rdx, [rbp+var_8]
0x180016e95  mov     r8, r15
0x180016e98  mov     rcx, rdi
0x180016e9b  call    PortGetConfigKey
0x180016ea0  mov     rcx, [rbp+var_8]; hKey
0x180016ea4  mov     ebx, eax
0x180016ea6  call    cs:__imp_RegCloseKey
0x180016eac  test    ebx, ebx
0x180016eae  jnz     short loc_180016EB7
0x180016eb0  inc     esi
0x180016eb2  cmp     esi, [rbp+cSubKeys]
0x180016eb5  jb      short loc_180016E39
0x180016eb7  mov     rcx, [rbp+hKey]; hKey
0x180016ebb  test    rcx, rcx
0x180016ebe  jz      short loc_180016ECB
0x180016ec0  test    r14d, r14d
0x180016ec3  jz      short loc_180016ECB
0x180016ec5  call    cs:__imp_RegCloseKey
0x180016ecb  test    rdi, rdi
0x180016ece  jz      short loc_180016ED9
0x180016ed0  mov     rcx, rdi; hMem
0x180016ed3  call    cs:__imp_LocalFree
0x180016ed9  mov     eax, ebx
0x180016edb  add     rsp, 70h
0x180016edf  pop     r15
0x180016ee1  pop     r14
0x180016ee3  pop     r12
0x180016ee5  pop     rdi
0x180016ee6  pop     rsi
0x180016ee7  pop     rbx
0x180016ee8  pop     rbp
0x180016ee9  retn
```
