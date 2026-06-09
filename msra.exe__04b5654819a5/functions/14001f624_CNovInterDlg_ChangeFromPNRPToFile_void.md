# CNovInterDlg::ChangeFromPNRPToFile(void)

- ea: `0x14001f624`
- end: `0x14001f89d`
- name: `?ChangeFromPNRPToFile@CNovInterDlg@@AEAAJXZ`
- size: `633`
- prototype: `__int64 __fastcall(CNovInterDlg *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140023830`

## callees

- `0x14001f624`
- `0x140024c44`
- `0x1400290c4`
- `0x14002981c`
- `0x140029978`
- `0x14002c670`
- `0x14002ceb0`
- `0x140034ce4`
- `0x14003db44`
- `0x14003ff50`
- `0x14004ad80`

## import_xrefs

- `USER32!GetWindowRect` at `0x14001f804`
- `USER32!GetWindowRect` at `0x14001f804`
- `USER32!MoveWindow` at `0x14001f82b`
- `USER32!MoveWindow` at `0x14001f82b`
- `msvcrt!_time64` at `0x14001f717`
- `msvcrt!_time64` at `0x14001f717`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f85e`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f872`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f85e`
- `OLEAUT32!__imp_SysFreeString` at `0x14001f872`

## pseudocode

```c
__int64 __fastcall CNovInterDlg::ChangeFromPNRPToFile(CNovInterDlg *this, __int64 a2, __int64 a3)
{
  unsigned __int16 *v3; // rdi
  HWND v4; // rdx
  CRATicket *v6; // r14
  signed int FileNameAsBSTR; // eax
  CEventLogger *v8; // rcx
  unsigned int v9; // ebx
  int v10; // r12d
  signed int UserInfoAsBSTR; // eax
  CEventLogger *v12; // rcx
  unsigned int v13; // r9d
  unsigned int v14; // eax
  int v15; // eax
  int v16; // edx
  unsigned int v18; // [rsp+40h] [rbp-19h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-11h] BYREF
  unsigned __int16 *v20; // [rsp+50h] [rbp-9h] BYREF
  __time64_t Time; // [rsp+58h] [rbp-1h] BYREF
  struct tagRECT Rect; // [rsp+60h] [rbp+7h] BYREF

  v3 = 0;
  v4 = (HWND)*((_QWORD *)this + 1);
  bstrString = 0;
  v20 = 0;
  v6 = (CRATicket *)*((_QWORD *)_AtlModule + 104);
  v18 = 0;
  Time = 0;
  Rect = 0;
  FileNameAsBSTR = GetFileNameAsBSTR(L"msrcincident", v4, a3, 2u, 0, 0x22Bu, &bstrString);
  v9 = FileNameAsBSTR;
  if ( FileNameAsBSTR < 0 )
  {
    CEventLogger::LogError(
      v8,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      0x149Eu,
      L"CNovInterDlg::ChangeFromPNRPToFile",
      FileNameAsBSTR);
    goto LABEL_18;
  }
  v10 = -2147467259;
  UserInfoAsBSTR = GetUserInfoAsBSTR(1, &v20);
  v3 = v20;
  v9 = UserInfoAsBSTR;
  if ( UserInfoAsBSTR < 0 )
  {
    v13 = 5284;
LABEL_13:
    CEventLogger::LogError(
      v12,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\novinterdialog.cpp",
      v13,
      L"CNovInterDlg::ChangeFromPNRPToFile",
      UserInfoAsBSTR);
    ShowRASpecificError(v10, *((HWND *)this + 1), 1);
    *((_DWORD *)v6 + 34) = 7;
    goto LABEL_18;
  }
  UserInfoAsBSTR = CRATicket::put_NoviceName(v6, v20);
  v9 = UserInfoAsBSTR;
  if ( UserInfoAsBSTR < 0 )
  {
    v13 = 5285;
    goto LABEL_13;
  }
  _time64(&Time);
  *((_DWORD *)v6 + 4) = Time;
  UserInfoAsBSTR = GetTicketDurationAsDWORD(&v18);
  v9 = UserInfoAsBSTR;
  if ( UserInfoAsBSTR < 0 )
  {
    v13 = 5295;
    goto LABEL_13;
  }
  v14 = v18;
  if ( !v18 )
    v14 = 60;
  *((_DWORD *)v6 + 36) = v14;
  *((_DWORD *)v6 + 34) = 1;
  v15 = VistaOnlyTicket();
  UserInfoAsBSTR = CRATicket::SaveRATicket((OLECHAR **)v6, bstrString, v15);
  v9 = UserInfoAsBSTR;
  if ( UserInfoAsBSTR < 0 )
  {
    v10 = -2147483121;
    v13 = 5312;
    goto LABEL_13;
  }
  v16 = 0;
  *((_DWORD *)this + 48) = 35;
  if ( !*((_DWORD *)this + 22) )
    LOBYTE(v16) = *(_DWORD *)(*((_QWORD *)_AtlModule + 104) + 136LL) != 3;
  CNovInterDlg::SetPWPanel(this, v16);
  GetWindowRect(*((HWND *)this + 1), &Rect);
  MoveWindow(*((HWND *)this + 1), Rect.left, Rect.top, Rect.right, Rect.bottom, 1);
  if ( *((_QWORD *)_AtlModule + 77) )
    *((_QWORD *)_AtlModule + 77) = 0;
LABEL_18:
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v3 )
    SysFreeString(v3);
  return v9;
}

