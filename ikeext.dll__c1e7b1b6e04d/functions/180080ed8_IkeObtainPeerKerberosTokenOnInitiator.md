# IkeObtainPeerKerberosTokenOnInitiator

- ea: `0x180080ed8`
- end: `0x180081571`
- name: `IkeObtainPeerKerberosTokenOnInitiator`
- size: `1689`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007ed08`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x1800061ec`
- `0x180008388`
- `0x180016534`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x18007f120`
- `0x1800809dc`
- `0x180080ed8`
- `0x180081578`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800811d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800811d2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800811e4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800811e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800811ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800812e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800811ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800812e7`
- `ntdll!RtlInitString` at `0x1800810f2`
- `ntdll!RtlInitString` at `0x1800810f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008152b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008152b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800812dd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800812dd`
- `SspiCli!LsaFreeReturnBuffer` at `0x180081433`
- `SspiCli!LsaFreeReturnBuffer` at `0x180081433`
- `SspiCli!LsaLogonUser` at `0x18008141e`
- `SspiCli!LsaLogonUser` at `0x18008141e`

## string_xrefs

- `0x1800812ed`: `GetTokenInformation`
- `0x1800811f4`: `OpenProcessToken`
- `0x18008100d`: `Ignoring initiator kerb token generation`
- `0x180080f1e`: `IkeObtainPeerKerberosTokenOnInitiator`
- `0x180081533`: `IkeObtainPeerKerberosTokenOnInitiator`
- `0x18008153f`: `IkeObtainPeerKerberosTokenOnInitiator`
- `0x1800810db`: `Can't obtain peer Kerberos token when using proxy`
- `0x18008128b`: `Calling GetTokenInformation`
- `0x18008119b`: `Calling OpenProcessToken`
- `0x1800814dc`: `Returning from IkeObtainPeerKerberosTokenOnInitiator`

## pseudocode

