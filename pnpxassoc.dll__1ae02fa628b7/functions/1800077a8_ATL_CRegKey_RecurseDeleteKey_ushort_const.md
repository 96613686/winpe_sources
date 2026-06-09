# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800077a8`
- end: `0x1800078ef`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800077a8`
- `0x180007c4c`

## callees

- `0x180006e00`
- `0x1800077a8`
- `0x180012e00`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180007809`
- `ADVAPI32!RegOpenKeyExW` at `0x180007809`
- `ADVAPI32!RegEnumKeyExW` at `0x18000788a`
- `ADVAPI32!RegEnumKeyExW` at `0x18000788a`
- `ADVAPI32!RegCloseKey` at `0x180007826`
- `ADVAPI32!RegCloseKey` at `0x18000789e`
- `ADVAPI32!RegCloseKey` at `0x1800078c0`
- `ADVAPI32!RegCloseKey` at `0x180007826`
- `ADVAPI32!RegCloseKey` at `0x18000789e`
- `ADVAPI32!RegCloseKey` at `0x1800078c0`

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
0x1800077a8  mov     [rsp-8+arg_10], rbx
0x1800077ad  mov     [rsp-8+arg_18], rsi
0x1800077b2  push    rbp
0x1800077b3  push    rdi
0x1800077b4  push    r14
0x1800077b6  lea     rbp, [rsp-180h]
0x1800077be  sub     rsp, 280h
0x1800077c5  mov     rax, cs:__security_cookie
0x1800077cc  xor     rax, rsp
0x1800077cf  mov     [rbp+190h+var_20], rax
0x1800077d6  xor     r14d, r14d
0x1800077d9  lea     rax, [rsp+290h+var_230]
0x1800077de  mov     rdi, rcx
0x1800077e1  mov     [rsp+290h+hKey], r14
0x1800077e6  mov     rcx, [rcx]; hKey
0x1800077e9  mov     r9d, 2001Fh; samDesired
0x1800077ef  xor     r8d, r8d; ulOptions
0x1800077f2  mov     [rsp+290h+var_240], r14
0x1800077f7  mov     [rsp+290h+var_238], r14
0x1800077fc  mov     rsi, rdx
0x1800077ff  mov     [rsp+290h+var_230], r14
0x180007804  mov     [rsp+290h+phkResult], rax; phkResult
0x180007809  call    cs:__imp_RegOpenKeyExW
0x18000780f  mov     rcx, [rsp+290h+hKey]; hKey
0x180007814  mov     ebx, eax
0x180007816  test    eax, eax
0x180007818  jnz     loc_1800078BB
0x18000781e  mov     ebx, r14d
0x180007821  test    rcx, rcx
0x180007824  jz      short loc_18000782E
0x180007826  call    cs:__imp_RegCloseKey
0x18000782c  mov     ebx, eax
0x18000782e  mov     rcx, [rsp+290h+var_230]
0x180007833  mov     [rsp+290h+hKey], rcx
0x180007838  test    ebx, ebx
0x18000783a  jnz     short loc_1800078BB
0x18000783c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180007841  jmp     short loc_18000785D
0x180007843  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180007848  lea     rcx, [rsp+290h+hKey]; this
0x18000784d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180007852  mov     rcx, [rsp+290h+hKey]; hKey
0x180007857  mov     ebx, eax
0x180007859  test    eax, eax
0x18000785b  jnz     short loc_1800078BB
0x18000785d  lea     rax, [rsp+290h+ftLastWriteTime]
0x180007862  mov     [rsp+290h+cchName], 100h
0x18000786a  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000786f  lea     r9, [rsp+290h+cchName]; lpcchName
0x180007874  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180007879  lea     r8, [rsp+290h+Name]; lpName
0x18000787e  mov     [rsp+290h+lpClass], r14; lpClass
0x180007883  xor     edx, edx; dwIndex
0x180007885  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000788a  call    cs:__imp_RegEnumKeyExW
0x180007890  test    eax, eax
0x180007892  jz      short loc_180007843
0x180007894  mov     rcx, [rsp+290h+hKey]; hKey
0x180007899  test    rcx, rcx
0x18000789c  jz      short loc_1800078A9
0x18000789e  call    cs:__imp_RegCloseKey
0x1800078a4  mov     [rsp+290h+hKey], r14
0x1800078a9  mov     rdx, rsi; unsigned __int16 *
0x1800078ac  mov     rcx, rdi; this
0x1800078af  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800078b4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800078b9  mov     ebx, eax
0x1800078bb  test    rcx, rcx
0x1800078be  jz      short loc_1800078C6
0x1800078c0  call    cs:__imp_RegCloseKey
0x1800078c6  mov     eax, ebx
0x1800078c8  mov     rcx, [rbp+190h+var_20]
0x1800078cf  xor     rcx, rsp; StackCookie
0x1800078d2  call    __security_check_cookie
0x1800078d7  lea     r11, [rsp+290h+var_10]
0x1800078df  mov     rbx, [r11+30h]
0x1800078e3  mov     rsi, [r11+38h]
0x1800078e7  mov     rsp, r11
0x1800078ea  pop     r14
0x1800078ec  pop     rdi
0x1800078ed  pop     rbp
0x1800078ee  retn
```
