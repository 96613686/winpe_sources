# CSessionManager::CRestrictedCalls::ValidateLogonCert(ushort const *,unsigned __int64 *)

- ea: `0x1800822f0`
- end: `0x1800828f6`
- name: `?ValidateLogonCert@CRestrictedCalls@CSessionManager@@UEAAJPEBGPEA_K@Z`
- size: `1542`
- prototype: `__int64 __fastcall(CSessionManager::CRestrictedCalls *__hidden this, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x180001b90`
- `0x1800031e0`
- `0x180003324`
- `0x180026c8c`
- `0x18002772c`
- `0x18004e850`
- `0x18004ec20`
- `0x18004ed00`
- `0x180081ad0`
- `0x180081f98`
- `0x1800822f0`
- `0x18009c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180082453`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180082453`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082771`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800827d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800827d8`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180082761`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180082761`
- `SspiCli!LogonUserExExW` at `0x180082370`
- `SspiCli!LogonUserExExW` at `0x180082370`
- `SspiCli!LsaLogonUser` at `0x1800826a4`
- `SspiCli!LsaLogonUser` at `0x1800826a4`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18008286d`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18008286d`
- `SspiCli!LsaConnectUntrusted` at `0x180082594`
- `SspiCli!LsaConnectUntrusted` at `0x180082594`

## string_xrefs

- `0x1800823b7`: `Legacy call to LogonUserExExW failed. Attempting LsaLogonuser.`
- `0x1800823e7`: `Terminal Services API`

## pseudocode

```c
__int64 __fastcall CSessionManager::CRestrictedCalls::ValidateLogonCert(
        CSessionManager::CRestrictedCalls *this,
        const unsigned __int16 *a2,
        unsigned __int64 *a3)
{
  unsigned __int16 *v6; // r14
  unsigned __int8 *AuthenticationInformation; // rsi
  signed int LastError; // eax
  ULONG v9; // ebx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int LogonBlobForCertValidation; // eax
  int v14; // r8d
  int v15; // r9d
  const struct std::nothrow_t *v16; // rdx
  signed int v17; // ebx
  int v18; // r8d
  int v19; // r9d
  NTSTATUS v20; // eax
  int v21; // r8d
  int v22; // r9d
  NTSTATUS v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  char *v27; // rdx
  const char *v28; // rax
  signed int v29; // eax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  unsigned int v33; // ebx
  __int64 (__fastcall *v34)(CSessionManager::CRestrictedCalls *, void *, _QWORD, unsigned __int64 *, unsigned int); // rdi
  DWORD CurrentProcessId; // eax
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  NTSTATUS v39; // eax
  int v40; // r8d
  int v41; // r9d
  ULONG AuthenticationInformationLength; // [rsp+70h] [rbp-90h] BYREF
  int v44; // [rsp+74h] [rbp-8Ch] BYREF
  const char *v45; // [rsp+78h] [rbp-88h] BYREF
  const char *v46; // [rsp+80h] [rbp-80h] BYREF
  ULONG ProfileBufferLength; // [rsp+88h] [rbp-78h] BYREF
  const char *v48; // [rsp+90h] [rbp-70h] BYREF
  unsigned int Pid; // [rsp+98h] [rbp-68h] BYREF
  const char *v50; // [rsp+A0h] [rbp-60h] BYREF
  const char *v51; // [rsp+A8h] [rbp-58h] BYREF
  int SubStatus; // [rsp+B0h] [rbp-50h] BYREF
  void *Token; // [rsp+B8h] [rbp-48h] BYREF
  void *LsaHandle; // [rsp+C0h] [rbp-40h] BYREF
  PVOID ProfileBuffer; // [rsp+C8h] [rbp-38h] BYREF
  _LSA_STRING OriginName; // [rsp+D0h] [rbp-30h] BYREF
  struct _LUID LogonId; // [rsp+E0h] [rbp-20h] BYREF
  struct _TOKEN_SOURCE SourceContext; // [rsp+E8h] [rbp-18h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+F8h] [rbp-8h] BYREF
  char v60[24]; // [rsp+128h] [rbp+28h] BYREF

  Pid = 0;
  v6 = 0;
  Token = 0;
  AuthenticationInformation = 0;
  LsaHandle = 0;
  if ( !(unsigned int)LogonUserExExW(a2, &dword_1800A8ADC, &dword_1800A8ADC, 3, 0, 0, &Token, 0, 0, 0, 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( !(unsigned int)IsNGCValidationEnabled() )
    {
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        ProfileBufferLength = v9;
        ProfileBuffer = "Legacy call to LogonUserExExW failed. New NGC Validation is disabled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v10,
          (unsigned int)word_1800CCD22,
          v11,
          v12,
          (__int64)&ProfileBuffer,
          (__int64)&ProfileBufferLength);
      }
      goto LABEL_24;
    }
    if ( (unsigned int)dword_1800DF020 > 4 )
    {
      AuthenticationInformationLength = v9;
      v45 = "Legacy call to LogonUserExExW failed. Attempting LsaLogonuser.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&unk_1800CCEA8,
        v11,
        v12,
        (__int64)&v45,
        (__int64)&AuthenticationInformationLength);
    }
    strcpy(v60, "Terminal Services API");
    AuthenticationInformationLength = 0;
    SourceContext = 0;
    *(_QWORD *)&OriginName.Length = 1441814;
    memset(&Quotas, 0, sizeof(Quotas));
    OriginName.Buffer = v60;
    ProfileBuffer = 0;
    ProfileBufferLength = 0;
    LogonId = 0;
    SubStatus = 0;
    v6 = (unsigned __int16 *)operator new[](0x208u);
    _o_wcsncpy_s(v6, 260, a2, -1);
    LogonBlobForCertValidation = GetLogonBlobForCertValidation(v6, &AuthenticationInformationLength, 0);
    if ( LogonBlobForCertValidation < 0 && (unsigned int)dword_1800DF020 > 3 )
    {
      v44 = LogonBlobForCertValidation;
      v45 = "ValidateLogonCert";
      v50 = "GetLogonBlobForCertValidation failed when telling us how big of a buffer.";
      v48 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1800DF020,
        (unsigned int)&unk_1800CCE68,
        v14,
        v15,
        (__int64)&v48,
        (__int64)&v50,
        (__int64)&v44,
        (__int64)&v45);
    }
    AuthenticationInformation = (unsigned __int8 *)operator new[](AuthenticationInformationLength);
    v17 = GetLogonBlobForCertValidation(v6, &AuthenticationInformationLength, AuthenticationInformation);
    if ( v17 < 0 )
    {
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        v50 = "ValidateLogonCert";
        v48 = "GetLogonBlobForCertValidation failed after allocating buffer";
        v44 = 320;
        v45 = "clientcore\\termsrv\\newsvc\\core\\restrictedcalls.cpp";
        v51 = "Error HResult failed";
        AuthenticationInformationLength = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          dword_1800DF020,
          (unsigned int)&word_1800CCE16,
          v18,
          v19,
          (__int64)&v51,
          (__int64)&AuthenticationInformationLength,
          (__int64)&v45,
          (__int64)&v44,
          (__int64)&v50,
          (__int64)&v48);
      }
      goto LABEL_32;
    }
    v20 = LsaConnectUntrusted(&LsaHandle);
    if ( v20 < 0 )
    {
      v17 = -2147467259;
      if ( (unsigned int)dword_1800DF020 > 2 )
      {
        v44 = v20;
        v48 = "ValidateLogonCert";
        v51 = "LsaConnectUntrusted failed";
        v50 = "clientcore\\termsrv\\newsvc\\core\\restrictedcalls.cpp";
        v46 = "Error HResult failed";
        AuthenticationInformationLength = 326;
        LODWORD(v45) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_1800DF020,
          (unsigned int)byte_1800CCDB9,
          v21,
          v22,
          (__int64)&v46,
          (__int64)&v45,
          (__int64)&v50,
          (__int64)&AuthenticationInformationLength,
          (__int64)&v48,
          (__int64)&v51,
          (__int64)&v44);
      }
      goto LABEL_32;
    }
    v23 = LsaLogonUser(
            LsaHandle,
            &OriginName,
            Network,
            0,
            AuthenticationInformation,
            AuthenticationInformationLength,
            0,
            &SourceContext,
            &ProfileBuffer,
            &ProfileBufferLength,
            &LogonId,
            &Token,
            &Quotas,
            &SubStatus);
    if ( v23 >= 0 )
    {
      if ( (unsigned int)dword_1800DF020 <= 4 )
        goto LABEL_24;
      LODWORD(v45) = v23;
      v28 = "LsaLogonuser with NGC was successful";
      v27 = byte_1800CCD4D;
      v44 = v17;
    }
    else
    {
      v24 = dword_1800DF020;
      if ( (unsigned int)dword_1800DF020 <= 2 )
        goto LABEL_24;
      LODWORD(v45) = v23;
      v27 = byte_1800CCD83;
      v28 = "LogonUser and LsaLogonuser with NGC cert failed";
      v44 = -2147467259;
    }
    v46 = v28;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v24,
      (_DWORD)v27,
      v25,
      v26,
      (__int64)&v46,
      (__int64)&v44,
      (__int64)&v45);
  }
