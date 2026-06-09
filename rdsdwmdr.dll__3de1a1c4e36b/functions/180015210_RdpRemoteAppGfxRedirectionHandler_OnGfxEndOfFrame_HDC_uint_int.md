# RdpRemoteAppGfxRedirectionHandler::OnGfxEndOfFrame(HDC__ *,uint,int)

- ea: `0x180015210`
- end: `0x1800154e0`
- name: `?OnGfxEndOfFrame@RdpRemoteAppGfxRedirectionHandler@@UEAAJPEAUHDC__@@IH@Z`
- size: `720`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *this, HDC, __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callees

- `0x1800010f8`
- `0x18000160c`
- `0x180001724`
- `0x180012e60`
- `0x180013850`
- `0x1800144c8`
- `0x180015210`
- `0x180016e64`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015338`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015346`

## string_xrefs

- `0x180015282`: `Channel not initialized. Dropping Surface Update PDUs`
- `0x180015314`: `Received frame markers with no surface update`
- `0x18001539b`: `Failed to signal graphics update event`
- `0x180015445`: `Failed to send graphics update to client`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::OnGfxEndOfFrame(
        RdpRemoteAppGfxRedirectionHandler *this,
        HDC a2,
        __int64 a3,
        __int64 a4)
{
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  signed int updated; // ebx
  signed int LastError; // eax
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  signed int v18; // [rsp+50h] [rbp+7h] BYREF
  __int64 v19; // [rsp+58h] [rbp+Fh] BYREF
  CTSCriticalSection *v20; // [rsp+60h] [rbp+17h] BYREF
  const char *v21; // [rsp+68h] [rbp+1Fh] BYREF
  const char *v22; // [rsp+70h] [rbp+27h] BYREF
  const char *v23; // [rsp+78h] [rbp+2Fh] BYREF
  const char *v24; // [rsp+80h] [rbp+37h] BYREF
  const char *v25; // [rsp+B0h] [rbp+67h] BYREF

  v19 = 0;
  if ( (unsigned int)dword_180044008 > 5 )
  {
    v25 = "OnGfxEndFrame";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (__int64)this,
      (__int64)&byte_18003CC3F,
      a3,
      a4,
      (const unsigned __int16 **)&v25);
  }
  v5 = RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized((RdpRemoteAppGfxRedirectionHandler *)((char *)this - 48));
  updated = v5;
  if ( v5 >= 0 )
  {
    if ( *((_DWORD *)this + 21) )
    {
      v20 = (RdpRemoteAppGfxRedirectionHandler *)((char *)this + 16);
      CTSCriticalSection::Lock((RdpRemoteAppGfxRedirectionHandler *)((char *)this + 16));
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 8) + 64LL))((char *)this + 64);
      while ( (*(unsigned int (__fastcall **)(char *, __int64 *))(*((_QWORD *)this + 8) + 72LL))(
                (char *)this + 64,
                &v19) )
      {
        updated = RdpRemoteAppGfxRedirectionHandler::SendGraphicsUpdatePdu(
                    (RdpRemoteAppGfxRedirectionHandler *)((char *)this - 48),
                    *(HWND *)(v19 + 56),
                    *(struct IRdpBoundsAccumulator **)(v19 + 48),
                    *((_QWORD *)this + 20));
        if ( updated < 0 )
        {
          if ( (unsigned int)dword_180044008 > 2 )
          {
            LODWORD(v25) = 851;
            v23 = "Failed to send graphics update to client";
            v18 = updated;
            v22 = "OnGfxEndOfFrame";
            v21 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
            v24 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v14,
              (__int64)byte_18003CAEB,
              v15,
              v16,
              (const unsigned __int16 **)&v24,
              (__int64)&v18,
              (const unsigned __int16 **)&v21,
              (__int64)&v25,
              (const unsigned __int16 **)&v22,
              (const unsigned __int16 **)&v23);
          }
          break;
        }
      }
      CTSAutoLock::~CTSAutoLock(&v20);
    }
    else
    {
      if ( (unsigned int)dword_180044008 > 3 )
      {
        v25 = "Received frame markers with no surface update";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v6,
          (__int64)&byte_18003CBA7,
          v7,
          v8,
          (const unsigned __int16 **)&v25);
      }
      if ( !SetEvent(*((HANDLE *)this + 13)) )
      {
        LastError = GetLastError();
        updated = LastError;
        if ( LastError > 0 )
          updated = (unsigned __int16)LastError | 0x80070000;
        if ( updated >= 0 )
          updated = -2147467259;
        if ( (unsigned int)dword_180044008 > 2 )
        {
          LODWORD(v25) = 830;
          v23 = "OnGfxEndOfFrame";
          v18 = updated;
          v22 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
          v21 = "Failed to signal graphics update event";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v11,
            (__int64)byte_18003CB4D,
            v12,
            v13,
            (const unsigned __int16 **)&v21,
            (__int64)&v18,
            (const unsigned __int16 **)&v22,
            (__int64)&v25,
            (const unsigned __int16 **)&v23);
        }
      }
    }
  }
  else if ( (unsigned int)dword_180044008 > 2 )
  {
    LODWORD(v25) = 819;
    v20 = (CTSCriticalSection *)"Channel not initialized. Dropping Surface Update PDUs";
    v18 = v5;
    v21 = "OnGfxEndOfFrame";
    v22 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
    v23 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)dword_180044008,
      (__int64)byte_18003CBDD,
      v7,
      v8,
      (const unsigned __int16 **)&v23,
      (__int64)&v18,
      (const unsigned __int16 **)&v22,
      (__int64)&v25,
      (const unsigned __int16 **)&v21,
      (const unsigned __int16 **)&v20);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180015210  mov     [rsp-8+arg_8], rbx
