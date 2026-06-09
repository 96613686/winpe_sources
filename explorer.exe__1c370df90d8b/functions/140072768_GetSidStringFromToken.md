# GetSidStringFromToken

- ea: `0x140072768`
- end: `0x140072896`
- name: `GetSidStringFromToken`
- size: `302`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14012b8d0`

## callees

- `0x140072768`
- `0x1400954e0`
- `0x1400987b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007284e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007284e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400727e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400727e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140072816`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140072816`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400727aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400727aa`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140072798`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400727d2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140072798`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400727d2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140072807`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140072807`

## string_xrefs

- `0x140072833`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x140072862`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`
- `0x14007287f`: `shellcommondesktopbase\base\embedded\sys\lockdown\config\lib\assignedaccessconfig.cpp`

## pseudocode

```c
__int64 __fastcall GetSidStringFromToken(HANDLE TokenHandle, LPWSTR *StringSid)
{
  PSID *v4; // rdi
  const char *v5; // r9
  unsigned int LastError; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SIZE_T cb; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(cb) = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&cb) || GetLastError() == 122 )
  {
    v4 = (PSID *)CoTaskMemAlloc((unsigned int)cb);
    if ( !v4 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
        (const char *)0x8007000ELL,
        ReturnLength);
      return LastError;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, v4, cb, (PDWORD)&cb) )
    {
      if ( *StringSid )
      {
        LocalFree(*StringSid);
        *StringSid = 0;
      }
      StringSid[1] = (LPWSTR)-1LL;
      StringSid[2] = (LPWSTR)-1LL;
      if ( ConvertSidToStringSidW(*v4, StringSid) )
      {
        LastError = 0;
LABEL_8:
        CoTaskMemFree(v4);
        return LastError;
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
                  v5);
    goto LABEL_8;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x1D,
           (unsigned int)"shellcommondesktopbase\\base\\embedded\\sys\\lockdown\\config\\lib\\assignedaccessconfig.cpp",
           v8);
}

```

## disassembly

```asm
0x140072768  mov     rax, rsp
0x14007276b  mov     [rax+8], rbx
0x14007276f  mov     [rax+10h], rsi
0x140072773  push    rdi
0x140072774  sub     rsp, 30h
0x140072778  xor     r9d, r9d; TokenInformationLength
0x14007277b  mov     dword ptr [rax+18h], 0
0x140072782  mov     rbx, rdx
0x140072785  lea     rax, [rax+18h]
0x140072789  xor     r8d, r8d; TokenInformation
0x14007278c  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x140072791  mov     rsi, rcx
0x140072794  lea     edx, [r9+1]; TokenInformationClass
0x140072798  call    cs:__imp_GetTokenInformation
0x14007279e  test    eax, eax
0x1400727a0  jz      loc_14007284E
0x1400727a6  mov     ecx, dword ptr [rsp+38h+cb]; cb
0x1400727aa  call    cs:__imp_CoTaskMemAlloc
0x1400727b0  mov     rdi, rax
0x1400727b3  test    rax, rax
0x1400727b6  jz      short loc_14007282E
0x1400727b8  mov     r9d, dword ptr [rsp+38h+cb]; TokenInformationLength
0x1400727bd  lea     rax, [rsp+38h+cb]
0x1400727c2  mov     r8, rdi; TokenInformation
0x1400727c5  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1400727ca  mov     edx, 1; TokenInformationClass
0x1400727cf  mov     rcx, rsi; TokenHandle
0x1400727d2  call    cs:__imp_GetTokenInformation
0x1400727d8  test    eax, eax
0x1400727da  jz      loc_140072875
0x1400727e0  mov     rcx, [rbx]; hMem
0x1400727e3  test    rcx, rcx
0x1400727e6  jz      short loc_1400727F5
0x1400727e8  call    cs:__imp_LocalFree
0x1400727ee  mov     qword ptr [rbx], 0
0x1400727f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400727f9  mov     rdx, rbx; StringSid
0x1400727fc  mov     [rbx+8], rax
0x140072800  mov     [rbx+10h], rax
0x140072804  mov     rcx, [rdi]; Sid
0x140072807  call    cs:__imp_ConvertSidToStringSidW
0x14007280d  test    eax, eax
0x14007280f  jz      short loc_14007288F
0x140072811  xor     ebx, ebx
0x140072813  mov     rcx, rdi; pv
0x140072816  call    cs:__imp_CoTaskMemFree
0x14007281c  mov     eax, ebx
0x14007281e  mov     rbx, [rsp+38h+arg_0]
0x140072823  mov     rsi, [rsp+38h+arg_8]
0x140072828  add     rsp, 30h
0x14007282c  pop     rdi
0x14007282d  retn
0x14007282e  mov     rcx, [rsp+38h]; this
0x140072833  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x14007283a  mov     ebx, 8007000Eh
0x14007283f  mov     edx, 20h ; ' '; void *
0x140072844  mov     r9d, ebx; char *
0x140072847  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007284c  jmp     short loc_14007281C
0x14007284e  call    cs:__imp_GetLastError
0x140072854  cmp     eax, 7Ah ; 'z'
0x140072857  jz      loc_1400727A6
0x14007285d  mov     rcx, [rsp+38h]; this
0x140072862  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140072869  mov     edx, 1Dh; void *
0x14007286e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140072873  jmp     short loc_14007281E
0x140072875  mov     edx, 21h ; '!'; void *
0x14007287a  mov     rcx, [rsp+38h]; this
0x14007287f  lea     r8, aShellcommondes_1; "shellcommondesktopbase\\base\\embedded"...
0x140072886  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14007288b  mov     ebx, eax
0x14007288d  jmp     short loc_140072813
0x14007288f  mov     edx, 22h ; '"'
0x140072894  jmp     short loc_14007287A
```