LABEL_24:
  if ( I_RpcBindingInqLocalClientPID(0, &Pid) )
  {
    v29 = GetLastError();
    v17 = v29;
    if ( v29 > 0 )
      v17 = (unsigned __int16)v29 | 0x80070000;
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      LODWORD(v45) = v17;
      v46 = "I_RpcBindingInqLocalClientPID failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)&byte_1800CCCF7,
        v31,
        v32,
        (__int64)&v46,
        (__int64)&v45);
    }
  }
  else
  {
    v33 = Pid;
    v34 = *(__int64 (__fastcall **)(CSessionManager::CRestrictedCalls *, void *, _QWORD, unsigned __int64 *, unsigned int))(*(_QWORD *)this + 24LL);
    CurrentProcessId = GetCurrentProcessId();
    v17 = v34(this, Token, CurrentProcessId, a3, v33);
    if ( v17 < 0 && (unsigned int)dword_1800DF020 > 3 )
    {
      LODWORD(v45) = v17;
      v46 = "ValidateLogonCert";
      v51 = "DuplicateHandleInPid";
      v48 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v36,
        (unsigned int)&byte_1800CCCB7,
        v37,
        v38,
        (__int64)&v48,
        (__int64)&v51,
        (__int64)&v45,
        (__int64)&v46);
    }
  }
