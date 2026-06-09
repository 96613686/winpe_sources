# RdpDisplayControlHandler::OnSessionConnect(void)

- ea: `0x14000fe28`
- end: `0x1400103e1`
- name: `?OnSessionConnect@RdpDisplayControlHandler@@QEAAJXZ`
- size: `1465`
- prototype: `__int64 __fastcall(RdpDisplayControlHandler *__hidden this)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140004fb0`
- `0x140015c20`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x140005f74`
- `0x14000e544`
- `0x14000fe28`
- `0x140010588`
- `0x14001096c`
- `0x140010998`
- `0x140011054`
- `0x140020930`
- `0x140025ffc`
- `0x14003035c`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `USER32!EnumDisplayDevicesW` at `0x140010301`
- `USER32!EnumDisplayDevicesW` at `0x140010301`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001012f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010171`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001012f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010171`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14001033b`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x14001033b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400100ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400100ff`
- `WINSTA!WinStationFreePropertyValue` at `0x1400100b2`
- `WINSTA!WinStationFreePropertyValue` at `0x1400100b2`
- `WINSTA!WinStationGetConnectionProperty` at `0x140010093`
- `WINSTA!WinStationGetConnectionProperty` at `0x140010093`

## string_xrefs

- `0x14000ffe4`: `CreateServerSideVCManager failed!`
- `0x140010069`: `IServerVCChannelManager::OpenDynamicChannel failed!`
- `0x140010146`: `m_hMonitorLayoutChangeCompletedEvent`
- `0x14001022c`: `CTimedCallback::CreateInstance failed!`
- `0x140010290`: `CreateThread failed!`
- `0x1400102e1`: `StartThread failed!`

## pseudocode

```c
__int64 __fastcall RdpDisplayControlHandler::OnSessionConnect(RdpDisplayControlHandler *this)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v3; // edx
  const char *v4; // rcx
  signed int ServerSideVCManager; // edi
  unsigned int v6; // eax
  int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // eax
  int v10; // edx
  const char *v11; // rcx
  unsigned int v12; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  signed int v17; // eax
  WCHAR *DeviceString; // rbx
  const unsigned __int16 *v19; // rdx
  __int64 v21; // [rsp+28h] [rbp-3D0h]
  __int64 v22; // [rsp+40h] [rbp-3B8h] BYREF
  GUID ActivityId; // [rsp+48h] [rbp-3B0h] BYREF
  struct _DISPLAY_DEVICEW DisplayDevice; // [rsp+60h] [rbp-398h] BYREF

  v22 = 0;
  memset_0(&DisplayDevice, 0, sizeof(DisplayDevice));
  if ( !*((_QWORD *)this + 12) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v3 = 21;
    v4 = "m_spPlatform";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      (unsigned int)&WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v4);
LABEL_7:
    ServerSideVCManager = -2147467261;
