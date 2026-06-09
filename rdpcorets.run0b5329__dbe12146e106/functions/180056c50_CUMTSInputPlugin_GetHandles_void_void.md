# CUMTSInputPlugin::GetHandles(void * *,void * *)

- ea: `0x180056c50`
- end: `0x180057542`
- name: `?GetHandles@CUMTSInputPlugin@@UEAAJPEAPEAX0@Z`
- size: `2290`
- prototype: `__int64 __fastcall(CUMTSInputPlugin *__hidden this, void **, void **)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800014d8`
- `0x1800015f0`
- `0x1800071c0`
- `0x1800071f0`
- `0x180009628`
- `0x18000ee00`
- `0x18000f784`
- `0x180012200`
- `0x1800180a8`
- `0x180023b4c`
- `0x18002ee24`
- `0x18002f734`
- `0x1800568e0`
- `0x180056c50`
- `0x180057910`
- `0x180057a70`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800574f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005750f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800574f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005750f`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180056c8c`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180056c8c`

## string_xrefs

- `0x180056d0c`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umtsinputplugin.cpp`
- `0x180057446`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umtsinputplugin.cpp`
- `0x180057495`: `clientcore\termsrv\rdp_bin\win\rdpcorets\umtsinputplugin.cpp`
- `0x18005742e`: `Mouse or Keyboard PDO not created`
- `0x180056cd5`: `First attempt to m_pKeyboard->WaitForDeviceReady started`
- `0x180056d36`: `First attempt to m_pKeyboard->WaitForDeviceReady failed, retrying`
- `0x180056eeb`: `CreateInputDevices failed`
- `0x1800572bf`: `CreateInputDevices failed`
- `0x180056f15`: `Keyboard PDO not created`
- `0x180056f8b`: `Second attempt to m_pKeyboard->WaitForDeviceReady started`
- `0x180056fc6`: `Second attempt to m_pKeyboard->WaitForDeviceReady completed`
- `0x180057035`: `First attempt to m_pKeyboard->WaitForDeviceReady completed successfully`
- `0x1800570e3`: `Failed to get keyboard Win32K read handle`
- `0x180057160`: `First attempt to m_pMouse->WaitForDeviceReady started`
- `0x1800571ae`: `First attempt to m_pMouse->WaitForDeviceReady failed, retrying`
- `0x1800572ed`: `Mouse PDO not created`
- `0x18005730c`: `Second attempt to m_pMouse->WaitForDeviceReady started`
- `0x180057347`: `Second attempt to m_pMouse->WaitForDeviceReady completed`
- `0x1800573b6`: `First attempt to m_pMouse->WaitForDeviceReady completed successfully`
- `0x1800573fa`: `Failed to get mouse read handle`

## pseudocode

```c
__int64 __fastcall CUMTSInputPlugin::GetHandles(CUMTSInputPlugin *this, void **a2, void **a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // r9d
  CTiBus **v9; // rcx
  int v10; // eax
  CUMTSInputPlugin *v11; // rcx
  int v12; // r8d
  int v13; // r9d
  int v14; // ebx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rcx
  int InputDevices; // ebx
  __int64 v19; // rax
  __int16 *v20; // rdx
  const char *v21; // rax
  const char *v22; // rax
  __int16 *v23; // rdx
  CUMTSInputPlugin *v24; // rcx
  int v25; // r8d
  int v26; // r9d
  int v27; // eax
  int v28; // r8d
  int v29; // r9d
  __int64 v30; // rdx
  int v31; // eax
  CUMTSInputPlugin *v32; // rcx
  int v33; // r8d
  int v34; // r9d
  int v35; // ebx
  __int64 v36; // rax
  CUMTSInputPlugin *v37; // rcx
  int v38; // r8d
  int v39; // r9d
  __int64 v40; // rdx
  __int64 v41; // r8
  const char *v43; // [rsp+50h] [rbp-28h] BYREF
  const char *v44; // [rsp+58h] [rbp-20h] BYREF
  const char *v45; // [rsp+60h] [rbp-18h] BYREF
  char *v46; // [rsp+68h] [rbp-10h] BYREF
  const char *v47; // [rsp+C0h] [rbp+48h] BYREF
  const char *v48; // [rsp+C8h] [rbp+50h] BYREF
  struct IUnknown *v49; // [rsp+D0h] [rbp+58h] BYREF
  const char *v50; // [rsp+D8h] [rbp+60h] BYREF

  v49 = 0;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v49);
  v9 = (CTiBus **)((char *)this + 120);
  v46 = (char *)this + 120;
  if ( *((_DWORD *)this + 32) )
    PAL_System_CritSecEnter(*v9, v6, v7);
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( !a2 || !a3 )
  {
    InputDevices = -2147024809;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      LODWORD(v47) = 737;
      v50 = "invalid argument";
      v45 = "GetHandles";
      v43 = "Error HResult failed";
      v44 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umtsinputplugin.cpp";
      LODWORD(v48) = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)v9,
        (unsigned int)&dword_180198E54,
        v7,
        v8,
        (__int64)&v43,
        (__int64)&v48,
        (__int64)&v44,
        (__int64)&v47,
        (__int64)&v45,
        (__int64)&v50);
    }
    if ( !a2 )
      goto LABEL_91;
    goto LABEL_89;
  }
  if ( *((_QWORD *)this + 12) && *((_QWORD *)this + 13) )
  {
    if ( (unsigned int)dword_1801B76C8 > 5 )
    {
      v47 = "First attempt to m_pKeyboard->WaitForDeviceReady started";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v9,
        (unsigned int)&dword_180198DDC,
        v7,
        v8,
        (__int64)&v47);
    }
    v10 = CTiDevice::WaitForDeviceReady(*((CTiDevice **)this + 12), 0x4E20u);
    v14 = v10;
    if ( v10 >= 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 5 )
      {
        v47 = "First attempt to m_pKeyboard->WaitForDeviceReady completed successfully";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v11,
          (unsigned int)&unk_180198BD0,
          v12,
          v13,
          (__int64)&v47);
      }
    }
    else
    {
      CUMTSInputPlugin::TraceDeviceProblemDetails(v11, *((struct CTiDevice **)this + 12), v10);
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v50 = "GetHandles";
        v44 = "First attempt to m_pKeyboard->WaitForDeviceReady failed, retrying";
        LODWORD(v47) = 754;
        v43 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umtsinputplugin.cpp";
        LODWORD(v48) = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_1801B76C8,
          (unsigned int)word_180198D92,
          v15,
          v16,
          (__int64)&v44,
          (__int64)&v48,
          (__int64)&v43,
          (__int64)&v47,
          (__int64)&v50);
      }
      v17 = *((_QWORD *)this + 10);
      if ( !v17 )
      {
        InputDevices = -2147467261;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v44 = "GetHandles";
          v50 = "m_pTiMgr is NULL";
          LODWORD(v47) = 759;
          v45 = "Error HResult failed";
          v43 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umtsinputplugin.cpp";
          LODWORD(v48) = -2147467261;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            0,
            (unsigned int)&unk_180198D40,
            v15,
            v16,
            (__int64)&v45,
            (__int64)&v48,
            (__int64)&v43,
            (__int64)&v47,
            (__int64)&v44,
            (__int64)&v50);
        }
        goto LABEL_89;
      }
      CTiBus::RemoveDevice(*(CTiBus **)(v17 + 48), *((struct CTiDevice **)this + 12), v15, v16);
      v19 = *((_QWORD *)this + 10);
      *((_QWORD *)this + 12) = 0;
      InputDevices = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))(v19 + 32))(
                       *(_QWORD *)(v19 + 32),
                       &IID_IUnknown,
                       &v49);
      if ( InputDevices < 0 )
      {
        LODWORD(v9) = dword_1801B76C8;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_89;
        LODWORD(v47) = 764;
        v20 = &word_180198CEE;
LABEL_22:
        v21 = "QI for TermInputMgr failed";
LABEL_23:
        LODWORD(v48) = InputDevices;
        goto LABEL_24;
      }
      InputDevices = CUMTSInputPlugin::CreateInputDevices(this, *((_DWORD *)this + 28), v49, 0);
      if ( InputDevices < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_89;
        v21 = "CreateInputDevices failed";
        LODWORD(v47) = 766;
        v20 = (__int16 *)&dword_180198C9C;
        goto LABEL_23;
      }
      if ( !*((_QWORD *)this + 12) )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
        {
LABEL_33:
          InputDevices = -2147467261;
          goto LABEL_89;
        }
        v22 = "Keyboard PDO not created";
        LODWORD(v47) = 770;
        v23 = word_180198C4A;
