# HNS::Service::Core::LayeredEntityManager::ResolveLayeredResource(HNS::Service::Network::ResourceRequirement &,bool,_GUID)

- ea: `0x1800eaee4`
- end: `0x1800eb540`
- name: `?ResolveLayeredResource@LayeredEntityManager@Core@Service@HNS@@QEAA?AV?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@AEAUResourceRequirement@Network@34@_NU_GUID@@@Z`
- size: `1628`
- prototype: `__int64 __usercall@<rax>(HNS::Service::Core::LayeredEntityManager *this@<rcx>, __int64)`
- caller_count: `3`
- callee_count: `29`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800c0300`
- `0x1800c2984`
- `0x1800c8cc0`

## callees

- `0x1800026fc`
- `0x18005f0c0`
- `0x18005f560`
- `0x18005ffa0`
- `0x180061240`
- `0x1800666b4`
- `0x1800677fc`
- `0x18006c530`
- `0x1800759d8`
- `0x180075aac`
- `0x180076f1c`
- `0x18007e864`
- `0x18007f05c`
- `0x1800b3310`
- `0x1800b4804`
- `0x1800e8768`
- `0x1800e87ec`
- `0x1800e8b34`
- `0x1800e946c`
- `0x1800e97d4`
- `0x1800e9a18`
- `0x1800ea900`
- `0x1800eabd0`
- `0x1800eaee4`
- `0x1800eb68c`
- `0x1800ebeac`
- `0x18016a518`
- `0x18016ce04`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800eb185`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800eb489`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800eb185`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800eb489`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800eb145`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800eb374`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800eb145`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800eb374`
- `RPCRT4!UuidCreate` at `0x1800eb125`
- `RPCRT4!UuidCreate` at `0x1800eb125`

## string_xrefs

- `0x1800eaf24`: `HNS::Service::Core::LayeredEntityManager::ResolveLayeredResource`
- `0x1800eafe8`: `HNS::Service::Core::LayeredEntityManager::ResolveLayeredResource`
- `0x1800eb45b`: `HNS::Service::Core::LayeredEntityManager::ResolveLayeredResource`
- `0x1800eb20f`: `onecore\vm\dv\net\hns\service\core\layeredentitymanager.cpp`
- `0x1800eb52e`: `onecore\vm\dv\net\hns\service\core\layeredentitymanager.cpp`
- `0x1800eb2d9`: `HNS::Service::Core::EntityManager<class std::shared_ptr<class HNS::Service::Network::LayeredResource> >::Add`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
HNS::Service::Network::LayeredResource **__fastcall HNS::Service::Core::LayeredEntityManager::ResolveLayeredResource(
        RTL_SRWLOCK *this,
        HNS::Service::Network::LayeredResource **a2,
        _QWORD *a3,
        char a4,
        char *a5)
{
  _QWORD *v8; // rdx
  HNS::Service::Network::LayeredResource *v9; // rdi
  int v10; // esi
  int v11; // r8d
  int v12; // r9d
  __int64 *v13; // rbx
  __int64 **v14; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  volatile signed __int32 *v17; // rdi
  UUID *v18; // r12
  UUID v19; // xmm0
  RTL_SRWLOCK *v20; // r15
  RTL_SRWLOCK *v21; // r13
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // ebx
  PVOID Ptr; // rcx
  volatile signed __int32 *v26; // rbx
  RTL_SRWLOCK *v27; // rsi
  _QWORD *v28; // rbx
  __int64 *k; // rdi
  _QWORD *v30; // rax
  __int64 *v31; // rcx
  void *v32; // rax
  __int64 **v33; // rcx
  __int64 m; // rax
  __int64 *n; // rcx
  volatile signed __int32 *v36; // rbx
  unsigned int v38; // eax
  int v39; // [rsp+20h] [rbp-E0h]
  const char *v40; // [rsp+28h] [rbp-D8h]
  char v41; // [rsp+40h] [rbp-C0h] BYREF
  char v42; // [rsp+41h] [rbp-BFh] BYREF
  HNS::Service::Network::LayeredResource *v43[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+60h] [rbp-A0h] BYREF
  const char *v45; // [rsp+68h] [rbp-98h] BYREF
  HNS::Service::Network::LayeredResource ***v46; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v47[80]; // [rsp+80h] [rbp-80h] BYREF
  HNS::Service::Network::LayeredResource **v48; // [rsp+D0h] [rbp-30h] BYREF
  RTL_SRWLOCK *v49; // [rsp+D8h] [rbp-28h]
  char *v50; // [rsp+E0h] [rbp-20h]
  char *v51; // [rsp+E8h] [rbp-18h]
  UUID Uuid; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v53; // [rsp+100h] [rbp+0h]
  __int16 v54; // [rsp+108h] [rbp+8h]
  _QWORD v55[7]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD *v56; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  char v58; // [rsp+1C8h] [rbp+C8h] BYREF

  v58 = a4;
  v45 = (const char *)a2;
  HNSTraceProvider::TraceEnter("HNS::Service::Core::LayeredEntityManager::ResolveLayeredResource", 0x4Fu);
  if ( !*((_BYTE *)a3 + 72) || memcmp_0(a3 + 7, &GUID_NULL, 0x10u) )
  {
    v55[0] = &std::_Func_impl_no_alloc<_lambda_103108bddb783e77add5a08e75fa90e6_,bool,std::shared_ptr<HNS::Service::Network::LayeredResource> const &>::`vftable';
    v55[1] = a3;
    v56 = v55;
    HNS::Service::Core::EntityManager<std::shared_ptr<HNS::Service::Network::LayeredResource>>::Search(this, &Uuid, v55);
    if ( v56 )
    {
      v8 = v55;
      LOBYTE(v8) = v56 != v55;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v56 + 32LL))(v56, v8);
      v56 = 0;
    }
    v9 = *(HNS::Service::Network::LayeredResource **)&Uuid.Data1;
    if ( *(_QWORD *)&Uuid.Data1 )
    {
      v10 = qword_180399588;
      if ( *(_DWORD *)qword_180399588 > 5u )
      {
        HNSObject::Get<_GUID>(*(_QWORD *)(*(_QWORD *)&Uuid.Data1 + 808LL), &v48, *(_QWORD *)&Uuid.Data1 + 752LL);
        v46 = &v48;
        v44 = 94;
        v45 = "HNS::Service::Core::LayeredEntityManager::ResolveLayeredResource";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
          v10,
          (unsigned int)&unk_1803372BA,
          v11,
          v12,
          (__int64)&v45,
          (__int64)&v44,
          (__int64)&v46);
      }
      v13 = *(__int64 **)a3[17];
      while ( !*((_BYTE *)v13 + 25) )
      {
        HNS::Service::Network::LayeredResource::SetExtension(v9, (const struct _GUID *)((char *)v13 + 28), 1);
        v14 = (__int64 **)v13[2];
        if ( *((_BYTE *)v14 + 25) )
        {
          for ( i = (__int64 *)v13[1]; !*((_BYTE *)i + 25) && v13 == (__int64 *)i[2]; i = (__int64 *)i[1] )
            v13 = i;
          v13 = i;
        }
        else
        {
          v13 = (__int64 *)v13[2];
          for ( j = *v14; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v13 = j;
        }
      }
      *a2 = v9;
      a2[1] = *(HNS::Service::Network::LayeredResource **)Uuid.Data4;
      return a2;
    }
    v17 = *(volatile signed __int32 **)Uuid.Data4;
    if ( *(_QWORD *)Uuid.Data4 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)Uuid.Data4 + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
  }
  HNS::Service::Core::LayeredEntityManager::PruneOrphans((HNS::Service::Core::LayeredEntityManager *)this);
  if ( *((_BYTE *)a3 + 74) && *((_BYTE *)a3 + 75) )
  {
    v38 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x7F,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\layeredentitymanager.cpp",
      (const char *)v38,
      (int)"Can not require multiple layer types",
      v40);
  }
  v18 = (UUID *)(a3 + 7);
  if ( !memcmp_0(a3 + 7, &GUID_NULL, 0x10u) )
  {
    if ( !memcmp_0(a3 + 5, &GUID_NULL, 0x10u) )
    {
      Uuid = 0;
      UuidCreate(&Uuid);
      v19 = Uuid;
    }
    else
    {
      v19 = *(UUID *)(a3 + 5);
    }
    *v18 = v19;
  }
  v20 = this + 58;
  AcquireSRWLockExclusive(this + 58);
  v45 = (const char *)&this[58];
  v21 = this + 59;
  Uuid = *v18;
  LOBYTE(v53) = v58;
  std::_Tree<std::_Tmap_traits<_GUID,bool,HNS::Service::Common::GuidLessThan,std::allocator<std::pair<_GUID const,bool>>,0>>::emplace<std::pair<_GUID,bool>>(
    &this[59],
    &v48,
    &Uuid);
  if ( this != (RTL_SRWLOCK *)-464LL )
    ReleaseSRWLockExclusive(this + 58);
  if ( !a3[13] )
  {
    v23 = HNS::Service::Core::LayeredEntityManager::GenerateUniqueName(this, &v48, a3);
    std::wstring::operator=(a3 + 11, v23);
    std::wstring::~wstring(&v48);
  }
  HNS::Service::Core::LayeredEntityManager::CreateLayer(v22, v43, *((_QWORD *)this[52].Ptr + 13), a3);
  HNS::Service::Core::EntityManager<std::shared_ptr<HNS::Service::Network::LayeredResource>>::AddPending(this, v43);
  v41 = 0;
  v42 = 0;
  v48 = v43;
  v49 = this;
  v50 = &v41;
  v51 = &v42;
  *(_QWORD *)&Uuid.Data1 = retaddr;
  *(_QWORD *)Uuid.Data4 = "onecore\\vm\\dv\\net\\hns\\service\\core\\layeredentitymanager.cpp";
  v53 = 0;
  v54 = 161;
  wil::scope_exit_log__lambda_2a8909c5b028381e1ec1e61496ab2c8e___(v47, &Uuid, &v48);
  v48 = v43;
  v49 = (RTL_SRWLOCK *)a3;
  v50 = &v58;
  v51 = a5;
  v24 = wil::ResultFromException__lambda_95bd53eef9d662f0985c0dfe227ee387___(&v48);
  HNS::Service::Network::LayeredResource::LogEntityEvent(v43[0], v24, 1);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\core\\layeredentitymanager.cpp",
      (const char *)(unsigned int)v24,
      v39);
  HNSObject::Get<_GUID>(*((_QWORD *)v43[0] + 101), &v48, (char *)v43[0] + 752);
  HNS::Service::Core::LayeredEntityManager::RaiseLayeredEvent(this, 22, &v48);
  HNSObject::Get<_GUID>(*((_QWORD *)v43[0] + 101), &v48, (char *)v43[0] + 752);
  HNSTraceProvider::TraceSuccess(
    "HNS::Service::Core::EntityManager<class std::shared_ptr<class HNS::Service::Network::LayeredResource> >::Add",
    0x48u);
  HNS::Service::Core::Repository<std::shared_ptr<HNS::Service::Network::LayeredResource>>::Add<std::shared_ptr<HNS::Service::Network::LayeredResource> &>(
    &this[17],
    &v48,
    v43);
  v41 = 1;
  Ptr = this[47].Ptr;
  if ( v43[1] )
    _InterlockedIncrement((volatile signed __int32 *)v43[1] + 2);
  Uuid = *(UUID *)v43;
  HNS::Service::Core::StorageManager::Add((_DWORD)Ptr, 0, (unsigned int)&Uuid, 0);
  v26 = *(volatile signed __int32 **)Uuid.Data4;
  if ( *(_QWORD *)Uuid.Data4 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)Uuid.Data4 + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  v42 = 1;
  AcquireSRWLockExclusive(this + 58);
  v27 = this + 60;
  v28 = *(_QWORD **)v21[1].Ptr;
  while ( v28 != v27->Ptr )
  {
    if ( !memcmp_0(v18, (char *)v28 + 28, 0x10u) )
    {
      k = (__int64 *)v28[2];
      if ( *((_BYTE *)k + 25) )
      {
        v30 = v28;
        for ( k = (__int64 *)v28[1]; !*((_BYTE *)k + 25) && v30 == (_QWORD *)k[2]; k = (__int64 *)k[1] )
          v30 = k;
      }
      else
      {
        v31 = (__int64 *)*k;
        if ( !*(_BYTE *)(*k + 25) )
        {
          do
          {
            k = v31;
            v31 = (__int64 *)*v31;
          }
          while ( !*((_BYTE *)v31 + 25) );
        }
      }
      v32 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,HNSObjectProperty>>>::_Extract(
                      v27,
                      v28);
      operator delete(v32, (const struct std::nothrow_t *)0x30);
      v28 = k;
    }
    else
    {
      v33 = (__int64 **)v28[2];
      if ( *((_BYTE *)v33 + 25) )
      {
        for ( m = v28[1]; !*(_BYTE *)(m + 25) && v28 == *(_QWORD **)(m + 16); m = *(_QWORD *)(m + 8) )
          v28 = (_QWORD *)m;
        v28 = (_QWORD *)m;
      }
      else
      {
        v28 = (_QWORD *)v28[2];
        for ( n = *v33; !*((_BYTE *)n + 25); n = (__int64 *)*n )
          v28 = n;
      }
    }
  }
  v47[72] = 0;
  HNSTraceProvider::TraceSuccess("HNS::Service::Core::LayeredEntityManager::ResolveLayeredResource", 0xD0u);
  *a2 = v43[0];
  a2[1] = v43[1];
  *(_OWORD *)v43 = 0;
  if ( v20 )
    ReleaseSRWLockExclusive(v20);
  wil::details::lambda_call_log__lambda_d3a5b0357b0c169713c4abeb4617039d___::reset(v47);
  v36 = (volatile signed __int32 *)v43[1];
  if ( v43[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v43[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
      if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800eaee4  mov     [rsp-8+arg_18], r9b
0x1800eaee9  push    rbp
0x1800eaeea  push    rbx
0x1800eaeeb  push    rsi
0x1800eaeec  push    rdi
0x1800eaeed  push    r12
0x1800eaeef  push    r13
0x1800eaef1  push    r14
0x1800eaef3  push    r15
0x1800eaef5  lea     rbp, [rsp-68h]
0x1800eaefa  sub     rsp, 168h
0x1800eaf01  mov     rax, cs:__security_cookie
0x1800eaf08  xor     rax, rsp
0x1800eaf0b  mov     [rbp+0A0h+var_50], rax
0x1800eaf0f  mov     rbx, r8
0x1800eaf12  mov     r14, rdx
0x1800eaf15  mov     rsi, rcx
0x1800eaf18  mov     [rsp+1A0h+var_138], rdx
0x1800eaf1d  xor     r15d, r15d
0x1800eaf20  lea     edx, [r15+4Fh]; unsigned int
0x1800eaf24  lea     rcx, aHnsServiceCore_182; "HNS::Service::Core::LayeredEntityManage"...
0x1800eaf2b  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1800eaf30  or      r12d, 0FFFFFFFFh
0x1800eaf34  lea     r13, GUID_NULL
0x1800eaf3b  cmp     [rbx+48h], r15b
0x1800eaf3f  jz      short loc_1800EAF59
0x1800eaf41  lea     rcx, [rbx+38h]; Buf1
0x1800eaf45  lea     r8d, [r15+10h]; Size
0x1800eaf49  mov     rdx, r13; Buf2
0x1800eaf4c  call    memcmp_0
0x1800eaf51  test    eax, eax
0x1800eaf53  jz      loc_1800EB0D5
0x1800eaf59  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_103108bddb783e77add5a08e75fa90e6_@@_NAEBV?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_103108bddb783e77add5a08e75fa90e6_,bool,std::shared_ptr<HNS::Service::Network::LayeredResource> const &>::`vftable'
0x1800eaf60  mov     [rbp+0A0h+var_90], rax
0x1800eaf64  mov     [rbp+0A0h+var_88], rbx
0x1800eaf68  lea     rax, [rbp+0A0h+var_90]
0x1800eaf6c  mov     [rbp+0A0h+var_58], rax
0x1800eaf70  lea     r8, [rbp+0A0h+var_90]
0x1800eaf74  lea     rdx, [rbp+0A0h+Uuid]
0x1800eaf78  mov     rcx, rsi
0x1800eaf7b  call    ?Search@?$EntityManager@V?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@@Core@Service@HNS@@IEAA?AV?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@AEBV?$function@$$A6A_NAEBV?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@@Z@6@@Z; HNS::Service::Core::EntityManager<std::shared_ptr<HNS::Service::Network::LayeredResource>>::Search(std::function<bool (std::shared_ptr<HNS::Service::Network::LayeredResource> const &)> const &)
0x1800eaf80  nop
0x1800eaf81  mov     rcx, [rbp+0A0h+var_58]
0x1800eaf85  test    rcx, rcx
0x1800eaf88  jz      short loc_1800EAFA4
0x1800eaf8a  mov     rax, [rcx]
0x1800eaf8d  lea     rdx, [rbp+0A0h+var_90]
0x1800eaf91  cmp     rcx, rdx
0x1800eaf94  setnz   dl
0x1800eaf97  mov     rax, [rax+20h]
0x1800eaf9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eafa0  mov     [rbp+0A0h+var_58], r15
0x1800eafa4  mov     rdi, qword ptr [rbp+0A0h+Uuid.Data1]
0x1800eafa8  test    rdi, rdi
0x1800eafab  jz      loc_1800EB095
0x1800eafb1  mov     rsi, cs:qword_180399588
0x1800eafb8  mov     eax, [rsi]
0x1800eafba  cmp     eax, 5
0x1800eafbd  jbe     short loc_1800EB021
0x1800eafbf  lea     rcx, [rdi+2F0h]
0x1800eafc6  mov     r8, rcx
0x1800eafc9  lea     rdx, [rbp+0A0h+var_D0]
0x1800eafcd  mov     rcx, [rcx+38h]
0x1800eafd1  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1800eafd6  nop
0x1800eafd7  lea     rax, [rbp+0A0h+var_D0]
0x1800eafdb  mov     [rsp+1A0h+var_128], rax
0x1800eafe0  mov     [rsp+1A0h+var_140], 5Eh ; '^'
0x1800eafe8  lea     rcx, aHnsServiceCore_182; "HNS::Service::Core::LayeredEntityManage"...
0x1800eafef  mov     [rsp+1A0h+var_138], rcx
0x1800eaff4  lea     rax, [rsp+1A0h+var_128]
0x1800eaff9  mov     [rsp+1A0h+var_170], rax
0x1800eaffe  lea     rax, [rsp+1A0h+var_140]
0x1800eb003  mov     [rsp+1A0h+var_178], rax
0x1800eb008  lea     rax, [rsp+1A0h+var_138]
0x1800eb00d  mov     qword ptr [rsp+1A0h+var_180], rax
0x1800eb012  lea     rdx, unk_1803372BA
0x1800eb019  mov     rcx, rsi
0x1800eb01c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800eb021  mov     rbx, [rbx+88h]
0x1800eb028  mov     rbx, [rbx]
0x1800eb02b  cmp     [rbx+19h], r15b
0x1800eb02f  jnz     short loc_1800EB085
0x1800eb031  lea     rdx, [rbx+1Ch]; struct _GUID *
0x1800eb035  mov     r8b, 1; bool
0x1800eb038  mov     rcx, rdi; this
0x1800eb03b  call    ?SetExtension@LayeredResource@Network@Service@HNS@@QEAAXAEBU_GUID@@_N@Z; HNS::Service::Network::LayeredResource::SetExtension(_GUID const &,bool)
0x1800eb040  mov     rcx, [rbx+10h]
0x1800eb044  cmp     [rcx+19h], r15b
0x1800eb048  jz      short loc_1800EB068
0x1800eb04a  mov     rax, [rbx+8]
0x1800eb04e  jmp     short loc_1800EB05D
0x1800eb050  cmp     rbx, [rax+10h]
0x1800eb054  jnz     short loc_1800EB063
0x1800eb056  mov     rbx, rax
0x1800eb059  mov     rax, [rax+8]
0x1800eb05d  cmp     [rax+19h], r15b
0x1800eb061  jz      short loc_1800EB050
0x1800eb063  mov     rbx, rax
0x1800eb066  jmp     short loc_1800EB02B
0x1800eb068  mov     rbx, rcx
0x1800eb06b  mov     rcx, [rcx]
0x1800eb06e  cmp     [rcx+19h], r15b
0x1800eb072  jnz     short loc_1800EB02B
0x1800eb074  mov     rbx, rcx
0x1800eb077  mov     rax, [rcx]
0x1800eb07a  mov     rcx, rax
0x1800eb07d  cmp     [rax+19h], r15b
0x1800eb081  jz      short loc_1800EB074
0x1800eb083  jmp     short loc_1800EB02B
0x1800eb085  mov     [r14], rdi
0x1800eb088  mov     rcx, qword ptr [rbp+0A0h+Uuid.Data4]
0x1800eb08c  mov     [r14+8], rcx
0x1800eb090  jmp     loc_1800EB4DA
0x1800eb095  mov     rdi, qword ptr [rbp+0A0h+Uuid.Data4]
0x1800eb099  test    rdi, rdi
0x1800eb09c  jz      short loc_1800EB0D5
0x1800eb09e  mov     eax, r12d
0x1800eb0a1  lock xadd [rdi+8], eax
0x1800eb0a6  add     eax, r12d
0x1800eb0a9  jnz     short loc_1800EB0D5
0x1800eb0ab  mov     rax, [rdi]
0x1800eb0ae  mov     rcx, rdi
0x1800eb0b1  mov     rax, [rax]
0x1800eb0b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb0b9  mov     eax, r12d
0x1800eb0bc  lock xadd [rdi+0Ch], eax
0x1800eb0c1  add     eax, r12d
0x1800eb0c4  jnz     short loc_1800EB0D5
0x1800eb0c6  mov     rax, [rdi]
0x1800eb0c9  mov     rcx, rdi
0x1800eb0cc  mov     rax, [rax+8]
0x1800eb0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb0d5  mov     rcx, rsi; this
0x1800eb0d8  call    ?PruneOrphans@LayeredEntityManager@Core@Service@HNS@@UEAAXXZ; HNS::Service::Core::LayeredEntityManager::PruneOrphans(void)
0x1800eb0dd  cmp     [rbx+4Ah], r15b
0x1800eb0e1  jz      short loc_1800EB0ED
0x1800eb0e3  cmp     [rbx+4Bh], r15b
0x1800eb0e7  jnz     loc_1800EB50E
0x1800eb0ed  lea     r12, [rbx+38h]
0x1800eb0f1  mov     r8d, 10h; Size
0x1800eb0f7  mov     rdx, r13; Buf2
0x1800eb0fa  mov     rcx, r12; Buf1
0x1800eb0fd  call    memcmp_0
0x1800eb102  test    eax, eax
0x1800eb104  jnz     short loc_1800EB13B
0x1800eb106  lea     r8d, [rax+10h]; Size
0x1800eb10a  mov     rdx, r13; Buf2
0x1800eb10d  lea     rcx, [rbx+28h]; Buf1
0x1800eb111  call    memcmp_0
0x1800eb116  test    eax, eax
0x1800eb118  jnz     short loc_1800EB131
0x1800eb11a  xorps   xmm0, xmm0
0x1800eb11d  movups  xmmword ptr [rbp+0A0h+Uuid.Data1], xmm0
0x1800eb121  lea     rcx, [rbp+0A0h+Uuid]; Uuid
0x1800eb125  call    cs:__imp_UuidCreate
0x1800eb12b  movaps  xmm0, xmmword ptr [rbp+0A0h+Uuid.Data1]
0x1800eb12f  jmp     short loc_1800EB135
0x1800eb131  movups  xmm0, xmmword ptr [rbx+28h]
0x1800eb135  movdqu  xmmword ptr [r12], xmm0
0x1800eb13b  lea     r15, [rsi+1D0h]
0x1800eb142  mov     rcx, r15; SRWLock
0x1800eb145  call    cs:__imp_AcquireSRWLockExclusive
0x1800eb14b  mov     [rsp+1A0h+var_138], r15
0x1800eb150  lea     r13, [rsi+1D8h]
0x1800eb157  movups  xmm0, xmmword ptr [r12]
0x1800eb15c  movdqu  xmmword ptr [rbp+0A0h+Uuid.Data1], xmm0
0x1800eb161  mov     al, [rbp+0A0h+arg_18]
0x1800eb167  mov     byte ptr [rbp+0A0h+var_A0], al
0x1800eb16a  lea     r8, [rbp+0A0h+Uuid]
0x1800eb16e  lea     rdx, [rbp+0A0h+var_D0]
0x1800eb172  mov     rcx, r13
0x1800eb175  call    ??$emplace@U?$pair@U_GUID@@_N@std@@@?$_Tree@V?$_Tmap_traits@U_GUID@@_NUGuidLessThan@Common@Service@HNS@@V?$allocator@U?$pair@$$CBU_GUID@@_N@std@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@_N@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@U_GUID@@_N@1@@Z; std::_Tree<std::_Tmap_traits<_GUID,bool,HNS::Service::Common::GuidLessThan,std::allocator<std::pair<_GUID const,bool>>,0>>::emplace<std::pair<_GUID,bool>>(std::pair<_GUID,bool> &&)
0x1800eb17a  nop
0x1800eb17b  xor     edi, edi
0x1800eb17d  test    r15, r15
0x1800eb180  jz      short loc_1800EB18B
0x1800eb182  mov     rcx, r15; SRWLock
0x1800eb185  call    cs:__imp_ReleaseSRWLockExclusive
0x1800eb18b  cmp     [rbx+68h], rdi
0x1800eb18f  jnz     short loc_1800EB1B5
0x1800eb191  mov     r8, rbx
0x1800eb194  lea     rdx, [rbp+0A0h+var_D0]
0x1800eb198  mov     rcx, rsi
0x1800eb19b  call    ?GenerateUniqueName@LayeredEntityManager@Core@Service@HNS@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUResourceRequirement@Network@34@@Z; HNS::Service::Core::LayeredEntityManager::GenerateUniqueName(HNS::Service::Network::ResourceRequirement const &)
0x1800eb1a0  lea     rcx, [rbx+58h]
0x1800eb1a4  mov     rdx, rax
0x1800eb1a7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800eb1ac  lea     rcx, [rbp+0A0h+var_D0]; void *
0x1800eb1b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800eb1b5  mov     r8, [rsi+1A0h]
0x1800eb1bc  mov     r9, rbx
0x1800eb1bf  mov     r8, [r8+68h]
0x1800eb1c3  lea     rdx, [rsp+1A0h+var_150]
0x1800eb1c8  call    ?CreateLayer@LayeredEntityManager@Core@Service@HNS@@AEAA?AV?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@_KAEAUResourceRequirement@Network@34@@Z; HNS::Service::Core::LayeredEntityManager::CreateLayer(unsigned __int64,HNS::Service::Network::ResourceRequirement &)
0x1800eb1cd  nop
0x1800eb1ce  lea     rdx, [rsp+1A0h+var_150]
0x1800eb1d3  mov     rcx, rsi
0x1800eb1d6  call    ?AddPending@?$EntityManager@V?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@@Core@Service@HNS@@IEAAXAEAV?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@@Z; HNS::Service::Core::EntityManager<std::shared_ptr<HNS::Service::Network::LayeredResource>>::AddPending(std::shared_ptr<HNS::Service::Network::LayeredResource> &)
0x1800eb1db  mov     [rsp+1A0h+var_160], dil
0x1800eb1e0  mov     [rsp+1A0h+var_15F], dil
0x1800eb1e5  lea     rax, [rsp+1A0h+var_150]
0x1800eb1ea  mov     [rbp+0A0h+var_D0], rax
0x1800eb1ee  mov     [rbp+0A0h+var_C8], rsi
0x1800eb1f2  lea     rax, [rsp+1A0h+var_160]
0x1800eb1f7  mov     [rbp+0A0h+var_C0], rax
0x1800eb1fb  lea     rax, [rsp+1A0h+var_15F]
0x1800eb200  mov     [rbp+0A0h+var_B8], rax
0x1800eb204  mov     rax, [rbp+0A8h]
0x1800eb20b  mov     qword ptr [rbp+0A0h+Uuid.Data1], rax
0x1800eb20f  lea     rdi, aOnecoreVmDvNet; "onecore\\vm\\dv\\net\\hns\\service\\cor"...
0x1800eb216  mov     qword ptr [rbp+0A0h+Uuid.Data4], rdi
0x1800eb21a  mov     [rbp+0A0h+var_A0], 0
0x1800eb222  mov     eax, 0A1h
0x1800eb227  mov     [rbp+0A0h+var_98], ax
0x1800eb22b  lea     r8, [rbp+0A0h+var_D0]
0x1800eb22f  lea     rdx, [rbp+0A0h+Uuid]
0x1800eb233  lea     rcx, [rbp+0A0h+var_120]
0x1800eb237  call    wil__scope_exit_log__lambda_2a8909c5b028381e1ec1e61496ab2c8e___
0x1800eb23c  nop
0x1800eb23d  lea     rax, [rsp+1A0h+var_150]
0x1800eb242  mov     [rbp+0A0h+var_D0], rax
0x1800eb246  mov     [rbp+0A0h+var_C8], rbx
0x1800eb24a  lea     rax, [rbp+0A0h+arg_18]
0x1800eb251  mov     [rbp+0A0h+var_C0], rax
0x1800eb255  mov     rax, [rbp+0A0h+arg_20]
0x1800eb25c  mov     [rbp+0A0h+var_B8], rax
0x1800eb260  lea     rcx, [rbp+0A0h+var_D0]
0x1800eb264  call    wil__ResultFromException__lambda_95bd53eef9d662f0985c0dfe227ee387___
0x1800eb269  mov     ebx, eax
0x1800eb26b  mov     r8b, 1; bool
0x1800eb26e  mov     edx, eax; int
0x1800eb270  mov     rcx, [rsp+1A0h+var_150]; this
0x1800eb275  call    ?LogEntityEvent@LayeredResource@Network@Service@HNS@@AEAAXJ_N@Z; HNS::Service::Network::LayeredResource::LogEntityEvent(long,bool)
0x1800eb27a  mov     rcx, [rbp+0A8h]; this
0x1800eb281  test    ebx, ebx
0x1800eb283  js      loc_1800EB4FD
0x1800eb289  mov     rcx, [rsp+1A0h+var_150]
0x1800eb28e  lea     r8, [rcx+2F0h]
0x1800eb295  lea     rdx, [rbp+0A0h+var_D0]
0x1800eb299  mov     rcx, [rcx+328h]
0x1800eb2a0  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1800eb2a5  nop
0x1800eb2a6  lea     r8, [rbp+0A0h+var_D0]
0x1800eb2aa  mov     edx, 16h
0x1800eb2af  mov     rcx, rsi
0x1800eb2b2  call    ?RaiseLayeredEvent@LayeredEntityManager@Core@Service@HNS@@AEAAXW4EventType@Events@34@AEBU_GUID@@@Z; HNS::Service::Core::LayeredEntityManager::RaiseLayeredEvent(HNS::Service::Events::EventType,_GUID const &)
0x1800eb2b7  mov     rcx, [rsp+1A0h+var_150]
0x1800eb2bc  lea     r8, [rcx+2F0h]
0x1800eb2c3  lea     rdx, [rbp+0A0h+var_D0]
0x1800eb2c7  mov     rcx, [rcx+328h]
0x1800eb2ce  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1800eb2d3  nop
0x1800eb2d4  mov     edx, 48h ; 'H'; unsigned int
0x1800eb2d9  lea     rcx, aHnsServiceCore_60; "HNS::Service::Core::EntityManager<class"...
0x1800eb2e0  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x1800eb2e5  lea     rcx, [rsi+88h]
0x1800eb2ec  lea     r8, [rsp+1A0h+var_150]
0x1800eb2f1  lea     rdx, [rbp+0A0h+var_D0]
0x1800eb2f5  call    ??$Add@AEAV?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@@?$Repository@V?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@@Core@Service@HNS@@QEAAXAEBU_GUID@@AEAV?$shared_ptr@VLayeredResource@Network@Service@HNS@@@std@@@Z; HNS::Service::Core::Repository<std::shared_ptr<HNS::Service::Network::LayeredResource>>::Add<std::shared_ptr<HNS::Service::Network::LayeredResource> &>(_GUID const &,std::shared_ptr<HNS::Service::Network::LayeredResource> &)
0x1800eb2fa  mov     [rsp+1A0h+var_160], 1
0x1800eb2ff  mov     rcx, [rsi+178h]
0x1800eb306  mov     rax, [rsp+1A0h+var_150+8]
0x1800eb30b  test    rax, rax
0x1800eb30e  jz      short loc_1800EB314
0x1800eb310  lock inc dword ptr [rax+8]
0x1800eb314  movaps  xmm0, xmmword ptr [rsp+1A0h+var_150]
0x1800eb319  movdqa  xmmword ptr [rbp+0A0h+Uuid.Data1], xmm0
0x1800eb31e  xor     r9d, r9d
0x1800eb321  lea     r8, [rbp+0A0h+Uuid]
0x1800eb325  xor     edx, edx
0x1800eb327  call    ?Add@StorageManager@Core@Service@HNS@@QEAAJW4StorageObjectGroup@@AEBV?$shared_ptr@VIEntity@Interface@Service@HNS@@@std@@_NE@Z; HNS::Service::Core::StorageManager::Add(StorageObjectGroup,std::shared_ptr<HNS::Service::Interface::IEntity> const &,bool,uchar)
0x1800eb32c  nop
0x1800eb32d  mov     rbx, qword ptr [rbp+0A0h+Uuid.Data4]
0x1800eb331  test    rbx, rbx
0x1800eb334  jz      short loc_1800EB36C
0x1800eb336  or      edi, 0FFFFFFFFh
0x1800eb339  mov     eax, edi
0x1800eb33b  lock xadd [rbx+8], eax
0x1800eb340  add     eax, edi
0x1800eb342  jnz     short loc_1800EB36C
0x1800eb344  mov     rax, [rbx]
0x1800eb347  mov     rcx, rbx
0x1800eb34a  mov     rax, [rax]
0x1800eb34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb352  mov     eax, edi
0x1800eb354  lock xadd [rbx+0Ch], eax
0x1800eb359  add     eax, edi
0x1800eb35b  jnz     short loc_1800EB36C
0x1800eb35d  mov     rax, [rbx]
0x1800eb360  mov     rcx, rbx
0x1800eb363  mov     rax, [rax+8]
0x1800eb367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb36c  mov     [rsp+1A0h+var_15F], 1
0x1800eb371  mov     rcx, r15; SRWLock
0x1800eb374  call    cs:__imp_AcquireSRWLockExclusive
0x1800eb37a  lea     rsi, [r13+8]
0x1800eb37e  mov     rbx, [rsi]
0x1800eb381  mov     rbx, [rbx]
0x1800eb384  xor     r13d, r13d
  ... truncated ...
```
