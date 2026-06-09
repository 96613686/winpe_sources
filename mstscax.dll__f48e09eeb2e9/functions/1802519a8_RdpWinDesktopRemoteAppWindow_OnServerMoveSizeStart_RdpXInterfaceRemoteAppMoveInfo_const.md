# RdpWinDesktopRemoteAppWindow::OnServerMoveSizeStart(RdpXInterfaceRemoteAppMoveInfo * const)

- ea: `0x1802519a8`
- end: `0x180252056`
- name: `?OnServerMoveSizeStart@RdpWinDesktopRemoteAppWindow@@QEAAJQEAURdpXInterfaceRemoteAppMoveInfo@@@Z`
- size: `1710`
- prototype: `__int64 __fastcall(RdpWinDesktopRemoteAppWindow *__hidden this, struct RdpXInterfaceRemoteAppMoveInfo *const)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180257fd0`

## callees

- `0x1800011f4`
- `0x180002660`
- `0x180039c98`
- `0x180039ce4`
- `0x18005e07c`
- `0x1800829d4`
- `0x180082ad8`
- `0x1800e9b1c`
- `0x18024d590`
- `0x18024e830`
- `0x18024ea20`
- `0x18024fac0`
- `0x180250150`
- `0x1802519a8`
- `0x1802551dc`
- `0x18025649c`
- `0x18025d94c`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180251b38`
- `KERNEL32!GetLastError` at `0x180251c66`
- `KERNEL32!GetLastError` at `0x180251d8c`
- `KERNEL32!GetLastError` at `0x180251b38`
- `KERNEL32!GetLastError` at `0x180251c66`
- `KERNEL32!GetLastError` at `0x180251d8c`
- `USER32!GetWindowLongPtrW` at `0x180251d78`
- `USER32!GetWindowLongPtrW` at `0x180251d78`
- `USER32!SetWindowLongPtrW` at `0x180251e2d`
- `USER32!SetWindowLongPtrW` at `0x180251e2d`
- `USER32!SystemParametersInfoW` at `0x180251b2e`
- `USER32!SystemParametersInfoW` at `0x180251c5c`
- `USER32!SystemParametersInfoW` at `0x18025202b`
- `USER32!SystemParametersInfoW` at `0x180251b2e`
- `USER32!SystemParametersInfoW` at `0x180251c5c`
- `USER32!SystemParametersInfoW` at `0x18025202b`

## string_xrefs

- `0x1802519bd`: `clientcore\termsrv\rdp\win\remoteapp\remoteappplugin\implementation\rdpwin32remoteappwindow.cpp`
- `0x180251dbb`: `clientcore\termsrv\rdp\win\remoteapp\remoteappplugin\implementation\rdpwin32remoteappwindow.cpp`
- `0x180251e0b`: `clientcore\termsrv\rdp\win\remoteapp\remoteappplugin\implementation\rdpwin32remoteappwindow.cpp`
- `0x180251fff`: `clientcore\termsrv\rdp\win\remoteapp\remoteappplugin\implementation\rdpwin32remoteappwindow.cpp`
- `0x180251a5b`: `Start of Move/size on server.`
- `0x1802519f7`: `pMoveSizeInfo`
- `0x180251bd1`: `Move/size in HiDef mode - skipping local move/size`
- `0x180251af3`: `Local movesize not allowed. Skipping`
- `0x180251a9f`: `Unexpected duplicate notification, we are already in the middle of movesize`
- `0x180251aaa`: `OnServerMoveSizeStart`
- `0x180251ba5`: `OnServerMoveSizeStart`
- `0x180251dac`: `GetWindowLongPtr failed. Skipping movesize`
- `0x180251d50`: `GetHittestFromMovesizeType failed`
- `0x180251cb3`: `Movesize in outline drag mode. Continuing local movesize`
- `0x180251fd5`: `InitiateMouseLocalMoveSize failed`
- `0x180251f4c`: `InitiateSyscommandLocalMoveSize failed`

## pseudocode

```c
__int64 __fastcall RdpWinDesktopRemoteAppWindow::OnServerMoveSizeStart(
        RdpWinDesktopRemoteAppWindow *this,
        struct RdpXInterfaceRemoteAppMoveInfo *const a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int HittestFromMovesizeType; // ebx
  unsigned int v6; // eax
  int v7; // r8d
  int v8; // r9d
  int v9; // ecx
  unsigned int v10; // r14d
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  signed int LastError; // edi
  unsigned int v15; // eax
  __int64 v16; // rdx
  RdpWinDesktopRemoteAppWindow *v18; // rcx
  unsigned int v19; // eax
  int v20; // edx
  const char *v21; // rcx
  unsigned int WindowLongPtrW; // eax
  signed int v23; // eax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // r9d
  WindowsRemoteAppLib::CTSWindowInformation *v28; // rcx
  UINT v29; // edx
  BOOL v30; // eax
  const char *v31; // r9
  __int64 v32; // [rsp+28h] [rbp-48h]
  int v33[2]; // [rsp+50h] [rbp-20h] BYREF
  int v34[2]; // [rsp+58h] [rbp-18h] BYREF
  const char *v35; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int pvParam; // [rsp+B8h] [rbp+48h] BYREF
  const char *v38; // [rsp+C0h] [rbp+50h] BYREF
  const char *v39; // [rsp+C8h] [rbp+58h] BYREF

  pvParam = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        182,
        (unsigned int)&WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"pMoveSizeInfo",
        -2147467259);
    }
    HittestFromMovesizeType = -2147467259;
    goto LABEL_75;
  }
  v6 = (*(__int64 (__fastcall **)(struct RdpXInterfaceRemoteAppMoveInfo *const))(*(_QWORD *)a2 + 40LL))(a2);
  v9 = dword_1808B5850;
  v10 = v6;
  if ( (unsigned int)dword_1808B5850 > 5 )
  {
    LODWORD(v38) = v6;
    v39 = "Start of Move/size on server.";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1808B5850,
      (unsigned int)byte_1808614F5,
      v7,
      v8,
      (__int64)&v39,
      (__int64)&v38);
  }
  if ( *((_DWORD *)this + 228) )
  {
    HittestFromMovesizeType = 0;
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v39 = "Unexpected duplicate notification, we are already in the middle of movesize";
      v38 = "OnServerMoveSizeStart";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)word_180861522,
        v7,
        v8,
        (__int64)&v39,
        (__int64)&v38);
    }
    return (unsigned int)HittestFromMovesizeType;
  }
  if ( !*((_DWORD *)this + 231) )
  {
    HittestFromMovesizeType = 0;
    if ( (unsigned int)dword_1808B5850 > 5 )
    {
      v38 = "Local movesize not allowed. Skipping";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)byte_180861465,
        0,
        v8,
        (__int64)&v38);
    }
    return (unsigned int)HittestFromMovesizeType;
  }
  if ( !SystemParametersInfoW(0x26u, 0, &pvParam, 0) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_21;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 183;
LABEL_20:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      &WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids,
      v15,
      LastError);
