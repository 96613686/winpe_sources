# RegistryRegRow::Clear(int)

- ea: `0x180027c90`
- end: `0x180027e44`
- name: `?Clear@RegistryRegRow@@UEAAJH@Z`
- size: `436`
- prototype: `__int64 __fastcall(RegistryRegRow *__hidden this, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180027c90`
- `0x18002c15c`
- `0x180043510`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027cef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027cef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180027dd4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180027dd4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027db9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027db9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180027d3f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180027d3f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180027d5a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180027d5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027dee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180027dee`

## pseudocode

```c
__int64 __fastcall RegistryRegRow::Clear(RegistryRegRow *this, int a2)
{
  const WCHAR *v4; // rdx
  HKEY v5; // rcx
  LSTATUS v6; // eax
  struct _FILETIME lpClass; // rbx
  LSTATUS v8; // eax
  bool v9; // cc
  LSTATUS v10; // eax
  bool v11; // cc
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  RegistryRegRow::ClearMaps(this);
  v4 = (const WCHAR *)*((_QWORD *)this + 15);
  v5 = (HKEY)*((_QWORD *)this + 16);
  hKey = 0;
  v6 = RegOpenKeyExW(v5, v4, 0, 0x2001Fu, &hKey);
  lpClass = (struct _FILETIME)(unsigned int)v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      lpClass.dwLowDateTime = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    if ( !a2 )
      goto LABEL_10;
    do
    {
      cchName = 260;
      ftLastWriteTime = lpClass;
      v8 = RegEnumKeyExW(
             hKey,
             0,
             Name,
             &cchName,
             *(LPDWORD *)&lpClass,
             *(LPWSTR *)&lpClass,
             *(LPDWORD *)&lpClass,
             &ftLastWriteTime);
      if ( v8 == 259 )
        goto LABEL_10;
      v9 = v8 <= 0;
      if ( v8 )
        break;
      v8 = RegDeleteTreeW(hKey, Name);
      v9 = v8 <= 0;
    }
    while ( !v8 );
    if ( v9 )
      lpClass.dwLowDateTime = v8;
    else
      lpClass.dwLowDateTime = (unsigned __int16)v8 | 0x80070000;
    if ( (lpClass.dwLowDateTime & 0x80000000) == 0 )
    {
LABEL_10:
      while ( 1 )
      {
        ftLastWriteTime.dwLowDateTime = 260;
        cchName = 0;
        v10 = RegEnumValueW(hKey, 0, Name, (LPDWORD)&ftLastWriteTime, 0, 0, 0, &cchName);
        if ( v10 == 259 )
          break;
        v11 = v10 <= 0;
        if ( !v10 )
        {
          v10 = RegDeleteValueW(hKey, Name);
          v11 = v10 <= 0;
          if ( !v10 )
            continue;
        }
        if ( v11 )
          lpClass.dwLowDateTime = v10;
        else
          lpClass.dwLowDateTime = (unsigned __int16)v10 | 0x80070000;
        break;
      }
    }
    RegCloseKey(hKey);
  }
  if ( (lpClass.dwLowDateTime & 0x80000000) == 0 )
    return (*(__int64 (__fastcall **)(RegistryRegRow *, __int64))(*(_QWORD *)this + 80LL))(this, 1);
  else
    return lpClass.dwLowDateTime;
}

