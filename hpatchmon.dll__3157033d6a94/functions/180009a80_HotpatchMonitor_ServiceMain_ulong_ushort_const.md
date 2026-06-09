# HotpatchMonitor::ServiceMain(ulong,ushort * * const)

- ea: `0x180009a80`
- end: `0x18000a938`
- name: `?ServiceMain@HotpatchMonitor@@UEAAXKQEAPEAG@Z`
- size: `3768`
- prototype: `void __fastcall(HotpatchMonitor *__hidden this, unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180002fb0`

## callees

- `0x180001008`
- `0x1800011cc`
- `0x18000126c`
- `0x18000132c`
- `0x180001408`
- `0x180002270`
- `0x1800051d8`
- `0x180009a80`
- `0x18000b294`
- `0x18000c5f4`
- `0x18000c694`
- `0x18000d568`
- `0x18000d610`
- `0x18000ed44`
- `0x1800114a4`
- `0x1800115c0`
- `0x180015010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000a37e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000a49b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000a37e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000a49b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ae8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a7ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000a7ea`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a4ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a719`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a4ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000a719`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180009ad9`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180009ad9`
- `msvcp_win!_Xtime_get_ticks` at `0x18000a58d`
- `msvcp_win!_Xtime_get_ticks` at `0x18000a58d`

## string_xrefs

- `0x180009bce`: `Feature_Servicing_HotpatchMonitoring_Service`
- `0x180009cab`: `HotpatchUpdateNotInstalled`
- `0x180009d24`: `HotpatchUpdateNotInstalled`
- `0x180009dc4`: `HotpatchLCUNotInstalled`
- `0x180009fb7`: `HotpatchUpdateInstalled`
- `0x18000a034`: `HotpatchUpdateInstalled`
- `0x18000a50a`: `AutologgerConsumerThreadStart`
- `0x18000a767`: `ConsumerThreadStart`

## pseudocode

```c
void __fastcall HotpatchMonitor::ServiceMain(HotpatchMonitor *this, unsigned int a2, unsigned __int16 **const a3)
{
  SERVICE_STATUS_HANDLE v6; // rax
  signed int LastError; // eax
  signed int v8; // ebx
  int v9; // eax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // r8
  int started; // eax
  int v15; // r8d
  int v16; // r9d
  int v17; // ecx
  int v18; // ebx
  __int64 *v19; // rdx
  char *v20; // rdx
  unsigned int v21; // eax
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  unsigned int v25; // ebx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // r9d
  int v30; // ebx
  const wchar_t *v31; // r8
  __int64 v32; // rdx
  __int16 v33; // ax
  int v34; // eax
  int v35; // r9d
  int v36; // ebx
  __int16 v37; // ax
  int v38; // eax
  int v39; // r8d
  int v40; // r9d
  int v41; // ebx
  __int16 v42; // ax
  __int16 *v43; // rdx
  void *v44; // rax
  signed int v45; // ecx
  int RunTime; // eax
  int v47; // r8d
  int v48; // r9d
  int v49; // ebx
  __int16 v50; // ax
  int v51; // r8d
  int v52; // r9d
  int v53; // ecx
  __int16 v54; // ax
  int v55; // [rsp+20h] [rbp-B9h]
  BYTE v56[8]; // [rsp+50h] [rbp-89h] BYREF
  char v57; // [rsp+58h] [rbp-81h]
  const char *v58; // [rsp+60h] [rbp-79h] BYREF
  __int64 v59; // [rsp+68h] [rbp-71h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v61[2]; // [rsp+78h] [rbp-61h] BYREF
  __int16 v62; // [rsp+80h] [rbp-59h]
  const wchar_t *v63; // [rsp+88h] [rbp-51h] BYREF
  __int16 v64; // [rsp+90h] [rbp-49h]
  _BYTE v65[32]; // [rsp+A0h] [rbp-39h] BYREF
  __int64 *v66; // [rsp+C0h] [rbp-19h]
  __int64 v67; // [rsp+C8h] [rbp-11h]
  const char **v68; // [rsp+D0h] [rbp-9h]
  __int64 v69; // [rsp+D8h] [rbp-1h]
  const char *v70; // [rsp+E0h] [rbp+7h]
  __int64 v71; // [rsp+E8h] [rbp+Fh]

  *(_QWORD *)((char *)this + 20) = 0;
  *(_QWORD *)((char *)this + 28) = 0;
  *(_QWORD *)((char *)this + 36) = 0;
  *((_DWORD *)this + 4) = 16;
  v6 = RegisterServiceCtrlHandlerExW(L"hpatchmon", HotpatchMonitor::SvcHandler, this);
  *((_QWORD *)this + 1) = v6;
  if ( v6 )
  {
    v9 = (*(__int64 (__fastcall **)(HotpatchMonitor *, __int64, _QWORD, __int64))(*(_QWORD *)this + 32LL))(
           this,
           2,
           0,
           5000);
    v8 = v9;
    if ( v9 < 0 )
    {
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        v61[0] = v9;
        v67 = 4;
        v66 = (__int64 *)v61;
        tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, byte_180018E81, 0, 0, 3, v65);
      }
      goto LABEL_133;
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        *(_QWORD *)v56 = "Feature_Servicing_HotpatchMonitoring_Service";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v10,
          (unsigned int)word_180018672,
          v11,
          v12,
          (__int64)v56);
      }
      v13 = 0;
      goto LABEL_15;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(HotpatchMonitor *))(*(_QWORD *)this + 72LL))(this) )
    {
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        v61[0] = v8;
        v66 = (__int64 *)v61;
        v67 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, byte_18001877B, 0, 0, 3, v65);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetImpl'::`2'::impl) )
      {
        v61[0] = 3;
        started = HotpatchMonitor::ConfigureServiceStartType(v61);
        v17 = dword_18001E080;
        v18 = started;
        if ( (unsigned int)dword_18001E080 > 5 )
        {
          v17 = qword_18001E090;
          if ( (qword_18001E090 & 0x800000000000LL) != 0 )
          {
            v17 = 0;
            if ( (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
            {
              *(_QWORD *)v56 = "HotpatchUpdateNotInstalled";
              v61[0] = 3;
              *(_DWORD *)Data = started;
              v59 = 0x1000000;
              v58 = (const char *)0x80000000LL;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                0,
                (unsigned int)&byte_180019367,
                v15,
                v16,
                (__int64)&v58,
                (__int64)&v59,
                (__int64)Data,
                (__int64)v61,
                (__int64)v56);
            }
          }
        }
        if ( (unsigned int)dword_18001E048 > 5 )
        {
          v58 = "HotpatchUpdateNotInstalled";
          *(_DWORD *)Data = v18;
          v61[0] = 3;
          *(_DWORD *)v56 = v18;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v17,
            (unsigned int)&dword_180018EB4,
            v15,
            v16,
            (__int64)v56,
            (__int64)v61,
            (__int64)&v58,
            (__int64)Data);
        }
      }
      (*(void (__fastcall **)(HotpatchMonitor *, __int64, __int64))(*(_QWORD *)this + 32LL))(this, 1, 2);
      if ( (unsigned int)dword_18001E080 <= 5
        || (qword_18001E090 & 0x800000000000LL) == 0
        || (qword_18001E098 & 0x800000000000LL) != qword_18001E098 )
      {
        return;
      }
      v59 = 0x80000000LL;
      v70 = "HotpatchLCUNotInstalled";
      v19 = (__int64 *)byte_180018D9D;
      v71 = 24;
      v68 = &v58;
      v55 = 5;
