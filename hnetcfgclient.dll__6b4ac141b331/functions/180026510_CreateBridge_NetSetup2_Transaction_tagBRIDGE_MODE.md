# CreateBridge(NetSetup2::Transaction &,tagBRIDGE_MODE)

- ea: `0x180026510`
- end: `0x1800267a3`
- name: `?CreateBridge@@YA?AVMux@NetSetup2@@AEAVTransaction@2@W4tagBRIDGE_MODE@@@Z`
- size: `659`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026144`

## callees

- `0x180001f0c`
- `0x18002165c`
- `0x180025924`
- `0x1800259c0`
- `0x180025a5c`
- `0x180025b0c`
- `0x180025cdc`
- `0x180025d28`
- `0x180025e38`
- `0x180026510`
- `0x18002ba50`
- `0x18002bb4c`
- `0x18002be3c`
- `0x18002d200`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180026614`
- `RPCRT4!UuidCreate` at `0x180026614`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180026647`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180026647`

## string_xrefs

- `0x180026694`: `COMPOSITEBUS\MS_IMPLAT_MP`

## pseudocode

```c
__int64 __fastcall CreateBridge(__int64 a1, _QWORD *a2, unsigned int a3)
{
  __int64 v6; // rdx
  RPC_STATUS v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rdx
  char v11[8]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int pExceptionObject; // [rsp+28h] [rbp-D8h] BYREF
  int v13; // [rsp+30h] [rbp-D0h]
  __int64 v14[3]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v15; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h]
  __int64 v17; // [rsp+68h] [rbp-98h]
  __int64 v18[4]; // [rsp+70h] [rbp-90h] BYREF
  UUID Uuid; // [rsp+90h] [rbp-70h] BYREF
  __int128 v20; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR sz[40]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v22[128]; // [rsp+100h] [rbp+0h] BYREF

  v17 = a1;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  std::wstring::wstring(v18);
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>((__int64)&v15, &NETSETUPPKEY_MUX_MuxType, v18);
  LOBYTE(v6) = 1;
  std::wstring::_Tidy(v18, v6, 0);
  pExceptionObject = a3;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    (__int64)&v15,
    (__int128 *)NETSETUPPKEY_Bridge_BridgeMode,
    (__int64)&pExceptionObject);
  pExceptionObject = 2;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    (__int64)&v15,
    (__int128 *)NETSETUPPKEY_Object_CreatedBy,
    (__int64)&pExceptionObject);
  NetSetup2::ObjectCreationTemplate::Create((__int64 *)&v15, &v20, a2, 8u);
  NetSetup2::details::TransactionBase::GetMuxById(a2, a1, &v20);
  v13 = 1;
  NetSetup2::Mux::CreateVirtualInterface(a1, v14);
  Uuid = 0;
  v7 = UuidCreate(&Uuid);
  if ( v7 )
  {
    pExceptionObject = v7 | 0x80010000;
    throw (long *)&pExceptionObject;
  }
  StringFromGUID2(&Uuid, sz, 40);
  swprintf_s<60>(v22, L"NDISIMPLAT(%ws)", sz);
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(
    (__int64)v14,
    (__int128 *)NETSETUPPKEY_Object_Id,
    (__int64)&Uuid);
  pExceptionObject = 6;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,unsigned long>(
    (__int64)v14,
    (__int128 *)NETSETUPPKEY_Interface_IfType,
    (__int64)&pExceptionObject);
  std::wstring::wstring(v18);
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(
    (__int64)v14,
    (__int128 *)NETSETUPPKEY_Interface_AnticipatedPnpHardwareId,
    v18);
  LOBYTE(v8) = 1;
  std::wstring::_Tidy(v18, v8, 0);
  std::wstring::wstring(v18);
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(
    (__int64)v14,
    (__int128 *)NETSETUPPKEY_Interface_AnticipatedPnpLocationPath,
    v18);
  LOBYTE(v9) = 1;
  std::wstring::_Tidy(v18, v9, 0);
  v11[0] = 1;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    (__int64)v14,
    (__int128 *)NETSETUPPKEY_Interface_RemovePnpDeviceWhenInterfaceRemoved,
    (__int64)v11);
  v11[0] = 1;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    (__int64)v14,
    (__int128 *)NETSETUPPKEY_Interface_IsHomeNetworkingBridge,
    (__int64)v11);
  v11[0] = 1;
  NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(
    (__int64)v14,
    (__int128 *)NETSETUPPKEY_Implat_IsDefaultTNic,
    (__int64)v11);
  NetSetup2::ObjectCreationTemplate::Create(v14, v18, a2, 2u);
  NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate((NetSetup2::ObjectCreationTemplate *)v14);
  NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate((NetSetup2::ObjectCreationTemplate *)&v15);
  return a1;
}

```

