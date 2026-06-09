# cdp::ActivityManager::HandleActivities(std::vector<shared::ActivityData,std::allocator<shared::ActivityData>> const &,shared::ActivityDataOrigin,cdp::ActivityCompletionOperation const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool)

- ea: `0x180043140`
- end: `0x180044610`
- name: `?HandleActivities@ActivityManager@cdp@@AEAA?AV?$vector@UActivityData@shared@@V?$allocator@UActivityData@shared@@@std@@@std@@AEBV34@W4ActivityDataOrigin@shared@@AEBVActivityCompletionOperation@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@_N@Z`
- size: `5328`
- prototype: `__int64 __usercall@<rax>(cdp::ActivityManager *this@<rcx>, __int64, __int64, char)`
- caller_count: `5`
- callee_count: `67`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800220a8`
- `0x18004bac4`
- `0x1800b96b0`
- `0x1801516b4`
- `0x1802ef300`

## callees

- `0x18000d350`
- `0x18000f8d0`
- `0x18000fac0`
- `0x180010ee0`
- `0x1800110f8`
- `0x1800113bc`
- `0x180013d6c`
- `0x180013da0`
- `0x18001ee70`
- `0x180030190`
- `0x180034638`
- `0x180035df8`
- `0x180036224`
- `0x1800370f0`
- `0x180042af8`
- `0x180043140`
- `0x180044618`
- `0x18004474c`
- `0x18004512c`
- `0x180046b64`
- `0x18004b9b4`
- `0x18004e170`
- `0x180052cc8`
- `0x180061db0`
- `0x180065cdc`
- `0x1800677f0`
- `0x180067954`
- `0x18006a280`
- `0x18006b714`
- `0x18006b7cc`
- `0x18006cae0`
- `0x18006cda4`
- `0x18006ce7c`
- `0x18006d02c`
- `0x1800710d8`
- `0x18007120c`
- `0x180072df0`
- `0x180074b50`
- `0x1800754b0`
- `0x1800784bc`
- `0x18007e71c`
- `0x18008dbc0`
- `0x18008e820`
- `0x1800a5020`
- `0x1800a77d4`
- `0x1800bef10`
- `0x1800d7ec0`
- `0x1800dd81c`
- `0x1800f07a8`
- `0x1800fb5b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strtoui64` at `0x180043941`
- `api-ms-win-crt-private-l1-1-0!_o__strtoui64` at `0x180043941`
- `msvcp_win!_Mtx_unlock` at `0x180044214`
- `msvcp_win!_Mtx_unlock` at `0x18004434a`
- `msvcp_win!_Mtx_unlock` at `0x180044214`
- `msvcp_win!_Mtx_unlock` at `0x18004434a`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180043dd4`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180043dd4`

## string_xrefs

- `0x18004396f`: `{"text":"Received a new Data Encryption Key with keyVersion=%llu and createdInCloudTime=%llu"}`
- `0x1800439c9`: `{"text":"Updating CreatedInCloud time for an existing Data Encryption Key"}`
- `0x180043a68`: `{"text":"Skipping updating CreatedInCloudTime for DEK activity %s because the timestamp is invalid."}`
- `0x1800444ef`: `Completed processing activities received during `
- `0x18004377e`: `ActivityStore.HandleDeleteActivity`
- `0x18004380d`: `{"text":"Cannot delete activity as it doesn't exist locally in the database. Ignoring."}`
- `0x180043d49`: `SELECT [Id], [AppId], [PackageIdHash], [AppActivityId], [ActivityType], [ActivityStatus], [ParentActivityId], [Tag], [Group], [MatchId], [LastModifiedTime], [ExpirationTime], [Payload], [Priority], [IsLocalOnly], [PlatformDeviceId], [CreatedInCloud], [StartTime], [EndTime], [LastModifiedOnClient], [IsInUploadQueue], [GroupAppActivityId], [ETag], [ClipboardPayload], [EnterpriseId], [UserActionState], [IsRead], [OriginalPayload], [OriginalLastModifiedOnClient], [GroupItems], [DdsDeviceId] FROM [Sm`
- `0x180043896`: `dds.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=42
_QWORD *__fastcall cdp::ActivityManager::HandleActivities(
        cdp::ActivityManager *this,
        _QWORD *a2,
        _QWORD *a3,
        char a4,
        __int64 a5,
        __int64 a6,
        char a7)
{
  cdp::ActivityManager *v9; // rsi
  ActivityFeedClient::DataEncryptionKey *v10; // rax
  __m128i si128; // xmm6
  struct _Mtx_internal_imp_t *v12; // rdi
  volatile signed __int32 *v13; // rax
  std::_Ref_count_base *v14; // rcx
  _DWORD *v15; // r15
  int v16; // esi
  cdp::ActivityManager *v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rax
  _DWORD *i; // rax
  cdp::ActivityManager *v21; // rsi
  struct shared::ActivityPolicies *Policies; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  unsigned int v26; // edx
  _QWORD *v27; // rax
  __int64 v28; // rsi
  void (__fastcall *v29)(__int64, struct _GUID *, std::_Ref_count_base **, _QWORD, int, __int128 *, const char *, _QWORD); // r14
  __int128 *v30; // rbx
  int v31; // r14d
  __int64 v32; // rcx
  const char *v33; // rax
  char *v34; // r8
  int v35; // ecx
  int v36; // edx
  _QWORD *v37; // rcx
  const char *v38; // rax
  const char *v39; // r8
  std::_Ref_count_base *v40; // rax
  std::_Ref_count_base *v41; // rcx
  std::_Ref_count_base *v42; // rdx
  __int64 v43; // rcx
  std::_Ref_count_base *v44; // rax
  std::_Ref_count_base *v45; // rdx
  std::_Ref_count_base *v46; // rcx
  std::_Ref_count_base *v47; // rbx
  __time64_t v48; // rax
  const struct ActivityFeedClient::ActivityData *v49; // rbx
  _QWORD *v50; // rax
  int v51; // r14d
  int v52; // eax
  int v53; // ecx
  int v54; // edx
  int v55; // r10d
  int v56; // r11d
  int v57; // esi
  int v58; // r14d
  int v59; // r15d
  _DWORD *v60; // r12
  __int128 *v61; // rax
  __int64 v62; // rdx
  int v63; // ebx
  _QWORD *v64; // rax
  int v65; // edx
  _QWORD *v66; // rax
  _DWORD *v67; // rcx
  __int64 v68; // rdx
  const char *v69; // r8
  char v70; // r14
  int v71; // r9d
  cdp::ActivityManager *v72; // rcx
  _QWORD *v73; // r15
  const struct shared::ActivityData *v74; // rbx
  const struct shared::ActivityData *v75; // rdi
  _QWORD *v76; // rdi
  const char *v77; // rbx
  __int64 v78; // rsi
  void (__fastcall *v79)(__int64, std::_Ref_count_base **, int *, _QWORD, int, __int128 *, const char *, _QWORD, _QWORD); // rdi
  __int128 *v80; // rbx
  __int64 v82; // rbx
  __int64 v83; // rax
  __int64 v84; // rdx
  __int64 v85; // r8
  _QWORD *v86; // rax
  int v87; // [rsp+20h] [rbp-738h]
  char v88; // [rsp+70h] [rbp-6E8h]
  char v89; // [rsp+71h] [rbp-6E7h]
  int v90; // [rsp+74h] [rbp-6E4h] BYREF
  int v91; // [rsp+78h] [rbp-6E0h]
  int v92; // [rsp+7Ch] [rbp-6DCh] BYREF
  _DWORD *v93; // [rsp+80h] [rbp-6D8h] BYREF
  std::_Ref_count_base *v94[2]; // [rsp+88h] [rbp-6D0h] BYREF
  unsigned int v95; // [rsp+98h] [rbp-6C0h] BYREF
  unsigned __int64 v96; // [rsp+A0h] [rbp-6B8h] BYREF
  cdp::ActivityManager *v97; // [rsp+A8h] [rbp-6B0h]
  _QWORD *v98; // [rsp+B0h] [rbp-6A8h]
  _QWORD *v99; // [rsp+B8h] [rbp-6A0h] BYREF
  std::_Ref_count_base *v100[2]; // [rsp+C0h] [rbp-698h] BYREF
  void *v101; // [rsp+D0h] [rbp-688h] BYREF
  __int64 v102; // [rsp+D8h] [rbp-680h]
  ActivityFeedClient::DataEncryptionKey *v103; // [rsp+E0h] [rbp-678h] BYREF
  __int64 v104; // [rsp+E8h] [rbp-670h] BYREF
  __int64 (__fastcall *v105)(); // [rsp+F0h] [rbp-668h] BYREF
  std::_Ref_count_base *v106; // [rsp+F8h] [rbp-660h]
  __int64 v107; // [rsp+100h] [rbp-658h] BYREF
  _QWORD *v108; // [rsp+108h] [rbp-650h]
  struct ActivityFeedClient::ActivityData *v109; // [rsp+110h] [rbp-648h] BYREF
  std::_Ref_count_base *v110; // [rsp+118h] [rbp-640h]
  _QWORD *v111; // [rsp+120h] [rbp-638h]
  __int64 v112; // [rsp+128h] [rbp-630h]
  void (__fastcall ***v113)(_QWORD, __int64); // [rsp+130h] [rbp-628h] BYREF
  __int64 v114; // [rsp+138h] [rbp-620h]
  cdp::ActivityManager *v115; // [rsp+140h] [rbp-618h]
  cdp::ActivityManager *v116; // [rsp+148h] [rbp-610h]
  _BYTE v117[8]; // [rsp+150h] [rbp-608h] BYREF
  char *v118; // [rsp+158h] [rbp-600h]
  _BYTE v119[8]; // [rsp+160h] [rbp-5F8h] BYREF
  std::_Ref_count_base *v120; // [rsp+168h] [rbp-5F0h] BYREF
  volatile signed __int32 *v121; // [rsp+170h] [rbp-5E8h]
  _BYTE v122[8]; // [rsp+190h] [rbp-5C8h] BYREF
  std::_Ref_count_base *v123; // [rsp+198h] [rbp-5C0h]
  _BYTE v124[12]; // [rsp+1A0h] [rbp-5B8h] BYREF
  int v125; // [rsp+1ACh] [rbp-5ACh]
  _BYTE v126[8]; // [rsp+1B8h] [rbp-5A0h] BYREF
  std::_Ref_count_base *v127; // [rsp+1C0h] [rbp-598h]
  struct _GUID v128; // [rsp+1D0h] [rbp-588h] BYREF
  _BYTE v129[48]; // [rsp+1E0h] [rbp-578h] BYREF
  __int128 v130; // [rsp+210h] [rbp-548h] BYREF
  __int128 v131; // [rsp+220h] [rbp-538h] BYREF
  __int128 v132; // [rsp+230h] [rbp-528h]
  std::_Ref_count_base *v133[2]; // [rsp+240h] [rbp-518h] BYREF
  std::_Ref_count_base *v134[2]; // [rsp+250h] [rbp-508h]
  struct _GUID v135; // [rsp+260h] [rbp-4F8h] BYREF
  __int128 v136; // [rsp+280h] [rbp-4D8h] BYREF
  __int64 v137; // [rsp+290h] [rbp-4C8h]
  unsigned __int64 v138; // [rsp+298h] [rbp-4C0h]
  unsigned __int64 v139; // [rsp+2A0h] [rbp-4B8h] BYREF
  _BYTE v140[16]; // [rsp+2A8h] [rbp-4B0h] BYREF
  _BYTE v141[16]; // [rsp+2B8h] [rbp-4A0h] BYREF
  __int64 v142; // [rsp+2C8h] [rbp-490h]
  _BYTE v143[32]; // [rsp+2E0h] [rbp-478h] BYREF
  int v144; // [rsp+300h] [rbp-458h]
  char v145; // [rsp+305h] [rbp-453h]
  __int64 v146; // [rsp+3B8h] [rbp-3A0h]
  __int64 v147; // [rsp+3C0h] [rbp-398h]
  char v148; // [rsp+478h] [rbp-2E0h]
  _BYTE v149[528]; // [rsp+4F0h] [rbp-268h] BYREF

  v98 = a2;
  v9 = this;
  v97 = this;
  v115 = this;
  v116 = this;
  v111 = a2;
  v112 = a5;
  v114 = a6;
  v91 = 0;
  v104 = 0xF83E0F83E0F83E1LL * ((__int64)(a3[1] - *a3) >> 4);
  v108 = (_QWORD *)((char *)this + 224);
  v99 = (_QWORD *)((char *)this + 248);
  if ( *((_QWORD *)this + 31) <= 0xFu )
    v10 = (cdp::ActivityManager *)((char *)this + 224);
  else
    v10 = (ActivityFeedClient::DataEncryptionKey *)*((_QWORD *)this + 28);
  v103 = v10;
  Log<char const *,unsigned __int64>(
    3,
    "{\"text\":\"Begin HandleActivities (stableUserId=%s activityCount=%lu)\"}",
    (const char *)&v103,
    (unsigned int)&v104);
  try
  {
    v95 = 0;
    v88 = 0;
    *a2 = 0;
    a2[1] = 0;
    a2[2] = 0;
    v31 = 1;
    v90 = 1;
    v91 = 1;
    cdp::ActivityManager::GetDatabaseConnectionLease(v9, v119);
    v102 = 0;
    v89 = 0;
    v66 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(32);
    *v66 = v66;
    v66[1] = v66;
    v66[2] = v66;
    *((_WORD *)v66 + 12) = 257;
    v101 = v66;
    v136 = 0;
    v137 = 0;
    v60 = (_DWORD *)*a3;
    v67 = (_DWORD *)a3[1];
    v104 = (__int64)v67;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v93 = v60;
      if ( v60 == v67 )
        break;
      v12 = (cdp::ActivityManager *)((char *)v9 + 296);
      v118 = (char *)v9 + 296;
      std::_Mutex_base::lock((cdp::ActivityManager *)((char *)v9 + 296));
      *(_OWORD *)v94 = 0;
      v13 = v121;
      if ( v121 )
      {
        _InterlockedIncrement(v121 + 2);
        v13 = v121;
      }
      v14 = v120;
      v94[0] = v120;
      v94[1] = (std::_Ref_count_base *)v13;
      *(_OWORD *)v100 = 0;
      if ( v13 )
      {
        _InterlockedIncrement(v13 + 2);
        v13 = v121;
        v14 = v120;
      }
      v100[0] = v14;
      v100[1] = (std::_Ref_count_base *)v13;
      v15 = v60 + 8;
      v16 = v60[8];
      v17 = v97;
      if ( *((_QWORD *)v97 + 76) == *((_QWORD *)v97 + 77) )
      {
        Log<>(4, "{\"text\":\"Loading known subscription types from database\"}");
        cdp::ActivityManager::GetDatabaseConnectionLease(v17, v129);
        v19 = cdp::ActivityManager::LoadAFSSettingsFromDatabase(v18, &v139, v129);
        std::vector<enum CDPActivityType>::operator=((char *)v17 + 608, v19);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v141);
        std::vector<enum CDPActivityType>::_Tidy(&v139);
        ActivityFeedClient::ConnectionLease::RestoreConnectionToPool((ActivityFeedClient::ConnectionLease *)v129);
        ActivityFeedClient::ConnectionLease::~ConnectionLease((ActivityFeedClient::ConnectionLease *)v129);
      }
      *(_QWORD *)&v135.Data1 = v60 + 8;
      for ( i = (_DWORD *)*((_QWORD *)v17 + 76); i != *((_DWORD **)v116 + 77); ++i )
      {
        if ( *i == v16 )
          goto LABEL_17;
      }
      std::_Tree<std::_Tset_traits<enum CDPActivityType,std::less<enum CDPActivityType>,std::allocator<enum CDPActivityType>,0>>::_Emplace<enum CDPActivityType>(
        &v101,
        v124,
        v60 + 8);
LABEL_17:
      v21 = v97;
      Policies = cdp::ActivityManager::GetPolicies(v97);
      if ( !(unsigned __int8)shared::ActivityPolicies::CanPerformOperation(Policies, v60, 2) )
      {
        v135 = *(struct _GUID *)v60;
        v23 = (_QWORD *)cdp::CDP_UUID::ToString(&v135, &v131);
        if ( v23[3] > 0xFu )
          v23 = (_QWORD *)*v23;
        *(_QWORD *)&v130 = v23;
        Log<unsigned __int64 &>(
          3,
          "{\"text\":\"Skipping activity %s because it is blocked by Policy\"}",
          (const char *)&v130);
        goto LABEL_21;
      }
      if ( *((_BYTE *)v60 + 37) && *((_BYTE *)v60 + 37) != 1 )
      {
        if ( *((_BYTE *)v60 + 37) == 2 )
        {
          v135 = *(struct _GUID *)v60;
          ActivityFeedClient::SmartActivityReader::GetActivityById(v94, &v107, &v135);
          if ( v107 )
          {
            cdp::TransformActivityDataFromDbToCloudModel(v143);
            v146 = *((_QWORD *)v60 + 27);
            v147 = *((_QWORD *)v60 + 28);
            v145 = 2;
            v148 = 2;
            std::vector<shared::ActivityData>::emplace_back<shared::ActivityData const &>(v98, v143);
            v135 = *(struct _GUID *)v60;
            v24 = (_QWORD *)cdp::CDP_UUID::ToString(&v135, &v131);
            if ( v24[3] > 0xFu )
              v24 = (_QWORD *)*v24;
            *(_QWORD *)&v130 = v24;
            Log<unsigned __int64 &>(4, "{\"text\":\"Tombstoning the activity %s\"}", (const char *)&v130);
            std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v131);
            v135 = *(struct _GUID *)v60;
            ActivityFeedClient::ActivityWriter::UpdateActivityStatus(v100, &v135);
            if ( (unsigned int)(v144 - 11) <= 1 )
            {
              v135 = *(struct _GUID *)v60;
              v25 = (_QWORD *)cdp::CDP_UUID::ToString(&v135, &v131);
              if ( v25[3] > 0xFu )
                v25 = (_QWORD *)*v25;
              *(_QWORD *)&v130 = v25;
              Log<unsigned __int64 &>(
                4,
                "{\"text\":\"Writing deletion time of CDS activity %s to database\"}",
                (const char *)&v130);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v131);
              v135 = *(struct _GUID *)v60;
              ActivityFeedClient::ActivityWriter::TombstoneActivity(
                (ActivityFeedClient::ActivityWriter *)v100,
                &v135,
                *((_QWORD *)v60 + 32));
            }
            if ( (unsigned __int8)cdp::ActivityManager::CanUploadTelemetryForActivityType(*(unsigned __int8 *)(v107 + 152)) )
            {
              *(_QWORD *)&v130 = EnumMapper::ToString(v26);
              v135 = *(struct _GUID *)v60;
              v27 = (_QWORD *)cdp::CDP_UUID::ToString(&v135, v133);
              if ( v27[3] > 0xFu )
                v27 = (_QWORD *)*v27;
              v93 = v27;
              cdp::StringFormat<unsigned __int64,char const *>(
                &v131,
                "ActivityId:%s|ActivityType:%s",
                (const char *)&v93,
                (const char *)&v130);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v133);
              v28 = *((_QWORD *)v21 + 60);
              v29 = *(void (__fastcall **)(__int64, struct _GUID *, std::_Ref_count_base **, _QWORD, int, __int128 *, const char *, _QWORD))(*(_QWORD *)v28 + 72LL);
              v30 = &v131;
              if ( *((_QWORD *)&v132 + 1) > 0xFu )
                v30 = (__int128 *)v131;
              *(_OWORD *)v133 = 0;
              *(__m128i *)v134 = si128;
              LOBYTE(v133[0]) = 0;
              std::string::string(&v135, "ActivityStore.HandleDeleteActivity");
              v29(v28, &v135, v133, 0, 1, v30, qword_1803986E0, 0);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v135);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v133);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v131);
              v31 = v90;
            }
            shared::ActivityData::~ActivityData((shared::ActivityData *)v143);
          }
          else
          {
            Log<>(2, "{\"text\":\"Cannot delete activity as it doesn't exist locally in the database. Ignoring.\"}");
          }
          std::unique_ptr<shared::InstanceManagerBase::InstanceHolder::Specific<ICDPUserCollection>>::~unique_ptr<shared::InstanceManagerBase::InstanceHolder::Specific<ICDPUserCollection>>(&v107);
        }
        else
        {
          Log<enum shared::ActivityStatus const &>();
        }
        goto LABEL_109;
      }
      if ( *v15 != 13 )
      {
        if ( *v15 == 15 )
        {
          v37 = v60 + 30;
          if ( *((_QWORD *)v60 + 18) > 0xFu )
            v37 = (_QWORD *)*v37;
          v96 = _o__strtoui64(v37, 0, 0);
          *(_QWORD *)&v130 = *((_QWORD *)v60 + 29);
          Log<char const *,unsigned __int64>(
            4,
            "{\"text\":\"Received a new Data Encryption Key with keyVersion=%llu and createdInCloudTime=%llu\"}",
            &v96,
            &v130);
          std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
            &v105,
            &v120);
          ActivityFeedClient::DataEncryptionKeysManager::GetDataEncryptionKey(&v105, &v103, v96);
          if ( v103 )
          {
            if ( (_QWORD)v130 )
            {
              Log<>(4, "{\"text\":\"Updating CreatedInCloud time for an existing Data Encryption Key\"}");
              ActivityFeedClient::DataEncryptionKeysManager::UpdateCreatedInCloudTime(
                (ActivityFeedClient::DataEncryptionKeysManager *)&v105,
                v96,
                v130);
              std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
                v122,
                &v120);
              ActivityFeedClient::MetadataManager::AddUpdateMetadata(
                (ActivityFeedClient::MetadataManager *)v122,
                "PendingFirstDEKUpload",
                "false");
              if ( v123 )
                std::_Ref_count_base::_Decref(v123);
            }
            else
            {
              v135 = *(struct _GUID *)v60;
              v38 = (const char *)cdp::CDP_UUID::ToString(&v135, &v131);
              Log<std::string const &>(
                3,
                "{\"text\":\"Skipping updating CreatedInCloudTime for DEK activity %s because the timestamp is invalid.\"}",
                v38);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v131);
            }
          }
          else
          {
            try
            {
              v92 = 0;
              Log<unsigned __int64 &>(4, "{\"text\":\"Saving DataEncryptionKey with keyVersion=%llu\"}", &v96);
              (*(void (__fastcall **)(_QWORD, __int128 *, _DWORD *))(**((_QWORD **)v21 + 64) + 40LL))(
                *((_QWORD *)v21 + 64),
                &v131,
                v60 + 86);
              v139 = v96;
              std::string::string(v140, &v131);
              v142 = v130;
              ActivityFeedClient::DataEncryptionKeysManager::AddDataEncryptionKey(
                (ActivityFeedClient::DataEncryptionKeysManager *)&v105,
                (const struct ActivityFeedClient::DataEncryptionKey *)&v139);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v140);
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v21 + 64) + 16LL))(*((_QWORD *)v21 + 64));
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v131);
            }
            catch ( ... )
            {
              v130 = *(_OWORD *)v93;
              v82 = cdp::CDP_UUID::ToString(&v130, &v131);
              LODWORD(v83) = GetCurrentThreadId();
              *(_QWORD *)&v130 = v83;
              v90 = 5532;
              cdp::CatchAllToHR<char const (&)[23],int,unsigned __int64,std::string>(&v92, v84, v85, &v90, &v130, v82);
            }
          }
          if ( v103 )
            ActivityFeedClient::DataEncryptionKey::`scalar deleting destructor'(v103, 1u);
          if ( v106 )
            std::_Ref_count_base::_Decref(v106);
        }
LABEL_69:
        if ( !cdp::ActivityManager::IsActivityDataValid(v21, (const struct shared::ActivityData *)v60) )
        {
          cdp::detail::StringFormat(
            &v131,
            "%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X",
            *v60,
            *((unsigned __int16 *)v60 + 2),
            *((unsigned __int16 *)v60 + 3),
            *((unsigned __int8 *)v60 + 8),
            *((unsigned __int8 *)v60 + 9),
            *((unsigned __int8 *)v60 + 10),
            *((unsigned __int8 *)v60 + 11),
            *((unsigned __int8 *)v60 + 12),
            *((unsigned __int8 *)v60 + 13),
            *((unsigned __int8 *)v60 + 14),
            *((unsigned __int8 *)v60 + 15));
          v91 = v90 | 6;
          v39 = (const char *)&v131;
          if ( *((_QWORD *)&v132 + 1) > 0xFu )
            v39 = (const char *)v131;
          cdp::detail::StringFormat(v133, "{\"text\":\"Ignoring. Received invalid activity from AFS. Id: %s\"}", v39);
          v31 = v90 | 0xE;
          v90 = v31;
          v91 = v31;
          shared::LogMessage(2, v133);
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v133);
LABEL_21:
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v131);
LABEL_109:
          if ( v100[1] )
            std::_Ref_count_base::_Decref(v100[1]);
          goto LABEL_111;
        }
        cdp::TransformActivityDataFromCloudToDbModel(&v109, v60, (char *)v21 + 1352);
        v128 = *(struct _GUID *)v60;
        *(_OWORD *)v133 = 0;
        *(_OWORD *)v134 = 0;
        v40 = v94[1];
        if ( v94[1] )
        {
          _InterlockedIncrement((volatile signed __int32 *)v94[1] + 2);
          v40 = v94[1];
        }
        v41 = v94[0];
        v133[0] = v94[0];
        v42 = v133[1];
        v133[1] = v40;
        if ( v42 )
        {
          std::_Ref_count_base::_Decref(v42);
          v41 = v133[0];
        }
        v43 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *, const char *))(*(_QWORD *)v41 + 144LL))(
                v41,
                v126,
                "SELECT [Id], [AppId], [PackageIdHash], [AppActivityId], [ActivityType], [ActivityStatus], [ParentActivit"
                "yId], [Tag], [Group], [MatchId], [LastModifiedTime], [ExpirationTime], [Payload], [Priority], [IsLocalOn"
                "ly], [PlatformDeviceId], [CreatedInCloud], [StartTime], [EndTime], [LastModifiedOnClient], [IsInUploadQu"
                "eue], [GroupAppActivityId], [ETag], [ClipboardPayload], [EnterpriseId], [UserActionState], [IsRead], [Or"
                "iginalPayload], [OriginalLastModifiedOnClient], [GroupItems], [DdsDeviceId] FROM [SmartLookup] WHERE [Id"
                "] = ? AND [ActivityStatus] <> 3 AND [ExpirationTime] > ? ");
        v44 = *(std::_Ref_count_base **)v43;
        v45 = *(std::_Ref_count_base **)(v43 + 8);
        *(_QWORD *)v43 = 0;
        *(_QWORD *)(v43 + 8) = 0;
        v134[0] = v44;
        v46 = v134[1];
        v134[1] = v45;
        if ( v46 )
          std::_Ref_count_base::_Decref(v46);
        if ( v127 )
          std::_Ref_count_base::_Decref(v127);
        v47 = v134[0];
        (*(void (__fastcall **)(std::_Ref_count_base *, __int64, __int64, struct _GUID *))(*(_QWORD *)v134[0] + 112LL))(
          v134[0],
          1,
          16,
          &v128);
        v48 = _time64(0);
        (*(void (__fastcall **)(std::_Ref_count_base *, __int64, __time64_t))(*(_QWORD *)v47 + 72LL))(v47, 2, v48);
        ActivityFeedClient::SmartActivityReader::RetrieveActivities(
          (unsigned int)v94,
          (unsigned int)&v135,
          v134[0],
          0,
          0);
        if ( (__int64)(*(_QWORD *)v135.Data4 - *(_QWORD *)&v135.Data1) >> 3 )
        {
          v49 = **(const struct ActivityFeedClient::ActivityData ***)&v135.Data1;
          **(_QWORD **)&v135.Data1 = 0;
          v50 = &v113;
          v51 = v31 | 0x10;
        }
        else
        {
          v50 = v117;
          v51 = v31 | 0x20;
          v49 = 0;
        }
        *v50 = 0;
        *(_QWORD *)&v130 = v49;
        v31 = v51 | 0x40;
        v90 = v31;
        v91 = v31;
        if ( (v31 & 0x20) != 0 )
        {
          v31 &= ~0x20u;
          v90 = v31;
          v91 = v31;
          std::unique_ptr<shared::InstanceManagerBase::InstanceHolder::Specific<ICDPUserCollection>>::~unique_ptr<shared::InstanceManagerBase::InstanceHolder::Specific<ICDPUserCollection>>(v117);
        }
        if ( (v31 & 0x10) != 0 )
        {
          v31 &= ~0x10u;
          v90 = v31;
          v91 = v31;
          if ( v113 )
            (**v113)(v113, 1);
        }
        std::vector<std::unique_ptr<ActivityFeedClient::ActivityData>>::_Tidy(&v135);
        ActivityFeedClient::AutoAddToCache::~AutoAddToCache((ActivityFeedClient::AutoAddToCache *)v133);
        if ( v49 )
        {
          if ( *((_QWORD *)v49 + 35) == *((_QWORD *)v109 + 35) )
          {
            v52 = *((unsigned __int8 *)v60 + 15);
            v53 = *((unsigned __int8 *)v60 + 14);
            v54 = *((unsigned __int8 *)v60 + 13);
            v55 = *((unsigned __int8 *)v60 + 12);
            v56 = *((unsigned __int8 *)v60 + 11);
            v57 = *((unsigned __int8 *)v60 + 10);
            v58 = *((unsigned __int8 *)v60 + 9);
            v59 = *((unsigned __int8 *)v60 + 8);
            v87 = *((unsigned __int16 *)v60 + 3);
            v60 = v93;
            cdp::detail::StringFormat(
              &v131,
              "%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X",
              *v93,
              *((unsigned __int16 *)v93 + 2),
              v87,
              v59,
              v58,
              v57,
              v56,
              v55,
              v54,
              v53,
              v52);
            v31 = v90 | 0x180;
            v90 = v31;
            v91 = v31;
            v61 = &v131;
            if ( *((_QWORD *)&v132 + 1) > 0xFu )
              v61 = (__int128 *)v131;
            *(_QWORD *)&v135.Data1 = v61;
            Log<unsigned __int64 &>(
              3,
              "{\"text\":\"Skipping activity %s because the last modified time matched the previously stored last modified time.\"}",
              (const char *)&v135);
            std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v131);
            (**(void (__fastcall ***)(const struct ActivityFeedClient::ActivityData *, __int64))v49)(v49, 1);
LABEL_107:
            if ( v110 )
              std::_Ref_count_base::_Decref(v110);
            goto LABEL_109;
          }
          cdp::ActivityManager::PopulatePackageIdTableIfRequired(
            v21,
            v49,
            v109,
            *((struct ICDPCrossPlatformAppId **)v60 + 5));
          ActivityFeedClient::ActivityWriter::AddOrUpdateActivity((ActivityFeedClient::ActivityWriter *)v100, v109);
        }
        else
        {
          cdp::ActivityManager::PopulatePackageIdTable(v21, v109, *((struct ICDPCrossPlatformAppId **)v60 + 5));
          if ( ActivityFeedClient::ActivityWriter::AddOrUpdateActivity((ActivityFeedClient::ActivityWriter *)v100, v109) )
          {
            if ( (unsigned __int8)cdp::ActivityManager::CanUploadTelemetryForActivityType((unsigned int)*v15) )
            {
              std::vector<shared::ActivityData>::emplace_back<shared::ActivityData const &>(&v136, v60);
              if ( *v15 == 10 )
              {
                v62 = *((_QWORD *)v60 + 27);
                if ( v62 )
                {
                  v133[0] = 0;
                  v133[1] = 0;
                  v134[0] = 0;
                  LODWORD(v134[1]) = 0;
                  BYTE4(v134[1]) = 0;
                  CDP_DATE_TIME::FromTimeTAsUtc((CDP_DATE_TIME *)v133, v62);
                  v63 = CDP_DATE_TIME::ToString(v133, &v139);
                  v135 = *(struct _GUID *)v60;
                  v64 = (_QWORD *)cdp::CDP_UUID::ToString(&v135, &v131);
                  if ( v64[3] > 0xFu )
                    v64 = (_QWORD *)*v64;
                  *(_QWORD *)&v135.Data1 = v64;
                  Log<char const *,std::string,std::string const &,std::string &>(
                    (_DWORD)v60 + 280,
                    v65,
                    (unsigned int)&v135,
                    v63,
                    (__int64)(v60 + 70),
                    (__int64)v21 + 1368);
                  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v131);
                  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v139);
                }
                else
                {
                  Log<>(1, "{\"text\":\"Expiration must be valid for a Clipboard activity (status=Active)\"}");
                }
              }
            }
          }
        }
        if ( *v15 == 13 || *((_BYTE *)v60 + 36) != 0xFF )
          v89 = 1;
        shared::ActivityData::ActivityData((shared::ActivityData *)v149, (const struct shared::ActivityData *)v60);
        v149[408] = 2;
        std::vector<shared::ActivityData>::emplace_back<shared::ActivityData>(v98, v149);
        shared::ActivityData::~ActivityData((shared::ActivityData *)v149);
        std::unique_ptr<shared::InstanceManagerBase::InstanceHolder::Specific<ICDPUserCollection>>::~unique_ptr<shared::InstanceManagerBase::InstanceHolder::Specific<ICDPUserCollection>>(&v130);
        goto LABEL_107;
      }
      v32 = *((_QWORD *)v60 + 5);
      if ( !v32 || !a4 || v88 )
        goto LABEL_69;
      v33 = (const char *)(*(__int64 (__fastcall **)(__int64, const char *))(*(_QWORD *)v32 + 24LL))(v32, "host");
      *(_QWORD *)&v130 = v33;
      if ( !v33 )
      {
        Log<>(2, "{\"text\":\"Skipping activity of type=UserNotificationFeed because host not specified\"}");
        goto LABEL_69;
      }
      if ( strcmp(v33, "dds.microsoft.com") )
      {
        v34 = (char *)("microsoft.projectrome.devicegraphchanges" - v33);
        do
        {
          v35 = (unsigned __int8)v34[(_QWORD)v33];
          v36 = *(unsigned __int8 *)v33 - v35;
          if ( v36 )
            break;
          ++v33;
        }
        while ( v35 );
        if ( v36 )
        {
          Log<unsigned __int64 &>(
            4,
            "{\"text\":\"Skipping activity of type=UserNotificationFeed with host=%s because it is not from DDS\"}",
            (const char *)&v130);
          goto LABEL_69;
        }
      }
      cdp::ActivityManager::HandleDeviceGraphChange(v21, (const struct shared::ActivityData *)v60);
      if ( v100[1] )
        std::_Ref_count_base::_Decref(v100[1]);
      v88 = 1;
LABEL_111:
      if ( v94[1] )
        std::_Ref_count_base::_Decref(v94[1]);
      _Mtx_unlock(v12);
      v60 += 132;
      v66 = v101;
      v9 = v97;
      v67 = (_DWORD *)v104;
    }
    if ( v102 )
    {
      v68 = std::vector<enum CDPActivityType>::vector<enum CDPActivityType>(v124, *v66, v66);
      v69 = (const char *)cdp::JsonSerializer<std::vector<enum CDPActivityType>>::Serialize(&v139, v68);
      Log<std::string const &>(
        3,
        "{\"text\":\"Allowing %s even though it is not in the known subscription types\"}",
        v69);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v139);
      std::vector<enum CDPActivityType>::_Tidy(v124);
    }
    if ( (_QWORD)v136 == *((_QWORD *)&v136 + 1) )
    {
      v70 = a4;
    }
    else
    {
      std::string::string(&v131, "ActivityStore.HandleActivity");
      v70 = a4;
      shared::UploadTelemetryForActivityBatch((_DWORD)v9 + 480, (unsigned int)&v131, (unsigned int)&v136, v71, v114, a4);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v131);
    }
    v113 = (void (__fastcall ***)(_QWORD, __int64))((char *)v9 + 296);
    std::_Mutex_base::lock((cdp::ActivityManager *)((char *)v9 + 296));
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v112 + 8LL))(v112, v119);
    _Mtx_unlock((cdp::ActivityManager *)((char *)v9 + 296));
    ActivityFeedClient::ConnectionLease::RestoreConnectionToPool((ActivityFeedClient::ConnectionLease *)v119);
    v73 = v98;
    if ( v70 )
    {
      v74 = (const struct shared::ActivityData *)*v98;
      v75 = (const struct shared::ActivityData *)v98[1];
      while ( v74 != v75 )
      {
        shared::ActivityData::ActivityData((shared::ActivityData *)v149, v74);
        cdp::ActivityManager::PublishActivityEvent(v9, (const struct shared::ActivityData *)v149);
        shared::ActivityData::~ActivityData((shared::ActivityData *)v149);
        v74 = (const struct shared::ActivityData *)((char *)v74 + 528);
      }
    }
    if ( *v73 != v73[1] )
    {
      v105 =  cdp::IActivityManagerObserver::`vcall'{160,{flat}};
      LODWORD(v106) = 0;
      HIDWORD(v106) = v125;
      shared::Observable<cdp::IActivityManagerWithTestHooks,cdp::IActivityManagerObserver>::RaiseEvent<void (cdp::IActivityManagerObserver::*)(std::vector<shared::ActivityData> const &),std::vector<shared::ActivityData> &>(
        v9,
        &v105,
        v73);
    }
    if ( v70 && v89 )
      cdp::ActivityManager::NotifyNewActivity(v72);
    v76 = v108;
    if ( *v99 > 0xFu )
      v76 = (_QWORD *)*v108;
    v99 = v76;
    Log<unsigned __int64 &>(3, "{\"text\":\"End HandleActivities(stableUserId = %s)\"}", (const char *)&v99);
    std::vector<shared::ActivityData>::_Tidy(&v136);
    std::_Tree_val<std::_Tree_simple_types<enum CDPActivityType>>::_Erase_tree<std::allocator<std::_Tree_node<enum CDPActivityType,void *>>>(
      &v101,
      &v101,
      *((_QWORD *)v101 + 1));
    operator delete(v101, (const struct std::nothrow_t *)0x20);
    ActivityFeedClient::ConnectionLease::~ConnectionLease((ActivityFeedClient::ConnectionLease *)v119);
  }
  catch ( ... )
  {
    LODWORD(v86) = GetCurrentThreadId();
    v99 = v86;
    v92 = 5691;
    cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
      (unsigned int)&v95,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\""
                    ":\"Failed to handle activities from sync\"}",
      (unsigned int)"..\\activitymanager.cpp",
      (unsigned int)&v92,
      (__int64)&v99);
  }
  if ( !a7 )
  {
    v77 = "full sync";
    if ( v70 )
      v77 = "delta sync";
    v131 = 0;
    v132 = 0;
    std::string::_Construct<1,char const *>(&v131, "Completed processing activities received during ", 48);
    std::operator+<char>(&v136, &v131, v77);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v131);
    v78 = *((_QWORD *)v9 + 60);
    v79 = *(void (__fastcall **)(__int64, std::_Ref_count_base **, int *, _QWORD, int, __int128 *, const char *, _QWORD, _QWORD))(*(_QWORD *)v78 + 64LL);
    v80 = &v136;
    if ( v138 > 0xF )
      v80 = (__int128 *)v136;
    v92 = 0;
    *(_OWORD *)v133 = 0;
    *(_OWORD *)v134 = 0;
    std::string::_Construct<1,char const *>(v133, "ActivityStore.HandleActivitiesFromSync", 38);
    v79(v78, v133, &v92, v95, 1, v80, qword_1803986E0, 0, 0);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v133);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v136);
  }
  return v73;
}

