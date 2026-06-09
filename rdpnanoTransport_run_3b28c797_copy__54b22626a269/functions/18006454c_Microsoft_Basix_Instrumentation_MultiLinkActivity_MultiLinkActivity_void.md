# Microsoft::Basix::Instrumentation::MultiLinkActivity::MultiLinkActivity(void)

- ea: `0x18006454c`
- end: `0x18006494b`
- name: `??0MultiLinkActivity@Instrumentation@Basix@Microsoft@@QEAA@XZ`
- size: `1023`
- prototype: `__int64 __fastcall(Microsoft::Basix::Instrumentation::MultiLinkActivity *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180099fa8`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180025fc0`
- `0x180026ba8`
- `0x18032f050`

## string_xrefs

- `0x180064606`: `Unique identifier generated for links created in SMILES for a given connection`
- `0x18006462c`: `LinkId`
- `0x1800648ce`: `Additional data as string in JSON format`
- `0x180064586`: `LinkId: %1%, LinkChangeId: %2%, State: %3%, Delay: %4%, PredecessorLinkChangeID: %5%, PoolCount: %6%, Props: %7%`
- `0x1800645ac`: `Microsoft::Basix::Instrumentation::MultiLinkActivity`
- `0x180064684`: `Unique identifier for every row in this table. This will be used to track the link switches`
- `0x1800646aa`: `LinkChangeId`
- `0x1800646fb`: `Operation representing various states the SMILES link goes through - LinkAdded, LinkPrimary, LinkDropped, LinkClosed or LinkUpdate`
- `0x1800647e8`: `Id of previous active link (Row Id). This will be populated only when link switching happens`
- `0x18006480c`: `PredecessorLinkChangeId`
- `0x18006485b`: `Number of SMILES links exist for a given connection.`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
Microsoft::Basix::Instrumentation::MultiLinkActivity *__fastcall Microsoft::Basix::Instrumentation::MultiLinkActivity::MultiLinkActivity(
        Microsoft::Basix::Instrumentation::MultiLinkActivity *this)
{
  __int128 v3; // [rsp+20h] [rbp-40h] BYREF
  __int128 v4; // [rsp+30h] [rbp-30h]
  __int128 v5; // [rsp+40h] [rbp-20h] BYREF
  __int128 v6; // [rsp+50h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+8h] BYREF

  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(
    &v5,
    "LinkId: %1%, LinkChangeId: %2%, State: %3%, Delay: %4%, PredecessorLinkChangeID: %5%, PoolCount: %6%, Props: %7%",
    (unsigned int)&retaddr + 16);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Microsoft::Basix::Instrumentation::MultiLinkActivity", 52);
  Microsoft::Basix::Instrumentation::RecordDescriptor::RecordDescriptor(this, &v3, 4, &v5);
  std::string::_Tidy_deallocate(&v3);
  std::string::_Tidy_deallocate(&v5);
  *(_QWORD *)this = &Microsoft::Basix::Instrumentation::MultiLinkActivity::`vftable';
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(
    &v3,
    "Unique identifier generated for links created in SMILES for a given connection",
    78);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "LinkId", 6);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 344,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(
    &v3,
    "Unique identifier for every row in this table. This will be used to track the link switches",
    91);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "LinkChangeId", 12);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 416,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(
    &v3,
    "Operation representing various states the SMILES link goes through - LinkAdded, LinkPrimary, LinkDropped, LinkClosed or LinkUpdate",
    130);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "State", 5);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 488,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Delay/latency in milliseconds", 29);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "Delay", 5);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 560,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(
    &v3,
    "Id of previous active link (Row Id). This will be populated only when link switching happens",
    92);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "PredecessorLinkChangeId", 23);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 632,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Number of SMILES links exist for a given connection.", 52);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "PoolCount", 9);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 704,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Additional data as string in JSON format", 40);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "Props", 5);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 776,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  return this;
}

