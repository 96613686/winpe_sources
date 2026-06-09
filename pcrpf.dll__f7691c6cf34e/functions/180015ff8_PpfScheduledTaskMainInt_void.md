# PpfScheduledTaskMainInt(void)

- ea: `0x180015ff8`
- end: `0x18001648f`
- name: `?PpfScheduledTaskMainInt@@YAJXZ`
- size: `1175`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b900`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000c458`
- `0x18000c5cc`
- `0x18000ca1c`
- `0x18000d1e8`
- `0x18000f300`
- `0x18000f5dc`
- `0x18000fec8`
- `0x1800107e8`
- `0x180015ff8`
- `0x1800187c4`
- `0x18001a34c`
- `0x18001b5a0`
- `0x18001c0a0`
- `0x18002d5ec`
- `0x180039354`
- `0x18003b418`

## string_xrefs

- `0x1800160a2`: `onecore\base\ngscb\pcrpf\dll\pcrpfcpp.h`
- `0x180016052`: `PpfScheduledTaskActivity`
- `0x1800160bd`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001615a`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x1800161e6`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001626c`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180016304`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x1800163a6`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180016024`: `PpfScheduledTaskMainInt`

## pseudocode

```c
__int64 PpfScheduledTaskMainInt(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  int v3; // eax
  int v4; // eax
  PpfTransformStore *v5; // rcx
  int v6; // eax
  bool v7; // bl
  int v8; // eax
  PpfTransformStore *v9; // rcx
  unsigned int v10; // edi
  int v11; // eax
  int v12; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+20h] [rbp-E0h]
  bool v15; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v16; // [rsp+38h] [rbp-C8h] BYREF
  char v17; // [rsp+40h] [rbp-C0h]
  _QWORD v18[42]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[208]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfScheduledTaskMainInt");
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "PpfScheduledTaskActivity");
  v18[0] = &PpfTraceLoggingProvider::PpfScheduledTaskActivity::`vftable';
  PpfTraceLoggingProvider::PpfScheduledTaskActivity::StartActivity((PpfTraceLoggingProvider::PpfScheduledTaskActivity *)v18);
  v16 = 0;
  v17 = 0;
  v0 = PpfLock(&v16);
  v1 = v0;
  if ( v0 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpfcpp.h",
      (const char *)(unsigned int)v0,
      v12);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x638,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)v1,
      v13);
    if ( v17 )
      PpfUnlock(&v16);
    v18[0] = &PpfTraceLoggingProvider::PpfScheduledTaskActivity::`vftable';
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v18);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfScheduledTaskMainInt");
    return v1;
  }
  v17 = 1;
  PpfState::PpfState((PpfState *)v19);
  v3 = PpfState::Initialize((PpfState *)v19, 0xFFFFFFFF, 0, 0);
  v1 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63D,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v3,
      v12);
    PpfState::~PpfState((PpfState *)v19);
    PpfUnlock(&v16);
    v18[0] = &PpfTraceLoggingProvider::PpfScheduledTaskActivity::`vftable';
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v18);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfScheduledTaskMainInt");
    return v1;
  }
  v4 = PpfState::Commit(v19, 0, 2, 0);
  v1 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63E,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v4,
      v12);
    PpfState::~PpfState((PpfState *)v19);
    PpfUnlock(&v16);
    v18[0] = &PpfTraceLoggingProvider::PpfScheduledTaskActivity::`vftable';
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v18);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfScheduledTaskMainInt");
    return v1;
  }
  v15 = 0;
  v6 = PpfTransformStore::WasLastUpdateInProgress(v5, &v15);
  v1 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x646,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
      (const char *)(unsigned int)v6,
      v12);
    PpfState::~PpfState((PpfState *)v19);
    PpfUnlock(&v16);
    v18[0] = &PpfTraceLoggingProvider::PpfScheduledTaskActivity::`vftable';
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v18);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfScheduledTaskMainInt");
    return v1;
  }
  v7 = v15;
  if ( v15 )
  {
    v8 = NotifySubscribers(0, 3, *(_QWORD *)&Data);
    v10 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64A,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)(unsigned int)v8,
        v12);
      PpfState::~PpfState((PpfState *)v19);
      PpfUnlock(&v16);
      v18[0] = &PpfTraceLoggingProvider::PpfScheduledTaskActivity::`vftable';
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v18);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfScheduledTaskMainInt");
      return v10;
    }
    v11 = PpfTransformStore::MarkUpdateInProgress(v9, 0, 0);
    v10 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F8,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
        (const char *)(unsigned int)v11,
        v12);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x64B,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)v10,
        v14);
      PpfState::~PpfState((PpfState *)v19);
      PpfUnlock(&v16);
      v18[0] = &PpfTraceLoggingProvider::PpfScheduledTaskActivity::`vftable';
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v18);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfScheduledTaskMainInt");
      return v10;
    }
  }
  PpfTraceLoggingProvider::PpfScheduledTaskActivity::StopActivity(
    (PpfTraceLoggingProvider::PpfScheduledTaskActivity *)v18,
    v7);
  PpfState::~PpfState((PpfState *)v19);
  PpfUnlock(&v16);
  v18[0] = &PpfTraceLoggingProvider::PpfScheduledTaskActivity::`vftable';
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v18);
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v18);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfScheduledTaskMainInt");
  return 0;
}

```

