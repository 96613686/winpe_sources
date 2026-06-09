# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180004148`
- end: `0x18000428f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004148`
- `0x18000460c`

## callees

- `0x1800038e8`
- `0x180004148`
- `0x180009a00`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800041c6`
- `ADVAPI32!RegCloseKey` at `0x18000423e`
- `ADVAPI32!RegCloseKey` at `0x180004260`
- `ADVAPI32!RegCloseKey` at `0x1800041c6`
- `ADVAPI32!RegCloseKey` at `0x18000423e`
- `ADVAPI32!RegCloseKey` at `0x180004260`
- `ADVAPI32!RegEnumKeyExW` at `0x18000422a`
- `ADVAPI32!RegEnumKeyExW` at `0x18000422a`
- `ADVAPI32!RegOpenKeyExW` at `0x1800041a9`
- `ADVAPI32!RegOpenKeyExW` at `0x1800041a9`

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
0x180004148  mov     [rsp-8+arg_10], rbx
0x18000414d  mov     [rsp-8+arg_18], rsi
0x180004152  push    rbp
0x180004153  push    rdi
0x180004154  push    r14
0x180004156  lea     rbp, [rsp-180h]
0x18000415e  sub     rsp, 280h
0x180004165  mov     rax, cs:__security_cookie
0x18000416c  xor     rax, rsp
0x18000416f  mov     [rbp+190h+var_20], rax
0x180004176  xor     r14d, r14d
0x180004179  lea     rax, [rsp+290h+var_230]
0x18000417e  mov     rdi, rcx
0x180004181  mov     [rsp+290h+hKey], r14
0x180004186  mov     rcx, [rcx]; hKey
0x180004189  mov     r9d, 2001Fh; samDesired
0x18000418f  xor     r8d, r8d; ulOptions
0x180004192  mov     [rsp+290h+var_240], r14
0x180004197  mov     [rsp+290h+var_238], r14
0x18000419c  mov     rsi, rdx
0x18000419f  mov     [rsp+290h+var_230], r14
0x1800041a4  mov     [rsp+290h+phkResult], rax; phkResult
0x1800041a9  call    cs:__imp_RegOpenKeyExW
0x1800041af  mov     rcx, [rsp+290h+hKey]; hKey
0x1800041b4  mov     ebx, eax
0x1800041b6  test    eax, eax
0x1800041b8  jnz     loc_18000425B
0x1800041be  mov     ebx, r14d
0x1800041c1  test    rcx, rcx
0x1800041c4  jz      short loc_1800041CE
0x1800041c6  call    cs:__imp_RegCloseKey
0x1800041cc  mov     ebx, eax
0x1800041ce  mov     rcx, [rsp+290h+var_230]
0x1800041d3  mov     [rsp+290h+hKey], rcx
0x1800041d8  test    ebx, ebx
0x1800041da  jnz     short loc_18000425B
0x1800041dc  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800041e1  jmp     short loc_1800041FD
0x1800041e3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800041e8  lea     rcx, [rsp+290h+hKey]; this
0x1800041ed  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800041f2  mov     rcx, [rsp+290h+hKey]; hKey
0x1800041f7  mov     ebx, eax
0x1800041f9  test    eax, eax
0x1800041fb  jnz     short loc_18000425B
0x1800041fd  lea     rax, [rsp+290h+ftLastWriteTime]
0x180004202  mov     [rsp+290h+cchName], 100h
0x18000420a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000420f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004214  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180004219  lea     r8, [rsp+290h+Name]; lpName
0x18000421e  mov     [rsp+290h+lpClass], r14; lpClass
0x180004223  xor     edx, edx; dwIndex
0x180004225  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000422a  call    cs:__imp_RegEnumKeyExW
0x180004230  test    eax, eax
0x180004232  jz      short loc_1800041E3
0x180004234  mov     rcx, [rsp+290h+hKey]; hKey
0x180004239  test    rcx, rcx
0x18000423c  jz      short loc_180004249
0x18000423e  call    cs:__imp_RegCloseKey
0x180004244  mov     [rsp+290h+hKey], r14
0x180004249  mov     rdx, rsi; unsigned __int16 *
0x18000424c  mov     rcx, rdi; this
0x18000424f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004254  mov     rcx, [rsp+290h+hKey]; hKey
0x180004259  mov     ebx, eax
0x18000425b  test    rcx, rcx
0x18000425e  jz      short loc_180004266
0x180004260  call    cs:__imp_RegCloseKey
0x180004266  mov     eax, ebx
0x180004268  mov     rcx, [rbp+190h+var_20]
0x18000426f  xor     rcx, rsp; StackCookie
0x180004272  call    __security_check_cookie
0x180004277  lea     r11, [rsp+290h+var_10]
0x18000427f  mov     rbx, [r11+30h]
0x180004283  mov     rsi, [r11+38h]
0x180004287  mov     rsp, r11
0x18000428a  pop     r14
0x18000428c  pop     rdi
0x18000428d  pop     rbp
0x18000428e  retn
```
