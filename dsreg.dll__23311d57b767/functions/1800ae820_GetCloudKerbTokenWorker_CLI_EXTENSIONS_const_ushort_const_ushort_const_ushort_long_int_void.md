# GetCloudKerbTokenWorker(CLI_EXTENSIONS const &,ushort const *,ushort const *,ushort * *,long *,int *,void *)

- ea: `0x1800ae820`
- end: `0x1800aee09`
- name: `?GetCloudKerbTokenWorker@@YAJAEBUCLI_EXTENSIONS@@PEBG1PEAPEAGPEAJPEAHPEAX@Z`
- size: `1513`
- prototype: `int(const struct CLI_EXTENSIONS *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, int *, int *, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ae7e0`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x180009780`
- `0x18000bac0`
- `0x180012c7c`
- `0x1800307c4`
- `0x180039e08`
- `0x180043ef8`
- `0x180046ae8`
- `0x180046b3c`
- `0x18008ddf0`
- `0x1800ae820`
- `0x1800b1dac`
- `0x1800b2d64`
- `0x1800b377c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aedb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aedb0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800aeda6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800aeda6`

## string_xrefs

- `0x1800aed3e`: `Logger::WriteDsRegCmdKerbFailureEvent`
- `0x1800aed37`: `EventWriteDsRegCmdKerbFailureEvent`
- `0x1800ae893`: `GetCloudKerbTokenWorker`
- `0x1800ae8ca`: `GetCloudKerbTokenWorker`
- `0x1800ae8e4`: `GetCloudKerbTokenWorker`
- `0x1800ae906`: `GetCloudKerbTokenWorker`
- `0x1800ae94b`: `GetCloudKerbTokenWorker`
- `0x1800ae989`: `GetCloudKerbTokenWorker`
- `0x1800ae9a6`: `GetCloudKerbTokenWorker`
- `0x1800ae9ea`: `GetCloudKerbTokenWorker`
- `0x1800aea2c`: `GetCloudKerbTokenWorker`
- `0x1800aea4c`: `GetCloudKerbTokenWorker`
- `0x1800aea73`: `GetCloudKerbTokenWorker`
- `0x1800aeaae`: `GetCloudKerbTokenWorker`
- `0x1800aeac8`: `GetCloudKerbTokenWorker`
- `0x1800aeaf9`: `GetCloudKerbTokenWorker`
- `0x1800aeb37`: `GetCloudKerbTokenWorker`
- `0x1800aeb54`: `GetCloudKerbTokenWorker`
- `0x1800aeb9a`: `GetCloudKerbTokenWorker`
- `0x1800aebd9`: `GetCloudKerbTokenWorker`
- `0x1800aec13`: `GetCloudKerbTokenWorker`
- `0x1800aec2c`: `GetCloudKerbTokenWorker`
- `0x1800aec61`: `GetCloudKerbTokenWorker`
- `0x1800aec92`: `GetCloudKerbTokenWorker`
- `0x1800aecd0`: `GetCloudKerbTokenWorker`
- `0x1800aecec`: `GetCloudKerbTokenWorker`
- `0x1800aed90`: `GetCloudKerbTokenWorker`
- `0x1800aedb9`: `GetCloudKerbTokenWorker`
- `0x1800aedcf`: `GetCloudKerbTokenWorker`
- `0x1800aeb00`: `%s: Failed to purge Kerberos cache. Error code: 0x%08x.\n`
- `0x1800aeb3e`: `%s: Failed to purge Kerberos cache. Error code: 0x%08x.\n`
- `0x1800aeb5b`: `%s: Failed to purge Kerberos cache. Error code: 0x%08x.\n`
- `0x1800aeb93`: `CLI_EXTENSIONS::pGetCloudKerbTicket`
- `0x1800ae9f1`: `%s: Failed to get Kerberos ticket for SPN "%s" with error code: 0x%08x. Purge cached Kerberos tickets and KDC proxy, then try again.\n`
- `0x1800aea33`: `%s: Failed to get Kerberos ticket for SPN "%s" with error code: 0x%08x. Purge cached Kerberos tickets and KDC proxy, then try again.\n`
- `0x1800aea53`: `%s: Failed to get Kerberos ticket for SPN "%s" with error code: 0x%08x. Purge cached Kerberos tickets and KDC proxy, then try again.\n`
- `0x1800aed97`: `%s: Set completion event with HRESULT 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCloudKerbTokenWorker(
        const struct CLI_EXTENSIONS *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        int *a5,
        int *a6,
        HANDLE hEvent)
{
  unsigned __int16 *v11; // r15
  int *v12; // rsi
  unsigned int v13; // ebx
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // rcx
  _QWORD *CurrentRef; // rax
  __int64 v23; // rdx
  _QWORD *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // ebx
  __int64 v30; // rdx
  __int64 v31; // rcx
  _QWORD *v32; // rax
  __int64 v33; // rdx
  _QWORD *v34; // rax
  __int64 v35; // rdx
  __int64 v36; // rax
  _BOOL8 v37; // rdx
  _BOOL8 v38; // rcx
  char v39; // bl
  __int64 v40; // rdx
  __int64 v41; // rcx
  _QWORD *v42; // rax
  __int64 v43; // rdx
  _QWORD *v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  unsigned int v49; // ebx
  __int64 v50; // rdx
  __int64 v51; // rcx
  _QWORD *v52; // rax
  __int64 v53; // rdx
  _QWORD *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rax
  int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // rcx
  _QWORD *v60; // rax
  __int64 v61; // rdx
  _QWORD *v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rax
  int v65; // eax
  __int64 v66; // rdx
  __int64 v67; // rcx
  _QWORD *v68; // rax
  __int64 v69; // rdx
  _QWORD *v70; // rax
  __int64 v71; // rdx
  __int64 v72; // rax
  int v73; // ecx
  const WCHAR *v74; // r9
  const WCHAR *v75; // rax
  unsigned int v76; // eax
  void *v77; // rdi
  DWORD LastError; // eax
  __int64 v80; // [rsp+20h] [rbp-71h]
  _QWORD v81[3]; // [rsp+30h] [rbp-61h] BYREF
  char v82; // [rsp+48h] [rbp-49h]
  __int128 v83; // [rsp+50h] [rbp-41h]
  __int128 v84; // [rsp+60h] [rbp-31h]
  __int128 v85; // [rsp+70h] [rbp-21h]
  __int128 v86; // [rsp+80h] [rbp-11h]
  __int64 v87; // [rsp+90h] [rbp-1h]
  __int64 v88; // [rsp+98h] [rbp+7h]
  DWORD cbBinary; // [rsp+E0h] [rbp+4Fh] BYREF
  unsigned __int16 *v90; // [rsp+E8h] [rbp+57h] BYREF
  void *lpMem; // [rsp+F8h] [rbp+67h] BYREF

  lpMem = 0;
  cbBinary = 0;
  v11 = 0;
  v90 = 0;
  v81[0] = *((_QWORD *)a1 + 2);
  v81[1] = 0;
  v81[2] = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  Logger::TraceVerbose((wchar_t *)L"%s started. Cloud kerb endpoint: %s. SPN: %s.", L"GetCloudKerbTokenWorker", a2, a3);
  if ( a4 )
    *a4 = 0;
  v12 = a6;
  if ( a6 )
    *a6 = 0;
  if ( !a2 )
  {
    v13 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetCloudKerbTokenWorker", L"endpoint");
    v14 = L"endpoint";
LABEL_7:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"GetCloudKerbTokenWorker", v14);
    goto LABEL_45;
  }
  if ( !a3 )
  {
    v13 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetCloudKerbTokenWorker", L"spn");
    v14 = L"spn";
    goto LABEL_7;
  }
  LOBYTE(a6) = 0;
  v19 = KdcProxyGpo::SetKdcProxy((KdcProxyGpo *)v81, a2, (bool *)&a6);
  if ( (v19 & 0x80000000) != 0 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v18, v17) )
    {
      wprintf(
        L"%s: Failed to set KDC proxy GPO. KdcProxyGpo::SetKdcProxy failed with error code: 0x%08x.\n",
        L"GetCloudKerbTokenWorker",
        v19);
      CurrentRef = (_QWORD *)CmdOptions::GetCurrentRef(v21, v20);
      if ( *(_BYTE *)(*CurrentRef + 12LL) )
      {
        v24 = (_QWORD *)CmdOptions::GetCurrentRef(*CurrentRef, v23);
        if ( *(_QWORD *)(*v24 + 184LL) )
        {
          v26 = CmdOptions::GetCurrentRef(*v24, v25);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v26 + 184LL),
            L"%s: Failed to set KDC proxy GPO. KdcProxyGpo::SetKdcProxy failed with error code: 0x%08x.\n",
            L"GetCloudKerbTokenWorker",
            v19);
        }
      }
    }
    Logger::TraceWarning(
      (wchar_t *)L"%s: Failed to set KDC proxy GPO. KdcProxyGpo::SetKdcProxy failed with error code: 0x%08x.\n",
      L"GetCloudKerbTokenWorker",
      v19);
  }
  v29 = (*((__int64 (__fastcall **)(const unsigned __int16 *, void **, DWORD *))a1 + 1))(a3, &lpMem, &cbBinary);
  if ( v29 >= 0 )
    goto LABEL_37;
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v28, v27) )
  {
    wprintf(
      L"%s: Failed to get Kerberos ticket for SPN \"%s\" with error code: 0x%08x. Purge cached Kerberos tickets and KDC pr"
       "oxy, then try again.\n",
      L"GetCloudKerbTokenWorker",
      a3,
      (unsigned int)v29);
    v32 = (_QWORD *)CmdOptions::GetCurrentRef(v31, v30);
    if ( *(_BYTE *)(*v32 + 12LL) )
    {
      v34 = (_QWORD *)CmdOptions::GetCurrentRef(*v32, v33);
      if ( *(_QWORD *)(*v34 + 184LL) )
      {
        v36 = CmdOptions::GetCurrentRef(*v34, v35);
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v36 + 184LL),
          L"%s: Failed to get Kerberos ticket for SPN \"%s\" with error code: 0x%08x. Purge cached Kerberos tickets and KD"
           "C proxy, then try again.\n",
          L"GetCloudKerbTokenWorker",
          a3,
          v29);
      }
    }
  }
  Logger::TraceWarning(
    (wchar_t *)L"%s: Failed to get Kerberos ticket for SPN \"%s\" with error code: 0x%08x. Purge cached Kerberos tickets a"
                "nd KDC proxy, then try again.\n",
    L"GetCloudKerbTokenWorker",
    a3,
    (unsigned int)v29);
  v39 = (char)a6;
  if ( (_BYTE)a6 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v38, v37) )
    {
      wprintf(
        L"%s: KDC proxy group policy was modified. Reload Kerberos policy before trying again.\n",
        L"GetCloudKerbTokenWorker");
      v42 = (_QWORD *)CmdOptions::GetCurrentRef(v41, v40);
      if ( *(_BYTE *)(*v42 + 12LL) )
      {
        v44 = (_QWORD *)CmdOptions::GetCurrentRef(*v42, v43);
        if ( *(_QWORD *)(*v44 + 184LL) )
        {
          v46 = CmdOptions::GetCurrentRef(v45, *v44);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v46 + 184LL),
            L"%s: KDC proxy group policy was modified. Reload Kerberos policy before trying again.\n",
            L"GetCloudKerbTokenWorker");
        }
      }
    }
    Logger::TraceWarning(
      (wchar_t *)L"%s: KDC proxy group policy was modified. Reload Kerberos policy before trying again.\n",
      L"GetCloudKerbTokenWorker");
  }
  v49 = DsrCmdJoinHelper::PurgeKerbCache(v38, v37, v39);
  if ( (v49 & 0x80000000) != 0 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v48, v47) )
    {
      wprintf(L"%s: Failed to purge Kerberos cache. Error code: 0x%08x.\n", L"GetCloudKerbTokenWorker", v49);
      v52 = (_QWORD *)CmdOptions::GetCurrentRef(v51, v50);
      if ( *(_BYTE *)(*v52 + 12LL) )
      {
        v54 = (_QWORD *)CmdOptions::GetCurrentRef(*v52, v53);
        if ( *(_QWORD *)(*v54 + 184LL) )
        {
          v56 = CmdOptions::GetCurrentRef(*v54, v55);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v56 + 184LL),
            L"%s: Failed to purge Kerberos cache. Error code: 0x%08x.\n",
            L"GetCloudKerbTokenWorker",
            v49);
        }
      }
    }
    Logger::TraceWarning(
      (wchar_t *)L"%s: Failed to purge Kerberos cache. Error code: 0x%08x.\n",
      L"GetCloudKerbTokenWorker",
      v49);
  }
  if ( v12 )
    *v12 = 1;
  v57 = (*((__int64 (__fastcall **)(const unsigned __int16 *, void **, DWORD *))a1 + 1))(a3, &lpMem, &cbBinary);
  v13 = v57;
  if ( v57 >= 0 )
  {
LABEL_37:
    if ( cbBinary )
    {
      v65 = ByteToBase64((BYTE *)lpMem, cbBinary, &v90, 0);
      v13 = v65;
      if ( v65 >= 0 )
      {
        if ( a4 )
        {
          *a4 = v90;
          v11 = 0;
        }
        else
        {
          v11 = v90;
        }
        goto LABEL_59;
      }
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"GetCloudKerbTokenWorker",
        L"ByteToBase64",
        (unsigned int)v65);
      v11 = v90;
    }
    else
    {
      v13 = -2145648493;
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v28, 0) )
      {
        wprintf(
          L"%s: The Kerberos ticket returned is empty. Return code: 0x%08x.\n",
          L"GetCloudKerbTokenWorker",
          2149318803LL);
        v60 = (_QWORD *)CmdOptions::GetCurrentRef(v59, v58);
        if ( *(_BYTE *)(*v60 + 12LL) )
        {
          v62 = (_QWORD *)CmdOptions::GetCurrentRef(*v60, v61);
          if ( *(_QWORD *)(*v62 + 184LL) )
          {
            v64 = CmdOptions::GetCurrentRef(*v62, v63);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v64 + 184LL),
              L"%s: The Kerberos ticket returned is empty. Return code: 0x%08x.\n",
              L"GetCloudKerbTokenWorker",
              2149318803LL);
          }
        }
      }
      Logger::TraceError(
        L"%s: The Kerberos ticket returned is empty. Return code: 0x%08x.\n",
        L"GetCloudKerbTokenWorker",
        2149318803LL);
    }
  }
  else
  {
    LODWORD(v80) = v57;
    Logger::TraceError(
      L"%s: %s(%s) failed with error code: 0x%08x.",
      L"GetCloudKerbTokenWorker",
      L"CLI_EXTENSIONS::pGetCloudKerbTicket",
      a3,
      v80);
  }