LABEL_32:
        v50 = v22;
        v43 = "Error HResult failed";
        LODWORD(v48) = -2147467261;
        v44 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umtsinputplugin.cpp";
        v45 = "GetHandles";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)v9,
          (_DWORD)v23,
          v7,
          v8,
          (__int64)&v43,
          (__int64)&v48,
          (__int64)&v44,
          (__int64)&v47,
          (__int64)&v45,
          (__int64)&v50);
        goto LABEL_33;
      }
      if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        v47 = "Second attempt to m_pKeyboard->WaitForDeviceReady started";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v9,
          (unsigned int)&dword_180198C24,
          v7,
          v8,
          (__int64)&v47);
      }
      InputDevices = CTiDevice::WaitForDeviceReady(*((CTiDevice **)this + 12), 0x4E20u);
      if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        LODWORD(v47) = InputDevices;
        v48 = "Second attempt to m_pKeyboard->WaitForDeviceReady completed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v24,
          (unsigned int)&word_180198BF6,
          v25,
          v26,
          (__int64)&v48,
          (__int64)&v47);
      }
      if ( InputDevices < 0 )
      {
        CUMTSInputPlugin::TraceDeviceProblemDetails(v24, *((struct CTiDevice **)this + 12), InputDevices);
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_89;
        v21 = "Keyboard not online";
        LODWORD(v47) = 784;
        v20 = &word_180198B7E;
        goto LABEL_23;
      }
    }
    if ( !*((_DWORD *)this + 44) )
    {
      v27 = CUMTSInputPlugin::SetIndicators((CUMTSInputPlugin *)((char *)this - 16));
      if ( v27 < 0 && (unsigned int)dword_1801B76C8 > 3 )
      {
        LODWORD(v47) = v27;
        v48 = "GetHandles";
        v50 = "GetHandles: SetIndicators failed, Not fatal";
        v45 = "HResult failed but continue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_1801B76C8,
          (unsigned int)&word_180198B3E,
          v28,
          v29,
          (__int64)&v45,
          (__int64)&v50,
          (__int64)&v47,
          (__int64)&v48);
      }
    }
    InputDevices = CTiDevice::GetWin32KReadHandle(*((CTiDevice **)this + 12), a2);
    if ( InputDevices < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_89;
      v21 = "Failed to get keyboard Win32K read handle";
      LODWORD(v47) = 796;
      v20 = (__int16 *)&dword_180198AEC;
      goto LABEL_23;
    }
    InputDevices = CUMTSInputPlugin::SendIndicatorstoKeyboard((CUMTSInputPlugin *)((char *)this - 16));
    if ( InputDevices < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_89;
      v21 = "SendIndicatorstoKeyboard()";
      LODWORD(v47) = 799;
      v20 = word_180198A9A;
      goto LABEL_23;
    }
    if ( v49 )
    {
      TCntPtr<IRdpSQMLogger>::SafeRelease(&v49, v30, v7);
      v49 = 0;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&v49);
    }
    if ( (unsigned int)dword_1801B76C8 > 5 )
    {
      v47 = "First attempt to m_pMouse->WaitForDeviceReady started";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (_DWORD)v9,
        (unsigned int)&dword_180198A74,
        v7,
        v8,
        (__int64)&v47);
    }
    v31 = CTiDevice::WaitForDeviceReady(*((CTiDevice **)this + 13), 0x4E20u);
    v35 = v31;
    if ( v31 >= 0 )
    {
      if ( (unsigned int)dword_1801B76C8 > 5 )
      {
        v47 = "First attempt to m_pMouse->WaitForDeviceReady completed successfully";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v32,
          (unsigned int)&unk_180198868,
          v33,
          v34,
          (__int64)&v47);
      }
    }
    else
    {
      CUMTSInputPlugin::TraceDeviceProblemDetails(v32, *((struct CTiDevice **)this + 13), v31);
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        v50 = "GetHandles";
        v44 = "First attempt to m_pMouse->WaitForDeviceReady failed, retrying";
        LODWORD(v47) = 810;
        v45 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umtsinputplugin.cpp";
        LODWORD(v48) = v35;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          dword_1801B76C8,
          (unsigned int)word_180198A2A,
          v7,
          v8,
          (__int64)&v44,
          (__int64)&v48,
          (__int64)&v45,
          (__int64)&v47,
          (__int64)&v50);
      }
      v9 = (CTiBus **)*((_QWORD *)this + 10);
      if ( !v9 )
      {
        InputDevices = -2147467261;
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_89;
        v21 = "m_pTiMgr is NULL";
        LODWORD(v47) = 815;
        LODWORD(v48) = -2147467261;
        v20 = (__int16 *)&unk_1801989D8;
        goto LABEL_24;
      }
      CTiBus::RemoveDevice(v9[6], *((struct CTiDevice **)this + 13), v7, v8);
      v36 = *((_QWORD *)this + 10);
      *((_QWORD *)this + 13) = 0;
      InputDevices = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IUnknown **))(v36 + 32))(
                       *(_QWORD *)(v36 + 32),
                       &IID_IUnknown,
                       &v49);
      if ( InputDevices < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_89;
        LODWORD(v47) = 820;
        v20 = &word_180198986;
        goto LABEL_22;
      }
      InputDevices = CUMTSInputPlugin::CreateInputDevices(this, *((_DWORD *)this + 28), v49, 0);
      if ( InputDevices < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_89;
        v21 = "CreateInputDevices failed";
        LODWORD(v47) = 822;
        v20 = (__int16 *)&dword_180198934;
        goto LABEL_23;
      }
      if ( !*((_QWORD *)this + 13) )
      {
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_33;
        v22 = "Mouse PDO not created";
        LODWORD(v47) = 826;
        v23 = word_1801988E2;
        goto LABEL_32;
      }
      if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        v47 = "Second attempt to m_pMouse->WaitForDeviceReady started";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (_DWORD)v9,
          (unsigned int)&dword_1801988BC,
          v7,
          v8,
          (__int64)&v47);
      }
      InputDevices = CTiDevice::WaitForDeviceReady(*((CTiDevice **)this + 13), 0x4E20u);
      if ( (unsigned int)dword_1801B76C8 > 3 )
      {
        LODWORD(v47) = InputDevices;
        v48 = "Second attempt to m_pMouse->WaitForDeviceReady completed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v37,
          (unsigned int)&word_18019888E,
          v38,
          v39,
          (__int64)&v48,
          (__int64)&v47);
      }
      if ( InputDevices < 0 )
      {
        CUMTSInputPlugin::TraceDeviceProblemDetails(v37, *((struct CTiDevice **)this + 13), InputDevices);
        if ( (unsigned int)dword_1801B76C8 <= 2 )
          goto LABEL_89;
        v21 = "Mouse not online";
        LODWORD(v47) = 840;
        v20 = &word_180198816;
        goto LABEL_23;
      }
    }
    InputDevices = CTiDevice::GetWin32KReadHandle(*((CTiDevice **)this + 13), a3);
    if ( InputDevices >= 0 )
      goto LABEL_94;
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_89;
    v21 = "Failed to get mouse read handle";
    LODWORD(v47) = 843;
    v20 = (__int16 *)&dword_1801987C4;
    goto LABEL_23;
  }
  InputDevices = -2147467261;
  if ( (unsigned int)dword_1801B76C8 <= 2 )
    goto LABEL_89;
  v21 = "Mouse or Keyboard PDO not created";
  LODWORD(v47) = 744;
  LODWORD(v48) = -2147467261;
  v20 = word_180198E02;
