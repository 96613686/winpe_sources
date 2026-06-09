# win_musl::InternalPartReceiverCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_musl::detail::CloseableCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_musl::InnerCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_scope::report_policy_throw>>>::AddOpcStream_Safe(wchar_t const *,__MIDL___MIDL_itf_opc2Eio_0000_0000_0002,__MIDL___MIDL_itf_dox2Ebase_0000_0000_0002,IByteCollection *,__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)

- ea: `0x1800101d0`
- end: `0x180010735`
- name: `?AddOpcStream_Safe@?$InternalPartReceiverCom@V?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@UIWin7InternalPartReceiver@@V?$CloseableCom@V?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@UIWin7InternalPartReceiver@@V?$InnerCom@V?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@UIWin7InternalPartReceiver@@Ureport_policy_throw@2@@win_musl@@@detail@win_musl@@@win_musl@@AEAAXPEB_WW4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@U__MIDL___MIDL_itf_dox2Ebase_0000_0000_0002@@PEAUIByteCollection@@PEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z`
- size: `1381`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180081968`

## callees

- `0x18000531c`
- `0x18000fd84`
- `0x1800101d0`
- `0x18001073c`
- `0x180011b14`
- `0x180011b80`
- `0x180011fe8`
- `0x1800120a4`
- `0x1800124f4`
- `0x18001568c`
- `0x180016bf0`
- `0x1800190e0`
- `0x1800195ac`
- `0x18002db70`
- `0x180058f20`
- `0x18007b560`
- `0x18009c7bc`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800cded0`
- `0x1800cdf2c`
- `0x1800d0848`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001035a`
- `msvcrt!memcpy_s` at `0x18001035a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010398`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010398`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010537`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010537`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010385`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010385`

## string_xrefs