LABEL_45:
  if ( **(_BYTE **)CmdOptions::GetCurrentRef(v16, v15) )
  {
    wprintf(
      L"%s: Failed to get Kerberos ticket for SPN \"%s\" with error code: 0x%08x.\n",
      L"GetCloudKerbTokenWorker",
      a3,
      v13);
    v68 = (_QWORD *)CmdOptions::GetCurrentRef(v67, v66);
    if ( *(_BYTE *)(*v68 + 12LL) )
    {
      v70 = (_QWORD *)CmdOptions::GetCurrentRef(*v68, v69);
      if ( *(_QWORD *)(*v70 + 184LL) )
      {
        v72 = CmdOptions::GetCurrentRef(*v70, v71);
        LODWORD(v80) = v13;
        fwprintf_s(
          *(FILE *const *)(*(_QWORD *)v72 + 184LL),
          L"%s: Failed to get Kerberos ticket for SPN \"%s\" with error code: 0x%08x.\n",
          L"GetCloudKerbTokenWorker",
          a3,
          v80);
      }
    }
  }
  Logger::TraceError(
    L"%s: Failed to get Kerberos ticket for SPN \"%s\" with error code: 0x%08x.\n",
    L"GetCloudKerbTokenWorker",
    a3,
    v13);
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v74 = &cchOriginalDestLength;
    v75 = &cchOriginalDestLength;
    if ( a3 )
      v75 = a3;
    if ( a2 )
      LODWORD(v74) = (_DWORD)a2;
    v76 = McTemplateU0dzz_EventWriteTransfer(
            v73,
            (unsigned int)DsRegCmdKerbFailureEvent,
            v13,
            (_DWORD)v74,
            (__int64)v75);
    if ( v76 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteDsRegCmdKerbFailureEvent",
        L"EventWriteDsRegCmdKerbFailureEvent",
        v76);
  }
