# HNS::Service::Network::Endpoint::Attach(ushort const *,_GUID,_GUID,bool)

- ea: `0x18014c5dc`
- end: `0x18014d986`
- name: `?Attach@Endpoint@Network@Service@HNS@@QEAAXPEBGU_GUID@@1_N@Z`
- size: `5034`
- prototype: `void __usercall(HNS::Service::Network::Endpoint *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, struct _GUID *__struct_ptr@<r8>, struct _GUID *__struct_ptr@<r9>, bool)`
- caller_count: `1`
- callee_count: `65`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180106458`

## callees

- `0x180001a00`
- `0x180001b3c`
- `0x180003b58`
- `0x180003c84`
- `0x18005f0c0`
- `0x18005ffa0`
- `0x18005ffb8`
- `0x18005ffc4`
- `0x180061240`
- `0x180064754`
- `0x180064814`
- `0x180064b4c`
- `0x180065d70`
- `0x1800666b4`
- `0x1800677fc`
- `0x180067c00`
- `0x180069104`
- `0x18006c530`
- `0x18006ea40`
- `0x180071c70`
- `0x1800759d8`
- `0x180075aac`
- `0x180077db0`
- `0x18007e864`
- `0x18007f05c`
- `0x18007f21c`
- `0x1800a01c8`
- `0x1800b30c4`
- `0x1800b5c7c`
- `0x1800b65d8`
- `0x1800c7aa8`
- `0x1800cfadc`
- `0x1800d2178`
- `0x1800d22b8`
- `0x1800d44b8`
- `0x1800d4834`
- `0x1800d8ccc`
- `0x1800d8ed8`
- `0x1800ee458`
- `0x1800f8b5c`
- `0x180100d8c`
- `0x180108a88`
- `0x1801092f0`
- `0x180109ed4`
- `0x180112480`
- `0x180114da8`
- `0x180124c34`
- `0x180146ea4`
- `0x180146fb4`
- `0x1801474a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18014d235`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18014d235`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18014d221`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18014d221`

## string_xrefs

