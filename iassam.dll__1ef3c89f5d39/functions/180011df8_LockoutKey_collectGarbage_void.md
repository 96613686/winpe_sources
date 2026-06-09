# LockoutKey::collectGarbage(void)

- ea: `0x180011df8`
- end: `0x180011f41`
- name: `?collectGarbage@LockoutKey@@IEAAXXZ`
- size: `329`
- prototype: `void __fastcall(LockoutKey *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180011b58`
- `0x18001215c`

## callees

- `0x180011df8`
- `0x18002b4a0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180011e39`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180011e39`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180011ea8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180011ea8`
- `ADVAPI32!RegEnumKeyExW` at `0x180011eef`
- `ADVAPI32!RegEnumKeyExW` at `0x180011eef`
- `ADVAPI32!RegDeleteKeyW` at `0x180011f10`
- `ADVAPI32!RegDeleteKeyW` at `0x180011f10`

## pseudocode

```c
void __fastcall LockoutKey::collectGarbage(LockoutKey *this)
{
  unsigned __int64 v1; // rdi
  HKEY v3; // rcx
  HKEY v4; // rcx
  DWORD v5; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[280]; // [rsp+80h] [rbp-80h] BYREF

  v1 = *((_QWORD *)this + 4);
  if ( v1 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( *(_QWORD *)&SystemTimeAsFileTime - *((_QWORD *)this + 5) >= v1 && !_InterlockedExchange(&dword_1800403B0, 1) )
    {
      v3 = (HKEY)*((_QWORD *)this + 1);
      *((struct _FILETIME *)this + 5) = SystemTimeAsFileTime;
      cSubKeys = 0;
      if ( !RegQueryInfoKeyW(v3, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) )
      {
        while ( 1 )
        {
          v5 = cSubKeys;
          if ( !cSubKeys )
            break;
          cchName = 273;
          --cSubKeys;
          v4 = (HKEY)*((_QWORD *)this + 1);
          ftLastWriteTime = 0;
          if ( !RegEnumKeyExW(v4, v5 - 1, Name, &cchName, 0, 0, 0, &ftLastWriteTime)
            && *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&ftLastWriteTime >= v1 )
          {
            RegDeleteKeyW(*((HKEY *)this + 1), Name);
          }
        }
      }
      _InterlockedExchange(&dword_1800403B0, 0);
    }
  }
}

```

## disassembly

```asm
0x180011df8  push    rbp
0x180011dfa  push    rbx
0x180011dfb  push    rsi
0x180011dfc  push    rdi
0x180011dfd  lea     rbp, [rsp-1C8h]
0x180011e05  sub     rsp, 2C8h
0x180011e0c  mov     rax, cs:__security_cookie
0x180011e13  xor     rax, rsp
0x180011e16  mov     [rbp+1E0h+var_30], rax
0x180011e1d  mov     rdi, [rcx+20h]
0x180011e21  xor     esi, esi
0x180011e23  mov     rbx, rcx
0x180011e26  test    rdi, rdi
0x180011e29  jz      loc_180011F26
0x180011e2f  lea     rcx, [rsp+2E0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180011e34  mov     qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180011e39  call    cs:__imp_GetSystemTimeAsFileTime
0x180011e3f  mov     rax, qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime]
0x180011e44  sub     rax, [rbx+28h]
0x180011e48  cmp     rax, rdi
0x180011e4b  jb      loc_180011F26
0x180011e51  lea     eax, [rsi+1]
0x180011e54  xchg    eax, cs:dword_1800403B0
0x180011e5a  test    eax, eax
0x180011e5c  jnz     loc_180011F26
0x180011e62  mov     rax, qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime]
0x180011e67  xor     r9d, r9d; lpReserved
0x180011e6a  mov     rcx, [rbx+8]; hKey
0x180011e6e  xor     r8d, r8d; lpcchClass
0x180011e71  mov     [rsp+2E0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180011e76  xor     edx, edx; lpClass
0x180011e78  mov     [rsp+2E0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180011e7d  mov     [rsp+2E0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180011e82  mov     [rsp+2E0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180011e87  mov     [rsp+2E0h+lpcValues], rsi; lpcValues
0x180011e8c  mov     [rbx+28h], rax
0x180011e90  lea     rax, [rsp+2E0h+cSubKeys]
0x180011e95  mov     [rsp+2E0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180011e9a  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180011e9f  mov     [rsp+2E0h+lpcSubKeys], rax; lpcSubKeys
0x180011ea4  mov     [rsp+2E0h+cSubKeys], esi
0x180011ea8  call    cs:__imp_RegQueryInfoKeyW
0x180011eae  test    eax, eax
0x180011eb0  jnz     short loc_180011F1E
0x180011eb2  jmp     short loc_180011F16
0x180011eb4  dec     eax
0x180011eb6  mov     [rsp+2E0h+cchName], 111h
0x180011ebe  lea     rcx, [rsp+2E0h+ftLastWriteTime]
0x180011ec3  mov     [rsp+2E0h+cSubKeys], eax
0x180011ec7  mov     [rsp+2E0h+lpcValues], rcx; lpftLastWriteTime
0x180011ecc  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x180011ed1  mov     rcx, [rbx+8]; hKey
0x180011ed5  lea     r8, [rbp+1E0h+Name]; lpName
0x180011ed9  mov     [rsp+2E0h+lpcbMaxClassLen], rsi; lpcchClass
0x180011ede  mov     edx, eax; dwIndex
0x180011ee0  mov     [rsp+2E0h+lpcbMaxSubKeyLen], rsi; lpClass
0x180011ee5  mov     [rsp+2E0h+lpcSubKeys], rsi; lpReserved
0x180011eea  mov     qword ptr [rsp+2E0h+ftLastWriteTime.dwLowDateTime], rsi
0x180011eef  call    cs:__imp_RegEnumKeyExW
0x180011ef5  test    eax, eax
0x180011ef7  jnz     short loc_180011F16
0x180011ef9  mov     rax, qword ptr [rsp+2E0h+SystemTimeAsFileTime.dwLowDateTime]
0x180011efe  sub     rax, qword ptr [rsp+2E0h+ftLastWriteTime.dwLowDateTime]
0x180011f03  cmp     rax, rdi
0x180011f06  jb      short loc_180011F16
0x180011f08  mov     rcx, [rbx+8]; hKey
0x180011f0c  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x180011f10  call    cs:__imp_RegDeleteKeyW
0x180011f16  mov     eax, [rsp+2E0h+cSubKeys]
0x180011f1a  test    eax, eax
0x180011f1c  jnz     short loc_180011EB4
0x180011f1e  mov     eax, esi
0x180011f20  xchg    eax, cs:dword_1800403B0
0x180011f26  mov     rcx, [rbp+1E0h+var_30]
0x180011f2d  xor     rcx, rsp; StackCookie
0x180011f30  call    __security_check_cookie
0x180011f35  add     rsp, 2C8h
0x180011f3c  pop     rdi
0x180011f3d  pop     rsi
0x180011f3e  pop     rbx
0x180011f3f  pop     rbp
0x180011f40  retn
```
