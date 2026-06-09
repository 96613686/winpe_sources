# blue2th::Migrator::Migrate(ulong *)

- ea: `0x180008940`
- end: `0x1800094b6`
- name: `?Migrate@Migrator@blue2th@@QEAAJPEAK@Z`
- size: `2934`
- prototype: `__int64 __fastcall(__int64 ***this, __int64 **, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180007840`

## callees

- `0x180001468`
- `0x180001514`
- `0x1800022e0`
- `0x180003320`
- `0x1800034ac`
- `0x1800035f2`
- `0x1800076a4`
- `0x180007720`
- `0x180007b38`
- `0x1800082ac`
- `0x1800083ec`
- `0x180008520`
- `0x180008940`
- `0x180009764`
- `0x18000977c`
- `0x1800097fc`
- `0x18000a688`
- `0x18000a6f4`
- `0x18000ac08`
- `0x18000c214`
- `0x18000c740`
- `0x18001b094`
- `0x180020010`

## import_xrefs

- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180008d5f`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x180008d5f`
- `OLEAUT32!__imp_SysFreeString` at `0x180008e56`
- `OLEAUT32!__imp_SysFreeString` at `0x1800090c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180009187`
- `OLEAUT32!__imp_SysFreeString` at `0x180009249`
- `OLEAUT32!__imp_SysFreeString` at `0x180008e56`
- `OLEAUT32!__imp_SysFreeString` at `0x1800090c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180009187`
- `OLEAUT32!__imp_SysFreeString` at `0x180009249`
- `OLEAUT32!__imp_SysStringLen` at `0x18000903a`
- `OLEAUT32!__imp_SysStringLen` at `0x18000903a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180008e46`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180008e46`

## string_xrefs

- `0x180008ba1`: `C:\Windows\System32\MDMAgent.exe`
- `0x18000929e`: `C:\Windows\System32\MDMAgent.exe`
- `0x1800093a4`: `C:\Windows\System32\MDMAgent.exe`
- `0x180008b44`: `Could not create migration server alert`
- `0x18000907f`: `Could not create migration server alert`
- `0x180009144`: `Could not create migration server alert`

## pseudocode

```c
__int64 __fastcall blue2th::Migrator::Migrate(__int64 ***this, __int64 **a2, __int64 a3)
{
  const unsigned __int16 *v5; // rdx
  const unsigned __int16 *v6; // rcx
  __int64 v7; // r8
  bool CanImpersonate; // r15
  __int128 *p_Src; // rdx
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // r8
  __int64 v12; // rdi
  unsigned __int64 v13; // r8
  __int64 v14; // rax
  int v15; // edi
  __int64 v16; // r8
  __int64 v17; // r9
  _QWORD *v19; // rax
  ScheduleMigrator *v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 DatabaseManagerInstance; // r9
  int v26; // edi
  int v27; // eax
  unsigned int v28; // edi
  unsigned __int64 v29; // r8
  __int64 v30; // rcx
  unsigned __int16 **v31; // r15
  char *v32; // rdi
  __int64 trivial_2; // rax
  unsigned __int64 v34; // r9
  __int64 v35; // rdx
  unsigned __int16 **v36; // rax
  unsigned __int64 v37; // rdi
  __int64 v38; // rcx
  unsigned __int16 **v39; // r15
  char *v40; // rdi
  __int64 v41; // rax
  unsigned __int64 v42; // r9
  __int64 v43; // rdx
  unsigned __int16 **v44; // rax
  unsigned __int64 v45; // rdi
  const unsigned __int16 *v46; // rcx
  int v47; // eax
  __int64 v48; // r8
  __int64 v49; // r9
  unsigned int v50; // edi
  const unsigned __int16 *v51; // rcx
  int v52; // eax
  __int64 v53; // r9
  int v54; // edi
  _QWORD *v55; // rax
  ScheduleMigrator *v56; // rcx
  unsigned int v57; // edi
  _QWORD *v58; // rax
  ScheduleMigrator *v59; // rcx
  __int64 v60; // r8
  int v61; // [rsp+40h] [rbp-148h] BYREF
  _QWORD *v62; // [rsp+48h] [rbp-140h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-138h] BYREF
  __int64 v64; // [rsp+58h] [rbp-130h] BYREF
  _BYTE rguid[24]; // [rsp+60h] [rbp-128h] BYREF
  unsigned __int16 *v66[2]; // [rsp+78h] [rbp-110h] BYREF
  unsigned __int64 v67; // [rsp+88h] [rbp-100h]
  unsigned __int64 v68; // [rsp+90h] [rbp-F8h]
  WCHAR SubKey[8]; // [rsp+98h] [rbp-F0h] BYREF
  __int128 v70; // [rsp+A8h] [rbp-E0h]
  __int128 Src; // [rsp+B8h] [rbp-D0h] BYREF
  __int128 v72; // [rsp+C8h] [rbp-C0h]
  __int128 v73; // [rsp+D8h] [rbp-B0h] BYREF
  __int128 v74; // [rsp+E8h] [rbp-A0h]
  __int64 ***v75; // [rsp+F8h] [rbp-90h] BYREF
  char v76; // [rsp+100h] [rbp-88h]
  OLECHAR sz[40]; // [rsp+110h] [rbp-78h] BYREF

  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, SystemMigrationTaskStarted, a3, 1, &v75);
  v62 = 0;
  blue2th::Migrator::GenerateRuntimeVariables(this);
  this[3] = a2;
  v75 = this;
  v76 = 1;
  Src = 0;
  v72 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&Src, L"SOFTWARE\\Microsoft\\Enrollments", 0x1Eu);
  std::wstring::append(&Src, L"\\");
  std::wstring::append(&Src, L"B92E7305-9462-4B48-AE6D-57D9D09FD698");
  if ( RegistryHelper::IsDwordValuePresent(v6, v5) )
  {
    CanImpersonate = blue2th::Migrator::CanImpersonate((blue2th::Migrator *)this);
    p_Src = &Src;
    if ( *((_QWORD *)&v72 + 1) > 7u )
      p_Src = (__int128 *)Src;
    *(_OWORD *)SubKey = 0;
    v70 = 0;
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)p_Src + v11) );
    std::wstring::_Construct<1,unsigned short const *>(SubKey, p_Src, v11);
    v12 = RegistryHelper::OpenKey(SubKey);
    std::wstring::~wstring((char **)SubKey);
    if ( v12 )
    {
      if ( !CanImpersonate )
      {
        *(_OWORD *)&rguid[8] = 0;
        v19 = operator new(0x60u);
        *v19 = v19;
        v19[1] = v19;
        v19[2] = v19;
        *((_WORD *)v19 + 12) = 257;
        *(_QWORD *)&rguid[8] = v19;
        ScheduleMigrator::DeleteSchedule(v20, 0);
        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((void **)&rguid[8]);
        *(_QWORD *)rguid = L"C:\\Windows\\System32\\MDMAgent.exe";
        *(_OWORD *)&rguid[8] = 0;
        v21 = operator new(0x60u);
        *v21 = v21;
        v21[1] = v21;
        v21[2] = v21;
        *((_WORD *)v21 + 12) = 257;
        *(_QWORD *)&rguid[8] = v21;
        v73 = 0;
        v74 = 0;
        do
          ++v10;
        while ( userSidRtv[v10] );
        std::wstring::_Construct<1,unsigned short const *>(&v73, userSidRtv, v10);
        v22 = std::map<std::wstring,std::wstring>::operator[](this, &v73);
        if ( *(_QWORD *)(v22 + 24) > 7u )
          v22 = *(_QWORD *)v22;
        ScheduleMigrator::CreateLogonTaskForUser((const unsigned __int16 **)rguid, (const unsigned __int16 *)v22);
        std::wstring::~wstring((char **)&v73);
        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((void **)&rguid[8]);
        if ( (unsigned int)dword_18002B0C0 > 5
          && (qword_18002B0D0 & 0x400000000000LL) != 0
          && (qword_18002B0D8 & 0x400000000000LL) == qword_18002B0D8 )
        {
          bstrString = (BSTR)"Migration will continue when enrolled user is logged in.";
          *(_QWORD *)rguid = "onecoreuap\\admin\\enterprisemgmt\\migrator\\blue2th\\lib\\migrator.cpp";
          v61 = 86;
          *(_QWORD *)SubKey = L"blue2th::Migrator::Migrate";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            qword_18002B0D8,
            (__int64)&byte_1800253EF,
            v23,
            v24,
            (const unsigned __int16 **)SubKey,
            (__int64)&v61,
            (const unsigned __int16 **)rguid,
            (const unsigned __int16 **)&bstrString);
        }
        std::wstring::~wstring((char **)&Src);
        this[3] = 0;
        if ( v62 )
          (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
        return 0;
      }
      BlueMigration::MigrateToCurrentFromWinBlue((struct blue2th::Migrator *)this);
      *(_OWORD *)SubKey = 0;
      v70 = 0;
      v13 = -1;
      do
        ++v13;
      while ( userSidRtv[v13] );
      std::wstring::_Construct<1,unsigned short const *>(SubKey, userSidRtv, v13);
      v14 = std::map<std::wstring,std::wstring>::operator[](this, SubKey);
      if ( *(_QWORD *)(v14 + 24) > 7u )
        v14 = *(_QWORD *)v14;
      v15 = ScheduleUpgradeAlert(L"B92E7305-9462-4B48-AE6D-57D9D09FD698", (const unsigned __int16 *)v14);
      std::wstring::~wstring((char **)SubKey);
      if ( v15 < 0 )
      {
        if ( (unsigned int)dword_18002B0C0 > 5 )
        {
          v61 = v15;
          bstrString = L"Could not create migration server alert";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)dword_18002B0C0,
            (__int64)byte_180025461,
            v16,
            v17,
            (const unsigned __int16 **)&bstrString,
            (__int64)&v61);
        }
        std::wstring::~wstring((char **)&Src);
        this[3] = 0;
        if ( v62 )
          (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
        return (unsigned int)v15;
      }
    }
    DatabaseManagerInstance = GetDatabaseManagerInstance();
    v26 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD **))(*(_QWORD *)DatabaseManagerInstance + 32LL))(
            DatabaseManagerInstance,
            222306401,
            &v62);
    if ( v26 >= 0 )
    {
      v64 = 0;
      v27 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v62 + 24LL))(v62, &v64);
      v28 = v27;
      if ( v27 < 0 || v27 == 1 )
      {
        if ( v64 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
        std::wstring::~wstring((char **)&Src);
        this[3] = 0;
        if ( v62 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v62 + 16LL))(v62, *v62);
        return v28;
      }
      else
      {
        while ( v64 )
        {
          *(_OWORD *)rguid = 0;
          if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v64 + 24LL))(v64, rguid) < 0 )
            break;
          bstrString = 0;
          v61 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v64 + 112LL))(v64, &bstrString);
          if ( StringFromGUID2((const GUID *const)rguid, sz, 39) != 39 )
          {
            SysFreeString(bstrString);
            if ( v64 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
            std::wstring::~wstring((char **)&Src);
            this[3] = 0;
            if ( v62 )
              (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
            return 2147549183LL;
          }
          *(_OWORD *)v66 = 0;
          v67 = 0;
          v68 = 0;
          v29 = -1;
          do
            ++v29;
          while ( sz[v29] );
          std::wstring::_Construct<1,unsigned short const *>(v66, sz, v29);
          v31 = v66;
          if ( v68 > 7 )
            v31 = (unsigned __int16 **)v66[0];
          if ( !v67
            || (v32 = (char *)v31 + 2 * v67, trivial_2 = _std_find_trivial_2(v31, v32, 123), (char *)trivial_2 == v32) )
          {
            v34 = -1;
          }
          else
          {
            v34 = (trivial_2 - (__int64)v31) >> 1;
          }
          if ( v67 < v34 )
            std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v30);
          v35 = 1;
          if ( v67 == v34 )
            v35 = v67 - v34;
          v36 = v66;
          if ( v68 > 7 )
            v36 = (unsigned __int16 **)v66[0];
          v37 = v67 - v35;
          memmove_0((char *)v36 + 2 * v34, (char *)v36 + 2 * v34 + 2 * v35, 2 * (v67 - v35 - v34) + 2);
          v67 = v37;
          v39 = v66;
          if ( v68 > 7 )
            v39 = (unsigned __int16 **)v66[0];
          if ( !v37 || (v40 = (char *)v39 + 2 * v37, v41 = _std_find_trivial_2(v39, v40, 125), (char *)v41 == v40) )
            v42 = -1;
          else
            v42 = (v41 - (__int64)v39) >> 1;
          if ( v67 < v42 )
            std::_String_val<std::_Simple_types<unsigned short>>::_Xran(v38);
          v43 = 1;
          if ( v67 == v42 )
            v43 = v67 - v42;
          v44 = v66;
          if ( v68 > 7 )
            v44 = (unsigned __int16 **)v66[0];
          v45 = v67 - v43;
          memmove_0((char *)v44 + 2 * v42, (char *)v44 + 2 * v42 + 2 * v43, 2 * (v67 - v43 - v42) + 2);
          v67 = v45;
          if ( v61 || !SysStringLen(bstrString) )
          {
            v51 = (const unsigned __int16 *)v66;
            if ( v68 > 7 )
              v51 = v66[0];
            v52 = ScheduleUpgradeAlert(v51, 0);
            v50 = v52;
            if ( v52 < 0 )
            {
              if ( (unsigned int)dword_18002B0C0 > 5 )
              {
                v61 = v52;
                *(_QWORD *)SubKey = L"Could not create migration server alert";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                  (unsigned int)dword_18002B0C0,
                  (__int64)byte_180025355,
                  v48,
                  v53,
                  (const unsigned __int16 **)SubKey,
                  (__int64)&v61);
              }
              std::wstring::~wstring((char **)v66);
              SysFreeString(bstrString);
              if ( v64 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
              std::wstring::~wstring((char **)&Src);
              this[3] = 0;
              if ( v62 )
                (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
              return v50;
            }
          }
          else
          {
            v46 = (const unsigned __int16 *)v66;
            if ( v68 > 7 )
              v46 = v66[0];
            v47 = ScheduleUpgradeAlert(v46, bstrString);
            v50 = v47;
            if ( v47 < 0 )
            {
              if ( (unsigned int)dword_18002B0C0 > 5 )
              {
                v61 = v47;
                *(_QWORD *)SubKey = L"Could not create migration server alert";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                  (unsigned int)dword_18002B0C0,
                  (__int64)word_1800253A2,
                  v48,
                  v49,
                  (const unsigned __int16 **)SubKey,
                  (__int64)&v61);
              }
              std::wstring::~wstring((char **)v66);
              SysFreeString(bstrString);
              if ( v64 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
              std::wstring::~wstring((char **)&Src);
              this[3] = 0;
              if ( v62 )
                (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
              return v50;
            }
          }
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
          {
            *(_QWORD *)&v74 = &v61;
            v61 = v50;
            *((_QWORD *)&v74 + 1) = 4;
            McGenEventWrite_EventWriteTransfer(
              &MDM_ENTERPRISE_DIAGNOSTICS_Context,
              SystemUpgradeAlertScheduled,
              v48,
              2,
              &v73);
          }
          v54 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v62 + 24LL))(v62, &v64);
          std::wstring::~wstring((char **)v66);
          SysFreeString(bstrString);
          if ( v54 < 0 )
          {
            if ( v64 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
            std::wstring::~wstring((char **)&Src);
            this[3] = 0;
            if ( v62 )
              (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
            return (unsigned int)v54;
          }
        }
        *(_QWORD *)rguid = L"C:\\Windows\\System32\\MDMAgent.exe";
        *(_OWORD *)&rguid[8] = 0;
        v55 = operator new(0x60u);
        *v55 = v55;
        v55[1] = v55;
        v55[2] = v55;
        *((_WORD *)v55 + 12) = 257;
        *(_QWORD *)&rguid[8] = v55;
        v57 = ScheduleMigrator::DeleteSchedule(v56, 0);
        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((void **)&rguid[8]);
        if ( v64 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
        std::wstring::~wstring((char **)&Src);
        this[3] = 0;
        if ( v62 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))(*v62 + 16LL))(v62, *v62);
        return v57;
      }
    }
    else
    {
      std::wstring::~wstring((char **)&Src);
      this[3] = 0;
      if ( v62 )
        (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
      return (unsigned int)v26;
    }
  }
  else
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, NoMigrationNeeded, v7, 1, SubKey);
    *(_QWORD *)rguid = L"C:\\Windows\\System32\\MDMAgent.exe";
    *(_OWORD *)&rguid[8] = 0;
    v58 = operator new(0x60u);
    *v58 = v58;
    v58[1] = v58;
    v58[2] = v58;
    *((_WORD *)v58 + 12) = 257;
    *(_QWORD *)&rguid[8] = v58;
    ScheduleMigrator::DeleteSchedule(v59, 0);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>((void **)&rguid[8]);
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
    {
      v61 = 0;
      *(_QWORD *)&v74 = &v61;
      *((_QWORD *)&v74 + 1) = 4;
      McGenEventWrite_EventWriteTransfer(&MDM_ENTERPRISE_DIAGNOSTICS_Context, SystemMigrationTaskDeleted, v60, 2, &v73);
    }
    std::wstring::~wstring((char **)&Src);
    this[3] = 0;
    if ( v62 )
      (*(void (__fastcall **)(_QWORD *))(*v62 + 16LL))(v62);
    return 0;
  }
}

