# CRASConnectionTestingPage::ConnectThread(CRASConnectionTestingPage *)

- ea: `0x18001b0f0`
- end: `0x18001b877`
- name: `?ConnectThread@CRASConnectionTestingPage@@KAP6AKPEAX@ZPEAV1@@Z`
- size: `1927`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180010c38`
- `0x18001b0f0`
- `0x18001b880`
- `0x18001b96c`
- `0x18002b970`
- `0x18002be68`
- `0x18002f382`
- `0x18002f3b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001b4f0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001b4f0`
- `connect!IsInternetConnectedGUID` at `0x18001b562`
- `connect!IsInternetConnectedGUID` at `0x18001b562`
- `RASAPI32!RasGetEntryHrasconnW` at `0x18001b1e8`
- `RASAPI32!RasGetEntryHrasconnW` at `0x18001b1e8`
- `RASAPI32!RasHangUpW` at `0x18001b6f0`
- `RASAPI32!RasHangUpW` at `0x18001b6f0`
- `RASDLG!RasDialDlgW` at `0x18001b323`
- `RASDLG!RasDialDlgW` at `0x18001b323`
- `USER32!PostMessageW` at `0x18001b82f`
- `USER32!PostMessageW` at `0x18001b82f`
- `USER32!SetWindowTextW` at `0x18001b14c`
- `USER32!SetWindowTextW` at `0x18001b490`
- `USER32!SetWindowTextW` at `0x18001b766`
- `USER32!SetWindowTextW` at `0x18001b14c`
- `USER32!SetWindowTextW` at `0x18001b490`
- `USER32!SetWindowTextW` at `0x18001b766`
- `USER32!ShowWindow` at `0x18001b13b`
- `USER32!ShowWindow` at `0x18001b158`
- `USER32!ShowWindow` at `0x18001b749`
- `USER32!ShowWindow` at `0x18001b755`
- `USER32!ShowWindow` at `0x18001b13b`
- `USER32!ShowWindow` at `0x18001b158`
- `USER32!ShowWindow` at `0x18001b749`
- `USER32!ShowWindow` at `0x18001b755`
- `USER32!SendMessageW` at `0x18001b16f`
- `USER32!SendMessageW` at `0x18001b4c9`
- `USER32!SendMessageW` at `0x18001b4de`
- `USER32!SendMessageW` at `0x18001b73d`
- `USER32!SendMessageW` at `0x18001b16f`
- `USER32!SendMessageW` at `0x18001b4c9`
- `USER32!SendMessageW` at `0x18001b4de`
- `USER32!SendMessageW` at `0x18001b73d`
- `USER32!GetParent` at `0x18001b81a`
- `USER32!GetParent` at `0x18001b81a`
- `rtutils!TracePrintfExA` at `0x18001b363`
- `rtutils!TracePrintfExA` at `0x18001b382`
- `rtutils!TracePrintfExA` at `0x18001b3da`
- `rtutils!TracePrintfExA` at `0x18001b47a`
- `rtutils!TracePrintfExA` at `0x18001b546`
- `rtutils!TracePrintfExA` at `0x18001b588`
- `rtutils!TracePrintfExA` at `0x18001b5ad`
- `rtutils!TracePrintfExA` at `0x18001b616`
- `rtutils!TracePrintfExA` at `0x18001b647`
- `rtutils!TracePrintfExA` at `0x18001b69f`
- `rtutils!TracePrintfExA` at `0x18001b6e7`
- `rtutils!TracePrintfExA` at `0x18001b714`
- `rtutils!TracePrintfExA` at `0x18001b7e1`
- `rtutils!TracePrintfExA` at `0x18001b810`
- `rtutils!TracePrintfExA` at `0x18001b84c`
- `rtutils!TracePrintfExA` at `0x18001b363`
- `rtutils!TracePrintfExA` at `0x18001b382`
- `rtutils!TracePrintfExA` at `0x18001b3da`
- `rtutils!TracePrintfExA` at `0x18001b47a`
- `rtutils!TracePrintfExA` at `0x18001b546`
- `rtutils!TracePrintfExA` at `0x18001b588`
- `rtutils!TracePrintfExA` at `0x18001b5ad`
- `rtutils!TracePrintfExA` at `0x18001b616`
- `rtutils!TracePrintfExA` at `0x18001b647`
- `rtutils!TracePrintfExA` at `0x18001b69f`
- `rtutils!TracePrintfExA` at `0x18001b6e7`
- `rtutils!TracePrintfExA` at `0x18001b714`
- `rtutils!TracePrintfExA` at `0x18001b7e1`
- `rtutils!TracePrintfExA` at `0x18001b810`
- `rtutils!TracePrintfExA` at `0x18001b84c`

## string_xrefs

- `0x18001b357`: `ConnectThread:RasDialDlg failed with error: %d`
- `0x18001b378`: `ConnectThread:Successfully made RAS Connection`
- `0x18001b470`: `ConnectThread:Performing Internet testing`
- `0x18001b57c`: `ConnectThread:IsConnectedToInternet returned: hr = %#x`
- `0x18001b5a1`: `ConnectThread:User pressed cancel hence exit`
- `0x18001b6d4`: `ConnectThread:Disconnecting - error = %d, cancel flag = %d`
- `0x18001b804`: `ConnectThread: Going to next page`
- `0x18001b840`: `ConnectThread: Done`

