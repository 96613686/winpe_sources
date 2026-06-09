# DhcpRegDeleteKey

- ea: `0x18001d640`
- end: `0x18001d81e`
- name: `DhcpRegDeleteKey`
- size: `478`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001d640`
- `0x180085840`
- `0x180086300`
- `0x1800a1004`

## callees

- `0x18001d640`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18001d71a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001d71a`
- `ADVAPI32!RegCloseKey` at `0x18001d7b5`
- `ADVAPI32!RegCloseKey` at `0x18001d7e8`
- `ADVAPI32!RegCloseKey` at `0x18001d7b5`
- `ADVAPI32!RegCloseKey` at `0x18001d7e8`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d6a5`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d6a5`
- `ADVAPI32!RegDeleteKeyW` at `0x18001d7d0`
- `ADVAPI32!RegDeleteKeyW` at `0x18001d7d0`
- `ADVAPI32!RegEnumKeyExW` at `0x18001d783`
- `ADVAPI32!RegEnumKeyExW` at `0x18001d783`

## pseudocode

```c
__int64 __fastcall DhcpRegDeleteKey(HKEY a1, const WCHAR *a2)
{
  unsigned int v4; // ebx
  int v5; // edi
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME v9; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Class[20]; // [rsp+80h] [rbp-80h] BYREF
  DWORD cchClass; // [rsp+A8h] [rbp-58h] BYREF
  DWORD cSubKeys; // [rsp+ACh] [rbp-54h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+B0h] [rbp-50h] BYREF
  DWORD cbMaxClassLen; // [rsp+B4h] [rbp-4Ch] BYREF
  DWORD cValues; // [rsp+B8h] [rbp-48h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+BCh] [rbp-44h] BYREF
  DWORD cbMaxValueLen; // [rsp+C0h] [rbp-40h] BYREF
  DWORD cbSecurityDescriptor; // [rsp+C4h] [rbp-3Ch] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+C8h] [rbp-38h] BYREF
  WCHAR SubKey[104]; // [rsp+D0h] [rbp-30h] BYREF

  hKey = 0;
  memset_0(Class, 0, 0x50u);
  v4 = RegOpenKeyExW(a1, a2, 0, 0xFu, &hKey);
  if ( !v4 )
  {
    cchClass = 20;
    v4 = RegQueryInfoKeyW(
           hKey,
           Class,
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
    if ( !v4 )
    {
      if ( cSubKeys )
      {
        v5 = 0;
        v9 = 0;
        while ( 1 )
        {
          cchName = 100;
          v4 = RegEnumKeyExW(hKey, 0, SubKey, &cchName, 0, 0, 0, &v9);
          if ( v4 )
            break;
          v4 = DhcpRegDeleteKey(hKey, SubKey);
          if ( v4 )
            break;
          if ( ++v5 >= cSubKeys )
            goto LABEL_8;
        }
      }
      else
      {
LABEL_8:
        RegCloseKey(hKey);
        hKey = 0;
        v4 = RegDeleteKeyW(a1, a2);
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18001d640  mov     [rsp-8+arg_10], rbx
0x18001d645  mov     [rsp-8+arg_18], rsi
0x18001d64a  push    rbp
0x18001d64b  push    rdi
0x18001d64c  push    r14
0x18001d64e  lea     rbp, [rsp-0B0h]
0x18001d656  sub     rsp, 1B0h
0x18001d65d  mov     rax, cs:__security_cookie
0x18001d664  xor     rax, rsp
0x18001d667  mov     [rbp+0C0h+var_20], rax
0x18001d66e  mov     r14, rdx
0x18001d671  mov     [rsp+1C0h+hKey], 0
0x18001d67a  xor     edx, edx; Val
0x18001d67c  mov     rsi, rcx
0x18001d67f  lea     rcx, [rbp+0C0h+Class]; void *
0x18001d683  lea     r8d, [rdx+50h]; Size
0x18001d687  call    memset_0
0x18001d68c  lea     rax, [rsp+1C0h+hKey]
0x18001d691  mov     r9d, 0Fh; samDesired
0x18001d697  xor     r8d, r8d; ulOptions
0x18001d69a  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18001d69f  mov     rdx, r14; lpSubKey
0x18001d6a2  mov     rcx, rsi; hKey
0x18001d6a5  call    cs:__imp_RegOpenKeyExW
0x18001d6ac  nop     dword ptr [rax+rax+00h]
0x18001d6b1  mov     ebx, eax
0x18001d6b3  test    eax, eax
0x18001d6b5  jnz     loc_18001D7DE
0x18001d6bb  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001d6c0  lea     rax, [rbp+0C0h+ftLastWriteTime]
0x18001d6c4  mov     [rsp+1C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001d6c9  lea     r8, [rbp+0C0h+cchClass]; lpcchClass
0x18001d6cd  lea     rax, [rbp+0C0h+cbSecurityDescriptor]
0x18001d6d1  mov     [rbp+0C0h+cchClass], 14h
0x18001d6d8  mov     [rsp+1C0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x18001d6dd  lea     rdx, [rbp+0C0h+Class]; lpClass
0x18001d6e1  lea     rax, [rbp+0C0h+cbMaxValueLen]
0x18001d6e5  xor     r9d, r9d; lpReserved
0x18001d6e8  mov     [rsp+1C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18001d6ed  lea     rax, [rbp+0C0h+cbMaxValueNameLen]
0x18001d6f1  mov     [rsp+1C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18001d6f6  lea     rax, [rbp+0C0h+cValues]
0x18001d6fa  mov     [rsp+1C0h+lpcValues], rax; lpcValues
0x18001d6ff  lea     rax, [rbp+0C0h+cbMaxClassLen]
0x18001d703  mov     [rsp+1C0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x18001d708  lea     rax, [rbp+0C0h+cbMaxSubKeyLen]
0x18001d70c  mov     [rsp+1C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18001d711  lea     rax, [rbp+0C0h+cSubKeys]
0x18001d715  mov     [rsp+1C0h+phkResult], rax; lpcSubKeys
0x18001d71a  call    cs:__imp_RegQueryInfoKeyW
0x18001d721  nop     dword ptr [rax+rax+00h]
0x18001d726  mov     ebx, eax
0x18001d728  test    eax, eax
0x18001d72a  jnz     loc_18001D7DE
0x18001d730  mov     eax, [rbp+0C0h+cSubKeys]
0x18001d733  test    eax, eax
0x18001d735  jz      short loc_18001D7B0
0x18001d737  xor     edi, edi
0x18001d739  mov     qword ptr [rsp+1C0h+var_150.dwLowDateTime], 0
0x18001d742  test    eax, eax
0x18001d744  jz      short loc_18001D7B0
0x18001d746  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001d74b  lea     rax, [rsp+1C0h+var_150]
0x18001d750  mov     [rsp+1C0h+lpcValues], rax; lpftLastWriteTime
0x18001d755  lea     r9, [rsp+1C0h+cchName]; lpcchName
0x18001d75a  mov     [rsp+1C0h+lpcbMaxClassLen], 0; lpcchClass
0x18001d763  lea     r8, [rbp+0C0h+SubKey]; lpName
0x18001d767  mov     [rsp+1C0h+lpcbMaxSubKeyLen], 0; lpClass
0x18001d770  xor     edx, edx; dwIndex
0x18001d772  mov     [rsp+1C0h+phkResult], 0; lpReserved
0x18001d77b  mov     [rsp+1C0h+cchName], 64h ; 'd'
0x18001d783  call    cs:__imp_RegEnumKeyExW
0x18001d78a  nop     dword ptr [rax+rax+00h]
0x18001d78f  mov     ebx, eax
0x18001d791  test    eax, eax
0x18001d793  jnz     short loc_18001D7DE
0x18001d795  mov     rcx, [rsp+1C0h+hKey]
0x18001d79a  lea     rdx, [rbp+0C0h+SubKey]
0x18001d79e  call    DhcpRegDeleteKey
0x18001d7a3  mov     ebx, eax
0x18001d7a5  test    eax, eax
0x18001d7a7  jnz     short loc_18001D7DE
0x18001d7a9  inc     edi
0x18001d7ab  cmp     edi, [rbp+0C0h+cSubKeys]
0x18001d7ae  jb      short loc_18001D746
0x18001d7b0  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001d7b5  call    cs:__imp_RegCloseKey
0x18001d7bc  nop     dword ptr [rax+rax+00h]
0x18001d7c1  mov     rdx, r14; lpSubKey
0x18001d7c4  mov     [rsp+1C0h+hKey], 0
0x18001d7cd  mov     rcx, rsi; hKey
0x18001d7d0  call    cs:__imp_RegDeleteKeyW
0x18001d7d7  nop     dword ptr [rax+rax+00h]
0x18001d7dc  mov     ebx, eax
0x18001d7de  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001d7e3  test    rcx, rcx
0x18001d7e6  jz      short loc_18001D7F4
0x18001d7e8  call    cs:__imp_RegCloseKey
0x18001d7ef  nop     dword ptr [rax+rax+00h]
0x18001d7f4  mov     eax, ebx
0x18001d7f6  mov     rcx, [rbp+0C0h+var_20]
0x18001d7fd  xor     rcx, rsp; StackCookie
0x18001d800  call    __security_check_cookie
0x18001d805  lea     r11, [rsp+1C0h+var_10]
0x18001d80d  mov     rbx, [r11+30h]
0x18001d811  mov     rsi, [r11+38h]
0x18001d815  mov     rsp, r11
0x18001d818  pop     r14
0x18001d81a  pop     rdi
0x18001d81b  pop     rbp
0x18001d81c  retn
```
