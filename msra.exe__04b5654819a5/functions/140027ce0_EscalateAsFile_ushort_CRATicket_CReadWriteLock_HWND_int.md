# EscalateAsFile(ushort *,CRATicket *,CReadWriteLock *,HWND__ *,int)

- ea: `0x140027ce0`
- end: `0x140027f1c`
- name: `?EscalateAsFile@@YAJPEAGPEAVCRATicket@@PEAVCReadWriteLock@@PEAUHWND__@@H@Z`
- size: `572`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, struct CRATicket *this@<rdx>, struct CReadWriteLock *@<r8>, HWND@<r9>, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1400146cc`
- `0x140032274`

## callees

- `0x140016a34`
- `0x140027ce0`
- `0x14002981c`
- `0x140029978`
- `0x14002b26c`
- `0x14002c670`
- `0x14002cb94`
- `0x14002ceb0`
- `0x140034ce4`
- `0x140034eac`
- `0x140037c8c`
- `0x1400383c8`
- `0x140038470`
- `0x14003af44`
- `0x14003db44`
- `0x14003ff50`

## import_xrefs

- `msvcrt!_time64` at `0x140027e0d`
- `msvcrt!_time64` at `0x140027e0d`
- `OLEAUT32!__imp_SysFreeString` at `0x140027ee5`
- `OLEAUT32!__imp_SysFreeString` at `0x140027ee5`

## string_xrefs

- `0x140027dae`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140027e93`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall EscalateAsFile(
        unsigned __int16 *a1,
        LPVOID *this,
        struct CReadWriteLock *a3,
        HWND a4,
        unsigned int a5)
{
  OLECHAR *v5; // rdi
  CEventLogger *v9; // rcx
  int v10; // ebp
  int v11; // ebx
  signed int Ticket; // eax
  CEventLogger *v13; // rcx
  signed int UserInfoAsBSTR; // eax
  CEventLogger *v15; // rcx
  signed int v16; // eax
  CEventLogger *v17; // rcx
  signed int TicketDurationAsDWORD; // eax
  CEventLogger *v19; // rcx
  int v20; // eax
  int v21; // eax
  CRemoteAssistanceApp *v22; // rcx
  CEventLogger *v23; // rcx
  char *v24; // rcx
  CEventLogger *v25; // rcx
  __time64_t Time[7]; // [rsp+30h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+18h] BYREF

  v5 = 0;
  bstrString = 0;
  Time[0] = 0;
  a5 = 0;
  if ( !(unsigned int)TakeLock(1) )
  {
    v10 = -2147483099;
    v11 = -2147467259;
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x373u,
      L"EscalateAsFile",
      0x80004005);
LABEL_15:
    ReleaseLock(1);
    goto LABEL_17;
  }
  CSqmManager::StartTimer((CEventLogger *)((char *)_AtlModule + 496), 1u);
  Ticket = CRATicket::CreateTicket(this);
  v11 = Ticket;
  if ( Ticket < 0 )
  {
    v10 = -2147483122;
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x37Cu,
      L"EscalateAsFile",
      Ticket);
    goto LABEL_15;
  }
  CSqmManager::StopTimer((CEventLogger *)((char *)_AtlModule + 496), 1u, 1);
  v10 = -2147467259;
  UserInfoAsBSTR = GetUserInfoAsBSTR(1, &bstrString);
  v11 = UserInfoAsBSTR;
  if ( UserInfoAsBSTR < 0 )
  {
    CEventLogger::LogError(
      v15,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x383u,
      L"EscalateAsFile",
      UserInfoAsBSTR);
    v5 = bstrString;
    goto LABEL_15;
  }
  v5 = bstrString;
  v16 = CRATicket::put_NoviceName((CRATicket *)this, bstrString);
  v11 = v16;
  if ( v16 < 0 )
  {
    CEventLogger::LogError(
      v17,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x384u,
      L"EscalateAsFile",
      v16);
    goto LABEL_15;
  }
  _time64(Time);
  *((_DWORD *)this + 4) = Time[0];
  TicketDurationAsDWORD = GetTicketDurationAsDWORD(&a5);
  v11 = TicketDurationAsDWORD;
  if ( TicketDurationAsDWORD < 0 )
  {
    CEventLogger::LogError(
      v19,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x38Eu,
      L"EscalateAsFile",
      TicketDurationAsDWORD);
    goto LABEL_15;
  }
  v20 = a5;
  v10 = -2147483121;
  if ( !a5 )
    v20 = 60;
  *((_DWORD *)this + 36) = v20;
  v21 = VistaOnlyTicket();
  v11 = CRATicket::SaveRATicket((OLECHAR **)this, a1, v21);
  if ( v11 < 0 )
  {
    CRemoteAssistanceApp::ResetTicketAndClearVC(v22);
    v11 = -2147024809;
    CEventLogger::LogError(
      v23,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x3A3u,
      L"EscalateAsFile",
      0x80070057);
    goto LABEL_15;
  }
  v24 = (char *)_AtlModule + 496;
  *((_DWORD *)_AtlModule + 131) = 3;
  CSqmManager::ProcessRAEvent(v24, 0);
  CEventLogger::LogEvent(v25, &Invitation_Opened);
