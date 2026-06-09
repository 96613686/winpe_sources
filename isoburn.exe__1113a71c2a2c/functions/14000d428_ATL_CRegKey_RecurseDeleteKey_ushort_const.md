# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x14000d428`
- end: `0x14000d56f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000d428`
- `0x14000d8cc`

## callees

- `0x140001fa0`
- `0x14000cd84`
- `0x14000d428`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000d4a6`
- `ADVAPI32!RegCloseKey` at `0x14000d51e`
- `ADVAPI32!RegCloseKey` at `0x14000d540`
- `ADVAPI32!RegCloseKey` at `0x14000d4a6`
- `ADVAPI32!RegCloseKey` at `0x14000d51e`
- `ADVAPI32!RegCloseKey` at `0x14000d540`
- `ADVAPI32!RegOpenKeyExW` at `0x14000d489`
- `ADVAPI32!RegOpenKeyExW` at `0x14000d489`
- `ADVAPI32!RegEnumKeyExW` at `0x14000d50a`
- `ADVAPI32!RegEnumKeyExW` at `0x14000d50a`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = *this;
  phkResult = 0;
  v5 = RegOpenKeyExW(v3, a2, 0, 0x2001Fu, &phkResult);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v8 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v6 = hKey[0];
      v7 = v8;
      if ( v8 )
        goto LABEL_8;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v9 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
    v6 = hKey[0];
    v7 = v9;
  }
LABEL_8:
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x14000d428  mov     [rsp-8+arg_10], rbx
0x14000d42d  mov     [rsp-8+arg_18], rsi
0x14000d432  push    rbp
0x14000d433  push    rdi
0x14000d434  push    r14
0x14000d436  lea     rbp, [rsp-180h]
0x14000d43e  sub     rsp, 280h
0x14000d445  mov     rax, cs:__security_cookie
0x14000d44c  xor     rax, rsp
0x14000d44f  mov     [rbp+190h+var_20], rax
0x14000d456  xor     r14d, r14d
0x14000d459  lea     rax, [rsp+290h+var_230]
0x14000d45e  mov     rdi, rcx
0x14000d461  mov     [rsp+290h+hKey], r14
0x14000d466  mov     rcx, [rcx]; hKey
0x14000d469  mov     r9d, 2001Fh; samDesired
0x14000d46f  xor     r8d, r8d; ulOptions
0x14000d472  mov     [rsp+290h+var_240], r14
0x14000d477  mov     [rsp+290h+var_238], r14
0x14000d47c  mov     rsi, rdx
0x14000d47f  mov     [rsp+290h+var_230], r14
0x14000d484  mov     [rsp+290h+phkResult], rax; phkResult
0x14000d489  call    cs:__imp_RegOpenKeyExW
0x14000d48f  mov     rcx, [rsp+290h+hKey]; hKey
0x14000d494  mov     ebx, eax
0x14000d496  test    eax, eax
0x14000d498  jnz     loc_14000D53B
0x14000d49e  mov     ebx, r14d
0x14000d4a1  test    rcx, rcx
0x14000d4a4  jz      short loc_14000D4AE
0x14000d4a6  call    cs:__imp_RegCloseKey
0x14000d4ac  mov     ebx, eax
0x14000d4ae  mov     rcx, [rsp+290h+var_230]
0x14000d4b3  mov     [rsp+290h+hKey], rcx
0x14000d4b8  test    ebx, ebx
0x14000d4ba  jnz     short loc_14000D53B
0x14000d4bc  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x14000d4c1  jmp     short loc_14000D4DD
0x14000d4c3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x14000d4c8  lea     rcx, [rsp+290h+hKey]; this
0x14000d4cd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x14000d4d2  mov     rcx, [rsp+290h+hKey]; hKey
0x14000d4d7  mov     ebx, eax
0x14000d4d9  test    eax, eax
0x14000d4db  jnz     short loc_14000D53B
0x14000d4dd  lea     rax, [rsp+290h+ftLastWriteTime]
0x14000d4e2  mov     [rsp+290h+cchName], 100h
0x14000d4ea  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14000d4ef  lea     r9, [rsp+290h+cchName]; lpcchName
0x14000d4f4  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x14000d4f9  lea     r8, [rsp+290h+Name]; lpName
0x14000d4fe  mov     [rsp+290h+lpClass], r14; lpClass
0x14000d503  xor     edx, edx; dwIndex
0x14000d505  mov     [rsp+290h+phkResult], r14; lpReserved
0x14000d50a  call    cs:__imp_RegEnumKeyExW
0x14000d510  test    eax, eax
0x14000d512  jz      short loc_14000D4C3
0x14000d514  mov     rcx, [rsp+290h+hKey]; hKey
0x14000d519  test    rcx, rcx
0x14000d51c  jz      short loc_14000D529
0x14000d51e  call    cs:__imp_RegCloseKey
0x14000d524  mov     [rsp+290h+hKey], r14
0x14000d529  mov     rdx, rsi; unsigned __int16 *
0x14000d52c  mov     rcx, rdi; this
0x14000d52f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x14000d534  mov     rcx, [rsp+290h+hKey]; hKey
0x14000d539  mov     ebx, eax
0x14000d53b  test    rcx, rcx
0x14000d53e  jz      short loc_14000D546
0x14000d540  call    cs:__imp_RegCloseKey
0x14000d546  mov     eax, ebx
0x14000d548  mov     rcx, [rbp+190h+var_20]
0x14000d54f  xor     rcx, rsp; StackCookie
0x14000d552  call    __security_check_cookie
0x14000d557  lea     r11, [rsp+290h+var_10]
0x14000d55f  mov     rbx, [r11+30h]
0x14000d563  mov     rsi, [r11+38h]
0x14000d567  mov     rsp, r11
0x14000d56a  pop     r14
0x14000d56c  pop     rdi
0x14000d56d  pop     rbp
0x14000d56e  retn
```
