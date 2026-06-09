# HNS::Service::Request::RequestManager::HandleGetCall<0,HNS::Schema::HostComputeNetwork>(std::shared_ptr<HNS::Service::Request::BaseRequest>,ushort const *,ushort const *)

- ea: `0x1801a8f94`
- end: `0x1801a95ce`
- name: `??$HandleGetCall@$0A@UHostComputeNetwork@Schema@HNS@@@RequestManager@Request@Service@HNS@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VBaseRequest@Request@Service@HNS@@@5@PEBG1@Z`
- size: `1594`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801af278`

## callees

- `0x180001b68`
- `0x180001df8`
- `0x180002164`
- `0x18005f0c0`
- `0x18005ffc4`
- `0x180061240`
- `0x1800666b4`
- `0x180069b04`
- `0x18006c530`
- `0x18006cc2c`
- `0x1800759d8`
- `0x1800776d8`
- `0x18007e864`
- `0x180087cc0`
- `0x1800bcae4`
- `0x1800bdd2c`
- `0x1801a4af8`
- `0x1801a4da0`
- `0x1801a4fec`
- `0x1801a6bf0`
- `0x1801a8f94`
- `0x1801a9658`
- `0x1801a9718`
- `0x1801a9810`
- `0x1801a98e8`
- `0x1801a9e18`
- `0x1801ab518`
- `0x1801ae5d0`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a901a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801a901a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a94a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a9393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801a94a8`

## string_xrefs