LABEL_21:
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
    HittestFromMovesizeType = LastError;
    goto LABEL_75;
  }
  if ( pvParam )
  {
    if ( *(_DWORD *)(*((_QWORD *)this + 149) + 176LL) )
    {
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v38 = "OnServerMoveSizeStart";
        v39 = "Move/size in HiDef mode - skipping local move/size";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v11,
          (unsigned int)&dword_180861484,
          v12,
          v13,
          (__int64)&v39,
          (__int64)&v38);
      }
      return 0;
    }
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v38 = "OnServerMoveSizeStart";
      v39 = "In non Hi-def mode, resetting SPI for drag windows.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)byte_1808614AD,
        v12,
        v13,
        (__int64)&v39,
        (__int64)&v38);
    }
    *((_DWORD *)this + 285) = pvParam;
    pvParam = 0;
    if ( !SystemParametersInfoW(0x25u, 0, 0, 0) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_21;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 184;
      goto LABEL_20;
    }
  }
  if ( (unsigned int)dword_1808B5850 > 5 )
  {
    v38 = "Movesize in outline drag mode. Continuing local movesize";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_1808B5850,
      (unsigned int)&word_1808614D6,
      0,
      v13,
      (__int64)&v38);
  }
  RdpWinDesktopRemoteAppWindow::ResetLocalMoveSizeState(this, 4);
  RdpXSPtr<RdpXInterfaceLayerManager>::operator=((char *)this + 240, a2);
  *((_DWORD *)this + 229) = 1;
  HittestFromMovesizeType = RdpWinDesktopRemoteAppWindow::GetHittestFromMovesizeType(v18, v10, (__int64 *)this + 134);
  if ( HittestFromMovesizeType < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 185;
      v21 = "GetHittestFromMovesizeType failed";
LABEL_74:
      LODWORD(v32) = HittestFromMovesizeType;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        (unsigned int)&WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids,
        v19,
        (__int64)v21,
        v32);
    }
