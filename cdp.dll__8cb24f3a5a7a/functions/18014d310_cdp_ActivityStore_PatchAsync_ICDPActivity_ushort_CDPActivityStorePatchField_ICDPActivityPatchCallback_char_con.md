# cdp::ActivityStore::PatchAsync(ICDPActivity *,ushort,CDPActivityStorePatchField *,ICDPActivityPatchCallback *,char const *)

- ea: `0x18014d310`
- end: `0x18014d8b4`
- name: `?PatchAsync@ActivityStore@cdp@@UEAAJPEAVICDPActivity@@GPEAW4CDPActivityStorePatchField@@PEAVICDPActivityPatchCallback@@PEBD@Z`
- size: `1444`
- prototype: `int(cdp::ActivityStore *__hidden this, struct ICDPActivity *, unsigned __int16, enum CDPActivityStorePatchField *, struct ICDPActivityPatchCallback *, const char *)`
- caller_count: `0`
- callee_count: `25`
- tags: `installer_update`

## callees

- `0x180013da0`
- `0x180030190`
- `0x180056b50`
- `0x180056e58`
- `0x18006a280`
- `0x180074b50`
- `0x180075a14`
- `0x180077340`
- `0x18008dbc0`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800f5fa0`
- `0x180143248`
- `0x18014cb4c`
- `0x18014cc00`
- `0x18014d310`
- `0x18017223c`
- `0x180172290`
- `0x180178b5c`
- `0x1801909cc`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x1801fcb5a`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014d436`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014d501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014d5b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014d7b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014d436`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014d501`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014d5b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014d7b7`

## string_xrefs

