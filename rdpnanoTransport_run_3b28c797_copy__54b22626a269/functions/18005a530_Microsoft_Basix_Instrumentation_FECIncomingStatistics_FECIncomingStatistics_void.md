# Microsoft::Basix::Instrumentation::FECIncomingStatistics::FECIncomingStatistics(void)

- ea: `0x18005a530`
- end: `0x18005a925`
- name: `??0FECIncomingStatistics@Instrumentation@Basix@Microsoft@@QEAA@XZ`
- size: `1013`
- prototype: `__int64 __fastcall(Microsoft::Basix::Instrumentation::FECIncomingStatistics *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800989c8`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180025fc0`
- `0x180026ba8`
- `0x18032f050`

## string_xrefs

- `0x18005a56a`: `FEC Incoming Statistics: CID=%1%, N=%2%, F=%3%, R=%4%, L=%7%, BOK=%5%, BFAIL=%6%`
- `0x18005a590`: `Microsoft::Basix::Instrumentation::FECIncomingStatistics`
- `0x18005a68e`: `IncomingDataPacketCount`
- `0x18005a705`: `IncomingFECPacketCount`
- `0x18005a777`: `IncomingRecoveredPacketCount`
- `0x18005a7e9`: `IncomingFECNoErrorBlocksCount`
- `0x18005a85c`: `IncomingFECNonRecoverableBlocksCount`
- `0x18005a8cf`: `IncomingMissingDataPacketCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
Microsoft::Basix::Instrumentation::FECIncomingStatistics *__fastcall Microsoft::Basix::Instrumentation::FECIncomingStatistics::FECIncomingStatistics(
        Microsoft::Basix::Instrumentation::FECIncomingStatistics *this)
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
    "FEC Incoming Statistics: CID=%1%, N=%2%, F=%3%, R=%4%, L=%7%, BOK=%5%, BFAIL=%6%",
    (unsigned int)&retaddr - 16);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Microsoft::Basix::Instrumentation::FECIncomingStatistics", 56);
  Microsoft::Basix::Instrumentation::RecordDescriptor::RecordDescriptor(this, &v3, 5, &v5);
  std::string::_Tidy_deallocate(&v3);
  std::string::_Tidy_deallocate(&v5);
  *(_QWORD *)this = &Microsoft::Basix::Instrumentation::FECIncomingStatistics::`vftable';
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "The channel ID", 14);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ChannelId", 9);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 344,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "The number of data packets that were received", 45);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "IncomingDataPacketCount", 23);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 416,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "The number of FEC packets that were received", 44);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "IncomingFECPacketCount", 22);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 488,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "The number of data packets that we recovered", 44);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "IncomingRecoveredPacketCount", 28);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 560,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "The number of FEC blocks that have no errors", 44);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "IncomingFECNoErrorBlocksCount", 29);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 632,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "The number of FEC blocks that have too many missing packets", 59);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "IncomingFECNonRecoverableBlocksCount", 36);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 704,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "The number of packets that could not be recovered", 49);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "IncomingMissingDataPacketCount", 30);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 776,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  return this;
}

```

## disassembly

