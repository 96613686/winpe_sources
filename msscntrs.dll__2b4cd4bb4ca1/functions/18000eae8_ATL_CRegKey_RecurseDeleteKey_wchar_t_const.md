# ATL::CRegKey::RecurseDeleteKey(wchar_t const *)

- ea: `0x18000eae8`
- end: `0x18000ec2f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const wchar_t *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000eae8`
- `0x18000efac`

## callees

- `0x1800024a0`
- `0x18000c790`
- `0x18000eae8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eb66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ebde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ec00`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000eb66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ebde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ec00`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000eb49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000eb49`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000ebca`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000ebca`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const wchar_t *a2)
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
0x18000eae8  mov     [rsp-8+arg_10], rbx
0x18000eaed  mov     [rsp-8+arg_18], rsi
0x18000eaf2  push    rbp
0x18000eaf3  push    rdi
0x18000eaf4  push    r14
0x18000eaf6  lea     rbp, [rsp-180h]
0x18000eafe  sub     rsp, 280h
0x18000eb05  mov     rax, cs:__security_cookie
0x18000eb0c  xor     rax, rsp
0x18000eb0f  mov     [rbp+190h+var_20], rax
0x18000eb16  xor     r14d, r14d
0x18000eb19  lea     rax, [rsp+290h+var_230]
0x18000eb1e  mov     rdi, rcx
0x18000eb21  mov     [rsp+290h+hKey], r14
0x18000eb26  mov     rcx, [rcx]; hKey
0x18000eb29  mov     r9d, 2001Fh; samDesired
0x18000eb2f  xor     r8d, r8d; ulOptions
0x18000eb32  mov     [rsp+290h+var_240], r14
0x18000eb37  mov     [rsp+290h+var_238], r14
0x18000eb3c  mov     rsi, rdx
0x18000eb3f  mov     [rsp+290h+var_230], r14
0x18000eb44  mov     [rsp+290h+phkResult], rax; phkResult
0x18000eb49  call    cs:__imp_RegOpenKeyExW
0x18000eb4f  mov     rcx, [rsp+290h+hKey]; hKey
0x18000eb54  mov     ebx, eax
0x18000eb56  test    eax, eax
0x18000eb58  jnz     loc_18000EBFB
0x18000eb5e  mov     ebx, r14d
0x18000eb61  test    rcx, rcx
0x18000eb64  jz      short loc_18000EB6E
0x18000eb66  call    cs:__imp_RegCloseKey
0x18000eb6c  mov     ebx, eax
0x18000eb6e  mov     rcx, [rsp+290h+var_230]
0x18000eb73  mov     [rsp+290h+hKey], rcx
0x18000eb78  test    ebx, ebx
0x18000eb7a  jnz     short loc_18000EBFB
0x18000eb7c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x18000eb81  jmp     short loc_18000EB9D
0x18000eb83  lea     rdx, [rsp+290h+Name]; wchar_t *
0x18000eb88  lea     rcx, [rsp+290h+hKey]; this
0x18000eb8d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::RecurseDeleteKey(wchar_t const *)
0x18000eb92  mov     rcx, [rsp+290h+hKey]; hKey
0x18000eb97  mov     ebx, eax
0x18000eb99  test    eax, eax
0x18000eb9b  jnz     short loc_18000EBFB
0x18000eb9d  lea     rax, [rsp+290h+ftLastWriteTime]
0x18000eba2  mov     [rsp+290h+cchName], 100h
0x18000ebaa  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000ebaf  lea     r9, [rsp+290h+cchName]; lpcchName
0x18000ebb4  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x18000ebb9  lea     r8, [rsp+290h+Name]; lpName
0x18000ebbe  mov     [rsp+290h+lpClass], r14; lpClass
0x18000ebc3  xor     edx, edx; dwIndex
0x18000ebc5  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000ebca  call    cs:__imp_RegEnumKeyExW
0x18000ebd0  test    eax, eax
0x18000ebd2  jz      short loc_18000EB83
0x18000ebd4  mov     rcx, [rsp+290h+hKey]; hKey
0x18000ebd9  test    rcx, rcx
0x18000ebdc  jz      short loc_18000EBE9
0x18000ebde  call    cs:__imp_RegCloseKey
0x18000ebe4  mov     [rsp+290h+hKey], r14
0x18000ebe9  mov     rdx, rsi; wchar_t *
0x18000ebec  mov     rcx, rdi; this
0x18000ebef  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z; ATL::CRegKey::DeleteSubKey(wchar_t const *)
0x18000ebf4  mov     rcx, [rsp+290h+hKey]; hKey
0x18000ebf9  mov     ebx, eax
0x18000ebfb  test    rcx, rcx
0x18000ebfe  jz      short loc_18000EC06
0x18000ec00  call    cs:__imp_RegCloseKey
0x18000ec06  mov     eax, ebx
0x18000ec08  mov     rcx, [rbp+190h+var_20]
0x18000ec0f  xor     rcx, rsp; StackCookie
0x18000ec12  call    __security_check_cookie
0x18000ec17  lea     r11, [rsp+290h+var_10]
0x18000ec1f  mov     rbx, [r11+30h]
0x18000ec23  mov     rsi, [r11+38h]
0x18000ec27  mov     rsp, r11
0x18000ec2a  pop     r14
0x18000ec2c  pop     rdi
0x18000ec2d  pop     rbp
0x18000ec2e  retn
```