- `0x18001025a`: `Failed or Close already called on this receiver`
- `0x18001064e`: `compressionOptions`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall win_musl::InternalPartReceiverCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_musl::detail::CloseableCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_musl::InnerCom<win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>,IWin7InternalPartReceiver,win_scope::report_policy_throw>>>::AddOpcStream_Safe(
        __int64 a1,
        _WORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v6; // r14d
  __int64 v9; // r15
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdi
  void **v12; // rcx
  void **v13; // rcx
  bool v14; // dl
  win_dox *v15; // rcx
  void *v16; // rax
  int v17; // edx
  const char *v18; // r8
  unsigned int v19; // r9d
  volatile signed __int32 *v20; // rax
  volatile signed __int32 *v21; // rbx
  __int64 v22; // rdx
  volatile signed __int32 *v23; // rcx
  __int64 v24; // r14
  __int64 v26; // rsi
  __int128 *v27; // [rsp+48h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+50h] [rbp-B8h] BYREF
  __int128 v29; // [rsp+60h] [rbp-A8h] BYREF
  void **v30; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v31[3]; // [rsp+78h] [rbp-90h] BYREF
  char v32[8]; // [rsp+90h] [rbp-78h] BYREF
  void *Destination[2]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v34; // [rsp+A8h] [rbp-60h]
  unsigned __int64 v35; // [rsp+B0h] [rbp-58h]
  _BYTE v36[48]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v38[160]; // [rsp+128h] [rbp+20h] BYREF

  v31[1] = -2;
  v6 = a3;
  if ( !a2 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      54,
      L"IWin7InternalPartReceiver",
      L"AddPart",
      L"logicalItemName",
      0);
  if ( (_DWORD)a3 != -1 && (_DWORD)a3 && (_DWORD)a3 != 3 && (_DWORD)a3 != 1 && (_DWORD)a3 != 2 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      69,
      L"IWin7InternalPartReceiver",
      L"AddPart",
      L"compressionOptions",
      2);
  if ( !a5 )
    win_musl::detail::ThrowParameter(
      a1,
      "(no filename)",
      a3,
      76,
      L"IWin7InternalPartReceiver",
      L"AddPart",
      L"pIInternalByteCollection",
      0);
  if ( !*(_QWORD *)(a1 + 8) || dword_1801C4E50 == -1 )
  {
    win_musl::DebugLogHelper(
      "(no filename)",
      &word_180139126,
      80,
      1024,
      -2147418113,
      L"Failed or Close already called on this receiver");
    std::string::string(v36, "Program has entered an unexpected state");
    std::logic_error::logic_error(pExceptionObject, v36);
    throw (std::logic_error *)pExceptionObject;
  }
  win_dox::to_interface<IReceiver>::resolve(v31);
  v30 = &win_dox::OpcRelationshipCollection::`vftable';
  v9 = *(_QWORD *)(a1 + 8);
  v10 = 7;
  v35 = 7;
  v34 = 0;
  LOWORD(Destination[0]) = 0;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  if ( v11 > 0x7FFFFFFFFFFFFFFELL )
    std::_String_base::_Xlen();
  if ( v11 > 7 )
  {
    std::wstring::_Copy(v32, v11, 0);
    v10 = v35;
  }
  else if ( !v11 )
  {
    v34 = 0;
    LOWORD(Destination[0]) = 0;
    goto LABEL_19;
  }
  v12 = Destination;
  if ( v10 >= 8 )
    v12 = (void **)Destination[0];
  memcpy_s(v12, 2 * v10, a2, 2 * v11);
  v13 = Destination;
  if ( v35 >= 8 )
    v13 = (void **)Destination[0];
  v34 = v11;
  *((_WORD *)v13 + v11) = 0;
LABEL_19:
  v31[2] = v9 + 200;
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
  v15 = (win_dox *)*(unsigned int *)(v9 + 244);
  *(_DWORD *)(v9 + 244) = (_DWORD)v15 + 1;
  if ( !(_DWORD)v15 )
    *(_DWORD *)(v9 + 240) = GetCurrentThreadId();
  LOBYTE(v15) = *(_BYTE *)(v9 + 256);
  win_dox::ThrowIfFailed(v15, v14);
  v16 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v16 )
    SplException::RealThrowFromHR((SplException *)0x8007000ELL, v17, v18, v19);
  v26 = win_musl::consumption::MetroConsumptionState::ByteCollectionHolder::ByteCollectionHolder(
          (_DWORD)v16,
          (unsigned int)v32,
          v6,
          (unsigned int)&v30,
          a6);
  v29 = 0;
  v27 = (__int128 *)v26;
  if ( v26 )
  {
    v20 = (volatile signed __int32 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v21 = v20;
    if ( !v20 )
    {
      win_scope::close_delete::close<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder>(&v27);
      win_scope::report_policy_throw::report_init_failure();
    }
    *((_QWORD *)v20 + 1) = 0;
    *(_QWORD *)v20 = &win_scope::counted_strong_weak<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::resource_policies>>::`vftable';
    *((_QWORD *)v20 + 2) = v26;
    *(_QWORD *)&v29 = v20;
    if ( _InterlockedIncrement(v20 + 2) == 1 )
      _InterlockedAdd(v20 + 3, 1u);
    *((_QWORD *)&v29 + 1) = v26;
    v22 = v26;
    v23 = v20;
  }
  else
  {
    v23 = 0;
    v22 = 0;
    v26 = *((_QWORD *)&v29 + 1);
    v21 = (volatile signed __int32 *)v29;
  }
  v24 = *(_QWORD *)(v9 + 64);
  v28 = 0;
  if ( v23 )
  {
    if ( _InterlockedIncrement(v23 + 2) == 1 )
      _InterlockedAdd(v23 + 3, 1u);
    *(_QWORD *)&v28 = v23;
    *((_QWORD *)&v28 + 1) = v22;
  }
  v27 = &v28;
  if ( *(_BYTE *)(v24 + 44) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v38,
      0x39u,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"no more messages allowed");
    throw (SplException::THResultException *)v38;
  }
  std::deque<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>>::push_back(
    v24 + 400,
    &v28);
  win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::TestDerecurse(v24 + 40);
  if ( *((_QWORD *)&v28 + 1) && (_QWORD)v28 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v28);
  if ( v21 && v26 )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v29);
  if ( (*(_DWORD *)(v9 + 244))-- == 1 )
    *(_DWORD *)(v9 + 240) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 200));
  if ( v35 >= 8 )
    operator delete(Destination[0]);
  if ( v31[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v31[0] + 16LL))(v31[0]);
}

