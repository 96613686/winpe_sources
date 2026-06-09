# HNS::Service::Network::ICSNetwork::~ICSNetwork(void)

- ea: `0x180128da4`
- end: `0x1801290cf`
- name: `??1ICSNetwork@Network@Service@HNS@@UEAA@XZ`
- size: `811`
- prototype: `void __fastcall(HNS::Service::Network::ICSNetwork *__hidden this)`
- caller_count: `6`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bea20`
- `0x1800beba0`
- `0x1800d13d0`
- `0x1800d1420`
- `0x180129460`
- `0x18028eb58`

## callees

- `0x18006c530`
- `0x180088898`
- `0x1800bd300`
- `0x1800d8268`
- `0x1800da494`
- `0x180128da4`
- `0x18019dcb8`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180128e63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180128e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180128e31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180128e31`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180128e5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180128eb6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180128e5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180128eb6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180128e52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180128ead`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180128e52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180128ead`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180128e44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180128e9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180128e44`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180128e9f`

## pseudocode

```c
void __fastcall HNS::Service::Network::ICSNetwork::~ICSNetwork(HNS::Service::Network::ICSNetwork *this)
{
  HNS::Service::Common::Notify::INotifyable *v2; // r14
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v5; // rbx
  HNSObject *v6; // rcx
  volatile signed __int32 *v7; // rbx
  HNSObject *v8; // rcx
  HNSObject *v9; // rcx
  HNSObject *v10; // rcx
  HNSObject *v11; // rcx
  HNSObject *v12; // rcx
  HNSObject *v13; // rcx
  HNSObject *v14; // rcx
  HNSObject *v15; // rcx
  HNSObject *v16; // rcx
  HNSObject *v17; // rcx
  HNSObject *v18; // rcx
  HNSObject *v19; // rcx
  volatile signed __int32 *v20; // rbx

  *(_QWORD *)this = &HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::IStorable'};
  v2 = (HNS::Service::Network::ICSNetwork *)((char *)this + 2480);
  *((_QWORD *)this + 4) = &HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::ILockable'};
  *((_QWORD *)this + 6) = &HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::ITraceable'};
  *((_QWORD *)this + 7) = &HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::IDiagnoseable'};
  *((_QWORD *)this + 32) = &HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Events::IEventHandleable'};
  *((_QWORD *)this + 102) = &HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::IResourceable'};
  *((_QWORD *)this + 113) = &HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::IPolicable'};
  *((_QWORD *)this + 122) = &HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Network::InternalNetwork'};
  *((_QWORD *)this + 310) = &HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Common::Notify::INotifyable'};
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 593);
  if ( v3 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 593) = 0;
  HNS::Service::Common::Notify::INotifyable::StopNotify(v2);
  std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>((char *)this + 4752);
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 593);
  if ( v5 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 593), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v5, 1);
    CloseThreadpoolTimer(v5);
  }
  v6 = (HNSObject *)*((_QWORD *)this + 591);
  if ( v6 )
    HNSObject::Release(v6);
  std::wstring::~wstring((char *)this + 4672);
  v7 = (volatile signed __int32 *)*((_QWORD *)this + 583);
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  v8 = (HNSObject *)*((_QWORD *)this + 581);
  if ( v8 )
    HNSObject::Release(v8);
  std::wstring::~wstring((char *)this + 4592);
  v9 = (HNSObject *)*((_QWORD *)this + 573);
  if ( v9 )
    HNSObject::Release(v9);
  std::wstring::~wstring((char *)this + 4528);
  v10 = (HNSObject *)*((_QWORD *)this + 565);
  if ( v10 )
    HNSObject::Release(v10);
  std::wstring::~wstring((char *)this + 4464);
  v11 = (HNSObject *)*((_QWORD *)this + 557);
  if ( v11 )
    HNSObject::Release(v11);
  std::wstring::~wstring((char *)this + 4400);
  v12 = (HNSObject *)*((_QWORD *)this + 549);
  if ( v12 )
    HNSObject::Release(v12);
  std::wstring::~wstring((char *)this + 4336);
  v13 = (HNSObject *)*((_QWORD *)this + 541);
  if ( v13 )
    HNSObject::Release(v13);
  std::wstring::~wstring((char *)this + 4272);
  v14 = (HNSObject *)*((_QWORD *)this + 533);
  if ( v14 )
    HNSObject::Release(v14);
  std::wstring::~wstring((char *)this + 4208);
  v15 = (HNSObject *)*((_QWORD *)this + 525);
  if ( v15 )
    HNSObject::Release(v15);
  std::wstring::~wstring((char *)this + 4144);
  v16 = (HNSObject *)*((_QWORD *)this + 517);
  if ( v16 )
    HNSObject::Release(v16);
  std::wstring::~wstring((char *)this + 4080);
  v17 = (HNSObject *)*((_QWORD *)this + 509);
  if ( v17 )
    HNSObject::Release(v17);
  std::wstring::~wstring((char *)this + 4016);
  v18 = (HNSObject *)*((_QWORD *)this + 501);
  if ( v18 )
    HNSObject::Release(v18);
  std::wstring::~wstring((char *)this + 3952);
  v19 = (HNSObject *)*((_QWORD *)this + 493);
  if ( v19 )
    HNSObject::Release(v19);
  std::wstring::~wstring((char *)this + 3888);
  v20 = (volatile signed __int32 *)*((_QWORD *)this + 485);
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  HNS::Service::Common::Notify::INotifyable::~INotifyable(v2);
  HNS::Service::Network::InternalNetwork::~InternalNetwork(this);
}

```