```

## disassembly

```asm
0x180027c90  mov     [rsp-8+arg_8], rbx
0x180027c95  mov     [rsp-8+arg_10], rsi
0x180027c9a  push    rbp
0x180027c9b  push    rdi
0x180027c9c  push    r14
0x180027c9e  lea     rbp, [rsp-180h]
0x180027ca6  sub     rsp, 280h
0x180027cad  mov     rax, cs:__security_cookie
0x180027cb4  xor     rax, rsp
0x180027cb7  mov     [rbp+190h+var_20], rax
0x180027cbe  mov     esi, edx
0x180027cc0  mov     r14, rcx
0x180027cc3  call    ?ClearMaps@RegistryRegRow@@AEAAXXZ; RegistryRegRow::ClearMaps(void)
0x180027cc8  mov     rdx, [r14+78h]; lpSubKey
0x180027ccc  lea     rax, [rsp+290h+hKey]
0x180027cd1  mov     rcx, [r14+80h]; hKey
0x180027cd8  mov     r9d, 2001Fh; samDesired
0x180027cde  xor     r8d, r8d; ulOptions
0x180027ce1  mov     [rsp+290h+phkResult], rax; phkResult
0x180027ce6  mov     [rsp+290h+hKey], 0
0x180027cef  call    cs:__imp_RegOpenKeyExW
0x180027cf5  mov     ebx, eax
0x180027cf7  test    eax, eax
0x180027cf9  jnz     loc_180027DF6
0x180027cff  mov     edi, 80070000h
0x180027d04  test    esi, esi
0x180027d06  jz      short loc_180027D73
0x180027d08  mov     rcx, [rsp+290h+hKey]; hKey
0x180027d0d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180027d12  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180027d17  lea     r9, [rsp+290h+cchName]; lpcchName
0x180027d1c  mov     [rsp+290h+lpcchClass], rbx; lpcchClass
0x180027d21  lea     r8, [rsp+290h+Name]; lpName
0x180027d26  mov     [rsp+290h+lpClass], rbx; lpClass
0x180027d2b  xor     edx, edx; dwIndex
0x180027d2d  mov     [rsp+290h+phkResult], rbx; lpReserved
0x180027d32  mov     [rsp+290h+cchName], 104h
0x180027d3a  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], rbx
0x180027d3f  call    cs:__imp_RegEnumKeyExW
0x180027d45  cmp     eax, 103h
0x180027d4a  jz      short loc_180027D73
0x180027d4c  test    eax, eax
0x180027d4e  jnz     short loc_180027D64
0x180027d50  mov     rcx, [rsp+290h+hKey]; hKey
0x180027d55  lea     rdx, [rsp+290h+Name]; lpSubKey
0x180027d5a  call    cs:__imp_RegDeleteTreeW
0x180027d60  test    eax, eax
0x180027d62  jz      short loc_180027D08
0x180027d64  jg      short loc_180027D6A
0x180027d66  mov     ebx, eax
0x180027d68  jmp     short loc_180027D6F
0x180027d6a  movzx   ebx, ax
0x180027d6d  or      ebx, edi
0x180027d6f  test    ebx, ebx
0x180027d71  js      short loc_180027DE9
0x180027d73  mov     rcx, [rsp+290h+hKey]; hKey
0x180027d78  lea     rax, [rsp+290h+cchName]
0x180027d7d  mov     [rsp+290h+lpftLastWriteTime], rax; lpcbData
0x180027d82  lea     r9, [rsp+290h+ftLastWriteTime]; lpcchValueName
0x180027d87  mov     [rsp+290h+lpcchClass], 0; lpData
0x180027d90  lea     r8, [rsp+290h+Name]; lpValueName
0x180027d95  mov     [rsp+290h+lpClass], 0; lpType
0x180027d9e  xor     edx, edx; dwIndex
0x180027da0  mov     [rsp+290h+phkResult], 0; lpReserved
0x180027da9  mov     [rsp+290h+ftLastWriteTime.dwLowDateTime], 104h
0x180027db1  mov     [rsp+290h+cchName], 0
0x180027db9  call    cs:__imp_RegEnumValueW
0x180027dbf  cmp     eax, 103h
0x180027dc4  jz      short loc_180027DE9
0x180027dc6  test    eax, eax
0x180027dc8  jnz     short loc_180027DDE
0x180027dca  mov     rcx, [rsp+290h+hKey]; hKey
0x180027dcf  lea     rdx, [rsp+290h+Name]; lpValueName
0x180027dd4  call    cs:__imp_RegDeleteValueW
0x180027dda  test    eax, eax
0x180027ddc  jz      short loc_180027D73
0x180027dde  jg      short loc_180027DE4
0x180027de0  mov     ebx, eax
0x180027de2  jmp     short loc_180027DE9
0x180027de4  movzx   ebx, ax
0x180027de7  or      ebx, edi
0x180027de9  mov     rcx, [rsp+290h+hKey]; hKey
0x180027dee  call    cs:__imp_RegCloseKey
0x180027df4  jmp     short loc_180027E01
0x180027df6  jle     short loc_180027E01
0x180027df8  movzx   ebx, ax
0x180027dfb  or      ebx, 80070000h
0x180027e01  test    ebx, ebx
0x180027e03  jns     short loc_180027E09
0x180027e05  mov     eax, ebx
0x180027e07  jmp     short loc_180027E1D
0x180027e09  mov     rax, [r14]
0x180027e0c  mov     edx, 1
0x180027e11  mov     rcx, r14
0x180027e14  mov     rax, [rax+50h]
0x180027e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e1d  mov     rcx, [rbp+190h+var_20]
0x180027e24  xor     rcx, rsp; StackCookie
0x180027e27  call    __security_check_cookie
0x180027e2c  lea     r11, [rsp+290h+var_10]
0x180027e34  mov     rbx, [r11+28h]
0x180027e38  mov     rsi, [r11+30h]
0x180027e3c  mov     rsp, r11
0x180027e3f  pop     r14
0x180027e41  pop     rdi
0x180027e42  pop     rbp
0x180027e43  retn
```