LABEL_75:
    RdpWinDesktopRemoteAppWindow::ResetLocalMoveSizeState(this, 5);
    v29 = *((_DWORD *)this + 285);
    if ( v29 )
    {
      v30 = SystemParametersInfoW(0x25u, v29, 0, 0);
      *((_DWORD *)this + 285) = 0;
      if ( !v30 )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x174C,
          (unsigned int)"clientcore\\termsrv\\rdp\\win\\remoteapp\\remoteappplugin\\implementation\\rdpwin32remoteappwindow.cpp",
          v31);
    }
    return (unsigned int)HittestFromMovesizeType;
  }
  if ( (unsigned __int64)(*((_QWORD *)this + 134) - 10LL) > 7 )
  {
LABEL_56:
    v28 = (WindowsRemoteAppLib::CTSWindowInformation *)*((_QWORD *)this + 17);
    v34[0] = 0;
    v33[0] = 0;
    LODWORD(v39) = 0;
    LODWORD(v38) = 0;
    WindowsRemoteAppLib::CTSWindowInformation::GetWndSize(v28, (int *)&v39, (int *)&v38);
    WindowsRemoteAppLib::CTSWindowInformation::GetWndOffset(
      *((WindowsRemoteAppLib::CTSWindowInformation **)this + 17),
      v34,
      v33);
    RdpWinDesktopRemoteAppWindow::SetRemoteAppWindowPos(
      this,
      0,
      (unsigned int)v34[0],
      (unsigned int)v33[0],
      (_DWORD)v39,
      (_DWORD)v38,
      8980,
      13);
    if ( v10 == 10 )
    {
      HittestFromMovesizeType = RdpWinDesktopRemoteAppWindow::InitiateSyscommandLocalMoveSize(this, 0xF010u);
      if ( HittestFromMovesizeType < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_75;
        }
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 186;
        goto LABEL_62;
      }
    }
    else if ( v10 == 11 )
    {
      HittestFromMovesizeType = RdpWinDesktopRemoteAppWindow::InitiateSyscommandLocalMoveSize(this, 0xF000u);
      if ( HittestFromMovesizeType < 0 )
      {
        if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
          || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_75;
        }
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 187;
LABEL_62:
        v21 = "InitiateSyscommandLocalMoveSize failed";
        goto LABEL_74;
      }
    }
    else
    {
      HittestFromMovesizeType = RdpWinDesktopRemoteAppWindow::InitiateMouseLocalMoveSize(this);
      if ( HittestFromMovesizeType < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 188;
          v21 = "InitiateMouseLocalMoveSize failed";
          goto LABEL_74;
        }
        goto LABEL_75;
      }
    }
    return 0;
  }
  WindowLongPtrW = GetWindowLongPtrW(*((HWND *)this + 6), -16);
  *((_DWORD *)this + 270) = WindowLongPtrW;
  if ( WindowLongPtrW )
  {
    SetWindowLongPtrW(*((HWND *)this + 6), -16, WindowLongPtrW | 0x40000LL);
    RdpWinDesktopRemoteAppWindow::SetRemoteAppWindowPos(this, 0, 0, 0, 0, 0, 55, 12);
    if ( (unsigned int)dword_1808B5850 > 5 )
    {
      v38 = "Changed window style for resize";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)byte_1808613DB,
        0,
        v27,
        (__int64)&v38);
    }
    goto LABEL_56;
  }
  v23 = GetLastError();
  HittestFromMovesizeType = v23;
  if ( v23 > 0 )
    HittestFromMovesizeType = (unsigned __int16)v23 | 0x80070000;
  if ( (unsigned int)dword_1808B5850 > 2 )
  {
    *(_QWORD *)v34 = "OnServerMoveSizeStart";
    v35 = "GetWindowLongPtr failed. Skipping movesize";
    LODWORD(v38) = 5906;
    *(_QWORD *)v33 = "clientcore\\termsrv\\rdp\\win\\remoteapp\\remoteappplugin\\implementation\\rdpwin32remoteappwindow.cpp";
    LODWORD(v39) = HittestFromMovesizeType;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v24,
      (unsigned int)qword_180861398,
      v25,
      v26,
      (__int64)&v35,
      (__int64)&v39,
      (__int64)v33,
      (__int64)&v38,
      (__int64)v34);
  }
  if ( HittestFromMovesizeType < 0 )
    goto LABEL_75;
  return (unsigned int)HittestFromMovesizeType;
}

