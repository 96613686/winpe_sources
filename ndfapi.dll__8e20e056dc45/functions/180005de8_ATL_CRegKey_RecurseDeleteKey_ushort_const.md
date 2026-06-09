# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180005de8`
- end: `0x180005f2f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180005de8`
- `0x1800062ac`

## callees

- `0x1800057a4`
- `0x180005de8`
- `0x18001f690`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180005e49`
- `ADVAPI32!RegOpenKeyExW` at `0x180005e49`
- `ADVAPI32!RegEnumKeyExW` at `0x180005eca`
- `ADVAPI32!RegEnumKeyExW` at `0x180005eca`
- `ADVAPI32!RegCloseKey` at `0x180005e66`
- `ADVAPI32!RegCloseKey` at `0x180005ede`
- `ADVAPI32!RegCloseKey` at `0x180005f00`
- `ADVAPI32!RegCloseKey` at `0x180005e66`
- `ADVAPI32!RegCloseKey` at `0x180005ede`
- `ADVAPI32!RegCloseKey` at `0x180005f00`

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
0x180005de8  mov     [rsp-8+arg_10], rbx
0x180005ded  mov     [rsp-8+arg_18], rsi
0x180005df2  push    rbp
0x180005df3  push    rdi
0x180005df4  push    r14
0x180005df6  lea     rbp, [rsp-180h]
0x180005dfe  sub     rsp, 280h
0x180005e05  mov     rax, cs:__security_cookie
0x180005e0c  xor     rax, rsp
0x180005e0f  mov     [rbp+190h+var_20], rax
0x180005e16  xor     r14d, r14d
0x180005e19  lea     rax, [rsp+290h+var_230]
0x180005e1e  mov     rdi, rcx
0x180005e21  mov     [rsp+290h+hKey], r14
0x180005e26  mov     rcx, [rcx]; hKey
0x180005e29  mov     r9d, 2001Fh; samDesired
0x180005e2f  xor     r8d, r8d; ulOptions
0x180005e32  mov     [rsp+290h+var_240], r14
0x180005e37  mov     [rsp+290h+var_238], r14
0x180005e3c  mov     rsi, rdx
0x180005e3f  mov     [rsp+290h+var_230], r14
0x180005e44  mov     [rsp+290h+phkResult], rax; phkResult
0x180005e49  call    cs:__imp_RegOpenKeyExW
0x180005e4f  mov     rcx, [rsp+290h+hKey]; hKey
0x180005e54  mov     ebx, eax
0x180005e56  test    eax, eax
0x180005e58  jnz     loc_180005EFB
0x180005e5e  mov     ebx, r14d
0x180005e61  test    rcx, rcx
0x180005e64  jz      short loc_180005E6E
0x180005e66  call    cs:__imp_RegCloseKey
0x180005e6c  mov     ebx, eax
0x180005e6e  mov     rcx, [rsp+290h+var_230]
0x180005e73  mov     [rsp+290h+hKey], rcx
0x180005e78  test    ebx, ebx
0x180005e7a  jnz     short loc_180005EFB
0x180005e7c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180005e81  jmp     short loc_180005E9D
0x180005e83  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180005e88  lea     rcx, [rsp+290h+hKey]; this
0x180005e8d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180005e92  mov     rcx, [rsp+290h+hKey]; hKey
0x180005e97  mov     ebx, eax
0x180005e99  test    eax, eax
0x180005e9b  jnz     short loc_180005EFB
0x180005e9d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180005ea2  mov     [rsp+290h+cchName], 100h
0x180005eaa  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180005eaf  lea     r9, [rsp+290h+cchName]; lpcchName
0x180005eb4  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180005eb9  lea     r8, [rsp+290h+Name]; lpName
0x180005ebe  mov     [rsp+290h+lpClass], r14; lpClass
0x180005ec3  xor     edx, edx; dwIndex
0x180005ec5  mov     [rsp+290h+phkResult], r14; lpReserved
0x180005eca  call    cs:__imp_RegEnumKeyExW
0x180005ed0  test    eax, eax
0x180005ed2  jz      short loc_180005E83
0x180005ed4  mov     rcx, [rsp+290h+hKey]; hKey
0x180005ed9  test    rcx, rcx
0x180005edc  jz      short loc_180005EE9
0x180005ede  call    cs:__imp_RegCloseKey
0x180005ee4  mov     [rsp+290h+hKey], r14
0x180005ee9  mov     rdx, rsi; unsigned __int16 *
0x180005eec  mov     rcx, rdi; this
0x180005eef  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180005ef4  mov     rcx, [rsp+290h+hKey]; hKey
0x180005ef9  mov     ebx, eax
0x180005efb  test    rcx, rcx
0x180005efe  jz      short loc_180005F06
0x180005f00  call    cs:__imp_RegCloseKey
0x180005f06  mov     eax, ebx
0x180005f08  mov     rcx, [rbp+190h+var_20]
0x180005f0f  xor     rcx, rsp; StackCookie
0x180005f12  call    __security_check_cookie
0x180005f17  lea     r11, [rsp+290h+var_10]
0x180005f1f  mov     rbx, [r11+30h]
0x180005f23  mov     rsi, [r11+38h]
0x180005f27  mov     rsp, r11
0x180005f2a  pop     r14
0x180005f2c  pop     rdi
0x180005f2d  pop     rbp
0x180005f2e  retn
```
