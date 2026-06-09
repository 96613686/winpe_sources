# CKsProxy::CKsProxy(IUnknown *,long *)

- ea: `0x100087bd`
- end: `0x10008bdd`
- name: `??0CKsProxy@@QAE@PAUIUnknown@@PAJ@Z`
- size: `1056`
- prototype: `CKsProxy *__thiscall(CKsProxy *__hidden this, struct IUnknown *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x10008240`

## callees

- `0x100063f1`
- `0x10007823`
- `0x1000784e`
- `0x100087bd`
- `0x1002d510`
- `0x1002e725`
- `0x1002e852`
- `0x1002f736`
- `0x1003a6fd`
- `0x1003a72c`
- `0x1003aba0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10008a48`
- `KERNEL32!GetLastError` at `0x10008afc`
- `KERNEL32!GetLastError` at `0x10008a48`
- `KERNEL32!GetLastError` at `0x10008afc`
- `KERNEL32!CreateEventW` at `0x10008a20`
- `KERNEL32!CreateEventW` at `0x10008ab3`
- `KERNEL32!CreateEventW` at `0x10008aec`
- `KERNEL32!CreateEventW` at `0x10008a20`
- `KERNEL32!CreateEventW` at `0x10008ab3`
- `KERNEL32!CreateEventW` at `0x10008aec`
- `KERNEL32!InitializeCriticalSection` at `0x100087e4`
- `KERNEL32!InitializeCriticalSection` at `0x100089e7`
- `KERNEL32!InitializeCriticalSection` at `0x100087e4`
- `KERNEL32!InitializeCriticalSection` at `0x100089e7`
- `KERNEL32!CreateSemaphoreW` at `0x10008a75`
- `KERNEL32!CreateSemaphoreW` at `0x10008a75`
- `KERNEL32!GetSystemTime` at `0x10008b98`
- `KERNEL32!GetSystemTime` at `0x10008b98`

## pseudocode

