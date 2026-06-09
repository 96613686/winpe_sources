# DhcpRegRecurseDeleteSub

- ea: `0x18000e04c`
- end: `0x18000e1da`
- name: `DhcpRegRecurseDeleteSub`
- size: `398`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e000`

## callees

- `0x1800048c0`
- `0x180005162`
- `0x18000e000`
- `0x18000e04c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e09c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e09c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000e0fc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000e171`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000e0fc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000e171`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000e18d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18000e18d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e1a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e1a5`

## pseudocode

```c
LSTATUS __fastcall DhcpRegRecurseDeleteSub(HKEY a1, const WCHAR *a2)
{
  LSTATUS result; // eax
  DWORD i; // edi
  LSTATUS v4; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[512]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  ftLastWriteTime = 0;
  result = RegOpenKeyExW(a1, a2, 0, 0xF003Fu, &hKey);
  if ( !result )
  {
    for ( i = 0; ; ++i )
    {
      memset_0(Name, 0, sizeof(Name));
      cchName = 512;
      v4 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( v4 )
        break;
      v4 = DhcpRegRecurseDelete(hKey, Name);
      if ( v4 )
        break;
      memset_0(Name, 0, sizeof(Name));
      cchName = 512;
      v4 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( v4 )
        break;
      v4 = RegDeleteKeyExW(hKey, Name, 0, 0);
      if ( v4 )
        break;
    }
    RegCloseKey(hKey);
    result = 0;
    if ( v4 != 259 )
      return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18000e04c  mov     [rsp-8+arg_10], rbx
0x18000e051  mov     [rsp-8+arg_18], rdi
0x18000e056  push    rbp
0x18000e057  lea     rbp, [rsp-370h]
0x18000e05f  sub     rsp, 470h
0x18000e066  mov     rax, cs:__security_cookie
0x18000e06d  xor     rax, rsp
0x18000e070  mov     [rbp+370h+var_10], rax
0x18000e077  lea     rax, [rsp+470h+hKey]
0x18000e07c  mov     [rsp+470h+hKey], 0
0x18000e085  mov     r9d, 0F003Fh; samDesired
0x18000e08b  mov     [rsp+470h+phkResult], rax; phkResult
0x18000e090  xor     r8d, r8d; ulOptions
0x18000e093  mov     qword ptr [rsp+470h+ftLastWriteTime.dwLowDateTime], 0
0x18000e09c  call    cs:__imp_RegOpenKeyExW
0x18000e0a2  test    eax, eax
0x18000e0a4  jnz     loc_18000E1B6
0x18000e0aa  xor     edi, edi
0x18000e0ac  xor     edx, edx; Val
0x18000e0ae  lea     rcx, [rsp+470h+Name]; void *
0x18000e0b3  mov     r8d, 400h; Size
0x18000e0b9  call    memset_0
0x18000e0be  mov     rcx, [rsp+470h+hKey]; hKey
0x18000e0c3  lea     rax, [rsp+470h+ftLastWriteTime]
0x18000e0c8  mov     [rsp+470h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000e0cd  lea     r9, [rsp+470h+cchName]; lpcchName
0x18000e0d2  mov     [rsp+470h+lpcchClass], 0; lpcchClass
0x18000e0db  lea     r8, [rsp+470h+Name]; lpName
0x18000e0e0  mov     [rsp+470h+lpClass], 0; lpClass
0x18000e0e9  mov     edx, edi; dwIndex
0x18000e0eb  mov     [rsp+470h+phkResult], 0; lpReserved
0x18000e0f4  mov     [rsp+470h+cchName], 200h
0x18000e0fc  call    cs:__imp_RegEnumKeyExW
0x18000e102  mov     ebx, eax
0x18000e104  test    eax, eax
0x18000e106  jnz     loc_18000E1A0
0x18000e10c  mov     rcx, [rsp+470h+hKey]; hKey
0x18000e111  lea     rdx, [rsp+470h+Name]; lpSubKey
0x18000e116  call    DhcpRegRecurseDelete
0x18000e11b  mov     ebx, eax
0x18000e11d  test    eax, eax
0x18000e11f  jnz     short loc_18000E1A0
0x18000e121  xor     edx, edx; Val
0x18000e123  lea     rcx, [rsp+470h+Name]; void *
0x18000e128  mov     r8d, 400h; Size
0x18000e12e  call    memset_0
0x18000e133  mov     rcx, [rsp+470h+hKey]; hKey
0x18000e138  lea     rax, [rsp+470h+ftLastWriteTime]
0x18000e13d  mov     [rsp+470h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000e142  lea     r9, [rsp+470h+cchName]; lpcchName
0x18000e147  mov     [rsp+470h+lpcchClass], 0; lpcchClass
0x18000e150  lea     r8, [rsp+470h+Name]; lpName
0x18000e155  mov     [rsp+470h+lpClass], 0; lpClass
0x18000e15e  mov     edx, edi; dwIndex
0x18000e160  mov     [rsp+470h+phkResult], 0; lpReserved
0x18000e169  mov     [rsp+470h+cchName], 200h
0x18000e171  call    cs:__imp_RegEnumKeyExW
0x18000e177  mov     ebx, eax
0x18000e179  test    eax, eax
0x18000e17b  jnz     short loc_18000E1A0
0x18000e17d  mov     rcx, [rsp+470h+hKey]; hKey
0x18000e182  lea     rdx, [rsp+470h+Name]; lpSubKey
0x18000e187  xor     r9d, r9d; Reserved
0x18000e18a  xor     r8d, r8d; samDesired
0x18000e18d  call    cs:__imp_RegDeleteKeyExW
0x18000e193  mov     ebx, eax
0x18000e195  test    eax, eax
0x18000e197  jnz     short loc_18000E1A0
0x18000e199  inc     edi
0x18000e19b  jmp     loc_18000E0AC
0x18000e1a0  mov     rcx, [rsp+470h+hKey]; hKey
0x18000e1a5  call    cs:__imp_RegCloseKey
0x18000e1ab  xor     eax, eax
0x18000e1ad  cmp     ebx, 103h
0x18000e1b3  cmovnz  eax, ebx
0x18000e1b6  mov     rcx, [rbp+370h+var_10]
0x18000e1bd  xor     rcx, rsp; StackCookie
0x18000e1c0  call    __security_check_cookie
0x18000e1c5  lea     r11, [rsp+470h+var_s0]
0x18000e1cd  mov     rbx, [r11+20h]
0x18000e1d1  mov     rdi, [r11+28h]
0x18000e1d5  mov     rsp, r11
0x18000e1d8  pop     rbp
0x18000e1d9  retn
```