```

## disassembly

```asm
0x180043140  mov     r11, rsp
0x180043143  mov     [r11+20h], r9b
0x180043147  push    rbx
0x180043148  push    rsi
0x180043149  push    rdi
0x18004314a  push    r12
0x18004314c  push    r13
0x18004314e  push    r14
0x180043150  push    r15
0x180043152  sub     rsp, 720h
0x180043159  movaps  xmmword ptr [r11-48h], xmm6
0x18004315e  mov     rax, cs:__security_cookie
0x180043165  xor     rax, rsp
0x180043168  mov     [rsp+758h+var_58], rax
0x180043170  mov     rbx, r8
0x180043173  mov     r15, rdx
0x180043176  mov     [r11-6A8h], rdx
0x18004317d  mov     rsi, rcx
0x180043180  mov     [rsp+758h+var_6B0], rcx
0x180043188  mov     [rsp+758h+var_618], rcx
0x180043190  mov     [rsp+758h+var_610], rcx
0x180043198  mov     [r11-638h], rdx
0x18004319f  mov     rax, [rsp+758h+arg_20]
0x1800431a7  mov     [rsp+758h+var_630], rax
0x1800431af  mov     rax, [rsp+758h+arg_28]
0x1800431b7  mov     [rsp+758h+var_620], rax
0x1800431bf  xor     r13d, r13d
0x1800431c2  mov     [rsp+758h+var_6E0], r13d
0x1800431c7  mov     rax, [r8+8]
0x1800431cb  sub     rax, [r8]
0x1800431ce  sar     rax, 4
0x1800431d2  mov     rcx, 0F83E0F83E0F83E1h
0x1800431dc  imul    rax, rcx
0x1800431e0  mov     [r11-670h], rax
0x1800431e7  lea     rdi, [rsi+0E0h]
0x1800431ee  mov     [rsp+758h+var_650], rdi
0x1800431f6  lea     rax, [rdi+18h]
0x1800431fa  mov     [rsp+758h+var_6A0], rax
0x180043202  cmp     qword ptr [rax], 0Fh
0x180043206  jbe     short loc_18004320D
0x180043208  mov     rax, [rdi]
0x18004320b  jmp     short loc_180043210
0x18004320d  mov     rax, rdi
0x180043210  mov     [rsp+758h+var_678], rax
0x180043218  lea     r9, [rsp+758h+var_670]
0x180043220  lea     r8, [rsp+758h+var_678]
0x180043228  lea     rdx, aTextBeginHandl; "{\"text\":\"Begin HandleActivities (sta"...
0x18004322f  mov     ecx, 3
0x180043234  call    ??$Log@PEBD_K@@YAXW4CDPLogLevel@@PEBD$$QEAPEBD$$QEA_K@Z; Log<char const *,unsigned __int64>(CDPLogLevel,char const *,char const * &&,unsigned __int64 &&)
0x180043239  mov     [rsp+758h+var_6C0], r13d
0x180043241  mov     [rsp+758h+var_6E8], r13b
0x180043246  mov     [r15], r13
0x180043249  mov     [r15+8], r13
0x18004324d  mov     [r15+10h], r13
0x180043251  mov     r14d, 1
0x180043257  mov     [rsp+758h+var_6E4], r14d
0x18004325c  mov     [rsp+758h+var_6E0], r14d
0x180043261  lea     rdx, [rsp+758h+var_5F8]
0x180043269  mov     rcx, rsi
0x18004326c  call    ?GetDatabaseConnectionLease@ActivityManager@cdp@@AEAA?AVConnectionLease@ActivityFeedClient@@XZ; cdp::ActivityManager::GetDatabaseConnectionLease(void)
0x180043271  nop
0x180043272  mov     [rsp+758h+var_688], r13
0x18004327a  mov     [rsp+758h+var_680], r13
0x180043282  mov     [rsp+758h+var_6E7], r13b
0x180043287  lea     ecx, [r14+1Fh]
0x18004328b  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180043290  mov     [rax], rax
0x180043293  mov     [rax+8], rax
0x180043297  mov     [rax+10h], rax
0x18004329b  mov     word ptr [rax+18h], 101h
0x1800432a1  mov     [rsp+758h+var_688], rax
0x1800432a9  xorps   xmm0, xmm0
0x1800432ac  movdqu  [rsp+758h+var_4D8], xmm0
0x1800432b5  mov     [rsp+758h+var_4C8], r13
0x1800432bd  mov     r12, [rbx]
0x1800432c0  mov     rcx, [rbx+8]
0x1800432c4  mov     [rsp+758h+var_670], rcx
0x1800432cc  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x1800432d4  mov     [rsp+758h+var_6D8], r12
0x1800432dc  cmp     r12, rcx
0x1800432df  jz      loc_18004423E
0x1800432e5  lea     rdi, [rsi+128h]
0x1800432ec  mov     [rsp+758h+var_600], rdi
0x1800432f4  mov     rcx, rdi; this
0x1800432f7  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800432fc  nop
0x1800432fd  xorps   xmm0, xmm0
0x180043300  movdqu  xmmword ptr [rsp+758h+var_6D0], xmm0
0x180043309  mov     rax, [rsp+758h+var_5E8]
0x180043311  test    rax, rax
0x180043314  jz      short loc_180043322
0x180043316  lock inc dword ptr [rax+8]
0x18004331a  mov     rax, [rsp+758h+var_5E8]
0x180043322  mov     rcx, [rsp+758h+var_5F0]
0x18004332a  mov     [rsp+758h+var_6D0], rcx
0x180043332  mov     [rsp+758h+var_6D0+8], rax
0x18004333a  movdqu  xmmword ptr [rsp+758h+var_698], xmm0
0x180043343  test    rax, rax
0x180043346  jz      short loc_18004335C
0x180043348  lock inc dword ptr [rax+8]
0x18004334c  mov     rax, [rsp+758h+var_5E8]
0x180043354  mov     rcx, [rsp+758h+var_5F0]
0x18004335c  mov     [rsp+758h+var_698], rcx
0x180043364  mov     [rsp+758h+var_698+8], rax
0x18004336c  lea     r15, [r12+20h]
0x180043371  mov     esi, [r15]
0x180043374  mov     rbx, [rsp+758h+var_6B0]
0x18004337c  mov     rax, [rbx+268h]
0x180043383  cmp     [rbx+260h], rax
0x18004338a  jnz     short loc_180043407
0x18004338c  lea     rdx, aTextLoadingKno; "{\"text\":\"Loading known subscription "...
0x180043393  mov     ecx, 4
0x180043398  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18004339d  lea     rdx, [rsp+758h+var_578]
0x1800433a5  mov     rcx, rbx
0x1800433a8  call    ?GetDatabaseConnectionLease@ActivityManager@cdp@@AEAA?AVConnectionLease@ActivityFeedClient@@XZ; cdp::ActivityManager::GetDatabaseConnectionLease(void)
0x1800433ad  nop
0x1800433ae  lea     r8, [rsp+758h+var_578]
0x1800433b6  lea     rdx, [rsp+758h+var_4B8]
0x1800433be  call    ?LoadAFSSettingsFromDatabase@ActivityManager@cdp@@AEAA?AUStoredAFSSettings@2@AEBVConnectionLease@ActivityFeedClient@@@Z; cdp::ActivityManager::LoadAFSSettingsFromDatabase(ActivityFeedClient::ConnectionLease const &)
0x1800433c3  mov     rdx, rax
0x1800433c6  lea     rcx, [rbx+260h]
0x1800433cd  call    ??4?$vector@W4CDPActivityType@@V?$allocator@W4CDPActivityType@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<CDPActivityType>::operator=(std::vector<CDPActivityType> &&)
0x1800433d2  lea     rcx, [rsp+758h+var_4A0]; void *
0x1800433da  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800433df  lea     rcx, [rsp+758h+var_4B8]
0x1800433e7  call    ?_Tidy@?$vector@W4CDPActivityType@@V?$allocator@W4CDPActivityType@@@std@@@std@@AEAAXXZ; std::vector<CDPActivityType>::_Tidy(void)
0x1800433ec  lea     rcx, [rsp+758h+var_578]; this
0x1800433f4  call    ?RestoreConnectionToPool@ConnectionLease@ActivityFeedClient@@QEAAXXZ; ActivityFeedClient::ConnectionLease::RestoreConnectionToPool(void)
0x1800433f9  nop
0x1800433fa  lea     rcx, [rsp+758h+var_578]; this
0x180043402  call    ??1ConnectionLease@ActivityFeedClient@@QEAA@XZ; ActivityFeedClient::ConnectionLease::~ConnectionLease(void)
0x180043407  mov     qword ptr [rsp+758h+var_4F8.Data1], r15
0x18004340f  mov     rax, [rsp+758h+var_610]
0x180043417  mov     rcx, [rax+268h]
0x18004341e  mov     rax, [rbx+260h]
0x180043425  mov     ebx, 4
0x18004342a  cmp     rax, rcx
0x18004342d  jz      short loc_180043438
0x18004342f  cmp     [rax], esi
0x180043431  jz      short loc_180043450
0x180043433  add     rax, rbx
0x180043436  jmp     short loc_18004342A
0x180043438  mov     r8, r15
0x18004343b  lea     rdx, [rsp+758h+var_5B8]
0x180043443  lea     rcx, [rsp+758h+var_688]
0x18004344b  call    ??$_Emplace@W4CDPActivityType@@@?$_Tree@V?$_Tset_traits@W4CDPActivityType@@U?$less@W4CDPActivityType@@@std@@V?$allocator@W4CDPActivityType@@@3@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@W4CDPActivityType@@PEAX@std@@_N@1@$$QEAW4CDPActivityType@@@Z; std::_Tree<std::_Tset_traits<CDPActivityType,std::less<CDPActivityType>,std::allocator<CDPActivityType>,0>>::_Emplace<CDPActivityType>(CDPActivityType &&)
0x180043450  mov     rsi, [rsp+758h+var_6B0]
0x180043458  mov     rcx, rsi; this
0x18004345b  call    ?GetPolicies@ActivityManager@cdp@@AEAAAEAVActivityPolicies@shared@@XZ; cdp::ActivityManager::GetPolicies(void)
0x180043460  mov     r8d, 2
0x180043466  mov     rdx, r12
0x180043469  mov     rcx, rax
0x18004346c  call    ?CanPerformOperation@ActivityPolicies@shared@@AEBA_NAEBUActivityData@2@W4ActivityBlockedOperationFlags@2@@Z; shared::ActivityPolicies::CanPerformOperation(shared::ActivityData const &,shared::ActivityBlockedOperationFlags)
0x180043471  test    al, al
0x180043473  jnz     short loc_1800434D7
0x180043475  movups  xmm0, xmmword ptr [r12]
0x18004347a  movdqu  xmmword ptr [rsp+758h+var_4F8.Data1], xmm0
0x180043483  lea     rdx, [rsp+758h+var_538]
0x18004348b  lea     rcx, [rsp+758h+var_4F8]
0x180043493  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x180043498  nop
0x180043499  cmp     qword ptr [rax+18h], 0Fh
0x18004349e  jbe     short loc_1800434A3
0x1800434a0  mov     rax, [rax]
0x1800434a3  mov     qword ptr [rsp+758h+var_548], rax
0x1800434ab  lea     r8, [rsp+758h+var_548]
0x1800434b3  lea     rdx, aTextSkippingAc_1; "{\"text\":\"Skipping activity %s becaus"...
0x1800434ba  mov     ecx, 3
0x1800434bf  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x1800434c4  nop
0x1800434c5  lea     rcx, [rsp+758h+var_538]; void *
0x1800434cd  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800434d2  jmp     loc_1800441EB
0x1800434d7  lea     r8, [r12+25h]
0x1800434dc  movzx   ecx, byte ptr [r8]
0x1800434e0  test    ecx, ecx
0x1800434e2  jz      loc_180043831
0x1800434e8  sub     ecx, 1
0x1800434eb  jz      loc_180043831
0x1800434f1  cmp     ecx, 1
0x1800434f4  jz      short loc_180043500
0x1800434f6  call    ??$Log@AEBW4ActivityStatus@shared@@@@YAXW4CDPLogLevel@@PEBDAEBW4ActivityStatus@shared@@@Z; Log<shared::ActivityStatus const &>(CDPLogLevel,char const *,shared::ActivityStatus const &)
0x1800434fb  jmp     loc_1800441EB
0x180043500  movups  xmm0, xmmword ptr [r12]
0x180043505  movdqu  xmmword ptr [rsp+758h+var_4F8.Data1], xmm0
0x18004350e  lea     r8, [rsp+758h+var_4F8]
0x180043516  lea     rdx, [rsp+758h+var_658]
0x18004351e  lea     rcx, [rsp+758h+var_6D0]
0x180043526  call    ?GetActivityById@SmartActivityReader@ActivityFeedClient@@QEAA?AV?$unique_ptr@VActivityData@ActivityFeedClient@@U?$default_delete@VActivityData@ActivityFeedClient@@@std@@@std@@U_GUID@@@Z; ActivityFeedClient::SmartActivityReader::GetActivityById(_GUID)
0x18004352b  nop
0x18004352c  mov     rdx, [rsp+758h+var_658]
0x180043534  test    rdx, rdx
0x180043537  jz      loc_18004380D
0x18004353d  lea     rcx, [rsp+758h+var_478]
0x180043545  call    ?TransformActivityDataFromDbToCloudModel@cdp@@YA?AUActivityData@shared@@PEBV2ActivityFeedClient@@@Z; cdp::TransformActivityDataFromDbToCloudModel(ActivityFeedClient::ActivityData const *)
0x18004354a  nop
0x18004354b  mov     rax, [r12+0D8h]
0x180043553  mov     [rsp+758h+var_3A0], rax
0x18004355b  mov     rax, [r12+0E0h]
0x180043563  mov     [rsp+758h+var_398], rax
0x18004356b  mov     [rsp+758h+var_453], 2
0x180043573  mov     [rsp+758h+var_2E0], 2
0x18004357b  lea     rdx, [rsp+758h+var_478]
0x180043583  mov     rcx, [rsp+758h+var_6A8]
0x18004358b  call    ??$emplace_back@AEBUActivityData@shared@@@?$vector@UActivityData@shared@@V?$allocator@UActivityData@shared@@@std@@@std@@QEAAAEAUActivityData@shared@@AEBU23@@Z; std::vector<shared::ActivityData>::emplace_back<shared::ActivityData const &>(shared::ActivityData const &)
0x180043590  movups  xmm0, xmmword ptr [r12]
0x180043595  movdqu  xmmword ptr [rsp+758h+var_4F8.Data1], xmm0
0x18004359e  lea     rdx, [rsp+758h+var_538]
0x1800435a6  lea     rcx, [rsp+758h+var_4F8]
0x1800435ae  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x1800435b3  nop
0x1800435b4  cmp     qword ptr [rax+18h], 0Fh
0x1800435b9  jbe     short loc_1800435BE
0x1800435bb  mov     rax, [rax]
0x1800435be  mov     qword ptr [rsp+758h+var_548], rax
0x1800435c6  lea     r8, [rsp+758h+var_548]
0x1800435ce  lea     rdx, aTextTombstonin; "{\"text\":\"Tombstoning the activity %s"...
0x1800435d5  mov     ecx, ebx
0x1800435d7  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x1800435dc  nop
0x1800435dd  lea     rcx, [rsp+758h+var_538]; void *
0x1800435e5  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800435ea  movups  xmm0, xmmword ptr [r12]
0x1800435ef  movdqu  xmmword ptr [rsp+758h+var_4F8.Data1], xmm0
0x1800435f8  lea     rdx, [rsp+758h+var_4F8]
0x180043600  lea     rcx, [rsp+758h+var_698]
0x180043608  call    ?UpdateActivityStatus@ActivityWriter@ActivityFeedClient@@QEAAXU_GUID@@W4Activity_Status@2@@Z; ActivityFeedClient::ActivityWriter::UpdateActivityStatus(_GUID,ActivityFeedClient::Activity_Status)
0x18004360d  mov     eax, [rsp+758h+var_458]
0x180043614  add     eax, 0FFFFFFF5h
0x180043617  cmp     eax, 1
0x18004361a  ja      loc_1800436A5
0x180043620  movups  xmm0, xmmword ptr [r12]
0x180043625  movdqu  xmmword ptr [rsp+758h+var_4F8.Data1], xmm0
0x18004362e  lea     rdx, [rsp+758h+var_538]
0x180043636  lea     rcx, [rsp+758h+var_4F8]
0x18004363e  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x180043643  nop
0x180043644  cmp     qword ptr [rax+18h], 0Fh
0x180043649  jbe     short loc_18004364E
0x18004364b  mov     rax, [rax]
0x18004364e  mov     qword ptr [rsp+758h+var_548], rax
0x180043656  lea     r8, [rsp+758h+var_548]
0x18004365e  lea     rdx, aTextWritingDel; "{\"text\":\"Writing deletion time of CD"...
0x180043665  mov     ecx, ebx
0x180043667  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x18004366c  nop
0x18004366d  lea     rcx, [rsp+758h+var_538]; void *
0x180043675  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18004367a  movups  xmm0, xmmword ptr [r12]
0x18004367f  movdqu  xmmword ptr [rsp+758h+var_4F8.Data1], xmm0
0x180043688  mov     r8, [r12+100h]; __int64
0x180043690  lea     rdx, [rsp+758h+var_4F8]; struct _GUID
0x180043698  lea     rcx, [rsp+758h+var_698]; this
0x1800436a0  call    ?TombstoneActivity@ActivityWriter@ActivityFeedClient@@QEAAXU_GUID@@_J@Z; ActivityFeedClient::ActivityWriter::TombstoneActivity(_GUID,__int64)
0x1800436a5  mov     rax, [rsp+758h+var_658]
0x1800436ad  movzx   edx, byte ptr [rax+98h]
0x1800436b4  mov     ecx, edx
0x1800436b6  call    ?CanUploadTelemetryForActivityType@ActivityManager@cdp@@CA_NW4CDPActivityType@@@Z; cdp::ActivityManager::CanUploadTelemetryForActivityType(CDPActivityType)
0x1800436bb  test    al, al
0x1800436bd  jz      loc_1800437FE
0x1800436c3  mov     ecx, edx
0x1800436c5  call    ?ToString@EnumMapper@@YAPEBDW4CDPActivityType@@@Z; EnumMapper::ToString(CDPActivityType)
0x1800436ca  mov     qword ptr [rsp+758h+var_548], rax
0x1800436d2  movups  xmm0, xmmword ptr [r12]
0x1800436d7  movdqu  xmmword ptr [rsp+758h+var_4F8.Data1], xmm0
0x1800436e0  lea     rdx, [rsp+758h+var_518]
0x1800436e8  lea     rcx, [rsp+758h+var_4F8]
0x1800436f0  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x1800436f5  nop
0x1800436f6  cmp     qword ptr [rax+18h], 0Fh
0x1800436fb  jbe     short loc_180043700
0x1800436fd  mov     rax, [rax]
0x180043700  mov     [rsp+758h+var_6D8], rax
0x180043708  lea     r9, [rsp+758h+var_548]
0x180043710  lea     r8, [rsp+758h+var_6D8]
0x180043718  lea     rdx, aActivityidSAct_0; "ActivityId:%s|ActivityType:%s"
0x18004371f  lea     rcx, [rsp+758h+var_538]
0x180043727  call    ??$StringFormat@_KPEBD@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD$$QEA_K$$QEAPEBD@Z; cdp::StringFormat<unsigned __int64,char const *>(char const *,unsigned __int64 &&,char const * &&)
0x18004372c  nop
0x18004372d  lea     rcx, [rsp+758h+var_518]; void *
0x180043735  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18004373a  mov     rsi, [rsi+1E0h]
0x180043741  mov     rax, [rsi]
0x180043744  mov     r14, [rax+48h]
0x180043748  lea     rbx, [rsp+758h+var_538]
0x180043750  cmp     [rsp+758h+var_520], 0Fh
0x180043759  cmova   rbx, qword ptr [rsp+758h+var_538]
0x180043762  xorps   xmm0, xmm0
0x180043765  movups  xmmword ptr [rsp+758h+var_518], xmm0
0x18004376d  movdqu  xmmword ptr [rsp+758h+var_508], xmm6
0x180043776  mov     byte ptr [rsp+758h+var_518], r13b
0x18004377e  lea     rdx, ?ActivityStoreHandleDeleteActivity@MetricsIdentifier@shared@@2QBDB; "ActivityStore.HandleDeleteActivity"
0x180043785  lea     rcx, [rsp+758h+var_4F8]
0x18004378d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180043792  nop
0x180043793  mov     [rsp+758h+var_720], r13
0x180043798  lea     rax, qword_1803986E0
0x18004379f  mov     [rsp+758h+var_728], rax
0x1800437a4  mov     [rsp+758h+var_730], rbx
  ... truncated ...
```
