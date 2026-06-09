# CRemoteAssistanceApp::ProcessGetContactHelp(ushort *)

- ea: `0x14001417c`
- end: `0x14001456e`
- name: `?ProcessGetContactHelp@CRemoteAssistanceApp@@QEAAJPEAG@Z`
- size: `1010`
- prototype: `int(CRemoteAssistanceApp *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140012794`

## callees

- `0x14001417c`
- `0x140029334`
- `0x140034ce4`
- `0x14003fdbc`
- `0x14003fe58`
- `0x140040070`
- `0x140041998`
- `0x140041a4c`
- `0x140041cc8`
- `0x140043b64`
- `0x140043bcc`
- `0x140043c34`
- `0x140043c9c`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1400142f4`
- `KERNEL32!CompareStringW` at `0x1400142f4`
- `OLEAUT32!__imp_SysFreeString` at `0x140014312`
- `OLEAUT32!__imp_SysFreeString` at `0x14001433d`
- `OLEAUT32!__imp_SysFreeString` at `0x140014507`
- `OLEAUT32!__imp_SysFreeString` at `0x14001451b`
- `OLEAUT32!__imp_SysFreeString` at `0x14001452f`
- `OLEAUT32!__imp_SysFreeString` at `0x140014312`
- `OLEAUT32!__imp_SysFreeString` at `0x14001433d`
- `OLEAUT32!__imp_SysFreeString` at `0x140014507`
- `OLEAUT32!__imp_SysFreeString` at `0x14001451b`
- `OLEAUT32!__imp_SysFreeString` at `0x14001452f`
- `OLEAUT32!__imp_SysStringLen` at `0x140014256`
- `OLEAUT32!__imp_SysStringLen` at `0x1400142c3`
- `OLEAUT32!__imp_SysStringLen` at `0x140014256`
- `OLEAUT32!__imp_SysStringLen` at `0x1400142c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRemoteAssistanceApp::ProcessGetContactHelp(CRATicket **this, unsigned __int16 *a2)
{
  unsigned __int16 *v4; // r15
  signed int InvitationManagerLoaded; // eax
  CEventLogger *v6; // rcx
  signed int v7; // ebx
  int v8; // r14d
  CRAInvitationHistoryManager *v9; // rcx
  WCHAR *lpString2; // rdi
  __int64 **v11; // r14
  int v12; // r12d
  signed int Address; // eax
  CEventLogger *v14; // rcx
  UINT cchCount2; // eax
  signed int v16; // eax
  signed int PublicKey; // eax
  CEventLogger *v18; // rcx
  unsigned __int16 *v19; // r14
  signed int Name; // eax
  CEventLogger *v21; // rcx
  unsigned __int16 *v22; // rdi
  signed int ComputerName; // eax
  CEventLogger *v24; // rcx
  BSTR pbstr; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v27; // [rsp+38h] [rbp-C8h] BYREF
  BSTR v28; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v30; // [rsp+50h] [rbp-B0h]
  _OWORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+98h] [rbp-68h]
  _DWORD v35[122]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v36[9]; // [rsp+288h] [rbp+188h] BYREF
  UINT cchCount1; // [rsp+2F8h] [rbp+1F8h]

  v33 = 0;
  v34 = 0;
  memset(v31, 0, sizeof(v31));
  v32 = 0;
  v35[0] = 0;
  v35[1] = 1;
  v36[1] = v36;
  v36[0] = v36;
  v28 = 0;
  bstrString = 0;
  v4 = 0;
  v27 = 0;
  InvitationManagerLoaded = GetInvitationManagerLoaded((struct CRAInvitationHistoryManager *)v35, 3);
  v7 = InvitationManagerLoaded;
  if ( InvitationManagerLoaded < 0 )
  {
    CEventLogger::LogError(
      v6,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x863u,
      L"CRemoteAssistanceApp::ProcessGetContactHelp",
      InvitationManagerLoaded);
    goto LABEL_38;
  }
  v8 = 0;
  cchCount1 = SysStringLen(a2);
  lpString2 = 0;
  pbstr = 0;
  if ( v35[0] <= 0 )
  {
    v7 = 0;
  }
  else
  {
    v11 = (__int64 **)v36[0];
    v12 = 0;
    v7 = 0;
    while ( 1 )
    {
      if ( v11 == v36 )
        goto LABEL_13;
      v30 = *v11;
      Address = CRAInvitationHistoryItem::get_Address((CRAInvitationHistoryItem *)v11[2], &pbstr);
      v7 = Address;
      if ( Address < 0 )
      {
        CEventLogger::LogError(
          v14,
          &Recoverable_Error,
          (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
          0x452u,
          L"CRAInvitationHistoryManager::get_InvitationItemByMatch",
          Address);
        lpString2 = pbstr;
        goto LABEL_13;
      }
      lpString2 = pbstr;
      cchCount2 = SysStringLen(pbstr);
      v9 = (CRAInvitationHistoryManager *)cchCount1;
      if ( cchCount1 == cchCount2 && CompareStringW(0x7Fu, 1u, a2, cchCount1, lpString2, cchCount2) == 2 )
        break;
      v11 = (__int64 **)v30;
      if ( lpString2 )
      {
        SysFreeString(lpString2);
        lpString2 = 0;
        pbstr = 0;
      }
      if ( ++v12 >= v35[0] )
        goto LABEL_13;
    }
    v16 = CRAInvitationHistoryManager::CloneHistoryItem(
            v9,
            (struct CRAInvitationHistoryItem *)v11[2],
            (struct CRAInvitationHistoryItem *)v31);
    v7 = v16;
    if ( v16 < 0 )
    {
      CEventLogger::LogError(
        v9,
        &Recoverable_Error,
        (unsigned __int16 *)"b\x00a\x00s\x00e\x00\\\x00d\x00i\x00a\x00g\x00n\x00o\x00s\x00i\x00s\x00\\\x00r\x00a\x00\\\x00c\x00o\x00r\x00e\x00\\\x00l\x00i\x00b\x00\\\x00r\x00a\x00h\x00i\x00s\x00t\x00o\x00r\x00y\x00.\x00c\x00p\x00p",
        0x468u,
        L"CRAInvitationHistoryManager::get_InvitationItemByMatch",
        v16);
LABEL_13:
      v8 = 0;
      goto LABEL_14;
    }
    v8 = 1;
  }
LABEL_14:
  if ( lpString2 )
    SysFreeString(lpString2);
  if ( !v8 )
  {
    v7 = -2147467259;
LABEL_24:
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x864u,
      L"CRemoteAssistanceApp::ProcessGetContactHelp",
      v7);
    goto LABEL_38;
  }
  if ( v7 < 0 )
    goto LABEL_24;
  PublicKey = CRAInvitationHistoryItem::get_PublicKey((CRAInvitationHistoryItem *)v31, &v28);
  v7 = PublicKey;
  v19 = v28;
  if ( PublicKey >= 0 )
  {
    Name = CRAInvitationHistoryItem::get_Name((CRAInvitationHistoryItem *)v31, &bstrString);
    v7 = Name;
    v22 = bstrString;
    if ( Name >= 0 )
    {
      ComputerName = CRAInvitationHistoryItem::get_ComputerName((CRAInvitationHistoryItem *)v31, &v27);
      v7 = ComputerName;
      if ( ComputerName >= 0 )
      {
        CRATicket::put_ExpertName(this[104], v22);
        v4 = v27;
        CRATicket::put_ComputerName(this[104], v27);
        CRATicket::put_PNRPAddress(this[104], v19);
        *((_DWORD *)this + 205) = 10;
        *((_DWORD *)this[104] + 34) = 8;
      }
      else
      {
        CEventLogger::LogError(
          v24,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\app.cpp",
          0x867u,
          L"CRemoteAssistanceApp::ProcessGetContactHelp",
          ComputerName);
        v4 = v27;
      }
    }
    else
    {
      CEventLogger::LogError(
        v21,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\app.cpp",
        0x866u,
        L"CRemoteAssistanceApp::ProcessGetContactHelp",
        Name);
    }
    if ( v22 )
      SysFreeString(v22);
  }
  else
  {
    CEventLogger::LogError(
      v18,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x865u,
      L"CRemoteAssistanceApp::ProcessGetContactHelp",
      PublicKey);
  }
  if ( v19 )
    SysFreeString(v19);
  if ( v4 )
    SysFreeString(v4);
