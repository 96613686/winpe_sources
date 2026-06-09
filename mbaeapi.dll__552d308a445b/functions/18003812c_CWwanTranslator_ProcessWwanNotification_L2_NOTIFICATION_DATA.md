# CWwanTranslator::ProcessWwanNotification(_L2_NOTIFICATION_DATA *)

- ea: `0x18003812c`
- end: `0x1800395b0`
- name: `?ProcessWwanNotification@CWwanTranslator@@QEAAXPEAU_L2_NOTIFICATION_DATA@@@Z`
- size: `5252`
- prototype: `void __fastcall(CWwanTranslator *__hidden this, struct _L2_NOTIFICATION_DATA *)`
- caller_count: `1`
- callee_count: `37`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800463a0`

## callees

- `0x18000178c`
- `0x180001aa0`
- `0x1800024e0`
- `0x1800040cd`
- `0x180009ffc`
- `0x18001105c`
- `0x180016bc0`
- `0x1800172bc`
- `0x18001dd10`
- `0x1800354dc`
- `0x180035744`
- `0x180035ef4`
- `0x18003812c`
- `0x18003bdfc`
- `0x18003e4f4`
- `0x18003e710`
- `0x18003ed2c`
- `0x18003f0b0`
- `0x18003f304`
- `0x18003f650`
- `0x18003f8e0`
- `0x18003fc28`
- `0x18003fe60`
- `0x1800407a4`
- `0x1800409f8`
- `0x180040c4c`
- `0x18004162c`
- `0x18004177c`
- `0x1800418cc`
- `0x180041e70`
- `0x180042254`
- `0x180042674`
- `0x1800428c8`
- `0x180042f4c`
- `0x1800431f0`
- `0x180043834`
- `0x180043de4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038196`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038196`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180038166`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180038166`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038206`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038206`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800381b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800381b0`

## string_xrefs

- `0x180039182`: `WwanMsmEventTypeProfileIStreamDeleted`
- `0x18003870f`: `WwanMsmEventTypeProfileIStreamCreated`
- `0x180038e48`: `WwanMsmEventTypeProfileIStreamUpdated`
- `0x180038482`: `WwanMsmEventTypeGetPinInfoComplete: Success`
- `0x18003859c`: `WwanMsmEventTypeGetPinInfoComplete: Failed`
- `0x180038bc7`: `WwanMsmEventTypePinActionComplete: Failed`
- `0x180038996`: `WwanMsmEventTypePinActionComplete: Success`
- `0x1800390f0`: `WwanMsmEventTypeConnectionIStreamUpdated`
- `0x18003911a`: `WwanMsmEventTypeConnectionIStreamCreated`
- `0x1800388f2`: `WwanMsmEventTypeSetRadioStateComplete`
- `0x1800383b4`: `WwanMsmEventTypeScanCompleted`
- `0x180039088`: `WwanMsmEventTypeDMConfigProfileUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CWwanTranslator::ProcessWwanNotification(CWwanTranslator *this, struct _L2_NOTIFICATION_DATA *a2)
{
  unsigned __int16 *v4; // rsi
  SlotBindingMap *v5; // rcx
  bool v6; // si
  bool v7; // r14
  __int64 v8; // r13
  DWORD NotificationCode; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  DWORD v13; // eax
  DWORD v14; // eax
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // r8
  __int64 v20; // r9
  const char *v21; // rcx
  int *v22; // rdx
  const struct _tlgProvider_t *v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  const char *v26; // rcx
  __int16 *v27; // rdx
  const struct _tlgProvider_t *v28; // rax
  __int64 v29; // r8
  __int64 v30; // r9
  const struct _tlgProvider_t *v31; // rax
  __int64 v32; // r8
  __int64 v33; // r9
  const struct _tlgProvider_t *v34; // rax
  __int64 v35; // r8
  __int64 v36; // r9
  const struct _tlgProvider_t *v37; // rax
  __int64 v38; // r8
  __int64 v39; // r9
  const struct _tlgProvider_t *v40; // rax
  __int64 v41; // r8
  __int64 v42; // r9
  DWORD v43; // eax
  DWORD v44; // eax
  DWORD v45; // eax
  DWORD v46; // eax
  DWORD v47; // eax
  const struct _tlgProvider_t *v48; // rax
  __int64 v49; // r8
  __int64 v50; // r9
  const struct _tlgProvider_t *v51; // rax
  __int64 v52; // r8
  __int64 v53; // r9
  unsigned __int16 **v54; // rcx
  const struct _tlgProvider_t *v55; // rax
  __int64 v56; // r8
  __int64 v57; // r9
  const struct _tlgProvider_t *v58; // rax
  __int64 v59; // r8
  __int64 v60; // r9
  const struct _tlgProvider_t *v61; // rax
  __int64 v62; // r8
  __int64 v63; // r9
  const char *v64; // rcx
  __int16 *v65; // rdx
  _QWORD *pData; // rsi
  const struct _tlgProvider_t *v67; // rax
  __int64 v68; // r8
  __int64 v69; // r9
  const struct _tlgProvider_t *v70; // rax
  __int64 v71; // r8
  __int64 v72; // r9
  const struct _tlgProvider_t *v73; // rax
  __int64 v74; // r8
  __int64 v75; // r9
  int v76; // edx
  const struct _tlgProvider_t *v77; // rax
  __int64 v78; // r8
  __int64 v79; // r9
  const struct _tlgProvider_t *v80; // rax
  __int64 v81; // r8
  __int64 v82; // r9
  const struct _tlgProvider_t *v83; // rax
  __int64 v84; // r8
  __int64 v85; // r9
  int Pin1PreviousState; // eax
  unsigned int v87; // ecx
  const struct _tlgProvider_t *v88; // rax
  __int64 v89; // r8
  __int64 v90; // r9
  const struct _tlgProvider_t *v91; // rax
  __int64 v92; // r8
  __int64 v93; // r9
  DWORD v94; // eax
  DWORD v95; // eax
  DWORD v96; // eax
  DWORD v97; // eax
  DWORD v98; // eax
  const struct _tlgProvider_t *v99; // rax
  __int64 v100; // r8
  __int64 v101; // r9
  const struct _tlgProvider_t *v102; // rax
  __int64 v103; // r8
  __int64 v104; // r9
  const struct _tlgProvider_t *v105; // rax
  __int64 v106; // r8
  __int64 v107; // r9
  const struct _tlgProvider_t *v108; // rax
  __int64 v109; // r8
  __int64 v110; // r9
  const char *v111; // rcx
  int *v112; // rdx
  const struct _tlgProvider_t *v113; // rax
  __int64 v114; // r8
  __int64 v115; // r9
  const struct _tlgProvider_t *v116; // rax
  __int64 v117; // r8
  __int64 v118; // r9
  DWORD v119; // eax
  DWORD v120; // eax
  DWORD v121; // eax
  DWORD v122; // eax
  DWORD v123; // eax
  const struct _tlgProvider_t *v124; // rax
  __int64 v125; // r8
  __int64 v126; // r9
  const struct _tlgProvider_t *v127; // rax
  __int64 v128; // r8
  __int64 v129; // r9
  const struct _tlgProvider_t *v130; // rax
  __int64 v131; // r8
  __int64 v132; // r9
  const struct _tlgProvider_t *v133; // rax
  __int64 v134; // r8
  __int64 v135; // r9
  const struct _tlgProvider_t *v136; // rax
  __int64 v137; // r8
  __int64 v138; // r9
  const struct _tlgProvider_t *v139; // rax
  __int64 v140; // r8
  __int64 v141; // r9
  const struct _tlgProvider_t *v142; // rax
  __int64 v143; // r8
  __int64 v144; // r9
  bool *v145; // [rsp+20h] [rbp-89h]
  unsigned int dwDataSize; // [rsp+40h] [rbp-69h] BYREF
  unsigned __int16 *p_Buf1; // [rsp+48h] [rbp-61h] BYREF
  bool v148; // [rsp+50h] [rbp-59h] BYREF
  bool v149[7]; // [rsp+51h] [rbp-58h] BYREF
  const char *v150; // [rsp+58h] [rbp-51h] BYREF
  bool v151; // [rsp+60h] [rbp-49h] BYREF
  unsigned __int16 *v152[2]; // [rsp+68h] [rbp-41h] BYREF
  __int64 v153; // [rsp+78h] [rbp-31h]
  unsigned __int16 *v154[2]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v155; // [rsp+90h] [rbp-19h]
  GUID Buf1; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int16 *v157[2]; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v158; // [rsp+B8h] [rbp+Fh]

  v4 = (unsigned __int16 *)((char *)this + 152);
  AcquireSRWLockShared((PSRWLOCK)this + 19);
  p_Buf1 = v4;
  if ( *((_QWORD *)this + 4) )
  {
    v5 = (SlotBindingMap *)*((_QWORD *)this + 17);
    if ( v5 )
      SlotBindingMap::OnWwanNotification(v5, a2);
  }
  if ( v4 )
    ReleaseSRWLockShared((PSRWLOCK)v4);
  v6 = 0;
  Buf1 = a2->InterfaceGuid;
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v7 = 1;
  if ( *((_QWORD *)this + 3) )
  {
    std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(
      (__int64)this + 16,
      v154,
      &Buf1);
    v8 = v155;
    if ( !*(_BYTE *)(v155 + 25) && memcmp_0(&Buf1, (const void *)(v155 + 32), 0x10u) >= 0 )
      v6 = v8 != *((_QWORD *)this + 2);
  }
  if ( this != (CWwanTranslator *)-40LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( !v6 )
    return;
  v149[0] = 0;
  v148 = 0;
  NotificationCode = a2->NotificationCode;
  if ( NotificationCode > 0x2E )
  {
    if ( NotificationCode > 0x4E )
    {
      v119 = NotificationCode - 85;
      if ( !v119 )
      {
        v142 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v142 > 5u )
        {
          dwDataSize = a2->dwDataSize;
          p_Buf1 = (unsigned __int16 *)&Buf1;
          v150 = "WwanMsmEventTypeHighestConnCategory";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            (__int64)v142,
            (__int64)&word_1800777C6,
            v143,
            v144,
            (const unsigned __int16 **)&v150,
            (__int64 *)&p_Buf1,
            (__int64)&dwDataSize);
        }
        CWwanTranslator::_ProcessHighestConnCategoryChange(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
        return;
      }
      v120 = v119 - 1;
      if ( !v120 )
      {
        v139 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v139 > 5u )
        {
          dwDataSize = a2->dwDataSize;
          p_Buf1 = (unsigned __int16 *)&Buf1;
          v150 = "WwanMsmEventTypeEnterpriseAPNParams";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            (__int64)v139,
            (__int64)byte_180077691,
            v140,
            v141,
            (const unsigned __int16 **)&v150,
            (__int64 *)&p_Buf1,
            (__int64)&dwDataSize);
        }
        CWwanTranslator::_ProcessEnterpriseAPNParams(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
        return;
      }
      v121 = v120 - 3;
      if ( !v121 )
      {
        v136 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v136 > 5u )
        {
          dwDataSize = a2->dwDataSize;
          p_Buf1 = (unsigned __int16 *)&Buf1;
          v150 = "WwanMsmEventTypeDisallowAutoConnectChanged";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            (__int64)v136,
            (__int64)&dword_180077894,
            v137,
            v138,
            (const unsigned __int16 **)&v150,
            (__int64 *)&p_Buf1,
            (__int64)&dwDataSize);
        }
        CWwanTranslator::_ProcessDisallowAutoConnectChange(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
        return;
      }
      v122 = v121 - 2;
      if ( !v122 )
      {
        v133 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v133 > 5u )
        {
          dwDataSize = a2->dwDataSize;
          p_Buf1 = (unsigned __int16 *)&Buf1;
          v150 = "WwanMsmEventTypeProvisioningStateChanged";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            (__int64)v133,
            (__int64)byte_1800775C3,
            v134,
            v135,
            (const unsigned __int16 **)&v150,
            (__int64 *)&p_Buf1,
            (__int64)&dwDataSize);
        }
        CWwanTranslator::_ProcessProvisioningStateChange(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
        return;
      }
      v123 = v122 - 4;
      if ( !v123 )
      {
        v130 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v130 > 5u )
        {
          dwDataSize = a2->dwDataSize;
          p_Buf1 = (unsigned __int16 *)&Buf1;
          v150 = "WwanMsmEventTypeMultiSIMInfo";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            (__int64)v130,
            (__int64)word_18007762A,
            v131,
            v132,
            (const unsigned __int16 **)&v150,
            (__int64 *)&p_Buf1,
            (__int64)&dwDataSize);
        }
        CWwanTranslator::_ProcessMultiSimInfoChange(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
        return;
      }
      if ( v123 == 1 )
      {
        v127 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v127 > 5u )
        {
          dwDataSize = a2->dwDataSize;
          p_Buf1 = (unsigned __int16 *)&Buf1;
          v150 = "WwanMsmEventTypeMultiSIMSlotMapping";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            (__int64)v127,
            (__int64)byte_1800774F5,
            v128,
            v129,
            (const unsigned __int16 **)&v150,
            (__int64 *)&p_Buf1,
            (__int64)&dwDataSize);
        }
        CWwanTranslator::_ProcessMultiSimSlotMappingChange(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
        return;
      }
      goto LABEL_156;
    }
    if ( NotificationCode == 78 )
    {
      v116 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v116 > 5u )
      {
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v150 = "WwanMsmEventTypeNetworkLTEAttachInfo";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (__int64)v116,
          (__int64)&unk_1800776F8,
          v117,
          v118,
          (const unsigned __int16 **)&v150,
          (__int64 *)&p_Buf1,
          (__int64)&dwDataSize);
      }
      CWwanTranslator::_ProcessLTEAttachInfoChanged(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
      return;
    }
    v94 = NotificationCode - 47;
    if ( !v94 )
    {
      v113 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v113 > 5u )
      {
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v150 = "WwanMsmEventTypeProfileIStreamDeleted";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (__int64)v113,
          (__int64)byte_180078073,
          v114,
          v115,
          (const unsigned __int16 **)&v150,
          (__int64 *)&p_Buf1,
          (__int64)&dwDataSize);
      }
      CWwanTranslator::_ProcessProfileDelete(this, &Buf1, (const unsigned __int16 *)a2->pData, a2->dwDataSize);
      return;
    }
    v95 = v94 - 1;
    if ( v95 )
    {
      v96 = v95 - 1;
      if ( v96 )
      {
        v97 = v96 - 10;
        if ( !v97 )
        {
          v105 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v105 > 5u )
          {
            dwDataSize = a2->dwDataSize;
            p_Buf1 = (unsigned __int16 *)&Buf1;
            v150 = "WwanMsmEventTypeDMConfigProfileUpdate";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              (__int64)v105,
              (__int64)&dword_18007755C,
              v106,
              v107,
              (const unsigned __int16 **)&v150,
              (__int64 *)&p_Buf1,
              (__int64)&dwDataSize);
          }
          CWwanTranslator::_ProcessDMConfigProfileChange(
            this,
            &Buf1,
            (struct WWAN_DMPROFILE_UPDATE_INFO *)a2->pData,
            a2->dwDataSize);
          return;
        }
        v98 = v97 - 13;
        if ( !v98 )
        {
          v102 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v102 > 5u )
          {
            dwDataSize = a2->dwDataSize;
            p_Buf1 = (unsigned __int16 *)&Buf1;
            v150 = "WwanMsmEventTypeDataEnablementChange";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              (__int64)v102,
              (__int64)byte_18007782D,
              v103,
              v104,
              (const unsigned __int16 **)&v150,
              (__int64 *)&p_Buf1,
              (__int64)&dwDataSize);
          }
          CWwanTranslator::_ProcessDataEnablementChange(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
          return;
        }
        if ( v98 == 1 )
        {
          v99 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v99 > 5u )
          {
            dwDataSize = a2->dwDataSize;
            p_Buf1 = (unsigned __int16 *)&Buf1;
            v150 = "WwanMsmEventTypeRoamingPolicyChange";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              (__int64)v99,
              (__int64)&byte_18007775F,
              v100,
              v101,
              (const unsigned __int16 **)&v150,
              (__int64 *)&p_Buf1,
              (__int64)&dwDataSize);
          }
          CWwanTranslator::_ProcessRoamingPolicyChange(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
          return;
        }
        goto LABEL_156;
      }
      v108 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v108 > 5u )
      {
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v111 = "WwanMsmEventTypeConnectionIStreamUpdated";
        v112 = &dword_180077BCC;
LABEL_142:
        v150 = v111;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (__int64)v108,
          (__int64)v112,
          v109,
          v110,
          (const unsigned __int16 **)&v150,
          (__int64 *)&p_Buf1,
          (__int64)&dwDataSize);
      }
    }
    else
    {
      v108 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v108 > 5u )
      {
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v111 = "WwanMsmEventTypeConnectionIStreamCreated";
        v112 = (int *)byte_180077B65;
        goto LABEL_142;
      }
    }
    CWwanTranslator::_ProcessConnectionIStream(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
    return;
  }
  if ( NotificationCode == 46 )
  {
    v88 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v88 > 5u )
    {
      dwDataSize = a2->dwDataSize;
      p_Buf1 = (unsigned __int16 *)&Buf1;
      v150 = "WwanMsmEventTypeProfileIStreamUpdated";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        (__int64)v88,
        (__int64)&dword_18007800C,
        v89,
        v90,
        (const unsigned __int16 **)&v150,
        (__int64 *)&p_Buf1,
        (__int64)&dwDataSize);
    }
    if ( a2->dwDataSize >= 0x18D8 )
    {
      CWwanTranslator::_ProcessWwanProfile((__int64)this, (__int64)&Buf1, 3, (__int64)a2->pData, 0);
      return;
    }
    *(_OWORD *)v152 = 0;
    v153 = 0;
    *(_OWORD *)v154 = 0;
    v155 = 0;
    std::vector<unsigned short>::resize(v152);
    std::vector<unsigned short>::resize(v154);
    StringCchPrintfW(v152[0], v152[1] - v152[0], L"Bad notification size. Expected: %ld.", 6360);
    LODWORD(v145) = 623;
    StringCchPrintfW(
      v154[0],
      v154[1] - v154[0],
      L"%S(%d):%s",
      "CWwanTranslator::ProcessWwanNotification",
      v145,
      v152[0]);
    v91 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v91 > 2u )
    {
      p_Buf1 = v154[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v91,
        (__int64)byte_180077F63,
        v92,
        v93,
        (const unsigned __int16 **)&p_Buf1);
    }
    goto LABEL_119;
  }
  if ( NotificationCode > 0x13 )
  {
    v43 = NotificationCode - 23;
    if ( v43 )
    {
      v44 = v43 - 5;
      if ( v44 )
      {
        v45 = v44 - 1;
        if ( v45 )
        {
          v46 = v45 - 1;
          if ( !v46 )
          {
            v58 = MbaeApiLogging::Provider();
            if ( *(_DWORD *)v58 > 5u )
            {
              dwDataSize = a2->dwDataSize;
              p_Buf1 = (unsigned __int16 *)&Buf1;
              v150 = "WwanMsmEventTypeSetRadioStateFailed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
                (__int64)v58,
                (__int64)byte_1800779C9,
                v59,
                v60,
                (const unsigned __int16 **)&v150,
                (__int64 *)&p_Buf1,
                (__int64)&dwDataSize);
            }
            CWwanTranslator::_ProcessRadioState(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize, 0);
            return;
          }
          v47 = v46 - 14;
          if ( !v47 )
          {
            v55 = MbaeApiLogging::Provider();
            if ( *(_DWORD *)v55 > 5u )
            {
              dwDataSize = a2->dwDataSize;
              p_Buf1 = (unsigned __int16 *)&Buf1;
              v150 = "WwanMsmEventTypeIStreamChanged";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
                (__int64)v55,
                (__int64)byte_180078141,
                v56,
                v57,
                (const unsigned __int16 **)&v150,
                (__int64 *)&p_Buf1,
                (__int64)&dwDataSize);
            }
            CWwanTranslator::_ProcessIStreamChanged(this, &Buf1, (unsigned __int8 *)a2->pData);
            return;
          }
          if ( v47 == 1 )
          {
            v48 = MbaeApiLogging::Provider();
            if ( *(_DWORD *)v48 > 5u )
            {
              dwDataSize = a2->dwDataSize;
              p_Buf1 = (unsigned __int16 *)&Buf1;
              v150 = "WwanMsmEventTypeProfileIStreamCreated";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
                (__int64)v48,
                (__int64)word_1800780DA,
                v49,
                v50,
                (const unsigned __int16 **)&v150,
                (__int64 *)&p_Buf1,
                (__int64)&dwDataSize);
            }
            if ( a2->dwDataSize >= 0x18D8 )
            {
              CWwanTranslator::_ProcessProfileAdded(this, &Buf1, v49, a2->pData);
              return;
            }
            *(_OWORD *)v157 = 0;
            v158 = 0;
            *(_OWORD *)v152 = 0;
            v153 = 0;
            std::vector<unsigned short>::resize(v157);
            std::vector<unsigned short>::resize(v152);
            StringCchPrintfW(v157[0], v157[1] - v157[0], L"Bad notification size. Expected: %ld.", 6360);
            LODWORD(v145) = 612;
            StringCchPrintfW(
              v152[0],
              v152[1] - v152[0],
              L"%S(%d):%s",
              "CWwanTranslator::ProcessWwanNotification",
              v145,
              v157[0]);
            v51 = MbaeApiLogging::Provider();
            if ( *(_DWORD *)v51 > 2u )
            {
              p_Buf1 = v152[0];
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                (__int64)v51,
                (__int64)byte_180077FEB,
                v52,
                v53,
                (const unsigned __int16 **)&p_Buf1);
            }
            goto LABEL_68;
          }
