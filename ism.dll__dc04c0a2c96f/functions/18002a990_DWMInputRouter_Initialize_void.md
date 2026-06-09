# DWMInputRouter::Initialize(void)

- ea: `0x18002a990`
- end: `0x18002c166`
- name: `?Initialize@DWMInputRouter@@IEAAJXZ`
- size: `6102`
- prototype: `__int64 __fastcall(DWMInputRouter *__hidden this)`
- caller_count: `2`
- callee_count: `48`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18002a8a0`
- `0x18019fb5c`

## callees

- `0x18000adec`
- `0x18000bacc`
- `0x18000dcd4`
- `0x180012b74`
- `0x180012ee0`
- `0x180029c28`
- `0x18002a990`
- `0x18002c16c`
- `0x18002c39c`
- `0x180030260`
- `0x18003afb0`
- `0x18005f6a8`
- `0x180069be0`
- `0x18007b2a8`
- `0x18007c198`
- `0x18007ff98`
- `0x180081694`
- `0x180082320`
- `0x1800829f4`
- `0x18008dcac`
- `0x18008dda4`
- `0x18008de98`
- `0x18008df44`
- `0x18008e194`
- `0x1800a23f4`
- `0x1800a4f34`
- `0x1800a63d8`
- `0x1800aa774`
- `0x1800ab0e4`
- `0x1800b1788`
- `0x1800b8b08`
- `0x1800f0acc`
- `0x180166a70`
- `0x180169f58`
- `0x18016bf98`
- `0x18019f200`
- `0x18019f230`
- `0x18019f2f4`
- `0x18019f40c`
- `0x1801a24cc`
- `0x1801a423c`
- `0x1801a654c`
- `0x1801a6ecc`
- `0x1801aa060`
- `0x1801acecc`
- `0x1801ad4a0`
- `0x1801b19a0`
- `0x1801ce010`

## import_xrefs

- `CoreMessaging!CoreUICreate` at `0x18002a9dd`
- `CoreMessaging!CoreUICreate` at `0x18002a9dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c129`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c14a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c129`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c14a`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18002aa12`
- `CoreUIComponents!CoreUIFactoryCreate` at `0x18002aa12`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002c121`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002c142`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002c121`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002c142`

## pseudocode

