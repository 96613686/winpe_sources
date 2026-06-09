# HNS::Service::Core::NetworkNotificationManager::ProcessNotification(void)

- ea: `0x1800f4090`
- end: `0x1800f4e74`
- name: `?ProcessNotification@NetworkNotificationManager@Core@Service@HNS@@EEAAXXZ`
- size: `3556`
- prototype: `void __fastcall(HNS::Service::Core::NetworkNotificationManager *__hidden this)`
- caller_count: `0`
- callee_count: `35`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001b68`
- `0x180001d38`
- `0x180003078`
- `0x18005f0c0`
- `0x18005f59c`
- `0x18005ffa0`
- `0x18005ffc4`
- `0x1800663fc`
- `0x1800666b4`
- `0x1800759d8`
- `0x180075aac`
- `0x18008a024`
- `0x1800b1948`
- `0x1800c1684`
- `0x1800c41f4`
- `0x1800c7634`
- `0x1800c8968`
- `0x1800c8b8c`
- `0x1800d7e58`
- `0x1800d7f70`
- `0x1800ee4fc`
- `0x1800f010c`
- `0x1800f0bc0`
- `0x1800f0d9c`
- `0x1800f1074`
- `0x1800f15d8`
- `0x1800f1e08`
- `0x1800f20fc`
- `0x1800f2194`
- `0x1800f4090`
- `0x1800f4e7c`
- `0x1800f533c`
- `0x1800f83e0`
- `0x18023e880`
- `0x1802b7010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800f48c0`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800f48c0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4328`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4584`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f468e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4bb6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4ca4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4328`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4584`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f468e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4bb6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4ca4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f4179`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f4741`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f4179`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f4741`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800f4102`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800f4102`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f415a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f46a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f415a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f46a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800f4434`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800f4a47`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800f4434`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800f4a47`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f49e9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800f49e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f4deb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800f4deb`

## string_xrefs

