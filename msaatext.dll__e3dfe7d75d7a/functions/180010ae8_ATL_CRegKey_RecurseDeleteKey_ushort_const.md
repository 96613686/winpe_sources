# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180010ae8`
- end: `0x180010c35`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `333`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010ae8`
- `0x180011038`

## callees

- `0x1800100a8`
- `0x180010ae8`
- `0x180012b40`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180010bce`
- `ADVAPI32!RegEnumKeyExW` at `0x180010bce`
- `ADVAPI32!RegCloseKey` at `0x180010b66`
- `ADVAPI32!RegCloseKey` at `0x180010be2`
- `ADVAPI32!RegCloseKey` at `0x180010c06`
- `ADVAPI32!RegCloseKey` at `0x180010b66`
- `ADVAPI32!RegCloseKey` at `0x180010be2`
- `ADVAPI32!RegCloseKey` at `0x180010c06`
- `ADVAPI32!RegOpenKeyExW` at `0x180010b49`
- `ADVAPI32!RegOpenKeyExW` at `0x180010b49`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  DWORD v4; // ebx
  HKEY v5; // rcx
  HKEY v6; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  phkResult = 0;
  v4 = RegOpenKeyExW(*this, a2, 0, 0x2001Fu, &phkResult);
  v5 = 0;
  if ( !v4 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_9;
      v6 = hKey[0];
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
LABEL_9:
    v5 = hKey[0];
  }
  if ( v5 )
    RegCloseKey(v5);
  return v4;
}

```

## disassembly

```asm
0x180010ae8  mov     [rsp-8+arg_10], rbx
0x180010aed  mov     [rsp-8+arg_18], rsi
0x180010af2  push    rbp
0x180010af3  push    rdi
0x180010af4  push    r14
0x180010af6  lea     rbp, [rsp-180h]
0x180010afe  sub     rsp, 280h
0x180010b05  mov     rax, cs:__security_cookie
0x180010b0c  xor     rax, rsp
0x180010b0f  mov     [rbp+190h+var_20], rax
0x180010b16  mov     rsi, rdx
0x180010b19  mov     rdi, rcx
0x180010b1c  xor     r14d, r14d
0x180010b1f  mov     [rsp+290h+hKey], r14
0x180010b24  mov     [rsp+290h+var_240], r14
0x180010b29  mov     [rsp+290h+var_238], r14
0x180010b2e  mov     [rsp+290h+var_230], r14
0x180010b33  lea     rax, [rsp+290h+var_230]
0x180010b38  mov     [rsp+290h+phkResult], rax; phkResult
0x180010b3d  mov     r9d, 2001Fh; samDesired
0x180010b43  xor     r8d, r8d; ulOptions
0x180010b46  mov     rcx, [rcx]; hKey
0x180010b49  call    cs:__imp_RegOpenKeyExW
0x180010b4f  mov     ebx, eax
0x180010b51  mov     rcx, [rsp+290h+hKey]; hKey
0x180010b56  test    eax, eax
0x180010b58  jnz     loc_180010C01
0x180010b5e  mov     ebx, r14d
0x180010b61  test    rcx, rcx
0x180010b64  jz      short loc_180010B6E
0x180010b66  call    cs:__imp_RegCloseKey
0x180010b6c  mov     ebx, eax
0x180010b6e  mov     rcx, [rsp+290h+var_230]
0x180010b73  mov     [rsp+290h+hKey], rcx
0x180010b78  test    ebx, ebx
0x180010b7a  jnz     loc_180010C01
0x180010b80  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180010b85  jmp     short loc_180010BA1
0x180010b87  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180010b8c  lea     rcx, [rsp+290h+hKey]; this
0x180010b91  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180010b96  mov     ebx, eax
0x180010b98  test    eax, eax
0x180010b9a  jnz     short loc_180010BFA
0x180010b9c  mov     rcx, [rsp+290h+hKey]; hKey
0x180010ba1  lea     rax, [rsp+290h+ftLastWriteTime]
0x180010ba6  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180010bab  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180010bb0  mov     [rsp+290h+lpClass], r14; lpClass
0x180010bb5  mov     [rsp+290h+phkResult], r14; lpReserved
0x180010bba  mov     [rsp+290h+cchName], 100h
0x180010bc2  lea     r9, [rsp+290h+cchName]; lpcchName
0x180010bc7  lea     r8, [rsp+290h+Name]; lpName
0x180010bcc  xor     edx, edx; dwIndex
0x180010bce  call    cs:__imp_RegEnumKeyExW
0x180010bd4  test    eax, eax
0x180010bd6  jz      short loc_180010B87
0x180010bd8  mov     rcx, [rsp+290h+hKey]; hKey
0x180010bdd  test    rcx, rcx
0x180010be0  jz      short loc_180010BED
0x180010be2  call    cs:__imp_RegCloseKey
0x180010be8  mov     [rsp+290h+hKey], r14
0x180010bed  mov     rdx, rsi; unsigned __int16 *
0x180010bf0  mov     rcx, rdi; this
0x180010bf3  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180010bf8  mov     ebx, eax
0x180010bfa  mov     rcx, [rsp+290h+hKey]
0x180010bff  jmp     short $+2
0x180010c01  test    rcx, rcx
0x180010c04  jz      short loc_180010C0C
0x180010c06  call    cs:__imp_RegCloseKey
0x180010c0c  mov     eax, ebx
0x180010c0e  mov     rcx, [rbp+190h+var_20]
0x180010c15  xor     rcx, rsp; StackCookie
0x180010c18  call    __security_check_cookie
0x180010c1d  lea     r11, [rsp+290h+var_10]
0x180010c25  mov     rbx, [r11+30h]
0x180010c29  mov     rsi, [r11+38h]
0x180010c2d  mov     rsp, r11
0x180010c30  pop     r14
0x180010c32  pop     rdi
0x180010c33  pop     rbp
0x180010c34  retn
```
