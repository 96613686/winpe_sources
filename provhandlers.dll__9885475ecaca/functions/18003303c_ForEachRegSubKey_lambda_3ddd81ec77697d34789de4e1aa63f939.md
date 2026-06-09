# ForEachRegSubKey__lambda_3ddd81ec77697d34789de4e1aa63f939_

- ea: `0x18003303c`
- end: `0x18003329d`
- name: `ForEachRegSubKey__lambda_3ddd81ec77697d34789de4e1aa63f939___`
- size: `609`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180035c34`

## callees

- `0x180012390`
- `0x180012d80`
- `0x180032f9c`
- `0x18003303c`
- `0x18003368c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180033228`
- `msvcrt!??3@YAXPEAX@Z` at `0x180033228`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800331c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800331c5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800331d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800331d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800331d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800331fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003320d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800331d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800331fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003320d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800331ed`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800331ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800330a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800330a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003315e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033191`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003315e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180033191`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003312f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003312f`

## string_xrefs

- `0x180033264`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x180033279`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`
- `0x18003328b`: `onecoreuap\internal\admin\inc\private\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ForEachRegSubKey__lambda_3ddd81ec77697d34789de4e1aa63f939_(HKEY hKey)
{
  unsigned int v2; // eax
  DWORD v3; // edx
  DWORD v4; // eax
  DWORD v5; // r8d
  const char *v6; // r9
  DWORD i; // esi
  unsigned int v8; // eax
  unsigned int v9; // eax
  HKEY v10; // r15
  DWORD LastError; // edi
  unsigned int lpcSubKeys; // [rsp+28h] [rbp-59h]
  unsigned int lpcSubKeysa; // [rsp+28h] [rbp-59h]
  unsigned int lpcSubKeysb; // [rsp+28h] [rbp-59h]
  DWORD cchName; // [rsp+68h] [rbp-19h] BYREF
  HKEY hKeya; // [rsp+70h] [rbp-11h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-9h] BYREF
  LPWSTR lpName[2]; // [rsp+80h] [rbp-1h] BYREF
  __int64 v20; // [rsp+90h] [rbp+Fh]
  HKEY *p_hKeya; // [rsp+98h] [rbp+17h]
  HKEY *p_phkResult; // [rsp+A0h] [rbp+1Fh]
  char v23; // [rsp+A8h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  DWORD cbMaxSubKeyLen; // [rsp+F8h] [rbp+77h] BYREF
  DWORD cSubKeys; // [rsp+100h] [rbp+7Fh] BYREF

  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v2 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      (const char *)v2,
      lpcSubKeys);
  v3 = cbMaxSubKeyLen;
  v4 = cbMaxSubKeyLen + 1;
  v5 = -1;
  if ( cbMaxSubKeyLen + 1 >= cbMaxSubKeyLen )
    v5 = cbMaxSubKeyLen + 1;
  v6 = v4 < cbMaxSubKeyLen ? (const char *)0x80070216LL : 0LL;
  cbMaxSubKeyLen = v5;
  if ( v4 < v3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
      v6,
      lpcSubKeys);
  *(_OWORD *)lpName = 0;
  v20 = 0;
  if ( v5 )
    std::vector<unsigned short>::_Reallocate((__int64)lpName, v5);
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = cbMaxSubKeyLen;
    v8 = RegEnumKeyExW(hKey, i, lpName[0], &cchName, 0, 0, 0, 0);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x4C,
        (unsigned int)"onecoreuap\\internal\\admin\\inc\\private\\RegistryUtils.h",
        (const char *)v8,
        lpcSubKeysa);
    phkResult = 0;
    v9 = RegOpenKeyExW(hKey, lpName[0], 0, 0x10009u, &phkResult);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xA8,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v9,
        lpcSubKeysb);
    hKeya = 0;
    if ( !RegOpenKeyExW(phkResult, L"Undo", 0, 1u, &hKeya) )
    {
      p_hKeya = &hKeya;
      p_phkResult = &phkResult;
      v23 = 1;
      ForEachRegValue__lambda_c0bb054420732f7ad70536e56c3edab6_(hKeya);
      v10 = hKeya;
      if ( hKeya )
      {
        LastError = GetLastError();
        RegCloseKey(v10);
        SetLastError(LastError);
      }
      hKeya = 0;
      RegDeleteTreeW(phkResult, L"Undo");
    }
    if ( hKeya )
      RegCloseKey(hKeya);
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( lpName[0] )
    operator delete(lpName[0]);
  return i;
}

