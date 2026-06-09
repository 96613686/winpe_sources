# cdp::ActivityManager::HandleActivityPublishResponse(long,std::shared_ptr<cdp::AFSPublishResponse> const &)

- ea: `0x1800738a0`
- end: `0x1800749b3`
- name: `?HandleActivityPublishResponse@ActivityManager@cdp@@AEAAXJAEBV?$shared_ptr@UAFSPublishResponse@cdp@@@std@@@Z`
- size: `4371`
- prototype: `__int64 __fastcall(cdp::ActivityManager *this)`
- caller_count: `1`
- callee_count: `54`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1802f35a0`

## callees

- `0x18000fac0`
- `0x180010ee0`
- `0x1800110f8`
- `0x180013d6c`
- `0x180013da0`
- `0x18001ee70`
- `0x1800206e0`
- `0x180021f30`
- `0x180030190`
- `0x180035df8`
- `0x1800360f8`
- `0x180036224`
- `0x1800370f0`
- `0x180042af8`
- `0x180042f74`
- `0x18004a444`
- `0x18004c834`
- `0x18004e170`
- `0x180054854`
- `0x180061db0`
- `0x180067954`
- `0x18006a280`
- `0x18006b714`
- `0x18006b7cc`
- `0x18006cda4`
- `0x180072488`
- `0x1800738a0`
- `0x1800749bc`
- `0x180074b50`
- `0x1800754b0`
- `0x1800755d0`
- `0x1800778f8`
- `0x18007e71c`
- `0x1800884ac`
- `0x18008dbc0`
- `0x18008e820`
- `0x1800a5b90`
- `0x1800cb350`
- `0x1800f0c90`
- `0x1800fb5b4`
- `0x180101834`
- `0x18010529c`
- `0x18014333c`
- `0x1801435b0`
- `0x18014d1f4`
- `0x180173c9c`
- `0x1801875dc`
- `0x1801f6fb0`
- `0x1802ed984`
- `0x1802eda7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x180074175`
- `api-ms-win-crt-private-l1-1-0!_o__difftime64` at `0x180074175`
- `msvcp_win!_Xtime_get_ticks` at `0x18007413e`
- `msvcp_win!_Xtime_get_ticks` at `0x18007413e`
- `msvcp_win!_Mtx_unlock` at `0x180073c13`
- `msvcp_win!_Mtx_unlock` at `0x1800744cf`
- `msvcp_win!_Mtx_unlock` at `0x180073c13`
- `msvcp_win!_Mtx_unlock` at `0x1800744cf`

## string_xrefs

- `0x1800742c5`: `CdsActivity.RemoveOperations`
- `0x180074424`: `CdsActivity.RemoveOperations`
- `0x18007444f`: `CDS Remove Operation Completed.`
- `0x1800742eb`: `Start Remove Operations for CDS Activity`
- `0x18007434b`: `DELETE FROM [ActivityOperation] WHERE [Id]=? AND [AppActivityId]=? AND [OperationOrder]=? AND [PublishProcessStatus]=?`
- `0x180073d68`: `{"text":"Activity %s was deleted from AFS. Tombstone it."}`
- `0x180073e83`: `{"text":"Received OnDeleteResult without a pending operation, ignoring."}`
- `0x180074519`: `{"text":"Raising Activity Sync Completion event!"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall cdp::ActivityManager::HandleActivityPublishResponse(cdp::ActivityManager *this, int a2, char ***a3)
{
  struct _Mtx_internal_imp_t *v5; // r13
  _QWORD *v6; // rax
  __int64 v7; // rcx
  ActivityFeedClient::ActivityOperation **v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r8
  struct ActivityFeedClient::ActivityOperation *v12; // rbx
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  ActivityFeedClient::ActivityOperation *v20; // rax
  __int64 v21; // rcx
  const struct ActivityFeedClient::ActivityData *v22; // r13
  std::_Ref_count_base *v23; // r12
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rcx
  unsigned int (__fastcall *v28)(_QWORD); // rdi
  unsigned int v29; // ebx
  __int64 v30; // rax
  const char *v31; // rax
  struct _Mtx_internal_imp_t *v32; // rcx
  __int64 v33; // rax
  const struct ActivityFeedClient::ActivityData *v34; // rdi
  std::_Ref_count_base *v35; // r13
  __int64 ticks; // rax
  char v37; // bl
  _QWORD *v38; // rax
  __int64 v39; // rdx
  __int64 v40; // rbx
  void (__fastcall *v41)(__int64, struct _GUID *, int *, _QWORD, int, const char *, const char *, _QWORD); // rdi
  __int64 v42; // r12
  _QWORD *v43; // rdi
  __int64 v44; // rbx
  __int64 v45; // rbx
  void (__fastcall *v46)(__int64, struct _GUID *, int *, _QWORD, int, const char *, const char *, _QWORD, _QWORD); // rdi
  char *v47; // r15
  char *v48; // rax
  __int64 *v49; // rbx
  std::_Ref_count_base **v50; // rax
  __int64 v51; // rbx
  __int64 v52; // rdi
  _QWORD *v53; // rbx
  _QWORD *v54; // r8
  std::_Ref_count_base **v55; // rcx
  std::_Ref_count_base **v56; // rax
  __int64 v57; // rbx
  void (__fastcall *v58)(__int64, _BYTE *, int *, _QWORD, int, const char *, const char *, _QWORD, _QWORD); // rdi
  const struct shared::ActivityData *v59; // rbx
  struct shared::ActivityData *v60; // rdi
  __int64 v61; // rdi
  __int64 v62; // r15
  int v63; // ebx
  __int64 *v64; // rax
  __int64 v65; // rcx
  unsigned int v66; // r13d
  __int64 v67; // rdi
  void (__fastcall *v68)(__int64, _BYTE *, int *, _QWORD, int, const char *, const char *, _QWORD, _QWORD); // rbx
  __int64 *v69; // rax
  char v70; // [rsp+50h] [rbp-408h]
  char v71; // [rsp+51h] [rbp-407h]
  char v72[2]; // [rsp+52h] [rbp-406h] BYREF
  int v73; // [rsp+54h] [rbp-404h] BYREF
  __int64 *v74; // [rsp+58h] [rbp-400h] BYREF
  __int64 (__fastcall *v75)(); // [rsp+60h] [rbp-3F8h] BYREF
  std::_Ref_count_base *v76; // [rsp+68h] [rbp-3F0h]
  int v77; // [rsp+70h] [rbp-3E8h] BYREF
  __int64 v78; // [rsp+78h] [rbp-3E0h] BYREF
  char v79[8]; // [rsp+80h] [rbp-3D8h] BYREF
  std::_Ref_count_base *v80; // [rsp+88h] [rbp-3D0h]
  struct ActivityFeedClient::ActivityOperation *v81; // [rsp+90h] [rbp-3C8h] BYREF
  ActivityFeedClient::ActivityOperation *v82; // [rsp+98h] [rbp-3C0h] BYREF
  int v83; // [rsp+A0h] [rbp-3B8h] BYREF
  __int64 v84; // [rsp+A8h] [rbp-3B0h] BYREF
  __int64 v85; // [rsp+B0h] [rbp-3A8h] BYREF
  __int64 v86; // [rsp+B8h] [rbp-3A0h] BYREF
  shared::ActivityData *v87[2]; // [rsp+C0h] [rbp-398h] BYREF
  shared::ActivityData *v88; // [rsp+D0h] [rbp-388h]
  char v89[8]; // [rsp+D8h] [rbp-380h] BYREF
  std::_Ref_count_base *v90; // [rsp+E0h] [rbp-378h]
  cdp::ActivityManager *v91; // [rsp+E8h] [rbp-370h]
  __int128 v92; // [rsp+F0h] [rbp-368h] BYREF
  __int64 v93; // [rsp+100h] [rbp-358h]
  struct shared::ActivityData *v94[2]; // [rsp+108h] [rbp-350h] BYREF
  __int64 v95; // [rsp+118h] [rbp-340h]
  __int64 v96; // [rsp+120h] [rbp-338h] BYREF
  std::_Ref_count_base *v97; // [rsp+128h] [rbp-330h]
  char *v98; // [rsp+130h] [rbp-328h]
  char v99[8]; // [rsp+138h] [rbp-320h] BYREF
  std::_Ref_count_base *v100; // [rsp+140h] [rbp-318h]
  char v101[8]; // [rsp+148h] [rbp-310h] BYREF
  std::_Ref_count_base *v102; // [rsp+150h] [rbp-308h]
  char v103[8]; // [rsp+158h] [rbp-300h] BYREF
  _BYTE v104[48]; // [rsp+160h] [rbp-2F8h] BYREF
  struct _GUID v105; // [rsp+190h] [rbp-2C8h] BYREF
  __int128 v106; // [rsp+1A0h] [rbp-2B8h]
  _BYTE v107[16]; // [rsp+1B0h] [rbp-2A8h] BYREF
  __int64 v108; // [rsp+1C0h] [rbp-298h]
  std::_Ref_count_base *v109[2]; // [rsp+1D0h] [rbp-288h] BYREF
  __int64 v110; // [rsp+1E0h] [rbp-278h]
  unsigned __int64 v111; // [rsp+1E8h] [rbp-270h]
  _OWORD v112[2]; // [rsp+1F0h] [rbp-268h] BYREF
  int v113; // [rsp+210h] [rbp-248h]
  char v114; // [rsp+215h] [rbp-243h]
  __int64 v115[22]; // [rsp+218h] [rbp-240h] BYREF
  __int64 v116; // [rsp+2C8h] [rbp-190h]
  __int64 v117; // [rsp+2D0h] [rbp-188h]
  __int64 v118; // [rsp+2D8h] [rbp-180h]
  __int64 v119; // [rsp+2F0h] [rbp-168h]
  char v120; // [rsp+388h] [rbp-D0h]

  try
  {
    v74 = (__int64 *)a3;
    v91 = this;
    v71 = 0;
    v70 = 0;
    v77 = 0;
    cdp::ActivityManager::HandleAFSRequestedActions(this, *a3);
    *(_OWORD *)v87 = 0;
    v88 = 0;
    *(_OWORD *)v94 = 0;
    v95 = 0;
    v92 = 0;
    v93 = 0;
    cdp::ActivityManager::GetDatabaseConnectionLease(this, v103);
    std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
      v79,
      v104);
    std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(
      v89,
      v104);
    v47 = (*a3)[11];
    v48 = (*a3)[12];
    v78 = (__int64)v48;
    while ( v47 != v48 )
    {
      v5 = (cdp::ActivityManager *)((char *)this + 296);
      v98 = (char *)this + 296;
      std::_Mutex_base::lock((cdp::ActivityManager *)((char *)this + 296));
      if ( *(_WORD *)v47 == 1 )
      {
        v105 = *(struct _GUID *)(v47 + 8);
        v6 = (_QWORD *)cdp::CDP_UUID::ToString(&v105, v107);
        if ( v6[3] > 0xFu )
          v6 = (_QWORD *)*v6;
        v86 = (__int64)v6;
        LOBYTE(v7) = v47[45];
        *(_QWORD *)&v105.Data1 = EnumMapper::ToString(v7);
        Log<char const *,unsigned __int64>(
          4,
          "{\"text\":\"%s operation for activity %s has failed. Discard the activity operation.\"}",
          (const char *)&v105,
          (const char *)&v86);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
        ActivityFeedClient::ActivityOperationManager::GetOperationsForOrder(v79, &v84, *((_QWORD *)v47 + 67));
        if ( v84 )
        {
          ActivityFeedClient::ActivityOperation::get_Activity(v84, &v96);
          cdp::TransformActivityDataFromDbToCloudModel(v112);
          v120 = 0;
          std::vector<shared::ActivityData>::emplace_back<shared::ActivityData const &>(&v92, v112);
          std::vector<shared::ActivityData>::emplace_back<shared::ActivityData const &>(v87, v112);
          ActivityFeedClient::ActivityOperationManager::RemoveOperationForOrder(
            (ActivityFeedClient::ActivityOperationManager *)v79,
            *((_QWORD *)v47 + 67));
          v70 = 1;
          shared::ActivityData::~ActivityData((shared::ActivityData *)v112);
          if ( v97 )
            std::_Ref_count_base::_Decref(v97);
        }
        else
        {
          Log<>(2, "{\"text\":\"Received publish result for activity with no pending operation\"}");
        }
        v8 = (ActivityFeedClient::ActivityOperation **)&v84;
        goto LABEL_37;
      }
      if ( *(_WORD *)v47 != 2 )
      {
        if ( *(_WORD *)v47 )
          goto LABEL_86;
        v105 = *(struct _GUID *)(v47 + 8);
        if ( v47[45] == 2 )
        {
          v13 = (_QWORD *)cdp::CDP_UUID::ToString(&v105, v107);
          if ( v13[3] > 0xFu )
            v13 = (_QWORD *)*v13;
          *(_QWORD *)&v105.Data1 = v13;
          Log<unsigned __int64 &>(
            3,
            "{\"text\":\"Received publish (deletion) result for activity %s\"}",
            (const char *)&v105);
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
          ActivityFeedClient::ActivityOperationManager::GetOperationsForOrder(v79, &v85, *((_QWORD *)v47 + 67));
          if ( v85 )
          {
            ActivityFeedClient::ActivityOperation::get_Activity(v85, v99);
            cdp::TransformActivityDataFromDbToCloudModel(v112);
            if ( v100 )
              std::_Ref_count_base::_Decref(v100);
            v114 = 2;
            v120 = 2;
            v105 = (struct _GUID)v112[0];
            v14 = (_QWORD *)cdp::CDP_UUID::ToString(&v105, v107);
            if ( v14[3] > 0xFu )
              v14 = (_QWORD *)*v14;
            *(_QWORD *)&v105.Data1 = v14;
            Log<unsigned __int64 &>(
              3,
              "{\"text\":\"Activity %s was deleted from AFS. Tombstone it.\"}",
              (const char *)&v105);
            std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
            v105 = (struct _GUID)v112[0];
            ActivityFeedClient::ActivityWriter::UpdateActivityStatus(v89, &v105);
            if ( (unsigned int)(v113 - 11) <= 1 )
            {
              v105 = (struct _GUID)v112[0];
              v15 = (_QWORD *)cdp::CDP_UUID::ToString(&v105, v107);
              if ( v15[3] > 0xFu )
                v15 = (_QWORD *)*v15;
              *(_QWORD *)&v105.Data1 = v15;
              Log<unsigned __int64 &>(
                4,
                "{\"text\":\"Writing deletion time of CDS activity %s to database\"}",
                (const char *)&v105);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
              v105 = (struct _GUID)v112[0];
              ActivityFeedClient::ActivityWriter::TombstoneActivity(
                (ActivityFeedClient::ActivityWriter *)v89,
                &v105,
                v119);
            }
            ActivityFeedClient::ActivityOperationManager::RemoveOperationForOrder(
              (ActivityFeedClient::ActivityOperationManager *)v79,
              *((_QWORD *)v47 + 67));
            shared::ActivityData::~ActivityData((shared::ActivityData *)v112);
          }
          else
          {
            Log<>(2, "{\"text\":\"Received OnDeleteResult without a pending operation, ignoring.\"}");
          }
          v8 = (ActivityFeedClient::ActivityOperation **)&v85;
LABEL_37:
          std::unique_ptr<ActivityFeedClient::ActivityOperation>::~unique_ptr<ActivityFeedClient::ActivityOperation>(v8);
LABEL_86:
          v32 = v5;
        }
        else
        {
          if ( (unsigned __int8)v47[45] >= 2u )
          {
            v16 = (_QWORD *)cdp::CDP_UUID::ToString(&v105, v107);
            if ( v16[3] > 0xFu )
              v16 = (_QWORD *)*v16;
            *(_QWORD *)&v105.Data1 = v16;
            Log<char const *,enum shared::ActivityStatus const &>(v18, v17, &v105, v47 + 45);
            std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
            goto LABEL_86;
          }
          v19 = (_QWORD *)cdp::CDP_UUID::ToString(&v105, v107);
          if ( v19[3] > 0xFu )
            v19 = (_QWORD *)*v19;
          *(_QWORD *)&v105.Data1 = v19;
          Log<unsigned __int64 &>(3, "{\"text\":\"Received publish result for activity %s\"}", (const char *)&v105);
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
          ActivityFeedClient::ActivityOperationManager::GetOperationsForOrder(v79, &v82, *((_QWORD *)v47 + 67));
          v20 = v82;
          if ( !v82 )
          {
            Log<>(2, "{\"text\":\"Received publish result for activity with no pending operation\"}");
            v8 = &v82;
            goto LABEL_37;
          }
          v21 = *((_QWORD *)v82 + 2);
          if ( v21 )
            _InterlockedAdd((volatile signed __int32 *)(v21 + 8), 1u);
          v22 = (const struct ActivityFeedClient::ActivityData *)*((_QWORD *)v20 + 1);
          v75 = (__int64 (__fastcall *)())v22;
          v23 = (std::_Ref_count_base *)*((_QWORD *)v20 + 2);
          v76 = v23;
          cdp::TransformActivityDataFromDbToCloudModel(v112);
          v114 = v47[45];
          v24 = v116;
          if ( *((_QWORD *)v47 + 28) )
            v24 = *((_QWORD *)v47 + 28);
          v116 = v24;
          v25 = v117;
          if ( *((_QWORD *)v47 + 29) )
            v25 = *((_QWORD *)v47 + 29);
          v117 = v25;
          v26 = v118;
          if ( *((_QWORD *)v47 + 30) )
            v26 = *((_QWORD *)v47 + 30);
          v118 = v26;
          v27 = *((_QWORD *)v47 + 6);
          *(_QWORD *)&v105.Data1 = v27;
          if ( v27 )
          {
            v28 = *(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v27 + 56LL);
            v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v115[0] + 56LL))(v115[0]);
            if ( v28(*(_QWORD *)&v105.Data1) > v29 )
            {
              v30 = shared::CloneCrossPlatformAppId(v101, *((_QWORD *)v47 + 6));
              std::shared_ptr<cdp::legacy::ITransportMessage>::operator=<cdp::legacy::PowerOffMessage,0>(v115, v30);
              if ( v102 )
                std::_Ref_count_base::_Decref(v102);
              cdp::ActivityManager::PopulatePackageIdTable(this, v22, *((struct ICDPCrossPlatformAppId **)v47 + 6));
            }
          }
          if ( cdp::ActivityManager::IsActivityDataValid(this, (const struct shared::ActivityData *)v112) )
          {
            v33 = cdp::TransformActivityDataFromCloudToDbModel(v109, v112, (char *)this + 1352);
            v34 = *(const struct ActivityFeedClient::ActivityData **)v33;
            v35 = *(std::_Ref_count_base **)(v33 + 8);
            *(_QWORD *)v33 = 0;
            *(_QWORD *)(v33 + 8) = 0;
            v75 = (__int64 (__fastcall *)())v34;
            v76 = v35;
            if ( v23 )
              std::_Ref_count_base::_Decref(v23);
            if ( v109[1] )
              std::_Ref_count_base::_Decref(v109[1]);
            ticks = _Xtime_get_ticks();
            v37 = 1;
            if ( _o__difftime64(*((_QWORD *)v47 + 28), ticks / 10000000) <= 0.0 )
            {
              v105 = *(struct _GUID *)(v47 + 8);
              v38 = (_QWORD *)cdp::CDP_UUID::ToString(&v105, v107);
              if ( v38[3] > 0xFu )
                v38 = (_QWORD *)*v38;
              *(_QWORD *)&v105.Data1 = v38;
              Log<unsigned __int64 &>(3, "{\"text\":\"%s activity is force expired by AFS\"}", (const char *)&v105);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
              v37 = 0;
            }
            ActivityFeedClient::ActivityWriter::AddOrUpdateActivity((ActivityFeedClient::ActivityWriter *)v89, v34);
            v120 = 2;
            if ( v87[1] == v88 )
            {
              std::vector<shared::ActivityData>::_Emplace_reallocate<shared::ActivityData const &>(v87, v87[1], v112);
            }
            else
            {
              shared::ActivityData::ActivityData(v87[1], (const struct shared::ActivityData *)v112);
              v87[1] = (shared::ActivityData *)((char *)v87[1] + 528);
            }
            if ( v37 )
              std::vector<shared::ActivityData>::emplace_back<shared::ActivityData const &>(v94, v112);
            LOBYTE(v39) = 1;
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDataStoreConcurrentPublish>::ReportUsage(
              `wil::Feature<__WilFeatureTraits_Feature_CloudDataStoreConcurrentPublish>::GetImpl'::`2'::impl,
              v39);
            if ( (unsigned int)(*((_DWORD *)v47 + 10) - 11) <= 1 )
            {
              v40 = *((_QWORD *)this + 60);
              v41 = *(void (__fastcall **)(__int64, struct _GUID *, int *, _QWORD, int, const char *, const char *, _QWORD))(*(_QWORD *)v40 + 48LL);
              v83 = 0;
              v105 = 0;
              v106 = 0;
              std::string::_Construct<1,char const *>(&v105, "CdsActivity.RemoveOperations", 28);
              v41(v40, &v105, &v83, 0, 1, "Start Remove Operations for CDS Activity", qword_1803986E0, 0);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v105);
              v42 = *((_QWORD *)v47 + 67);
              v43 = v47 + 64;
              if ( *((_QWORD *)v47 + 11) > 0xFu )
                v43 = (_QWORD *)*v43;
              v105 = *(struct _GUID *)(v47 + 8);
              ActivityFeedClient::AutoAddToCache::AutoAddToCache(
                v107,
                v79,
                "DELETE FROM [ActivityOperation] WHERE [Id]=? AND [AppActivityId]=? AND [OperationOrder]=? AND [PublishProcessStatus]=?");
              v44 = v108;
              (*(void (__fastcall **)(__int64, __int64, __int64, struct _GUID *))(*(_QWORD *)v108 + 112LL))(
                v108,
                1,
                16,
                &v105);
              (*(void (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v44 + 104LL))(v44, 2, v43);
              (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v44 + 72LL))(v44, 3, v42);
              (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v44 + 80LL))(v44, 4, 2);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v108 + 48LL))(v108);
              ActivityFeedClient::AutoAddToCache::~AutoAddToCache((ActivityFeedClient::AutoAddToCache *)v107);
              v45 = *((_QWORD *)this + 60);
              v46 = *(void (__fastcall **)(__int64, struct _GUID *, int *, _QWORD, int, const char *, const char *, _QWORD, _QWORD))(*(_QWORD *)v45 + 64LL);
              v73 = 0;
              v105 = 0;
              v106 = 0;
              std::string::_Construct<1,char const *>(&v105, "CdsActivity.RemoveOperations", 28);
              v46(v45, &v105, &v73, 0, 1, "CDS Remove Operation Completed.", qword_1803986E0, 0, 0);
              std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v105);
            }
            else
            {
              ActivityFeedClient::ActivityOperationManager::RemoveOperationForOrder(
                (ActivityFeedClient::ActivityOperationManager *)v79,
                *((_QWORD *)v47 + 67));
            }
            shared::ActivityData::~ActivityData((shared::ActivityData *)v112);
            if ( v35 )
              std::_Ref_count_base::_Decref(v35);
            if ( v82 )
              ActivityFeedClient::ActivityOperation::`vector deleting destructor'(v82, 1u);
            v5 = (cdp::ActivityManager *)((char *)this + 296);
            goto LABEL_86;
          }
          v105 = *(struct _GUID *)(v47 + 8);
          v31 = (const char *)cdp::CDP_UUID::ToString(&v105, v107);
          Log<std::string const &>(
            2,
            "{\"text\":\"Ignoring. Received publish result for activity %s, with invalid data\"}",
            v31);
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
          shared::ActivityData::~ActivityData((shared::ActivityData *)v112);
          if ( v23 )
            std::_Ref_count_base::_Decref(v23);
          std::unique_ptr<ActivityFeedClient::ActivityOperation>::~unique_ptr<ActivityFeedClient::ActivityOperation>(&v82);
          v32 = (cdp::ActivityManager *)((char *)this + 296);
        }
        _Mtx_unlock(v32);
        goto LABEL_88;
      }
      v105 = *(struct _GUID *)(v47 + 8);
      v9 = (_QWORD *)cdp::CDP_UUID::ToString(&v105, v107);
      if ( v9[3] > 0xFu )
        v9 = (_QWORD *)*v9;
      *(_QWORD *)&v105.Data1 = v9;
      LOBYTE(v10) = v47[45];
      v86 = EnumMapper::ToString(v10);
      Log<char const *,unsigned __int64>(
        4,
        "{\"text\":\"Retry %s operation for activity %s\"}",
        (const char *)&v86,
        (const char *)&v105);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
      v71 = 1;
      ActivityFeedClient::ActivityOperationManager::GetOperationsForOrder(v79, &v81, *((_QWORD *)v47 + 67));
      v12 = v81;
      if ( !v81 )
      {
        Log<>(2, "{\"text\":\"Received throttled result for activity with no pending operation\"}");
        v8 = &v81;
        goto LABEL_37;
      }
      if ( v47[45] )
      {
        if ( v47[45] == 1 )
          LOBYTE(v11) = 5;
        else
          LOBYTE(v11) = v47[45] == 2;
      }
      else
      {
        LOBYTE(v11) = 4;
      }
      *((_QWORD *)v12 + 15) = cdp::ActivityThrottling::GetReleaseTimeForActivityOperation(
                                (char *)this + 1800,
                                v47 + 8,
                                v11);
      ActivityFeedClient::ActivityOperationManager::UpdateOperation(
        (ActivityFeedClient::ActivityOperationManager *)v79,
        v81);
      std::unique_ptr<ActivityFeedClient::ActivityOperation>::~unique_ptr<ActivityFeedClient::ActivityOperation>(&v81);
      _Mtx_unlock((cdp::ActivityManager *)((char *)this + 296));
LABEL_88:
      v47 += 544;
      v48 = (char *)v78;
    }
    if ( !(*(__int64 (__fastcall **)(cdp::ActivityManager *))(*(_QWORD *)this + 448LL))(this) )
    {
      Log<>(3, "{\"text\":\"Raising Activity Sync Completion event!\"}");
      v75 =  cdp::CommonFactory::`vcall'{152,{flat}};
      LODWORD(v76) = 0;
      HIDWORD(v76) = HIDWORD(v109[1]);
      shared::Observable<cdp::IActivityManagerWithTestHooks,cdp::IActivityManagerObserver>::RaiseEvent<void (cdp::IActivityManagerObserver::*)(void),>(
        this,
        &v75);
    }
    ActivityFeedClient::ConnectionLease::RestoreConnectionToPool((ActivityFeedClient::ConnectionLease *)v103);
    if ( v90 )
      std::_Ref_count_base::_Decref(v90);
    if ( v80 )
      std::_Ref_count_base::_Decref(v80);
    ActivityFeedClient::ConnectionLease::~ConnectionLease((ActivityFeedClient::ConnectionLease *)v103);
    v49 = v74;
    if ( *(_QWORD *)(*v74 + 72) && *(_QWORD *)(*v74 + 40) )
    {
      (*(void (__fastcall **)(cdp::ActivityManager *, std::_Ref_count_base **))(*(_QWORD *)this + 400LL))(this, v109);
      v50 = v109;
      if ( v111 > 0xF )
        v50 = (std::_Ref_count_base **)v109[0];
      v74 = (__int64 *)v50;
      Log<unsigned __int64 &>(
        4,
        "{\"text\":\"HandleActivityPublishResponse : AFC current etag %s.\"}",
        (const char *)&v74);
      v51 = *v49;
      v52 = v51 + 24;
      if ( (unsigned __int8)std::operator!=<char>(v109, v51 + 24) )
      {
        v53 = (_QWORD *)(v51 + 56);
        if ( v53[3] <= 0xFu )
          v54 = v53;
        else
          v54 = (_QWORD *)*v53;
        v55 = v109;
        if ( v111 > 0xF )
          v55 = (std::_Ref_count_base **)v109[0];
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v55, v110, v54, v53[2]) )
        {
          (*(void (__fastcall **)(cdp::ActivityManager *, __int64))(*(_QWORD *)this + 496LL))(this, v52);
        }
        else
        {
          if ( v53[3] > 0xFu )
            v53 = (_QWORD *)*v53;
          v74 = v53;
          v56 = v109;
          if ( v111 > 0xF )
            v56 = (std::_Ref_count_base **)v109[0];
          v78 = (__int64)v56;
          Log<char const *,unsigned __int64>(
            3,
            "{\"text\":\"ETag mismatch. Current = %s. Base = %s\"}",
            (const char *)&v78,
            (const char *)&v74);
          cdp::ActivityManager::EnqueueSyncActivitiesRequest(this, 0);
          v57 = *((_QWORD *)this + 60);
          v58 = *(void (__fastcall **)(__int64, _BYTE *, int *, _QWORD, int, const char *, const char *, _QWORD, _QWORD))(*(_QWORD *)v57 + 64LL);
          v73 = 0;
          std::string::string(v107, "ActivityStore.DeltaSync");
          v58(
            v57,
            v107,
            &v73,
            0,
            1,
            "ETag mismatch while handling publish response. Scheduling delta sync.",
            qword_1803986E0,
            0,
            0);
          std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
        }
      }
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v109);
    }
    v59 = v94[0];
    v60 = v94[1];
    while ( v59 != v60 )
    {
      cdp::ActivityManager::PublishActivityEvent(this, v59);
      v59 = (const struct shared::ActivityData *)((char *)v59 + 528);
    }
    if ( v87[0] != v87[1] )
    {
      v75 =  cdp::IActivityManagerObserver::`vcall'{160,{flat}};
      LODWORD(v76) = 0;
      HIDWORD(v76) = HIDWORD(v109[1]);
      shared::Observable<cdp::IActivityManagerWithTestHooks,cdp::IActivityManagerObserver>::RaiseEvent<void (cdp::IActivityManagerObserver::*)(std::vector<shared::ActivityData> const &),std::vector<shared::ActivityData> &>(
        this,
        &v75,
        v87);
    }
    v62 = *((_QWORD *)&v92 + 1);
    v61 = v92;
    v63 = HIDWORD(v109[1]);
    while ( v61 != v62 )
    {
      *(_OWORD *)v109 = *(_OWORD *)v61;
      v64 = (__int64 *)cdp::CDP_UUID::ToString(v109, v107);
      if ( (unsigned __int64)v64[3] > 0xF )
        v64 = (__int64 *)*v64;
      v74 = v64;
      LOBYTE(v65) = *(_BYTE *)(v61 + 37);
      v78 = EnumMapper::ToString(v65);
      Log<char const *,unsigned __int64>(
        4,
        "{\"text\":\"Raising events back to the caller for failed %s operation for activity %s\"}",
        (const char *)&v78,
        (const char *)&v74);
      std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
      v72[0] = 0;
      v75 =  shared::SharedCommonFactory::`vcall'{56,{flat}};
      LODWORD(v76) = 0;
      HIDWORD(v76) = v63;
      shared::Observable<cdp::IActivityManagerWithTestHooks,cdp::IActivityManagerObserver>::RaiseEventAsync<void (cdp::IActivityManagerObserver::*)(shared::ActivityData const &,bool),shared::ActivityData const &,bool>(
        this,
        &v75,
        v61,
        v72);
      v61 += 528;
    }
    std::vector<shared::ActivityData>::_Tidy(&v92);
    std::vector<shared::ActivityData>::_Tidy(v94);
    std::vector<shared::ActivityData>::_Tidy(v87);
  }
  catch ( ... )
  {
    LODWORD(v69) = GetCurrentThreadId();
    v74 = v69;
    v73 = 3847;
    cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
      (unsigned int)&v77,
      (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\""
                    ":\"Failed to handle AFS Publish response\"}",
      (unsigned int)"..\\activitymanager.cpp",
      (unsigned int)&v73,
      (__int64)&v74);
  }
  v66 = v77;
  if ( v77 >= 0 )
  {
    if ( a2 >= 0 )
    {
      *((_QWORD *)this + 186) = 0x8000000000000000uLL;
      *((_QWORD *)this + 185) = 0;
      goto LABEL_128;
    }
  }
  else
  {
    v67 = *((_QWORD *)this + 60);
    v68 = *(void (__fastcall **)(__int64, _BYTE *, int *, _QWORD, int, const char *, const char *, _QWORD, _QWORD))(*(_QWORD *)v67 + 64LL);
    v73 = 0;
    std::string::string(v107, "ActivityStore.HandleActivityPublishResponse");
    v68(v67, v107, &v73, v66, 1, "Failed to handle & store activity publish response", qword_1803986E0, 0, 0);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v107);
  }
  cdp::AfcWorkBackoff::OnFailure((cdp::ActivityManager *)((char *)this + 1448));
