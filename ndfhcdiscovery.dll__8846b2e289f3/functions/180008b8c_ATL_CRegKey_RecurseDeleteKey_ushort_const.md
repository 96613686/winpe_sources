# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180008b8c`
- end: `0x180008cf6`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008b8c`
- `0x180009108`

## callees

- `0x180006f3c`
- `0x180008b8c`
- `0x1800136b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180008c10`
- `ADVAPI32!RegCloseKey` at `0x180008c98`
- `ADVAPI32!RegCloseKey` at `0x180008cc0`
- `ADVAPI32!RegCloseKey` at `0x180008c10`
- `ADVAPI32!RegCloseKey` at `0x180008c98`
- `ADVAPI32!RegCloseKey` at `0x180008cc0`
- `ADVAPI32!RegOpenKeyExW` at `0x180008bed`
- `ADVAPI32!RegOpenKeyExW` at `0x180008bed`
- `ADVAPI32!RegEnumKeyExW` at `0x180008c7e`
- `ADVAPI32!RegEnumKeyExW` at `0x180008c7e`

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
0x180008b8c  mov     [rsp-8+arg_10], rbx
0x180008b91  mov     [rsp-8+arg_18], rsi
0x180008b96  push    rbp
0x180008b97  push    rdi
0x180008b98  push    r14
0x180008b9a  lea     rbp, [rsp-180h]
0x180008ba2  sub     rsp, 280h
0x180008ba9  mov     rax, cs:__security_cookie
0x180008bb0  xor     rax, rsp
0x180008bb3  mov     [rbp+190h+var_20], rax
0x180008bba  xor     r14d, r14d
0x180008bbd  lea     rax, [rsp+290h+var_230]
0x180008bc2  mov     rdi, rcx
0x180008bc5  mov     [rsp+290h+hKey], r14
0x180008bca  mov     rcx, [rcx]; hKey
0x180008bcd  mov     r9d, 2001Fh; samDesired
0x180008bd3  xor     r8d, r8d; ulOptions
0x180008bd6  mov     [rsp+290h+var_240], r14
0x180008bdb  mov     [rsp+290h+var_238], r14
0x180008be0  mov     rsi, rdx
0x180008be3  mov     [rsp+290h+var_230], r14
0x180008be8  mov     [rsp+290h+phkResult], rax; phkResult
0x180008bed  call    cs:__imp_RegOpenKeyExW
0x180008bf4  nop     dword ptr [rax+rax+00h]
0x180008bf9  mov     rcx, [rsp+290h+hKey]; hKey
0x180008bfe  mov     ebx, eax
0x180008c00  test    eax, eax
0x180008c02  jnz     loc_180008CBB
0x180008c08  mov     ebx, r14d
0x180008c0b  test    rcx, rcx
0x180008c0e  jz      short loc_180008C1E
0x180008c10  call    cs:__imp_RegCloseKey
0x180008c17  nop     dword ptr [rax+rax+00h]
0x180008c1c  mov     ebx, eax
0x180008c1e  mov     rcx, [rsp+290h+var_230]
0x180008c23  mov     [rsp+290h+hKey], rcx
0x180008c28  test    ebx, ebx
0x180008c2a  jnz     loc_180008CBB
0x180008c30  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180008c35  jmp     short loc_180008C51
0x180008c37  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180008c3c  lea     rcx, [rsp+290h+hKey]; this
0x180008c41  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008c46  mov     rcx, [rsp+290h+hKey]; hKey
0x180008c4b  mov     ebx, eax
0x180008c4d  test    eax, eax
0x180008c4f  jnz     short loc_180008CBB
0x180008c51  lea     rax, [rsp+290h+ftLastWriteTime]
0x180008c56  mov     [rsp+290h+cchName], 100h
0x180008c5e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180008c63  lea     r9, [rsp+290h+cchName]; lpcchName
0x180008c68  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180008c6d  lea     r8, [rsp+290h+Name]; lpName
0x180008c72  mov     [rsp+290h+lpClass], r14; lpClass
0x180008c77  xor     edx, edx; dwIndex
0x180008c79  mov     [rsp+290h+phkResult], r14; lpReserved
0x180008c7e  call    cs:__imp_RegEnumKeyExW
0x180008c85  nop     dword ptr [rax+rax+00h]
0x180008c8a  test    eax, eax
0x180008c8c  jz      short loc_180008C37
0x180008c8e  mov     rcx, [rsp+290h+hKey]; hKey
0x180008c93  test    rcx, rcx
0x180008c96  jz      short loc_180008CA9
0x180008c98  call    cs:__imp_RegCloseKey
0x180008c9f  nop     dword ptr [rax+rax+00h]
0x180008ca4  mov     [rsp+290h+hKey], r14
0x180008ca9  mov     rdx, rsi; unsigned __int16 *
0x180008cac  mov     rcx, rdi; this
0x180008caf  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180008cb4  mov     rcx, [rsp+290h+hKey]; hKey
0x180008cb9  mov     ebx, eax
0x180008cbb  test    rcx, rcx
0x180008cbe  jz      short loc_180008CCC
0x180008cc0  call    cs:__imp_RegCloseKey
0x180008cc7  nop     dword ptr [rax+rax+00h]
0x180008ccc  mov     eax, ebx
0x180008cce  mov     rcx, [rbp+190h+var_20]
0x180008cd5  xor     rcx, rsp; StackCookie
0x180008cd8  call    __security_check_cookie
0x180008cdd  lea     r11, [rsp+290h+var_10]
0x180008ce5  mov     rbx, [r11+30h]
0x180008ce9  mov     rsi, [r11+38h]
0x180008ced  mov     rsp, r11
0x180008cf0  pop     r14
0x180008cf2  pop     rdi
0x180008cf3  pop     rbp
0x180008cf4  retn
```