- `0x18014d7ec`: `onecore\vm\dv\net\hns\service\entity\endpoint\endpoint.cpp`
- `0x18014d8ad`: `onecore\vm\dv\net\hns\service\entity\endpoint\endpoint.cpp`
- `0x18014d8c5`: `onecore\vm\dv\net\hns\service\entity\endpoint\endpoint.cpp`
- `0x18014d8dd`: `onecore\vm\dv\net\hns\service\entity\endpoint\endpoint.cpp`
- `0x18014d8f8`: `onecore\vm\dv\net\hns\service\entity\endpoint\endpoint.cpp`
- `0x18014d92a`: `onecore\vm\dv\net\hns\service\entity\endpoint\endpoint.cpp`
- `0x18014d942`: `onecore\vm\dv\net\hns\service\entity\endpoint\endpoint.cpp`
- `0x18014d974`: `onecore\vm\dv\net\hns\service\entity\endpoint\endpoint.cpp`
- `0x18014d7e0`: `Mirrored network endpoint cannot be attached without an associated GuestNetworkService present.`
- `0x18014c634`: `HNS::Service::Network::Endpoint::Attach`
- `0x18014d72d`: `HNS::Service::Network::Endpoint::Attach`
- `0x18014d858`: `HNS::Service::Network::Endpoint::Attach`
- `0x18014d83e`: `AlreadyAttached`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall HNS::Service::Network::Endpoint::Attach(
        HNS::Service::Network::Endpoint *this,
        unsigned __int16 *a2,
        struct _GUID *a3,
        struct _GUID *a4,
        char a5)
{
  volatile signed __int32 *v7; // rdi
  volatile signed __int32 *v8; // r12
  int v9; // ebx
  __int64 String; // rax
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // rbx
  struct _GUID v13; // xmm6
  struct _GUID v14; // xmm7
  struct _GUID v15; // xmm8
  __int128 *v16; // r9
  __int64 v17; // rdx
  unsigned __int16 *v18; // rax
  char v19; // si
  __int64 v20; // r8
  void **v21; // rsi
  size_t v22; // rbx
  __int64 v23; // rbx
  struct _GUID *Activity; // rax
  volatile signed __int32 *v25; // rbx
  __int128 v26; // kr00_16
  volatile signed __int32 *v27; // rbx
  volatile signed __int32 *v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rax
  volatile signed __int32 *v31; // rbx
  __int64 v32; // rsi
  __int64 v33; // rbx
  GUID v34; // xmm6
  __int64 EventRoute; // rax
  void *v36; // rbx
  HNS::Service::Entity::Common::GuestNetworkService *v37; // rsi
  volatile signed __int32 *v38; // rbx
  __int64 v40; // r12
  unsigned int v41; // r12d
  unsigned __int16 *v42; // rax
  unsigned int v43; // esi
  unsigned int v44; // eax
  volatile signed __int32 *v45; // rsi
  int v46; // r12d
  int v47; // r8d
  int v48; // r9d
  __int64 v49; // rax
  volatile signed __int32 *v50; // rsi
  HNS::Service::Entity::Common::GuestNetworkService *v51; // rsi
  __int64 v52; // rdx
  int v53; // r12d
  int v54; // r8d
  int v55; // r9d
  volatile signed __int32 *v56; // rbx
  volatile signed __int32 *v57; // rbx
  __int64 v58; // rbx
  GUID v59; // xmm6
  __int64 v60; // rbx
  GUID v61; // xmm6
  unsigned int v62; // eax
  int v63; // edi
  __int64 v64; // rbx
  __int64 v65; // rax
  __int64 v66; // r8
  int v67; // r9d
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  int v71; // [rsp+28h] [rbp-E0h]
  int v72; // [rsp+28h] [rbp-E0h]
  char *v73; // [rsp+30h] [rbp-D8h]
  FseDriverHelper *v74[2]; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v75[4]; // [rsp+88h] [rbp-80h] BYREF
  struct _GUID v76; // [rsp+98h] [rbp-70h] BYREF
  void *Buf1[2]; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v78; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int16 *v79[2]; // [rsp+C8h] [rbp-40h] BYREF
  void *Src; // [rsp+D8h] [rbp-30h]
  HNS::Service::Entity::Common::GuestNetworkService *v81; // [rsp+E8h] [rbp-20h] BYREF
  volatile signed __int32 *v82; // [rsp+F0h] [rbp-18h]
  volatile signed __int32 *v83; // [rsp+F8h] [rbp-10h] BYREF
  struct _GUID v84; // [rsp+108h] [rbp+0h] BYREF
  struct _GUID v85; // [rsp+118h] [rbp+10h] BYREF
  __int128 v86; // [rsp+128h] [rbp+20h] BYREF
  __int128 v87; // [rsp+138h] [rbp+30h]
  struct _GUID v88; // [rsp+148h] [rbp+40h] BYREF
  struct _GUID v89; // [rsp+168h] [rbp+60h] BYREF
  __int128 v90; // [rsp+178h] [rbp+70h] BYREF
  unsigned __int16 *v91; // [rsp+188h] [rbp+80h]
  unsigned __int64 v92; // [rsp+190h] [rbp+88h]
  HNSObject *v93; // [rsp+1B0h] [rbp+A8h]
  _QWORD v94[2]; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v95; // [rsp+1C8h] [rbp+C0h] BYREF
  __m128i si128; // [rsp+1D8h] [rbp+D0h]
  _OWORD v97[6]; // [rsp+1E8h] [rbp+E0h] BYREF
  int v98; // [rsp+248h] [rbp+140h]
  void *v99[2]; // [rsp+250h] [rbp+148h] BYREF
  unsigned __int64 v100; // [rsp+260h] [rbp+158h]
  unsigned __int64 v101; // [rsp+268h] [rbp+160h]
  _BYTE v102[56]; // [rsp+278h] [rbp+170h] BYREF
  HNSObject *v103; // [rsp+2B0h] [rbp+1A8h]
  _BYTE v104[56]; // [rsp+2B8h] [rbp+1B0h] BYREF
  HNSObject *v105; // [rsp+2F0h] [rbp+1E8h]
  _QWORD v106[42]; // [rsp+2F8h] [rbp+1F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4C0h] [rbp+3B8h]

  *(_QWORD *)&v78 = a4;
  Buf1[0] = a3;
  Src = a2;
  HNSTraceProvider::TraceEnter("HNS::Service::Network::Endpoint::Attach", 0x6BFu);
  HNSObject::Get<_GUID>(*((_QWORD *)this + 101), &v76, (char *)this + 752);
  wil::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v106,
    "EndpointAttachVNic");
  v106[0] = &HNSTraceProvider::EndpointAttachVNic::`vftable';
  HNSTraceProvider::EndpointAttachVNic::StartActivity((HNSTraceProvider::EndpointAttachVNic *)v106, &v76, a2);
  HNS::Service::Interface::IEntity::ValidateAndThrow(this);
  *((_DWORD *)this + 314) = 2;
  if ( (unsigned __int8)Property<unsigned long>::get((char *)this + 496) == 2
    || (unsigned __int8)Property<unsigned long>::get((char *)this + 496) == 3 )
  {
    v63 = qword_18039AA48;
    if ( *(_DWORD *)qword_18039AA48 > 5u && (unsigned __int8)tlgKeywordOn(qword_18039AA48, 0) )
    {
      v64 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v83, a2);
      v74[0] = (FseDriverHelper *)HNS::Service::Interface::IEntity::GetID(this, &v88);
      _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v79, L"AlreadyAttached");
      v75[0] = 1743;
      v65 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(Buf1, "HNS::Service::Network::Endpoint::Attach");
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
        v63,
        (unsigned int)&unk_18033BD14,
        v66,
        v67,
        v65,
        (__int64)v75,
        v66,
        (__int64)v74,
        v64);
    }
    v68 = wil::verify_hresult<long>(2151350292LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D1,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\endpoint\\endpoint.cpp",
      (const char *)v68,
      v71);
  }
  v7 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  v83 = v7;
  if ( v7 )
    _InterlockedIncrement(v7 + 4);
  if ( *((_BYTE *)this + 992) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D9,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\endpoint\\endpoint.cpp",
      (const char *)0x803B000FLL,
      v71);
  if ( (unsigned int)HNSObject::IsEqualType(v7) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6DA,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\endpoint\\endpoint.cpp",
      (const char *)0x803B000CLL,
      v71);
  if ( *((_QWORD *)this + 233) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6DF,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\endpoint\\endpoint.cpp",
      (const char *)0x803B0014LL,
      v71);
  memset_0(v94, 0, 0xB8u);
  v95 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v95) = 0;
  v97[0] = 0;
  v97[1] = si128;
  LOWORD(v97[0]) = 0;
  memset(&v97[2], 0, 64);
  v98 = 0;
  v94[0] = &HNS::Service::Resource::VmPortResource::VariableSet::`vftable';
  *(_OWORD *)v99 = 0;
  v100 = 0;
  v101 = 7;
  LOWORD(v99[0]) = 0;
  HNSObject::Get<_GUID>(*((_QWORD *)this + 101), &v76, (char *)this + 752);
  GuidToString(&v90, &v76, 0);
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  v74[0] = (FseDriverHelper *)v8;
  if ( v8 )
    _InterlockedIncrement(v8 + 4);
  v86 = 0;
  v87 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v86, L"PortFriendlyName", 0x10u);
  v9 = HNSObject::PropertyExists(v8, &v86);
  std::wstring::~wstring(&v86);
  if ( !v9 )
  {
    v86 = 0;
    v87 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v86, L"PortFriendlyName", 0x10u);
    String = HNSObject::GetString(v8, &v88, &v86);
    std::wstring::operator=(&v90, String);
    std::wstring::~wstring(&v88);
    std::wstring::~wstring(&v86);
  }
  v11 = -1;
  v12 = -1;
  do
    ++v12;
  while ( *((_WORD *)Src + v12) );
  HNSObject::Get<_GUID>(*((_QWORD *)this + 101), &v76, (char *)this + 752);
  v13 = v76;
  v14 = *HNS::Service::Network::Endpoint::GetNetworkID(this, &v88);
  v15 = *HNS::Service::Network::BaseNetwork::SwitchGuid(*((HNS::Service::Network::BaseNetwork **)this + 122), &v89);
  HNSObject::Get<std::wstring>(*((_QWORD *)this + 189), &v86, (char *)this + 1456);
  v16 = &v86;
  if ( *((_QWORD *)&v87 + 1) > 7u )
    v16 = (__int128 *)v86;
  v17 = -1;
  do
    ++v17;
  while ( aEndpointPort[v17] );
  v18 = (unsigned __int16 *)&v90;
  if ( v92 > 7 )
    v18 = (unsigned __int16 *)v90;
  *(struct _GUID *)v75 = v13;
  v85 = v14;
  v78 = *(_OWORD *)v78;
  v84 = v15;
  *(_QWORD *)&v76.Data1 = v16;
  *(_QWORD *)v76.Data4 = v87;
  v81 = (HNS::Service::Entity::Common::GuestNetworkService *)L"Endpoint Port";
  v82 = (volatile signed __int32 *)v17;
  v79[0] = v18;
  v79[1] = v91;
  v19 = a5;
  HNS::Service::Resource::PortResource::VariableSet::Get(
    (unsigned int)v94,
    (unsigned int)v79,
    (unsigned int)&v81,
    (unsigned int)&v76,
    (__int64)&v84,
    (__int64)&v78,
    (__int64)&v85,
    (__int64)v75,
    a5,
    0,
    a5 ^ 1,
    1);
  if ( v12 > v101 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v99, v12, v20, Src);
  }
  else
  {
    v21 = v99;
    if ( v101 > 7 )
      v21 = (void **)v99[0];
    v100 = v12;
    v22 = 2 * v12;
    memmove_0(v21, Src, v22);
    *(_WORD *)((char *)v21 + v22) = 0;
    v19 = a5;
  }
  std::wstring::~wstring(&v86);
  if ( v8 )
    HNSObject::Release((HNSObject *)v8);
  std::wstring::~wstring(&v90);
  v23 = *((_QWORD *)this + 103);
  *(_QWORD *)v75 = v94;
  Activity = HNS::Service::Interface::IResourceable::GetActivity(
               (HNS::Service::Network::Endpoint *)((char *)this + 816),
               &v88);
  HNS::Service::Resource::ResourceManager::GetActivity(v23, &v76, Activity);
  HNS::Service::Resource::Activity::AllocateResource<23,HNS::Service::Resource::VmPortResource::VariableSet *>(
    *(_QWORD *)&v76.Data1,
    v74,
    v75);
  v25 = *(volatile signed __int32 **)v76.Data4;
  if ( *(_QWORD *)v76.Data4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v76.Data4 + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  v26 = *(_OWORD *)v74;
  *(_OWORD *)v74 = 0u;
  *((_QWORD *)this + 233) = v26;
  v27 = (volatile signed __int32 *)*((_QWORD *)this + 234);
  *((_QWORD *)this + 234) = *((_QWORD *)&v26 + 1);
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
    v28 = (volatile signed __int32 *)v74[1];
    if ( v74[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v74[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
        if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
      }
    }
  }
  v29 = *(_QWORD *)HNS::Service::Network::BaseNetwork::GetSwitch(*((_QWORD *)this + 122), &v84);
  *(_OWORD *)v74 = 0;
  v30 = *((_QWORD *)this + 234);
  if ( v30 )
    _InterlockedIncrement((volatile signed __int32 *)(v30 + 8));
  *(_OWORD *)v74 = *(_OWORD *)((char *)this + 1864);
  HNS::Service::Resource::SwitchResource::AddEndpointPort(v29, v74);
  v31 = *(volatile signed __int32 **)v84.Data4;
  if ( *(_QWORD *)v84.Data4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v84.Data4 + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  if ( !v19 )
  {
    HNS::Service::Events::VmsIfClient::Get();
    v32 = *(_QWORD *)v75;
    v33 = *((_QWORD *)this + 233);
    if ( (unsigned int)HNSObject::PropertyExists(*(_QWORD *)(v33 + 1560), v33 + 1504) )
    {
      v34 = GUID_NULL;
    }
    else
    {
      HNSObject::Get<_GUID>(*(_QWORD *)(v33 + 1560), &v84, v33 + 1504);
      v34 = v84;
    }
    HNSObject::Get<_GUID>(*((_QWORD *)this + 101), &v84, (char *)this + 752);
    HNSObject::Get<_GUID>(*(_QWORD *)(*((_QWORD *)this + 122) + 808LL), &v85, *((_QWORD *)this + 122) + 752LL);
    v76 = GUID_NULL;
    EventRoute = HNS::Service::Events::EventRoute::GetEventRoute(&v81, &v76, &v85, &v84);
    v84 = v34;
    *(_OWORD *)((char *)this + 1880) = *(_OWORD *)HNS::Service::Events::FilteredEventManager<_GUID,HNS::Service::Common::GuidLessThan>::SubscribeEvent(
                                                    (int)v32 + 16,
                                                    (unsigned int)&v88,
                                                    5,
                                                    1,
                                                    EventRoute,
                                                    (__int64)&v84);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  v36 = Buf1[0];
  if ( memcmp_0(Buf1[0], &GUID_NULL, 0x10u) )
  {
    v84 = (struct _GUID)*((_OWORD *)this + 85);
    HNSObject::Set<_GUID>(*((_QWORD *)this + 173), (char *)this + 1328, v36, *((unsigned int *)this + 344), &v84);
    if ( (unsigned int)HNSObject::PropertyExists(*((_QWORD *)this + 181), (char *)this + 1392) )
    {
      HNS::Service::Core::GuestNetworkServiceManager::GetInstance(&v76);
      HNSObject::Get<_GUID>(*((_QWORD *)this + 173), &v84, (char *)this + 1328);
      HNS::Service::Core::GuestNetworkServiceManager::FindFilterVirtualMachineId(*(_QWORD *)&v76.Data1, &v81, &v84);
      v37 = v81;
      if ( v81 )
      {
        HNSObject::Get<_GUID>(*((_QWORD *)v81 + 101), &v85, (char *)v81 + 752);
        v84 = (struct _GUID)*((_OWORD *)this + 89);
        HNSObject::Set<_GUID>(*((_QWORD *)this + 181), (char *)this + 1392, &v85, *((unsigned int *)this + 360), &v84);
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 122) + 184LL))(*((_QWORD *)this + 122))
          && !(unsigned int)HNSObject::PropertyExists(*((_QWORD *)v37 + 310), (char *)v37 + 2424)
          && (unsigned int)Property<unsigned long>::get((char *)v37 + 2424) )
        {
          HNS::Service::Network::BaseNetwork::GetInterfaceConstraint(*((_QWORD *)this + 122), Buf1);
          v38 = (volatile signed __int32 *)Buf1[0];
          if ( !Buf1[0] )
          {
            v69 = wil::verify_hresult<long>(2151350284LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x731,
              (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\endpoint\\endpoint.cpp",
              (const char *)v69,
              (int)"Mirrored network endpoint is missing required interface constraints.",
              v73);
          }
          *(void **)v75 = Buf1[0];
          _InterlockedIncrement((volatile signed __int32 *)Buf1[0] + 4);
          v84 = GUID_NULL;
          v85 = *(struct _GUID *)wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(
                                   &v88,
                                   (__int64)L"InterfaceGuid");
          Property<_GUID>::Property<_GUID>(&v90, &v85, v75, &v84);
          if ( !(unsigned int)HNSObject::PropertyExists(v93, &v90)
            && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 122) + 496LL))(*((_QWORD *)this + 122)) )
          {
            HNSObject::Get<_GUID>(v93, &v84, &v90);
            HNSObject::Get<_GUID>(*((_QWORD *)this + 101), &v85, (char *)this + 752);
            HNS::Service::Entity::Common::GuestNetworkService::AddMirroredInterface(v37, &v85, &v84);
          }
          if ( *((_BYTE *)this + 993) )
          {
            if ( (unsigned int)HNSObject::PropertyExists(*((_QWORD *)v37 + 310), (char *)v37 + 2424)
              || (unsigned int)Property<unsigned long>::get((char *)v37 + 2424) != 2 )
            {
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x746,
                (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\endpoint\\endpoint.cpp",
                (const char *)0x803B0015LL,
                v72);
            }
            *(_QWORD *)&v78 = v38;
            if ( v38 )
            {
              v40 = (__int64)(v38 + 4);
              _InterlockedIncrement(v38 + 4);
            }
            else
            {
              v40 = 16;
            }
            v84 = GUID_NULL;
            v85 = *(struct _GUID *)wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(
                                     &v89,
                                     (__int64)L"InterfaceIndex");
            Property<_GUID>::Property<_GUID>(v104, &v85, &v78, &v84);
            *(_QWORD *)v75 = v38;
            if ( v38 )
              _InterlockedIncrement((volatile signed __int32 *)v40);
            v84 = GUID_NULL;
            v85 = *(struct _GUID *)wil::basic_zstring_view<unsigned short>::basic_zstring_view<unsigned short>(
                                     &v88,
                                     (__int64)L"InterfaceMediaType");
            Property<_GUID>::Property<_GUID>(v102, &v85, v75, &v84);
            v41 = 0;
            if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 122) + 496LL))(*((_QWORD *)this + 122)) )
            {
              wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_WSL_OpenVPN_Fix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Netsec_WSL_OpenVPN_Fix>::GetImpl'::`2'::impl);
              v41 = 1;
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Netsec_WSL_OpenVPN_Fix>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Netsec_WSL_OpenVPN_Fix>::GetImpl'::`2'::impl)
              && (unsigned __int8)Property<unsigned char>::get((char *)this + 1776) )
            {
              v41 |= 2u;
            }
            if ( (unsigned int)HNSObject::PropertyExists(v105, v104)
              || (unsigned int)HNSObject::PropertyExists(v103, v102) )
            {
              v70 = wil::verify_hresult<long>(2151350284LL);
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x773,
                (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\endpoint\\endpoint.cpp",
                (const char *)v70,
                (int)"Mirrored network endpoint is missing required interface constraints.",
                v73);
            }
            LODWORD(v78) = HNS::Service::Network::Endpoint::GetIsolationFromPolicy(this);
            v74[0] = *(FseDriverHelper **)FseDriverHelper::GetInstance(&v85);
            HNSObject::Get<std::wstring>(*((_QWORD *)this + 189), &v86, (char *)this + 1456);
            v42 = (unsigned __int16 *)&v86;
            if ( *((_QWORD *)&v87 + 1) > 7u )
              v42 = (unsigned __int16 *)v86;
            v79[0] = v42;
            v75[0] = Property<unsigned long>::get(v102);
            if ( (unsigned int)HNSObject::PropertyExists(*((_QWORD *)v37 + 302), (char *)v37 + 2360) )
              v43 = 0;
            else
              v43 = Property<unsigned long>::get((char *)v37 + 2360);
            HNSObject::Get<_GUID>(*((_QWORD *)this + 173), &v84, (char *)this + 1328);
            v44 = Property<unsigned long>::get(v104);
            FseDriverHelper::CreateNicPair(v74[0], v44, v78, &v84, v43, v75[0], v79[0], v41);
            std::wstring::~wstring(&v86);
            v45 = *(volatile signed __int32 **)v85.Data4;
            if ( *(_QWORD *)v85.Data4 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v85.Data4 + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
                if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
              }
            }
            if ( v103 )
              HNSObject::Release(v103);
            std::wstring::~wstring(v102);
            if ( v105 )
              HNSObject::Release(v105);
            std::wstring::~wstring(v104);
          }
          if ( v93 )
            HNSObject::Release(v93);
          std::wstring::~wstring(&v90);
          HNSObject::Release((HNSObject *)v38);
        }
        else
        {
          AcquireSRWLockExclusive((PSRWLOCK)v37 + 104);
          ++*((_DWORD *)v37 + 206);
          if ( v37 != (HNS::Service::Entity::Common::GuestNetworkService *)-832LL )
            ReleaseSRWLockExclusive((PSRWLOCK)v37 + 104);
          HNSObject::Get<_GUID>(*((_QWORD *)v37 + 101), &v85, (char *)v37 + 752);
          v84 = (struct _GUID)*((_OWORD *)this + 89);
          HNSObject::Set<_GUID>(*((_QWORD *)this + 181), (char *)this + 1392, &v85, *((unsigned int *)this + 360), &v84);
          v46 = qword_18039AA48;
          if ( *(_DWORD *)qword_18039AA48 > 5u )
          {
            v75[0] = *((_DWORD *)v37 + 206);
            HNSObject::Get<_GUID>(*((_QWORD *)this + 101), &v84, (char *)this + 752);
            v74[0] = (FseDriverHelper *)&v84;
            HNSObject::Get<_GUID>(*(_QWORD *)(*((_QWORD *)this + 122) + 808LL), &v85, *((_QWORD *)this + 122) + 752LL);
            v79[0] = (unsigned __int16 *)&v85;
            HNSObject::Get<_GUID>(*((_QWORD *)this + 173), &v89, (char *)this + 1328);
            Buf1[0] = &v89;
            HNSObject::Get<_GUID>(*((_QWORD *)this + 181), &v88, (char *)this + 1392);
            *(_QWORD *)&v78 = &v88;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              v46,
              (unsigned int)&unk_18033BCAD,
              v47,
              v48,
              (__int64)&v78,
              (__int64)Buf1,
              (__int64)v79,
              (__int64)v74,
              (__int64)v75);
          }
        }
      }
      else
      {
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 122) + 184LL))(*((_QWORD *)this + 122)) )
        {
          v62 = wil::verify_hresult<long>(2151350293LL);
          wil::details::in1diag3::Throw_HrMsg(
            retaddr,
            (void *)0x794,
            (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\endpoint\\endpoint.cpp",
            (const char *)v62,
            (int)"Mirrored network endpoint cannot be attached without an associated GuestNetworkService present.",
            v73);
        }
        HNSObject::Get<_GUID>(*((_QWORD *)this + 173), &v88, (char *)this + 1328);
        v49 = HNS::Service::Core::GuestNetworkServiceManager::FindOrCreate(*(_QWORD *)&v76.Data1, &v89, &v88);
        std::shared_ptr<HNS::Service::Core::NamespaceEntityManager>::operator=(&v81, v49);
        v50 = *(volatile signed __int32 **)v89.Data4;
        if ( *(_QWORD *)v89.Data4 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v89.Data4 + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
            if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
          }
        }
        v51 = v81;
        HNSObject::Get<_GUID>(*((_QWORD *)v81 + 101), &v89, (char *)v81 + 752);
        v88 = (struct _GUID)*((_OWORD *)this + 89);
        HNSObject::Set<_GUID>(*((_QWORD *)this + 181), (char *)this + 1392, &v89, *((unsigned int *)this + 360), &v88);
        v53 = qword_18039AA48;
        if ( *(_DWORD *)qword_18039AA48 > 5u )
        {
          v75[0] = *((_DWORD *)v51 + 206);
          HNSObject::Get<_GUID>(*((_QWORD *)this + 101), &v88, (char *)this + 752);
          v74[0] = (FseDriverHelper *)&v88;
          HNSObject::Get<_GUID>(*(_QWORD *)(*((_QWORD *)this + 122) + 808LL), &v89, *((_QWORD *)this + 122) + 752LL);
          v79[0] = (unsigned __int16 *)&v89;
          HNSObject::Get<_GUID>(*((_QWORD *)this + 173), &v84, (char *)this + 1328);
          Buf1[0] = &v84;
          HNSObject::Get<_GUID>(*((_QWORD *)this + 181), &v85, (char *)this + 1392);
          *(_QWORD *)&v78 = &v85;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
            v53,
            (unsigned int)&unk_18033BC47,
            v54,
            v55,
            (__int64)&v78,
            (__int64)Buf1,
            (__int64)v79,
            (__int64)v74,
            (__int64)v75);
        }
        LOBYTE(v52) = 3;
        HNS::Service::Entity::Common::GuestNetworkService::ChangeStateExisting(v51, v52);
      }
      v56 = v82;
      if ( v82 )
      {
        if ( _InterlockedExchangeAdd(v82 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
          if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
        }
      }
      v57 = *(volatile signed __int32 **)v76.Data4;
      if ( *(_QWORD *)v76.Data4 )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v76.Data4 + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
          if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
        }
      }
    }
  }
  v58 = *((_QWORD *)this + 233);
  if ( (unsigned int)HNSObject::PropertyExists(*(_QWORD *)(v58 + 1560), v58 + 1504) )
  {
    v59 = GUID_NULL;
  }
  else
  {
    HNSObject::Get<_GUID>(*(_QWORD *)(v58 + 1560), &v88, v58 + 1504);
    v59 = v88;
  }
  v86 = 0;
  v87 = 0u;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v86, L"SwitchPortId", 0xCu);
  v88 = v59;
  HNS::Service::Interface::IEntity::AddAdditionalParam<_GUID>(this, &v86, &v88);
  v60 = *((_QWORD *)this + 233);
  if ( (unsigned int)HNSObject::PropertyExists(*(_QWORD *)(v60 + 1624), v60 + 1568) )
  {
    v61 = GUID_NULL;
  }
  else
  {
    HNSObject::Get<_GUID>(*(_QWORD *)(v60 + 1624), &v88, v60 + 1568);
    v61 = v88;
  }
  v86 = 0;
  v87 = 0u;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v86, L"SwitchId", 8u);
  v88 = v61;
  HNS::Service::Interface::IEntity::AddAdditionalParam<_GUID>(this, &v86, &v88);
  v74[0] = (FseDriverHelper *)&v86;
  v86 = 0;
  v87 = 0u;
  do
    ++v11;
  while ( *((_WORD *)Src + v11) );
  std::wstring::_Construct<1,unsigned short const *>((char **)&v86, Src, v11);
  v90 = 0;
  v91 = 0;
  v92 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v90, L"VmSwitchNicName", 0xFu);
  HNS::Service::Interface::IEntity::AddAdditionalParam<std::wstring>(this, &v90, &v86);
  v75[0] = 2;
  v88 = (struct _GUID)*((_OWORD *)this + 33);
  HNSObject::Set<unsigned long>(*((_QWORD *)this + 69), (char *)this + 496, v75, *((unsigned int *)this + 136), &v88);
  wil::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v106);
  HNSTraceProvider::TraceSuccess("HNS::Service::Network::Endpoint::Attach", 0x7BBu);
  std::wstring::~wstring(v99);
  std::wstring::~wstring(v97);
  std::wstring::~wstring(&v95);
  if ( v7 )
    HNSObject::Release((HNSObject *)v7);
  v106[0] = &HNSTraceProvider::EndpointAttachVNic::`vftable';
  wil::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v106);
  wil::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v106);
}

```

