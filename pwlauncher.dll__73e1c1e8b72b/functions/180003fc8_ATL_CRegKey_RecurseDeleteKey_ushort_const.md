# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180003fc8`
- end: `0x18000410f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003fc8`
- `0x18000448c`

## callees

- `0x180003874`
- `0x180003fc8`
- `0x18000fe10`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180004046`
- `ADVAPI32!RegCloseKey` at `0x1800040be`
- `ADVAPI32!RegCloseKey` at `0x1800040e0`
- `ADVAPI32!RegCloseKey` at `0x180004046`
- `ADVAPI32!RegCloseKey` at `0x1800040be`
- `ADVAPI32!RegCloseKey` at `0x1800040e0`
- `ADVAPI32!RegEnumKeyExW` at `0x1800040aa`
- `ADVAPI32!RegEnumKeyExW` at `0x1800040aa`
- `ADVAPI32!RegOpenKeyExW` at `0x180004029`
- `ADVAPI32!RegOpenKeyExW` at `0x180004029`

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
0x180003fc8  mov     [rsp-8+arg_10], rbx
0x180003fcd  mov     [rsp-8+arg_18], rsi
0x180003fd2  push    rbp
0x180003fd3  push    rdi
0x180003fd4  push    r14
0x180003fd6  lea     rbp, [rsp-180h]
0x180003fde  sub     rsp, 280h
0x180003fe5  mov     rax, cs:__security_cookie
0x180003fec  xor     rax, rsp
0x180003fef  mov     [rbp+190h+var_20], rax
0x180003ff6  xor     r14d, r14d
0x180003ff9  lea     rax, [rsp+290h+var_230]
0x180003ffe  mov     rdi, rcx
0x180004001  mov     [rsp+290h+hKey], r14
0x180004006  mov     rcx, [rcx]; hKey
0x180004009  mov     r9d, 2001Fh; samDesired
0x18000400f  xor     r8d, r8d; ulOptions
0x180004012  mov     [rsp+290h+var_240], r14
0x180004017  mov     [rsp+290h+var_238], r14
0x18000401c  mov     rsi, rdx
0x18000401f  mov     [rsp+290h+var_230], r14
0x180004024  mov     [rsp+290h+phkResult], rax; phkResult
0x180004029  call    cs:__imp_RegOpenKeyExW
0x18000402f  mov     rcx, [rsp+290h+hKey]; hKey
0x180004034  mov     ebx, eax
0x180004036  test    eax, eax
0x180004038  jnz     loc_1800040DB
0x18000403e  mov     ebx, r14d
0x180004041  test    rcx, rcx
0x180004044  jz      short loc_18000404E
0x180004046  call    cs:__imp_RegCloseKey
0x18000404c  mov     ebx, eax
0x18000404e  mov     rcx, [rsp+290h+var_230]
0x180004053  mov     [rsp+290h+hKey], rcx
0x180004058  test    ebx, ebx
0x18000405a  jnz     short loc_1800040DB
0x18000405c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180004061  jmp     short loc_18000407D
0x180004063  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180004068  lea     rcx, [rsp+290h+hKey]; this
0x18000406d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004072  mov     rcx, [rsp+290h+hKey]; hKey
0x180004077  mov     ebx, eax
0x180004079  test    eax, eax
0x18000407b  jnz     short loc_1800040DB
0x18000407d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180004082  mov     [rsp+290h+cchName], 100h
0x18000408a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000408f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004094  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180004099  lea     r8, [rsp+290h+Name]; lpName
0x18000409e  mov     [rsp+290h+lpClass], r14; lpClass
0x1800040a3  xor     edx, edx; dwIndex
0x1800040a5  mov     [rsp+290h+phkResult], r14; lpReserved
0x1800040aa  call    cs:__imp_RegEnumKeyExW
0x1800040b0  test    eax, eax
0x1800040b2  jz      short loc_180004063
0x1800040b4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800040b9  test    rcx, rcx
0x1800040bc  jz      short loc_1800040C9
0x1800040be  call    cs:__imp_RegCloseKey
0x1800040c4  mov     [rsp+290h+hKey], r14
0x1800040c9  mov     rdx, rsi; unsigned __int16 *
0x1800040cc  mov     rcx, rdi; this
0x1800040cf  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800040d4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800040d9  mov     ebx, eax
0x1800040db  test    rcx, rcx
0x1800040de  jz      short loc_1800040E6
0x1800040e0  call    cs:__imp_RegCloseKey
0x1800040e6  mov     eax, ebx
0x1800040e8  mov     rcx, [rbp+190h+var_20]
0x1800040ef  xor     rcx, rsp; StackCookie
0x1800040f2  call    __security_check_cookie
0x1800040f7  lea     r11, [rsp+290h+var_10]
0x1800040ff  mov     rbx, [r11+30h]
0x180004103  mov     rsi, [r11+38h]
0x180004107  mov     rsp, r11
0x18000410a  pop     r14
0x18000410c  pop     rdi
0x18000410d  pop     rbp
0x18000410e  retn
```
