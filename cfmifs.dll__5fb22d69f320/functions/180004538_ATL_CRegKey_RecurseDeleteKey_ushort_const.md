# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180004538`
- end: `0x18000467f`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `327`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004538`
- `0x1800049dc`

## callees

- `0x180003d68`
- `0x180004538`
- `0x180006030`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000461a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000461a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004599`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004599`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800045b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000462e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004650`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800045b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000462e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004650`

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
0x180004538  mov     [rsp-8+arg_10], rbx
0x18000453d  mov     [rsp-8+arg_18], rsi
0x180004542  push    rbp
0x180004543  push    rdi
0x180004544  push    r14
0x180004546  lea     rbp, [rsp-180h]
0x18000454e  sub     rsp, 280h
0x180004555  mov     rax, cs:__security_cookie
0x18000455c  xor     rax, rsp
0x18000455f  mov     [rbp+190h+var_20], rax
0x180004566  xor     r14d, r14d
0x180004569  lea     rax, [rsp+290h+var_230]
0x18000456e  mov     rdi, rcx
0x180004571  mov     [rsp+290h+hKey], r14
0x180004576  mov     rcx, [rcx]; hKey
0x180004579  mov     r9d, 2001Fh; samDesired
0x18000457f  xor     r8d, r8d; ulOptions
0x180004582  mov     [rsp+290h+var_240], r14
0x180004587  mov     [rsp+290h+var_238], r14
0x18000458c  mov     rsi, rdx
0x18000458f  mov     [rsp+290h+var_230], r14
0x180004594  mov     [rsp+290h+phkResult], rax; phkResult
0x180004599  call    cs:__imp_RegOpenKeyExW
0x18000459f  mov     rcx, [rsp+290h+hKey]; hKey
0x1800045a4  mov     ebx, eax
0x1800045a6  test    eax, eax
0x1800045a8  jnz     loc_18000464B
0x1800045ae  mov     ebx, r14d
0x1800045b1  test    rcx, rcx
0x1800045b4  jz      short loc_1800045BE
0x1800045b6  call    cs:__imp_RegCloseKey
0x1800045bc  mov     ebx, eax
0x1800045be  mov     rcx, [rsp+290h+var_230]
0x1800045c3  mov     [rsp+290h+hKey], rcx
0x1800045c8  test    ebx, ebx
0x1800045ca  jnz     short loc_18000464B
0x1800045cc  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x1800045d1  jmp     short loc_1800045ED
0x1800045d3  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x1800045d8  lea     rcx, [rsp+290h+hKey]; this
0x1800045dd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800045e2  mov     rcx, [rsp+290h+hKey]; hKey
0x1800045e7  mov     ebx, eax
0x1800045e9  test    eax, eax
0x1800045eb  jnz     short loc_18000464B
0x1800045ed  lea     rax, [rsp+290h+ftLastWriteTime]
0x1800045f2  mov     [rsp+290h+cchName], 100h
0x1800045fa  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800045ff  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004604  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180004609  lea     r8, [rsp+290h+Name]; lpName
0x18000460e  mov     [rsp+290h+lpClass], r14; lpClass
0x180004613  xor     edx, edx; dwIndex
0x180004615  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000461a  call    cs:__imp_RegEnumKeyExW
0x180004620  test    eax, eax
0x180004622  jz      short loc_1800045D3
0x180004624  mov     rcx, [rsp+290h+hKey]; hKey
0x180004629  test    rcx, rcx
0x18000462c  jz      short loc_180004639
0x18000462e  call    cs:__imp_RegCloseKey
0x180004634  mov     [rsp+290h+hKey], r14
0x180004639  mov     rdx, rsi; unsigned __int16 *
0x18000463c  mov     rcx, rdi; this
0x18000463f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004644  mov     rcx, [rsp+290h+hKey]; hKey
0x180004649  mov     ebx, eax
0x18000464b  test    rcx, rcx
0x18000464e  jz      short loc_180004656
0x180004650  call    cs:__imp_RegCloseKey
0x180004656  mov     eax, ebx
0x180004658  mov     rcx, [rbp+190h+var_20]
0x18000465f  xor     rcx, rsp; StackCookie
0x180004662  call    __security_check_cookie
0x180004667  lea     r11, [rsp+290h+var_10]
0x18000466f  mov     rbx, [r11+30h]
0x180004673  mov     rsi, [r11+38h]
0x180004677  mov     rsp, r11
0x18000467a  pop     r14
0x18000467c  pop     rdi
0x18000467d  pop     rbp
0x18000467e  retn
```
