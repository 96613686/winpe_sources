# Microsoft::Basix::Instrumentation::MultiLinkError::MultiLinkError(void)

- ea: `0x1800652bc`
- end: `0x18006579b`
- name: `??0MultiLinkError@Instrumentation@Basix@Microsoft@@QEAA@XZ`
- size: `1247`
- prototype: `__int64 __fastcall(Microsoft::Basix::Instrumentation::MultiLinkError *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18009a0e8`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180025fc0`
- `0x180026ba8`
- `0x18032f050`

## string_xrefs

- `0x180065374`: `Unique identifier generated for links created in SMILES for a given connection`
- `0x180065398`: `LinkId`
- `0x180065721`: `Additional data as string in JSON format`
- `0x1800652f6`: `LinkId: %1%, ErrorSource: %2%, ErrorCode: %3%, ErrorCodeSymbolic: %4%, ErrorMessage: %5%, ReportedBy: %6%`
- `0x18006531e`: `Microsoft::Basix::Instrumentation::MultiLinkError`
- `0x1800654db`: `Error code symbolic`
- `0x1800654ff`: `ErrorCodeSymbolic`
- `0x1800655c5`: `Name of service component that emitted error`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
Microsoft::Basix::Instrumentation::MultiLinkError *__fastcall Microsoft::Basix::Instrumentation::MultiLinkError::MultiLinkError(
        Microsoft::Basix::Instrumentation::MultiLinkError *this)
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
    "LinkId: %1%, ErrorSource: %2%, ErrorCode: %3%, ErrorCodeSymbolic: %4%, ErrorMessage: %5%, ReportedBy: %6%",
    (unsigned int)&retaddr + 9);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Microsoft::Basix::Instrumentation::MultiLinkError", 49);
  Microsoft::Basix::Instrumentation::RecordDescriptor::RecordDescriptor(this, &v3, 3, &v5);
  std::string::_Tidy_deallocate(&v3);
  std::string::_Tidy_deallocate(&v5);
  *(_QWORD *)this = &Microsoft::Basix::Instrumentation::MultiLinkError::`vftable';
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
  std::string::_Construct<1,char const *>(&v3, "Source of error. E.g. Client, Gateway, Stack, etc", 49);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ErrorSource", 11);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 416,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Error code", 10);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ErrorCode", 9);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 488,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Error code symbolic", 19);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ErrorCodeSymbolic", 17);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 560,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Error Message", 13);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ErrorMessage", 12);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 632,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Name of service component that emitted error", 44);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ReportedBy", 10);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 704,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Error operation", 15);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ErrorOperation", 14);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 776,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Error classification internal vs external ", 42);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ErrorInternal", 13);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 848,
    &bool `RTTI Type Descriptor',
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
    (char *)this + 920,
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
0x1800652bc  mov     rax, rsp
0x1800652bf  mov     [rax+10h], rbx
0x1800652c3  mov     [rax+18h], rdi
0x1800652c7  mov     [rax+20h], r14
0x1800652cb  mov     [rax+8], rcx
0x1800652cf  push    rbp
0x1800652d0  mov     rbp, rsp
0x1800652d3  mov     eax, 60h
0x1800652d8  call    _alloca_probe
0x1800652dd  sub     rsp, rax
0x1800652e0  mov     rbx, rcx
0x1800652e3  xorps   xmm0, xmm0
0x1800652e6  movups  [rbp+var_20], xmm0
0x1800652ea  xorps   xmm1, xmm1
0x1800652ed  movdqu  [rbp+var_10], xmm1
0x1800652f2  lea     r8d, [rax+9]
0x1800652f6  lea     rdx, aLinkid1Errorso; "LinkId: %1%, ErrorSource: %2%, ErrorCod"...
0x1800652fd  lea     rcx, [rbp+var_20]
0x180065301  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180065306  nop
0x180065307  xorps   xmm0, xmm0
0x18006530a  movups  [rbp+var_40], xmm0
0x18006530e  xorps   xmm1, xmm1
0x180065311  movdqu  [rbp+var_30], xmm1
0x180065316  mov     edi, 31h ; '1'
0x18006531b  mov     r8d, edi
0x18006531e  lea     rdx, aMicrosoftBasix_139; "Microsoft::Basix::Instrumentation::Mult"...
0x180065325  lea     rcx, [rbp+var_40]
0x180065329  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006532e  nop
0x18006532f  lea     r9, [rbp+var_20]
0x180065333  lea     r8d, [rdi-2Eh]
0x180065337  lea     rdx, [rbp+var_40]
0x18006533b  mov     rcx, rbx
0x18006533e  call    ??0RecordDescriptor@Instrumentation@Basix@Microsoft@@IEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Level@0123@0@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::RecordDescriptor(std::string const &,Microsoft::Basix::Instrumentation::RecordDescriptor::Level,std::string const &)
0x180065343  nop
0x180065344  lea     rcx, [rbp+var_40]
0x180065348  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006534d  nop
0x18006534e  lea     rcx, [rbp+var_20]
0x180065352  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180065357  lea     rax, ??_7MultiLinkError@Instrumentation@Basix@Microsoft@@6B@; const Microsoft::Basix::Instrumentation::MultiLinkError::`vftable'
0x18006535e  mov     [rbx], rax
0x180065361  xorps   xmm0, xmm0
0x180065364  movups  [rbp+var_40], xmm0
0x180065368  xorps   xmm1, xmm1
0x18006536b  movdqu  [rbp+var_30], xmm1
0x180065370  lea     r8d, [rdi+1Dh]
0x180065374  lea     rdx, aUniqueIdentifi_0; "Unique identifier generated for links c"...
0x18006537b  lea     rcx, [rbp+var_40]
0x18006537f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180065384  nop
0x180065385  xorps   xmm0, xmm0
0x180065388  movups  [rbp+var_20], xmm0
0x18006538c  xorps   xmm1, xmm1
0x18006538f  movdqu  [rbp+var_10], xmm1
0x180065394  lea     r8d, [rdi-2Bh]
0x180065398  lea     rdx, aLinkid; "LinkId"
0x18006539f  lea     rcx, [rbp+var_20]
0x1800653a3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800653a8  nop
0x1800653a9  lea     rcx, [rbx+158h]
0x1800653b0  lea     r9, [rbp+var_40]
0x1800653b4  lea     r8, [rbp+var_20]
0x1800653b8  lea     rdx, ??_R0I@8; uint `RTTI Type Descriptor'
0x1800653bf  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x1800653c4  nop
0x1800653c5  lea     rcx, [rbp+var_20]
0x1800653c9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800653ce  nop
0x1800653cf  lea     rcx, [rbp+var_40]
0x1800653d3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800653d8  xorps   xmm0, xmm0
0x1800653db  movups  [rbp+var_40], xmm0
0x1800653df  xorps   xmm1, xmm1
0x1800653e2  movdqu  [rbp+var_30], xmm1
0x1800653e7  mov     r8d, edi
0x1800653ea  lea     rdx, aSourceOfErrorE; "Source of error. E.g. Client, Gateway, "...
0x1800653f1  lea     rcx, [rbp+var_40]
0x1800653f5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800653fa  nop
0x1800653fb  xorps   xmm0, xmm0
0x1800653fe  movups  [rbp+var_20], xmm0
0x180065402  xorps   xmm1, xmm1
0x180065405  movdqu  [rbp+var_10], xmm1
0x18006540a  lea     r8d, [rdi-26h]
0x18006540e  lea     rdx, aErrorsource; "ErrorSource"
0x180065415  lea     rcx, [rbp+var_20]
0x180065419  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006541e  nop
0x18006541f  lea     rcx, [rbx+1A0h]
0x180065426  lea     r9, [rbp+var_40]
0x18006542a  lea     r8, [rbp+var_20]
0x18006542e  lea     r14, ??_R0?AVEncodedString@Instrumentation@Basix@Microsoft@@@8; Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor'
0x180065435  mov     rdx, r14
0x180065438  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18006543d  nop
0x18006543e  lea     rcx, [rbp+var_20]
0x180065442  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180065447  nop
0x180065448  lea     rcx, [rbp+var_40]
0x18006544c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180065451  xorps   xmm0, xmm0
0x180065454  movups  [rbp+var_40], xmm0
0x180065458  xorps   xmm1, xmm1
0x18006545b  movdqu  [rbp+var_30], xmm1
0x180065460  lea     r8d, [rdi-27h]
0x180065464  lea     rdx, aErrorCode; "Error code"
0x18006546b  lea     rcx, [rbp+var_40]
0x18006546f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180065474  nop
0x180065475  xorps   xmm0, xmm0
0x180065478  movups  [rbp+var_20], xmm0
0x18006547c  xorps   xmm1, xmm1
0x18006547f  movdqu  [rbp+var_10], xmm1
0x180065484  lea     r8d, [rdi-28h]
0x180065488  lea     rdx, aErrorcode; "ErrorCode"
0x18006548f  lea     rcx, [rbp+var_20]
0x180065493  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180065498  nop
0x180065499  lea     rcx, [rbx+1E8h]
0x1800654a0  lea     r9, [rbp+var_40]
0x1800654a4  lea     r8, [rbp+var_20]
0x1800654a8  lea     rdx, ??_R0I@8; uint `RTTI Type Descriptor'
0x1800654af  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x1800654b4  nop
0x1800654b5  lea     rcx, [rbp+var_20]
0x1800654b9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800654be  nop
0x1800654bf  lea     rcx, [rbp+var_40]
0x1800654c3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800654c8  xorps   xmm0, xmm0
0x1800654cb  movups  [rbp+var_40], xmm0
0x1800654cf  xorps   xmm1, xmm1
0x1800654d2  movdqu  [rbp+var_30], xmm1
0x1800654d7  lea     r8d, [rdi-1Eh]
0x1800654db  lea     rdx, aErrorCodeSymbo; "Error code symbolic"
0x1800654e2  lea     rcx, [rbp+var_40]
0x1800654e6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800654eb  nop
0x1800654ec  xorps   xmm0, xmm0
0x1800654ef  movups  [rbp+var_20], xmm0
0x1800654f3  xorps   xmm1, xmm1
0x1800654f6  movdqu  [rbp+var_10], xmm1
0x1800654fb  lea     r8d, [rdi-20h]
0x1800654ff  lea     rdx, aErrorcodesymbo; "ErrorCodeSymbolic"
0x180065506  lea     rcx, [rbp+var_20]
0x18006550a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006550f  nop
0x180065510  lea     rcx, [rbx+230h]
0x180065517  lea     r9, [rbp+var_40]
0x18006551b  lea     r8, [rbp+var_20]
0x18006551f  mov     rdx, r14
0x180065522  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180065527  nop
0x180065528  lea     rcx, [rbp+var_20]
0x18006552c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180065531  nop
0x180065532  lea     rcx, [rbp+var_40]
0x180065536  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006553b  xorps   xmm0, xmm0
0x18006553e  movups  [rbp+var_40], xmm0
0x180065542  xorps   xmm1, xmm1
0x180065545  movdqu  [rbp+var_30], xmm1
0x18006554a  mov     edi, 0Dh
0x18006554f  mov     r8d, edi
0x180065552  lea     rdx, aErrorMessage; "Error Message"
0x180065559  lea     rcx, [rbp+var_40]
0x18006555d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180065562  nop
0x180065563  xorps   xmm0, xmm0
0x180065566  movups  [rbp+var_20], xmm0
0x18006556a  xorps   xmm1, xmm1
0x18006556d  movdqu  [rbp+var_10], xmm1
0x180065572  lea     r8d, [rdi-1]
0x180065576  lea     rdx, aErrormessage_0; "ErrorMessage"
0x18006557d  lea     rcx, [rbp+var_20]
0x180065581  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180065586  nop
0x180065587  lea     rcx, [rbx+278h]
0x18006558e  lea     r9, [rbp+var_40]
0x180065592  lea     r8, [rbp+var_20]
0x180065596  mov     rdx, r14
0x180065599  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x18006559e  nop
0x18006559f  lea     rcx, [rbp+var_20]
0x1800655a3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800655a8  nop
0x1800655a9  lea     rcx, [rbp+var_40]
0x1800655ad  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800655b2  xorps   xmm0, xmm0
0x1800655b5  movups  [rbp+var_40], xmm0
0x1800655b9  xorps   xmm1, xmm1
0x1800655bc  movdqu  [rbp+var_30], xmm1
0x1800655c1  lea     r8d, [rdi+1Fh]
0x1800655c5  lea     rdx, aNameOfServiceC; "Name of service component that emitted "...
0x1800655cc  lea     rcx, [rbp+var_40]
0x1800655d0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800655d5  nop
0x1800655d6  xorps   xmm0, xmm0
0x1800655d9  movups  [rbp+var_20], xmm0
0x1800655dd  xorps   xmm1, xmm1
0x1800655e0  movdqu  [rbp+var_10], xmm1
0x1800655e5  lea     r8d, [rdi-3]
0x1800655e9  lea     rdx, aReportedby; "ReportedBy"
0x1800655f0  lea     rcx, [rbp+var_20]
0x1800655f4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800655f9  nop
0x1800655fa  lea     rcx, [rbx+2C0h]
0x180065601  lea     r9, [rbp+var_40]
0x180065605  lea     r8, [rbp+var_20]
0x180065609  mov     rdx, r14
0x18006560c  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180065611  nop
0x180065612  lea     rcx, [rbp+var_20]
0x180065616  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006561b  nop
0x18006561c  lea     rcx, [rbp+var_40]
0x180065620  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180065625  xorps   xmm0, xmm0
0x180065628  movups  [rbp+var_40], xmm0
0x18006562c  xorps   xmm1, xmm1
0x18006562f  movdqu  [rbp+var_30], xmm1
0x180065634  lea     r8d, [rdi+2]
0x180065638  lea     rdx, aErrorOperation; "Error operation"
0x18006563f  lea     rcx, [rbp+var_40]
0x180065643  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180065648  nop
0x180065649  xorps   xmm0, xmm0
0x18006564c  movups  [rbp+var_20], xmm0
0x180065650  xorps   xmm1, xmm1
0x180065653  movdqu  [rbp+var_10], xmm1
0x180065658  lea     r8d, [rdi+1]
0x18006565c  lea     rdx, aErroroperation; "ErrorOperation"
0x180065663  lea     rcx, [rbp+var_20]
0x180065667  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006566c  nop
0x18006566d  lea     rcx, [rbx+308h]
0x180065674  lea     r9, [rbp+var_40]
0x180065678  lea     r8, [rbp+var_20]
0x18006567c  mov     rdx, r14
0x18006567f  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180065684  nop
0x180065685  lea     rcx, [rbp+var_20]
0x180065689  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006568e  nop
0x18006568f  lea     rcx, [rbp+var_40]
0x180065693  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180065698  xorps   xmm0, xmm0
0x18006569b  movups  [rbp+var_40], xmm0
0x18006569f  xorps   xmm1, xmm1
0x1800656a2  movdqu  [rbp+var_30], xmm1
0x1800656a7  lea     r8d, [rdi+1Dh]
0x1800656ab  lea     rdx, aErrorClassific; "Error classification internal vs extern"...
0x1800656b2  lea     rcx, [rbp+var_40]
0x1800656b6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800656bb  nop
0x1800656bc  xorps   xmm0, xmm0
0x1800656bf  movups  [rbp+var_20], xmm0
0x1800656c3  xorps   xmm1, xmm1
0x1800656c6  movdqu  [rbp+var_10], xmm1
0x1800656cb  mov     r8d, edi
0x1800656ce  lea     rdx, aErrorinternal; "ErrorInternal"
0x1800656d5  lea     rcx, [rbp+var_20]
0x1800656d9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800656de  nop
0x1800656df  lea     rcx, [rbx+350h]
0x1800656e6  lea     r9, [rbp+var_40]
0x1800656ea  lea     r8, [rbp+var_20]
0x1800656ee  lea     rdx, ??_R0_N@8; bool `RTTI Type Descriptor'
0x1800656f5  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x1800656fa  nop
0x1800656fb  lea     rcx, [rbp+var_20]
0x1800656ff  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180065704  nop
0x180065705  lea     rcx, [rbp+var_40]
0x180065709  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18006570e  xorps   xmm0, xmm0
0x180065711  movups  [rbp+var_40], xmm0
0x180065715  xorps   xmm1, xmm1
0x180065718  movdqu  [rbp+var_30], xmm1
0x18006571d  lea     r8d, [rdi+1Bh]
0x180065721  lea     rdx, aAdditionalData; "Additional data as string in JSON forma"...
0x180065728  lea     rcx, [rbp+var_40]
0x18006572c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180065731  nop
0x180065732  xorps   xmm0, xmm0
0x180065735  movups  [rbp+var_20], xmm0
0x180065739  xorps   xmm1, xmm1
0x18006573c  movdqu  [rbp+var_10], xmm1
0x180065741  lea     r8d, [rdi-8]
0x180065745  lea     rdx, aProps; "Props"
0x18006574c  lea     rcx, [rbp+var_20]
0x180065750  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180065755  nop
0x180065756  lea     rcx, [rbx+398h]
0x18006575d  lea     r9, [rbp+var_40]
0x180065761  lea     r8, [rbp+var_20]
0x180065765  mov     rdx, r14
0x180065768  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
  ... truncated ...
```