LABEL_156:
          *(_OWORD *)v152 = 0;
          v153 = 0;
          *(_OWORD *)v154 = 0;
          v155 = 0;
          std::vector<unsigned short>::resize(v152);
          std::vector<unsigned short>::resize(v154);
          StringCchPrintfW(v152[0], v152[1] - v152[0], L"Ignore notification with code 0x%08x.", a2->NotificationCode);
          StringCchPrintfW(
            v154[0],
            v154[1] - v154[0],
            L"%S(%d):%s",
            "CWwanTranslator::ProcessWwanNotification",
            806,
            v152[0]);
          v124 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v124 > 5u )
          {
            p_Buf1 = v154[0];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (__int64)v124,
              (__int64)&byte_1800774AF,
              v125,
              v126,
              (const unsigned __int16 **)&p_Buf1);
          }
          std::vector<unsigned short>::~vector<unsigned short>((char **)v154);
          goto LABEL_120;
        }
        v61 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v61 <= 5u )
        {
LABEL_79:
          CWwanTranslator::_ProcessRadioState(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize, 1);
          return;
        }
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v64 = "WwanMsmEventTypeSetRadioStateComplete";
        v65 = (__int16 *)&byte_180077A97;
      }
      else
      {
        v61 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v61 <= 5u )
          goto LABEL_79;
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v64 = "WwanMsmEventTypeRadioState";
        v65 = &word_180077AFE;
      }
      v150 = v64;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        (__int64)v61,
        (__int64)v65,
        v62,
        v63,
        (const unsigned __int16 **)&v150,
        (__int64 *)&p_Buf1,
        (__int64)&dwDataSize);
      goto LABEL_79;
    }
    pData = a2->pData;
    if ( *(_DWORD *)pData )
    {
      v77 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v77 > 5u )
      {
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v150 = "WwanMsmEventTypePinActionComplete: Failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (__int64)v77,
          (__int64)&word_180077C96,
          v78,
          v79,
          (const unsigned __int16 **)&v150,
          (__int64 *)&p_Buf1,
          (__int64)&dwDataSize);
      }
      if ( a2->dwDataSize != 24 )
      {
        *(_OWORD *)v152 = 0;
        v153 = 0;
        *(_OWORD *)v154 = 0;
        v155 = 0;
        std::vector<unsigned short>::resize(v152);
        std::vector<unsigned short>::resize(v154);
        StringCchPrintfW(v152[0], v152[1] - v152[0], L"Bad notification size. Expected: %ld.", 24);
        LODWORD(v145) = 701;
        StringCchPrintfW(
          v154[0],
          v154[1] - v154[0],
          L"%S(%d):%s",
          "CWwanTranslator::ProcessWwanNotification",
          v145,
          v152[0]);
        v80 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v80 > 2u )
        {
          p_Buf1 = v154[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v80,
            (__int64)byte_180077C33,
            v81,
            v82,
            (const unsigned __int16 **)&p_Buf1);
        }
        goto LABEL_119;
      }
      if ( CWwanTranslator::GetPinReportedByAdapterId(this, &Buf1, v149, &v148) < 0 )
      {
        *(_OWORD *)v152 = 0;
        v153 = 0;
        *(_OWORD *)v154 = 0;
        v155 = 0;
        std::vector<unsigned short>::resize(v152);
        std::vector<unsigned short>::resize(v154);
        StringCchPrintfW(v152[0], v152[1] - v152[0], L"Error getting pin1Reported and pin2Reported.");
        LODWORD(v145) = 707;
        StringCchPrintfW(
          v154[0],
          v154[1] - v154[0],
          L"%S(%d):%s",
          "CWwanTranslator::ProcessWwanNotification",
          v145,
          v152[0]);
        v83 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v83 > 2u )
        {
          p_Buf1 = v154[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v83,
            (__int64)&dword_180077C54,
            v84,
            v85,
            (const unsigned __int16 **)&p_Buf1);
        }
        goto LABEL_119;
      }
      *(_OWORD *)v157 = *(_OWORD *)pData;
      v158 = pData[2];
      if ( CWwanTranslator::_CheckChainPinOperation(
             (struct _RTL_CRITICAL_SECTION *)this,
             &Buf1,
             (struct _WWAN_PIN_ACTION_RESULT *)v157,
             _mm_cvtsi128_si32(*(__m128i *)v157)) )
      {
        return;
      }
      CWwanTranslator::_ProcessPinAction(
        this,
        &Buf1,
        (const struct _WWAN_PIN_ACTION_RESULT *)v157,
        (unsigned int)v157[0]);
      if ( HIDWORD(v157[1]) == 2 )
      {
        dwDataSize = 0;
        Pin1PreviousState = CWwanTranslator::GetPin1PreviousState(this, &Buf1, (enum _WWAN_PIN_STATE *)&dwDataSize);
        v87 = v158;
        if ( Pin1PreviousState >= 0 )
          v87 = dwDataSize;
        LODWORD(v158) = v87;
      }
    }
    else
    {
      v67 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v67 > 5u )
      {
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v150 = "WwanMsmEventTypePinActionComplete: Success";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (__int64)v67,
          (__int64)byte_180077CFD,
          v68,
          v69,
          (const unsigned __int16 **)&v150,
          (__int64 *)&p_Buf1,
          (__int64)&dwDataSize);
      }
      if ( a2->dwDataSize != 24 )
      {
        *(_OWORD *)v154 = 0;
        v155 = 0;
        *(_OWORD *)v152 = 0;
        v153 = 0;
        std::vector<unsigned short>::resize(v154);
        std::vector<unsigned short>::resize(v152);
        StringCchPrintfW(v154[0], v154[1] - v154[0], L"Bad notification size. Expected: %ld.", 24);
        LODWORD(v145) = 672;
        StringCchPrintfW(
          v152[0],
          v152[1] - v152[0],
          L"%S(%d):%s",
          "CWwanTranslator::ProcessWwanNotification",
          v145,
          v154[0]);
        v70 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v70 > 2u )
        {
          p_Buf1 = v152[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v70,
            (__int64)&dword_180077D64,
            v71,
            v72,
            (const unsigned __int16 **)&p_Buf1);
        }
        std::vector<unsigned short>::~vector<unsigned short>((char **)v152);
        v54 = v154;
        goto LABEL_69;
      }
      if ( CWwanTranslator::GetPinReportedByAdapterId(this, &Buf1, v149, &v148) < 0 )
      {
        *(_OWORD *)v152 = 0;
        v153 = 0;
        *(_OWORD *)v154 = 0;
        v155 = 0;
        std::vector<unsigned short>::resize(v152);
        std::vector<unsigned short>::resize(v154);
        StringCchPrintfW(v152[0], v152[1] - v152[0], L"Error getting pin1Reported and pin2Reported.");
        LODWORD(v145) = 678;
        StringCchPrintfW(
          v154[0],
          v154[1] - v154[0],
          L"%S(%d):%s",
          "CWwanTranslator::ProcessWwanNotification",
          v145,
          v152[0]);
        v73 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v73 > 2u )
        {
          p_Buf1 = v154[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v73,
            (__int64)byte_180077C75,
            v74,
            v75,
            (const unsigned __int16 **)&p_Buf1);
        }