LABEL_32:
  if ( LsaHandle )
  {
    v39 = LsaDeregisterLogonProcess(LsaHandle);
    if ( (unsigned int)dword_1800DF020 > 3 )
    {
      LODWORD(v45) = v39;
      v46 = "LsaDeregisterLogonProcess failed, leaked handle?";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DF020,
        (unsigned int)&byte_1800CCC87,
        v40,
        v41,
        (__int64)&v46,
        (__int64)&v45);
    }
  }
  if ( v6 )
    operator delete(v6, v16);
  if ( AuthenticationInformation )
    operator delete(AuthenticationInformation, v16);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800822f0  mov     [rsp-8+arg_18], rbx
0x1800822f5  push    rbp
0x1800822f6  push    rsi
0x1800822f7  push    rdi
0x1800822f8  push    r12
0x1800822fa  push    r13
0x1800822fc  push    r14
0x1800822fe  push    r15
0x180082300  lea     rbp, [rsp-50h]
0x180082305  sub     rsp, 150h
0x18008230c  mov     rax, cs:__security_cookie
0x180082313  xor     rax, rsp
0x180082316  mov     [rbp+80h+var_40], rax
0x18008231a  xor     r13d, r13d
0x18008231d  lea     rax, [rbp+80h+var_C8]
0x180082321  mov     [rsp+180h+LogonId], r13
0x180082326  mov     rdi, rdx
0x180082329  mov     [rsp+180h+ProfileBufferLength], r13
0x18008232e  lea     rdx, dword_1800A8ADC
0x180082335  mov     [rsp+180h+ProfileBuffer], r13
0x18008233a  mov     r12, r8
0x18008233d  mov     [rsp+180h+SourceContext], r13
0x180082342  lea     r9d, [r13+3]
0x180082346  mov     [rsp+180h+LocalGroups], rax
0x18008234b  mov     r15, rcx
0x18008234e  mov     qword ptr [rsp+180h+AuthenticationInformationLength], r13
0x180082353  mov     r8, rdx
0x180082356  mov     rcx, rdi
0x180082359  mov     dword ptr [rsp+180h+AuthenticationInformation], r13d
0x18008235e  mov     [rbp+80h+Pid], r13d
0x180082362  mov     r14d, r13d
0x180082365  mov     [rbp+80h+var_C8], r13
0x180082369  mov     esi, r13d
0x18008236c  mov     [rbp+80h+LsaHandle], r13
0x180082370  call    cs:__imp_LogonUserExExW
0x180082377  nop     dword ptr [rax+rax+00h]
0x18008237c  test    eax, eax
0x18008237e  jnz     loc_18008275B
0x180082384  call    cs:__imp_GetLastError
0x18008238b  nop     dword ptr [rax+rax+00h]
0x180082390  mov     ebx, eax
0x180082392  test    eax, eax
0x180082394  jle     short loc_18008239F
0x180082396  movzx   ebx, ax
0x180082399  or      ebx, 80070000h
0x18008239f  call    ?IsNGCValidationEnabled@@YAHXZ; IsNGCValidationEnabled(void)
0x1800823a4  test    eax, eax
0x1800823a6  mov     eax, cs:dword_1800DF020
0x1800823ac  jz      loc_18008272A
0x1800823b2  cmp     eax, 4
0x1800823b5  jbe     short loc_1800823E7
0x1800823b7  lea     rax, aLegacyCallToLo; "Legacy call to LogonUserExExW failed. A"...
0x1800823be  mov     [rsp+180h+var_110], ebx
0x1800823c2  mov     [rsp+180h+var_108], rax
0x1800823c7  lea     rdx, unk_1800CCEA8
0x1800823ce  lea     rax, [rsp+180h+var_110]
0x1800823d3  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x1800823d8  lea     rax, [rsp+180h+var_108]
0x1800823dd  mov     [rsp+180h+AuthenticationInformation], rax
0x1800823e2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800823e7  movups  xmm0, xmmword ptr cs:aTerminalServic_1; "Terminal Services API"
0x1800823ee  lea     rax, [rbp+80h+var_58]
0x1800823f2  mov     ecx, 208h; unsigned __int64
0x1800823f7  movsd   xmm1, qword ptr cs:aTerminalServic_1+0Eh; "ces API"
0x1800823ff  movups  xmmword ptr [rbp+80h+var_58], xmm0
0x180082403  mov     [rsp+180h+var_110], r13d
0x180082408  xorps   xmm0, xmm0
0x18008240b  movsd   qword ptr [rbp+80h+var_58+0Eh], xmm1
0x180082410  movups  xmmword ptr [rbp+80h+var_98.SourceName], xmm0
0x180082414  mov     qword ptr [rbp+80h+OriginName.Length], 160016h
0x18008241c  movups  xmmword ptr [rbp+80h+var_88.PagedPoolLimit], xmm0
0x180082420  mov     [rbp+80h+OriginName.Buffer], rax
0x180082424  movups  xmmword ptr [rbp+80h+var_88.MinimumWorkingSetSize], xmm0
0x180082428  mov     [rbp+80h+var_B8], r13
0x18008242c  movups  xmmword ptr [rbp+80h+var_88.PagefileLimit], xmm0
0x180082430  mov     [rbp+80h+var_F8], r13d
0x180082434  mov     qword ptr [rbp+80h+var_A0.LowPart], r13
0x180082438  mov     [rbp+80h+var_D0], r13d
0x18008243c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180082441  or      r9, 0FFFFFFFFFFFFFFFFh
0x180082445  mov     r8, rdi
0x180082448  mov     edx, 104h
0x18008244d  mov     rcx, rax
0x180082450  mov     r14, rax
0x180082453  call    cs:__imp__o_wcsncpy_s
0x18008245a  nop     dword ptr [rax+rax+00h]
0x18008245f  xor     r8d, r8d; unsigned __int8 *
0x180082462  lea     rdx, [rsp+180h+var_110]; unsigned int *
0x180082467  mov     rcx, r14; unsigned __int16 *
0x18008246a  call    ?GetLogonBlobForCertValidation@@YAJPEAGPEAKPEAE@Z; GetLogonBlobForCertValidation(ushort *,ulong *,uchar *)
0x18008246f  test    eax, eax
0x180082471  jns     short loc_1800824D8
0x180082473  mov     ecx, cs:dword_1800DF020
0x180082479  cmp     ecx, 3
0x18008247c  jbe     short loc_1800824D8
0x18008247e  mov     [rsp+180h+var_10C], eax
0x180082482  lea     rdi, aValidatelogonc; "ValidateLogonCert"
0x180082489  lea     rax, aGetlogonblobfo; "GetLogonBlobForCertValidation failed wh"...
0x180082490  mov     [rsp+180h+var_108], rdi
0x180082495  mov     [rbp+80h+var_E0], rax
0x180082499  lea     rdx, unk_1800CCE68
0x1800824a0  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800824a7  mov     [rbp+80h+var_F0], rax
0x1800824ab  lea     rax, [rsp+180h+var_108]
0x1800824b0  mov     [rsp+180h+SourceContext], rax
0x1800824b5  lea     rax, [rsp+180h+var_10C]
0x1800824ba  mov     [rsp+180h+LocalGroups], rax
0x1800824bf  lea     rax, [rbp+80h+var_E0]
0x1800824c3  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x1800824c8  lea     rax, [rbp+80h+var_F0]
0x1800824cc  mov     [rsp+180h+AuthenticationInformation], rax
0x1800824d1  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800824d6  jmp     short loc_1800824DF
0x1800824d8  lea     rdi, aValidatelogonc; "ValidateLogonCert"
0x1800824df  mov     ecx, [rsp+180h+var_110]; unsigned __int64
0x1800824e3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800824e8  mov     r8, rax; unsigned __int8 *
0x1800824eb  lea     rdx, [rsp+180h+var_110]; unsigned int *
0x1800824f0  mov     rcx, r14; unsigned __int16 *
0x1800824f3  mov     rsi, rax
0x1800824f6  call    ?GetLogonBlobForCertValidation@@YAJPEAGPEAKPEAE@Z; GetLogonBlobForCertValidation(ushort *,ulong *,uchar *)
0x1800824fb  mov     ebx, eax
0x1800824fd  test    eax, eax
0x1800824ff  jns     loc_180082590
0x180082505  mov     ecx, cs:dword_1800DF020
0x18008250b  cmp     ecx, 2
0x18008250e  jbe     loc_180082864
0x180082514  lea     rax, aGetlogonblobfo_0; "GetLogonBlobForCertValidation failed af"...
0x18008251b  mov     [rbp+80h+var_E0], rdi
0x18008251f  mov     [rbp+80h+var_F0], rax
0x180082523  lea     rdx, word_1800CCE16
0x18008252a  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\newsvc\\core\\rest"...
0x180082531  mov     [rsp+180h+var_10C], 140h
0x180082539  mov     [rsp+180h+var_108], rax
0x18008253e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180082545  mov     [rbp+80h+var_D8], rax
0x180082549  lea     rax, [rbp+80h+var_F0]
0x18008254d  mov     [rsp+180h+ProfileBufferLength], rax
0x180082552  lea     rax, [rbp+80h+var_E0]
0x180082556  mov     [rsp+180h+ProfileBuffer], rax
0x18008255b  lea     rax, [rsp+180h+var_10C]
0x180082560  mov     [rsp+180h+SourceContext], rax
0x180082565  lea     rax, [rsp+180h+var_108]
0x18008256a  mov     [rsp+180h+LocalGroups], rax
0x18008256f  lea     rax, [rsp+180h+var_110]
0x180082574  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x180082579  lea     rax, [rbp+80h+var_D8]
0x18008257d  mov     [rsp+180h+AuthenticationInformation], rax
0x180082582  mov     [rsp+180h+var_110], ebx
0x180082586  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008258b  jmp     loc_180082864
0x180082590  lea     rcx, [rbp+80h+LsaHandle]; LsaHandle
0x180082594  call    cs:__imp_LsaConnectUntrusted
0x18008259b  nop     dword ptr [rax+rax+00h]
0x1800825a0  test    eax, eax
0x1800825a2  jns     loc_180082644
0x1800825a8  mov     ecx, cs:dword_1800DF020
0x1800825ae  mov     ebx, 80004005h
0x1800825b3  cmp     ecx, 2
0x1800825b6  jbe     loc_180082864
0x1800825bc  mov     [rsp+180h+var_10C], eax
0x1800825c0  lea     rdx, byte_1800CCDB9
0x1800825c7  lea     rax, aLsaconnectuntr_0; "LsaConnectUntrusted failed"
0x1800825ce  mov     [rbp+80h+var_F0], rdi
0x1800825d2  mov     [rbp+80h+var_D8], rax
0x1800825d6  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\newsvc\\core\\rest"...
0x1800825dd  mov     [rbp+80h+var_E0], rax
0x1800825e1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800825e8  mov     [rbp+80h+var_100], rax
0x1800825ec  lea     rax, [rsp+180h+var_10C]
0x1800825f1  mov     [rsp+180h+LogonId], rax
0x1800825f6  lea     rax, [rbp+80h+var_D8]
0x1800825fa  mov     [rsp+180h+ProfileBufferLength], rax
0x1800825ff  lea     rax, [rbp+80h+var_F0]
0x180082603  mov     [rsp+180h+ProfileBuffer], rax
0x180082608  lea     rax, [rsp+180h+var_110]
0x18008260d  mov     [rsp+180h+SourceContext], rax
0x180082612  lea     rax, [rbp+80h+var_E0]
0x180082616  mov     [rsp+180h+LocalGroups], rax
0x18008261b  lea     rax, [rsp+180h+var_108]
0x180082620  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x180082625  lea     rax, [rbp+80h+var_100]
0x180082629  mov     [rsp+180h+AuthenticationInformation], rax
0x18008262e  mov     [rsp+180h+var_110], 146h
0x180082636  mov     dword ptr [rsp+180h+var_108], ebx
0x18008263a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008263f  jmp     loc_180082864
0x180082644  mov     rcx, [rbp+80h+LsaHandle]; LsaHandle
0x180082648  lea     rax, [rbp+80h+var_D0]
0x18008264c  mov     [rsp+180h+SubStatus], rax; SubStatus
0x180082651  lea     rdx, [rbp+80h+OriginName]; OriginName
0x180082655  lea     rax, [rbp+80h+var_88]
0x180082659  xor     r9d, r9d; AuthenticationPackage
0x18008265c  mov     [rsp+180h+Quotas], rax; Quotas
0x180082661  lea     rax, [rbp+80h+var_C8]
0x180082665  mov     [rsp+180h+Token], rax; Token
0x18008266a  lea     rax, [rbp+80h+var_A0]
0x18008266e  mov     [rsp+180h+LogonId], rax; LogonId
0x180082673  lea     rax, [rbp+80h+var_F8]
0x180082677  mov     [rsp+180h+ProfileBufferLength], rax; ProfileBufferLength
0x18008267c  lea     r8d, [r9+3]; LogonType
0x180082680  lea     rax, [rbp+80h+var_B8]
0x180082684  mov     [rsp+180h+ProfileBuffer], rax; ProfileBuffer
0x180082689  lea     rax, [rbp+80h+var_98]
0x18008268d  mov     [rsp+180h+SourceContext], rax; SourceContext
0x180082692  mov     eax, [rsp+180h+var_110]
0x180082696  mov     [rsp+180h+LocalGroups], r13; LocalGroups
0x18008269b  mov     [rsp+180h+AuthenticationInformationLength], eax; AuthenticationInformationLength
0x18008269f  mov     [rsp+180h+AuthenticationInformation], rsi; AuthenticationInformation
0x1800826a4  call    cs:__imp_LsaLogonUser
0x1800826ab  nop     dword ptr [rax+rax+00h]
0x1800826b0  mov     edx, eax
0x1800826b2  test    eax, eax
0x1800826b4  jns     short loc_1800826E1
0x1800826b6  mov     ecx, cs:dword_1800DF020
0x1800826bc  cmp     ecx, 2
0x1800826bf  jbe     loc_18008275B
0x1800826c5  mov     dword ptr [rsp+180h+var_108], eax
0x1800826c9  lea     rdx, byte_1800CCD83
0x1800826d0  lea     rax, aLogonuserAndLs; "LogonUser and LsaLogonuser with NGC cer"...
0x1800826d7  mov     [rsp+180h+var_10C], 80004005h
0x1800826df  jmp     short loc_180082702
0x1800826e1  mov     eax, cs:dword_1800DF020
0x1800826e7  cmp     eax, 4
0x1800826ea  jbe     short loc_18008275B
0x1800826ec  mov     dword ptr [rsp+180h+var_108], edx
0x1800826f0  lea     rax, aLsalogonuserWi; "LsaLogonuser with NGC was successful"
0x1800826f7  lea     rdx, byte_1800CCD4D
0x1800826fe  mov     [rsp+180h+var_10C], ebx
0x180082702  mov     [rbp+80h+var_100], rax
0x180082706  lea     rax, [rsp+180h+var_108]
0x18008270b  mov     [rsp+180h+LocalGroups], rax
0x180082710  lea     rax, [rsp+180h+var_10C]
0x180082715  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x18008271a  lea     rax, [rbp+80h+var_100]
0x18008271e  mov     [rsp+180h+AuthenticationInformation], rax
0x180082723  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180082728  jmp     short loc_18008275B
0x18008272a  cmp     eax, 4
0x18008272d  jbe     short loc_18008275B
0x18008272f  lea     rax, aLegacyCallToLo_0; "Legacy call to LogonUserExExW failed. N"...
0x180082736  mov     [rbp+80h+var_F8], ebx
0x180082739  mov     [rbp+80h+var_B8], rax
0x18008273d  lea     rdx, word_1800CCD22
0x180082744  lea     rax, [rbp+80h+var_F8]
0x180082748  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x18008274d  lea     rax, [rbp+80h+var_B8]
0x180082751  mov     [rsp+180h+AuthenticationInformation], rax
0x180082756  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008275b  lea     rdx, [rbp+80h+Pid]; Pid
0x18008275f  xor     ecx, ecx; Binding
0x180082761  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180082768  nop     dword ptr [rax+rax+00h]
0x18008276d  test    eax, eax
0x18008276f  jz      short loc_1800827CE
0x180082771  call    cs:__imp_GetLastError
0x180082778  nop     dword ptr [rax+rax+00h]
0x18008277d  mov     ebx, eax
0x18008277f  test    eax, eax
0x180082781  jle     short loc_18008278C
0x180082783  movzx   ebx, ax
0x180082786  or      ebx, 80070000h
0x18008278c  mov     eax, cs:dword_1800DF020
0x180082792  cmp     eax, 3
0x180082795  jbe     loc_180082864
0x18008279b  lea     rax, aIRpcbindinginq_0; "I_RpcBindingInqLocalClientPID failed"
0x1800827a2  mov     dword ptr [rsp+180h+var_108], ebx
0x1800827a6  mov     [rbp+80h+var_100], rax
0x1800827aa  lea     rdx, byte_1800CCCF7
0x1800827b1  lea     rax, [rsp+180h+var_108]
0x1800827b6  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x1800827bb  lea     rax, [rbp+80h+var_100]
0x1800827bf  mov     [rsp+180h+AuthenticationInformation], rax
0x1800827c4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800827c9  jmp     loc_180082864
0x1800827ce  mov     rax, [r15]
0x1800827d1  mov     ebx, [rbp+80h+Pid]
0x1800827d4  mov     rdi, [rax+18h]
0x1800827d8  call    cs:__imp_GetCurrentProcessId
0x1800827df  nop     dword ptr [rax+rax+00h]
0x1800827e4  mov     rdx, [rbp+80h+var_C8]
0x1800827e8  mov     r9, r12
0x1800827eb  mov     r8d, eax
0x1800827ee  mov     dword ptr [rsp+180h+AuthenticationInformation], ebx
0x1800827f2  mov     rax, rdi
0x1800827f5  mov     rcx, r15
0x1800827f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800827fd  mov     ebx, eax
0x1800827ff  test    eax, eax
0x180082801  jns     short loc_180082864
0x180082803  mov     eax, cs:dword_1800DF020
0x180082809  cmp     eax, 3
0x18008280c  jbe     short loc_180082864
0x18008280e  lea     rax, aValidatelogonc; "ValidateLogonCert"
0x180082815  mov     dword ptr [rsp+180h+var_108], ebx
0x180082819  mov     [rbp+80h+var_100], rax
0x18008281d  lea     rdx, byte_1800CCCB7
0x180082824  lea     rax, aDuplicatehandl_1; "DuplicateHandleInPid"
0x18008282b  mov     [rbp+80h+var_D8], rax
0x18008282f  lea     rax, aWarningHresult; "Warning HResult failed"
  ... truncated ...
```