## disassembly

```asm
0x180026510  mov     [rsp-8+arg_18], rbx
0x180026515  push    rbp
0x180026516  push    rsi
0x180026517  push    rdi
0x180026518  lea     rbp, [rsp-90h]
0x180026520  sub     rsp, 190h
0x180026527  mov     rax, cs:__security_cookie
0x18002652e  xor     rax, rsp
0x180026531  mov     [rbp+0A0h+var_20], rax
0x180026538  mov     ebx, r8d
0x18002653b  mov     rsi, rdx
0x18002653e  mov     rdi, rcx
0x180026541  mov     [rsp+1A0h+var_138], rcx
0x180026546  mov     [rsp+1A0h+var_170], 0
0x18002654e  xor     eax, eax
0x180026550  xorps   xmm1, xmm1
0x180026553  movdqu  [rsp+1A0h+var_150], xmm1
0x180026559  mov     [rsp+1A0h+var_140], rax
0x18002655e  lea     rdx, aBridge; "Bridge"
0x180026565  lea     rcx, [rsp+1A0h+var_130]; void *
0x18002656a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18002656f  nop
0x180026570  lea     r8, [rsp+1A0h+var_130]
0x180026575  lea     rdx, NETSETUPPKEY_MUX_MuxType
0x18002657c  lea     rcx, [rsp+1A0h+var_150]
0x180026581  call    ??$SetPropertyToValue@$0BC@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(_NETSETUPPROPKEY const &,std::wstring const &)
0x180026586  nop
0x180026587  xor     r8d, r8d
0x18002658a  mov     dl, 1
0x18002658c  lea     rcx, [rsp+1A0h+var_130]
0x180026591  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026596  mov     [rsp+1A0h+pExceptionObject], ebx
0x18002659a  lea     r8, [rsp+1A0h+pExceptionObject]
0x18002659f  lea     rdx, NETSETUPPKEY_Bridge_BridgeMode
0x1800265a6  lea     rcx, [rsp+1A0h+var_150]
0x1800265ab  call    ??$SetPropertyToValue@$06K@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBK@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,ulong>(_NETSETUPPROPKEY const &,ulong const &)
0x1800265b0  mov     ebx, 2
0x1800265b5  mov     [rsp+1A0h+pExceptionObject], ebx
0x1800265b9  lea     r8, [rsp+1A0h+pExceptionObject]
0x1800265be  lea     rdx, NETSETUPPKEY_Object_CreatedBy
0x1800265c5  lea     rcx, [rsp+1A0h+var_150]
0x1800265ca  call    ??$SetPropertyToValue@$06K@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBK@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,ulong>(_NETSETUPPROPKEY const &,ulong const &)
0x1800265cf  lea     r9d, [rbx+6]
0x1800265d3  mov     r8, rsi
0x1800265d6  lea     rdx, [rbp+0A0h+var_100]
0x1800265da  lea     rcx, [rsp+1A0h+var_150]
0x1800265df  call    ?Create@ObjectCreationTemplate@NetSetup2@@QEAA?AU_GUID@@AEAVTransactionBase@details@2@W4_NETSETUP_OBJECT_TYPE@@@Z; NetSetup2::ObjectCreationTemplate::Create(NetSetup2::details::TransactionBase &,_NETSETUP_OBJECT_TYPE)
0x1800265e4  lea     r8, [rbp+0A0h+var_100]
0x1800265e8  mov     rdx, rdi
0x1800265eb  mov     rcx, rsi
0x1800265ee  call    ?GetMuxById@TransactionBase@details@NetSetup2@@QEAA?AVMux@3@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::GetMuxById(_GUID const &)
0x1800265f3  mov     [rsp+1A0h+var_170], 1
0x1800265fb  lea     rdx, [rsp+1A0h+var_168]
0x180026600  mov     rcx, rdi
0x180026603  call    ?CreateVirtualInterface@Mux@NetSetup2@@QEBA?AVNetworkInterfaceTemplate@2@XZ; NetSetup2::Mux::CreateVirtualInterface(void)
0x180026608  nop
0x180026609  xorps   xmm0, xmm0
0x18002660c  movups  xmmword ptr [rbp+0A0h+Uuid.Data1], xmm0
0x180026610  lea     rcx, [rbp+0A0h+Uuid]; Uuid
0x180026614  call    cs:__imp_UuidCreate
0x18002661a  test    eax, eax
0x18002661c  jz      short loc_180026639
0x18002661e  or      eax, 80010000h
0x180026623  mov     [rsp+1A0h+pExceptionObject], eax
0x180026627  lea     rdx, _TI1J; pThrowInfo
0x18002662e  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x180026633  call    _CxxThrowException_0
0x180026639  mov     r8d, 28h ; '('; cchMax
0x18002663f  lea     rdx, [rbp+0A0h+sz]; lpsz
0x180026643  lea     rcx, [rbp+0A0h+Uuid]; rguid
0x180026647  call    cs:__imp_StringFromGUID2
0x18002664d  lea     r8, [rbp+0A0h+sz]
0x180026651  lea     rdx, aNdisimplatWs; "NDISIMPLAT(%ws)"
0x180026658  lea     rcx, [rbp+0A0h+var_A0]
0x18002665c  call    ??$swprintf_s@$0DM@@@YAHAEAY0DM@GPEBGZZ; swprintf_s<60>(ushort (&)[60],ushort const *,...)
0x180026661  lea     r8, [rbp+0A0h+Uuid]
0x180026665  lea     rdx, NETSETUPPKEY_Object_Id
0x18002666c  lea     rcx, [rsp+1A0h+var_168]
0x180026671  call    ??$SetPropertyToValue@$0N@U_GUID@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBU_GUID@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<13,_GUID>(_NETSETUPPROPKEY const &,_GUID const &)
0x180026676  mov     [rsp+1A0h+pExceptionObject], 6
0x18002667e  lea     r8, [rsp+1A0h+pExceptionObject]
0x180026683  lea     rdx, NETSETUPPKEY_Interface_IfType
0x18002668a  lea     rcx, [rsp+1A0h+var_168]
0x18002668f  call    ??$SetPropertyToValue@$06K@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBK@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<7,ulong>(_NETSETUPPROPKEY const &,ulong const &)
0x180026694  lea     rdx, aCompositebusMs; "COMPOSITEBUS\\MS_IMPLAT_MP"
0x18002669b  lea     rcx, [rsp+1A0h+var_130]; void *
0x1800266a0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800266a5  nop
0x1800266a6  lea     r8, [rsp+1A0h+var_130]
0x1800266ab  lea     rdx, NETSETUPPKEY_Interface_AnticipatedPnpHardwareId
0x1800266b2  lea     rcx, [rsp+1A0h+var_168]
0x1800266b7  call    ??$SetPropertyToValue@$0BC@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(_NETSETUPPROPKEY const &,std::wstring const &)
0x1800266bc  nop
0x1800266bd  xor     r8d, r8d
0x1800266c0  mov     dl, 1
0x1800266c2  lea     rcx, [rsp+1A0h+var_130]
0x1800266c7  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800266cc  lea     rdx, [rbp+0A0h+var_A0]
0x1800266d0  lea     rcx, [rsp+1A0h+var_130]; void *
0x1800266d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800266da  nop
0x1800266db  lea     r8, [rsp+1A0h+var_130]
0x1800266e0  lea     rdx, NETSETUPPKEY_Interface_AnticipatedPnpLocationPath
0x1800266e7  lea     rcx, [rsp+1A0h+var_168]
0x1800266ec  call    ??$SetPropertyToValue@$0BC@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<18,std::wstring>(_NETSETUPPROPKEY const &,std::wstring const &)
0x1800266f1  nop
0x1800266f2  xor     r8d, r8d
0x1800266f5  mov     dl, 1
0x1800266f7  lea     rcx, [rsp+1A0h+var_130]
0x1800266fc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180026701  mov     [rsp+1A0h+var_180], 1
0x180026706  lea     r8, [rsp+1A0h+var_180]
0x18002670b  lea     rdx, NETSETUPPKEY_Interface_RemovePnpDeviceWhenInterfaceRemoved
0x180026712  lea     rcx, [rsp+1A0h+var_168]
0x180026717  call    ??$SetPropertyToValue@$0BB@_N@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x18002671c  mov     [rsp+1A0h+var_180], 1
0x180026721  lea     r8, [rsp+1A0h+var_180]
0x180026726  lea     rdx, NETSETUPPKEY_Interface_IsHomeNetworkingBridge
0x18002672d  lea     rcx, [rsp+1A0h+var_168]
0x180026732  call    ??$SetPropertyToValue@$0BB@_N@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x180026737  mov     [rsp+1A0h+var_180], 1
0x18002673c  lea     r8, [rsp+1A0h+var_180]
0x180026741  lea     rdx, NETSETUPPKEY_Implat_IsDefaultTNic
0x180026748  lea     rcx, [rsp+1A0h+var_168]
0x18002674d  call    ??$SetPropertyToValue@$0BB@_N@ObjectCreationTemplate@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ObjectCreationTemplate::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x180026752  mov     r9d, ebx
0x180026755  mov     r8, rsi
0x180026758  lea     rdx, [rsp+1A0h+var_130]
0x18002675d  lea     rcx, [rsp+1A0h+var_168]
0x180026762  call    ?Create@ObjectCreationTemplate@NetSetup2@@QEAA?AU_GUID@@AEAVTransactionBase@details@2@W4_NETSETUP_OBJECT_TYPE@@@Z; NetSetup2::ObjectCreationTemplate::Create(NetSetup2::details::TransactionBase &,_NETSETUP_OBJECT_TYPE)
0x180026767  nop
0x180026768  lea     rcx, [rsp+1A0h+var_168]; this
0x18002676d  call    ??1ObjectCreationTemplate@NetSetup2@@QEAA@XZ; NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate(void)
0x180026772  nop
0x180026773  lea     rcx, [rsp+1A0h+var_150]; this
0x180026778  call    ??1ObjectCreationTemplate@NetSetup2@@QEAA@XZ; NetSetup2::ObjectCreationTemplate::~ObjectCreationTemplate(void)
0x18002677d  mov     rax, rdi
0x180026780  mov     rcx, [rbp+0A0h+var_20]
0x180026787  xor     rcx, rsp; StackCookie
0x18002678a  call    __security_check_cookie
0x18002678f  mov     rbx, [rsp+1A0h+arg_18]
0x180026797  add     rsp, 190h
0x18002679e  pop     rdi
0x18002679f  pop     rsi
0x1800267a0  pop     rbp
0x1800267a1  retn
```
