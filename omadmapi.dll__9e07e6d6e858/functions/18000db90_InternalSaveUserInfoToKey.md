# InternalSaveUserInfoToKey

- ea: `0x18000db90`
- end: `0x18000de09`
- name: `InternalSaveUserInfoToKey`
- size: `633`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, BYTE *lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180012e04`

## callees

- `0x180008600`
- `0x180009bf4`
- `0x18000db90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000dd30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000dda9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000dd30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000dda9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ddd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dde6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ddd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dde6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000dcfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000dcfb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dc08`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dc64`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dc08`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dc64`

## string_xrefs

- `0x18000dd8b`: `UserSID`

## pseudocode

```c
__int64 __fastcall InternalSaveUserInfoToKey(HKEY hKey, __int64 a2, const WCHAR *lpData)
{
  signed int v6; // ebx
  HKEY *phkResult; // rax
  LSTATUS v8; // eax
  bool v9; // cc
  HKEY *v10; // rax
  __int64 v11; // rdx
  const WCHAR *v12; // rax
  unsigned int v13; // edi
  HKEY v15; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKeya; // [rsp+68h] [rbp-8h] BYREF
  DWORD dwDisposition; // [rsp+A0h] [rbp+30h] BYREF
  DWORD cSubKeys; // [rsp+B8h] [rbp+48h] BYREF

  dwDisposition = 0;
  hKeya = 0;
  v15 = 0;
  if ( !hKey || !a2 )
    return (unsigned int)-2147024809;
  phkResult = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKeya);
  v8 = RegCreateKeyExW(hKey, L"UserInfo", 0, 0, 0, 0x20107u, 0, phkResult, &dwDisposition);
  v6 = v8;
  v9 = v8 <= 0;
  if ( v8 )
    goto LABEL_5;
  v10 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v15);
  v8 = RegCreateKeyExW(hKeya, lpData, 0, 0, 0, 0x20106u, 0, v10, &dwDisposition);
  v6 = v8;
  v9 = v8 <= 0;
  if ( v8 )
    goto LABEL_5;
  v6 = SaveStructInRegistry(v15, 2, a2, 8, (unsigned __int8 *)&qword_18002A538, 0x10u);
  if ( v6 >= 0 )
  {
    cSubKeys = 0;
    v8 = RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v6 = v8;
    v9 = v8 <= 0;
    if ( !v8 )
    {
      v8 = RegSetValueExW(hKey, L"CountOfUserInfo", 0, 4u, (const BYTE *)&cSubKeys, 4u);
      v6 = v8;
      v9 = v8 <= 0;
      if ( !v8 )
      {
        if ( !lpData )
        {
          v6 = -2147024809;
          goto LABEL_19;
        }
        v11 = 2147483646;
        v12 = lpData;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v11;
        }
        while ( v11 );
        v13 = v11 == 0 ? 0x80070057 : 0;
        if ( !v11
          || (v8 = RegSetValueExW(v15, L"UserSID", 0, 1u, (const BYTE *)lpData, v11 != 0 ? -4 - 2 * v11 + 2 : 2),
              v6 = v8,
              v9 = v8 <= 0,
              !v8) )
        {
          v6 = v13;
          goto LABEL_19;
        }
      }
    }
LABEL_5:
    if ( !v9 )
      v6 = (unsigned __int16)v8 | 0x80070000;
  }
LABEL_19:
  if ( v15 )
    RegCloseKey(v15);
  if ( hKeya )
    RegCloseKey(hKeya);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000db90  mov     [rsp-28h+arg_8], rbx
0x18000db95  push    rbp
0x18000db96  push    rsi
0x18000db97  push    rdi
0x18000db98  push    r14
0x18000db9a  push    r15
0x18000db9c  mov     rbp, rsp
0x18000db9f  sub     rsp, 70h
0x18000dba3  xor     r15d, r15d
0x18000dba6  mov     rsi, r8
0x18000dba9  mov     [rbp+dwDisposition], r15d
0x18000dbad  mov     rdi, rdx
0x18000dbb0  mov     [rbp+hKey], r15
0x18000dbb4  mov     r14, rcx
0x18000dbb7  mov     [rbp+var_10], r15
0x18000dbbb  test    rcx, rcx
0x18000dbbe  jnz     short loc_18000DBCA
0x18000dbc0  mov     ebx, 80070057h
0x18000dbc5  jmp     loc_18000DDF2
0x18000dbca  test    rdi, rdi
0x18000dbcd  jz      short loc_18000DBC0
0x18000dbcf  lea     rcx, [rbp+hKey]
0x18000dbd3  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000dbd8  lea     rcx, [rbp+dwDisposition]
0x18000dbdc  xor     r9d, r9d; lpClass
0x18000dbdf  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x18000dbe4  lea     rdx, aUserinfo; "UserInfo"
0x18000dbeb  mov     [rsp+70h+phkResult], rax; phkResult
0x18000dbf0  xor     r8d, r8d; Reserved
0x18000dbf3  mov     [rsp+70h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000dbf8  mov     rcx, r14; hKey
0x18000dbfb  mov     [rsp+70h+samDesired], 20107h; samDesired
0x18000dc03  mov     [rsp+70h+dwOptions], r15d; dwOptions
0x18000dc08  call    cs:__imp_RegCreateKeyExW
0x18000dc0f  nop     dword ptr [rax+rax+00h]
0x18000dc14  mov     ebx, eax
0x18000dc16  test    eax, eax
0x18000dc18  jz      short loc_18000DC2E
0x18000dc1a  jle     loc_18000DDC8
0x18000dc20  movzx   ebx, ax
0x18000dc23  or      ebx, 80070000h
0x18000dc29  jmp     loc_18000DDC8
0x18000dc2e  lea     rcx, [rbp+var_10]
0x18000dc32  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18000dc37  lea     rcx, [rbp+dwDisposition]
0x18000dc3b  xor     r9d, r9d; lpClass
0x18000dc3e  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x18000dc43  xor     r8d, r8d; Reserved
0x18000dc46  mov     rcx, [rbp+hKey]; hKey
0x18000dc4a  mov     rdx, rsi; lpSubKey
0x18000dc4d  mov     [rsp+70h+phkResult], rax; phkResult
0x18000dc52  mov     [rsp+70h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000dc57  mov     [rsp+70h+samDesired], 20106h; samDesired
0x18000dc5f  mov     [rsp+70h+dwOptions], r15d; dwOptions
0x18000dc64  call    cs:__imp_RegCreateKeyExW
0x18000dc6b  nop     dword ptr [rax+rax+00h]
0x18000dc70  mov     ebx, eax
0x18000dc72  test    eax, eax
0x18000dc74  jnz     short loc_18000DC1A
0x18000dc76  mov     r8d, [rdi]
0x18000dc79  lea     rax, qword_18002A538
0x18000dc80  mov     rcx, [rbp+var_10]; hKey
0x18000dc84  lea     r9, off_180025C60; "AADTokenNeedsUserInteraction"
0x18000dc8b  mov     dword ptr [rsp+70h+lpdwDisposition], 10h; unsigned int
0x18000dc93  lea     edx, [rbx+1]
0x18000dc96  mov     [rsp+70h+phkResult], rax; unsigned __int8 *
0x18000dc9b  mov     dword ptr [rsp+70h+lpSecurityAttributes], 8; int
0x18000dca3  mov     qword ptr [rsp+70h+samDesired], rdi; __int64
0x18000dca8  mov     [rsp+70h+dwOptions], 2; int
0x18000dcb0  call    SaveStructInRegistry
0x18000dcb5  mov     ebx, eax
0x18000dcb7  test    eax, eax
0x18000dcb9  js      loc_18000DDC8
0x18000dcbf  mov     rcx, [rbp+hKey]; hKey
0x18000dcc3  lea     rax, [rbp+cSubKeys]
0x18000dcc7  mov     [rsp+70h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000dccc  xor     r9d, r9d; lpReserved
0x18000dccf  mov     [rsp+70h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000dcd4  xor     r8d, r8d; lpcchClass
0x18000dcd7  mov     [rsp+70h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000dcdc  xor     edx, edx; lpClass
0x18000dcde  mov     [rsp+70h+lpdwDisposition], r15; lpcbMaxValueNameLen
0x18000dce3  mov     [rsp+70h+phkResult], r15; lpcValues
0x18000dce8  mov     [rsp+70h+lpSecurityAttributes], r15; lpcbMaxClassLen
0x18000dced  mov     qword ptr [rsp+70h+samDesired], r15; lpcbMaxSubKeyLen
0x18000dcf2  mov     qword ptr [rsp+70h+dwOptions], rax; lpcSubKeys
0x18000dcf7  mov     [rbp+cSubKeys], r15d
0x18000dcfb  call    cs:__imp_RegQueryInfoKeyW
0x18000dd02  nop     dword ptr [rax+rax+00h]
0x18000dd07  mov     ebx, eax
0x18000dd09  test    eax, eax
0x18000dd0b  jnz     loc_18000DC1A
0x18000dd11  lea     r9d, [rax+4]; dwType
0x18000dd15  xor     r8d, r8d; Reserved
0x18000dd18  lea     rax, [rbp+cSubKeys]
0x18000dd1c  mov     [rsp+70h+samDesired], r9d; cbData
0x18000dd21  lea     rdx, aCountofuserinf; "CountOfUserInfo"
0x18000dd28  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18000dd2d  mov     rcx, r14; hKey
0x18000dd30  call    cs:__imp_RegSetValueExW
0x18000dd37  nop     dword ptr [rax+rax+00h]
0x18000dd3c  mov     ebx, eax
0x18000dd3e  test    eax, eax
0x18000dd40  jnz     loc_18000DC1A
0x18000dd46  test    rsi, rsi
0x18000dd49  jz      short loc_18000DDC3
0x18000dd4b  mov     edx, 7FFFFFFEh
0x18000dd50  mov     rax, rsi
0x18000dd53  cmp     [rax], r15w
0x18000dd57  jz      short loc_18000DD63
0x18000dd59  add     rax, 2
0x18000dd5d  sub     rdx, 1
0x18000dd61  jnz     short loc_18000DD53
0x18000dd63  mov     rax, rdx
0x18000dd66  neg     rax
0x18000dd69  sbb     edi, edi
0x18000dd6b  not     edi
0x18000dd6d  and     edi, 80070057h
0x18000dd73  test    rdx, rdx
0x18000dd76  jz      short loc_18000DDBF
0x18000dd78  lea     eax, [rdx+rdx]
0x18000dd7b  mov     ecx, 0FFFFFFFCh
0x18000dd80  sub     ecx, eax
0x18000dd82  mov     r9d, 1; dwType
0x18000dd88  neg     rdx
0x18000dd8b  lea     rdx, aUsersid; "UserSID"
0x18000dd92  sbb     eax, eax
0x18000dd94  xor     r8d, r8d; Reserved
0x18000dd97  and     eax, ecx
0x18000dd99  mov     rcx, [rbp+var_10]; hKey
0x18000dd9d  add     eax, 2
0x18000dda0  mov     [rsp+70h+samDesired], eax; cbData
0x18000dda4  mov     qword ptr [rsp+70h+dwOptions], rsi; lpData
0x18000dda9  call    cs:__imp_RegSetValueExW
0x18000ddb0  nop     dword ptr [rax+rax+00h]
0x18000ddb5  mov     ebx, eax
0x18000ddb7  test    eax, eax
0x18000ddb9  jnz     loc_18000DC1A
0x18000ddbf  mov     ebx, edi
0x18000ddc1  jmp     short loc_18000DDC8
0x18000ddc3  mov     ebx, 80070057h
0x18000ddc8  mov     rcx, [rbp+var_10]; hKey
0x18000ddcc  test    rcx, rcx
0x18000ddcf  jz      short loc_18000DDDD
0x18000ddd1  call    cs:__imp_RegCloseKey
0x18000ddd8  nop     dword ptr [rax+rax+00h]
0x18000dddd  mov     rcx, [rbp+hKey]; hKey
0x18000dde1  test    rcx, rcx
0x18000dde4  jz      short loc_18000DDF2
0x18000dde6  call    cs:__imp_RegCloseKey
0x18000dded  nop     dword ptr [rax+rax+00h]
0x18000ddf2  mov     eax, ebx
0x18000ddf4  mov     rbx, [rsp+70h+arg_8]
0x18000ddfc  add     rsp, 70h
0x18000de00  pop     r15
0x18000de02  pop     r14
0x18000de04  pop     rdi
0x18000de05  pop     rsi
0x18000de06  pop     rbp
0x18000de07  retn
```