```c
__int64 __fastcall IkeObtainPeerKerberosTokenOnInitiator(__int64 a1, __int64 a2, void **a3)
{
  __int64 PolicyFromSspi; // r14
  _BYTE *v6; // rcx
  __int64 v7; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v9; // rcx
  int TlsMmLuid; // eax
  __int64 v11; // rcx
  const WCHAR *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  char *v15; // rdx
  const char *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rdi
  __int64 v19; // rbx
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  const WCHAR *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  PVOID v26; // r13
  __int64 v27; // rdi
  __int64 v28; // rbx
  __int64 v29; // rcx
  int v30; // eax
  __int64 v31; // rcx
  const WCHAR *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  HANDLE CurrentProcess; // rax
  __int64 v36; // rcx
  DWORD LastError; // eax
  __int64 v38; // rcx
  const char *v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 v42; // rbx
  __int64 v43; // rcx
  int v44; // eax
  __int64 v45; // rcx
  const WCHAR *v46; // rax
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rcx
  __int64 v50; // rdi
  __int64 v51; // rbx
  __int64 v52; // rcx
  int v53; // eax
  __int64 v54; // rcx
  const WCHAR *v55; // rax
  __int64 v56; // r8
  __int64 v57; // r9
  PVOID v58; // rcx
  NTSTATUS v59; // ebx
  __int64 v60; // r8
  __int64 v61; // rdi
  __int64 v62; // rbx
  __int64 v63; // rcx
  int v64; // eax
  __int64 v65; // rcx
  const WCHAR *v66; // rax
  __int64 v67; // r8
  __int64 v68; // r9
  ULONG AuthenticationInformationLength; // [rsp+70h] [rbp-90h] BYREF
  PVOID AuthenticationInformation; // [rsp+78h] [rbp-88h] BYREF
  int SubStatus; // [rsp+80h] [rbp-80h] BYREF
  PVOID Buffer; // [rsp+88h] [rbp-78h] BYREF
  void *TokenHandle; // [rsp+90h] [rbp-70h] BYREF
  _BYTE *v75; // [rsp+98h] [rbp-68h] BYREF
  DWORD ReturnLength; // [rsp+A0h] [rbp-60h] BYREF
  ULONG ProfileBufferLength; // [rsp+A4h] [rbp-5Ch] BYREF
  PHANDLE Token; // [rsp+A8h] [rbp-58h] BYREF
  struct _LUID LogonId; // [rsp+B0h] [rbp-50h] BYREF
  struct _TOKEN_SOURCE TokenInformation; // [rsp+B8h] [rbp-48h] BYREF
  _STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v83[32]; // [rsp+110h] [rbp+10h] BYREF
  PHANDLE *p_Token; // [rsp+130h] [rbp+30h]
  __int64 v85; // [rsp+138h] [rbp+38h]
  _BYTE v86[16]; // [rsp+140h] [rbp+40h] BYREF
  const char *v87; // [rsp+150h] [rbp+50h]
  __int64 v88; // [rsp+158h] [rbp+58h]

  Token = a3;
  Buffer = 0;
  ProfileBufferLength = 0;
  LogonId = 0;
  SubStatus = 0;
  AuthenticationInformation = 0;
  DestinationString = 0;
  AuthenticationInformationLength = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  TokenHandle = 0;
  ReturnLength = 0;
  v75 = 0;
  TokenInformation = 0;
  TraceLogHelper("IkeObtainPeerKerberosTokenOnInitiator", 1);
  PolicyFromSspi = IkeGetPolicyFromSspi(a1, a2, &v75);
  if ( PolicyFromSspi )
    goto LABEL_57;
  v6 = v75;
  if ( (*v75 & 1) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v75);
      TlsMmLuid = IkeGetTlsMmLuid(v9);
      WPP_SF_iS(v7, 73, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v75 = (_BYTE *)IkeGetTlsMmLuid(v6);
      p_Token = (PHANDLE *)&v75;
      v85 = 8;
      v12 = (const WCHAR *)IkeGetTlsPeerAddr(v11);
      tlgCreate1Sz_wchar_t((__int64)v86, v12);
      v15 = byte_180154EA3;
      v88 = 41;
      v16 = "Ignoring initiator kerb token generation";
LABEL_9:
      v87 = v16;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)v15,
        v13,
        v14,
        5,
        (__int64)v83);
      goto LABEL_57;
    }
    goto LABEL_57;
  }
  if ( !(unsigned int)IkeIsKerberosAuthUsingProxy(v75) )
  {
    RtlInitString(&DestinationString, "Ike/AuthIP");
    v24 = IkePackS4u(a2, (LPCVOID *)&AuthenticationInformation, &AuthenticationInformationLength);
    v26 = AuthenticationInformation;
    PolicyFromSspi = v24;
    if ( v24 )
      goto LABEL_55;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v27 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v28 = IkeGetTlsPeerAddr(v25);
      v30 = IkeGetTlsMmLuid(v29);
      WPP_SF_iS(v27, 75, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v30, v28);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v75 = (_BYTE *)IkeGetTlsMmLuid(v25);
      p_Token = (PHANDLE *)&v75;
      v85 = 8;
      v32 = (const WCHAR *)IkeGetTlsPeerAddr(v31);
      tlgCreate1Sz_wchar_t((__int64)v86, v32);
      v88 = 25;
      v87 = "Calling OpenProcessToken";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_180154DE9,
        v33,
        v34,
        5,
        (__int64)v83);
    }
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x10u, &TokenHandle) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v41 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v42 = IkeGetTlsPeerAddr(v36);
        v44 = IkeGetTlsMmLuid(v43);
        WPP_SF_iS(v41, 76, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v44, v42);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v75 = (_BYTE *)IkeGetTlsMmLuid(v36);
        p_Token = (PHANDLE *)&v75;
        v85 = 8;
        v46 = (const WCHAR *)IkeGetTlsPeerAddr(v45);
        tlgCreate1Sz_wchar_t((__int64)v86, v46);
        v88 = 28;
        v87 = "Calling GetTokenInformation";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)byte_180154E65,
          v47,
          v48,
          5,
          (__int64)v83);
      }
      if ( GetTokenInformation(TokenHandle, TokenSource, &TokenInformation, 0x10u, &ReturnLength) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v50 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v51 = IkeGetTlsPeerAddr(v49);
          v53 = IkeGetTlsMmLuid(v52);
          WPP_SF_iS(v50, 77, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v53, v51);
        }
        if ( (unsigned int)dword_180173278 > 4 )
        {
          v75 = (_BYTE *)IkeGetTlsMmLuid(v49);
          p_Token = (PHANDLE *)&v75;
          v85 = 8;
          v55 = (const WCHAR *)IkeGetTlsPeerAddr(v54);
          tlgCreate1Sz_wchar_t((__int64)v86, v55);
          v88 = 21;
          v87 = "Calling LsaLogonUser";
          tlgWriteTransfer_EtwEventWriteTransfer(
            (__int64)&dword_180173278,
            (unsigned __int8 *)byte_180154D6D,
            v56,
            v57,
            5,
            (__int64)v83);
        }
        v59 = LsaLogonUser(
                gIkeExtGlobals[74].OwningThread,
                (PLSA_STRING)&DestinationString,
                Network,
                HIDWORD(gIkeExtGlobals[74].LockSemaphore),
                v26,
                AuthenticationInformationLength,
                0,
                &TokenInformation,
                &Buffer,
                &ProfileBufferLength,
                &LogonId,
                Token,
                &Quotas,
                &SubStatus);
        if ( v59 >= 0 )
        {
          v58 = Buffer;
          if ( Buffer )
          {
            LsaFreeReturnBuffer(Buffer);
            Buffer = 0;
          }
        }
        if ( v59 )
        {
          v60 = (unsigned int)v59;
        }
        else
        {
          v60 = (unsigned int)SubStatus;
          if ( !SubStatus )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v61 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v62 = IkeGetTlsPeerAddr(v58);
              v64 = IkeGetTlsMmLuid(v63);
              WPP_SF_iS(v61, 78, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v64, v62);
            }
            if ( (unsigned int)dword_180173278 > 4 )
            {
              Token = (PHANDLE)IkeGetTlsMmLuid(v58);
              p_Token = &Token;
              v85 = 8;
              v66 = (const WCHAR *)IkeGetTlsPeerAddr(v65);
              tlgCreate1Sz_wchar_t((__int64)v86, v66);
              v88 = 53;
              v87 = "Returning from IkeObtainPeerKerberosTokenOnInitiator";
              tlgWriteTransfer_EtwEventWriteTransfer(
                (__int64)&dword_180173278,
                (unsigned __int8 *)byte_180154DAB,
                v67,
                v68,
                5,
                (__int64)v83);
            }
            goto LABEL_55;
          }
        }
        v40 = WfpReportSysErrorAsNtStatus(v58, "LsaLogonUser", v60);
        goto LABEL_27;
      }
      LastError = GetLastError();
      v39 = "GetTokenInformation";
    }
    else
    {
      LastError = GetLastError();
      v39 = "OpenProcessToken";
    }
    v40 = WfpReportSysErrorAsWinError(v38, v39, LastError, 1);
LABEL_27:
    PolicyFromSspi = v40;
LABEL_55:
    if ( v26 )
      WfpMemFree((LPCVOID *)&AuthenticationInformation);
    goto LABEL_57;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v18 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v19 = IkeGetTlsPeerAddr(v17);
    v21 = IkeGetTlsMmLuid(v20);
    WPP_SF_iS(v18, 74, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v21, v19);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v75 = (_BYTE *)IkeGetTlsMmLuid(v17);
    p_Token = (PHANDLE *)&v75;
    v85 = 8;
    v23 = (const WCHAR *)IkeGetTlsPeerAddr(v22);
    tlgCreate1Sz_wchar_t((__int64)v86, v23);
    v15 = &byte_180154E27;
    v88 = 50;
    v16 = "Can't obtain peer Kerberos token when using proxy";
    goto LABEL_9;
  }
LABEL_57:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  TraceLogHelper("IkeObtainPeerKerberosTokenOnInitiator", 0);
  return IkeReturnError(PolicyFromSspi, "IkeObtainPeerKerberosTokenOnInitiator");
}

```