## disassembly

```asm
0x180015ff8  push    rbp
0x180015ffa  push    rbx
0x180015ffb  push    rdi
0x180015ffc  push    r12
0x180015ffe  push    r13
0x180016000  push    r14
0x180016002  push    r15
0x180016004  lea     rbp, [rsp-180h]
0x18001600c  sub     rsp, 280h
0x180016013  mov     rax, cs:__security_cookie
0x18001601a  xor     rax, rsp
0x18001601d  mov     [rbp+1B0h+var_40], rax
0x180016024  lea     r13, aPpfscheduledta_4; "PpfScheduledTaskMainInt"
0x18001602b  mov     qword ptr [rsp+2B0h+var_290], r13; int
0x180016030  lea     r9, aEnteringHs; "Entering %hs"
0x180016037  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18001603e  mov     edx, 84h; unsigned int
0x180016043  lea     r15, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001604a  mov     rcx, r15; char *
0x18001604d  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180016052  lea     rdx, aPpfscheduledta_1; "PpfScheduledTaskActivity"
0x180016059  lea     rcx, [rsp+2B0h+var_260]
0x18001605e  call    ??0?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180016063  lea     r12, ??_7PpfScheduledTaskActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::PpfScheduledTaskActivity::`vftable'
0x18001606a  mov     [rsp+2B0h+var_260], r12
0x18001606f  lea     rcx, [rsp+2B0h+var_260]; this
0x180016074  call    ?StartActivity@PpfScheduledTaskActivity@PpfTraceLoggingProvider@@QEAAXXZ; PpfTraceLoggingProvider::PpfScheduledTaskActivity::StartActivity(void)
0x180016079  xor     eax, eax
0x18001607b  mov     [rsp+2B0h+var_278], rax
0x180016080  mov     [rsp+2B0h+var_270], al
0x180016084  lea     rcx, [rsp+2B0h+var_278]
0x180016089  call    PpfLock
0x18001608e  mov     ebx, eax
0x180016090  test    eax, eax
0x180016092  jns     loc_180016121
0x180016098  mov     rcx, [rbp+1B8h]; this
0x18001609f  mov     r9d, eax; char *
0x1800160a2  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800160a9  mov     edx, 11h; void *
0x1800160ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800160b3  mov     rcx, [rbp+1B8h]; this
0x1800160ba  mov     r9d, ebx; char *
0x1800160bd  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800160c4  mov     edx, 638h; void *
0x1800160c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800160ce  cmp     [rsp+2B0h+var_270], 0
0x1800160d3  jz      short loc_1800160DF
0x1800160d5  lea     rcx, [rsp+2B0h+var_278]
0x1800160da  call    PpfUnlock
0x1800160df  mov     [rsp+2B0h+var_260], r12
0x1800160e4  lea     rcx, [rsp+2B0h+var_260]
0x1800160e9  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800160ee  lea     rcx, [rsp+2B0h+var_260]
0x1800160f3  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800160f8  nop
0x1800160f9  mov     qword ptr [rsp+2B0h+var_290], r13
0x1800160fe  lea     r9, aLeavingHs; "Leaving %hs"
0x180016105  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001610c  mov     edx, 89h; unsigned int
0x180016111  mov     rcx, r15; char *
0x180016114  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180016119  nop
0x18001611a  mov     eax, ebx
0x18001611c  jmp     loc_18001646C
0x180016121  mov     r14b, 1
0x180016124  mov     [rsp+2B0h+var_270], r14b
0x180016129  lea     rcx, [rbp+1B0h+var_110]; this
0x180016130  call    ??0PpfState@@QEAA@XZ; PpfState::PpfState(void)
0x180016135  xor     r9d, r9d; unsigned __int16 *
0x180016138  xor     r8d, r8d; bool
0x18001613b  or      edx, 0FFFFFFFFh; unsigned int
0x18001613e  lea     rcx, [rbp+1B0h+var_110]; this
0x180016145  call    ?Initialize@PpfState@@QEAAJI_NPEBG@Z; PpfState::Initialize(uint,bool,ushort const *)
0x18001614a  mov     ebx, eax
0x18001614c  test    eax, eax
0x18001614e  jns     short loc_1800161C1
0x180016150  mov     rcx, [rbp+1B8h]; this
0x180016157  mov     r9d, eax; char *
0x18001615a  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180016161  mov     edx, 63Dh; void *
0x180016166  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001616b  lea     rcx, [rbp+1B0h+var_110]; this
0x180016172  call    ??1PpfState@@QEAA@XZ; PpfState::~PpfState(void)
0x180016177  lea     rcx, [rsp+2B0h+var_278]
0x18001617c  call    PpfUnlock
0x180016181  mov     [rsp+2B0h+var_260], r12
0x180016186  lea     rcx, [rsp+2B0h+var_260]
0x18001618b  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180016190  lea     rcx, [rsp+2B0h+var_260]
0x180016195  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001619a  nop
0x18001619b  mov     qword ptr [rsp+2B0h+var_290], r13
0x1800161a0  lea     r9, aLeavingHs; "Leaving %hs"
0x1800161a7  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800161ae  mov     edx, 89h; unsigned int
0x1800161b3  mov     rcx, r15; char *
0x1800161b6  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800161bb  nop
0x1800161bc  jmp     loc_18001611A
0x1800161c1  xor     r9d, r9d
0x1800161c4  xor     edx, edx
0x1800161c6  lea     r8d, [r9+2]
0x1800161ca  lea     rcx, [rbp+1B0h+var_110]
0x1800161d1  call    ?Commit@PpfState@@QEAAJIW4PPF_SUBSCRIBER_NOTIFICATION_SCENARIO@@PEBG@Z; PpfState::Commit(uint,PPF_SUBSCRIBER_NOTIFICATION_SCENARIO,ushort const *)
0x1800161d6  mov     ebx, eax
0x1800161d8  test    eax, eax
0x1800161da  jns     short loc_18001624D
0x1800161dc  mov     rcx, [rbp+1B8h]; this
0x1800161e3  mov     r9d, eax; char *
0x1800161e6  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800161ed  mov     edx, 63Eh; void *
0x1800161f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800161f7  lea     rcx, [rbp+1B0h+var_110]; this
0x1800161fe  call    ??1PpfState@@QEAA@XZ; PpfState::~PpfState(void)
0x180016203  lea     rcx, [rsp+2B0h+var_278]
0x180016208  call    PpfUnlock
0x18001620d  mov     [rsp+2B0h+var_260], r12
0x180016212  lea     rcx, [rsp+2B0h+var_260]
0x180016217  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001621c  lea     rcx, [rsp+2B0h+var_260]
0x180016221  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180016226  nop
0x180016227  mov     qword ptr [rsp+2B0h+var_290], r13
0x18001622c  lea     r9, aLeavingHs; "Leaving %hs"
0x180016233  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001623a  mov     edx, 89h; unsigned int
0x18001623f  mov     rcx, r15; char *
0x180016242  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180016247  nop
0x180016248  jmp     loc_18001611A
0x18001624d  mov     [rsp+2B0h+var_280], 0
0x180016252  lea     rdx, [rsp+2B0h+var_280]; bool *
0x180016257  call    ?WasLastUpdateInProgress@PpfTransformStore@@QEAAJPEA_N@Z; PpfTransformStore::WasLastUpdateInProgress(bool *)
0x18001625c  mov     ebx, eax
0x18001625e  test    eax, eax
0x180016260  jns     short loc_1800162D3
0x180016262  mov     rcx, [rbp+1B8h]; this
0x180016269  mov     r9d, eax; char *
0x18001626c  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180016273  mov     edx, 646h; void *
0x180016278  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001627d  lea     rcx, [rbp+1B0h+var_110]; this
0x180016284  call    ??1PpfState@@QEAA@XZ; PpfState::~PpfState(void)
0x180016289  lea     rcx, [rsp+2B0h+var_278]
0x18001628e  call    PpfUnlock
0x180016293  mov     [rsp+2B0h+var_260], r12
0x180016298  lea     rcx, [rsp+2B0h+var_260]
0x18001629d  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800162a2  lea     rcx, [rsp+2B0h+var_260]
0x1800162a7  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800162ac  nop
0x1800162ad  mov     qword ptr [rsp+2B0h+var_290], r13
0x1800162b2  lea     r9, aLeavingHs; "Leaving %hs"
0x1800162b9  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800162c0  mov     edx, 89h; unsigned int
0x1800162c5  mov     rcx, r15; char *
0x1800162c8  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800162cd  nop
0x1800162ce  jmp     loc_18001611A
0x1800162d3  mov     bl, [rsp+2B0h+var_280]
0x1800162d7  test    bl, bl
0x1800162d9  jz      loc_18001640D
0x1800162df  xor     r9d, r9d
0x1800162e2  mov     r8, cs:Data
0x1800162e9  lea     edx, [r9+3]
0x1800162ed  xor     ecx, ecx
0x1800162ef  call    ?NotifySubscribers@@YAJIW4PPF_SUBSCRIBER_NOTIFICATION_SCENARIO@@_KPEBG@Z; NotifySubscribers(uint,PPF_SUBSCRIBER_NOTIFICATION_SCENARIO,unsigned __int64,ushort const *)
0x1800162f4  mov     edi, eax
0x1800162f6  test    eax, eax
0x1800162f8  jns     short loc_18001636D
0x1800162fa  mov     rcx, [rbp+1B8h]; this
0x180016301  mov     r9d, eax; char *
0x180016304  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001630b  mov     edx, 64Ah; void *
0x180016310  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016315  lea     rcx, [rbp+1B0h+var_110]; this
0x18001631c  call    ??1PpfState@@QEAA@XZ; PpfState::~PpfState(void)
0x180016321  lea     rcx, [rsp+2B0h+var_278]
0x180016326  call    PpfUnlock
0x18001632b  mov     [rsp+2B0h+var_260], r12
0x180016330  lea     rcx, [rsp+2B0h+var_260]
0x180016335  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001633a  lea     rcx, [rsp+2B0h+var_260]
0x18001633f  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180016344  nop
0x180016345  mov     qword ptr [rsp+2B0h+var_290], r13
0x18001634a  lea     r9, aLeavingHs; "Leaving %hs"
0x180016351  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180016358  mov     edx, 89h; unsigned int
0x18001635d  mov     rcx, r15; char *
0x180016360  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180016365  nop
0x180016366  mov     eax, edi
0x180016368  jmp     loc_18001646C
0x18001636d  xor     r8d, r8d; bool
0x180016370  xor     edx, edx; HKEY
0x180016372  call    ?MarkUpdateInProgress@PpfTransformStore@@AEAAJPEAUHKEY__@@_N@Z; PpfTransformStore::MarkUpdateInProgress(HKEY__ *,bool)
0x180016377  mov     edi, eax
0x180016379  test    eax, eax
0x18001637b  jns     loc_18001640D
0x180016381  mov     rcx, [rbp+1B8h]; this
0x180016388  mov     r9d, eax; char *
0x18001638b  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180016392  mov     edx, 1F8h; void *
0x180016397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001639c  mov     rcx, [rbp+1B8h]; this
0x1800163a3  mov     r9d, edi; char *
0x1800163a6  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800163ad  mov     edx, 64Bh; void *
0x1800163b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800163b7  lea     rcx, [rbp+1B0h+var_110]; this
0x1800163be  call    ??1PpfState@@QEAA@XZ; PpfState::~PpfState(void)
0x1800163c3  lea     rcx, [rsp+2B0h+var_278]
0x1800163c8  call    PpfUnlock
0x1800163cd  mov     [rsp+2B0h+var_260], r12
0x1800163d2  lea     rcx, [rsp+2B0h+var_260]
0x1800163d7  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800163dc  lea     rcx, [rsp+2B0h+var_260]
0x1800163e1  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800163e6  nop
0x1800163e7  mov     qword ptr [rsp+2B0h+var_290], r13
0x1800163ec  lea     r9, aLeavingHs; "Leaving %hs"
0x1800163f3  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800163fa  mov     edx, 89h; unsigned int
0x1800163ff  mov     rcx, r15; char *
0x180016402  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180016407  nop
0x180016408  jmp     loc_180016366
0x18001640d  mov     dl, bl; bool
0x18001640f  lea     rcx, [rsp+2B0h+var_260]; this
0x180016414  call    ?StopActivity@PpfScheduledTaskActivity@PpfTraceLoggingProvider@@QEAAX_N@Z; PpfTraceLoggingProvider::PpfScheduledTaskActivity::StopActivity(bool)
0x180016419  lea     rcx, [rbp+1B0h+var_110]; this
0x180016420  call    ??1PpfState@@QEAA@XZ; PpfState::~PpfState(void)
0x180016425  lea     rcx, [rsp+2B0h+var_278]
0x18001642a  call    PpfUnlock
0x18001642f  mov     [rsp+2B0h+var_260], r12
0x180016434  lea     rcx, [rsp+2B0h+var_260]
0x180016439  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18001643e  lea     rcx, [rsp+2B0h+var_260]
0x180016443  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180016448  nop
0x180016449  mov     qword ptr [rsp+2B0h+var_290], r13
0x18001644e  lea     r9, aLeavingHs; "Leaving %hs"
0x180016455  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001645c  mov     edx, 89h; unsigned int
0x180016461  mov     rcx, r15; char *
0x180016464  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180016469  nop
0x18001646a  xor     eax, eax
0x18001646c  mov     rcx, [rbp+1B0h+var_40]
0x180016473  xor     rcx, rsp; StackCookie
0x180016476  call    __security_check_cookie
0x18001647b  add     rsp, 280h
0x180016482  pop     r15
0x180016484  pop     r14
0x180016486  pop     r13
0x180016488  pop     r12
0x18001648a  pop     rdi
0x18001648b  pop     rbx
0x18001648c  pop     rbp
0x18001648d  retn
```
