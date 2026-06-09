# NcsiHotspotAuthEventMonitor::ProcessEvent(void *)

- ea: `0x18005cac0`
- end: `0x18005cec8`
- name: `?ProcessEvent@NcsiHotspotAuthEventMonitor@@MEAAXPEAX@Z`
- size: `1032`
- prototype: `void(NcsiHotspotAuthEventMonitor *__hidden this, void *)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180009804`
- `0x18000e350`
- `0x18000e59c`
- `0x180010200`
- `0x180011a58`
- `0x180013eb0`
- `0x18001c698`
- `0x180021e7c`
- `0x18002a004`
- `0x18002d644`
- `0x180047240`
- `0x180047f78`
- `0x18005cac0`
- `0x18005ced0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cdf2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cdf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ccc4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005ccc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbec`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x18005cb40`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtCreateRenderContext` at `0x18005cb40`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18005ce87`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x18005ce87`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18005cbe2`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtRender` at `0x18005cbe2`

## pseudocode

```c
void __fastcall NcsiHotspotAuthEventMonitor::ProcessEvent(NcsiHotspotAuthEventMonitor *this, void *a2)
{
  EVT_HANDLE RenderContext; // rsi
  DWORD LastError; // eax
  DWORD v5; // eax
  DWORD v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int16 v10; // di
  NCSI_INTERFACE_ATTRIBUTES *i; // rbx
  __int64 v12; // rax
  char IsBehindHotspot; // al
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int16 v17; // r10
  __int64 v18; // r9
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int16 v23; // r10
  const char *v24; // r9
  DWORD PropertyCount; // [rsp+40h] [rbp-49h] BYREF
  DWORD BufferUsed; // [rsp+44h] [rbp-45h] BYREF
  LPCWSTR ValuePaths[3]; // [rsp+48h] [rbp-41h] BYREF
  __int64 Buffer; // [rsp+60h] [rbp-29h] BYREF
  int v29; // [rsp+6Ch] [rbp-1Dh]
  _QWORD *v30; // [rsp+70h] [rbp-19h]
  int v31; // [rsp+7Ch] [rbp-Dh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_62749a71087337d15a6403c372724797_Traceguids);
  }
  ValuePaths[0] = L"Event/System/EventID";
  ValuePaths[1] = L"Event/EventData/Data[@Name=\"InterfaceGuid\"]";
  RenderContext = EvtCreateRenderContext(2u, ValuePaths, 0);
  if ( !RenderContext )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_62749a71087337d15a6403c372724797_Traceguids, LastError);
    }
    return;
  }
  memset_0(&Buffer, 0, 0x52u);
  BufferUsed = 0;
  PropertyCount = 0;
  if ( !EvtRender(RenderContext, a2, 0, 0x52u, &Buffer, &BufferUsed, &PropertyCount) )
  {
    v5 = GetLastError();
    v6 = v5;
    v7 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_62749a71087337d15a6403c372724797_Traceguids, v5);
    }
    if ( v6 == 122 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v7);
    goto LABEL_68;
  }
  if ( !CheckIfClientPresent() )
  {
    v8 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      v9 = 13;
LABEL_67:
      WPP_SF_(*(_QWORD *)(v8 + 16), v9, WPP_62749a71087337d15a6403c372724797_Traceguids);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  if ( PropertyCount >= 2 && v29 == 6 && v31 == 15 )
  {
    v10 = Buffer;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF__guid_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, WPP_62749a71087337d15a6403c372724797_Traceguids, Buffer);
    }
    EnterCriticalSection(&g_ncsiLock);
    for ( i = g_ncsiInterfaceList; ; i = (NCSI_INTERFACE_ATTRIBUTES *)((char *)i + 12888) )
    {
      if ( i == xmmword_18009DCC0 )
        goto LABEL_55;
      if ( !*((_DWORD *)i + 6) )
      {
        v12 = *((_QWORD *)i + 1) - *v30;
        if ( !v12 )
          v12 = *((_QWORD *)i + 2) - v30[1];
        if ( !v12 )
          break;
      }
    }
    IsBehindHotspot = NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(i, 0);
    v17 = 1003;
    v18 = 1002;
    if ( !IsBehindHotspot || (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(v15, v14, v16, 1002) )
    {
      LOBYTE(v16) = 0;
      if ( v10 != v17 || !(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsActiveProbeCompleted(i, 0, v16, v18) )
        goto LABEL_47;
    }
    else if ( v10 != (_WORD)v18 )
    {
      goto LABEL_47;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_i(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        16,
        WPP_62749a71087337d15a6403c372724797_Traceguids,
        *(_QWORD *)i);
    }
    ActiveProbeManager::TryNcsiQueueActiveInternetProbe(i, 4);
LABEL_47:
    if ( !(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(i, 1)
      || (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(v20, v19, v21, v22) )
    {
      if ( v10 != v23 || !(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsActiveProbeCompleted(i, 1, v21, v22) )
      {
LABEL_50:
        if ( !(_BYTE)v21
          && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
          && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
        {
          WPP_SF_i(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            18,
            WPP_62749a71087337d15a6403c372724797_Traceguids,
            *(_QWORD *)i);
        }
        goto LABEL_55;
      }
    }
    else if ( v10 != (_WORD)v22 )
    {
      goto LABEL_50;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_i(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        17,
        WPP_62749a71087337d15a6403c372724797_Traceguids,
        *(_QWORD *)i);
    }
    ActiveProbeManager::TryNcsiQueueActiveInternetProbe(i, 4);
LABEL_55:
    LeaveCriticalSection(&g_ncsiLock);
    goto LABEL_68;
  }
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v9 = 14;
    goto LABEL_67;
  }
LABEL_68:
  if ( !EvtClose(RenderContext) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\net\\diagnostics\\ncsi\\lib\\hotspotauthmonitor.cpp",
      v24);
}

```

