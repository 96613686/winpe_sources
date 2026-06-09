# GetSidStringFromToken

- ea: `0x1800800a8`
- end: `0x1800801ba`
- name: `GetSidStringFromToken`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18007571c`
- `0x180080388`

## callees

- `0x180017988`
- `0x1800179ac`
- `0x1800800a8`
- `0x180080318`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800800e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800800e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008010c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008010c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800801a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800801a2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800800d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080152`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800800d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180080152`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008017b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008017b`

## string_xrefs

- `0x1800800f2`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x18008011f`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x18008018d`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
__int64 __fastcall GetSidStringFromToken(HANDLE TokenHandle, LPWSTR *StringSid)
{
  const char *v4; // r9
  PSID *v6; // rdi
  unsigned int LastError; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SIZE_T cb; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(cb) = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&cb) && GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1D,
             (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
             v4);
  v6 = (PSID *)CoTaskMemAlloc((unsigned int)cb);
  if ( v6 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, v6, cb, (PDWORD)&cb) )
    {
      Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<unsigned short>>::_Free(StringSid);
      StringSid[1] = (LPWSTR)-1LL;
      StringSid[2] = (LPWSTR)-1LL;
      if ( ConvertSidToStringSidW(*v6, StringSid) )
      {
        LastError = 0;
        goto LABEL_12;
      }
      v9 = 34;
    }
    else
    {
      v9 = 33;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
                  v8);
LABEL_12:
    CoTaskMemFree(v6);
    return LastError;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x20,
    (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
    (const char *)0x8007000ELL,
    ReturnLength);
  return LastError;
}

```

## disassembly

```asm
0x1800800a8  mov     rax, rsp
0x1800800ab  mov     [rax+8], rbx
0x1800800af  mov     [rax+10h], rsi
0x1800800b3  push    rdi
0x1800800b4  sub     rsp, 30h
0x1800800b8  xor     r9d, r9d; TokenInformationLength
0x1800800bb  mov     dword ptr [rax+18h], 0
0x1800800c2  mov     rbx, rdx
0x1800800c5  lea     rax, [rax+18h]
0x1800800c9  xor     r8d, r8d; TokenInformation
0x1800800cc  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1800800d1  mov     rsi, rcx
0x1800800d4  lea     edx, [r9+1]; TokenInformationClass
0x1800800d8  call    cs:__imp_GetTokenInformation
0x1800800de  test    eax, eax
0x1800800e0  jnz     short loc_180080108
0x1800800e2  call    cs:__imp_GetLastError
0x1800800e8  cmp     eax, 7Ah ; 'z'
0x1800800eb  jz      short loc_180080108
0x1800800ed  mov     rcx, [rsp+38h]; this
0x1800800f2  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x1800800f9  mov     edx, 1Dh; void *
0x1800800fe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180080103  jmp     loc_1800801AA
0x180080108  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x18008010c  call    cs:__imp_CoTaskMemAlloc
0x180080112  mov     rdi, rax
0x180080115  test    rax, rax
0x180080118  jnz     short loc_180080138
0x18008011a  mov     rcx, [rsp+38h]; this
0x18008011f  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x180080126  mov     ebx, 8007000Eh
0x18008012b  lea     edx, [rax+20h]; void *
0x18008012e  mov     r9d, ebx; char *
0x180080131  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080136  jmp     short loc_1800801A8
0x180080138  mov     r9d, dword ptr [rsp+38h+cb]; TokenInformationLength
0x18008013d  lea     rax, [rsp+38h+cb]
0x180080142  mov     r8, rdi; TokenInformation
0x180080145  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x18008014a  mov     edx, 1; TokenInformationClass
0x18008014f  mov     rcx, rsi; TokenHandle
0x180080152  call    cs:__imp_GetTokenInformation
0x180080158  test    eax, eax
0x18008015a  jnz     short loc_180080161
0x18008015c  lea     edx, [rax+21h]
0x18008015f  jmp     short loc_180080188
0x180080161  mov     rcx, rbx
0x180080164  call    ?_Free@?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>>::_Free(void)
0x180080169  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008016d  mov     rdx, rbx; StringSid
0x180080170  mov     [rbx+8], rax
0x180080174  mov     [rbx+10h], rax
0x180080178  mov     rcx, [rdi]; Sid
0x18008017b  call    cs:__imp_ConvertSidToStringSidW
0x180080181  test    eax, eax
0x180080183  jnz     short loc_18008019D
0x180080185  lea     edx, [rax+22h]; void *
0x180080188  mov     rcx, [rsp+38h]; this
0x18008018d  lea     r8, aShellcommondes_0; "shellcommondesktopbase\\base\\embedded"...
0x180080194  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180080199  mov     ebx, eax
0x18008019b  jmp     short loc_18008019F
0x18008019d  xor     ebx, ebx
0x18008019f  mov     rcx, rdi; pv
0x1800801a2  call    cs:__imp_CoTaskMemFree
0x1800801a8  mov     eax, ebx
0x1800801aa  mov     rbx, [rsp+38h+arg_0]
0x1800801af  mov     rsi, [rsp+38h+arg_8]
0x1800801b4  add     rsp, 30h
0x1800801b8  pop     rdi
0x1800801b9  retn
```