LABEL_119:
        std::vector<unsigned short>::~vector<unsigned short>((char **)v154);
LABEL_120:
        v54 = v152;
        goto LABEL_69;
      }
      *(_OWORD *)v157 = *(_OWORD *)pData;
      v158 = pData[2];
      if ( CWwanTranslator::_CheckChainPinOperation(
             (struct _RTL_CRITICAL_SECTION *)this,
             &Buf1,
             (struct _WWAN_PIN_ACTION_RESULT *)v157,
             0) )
      {
        return;
      }
      CWwanTranslator::_ProcessPinAction(this, &Buf1, (const struct _WWAN_PIN_ACTION_RESULT *)v157, 0);
      v76 = HIDWORD(v158);
      if ( HIDWORD(v157[1]) == *((_DWORD *)pData + 3) )
        v76 = 0;
      HIDWORD(v158) = v76;
    }
    v151 = LODWORD(v157[0]) != 0;
    dwDataSize = 0;
    CWwanTranslator::_ProcessPinInfo(
      this,
      &Buf1,
      (struct _WWAN_PIN_INFO *)((char *)&v157[1] + 4),
      v149,
      &v148,
      &dwDataSize,
      &v151);
    return;
  }
  if ( NotificationCode == 19 )
  {
    if ( !*((_DWORD *)a2->pData + 4) )
    {
      v31 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v31 > 5u )
      {
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v150 = "WwanMsmEventTypeGetPinInfoComplete: Success";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (__int64)v31,
          (__int64)byte_180077E0D,
          v32,
          v33,
          (const unsigned __int16 **)&v150,
          (__int64 *)&p_Buf1,
          (__int64)&dwDataSize);
      }
      if ( CWwanTranslator::GetPinReportedByAdapterId(this, &Buf1, v149, &v148) < 0 )
      {
        *(_OWORD *)v152 = 0;
        v153 = 0;
        *(_OWORD *)v157 = 0;
        v158 = 0;
        std::vector<unsigned short>::resize(v152);
        std::vector<unsigned short>::resize(v157);
        StringCchPrintfW(v152[0], v152[1] - v152[0], L"Error getting pin1Reported and pin2Reported.");
        LODWORD(v145) = 646;
        StringCchPrintfW(
          v157[0],
          v157[1] - v157[0],
          L"%S(%d):%s",
          "CWwanTranslator::ProcessWwanNotification",
          v145,
          v152[0]);
        v34 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v34 > 2u )
        {
          p_Buf1 = v157[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v34,
            (__int64)&dword_180077E74,
            v35,
            v36,
            (const unsigned __int16 **)&p_Buf1);
        }
        std::vector<unsigned short>::~vector<unsigned short>((char **)v157);
        goto LABEL_120;
      }
