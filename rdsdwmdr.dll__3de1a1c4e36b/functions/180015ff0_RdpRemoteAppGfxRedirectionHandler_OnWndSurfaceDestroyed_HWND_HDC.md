# RdpRemoteAppGfxRedirectionHandler::OnWndSurfaceDestroyed(HWND__ *,HDC__ *)

- ea: `0x180015ff0`
- end: `0x180016184`
- name: `?OnWndSurfaceDestroyed@RdpRemoteAppGfxRedirectionHandler@@UEAAJPEAUHWND__@@PEAUHDC__@@@Z`
- size: `404`
- prototype: `int(RdpRemoteAppGfxRedirectionHandler *__hidden this, HWND, HDC)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001188`
- `0x180001724`
- `0x180001bfc`
- `0x180005f9c`
- `0x180012b7c`
- `0x180015ff0`
- `0x180016970`
- `0x18002c010`

## string_xrefs

- `0x180016090`: `Failed to remove dirty surface context`
- `0x1800160f0`: `Failed to send delete surface event to client`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::OnWndSurfaceDestroyed(
        RdpRemoteAppGfxRedirectionHandler *this,
        HWND a2,
        __int64 a3,
        __int64 a4)
{
  int v6; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v13; // [rsp+50h] [rbp-30h] BYREF
  const char *v14; // [rsp+58h] [rbp-28h] BYREF
  const char *v15; // [rsp+60h] [rbp-20h] BYREF
  const char *v16; // [rsp+68h] [rbp-18h] BYREF
  const char *v17; // [rsp+70h] [rbp-10h] BYREF
  HWND v18; // [rsp+A0h] [rbp+20h] BYREF
  const char *v19; // [rsp+B8h] [rbp+38h] BYREF

  v13 = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v18 = a2;
    v19 = "OnWndSurfaceDestroyed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
      (__int64)this,
      (__int64)byte_18003C821,
      a3,
      a4,
      (const unsigned __int16 **)&v19,
      (__int64)&v18);
  }
  if ( (unsigned int)CTSSimpleComPtrArray<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::Find<HWND__ *,&public: static int RdpRemoteAppGfxRedirectionHandler::DirtySurface::MatchSurfaceByHWND(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface *)>(
                       (__int64)this + 64,
                       (__int64)a2,
                       &v13) )
  {
    v6 = (*(__int64 (__fastcall **)(char *, __int64))(*((_QWORD *)this + 8) + 16LL))((char *)this + 64, v13);
    if ( v6 < 0 && (unsigned int)dword_180044008 > 3 )
    {
      LODWORD(v18) = v6;
      v19 = "OnWndSurfaceDestroyed";
      v14 = "Failed to remove dirty surface context";
      v15 = "HResult failed but continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (unsigned int)dword_180044008,
        (__int64)byte_18003C7D1,
        v7,
        v8,
        (const unsigned __int16 **)&v15,
        (const unsigned __int16 **)&v14,
        (__int64)&v18,
        (const unsigned __int16 **)&v19);
    }
  }
  v9 = RdpRemoteAppGfxRedirectionHandler::SendDeleteSurfacePdu(
         (RdpRemoteAppGfxRedirectionHandler *)((char *)this - 48),
         a2);
  if ( v9 < 0 && (unsigned int)dword_180044008 > 2 )
  {
    v14 = "OnWndSurfaceDestroyed";
    v15 = "Failed to send delete surface event to client";
    LODWORD(v18) = 992;
    v16 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    v17 = "Error HResult failed";
    LODWORD(v19) = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)&byte_18003C76F,
      v10,
      v11,
      (const unsigned __int16 **)&v17,
      (__int64)&v19,
      (const unsigned __int16 **)&v16,
      (__int64)&v18,
      (const unsigned __int16 **)&v14,
      (const unsigned __int16 **)&v15);
  }
  TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(&v13);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180015ff0  mov     r11, rsp
