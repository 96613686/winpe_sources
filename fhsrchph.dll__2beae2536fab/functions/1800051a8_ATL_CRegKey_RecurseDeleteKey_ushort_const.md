# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800051a8`
- end: `0x1800052ef`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800051a8`
- `0x18000566c`

## callees

- `0x1800027b4`
- `0x1800051a8`
- `0x18000ab60`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x18000528a`
- `ADVAPI32!RegEnumKeyExW` at `0x18000528a`
- `ADVAPI32!RegOpenKeyExW` at `0x180005209`
- `ADVAPI32!RegOpenKeyExW` at `0x180005209`
- `ADVAPI32!RegCloseKey` at `0x180005226`
- `ADVAPI32!RegCloseKey` at `0x18000529e`
- `ADVAPI32!RegCloseKey` at `0x1800052c0`
- `ADVAPI32!RegCloseKey` at `0x180005226`
- `ADVAPI32!RegCloseKey` at `0x18000529e`
- `ADVAPI32!RegCloseKey` at `0x1800052c0`

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
0x1800051a8  mov     [rsp-8+arg_10], rbx
0x1800051ad  mov     [rsp-8+arg_18], rsi
0x1800051b2  push    rbp
0x1800051b3  push    rdi
0x1800051b4  push    r14
0x1800051b6  lea     rbp, [rsp-180h]
0x1800051be  sub     rsp, 280h
0x1800051c5  mov     rax, cs:__security_cookie
0x1800051cc  xor     rax, rsp
0x1800051cf  mov     [rbp+190h+var_20], rax
0x1800051d6  xor     r14d, r14d
0x1800051d9  lea     rax, [rsp+290h+var_230]
0x1800051de  mov     rdi, rcx
0x1800051e1  mov     [rsp+290h+hKey], r14
0x1800051e6  mov     rcx, [rcx]; hKey
0x1800051e9  mov     r9d, 2001Fh; samDesired
0x1800051ef  xor     r8d, r8d; ulOptions
0x1800051f2  mov     [rsp+290h+var_240], r14
0x1800051f7  mov     [rsp+290h+var_238], r14
0x1800051fc  mov     rsi, rdx
0x1800051ff  mov     [rsp+290h+var_230], r14
0x180005204  mov     [rsp+290h+phkResult], rax; phkResult
0x180005209  call    cs:__imp_RegOpenKeyExW
0x18000520f  mov     rcx, [rsp+290h+hKey]; hKey
0x180005214  mov     ebx, eax
0x180005216  test    eax, eax
0x180005218  jnz     loc_1800052BB
0x18000521e  mov     ebx, r14d
0x180005221  test    rcx, rcx
0x180005224  jz      short loc_18000522E
0x180005226  call    cs:__imp_RegCloseKey
0x18000522c  mov     ebx, eax
0x18000522e  mov     rcx, [rsp+290h+var_230]
0x180005233  mov     [rsp+290h+hKey], rcx
0x180005238  test    ebx, ebx
0x18000523a  jnz     short loc_1800052BB
0x18000523c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180005241  jmp     short loc_18000525D
0x180005243  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180005248  lea     rcx, [rsp+290h+hKey]; this
0x18000524d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180005252  mov     rcx, [rsp+290h+hKey]; hKey
0x180005257  mov     ebx, eax
0x180005259  test    eax, eax
0x18000525b  jnz     short loc_1800052BB
0x18000525d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180005262  mov     [rsp+290h+cchName], 100h
0x18000526a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000526f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180005274  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180005279  lea     r8, [rsp+290h+Name]; lpName
0x18000527e  mov     [rsp+290h+lpClass], r14; lpClass
0x180005283  xor     edx, edx; dwIndex
0x180005285  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000528a  call    cs:__imp_RegEnumKeyExW
0x180005290  test    eax, eax
0x180005292  jz      short loc_180005243
0x180005294  mov     rcx, [rsp+290h+hKey]; hKey
0x180005299  test    rcx, rcx
0x18000529c  jz      short loc_1800052A9
0x18000529e  call    cs:__imp_RegCloseKey
0x1800052a4  mov     [rsp+290h+hKey], r14
0x1800052a9  mov     rdx, rsi; unsigned __int16 *
0x1800052ac  mov     rcx, rdi; this
0x1800052af  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800052b4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800052b9  mov     ebx, eax
0x1800052bb  test    rcx, rcx
0x1800052be  jz      short loc_1800052C6
0x1800052c0  call    cs:__imp_RegCloseKey
0x1800052c6  mov     eax, ebx
0x1800052c8  mov     rcx, [rbp+190h+var_20]
0x1800052cf  xor     rcx, rsp; StackCookie
0x1800052d2  call    __security_check_cookie
0x1800052d7  lea     r11, [rsp+290h+var_10]
0x1800052df  mov     rbx, [r11+30h]
0x1800052e3  mov     rsi, [r11+38h]
0x1800052e7  mov     rsp, r11
0x1800052ea  pop     r14
0x1800052ec  pop     rdi
0x1800052ed  pop     rbp
0x1800052ee  retn
```