```

## disassembly

```asm
0x14001f624  push    rbp
0x14001f626  push    rbx
0x14001f627  push    rsi
0x14001f628  push    rdi
0x14001f629  push    r12
0x14001f62b  push    r14
0x14001f62d  lea     rbp, [rsp-2Fh]
0x14001f632  sub     rsp, 88h
0x14001f639  mov     rax, cs:__security_cookie
0x14001f640  xor     rax, rsp
0x14001f643  mov     [rbp+57h+var_40], rax
0x14001f647  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001f64e  xor     edi, edi
0x14001f650  mov     rdx, [rcx+8]; HWND
0x14001f654  mov     rsi, rcx
0x14001f657  xorps   xmm0, xmm0
0x14001f65a  mov     [rbp+57h+bstrString], 0
0x14001f662  lea     rcx, aMsrcincident_0; "msrcincident"
0x14001f669  mov     [rbp+57h+var_60], rdi
0x14001f66d  mov     r14, [rax+340h]
0x14001f674  lea     r9d, [rdi+2]; unsigned int
0x14001f678  lea     rax, [rbp+57h+bstrString]
0x14001f67c  mov     [rbp+57h+var_70], edi
0x14001f67f  mov     [rsp+0B0h+var_80], rax; unsigned __int16 **
0x14001f684  mov     [rsp+0B0h+bRepaint], 22Bh; uID
0x14001f68c  mov     [rsp+0B0h+nHeight], edi; int
0x14001f690  mov     [rbp+57h+Time], rdi
0x14001f694  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x14001f698  call    ?GetFileNameAsBSTR@@YAJPEAGPEAUHWND__@@HKHHPEAPEAG@Z; GetFileNameAsBSTR(ushort *,HWND__ *,int,ulong,int,int,ushort * *)
0x14001f69d  mov     ebx, eax
0x14001f69f  test    eax, eax
0x14001f6a1  jns     short loc_14001F6D1
0x14001f6a3  mov     [rsp+0B0h+bRepaint], eax; unsigned int
0x14001f6a7  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x14001f6ae  lea     rax, aCnovinterdlgCh; "CNovInterDlg::ChangeFromPNRPToFile"
0x14001f6b5  mov     r9d, 149Eh; unsigned int
0x14001f6bb  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14001f6c2  mov     qword ptr [rsp+0B0h+nHeight], rax; unsigned __int16 *
0x14001f6c7  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001f6cc  jmp     loc_14001F853
0x14001f6d1  lea     rdx, [rbp+57h+var_60]
0x14001f6d5  mov     ecx, 1
0x14001f6da  mov     r12d, 80004005h
0x14001f6e0  call    ?GetUserInfoAsBSTR@@YAJW4_USERINFOTYPE@@PEAPEAG@Z; GetUserInfoAsBSTR(_USERINFOTYPE,ushort * *)
0x14001f6e5  mov     rdi, [rbp+57h+var_60]
0x14001f6e9  mov     ebx, eax
0x14001f6eb  test    eax, eax
0x14001f6ed  jns     short loc_14001F6FA
0x14001f6ef  mov     r9d, 14A4h
0x14001f6f5  jmp     loc_14001F786
0x14001f6fa  mov     rdx, rdi; unsigned __int16 *
0x14001f6fd  mov     rcx, r14; this
0x14001f700  call    ?put_NoviceName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_NoviceName(ushort *)
0x14001f705  mov     ebx, eax
0x14001f707  test    eax, eax
0x14001f709  jns     short loc_14001F713
0x14001f70b  mov     r9d, 14A5h
0x14001f711  jmp     short loc_14001F786
0x14001f713  lea     rcx, [rbp+57h+Time]; Time
0x14001f717  call    cs:__imp__time64
0x14001f71e  nop     dword ptr [rax+rax+00h]
0x14001f723  mov     eax, dword ptr [rbp+57h+Time]
0x14001f726  lea     rcx, [rbp+57h+var_70]; unsigned int *
0x14001f72a  mov     [r14+10h], eax
0x14001f72e  call    ?GetTicketDurationAsDWORD@@YAJPEAK@Z; GetTicketDurationAsDWORD(ulong *)
0x14001f733  mov     ebx, eax
0x14001f735  test    eax, eax
0x14001f737  jns     short loc_14001F741
0x14001f739  mov     r9d, 14AFh
0x14001f73f  jmp     short loc_14001F786
0x14001f741  mov     eax, [rbp+57h+var_70]
0x14001f744  mov     ecx, 3Ch ; '<'
0x14001f749  test    eax, eax
0x14001f74b  cmovz   eax, ecx
0x14001f74e  mov     [r14+90h], eax
0x14001f755  lea     r12d, [rcx-3Bh]
0x14001f759  mov     [r14+88h], r12d
0x14001f760  call    ?VistaOnlyTicket@@YAHXZ; VistaOnlyTicket(void)
0x14001f765  mov     rdx, [rbp+57h+bstrString]; unsigned __int16 *
0x14001f769  mov     r8d, eax; int
0x14001f76c  mov     rcx, r14; this
0x14001f76f  call    ?SaveRATicket@CRATicket@@QEAAJPEAGH@Z; CRATicket::SaveRATicket(ushort *,int)
0x14001f774  mov     ebx, eax
0x14001f776  test    eax, eax
0x14001f778  jns     short loc_14001F7CB
0x14001f77a  mov     r12d, 8000020Fh
0x14001f780  mov     r9d, 14C0h; unsigned int
0x14001f786  mov     [rsp+0B0h+bRepaint], eax; unsigned int
0x14001f78a  lea     r8, aBaseDiagnosisR_32; "base\\diagnosis\\ra\\ui\\novinterdialog"...
0x14001f791  lea     rax, aCnovinterdlgCh; "CNovInterDlg::ChangeFromPNRPToFile"
0x14001f798  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14001f79f  mov     qword ptr [rsp+0B0h+nHeight], rax; unsigned __int16 *
0x14001f7a4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001f7a9  mov     rdx, [rsi+8]; HWND
0x14001f7ad  mov     r8d, 1; int
0x14001f7b3  mov     ecx, r12d; int
0x14001f7b6  call    ?ShowRASpecificError@@YAHJPEAUHWND__@@H@Z; ShowRASpecificError(long,HWND__ *,int)
0x14001f7bb  mov     dword ptr [r14+88h], 7
0x14001f7c6  jmp     loc_14001F853
0x14001f7cb  xor     edx, edx
0x14001f7cd  mov     dword ptr [rsi+0C0h], 23h ; '#'
0x14001f7d7  cmp     [rsi+58h], edx
0x14001f7da  jnz     short loc_14001F7F4
0x14001f7dc  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001f7e3  mov     rcx, [rax+340h]
0x14001f7ea  cmp     dword ptr [rcx+88h], 3
0x14001f7f1  setnz   dl; int
0x14001f7f4  mov     rcx, rsi; this
0x14001f7f7  call    ?SetPWPanel@CNovInterDlg@@AEAAXH@Z; CNovInterDlg::SetPWPanel(int)
0x14001f7fc  mov     rcx, [rsi+8]; hWnd
0x14001f800  lea     rdx, [rbp+57h+Rect]; lpRect
0x14001f804  call    cs:__imp_GetWindowRect
0x14001f80b  nop     dword ptr [rax+rax+00h]
0x14001f810  mov     eax, [rbp+57h+Rect.bottom]
0x14001f813  mov     r9d, [rbp+57h+Rect.right]; nWidth
0x14001f817  mov     r8d, [rbp+57h+Rect.top]; Y
0x14001f81b  mov     edx, [rbp+57h+Rect.left]; X
0x14001f81e  mov     rcx, [rsi+8]; hWnd
0x14001f822  mov     [rsp+0B0h+bRepaint], r12d; bRepaint
0x14001f827  mov     [rsp+0B0h+nHeight], eax; nHeight
0x14001f82b  call    cs:__imp_MoveWindow
0x14001f832  nop     dword ptr [rax+rax+00h]
0x14001f837  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001f83e  cmp     qword ptr [rax+268h], 0
0x14001f846  jz      short loc_14001F853
0x14001f848  mov     qword ptr [rax+268h], 0
0x14001f853  cmp     [rbp+57h+bstrString], 0
0x14001f858  jz      short loc_14001F86A
0x14001f85a  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14001f85e  call    cs:__imp_SysFreeString
0x14001f865  nop     dword ptr [rax+rax+00h]
0x14001f86a  test    rdi, rdi
0x14001f86d  jz      short loc_14001F87E
0x14001f86f  mov     rcx, rdi; bstrString
0x14001f872  call    cs:__imp_SysFreeString
0x14001f879  nop     dword ptr [rax+rax+00h]
0x14001f87e  mov     eax, ebx
0x14001f880  mov     rcx, [rbp+57h+var_40]
0x14001f884  xor     rcx, rsp; StackCookie
0x14001f887  call    __security_check_cookie
0x14001f88c  add     rsp, 88h
0x14001f893  pop     r14
0x14001f895  pop     r12
0x14001f897  pop     rdi
0x14001f898  pop     rsi
0x14001f899  pop     rbx
0x14001f89a  pop     rbp
0x14001f89b  retn
```
