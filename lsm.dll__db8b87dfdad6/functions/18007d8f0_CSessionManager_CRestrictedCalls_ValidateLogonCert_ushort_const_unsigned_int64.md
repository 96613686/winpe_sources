# CSessionManager::CRestrictedCalls::ValidateLogonCert(ushort const *,unsigned __int64 *)

- ea: `0x18007d8f0`
- end: `0x18007debf`
- name: `?ValidateLogonCert@CRestrictedCalls@CSessionManager@@UEAAJPEBGPEA_K@Z`
- size: `1487`
- prototype: `__int64 __fastcall(CSessionManager::CRestrictedCalls *__hidden this, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task`

## callees

- `0x180001b80`
- `0x1800031c4`
- `0x180003308`
- `0x180024ce0`
- `0x180025890`
- `0x18004b460`
- `0x18004b830`
- `0x18004b910`
- `0x18007d13c`
- `0x18007d5c8`
- `0x18007d8f0`
- `0x180097010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18007da47`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18007da47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d97e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dd4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d97e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007dd4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007ddae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007ddae`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18007dd43`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18007dd43`
- `SspiCli!LogonUserExExW` at `0x18007d970`
- `SspiCli!LogonUserExExW` at `0x18007d970`
- `SspiCli!LsaLogonUser` at `0x18007dc8c`
- `SspiCli!LsaLogonUser` at `0x18007dc8c`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18007de3d`
- `SspiCli!LsaDeregisterLogonProcess` at `0x18007de3d`
- `SspiCli!LsaConnectUntrusted` at `0x18007db82`
- `SspiCli!LsaConnectUntrusted` at `0x18007db82`

## string_xrefs

