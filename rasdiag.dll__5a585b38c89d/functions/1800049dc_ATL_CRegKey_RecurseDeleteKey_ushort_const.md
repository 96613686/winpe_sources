# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800049dc`
- end: `0x180004b46`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `362`
- prototype: `__int64 __fastcall(HKEY *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800049dc`
- `0x180004ef8`

## callees

- `0x1800042e0`
- `0x1800049dc`
- `0x18000df10`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180004ace`
- `ADVAPI32!RegEnumKeyExW` at `0x180004ace`
- `ADVAPI32!RegOpenKeyExW` at `0x180004a3d`
- `ADVAPI32!RegOpenKeyExW` at `0x180004a3d`
- `ADVAPI32!RegCloseKey` at `0x180004a60`
- `ADVAPI32!RegCloseKey` at `0x180004ae8`
- `ADVAPI32!RegCloseKey` at `0x180004b10`
- `ADVAPI32!RegCloseKey` at `0x180004a60`
- `ADVAPI32!RegCloseKey` at `0x180004ae8`
- `ADVAPI32!RegCloseKey` at `0x180004b10`

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
0x1800049dc  mov     [rsp-8+arg_10], rbx
0x1800049e1  mov     [rsp-8+arg_18], rsi
0x1800049e6  push    rbp
0x1800049e7  push    rdi
0x1800049e8  push    r14
0x1800049ea  lea     rbp, [rsp-180h]
0x1800049f2  sub     rsp, 280h
0x1800049f9  mov     rax, cs:__security_cookie
0x180004a00  xor     rax, rsp
0x180004a03  mov     [rbp+190h+var_20], rax
0x180004a0a  xor     r14d, r14d
0x180004a0d  lea     rax, [rsp+290h+var_230]
0x180004a12  mov     rdi, rcx
0x180004a15  mov     [rsp+290h+hKey], r14
0x180004a1a  mov     rcx, [rcx]; hKey
0x180004a1d  mov     r9d, 2001Fh; samDesired
0x180004a23  xor     r8d, r8d; ulOptions
0x180004a26  mov     [rsp+290h+var_240], r14
0x180004a2b  mov     [rsp+290h+var_238], r14
0x180004a30  mov     rsi, rdx
0x180004a33  mov     [rsp+290h+var_230], r14
0x180004a38  mov     [rsp+290h+phkResult], rax; phkResult
0x180004a3d  call    cs:__imp_RegOpenKeyExW
0x180004a44  nop     dword ptr [rax+rax+00h]
0x180004a49  mov     rcx, [rsp+290h+hKey]; hKey
0x180004a4e  mov     ebx, eax
0x180004a50  test    eax, eax
0x180004a52  jnz     loc_180004B0B
0x180004a58  mov     ebx, r14d
0x180004a5b  test    rcx, rcx
0x180004a5e  jz      short loc_180004A6E
0x180004a60  call    cs:__imp_RegCloseKey
0x180004a67  nop     dword ptr [rax+rax+00h]
0x180004a6c  mov     ebx, eax
0x180004a6e  mov     rcx, [rsp+290h+var_230]
0x180004a73  mov     [rsp+290h+hKey], rcx
0x180004a78  test    ebx, ebx
0x180004a7a  jnz     loc_180004B0B
0x180004a80  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180004a85  jmp     short loc_180004AA1
0x180004a87  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180004a8c  lea     rcx, [rsp+290h+hKey]; this
0x180004a91  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004a96  mov     rcx, [rsp+290h+hKey]; hKey
0x180004a9b  mov     ebx, eax
0x180004a9d  test    eax, eax
0x180004a9f  jnz     short loc_180004B0B
0x180004aa1  lea     rax, [rsp+290h+ftLastWriteTime]
0x180004aa6  mov     [rsp+290h+cchName], 100h
0x180004aae  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004ab3  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004ab8  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180004abd  lea     r8, [rsp+290h+Name]; lpName
0x180004ac2  mov     [rsp+290h+lpClass], r14; lpClass
0x180004ac7  xor     edx, edx; dwIndex
0x180004ac9  mov     [rsp+290h+phkResult], r14; lpReserved
0x180004ace  call    cs:__imp_RegEnumKeyExW
0x180004ad5  nop     dword ptr [rax+rax+00h]
0x180004ada  test    eax, eax
0x180004adc  jz      short loc_180004A87
0x180004ade  mov     rcx, [rsp+290h+hKey]; hKey
0x180004ae3  test    rcx, rcx
0x180004ae6  jz      short loc_180004AF9
0x180004ae8  call    cs:__imp_RegCloseKey
0x180004aef  nop     dword ptr [rax+rax+00h]
0x180004af4  mov     [rsp+290h+hKey], r14
0x180004af9  mov     rdx, rsi; unsigned __int16 *
0x180004afc  mov     rcx, rdi; this
0x180004aff  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004b04  mov     rcx, [rsp+290h+hKey]; hKey
0x180004b09  mov     ebx, eax
0x180004b0b  test    rcx, rcx
0x180004b0e  jz      short loc_180004B1C
0x180004b10  call    cs:__imp_RegCloseKey
0x180004b17  nop     dword ptr [rax+rax+00h]
0x180004b1c  mov     eax, ebx
0x180004b1e  mov     rcx, [rbp+190h+var_20]
0x180004b25  xor     rcx, rsp; StackCookie
0x180004b28  call    __security_check_cookie
0x180004b2d  lea     r11, [rsp+290h+var_10]
0x180004b35  mov     rbx, [r11+30h]
0x180004b39  mov     rsi, [r11+38h]
0x180004b3d  mov     rsp, r11
0x180004b40  pop     r14
0x180004b42  pop     rdi
0x180004b43  pop     rbp
0x180004b44  retn
```
