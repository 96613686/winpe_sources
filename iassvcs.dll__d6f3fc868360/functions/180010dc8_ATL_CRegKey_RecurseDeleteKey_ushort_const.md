# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180010dc8`
- end: `0x180010f0f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010dc8`
- `0x180011384`

## callees

- `0x18000fd78`
- `0x180010dc8`
- `0x1800181e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180010e46`
- `ADVAPI32!RegCloseKey` at `0x180010ebe`
- `ADVAPI32!RegCloseKey` at `0x180010ee0`
- `ADVAPI32!RegCloseKey` at `0x180010e46`
- `ADVAPI32!RegCloseKey` at `0x180010ebe`
- `ADVAPI32!RegCloseKey` at `0x180010ee0`
- `ADVAPI32!RegEnumKeyExW` at `0x180010eaa`
- `ADVAPI32!RegEnumKeyExW` at `0x180010eaa`
- `ADVAPI32!RegOpenKeyExW` at `0x180010e29`
- `ADVAPI32!RegOpenKeyExW` at `0x180010e29`

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
0x180010dc8  mov     [rsp-8+arg_10], rbx
0x180010dcd  mov     [rsp-8+arg_18], rsi
0x180010dd2  push    rbp
0x180010dd3  push    rdi
0x180010dd4  push    r14
0x180010dd6  lea     rbp, [rsp-180h]
0x180010dde  sub     rsp, 280h
0x180010de5  mov     rax, cs:__security_cookie
0x180010dec  xor     rax, rsp
0x180010def  mov     [rbp+190h+var_20], rax
0x180010df6  xor     r14d, r14d
0x180010df9  lea     rax, [rsp+290h+var_230]
0x180010dfe  mov     rdi, rcx
0x180010e01  mov     [rsp+290h+hKey], r14
0x180010e06  mov     rcx, [rcx]; hKey
0x180010e09  mov     r9d, 2001Fh; samDesired
0x180010e0f  xor     r8d, r8d; ulOptions
0x180010e12  mov     [rsp+290h+var_240], r14
0x180010e17  mov     [rsp+290h+var_238], r14
0x180010e1c  mov     rsi, rdx
0x180010e1f  mov     [rsp+290h+var_230], r14
0x180010e24  mov     [rsp+290h+phkResult], rax; phkResult
0x180010e29  call    cs:__imp_RegOpenKeyExW
0x180010e2f  mov     rcx, [rsp+290h+hKey]; hKey
0x180010e34  mov     ebx, eax
0x180010e36  test    eax, eax
0x180010e38  jnz     loc_180010EDB
0x180010e3e  mov     ebx, r14d
0x180010e41  test    rcx, rcx
0x180010e44  jz      short loc_180010E4E
0x180010e46  call    cs:__imp_RegCloseKey
0x180010e4c  mov     ebx, eax
0x180010e4e  mov     rcx, [rsp+290h+var_230]
0x180010e53  mov     [rsp+290h+hKey], rcx
0x180010e58  test    ebx, ebx
0x180010e5a  jnz     short loc_180010EDB
0x180010e5c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180010e61  jmp     short loc_180010E7D
0x180010e63  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180010e68  lea     rcx, [rsp+290h+hKey]; this
0x180010e6d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180010e72  mov     rcx, [rsp+290h+hKey]; hKey
0x180010e77  mov     ebx, eax
0x180010e79  test    eax, eax
0x180010e7b  jnz     short loc_180010EDB
0x180010e7d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180010e82  mov     [rsp+290h+cchName], 100h
0x180010e8a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180010e8f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180010e94  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180010e99  lea     r8, [rsp+290h+Name]; lpName
0x180010e9e  mov     [rsp+290h+lpClass], r14; lpClass
0x180010ea3  xor     edx, edx; dwIndex
0x180010ea5  mov     [rsp+290h+phkResult], r14; lpReserved
0x180010eaa  call    cs:__imp_RegEnumKeyExW
0x180010eb0  test    eax, eax
0x180010eb2  jz      short loc_180010E63
0x180010eb4  mov     rcx, [rsp+290h+hKey]; hKey
0x180010eb9  test    rcx, rcx
0x180010ebc  jz      short loc_180010EC9
0x180010ebe  call    cs:__imp_RegCloseKey
0x180010ec4  mov     [rsp+290h+hKey], r14
0x180010ec9  mov     rdx, rsi; unsigned __int16 *
0x180010ecc  mov     rcx, rdi; this
0x180010ecf  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180010ed4  mov     rcx, [rsp+290h+hKey]; hKey
0x180010ed9  mov     ebx, eax
0x180010edb  test    rcx, rcx
0x180010ede  jz      short loc_180010EE6
0x180010ee0  call    cs:__imp_RegCloseKey
0x180010ee6  mov     eax, ebx
0x180010ee8  mov     rcx, [rbp+190h+var_20]
0x180010eef  xor     rcx, rsp; StackCookie
0x180010ef2  call    __security_check_cookie
0x180010ef7  lea     r11, [rsp+290h+var_10]
0x180010eff  mov     rbx, [r11+30h]
0x180010f03  mov     rsi, [r11+38h]
0x180010f07  mov     rsp, r11
0x180010f0a  pop     r14
0x180010f0c  pop     rdi
0x180010f0d  pop     rbp
0x180010f0e  retn
```
