# CExpInterDlg::OnInitDialog(uint,unsigned __int64,__int64,int &)

- ea: `0x14001c458`
- end: `0x14001c93e`
- name: `?OnInitDialog@CExpInterDlg@@QEAA_JI_K_JAEAH@Z`
- size: `1254`
- prototype: `__int64 __usercall@<rax>(CExpInterDlg *__hidden this@<rcx>, unsigned int@<edx>, unsigned __int64@<r8>, __int64@<r9>, int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14001db80`

## callees

- `0x1400044f8`
- `0x14000a0e4`
- `0x140019e04`
- `0x14001a978`
- `0x14001ac1c`
- `0x14001b0bc`
- `0x14001b1fc`
- `0x14001b7b0`
- `0x14001b90c`
- `0x14001ba74`
- `0x14001c458`
- `0x14001e344`
- `0x14001e524`
- `0x140029978`
- `0x14002ad4c`
- `0x14002c0a4`
- `0x14002cb94`
- `0x140034ce4`
- `0x140034eac`
- `0x140035a10`
- `0x140035b20`
- `0x14003806c`
- `0x14003bf1c`
- `0x14003f9fc`
- `0x14003fe58`
- `0x14004d010`

## import_xrefs

- `USER32!SendMessageW` at `0x14001c66a`
- `USER32!SendMessageW` at `0x14001c761`
- `USER32!SendMessageW` at `0x14001c66a`
- `USER32!SendMessageW` at `0x14001c761`
- `USER32!ShowWindow` at `0x14001c73b`
- `USER32!ShowWindow` at `0x14001c73b`
- `USER32!GetDlgItem` at `0x14001c64d`
- `USER32!GetDlgItem` at `0x14001c67f`
- `USER32!GetDlgItem` at `0x14001c6e0`
- `USER32!GetDlgItem` at `0x14001c77b`
- `USER32!GetDlgItem` at `0x14001c7aa`
- `USER32!GetDlgItem` at `0x14001c7da`
- `USER32!GetDlgItem` at `0x14001c64d`
- `USER32!GetDlgItem` at `0x14001c67f`
- `USER32!GetDlgItem` at `0x14001c6e0`
- `USER32!GetDlgItem` at `0x14001c77b`
- `USER32!GetDlgItem` at `0x14001c7aa`
- `USER32!GetDlgItem` at `0x14001c7da`
- `USER32!PostMessageW` at `0x14001c812`
- `USER32!PostMessageW` at `0x14001c812`
- `USER32!SetForegroundWindow` at `0x14001c726`
- `USER32!SetForegroundWindow` at `0x14001c726`
- `USER32!UpdateWindow` at `0x14001c6ff`
- `USER32!UpdateWindow` at `0x14001c6ff`
- `USER32!EnableWindow` at `0x14001c690`
- `USER32!EnableWindow` at `0x14001c690`
- `USER32!SetFocus` at `0x14001c6ef`
- `USER32!SetFocus` at `0x14001c6ef`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14001c8f2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14001c8f2`
- `OLEAUT32!__imp_SysAllocString` at `0x14001c885`
- `OLEAUT32!__imp_SysAllocString` at `0x14001c885`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c610`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c826`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c8c7`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c610`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c826`
- `OLEAUT32!__imp_SysFreeString` at `0x14001c8c7`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14001c797`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14001c7c7`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14001c7f7`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14001c797`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14001c7c7`
- `COMCTL32!__imp_SetWindowSubclass` at `0x14001c7f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CExpInterDlg::OnInitDialog(CExpInterDlg *this, int a2, __int64 a3, __int64 a4, int *a5)
{
  OLECHAR *v6; // rdi
  unsigned int *v7; // rsi
  __int64 v8; // rdx
  char *v9; // rcx
  void (*v10)(int, int); // rdx
  void (*v11)(void *); // r8
  void (*v12)(void); // r9
  signed int inited; // esi
  unsigned int v14; // r8d
  HWND v15; // rdx
  CEventLogger *v16; // rcx
  CEventLogger *v17; // rcx
  HWND DlgItem; // rax
  HWND v20; // rax
  unsigned __int16 v21; // dx
  HWND v22; // r9
  HWND v23; // rax
  HWND v24; // rax
  HWND v25; // rax
  HWND v26; // rax
  int RegistryValue; // eax
  unsigned __int16 *v28; // rdi
  int v29; // eax
  unsigned __int16 *v30; // [rsp+28h] [rbp-41h]
  int *v31; // [rsp+28h] [rbp-41h]
  void (*v32)(int); // [rsp+30h] [rbp-39h]
  void (*v33)(void); // [rsp+38h] [rbp-31h]
  void (*v34)(int, int); // [rsp+40h] [rbp-29h]
  void (*v35)(enum __MIDL___MIDL_itf_rdpencomapi_0000_0000_0001); // [rsp+48h] [rbp-21h]
  void (*v36)(void); // [rsp+50h] [rbp-19h]
  void (*v37)(void); // [rsp+58h] [rbp-11h]
  void (*v38)(void); // [rsp+60h] [rbp-9h]
  void (*v39)(int); // [rsp+68h] [rbp-1h]
  void (*v40)(void); // [rsp+70h] [rbp+7h]
  void (*v41)(int); // [rsp+78h] [rbp+Fh]
  void (*v42)(unsigned __int16 *, unsigned __int16 *); // [rsp+80h] [rbp+17h]
  struct tagRECT v43; // [rsp+90h] [rbp+27h] BYREF
  int v44; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v45; // [rsp+D8h] [rbp+6Fh] BYREF
  BSTR bstrString; // [rsp+E0h] [rbp+77h] BYREF

  v45 = a3;
  v44 = a2;
  v43 = 0;
  v6 = 0;
  bstrString = 0;
  v7 = (unsigned int *)*((_QWORD *)_AtlModule + 104);
  v44 = -1;
  v8 = v7[34];
  v9 = (char *)_AtlModule + 496;
  *((_DWORD *)_AtlModule + 124) = 2;
  CSqmManager::SetEscalationMethod(v9, v8);
  if ( !(unsigned int)TakeLock(0) )
  {
    ShowErrorMessage(0x225u, 0x295u, 0, 0, (unsigned __int16 *)0xFFFE, 0);
LABEL_11:
    if ( v6 )
      SysFreeString(v6);
    return CExpInterDlg::KillDialog(this);
  }
  if ( !(unsigned int)GetRegistryValue(L"fEnableChatControl", &v44, 2) )
    *((_DWORD *)this + 41) = v44 != 0;
  CRATicket::get_ExpertName((CRATicket *)v7, &bstrString);
  v6 = bstrString;
  if ( !bstrString )
  {
    GetUserInfoAsBSTR(1, &bstrString);
    v6 = bstrString;
    CRATicket::put_ExpertName((CRATicket *)v7, bstrString);
  }
  CExpInterDlg::MoveTopLeft(this);
  CExpInterDlg::CreateToolbarCtl((HWND *)this, *((HWND *)this + 1));
  CExpInterDlg::AddToolbarButtons(this);
  CExpInterDlg::SetSplitterArea(this, &v43);
  CExpInterDlg::CreateViewerControl((HWND *)this);
  inited = CRATicket::InitRDPEventsExpert(
             (CRATicket *)v7,
             v10,
             v11,
             v12,
             (void (*)(void))v30,
             v32,
             v33,
             v34,
             v35,
             v36,
             v37,
             v38,
             v39,
             v40,
             v41,
             v42);
  v15 = (HWND)*((_QWORD *)this + 1);
  if ( inited < 0 )
  {
    ShowErrorMessage(0x213u, 0x28Au, v15, 0, (unsigned __int16 *)0xFFFE, 0);
    CEventLogger::LogError(
      v16,
      &Critical_Error,
      L"base\\diagnosis\\ra\\ui\\expinterdialog.cpp",
      0xCDu,
      L"CExpInterDlg::OnInitDialog",
      inited);
    goto LABEL_11;
  }
  if ( (int)OpenSessionLog((CEventLogger *)((char *)_AtlModule + 728), v15, v14, 0) < 0 )
  {
    CEventLogger::LogEvent(v17, &Session_Log_Problem);
    ShowErrorMessage(0x273u, 0x29Eu, *((HWND *)this + 1), 0, (unsigned __int16 *)0xFFFE, 0);
    goto LABEL_11;
  }
  DlgItem = GetDlgItem(*((HWND *)this + 1), 1036);
  SendMessageW(DlgItem, 0xC5u, 0x200u, 0);
  v20 = GetDlgItem(*((HWND *)this + 1), 1037);
  EnableWindow(v20, 0);
  *(_QWORD *)((char *)this + 124) = 0;
  CExpInterDlg::OnButtonFitToScreen(this, v21, 0, v22, v31);
  *((_DWORD *)this + 33) = 0;
  *((_QWORD *)_AtlModule + 101) = *((_QWORD *)this + 1);
  CExpInterDlg::EnableChatControls(this, 0);
  v23 = GetDlgItem(*((HWND *)this + 1), 1035);
  SetFocus(v23);
  UpdateWindow(*((HWND *)this + 1));
  ATL::CDialogImplBaseT<ATL::CWindow>::ExecuteDlgInit(this, 112);
  *a5 = 0;
  SetForegroundWindow(*((HWND *)this + 1));
  ShowWindow(*((HWND *)this + 1), 3);
  SendMessageW(*((HWND *)this + 1), 0x80u, 0, *((_QWORD *)_AtlModule + 75));
  CExpInterDlg::SetAccProperties(this);
  v24 = GetDlgItem(*((HWND *)this + 1), 1035);
  SetWindowSubclass(v24, StopESCPressSubclass, 0x40Bu, 0);
  v25 = GetDlgItem(*((HWND *)this + 1), 1037);
  SetWindowSubclass(v25, StopESCPressSubclass, 0x40Du, 0);
  v26 = GetDlgItem(*((HWND *)this + 1), 1036);
  SetWindowSubclass(v26, ExpEditBoxSubClass, 0x40Cu, 0);
  PostMessageW(*((HWND *)this + 1), 0x8018u, 0, 0);
  if ( v6 )
    SysFreeString(v6);
  bstrString = 0;
  RegistryValue = GetRegistryValue(L"cookie", (BYTE **)&bstrString, 1);
  v28 = bstrString;
  if ( !RegistryValue )
  {
    v45 = 0;
    (***((void (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 14))(
      *((_QWORD *)this + 14),
      &GUID_aa1e42b5_496d_4ca4_a690_348dcb2ec4ad,
      &v45);
    bstrString = SysAllocString(L"cookie=");
    if ( !bstrString )
      ATL::AtlThrowImpl(-2147024882);
    v29 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, v28);
    if ( v29 < 0 )
      ATL::AtlThrowImpl(v29);
    (*(void (__fastcall **)(__int64, BSTR))(*(_QWORD *)v45 + 24LL))(v45, bstrString);
    SysFreeString(bstrString);
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  if ( v28 )
    operator delete[](v28);
  return 0;
}

```

## disassembly

```asm
0x14001c458  mov     rax, rsp
0x14001c45b  mov     [rax+8], rbx
0x14001c45f  mov     [rax+20h], r9
0x14001c463  mov     [rax+18h], r8
0x14001c467  mov     [rax+10h], edx
0x14001c46a  push    rbp
0x14001c46b  push    rsi
0x14001c46c  push    rdi
0x14001c46d  lea     rbp, [rax-57h]
0x14001c471  sub     rsp, 0A0h
0x14001c478  mov     rbx, rcx
0x14001c47b  xorps   xmm0, xmm0
0x14001c47e  movups  xmmword ptr [rbp+4Fh+var_28.left], xmm0
0x14001c482  mov     [rbp+4Fh+var_30], 0
0x14001c48a  xor     edi, edi
0x14001c48c  mov     [rbp+4Fh+bstrString], rdi
0x14001c490  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001c497  mov     rsi, [rax+340h]
0x14001c49e  mov     [rbp+4Fh+arg_8], 0FFFFFFFFh
0x14001c4a5  mov     edx, [rsi+88h]
0x14001c4ab  lea     rcx, [rax+1F0h]
0x14001c4b2  mov     dword ptr [rcx], 2
0x14001c4b8  call    ?SetEscalationMethod@CSqmManager@@QEAAXW4_RATYPE@@@Z; CSqmManager::SetEscalationMethod(_RATYPE)
0x14001c4bd  xor     ecx, ecx; int
0x14001c4bf  call    ?TakeLock@@YAHH@Z; TakeLock(int)
0x14001c4c4  test    eax, eax
0x14001c4c6  jnz     short loc_14001C4DC
0x14001c4c8  mov     [rsp+28h], edi
0x14001c4cc  xor     r8d, r8d
0x14001c4cf  mov     edx, 295h
0x14001c4d4  lea     ecx, [rdx-70h]
0x14001c4d7  jmp     loc_14001C5F7
0x14001c4dc  mov     r8d, 2
0x14001c4e2  lea     rdx, [rbp+4Fh+arg_8]
0x14001c4e6  lea     rcx, aFenablechatcon; "fEnableChatControl"
0x14001c4ed  call    ?GetRegistryValue@@YAJPEAGPEAKW4_RAREGHIVE@@@Z; GetRegistryValue(ushort *,ulong *,_RAREGHIVE)
0x14001c4f2  test    eax, eax
0x14001c4f4  jnz     short loc_14001C502
0x14001c4f6  cmp     [rbp+4Fh+arg_8], eax
0x14001c4f9  setnz   al
0x14001c4fc  mov     [rbx+0A4h], eax
0x14001c502  lea     rdx, [rbp+4Fh+bstrString]; unsigned __int16 **
0x14001c506  mov     rcx, rsi; this
0x14001c509  call    ?get_ExpertName@CRATicket@@QEAAJPEAPEAG@Z; CRATicket::get_ExpertName(ushort * *)
0x14001c50e  mov     rdi, [rbp+4Fh+bstrString]
0x14001c512  test    rdi, rdi
0x14001c515  jnz     short loc_14001C532
0x14001c517  lea     rdx, [rbp+4Fh+bstrString]
0x14001c51b  lea     ecx, [rdi+1]
0x14001c51e  call    ?GetUserInfoAsBSTR@@YAJW4_USERINFOTYPE@@PEAPEAG@Z; GetUserInfoAsBSTR(_USERINFOTYPE,ushort * *)
0x14001c523  mov     rdi, [rbp+4Fh+bstrString]
0x14001c527  mov     rdx, rdi; unsigned __int16 *
0x14001c52a  mov     rcx, rsi; this
0x14001c52d  call    ?put_ExpertName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_ExpertName(ushort *)
0x14001c532  mov     rcx, rbx; this
0x14001c535  call    ?MoveTopLeft@CExpInterDlg@@AEAAXXZ; CExpInterDlg::MoveTopLeft(void)
0x14001c53a  mov     rdx, [rbx+8]; hWndParent
0x14001c53e  mov     rcx, rbx; this
0x14001c541  call    ?CreateToolbarCtl@CExpInterDlg@@AEAAHPEAUHWND__@@@Z; CExpInterDlg::CreateToolbarCtl(HWND__ *)
0x14001c546  mov     rcx, rbx; this
0x14001c549  call    ?AddToolbarButtons@CExpInterDlg@@AEAAHXZ; CExpInterDlg::AddToolbarButtons(void)
0x14001c54e  lea     rdx, [rbp+4Fh+var_28]; struct tagRECT *
0x14001c552  mov     rcx, rbx; this
0x14001c555  call    ?SetSplitterArea@CExpInterDlg@@AEAAXPEAUtagRECT@@@Z; CExpInterDlg::SetSplitterArea(tagRECT *)
0x14001c55a  mov     rcx, rbx; this
0x14001c55d  call    ?CreateViewerControl@CExpInterDlg@@QEAAJXZ; CExpInterDlg::CreateViewerControl(void)
0x14001c562  mov     rcx, rsi; this
0x14001c565  call    ?InitRDPEventsExpert@CRATicket@@QEAAJP6AXJJ@ZP6AXPEAX@ZP6AXXZ3P6AXJ@Z30P6AXW4__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001@@@Z33343P6AXH@ZP6AXPEAG8@Z@Z; CRATicket::InitRDPEventsExpert(void (*)(long,long),void (*)(void *),void (*)(void),void (*)(void),void (*)(long),void (*)(void),void (*)(long,long),void (*)(__MIDL___MIDL_itf_rdpencomapi_0000_0000_0001),void (*)(void),void (*)(void),void (*)(void),void (*)(long),void (*)(void),void (*)(int),void (*)(ushort *,ushort *))
0x14001c56a  mov     esi, eax
0x14001c56c  mov     rdx, [rbx+8]; HWND
0x14001c570  xor     r9d, r9d; int
0x14001c573  test    eax, eax
0x14001c575  jns     short loc_14001C5C0
0x14001c577  mov     [rsp+28h], r9d; int
0x14001c57c  mov     [rsp+0B0h+var_90], 0FFFEh; unsigned __int16 *
0x14001c585  mov     r8, rdx; HWND
0x14001c588  mov     edx, 28Ah; int
0x14001c58d  lea     ecx, [rdx-77h]; int
0x14001c590  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x14001c595  mov     [rsp+28h], esi; unsigned int
0x14001c599  lea     rax, aCexpinterdlgOn; "CExpInterDlg::OnInitDialog"
0x14001c5a0  mov     [rsp+0B0h+var_90], rax; unsigned __int16 *
0x14001c5a5  mov     r9d, 0CDh; unsigned int
0x14001c5ab  lea     r8, aBaseDiagnosisR_27; "base\\diagnosis\\ra\\ui\\expinterdialog"...
0x14001c5b2  lea     rdx, Critical_Error; struct _EVENT_DESCRIPTOR *
0x14001c5b9  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001c5be  jmp     short loc_14001C608
0x14001c5c0  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001c5c7  add     rcx, 2D8h; this
0x14001c5ce  call    ?OpenSessionLog@@YAJPEAVCSessionLogger@@PEAUHWND__@@IH@Z; OpenSessionLog(CSessionLogger *,HWND__ *,uint,int)
0x14001c5d3  test    eax, eax
0x14001c5d5  jns     short loc_14001C644
0x14001c5d7  lea     rdx, Session_Log_Problem; struct _EVENT_DESCRIPTOR *
0x14001c5de  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)
0x14001c5e3  mov     dword ptr [rsp+28h], 0; int
0x14001c5eb  mov     r8, [rbx+8]; HWND
0x14001c5ef  mov     edx, 29Eh; int
0x14001c5f4  lea     ecx, [rdx-2Bh]; int
0x14001c5f7  mov     [rsp+0B0h+var_90], 0FFFEh; unsigned __int16 *
0x14001c600  xor     r9d, r9d; int
0x14001c603  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x14001c608  test    rdi, rdi
0x14001c60b  jz      short loc_14001C61C
0x14001c60d  mov     rcx, rdi; bstrString
0x14001c610  call    cs:__imp_SysFreeString
0x14001c617  nop     dword ptr [rax+rax+00h]
0x14001c61c  mov     rcx, rbx; this
0x14001c61f  call    ?KillDialog@CExpInterDlg@@AEAAIXZ; CExpInterDlg::KillDialog(void)
0x14001c624  mov     ebx, eax
0x14001c626  mov     rcx, [rbp+4Fh+var_30]
0x14001c62a  test    rcx, rcx
0x14001c62d  jz      short loc_14001C63C
0x14001c62f  mov     rdx, [rcx]
0x14001c632  mov     rax, [rdx+10h]
0x14001c636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c63b  nop
0x14001c63c  mov     rax, rbx
0x14001c63f  jmp     loc_14001C917
0x14001c644  mov     edx, 40Ch; nIDDlgItem
0x14001c649  mov     rcx, [rbx+8]; hDlg
0x14001c64d  call    cs:__imp_GetDlgItem
0x14001c654  nop     dword ptr [rax+rax+00h]
0x14001c659  mov     rcx, rax; hWnd
0x14001c65c  xor     r9d, r9d; lParam
0x14001c65f  mov     edx, 0C5h; Msg
0x14001c664  mov     r8d, 200h; wParam
0x14001c66a  call    cs:__imp_SendMessageW
0x14001c671  nop     dword ptr [rax+rax+00h]
0x14001c676  mov     edx, 40Dh; nIDDlgItem
0x14001c67b  mov     rcx, [rbx+8]; hDlg
0x14001c67f  call    cs:__imp_GetDlgItem
0x14001c686  nop     dword ptr [rax+rax+00h]
0x14001c68b  xor     edx, edx; bEnable
0x14001c68d  mov     rcx, rax; hWnd
0x14001c690  call    cs:__imp_EnableWindow
0x14001c697  nop     dword ptr [rax+rax+00h]
0x14001c69c  mov     qword ptr [rbx+7Ch], 0
0x14001c6a4  xor     r8d, r8d; unsigned __int16
0x14001c6a7  mov     rcx, rbx; this
0x14001c6aa  call    ?OnButtonFitToScreen@CExpInterDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z; CExpInterDlg::OnButtonFitToScreen(ushort,ushort,HWND__ *,int &)
0x14001c6af  mov     dword ptr [rbx+84h], 0
0x14001c6b9  mov     rcx, [rbx+8]
0x14001c6bd  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001c6c4  mov     [rax+328h], rcx
0x14001c6cb  xor     edx, edx; int
0x14001c6cd  mov     rcx, rbx; this
0x14001c6d0  call    ?EnableChatControls@CExpInterDlg@@AEAAXH@Z; CExpInterDlg::EnableChatControls(int)
0x14001c6d5  mov     esi, 40Bh
0x14001c6da  mov     edx, esi; nIDDlgItem
0x14001c6dc  mov     rcx, [rbx+8]; hDlg
0x14001c6e0  call    cs:__imp_GetDlgItem
0x14001c6e7  nop     dword ptr [rax+rax+00h]
0x14001c6ec  mov     rcx, rax; hWnd
0x14001c6ef  call    cs:__imp_SetFocus
0x14001c6f6  nop     dword ptr [rax+rax+00h]
0x14001c6fb  mov     rcx, [rbx+8]; hWnd
0x14001c6ff  call    cs:__imp_UpdateWindow
0x14001c706  nop     dword ptr [rax+rax+00h]
0x14001c70b  mov     edx, 70h ; 'p'
0x14001c710  mov     rcx, rbx
0x14001c713  call    ?ExecuteDlgInit@?$CDialogImplBaseT@VCWindow@ATL@@@ATL@@QEAAHH@Z; ATL::CDialogImplBaseT<ATL::CWindow>::ExecuteDlgInit(int)
0x14001c718  mov     rax, [rbp+4Fh+arg_20]
0x14001c71c  mov     dword ptr [rax], 0
0x14001c722  mov     rcx, [rbx+8]; hWnd
0x14001c726  call    cs:__imp_SetForegroundWindow
0x14001c72d  nop     dword ptr [rax+rax+00h]
0x14001c732  mov     edx, 3; nCmdShow
0x14001c737  mov     rcx, [rbx+8]; hWnd
0x14001c73b  call    cs:__imp_ShowWindow
0x14001c742  nop     dword ptr [rax+rax+00h]
0x14001c747  mov     r9, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001c74e  mov     r9, [r9+258h]; lParam
0x14001c755  xor     r8d, r8d; wParam
0x14001c758  mov     edx, 80h; Msg
0x14001c75d  mov     rcx, [rbx+8]; hWnd
0x14001c761  call    cs:__imp_SendMessageW
0x14001c768  nop     dword ptr [rax+rax+00h]
0x14001c76d  mov     rcx, rbx; this
0x14001c770  call    ?SetAccProperties@CExpInterDlg@@AEAAXXZ; CExpInterDlg::SetAccProperties(void)
0x14001c775  mov     edx, esi; nIDDlgItem
0x14001c777  mov     rcx, [rbx+8]; hDlg
0x14001c77b  call    cs:__imp_GetDlgItem
0x14001c782  nop     dword ptr [rax+rax+00h]
0x14001c787  xor     r9d, r9d; dwRefData
0x14001c78a  mov     r8d, esi; uIdSubclass
0x14001c78d  lea     rdx, ?StopESCPressSubclass@@YA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x14001c794  mov     rcx, rax; hWnd
0x14001c797  call    cs:__imp_SetWindowSubclass
0x14001c79e  nop     dword ptr [rax+rax+00h]
0x14001c7a3  lea     edx, [rsi+2]; nIDDlgItem
0x14001c7a6  mov     rcx, [rbx+8]; hDlg
0x14001c7aa  call    cs:__imp_GetDlgItem
0x14001c7b1  nop     dword ptr [rax+rax+00h]
0x14001c7b6  xor     r9d, r9d; dwRefData
0x14001c7b9  lea     r8d, [rsi+2]; uIdSubclass
0x14001c7bd  lea     rdx, ?StopESCPressSubclass@@YA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x14001c7c4  mov     rcx, rax; hWnd
0x14001c7c7  call    cs:__imp_SetWindowSubclass
0x14001c7ce  nop     dword ptr [rax+rax+00h]
0x14001c7d3  lea     edx, [rsi+1]; nIDDlgItem
0x14001c7d6  mov     rcx, [rbx+8]; hDlg
0x14001c7da  call    cs:__imp_GetDlgItem
0x14001c7e1  nop     dword ptr [rax+rax+00h]
0x14001c7e6  xor     r9d, r9d; dwRefData
0x14001c7e9  lea     r8d, [rsi+1]; uIdSubclass
0x14001c7ed  lea     rdx, ?ExpEditBoxSubClass@@YA_JPEAUHWND__@@I_K_J11@Z; pfnSubclass
0x14001c7f4  mov     rcx, rax; hWnd
0x14001c7f7  call    cs:__imp_SetWindowSubclass
0x14001c7fe  nop     dword ptr [rax+rax+00h]
0x14001c803  xor     r9d, r9d; lParam
0x14001c806  xor     r8d, r8d; wParam
0x14001c809  mov     edx, 8018h; Msg
0x14001c80e  mov     rcx, [rbx+8]; hWnd
0x14001c812  call    cs:__imp_PostMessageW
0x14001c819  nop     dword ptr [rax+rax+00h]
0x14001c81e  test    rdi, rdi
0x14001c821  jz      short loc_14001C832
0x14001c823  mov     rcx, rdi; bstrString
0x14001c826  call    cs:__imp_SysFreeString
0x14001c82d  nop     dword ptr [rax+rax+00h]
0x14001c832  mov     [rbp+4Fh+bstrString], 0
0x14001c83a  mov     r8d, 1
0x14001c840  lea     rdx, [rbp+4Fh+bstrString]
0x14001c844  lea     rcx, aCookie_0; "cookie"
0x14001c84b  call    ?GetRegistryValue@@YAJPEAGPEAPEAGW4_RAREGHIVE@@@Z; GetRegistryValue(ushort *,ushort * *,_RAREGHIVE)
0x14001c850  mov     rdi, [rbp+4Fh+bstrString]
0x14001c854  test    eax, eax
0x14001c856  jnz     loc_14001C8EA
0x14001c85c  mov     [rbp+4Fh+arg_10], 0
0x14001c864  mov     rcx, [rbx+70h]
0x14001c868  mov     rax, [rcx]
0x14001c86b  lea     r8, [rbp+4Fh+arg_10]
0x14001c86f  lea     rdx, _GUID_aa1e42b5_496d_4ca4_a690_348dcb2ec4ad
0x14001c876  mov     rax, [rax]
0x14001c879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c87e  lea     rcx, aCookie; "cookie="
0x14001c885  call    cs:__imp_SysAllocString
0x14001c88c  nop     dword ptr [rax+rax+00h]
0x14001c891  mov     [rbp+4Fh+bstrString], rax
0x14001c895  test    rax, rax
0x14001c898  jz      loc_14001C933
0x14001c89e  mov     rdx, rdi; unsigned __int16 *
0x14001c8a1  lea     rcx, [rbp+4Fh+bstrString]; this
0x14001c8a5  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14001c8aa  test    eax, eax
0x14001c8ac  js      short loc_14001C92B
0x14001c8ae  mov     rcx, [rbp+4Fh+arg_10]
0x14001c8b2  mov     rax, [rcx]
0x14001c8b5  mov     rdx, [rbp+4Fh+bstrString]
0x14001c8b9  mov     rax, [rax+18h]
0x14001c8bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c8c2  nop
0x14001c8c3  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x14001c8c7  call    cs:__imp_SysFreeString
0x14001c8ce  nop     dword ptr [rax+rax+00h]
0x14001c8d3  nop
0x14001c8d4  mov     rcx, [rbp+4Fh+arg_10]
0x14001c8d8  test    rcx, rcx
0x14001c8db  jz      short loc_14001C8EA
0x14001c8dd  mov     rax, [rcx]
0x14001c8e0  mov     rax, [rax+10h]
0x14001c8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c8e9  nop
0x14001c8ea  test    rdi, rdi
0x14001c8ed  jz      short loc_14001C8FF
0x14001c8ef  mov     rcx, rdi
0x14001c8f2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14001c8f9  nop     dword ptr [rax+rax+00h]
0x14001c8fe  nop
0x14001c8ff  mov     rcx, [rbp+4Fh+var_30]
0x14001c903  test    rcx, rcx
0x14001c906  jz      short loc_14001C915
0x14001c908  mov     rax, [rcx]
0x14001c90b  mov     rax, [rax+10h]
0x14001c90f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c914  nop
0x14001c915  xor     eax, eax
0x14001c917  mov     rbx, [rsp+0B0h+arg_0]
0x14001c91f  add     rsp, 0A0h
0x14001c926  pop     rdi
0x14001c927  pop     rsi
0x14001c928  pop     rbp
0x14001c929  retn
0x14001c92b  mov     ecx, eax; int
0x14001c92d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14001c933  mov     ecx, 8007000Eh; int
0x14001c938  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
