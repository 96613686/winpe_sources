# CflApi::InCamSession

- ea: `0x18001f2d8`
- end: `0x18001f464`
- name: `CflApi::InCamSession`
- size: `396`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011b10`
- `0x180020378`

## callees

- `0x1800035bc`
- `0x180010700`
- `0x18001e970`
- `0x18001f2d8`
- `0x18002220c`
- `0x18002222c`
- `0x18002d50c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f36a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f36a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f37d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f37d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f375`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f43b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f45a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f375`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f43b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f45a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001f393`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001f393`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x18001f3de`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x18001f3de`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsEphemeralCandidateUser` at `0x18001f410`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsEphemeralCandidateUser` at `0x18001f410`

## string_xrefs

- `0x18001f347`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001f3a1`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001f3ef`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001f421`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char CflApi::InCamSession()
{
  int UserSid; // eax
  HLOCAL v1; // rsi
  DWORD LastError; // edi
  const char *v3; // r9
  HLOCAL v4; // rcx
  int IsCandidateUser; // eax
  int IsEphemeralCandidateUser; // eax
  int v8[4]; // [rsp+20h] [rbp-20h] BYREF
  char v9; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  LPCWSTR StringSid; // [rsp+60h] [rbp+20h] BYREF
  int v12; // [rsp+68h] [rbp+28h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+30h] BYREF

  if ( !(unsigned __int8)IsCamGetCandidateAccountCredzPresent() )
    return 0;
  if ( !(unsigned __int8)IsCamGetCandidateAccountCredzPresent() )
    return 0;
  v9 = 0;
  PwdlessPlat::ImageCustomizations::QueryCustomizations((PwdlessPlat::ImageCustomizations *)v8);
  if ( !v9 )
    return 0;
  hMem = 0;
  StringSid = 0;
  UserSid = CflApi::GetUserSid(NtCurrentPeb()->SessionId, &StringSid);
  if ( UserSid >= 0 )
  {
    if ( StringSid )
    {
      v1 = hMem;
      if ( hMem )
      {
        LastError = GetLastError();
        LocalFree(v1);
        SetLastError(LastError);
      }
      hMem = 0;
      if ( !ConvertStringSidToSidW(StringSid, &hMem) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x4C2,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
          v3);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4C0,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)UserSid,
      v8[0]);
  }
  if ( StringSid )
    CflFreeBuffer((HLOCAL)StringSid);
  v4 = hMem;
  if ( !hMem )
  {
LABEL_20:
    if ( v4 )
      LocalFree(v4);
    return 0;
  }
  LODWORD(StringSid) = 0;
  v12 = 0;
  IsCandidateUser = CamIsCandidateUser(hMem, &StringSid);
  if ( IsCandidateUser >= 0 )
  {
    if ( (_DWORD)StringSid )
      goto LABEL_24;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4C9,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)IsCandidateUser,
      v8[0]);
  }
  IsEphemeralCandidateUser = CamIsEphemeralCandidateUser(hMem, &v12);
  if ( IsEphemeralCandidateUser < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x4CA,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)IsEphemeralCandidateUser,
      v8[0]);
LABEL_19:
    v4 = hMem;
    goto LABEL_20;
  }
  if ( !v12 )
    goto LABEL_19;
LABEL_24:
  if ( hMem )
    LocalFree(hMem);
  return 1;
}

```

## disassembly