## pseudocode

```c
__int64 __fastcall CRASConnectionTestingPage::ConnectThread(char *Parameter)
{
  unsigned int v1; // esi
  HRASCONN *v2; // r15
  HWND v4; // rcx
  __int64 v5; // rcx
  const wchar_t *v6; // r8
  int v7; // r13d
  unsigned int v8; // edi
  unsigned int v9; // edx
  struct _RASNCWINFO *RASConnectionPropertiesFromPropertyBag; // r14
  int EntryHrasconnW; // eax
  __int16 *v12; // r14
  HWND v13; // rax
  DWORD dwError; // edx
  int v15; // eax
  HWND v16; // rcx
  LPARAM StringPcch; // r15
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  unsigned __int16 *v21; // rcx
  int v22; // r14d
  int v23; // eax
  DWORD v24; // eax
  __int64 v25; // rcx
  char *v26; // rdx
  __int64 (__fastcall *v27)(__int64, char *, const wchar_t *, GUID *, int); // rax
  int v28; // eax
  int v29; // eax
  HWND Parent; // rax
  unsigned __int16 *v32; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v33; // [rsp+38h] [rbp-C8h]
  tagRASDIALDLG Info; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v35[6]; // [rsp+70h] [rbp-90h] BYREF
  int v36; // [rsp+88h] [rbp-78h]
  int *v37; // [rsp+90h] [rbp-70h]
  int v38; // [rsp+98h] [rbp-68h]
  __int64 (__usercall *v39)@<rax>(CRASConnectionTestingPage *@<rcx>, HRASCONN@<rdx>, enum tagRASCONNSTATE@<r8d>, unsigned __int16 *@<r9>, unsigned __int16 *); // [rsp+A8h] [rbp-58h]
  char *v40; // [rsp+B0h] [rbp-50h]
  int v41; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v42[8]; // [rsp+D4h] [rbp-2Ch] BYREF
  unsigned __int16 v43[257]; // [rsp+DCh] [rbp-24h] BYREF
  unsigned __int16 v44[257]; // [rsp+2DEh] [rbp+1DEh] BYREF
  unsigned __int16 v45[16]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v1 = 0;
  v2 = (HRASCONN *)(Parameter + 1144);
  *((_DWORD *)Parameter + 283) = 0;
  v4 = (HWND)*((_QWORD *)Parameter + 3);
  *v2 = 0;
  ShowWindow(v4, 5);
  SetWindowTextW(*((HWND *)Parameter + 4), &cchOriginalDestLength);
  ShowWindow(*((HWND *)Parameter + 4), 5);
  SendMessageW(*((HWND *)Parameter + 3), 0x40Au, 1u, 100);
  v5 = *((_QWORD *)Parameter + 10);
  v32 = 0;
  v6 = L"SkipConnectionLaunch";
  if ( *((_DWORD *)Parameter + 15) )
    v6 = L"SkipConnectionTesting";
  (*(void (__fastcall **)(__int64, char *, const wchar_t *, unsigned __int16 **, _QWORD))(*(_QWORD *)v5 + 48LL))(
    v5,
    Parameter + 44,
    v6,
    &v32,
    0);
  if ( v32 )
  {
    v22 = 0;
    goto LABEL_76;
  }
  v7 = 0;
  v8 = 0;
  RASConnectionPropertiesFromPropertyBag = CRASConnectionTestingPage::GetRASConnectionPropertiesFromPropertyBag((CRASConnectionTestingPage *)Parameter);
  if ( !RASConnectionPropertiesFromPropertyBag )
  {
    v22 = 1;
    if ( g_dwTraceId == -1 )
      goto LABEL_76;
    v1 = 1;
    TracePrintfExA(g_dwTraceId, 0xCu, "Failed to get the m_pRasNcwInfo. hr = %#x", 0);
    goto LABEL_66;
  }
  CRASConnectionTestingPage::HrSetHeaderTitle((CRASConnectionTestingPage *)Parameter, v9);
  EntryHrasconnW = RasGetEntryHrasconnW(
                     (char *)RASConnectionPropertiesFromPropertyBag + 12,
                     (char *)RASConnectionPropertiesFromPropertyBag + 1038,
                     v2);
  if ( !EntryHrasconnW || EntryHrasconnW == 668 )
  {
    if ( *v2 )
      goto LABEL_31;
    v1 = 1;
  }
  else
  {
    if ( EntryHrasconnW > 0 )
      v8 = (unsigned __int16)EntryHrasconnW | 0x80070000;
    else
      v8 = EntryHrasconnW;
    v1 = v8;
  }
  if ( v1 != 1 )
    goto LABEL_31;
  memset(&Info, 0, sizeof(Info));
  memset_0(v35, 0, 0x58u);
  memset_0(v42, 0, 0x42Cu);
  v41 = 1072;
  v32 = (unsigned __int16 *)((char *)RASConnectionPropertiesFromPropertyBag + 1820);
  StringCchCopyW(v43, 0x101u, (unsigned __int16 *)RASConnectionPropertiesFromPropertyBag + 910);
  v33 = (unsigned __int16 *)((char *)RASConnectionPropertiesFromPropertyBag + 2848);
  StringCchCopyW(v45, 0x10u, (unsigned __int16 *)RASConnectionPropertiesFromPropertyBag + 1424);
  v12 = (__int16 *)((char *)RASConnectionPropertiesFromPropertyBag + 2334);
  EncodePasswordW(v12);
  StringCchCopyW(v44, 0x101u, (unsigned __int16 *)v12);
  EncodePasswordW(v12);
  EncodePasswordW((__int16 *)v44);
  v13 = (HWND)*((_QWORD *)Parameter + 1);
  v36 |= 0xFu;
  Info.hwndOwner = v13;
  Info.dwSize = 48;
  v39 = CRASConnectionTestingPage::RasDialInternalCallBack;
  v35[0] = 1;
  v37 = &v41;
  Info.reserved = (ULONG_PTR)v35;
  v40 = Parameter;
  if ( RasDialDlgW((LPWSTR)Parameter + 301, (LPWSTR)Parameter + 44, 0, &Info) )
  {
    v1 = 0;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "ConnectThread:Successfully made RAS Connection");
  }
  else
  {
    dwError = Info.dwError;
    if ( Info.dwError )
    {
      if ( (int)Info.dwError > 0 )
        v1 = LOWORD(Info.dwError) | 0x80070000;
      else
        v1 = Info.dwError;
    }
    else
    {
      v1 = 1;
    }
    if ( g_dwTraceId == -1 )
      goto LABEL_25;
    TracePrintfExA(g_dwTraceId, 0xCu, "ConnectThread:RasDialDlg failed with error: %d", Info.dwError);
  }
  dwError = Info.dwError;
LABEL_25:
  if ( !*((_DWORD *)Parameter + 282) )
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, _QWORD, int))(**((_QWORD **)Parameter + 10) + 40LL))(
            *((_QWORD *)Parameter + 10),
            Parameter + 44,
            L"ConnectionResult",
            dwError,
            2);
    v8 = v15;
    if ( v15 < 0 && g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Unable to set the tested flag in the property bag. hr = %#x", v15);
  }
  if ( v38 )
  {
    StringCchCopyW(v32, 0x101u, v43);
    StringCchCopyW(v33, 0x11u, v45);
    EncodePasswordW((__int16 *)v44);
    StringCchCopyW((unsigned __int16 *)v12, 0x101u, v44);
    EncodePasswordW((__int16 *)v44);
    EncodePasswordW(v12);
  }
LABEL_31:
  if ( *((_DWORD *)Parameter + 15) && !v1 && !*((_DWORD *)Parameter + 282) )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "ConnectThread:Performing Internet testing");
    v16 = (HWND)*((_QWORD *)Parameter + 4);
    if ( v16 )
    {
      SetWindowTextW(v16, &cchOriginalDestLength);
      LODWORD(v32) = 0;
      StringPcch = PszLoadStringPcch(hInst);
      if ( StringPcch )
      {
        v18 = SendMessageW(*((HWND *)Parameter + 2), 0x481u, *((_QWORD *)Parameter + 1), 0);
        SendMessageW(*((HWND *)Parameter + 2), 0x47Eu, v18, StringPcch);
      }
      v2 = (HRASCONN *)(Parameter + 1144);
    }
    Sleep(0x1B58u);
    if ( *((_DWORD *)Parameter + 282) )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "ConnectThread:User pressed cancel hence exit");
    }
    else
    {
      v19 = *((_QWORD *)Parameter + 10);
      v32 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, char *, const wchar_t *, unsigned __int16 **, _QWORD))(*(_QWORD *)v19 + 48LL))(
              v19,
              Parameter + 44,
              L"ConnectionGUID",
              &v32,
              0);
      if ( v20 >= 0 )
      {
        v21 = v32;
      }
      else
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "CRASConnectionTestingPage::InitializeConnectionGUID:Unable to get c_szConnectionGUID info. hr = %#x",
            v20);
        v21 = 0;
        v32 = 0;
      }
      if ( !v21 || (v8 = IsInternetConnectedGUID(v21, Parameter + 1128)) != 0 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "ConnectThread:IsConnectedToInternet returned: hr = %#x", v8);
        v7 = 1;
      }
    }
  }
  if ( !*((_DWORD *)Parameter + 282) )
  {
    if ( v1 )
    {
      if ( !v7 )
        goto LABEL_66;
    }
    else if ( !v7 )
    {
      v22 = 0;
      v23 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, __int64, int))(**((_QWORD **)Parameter + 10)
                                                                                     + 40LL))(
              *((_QWORD *)Parameter + 10),
              Parameter + 44,
              L"ConnectionTested",
              1,
              2);
      v8 = v23;
      if ( v23 >= 0 )
      {
        v8 = 0;
      }
      else if ( g_dwTraceId != -1 )
      {
        TracePrintfExA(g_dwTraceId, 0xCu, "Unable to set the tested flag in the property bag. hr = %#x", v23);
      }
      goto LABEL_68;
    }
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Internet Testing failed. hr = %#x", v8);
    v8 = (*(__int64 (__fastcall **)(_QWORD, char *, const wchar_t *, __int64, int))(**((_QWORD **)Parameter + 10) + 40LL))(
           *((_QWORD *)Parameter + 10),
           Parameter + 44,
           L"InternetTestFailed",
           1,
           2);
  }
LABEL_66:
  v22 = 1;
  if ( v1 )
    goto LABEL_76;
  if ( v7 )
    goto LABEL_69;
LABEL_68:
  if ( *((_DWORD *)Parameter + 282) )
  {
LABEL_69:
    if ( *v2 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "ConnectThread:Disconnecting - error = %d, cancel flag = %d",
          v8,
          *((_DWORD *)Parameter + 282));
      v24 = RasHangUpW(*v2);
      if ( v24 && g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed to disconnect the connection again. dwErr = %d", v24);
    }
LABEL_76:
    if ( *((_DWORD *)Parameter + 282) )
      goto LABEL_78;
  }
  SendMessageW(*((HWND *)Parameter + 3), 0x40Au, 0, 100);
  ShowWindow(*((HWND *)Parameter + 3), 0);
  ShowWindow(*((HWND *)Parameter + 4), 0);
  SetWindowTextW(*((HWND *)Parameter + 4), &cchOriginalDestLength);
LABEL_78:
  if ( v22 )
  {
    v25 = *((_QWORD *)Parameter + 10);
    v26 = Parameter + 44;
    v27 = *(__int64 (__fastcall **)(__int64, char *, const wchar_t *, GUID *, int))(*(_QWORD *)v25 + 40LL);
    if ( *((_DWORD *)Parameter + 15) )
    {
      v28 = v27(v25, v26, L"ConnectionDiagnostics", &CLSID_RASCTIFinishPage, 2);
      if ( v28 < 0 && g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "Unable to set the tested flag in the property bag. hr = %#x",
          (unsigned int)v28);
    }
    else
    {
      v29 = v27(v25, v26, L"ConnectionDiagnostics", &CLSID_RASCTWFinishPage, 2);
      if ( v29 < 0 && g_dwTraceId != -1 )
        TracePrintfExA(
          g_dwTraceId,
          0xCu,
          "Unable to set the diagnostics flag in the property bag. hr = %#x",
          (unsigned int)v29);
    }
  }
  *((_DWORD *)Parameter + 283) = 1;
  if ( !*((_DWORD *)Parameter + 282) )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "ConnectThread: Going to next page");
    Parent = GetParent(*((HWND *)Parameter + 1));
    PostMessageW(Parent, 0x471u, 1u, 0);
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "ConnectThread: Done");
  return 0;
}

```

