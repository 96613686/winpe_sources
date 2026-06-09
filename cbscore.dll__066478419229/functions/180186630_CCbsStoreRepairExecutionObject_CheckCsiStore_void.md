# CCbsStoreRepairExecutionObject::CheckCsiStore(void)

- ea: `0x180186630`
- end: `0x18018764a`
- name: `?CheckCsiStore@CCbsStoreRepairExecutionObject@@IEAAJXZ`
- size: `4122`
- prototype: `__int64 __fastcall(CCbsStoreRepairExecutionObject *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180189b14`

## callees

- `0x180010cc0`
- `0x180012fe4`
- `0x180015420`
- `0x18001de20`
- `0x18002e0d0`
- `0x18004854c`
- `0x18004a920`
- `0x180095924`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800c3370`
- `0x1800eb920`
- `0x1800ef360`
- `0x1800f19ec`
- `0x180177464`
- `0x180184a08`
- `0x180186630`
- `0x1801888dc`
- `0x18018d710`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180186771`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180186771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018753b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18018753b`

## string_xrefs

- `0x1801868d3`: `Failed to convert ICSIStore to a service provider.`
- `0x18018671e`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x18018680c`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180186b05`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180186f96`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x1801873c8`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x1801875b4`: `onecore\base\cbs\core\cbsstorerepairexecutionobject.cpp`
- `0x180186ccf`: `Repr: Non CBS installed component found, ignore it since it is not repairble`
- `0x180186c3f`: `Rept: Failed to enumerate corrupted components.`
- `0x180186b35`: `Repr: CSI meta data corruption found, will commit repair transaction if repair is asked.`
- `0x180186ec7`: `Repr: Non CBS installed component found when attempting to find owner for corrupt file: {}, ignore it since it is not repairble`
- `0x180187210`: `Repr: Non CBS installed component found when attempting to find owner for corrupt file: {}, ignore it since it is not repairble`
- `0x180186d49`: `Invalid component corruption type {}`
- `0x180186d9f`: `Failed to create a new corrupted component entry.`
- `0x1801870e8`: `Failed to create a new corrupted component entry.`
- `0x180187458`: `Failed to create a new corrupted component entry.`
- `0x18018755a`: `Repr: Failed to create cancel event.`
- `0x1801866df`: `Repair transaction is already active`
- `0x1801869e2`: `Repr: Failed to get repair transaction.`

## pseudocode