LABEL_55:
      CWwanTranslator::_ProcessPin(this, a2, v7, v149, &v148);
      return;
    }
    v37 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v37 > 5u )
    {
      dwDataSize = a2->dwDataSize;
      p_Buf1 = (unsigned __int16 *)&Buf1;
      v150 = "WwanMsmEventTypeGetPinInfoComplete: Failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        (__int64)v37,
        (__int64)byte_180077D85,
        v38,
        v39,
        (const unsigned __int16 **)&v150,
        (__int64 *)&p_Buf1,
        (__int64)&dwDataSize);
    }
    if ( CWwanTranslator::GetPinReportedByAdapterId(this, &Buf1, v149, &v148) >= 0 )
    {
      v7 = 0;
      goto LABEL_55;
    }
    *(_OWORD *)v157 = 0;
    v158 = 0;
    *(_OWORD *)v152 = 0;
    v153 = 0;
    std::vector<unsigned short>::resize(v157);
    std::vector<unsigned short>::resize(v152);
    StringCchPrintfW(v157[0], v157[1] - v157[0], L"Error getting pin1Reported and pin2Reported.");
    LODWORD(v145) = 656;
    StringCchPrintfW(
      v152[0],
      v152[1] - v152[0],
      L"%S(%d):%s",
      "CWwanTranslator::ProcessWwanNotification",
      v145,
      v157[0]);
    v40 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v40 > 2u )
    {
      p_Buf1 = v152[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v40,
        (__int64)&dword_180077DEC,
        v41,
        v42,
        (const unsigned __int16 **)&p_Buf1);
    }