LABEL_79:
    RdpDisplayControlHandler::DestroyDisplayControlObjects(this);
    return (unsigned int)ServerSideVCManager;
  }
  if ( !*((_QWORD *)this + 13) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v3 = 22;
    v4 = "m_spCoreEvents";
    goto LABEL_6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v6 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids, v6);
  }
  v7 = RdpDisplayControlHandler::DestroyDisplayControlObjects(this);
  if ( v7 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)&WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
      v8,
      (__int64)"DestroyDisplayControlObjects failed",
      v7);
  }
  ServerSideVCManager = CreateServerSideVCManager((struct IServerVCChannelManager **)this + 22);
  if ( ServerSideVCManager < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_79;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 25;
    v11 = "CreateServerSideVCManager failed!";
    goto LABEL_78;
  }
  ServerSideVCManager = (*(__int64 (__fastcall **)(_QWORD, const char *, __int64, _QWORD, int, unsigned __int64, char *))(**((_QWORD **)this + 22) + 32LL))(
                          *((_QWORD *)this + 22),
                          "Microsoft::Windows::RDS::DisplayControl",
                          0xFFFFFFFFLL,
                          0,
                          1,
                          ((unsigned __int64)this + 48) & -(__int64)(this != 0),
                          (char *)this + 136);
  if ( ServerSideVCManager < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_79;
    }
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 26;
    v11 = "IServerVCChannelManager::OpenDynamicChannel failed!";
    goto LABEL_78;
  }
  *((_OWORD *)this + 15) = 0;
  if ( (unsigned __int8)WinStationGetConnectionProperty(0xFFFFFFFFLL, PROPERTY_TYPE_CORRELATIONID_GUID, &v22) )
  {
    if ( *(_WORD *)v22 == 4 )
      *((_OWORD *)this + 15) = *(_OWORD *)(v22 + 8);
    WinStationFreePropertyValue();
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_a707b627246d345b17349f1c0bcffaca_Traceguids, v12);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 21) = EventW;
  if ( EventW )
  {
    ServerSideVCManager = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(**((_QWORD **)this + 13) + 56LL))(
                            *((_QWORD *)this + 13),
                            192,
                            (char *)this + 144);
    if ( ServerSideVCManager >= 0 )
    {
      ServerSideVCManager = CTimedCallback::CreateInstance((struct CTimedCallback **)this + 19);
      if ( ServerSideVCManager >= 0 )
      {
        ServerSideVCManager = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(void *), RdpDisplayControlHandler *, char *))(**((_QWORD **)this + 12) + 56LL))(
                                *((_QWORD *)this + 12),
                                RdpDisplayControlHandler::StaticDisplayControlProcessThreadMain,
                                this,
                                (char *)this + 160);
        if ( ServerSideVCManager >= 0 )
        {
          ServerSideVCManager = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 20) + 32LL))(
                                  *((_QWORD *)this + 20),
                                  0);
          if ( ServerSideVCManager >= 0 )
          {
            DisplayDevice.cb = 840;
            DeviceString = DisplayDevice.DeviceString;
            if ( !EnumDisplayDevicesW(0, 0, &DisplayDevice, 0) )
              DeviceString = L"unknown";
            CAutoSetThreadActivityId::CAutoSetThreadActivityId(&ActivityId, (const struct _GUID *)this + 15);
            RDPGraphicsTraceLogging::LogRDPGraphicsAdapter((RDPGraphicsTraceLogging *)DeviceString, v19);
            EventActivityIdControl(2u, &ActivityId);
            ServerSideVCManager = RdpDisplayControlHandler::SendCaps(this);
            if ( ServerSideVCManager >= 0 )
            {
              CTSReaderWriterLock::WriteLock((RdpDisplayControlHandler *)((char *)this + 112));
              *((_DWORD *)this + 32) = 1;
              CTSReaderWriterLock::WriteUnlock((RdpDisplayControlHandler *)((char *)this + 112));
              return (unsigned int)ServerSideVCManager;
            }
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_79;
            }
            v9 = RdpWppGetCurrentThreadActivityIdPrefix();
            v10 = 33;
            v11 = "SendCaps failed!";
          }
          else
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_79;
            }
            v9 = RdpWppGetCurrentThreadActivityIdPrefix();
            v10 = 32;
            v11 = "StartThread failed!";
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_79;
          }
          v9 = RdpWppGetCurrentThreadActivityIdPrefix();
          v10 = 31;
          v11 = "CreateThread failed!";
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_79;
        }
        v9 = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = 30;
        v11 = "CTimedCallback::CreateInstance failed!";
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_79;
      }
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      v10 = 29;
      v11 = "RegisterNotificationSource (DISPLAYCONTROL_EVENT_MONITOR_LAYOUT_CHANGE_REQUESTED) failed!";
    }
LABEL_78:
    LODWORD(v21) = ServerSideVCManager;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)&WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
      v9,
      (__int64)v11,
      v21);
    goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(v21) = v15;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned int)&WPP_a707b627246d345b17349f1c0bcffaca_Traceguids,
      v16,
      (__int64)"m_hMonitorLayoutChangeCompletedEvent",
      v21);
  }
  v17 = GetLastError();
  ServerSideVCManager = v17;
  if ( v17 > 0 )
    ServerSideVCManager = (unsigned __int16)v17 | 0x80070000;
  if ( ServerSideVCManager < 0 )
    goto LABEL_79;
  return (unsigned int)ServerSideVCManager;
}

