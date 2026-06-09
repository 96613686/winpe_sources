# RecursivelyDeleteRegistryTree

- ea: `0x18003592c`
- end: `0x180035ac5`
- name: `RecursivelyDeleteRegistryTree`
- size: `409`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800317c8`
- `0x180032294`
- `0x180034690`
- `0x18003592c`
- `0x180035bc0`

## callees

- `0x1800222f0`
- `0x1800327a8`
- `0x1800327f0`
- `0x18003592c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800359fb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800359fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035a3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035a94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035a3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180035a94`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035987`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180035987`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180035a6a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180035a6a`

## string_xrefs

- `0x1800359b1`: `Could not open key to delete`
- `0x180035a2a`: `Failed to recursively delete subtree`
- `0x180035a7c`: `Failed to delete target key`

## pseudocode

```c
__int64 __fastcall RecursivelyDeleteRegistryTree(HKEY a1, const WCHAR *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  const wchar_t *v6; // rdx
  __int64 v7; // rcx
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[256]; // [rsp+60h] [rbp-A0h] BYREF

  ftLastWriteTime = 0;
  cchName = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0xF003Fu, &hKey);
  v5 = v4;
  if ( v4 == 2 )
  {
    LogMsg(L"Root key does not exist");
    v5 = 0;
    goto LABEL_15;
  }
  if ( v4 )
  {
    v6 = L"Could not open key to delete";
LABEL_13:
    v7 = v4;
    goto LABEL_14;
  }
  do
  {
    cchName = 256;
    v5 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( v5 )
      break;
    v5 = RecursivelyDeleteRegistryTree(hKey, Name);
  }
  while ( !v5 );
  if ( v5 == 259 )
  {
    v4 = RegCloseKey(hKey);
    hKey = 0;
    v5 = v4;
    if ( v4 )
    {
      v6 = L"Failed to close target key";
    }
    else
    {
      v4 = RegDeleteKeyExW(a1, a2, 0, 0);
      v5 = v4;
      if ( !v4 )
        goto LABEL_15;
      v6 = L"Failed to delete target key";
    }
    goto LABEL_13;
  }
  v6 = L"Failed to recursively delete subtree";
  v7 = v5;
LABEL_14:
  LogError(v7, v6);
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x18003592c  mov     [rsp-8+arg_10], rbx
0x180035931  push    rbp
0x180035932  push    rsi
0x180035933  push    rdi
0x180035934  lea     rbp, [rsp-170h]
0x18003593c  sub     rsp, 270h
0x180035943  mov     rax, cs:__security_cookie
0x18003594a  xor     rax, rsp
0x18003594d  mov     [rbp+180h+var_20], rax
0x180035954  lea     rax, [rsp+280h+hKey]
0x180035959  mov     qword ptr [rsp+280h+ftLastWriteTime.dwLowDateTime], 0
0x180035962  mov     r9d, 0F003Fh; samDesired
0x180035968  mov     [rsp+280h+phkResult], rax; phkResult
0x18003596d  xor     r8d, r8d; ulOptions
0x180035970  mov     [rsp+280h+cchName], 0
0x180035978  mov     rsi, rdx
0x18003597b  mov     [rsp+280h+hKey], 0
0x180035984  mov     rdi, rcx
0x180035987  call    cs:__imp_RegOpenKeyExW
0x18003598e  nop     dword ptr [rax+rax+00h]
0x180035993  mov     ebx, eax
0x180035995  cmp     eax, 2
0x180035998  jnz     short loc_1800359AD
0x18003599a  lea     rcx, aRootKeyDoesNot; "Root key does not exist"
0x1800359a1  call    LogMsg
0x1800359a6  xor     ebx, ebx
0x1800359a8  jmp     loc_180035A8A
0x1800359ad  test    eax, eax
0x1800359af  jz      short loc_1800359BD
0x1800359b1  lea     rdx, aCouldNotOpenKe_0; "Could not open key to delete"
0x1800359b8  jmp     loc_180035A83
0x1800359bd  mov     rcx, [rsp+280h+hKey]; hKey
0x1800359c2  lea     rax, [rsp+280h+ftLastWriteTime]
0x1800359c7  mov     [rsp+280h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800359cc  lea     r9, [rsp+280h+cchName]; lpcchName
0x1800359d1  mov     [rsp+280h+lpcchClass], 0; lpcchClass
0x1800359da  lea     r8, [rsp+280h+Name]; lpName
0x1800359df  mov     [rsp+280h+lpClass], 0; lpClass
0x1800359e8  xor     edx, edx; dwIndex
0x1800359ea  mov     [rsp+280h+phkResult], 0; lpReserved
0x1800359f3  mov     [rsp+280h+cchName], 100h
0x1800359fb  call    cs:__imp_RegEnumKeyExW
0x180035a02  nop     dword ptr [rax+rax+00h]
0x180035a07  mov     ebx, eax
0x180035a09  test    eax, eax
0x180035a0b  jnz     short loc_180035A22
0x180035a0d  mov     rcx, [rsp+280h+hKey]
0x180035a12  lea     rdx, [rsp+280h+Name]
0x180035a17  call    RecursivelyDeleteRegistryTree
0x180035a1c  mov     ebx, eax
0x180035a1e  test    eax, eax
0x180035a20  jz      short loc_1800359BD
0x180035a22  cmp     ebx, 103h
0x180035a28  jz      short loc_180035A35
0x180035a2a  lea     rdx, aFailedToRecurs; "Failed to recursively delete subtree"
0x180035a31  mov     ecx, ebx
0x180035a33  jmp     short loc_180035A85
0x180035a35  mov     rcx, [rsp+280h+hKey]; hKey
0x180035a3a  call    cs:__imp_RegCloseKey
0x180035a41  nop     dword ptr [rax+rax+00h]
0x180035a46  mov     [rsp+280h+hKey], 0
0x180035a4f  mov     ebx, eax
0x180035a51  test    eax, eax
0x180035a53  jz      short loc_180035A5E
0x180035a55  lea     rdx, aFailedToCloseT; "Failed to close target key"
0x180035a5c  jmp     short loc_180035A83
0x180035a5e  xor     r9d, r9d; Reserved
0x180035a61  xor     r8d, r8d; samDesired
0x180035a64  mov     rdx, rsi; lpSubKey
0x180035a67  mov     rcx, rdi; hKey
0x180035a6a  call    cs:__imp_RegDeleteKeyExW
0x180035a71  nop     dword ptr [rax+rax+00h]
0x180035a76  mov     ebx, eax
0x180035a78  test    eax, eax
0x180035a7a  jz      short loc_180035A8A
0x180035a7c  lea     rdx, aFailedToDelete; "Failed to delete target key"
0x180035a83  mov     ecx, eax
0x180035a85  call    LogError
0x180035a8a  mov     rcx, [rsp+280h+hKey]; hKey
0x180035a8f  test    rcx, rcx
0x180035a92  jz      short loc_180035AA0
0x180035a94  call    cs:__imp_RegCloseKey
0x180035a9b  nop     dword ptr [rax+rax+00h]
0x180035aa0  mov     eax, ebx
0x180035aa2  mov     rcx, [rbp+180h+var_20]
0x180035aa9  xor     rcx, rsp; StackCookie
0x180035aac  call    __security_check_cookie
0x180035ab1  mov     rbx, [rsp+280h+arg_10]
0x180035ab9  add     rsp, 270h
0x180035ac0  pop     rdi
0x180035ac1  pop     rsi
0x180035ac2  pop     rbp
0x180035ac3  retn
```