LABEL_68:
    std::vector<unsigned short>::~vector<unsigned short>((char **)v152);
    v54 = v157;
LABEL_69:
    std::vector<unsigned short>::~vector<unsigned short>((char **)v54);
    return;
  }
  v10 = NotificationCode - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 3;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 == 11 )
            {
              v15 = MbaeApiLogging::Provider();
              if ( *(_DWORD *)v15 > 5u )
              {
                dwDataSize = a2->dwDataSize;
                v150 = (const char *)&Buf1;
                p_Buf1 = (unsigned __int16 *)"WwanMsmEventTypeSubscriberInfo";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
                  (__int64)v15,
                  (__int64)&dword_180077F84,
                  v16,
                  v17,
                  (const unsigned __int16 **)&p_Buf1,
                  (__int64 *)&v150,
                  (__int64)&dwDataSize);
              }
              CWwanTranslator::_ProcessSubscriberInfo(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
              return;
            }
            goto LABEL_156;
          }
          v18 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v18 > 5u )
          {
            dwDataSize = a2->dwDataSize;
            p_Buf1 = (unsigned __int16 *)&Buf1;
            v21 = "WwanMsmEventTypeDeregistered";
            v22 = &dword_180077EFC;
LABEL_30:
            v150 = v21;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              (__int64)v18,
              (__int64)v22,
              v19,
              v20,
              (const unsigned __int16 **)&v150,
              (__int64 *)&p_Buf1,
              (__int64)&dwDataSize);
          }
        }
        else
        {
          v18 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v18 > 5u )
          {
            dwDataSize = a2->dwDataSize;
            p_Buf1 = (unsigned __int16 *)&Buf1;
            v21 = "WwanMsmEventTypeRegistered";
            v22 = (int *)byte_180077E95;
            goto LABEL_30;
          }
        }
        CWwanTranslator::_ProcessRegisterState(this, &Buf1, (unsigned __int8 *)a2->pData, a2->dwDataSize);
        return;
      }
      v23 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v23 > 5u )
      {
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v26 = "WwanMsmEventTypeScanFailed";
        v27 = word_180077962;
LABEL_36:
        v150 = v26;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (__int64)v23,
          (__int64)v27,
          v24,
          v25,
          (const unsigned __int16 **)&v150,
          (__int64 *)&p_Buf1,
          (__int64)&dwDataSize);
      }
    }
    else
    {
      v23 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v23 > 5u )
      {
        dwDataSize = a2->dwDataSize;
        p_Buf1 = (unsigned __int16 *)&Buf1;
        v26 = "WwanMsmEventTypeScanCompleted";
        v27 = (__int16 *)byte_1800778FB;
        goto LABEL_36;
      }
    }
    CWwanTranslator::_ProcessNetworkScan(this, &Buf1);
    return;
  }
  v28 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v28 > 5u )
  {
    dwDataSize = a2->dwDataSize;
    p_Buf1 = (unsigned __int16 *)&Buf1;
    v150 = "WwanPnpEventTypeInterfaceRemoval";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (__int64)v28,
      (__int64)&unk_180077A30,
      v29,
      v30,
      (const unsigned __int16 **)&v150,
      (__int64 *)&p_Buf1,
      (__int64)&dwDataSize);
  }
  CWwanTranslator::_ProcessInterfaceRemoval(this, &Buf1);
}

