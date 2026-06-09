# CNovInterDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x140021e00`
- end: `0x1400223be`
- name: `?OnInitDialog@CNovInterDlg@@QEAA_JI_K_JAEAH@Z`
- size: `1470`
- prototype: `__int64 __fastcall(CNovInterDlg *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140023830`

## callees

- `0x14000aa78`
- `0x14001f2f8`
- `0x14001fa68`
- `0x14001fca0`
- `0x140020310`
- `0x140020470`
- `0x140021e00`
- `0x1400242fc`
- `0x1400244dc`
- `0x140024734`
- `0x140024c44`
- `0x140028818`
- `0x140029518`
- `0x140029978`
- `0x14002ad4c`
- `0x14002c0a4`
- `0x140034ce4`
- `0x140034eac`
- `0x140035a10`
- `0x140037c8c`
- `0x140037ed0`
- `0x1400380dc`
- `0x14003c120`
- `0x14003fa5c`
- `0x14003fb64`
- `0x14003ff50`
- `0x14004ad80`

## import_xrefs

- `GDI32!DeleteObject` at `0x14002217b`
- `GDI32!DeleteObject` at `0x14002217b`
- `USER32!SendMessageW` at `0x1400220ca`
- `USER32!SendMessageW` at `0x140022101`
- `USER32!SendMessageW` at `0x140022273`
- `USER32!SendMessageW` at `0x1400220ca`
- `USER32!SendMessageW` at `0x140022101`
- `USER32!SendMessageW` at `0x140022273`
- `USER32!GetDlgItem` at `0x14002206b`
- `USER32!GetDlgItem` at `0x1400220e4`
- `USER32!GetDlgItem` at `0x140022112`
- `USER32!GetDlgItem` at `0x140022144`
- `USER32!GetDlgItem` at `0x140022192`
- `USER32!GetDlgItem` at `0x140022259`
- `USER32!GetDlgItem` at `0x14002206b`
- `USER32!GetDlgItem` at `0x1400220e4`
- `USER32!GetDlgItem` at `0x140022112`
- `USER32!GetDlgItem` at `0x140022144`
- `USER32!GetDlgItem` at `0x140022192`
- `USER32!GetDlgItem` at `0x140022259`
- `USER32!SetTimer` at `0x140022097`
- `USER32!SetTimer` at `0x140022097`
- `USER32!MapDialogRect` at `0x140021f69`
- `USER32!MapDialogRect` at `0x140021f69`
- `USER32!PostMessageW` at `0x14002232c`
- `USER32!PostMessageW` at `0x14002232c`
- `USER32!SetForegroundWindow` at `0x140021f4b`
- `USER32!SetForegroundWindow` at `0x140021f4b`
- `USER32!EnableWindow` at `0x14002207c`
- `USER32!EnableWindow` at `0x14002207c`
- `USER32!SetFocus` at `0x140022232`
- `USER32!SetFocus` at `0x140022232`
- `USER32!GetSysColor` at `0x140022243`
- `USER32!GetSysColor` at `0x140022243`
- `USER32!GetClientRect` at `0x140022306`
- `USER32!GetClientRect` at `0x140022306`
- `OLEAUT32!__imp_SysFreeString` at `0x140022055`
- `OLEAUT32!__imp_SysFreeString` at `0x1400222ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1400222f3`
- `OLEAUT32!__imp_SysFreeString` at `0x140022055`
- `OLEAUT32!__imp_SysFreeString` at `0x1400222ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1400222f3`
- `OLEAUT32!__imp_SysStringLen` at `0x140022010`
- `OLEAUT32!__imp_SysStringLen` at `0x140022010`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14002212e`
- `COMCTL32!__imp_SetWindowSubclass` at `0x140022160`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14002212e`
- `COMCTL32!__imp_SetWindowSubclass` at `0x140022160`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNovInterDlg::OnInitDialog(CNovInterDlg *this)
{
  void (*v2)(int); // r8
  CEventLogger *v3; // rcx
  signed int inited; // eax
  CEventLogger *v5; // rcx
  unsigned int v6; // ebx
  HWND *v7; // rsi
  int v8; // eax
  CEventLogger *v9; // rcx
  unsigned int v10; // r8d
  CEventLogger *v11; // rcx
  unsigned __int16 v12; // dx
  unsigned int v13; // ecx
  struct IRDPSRAPIAttendee *v14; // rcx
  unsigned __int16 *v15; // rbx
  HWND DlgItem; // rax
  HWND v17; // rax
  HWND v18; // rax
  HWND v19; // rax
  void *v20; // rcx
  HWND v21; // rax
  int v22; // edx
  OLECHAR *v23; // r14
  int UserInfoAsBSTR; // eax
  DWORD SysColor; // ebx
  HWND v26; // rax
  OLECHAR *v27; // rbx
  void (*v29)(int); // [rsp+28h] [rbp-48h]
  void (*v30)(unsigned __int16 *, unsigned __int16 *); // [rsp+30h] [rbp-40h]
  BSTR pbstr; // [rsp+40h] [rbp-30h] BYREF
  BSTR v32; // [rsp+48h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-20h] BYREF
  struct tagRECT Rect; // [rsp+58h] [rbp-18h] BYREF

  Rect = (struct tagRECT)_mm_load_si128((const __m128i *)&_xmm);
  v32 = 0;
  bstrString = 0;
  LODWORD(pbstr) = -1;
  if ( !(unsigned int)GetRegistryValue(L"fEnableChatControl", &pbstr, 2) )
    *((_DWORD *)this + 49) = (_DWORD)pbstr != 0;
  v3 = _AtlModule;
  *((_DWORD *)_AtlModule + 124) = 1;
  inited = CRATicket::InitRDPEventsNovice(
             *((CRATicket **)v3 + 104),
             (void (__high *)(void *, enum _STATUS))&OnAttendeeConnectedProc,
             v2,
             (void (*)(void *, enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0001))OnControlLevelChangeRequest,
             (void (*)(void *, enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0001))OnControlLevelChangeRequest,
             v29,
             v30);
  v6 = inited;
  if ( inited < 0 )
  {
    CEventLogger::LogError(
      v5,
      &Critical_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0xADu,
      L"CNovInterDlg::OnInitDialog",
      inited);
    v7 = (HWND *)((char *)this + 8);
LABEL_30:
    v12 = 650;
    v13 = 531;
    goto LABEL_31;
  }
  *((_DWORD *)this + 22) = 0;
  v8 = 56;
  if ( *(_DWORD *)(*((_QWORD *)_AtlModule + 104) + 136LL) != 7 )
    v8 = 35;
  *((_DWORD *)this + 48) = v8;
  v7 = (HWND *)((char *)this + 8);
  if ( !CNovInterDlg::InitSpecialControls(this, *((HWND *)this + 1))
    || (unsigned int)CNovInterDlg::AddToolbarButtons(this) != 1 )
  {
    CEventLogger::LogError(
      v9,
      &Critical_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0xC4u,
      L"CNovInterDlg::OnInitDialog",
      v6);
    goto LABEL_30;
  }
  *((_QWORD *)_AtlModule + 101) = *v7;
  CNovInterDlg::MoveTopLeft(this);
  SetForegroundWindow(*v7);
  CNovInterDlg::EnableChatControls(this, *((_DWORD *)this + 28));
  MapDialogRect(*v7, &Rect);
  *((_DWORD *)this + 29) = Rect.top;
  if ( (int)OpenSessionLog((CEventLogger *)((char *)_AtlModule + 728), *v7, v10, 1) < 0 )
  {
    CEventLogger::LogEvent(v11, &Session_Log_Problem);
    v12 = 670;
    v13 = 627;
LABEL_31:
    ShowErrorMessage(v13, v12, *v7, 0, (unsigned __int16 *)0xFFFE, 0);
    return CNovInterDlg::KillDialog(this);
  }
  CSessionLogger::WriteToLog((int *)_AtlModule + 182, 0, 0);
  if ( *((_DWORD *)this + 24) )
  {
    CNovInterDlg::SetConnectionStatus(this, 1);
    CNovInterDlg::SetControlStatus(this, CTRL_LEVEL_VIEW, *((void **)this + 13));
    v14 = (struct IRDPSRAPIAttendee *)*((_QWORD *)this + 13);
    if ( v14 )
    {
      pbstr = 0;
      FetchIPAddress(v14, &pbstr);
      v15 = pbstr;
      if ( SysStringLen(pbstr) )
      {
        CSessionLogger::WriteToLog((int *)_AtlModule + 182, 21, (__int64)v15);
        CSqmManager::SetConnectionType((CEventLogger *)((char *)_AtlModule + 496), v15);
      }
      SysFreeString(v15);
    }
  }
  else
  {
    DlgItem = GetDlgItem(*v7, 1037);
    EnableWindow(DlgItem, 0);
    SetTimer(*v7, 1u, 0xEA60u, 0);
    *((_DWORD *)this + 51) = 0;
  }
  *((_DWORD *)this + 43) = 0;
  SendMessageW(*v7, 0x80u, 0, *((_QWORD *)_AtlModule + 75));
  *((_DWORD *)this + 30) = 0;
  v17 = GetDlgItem(*v7, 1036);
  SendMessageW(v17, 0xC5u, 0x200u, 0);
  v18 = GetDlgItem(*v7, 1036);
  SetWindowSubclass(v18, NovEditBoxSubClass, 0x40Cu, 0);
  v19 = GetDlgItem(*v7, 1042);
  SetWindowSubclass(v19, NovPWFieldSubClass, 0x412u, 0);
  v20 = (void *)*((_QWORD *)this + 19);
  if ( v20 )
  {
    DeleteObject(v20);
    *((_QWORD *)this + 19) = 0;
  }
  v21 = GetDlgItem(*v7, 1059);
  *((_DWORD *)this + 41) = (int)GetTDColorAndSetFont(v21, (COLORREF *)this + 40, (HFONT *)this + 19) >= 0;
  v22 = 0;
  if ( !*((_DWORD *)this + 22) )
    LOBYTE(v22) = *(_DWORD *)(*((_QWORD *)_AtlModule + 104) + 136LL) != 3;
  CNovInterDlg::SetPWPanel(this, v22);
  CRATicket::get_NoviceName(*((CRATicket **)_AtlModule + 104), &v32);
  v23 = v32;
  if ( !v32 )
  {
    UserInfoAsBSTR = GetUserInfoAsBSTR(1, &v32);
    v23 = v32;
    if ( UserInfoAsBSTR >= 0 )
      CRATicket::put_NoviceName(*((CRATicket **)_AtlModule + 104), v32);
  }
  SetFocus(*((HWND *)this + 9));
  SysColor = GetSysColor(5);
  v26 = GetDlgItem(*v7, 1042);
  SendMessageW(v26, 0x443u, SysColor, 0);
  CRATicket::get_RATicketString(*((CRATicket **)_AtlModule + 104), &bstrString);
  v27 = bstrString;
  if ( bstrString )
  {
    CSqmManager::SetNetworkStatus((CEventLogger *)((char *)_AtlModule + 496), bstrString);
    CSqmManager::ProcessRAEvent((char *)_AtlModule + 496, 1);
    SysFreeString(v27);
  }
  *((_QWORD *)_AtlModule + 74) = *v7;
  if ( v23 )
    SysFreeString(v23);
  GetClientRect(*v7, &Rect);
  PostMessageW(*v7, 5u, 0, LOWORD(Rect.right) | (unsigned __int64)(LOWORD(Rect.bottom) << 16));
  CNovInterDlg::SetAccProperties(this);
  return 0;
}