```c
// Hidden C++ exception states: #wind=78
__int64 __fastcall DWMInputRouter::Initialize(struct ICursorBroker **this)
{
  char *v2; // r12
  int v3; // eax
  _QWORD *v4; // r14
  int v5; // eax
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, HLOCAL, struct ICursorBroker **); // rdi
  int v10; // eax
  __int64 v11; // rdx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HLOCAL, struct ICursorBroker **); // rbx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, struct ICursorBroker **, _QWORD, _QWORD); // rdi
  int v19; // eax
  int v20; // eax
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, struct ICursorBroker **, _QWORD, _QWORD); // rdi
  int v23; // eax
  struct InputSystemServerConnection *BamoServerConnection; // rbx
  __int64 v25; // rsi
  void (__fastcall *v26)(__int64, UIAHitTestServer *); // rdi
  UIAHitTestServer *v27; // rax
  int v28; // eax
  __int64 v29; // r8
  const char *v30; // r9
  struct ISMTestMode *v31; // rax
  char *v32; // rcx
  int v33; // eax
  int v34; // eax
  struct InputSystemServerConnection *v35; // rax
  struct ContextualProcessorManager *v36; // rax
  struct ContextualProcessorManager *v37; // rdi
  struct ICursorBroker *v38; // rdi
  struct ICursorBroker *v39; // rbx
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // r8
  int v43; // eax
  int v44; // eax
  int v45; // eax
  GameInputProcessor *v46; // rbx
  __int64 (__fastcall *v47)(GameInputProcessor *, GUID *, void **); // rdi
  int v48; // eax
  int v49; // eax
  int v50; // eax
  GameInputProcessor *v51; // rbx
  __int64 (__fastcall *v52)(GameInputProcessor *, GUID *, void **); // rdi
  int v53; // eax
  int v54; // eax
  int v55; // eax
  GameInputProcessor *v56; // rbx
  __int64 (__fastcall *v57)(GameInputProcessor *, GUID *, void **); // rdi
  int v58; // eax
  int v59; // eax
  int v60; // eax
  GameInputProcessor *v61; // rdi
  __int64 (__fastcall *v62)(GameInputProcessor *, GUID *, void **); // rbx
  int v63; // eax
  int v64; // eax
  void *v65; // rcx
  int v66; // eax
  GameInputProcessor *v67; // rbx
  __int64 (__fastcall *v68)(GameInputProcessor *, GUID *, void **); // rdi
  int v69; // eax
  int v70; // eax
  int v71; // eax
  GameInputProcessor *v72; // rbx
  __int64 (__fastcall *v73)(GameInputProcessor *, GUID *, void **); // rdi
  int v74; // eax
  int v75; // eax
  int v76; // eax
  GameInputProcessor *v77; // rbx
  __int64 (__fastcall *v78)(GameInputProcessor *, GUID *, void **); // rdi
  int v79; // eax
  int v80; // eax
  char *v81; // rax
  struct ICursorBroker **v82; // rbx
  GameInputProcessor *v83; // rcx
  __int64 (__fastcall *v84)(struct ICursorBroker **, GUID *, void **); // rdi
  int v85; // eax
  int v86; // eax
  int v87; // eax
  GameInputProcessor *v88; // rbx
  __int64 (__fastcall *v89)(GameInputProcessor *, GUID *, void **); // rdi
  int v90; // eax
  int v91; // eax
  __int64 v92; // rdx
  int v93; // eax
  int v94; // eax
  int v95; // eax
  GameInputProcessor *v96; // rbx
  __int64 (__fastcall *v97)(GameInputProcessor *, GUID *, void **); // rdi
  int v98; // eax
  int v99; // eax
  int v100; // eax
  GameInputProcessor *v101; // rbx
  __int64 (__fastcall *v102)(GameInputProcessor *, GUID *, void **); // rdi
  int v103; // eax
  int v104; // eax
  void *v105; // rcx
  GameInputProcessor *v106; // rcx
  __int64 (__fastcall ***v107)(_QWORD, _QWORD, _QWORD); // rsi
  int v108; // eax
  __int64 (__fastcall *v109)(_QWORD, GUID *, void **); // rbx
  int v110; // eax
  int v111; // eax
  int v112; // eax
  GameInputProcessor *v113; // rbx
  __int64 (__fastcall *v114)(GameInputProcessor *, GUID *, void **); // rdi
  int v115; // eax
  int v116; // eax
  int v117; // eax
  GameInputProcessor *v118; // rbx
  int v119; // eax
  int v120; // eax
  int v121; // eax
  GameInputProcessor *v122; // rbx
  __int64 (__fastcall *v123)(GameInputProcessor *, GUID *, void **); // rdi
  int v124; // eax
  int v125; // eax
  int v126; // eax
  GameInputProcessor *v127; // rbx
  __int64 (__fastcall *v128)(GameInputProcessor *, GUID *, void **); // rdi
  int v129; // eax
  int v130; // eax
  int v131; // eax
  GameInputProcessor *v132; // rbx
  __int64 (__fastcall *v133)(GameInputProcessor *, GUID *, void **); // rdi
  int v134; // eax
  int v135; // eax
  int v136; // eax
  GameInputProcessor *v137; // rbx
  __int64 (__fastcall *v138)(GameInputProcessor *, GUID *, void **); // rdi
  int v139; // eax
  int v140; // eax
  int v141; // eax
  GameInputProcessor *v142; // rbx
  __int64 (__fastcall *v143)(GameInputProcessor *, GUID *, void **); // rdi
  int v144; // eax
  int v145; // eax
  int v146; // eax
  GameInputProcessor *v147; // rbx
  __int64 (__fastcall *v148)(GameInputProcessor *, GUID *, void **); // rdi
  int v149; // eax
  int v150; // eax
  void *v151; // rcx
  GameInputProcessor *v152; // rcx
  struct ContextualProcessorManager *v153; // rbx
  struct ICursorBroker *v154; // rcx
  struct ContextualProcessorManager *v155; // rcx
  struct InputSystemServerConnection *v156; // rdi
  __int64 v157; // r14
  void (__fastcall *v158)(__int64, __int64); // rsi
  GameInputProcessor *v159; // rbx
  __int64 v160; // rax
  int v162; // [rsp+20h] [rbp-89h]
  struct ICursorBroker **v163; // [rsp+40h] [rbp-69h] BYREF
  __int64 (__fastcall ***v164)(_QWORD, GUID *, void **); // [rsp+48h] [rbp-61h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-59h] BYREF
  char v166; // [rsp+58h] [rbp-51h]
  HLOCAL v167; // [rsp+60h] [rbp-49h] BYREF
  char v168; // [rsp+68h] [rbp-41h]
  __int64 v169; // [rsp+70h] [rbp-39h]
  char v170; // [rsp+78h] [rbp-31h] BYREF
  _QWORD v171[16]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  unsigned int v173; // [rsp+110h] [rbp+67h] BYREF
  struct ContextualProcessorManager *v174; // [rsp+118h] [rbp+6Fh] BYREF
  void *v175; // [rsp+120h] [rbp+77h] BYREF
  GameInputProcessor *v176; // [rsp+128h] [rbp+7Fh] BYREF

  LODWORD(v174) = 0;
  v167 = 0;
  v168 = 0;
  hMem = 0;
  v166 = 0;
  v173 = 0;
  v169 = 0;
  v2 = (char *)(this + 19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 19);
  v3 = CoreUICreate(v2);
  if ( v3 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v3,
      v162);
  v4 = this + 20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 20);
  v5 = CoreUIFactoryCreate(this + 20);
  if ( v5 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v5,
      v162);
  v7 = InputSecurityDescriptor::QueryDescriptor(&v167, v6, c_wszMessagePortNames);
  if ( v7 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v7,
      v162);
  v8 = *(_QWORD *)v2;
  v9 = *(__int64 (__fastcall **)(__int64, HLOCAL, struct ICursorBroker **))(**(_QWORD **)v2 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 21);
  v10 = v9(v8, v167, this + 21);
  if ( v10 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v10,
      v162);
  v12 = InputSecurityDescriptor::QueryDescriptor(&hMem, v11, c_wszMessagePortNames);
  if ( v12 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xCC,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v12,
      v162);
  v13 = *(_QWORD *)v2;
  v14 = *(__int64 (__fastcall **)(__int64, HLOCAL, struct ICursorBroker **))(**(_QWORD **)v2 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 22);
  v15 = v14(v13, hMem, this + 22);
  if ( v15 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v15,
      v162);
  v16 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned int *))(*(_QWORD *)*v4 + 24LL))(
          *v4,
          &GUID_f61d2579_c998_4734_9f88_0b4bc8bcf062,
          &v173);
  if ( v16 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v16,
      v162);
  v17 = *v4;
  v18 = *(__int64 (__fastcall **)(__int64, struct ICursorBroker **, _QWORD, _QWORD))(*(_QWORD *)*v4 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 39);
  v19 = v18(v17, this + 3, 0, v173);
  if ( v19 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xE0,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v19,
      (int)L"IRemoteViewHitTestApi");
  v20 = (*(__int64 (__fastcall **)(_QWORD, GUID *, unsigned int *))(*(_QWORD *)*v4 + 24LL))(
          *v4,
          &GUID_adcbf490_e8c4_4bfa_8754_f40fc58292fc,
          &v173);
  if ( v20 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xE8,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v20,
      (int)L"IRemoteViewHitTestApi");
  v21 = *v4;
  v22 = *(__int64 (__fastcall **)(__int64, struct ICursorBroker **, _QWORD, _QWORD))(*(_QWORD *)*v4 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 40);
  v23 = v22(v21, this + 4, 0, v173);
  if ( v23 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xF0,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v23,
      (int)L"IRemoteViewHitTestRequestApi");
  BamoServerConnection = ISMStatics::GetBamoServerConnection();
  v25 = *((_QWORD *)BamoServerConnection + 31);
  v26 = *(void (__fastcall **)(__int64, UIAHitTestServer *))(*(_QWORD *)(v25 + 8) + 272LL);
  v174 = (struct ContextualProcessorManager *)operator new(0x40u);
  v27 = UIAHitTestServer::UIAHitTestServer(v174, BamoServerConnection, (struct DWMInputRouter *)this);
  v26(v25 + 8, v27);
  ISMStatics::GetAnimationDataProvider();
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 33);
  v28 = DWMCursorBroker::Create((struct ISystemInputRouter *)this, this + 33);
  if ( v28 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v28,
      (int)L"IRemoteViewHitTestRequestApi");
  v31 = ISMTestMode::s_instance;
  if ( !ISMTestMode::s_instance )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\ismstatics\\system\\ismtestmode.cpp",
      v30);
  if ( !*(_BYTE *)ISMTestMode::s_instance )
  {
    v171[0] = off_1801E4420;
    v171[1] = this;
    v171[7] = v171;
    KernelInputConnection<_MIT_POINTER_INPUT_DOWN_MESSAGE>::Initialize(this + 44, v2, v29, v171);
    v31 = ISMTestMode::s_instance;
  }
  if ( !v31 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\ismstatics\\system\\ismtestmode.cpp",
      v30);
  v32 = (char *)(this + 42);
  if ( *(_BYTE *)v31 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v32);
    v33 = NonBamoInputDeliveryServer::Create(this + 7, L"InputDeliveryTest", 1, this + 42);
    if ( v33 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v33,
        (int)L"IRemoteViewHitTestRequestApi");
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v32);
    v34 = NonBamoInputDeliveryServer::Create(this + 7, L"System\\InputDelivery", 0, this + 42);
    if ( v34 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v34,
        (int)L"IRemoteViewHitTestRequestApi");
  }
  v35 = ISMStatics::GetBamoServerConnection();
  v36 = (struct ContextualProcessorManager *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v35 + 31) + 8LL)
                                                                                + 120LL))(*((_QWORD *)v35 + 31) + 8LL);
  v37 = v36;
  if ( this[43] != v36 )
  {
    v174 = v36;
    Microsoft::WRL::ComPtr<BamoDragSourceClientProxy>::InternalAddRef(&v174);
    v174 = this[43];
    this[43] = v37;
    Microsoft::WRL::ComPtr<DataProviderRegistrarProxy>::InternalRelease(&v174);
  }
  v38 = this[43];
  v39 = this[42];
  if ( *((struct ICursorBroker **)v38 + 31) != v39 )
  {
    if ( v39 )
      (*(void (__fastcall **)(struct ICursorBroker *))(*(_QWORD *)v39 + 8LL))(v39);
    v174 = (struct ContextualProcessorManager *)*((_QWORD *)v38 + 31);
    *((_QWORD *)v38 + 31) = v39;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v174);
  }
  v174 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v174);
  v40 = ContextualProcessorManager::Create(&v174);
  if ( v40 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v40,
      (int)L"IRemoteViewHitTestRequestApi");
  LOBYTE(v42) = 3;
  LOBYTE(v41) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbSh1>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_MTestAbSh1>::GetImpl'::`2'::impl,
    v41,
    v42);
  v175 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
  v43 = Microsoft::WRL::Details::MakeAndInitialize<ShellHandwritingProcessor,IContextualProcessor,>(&v175);
  if ( v43 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x141,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v43,
      (int)L"IRemoteViewHitTestRequestApi");
  v44 = ContextualProcessorManager::RegisterProcessor(v174, v175, 1);
  if ( v44 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v44,
      (int)L"IRemoteViewHitTestRequestApi");
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
  if ( IsEdition(0x3DDA1u) )
  {
    v176 = 0;
    v175 = 0;
    v163 = this;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v45 = Microsoft::WRL::Details::MakeAndInitialize<CursorSuppressionProcessor,CursorSuppressionProcessor,DWMInputRouter *>(
            &v176,
            &v163);
    if ( v45 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x151,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v45,
        (int)L"IRemoteViewHitTestRequestApi");
    v46 = v176;
    v47 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v48 = v47(v46, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v48 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x152,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v48,
        (int)L"IRemoteViewHitTestRequestApi");
    v49 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v49 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x153,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v49,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( IsEdition(0x3DDA1u) )
  {
    v176 = 0;
    v175 = 0;
    v163 = this;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v50 = Microsoft::WRL::Details::MakeAndInitialize<CursorProcessor,CursorProcessor,DWMInputRouter *>(&v176, &v163);
    if ( v50 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v50,
        (int)L"IRemoteViewHitTestRequestApi");
    v51 = v176;
    v52 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v53 = v52(v51, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v53 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v53,
        (int)L"IRemoteViewHitTestRequestApi");
    v54 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v54 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v54,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( IsEdition(0x1C000u) || IsEdition(0x224Au) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v55 = TipToGlassProcessor::Create(&v176);
    if ( v55 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x16C,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v55,
        (int)L"IRemoteViewHitTestRequestApi");
    v56 = v176;
    v57 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v58 = v57(v56, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v58 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x16D,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v58,
        (int)L"IRemoteViewHitTestRequestApi");
    v59 = ContextualProcessorManager::RegisterProcessor(v174, v175, 1);
    if ( v59 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v59,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  v176 = 0;
  v175 = 0;
  v60 = Microsoft::WRL::Details::MakeAndInitialize<DelegatedInkCanvasProcessor,DelegatedInkCanvasProcessor,>(&v176);
  if ( v60 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v60,
      (int)L"IRemoteViewHitTestRequestApi");
  v61 = v176;
  v62 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
  v63 = v62(v61, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
  if ( v63 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v63,
      (int)L"IRemoteViewHitTestRequestApi");
  v64 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
  if ( v64 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x179,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v64,
      (int)L"IRemoteViewHitTestRequestApi");
  v65 = v175;
  if ( v175 )
  {
    v175 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v65 + 16LL))(v65);
  }
  if ( v61 )
    (*(void (__fastcall **)(GameInputProcessor *))(*(_QWORD *)v61 + 16LL))(v61);
  if ( IsEdition(0x1C000u) || IsEdition(0x400u) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v66 = TapProcessor::Create(&v176);
    if ( v66 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v66,
        (int)L"IRemoteViewHitTestRequestApi");
    v67 = v176;
    v68 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v69 = v68(v67, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v69 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v69,
        (int)L"IRemoteViewHitTestRequestApi");
    v70 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v70 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v70,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( IsEdition(0x1C000u) || IsEdition(0x224Au) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v71 = LightDismissProcessor::Create(&v176);
    if ( v71 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x192,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v71,
        (int)L"IRemoteViewHitTestRequestApi");
    v72 = v176;
    v73 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v74 = v73(v72, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v74 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x193,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v74,
        (int)L"IRemoteViewHitTestRequestApi");
    v75 = ContextualProcessorManager::RegisterProcessor(v174, v175, 1);
    if ( v75 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v75,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( IsEdition(0x1C000u) || IsEdition(0x224Au) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v76 = Microsoft::WRL::Details::MakeAndInitialize<ShellGesturesProcessor,ShellGesturesProcessor,>(&v176);
    if ( v76 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1A0,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v76,
        (int)L"IRemoteViewHitTestRequestApi");
    v77 = v176;
    v78 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v79 = v78(v77, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v79 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1A1,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v79,
        (int)L"IRemoteViewHitTestRequestApi");
    v80 = ContextualProcessorManager::RegisterProcessor(v174, v175, 1);
    if ( v80 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1A2,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v80,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( IsEdition(0x1C000u) )
  {
    v163 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<ISystemInputRouterHitTest>::ComPtr<ISystemInputRouterHitTest>(&v164, this);
    v81 = (char *)EdgyProcessor::Create(&v176, &v164);
    v82 = 0;
    if ( &v170 != v81 )
    {
      v82 = *(struct ICursorBroker ***)v81;
      *(_QWORD *)v81 = 0;
    }
    v163 = v82;
    v83 = v176;
    if ( v176 )
    {
      v176 = 0;
      (*(void (__fastcall **)(GameInputProcessor *))(*(_QWORD *)v83 + 16LL))(v83);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v164);
    v84 = *(__int64 (__fastcall **)(struct ICursorBroker **, GUID *, void **))*v82;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v85 = v84(v82, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v85 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1AF,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v85,
        (int)L"IRemoteViewHitTestRequestApi");
    v86 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v86 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v86,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    (*((void (__fastcall **)(struct ICursorBroker **))*v82 + 2))(v82);
  }
  if ( IsEdition(0x1C000u) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v87 = EdgyLegacyProcessor::Create(&v176);
    if ( v87 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1BC,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v87,
        (int)L"IRemoteViewHitTestRequestApi");
    v88 = v176;
    v89 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v90 = v89(v88, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v90 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1BD,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v90,
        (int)L"IRemoteViewHitTestRequestApi");
    v91 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v91 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1BE,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v91,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( IsEdition(0x1C000u) )
  {
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v93 = Microsoft::WRL::Details::MakeAndInitialize<MagnifierProcessor,IContextualProcessor,>(&v175);
    if ( v93 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1C9,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v93,
        (int)L"IRemoteViewHitTestRequestApi");
    v94 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v94 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1CA,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v94,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
  }
  LOBYTE(v92) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_SupportFnKey>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_SupportFnKey>::GetImpl'::`2'::impl,
    v92);
  v176 = 0;
  v175 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  v95 = SystemButtonProcessor::Create(&v176);
  if ( v95 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x1D6,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v95,
      (int)L"IRemoteViewHitTestRequestApi");
  v96 = v176;
  v97 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
  v98 = v97(v96, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
  if ( v98 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v98,
      (int)L"IRemoteViewHitTestRequestApi");
  v99 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
  if ( v99 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v99,
      (int)L"IRemoteViewHitTestRequestApi");
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  v176 = 0;
  v175 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  v100 = InputRedirectionProcessor::Create((struct IInputDeviceInfoStore *)(this + 6), &v176);
  if ( v100 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v100,
      (int)L"IRemoteViewHitTestRequestApi");
  v101 = v176;
  v102 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
  v103 = v102(v101, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
  if ( v103 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v103,
      (int)L"IRemoteViewHitTestRequestApi");
  v104 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
  if ( v104 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x1E5,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v104,
      (int)L"IRemoteViewHitTestRequestApi");
  v105 = v175;
  if ( v175 )
  {
    v175 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v105 + 16LL))(v105);
  }
  v106 = v176;
  if ( v176 )
  {
    v176 = 0;
    (*(void (__fastcall **)(GameInputProcessor *))(*(_QWORD *)v106 + 16LL))(v106);
  }
  v107 = 0;
  v164 = 0;
  if ( IsEdition(0x3DDA1u) )
  {
    v175 = 0;
    v176 = (GameInputProcessor *)this;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v164);
    v108 = Microsoft::WRL::Details::MakeAndInitialize<ActivationProcessor,ActivationProcessor,DWMInputRouter *>(
             &v164,
             &v176);
    if ( v108 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1F2,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v108,
        (int)L"IRemoteViewHitTestRequestApi");
    v107 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v164;
    v109 = **v164;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v110 = v109(v107, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v110 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1F3,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v110,
        (int)L"IRemoteViewHitTestRequestApi");
    v111 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v111 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x1F4,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v111,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
  }
  if ( IsEdition(0x3DDA1u) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v112 = Microsoft::WRL::Details::MakeAndInitialize<HotkeyContextualProcessor,HotkeyContextualProcessor,>(&v176);
    if ( v112 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x200,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v112,
        (int)L"IRemoteViewHitTestRequestApi");
    v113 = v176;
    v114 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v115 = v114(v113, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v115 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x201,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v115,
        (int)L"IRemoteViewHitTestRequestApi");
    v116 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v116 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v116,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( !IsEdition(0x2200u) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<GameInputProcessor>::InternalRelease(&v176);
    v117 = GameInputProcessor::Create((struct IInputDeviceInfoStore *)(this + 6), &v176);
    if ( v117 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x20E,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v117,
        (int)L"IRemoteViewHitTestRequestApi");
    v118 = v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v119 = GameInputProcessor::QueryInterface(v118, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v119 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x20F,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v119,
        (int)L"IRemoteViewHitTestRequestApi");
    v120 = ContextualProcessorManager::RegisterProcessor(v174, v175, 1);
    if ( v120 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x210,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v120,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<GameInputProcessor>::InternalRelease(&v176);
  }
  if ( IsEdition(0x1C000u) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v121 = ResizeProcessor::Create(&v176);
    if ( v121 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x21C,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v121,
        (int)L"IRemoteViewHitTestRequestApi");
    v122 = v176;
    v123 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v124 = v123(v122, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v124 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x21D,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v124,
        (int)L"IRemoteViewHitTestRequestApi");
    v125 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v125 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x21E,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v125,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( IsEdition(0x1C000u) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    Microsoft::WRL::ComPtr<ISystemInputRouterHitTest>::ComPtr<ISystemInputRouterHitTest>(&v163, this);
    v126 = DragNDropProcessor::Create(&v163, &v164, &v176);
    if ( v126 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x22A,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v126,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v163);
    v127 = v176;
    v128 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v129 = v128(v127, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v129 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x22B,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v129,
        (int)L"IRemoteViewHitTestRequestApi");
    v130 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v130 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x22C,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v130,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( IsEdition(0x1C000u) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v131 = InputForwardProcessor::Create(&v176);
    if ( v131 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x238,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v131,
        (int)L"IRemoteViewHitTestRequestApi");
    v132 = v176;
    v133 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v134 = v133(v132, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v134 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x239,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v134,
        (int)L"IRemoteViewHitTestRequestApi");
    v135 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v135 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x23A,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v135,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( IsEdition(0x1C000u) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v136 = ComboButtonProcessor::Create(&v176);
    if ( v136 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v136,
        (int)L"IRemoteViewHitTestRequestApi");
    v137 = v176;
    v138 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v139 = v138(v137, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v139 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x247,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v139,
        (int)L"IRemoteViewHitTestRequestApi");
    v140 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v140 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x248,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v140,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  if ( IsEdition(0x3DDA1u) )
  {
    v176 = 0;
    v175 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
    v141 = RawButtonProcessor::Create(&v176);
    if ( v141 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x254,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v141,
        (int)L"IRemoteViewHitTestRequestApi");
    v142 = v176;
    v143 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    v144 = v143(v142, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
    if ( v144 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x255,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v144,
        (int)L"IRemoteViewHitTestRequestApi");
    v145 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
    if ( v145 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x256,
        (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
        (const char *)(unsigned int)v145,
        (int)L"IRemoteViewHitTestRequestApi");
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  }
  v176 = 0;
  v175 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v176);
  v146 = InputServiceProcessor::Create(&v176);
  if ( v146 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x261,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v146,
      (int)L"IRemoteViewHitTestRequestApi");
  v147 = v176;
  v148 = **(__int64 (__fastcall ***)(GameInputProcessor *, GUID *, void **))v176;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
  v149 = v148(v147, &GUID_7303df7a_7fda_4ca1_b274_a0a033ec3f5b, &v175);
  if ( v149 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x262,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v149,
      (int)L"IRemoteViewHitTestRequestApi");
  v150 = ContextualProcessorManager::RegisterProcessor(v174, v175, 0);
  if ( v150 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0x263,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\systeminputrouters\\dwm\\lib\\dwminputrouter.cpp",
      (const char *)(unsigned int)v150,
      (int)L"IRemoteViewHitTestRequestApi");
  v151 = v175;
  if ( v175 )
  {
    v175 = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v151 + 16LL))(v151);
  }
  v152 = v176;
  if ( v176 )
  {
    v176 = 0;
    (*(void (__fastcall **)(GameInputProcessor *))(*(_QWORD *)v152 + 16LL))(v152);
  }
  v153 = v174;
  if ( this[32] != v174 )
  {
    if ( v174 )
      (*(void (__fastcall **)(struct ContextualProcessorManager *))(*(_QWORD *)v174 + 8LL))(v174);
    v154 = this[32];
    this[32] = v153;
    if ( v154 )
      (*(void (__fastcall **)(struct ICursorBroker *))(*(_QWORD *)v154 + 16LL))(v154);
  }
  if ( v107 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v107)[2])(v107);
  v155 = v174;
  if ( v174 )
  {
    v174 = 0;
    (*(void (__fastcall **)(struct ContextualProcessorManager *))(*(_QWORD *)v155 + 16LL))(v155);
  }
  v156 = ISMStatics::GetBamoServerConnection();
  v157 = *((_QWORD *)v156 + 31);
  v158 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v157 + 8) + 256LL);
  v159 = (GameInputProcessor *)operator new(0x40u);
  v176 = v159;
  v175 = this;
  wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(&v175);
  LODWORD(v174) = 1;
  v160 = TestCommands::TestCommands(v159, v156, &v175);
  v158(v157 + 8, v160);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v175);
  *((_QWORD *)ISMStatics::GetForegroundManager() + 2) = this + 2;
  if ( hMem )
  {
    if ( v166 )
      FreeTransientObjectSecurityDescriptor();
    else
      LocalFree(hMem);
    hMem = 0;
  }
  if ( v167 )
  {
    if ( v168 )
      FreeTransientObjectSecurityDescriptor();
    else
      LocalFree(v167);
  }
  return 0;
}

```

## disassembly

```asm
0x18002a990  push    rbp
0x18002a992  push    rbx
0x18002a993  push    rsi
0x18002a994  push    rdi
0x18002a995  push    r12
0x18002a997  push    r13
0x18002a999  push    r14
0x18002a99b  push    r15
0x18002a99d  lea     rbp, [rsp-1Fh]
0x18002a9a2  sub     rsp, 0C8h
0x18002a9a9  mov     r15, rcx
0x18002a9ac  xor     r13d, r13d
0x18002a9af  mov     dword ptr [rbp+57h+arg_8], r13d
0x18002a9b3  mov     [rbp+57h+var_A0], r13
0x18002a9b7  mov     [rbp+57h+var_98], r13b
0x18002a9bb  mov     [rbp+57h+hMem], r13
0x18002a9bf  mov     [rbp+57h+var_A8], r13b
0x18002a9c3  mov     [rbp+57h+arg_0], r13d
0x18002a9c7  mov     [rbp+57h+var_90], r13
0x18002a9cb  lea     r12, [rcx+98h]
0x18002a9d2  mov     rcx, r12
0x18002a9d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002a9da  mov     rcx, r12
0x18002a9dd  call    cs:__imp_CoreUICreate
0x18002a9e3  mov     rcx, [rbp+5Fh]; this
0x18002a9e7  test    eax, eax
0x18002a9e9  jns     short loc_18002AA00
0x18002a9eb  mov     r9d, eax; char *
0x18002a9ee  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002a9f5  mov     edx, 0B2h; void *
0x18002a9fa  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002aa00  lea     r14, [r15+0A0h]
0x18002aa07  mov     rcx, r14
0x18002aa0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002aa0f  mov     rcx, r14
0x18002aa12  call    cs:__imp_CoreUIFactoryCreate
0x18002aa18  mov     rcx, [rbp+5Fh]; this
0x18002aa1c  test    eax, eax
0x18002aa1e  jns     short loc_18002AA35
0x18002aa20  mov     r9d, eax; char *
0x18002aa23  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002aa2a  mov     edx, 0B8h; void *
0x18002aa2f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002aa35  mov     r8, cs:?c_wszMessagePortNames@@3QBQEBGB; ushort const * const near * const c_wszMessagePortNames
0x18002aa3c  lea     rcx, [rbp+57h+var_A0]
0x18002aa40  call    ?QueryDescriptor@InputSecurityDescriptor@@QEAAJW4TransientObject_Type@@PEBG@Z; InputSecurityDescriptor::QueryDescriptor(TransientObject_Type,ushort const *)
0x18002aa45  mov     rcx, [rbp+5Fh]; this
0x18002aa49  test    eax, eax
0x18002aa4b  jns     short loc_18002AA62
0x18002aa4d  mov     r9d, eax; char *
0x18002aa50  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002aa57  mov     edx, 0BFh; void *
0x18002aa5c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002aa62  mov     rsi, [r12]
0x18002aa66  mov     rax, [rsi]
0x18002aa69  mov     rdi, [rax+40h]
0x18002aa6d  lea     rbx, [r15+0A8h]
0x18002aa74  mov     rcx, rbx
0x18002aa77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002aa7c  mov     r8, rbx
0x18002aa7f  mov     rdx, [rbp+57h+var_A0]
0x18002aa83  mov     rcx, rsi
0x18002aa86  mov     rax, rdi
0x18002aa89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa8e  mov     rcx, [rbp+5Fh]; this
0x18002aa92  test    eax, eax
0x18002aa94  jns     short loc_18002AAAB
0x18002aa96  mov     r9d, eax; char *
0x18002aa99  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002aaa0  mov     edx, 0C3h; void *
0x18002aaa5  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002aaab  mov     r8, cs:?c_wszMessagePortNames@@3QBQEBGB; ushort const * const near * const c_wszMessagePortNames
0x18002aab2  lea     rcx, [rbp+57h+hMem]
0x18002aab6  call    ?QueryDescriptor@InputSecurityDescriptor@@QEAAJW4TransientObject_Type@@PEBG@Z; InputSecurityDescriptor::QueryDescriptor(TransientObject_Type,ushort const *)
0x18002aabb  mov     rcx, [rbp+5Fh]; this
0x18002aabf  test    eax, eax
0x18002aac1  jns     short loc_18002AAD8
0x18002aac3  mov     r9d, eax; char *
0x18002aac6  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002aacd  mov     edx, 0CCh; void *
0x18002aad2  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002aad8  mov     rdi, [r12]
0x18002aadc  mov     rax, [rdi]
0x18002aadf  mov     rbx, [rax+40h]
0x18002aae3  lea     r13, [r15+0B0h]
0x18002aaea  mov     rcx, r13
0x18002aaed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002aaf2  mov     r8, r13
0x18002aaf5  mov     rdx, [rbp+57h+hMem]
0x18002aaf9  mov     rcx, rdi
0x18002aafc  mov     rax, rbx
0x18002aaff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab04  mov     rcx, [rbp+5Fh]; this
0x18002ab08  test    eax, eax
0x18002ab0a  jns     short loc_18002AB21
0x18002ab0c  mov     r9d, eax; char *
0x18002ab0f  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002ab16  mov     edx, 0D0h; void *
0x18002ab1b  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002ab21  mov     rcx, [r14]
0x18002ab24  mov     rax, [rcx]
0x18002ab27  lea     r8, [rbp+57h+arg_0]
0x18002ab2b  lea     rdx, _GUID_f61d2579_c998_4734_9f88_0b4bc8bcf062
0x18002ab32  mov     rax, [rax+18h]
0x18002ab36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab3b  mov     rcx, [rbp+5Fh]; this
0x18002ab3f  test    eax, eax
0x18002ab41  jns     short loc_18002AB58
0x18002ab43  mov     r9d, eax; char *
0x18002ab46  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002ab4d  mov     edx, 0D8h; void *
0x18002ab52  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002ab58  mov     rsi, [r14]
0x18002ab5b  mov     rax, [rsi]
0x18002ab5e  mov     rdi, [rax+20h]
0x18002ab62  lea     rbx, [r15+138h]
0x18002ab69  mov     rcx, rbx
0x18002ab6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ab71  lea     rdx, [r15+18h]
0x18002ab75  mov     [rsp+100h+var_D0], rbx
0x18002ab7a  mov     r8, [r13+0]
0x18002ab7e  mov     [rsp+100h+var_D8], r8
0x18002ab83  lea     rax, aIremoteviewhit_0; "IRemoteViewHitTestApi"
0x18002ab8a  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18002ab8f  mov     r9d, [rbp+57h+arg_0]
0x18002ab93  xor     r8d, r8d
0x18002ab96  mov     rcx, rsi
0x18002ab99  mov     rax, rdi
0x18002ab9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aba1  mov     rcx, [rbp+5Fh]; this
0x18002aba5  test    eax, eax
0x18002aba7  jns     short loc_18002ABBE
0x18002aba9  mov     r9d, eax; char *
0x18002abac  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002abb3  mov     edx, 0E0h; void *
0x18002abb8  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002abbe  mov     rcx, [r14]
0x18002abc1  mov     rax, [rcx]
0x18002abc4  lea     r8, [rbp+57h+arg_0]
0x18002abc8  lea     rdx, _GUID_adcbf490_e8c4_4bfa_8754_f40fc58292fc
0x18002abcf  mov     rax, [rax+18h]
0x18002abd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abd8  mov     rcx, [rbp+5Fh]; this
0x18002abdc  test    eax, eax
0x18002abde  jns     short loc_18002ABF5
0x18002abe0  mov     r9d, eax; char *
0x18002abe3  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002abea  mov     edx, 0E8h; void *
0x18002abef  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002abf5  mov     rsi, [r14]
0x18002abf8  mov     rax, [rsi]
0x18002abfb  mov     rdi, [rax+20h]
0x18002abff  lea     rbx, [r15+140h]
0x18002ac06  mov     rcx, rbx
0x18002ac09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ac0e  lea     rdx, [r15+20h]
0x18002ac12  mov     [rsp+100h+var_D0], rbx
0x18002ac17  mov     r8, [r13+0]
0x18002ac1b  mov     [rsp+100h+var_D8], r8
0x18002ac20  lea     rax, aIremoteviewhit; "IRemoteViewHitTestRequestApi"
0x18002ac27  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18002ac2c  mov     r9d, [rbp+57h+arg_0]
0x18002ac30  xor     r8d, r8d
0x18002ac33  mov     rcx, rsi
0x18002ac36  mov     rax, rdi
0x18002ac39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac3e  mov     rcx, [rbp+5Fh]; this
0x18002ac42  xor     r13d, r13d
0x18002ac45  test    eax, eax
0x18002ac47  jns     short loc_18002AC5E
0x18002ac49  mov     r9d, eax; char *
0x18002ac4c  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002ac53  mov     edx, 0F0h; void *
0x18002ac58  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002ac5e  call    ?GetBamoServerConnection@ISMStatics@@SAPEAVInputSystemServerConnection@@XZ; ISMStatics::GetBamoServerConnection(void)
0x18002ac63  mov     rbx, rax
0x18002ac66  mov     rsi, [rax+0F8h]
0x18002ac6d  mov     rcx, [rsi+8]
0x18002ac71  mov     rdi, [rcx+110h]
0x18002ac78  mov     ecx, 40h ; '@'; Size
0x18002ac7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002ac82  mov     [rbp+57h+arg_8], rax
0x18002ac86  mov     r8, r15; struct DWMInputRouter *
0x18002ac89  mov     rdx, rbx; struct ISMBamos_AutoBamos::BamoConnection *
0x18002ac8c  mov     rcx, rax; this
0x18002ac8f  call    ??0UIAHitTestServer@@QEAA@PEAVBamoConnection@ISMBamos_AutoBamos@@PEAVDWMInputRouter@@@Z; UIAHitTestServer::UIAHitTestServer(ISMBamos_AutoBamos::BamoConnection *,DWMInputRouter *)
0x18002ac94  nop
0x18002ac95  mov     rdx, rax
0x18002ac98  lea     rcx, [rsi+8]
0x18002ac9c  mov     rax, rdi
0x18002ac9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aca4  call    ?GetAnimationDataProvider@ISMStatics@@SAPEAUIAnimationDataProvider@@XZ; ISMStatics::GetAnimationDataProvider(void)
0x18002aca9  lea     rbx, [r15+108h]
0x18002acb0  mov     rcx, rbx
0x18002acb3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002acb8  mov     rdx, rbx; struct ICursorBroker **
0x18002acbb  mov     rcx, r15; struct ISystemInputRouter *
0x18002acbe  call    ?Create@DWMCursorBroker@@SAJPEAUISystemInputRouter@@PEAPEAUICursorBroker@@@Z; DWMCursorBroker::Create(ISystemInputRouter *,ICursorBroker * *)
0x18002acc3  mov     rcx, [rbp+5Fh]; this
0x18002acc7  test    eax, eax
0x18002acc9  jns     short loc_18002ACE0
0x18002accb  mov     r9d, eax; char *
0x18002acce  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002acd5  mov     edx, 103h; void *
0x18002acda  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002ace0  mov     rcx, [rbp+5Fh]; this
0x18002ace4  mov     rax, cs:?s_instance@ISMTestMode@@0PEAV1@EA; ISMTestMode * ISMTestMode::s_instance
0x18002aceb  test    rax, rax
0x18002acee  jnz     short loc_18002AD00
0x18002acf0  lea     r8, aOnecoreuapWind_223; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002acf7  lea     edx, [rax+21h]; void *
0x18002acfa  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002ad00  cmp     [rax], r13b
0x18002ad03  jnz     short loc_18002AD36
0x18002ad05  lea     rax, off_1801E4420
0x18002ad0c  mov     [rbp+57h+var_80], rax
0x18002ad10  mov     [rbp+57h+var_78], r15
0x18002ad14  lea     rax, [rbp+57h+var_80]
0x18002ad18  mov     [rbp+57h+var_48], rax
0x18002ad1c  lea     rcx, [r15+160h]
0x18002ad23  lea     r9, [rbp+57h+var_80]
0x18002ad27  mov     rdx, r12
0x18002ad2a  call    ?Initialize@?$KernelInputConnection@U_MIT_POINTER_INPUT_DOWN_MESSAGE@@@@QEAAXAEBV?$ComPtr@UIMessageSession@@@WRL@Microsoft@@W4_MIT_ENDPOINT@@V?$function@$$A6AXPEBU_MIT_POINTER_INPUT_DOWN_MESSAGE@@@Z@std@@@Z; KernelInputConnection<_MIT_POINTER_INPUT_DOWN_MESSAGE>::Initialize(Microsoft::WRL::ComPtr<IMessageSession> const &,_MIT_ENDPOINT,std::function<void (_MIT_POINTER_INPUT_DOWN_MESSAGE const *)>)
0x18002ad2f  mov     rax, cs:?s_instance@ISMTestMode@@0PEAV1@EA; ISMTestMode * ISMTestMode::s_instance
0x18002ad36  mov     rcx, [rbp+5Fh]; this
0x18002ad3a  test    rax, rax
0x18002ad3d  jnz     short loc_18002AD4F
0x18002ad3f  lea     r8, aOnecoreuapWind_223; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002ad46  lea     edx, [rax+21h]; void *
0x18002ad49  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002ad4f  lea     rbx, [r15+150h]
0x18002ad56  mov     esi, 1
0x18002ad5b  mov     rcx, rbx
0x18002ad5e  cmp     [rax], r13b
0x18002ad61  jz      short loc_18002AD9B
0x18002ad63  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ad68  mov     r9, rbx
0x18002ad6b  mov     r8d, esi
0x18002ad6e  lea     rdx, aInputdeliveryt; "InputDeliveryTest"
0x18002ad75  lea     rcx, [r15+38h]
0x18002ad79  call    ?Create@NonBamoInputDeliveryServer@@SAJPEAUIInputDeliveryServerHost@@PEBGW4TestMode@1@PEAPEAUIInputDeliveryServer@@@Z; NonBamoInputDeliveryServer::Create(IInputDeliveryServerHost *,ushort const *,NonBamoInputDeliveryServer::TestMode,IInputDeliveryServer * *)
0x18002ad7e  mov     rcx, [rbp+5Fh]; this
0x18002ad82  test    eax, eax
0x18002ad84  jns     short loc_18002ADD3
0x18002ad86  mov     r9d, eax; char *
0x18002ad89  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002ad90  mov     edx, 11Eh; void *
0x18002ad95  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002ad9b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ada0  mov     r9, rbx
0x18002ada3  xor     r8d, r8d
0x18002ada6  lea     rdx, aSystemInputdel; "System\\InputDelivery"
0x18002adad  lea     rcx, [r15+38h]
0x18002adb1  call    ?Create@NonBamoInputDeliveryServer@@SAJPEAUIInputDeliveryServerHost@@PEBGW4TestMode@1@PEAPEAUIInputDeliveryServer@@@Z; NonBamoInputDeliveryServer::Create(IInputDeliveryServerHost *,ushort const *,NonBamoInputDeliveryServer::TestMode,IInputDeliveryServer * *)
0x18002adb6  mov     rcx, [rbp+5Fh]; this
0x18002adba  test    eax, eax
0x18002adbc  jns     short loc_18002ADD3
0x18002adbe  mov     r9d, eax; char *
0x18002adc1  lea     r8, aOnecoreuapWind_63; "onecoreuap\\windows\\moderncore\\inputv"...
0x18002adc8  mov     edx, 124h; void *
0x18002adcd  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18002add3  call    ?GetBamoServerConnection@ISMStatics@@SAPEAVInputSystemServerConnection@@XZ; ISMStatics::GetBamoServerConnection(void)
0x18002add8  mov     rcx, [rax+0F8h]
0x18002addf  add     rcx, 8
0x18002ade3  mov     rax, [rcx]
0x18002ade6  mov     rax, [rax+78h]
0x18002adea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002adef  mov     rdi, rax
0x18002adf2  cmp     [r15+158h], rax
0x18002adf9  jz      short loc_18002AE23
0x18002adfb  mov     [rbp+57h+arg_8], rax
0x18002adff  lea     rcx, [rbp+57h+arg_8]
0x18002ae03  call    ?InternalAddRef@?$ComPtr@VBamoDragSourceClientProxy@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<BamoDragSourceClientProxy>::InternalAddRef(void)
0x18002ae08  mov     rcx, [r15+158h]
0x18002ae0f  mov     [rbp+57h+arg_8], rcx
0x18002ae13  mov     [r15+158h], rdi
0x18002ae1a  lea     rcx, [rbp+57h+arg_8]
0x18002ae1e  call    ?InternalRelease@?$ComPtr@VDataProviderRegistrarProxy@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<DataProviderRegistrarProxy>::InternalRelease(void)
0x18002ae23  mov     rdi, [r15+158h]
0x18002ae2a  mov     rbx, [rbx]
0x18002ae2d  cmp     [rdi+0F8h], rbx
0x18002ae34  jz      short loc_18002AE66
0x18002ae36  test    rbx, rbx
0x18002ae39  jz      short loc_18002AE4B
0x18002ae3b  mov     rax, [rbx]
0x18002ae3e  mov     rcx, rbx
0x18002ae41  mov     rax, [rax+8]
0x18002ae45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ae4a  nop
0x18002ae4b  mov     rax, [rdi+0F8h]
0x18002ae52  mov     [rbp+57h+arg_8], rax
0x18002ae56  mov     [rdi+0F8h], rbx
0x18002ae5d  lea     rcx, [rbp+57h+arg_8]
0x18002ae61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ae66  mov     [rbp+57h+arg_8], r13
0x18002ae6a  lea     rcx, [rbp+57h+arg_8]
0x18002ae6e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ae73  lea     rcx, [rbp+57h+arg_8]; struct ContextualProcessorManager **
0x18002ae77  call    ?Create@ContextualProcessorManager@@SAJPEAPEAV1@@Z; ContextualProcessorManager::Create(ContextualProcessorManager * *)
0x18002ae7c  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
