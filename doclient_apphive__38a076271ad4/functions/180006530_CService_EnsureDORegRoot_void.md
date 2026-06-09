# CService::_EnsureDORegRoot(void)

- ea: `0x180006530`
- end: `0x1800066a9`
- name: `?_EnsureDORegRoot@CService@@AEAAJXZ`
- size: `377`
- prototype: `__int64 __fastcall(CService *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000516c`

## callees

- `0x180006530`
- `0x18009b290`
- `0x18009bc68`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065f8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800065f8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800065b0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800065b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000667b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800065f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000667b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180006646`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180006646`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x18000666a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x18000666a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CService::_EnsureDORegRoot(CService *this)
{
  struct CPersistenceLocation *v1; // rax
  const CHAR *v2; // rbx
  struct CPersistenceLocation *v3; // rax
  LSTATUS v4; // eax
  const char *v5; // r9
  signed int fixed; // ebx
  HKEY v7; // rdi
  DWORD LastError; // ebx
  struct CPersistenceLocation *v9; // rax
  const CHAR *v10; // rbx
  struct CPersistenceLocation *v11; // rax
  LSTATUS v12; // eax
  __int64 result; // rax
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    hKey = 0;
    v1 = CPersistenceLocation::Instance();
    v2 = (const CHAR *)v1;
    if ( *((_QWORD *)v1 + 3) > 0xFu )
      v2 = *(const CHAR **)v1;
    v3 = CPersistenceLocation::Instance();
    v4 = RegCreateKeyExA((HKEY)(-(__int64)(*((_BYTE *)v3 + 160) != 0) - 2147483645), v2, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    fixed = (unsigned __int16)v4 | 0x80070000;
    if ( v4 <= 0 )
      fixed = v4;
    if ( fixed < 0 )
    {
      fixed = CPersistenceLocation::FixRegistryPermissions();
      if ( fixed >= 0 )
      {
        v7 = hKey;
        if ( hKey )
        {
          LastError = GetLastError();
          RegCloseKey(v7);
          SetLastError(LastError);
        }
        hKey = 0;
        v9 = CPersistenceLocation::Instance();
        v10 = (const CHAR *)v9;
        if ( *((_QWORD *)v9 + 3) > 0xFu )
          v10 = *(const CHAR **)v9;
        v11 = CPersistenceLocation::Instance();
        v12 = RegOpenKeyExA((HKEY)(-(__int64)(*((_BYTE *)v11 + 160) != 0) - 2147483645), v10, 0, 0x2001Fu, &hKey);
        fixed = (unsigned __int16)v12 | 0x80070000;
        if ( v12 <= 0 )
          fixed = v12;
        if ( fixed >= 0 )
          RegDeleteValueA(hKey, "Migrated");
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    result = (unsigned int)fixed;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x16D,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
                           v5);
  }
  return result;
}

```

## disassembly

```asm
0x180006530  mov     [rsp+arg_0], rbx
0x180006535  push    rdi
0x180006536  sub     rsp, 60h
0x18000653a  mov     rax, cs:__security_cookie
0x180006541  xor     rax, rsp
0x180006544  mov     [rsp+68h+var_10], rax
0x180006549  mov     [rsp+68h+hKey], 0
0x180006552  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x180006557  mov     rbx, rax
0x18000655a  cmp     qword ptr [rax+18h], 0Fh
0x18000655f  jbe     short loc_180006564
0x180006561  mov     rbx, [rax]
0x180006564  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x180006569  mov     al, [rax+0A0h]
0x18000656f  neg     al
0x180006571  sbb     rcx, rcx
0x180006574  add     rcx, 0FFFFFFFF80000003h; hKey
0x18000657b  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180006584  lea     rax, [rsp+68h+hKey]
0x180006589  mov     [rsp+68h+phkResult], rax; phkResult
0x18000658e  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180006597  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x18000659f  mov     [rsp+68h+dwOptions], 0; dwOptions
0x1800065a7  xor     r9d, r9d; lpClass
0x1800065aa  xor     r8d, r8d; Reserved
0x1800065ad  mov     rdx, rbx; lpSubKey
0x1800065b0  call    cs:__imp_RegCreateKeyExA
0x1800065b6  movzx   ebx, ax
0x1800065b9  or      ebx, 80070000h
0x1800065bf  test    eax, eax
0x1800065c1  cmovle  ebx, eax
0x1800065c4  test    ebx, ebx
0x1800065c6  jns     loc_180006671
0x1800065cc  call    ?FixRegistryPermissions@CPersistenceLocation@@SAJXZ; CPersistenceLocation::FixRegistryPermissions(void)
0x1800065d1  mov     ebx, eax
0x1800065d3  test    eax, eax
0x1800065d5  js      loc_180006671
0x1800065db  mov     rdi, [rsp+68h+hKey]
0x1800065e0  test    rdi, rdi
0x1800065e3  jz      short loc_1800065FE
0x1800065e5  call    cs:__imp_GetLastError
0x1800065eb  mov     ebx, eax
0x1800065ed  mov     rcx, rdi; hKey
0x1800065f0  call    cs:__imp_RegCloseKey
0x1800065f6  mov     ecx, ebx; dwErrCode
0x1800065f8  call    cs:__imp_SetLastError
0x1800065fe  mov     [rsp+68h+hKey], 0
0x180006607  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18000660c  mov     rbx, rax
0x18000660f  cmp     qword ptr [rax+18h], 0Fh
0x180006614  jbe     short loc_180006619
0x180006616  mov     rbx, [rax]
0x180006619  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x18000661e  mov     al, [rax+0A0h]
0x180006624  neg     al
0x180006626  sbb     rcx, rcx
0x180006629  add     rcx, 0FFFFFFFF80000003h; hKey
0x180006630  lea     rax, [rsp+68h+hKey]
0x180006635  mov     qword ptr [rsp+68h+dwOptions], rax; phkResult
0x18000663a  mov     r9d, 2001Fh; samDesired
0x180006640  xor     r8d, r8d; ulOptions
0x180006643  mov     rdx, rbx; lpSubKey
0x180006646  call    cs:__imp_RegOpenKeyExA
0x18000664c  movzx   ebx, ax
0x18000664f  or      ebx, 80070000h
0x180006655  test    eax, eax
0x180006657  cmovle  ebx, eax
0x18000665a  test    ebx, ebx
0x18000665c  js      short loc_180006671
0x18000665e  lea     rdx, ValueName; "Migrated"
0x180006665  mov     rcx, [rsp+68h+hKey]; hKey
0x18000666a  call    cs:__imp_RegDeleteValueA
0x180006670  nop
0x180006671  mov     rcx, [rsp+68h+hKey]; hKey
0x180006676  test    rcx, rcx
0x180006679  jz      short loc_180006681
0x18000667b  call    cs:__imp_RegCloseKey
0x180006681  mov     eax, ebx
0x180006683  jmp     short loc_180006690
0x180006685  mov     eax, 8007000Eh
0x18000668a  jmp     short loc_180006690
0x18000668c  mov     eax, dword ptr [rsp+68h+hKey]
0x180006690  mov     rcx, [rsp+68h+var_10]
0x180006695  xor     rcx, rsp; StackCookie
0x180006698  call    __security_check_cookie
0x18000669d  mov     rbx, [rsp+68h+arg_0]
0x1800066a2  add     rsp, 60h
0x1800066a6  pop     rdi
0x1800066a7  retn
```
