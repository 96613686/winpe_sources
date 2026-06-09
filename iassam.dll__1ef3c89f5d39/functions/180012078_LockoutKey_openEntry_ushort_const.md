# LockoutKey::openEntry(ushort const *)

- ea: `0x180012078`
- end: `0x180012153`
- name: `?openEntry@LockoutKey@@QEAAPEAUHKEY__@@PEBG@Z`
- size: `219`
- prototype: `HKEY(LockoutKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001195c`
- `0x180011a8c`

## callees

- `0x180012078`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180012112`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180012112`
- `ADVAPI32!RegCloseKey` at `0x18001212d`
- `ADVAPI32!RegCloseKey` at `0x18001212d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180012100`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180012100`
- `ADVAPI32!RegOpenKeyExW` at `0x1800120a9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800120a9`
- `ADVAPI32!RegDeleteKeyW` at `0x180012141`
- `ADVAPI32!RegDeleteKeyW` at `0x180012141`

## pseudocode

```c
HKEY __fastcall LockoutKey::openEntry(LockoutKey *this, const unsigned __int16 *a2)
{
  HKEY hKey; // [rsp+80h] [rbp+20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp+30h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+98h] [rbp+38h] BYREF

  hKey = 0;
  if ( !RegOpenKeyExW(::hKey, a2, 0, 0x2001Fu, &hKey) )
  {
    if ( qword_18003FAF0 )
    {
      ftLastWriteTime = 0;
      if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime) )
      {
        SystemTimeAsFileTime = 0;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)&ftLastWriteTime >= (unsigned __int64)qword_18003FAF0 )
        {
          RegCloseKey(hKey);
          hKey = 0;
          RegDeleteKeyW(::hKey, a2);
        }
      }
    }
  }
  return hKey;
}

```

## disassembly

```asm
0x180012078  mov     [rsp-18h+hKey], rcx
0x18001207d  push    rbp
0x18001207e  push    rbx
0x18001207f  push    rdi
0x180012080  mov     rbp, rsp
0x180012083  sub     rsp, 60h
0x180012087  mov     rcx, cs:hKey; hKey
0x18001208e  lea     rax, [rbp+hKey]
0x180012092  xor     edi, edi
0x180012094  mov     [rsp+60h+phkResult], rax; phkResult
0x180012099  mov     r9d, 2001Fh; samDesired
0x18001209f  mov     [rbp+hKey], rdi
0x1800120a3  xor     r8d, r8d; ulOptions
0x1800120a6  mov     rbx, rdx
0x1800120a9  call    cs:__imp_RegOpenKeyExW
0x1800120af  test    eax, eax
0x1800120b1  jnz     loc_180012147
0x1800120b7  cmp     cs:qword_18003FAF0, rdi
0x1800120be  jz      loc_180012147
0x1800120c4  mov     rcx, [rbp+hKey]; hKey
0x1800120c8  lea     rax, [rbp+ftLastWriteTime]
0x1800120cc  mov     [rsp+60h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800120d1  xor     r9d, r9d; lpReserved
0x1800120d4  mov     [rsp+60h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800120d9  xor     r8d, r8d; lpcchClass
0x1800120dc  mov     [rsp+60h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800120e1  xor     edx, edx; lpClass
0x1800120e3  mov     [rsp+60h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1800120e8  mov     [rsp+60h+lpcValues], rdi; lpcValues
0x1800120ed  mov     [rsp+60h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800120f2  mov     [rsp+60h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x1800120f7  mov     [rsp+60h+phkResult], rdi; lpcSubKeys
0x1800120fc  mov     qword ptr [rbp+ftLastWriteTime.dwLowDateTime], rdi
0x180012100  call    cs:__imp_RegQueryInfoKeyW
0x180012106  test    eax, eax
0x180012108  jnz     short loc_180012147
0x18001210a  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001210e  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rdi
0x180012112  call    cs:__imp_GetSystemTimeAsFileTime
0x180012118  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001211c  sub     rax, qword ptr [rbp+ftLastWriteTime.dwLowDateTime]
0x180012120  cmp     rax, cs:qword_18003FAF0
0x180012127  jb      short loc_180012147
0x180012129  mov     rcx, [rbp+hKey]; hKey
0x18001212d  call    cs:__imp_RegCloseKey
0x180012133  mov     rcx, cs:hKey; hKey
0x18001213a  mov     rdx, rbx; lpSubKey
0x18001213d  mov     [rbp+hKey], rdi
0x180012141  call    cs:__imp_RegDeleteKeyW
0x180012147  mov     rax, [rbp+hKey]
0x18001214b  add     rsp, 60h
0x18001214f  pop     rdi
0x180012150  pop     rbx
0x180012151  pop     rbp
0x180012152  retn
```