## disassembly

```asm
0x18005cac0  mov     [rsp-8+arg_0], rbx
0x18005cac5  mov     [rsp-8+arg_10], rsi
0x18005caca  push    rbp
0x18005cacb  push    rdi
0x18005cacc  push    r12
0x18005cace  lea     rbp, [rsp-47h]
0x18005cad3  sub     rsp, 0D0h
0x18005cada  mov     rax, cs:__security_cookie
0x18005cae1  xor     rax, rsp
0x18005cae4  mov     [rbp+57h+var_20], rax
0x18005cae8  mov     rbx, rdx
0x18005caeb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005caf2  lea     r12, WPP_GLOBAL_Control
0x18005caf9  cmp     rcx, r12
0x18005cafc  jz      short loc_18005CB1F
0x18005cafe  test    byte ptr [rcx+1Ch], 10h
0x18005cb02  jz      short loc_18005CB1F
0x18005cb04  cmp     byte ptr [rcx+19h], 5
0x18005cb08  jb      short loc_18005CB1F
0x18005cb0a  mov     rcx, [rcx+10h]
0x18005cb0e  lea     r8, WPP_62749a71087337d15a6403c372724797_Traceguids
0x18005cb15  mov     edx, 0Ah
0x18005cb1a  call    WPP_SF_
0x18005cb1f  xor     r8d, r8d; Flags
0x18005cb22  lea     rax, aEventSystemEve_0; "Event/System/EventID"
0x18005cb29  mov     [rbp+57h+ValuePaths], rax
0x18005cb2d  lea     rdx, [rbp+57h+ValuePaths]; ValuePaths
0x18005cb31  lea     rax, aEventEventdata; "Event/EventData/Data[@Name=\"InterfaceG"...
0x18005cb38  mov     [rbp+57h+var_90], rax
0x18005cb3c  lea     ecx, [r8+2]; ValuePathsCount
0x18005cb40  call    cs:__imp_EvtCreateRenderContext
0x18005cb46  mov     rsi, rax
0x18005cb49  test    rax, rax
0x18005cb4c  jnz     short loc_18005CB9A
0x18005cb4e  mov     rax, cs:WPP_GLOBAL_Control
0x18005cb55  cmp     rax, r12
0x18005cb58  jz      loc_18005CEA4
0x18005cb5e  test    byte ptr [rax+1Ch], 10h
0x18005cb62  jz      loc_18005CEA4
0x18005cb68  cmp     byte ptr [rax+19h], 2
0x18005cb6c  jb      loc_18005CEA4
0x18005cb72  call    cs:__imp_GetLastError
0x18005cb78  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cb7f  lea     edx, [rsi+0Bh]
0x18005cb82  mov     r9d, eax
0x18005cb85  lea     r8, WPP_62749a71087337d15a6403c372724797_Traceguids
0x18005cb8c  mov     rcx, [rcx+10h]
0x18005cb90  call    WPP_SF_d
0x18005cb95  jmp     loc_18005CEA4
0x18005cb9a  mov     edi, 52h ; 'R'
0x18005cb9f  lea     rcx, [rbp+57h+var_80]; void *
0x18005cba3  mov     r8d, edi; Size
0x18005cba6  xor     edx, edx; Val
0x18005cba8  call    memset_0
0x18005cbad  lea     rax, [rbp+57h+var_A0]
0x18005cbb1  mov     [rbp+57h+var_9C], 0
0x18005cbb8  mov     [rsp+0E0h+PropertyCount], rax; PropertyCount
0x18005cbbd  mov     r9d, edi; BufferSize
0x18005cbc0  lea     rax, [rbp+57h+var_9C]
0x18005cbc4  mov     [rbp+57h+var_A0], 0
0x18005cbcb  mov     [rsp+0E0h+BufferUsed], rax; BufferUsed
0x18005cbd0  xor     r8d, r8d; Flags
0x18005cbd3  lea     rax, [rbp+57h+var_80]
0x18005cbd7  mov     rdx, rbx; Fragment
0x18005cbda  mov     rcx, rsi; Context
0x18005cbdd  mov     [rsp+0E0h+Buffer], rax; Buffer
0x18005cbe2  call    cs:__imp_EvtRender
0x18005cbe8  test    eax, eax
0x18005cbea  jnz     short loc_18005CC35
0x18005cbec  call    cs:__imp_GetLastError
0x18005cbf2  mov     ebx, eax
0x18005cbf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cbfb  cmp     rcx, r12
0x18005cbfe  jz      short loc_18005CC22
0x18005cc00  test    byte ptr [rcx+1Ch], 10h
0x18005cc04  jz      short loc_18005CC22
0x18005cc06  cmp     byte ptr [rcx+19h], 2
0x18005cc0a  jb      short loc_18005CC22
0x18005cc0c  mov     rcx, [rcx+10h]
0x18005cc10  lea     edx, [rdi-46h]
0x18005cc13  mov     r9d, eax
0x18005cc16  lea     r8, WPP_62749a71087337d15a6403c372724797_Traceguids
0x18005cc1d  call    WPP_SF_d
0x18005cc22  cmp     ebx, 7Ah ; 'z'
0x18005cc25  jnz     loc_18005CE84
0x18005cc2b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005cc30  jmp     loc_18005CE84
0x18005cc35  call    ?CheckIfClientPresent@@YA_NXZ; CheckIfClientPresent(void)
0x18005cc3a  test    al, al
0x18005cc3c  jnz     short loc_18005CC6C
0x18005cc3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cc45  cmp     rcx, r12
0x18005cc48  jz      loc_18005CE84
0x18005cc4e  test    byte ptr [rcx+1Ch], 10h
0x18005cc52  jz      loc_18005CE84
0x18005cc58  cmp     byte ptr [rcx+19h], 5
0x18005cc5c  jb      loc_18005CE84
0x18005cc62  mov     edx, 0Dh
0x18005cc67  jmp     loc_18005CE74
0x18005cc6c  cmp     [rbp+57h+var_A0], 2
0x18005cc70  jb      loc_18005CE57
0x18005cc76  cmp     [rbp+57h+var_74], 6
0x18005cc7a  jnz     loc_18005CE57
0x18005cc80  mov     edx, 0Fh
0x18005cc85  cmp     [rbp+57h+var_64], edx
0x18005cc88  jnz     loc_18005CE57
0x18005cc8e  mov     rdi, [rbp+57h+var_80]
0x18005cc92  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cc99  cmp     rcx, r12
0x18005cc9c  jz      short loc_18005CCBD
0x18005cc9e  test    byte ptr [rcx+1Ch], 10h
0x18005cca2  jz      short loc_18005CCBD
0x18005cca4  cmp     byte ptr [rcx+19h], 5
0x18005cca8  jb      short loc_18005CCBD
0x18005ccaa  mov     rcx, [rcx+10h]
0x18005ccae  lea     r8, WPP_62749a71087337d15a6403c372724797_Traceguids
0x18005ccb5  mov     r9, rdi
0x18005ccb8  call    WPP_SF__guid_
0x18005ccbd  lea     rcx, ?g_ncsiLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18005ccc4  call    cs:__imp_EnterCriticalSection
0x18005ccca  mov     rcx, [rbp+57h+var_70]
0x18005ccce  mov     rbx, cs:?g_ncsiInterfaceList@@3V?$vector@VNCSI_INTERFACE_ATTRIBUTES@@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@A; std::vector<NCSI_INTERFACE_ATTRIBUTES> g_ncsiInterfaceList
0x18005ccd5  cmp     rbx, qword ptr cs:xmmword_18009DCC0
0x18005ccdc  jz      loc_18005CDEB
0x18005cce2  cmp     dword ptr [rbx+18h], 0
0x18005cce6  jnz     short loc_18005CCFE
0x18005cce8  mov     rax, [rbx+8]
0x18005ccec  sub     rax, [rcx]
0x18005ccef  jnz     short loc_18005CCF9
0x18005ccf1  mov     rax, [rbx+10h]
0x18005ccf5  sub     rax, [rcx+8]
0x18005ccf9  test    rax, rax
0x18005ccfc  jz      short loc_18005CD07
0x18005ccfe  add     rbx, 3258h
0x18005cd05  jmp     short loc_18005CCD5
0x18005cd07  xor     edx, edx
0x18005cd09  mov     rcx, rbx
0x18005cd0c  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x18005cd11  mov     r10d, 3EBh
0x18005cd17  lea     r9d, [r10-1]
0x18005cd1b  test    al, al
0x18005cd1d  jz      short loc_18005CD33
0x18005cd1f  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x18005cd24  test    al, al
0x18005cd26  jnz     short loc_18005CD33
0x18005cd28  cmp     di, r9w
0x18005cd2c  jz      short loc_18005CD4A
0x18005cd2e  xor     r8b, r8b
0x18005cd31  jmp     short loc_18005CD96
0x18005cd33  xor     r8b, r8b
0x18005cd36  cmp     di, r10w
0x18005cd3a  jnz     short loc_18005CD96
0x18005cd3c  xor     edx, edx
0x18005cd3e  mov     rcx, rbx
0x18005cd41  call    ?IsActiveProbeCompleted@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsActiveProbeCompleted(_NLA_CONNECTIVITY_FAMILY)
0x18005cd46  test    al, al
0x18005cd48  jz      short loc_18005CD96
0x18005cd4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cd51  cmp     rcx, r12
0x18005cd54  jz      short loc_18005CD7A
0x18005cd56  test    byte ptr [rcx+1Ch], 10h
0x18005cd5a  jz      short loc_18005CD7A
0x18005cd5c  cmp     byte ptr [rcx+19h], 5
0x18005cd60  jb      short loc_18005CD7A
0x18005cd62  mov     r9, [rbx]
0x18005cd65  lea     r8, WPP_62749a71087337d15a6403c372724797_Traceguids
0x18005cd6c  mov     rcx, [rcx+10h]
0x18005cd70  mov     edx, 10h
0x18005cd75  call    WPP_SF_i
0x18005cd7a  xor     r8d, r8d
0x18005cd7d  mov     rcx, rbx
0x18005cd80  lea     edx, [r8+4]
0x18005cd84  call    ?TryNcsiQueueActiveInternetProbe@ActiveProbeManager@@SA?AW4ActiveProbeQueueResult@@PEAVNCSI_INTERFACE_ATTRIBUTES@@W4NcsiProbePerformReason@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; ActiveProbeManager::TryNcsiQueueActiveInternetProbe(NCSI_INTERFACE_ATTRIBUTES *,NcsiProbePerformReason,_NLA_CONNECTIVITY_FAMILY)
0x18005cd89  mov     r9d, 3EAh
0x18005cd8f  mov     r8b, 1
0x18005cd92  lea     r10d, [r9+1]
0x18005cd96  mov     edx, 1
0x18005cd9b  mov     rcx, rbx
0x18005cd9e  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x18005cda3  test    al, al
0x18005cda5  jz      short loc_18005CDFD
0x18005cda7  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x18005cdac  test    al, al
0x18005cdae  jnz     short loc_18005CDFD
0x18005cdb0  cmp     di, r9w
0x18005cdb4  jz      short loc_18005CE14
0x18005cdb6  test    r8b, r8b
0x18005cdb9  jnz     short loc_18005CDEB
0x18005cdbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005cdc2  cmp     rcx, r12
0x18005cdc5  jz      short loc_18005CDEB
0x18005cdc7  test    byte ptr [rcx+1Ch], 10h
0x18005cdcb  jz      short loc_18005CDEB
0x18005cdcd  cmp     byte ptr [rcx+19h], 5
0x18005cdd1  jb      short loc_18005CDEB
0x18005cdd3  mov     r9, [rbx]
0x18005cdd6  lea     r8, WPP_62749a71087337d15a6403c372724797_Traceguids
0x18005cddd  mov     rcx, [rcx+10h]
0x18005cde1  mov     edx, 12h
0x18005cde6  call    WPP_SF_i
0x18005cdeb  lea     rcx, ?g_ncsiLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18005cdf2  call    cs:__imp_LeaveCriticalSection
0x18005cdf8  jmp     loc_18005CE84
0x18005cdfd  cmp     di, r10w
0x18005ce01  jnz     short loc_18005CDB6
0x18005ce03  mov     edx, 1
0x18005ce08  mov     rcx, rbx
0x18005ce0b  call    ?IsActiveProbeCompleted@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsActiveProbeCompleted(_NLA_CONNECTIVITY_FAMILY)
0x18005ce10  test    al, al
0x18005ce12  jz      short loc_18005CDB6
0x18005ce14  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ce1b  cmp     rcx, r12
0x18005ce1e  jz      short loc_18005CE44
0x18005ce20  test    byte ptr [rcx+1Ch], 10h
0x18005ce24  jz      short loc_18005CE44
0x18005ce26  cmp     byte ptr [rcx+19h], 5
0x18005ce2a  jb      short loc_18005CE44
0x18005ce2c  mov     r9, [rbx]
0x18005ce2f  lea     r8, WPP_62749a71087337d15a6403c372724797_Traceguids
0x18005ce36  mov     rcx, [rcx+10h]
0x18005ce3a  mov     edx, 11h
0x18005ce3f  call    WPP_SF_i
0x18005ce44  mov     edx, 4
0x18005ce49  mov     rcx, rbx
0x18005ce4c  lea     r8d, [rdx-3]
0x18005ce50  call    ?TryNcsiQueueActiveInternetProbe@ActiveProbeManager@@SA?AW4ActiveProbeQueueResult@@PEAVNCSI_INTERFACE_ATTRIBUTES@@W4NcsiProbePerformReason@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; ActiveProbeManager::TryNcsiQueueActiveInternetProbe(NCSI_INTERFACE_ATTRIBUTES *,NcsiProbePerformReason,_NLA_CONNECTIVITY_FAMILY)
0x18005ce55  jmp     short loc_18005CDEB
0x18005ce57  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ce5e  cmp     rcx, r12
0x18005ce61  jz      short loc_18005CE84
0x18005ce63  test    byte ptr [rcx+1Ch], 10h
0x18005ce67  jz      short loc_18005CE84
0x18005ce69  cmp     byte ptr [rcx+19h], 2
0x18005ce6d  jb      short loc_18005CE84
0x18005ce6f  mov     edx, 0Eh
0x18005ce74  mov     rcx, [rcx+10h]
0x18005ce78  lea     r8, WPP_62749a71087337d15a6403c372724797_Traceguids
0x18005ce7f  call    WPP_SF_
0x18005ce84  mov     rcx, rsi; Object
0x18005ce87  call    cs:__imp_EvtClose
0x18005ce8d  test    eax, eax
0x18005ce8f  jnz     short loc_18005CEA4
0x18005ce91  mov     rcx, [rbp+5Fh]; this
0x18005ce95  lea     r8, aOnecoreNetDiag_2; "onecore\\net\\diagnostics\\ncsi\\lib\\h"...
0x18005ce9c  lea     edx, [rax+74h]; void *
0x18005ce9f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18005cea4  mov     rcx, [rbp+57h+var_20]
0x18005cea8  xor     rcx, rsp; StackCookie
0x18005ceab  call    __security_check_cookie
0x18005ceb0  lea     r11, [rsp+0E0h+var_10]
0x18005ceb8  mov     rbx, [r11+20h]
0x18005cebc  mov     rsi, [r11+30h]
0x18005cec0  mov     rsp, r11
0x18005cec3  pop     r12
0x18005cec5  pop     rdi
0x18005cec6  pop     rbp
0x18005cec7  retn
```
