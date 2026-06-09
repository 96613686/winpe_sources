# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180004a38`
- end: `0x180004b7f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004a38`
- `0x180004efc`

## callees

- `0x1800040c8`
- `0x180004a38`
- `0x18000dd10`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180004a99`
- `ADVAPI32!RegOpenKeyExW` at `0x180004a99`
- `ADVAPI32!RegEnumKeyExW` at `0x180004b1a`
- `ADVAPI32!RegEnumKeyExW` at `0x180004b1a`
- `ADVAPI32!RegCloseKey` at `0x180004ab6`
- `ADVAPI32!RegCloseKey` at `0x180004b2e`
- `ADVAPI32!RegCloseKey` at `0x180004b50`
- `ADVAPI32!RegCloseKey` at `0x180004ab6`
- `ADVAPI32!RegCloseKey` at `0x180004b2e`
- `ADVAPI32!RegCloseKey` at `0x180004b50`

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
0x180004a38  mov     [rsp-8+arg_10], rbx
0x180004a3d  mov     [rsp-8+arg_18], rsi
0x180004a42  push    rbp
0x180004a43  push    rdi
0x180004a44  push    r14
0x180004a46  lea     rbp, [rsp-180h]
0x180004a4e  sub     rsp, 280h
0x180004a55  mov     rax, cs:__security_cookie
0x180004a5c  xor     rax, rsp
0x180004a5f  mov     [rbp+190h+var_20], rax
0x180004a66  xor     r14d, r14d
0x180004a69  lea     rax, [rsp+290h+var_230]
0x180004a6e  mov     rdi, rcx
0x180004a71  mov     [rsp+290h+hKey], r14
0x180004a76  mov     rcx, [rcx]; hKey
0x180004a79  mov     r9d, 2001Fh; samDesired
0x180004a7f  xor     r8d, r8d; ulOptions
0x180004a82  mov     [rsp+290h+var_240], r14
0x180004a87  mov     [rsp+290h+var_238], r14
0x180004a8c  mov     rsi, rdx
0x180004a8f  mov     [rsp+290h+var_230], r14
0x180004a94  mov     [rsp+290h+phkResult], rax; phkResult
0x180004a99  call    cs:__imp_RegOpenKeyExW
0x180004a9f  mov     rcx, [rsp+290h+hKey]; hKey
0x180004aa4  mov     ebx, eax
0x180004aa6  test    eax, eax
0x180004aa8  jnz     loc_180004B4B
0x180004aae  mov     ebx, r14d
0x180004ab1  test    rcx, rcx
0x180004ab4  jz      short loc_180004ABE
0x180004ab6  call    cs:__imp_RegCloseKey
0x180004abc  mov     ebx, eax
0x180004abe  mov     rcx, [rsp+290h+var_230]
0x180004ac3  mov     [rsp+290h+hKey], rcx
0x180004ac8  test    ebx, ebx
0x180004aca  jnz     short loc_180004B4B
0x180004acc  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180004ad1  jmp     short loc_180004AED
0x180004ad3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180004ad8  lea     rcx, [rsp+290h+hKey]; this
0x180004add  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004ae2  mov     rcx, [rsp+290h+hKey]; hKey
0x180004ae7  mov     ebx, eax
0x180004ae9  test    eax, eax
0x180004aeb  jnz     short loc_180004B4B
0x180004aed  lea     rax, [rsp+290h+ftLastWriteTime]
0x180004af2  mov     [rsp+290h+cchName], 100h
0x180004afa  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004aff  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004b04  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180004b09  lea     r8, [rsp+290h+Name]; lpName
0x180004b0e  mov     [rsp+290h+lpClass], r14; lpClass
0x180004b13  xor     edx, edx; dwIndex
0x180004b15  mov     [rsp+290h+phkResult], r14; lpReserved
0x180004b1a  call    cs:__imp_RegEnumKeyExW
0x180004b20  test    eax, eax
0x180004b22  jz      short loc_180004AD3
0x180004b24  mov     rcx, [rsp+290h+hKey]; hKey
0x180004b29  test    rcx, rcx
0x180004b2c  jz      short loc_180004B39
0x180004b2e  call    cs:__imp_RegCloseKey
0x180004b34  mov     [rsp+290h+hKey], r14
0x180004b39  mov     rdx, rsi; unsigned __int16 *
0x180004b3c  mov     rcx, rdi; this
0x180004b3f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004b44  mov     rcx, [rsp+290h+hKey]; hKey
0x180004b49  mov     ebx, eax
0x180004b4b  test    rcx, rcx
0x180004b4e  jz      short loc_180004B56
0x180004b50  call    cs:__imp_RegCloseKey
0x180004b56  mov     eax, ebx
0x180004b58  mov     rcx, [rbp+190h+var_20]
0x180004b5f  xor     rcx, rsp; StackCookie
0x180004b62  call    __security_check_cookie
0x180004b67  lea     r11, [rsp+290h+var_10]
0x180004b6f  mov     rbx, [r11+30h]
0x180004b73  mov     rsi, [r11+38h]
0x180004b77  mov     rsp, r11
0x180004b7a  pop     r14
0x180004b7c  pop     rdi
0x180004b7d  pop     rbp
0x180004b7e  retn
```
