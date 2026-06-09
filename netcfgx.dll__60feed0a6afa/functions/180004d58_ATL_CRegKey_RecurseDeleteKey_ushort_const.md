# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180004d58`
- end: `0x180004e9f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004d58`
- `0x18000521c`

## callees

- `0x180001f90`
- `0x1800043d8`
- `0x180004d58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004db9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004db9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180004e3a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180004e3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004dd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e70`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004dd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004e70`

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
0x180004d58  mov     [rsp-8+arg_10], rbx
0x180004d5d  mov     [rsp-8+arg_18], rsi
0x180004d62  push    rbp
0x180004d63  push    rdi
0x180004d64  push    r14
0x180004d66  lea     rbp, [rsp-180h]
0x180004d6e  sub     rsp, 280h
0x180004d75  mov     rax, cs:__security_cookie
0x180004d7c  xor     rax, rsp
0x180004d7f  mov     [rbp+190h+var_20], rax
0x180004d86  xor     r14d, r14d
0x180004d89  lea     rax, [rsp+290h+var_230]
0x180004d8e  mov     rdi, rcx
0x180004d91  mov     [rsp+290h+hKey], r14
0x180004d96  mov     rcx, [rcx]; hKey
0x180004d99  mov     r9d, 2001Fh; samDesired
0x180004d9f  xor     r8d, r8d; ulOptions
0x180004da2  mov     [rsp+290h+var_240], r14
0x180004da7  mov     [rsp+290h+var_238], r14
0x180004dac  mov     rsi, rdx
0x180004daf  mov     [rsp+290h+var_230], r14
0x180004db4  mov     [rsp+290h+phkResult], rax; phkResult
0x180004db9  call    cs:__imp_RegOpenKeyExW
0x180004dbf  mov     rcx, [rsp+290h+hKey]; hKey
0x180004dc4  mov     ebx, eax
0x180004dc6  test    eax, eax
0x180004dc8  jnz     loc_180004E6B
0x180004dce  mov     ebx, r14d
0x180004dd1  test    rcx, rcx
0x180004dd4  jz      short loc_180004DDE
0x180004dd6  call    cs:__imp_RegCloseKey
0x180004ddc  mov     ebx, eax
0x180004dde  mov     rcx, [rsp+290h+var_230]
0x180004de3  mov     [rsp+290h+hKey], rcx
0x180004de8  test    ebx, ebx
0x180004dea  jnz     short loc_180004E6B
0x180004dec  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180004df1  jmp     short loc_180004E0D
0x180004df3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180004df8  lea     rcx, [rsp+290h+hKey]; this
0x180004dfd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004e02  mov     rcx, [rsp+290h+hKey]; hKey
0x180004e07  mov     ebx, eax
0x180004e09  test    eax, eax
0x180004e0b  jnz     short loc_180004E6B
0x180004e0d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180004e12  mov     [rsp+290h+cchName], 100h
0x180004e1a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004e1f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004e24  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180004e29  lea     r8, [rsp+290h+Name]; lpName
0x180004e2e  mov     [rsp+290h+lpClass], r14; lpClass
0x180004e33  xor     edx, edx; dwIndex
0x180004e35  mov     [rsp+290h+phkResult], r14; lpReserved
0x180004e3a  call    cs:__imp_RegEnumKeyExW
0x180004e40  test    eax, eax
0x180004e42  jz      short loc_180004DF3
0x180004e44  mov     rcx, [rsp+290h+hKey]; hKey
0x180004e49  test    rcx, rcx
0x180004e4c  jz      short loc_180004E59
0x180004e4e  call    cs:__imp_RegCloseKey
0x180004e54  mov     [rsp+290h+hKey], r14
0x180004e59  mov     rdx, rsi; unsigned __int16 *
0x180004e5c  mov     rcx, rdi; this
0x180004e5f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004e64  mov     rcx, [rsp+290h+hKey]; hKey
0x180004e69  mov     ebx, eax
0x180004e6b  test    rcx, rcx
0x180004e6e  jz      short loc_180004E76
0x180004e70  call    cs:__imp_RegCloseKey
0x180004e76  mov     eax, ebx
0x180004e78  mov     rcx, [rbp+190h+var_20]
0x180004e7f  xor     rcx, rsp; StackCookie
0x180004e82  call    __security_check_cookie
0x180004e87  lea     r11, [rsp+290h+var_10]
0x180004e8f  mov     rbx, [r11+30h]
0x180004e93  mov     rsi, [r11+38h]
0x180004e97  mov     rsp, r11
0x180004e9a  pop     r14
0x180004e9c  pop     rdi
0x180004e9d  pop     rbp
0x180004e9e  retn
```
