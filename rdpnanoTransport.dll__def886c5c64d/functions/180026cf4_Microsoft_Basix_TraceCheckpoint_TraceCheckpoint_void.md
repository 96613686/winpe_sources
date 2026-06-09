# Microsoft::Basix::TraceCheckpoint::TraceCheckpoint(void)

- ea: `0x180026cf4`
- end: `0x180027082`
- name: `??0TraceCheckpoint@Basix@Microsoft@@QEAA@XZ`
- size: `910`
- prototype: `__int64 __fastcall(Microsoft::Basix::TraceCheckpoint *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e114`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180025fc0`
- `0x180026ba8`
- `0x18032f050`

## string_xrefs

- `0x180026db0`: `TaskName`
- `0x180026dd3`: `TaskName`
- `0x180026ea7`: `Component`
- `0x180026eca`: `Component`
- `0x180026f1d`: `SubComponent`
- `0x180026f40`: `SubComponent`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
Microsoft::Basix::TraceCheckpoint *__fastcall Microsoft::Basix::TraceCheckpoint::TraceCheckpoint(
        Microsoft::Basix::TraceCheckpoint *this)
{
  __int128 v3; // [rsp+20h] [rbp-40h] BYREF
  __int128 v4; // [rsp+30h] [rbp-30h]
  __int128 v5; // [rsp+40h] [rbp-20h] BYREF
  __int128 v6; // [rsp+50h] [rbp-10h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+8h] BYREF

  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "%3%::%4%: %1% - Properties: %6%", (unsigned int)&retaddr - 65);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Microsoft::Basix::TraceCheckpoint", 33);
  Microsoft::Basix::Instrumentation::RecordDescriptor::RecordDescriptor(this, &v3, 4, &v5);
  std::string::_Tidy_deallocate(&v3);
  std::string::_Tidy_deallocate(&v5);
  *(_QWORD *)this = &Microsoft::Basix::TraceCheckpoint::`vftable';
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "TaskName", 8);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "TaskName", 8);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 344,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "CheckpointType", 14);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "CheckpointType", 14);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 416,
    &unsigned int `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Component", 9);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "Component", 9);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 488,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "SubComponent", 12);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "SubComponent", 12);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 560,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Msg", 3);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "Msg", 3);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 632,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Props", 5);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "Props", 5);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 704,
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
0x180026cf4  mov     rax, rsp
0x180026cf7  mov     [rax+10h], rbx
0x180026cfb  mov     [rax+18h], rsi
0x180026cff  mov     [rax+20h], rdi
0x180026d03  mov     [rax+8], rcx
0x180026d07  push    rbp
0x180026d08  mov     rbp, rsp
0x180026d0b  mov     eax, 60h
0x180026d10  call    _alloca_probe
0x180026d15  sub     rsp, rax
0x180026d18  mov     rbx, rcx
0x180026d1b  xorps   xmm0, xmm0
0x180026d1e  movups  [rbp+var_20], xmm0
0x180026d22  xorps   xmm1, xmm1
0x180026d25  movdqu  [rbp+var_10], xmm1
0x180026d2a  lea     r8d, [rax-41h]
0x180026d2e  lea     rdx, a341Properties6; "%3%::%4%: %1% - Properties: %6%"
0x180026d35  lea     rcx, [rbp+var_20]
0x180026d39  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026d3e  nop
0x180026d3f  xorps   xmm0, xmm0
0x180026d42  movups  [rbp+var_40], xmm0
0x180026d46  xorps   xmm1, xmm1
0x180026d49  movdqu  [rbp+var_30], xmm1
0x180026d4e  mov     r8d, 21h ; '!'
0x180026d54  lea     rdx, aMicrosoftBasix_234; "Microsoft::Basix::TraceCheckpoint"
0x180026d5b  lea     rcx, [rbp+var_40]
0x180026d5f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026d64  nop
0x180026d65  lea     r9, [rbp+var_20]
0x180026d69  mov     r8d, 4
0x180026d6f  lea     rdx, [rbp+var_40]
0x180026d73  mov     rcx, rbx
0x180026d76  call    ??0RecordDescriptor@Instrumentation@Basix@Microsoft@@IEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Level@0123@0@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::RecordDescriptor(std::string const &,Microsoft::Basix::Instrumentation::RecordDescriptor::Level,std::string const &)
0x180026d7b  nop
0x180026d7c  lea     rcx, [rbp+var_40]
0x180026d80  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026d85  nop
0x180026d86  lea     rcx, [rbp+var_20]
0x180026d8a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026d8f  lea     rax, ??_7TraceCheckpoint@Basix@Microsoft@@6B@; const Microsoft::Basix::TraceCheckpoint::`vftable'
0x180026d96  mov     [rbx], rax
0x180026d99  xorps   xmm0, xmm0
0x180026d9c  movups  [rbp+var_40], xmm0
0x180026da0  xorps   xmm1, xmm1
0x180026da3  movdqu  [rbp+var_30], xmm1
0x180026da8  mov     edi, 8
0x180026dad  mov     r8d, edi
0x180026db0  lea     rdx, aTaskname; "TaskName"
0x180026db7  lea     rcx, [rbp+var_40]
0x180026dbb  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026dc0  nop
0x180026dc1  xorps   xmm0, xmm0
0x180026dc4  movups  [rbp+var_20], xmm0
0x180026dc8  xorps   xmm1, xmm1
0x180026dcb  movdqu  [rbp+var_10], xmm1
0x180026dd0  mov     r8d, edi
0x180026dd3  lea     rdx, aTaskname; "TaskName"
0x180026dda  lea     rcx, [rbp+var_20]
0x180026dde  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026de3  nop
0x180026de4  lea     rcx, [rbx+158h]
0x180026deb  lea     r9, [rbp+var_40]
0x180026def  lea     r8, [rbp+var_20]
0x180026df3  lea     rsi, ??_R0?AVEncodedString@Instrumentation@Basix@Microsoft@@@8; Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor'
0x180026dfa  mov     rdx, rsi
0x180026dfd  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180026e02  nop
0x180026e03  lea     rcx, [rbp+var_20]
0x180026e07  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026e0c  nop
0x180026e0d  lea     rcx, [rbp+var_40]
0x180026e11  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026e16  xorps   xmm0, xmm0
0x180026e19  movups  [rbp+var_40], xmm0
0x180026e1d  xorps   xmm1, xmm1
0x180026e20  movdqu  [rbp+var_30], xmm1
0x180026e25  mov     edi, 0Eh
0x180026e2a  mov     r8d, edi
0x180026e2d  lea     rdx, aCheckpointtype; "CheckpointType"
0x180026e34  lea     rcx, [rbp+var_40]
0x180026e38  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026e3d  nop
0x180026e3e  xorps   xmm0, xmm0
0x180026e41  movups  [rbp+var_20], xmm0
0x180026e45  xorps   xmm1, xmm1
0x180026e48  movdqu  [rbp+var_10], xmm1
0x180026e4d  mov     r8d, edi
0x180026e50  lea     rdx, aCheckpointtype; "CheckpointType"
0x180026e57  lea     rcx, [rbp+var_20]
0x180026e5b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026e60  nop
0x180026e61  lea     rcx, [rbx+1A0h]
0x180026e68  lea     r9, [rbp+var_40]
0x180026e6c  lea     r8, [rbp+var_20]
0x180026e70  lea     rdx, ??_R0I@8; uint `RTTI Type Descriptor'
0x180026e77  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180026e7c  nop
0x180026e7d  lea     rcx, [rbp+var_20]
0x180026e81  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026e86  nop
0x180026e87  lea     rcx, [rbp+var_40]
0x180026e8b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026e90  xorps   xmm0, xmm0
0x180026e93  movups  [rbp+var_40], xmm0
0x180026e97  xorps   xmm1, xmm1
0x180026e9a  movdqu  [rbp+var_30], xmm1
0x180026e9f  mov     edi, 9
0x180026ea4  mov     r8d, edi
0x180026ea7  lea     rdx, aComponent; "Component"
0x180026eae  lea     rcx, [rbp+var_40]
0x180026eb2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026eb7  nop
0x180026eb8  xorps   xmm0, xmm0
0x180026ebb  movups  [rbp+var_20], xmm0
0x180026ebf  xorps   xmm1, xmm1
0x180026ec2  movdqu  [rbp+var_10], xmm1
0x180026ec7  mov     r8d, edi
0x180026eca  lea     rdx, aComponent; "Component"
0x180026ed1  lea     rcx, [rbp+var_20]
0x180026ed5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026eda  nop
0x180026edb  lea     rcx, [rbx+1E8h]
0x180026ee2  lea     r9, [rbp+var_40]
0x180026ee6  lea     r8, [rbp+var_20]
0x180026eea  mov     rdx, rsi
0x180026eed  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180026ef2  nop
0x180026ef3  lea     rcx, [rbp+var_20]
0x180026ef7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026efc  nop
0x180026efd  lea     rcx, [rbp+var_40]
0x180026f01  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026f06  xorps   xmm0, xmm0
0x180026f09  movups  [rbp+var_40], xmm0
0x180026f0d  xorps   xmm1, xmm1
0x180026f10  movdqu  [rbp+var_30], xmm1
0x180026f15  mov     edi, 0Ch
0x180026f1a  mov     r8d, edi
0x180026f1d  lea     rdx, aSubcomponent; "SubComponent"
0x180026f24  lea     rcx, [rbp+var_40]
0x180026f28  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026f2d  nop
0x180026f2e  xorps   xmm0, xmm0
0x180026f31  movups  [rbp+var_20], xmm0
0x180026f35  xorps   xmm1, xmm1
0x180026f38  movdqu  [rbp+var_10], xmm1
0x180026f3d  mov     r8d, edi
0x180026f40  lea     rdx, aSubcomponent; "SubComponent"
0x180026f47  lea     rcx, [rbp+var_20]
0x180026f4b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026f50  nop
0x180026f51  lea     rcx, [rbx+230h]
0x180026f58  lea     r9, [rbp+var_40]
0x180026f5c  lea     r8, [rbp+var_20]
0x180026f60  mov     rdx, rsi
0x180026f63  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180026f68  nop
0x180026f69  lea     rcx, [rbp+var_20]
0x180026f6d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026f72  nop
0x180026f73  lea     rcx, [rbp+var_40]
0x180026f77  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026f7c  xorps   xmm0, xmm0
0x180026f7f  movups  [rbp+var_40], xmm0
0x180026f83  xorps   xmm1, xmm1
0x180026f86  movdqu  [rbp+var_30], xmm1
0x180026f8b  mov     edi, 3
0x180026f90  mov     r8d, edi
0x180026f93  lea     rdx, aMsg; "Msg"
0x180026f9a  lea     rcx, [rbp+var_40]
0x180026f9e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026fa3  nop
0x180026fa4  xorps   xmm0, xmm0
0x180026fa7  movups  [rbp+var_20], xmm0
0x180026fab  xorps   xmm1, xmm1
0x180026fae  movdqu  [rbp+var_10], xmm1
0x180026fb3  mov     r8d, edi
0x180026fb6  lea     rdx, aMsg; "Msg"
0x180026fbd  lea     rcx, [rbp+var_20]
0x180026fc1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180026fc6  nop
0x180026fc7  lea     rcx, [rbx+278h]
0x180026fce  lea     r9, [rbp+var_40]
0x180026fd2  lea     r8, [rbp+var_20]
0x180026fd6  mov     rdx, rsi
0x180026fd9  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180026fde  nop
0x180026fdf  lea     rcx, [rbp+var_20]
0x180026fe3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026fe8  nop
0x180026fe9  lea     rcx, [rbp+var_40]
0x180026fed  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180026ff2  xorps   xmm0, xmm0
0x180026ff5  movups  [rbp+var_40], xmm0
0x180026ff9  xorps   xmm1, xmm1
0x180026ffc  movdqu  [rbp+var_30], xmm1
0x180027001  mov     edi, 5
0x180027006  mov     r8d, edi
0x180027009  lea     rdx, aProps; "Props"
0x180027010  lea     rcx, [rbp+var_40]
0x180027014  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180027019  nop
0x18002701a  xorps   xmm0, xmm0
0x18002701d  movups  [rbp+var_20], xmm0
0x180027021  xorps   xmm1, xmm1
0x180027024  movdqu  [rbp+var_10], xmm1
0x180027029  mov     r8d, edi
0x18002702c  lea     rdx, aProps; "Props"
0x180027033  lea     rcx, [rbp+var_20]
0x180027037  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18002703c  nop
0x18002703d  lea     rcx, [rbx+2C0h]
0x180027044  lea     r9, [rbp+var_40]
0x180027048  lea     r8, [rbp+var_20]
0x18002704c  mov     rdx, rsi
0x18002704f  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180027054  nop
0x180027055  lea     rcx, [rbp+var_20]
0x180027059  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18002705e  nop
0x18002705f  lea     rcx, [rbp+var_40]
0x180027063  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180027068  nop
0x180027069  mov     rax, rbx
0x18002706c  lea     r11, [rsp+60h+var_s0]
0x180027071  mov     rbx, [r11+18h]
0x180027075  mov     rsi, [r11+20h]
0x180027079  mov     rdi, [r11+28h]
0x18002707d  mov     rsp, r11
0x180027080  pop     rbp
0x180027081  retn
```
