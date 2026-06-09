# RdpRemoteAppGfxRedirectionHandler::Initialize(_GUID)

- ea: `0x1800141d0`
- end: `0x1800144c2`
- name: `?Initialize@RdpRemoteAppGfxRedirectionHandler@@IEAAJU_GUID@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectionHandler *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180013444`

## callees

- `0x18000160c`
- `0x180001724`
- `0x180001f98`
- `0x1800138a8`
- `0x180014044`
- `0x1800141d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800142a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014359`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800142a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180014359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001436b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001436b`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800143fe`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800143fe`

## string_xrefs

- `0x18001430a`: `Failed to create graphics update event`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectionHandler::Initialize(
        RdpRemoteAppGfxRedirectionHandler *this,
        struct _GUID *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  unsigned int v7; // ebx
  HANDLE EventW; // rax
  signed int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int16 *v13; // rdx
  const char *v14; // rax
  HANDLE v15; // rax
  signed int LastError; // eax
  int v17; // eax
  __int64 v18; // r8
  __int64 v19; // r9
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  const unsigned __int16 *v23[2]; // [rsp+60h] [rbp-10h] BYREF
  int v24; // [rsp+90h] [rbp+20h] BYREF
  int v25; // [rsp+A0h] [rbp+30h] BYREF
  const char *v26; // [rsp+A8h] [rbp+38h] BYREF

  v24 = 0;
  if ( !(unsigned int)CTSCriticalSection::Initialize((RdpRemoteAppGfxRedirectionHandler *)((char *)this + 64)) )
  {
    v7 = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v24 = 243;
      v26 = "CTSCriticalSection::Initialize failed!";
      v25 = -2147467259;
      v21 = "Initialize";
      v22 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v23[0] = (const unsigned __int16 *)"Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v4,
        (__int64)&dword_18003D664,
        v5,
        v6,
        v23,
        (__int64)&v25,
        (const unsigned __int16 **)&v22,
        (__int64)&v24,
        (const unsigned __int16 **)&v21,
        (const unsigned __int16 **)&v26);
    }
    return v7;
  }
  *(struct _GUID *)((char *)this + 168) = *a2;
  EventW = CreateEventW(0, 0, 1, 0);
  *((_QWORD *)this + 19) = EventW;
  if ( EventW )
  {
    v15 = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 20) = v15;
    if ( v15 )
    {
      v17 = RtlSubscribeWnfStateChangeNotification(
              (char *)this + 184,
              WNF_DX_VAIL_CHANGE_NOTIFICATION,
              0,
              RdpRemoteAppGfxRedirectionHandler::NotifyVailStateChangeCallback,
              this,
              0,
              0,
              0);
      if ( v17 >= 0 )
      {
        *((_DWORD *)this + 37) = 0;
        if ( (int)RdpRemoteAppGfxRedirectionHandler::GetChannelRegistrySetting(&v24) >= 0 && !v24 )
          *((_DWORD *)this + 37) = 1;
        return 0;
      }
      else
      {
        v7 = v17 | 0x10000000;
        if ( (unsigned int)dword_180044008 > 2 )
        {
          v24 = v17;
          v25 = 263;
          v23[0] = (const unsigned __int16 *)"Initialize";
          v22 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
          v21 = "RtlSubscribeWnfStateChangeNotification failed! Error: %!STATUS!";
          LODWORD(v26) = v17 | 0x10000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)dword_180044008,
            (__int64)&word_18003D54E,
            v18,
            v19,
            (const unsigned __int16 **)&v21,
            (__int64)&v26,
            (const unsigned __int16 **)&v22,
            (__int64)&v25,
            v23,
            (__int64)&v24);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      v7 = LastError;
      if ( (unsigned int)dword_180044008 > 2 )
      {
        v24 = 253;
        v26 = "Initialize";
        v13 = (__int16 *)&unk_18003D5B0;
        v23[0] = (const unsigned __int16 *)"clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
        v14 = "Failed to session disconnect event";
        goto LABEL_11;
      }
    }
  }
  else
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2147467259;
    v7 = v9;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v24 = 249;
      v26 = "Initialize";
      v13 = word_18003D60A;
      v23[0] = (const unsigned __int16 *)"clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v14 = "Failed to create graphics update event";
LABEL_11:
      v22 = v14;
      v25 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v10,
        (__int64)v13,
        v11,
        v12,
        (const unsigned __int16 **)&v22,
        (__int64)&v25,
        v23,
        (__int64)&v24,
        (const unsigned __int16 **)&v26);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800141d0  push    rbp
0x1800141d2  push    rbx
0x1800141d3  push    rdi
0x1800141d4  mov     rbp, rsp
0x1800141d7  sub     rsp, 70h
0x1800141db  mov     rbx, rcx
0x1800141de  mov     [rbp+arg_0], 0
0x1800141e5  add     rcx, 40h ; '@'; this
0x1800141e9  mov     rdi, rdx
0x1800141ec  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x1800141f1  test    eax, eax
0x1800141f3  jnz     loc_18001428A
0x1800141f9  mov     eax, cs:dword_180044008
0x1800141ff  mov     ebx, 80004005h
0x180014204  cmp     eax, 2
0x180014207  jbe     loc_1800144B8
0x18001420d  lea     rax, aCtscriticalsec; "CTSCriticalSection::Initialize failed!"
0x180014214  mov     [rbp+arg_0], 0F3h
0x18001421b  mov     [rbp+arg_18], rax
0x18001421f  lea     rdx, dword_18003D664
0x180014226  lea     rax, aInitialize; "Initialize"
0x18001422d  mov     [rbp+arg_10], ebx
0x180014230  mov     [rbp+var_20], rax
0x180014234  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x18001423b  mov     [rbp+var_18], rax
0x18001423f  lea     rax, aErrorCondition; "Error condition failed"
0x180014246  mov     [rbp+var_10], rax
0x18001424a  lea     rax, [rbp+arg_18]
0x18001424e  mov     [rsp+70h+var_28], rax
0x180014253  lea     rax, [rbp+var_20]
0x180014257  mov     [rsp+70h+var_30], rax
0x18001425c  lea     rax, [rbp+arg_0]
0x180014260  mov     [rsp+70h+var_38], rax
0x180014265  lea     rax, [rbp+var_18]
0x180014269  mov     [rsp+70h+var_40], rax
0x18001426e  lea     rax, [rbp+arg_10]
0x180014272  mov     [rsp+70h+var_48], rax
0x180014277  lea     rax, [rbp+var_10]
0x18001427b  mov     [rsp+70h+var_50], rax
0x180014280  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180014285  jmp     loc_1800144B8
0x18001428a  movups  xmm0, xmmword ptr [rdi]
0x18001428d  xor     r9d, r9d; lpName
0x180014290  xor     edx, edx; bManualReset
0x180014292  xor     ecx, ecx; lpEventAttributes
0x180014294  movdqu  xmmword ptr [rbx+0A8h], xmm0
0x18001429c  lea     edi, [r9+1]
0x1800142a0  mov     r8d, edi; bInitialState
0x1800142a3  call    cs:__imp_CreateEventW
0x1800142a9  mov     [rbx+98h], rax
0x1800142b0  test    rax, rax
0x1800142b3  jnz     loc_18001434F
0x1800142b9  call    cs:__imp_GetLastError
0x1800142bf  test    eax, eax
0x1800142c1  jle     short loc_1800142CB
0x1800142c3  movzx   eax, ax
0x1800142c6  or      eax, 80070000h
0x1800142cb  test    eax, eax
0x1800142cd  mov     ebx, 80004005h
0x1800142d2  cmovns  eax, ebx
0x1800142d5  mov     ebx, eax
0x1800142d7  mov     eax, cs:dword_180044008
0x1800142dd  cmp     eax, 2
0x1800142e0  jbe     loc_1800144B8
0x1800142e6  lea     rax, aInitialize; "Initialize"
0x1800142ed  mov     [rbp+arg_0], 0F9h
0x1800142f4  mov     [rbp+arg_18], rax
0x1800142f8  lea     rdx, word_18003D60A
0x1800142ff  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014306  mov     [rbp+var_10], rax
0x18001430a  lea     rax, aFailedToCreate_2; "Failed to create graphics update event"
0x180014311  mov     [rbp+var_18], rax
0x180014315  lea     rax, [rbp+arg_18]
0x180014319  mov     [rsp+70h+var_30], rax
0x18001431e  lea     rax, [rbp+arg_0]
0x180014322  mov     [rsp+70h+var_38], rax
0x180014327  lea     rax, [rbp+var_10]
0x18001432b  mov     [rsp+70h+var_40], rax
0x180014330  lea     rax, [rbp+arg_10]
0x180014334  mov     [rsp+70h+var_48], rax
0x180014339  lea     rax, [rbp+var_18]
0x18001433d  mov     [rsp+70h+var_50], rax
0x180014342  mov     [rbp+arg_10], ebx
0x180014345  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001434a  jmp     loc_1800144B8
0x18001434f  xor     r9d, r9d; lpName
0x180014352  xor     r8d, r8d; bInitialState
0x180014355  mov     edx, edi; bManualReset
0x180014357  xor     ecx, ecx; lpEventAttributes
0x180014359  call    cs:__imp_CreateEventW
0x18001435f  mov     [rbx+0A0h], rax
0x180014366  test    rax, rax
0x180014369  jnz     short loc_1800143C8
0x18001436b  call    cs:__imp_GetLastError
0x180014371  test    eax, eax
0x180014373  jle     short loc_18001437D
0x180014375  movzx   eax, ax
0x180014378  or      eax, 80070000h
0x18001437d  test    eax, eax
0x18001437f  mov     ebx, 80004005h
0x180014384  cmovns  eax, ebx
0x180014387  mov     ebx, eax
0x180014389  mov     eax, cs:dword_180044008
0x18001438f  cmp     eax, 2
0x180014392  jbe     loc_1800144B8
0x180014398  lea     rax, aInitialize; "Initialize"
0x18001439f  mov     [rbp+arg_0], 0FDh
0x1800143a6  mov     [rbp+arg_18], rax
0x1800143aa  lea     rdx, unk_18003D5B0
0x1800143b1  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x1800143b8  mov     [rbp+var_10], rax
0x1800143bc  lea     rax, aFailedToSessio; "Failed to session disconnect event"
0x1800143c3  jmp     loc_180014311
0x1800143c8  mov     rdx, cs:WNF_DX_VAIL_CHANGE_NOTIFICATION
0x1800143cf  lea     rcx, [rbx+0B8h]
0x1800143d6  mov     dword ptr [rsp+70h+var_38], 0
0x1800143de  lea     r9, ?NotifyVailStateChangeCallback@RdpRemoteAppGfxRedirectionHandler@@SAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; RdpRemoteAppGfxRedirectionHandler::NotifyVailStateChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800143e5  mov     dword ptr [rsp+70h+var_40], 0
0x1800143ed  xor     r8d, r8d
0x1800143f0  mov     [rsp+70h+var_48], 0
0x1800143f9  mov     [rsp+70h+var_50], rbx
0x1800143fe  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180014404  test    eax, eax
0x180014406  jns     loc_180014493
0x18001440c  mov     ecx, cs:dword_180044008
0x180014412  mov     ebx, eax
0x180014414  bts     ebx, 1Ch
0x180014418  cmp     ecx, 2
0x18001441b  jbe     loc_1800144B8
0x180014421  mov     [rbp+arg_0], eax
0x180014424  lea     rdx, word_18003D54E
0x18001442b  lea     rax, aInitialize; "Initialize"
0x180014432  mov     [rbp+arg_10], 107h
0x180014439  mov     [rbp+var_10], rax
0x18001443d  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014444  mov     [rbp+var_18], rax
0x180014448  lea     rax, aRtlsubscribewn; "RtlSubscribeWnfStateChangeNotification "...
0x18001444f  mov     [rbp+var_20], rax
0x180014453  lea     rax, [rbp+arg_0]
0x180014457  mov     [rsp+70h+var_28], rax
0x18001445c  lea     rax, [rbp+var_10]
0x180014460  mov     [rsp+70h+var_30], rax
0x180014465  lea     rax, [rbp+arg_10]
0x180014469  mov     [rsp+70h+var_38], rax
0x18001446e  lea     rax, [rbp+var_18]
0x180014472  mov     [rsp+70h+var_40], rax
0x180014477  lea     rax, [rbp+arg_18]
0x18001447b  mov     [rsp+70h+var_48], rax
0x180014480  lea     rax, [rbp+var_20]
0x180014484  mov     [rsp+70h+var_50], rax
0x180014489  mov     dword ptr [rbp+arg_18], ebx
0x18001448c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180014491  jmp     short loc_1800144B8
0x180014493  lea     rcx, [rbp+arg_0]; int *
0x180014497  mov     dword ptr [rbx+94h], 0
0x1800144a1  call    ?GetChannelRegistrySetting@RdpRemoteAppGfxRedirectionHandler@@SAJPEAH@Z; RdpRemoteAppGfxRedirectionHandler::GetChannelRegistrySetting(int *)
0x1800144a6  test    eax, eax
0x1800144a8  js      short loc_1800144B6
0x1800144aa  cmp     [rbp+arg_0], 0
0x1800144ae  jnz     short loc_1800144B6
0x1800144b0  mov     [rbx+94h], edi
0x1800144b6  xor     ebx, ebx
0x1800144b8  mov     eax, ebx
0x1800144ba  add     rsp, 70h
0x1800144be  pop     rdi
0x1800144bf  pop     rbx
0x1800144c0  pop     rbp
0x1800144c1  retn
```