LABEL_38:
  CRAInvitationHistoryManager::EmptyList((CRAInvitationHistoryManager *)v35);
  CRAInvitationHistoryItem::~CRAInvitationHistoryItem((CRAInvitationHistoryItem *)v31);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001417c  mov     [rsp-8+arg_0], rbx
0x140014181  mov     [rsp-8+lpString1], rdx
0x140014186  push    rbp
0x140014187  push    rsi
0x140014188  push    rdi
0x140014189  push    r12
0x14001418b  push    r13
0x14001418d  push    r14
0x14001418f  push    r15
0x140014191  lea     rbp, [rsp-1A0h]
0x140014199  sub     rsp, 2A0h
0x1400141a0  mov     rdi, rdx
0x1400141a3  mov     r13, rcx
0x1400141a6  xorps   xmm0, xmm0
0x1400141a9  movups  [rbp+1D0h+var_248], xmm0
0x1400141ad  mov     [rbp+1D0h+var_238], 0
0x1400141b4  movdqa  [rsp+2D0h+var_270], xmm0
0x1400141ba  xorps   xmm1, xmm1
0x1400141bd  movdqa  [rsp+2D0h+var_260], xmm1
0x1400141c3  mov     [rbp+1D0h+var_250], 0
0x1400141cb  mov     [rbp+1D0h+var_230], 0
0x1400141d2  mov     [rbp+1D0h+var_22C], 1
0x1400141d9  lea     rax, [rbp+1D0h+var_48]
0x1400141e0  mov     [rbp+1D0h+var_40], rax
0x1400141e7  lea     rax, [rbp+1D0h+var_48]
0x1400141ee  mov     [rbp+1D0h+var_48], rax
0x1400141f5  mov     [rsp+2D0h+var_290], 0
0x1400141fe  mov     [rsp+2D0h+bstrString], 0
0x140014207  xor     r15d, r15d
0x14001420a  mov     [rsp+2D0h+var_298], r15
0x14001420f  lea     edx, [r15+3]; int
0x140014213  lea     rcx, [rbp+1D0h+var_230]; this
0x140014217  call    ?GetInvitationManagerLoaded@@YAJPEAVCRAInvitationHistoryManager@@H@Z; GetInvitationManagerLoaded(CRAInvitationHistoryManager *,int)
0x14001421c  mov     ebx, eax
0x14001421e  test    eax, eax
0x140014220  jns     short loc_140014250
0x140014222  mov     [rsp+2D0h+cchCount2], eax; unsigned int
0x140014226  mov     r9d, 863h; unsigned int
0x14001422c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140014233  lea     rax, aCremoteassista_1; "CRemoteAssistanceApp::ProcessGetContact"...
0x14001423a  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x140014241  mov     [rsp+2D0h+lpString2], rax; unsigned __int16 *
0x140014246  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001424b  jmp     loc_14001453C
0x140014250  xor     r14d, r14d
0x140014253  mov     rcx, rdi; pbstr
0x140014256  call    cs:__imp_SysStringLen
0x14001425d  nop     dword ptr [rax+rax+00h]
0x140014262  mov     [rbp+1D0h+cchCount1], eax
0x140014268  xor     edi, edi
0x14001426a  mov     [rsp+2D0h+pbstr], rdi
0x14001426f  lea     rsi, Recoverable_Error
0x140014276  cmp     [rbp+1D0h+var_230], edi
0x140014279  jle     loc_1400143CB
0x14001427f  mov     r14, [rbp+1D0h+var_48]
0x140014286  xor     r12d, r12d
0x140014289  xor     ebx, ebx
0x14001428b  lea     rax, [rbp+1D0h+var_48]
0x140014292  cmp     r14, rax
0x140014295  jz      loc_140014332
0x14001429b  mov     rax, [r14]
0x14001429e  mov     [rsp+2D0h+var_280], rax
0x1400142a3  lea     rdx, [rsp+2D0h+pbstr]; unsigned __int16 **
0x1400142a8  mov     rcx, [r14+10h]; this
0x1400142ac  call    ?get_Address@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_Address(ushort * *)
0x1400142b1  mov     ebx, eax
0x1400142b3  test    eax, eax
0x1400142b5  js      loc_14001439C
0x1400142bb  mov     rdi, [rsp+2D0h+pbstr]
0x1400142c0  mov     rcx, rdi; pbstr
0x1400142c3  call    cs:__imp_SysStringLen
0x1400142ca  nop     dword ptr [rax+rax+00h]
0x1400142cf  mov     ecx, [rbp+1D0h+cchCount1]
0x1400142d5  cmp     ecx, eax
0x1400142d7  jnz     short loc_140014305
0x1400142d9  mov     [rsp+2D0h+cchCount2], eax; cchCount2
0x1400142dd  mov     [rsp+2D0h+lpString2], rdi; lpString2
0x1400142e2  mov     r9d, ecx; cchCount1
0x1400142e5  mov     r8, [rbp+1D0h+lpString1]; lpString1
0x1400142ec  mov     edx, 1; dwCmpFlags
0x1400142f1  lea     ecx, [rdx+7Eh]; Locale
0x1400142f4  call    cs:__imp_CompareStringW
0x1400142fb  nop     dword ptr [rax+rax+00h]
0x140014300  cmp     eax, 2
0x140014303  jz      short loc_140014359
0x140014305  mov     r14, [rsp+2D0h+var_280]
0x14001430a  test    rdi, rdi
0x14001430d  jz      short loc_140014325
0x14001430f  mov     rcx, rdi; bstrString
0x140014312  call    cs:__imp_SysFreeString
0x140014319  nop     dword ptr [rax+rax+00h]
0x14001431e  xor     edi, edi
0x140014320  mov     [rsp+2D0h+pbstr], rdi
0x140014325  inc     r12d
0x140014328  cmp     r12d, [rbp+1D0h+var_230]
0x14001432c  jl      loc_14001428B
0x140014332  mov     r14d, r15d
0x140014335  test    rdi, rdi
0x140014338  jz      short loc_140014349
0x14001433a  mov     rcx, rdi; bstrString
0x14001433d  call    cs:__imp_SysFreeString
0x140014344  nop     dword ptr [rax+rax+00h]
0x140014349  test    r14d, r14d
0x14001434c  jnz     loc_1400143D2
0x140014352  mov     ebx, 80004005h
0x140014357  jmp     short loc_1400143D6
0x140014359  lea     r8, [rsp+2D0h+var_270]; struct CRAInvitationHistoryItem *
0x14001435e  mov     rdx, [r14+10h]; struct CRAInvitationHistoryItem *
0x140014362  call    ?CloneHistoryItem@CRAInvitationHistoryManager@@AEAAJPEAVCRAInvitationHistoryItem@@0@Z; CRAInvitationHistoryManager::CloneHistoryItem(CRAInvitationHistoryItem *,CRAInvitationHistoryItem *)
0x140014367  mov     ebx, eax
0x140014369  test    eax, eax
0x14001436b  jns     short loc_140014394
0x14001436d  mov     [rsp+2D0h+cchCount2], eax; unsigned int
0x140014371  lea     rax, aCrainvitationh_4; "CRAInvitationHistoryManager::get_Invita"...
0x140014378  mov     [rsp+2D0h+lpString2], rax; unsigned __int16 *
0x14001437d  mov     r9d, 468h; unsigned int
0x140014383  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x14001438a  mov     rdx, rsi; struct _EVENT_DESCRIPTOR *
0x14001438d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014392  jmp     short loc_140014332
0x140014394  mov     r14d, 1
0x14001439a  jmp     short loc_140014335
0x14001439c  mov     [rsp+2D0h+cchCount2], eax; unsigned int
0x1400143a0  lea     rax, aCrainvitationh_4; "CRAInvitationHistoryManager::get_Invita"...
0x1400143a7  mov     [rsp+2D0h+lpString2], rax; unsigned __int16 *
0x1400143ac  mov     r9d, 452h; unsigned int
0x1400143b2  lea     r8, a0123456789abcd+10h; unsigned __int16 *
0x1400143b9  mov     rdx, rsi; struct _EVENT_DESCRIPTOR *
0x1400143bc  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400143c1  mov     rdi, [rsp+2D0h+pbstr]
0x1400143c6  jmp     loc_140014332
0x1400143cb  xor     ebx, ebx
0x1400143cd  jmp     loc_140014335
0x1400143d2  test    ebx, ebx
0x1400143d4  jns     short loc_1400143E8
0x1400143d6  mov     [rsp+2D0h+cchCount2], ebx
0x1400143da  mov     r9d, 864h
0x1400143e0  mov     rdx, rsi
0x1400143e3  jmp     loc_140014233
0x1400143e8  lea     rdx, [rsp+2D0h+var_290]; unsigned __int16 **
0x1400143ed  lea     rcx, [rsp+2D0h+var_270]; this
0x1400143f2  call    ?get_PublicKey@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_PublicKey(ushort * *)
0x1400143f7  mov     ebx, eax
0x1400143f9  mov     r14, [rsp+2D0h+var_290]
0x1400143fe  test    eax, eax
0x140014400  jns     short loc_14001442C
0x140014402  mov     [rsp+2D0h+cchCount2], eax; unsigned int
0x140014406  lea     rax, aCremoteassista_1; "CRemoteAssistanceApp::ProcessGetContact"...
0x14001440d  mov     [rsp+2D0h+lpString2], rax; unsigned __int16 *
0x140014412  mov     r9d, 865h; unsigned int
0x140014418  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14001441f  mov     rdx, rsi; struct _EVENT_DESCRIPTOR *
0x140014422  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014427  jmp     loc_140014513
0x14001442c  lea     rdx, [rsp+2D0h+bstrString]; unsigned __int16 **
0x140014431  lea     rcx, [rsp+2D0h+var_270]; this
0x140014436  call    ?get_Name@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_Name(ushort * *)
0x14001443b  mov     ebx, eax
0x14001443d  mov     rdi, [rsp+2D0h+bstrString]
0x140014442  test    eax, eax
0x140014444  jns     short loc_140014470
0x140014446  mov     [rsp+2D0h+cchCount2], eax; unsigned int
0x14001444a  lea     rax, aCremoteassista_1; "CRemoteAssistanceApp::ProcessGetContact"...
0x140014451  mov     [rsp+2D0h+lpString2], rax; unsigned __int16 *
0x140014456  mov     r9d, 866h; unsigned int
0x14001445c  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x140014463  mov     rdx, rsi; struct _EVENT_DESCRIPTOR *
0x140014466  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001446b  jmp     loc_1400144FF
0x140014470  lea     rdx, [rsp+2D0h+var_298]; unsigned __int16 **
0x140014475  lea     rcx, [rsp+2D0h+var_270]; this
0x14001447a  call    ?get_ComputerName@CRAInvitationHistoryItem@@QEAAJPEAPEAG@Z; CRAInvitationHistoryItem::get_ComputerName(ushort * *)
0x14001447f  mov     ebx, eax
0x140014481  test    eax, eax
0x140014483  jns     short loc_1400144B1
0x140014485  mov     [rsp+2D0h+cchCount2], eax; unsigned int
0x140014489  lea     rax, aCremoteassista_1; "CRemoteAssistanceApp::ProcessGetContact"...
0x140014490  mov     [rsp+2D0h+lpString2], rax; unsigned __int16 *
0x140014495  mov     r9d, 867h; unsigned int
0x14001449b  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x1400144a2  mov     rdx, rsi; struct _EVENT_DESCRIPTOR *
0x1400144a5  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400144aa  mov     r15, [rsp+2D0h+var_298]
0x1400144af  jmp     short loc_1400144FF
0x1400144b1  mov     rdx, rdi; unsigned __int16 *
0x1400144b4  mov     rcx, [r13+340h]; this
0x1400144bb  call    ?put_ExpertName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_ExpertName(ushort *)
0x1400144c0  mov     r15, [rsp+2D0h+var_298]
0x1400144c5  mov     rdx, r15; unsigned __int16 *
0x1400144c8  mov     rcx, [r13+340h]; this
0x1400144cf  call    ?put_ComputerName@CRATicket@@QEAAJPEAG@Z; CRATicket::put_ComputerName(ushort *)
0x1400144d4  mov     rdx, r14; unsigned __int16 *
0x1400144d7  mov     rcx, [r13+340h]; this
0x1400144de  call    ?put_PNRPAddress@CRATicket@@QEAAJPEAG@Z; CRATicket::put_PNRPAddress(ushort *)
0x1400144e3  mov     dword ptr [r13+334h], 0Ah
0x1400144ee  mov     rax, [r13+340h]
0x1400144f5  mov     dword ptr [rax+88h], 8
0x1400144ff  test    rdi, rdi
0x140014502  jz      short loc_140014513
0x140014504  mov     rcx, rdi; bstrString
0x140014507  call    cs:__imp_SysFreeString
0x14001450e  nop     dword ptr [rax+rax+00h]
0x140014513  test    r14, r14
0x140014516  jz      short loc_140014527
0x140014518  mov     rcx, r14; bstrString
0x14001451b  call    cs:__imp_SysFreeString
0x140014522  nop     dword ptr [rax+rax+00h]
0x140014527  test    r15, r15
0x14001452a  jz      short loc_14001453C
0x14001452c  mov     rcx, r15; bstrString
0x14001452f  call    cs:__imp_SysFreeString
0x140014536  nop     dword ptr [rax+rax+00h]
0x14001453b  nop
0x14001453c  lea     rcx, [rbp+1D0h+var_230]; this
0x140014540  call    ?EmptyList@CRAInvitationHistoryManager@@AEAAXXZ; CRAInvitationHistoryManager::EmptyList(void)
0x140014545  nop
0x140014546  lea     rcx, [rsp+2D0h+var_270]; this
0x14001454b  call    ??1CRAInvitationHistoryItem@@QEAA@XZ; CRAInvitationHistoryItem::~CRAInvitationHistoryItem(void)
0x140014550  mov     eax, ebx
0x140014552  mov     rbx, [rsp+2D0h+arg_0]
0x14001455a  add     rsp, 2A0h
0x140014561  pop     r15
0x140014563  pop     r14
0x140014565  pop     r13
0x140014567  pop     r12
0x140014569  pop     rdi
0x14001456a  pop     rsi
0x14001456b  pop     rbp
0x14001456c  retn
```