- `0x1801a909d`: `onecore\vm\dv\net\hns\service\request\requestmanager.cpp`
- `0x1801a959a`: `onecore\vm\dv\net\hns\service\request\requestmanager.cpp`
- `0x1801a8fee`: `HNS::Service::Request::RequestManager::HandleGetCall`
- `0x1801a90cb`: `HandleGetCall - Open function not supported for object`
- `0x1801a958e`: `HandleGetCall via WcnAgent failed %ws %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall HNS::Service::Request::RequestManager::HandleGetCall<0,HNS::Schema::HostComputeNetwork>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v9; // eax
  __int64 v10; // r8
  int v11; // r9d
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // r14
  __m128i si128; // xmm6
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  int v21; // r8d
  int v22; // r9d
  _QWORD *v23; // rax
  __m128i *v24; // rdx
  int v25; // r8d
  int v26; // r9d
  _QWORD *v27; // rax
  volatile signed __int32 *v28; // rbx
  volatile signed __int32 *v29; // rbx
  unsigned int v31; // eax
  int v32; // [rsp+28h] [rbp-E0h]
  int v33; // [rsp+28h] [rbp-E0h]
  int v34; // [rsp+28h] [rbp-E0h]
  int v35; // [rsp+28h] [rbp-E0h]
  int v36; // [rsp+28h] [rbp-E0h]
  const char *v37; // [rsp+38h] [rbp-D0h]
  const char *v38; // [rsp+38h] [rbp-D0h]
  const char *v39; // [rsp+38h] [rbp-D0h]
  const char *v40; // [rsp+38h] [rbp-D0h]
  int v41[2]; // [rsp+48h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v43; // [rsp+58h] [rbp-B0h] BYREF
  volatile signed __int32 *v44; // [rsp+60h] [rbp-A8h]
  _WORD *v45; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID v46[2]; // [rsp+70h] [rbp-98h] BYREF
  LPVOID v47; // [rsp+80h] [rbp-88h]
  _QWORD *v48; // [rsp+88h] [rbp-80h] BYREF
  __int128 v49; // [rsp+90h] [rbp-78h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-68h]
  _QWORD v51[2]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v52[5]; // [rsp+B8h] [rbp-50h] BYREF
  char v53; // [rsp+E0h] [rbp-28h]
  __int128 v54; // [rsp+E8h] [rbp-20h] BYREF
  __m128i v55; // [rsp+F8h] [rbp-10h]
  _QWORD v56[4]; // [rsp+108h] [rbp+0h] BYREF
  char v57[8]; // [rsp+128h] [rbp+20h] BYREF
  __int128 v58; // [rsp+130h] [rbp+28h] BYREF
  __int64 v59; // [rsp+140h] [rbp+38h]
  __int64 v60; // [rsp+148h] [rbp+40h]
  __int64 v61; // [rsp+150h] [rbp+48h] BYREF
  __int128 v62; // [rsp+158h] [rbp+50h]
  __int128 v63; // [rsp+168h] [rbp+60h]
  __int128 v64; // [rsp+178h] [rbp+70h]
  int v65; // [rsp+188h] [rbp+80h]
  _BYTE v66[64]; // [rsp+198h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+240h] [rbp+138h]

  *(_QWORD *)&v54 = a2;
  v52[2] = a3;
  LODWORD(pv) = 1;
  HNSTraceProvider::TraceEnter("HNS::Service::Request::RequestManager::HandleGetCall", 0x13Cu);
  if ( *(_WORD *)a4 && (*(_WORD *)a4 != 47 || *(_WORD *)(a4 + 2)) && (unsigned int)_o__wcsicmp(L"/all", a4) )
  {
    v31 = wil::verify_hresult<long>(2151350293LL);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x192,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
      (const char *)v31,
      (int)"HandleGetCall via WcnAgent failed %ws %ws",
      (const char *)a4,
      a5);
  }
  if ( *(_DWORD *)qword_18039BB28 > 4u )
    tlgWriteTransfer_EventWriteTransfer(qword_18039BB28, &unk_18033EE18, 0, 0, 2, v66);
  HNS::Service::Request::RequestManager::GetWcnAgentManager(a1, &v43);
  LOBYTE(v32) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 24LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x14B,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v32,
    (bool)"HandleGetCall - Enumerate function not supported for object",
    v37);
  LOBYTE(v33) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 40LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x150,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v33,
    (bool)"HandleGetCall - Open function not supported for object",
    v38);
  LOBYTE(v34) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 72LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x155,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v34,
    (bool)"HandleGetCall - Close function not supported for object",
    v39);
  LOBYTE(v35) = *(_QWORD *)(*(_QWORD *)(v43 + 128) + 56LL) == 0;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x15A,
    (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
    (const char *)0x803B0015LL,
    v35,
    (bool)"HandleGetCall - Query function not supported for object",
    v40);
  v45 = 0;
  v9 = HNS::Service::Core::WcnAgentManager::InvokeEnumerateFunction<HNS::Schema::HostComputeNetwork>(v43, a5, &v45);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15E,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
      (const char *)(unsigned int)v9,
      v36);
  if ( *(_DWORD *)qword_18039BB28 > 4u )
  {
    *(_QWORD *)v41 = v45;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      qword_18039BB28,
      (unsigned int)&unk_18033EE6C,
      v10,
      v11,
      (__int64)v41);
  }
  v49 = 0;
  v50 = 0;
  v12 = -1;
  do
    ++v12;
  while ( v45[v12] );
  *(_QWORD *)&v54 = v45;
  *((_QWORD *)&v54 + 1) = v12;
  Marshal::FromJsonThrow<std::vector<_GUID>,>(&v54, &v49, v10, 2147942413LL);
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v14 = *((_QWORD *)&v49 + 1);
  v13 = v49;
  if ( (_QWORD)v49 != *((_QWORD *)&v49 + 1) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      *(_QWORD *)v41 = 0;
      v52[3] = v41;
      v52[4] = &v43;
      v53 = 1;
      v16 = HNS::Service::Core::WcnAgentManager::InvokeOpenFunction<HNS::Schema::HostComputeNetwork,void *>(
              v43,
              v13,
              v41);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x174,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
          (const char *)(unsigned int)v16,
          v36);
      pv = 0;
      v17 = HNS::Service::Core::WcnAgentManager::InvokeQueryFunction<HNS::Schema::HostComputeNetwork,void *>(
              v43,
              *(_QWORD *)v41,
              &unk_1802E2A80,
              &pv);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\request\\requestmanager.cpp",
          (const char *)(unsigned int)v17,
          v36);
      v51[0] = pv;
      v18 = -1;
      do
        ++v18;
      while ( *((_WORD *)pv + v18) );
      v51[1] = v18;
      v19 = (_QWORD *)HNS::Schema::ConvertV2ToInternalSchema<0>(v66, v51);
      if ( v19[3] <= 7u )
        v20 = v19;
      else
        v20 = (_QWORD *)*v19;
      v52[0] = v20;
      v52[1] = v19[2];
      HNS::Schema::ConvertInternalToV1Schema<2>(v56, v52);
      std::wstring::~wstring(v66);
      if ( *(_DWORD *)qword_18039BB28 > 4u )
      {
        v23 = v56;
        if ( v56[3] > 7u )
          v23 = (_QWORD *)v56[0];
        v48 = v23;
        *(_QWORD *)&v54 = pv;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          qword_18039BB28,
          (unsigned int)&unk_18033EED4,
          v21,
          v22,
          (__int64)&v54,
          (__int64)&v48);
      }
      std::wstring::wstring(&v54, v56);
      v24 = (__m128i *)v46[1];
      if ( v46[1] == v47 )
      {
        std::vector<Marshal::RawJson>::_Emplace_reallocate<Marshal::RawJson>(v46, (__int64)v46[1], &v54);
      }
      else
      {
        *(_OWORD *)v46[1] = v54;
        v24[1] = v55;
        v55 = si128;
        LOWORD(v54) = 0;
        v46[1] = (char *)v46[1] + 32;
      }
      std::wstring::~wstring(&v54);
      std::wstring::~wstring(v56);
      if ( pv )
        CoTaskMemFree(pv);
      if ( *(_QWORD *)v41 )
        HNS::Service::Core::WcnAgentManager::InvokeCloseFunction<HNS::Schema::HostComputeNetwork,void *>(v43);
      v13 += 16;
    }
    while ( v13 != v14 );
  }
  v58 = 0;
  v59 = 0;
  v60 = 7;
  LOWORD(v58) = 0;
  memset_0(&v61, 0, 0x40u);
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v57[0] = 1;
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(
    (__int64)v66,
    (__int64 *)v46);
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::operator=(&v61, v66);
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(v66);
  Marshal::ToJson<Config::Network::HNS::v2::Response &,>(a2, v57);
  if ( *(_DWORD *)qword_18039BB28 > 4u )
  {
    if ( a2[3] <= 7u )
      v27 = a2;
    else
      v27 = (_QWORD *)*a2;
    *(_QWORD *)&v54 = v27;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      qword_18039BB28,
      (unsigned int)&unk_18033F127,
      v25,
      v26,
      (__int64)&v54);
  }
  Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(&v61);
  std::wstring::~wstring(&v58);
  std::vector<std::wstring>::_Tidy(v46);
  std::vector<_GUID>::~vector<_GUID>(&v49);
  if ( v45 )
    CoTaskMemFree(v45);
  v28 = v44;
  if ( v44 )
  {
    if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    }
  }
  v29 = *(volatile signed __int32 **)(a3 + 8);
  if ( v29 )
  {
    if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
      if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1801a8f94  mov     rax, rsp
0x1801a8f97  push    rbp
0x1801a8f98  push    rbx
0x1801a8f99  push    rsi
0x1801a8f9a  push    rdi
0x1801a8f9b  push    r12
0x1801a8f9d  push    r13
0x1801a8f9f  push    r14
0x1801a8fa1  push    r15
0x1801a8fa3  lea     rbp, [rax-138h]
0x1801a8faa  sub     rsp, 1F8h
0x1801a8fb1  movaps  xmmword ptr [rax-58h], xmm6
0x1801a8fb5  mov     rax, cs:__security_cookie
0x1801a8fbc  xor     rax, rsp
0x1801a8fbf  mov     [rbp+130h+var_60], rax
0x1801a8fc6  mov     rbx, r9
0x1801a8fc9  mov     r15, r8
0x1801a8fcc  mov     rdi, rdx
0x1801a8fcf  mov     rsi, rcx
0x1801a8fd2  mov     qword ptr [rbp+130h+var_150], rdx
0x1801a8fd6  mov     [rbp+130h+var_170], r8
0x1801a8fda  mov     r12, [rbp+130h+arg_20]
0x1801a8fe1  mov     dword ptr [rsp+230h+pv], 1
0x1801a8fe9  mov     edx, 13Ch; unsigned int
0x1801a8fee  lea     rcx, aHnsServiceRequ_3; "HNS::Service::Request::RequestManager::"...
0x1801a8ff5  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1801a8ffa  xor     r13d, r13d
0x1801a8ffd  cmp     [rbx], r13w
0x1801a9001  jz      short loc_1801A9028
0x1801a9003  cmp     word ptr [rbx], 2Fh ; '/'
0x1801a9007  jnz     short loc_1801A9010
0x1801a9009  cmp     [rbx+2], r13w
0x1801a900e  jz      short loc_1801A9028
0x1801a9010  mov     rdx, rbx
0x1801a9013  lea     rcx, aAll_1; "/all"
0x1801a901a  call    cs:__imp__o__wcsicmp
0x1801a9020  test    eax, eax
0x1801a9022  jnz     loc_1801A9570
0x1801a9028  mov     rcx, cs:qword_18039BB28
0x1801a902f  mov     eax, [rcx]
0x1801a9031  cmp     eax, 4
0x1801a9034  jbe     short loc_1801A905C
0x1801a9036  lea     rax, [rbp+130h+var_A0]
0x1801a903d  mov     [rsp+230h+var_208], rax
0x1801a9042  mov     [rsp+230h+var_210], 2
0x1801a904a  xor     r9d, r9d
0x1801a904d  xor     r8d, r8d
0x1801a9050  lea     rdx, unk_18033EE18
0x1801a9057  call    _tlgWriteTransfer_EventWriteTransfer
0x1801a905c  lea     rdx, [rsp+230h+var_1E0]
0x1801a9061  mov     rcx, rsi
0x1801a9064  call    ?GetWcnAgentManager@RequestManager@Request@Service@HNS@@QEAA?AV?$shared_ptr@VWcnAgentManager@Core@Service@HNS@@@std@@XZ; HNS::Service::Request::RequestManager::GetWcnAgentManager(void)
0x1801a9069  nop
0x1801a906a  mov     rax, [rsp+230h+var_1E0]
0x1801a906f  mov     rcx, [rax+80h]
0x1801a9076  cmp     [rcx+18h], r13
0x1801a907a  setz    al
0x1801a907d  mov     rcx, [rbp+138h]; this
0x1801a9084  lea     rdx, aHandlegetcallE; "HandleGetCall - Enumerate function not "...
0x1801a908b  mov     [rsp+230h+var_208], rdx; bool
0x1801a9090  mov     byte ptr [rsp+230h+var_210], al; int
0x1801a9094  mov     r14d, 803B0015h
0x1801a909a  mov     r9d, r14d; char *
0x1801a909d  lea     rsi, aOnecoreVmDvNet_121; "onecore\\vm\\dv\\net\\hns\\service\\req"...
0x1801a90a4  mov     r8, rsi; unsigned int
0x1801a90a7  mov     edx, 14Bh; void *
0x1801a90ac  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a90b1  mov     rax, [rsp+230h+var_1E0]
0x1801a90b6  mov     rcx, [rax+80h]
0x1801a90bd  cmp     [rcx+28h], r13
0x1801a90c1  setz    al
0x1801a90c4  mov     rcx, [rbp+138h]; this
0x1801a90cb  lea     rdx, aHandlegetcallO; "HandleGetCall - Open function not suppo"...
0x1801a90d2  mov     [rsp+230h+var_208], rdx; bool
0x1801a90d7  mov     byte ptr [rsp+230h+var_210], al; int
0x1801a90db  mov     r9d, r14d; char *
0x1801a90de  mov     r8, rsi; unsigned int
0x1801a90e1  mov     edx, 150h; void *
0x1801a90e6  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a90eb  mov     rax, [rsp+230h+var_1E0]
0x1801a90f0  mov     rcx, [rax+80h]
0x1801a90f7  cmp     [rcx+48h], r13
0x1801a90fb  setz    al
0x1801a90fe  mov     rcx, [rbp+138h]; this
0x1801a9105  lea     rdx, aHandlegetcallC; "HandleGetCall - Close function not supp"...
0x1801a910c  mov     [rsp+230h+var_208], rdx; bool
0x1801a9111  mov     byte ptr [rsp+230h+var_210], al; int
0x1801a9115  mov     r9d, r14d; char *
0x1801a9118  mov     r8, rsi; unsigned int
0x1801a911b  mov     edx, 155h; void *
0x1801a9120  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a9125  mov     rax, [rsp+230h+var_1E0]
0x1801a912a  mov     rcx, [rax+80h]
0x1801a9131  cmp     [rcx+38h], r13
0x1801a9135  setz    al
0x1801a9138  mov     rcx, [rbp+138h]; this
0x1801a913f  lea     rdx, aHandlegetcallQ; "HandleGetCall - Query function not supp"...
0x1801a9146  mov     [rsp+230h+var_208], rdx; bool
0x1801a914b  mov     byte ptr [rsp+230h+var_210], al; int
0x1801a914f  mov     r9d, r14d; char *
0x1801a9152  mov     r8, rsi; unsigned int
0x1801a9155  mov     edx, 15Ah; void *
0x1801a915a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1801a915f  nop
0x1801a9160  mov     [rsp+230h+var_1D0], r13
0x1801a9165  lea     r8, [rsp+230h+var_1D0]
0x1801a916a  mov     rdx, r12
0x1801a916d  mov     rcx, [rsp+230h+var_1E0]
0x1801a9172  call    ??$InvokeEnumerateFunction@UHostComputeNetwork@Schema@HNS@@@WcnAgentManager@Core@Service@HNS@@QEBAJPEBGPEAPEAG@Z; HNS::Service::Core::WcnAgentManager::InvokeEnumerateFunction<HNS::Schema::HostComputeNetwork>(ushort const *,ushort * *)
0x1801a9177  mov     rcx, [rbp+138h]; this
0x1801a917e  test    eax, eax
0x1801a9180  js      loc_1801A95AC
0x1801a9186  mov     rcx, cs:qword_18039BB28
0x1801a918d  mov     eax, [rcx]
0x1801a918f  cmp     eax, 4
0x1801a9192  jbe     short loc_1801A91B4
0x1801a9194  mov     rax, [rsp+230h+var_1D0]
0x1801a9199  mov     qword ptr [rsp+230h+var_1F0], rax
0x1801a919e  lea     rax, [rsp+230h+var_1F0]
0x1801a91a3  mov     qword ptr [rsp+230h+var_210], rax; int
0x1801a91a8  lea     rdx, unk_18033EE6C
0x1801a91af  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1801a91b4  xorps   xmm0, xmm0
0x1801a91b7  movdqu  [rbp+130h+var_1A8], xmm0
0x1801a91bc  mov     [rbp+130h+var_198], r13
0x1801a91c0  mov     rcx, [rsp+230h+var_1D0]
0x1801a91c5  or      r12, 0FFFFFFFFFFFFFFFFh
0x1801a91c9  mov     rax, r12
0x1801a91cc  inc     rax
0x1801a91cf  cmp     [rcx+rax*2], r13w
0x1801a91d4  jnz     short loc_1801A91CC
0x1801a91d6  mov     qword ptr [rbp+130h+var_150], rcx
0x1801a91da  mov     qword ptr [rbp+130h+var_150+8], rax
0x1801a91de  mov     r9d, 8007000Dh
0x1801a91e4  lea     rdx, [rbp+130h+var_1A8]
0x1801a91e8  lea     rcx, [rbp+130h+var_150]
0x1801a91ec  call    ??$FromJsonThrow@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@$$V@Marshal@@YAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@W4UnmarshalFlags@0@J@Z; Marshal::FromJsonThrow<std::vector<_GUID>,>(std::basic_string_view<ushort>,std::vector<_GUID> *,Marshal::UnmarshalFlags,long)
0x1801a91f1  xorps   xmm0, xmm0
0x1801a91f4  movdqu  xmmword ptr [rsp+230h+var_1D0+8], xmm0
0x1801a91fa  mov     [rsp+230h+var_1B8], r13
0x1801a91ff  mov     rbx, qword ptr [rbp+130h+var_1A8]
0x1801a9203  mov     r14, qword ptr [rbp+130h+var_1A8+8]
0x1801a9207  cmp     rbx, r14
0x1801a920a  jz      loc_1801A93BB
0x1801a9210  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1801a9218  mov     qword ptr [rsp+230h+var_1F0], r13
0x1801a921d  lea     rax, [rsp+230h+var_1F0]
0x1801a9222  mov     [rbp+130h+var_168], rax
0x1801a9226  lea     rax, [rsp+230h+var_1E0]
0x1801a922b  mov     [rbp+130h+var_160], rax
0x1801a922f  mov     [rbp+130h+var_158], 1
0x1801a9233  lea     r8, [rsp+230h+var_1F0]
0x1801a9238  mov     rdx, rbx
0x1801a923b  mov     rcx, [rsp+230h+var_1E0]
0x1801a9240  call    ??$InvokeOpenFunction@UHostComputeNetwork@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJAEBU_GUID@@PEAPEAX@Z; HNS::Service::Core::WcnAgentManager::InvokeOpenFunction<HNS::Schema::HostComputeNetwork,void *>(_GUID const &,void * *)
0x1801a9245  mov     rcx, [rbp+138h]; this
0x1801a924c  test    eax, eax
0x1801a924e  js      loc_1801A955F
0x1801a9254  mov     [rsp+230h+pv], r13
0x1801a9259  lea     r9, [rsp+230h+pv]
0x1801a925e  lea     r8, unk_1802E2A80
0x1801a9265  mov     rdx, qword ptr [rsp+230h+var_1F0]
0x1801a926a  mov     rcx, [rsp+230h+var_1E0]
0x1801a926f  call    ??$InvokeQueryFunction@UHostComputeNetwork@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJPEAXPEBGPEAPEAG@Z; HNS::Service::Core::WcnAgentManager::InvokeQueryFunction<HNS::Schema::HostComputeNetwork,void *>(void *,ushort const *,ushort * *)
0x1801a9274  mov     rcx, [rbp+138h]; this
0x1801a927b  test    eax, eax
0x1801a927d  js      loc_1801A95BD
0x1801a9283  mov     rcx, [rsp+230h+pv]
0x1801a9288  mov     [rbp+130h+var_190], rcx
0x1801a928c  mov     rax, r12
0x1801a928f  inc     rax
0x1801a9292  cmp     [rcx+rax*2], r13w
0x1801a9297  jnz     short loc_1801A928F
0x1801a9299  mov     [rbp+130h+var_188], rax
0x1801a929d  lea     rdx, [rbp+130h+var_190]
0x1801a92a1  lea     rcx, [rbp+130h+var_A0]
0x1801a92a8  call    ??$ConvertV2ToInternalSchema@$0A@@Schema@HNS@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; HNS::Schema::ConvertV2ToInternalSchema<0>(std::basic_string_view<ushort> const &)
0x1801a92ad  nop
0x1801a92ae  cmp     qword ptr [rax+18h], 7
0x1801a92b3  jbe     short loc_1801A92BA
0x1801a92b5  mov     rcx, [rax]
0x1801a92b8  jmp     short loc_1801A92BD
0x1801a92ba  mov     rcx, rax
0x1801a92bd  mov     [rbp+130h+var_180], rcx
0x1801a92c1  mov     rax, [rax+10h]
0x1801a92c5  mov     [rbp+130h+var_178], rax
0x1801a92c9  lea     rdx, [rbp+130h+var_180]
0x1801a92cd  lea     rcx, [rbp+130h+var_130]
0x1801a92d1  call    ??$ConvertInternalToV1Schema@$01@Schema@HNS@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string_view@GU?$char_traits@G@std@@@3@@Z; HNS::Schema::ConvertInternalToV1Schema<2>(std::basic_string_view<ushort> const &)
0x1801a92d6  nop
0x1801a92d7  lea     rcx, [rbp+130h+var_A0]; void *
0x1801a92de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a92e3  nop
0x1801a92e4  mov     rcx, cs:qword_18039BB28
0x1801a92eb  mov     eax, [rcx]
0x1801a92ed  cmp     eax, 4
0x1801a92f0  jbe     short loc_1801A932B
0x1801a92f2  lea     rax, [rbp+130h+var_130]
0x1801a92f6  cmp     [rbp+130h+var_118], 7
0x1801a92fb  cmova   rax, [rbp+130h+var_130]
0x1801a9300  mov     [rbp+130h+var_1B0], rax
0x1801a9304  mov     rax, [rsp+230h+pv]
0x1801a9309  mov     qword ptr [rbp+130h+var_150], rax
0x1801a930d  lea     rax, [rbp+130h+var_1B0]
0x1801a9311  mov     [rsp+230h+var_208], rax
0x1801a9316  lea     rax, [rbp+130h+var_150]
0x1801a931a  mov     qword ptr [rsp+230h+var_210], rax
0x1801a931f  lea     rdx, unk_18033EED4
0x1801a9326  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801a932b  lea     rdx, [rbp+130h+var_130]
0x1801a932f  lea     rcx, [rbp+130h+var_150]
0x1801a9333  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801a9338  nop
0x1801a9339  mov     rdx, [rsp+230h+var_1C0]
0x1801a933e  cmp     rdx, [rsp+230h+var_1B8]
0x1801a9343  jz      short loc_1801A9366
0x1801a9345  movups  xmm0, [rbp+130h+var_150]
0x1801a9349  movups  xmmword ptr [rdx], xmm0
0x1801a934c  movups  xmm1, [rbp+130h+var_140]
0x1801a9350  movups  xmmword ptr [rdx+10h], xmm1
0x1801a9354  movdqu  [rbp+130h+var_140], xmm6
0x1801a9359  mov     word ptr [rbp+130h+var_150], r13w
0x1801a935e  add     [rsp+230h+var_1C0], 20h ; ' '
0x1801a9364  jmp     short loc_1801A9375
0x1801a9366  lea     r8, [rbp+130h+var_150]
0x1801a936a  lea     rcx, [rsp+230h+var_1D0+8]
0x1801a936f  call    ??$_Emplace_reallocate@URawJson@Marshal@@@?$vector@URawJson@Marshal@@V?$allocator@URawJson@Marshal@@@std@@@std@@AEAAPEAURawJson@Marshal@@QEAU23@$$QEAU23@@Z; std::vector<Marshal::RawJson>::_Emplace_reallocate<Marshal::RawJson>(Marshal::RawJson * const,Marshal::RawJson &&)
0x1801a9374  nop
0x1801a9375  lea     rcx, [rbp+130h+var_150]; void *
0x1801a9379  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a937e  nop
0x1801a937f  lea     rcx, [rbp+130h+var_130]; void *
0x1801a9383  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a9388  nop
0x1801a9389  mov     rcx, [rsp+230h+pv]; pv
0x1801a938e  test    rcx, rcx
0x1801a9391  jz      short loc_1801A939A
0x1801a9393  call    cs:__imp_CoTaskMemFree
0x1801a9399  nop
0x1801a939a  mov     rdx, qword ptr [rsp+230h+var_1F0]
0x1801a939f  test    rdx, rdx
0x1801a93a2  jz      short loc_1801A93AE
0x1801a93a4  mov     rcx, [rsp+230h+var_1E0]
0x1801a93a9  call    ??$InvokeCloseFunction@UHostComputeNetwork@Schema@HNS@@PEAX@WcnAgentManager@Core@Service@HNS@@QEBAJPEAX@Z; HNS::Service::Core::WcnAgentManager::InvokeCloseFunction<HNS::Schema::HostComputeNetwork,void *>(void *)
0x1801a93ae  add     rbx, 10h
0x1801a93b2  cmp     rbx, r14
0x1801a93b5  jnz     loc_1801A9218
0x1801a93bb  xorps   xmm0, xmm0
0x1801a93be  movups  [rbp+130h+var_108], xmm0
0x1801a93c2  mov     [rbp+130h+var_F8], r13
0x1801a93c6  mov     [rbp+130h+var_F0], 7
0x1801a93ce  mov     word ptr [rbp+130h+var_108], r13w
0x1801a93d3  xor     edx, edx; Val
0x1801a93d5  lea     r8d, [rdx+40h]; Size
0x1801a93d9  lea     rcx, [rbp+130h+var_E8]; void *
0x1801a93dd  call    memset_0
0x1801a93e2  mov     [rbp+130h+var_E8], r13
0x1801a93e6  xorps   xmm0, xmm0
0x1801a93e9  movdqa  [rbp+130h+var_E0], xmm0
0x1801a93ee  xorps   xmm1, xmm1
0x1801a93f1  movdqa  [rbp+130h+var_D0], xmm1
0x1801a93f6  movdqa  [rbp+130h+var_C0], xmm0
0x1801a93fb  mov     [rbp+130h+var_B0], r13d
0x1801a9402  mov     [rbp+130h+var_110], 1
0x1801a9406  lea     rdx, [rsp+230h+var_1D0+8]
0x1801a940b  lea     rcx, [rbp+130h+var_A0]
0x1801a9412  call    ??$?0AEAV?$vector@URawJson@Marshal@@V?$allocator@URawJson@Marshal@@@std@@@std@@@?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@AEAV?$vector@URawJson@Marshal@@V?$allocator@URawJson@Marshal@@@std@@@std@@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::DelayedBase<void,Marshal::Details::DelayedJsonTraits>(std::vector<Marshal::RawJson> &)
0x1801a9417  lea     rdx, [rbp+130h+var_A0]
0x1801a941e  lea     rcx, [rbp+130h+var_E8]
0x1801a9422  call    ??4?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAAAEAV01@$$QEAV01@@Z; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::operator=(Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits> &&)
0x1801a9427  lea     rcx, [rbp+130h+var_A0]
0x1801a942e  call    ??1?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(void)
0x1801a9433  lea     rdx, [rbp+130h+var_110]
0x1801a9437  mov     rcx, rdi
0x1801a943a  call    ??$ToJson@AEAUResponse@v2@HNS@Network@Config@@$$V@Marshal@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAUResponse@v2@HNS@Network@Config@@W4MarshalFlags@0@@Z; Marshal::ToJson<Config::Network::HNS::v2::Response &,>(Config::Network::HNS::v2::Response &,Marshal::MarshalFlags)
0x1801a943f  mov     rcx, cs:qword_18039BB28
0x1801a9446  mov     eax, [rcx]
0x1801a9448  cmp     eax, 4
0x1801a944b  jbe     short loc_1801A9476
0x1801a944d  cmp     qword ptr [rdi+18h], 7
0x1801a9452  jbe     short loc_1801A9459
0x1801a9454  mov     rax, [rdi]
0x1801a9457  jmp     short loc_1801A945C
0x1801a9459  mov     rax, rdi
0x1801a945c  mov     qword ptr [rbp+130h+var_150], rax
0x1801a9460  lea     rax, [rbp+130h+var_150]
0x1801a9464  mov     qword ptr [rsp+230h+var_210], rax
0x1801a9469  lea     rdx, unk_18033F127
0x1801a9470  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1801a9475  nop
0x1801a9476  lea     rcx, [rbp+130h+var_E8]
0x1801a947a  call    ??1?$DelayedBase@XUDelayedJsonTraits@Details@Marshal@@@Marshal@@QEAA@XZ; Marshal::DelayedBase<void,Marshal::Details::DelayedJsonTraits>::~DelayedBase<void,Marshal::Details::DelayedJsonTraits>(void)
0x1801a947f  lea     rcx, [rbp+130h+var_108]; void *
0x1801a9483  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801a9488  nop
0x1801a9489  lea     rcx, [rsp+230h+var_1D0+8]
0x1801a948e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1801a9493  nop
0x1801a9494  lea     rcx, [rbp+130h+var_1A8]
0x1801a9498  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
  ... truncated ...
```