```

## disassembly

```asm
0x180008940  mov     [rsp+arg_8], rbx
0x180008945  mov     [rsp+arg_10], rsi
0x18000894a  push    rdi
0x18000894b  push    r12
0x18000894d  push    r15
0x18000894f  sub     rsp, 170h
0x180008956  mov     rax, cs:__security_cookie
0x18000895d  xor     rax, rsp
0x180008960  mov     [rsp+188h+var_28], rax
0x180008968  mov     rdi, rdx
0x18000896b  mov     rbx, rcx
0x18000896e  mov     r12b, 10h
0x180008971  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, r12b
0x180008978  jz      short loc_1800089A0
0x18000897a  lea     rax, [rsp+188h+var_90]
0x180008982  mov     [rsp+188h+var_168], rax
0x180008987  mov     r9d, 1
0x18000898d  lea     rdx, SystemMigrationTaskStarted
0x180008994  lea     rcx, MDM_ENTERPRISE_DIAGNOSTICS_Context
0x18000899b  call    McGenEventWrite_EventWriteTransfer
0x1800089a0  xor     esi, esi
0x1800089a2  mov     [rsp+188h+var_140], rsi
0x1800089a7  mov     rcx, rbx; this
0x1800089aa  call    ?GenerateRuntimeVariables@Migrator@blue2th@@QEAAXXZ; blue2th::Migrator::GenerateRuntimeVariables(void)
0x1800089af  mov     [rbx+18h], rdi
0x1800089b3  mov     [rsp+188h+var_90], rbx
0x1800089bb  mov     [rsp+188h+var_88], 1
0x1800089c3  xorps   xmm0, xmm0
0x1800089c6  movups  [rsp+188h+Src], xmm0
0x1800089ce  xorps   xmm1, xmm1
0x1800089d1  movdqu  [rsp+188h+var_C0], xmm1
0x1800089da  lea     r8d, [rsi+1Eh]
0x1800089de  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Enrollments"
0x1800089e5  lea     rcx, [rsp+188h+Src]
0x1800089ed  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800089f2  nop
0x1800089f3  lea     rdx, asc_180021D44; "\\"
0x1800089fa  lea     rcx, [rsp+188h+Src]; Src
0x180008a02  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180008a07  lea     rdx, aB92e730594624b; "B92E7305-9462-4B48-AE6D-57D9D09FD698"
0x180008a0e  lea     rcx, [rsp+188h+Src]; Src
0x180008a16  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180008a1b  call    ?IsDwordValuePresent@RegistryHelper@@SA_NPEBG0@Z; RegistryHelper::IsDwordValuePresent(ushort const *,ushort const *)
0x180008a20  test    al, al
0x180008a22  jz      loc_180009375
0x180008a28  mov     rcx, rbx; this
0x180008a2b  call    ?CanImpersonate@Migrator@blue2th@@QEAA_NXZ; blue2th::Migrator::CanImpersonate(void)
0x180008a30  mov     r15b, al
0x180008a33  lea     rdx, [rsp+188h+Src]
0x180008a3b  cmp     qword ptr [rsp+188h+var_C0+8], 7
0x180008a44  cmova   rdx, qword ptr [rsp+188h+Src]
0x180008a4d  xorps   xmm0, xmm0
0x180008a50  movups  xmmword ptr [rsp+188h+SubKey], xmm0
0x180008a58  xorps   xmm1, xmm1
0x180008a5b  movdqu  [rsp+188h+var_E0], xmm1
0x180008a64  or      r12, 0FFFFFFFFFFFFFFFFh
0x180008a68  mov     r8, r12
0x180008a6b  inc     r8
0x180008a6e  cmp     [rdx+r8*2], si
0x180008a73  jnz     short loc_180008A6B
0x180008a75  lea     rcx, [rsp+188h+SubKey]
0x180008a7d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180008a82  nop
0x180008a83  xor     edx, edx
0x180008a85  lea     rcx, [rsp+188h+SubKey]; lpSubKey
0x180008a8d  call    ?OpenKey@RegistryHelper@@SAPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; RegistryHelper::OpenKey(std::wstring const &,bool)
0x180008a92  mov     rdi, rax
0x180008a95  lea     rcx, [rsp+188h+SubKey]; void *
0x180008a9d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008aa2  test    rdi, rdi
0x180008aa5  jz      loc_180008D5F
0x180008aab  test    r15b, r15b
0x180008aae  jz      loc_180008BA1
0x180008ab4  mov     rcx, rbx; struct blue2th::Migrator *
0x180008ab7  call    ?MigrateToCurrentFromWinBlue@BlueMigration@@SAXPEAVMigrator@blue2th@@@Z; BlueMigration::MigrateToCurrentFromWinBlue(blue2th::Migrator *)
0x180008abc  mov     rdx, cs:?userSidRtv@@3PEBGEB; ushort const * const userSidRtv
0x180008ac3  xorps   xmm0, xmm0
0x180008ac6  movups  xmmword ptr [rsp+188h+SubKey], xmm0
0x180008ace  xorps   xmm1, xmm1
0x180008ad1  movdqu  [rsp+188h+var_E0], xmm1
0x180008ada  mov     r8, r12
0x180008add  inc     r8
0x180008ae0  cmp     [rdx+r8*2], si
0x180008ae5  jnz     short loc_180008ADD
0x180008ae7  lea     rcx, [rsp+188h+SubKey]
0x180008aef  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180008af4  nop
0x180008af5  lea     rdx, [rsp+188h+SubKey]
0x180008afd  mov     rcx, rbx
0x180008b00  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180008b05  cmp     qword ptr [rax+18h], 7
0x180008b0a  jbe     short loc_180008B0F
0x180008b0c  mov     rax, [rax]
0x180008b0f  mov     rdx, rax; unsigned __int16 *
0x180008b12  lea     rcx, aB92e730594624b; "B92E7305-9462-4B48-AE6D-57D9D09FD698"
0x180008b19  call    ?ScheduleUpgradeAlert@@YAJPEBG0@Z; ScheduleUpgradeAlert(ushort const *,ushort const *)
0x180008b1e  mov     edi, eax
0x180008b20  lea     rcx, [rsp+188h+SubKey]; void *
0x180008b28  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008b2d  test    edi, edi
0x180008b2f  jns     loc_180008D5F
0x180008b35  mov     ecx, cs:dword_18002B0C0
0x180008b3b  cmp     ecx, 5
0x180008b3e  jbe     short loc_180008B71
0x180008b40  mov     [rsp+188h+var_148], edi
0x180008b44  lea     rax, aCouldNotCreate; "Could not create migration server alert"
0x180008b4b  mov     [rsp+188h+bstrString], rax
0x180008b50  lea     rax, [rsp+188h+var_148]
0x180008b55  mov     [rsp+188h+var_160], rax
0x180008b5a  lea     rax, [rsp+188h+bstrString]
0x180008b5f  mov     [rsp+188h+var_168], rax
0x180008b64  lea     rdx, byte_180025461
0x180008b6b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180008b70  nop
0x180008b71  lea     rcx, [rsp+188h+Src]; void *
0x180008b79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008b7e  nop
0x180008b7f  mov     [rbx+18h], rsi
0x180008b83  mov     rcx, [rsp+188h+var_140]
0x180008b88  test    rcx, rcx
0x180008b8b  jz      short loc_180008B9A
0x180008b8d  mov     rax, [rcx]
0x180008b90  mov     rax, [rax+10h]
0x180008b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b99  nop
0x180008b9a  mov     eax, edi
0x180008b9c  jmp     loc_180009480
0x180008ba1  lea     rdi, aCWindowsSystem; "C:\\Windows\\System32\\MDMAgent.exe"
0x180008ba8  mov     qword ptr [rsp+188h+rguid], rdi
0x180008bad  xorps   xmm0, xmm0
0x180008bb0  movdqu  xmmword ptr [rsp+188h+rguid+8], xmm0
0x180008bb6  mov     r15d, 60h ; '`'
0x180008bbc  mov     ecx, r15d; Size
0x180008bbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008bc4  mov     [rax], rax
0x180008bc7  mov     [rax+8], rax
0x180008bcb  mov     [rax+10h], rax
0x180008bcf  mov     word ptr [rax+18h], 101h
0x180008bd5  mov     qword ptr [rsp+188h+rguid+8], rax
0x180008bda  xor     edx, edx; unsigned __int16 *
0x180008bdc  call    ?DeleteSchedule@ScheduleMigrator@@QEAAJPEBG@Z; ScheduleMigrator::DeleteSchedule(ushort const *)
0x180008be1  nop
0x180008be2  lea     rcx, [rsp+188h+rguid+8]
0x180008be7  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180008bec  mov     qword ptr [rsp+188h+rguid], rdi
0x180008bf1  xorps   xmm0, xmm0
0x180008bf4  movdqu  xmmword ptr [rsp+188h+rguid+8], xmm0
0x180008bfa  mov     ecx, r15d; Size
0x180008bfd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008c02  mov     [rax], rax
0x180008c05  mov     [rax+8], rax
0x180008c09  mov     [rax+10h], rax
0x180008c0d  mov     word ptr [rax+18h], 101h
0x180008c13  mov     qword ptr [rsp+188h+rguid+8], rax
0x180008c18  mov     rdx, cs:?userSidRtv@@3PEBGEB; ushort const * const userSidRtv
0x180008c1f  xorps   xmm0, xmm0
0x180008c22  movups  [rsp+188h+var_B0], xmm0
0x180008c2a  xorps   xmm1, xmm1
0x180008c2d  movdqu  [rsp+188h+var_A0], xmm1
0x180008c36  inc     r12
0x180008c39  cmp     [rdx+r12*2], si
0x180008c3e  jnz     short loc_180008C36
0x180008c40  mov     r8, r12
0x180008c43  lea     rcx, [rsp+188h+var_B0]
0x180008c4b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180008c50  nop
0x180008c51  lea     rdx, [rsp+188h+var_B0]
0x180008c59  mov     rcx, rbx
0x180008c5c  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180008c61  cmp     qword ptr [rax+18h], 7
0x180008c66  jbe     short loc_180008C6B
0x180008c68  mov     rax, [rax]
0x180008c6b  mov     rdx, rax; unsigned __int16 *
0x180008c6e  lea     rcx, [rsp+188h+rguid]; this
0x180008c73  call    ?CreateLogonTaskForUser@ScheduleMigrator@@QEAAJPEBG@Z; ScheduleMigrator::CreateLogonTaskForUser(ushort const *)
0x180008c78  nop
0x180008c79  lea     rcx, [rsp+188h+var_B0]; void *
0x180008c81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008c86  nop
0x180008c87  lea     rcx, [rsp+188h+rguid+8]
0x180008c8c  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x180008c91  mov     eax, cs:dword_18002B0C0
0x180008c97  cmp     eax, 5
0x180008c9a  jbe     loc_180008D2F
0x180008ca0  mov     rcx, cs:qword_18002B0D8
0x180008ca7  mov     rax, cs:qword_18002B0D0
0x180008cae  mov     rdx, 400000000000h
0x180008cb8  test    rdx, rax
0x180008cbb  jz      short loc_180008D2F
0x180008cbd  mov     rax, rcx
0x180008cc0  and     rax, rdx
0x180008cc3  cmp     rax, rcx
0x180008cc6  jnz     short loc_180008D2F
0x180008cc8  lea     rax, aMigrationWillC; "Migration will continue when enrolled u"...
0x180008ccf  mov     [rsp+188h+bstrString], rax
0x180008cd4  lea     rax, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\migr"...
0x180008cdb  mov     qword ptr [rsp+188h+rguid], rax
0x180008ce0  mov     [rsp+188h+var_148], 56h ; 'V'
0x180008ce8  lea     rax, aBlue2thMigrato; "blue2th::Migrator::Migrate"
0x180008cef  mov     qword ptr [rsp+188h+SubKey], rax
0x180008cf7  lea     rax, [rsp+188h+bstrString]
0x180008cfc  mov     [rsp+188h+var_150], rax
0x180008d01  lea     rax, [rsp+188h+rguid]
0x180008d06  mov     [rsp+188h+var_158], rax
0x180008d0b  lea     rax, [rsp+188h+var_148]
0x180008d10  mov     [rsp+188h+var_160], rax
0x180008d15  lea     rax, [rsp+188h+SubKey]
0x180008d1d  mov     [rsp+188h+var_168], rax
0x180008d22  lea     rdx, byte_1800253EF
0x180008d29  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180008d2e  nop
0x180008d2f  lea     rcx, [rsp+188h+Src]; void *
0x180008d37  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008d3c  nop
0x180008d3d  mov     [rbx+18h], rsi
0x180008d41  mov     rcx, [rsp+188h+var_140]
0x180008d46  test    rcx, rcx
0x180008d49  jz      short loc_180008D58
0x180008d4b  mov     rax, [rcx]
0x180008d4e  mov     rax, [rax+10h]
0x180008d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d57  nop
0x180008d58  xor     eax, eax
0x180008d5a  jmp     loc_180009480
0x180008d5f  call    cs:__imp_GetDatabaseManagerInstance
0x180008d65  mov     r9, rax
0x180008d68  mov     rcx, [rax]
0x180008d6b  mov     rax, [rcx+20h]
0x180008d6f  lea     r8, [rsp+188h+var_140]
0x180008d74  mov     edx, 0D402061h
0x180008d79  mov     rcx, r9
0x180008d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d81  mov     edi, eax
0x180008d83  test    eax, eax
0x180008d85  jns     short loc_180008DB7
0x180008d87  lea     rcx, [rsp+188h+Src]; void *
0x180008d8f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008d94  nop
0x180008d95  mov     [rbx+18h], rsi
0x180008d99  mov     rcx, [rsp+188h+var_140]
0x180008d9e  test    rcx, rcx
0x180008da1  jz      short loc_180008DB0
0x180008da3  mov     rax, [rcx]
0x180008da6  mov     rax, [rax+10h]
0x180008daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008daf  nop
0x180008db0  mov     eax, edi
0x180008db2  jmp     loc_180009480
0x180008db7  mov     [rsp+188h+var_130], rsi
0x180008dbc  mov     rcx, [rsp+188h+var_140]
0x180008dc1  mov     rax, [rcx]
0x180008dc4  lea     rdx, [rsp+188h+var_130]
0x180008dc9  mov     rax, [rax+18h]
0x180008dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dd2  mov     edi, eax
0x180008dd4  test    eax, eax
0x180008dd6  js      loc_18000932E
0x180008ddc  cmp     eax, 1
0x180008ddf  jz      loc_18000932E
0x180008de5  mov     rcx, [rsp+188h+var_130]
0x180008dea  test    rcx, rcx
0x180008ded  jz      loc_18000929E
0x180008df3  xorps   xmm0, xmm0
0x180008df6  movups  xmmword ptr [rsp+188h+rguid], xmm0
0x180008dfb  mov     rax, [rcx]
0x180008dfe  lea     rdx, [rsp+188h+rguid]
0x180008e03  mov     rax, [rax+18h]
0x180008e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0c  test    eax, eax
0x180008e0e  js      loc_18000929E
0x180008e14  mov     [rsp+188h+bstrString], rsi
0x180008e19  mov     rcx, [rsp+188h+var_130]
0x180008e1e  mov     rax, [rcx]
0x180008e21  lea     rdx, [rsp+188h+bstrString]
0x180008e26  mov     rax, [rax+70h]
0x180008e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e2f  mov     [rsp+188h+var_148], eax
0x180008e33  mov     r8d, 27h ; '''; cchMax
0x180008e39  lea     rdx, [rsp+188h+sz]; lpsz
0x180008e41  lea     rcx, [rsp+188h+rguid]; rguid
0x180008e46  call    cs:__imp_StringFromGUID2
0x180008e4c  cmp     eax, 27h ; '''
0x180008e4f  jz      short loc_180008EA7
0x180008e51  mov     rcx, [rsp+188h+bstrString]; bstrString
0x180008e56  call    cs:__imp_SysFreeString
0x180008e5c  nop
0x180008e5d  mov     rcx, [rsp+188h+var_130]
0x180008e62  test    rcx, rcx
0x180008e65  jz      short loc_180008E74
0x180008e67  mov     rax, [rcx]
0x180008e6a  mov     rax, [rax+10h]
0x180008e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e73  nop
0x180008e74  lea     rcx, [rsp+188h+Src]; void *
0x180008e7c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008e81  nop
0x180008e82  mov     [rbx+18h], rsi
0x180008e86  mov     rcx, [rsp+188h+var_140]
0x180008e8b  test    rcx, rcx
0x180008e8e  jz      short loc_180008E9D
  ... truncated ...
```
