# CflApiNew::InCamSession

- ea: `0x18002ad54`
- end: `0x18002aee0`
- name: `CflApiNew::InCamSession`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ba10`

## callees

- `0x1800035bc`
- `0x180010700`
- `0x18002220c`
- `0x18002222c`
- `0x18002a7cc`
- `0x18002ad54`
- `0x18002d50c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ade6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ade6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002adf9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002adf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002adf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aeb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aed6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002adf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aeb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aed6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002ae0f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002ae0f`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x18002ae5a`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsCandidateUser` at `0x18002ae5a`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsEphemeralCandidateUser` at `0x18002ae8c`
- `ext-ms-win-session-candidateaccountmgr-l1-1-0!CamIsEphemeralCandidateUser` at `0x18002ae8c`

## string_xrefs

- `0x18002adc3`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002ae1d`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002ae6b`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002ae9d`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
char CflApiNew::InCamSession()
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
  UserSid = CflApiNew::GetUserSid(NtCurrentPeb()->SessionId, &StringSid);
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
          (void *)0x245,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
          v3);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x243,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
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
      (void *)0x24C,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)IsCandidateUser,
      v8[0]);
  }
  IsEphemeralCandidateUser = CamIsEphemeralCandidateUser(hMem, &v12);
  if ( IsEphemeralCandidateUser < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
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
0x18002ad54  push    rbp
0x18002ad56  push    rsi
0x18002ad57  push    rdi
0x18002ad58  mov     rbp, rsp
0x18002ad5b  sub     rsp, 40h
0x18002ad5f  call    IsCamGetCandidateAccountCredzPresent
0x18002ad64  test    al, al
0x18002ad66  jz      loc_18002AEBD
0x18002ad6c  call    IsCamGetCandidateAccountCredzPresent
0x18002ad71  test    al, al
0x18002ad73  jz      loc_18002AEBD
0x18002ad79  mov     [rbp+var_10], 0
0x18002ad7d  lea     rcx, [rbp+var_20]; this
0x18002ad81  call    ?QueryCustomizations@ImageCustomizations@PwdlessPlat@@AEAAXXZ; PwdlessPlat::ImageCustomizations::QueryCustomizations(void)
0x18002ad86  cmp     [rbp+var_10], 0
0x18002ad8a  jz      loc_18002AEBD
0x18002ad90  mov     [rbp+hMem], 0
0x18002ad98  mov     [rbp+StringSid], 0
0x18002ada0  mov     rcx, gs:60h
0x18002ada9  lea     rdx, [rbp+StringSid]
0x18002adad  mov     ecx, [rcx+2C0h]
0x18002adb3  call    CflApiNew__GetUserSid
0x18002adb8  mov     rcx, [rbp+18h]; this
0x18002adbc  test    eax, eax
0x18002adbe  jns     short loc_18002ADD6
0x18002adc0  mov     r9d, eax; char *
0x18002adc3  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002adca  mov     edx, 243h; void *
0x18002adcf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002add4  jmp     short loc_18002AE2F
0x18002add6  cmp     [rbp+StringSid], 0
0x18002addb  jz      short loc_18002AE2F
0x18002addd  mov     rsi, [rbp+hMem]
0x18002ade1  test    rsi, rsi
0x18002ade4  jz      short loc_18002ADFF
0x18002ade6  call    cs:__imp_GetLastError
0x18002adec  mov     edi, eax
0x18002adee  mov     rcx, rsi; hMem
0x18002adf1  call    cs:__imp_LocalFree
0x18002adf7  mov     ecx, edi; dwErrCode
0x18002adf9  call    cs:__imp_SetLastError
0x18002adff  mov     [rbp+hMem], 0
0x18002ae07  lea     rdx, [rbp+hMem]; Sid
0x18002ae0b  mov     rcx, [rbp+StringSid]; StringSid
0x18002ae0f  call    cs:__imp_ConvertStringSidToSidW
0x18002ae15  mov     rcx, [rbp+18h]; this
0x18002ae19  test    eax, eax
0x18002ae1b  jnz     short loc_18002AE2F
0x18002ae1d  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002ae24  mov     edx, 245h; void *
0x18002ae29  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18002ae2e  nop
0x18002ae2f  cmp     [rbp+StringSid], 0
0x18002ae34  jz      short loc_18002AE3F
0x18002ae36  mov     rcx, [rbp+StringSid]; hMem
0x18002ae3a  call    CflFreeBuffer
0x18002ae3f  mov     rcx, [rbp+hMem]
0x18002ae43  test    rcx, rcx
0x18002ae46  jz      short loc_18002AEB2
0x18002ae48  mov     dword ptr [rbp+StringSid], 0
0x18002ae4f  mov     [rbp+arg_8], 0
0x18002ae56  lea     rdx, [rbp+StringSid]
0x18002ae5a  call    cs:__imp_CamIsCandidateUser
0x18002ae60  mov     rcx, [rbp+18h]; this
0x18002ae64  test    eax, eax
0x18002ae66  jns     short loc_18002AE7E
0x18002ae68  mov     r9d, eax; char *
0x18002ae6b  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002ae72  mov     edx, 24Ch; void *
0x18002ae77  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ae7c  jmp     short loc_18002AE84
0x18002ae7e  cmp     dword ptr [rbp+StringSid], 0
0x18002ae82  jnz     short loc_18002AECD
0x18002ae84  lea     rdx, [rbp+arg_8]
0x18002ae88  mov     rcx, [rbp+hMem]
0x18002ae8c  call    cs:__imp_CamIsEphemeralCandidateUser
0x18002ae92  mov     rcx, [rbp+18h]; this
0x18002ae96  test    eax, eax
0x18002ae98  jns     short loc_18002AEC7
0x18002ae9a  mov     r9d, eax; char *
0x18002ae9d  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002aea4  mov     edx, 24Dh; void *
0x18002aea9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002aeae  mov     rcx, [rbp+hMem]; hMem
0x18002aeb2  test    rcx, rcx
0x18002aeb5  jz      short loc_18002AEBD
0x18002aeb7  call    cs:__imp_LocalFree
0x18002aebd  xor     al, al
0x18002aebf  add     rsp, 40h
0x18002aec3  pop     rdi
0x18002aec4  pop     rsi
0x18002aec5  pop     rbp
0x18002aec6  retn
0x18002aec7  cmp     [rbp+arg_8], 0
0x18002aecb  jz      short loc_18002AEAE
0x18002aecd  mov     rcx, [rbp+hMem]; hMem
0x18002aed1  test    rcx, rcx
0x18002aed4  jz      short loc_18002AEDC
0x18002aed6  call    cs:__imp_LocalFree
0x18002aedc  mov     al, 1
0x18002aede  jmp     short loc_18002AEBF
```
