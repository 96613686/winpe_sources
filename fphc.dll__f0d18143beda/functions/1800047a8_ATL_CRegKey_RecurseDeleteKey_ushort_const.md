# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800047a8`
- end: `0x1800048ef`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800047a8`
- `0x180004c68`

## callees

- `0x180004164`
- `0x1800047a8`
- `0x180011340`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004826`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000489e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800048c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004826`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000489e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800048c0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000488a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000488a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004809`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004809`

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
0x1800047a8  mov     [rsp-8+arg_10], rbx
0x1800047ad  mov     [rsp-8+arg_18], rsi
0x1800047b2  push    rbp
0x1800047b3  push    rdi
0x1800047b4  push    r14
0x1800047b6  lea     rbp, [rsp-180h]
0x1800047be  sub     rsp, 280h
0x1800047c5  mov     rax, cs:__security_cookie
0x1800047cc  xor     rax, rsp
0x1800047cf  mov     [rbp+190h+var_20], rax
0x1800047d6  xor     r14d, r14d
0x1800047d9  lea     rax, [rsp+290h+var_230]
0x1800047de  mov     rdi, rcx
0x1800047e1  mov     [rsp+290h+hKey], r14
0x1800047e6  mov     rcx, [rcx]; hKey
0x1800047e9  mov     r9d, 2001Fh; samDesired
0x1800047ef  xor     r8d, r8d; ulOptions
0x1800047f2  mov     [rsp+290h+var_240], r14
0x1800047f7  mov     [rsp+290h+var_238], r14
0x1800047fc  mov     rsi, rdx
0x1800047ff  mov     [rsp+290h+var_230], r14
0x180004804  mov     [rsp+290h+phkResult], rax; phkResult
0x180004809  call    cs:__imp_RegOpenKeyExW
0x18000480f  mov     rcx, [rsp+290h+hKey]; hKey
0x180004814  mov     ebx, eax
0x180004816  test    eax, eax
0x180004818  jnz     loc_1800048BB
0x18000481e  mov     ebx, r14d
0x180004821  test    rcx, rcx
0x180004824  jz      short loc_18000482E
0x180004826  call    cs:__imp_RegCloseKey
0x18000482c  mov     ebx, eax
0x18000482e  mov     rcx, [rsp+290h+var_230]
0x180004833  mov     [rsp+290h+hKey], rcx
0x180004838  test    ebx, ebx
0x18000483a  jnz     short loc_1800048BB
0x18000483c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180004841  jmp     short loc_18000485D
0x180004843  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180004848  lea     rcx, [rsp+290h+hKey]; this
0x18000484d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004852  mov     rcx, [rsp+290h+hKey]; hKey
0x180004857  mov     ebx, eax
0x180004859  test    eax, eax
0x18000485b  jnz     short loc_1800048BB
0x18000485d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180004862  mov     [rsp+290h+cchName], 100h
0x18000486a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000486f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004874  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180004879  lea     r8, [rsp+290h+Name]; lpName
0x18000487e  mov     [rsp+290h+lpClass], r14; lpClass
0x180004883  xor     edx, edx; dwIndex
0x180004885  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000488a  call    cs:__imp_RegEnumKeyExW
0x180004890  test    eax, eax
0x180004892  jz      short loc_180004843
0x180004894  mov     rcx, [rsp+290h+hKey]; hKey
0x180004899  test    rcx, rcx
0x18000489c  jz      short loc_1800048A9
0x18000489e  call    cs:__imp_RegCloseKey
0x1800048a4  mov     [rsp+290h+hKey], r14
0x1800048a9  mov     rdx, rsi; unsigned __int16 *
0x1800048ac  mov     rcx, rdi; this
0x1800048af  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800048b4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800048b9  mov     ebx, eax
0x1800048bb  test    rcx, rcx
0x1800048be  jz      short loc_1800048C6
0x1800048c0  call    cs:__imp_RegCloseKey
0x1800048c6  mov     eax, ebx
0x1800048c8  mov     rcx, [rbp+190h+var_20]
0x1800048cf  xor     rcx, rsp; StackCookie
0x1800048d2  call    __security_check_cookie
0x1800048d7  lea     r11, [rsp+290h+var_10]
0x1800048df  mov     rbx, [r11+30h]
0x1800048e3  mov     rsi, [r11+38h]
0x1800048e7  mov     rsp, r11
0x1800048ea  pop     r14
0x1800048ec  pop     rdi
0x1800048ed  pop     rbp
0x1800048ee  retn
```