- `0x18014d461`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014d52c`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014d5dc`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014d7e2`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014d847`: `{"text":"Attempted to patch with no fields and no callback so nothing will be done"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall cdp::ActivityStore::PatchAsync(
        cdp::ActivityStore *this,
        struct ICDPActivity *a2,
        unsigned __int16 a3,
        enum CDPActivityStorePatchField *a4,
        struct ICDPActivityPatchCallback *a5,
        const char *a6)
{
  size_t v7; // r15
  unsigned int v10; // ebx
  __int64 v12; // rax
  int v13; // edi
  DWORD CurrentThreadId; // ecx
  __int64 v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  int v19; // ecx
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  int v24; // edi
  DWORD v25; // eax
  __int64 v26; // r9
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rax
  const struct shared::ActivityData *v31; // rax
  char *v32; // rbx
  _QWORD *v33; // rdx
  int v34; // ebx
  DWORD v35; // eax
  __int64 v36; // r9
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v40; // rax
  int v41; // [rsp+28h] [rbp-410h]
  __int64 v42; // [rsp+30h] [rbp-408h]
  int v43; // [rsp+30h] [rbp-408h] BYREF
  _BYTE v44[4]; // [rsp+34h] [rbp-404h] BYREF
  int v45; // [rsp+38h] [rbp-400h] BYREF
  const char *v46; // [rsp+40h] [rbp-3F8h] BYREF
  std::_Ref_count_base **v47; // [rsp+48h] [rbp-3F0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-3E8h] BYREF
  void *v49[2]; // [rsp+58h] [rbp-3E0h] BYREF
  __int64 v50; // [rsp+68h] [rbp-3D0h]
  __int64 v51; // [rsp+70h] [rbp-3C8h] BYREF
  std::_Ref_count_base *v52; // [rsp+78h] [rbp-3C0h]
  std::_Ref_count_base *v53[2]; // [rsp+80h] [rbp-3B8h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+90h] [rbp-3A8h] BYREF
  _BYTE v55[56]; // [rsp+C8h] [rbp-370h] BYREF
  _BYTE v56[56]; // [rsp+100h] [rbp-338h] BYREF
  _BYTE v57[56]; // [rsp+138h] [rbp-300h] BYREF
  _BYTE v58[56]; // [rsp+170h] [rbp-2C8h] BYREF
  std::_Ref_count_base *v59[2]; // [rsp+1A8h] [rbp-290h] BYREF
  _QWORD v60[5]; // [rsp+1B8h] [rbp-280h] BYREF
  _BYTE v61[528]; // [rsp+1E0h] [rbp-258h] BYREF

  v7 = a3;
  cdp::TryCreateOrExtendCorrelationVector(v60, a6);
  if ( !a2 )
  {
    v43 = 236;
LABEL_6:
    v45 = -2147024809;
    Log<long &,char const (&)[21],int>(
      1,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v45,
      (unsigned int)"..\\activitystore.cpp",
      (__int64)&v43);
    v10 = v45;
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v60);
    return v10;
  }
  if ( a4 && !(_WORD)v7 )
  {
    v43 = 237;
    goto LABEL_6;
  }
  try
  {
    v45 = 0;
    v44[0] = 0;
    *(_OWORD *)v53 = 0;
    v12 = *(_QWORD *)a2;
    v46 = 0;
    v47 = v53;
    v13 = (*(__int64 (__fastcall **)(struct ICDPActivity *, const char **))(v12 + 208))(a2, &v46);
    cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(&v46);
    if ( v13 < 0 )
    {
      v46 = "..\\activitystore.cpp";
      LODWORD(v47) = 244;
      v43 = v13;
      CurrentThreadId = GetCurrentThreadId();
      v48 = CurrentThreadId;
      Log<long &,char const * &,int &,unsigned __int64>(
        CurrentThreadId,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v43,
        (unsigned int)&v46,
        (__int64)&v47,
        (__int64)&v48);
      v15 = cdp::ExceptionStackFromSourceLocationInfo(v49, &v46);
      v18 = cdp::ErrorCodeToString((unsigned int)v13, v16, v17, v15);
      ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v13, v18);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    shared::GetEffectiveAppId(&v51, v53[0], v44);
    if ( v44[0] && !(unsigned __int8)IsValidCrossPlatformAppId_0(v51) )
    {
      v46 = "..\\activitystore.cpp";
      LODWORD(v47) = 246;
      v43 = -2147024891;
      v48 = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v19,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v43,
        (unsigned int)&v46,
        (__int64)&v47,
        (__int64)&v48);
      v20 = cdp::ExceptionStackFromSourceLocationInfo(v49, &v46);
      v23 = cdp::ErrorCodeToString(2147942405LL, v21, v22, v20);
      ConnectedDevices::Exception::Exception(v55, 2147942405LL, v23);
      throw (ConnectedDevices::Exception *)v55;
    }
    v24 = (*(__int64 (__fastcall **)(struct ICDPActivity *, __int64))(*(_QWORD *)a2 + 216LL))(a2, v51);
    if ( v24 < 0 )
    {
      v46 = "..\\activitystore.cpp";
      LODWORD(v47) = 247;
      v43 = v24;
      v25 = GetCurrentThreadId();
      v48 = v25;
      Log<long &,char const * &,int &,unsigned __int64>(
        v25,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v43,
        (unsigned int)&v46,
        (__int64)&v47,
        (__int64)&v48);
      v26 = cdp::ExceptionStackFromSourceLocationInfo(v49, &v46);
      v29 = cdp::ErrorCodeToString((unsigned int)v24, v27, v28, v26);
      ConnectedDevices::Exception::Exception(v56, (unsigned int)v24, v29);
      throw (ConnectedDevices::Exception *)v56;
    }
    if ( (_WORD)v7 )
    {
      cdp::query_interface<cdp::ICDPInternalActivityBase,ICDPActivity>(v59, a2);
      if ( !v59[0] )
      {
        v46 = "..\\activitystore.cpp";
        LODWORD(v47) = 252;
        v30 = cdp::MakeException<cdp::HResultException<-2147467262>,>(
                v58,
                &v46,
                "ActivityStore missing required interface");
        cdp::CdpThrow<cdp::HResultException<-2147467262>>(&v46, v30);
      }
      v31 = (const struct shared::ActivityData *)(*(__int64 (__fastcall **)(std::_Ref_count_base *))(*(_QWORD *)v59[0] + 24LL))(v59[0]);
      shared::ActivityData::ActivityData((shared::ActivityData *)v61, v31);
      *(_OWORD *)v49 = 0;
      v50 = 0;
      std::vector<enum CDPActivityStorePatchField>::_Buy_nonzero(v49, v7);
      v32 = (char *)v49[0];
      memmove_0(v49[0], a4, v7);
      v49[1] = &v32[v7];
      v48 = 0;
      std::_Tidy_guard<std::vector<char>>::~_Tidy_guard<std::vector<char>>(&v48);
      v33 = v60;
      if ( v60[3] > 0xFu )
        v33 = (_QWORD *)v60[0];
      (*(void (__fastcall **)(_QWORD, _BYTE *, void **, struct ICDPActivityPatchCallback *, _QWORD *))(**((_QWORD **)this + 4) + 48LL))(
        *((_QWORD *)this + 4),
        v61,
        v49,
        a5,
        v33);
      std::vector<enum CDPActivityStorePatchField>::_Tidy(v49);
      shared::ActivityData::~ActivityData((shared::ActivityData *)v61);
      if ( v59[1] )
        std::_Ref_count_base::_Decref(v59[1]);
    }
    else if ( a5 )
    {
      *(_OWORD *)v59 = 0;
      v34 = (*(__int64 (__fastcall **)(struct ICDPActivity *, std::_Ref_count_base **))(*(_QWORD *)a2 + 24LL))(a2, v59);
      if ( v34 < 0 )
      {
        v46 = "..\\activitystore.cpp";
        LODWORD(v47) = 261;
        v43 = v34;
        v35 = GetCurrentThreadId();
        v48 = v35;
        Log<long &,char const * &,int &,unsigned __int64>(
          v35,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v43,
          (unsigned int)&v46,
          (__int64)&v47,
          (__int64)&v48);
        v36 = cdp::ExceptionStackFromSourceLocationInfo(v49, &v46);
        v39 = cdp::ErrorCodeToString((unsigned int)v34, v37, v38, v36);
        ConnectedDevices::Exception::Exception(v57, (unsigned int)v34, v39);
        throw (ConnectedDevices::Exception *)v57;
      }
      (*(void (__fastcall **)(struct ICDPActivityPatchCallback *, std::_Ref_count_base **))(*(_QWORD *)a5 + 24LL))(
        a5,
        v59);
    }
    else
    {
      Log<>(3, "{\"text\":\"Attempted to patch with no fields and no callback so nothing will be done\"}");
    }
    if ( v52 )
      std::_Ref_count_base::_Decref(v52);
    if ( v53[1] )
      std::_Ref_count_base::_Decref(v53[1]);
  }
  catch ( ... )
  {
    LODWORD(v40) = GetCurrentThreadId();
    v48 = v40;
    v43 = 269;
    cdp::CatchAllToHR<char const (&)[21],int,unsigned __int64>(
      &v45,
      "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Failed to p"
      "atch activity\"}",
      (unsigned int)"..\\activitystore.cpp",
      (const char *)&v43,
      (const char *)&v48,
      v41,
      v42);
  }
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v60);
  return 0;
}

```