LABEL_138:
      v66 = &v59;
      v58 = (const char *)0x1000000;
      v69 = 8;
      v67 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E080, v19, 0, 0, v55, v65);
      return;
    }
    v8 = (*(__int64 (__fastcall **)(HotpatchMonitor *, _QWORD, unsigned __int16 **const))(*(_QWORD *)this + 48LL))(
           this,
           a2,
           a3);
    if ( v8 < 0 )
    {
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        v67 = 4;
        v66 = (__int64 *)v56;
        v20 = (char *)&unk_180019518;
LABEL_132:
        *(_DWORD *)v56 = v8;
        tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, v20, 0, 0, 3, v65);
      }
LABEL_133:
      (*(void (__fastcall **)(HotpatchMonitor *))(*(_QWORD *)this + 56LL))(this);
      v13 = (unsigned int)v8;
LABEL_15:
      (*(void (__fastcall **)(HotpatchMonitor *, __int64, __int64, _QWORD))(*(_QWORD *)this + 32LL))(this, 1, v13, 0);
      return;
    }
    v8 = (*(__int64 (__fastcall **)(HotpatchMonitor *, __int64, _QWORD))(*(_QWORD *)this + 32LL))(this, 4, 0);
    if ( v8 < 0 )
    {
      if ( (unsigned int)dword_18001E048 <= 5 )
        goto LABEL_133;
      v66 = (__int64 *)v56;
      v20 = byte_180018F81;
      goto LABEL_131;
    }
    if ( (unsigned int)dword_18001E080 > 5
      && (qword_18001E090 & 0x800000000000LL) != 0
      && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
    {
      v58 = (const char *)0x1000000;
      v68 = &v58;
      v59 = 0x80000000LL;
      v66 = &v59;
      v69 = 8;
      v67 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E080, qword_180018C10, 0, 0, 4, v65);
    }
    v8 = (*(__int64 (__fastcall **)(HotpatchMonitor *))(*(_QWORD *)this + 40LL))(this);
    if ( v8 < 0 )
    {
      if ( (unsigned int)dword_18001E048 <= 5 )
        goto LABEL_133;
      v66 = (__int64 *)v56;
      v20 = (char *)&dword_180018ADC;
      goto LABEL_131;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetImpl'::`2'::impl) )
    {
      *(_DWORD *)v56 = 2;
      v21 = HotpatchMonitor::ConfigureServiceStartType((const unsigned int *)v56);
      v24 = dword_18001E080;
      v25 = v21;
      if ( (unsigned int)dword_18001E080 > 5 )
      {
        v24 = qword_18001E090;
        if ( (qword_18001E090 & 0x800000000000LL) != 0 )
        {
          v24 = 0;
          if ( (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
          {
            v58 = "HotpatchUpdateInstalled";
            *(_DWORD *)v56 = 2;
            *(_DWORD *)Data = v21;
            v59 = 0x1000000;
            *(_QWORD *)v61 = 0x80000000LL;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              0,
              (unsigned int)byte_1800191FD,
              v22,
              v23,
              (__int64)v61,
              (__int64)&v59,
              (__int64)Data,
              (__int64)v56,
              (__int64)&v58);
          }
        }
      }
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        v58 = "HotpatchUpdateInstalled";
        *(_DWORD *)v56 = v25;
        *(_DWORD *)Data = 2;
        v61[0] = v25;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)byte_1800189A9,
          v22,
          v23,
          (__int64)v61,
          (__int64)Data,
          (__int64)&v58,
          (__int64)v56);
      }
    }
    else
    {
      v26 = HotpatchMonitor::SetServiceToAutoStart();
      if ( v26 < 0 && (unsigned int)dword_18001E048 > 5 )
      {
        *(_DWORD *)v56 = v26;
        v67 = 4;
        v66 = (__int64 *)v56;
        tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, &unk_180018970, 0, 0, 3, v65);
      }
    }
    *(_DWORD *)v56 = 0;
    v27 = RegUtil::SetHotpatchError(v56);
    if ( v27 < 0 && (unsigned int)dword_18001E048 > 5 )
    {
      *(_DWORD *)v56 = v27;
      v67 = 4;
      v66 = (__int64 *)v56;
      tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, &byte_18001881F, 0, 0, 3, v65);
    }
    v28 = etwConsumer::initialize((HotpatchMonitor *)((char *)this + 104));
    v30 = v28;
    if ( v28 >= 0 )
    {
      v57 = 0;
      v34 = etwConsumer::startSession((HotpatchMonitor *)((char *)this + 104));
      v36 = v34;
      if ( v34 < 0 )
      {
        if ( (unsigned int)dword_18001E048 > 5 )
        {
          *(_DWORD *)v56 = v34;
          v67 = 4;
          v66 = (__int64 *)v56;
          tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, &dword_1800190B4, 0, 0, 3, v65);
        }
        if ( (unsigned int)dword_18001E080 > 5
          && (qword_18001E090 & 0x800000000000LL) != 0
          && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
        {
          *(_DWORD *)v56 = v36;
          v58 = "StartSession";
          if ( (unsigned __int16)TraceUtil::RealtimeStringLength > 0x7FFFu )
            v37 = -2;
          else
            v37 = 2 * TraceUtil::RealtimeStringLength;
          v62 = v37;
          *(_QWORD *)v61 = L"Realtime";
          *(_QWORD *)Data = 0x80000000LL;
          v59 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            qword_18001E098,
            (unsigned int)byte_180018853,
            (unsigned int)L"Realtime",
            v35,
            (__int64)Data,
            (__int64)&v59,
            (__int64)v61,
            (__int64)&v58,
            (__int64)v56);
        }
        v57 = 1;
      }
      *((_QWORD *)this + 12) = _o__beginthreadex(0, 0, TraceUtil::EtwConsumerThread, (char *)this + 64, 0, 0);
    }
    else
    {
      if ( (unsigned int)dword_18001E048 > 5 )
      {
        *(_DWORD *)v56 = v28;
        v67 = 4;
        v66 = (__int64 *)v56;
        tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, &dword_18001932C, 0, 0, 3, v65);
      }
      v31 = L"Realtime";
      v32 = 0x7FFF;
      if ( (unsigned int)dword_18001E080 > 5
        && (qword_18001E090 & 0x800000000000LL) != 0
        && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
      {
        *(_DWORD *)v56 = v30;
        v58 = "InitializeSession";
        if ( (unsigned __int16)TraceUtil::RealtimeStringLength > 0x7FFFu )
          v33 = -2;
        else
          v33 = 2 * TraceUtil::RealtimeStringLength;
        v62 = v33;
        *(_QWORD *)v61 = L"Realtime";
        *(_QWORD *)Data = 0x80000000LL;
        v59 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          qword_18001E098,
          (unsigned int)&unk_180019410,
          (unsigned int)L"Realtime",
          v29,
          (__int64)Data,
          (__int64)&v59,
          (__int64)v61,
          (__int64)&v58,
          (__int64)v56);
      }
      v57 = 1;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(HotpatchMonitor *, __int64, const wchar_t *))(*(_QWORD *)this + 80LL))(
            this,
            v32,
            v31) )
    {
      v38 = autologgerProcessor::initialize((HotpatchMonitor *)((char *)this + 184));
      v41 = v38;
      if ( v38 < 0 )
      {
        if ( (unsigned int)dword_18001E048 > 5 )
        {
          *(_DWORD *)v56 = v38;
          v67 = 4;
          v66 = (__int64 *)v56;
          tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, &word_180019136, 0, 0, 3, v65);
        }
        if ( (unsigned int)dword_18001E080 <= 5
          || (qword_18001E090 & 0x800000000000LL) == 0
          || (qword_18001E098 & 0x800000000000LL) != qword_18001E098 )
        {
          goto LABEL_114;
        }
        *(_DWORD *)v56 = v41;
        v58 = "AutologgerInitializeSession";
        if ( (unsigned __int16)TraceUtil::AutologgerStringLength > 0x7FFFu )
          v42 = -2;
        else
          v42 = 2 * TraceUtil::AutologgerStringLength;
        v43 = word_180018BAA;
        goto LABEL_101;
      }
      *((_QWORD *)this + 19) = *((_QWORD *)this + 24);
      *((_QWORD *)this + 20) = *((_QWORD *)this + 26);
      v44 = (void *)_o__beginthreadex(0, 0, TraceUtil::AutologgerProcessorThread, (char *)this + 152, 0, 0);
      *((_QWORD *)this + 22) = v44;
      if ( !WaitForSingleObject(v44, 0xFFFFFFFF) )
      {
        v45 = *((_DWORD *)this + 42);
        if ( !v45 )
        {
          *(_QWORD *)Data = _Xtime_get_ticks() / 10000;
          RunTime = RegUtil::SetAutologgerLastRunTime(Data);
          v49 = RunTime;
          if ( RunTime < 0 )
          {
            if ( (unsigned int)dword_18001E048 > 5 )
            {
              *(_DWORD *)v56 = RunTime;
              v67 = 4;
              v66 = (__int64 *)v56;
              tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, &word_180019476, 0, 0, 3, v65);
            }
            if ( (unsigned int)dword_18001E080 > 5
              && (qword_18001E090 & 0x800000000000LL) != 0
              && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
            {
              *(_DWORD *)v56 = v49;
              v58 = "SetAutologgerLastRunTime";
              if ( (unsigned __int16)TraceUtil::AutologgerStringLength > 0x7FFFu )
                v50 = -2;
              else
                v50 = 2 * TraceUtil::AutologgerStringLength;
              v64 = v50;
              v63 = L"Autologger";
              *(_QWORD *)v61 = 0x80000000LL;
              v59 = 0x1000000;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                (unsigned int)L"Autologger",
                (unsigned int)word_1800194B2,
                v47,
                v48,
                (__int64)v61,
                (__int64)&v59,
                (__int64)&v63,
                (__int64)&v58,
                (__int64)v56);
            }
          }
          if ( (unsigned int)dword_18001E048 > 5 )
          {
            v58 = *(const char **)Data;
            v67 = 8;
            v66 = (__int64 *)&v58;
            tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, &unk_180018E40, 0, 0, 3, v65);
          }
          goto LABEL_114;
        }
        if ( v45 > 0 )
          v45 = (unsigned __int16)v45 | 0x80070000;
        if ( (unsigned int)dword_18001E080 > 5
          && (qword_18001E090 & 0x800000000000LL) != 0
          && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
        {
          *(_DWORD *)v56 = v45;
          v58 = "AutologgerConsumerThreadStart";
          if ( (unsigned __int16)TraceUtil::AutologgerStringLength > 0x7FFFu )
            v42 = -2;
          else
            v42 = 2 * TraceUtil::AutologgerStringLength;
          v43 = &word_18001904E;
LABEL_101:
          v62 = v42;
          v59 = 0x1000000;
          *(_QWORD *)Data = 0x80000000LL;
          *(_QWORD *)v61 = L"Autologger";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)L"Autologger",
            (_DWORD)v43,
            v39,
            v40,
            (__int64)Data,
            (__int64)&v59,
            (__int64)v61,
            (__int64)&v58,
            (__int64)v56);
        }
      }
    }