## disassembly

```asm
0x18014c5dc  mov     rax, rsp
0x18014c5df  mov     [rax+18h], rbx
0x18014c5e3  push    rbp
0x18014c5e4  push    rsi
0x18014c5e5  push    rdi
0x18014c5e6  push    r12
0x18014c5e8  push    r13
0x18014c5ea  push    r14
0x18014c5ec  push    r15
0x18014c5ee  lea     rbp, [rax-3B8h]
0x18014c5f5  sub     rsp, 480h
0x18014c5fc  movaps  xmmword ptr [rax-48h], xmm6
0x18014c600  movaps  xmmword ptr [rax-58h], xmm7
0x18014c604  movaps  xmmword ptr [rax-68h], xmm8
0x18014c609  mov     rax, cs:__security_cookie
0x18014c610  xor     rax, rsp
0x18014c613  mov     [rbp+3B0h+var_70], rax
0x18014c61a  mov     qword ptr [rbp+3B0h+var_400], r9
0x18014c61e  mov     [rbp+3B0h+Buf1], r8
0x18014c622  mov     rbx, rdx
0x18014c625  mov     [rbp+3B0h+Src], rdx
0x18014c629  mov     r15, rcx
0x18014c62c  xor     r14d, r14d
0x18014c62f  mov     edx, 6BFh; unsigned int
0x18014c634  lea     rcx, aHnsServiceNetw_51; "HNS::Service::Network::Endpoint::Attach"
0x18014c63b  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x18014c640  nop
0x18014c641  lea     rsi, [r15+2F0h]
0x18014c648  mov     r8, rsi
0x18014c64b  lea     rdx, [rbp+3B0h+var_420]
0x18014c64f  mov     rcx, [rsi+38h]
0x18014c653  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x18014c658  nop
0x18014c659  lea     rdx, aEndpointattach_1; "EndpointAttachVNic"
0x18014c660  lea     rcx, [rbp+3B0h+var_1C0]
0x18014c667  call    ??0?$ActivityBase@VHNSTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18014c66c  lea     rax, ??_7EndpointAttachVNic@HNSTraceProvider@@6B@; const HNSTraceProvider::EndpointAttachVNic::`vftable'
0x18014c673  mov     [rbp+3B0h+var_1C0], rax
0x18014c67a  movaps  xmm0, xmmword ptr [rbp+3B0h+var_420.Data1]
0x18014c67e  movdqa  xmmword ptr [rbp+3B0h+var_420.Data1], xmm0
0x18014c683  mov     r8, rbx; unsigned __int16 *
0x18014c686  lea     rdx, [rbp+3B0h+var_420]; struct _GUID
0x18014c68a  lea     rcx, [rbp+3B0h+var_1C0]; this
0x18014c691  call    ?StartActivity@EndpointAttachVNic@HNSTraceProvider@@QEAAXU_GUID@@PEBG@Z; HNSTraceProvider::EndpointAttachVNic::StartActivity(_GUID,ushort const *)
0x18014c696  nop
0x18014c697  mov     rcx, r15; this
0x18014c69a  call    ?ValidateAndThrow@IEntity@Interface@Service@HNS@@QEAAXXZ; HNS::Service::Interface::IEntity::ValidateAndThrow(void)
0x18014c69f  mov     dword ptr [r15+4E8h], 2
0x18014c6aa  lea     rdi, [r15+1F0h]
0x18014c6b1  mov     rcx, rdi
0x18014c6b4  call    ?get@?$Property@K@@QEBA?BKXZ; Property<ulong>::get(void)
0x18014c6b9  nop
0x18014c6ba  cmp     al, 2
0x18014c6bc  jz      loc_18014D7FE
0x18014c6c2  mov     rcx, rdi
0x18014c6c5  call    ?get@?$Property@K@@QEBA?BKXZ; Property<ulong>::get(void)
0x18014c6ca  nop
0x18014c6cb  cmp     al, 3
0x18014c6cd  jz      loc_18014D7FE
0x18014c6d3  mov     rdi, [r15+8]
0x18014c6d7  mov     [rbp+3B0h+var_3C0], rdi
0x18014c6db  test    rdi, rdi
0x18014c6de  jz      short loc_18014C6E4
0x18014c6e0  lock inc dword ptr [rdi+10h]
0x18014c6e4  mov     rcx, [rbp+3B8h]; this
0x18014c6eb  cmp     [r15+3E0h], r14b
0x18014c6f2  jnz     loc_18014D8BF
0x18014c6f8  mov     rbx, [rbp+3B8h]
0x18014c6ff  mov     rcx, rdi
0x18014c702  call    ?IsEqualType@HNSObject@@QEBAJW4HNSObjectType@@@Z; HNSObject::IsEqualType(HNSObjectType)
0x18014c707  test    eax, eax
0x18014c709  jnz     loc_18014D8D7
0x18014c70f  mov     rcx, [rbp+3B8h]; this
0x18014c716  cmp     [r15+748h], r14
0x18014c71d  jnz     loc_18014D8F2
0x18014c723  xor     edx, edx; Val
0x18014c725  mov     r8d, 0B8h; Size
0x18014c72b  lea     rcx, [rbp+3B0h+var_300]; void *
0x18014c732  call    memset_0
0x18014c737  xorps   xmm0, xmm0
0x18014c73a  movups  [rbp+3B0h+var_2F0], xmm0
0x18014c741  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18014c749  movdqa  [rbp+3B0h+var_2E0], xmm1
0x18014c751  mov     word ptr [rbp+3B0h+var_2F0], r14w
0x18014c759  movups  [rbp+3B0h+var_2D0], xmm0
0x18014c760  movdqa  [rbp+3B0h+var_2C0], xmm1
0x18014c768  mov     word ptr [rbp+3B0h+var_2D0], r14w
0x18014c770  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014c777  movdqu  [rbp+3B0h+var_2B0], xmm0
0x18014c77f  movdqu  [rbp+3B0h+var_2A0], xmm0
0x18014c787  movdqu  [rbp+3B0h+var_290], xmm0
0x18014c78f  movdqu  [rbp+3B0h+var_280], xmm0
0x18014c797  mov     [rbp+3B0h+var_270], r14d
0x18014c79e  lea     rax, ??_7VariableSet@VmPortResource@Resource@Service@HNS@@6B@; const HNS::Service::Resource::VmPortResource::VariableSet::`vftable'
0x18014c7a5  mov     [rbp+3B0h+var_300], rax
0x18014c7ac  xorps   xmm0, xmm0
0x18014c7af  movups  xmmword ptr [rbp+3B0h+var_268], xmm0
0x18014c7b6  mov     [rbp+3B0h+var_258], r14
0x18014c7bd  mov     [rbp+3B0h+var_250], 7
0x18014c7c8  mov     word ptr [rbp+3B0h+var_268], r14w
0x18014c7d0  mov     r8, rsi
0x18014c7d3  lea     rdx, [rbp+3B0h+var_420]
0x18014c7d7  mov     rcx, [rsi+38h]
0x18014c7db  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x18014c7e0  nop
0x18014c7e1  xor     r8d, r8d
0x18014c7e4  lea     rdx, [rbp+3B0h+var_420]
0x18014c7e8  lea     rcx, [rbp+3B0h+var_340]
0x18014c7ec  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x18014c7f1  nop
0x18014c7f2  mov     r12, [r15+8]
0x18014c7f6  mov     [rsp+4B0h+var_450+8], r12
0x18014c7fb  test    r12, r12
0x18014c7fe  jz      short loc_18014C806
0x18014c800  lock inc dword ptr [r12+10h]
0x18014c806  xorps   xmm0, xmm0
0x18014c809  movups  [rbp+3B0h+var_390], xmm0
0x18014c80d  xorps   xmm1, xmm1
0x18014c810  movdqu  [rbp+3B0h+var_380], xmm1
0x18014c815  mov     r13d, 10h
0x18014c81b  mov     r8d, r13d
0x18014c81e  lea     rdx, aPortfriendlyna; "PortFriendlyName"
0x18014c825  lea     rcx, [rbp+3B0h+var_390]
0x18014c829  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18014c82e  lea     rdx, [rbp+3B0h+var_390]
0x18014c832  mov     rcx, r12
0x18014c835  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x18014c83a  mov     ebx, eax
0x18014c83c  lea     rcx, [rbp+3B0h+var_390]; void *
0x18014c840  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18014c845  test    ebx, ebx
0x18014c847  jnz     short loc_18014C89B
0x18014c849  xorps   xmm0, xmm0
0x18014c84c  movups  [rbp+3B0h+var_390], xmm0
0x18014c850  xorps   xmm1, xmm1
0x18014c853  movdqu  [rbp+3B0h+var_380], xmm1
0x18014c858  mov     r8d, r13d
0x18014c85b  lea     rdx, aPortfriendlyna; "PortFriendlyName"
0x18014c862  lea     rcx, [rbp+3B0h+var_390]
0x18014c866  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18014c86b  nop
0x18014c86c  lea     r8, [rbp+3B0h+var_390]
0x18014c870  lea     rdx, [rbp+3B0h+var_370]
0x18014c874  mov     rcx, r12
0x18014c877  call    ?GetString@HNSObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; HNSObject::GetString(std::wstring const &)
0x18014c87c  mov     rdx, rax
0x18014c87f  lea     rcx, [rbp+3B0h+var_340]
0x18014c883  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18014c888  lea     rcx, [rbp+3B0h+var_370]; void *
0x18014c88c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18014c891  nop
0x18014c892  lea     rcx, [rbp+3B0h+var_390]; void *
0x18014c896  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18014c89b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18014c89f  mov     rbx, r14
0x18014c8a2  mov     rax, [rbp+3B0h+Src]
0x18014c8a6  xor     ecx, ecx
0x18014c8a8  inc     rbx
0x18014c8ab  cmp     [rax+rbx*2], cx
0x18014c8af  jnz     short loc_18014C8A8
0x18014c8b1  mov     al, [rbp+3B0h+arg_20]
0x18014c8b7  xor     al, 1
0x18014c8b9  mov     byte ptr [rsp+4B0h+var_450], al
0x18014c8bd  mov     r8, rsi
0x18014c8c0  lea     rdx, [rbp+3B0h+var_420]
0x18014c8c4  mov     rcx, [rsi+38h]
0x18014c8c8  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x18014c8cd  nop
0x18014c8ce  movups  xmm6, xmmword ptr [rbp+3B0h+var_420.Data1]
0x18014c8d2  lea     rdx, [rbp+3B0h+var_370]; retstr
0x18014c8d6  mov     rcx, r15; this
0x18014c8d9  call    ?GetNetworkID@Endpoint@Network@Service@HNS@@QEAA?AU_GUID@@XZ; HNS::Service::Network::Endpoint::GetNetworkID(void)
0x18014c8de  movups  xmm7, xmmword ptr [rax]
0x18014c8e1  lea     rdx, [rbp+3B0h+var_350]; retstr
0x18014c8e5  mov     rcx, [r15+3D0h]; this
0x18014c8ec  call    ?SwitchGuid@BaseNetwork@Network@Service@HNS@@QEBA?AU_GUID@@XZ; HNS::Service::Network::BaseNetwork::SwitchGuid(void)
0x18014c8f1  movups  xmm8, xmmword ptr [rax]
0x18014c8f5  lea     rax, [r15+5B0h]
0x18014c8fc  mov     r8, rax
0x18014c8ff  lea     rdx, [rbp+3B0h+var_390]
0x18014c903  mov     rcx, [rax+38h]
0x18014c907  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x18014c90c  nop
0x18014c90d  mov     r10, qword ptr [rbp+3B0h+var_380]
0x18014c911  lea     r9, [rbp+3B0h+var_390]
0x18014c915  cmp     qword ptr [rbp+3B0h+var_380+8], 7
0x18014c91a  cmova   r9, qword ptr [rbp+3B0h+var_390]
0x18014c91f  mov     r8, cs:off_1802D1DD8; "Endpoint Port"
0x18014c926  mov     rdx, r14
0x18014c929  xor     esi, esi
0x18014c92b  inc     rdx
0x18014c92e  cmp     [r8+rdx*2], si
0x18014c933  jnz     short loc_18014C92B
0x18014c935  mov     rcx, [rbp+3B0h+var_330]
0x18014c93c  lea     rax, [rbp+3B0h+var_340]
0x18014c940  cmp     [rbp+3B0h+var_328], 7
0x18014c948  cmova   rax, qword ptr [rbp+3B0h+var_340]
0x18014c94d  movdqu  xmmword ptr [rbp+3B0h+var_430], xmm6
0x18014c952  movdqu  xmmword ptr [rbp+3B0h+var_3A0.Data1], xmm7
0x18014c957  mov     r11, qword ptr [rbp+3B0h+var_400]
0x18014c95b  movups  xmm0, xmmword ptr [r11]
0x18014c95f  movdqu  [rbp+3B0h+var_400], xmm0
0x18014c964  movdqu  xmmword ptr [rbp+3B0h+var_3B0.Data1], xmm8
0x18014c96a  mov     qword ptr [rbp+3B0h+var_420.Data1], r9
0x18014c96e  mov     qword ptr [rbp+3B0h+var_420.Data4], r10
0x18014c972  mov     [rbp+3B0h+var_3D0], r8
0x18014c976  mov     [rbp+3B0h+var_3C8], rdx
0x18014c97a  mov     [rbp+3B0h+var_3F0], rax
0x18014c97e  mov     [rbp+3B0h+var_3E8], rcx
0x18014c982  mov     [rsp+4B0h+var_458], 1
0x18014c987  mov     al, byte ptr [rsp+4B0h+var_450]
0x18014c98b  mov     [rsp+4B0h+var_460], al
0x18014c98f  mov     [rsp+4B0h+var_468], sil
0x18014c994  mov     sil, [rbp+3B0h+arg_20]
0x18014c99b  mov     [rsp+4B0h+var_470], sil
0x18014c9a0  lea     rax, [rbp+3B0h+var_430]
0x18014c9a4  mov     qword ptr [rsp+4B0h+var_478], rax
0x18014c9a9  lea     rax, [rbp+3B0h+var_3A0]
0x18014c9ad  mov     [rsp+4B0h+var_480], rax
0x18014c9b2  lea     rax, [rbp+3B0h+var_400]
0x18014c9b6  mov     [rsp+4B0h+var_488], rax
0x18014c9bb  lea     rax, [rbp+3B0h+var_3B0]
0x18014c9bf  mov     qword ptr [rsp+4B0h+var_490], rax
0x18014c9c4  lea     r9, [rbp+3B0h+var_420]
0x18014c9c8  lea     r8, [rbp+3B0h+var_3D0]
0x18014c9cc  lea     rdx, [rbp+3B0h+var_3F0]
0x18014c9d0  lea     rcx, [rbp+3B0h+var_300]
0x18014c9d7  call    ?Get@VariableSet@PortResource@Resource@Service@HNS@@SAXAEAU12345@V?$basic_zstring_view@G@wil@@11U_GUID@@222EEEE@Z; HNS::Service::Resource::PortResource::VariableSet::Get(HNS::Service::Resource::PortResource::VariableSet &,wil::basic_zstring_view<ushort>,wil::basic_zstring_view<ushort>,wil::basic_zstring_view<ushort>,_GUID,_GUID,_GUID,_GUID,uchar,uchar,uchar,uchar)
0x18014c9dc  cmp     rbx, [rbp+3B0h+var_250]
0x18014c9e3  ja      short loc_18014CA24
0x18014c9e5  lea     rsi, [rbp+3B0h+var_268]
0x18014c9ec  cmp     [rbp+3B0h+var_250], 7
0x18014c9f4  cmova   rsi, [rbp+3B0h+var_268]
0x18014c9fc  mov     [rbp+3B0h+var_258], rbx
0x18014ca03  add     rbx, rbx
0x18014ca06  mov     r8, rbx; Size
0x18014ca09  mov     rdx, [rbp+3B0h+Src]; Src
0x18014ca0d  mov     rcx, rsi; void *
0x18014ca10  call    memmove_0
0x18014ca15  xor     ecx, ecx
0x18014ca17  mov     [rbx+rsi], cx
0x18014ca1b  mov     sil, [rbp+3B0h+arg_20]
0x18014ca22  jmp     short loc_18014CA38
0x18014ca24  mov     r9, [rbp+3B0h+Src]
0x18014ca28  mov     rdx, rbx
0x18014ca2b  lea     rcx, [rbp+3B0h+var_268]
0x18014ca32  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18014ca37  nop
0x18014ca38  lea     rcx, [rbp+3B0h+var_390]; void *
0x18014ca3c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18014ca41  nop
0x18014ca42  test    r12, r12
0x18014ca45  jz      short loc_18014CA50
0x18014ca47  mov     rcx, r12; this
0x18014ca4a  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x18014ca4f  nop
0x18014ca50  lea     rcx, [rbp+3B0h+var_340]; void *
0x18014ca54  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18014ca59  mov     rbx, [r15+338h]
0x18014ca60  lea     rax, [rbp+3B0h+var_300]
0x18014ca67  mov     qword ptr [rbp+3B0h+var_430], rax
0x18014ca6b  lea     rcx, [r15+330h]; this
0x18014ca72  lea     rdx, [rbp+3B0h+var_370]; retstr
0x18014ca76  call    ?GetActivity@IResourceable@Interface@Service@HNS@@QEBA?AU_GUID@@XZ; HNS::Service::Interface::IResourceable::GetActivity(void)
0x18014ca7b  mov     r8, rax
0x18014ca7e  lea     rdx, [rbp+3B0h+var_420]
0x18014ca82  mov     rcx, rbx
0x18014ca85  call    ?GetActivity@ResourceManager@Resource@Service@HNS@@AEAA?AV?$shared_ptr@VActivity@Resource@Service@HNS@@@std@@AEBU_GUID@@@Z; HNS::Service::Resource::ResourceManager::GetActivity(_GUID const &)
0x18014ca8a  nop
0x18014ca8b  lea     r8, [rbp+3B0h+var_430]
0x18014ca8f  lea     rdx, [rsp+4B0h+var_450+8]
0x18014ca94  mov     rcx, qword ptr [rbp+3B0h+var_420.Data1]
0x18014ca98  call    ??$AllocateResource@$0BH@PEAUVariableSet@VmPortResource@Resource@Service@HNS@@@Activity@Resource@Service@HNS@@QEAA?A_PAEBQEAUVariableSet@VmPortResource@123@E@Z
0x18014ca9d  nop
0x18014ca9e  mov     rbx, qword ptr [rbp+3B0h+var_420.Data4]
0x18014caa2  xor     r12d, r12d
0x18014caa5  test    rbx, rbx
0x18014caa8  jz      short loc_18014CAE1
0x18014caaa  mov     eax, r14d
0x18014caad  lock xadd [rbx+8], eax
0x18014cab2  add     eax, r14d
0x18014cab5  jnz     short loc_18014CAE1
0x18014cab7  mov     rax, [rbx]
0x18014caba  mov     rcx, rbx
0x18014cabd  mov     rax, [rax]
0x18014cac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cac5  mov     eax, r14d
0x18014cac8  lock xadd [rbx+0Ch], eax
0x18014cacd  add     eax, r14d
0x18014cad0  jnz     short loc_18014CAE1
0x18014cad2  mov     rax, [rbx]
0x18014cad5  mov     rcx, rbx
0x18014cad8  mov     rax, [rax+8]
0x18014cadc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014cae1  mov     rax, [rsp+4B0h+var_450+8]
0x18014cae6  mov     rcx, [rsp+4B0h+var_440]
0x18014caeb  mov     [rsp+4B0h+var_450+8], r12
0x18014caf0  mov     [rsp+4B0h+var_440], r12
0x18014caf5  mov     [r15+748h], rax
0x18014cafc  mov     rbx, [r15+750h]
  ... truncated ...
```