LABEL_59:
  SafeFree(lpMem);
  operator delete(v11);
  if ( a5 )
    *a5 = v13;
  v77 = hEvent;
  if ( hEvent )
  {
    Logger::TraceVerbose((wchar_t *)L"%s: Set completion event with HRESULT 0x%08x", L"GetCloudKerbTokenWorker", v13);
    if ( !SetEvent(v77) )
    {
      LastError = GetLastError();
      Logger::TraceWarning(
        (wchar_t *)L"%s: SetEvent failed with error code: 0x%08x",
        L"GetCloudKerbTokenWorker",
        LastError);
    }
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"GetCloudKerbTokenWorker", v13);
  KdcProxyGpo::~KdcProxyGpo((KdcProxyGpo *)v81);
  return v13;
}

```

## disassembly

```asm
0x1800ae820  mov     [rsp-8+arg_10], rbx
0x1800ae825  push    rbp
0x1800ae826  push    rsi
0x1800ae827  push    rdi
0x1800ae828  push    r12
0x1800ae82a  push    r13
0x1800ae82c  push    r14
0x1800ae82e  push    r15
0x1800ae830  lea     rbp, [rsp-0Fh]
0x1800ae835  sub     rsp, 0A0h
0x1800ae83c  mov     r14, r9
0x1800ae83f  mov     rdi, r8
0x1800ae842  mov     r12, rdx
0x1800ae845  mov     r13, rcx
0x1800ae848  xor     ebx, ebx
0x1800ae84a  mov     [rbp+3Fh+lpMem], rbx
0x1800ae84e  mov     [rbp+3Fh+cbBinary], ebx
0x1800ae851  mov     r15d, ebx
0x1800ae854  mov     [rbp+3Fh+arg_8], rbx
0x1800ae858  mov     rax, [rcx+10h]
0x1800ae85c  mov     [rbp+3Fh+var_A0], rax
0x1800ae860  mov     [rbp+3Fh+var_98], rbx
0x1800ae864  mov     [rbp+3Fh+var_90], rbx
0x1800ae868  mov     [rbp+3Fh+var_88], bl
0x1800ae86b  xorps   xmm0, xmm0
0x1800ae86e  movdqa  [rbp+3Fh+var_80], xmm0
0x1800ae873  xorps   xmm1, xmm1
0x1800ae876  movdqa  [rbp+3Fh+var_70], xmm1
0x1800ae87b  movdqa  [rbp+3Fh+var_60], xmm0
0x1800ae880  movdqa  [rbp+3Fh+var_50], xmm1
0x1800ae885  mov     [rbp+3Fh+var_40], rbx
0x1800ae889  mov     [rbp+3Fh+var_38], rbx
0x1800ae88d  mov     r9, r8
0x1800ae890  mov     r8, rdx
0x1800ae893  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800ae89a  lea     rcx, aSStartedCloudK; "%s started. Cloud kerb endpoint: %s. SP"...
0x1800ae8a1  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800ae8a6  test    r14, r14
0x1800ae8a9  jz      short loc_1800AE8AE
0x1800ae8ab  mov     [r14], rbx
0x1800ae8ae  mov     rsi, [rbp+3Fh+arg_28]
0x1800ae8b2  test    rsi, rsi
0x1800ae8b5  jz      short loc_1800AE8B9
0x1800ae8b7  mov     [rsi], ebx
0x1800ae8b9  test    r12, r12
0x1800ae8bc  jnz     short loc_1800AE8F5
0x1800ae8be  mov     ebx, 80070057h
0x1800ae8c3  lea     r8, aEndpoint; "endpoint"
0x1800ae8ca  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800ae8d1  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800ae8d8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ae8dd  lea     rdx, aEndpoint; "endpoint"
0x1800ae8e4  lea     rcx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800ae8eb  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800ae8f0  jmp     loc_1800AEC78
0x1800ae8f5  test    rdi, rdi
0x1800ae8f8  jnz     short loc_1800AE922
0x1800ae8fa  mov     ebx, 80070057h
0x1800ae8ff  lea     r8, aSpn_0; "spn"
0x1800ae906  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800ae90d  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x1800ae914  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800ae919  lea     rdx, aSpn_0; "spn"
0x1800ae920  jmp     short loc_1800AE8E4
0x1800ae922  mov     byte ptr [rbp+3Fh+arg_28], bl
0x1800ae925  lea     r8, [rbp+3Fh+arg_28]; bool *
0x1800ae929  mov     rdx, r12; pwszUrl
0x1800ae92c  lea     rcx, [rbp+3Fh+var_A0]; this
0x1800ae930  call    ?SetKdcProxy@KdcProxyGpo@@QEAAJPEBGAEA_N@Z; KdcProxyGpo::SetKdcProxy(ushort const *,bool &)
0x1800ae935  mov     ebx, eax
0x1800ae937  test    eax, eax
0x1800ae939  jns     short loc_1800AE9B9
0x1800ae93b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ae940  mov     rcx, [rax]
0x1800ae943  cmp     byte ptr [rcx], 0
0x1800ae946  jz      short loc_1800AE9A3
0x1800ae948  mov     r8d, ebx
0x1800ae94b  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800ae952  lea     rcx, aSFailedToSetKd; "%s: Failed to set KDC proxy GPO. KdcPro"...
0x1800ae959  call    wprintf
0x1800ae95e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ae963  mov     rcx, [rax]
0x1800ae966  cmp     byte ptr [rcx+0Ch], 0
0x1800ae96a  jz      short loc_1800AE9A3
0x1800ae96c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ae971  mov     rcx, [rax]
0x1800ae974  cmp     qword ptr [rcx+0B8h], 0
0x1800ae97c  jz      short loc_1800AE9A3
0x1800ae97e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ae983  mov     rcx, [rax]
0x1800ae986  mov     r9d, ebx
0x1800ae989  lea     r8, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800ae990  lea     rdx, aSFailedToSetKd; "%s: Failed to set KDC proxy GPO. KdcPro"...
0x1800ae997  mov     rcx, [rcx+0B8h]; Stream
0x1800ae99e  call    fwprintf_s
0x1800ae9a3  mov     r8d, ebx
0x1800ae9a6  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800ae9ad  lea     rcx, aSFailedToSetKd; "%s: Failed to set KDC proxy GPO. KdcPro"...
0x1800ae9b4  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800ae9b9  lea     r8, [rbp+3Fh+cbBinary]
0x1800ae9bd  lea     rdx, [rbp+3Fh+lpMem]
0x1800ae9c1  mov     rcx, rdi
0x1800ae9c4  mov     rax, [r13+8]
0x1800ae9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae9cd  mov     ebx, eax
0x1800ae9cf  test    eax, eax
0x1800ae9d1  jns     loc_1800AEBB2
0x1800ae9d7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800ae9dc  mov     rcx, [rax]
0x1800ae9df  cmp     byte ptr [rcx], 0
0x1800ae9e2  jz      short loc_1800AEA46
0x1800ae9e4  mov     r9d, ebx
0x1800ae9e7  mov     r8, rdi
0x1800ae9ea  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800ae9f1  lea     rcx, aSFailedToGetKe; "%s: Failed to get Kerberos ticket for S"...
0x1800ae9f8  call    wprintf
0x1800ae9fd  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aea02  mov     rcx, [rax]
0x1800aea05  cmp     byte ptr [rcx+0Ch], 0
0x1800aea09  jz      short loc_1800AEA46
0x1800aea0b  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aea10  mov     rcx, [rax]
0x1800aea13  cmp     qword ptr [rcx+0B8h], 0
0x1800aea1b  jz      short loc_1800AEA46
0x1800aea1d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aea22  mov     rcx, [rax]
0x1800aea25  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1800aea29  mov     r9, rdi
0x1800aea2c  lea     r8, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aea33  lea     rdx, aSFailedToGetKe; "%s: Failed to get Kerberos ticket for S"...
0x1800aea3a  mov     rcx, [rcx+0B8h]; Stream
0x1800aea41  call    fwprintf_s
0x1800aea46  mov     r9d, ebx
0x1800aea49  mov     r8, rdi
0x1800aea4c  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aea53  lea     rcx, aSFailedToGetKe; "%s: Failed to get Kerberos ticket for S"...
0x1800aea5a  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800aea5f  mov     bl, byte ptr [rbp+3Fh+arg_28]
0x1800aea62  test    bl, bl
0x1800aea64  jz      short loc_1800AEADB
0x1800aea66  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aea6b  mov     rcx, [rax]
0x1800aea6e  cmp     byte ptr [rcx], 0
0x1800aea71  jz      short loc_1800AEAC8
0x1800aea73  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aea7a  lea     rcx, aSKdcProxyGroup; "%s: KDC proxy group policy was modified"...
0x1800aea81  call    wprintf
0x1800aea86  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aea8b  mov     rcx, [rax]
0x1800aea8e  cmp     byte ptr [rcx+0Ch], 0
0x1800aea92  jz      short loc_1800AEAC8
0x1800aea94  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aea99  mov     rdx, [rax]
0x1800aea9c  cmp     qword ptr [rdx+0B8h], 0
0x1800aeaa4  jz      short loc_1800AEAC8
0x1800aeaa6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aeaab  mov     rcx, [rax]
0x1800aeaae  lea     r8, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aeab5  lea     rdx, aSKdcProxyGroup; "%s: KDC proxy group policy was modified"...
0x1800aeabc  mov     rcx, [rcx+0B8h]; Stream
0x1800aeac3  call    fwprintf_s
0x1800aeac8  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aeacf  lea     rcx, aSKdcProxyGroup; "%s: KDC proxy group policy was modified"...
0x1800aead6  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800aeadb  mov     r8b, bl; bool
0x1800aeade  call    ?PurgeKerbCache@DsrCmdJoinHelper@@SAJ_N00@Z; DsrCmdJoinHelper::PurgeKerbCache(bool,bool,bool)
0x1800aeae3  mov     ebx, eax
0x1800aeae5  test    eax, eax
0x1800aeae7  jns     short loc_1800AEB67
0x1800aeae9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aeaee  mov     rcx, [rax]
0x1800aeaf1  cmp     byte ptr [rcx], 0
0x1800aeaf4  jz      short loc_1800AEB51
0x1800aeaf6  mov     r8d, ebx
0x1800aeaf9  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aeb00  lea     rcx, aSFailedToPurge; "%s: Failed to purge Kerberos cache. Err"...
0x1800aeb07  call    wprintf
0x1800aeb0c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aeb11  mov     rcx, [rax]
0x1800aeb14  cmp     byte ptr [rcx+0Ch], 0
0x1800aeb18  jz      short loc_1800AEB51
0x1800aeb1a  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aeb1f  mov     rcx, [rax]
0x1800aeb22  cmp     qword ptr [rcx+0B8h], 0
0x1800aeb2a  jz      short loc_1800AEB51
0x1800aeb2c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aeb31  mov     rcx, [rax]
0x1800aeb34  mov     r9d, ebx
0x1800aeb37  lea     r8, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aeb3e  lea     rdx, aSFailedToPurge; "%s: Failed to purge Kerberos cache. Err"...
0x1800aeb45  mov     rcx, [rcx+0B8h]; Stream
0x1800aeb4c  call    fwprintf_s
0x1800aeb51  mov     r8d, ebx
0x1800aeb54  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aeb5b  lea     rcx, aSFailedToPurge; "%s: Failed to purge Kerberos cache. Err"...
0x1800aeb62  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800aeb67  test    rsi, rsi
0x1800aeb6a  jz      short loc_1800AEB72
0x1800aeb6c  mov     dword ptr [rsi], 1
0x1800aeb72  lea     r8, [rbp+3Fh+cbBinary]
0x1800aeb76  lea     rdx, [rbp+3Fh+lpMem]
0x1800aeb7a  mov     rcx, rdi
0x1800aeb7d  mov     rax, [r13+8]
0x1800aeb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb86  mov     ebx, eax
0x1800aeb88  test    eax, eax
0x1800aeb8a  jns     short loc_1800AEBB2
0x1800aeb8c  mov     dword ptr [rsp+0D0h+var_B0], eax
0x1800aeb90  mov     r9, rdi
0x1800aeb93  lea     r8, aCliExtensionsP; "CLI_EXTENSIONS::pGetCloudKerbTicket"
0x1800aeb9a  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aeba1  lea     rcx, aSSSFailedWithE; "%s: %s(%s) failed with error code: 0x%0"...
0x1800aeba8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800aebad  jmp     loc_1800AEC78
0x1800aebb2  mov     edx, [rbp+3Fh+cbBinary]; cbBinary
0x1800aebb5  test    edx, edx
0x1800aebb7  jnz     loc_1800AEC3D
0x1800aebbd  mov     ebx, 801C0093h
0x1800aebc2  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aebc7  mov     rcx, [rax]
0x1800aebca  lea     rsi, aSTheKerberosTi; "%s: The Kerberos ticket returned is emp"...
0x1800aebd1  cmp     byte ptr [rcx], 0
0x1800aebd4  jz      short loc_1800AEC29
0x1800aebd6  mov     r8d, ebx
0x1800aebd9  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aebe0  mov     rcx, rsi; Format
0x1800aebe3  call    wprintf
0x1800aebe8  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aebed  mov     rcx, [rax]
0x1800aebf0  cmp     byte ptr [rcx+0Ch], 0
0x1800aebf4  jz      short loc_1800AEC29
0x1800aebf6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aebfb  mov     rcx, [rax]
0x1800aebfe  cmp     qword ptr [rcx+0B8h], 0
0x1800aec06  jz      short loc_1800AEC29
0x1800aec08  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aec0d  mov     rcx, [rax]
0x1800aec10  mov     r9d, ebx
0x1800aec13  lea     r8, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aec1a  mov     rdx, rsi; Format
0x1800aec1d  mov     rcx, [rcx+0B8h]; Stream
0x1800aec24  call    fwprintf_s
0x1800aec29  mov     r8d, ebx
0x1800aec2c  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aec33  mov     rcx, rsi; unsigned __int16 *
0x1800aec36  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800aec3b  jmp     short loc_1800AEC78
0x1800aec3d  xor     r9d, r9d; unsigned __int64 *
0x1800aec40  lea     r8, [rbp+3Fh+arg_8]; unsigned __int16 **
0x1800aec44  mov     rcx, [rbp+3Fh+lpMem]; pbBinary
0x1800aec48  call    ?ByteToBase64@@YAJPEBEKPEAPEAGPEA_K@Z; ByteToBase64(uchar const *,ulong,ushort * *,unsigned __int64 *)
0x1800aec4d  mov     ebx, eax
0x1800aec4f  test    eax, eax
0x1800aec51  jns     loc_1800AED53
0x1800aec57  mov     r9d, eax
0x1800aec5a  lea     r8, aBytetobase64; "ByteToBase64"
0x1800aec61  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aec68  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800aec6f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800aec74  mov     r15, [rbp+3Fh+arg_8]
0x1800aec78  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aec7d  mov     rcx, [rax]
0x1800aec80  lea     rsi, aSFailedToGetKe_0; "%s: Failed to get Kerberos ticket for S"...
0x1800aec87  cmp     byte ptr [rcx], 0
0x1800aec8a  jz      short loc_1800AECE6
0x1800aec8c  mov     r9d, ebx
0x1800aec8f  mov     r8, rdi
0x1800aec92  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aec99  mov     rcx, rsi; Format
0x1800aec9c  call    wprintf
0x1800aeca1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aeca6  mov     rcx, [rax]
0x1800aeca9  cmp     byte ptr [rcx+0Ch], 0
0x1800aecad  jz      short loc_1800AECE6
0x1800aecaf  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aecb4  mov     rcx, [rax]
0x1800aecb7  cmp     qword ptr [rcx+0B8h], 0
0x1800aecbf  jz      short loc_1800AECE6
0x1800aecc1  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800aecc6  mov     rcx, [rax]
0x1800aecc9  mov     dword ptr [rsp+0D0h+var_B0], ebx
0x1800aeccd  mov     r9, rdi
0x1800aecd0  lea     r8, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aecd7  mov     rdx, rsi; Format
0x1800aecda  mov     rcx, [rcx+0B8h]; Stream
0x1800aece1  call    fwprintf_s
0x1800aece6  mov     r9d, ebx
0x1800aece9  mov     r8, rdi
0x1800aecec  lea     rdx, aGetcloudkerbto; "GetCloudKerbTokenWorker"
0x1800aecf3  mov     rcx, rsi; unsigned __int16 *
0x1800aecf6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800aecfb  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800aed02  jz      short loc_1800AED68
0x1800aed04  lea     r9, cchOriginalDestLength
0x1800aed0b  mov     rax, r9
0x1800aed0e  test    rdi, rdi
0x1800aed11  cmovnz  rax, rdi
0x1800aed15  test    r12, r12
0x1800aed18  cmovnz  r9, r12
0x1800aed1c  mov     [rsp+0D0h+var_B0], rax
  ... truncated ...
```