LABEL_24:
  v50 = v21;
  v43 = "Error HResult failed";
  v45 = "GetHandles";
  v44 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umtsinputplugin.cpp";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
    (_DWORD)v9,
    (_DWORD)v20,
    v7,
    v8,
    (__int64)&v43,
    (__int64)&v48,
    (__int64)&v44,
    (__int64)&v47,
    (__int64)&v45,
    (__int64)&v50);
LABEL_89:
  if ( *a2 )
  {
    CloseHandle(*a2);
    *a2 = 0;
  }
LABEL_91:
  if ( a3 && *a3 )
  {
    CloseHandle(*a3);
    *a3 = 0;
  }
LABEL_94:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v46);
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v49, v40, v41);
  return (unsigned int)InputDevices;
}

```

## disassembly

```asm
0x180056c50  push    rbp
0x180056c52  push    rbx
0x180056c53  push    rsi
0x180056c54  push    rdi
0x180056c55  push    r12
0x180056c57  push    r13
0x180056c59  push    r14
0x180056c5b  push    r15
0x180056c5d  mov     rbp, rsp
0x180056c60  sub     rsp, 78h
0x180056c64  mov     rdi, rcx
0x180056c67  xor     ebx, ebx
0x180056c69  lea     rcx, [rbp+arg_10]
0x180056c6d  mov     [rbp+arg_10], rbx
0x180056c71  mov     r12, r8
0x180056c74  mov     r13, rdx
0x180056c77  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180056c7c  lea     rcx, [rdi+78h]
0x180056c80  mov     [rbp+var_10], rcx
0x180056c84  cmp     [rcx+8], ebx
0x180056c87  jz      short loc_180056C92
0x180056c89  mov     rcx, [rcx]
0x180056c8c  call    cs:__imp_PAL_System_CritSecEnter
0x180056c92  test    r13, r13
0x180056c95  jz      short loc_180056C9B
0x180056c97  mov     [r13+0], rbx
0x180056c9b  test    r12, r12
0x180056c9e  jz      short loc_180056CA4
0x180056ca0  mov     [r12], rbx
0x180056ca4  test    r13, r13
0x180056ca7  jz      loc_180057459
0x180056cad  test    r12, r12
0x180056cb0  jz      loc_180057459
0x180056cb6  cmp     [rdi+60h], rbx
0x180056cba  jz      loc_180057414
0x180056cc0  cmp     [rdi+68h], rbx
0x180056cc4  jz      loc_180057414
0x180056cca  mov     eax, cs:dword_1801B76C8
0x180056cd0  cmp     eax, 5
0x180056cd3  jbe     short loc_180056CF5
0x180056cd5  lea     rax, aFirstAttemptTo_3; "First attempt to m_pKeyboard->WaitForDe"...
0x180056cdc  mov     [rbp+arg_0], rax
0x180056ce0  lea     rdx, dword_180198DDC
0x180056ce7  lea     rax, [rbp+arg_0]
0x180056ceb  mov     [rsp+78h+var_58], rax
0x180056cf0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180056cf5  mov     rcx, [rdi+60h]; this
0x180056cf9  mov     edx, 4E20h; unsigned int
0x180056cfe  call    ?WaitForDeviceReady@CTiDevice@@QEAAJK@Z; CTiDevice::WaitForDeviceReady(ulong)
0x180056d03  lea     r14, aGethandles; "GetHandles"
0x180056d0a  mov     ebx, eax
0x180056d0c  lea     r15, aClientcoreTerm_2; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x180056d13  mov     esi, 2
0x180056d18  test    eax, eax
0x180056d1a  jns     loc_18005702A
0x180056d20  mov     rdx, [rdi+60h]; struct CTiDevice *
0x180056d24  mov     r8d, eax; int
0x180056d27  call    ?TraceDeviceProblemDetails@CUMTSInputPlugin@@IEAAXPEAVCTiDevice@@J@Z; CUMTSInputPlugin::TraceDeviceProblemDetails(CTiDevice *,long)
0x180056d2c  mov     ecx, cs:dword_1801B76C8
0x180056d32  cmp     ecx, esi
0x180056d34  jbe     short loc_180056D8C
0x180056d36  lea     rax, aFirstAttemptTo_1; "First attempt to m_pKeyboard->WaitForDe"...
0x180056d3d  mov     [rbp+arg_18], r14
0x180056d41  mov     [rbp+var_20], rax
0x180056d45  lea     rdx, word_180198D92
0x180056d4c  lea     rax, [rbp+arg_18]
0x180056d50  mov     dword ptr [rbp+arg_0], 2F2h
0x180056d57  mov     [rsp+78h+var_38], rax
0x180056d5c  lea     rax, [rbp+arg_0]
0x180056d60  mov     [rsp+78h+var_40], rax
0x180056d65  lea     rax, [rbp+var_28]
0x180056d69  mov     [rsp+78h+var_48], rax
0x180056d6e  lea     rax, [rbp+arg_8]
0x180056d72  mov     [rsp+78h+var_50], rax
0x180056d77  lea     rax, [rbp+var_20]
0x180056d7b  mov     [rsp+78h+var_58], rax
0x180056d80  mov     [rbp+var_28], r15
0x180056d84  mov     dword ptr [rbp+arg_8], ebx
0x180056d87  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180056d8c  mov     rcx, [rdi+50h]
0x180056d90  test    rcx, rcx
0x180056d93  jnz     short loc_180056E0F
0x180056d95  mov     eax, cs:dword_1801B76C8
0x180056d9b  mov     edi, 80004003h
0x180056da0  mov     ebx, edi
0x180056da2  cmp     eax, esi
0x180056da4  jbe     loc_1800574EA
0x180056daa  lea     rax, aMPtimgrIsNull; "m_pTiMgr is NULL"
0x180056db1  mov     [rbp+var_20], r14
0x180056db5  mov     [rbp+arg_18], rax
0x180056db9  lea     rdx, unk_180198D40
0x180056dc0  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180056dc7  mov     dword ptr [rbp+arg_0], 2F7h
0x180056dce  mov     [rbp+var_18], rax
0x180056dd2  lea     rax, [rbp+arg_18]
0x180056dd6  mov     [rsp+78h+var_30], rax
0x180056ddb  lea     rax, [rbp+var_20]
0x180056ddf  mov     [rsp+78h+var_38], rax
0x180056de4  lea     rax, [rbp+arg_0]
0x180056de8  mov     [rsp+78h+var_40], rax
0x180056ded  lea     rax, [rbp+var_28]
0x180056df1  mov     [rsp+78h+var_48], rax
0x180056df6  lea     rax, [rbp+arg_8]
0x180056dfa  mov     [rsp+78h+var_50], rax
0x180056dff  lea     rax, [rbp+var_18]
0x180056e03  mov     [rbp+var_28], r15
0x180056e07  mov     dword ptr [rbp+arg_8], edi
0x180056e0a  jmp     loc_180056EB6
0x180056e0f  mov     rdx, [rdi+60h]; struct CTiDevice *
0x180056e13  mov     rcx, [rcx+30h]; this
0x180056e17  call    ?RemoveDevice@CTiBus@@QEAAXPEAVCTiDevice@@HH@Z; CTiBus::RemoveDevice(CTiDevice *,int,int)
0x180056e1c  mov     rax, [rdi+50h]
0x180056e20  lea     r8, [rbp+arg_10]
0x180056e24  mov     qword ptr [rdi+60h], 0
0x180056e2c  lea     rdx, IID_IUnknown
0x180056e33  mov     rcx, [rax+20h]
0x180056e37  mov     rax, [rcx]
0x180056e3a  mov     rax, [rax]
0x180056e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e42  mov     ebx, eax
0x180056e44  test    eax, eax
0x180056e46  jns     short loc_180056EC5
0x180056e48  mov     ecx, cs:dword_1801B76C8
0x180056e4e  cmp     ecx, esi
0x180056e50  jbe     loc_1800574EA
0x180056e56  mov     dword ptr [rbp+arg_0], 2FCh
0x180056e5d  lea     rdx, word_180198CEE
0x180056e64  lea     rax, aQiForTerminput; "QI for TermInputMgr failed"
0x180056e6b  mov     dword ptr [rbp+arg_8], ebx
0x180056e6e  mov     [rbp+arg_18], rax
0x180056e72  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180056e79  mov     [rbp+var_28], rax
0x180056e7d  lea     rax, [rbp+arg_18]
0x180056e81  mov     [rsp+78h+var_30], rax
0x180056e86  lea     rax, [rbp+var_18]
0x180056e8a  mov     [rsp+78h+var_38], rax
0x180056e8f  lea     rax, [rbp+arg_0]
0x180056e93  mov     [rsp+78h+var_40], rax
0x180056e98  lea     rax, [rbp+var_20]
0x180056e9c  mov     [rsp+78h+var_48], rax
0x180056ea1  lea     rax, [rbp+arg_8]
0x180056ea5  mov     [rsp+78h+var_50], rax
0x180056eaa  lea     rax, [rbp+var_28]
0x180056eae  mov     [rbp+var_18], r14
0x180056eb2  mov     [rbp+var_20], r15
0x180056eb6  mov     [rsp+78h+var_58], rax
0x180056ebb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180056ec0  jmp     loc_1800574EA
0x180056ec5  mov     r8, [rbp+arg_10]; struct IUnknown *
0x180056ec9  xor     r9d, r9d; int
0x180056ecc  mov     edx, [rdi+70h]; unsigned int
0x180056ecf  mov     rcx, rdi; this
0x180056ed2  call    ?CreateInputDevices@CUMTSInputPlugin@@UEAAJKPEAUIUnknown@@H@Z; CUMTSInputPlugin::CreateInputDevices(ulong,IUnknown *,int)
0x180056ed7  mov     ebx, eax
0x180056ed9  test    eax, eax
0x180056edb  mov     eax, cs:dword_1801B76C8
0x180056ee1  jns     short loc_180056F05
0x180056ee3  cmp     eax, esi
0x180056ee5  jbe     loc_1800574EA
0x180056eeb  lea     rax, aCreateinputdev; "CreateInputDevices failed"
0x180056ef2  mov     dword ptr [rbp+arg_0], 2FEh
0x180056ef9  lea     rdx, dword_180198C9C
0x180056f00  jmp     loc_180056E6B
0x180056f05  cmp     qword ptr [rdi+60h], 0
0x180056f0a  jnz     short loc_180056F86
0x180056f0c  mov     edi, 80004003h
0x180056f11  cmp     eax, esi
0x180056f13  jbe     short loc_180056F7F
0x180056f15  lea     rax, aKeyboardPdoNot; "Keyboard PDO not created"
0x180056f1c  mov     dword ptr [rbp+arg_0], 302h
0x180056f23  lea     rdx, word_180198C4A
0x180056f2a  mov     [rbp+arg_18], rax
0x180056f2e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180056f35  mov     [rbp+var_28], rax
0x180056f39  lea     rax, [rbp+arg_18]
0x180056f3d  mov     [rsp+78h+var_30], rax
0x180056f42  lea     rax, [rbp+var_18]
0x180056f46  mov     [rsp+78h+var_38], rax
0x180056f4b  lea     rax, [rbp+arg_0]
0x180056f4f  mov     [rsp+78h+var_40], rax
0x180056f54  lea     rax, [rbp+var_20]
0x180056f58  mov     [rsp+78h+var_48], rax
0x180056f5d  lea     rax, [rbp+arg_8]
0x180056f61  mov     [rsp+78h+var_50], rax
0x180056f66  lea     rax, [rbp+var_28]
0x180056f6a  mov     [rsp+78h+var_58], rax
0x180056f6f  mov     dword ptr [rbp+arg_8], edi
0x180056f72  mov     [rbp+var_20], r15
0x180056f76  mov     [rbp+var_18], r14
0x180056f7a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180056f7f  mov     ebx, edi
0x180056f81  jmp     loc_1800574EA
0x180056f86  cmp     eax, 3
0x180056f89  jbe     short loc_180056FAB
0x180056f8b  lea     rax, aSecondAttemptT_2; "Second attempt to m_pKeyboard->WaitForD"...
0x180056f92  mov     [rbp+arg_0], rax
0x180056f96  lea     rdx, dword_180198C24
0x180056f9d  lea     rax, [rbp+arg_0]
0x180056fa1  mov     [rsp+78h+var_58], rax
0x180056fa6  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180056fab  mov     rcx, [rdi+60h]; this
0x180056faf  mov     edx, 4E20h; unsigned int
0x180056fb4  call    ?WaitForDeviceReady@CTiDevice@@QEAAJK@Z; CTiDevice::WaitForDeviceReady(ulong)
0x180056fb9  mov     ebx, eax
0x180056fbb  mov     eax, cs:dword_1801B76C8
0x180056fc1  cmp     eax, 3
0x180056fc4  jbe     short loc_180056FF2
0x180056fc6  lea     rax, aSecondAttemptT_0; "Second attempt to m_pKeyboard->WaitForD"...
0x180056fcd  mov     dword ptr [rbp+arg_0], ebx
0x180056fd0  mov     [rbp+arg_8], rax
0x180056fd4  lea     rdx, word_180198BF6
0x180056fdb  lea     rax, [rbp+arg_0]
0x180056fdf  mov     [rsp+78h+var_50], rax
0x180056fe4  lea     rax, [rbp+arg_8]
0x180056fe8  mov     [rsp+78h+var_58], rax
0x180056fed  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180056ff2  test    ebx, ebx
0x180056ff4  jns     short loc_180057055
0x180056ff6  mov     rdx, [rdi+60h]; struct CTiDevice *
0x180056ffa  mov     r8d, ebx; int
0x180056ffd  call    ?TraceDeviceProblemDetails@CUMTSInputPlugin@@IEAAXPEAVCTiDevice@@J@Z; CUMTSInputPlugin::TraceDeviceProblemDetails(CTiDevice *,long)
0x180057002  mov     eax, cs:dword_1801B76C8
0x180057008  cmp     eax, esi
0x18005700a  jbe     loc_1800574EA
0x180057010  lea     rax, aKeyboardNotOnl; "Keyboard not online"
0x180057017  mov     dword ptr [rbp+arg_0], 310h
0x18005701e  lea     rdx, word_180198B7E
0x180057025  jmp     loc_180056E6B
0x18005702a  mov     eax, cs:dword_1801B76C8
0x180057030  cmp     eax, 5
0x180057033  jbe     short loc_180057055
0x180057035  lea     rax, aFirstAttemptTo_2; "First attempt to m_pKeyboard->WaitForDe"...
0x18005703c  mov     [rbp+arg_0], rax
0x180057040  lea     rdx, unk_180198BD0
0x180057047  lea     rax, [rbp+arg_0]
0x18005704b  mov     [rsp+78h+var_58], rax
0x180057050  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180057055  cmp     dword ptr [rdi+0B0h], 0
0x18005705c  jnz     short loc_1800570C3
0x18005705e  lea     rcx, [rdi-10h]; this
0x180057062  call    ?SetIndicators@CUMTSInputPlugin@@IEAAJXZ; CUMTSInputPlugin::SetIndicators(void)
0x180057067  test    eax, eax
0x180057069  jns     short loc_1800570C3
0x18005706b  mov     ecx, cs:dword_1801B76C8
0x180057071  cmp     ecx, 3
0x180057074  jbe     short loc_1800570C3
0x180057076  mov     dword ptr [rbp+arg_0], eax
0x180057079  lea     rdx, word_180198B3E
0x180057080  lea     rax, aGethandlesSeti; "GetHandles: SetIndicators failed, Not f"...
0x180057087  mov     [rbp+arg_8], r14
0x18005708b  mov     [rbp+arg_18], rax
0x18005708f  lea     rax, aHresultFailedB; "HResult failed but continue"
0x180057096  mov     [rbp+var_18], rax
0x18005709a  lea     rax, [rbp+arg_8]
0x18005709e  mov     [rsp+78h+var_40], rax
0x1800570a3  lea     rax, [rbp+arg_0]
0x1800570a7  mov     [rsp+78h+var_48], rax
0x1800570ac  lea     rax, [rbp+arg_18]
0x1800570b0  mov     [rsp+78h+var_50], rax
0x1800570b5  lea     rax, [rbp+var_18]
0x1800570b9  mov     [rsp+78h+var_58], rax
0x1800570be  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800570c3  mov     rcx, [rdi+60h]; this
0x1800570c7  mov     rdx, r13; void **
0x1800570ca  call    ?GetWin32KReadHandle@CTiDevice@@QEAAJPEAPEAX@Z; CTiDevice::GetWin32KReadHandle(void * *)
0x1800570cf  mov     ebx, eax
0x1800570d1  test    eax, eax
0x1800570d3  jns     short loc_1800570FD
0x1800570d5  mov     eax, cs:dword_1801B76C8
0x1800570db  cmp     eax, esi
0x1800570dd  jbe     loc_1800574EA
0x1800570e3  lea     rax, aFailedToGetKey; "Failed to get keyboard Win32K read hand"...
0x1800570ea  mov     dword ptr [rbp+arg_0], 31Ch
0x1800570f1  lea     rdx, dword_180198AEC
0x1800570f8  jmp     loc_180056E6B
0x1800570fd  lea     rcx, [rdi-10h]; this
0x180057101  call    ?SendIndicatorstoKeyboard@CUMTSInputPlugin@@IEAAJXZ; CUMTSInputPlugin::SendIndicatorstoKeyboard(void)
0x180057106  mov     ebx, eax
0x180057108  test    eax, eax
0x18005710a  jns     short loc_180057134
0x18005710c  mov     eax, cs:dword_1801B76C8
0x180057112  cmp     eax, esi
0x180057114  jbe     loc_1800574EA
0x18005711a  lea     rax, aSendindicators; "SendIndicatorstoKeyboard()"
0x180057121  mov     dword ptr [rbp+arg_0], 31Fh
0x180057128  lea     rdx, word_180198A9A
0x18005712f  jmp     loc_180056E6B
0x180057134  cmp     [rbp+arg_10], 0
0x180057139  jz      short loc_180057155
0x18005713b  lea     rcx, [rbp+arg_10]
0x18005713f  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x180057144  lea     rcx, [rbp+arg_10]
0x180057148  mov     [rbp+arg_10], 0
0x180057150  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x180057155  mov     eax, cs:dword_1801B76C8
0x18005715b  cmp     eax, 5
0x18005715e  jbe     short loc_180057180
0x180057160  lea     rax, aFirstAttemptTo_4; "First attempt to m_pMouse->WaitForDevic"...
0x180057167  mov     [rbp+arg_0], rax
0x18005716b  lea     rdx, dword_180198A74
  ... truncated ...
```