```asm
0x18005a530  mov     rax, rsp
0x18005a533  mov     [rax+10h], rbx
0x18005a537  mov     [rax+18h], rsi
0x18005a53b  mov     [rax+20h], rdi
0x18005a53f  mov     [rax+8], rcx
0x18005a543  push    rbp
0x18005a544  mov     rbp, rsp
0x18005a547  mov     eax, 60h
0x18005a54c  call    _alloca_probe
0x18005a551  sub     rsp, rax
0x18005a554  mov     rbx, rcx
0x18005a557  xorps   xmm0, xmm0
0x18005a55a  movups  [rbp+var_20], xmm0
0x18005a55e  xorps   xmm1, xmm1
0x18005a561  movdqu  [rbp+var_10], xmm1
0x18005a566  lea     r8d, [rax-10h]
0x18005a56a  lea     rdx, aFecIncomingSta; "FEC Incoming Statistics: CID=%1%, N=%2%"...
0x18005a571  lea     rcx, [rbp+var_20]
0x18005a575  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a57a  nop
0x18005a57b  xorps   xmm0, xmm0
0x18005a57e  movups  [rbp+var_40], xmm0
0x18005a582  xorps   xmm1, xmm1
0x18005a585  movdqu  [rbp+var_30], xmm1
0x18005a58a  mov     r8d, 38h ; '8'
0x18005a590  lea     rdx, aMicrosoftBasix_53; "Microsoft::Basix::Instrumentation::FECI"...
0x18005a597  lea     rcx, [rbp+var_40]
0x18005a59b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a5a0  nop
0x18005a5a1  lea     r9, [rbp+var_20]
0x18005a5a5  mov     r8d, 5
0x18005a5ab  lea     rdx, [rbp+var_40]
0x18005a5af  mov     rcx, rbx
0x18005a5b2  call    ??0RecordDescriptor@Instrumentation@Basix@Microsoft@@IEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Level@0123@0@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::RecordDescriptor(std::string const &,Microsoft::Basix::Instrumentation::RecordDescriptor::Level,std::string const &)
0x18005a5b7  nop
0x18005a5b8  lea     rcx, [rbp+var_40]
0x18005a5bc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a5c1  nop
0x18005a5c2  lea     rcx, [rbp+var_20]
0x18005a5c6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a5cb  lea     rax, ??_7FECIncomingStatistics@Instrumentation@Basix@Microsoft@@6B@; const Microsoft::Basix::Instrumentation::FECIncomingStatistics::`vftable'
0x18005a5d2  mov     [rbx], rax
0x18005a5d5  xorps   xmm0, xmm0
0x18005a5d8  movups  [rbp+var_40], xmm0
0x18005a5dc  xorps   xmm1, xmm1
0x18005a5df  movdqu  [rbp+var_30], xmm1
0x18005a5e4  mov     r8d, 0Eh
0x18005a5ea  lea     rdx, aTheChannelId; "The channel ID"
0x18005a5f1  lea     rcx, [rbp+var_40]
0x18005a5f5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a5fa  nop
0x18005a5fb  xorps   xmm0, xmm0
0x18005a5fe  movups  [rbp+var_20], xmm0
0x18005a602  xorps   xmm1, xmm1
0x18005a605  movdqu  [rbp+var_10], xmm1
0x18005a60a  mov     r8d, 9
0x18005a610  lea     rdx, aChannelid_0; "ChannelId"
0x18005a617  lea     rcx, [rbp+var_20]
0x18005a61b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a620  nop
0x18005a621  lea     rcx, [rbx+158h]
0x18005a628  lea     r9, [rbp+var_40]
0x18005a62c  lea     r8, [rbp+var_20]
0x18005a630  lea     rsi, ??_R0I@8; uint `RTTI Type Descriptor'
0x18005a637  mov     rdx, rsi
0x18005a63a  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18005a63f  nop
0x18005a640  lea     rcx, [rbp+var_20]
0x18005a644  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a649  nop
0x18005a64a  lea     rcx, [rbp+var_40]
0x18005a64e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a653  xorps   xmm0, xmm0
0x18005a656  movups  [rbp+var_40], xmm0
0x18005a65a  xorps   xmm1, xmm1
0x18005a65d  movdqu  [rbp+var_30], xmm1
0x18005a662  mov     r8d, 2Dh ; '-'
0x18005a668  lea     rdx, aTheNumberOfDat_1; "The number of data packets that were re"...
0x18005a66f  lea     rcx, [rbp+var_40]
0x18005a673  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a678  nop
0x18005a679  xorps   xmm0, xmm0
0x18005a67c  movups  [rbp+var_20], xmm0
0x18005a680  xorps   xmm1, xmm1
0x18005a683  movdqu  [rbp+var_10], xmm1
0x18005a688  mov     r8d, 17h
0x18005a68e  lea     rdx, aIncomingdatapa; "IncomingDataPacketCount"
0x18005a695  lea     rcx, [rbp+var_20]
0x18005a699  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a69e  nop
0x18005a69f  lea     rcx, [rbx+1A0h]
0x18005a6a6  lea     r9, [rbp+var_40]
0x18005a6aa  lea     r8, [rbp+var_20]
0x18005a6ae  mov     rdx, rsi
0x18005a6b1  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18005a6b6  nop
0x18005a6b7  lea     rcx, [rbp+var_20]
0x18005a6bb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a6c0  nop
0x18005a6c1  lea     rcx, [rbp+var_40]
0x18005a6c5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a6ca  xorps   xmm0, xmm0
0x18005a6cd  movups  [rbp+var_40], xmm0
0x18005a6d1  xorps   xmm1, xmm1
0x18005a6d4  movdqu  [rbp+var_30], xmm1
0x18005a6d9  mov     edi, 2Ch ; ','
0x18005a6de  mov     r8d, edi
0x18005a6e1  lea     rdx, aTheNumberOfFec; "The number of FEC packets that were rec"...
0x18005a6e8  lea     rcx, [rbp+var_40]
0x18005a6ec  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a6f1  nop
0x18005a6f2  xorps   xmm0, xmm0
0x18005a6f5  movups  [rbp+var_20], xmm0
0x18005a6f9  xorps   xmm1, xmm1
0x18005a6fc  movdqu  [rbp+var_10], xmm1
0x18005a701  lea     r8d, [rdi-16h]
0x18005a705  lea     rdx, aIncomingfecpac; "IncomingFECPacketCount"
0x18005a70c  lea     rcx, [rbp+var_20]
0x18005a710  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a715  nop
0x18005a716  lea     rcx, [rbx+1E8h]
0x18005a71d  lea     r9, [rbp+var_40]
0x18005a721  lea     r8, [rbp+var_20]
0x18005a725  mov     rdx, rsi
0x18005a728  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18005a72d  nop
0x18005a72e  lea     rcx, [rbp+var_20]
0x18005a732  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a737  nop
0x18005a738  lea     rcx, [rbp+var_40]
0x18005a73c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a741  xorps   xmm0, xmm0
0x18005a744  movups  [rbp+var_40], xmm0
0x18005a748  xorps   xmm1, xmm1
0x18005a74b  movdqu  [rbp+var_30], xmm1
0x18005a750  mov     r8d, edi
0x18005a753  lea     rdx, aTheNumberOfDat; "The number of data packets that we reco"...
0x18005a75a  lea     rcx, [rbp+var_40]
0x18005a75e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a763  nop
0x18005a764  xorps   xmm0, xmm0
0x18005a767  movups  [rbp+var_20], xmm0
0x18005a76b  xorps   xmm1, xmm1
0x18005a76e  movdqu  [rbp+var_10], xmm1
0x18005a773  lea     r8d, [rdi-10h]
0x18005a777  lea     rdx, aIncomingrecove; "IncomingRecoveredPacketCount"
0x18005a77e  lea     rcx, [rbp+var_20]
0x18005a782  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a787  nop
0x18005a788  lea     rcx, [rbx+230h]
0x18005a78f  lea     r9, [rbp+var_40]
0x18005a793  lea     r8, [rbp+var_20]
0x18005a797  mov     rdx, rsi
0x18005a79a  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18005a79f  nop
0x18005a7a0  lea     rcx, [rbp+var_20]
0x18005a7a4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a7a9  nop
0x18005a7aa  lea     rcx, [rbp+var_40]
0x18005a7ae  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a7b3  xorps   xmm0, xmm0
0x18005a7b6  movups  [rbp+var_40], xmm0
0x18005a7ba  xorps   xmm1, xmm1
0x18005a7bd  movdqu  [rbp+var_30], xmm1
0x18005a7c2  mov     r8d, edi
0x18005a7c5  lea     rdx, aTheNumberOfFec_1; "The number of FEC blocks that have no e"...
0x18005a7cc  lea     rcx, [rbp+var_40]
0x18005a7d0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a7d5  nop
0x18005a7d6  xorps   xmm0, xmm0
0x18005a7d9  movups  [rbp+var_20], xmm0
0x18005a7dd  xorps   xmm1, xmm1
0x18005a7e0  movdqu  [rbp+var_10], xmm1
0x18005a7e5  lea     r8d, [rdi-0Fh]
0x18005a7e9  lea     rdx, aIncomingfecnoe; "IncomingFECNoErrorBlocksCount"
0x18005a7f0  lea     rcx, [rbp+var_20]
0x18005a7f4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a7f9  nop
0x18005a7fa  lea     rcx, [rbx+278h]
0x18005a801  lea     r9, [rbp+var_40]
0x18005a805  lea     r8, [rbp+var_20]
0x18005a809  mov     rdx, rsi
0x18005a80c  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18005a811  nop
0x18005a812  lea     rcx, [rbp+var_20]
0x18005a816  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a81b  nop
0x18005a81c  lea     rcx, [rbp+var_40]
0x18005a820  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a825  xorps   xmm0, xmm0
0x18005a828  movups  [rbp+var_40], xmm0
0x18005a82c  xorps   xmm1, xmm1
0x18005a82f  movdqu  [rbp+var_30], xmm1
0x18005a834  lea     r8d, [rdi+0Fh]
0x18005a838  lea     rdx, aTheNumberOfFec_0; "The number of FEC blocks that have too "...
0x18005a83f  lea     rcx, [rbp+var_40]
0x18005a843  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a848  nop
0x18005a849  xorps   xmm0, xmm0
0x18005a84c  movups  [rbp+var_20], xmm0
0x18005a850  xorps   xmm1, xmm1
0x18005a853  movdqu  [rbp+var_10], xmm1
0x18005a858  lea     r8d, [rdi-8]
0x18005a85c  lea     rdx, aIncomingfecnon; "IncomingFECNonRecoverableBlocksCount"
0x18005a863  lea     rcx, [rbp+var_20]
0x18005a867  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a86c  nop
0x18005a86d  lea     rcx, [rbx+2C0h]
0x18005a874  lea     r9, [rbp+var_40]
0x18005a878  lea     r8, [rbp+var_20]
0x18005a87c  mov     rdx, rsi
0x18005a87f  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18005a884  nop
0x18005a885  lea     rcx, [rbp+var_20]
0x18005a889  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a88e  nop
0x18005a88f  lea     rcx, [rbp+var_40]
0x18005a893  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a898  xorps   xmm0, xmm0
0x18005a89b  movups  [rbp+var_40], xmm0
0x18005a89f  xorps   xmm1, xmm1
0x18005a8a2  movdqu  [rbp+var_30], xmm1
0x18005a8a7  lea     r8d, [rdi+5]
0x18005a8ab  lea     rdx, aTheNumberOfPac; "The number of packets that could not be"...
0x18005a8b2  lea     rcx, [rbp+var_40]
0x18005a8b6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a8bb  nop
0x18005a8bc  xorps   xmm0, xmm0
0x18005a8bf  movups  [rbp+var_20], xmm0
0x18005a8c3  xorps   xmm1, xmm1
0x18005a8c6  movdqu  [rbp+var_10], xmm1
0x18005a8cb  lea     r8d, [rdi-0Eh]
0x18005a8cf  lea     rdx, aIncomingmissin; "IncomingMissingDataPacketCount"
0x18005a8d6  lea     rcx, [rbp+var_20]
0x18005a8da  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18005a8df  nop
0x18005a8e0  lea     rcx, [rbx+308h]
0x18005a8e7  lea     r9, [rbp+var_40]
0x18005a8eb  lea     r8, [rbp+var_20]
0x18005a8ef  mov     rdx, rsi
0x18005a8f2  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18005a8f7  nop
0x18005a8f8  lea     rcx, [rbp+var_20]
0x18005a8fc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a901  nop
0x18005a902  lea     rcx, [rbp+var_40]
0x18005a906  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18005a90b  nop
0x18005a90c  mov     rax, rbx
0x18005a90f  lea     r11, [rsp+60h+var_s0]
0x18005a914  mov     rbx, [r11+18h]
0x18005a918  mov     rsi, [r11+20h]
0x18005a91c  mov     rdi, [r11+28h]
0x18005a920  mov     rsp, r11
0x18005a923  pop     rbp
0x18005a924  retn
```
