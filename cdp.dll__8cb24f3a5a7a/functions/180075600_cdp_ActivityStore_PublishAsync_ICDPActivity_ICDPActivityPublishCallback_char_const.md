# cdp::ActivityStore::PublishAsync(ICDPActivity *,ICDPActivityPublishCallback *,char const *)

- ea: `0x180075600`
- end: `0x180075a0e`
- name: `?PublishAsync@ActivityStore@cdp@@UEAAJPEAVICDPActivity@@PEAVICDPActivityPublishCallback@@PEBD@Z`
- size: `1038`
- prototype: `__int64 __fastcall(cdp::ActivityStore *__hidden this, struct ICDPActivity *, struct ICDPActivityPublishCallback *, const char *)`
- caller_count: `0`
- callee_count: `21`
- tags: ``

## callees

- `0x180013da0`
- `0x180030190`
- `0x180056b50`
- `0x180056e58`
- `0x18006a280`
- `0x180074b50`
- `0x180075600`
- `0x180075a14`
- `0x180075d78`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800f5fa0`
- `0x180143248`
- `0x18014cb4c`
- `0x18014cc00`
- `0x180178b5c`
- `0x1801909cc`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800756f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800757c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180075878`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800756f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800757c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180075878`

## string_xrefs

- `0x180075722`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800757f0`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x1800758a3`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall cdp::ActivityStore::PublishAsync(
        cdp::ActivityStore *this,
        struct ICDPActivity *a2,
        struct ICDPActivityPublishCallback *a3,
        const char *a4)
{
  int v7; // eax
  __int64 v8; // rax
  int v9; // edi
  DWORD CurrentThreadId; // ecx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  int v20; // edi
  DWORD v21; // eax
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rax
  const struct shared::ActivityData *v27; // rax
  _QWORD *v28; // r9
  unsigned int v29; // ebx
  __int64 v31; // rax
  int v32; // [rsp+28h] [rbp-3C0h]
  __int64 v33; // [rsp+30h] [rbp-3B8h]
  _BYTE v34[4]; // [rsp+30h] [rbp-3B8h] BYREF
  int v35; // [rsp+34h] [rbp-3B4h] BYREF
  int v36; // [rsp+38h] [rbp-3B0h] BYREF
  const char *v37; // [rsp+40h] [rbp-3A8h] BYREF
  std::_Ref_count_base **v38; // [rsp+48h] [rbp-3A0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-398h] BYREF
  __int64 v40; // [rsp+58h] [rbp-390h] BYREF
  std::_Ref_count_base *v41; // [rsp+60h] [rbp-388h]
  std::_Ref_count_base *v42[2]; // [rsp+68h] [rbp-380h] BYREF
  __int64 v43; // [rsp+78h] [rbp-370h] BYREF
  std::_Ref_count_base *v44; // [rsp+80h] [rbp-368h]
  _BYTE v45[24]; // [rsp+88h] [rbp-360h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+A0h] [rbp-348h] BYREF
  _BYTE v47[56]; // [rsp+D8h] [rbp-310h] BYREF
  _BYTE v48[56]; // [rsp+110h] [rbp-2D8h] BYREF
  _BYTE v49[56]; // [rsp+148h] [rbp-2A0h] BYREF
  _QWORD v50[4]; // [rsp+180h] [rbp-268h] BYREF
  _BYTE v51[528]; // [rsp+1A0h] [rbp-248h] BYREF

  cdp::TryCreateOrExtendCorrelationVector(v50, a4);
  if ( !a2 )
  {
    v36 = -2147024809;
    v35 = 198;
LABEL_5:
    Log<long &,char const (&)[21],int>(
      1,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
      (unsigned int)&v36,
      (unsigned int)"..\\activitystore.cpp",
      (__int64)&v35);
    v29 = v36;
    goto LABEL_24;
  }
  v7 = cdp::ActivityStore::CheckActivityManager(this);
  if ( v7 < 0 )
  {
    v36 = v7;
    v35 = 199;
    goto LABEL_5;
  }
  try
  {
    v29 = 0;
    v36 = 0;
    *(_OWORD *)v42 = 0;
    v8 = *(_QWORD *)a2;
    v37 = 0;
    v38 = v42;
    v9 = (*(__int64 (__fastcall **)(struct ICDPActivity *, const char **))(v8 + 208))(a2, &v37);
    cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(&v37);
    if ( v9 < 0 )
    {
      v37 = "..\\activitystore.cpp";
      LODWORD(v38) = 207;
      v35 = v9;
      CurrentThreadId = GetCurrentThreadId();
      v39 = CurrentThreadId;
      Log<long &,char const * &,int &,unsigned __int64>(
        CurrentThreadId,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v35,
        (unsigned int)&v37,
        (__int64)&v38,
        (__int64)&v39);
      v11 = cdp::ExceptionStackFromSourceLocationInfo(v45, &v37);
      v14 = cdp::ErrorCodeToString((unsigned int)v9, v12, v13, v11);
      ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v9, v14);
      throw (ConnectedDevices::Exception *)pExceptionObject;
    }
    v34[0] = 0;
    shared::GetEffectiveAppId(&v40, v42[0], v34);
    if ( v34[0] && !(unsigned __int8)IsValidCrossPlatformAppId_0(v40) )
    {
      v37 = "..\\activitystore.cpp";
      LODWORD(v38) = 215;
      v35 = -2147024891;
      v39 = GetCurrentThreadId();
      Log<long &,char const * &,int &,unsigned __int64>(
        v15,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v35,
        (unsigned int)&v37,
        (__int64)&v38,
        (__int64)&v39);
      v16 = cdp::ExceptionStackFromSourceLocationInfo(v45, &v37);
      v19 = cdp::ErrorCodeToString(2147942405LL, v17, v18, v16);
      ConnectedDevices::Exception::Exception(v47, 2147942405LL, v19);
      throw (ConnectedDevices::Exception *)v47;
    }
    v20 = (*(__int64 (__fastcall **)(struct ICDPActivity *, __int64))(*(_QWORD *)a2 + 216LL))(a2, v40);
    if ( v20 < 0 )
    {
      v37 = "..\\activitystore.cpp";
      LODWORD(v38) = 216;
      v35 = v20;
      v21 = GetCurrentThreadId();
      v39 = v21;
      Log<long &,char const * &,int &,unsigned __int64>(
        v21,
        (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
        (unsigned int)&v35,
        (unsigned int)&v37,
        (__int64)&v38,
        (__int64)&v39);
      v22 = cdp::ExceptionStackFromSourceLocationInfo(v45, &v37);
      v25 = cdp::ErrorCodeToString((unsigned int)v20, v23, v24, v22);
      ConnectedDevices::Exception::Exception(v48, (unsigned int)v20, v25);
      throw (ConnectedDevices::Exception *)v48;
    }
    cdp::query_interface<cdp::ICDPInternalActivityBase,ICDPActivity>(&v43, a2);
    if ( !v43 )
    {
      v37 = "..\\activitystore.cpp";
      LODWORD(v38) = 219;
      v26 = cdp::MakeException<cdp::HResultException<-2147467262>,>(
              v49,
              &v37,
              "ActivityStore missing required interface");
      cdp::CdpThrow<cdp::HResultException<-2147467262>>(&v37, v26);
    }
    v27 = (const struct shared::ActivityData *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 24LL))(v43);
    shared::ActivityData::ActivityData((shared::ActivityData *)v51, v27);
    v28 = v50;
    if ( v50[3] > 0xFu )
      v28 = (_QWORD *)v50[0];
    (*(void (__fastcall **)(_QWORD, _BYTE *, struct ICDPActivityPublishCallback *, _QWORD *))(**((_QWORD **)this + 4)
                                                                                            + 32LL))(
      *((_QWORD *)this + 4),
      v51,
      a3,
      v28);
    shared::ActivityData::~ActivityData((shared::ActivityData *)v51);
    if ( v44 )
      std::_Ref_count_base::_Decref(v44);
    if ( v41 )
      std::_Ref_count_base::_Decref(v41);
    if ( v42[1] )
      std::_Ref_count_base::_Decref(v42[1]);
  }
  catch ( ... )
  {
    LODWORD(v31) = GetCurrentThreadId();
    v39 = v31;
    v35 = 224;
    cdp::CatchAllToHR<char const (&)[21],int,unsigned __int64>(
      &v36,
      "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Failed to p"
      "ublish activity\"}",
      (unsigned int)"..\\activitystore.cpp",
      (const char *)&v35,
      (const char *)&v39,
      v32,
      v33);
  }
LABEL_24:
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v50);
  return v29;
}

```