```

## disassembly

```asm
0x1800101d0  mov     rax, rsp
0x1800101d3  push    rbp
0x1800101d4  push    rsi
0x1800101d5  push    rdi
0x1800101d6  push    r12
0x1800101d8  push    r13
0x1800101da  push    r14
0x1800101dc  push    r15
0x1800101de  lea     rbp, [rax-108h]
0x1800101e5  sub     rsp, 1D0h
0x1800101ec  mov     qword ptr [rsp+78h], 0FFFFFFFFFFFFFFFEh
0x1800101f5  mov     [rax+20h], rbx
0x1800101f9  mov     rax, cs:__security_cookie
0x180010200  xor     rax, rsp
0x180010203  mov     [rbp+100h+var_40], rax
0x18001020a  mov     r14d, r8d
0x18001020d  mov     rsi, rdx
0x180010210  mov     rbx, rcx
0x180010213  mov     rdx, [rbp+100h+arg_20]
0x18001021a  mov     r12, [rbp+100h+arg_28]
0x180010221  xor     r13d, r13d
0x180010224  test    rsi, rsi
0x180010227  jz      loc_1800105F6
0x18001022d  cmp     r8d, 0FFFFFFFFh
0x180010231  jz      short loc_180010242
0x180010233  test    r8d, r8d
0x180010236  jz      short loc_180010242
0x180010238  cmp     r8d, 3
0x18001023c  jnz     loc_180010632
0x180010242  test    rdx, rdx
0x180010245  jz      loc_180010685
0x18001024b  cmp     [rcx+8], r13
0x18001024f  jz      short loc_18001025A
0x180010251  cmp     cs:dword_1801C4E50, 0FFFFFFFFh
0x180010258  jnz     short loc_1800102BC
0x18001025a  lea     rax, aFailedOrCloseA; "Failed or Close already called on this "...
0x180010261  mov     qword ptr [rsp+200h+var_1D8], rax
0x180010266  mov     [rsp+200h+var_1E0], 8000FFFFh
0x18001026e  mov     r9d, 400h
0x180010274  mov     r8d, 50h ; 'P'
0x18001027a  lea     rdx, word_180139126
0x180010281  lea     rcx, aNoFilename; "(no filename)"
0x180010288  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x18001028d  lea     rdx, aProgramHasEnte; "Program has entered an unexpected state"
0x180010294  lea     rcx, [rbp+100h+var_150]
0x180010298  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x18001029d  nop
0x18001029e  lea     rdx, [rbp+100h+var_150]
0x1800102a2  lea     rcx, [rbp+100h+pExceptionObject]
0x1800102a6  call    ??0logic_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::logic_error::logic_error(std::string const &)
0x1800102ab  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x1800102b2  lea     rcx, [rbp+100h+pExceptionObject]; pExceptionObject
0x1800102b6  call    _CxxThrowException_0
0x1800102bc  lea     rax, ??_7OpcRelationshipSender@win_dox@@6B@; const win_dox::OpcRelationshipSender::`vftable'
0x1800102c3  mov     [rsp+200h+var_198], rax
0x1800102c8  lea     rcx, [rsp+200h+var_190]
0x1800102cd  call    ?resolve@?$to_interface@UIReceiver@@@win_dox@@SA?AV?$scope@PEAUIReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@PEAUIReceiver@@@Z; win_dox::to_interface<IReceiver>::resolve(IReceiver *)
0x1800102d2  lea     rax, ??_7OpcRelationshipCollection@win_dox@@6B@; const win_dox::OpcRelationshipCollection::`vftable'
0x1800102d9  mov     [rsp+200h+var_198], rax
0x1800102de  mov     r15, [rbx+8]
0x1800102e2  mov     edx, 7
0x1800102e7  mov     [rbp+100h+var_158], rdx
0x1800102eb  mov     r8, r13
0x1800102ee  mov     [rbp+100h+var_160], r13
0x1800102f2  mov     word ptr [rbp+100h+Destination], r13w
0x1800102f7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800102fb  inc     rdi
0x1800102fe  cmp     [rsi+rdi*2], r13w
0x180010303  jnz     short loc_1800102FB
0x180010305  lea     rax, [rbp+100h+Destination]
0x180010309  cmp     rsi, rax
0x18001030c  jb      short loc_18001031B
0x18001030e  lea     rax, [rbp+100h+Destination]
0x180010312  cmp     rax, rsi
0x180010315  ja      loc_1800103EC
0x18001031b  mov     rax, 7FFFFFFFFFFFFFFEh
0x180010325  cmp     rdi, rax
0x180010328  ja      loc_1800106CF
0x18001032e  cmp     rdx, rdi
0x180010331  jb      loc_1800103D2
0x180010337  test    rdi, rdi
0x18001033a  jz      loc_18001042A
0x180010340  lea     rcx, [rbp+100h+Destination]
0x180010344  cmp     rdx, 8
0x180010348  cmovnb  rcx, [rbp+100h+Destination]; Destination
0x18001034d  lea     rbx, [rdi+rdi]
0x180010351  add     rdx, rdx; DestinationSize
0x180010354  mov     r9, rbx; SourceSize
0x180010357  mov     r8, rsi; Source
0x18001035a  call    cs:__imp_memcpy_s
0x180010360  lea     rcx, [rbp+100h+Destination]
0x180010364  cmp     [rbp+100h+var_158], 8
0x180010369  cmovnb  rcx, [rbp+100h+Destination]
0x18001036e  mov     [rbp+100h+var_160], rdi
0x180010372  mov     [rcx+rbx], r13w
0x180010377  lea     rdi, [r15+0C8h]
0x18001037e  mov     [rbp+100h+var_180], rdi
0x180010382  mov     rcx, rdi; lpCriticalSection
0x180010385  call    cs:__imp_EnterCriticalSection
0x18001038b  mov     ecx, [rdi+2Ch]
0x18001038e  lea     eax, [rcx+1]
0x180010391  mov     [rdi+2Ch], eax
0x180010394  test    ecx, ecx
0x180010396  jnz     short loc_1800103A1
0x180010398  call    cs:__imp_GetCurrentThreadId
0x18001039e  mov     [rdi+28h], eax
0x1800103a1  mov     cl, [r15+100h]; this
0x1800103a8  call    ?ThrowIfFailed@win_dox@@YAX_N@Z; win_dox::ThrowIfFailed(bool)
0x1800103ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800103b4  mov     ecx, 88h; unsigned __int64
0x1800103b9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800103be  test    rax, rax
0x1800103c1  jnz     loc_1800105A5
0x1800103c7  mov     ecx, 8007000Eh; this
0x1800103cc  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800103d2  mov     rdx, rdi
0x1800103d5  lea     rcx, [rbp+100h+var_178]
0x1800103d9  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1800103de  mov     rdx, [rbp+100h+var_158]
0x1800103e2  test    rdi, rdi
0x1800103e5  jz      short loc_180010377
0x1800103e7  jmp     loc_180010340
0x1800103ec  lea     rax, [rbp+100h+Destination]
0x1800103f0  sub     rsi, rax
0x1800103f3  sar     rsi, 1
0x1800103f6  jnz     loc_1800106C1
0x1800103fc  sub     r8, rsi
0x1800103ff  cmp     rdi, r8
0x180010402  cmovb   r8, rdi
0x180010406  lea     rdx, [rsi+r8]
0x18001040a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001040e  lea     rcx, [rbp+100h+var_178]
0x180010412  call    ?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180010417  mov     r8, rsi
0x18001041a  xor     edx, edx
0x18001041c  lea     rcx, [rbp+100h+var_178]
0x180010420  call    ?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180010425  jmp     loc_180010377
0x18001042a  lea     rcx, [rbp+100h+Destination]
0x18001042e  cmp     rdx, 8
0x180010432  cmovnb  rcx, [rbp+100h+Destination]
0x180010437  mov     [rbp+100h+var_160], r13
0x18001043b  mov     [rcx], r13w
0x18001043f  jmp     loc_180010377
0x180010444  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001044b  mov     ecx, 18h; unsigned __int64
0x180010450  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010455  mov     rbx, rax
0x180010458  test    rax, rax
0x18001045b  jz      loc_1800106E1
0x180010461  mov     [rax+8], r13
0x180010465  lea     rax, ??_7?$counted_strong_weak@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@6B@; const win_scope::counted_strong_weak<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::resource_policies>>::`vftable'
0x18001046c  mov     [rbx], rax
0x18001046f  mov     [rbx+10h], rsi
0x180010473  mov     qword ptr [rsp+200h+var_1B0+8], rbx
0x180010478  mov     r8d, 1
0x18001047e  mov     ecx, r8d
0x180010481  lock xadd [rbx+8], ecx
0x180010486  add     ecx, r8d
0x180010489  cmp     ecx, r8d
0x18001048c  jz      loc_180010590
0x180010492  mov     [rsp+200h+var_1A0], rsi
0x180010497  mov     rdx, rsi
0x18001049a  mov     rcx, rbx
0x18001049d  mov     r14, [r15+40h]
0x1800104a1  xorps   xmm0, xmm0
0x1800104a4  movdqu  [rsp+200h+var_1C0+8], xmm0
0x1800104aa  test    rcx, rcx
0x1800104ad  jz      short loc_1800104CD
0x1800104af  mov     eax, r8d
0x1800104b2  lock xadd [rcx+8], eax
0x1800104b7  add     eax, r8d
0x1800104ba  cmp     eax, r8d
0x1800104bd  jz      loc_180010586
0x1800104c3  mov     qword ptr [rsp+200h+var_1C0+8], rcx
0x1800104c8  mov     qword ptr [rsp+200h+var_1B0], rdx
0x1800104cd  lea     rax, [rsp+200h+var_1C0+8]
0x1800104d2  mov     qword ptr [rsp+200h+var_1C0], rax
0x1800104d7  cmp     [r14+2Ch], r13b
0x1800104db  jnz     loc_1800106F1
0x1800104e1  lea     rcx, [r14+190h]
0x1800104e8  lea     rdx, [rsp+200h+var_1C0+8]
0x1800104ed  call    ?push_back@?$deque@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@QEAAXAEBV?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@Z; std::deque<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>>::push_back(win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>> const &)
0x1800104f2  lea     rcx, [r14+28h]
0x1800104f6  call    ?TestDerecurse@?$MessageHandlerCoordinator@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$type_list@V?$KeyedMessageHandler@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VUriHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVUriHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@UUriExtractor@MetroConsumptionState@consumption@6@@win_musl@@V?$type_list@V?$BroadcastMessageHandler@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$EventHandler@VBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@V?$scope@PEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$scope@PEAVBroadcastHandlerBase@MetroConsumptionState@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@6@@win_musl@@@win_musl@@Vnull_type@win_mp_lib@@@win_mp_lib@@@win_mp_lib@@@win_musl@@AEAAXXZ; win_musl::MessageHandlerCoordinator<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_mp_lib::type_list<win_musl::KeyedMessageHandler<std::wstring,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::UriHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::UriHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>,win_musl::consumption::MetroConsumptionState::UriExtractor>,win_mp_lib::type_list<win_musl::BroadcastMessageHandler<win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_musl::EventHandler<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase,win_scope::scope<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder *,win_scope::const_policies<win_scope::shared_policies>>,win_scope::scope<win_musl::consumption::MetroConsumptionState::BroadcastHandlerBase *,win_scope::const_policies<win_scope::shared_policies>>>>,win_mp_lib::null_type>>>::TestDerecurse(void)
0x1800104fb  nop
0x1800104fc  cmp     qword ptr [rsp+200h+var_1B0], r13
0x180010501  jz      short loc_180010515
0x180010503  cmp     qword ptr [rsp+200h+var_1C0+8], r13
0x180010508  jz      short loc_180010515
0x18001050a  lea     rcx, [rsp+200h+var_1C0+8]
0x18001050f  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180010514  nop
0x180010515  test    rbx, rbx
0x180010518  jz      short loc_18001052A
0x18001051a  test    rsi, rsi
0x18001051d  jz      short loc_18001052A
0x18001051f  lea     rcx, [rsp+200h+var_1B0+8]
0x180010524  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x180010529  nop
0x18001052a  add     dword ptr [rdi+2Ch], 0FFFFFFFFh
0x18001052e  jnz     short loc_180010534
0x180010530  mov     [rdi+28h], r13d
0x180010534  mov     rcx, rdi; lpCriticalSection
0x180010537  call    cs:__imp_LeaveCriticalSection
0x18001053d  nop
0x18001053e  cmp     [rbp+100h+var_158], 8
0x180010543  jnb     short loc_18001059A
0x180010545  mov     rcx, [rsp+200h+var_190]
0x18001054a  test    rcx, rcx
0x18001054d  jz      short loc_18001055C
0x18001054f  mov     rax, [rcx]
0x180010552  mov     rax, [rax+10h]
0x180010556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001055b  nop
0x18001055c  mov     rcx, [rbp+100h+var_40]
0x180010563  xor     rcx, rsp; StackCookie
0x180010566  call    __security_check_cookie
0x18001056b  mov     rbx, [rsp+200h+arg_18]
0x180010573  add     rsp, 1D0h
0x18001057a  pop     r15
0x18001057c  pop     r14
0x18001057e  pop     r13
0x180010580  pop     r12
0x180010582  pop     rdi
0x180010583  pop     rsi
0x180010584  pop     rbp
0x180010585  retn
0x180010586  lock add [rcx+0Ch], r8d
0x18001058b  jmp     loc_1800104C3
0x180010590  lock add [rbx+0Ch], r8d
0x180010595  jmp     loc_180010492
0x18001059a  mov     rcx, [rbp+100h+Destination]; Block
0x18001059e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800105a3  jmp     short loc_180010545
0x1800105a5  mov     qword ptr [rsp+200h+var_1C0], rax
0x1800105aa  mov     qword ptr [rsp+200h+var_1E0], r12
0x1800105af  lea     r9, [rsp+200h+var_198]
0x1800105b4  mov     r8d, r14d
0x1800105b7  lea     rdx, [rbp+100h+var_178]
0x1800105bb  mov     rcx, rax
0x1800105be  call    ??0ByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@W4__MIDL___MIDL_itf_opc2Eio_0000_0000_0002@@AEAVByteCollection@win_dox@@PEBU__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005@@@Z; win_musl::consumption::MetroConsumptionState::ByteCollectionHolder::ByteCollectionHolder(std::wstring const &,__MIDL___MIDL_itf_opc2Eio_0000_0000_0002,win_dox::ByteCollection &,__MIDL___MIDL_itf_win72Edox2Ebase_0000_0000_0005 const *)
0x1800105c3  mov     rsi, rax
0x1800105c6  xorps   xmm0, xmm0
0x1800105c9  movdqu  [rsp+200h+var_1B0+8], xmm0
0x1800105cf  mov     qword ptr [rsp+200h+var_1C0], rax
0x1800105d4  test    rax, rax
0x1800105d7  jnz     loc_180010444
0x1800105dd  mov     rcx, r13
0x1800105e0  mov     rdx, r13
0x1800105e3  mov     rsi, [rsp+200h+var_1A0]
0x1800105e8  mov     rbx, qword ptr [rsp+200h+var_1B0+8]
0x1800105ed  lea     r8d, [rax+1]
0x1800105f1  jmp     loc_18001049D
0x1800105f6  mov     dword ptr [rsp+200h+var_1C8], r13d
0x1800105fb  lea     rax, aLogicalitemnam; "logicalItemName"
0x180010602  mov     [rsp+200h+var_1D0], rax
0x180010607  lea     rax, aAddpart; "AddPart"
0x18001060e  mov     qword ptr [rsp+200h+var_1D8], rax
0x180010613  lea     rax, aIwin7internalp; "IWin7InternalPartReceiver"
0x18001061a  mov     qword ptr [rsp+200h+var_1E0], rax
0x18001061f  mov     r9d, 36h ; '6'
0x180010625  lea     rdx, aNoFilename; "(no filename)"
0x18001062c  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180010632  cmp     r14d, 1
0x180010636  jz      loc_180010242
0x18001063c  cmp     r14d, 2
0x180010640  jz      loc_180010242
0x180010646  mov     dword ptr [rsp+200h+var_1C8], 2
0x18001064e  lea     rax, aCompressionopt_2; "compressionOptions"
0x180010655  mov     [rsp+200h+var_1D0], rax
0x18001065a  lea     rax, aAddpart; "AddPart"
0x180010661  mov     qword ptr [rsp+200h+var_1D8], rax
0x180010666  lea     rax, aIwin7internalp; "IWin7InternalPartReceiver"
0x18001066d  mov     qword ptr [rsp+200h+var_1E0], rax
0x180010672  mov     r9d, 45h ; 'E'
0x180010678  lea     rdx, aNoFilename; "(no filename)"
0x18001067f  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180010685  mov     dword ptr [rsp+200h+var_1C8], r13d
0x18001068a  lea     rax, aPiinternalbyte; "pIInternalByteCollection"
0x180010691  mov     [rsp+200h+var_1D0], rax
0x180010696  lea     rax, aAddpart; "AddPart"
0x18001069d  mov     qword ptr [rsp+200h+var_1D8], rax
0x1800106a2  lea     rax, aIwin7internalp; "IWin7InternalPartReceiver"
0x1800106a9  mov     qword ptr [rsp+200h+var_1E0], rax
0x1800106ae  mov     r9d, 4Ch ; 'L'
0x1800106b4  lea     rdx, aNoFilename; "(no filename)"
0x1800106bb  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x1800106c1  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x1800106c6  mov     r8, [rbp+100h+var_160]
0x1800106ca  jmp     loc_1800103FC
0x1800106cf  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x1800106d4  mov     rdx, [rbp+100h+var_158]
0x1800106d8  mov     r8, [rbp+100h+var_160]
0x1800106dc  jmp     loc_18001032E
0x1800106e1  lea     rcx, [rsp+200h+var_1C0]
0x1800106e6  call    ??$close@VByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@@close_delete@win_scope@@SAXPEAPEAVByteCollectionHolder@MetroConsumptionState@consumption@win_musl@@@Z; win_scope::close_delete::close<win_musl::consumption::MetroConsumptionState::ByteCollectionHolder>(win_musl::consumption::MetroConsumptionState::ByteCollectionHolder * *)
0x1800106eb  call    ?report_init_failure@report_policy_throw@win_scope@@SAXXZ; win_scope::report_policy_throw::report_init_failure(void)
0x1800106f1  lea     rax, aNoMoreMessages; "no more messages allowed"
0x1800106f8  mov     [rsp+200h+var_1D0], rax; struct win_musl::TStringEllipseBase *
  ... truncated ...
```
