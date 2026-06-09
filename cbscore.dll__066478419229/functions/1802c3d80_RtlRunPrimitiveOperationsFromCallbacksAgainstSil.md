# RtlRunPrimitiveOperationsFromCallbacksAgainstSil

- ea: `0x1802c3d80`
- end: `0x1802c4bae`
- name: `RtlRunPrimitiveOperationsFromCallbacksAgainstSil`
- size: `3630`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, struct Windows::Rtl::IRtlSystemIsolationLayerPublic *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `39`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180010cc0`
- `0x180019bdc`
- `0x18002ec34`
- `0x180044e7c`
- `0x180045444`
- `0x180048c24`
- `0x180048c80`
- `0x180064c6c`
- `0x1800a26b0`
- `0x1800aa1a4`
- `0x1800aa1d4`
- `0x1800bea58`
- `0x1800c22ec`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800ef360`
- `0x18011a3d8`
- `0x180210b50`
- `0x180212434`
- `0x180232608`
- `0x18027d474`
- `0x1802b95a0`
- `0x1802bce2c`
- `0x1802bcfb8`
- `0x1802bd248`
- `0x1802bd4a8`
- `0x1802bd4d8`
- `0x1802bd5dc`
- `0x1802bd644`
- `0x1802bd6a0`
- `0x1802be4b0`
- `0x1802bed98`
- `0x1802bf654`
- `0x1802c3d80`
- `0x1802c556c`
- `0x1802c56d4`
- `0x1802ccd1c`
- `0x1802cdb0c`
- `0x1802d5010`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x1802c427b`
- `ntdll!NtQuerySystemInformation` at `0x1802c427b`
- `ntdll!NtCreateEvent` at `0x1802c4478`
- `ntdll!NtCreateEvent` at `0x1802c44dc`
- `ntdll!NtCreateEvent` at `0x1802c4478`
- `ntdll!NtCreateEvent` at `0x1802c44dc`
- `ntdll!NtCreateIoCompletion` at `0x1802c43b8`
- `ntdll!NtCreateIoCompletion` at `0x1802c4414`
- `ntdll!NtCreateIoCompletion` at `0x1802c43b8`
- `ntdll!NtCreateIoCompletion` at `0x1802c4414`
- `ntdll!TpSimpleTryPost` at `0x1802c4532`
- `ntdll!TpSimpleTryPost` at `0x1802c4590`
- `ntdll!TpSimpleTryPost` at `0x1802c4532`
- `ntdll!TpSimpleTryPost` at `0x1802c4590`

## string_xrefs

- `0x1802c43ed`: `::NtCreateIoCompletion(CompletionContext.DispatcherPort.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, 0)`
- `0x1802c4449`: `::NtCreateIoCompletion(CompletionContext.WorkerPort.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, 0)`
- `0x1802c4365`: `!GlobalContext.fPendingDeletesBehavior || GlobalContext.fAgainstUnbufferedSil`
- `0x1802c4567`: `::TpSimpleTryPost(DispatcherCallback, &CompletionContext, nullptr)`
- `0x1802c4687`: `::TpSimpleTryPost(WorkerCallback, &CompletionContext, nullptr)`
- `0x1802c44ad`: `::NtCreateEvent(CompletionContext.DispatcherEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, SynchronizationEvent, 0 )`
- `0x1802c4511`: `::NtCreateEvent(CompletionContext.WorkerEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, SynchronizationEvent, 0 )`

## pseudocode

```c
__int64 __fastcall RtlRunPrimitiveOperationsFromCallbacksAgainstSil(
        unsigned int a1,
        struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *a2,
        void (__fastcall *a3)(__int64, _BYTE *, __int128 *, char *),
        __int64 a4,
        __int64 a5,
        __int64 a6,
        struct Windows::Rtl::IRtlSystemIsolationLayerPublic *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10)
{
  __int64 v12; // r12
  __int64 v13; // r9
  unsigned int v14; // eax
  _QWORD *v15; // rdx
  unsigned int v16; // ebx
  __int64 v17; // rax
  int v18; // eax
  Windows::Rtl::SystemImplementation::CSystemIsolationLayer *v19; // rax
  struct Windows::Rtl::IRtlDirectory *v20; // r8
  struct IUpdateReserveManager *v21; // r9
  __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  unsigned __int64 v26; // rdi
  NTSTATUS v27; // eax
  __int64 v28; // r8
  _QWORD *v29; // rdx
  unsigned int v30; // eax
  char v31; // al
  char v32; // cl
  __int64 v33; // rdx
  char v34; // cl
  void **InitPointer; // rax
  NTSTATUS IoCompletion; // eax
  __int64 v37; // rdx
  void **v38; // rax
  NTSTATUS v39; // eax
  void **v40; // rax
  NTSTATUS Event; // eax
  void **v42; // rax
  NTSTATUS v43; // eax
  int v44; // eax
  __int64 v45; // rbx
  int v46; // eax
  __int64 v47; // rdx
  bool v48; // al
  int v49; // eax
  unsigned int v50; // edi
  void (__fastcall *v51)(__int64, _BYTE *, __int128 *, char *); // r13
  char v52; // al
  Windows::Rtl::StopWatch *v53; // rbx
  int v54; // esi
  __int64 v55; // rcx
  char v56; // al
  int v57; // eax
  _QWORD *v58; // rbx
  int v59; // eax
  int v60; // edx
  int v61; // r8d
  unsigned int v63; // r8d
  __int64 v64; // rdx
  unsigned __int64 v65; // [rsp+58h] [rbp-A8h]
  bool v66; // [rsp+60h] [rbp-A0h] BYREF
  void (__fastcall *v67)(__int64, _BYTE *, __int128 *, char *); // [rsp+68h] [rbp-98h]
  __int64 v68; // [rsp+70h] [rbp-90h]
  __int64 v69; // [rsp+78h] [rbp-88h]
  _QWORD v70[4]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v71[4]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v72[4]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v73[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v74[4]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v75[4]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v76[4]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v77[4]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v78[4]; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v79[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v80[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  _QWORD v81[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v82; // [rsp+200h] [rbp+100h] BYREF
  __int128 v83; // [rsp+210h] [rbp+110h] BYREF
  signed __int32 v84; // [rsp+220h] [rbp+120h] BYREF
  unsigned int v85; // [rsp+224h] [rbp+124h]
  unsigned int v86; // [rsp+228h] [rbp+128h]
  int v87; // [rsp+22Ch] [rbp+12Ch]
  char v88; // [rsp+230h] [rbp+130h]
  __int64 v89; // [rsp+238h] [rbp+138h] BYREF
  struct Windows::Rtl::IRtlSystemIsolationLayerPublic *v90; // [rsp+240h] [rbp+140h]
  _OWORD v91[2]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v92; // [rsp+270h] [rbp+170h]
  __int128 *v93; // [rsp+278h] [rbp+178h]
  __int128 v94; // [rsp+280h] [rbp+180h]
  __int128 v95; // [rsp+290h] [rbp+190h]
  int v96; // [rsp+2A0h] [rbp+1A0h]
  int v97; // [rsp+2A4h] [rbp+1A4h]
  __int16 v98; // [rsp+2A8h] [rbp+1A8h]
  _BYTE v99[48]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _QWORD v100[8]; // [rsp+2E0h] [rbp+1E0h] BYREF
  int v101; // [rsp+320h] [rbp+220h]
  int v102; // [rsp+330h] [rbp+230h] BYREF
  char v103[4]; // [rsp+334h] [rbp+234h] BYREF
  __int64 v104; // [rsp+338h] [rbp+238h] BYREF
  __int64 v105; // [rsp+340h] [rbp+240h] BYREF
  __int64 v106; // [rsp+348h] [rbp+248h] BYREF
  __int64 v107; // [rsp+350h] [rbp+250h] BYREF
  __int64 v108; // [rsp+358h] [rbp+258h] BYREF
  char v109[8]; // [rsp+360h] [rbp+260h] BYREF
  __int64 v110; // [rsp+368h] [rbp+268h]
  __int64 v111; // [rsp+370h] [rbp+270h]
  __int64 v112; // [rsp+378h] [rbp+278h]
  __int64 v113; // [rsp+380h] [rbp+280h]
  char v114[8]; // [rsp+388h] [rbp+288h] BYREF
  __int64 v115; // [rsp+390h] [rbp+290h]
  __int64 v116; // [rsp+398h] [rbp+298h]
  __int64 v117; // [rsp+3A0h] [rbp+2A0h]
  __int64 v118; // [rsp+3A8h] [rbp+2A8h]
  char v119[8]; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v120; // [rsp+3B8h] [rbp+2B8h]
  __int64 v121; // [rsp+3C0h] [rbp+2C0h]
  __int64 v122; // [rsp+3C8h] [rbp+2C8h]
  __int64 v123; // [rsp+3D0h] [rbp+2D0h]
  __int128 v124; // [rsp+3D8h] [rbp+2D8h] BYREF
  __int64 v125; // [rsp+3E8h] [rbp+2E8h]
  __int128 v126; // [rsp+3F0h] [rbp+2F0h] BYREF
  int v127; // [rsp+400h] [rbp+300h]
  __int64 v128; // [rsp+408h] [rbp+308h]
  __int64 v129; // [rsp+410h] [rbp+310h]
  __int64 v130; // [rsp+418h] [rbp+318h]
  __int64 v131; // [rsp+420h] [rbp+320h]
  __int64 v132; // [rsp+428h] [rbp+328h]
  __int64 v133; // [rsp+430h] [rbp+330h]
  _BYTE v134[4]; // [rsp+440h] [rbp+340h] BYREF
  int v135; // [rsp+444h] [rbp+344h]
  __int64 v136; // [rsp+490h] [rbp+390h]
  __int64 v137; // [rsp+498h] [rbp+398h]
  __int128 v138; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE SystemInformation[56]; // [rsp+4B0h] [rbp+3B0h] BYREF
  char v140; // [rsp+4E8h] [rbp+3E8h]
  int v141[14]; // [rsp+4F0h] [rbp+3F0h] BYREF
  char v142; // [rsp+528h] [rbp+428h]

  v12 = 0;
  v107 = a10;
  v69 = a6;
  v68 = a4;
  v67 = a3;
  v108 = a8;
  v102 = 0;
  Windows::WCP::Rtl::RtlGetFacilityTracingFlags((Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_POQ, a2);
  v141[10] = 0;
  v142 = 0;
  v141[2] = 1;
  if ( (unsigned __int8)Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::ShouldArm(&Windows::WCP::Rtl::Facility_POQ) )
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::Arm(
      (int)v141,
      0,
      (int)&v102,
      (int)Windows::WCP::Rtl::RtlTraceFormat_PCNTSTATUS,
      0,
      (__int64)"RtlRunPrimitiveOperationsFromCallbacksAgainstSil",
      (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_POQ,
      0,
      0,
      0,
      0,
      v65);
  v103[0] = 0;
  memset(v91, 0, sizeof(v91));
  v94 = 0;
  v95 = 0;
  v92 = 0;
  v93 = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  OperationContext::OperationContext((OperationContext *)v99);
  v88 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v89 = 0;
  v90 = 0;
  if ( a9 )
  {
    *(_OWORD *)a9 = 0;
    *(_OWORD *)(a9 + 16) = 0;
    *(_OWORD *)(a9 + 32) = 0;
  }
  if ( (a1 & 0xFFFFFCC6) != 0 )
  {
    v77[1] = v13;
    v77[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v77[2] = 3986;
    v77[3] = "Valid flags check failed: Flags";
    v14 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v102,
            v77);
LABEL_10:
    v16 = v14;
LABEL_112:
    IoCompletionContext::~IoCompletionContext((IoCompletionContext *)&v82);
    OperationContext::~OperationContext((OperationContext *)v99);
    PoqContext::~PoqContext((PoqContext *)v91);
    Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>(v141);
    return v16;
  }
  if ( !a7 )
  {
    v78[1] = v13;
    v78[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v15 = v78;
    v78[2] = 3988;
    v78[3] = "Not-null check failed: IsoLayer";
LABEL_9:
    v14 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v102,
            v15);
    goto LABEL_10;
  }
  if ( !a3 )
  {
    v79[1] = v13;
    v79[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v15 = v79;
    v79[2] = 3989;
    v79[3] = "Not-null check failed: GetOperationCallback";
    goto LABEL_9;
  }
  v17 = *(_QWORD *)a7;
  v104 = 0;
  v18 = (*(__int64 (__fastcall **)(struct Windows::Rtl::IRtlSystemIsolationLayerPublic *, GUID *, __int64 *))(v17 + 8))(
          a7,
          &GUID_bf537349_9167_47f4_a8a8_df3c233df232,
          &v104);
  v16 = v18;
  if ( v18 < 0 )
    goto LABEL_14;
  v100[7] = v91;
  v92 = a5;
  v19 = (Windows::Rtl::SystemImplementation::CSystemIsolationLayer *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
  LOBYTE(v97) = Windows::Rtl::SystemImplementation::CSystemIsolationLayer::IsUnbufferedSil(v19);
  *(_QWORD *)&v94 = a9;
  *((_QWORD *)&v94 + 1) = a8;
  BYTE1(v97) = a1 & 1;
  HIBYTE(v98) = (a1 & 0x200) != 0;
  v93 = &v82;
  v18 = Windows::Rtl::PendingDeletesHelper::Initialize((Windows::Rtl::PendingDeletesHelper *)v91, a7, v20, v21);
  v16 = v18;
  if ( v18 < 0 )
    goto LABEL_14;
  if ( v100[0] )
    __debugbreak();
  v18 = Windows::Rtl::IRtlObject::CreateRequiredInterface<Windows::Rtl::IRtlSystemIsolationLayer>(a7, v100);
  v16 = v18;
  if ( v18 < 0 )
    goto LABEL_14;
  if ( !HIBYTE(v98) )
  {
    v18 = SafeOpenCreateHelper::TryAddProtectedPath(
            (SafeOpenCreateHelper *)v99,
            (const struct _LUNICODE_STRING *)___LiteralObject__2U__BaseLiteralBuffer__0M_U_LUNICODE_STRING___W_Details_RtlStringLiterals__3_W0FM__0FD__0HJ__0HD__0HE__0GF__0GN__0FC__0GP__0GP__0HE__0A_____0A__00_01_02_03_04_05_06_07_08_09_0L__Details_RtlStringLiterals__3U_LUNICODE_STRING__B);
    v16 = v18;
    if ( v18 < 0 )
    {
LABEL_14:
      v102 = v18;
LABEL_111:
      Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v104);
      goto LABEL_112;
    }
    v22 = *(_QWORD *)a7;
    v105 = 0;
    v23 = (*(__int64 (__fastcall **)(struct Windows::Rtl::IRtlSystemIsolationLayerPublic *, _QWORD, _QWORD, __int64 *, _QWORD))(v22 + 128))(
            a7,
            0,
            0,
            &v105,
            0);
    v16 = v23;
    if ( v23 < 0 )
    {
      v102 = v23;
LABEL_23:
      Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v105);
      goto LABEL_111;
    }
    v125 = 0;
    v124 = 0;
    v24 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int128 *, _QWORD))(*(_QWORD *)v105 + 32LL))(
            v105,
            0,
            0x100000,
            &v124,
            0);
    v16 = v24;
    if ( v24 < 0 )
    {
      v102 = v24;
LABEL_26:
      Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v124);
      goto LABEL_23;
    }
    if ( (*(unsigned __int8 (__fastcall **)(struct Windows::Rtl::IRtlSystemIsolationLayerPublic *, __int128 *, __int64))(*(_QWORD *)a7 + 176LL))(
           a7,
           &v124,
           0x80000000LL) )
    {
      v106 = 0;
      v25 = SafeOpenCreateHelper::SafeOpenDirectory((SafeOpenCreateHelper *)v99, 0);
      v16 = v25;
      if ( v25 < 0 )
      {
        v102 = v25;
        Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v106);
        goto LABEL_26;
      }
      Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v106);
    }
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v124);
    Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v105);
  }
  if ( (a1 & 0x100) != 0 )
  {
    HIWORD(v97) = 257;
    LOBYTE(v98) = 1;
  }
  v26 = 0;
  if ( (_BYTE)v97 )
  {
    memset_0(SystemInformation, 0, 0x40u);
    v27 = NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
    v28 = (unsigned int)v27;
    if ( v27 < 0 )
    {
      v80[2] = 4043;
      v80[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v80;
      v80[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v80[3] = "NtQuerySystemInformation(SystemBasicInformation, &SystemInformation, sizeof(SystemInformation), nullptr)";
LABEL_37:
      v30 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v102,
              v29,
              v28);
LABEL_38:
      v16 = v30;
      goto LABEL_111;
    }
    v31 = v140;
    if ( v140 >= 2 )
    {
      v32 = 10;
      if ( v140 > 10 )
      {
LABEL_43:
        v26 = v32;
        goto LABEL_44;
      }
    }
    else
    {
      v31 = 2;
    }
    v32 = v31;
    goto LABEL_43;
  }
LABEL_44:
  v18 = (*(__int64 (__fastcall **)(struct Windows::Rtl::IRtlSystemIsolationLayerPublic *, __int64 *))(*(_QWORD *)a7 + 104LL))(
          a7,
          &v89);
  v16 = v18;
  if ( v18 < 0 )
    goto LABEL_14;
  v90 = a7;
  if ( BYTE1(v97) && !(_BYTE)v97 )
  {
    v81[2] = 4057;
    v81[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v81[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
    v81[3] = "!GlobalContext.fPendingDeletesBehavior || GlobalContext.fAgainstUnbufferedSil";
    v30 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
            &v102,
            v81);
    goto LABEL_38;
  }
  v34 = v88;
  if ( (a1 & 0x18) != 0 )
    v34 = 0;
  v88 = v34;
  if ( v34 )
  {
    InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                             &v82,
                             v33);
    IoCompletion = NtCreateIoCompletion(InitPointer, 0x1F0003u, 0, 0);
    v28 = (unsigned int)IoCompletion;
    if ( IoCompletion < 0 )
    {
      v70[2] = 4067;
      v70[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v70;
      v70[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v70[3] = "::NtCreateIoCompletion(CompletionContext.DispatcherPort.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, 0)";
      goto LABEL_37;
    }
    v38 = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                     (char *)&v82 + 8,
                     v37);
    v39 = NtCreateIoCompletion(v38, 0x1F0003u, 0, 0);
    v28 = (unsigned int)v39;
    if ( v39 < 0 )
    {
      v76[2] = 4068;
      v76[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v76;
      v76[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v76[3] = "::NtCreateIoCompletion(CompletionContext.WorkerPort.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullptr, 0)";
      goto LABEL_37;
    }
    v40 = (void **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v83);
    Event = NtCreateEvent(v40, 0x1F0003u, 0, SynchronizationEvent, 0);
    v28 = (unsigned int)Event;
    if ( Event < 0 )
    {
      v75[2] = 4070;
      v75[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v75;
      v75[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v75[3] = "::NtCreateEvent(CompletionContext.DispatcherEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nu"
               "llptr, SynchronizationEvent, 0 )";
      goto LABEL_37;
    }
    v42 = (void **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer((char *)&v83 + 8);
    v43 = NtCreateEvent(v42, 0x1F0003u, 0, SynchronizationEvent, 0);
    v28 = (unsigned int)v43;
    if ( v43 < 0 )
    {
      v74[2] = 4071;
      v74[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v74;
      v74[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v74[3] = "::NtCreateEvent(CompletionContext.WorkerEvent.GetInitPointer(), ((0x000F0000L)|(0x00100000L)|0x3), nullpt"
               "r, SynchronizationEvent, 0 )";
      goto LABEL_37;
    }
    v44 = TpSimpleTryPost(DispatcherCallback_0, &v82, 0);
    v28 = (unsigned int)v44;
    if ( v44 < 0 )
    {
      v73[2] = 4073;
      v73[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v73;
      v73[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v73[3] = "::TpSimpleTryPost(DispatcherCallback, &CompletionContext, nullptr)";
      goto LABEL_37;
    }
    v45 = 0;
    if ( v26 )
    {
      while ( 1 )
      {
        v46 = TpSimpleTryPost(WorkerCallback_0, &v82, 0);
        v28 = (unsigned int)v46;
        if ( v46 < 0 )
          break;
        _InterlockedIncrement(&v84);
        if ( ++v45 >= v26 )
          goto LABEL_64;
      }
      v72[2] = 4078;
      v72[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
      v29 = v72;
      v72[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
      v72[3] = "::TpSimpleTryPost(WorkerCallback, &CompletionContext, nullptr)";
      goto LABEL_37;
    }
  }
LABEL_64:
  v112 = 0;
  v113 = 0;
  v109[0] = 0;
  v110 = 0;
  v111 = 0;
  Windows::Rtl::StopWatch::Start((Windows::Rtl::StopWatch *)v109);
  v127 = 0;
  v126 = 0;
  v48 = 0;
  v66 = 0;
  v128 = 0;
  v129 = 0;
  v130 = 0;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  if ( (a1 & 0x18) != 0 )
  {
    v49 = RMContext::Initialize((RMContext *)&v126, v47, &v66);
    v16 = v49;
    if ( v49 < 0 )
    {
      v102 = v49;
LABEL_110:
      RMContext::~RMContext((RMContext *)&v126);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v109);
      goto LABEL_111;
    }
    v48 = v66;
  }
  v50 = (a1 >> 5) & 1;
  if ( v48 )
  {
    v50 |= 4u;
    if ( (a1 & 8) != 0 )
      v50 |= 2u;
  }
  v122 = 0;
  v123 = 0;
  v119[0] = 0;
  v120 = 0;
  v121 = 0;
  v117 = 0;
  v118 = 0;
  v114[0] = 0;
  v115 = 0;
  v116 = 0;
  if ( !v103[0] )
  {
    v51 = v67;
    while ( 1 )
    {
      v135 = 0;
      memset_0(v134, 0, 0x50u);
      v136 = v68;
      v137 = v69;
      v138 = 0;
      v51(v69, v134, &v138, v103);
      if ( v103[0] )
        goto LABEL_95;
      if ( (_DWORD)v138 == 9
        || (_DWORD)v138 == 10
        || (_DWORD)v138 == 11
        || (_DWORD)v138 == 12
        || (_DWORD)v138 == 13
        || (v52 = 0, (_DWORD)v138 == 19) )
      {
        v52 = 1;
      }
      v53 = (Windows::Rtl::StopWatch *)v114;
      if ( v52 )
        v53 = (Windows::Rtl::StopWatch *)v119;
      Windows::Rtl::StopWatch::Start(v53);
      v54 = ExecuteSingleOperation(v50, a7, v134, v99, &v126);
      Windows::Rtl::StopWatch::Stop(v53);
      v56 = v88;
      if ( !v88 )
      {
        SendProgress(v55, v134, v108);
        v56 = v88;
      }
      if ( v54 < 0 )
        break;
      v54 = v101;
      if ( v101 < 0 )
        break;
      ++v12;
      FireDoneOperation::~FireDoneOperation((FireDoneOperation *)v134);
      if ( v103[0] )
        goto LABEL_96;
    }
    if ( v56 )
    {
      v87 = v54;
      v57 = IoCompletionContext::WaitForThreads((IoCompletionContext *)&v82);
      v16 = v57;
      if ( v57 < 0 )
        goto LABEL_92;
    }
    if ( !a9 )
    {
      if ( v54 >= 0 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x1802C4BADLL);
      }
      v102 = v54;
      FireDoneOperation::~FireDoneOperation((FireDoneOperation *)v134);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v114);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v119);
      RMContext::~RMContext((RMContext *)&v126);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v109);
      Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v104);
      v16 = v54;
      goto LABEL_112;
    }
    *(_DWORD *)(a9 + 4) = v138;
    *(_DWORD *)a9 = v54;
    *(_QWORD *)(a9 + 16) = v12;
    v57 = RtlpGenerateDiagnosabilityString(&v138, a9 + 24);
    v16 = v57;
    if ( v57 < 0 )
    {
LABEL_92:
      v102 = v57;
      FireDoneOperation::~FireDoneOperation((FireDoneOperation *)v134);
      goto LABEL_109;
    }
LABEL_95:
    FireDoneOperation::~FireDoneOperation((FireDoneOperation *)v134);
  }
LABEL_96:
  v58 = (_QWORD *)v107;
  if ( v107 )
  {
    *v58 += Windows::Rtl::StopWatch::ElapsedMilliseconds((Windows::Rtl::StopWatch *)v119);
    v58[1] += Windows::Rtl::StopWatch::ElapsedMilliseconds((Windows::Rtl::StopWatch *)v114);
  }
  if ( v88 )
  {
    v59 = IoCompletionContext::WaitForThreads((IoCompletionContext *)&v82);
    v16 = v59;
    if ( v59 < 0 )
    {
      v102 = v59;
LABEL_109:
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v114);
      Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v119);
      goto LABEL_110;
    }
    if ( v88 )
    {
      if ( v87 >= 0 )
      {
        if ( v85 != v86 )
        {
          v108 = v85;
          v107 = v86;
          Windows::WCP::Rtl::RtlAutoTrace<unsigned __int64,unsigned __int64>(
            v86,
            v60,
            v61,
            (unsigned int)&v108,
            (__int64)&v107);
          v71[2] = 4191;
          v71[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
          v71[3] = 0;
          v71[1] = "RtlRunPrimitiveOperationsFromCallbacksAgainstSil";
          v16 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                  &v102,
                  v71,
                  3221225701LL);
          goto LABEL_109;
        }
      }
      else if ( !a9 )
      {
        v16 = v87;
        v102 = v87;
        goto LABEL_109;
      }
    }
  }
  RMContext::Close((RMContext *)&v126);
  Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)v109);
  if ( Windows::WCP::Rtl::RtlIsTracingEnabled(
         (Windows::WCP::Rtl *)&Windows::WCP::Rtl::Facility_POQ,
         (struct Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)0x20000,
         v63) )
  {
    Windows::WCP::Rtl::RtlAutoTrace<Windows::Rtl::StopWatch>(1, v64, "CSI Perf Trace\nCSIPERF:POQEXECUTE:{}\n", v109);
  }
  v142 = 1;
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v114);
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v119);
  RMContext::~RMContext((RMContext *)&v126);
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v109);
  Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v104);
  IoCompletionContext::~IoCompletionContext((IoCompletionContext *)&v82);
  OperationContext::~OperationContext((OperationContext *)v99);
  PoqContext::~PoqContext((PoqContext *)v91);
  Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::~CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>(v141);
  return (unsigned int)v102;
}

