# Microsoft::Basix::Instrumentation::MultiLinkAdd::MultiLinkAdd(void)

- ea: `0x18006494c`
- end: `0x1800652ba`
- name: `??0MultiLinkAdd@Instrumentation@Basix@Microsoft@@QEAA@XZ`
- size: `2414`
- prototype: `__int64 __fastcall(Microsoft::Basix::Instrumentation::MultiLinkAdd *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009a048`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180025fc0`
- `0x180026ba8`
- `0x18032f050`

## string_xrefs

- `0x18006498b`: `LinkId: %1%, TransportType: %2%, ClientTransportType: %3%, ServerTransportType: %4%,     IsUPnP: %5%, ServerTURNIP: %6%, ServerTURNRegion: %7%, ClientTURNIP: %8%, ClientTURNRegion: %9%, GatewayConnectionID: %10%,     GatewayInstanceID: %11%, GatewayCluster: %12%, GatewayRegion: %13%, SMILESVersion: %14%,     ClientTransportIP: %15%, ServerTransportIP: %16%, ClientNatIP: %17%, ServerNatIP: %18%, Props: %19%`
- `0x1800649b1`: `Microsoft::Basix::Instrumentation::MultiLinkAdd`
- `0x180064a0b`: `Unique identifier generated for links created in SMILES for a given connection`
- `0x180064a33`: `LinkId`
- `0x180064a86`: `TransportType - Shortpath public, shortpath private, websocket or relay`
- `0x180064b05`: `Transport used from client side - Direct, TURN, STUN, Rendezvous`
- `0x180064b7a`: `Transport used from server side - Direct, TURN, STUN, Rendezvous`
- `0x180064e32`: `Rendezvous: Connection ID guid for this Rendezvous link`
- `0x180064ea3`: `Rendezvous: Unique (within activity id) instance ID for Rendezvous link gateway`
- `0x180064f19`: `Rendezvous: Cluster for the Rendezvous link gateway`
- `0x180064f90`: `Rendezvous: Region for the Rendezvous link gateway`
- `0x180065075`: `STUN/TURN IP along with port number used at client side `
- `0x1800650e6`: `STUN/TURN IP along with port number used at server side `
- `0x180065157`: `NAT IP along with port number used at client side `
- `0x1800651cb`: `NAT IP along with port number used at server side `
- `0x18006523d`: `Additional data as string in JSON format`

## pseudocode

```c
// Hidden C++ exception states: #wind=97
Microsoft::Basix::Instrumentation::MultiLinkAdd *__fastcall Microsoft::Basix::Instrumentation::MultiLinkAdd::MultiLinkAdd(
        Microsoft::Basix::Instrumentation::MultiLinkAdd *this)
{
  __int128 v3; // [rsp+20h] [rbp-40h] BYREF
  __int128 v4; // [rsp+30h] [rbp-30h]
  __int128 v5; // [rsp+40h] [rbp-20h] BYREF
  __int128 v6; // [rsp+50h] [rbp-10h]

  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(
    &v5,
    "LinkId: %1%, TransportType: %2%, ClientTransportType: %3%, ServerTransportType: %4%,     IsUPnP: %5%, ServerTURNIP: "
    "%6%, ServerTURNRegion: %7%, ClientTURNIP: %8%, ClientTURNRegion: %9%, GatewayConnectionID: %10%,     GatewayInstance"
    "ID: %11%, GatewayCluster: %12%, GatewayRegion: %13%, SMILESVersion: %14%,     ClientTransportIP: %15%, ServerTranspo"
    "rtIP: %16%, ClientNatIP: %17%, ServerNatIP: %18%, Props: %19%",
    409);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Microsoft::Basix::Instrumentation::MultiLinkAdd", 47);
  Microsoft::Basix::Instrumentation::RecordDescriptor::RecordDescriptor(this, &v3, 4, &v5);
  std::string::_Tidy_deallocate(&v3);
  std::string::_Tidy_deallocate(&v5);
  *(_QWORD *)this = &Microsoft::Basix::Instrumentation::MultiLinkAdd::`vftable';
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
    "TransportType - Shortpath public, shortpath private, websocket or relay",
    71);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "TransportType", 13);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 416,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Transport used from client side - Direct, TURN, STUN, Rendezvous", 64);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ClientTransportType", 19);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 488,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Transport used from server side - Direct, TURN, STUN, Rendezvous", 64);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ServerTransportType", 19);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 560,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Set to true if client is using UPnP", 35);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "IsUPnP", 6);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 632,
    &bool `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(
    &v3,
    "IP address of TURN server used by VM/session host. Will be empty if local TURN server is not used",
    97);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ServerTURNIP", 12);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 704,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(
    &v3,
    "TURN server geography. Will be empty if local TURN server is not used",
    69);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ServerTURNRegion", 16);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 776,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(
    &v3,
    "IP address of TURN server used by client. Will be empty if client TURN server is not used",
    89);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ClientTURNIP", 12);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 848,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(
    &v3,
    "Client TURN server geography. Will be empty if client TURN server is not used. ",
    79);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ClientTURNRegion", 16);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 920,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Rendezvous: Connection ID guid for this Rendezvous link", 55);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "GatewayConnectionID", 19);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 992,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(
    &v3,
    "Rendezvous: Unique (within activity id) instance ID for Rendezvous link gateway",
    79);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "GatewayInstanceID", 17);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 1064,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Rendezvous: Cluster for the Rendezvous link gateway", 51);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "GatewayCluster", 14);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 1136,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "Rendezvous: Region for the Rendezvous link gateway", 50);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "GatewayRegion", 13);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 1208,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "SMILES version", 14);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "SMILESVersion", 13);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 1280,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "STUN/TURN IP along with port number used at client side ", 56);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ClientTransportIP", 17);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 1352,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "STUN/TURN IP along with port number used at server side ", 56);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ServerTransportIP", 17);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 1424,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "NAT IP along with port number used at client side ", 50);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ClientNatIP", 11);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 1496,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
    &v5,
    &v3);
  std::string::_Tidy_deallocate(&v5);
  std::string::_Tidy_deallocate(&v3);
  v3 = 0;
  v4 = 0;
  std::string::_Construct<1,char const *>(&v3, "NAT IP along with port number used at server side ", 50);
  v5 = 0;
  v6 = 0;
  std::string::_Construct<1,char const *>(&v5, "ServerNatIP", 11);
  Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(
    (char *)this + 1568,
    &Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor',
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
    (char *)this + 1640,
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
0x18006494c  mov     [rsp-28h+arg_8], rbx
0x180064951  mov     [rsp-28h+arg_10], rsi
0x180064956  mov     [rsp-28h+arg_0], rcx
0x18006495b  push    rbp
0x18006495c  push    rdi
0x18006495d  push    r12
0x18006495f  push    r14
0x180064961  push    r15
0x180064963  mov     rbp, rsp
0x180064966  mov     eax, 60h
0x18006496b  call    _alloca_probe
0x180064970  sub     rsp, rax
0x180064973  mov     rbx, rcx
0x180064976  xorps   xmm0, xmm0
0x180064979  movups  [rbp+var_20], xmm0
0x18006497d  xorps   xmm1, xmm1
0x180064980  movdqu  [rbp+var_10], xmm1
0x180064985  mov     r8d, 199h
0x18006498b  lea     rdx, aLinkid1Transpo; "LinkId: %1%, TransportType: %2%, Client"...
0x180064992  lea     rcx, [rbp+var_20]
0x180064996  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18006499b  nop
0x18006499c  xorps   xmm0, xmm0
0x18006499f  movups  [rbp+var_40], xmm0
0x1800649a3  xorps   xmm1, xmm1
0x1800649a6  movdqu  [rbp+var_30], xmm1
0x1800649ab  mov     r8d, 2Fh ; '/'
0x1800649b1  lea     rdx, aMicrosoftBasix_0; "Microsoft::Basix::Instrumentation::Mult"...
0x1800649b8  lea     rcx, [rbp+var_40]
0x1800649bc  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800649c1  nop
0x1800649c2  lea     r9, [rbp+var_20]
0x1800649c6  mov     r8d, 4
0x1800649cc  lea     rdx, [rbp+var_40]
0x1800649d0  mov     rcx, rbx
0x1800649d3  call    ??0RecordDescriptor@Instrumentation@Basix@Microsoft@@IEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4Level@0123@0@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::RecordDescriptor(std::string const &,Microsoft::Basix::Instrumentation::RecordDescriptor::Level,std::string const &)
0x1800649d8  nop
0x1800649d9  lea     rcx, [rbp+var_40]
0x1800649dd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800649e2  nop
0x1800649e3  lea     rcx, [rbp+var_20]
0x1800649e7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800649ec  lea     rax, ??_7MultiLinkAdd@Instrumentation@Basix@Microsoft@@6B@; const Microsoft::Basix::Instrumentation::MultiLinkAdd::`vftable'
0x1800649f3  mov     [rbx], rax
0x1800649f6  xorps   xmm0, xmm0
0x1800649f9  movups  [rbp+var_40], xmm0
0x1800649fd  xorps   xmm1, xmm1
0x180064a00  movdqu  [rbp+var_30], xmm1
0x180064a05  mov     r8d, 4Eh ; 'N'
0x180064a0b  lea     rdx, aUniqueIdentifi_0; "Unique identifier generated for links c"...
0x180064a12  lea     rcx, [rbp+var_40]
0x180064a16  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064a1b  nop
0x180064a1c  xorps   xmm0, xmm0
0x180064a1f  movups  [rbp+var_20], xmm0
0x180064a23  xorps   xmm1, xmm1
0x180064a26  movdqu  [rbp+var_10], xmm1
0x180064a2b  mov     esi, 6
0x180064a30  mov     r8d, esi
0x180064a33  lea     rdx, aLinkid; "LinkId"
0x180064a3a  lea     rcx, [rbp+var_20]
0x180064a3e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064a43  nop
0x180064a44  lea     rcx, [rbx+158h]
0x180064a4b  lea     r9, [rbp+var_40]
0x180064a4f  lea     r8, [rbp+var_20]
0x180064a53  lea     rdx, ??_R0I@8; uint `RTTI Type Descriptor'
0x180064a5a  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180064a5f  nop
0x180064a60  lea     rcx, [rbp+var_20]
0x180064a64  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064a69  nop
0x180064a6a  lea     rcx, [rbp+var_40]
0x180064a6e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064a73  xorps   xmm0, xmm0
0x180064a76  movups  [rbp+var_40], xmm0
0x180064a7a  xorps   xmm1, xmm1
0x180064a7d  movdqu  [rbp+var_30], xmm1
0x180064a82  lea     r8d, [rsi+41h]
0x180064a86  lea     rdx, aTransporttypeS; "TransportType - Shortpath public, short"...
0x180064a8d  lea     rcx, [rbp+var_40]
0x180064a91  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064a96  nop
0x180064a97  xorps   xmm0, xmm0
0x180064a9a  movups  [rbp+var_20], xmm0
0x180064a9e  xorps   xmm1, xmm1
0x180064aa1  movdqu  [rbp+var_10], xmm1
0x180064aa6  lea     r15d, [rsi+7]
0x180064aaa  mov     r8d, r15d
0x180064aad  lea     rdx, aTransporttype; "TransportType"
0x180064ab4  lea     rcx, [rbp+var_20]
0x180064ab8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064abd  nop
0x180064abe  lea     rcx, [rbx+1A0h]
0x180064ac5  lea     r9, [rbp+var_40]
0x180064ac9  lea     r8, [rbp+var_20]
0x180064acd  lea     r12, ??_R0?AVEncodedString@Instrumentation@Basix@Microsoft@@@8; Microsoft::Basix::Instrumentation::EncodedString `RTTI Type Descriptor'
0x180064ad4  mov     rdx, r12
0x180064ad7  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180064adc  nop
0x180064add  lea     rcx, [rbp+var_20]
0x180064ae1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064ae6  nop
0x180064ae7  lea     rcx, [rbp+var_40]
0x180064aeb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064af0  xorps   xmm0, xmm0
0x180064af3  movups  [rbp+var_40], xmm0
0x180064af7  xorps   xmm1, xmm1
0x180064afa  movdqu  [rbp+var_30], xmm1
0x180064aff  lea     edi, [rsi+3Ah]
0x180064b02  mov     r8d, edi
0x180064b05  lea     rdx, aTransportUsedF; "Transport used from client side - Direc"...
0x180064b0c  lea     rcx, [rbp+var_40]
0x180064b10  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064b15  nop
0x180064b16  xorps   xmm0, xmm0
0x180064b19  movups  [rbp+var_20], xmm0
0x180064b1d  xorps   xmm1, xmm1
0x180064b20  movdqu  [rbp+var_10], xmm1
0x180064b25  lea     r14d, [rsi+0Dh]
0x180064b29  mov     r8d, r14d
0x180064b2c  lea     rdx, aClienttranspor; "ClientTransportType"
0x180064b33  lea     rcx, [rbp+var_20]
0x180064b37  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064b3c  nop
0x180064b3d  lea     rcx, [rbx+1E8h]
0x180064b44  lea     r9, [rbp+var_40]
0x180064b48  lea     r8, [rbp+var_20]
0x180064b4c  mov     rdx, r12
0x180064b4f  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180064b54  nop
0x180064b55  lea     rcx, [rbp+var_20]
0x180064b59  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064b5e  nop
0x180064b5f  lea     rcx, [rbp+var_40]
0x180064b63  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064b68  xorps   xmm0, xmm0
0x180064b6b  movups  [rbp+var_40], xmm0
0x180064b6f  xorps   xmm1, xmm1
0x180064b72  movdqu  [rbp+var_30], xmm1
0x180064b77  mov     r8d, edi
0x180064b7a  lea     rdx, aTransportUsedF_0; "Transport used from server side - Direc"...
0x180064b81  lea     rcx, [rbp+var_40]
0x180064b85  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064b8a  nop
0x180064b8b  xorps   xmm0, xmm0
0x180064b8e  movups  [rbp+var_20], xmm0
0x180064b92  xorps   xmm1, xmm1
0x180064b95  movdqu  [rbp+var_10], xmm1
0x180064b9a  mov     r8d, r14d
0x180064b9d  lea     rdx, aServertranspor; "ServerTransportType"
0x180064ba4  lea     rcx, [rbp+var_20]
0x180064ba8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064bad  nop
0x180064bae  lea     rcx, [rbx+230h]
0x180064bb5  lea     r9, [rbp+var_40]
0x180064bb9  lea     r8, [rbp+var_20]
0x180064bbd  mov     rdx, r12
0x180064bc0  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180064bc5  nop
0x180064bc6  lea     rcx, [rbp+var_20]
0x180064bca  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064bcf  nop
0x180064bd0  lea     rcx, [rbp+var_40]
0x180064bd4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064bd9  xorps   xmm0, xmm0
0x180064bdc  movups  [rbp+var_40], xmm0
0x180064be0  xorps   xmm1, xmm1
0x180064be3  movdqu  [rbp+var_30], xmm1
0x180064be8  lea     r8d, [rsi+1Dh]
0x180064bec  lea     rdx, aSetToTrueIfCli; "Set to true if client is using UPnP"
0x180064bf3  lea     rcx, [rbp+var_40]
0x180064bf7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064bfc  nop
0x180064bfd  xorps   xmm0, xmm0
0x180064c00  movups  [rbp+var_20], xmm0
0x180064c04  xorps   xmm1, xmm1
0x180064c07  movdqu  [rbp+var_10], xmm1
0x180064c0c  mov     r8d, esi
0x180064c0f  lea     rdx, aIsupnp; "IsUPnP"
0x180064c16  lea     rcx, [rbp+var_20]
0x180064c1a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064c1f  nop
0x180064c20  lea     rcx, [rbx+278h]
0x180064c27  lea     r9, [rbp+var_40]
0x180064c2b  lea     r8, [rbp+var_20]
0x180064c2f  lea     rdx, ??_R0_N@8; bool `RTTI Type Descriptor'
0x180064c36  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180064c3b  nop
0x180064c3c  lea     rcx, [rbp+var_20]
0x180064c40  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064c45  nop
0x180064c46  lea     rcx, [rbp+var_40]
0x180064c4a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064c4f  xorps   xmm0, xmm0
0x180064c52  movups  [rbp+var_40], xmm0
0x180064c56  xorps   xmm1, xmm1
0x180064c59  movdqu  [rbp+var_30], xmm1
0x180064c5e  lea     r8d, [rsi+5Bh]
0x180064c62  lea     rdx, aIpAddressOfTur_0; "IP address of TURN server used by VM/se"...
0x180064c69  lea     rcx, [rbp+var_40]
0x180064c6d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064c72  nop
0x180064c73  xorps   xmm0, xmm0
0x180064c76  movups  [rbp+var_20], xmm0
0x180064c7a  xorps   xmm1, xmm1
0x180064c7d  movdqu  [rbp+var_10], xmm1
0x180064c82  lea     edi, [rsi+6]
0x180064c85  mov     r8d, edi
0x180064c88  lea     rdx, aServerturnip; "ServerTURNIP"
0x180064c8f  lea     rcx, [rbp+var_20]
0x180064c93  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064c98  nop
0x180064c99  lea     rcx, [rbx+2C0h]
0x180064ca0  lea     r9, [rbp+var_40]
0x180064ca4  lea     r8, [rbp+var_20]
0x180064ca8  mov     rdx, r12
0x180064cab  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180064cb0  nop
0x180064cb1  lea     rcx, [rbp+var_20]
0x180064cb5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064cba  nop
0x180064cbb  lea     rcx, [rbp+var_40]
0x180064cbf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064cc4  xorps   xmm0, xmm0
0x180064cc7  movups  [rbp+var_40], xmm0
0x180064ccb  xorps   xmm1, xmm1
0x180064cce  movdqu  [rbp+var_30], xmm1
0x180064cd3  lea     r8d, [rsi+3Fh]
0x180064cd7  lea     rdx, aTurnServerGeog; "TURN server geography. Will be empty if"...
0x180064cde  lea     rcx, [rbp+var_40]
0x180064ce2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064ce7  nop
0x180064ce8  xorps   xmm0, xmm0
0x180064ceb  movups  [rbp+var_20], xmm0
0x180064cef  xorps   xmm1, xmm1
0x180064cf2  movdqu  [rbp+var_10], xmm1
0x180064cf7  lea     esi, [rdi+4]
0x180064cfa  mov     r8d, esi
0x180064cfd  lea     rdx, aServerturnregi; "ServerTURNRegion"
0x180064d04  lea     rcx, [rbp+var_20]
0x180064d08  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064d0d  nop
0x180064d0e  lea     rcx, [rbx+308h]
0x180064d15  lea     r9, [rbp+var_40]
0x180064d19  lea     r8, [rbp+var_20]
0x180064d1d  mov     rdx, r12
0x180064d20  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180064d25  nop
0x180064d26  lea     rcx, [rbp+var_20]
0x180064d2a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064d2f  nop
0x180064d30  lea     rcx, [rbp+var_40]
0x180064d34  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064d39  xorps   xmm0, xmm0
0x180064d3c  movups  [rbp+var_40], xmm0
0x180064d40  xorps   xmm1, xmm1
0x180064d43  movdqu  [rbp+var_30], xmm1
0x180064d48  lea     r8d, [r15+4Ch]
0x180064d4c  lea     rdx, aIpAddressOfTur; "IP address of TURN server used by clien"...
0x180064d53  lea     rcx, [rbp+var_40]
0x180064d57  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064d5c  nop
0x180064d5d  xorps   xmm0, xmm0
0x180064d60  movups  [rbp+var_20], xmm0
0x180064d64  xorps   xmm1, xmm1
0x180064d67  movdqu  [rbp+var_10], xmm1
0x180064d6c  mov     r8d, edi
0x180064d6f  lea     rdx, aClientturnip; "ClientTURNIP"
0x180064d76  lea     rcx, [rbp+var_20]
0x180064d7a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064d7f  nop
0x180064d80  lea     rcx, [rbx+350h]
0x180064d87  lea     r9, [rbp+var_40]
0x180064d8b  lea     r8, [rbp+var_20]
0x180064d8f  mov     rdx, r12
0x180064d92  call    ??0Field@RecordDescriptor@Instrumentation@Basix@Microsoft@@QEAA@AEBVtype_info@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1@Z; Microsoft::Basix::Instrumentation::RecordDescriptor::Field::Field(type_info const &,std::string const &,std::string const &)
0x180064d97  nop
0x180064d98  lea     rcx, [rbp+var_20]
0x180064d9c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064da1  nop
0x180064da2  lea     rcx, [rbp+var_40]
0x180064da6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180064dab  xorps   xmm0, xmm0
0x180064dae  movups  [rbp+var_40], xmm0
0x180064db2  xorps   xmm1, xmm1
0x180064db5  movdqu  [rbp+var_30], xmm1
0x180064dba  lea     edi, [rsi+3Fh]
0x180064dbd  mov     r8d, edi
0x180064dc0  lea     rdx, aClientTurnServ; "Client TURN server geography. Will be e"...
0x180064dc7  lea     rcx, [rbp+var_40]
0x180064dcb  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180064dd0  nop
0x180064dd1  xorps   xmm0, xmm0
0x180064dd4  movups  [rbp+var_20], xmm0
0x180064dd8  xorps   xmm1, xmm1
0x180064ddb  movdqu  [rbp+var_10], xmm1
0x180064de0  mov     r8d, esi
0x180064de3  lea     rdx, aClientturnregi; "ClientTURNRegion"
0x180064dea  lea     rcx, [rbp+var_20]
  ... truncated ...
```