- `0x18007d9db`: `Terminal Services API`
- `0x18007d9ab`: `Legacy call to LogonUserExExW failed. Attempting LsaLogonuser.`

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
  __int16 *v27; // rdx
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
  if ( !(unsigned int)LogonUserExExW(a2, &qword_1800A3968, &qword_1800A3968, 3, 0, 0, &Token, 0, 0, 0, 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( !(unsigned int)IsNGCValidationEnabled() )
    {
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        ProfileBufferLength = v9;
        ProfileBuffer = "Legacy call to LogonUserExExW failed. New NGC Validation is disabled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v10,
          (unsigned int)&unk_1800C7BD0,
          v11,
          v12,
          (__int64)&ProfileBuffer,
          (__int64)&ProfileBufferLength);
      }
      goto LABEL_24;
    }
    if ( (unsigned int)dword_1800DA020 > 4 )
    {
      AuthenticationInformationLength = v9;
      v45 = "Legacy call to LogonUserExExW failed. Attempting LsaLogonuser.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&unk_1800C7D20,
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
    if ( LogonBlobForCertValidation < 0 && (unsigned int)dword_1800DA020 > 3 )
    {
      v44 = LogonBlobForCertValidation;
      v45 = "ValidateLogonCert";
      v50 = "GetLogonBlobForCertValidation failed when telling us how big of a buffer.";
      v48 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        dword_1800DA020,
        (unsigned int)&unk_1800C7CE0,
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
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        v50 = "ValidateLogonCert";
        v48 = "GetLogonBlobForCertValidation failed after allocating buffer";
        v44 = 320;
        v45 = "clientcore\\termsrv\\newsvc\\core\\restrictedcalls.cpp";
        v51 = "Error HResult failed";
        AuthenticationInformationLength = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          dword_1800DA020,
          (unsigned int)&word_1800C7C8E,
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
      if ( (unsigned int)dword_1800DA020 > 2 )
      {
        v44 = v20;
        v48 = "ValidateLogonCert";
        v51 = "LsaConnectUntrusted failed";
        v50 = "clientcore\\termsrv\\newsvc\\core\\restrictedcalls.cpp";
        v46 = "Error HResult failed";
        AuthenticationInformationLength = 326;
        LODWORD(v45) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_1800DA020,
          (unsigned int)byte_1800C7BFB,
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
      if ( (unsigned int)dword_1800DA020 <= 4 )
        goto LABEL_24;
      LODWORD(v45) = v23;
      v28 = "LsaLogonuser with NGC was successful";
      v27 = word_1800C7B9A;
      v44 = v17;
    }
    else
    {
      v24 = dword_1800DA020;
      if ( (unsigned int)dword_1800DA020 <= 2 )
        goto LABEL_24;
      LODWORD(v45) = v23;
      v27 = (__int16 *)&unk_1800C7C58;
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
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      LODWORD(v45) = v17;
      v46 = "I_RpcBindingInqLocalClientPID failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)&byte_1800C7B2F,
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
    if ( v17 < 0 && (unsigned int)dword_1800DA020 > 3 )
    {
      LODWORD(v45) = v17;
      v46 = "ValidateLogonCert";
      v51 = "DuplicateHandleInPid";
      v48 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v36,
        (unsigned int)word_1800C7B5A,
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
    if ( (unsigned int)dword_1800DA020 > 3 )
    {
      LODWORD(v45) = v39;
      v46 = "LsaDeregisterLogonProcess failed, leaked handle?";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1800DA020,
        (unsigned int)&byte_1800C7AFF,
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
0x18007d8f0  mov     [rsp-8+arg_18], rbx
0x18007d8f5  push    rbp
0x18007d8f6  push    rsi
0x18007d8f7  push    rdi
0x18007d8f8  push    r12
0x18007d8fa  push    r13
0x18007d8fc  push    r14
0x18007d8fe  push    r15
0x18007d900  lea     rbp, [rsp-50h]
0x18007d905  sub     rsp, 150h
0x18007d90c  mov     rax, cs:__security_cookie
0x18007d913  xor     rax, rsp
0x18007d916  mov     [rbp+80h+var_40], rax
0x18007d91a  xor     r13d, r13d
0x18007d91d  lea     rax, [rbp+80h+var_C8]
0x18007d921  mov     [rsp+180h+LogonId], r13
0x18007d926  mov     rdi, rdx
0x18007d929  mov     [rsp+180h+ProfileBufferLength], r13
0x18007d92e  lea     rdx, qword_1800A3968
0x18007d935  mov     [rsp+180h+ProfileBuffer], r13
0x18007d93a  mov     r12, r8
0x18007d93d  mov     [rsp+180h+SourceContext], r13
0x18007d942  lea     r9d, [r13+3]
0x18007d946  mov     [rsp+180h+LocalGroups], rax
0x18007d94b  mov     r15, rcx
0x18007d94e  mov     qword ptr [rsp+180h+AuthenticationInformationLength], r13
0x18007d953  mov     r8, rdx
0x18007d956  mov     rcx, rdi
0x18007d959  mov     dword ptr [rsp+180h+AuthenticationInformation], r13d
0x18007d95e  mov     [rbp+80h+Pid], r13d
0x18007d962  mov     r14d, r13d
0x18007d965  mov     [rbp+80h+var_C8], r13
0x18007d969  mov     esi, r13d
0x18007d96c  mov     [rbp+80h+LsaHandle], r13
0x18007d970  call    cs:__imp_LogonUserExExW
0x18007d976  test    eax, eax
0x18007d978  jnz     loc_18007DD3D
0x18007d97e  call    cs:__imp_GetLastError
0x18007d984  mov     ebx, eax
0x18007d986  test    eax, eax
0x18007d988  jle     short loc_18007D993
0x18007d98a  movzx   ebx, ax
0x18007d98d  or      ebx, 80070000h
0x18007d993  call    ?IsNGCValidationEnabled@@YAHXZ; IsNGCValidationEnabled(void)
0x18007d998  test    eax, eax
0x18007d99a  mov     eax, cs:dword_1800DA020
0x18007d9a0  jz      loc_18007DD0C
0x18007d9a6  cmp     eax, 4
0x18007d9a9  jbe     short loc_18007D9DB
0x18007d9ab  lea     rax, aLegacyCallToLo; "Legacy call to LogonUserExExW failed. A"...
0x18007d9b2  mov     [rsp+180h+var_110], ebx
0x18007d9b6  mov     [rsp+180h+var_108], rax
0x18007d9bb  lea     rdx, unk_1800C7D20
0x18007d9c2  lea     rax, [rsp+180h+var_110]
0x18007d9c7  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x18007d9cc  lea     rax, [rsp+180h+var_108]
0x18007d9d1  mov     [rsp+180h+AuthenticationInformation], rax
0x18007d9d6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007d9db  movups  xmm0, xmmword ptr cs:aTerminalServic_1; "Terminal Services API"
0x18007d9e2  lea     rax, [rbp+80h+var_58]
0x18007d9e6  mov     ecx, 208h; unsigned __int64
0x18007d9eb  movsd   xmm1, qword ptr cs:aTerminalServic_1+0Eh; "ces API"
0x18007d9f3  movups  xmmword ptr [rbp+80h+var_58], xmm0
0x18007d9f7  mov     [rsp+180h+var_110], r13d
0x18007d9fc  xorps   xmm0, xmm0
0x18007d9ff  movsd   qword ptr [rbp+80h+var_58+0Eh], xmm1
0x18007da04  movups  xmmword ptr [rbp+80h+var_98.SourceName], xmm0
0x18007da08  mov     qword ptr [rbp+80h+OriginName.Length], 160016h
0x18007da10  movups  xmmword ptr [rbp+80h+var_88.PagedPoolLimit], xmm0
0x18007da14  mov     [rbp+80h+OriginName.Buffer], rax
0x18007da18  movups  xmmword ptr [rbp+80h+var_88.MinimumWorkingSetSize], xmm0
0x18007da1c  mov     [rbp+80h+var_B8], r13
0x18007da20  movups  xmmword ptr [rbp+80h+var_88.PagefileLimit], xmm0
0x18007da24  mov     [rbp+80h+var_F8], r13d
0x18007da28  mov     qword ptr [rbp+80h+var_A0.LowPart], r13
0x18007da2c  mov     [rbp+80h+var_D0], r13d
0x18007da30  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007da35  or      r9, 0FFFFFFFFFFFFFFFFh
0x18007da39  mov     r8, rdi
0x18007da3c  mov     edx, 104h
0x18007da41  mov     rcx, rax
0x18007da44  mov     r14, rax
0x18007da47  call    cs:__imp__o_wcsncpy_s
0x18007da4d  xor     r8d, r8d; unsigned __int8 *
0x18007da50  lea     rdx, [rsp+180h+var_110]; unsigned int *
0x18007da55  mov     rcx, r14; unsigned __int16 *
0x18007da58  call    ?GetLogonBlobForCertValidation@@YAJPEAGPEAKPEAE@Z; GetLogonBlobForCertValidation(ushort *,ulong *,uchar *)
0x18007da5d  test    eax, eax
0x18007da5f  jns     short loc_18007DAC6
0x18007da61  mov     ecx, cs:dword_1800DA020
0x18007da67  cmp     ecx, 3
0x18007da6a  jbe     short loc_18007DAC6
0x18007da6c  mov     [rsp+180h+var_10C], eax
0x18007da70  lea     rdi, aValidatelogonc; "ValidateLogonCert"
0x18007da77  lea     rax, aGetlogonblobfo; "GetLogonBlobForCertValidation failed wh"...
0x18007da7e  mov     [rsp+180h+var_108], rdi
0x18007da83  mov     [rbp+80h+var_E0], rax
0x18007da87  lea     rdx, unk_1800C7CE0
0x18007da8e  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18007da95  mov     [rbp+80h+var_F0], rax
0x18007da99  lea     rax, [rsp+180h+var_108]
0x18007da9e  mov     [rsp+180h+SourceContext], rax
0x18007daa3  lea     rax, [rsp+180h+var_10C]
0x18007daa8  mov     [rsp+180h+LocalGroups], rax
0x18007daad  lea     rax, [rbp+80h+var_E0]
0x18007dab1  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x18007dab6  lea     rax, [rbp+80h+var_F0]
0x18007daba  mov     [rsp+180h+AuthenticationInformation], rax
0x18007dabf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18007dac4  jmp     short loc_18007DACD
0x18007dac6  lea     rdi, aValidatelogonc; "ValidateLogonCert"
0x18007dacd  mov     ecx, [rsp+180h+var_110]; unsigned __int64
0x18007dad1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007dad6  mov     r8, rax; unsigned __int8 *
0x18007dad9  lea     rdx, [rsp+180h+var_110]; unsigned int *
0x18007dade  mov     rcx, r14; unsigned __int16 *
0x18007dae1  mov     rsi, rax
0x18007dae4  call    ?GetLogonBlobForCertValidation@@YAJPEAGPEAKPEAE@Z; GetLogonBlobForCertValidation(ushort *,ulong *,uchar *)
0x18007dae9  mov     ebx, eax
0x18007daeb  test    eax, eax
0x18007daed  jns     loc_18007DB7E
0x18007daf3  mov     ecx, cs:dword_1800DA020
0x18007daf9  cmp     ecx, 2
0x18007dafc  jbe     loc_18007DE34
0x18007db02  lea     rax, aGetlogonblobfo_0; "GetLogonBlobForCertValidation failed af"...
0x18007db09  mov     [rbp+80h+var_E0], rdi
0x18007db0d  mov     [rbp+80h+var_F0], rax
0x18007db11  lea     rdx, word_1800C7C8E
0x18007db18  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\newsvc\\core\\rest"...
0x18007db1f  mov     [rsp+180h+var_10C], 140h
0x18007db27  mov     [rsp+180h+var_108], rax
0x18007db2c  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007db33  mov     [rbp+80h+var_D8], rax
0x18007db37  lea     rax, [rbp+80h+var_F0]
0x18007db3b  mov     [rsp+180h+ProfileBufferLength], rax
0x18007db40  lea     rax, [rbp+80h+var_E0]
0x18007db44  mov     [rsp+180h+ProfileBuffer], rax
0x18007db49  lea     rax, [rsp+180h+var_10C]
0x18007db4e  mov     [rsp+180h+SourceContext], rax
0x18007db53  lea     rax, [rsp+180h+var_108]
0x18007db58  mov     [rsp+180h+LocalGroups], rax
0x18007db5d  lea     rax, [rsp+180h+var_110]
0x18007db62  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x18007db67  lea     rax, [rbp+80h+var_D8]
0x18007db6b  mov     [rsp+180h+AuthenticationInformation], rax
0x18007db70  mov     [rsp+180h+var_110], ebx
0x18007db74  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007db79  jmp     loc_18007DE34
0x18007db7e  lea     rcx, [rbp+80h+LsaHandle]; LsaHandle
0x18007db82  call    cs:__imp_LsaConnectUntrusted
0x18007db88  test    eax, eax
0x18007db8a  jns     loc_18007DC2C
0x18007db90  mov     ecx, cs:dword_1800DA020
0x18007db96  mov     ebx, 80004005h
0x18007db9b  cmp     ecx, 2
0x18007db9e  jbe     loc_18007DE34
0x18007dba4  mov     [rsp+180h+var_10C], eax
0x18007dba8  lea     rdx, byte_1800C7BFB
0x18007dbaf  lea     rax, aLsaconnectuntr_0; "LsaConnectUntrusted failed"
0x18007dbb6  mov     [rbp+80h+var_F0], rdi
0x18007dbba  mov     [rbp+80h+var_D8], rax
0x18007dbbe  lea     rax, aClientcoreTerm_2; "clientcore\\termsrv\\newsvc\\core\\rest"...
0x18007dbc5  mov     [rbp+80h+var_E0], rax
0x18007dbc9  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18007dbd0  mov     [rbp+80h+var_100], rax
0x18007dbd4  lea     rax, [rsp+180h+var_10C]
0x18007dbd9  mov     [rsp+180h+LogonId], rax
0x18007dbde  lea     rax, [rbp+80h+var_D8]
0x18007dbe2  mov     [rsp+180h+ProfileBufferLength], rax
0x18007dbe7  lea     rax, [rbp+80h+var_F0]
0x18007dbeb  mov     [rsp+180h+ProfileBuffer], rax
0x18007dbf0  lea     rax, [rsp+180h+var_110]
0x18007dbf5  mov     [rsp+180h+SourceContext], rax
0x18007dbfa  lea     rax, [rbp+80h+var_E0]
0x18007dbfe  mov     [rsp+180h+LocalGroups], rax
0x18007dc03  lea     rax, [rsp+180h+var_108]
0x18007dc08  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x18007dc0d  lea     rax, [rbp+80h+var_100]
0x18007dc11  mov     [rsp+180h+AuthenticationInformation], rax
0x18007dc16  mov     [rsp+180h+var_110], 146h
0x18007dc1e  mov     dword ptr [rsp+180h+var_108], ebx
0x18007dc22  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007dc27  jmp     loc_18007DE34
0x18007dc2c  mov     rcx, [rbp+80h+LsaHandle]; LsaHandle
0x18007dc30  lea     rax, [rbp+80h+var_D0]
0x18007dc34  mov     [rsp+180h+SubStatus], rax; SubStatus
0x18007dc39  lea     rdx, [rbp+80h+OriginName]; OriginName
0x18007dc3d  lea     rax, [rbp+80h+var_88]
0x18007dc41  xor     r9d, r9d; AuthenticationPackage
0x18007dc44  mov     [rsp+180h+Quotas], rax; Quotas
0x18007dc49  lea     rax, [rbp+80h+var_C8]
0x18007dc4d  mov     [rsp+180h+Token], rax; Token
0x18007dc52  lea     rax, [rbp+80h+var_A0]
0x18007dc56  mov     [rsp+180h+LogonId], rax; LogonId
0x18007dc5b  lea     rax, [rbp+80h+var_F8]
0x18007dc5f  mov     [rsp+180h+ProfileBufferLength], rax; ProfileBufferLength
0x18007dc64  lea     r8d, [r9+3]; LogonType
0x18007dc68  lea     rax, [rbp+80h+var_B8]
0x18007dc6c  mov     [rsp+180h+ProfileBuffer], rax; ProfileBuffer
0x18007dc71  lea     rax, [rbp+80h+var_98]
0x18007dc75  mov     [rsp+180h+SourceContext], rax; SourceContext
0x18007dc7a  mov     eax, [rsp+180h+var_110]
0x18007dc7e  mov     [rsp+180h+LocalGroups], r13; LocalGroups
0x18007dc83  mov     [rsp+180h+AuthenticationInformationLength], eax; AuthenticationInformationLength
0x18007dc87  mov     [rsp+180h+AuthenticationInformation], rsi; AuthenticationInformation
0x18007dc8c  call    cs:__imp_LsaLogonUser
0x18007dc92  mov     edx, eax
0x18007dc94  test    eax, eax
0x18007dc96  jns     short loc_18007DCC3
0x18007dc98  mov     ecx, cs:dword_1800DA020
0x18007dc9e  cmp     ecx, 2
0x18007dca1  jbe     loc_18007DD3D
0x18007dca7  mov     dword ptr [rsp+180h+var_108], eax
0x18007dcab  lea     rdx, unk_1800C7C58
0x18007dcb2  lea     rax, aLogonuserAndLs; "LogonUser and LsaLogonuser with NGC cer"...
0x18007dcb9  mov     [rsp+180h+var_10C], 80004005h
0x18007dcc1  jmp     short loc_18007DCE4
0x18007dcc3  mov     eax, cs:dword_1800DA020
0x18007dcc9  cmp     eax, 4
0x18007dccc  jbe     short loc_18007DD3D
0x18007dcce  mov     dword ptr [rsp+180h+var_108], edx
0x18007dcd2  lea     rax, aLsalogonuserWi; "LsaLogonuser with NGC was successful"
0x18007dcd9  lea     rdx, word_1800C7B9A
0x18007dce0  mov     [rsp+180h+var_10C], ebx
0x18007dce4  mov     [rbp+80h+var_100], rax
0x18007dce8  lea     rax, [rsp+180h+var_108]
0x18007dced  mov     [rsp+180h+LocalGroups], rax
0x18007dcf2  lea     rax, [rsp+180h+var_10C]
0x18007dcf7  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x18007dcfc  lea     rax, [rbp+80h+var_100]
0x18007dd00  mov     [rsp+180h+AuthenticationInformation], rax
0x18007dd05  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007dd0a  jmp     short loc_18007DD3D
0x18007dd0c  cmp     eax, 4
0x18007dd0f  jbe     short loc_18007DD3D
0x18007dd11  lea     rax, aLegacyCallToLo_0; "Legacy call to LogonUserExExW failed. N"...
0x18007dd18  mov     [rbp+80h+var_F8], ebx
0x18007dd1b  mov     [rbp+80h+var_B8], rax
0x18007dd1f  lea     rdx, unk_1800C7BD0
0x18007dd26  lea     rax, [rbp+80h+var_F8]
0x18007dd2a  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x18007dd2f  lea     rax, [rbp+80h+var_B8]
0x18007dd33  mov     [rsp+180h+AuthenticationInformation], rax
0x18007dd38  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007dd3d  lea     rdx, [rbp+80h+Pid]; Pid
0x18007dd41  xor     ecx, ecx; Binding
0x18007dd43  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18007dd49  test    eax, eax
0x18007dd4b  jz      short loc_18007DDA4
0x18007dd4d  call    cs:__imp_GetLastError
0x18007dd53  mov     ebx, eax
0x18007dd55  test    eax, eax
0x18007dd57  jle     short loc_18007DD62
0x18007dd59  movzx   ebx, ax
0x18007dd5c  or      ebx, 80070000h
0x18007dd62  mov     eax, cs:dword_1800DA020
0x18007dd68  cmp     eax, 3
0x18007dd6b  jbe     loc_18007DE34
0x18007dd71  lea     rax, aIRpcbindinginq_0; "I_RpcBindingInqLocalClientPID failed"
0x18007dd78  mov     dword ptr [rsp+180h+var_108], ebx
0x18007dd7c  mov     [rbp+80h+var_100], rax
0x18007dd80  lea     rdx, byte_1800C7B2F
0x18007dd87  lea     rax, [rsp+180h+var_108]
0x18007dd8c  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x18007dd91  lea     rax, [rbp+80h+var_100]
0x18007dd95  mov     [rsp+180h+AuthenticationInformation], rax
0x18007dd9a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007dd9f  jmp     loc_18007DE34
0x18007dda4  mov     rax, [r15]
0x18007dda7  mov     ebx, [rbp+80h+Pid]
0x18007ddaa  mov     rdi, [rax+18h]
0x18007ddae  call    cs:__imp_GetCurrentProcessId
0x18007ddb4  mov     rdx, [rbp+80h+var_C8]
0x18007ddb8  mov     r9, r12
0x18007ddbb  mov     r8d, eax
0x18007ddbe  mov     dword ptr [rsp+180h+AuthenticationInformation], ebx
0x18007ddc2  mov     rax, rdi
0x18007ddc5  mov     rcx, r15
0x18007ddc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ddcd  mov     ebx, eax
0x18007ddcf  test    eax, eax
0x18007ddd1  jns     short loc_18007DE34
0x18007ddd3  mov     eax, cs:dword_1800DA020
0x18007ddd9  cmp     eax, 3
0x18007dddc  jbe     short loc_18007DE34
0x18007ddde  lea     rax, aValidatelogonc; "ValidateLogonCert"
0x18007dde5  mov     dword ptr [rsp+180h+var_108], ebx
0x18007dde9  mov     [rbp+80h+var_100], rax
0x18007dded  lea     rdx, word_1800C7B5A
0x18007ddf4  lea     rax, aDuplicatehandl_1; "DuplicateHandleInPid"
0x18007ddfb  mov     [rbp+80h+var_D8], rax
0x18007ddff  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007de06  mov     [rbp+80h+var_F0], rax
0x18007de0a  lea     rax, [rbp+80h+var_100]
0x18007de0e  mov     [rsp+180h+SourceContext], rax
0x18007de13  lea     rax, [rsp+180h+var_108]
0x18007de18  mov     [rsp+180h+LocalGroups], rax
0x18007de1d  lea     rax, [rbp+80h+var_D8]
0x18007de21  mov     qword ptr [rsp+180h+AuthenticationInformationLength], rax
0x18007de26  lea     rax, [rbp+80h+var_F0]
  ... truncated ...
```