```asm
0x18001f2d8  push    rbp
0x18001f2da  push    rsi
0x18001f2db  push    rdi
0x18001f2dc  mov     rbp, rsp
0x18001f2df  sub     rsp, 40h
0x18001f2e3  call    IsCamGetCandidateAccountCredzPresent
0x18001f2e8  test    al, al
0x18001f2ea  jz      loc_18001F441
0x18001f2f0  call    IsCamGetCandidateAccountCredzPresent
0x18001f2f5  test    al, al
0x18001f2f7  jz      loc_18001F441
0x18001f2fd  mov     [rbp+var_10], 0
0x18001f301  lea     rcx, [rbp+var_20]; this
0x18001f305  call    ?QueryCustomizations@ImageCustomizations@PwdlessPlat@@AEAAXXZ; PwdlessPlat::ImageCustomizations::QueryCustomizations(void)
0x18001f30a  cmp     [rbp+var_10], 0
0x18001f30e  jz      loc_18001F441
0x18001f314  mov     [rbp+hMem], 0
0x18001f31c  mov     [rbp+StringSid], 0
0x18001f324  mov     rcx, gs:60h
0x18001f32d  lea     rdx, [rbp+StringSid]
0x18001f331  mov     ecx, [rcx+2C0h]
0x18001f337  call    CflApi__GetUserSid
0x18001f33c  mov     rcx, [rbp+18h]; this
0x18001f340  test    eax, eax
0x18001f342  jns     short loc_18001F35A
0x18001f344  mov     r9d, eax; char *
0x18001f347  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f34e  mov     edx, 4C0h; void *
0x18001f353  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f358  jmp     short loc_18001F3B3
0x18001f35a  cmp     [rbp+StringSid], 0
0x18001f35f  jz      short loc_18001F3B3
0x18001f361  mov     rsi, [rbp+hMem]
0x18001f365  test    rsi, rsi
0x18001f368  jz      short loc_18001F383
0x18001f36a  call    cs:__imp_GetLastError
0x18001f370  mov     edi, eax
0x18001f372  mov     rcx, rsi; hMem
0x18001f375  call    cs:__imp_LocalFree
0x18001f37b  mov     ecx, edi; dwErrCode
0x18001f37d  call    cs:__imp_SetLastError
0x18001f383  mov     [rbp+hMem], 0
0x18001f38b  lea     rdx, [rbp+hMem]; Sid
0x18001f38f  mov     rcx, [rbp+StringSid]; StringSid
0x18001f393  call    cs:__imp_ConvertStringSidToSidW
0x18001f399  mov     rcx, [rbp+18h]; this
0x18001f39d  test    eax, eax
0x18001f39f  jnz     short loc_18001F3B3
0x18001f3a1  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f3a8  mov     edx, 4C2h; void *
0x18001f3ad  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001f3b2  nop
0x18001f3b3  cmp     [rbp+StringSid], 0
0x18001f3b8  jz      short loc_18001F3C3
0x18001f3ba  mov     rcx, [rbp+StringSid]; hMem
0x18001f3be  call    CflFreeBuffer
0x18001f3c3  mov     rcx, [rbp+hMem]
0x18001f3c7  test    rcx, rcx
0x18001f3ca  jz      short loc_18001F436
0x18001f3cc  mov     dword ptr [rbp+StringSid], 0
0x18001f3d3  mov     [rbp+arg_8], 0
0x18001f3da  lea     rdx, [rbp+StringSid]
0x18001f3de  call    cs:__imp_CamIsCandidateUser
0x18001f3e4  mov     rcx, [rbp+18h]; this
0x18001f3e8  test    eax, eax
0x18001f3ea  jns     short loc_18001F402
0x18001f3ec  mov     r9d, eax; char *
0x18001f3ef  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f3f6  mov     edx, 4C9h; void *
0x18001f3fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f400  jmp     short loc_18001F408
0x18001f402  cmp     dword ptr [rbp+StringSid], 0
0x18001f406  jnz     short loc_18001F451
0x18001f408  lea     rdx, [rbp+arg_8]
0x18001f40c  mov     rcx, [rbp+hMem]
0x18001f410  call    cs:__imp_CamIsEphemeralCandidateUser
0x18001f416  mov     rcx, [rbp+18h]; this
0x18001f41a  test    eax, eax
0x18001f41c  jns     short loc_18001F44B
0x18001f41e  mov     r9d, eax; char *
0x18001f421  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f428  mov     edx, 4CAh; void *
0x18001f42d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f432  mov     rcx, [rbp+hMem]; hMem
0x18001f436  test    rcx, rcx
0x18001f439  jz      short loc_18001F441
0x18001f43b  call    cs:__imp_LocalFree
0x18001f441  xor     al, al
0x18001f443  add     rsp, 40h
0x18001f447  pop     rdi
0x18001f448  pop     rsi
0x18001f449  pop     rbp
0x18001f44a  retn
0x18001f44b  cmp     [rbp+arg_8], 0
0x18001f44f  jz      short loc_18001F432
0x18001f451  mov     rcx, [rbp+hMem]; hMem
0x18001f455  test    rcx, rcx
0x18001f458  jz      short loc_18001F460
0x18001f45a  call    cs:__imp_LocalFree
0x18001f460  mov     al, 1
0x18001f462  jmp     short loc_18001F443
```
