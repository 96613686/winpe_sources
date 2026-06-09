# CESimSettingServer::ProcessServiceInfo(unsigned __int64,uchar *)

- ea: `0x180024a88`
- end: `0x180025b01`
- name: `?ProcessServiceInfo@CESimSettingServer@@AEAAX_KPEAE@Z`
- size: `4217`
- prototype: `void __fastcall(CESimSettingServer *__hidden this, unsigned __int64, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `26`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001fc54`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x1800028ec`
- `0x180002efc`
- `0x1800040e5`
- `0x180009ffc`
- `0x18001105c`
- `0x180016134`
- `0x1800171b8`
- `0x1800172bc`
- `0x18001dd10`
- `0x18001e0d0`
- `0x18001e3fc`
- `0x18001e8fc`
- `0x18001efcc`
- `0x180020954`
- `0x180020994`
- `0x180024a88`
- `0x1800288c0`
- `0x180028bf8`
- `0x1800329f8`
- `0x180051e80`
- `0x180052818`
- `0x180052b14`
- `0x180058298`
- `0x18005c010`

## import_xrefs

- `luiapi!LuiRegisterForAllProfileNotifications` at `0x18002578c`
- `luiapi!LuiRegisterForAllProfileNotifications` at `0x18002578c`
- `luiapi!LuiRegisterForEsimNotifications` at `0x1800256aa`
- `luiapi!LuiRegisterForEsimNotifications` at `0x1800256aa`

## string_xrefs

- `0x180024b1e`: `CESimSettingServer::ProcessServiceInfo`
- `0x18002533e`: `CESimSettingServer::ProcessServiceInfo`
- `0x1800255da`: `CESimSettingServer::ProcessServiceInfo`
- `0x1800258b6`: `CESimSettingServer::ProcessServiceInfo`
- `0x180024eaa`: `Ignoring LPA_SERVICE_INFO for removed eSim {%ls}.`
- `0x180025a84`: `LPA_ESIM_INFO in LPA_SERVICE_INFO is missing fields, dwParam = 0x%08x.`
- `0x18002516f`: `eSim ID empty while processing LPA_SERVICE_INFO for [Adapter:Slot] - [%ws:%d].`
- `0x180025310`: `Created entry for [Adapter:Slot] - [%ls:%d].`
- `0x1800255ac`: `Updated the m_adapterSlotMap with an entry for eSim {%ls}`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall CESimSettingServer::ProcessServiceInfo(
        CESimSettingServer *this,
        unsigned __int64 a2,
        unsigned __int8 *a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rbx
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned __int16 **v13; // rcx
  int v14; // edx
  const struct _tlgProvider_t *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned __int8 v19; // bl
  unsigned int v20; // edi
  const struct _tlgProvider_t *v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rax
  __int64 v25; // rbx
  int v26; // ecx
  const struct _tlgProvider_t *v27; // rax
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // edi
  const struct _tlgProvider_t *v31; // rax
  __int64 v32; // r8
  __int64 v33; // r9
  unsigned __int8 *v34; // r12
  const struct _tlgProvider_t *v35; // rax
  __int64 v36; // r8
  __int64 v37; // r9
  unsigned __int64 v38; // r8
  const char *p_Src; // rdx
  char *v40; // rbx
  unsigned __int16 *v41; // rsi
  __int64 v42; // rcx
  _QWORD *v43; // rax
  volatile signed __int32 *v44; // rdi
  __int128 *v45; // r9
  const struct _tlgProvider_t *v46; // rax
  __int64 v47; // r8
  __int64 v48; // r9
  __int64 v49; // rax
  __int64 v50; // rcx
  unsigned __int16 *v51; // r13
  __int64 v52; // rsi
  unsigned __int16 *v53; // rdi
  __int64 v54; // r8
  volatile signed __int32 *v55; // rbx
  char **v56; // rcx
  unsigned __int64 v57; // rdx
  char *v58; // rdi
  __int64 v59; // rbx
  __int64 v60; // rbx
  unsigned __int64 v61; // r8
  const struct _tlgProvider_t *v62; // rax
  __int64 v63; // r8
  __int64 v64; // r9
  int v65; // eax
  wil::details::in1diag3 *v66; // rcx
  const struct _tlgProvider_t *v67; // rax
  __int64 v68; // r8
  __int64 v69; // r9
  const struct _tlgProvider_t *v70; // rax
  __int64 v71; // r8
  __int64 v72; // r9
  const struct _tlgProvider_t *v73; // rax
  __int64 v74; // r8
  __int64 v75; // r9
  __int64 v76; // rdx
  const struct _tlgProvider_t *v77; // rax
  __int64 v78; // r8
  __int64 v79; // r9
  void *v80; // [rsp+20h] [rbp-E0h]
  void *v81; // [rsp+20h] [rbp-E0h]
  void *v82; // [rsp+20h] [rbp-E0h]
  void *v83; // [rsp+20h] [rbp-E0h]
  void *v84; // [rsp+20h] [rbp-E0h]
  void *v85; // [rsp+20h] [rbp-E0h]
  void *v86; // [rsp+20h] [rbp-E0h]
  char *v87; // [rsp+28h] [rbp-D8h]
  __int64 v88; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v89; // [rsp+40h] [rbp-C0h] BYREF
  char v90; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v91[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v92; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v93[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v94; // [rsp+78h] [rbp-88h]
  __int64 v95; // [rsp+80h] [rbp-80h]
  unsigned int v96; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v97[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v98; // [rsp+A0h] [rbp-60h]
  int v99; // [rsp+A8h] [rbp-58h]
  const unsigned __int16 *v100[5]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v101[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v102; // [rsp+E8h] [rbp-18h]
  __int128 Src; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v104; // [rsp+100h] [rbp+0h]
  unsigned __int64 v105; // [rsp+108h] [rbp+8h]
  __int128 v106; // [rsp+110h] [rbp+10h] BYREF
  __int64 v107; // [rsp+120h] [rbp+20h]
  __int64 v108; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  *(_OWORD *)v97 = 0;
  v98 = 0;
  *(_OWORD *)v101 = 0;
  v102 = 0;
  std::vector<unsigned short>::resize(v97);
  std::vector<unsigned short>::resize(v101);
  StringCchPrintfW(v97[0], v97[1] - v97[0], L"Enter");
  StringCchPrintfW(v101[0], v101[1] - v101[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", 458, v97[0]);
  v6 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v6 > 5u )
  {
    v89 = v101[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v6,
      (__int64)&byte_180075B07,
      v7,
      v8,
      (const unsigned __int16 **)&v89);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v101);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v97);
  v9 = 20;
  if ( a2 < 0x14 )
  {
    *(_OWORD *)v97 = 0;
    v98 = 0;
    *(_OWORD *)v101 = 0;
    v102 = 0;
    std::vector<unsigned short>::resize(v97);
    std::vector<unsigned short>::resize(v101);
    LODWORD(v80) = 20;
    StringCchPrintfW(v97[0], v97[1] - v97[0], L"Buffer size: %ld, must be at least: %ld", (unsigned int)a2, v80);
    LODWORD(v81) = 463;
    StringCchPrintfW(v101[0], v101[1] - v101[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v81, v97[0]);
    v10 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v10 > 2u )
    {
      v89 = v101[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v10,
        (__int64)&word_180075AE6,
        v11,
        v12,
        (const unsigned __int16 **)&v89);
    }
LABEL_6:
    std::vector<unsigned short>::~vector<unsigned short>((char **)v101);
    v13 = v97;
    goto LABEL_104;
  }
  v14 = *((_DWORD *)a3 + 1);
  if ( (a3[4] & 0xC) == 0xC )
    v9 = 108LL * *((unsigned int *)a3 + 4) + 20;
  if ( v9 != a2 )
  {
    *(_OWORD *)v97 = 0;
    v98 = 0;
    *(_OWORD *)v101 = 0;
    v102 = 0;
    std::vector<unsigned short>::resize(v97);
    std::vector<unsigned short>::resize(v101);
    LODWORD(v80) = v9;
    StringCchPrintfW(
      v97[0],
      v97[1] - v97[0],
      L"Failed the size check, actual: %ld, expected: %ld",
      (unsigned int)a2,
      v80);
    LODWORD(v82) = 475;
    StringCchPrintfW(v101[0], v101[1] - v101[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v82, v97[0]);
    v15 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v15 > 2u )
    {
      v89 = v101[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v15,
        (__int64)byte_180075AC5,
        v16,
        v17,
        (const unsigned __int16 **)&v89);
    }
    goto LABEL_6;
  }
  v90 = 0;
  v18 = v14 & 3;
  if ( (_BYTE)v18 == 3 )
  {
    v19 = (a3[12] & 1) == 0;
    v20 = *((_DWORD *)a3 + 2);
    if ( !*((_BYTE *)this + 76) || *((_DWORD *)this + 18) != v20 || *((_BYTE *)this + 80) != v19 )
    {
      *(_OWORD *)v97 = 0;
      v98 = 0;
      *(_OWORD *)v101 = 0;
      v102 = 0;
      std::vector<unsigned short>::resize(v97);
      std::vector<unsigned short>::resize(v101);
      LODWORD(v80) = v19;
      StringCchPrintfW(
        v97[0],
        v97[1] - v97[0],
        L"AuthInfo userAuthMode: [%d], isNeverAuthenticateOptionAllowed: [%d]",
        v20,
        v80);
      LODWORD(v83) = 489;
      StringCchPrintfW(v101[0], v101[1] - v101[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v83, v97[0]);
      v21 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v21 > 4u )
      {
        v89 = v101[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v21,
          (__int64)byte_180075AA5,
          v22,
          v23,
          (const unsigned __int16 **)&v89);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v101);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v97);
      *((_DWORD *)this + 18) = v20;
      *((_BYTE *)this + 76) = 1;
      *(_WORD *)((char *)this + 77) = *(_WORD *)((char *)&v89 + 5);
      *((_BYTE *)this + 79) = HIBYTE(v89);
      *((_BYTE *)this + 80) = v19;
      if ( !v19 && v20 == 2 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v90 = 1;
    }
  }
  if ( (a3[4] & 0xC) != 0xC || (v24 = 0, v99 = 0, !*((_DWORD *)a3 + 4)) )
  {
LABEL_98:
    if ( v90 )
    {
      if ( !*((_BYTE *)this + 76) )
        std::_Throw_bad_optional_access();
      LOBYTE(v18) = *((_BYTE *)this + 80);
      (*(void (__fastcall **)(char *, __int64, _QWORD))(*((_QWORD *)this + 1) + 80LL))(
        (char *)this + 8,
        v18,
        *((unsigned int *)this + 18));
    }
    *(_OWORD *)v91 = 0;
    v92 = 0;
    *(_OWORD *)v93 = 0;
    v94 = 0;
    std::vector<unsigned short>::resize(v91);
    std::vector<unsigned short>::resize(v93);
    StringCchPrintfW(v91[0], v91[1] - v91[0], L"Exit");
    LODWORD(v80) = 606;
    StringCchPrintfW(v93[0], v93[1] - v93[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v80, v91[0]);
    v73 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v73 > 5u )
    {
      v100[0] = v93[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v73,
        (__int64)&word_18007597E,
        v74,
        v75,
        v100);
    }
    goto LABEL_103;
  }
  while ( 1 )
  {
    v25 = 108 * v24;
    v26 = *(_DWORD *)&a3[108 * v24 + 20];
    if ( (v26 & 8) != 0 && *(_DWORD *)&a3[v25 + 112] == 3 )
    {
      *(_OWORD *)v93 = 0;
      v94 = 0;
      *(_OWORD *)v91 = 0;
      v92 = 0;
      std::vector<unsigned short>::resize(v93);
      std::vector<unsigned short>::resize(v91);
      StringCchPrintfW(v93[0], v93[1] - v93[0], L"Ignoring LPA_SERVICE_INFO for removed eSim {%ls}.", &a3[v25 + 24]);
      LODWORD(v80) = 507;
      StringCchPrintfW(v91[0], v91[1] - v91[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v80, v93[0]);
      v27 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v27 > 3u )
      {
        v89 = v91[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v27,
          (__int64)word_180075A82,
          v28,
          v29,
          (const unsigned __int16 **)&v89);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v91);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
      goto LABEL_97;
    }
    v92 = 0;
    *(_OWORD *)v91 = 0;
    if ( (v26 & 3) != 3 )
      break;
    v30 = 0;
    if ( (v26 & 0x20) != 0 )
    {
      LOBYTE(v30) = *(_DWORD *)&a3[v25 + 120] != 0;
      v96 = v30;
      *(_OWORD *)v93 = 0;
      v94 = 0;
      std::vector<unsigned short>::resize(v91);
      std::vector<unsigned short>::resize(v93);
      v34 = &a3[v25 + 24];
      LODWORD(v87) = *(_DWORD *)&a3[v25 + 124];
      LODWORD(v80) = *(_DWORD *)&a3[v25 + 120];
      StringCchPrintfW(v91[0], v91[1] - v91[0], L"eSim {%ls}, slot {%d}, with IsActive: {%d}", v34, v80, v87);
      LODWORD(v84) = 529;
      StringCchPrintfW(v93[0], v93[1] - v93[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v84, v91[0]);
      v35 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v35 > 4u )
      {
        v89 = v93[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v35,
          (__int64)byte_180075A21,
          v36,
          v37,
          (const unsigned __int16 **)&v89);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v91);
    }
    else
    {
      v96 = 0;
      *(_OWORD *)v93 = 0;
      v94 = 0;
      std::vector<unsigned short>::resize(v91);
      std::vector<unsigned short>::resize(v93);
      StringCchPrintfW(
        v91[0],
        v91[1] - v91[0],
        L"The LPA_ESIM_INFO is missing LPA_ESIM_SLOT_INFO, dwParam = 0x%08x. Interpreting as single slot eSim device with only Slot0.",
        *(unsigned int *)&a3[v25 + 20]);
      LODWORD(v80) = 523;
      StringCchPrintfW(v93[0], v93[1] - v93[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v80, v91[0]);
      v31 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v31 > 4u )
      {
        v89 = v93[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v31,
          (__int64)byte_180075A41,
          v32,
          v33,
          (const unsigned __int16 **)&v89);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v91);
      if ( *((_DWORD *)a3 + 4) == 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v34 = &a3[v25 + 24];
    }
    Src = 0;
    v104 = 0;
    v105 = 7;
    LOWORD(Src) = 0;
    CellularSettingUtils::GuidToString((GUID *)&a3[v25 + 92], &Src);
    v106 = 0;
    v107 = 0;
    v108 = 0;
    v38 = -1;
    do
      ++v38;
    while ( *(_WORD *)&v34[2 * v38] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v106, v34, v38);
    p_Src = (const char *)&Src;
    if ( v105 > 7 )
      p_Src = (const char *)Src;
    LODWORD(v88) = v30;
    wil::details::in1diag3::FailFast_IfMsg(
      retaddr,
      (void *)0x218,
      (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
      (const char *)(v107 == 0),
      "eSim ID empty while processing LPA_SERVICE_INFO for [Adapter:Slot] - [%ws:%d].",
      p_Src,
      v88);
    *(_OWORD *)v101 = *(_OWORD *)&a3[v25 + 92];
    LODWORD(v102) = v30;
    std::_Tree<std::_Tmap_traits<std::pair<_GUID,enum SimSlot>,std::shared_ptr<AdapterSlotData>,AdapterSlot_COMP,std::allocator<std::pair<std::pair<_GUID,enum SimSlot> const,std::shared_ptr<AdapterSlotData>>>,0>>::find(
      (char *)this + 88,
      v100,
      v101);
    if ( v100[0] == *((const unsigned __int16 **)this + 11) )
    {
      v89 = 0;
      CESimSettingApi::CreateInstance((__int128 *)&a3[v25 + 92], v30, (__int64)this, &v89);
      v40 = (char *)operator new(0x30u);
      v100[1] = (const unsigned __int16 *)v40;
      *(_OWORD *)v40 = 0;
      *((_DWORD *)v40 + 2) = 1;
      *((_DWORD *)v40 + 3) = 1;
      *(_QWORD *)v40 = &std::_Ref_count_obj2<AdapterSlotData>::`vftable';
      *((_QWORD *)v40 + 2) = 0;
      *((_QWORD *)v40 + 3) = 0;
      *((_QWORD *)v40 + 4) = 0;
      *((_QWORD *)v40 + 5) = 0;
      v100[3] = (const unsigned __int16 *)(v40 + 16);
      v100[4] = (const unsigned __int16 *)v40;
      *((_DWORD *)v40 + 4) = 0;
      v41 = v89;
      if ( *((unsigned __int16 **)v40 + 3) != v89 )
      {
        if ( v89 )
          (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v89 + 8LL))(v89);
        v42 = *((_QWORD *)v40 + 3);
        if ( v42 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        *((_QWORD *)v40 + 3) = v41;
      }
      v43 = (_QWORD *)std::map<std::pair<_GUID,enum SimSlot>,std::shared_ptr<AdapterSlotData>,AdapterSlot_COMP,std::allocator<std::pair<std::pair<_GUID,enum SimSlot> const,std::shared_ptr<AdapterSlotData>>>>::operator[](
                        (__int64 *)this + 11,
                        v101);
      _InterlockedIncrement((volatile signed __int32 *)v40 + 2);
      *v43 = v40 + 16;
      v44 = (volatile signed __int32 *)v43[1];
      v43[1] = v40;
      if ( v44 )
      {
        if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
          if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
        }
      }
      *(_OWORD *)v91 = 0;
      v92 = 0;
      *(_OWORD *)v93 = 0;
      v94 = 0;
      std::vector<unsigned short>::resize(v91);
      std::vector<unsigned short>::resize(v93);
      v45 = &Src;
      if ( v105 > 7 )
        v45 = (__int128 *)Src;
      LODWORD(v80) = v96;
      StringCchPrintfW(v91[0], v91[1] - v91[0], L"Created entry for [Adapter:Slot] - [%ls:%d].", v45, v80);
      LODWORD(v85) = 549;
      StringCchPrintfW(v93[0], v93[1] - v93[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v85, v91[0]);
      v46 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v46 > 4u )
      {
        v89 = v93[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v46,
          (__int64)byte_180075A01,
          v47,
          v48,
          (const unsigned __int16 **)&v89);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v91);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v40 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v40)(v40);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v40 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v40 + 8LL))(v40);
      }
      if ( v41 )
        (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v41 + 16LL))(v41);
    }
    if ( !CESimSettingServer::GetAdapterSlotData(this, &v106) )
    {
      v49 = std::map<std::pair<_GUID,enum SimSlot>,std::shared_ptr<AdapterSlotData>,AdapterSlot_COMP,std::allocator<std::pair<std::pair<_GUID,enum SimSlot> const,std::shared_ptr<AdapterSlotData>>>>::operator[](
              (__int64 *)this + 11,
              v101);
      v50 = *(_QWORD *)(v49 + 8);
      if ( v50 )
        _InterlockedIncrement((volatile signed __int32 *)(v50 + 8));
      v97[0] = *(unsigned __int16 **)v49;
      v51 = v97[0];
      v52 = *(_QWORD *)(v49 + 8);
      v97[1] = (unsigned __int16 *)v52;
      v53 = (unsigned __int16 *)operator new(0x268u);
      v100[2] = v53;
      *(_OWORD *)v53 = 0;
      *((_DWORD *)v53 + 2) = 1;
      *((_DWORD *)v53 + 3) = 1;
      *(_QWORD *)v53 = &std::_Ref_count_obj2<ESimData>::`vftable';
      memset_0(v53 + 8, 0, 0x258u);
      ESimData::ESimData((ESimData *)(v53 + 8));
      *((_QWORD *)v51 + 2) = v53 + 8;
      v55 = (volatile signed __int32 *)*((_QWORD *)v51 + 3);
      *((_QWORD *)v51 + 3) = v53;
      if ( v55 )
      {
        if ( _InterlockedExchangeAdd(v55 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
          if ( _InterlockedExchangeAdd(v55 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
        }
      }
      *(_DWORD *)(*((_QWORD *)v51 + 2) + 560LL) = -1;
      v56 = (char **)*((_QWORD *)v51 + 2);
      v57 = -1;
      do
        ++v57;
      while ( *(_WORD *)&v34[2 * v57] );
      if ( v57 > (unsigned __int64)v56[3] )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          v56,
          v57,
          v54,
          v34);
      }
      else
      {
        if ( (unsigned __int64)v56[3] <= 7 )
          v58 = (char *)*((_QWORD *)v51 + 2);
        else
          v58 = *v56;
        v56[2] = (char *)v57;
        v59 = 2 * v57;
        memmove_0(v58, v34, 2 * v57);
        *(_WORD *)&v58[v59] = 0;
      }
      *(_DWORD *)(*((_QWORD *)v51 + 2) + 32LL) = 1;
      *(_DWORD *)(*((_QWORD *)v51 + 2) + 36LL) = 0;
      v60 = *((_QWORD *)v51 + 1);
      *(_OWORD *)v93 = 0;
      v94 = 0;
      v95 = 0;
      v61 = -1;
      do
        ++v61;
      while ( *(_WORD *)&v34[2 * v61] );
      std::wstring::_Construct<1,unsigned short const *>((char **)v93, v34, v61);
      CESimSettingApi::ResetESimId(v60, v93);
      CESimSettingApi::ResetLpaHandle(*((CESimSettingApi **)v51 + 1), *((void **)this + 14));
      *(_OWORD *)v91 = 0;
      v92 = 0;
      *(_OWORD *)v93 = 0;
      v94 = 0;
      std::vector<unsigned short>::resize(v91);
      std::vector<unsigned short>::resize(v93);
      StringCchPrintfW(v91[0], v91[1] - v91[0], L"Updated the m_adapterSlotMap with an entry for eSim {%ls}", v34);
      LODWORD(v80) = 567;
      StringCchPrintfW(v93[0], v93[1] - v93[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v80, v91[0]);
      v62 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v62 > 4u )
      {
        v89 = v93[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v62,
          (__int64)byte_1800759E1,
          v63,
          v64,
          (const unsigned __int16 **)&v89);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v91);
      (*(void (__fastcall **)(char *, unsigned __int16 **, _QWORD, _QWORD))(*((_QWORD *)this + 1) + 24LL))(
        (char *)this + 8,
        v101,
        (unsigned int)v102,
        *((_QWORD *)v51 + 1));
      (*(void (__fastcall **)(char *, unsigned __int16 **, _QWORD, _QWORD, _DWORD))(*((_QWORD *)this + 1) + 32LL))(
        (char *)this + 8,
        v101,
        (unsigned int)v102,
        *(unsigned int *)(*((_QWORD *)v51 + 2) + 32LL),
        *(_DWORD *)(*((_QWORD *)v51 + 2) + 36LL));
      if ( !*((_BYTE *)this + 76) || *((_DWORD *)this + 18) >= 2u )
      {
        v96 = 0;
        v65 = LuiRegisterForEsimNotifications(*((_QWORD *)this + 14), 0, v34, &v96);
        v66 = retaddr;
        if ( v65 < 0 )
        {
          v76 = 579;
LABEL_107:
          wil::details::in1diag3::_Log_Hr(
            v66,
            (void *)v76,
            (int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\esimsettingserver.cpp",
            (const char *)(unsigned int)v65);
          if ( v52 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v52 + 8), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(__int64))v52)(v52);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v52 + 12), 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
            }
          }
          std::wstring::~wstring((char **)&v106);
          std::wstring::~wstring((char **)&Src);
          return;
        }
        *(_OWORD *)v91 = 0;
        v92 = 0;
        *(_OWORD *)v93 = 0;
        v94 = 0;
        std::vector<unsigned short>::resize(v91);
        std::vector<unsigned short>::resize(v93);
        StringCchPrintfW(
          v91[0],
          v91[1] - v91[0],
          L"LuiRegisterForEsimNotifications succeeded [Transaction ID]: %d",
          v96);
        LODWORD(v80) = 583;
        StringCchPrintfW(v93[0], v93[1] - v93[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v80, v91[0]);
        v67 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v67 > 4u )
        {
          v89 = v93[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v67,
            (__int64)byte_1800759C1,
            v68,
            v69,
            (const unsigned __int16 **)&v89);
        }
        std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
        std::vector<unsigned short>::~vector<unsigned short>((char **)v91);
        v65 = LuiRegisterForAllProfileNotifications(*((_QWORD *)this + 14), 0, v34, &v96);
        v66 = retaddr;
        if ( v65 < 0 )
        {
          v76 = 585;
          goto LABEL_107;
        }
        *(_OWORD *)v91 = 0;
        v92 = 0;
        *(_OWORD *)v93 = 0;
        v94 = 0;
        std::vector<unsigned short>::resize(v91);
        std::vector<unsigned short>::resize(v93);
        StringCchPrintfW(
          v91[0],
          v91[1] - v91[0],
          L"LuiRegisterForAllProfileNotifications succeeded [Transaction ID]: %d",
          v96);
        LODWORD(v86) = 589;
        StringCchPrintfW(v93[0], v93[1] - v93[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v86, v91[0]);
        v70 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v70 > 4u )
        {
          v89 = v93[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v70,
            (__int64)byte_1800759A1,
            v71,
            v72,
            (const unsigned __int16 **)&v89);
        }
        std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
        std::vector<unsigned short>::~vector<unsigned short>((char **)v91);
      }
      if ( v52 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v52 + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(__int64))v52)(v52);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v52 + 12), 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 8LL))(v52);
        }
      }
    }
    std::wstring::~wstring((char **)&v106);
    std::wstring::~wstring((char **)&Src);
LABEL_97:
    v24 = (unsigned int)(v99 + 1);
    v99 = v24;
    if ( (unsigned int)v24 >= *((_DWORD *)a3 + 4) )
      goto LABEL_98;
  }
  *(_OWORD *)v93 = 0;
  v94 = 0;
  std::vector<unsigned short>::resize(v91);
  std::vector<unsigned short>::resize(v93);
  StringCchPrintfW(
    v91[0],
    v91[1] - v91[0],
    L"LPA_ESIM_INFO in LPA_SERVICE_INFO is missing fields, dwParam = 0x%08x.",
    *(unsigned int *)&a3[v25 + 20]);
  LODWORD(v80) = 513;
  StringCchPrintfW(v93[0], v93[1] - v93[0], L"%S(%d):%s", "CESimSettingServer::ProcessServiceInfo", v80, v91[0]);
  v77 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v77 > 2u )
  {
    v100[0] = v93[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v77,
      (__int64)byte_180075A61,
      v78,
      v79,
      v100);
  }
LABEL_103:
  std::vector<unsigned short>::~vector<unsigned short>((char **)v93);
  v13 = v91;
LABEL_104:
  std::vector<unsigned short>::~vector<unsigned short>((char **)v13);
}

```

## disassembly

```asm
0x180024a88  mov     [rsp-8+arg_18], rbx
0x180024a8d  push    rbp
0x180024a8e  push    rsi
0x180024a8f  push    rdi
0x180024a90  push    r12
0x180024a92  push    r13
0x180024a94  push    r14
0x180024a96  push    r15
0x180024a98  lea     rbp, [rsp-40h]
0x180024a9d  sub     rsp, 140h
0x180024aa4  mov     rax, cs:__security_cookie
0x180024aab  xor     rax, rsp
0x180024aae  mov     [rbp+70h+var_40], rax
0x180024ab2  mov     r15, r8
0x180024ab5  mov     rdi, rdx
0x180024ab8  mov     r14, rcx
0x180024abb  xor     r13d, r13d
0x180024abe  xorps   xmm0, xmm0
0x180024ac1  movdqu  xmmword ptr [rbp+70h+var_E0], xmm0
0x180024ac6  mov     [rbp+70h+var_D0], r13
0x180024aca  movdqu  xmmword ptr [rbp+70h+var_98], xmm0
0x180024acf  mov     [rbp+70h+var_88], r13
0x180024ad3  lea     rcx, [rbp+70h+var_E0]
0x180024ad7  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180024adc  lea     rcx, [rbp+70h+var_98]
0x180024ae0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180024ae5  mov     rdx, [rbp+70h+var_E0+8]
0x180024ae9  mov     rcx, [rbp+70h+var_E0]; unsigned __int16 *
0x180024aed  sub     rdx, rcx
0x180024af0  sar     rdx, 1; unsigned __int64
0x180024af3  lea     r8, aEnter; "Enter"
0x180024afa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024aff  mov     rdx, [rbp+70h+var_98+8]
0x180024b03  mov     rcx, [rbp+70h+var_98]; unsigned __int16 *
0x180024b07  sub     rdx, rcx
0x180024b0a  sar     rdx, 1; unsigned __int64
0x180024b0d  mov     rax, [rbp+70h+var_E0]
0x180024b11  mov     [rsp+170h+var_148], rax
0x180024b16  mov     dword ptr [rsp+170h+var_150], 1CAh
0x180024b1e  lea     rsi, aCesimsettingse_16; "CESimSettingServer::ProcessServiceInfo"
0x180024b25  mov     r9, rsi
0x180024b28  lea     r12, aSDS; "%S(%d):%s"
0x180024b2f  mov     r8, r12; unsigned __int16 *
0x180024b32  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024b37  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180024b3c  mov     ecx, [rax]
0x180024b3e  cmp     ecx, 5
0x180024b41  jbe     short loc_180024B66
0x180024b43  mov     rcx, [rbp+70h+var_98]
0x180024b47  mov     [rsp+170h+var_130], rcx
0x180024b4c  lea     rcx, [rsp+170h+var_130]
0x180024b51  mov     [rsp+170h+var_150], rcx
0x180024b56  lea     rdx, byte_180075B07
0x180024b5d  mov     rcx, rax
0x180024b60  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180024b65  nop
0x180024b66  lea     rcx, [rbp+70h+var_98]
0x180024b6a  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180024b6f  nop
0x180024b70  lea     rcx, [rbp+70h+var_E0]
0x180024b74  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180024b79  mov     ebx, 14h
0x180024b7e  cmp     rdi, rbx
0x180024b81  jnb     loc_180024C3B
0x180024b87  xorps   xmm0, xmm0
0x180024b8a  movdqu  xmmword ptr [rbp+70h+var_E0], xmm0
0x180024b8f  mov     [rbp+70h+var_D0], r13
0x180024b93  movdqu  xmmword ptr [rbp+70h+var_98], xmm0
0x180024b98  mov     [rbp+70h+var_88], r13
0x180024b9c  lea     rcx, [rbp+70h+var_E0]
0x180024ba0  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180024ba5  lea     rcx, [rbp+70h+var_98]
0x180024ba9  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180024bae  mov     r9d, edi
0x180024bb1  mov     rdx, [rbp+70h+var_E0+8]
0x180024bb5  mov     rcx, [rbp+70h+var_E0]; unsigned __int16 *
0x180024bb9  sub     rdx, rcx
0x180024bbc  sar     rdx, 1; unsigned __int64
0x180024bbf  mov     dword ptr [rsp+170h+var_150], ebx
0x180024bc3  lea     r8, aBufferSizeLdMu; "Buffer size: %ld, must be at least: %ld"
0x180024bca  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024bcf  mov     rdx, [rbp+70h+var_98+8]
0x180024bd3  mov     rcx, [rbp+70h+var_98]; unsigned __int16 *
0x180024bd7  sub     rdx, rcx
0x180024bda  sar     rdx, 1; unsigned __int64
0x180024bdd  mov     rax, [rbp+70h+var_E0]
0x180024be1  mov     [rsp+170h+var_148], rax
0x180024be6  mov     dword ptr [rsp+170h+var_150], 1CFh
0x180024bee  mov     r9, rsi
0x180024bf1  mov     r8, r12; unsigned __int16 *
0x180024bf4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024bf9  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180024bfe  mov     ecx, [rax]
0x180024c00  cmp     ecx, 2
0x180024c03  jbe     short loc_180024C28
0x180024c05  mov     rcx, [rbp+70h+var_98]
0x180024c09  mov     [rsp+170h+var_130], rcx
0x180024c0e  lea     rcx, [rsp+170h+var_130]
0x180024c13  mov     [rsp+170h+var_150], rcx
0x180024c18  lea     rdx, word_180075AE6
0x180024c1f  mov     rcx, rax
0x180024c22  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180024c27  nop
0x180024c28  lea     rcx, [rbp+70h+var_98]
0x180024c2c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180024c31  nop
0x180024c32  lea     rcx, [rbp+70h+var_E0]
0x180024c36  jmp     loc_1800259B3
0x180024c3b  mov     edx, [r15+4]
0x180024c3f  mov     eax, edx
0x180024c41  and     eax, 0Ch
0x180024c44  cmp     al, 0Ch
0x180024c46  jnz     short loc_180024C53
0x180024c48  mov     eax, [r15+10h]
0x180024c4c  imul    rcx, rax, 6Ch ; 'l'
0x180024c50  add     rbx, rcx
0x180024c53  cmp     rbx, rdi
0x180024c56  jz      loc_180024D0C
0x180024c5c  xorps   xmm0, xmm0
0x180024c5f  movdqu  xmmword ptr [rbp+70h+var_E0], xmm0
0x180024c64  mov     [rbp+70h+var_D0], r13
0x180024c68  movdqu  xmmword ptr [rbp+70h+var_98], xmm0
0x180024c6d  mov     [rbp+70h+var_88], r13
0x180024c71  lea     rcx, [rbp+70h+var_E0]
0x180024c75  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180024c7a  lea     rcx, [rbp+70h+var_98]
0x180024c7e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180024c83  mov     r9d, edi
0x180024c86  mov     rdx, [rbp+70h+var_E0+8]
0x180024c8a  mov     rcx, [rbp+70h+var_E0]; unsigned __int16 *
0x180024c8e  sub     rdx, rcx
0x180024c91  sar     rdx, 1; unsigned __int64
0x180024c94  mov     dword ptr [rsp+170h+var_150], ebx
0x180024c98  lea     r8, aFailedTheSizeC; "Failed the size check, actual: %ld, exp"...
0x180024c9f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024ca4  mov     rdx, [rbp+70h+var_98+8]
0x180024ca8  mov     rcx, [rbp+70h+var_98]; unsigned __int16 *
0x180024cac  sub     rdx, rcx
0x180024caf  sar     rdx, 1; unsigned __int64
0x180024cb2  mov     rax, [rbp+70h+var_E0]
0x180024cb6  mov     [rsp+170h+var_148], rax
0x180024cbb  mov     dword ptr [rsp+170h+var_150], 1DBh
0x180024cc3  mov     r9, rsi
0x180024cc6  mov     r8, r12; unsigned __int16 *
0x180024cc9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024cce  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180024cd3  mov     ecx, [rax]
0x180024cd5  cmp     ecx, 2
0x180024cd8  jbe     short loc_180024CFD
0x180024cda  mov     rcx, [rbp+70h+var_98]
0x180024cde  mov     [rsp+170h+var_130], rcx
0x180024ce3  lea     rcx, [rsp+170h+var_130]
0x180024ce8  mov     [rsp+170h+var_150], rcx
0x180024ced  lea     rdx, byte_180075AC5
0x180024cf4  mov     rcx, rax
0x180024cf7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180024cfc  nop
0x180024cfd  lea     rcx, [rbp+70h+var_98]
0x180024d01  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180024d06  nop
0x180024d07  jmp     loc_180024C32
0x180024d0c  mov     [rsp+170h+var_128], r13b
0x180024d11  and     edx, 3
0x180024d14  cmp     dl, 3
0x180024d17  jnz     loc_180024E29
0x180024d1d  mov     bl, [r15+0Ch]
0x180024d21  not     bl
0x180024d23  and     bl, 1
0x180024d26  mov     edi, [r15+8]
0x180024d2a  cmp     [r14+4Ch], r13b
0x180024d2e  jz      short loc_180024D40
0x180024d30  cmp     [r14+48h], edi
0x180024d34  jnz     short loc_180024D40
0x180024d36  cmp     [r14+50h], bl
0x180024d3a  jz      loc_180024E29
0x180024d40  xorps   xmm0, xmm0
0x180024d43  movdqu  xmmword ptr [rbp+70h+var_E0], xmm0
0x180024d48  mov     [rbp+70h+var_D0], r13
0x180024d4c  movdqu  xmmword ptr [rbp+70h+var_98], xmm0
0x180024d51  mov     [rbp+70h+var_88], r13
0x180024d55  lea     rcx, [rbp+70h+var_E0]
0x180024d59  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180024d5e  lea     rcx, [rbp+70h+var_98]
0x180024d62  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180024d67  movzx   eax, bl
0x180024d6a  mov     rdx, [rbp+70h+var_E0+8]
0x180024d6e  mov     rcx, [rbp+70h+var_E0]; unsigned __int16 *
0x180024d72  sub     rdx, rcx
0x180024d75  sar     rdx, 1; unsigned __int64
0x180024d78  mov     dword ptr [rsp+170h+var_150], eax
0x180024d7c  mov     r9d, edi
0x180024d7f  lea     r8, aAuthinfoUserau; "AuthInfo userAuthMode: [%d], isNeverAut"...
0x180024d86  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024d8b  mov     rdx, [rbp+70h+var_98+8]
0x180024d8f  mov     rcx, [rbp+70h+var_98]; unsigned __int16 *
0x180024d93  sub     rdx, rcx
0x180024d96  sar     rdx, 1; unsigned __int64
0x180024d99  mov     rax, [rbp+70h+var_E0]
0x180024d9d  mov     [rsp+170h+var_148], rax
0x180024da2  mov     dword ptr [rsp+170h+var_150], 1E9h
0x180024daa  mov     r9, rsi
0x180024dad  mov     r8, r12; unsigned __int16 *
0x180024db0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024db5  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180024dba  mov     ecx, [rax]
0x180024dbc  cmp     ecx, 4
0x180024dbf  jbe     short loc_180024DE4
0x180024dc1  mov     rcx, [rbp+70h+var_98]
0x180024dc5  mov     [rsp+170h+var_130], rcx
0x180024dca  lea     rcx, [rsp+170h+var_130]
0x180024dcf  mov     [rsp+170h+var_150], rcx
0x180024dd4  lea     rdx, byte_180075AA5
0x180024ddb  mov     rcx, rax
0x180024dde  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180024de3  nop
0x180024de4  lea     rcx, [rbp+70h+var_98]
0x180024de8  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180024ded  nop
0x180024dee  lea     rcx, [rbp+70h+var_E0]
0x180024df2  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180024df7  mov     [r14+48h], edi
0x180024dfb  mov     byte ptr [r14+4Ch], 1
0x180024e00  movzx   eax, word ptr [rsp+170h+var_130+5]
0x180024e05  mov     [r14+4Dh], ax
0x180024e0a  mov     al, byte ptr [rsp+170h+var_130+7]
0x180024e0e  mov     [r14+4Fh], al
0x180024e12  mov     [r14+50h], bl
0x180024e16  test    bl, bl
0x180024e18  jnz     short loc_180024E24
0x180024e1a  cmp     edi, 2
0x180024e1d  jnz     short loc_180024E24
0x180024e1f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024e24  mov     [rsp+170h+var_128], 1
0x180024e29  mov     eax, [r15+4]
0x180024e2d  and     eax, 0Ch
0x180024e30  cmp     al, 0Ch
0x180024e32  jnz     loc_1800258D6
0x180024e38  mov     eax, r13d
0x180024e3b  mov     [rbp+70h+var_C8], eax
0x180024e3e  cmp     [r15+10h], r13d
0x180024e42  jbe     loc_1800258D6
0x180024e48  imul    rbx, rax, 6Ch ; 'l'
0x180024e4c  mov     ecx, [rbx+r15+14h]
0x180024e51  test    cl, 8
0x180024e54  jz      loc_180024F2D
0x180024e5a  cmp     dword ptr [rbx+r15+70h], 3
0x180024e60  jnz     loc_180024F2D
0x180024e66  xorps   xmm0, xmm0
0x180024e69  movdqu  xmmword ptr [rsp+170h+var_108], xmm0
0x180024e6f  mov     [rsp+170h+var_F8], r13
0x180024e74  movdqu  xmmword ptr [rsp+170h+var_120], xmm0
0x180024e7a  mov     [rsp+170h+var_110], r13
0x180024e7f  lea     rcx, [rsp+170h+var_108]
0x180024e84  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180024e89  lea     rcx, [rsp+170h+var_120]
0x180024e8e  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180024e93  lea     r9, [r15+18h]
0x180024e97  add     r9, rbx
0x180024e9a  mov     rdx, [rsp+170h+var_108+8]
0x180024e9f  mov     rcx, [rsp+170h+var_108]; unsigned __int16 *
0x180024ea4  sub     rdx, rcx
0x180024ea7  sar     rdx, 1; unsigned __int64
0x180024eaa  lea     r8, aIgnoringLpaSer; "Ignoring LPA_SERVICE_INFO for removed e"...
0x180024eb1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024eb6  mov     rdx, [rsp+170h+var_120+8]
0x180024ebb  mov     rcx, [rsp+170h+var_120]; unsigned __int16 *
0x180024ec0  sub     rdx, rcx
0x180024ec3  sar     rdx, 1; unsigned __int64
0x180024ec6  mov     rax, [rsp+170h+var_108]
0x180024ecb  mov     [rsp+170h+var_148], rax
0x180024ed0  mov     dword ptr [rsp+170h+var_150], 1FBh
0x180024ed8  mov     r9, rsi
0x180024edb  mov     r8, r12; unsigned __int16 *
0x180024ede  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180024ee3  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180024ee8  mov     ecx, [rax]
0x180024eea  cmp     ecx, 3
0x180024eed  jbe     short loc_180024F13
0x180024eef  mov     rcx, [rsp+170h+var_120]
0x180024ef4  mov     [rsp+170h+var_130], rcx
0x180024ef9  lea     rcx, [rsp+170h+var_130]
0x180024efe  mov     [rsp+170h+var_150], rcx
0x180024f03  lea     rdx, word_180075A82
0x180024f0a  mov     rcx, rax
0x180024f0d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180024f12  nop
0x180024f13  lea     rcx, [rsp+170h+var_120]
0x180024f18  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180024f1d  nop
0x180024f1e  lea     rcx, [rsp+170h+var_108]
0x180024f23  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180024f28  jmp     loc_1800258C4
0x180024f2d  mov     eax, ecx
0x180024f2f  and     eax, 3
0x180024f32  xorps   xmm0, xmm0
0x180024f35  mov     [rsp+170h+var_110], r13
0x180024f3a  movdqu  xmmword ptr [rsp+170h+var_120], xmm0
0x180024f40  cmp     al, 3
0x180024f42  jnz     loc_180025A50
0x180024f48  mov     edi, r13d
  ... truncated ...
```