```

## disassembly

```asm
0x18003303c  mov     rax, rsp
0x18003303f  mov     [rax+8], rbx
0x180033043  mov     [rax+10h], rsi
0x180033047  push    rbp
0x180033048  push    rdi
0x180033049  push    r12
0x18003304b  push    r13
0x18003304d  push    r15
0x18003304f  lea     rbp, [rax-5Fh]
0x180033053  sub     rsp, 0B0h
0x18003305a  mov     rbx, rdx
0x18003305d  mov     r12, rcx
0x180033060  xor     r13d, r13d
0x180033063  mov     [rbp+57h+cSubKeys], r13d
0x180033067  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18003306b  mov     [rax-80h], r13
0x18003306f  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180033074  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180033079  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18003307e  mov     [rsp+0D0h+lpcValues], r13; lpcValues
0x180033083  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180033088  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18003308c  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180033091  lea     rax, [rbp+57h+cSubKeys]
0x180033095  mov     [rsp+0D0h+lpcSubKeys], rax; int
0x18003309a  xor     r9d, r9d; lpReserved
0x18003309d  xor     r8d, r8d; lpcchClass
0x1800330a0  xor     edx, edx; lpClass
0x1800330a2  call    cs:__imp_RegQueryInfoKeyW
0x1800330a8  mov     rcx, [rbp+5Fh]; this
0x1800330ac  test    eax, eax
0x1800330ae  jnz     loc_180033276
0x1800330b4  mov     edx, [rbp+57h+cbMaxSubKeyLen]
0x1800330b7  lea     eax, [rdx+1]
0x1800330ba  or      r8d, 0FFFFFFFFh
0x1800330be  cmp     eax, edx
0x1800330c0  cmovnb  r8d, eax
0x1800330c4  sbb     r9d, r9d
0x1800330c7  and     r9d, 80070216h; char *
0x1800330ce  mov     [rbp+57h+cbMaxSubKeyLen], r8d
0x1800330d2  mov     rcx, [rbp+5Fh]; this
0x1800330d6  cmp     eax, edx
0x1800330d8  jb      loc_18003328B
0x1800330de  xorps   xmm0, xmm0
0x1800330e1  movdqu  xmmword ptr [rbp+57h+lpName], xmm0
0x1800330e6  mov     [rbp+57h+var_48], r13
0x1800330ea  mov     edx, r8d
0x1800330ed  test    r8d, r8d
0x1800330f0  jz      short loc_1800330FB
0x1800330f2  lea     rcx, [rbp+57h+lpName]
0x1800330f6  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x1800330fb  mov     esi, r13d
0x1800330fe  cmp     [rbp+57h+cSubKeys], r13d
0x180033102  jbe     loc_18003321E
0x180033108  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18003310b  mov     [rbp+57h+cchName], eax
0x18003310e  mov     [rsp+0D0h+lpcValues], r13; lpftLastWriteTime
0x180033113  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcchClass
0x180033118  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpClass
0x18003311d  mov     [rsp+0D0h+lpcSubKeys], r13; unsigned int
0x180033122  lea     r9, [rbp+57h+cchName]; lpcchName
0x180033126  mov     r8, [rbp+57h+lpName]; lpName
0x18003312a  mov     edx, esi; dwIndex
0x18003312c  mov     rcx, r12; hKey
0x18003312f  call    cs:__imp_RegEnumKeyExW
0x180033135  mov     rcx, [rbp+5Fh]; this
0x180033139  test    eax, eax
0x18003313b  jnz     loc_180033261
0x180033141  mov     [rbp+57h+phkResult], r13
0x180033145  lea     rax, [rbp+57h+phkResult]
0x180033149  mov     [rsp+0D0h+lpcSubKeys], rax; unsigned int
0x18003314e  mov     r9d, 10009h; samDesired
0x180033154  xor     r8d, r8d; ulOptions
0x180033157  mov     rdx, [rbp+57h+lpName]; lpSubKey
0x18003315b  mov     rcx, r12; hKey
0x18003315e  call    cs:__imp_RegOpenKeyExW
0x180033164  mov     rcx, [rbp+5Fh]; this
0x180033168  test    eax, eax
0x18003316a  jnz     loc_18003324C
0x180033170  mov     [rbp+57h+hKey], r13
0x180033174  lea     rax, [rbp+57h+hKey]
0x180033178  mov     [rsp+0D0h+lpcSubKeys], rax; phkResult
0x18003317d  mov     r9d, 1; samDesired
0x180033183  xor     r8d, r8d; ulOptions
0x180033186  lea     rdx, ?gc_wszUndo@@3QBGB; "Undo"
0x18003318d  mov     rcx, [rbp+57h+phkResult]; hKey
0x180033191  call    cs:__imp_RegOpenKeyExW
0x180033197  test    eax, eax
0x180033199  jnz     short loc_1800331F4
0x18003319b  lea     rax, [rbp+57h+hKey]
0x18003319f  mov     [rbp+57h+var_40], rax
0x1800331a3  lea     rax, [rbp+57h+phkResult]
0x1800331a7  mov     [rbp+57h+var_38], rax
0x1800331ab  mov     [rbp+57h+var_30], 1
0x1800331af  mov     rdx, rbx
0x1800331b2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800331b6  call    ForEachRegValue__lambda_c0bb054420732f7ad70536e56c3edab6___; ForEachRegValue__lambda_c0bb054420732f7ad70536e56c3edab6_
0x1800331bb  nop
0x1800331bc  mov     r15, [rbp+57h+hKey]
0x1800331c0  test    r15, r15
0x1800331c3  jz      short loc_1800331DE
0x1800331c5  call    cs:__imp_GetLastError
0x1800331cb  mov     edi, eax
0x1800331cd  mov     rcx, r15; hKey
0x1800331d0  call    cs:__imp_RegCloseKey
0x1800331d6  mov     ecx, edi; dwErrCode
0x1800331d8  call    cs:__imp_SetLastError
0x1800331de  mov     [rbp+57h+hKey], r13
0x1800331e2  lea     rdx, ?gc_wszUndo@@3QBGB; "Undo"
0x1800331e9  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800331ed  call    cs:__imp_RegDeleteTreeW
0x1800331f3  nop
0x1800331f4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800331f8  test    rcx, rcx
0x1800331fb  jz      short loc_180033204
0x1800331fd  call    cs:__imp_RegCloseKey
0x180033203  nop
0x180033204  mov     rcx, [rbp+57h+phkResult]; hKey
0x180033208  test    rcx, rcx
0x18003320b  jz      short loc_180033213
0x18003320d  call    cs:__imp_RegCloseKey
0x180033213  inc     esi
0x180033215  cmp     esi, [rbp+57h+cSubKeys]
0x180033218  jb      loc_180033108
0x18003321e  cmp     [rbp+57h+lpName], r13
0x180033222  jz      short loc_18003322E
0x180033224  mov     rcx, [rbp+57h+lpName]
0x180033228  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003322e  mov     eax, esi
0x180033230  lea     r11, [rsp+0D0h+var_20]
0x180033238  mov     rbx, [r11+30h]
0x18003323c  mov     rsi, [r11+38h]
0x180033240  mov     rsp, r11
0x180033243  pop     r15
0x180033245  pop     r13
0x180033247  pop     r12
0x180033249  pop     rdi
0x18003324a  pop     rbp
0x18003324b  retn
0x18003324c  mov     r9d, eax; char *
0x18003324f  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180033256  mov     edx, 0A8h; void *
0x18003325b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180033261  mov     r9d, eax; char *
0x180033264  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x18003326b  mov     edx, 4Ch ; 'L'; void *
0x180033270  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180033276  mov     r9d, eax; char *
0x180033279  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180033280  mov     edx, 40h ; '@'; void *
0x180033285  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003328b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180033292  mov     edx, 43h ; 'C'; void *
0x180033297  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