## disassembly

```asm
0x18001b0f0  push    rbp
0x18001b0f2  push    rbx
0x18001b0f3  push    rsi
0x18001b0f4  push    rdi
0x18001b0f5  push    r12
0x18001b0f7  push    r13
0x18001b0f9  push    r14
0x18001b0fb  push    r15
0x18001b0fd  lea     rbp, [rsp-418h]
0x18001b105  sub     rsp, 518h
0x18001b10c  mov     rax, cs:__security_cookie
0x18001b113  xor     rax, rsp
0x18001b116  mov     [rbp+450h+var_50], rax
0x18001b11d  xor     esi, esi
0x18001b11f  lea     r15, [rcx+478h]
0x18001b126  mov     rbx, rcx
0x18001b129  mov     [rcx+46Ch], esi
0x18001b12f  mov     rcx, [rcx+18h]; hWnd
0x18001b133  mov     [r15], rsi
0x18001b136  lea     edi, [rsi+5]
0x18001b139  mov     edx, edi; nCmdShow
0x18001b13b  call    cs:__imp_ShowWindow
0x18001b141  mov     rcx, [rbx+20h]; hWnd
0x18001b145  lea     rdx, cchOriginalDestLength; lpString
0x18001b14c  call    cs:__imp_SetWindowTextW
0x18001b152  mov     rcx, [rbx+20h]; hWnd
0x18001b156  mov     edx, edi; nCmdShow
0x18001b158  call    cs:__imp_ShowWindow
0x18001b15e  mov     rcx, [rbx+18h]; hWnd
0x18001b162  lea     r9d, [rsi+64h]; lParam
0x18001b166  mov     edx, 40Ah; Msg
0x18001b16b  lea     r8d, [rsi+1]; wParam
0x18001b16f  call    cs:__imp_SendMessageW
0x18001b175  lea     r12, [rbx+2Ch]
0x18001b179  mov     rcx, [rbx+50h]
0x18001b17d  lea     r9, [rsp+550h+var_520]
0x18001b182  mov     [rsp+550h+var_520], rsi
0x18001b187  lea     r8, aSkipconnection_4; "SkipConnectionLaunch"
0x18001b18e  mov     [rsp+550h+var_530], rsi
0x18001b193  mov     rdx, r12
0x18001b196  mov     rax, [rcx]
0x18001b199  mov     rax, [rax+30h]
0x18001b19d  cmp     [rbx+3Ch], esi
0x18001b1a0  jz      short loc_18001B1A9
0x18001b1a2  lea     r8, aSkipconnection_5; "SkipConnectionTesting"
0x18001b1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1ae  cmp     [rsp+550h+var_520], rsi
0x18001b1b3  jnz     loc_18001B71C
0x18001b1b9  mov     rcx, rbx; this
0x18001b1bc  mov     r13d, esi
0x18001b1bf  mov     edi, esi
0x18001b1c1  call    ?GetRASConnectionPropertiesFromPropertyBag@CRASConnectionTestingPage@@IEAAPEAU_RASNCWINFO@@XZ; CRASConnectionTestingPage::GetRASConnectionPropertiesFromPropertyBag(void)
0x18001b1c6  mov     r14, rax
0x18001b1c9  test    rax, rax
0x18001b1cc  jz      loc_18001B679
0x18001b1d2  mov     rcx, rbx; this
0x18001b1d5  call    ?HrSetHeaderTitle@CRASConnectionTestingPage@@IEAAJI@Z; CRASConnectionTestingPage::HrSetHeaderTitle(uint)
0x18001b1da  lea     rdx, [r14+40Eh]
0x18001b1e1  mov     r8, r15
0x18001b1e4  lea     rcx, [r14+0Ch]
0x18001b1e8  call    cs:__imp_RasGetEntryHrasconnW
0x18001b1ee  test    eax, eax
0x18001b1f0  jz      short loc_18001B20E
0x18001b1f2  cmp     eax, 29Ch
0x18001b1f7  jz      short loc_18001B20E
0x18001b1f9  test    eax, eax
0x18001b1fb  jg      short loc_18001B201
0x18001b1fd  mov     edi, eax
0x18001b1ff  jmp     short loc_18001B20A
0x18001b201  movzx   edi, ax
0x18001b204  or      edi, 80070000h
0x18001b20a  mov     esi, edi
0x18001b20c  jmp     short loc_18001B21C
0x18001b20e  cmp     [r15], rsi
0x18001b211  jnz     loc_18001B443
0x18001b217  mov     esi, 1
0x18001b21c  cmp     esi, 1
0x18001b21f  jnz     loc_18001B443
0x18001b225  xorps   xmm0, xmm0
0x18001b228  lea     r8d, [rsi+57h]; Size
0x18001b22c  xor     edx, edx; Val
0x18001b22e  lea     rcx, [rsp+550h+var_4E0]; void *
0x18001b233  movups  xmmword ptr [rsp+550h+Info.dwSize], xmm0
0x18001b238  movups  xmmword ptr [rsp+550h+Info.xDlg], xmm0
0x18001b23d  movups  xmmword ptr [rsp+550h+Info.reserved], xmm0
0x18001b242  call    memset_0
0x18001b247  xor     edx, edx; Val
0x18001b249  lea     rcx, [rbp+450h+var_47C]; void *
0x18001b24d  mov     r8d, 42Ch; Size
0x18001b253  call    memset_0
0x18001b258  lea     rax, [r14+71Ch]
0x18001b25f  mov     [rbp+450h+var_480], 430h
0x18001b266  mov     esi, 101h
0x18001b26b  mov     [rsp+550h+var_520], rax
0x18001b270  mov     r8, rax; unsigned __int16 *
0x18001b273  lea     rcx, [rbp+450h+var_474]; unsigned __int16 *
0x18001b277  mov     edx, esi; unsigned __int64
0x18001b279  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b27e  lea     rax, [r14+0B20h]
0x18001b285  mov     edx, 10h; unsigned __int64
0x18001b28a  mov     r8, rax; unsigned __int16 *
0x18001b28d  mov     [rsp+550h+var_518], rax
0x18001b292  lea     rcx, [rbp+450h+var_70]; unsigned __int16 *
0x18001b299  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b29e  add     r14, 91Eh
0x18001b2a5  mov     rcx, r14
0x18001b2a8  call    EncodePasswordW
0x18001b2ad  mov     r8, r14; unsigned __int16 *
0x18001b2b0  lea     rcx, [rbp+450h+var_272]; unsigned __int16 *
0x18001b2b7  mov     edx, esi; unsigned __int64
0x18001b2b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b2be  mov     rcx, r14
0x18001b2c1  call    EncodePasswordW
0x18001b2c6  lea     rcx, [rbp+450h+var_272]
0x18001b2cd  call    EncodePasswordW
0x18001b2d2  mov     rax, [rbx+8]
0x18001b2d6  lea     rdx, [rbx+58h]; lpszEntry
0x18001b2da  or      [rbp+450h+var_4C8], 0Fh
0x18001b2de  lea     rcx, [rbx+25Ah]; lpszPhonebook
0x18001b2e5  mov     [rsp+550h+Info.hwndOwner], rax
0x18001b2ea  lea     r9, [rsp+550h+Info]; lpInfo
0x18001b2ef  lea     rax, ?RasDialInternalCallBack@CRASConnectionTestingPage@@KAHPEAXPEAUHRASCONN__@@W4tagRASCONNSTATE@@PEAG3@Z; CRASConnectionTestingPage::RasDialInternalCallBack(void *,HRASCONN__ *,tagRASCONNSTATE,ushort *,ushort *)
0x18001b2f6  mov     [rsp+550h+Info.dwSize], 30h ; '0'
0x18001b2fe  mov     [rbp+450h+var_4A8], rax
0x18001b302  xor     r8d, r8d; lpszPhoneNumber
0x18001b305  lea     rax, [rbp+450h+var_480]
0x18001b309  mov     [rsp+550h+var_4E0], 1
0x18001b311  mov     [rbp+450h+var_4C0], rax
0x18001b315  lea     rax, [rsp+550h+var_4E0]
0x18001b31a  mov     [rsp+550h+Info.reserved], rax
0x18001b31f  mov     [rbp+450h+var_4A0], rbx
0x18001b323  call    cs:__imp_RasDialDlgW
0x18001b329  test    eax, eax
0x18001b32b  jnz     short loc_18001B36B
0x18001b32d  mov     edx, [rsp+550h+Info.dwError]
0x18001b331  test    edx, edx
0x18001b333  jnz     short loc_18001B33A
0x18001b335  lea     esi, [rax+1]
0x18001b338  jmp     short loc_18001B349
0x18001b33a  jg      short loc_18001B340
0x18001b33c  mov     esi, edx
0x18001b33e  jmp     short loc_18001B349
0x18001b340  movzx   esi, dx
0x18001b343  or      esi, 80070000h
0x18001b349  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b34f  cmp     ecx, 0FFFFFFFFh
0x18001b352  jz      short loc_18001B38C
0x18001b354  mov     r9d, edx
0x18001b357  lea     r8, aConnectthreadR; "ConnectThread:RasDialDlg failed with er"...
0x18001b35e  mov     edx, 0Ch; dwFlags
0x18001b363  call    cs:__imp_TracePrintfExA
0x18001b369  jmp     short loc_18001B388
0x18001b36b  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b371  xor     esi, esi
0x18001b373  cmp     ecx, 0FFFFFFFFh
0x18001b376  jz      short loc_18001B388
0x18001b378  lea     r8, aConnectthreadS; "ConnectThread:Successfully made RAS Con"...
0x18001b37f  lea     edx, [rsi+0Ch]; dwFlags
0x18001b382  call    cs:__imp_TracePrintfExA
0x18001b388  mov     edx, [rsp+550h+Info.dwError]
0x18001b38c  cmp     [rbx+468h], r13d
0x18001b393  jnz     short loc_18001B3E0
0x18001b395  mov     rcx, [rbx+50h]
0x18001b399  lea     r8, aConnectionresu_0; "ConnectionResult"
0x18001b3a0  mov     r9d, edx
0x18001b3a3  mov     rdx, r12
0x18001b3a6  mov     dword ptr [rsp+550h+var_530], 2
0x18001b3ae  mov     rax, [rcx]
0x18001b3b1  mov     rax, [rax+28h]
0x18001b3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3ba  mov     edi, eax
0x18001b3bc  test    eax, eax
0x18001b3be  jns     short loc_18001B3E0
0x18001b3c0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b3c6  cmp     ecx, 0FFFFFFFFh
0x18001b3c9  jz      short loc_18001B3E0
0x18001b3cb  mov     r9d, eax
0x18001b3ce  lea     r8, aUnableToSetThe_0; "Unable to set the tested flag in the pr"...
0x18001b3d5  mov     edx, 0Ch; dwFlags
0x18001b3da  call    cs:__imp_TracePrintfExA
0x18001b3e0  cmp     [rbp+450h+var_4B8], r13d
0x18001b3e4  jz      short loc_18001B443
0x18001b3e6  mov     rcx, [rsp+550h+var_520]; unsigned __int16 *
0x18001b3eb  lea     r8, [rbp+450h+var_474]; unsigned __int16 *
0x18001b3ef  mov     edx, 101h; unsigned __int64
0x18001b3f4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b3f9  mov     rcx, [rsp+550h+var_518]; unsigned __int16 *
0x18001b3fe  lea     r8, [rbp+450h+var_70]; unsigned __int16 *
0x18001b405  mov     edx, 11h; unsigned __int64
0x18001b40a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b40f  lea     rcx, [rbp+450h+var_272]
0x18001b416  call    EncodePasswordW
0x18001b41b  lea     r8, [rbp+450h+var_272]; unsigned __int16 *
0x18001b422  mov     edx, 101h; unsigned __int64
0x18001b427  mov     rcx, r14; unsigned __int16 *
0x18001b42a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b42f  lea     rcx, [rbp+450h+var_272]
0x18001b436  call    EncodePasswordW
0x18001b43b  mov     rcx, r14
0x18001b43e  call    EncodePasswordW
0x18001b443  cmp     [rbx+3Ch], r13d
0x18001b447  jz      loc_18001B5B3
0x18001b44d  test    esi, esi
0x18001b44f  jnz     loc_18001B5B3
0x18001b455  lea     r14, [rbx+468h]
0x18001b45c  cmp     [r14], r13d
0x18001b45f  jnz     loc_18001B5B3
0x18001b465  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b46b  cmp     ecx, 0FFFFFFFFh
0x18001b46e  jz      short loc_18001B480
0x18001b470  lea     r8, aConnectthreadP; "ConnectThread:Performing Internet testi"...
0x18001b477  lea     edx, [rsi+0Ch]; dwFlags
0x18001b47a  call    cs:__imp_TracePrintfExA
0x18001b480  mov     rcx, [rbx+20h]; hWnd
0x18001b484  test    rcx, rcx
0x18001b487  jz      short loc_18001B4EB
0x18001b489  lea     rdx, cchOriginalDestLength; lpString
0x18001b490  call    cs:__imp_SetWindowTextW
0x18001b496  mov     rcx, cs:hInst; hModule
0x18001b49d  lea     r8, [rsp+550h+var_520]
0x18001b4a2  mov     edx, 0BDEh
0x18001b4a7  mov     dword ptr [rsp+550h+var_520], r13d
0x18001b4ac  call    PszLoadStringPcch
0x18001b4b1  mov     r15, rax
0x18001b4b4  test    rax, rax
0x18001b4b7  jz      short loc_18001B4E4
0x18001b4b9  mov     r8, [rbx+8]; wParam
0x18001b4bd  xor     r9d, r9d; lParam
0x18001b4c0  mov     rcx, [rbx+10h]; hWnd
0x18001b4c4  mov     edx, 481h; Msg
0x18001b4c9  call    cs:__imp_SendMessageW
0x18001b4cf  mov     rcx, [rbx+10h]; hWnd
0x18001b4d3  mov     r9, r15; lParam
0x18001b4d6  movsxd  r8, eax; wParam
0x18001b4d9  mov     edx, 47Eh; Msg
0x18001b4de  call    cs:__imp_SendMessageW
0x18001b4e4  lea     r15, [rbx+478h]
0x18001b4eb  mov     ecx, 1B58h; dwMilliseconds
0x18001b4f0  call    cs:__imp_Sleep
0x18001b4f6  cmp     [r14], r13d
0x18001b4f9  jnz     loc_18001B596
0x18001b4ff  mov     rcx, [rbx+50h]
0x18001b503  lea     r9, [rsp+550h+var_520]
0x18001b508  mov     [rsp+550h+var_520], r13
0x18001b50d  lea     r8, aConnectionguid_0; "ConnectionGUID"
0x18001b514  mov     rdx, r12
0x18001b517  mov     [rsp+550h+var_530], r13
0x18001b51c  mov     rax, [rcx]
0x18001b51f  mov     rax, [rax+30h]
0x18001b523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b528  test    eax, eax
0x18001b52a  jns     short loc_18001B555
0x18001b52c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b532  cmp     ecx, 0FFFFFFFFh
0x18001b535  jz      short loc_18001B54C
0x18001b537  mov     r9d, eax
0x18001b53a  lea     r8, aCrasconnection_3; "CRASConnectionTestingPage::InitializeCo"...
0x18001b541  mov     edx, 0Ch; dwFlags
0x18001b546  call    cs:__imp_TracePrintfExA
0x18001b54c  xor     ecx, ecx
0x18001b54e  mov     [rsp+550h+var_520], rcx
0x18001b553  jmp     short loc_18001B55A
0x18001b555  mov     rcx, [rsp+550h+var_520]
0x18001b55a  test    rcx, rcx
0x18001b55d  jz      short loc_18001B56E
0x18001b55f  mov     rdx, r14
0x18001b562  call    cs:__imp_IsInternetConnectedGUID
0x18001b568  mov     edi, eax
0x18001b56a  test    eax, eax
0x18001b56c  jz      short loc_18001B5B3
0x18001b56e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b574  cmp     ecx, 0FFFFFFFFh
0x18001b577  jz      short loc_18001B58E
0x18001b579  mov     r9d, edi
0x18001b57c  lea     r8, aConnectthreadI; "ConnectThread:IsConnectedToInternet ret"...
0x18001b583  mov     edx, 0Ch; dwFlags
0x18001b588  call    cs:__imp_TracePrintfExA
0x18001b58e  mov     r13d, 1
0x18001b594  jmp     short loc_18001B5B3
0x18001b596  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b59c  cmp     ecx, 0FFFFFFFFh
0x18001b59f  jz      short loc_18001B5B3
0x18001b5a1  lea     r8, aConnectthreadU; "ConnectThread:User pressed cancel hence"...
0x18001b5a8  mov     edx, 0Ch; dwFlags
0x18001b5ad  call    cs:__imp_TracePrintfExA
0x18001b5b3  cmp     dword ptr [rbx+468h], 0
0x18001b5ba  jnz     loc_18001B6A5
0x18001b5c0  test    esi, esi
0x18001b5c2  jnz     short loc_18001B628
0x18001b5c4  test    r13d, r13d
0x18001b5c7  jnz     short loc_18001B62D
0x18001b5c9  mov     rcx, [rbx+50h]
0x18001b5cd  lea     r9d, [r13+1]
0x18001b5d1  xor     esi, esi
0x18001b5d3  mov     dword ptr [rsp+550h+var_530], 2
0x18001b5db  lea     r8, aConnectiontest_1; "ConnectionTested"
0x18001b5e2  mov     rdx, r12
0x18001b5e5  mov     r14d, esi
0x18001b5e8  mov     rax, [rcx]
0x18001b5eb  mov     rax, [rax+28h]
  ... truncated ...
```