```

## disassembly

```asm
0x1802519a8  push    rbp
0x1802519aa  push    rbx
0x1802519ab  push    rsi
0x1802519ac  push    rdi
0x1802519ad  push    r12
0x1802519af  push    r14
0x1802519b1  push    r15
0x1802519b3  mov     rbp, rsp
0x1802519b6  sub     rsp, 70h
0x1802519ba  xor     r12d, r12d
0x1802519bd  lea     rdi, aClientcoreTerm_36; "clientcore\\termsrv\\rdp\\win\\remoteap"...
0x1802519c4  mov     [rbp+pvParam], r12d
0x1802519c8  mov     rbx, rdx
0x1802519cb  mov     rsi, rcx
0x1802519ce  test    rdx, rdx
0x1802519d1  jnz     short loc_180251A34
0x1802519d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1802519da  lea     rax, WPP_GLOBAL_Control
0x1802519e1  cmp     rcx, rax
0x1802519e4  jz      short loc_180251A2A
0x1802519e6  test    byte ptr [rcx+1Ch], 8
0x1802519ea  jz      short loc_180251A2A
0x1802519ec  cmp     byte ptr [rcx+19h], 2
0x1802519f0  jb      short loc_180251A2A
0x1802519f2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1802519f7  lea     rcx, aPmovesizeinfo; "pMoveSizeInfo"
0x1802519fe  mov     dword ptr [rsp+70h+var_48], 80004005h
0x180251a06  mov     [rsp+70h+var_50], rcx
0x180251a0b  lea     r8, WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids
0x180251a12  mov     rcx, cs:WPP_GLOBAL_Control
0x180251a19  mov     edx, 0B6h
0x180251a1e  mov     r9d, eax
0x180251a21  mov     rcx, [rcx+10h]
0x180251a25  call    WPP_SF_DsD
0x180251a2a  mov     ebx, 80004005h
0x180251a2f  jmp     loc_180252006
0x180251a34  mov     rax, [rdx]
0x180251a37  mov     rcx, rbx
0x180251a3a  mov     rax, [rax+28h]
0x180251a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180251a43  mov     ecx, cs:dword_1808B5850
0x180251a49  mov     r14d, eax
0x180251a4c  cmp     ecx, 5
0x180251a4f  jbe     short loc_180251A84
0x180251a51  mov     dword ptr [rbp+arg_10], eax
0x180251a54  lea     rdx, byte_1808614F5
0x180251a5b  lea     rax, aStartOfMoveSiz; "Start of Move/size on server."
0x180251a62  mov     [rbp+arg_18], rax
0x180251a66  lea     rcx, dword_1808B5850
0x180251a6d  lea     rax, [rbp+arg_10]
0x180251a71  mov     [rsp+70h+var_48], rax
0x180251a76  lea     rax, [rbp+arg_18]
0x180251a7a  mov     [rsp+70h+var_50], rax
0x180251a7f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180251a84  cmp     [rsi+390h], r12d
0x180251a8b  jz      short loc_180251AD8
0x180251a8d  mov     eax, cs:dword_1808B5850
0x180251a93  mov     ebx, r12d
0x180251a96  cmp     eax, 4
0x180251a99  jbe     loc_180251C01
0x180251a9f  lea     rax, aUnexpectedDupl; "Unexpected duplicate notification, we a"...
0x180251aa6  mov     [rbp+arg_18], rax
0x180251aaa  lea     rdi, aOnservermovesi; "OnServerMoveSizeStart"
0x180251ab1  lea     rax, [rbp+arg_10]
0x180251ab5  mov     [rbp+arg_10], rdi
0x180251ab9  mov     [rsp+70h+var_48], rax
0x180251abe  lea     rdx, word_180861522
0x180251ac5  lea     rax, [rbp+arg_18]
0x180251ac9  mov     [rsp+70h+var_50], rax
0x180251ace  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180251ad3  jmp     loc_180251C01
0x180251ad8  cmp     [rsi+39Ch], r12d
0x180251adf  jnz     short loc_180251B22
0x180251ae1  mov     eax, cs:dword_1808B5850
0x180251ae7  mov     ebx, r12d
0x180251aea  cmp     eax, 5
0x180251aed  jbe     loc_180251C01
0x180251af3  lea     rax, aLocalMovesizeN; "Local movesize not allowed. Skipping"
0x180251afa  xor     r8d, r8d
0x180251afd  mov     [rbp+arg_10], rax
0x180251b01  lea     rdx, byte_180861465
0x180251b08  lea     rax, [rbp+arg_10]
0x180251b0c  lea     rcx, dword_1808B5850
0x180251b13  mov     [rsp+70h+var_50], rax
0x180251b18  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180251b1d  jmp     loc_180251C01
0x180251b22  xor     edx, edx; uiParam
0x180251b24  lea     r8, [rbp+pvParam]; pvParam
0x180251b28  xor     r9d, r9d; fWinIni
0x180251b2b  lea     ecx, [rdx+26h]; uiAction
0x180251b2e  call    cs:__imp_SystemParametersInfoW
0x180251b34  test    eax, eax
0x180251b36  jnz     short loc_180251BA5
0x180251b38  call    cs:__imp_GetLastError
0x180251b3e  mov     edi, eax
0x180251b40  mov     rcx, cs:WPP_GLOBAL_Control
0x180251b47  lea     rax, WPP_GLOBAL_Control
0x180251b4e  cmp     rcx, rax
0x180251b51  jz      short loc_180251B87
0x180251b53  test    byte ptr [rcx+1Ch], 8
0x180251b57  jz      short loc_180251B87
0x180251b59  cmp     byte ptr [rcx+19h], 2
0x180251b5d  jb      short loc_180251B87
0x180251b5f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180251b64  mov     edx, 0B7h
0x180251b69  mov     rcx, cs:WPP_GLOBAL_Control
0x180251b70  lea     r8, WPP_b9fbef0724383b2abfac2d1be7fb3719_Traceguids
0x180251b77  mov     r9d, eax
0x180251b7a  mov     dword ptr [rsp+70h+var_50], edi
0x180251b7e  mov     rcx, [rcx+10h]
0x180251b82  call    WPP_SF_Dd
0x180251b87  test    edi, edi
0x180251b89  jle     short loc_180251B94
0x180251b8b  movzx   edi, di
0x180251b8e  or      edi, 80070000h
0x180251b94  mov     ebx, 80004005h
0x180251b99  test    edi, edi
0x180251b9b  cmovns  edi, ebx
0x180251b9e  mov     ebx, edi
0x180251ba0  jmp     loc_180251FFF
0x180251ba5  lea     rdi, aOnservermovesi; "OnServerMoveSizeStart"
0x180251bac  cmp     [rbp+pvParam], r12d
0x180251bb0  jz      loc_180251CA8
0x180251bb6  mov     rax, [rsi+4A8h]
0x180251bbd  cmp     [rax+0B0h], r12d
0x180251bc4  mov     eax, cs:dword_1808B5850
0x180251bca  jz      short loc_180251C12
0x180251bcc  cmp     eax, 4
0x180251bcf  jbe     short loc_180251BFE
0x180251bd1  lea     rax, aMoveSizeInHide; "Move/size in HiDef mode - skipping loca"...
0x180251bd8  mov     [rbp+arg_10], rdi
0x180251bdc  mov     [rbp+arg_18], rax
0x180251be0  lea     rdx, dword_180861484
0x180251be7  lea     rax, [rbp+arg_10]
0x180251beb  mov     [rsp+70h+var_48], rax
0x180251bf0  lea     rax, [rbp+arg_18]
0x180251bf4  mov     [rsp+70h+var_50], rax
0x180251bf9  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180251bfe  mov     ebx, r12d
0x180251c01  mov     eax, ebx
0x180251c03  add     rsp, 70h
0x180251c07  pop     r15
0x180251c09  pop     r14
0x180251c0b  pop     r12
0x180251c0d  pop     rdi
0x180251c0e  pop     rsi
0x180251c0f  pop     rbx
0x180251c10  pop     rbp
0x180251c11  retn
0x180251c12  cmp     eax, 4
0x180251c15  jbe     short loc_180251C44
0x180251c17  lea     rax, aInNonHiDefMode; "In non Hi-def mode, resetting SPI for d"...
0x180251c1e  mov     [rbp+arg_10], rdi
0x180251c22  mov     [rbp+arg_18], rax
0x180251c26  lea     rdx, byte_1808614AD
0x180251c2d  lea     rax, [rbp+arg_10]
0x180251c31  mov     [rsp+70h+var_48], rax
0x180251c36  lea     rax, [rbp+arg_18]
0x180251c3a  mov     [rsp+70h+var_50], rax
0x180251c3f  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180251c44  mov     eax, [rbp+pvParam]
0x180251c47  xor     edx, edx; uiParam
0x180251c49  xor     r9d, r9d; fWinIni
0x180251c4c  mov     [rsi+474h], eax
0x180251c52  xor     r8d, r8d; pvParam
0x180251c55  mov     [rbp+pvParam], r12d
0x180251c59  lea     ecx, [rdx+25h]; uiAction
0x180251c5c  call    cs:__imp_SystemParametersInfoW
0x180251c62  test    eax, eax
0x180251c64  jnz     short loc_180251CA8
0x180251c66  call    cs:__imp_GetLastError
0x180251c6c  mov     edi, eax
0x180251c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180251c75  lea     rax, WPP_GLOBAL_Control
0x180251c7c  cmp     rcx, rax
0x180251c7f  jz      loc_180251B87
0x180251c85  test    byte ptr [rcx+1Ch], 8
0x180251c89  jz      loc_180251B87
0x180251c8f  cmp     byte ptr [rcx+19h], 2
0x180251c93  jb      loc_180251B87
0x180251c99  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180251c9e  mov     edx, 0B8h
0x180251ca3  jmp     loc_180251B69
0x180251ca8  mov     eax, cs:dword_1808B5850
0x180251cae  cmp     eax, 5
0x180251cb1  jbe     short loc_180251CDD
0x180251cb3  lea     rax, aMovesizeInOutl; "Movesize in outline drag mode. Continui"...
0x180251cba  xor     r8d, r8d
0x180251cbd  mov     [rbp+arg_10], rax
0x180251cc1  lea     rdx, word_1808614D6
0x180251cc8  lea     rax, [rbp+arg_10]
0x180251ccc  lea     rcx, dword_1808B5850
0x180251cd3  mov     [rsp+70h+var_50], rax
0x180251cd8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180251cdd  mov     edx, 4
0x180251ce2  mov     rcx, rsi
0x180251ce5  call    ?ResetLocalMoveSizeState@RdpWinDesktopRemoteAppWindow@@QEAAXW4MoveSizeReason_End@@@Z; RdpWinDesktopRemoteAppWindow::ResetLocalMoveSizeState(MoveSizeReason_End)
0x180251cea  lea     rcx, [rsi+0F0h]
0x180251cf1  mov     rdx, rbx
0x180251cf4  call    ??4?$RdpXSPtr@URdpXInterfaceLayerManager@@@@QEAAPEAURdpXInterfaceLayerManager@@PEAU1@@Z; RdpXSPtr<RdpXInterfaceLayerManager>::operator=(RdpXInterfaceLayerManager *)
0x180251cf9  lea     r15, [rsi+430h]
0x180251d00  mov     dword ptr [rsi+394h], 1
0x180251d0a  mov     r8, r15; __int64 *
0x180251d0d  mov     edx, r14d; unsigned int
0x180251d10  call    ?GetHittestFromMovesizeType@RdpWinDesktopRemoteAppWindow@@IEAAJIPEA_J@Z; RdpWinDesktopRemoteAppWindow::GetHittestFromMovesizeType(uint,__int64 *)
0x180251d15  mov     ebx, eax
0x180251d17  test    eax, eax
0x180251d19  jns     short loc_180251D5C
0x180251d1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180251d22  lea     rax, WPP_GLOBAL_Control
0x180251d29  cmp     rcx, rax
0x180251d2c  jz      loc_180251FFF
0x180251d32  test    byte ptr [rcx+1Ch], 8
0x180251d36  jz      loc_180251FFF
0x180251d3c  cmp     byte ptr [rcx+19h], 2
0x180251d40  jb      loc_180251FFF
0x180251d46  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180251d4b  mov     edx, 0B9h
0x180251d50  lea     rcx, aGethittestfrom_0; "GetHittestFromMovesizeType failed"
0x180251d57  jmp     loc_180251FDC
0x180251d5c  mov     rax, [r15]
0x180251d5f  sub     rax, 0Ah
0x180251d63  cmp     rax, 7
0x180251d67  ja      loc_180251E92
0x180251d6d  mov     rcx, [rsi+30h]; hWnd
0x180251d71  mov     ebx, 0FFFFFFF0h
0x180251d76  mov     edx, ebx; nIndex
0x180251d78  call    cs:__imp_GetWindowLongPtrW
0x180251d7e  mov     [rsi+438h], eax
0x180251d84  test    eax, eax
0x180251d86  jnz     loc_180251E1F
0x180251d8c  call    cs:__imp_GetLastError
0x180251d92  mov     ebx, eax
0x180251d94  test    eax, eax
0x180251d96  jle     short loc_180251DA1
0x180251d98  movzx   ebx, ax
0x180251d9b  or      ebx, 80070000h
0x180251da1  mov     eax, cs:dword_1808B5850
0x180251da7  cmp     eax, 2
0x180251daa  jbe     short loc_180251E0B
0x180251dac  lea     rax, aGetwindowlongp; "GetWindowLongPtr failed. Skipping moves"...
0x180251db3  mov     qword ptr [rbp+var_18], rdi
0x180251db7  mov     [rbp+var_10], rax
0x180251dbb  lea     rdi, aClientcoreTerm_36; "clientcore\\termsrv\\rdp\\win\\remoteap"...
0x180251dc2  lea     rax, [rbp+var_18]
0x180251dc6  mov     dword ptr [rbp+arg_10], 1712h
0x180251dcd  mov     [rsp+70h+var_30], rax
0x180251dd2  lea     rdx, qword_180861398
0x180251dd9  lea     rax, [rbp+arg_10]
0x180251ddd  mov     qword ptr [rbp+var_20], rdi
0x180251de1  mov     [rsp+70h+var_38], rax
0x180251de6  lea     rax, [rbp+var_20]
0x180251dea  mov     [rsp+70h+var_40], rax
0x180251def  lea     rax, [rbp+arg_18]
0x180251df3  mov     [rsp+70h+var_48], rax
0x180251df8  lea     rax, [rbp+var_10]
0x180251dfc  mov     [rsp+70h+var_50], rax
0x180251e01  mov     dword ptr [rbp+arg_18], ebx
0x180251e04  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180251e09  jmp     short loc_180251E12
0x180251e0b  lea     rdi, aClientcoreTerm_36; "clientcore\\termsrv\\rdp\\win\\remoteap"...
0x180251e12  test    ebx, ebx
0x180251e14  jns     loc_180251C01
0x180251e1a  jmp     loc_180252006
0x180251e1f  mov     rcx, [rsi+30h]; hWnd
0x180251e23  mov     edx, ebx; nIndex
0x180251e25  mov     r8d, eax
0x180251e28  bts     r8, 12h; dwNewLong
0x180251e2d  call    cs:__imp_SetWindowLongPtrW
0x180251e33  mov     dword ptr [rsp+70h+var_38], 0Ch
0x180251e3b  xor     r9d, r9d
0x180251e3e  mov     dword ptr [rsp+70h+var_40], 37h ; '7'
0x180251e46  xor     r8d, r8d
0x180251e49  mov     dword ptr [rsp+70h+var_48], r12d
0x180251e4e  xor     edx, edx
0x180251e50  mov     rcx, rsi
0x180251e53  mov     dword ptr [rsp+70h+var_50], r12d
0x180251e58  call    ?SetRemoteAppWindowPos@RdpWinDesktopRemoteAppWindow@@IEAAHPEAUHWND__@@HHHHHW4SetRemoteAppWindowPosReason@@@Z; RdpWinDesktopRemoteAppWindow::SetRemoteAppWindowPos(HWND__ *,int,int,int,int,int,SetRemoteAppWindowPosReason)
0x180251e5d  mov     eax, cs:dword_1808B5850
0x180251e63  cmp     eax, 5
0x180251e66  jbe     short loc_180251E92
0x180251e68  lea     rax, aChangedWindowS; "Changed window style for resize"
0x180251e6f  xor     r8d, r8d
0x180251e72  mov     [rbp+arg_10], rax
0x180251e76  lea     rdx, byte_1808613DB
0x180251e7d  lea     rax, [rbp+arg_10]
0x180251e81  lea     rcx, dword_1808B5850
0x180251e88  mov     [rsp+70h+var_50], rax
0x180251e8d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180251e92  mov     rcx, [rsi+88h]; this
0x180251e99  lea     r8, [rbp+arg_10]; int *
0x180251e9d  lea     rdx, [rbp+arg_18]; int *
0x180251ea1  mov     [rbp+var_18], r12d
0x180251ea5  mov     [rbp+var_20], r12d
0x180251ea9  mov     dword ptr [rbp+arg_18], r12d
0x180251ead  mov     dword ptr [rbp+arg_10], r12d
0x180251eb1  call    ?GetWndSize@CTSWindowInformation@WindowsRemoteAppLib@@UEBAJPEAH0@Z; WindowsRemoteAppLib::CTSWindowInformation::GetWndSize(int *,int *)
0x180251eb6  mov     rcx, [rsi+88h]; this
0x180251ebd  lea     r8, [rbp+var_20]; int *
0x180251ec1  lea     rdx, [rbp+var_18]; int *
  ... truncated ...
```
