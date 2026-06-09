# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x140003e48`
- end: `0x140003f8f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003e48`
- `0x1400042ec`

## callees

- `0x140003018`
- `0x140003e48`
- `0x1400065f0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140003ec6`
- `ADVAPI32!RegCloseKey` at `0x140003f3e`
- `ADVAPI32!RegCloseKey` at `0x140003f60`
- `ADVAPI32!RegCloseKey` at `0x140003ec6`
- `ADVAPI32!RegCloseKey` at `0x140003f3e`
- `ADVAPI32!RegCloseKey` at `0x140003f60`
- `ADVAPI32!RegEnumKeyExW` at `0x140003f2a`
- `ADVAPI32!RegEnumKeyExW` at `0x140003f2a`
- `ADVAPI32!RegOpenKeyExW` at `0x140003ea9`
- `ADVAPI32!RegOpenKeyExW` at `0x140003ea9`

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
0x140003e48  mov     [rsp-8+arg_10], rbx
0x140003e4d  mov     [rsp-8+arg_18], rsi
0x140003e52  push    rbp
0x140003e53  push    rdi
0x140003e54  push    r14
0x140003e56  lea     rbp, [rsp-180h]
0x140003e5e  sub     rsp, 280h
0x140003e65  mov     rax, cs:__security_cookie
0x140003e6c  xor     rax, rsp
0x140003e6f  mov     [rbp+190h+var_20], rax
0x140003e76  xor     r14d, r14d
0x140003e79  lea     rax, [rsp+290h+var_230]
0x140003e7e  mov     rdi, rcx
0x140003e81  mov     [rsp+290h+hKey], r14
0x140003e86  mov     rcx, [rcx]; hKey
0x140003e89  mov     r9d, 2001Fh; samDesired
0x140003e8f  xor     r8d, r8d; ulOptions
0x140003e92  mov     [rsp+290h+var_240], r14
0x140003e97  mov     [rsp+290h+var_238], r14
0x140003e9c  mov     rsi, rdx
0x140003e9f  mov     [rsp+290h+var_230], r14
0x140003ea4  mov     [rsp+290h+phkResult], rax; phkResult
0x140003ea9  call    cs:__imp_RegOpenKeyExW
0x140003eaf  mov     rcx, [rsp+290h+hKey]; hKey
0x140003eb4  mov     ebx, eax
0x140003eb6  test    eax, eax
0x140003eb8  jnz     loc_140003F5B
0x140003ebe  mov     ebx, r14d
0x140003ec1  test    rcx, rcx
0x140003ec4  jz      short loc_140003ECE
0x140003ec6  call    cs:__imp_RegCloseKey
0x140003ecc  mov     ebx, eax
0x140003ece  mov     rcx, [rsp+290h+var_230]
0x140003ed3  mov     [rsp+290h+hKey], rcx
0x140003ed8  test    ebx, ebx
0x140003eda  jnz     short loc_140003F5B
0x140003edc  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x140003ee1  jmp     short loc_140003EFD
0x140003ee3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x140003ee8  lea     rcx, [rsp+290h+hKey]; this
0x140003eed  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140003ef2  mov     rcx, [rsp+290h+hKey]; hKey
0x140003ef7  mov     ebx, eax
0x140003ef9  test    eax, eax
0x140003efb  jnz     short loc_140003F5B
0x140003efd  lea     rax, [rsp+290h+ftLastWriteTime]
0x140003f02  mov     [rsp+290h+cchName], 100h
0x140003f0a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140003f0f  lea     r9, [rsp+290h+cchName]; lpcchName
0x140003f14  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x140003f19  lea     r8, [rsp+290h+Name]; lpName
0x140003f1e  mov     [rsp+290h+lpClass], r14; lpClass
0x140003f23  xor     edx, edx; dwIndex
0x140003f25  mov     [rsp+290h+phkResult], r14; lpReserved
0x140003f2a  call    cs:__imp_RegEnumKeyExW
0x140003f30  test    eax, eax
0x140003f32  jz      short loc_140003EE3
0x140003f34  mov     rcx, [rsp+290h+hKey]; hKey
0x140003f39  test    rcx, rcx
0x140003f3c  jz      short loc_140003F49
0x140003f3e  call    cs:__imp_RegCloseKey
0x140003f44  mov     [rsp+290h+hKey], r14
0x140003f49  mov     rdx, rsi; unsigned __int16 *
0x140003f4c  mov     rcx, rdi; this
0x140003f4f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x140003f54  mov     rcx, [rsp+290h+hKey]; hKey
0x140003f59  mov     ebx, eax
0x140003f5b  test    rcx, rcx
0x140003f5e  jz      short loc_140003F66
0x140003f60  call    cs:__imp_RegCloseKey
0x140003f66  mov     eax, ebx
0x140003f68  mov     rcx, [rbp+190h+var_20]
0x140003f6f  xor     rcx, rsp; StackCookie
0x140003f72  call    __security_check_cookie
0x140003f77  lea     r11, [rsp+290h+var_10]
0x140003f7f  mov     rbx, [r11+30h]
0x140003f83  mov     rsi, [r11+38h]
0x140003f87  mov     rsp, r11
0x140003f8a  pop     r14
0x140003f8c  pop     rdi
0x140003f8d  pop     rbp
0x140003f8e  retn
```