```c
__int64 __fastcall CCbsStoreRepairExecutionObject::CheckCsiStore(CCbsStoreRepairExecutionObject *this)
{
  _QWORD *v2; // r15
  signed int CorruptComponentEntry; // ebx
  int v4; // edx
  void (*v5)(void); // rax
  char *EventW; // rbx
  CCbsSession *v7; // rdi
  struct ICSIStore **InitPointer; // rax
  signed int Store; // eax
  int v10; // edi
  int v11; // edx
  __int64 v12; // rdx
  __int64 (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v15)(_QWORD, GUID *, __int64); // rdi
  __int64 v16; // rax
  signed int v17; // eax
  int v18; // edx
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, GUID *, GUID *, __int64); // rdi
  __int64 v21; // rax
  signed int v22; // eax
  int v23; // edx
  signed int v24; // eax
  int v25; // edx
  unsigned int v26; // edi
  signed int v27; // eax
  int v28; // edx
  __int64 v29; // rdx
  int v30; // ecx
  bool v31; // zf
  __int64 v32; // rax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, _QWORD, __int64, int *); // rbx
  __int64 v35; // rax
  signed int v36; // eax
  int v37; // edx
  struct CorruptPackage::CorruptComponent *v38; // rcx
  int v39; // edx
  int v40; // edx
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, _QWORD, __int64, int *); // rbx
  __int64 v43; // rax
  int v44; // eax
  int v45; // edx
  int v46; // edx
  CorruptPackage::CorruptComponent::CorruptedFile *v47; // rbx
  struct CorruptPackage::CorruptComponent *v48; // r13
  __int64 v49; // rdx
  unsigned int v50; // edx
  int v51; // edx
  int v52; // edx
  int v53; // edx
  int v54; // edx
  __int64 v55; // rdi
  __int64 (__fastcall *v56)(__int64, _QWORD, __int64, int *); // rbx
  __int64 v57; // rax
  int v58; // eax
  int v59; // edx
  int v60; // edx
  struct CorruptPackage::CorruptComponent *v61; // rcx
  int v62; // edx
  __int64 v63; // rdx
  int v64; // edx
  int v65; // edx
  void (*v66)(void); // rax
  int v67; // edx
  signed int LastError; // ebx
  int v69; // edx
  unsigned int v70; // eax
  unsigned int v71; // [rsp+20h] [rbp-99h]
  char v72[8]; // [rsp+30h] [rbp-89h] BYREF
  __int64 (__fastcall ***v73)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-81h] BYREF
  CorruptPackage::CorruptComponent::CorruptedFile *v74; // [rsp+40h] [rbp-79h] BYREF
  __int64 v75; // [rsp+48h] [rbp-71h] BYREF
  char *v76; // [rsp+50h] [rbp-69h] BYREF
  struct IDefinitionIdentity *v77[2]; // [rsp+58h] [rbp-61h] BYREF
  __int128 v78; // [rsp+68h] [rbp-51h] BYREF
  __int128 v79; // [rsp+78h] [rbp-41h]
  __int64 v80; // [rsp+88h] [rbp-31h] BYREF
  unsigned int v81; // [rsp+90h] [rbp-29h] BYREF
  __int64 v82; // [rsp+98h] [rbp-21h] BYREF
  __int64 v83; // [rsp+A0h] [rbp-19h] BYREF
  struct CorruptPackage::CorruptComponent *v84; // [rsp+A8h] [rbp-11h] BYREF
  int v85; // [rsp+B0h] [rbp-9h] BYREF
  int v86; // [rsp+B4h] [rbp-5h] BYREF
  __int64 v87; // [rsp+B8h] [rbp-1h] BYREF
  int v88; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v83 = 0;
  v73 = 0;
  v80 = 0;
  v88 = 0;
  v72[0] = 1;
  v82 = 0;
  v86 = 0;
  v75 = 0;
  v87 = 0;
  v74 = 0;
  v81 = 0;
  v85 = 0;
  *(_OWORD *)v77 = 0;
  v78 = 0;
  v79 = 0;
  if ( vpfnTiLockProcess )
    vpfnTiLockProcess(0);
  v2 = (_QWORD *)((char *)this + 344);
  if ( *((_QWORD *)this + 43) )
  {
    CorruptComponentEntry = -2146498560;
    v81 = -2146498560;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Repair transaction is already active");
      v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v81;
      LOBYTE(v4) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v4,
        3,
        (unsigned int)": {}",
        (__int64)&v74);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
      (const char *)0x800F0800LL,
      v71);
LABEL_7:
    AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v72);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v75);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v82);
    if ( v80 )
    {
      v5 = *(void (**)(void))(*(_QWORD *)v80 + 16LL);
LABEL_165:
      v5();
      v80 = 0;
      goto LABEL_166;
    }
    goto LABEL_166;
  }
  EventW = (char *)CreateEventW(0, 0, 0, 0);
  v76 = EventW;
  if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Repr: Failed to create cancel event.");
      if ( LastError > 0 )
        v70 = (unsigned __int16)LastError | 0x80070000;
      else
        v70 = LastError;
      LODWORD(v84) = v70;
      LOBYTE(v69) = 1;
      v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v84;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v69,
        3,
        (unsigned int)": {0}",
        (__int64)&v74);
    }
    if ( LastError )
    {
      CorruptComponentEntry = wil::details::in1diag3::Return_Win32(
                                retaddr,
                                (void *)0x422,
                                (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
                                (const char *)(unsigned int)LastError,
                                v71);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v76);
      AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v72);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v75);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v82);
      if ( v80 )
      {
        v5 = *(void (**)(void))(*(_QWORD *)v80 + 16LL);
        goto LABEL_165;
      }
LABEL_166:
      if ( v73 )
      {
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v73)[2])(v73);
        v73 = 0;
      }
      if ( v83 )
      {
        v66 = *(void (**)(void))(*(_QWORD *)v83 + 16LL);
LABEL_170:
        v66();
      }
      return (unsigned int)CorruptComponentEntry;
    }
    goto LABEL_150;
  }
  v7 = (CCbsSession *)*((_QWORD *)this + 6);
  InitPointer = (struct ICSIStore **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v73);
  Store = CCbsSession::GetStore(v7, InitPointer);
  v10 = Store;
  if ( Store < 0 )
  {
    v81 = Store;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get CSI session store.");
      v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v81;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)&v74);
    }
    v12 = 1060;
    goto LABEL_14;
  }
  v14 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v73;
  v15 = **v73;
  v16 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v80);
  v17 = v15(v14, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa, v16);
  v10 = v17;
  if ( v17 < 0 )
  {
    v81 = v17;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed to convert ICSIStore to a service provider.");
      v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v81;
      LOBYTE(v18) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v18,
        3,
        (unsigned int)": {}",
        (__int64)&v74);
    }
    v12 = 1064;
    goto LABEL_14;
  }
  v19 = v80;
  v20 = *(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64))(*(_QWORD *)v80 + 24LL);
  v21 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v83);
  v22 = v20(v19, &GUID_a817521b_2b43_489f_8b84_67aceeab24a8, &GUID_a817521b_2b43_489f_8b84_67aceeab24a8, v21);
  v10 = v22;
  if ( v22 < 0 )
  {
    v81 = v22;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Repr: Failed to get store2.");
      v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v81;
      LOBYTE(v23) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v23,
        3,
        (unsigned int)": {}",
        (__int64)&v74);
    }
    v12 = 1067;
    goto LABEL_14;
  }
  if ( *v2 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x180187649LL);
  }
  v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, char *))(*(_QWORD *)v83 + 328LL))(
          v83,
          0,
          &v88,
          (char *)this + 344);
  v10 = v24;
  if ( v24 >= 0 )
  {
    if ( *((_DWORD *)this + 92) )
    {
      v26 = 4;
      if ( !CbsRegQueryDWORDValue(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\Servicing",
              1u,
              L"IgnorePayloadCorruption",
              &v81)
        && v81 )
      {
        LogAdapter::TraceAtLevel<>(
          1,
          "Repr: GPO ignore payload corruption is set, detection will only check for payload missing.");
        v26 = 12;
      }
    }
    else
    {
      v26 = 20;
    }
    if ( *((_BYTE *)this + 365) )
      v26 = 32;
    v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, int *))(*(_QWORD *)*v2 + 24LL))(*v2, v26, EventW, &v85);
    CorruptComponentEntry = v27;
    if ( v27 < 0 )
    {
      v81 = v27;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Rept: Failed to call CSI detect.");
        v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v81;
        LOBYTE(v28) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v28,
          3,
          (unsigned int)": {}",
          (__int64)&v74);
      }
      v29 = 1103;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v29,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
        (const char *)(unsigned int)CorruptComponentEntry,
        v71);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v76);
      goto LABEL_7;
    }
    v30 = v85;
    v31 = (v85 & 0x10000) == 0;
    *((_DWORD *)this + 101) = v85 & 0x10000;
    if ( !v31 )
    {
      LogAdapter::TraceAtLevel<>(
        1,
        "Repr: CSI meta data corruption found, will commit repair transaction if repair is asked.");
      v30 = v85;
    }
    if ( (unsigned __int16)v30 == 3 )
    {
      *((_DWORD *)this + 88) = 1;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v76);
      AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v72);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v75);
      Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v82);
      if ( v80 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
        v80 = 0;
      }
      if ( v73 )
      {
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v73)[2])(v73);
        v73 = 0;
      }
      if ( v83 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
      return 2148468769LL;
    }
    if ( (v30 & 0xFFFF0000) != 0x20000 )
    {
      v32 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v75);
      GetTaskAllocator(v32);
      v33 = *v2;
      v84 = 0;
      v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *))(*(_QWORD *)v33 + 32LL);
      v35 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v82);
      v36 = v34(v33, 0, v35, &v86);
      CorruptComponentEntry = v36;
      if ( v36 >= 0 )
      {
        while ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct IDefinitionIdentity **, __int64 *))(*(_QWORD *)v82 + 24LL))(
                   v82,
                   1,
                   v77,
                   &v87)
             && v87 )
        {
          CorruptComponentEntry = CCbsStoreRepairExecutionObject::GetCorruptComponentEntry(this, v77[1], &v84);
          if ( CorruptComponentEntry == -2146498292 )
          {
            LogAdapter::TraceAtLevel<>(
              1,
              "Repr: Non CBS installed component found, ignore it since it is not repairble");
          }
          else
          {
            if ( CorruptComponentEntry < 0 )
            {
              LODWORD(v84) = CorruptComponentEntry;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(
                  LogAdapter::g_Logger,
                  0,
                  3,
                  "Failed to create a new corrupted component entry.");
                v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v84;
                LOBYTE(v40) = 1;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v40,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v74);
              }
              v29 = 1154;
              goto LABEL_46;
            }
            if ( LODWORD(v77[0]) == 1 )
            {
              v38 = v84;
              *((_BYTE *)v84 + 92) = 1;
            }
            else
            {
              if ( LODWORD(v77[0]) != 3 )
              {
                CorruptComponentEntry = -2146498560;
                v81 = -2146498560;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<unsigned long>(
                    (_DWORD)LogAdapter::g_Logger,
                    0,
                    3,
                    (unsigned int)"Invalid component corruption type {}",
                    (__int64)v77);
                  v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v81;
                  LOBYTE(v39) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v39,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v74);
                }
                v29 = 1166;
                goto LABEL_46;
              }
              v38 = v84;
              ++*((_DWORD *)v84 + 22);
            }
            *((_BYTE *)v38 + 100) = (_DWORD)v79 != 0;
            *((_DWORD *)v38 + 24) = DWORD1(v79);
            *((_BYTE *)v38 + 101) = DWORD2(v79) != 0;
          }
          ClearCorruptComponentStructure(v75, v77);
        }
        Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v82);
        v41 = *v2;
        v42 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *))(*(_QWORD *)*v2 + 40LL);
        v43 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v82);
        v44 = v42(v41, 0, v43, &v86);
        CorruptComponentEntry = v44;
        if ( v44 >= 0 )
        {
          while ( !(*(unsigned int (__fastcall **)(__int64, __int64, struct IDefinitionIdentity **, __int64 *))(*(_QWORD *)v82 + 24LL))(
                     v82,
                     1,
                     v77,
                     &v87)
               && v87 )
          {
            CorruptComponentEntry = CCbsStoreRepairExecutionObject::GetCorruptComponentEntry(this, v77[1], &v84);
            if ( CorruptComponentEntry == -2146498292 )
            {
              if ( LogAdapter::g_Logger )
              {
                LOBYTE(v46) = 1;
                LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                  (_DWORD)LogAdapter::g_Logger,
                  v46,
                  1,
                  (unsigned int)"Repr: Non CBS installed component found when attempting to find owner for corrupt file: "
                                "{}, ignore it since it is not repairble",
                  (__int64)&v78);
              }
              ClearCorruptComponentStructure(v75, v77);
            }
            else
            {
              if ( CorruptComponentEntry < 0 )
              {
                v81 = CorruptComponentEntry;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to create a new corrupted component entry.");
                  v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v81;
                  LOBYTE(v54) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v54,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v74);
                }
                v29 = 1198;
                goto LABEL_46;
              }
              if ( LODWORD(v77[0]) != 2 )
              {
                CorruptComponentEntry = -2146498560;
                LODWORD(v84) = -2146498560;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Expecting payload corruption");
                  v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v84;
                  LOBYTE(v53) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v53,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v74);
                }
                v29 = 1203;
                goto LABEL_46;
              }
              if ( !(_QWORD)v78 )
              {
                CorruptComponentEntry = -2146498560;
                LODWORD(v84) = -2146498560;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Expecting valid file name");
                  v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v84;
                  LOBYTE(v52) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v52,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v74);
                }
                v29 = 1204;
                goto LABEL_46;
              }
              Windows::AutoNewPtr<CorruptPackage::CorruptComponent::CorruptedFile>::Allocate<>(&v74);
              v47 = v74;
              if ( !v74 )
              {
                CorruptComponentEntry = -2147024882;
                LODWORD(v84) = -2147024882;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(
                    LogAdapter::g_Logger,
                    0,
                    3,
                    "Failed to allocate corruption file structure");
                  v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v84;
                  LOBYTE(v51) = 1;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v51,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v74);
                }
                v29 = 1207;
                goto LABEL_46;
              }
              v10 = SczAllocFromSz(v74, v78);
              if ( v10 < 0 )
              {
                v49 = 1209;
LABEL_98:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v49,
                  (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
                  (const char *)(unsigned int)v10,
                  v71);
                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v76);
                AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v72);
                if ( v47 )
                  CorruptPackage::CorruptComponent::CorruptedFile::`scalar deleting destructor'(v47, v50);
                goto LABEL_15;
              }
              v48 = v84;
              *((_DWORD *)v47 + 6) = 2;
              v74 = v47;
              *((_BYTE *)v47 + 12) = (_DWORD)v79 != 0;
              *((_DWORD *)v47 + 2) = DWORD1(v79);
              v10 = CCbsArrayBase<CCbsTask *,CCbsPointerArray<CCbsTask *>>::Add(v48, &v74);
              if ( v10 < 0 )
              {
                v49 = 1215;
                goto LABEL_98;
              }
              v74 = 0;
              *((_BYTE *)v48 + 101) = DWORD2(v79) != 0;
              ClearCorruptComponentStructure(v75, v77);
            }
          }
          Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v82);
          v55 = *v2;
          v56 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, int *))(*(_QWORD *)*v2 + 48LL);
          v57 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v82);
          v58 = v56(v55, 0, v57, &v86);
          CorruptComponentEntry = v58;
          if ( v58 >= 0 )
          {
            while ( 1 )
            {
              if ( (*(unsigned int (__fastcall **)(__int64, __int64, struct IDefinitionIdentity **, __int64 *))(*(_QWORD *)v82 + 24LL))(
                     v82,
                     1,
                     v77,
                     &v87)
                || !v87 )
              {
                goto LABEL_149;
              }
              CorruptComponentEntry = CCbsStoreRepairExecutionObject::GetCorruptComponentEntry(this, v77[1], &v84);
              if ( CorruptComponentEntry == -2146498292 )
              {
                if ( LogAdapter::g_Logger )
                {
                  LOBYTE(v60) = 1;
                  LogAdapter::Logger::LogNumObjects<wchar_t const *>(
                    (_DWORD)LogAdapter::g_Logger,
                    v60,
                    1,
                    (unsigned int)"Repr: Non CBS installed component found when attempting to find owner for corrupt file"
                                  ": {}, ignore it since it is not repairble",
                    (__int64)&v78);
                }
              }
              else
              {
                if ( CorruptComponentEntry < 0 )
                {
                  v81 = CorruptComponentEntry;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to create a new corrupted component entry.");
                    v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v81;
                    LOBYTE(v67) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v67,
                      3,
                      (unsigned int)": {}",
                      (__int64)&v74);
                  }
                  v29 = 1245;
                  goto LABEL_46;
                }
                if ( LODWORD(v77[0]) != 4 )
                {
                  CorruptComponentEntry = -2146498560;
                  LODWORD(v84) = -2146498560;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      LogAdapter::g_Logger,
                      0,
                      3,
                      "Expecting payload delta corruption");
                    v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v84;
                    LOBYTE(v65) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v65,
                      3,
                      (unsigned int)": {}",
                      (__int64)&v74);
                  }
                  v63 = 1250;