## disassembly

```asm
0x180075600  push    rbx
0x180075602  push    rsi
0x180075603  push    rdi
0x180075604  push    r14
0x180075606  push    r15
0x180075608  sub     rsp, 3C0h
0x18007560f  mov     rax, cs:__security_cookie
0x180075616  xor     rax, rsp
0x180075619  mov     [rsp+3E8h+var_38], rax
0x180075621  mov     r15, r8
0x180075624  mov     rsi, rdx
0x180075627  mov     r14, rcx
0x18007562a  mov     rdx, r9
0x18007562d  lea     rcx, [rsp+3E8h+var_268]
0x180075635  call    ?TryCreateOrExtendCorrelationVector@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBD@Z; cdp::TryCreateOrExtendCorrelationVector(char const *)
0x18007563a  nop
0x18007563b  test    rsi, rsi
0x18007563e  jnz     short loc_180075652
0x180075640  mov     [rsp+3E8h+var_3B0], 80070057h
0x180075648  mov     [rsp+3E8h+var_3B4], 0C6h
0x180075650  jmp     short loc_18007566A
0x180075652  mov     rcx, r14; this
0x180075655  call    ?CheckActivityManager@ActivityStore@cdp@@AEAAJXZ; cdp::ActivityStore::CheckActivityManager(void)
0x18007565a  test    eax, eax
0x18007565c  jns     short loc_180075696
0x18007565e  mov     [rsp+3E8h+var_3B0], eax
0x180075662  mov     [rsp+3E8h+var_3B4], 0C7h
0x18007566a  lea     rax, [rsp+3E8h+var_3B4]
0x18007566f  mov     [rsp+3E8h+var_3C8], rax
0x180075674  lea     r9, aActivitystoreC; "..\\activitystore.cpp"
0x18007567b  lea     r8, [rsp+3E8h+var_3B0]
0x180075680  lea     rdx, aHr0x08xFileSLi_93; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180075687  mov     ecx, 1
0x18007568c  call    ??$Log@AEAJAEAY0BF@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BF@$$CBD$$QEAH@Z; Log<long &,char const (&)[21],int>(CDPLogLevel,char const *,long &,char const (&)[21],int &&)
0x180075691  jmp     loc_1800759DC
0x180075696  xor     ebx, ebx
0x180075698  mov     [rsp+3E8h+var_3B0], ebx
0x18007569c  xorps   xmm0, xmm0
0x18007569f  movdqu  xmmword ptr [rsp+3E8h+var_380], xmm0
0x1800756a5  mov     rax, [rsi]
0x1800756a8  mov     [rsp+3E8h+var_3A8], rbx
0x1800756ad  lea     rcx, [rsp+3E8h+var_380]
0x1800756b2  mov     [rsp+3E8h+var_3A0], rcx
0x1800756b7  lea     rdx, [rsp+3E8h+var_3A8]
0x1800756bc  mov     rcx, rsi
0x1800756bf  mov     rax, [rax+0D0h]
0x1800756c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800756cb  mov     edi, eax
0x1800756cd  lea     rcx, [rsp+3E8h+var_3A8]
0x1800756d2  call    ??1?$address_of@VICDPCrossPlatformAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(void)
0x1800756d7  test    edi, edi
0x1800756d9  jns     loc_180075771
0x1800756df  lea     rax, aActivitystoreC; "..\\activitystore.cpp"
0x1800756e6  mov     [rsp+3E8h+var_3A8], rax
0x1800756eb  mov     dword ptr [rsp+3E8h+var_3A0], 0CFh
0x1800756f3  mov     [rsp+3E8h+var_3B4], edi
0x1800756f7  call    cs:__imp_GetCurrentThreadId
0x1800756fd  mov     ecx, eax
0x1800756ff  mov     [rsp+3E8h+var_398], rcx
0x180075704  lea     rax, [rsp+3E8h+var_398]
0x180075709  mov     [rsp+3E8h+var_3C0], rax
0x18007570e  lea     rax, [rsp+3E8h+var_3A0]
0x180075713  mov     [rsp+3E8h+var_3C8], rax
0x180075718  lea     r9, [rsp+3E8h+var_3A8]
0x18007571d  lea     r8, [rsp+3E8h+var_3B4]
0x180075722  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180075729  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18007572e  lea     rdx, [rsp+3E8h+var_3A8]
0x180075733  lea     rcx, [rsp+3E8h+var_360]
0x18007573b  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180075740  mov     r9, rax
0x180075743  mov     ecx, edi
0x180075745  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18007574a  mov     r8, rax
0x18007574d  mov     edx, edi
0x18007574f  lea     rcx, [rsp+3E8h+pExceptionObject]
0x180075757  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18007575c  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180075763  lea     rcx, [rsp+3E8h+pExceptionObject]; pExceptionObject
0x18007576b  call    _CxxThrowException_0
0x180075771  mov     [rsp+3E8h+var_3B8], 0
0x180075776  lea     r8, [rsp+3E8h+var_3B8]
0x18007577b  mov     rdx, [rsp+3E8h+var_380]
0x180075780  lea     rcx, [rsp+3E8h+var_390]
0x180075785  call    ?GetEffectiveAppId@shared@@YA?AV?$shared_ptr@VICDPCrossPlatformAppId@@@std@@PEAVICDPCrossPlatformAppId@@PEA_N@Z; shared::GetEffectiveAppId(ICDPCrossPlatformAppId *,bool *)
0x18007578a  nop
0x18007578b  cmp     [rsp+3E8h+var_3B8], 0
0x180075790  jz      loc_18007583F
0x180075796  mov     rcx, [rsp+3E8h+var_390]
0x18007579b  call    IsValidCrossPlatformAppId_0
0x1800757a0  test    al, al
0x1800757a2  jnz     loc_18007583F
0x1800757a8  lea     rax, aActivitystoreC; "..\\activitystore.cpp"
0x1800757af  mov     [rsp+3E8h+var_3A8], rax
0x1800757b4  mov     dword ptr [rsp+3E8h+var_3A0], 0D7h
0x1800757bc  mov     ebx, 80070005h
0x1800757c1  mov     [rsp+3E8h+var_3B4], ebx
0x1800757c5  call    cs:__imp_GetCurrentThreadId
0x1800757cb  mov     eax, eax
0x1800757cd  mov     [rsp+3E8h+var_398], rax
0x1800757d2  lea     rax, [rsp+3E8h+var_398]
0x1800757d7  mov     [rsp+3E8h+var_3C0], rax
0x1800757dc  lea     rax, [rsp+3E8h+var_3A0]
0x1800757e1  mov     [rsp+3E8h+var_3C8], rax
0x1800757e6  lea     r9, [rsp+3E8h+var_3A8]
0x1800757eb  lea     r8, [rsp+3E8h+var_3B4]
0x1800757f0  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800757f7  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800757fc  lea     rdx, [rsp+3E8h+var_3A8]
0x180075801  lea     rcx, [rsp+3E8h+var_360]
0x180075809  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18007580e  mov     r9, rax
0x180075811  mov     ecx, ebx
0x180075813  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180075818  mov     r8, rax
0x18007581b  mov     edx, ebx
0x18007581d  lea     rcx, [rsp+3E8h+var_310]
0x180075825  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18007582a  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180075831  lea     rcx, [rsp+3E8h+var_310]; pExceptionObject
0x180075839  call    _CxxThrowException_0
0x18007583f  mov     rax, [rsi]
0x180075842  mov     rdx, [rsp+3E8h+var_390]
0x180075847  mov     rcx, rsi
0x18007584a  mov     rax, [rax+0D8h]
0x180075851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075856  mov     edi, eax
0x180075858  test    eax, eax
0x18007585a  jns     loc_1800758F2
0x180075860  lea     rax, aActivitystoreC; "..\\activitystore.cpp"
0x180075867  mov     [rsp+3E8h+var_3A8], rax
0x18007586c  mov     dword ptr [rsp+3E8h+var_3A0], 0D8h
0x180075874  mov     [rsp+3E8h+var_3B4], edi
0x180075878  call    cs:__imp_GetCurrentThreadId
0x18007587e  mov     ecx, eax
0x180075880  mov     [rsp+3E8h+var_398], rcx
0x180075885  lea     rax, [rsp+3E8h+var_398]
0x18007588a  mov     [rsp+3E8h+var_3C0], rax
0x18007588f  lea     rax, [rsp+3E8h+var_3A0]
0x180075894  mov     [rsp+3E8h+var_3C8], rax
0x180075899  lea     r9, [rsp+3E8h+var_3A8]
0x18007589e  lea     r8, [rsp+3E8h+var_3B4]
0x1800758a3  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x1800758aa  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x1800758af  lea     rdx, [rsp+3E8h+var_3A8]
0x1800758b4  lea     rcx, [rsp+3E8h+var_360]
0x1800758bc  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x1800758c1  mov     r9, rax
0x1800758c4  mov     ecx, edi
0x1800758c6  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x1800758cb  mov     r8, rax
0x1800758ce  mov     edx, edi
0x1800758d0  lea     rcx, [rsp+3E8h+var_2D8]
0x1800758d8  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x1800758dd  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x1800758e4  lea     rcx, [rsp+3E8h+var_2D8]; pExceptionObject
0x1800758ec  call    _CxxThrowException_0
0x1800758f2  mov     rdx, rsi
0x1800758f5  lea     rcx, [rsp+3E8h+var_370]
0x1800758fa  call    ??$query_interface@VICDPInternalActivityBase@cdp@@VICDPActivity@@@cdp@@YA?AV?$shared_ptr@VICDPInternalActivityBase@cdp@@@std@@PEAVICDPActivity@@@Z; cdp::query_interface<cdp::ICDPInternalActivityBase,ICDPActivity>(ICDPActivity *)
0x1800758ff  nop
0x180075900  mov     rcx, [rsp+3E8h+var_370]
0x180075905  test    rcx, rcx
0x180075908  jnz     short loc_180075946
0x18007590a  lea     rax, aActivitystoreC; "..\\activitystore.cpp"
0x180075911  mov     [rsp+3E8h+var_3A8], rax
0x180075916  mov     dword ptr [rsp+3E8h+var_3A0], 0DBh
0x18007591e  lea     r8, aActivitystoreM; "ActivityStore missing required interfac"...
0x180075925  lea     rdx, [rsp+3E8h+var_3A8]
0x18007592a  lea     rcx, [rsp+3E8h+var_2A0]
0x180075932  call    ??$MakeException@V?$HResultException@$0?HPPPLPPO@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPPLPPO@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147467262>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180075937  nop
0x180075938  mov     rdx, rax
0x18007593b  lea     rcx, [rsp+3E8h+var_3A8]
0x180075940  call    ??$CdpThrow@V?$HResultException@$0?HPPPLPPO@@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAV?$HResultException@$0?HPPPLPPO@@0@@Z; cdp::CdpThrow<cdp::HResultException<-2147467262>>(cdp::CDPSourceLocationInfo const &,cdp::HResultException<-2147467262> &&)
0x180075946  mov     rax, [rcx]
0x180075949  mov     rax, [rax+18h]
0x18007594d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075952  mov     rdx, rax; struct shared::ActivityData *
0x180075955  lea     rcx, [rsp+3E8h+var_248]; this
0x18007595d  call    ??0ActivityData@shared@@QEAA@AEBU01@@Z; shared::ActivityData::ActivityData(shared::ActivityData const &)
0x180075962  nop
0x180075963  mov     rcx, [r14+20h]
0x180075967  mov     rax, [rcx]
0x18007596a  lea     r9, [rsp+3E8h+var_268]
0x180075972  cmp     [rsp+3E8h+var_250], 0Fh
0x18007597b  cmova   r9, [rsp+3E8h+var_268]
0x180075984  mov     r8, r15
0x180075987  lea     rdx, [rsp+3E8h+var_248]
0x18007598f  mov     rax, [rax+20h]
0x180075993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075998  nop
0x180075999  lea     rcx, [rsp+3E8h+var_248]; this
0x1800759a1  call    ??1ActivityData@shared@@QEAA@XZ; shared::ActivityData::~ActivityData(void)
0x1800759a6  nop
0x1800759a7  mov     rcx, [rsp+3E8h+var_368]; this
0x1800759af  test    rcx, rcx
0x1800759b2  jz      short loc_1800759BA
0x1800759b4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800759b9  nop
0x1800759ba  mov     rcx, [rsp+3E8h+var_388]; this
0x1800759bf  test    rcx, rcx
0x1800759c2  jz      short loc_1800759CA
0x1800759c4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800759c9  nop
0x1800759ca  mov     rcx, [rsp+3E8h+var_380+8]; this
0x1800759cf  test    rcx, rcx
0x1800759d2  jz      short loc_1800759DA
0x1800759d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800759d9  nop
0x1800759da  jmp     short loc_1800759E0
0x1800759dc  mov     ebx, [rsp+3E8h+var_3B0]
0x1800759e0  lea     rcx, [rsp+3E8h+var_268]; void *
0x1800759e8  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800759ed  mov     eax, ebx
0x1800759ef  mov     rcx, [rsp+3E8h+var_38]
0x1800759f7  xor     rcx, rsp; StackCookie
0x1800759fa  call    __security_check_cookie
0x1800759ff  add     rsp, 3C0h
0x180075a06  pop     r15
0x180075a08  pop     r14
0x180075a0a  pop     rdi
0x180075a0b  pop     rsi
0x180075a0c  pop     rbx
0x180075a0d  retn
```