## disassembly

```asm
0x18014d310  push    rbx
0x18014d312  push    rsi
0x18014d313  push    rdi
0x18014d314  push    r12
0x18014d316  push    r13
0x18014d318  push    r14
0x18014d31a  push    r15
0x18014d31c  sub     rsp, 400h
0x18014d323  mov     rax, cs:__security_cookie
0x18014d32a  xor     rax, rsp
0x18014d32d  mov     [rsp+438h+var_48], rax
0x18014d335  mov     r12, r9
0x18014d338  movzx   r15d, r8w
0x18014d33c  mov     rbx, rdx
0x18014d33f  mov     r13, rcx
0x18014d342  mov     r14, [rsp+438h+arg_20]
0x18014d34a  mov     rdx, [rsp+438h+arg_28]
0x18014d352  lea     rcx, [rsp+438h+var_280]
0x18014d35a  call    ?TryCreateOrExtendCorrelationVector@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::TryCreateOrExtendCorrelationVector(char const *)
0x18014d35f  nop
0x18014d360  xor     ecx, ecx
0x18014d362  test    rbx, rbx
0x18014d365  jnz     short loc_18014D371
0x18014d367  mov     [rsp+438h+var_408], 0ECh
0x18014d36f  jmp     short loc_18014D384
0x18014d371  test    r12, r12
0x18014d374  jz      short loc_18014D3CB
0x18014d376  test    r15w, r15w
0x18014d37a  jnz     short loc_18014D3CB
0x18014d37c  mov     [rsp+438h+var_408], 0EDh
0x18014d384  lea     rax, [rsp+438h+var_408]
0x18014d389  mov     [rsp+438h+var_418], rax
0x18014d38e  mov     [rsp+438h+var_400], 80070057h
0x18014d396  lea     r9, aActivitystoreC; "..\\activitystore.cpp"
0x18014d39d  lea     r8, [rsp+438h+var_400]
0x18014d3a2  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014d3a9  mov     ecx, 1
0x18014d3ae  call    ??$Log@AEAJAEAY0BF@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BF@$$CBD$$QEAH@Z; Log<long &,char const (&)[21],int>(CDPLogLevel,char const *,long &,char const (&)[21],int &&)
0x18014d3b3  mov     ebx, [rsp+438h+var_400]
0x18014d3b7  lea     rcx, [rsp+438h+var_280]; void *
0x18014d3bf  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18014d3c4  mov     eax, ebx
0x18014d3c6  jmp     loc_18014D891
0x18014d3cb  mov     esi, ecx
0x18014d3cd  mov     [rsp+438h+var_400], ecx
0x18014d3d1  mov     [rsp+438h+var_404], cl
0x18014d3d5  xorps   xmm0, xmm0
0x18014d3d8  movdqu  xmmword ptr [rsp+438h+var_3B8], xmm0
0x18014d3e1  mov     rax, [rbx]
0x18014d3e4  mov     [rsp+438h+var_3F8], rcx
0x18014d3e9  lea     rcx, [rsp+438h+var_3B8]
0x18014d3f1  mov     [rsp+438h+var_3F0], rcx
0x18014d3f6  lea     rdx, [rsp+438h+var_3F8]
0x18014d3fb  mov     rcx, rbx
0x18014d3fe  mov     rax, [rax+0D0h]
0x18014d405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d40a  mov     edi, eax
0x18014d40c  lea     rcx, [rsp+438h+var_3F8]
0x18014d411  call    ??1?$address_of@VICDPCrossPlatformAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(void)
0x18014d416  test    edi, edi
0x18014d418  jns     loc_18014D4AD
0x18014d41e  lea     rax, aActivitystoreC; "..\\activitystore.cpp"
0x18014d425  mov     [rsp+438h+var_3F8], rax
0x18014d42a  mov     dword ptr [rsp+438h+var_3F0], 0F4h
0x18014d432  mov     [rsp+438h+var_408], edi
0x18014d436  call    cs:__imp_GetCurrentThreadId
0x18014d43c  mov     ecx, eax
0x18014d43e  mov     [rsp+438h+var_3E8], rcx
0x18014d443  lea     rax, [rsp+438h+var_3E8]
0x18014d448  mov     [rsp+438h+var_410], rax
0x18014d44d  lea     rax, [rsp+438h+var_3F0]
0x18014d452  mov     [rsp+438h+var_418], rax
0x18014d457  lea     r9, [rsp+438h+var_3F8]
0x18014d45c  lea     r8, [rsp+438h+var_408]
0x18014d461  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014d468  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014d46d  lea     rdx, [rsp+438h+var_3F8]
0x18014d472  lea     rcx, [rsp+438h+var_3E0]
0x18014d477  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014d47c  mov     r9, rax
0x18014d47f  mov     ecx, edi
0x18014d481  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014d486  mov     r8, rax
0x18014d489  mov     edx, edi
0x18014d48b  lea     rcx, [rsp+438h+pExceptionObject]
0x18014d493  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014d498  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014d49f  lea     rcx, [rsp+438h+pExceptionObject]; pExceptionObject
0x18014d4a7  call    _CxxThrowException_0
0x18014d4ad  lea     r8, [rsp+438h+var_404]
0x18014d4b2  mov     rdx, [rsp+438h+var_3B8]
0x18014d4ba  lea     rcx, [rsp+438h+var_3C8]
0x18014d4bf  call    ?GetEffectiveAppId@shared@@YA?AV?$shared_ptr@VICDPCrossPlatformAppId@@@std@@PEAVICDPCrossPlatformAppId@@PEA_N@Z; shared::GetEffectiveAppId(ICDPCrossPlatformAppId *,bool *)
0x18014d4c4  nop
0x18014d4c5  xor     edi, edi
0x18014d4c7  cmp     [rsp+438h+var_404], dil
0x18014d4cc  jz      loc_18014D578
0x18014d4d2  mov     rcx, [rsp+438h+var_3C8]
0x18014d4d7  call    IsValidCrossPlatformAppId_0
0x18014d4dc  test    al, al
0x18014d4de  jnz     loc_18014D578
0x18014d4e4  lea     rax, aActivitystoreC; "..\\activitystore.cpp"
0x18014d4eb  mov     [rsp+438h+var_3F8], rax
0x18014d4f0  mov     dword ptr [rsp+438h+var_3F0], 0F6h
0x18014d4f8  mov     ebx, 80070005h
0x18014d4fd  mov     [rsp+438h+var_408], ebx
0x18014d501  call    cs:__imp_GetCurrentThreadId
0x18014d507  mov     eax, eax
0x18014d509  mov     [rsp+438h+var_3E8], rax
0x18014d50e  lea     rax, [rsp+438h+var_3E8]
0x18014d513  mov     [rsp+438h+var_410], rax
0x18014d518  lea     rax, [rsp+438h+var_3F0]
0x18014d51d  mov     [rsp+438h+var_418], rax
0x18014d522  lea     r9, [rsp+438h+var_3F8]
0x18014d527  lea     r8, [rsp+438h+var_408]
0x18014d52c  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014d533  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014d538  lea     rdx, [rsp+438h+var_3F8]
0x18014d53d  lea     rcx, [rsp+438h+var_3E0]
0x18014d542  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014d547  mov     r9, rax
0x18014d54a  mov     ecx, ebx
0x18014d54c  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014d551  mov     r8, rax
0x18014d554  mov     edx, ebx
0x18014d556  lea     rcx, [rsp+438h+var_370]
0x18014d55e  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014d563  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014d56a  lea     rcx, [rsp+438h+var_370]; pExceptionObject
0x18014d572  call    _CxxThrowException_0
0x18014d578  mov     rax, [rbx]
0x18014d57b  mov     rdx, [rsp+438h+var_3C8]
0x18014d580  mov     rcx, rbx
0x18014d583  mov     rax, [rax+0D8h]
0x18014d58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d58f  mov     edi, eax
0x18014d591  test    eax, eax
0x18014d593  jns     loc_18014D628
0x18014d599  lea     rax, aActivitystoreC; "..\\activitystore.cpp"
0x18014d5a0  mov     [rsp+438h+var_3F8], rax
0x18014d5a5  mov     dword ptr [rsp+438h+var_3F0], 0F7h
0x18014d5ad  mov     [rsp+438h+var_408], edi
0x18014d5b1  call    cs:__imp_GetCurrentThreadId
0x18014d5b7  mov     ecx, eax
0x18014d5b9  mov     [rsp+438h+var_3E8], rcx
0x18014d5be  lea     rax, [rsp+438h+var_3E8]
0x18014d5c3  mov     [rsp+438h+var_410], rax
0x18014d5c8  lea     rax, [rsp+438h+var_3F0]
0x18014d5cd  mov     [rsp+438h+var_418], rax
0x18014d5d2  lea     r9, [rsp+438h+var_3F8]
0x18014d5d7  lea     r8, [rsp+438h+var_408]
0x18014d5dc  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014d5e3  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014d5e8  lea     rdx, [rsp+438h+var_3F8]
0x18014d5ed  lea     rcx, [rsp+438h+var_3E0]
0x18014d5f2  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014d5f7  mov     r9, rax
0x18014d5fa  mov     ecx, edi
0x18014d5fc  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014d601  mov     r8, rax
0x18014d604  mov     edx, edi
0x18014d606  lea     rcx, [rsp+438h+var_338]
0x18014d60e  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014d613  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014d61a  lea     rcx, [rsp+438h+var_338]; pExceptionObject
0x18014d622  call    _CxxThrowException_0
0x18014d628  test    r15w, r15w
0x18014d62c  jz      loc_18014D76A
0x18014d632  mov     rdx, rbx
0x18014d635  lea     rcx, [rsp+438h+var_290]
0x18014d63d  call    ??$query_interface@VICDPInternalActivityBase@cdp@@VICDPActivity@@@cdp@@YA?AV?$shared_ptr@VICDPInternalActivityBase@cdp@@@std@@PEAVICDPActivity@@@Z; cdp::query_interface<cdp::ICDPInternalActivityBase,ICDPActivity>(ICDPActivity *)
0x18014d642  nop
0x18014d643  mov     rcx, [rsp+438h+var_290]
0x18014d64b  test    rcx, rcx
0x18014d64e  jnz     short loc_18014D68C
0x18014d650  lea     rax, aActivitystoreC; "..\\activitystore.cpp"
0x18014d657  mov     [rsp+438h+var_3F8], rax
0x18014d65c  mov     dword ptr [rsp+438h+var_3F0], 0FCh
0x18014d664  lea     r8, aActivitystoreM; "ActivityStore missing required interfac"...
0x18014d66b  lea     rdx, [rsp+438h+var_3F8]
0x18014d670  lea     rcx, [rsp+438h+var_2C8]
0x18014d678  call    ??$MakeException@V?$HResultException@$0?HPPPLPPO@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPLPPO@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147467262>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x18014d67d  nop
0x18014d67e  mov     rdx, rax
0x18014d681  lea     rcx, [rsp+438h+var_3F8]
0x18014d686  call    ??$CdpThrow@V?$HResultException@$0?HPPPLPPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPPLPPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147467262>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147467262> &&)
0x18014d68c  mov     rax, [rcx]
0x18014d68f  mov     rax, [rax+18h]
0x18014d693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d698  mov     rdx, rax; struct shared::ActivityData *
0x18014d69b  lea     rcx, [rsp+438h+var_258]; this
0x18014d6a3  call    ??0ActivityData@shared@@QEAA@AEBU01@@Z; shared::ActivityData::ActivityData(shared::ActivityData const &)
0x18014d6a8  nop
0x18014d6a9  xorps   xmm0, xmm0
0x18014d6ac  movdqu  xmmword ptr [rsp+438h+var_3E0], xmm0
0x18014d6b2  mov     [rsp+438h+var_3D0], 0
0x18014d6bb  mov     rdx, r15
0x18014d6be  lea     rcx, [rsp+438h+var_3E0]
0x18014d6c3  call    ?_Buy_nonzero@?$vector@W4CDPActivityStorePatchField@@V?$allocator@W4CDPActivityStorePatchField@@@std@@@std@@AEAAX_K@Z; std::vector<CDPActivityStorePatchField>::_Buy_nonzero(unsigned __int64)
0x18014d6c8  mov     rbx, [rsp+438h+var_3E0]
0x18014d6cd  mov     r8, r15; Size
0x18014d6d0  mov     rdx, r12; Src
0x18014d6d3  mov     rcx, rbx; void *
0x18014d6d6  call    memmove_0
0x18014d6db  lea     rax, [r15+rbx]
0x18014d6df  mov     [rsp+438h+var_3E0+8], rax
0x18014d6e4  xor     edi, edi
0x18014d6e6  mov     [rsp+438h+var_3E8], rdi
0x18014d6eb  lea     rcx, [rsp+438h+var_3E8]
0x18014d6f0  call    ??1?$_Tidy_guard@V?$vector@DV?$allocator@D@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<char>>::~_Tidy_guard<std::vector<char>>(void)
0x18014d6f5  nop
0x18014d6f6  mov     rcx, [r13+20h]
0x18014d6fa  mov     rax, [rcx]
0x18014d6fd  lea     rdx, [rsp+438h+var_280]
0x18014d705  cmp     [rsp+438h+var_268], 0Fh
0x18014d70e  cmova   rdx, [rsp+438h+var_280]
0x18014d717  mov     [rsp+438h+var_418], rdx
0x18014d71c  mov     r9, r14
0x18014d71f  lea     r8, [rsp+438h+var_3E0]
0x18014d724  lea     rdx, [rsp+438h+var_258]
0x18014d72c  mov     rax, [rax+30h]
0x18014d730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d735  nop
0x18014d736  lea     rcx, [rsp+438h+var_3E0]; void *
0x18014d73b  call    ?_Tidy@?$vector@W4CDPActivityStorePatchField@@V?$allocator@W4CDPActivityStorePatchField@@@std@@@std@@AEAAXXZ; std::vector<CDPActivityStorePatchField>::_Tidy(void)
0x18014d740  nop
0x18014d741  lea     rcx, [rsp+438h+var_258]; this
0x18014d749  call    ??1ActivityData@shared@@QEAA@XZ; shared::ActivityData::~ActivityData(void)
0x18014d74e  nop
0x18014d74f  mov     rcx, [rsp+438h+var_290+8]; this
0x18014d757  test    rcx, rcx
0x18014d75a  jz      loc_18014D859
0x18014d760  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014d765  jmp     loc_18014D859
0x18014d76a  test    r14, r14
0x18014d76d  jz      loc_18014D847
0x18014d773  xorps   xmm0, xmm0
0x18014d776  movups  xmmword ptr [rsp+438h+var_290], xmm0
0x18014d77e  mov     rax, [rbx]
0x18014d781  lea     rdx, [rsp+438h+var_290]
0x18014d789  mov     rcx, rbx
0x18014d78c  mov     rax, [rax+18h]
0x18014d790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d795  mov     ebx, eax
0x18014d797  test    eax, eax
0x18014d799  jns     loc_18014D82E
0x18014d79f  lea     rax, aActivitystoreC; "..\\activitystore.cpp"
0x18014d7a6  mov     [rsp+438h+var_3F8], rax
0x18014d7ab  mov     dword ptr [rsp+438h+var_3F0], 105h
0x18014d7b3  mov     [rsp+438h+var_408], ebx
0x18014d7b7  call    cs:__imp_GetCurrentThreadId
0x18014d7bd  mov     ecx, eax
0x18014d7bf  mov     [rsp+438h+var_3E8], rcx
0x18014d7c4  lea     rax, [rsp+438h+var_3E8]
0x18014d7c9  mov     [rsp+438h+var_410], rax
0x18014d7ce  lea     rax, [rsp+438h+var_3F0]
0x18014d7d3  mov     [rsp+438h+var_418], rax
0x18014d7d8  lea     r9, [rsp+438h+var_3F8]
0x18014d7dd  lea     r8, [rsp+438h+var_408]
0x18014d7e2  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014d7e9  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014d7ee  lea     rdx, [rsp+438h+var_3F8]
0x18014d7f3  lea     rcx, [rsp+438h+var_3E0]
0x18014d7f8  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014d7fd  mov     r9, rax
0x18014d800  mov     ecx, ebx
0x18014d802  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014d807  mov     r8, rax
0x18014d80a  mov     edx, ebx
0x18014d80c  lea     rcx, [rsp+438h+var_300]
0x18014d814  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014d819  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014d820  lea     rcx, [rsp+438h+var_300]; pExceptionObject
0x18014d828  call    _CxxThrowException_0
0x18014d82e  mov     rax, [r14]
0x18014d831  lea     rdx, [rsp+438h+var_290]
0x18014d839  mov     rcx, r14
0x18014d83c  mov     rax, [rax+18h]
0x18014d840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014d845  jmp     short loc_18014D859
0x18014d847  lea     rdx, aTextAttemptedT_1; "{\"text\":\"Attempted to patch with no "...
0x18014d84e  mov     ecx, 3
0x18014d853  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18014d858  nop
0x18014d859  mov     rcx, [rsp+438h+var_3C0]; this
0x18014d85e  test    rcx, rcx
0x18014d861  jz      short loc_18014D869
0x18014d863  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014d868  nop
0x18014d869  mov     rcx, [rsp+438h+var_3B8+8]; this
0x18014d871  test    rcx, rcx
0x18014d874  jz      short loc_18014D87C
0x18014d876  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014d87b  nop
0x18014d87c  jmp     short loc_18014D882
0x18014d87e  mov     esi, [rsp+438h+var_400]
0x18014d882  lea     rcx, [rsp+438h+var_280]; void *
0x18014d88a  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18014d88f  mov     eax, esi
0x18014d891  mov     rcx, [rsp+438h+var_48]
  ... truncated ...
```
