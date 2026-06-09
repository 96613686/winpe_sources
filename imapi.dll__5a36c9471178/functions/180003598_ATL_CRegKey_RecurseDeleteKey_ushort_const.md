# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180003598`
- end: `0x1800036df`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003598`
- `0x180003a3c`

## callees

- `0x180002e78`
- `0x180003598`
- `0x180018500`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180003616`
- `ADVAPI32!RegCloseKey` at `0x18000368e`
- `ADVAPI32!RegCloseKey` at `0x1800036b0`
- `ADVAPI32!RegCloseKey` at `0x180003616`
- `ADVAPI32!RegCloseKey` at `0x18000368e`
- `ADVAPI32!RegCloseKey` at `0x1800036b0`
- `ADVAPI32!RegEnumKeyExW` at `0x18000367a`
- `ADVAPI32!RegEnumKeyExW` at `0x18000367a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800035f9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800035f9`

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
0x180003598  mov     [rsp-8+arg_10], rbx
0x18000359d  mov     [rsp-8+arg_18], rsi
0x1800035a2  push    rbp
0x1800035a3  push    rdi
0x1800035a4  push    r14
0x1800035a6  lea     rbp, [rsp-180h]
0x1800035ae  sub     rsp, 280h
0x1800035b5  mov     rax, cs:__security_cookie
0x1800035bc  xor     rax, rsp
0x1800035bf  mov     [rbp+190h+var_20], rax
0x1800035c6  xor     r14d, r14d
0x1800035c9  lea     rax, [rsp+290h+var_230]
0x1800035ce  mov     rdi, rcx
0x1800035d1  mov     [rsp+290h+hKey], r14
0x1800035d6  mov     rcx, [rcx]; hKey
0x1800035d9  mov     r9d, 2001Fh; samDesired
0x1800035df  xor     r8d, r8d; ulOptions
0x1800035e2  mov     [rsp+290h+var_240], r14
0x1800035e7  mov     [rsp+290h+var_238], r14
0x1800035ec  mov     rsi, rdx
0x1800035ef  mov     [rsp+290h+var_230], r14
0x1800035f4  mov     [rsp+290h+phkResult], rax; phkResult
0x1800035f9  call    cs:__imp_RegOpenKeyExW
0x1800035ff  mov     rcx, [rsp+290h+hKey]; hKey
0x180003604  mov     ebx, eax
0x180003606  test    eax, eax
0x180003608  jnz     loc_1800036AB
0x18000360e  mov     ebx, r14d
0x180003611  test    rcx, rcx
0x180003614  jz      short loc_18000361E
0x180003616  call    cs:__imp_RegCloseKey
0x18000361c  mov     ebx, eax
0x18000361e  mov     rcx, [rsp+290h+var_230]
0x180003623  mov     [rsp+290h+hKey], rcx
0x180003628  test    ebx, ebx
0x18000362a  jnz     short loc_1800036AB
0x18000362c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180003631  jmp     short loc_18000364D
0x180003633  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180003638  lea     rcx, [rsp+290h+hKey]; this
0x18000363d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180003642  mov     rcx, [rsp+290h+hKey]; hKey
0x180003647  mov     ebx, eax
0x180003649  test    eax, eax
0x18000364b  jnz     short loc_1800036AB
0x18000364d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180003652  mov     [rsp+290h+cchName], 100h
0x18000365a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000365f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180003664  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180003669  lea     r8, [rsp+290h+Name]; lpName
0x18000366e  mov     [rsp+290h+lpClass], r14; lpClass
0x180003673  xor     edx, edx; dwIndex
0x180003675  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000367a  call    cs:__imp_RegEnumKeyExW
0x180003680  test    eax, eax
0x180003682  jz      short loc_180003633
0x180003684  mov     rcx, [rsp+290h+hKey]; hKey
0x180003689  test    rcx, rcx
0x18000368c  jz      short loc_180003699
0x18000368e  call    cs:__imp_RegCloseKey
0x180003694  mov     [rsp+290h+hKey], r14
0x180003699  mov     rdx, rsi; unsigned __int16 *
0x18000369c  mov     rcx, rdi; this
0x18000369f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800036a4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800036a9  mov     ebx, eax
0x1800036ab  test    rcx, rcx
0x1800036ae  jz      short loc_1800036B6
0x1800036b0  call    cs:__imp_RegCloseKey
0x1800036b6  mov     eax, ebx
0x1800036b8  mov     rcx, [rbp+190h+var_20]
0x1800036bf  xor     rcx, rsp; StackCookie
0x1800036c2  call    __security_check_cookie
0x1800036c7  lea     r11, [rsp+290h+var_10]
0x1800036cf  mov     rbx, [r11+30h]
0x1800036d3  mov     rsi, [r11+38h]
0x1800036d7  mov     rsp, r11
0x1800036da  pop     r14
0x1800036dc  pop     rdi
0x1800036dd  pop     rbp
0x1800036de  retn
```
