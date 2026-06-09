# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180011608`
- end: `0x18001174f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011608`
- `0x180011ac8`

## callees

- `0x1800024e0`
- `0x18000faf8`
- `0x180011608`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011669`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011720`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011686`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800116fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011720`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800116ea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800116ea`

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
0x180011608  mov     [rsp-8+arg_10], rbx
0x18001160d  mov     [rsp-8+arg_18], rsi
0x180011612  push    rbp
0x180011613  push    rdi
0x180011614  push    r14
0x180011616  lea     rbp, [rsp-180h]
0x18001161e  sub     rsp, 280h
0x180011625  mov     rax, cs:__security_cookie
0x18001162c  xor     rax, rsp
0x18001162f  mov     [rbp+190h+var_20], rax
0x180011636  xor     r14d, r14d
0x180011639  lea     rax, [rsp+290h+var_230]
0x18001163e  mov     rdi, rcx
0x180011641  mov     [rsp+290h+hKey], r14
0x180011646  mov     rcx, [rcx]; hKey
0x180011649  mov     r9d, 2001Fh; samDesired
0x18001164f  xor     r8d, r8d; ulOptions
0x180011652  mov     [rsp+290h+var_240], r14
0x180011657  mov     [rsp+290h+var_238], r14
0x18001165c  mov     rsi, rdx
0x18001165f  mov     [rsp+290h+var_230], r14
0x180011664  mov     [rsp+290h+phkResult], rax; phkResult
0x180011669  call    cs:__imp_RegOpenKeyExW
0x18001166f  mov     rcx, [rsp+290h+hKey]; hKey
0x180011674  mov     ebx, eax
0x180011676  test    eax, eax
0x180011678  jnz     loc_18001171B
0x18001167e  mov     ebx, r14d
0x180011681  test    rcx, rcx
0x180011684  jz      short loc_18001168E
0x180011686  call    cs:__imp_RegCloseKey
0x18001168c  mov     ebx, eax
0x18001168e  mov     rcx, [rsp+290h+var_230]
0x180011693  mov     [rsp+290h+hKey], rcx
0x180011698  test    ebx, ebx
0x18001169a  jnz     short loc_18001171B
0x18001169c  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800116a1  jmp     short loc_1800116BD
0x1800116a3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800116a8  lea     rcx, [rsp+290h+hKey]; this
0x1800116ad  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800116b2  mov     rcx, [rsp+290h+hKey]; hKey
0x1800116b7  mov     ebx, eax
0x1800116b9  test    eax, eax
0x1800116bb  jnz     short loc_18001171B
0x1800116bd  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800116c2  mov     [rsp+290h+cchName], 100h
0x1800116ca  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800116cf  lea     r9, [rsp+290h+cchName]; lpcchName
0x1800116d4  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1800116d9  lea     r8, [rsp+290h+Name]; lpName
0x1800116de  mov     [rsp+290h+lpClass], r14; lpClass
0x1800116e3  xor     edx, edx; dwIndex
0x1800116e5  mov     [rsp+290h+phkResult], r14; lpReserved
0x1800116ea  call    cs:__imp_RegEnumKeyExW
0x1800116f0  test    eax, eax
0x1800116f2  jz      short loc_1800116A3
0x1800116f4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800116f9  test    rcx, rcx
0x1800116fc  jz      short loc_180011709
0x1800116fe  call    cs:__imp_RegCloseKey
0x180011704  mov     [rsp+290h+hKey], r14
0x180011709  mov     rdx, rsi; unsigned __int16 *
0x18001170c  mov     rcx, rdi; this
0x18001170f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180011714  mov     rcx, [rsp+290h+hKey]; hKey
0x180011719  mov     ebx, eax
0x18001171b  test    rcx, rcx
0x18001171e  jz      short loc_180011726
0x180011720  call    cs:__imp_RegCloseKey
0x180011726  mov     eax, ebx
0x180011728  mov     rcx, [rbp+190h+var_20]
0x18001172f  xor     rcx, rsp; StackCookie
0x180011732  call    __security_check_cookie
0x180011737  lea     r11, [rsp+290h+var_10]
0x18001173f  mov     rbx, [r11+30h]
0x180011743  mov     rsi, [r11+38h]
0x180011747  mov     rsp, r11
0x18001174a  pop     r14
0x18001174c  pop     rdi
0x18001174d  pop     rbp
0x18001174e  retn
```