0x180015ff3  mov     [r11+10h], rbx
0x180015ff7  mov     [r11+18h], rsi
0x180015ffb  push    rbp
0x180015ffc  push    rdi
0x180015ffd  push    r14
0x180015fff  mov     rbp, rsp
0x180016002  sub     rsp, 80h
0x180016009  mov     eax, cs:dword_180044008
0x18001600f  lea     r14, aOnwndsurfacede; "OnWndSurfaceDestroyed"
0x180016016  mov     [rbp+var_30], 0
0x18001601e  mov     rbx, rdx
0x180016021  mov     rsi, rcx
0x180016024  cmp     eax, 5
0x180016027  jbe     short loc_18001604D
0x180016029  lea     rax, [rbp+arg_0]
0x18001602d  mov     [rbp+arg_0], rdx
0x180016031  mov     [r11-70h], rax
0x180016035  lea     rdx, byte_18003C821
0x18001603c  lea     rax, [rbp+arg_18]
0x180016040  mov     [rbp+arg_18], r14
0x180016044  mov     [r11-78h], rax
0x180016048  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18001604d  lea     rdi, [rsi+40h]
0x180016051  mov     rdx, rbx
0x180016054  mov     rcx, rdi
0x180016057  lea     r8, [rbp+var_30]
0x18001605b  call    ??$Find@PEAUHWND__@@$1?MatchSurfaceByHWND@DirtySurface@RdpRemoteAppGfxRedirectionHandler@@SAHPEAU1@PEAV34@@Z@?$CTSSimpleComPtrArray@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@QEAAHPEAUHWND__@@PEAPEAVDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@Z; CTSSimpleComPtrArray<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::Find<HWND__ *,&RdpRemoteAppGfxRedirectionHandler::DirtySurface::MatchSurfaceByHWND(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface *)>(HWND__ *,RdpRemoteAppGfxRedirectionHandler::DirtySurface * *)
0x180016060  test    eax, eax
0x180016062  jz      short loc_1800160D3
0x180016064  mov     rax, [rdi]
0x180016067  mov     rcx, rdi
0x18001606a  mov     rdx, [rbp+var_30]
0x18001606e  mov     rax, [rax+10h]
0x180016072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016077  test    eax, eax
0x180016079  jns     short loc_1800160D3
0x18001607b  mov     ecx, cs:dword_180044008
0x180016081  cmp     ecx, 3
0x180016084  jbe     short loc_1800160D3
0x180016086  mov     dword ptr [rbp+arg_0], eax
0x180016089  lea     rdx, byte_18003C7D1
0x180016090  lea     rax, aFailedToRemove_0; "Failed to remove dirty surface context"
0x180016097  mov     [rbp+arg_18], r14
0x18001609b  mov     [rbp+var_28], rax
0x18001609f  lea     rax, aHresultFailedB; "HResult failed but continue"
0x1800160a6  mov     [rbp+var_20], rax
0x1800160aa  lea     rax, [rbp+arg_18]
0x1800160ae  mov     [rsp+80h+var_48], rax
0x1800160b3  lea     rax, [rbp+arg_0]
0x1800160b7  mov     [rsp+80h+var_50], rax
0x1800160bc  lea     rax, [rbp+var_28]
0x1800160c0  mov     [rsp+80h+var_58], rax
0x1800160c5  lea     rax, [rbp+var_20]
0x1800160c9  mov     [rsp+80h+var_60], rax
0x1800160ce  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800160d3  lea     rcx, [rsi-30h]; this
0x1800160d7  mov     rdx, rbx; HWND
0x1800160da  call    ?SendDeleteSurfacePdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJPEAUHWND__@@@Z; RdpRemoteAppGfxRedirectionHandler::SendDeleteSurfacePdu(HWND__ *)
0x1800160df  mov     ebx, eax
0x1800160e1  test    eax, eax
0x1800160e3  jns     short loc_180016161
0x1800160e5  mov     ecx, cs:dword_180044008
0x1800160eb  cmp     ecx, 2
0x1800160ee  jbe     short loc_180016161
0x1800160f0  lea     rax, aFailedToSendDe_0; "Failed to send delete surface event to "...
0x1800160f7  mov     [rbp+var_28], r14
0x1800160fb  mov     [rbp+var_20], rax
0x1800160ff  lea     rdx, byte_18003C76F
0x180016106  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x18001610d  mov     dword ptr [rbp+arg_0], 3E0h
0x180016114  mov     [rbp+var_18], rax
0x180016118  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001611f  mov     [rbp+var_10], rax
0x180016123  lea     rax, [rbp+var_20]
0x180016127  mov     [rsp+80h+var_38], rax
0x18001612c  lea     rax, [rbp+var_28]
0x180016130  mov     [rsp+80h+var_40], rax
0x180016135  lea     rax, [rbp+arg_0]
0x180016139  mov     [rsp+80h+var_48], rax
0x18001613e  lea     rax, [rbp+var_18]
0x180016142  mov     [rsp+80h+var_50], rax
0x180016147  lea     rax, [rbp+arg_18]
0x18001614b  mov     [rsp+80h+var_58], rax
0x180016150  lea     rax, [rbp+var_10]
0x180016154  mov     [rsp+80h+var_60], rax
0x180016159  mov     dword ptr [rbp+arg_18], ebx
0x18001615c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180016161  lea     rcx, [rbp+var_30]
0x180016165  call    ?SafeRelease@?$TCntPtr@VDirtySurface@RdpRemoteAppGfxRedirectionHandler@@@@AEAAXXZ; TCntPtr<RdpRemoteAppGfxRedirectionHandler::DirtySurface>::SafeRelease(void)
0x18001616a  lea     r11, [rsp+80h+var_s0]
0x180016172  mov     eax, ebx
0x180016174  mov     rbx, [r11+28h]
0x180016178  mov     rsi, [r11+30h]
0x18001617c  mov     rsp, r11
0x18001617f  pop     r14
0x180016181  pop     rdi
0x180016182  pop     rbp
0x180016183  retn
```