LABEL_114:
    if ( !v57 && !WaitForSingleObject(*((HANDLE *)this + 9), 0xFFFFFFFF) )
    {
      v53 = *((_DWORD *)this + 22);
      if ( v53 )
      {
        if ( (unsigned int)dword_18001E080 > 5
          && (qword_18001E090 & 0x800000000000LL) != 0
          && (qword_18001E098 & 0x800000000000LL) == qword_18001E098 )
        {
          *(_DWORD *)v56 = v53 | 0x10000000;
          v58 = "ConsumerThreadStart";
          if ( (unsigned __int16)TraceUtil::RealtimeStringLength > 0x7FFFu )
            v54 = -2;
          else
            v54 = 2 * TraceUtil::RealtimeStringLength;
          v64 = v54;
          v63 = L"Realtime";
          v59 = 0x1000000;
          *(_QWORD *)Data = 0x80000000LL;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<1>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)L"Realtime",
            (unsigned int)&byte_180018697,
            v51,
            v52,
            (__int64)Data,
            (__int64)&v59,
            (__int64)&v63,
            (__int64)&v58,
            (__int64)v56);
        }
      }
    }
    WaitForSingleObjectEx(*((HANDLE *)this + 6), 0xFFFFFFFF, 0);
    v8 = (*(__int64 (__fastcall **)(HotpatchMonitor *))(*(_QWORD *)this + 56LL))(this);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(HotpatchMonitor *, __int64, _QWORD))(*(_QWORD *)this + 32LL))(this, 1, 0);
      if ( v8 >= 0 )
      {
        if ( (unsigned int)dword_18001E080 <= 5
          || (qword_18001E090 & 0x800000000000LL) == 0
          || (qword_18001E098 & 0x800000000000LL) != qword_18001E098 )
        {
          return;
        }
        v19 = qword_180018A38;
        v59 = 0x80000000LL;
        v68 = &v58;
        v55 = 4;
        goto LABEL_138;
      }
      if ( (unsigned int)dword_18001E048 <= 5 )
        goto LABEL_133;
      v20 = &byte_1800192EF;
    }
    else
    {
      if ( (unsigned int)dword_18001E048 <= 5 )
        goto LABEL_133;
      v20 = byte_180018945;
    }
    v66 = (__int64 *)v56;