- `0x1800f4e4b`: `onecore\vm\common\vml\vmosversion.h`
- `0x1800f4e63`: `onecore\vm\common\vml\vmosversion.h`
- `0x1800f4e31`: `onecore\vm\dv\net\hns\service\core\networknotificationmanager.cpp`
- `0x1800f40d1`: `HNS::Service::Core::NetworkNotificationManager::ProcessNotification`
- `0x1800f4903`: `HNS::Service::Core::NetworkNotificationManager::ProcessNotification`
- `0x1800f49b3`: `HNS::Service::Core::NetworkNotificationManager::ProcessNotification`
- `0x1800f49d0`: `HNS::Service::Core::NetworkNotificationManager::ProcessNotification`
- `0x1800f4cb4`: `HNS::Service::Core::NetworkNotificationManager::ProcessNotification`
- `0x1800f4ce3`: `HNS::Service::Core::NetworkNotificationManager::ProcessNotification`
- `0x1800f4d6e`: `HNS::Service::Core::NetworkNotificationManager::ProcessNotification`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall HNS::Service::Core::NetworkNotificationManager::ProcessNotification(
        HNS::Service::Core::NetworkNotificationManager *this)
{
  HNS::Service::Core::NetworkNotificationManager *v1; // r15
  _QWORD *v2; // rax
  int v3; // r8d
  int v4; // r9d
  HNS::Service::Core::NetworkEntityManager **v5; // r12
  _QWORD *v6; // rsi
  struct _IP_ADAPTER_ADDRESSES_LH *v7; // rdi
  const char *v8; // rbx
  int v9; // r8d
  int v10; // r9d
  struct _IP_ADAPTER_ADDRESSES_LH *i; // rcx
  void *v12; // rcx
  PWCHAR FriendlyName; // rdx
  __int64 v14; // rax
  unsigned int v15; // eax
  HNS::Service::Common *v16; // rcx
  __int64 v17; // r8
  const char *v18; // r9
  unsigned int v19; // r12d
  HNS::Service::Core::NetworkEntityManager **v20; // rbx
  struct _IP_ADAPTER_ADDRESSES_LH *v21; // r13
  volatile signed __int32 *v22; // rbx
  wil *v23; // rcx
  __int64 v24; // rcx
  int v25; // r9d
  int v26; // ebx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 *v29; // rcx
  __int64 *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r12
  HNS::Service::Core::RegKeyWatcher **j; // rbx
  struct _IP_ADAPTER_ADDRESSES_LH *v34; // r13
  int v35; // r8d
  int v36; // r9d
  int v37; // r8d
  int v38; // r9d
  struct _IP_ADAPTER_ADDRESSES_LH *k; // rax
  int v40; // ecx
  void *v41; // rdx
  HNS::Service::Common *v42; // rcx
  const char *v43; // r9
  __int64 v44; // r8
  wil *v45; // rcx
  __int64 v46; // r8
  wil *v47; // rcx
  __int64 v48; // rcx
  int v49; // r9d
  int v50; // r12d
  __int64 v51; // rcx
  __int64 v52; // rax
  wil *v53; // rcx
  __int64 **v54; // rcx
  __int64 n; // rax
  __int64 *m; // rcx
  int v57; // r8d
  const char *v58; // r9
  __int64 v59; // rbx
  int v60; // ebx
  int v61; // r8d
  int v62; // r9d
  __int64 v63; // rbx
  int v64; // ebx
  int v65; // r8d
  int v66; // r9d
  __int64 v67; // rbx
  int v68; // ebx
  int v69; // r8d
  int v70; // r9d
  int v71; // [rsp+20h] [rbp-528h]
  char v72; // [rsp+40h] [rbp-508h]
  struct _IP_ADAPTER_ADDRESSES_LH *v73; // [rsp+48h] [rbp-500h] BYREF
  struct _IP_ADAPTER_ADDRESSES_LH *v74; // [rsp+50h] [rbp-4F8h] BYREF
  const char *v75; // [rsp+58h] [rbp-4F0h] BYREF
  HNS::Service::Core::NetworkEntityManager **v76; // [rsp+60h] [rbp-4E8h]
  struct _IP_ADAPTER_ADDRESSES_LH *v77; // [rsp+68h] [rbp-4E0h] BYREF
  HNS::Service::Core::NetworkNotificationManager *v78; // [rsp+70h] [rbp-4D8h]
  __int16 v79; // [rsp+78h] [rbp-4D0h] BYREF
  int v80; // [rsp+7Ch] [rbp-4CCh]
  int v81; // [rsp+80h] [rbp-4C8h] BYREF
  int v82; // [rsp+84h] [rbp-4C4h] BYREF
  _QWORD *v83; // [rsp+88h] [rbp-4C0h]
  HNS::Service::Core::NetworkEntityManager **v84; // [rsp+90h] [rbp-4B8h]
  const char *v85; // [rsp+98h] [rbp-4B0h] BYREF
  const char *v86; // [rsp+A0h] [rbp-4A8h] BYREF
  int v87; // [rsp+A8h] [rbp-4A0h] BYREF
  int v88; // [rsp+ACh] [rbp-49Ch] BYREF
  int v89; // [rsp+B0h] [rbp-498h] BYREF
  int v90; // [rsp+B4h] [rbp-494h] BYREF
  int v91; // [rsp+B8h] [rbp-490h] BYREF
  int v92; // [rsp+BCh] [rbp-48Ch] BYREF
  int v93; // [rsp+C0h] [rbp-488h] BYREF
  HNS::Service::Core::NetworkNotificationManager *v94; // [rsp+C8h] [rbp-480h]
  char v95[8]; // [rsp+D0h] [rbp-478h] BYREF
  void *v96; // [rsp+D8h] [rbp-470h]
  char v97[8]; // [rsp+E0h] [rbp-468h] BYREF
  void *Block; // [rsp+E8h] [rbp-460h]
  struct _IP_ADAPTER_ADDRESSES_LH *v99; // [rsp+F0h] [rbp-458h] BYREF
  struct _IP_ADAPTER_ADDRESSES_LH *v100; // [rsp+F8h] [rbp-450h] BYREF
  _QWORD *v101; // [rsp+100h] [rbp-448h]
  HANDLE *v102; // [rsp+108h] [rbp-440h]
  const char *v103; // [rsp+110h] [rbp-438h]
  struct _IP_ADAPTER_ADDRESSES_LH *v104; // [rsp+118h] [rbp-430h] BYREF
  __int64 (__fastcall *v105)(); // [rsp+120h] [rbp-428h] BYREF
  int v106; // [rsp+128h] [rbp-420h]
  int v107; // [rsp+12Ch] [rbp-41Ch]
  __int64 (__fastcall *v108)(); // [rsp+130h] [rbp-418h] BYREF
  int v109; // [rsp+138h] [rbp-410h]
  int v110; // [rsp+13Ch] [rbp-40Ch]
  __int64 (__fastcall *v111)(); // [rsp+140h] [rbp-408h] BYREF
  int v112; // [rsp+148h] [rbp-400h]
  int v113; // [rsp+14Ch] [rbp-3FCh]
  __int64 (__fastcall *v114)(); // [rsp+150h] [rbp-3F8h] BYREF
  int v115; // [rsp+158h] [rbp-3F0h]
  int v116; // [rsp+15Ch] [rbp-3ECh]
  _QWORD v117[2]; // [rsp+160h] [rbp-3E8h] BYREF
  char v118[8]; // [rsp+170h] [rbp-3D8h] BYREF
  _QWORD *v119; // [rsp+178h] [rbp-3D0h]
  __int64 v120; // [rsp+180h] [rbp-3C8h]
  _QWORD v121[2]; // [rsp+188h] [rbp-3C0h] BYREF
  char v122[8]; // [rsp+198h] [rbp-3B0h] BYREF
  volatile signed __int32 *v123; // [rsp+1A0h] [rbp-3A8h]
  char v124[8]; // [rsp+1A8h] [rbp-3A0h] BYREF
  char v125[12]; // [rsp+1B0h] [rbp-398h] BYREF
  int v126; // [rsp+1BCh] [rbp-38Ch]
  char v127[40]; // [rsp+1C0h] [rbp-388h] BYREF
  struct _OSVERSIONINFOW v128; // [rsp+1E8h] [rbp-360h] BYREF
  char v129; // [rsp+302h] [rbp-246h]
  struct _OSVERSIONINFOW VersionInformation; // [rsp+308h] [rbp-240h] BYREF
  char v131; // [rsp+422h] [rbp-126h]
  struct _GUID v132; // [rsp+428h] [rbp-120h] BYREF
  struct _GUID v133; // [rsp+438h] [rbp-110h] BYREF
  struct _GUID Buf1; // [rsp+448h] [rbp-100h] BYREF
  char v135; // [rsp+458h] [rbp-F0h] BYREF
  int v136; // [rsp+464h] [rbp-E4h]
  char v137; // [rsp+468h] [rbp-E0h] BYREF
  int v138; // [rsp+474h] [rbp-D4h]
  char v139; // [rsp+478h] [rbp-D0h] BYREF
  char v140; // [rsp+488h] [rbp-C0h] BYREF
  _BYTE v141[32]; // [rsp+4A0h] [rbp-A8h] BYREF
  const char *v142; // [rsp+4C0h] [rbp-88h]
  __int64 v143; // [rsp+4C8h] [rbp-80h]
  int *v144; // [rsp+4D0h] [rbp-78h]
  __int64 v145; // [rsp+4D8h] [rbp-70h]
  _QWORD *v146; // [rsp+4E0h] [rbp-68h]
  __int64 v147; // [rsp+4E8h] [rbp-60h]
  const char **v148; // [rsp+4F0h] [rbp-58h]
  __int64 v149; // [rsp+4F8h] [rbp-50h]
  int *v150; // [rsp+500h] [rbp-48h]
  __int64 v151; // [rsp+508h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+0h]

  v1 = this;
  v78 = this;
  v94 = this;
  HNSTraceProvider::TraceEnter("HNS::Service::Core::NetworkNotificationManager::ProcessNotification", 0xE1u);
  if ( *((_DWORD *)v1 - 6) == 2 )
  {
    v80 = 0;
    v102 = (HANDLE *)((char *)v1 + 8);
    ResetEvent(*((HANDLE *)v1 + 1));
    try
    {
      v117[1] = 0;
      v117[0] = &HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,std::list<HNS::Service::Common::Notify::InterfaceNotification>,NET_LUID_Comparator>::`vftable';
      v120 = 0;
      v2 = operator new(0x38u);
      *v2 = v2;
      v2[1] = v2;
      v2[2] = v2;
      *((_WORD *)v2 + 12) = 257;
      v119 = v2;
      AcquireSRWLockExclusive((PSRWLOCK)v1 + 4);
      HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,std::list<HNS::Service::Common::Notify::InterfaceNotification>,NET_LUID_Comparator>::operator=(
        v117,
        (char *)v1 + 24);
      if ( v1 != (HNS::Service::Core::NetworkNotificationManager *)-32LL )
        ReleaseSRWLockExclusive((PSRWLOCK)v1 + 4);
      v5 = (HNS::Service::Core::NetworkEntityManager **)((char *)v1 + 1608);
      v76 = (HNS::Service::Core::NetworkEntityManager **)((char *)v1 + 1608);
      if ( *(_DWORD *)(*((_QWORD *)v1 + 201) + 80LL) != 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networknotificationmanager.cpp",
          (const char *)0x80070015LL,
          v71);
      v84 = (HNS::Service::Core::NetworkEntityManager **)((char *)v1 + 1608);
      v6 = (_QWORD *)*v119;
      v101 = v119;
LABEL_7:
      v83 = v6;
      while ( v6 != v101 )
      {
        v7 = (struct _IP_ADAPTER_ADDRESSES_LH *)v6[4];
        v74 = v7;
        if ( *(_DWORD *)qword_180399BB8 > 5u )
        {
          v77 = v7;
          LODWORD(v73) = 268;
          v85 = "HNS::Service::Core::NetworkNotificationManager::ProcessNotification";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            qword_180399BB8,
            (unsigned int)&unk_180337F2A,
            v3,
            v4,
            (__int64)&v85,
            (__int64)&v73,
            (__int64)&v77);
        }
        try
        {
          std::list<HNS::Service::Common::Notify::InterfaceNotification>::list<HNS::Service::Common::Notify::InterfaceNotification>(
            v121,
            v6 + 5);
          v85 = *(const char **)v121[0];
          v103 = (const char *)v121[0];
          while ( 2 )
          {
            v8 = v85;
            if ( v85 == v103 )
            {
              std::list<HNS::Service::Common::Notify::InterfaceNotification>::~list<HNS::Service::Common::Notify::InterfaceNotification>(v121);
              goto LABEL_158;
            }
            ++v80;
            if ( *((_DWORD *)v85 + 4) != 1 )
            {
              if ( *((_DWORD *)v85 + 4) != 2 )
              {
                if ( *((_DWORD *)v85 + 4) != 4 )
                  goto LABEL_114;
                IPHelper::GetAdapterAddresses(v97, 2, 134);
                for ( i = (struct _IP_ADAPTER_ADDRESSES_LH *)Block;
                      i && (struct _IP_ADAPTER_ADDRESSES_LH *)i->Luid.Value != v7;
                      i = i->Next )
                {
                  ;
                }
                v77 = i;
                if ( !i )
                {
                  if ( *(_DWORD *)qword_180399BB8 > 5u )
                  {
                    v77 = v7;
                    LODWORD(v73) = 293;
                    v75 = "HNS::Service::Core::NetworkNotificationManager::ProcessNotification";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                      qword_180399BB8,
                      (unsigned int)&unk_180337F74,
                      v9,
                      v10,
                      (__int64)&v75,
                      (__int64)&v73,
                      (__int64)&v77);
                  }
                  v12 = Block;
LABEL_23:
                  if ( v12 )
                    free(v12);
LABEL_114:
                  v85 = *(const char **)v85;
                  continue;
                }
                if ( *(_DWORD *)qword_180399BB8 > 5u )
                {
                  v75 = (const char *)v7;
                  FriendlyName = i->FriendlyName;
                  v87 = 303;
                  v148 = &v75;
                  v149 = 8;
                  if ( FriendlyName )
                  {
                    v14 = -1;
                    do
                      ++v14;
                    while ( FriendlyName[v14] );
                    v15 = 2 * v14 + 2;
                  }
                  else
                  {
                    FriendlyName = (PWCHAR)&unk_1802E2A80;
                    v15 = 2;
                  }
                  v146 = FriendlyName;
                  v147 = v15;
                  v144 = &v87;
                  v145 = 4;
                  v142 = "HNS::Service::Core::NetworkNotificationManager::ProcessNotification";
                  v143 = 68;
                  tlgWriteTransfer_EventWriteTransfer(qword_180399BB8, &unk_180337C55, 0, 0, 6, v141);
                }
                memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
                VersionInformation.dwOSVersionInfoSize = 284;
                if ( !GetVersionExW(&VersionInformation) )
                  wil::details::in1diag3::Throw_GetLastError(
                    retaddr,
                    (void *)0x40,
                    (unsigned int)"onecore\\vm\\common\\vml\\vmosversion.h",
                    v18);
                if ( v131 == 1 || HNS::Service::Common::IsClientMultiSession(v16) )
                {
                  LODWORD(v73) = (v8[40] & 1) != 0 ? 9 : 7;
                  v19 = (unsigned int)v73;
                  v20 = v76;
                  LOBYTE(v17) = _InterlockedCompareExchange((volatile signed __int32 *)*v76 + 236, 0, 0) != 0;
                  if ( (unsigned __int8)HNS::Service::Core::IsAdapterSuitableForMirroring(&v77, v19, v17) )
                  {
                    v21 = v77;
                    v75 = *(const char **)HNS::Service::Core::NetworkEntityManager::FindMirroredNetworks(
                                            *v20,
                                            v122,
                                            &v77->Luid,
                                            v19);
                    v22 = v123;
                    if ( v123 )
                    {
                      if ( _InterlockedExchangeAdd(v123 + 2, 0xFFFFFFFF) == 1 )
                      {
                        (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
                        if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
                      }
                    }
                    if ( !v75 )
                    {
                      try
                      {
                        HNS::Service::Core::NetworkEntityManager::CreateMirroredNetwork(*v76, v21, v19);
                      }
                      catch ( ... )
                      {
                        v59 = qword_180399BB8;
                        if ( *(_DWORD *)qword_180399BB8 > 2u )
                        {
                          v88 = wil::ResultFromCaughtException(v23);
                          v79 = (__int16)v73;
                          v104 = v74;
                          v93 = 341;
                          v150 = &v88;
                          v151 = 4;
                          v148 = (const char **)&v79;
                          v149 = 2;
                          v146 = &v104;
                          v147 = 8;
                          v144 = &v93;
                          v145 = 4;
                          v142 = "HNS::Service::Core::NetworkNotificationManager::ProcessNotification";
                          v143 = 68;
                          tlgWriteTransfer_EventWriteTransfer(v59, &unk_180337CC6, 0, 0, 7, v141);
                        }
                        if ( Block )
                          free(Block);
                        v6 = v83;
                        v7 = v74;
                        v5 = v84;
                        v76 = v84;
                        v1 = v78;
                        goto LABEL_114;
                      }
                    }
                    if ( v21->IfType != 24 )
                      HNS::Service::Core::RegistryKeyNotificationManager::NotifyDNSServerChange(
                        *((HNS::Service::Core::RegistryKeyNotificationManager **)v1 + 205),
                        v21);
                  }
                }
                if ( !(unsigned __int8)HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::Contains(
                                         (char *)v1 + 1568,
                                         &v74) )
                {
                  v24 = *((_QWORD *)v1 + 203) + 104LL;
                  if ( v1 == (HNS::Service::Core::NetworkNotificationManager *)104 )
                  {
                    v25 = 0;
                    v26 = (_DWORD)v94 + 1392;
                  }
                  else
                  {
                    v25 = (_DWORD)v1 + 1392;
                    v26 = (_DWORD)v1 + 1392;
                  }
                  v105 = HNS::Service::Core::NetworkNotificationManager::OnNetworkInterfaceRemoved;
                  v106 = 0;
                  v107 = HIDWORD(v123);
                  HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(
                    v24,
                    (unsigned int)&v135,
                    26,
                    v25,
                    (__int64)&v105,
                    (char)v7);
                  v27 = *((_QWORD *)v1 + 203) + 104LL;
                  v108 = HNS::Service::Core::NetworkNotificationManager::OnNetworkAddressChanged;
                  v109 = 0;
                  v110 = v136;
                  v28 = HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(
                          v27,
                          (unsigned int)&v139,
                          28,
                          v26 & (unsigned int)-(v1 != (HNS::Service::Core::NetworkNotificationManager *)104),
                          (__int64)&v108,
                          (char)v7);
                  HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::Add<_GUID>(
                    (char *)v1 + 1568,
                    &v74,
                    v28);
                  v7 = v74;
                }
                if ( Block )
                  free(Block);
LABEL_113:
                v5 = v76;
                goto LABEL_114;
              }
              AcquireSRWLockExclusive((PSRWLOCK)v1 + 197);
              v75 = (char *)v1 + 1576;
              v29 = (__int64 *)*((_QWORD *)v1 + 199);
              v30 = (__int64 *)v29[1];
              while ( !*((_BYTE *)v30 + 25) )
              {
                if ( v30[4] >= (unsigned __int64)v7 )
                {
                  v29 = v30;
                  v30 = (__int64 *)*v30;
                }
                else
                {
                  v30 = (__int64 *)v30[2];
                }
              }
              if ( !*((_BYTE *)v29 + 25) && (unsigned __int64)v7 >= v29[4] )
              {
                Buf1 = *(struct _GUID *)(v29 + 5);
                if ( memcmp_0(&Buf1, &xmmword_18039A420, 0x10u) )
                {
                  HNS::Service::Events::InternalEventManager::Unsubscribe(
                    (HNS::Service::Events::InternalEventManager *)(*((_QWORD *)v1 + 203) + 104LL),
                    &Buf1);
                  HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::RemoveLocked(
                    (char *)v1 + 1568,
                    &v74);
                }
                if ( v1 != (HNS::Service::Core::NetworkNotificationManager *)-1576LL )
                  ReleaseSRWLockExclusive((PSRWLOCK)v1 + 197);
                v132 = GUID_NULL;
                v133 = GUID_NULL;
                if ( (unsigned int)HNS::Service::Core::NetworkEntityManager::IsMirroredNetworkingTypeEnabled(*v5, 2) )
                {
                  v132 = *(struct _GUID *)HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::Find(
                                            (char *)v1 + 1488,
                                            v127,
                                            &v74);
                  if ( memcmp_0(&v132, &GUID_NULL, 0x10u) )
                    HNS::Service::Core::NetworkEntityManager::DestroyMirroredNetwork(*v5, &v132);
                }
                if ( (unsigned int)HNS::Service::Core::NetworkEntityManager::IsMirroredNetworkingTypeEnabled(*v5, 1) )
                {
                  v133 = *(struct _GUID *)HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::Find(
                                            (char *)v1 + 1448,
                                            v125,
                                            &v74);
                  if ( memcmp_0(&v133, &GUID_NULL, 0x10u) )
                    HNS::Service::Core::NetworkEntityManager::DestroyMirroredNetwork(*v5, &v133);
                }
                if ( !memcmp_0(&v132, &GUID_NULL, 0x10u) && !memcmp_0(&v133, &GUID_NULL, 0x10u) )
                  goto LABEL_114;
                v31 = *((_QWORD *)v1 + 205);
                v32 = v31 + 128;
                for ( j = *(HNS::Service::Core::RegKeyWatcher ***)(v31 + 128);
                      j != *(HNS::Service::Core::RegKeyWatcher ***)(v31 + 136);
                      j += 2 )
                {
                  if ( *((struct _IP_ADAPTER_ADDRESSES_LH **)*j + 8) == v7 )
                  {
                    HNS::Service::Core::RegKeyWatcher::Stop(*j);
                    std::vector<std::shared_ptr<HNS::Service::Core::RegKeyWatcher>>::erase(v32, v124, j);
                    goto LABEL_113;
                  }
                }
                goto LABEL_113;
              }
              std::_Xout_of_range("invalid map<K, T> key");
            }
            break;
          }
          v34 = (struct _IP_ADAPTER_ADDRESSES_LH *)((char *)v1 + 1568);
          v77 = (struct _IP_ADAPTER_ADDRESSES_LH *)((char *)v1 + 1568);
          if ( (unsigned __int8)HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::Contains(
                                  (char *)v1 + 1568,
                                  &v74) )
          {
            if ( *(_DWORD *)qword_180399BB8 > 5u )
            {
              v75 = (const char *)v7;
              LODWORD(v73) = 402;
              v77 = (struct _IP_ADAPTER_ADDRESSES_LH *)"HNS::Service::Core::NetworkNotificationManager::ProcessNotification";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                qword_180399BB8,
                (unsigned int)&unk_180337B57,
                v35,
                v36,
                (__int64)&v77,
                (__int64)&v73,
                (__int64)&v75);
            }
            goto LABEL_114;
          }
          IPHelper::GetAdapterAddresses(v95, 2, 134);
          for ( k = (struct _IP_ADAPTER_ADDRESSES_LH *)v96;
                k && (struct _IP_ADAPTER_ADDRESSES_LH *)k->Luid.Value != v7;
                k = k->Next )
          {
            ;
          }
          v73 = k;
          if ( k )
          {
            Sleep(0x3E8u);
            if ( !HNS::Service::Core::NetworkEntityManager::IsHnsOwnedAdapter(&v73) )
            {
              memset_0(&v128.dwMajorVersion, 0, 0x118u);
              v128.dwOSVersionInfoSize = 284;
              if ( !GetVersionExW(&v128) )
                wil::details::in1diag3::Throw_GetLastError(
                  retaddr,
                  (void *)0x40,
                  (unsigned int)"onecore\\vm\\common\\vml\\vmosversion.h",
                  v43);
              if ( v129 == 1 || HNS::Service::Common::IsClientMultiSession(v42) )
              {
                v72 = 0;
                if ( (unsigned int)HNS::Service::Core::NetworkEntityManager::IsMirroredNetworkingTypeEnabled(*v5, 2) )
                {
                  LOBYTE(v44) = _InterlockedCompareExchange((volatile signed __int32 *)*v5 + 236, 0, 0) != 0;
                  if ( (unsigned __int8)HNS::Service::Core::IsAdapterSuitableForMirroring(&v73, 9, v44) )
                  {
                    try
                    {
                      HNS::Service::Core::NetworkEntityManager::CreateMirroredNetwork(*v5, v73, 9);
                      v72 = 1;
                    }
                    catch ( ... )
                    {
                      v60 = qword_180399BB8;
                      if ( *(_DWORD *)qword_180399BB8 > 2u )
                      {
                        v89 = wil::ResultFromCaughtException(v45);
                        v99 = v74;
                        v90 = 475;
                        v75 = "HNS::Service::Core::NetworkNotificationManager::ProcessNotification";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                          v60,
                          (unsigned int)&unk_180337EB3,
                          v61,
                          v62,
                          (__int64)&v75,
                          (__int64)&v90,
                          (__int64)&v99,
                          (__int64)&v89);
                      }
                      v63 = *((_QWORD *)v78 + 201);
                      if ( *(_BYTE *)(v63 + 664) )
                      {
                        EnterCriticalSection((LPCRITICAL_SECTION)(v63 + 736));
                        *(_BYTE *)(v63 + 664) = 0;
                        if ( v63 != -736 )
                          LeaveCriticalSection((LPCRITICAL_SECTION)(v63 + 736));
                      }
                      v6 = v83;
                      v7 = v74;
                      v5 = v84;
                      v76 = v84;
                      v1 = v78;
                      v34 = v77;
                    }
                  }
                }
                if ( (unsigned int)HNS::Service::Core::NetworkEntityManager::IsMirroredNetworkingTypeEnabled(*v5, 1)
                  && (LOBYTE(v46) = _InterlockedCompareExchange((volatile signed __int32 *)*v5 + 236, 0, 0) != 0,
                      (unsigned __int8)HNS::Service::Core::IsAdapterSuitableForMirroring(&v73, 7, v46)) )
                {
                  try
                  {
                    HNS::Service::Core::NetworkEntityManager::CreateMirroredNetwork(*v5, v73, 7);
                    v72 = 1;
                  }
                  catch ( ... )
                  {
                    v64 = qword_180399BB8;
                    if ( *(_DWORD *)qword_180399BB8 > 2u )
                    {
                      v91 = wil::ResultFromCaughtException(v47);
                      v100 = v74;
                      v92 = 504;
                      v75 = "HNS::Service::Core::NetworkNotificationManager::ProcessNotification";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                        v64,
                        (unsigned int)&unk_180337D60,
                        v65,
                        v66,
                        (__int64)&v75,
                        (__int64)&v92,
                        (__int64)&v100,
                        (__int64)&v91);
                    }
                    v67 = *((_QWORD *)v78 + 201);
                    if ( *(_BYTE *)(v67 + 496) )
                    {
                      EnterCriticalSection((LPCRITICAL_SECTION)(v67 + 568));
                      *(_BYTE *)(v67 + 496) = 0;
                      if ( v67 != -568 )
                        LeaveCriticalSection((LPCRITICAL_SECTION)(v67 + 568));
                    }
                    v6 = v83;
                    v7 = v74;
                    v5 = v84;
                    v76 = v84;
                    v1 = v78;
                    v34 = v77;
                    goto LABEL_106;
                  }
                }
                else
                {
LABEL_106:
                  if ( !v72 )
                  {
                    if ( v96 )
                      free(v96);
                    goto LABEL_114;
                  }
                }
                if ( v73->IfType != 24 )
                  HNS::Service::Core::RegistryKeyNotificationManager::NotifyDNSServerChange(
                    *((HNS::Service::Core::RegistryKeyNotificationManager **)v1 + 205),
                    v73);
              }
              v48 = *((_QWORD *)v1 + 203) + 104LL;
              if ( v1 == (HNS::Service::Core::NetworkNotificationManager *)104 )
              {
                v49 = 0;
                v50 = (_DWORD)v94 + 1392;
              }
              else
              {
                v49 = (_DWORD)v1 + 1392;
                v50 = (_DWORD)v1 + 1392;
              }
              v111 = HNS::Service::Core::NetworkNotificationManager::OnNetworkInterfaceRemoved;
              v112 = 0;
              v113 = v126;
              HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(
                v48,
                (unsigned int)&v137,
                26,
                v49,
                (__int64)&v111,
                (char)v7);
              v51 = *((_QWORD *)v1 + 203) + 104LL;
              v114 = HNS::Service::Core::NetworkNotificationManager::OnNetworkAddressChanged;
              v115 = 0;
              v116 = v138;
              v52 = HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(
                      v51,
                      (unsigned int)&v140,
                      28,
                      v50 & (unsigned int)-(v1 != (HNS::Service::Core::NetworkNotificationManager *)104),
                      (__int64)&v114,
                      (char)v7);
              HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::Add<_GUID>(v34, &v74, v52);
              HNS::Service::Core::NetworkNotificationManager::ProxyInterfaceAddEvent((HNS::Service::Core::NetworkNotificationManager *)((char *)v1 - 104));
              if ( v96 )
                free(v96);
              v7 = v74;
              goto LABEL_113;
            }
            v40 = qword_180399BB8;
            if ( *(_DWORD *)qword_180399BB8 > 5u )
            {
              LODWORD(v73) = 444;
              v41 = &unk_180337E3C;
LABEL_89:
              v77 = (struct _IP_ADAPTER_ADDRESSES_LH *)"HNS::Service::Core::NetworkNotificationManager::ProcessNotification";
              v75 = (const char *)v7;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
                v40,
                (_DWORD)v41,
                v37,
                v38,
                (__int64)&v77,
                (__int64)&v73,
                (__int64)&v75);
            }
          }
          else
          {
            v40 = qword_180399BB8;
            if ( *(_DWORD *)qword_180399BB8 > 5u )
            {
              LODWORD(v73) = 426;
              v41 = &unk_180337BD0;
              goto LABEL_89;
            }
          }
          v12 = v96;
          goto LABEL_23;
        }
        catch ( ... )
        {
          v68 = qword_180399BB8;
          if ( *(_DWORD *)qword_180399BB8 > 5u )
          {
            v86 = (const char *)v74;
            v82 = wil::ResultFromCaughtException(v53);
            v81 = 635;
            v75 = "HNS::Service::Core::NetworkNotificationManager::ProcessNotification";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
              v68,
              (unsigned int)&unk_180337DD7,
              v69,
              v70,
              (__int64)&v75,
              (__int64)&v81,
              (__int64)&v82,
              (__int64)&v86);
          }
          v6 = v83;
          v5 = v84;
          v76 = v84;
          v1 = v78;
        }
LABEL_158:
        v54 = (__int64 **)v6[2];
        if ( !*((_BYTE *)v54 + 25) )
        {
          v6 = (_QWORD *)v6[2];
          for ( m = *v54; !*((_BYTE *)m + 25); m = (__int64 *)*m )
            v6 = m;
          goto LABEL_7;
        }
        for ( n = v6[1]; !*(_BYTE *)(n + 25) && v6 == *(_QWORD **)(n + 16); n = *(_QWORD *)(n + 8) )
          v6 = (_QWORD *)n;
        v6 = (_QWORD *)n;
        v83 = (_QWORD *)n;
      }
      std::_Tree<std::_Tmap_traits<_NET_LUID_LH,std::list<HNS::Service::Common::Notify::InterfaceNotification>,NET_LUID_Comparator,std::allocator<std::pair<_NET_LUID_LH const,std::list<HNS::Service::Common::Notify::InterfaceNotification>>>,0>>::~_Tree<std::_Tmap_traits<_NET_LUID_LH,std::list<HNS::Service::Common::Notify::InterfaceNotification>,NET_LUID_Comparator,std::allocator<std::pair<_NET_LUID_LH const,std::list<HNS::Service::Common::Notify::InterfaceNotification>>>,0>>(v118);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x27F,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\networknotificationmanager.cpp",
        v58);
      v1 = v78;
    }
    if ( *(_DWORD *)qword_180399BB8 > 5u )
    {
      v81 = v80;
      v82 = 645;
      v86 = "HNS::Service::Core::NetworkNotificationManager::ProcessNotification";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        qword_180399BB8,
        (unsigned int)&unk_18033792E,
        v57,
        (_DWORD)v58,
        (__int64)&v86,
        (__int64)&v82,
        (__int64)&v81);
    }
    SetThreadpoolWait(*((PTP_WAIT *)v1 + 2), *v102, 0);
    HNSTraceProvider::TraceSuccess("HNS::Service::Core::NetworkNotificationManager::ProcessNotification", 0x289u);
  }
}

```

## disassembly

```asm
0x1800f4090  mov     [rsp+arg_8], rbx
0x1800f4095  mov     [rsp+arg_10], rsi
0x1800f409a  push    rdi
0x1800f409b  push    r12
0x1800f409d  push    r13
0x1800f409f  push    r14
0x1800f40a1  push    r15
0x1800f40a3  sub     rsp, 520h
0x1800f40aa  mov     rax, cs:__security_cookie
0x1800f40b1  xor     rax, rsp
0x1800f40b4  mov     [rsp+548h+var_38], rax
0x1800f40bc  mov     r15, rcx
0x1800f40bf  mov     [rsp+548h+var_4D8], rcx
0x1800f40c4  mov     [rsp+548h+var_480], rcx
0x1800f40cc  mov     edx, 0E1h; unsigned int
0x1800f40d1  lea     r13, aHnsServiceCore_173; "HNS::Service::Core::NetworkNotification"...
0x1800f40d8  mov     rcx, r13; char *
0x1800f40db  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800f40e0  cmp     dword ptr [r15-18h], 2
0x1800f40e5  jnz     loc_1800F4DFE
0x1800f40eb  xor     r14d, r14d
0x1800f40ee  mov     [rsp+548h+var_4CC], r14d
0x1800f40f3  lea     rcx, [r15+8]
0x1800f40f7  mov     [rsp+548h+var_440], rcx
0x1800f40ff  mov     rcx, [rcx]; hEvent
0x1800f4102  call    cs:__imp_ResetEvent
0x1800f4108  xor     eax, eax
0x1800f410a  mov     [rsp+548h+var_3E0], rax
0x1800f4112  lea     rax, ??_7?$ConcurrentMap@T_NET_LUID_LH@@V?$list@UInterfaceNotification@Notify@Common@Service@HNS@@V?$allocator@UInterfaceNotification@Notify@Common@Service@HNS@@@std@@@std@@UNET_LUID_Comparator@@@Common@Service@HNS@@6B@; const HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,std::list<HNS::Service::Common::Notify::InterfaceNotification>,NET_LUID_Comparator>::`vftable'
0x1800f4119  mov     [rsp+548h+var_3E8], rax
0x1800f4121  mov     [rsp+548h+var_3D0], r14
0x1800f4129  mov     [rsp+548h+var_3C8], r14
0x1800f4131  lea     ecx, [r14+38h]; Size
0x1800f4135  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f413a  mov     [rax], rax
0x1800f413d  mov     [rax+8], rax
0x1800f4141  mov     [rax+10h], rax
0x1800f4145  mov     word ptr [rax+18h], 101h
0x1800f414b  mov     [rsp+548h+var_3D0], rax
0x1800f4153  lea     rdi, [r15+20h]
0x1800f4157  mov     rcx, rdi; SRWLock
0x1800f415a  call    cs:__imp_AcquireSRWLockExclusive
0x1800f4160  lea     rdx, [r15+18h]
0x1800f4164  lea     rcx, [rsp+548h+var_3E8]
0x1800f416c  call    ??4?$ConcurrentMap@T_NET_LUID_LH@@V?$list@UInterfaceNotification@Notify@Common@Service@HNS@@V?$allocator@UInterfaceNotification@Notify@Common@Service@HNS@@@std@@@std@@UNET_LUID_Comparator@@@Common@Service@HNS@@QEAAAEAV0123@$$QEAV0123@@Z; HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,std::list<HNS::Service::Common::Notify::InterfaceNotification>,NET_LUID_Comparator>::operator=(HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,std::list<HNS::Service::Common::Notify::InterfaceNotification>,NET_LUID_Comparator> &&)
0x1800f4171  test    rdi, rdi
0x1800f4174  jz      short loc_1800F417F
0x1800f4176  mov     rcx, rdi; SRWLock
0x1800f4179  call    cs:__imp_ReleaseSRWLockExclusive
0x1800f417f  lea     r12, [r15+648h]
0x1800f4186  mov     [rsp+548h+var_4E8], r12
0x1800f418b  mov     rcx, [rsp+548h]; this
0x1800f4193  mov     rax, [r12]
0x1800f4197  cmp     dword ptr [rax+50h], 2
0x1800f419b  jnz     loc_1800F4E2B
0x1800f41a1  mov     [rsp+548h+var_4B8], r12
0x1800f41a9  mov     rax, [rsp+548h+var_3D0]
0x1800f41b1  mov     rsi, [rax]
0x1800f41b4  mov     [rsp+548h+var_448], rax
0x1800f41bc  mov     [rsp+548h+var_4C0], rsi
0x1800f41c4  cmp     rsi, [rsp+548h+var_448]
0x1800f41cc  jz      loc_1800F4D5E
0x1800f41d2  mov     rdi, [rsi+20h]
0x1800f41d6  mov     [rsp+548h+var_4F8], rdi
0x1800f41db  mov     rcx, cs:qword_180399BB8
0x1800f41e2  mov     eax, [rcx]
0x1800f41e4  cmp     eax, 5
0x1800f41e7  jbe     short loc_1800F422B
0x1800f41e9  mov     [rsp+548h+var_4E0], rdi
0x1800f41ee  mov     dword ptr [rsp+548h+var_500], 10Ch
0x1800f41f6  mov     [rsp+548h+var_4B0], r13
0x1800f41fe  lea     rax, [rsp+548h+var_4E0]
0x1800f4203  mov     [rsp+548h+var_518], rax
0x1800f4208  lea     rax, [rsp+548h+var_500]
0x1800f420d  mov     [rsp+548h+var_520], rax
0x1800f4212  lea     rax, [rsp+548h+var_4B0]
0x1800f421a  mov     [rsp+548h+var_528], rax
0x1800f421f  lea     rdx, unk_180337F2A
0x1800f4226  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800f422b  lea     rdx, [rsi+28h]
0x1800f422f  lea     rcx, [rsp+548h+var_3C0]
0x1800f4237  call    ??0?$list@UInterfaceNotification@Notify@Common@Service@HNS@@V?$allocator@UInterfaceNotification@Notify@Common@Service@HNS@@@std@@@std@@QEAA@AEBV01@@Z; std::list<HNS::Service::Common::Notify::InterfaceNotification>::list<HNS::Service::Common::Notify::InterfaceNotification>(std::list<HNS::Service::Common::Notify::InterfaceNotification> const &)
0x1800f423c  nop
0x1800f423d  mov     rcx, [rsp+548h+var_3C0]
0x1800f4245  mov     rax, [rcx]
0x1800f4248  mov     [rsp+548h+var_4B0], rax
0x1800f4250  mov     [rsp+548h+var_438], rcx
0x1800f4258  mov     rbx, [rsp+548h+var_4B0]
0x1800f4260  cmp     rbx, [rsp+548h+var_438]
0x1800f4268  jz      loc_1800F4CD3
0x1800f426e  inc     [rsp+548h+var_4CC]
0x1800f4272  mov     ecx, [rbx+10h]
0x1800f4275  sub     ecx, 1
0x1800f4278  jz      loc_1800F48C7
0x1800f427e  sub     ecx, 1
0x1800f4281  jz      loc_1800F4699
0x1800f4287  cmp     ecx, 2
0x1800f428a  jnz     loc_1800F4CBB
0x1800f4290  mov     edx, ecx
0x1800f4292  mov     r8d, 86h
0x1800f4298  lea     rcx, [rsp+548h+var_468]
0x1800f42a0  call    ?GetAdapterAddresses@IPHelper@@SA?AV?$unique_ptr@U_IP_ADAPTER_ADDRESSES_LH@@UAutoFree@@@std@@KK@Z; IPHelper::GetAdapterAddresses(ulong,ulong)
0x1800f42a5  nop
0x1800f42a6  mov     rcx, [rsp+548h+Block]
0x1800f42ae  jmp     short loc_1800F42BD
0x1800f42b0  cmp     [rcx+0E0h], rdi
0x1800f42b7  jz      short loc_1800F42C2
0x1800f42b9  mov     rcx, [rcx+8]
0x1800f42bd  test    rcx, rcx
0x1800f42c0  jnz     short loc_1800F42B0
0x1800f42c2  mov     [rsp+548h+var_4E0], rcx
0x1800f42c7  test    rcx, rcx
0x1800f42ca  jnz     short loc_1800F4333
0x1800f42cc  mov     rcx, cs:qword_180399BB8
0x1800f42d3  mov     eax, [rcx]
0x1800f42d5  cmp     eax, 5
0x1800f42d8  jbe     short loc_1800F4317
0x1800f42da  mov     [rsp+548h+var_4E0], rdi
0x1800f42df  mov     dword ptr [rsp+548h+var_500], 125h
0x1800f42e7  mov     [rsp+548h+var_4F0], r13
0x1800f42ec  lea     rax, [rsp+548h+var_4E0]
0x1800f42f1  mov     [rsp+548h+var_518], rax
0x1800f42f6  lea     rax, [rsp+548h+var_500]
0x1800f42fb  mov     [rsp+548h+var_520], rax
0x1800f4300  lea     rax, [rsp+548h+var_4F0]
0x1800f4305  mov     [rsp+548h+var_528], rax
0x1800f430a  lea     rdx, unk_180337F74
0x1800f4311  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800f4316  nop
0x1800f4317  mov     rcx, [rsp+548h+Block]; Block
0x1800f431f  test    rcx, rcx
0x1800f4322  jz      loc_1800F4CBB
0x1800f4328  call    cs:__imp_free
0x1800f432e  jmp     loc_1800F4CBB
0x1800f4333  mov     r10, cs:qword_180399BB8
0x1800f433a  mov     eax, [r10]
0x1800f433d  cmp     eax, 5
0x1800f4340  jbe     loc_1800F440C
0x1800f4346  mov     [rsp+548h+var_4F0], rdi
0x1800f434b  mov     rdx, [rcx+48h]
0x1800f434f  mov     [rsp+548h+var_4A0], 12Fh
0x1800f435a  lea     rax, [rsp+548h+var_4F0]
0x1800f435f  mov     [rsp+548h+var_58], rax
0x1800f4367  mov     [rsp+548h+var_50], 8
0x1800f4373  test    rdx, rdx
0x1800f4376  jz      short loc_1800F438F
0x1800f4378  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f437c  inc     rax
0x1800f437f  cmp     [rdx+rax*2], r14w
0x1800f4384  jnz     short loc_1800F437C
0x1800f4386  lea     eax, ds:2[rax*2]
0x1800f438d  jmp     short loc_1800F439B
0x1800f438f  lea     rdx, unk_1802E2A80
0x1800f4396  mov     eax, 2
0x1800f439b  mov     [rsp+548h+var_68], rdx
0x1800f43a3  mov     [rsp+548h+var_60], eax
0x1800f43aa  mov     [rsp+548h+var_5C], r14d
0x1800f43b2  lea     rax, [rsp+548h+var_4A0]
0x1800f43ba  mov     [rsp+548h+var_78], rax
0x1800f43c2  mov     [rsp+548h+var_70], 4
0x1800f43ce  mov     [rsp+548h+var_88], r13
0x1800f43d6  mov     [rsp+548h+var_80], 44h ; 'D'
0x1800f43e2  lea     rax, [rsp+548h+var_A8]
0x1800f43ea  mov     [rsp+548h+var_520], rax
0x1800f43ef  mov     dword ptr [rsp+548h+var_528], 6
0x1800f43f7  xor     r9d, r9d
0x1800f43fa  xor     r8d, r8d
0x1800f43fd  lea     rdx, unk_180337C55
0x1800f4404  mov     rcx, r10
0x1800f4407  call    _tlgWriteTransfer_EventWriteTransfer
0x1800f440c  xor     edx, edx; Val
0x1800f440e  mov     r8d, 118h; Size
0x1800f4414  lea     rcx, [rsp+548h+VersionInformation.dwMajorVersion]; void *
0x1800f441c  call    memset_0
0x1800f4421  mov     [rsp+548h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800f442c  lea     rcx, [rsp+548h+VersionInformation]; lpVersionInformation
0x1800f4434  call    cs:__imp_GetVersionExW
0x1800f443a  test    eax, eax
0x1800f443c  jz      loc_1800F4E43
0x1800f4442  cmp     [rsp+548h+var_126], 1
0x1800f444a  jz      short loc_1800F4459
0x1800f444c  call    ?IsClientMultiSession@Common@Service@HNS@@YA_NXZ; HNS::Service::Common::IsClientMultiSession(void)
0x1800f4451  test    al, al
0x1800f4453  jz      loc_1800F4538
0x1800f4459  mov     al, [rbx+28h]
0x1800f445c  and     al, 1
0x1800f445e  neg     al
0x1800f4460  sbb     r12d, r12d
0x1800f4463  and     r12d, 2
0x1800f4467  add     r12d, 7
0x1800f446b  mov     dword ptr [rsp+548h+var_500], r12d
0x1800f4470  mov     rbx, [rsp+548h+var_4E8]
0x1800f4475  mov     rcx, [rbx]
0x1800f4478  xor     eax, eax
0x1800f447a  lock cmpxchg [rcx+3B0h], r14d
0x1800f4483  setnz   r8b
0x1800f4487  mov     edx, r12d
0x1800f448a  lea     rcx, [rsp+548h+var_4E0]
0x1800f448f  call    ?IsAdapterSuitableForMirroring@Core@Service@HNS@@YA_NAEAPEAU_IP_ADAPTER_ADDRESSES_LH@@W4NetworkType@@_N@Z; HNS::Service::Core::IsAdapterSuitableForMirroring(_IP_ADAPTER_ADDRESSES_LH * &,NetworkType,bool)
0x1800f4494  test    al, al
0x1800f4496  jz      loc_1800F4538
0x1800f449c  mov     r13, [rsp+548h+var_4E0]
0x1800f44a1  lea     r8, [r13+0E0h]
0x1800f44a8  mov     r9d, r12d
0x1800f44ab  lea     rdx, [rsp+548h+var_3B0]
0x1800f44b3  mov     rcx, [rbx]
0x1800f44b6  call    ?FindMirroredNetworks@NetworkEntityManager@Core@Service@HNS@@QEAA?AV?$shared_ptr@VBaseNetwork@Network@Service@HNS@@@std@@AEBT_NET_LUID_LH@@W4NetworkType@@@Z; HNS::Service::Core::NetworkEntityManager::FindMirroredNetworks(_NET_LUID_LH const &,NetworkType)
0x1800f44bb  mov     rbx, [rax]
0x1800f44be  mov     [rsp+548h+var_4F0], rbx
0x1800f44c3  mov     rbx, [rsp+548h+var_3A8]
0x1800f44cb  test    rbx, rbx
0x1800f44ce  jz      short loc_1800F4507
0x1800f44d0  or      eax, 0FFFFFFFFh
0x1800f44d3  lock xadd [rbx+8], eax
0x1800f44d8  cmp     eax, 1
0x1800f44db  jnz     short loc_1800F4507
0x1800f44dd  mov     rax, [rbx]
0x1800f44e0  mov     rcx, rbx
0x1800f44e3  mov     rax, [rax]
0x1800f44e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f44eb  or      eax, 0FFFFFFFFh
0x1800f44ee  lock xadd [rbx+0Ch], eax
0x1800f44f3  cmp     eax, 1
0x1800f44f6  jnz     short loc_1800F4507
0x1800f44f8  mov     rax, [rbx]
0x1800f44fb  mov     rcx, rbx
0x1800f44fe  mov     rax, [rax+8]
0x1800f4502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4507  cmp     [rsp+548h+var_4F0], r14
0x1800f450c  jnz     short loc_1800F4522
0x1800f450e  mov     r8d, r12d
0x1800f4511  mov     rdx, r13
0x1800f4514  mov     rcx, [rsp+548h+var_4E8]
0x1800f4519  mov     rcx, [rcx]
0x1800f451c  call    ?CreateMirroredNetwork@NetworkEntityManager@Core@Service@HNS@@QEAAXPEAU_IP_ADAPTER_ADDRESSES_LH@@W4NetworkType@@@Z; HNS::Service::Core::NetworkEntityManager::CreateMirroredNetwork(_IP_ADAPTER_ADDRESSES_LH *,NetworkType)
0x1800f4521  nop
0x1800f4522  cmp     dword ptr [r13+64h], 18h
0x1800f4527  jz      short loc_1800F4538
0x1800f4529  mov     rdx, r13; struct _IP_ADAPTER_ADDRESSES_LH *
0x1800f452c  mov     rcx, [r15+668h]; this
0x1800f4533  call    ?NotifyDNSServerChange@RegistryKeyNotificationManager@Core@Service@HNS@@QEAAXPEAU_IP_ADAPTER_ADDRESSES_LH@@@Z; HNS::Service::Core::RegistryKeyNotificationManager::NotifyDNSServerChange(_IP_ADAPTER_ADDRESSES_LH *)
0x1800f4538  lea     r13, [r15+620h]
0x1800f453f  lea     rdx, [rsp+548h+var_4F8]
0x1800f4544  mov     rcx, r13
0x1800f4547  call    ?Contains@?$ConcurrentMap@T_NET_LUID_LH@@U_GUID@@UNET_LUID_Comparator@@@Common@Service@HNS@@QEAA_NAEBT_NET_LUID_LH@@@Z; HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::Contains(_NET_LUID_LH const &)
0x1800f454c  test    al, al
0x1800f454e  jnz     loc_1800F467D
0x1800f4554  mov     rcx, [r15+658h]
0x1800f455b  add     rcx, 68h ; 'h'
0x1800f455f  lea     r12, [r15-68h]
0x1800f4563  test    r12, r12
0x1800f4566  jz      short loc_1800F45AE
0x1800f4568  lea     r9, [r15+570h]
0x1800f456f  mov     rbx, r9
0x1800f4572  jmp     short loc_1800F45C0
0x1800f4574  mov     rcx, [rsp+548h+Block]; Block
0x1800f457c  xor     r14d, r14d
0x1800f457f  test    rcx, rcx
0x1800f4582  jz      short loc_1800F458A
0x1800f4584  call    cs:__imp_free
0x1800f458a  mov     rsi, [rsp+548h+var_4C0]
0x1800f4592  mov     rdi, [rsp+548h+var_4F8]
0x1800f4597  mov     r12, [rsp+548h+var_4B8]
0x1800f459f  mov     [rsp+548h+var_4E8], r12
0x1800f45a4  mov     r15, [rsp+548h+var_4D8]
0x1800f45a9  jmp     loc_1800F4CB4
0x1800f45ae  mov     r9, r14
0x1800f45b1  mov     rbx, [rsp+548h+var_480]
0x1800f45b9  add     rbx, 570h
0x1800f45c0  lea     rax, ?OnNetworkInterfaceRemoved@NetworkNotificationManager@Core@Service@HNS@@AEAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z; HNS::Service::Core::NetworkNotificationManager::OnNetworkInterfaceRemoved(std::shared_ptr<HNS::Service::Events::Event> const &)
0x1800f45c7  mov     [rsp+548h+var_428], rax
0x1800f45cf  mov     [rsp+548h+var_420], r14d
0x1800f45d7  mov     eax, dword ptr [rsp+548h+var_3A8+4]
0x1800f45de  mov     [rsp+548h+var_41C], eax
0x1800f45e5  mov     [rsp+548h+var_520], rdi
0x1800f45ea  lea     rax, [rsp+548h+var_428]
0x1800f45f2  mov     [rsp+548h+var_528], rax
0x1800f45f7  mov     r8d, 1Ah
0x1800f45fd  lea     rdx, [rsp+548h+var_F0]
0x1800f4605  call    ??$SubscribeEvent@P8NetworkNotificationManager@Core@Service@HNS@@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z@?$FilteredEventManager@T_NET_LUID_LH@@UNET_LUID_Comparator@@@Events@Service@HNS@@QEAA?AU_GUID@@W4EventType@123@PEAVIEventHandleable@123@P8NetworkNotificationManager@Core@23@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@ZT_NET_LUID_LH@@@Z; HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(HNS::Service::Events::EventType,HNS::Service::Events::IEventHandleable *,bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &),_NET_LUID_LH)
0x1800f460a  mov     rcx, [r15+658h]
0x1800f4611  add     rcx, 68h ; 'h'
0x1800f4615  neg     r12
0x1800f4618  sbb     r9, r9
0x1800f461b  and     r9, rbx
0x1800f461e  lea     rax, ?OnNetworkAddressChanged@NetworkNotificationManager@Core@Service@HNS@@AEAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z; HNS::Service::Core::NetworkNotificationManager::OnNetworkAddressChanged(std::shared_ptr<HNS::Service::Events::Event> const &)
0x1800f4625  mov     [rsp+548h+var_418], rax
0x1800f462d  mov     [rsp+548h+var_410], r14d
0x1800f4635  mov     eax, [rsp+548h+var_E4]
0x1800f463c  mov     [rsp+548h+var_40C], eax
0x1800f4643  mov     [rsp+548h+var_520], rdi
0x1800f4648  lea     rax, [rsp+548h+var_418]
0x1800f4650  mov     [rsp+548h+var_528], rax
0x1800f4655  mov     r8d, 1Ch
0x1800f465b  lea     rdx, [rsp+548h+var_D0]
0x1800f4663  call    ??$SubscribeEvent@P8NetworkNotificationManager@Core@Service@HNS@@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@Z@?$FilteredEventManager@T_NET_LUID_LH@@UNET_LUID_Comparator@@@Events@Service@HNS@@QEAA?AU_GUID@@W4EventType@123@PEAVIEventHandleable@123@P8NetworkNotificationManager@Core@23@EAA_NAEBV?$shared_ptr@VEvent@Events@Service@HNS@@@std@@@ZT_NET_LUID_LH@@@Z; HNS::Service::Events::FilteredEventManager<_NET_LUID_LH,NET_LUID_Comparator>::SubscribeEvent<bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &)>(HNS::Service::Events::EventType,HNS::Service::Events::IEventHandleable *,bool (HNS::Service::Core::NetworkNotificationManager::*)(std::shared_ptr<HNS::Service::Events::Event> const &),_NET_LUID_LH)
0x1800f4668  mov     r8, rax
0x1800f466b  lea     rdx, [rsp+548h+var_4F8]
0x1800f4670  mov     rcx, r13
0x1800f4673  call    ??$Add@U_GUID@@@?$ConcurrentMap@T_NET_LUID_LH@@U_GUID@@UNET_LUID_Comparator@@@Common@Service@HNS@@QEAAXAEBT_NET_LUID_LH@@$$QEAU_GUID@@@Z; HNS::Service::Common::ConcurrentMap<_NET_LUID_LH,_GUID,NET_LUID_Comparator>::Add<_GUID>(_NET_LUID_LH const &,_GUID &&)
  ... truncated ...
```