```

## disassembly

```asm
0x18006454c  mov     rax, rsp
0x18006454f  mov     [rax+10h], rbx
0x180064553  mov     [rax+18h], rsi
0x180064557  mov     [rax+20h], rdi
0x18006455b  mov     [rax+8], rcx
0x18006455f  push    rbp
0x180064560  mov     rbp, rsp
0x180064563  mov     eax, 60h
0x180064568  call    _alloca_probe
0x18006456d  sub     rsp, rax
0x180064570  mov     rbx, rcx
0x180064573  xorps   xmm0, xmm0
0x180064576  movups  [rbp+var_20], xmm0
0x18006457a  xorps   xmm1, xmm1
0x18006457d  movdqu  [rbp+var_10], xmm1
0x180064582  lea     r8d, [rax+10h]
0x180064586  lea     rdx, aLinkid1Linkcha; "LinkId: %1%, LinkChangeId: %2%, State: "...
0x18006458d  lea     rcx, [rbp+var_20]
0x180064591  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064596  nop
0x180064597  xorps   xmm0, xmm0
0x18006459a  movups  [rbp+var_40], xmm0
0x18006459e  xorps   xmm1, xmm1
0x1800645a1  movdqu  [rbp+var_30], xmm1
0x1800645a6  mov     r8d, 34h ; '4'
0x1800645ac  lea     rdx, aMicrosoftBasix_42; "Microsoft::Basix::Instrumentation::Mult"...
0x1800645b3  lea     rcx, [rbp+var_40]
0x1800645b7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800645bc  nop
0x1800645bd  lea     r9, [rbp+var_20]
0x1800645c1  mov     r8d, 4
0x1800645c7  lea     rdx, [rbp+var_40]
0x1800645cb  mov     rcx, rbx
0x1800645ce  call    ??0RecordDescriptor@Instrumentation@Basix@Microsoft@@IEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Level@0123@0@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::RecordDescriptor(std::string const &,Microsoft::Basix::Instrumentation::RecordDescriptor::Level,std::string const &)
0x1800645d3  nop
0x1800645d4  lea     rcx, [rbp+var_40]
0x1800645d8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800645dd  nop
0x1800645de  lea     rcx, [rbp+var_20]
0x1800645e2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800645e7  lea     rax, ??_7MultiLinkActivity@Instrumentation@Basix@Microsoft@@6B@; const Microsoft::Basix::Instrumentation::MultiLinkActivity::`vftable'
0x1800645ee  mov     [rbx], rax
0x1800645f1  xorps   xmm0, xmm0
0x1800645f4  movups  [rbp+var_40], xmm0
0x1800645f8  xorps   xmm1, xmm1
0x1800645fb  movdqu  [rbp+var_30], xmm1
0x180064600  mov     r8d, 4Eh ; 'N'
0x180064606  lea     rdx, aUniqueIdentifi_0; "Unique identifier generated for links c"...
0x18006460d  lea     rcx, [rbp+var_40]
0x180064611  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064616  nop
0x180064617  xorps   xmm0, xmm0
0x18006461a  movups  [rbp+var_20], xmm0
0x18006461e  xorps   xmm1, xmm1
0x180064621  movdqu  [rbp+var_10], xmm1
0x180064626  mov     r8d, 6
0x18006462c  lea     rdx, aLinkid; "LinkId"
0x180064633  lea     rcx, [rbp+var_20]
0x180064637  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006463c  nop
0x18006463d  lea     rcx, [rbx+158h]
0x180064644  lea     r9, [rbp+var_40]
0x180064648  lea     r8, [rbp+var_20]
0x18006464c  lea     rsi, ??_R0I@8; uint `RTTI Type Descriptor'
0x180064653  mov     rdx, rsi
0x180064656  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18006465b  nop
0x18006465c  lea     rcx, [rbp+var_20]
0x180064660  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064665  nop
0x180064666  lea     rcx, [rbp+var_40]
0x18006466a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006466f  xorps   xmm0, xmm0
0x180064672  movups  [rbp+var_40], xmm0
0x180064676  xorps   xmm1, xmm1
0x180064679  movdqu  [rbp+var_30], xmm1
0x18006467e  mov     r8d, 5Bh ; '['
0x180064684  lea     rdx, aUniqueIdentifi_1; "Unique identifier for every row in this"...
0x18006468b  lea     rcx, [rbp+var_40]
0x18006468f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064694  nop
0x180064695  xorps   xmm0, xmm0
0x180064698  movups  [rbp+var_20], xmm0
0x18006469c  xorps   xmm1, xmm1
0x18006469f  movdqu  [rbp+var_10], xmm1
0x1800646a4  mov     r8d, 0Ch
0x1800646aa  lea     rdx, aLinkchangeid; "LinkChangeId"
0x1800646b1  lea     rcx, [rbp+var_20]
0x1800646b5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800646ba  nop
0x1800646bb  lea     rcx, [rbx+1A0h]
0x1800646c2  lea     r9, [rbp+var_40]
0x1800646c6  lea     r8, [rbp+var_20]
0x1800646ca  mov     rdx, rsi
0x1800646cd  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x1800646d2  nop
0x1800646d3  lea     rcx, [rbp+var_20]
0x1800646d7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800646dc  nop
0x1800646dd  lea     rcx, [rbp+var_40]
0x1800646e1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800646e6  xorps   xmm0, xmm0
0x1800646e9  movups  [rbp+var_40], xmm0
0x1800646ed  xorps   xmm1, xmm1
0x1800646f0  movdqu  [rbp+var_30], xmm1
0x1800646f5  mov     r8d, 82h
0x1800646fb  lea     rdx, aOperationRepre; "Operation representing various states t"...
0x180064702  lea     rcx, [rbp+var_40]
0x180064706  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006470b  nop
0x18006470c  xorps   xmm0, xmm0
0x18006470f  movups  [rbp+var_20], xmm0
0x180064713  xorps   xmm1, xmm1
0x180064716  movdqu  [rbp+var_10], xmm1
0x18006471b  mov     edi, 5
0x180064720  mov     r8d, edi
0x180064723  lea     rdx, aState; "State"
0x18006472a  lea     rcx, [rbp+var_20]
0x18006472e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064733  nop
0x180064734  lea     rcx, [rbx+1E8h]
0x18006473b  lea     r9, [rbp+var_40]
0x18006473f  lea     r8, [rbp+var_20]
0x180064743  lea     rdx, ??_R0?AVEncodedString@Instrumentation@Basix@Microsoft@@@8; Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor'
0x18006474a  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18006474f  nop
0x180064750  lea     rcx, [rbp+var_20]
0x180064754  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064759  nop
0x18006475a  lea     rcx, [rbp+var_40]
0x18006475e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064763  xorps   xmm0, xmm0
0x180064766  movups  [rbp+var_40], xmm0
0x18006476a  xorps   xmm1, xmm1
0x18006476d  movdqu  [rbp+var_30], xmm1
0x180064772  lea     r8d, [rdi+18h]
0x180064776  lea     rdx, aDelayLatencyIn; "Delay/latency in milliseconds"
0x18006477d  lea     rcx, [rbp+var_40]
0x180064781  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064786  nop
0x180064787  xorps   xmm0, xmm0
0x18006478a  movups  [rbp+var_20], xmm0
0x18006478e  xorps   xmm1, xmm1
0x180064791  movdqu  [rbp+var_10], xmm1
0x180064796  mov     r8d, edi
0x180064799  lea     rdx, aDelay_0; "Delay"
0x1800647a0  lea     rcx, [rbp+var_20]
0x1800647a4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800647a9  nop
0x1800647aa  lea     rcx, [rbx+230h]
0x1800647b1  lea     r9, [rbp+var_40]
0x1800647b5  lea     r8, [rbp+var_20]
0x1800647b9  mov     rdx, rsi
0x1800647bc  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x1800647c1  nop
0x1800647c2  lea     rcx, [rbp+var_20]
0x1800647c6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800647cb  nop
0x1800647cc  lea     rcx, [rbp+var_40]
0x1800647d0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800647d5  xorps   xmm0, xmm0
0x1800647d8  movups  [rbp+var_40], xmm0
0x1800647dc  xorps   xmm1, xmm1
0x1800647df  movdqu  [rbp+var_30], xmm1
0x1800647e4  lea     r8d, [rdi+57h]
0x1800647e8  lea     rdx, aIdOfPreviousAc; "Id of previous active link (Row Id). Th"...
0x1800647ef  lea     rcx, [rbp+var_40]
0x1800647f3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800647f8  nop
0x1800647f9  xorps   xmm0, xmm0
0x1800647fc  movups  [rbp+var_20], xmm0
0x180064800  xorps   xmm1, xmm1
0x180064803  movdqu  [rbp+var_10], xmm1
0x180064808  lea     r8d, [rdi+12h]
0x18006480c  lea     rdx, aPredecessorlin; "PredecessorLinkChangeId"
0x180064813  lea     rcx, [rbp+var_20]
0x180064817  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006481c  nop
0x18006481d  lea     rcx, [rbx+278h]
0x180064824  lea     r9, [rbp+var_40]
0x180064828  lea     r8, [rbp+var_20]
0x18006482c  mov     rdx, rsi
0x18006482f  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180064834  nop
0x180064835  lea     rcx, [rbp+var_20]
0x180064839  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006483e  nop
0x18006483f  lea     rcx, [rbp+var_40]
0x180064843  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064848  xorps   xmm0, xmm0
0x18006484b  movups  [rbp+var_40], xmm0
0x18006484f  xorps   xmm1, xmm1
0x180064852  movdqu  [rbp+var_30], xmm1
0x180064857  lea     r8d, [rdi+2Fh]
0x18006485b  lea     rdx, aNumberOfSmiles; "Number of SMILES links exist for a give"...
0x180064862  lea     rcx, [rbp+var_40]
0x180064866  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006486b  nop
0x18006486c  xorps   xmm0, xmm0
0x18006486f  movups  [rbp+var_20], xmm0
0x180064873  xorps   xmm1, xmm1
0x180064876  movdqu  [rbp+var_10], xmm1
0x18006487b  lea     r8d, [rdi+4]
0x18006487f  lea     rdx, aPoolcount; "PoolCount"
0x180064886  lea     rcx, [rbp+var_20]
0x18006488a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006488f  nop
0x180064890  lea     rcx, [rbx+2C0h]
0x180064897  lea     r9, [rbp+var_40]
0x18006489b  lea     r8, [rbp+var_20]
0x18006489f  mov     rdx, rsi
0x1800648a2  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x1800648a7  nop
0x1800648a8  lea     rcx, [rbp+var_20]
0x1800648ac  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800648b1  nop
0x1800648b2  lea     rcx, [rbp+var_40]
0x1800648b6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800648bb  xorps   xmm0, xmm0
0x1800648be  movups  [rbp+var_40], xmm0
0x1800648c2  xorps   xmm1, xmm1
0x1800648c5  movdqu  [rbp+var_30], xmm1
0x1800648ca  lea     r8d, [rdi+23h]
0x1800648ce  lea     rdx, aAdditionalData; "Additional data as string in JSON forma"...
0x1800648d5  lea     rcx, [rbp+var_40]
0x1800648d9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800648de  nop
0x1800648df  xorps   xmm0, xmm0
0x1800648e2  movups  [rbp+var_20], xmm0
0x1800648e6  xorps   xmm1, xmm1
0x1800648e9  movdqu  [rbp+var_10], xmm1
0x1800648ee  mov     r8d, edi
0x1800648f1  lea     rdx, aProps; "Props"
0x1800648f8  lea     rcx, [rbp+var_20]
0x1800648fc  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064901  nop
0x180064902  lea     rcx, [rbx+308h]
0x180064909  lea     r9, [rbp+var_40]
0x18006490d  lea     r8, [rbp+var_20]
0x180064911  lea     rdx, ??_R0?AVEncodedString@Instrumentation@Basix@Microsoft@@@8; Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor'
0x180064918  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18006491d  nop
0x18006491e  lea     rcx, [rbp+var_20]
0x180064922  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064927  nop
0x180064928  lea     rcx, [rbp+var_40]
0x18006492c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064931  nop
0x180064932  mov     rax, rbx
0x180064935  lea     r11, [rsp+60h+var_s0]
0x18006493a  mov     rbx, [r11+18h]
0x18006493e  mov     rsi, [r11+20h]
0x180064942  mov     rdi, [r11+28h]
0x180064946  mov     rsp, r11
0x180064949  pop     rbp
0x18006494a  retn
```