LABEL_131:
    v67 = 4;
    goto LABEL_132;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( (unsigned int)dword_18001E048 > 5 )
  {
    v61[0] = v8;
    v66 = (__int64 *)v61;
    v67 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_18001E048, word_180019262, 0, 0, 3, v65);
  }
  if ( v8 < 0 )
    goto LABEL_133;
}

```

## disassembly

```asm
0x180009a80  mov     [rsp-8+arg_18], rbx
0x180009a85  push    rbp
0x180009a86  push    rsi
0x180009a87  push    rdi
0x180009a88  push    r12
0x180009a8a  push    r13
0x180009a8c  push    r14
0x180009a8e  push    r15
0x180009a90  lea     rbp, [rsp-27h]
0x180009a95  sub     rsp, 100h
0x180009a9c  mov     rax, cs:__security_cookie
0x180009aa3  xor     rax, rsp
0x180009aa6  mov     [rbp+57h+var_40], rax
0x180009aaa  xor     r12d, r12d
0x180009aad  mov     r14, r8
0x180009ab0  mov     [rcx+14h], r12
0x180009ab4  mov     esi, edx
0x180009ab6  mov     [rcx+1Ch], r12
0x180009aba  lea     rdx, ?SvcHandler@HotpatchMonitor@@KAKKKPEAX0@Z; lpHandlerProc
0x180009ac1  mov     [rcx+24h], r12
0x180009ac5  mov     rdi, rcx
0x180009ac8  mov     dword ptr [rcx+10h], 10h
0x180009acf  mov     r8, rcx; lpContext
0x180009ad2  lea     rcx, ServiceName; "hpatchmon"
0x180009ad9  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180009adf  mov     [rdi+8], rax
0x180009ae3  test    rax, rax
0x180009ae6  jnz     short loc_180009B52
0x180009ae8  call    cs:__imp_GetLastError
0x180009aee  mov     ebx, eax
0x180009af0  test    eax, eax
0x180009af2  jle     short loc_180009AFD
0x180009af4  movzx   ebx, ax
0x180009af7  or      ebx, 80070000h
0x180009afd  mov     eax, cs:dword_18001E048
0x180009b03  cmp     eax, 5
0x180009b06  jbe     short loc_180009B45
0x180009b08  lea     rax, [rbp+57h+var_B8]
0x180009b0c  mov     [rbp+57h+var_B8], ebx
0x180009b0f  mov     [rbp+57h+var_70], rax
0x180009b13  lea     rdx, word_180019262
0x180009b1a  lea     rax, [rbp+57h+var_90]
0x180009b1e  mov     [rbp+57h+var_68], 4
0x180009b26  mov     [rsp+130h+var_108], rax
0x180009b2b  lea     rcx, dword_18001E048
0x180009b32  xor     r9d, r9d
0x180009b35  mov     dword ptr [rsp+130h+var_110], 3
0x180009b3d  xor     r8d, r8d
0x180009b40  call    _tlgWriteTransfer_EventWriteTransfer
0x180009b45  test    ebx, ebx
0x180009b47  jns     loc_18000A911
0x180009b4d  jmp     loc_18000A87A
0x180009b52  mov     rax, [rdi]
0x180009b55  xor     r8d, r8d
0x180009b58  mov     r9d, 1388h
0x180009b5e  mov     rcx, rdi
0x180009b61  mov     rax, [rax+20h]
0x180009b65  lea     edx, [r8+2]
0x180009b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b6e  mov     ebx, eax
0x180009b70  test    eax, eax
0x180009b72  jns     short loc_180009BB3
0x180009b74  mov     ecx, cs:dword_18001E048
0x180009b7a  cmp     ecx, 5
0x180009b7d  jbe     loc_18000A87A
0x180009b83  mov     [rbp+57h+var_B8], eax
0x180009b86  lea     rdx, byte_180018E81
0x180009b8d  lea     rax, [rbp+57h+var_B8]
0x180009b91  mov     [rbp+57h+var_68], 4
0x180009b99  mov     [rbp+57h+var_70], rax
0x180009b9d  lea     rax, [rbp+57h+var_90]
0x180009ba1  mov     [rsp+130h+var_108], rax
0x180009ba6  mov     dword ptr [rsp+130h+var_110], 3
0x180009bae  jmp     loc_18000A868
0x180009bb3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service> `wil::Feature<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::GetImpl(void)'::`2'::impl
0x180009bba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service>::__private_IsEnabled(void)
0x180009bbf  test    al, al
0x180009bc1  jnz     short loc_180009C0F
0x180009bc3  mov     eax, cs:dword_18001E048
0x180009bc9  cmp     eax, 5
0x180009bcc  jbe     short loc_180009BF0
0x180009bce  lea     rax, aFeatureServici; "Feature_Servicing_HotpatchMonitoring_Se"...
0x180009bd5  mov     qword ptr [rsp+130h+var_E0], rax
0x180009bda  lea     rdx, word_180018672
0x180009be1  lea     rax, [rsp+130h+var_E0]
0x180009be6  mov     [rsp+130h+var_110], rax
0x180009beb  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180009bf0  xor     r9d, r9d
0x180009bf3  xor     r8d, r8d
0x180009bf6  mov     rax, [rdi]
0x180009bf9  mov     edx, 1
0x180009bfe  mov     rcx, rdi
0x180009c01  mov     rax, [rax+20h]
0x180009c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c0a  jmp     loc_18000A911
0x180009c0f  mov     rax, [rdi]
0x180009c12  mov     rcx, rdi
0x180009c15  mov     rax, [rax+48h]
0x180009c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c1e  test    al, al
0x180009c20  jnz     loc_180009E00
0x180009c26  mov     eax, cs:dword_18001E048
0x180009c2c  mov     esi, 3
0x180009c31  cmp     eax, 5
0x180009c34  jbe     short loc_180009C6F
0x180009c36  lea     rax, [rbp+57h+var_B8]
0x180009c3a  mov     [rbp+57h+var_B8], ebx
0x180009c3d  mov     [rbp+57h+var_70], rax
0x180009c41  lea     rdx, byte_18001877B
0x180009c48  lea     rax, [rbp+57h+var_90]
0x180009c4c  mov     [rbp+57h+var_68], 4
0x180009c54  mov     [rsp+130h+var_108], rax
0x180009c59  lea     rcx, dword_18001E048
0x180009c60  xor     r9d, r9d
0x180009c63  mov     dword ptr [rsp+130h+var_110], esi
0x180009c67  xor     r8d, r8d
0x180009c6a  call    _tlgWriteTransfer_EventWriteTransfer
0x180009c6f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart> `wil::Feature<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetImpl(void)'::`2'::impl
0x180009c76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::__private_IsEnabled(void)
0x180009c7b  mov     r14, 800000000000h
0x180009c85  mov     r13d, 1000000h
0x180009c8b  mov     r15d, 80000000h
0x180009c91  test    al, al
0x180009c93  jz      loc_180009D75
0x180009c99  lea     rcx, [rbp+57h+var_B8]; unsigned int *
0x180009c9d  mov     [rbp+57h+var_B8], esi
0x180009ca0  call    ?ConfigureServiceStartType@HotpatchMonitor@@KAJAEBK@Z; HotpatchMonitor::ConfigureServiceStartType(ulong const &)
0x180009ca5  mov     ecx, cs:dword_18001E080
0x180009cab  lea     rdx, aHotpatchupdate_0; "HotpatchUpdateNotInstalled"
0x180009cb2  mov     ebx, eax
0x180009cb4  cmp     ecx, 5
0x180009cb7  jbe     short loc_180009D2B
0x180009cb9  mov     rax, cs:qword_18001E098
0x180009cc0  mov     rcx, cs:qword_18001E090
0x180009cc7  test    r14, rcx
0x180009cca  jz      short loc_180009D2B
0x180009ccc  mov     rcx, rax
0x180009ccf  and     rcx, r14
0x180009cd2  cmp     rcx, rax
0x180009cd5  jnz     short loc_180009D2B
0x180009cd7  lea     rax, [rsp+130h+var_E0]
0x180009cdc  mov     qword ptr [rsp+130h+var_E0], rdx
0x180009ce1  mov     [rsp+130h+var_F0], rax
0x180009ce6  lea     rdx, byte_180019367
0x180009ced  lea     rax, [rbp+57h+var_B8]
0x180009cf1  mov     [rbp+57h+var_B8], esi
0x180009cf4  mov     [rsp+130h+var_F8], rax
0x180009cf9  lea     rax, [rbp+57h+Data]
0x180009cfd  mov     [rsp+130h+var_100], rax
0x180009d02  lea     rax, [rbp+57h+var_C8]
0x180009d06  mov     [rsp+130h+var_108], rax
0x180009d0b  lea     rax, [rbp+57h+var_D0]
0x180009d0f  mov     [rsp+130h+var_110], rax
0x180009d14  mov     dword ptr [rbp+57h+Data], ebx
0x180009d17  mov     [rbp+57h+var_C8], r13
0x180009d1b  mov     [rbp+57h+var_D0], r15
0x180009d1f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180009d24  lea     rdx, aHotpatchupdate_0; "HotpatchUpdateNotInstalled"
0x180009d2b  mov     eax, cs:dword_18001E048
0x180009d31  cmp     eax, 5
0x180009d34  jbe     short loc_180009D75
0x180009d36  lea     rax, [rbp+57h+Data]
0x180009d3a  mov     [rbp+57h+var_D0], rdx
0x180009d3e  mov     [rsp+130h+var_F8], rax
0x180009d43  lea     rdx, dword_180018EB4
0x180009d4a  lea     rax, [rbp+57h+var_D0]
0x180009d4e  mov     dword ptr [rbp+57h+Data], ebx
0x180009d51  mov     [rsp+130h+var_100], rax
0x180009d56  lea     rax, [rbp+57h+var_B8]
0x180009d5a  mov     [rsp+130h+var_108], rax
0x180009d5f  lea     rax, [rsp+130h+var_E0]
0x180009d64  mov     [rsp+130h+var_110], rax
0x180009d69  mov     [rbp+57h+var_B8], esi
0x180009d6c  mov     dword ptr [rsp+130h+var_E0], ebx
0x180009d70  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180009d75  mov     rax, [rdi]
0x180009d78  xor     r9d, r9d
0x180009d7b  mov     rcx, rdi
0x180009d7e  mov     rax, [rax+20h]
0x180009d82  lea     edx, [r9+1]
0x180009d86  lea     r8d, [r9+2]
0x180009d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d8f  mov     eax, cs:dword_18001E080
0x180009d95  cmp     eax, 5
0x180009d98  jbe     loc_18000A911
0x180009d9e  mov     rcx, cs:qword_18001E098
0x180009da5  mov     rax, cs:qword_18001E090
0x180009dac  test    r14, rax
0x180009daf  jz      loc_18000A911
0x180009db5  mov     rax, rcx
0x180009db8  and     rax, r14
0x180009dbb  cmp     rax, rcx
0x180009dbe  jnz     loc_18000A911
0x180009dc4  lea     rax, aHotpatchlcunot; "HotpatchLCUNotInstalled"
0x180009dcb  mov     [rbp+57h+var_C8], r15
0x180009dcf  mov     [rbp+57h+var_50], rax
0x180009dd3  lea     rdx, byte_180018D9D
0x180009dda  lea     rax, [rbp+57h+var_D0]
0x180009dde  mov     [rbp+57h+var_48], 18h
0x180009de6  mov     [rbp+57h+var_60], rax
0x180009dea  lea     rax, [rbp+57h+var_90]
0x180009dee  mov     [rsp+130h+var_108], rax
0x180009df3  mov     dword ptr [rsp+130h+var_110], 5
0x180009dfb  jmp     loc_18000A8E3
0x180009e00  mov     rax, [rdi]
0x180009e03  mov     r8, r14
0x180009e06  mov     edx, esi
0x180009e08  mov     rcx, rdi
0x180009e0b  mov     rax, [rax+30h]
0x180009e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e14  mov     ebx, eax
0x180009e16  test    eax, eax
0x180009e18  jns     short loc_180009E57
0x180009e1a  mov     eax, cs:dword_18001E048
0x180009e20  cmp     eax, 5
0x180009e23  jbe     loc_18000A87A
0x180009e29  lea     rax, [rsp+130h+var_E0]
0x180009e2e  mov     [rbp+57h+var_68], 4
0x180009e36  mov     [rbp+57h+var_70], rax
0x180009e3a  lea     rdx, unk_180019518
0x180009e41  lea     rax, [rbp+57h+var_90]
0x180009e45  mov     [rsp+130h+var_108], rax
0x180009e4a  mov     dword ptr [rsp+130h+var_110], 3
0x180009e52  jmp     loc_18000A864
0x180009e57  mov     rax, [rdi]
0x180009e5a  xor     r9d, r9d
0x180009e5d  xor     r8d, r8d
0x180009e60  mov     rcx, rdi
0x180009e63  mov     rax, [rax+20h]
0x180009e67  lea     r15d, [r9+4]
0x180009e6b  mov     edx, r15d
0x180009e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e73  mov     ebx, eax
0x180009e75  test    eax, eax
0x180009e77  jns     short loc_180009EAE
0x180009e79  mov     eax, cs:dword_18001E048
0x180009e7f  cmp     eax, 5
0x180009e82  jbe     loc_18000A87A
0x180009e88  lea     rax, [rsp+130h+var_E0]
0x180009e8d  mov     [rbp+57h+var_70], rax
0x180009e91  lea     rdx, byte_180018F81
0x180009e98  lea     rax, [rbp+57h+var_90]
0x180009e9c  mov     [rsp+130h+var_108], rax
0x180009ea1  mov     dword ptr [rsp+130h+var_110], 3
0x180009ea9  jmp     loc_18000A860
0x180009eae  mov     eax, cs:dword_18001E080
0x180009eb4  mov     r14, 800000000000h
0x180009ebe  mov     r13d, 1000000h
0x180009ec4  mov     r12d, 80000000h
0x180009eca  cmp     eax, 5
0x180009ecd  jbe     short loc_180009F3C
0x180009ecf  mov     rcx, cs:qword_18001E098
0x180009ed6  mov     rax, cs:qword_18001E090
0x180009edd  test    r14, rax
0x180009ee0  jz      short loc_180009F3C
0x180009ee2  mov     rax, rcx
0x180009ee5  and     rax, r14
0x180009ee8  cmp     rax, rcx
0x180009eeb  jnz     short loc_180009F3C
0x180009eed  lea     rax, [rbp+57h+var_D0]
0x180009ef1  mov     [rbp+57h+var_D0], r13
0x180009ef5  mov     [rbp+57h+var_60], rax
0x180009ef9  lea     rdx, qword_180018C10
0x180009f00  lea     rax, [rbp+57h+var_C8]
0x180009f04  mov     [rbp+57h+var_C8], r12
0x180009f08  mov     [rbp+57h+var_70], rax
0x180009f0c  lea     rcx, dword_18001E080
0x180009f13  lea     rax, [rbp+57h+var_90]
0x180009f17  mov     [rbp+57h+var_58], 8
0x180009f1f  mov     [rsp+130h+var_108], rax
0x180009f24  xor     r9d, r9d
0x180009f27  xor     r8d, r8d
0x180009f2a  mov     dword ptr [rsp+130h+var_110], r15d
0x180009f2f  mov     [rbp+57h+var_68], 8
0x180009f37  call    _tlgWriteTransfer_EventWriteTransfer
0x180009f3c  mov     rax, [rdi]
0x180009f3f  mov     rcx, rdi
0x180009f42  mov     rax, [rax+28h]
0x180009f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f4b  mov     ebx, eax
0x180009f4d  test    eax, eax
0x180009f4f  jns     short loc_180009F86
0x180009f51  mov     eax, cs:dword_18001E048
0x180009f57  cmp     eax, 5
0x180009f5a  jbe     loc_18000A87A
0x180009f60  lea     rax, [rsp+130h+var_E0]
0x180009f65  mov     [rbp+57h+var_70], rax
0x180009f69  lea     rdx, dword_180018ADC
0x180009f70  lea     rax, [rbp+57h+var_90]
0x180009f74  mov     [rsp+130h+var_108], rax
0x180009f79  mov     dword ptr [rsp+130h+var_110], 3
0x180009f81  jmp     loc_18000A860
0x180009f86  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart> `wil::Feature<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::GetImpl(void)'::`2'::impl
0x180009f8d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_HotpatchMonitoring_Service_SmartStart>::__private_IsEnabled(void)
0x180009f92  mov     esi, 3
0x180009f97  test    al, al
0x180009f99  jz      loc_18000A08F
0x180009f9f  lea     rcx, [rsp+130h+var_E0]; unsigned int *
0x180009fa4  mov     dword ptr [rsp+130h+var_E0], 2
0x180009fac  call    ?ConfigureServiceStartType@HotpatchMonitor@@KAJAEBK@Z; HotpatchMonitor::ConfigureServiceStartType(ulong const &)
  ... truncated ...
```
