# DsrCmdDeviceEnroller::Leave(DsregServerResponse *,int)

- ea: `0x180034684`
- end: `0x180034cc8`
- name: `?Leave@DsrCmdDeviceEnroller@@QEAAJPEAVDsregServerResponse@@H@Z`
- size: `1604`
- prototype: `__int64 __fastcall(DsrCmdDeviceEnroller *__hidden this, struct DsregServerResponse *, int)`
- caller_count: `3`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180099424`
- `0x1800aee10`
- `0x1800b0bf8`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000cb50`
- `0x18000db10`
- `0x180012c7c`
- `0x18001378c`
- `0x18001ebe4`
- `0x180029e68`
- `0x18002b9b4`
- `0x180032418`
- `0x180034684`
- `0x180038cc0`
- `0x18004271c`
- `0x180044300`
- `0x180044d30`
- `0x180046ae8`
- `0x180046b3c`
- `0x180052698`
- `0x1800a02e0`
- `0x1800a088c`
- `0x1800aae0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003494f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034781`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800348ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003494f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180034772`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180034772`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180034829`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180034829`

## string_xrefs

- `0x180034799`: `CreateEventExW`
- `0x180034bad`: `Logger::WriteDsRegCmdLeaveMdmUnenrollFailedEvent`
- `0x180034ba6`: `EventWriteDsRegCmdLeaveMdmUnenrollFailedEvent`
- `0x180034bfd`: `Logger::WriteDsRegCmdLeaveMdmUnenrollSuccessEvent`
- `0x180034bf6`: `EventWriteDsRegCmdLeaveMdmUnenrollSuccessEvent`
- `0x180034a3a`: `%s: NgcReg::NgcRemoveAllRegistrations failed 0x%08x\n`
- `0x180034ab2`: `Only the NGC for the current user is being removed. To remove all rerun as SYSTEM.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DsrCmdDeviceEnroller::Leave(DsrCmdDeviceEnroller *this, struct DsregServerResponse *a2, int a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  int IsDeviceJoined; // edi
  _BYTE **CurrentRef; // rax
  const wchar_t *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  HANDLE Event; // rax
  signed int LastError; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  DWORD v22; // eax
  DWORD v23; // ebx
  __int64 v24; // rdx
  __int64 v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rdx
  _QWORD *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rax
  signed int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  DWORD v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  _QWORD *v37; // rax
  __int64 v38; // rdx
  DWORD v39; // ebx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rax
  DWORD v43; // eax
  __int64 v44; // rdx
  __int64 v45; // rcx
  _QWORD *v46; // rax
  __int64 v47; // rdx
  _QWORD *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rdx
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rcx
  _QWORD *v57; // rax
  __int64 v58; // rdx
  _QWORD *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rcx
  _QWORD *v64; // rax
  __int64 v65; // rdx
  _QWORD *v66; // rax
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rcx
  int v71; // eax
  __int64 v72; // rcx
  _QWORD *v73; // r9
  unsigned int v74; // eax
  const wchar_t *v75; // r8
  const wchar_t *v76; // rdx
  _QWORD *v77; // r8
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // rdx
  __int64 v81; // rcx
  _QWORD *v82; // rax
  __int64 v83; // rdx
  _QWORD *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rax
  int v88; // [rsp+30h] [rbp-D0h] BYREF
  WINBOOL IsMember[3]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v90[40]; // [rsp+40h] [rbp-C0h] BYREF
  int v91; // [rsp+68h] [rbp-98h]
  __int64 v92; // [rsp+178h] [rbp+78h]
  _QWORD v93[3]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v94; // [rsp+198h] [rbp+98h]

  v88 = 0;
  if ( a2 )
    DsrFreeServerResponseContent(a2);
  *(_QWORD *)this = a2;
  IsDeviceJoined = DsrIsDeviceJoinedEx(&v88, 0, 0);
  if ( IsDeviceJoined < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v7, v6);
    v10 = L"%s: DsrIsDeviceJoined failed 0x%08x\n";
    goto LABEL_5;
  }
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  *((_QWORD *)this + 5) = Event;
  if ( !Event )
  {
    LastError = GetLastError();
    IsDeviceJoined = LastError;
    if ( LastError > 0 )
      IsDeviceJoined = (unsigned __int16)LastError | 0x80070000;
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"DsrCmdDeviceEnroller::Leave",
      L"CreateEventExW",
      (unsigned int)IsDeviceJoined);
    goto LABEL_71;
  }
  memset_0(v90, 0, 0x140u);
  v92 = *((_QWORD *)this + 3);
  v91 = 0;
  IsDeviceJoined = DeviceRegistrationApi::BeginJoin(
                     8u,
                     v90,
                     (void (__fastcall *)(__int128 *, __int64, _QWORD))&DsrCmdDeviceEnroller::LeaveCallback,
                     (__int64)this,
                     &_JOIN_OPERATION_CONTEXT::DEFAULT);
  if ( IsDeviceJoined < 0 )
    goto LABEL_15;
  v22 = WaitForSingleObjectEx(*((HANDLE *)this + 5), 0x927C0u, 0);
  v23 = v22;
  if ( v22 )
  {
    if ( v22 == 258 )
    {
      IsDeviceJoined = -2145648612;
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v21, v20) )
      {
        wprintf(L"%s: WaitForSingleObjectEx timed out 0x%08x\n", L"DsrCmdDeviceEnroller::Leave", 2149318684LL);
        v46 = (_QWORD *)CmdOptions::GetCurrentRef(v45, v44);
        if ( *(_BYTE *)(*v46 + 12LL) )
        {
          v48 = (_QWORD *)CmdOptions::GetCurrentRef(*v46, v47);
          if ( *(_QWORD *)(*v48 + 184LL) )
          {
            v50 = CmdOptions::GetCurrentRef(*v48, v49);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v50 + 184LL),
              L"%s: WaitForSingleObjectEx timed out 0x%08x\n",
              L"DsrCmdDeviceEnroller::Leave",
              2149318684LL);
          }
        }
      }
      Logger::TraceError(L"%s: WaitForSingleObjectEx timed out 0x%08x\n", L"DsrCmdDeviceEnroller::Leave", 2149318684LL);
      goto LABEL_15;
    }
    if ( v22 != -1 )
    {
      IsDeviceJoined = -2145648612;
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v21, v20) )
      {
        wprintf(
          L"%s: WaitForSingleObjectEx returned unexpected wait status: 0x%08x\n",
          L"DsrCmdDeviceEnroller::Leave",
          v23);
        v26 = (_QWORD *)CmdOptions::GetCurrentRef(v25, v24);
        if ( *(_BYTE *)(*v26 + 12LL) )
        {
          v28 = (_QWORD *)CmdOptions::GetCurrentRef(*v26, v27);
          if ( *(_QWORD *)(*v28 + 184LL) )
          {
            v30 = CmdOptions::GetCurrentRef(*v28, v29);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v30 + 184LL),
              L"%s: WaitForSingleObjectEx returned unexpected wait status: 0x%08x\n",
              L"DsrCmdDeviceEnroller::Leave",
              v23);
          }
        }
      }
      Logger::TraceError(
        L"%s: WaitForSingleObjectEx returned unexpected wait status: 0x%08x\n",
        L"DsrCmdDeviceEnroller::Leave",
        v23);
      goto LABEL_15;
    }
    v31 = GetLastError();
    IsDeviceJoined = v31;
    if ( v31 > 0 )
      IsDeviceJoined = (unsigned __int16)v31 | 0x80070000;
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v33, v32) )
    {
      v34 = GetLastError();
      wprintf(L"%s: WaitForSingleObjectEx failed: 0x%08x\n", L"DsrCmdDeviceEnroller::Leave", v34);
      v37 = (_QWORD *)CmdOptions::GetCurrentRef(v36, v35);
      if ( *(_BYTE *)(*v37 + 12LL) )
      {
        if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(*v37, v38) + 184LL) )
        {
          v39 = GetLastError();
          v42 = CmdOptions::GetCurrentRef(v41, v40);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v42 + 184LL),
            L"%s: WaitForSingleObjectEx failed: 0x%08x\n",
            L"DsrCmdDeviceEnroller::Leave",
            v39);
        }
      }
    }
    v43 = GetLastError();
    Logger::TraceError(L"%s: WaitForSingleObjectEx failed: 0x%08x\n", L"DsrCmdDeviceEnroller::Leave", v43);
  }
  else
  {
    IsDeviceJoined = *((_DWORD *)this + 8);
  }
  if ( IsDeviceJoined < 0 )
  {
LABEL_15:
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v21, v20);
    v10 = L"%s: DsrBeginDeviceUnjoin failed 0x%08x\n";
    goto LABEL_5;
  }
  IsMember[0] = 0;
  IsDeviceJoined = IsCurrentUserSystem(IsMember);
  if ( IsDeviceJoined < 0 )
  {
    CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v52, v51);
    v10 = L"%s: IsCurrentUserSystem check failed 0x%08x.\n";
    goto LABEL_5;
  }
  if ( IsMember[0] )
  {
    IsDeviceJoined = NgcRegController::NgcRemoveAllRegistrations(0);
    if ( IsDeviceJoined < 0 )
    {
      if ( **(_BYTE **)CmdOptions::GetCurrentRef(v54, v53) )
      {
        wprintf(
          L"%s: NgcReg::NgcRemoveAllRegistrations failed 0x%08x\n",
          L"DsrCmdDeviceEnroller::Leave",
          (unsigned int)IsDeviceJoined);
        v57 = (_QWORD *)CmdOptions::GetCurrentRef(v56, v55);
        if ( *(_BYTE *)(*v57 + 12LL) )
        {
          v59 = (_QWORD *)CmdOptions::GetCurrentRef(*v57, v58);
          if ( *(_QWORD *)(*v59 + 184LL) )
          {
            v61 = CmdOptions::GetCurrentRef(*v59, v60);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v61 + 184LL),
              L"%s: NgcReg::NgcRemoveAllRegistrations failed 0x%08x\n",
              L"DsrCmdDeviceEnroller::Leave",
              (unsigned int)IsDeviceJoined);
          }
        }
      }
      Logger::TraceError(
        L"%s: NgcReg::NgcRemoveAllRegistrations failed 0x%08x\n",
        L"DsrCmdDeviceEnroller::Leave",
        (unsigned int)IsDeviceJoined);
      Logger::WriteNgcRemoveAllRegistrationFailureEvent(IsDeviceJoined);
      IsDeviceJoined = 0;
    }
  }
  else
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v52, v51) )
    {
      wprintf(L"Only the NGC for the current user is being removed. To remove all rerun as SYSTEM.\n");
      v64 = (_QWORD *)CmdOptions::GetCurrentRef(v63, v62);
      if ( *(_BYTE *)(*v64 + 12LL) )
      {
        v66 = (_QWORD *)CmdOptions::GetCurrentRef(*v64, v65);
        if ( *(_QWORD *)(*v66 + 184LL) )
        {
          v68 = CmdOptions::GetCurrentRef(v67, *v66);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v68 + 184LL),
            L"Only the NGC for the current user is being removed. To remove all rerun as SYSTEM.\n");
        }
      }
    }
    Logger::TraceWarning((wchar_t *)L"Only the NGC for the current user is being removed. To remove all rerun as SYSTEM.\n");
  }
  if ( v88 && a3 )
  {
    v88 = 0;
    IsDeviceJoined = IsLocalMachineDomainJoined(&v88, 0);
    if ( IsDeviceJoined < 0 )
    {
      CurrentRef = (_BYTE **)CmdOptions::GetCurrentRef(v70, v69);
      v10 = L"%s: IsLocalMachineDomainJoined failed 0x%08x\n";
LABEL_5:
      if ( **CurrentRef )
      {
        wprintf(v10, L"DsrCmdDeviceEnroller::Leave", (unsigned int)IsDeviceJoined);
        v13 = (_QWORD *)CmdOptions::GetCurrentRef(v12, v11);
        if ( *(_BYTE *)(*v13 + 12LL) )
        {
          v15 = (_QWORD *)CmdOptions::GetCurrentRef(*v13, v14);
          if ( *(_QWORD *)(*v15 + 184LL) )
          {
            v17 = CmdOptions::GetCurrentRef(*v15, v16);
            fwprintf_s(
              *(FILE *const *)(*(_QWORD *)v17 + 184LL),
              v10,
              L"DsrCmdDeviceEnroller::Leave",
              (unsigned int)IsDeviceJoined);
          }
        }
      }
      Logger::TraceError(v10, L"DsrCmdDeviceEnroller::Leave", (unsigned int)IsDeviceJoined);
      goto LABEL_71;
    }
    if ( v88 )
      goto LABEL_71;
    std::wstring::wstring((__int64)v93, (__int64)&cchOriginalDestLength);
    v71 = DsrCmdDeviceEnroller::UnenrollFromMDM(v93);
    if ( v71 >= 0 )
    {
      if ( !v93[2] )
        goto LABEL_70;
      v77 = v93;
      if ( v94 > 7 )
        v77 = (_QWORD *)v93[0];
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) == 0 )
        goto LABEL_70;
      v74 = McTemplateU0z_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              DsRegCmdLeaveMdmUnenrollSuccessEvent,
              v77);
      if ( !v74 )
        goto LABEL_70;
      v75 = L"EventWriteDsRegCmdLeaveMdmUnenrollSuccessEvent";
      v76 = L"Logger::WriteDsRegCmdLeaveMdmUnenrollSuccessEvent";
    }
    else
    {
      v73 = v93;
      if ( v94 > 7 )
        v73 = (_QWORD *)v93[0];
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 4) == 0 )
        goto LABEL_70;
      v74 = McTemplateU0dz_EventWriteTransfer(v72, DsRegCmdLeaveMdmUnenrollFailedEvent, (unsigned int)v71, v73);
      if ( !v74 )
        goto LABEL_70;
      v75 = L"EventWriteDsRegCmdLeaveMdmUnenrollFailedEvent";
      v76 = L"Logger::WriteDsRegCmdLeaveMdmUnenrollFailedEvent";
    }
    Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", v76, v75, v74);
LABEL_70:
    std::wstring::_Tidy_deallocate((__int64)v93);
  }
LABEL_71:
  DsrCmdDeviceEnroller::CloseAllEvents(this);
  *(_QWORD *)this = 0;
  if ( IsDeviceJoined < 0 )
  {
    if ( **(_BYTE **)CmdOptions::GetCurrentRef(v79, v78) )
    {
      wprintf(L"%s: Leave failed with 0x%08x\n", L"DsrCmdDeviceEnroller::Leave", (unsigned int)IsDeviceJoined);
      v82 = (_QWORD *)CmdOptions::GetCurrentRef(v81, v80);
      if ( *(_BYTE *)(*v82 + 12LL) )
      {
        v84 = (_QWORD *)CmdOptions::GetCurrentRef(*v82, v83);
        if ( *(_QWORD *)(*v84 + 184LL) )
        {
          v86 = CmdOptions::GetCurrentRef(*v84, v85);
          fwprintf_s(
            *(FILE *const *)(*(_QWORD *)v86 + 184LL),
            L"%s: Leave failed with 0x%08x\n",
            L"DsrCmdDeviceEnroller::Leave",
            (unsigned int)IsDeviceJoined);
        }
      }
    }
    Logger::TraceError(L"%s: Leave failed with 0x%08x\n", L"DsrCmdDeviceEnroller::Leave", (unsigned int)IsDeviceJoined);
  }
  return (unsigned int)IsDeviceJoined;
}

```