```

## disassembly

```asm
0x18003812c  mov     [rsp-8+arg_10], rbx
0x180038131  push    rbp
0x180038132  push    rsi
0x180038133  push    rdi
0x180038134  push    r12
0x180038136  push    r13
0x180038138  push    r14
0x18003813a  push    r15
0x18003813c  lea     rbp, [rsp-27h]
0x180038141  sub     rsp, 0D0h
0x180038148  mov     rax, cs:__security_cookie
0x18003814f  xor     rax, rsp
0x180038152  mov     [rbp+57h+var_40], rax
0x180038156  mov     rbx, rdx
0x180038159  mov     rdi, rcx
0x18003815c  lea     rsi, [rcx+98h]
0x180038163  mov     rcx, rsi; SRWLock
0x180038166  call    cs:__imp_AcquireSRWLockShared
0x18003816c  mov     [rbp+57h+var_B8], rsi
0x180038170  xor     r12d, r12d
0x180038173  cmp     [rdi+20h], r12
0x180038177  jz      short loc_18003818E
0x180038179  mov     rcx, [rdi+88h]; this
0x180038180  test    rcx, rcx
0x180038183  jz      short loc_18003818E
0x180038185  mov     rdx, rbx; struct _L2_NOTIFICATION_DATA *
0x180038188  call    ?OnWwanNotification@SlotBindingMap@@QEAAJPEAU_L2_NOTIFICATION_DATA@@@Z; SlotBindingMap::OnWwanNotification(_L2_NOTIFICATION_DATA *)
0x18003818d  nop
0x18003818e  test    rsi, rsi
0x180038191  jz      short loc_18003819C
0x180038193  mov     rcx, rsi; SRWLock
0x180038196  call    cs:__imp_ReleaseSRWLockShared
0x18003819c  movzx   esi, r12b
0x1800381a0  movups  xmm0, xmmword ptr [rbx+8]
0x1800381a4  movdqu  [rbp+57h+Buf1], xmm0
0x1800381a9  lea     r15, [rdi+28h]
0x1800381ad  mov     rcx, r15; lpCriticalSection
0x1800381b0  call    cs:__imp_EnterCriticalSection
0x1800381b6  mov     r14d, 1
0x1800381bc  cmp     [rdi+18h], r12
0x1800381c0  jz      short loc_1800381FE
0x1800381c2  lea     r8, [rbp+57h+Buf1]
0x1800381c6  lea     rdx, [rbp+57h+var_80]
0x1800381ca  lea     rcx, [rdi+10h]
0x1800381ce  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x1800381d3  mov     r13, [rbp+57h+var_70]
0x1800381d7  cmp     byte ptr [r13+19h], 0
0x1800381dc  jnz     short loc_1800381FB
0x1800381de  lea     rdx, [r13+20h]; Buf2
0x1800381e2  lea     r8d, [r14+0Fh]; Size
0x1800381e6  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800381ea  call    memcmp_0
0x1800381ef  test    eax, eax
0x1800381f1  js      short loc_1800381FB
0x1800381f3  cmp     r13, [rdi+10h]
0x1800381f7  cmovnz  esi, r14d
0x1800381fb  xor     r12d, r12d
0x1800381fe  test    r15, r15
0x180038201  jz      short loc_18003820C
0x180038203  mov     rcx, r15; lpCriticalSection
0x180038206  call    cs:__imp_LeaveCriticalSection
0x18003820c  test    sil, sil
0x18003820f  jz      loc_180039589
0x180038215  mov     [rbp+57h+var_AF], r12b
0x180038219  mov     [rbp+57h+var_B0], r12b
0x18003821d  mov     eax, [rbx+4]
0x180038220  mov     r15d, 5
0x180038226  cmp     eax, 2Eh ; '.'
0x180038229  ja      loc_180038F5D
0x18003822f  jz      loc_180038E2E
0x180038235  cmp     eax, 13h
0x180038238  ja      loc_1800386BF
0x18003823e  jz      loc_18003845A
0x180038244  sub     eax, r14d
0x180038247  jz      loc_1800383FA
0x18003824d  sub     eax, r14d
0x180038250  jz      loc_18003839A
0x180038256  sub     eax, r14d
0x180038259  jz      loc_180038370
0x18003825f  sub     eax, 3
0x180038262  jz      loc_180038308
0x180038268  sub     eax, r14d
0x18003826b  jz      short loc_1800382DE
0x18003826d  cmp     eax, 0Bh
0x180038270  jnz     loc_18003926E
0x180038276  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003827b  mov     ecx, [rax]
0x18003827d  cmp     ecx, r15d
0x180038280  jbe     short loc_1800382C5
0x180038282  mov     ecx, [rbx+18h]
0x180038285  mov     [rbp+57h+var_C0], ecx
0x180038288  lea     rcx, [rbp+57h+Buf1]
0x18003828c  mov     [rbp+57h+var_A8], rcx
0x180038290  lea     rcx, aWwanmsmeventty_18; "WwanMsmEventTypeSubscriberInfo"
0x180038297  mov     [rbp+57h+var_B8], rcx
0x18003829b  lea     rcx, [rbp+57h+var_C0]
0x18003829f  mov     [rsp+100h+var_D0], rcx
0x1800382a4  lea     rcx, [rbp+57h+var_A8]
0x1800382a8  mov     [rsp+100h+var_D8], rcx
0x1800382ad  lea     rcx, [rbp+57h+var_B8]
0x1800382b1  mov     [rsp+100h+var_E0], rcx
0x1800382b6  lea     rdx, dword_180077F84
0x1800382bd  mov     rcx, rax
0x1800382c0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800382c5  mov     r9d, [rbx+18h]; unsigned int
0x1800382c9  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800382cd  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x1800382d1  mov     rcx, rdi; this
0x1800382d4  call    ?_ProcessSubscriberInfo@CWwanTranslator@@AEAAJAEBU_GUID@@PEAEI@Z; CWwanTranslator::_ProcessSubscriberInfo(_GUID const &,uchar *,uint)
0x1800382d9  jmp     loc_180039589
0x1800382de  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800382e3  mov     ecx, [rax]
0x1800382e5  cmp     ecx, r15d
0x1800382e8  jbe     short loc_180038357
0x1800382ea  mov     ecx, [rbx+18h]
0x1800382ed  mov     [rbp+57h+var_C0], ecx
0x1800382f0  lea     rcx, [rbp+57h+Buf1]
0x1800382f4  mov     [rbp+57h+var_B8], rcx
0x1800382f8  lea     rcx, aWwanmsmeventty_4; "WwanMsmEventTypeDeregistered"
0x1800382ff  lea     rdx, dword_180077EFC
0x180038306  jmp     short loc_180038330
0x180038308  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003830d  mov     ecx, [rax]
0x18003830f  cmp     ecx, r15d
0x180038312  jbe     short loc_180038357
0x180038314  mov     ecx, [rbx+18h]
0x180038317  mov     [rbp+57h+var_C0], ecx
0x18003831a  lea     rcx, [rbp+57h+Buf1]
0x18003831e  mov     [rbp+57h+var_B8], rcx
0x180038322  lea     rcx, aWwanmsmeventty_22; "WwanMsmEventTypeRegistered"
0x180038329  lea     rdx, byte_180077E95
0x180038330  mov     [rbp+57h+var_A8], rcx
0x180038334  lea     rcx, [rbp+57h+var_C0]
0x180038338  mov     [rsp+100h+var_D0], rcx
0x18003833d  lea     rcx, [rbp+57h+var_B8]
0x180038341  mov     [rsp+100h+var_D8], rcx
0x180038346  lea     rcx, [rbp+57h+var_A8]
0x18003834a  mov     [rsp+100h+var_E0], rcx
0x18003834f  mov     rcx, rax
0x180038352  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180038357  mov     r9d, [rbx+18h]; unsigned int
0x18003835b  mov     r8, [rbx+20h]; unsigned __int8 *
0x18003835f  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x180038363  mov     rcx, rdi; this
0x180038366  call    ?_ProcessRegisterState@CWwanTranslator@@AEAAJAEBU_GUID@@PEAEK@Z; CWwanTranslator::_ProcessRegisterState(_GUID const &,uchar *,ulong)
0x18003836b  jmp     loc_180039589
0x180038370  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180038375  mov     ecx, [rax]
0x180038377  cmp     ecx, r15d
0x18003837a  jbe     short loc_1800383E9
0x18003837c  mov     ecx, [rbx+18h]
0x18003837f  mov     [rbp+57h+var_C0], ecx
0x180038382  lea     rcx, [rbp+57h+Buf1]
0x180038386  mov     [rbp+57h+var_B8], rcx
0x18003838a  lea     rcx, aWwanmsmeventty_0; "WwanMsmEventTypeScanFailed"
0x180038391  lea     rdx, word_180077962
0x180038398  jmp     short loc_1800383C2
0x18003839a  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003839f  mov     ecx, [rax]
0x1800383a1  cmp     ecx, r15d
0x1800383a4  jbe     short loc_1800383E9
0x1800383a6  mov     ecx, [rbx+18h]
0x1800383a9  mov     [rbp+57h+var_C0], ecx
0x1800383ac  lea     rcx, [rbp+57h+Buf1]
0x1800383b0  mov     [rbp+57h+var_B8], rcx
0x1800383b4  lea     rcx, aWwanmsmeventty_10; "WwanMsmEventTypeScanCompleted"
0x1800383bb  lea     rdx, byte_1800778FB
0x1800383c2  mov     [rbp+57h+var_A8], rcx
0x1800383c6  lea     rcx, [rbp+57h+var_C0]
0x1800383ca  mov     [rsp+100h+var_D0], rcx
0x1800383cf  lea     rcx, [rbp+57h+var_B8]
0x1800383d3  mov     [rsp+100h+var_D8], rcx
0x1800383d8  lea     rcx, [rbp+57h+var_A8]
0x1800383dc  mov     [rsp+100h+var_E0], rcx
0x1800383e1  mov     rcx, rax
0x1800383e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800383e9  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x1800383ed  mov     rcx, rdi; this
0x1800383f0  call    ?_ProcessNetworkScan@CWwanTranslator@@AEAAJAEBU_GUID@@@Z; CWwanTranslator::_ProcessNetworkScan(_GUID const &)
0x1800383f5  jmp     loc_180039589
0x1800383fa  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x1800383ff  mov     ecx, [rax]
0x180038401  cmp     ecx, r15d
0x180038404  jbe     short loc_180038449
0x180038406  mov     ecx, [rbx+18h]
0x180038409  mov     [rbp+57h+var_C0], ecx
0x18003840c  lea     rcx, [rbp+57h+Buf1]
0x180038410  mov     [rbp+57h+var_B8], rcx
0x180038414  lea     rcx, aWwanpnpeventty; "WwanPnpEventTypeInterfaceRemoval"
0x18003841b  mov     [rbp+57h+var_A8], rcx
0x18003841f  lea     rcx, [rbp+57h+var_C0]
0x180038423  mov     [rsp+100h+var_D0], rcx
0x180038428  lea     rcx, [rbp+57h+var_B8]
0x18003842c  mov     [rsp+100h+var_D8], rcx
0x180038431  lea     rcx, [rbp+57h+var_A8]
0x180038435  mov     [rsp+100h+var_E0], rcx
0x18003843a  lea     rdx, unk_180077A30
0x180038441  mov     rcx, rax
0x180038444  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180038449  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x18003844d  mov     rcx, rdi; this
0x180038450  call    ?_ProcessInterfaceRemoval@CWwanTranslator@@AEAAJAEBU_GUID@@@Z; CWwanTranslator::_ProcessInterfaceRemoval(_GUID const &)
0x180038455  jmp     loc_180039589
0x18003845a  mov     rax, [rbx+20h]
0x18003845e  cmp     [rax+10h], r12d
0x180038462  jnz     loc_180038582
0x180038468  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003846d  mov     ecx, [rax]
0x18003846f  cmp     ecx, r15d
0x180038472  jbe     short loc_1800384B7
0x180038474  mov     ecx, [rbx+18h]
0x180038477  mov     [rbp+57h+var_C0], ecx
0x18003847a  lea     rcx, [rbp+57h+Buf1]
0x18003847e  mov     [rbp+57h+var_B8], rcx
0x180038482  lea     rcx, aWwanmsmeventty_25; "WwanMsmEventTypeGetPinInfoComplete: Suc"...
0x180038489  mov     [rbp+57h+var_A8], rcx
0x18003848d  lea     rcx, [rbp+57h+var_C0]
0x180038491  mov     [rsp+100h+var_D0], rcx
0x180038496  lea     rcx, [rbp+57h+var_B8]
0x18003849a  mov     [rsp+100h+var_D8], rcx
0x18003849f  lea     rcx, [rbp+57h+var_A8]
0x1800384a3  mov     [rsp+100h+var_E0], rcx
0x1800384a8  lea     rdx, byte_180077E0D
0x1800384af  mov     rcx, rax
0x1800384b2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800384b7  lea     r9, [rbp+57h+var_B0]; bool *
0x1800384bb  lea     r8, [rbp+57h+var_AF]; bool *
0x1800384bf  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x1800384c3  mov     rcx, rdi; this
0x1800384c6  call    ?GetPinReportedByAdapterId@CWwanTranslator@@AEAAJAEBU_GUID@@AEA_N1@Z; CWwanTranslator::GetPinReportedByAdapterId(_GUID const &,bool &,bool &)
0x1800384cb  test    eax, eax
0x1800384cd  jns     loc_18003869F
0x1800384d3  xorps   xmm0, xmm0
0x1800384d6  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x1800384db  mov     [rbp+57h+var_88], r12
0x1800384df  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x1800384e4  mov     [rbp+57h+var_48], r12
0x1800384e8  lea     rcx, [rbp+57h+var_98]
0x1800384ec  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800384f1  lea     rcx, [rbp+57h+var_58]
0x1800384f5  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800384fa  mov     rdx, [rbp+57h+var_98+8]
0x1800384fe  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x180038502  sub     rdx, rcx
0x180038505  sar     rdx, 1; unsigned __int64
0x180038508  lea     r8, aErrorGettingPi; "Error getting pin1Reported and pin2Repo"...
0x18003850f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038514  mov     rdx, [rbp+57h+var_58+8]
0x180038518  mov     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x18003851c  sub     rdx, rcx
0x18003851f  sar     rdx, 1; unsigned __int64
0x180038522  mov     rax, [rbp+57h+var_98]
0x180038526  mov     [rsp+100h+var_D8], rax
0x18003852b  mov     dword ptr [rsp+100h+var_E0], 286h
0x180038533  lea     r9, aCwwantranslato_69; "CWwanTranslator::ProcessWwanNotificatio"...
0x18003853a  lea     r8, aSDS; "%S(%d):%s"
0x180038541  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180038546  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003854b  mov     ecx, [rax]
0x18003854d  cmp     ecx, 2
0x180038550  jbe     short loc_180038573
0x180038552  mov     rcx, [rbp+57h+var_58]
0x180038556  mov     [rbp+57h+var_B8], rcx
0x18003855a  lea     rcx, [rbp+57h+var_B8]
0x18003855e  mov     [rsp+100h+var_E0], rcx
0x180038563  lea     rdx, dword_180077E74
0x18003856a  mov     rcx, rax
0x18003856d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180038572  nop
0x180038573  lea     rcx, [rbp+57h+var_58]
0x180038577  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003857c  nop
0x18003857d  jmp     loc_180038F54
0x180038582  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180038587  mov     ecx, [rax]
0x180038589  cmp     ecx, r15d
0x18003858c  jbe     short loc_1800385D1
0x18003858e  mov     ecx, [rbx+18h]
0x180038591  mov     [rbp+57h+var_C0], ecx
0x180038594  lea     rcx, [rbp+57h+Buf1]
0x180038598  mov     [rbp+57h+var_B8], rcx
0x18003859c  lea     rcx, aWwanmsmeventty_5; "WwanMsmEventTypeGetPinInfoComplete: Fai"...
0x1800385a3  mov     [rbp+57h+var_A8], rcx
0x1800385a7  lea     rcx, [rbp+57h+var_C0]
0x1800385ab  mov     [rsp+100h+var_D0], rcx
0x1800385b0  lea     rcx, [rbp+57h+var_B8]
0x1800385b4  mov     [rsp+100h+var_D8], rcx
0x1800385b9  lea     rcx, [rbp+57h+var_A8]
0x1800385bd  mov     [rsp+100h+var_E0], rcx
0x1800385c2  lea     rdx, byte_180077D85
0x1800385c9  mov     rcx, rax
0x1800385cc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800385d1  lea     r9, [rbp+57h+var_B0]; bool *
0x1800385d5  lea     r8, [rbp+57h+var_AF]; bool *
0x1800385d9  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x1800385dd  mov     rcx, rdi; this
0x1800385e0  call    ?GetPinReportedByAdapterId@CWwanTranslator@@AEAAJAEBU_GUID@@AEA_N1@Z; CWwanTranslator::GetPinReportedByAdapterId(_GUID const &,bool &,bool &)
0x1800385e5  test    eax, eax
0x1800385e7  jns     loc_18003869C
0x1800385ed  xorps   xmm0, xmm0
  ... truncated ...
```