```c
CKsProxy *__thiscall CKsProxy::CKsProxy(CKsProxy *this, struct IUnknown *a2, int *a3)
{
  CCritSec *v4; // ebx
  const unsigned __int16 *v5; // ecx
  CAggregateDShowKsProxyTelemetry *v6; // eax
  CKsProxy *v7; // ebx
  _KSSTREAM_SEGMENT **v8; // eax
  void **v9; // eax
  int m_ActiveIoEventCount; // ecx
  signed int v11; // eax
  unsigned int v12; // ecx
  HANDLE SemaphoreW; // eax
  void **v14; // eax
  void **v15; // eax
  unsigned int m_ActiveWaitEventCount; // ecx
  HANDLE EventW; // eax
  signed int LastError; // eax
  unsigned int v19; // ecx
  CAggregateDShowKsProxyTelemetry *v20; // eax
  int v21; // edi
  struct CAggregateDShowKsProxyTelemetry *m_pDShowKsProxyEvents; // ecx
  struct _GUID v24; // [esp+Ch] [ebp-38h] BYREF
  CAggregateDShowKsProxyTelemetry *v25; // [esp+1Ch] [ebp-28h]
  int *v26; // [esp+20h] [ebp-24h]
  _SYSTEMTIME SystemTime; // [esp+24h] [ebp-20h] BYREF
  int v28; // [esp+34h] [ebp-10h]
  int v29; // [esp+38h] [ebp-Ch]
  int v30; // [esp+3Ch] [ebp-8h]

  v26 = a3;
  v25 = (CAggregateDShowKsProxyTelemetry *)this;
  v4 = &this->CCritSec;
  InitializeCriticalSection(&this->m_CritSec);
  CUnknown::CUnknown(this, v5, a2);
  this->m_tStart.m_time = 0;
  this->m_State = State_Stopped;
  this->m_pClock = 0;
  v6 = v25;
  if ( !v25 )
    v4 = 0;
  this->m_clsid = _GUID_17cca71b_ecd7_11d0_b908_00a0c9223196;
  *((_DWORD *)v6 + 14) = v4;
  v7 = (CKsProxy *)v6;
  *((_DWORD *)v6 + 22) = 0;
  *((_DWORD *)v6 + 21) = 0;
  *((_DWORD *)v6 + 43) = 0;
  *((_DWORD *)v6 + 44) = 0;
  *((_DWORD *)v6 + 45) = 0;
  *((_DWORD *)v6 + 46) = 10;
  *((_DWORD *)v6 + 47) = 0;
  *((_DWORD *)v6 + 48) = 0;
  *((_DWORD *)v6 + 49) = 0;
  *((_DWORD *)v6 + 50) = 0;
  *((_DWORD *)v6 + 51) = 0;
  *((_DWORD *)v6 + 52) = 10;
  *((_DWORD *)v6 + 53) = 0;
  *((_DWORD *)v6 + 54) = 0;
  *((_DWORD *)v6 + 15) = 0;
  *((_DWORD *)v6 + 16) = 0;
  *((_DWORD *)v6 + 17) = 0;
  *((_DWORD *)v6 + 18) = 1;
  *(_DWORD *)v6 = &CKsProxy::`vftable'{for `CUnknown'};
  *((_DWORD *)v6 + 3) = &CKsProxy::`vftable'{for `IBaseFilter'};
  *((_DWORD *)v6 + 4) = &CKsProxy::`vftable'{for `IAMovieSetup'};
  *((_DWORD *)v6 + 20) = &CKsProxy::`vftable'{for `CPersistStream'};
  *((_DWORD *)v6 + 23) = &CKsProxy::`vftable'{for `ISpecifyPropertyPages'};
  *((_DWORD *)v6 + 24) = &CKsProxy::`vftable'{for `IPersistPropertyBag'};
  *((_DWORD *)v6 + 25) = &CKsProxy::`vftable'{for `IReferenceClock'};
  *((_DWORD *)v6 + 26) = &CKsProxy::`vftable'{for `IMediaSeeking'};
  *((_DWORD *)v6 + 27) = &CKsProxy::`vftable'{for `IKsObject'};
  *((_DWORD *)v6 + 28) = &CKsProxy::`vftable'{for `IKsClock'};
  *((_DWORD *)v6 + 29) = &CKsProxy::`vftable'{for `IKsPropertySet'};
  *((_DWORD *)v6 + 30) = &CKsProxy::`vftable'{for `IKsClockPropertySet'};
  *((_DWORD *)v6 + 31) = &CKsProxy::`vftable'{for `IAMFilterMiscFlags'};
  *((_DWORD *)v6 + 32) = &CKsProxy::`vftable'{for `IKsControl'};
  *((_DWORD *)v6 + 33) = &CKsProxy::`vftable'{for `IKsTopology'};
  *((_DWORD *)v6 + 34) = &CKsProxy::`vftable'{for `IKsAggregateControl'};
  *((_DWORD *)v6 + 35) = &CKsProxy::`vftable'{for `IAMDeviceRemoval'};
  *((_DWORD *)v6 + 36) = &CKsProxy::`vftable'{for `IKsNotifyEvent'};
  *((_DWORD *)v6 + 55) = 0;
  *((_DWORD *)v6 + 56) = 0;
  *((_DWORD *)v6 + 57) = 0;
  *((_DWORD *)v6 + 58) = 0;
  *((_DWORD *)v6 + 60) = 0;
  *((_DWORD *)v6 + 67) = 0;
  *((_DWORD *)v6 + 68) = 0;
  *((_DWORD *)v6 + 69) = 0;
  *((_DWORD *)v6 + 70) = 0;
  *((_DWORD *)v6 + 71) = 0;
  *((_DWORD *)v6 + 72) = 0;
  *((_DWORD *)v6 + 77) = 0;
  *((_DWORD *)v6 + 78) = 0;
  *((_DWORD *)v6 + 79) = 0;
  *((_DWORD *)v6 + 80) = 0;
  *((_DWORD *)v6 + 92) = 0;
  *((_DWORD *)v6 + 73) = 0;
  *((_DWORD *)v6 + 74) = 0;
  *((_DWORD *)v6 + 75) = 0;
  *((_DWORD *)v6 + 76) = 0;
  *((_DWORD *)v6 + 83) = 0;
  *((_DWORD *)v6 + 84) = 0;
  *((_DWORD *)v6 + 85) = 0;
  *((_DWORD *)v6 + 90) = 0;
  *((_DWORD *)v6 + 91) = 0;
  *((_DWORD *)v6 + 93) = 0;
  *((_DWORD *)v6 + 94) = 0;
  *((_DWORD *)v6 + 95) = 0;
  *((_DWORD *)v6 + 96) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF_(0xEu, &WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids, *((_QWORD *)WPP_GLOBAL_Control + 2));
  InitializeCriticalSection(&v7->m_IoThreadCriticalSection);
  v8 = (_KSSTREAM_SEGMENT **)operator new[](0x100u);
  v7->m_IoSegments = v8;
  if ( !v8 )
    goto LABEL_27;
  v9 = (void **)operator new[](0x100u);
  v7->m_IoEvents = v9;
  if ( !v9 )
    goto LABEL_27;
  v7->m_IoEvents[v7->m_ActiveIoEventCount] = CreateEventW(0, 0, 0, 0);
  m_ActiveIoEventCount = v7->m_ActiveIoEventCount;
  if ( !v7->m_IoEvents[m_ActiveIoEventCount] )
    goto LABEL_9;
  v7->m_ActiveIoEventCount = m_ActiveIoEventCount + 1;
  SemaphoreW = CreateSemaphoreW(0, 63, 63, 0);
  v7->m_IoFreeSlotSemaphore = SemaphoreW;
  if ( !SemaphoreW )
    goto LABEL_9;
  v14 = (void **)operator new[](0x100u);
  v7->m_WaitEvents = v14;
  if ( !v14 || (v15 = (void **)operator new[](0x100u), (v7->m_WaitPins = v15) == 0) )
  {
LABEL_27:
    *v26 = -2147024882;
    return v7;
  }
  v7->m_WaitEvents[v7->m_ActiveWaitEventCount] = CreateEventW(0, 0, 0, 0);
  m_ActiveWaitEventCount = v7->m_ActiveWaitEventCount;
  if ( v7->m_WaitEvents[m_ActiveWaitEventCount] )
  {
    v7->m_ActiveWaitEventCount = m_ActiveWaitEventCount + 1;
    EventW = CreateEventW(0, 0, 0, 0);
    v7->m_WaitReplyHandle = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v19 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v19 = LastError;
      *v26 = v19;
    }
    v7->m_lInProgress = 0;
    v25 = (CAggregateDShowKsProxyTelemetry *)operator new(8u);
    if ( v25 )
    {
      v24 = *SessionIdProvider::CreateSessionId((struct _GUID *)&SystemTime.wSecond);
      v20 = CAggregateDShowKsProxyTelemetry::CAggregateDShowKsProxyTelemetry(v25, &v24);
    }
    else
    {
      v20 = 0;
    }
    v7->m_pDShowKsProxyEvents = v20;
    if ( v20 )
    {
      v21 = *((_DWORD *)v20 + 1);
      if ( v21 )
        (*(void (__thiscall **)(int, int, _DWORD))(*(_DWORD *)v21 + 20))(v21, 300000, 0);
      memset(&v24, 0, sizeof(v24));
      v29 = 0;
      v30 = 0;
      memset(&SystemTime, 0, sizeof(SystemTime));
      v28 = 0;
      GetSystemTime(&SystemTime);
      m_pDShowKsProxyEvents = v7->m_pDShowKsProxyEvents;
      v28 = *v26;
      CAggregateDShowKsProxyTelemetry::AddData(m_pDShowKsProxyEvents, 0, &SystemTime);
      DShowKsProxyTelemetryValue::~DShowKsProxyTelemetryValue((DShowKsProxyTelemetryValue *)&SystemTime);
    }
    return v7;
  }