```

## disassembly

```asm
0x14000fe28  push    rbx
0x14000fe2a  push    rsi
0x14000fe2b  push    rdi
0x14000fe2c  push    r12
0x14000fe2e  push    r14
0x14000fe30  push    r15
0x14000fe32  sub     rsp, 3C8h
0x14000fe39  mov     rax, cs:__security_cookie
0x14000fe40  xor     rax, rsp
0x14000fe43  mov     [rsp+3F8h+var_48], rax
0x14000fe4b  mov     r15, rcx
0x14000fe4e  mov     [rsp+3F8h+var_3B8], 0
0x14000fe57  lea     rcx, [rsp+3F8h+DisplayDevice]; void *
0x14000fe5c  xor     edx, edx; Val
0x14000fe5e  mov     r8d, 348h; Size
0x14000fe64  call    memset_0
0x14000fe69  cmp     qword ptr [r15+60h], 0
0x14000fe6e  jnz     short loc_14000FEC9
0x14000fe70  mov     rax, cs:WPP_GLOBAL_Control
0x14000fe77  lea     rsi, WPP_GLOBAL_Control
0x14000fe7e  cmp     rax, rsi
0x14000fe81  jz      short loc_14000FEBF
0x14000fe83  test    byte ptr [rax+1Ch], 8
0x14000fe87  jz      short loc_14000FEBF
0x14000fe89  cmp     byte ptr [rax+19h], 2
0x14000fe8d  jb      short loc_14000FEBF
0x14000fe8f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000fe94  mov     edx, 15h
0x14000fe99  lea     rcx, aMSpplatform; "m_spPlatform"
0x14000fea0  mov     [rsp+3F8h+var_3D8], rcx
0x14000fea5  lea     r8, WPP_a707b627246d345b17349f1c0bcffaca_Traceguids
0x14000feac  mov     rcx, cs:WPP_GLOBAL_Control
0x14000feb3  mov     r9d, eax
0x14000feb6  mov     rcx, [rcx+10h]
0x14000feba  call    WPP_SF_Ds
0x14000febf  mov     edi, 80004003h
0x14000fec4  jmp     loc_140010397
0x14000fec9  cmp     qword ptr [r15+68h], 0
0x14000fece  jnz     short loc_14000FF02
0x14000fed0  mov     rax, cs:WPP_GLOBAL_Control
0x14000fed7  lea     rsi, WPP_GLOBAL_Control
0x14000fede  cmp     rax, rsi
0x14000fee1  jz      short loc_14000FEBF
0x14000fee3  test    byte ptr [rax+1Ch], 8
0x14000fee7  jz      short loc_14000FEBF
0x14000fee9  cmp     byte ptr [rax+19h], 2
0x14000feed  jb      short loc_14000FEBF
0x14000feef  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000fef4  mov     edx, 16h
0x14000fef9  lea     rcx, aMSpcoreevents; "m_spCoreEvents"
0x14000ff00  jmp     short loc_14000FEA0
0x14000ff02  mov     rax, cs:WPP_GLOBAL_Control
0x14000ff09  lea     rsi, WPP_GLOBAL_Control
0x14000ff10  lea     r14, WPP_a707b627246d345b17349f1c0bcffaca_Traceguids
0x14000ff17  cmp     rax, rsi
0x14000ff1a  jz      short loc_14000FF4B
0x14000ff1c  test    dword ptr [rax+1Ch], 100h
0x14000ff23  jz      short loc_14000FF4B
0x14000ff25  cmp     byte ptr [rax+19h], 4
0x14000ff29  jb      short loc_14000FF4B
0x14000ff2b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000ff30  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff37  mov     edx, 17h
0x14000ff3c  mov     r9d, eax
0x14000ff3f  mov     r8, r14
0x14000ff42  mov     rcx, [rcx+10h]
0x14000ff46  call    WPP_SF_d
0x14000ff4b  mov     rcx, r15; this
0x14000ff4e  call    ?DestroyDisplayControlObjects@RdpDisplayControlHandler@@AEAAJXZ; RdpDisplayControlHandler::DestroyDisplayControlObjects(void)
0x14000ff53  mov     ebx, eax
0x14000ff55  test    eax, eax
0x14000ff57  jns     short loc_14000FFA1
0x14000ff59  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff60  cmp     rcx, rsi
0x14000ff63  jz      short loc_14000FFA1
0x14000ff65  test    byte ptr [rcx+1Ch], 8
0x14000ff69  jz      short loc_14000FFA1
0x14000ff6b  cmp     byte ptr [rcx+19h], 2
0x14000ff6f  jb      short loc_14000FFA1
0x14000ff71  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000ff76  lea     rcx, aDestroydisplay; "DestroyDisplayControlObjects failed"
0x14000ff7d  mov     dword ptr [rsp+3F8h+var_3D0], ebx
0x14000ff81  mov     [rsp+3F8h+var_3D8], rcx
0x14000ff86  mov     edx, 18h
0x14000ff8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff92  mov     r9d, eax
0x14000ff95  mov     r8, r14
0x14000ff98  mov     rcx, [rcx+10h]
0x14000ff9c  call    WPP_SF_DsD
0x14000ffa1  lea     rbx, [r15+0B0h]
0x14000ffa8  mov     rcx, rbx; struct IServerVCChannelManager **
0x14000ffab  call    ?CreateServerSideVCManager@@YAJPEAPEAUIServerVCChannelManager@@@Z; CreateServerSideVCManager(IServerVCChannelManager * *)
0x14000ffb0  mov     edi, eax
0x14000ffb2  test    eax, eax
0x14000ffb4  jns     short loc_14000FFF0
0x14000ffb6  mov     rax, cs:WPP_GLOBAL_Control
0x14000ffbd  cmp     rax, rsi
0x14000ffc0  jz      loc_140010397
0x14000ffc6  test    byte ptr [rax+1Ch], 8
0x14000ffca  jz      loc_140010397
0x14000ffd0  cmp     byte ptr [rax+19h], 2
0x14000ffd4  jb      loc_140010397
0x14000ffda  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000ffdf  mov     edx, 19h
0x14000ffe4  lea     rcx, aCreateserversi; "CreateServerSideVCManager failed!"
0x14000ffeb  jmp     loc_140010378
0x14000fff0  mov     rcx, [rbx]
0x14000fff3  lea     rdx, [r15+30h]
0x14000fff7  lea     r10, [r15+88h]
0x14000fffe  mov     rax, r15
0x140010001  neg     rax
0x140010004  mov     [rsp+3F8h+var_3C8], r10
0x140010009  mov     ebx, 1
0x14001000e  mov     r9, [rcx]
0x140010011  sbb     r8, r8
0x140010014  and     r8, rdx
0x140010017  lea     rdx, aMicrosoftWindo_3; "Microsoft::Windows::RDS::DisplayControl"
0x14001001e  mov     [rsp+3F8h+var_3D0], r8
0x140010023  or      r8d, 0FFFFFFFFh
0x140010027  mov     dword ptr [rsp+3F8h+var_3D8], ebx
0x14001002b  mov     rax, [r9+20h]
0x14001002f  xor     r9d, r9d
0x140010032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010037  mov     edi, eax
0x140010039  test    eax, eax
0x14001003b  jns     short loc_140010075
0x14001003d  mov     rax, cs:WPP_GLOBAL_Control
0x140010044  cmp     rax, rsi
0x140010047  jz      loc_140010397
0x14001004d  test    byte ptr [rax+1Ch], 8
0x140010051  jz      loc_140010397
0x140010057  cmp     byte ptr [rax+19h], 2
0x14001005b  jb      loc_140010397
0x140010061  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140010066  lea     edx, [rbx+19h]
0x140010069  lea     rcx, aIservervcchann; "IServerVCChannelManager::OpenDynamicCha"...
0x140010070  jmp     loc_140010378
0x140010075  xorps   xmm0, xmm0
0x140010078  lea     r12, [r15+0F0h]
0x14001007f  lea     r8, [rsp+3F8h+var_3B8]
0x140010084  or      ecx, 0FFFFFFFFh
0x140010087  lea     rdx, PROPERTY_TYPE_CORRELATIONID_GUID
0x14001008e  movups  xmmword ptr [r12], xmm0
0x140010093  call    cs:__imp_WinStationGetConnectionProperty
0x140010099  test    al, al
0x14001009b  jz      short loc_1400100BA
0x14001009d  mov     rcx, [rsp+3F8h+var_3B8]
0x1400100a2  cmp     word ptr [rcx], 4
0x1400100a6  jnz     short loc_1400100B2
0x1400100a8  movups  xmm0, xmmword ptr [rcx+8]
0x1400100ac  movdqu  xmmword ptr [r12], xmm0
0x1400100b2  call    cs:__imp_WinStationFreePropertyValue
0x1400100b8  jmp     short loc_1400100F5
0x1400100ba  mov     rax, cs:WPP_GLOBAL_Control
0x1400100c1  cmp     rax, rsi
0x1400100c4  jz      short loc_1400100F5
0x1400100c6  test    dword ptr [rax+1Ch], 100h
0x1400100cd  jz      short loc_1400100F5
0x1400100cf  cmp     byte ptr [rax+19h], 2
0x1400100d3  jb      short loc_1400100F5
0x1400100d5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400100da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400100e1  mov     edx, 1Bh
0x1400100e6  mov     r9d, eax
0x1400100e9  mov     r8, r14
0x1400100ec  mov     rcx, [rcx+10h]
0x1400100f0  call    WPP_SF_d
0x1400100f5  xor     r9d, r9d; lpName
0x1400100f8  xor     r8d, r8d; bInitialState
0x1400100fb  mov     edx, ebx; bManualReset
0x1400100fd  xor     ecx, ecx; lpEventAttributes
0x1400100ff  call    cs:__imp_CreateEventW
0x140010105  mov     [r15+0A8h], rax
0x14001010c  test    rax, rax
0x14001010f  jnz     short loc_140010190
0x140010111  mov     rax, cs:WPP_GLOBAL_Control
0x140010118  mov     r12d, 80070000h
0x14001011e  cmp     rax, rsi
0x140010121  jz      short loc_140010171
0x140010123  test    byte ptr [rax+1Ch], 8
0x140010127  jz      short loc_140010171
0x140010129  cmp     byte ptr [rax+19h], 2
0x14001012d  jb      short loc_140010171
0x14001012f  call    cs:__imp_GetLastError
0x140010135  mov     ebx, eax
0x140010137  test    eax, eax
0x140010139  jle     short loc_140010141
0x14001013b  movzx   ebx, ax
0x14001013e  or      ebx, r12d
0x140010141  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140010146  lea     rcx, aMHmonitorlayou; "m_hMonitorLayoutChangeCompletedEvent"
0x14001014d  mov     dword ptr [rsp+3F8h+var_3D0], ebx
0x140010151  mov     [rsp+3F8h+var_3D8], rcx
0x140010156  mov     edx, 1Ch
0x14001015b  mov     rcx, cs:WPP_GLOBAL_Control
0x140010162  mov     r9d, eax
0x140010165  mov     r8, r14
0x140010168  mov     rcx, [rcx+10h]
0x14001016c  call    WPP_SF_DsD
0x140010171  call    cs:__imp_GetLastError
0x140010177  mov     edi, eax
0x140010179  test    eax, eax
0x14001017b  jle     short loc_140010183
0x14001017d  movzx   edi, ax
0x140010180  or      edi, r12d
0x140010183  test    edi, edi
0x140010185  jns     loc_1400103BE
0x14001018b  jmp     loc_140010397
0x140010190  mov     rcx, [r15+68h]
0x140010194  lea     r8, [r15+90h]
0x14001019b  mov     edx, 0C0h
0x1400101a0  mov     rax, [rcx]
0x1400101a3  mov     rax, [rax+38h]
0x1400101a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400101ac  mov     edi, eax
0x1400101ae  test    eax, eax
0x1400101b0  jns     short loc_1400101EC
0x1400101b2  mov     rax, cs:WPP_GLOBAL_Control
0x1400101b9  cmp     rax, rsi
0x1400101bc  jz      loc_140010397
0x1400101c2  test    byte ptr [rax+1Ch], 8
0x1400101c6  jz      loc_140010397
0x1400101cc  cmp     byte ptr [rax+19h], 2
0x1400101d0  jb      loc_140010397
0x1400101d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400101db  mov     edx, 1Dh
0x1400101e0  lea     rcx, aRegisternotifi_0; "RegisterNotificationSource (DISPLAYCONT"...
0x1400101e7  jmp     loc_140010378
0x1400101ec  lea     rcx, [r15+98h]; struct CTimedCallback **
0x1400101f3  call    ?CreateInstance@CTimedCallback@@SAJPEAPEAV1@@Z; CTimedCallback::CreateInstance(CTimedCallback * *)
0x1400101f8  mov     edi, eax
0x1400101fa  test    eax, eax
0x1400101fc  jns     short loc_140010238
0x1400101fe  mov     rax, cs:WPP_GLOBAL_Control
0x140010205  cmp     rax, rsi
0x140010208  jz      loc_140010397
0x14001020e  test    byte ptr [rax+1Ch], 8
0x140010212  jz      loc_140010397
0x140010218  cmp     byte ptr [rax+19h], 2
0x14001021c  jb      loc_140010397
0x140010222  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140010227  mov     edx, 1Eh
0x14001022c  lea     rcx, aCtimedcallback_3; "CTimedCallback::CreateInstance failed!"
0x140010233  jmp     loc_140010378
0x140010238  mov     rcx, [r15+60h]
0x14001023c  lea     rbx, [r15+0A0h]
0x140010243  mov     r9, rbx
0x140010246  lea     rdx, ?StaticDisplayControlProcessThreadMain@RdpDisplayControlHandler@@CAXPEAX@Z; RdpDisplayControlHandler::StaticDisplayControlProcessThreadMain(void *)
0x14001024d  mov     r8, r15
0x140010250  mov     rax, [rcx]
0x140010253  mov     rax, [rax+38h]
0x140010257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001025c  mov     edi, eax
0x14001025e  test    eax, eax
0x140010260  jns     short loc_14001029C
0x140010262  mov     rax, cs:WPP_GLOBAL_Control
0x140010269  cmp     rax, rsi
0x14001026c  jz      loc_140010397
0x140010272  test    byte ptr [rax+1Ch], 8
0x140010276  jz      loc_140010397
0x14001027c  cmp     byte ptr [rax+19h], 2
0x140010280  jb      loc_140010397
0x140010286  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001028b  mov     edx, 1Fh
0x140010290  lea     rcx, aCreatethreadFa; "CreateThread failed!"
0x140010297  jmp     loc_140010378
0x14001029c  mov     rcx, [rbx]
0x14001029f  xor     edx, edx
0x1400102a1  mov     rax, [rcx]
0x1400102a4  mov     rax, [rax+20h]
0x1400102a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400102ad  mov     edi, eax
0x1400102af  test    eax, eax
0x1400102b1  jns     short loc_1400102ED
0x1400102b3  mov     rax, cs:WPP_GLOBAL_Control
0x1400102ba  cmp     rax, rsi
0x1400102bd  jz      loc_140010397
0x1400102c3  test    byte ptr [rax+1Ch], 8
0x1400102c7  jz      loc_140010397
0x1400102cd  cmp     byte ptr [rax+19h], 2
0x1400102d1  jb      loc_140010397
0x1400102d7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400102dc  mov     edx, 20h ; ' '
0x1400102e1  lea     rcx, aStartthreadFai; "StartThread failed!"
0x1400102e8  jmp     loc_140010378
0x1400102ed  xor     r9d, r9d; dwFlags
0x1400102f0  mov     [rsp+3F8h+DisplayDevice.cb], 348h
0x1400102f8  lea     r8, [rsp+3F8h+DisplayDevice]; lpDisplayDevice
0x1400102fd  xor     edx, edx; iDevNum
0x1400102ff  xor     ecx, ecx; lpDevice
0x140010301  call    cs:__imp_EnumDisplayDevicesW
0x140010307  lea     rcx, aUnknown_0; "unknown"
0x14001030e  mov     rdx, r12; struct _GUID *
0x140010311  test    eax, eax
0x140010313  lea     rbx, [rsp+3F8h+DisplayDevice.DeviceString]
0x14001031b  cmovz   rbx, rcx
0x14001031f  lea     rcx, [rsp+3F8h+ActivityId]; ActivityId
0x140010324  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x140010329  mov     rcx, rbx; this
0x14001032c  call    ?LogRDPGraphicsAdapter@RDPGraphicsTraceLogging@@YAXPEBG@Z; RDPGraphicsTraceLogging::LogRDPGraphicsAdapter(ushort const *)
  ... truncated ...
```