LABEL_17:
  if ( v5 )
    SysFreeString(v5);
  if ( v11 < 0 )
    ShowRASpecificError(v10, a4, 1);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140027ce0  mov     rax, rsp
0x140027ce3  mov     [rax+8], rbx
0x140027ce7  mov     [rax+10h], rbp
0x140027ceb  mov     [rax+18h], r8
0x140027cef  push    rsi
0x140027cf0  push    rdi
0x140027cf1  push    r12
0x140027cf3  push    r14
0x140027cf5  push    r15
0x140027cf7  sub     rsp, 40h
0x140027cfb  xor     edi, edi
0x140027cfd  mov     r14, rcx
0x140027d00  mov     r15, r9
0x140027d03  mov     [rax+18h], rdi
0x140027d07  mov     rsi, rdx
0x140027d0a  mov     [rax-38h], rdi
0x140027d0e  mov     [rax+28h], edi
0x140027d11  lea     r12d, [rdi+1]
0x140027d15  mov     ecx, r12d; int
0x140027d18  call    ?TakeLock@@YAHH@Z; TakeLock(int)
0x140027d1d  test    eax, eax
0x140027d1f  jnz     short loc_140027D3E
0x140027d21  mov     ebp, 80000225h
0x140027d26  mov     [rsp+68h+var_40], 80004005h
0x140027d2e  mov     ebx, 80004005h
0x140027d33  mov     r9d, 373h
0x140027d39  jmp     loc_140027E8C
0x140027d3e  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140027d45  mov     edx, r12d; unsigned int
0x140027d48  add     rcx, 1F0h; this
0x140027d4f  call    ?StartTimer@CSqmManager@@QEAAXK@Z; CSqmManager::StartTimer(ulong)
0x140027d54  mov     rcx, rsi; this
0x140027d57  call    ?CreateTicket@CRATicket@@QEAAJXZ; CRATicket::CreateTicket(void)
0x140027d5c  mov     ebx, eax
0x140027d5e  test    eax, eax
0x140027d60  jns     short loc_140027D76
0x140027d62  mov     ebp, 8000020Eh
0x140027d67  mov     [rsp+68h+var_40], eax
0x140027d6b  mov     r9d, 37Ch
0x140027d71  jmp     loc_140027E8C
0x140027d76  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140027d7d  mov     r8d, r12d; int
0x140027d80  add     rcx, 1F0h; this
0x140027d87  mov     edx, r12d; unsigned int
0x140027d8a  call    ?StopTimer@CSqmManager@@QEAAKKH@Z; CSqmManager::StopTimer(ulong,int)
0x140027d8f  lea     rdx, [rsp+68h+bstrString]
0x140027d97  mov     ecx, r12d
0x140027d9a  mov     ebp, 80004005h
0x140027d9f  call    ?GetUserInfoAsBSTR@@YAJW4_USERINFOTYPE@@PEAPEAG@Z; GetUserInfoAsBSTR(_USERINFOTYPE,ushort * *)
0x140027da4  mov     ebx, eax
0x140027da6  test    eax, eax
0x140027da8  jns     short loc_140027DE0
0x140027daa  mov     [rsp+68h+var_40], eax; unsigned int
0x140027dae  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140027db5  lea     rax, aEscalateasfile; "EscalateAsFile"
0x140027dbc  mov     r9d, 383h; unsigned int
0x140027dc2  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140027dc9  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x140027dce  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140027dd3  mov     rdi, [rsp+68h+bstrString]
0x140027ddb  jmp     loc_140027EAB
0x140027de0  mov     rdi, [rsp+68h+bstrString]
0x140027de8  mov     rcx, rsi; this
0x140027deb  mov     rdx, rdi; unsigned __int16 *
0x140027dee  call    ?put_NoviceName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_NoviceName(ushort *)
0x140027df3  mov     ebx, eax
0x140027df5  test    eax, eax
0x140027df7  jns     short loc_140027E08
0x140027df9  mov     [rsp+68h+var_40], eax
0x140027dfd  mov     r9d, 384h
0x140027e03  jmp     loc_140027E8C
0x140027e08  lea     rcx, [rsp+68h+Time]; Time
0x140027e0d  call    cs:__imp__time64
0x140027e14  nop     dword ptr [rax+rax+00h]
0x140027e19  mov     eax, dword ptr [rsp+68h+Time]
0x140027e1d  lea     rcx, [rsp+68h+arg_20]; unsigned int *
0x140027e25  mov     [rsi+10h], eax
0x140027e28  call    ?GetTicketDurationAsDWORD@@YAJPEAK@Z; GetTicketDurationAsDWORD(ulong *)
0x140027e2d  mov     ebx, eax
0x140027e2f  test    eax, eax
0x140027e31  jns     short loc_140027E3F
0x140027e33  mov     [rsp+68h+var_40], eax
0x140027e37  mov     r9d, 38Eh
0x140027e3d  jmp     short loc_140027E8C
0x140027e3f  mov     eax, [rsp+68h+arg_20]
0x140027e46  mov     ecx, 3Ch ; '<'
0x140027e4b  test    eax, eax
0x140027e4d  mov     ebp, 8000020Fh
0x140027e52  cmovz   eax, ecx
0x140027e55  mov     [rsi+90h], eax
0x140027e5b  call    ?VistaOnlyTicket@@YAHXZ; VistaOnlyTicket(void)
0x140027e60  mov     r8d, eax; int
0x140027e63  mov     rdx, r14; unsigned __int16 *
0x140027e66  mov     rcx, rsi; this
0x140027e69  call    ?SaveRATicket@CRATicket@@QEAAJPEAGH@Z; CRATicket::SaveRATicket(ushort *,int)
0x140027e6e  mov     ebx, eax
0x140027e70  test    eax, eax
0x140027e72  jns     short loc_140027EB5
0x140027e74  call    ?ResetTicketAndClearVC@CRemoteAssistanceApp@@QEAAJXZ; CRemoteAssistanceApp::ResetTicketAndClearVC(void)
0x140027e79  mov     r9d, 3A3h; unsigned int
0x140027e7f  mov     [rsp+68h+var_40], 80070057h; unsigned int
0x140027e87  mov     ebx, 80070057h
0x140027e8c  lea     rax, aEscalateasfile; "EscalateAsFile"
0x140027e93  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140027e9a  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x140027e9f  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140027ea6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140027eab  mov     ecx, r12d; int
0x140027eae  call    ?ReleaseLock@@YAXH@Z; ReleaseLock(int)
0x140027eb3  jmp     short loc_140027EDD
0x140027eb5  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140027ebc  xor     edx, edx
0x140027ebe  add     rcx, 1F0h
0x140027ec5  mov     dword ptr [rcx+1Ch], 3
0x140027ecc  call    ?ProcessRAEvent@CSqmManager@@QEAAXW4_RASQM_EVENT@@@Z; CSqmManager::ProcessRAEvent(_RASQM_EVENT)
0x140027ed1  lea     rdx, Invitation_Opened; struct _EVENT_DESCRIPTOR *
0x140027ed8  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)
0x140027edd  test    rdi, rdi
0x140027ee0  jz      short loc_140027EF1
0x140027ee2  mov     rcx, rdi; bstrString
0x140027ee5  call    cs:__imp_SysFreeString
0x140027eec  nop     dword ptr [rax+rax+00h]
0x140027ef1  test    ebx, ebx
0x140027ef3  jns     short loc_140027F02
0x140027ef5  mov     r8d, r12d; int
0x140027ef8  mov     rdx, r15; HWND
0x140027efb  mov     ecx, ebp; int
0x140027efd  call    ?ShowRASpecificError@@YAHJPEAUHWND__@@H@Z; ShowRASpecificError(long,HWND__ *,int)
0x140027f02  mov     rbp, [rsp+68h+arg_8]
0x140027f07  mov     eax, ebx
0x140027f09  mov     rbx, [rsp+68h+arg_0]
0x140027f0e  add     rsp, 40h
0x140027f12  pop     r15
0x140027f14  pop     r14
0x140027f16  pop     r12
0x140027f18  pop     rdi
0x140027f19  pop     rsi
0x140027f1a  retn
```