LABEL_9:
  v11 = GetLastError();
  v12 = (unsigned __int16)v11 | 0x80070000;
  if ( v11 <= 0 )
    v12 = v11;
  *v26 = v12;
  return v7;
}

```

## disassembly

```asm
0x100087bd  mov     edi, edi
0x100087bf  push    ebp
0x100087c0  mov     ebp, esp
0x100087c2  sub     esp, 38h
0x100087c5  mov     eax, ___security_cookie
0x100087ca  xor     eax, ebp
0x100087cc  mov     [ebp+var_4], eax
0x100087cf  mov     eax, [ebp+arg_4]
0x100087d2  push    ebx
0x100087d3  push    esi
0x100087d4  mov     esi, ecx
0x100087d6  mov     [ebp+var_24], eax
0x100087d9  push    edi
0x100087da  mov     [ebp+var_28], esi
0x100087dd  lea     ebx, [esi+94h]
0x100087e3  push    ebx; lpCriticalSection
0x100087e4  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x100087ea  push    [ebp+arg_0]; struct IUnknown *
0x100087ed  push    ecx; unsigned __int16 *
0x100087ee  mov     ecx, esi; this
0x100087f0  call    ??0CUnknown@@QAE@PBGPAUIUnknown@@@Z; CUnknown::CUnknown(ushort const *,IUnknown *)
0x100087f5  xor     eax, eax
0x100087f7  lea     edi, [esi+28h]
0x100087fa  mov     [esi+20h], eax
0x100087fd  xor     ecx, ecx
0x100087ff  mov     [esi+24h], eax
0x10008802  mov     [esi+14h], eax
0x10008805  mov     [esi+18h], eax
0x10008808  mov     esi, offset __GUID_17cca71b_ecd7_11d0_b908_00a0c9223196
0x1000880d  mov     eax, [ebp+var_28]
0x10008810  test    eax, eax
0x10008812  push    0Ah
0x10008814  cmovz   ebx, ecx
0x10008817  movsd
0x10008818  movsd
0x10008819  movsd
0x1000881a  movsd
0x1000881b  xor     esi, esi
0x1000881d  mov     [eax+38h], ebx
0x10008820  mov     ebx, eax
0x10008822  pop     eax
0x10008823  mov     [ebx+58h], esi
0x10008826  mov     [ebx+54h], esi
0x10008829  mov     [ebx+0ACh], esi
0x1000882f  mov     [ebx+0B0h], esi
0x10008835  mov     [ebx+0B4h], esi
0x1000883b  mov     [ebx+0B8h], eax
0x10008841  mov     [ebx+0BCh], esi
0x10008847  mov     [ebx+0C0h], esi
0x1000884d  mov     [ebx+0C4h], esi
0x10008853  mov     [ebx+0C8h], esi
0x10008859  mov     [ebx+0CCh], esi
0x1000885f  mov     [ebx+0D0h], eax
0x10008865  mov     [ebx+0D4h], esi
0x1000886b  mov     [ebx+0D8h], esi
0x10008871  mov     [ebx+3Ch], esi
0x10008874  mov     [ebx+40h], esi
0x10008877  mov     [ebx+44h], esi
0x1000887a  mov     dword ptr [ebx+48h], 1
0x10008881  mov     dword ptr [ebx], offset ??_7CKsProxy@@6BCUnknown@@@; const CKsProxy::`vftable'{for `CUnknown'}
0x10008887  mov     dword ptr [ebx+0Ch], offset ??_7CKsProxy@@6BIBaseFilter@@@; const CKsProxy::`vftable'{for `IBaseFilter'}
0x1000888e  mov     dword ptr [ebx+10h], offset ??_7CKsProxy@@6BIAMovieSetup@@@; const CKsProxy::`vftable'{for `IAMovieSetup'}
0x10008895  mov     dword ptr [ebx+50h], offset ??_7CKsProxy@@6BCPersistStream@@@; const CKsProxy::`vftable'{for `CPersistStream'}
0x1000889c  mov     dword ptr [ebx+5Ch], offset ??_7CKsProxy@@6BISpecifyPropertyPages@@@; const CKsProxy::`vftable'{for `ISpecifyPropertyPages'}
0x100088a3  mov     dword ptr [ebx+60h], offset ??_7CKsProxy@@6BIPersistPropertyBag@@@; const CKsProxy::`vftable'{for `IPersistPropertyBag'}
0x100088aa  mov     dword ptr [ebx+64h], offset ??_7CKsProxy@@6BIReferenceClock@@@; const CKsProxy::`vftable'{for `IReferenceClock'}
0x100088b1  mov     dword ptr [ebx+68h], offset ??_7CKsProxy@@6BIMediaSeeking@@@; const CKsProxy::`vftable'{for `IMediaSeeking'}
0x100088b8  mov     dword ptr [ebx+6Ch], offset ??_7CKsProxy@@6BIKsObject@@@; const CKsProxy::`vftable'{for `IKsObject'}
0x100088bf  mov     dword ptr [ebx+70h], offset ??_7CKsProxy@@6BIKsClock@@@; const CKsProxy::`vftable'{for `IKsClock'}
0x100088c6  mov     dword ptr [ebx+74h], offset ??_7CKsProxy@@6BIKsPropertySet@@@; const CKsProxy::`vftable'{for `IKsPropertySet'}
0x100088cd  mov     dword ptr [ebx+78h], offset ??_7CKsProxy@@6BIKsClockPropertySet@@@; const CKsProxy::`vftable'{for `IKsClockPropertySet'}
0x100088d4  mov     dword ptr [ebx+7Ch], offset ??_7CKsProxy@@6BIAMFilterMiscFlags@@@; const CKsProxy::`vftable'{for `IAMFilterMiscFlags'}
0x100088db  mov     dword ptr [ebx+80h], offset ??_7CKsProxy@@6BIKsControl@@@; const CKsProxy::`vftable'{for `IKsControl'}
0x100088e5  mov     dword ptr [ebx+84h], offset ??_7CKsProxy@@6BIKsTopology@@@; const CKsProxy::`vftable'{for `IKsTopology'}
0x100088ef  mov     dword ptr [ebx+88h], offset ??_7CKsProxy@@6BIKsAggregateControl@@@; const CKsProxy::`vftable'{for `IKsAggregateControl'}
0x100088f9  mov     dword ptr [ebx+8Ch], offset ??_7CKsProxy@@6BIAMDeviceRemoval@@@; const CKsProxy::`vftable'{for `IAMDeviceRemoval'}
0x10008903  mov     dword ptr [ebx+90h], offset ??_7CKsProxy@@6BIKsNotifyEvent@@@; const CKsProxy::`vftable'{for `IKsNotifyEvent'}
0x1000890d  mov     [ebx+0DCh], esi
0x10008913  mov     [ebx+0E0h], esi
0x10008919  mov     [ebx+0E4h], esi
0x1000891f  mov     [ebx+0E8h], esi
0x10008925  mov     [ebx+0F0h], esi
0x1000892b  mov     [ebx+10Ch], esi
0x10008931  mov     [ebx+110h], esi
0x10008937  mov     [ebx+114h], esi
0x1000893d  mov     [ebx+118h], esi
0x10008943  mov     [ebx+11Ch], esi
0x10008949  mov     [ebx+120h], esi
0x1000894f  mov     [ebx+134h], esi
0x10008955  mov     [ebx+138h], esi
0x1000895b  mov     [ebx+13Ch], esi
0x10008961  mov     [ebx+140h], esi
0x10008967  mov     [ebx+170h], esi
0x1000896d  mov     [ebx+124h], esi
0x10008973  mov     [ebx+128h], esi
0x10008979  mov     [ebx+12Ch], esi
0x1000897f  mov     [ebx+130h], esi
0x10008985  mov     [ebx+14Ch], esi
0x1000898b  mov     [ebx+150h], esi
0x10008991  mov     [ebx+154h], esi
0x10008997  mov     [ebx+168h], esi
0x1000899d  mov     [ebx+16Ch], esi
0x100089a3  mov     [ebx+174h], esi
0x100089a9  mov     [ebx+178h], esi
0x100089af  mov     [ebx+17Ch], esi
0x100089b5  mov     [ebx+180h], esi
0x100089bb  mov     eax, _WPP_GLOBAL_Control
0x100089c0  cmp     eax, offset _WPP_GLOBAL_Control
0x100089c5  jz      short loc_100089E0
0x100089c7  cmp     byte ptr [eax+19h], 5
0x100089cb  jb      short loc_100089E0
0x100089cd  push    dword ptr [eax+14h]
0x100089d0  mov     edx, offset _WPP_30ed42259abc31301495a1e3ed82e77f_Traceguids; MessageGuid
0x100089d5  push    dword ptr [eax+10h]; LoggerHandle
0x100089d8  push    0Eh
0x100089da  pop     ecx; MessageNumber
0x100089db  call    _WPP_SF_@16; WPP_SF_(x,x,x,x)
0x100089e0  lea     eax, [ebx+0F4h]
0x100089e6  push    eax; lpCriticalSection
0x100089e7  call    ds:__imp__InitializeCriticalSection@4; InitializeCriticalSection(x)
0x100089ed  mov     edi, 100h
0x100089f2  push    edi; unsigned int
0x100089f3  call    ??_U@YAPAXI@Z; operator new[](uint)
0x100089f8  mov     [ebx+114h], eax
0x100089fe  pop     ecx
0x100089ff  test    eax, eax
0x10008a01  jz      loc_10008BC1
0x10008a07  push    edi; unsigned int
0x10008a08  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10008a0d  mov     [ebx+110h], eax
0x10008a13  pop     ecx
0x10008a14  test    eax, eax
0x10008a16  jz      loc_10008BC1
0x10008a1c  push    esi; lpName
0x10008a1d  push    esi; bInitialState
0x10008a1e  push    esi; bManualReset
0x10008a1f  push    esi; lpEventAttributes
0x10008a20  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10008a26  mov     ecx, [ebx+118h]
0x10008a2c  mov     edx, eax
0x10008a2e  mov     eax, [ebx+110h]
0x10008a34  mov     [eax+ecx*4], edx
0x10008a37  mov     ecx, [ebx+118h]
0x10008a3d  mov     eax, [ebx+110h]
0x10008a43  cmp     [eax+ecx*4], esi
0x10008a46  jnz     short loc_10008A66
0x10008a48  call    ds:__imp__GetLastError@0; GetLastError()
0x10008a4e  mov     edx, [ebp+var_24]
0x10008a51  movzx   ecx, ax
0x10008a54  or      ecx, 80070000h
0x10008a5a  test    eax, eax
0x10008a5c  cmovle  ecx, eax
0x10008a5f  mov     [edx], ecx
0x10008a61  jmp     loc_10008BCA
0x10008a66  push    esi; lpName
0x10008a67  push    3Fh ; '?'; lMaximumCount
0x10008a69  push    3Fh ; '?'; lInitialCount
0x10008a6b  lea     eax, [ecx+1]
0x10008a6e  push    esi; lpSemaphoreAttributes
0x10008a6f  mov     [ebx+118h], eax
0x10008a75  call    ds:__imp__CreateSemaphoreW@16; CreateSemaphoreW(x,x,x,x)
0x10008a7b  mov     [ebx+10Ch], eax
0x10008a81  test    eax, eax
0x10008a83  jz      short loc_10008A48
0x10008a85  push    edi; unsigned int
0x10008a86  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10008a8b  mov     [ebx+134h], eax
0x10008a91  pop     ecx
0x10008a92  test    eax, eax
0x10008a94  jz      loc_10008BC1
0x10008a9a  push    edi; unsigned int
0x10008a9b  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10008aa0  mov     [ebx+138h], eax
0x10008aa6  pop     ecx
0x10008aa7  test    eax, eax
0x10008aa9  jz      loc_10008BC1
0x10008aaf  push    esi; lpName
0x10008ab0  push    esi; bInitialState
0x10008ab1  push    esi; bManualReset
0x10008ab2  push    esi; lpEventAttributes
0x10008ab3  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10008ab9  mov     ecx, [ebx+13Ch]
0x10008abf  mov     edx, eax
0x10008ac1  mov     eax, [ebx+134h]
0x10008ac7  mov     [eax+ecx*4], edx
0x10008aca  mov     ecx, [ebx+13Ch]
0x10008ad0  mov     eax, [ebx+134h]
0x10008ad6  cmp     [eax+ecx*4], esi
0x10008ad9  jz      loc_10008A48
0x10008adf  push    esi; lpName
0x10008ae0  push    esi; bInitialState
0x10008ae1  push    esi; bManualReset
0x10008ae2  lea     eax, [ecx+1]
0x10008ae5  push    esi; lpEventAttributes
0x10008ae6  mov     [ebx+13Ch], eax
0x10008aec  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10008af2  mov     [ebx+140h], eax
0x10008af8  test    eax, eax
0x10008afa  jnz     short loc_10008B15
0x10008afc  call    ds:__imp__GetLastError@0; GetLastError()
0x10008b02  movzx   ecx, ax
0x10008b05  or      ecx, 80070000h
0x10008b0b  test    eax, eax
0x10008b0d  cmovle  ecx, eax
0x10008b10  mov     eax, [ebp+var_24]
0x10008b13  mov     [eax], ecx
0x10008b15  push    8; Size
0x10008b17  mov     [ebx+184h], esi
0x10008b1d  call    ??2@YAPAXI@Z; operator new(uint)
0x10008b22  mov     [ebp+var_28], eax
0x10008b25  pop     ecx
0x10008b26  test    eax, eax
0x10008b28  jz      short loc_10008B4C
0x10008b2a  lea     eax, [ebp+SystemTime.wSecond]
0x10008b2d  push    eax; retstr
0x10008b2e  call    ?CreateSessionId@SessionIdProvider@@SG?AU_GUID@@XZ; SessionIdProvider::CreateSessionId(void)
0x10008b33  mov     ecx, [ebp+var_28]; this
0x10008b36  lea     edi, [ebp+var_38]
0x10008b39  mov     esi, eax
0x10008b3b  lea     eax, [ebp+var_38]
0x10008b3e  push    eax; struct _GUID *
0x10008b3f  movsd
0x10008b40  movsd
0x10008b41  movsd
0x10008b42  movsd
0x10008b43  call    ??0CAggregateDShowKsProxyTelemetry@@QAE@ABU_GUID@@@Z; CAggregateDShowKsProxyTelemetry::CAggregateDShowKsProxyTelemetry(_GUID const &)
0x10008b48  xor     esi, esi
0x10008b4a  jmp     short loc_10008B4E
0x10008b4c  mov     eax, esi
0x10008b4e  mov     [ebx+170h], eax
0x10008b54  test    eax, eax
0x10008b56  jz      short loc_10008BCA
0x10008b58  mov     edi, [eax+4]
0x10008b5b  test    edi, edi
0x10008b5d  jz      short loc_10008B76
0x10008b5f  mov     eax, [edi]
0x10008b61  push    esi
0x10008b62  push    493E0h
0x10008b67  mov     esi, [eax+14h]
0x10008b6a  mov     ecx, esi; this
0x10008b6c  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x10008b72  mov     ecx, edi
0x10008b74  call    esi
0x10008b76  xor     eax, eax
0x10008b78  lea     edi, [ebp+var_38]
0x10008b7b  stosd
0x10008b7c  lea     esi, [ebp+var_38]
0x10008b7f  xor     ecx, ecx
0x10008b81  mov     [ebp+var_C], ecx
0x10008b84  mov     [ebp+var_8], ecx
0x10008b87  stosd
0x10008b88  stosd
0x10008b89  stosd
0x10008b8a  lea     eax, [ebp+SystemTime]
0x10008b8d  lea     edi, [ebp+SystemTime]
0x10008b90  movsd
0x10008b91  push    eax; lpSystemTime
0x10008b92  movsd
0x10008b93  movsd
0x10008b94  movsd
0x10008b95  mov     [ebp+var_10], ecx
0x10008b98  call    ds:__imp__GetSystemTime@4; GetSystemTime(x)
0x10008b9e  mov     edx, [ebp+var_24]
0x10008ba1  mov     ecx, [ebx+170h]
0x10008ba7  mov     eax, [edx]
0x10008ba9  mov     [ebp+var_10], eax
0x10008bac  lea     eax, [ebp+SystemTime]
0x10008baf  push    eax
0x10008bb0  push    0
0x10008bb2  call    ?AddData@CAggregateDShowKsProxyTelemetry@@QAEXW4DShowKsProxyTelemetryType@@ABUDShowKsProxyTelemetryValue@@@Z; CAggregateDShowKsProxyTelemetry::AddData(DShowKsProxyTelemetryType,DShowKsProxyTelemetryValue const &)
0x10008bb7  lea     ecx, [ebp+SystemTime]; this
0x10008bba  call    ??1DShowKsProxyTelemetryValue@@QAE@XZ; DShowKsProxyTelemetryValue::~DShowKsProxyTelemetryValue(void)
0x10008bbf  jmp     short loc_10008BCA
0x10008bc1  mov     eax, [ebp+var_24]
0x10008bc4  mov     dword ptr [eax], 8007000Eh
0x10008bca  mov     ecx, [ebp+var_4]
0x10008bcd  mov     eax, ebx
0x10008bcf  pop     edi
0x10008bd0  pop     esi
0x10008bd1  xor     ecx, ebp; StackCookie
0x10008bd3  pop     ebx
0x10008bd4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10008bd9  leave
0x10008bda  retn    8
```