LABEL_140:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v63,
                    (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
                    (const char *)(unsigned int)CorruptComponentEntry,
                    v71);
                  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v76);
                  AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v72);
                  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v75);
                  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v82);
                  if ( v80 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
                    v80 = 0;
                  }
                  if ( v73 )
                  {
                    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v73)[2])(v73);
                    v73 = 0;
                  }
                  if ( v83 )
                  {
                    v66 = *(void (**)(void))(*(_QWORD *)v83 + 16LL);
                    goto LABEL_170;
                  }
                  return (unsigned int)CorruptComponentEntry;
                }
                if ( !(_QWORD)v78 )
                {
                  CorruptComponentEntry = -2146498560;
                  LODWORD(v84) = -2146498560;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Expecting valid file name");
                    v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v84;
                    LOBYTE(v64) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v64,
                      3,
                      (unsigned int)": {}",
                      (__int64)&v74);
                  }
                  v29 = 1251;
                  goto LABEL_46;
                }
                Windows::AutoNewPtr<CorruptPackage::CorruptComponent::CorruptedFile>::Allocate<>(&v74);
                v47 = v74;
                if ( !v74 )
                {
                  CorruptComponentEntry = -2147024882;
                  LODWORD(v84) = -2147024882;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(
                      LogAdapter::g_Logger,
                      0,
                      3,
                      "Failed to allocate corruption file structure");
                    v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v84;
                    LOBYTE(v62) = 1;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v62,
                      3,
                      (unsigned int)": {}",
                      (__int64)&v74);
                  }
                  v63 = 1254;
                  goto LABEL_140;
                }
                v10 = SczAllocFromSz(v74, v78);
                if ( v10 < 0 )
                {
                  v49 = 1256;
                  goto LABEL_98;
                }
                v61 = v84;
                *((_DWORD *)v47 + 6) = 4;
                v74 = v47;
                *((_BYTE *)v47 + 12) = (_DWORD)v79 != 0;
                *((_DWORD *)v47 + 2) = DWORD1(v79);
                v10 = CCbsArrayBase<CCbsTask *,CCbsPointerArray<CCbsTask *>>::Add(v61, &v74);
                if ( v10 < 0 )
                {
                  v49 = 1262;
                  goto LABEL_98;
                }
                v74 = 0;
              }
              ClearCorruptComponentStructure(v75, v77);
            }
          }
          LODWORD(v84) = v58;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Rept: Failed to enumerate corrupted files.");
            v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v84;
            LOBYTE(v59) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v59,
              3,
              (unsigned int)": {}",
              (__int64)&v74);
          }
          v29 = 1229;
        }
        else
        {
          LODWORD(v84) = v44;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Rept: Failed to enumerate corrupted files.");
            v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v84;
            LOBYTE(v45) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v45,
              3,
              (unsigned int)": {}",
              (__int64)&v74);
          }
          v29 = 1182;
        }
      }
      else
      {
        v81 = v36;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Rept: Failed to enumerate corrupted components.");
          v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v81;
          LOBYTE(v37) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v37,
            3,
            (unsigned int)": {}",
            (__int64)&v74);
        }
        v29 = 1141;
      }
      goto LABEL_46;
    }
