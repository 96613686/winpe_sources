# RegistryOwnershipManager::TakeOwnershipOfSingleKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180116108`
- end: `0x180116400`
- name: `?TakeOwnershipOfSingleKey@RegistryOwnershipManager@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180116408`

## callees

- `0x180005704`
- `0x18000dad8`
- `0x180116108`
- `0x1801b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801161d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801162df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801161d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801162df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801161f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801162ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801161f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801162ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801162f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011633a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801163a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801163bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180116185`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801161e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801163d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180116185`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801161e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801163d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180116152`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180116229`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180116152`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180116229`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801161b8`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18011636d`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801161b8`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18011636d`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1801162ba`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1801162ba`

## string_xrefs

- `0x18011616e`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x18011631a`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`
- `0x180116384`: `onecore\base\flighting\featuremanagement\libs\inc\RegSecurity.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryOwnershipManager::TakeOwnershipOfSingleKey(__int64 a1, const WCHAR *a2)
{
  const WCHAR *v2; // rdi
  DWORD v4; // eax
  __int64 v5; // rdx
  unsigned int v6; // ebx
  HKEY v8; // r14
  DWORD LastError; // ebx
  DWORD v10; // r14d
  struct _ACL *v11; // r15
  PACL v12; // rsi
  DWORD v13; // ebx
  DWORD v14; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-69h]
  unsigned int phkResulta; // [rsp+20h] [rbp-69h]
  PACL NewAcl; // [rsp+48h] [rbp-41h] BYREF
  char v18; // [rsp+50h] [rbp-39h]
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+60h] [rbp-29h] BYREF
  int v20; // [rsp+90h] [rbp+7h]
  int v21; // [rsp+94h] [rbp+Bh]
  int v22; // [rsp+98h] [rbp+Fh]
  int v23; // [rsp+ACh] [rbp+23h]
  int v24; // [rsp+B0h] [rbp+27h]
  __int64 v25; // [rsp+B8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  HKEY hKey; // [rsp+F0h] [rbp+67h] BYREF
  PACL pDacl; // [rsp+F8h] [rbp+6Fh]

  v2 = a2;
  hKey = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v4 = RegOpenKeyExW(*(HKEY *)a1, a2, 0, 0x80000u, &hKey);
  if ( v4 )
  {
    v5 = 158;
LABEL_5:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v5,
           (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
           (const char *)v4,
           phkResult);
LABEL_6:
    if ( hKey )
      RegCloseKey(hKey);
    return v6;
  }
  v4 = SetSecurityInfo(hKey, SE_REGISTRY_KEY, 1u, *(PSID *)(a1 + 40), 0, 0, 0);
  if ( v4 )
  {
    v5 = 161;
    goto LABEL_5;
  }
  v8 = hKey;
  if ( hKey )
  {
    LastError = GetLastError();
    RegCloseKey(v8);
    SetLastError(LastError);
  }
  hKey = 0;
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(const WCHAR **)v2;
  v4 = RegOpenKeyExW(*(HKEY *)a1, v2, 0, 0x40000u, &hKey);
  if ( v4 )
  {
    v5 = 164;
    goto LABEL_5;
  }
  memset_0(&pListOfExplicitEntries, 0, 0x60u);
  pListOfExplicitEntries.grfAccessPermissions = 983103;
  pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_GROUP;
  pListOfExplicitEntries.Trustee.ptstrName = *(LPWCH *)(a1 + 40);
  v20 = 983103;
  v21 = 2;
  v22 = 3;
  v23 = 0;
  v24 = 5;
  v25 = *(_QWORD *)(a1 + 48);
  pDacl = 0;
  NewAcl = 0;
  v18 = 1;
  v10 = SetEntriesInAclW(2u, &pListOfExplicitEntries, 0, &NewAcl);
  if ( v18 )
  {
    v11 = NewAcl;
    v12 = pDacl;
    if ( pDacl )
    {
      v13 = GetLastError();
      ((void (__fastcall *)(PACL))LocalFree)(v12);
      SetLastError(v13);
    }
    pDacl = v11;
  }
  if ( v10 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xB6,
           (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
           (const char *)v10,
           phkResult);
    if ( !pDacl )
      goto LABEL_6;
LABEL_23:
    ((void (*)(void))LocalFree)();
    goto LABEL_6;
  }
  v14 = SetSecurityInfo(hKey, SE_REGISTRY_KEY, 4u, 0, 0, pDacl, 0);
  if ( v14 )
  {
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xB8,
           (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\inc\\RegSecurity.h",
           (const char *)v14,
           phkResulta);
    if ( !pDacl )
      goto LABEL_6;
    goto LABEL_23;
  }
  if ( pDacl )
    ((void (*)(void))LocalFree)();
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180116108  mov     [rsp-8+arg_10], rbx
0x18011610d  mov     [rsp-8+arg_18], rsi
0x180116112  push    rbp
0x180116113  push    rdi
0x180116114  push    r12
0x180116116  push    r14
0x180116118  push    r15
0x18011611a  lea     rbp, [rsp-37h]
0x18011611f  sub     rsp, 0C0h
0x180116126  mov     rdi, rdx
0x180116129  mov     rsi, rcx
0x18011612c  xor     r12d, r12d
0x18011612f  mov     [rbp+57h+hKey], r12
0x180116133  cmp     qword ptr [rdx+18h], 7
0x180116138  jbe     short loc_18011613D
0x18011613a  mov     rdx, [rdx]; lpSubKey
0x18011613d  lea     rax, [rbp+57h+hKey]
0x180116141  mov     [rsp+0E0h+phkResult], rax; unsigned int
0x180116146  mov     r9d, 80000h; samDesired
0x18011614c  xor     r8d, r8d; ulOptions
0x18011614f  mov     rcx, [rcx]; hKey
0x180116152  call    cs:__imp_RegOpenKeyExW
0x180116159  nop     dword ptr [rax+rax+00h]
0x18011615e  test    eax, eax
0x180116160  jz      short loc_180116198
0x180116162  mov     edx, 9Eh; void *
0x180116167  mov     rcx, [rbp+5Fh]; this
0x18011616b  mov     r9d, eax; char *
0x18011616e  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180116175  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18011617a  mov     ebx, eax
0x18011617c  mov     rcx, [rbp+57h+hKey]; hKey
0x180116180  test    rcx, rcx
0x180116183  jz      short loc_180116191
0x180116185  call    cs:__imp_RegCloseKey
0x18011618c  nop     dword ptr [rax+rax+00h]
0x180116191  mov     eax, ebx
0x180116193  jmp     loc_1801163E3
0x180116198  mov     [rsp+0E0h+pSacl], r12; pSacl
0x18011619d  mov     [rsp+0E0h+pDacl], r12; pDacl
0x1801161a2  mov     [rsp+0E0h+phkResult], r12; psidGroup
0x1801161a7  mov     r9, [rsi+28h]; psidOwner
0x1801161ab  mov     edx, 4; ObjectType
0x1801161b0  lea     r8d, [rdx-3]; SecurityInfo
0x1801161b4  mov     rcx, [rbp+57h+hKey]; handle
0x1801161b8  call    cs:__imp_SetSecurityInfo
0x1801161bf  nop     dword ptr [rax+rax+00h]
0x1801161c4  test    eax, eax
0x1801161c6  jz      short loc_1801161CF
0x1801161c8  mov     edx, 0A1h
0x1801161cd  jmp     short loc_180116167
0x1801161cf  mov     r14, [rbp+57h+hKey]
0x1801161d3  test    r14, r14
0x1801161d6  jz      short loc_180116203
0x1801161d8  call    cs:__imp_GetLastError
0x1801161df  nop     dword ptr [rax+rax+00h]
0x1801161e4  mov     ebx, eax
0x1801161e6  mov     rcx, r14; hKey
0x1801161e9  call    cs:__imp_RegCloseKey
0x1801161f0  nop     dword ptr [rax+rax+00h]
0x1801161f5  mov     ecx, ebx; dwErrCode
0x1801161f7  call    cs:__imp_SetLastError
0x1801161fe  nop     dword ptr [rax+rax+00h]
0x180116203  mov     [rbp+57h+hKey], r12
0x180116207  cmp     qword ptr [rdi+18h], 7
0x18011620c  jbe     short loc_180116211
0x18011620e  mov     rdi, [rdi]
0x180116211  lea     rax, [rbp+57h+hKey]
0x180116215  mov     [rsp+0E0h+phkResult], rax; unsigned int
0x18011621a  mov     r9d, 40000h; samDesired
0x180116220  xor     r8d, r8d; ulOptions
0x180116223  mov     rdx, rdi; lpSubKey
0x180116226  mov     rcx, [rsi]; hKey
0x180116229  call    cs:__imp_RegOpenKeyExW
0x180116230  nop     dword ptr [rax+rax+00h]
0x180116235  test    eax, eax
0x180116237  jz      short loc_180116243
0x180116239  mov     edx, 0A4h
0x18011623e  jmp     loc_180116167
0x180116243  xor     edx, edx; Val
0x180116245  lea     r8d, [rdx+60h]; Size
0x180116249  lea     rcx, [rbp+57h+pListOfExplicitEntries]; void *
0x18011624d  call    memset_0
0x180116252  mov     ecx, 0F003Fh
0x180116257  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x18011625a  mov     r10d, 2
0x180116260  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], r10d
0x180116264  lea     edx, [r10+1]
0x180116268  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], edx
0x18011626b  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], r12d
0x18011626f  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], r10d
0x180116273  mov     rax, [rsi+28h]
0x180116277  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18011627b  mov     [rbp+57h+var_50], ecx
0x18011627e  mov     [rbp+57h+var_4C], r10d
0x180116282  mov     [rbp+57h+var_48], edx
0x180116285  mov     [rbp+57h+var_34], r12d
0x180116289  mov     [rbp+57h+var_30], 5
0x180116290  mov     rax, [rsi+30h]
0x180116294  mov     [rbp+57h+var_28], rax
0x180116298  mov     [rbp+57h+arg_8], r12
0x18011629c  lea     rax, [rbp+57h+arg_8]
0x1801162a0  mov     [rbp+57h+var_A0], rax
0x1801162a4  mov     [rbp+57h+NewAcl], r12
0x1801162a8  mov     [rbp+57h+var_90], 1
0x1801162ac  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x1801162b0  xor     r8d, r8d; OldAcl
0x1801162b3  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1801162b7  mov     ecx, r10d; cCountOfExplicitEntries
0x1801162ba  call    cs:__imp_SetEntriesInAclW
0x1801162c1  nop     dword ptr [rax+rax+00h]
0x1801162c6  mov     r14d, eax
0x1801162c9  cmp     [rbp+57h+var_90], r12b
0x1801162cd  jz      short loc_18011630E
0x1801162cf  mov     r15, [rbp+57h+NewAcl]
0x1801162d3  mov     rdi, [rbp+57h+var_A0]
0x1801162d7  mov     rsi, [rdi]
0x1801162da  test    rsi, rsi
0x1801162dd  jz      short loc_18011630B
0x1801162df  call    cs:__imp_GetLastError
0x1801162e6  nop     dword ptr [rax+rax+00h]
0x1801162eb  mov     ebx, eax
0x1801162ed  mov     rcx, rsi
0x1801162f0  mov     rax, cs:__imp_LocalFree
0x1801162f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801162fc  nop
0x1801162fd  mov     ecx, ebx; dwErrCode
0x1801162ff  call    cs:__imp_SetLastError
0x180116306  nop     dword ptr [rax+rax+00h]
0x18011630b  mov     [rdi], r15
0x18011630e  test    r14d, r14d
0x180116311  jz      short loc_18011634C
0x180116313  mov     rcx, [rbp+5Fh]; this
0x180116317  mov     r9d, r14d; char *
0x18011631a  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x180116321  mov     edx, 0B6h; void *
0x180116326  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18011632b  mov     ebx, eax
0x18011632d  mov     rcx, [rbp+57h+arg_8]
0x180116331  test    rcx, rcx
0x180116334  jz      loc_18011617C
0x18011633a  mov     rax, cs:__imp_LocalFree
0x180116341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180116346  nop
0x180116347  jmp     loc_18011617C
0x18011634c  mov     rax, [rbp+57h+arg_8]
0x180116350  mov     [rsp+0E0h+pSacl], r12; pSacl
0x180116355  mov     [rsp+0E0h+pDacl], rax; pDacl
0x18011635a  mov     [rsp+0E0h+phkResult], r12; unsigned int
0x18011635f  xor     r9d, r9d; psidOwner
0x180116362  lea     edx, [r9+4]; ObjectType
0x180116366  mov     r8d, edx; SecurityInfo
0x180116369  mov     rcx, [rbp+57h+hKey]; handle
0x18011636d  call    cs:__imp_SetSecurityInfo
0x180116374  nop     dword ptr [rax+rax+00h]
0x180116379  test    eax, eax
0x18011637b  jz      short loc_1801163B6
0x18011637d  mov     rcx, [rbp+5Fh]; this
0x180116381  mov     r9d, eax; char *
0x180116384  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\featuremanage"...
0x18011638b  mov     edx, 0B8h; void *
0x180116390  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180116395  mov     ebx, eax
0x180116397  mov     rcx, [rbp+57h+arg_8]
0x18011639b  test    rcx, rcx
0x18011639e  jz      loc_18011617C
0x1801163a4  mov     rax, cs:__imp_LocalFree
0x1801163ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801163b0  nop
0x1801163b1  jmp     loc_18011617C
0x1801163b6  mov     rcx, [rbp+57h+arg_8]
0x1801163ba  test    rcx, rcx
0x1801163bd  jz      short loc_1801163CC
0x1801163bf  mov     rax, cs:__imp_LocalFree
0x1801163c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801163cb  nop
0x1801163cc  mov     rcx, [rbp+57h+hKey]; hKey
0x1801163d0  test    rcx, rcx
0x1801163d3  jz      short loc_1801163E1
0x1801163d5  call    cs:__imp_RegCloseKey
0x1801163dc  nop     dword ptr [rax+rax+00h]
0x1801163e1  xor     eax, eax
0x1801163e3  lea     r11, [rsp+0E0h+var_20]
0x1801163eb  mov     rbx, [r11+40h]
0x1801163ef  mov     rsi, [r11+48h]
0x1801163f3  mov     rsp, r11
0x1801163f6  pop     r15
0x1801163f8  pop     r14
0x1801163fa  pop     r12
0x1801163fc  pop     rdi
0x1801163fd  pop     rbp
0x1801163fe  retn
```
