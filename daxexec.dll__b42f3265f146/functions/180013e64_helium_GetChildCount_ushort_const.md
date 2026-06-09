# helium::GetChildCount(ushort const *)

- ea: `0x180013e64`
- end: `0x180014005`
- name: `?GetChildCount@helium@@YAKPEBG@Z`
- size: `417`
- prototype: `unsigned int __fastcall(helium *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180014918`
- `0x180014a9c`

## callees

- `0x180013e64`
- `0x180014e74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f05`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ee6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013ee6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013ec2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013ec2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013ef7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013fb5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013ef7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013f22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013fb5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013f95`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013f95`

## string_xrefs

- `0x180013fde`: `onecore\base\appmodel\execmodel\desktopappx\lib\lookaside.cpp`
- `0x180013ff3`: `onecore\base\appmodel\execmodel\desktopappx\lib\lookaside.cpp`
- `0x180013eb4`: `Software\Microsoft\AppModel\Lookaside\Packages`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall helium::GetChildCount(helium *this, const unsigned __int16 *a2)
{
  unsigned int v2; // edi
  HKEY v3; // r15
  HKEY v4; // r14
  DWORD LastError; // ebx
  unsigned int v7; // eax
  DWORD v8; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  unsigned int phkResulta; // [rsp+20h] [rbp-60h]
  HKEY v11; // [rsp+68h] [rbp-18h] BYREF
  char v12; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  DWORD cSubKeys; // [rsp+B0h] [rbp+30h] BYREF
  int v15; // [rsp+B4h] [rbp+34h]
  HKEY hKey; // [rsp+B8h] [rbp+38h]

  v15 = HIDWORD(this);
  cSubKeys = 0;
  hKey = 0;
  v11 = 0;
  v12 = 1;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\AppModel\\Lookaside\\Packages", 0, 0x20019u, &v11);
  if ( v12 )
  {
    v3 = v11;
    v4 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v4);
      SetLastError(LastError);
    }
    hKey = v3;
  }
  if ( v2 == 2 )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    if ( v2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xEF,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\lookaside.cpp",
        (const char *)v2,
        phkResult);
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\lookaside.cpp",
        (const char *)v7,
        phkResulta);
    v8 = cSubKeys;
    if ( hKey )
      RegCloseKey(hKey);
    return v8;
  }
}

```

## disassembly

```asm
0x180013e64  mov     [rsp-28h+arg_10], rbx
0x180013e69  mov     qword ptr [rsp-28h+cSubKeys], rcx
0x180013e6e  push    rbp
0x180013e6f  push    rsi
0x180013e70  push    rdi
0x180013e71  push    r14
0x180013e73  push    r15
0x180013e75  mov     rbp, rsp
0x180013e78  sub     rsp, 80h
0x180013e7f  mov     [rbp+cSubKeys], 0
0x180013e86  mov     [rbp+hKey], 0
0x180013e8e  lea     rax, [rbp+hKey]
0x180013e92  mov     [rbp+var_20], rax
0x180013e96  mov     [rbp+var_18], 0
0x180013e9e  mov     [rbp+var_10], 1
0x180013ea2  lea     rax, [rbp+var_18]
0x180013ea6  mov     [rsp+80h+phkResult], rax; unsigned int
0x180013eab  mov     r9d, 20019h; samDesired
0x180013eb1  xor     r8d, r8d; ulOptions
0x180013eb4  lea     rdx, SubKey; "Software\\Microsoft\\AppModel\\Lookasid"...
0x180013ebb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013ec2  call    cs:__imp_RegOpenKeyExW
0x180013ec9  nop     dword ptr [rax+rax+00h]
0x180013ece  mov     edi, eax
0x180013ed0  cmp     [rbp+var_10], 0
0x180013ed4  jz      short loc_180013F14
0x180013ed6  mov     r15, [rbp+var_18]
0x180013eda  mov     rsi, [rbp+var_20]
0x180013ede  mov     r14, [rsi]
0x180013ee1  test    r14, r14
0x180013ee4  jz      short loc_180013F11
0x180013ee6  call    cs:__imp_GetLastError
0x180013eed  nop     dword ptr [rax+rax+00h]
0x180013ef2  mov     ebx, eax
0x180013ef4  mov     rcx, r14; hKey
0x180013ef7  call    cs:__imp_RegCloseKey
0x180013efe  nop     dword ptr [rax+rax+00h]
0x180013f03  mov     ecx, ebx; dwErrCode
0x180013f05  call    cs:__imp_SetLastError
0x180013f0c  nop     dword ptr [rax+rax+00h]
0x180013f11  mov     [rsi], r15
0x180013f14  cmp     edi, 2
0x180013f17  jnz     short loc_180013F35
0x180013f19  mov     rcx, [rbp+hKey]; hKey
0x180013f1d  test    rcx, rcx
0x180013f20  jz      short loc_180013F2E
0x180013f22  call    cs:__imp_RegCloseKey
0x180013f29  nop     dword ptr [rax+rax+00h]
0x180013f2e  xor     eax, eax
0x180013f30  jmp     loc_180013FC3
0x180013f35  mov     rcx, [rbp+28h]; this
0x180013f39  test    edi, edi
0x180013f3b  jnz     loc_180013FF0
0x180013f41  mov     [rsp+80h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180013f4a  mov     [rsp+80h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x180013f53  mov     [rsp+80h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180013f5c  mov     [rsp+80h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x180013f65  mov     [rsp+80h+lpcValues], 0; lpcValues
0x180013f6e  mov     [rsp+80h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x180013f77  mov     [rsp+80h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x180013f80  lea     rax, [rbp+cSubKeys]
0x180013f84  mov     [rsp+80h+phkResult], rax; unsigned int
0x180013f89  xor     r9d, r9d; lpReserved
0x180013f8c  xor     r8d, r8d; lpcchClass
0x180013f8f  xor     edx, edx; lpClass
0x180013f91  mov     rcx, [rbp+hKey]; hKey
0x180013f95  call    cs:__imp_RegQueryInfoKeyW
0x180013f9c  nop     dword ptr [rax+rax+00h]
0x180013fa1  mov     rcx, [rbp+28h]; this
0x180013fa5  test    eax, eax
0x180013fa7  jnz     short loc_180013FDB
0x180013fa9  mov     ebx, [rbp+cSubKeys]
0x180013fac  mov     rcx, [rbp+hKey]; hKey
0x180013fb0  test    rcx, rcx
0x180013fb3  jz      short loc_180013FC1
0x180013fb5  call    cs:__imp_RegCloseKey
0x180013fbc  nop     dword ptr [rax+rax+00h]
0x180013fc1  mov     eax, ebx
0x180013fc3  mov     rbx, [rsp+80h+arg_10]
0x180013fcb  add     rsp, 80h
0x180013fd2  pop     r15
0x180013fd4  pop     r14
0x180013fd6  pop     rdi
0x180013fd7  pop     rsi
0x180013fd8  pop     rbp
0x180013fd9  retn
0x180013fdb  mov     r9d, eax; char *
0x180013fde  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180013fe5  mov     edx, 0F0h; void *
0x180013fea  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180013ff0  mov     r9d, edi; char *
0x180013ff3  lea     r8, aOnecoreBaseApp_58; "onecore\\base\\appmodel\\execmodel\\des"...
0x180013ffa  mov     edx, 0EFh; void *
0x180013fff  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
