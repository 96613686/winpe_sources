# CUMRDPProtocolManager::CreateListener(ushort *,IWRdsProtocolListener * *)

- ea: `0x18003ad40`
- end: `0x18003b50d`
- name: `?CreateListener@CUMRDPProtocolManager@@UEAAJPEAGPEAPEAUIWRdsProtocolListener@@@Z`
- size: `1997`
- prototype: `__int64 __fastcall(CUMRDPProtocolManager *this, unsigned __int16 *, struct IWRdsProtocolListener **, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800015f0`
- `0x180009088`
- `0x180009628`
- `0x18000ee00`
- `0x18000f784`
- `0x180010960`
- `0x18002f734`
- `0x180033da0`
- `0x180034970`
- `0x18003a8a0`
- `0x18003a9d4`
- `0x18003aad4`
- `0x18003abe8`
- `0x18003ac90`
- `0x18003ad40`
- `0x1800446bc`
- `0x1800ab8c0`
- `0x18014c304`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b0cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003b0cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b17d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b17d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b08a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b08a`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18003b3c8`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18003b3c8`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18003b43f`
- `RDPBASE!PAL_System_CritSecLeave` at `0x18003b43f`

## string_xrefs

- `0x18003adae`: `CUMRDPProtocolManager::CreateListener DEBUG/VM/ReverseTCP/ReverseUDP/INET`
- `0x18003ae0f`: `CUMRDPProtocolManager::CreateListener: pTiBus is NULL`
- `0x18003ae22`: `CreateListener`
- `0x18003aea9`: `CreateListener`
- `0x18003b47c`: `CreateListener`
- `0x18003aeb5`: `CUMRDPProtocolManager::CreateListener: wait for input bus timed out, will retry`
- `0x18003af2b`: `CUMRDPProtocolManager::CreateListener: recreate input bus failed`
- `0x18003afc7`: `CUMRDPProtocolManager::CreateListener: wait for input bus timed out again`
- `0x18003b468`: `CUMRDPProtocolManager::CreateListener: TermInputMgr not initialized`
- `0x18003b144`: `Can't find listener registry key in Winstations.`
- `0x18003b190`: `StringCchPrintfW wszListenerKeyPath failed`
- `0x18003b222`: `Creating NP Agent listener`

## pseudocode