0x180015215  mov     [rsp-8+arg_10], rsi
0x18001521a  push    rbp
0x18001521b  push    rdi
0x18001521c  push    r14
0x18001521e  lea     rbp, [rsp-47h]
0x180015223  sub     rsp, 90h
0x18001522a  mov     eax, cs:dword_180044008
0x180015230  mov     rdi, rcx
0x180015233  mov     [rbp+57h+var_48], 0
0x18001523b  cmp     eax, 5
0x18001523e  jbe     short loc_180015260
0x180015240  lea     rax, aOngfxendframe; "OnGfxEndFrame"
0x180015247  mov     [rbp+57h+arg_0], rax
0x18001524b  lea     rdx, byte_18003CC3F
0x180015252  lea     rax, [rbp+57h+arg_0]
0x180015256  mov     [rsp+0A0h+var_80], rax
0x18001525b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180015260  lea     rcx, [rdi-30h]; this
0x180015264  call    ?EnsureChannelInitialized@RdpRemoteAppGfxRedirectionHandler@@IEAAJXZ; RdpRemoteAppGfxRedirectionHandler::EnsureChannelInitialized(void)
0x180015269  mov     ebx, eax
0x18001526b  test    eax, eax
0x18001526d  jns     loc_1800152FF
0x180015273  mov     ecx, cs:dword_180044008
0x180015279  cmp     ecx, 2
0x18001527c  jbe     loc_1800154C6
0x180015282  lea     rax, aChannelNotInit_0; "Channel not initialized. Dropping Surfa"...
0x180015289  mov     dword ptr [rbp+57h+arg_0], 333h
0x180015290  mov     [rbp+57h+var_40], rax
0x180015294  lea     rdx, byte_18003CBDD
0x18001529b  lea     rax, aOngfxendoffram; "OnGfxEndOfFrame"
0x1800152a2  mov     [rbp+57h+var_50], ebx
0x1800152a5  mov     [rbp+57h+var_38], rax
0x1800152a9  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800152b0  mov     [rbp+57h+var_30], rax
0x1800152b4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800152bb  mov     [rbp+57h+var_28], rax
0x1800152bf  lea     rax, [rbp+57h+var_40]
0x1800152c3  mov     [rsp+0A0h+var_58], rax
0x1800152c8  lea     rax, [rbp+57h+var_38]
0x1800152cc  mov     [rsp+0A0h+var_60], rax
0x1800152d1  lea     rax, [rbp+57h+arg_0]
0x1800152d5  mov     [rsp+0A0h+var_68], rax
0x1800152da  lea     rax, [rbp+57h+var_30]
0x1800152de  mov     [rsp+0A0h+var_70], rax
0x1800152e3  lea     rax, [rbp+57h+var_50]
0x1800152e7  mov     [rsp+0A0h+var_78], rax
0x1800152ec  lea     rax, [rbp+57h+var_28]
0x1800152f0  mov     [rsp+0A0h+var_80], rax
0x1800152f5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800152fa  jmp     loc_1800154C6
0x1800152ff  cmp     dword ptr [rdi+54h], 0
0x180015303  jnz     loc_1800153DD
0x180015309  mov     eax, cs:dword_180044008
0x18001530f  cmp     eax, 3
0x180015312  jbe     short loc_180015334
0x180015314  lea     rax, aReceivedFrameM; "Received frame markers with no surface "...
0x18001531b  mov     [rbp+57h+arg_0], rax
0x18001531f  lea     rdx, byte_18003CBA7
0x180015326  lea     rax, [rbp+57h+arg_0]
0x18001532a  mov     [rsp+0A0h+var_80], rax
0x18001532f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180015334  mov     rcx, [rdi+68h]; hEvent
0x180015338  call    cs:__imp_SetEvent
0x18001533e  test    eax, eax
0x180015340  jnz     loc_1800154C6
0x180015346  call    cs:__imp_GetLastError
0x18001534c  mov     ebx, eax
0x18001534e  test    eax, eax
0x180015350  jle     short loc_18001535B
0x180015352  movzx   ebx, ax
0x180015355  or      ebx, 80070000h
0x18001535b  test    ebx, ebx
0x18001535d  mov     eax, 80004005h
0x180015362  cmovns  ebx, eax
0x180015365  mov     eax, cs:dword_180044008
0x18001536b  cmp     eax, 2
0x18001536e  jbe     loc_1800154C6
0x180015374  lea     rax, aOngfxendoffram; "OnGfxEndOfFrame"
0x18001537b  mov     dword ptr [rbp+57h+arg_0], 33Eh
0x180015382  mov     [rbp+57h+var_28], rax
0x180015386  lea     rdx, byte_18003CB4D
0x18001538d  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015394  mov     [rbp+57h+var_50], ebx
0x180015397  mov     [rbp+57h+var_30], rax
0x18001539b  lea     rax, aFailedToSignal_1; "Failed to signal graphics update event"
0x1800153a2  mov     [rbp+57h+var_38], rax
0x1800153a6  lea     rax, [rbp+57h+var_28]
0x1800153aa  mov     [rsp+0A0h+var_60], rax
0x1800153af  lea     rax, [rbp+57h+arg_0]
0x1800153b3  mov     [rsp+0A0h+var_68], rax
0x1800153b8  lea     rax, [rbp+57h+var_30]
0x1800153bc  mov     [rsp+0A0h+var_70], rax
0x1800153c1  lea     rax, [rbp+57h+var_50]
0x1800153c5  mov     [rsp+0A0h+var_78], rax
0x1800153ca  lea     rax, [rbp+57h+var_38]
0x1800153ce  mov     [rsp+0A0h+var_80], rax
0x1800153d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800153d8  jmp     loc_1800154C6
0x1800153dd  lea     rcx, [rdi+10h]; this
0x1800153e1  mov     [rbp+57h+var_40], rcx
0x1800153e5  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800153ea  lea     r14, [rdi+40h]
0x1800153ee  mov     rax, [r14]
0x1800153f1  mov     rcx, r14
0x1800153f4  mov     rax, [rax+40h]
0x1800153f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153fd  mov     rax, [r14]
0x180015400  lea     rdx, [rbp+57h+var_48]
0x180015404  mov     rcx, r14
0x180015407  mov     rax, [rax+48h]
0x18001540b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015410  test    eax, eax
0x180015412  jz      loc_1800154BD
0x180015418  mov     rdx, [rbp+57h+var_48]
0x18001541c  lea     rcx, [rdi-30h]; this
0x180015420  mov     r9, [rdi+0A0h]; __int64
0x180015427  mov     r8, [rdx+30h]; struct IRdpBoundsAccumulator *
0x18001542b  mov     rdx, [rdx+38h]; HWND
0x18001542f  call    ?SendGraphicsUpdatePdu@RdpRemoteAppGfxRedirectionHandler@@IEAAJPEAUHWND__@@PEAVIRdpBoundsAccumulator@@_J@Z; RdpRemoteAppGfxRedirectionHandler::SendGraphicsUpdatePdu(HWND__ *,IRdpBoundsAccumulator *,__int64)
0x180015434  mov     ebx, eax
0x180015436  test    eax, eax
0x180015438  jns     short loc_1800153FD
0x18001543a  mov     eax, cs:dword_180044008
0x180015440  cmp     eax, 2
0x180015443  jbe     short loc_1800154BD
0x180015445  lea     rax, aFailedToSendGr; "Failed to send graphics update to clien"...
0x18001544c  mov     dword ptr [rbp+57h+arg_0], 353h
0x180015453  mov     [rbp+57h+var_28], rax
0x180015457  lea     rdx, byte_18003CAEB
0x18001545e  lea     rax, aOngfxendoffram; "OnGfxEndOfFrame"
0x180015465  mov     [rbp+57h+var_50], ebx
0x180015468  mov     [rbp+57h+var_30], rax
0x18001546c  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180015473  mov     [rbp+57h+var_38], rax
0x180015477  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001547e  mov     [rbp+57h+var_20], rax
0x180015482  lea     rax, [rbp+57h+var_28]
0x180015486  mov     [rsp+0A0h+var_58], rax
0x18001548b  lea     rax, [rbp+57h+var_30]
0x18001548f  mov     [rsp+0A0h+var_60], rax
0x180015494  lea     rax, [rbp+57h+arg_0]
0x180015498  mov     [rsp+0A0h+var_68], rax
0x18001549d  lea     rax, [rbp+57h+var_38]
0x1800154a1  mov     [rsp+0A0h+var_70], rax
0x1800154a6  lea     rax, [rbp+57h+var_50]
0x1800154aa  mov     [rsp+0A0h+var_78], rax
0x1800154af  lea     rax, [rbp+57h+var_20]
0x1800154b3  mov     [rsp+0A0h+var_80], rax
0x1800154b8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800154bd  lea     rcx, [rbp+57h+var_40]; this
0x1800154c1  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x1800154c6  lea     r11, [rsp+0A0h+var_10]
0x1800154ce  mov     eax, ebx
0x1800154d0  mov     rbx, [r11+28h]
0x1800154d4  mov     rsi, [r11+30h]
0x1800154d8  mov     rsp, r11
0x1800154db  pop     r14
0x1800154dd  pop     rdi
0x1800154de  pop     rbp
0x1800154df  retn
```