## disassembly

```asm
0x180080ed8  mov     [rsp-8+arg_18], rbx
0x180080edd  push    rbp
0x180080ede  push    rsi
0x180080edf  push    rdi
0x180080ee0  push    r13
0x180080ee2  push    r14
0x180080ee4  lea     rbp, [rsp-70h]
0x180080ee9  sub     rsp, 170h
0x180080ef0  mov     rax, cs:__security_cookie
0x180080ef7  xor     rax, rsp
0x180080efa  mov     [rbp+90h+var_30], rax
0x180080efe  xor     eax, eax
0x180080f00  mov     [rbp+90h+var_E8], r8
0x180080f04  xorps   xmm0, xmm0
0x180080f07  mov     [rbp+90h+Buffer], rax
0x180080f0b  mov     rdi, rdx
0x180080f0e  mov     [rbp+90h+var_EC], eax
0x180080f11  mov     rbx, rcx
0x180080f14  mov     qword ptr [rbp+90h+var_E0.LowPart], rax
0x180080f18  lea     edx, [rax+1]
0x180080f1b  mov     [rbp+90h+var_110], eax
0x180080f1e  lea     rcx, aIkeobtainpeerk; "IkeObtainPeerKerberosTokenOnInitiator"
0x180080f25  mov     [rsp+190h+AuthenticationInformation], rax
0x180080f2a  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x180080f2e  mov     [rsp+190h+var_120], eax
0x180080f32  movups  xmmword ptr [rbp+90h+var_B8.PagedPoolLimit], xmm0
0x180080f36  mov     [rbp+90h+TokenHandle], rax
0x180080f3a  movups  xmmword ptr [rbp+90h+var_B8.MinimumWorkingSetSize], xmm0
0x180080f3e  mov     [rbp+90h+var_F0], eax
0x180080f41  movups  xmmword ptr [rbp+90h+var_B8.PagefileLimit], xmm0
0x180080f45  mov     [rbp+90h+var_F8], rax
0x180080f49  movups  [rbp+90h+TokenInformation], xmm0
0x180080f4d  call    TraceLogHelper
0x180080f52  lea     r8, [rbp+90h+var_F8]
0x180080f56  mov     rdx, rdi
0x180080f59  mov     rcx, rbx
0x180080f5c  call    IkeGetPolicyFromSspi
0x180080f61  mov     r14, rax
0x180080f64  test    rax, rax
0x180080f67  jnz     loc_180081522
0x180080f6d  mov     rcx, [rbp+90h+var_F8]
0x180080f71  test    byte ptr [rcx], 1
0x180080f74  jz      loc_18008103A
0x180080f7a  mov     rdi, cs:WPP_GLOBAL_Control
0x180080f81  lea     rsi, WPP_GLOBAL_Control
0x180080f88  cmp     rdi, rsi
0x180080f8b  jz      short loc_180080FC5
0x180080f8d  cmp     byte ptr [rdi+19h], 4
0x180080f91  jb      short loc_180080FC5
0x180080f93  test    byte ptr [rdi+1Ch], 10h
0x180080f97  jz      short loc_180080FC5
0x180080f99  mov     rdi, [rdi+10h]
0x180080f9d  call    IkeGetTlsPeerAddr
0x180080fa2  mov     rbx, rax
0x180080fa5  call    IkeGetTlsMmLuid
0x180080faa  mov     r9, rax
0x180080fad  mov     [rsp+190h+ReturnLength], rbx
0x180080fb2  lea     edx, [r14+49h]
0x180080fb6  mov     rcx, rdi
0x180080fb9  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180080fc0  call    WPP_SF_iS
0x180080fc5  mov     eax, cs:dword_180173278
0x180080fcb  cmp     eax, 4
0x180080fce  jbe     loc_180081522
0x180080fd4  call    IkeGetTlsMmLuid
0x180080fd9  mov     [rbp+90h+var_F8], rax
0x180080fdd  lea     rax, [rbp+90h+var_F8]
0x180080fe1  mov     [rbp+90h+var_60], rax
0x180080fe5  mov     [rbp+90h+var_58], 8
0x180080fed  call    IkeGetTlsPeerAddr
0x180080ff2  mov     rdx, rax
0x180080ff5  lea     rcx, [rbp+90h+var_50]
0x180080ff9  call    _tlgCreate1Sz_wchar_t
0x180080ffe  lea     rdx, byte_180154EA3
0x180081005  mov     [rbp+90h+var_38], 29h ; ')'
0x18008100d  lea     rcx, aIgnoringInitia; "Ignoring initiator kerb token generatio"...
0x180081014  lea     rax, [rbp+90h+var_80]
0x180081018  mov     [rbp+90h+var_40], rcx
0x18008101c  mov     qword ptr [rsp+190h+AuthenticationInformationLength], rax
0x180081021  lea     rcx, dword_180173278
0x180081028  mov     dword ptr [rsp+190h+ReturnLength], 5
0x180081030  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180081035  jmp     loc_180081522
0x18008103a  call    IkeIsKerberosAuthUsingProxy
0x18008103f  test    eax, eax
0x180081041  jz      loc_1800810E7
0x180081047  mov     rdi, cs:WPP_GLOBAL_Control
0x18008104e  lea     rsi, WPP_GLOBAL_Control
0x180081055  cmp     rdi, rsi
0x180081058  jz      short loc_180081093
0x18008105a  cmp     byte ptr [rdi+19h], 4
0x18008105e  jb      short loc_180081093
0x180081060  test    byte ptr [rdi+1Ch], 10h
0x180081064  jz      short loc_180081093
0x180081066  mov     rdi, [rdi+10h]
0x18008106a  call    IkeGetTlsPeerAddr
0x18008106f  mov     rbx, rax
0x180081072  call    IkeGetTlsMmLuid
0x180081077  mov     r9, rax
0x18008107a  mov     [rsp+190h+ReturnLength], rbx
0x18008107f  mov     edx, 4Ah ; 'J'
0x180081084  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18008108b  mov     rcx, rdi
0x18008108e  call    WPP_SF_iS
0x180081093  mov     eax, cs:dword_180173278
0x180081099  cmp     eax, 4
0x18008109c  jbe     loc_180081522
0x1800810a2  call    IkeGetTlsMmLuid
0x1800810a7  mov     [rbp+90h+var_F8], rax
0x1800810ab  lea     rax, [rbp+90h+var_F8]
0x1800810af  mov     [rbp+90h+var_60], rax
0x1800810b3  mov     [rbp+90h+var_58], 8
0x1800810bb  call    IkeGetTlsPeerAddr
0x1800810c0  mov     rdx, rax
0x1800810c3  lea     rcx, [rbp+90h+var_50]
0x1800810c7  call    _tlgCreate1Sz_wchar_t
0x1800810cc  lea     rdx, byte_180154E27
0x1800810d3  mov     [rbp+90h+var_38], 32h ; '2'
0x1800810db  lea     rcx, aCanTObtainPeer; "Can't obtain peer Kerberos token when u"...
0x1800810e2  jmp     loc_180081014
0x1800810e7  lea     rdx, SourceString; "Ike/AuthIP"
0x1800810ee  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x1800810f2  call    cs:__imp_RtlInitString
0x1800810f8  lea     r8, [rsp+190h+var_120]
0x1800810fd  mov     rcx, rdi
0x180081100  lea     rdx, [rsp+190h+AuthenticationInformation]
0x180081105  call    IkePackS4u
0x18008110a  mov     r13, [rsp+190h+AuthenticationInformation]
0x18008110f  mov     r14, rax
0x180081112  test    rax, rax
0x180081115  jnz     loc_180081513
0x18008111b  mov     rdi, cs:WPP_GLOBAL_Control
0x180081122  lea     rsi, WPP_GLOBAL_Control
0x180081129  cmp     rdi, rsi
0x18008112c  jz      short loc_180081166
0x18008112e  cmp     byte ptr [rdi+19h], 4
0x180081132  jb      short loc_180081166
0x180081134  test    byte ptr [rdi+1Ch], 10h
0x180081138  jz      short loc_180081166
0x18008113a  mov     rdi, [rdi+10h]
0x18008113e  call    IkeGetTlsPeerAddr
0x180081143  mov     rbx, rax
0x180081146  call    IkeGetTlsMmLuid
0x18008114b  mov     r9, rax
0x18008114e  mov     [rsp+190h+ReturnLength], rbx
0x180081153  lea     edx, [r14+4Bh]
0x180081157  mov     rcx, rdi
0x18008115a  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180081161  call    WPP_SF_iS
0x180081166  mov     eax, cs:dword_180173278
0x18008116c  cmp     eax, 4
0x18008116f  jbe     short loc_1800811D2
0x180081171  call    IkeGetTlsMmLuid
0x180081176  mov     [rbp+90h+var_F8], rax
0x18008117a  lea     rax, [rbp+90h+var_F8]
0x18008117e  mov     [rbp+90h+var_60], rax
0x180081182  mov     [rbp+90h+var_58], 8
0x18008118a  call    IkeGetTlsPeerAddr
0x18008118f  mov     rdx, rax
0x180081192  lea     rcx, [rbp+90h+var_50]
0x180081196  call    _tlgCreate1Sz_wchar_t
0x18008119b  lea     rcx, aCallingOpenpro; "Calling OpenProcessToken"
0x1800811a2  mov     [rbp+90h+var_38], 19h
0x1800811aa  lea     rax, [rbp+90h+var_80]
0x1800811ae  mov     [rbp+90h+var_40], rcx
0x1800811b2  mov     qword ptr [rsp+190h+AuthenticationInformationLength], rax
0x1800811b7  lea     rcx, dword_180173278
0x1800811be  lea     rdx, byte_180154DE9
0x1800811c5  mov     dword ptr [rsp+190h+ReturnLength], 5
0x1800811cd  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800811d2  call    cs:__imp_GetCurrentProcess
0x1800811d8  lea     r8, [rbp+90h+TokenHandle]; TokenHandle
0x1800811dc  mov     edx, 10h; DesiredAccess
0x1800811e1  mov     rcx, rax; ProcessHandle
0x1800811e4  call    cs:__imp_OpenProcessToken
0x1800811ea  test    eax, eax
0x1800811ec  jnz     short loc_180081211
0x1800811ee  call    cs:__imp_GetLastError
0x1800811f4  lea     rdx, aOpenprocesstok; "OpenProcessToken"
0x1800811fb  mov     r9d, 1
0x180081201  mov     r8d, eax
0x180081204  call    WfpReportSysErrorAsWinError
0x180081209  mov     r14, rax
0x18008120c  jmp     loc_180081513
0x180081211  mov     rdi, cs:WPP_GLOBAL_Control
0x180081218  cmp     rdi, rsi
0x18008121b  jz      short loc_180081256
0x18008121d  cmp     byte ptr [rdi+19h], 4
0x180081221  jb      short loc_180081256
0x180081223  test    byte ptr [rdi+1Ch], 10h
0x180081227  jz      short loc_180081256
0x180081229  mov     rdi, [rdi+10h]
0x18008122d  call    IkeGetTlsPeerAddr
0x180081232  mov     rbx, rax
0x180081235  call    IkeGetTlsMmLuid
0x18008123a  mov     r9, rax
0x18008123d  mov     [rsp+190h+ReturnLength], rbx
0x180081242  mov     edx, 4Ch ; 'L'
0x180081247  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x18008124e  mov     rcx, rdi
0x180081251  call    WPP_SF_iS
0x180081256  mov     eax, cs:dword_180173278
0x18008125c  cmp     eax, 4
0x18008125f  jbe     short loc_1800812C2
0x180081261  call    IkeGetTlsMmLuid
0x180081266  mov     [rbp+90h+var_F8], rax
0x18008126a  lea     rax, [rbp+90h+var_F8]
0x18008126e  mov     [rbp+90h+var_60], rax
0x180081272  mov     [rbp+90h+var_58], 8
0x18008127a  call    IkeGetTlsPeerAddr
0x18008127f  mov     rdx, rax
0x180081282  lea     rcx, [rbp+90h+var_50]
0x180081286  call    _tlgCreate1Sz_wchar_t
0x18008128b  lea     rcx, aCallingGettoke; "Calling GetTokenInformation"
0x180081292  mov     [rbp+90h+var_38], 1Ch
0x18008129a  lea     rax, [rbp+90h+var_80]
0x18008129e  mov     [rbp+90h+var_40], rcx
0x1800812a2  mov     qword ptr [rsp+190h+AuthenticationInformationLength], rax
0x1800812a7  lea     rcx, dword_180173278
0x1800812ae  lea     rdx, byte_180154E65
0x1800812b5  mov     dword ptr [rsp+190h+ReturnLength], 5
0x1800812bd  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800812c2  mov     rcx, [rbp+90h+TokenHandle]; TokenHandle
0x1800812c6  lea     rax, [rbp+90h+var_F0]
0x1800812ca  mov     r9d, 10h; TokenInformationLength
0x1800812d0  mov     [rsp+190h+ReturnLength], rax; ReturnLength
0x1800812d5  lea     r8, [rbp+90h+TokenInformation]; TokenInformation
0x1800812d9  lea     edx, [r9-9]; TokenInformationClass
0x1800812dd  call    cs:__imp_GetTokenInformation
0x1800812e3  test    eax, eax
0x1800812e5  jnz     short loc_1800812F9
0x1800812e7  call    cs:__imp_GetLastError
0x1800812ed  lea     rdx, aGettokeninform; "GetTokenInformation"
0x1800812f4  jmp     loc_1800811FB
0x1800812f9  mov     rdi, cs:WPP_GLOBAL_Control
0x180081300  cmp     rdi, rsi
0x180081303  jz      short loc_18008133E
0x180081305  cmp     byte ptr [rdi+19h], 4
0x180081309  jb      short loc_18008133E
0x18008130b  test    byte ptr [rdi+1Ch], 10h
0x18008130f  jz      short loc_18008133E
0x180081311  mov     rdi, [rdi+10h]
0x180081315  call    IkeGetTlsPeerAddr
0x18008131a  mov     rbx, rax
0x18008131d  call    IkeGetTlsMmLuid
0x180081322  mov     r9, rax
0x180081325  mov     [rsp+190h+ReturnLength], rbx
0x18008132a  mov     edx, 4Dh ; 'M'
0x18008132f  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x180081336  mov     rcx, rdi
0x180081339  call    WPP_SF_iS
0x18008133e  mov     eax, cs:dword_180173278
0x180081344  cmp     eax, 4
0x180081347  jbe     short loc_1800813AA
0x180081349  call    IkeGetTlsMmLuid
0x18008134e  mov     [rbp+90h+var_F8], rax
0x180081352  lea     rax, [rbp+90h+var_F8]
0x180081356  mov     [rbp+90h+var_60], rax
0x18008135a  mov     [rbp+90h+var_58], 8
0x180081362  call    IkeGetTlsPeerAddr
0x180081367  mov     rdx, rax
0x18008136a  lea     rcx, [rbp+90h+var_50]
0x18008136e  call    _tlgCreate1Sz_wchar_t
0x180081373  lea     rcx, aCallingLsalogo; "Calling LsaLogonUser"
0x18008137a  mov     [rbp+90h+var_38], 15h
0x180081382  lea     rax, [rbp+90h+var_80]
0x180081386  mov     [rbp+90h+var_40], rcx
0x18008138a  mov     qword ptr [rsp+190h+AuthenticationInformationLength], rax
0x18008138f  lea     rcx, dword_180173278
0x180081396  lea     rdx, byte_180154D6D
0x18008139d  mov     dword ptr [rsp+190h+ReturnLength], 5
0x1800813a5  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x1800813aa  mov     rcx, cs:gIkeExtGlobals
0x1800813b1  lea     rax, [rbp+90h+var_110]
0x1800813b5  mov     [rsp+190h+SubStatus], rax; SubStatus
0x1800813ba  lea     rdx, [rbp+90h+DestinationString]; OriginName
0x1800813be  lea     rax, [rbp+90h+var_B8]
0x1800813c2  mov     r8d, 3; LogonType
0x1800813c8  mov     [rsp+190h+Quotas], rax; Quotas
0x1800813cd  mov     rax, [rbp+90h+var_E8]
0x1800813d1  mov     r9d, [rcx+0BACh]; AuthenticationPackage
0x1800813d8  mov     rcx, [rcx+0BA0h]; LsaHandle
0x1800813df  mov     [rsp+190h+Token], rax; Token
0x1800813e4  lea     rax, [rbp+90h+var_E0]
0x1800813e8  mov     [rsp+190h+LogonId], rax; LogonId
0x1800813ed  lea     rax, [rbp+90h+var_EC]
0x1800813f1  mov     [rsp+190h+ProfileBufferLength], rax; ProfileBufferLength
0x1800813f6  lea     rax, [rbp+90h+Buffer]
0x1800813fa  mov     [rsp+190h+ProfileBuffer], rax; ProfileBuffer
0x1800813ff  lea     rax, [rbp+90h+TokenInformation]
0x180081403  mov     [rsp+190h+SourceContext], rax; SourceContext
0x180081408  mov     eax, [rsp+190h+var_120]
0x18008140c  mov     [rsp+190h+LocalGroups], 0; LocalGroups
0x180081415  mov     [rsp+190h+AuthenticationInformationLength], eax; AuthenticationInformationLength
0x180081419  mov     [rsp+190h+ReturnLength], r13; AuthenticationInformation
0x18008141e  call    cs:__imp_LsaLogonUser
0x180081424  mov     ebx, eax
0x180081426  test    eax, eax
0x180081428  js      short loc_180081441
0x18008142a  mov     rcx, [rbp+90h+Buffer]; Buffer
  ... truncated ...
```