```c
__int64 __fastcall CUMRDPProtocolManager::CreateListener(
        CUMRDPProtocolManager *this,
        unsigned __int16 *a2,
        struct IWRdsProtocolListener **a3,
        int a4)
{
  _QWORD *v5; // rcx
  __int64 v8; // r15
  CTiDevice *v9; // r15
  int v10; // edi
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  const char *v31; // rax
  char *v32; // rdx
  struct IWRdsProtocolListener *v33; // rbx
  int v34; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // eax
  int v39; // ecx
  int v40; // r8d
  int v41; // r9d
  _OWORD *v42; // r9
  __int64 v43; // rdx
  __int64 v44; // r8
  bool v45; // zf
  __int128 v46; // xmm0
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  const char *v55; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData[2]; // [rsp+58h] [rbp-A8h] BYREF
  const char *v57; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[8]; // [rsp+68h] [rbp-98h] BYREF
  const char *v59; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type[2]; // [rsp+78h] [rbp-88h] BYREF
  const char *v61; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  _OWORD v63[8]; // [rsp+90h] [rbp-70h] BYREF
  int v64; // [rsp+110h] [rbp+10h]
  WCHAR SubKey[264]; // [rsp+120h] [rbp+20h] BYREF

  v61 = 0;
  v5 = (_QWORD *)((char *)this + 296);
  v55 = 0;
  hKey = 0;
  if ( !*v5 )
    CTraceAndLogUtil<IRdpStateTransitionEventLogCallbacks>::CreateEventLogSession();
  if ( (unsigned int)dword_1801B76C8 > 4 )
  {
    *(_QWORD *)cbData = a2;
    *(_QWORD *)Data = "CUMRDPProtocolManager::CreateListener DEBUG/VM/ReverseTCP/ReverseUDP/INET";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v5,
      (unsigned int)byte_18018EB89,
      (_DWORD)a3,
      a4,
      (__int64)Data,
      (__int64)cbData);
  }
  v8 = *((_QWORD *)this + 15);
  if ( v8 )
  {
    v9 = *(CTiDevice **)(v8 + 48);
    if ( !v9 )
    {
      v10 = -2147467261;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        *(_DWORD *)Data = 2752;
        v61 = "CUMRDPProtocolManager::CreateListener: pTiBus is NULL";
        v55 = "CreateListener";
        *(_QWORD *)cbData = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
        Type[0] = -2147467261;
        v59 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          -2147467261,
          (unsigned int)byte_18018EB33,
          (_DWORD)a3,
          a4,
          (__int64)&v59,
          (__int64)Type,
          (__int64)cbData,
          (__int64)Data,
          (__int64)&v55,
          (__int64)&v61);
      }
      return (unsigned int)v10;
    }
    v11 = CTiDevice::WaitForDeviceReady(v9, 0x9C40u);
    if ( v11 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        v59 = "CreateListener";
        *(_QWORD *)cbData = "CUMRDPProtocolManager::CreateListener: wait for input bus timed out, will retry";
        *(_DWORD *)Data = v11;
        *(_QWORD *)Type = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v11,
          (unsigned int)&byte_18018EAEF,
          v12,
          v13,
          (__int64)Type,
          (__int64)cbData,
          (__int64)Data,
          (__int64)&v59);
      }
      v10 = CTiBus::RecreateBus(v9);
      if ( v10 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v61 = "CreateListener";
          v59 = "CUMRDPProtocolManager::CreateListener: recreate input bus failed";
          *(_DWORD *)Data = 2761;
          v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
          *(_QWORD *)cbData = "Error HResult failed";
          Type[0] = v10;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            dword_1801B76C8,
            (unsigned int)byte_18018EA99,
            v14,
            v15,
            (__int64)cbData,
            (__int64)Type,
            (__int64)&v55,
            (__int64)Data,
            (__int64)&v61,
            (__int64)&v59);
        }
        return (unsigned int)v10;
      }
      v10 = CTiDevice::WaitForDeviceReady(v9, 0x1D4C0u);
      if ( v10 < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v61 = "CreateListener";
          v59 = "CUMRDPProtocolManager::CreateListener: wait for input bus timed out again";
          *(_DWORD *)Data = 2764;
          v55 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
          *(_QWORD *)cbData = "Error HResult failed";
          Type[0] = v10;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v16,
            (unsigned int)byte_18018EA43,
            v17,
            v18,
            (__int64)cbData,
            (__int64)Type,
            (__int64)&v55,
            (__int64)Data,
            (__int64)&v61,
            (__int64)&v59);
        }
        return (unsigned int)v10;
      }
    }
    v19 = StringCchPrintfW(
            SubKey,
            0x104u,
            L"%s\\%s",
            L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
            a2);
    if ( v19 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        cbData[0] = v19;
        v57 = "StringCchPrintfW wszListenerKeyPath failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)byte_18018E951,
          v20,
          v21,
          (__int64)&v57,
          (__int64)cbData);
      }
    }
    else
    {
      v22 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      if ( v22 )
      {
        if ( (unsigned int)dword_1801B76C8 > 3 )
        {
          if ( v22 > 0 )
            v22 = (unsigned __int16)v22 | 0x80070000;
          cbData[0] = v22;
          v57 = "Can't find listener registry key in Winstations.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)byte_18018E983,
            v23,
            v24,
            (__int64)&v57,
            (__int64)cbData);
        }
      }
      else
      {
        *(_DWORD *)Data = 0;
        Type[0] = 4;
        cbData[0] = 4;
        if ( !RegQueryValueExW(hKey, L"fReverseConnectMode", 0, Type, Data, cbData)
          && Type[0] == 4
          && *(_DWORD *)Data
          && (unsigned int)dword_1801B76C8 > 4 )
        {
          v59 = (const char *)a2;
          v57 = "Found Reverse Connect Mode reg value for listener";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v25,
            (unsigned int)byte_18018E9B5,
            v26,
            v27,
            (__int64)&v57,
            (__int64)&v59);
        }
      }
      if ( hKey )
        RegCloseKey(hKey);
    }
    *a3 = 0;
    if ( !wcscmp_0(L"7A78855482A04FA781DC", a2) )
    {
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        v31 = "Creating NP Debug listener";
        v32 = &byte_18018E927;
LABEL_40:
        v57 = v31;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v28,
          (_DWORD)v32,
          v29,
          v30,
          (__int64)&v57);
        goto LABEL_41;
      }
      goto LABEL_41;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl)
      && !wcscmp_0(L"D8D584DCE21F4BD4B923", a2) )
    {
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        v31 = "Creating NP Agent listener";
        v32 = byte_18018E8FD;
        goto LABEL_40;
      }
LABEL_41:
      v10 = ATL::CComObject<CUMRDPListenerNPDebug>::CreateInstance(&v55);
      if ( v10 < 0 )
        return (unsigned int)v10;
      v33 = (struct IWRdsProtocolListener *)v55;
      v34 = (*(__int64 (__fastcall **)(const char *, unsigned __int16 *, CUMRDPProtocolManager *))(*(_QWORD *)v55 + 96LL))(
              v55,
              a2,
              this);
LABEL_54:
      v10 = v34;
      *a3 = v33 + 1;
      ((void (__fastcall *)(struct IWRdsProtocolListener *))v33[1].lpVtbl->AddRef)(&v33[1]);
      return (unsigned int)v10;
    }
    if ( !wcscmp_0(L"31C5CE94259D4006A9E4", a2) )
    {
      v55 = 0;
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        v57 = "Creating VMBus listener";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v35,
          (unsigned int)byte_18018E8D3,
          v36,
          v37,
          (__int64)&v57);
      }
      v38 = ATL::CComObject<CUMRDPListenerVMBus>::CreateInstance(&v55);
LABEL_51:
      v10 = v38;
      if ( v38 < 0 )
        return (unsigned int)v10;
      v33 = (struct IWRdsProtocolListener *)v55;
      v42 = 0;
      goto LABEL_53;
    }
    if ( !wcscmp_0(L"41C5CE94259D4006A9E4", a2) )
    {
      v55 = 0;
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        v57 = "Creating HvSocket listener";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v39,
          (unsigned int)byte_18018E8A9,
          v40,
          v41,
          (__int64)&v57);
      }
      v38 = ATL::CComObject<CUMRDPListenerHvSocket>::CreateInstance(&v55);
      goto LABEL_51;
    }
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      v57 = (const char *)a2;
      v59 = "Creating standard listener";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v39,
        (unsigned int)byte_18018E871,
        v40,
        v41,
        (__int64)&v59,
        (__int64)&v57);
    }
    v10 = ATL::CComObject<CUMRDPListenerInet>::CreateInstance(&v61);
    if ( v10 >= 0 )
    {
      memset_0(v63, 0, 0x84u);
      if ( *((_DWORD *)this + 36) )
        PAL_System_CritSecEnter(*((_QWORD *)this + 17), v43, v44);
      v45 = *((_DWORD *)this + 36) == 0;
      v46 = *(_OWORD *)((char *)this + 152);
      v47 = *(_OWORD *)((char *)this + 168);
      v64 = *((_DWORD *)this + 70);
      v63[0] = v46;
      v48 = *(_OWORD *)((char *)this + 184);
      v63[1] = v47;
      v49 = *(_OWORD *)((char *)this + 200);
      v63[2] = v48;
      v50 = *(_OWORD *)((char *)this + 216);
      v63[3] = v49;
      v51 = *(_OWORD *)((char *)this + 232);
      v63[4] = v50;
      v52 = *(_OWORD *)((char *)this + 248);
      v63[5] = v51;
      v53 = *(_OWORD *)((char *)this + 264);
      v63[6] = v52;
      v63[7] = v53;
      if ( !v45 )
        PAL_System_CritSecLeave(*((_QWORD *)this + 17));
      v33 = (struct IWRdsProtocolListener *)v61;
      v42 = v63;
LABEL_53:
      v34 = ((__int64 (__fastcall *)(struct IWRdsProtocolListener *, unsigned __int16 *, CUMRDPProtocolManager *, _OWORD *))v33->lpVtbl[1].GetSettings)(
              v33,
              a2,
              this,
              v42);
      goto LABEL_54;
    }
  }
  else
  {
    v10 = -2147467261;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      cbData[0] = 2770;
      v57 = "CUMRDPProtocolManager::CreateListener: TermInputMgr not initialized";
      v59 = "CreateListener";
      v61 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
      *(_DWORD *)Data = -2147467261;
      v55 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147467261,
        (unsigned int)byte_18018E9ED,
        (_DWORD)a3,
        a4,
        (__int64)&v55,
        (__int64)Data,
        (__int64)&v61,
        (__int64)cbData,
        (__int64)&v59,
        (__int64)&v57);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003ad40  push    rbp
0x18003ad42  push    rbx
0x18003ad43  push    rsi
0x18003ad44  push    rdi
0x18003ad45  push    r12
0x18003ad47  push    r14
0x18003ad49  push    r15
0x18003ad4b  lea     rbp, [rsp-240h]
0x18003ad53  sub     rsp, 340h
0x18003ad5a  mov     rax, cs:__security_cookie
0x18003ad61  xor     rax, rsp
0x18003ad64  mov     [rbp+270h+var_40], rax
0x18003ad6b  mov     rsi, rcx
0x18003ad6e  mov     [rbp+270h+var_2F0], 0
0x18003ad76  add     rcx, 128h
0x18003ad7d  mov     [rsp+370h+var_320], 0
0x18003ad86  mov     r12, r8
0x18003ad89  mov     [rbp+270h+hKey], 0
0x18003ad91  mov     r14, rdx
0x18003ad94  cmp     qword ptr [rcx], 0
0x18003ad98  jnz     short loc_18003AD9F
0x18003ad9a  call    ?CreateEventLogSession@?$CTraceAndLogUtil@VIRdpStateTransitionEventLogCallbacks@@@@QEAAJAEBU_GUID@@@Z; CTraceAndLogUtil<IRdpStateTransitionEventLogCallbacks>::CreateEventLogSession(_GUID const &)
0x18003ad9f  mov     eax, cs:dword_1801B76C8
0x18003ada5  mov     ebx, 4
0x18003adaa  cmp     eax, ebx
0x18003adac  jbe     short loc_18003ADDF
0x18003adae  lea     rax, aCumrdpprotocol_0; "CUMRDPProtocolManager::CreateListener D"...
0x18003adb5  mov     qword ptr [rsp+370h+cbData], r14
0x18003adba  mov     qword ptr [rsp+370h+Data], rax
0x18003adbf  lea     rdx, byte_18018EB89
0x18003adc6  lea     rax, [rsp+370h+cbData]
0x18003adcb  mov     [rsp+370h+lpcbData], rax
0x18003add0  lea     rax, [rsp+370h+Data]
0x18003add5  mov     [rsp+370h+phkResult], rax
0x18003adda  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003addf  mov     r15, [rsi+78h]
0x18003ade3  test    r15, r15
0x18003ade6  jz      loc_18003B452
0x18003adec  mov     r15, [r15+30h]
0x18003adf0  test    r15, r15
0x18003adf3  jnz     loc_18003AE8C
0x18003adf9  mov     eax, cs:dword_1801B76C8
0x18003adff  mov     ecx, 80004003h
0x18003ae04  mov     edi, ecx
0x18003ae06  cmp     eax, 2
0x18003ae09  jbe     loc_18003B4EA
0x18003ae0f  lea     rax, aCumrdpprotocol_1; "CUMRDPProtocolManager::CreateListener: "...
0x18003ae16  mov     dword ptr [rsp+370h+Data], 0AC0h
0x18003ae1e  mov     [rbp+270h+var_2F0], rax
0x18003ae22  lea     rbx, aCreatelistener; "CreateListener"
0x18003ae29  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003ae30  mov     [rsp+370h+var_320], rbx
0x18003ae35  mov     qword ptr [rsp+370h+cbData], rax
0x18003ae3a  lea     rdx, byte_18018EB33
0x18003ae41  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003ae48  mov     [rsp+370h+Type], ecx
0x18003ae4c  mov     [rsp+370h+var_300], rax
0x18003ae51  lea     rax, [rbp+270h+var_2F0]
0x18003ae55  mov     [rsp+370h+var_328], rax
0x18003ae5a  lea     rax, [rsp+370h+var_320]
0x18003ae5f  mov     [rsp+370h+var_330], rax
0x18003ae64  lea     rax, [rsp+370h+Data]
0x18003ae69  mov     [rsp+370h+var_338], rax
0x18003ae6e  lea     rax, [rsp+370h+cbData]
0x18003ae73  mov     [rsp+370h+var_340], rax
0x18003ae78  lea     rax, [rsp+370h+Type]
0x18003ae7d  mov     [rsp+370h+lpcbData], rax
0x18003ae82  lea     rax, [rsp+370h+var_300]
0x18003ae87  jmp     loc_18003B4E0
0x18003ae8c  mov     edx, 9C40h; unsigned int
0x18003ae91  mov     rcx, r15; this
0x18003ae94  call    ?WaitForDeviceReady@CTiDevice@@QEAAJK@Z; CTiDevice::WaitForDeviceReady(ulong)
0x18003ae99  mov     ecx, eax
0x18003ae9b  test    eax, eax
0x18003ae9d  jns     loc_18003B042
0x18003aea3  mov     eax, cs:dword_1801B76C8
0x18003aea9  lea     rbx, aCreatelistener; "CreateListener"
0x18003aeb0  cmp     eax, 3
0x18003aeb3  jbe     short loc_18003AF0A
0x18003aeb5  lea     rax, aCumrdpprotocol_4; "CUMRDPProtocolManager::CreateListener: "...
0x18003aebc  mov     [rsp+370h+var_300], rbx
0x18003aec1  mov     qword ptr [rsp+370h+cbData], rax
0x18003aec6  lea     rdx, byte_18018EAEF
0x18003aecd  lea     rax, aHresultFailedB; "HResult failed but continue"
0x18003aed4  mov     dword ptr [rsp+370h+Data], ecx
0x18003aed8  mov     qword ptr [rsp+370h+Type], rax
0x18003aedd  lea     rax, [rsp+370h+var_300]
0x18003aee2  mov     [rsp+370h+var_338], rax
0x18003aee7  lea     rax, [rsp+370h+Data]
0x18003aeec  mov     [rsp+370h+var_340], rax
0x18003aef1  lea     rax, [rsp+370h+cbData]
0x18003aef6  mov     [rsp+370h+lpcbData], rax
0x18003aefb  lea     rax, [rsp+370h+Type]
0x18003af00  mov     [rsp+370h+phkResult], rax
0x18003af05  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003af0a  mov     rcx, r15; this
0x18003af0d  call    ?RecreateBus@CTiBus@@QEAAJXZ; CTiBus::RecreateBus(void)
0x18003af12  mov     edi, eax
0x18003af14  test    eax, eax
0x18003af16  jns     loc_18003AFA1
0x18003af1c  mov     ecx, cs:dword_1801B76C8
0x18003af22  cmp     ecx, 2
0x18003af25  jbe     loc_18003B4EA
0x18003af2b  lea     rax, aCumrdpprotocol_3; "CUMRDPProtocolManager::CreateListener: "...
0x18003af32  mov     [rbp+270h+var_2F0], rbx
0x18003af36  mov     [rsp+370h+var_300], rax
0x18003af3b  lea     rdx, byte_18018EA99
0x18003af42  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003af49  mov     dword ptr [rsp+370h+Data], 0AC9h
0x18003af51  mov     [rsp+370h+var_320], rax
0x18003af56  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003af5d  mov     qword ptr [rsp+370h+cbData], rax
0x18003af62  lea     rax, [rsp+370h+var_300]
0x18003af67  mov     [rsp+370h+var_328], rax
0x18003af6c  lea     rax, [rbp+270h+var_2F0]
0x18003af70  mov     [rsp+370h+var_330], rax
0x18003af75  lea     rax, [rsp+370h+Data]
0x18003af7a  mov     [rsp+370h+var_338], rax
0x18003af7f  lea     rax, [rsp+370h+var_320]
0x18003af84  mov     [rsp+370h+var_340], rax
0x18003af89  lea     rax, [rsp+370h+Type]
0x18003af8e  mov     [rsp+370h+lpcbData], rax
0x18003af93  lea     rax, [rsp+370h+cbData]
0x18003af98  mov     [rsp+370h+Type], edi
0x18003af9c  jmp     loc_18003B4E0
0x18003afa1  mov     edx, 1D4C0h; unsigned int
0x18003afa6  mov     rcx, r15; this
0x18003afa9  call    ?WaitForDeviceReady@CTiDevice@@QEAAJK@Z; CTiDevice::WaitForDeviceReady(ulong)
0x18003afae  mov     edi, eax
0x18003afb0  test    eax, eax
0x18003afb2  jns     loc_18003B03D
0x18003afb8  mov     eax, cs:dword_1801B76C8
0x18003afbe  cmp     eax, 2
0x18003afc1  jbe     loc_18003B4EA
0x18003afc7  lea     rax, aCumrdpprotocol_2; "CUMRDPProtocolManager::CreateListener: "...
0x18003afce  mov     [rbp+270h+var_2F0], rbx
0x18003afd2  mov     [rsp+370h+var_300], rax
0x18003afd7  lea     rdx, byte_18018EA43
0x18003afde  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003afe5  mov     dword ptr [rsp+370h+Data], 0ACCh
0x18003afed  mov     [rsp+370h+var_320], rax
0x18003aff2  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003aff9  mov     qword ptr [rsp+370h+cbData], rax
0x18003affe  lea     rax, [rsp+370h+var_300]
0x18003b003  mov     [rsp+370h+var_328], rax
0x18003b008  lea     rax, [rbp+270h+var_2F0]
0x18003b00c  mov     [rsp+370h+var_330], rax
0x18003b011  lea     rax, [rsp+370h+Data]
0x18003b016  mov     [rsp+370h+var_338], rax
0x18003b01b  lea     rax, [rsp+370h+var_320]
0x18003b020  mov     [rsp+370h+var_340], rax
0x18003b025  lea     rax, [rsp+370h+Type]
0x18003b02a  mov     [rsp+370h+lpcbData], rax
0x18003b02f  lea     rax, [rsp+370h+cbData]
0x18003b034  mov     [rsp+370h+Type], edi
0x18003b038  jmp     loc_18003B4E0
0x18003b03d  mov     ebx, 4
0x18003b042  lea     r9, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Ter"...
0x18003b049  mov     [rsp+370h+phkResult], r14
0x18003b04e  lea     r8, aSS; "%s\\%s"
0x18003b055  mov     edx, 104h; unsigned __int64
0x18003b05a  lea     rcx, [rbp+270h+SubKey]; unsigned __int16 *
0x18003b05e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003b063  mov     ecx, eax
0x18003b065  test    eax, eax
0x18003b067  js      loc_18003B185
0x18003b06d  lea     rax, [rbp+270h+hKey]
0x18003b071  mov     r9d, 20019h; samDesired
0x18003b077  xor     r8d, r8d; ulOptions
0x18003b07a  mov     [rsp+370h+phkResult], rax; phkResult
0x18003b07f  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x18003b083  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b08a  call    cs:__imp_RegOpenKeyExW
0x18003b090  mov     ecx, eax
0x18003b092  test    eax, eax
0x18003b094  jnz     loc_18003B12C
0x18003b09a  mov     rcx, [rbp+270h+hKey]; hKey
0x18003b09e  lea     r9, [rsp+370h+Type]; lpType
0x18003b0a3  mov     dword ptr [rsp+370h+Data], eax
0x18003b0a7  lea     rdx, aFreverseconnec; "fReverseConnectMode"
0x18003b0ae  lea     rax, [rsp+370h+cbData]
0x18003b0b3  mov     [rsp+370h+Type], ebx
0x18003b0b7  mov     [rsp+370h+lpcbData], rax; lpcbData
0x18003b0bc  xor     r8d, r8d; lpReserved
0x18003b0bf  lea     rax, [rsp+370h+Data]
0x18003b0c4  mov     [rsp+370h+cbData], ebx
0x18003b0c8  mov     [rsp+370h+phkResult], rax; lpData
0x18003b0cd  call    cs:__imp_RegQueryValueExW
0x18003b0d3  test    eax, eax
0x18003b0d5  jnz     loc_18003B174
0x18003b0db  cmp     [rsp+370h+Type], ebx
0x18003b0df  jnz     loc_18003B174
0x18003b0e5  cmp     dword ptr [rsp+370h+Data], eax
0x18003b0e9  jz      loc_18003B174
0x18003b0ef  mov     eax, cs:dword_1801B76C8
0x18003b0f5  cmp     eax, ebx
0x18003b0f7  jbe     short loc_18003B174
0x18003b0f9  lea     rax, aFoundReverseCo; "Found Reverse Connect Mode reg value fo"...
0x18003b100  mov     [rsp+370h+var_300], r14
0x18003b105  mov     [rsp+370h+var_310], rax
0x18003b10a  lea     rdx, byte_18018E9B5
0x18003b111  lea     rax, [rsp+370h+var_300]
0x18003b116  mov     [rsp+370h+lpcbData], rax
0x18003b11b  lea     rax, [rsp+370h+var_310]
0x18003b120  mov     [rsp+370h+phkResult], rax
0x18003b125  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003b12a  jmp     short loc_18003B174
0x18003b12c  mov     eax, cs:dword_1801B76C8
0x18003b132  cmp     eax, 3
0x18003b135  jbe     short loc_18003B174
0x18003b137  test    ecx, ecx
0x18003b139  jle     short loc_18003B144
0x18003b13b  movzx   ecx, cx
0x18003b13e  or      ecx, 80070000h
0x18003b144  lea     rax, aCanTFindListen; "Can't find listener registry key in Win"...
0x18003b14b  mov     [rsp+370h+cbData], ecx
0x18003b14f  mov     [rsp+370h+var_310], rax
0x18003b154  lea     rdx, byte_18018E983
0x18003b15b  lea     rax, [rsp+370h+cbData]
0x18003b160  mov     [rsp+370h+lpcbData], rax
0x18003b165  lea     rax, [rsp+370h+var_310]
0x18003b16a  mov     [rsp+370h+phkResult], rax
0x18003b16f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003b174  mov     rcx, [rbp+270h+hKey]; hKey
0x18003b178  test    rcx, rcx
0x18003b17b  jz      short loc_18003B1C0
0x18003b17d  call    cs:__imp_RegCloseKey
0x18003b183  jmp     short loc_18003B1C0
0x18003b185  mov     eax, cs:dword_1801B76C8
0x18003b18b  cmp     eax, 3
0x18003b18e  jbe     short loc_18003B1C0
0x18003b190  lea     rax, aStringcchprint_0; "StringCchPrintfW wszListenerKeyPath fai"...
0x18003b197  mov     [rsp+370h+cbData], ecx
0x18003b19b  mov     [rsp+370h+var_310], rax
0x18003b1a0  lea     rdx, byte_18018E951
0x18003b1a7  lea     rax, [rsp+370h+cbData]
0x18003b1ac  mov     [rsp+370h+lpcbData], rax
0x18003b1b1  lea     rax, [rsp+370h+var_310]
0x18003b1b6  mov     [rsp+370h+phkResult], rax
0x18003b1bb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003b1c0  mov     rdx, r14; String2
0x18003b1c3  mov     qword ptr [r12], 0
0x18003b1cb  lea     rcx, a7a78855482a04f; "7A78855482A04FA781DC"
0x18003b1d2  call    wcscmp_0
0x18003b1d7  test    eax, eax
0x18003b1d9  jnz     short loc_18003B1F5
0x18003b1db  mov     eax, cs:dword_1801B76C8
0x18003b1e1  cmp     eax, ebx
0x18003b1e3  jbe     short loc_18003B244
0x18003b1e5  lea     rax, aCreatingNpDebu; "Creating NP Debug listener"
0x18003b1ec  lea     rdx, byte_18018E927
0x18003b1f3  jmp     short loc_18003B230
0x18003b1f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x18003b1fc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x18003b201  test    al, al
0x18003b203  jz      short loc_18003B277
0x18003b205  mov     rdx, r14; String2
0x18003b208  lea     rcx, aD8d584dce21f4b; "D8D584DCE21F4BD4B923"
0x18003b20f  call    wcscmp_0
0x18003b214  test    eax, eax
0x18003b216  jnz     short loc_18003B277
0x18003b218  mov     eax, cs:dword_1801B76C8
0x18003b21e  cmp     eax, ebx
0x18003b220  jbe     short loc_18003B244
0x18003b222  lea     rax, aCreatingNpAgen; "Creating NP Agent listener"
0x18003b229  lea     rdx, byte_18018E8FD
0x18003b230  mov     [rsp+370h+var_310], rax
0x18003b235  lea     rax, [rsp+370h+var_310]
0x18003b23a  mov     [rsp+370h+phkResult], rax
0x18003b23f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003b244  lea     rcx, [rsp+370h+var_320]
0x18003b249  call    ?CreateInstance@?$CComObject@VCUMRDPListenerNPDebug@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUMRDPListenerNPDebug>::CreateInstance(ATL::CComObject<CUMRDPListenerNPDebug> * *)
0x18003b24e  mov     edi, eax
0x18003b250  test    eax, eax
0x18003b252  js      loc_18003B4EA
0x18003b258  mov     rbx, [rsp+370h+var_320]
0x18003b25d  mov     r8, rsi
0x18003b260  mov     rdx, r14
0x18003b263  mov     rcx, rbx
0x18003b266  mov     rax, [rbx]
0x18003b269  mov     rax, [rax+60h]
0x18003b26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b272  jmp     loc_18003B344
0x18003b277  mov     rdx, r14; String2
0x18003b27a  lea     rcx, a31c5ce94259d40; "31C5CE94259D4006A9E4"
0x18003b281  call    wcscmp_0
0x18003b286  test    eax, eax
0x18003b288  jnz     short loc_18003B2CB
0x18003b28a  mov     eax, cs:dword_1801B76C8
0x18003b290  mov     [rsp+370h+var_320], 0
0x18003b299  cmp     eax, ebx
0x18003b29b  jbe     short loc_18003B2BF
0x18003b29d  lea     rax, aCreatingVmbusL; "Creating VMBus listener"
0x18003b2a4  mov     [rsp+370h+var_310], rax
0x18003b2a9  lea     rdx, byte_18018E8D3
0x18003b2b0  lea     rax, [rsp+370h+var_310]
0x18003b2b5  mov     [rsp+370h+phkResult], rax
0x18003b2ba  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003b2bf  lea     rcx, [rsp+370h+var_320]
0x18003b2c4  call    ?CreateInstance@?$CComObject@VCUMRDPListenerVMBus@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CUMRDPListenerVMBus>::CreateInstance(ATL::CComObject<CUMRDPListenerVMBus> * *)
  ... truncated ...
```