```

## disassembly

```asm
0x140021e00  mov     [rsp-28h+arg_8], rbx
0x140021e05  mov     [rsp-28h+arg_10], rsi
0x140021e0a  push    rbp
0x140021e0b  push    rdi
0x140021e0c  push    r12
0x140021e0e  push    r14
0x140021e10  push    r15
0x140021e12  mov     rbp, rsp
0x140021e15  sub     rsp, 70h
0x140021e19  mov     rax, cs:__security_cookie
0x140021e20  xor     rax, rsp
0x140021e23  mov     [rbp+var_8], rax
0x140021e27  mov     rdi, rcx
0x140021e2a  movdqa  xmm0, cs:__xmm@0000000100000001000000c800000000
0x140021e32  movdqu  xmmword ptr [rbp+Rect.left], xmm0
0x140021e37  xor     r15d, r15d
0x140021e3a  mov     [rbp+var_28], r15
0x140021e3e  mov     [rbp+bstrString], r15
0x140021e42  mov     dword ptr [rbp+pbstr], 0FFFFFFFFh
0x140021e49  lea     r8d, [r15+2]
0x140021e4d  lea     rdx, [rbp+pbstr]
0x140021e51  lea     rcx, aFenablechatcon; "fEnableChatControl"
0x140021e58  call    ?GetRegistryValue@@YAJPEAGPEAKW4_RAREGHIVE@@@Z; GetRegistryValue(ushort *,ulong *,_RAREGHIVE)
0x140021e5d  test    eax, eax
0x140021e5f  jnz     short loc_140021E71
0x140021e61  mov     eax, r15d
0x140021e64  cmp     dword ptr [rbp+pbstr], r15d
0x140021e68  setnz   al
0x140021e6b  mov     [rdi+0C4h], eax
0x140021e71  mov     r12d, 1
0x140021e77  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140021e7e  mov     [rcx+1F0h], r12d
0x140021e85  lea     r9, ?OnControlLevelChangeRequest@@YAXPEAXW4__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001@@@Z; void (*)(void *, enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0001)
0x140021e8c  mov     [rsp+70h+var_50], r9; void (*)(void *, enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0001)
0x140021e91  lea     rdx, ?OnAttendeeConnectedProc@@YAXPEAXW4_STATUS@@@Z; void (__high *)(void *, enum _STATUS)
0x140021e98  mov     rcx, [rcx+340h]; this
0x140021e9f  call    ?InitRDPEventsNovice@CRATicket@@QEAAJP6AXPEAXW4_STATUS@@@ZP6AXJ@ZP6AX0W4__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001@@@Z5P6AXH@ZP6AXPEAG7@Z@Z; CRATicket::InitRDPEventsNovice(void (*)(void *,_STATUS),void (*)(long),void (*)(void *,__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001),void (*)(void *,__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001),void (*)(int),void (*)(ushort *,ushort *))
0x140021ea4  mov     ebx, eax
0x140021ea6  test    eax, eax
0x140021ea8  jns     short loc_140021EDC
0x140021eaa  mov     dword ptr [rsp+70h+var_48], eax; unsigned int
0x140021eae  lea     rax, aCnovinterdlgOn_5; "CNovInterDlg::OnInitDialog"
0x140021eb5  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x140021eba  mov     r9d, 0ADh; unsigned int
0x140021ec0  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x140021ec7  lea     rdx, Critical_Error; struct _EVENT_DESCRIPTOR *
0x140021ece  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140021ed3  lea     rsi, [rdi+8]
0x140021ed7  jmp     loc_14002236D
0x140021edc  mov     [rdi+58h], r15d
0x140021ee0  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140021ee7  mov     rcx, [rax+340h]
0x140021eee  mov     eax, 38h ; '8'
0x140021ef3  lea     edx, [rax-15h]
0x140021ef6  cmp     dword ptr [rcx+88h], 7
0x140021efd  cmovnz  eax, edx
0x140021f00  mov     [rdi+0C0h], eax
0x140021f06  lea     rsi, [rdi+8]
0x140021f0a  mov     rdx, [rsi]; hWndParent
0x140021f0d  mov     rcx, rdi; this
0x140021f10  call    ?InitSpecialControls@CNovInterDlg@@AEAAHPEAUHWND__@@@Z; CNovInterDlg::InitSpecialControls(HWND__ *)
0x140021f15  cmp     eax, r12d
0x140021f18  jnz     loc_140022344
0x140021f1e  mov     rcx, rdi; this
0x140021f21  call    ?AddToolbarButtons@CNovInterDlg@@AEAAHXZ; CNovInterDlg::AddToolbarButtons(void)
0x140021f26  cmp     eax, r12d
0x140021f29  jnz     loc_140022344
0x140021f2f  mov     rcx, [rsi]
0x140021f32  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140021f39  mov     [rax+328h], rcx
0x140021f40  mov     rcx, rdi; this
0x140021f43  call    ?MoveTopLeft@CNovInterDlg@@AEAAXXZ; CNovInterDlg::MoveTopLeft(void)
0x140021f48  mov     rcx, [rsi]; hWnd
0x140021f4b  call    cs:__imp_SetForegroundWindow
0x140021f52  nop     dword ptr [rax+rax+00h]
0x140021f57  mov     edx, [rdi+70h]; int
0x140021f5a  mov     rcx, rdi; this
0x140021f5d  call    ?EnableChatControls@CNovInterDlg@@AEAAXH@Z; CNovInterDlg::EnableChatControls(int)
0x140021f62  lea     rdx, [rbp+Rect]; lpRect
0x140021f66  mov     rcx, [rsi]; hDlg
0x140021f69  call    cs:__imp_MapDialogRect
0x140021f70  nop     dword ptr [rax+rax+00h]
0x140021f75  mov     eax, [rbp+Rect.top]
0x140021f78  mov     [rdi+74h], eax
0x140021f7b  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140021f82  add     rcx, 2D8h; this
0x140021f89  mov     r9d, r12d; int
0x140021f8c  mov     rdx, [rsi]; HWND
0x140021f8f  call    ?OpenSessionLog@@YAJPEAVCSessionLogger@@PEAUHWND__@@IH@Z; OpenSessionLog(CSessionLogger *,HWND__ *,uint,int)
0x140021f94  test    eax, eax
0x140021f96  jns     short loc_140021FB1
0x140021f98  lea     rdx, Session_Log_Problem; struct _EVENT_DESCRIPTOR *
0x140021f9f  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)
0x140021fa4  mov     edx, 29Eh
0x140021fa9  lea     ecx, [rdx-2Bh]
0x140021fac  jmp     loc_140022375
0x140021fb1  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140021fb8  add     rcx, 2D8h
0x140021fbf  xor     r8d, r8d
0x140021fc2  xor     edx, edx
0x140021fc4  call    ?WriteToLog@CSessionLogger@@QEAAJW4_SessionEvent@@PEAG@Z; CSessionLogger::WriteToLog(_SessionEvent,ushort *)
0x140021fc9  cmp     [rdi+60h], r15d
0x140021fcd  jz      loc_140022063
0x140021fd3  mov     edx, r12d
0x140021fd6  mov     rcx, rdi
0x140021fd9  call    ?SetConnectionStatus@CNovInterDlg@@QEAAXW4_STATUS@@@Z; CNovInterDlg::SetConnectionStatus(_STATUS)
0x140021fde  mov     r8, [rdi+68h]; void *
0x140021fe2  mov     edx, 2; enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0001
0x140021fe7  mov     rcx, rdi; this
0x140021fea  call    ?SetControlStatus@CNovInterDlg@@QEAAXW4__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001@@PEAX@Z; CNovInterDlg::SetControlStatus(__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001,void *)
0x140021fef  mov     rcx, [rdi+68h]; struct IRDPSRAPIAttendee *
0x140021ff3  test    rcx, rcx
0x140021ff6  jz      loc_1400220AA
0x140021ffc  mov     [rbp+pbstr], r15
0x140022000  lea     rdx, [rbp+pbstr]; unsigned __int16 **
0x140022004  call    ?FetchIPAddress@@YAJPEAUIRDPSRAPIAttendee@@PEAPEAG@Z; FetchIPAddress(IRDPSRAPIAttendee *,ushort * *)
0x140022009  mov     rbx, [rbp+pbstr]
0x14002200d  mov     rcx, rbx; pbstr
0x140022010  call    cs:__imp_SysStringLen
0x140022017  nop     dword ptr [rax+rax+00h]
0x14002201c  test    eax, eax
0x14002201e  jz      short loc_140022052
0x140022020  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140022027  add     rcx, 2D8h
0x14002202e  mov     r8, rbx
0x140022031  mov     edx, 15h
0x140022036  call    ?WriteToLog@CSessionLogger@@QEAAJW4_SessionEvent@@PEAG@Z; CSessionLogger::WriteToLog(_SessionEvent,ushort *)
0x14002203b  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140022042  add     rcx, 1F0h; this
0x140022049  mov     rdx, rbx; unsigned __int16 *
0x14002204c  call    ?SetConnectionType@CSqmManager@@QEAAJPEAG@Z; CSqmManager::SetConnectionType(ushort *)
0x140022051  nop
0x140022052  mov     rcx, rbx; bstrString
0x140022055  call    cs:__imp_SysFreeString
0x14002205c  nop     dword ptr [rax+rax+00h]
0x140022061  jmp     short loc_1400220AA
0x140022063  mov     edx, 40Dh; nIDDlgItem
0x140022068  mov     rcx, [rsi]; hDlg
0x14002206b  call    cs:__imp_GetDlgItem
0x140022072  nop     dword ptr [rax+rax+00h]
0x140022077  xor     edx, edx; bEnable
0x140022079  mov     rcx, rax; hWnd
0x14002207c  call    cs:__imp_EnableWindow
0x140022083  nop     dword ptr [rax+rax+00h]
0x140022088  xor     r9d, r9d; lpTimerFunc
0x14002208b  mov     r8d, 0EA60h; uElapse
0x140022091  mov     rdx, r12; nIDEvent
0x140022094  mov     rcx, [rsi]; hWnd
0x140022097  call    cs:__imp_SetTimer
0x14002209e  nop     dword ptr [rax+rax+00h]
0x1400220a3  mov     [rdi+0CCh], r15d
0x1400220aa  mov     [rdi+0ACh], r15d
0x1400220b1  mov     r9, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400220b8  mov     r9, [r9+258h]; lParam
0x1400220bf  xor     r8d, r8d; wParam
0x1400220c2  mov     edx, 80h; Msg
0x1400220c7  mov     rcx, [rsi]; hWnd
0x1400220ca  call    cs:__imp_SendMessageW
0x1400220d1  nop     dword ptr [rax+rax+00h]
0x1400220d6  mov     [rdi+78h], r15d
0x1400220da  mov     ebx, 40Ch
0x1400220df  mov     edx, ebx; nIDDlgItem
0x1400220e1  mov     rcx, [rsi]; hDlg
0x1400220e4  call    cs:__imp_GetDlgItem
0x1400220eb  nop     dword ptr [rax+rax+00h]
0x1400220f0  xor     r9d, r9d; lParam
0x1400220f3  mov     edx, 0C5h; Msg
0x1400220f8  mov     r8d, 200h; wParam
0x1400220fe  mov     rcx, rax; hWnd
0x140022101  call    cs:__imp_SendMessageW
0x140022108  nop     dword ptr [rax+rax+00h]
0x14002210d  mov     edx, ebx; nIDDlgItem
0x14002210f  mov     rcx, [rsi]; hDlg
0x140022112  call    cs:__imp_GetDlgItem
0x140022119  nop     dword ptr [rax+rax+00h]
0x14002211e  xor     r9d, r9d; dwRefData
0x140022121  mov     r8d, ebx; uIdSubclass
0x140022124  lea     rdx, ?NovEditBoxSubClass@@YA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x14002212b  mov     rcx, rax; hWnd
0x14002212e  call    cs:__imp_SetWindowSubclass
0x140022135  nop     dword ptr [rax+rax+00h]
0x14002213a  mov     ebx, 412h
0x14002213f  mov     edx, ebx; nIDDlgItem
0x140022141  mov     rcx, [rsi]; hDlg
0x140022144  call    cs:__imp_GetDlgItem
0x14002214b  nop     dword ptr [rax+rax+00h]
0x140022150  xor     r9d, r9d; dwRefData
0x140022153  mov     r8d, ebx; uIdSubclass
0x140022156  lea     rdx, ?NovPWFieldSubClass@@YA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x14002215d  mov     rcx, rax; hWnd
0x140022160  call    cs:__imp_SetWindowSubclass
0x140022167  nop     dword ptr [rax+rax+00h]
0x14002216c  lea     rbx, [rdi+98h]
0x140022173  mov     rcx, [rbx]; ho
0x140022176  test    rcx, rcx
0x140022179  jz      short loc_14002218A
0x14002217b  call    cs:__imp_DeleteObject
0x140022182  nop     dword ptr [rax+rax+00h]
0x140022187  mov     [rbx], r15
0x14002218a  mov     edx, 423h; nIDDlgItem
0x14002218f  mov     rcx, [rsi]; hDlg
0x140022192  call    cs:__imp_GetDlgItem
0x140022199  nop     dword ptr [rax+rax+00h]
0x14002219e  lea     rdx, [rdi+0A0h]; pColor
0x1400221a5  mov     r8, rbx; HFONT *
0x1400221a8  mov     rcx, rax; hWnd
0x1400221ab  call    ?GetTDColorAndSetFont@@YAJPEAUHWND__@@PEAKPEAPEAUHFONT__@@@Z; GetTDColorAndSetFont(HWND__ *,ulong *,HFONT__ * *)
0x1400221b0  not     eax
0x1400221b2  shr     eax, 1Fh
0x1400221b5  mov     [rdi+0A4h], eax
0x1400221bb  mov     edx, r15d
0x1400221be  cmp     [rdi+58h], r15d
0x1400221c2  jnz     short loc_1400221DC
0x1400221c4  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400221cb  mov     rcx, [rax+340h]
0x1400221d2  cmp     dword ptr [rcx+88h], 3
0x1400221d9  setnz   dl; int
0x1400221dc  mov     rcx, rdi; this
0x1400221df  call    ?SetPWPanel@CNovInterDlg@@AEAAXH@Z; CNovInterDlg::SetPWPanel(int)
0x1400221e4  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x1400221e8  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400221ef  mov     rcx, [rcx+340h]; this
0x1400221f6  call    ?get_NoviceName@CRATicket@@QEAAJPEAPEAG@Z; CRATicket::get_NoviceName(ushort * *)
0x1400221fb  mov     r14, [rbp+var_28]
0x1400221ff  test    r14, r14
0x140022202  jnz     short loc_14002222E
0x140022204  lea     rdx, [rbp+var_28]
0x140022208  mov     ecx, r12d
0x14002220b  call    ?GetUserInfoAsBSTR@@YAJW4_USERINFOTYPE@@PEAPEAG@Z; GetUserInfoAsBSTR(_USERINFOTYPE,ushort * *)
0x140022210  mov     r14, [rbp+var_28]
0x140022214  test    eax, eax
0x140022216  js      short loc_14002222E
0x140022218  mov     rdx, r14; unsigned __int16 *
0x14002221b  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140022222  mov     rcx, [rcx+340h]; this
0x140022229  call    ?put_NoviceName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_NoviceName(ushort *)
0x14002222e  mov     rcx, [rdi+48h]; hWnd
0x140022232  call    cs:__imp_SetFocus
0x140022239  nop     dword ptr [rax+rax+00h]
0x14002223e  mov     ecx, 5; nIndex
0x140022243  call    cs:__imp_GetSysColor
0x14002224a  nop     dword ptr [rax+rax+00h]
0x14002224f  mov     ebx, eax
0x140022251  mov     edx, 412h; nIDDlgItem
0x140022256  mov     rcx, [rsi]; hDlg
0x140022259  call    cs:__imp_GetDlgItem
0x140022260  nop     dword ptr [rax+rax+00h]
0x140022265  xor     r9d, r9d; lParam
0x140022268  mov     r8d, ebx; wParam
0x14002226b  mov     edx, 443h; Msg
0x140022270  mov     rcx, rax; hWnd
0x140022273  call    cs:__imp_SendMessageW
0x14002227a  nop     dword ptr [rax+rax+00h]
0x14002227f  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x140022283  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14002228a  mov     rcx, [rcx+340h]; this
0x140022291  call    ?get_RATicketString@CRATicket@@QEAAJPEAPEAG@Z; CRATicket::get_RATicketString(ushort * *)
0x140022296  mov     rbx, [rbp+bstrString]
0x14002229a  test    rbx, rbx
0x14002229d  jz      short loc_1400222DA
0x14002229f  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400222a6  add     rcx, 1F0h; this
0x1400222ad  mov     rdx, rbx; unsigned __int16 *
0x1400222b0  call    ?SetNetworkStatus@CSqmManager@@QEAAJPEAG@Z; CSqmManager::SetNetworkStatus(ushort *)
0x1400222b5  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400222bc  add     rcx, 1F0h
0x1400222c3  mov     edx, r12d
0x1400222c6  call    ?ProcessRAEvent@CSqmManager@@QEAAXW4_RASQM_EVENT@@@Z; CSqmManager::ProcessRAEvent(_RASQM_EVENT)
0x1400222cb  mov     rcx, rbx; bstrString
0x1400222ce  call    cs:__imp_SysFreeString
0x1400222d5  nop     dword ptr [rax+rax+00h]
0x1400222da  mov     rdx, [rsi]
0x1400222dd  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400222e4  mov     [rax+250h], rdx
0x1400222eb  test    r14, r14
0x1400222ee  jz      short loc_1400222FF
0x1400222f0  mov     rcx, r14; bstrString
0x1400222f3  call    cs:__imp_SysFreeString
0x1400222fa  nop     dword ptr [rax+rax+00h]
0x1400222ff  lea     rdx, [rbp+Rect]; lpRect
0x140022303  mov     rcx, [rsi]; hWnd
0x140022306  call    cs:__imp_GetClientRect
0x14002230d  nop     dword ptr [rax+rax+00h]
0x140022312  movzx   r9d, word ptr [rbp+Rect.bottom]
0x140022317  shl     r9d, 10h
0x14002231b  movzx   eax, word ptr [rbp+Rect.right]
0x14002231f  or      r9, rax; lParam
0x140022322  xor     r8d, r8d; wParam
0x140022325  lea     edx, [r8+5]; Msg
0x140022329  mov     rcx, [rsi]; hWnd
0x14002232c  call    cs:__imp_PostMessageW
0x140022333  nop     dword ptr [rax+rax+00h]
0x140022338  mov     rcx, rdi; this
0x14002233b  call    ?SetAccProperties@CNovInterDlg@@AEAAXXZ; CNovInterDlg::SetAccProperties(void)
0x140022340  xor     eax, eax
0x140022342  jmp     short loc_140022398
0x140022344  mov     dword ptr [rsp+70h+var_48], ebx; unsigned int
0x140022348  lea     rax, aCnovinterdlgOn_5; "CNovInterDlg::OnInitDialog"
0x14002234f  mov     [rsp+70h+var_50], rax; unsigned __int16 *
0x140022354  mov     r9d, 0C4h; unsigned int
  ... truncated ...
```