## disassembly

```asm
0x180128da4  push    rbx
0x180128da6  push    rsi
0x180128da7  push    rdi
0x180128da8  push    r14
0x180128daa  sub     rsp, 28h
0x180128dae  lea     rax, ??_7ICSNetwork@Network@Service@HNS@@6BIStorable@Interface@23@@; const HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::IStorable'}
0x180128db5  mov     rdi, rcx
0x180128db8  mov     [rcx], rax
0x180128dbb  lea     r14, [rcx+9B0h]
0x180128dc2  lea     rax, ??_7ICSNetwork@Network@Service@HNS@@6BILockable@Interface@23@@; const HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::ILockable'}
0x180128dc9  mov     [rcx+20h], rax
0x180128dcd  lea     rax, ??_7ICSNetwork@Network@Service@HNS@@6BITraceable@Interface@23@@; const HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::ITraceable'}
0x180128dd4  mov     [rcx+30h], rax
0x180128dd8  lea     rax, ??_7ICSNetwork@Network@Service@HNS@@6BIDiagnoseable@Interface@23@@; const HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::IDiagnoseable'}
0x180128ddf  mov     [rcx+38h], rax
0x180128de3  lea     rax, ??_7ICSNetwork@Network@Service@HNS@@6BIEventHandleable@Events@23@@; const HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Events::IEventHandleable'}
0x180128dea  mov     [rcx+100h], rax
0x180128df1  lea     rax, ??_7ICSNetwork@Network@Service@HNS@@6BIResourceable@Interface@23@@; const HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::IResourceable'}
0x180128df8  mov     [rcx+330h], rax
0x180128dff  lea     rax, ??_7ICSNetwork@Network@Service@HNS@@6BIPolicable@Interface@23@@; const HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Interface::IPolicable'}
0x180128e06  mov     [rcx+388h], rax
0x180128e0d  lea     rax, ??_7ICSNetwork@Network@Service@HNS@@6BInternalNetwork@123@@; const HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Network::InternalNetwork'}
0x180128e14  mov     [rcx+3D0h], rax
0x180128e1b  lea     rax, ??_7ICSNetwork@Network@Service@HNS@@6BINotifyable@Notify@Common@23@@; const HNS::Service::Network::ICSNetwork::`vftable'{for `HNS::Service::Common::Notify::INotifyable'}
0x180128e22  mov     [r14], rax
0x180128e25  mov     rsi, [rcx+1288h]
0x180128e2c  test    rsi, rsi
0x180128e2f  jz      short loc_180128E69
0x180128e31  call    cs:__imp_GetLastError
0x180128e37  xor     r9d, r9d; msWindowLength
0x180128e3a  xor     r8d, r8d; msPeriod
0x180128e3d  xor     edx, edx; pftDueTime
0x180128e3f  mov     rcx, rsi; pti
0x180128e42  mov     ebx, eax
0x180128e44  call    cs:__imp_SetThreadpoolTimer
0x180128e4a  mov     edx, 1; fCancelPendingCallbacks
0x180128e4f  mov     rcx, rsi; pti
0x180128e52  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180128e58  mov     rcx, rsi; pti
0x180128e5b  call    cs:__imp_CloseThreadpoolTimer
0x180128e61  mov     ecx, ebx; dwErrCode
0x180128e63  call    cs:__imp_SetLastError
0x180128e69  mov     rcx, r14; this
0x180128e6c  mov     qword ptr [rdi+1288h], 0
0x180128e77  call    ?StopNotify@INotifyable@Notify@Common@Service@HNS@@IEAAXXZ; HNS::Service::Common::Notify::INotifyable::StopNotify(void)
0x180128e7c  lea     rcx, [rdi+1290h]
0x180128e83  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,unsigned __int64,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,unsigned __int64>>,0>>(void)
0x180128e88  mov     rbx, [rdi+1288h]
0x180128e8f  test    rbx, rbx
0x180128e92  jz      short loc_180128EBC
0x180128e94  xor     r9d, r9d; msWindowLength
0x180128e97  xor     r8d, r8d; msPeriod
0x180128e9a  xor     edx, edx; pftDueTime
0x180128e9c  mov     rcx, rbx; pti
0x180128e9f  call    cs:__imp_SetThreadpoolTimer
0x180128ea5  mov     edx, 1; fCancelPendingCallbacks
0x180128eaa  mov     rcx, rbx; pti
0x180128ead  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180128eb3  mov     rcx, rbx; pti
0x180128eb6  call    cs:__imp_CloseThreadpoolTimer
0x180128ebc  lea     rbx, [rdi+1240h]
0x180128ec3  mov     rcx, [rbx+38h]; this
0x180128ec7  test    rcx, rcx
0x180128eca  jz      short loc_180128ED1
0x180128ecc  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180128ed1  mov     rcx, rbx; void *
0x180128ed4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180128ed9  mov     rbx, [rdi+1238h]
0x180128ee0  or      esi, 0FFFFFFFFh
0x180128ee3  test    rbx, rbx
0x180128ee6  jz      short loc_180128F1B
0x180128ee8  mov     eax, esi
0x180128eea  lock xadd [rbx+8], eax
0x180128eef  add     eax, esi
0x180128ef1  jnz     short loc_180128F1B
0x180128ef3  mov     rax, [rbx]
0x180128ef6  mov     rcx, rbx
0x180128ef9  mov     rax, [rax]
0x180128efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128f01  mov     eax, esi
0x180128f03  lock xadd [rbx+0Ch], eax
0x180128f08  add     eax, esi
0x180128f0a  jnz     short loc_180128F1B
0x180128f0c  mov     rax, [rbx]
0x180128f0f  mov     rcx, rbx
0x180128f12  mov     rax, [rax+8]
0x180128f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128f1b  lea     rbx, [rdi+11F0h]
0x180128f22  mov     rcx, [rbx+38h]; this
0x180128f26  test    rcx, rcx
0x180128f29  jz      short loc_180128F30
0x180128f2b  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180128f30  mov     rcx, rbx; void *
0x180128f33  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180128f38  lea     rbx, [rdi+11B0h]
0x180128f3f  mov     rcx, [rbx+38h]; this
0x180128f43  test    rcx, rcx
0x180128f46  jz      short loc_180128F4D
0x180128f48  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180128f4d  mov     rcx, rbx; void *
0x180128f50  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180128f55  lea     rbx, [rdi+1170h]
0x180128f5c  mov     rcx, [rbx+38h]; this
0x180128f60  test    rcx, rcx
0x180128f63  jz      short loc_180128F6A
0x180128f65  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180128f6a  mov     rcx, rbx; void *
0x180128f6d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180128f72  lea     rbx, [rdi+1130h]
0x180128f79  mov     rcx, [rbx+38h]; this
0x180128f7d  test    rcx, rcx
0x180128f80  jz      short loc_180128F87
0x180128f82  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180128f87  mov     rcx, rbx; void *
0x180128f8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180128f8f  lea     rbx, [rdi+10F0h]
0x180128f96  mov     rcx, [rbx+38h]; this
0x180128f9a  test    rcx, rcx
0x180128f9d  jz      short loc_180128FA4
0x180128f9f  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180128fa4  mov     rcx, rbx; void *
0x180128fa7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180128fac  lea     rbx, [rdi+10B0h]
0x180128fb3  mov     rcx, [rbx+38h]; this
0x180128fb7  test    rcx, rcx
0x180128fba  jz      short loc_180128FC1
0x180128fbc  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180128fc1  mov     rcx, rbx; void *
0x180128fc4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180128fc9  lea     rbx, [rdi+1070h]
0x180128fd0  mov     rcx, [rbx+38h]; this
0x180128fd4  test    rcx, rcx
0x180128fd7  jz      short loc_180128FDE
0x180128fd9  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180128fde  mov     rcx, rbx; void *
0x180128fe1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180128fe6  lea     rbx, [rdi+1030h]
0x180128fed  mov     rcx, [rbx+38h]; this
0x180128ff1  test    rcx, rcx
0x180128ff4  jz      short loc_180128FFB
0x180128ff6  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180128ffb  mov     rcx, rbx; void *
0x180128ffe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180129003  lea     rbx, [rdi+0FF0h]
0x18012900a  mov     rcx, [rbx+38h]; this
0x18012900e  test    rcx, rcx
0x180129011  jz      short loc_180129018
0x180129013  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180129018  mov     rcx, rbx; void *
0x18012901b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180129020  lea     rbx, [rdi+0FB0h]
0x180129027  mov     rcx, [rbx+38h]; this
0x18012902b  test    rcx, rcx
0x18012902e  jz      short loc_180129035
0x180129030  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180129035  mov     rcx, rbx; void *
0x180129038  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18012903d  lea     rbx, [rdi+0F70h]
0x180129044  mov     rcx, [rbx+38h]; this
0x180129048  test    rcx, rcx
0x18012904b  jz      short loc_180129052
0x18012904d  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x180129052  mov     rcx, rbx; void *
0x180129055  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18012905a  lea     rbx, [rdi+0F30h]
0x180129061  mov     rcx, [rbx+38h]; this
0x180129065  test    rcx, rcx
0x180129068  jz      short loc_18012906F
0x18012906a  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x18012906f  mov     rcx, rbx; void *
0x180129072  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180129077  mov     rbx, [rdi+0F28h]
0x18012907e  test    rbx, rbx
0x180129081  jz      short loc_1801290B6
0x180129083  mov     eax, esi
0x180129085  lock xadd [rbx+8], eax
0x18012908a  add     eax, esi
0x18012908c  jnz     short loc_1801290B6
0x18012908e  mov     rax, [rbx]
0x180129091  mov     rcx, rbx
0x180129094  mov     rax, [rax]
0x180129097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012909c  mov     eax, esi
0x18012909e  lock xadd [rbx+0Ch], eax
0x1801290a3  add     eax, esi
0x1801290a5  jnz     short loc_1801290B6
0x1801290a7  mov     rax, [rbx]
0x1801290aa  mov     rcx, rbx
0x1801290ad  mov     rax, [rax+8]
0x1801290b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801290b6  mov     rcx, r14; this
0x1801290b9  call    ??1INotifyable@Notify@Common@Service@HNS@@UEAA@XZ; HNS::Service::Common::Notify::INotifyable::~INotifyable(void)
0x1801290be  mov     rcx, rdi; this
0x1801290c1  add     rsp, 28h
0x1801290c5  pop     r14
0x1801290c7  pop     rdi
0x1801290c8  pop     rsi
0x1801290c9  pop     rbx
0x1801290ca  jmp     ??1InternalNetwork@Network@Service@HNS@@UEAA@XZ; HNS::Service::Network::InternalNetwork::~InternalNetwork(void)
```