LABEL_149:
    ClearCorruptComponentStructure(v75, v77);
LABEL_150:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v76);
    AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v72);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v75);
    Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v82);
    if ( v80 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
      v80 = 0;
    }
    if ( v73 )
    {
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v73)[2])(v73);
      v73 = 0;
    }
    if ( v83 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
    return 0;
  }
  v81 = v24;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Repr: Failed to get repair transaction.");
    v74 = (CorruptPackage::CorruptComponent::CorruptedFile *)&v81;
    LOBYTE(v25) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v25,
      3,
      (unsigned int)": {}",
      (__int64)&v74);
  }
  v12 = 1070;
LABEL_14:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\base\\cbs\\core\\cbsstorerepairexecutionobject.cpp",
    (const char *)(unsigned int)v10,
    v71);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v76);
  AutoCsiStoreLock::~AutoCsiStoreLock((AutoCsiStoreLock *)v72);
LABEL_15:
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v75);
  Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(&v82);
  if ( v80 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    v80 = 0;
  }
  if ( v73 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v73)[2])(v73);
    v73 = 0;
  }
  if ( v83 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180186630  push    rbp
0x180186632  push    rbx
0x180186633  push    rsi
0x180186634  push    rdi
0x180186635  push    r12
0x180186637  push    r13
0x180186639  push    r14
0x18018663b  push    r15
0x18018663d  lea     rbp, [rsp-1Fh]
0x180186642  sub     rsp, 0D8h
0x180186649  mov     rax, cs:__security_cookie
0x180186650  xor     rax, rsp
0x180186653  mov     [rbp+57h+var_48], rax
0x180186657  mov     rax, cs:?vpfnTiLockProcess@@3P6AHH@ZEA; int (*vpfnTiLockProcess)(int)
0x18018665e  xor     r12d, r12d
0x180186661  mov     [rbp+57h+var_70], r12
0x180186665  xorps   xmm0, xmm0
0x180186668  mov     [rsp+110h+var_D8], r12
0x18018666d  mov     r14, rcx
0x180186670  mov     [rbp+57h+var_88], r12
0x180186674  mov     [rbp+57h+var_50], r12d
0x180186678  lea     r13d, [r12+1]
0x18018667d  mov     [rsp+110h+var_E0], r13b
0x180186682  mov     [rbp+57h+var_78], r12
0x180186686  mov     [rbp+57h+var_5C], r12d
0x18018668a  mov     [rbp+57h+var_C8], r12
0x18018668e  mov     [rbp+57h+var_58], r12
0x180186692  mov     [rbp+57h+var_D0], r12
0x180186696  mov     [rbp+57h+var_80], r12d
0x18018669a  mov     [rbp+57h+var_60], r12d
0x18018669e  movups  xmmword ptr [rbp+57h+var_B8], xmm0
0x1801866a2  movups  [rbp+57h+var_A8], xmm0
0x1801866a6  movups  [rbp+57h+var_98], xmm0
0x1801866aa  test    rax, rax
0x1801866ad  jz      short loc_1801866B6
0x1801866af  xor     ecx, ecx
0x1801866b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801866b6  lea     r15, [r14+158h]
0x1801866bd  cmp     [r15], r12
0x1801866c0  jz      loc_180186767
0x1801866c6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801866cd  mov     ebx, 800F0800h
0x1801866d2  mov     [rbp+57h+var_80], ebx
0x1801866d5  test    rcx, rcx
0x1801866d8  jz      short loc_18018671A
0x1801866da  mov     esi, 3
0x1801866df  lea     r9, aRepairTransact; "Repair transaction is already active"
0x1801866e6  mov     r8d, esi
0x1801866e9  xor     edx, edx
0x1801866eb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801866f0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801866f7  lea     rax, [rbp+57h+var_80]
0x1801866fb  mov     [rbp+57h+var_D0], rax
0x1801866ff  lea     r9, asc_1802EE7AC; ": {}"
0x180186706  lea     rax, [rbp+57h+var_D0]
0x18018670a  mov     r8d, esi
0x18018670d  mov     dl, r13b
0x180186710  mov     qword ptr [rsp+110h+var_F0], rax; int
0x180186715  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018671a  mov     rcx, [rbp+5Fh]; this
0x18018671e  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x180186725  mov     r9d, ebx; char *
0x180186728  mov     edx, 41Fh; void *
0x18018672d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180186732  lea     rcx, [rsp+110h+var_E0]; this
0x180186737  call    ??1AutoCsiStoreLock@@QEAA@XZ; AutoCsiStoreLock::~AutoCsiStoreLock(void)
0x18018673c  lea     rcx, [rbp+57h+var_C8]
0x180186740  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180186745  lea     rcx, [rbp+57h+var_78]
0x180186749  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x18018674e  mov     rcx, [rbp+57h+var_88]
0x180186752  test    rcx, rcx
0x180186755  jz      loc_180187608
0x18018675b  mov     rax, [rcx]
0x18018675e  mov     rax, [rax+10h]
0x180186762  jmp     loc_1801875FF
0x180186767  xor     r9d, r9d; lpName
0x18018676a  xor     r8d, r8d; bInitialState
0x18018676d  xor     edx, edx; bManualReset
0x18018676f  xor     ecx, ecx; lpEventAttributes
0x180186771  call    cs:__imp_CreateEventW
0x180186778  nop     dword ptr [rax+rax+00h]
0x18018677d  mov     rbx, rax
0x180186780  mov     [rbp+57h+var_C0], rax
0x180186784  dec     rax
0x180186787  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18018678b  ja      loc_18018753B
0x180186791  mov     rdi, [r14+30h]
0x180186795  lea     rcx, [rsp+110h+var_D8]
0x18018679a  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18018679f  mov     rdx, rax; struct ICSIStore **
0x1801867a2  mov     rcx, rdi; this
0x1801867a5  call    ?GetStore@CCbsSession@@QEAAJPEAPEAUICSIStore@@@Z; CCbsSession::GetStore(ICSIStore * *)
0x1801867aa  mov     edi, eax
0x1801867ac  test    eax, eax
0x1801867ae  jns     loc_180186890
0x1801867b4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801867bb  mov     [rbp+57h+var_80], eax
0x1801867be  test    rcx, rcx
0x1801867c1  jz      short loc_180186803
0x1801867c3  mov     esi, 3
0x1801867c8  lea     r9, aFailedToGetCsi_2; "Failed to get CSI session store."
0x1801867cf  mov     r8d, esi
0x1801867d2  xor     edx, edx
0x1801867d4  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801867d9  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801867e0  lea     rax, [rbp+57h+var_80]
0x1801867e4  mov     [rbp+57h+var_D0], rax
0x1801867e8  lea     r9, asc_1802EE7AC; ": {}"
0x1801867ef  lea     rax, [rbp+57h+var_D0]
0x1801867f3  mov     r8d, esi
0x1801867f6  mov     dl, r13b
0x1801867f9  mov     qword ptr [rsp+110h+var_F0], rax; int
0x1801867fe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180186803  mov     edx, 424h; void *
0x180186808  mov     rcx, [rbp+5Fh]; this
0x18018680c  lea     r8, Str; "onecore\\base\\cbs\\core\\cbsstorerepai"...
0x180186813  mov     r9d, edi; char *
0x180186816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018681b  lea     rcx, [rbp+57h+var_C0]
0x18018681f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180186824  lea     rcx, [rsp+110h+var_E0]; this
0x180186829  call    ??1AutoCsiStoreLock@@QEAA@XZ; AutoCsiStoreLock::~AutoCsiStoreLock(void)
0x18018682e  lea     rcx, [rbp+57h+var_C8]
0x180186832  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180186837  lea     rcx, [rbp+57h+var_78]
0x18018683b  call    ?Close@?$AutoComPtr@UIEnumCSI_PENDING_TRANSACTION@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IEnumCSI_PENDING_TRANSACTION>::Close(void)
0x180186840  mov     rcx, [rbp+57h+var_88]
0x180186844  test    rcx, rcx
0x180186847  jz      short loc_180186859
0x180186849  mov     rax, [rcx]
0x18018684c  mov     rax, [rax+10h]
0x180186850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186855  mov     [rbp+57h+var_88], r12
0x180186859  mov     rcx, [rsp+110h+var_D8]
0x18018685e  test    rcx, rcx
0x180186861  jz      short loc_180186874
0x180186863  mov     rax, [rcx]
0x180186866  mov     rax, [rax+10h]
0x18018686a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018686f  mov     [rsp+110h+var_D8], r12
0x180186874  mov     rcx, [rbp+57h+var_70]
0x180186878  test    rcx, rcx
0x18018687b  jz      short loc_180186889
0x18018687d  mov     rax, [rcx]
0x180186880  mov     rax, [rax+10h]
0x180186884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186889  mov     eax, edi
0x18018688b  jmp     loc_18018751A
0x180186890  mov     rsi, [rsp+110h+var_D8]
0x180186895  lea     rcx, [rbp+57h+var_88]
0x180186899  mov     rax, [rsi]
0x18018689c  mov     rdi, [rax]
0x18018689f  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801868a4  mov     r8, rax
0x1801868a7  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa
0x1801868ae  mov     rax, rdi
0x1801868b1  mov     rcx, rsi
0x1801868b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801868b9  mov     edi, eax
0x1801868bb  test    eax, eax
0x1801868bd  jns     short loc_180186918
0x1801868bf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801868c6  mov     [rbp+57h+var_80], eax
0x1801868c9  test    rcx, rcx
0x1801868cc  jz      short loc_18018690E
0x1801868ce  mov     esi, 3
0x1801868d3  lea     r9, aFailedToConver_16; "Failed to convert ICSIStore to a servic"...
0x1801868da  mov     r8d, esi
0x1801868dd  xor     edx, edx
0x1801868df  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801868e4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801868eb  lea     rax, [rbp+57h+var_80]
0x1801868ef  mov     [rbp+57h+var_D0], rax
0x1801868f3  lea     r9, asc_1802EE7AC; ": {}"
0x1801868fa  lea     rax, [rbp+57h+var_D0]
0x1801868fe  mov     r8d, esi
0x180186901  mov     dl, r13b
0x180186904  mov     qword ptr [rsp+110h+var_F0], rax
0x180186909  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18018690e  mov     edx, 428h
0x180186913  jmp     loc_180186808
0x180186918  mov     rsi, [rbp+57h+var_88]
0x18018691c  lea     rcx, [rbp+57h+var_70]
0x180186920  mov     rax, [rsi]
0x180186923  mov     rdi, [rax+18h]
0x180186927  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x18018692c  lea     rdx, _GUID_a817521b_2b43_489f_8b84_67aceeab24a8
0x180186933  mov     r9, rax
0x180186936  mov     r8, rdx
0x180186939  mov     rcx, rsi
0x18018693c  mov     rax, rdi
0x18018693f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186944  mov     edi, eax
0x180186946  test    eax, eax
0x180186948  jns     short loc_1801869A3
0x18018694a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180186951  mov     [rbp+57h+var_80], eax
0x180186954  test    rcx, rcx
0x180186957  jz      short loc_180186999
0x180186959  mov     esi, 3
0x18018695e  lea     r9, aReprFailedToGe; "Repr: Failed to get store2."
0x180186965  mov     r8d, esi
0x180186968  xor     edx, edx
0x18018696a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18018696f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180186976  lea     rax, [rbp+57h+var_80]
0x18018697a  mov     [rbp+57h+var_D0], rax
0x18018697e  lea     r9, asc_1802EE7AC; ": {}"
0x180186985  lea     rax, [rbp+57h+var_D0]
0x180186989  mov     r8d, esi
0x18018698c  mov     dl, r13b
0x18018698f  mov     qword ptr [rsp+110h+var_F0], rax
0x180186994  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180186999  mov     edx, 42Bh
0x18018699e  jmp     loc_180186808
0x1801869a3  cmp     [r15], r12
0x1801869a6  jnz     loc_18018763F
0x1801869ac  mov     rcx, [rbp+57h+var_70]
0x1801869b0  lea     r8, [rbp+57h+var_50]
0x1801869b4  mov     r9, r15
0x1801869b7  xor     edx, edx
0x1801869b9  mov     rax, [rcx]
0x1801869bc  mov     rax, [rax+148h]
0x1801869c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801869c8  mov     edi, eax
0x1801869ca  test    eax, eax
0x1801869cc  jns     short loc_180186A27
0x1801869ce  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801869d5  mov     [rbp+57h+var_80], eax
0x1801869d8  test    rcx, rcx
0x1801869db  jz      short loc_180186A1D
0x1801869dd  mov     esi, 3
0x1801869e2  lea     r9, aReprFailedToGe_0; "Repr: Failed to get repair transaction."
0x1801869e9  mov     r8d, esi
0x1801869ec  xor     edx, edx
0x1801869ee  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801869f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801869fa  lea     rax, [rbp+57h+var_80]
0x1801869fe  mov     [rbp+57h+var_D0], rax
0x180186a02  lea     r9, asc_1802EE7AC; ": {}"
0x180186a09  lea     rax, [rbp+57h+var_D0]
0x180186a0d  mov     r8d, esi
0x180186a10  mov     dl, r13b
0x180186a13  mov     qword ptr [rsp+110h+var_F0], rax
0x180186a18  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180186a1d  mov     edx, 42Eh
0x180186a22  jmp     loc_180186808
0x180186a27  cmp     [r14+170h], r12d
0x180186a2e  jz      short loc_180186A7B
0x180186a30  lea     rax, [rbp+57h+var_80]
0x180186a34  mov     r8d, r13d; unsigned int
0x180186a37  lea     r9, aIgnorepayloadc; "IgnorePayloadCorruption"
0x180186a3e  mov     qword ptr [rsp+110h+var_F0], rax; unsigned int *
0x180186a43  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180186a4a  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180186a51  mov     edi, 4
0x180186a56  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x180186a5b  test    eax, eax
0x180186a5d  jnz     short loc_180186A80
0x180186a5f  cmp     [rbp+57h+var_80], r12d
0x180186a63  jz      short loc_180186A80
0x180186a65  lea     rdx, aReprGpoIgnoreP; "Repr: GPO ignore payload corruption is "...
0x180186a6c  mov     ecx, r13d
0x180186a6f  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180186a74  mov     edi, 0Ch
0x180186a79  jmp     short loc_180186A80
0x180186a7b  mov     edi, 14h
0x180186a80  mov     rcx, [r15]
0x180186a83  lea     r9, [rbp+57h+var_60]
0x180186a87  cmp     [r14+16Dh], r12b
0x180186a8e  mov     eax, 20h ; ' '
0x180186a93  mov     r8, rbx
0x180186a96  cmovnz  edi, eax
0x180186a99  mov     rax, [rcx]
0x180186a9c  mov     edx, edi
0x180186a9e  mov     rax, [rax+18h]
0x180186aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180186aa7  mov     ebx, eax
0x180186aa9  test    eax, eax
0x180186aab  jns     short loc_180186B22
0x180186aad  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180186ab4  mov     [rbp+57h+var_80], eax
0x180186ab7  test    rcx, rcx
0x180186aba  jz      short loc_180186AFC
0x180186abc  mov     esi, 3
0x180186ac1  lea     r9, aReptFailedToCa_0; "Rept: Failed to call CSI detect."
0x180186ac8  mov     r8d, esi
0x180186acb  xor     edx, edx
0x180186acd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180186ad2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180186ad9  lea     rax, [rbp+57h+var_80]
0x180186add  mov     [rbp+57h+var_D0], rax
0x180186ae1  lea     r9, asc_1802EE7AC; ": {}"
0x180186ae8  lea     rax, [rbp+57h+var_D0]
0x180186aec  mov     r8d, esi
0x180186aef  mov     dl, r13b
0x180186af2  mov     qword ptr [rsp+110h+var_F0], rax; int
0x180186af7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180186afc  mov     edx, 44Fh; void *
  ... truncated ...
```