## disassembly

```asm
0x180034684  mov     [rsp-8+arg_10], rbx
0x180034689  mov     [rsp-8+arg_18], rsi
0x18003468e  push    rbp
0x18003468f  push    rdi
0x180034690  push    r12
0x180034692  push    r14
0x180034694  push    r15
0x180034696  lea     rbp, [rsp-0B0h]
0x18003469e  sub     rsp, 1B0h
0x1800346a5  mov     rax, cs:__security_cookie
0x1800346ac  xor     rax, rsp
0x1800346af  mov     [rbp+0D0h+var_30], rax
0x1800346b6  mov     r15d, r8d
0x1800346b9  mov     rbx, rdx
0x1800346bc  mov     r14, rcx
0x1800346bf  xor     r12d, r12d
0x1800346c2  mov     [rsp+1D0h+var_1A0], r12d
0x1800346c7  test    rdx, rdx
0x1800346ca  jz      short loc_1800346D4
0x1800346cc  mov     rcx, rdx
0x1800346cf  call    DsrFreeServerResponseContent
0x1800346d4  mov     [r14], rbx
0x1800346d7  xor     r8d, r8d
0x1800346da  xor     edx, edx
0x1800346dc  lea     rcx, [rsp+1D0h+var_1A0]
0x1800346e1  call    DsrIsDeviceJoinedEx
0x1800346e6  mov     edi, eax
0x1800346e8  test    eax, eax
0x1800346ea  jns     short loc_180034764
0x1800346ec  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800346f1  lea     rsi, aDsrcmddeviceen_3; "DsrCmdDeviceEnroller::Leave"
0x1800346f8  lea     rbx, aSDsrisdevicejo; "%s: DsrIsDeviceJoined failed 0x%08x\n"
0x1800346ff  mov     rcx, [rax]
0x180034702  cmp     [rcx], r12b
0x180034705  jz      short loc_180034751
0x180034707  mov     r8d, edi
0x18003470a  mov     rdx, rsi
0x18003470d  mov     rcx, rbx; Format
0x180034710  call    wprintf
0x180034715  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003471a  mov     rcx, [rax]
0x18003471d  cmp     [rcx+0Ch], r12b
0x180034721  jz      short loc_180034751
0x180034723  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034728  mov     rcx, [rax]
0x18003472b  cmp     [rcx+0B8h], r12
0x180034732  jz      short loc_180034751
0x180034734  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034739  mov     rcx, [rax]
0x18003473c  mov     r9d, edi
0x18003473f  mov     r8, rsi
0x180034742  mov     rdx, rbx; Format
0x180034745  mov     rcx, [rcx+0B8h]; Stream
0x18003474c  call    fwprintf_s
0x180034751  mov     r8d, edi
0x180034754  mov     rdx, rsi
0x180034757  mov     rcx, rbx; unsigned __int16 *
0x18003475a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003475f  jmp     loc_180034C20
0x180034764  xor     edx, edx; lpName
0x180034766  xor     ecx, ecx; lpEventAttributes
0x180034768  mov     r9d, 1F0003h; dwDesiredAccess
0x18003476e  lea     r8d, [rdx+1]; dwFlags
0x180034772  call    cs:__imp_CreateEventExW
0x180034778  mov     [r14+28h], rax
0x18003477c  test    rax, rax
0x18003477f  jnz     short loc_1800347BB
0x180034781  call    cs:__imp_GetLastError
0x180034787  mov     edi, eax
0x180034789  test    eax, eax
0x18003478b  jle     short loc_180034796
0x18003478d  movzx   edi, ax
0x180034790  or      edi, 80070000h
0x180034796  mov     r9d, edi
0x180034799  lea     r8, aCreateeventexw; "CreateEventExW"
0x1800347a0  lea     rsi, aDsrcmddeviceen_3; "DsrCmdDeviceEnroller::Leave"
0x1800347a7  mov     rdx, rsi
0x1800347aa  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x1800347b1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800347b6  jmp     loc_180034C20
0x1800347bb  xor     edx, edx; Val
0x1800347bd  mov     r8d, 140h; Size
0x1800347c3  lea     rcx, [rsp+1D0h+var_190]; void *
0x1800347c8  call    memset_0
0x1800347cd  mov     rax, [r14+18h]
0x1800347d1  mov     [rbp+0D0h+var_58], rax
0x1800347d5  mov     [rsp+1D0h+var_168], r12d
0x1800347da  lea     rax, ?DEFAULT@_JOIN_OPERATION_CONTEXT@@2U1@B; _JOIN_OPERATION_CONTEXT const _JOIN_OPERATION_CONTEXT::DEFAULT
0x1800347e1  mov     [rsp+1D0h+var_1B0], rax
0x1800347e6  mov     r9, r14
0x1800347e9  lea     r8, ?LeaveCallback@DsrCmdDeviceEnroller@@SAXUstruct_dsreg_server_response@@_KJ@Z; DsrCmdDeviceEnroller::LeaveCallback(struct_dsreg_server_response,unsigned __int64,long)
0x1800347f0  lea     rdx, [rsp+1D0h+var_190]
0x1800347f5  mov     ecx, 8
0x1800347fa  call    ?BeginJoin@DeviceRegistrationApi@@SAJW4_JOIN_TYPE@@PEAXP6AXXZ_KPEBU_JOIN_OPERATION_CONTEXT@@@Z; DeviceRegistrationApi::BeginJoin(_JOIN_TYPE,void *,void (*)(void),unsigned __int64,_JOIN_OPERATION_CONTEXT const *)
0x1800347ff  mov     edi, eax
0x180034801  test    eax, eax
0x180034803  jns     short loc_18003481D
0x180034805  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003480a  lea     rsi, aDsrcmddeviceen_3; "DsrCmdDeviceEnroller::Leave"
0x180034811  lea     rbx, aSDsrbegindevic_0; "%s: DsrBeginDeviceUnjoin failed 0x%08x"...
0x180034818  jmp     loc_1800346FF
0x18003481d  xor     r8d, r8d; bAlertable
0x180034820  mov     edx, 927C0h; dwMilliseconds
0x180034825  mov     rcx, [r14+28h]; hHandle
0x180034829  call    cs:__imp_WaitForSingleObjectEx
0x18003482f  mov     ebx, eax
0x180034831  lea     rsi, aDsrcmddeviceen_3; "DsrCmdDeviceEnroller::Leave"
0x180034838  test    eax, eax
0x18003483a  jz      loc_1800349DE
0x180034840  cmp     eax, 102h
0x180034845  jz      loc_180034969
0x18003484b  cmp     eax, 0FFFFFFFFh
0x18003484e  jz      short loc_1800348CD
0x180034850  mov     edi, 801C001Ch
0x180034855  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003485a  mov     rcx, [rax]
0x18003485d  lea     rsi, aDsrcmddeviceen_3; "DsrCmdDeviceEnroller::Leave"
0x180034864  lea     r15, aSWaitforsingle_3; "%s: WaitForSingleObjectEx returned unex"...
0x18003486b  cmp     [rcx], r12b
0x18003486e  jz      short loc_1800348BA
0x180034870  mov     r8d, ebx
0x180034873  mov     rdx, rsi
0x180034876  mov     rcx, r15; Format
0x180034879  call    wprintf
0x18003487e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034883  mov     rcx, [rax]
0x180034886  cmp     [rcx+0Ch], r12b
0x18003488a  jz      short loc_1800348BA
0x18003488c  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034891  mov     rcx, [rax]
0x180034894  cmp     [rcx+0B8h], r12
0x18003489b  jz      short loc_1800348BA
0x18003489d  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800348a2  mov     rcx, [rax]
0x1800348a5  mov     r9d, ebx
0x1800348a8  mov     r8, rsi
0x1800348ab  mov     rdx, r15; Format
0x1800348ae  mov     rcx, [rcx+0B8h]; Stream
0x1800348b5  call    fwprintf_s
0x1800348ba  mov     r8d, ebx
0x1800348bd  mov     rcx, r15; unsigned __int16 *
0x1800348c0  mov     rdx, rsi
0x1800348c3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800348c8  jmp     loc_1800349E6
0x1800348cd  call    cs:__imp_GetLastError
0x1800348d3  mov     edi, eax
0x1800348d5  test    eax, eax
0x1800348d7  jle     short loc_1800348E2
0x1800348d9  movzx   edi, ax
0x1800348dc  or      edi, 80070000h
0x1800348e2  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800348e7  mov     rcx, [rax]
0x1800348ea  cmp     [rcx], r12b
0x1800348ed  jz      short loc_18003494F
0x1800348ef  call    cs:__imp_GetLastError
0x1800348f5  mov     r8d, eax
0x1800348f8  mov     rdx, rsi
0x1800348fb  lea     rcx, aSWaitforsingle_0; "%s: WaitForSingleObjectEx failed: 0x%08"...
0x180034902  call    wprintf
0x180034907  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003490c  mov     rcx, [rax]
0x18003490f  cmp     [rcx+0Ch], r12b
0x180034913  jz      short loc_18003494F
0x180034915  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003491a  mov     rcx, [rax]
0x18003491d  cmp     [rcx+0B8h], r12
0x180034924  jz      short loc_18003494F
0x180034926  call    cs:__imp_GetLastError
0x18003492c  mov     ebx, eax
0x18003492e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034933  mov     rcx, [rax]
0x180034936  mov     r9d, ebx
0x180034939  mov     r8, rsi
0x18003493c  lea     rdx, aSWaitforsingle_0; "%s: WaitForSingleObjectEx failed: 0x%08"...
0x180034943  mov     rcx, [rcx+0B8h]; Stream
0x18003494a  call    fwprintf_s
0x18003494f  call    cs:__imp_GetLastError
0x180034955  mov     r8d, eax
0x180034958  mov     rdx, rsi
0x18003495b  lea     rcx, aSWaitforsingle_0; "%s: WaitForSingleObjectEx failed: 0x%08"...
0x180034962  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180034967  jmp     short loc_1800349E2
0x180034969  mov     edi, 801C001Ch
0x18003496e  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034973  mov     rcx, [rax]
0x180034976  lea     rsi, aDsrcmddeviceen_3; "DsrCmdDeviceEnroller::Leave"
0x18003497d  lea     rbx, aSWaitforsingle_15; "%s: WaitForSingleObjectEx timed out 0x%"...
0x180034984  cmp     [rcx], r12b
0x180034987  jz      short loc_1800349D3
0x180034989  mov     r8d, edi
0x18003498c  mov     rdx, rsi
0x18003498f  mov     rcx, rbx; Format
0x180034992  call    wprintf
0x180034997  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18003499c  mov     rcx, [rax]
0x18003499f  cmp     [rcx+0Ch], r12b
0x1800349a3  jz      short loc_1800349D3
0x1800349a5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800349aa  mov     rcx, [rax]
0x1800349ad  cmp     [rcx+0B8h], r12
0x1800349b4  jz      short loc_1800349D3
0x1800349b6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800349bb  mov     rcx, [rax]
0x1800349be  mov     r9d, edi
0x1800349c1  mov     r8, rsi
0x1800349c4  mov     rdx, rbx; Format
0x1800349c7  mov     rcx, [rcx+0B8h]; Stream
0x1800349ce  call    fwprintf_s
0x1800349d3  mov     r8d, edi
0x1800349d6  mov     rcx, rbx
0x1800349d9  jmp     loc_1800348C0
0x1800349de  mov     edi, [r14+20h]
0x1800349e2  test    edi, edi
0x1800349e4  jns     short loc_1800349F0
0x1800349e6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x1800349eb  jmp     loc_180034811
0x1800349f0  mov     [rsp+1D0h+IsMember], r12d
0x1800349f5  lea     rcx, [rsp+1D0h+IsMember]; IsMember
0x1800349fa  call    ?IsCurrentUserSystem@@YAJAEAH@Z; IsCurrentUserSystem(int &)
0x1800349ff  mov     edi, eax
0x180034a01  test    eax, eax
0x180034a03  jns     short loc_180034A16
0x180034a05  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034a0a  lea     rbx, aSIscurrentuser_0; "%s: IsCurrentUserSystem check failed 0x"...
0x180034a11  jmp     loc_1800346FF
0x180034a16  cmp     [rsp+1D0h+IsMember], r12d
0x180034a1b  jz      loc_180034AAA
0x180034a21  xor     ecx, ecx
0x180034a23  call    ?NgcRemoveAllRegistrations@NgcRegController@@SAJW4_NGC_REG_REMOVE_OPTIONS@@@Z; NgcRegController::NgcRemoveAllRegistrations(_NGC_REG_REMOVE_OPTIONS)
0x180034a28  mov     edi, eax
0x180034a2a  test    eax, eax
0x180034a2c  jns     loc_180034B04
0x180034a32  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034a37  mov     rcx, [rax]
0x180034a3a  lea     rbx, aSNgcregNgcremo_0; "%s: NgcReg::NgcRemoveAllRegistrations f"...
0x180034a41  cmp     [rcx], r12b
0x180034a44  jz      short loc_180034A90
0x180034a46  mov     r8d, edi
0x180034a49  mov     rdx, rsi
0x180034a4c  mov     rcx, rbx; Format
0x180034a4f  call    wprintf
0x180034a54  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034a59  mov     rcx, [rax]
0x180034a5c  cmp     [rcx+0Ch], r12b
0x180034a60  jz      short loc_180034A90
0x180034a62  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034a67  mov     rcx, [rax]
0x180034a6a  cmp     [rcx+0B8h], r12
0x180034a71  jz      short loc_180034A90
0x180034a73  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034a78  mov     rcx, [rax]
0x180034a7b  mov     r9d, edi
0x180034a7e  mov     r8, rsi
0x180034a81  mov     rdx, rbx; Format
0x180034a84  mov     rcx, [rcx+0B8h]; Stream
0x180034a8b  call    fwprintf_s
0x180034a90  mov     r8d, edi
0x180034a93  mov     rdx, rsi
0x180034a96  mov     rcx, rbx; unsigned __int16 *
0x180034a99  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180034a9e  mov     ecx, edi; int
0x180034aa0  call    ?WriteNgcRemoveAllRegistrationFailureEvent@Logger@@SAJJ@Z; Logger::WriteNgcRemoveAllRegistrationFailureEvent(long)
0x180034aa5  mov     edi, r12d
0x180034aa8  jmp     short loc_180034B04
0x180034aaa  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034aaf  mov     rcx, [rax]
0x180034ab2  lea     rbx, aOnlyTheNgcForT; "Only the NGC for the current user is be"...
0x180034ab9  cmp     [rcx], r12b
0x180034abc  jz      short loc_180034AFC
0x180034abe  mov     rcx, rbx; Format
0x180034ac1  call    wprintf
0x180034ac6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034acb  mov     rcx, [rax]
0x180034ace  cmp     [rcx+0Ch], r12b
0x180034ad2  jz      short loc_180034AFC
0x180034ad4  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034ad9  mov     rdx, [rax]
0x180034adc  cmp     [rdx+0B8h], r12
0x180034ae3  jz      short loc_180034AFC
0x180034ae5  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034aea  mov     rcx, [rax]
0x180034aed  mov     rdx, rbx; Format
0x180034af0  mov     rcx, [rcx+0B8h]; Stream
0x180034af7  call    fwprintf_s
0x180034afc  mov     rcx, rbx; Format
0x180034aff  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180034b04  cmp     [rsp+1D0h+var_1A0], r12d
0x180034b09  jz      loc_180034C20
0x180034b0f  test    r15d, r15d
0x180034b12  jz      loc_180034C20
0x180034b18  mov     [rsp+1D0h+var_1A0], r12d
0x180034b1d  xor     edx, edx; unsigned __int16 **
0x180034b1f  lea     rcx, [rsp+1D0h+var_1A0]; int *
0x180034b24  call    ?IsLocalMachineDomainJoined@@YAJPEAHPEAPEAG@Z; IsLocalMachineDomainJoined(int *,ushort * *)
0x180034b29  mov     edi, eax
0x180034b2b  test    eax, eax
0x180034b2d  jns     short loc_180034B40
0x180034b2f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x180034b34  lea     rbx, aSIslocalmachin_1; "%s: IsLocalMachineDomainJoined failed 0"...
0x180034b3b  jmp     loc_1800346FF
  ... truncated ...
```
