# DeleteKeyRecursivelyW

- ea: `0x180082044`
- end: `0x1800821ba`
- name: `DeleteKeyRecursivelyW`
- size: `374`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180063e00`
- `0x180082044`

## callees

- `0x180082044`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180082093`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180082093`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008212f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008212f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800820ea`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800820ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180082152`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180082152`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180082187`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180082187`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180082120`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180082120`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180082140`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180082140`

## pseudocode

```c
__int64 __fastcall DeleteKeyRecursivelyW(HKEY a1, const WCHAR *a2)
{
  unsigned int v4; // ebx
  HKEY v5; // rcx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  hKey = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x2000000u, &hKey);
  if ( !v4 )
  {
    cSubKeys = 0;
    cchName = 261;
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( !v4 )
    {
      while ( !RegEnumKeyW(hKey, --cSubKeys, Name, cchName) )
        DeleteKeyRecursivelyW(hKey, Name);
    }
    RegCloseKey(hKey);
    v5 = a1;
    if ( a2 )
    {
      return (unsigned int)RegDeleteKeyW(a1, a2);
    }
    else
    {
      while ( 1 )
      {
        cchName = 261;
        if ( RegEnumValueW(v5, 0, Name, &cchName, 0, 0, 0, 0) || RegDeleteValueW(a1, Name) )
          break;
        v5 = a1;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180082044  mov     [rsp-8+arg_10], rbx
0x180082049  mov     [rsp-8+arg_18], rsi
0x18008204e  push    rbp
0x18008204f  push    rdi
0x180082050  push    r14
0x180082052  lea     rbp, [rsp-190h]
0x18008205a  sub     rsp, 290h
0x180082061  mov     rax, cs:__security_cookie
0x180082068  xor     rax, rsp
0x18008206b  mov     [rbp+1A0h+var_20], rax
0x180082072  lea     rax, [rsp+2A0h+hKey]
0x180082077  xor     r14d, r14d
0x18008207a  mov     r9d, 2000000h; samDesired
0x180082080  mov     [rsp+2A0h+hKey], r14
0x180082085  xor     r8d, r8d; ulOptions
0x180082088  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18008208d  mov     rsi, rdx
0x180082090  mov     rdi, rcx
0x180082093  call    cs:__imp_RegOpenKeyExW
0x180082099  mov     ebx, eax
0x18008209b  test    eax, eax
0x18008209d  jnz     loc_180082191
0x1800820a3  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800820a8  lea     rax, [rsp+2A0h+cSubKeys]
0x1800820ad  mov     [rsp+2A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800820b2  xor     r9d, r9d; lpReserved
0x1800820b5  mov     [rsp+2A0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800820ba  xor     r8d, r8d; lpcchClass
0x1800820bd  mov     [rsp+2A0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800820c2  xor     edx, edx; lpClass
0x1800820c4  mov     [rsp+2A0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800820c9  mov     [rsp+2A0h+lpcValues], r14; lpcValues
0x1800820ce  mov     [rsp+2A0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800820d3  mov     [rsp+2A0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800820d8  mov     [rsp+2A0h+phkResult], rax; lpcSubKeys
0x1800820dd  mov     [rsp+2A0h+cSubKeys], r14d
0x1800820e2  mov     [rsp+2A0h+cchName], 105h
0x1800820ea  call    cs:__imp_RegQueryInfoKeyW
0x1800820f0  mov     ebx, eax
0x1800820f2  test    eax, eax
0x1800820f4  jnz     short loc_18008212A
0x1800820f6  jmp     short loc_180082107
0x1800820f8  mov     rcx, [rsp+2A0h+hKey]
0x1800820fd  lea     rdx, [rsp+2A0h+Name]
0x180082102  call    DeleteKeyRecursivelyW
0x180082107  mov     edx, [rsp+2A0h+cSubKeys]
0x18008210b  lea     r8, [rsp+2A0h+Name]; lpName
0x180082110  mov     r9d, [rsp+2A0h+cchName]; cchName
0x180082115  dec     edx; dwIndex
0x180082117  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18008211c  mov     [rsp+2A0h+cSubKeys], edx
0x180082120  call    cs:__imp_RegEnumKeyW
0x180082126  test    eax, eax
0x180082128  jz      short loc_1800820F8
0x18008212a  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18008212f  call    cs:__imp_RegCloseKey
0x180082135  mov     rcx, rdi; hKey
0x180082138  test    rsi, rsi
0x18008213b  jz      short loc_18008215F
0x18008213d  mov     rdx, rsi; lpSubKey
0x180082140  call    cs:__imp_RegDeleteKeyW
0x180082146  mov     ebx, eax
0x180082148  jmp     short loc_180082191
0x18008214a  lea     rdx, [rsp+2A0h+Name]; lpValueName
0x18008214f  mov     rcx, rdi; hKey
0x180082152  call    cs:__imp_RegDeleteValueW
0x180082158  test    eax, eax
0x18008215a  jnz     short loc_180082191
0x18008215c  mov     rcx, rdi; hKey
0x18008215f  mov     [rsp+2A0h+lpcValues], r14; lpcbData
0x180082164  lea     r9, [rsp+2A0h+cchName]; lpcchValueName
0x180082169  mov     [rsp+2A0h+lpcbMaxClassLen], r14; lpData
0x18008216e  lea     r8, [rsp+2A0h+Name]; lpValueName
0x180082173  mov     [rsp+2A0h+lpcbMaxSubKeyLen], r14; lpType
0x180082178  xor     edx, edx; dwIndex
0x18008217a  mov     [rsp+2A0h+phkResult], r14; lpReserved
0x18008217f  mov     [rsp+2A0h+cchName], 105h
0x180082187  call    cs:__imp_RegEnumValueW
0x18008218d  test    eax, eax
0x18008218f  jz      short loc_18008214A
0x180082191  mov     eax, ebx
0x180082193  mov     rcx, [rbp+1A0h+var_20]
0x18008219a  xor     rcx, rsp; StackCookie
0x18008219d  call    __security_check_cookie
0x1800821a2  lea     r11, [rsp+2A0h+var_10]
0x1800821aa  mov     rbx, [r11+30h]
0x1800821ae  mov     rsi, [r11+38h]
0x1800821b2  mov     rsp, r11
0x1800821b5  pop     r14
0x1800821b7  pop     rdi
0x1800821b8  pop     rbp
0x1800821b9  retn
```
