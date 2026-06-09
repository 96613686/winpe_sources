# LockoutKey::clear(void)

- ea: `0x180011d10`
- end: `0x180011df1`
- name: `?clear@LockoutKey@@IEAAXXZ`
- size: `225`
- prototype: `void __fastcall(LockoutKey *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001215c`

## callees

- `0x180011d10`
- `0x18002b4a0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x180011d71`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180011d71`
- `ADVAPI32!RegEnumKeyExW` at `0x180011daf`
- `ADVAPI32!RegEnumKeyExW` at `0x180011daf`
- `ADVAPI32!RegDeleteKeyW` at `0x180011dc2`
- `ADVAPI32!RegDeleteKeyW` at `0x180011dc2`

## pseudocode

```c
void __fastcall LockoutKey::clear(LockoutKey *this)
{
  HKEY v2; // rcx
  HKEY v3; // rcx
  DWORD v4; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-258h] BYREF
  DWORD cchName[3]; // [rsp+64h] [rbp-254h] BYREF
  WCHAR Name[280]; // [rsp+70h] [rbp-248h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 1);
  cSubKeys = 0;
  if ( !RegQueryInfoKeyW(v2, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) )
  {
    while ( 1 )
    {
      v4 = cSubKeys;
      if ( !cSubKeys )
        break;
      v3 = (HKEY)*((_QWORD *)this + 1);
      --cSubKeys;
      cchName[0] = 273;
      if ( !RegEnumKeyExW(v3, v4 - 1, Name, cchName, 0, 0, 0, 0) )
        RegDeleteKeyW(*((HKEY *)this + 1), Name);
    }
  }
}

```

## disassembly

```asm
0x180011d10  mov     [rsp+arg_8], rbx
0x180011d15  push    rdi
0x180011d16  sub     rsp, 2B0h
0x180011d1d  mov     rax, cs:__security_cookie
0x180011d24  xor     rax, rsp
0x180011d27  mov     [rsp+2B8h+var_18], rax
0x180011d2f  xor     edi, edi
0x180011d31  lea     rax, [rsp+2B8h+cSubKeys]
0x180011d36  mov     [rsp+2B8h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180011d3b  mov     rbx, rcx
0x180011d3e  mov     rcx, [rcx+8]; hKey
0x180011d42  xor     r9d, r9d; lpReserved
0x180011d45  mov     [rsp+2B8h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180011d4a  xor     r8d, r8d; lpcchClass
0x180011d4d  mov     [rsp+2B8h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180011d52  xor     edx, edx; lpClass
0x180011d54  mov     [rsp+2B8h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180011d59  mov     [rsp+2B8h+lpcValues], rdi; lpcValues
0x180011d5e  mov     [rsp+2B8h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180011d63  mov     [rsp+2B8h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x180011d68  mov     [rsp+2B8h+lpcSubKeys], rax; lpcSubKeys
0x180011d6d  mov     [rsp+2B8h+cSubKeys], edi
0x180011d71  call    cs:__imp_RegQueryInfoKeyW
0x180011d77  test    eax, eax
0x180011d79  jnz     short loc_180011DD0
0x180011d7b  jmp     short loc_180011DC8
0x180011d7d  mov     rcx, [rbx+8]; hKey
0x180011d81  lea     r9, [rsp+2B8h+cchName]; lpcchName
0x180011d86  dec     eax
0x180011d88  mov     [rsp+2B8h+lpcValues], rdi; lpftLastWriteTime
0x180011d8d  mov     [rsp+2B8h+lpcbMaxClassLen], rdi; lpcchClass
0x180011d92  lea     r8, [rsp+2B8h+Name]; lpName
0x180011d97  mov     [rsp+2B8h+lpcbMaxSubKeyLen], rdi; lpClass
0x180011d9c  mov     edx, eax; dwIndex
0x180011d9e  mov     [rsp+2B8h+lpcSubKeys], rdi; lpReserved
0x180011da3  mov     [rsp+2B8h+cSubKeys], eax
0x180011da7  mov     [rsp+2B8h+cchName], 111h
0x180011daf  call    cs:__imp_RegEnumKeyExW
0x180011db5  test    eax, eax
0x180011db7  jnz     short loc_180011DC8
0x180011db9  mov     rcx, [rbx+8]; hKey
0x180011dbd  lea     rdx, [rsp+2B8h+Name]; lpSubKey
0x180011dc2  call    cs:__imp_RegDeleteKeyW
0x180011dc8  mov     eax, [rsp+2B8h+cSubKeys]
0x180011dcc  test    eax, eax
0x180011dce  jnz     short loc_180011D7D
0x180011dd0  mov     rcx, [rsp+2B8h+var_18]
0x180011dd8  xor     rcx, rsp; StackCookie
0x180011ddb  call    __security_check_cookie
0x180011de0  mov     rbx, [rsp+2B8h+arg_8]
0x180011de8  add     rsp, 2B0h
0x180011def  pop     rdi
0x180011df0  retn
```
