# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x18000892c`
- end: `0x180008a73`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000892c`
- `0x180008dd0`

## callees

- `0x1800052a0`
- `0x18000892c`
- `0x180018500`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180008a0e`
- `ADVAPI32!RegEnumKeyExW` at `0x180008a0e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000898d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000898d`
- `ADVAPI32!RegCloseKey` at `0x1800089aa`
- `ADVAPI32!RegCloseKey` at `0x180008a22`
- `ADVAPI32!RegCloseKey` at `0x180008a44`
- `ADVAPI32!RegCloseKey` at `0x1800089aa`
- `ADVAPI32!RegCloseKey` at `0x180008a22`
- `ADVAPI32!RegCloseKey` at `0x180008a44`

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
0x18000892c  mov     [rsp-8+arg_10], rbx
0x180008931  mov     [rsp-8+arg_18], rsi
0x180008936  push    rbp
0x180008937  push    rdi
0x180008938  push    r14
0x18000893a  lea     rbp, [rsp-180h]
0x180008942  sub     rsp, 280h
0x180008949  mov     rax, cs:__security_cookie
0x180008950  xor     rax, rsp
0x180008953  mov     [rbp+190h+var_20], rax
0x18000895a  xor     r14d, r14d
0x18000895d  lea     rax, [rsp+290h+var_230]
0x180008962  mov     rdi, rcx
0x180008965  mov     [rsp+290h+hKey], r14
0x18000896a  mov     rcx, [rcx]; hKey
0x18000896d  mov     r9d, 2001Fh; samDesired
0x180008973  xor     r8d, r8d; ulOptions
0x180008976  mov     [rsp+290h+var_240], r14
0x18000897b  mov     [rsp+290h+var_238], r14
0x180008980  mov     rsi, rdx
0x180008983  mov     [rsp+290h+var_230], r14
0x180008988  mov     [rsp+290h+phkResult], rax; phkResult
0x18000898d  call    cs:__imp_RegOpenKeyExW
0x180008993  mov     rcx, [rsp+290h+hKey]; hKey
0x180008998  mov     ebx, eax
0x18000899a  test    eax, eax
0x18000899c  jnz     loc_180008A3F
0x1800089a2  mov     ebx, r14d
0x1800089a5  test    rcx, rcx
0x1800089a8  jz      short loc_1800089B2
0x1800089aa  call    cs:__imp_RegCloseKey
0x1800089b0  mov     ebx, eax
0x1800089b2  mov     rcx, [rsp+290h+var_230]
0x1800089b7  mov     [rsp+290h+hKey], rcx
0x1800089bc  test    ebx, ebx
0x1800089be  jnz     short loc_180008A3F
0x1800089c0  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800089c5  jmp     short loc_1800089E1
0x1800089c7  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800089cc  lea     rcx, [rsp+290h+hKey]; this
0x1800089d1  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800089d6  mov     rcx, [rsp+290h+hKey]; hKey
0x1800089db  mov     ebx, eax
0x1800089dd  test    eax, eax
0x1800089df  jnz     short loc_180008A3F
0x1800089e1  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800089e6  mov     [rsp+290h+cchName], 100h
0x1800089ee  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800089f3  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800089f8  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800089fd  lea     r8, [rsp+290h+Name]; lpName
0x180008a02  mov     [rsp+290h+lpClass], r14; lpClass
0x180008a07  xor     edx, edx; dwIndex
0x180008a09  mov     [rsp+290h+phkResult], r14; lpReserved
0x180008a0e  call    cs:__imp_RegEnumKeyExW
0x180008a14  test    eax, eax
0x180008a16  jz      short loc_1800089C7
0x180008a18  mov     rcx, [rsp+290h+hKey]; hKey
0x180008a1d  test    rcx, rcx
0x180008a20  jz      short loc_180008A2D
0x180008a22  call    cs:__imp_RegCloseKey
0x180008a28  mov     [rsp+290h+hKey], r14
0x180008a2d  mov     rdx, rsi; unsigned __int16 *
0x180008a30  mov     rcx, rdi; this
0x180008a33  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180008a38  mov     rcx, [rsp+290h+hKey]; hKey
0x180008a3d  mov     ebx, eax
0x180008a3f  test    rcx, rcx
0x180008a42  jz      short loc_180008A4A
0x180008a44  call    cs:__imp_RegCloseKey
0x180008a4a  mov     eax, ebx
0x180008a4c  mov     rcx, [rbp+190h+var_20]
0x180008a53  xor     rcx, rsp; StackCookie
0x180008a56  call    __security_check_cookie
0x180008a5b  lea     r11, [rsp+290h+var_10]
0x180008a63  mov     rbx, [r11+30h]
0x180008a67  mov     rsi, [r11+38h]
0x180008a6b  mov     rsp, r11
0x180008a6e  pop     r14
0x180008a70  pop     rdi
0x180008a71  pop     rbp
0x180008a72  retn
```
