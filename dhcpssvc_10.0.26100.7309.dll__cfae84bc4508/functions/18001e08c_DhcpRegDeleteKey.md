# DhcpRegDeleteKey

- ea: `0x18001e08c`
- end: `0x18001e258`
- name: `DhcpRegDeleteKey`
- size: `460`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001e08c`
- `0x180085940`
- `0x1800863f0`
- `0x1800a032c`

## callees

- `0x18001e08c`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18001e163`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18001e163`
- `ADVAPI32!RegCloseKey` at `0x18001e1f2`
- `ADVAPI32!RegCloseKey` at `0x18001e222`
- `ADVAPI32!RegCloseKey` at `0x18001e1f2`
- `ADVAPI32!RegCloseKey` at `0x18001e222`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e0ee`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e0ee`
- `ADVAPI32!RegDeleteKeyW` at `0x18001e20a`
- `ADVAPI32!RegDeleteKeyW` at `0x18001e20a`
- `ADVAPI32!RegEnumKeyExW` at `0x18001e1c0`
- `ADVAPI32!RegEnumKeyExW` at `0x18001e1c0`

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
        v9 = 0;
        v5 = 0;
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
0x18001e08c  mov     [rsp-8+arg_10], rbx
0x18001e091  mov     [rsp-8+arg_18], rsi
0x18001e096  push    rbp
0x18001e097  push    rdi
0x18001e098  push    r14
0x18001e09a  lea     rbp, [rsp-0B0h]
0x18001e0a2  sub     rsp, 1B0h
0x18001e0a9  mov     rax, cs:__security_cookie
0x18001e0b0  xor     rax, rsp
0x18001e0b3  mov     [rbp+0C0h+var_20], rax
0x18001e0ba  and     [rsp+1C0h+hKey], 0
0x18001e0c0  mov     r14, rdx
0x18001e0c3  xor     edx, edx; Val
0x18001e0c5  mov     rsi, rcx
0x18001e0c8  lea     rcx, [rbp+0C0h+Class]; void *
0x18001e0cc  lea     r8d, [rdx+50h]; Size
0x18001e0d0  call    memset_0
0x18001e0d5  lea     rax, [rsp+1C0h+hKey]
0x18001e0da  mov     r9d, 0Fh; samDesired
0x18001e0e0  xor     r8d, r8d; ulOptions
0x18001e0e3  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18001e0e8  mov     rdx, r14; lpSubKey
0x18001e0eb  mov     rcx, rsi; hKey
0x18001e0ee  call    cs:__imp_RegOpenKeyExW
0x18001e0f5  nop     dword ptr [rax+rax+00h]
0x18001e0fa  mov     ebx, eax
0x18001e0fc  test    eax, eax
0x18001e0fe  jnz     loc_18001E218
0x18001e104  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001e109  lea     rax, [rbp+0C0h+ftLastWriteTime]
0x18001e10d  mov     [rsp+1C0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001e112  lea     r8, [rbp+0C0h+cchClass]; lpcchClass
0x18001e116  lea     rax, [rbp+0C0h+cbSecurityDescriptor]
0x18001e11a  mov     [rbp+0C0h+cchClass], 14h
0x18001e121  mov     [rsp+1C0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x18001e126  lea     rdx, [rbp+0C0h+Class]; lpClass
0x18001e12a  lea     rax, [rbp+0C0h+cbMaxValueLen]
0x18001e12e  xor     r9d, r9d; lpReserved
0x18001e131  mov     [rsp+1C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18001e136  lea     rax, [rbp+0C0h+cbMaxValueNameLen]
0x18001e13a  mov     [rsp+1C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18001e13f  lea     rax, [rbp+0C0h+cValues]
0x18001e143  mov     [rsp+1C0h+lpcValues], rax; lpcValues
0x18001e148  lea     rax, [rbp+0C0h+cbMaxClassLen]
0x18001e14c  mov     [rsp+1C0h+lpcbMaxClassLen], rax; lpcchClass
0x18001e151  lea     rax, [rbp+0C0h+cbMaxSubKeyLen]
0x18001e155  mov     [rsp+1C0h+lpcbMaxSubKeyLen], rax; lpClass
0x18001e15a  lea     rax, [rbp+0C0h+cSubKeys]
0x18001e15e  mov     [rsp+1C0h+phkResult], rax; lpReserved
0x18001e163  call    cs:__imp_RegQueryInfoKeyW
0x18001e16a  nop     dword ptr [rax+rax+00h]
0x18001e16f  mov     ebx, eax
0x18001e171  test    eax, eax
0x18001e173  jnz     loc_18001E218
0x18001e179  mov     eax, [rbp+0C0h+cSubKeys]
0x18001e17c  test    eax, eax
0x18001e17e  jz      short loc_18001E1ED
0x18001e180  and     qword ptr [rsp+1C0h+var_150.dwLowDateTime], 0
0x18001e186  xor     edi, edi
0x18001e188  test    eax, eax
0x18001e18a  jz      short loc_18001E1ED
0x18001e18c  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001e191  lea     rax, [rsp+1C0h+var_150]
0x18001e196  mov     [rsp+1C0h+lpcValues], rax; lpftLastWriteTime
0x18001e19b  lea     r9, [rsp+1C0h+cchName]; lpcchName
0x18001e1a0  and     [rsp+1C0h+lpcbMaxClassLen], 0
0x18001e1a6  lea     r8, [rbp+0C0h+SubKey]; lpName
0x18001e1aa  and     [rsp+1C0h+lpcbMaxSubKeyLen], 0
0x18001e1b0  xor     edx, edx; dwIndex
0x18001e1b2  and     [rsp+1C0h+phkResult], 0
0x18001e1b8  mov     [rsp+1C0h+cchName], 64h ; 'd'
0x18001e1c0  call    cs:__imp_RegEnumKeyExW
0x18001e1c7  nop     dword ptr [rax+rax+00h]
0x18001e1cc  mov     ebx, eax
0x18001e1ce  test    eax, eax
0x18001e1d0  jnz     short loc_18001E218
0x18001e1d2  mov     rcx, [rsp+1C0h+hKey]
0x18001e1d7  lea     rdx, [rbp+0C0h+SubKey]
0x18001e1db  call    DhcpRegDeleteKey
0x18001e1e0  mov     ebx, eax
0x18001e1e2  test    eax, eax
0x18001e1e4  jnz     short loc_18001E218
0x18001e1e6  inc     edi
0x18001e1e8  cmp     edi, [rbp+0C0h+cSubKeys]
0x18001e1eb  jb      short loc_18001E18C
0x18001e1ed  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001e1f2  call    cs:__imp_RegCloseKey
0x18001e1f9  nop     dword ptr [rax+rax+00h]
0x18001e1fe  and     [rsp+1C0h+hKey], 0
0x18001e204  mov     rdx, r14; lpSubKey
0x18001e207  mov     rcx, rsi; hKey
0x18001e20a  call    cs:__imp_RegDeleteKeyW
0x18001e211  nop     dword ptr [rax+rax+00h]
0x18001e216  mov     ebx, eax
0x18001e218  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18001e21d  test    rcx, rcx
0x18001e220  jz      short loc_18001E22E
0x18001e222  call    cs:__imp_RegCloseKey
0x18001e229  nop     dword ptr [rax+rax+00h]
0x18001e22e  mov     eax, ebx
0x18001e230  mov     rcx, [rbp+0C0h+var_20]
0x18001e237  xor     rcx, rsp; StackCookie
0x18001e23a  call    __security_check_cookie
0x18001e23f  lea     r11, [rsp+1C0h+var_10]
0x18001e247  mov     rbx, [r11+30h]
0x18001e24b  mov     rsi, [r11+38h]
0x18001e24f  mov     rsp, r11
0x18001e252  pop     r14
0x18001e254  pop     rdi
0x18001e255  pop     rbp
0x18001e256  retn
```