```

## disassembly

```asm
0x1802c3d80  push    rbp
0x1802c3d82  push    rbx
0x1802c3d83  push    rsi
0x1802c3d84  push    rdi
0x1802c3d85  push    r12
0x1802c3d87  push    r13
0x1802c3d89  push    r14
0x1802c3d8b  push    r15
0x1802c3d8d  lea     rbp, [rsp-4E8h]
0x1802c3d95  sub     rsp, 5E8h
0x1802c3d9c  mov     rax, cs:__security_cookie
0x1802c3da3  xor     rax, rsp
0x1802c3da6  mov     [rbp+520h+var_50], rax
0x1802c3dad  mov     rax, [rbp+520h+arg_48]
0x1802c3db4  mov     rbx, r8
0x1802c3db7  mov     rsi, [rbp+520h+arg_38]
0x1802c3dbe  mov     r13d, ecx
0x1802c3dc1  mov     r14, [rbp+520h+arg_40]
0x1802c3dc8  lea     rcx, ?Facility_POQ@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; this
0x1802c3dcf  mov     rdi, [rbp+520h+arg_20]
0x1802c3dd6  xor     r12d, r12d
0x1802c3dd9  mov     r15, [rbp+520h+arg_30]
0x1802c3de0  mov     [rbp+520h+var_2D0], rax
0x1802c3de7  mov     rax, [rbp+520h+arg_28]
0x1802c3dee  mov     [rsp+620h+var_5A8], rax
0x1802c3df3  mov     [rsp+620h+var_5B0], r9
0x1802c3df8  mov     [rsp+620h+var_5B8], rbx
0x1802c3dfd  mov     [rbp+520h+var_2C8], rsi
0x1802c3e04  mov     [rbp+520h+var_2F0], r12d
0x1802c3e0b  call    ?RtlGetFacilityTracingFlags@Rtl@WCP@Windows@@YAKPEAU_RTL_TRACING_FACILITY@123@@Z; Windows::WCP::Rtl::RtlGetFacilityTracingFlags(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x1802c3e10  lea     rcx, ?Facility_POQ@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_POQ
0x1802c3e17  mov     [rbp+520h+var_108], r12d
0x1802c3e1e  mov     [rbp+520h+var_F8], r12b
0x1802c3e25  mov     [rbp+520h+var_128], 1
0x1802c3e2f  call    ?ShouldArm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$0A@@Rtl@WCP@Windows@@SA_NPEAU_RTL_TRACING_FACILITY@234@@Z; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::ShouldArm(Windows::WCP::Rtl::_RTL_TRACING_FACILITY *)
0x1802c3e34  lea     r9, aRtlrunprimitiv; "RtlRunPrimitiveOperationsFromCallbacksA"...
0x1802c3e3b  test    al, al
0x1802c3e3d  jz      short loc_1802C3E8C
0x1802c3e3f  mov     qword ptr [rsp+620h+var_5D0], r12; unsigned int
0x1802c3e44  lea     rax, ?Facility_POQ@Rtl@WCP@Windows@@3U_RTL_TRACING_FACILITY@123@A; Windows::WCP::Rtl::_RTL_TRACING_FACILITY Windows::WCP::Rtl::Facility_POQ
0x1802c3e4b  mov     [rsp+620h+var_5D8], r12; __int64
0x1802c3e50  lea     r8, [rbp+520h+var_2F0]; int
0x1802c3e57  mov     [rsp+620h+var_5E0], r12; __int64
0x1802c3e5c  lea     rcx, [rbp+520h+var_130]; int
0x1802c3e63  mov     [rsp+620h+var_5E8], r12; __int64
0x1802c3e68  xor     edx, edx; int
0x1802c3e6a  mov     [rsp+620h+var_5F0], rax; Windows::WCP::Rtl *
0x1802c3e6f  mov     [rsp+620h+var_5F8], r9; __int64
0x1802c3e74  lea     r9, ?RtlTraceFormat_PCNTSTATUS@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@PEBX@Z; int
0x1802c3e7b  mov     qword ptr [rsp+620h+InitialState], r12; __int64
0x1802c3e80  call    ?Arm@?$CEnterExitTracer@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@$0A@@Rtl@WCP@Windows@@QEAAXKAEBUCSimpleNtStatusCarryingFrame@2ErrorHandling@4@P6AXPEAUIRtlFormattedOutputStream@24@PEBX@Z2QEBDPEAU_RTL_TRACING_FACILITY@234@444_KZZ; Windows::WCP::Rtl::CEnterExitTracer<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,0>::Arm(ulong,Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame const &,void (*)(Windows::Rtl::IRtlFormattedOutputStream *,void const *),void const *,char const * const,Windows::WCP::Rtl::_RTL_TRACING_FACILITY *,char const * const,char const * const,char const * const,unsigned __int64,...)
0x1802c3e85  lea     r9, aRtlrunprimitiv; "RtlRunPrimitiveOperationsFromCallbacksA"...
0x1802c3e8c  xorps   xmm0, xmm0
0x1802c3e8f  mov     [rbp+520h+var_2EC], r12b
0x1802c3e96  xorps   xmm1, xmm1
0x1802c3e99  movdqa  [rbp+520h+var_3D0], xmm0
0x1802c3ea1  movdqa  [rbp+520h+var_3C0], xmm1
0x1802c3ea9  lea     rcx, [rbp+520h+var_370]; this
0x1802c3eb0  movdqa  [rbp+520h+var_3A0], xmm0
0x1802c3eb8  movdqa  [rbp+520h+var_390], xmm1
0x1802c3ec0  mov     [rbp+520h+var_3B0], r12
0x1802c3ec7  mov     [rbp+520h+var_3A8], r12
0x1802c3ece  mov     [rbp+520h+var_380], r12d
0x1802c3ed5  mov     [rbp+520h+var_37C], r12d
0x1802c3edc  mov     [rbp+520h+var_378], r12w
0x1802c3ee4  call    ??0OperationContext@@QEAA@XZ; OperationContext::OperationContext(void)
0x1802c3ee9  mov     [rbp+520h+var_3F0], r12b
0x1802c3ef0  xorps   xmm2, xmm2
0x1802c3ef3  movdqa  [rbp+520h+var_420], xmm2
0x1802c3efb  xorps   xmm3, xmm3
0x1802c3efe  movdqa  [rbp+520h+var_410], xmm3
0x1802c3f06  mov     [rbp+520h+var_400], r12d
0x1802c3f0d  mov     [rbp+520h+var_3FC], r12d
0x1802c3f14  mov     [rbp+520h+var_3F8], r12d
0x1802c3f1b  mov     [rbp+520h+var_3F4], r12d
0x1802c3f22  mov     [rbp+520h+var_3E8], r12
0x1802c3f29  mov     [rbp+520h+var_3E0], r12
0x1802c3f30  test    r14, r14
0x1802c3f33  jz      short loc_1802C3F46
0x1802c3f35  xorps   xmm0, xmm0
0x1802c3f38  movups  xmmword ptr [r14], xmm0
0x1802c3f3c  movups  xmmword ptr [r14+10h], xmm0
0x1802c3f41  movups  xmmword ptr [r14+20h], xmm0
0x1802c3f46  test    r13d, 0FFFFFCC6h
0x1802c3f4d  jz      short loc_1802C3F83
0x1802c3f4f  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c3f56  mov     [rbp+520h+var_4B8], r9
0x1802c3f5a  mov     [rbp+520h+var_4C0], rax
0x1802c3f5e  lea     rdx, [rbp+520h+var_4C0]
0x1802c3f62  lea     rax, aValidFlagsChec_0; "Valid flags check failed: Flags"
0x1802c3f69  mov     [rbp+520h+var_4B0], 0F92h
0x1802c3f71  lea     rcx, [rbp+520h+var_2F0]
0x1802c3f78  mov     [rbp+520h+var_4A8], rax
0x1802c3f7c  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1802c3f81  jmp     short loc_1802C3FC9
0x1802c3f83  test    r15, r15
0x1802c3f86  jnz     short loc_1802C3FD0
0x1802c3f88  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c3f8f  mov     [rbp+520h+var_498], r9
0x1802c3f96  mov     [rbp+520h+var_4A0], rax
0x1802c3f9d  lea     rdx, [rbp+520h+var_4A0]
0x1802c3fa4  lea     rax, aNotNullCheckFa_25; "Not-null check failed: IsoLayer"
0x1802c3fab  mov     [rbp+520h+var_490], 0F94h
0x1802c3fb6  mov     [rbp+520h+var_488], rax
0x1802c3fbd  lea     rcx, [rbp+520h+var_2F0]
0x1802c3fc4  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1802c3fc9  mov     ebx, eax
0x1802c3fcb  jmp     loc_1802C4A7F
0x1802c3fd0  test    rbx, rbx
0x1802c3fd3  jnz     short loc_1802C400C
0x1802c3fd5  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c3fdc  mov     [rbp+520h+var_478], r9
0x1802c3fe3  mov     [rbp+520h+var_480], rax
0x1802c3fea  lea     rdx, [rbp+520h+var_480]
0x1802c3ff1  lea     rax, aNotNullCheckFa_60; "Not-null check failed: GetOperationCall"...
0x1802c3ff8  mov     [rbp+520h+var_470], 0F95h
0x1802c4003  mov     [rbp+520h+var_468], rax
0x1802c400a  jmp     short loc_1802C3FBD
0x1802c400c  mov     rax, [r15]
0x1802c400f  lea     r8, [rbp+520h+var_2E8]
0x1802c4016  lea     rdx, _GUID_bf537349_9167_47f4_a8a8_df3c233df232
0x1802c401d  mov     [rbp+520h+var_2E8], r12
0x1802c4024  mov     rcx, r15
0x1802c4027  mov     rax, [rax+8]
0x1802c402b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4030  mov     ebx, eax
0x1802c4032  test    eax, eax
0x1802c4034  jns     short loc_1802C4041
0x1802c4036  mov     [rbp+520h+var_2F0], eax
0x1802c403c  jmp     loc_1802C4A73
0x1802c4041  mov     rcx, [rbp+520h+var_2E8]
0x1802c4048  lea     rax, [rbp+520h+var_3D0]
0x1802c404f  mov     [rbp+520h+var_308], rax
0x1802c4056  mov     [rbp+520h+var_3B0], rdi
0x1802c405d  mov     rax, [rcx]
0x1802c4060  mov     rax, [rax+10h]
0x1802c4064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4069  mov     rcx, rax; this
0x1802c406c  call    ?IsUnbufferedSil@CSystemIsolationLayer@SystemImplementation@Rtl@Windows@@QEBA_NXZ; Windows::Rtl::SystemImplementation::CSystemIsolationLayer::IsUnbufferedSil(void)
0x1802c4071  mov     byte ptr [rbp+520h+var_37C], al
0x1802c4077  lea     rcx, [rbp+520h+var_3D0]; this
0x1802c407e  mov     al, r13b
0x1802c4081  mov     qword ptr [rbp+520h+var_3A0], r14
0x1802c4088  and     al, 1
0x1802c408a  mov     qword ptr [rbp+520h+var_3A0+8], rsi
0x1802c4091  mov     byte ptr [rbp+520h+var_37C+1], al
0x1802c4097  mov     rdx, r15; struct Windows::Rtl::IRtlSystemIsolationLayerPublic *
0x1802c409a  mov     eax, r13d
0x1802c409d  shr     eax, 9
0x1802c40a0  and     al, 1
0x1802c40a2  mov     byte ptr [rbp+520h+var_378+1], al
0x1802c40a8  lea     rax, [rbp+520h+var_420]
0x1802c40af  mov     [rbp+520h+var_3A8], rax
0x1802c40b6  call    ?Initialize@PendingDeletesHelper@Rtl@Windows@@QEAAJPEAUIRtlSystemIsolationLayerPublic@23@PEAUIRtlDirectory@23@PEAVIUpdateReserveManager@@@Z; Windows::Rtl::PendingDeletesHelper::Initialize(Windows::Rtl::IRtlSystemIsolationLayerPublic *,Windows::Rtl::IRtlDirectory *,IUpdateReserveManager *)
0x1802c40bb  mov     ebx, eax
0x1802c40bd  test    eax, eax
0x1802c40bf  js      loc_1802C4036
0x1802c40c5  cmp     [rbp+520h+var_340], r12
0x1802c40cc  jz      short loc_1802C40CF
0x1802c40ce  int     3; Trap to Debugger
0x1802c40cf  lea     rdx, [rbp+520h+var_340]
0x1802c40d6  mov     rcx, r15
0x1802c40d9  call    ??$CreateRequiredInterface@UIRtlSystemIsolationLayer@Rtl@Windows@@@IRtlObject@Rtl@Windows@@QEAAJPEAV?$Auto@PEAUIRtlSystemIsolationLayer@Rtl@Windows@@@2@@Z; Windows::Rtl::IRtlObject::CreateRequiredInterface<Windows::Rtl::IRtlSystemIsolationLayer>(Windows::Auto<Windows::Rtl::IRtlSystemIsolationLayer *> *)
0x1802c40de  mov     ebx, eax
0x1802c40e0  test    eax, eax
0x1802c40e2  js      loc_1802C4036
0x1802c40e8  cmp     byte ptr [rbp+520h+var_378+1], r12b
0x1802c40ef  jnz     loc_1802C422F
0x1802c40f5  lea     rdx, ??$LiteralObject@$2U?$BaseLiteralBuffer@$0M@U_LUNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FM@@0FD@@0HJ@@0HD@@0HE@@0GF@@0GN@@0FC@@0GP@@0GP@@0HE@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08$09$0L@@Details@RtlStringLiterals@@3U_LUNICODE_STRING@@B; struct _LUNICODE_STRING *
0x1802c40fc  lea     rcx, [rbp+520h+var_370]; this
0x1802c4103  call    ?TryAddProtectedPath@SafeOpenCreateHelper@@QEAAJAEBU_LUNICODE_STRING@@@Z; SafeOpenCreateHelper::TryAddProtectedPath(_LUNICODE_STRING const &)
0x1802c4108  mov     ebx, eax
0x1802c410a  test    eax, eax
0x1802c410c  js      loc_1802C4036
0x1802c4112  mov     rax, [r15]
0x1802c4115  lea     r9, [rbp+520h+var_2E0]
0x1802c411c  xor     r8d, r8d
0x1802c411f  mov     [rbp+520h+var_2E0], r12
0x1802c4126  xor     edx, edx
0x1802c4128  mov     qword ptr [rsp+620h+InitialState], r12
0x1802c412d  mov     rcx, r15
0x1802c4130  mov     rax, [rax+80h]
0x1802c4137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c413c  mov     ebx, eax
0x1802c413e  test    eax, eax
0x1802c4140  jns     short loc_1802C4159
0x1802c4142  mov     [rbp+520h+var_2F0], eax
0x1802c4148  lea     rcx, [rbp+520h+var_2E0]
0x1802c414f  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c4154  jmp     loc_1802C4A73
0x1802c4159  mov     rcx, [rbp+520h+var_2E0]
0x1802c4160  lea     r9, [rbp+520h+var_248]
0x1802c4167  xor     eax, eax
0x1802c4169  mov     qword ptr [rsp+620h+InitialState], r12
0x1802c416e  mov     [rbp+520h+var_238], rax
0x1802c4175  xorps   xmm0, xmm0
0x1802c4178  movups  [rbp+520h+var_248], xmm0
0x1802c417f  mov     rax, [rcx]
0x1802c4182  xor     edx, edx
0x1802c4184  mov     r8d, 100000h
0x1802c418a  mov     rax, [rax+20h]
0x1802c418e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c4193  mov     ebx, eax
0x1802c4195  test    eax, eax
0x1802c4197  jns     short loc_1802C41AD
0x1802c4199  mov     [rbp+520h+var_2F0], eax
0x1802c419f  lea     rcx, [rbp+520h+var_248]
0x1802c41a6  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1802c41ab  jmp     short loc_1802C4148
0x1802c41ad  mov     rax, [r15]
0x1802c41b0  lea     rdx, [rbp+520h+var_248]
0x1802c41b7  mov     r8d, 80000000h
0x1802c41bd  mov     rcx, r15
0x1802c41c0  mov     rax, [rax+0B0h]
0x1802c41c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c41cc  test    al, al
0x1802c41ce  jz      short loc_1802C4217
0x1802c41d0  lea     r9, [rbp+520h+var_2D8]
0x1802c41d7  mov     [rbp+520h+var_2D8], r12
0x1802c41de  lea     r8, [rbp+520h+var_248]
0x1802c41e5  mov     qword ptr [rsp+620h+InitialState], r12; __int64
0x1802c41ea  xor     edx, edx
0x1802c41ec  lea     rcx, [rbp+520h+var_370]; this
0x1802c41f3  call    ?SafeOpenDirectory@SafeOpenCreateHelper@@QEAAJW4SafeOpenDirectoryFlags@1@AEBU_LUNICODE_STRING@@PEAV?$Auto@PEAUIRtlDirectory@Rtl@Windows@@@Windows@@PEAW4SafeOpenDirectoryDisposition@1@@Z; SafeOpenCreateHelper::SafeOpenDirectory(SafeOpenCreateHelper::SafeOpenDirectoryFlags,_LUNICODE_STRING const &,Windows::Auto<Windows::Rtl::IRtlDirectory *> *,SafeOpenCreateHelper::SafeOpenDirectoryDisposition *)
0x1802c41f8  lea     rcx, [rbp+520h+var_2D8]
0x1802c41ff  mov     ebx, eax
0x1802c4201  test    eax, eax
0x1802c4203  jns     short loc_1802C4212
0x1802c4205  mov     [rbp+520h+var_2F0], eax
0x1802c420b  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c4210  jmp     short loc_1802C419F
0x1802c4212  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c4217  lea     rcx, [rbp+520h+var_248]
0x1802c421e  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1802c4223  lea     rcx, [rbp+520h+var_2E0]
0x1802c422a  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x1802c422f  bt      r13d, 8
0x1802c4234  jnb     short loc_1802C4246
0x1802c4236  mov     word ptr [rbp+520h+var_37C+2], 101h
0x1802c423f  mov     byte ptr [rbp+520h+var_378], 1
0x1802c4246  mov     rdi, r12
0x1802c4249  cmp     byte ptr [rbp+520h+var_37C], r12b
0x1802c4250  jz      loc_1802C42F7
0x1802c4256  mov     ebx, 40h ; '@'
0x1802c425b  lea     rcx, [rbp+520h+SystemInformation]; void *
0x1802c4262  mov     r8d, ebx; Size
0x1802c4265  xor     edx, edx; Val
0x1802c4267  call    memset_0
0x1802c426c  xor     r9d, r9d; ReturnLength
0x1802c426f  lea     rdx, [rbp+520h+SystemInformation]; SystemInformation
0x1802c4276  mov     r8d, ebx; SystemInformationLength
0x1802c4279  xor     ecx, ecx; SystemInformationClass
0x1802c427b  call    cs:__imp_NtQuerySystemInformation
0x1802c4282  nop     dword ptr [rax+rax+00h]
0x1802c4287  mov     r8d, eax
0x1802c428a  test    eax, eax
0x1802c428c  jns     short loc_1802C42DD
0x1802c428e  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c4295  mov     [rbp+520h+var_450], 0FCBh
0x1802c42a0  mov     [rbp+520h+var_460], rax
0x1802c42a7  lea     rdx, [rbp+520h+var_460]
0x1802c42ae  lea     rax, aRtlrunprimitiv; "RtlRunPrimitiveOperationsFromCallbacksA"...
0x1802c42b5  mov     [rbp+520h+var_458], rax
0x1802c42bc  lea     rax, aNtquerysystemi; "NtQuerySystemInformation(SystemBasicInf"...
0x1802c42c3  mov     [rbp+520h+var_448], rax
0x1802c42ca  lea     rcx, [rbp+520h+var_2F0]
0x1802c42d1  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1802c42d6  mov     ebx, eax
0x1802c42d8  jmp     loc_1802C4A73
0x1802c42dd  mov     al, [rbp+520h+var_138]
0x1802c42e3  cmp     al, 2
0x1802c42e5  jge     short loc_1802C42EB
0x1802c42e7  mov     al, 2
0x1802c42e9  jmp     short loc_1802C42F1
0x1802c42eb  mov     cl, 0Ah
0x1802c42ed  cmp     al, cl
0x1802c42ef  jg      short loc_1802C42F3
0x1802c42f1  mov     cl, al
0x1802c42f3  movsx   rdi, cl
0x1802c42f7  mov     rax, [r15]
0x1802c42fa  lea     rdx, [rbp+520h+var_3E8]
0x1802c4301  mov     rcx, r15
0x1802c4304  mov     rax, [rax+68h]
0x1802c4308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802c430d  mov     ebx, eax
0x1802c430f  test    eax, eax
0x1802c4311  js      loc_1802C4036
0x1802c4317  mov     [rbp+520h+var_3E0], r15
0x1802c431e  cmp     byte ptr [rbp+520h+var_37C+1], r12b
0x1802c4325  jz      short loc_1802C437D
0x1802c4327  cmp     byte ptr [rbp+520h+var_37C], r12b
0x1802c432e  jnz     short loc_1802C437D
0x1802c4330  lea     rax, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c4337  mov     [rbp+520h+var_430], 0FD9h
0x1802c4342  mov     [rbp+520h+var_440], rax
0x1802c4349  lea     rdx, [rbp+520h+var_440]
0x1802c4350  lea     rax, aRtlrunprimitiv; "RtlRunPrimitiveOperationsFromCallbacksA"...
0x1802c4357  mov     [rbp+520h+var_438], rax
0x1802c435e  lea     rcx, [rbp+520h+var_2F0]
0x1802c4365  lea     rax, aGlobalcontextF; "!GlobalContext.fPendingDeletesBehavior "...
  ... truncated ...
```