LABEL_128:
  cdp::ActivityManager::CompleteAfsRequestCallback(this);
  if ( v70 || v71 )
    cdp::ActivityManager::ScheduleCheckForWork(this);
}

```

## disassembly

```asm
0x1800738a0  mov     rax, rsp
0x1800738a3  mov     [rax+10h], edx
0x1800738a6  push    rbx
0x1800738a7  push    rsi
0x1800738a8  push    rdi
0x1800738a9  push    r12
0x1800738ab  push    r13
0x1800738ad  push    r14
0x1800738af  push    r15
0x1800738b1  sub     rsp, 420h
0x1800738b8  movaps  xmmword ptr [rax-48h], xmm6
0x1800738bc  mov     rax, cs:__security_cookie
0x1800738c3  xor     rax, rsp
0x1800738c6  mov     [rsp+458h+var_58], rax
0x1800738ce  mov     rbx, r8
0x1800738d1  mov     [rsp+458h+var_400], rbx
0x1800738d6  mov     r14, rcx
0x1800738d9  mov     [rsp+458h+var_370], rcx
0x1800738e1  xor     esi, esi
0x1800738e3  mov     [rsp+458h+var_407], sil
0x1800738e8  mov     [rsp+458h+var_408], sil
0x1800738ed  mov     [rsp+458h+var_3E8], esi
0x1800738f1  mov     rdx, [r8]
0x1800738f4  call    ?HandleAFSRequestedActions@ActivityManager@cdp@@AEAAXAEBV?$vector@UAFSRequestedAction@cdp@@V?$allocator@UAFSRequestedAction@cdp@@@std@@@std@@@Z; cdp::ActivityManager::HandleAFSRequestedActions(std::vector<cdp::AFSRequestedAction> const &)
0x1800738f9  xorps   xmm0, xmm0
0x1800738fc  movdqu  xmmword ptr [rsp+458h+var_398], xmm0
0x180073905  mov     [rsp+458h+var_388], rsi
0x18007390d  movdqu  xmmword ptr [rsp+458h+var_350], xmm0
0x180073916  mov     [rsp+458h+var_340], rsi
0x18007391e  movdqu  [rsp+458h+var_368], xmm0
0x180073927  mov     [rsp+458h+var_358], rsi
0x18007392f  lea     rdx, [rsp+458h+var_300]
0x180073937  mov     rcx, r14
0x18007393a  call    ?GetDatabaseConnectionLease@ActivityManager@cdp@@AEAA?AVConnectionLease@ActivityFeedClient@@XZ; cdp::ActivityManager::GetDatabaseConnectionLease(void)
0x18007393f  nop
0x180073940  lea     rdx, [rsp+458h+var_2F8]
0x180073948  lea     rcx, [rsp+458h+var_3D8]
0x180073950  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x180073955  nop
0x180073956  lea     rdx, [rsp+458h+var_2F8]
0x18007395e  lea     rcx, [rsp+458h+var_380]
0x180073966  call    ??$?0VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@$0A@@?$shared_ptr@VICommandServiceInternalRequestObserver@cdp@@@std@@QEAA@AEBV?$shared_ptr@VCommandServiceInternalRequestObserver@CommandServiceClient@cdp@@@1@@Z; std::shared_ptr<cdp::ICommandServiceInternalRequestObserver>::shared_ptr<cdp::ICommandServiceInternalRequestObserver>(std::shared_ptr<cdp::CommandServiceClient::CommandServiceInternalRequestObserver> const &)
0x18007396b  nop
0x18007396c  mov     rax, [rbx]
0x18007396f  mov     r15, [rax+58h]
0x180073973  mov     rax, [rax+60h]
0x180073977  mov     [rsp+458h+var_3E0], rax
0x18007397c  lea     edi, [rsi+2]
0x18007397f  xorps   xmm6, xmm6
0x180073982  mov     r12d, 1
0x180073988  cmp     r15, rax
0x18007398b  jz      loc_180074502
0x180073991  lea     r13, [r14+128h]
0x180073998  mov     [rsp+458h+var_328], r13
0x1800739a0  mov     rcx, r13; this
0x1800739a3  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800739a8  nop
0x1800739a9  cmp     [r15], r12w
0x1800739ad  jnz     loc_180073B04
0x1800739b3  movups  xmm0, xmmword ptr [r15+8]
0x1800739b8  movdqu  xmmword ptr [rsp+458h+var_2C8.Data1], xmm0
0x1800739c1  lea     rdx, [rsp+458h+var_2A8]
0x1800739c9  lea     rcx, [rsp+458h+var_2C8]
0x1800739d1  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x1800739d6  nop
0x1800739d7  cmp     qword ptr [rax+18h], 0Fh
0x1800739dc  jbe     short loc_1800739E1
0x1800739de  mov     rax, [rax]
0x1800739e1  mov     [rsp+458h+var_3A0], rax
0x1800739e9  mov     cl, [r15+2Dh]
0x1800739ed  call    ?ToString@EnumMapper@@YAPEBDW4ActivityStatus@shared@@@Z; EnumMapper::ToString(shared::ActivityStatus)
0x1800739f2  mov     qword ptr [rsp+458h+var_2C8.Data1], rax
0x1800739fa  lea     r9, [rsp+458h+var_3A0]
0x180073a02  lea     r8, [rsp+458h+var_2C8]
0x180073a0a  lea     rdx, aTextSOperation_0; "{\"text\":\"%s operation for activity %"...
0x180073a11  mov     ecx, 4
0x180073a16  call    ??$Log@PEBD_K@@YAXW4CDPLogLevel@@PEBD$$QEAPEBD$$QEA_K@Z; Log<char const *,unsigned __int64>(CDPLogLevel,char const *,char const * &&,unsigned __int64 &&)
0x180073a1b  nop
0x180073a1c  lea     rcx, [rsp+458h+var_2A8]; void *
0x180073a24  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180073a29  mov     r8, [r15+218h]
0x180073a30  lea     rdx, [rsp+458h+var_3B0]
0x180073a38  lea     rcx, [rsp+458h+var_3D8]
0x180073a40  call    ?GetOperationsForOrder@ActivityOperationManager@ActivityFeedClient@@QEAA?AV?$unique_ptr@VActivityOperation@ActivityFeedClient@@U?$default_delete@VActivityOperation@ActivityFeedClient@@@std@@@std@@_K@Z; ActivityFeedClient::ActivityOperationManager::GetOperationsForOrder(unsigned __int64)
0x180073a45  nop
0x180073a46  mov     rcx, [rsp+458h+var_3B0]
0x180073a4e  test    rcx, rcx
0x180073a51  jz      loc_180073AF4
0x180073a57  lea     rdx, [rsp+458h+var_338]
0x180073a5f  call    ?get_Activity@ActivityOperation@ActivityFeedClient@@QEBA?AV?$shared_ptr@VActivityData@ActivityFeedClient@@@std@@XZ; ActivityFeedClient::ActivityOperation::get_Activity(void)
0x180073a64  nop
0x180073a65  mov     rdx, [rsp+458h+var_338]
0x180073a6d  lea     rcx, [rsp+458h+var_268]
0x180073a75  call    ?TransformActivityDataFromDbToCloudModel@cdp@@YA?AUActivityData@shared@@PEBV2ActivityFeedClient@@@Z; cdp::TransformActivityDataFromDbToCloudModel(ActivityFeedClient::ActivityData const *)
0x180073a7a  nop
0x180073a7b  mov     [rsp+458h+var_D0], sil
0x180073a83  lea     rdx, [rsp+458h+var_268]
0x180073a8b  lea     rcx, [rsp+458h+var_368]
0x180073a93  call    ??$emplace_back@AEBUActivityData@shared@@@?$vector@UActivityData@shared@@V?$allocator@UActivityData@shared@@@std@@@std@@QEAAAEAUActivityData@shared@@AEBU23@@Z; std::vector<shared::ActivityData>::emplace_back<shared::ActivityData const &>(shared::ActivityData const &)
0x180073a98  lea     rdx, [rsp+458h+var_268]
0x180073aa0  lea     rcx, [rsp+458h+var_398]
0x180073aa8  call    ??$emplace_back@AEBUActivityData@shared@@@?$vector@UActivityData@shared@@V?$allocator@UActivityData@shared@@@std@@@std@@QEAAAEAUActivityData@shared@@AEBU23@@Z; std::vector<shared::ActivityData>::emplace_back<shared::ActivityData const &>(shared::ActivityData const &)
0x180073aad  mov     rdx, [r15+218h]; unsigned __int64
0x180073ab4  lea     rcx, [rsp+458h+var_3D8]; this
0x180073abc  call    ?RemoveOperationForOrder@ActivityOperationManager@ActivityFeedClient@@QEAAX_K@Z; ActivityFeedClient::ActivityOperationManager::RemoveOperationForOrder(unsigned __int64)
0x180073ac1  mov     [rsp+458h+var_408], r12b
0x180073ac6  lea     rcx, [rsp+458h+var_268]; this
0x180073ace  call    ??1ActivityData@shared@@QEAA@XZ; shared::ActivityData::~ActivityData(void)
0x180073ad3  nop
0x180073ad4  mov     rcx, [rsp+458h+var_330]; this
0x180073adc  test    rcx, rcx
0x180073adf  jz      short loc_180073AE7
0x180073ae1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180073ae6  nop
0x180073ae7  lea     rcx, [rsp+458h+var_3B0]
0x180073aef  jmp     loc_180073E79
0x180073af4  lea     rdx, aTextReceivedPu_0; "{\"text\":\"Received publish result for"...
0x180073afb  mov     ecx, edi
0x180073afd  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180073b02  jmp     short loc_180073AE7
0x180073b04  cmp     [r15], di
0x180073b08  jnz     loc_180073C44
0x180073b0e  movups  xmm0, xmmword ptr [r15+8]
0x180073b13  movdqu  xmmword ptr [rsp+458h+var_2C8.Data1], xmm0
0x180073b1c  lea     rdx, [rsp+458h+var_2A8]
0x180073b24  lea     rcx, [rsp+458h+var_2C8]
0x180073b2c  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x180073b31  nop
0x180073b32  cmp     qword ptr [rax+18h], 0Fh
0x180073b37  jbe     short loc_180073B3C
0x180073b39  mov     rax, [rax]
0x180073b3c  mov     qword ptr [rsp+458h+var_2C8.Data1], rax
0x180073b44  mov     cl, [r15+2Dh]
0x180073b48  call    ?ToString@EnumMapper@@YAPEBDW4ActivityStatus@shared@@@Z; EnumMapper::ToString(shared::ActivityStatus)
0x180073b4d  mov     [rsp+458h+var_3A0], rax
0x180073b55  lea     r9, [rsp+458h+var_2C8]
0x180073b5d  lea     r8, [rsp+458h+var_3A0]
0x180073b65  lea     rdx, aTextRetrySOper; "{\"text\":\"Retry %s operation for acti"...
0x180073b6c  mov     ecx, 4
0x180073b71  call    ??$Log@PEBD_K@@YAXW4CDPLogLevel@@PEBD$$QEAPEBD$$QEA_K@Z; Log<char const *,unsigned __int64>(CDPLogLevel,char const *,char const * &&,unsigned __int64 &&)
0x180073b76  nop
0x180073b77  lea     rcx, [rsp+458h+var_2A8]; void *
0x180073b7f  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180073b84  mov     [rsp+458h+var_407], r12b
0x180073b89  mov     r8, [r15+218h]
0x180073b90  lea     rdx, [rsp+458h+var_3C8]
0x180073b98  lea     rcx, [rsp+458h+var_3D8]
0x180073ba0  call    ?GetOperationsForOrder@ActivityOperationManager@ActivityFeedClient@@QEAA?AV?$unique_ptr@VActivityOperation@ActivityFeedClient@@U?$default_delete@VActivityOperation@ActivityFeedClient@@@std@@@std@@_K@Z; ActivityFeedClient::ActivityOperationManager::GetOperationsForOrder(unsigned __int64)
0x180073ba5  nop
0x180073ba6  mov     rbx, [rsp+458h+var_3C8]
0x180073bae  test    rbx, rbx
0x180073bb1  jz      short loc_180073C23
0x180073bb3  movzx   ecx, byte ptr [r15+2Dh]
0x180073bb8  test    ecx, ecx
0x180073bba  jz      short loc_180073BD5
0x180073bbc  sub     ecx, 1
0x180073bbf  jz      short loc_180073BD0
0x180073bc1  cmp     ecx, 1
0x180073bc4  jz      short loc_180073BCB
0x180073bc6  mov     r8b, sil
0x180073bc9  jmp     short loc_180073BD8
0x180073bcb  mov     r8b, r12b
0x180073bce  jmp     short loc_180073BD8
0x180073bd0  mov     r8b, 5
0x180073bd3  jmp     short loc_180073BD8
0x180073bd5  mov     r8b, 4
0x180073bd8  lea     rdx, [r15+8]
0x180073bdc  lea     rcx, [r14+708h]
0x180073be3  call    ?GetReleaseTimeForActivityOperation@ActivityThrottling@cdp@@QEAA_JAEBUActivityData@shared@@W4AFSOperationType@2@@Z; cdp::ActivityThrottling::GetReleaseTimeForActivityOperation(shared::ActivityData const &,cdp::AFSOperationType)
0x180073be8  mov     [rbx+78h], rax
0x180073bec  mov     rdx, [rsp+458h+var_3C8]; struct ActivityFeedClient::ActivityOperation *
0x180073bf4  lea     rcx, [rsp+458h+var_3D8]; this
0x180073bfc  call    ?UpdateOperation@ActivityOperationManager@ActivityFeedClient@@QEAAXPEAVActivityOperation@2@@Z; ActivityFeedClient::ActivityOperationManager::UpdateOperation(ActivityFeedClient::ActivityOperation *)
0x180073c01  nop
0x180073c02  lea     rcx, [rsp+458h+var_3C8]
0x180073c0a  call    ??1?$unique_ptr@VActivityOperation@ActivityFeedClient@@U?$default_delete@VActivityOperation@ActivityFeedClient@@@std@@@std@@QEAA@XZ; std::unique_ptr<ActivityFeedClient::ActivityOperation>::~unique_ptr<ActivityFeedClient::ActivityOperation>(void)
0x180073c0f  nop
0x180073c10  mov     rcx, r13; _Mtx_t
0x180073c13  call    cs:__imp__Mtx_unlock
0x180073c19  mov     edi, 2
0x180073c1e  jmp     loc_1800744D5
0x180073c23  lea     rdx, aTextReceivedTh; "{\"text\":\"Received throttled result f"...
0x180073c2a  mov     edi, 2
0x180073c2f  mov     ecx, edi
0x180073c31  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180073c36  nop
0x180073c37  lea     rcx, [rsp+458h+var_3C8]
0x180073c3f  jmp     loc_180073E79
0x180073c44  cmp     [r15], si
0x180073c48  jnz     loc_1800744CC
0x180073c4e  lea     rbx, [r15+2Dh]
0x180073c52  movups  xmm0, xmmword ptr [r15+8]
0x180073c57  lea     rdx, [rsp+458h+var_2A8]
0x180073c5f  lea     rcx, [rsp+458h+var_2C8]
0x180073c67  movdqu  xmmword ptr [rsp+458h+var_2C8.Data1], xmm0
0x180073c70  cmp     [rbx], dil
0x180073c73  jnz     loc_180073E93
0x180073c79  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x180073c7e  nop
0x180073c7f  cmp     qword ptr [rax+18h], 0Fh
0x180073c84  jbe     short loc_180073C89
0x180073c86  mov     rax, [rax]
0x180073c89  mov     qword ptr [rsp+458h+var_2C8.Data1], rax
0x180073c91  lea     r8, [rsp+458h+var_2C8]
0x180073c99  lea     rdx, aTextReceivedPu; "{\"text\":\"Received publish (deletion)"...
0x180073ca0  mov     ecx, 3
0x180073ca5  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x180073caa  nop
0x180073cab  lea     rcx, [rsp+458h+var_2A8]; void *
0x180073cb3  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180073cb8  mov     r8, [r15+218h]
0x180073cbf  lea     rdx, [rsp+458h+var_3A8]
0x180073cc7  lea     rcx, [rsp+458h+var_3D8]
0x180073ccf  call    ?GetOperationsForOrder@ActivityOperationManager@ActivityFeedClient@@QEAA?AV?$unique_ptr@VActivityOperation@ActivityFeedClient@@U?$default_delete@VActivityOperation@ActivityFeedClient@@@std@@@std@@_K@Z; ActivityFeedClient::ActivityOperationManager::GetOperationsForOrder(unsigned __int64)
0x180073cd4  nop
0x180073cd5  mov     rcx, [rsp+458h+var_3A8]
0x180073cdd  test    rcx, rcx
0x180073ce0  jz      loc_180073E83
0x180073ce6  lea     rdx, [rsp+458h+var_320]
0x180073cee  call    ?get_Activity@ActivityOperation@ActivityFeedClient@@QEBA?AV?$shared_ptr@VActivityData@ActivityFeedClient@@@std@@XZ; ActivityFeedClient::ActivityOperation::get_Activity(void)
0x180073cf3  nop
0x180073cf4  mov     rdx, [rax]
0x180073cf7  lea     rcx, [rsp+458h+var_268]
0x180073cff  call    ?TransformActivityDataFromDbToCloudModel@cdp@@YA?AUActivityData@shared@@PEBV2ActivityFeedClient@@@Z; cdp::TransformActivityDataFromDbToCloudModel(ActivityFeedClient::ActivityData const *)
0x180073d04  nop
0x180073d05  mov     rcx, [rsp+458h+var_318]; this
0x180073d0d  test    rcx, rcx
0x180073d10  jz      short loc_180073D17
0x180073d12  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180073d17  mov     [rsp+458h+var_243], dil
0x180073d1f  mov     [rsp+458h+var_D0], dil
0x180073d27  movaps  xmm0, [rsp+458h+var_268]
0x180073d2f  movdqu  xmmword ptr [rsp+458h+var_2C8.Data1], xmm0
0x180073d38  lea     rdx, [rsp+458h+var_2A8]
0x180073d40  lea     rcx, [rsp+458h+var_2C8]
0x180073d48  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x180073d4d  nop
0x180073d4e  cmp     qword ptr [rax+18h], 0Fh
0x180073d53  jbe     short loc_180073D58
0x180073d55  mov     rax, [rax]
0x180073d58  mov     qword ptr [rsp+458h+var_2C8.Data1], rax
0x180073d60  lea     r8, [rsp+458h+var_2C8]
0x180073d68  lea     rdx, aTextActivitySW; "{\"text\":\"Activity %s was deleted fro"...
0x180073d6f  mov     ecx, 3
0x180073d74  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x180073d79  nop
0x180073d7a  lea     rcx, [rsp+458h+var_2A8]; void *
0x180073d82  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180073d87  movaps  xmm0, [rsp+458h+var_268]
0x180073d8f  movdqu  xmmword ptr [rsp+458h+var_2C8.Data1], xmm0
0x180073d98  lea     rdx, [rsp+458h+var_2C8]
0x180073da0  lea     rcx, [rsp+458h+var_380]
0x180073da8  call    ?UpdateActivityStatus@ActivityWriter@ActivityFeedClient@@QEAAXU_GUID@@W4Activity_Status@2@@Z; ActivityFeedClient::ActivityWriter::UpdateActivityStatus(_GUID,ActivityFeedClient::Activity_Status)
0x180073dad  mov     eax, [rsp+458h+var_248]
0x180073db4  add     eax, 0FFFFFFF5h
0x180073db7  cmp     eax, r12d
0x180073dba  ja      loc_180073E4E
0x180073dc0  movaps  xmm0, [rsp+458h+var_268]
0x180073dc8  movdqu  xmmword ptr [rsp+458h+var_2C8.Data1], xmm0
0x180073dd1  lea     rdx, [rsp+458h+var_2A8]
0x180073dd9  lea     rcx, [rsp+458h+var_2C8]
0x180073de1  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x180073de6  nop
0x180073de7  cmp     qword ptr [rax+18h], 0Fh
0x180073dec  jbe     short loc_180073DF1
0x180073dee  mov     rax, [rax]
0x180073df1  mov     qword ptr [rsp+458h+var_2C8.Data1], rax
0x180073df9  lea     r8, [rsp+458h+var_2C8]
0x180073e01  lea     rdx, aTextWritingDel; "{\"text\":\"Writing deletion time of CD"...
0x180073e08  mov     ecx, 4
0x180073e0d  call    ??$Log@AEA_K@@YAXW4CDPLogLevel@@PEBDAEA_K@Z; Log<unsigned __int64 &>(CDPLogLevel,char const *,unsigned __int64 &)
0x180073e12  nop
0x180073e13  lea     rcx, [rsp+458h+var_2A8]; void *
0x180073e1b  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180073e20  movaps  xmm0, [rsp+458h+var_268]
0x180073e28  movdqu  xmmword ptr [rsp+458h+var_2C8.Data1], xmm0
0x180073e31  mov     r8, [rsp+458h+var_168]; __int64
0x180073e39  lea     rdx, [rsp+458h+var_2C8]; struct _GUID
0x180073e41  lea     rcx, [rsp+458h+var_380]; this
0x180073e49  call    ?TombstoneActivity@ActivityWriter@ActivityFeedClient@@QEAAXU_GUID@@_J@Z; ActivityFeedClient::ActivityWriter::TombstoneActivity(_GUID,__int64)
0x180073e4e  mov     rdx, [r15+218h]; unsigned __int64
0x180073e55  lea     rcx, [rsp+458h+var_3D8]; this
0x180073e5d  call    ?RemoveOperationForOrder@ActivityOperationManager@ActivityFeedClient@@QEAAX_K@Z; ActivityFeedClient::ActivityOperationManager::RemoveOperationForOrder(unsigned __int64)
0x180073e62  nop
0x180073e63  lea     rcx, [rsp+458h+var_268]; this
0x180073e6b  call    ??1ActivityData@shared@@QEAA@XZ; shared::ActivityData::~ActivityData(void)
0x180073e70  nop
0x180073e71  lea     rcx, [rsp+458h+var_3A8]
0x180073e79  call    ??1?$unique_ptr@VActivityOperation@ActivityFeedClient@@U?$default_delete@VActivityOperation@ActivityFeedClient@@@std@@@std@@QEAA@XZ; std::unique_ptr<ActivityFeedClient::ActivityOperation>::~unique_ptr<ActivityFeedClient::ActivityOperation>(void)
0x180073e7e  jmp     loc_1800744CC
0x180073e83  lea     rdx, aTextReceivedOn_14; "{\"text\":\"Received OnDeleteResult wit"...
0x180073e8a  mov     ecx, edi
0x180073e8c  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x180073e91  jmp     short loc_180073E71
0x180073e93  jb      short loc_180073ED0
0x180073e95  call    ?ToString@CDP_UUID@cdp@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; cdp::CDP_UUID::ToString(void)
0x180073e9a  nop
0x180073e9b  cmp     qword ptr [rax+18h], 0Fh
0x180073ea0  jbe     short loc_180073EA5
0x180073ea2  mov     rax, [rax]
  ... truncated ...
```
