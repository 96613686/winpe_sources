# PpfState::Commit(uint,PPF_SUBSCRIBER_NOTIFICATION_SCENARIO,ushort const *)

- ea: `0x18000fec8`
- end: `0x18001056c`
- name: `?Commit@PpfState@@QEAAJIW4PPF_SUBSCRIBER_NOTIFICATION_SCENARIO@@PEBG@Z`
- size: `1700`
- prototype: `__int64 __fastcall(_BYTE *, int, unsigned int, __int64)`
- caller_count: `4`
- callee_count: `18`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013ef4`
- `0x1800141f4`
- `0x180015ff8`
- `0x180016498`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000c458`
- `0x18000c5cc`
- `0x18000ca1c`
- `0x18000d1e8`
- `0x18000fec8`
- `0x180018224`
- `0x180018d3c`
- `0x18001af7c`
- `0x18001aff0`
- `0x18002d5ec`
- `0x18003796c`
- `0x180038c7c`
- `0x180038d80`
- `0x18003c02c`
- `0x18003c280`
- `0x18003fcac`

## string_xrefs

- `0x18000ff2c`: `PpfCommitActivity`
- `0x18000ffe9`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001006d`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001010e`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x1800101a6`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x1800101c8`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x1800101fe`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180010219`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001028d`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180010325`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180010347`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001037d`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180010398`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18001040c`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x180010487`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`
- `0x18000ff01`: `PpfState::Commit`
- `0x18001001b`: `PpfState::Commit`
- `0x18001009f`: `PpfState::Commit`
- `0x180010140`: `PpfState::Commit`
- `0x180010197`: `PpfState::Commit`
- `0x1800102bf`: `PpfState::Commit`
- `0x180010316`: `PpfState::Commit`
- `0x18001043e`: `PpfState::Commit`
- `0x1800104b9`: `PpfState::Commit`
- `0x18001051a`: `PpfState::Commit`

## pseudocode

```c
// Hidden C++ exception states: #wind=54
__int64 __fastcall PpfState::Commit(_BYTE *a1, int a2, unsigned int a3, __int64 a4)
{
  PpfTransformStore *v8; // rsi
  char v9; // al
  __int64 *v10; // rax
  __int64 **v11; // rdx
  __int64 *i; // rcx
  __int64 *j; // rdx
  PpfScheduledTask *v14; // rbx
  int v15; // eax
  unsigned int v16; // edi
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  unsigned int v27; // ebx
  int v28; // [rsp+20h] [rbp-E0h]
  char v29; // [rsp+30h] [rbp-D0h]
  _QWORD v30[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfState::Commit");
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v30,
    "PpfCommitActivity");
  v30[0] = &PpfTraceLoggingProvider::PpfCommitActivity::`vftable';
  PpfTraceLoggingProvider::PpfCommitActivity::StartActivity((PpfTraceLoggingProvider::PpfCommitActivity *)v30);
  v8 = (PpfTransformStore *)(a1 + 16);
  v9 = a1[112];
  v29 = v9;
  if ( v9 )
  {
    v10 = *(__int64 **)qword_180072C10;
    while ( 1 )
    {
      if ( *((_BYTE *)v10 + 25) )
      {
        v14 = (PpfScheduledTask *)(a1 + 136);
        goto LABEL_18;
      }
      if ( *((_DWORD *)v10 + 16) == 2 )
        break;
      v11 = (__int64 **)v10[2];
      if ( *((_BYTE *)v11 + 25) )
      {
        for ( i = (__int64 *)v10[1]; !*((_BYTE *)i + 25) && v10 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v10 = i;
        v10 = i;
      }
      else
      {
        v10 = (__int64 *)v10[2];
        for ( j = *v11; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v10 = j;
      }
    }
    v14 = (PpfScheduledTask *)(a1 + 136);
    v15 = PpfScheduledTask::ManageScheduledTask((PpfScheduledTask *)(a1 + 136), 1);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F5,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)(unsigned int)v15,
        v28);
      v30[0] = &PpfTraceLoggingProvider::PpfCommitActivity::`vftable';
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v30);
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v30);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfState::Commit");
      return v16;
    }
LABEL_18:
    v18 = PpfTransformStore::Finalize((PpfTransformStore *)(a1 + 16));
    v16 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2FB,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)(unsigned int)v18,
        v28);
      v30[0] = &PpfTraceLoggingProvider::PpfCommitActivity::`vftable';
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v30);
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v30);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfState::Commit");
      return v16;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
    {
      if ( !qword_180072C40 )
      {
        v19 = PpfScheduledTask::EnableTemporarily((PpfScheduledTask *)(a1 + 136));
        v16 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x304,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
            (const char *)(unsigned int)v19,
            v28);
          v30[0] = &PpfTraceLoggingProvider::PpfCommitActivity::`vftable';
          wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v30);
          wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v30);
          PpfTraceLogFormat(
            "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
            0x89u,
            "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
            "Leaving %hs",
            "PpfState::Commit");
          return v16;
        }
        v16 = NotifySubscribers(a2, a3, *(unsigned __int64 *)&Data, a4);
        if ( (v16 & 0x80000000) != 0 )
        {
          PpfTraceLogFormat(
            "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
            0x309u,
            "PpfState::Commit",
            "Subscribers notification failed, discarding changes");
          v20 = PpfTransformStore::DiscardChanges(v8);
          if ( v20 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x30A,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
              (const char *)(unsigned int)v20,
              v28);
          v21 = NotifySubscribers(a2, 3u, *(unsigned __int64 *)&Data, a4);
          if ( v21 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x30C,
              (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
              (const char *)(unsigned int)v21,
              v28);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30D,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
            (const char *)v16,
            v28);
          v30[0] = &PpfTraceLoggingProvider::PpfCommitActivity::`vftable';
          wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v30);
          wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v30);
          PpfTraceLogFormat(
            "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
            0x89u,
            "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
            "Leaving %hs",
            "PpfState::Commit");
          return v16;
        }
      }
    }
    else
    {
      v22 = PpfScheduledTask::EnableTemporarily(v14);
      v16 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x314,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
          (const char *)(unsigned int)v22,
          v28);
        v30[0] = &PpfTraceLoggingProvider::PpfCommitActivity::`vftable';
        wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v30);
        wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v30);
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "PpfState::Commit");
        return v16;
      }
      v16 = NotifySubscribers(a2, a3, *(unsigned __int64 *)&Data, a4);
      if ( (v16 & 0x80000000) != 0 )
      {
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
          0x319u,
          "PpfState::Commit",
          "Subscribers notification failed, discarding changes");
        v23 = PpfTransformStore::DiscardChanges(v8);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x31A,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
            (const char *)(unsigned int)v23,
            v28);
        v24 = NotifySubscribers(a2, 3u, *(unsigned __int64 *)&Data, a4);
        if ( v24 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x31C,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
            (const char *)(unsigned int)v24,
            v28);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x31D,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
          (const char *)v16,
          v28);
        v30[0] = &PpfTraceLoggingProvider::PpfCommitActivity::`vftable';
        wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v30);
        wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v30);
        PpfTraceLogFormat(
          "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
          0x89u,
          "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
          "Leaving %hs",
          "PpfState::Commit");
        return v16;
      }
    }
    v25 = PpfTransformStore::CommitTransforms((PpfTransformStore *)(a1 + 16));
    v16 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x322,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)(unsigned int)v25,
        v28);
      v30[0] = &PpfTraceLoggingProvider::PpfCommitActivity::`vftable';
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v30);
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v30);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfState::Commit");
      return v16;
    }
    v26 = PpfScheduledTask::DisableIfEnabledTemporarily(v14);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x323,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
        (const char *)(unsigned int)v26,
        v28);
      v30[0] = &PpfTraceLoggingProvider::PpfCommitActivity::`vftable';
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v30);
      wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v30);
      PpfTraceLogFormat(
        "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
        0x89u,
        "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
        "Leaving %hs",
        "PpfState::Commit");
      return v27;
    }
    v9 = v29;
  }
  PpfTraceLoggingProvider::PpfCommitActivity::StopActivity((PpfTraceLoggingProvider::PpfCommitActivity *)v30, v9);
  v30[0] = &PpfTraceLoggingProvider::PpfCommitActivity::`vftable';
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v30);
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v30);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "PpfState::Commit");
  return 0;
}

```

## disassembly

```asm
0x18000fec8  push    rbp
0x18000feca  push    rbx
0x18000fecb  push    rsi
0x18000fecc  push    rdi
0x18000fecd  push    r12
0x18000fecf  push    r13
0x18000fed1  push    r14
0x18000fed3  push    r15
0x18000fed5  lea     rbp, [rsp-0A8h]
0x18000fedd  sub     rsp, 1A8h
0x18000fee4  mov     rax, cs:__security_cookie
0x18000feeb  xor     rax, rsp
0x18000feee  mov     [rbp+0E0h+var_50], rax
0x18000fef5  mov     r12, r9
0x18000fef8  mov     r13d, r8d
0x18000fefb  mov     r15d, edx
0x18000fefe  mov     r14, rcx
0x18000ff01  lea     rax, aPpfstateCommit; "PpfState::Commit"
0x18000ff08  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18000ff0d  lea     r9, aEnteringHs; "Entering %hs"
0x18000ff14  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x18000ff1b  mov     edx, 84h; unsigned int
0x18000ff20  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18000ff27  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18000ff2c  lea     rdx, aPpfcommitactiv; "PpfCommitActivity"
0x18000ff33  lea     rcx, [rsp+1E0h+var_1A0]
0x18000ff38  call    ??0?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000ff3d  lea     rax, ??_7PpfCommitActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::PpfCommitActivity::`vftable'
0x18000ff44  mov     [rsp+1E0h+var_1A0], rax
0x18000ff49  lea     rcx, [rsp+1E0h+var_1A0]; this
0x18000ff4e  call    ?StartActivity@PpfCommitActivity@PpfTraceLoggingProvider@@QEAAXXZ; PpfTraceLoggingProvider::PpfCommitActivity::StartActivity(void)
0x18000ff53  lea     rsi, [r14+10h]
0x18000ff57  mov     al, [rsi+60h]
0x18000ff5a  mov     [rsp+1E0h+var_1B0], al
0x18000ff5e  xor     r8d, r8d
0x18000ff61  test    al, al
0x18000ff63  jz      loc_1800104ED
0x18000ff69  mov     rax, cs:qword_180072C10
0x18000ff70  mov     rax, [rax]
0x18000ff73  cmp     [rax+19h], r8b
0x18000ff77  jnz     loc_18001004E
0x18000ff7d  cmp     dword ptr [rax+40h], 2
0x18000ff81  jz      short loc_18000FFC8
0x18000ff83  mov     rdx, [rax+10h]
0x18000ff87  cmp     [rdx+19h], r8b
0x18000ff8b  jz      short loc_18000FFAB
0x18000ff8d  mov     rcx, [rax+8]
0x18000ff91  jmp     short loc_18000FFA0
0x18000ff93  cmp     rax, [rcx+10h]
0x18000ff97  jnz     short loc_18000FFA6
0x18000ff99  mov     rax, rcx
0x18000ff9c  mov     rcx, [rcx+8]
0x18000ffa0  cmp     [rcx+19h], r8b
0x18000ffa4  jz      short loc_18000FF93
0x18000ffa6  mov     rax, rcx
0x18000ffa9  jmp     short loc_18000FF73
0x18000ffab  mov     rax, rdx
0x18000ffae  mov     rdx, [rdx]
0x18000ffb1  cmp     [rdx+19h], r8b
0x18000ffb5  jnz     short loc_18000FF73
0x18000ffb7  mov     rax, rdx
0x18000ffba  mov     rcx, [rdx]
0x18000ffbd  mov     rdx, rcx
0x18000ffc0  cmp     [rcx+19h], r8b
0x18000ffc4  jz      short loc_18000FFB7
0x18000ffc6  jmp     short loc_18000FF73
0x18000ffc8  lea     rbx, [r14+88h]
0x18000ffcf  mov     dl, 1; bool
0x18000ffd1  mov     rcx, rbx; this
0x18000ffd4  call    ?ManageScheduledTask@PpfScheduledTask@@QEAAJ_N@Z; PpfScheduledTask::ManageScheduledTask(bool)
0x18000ffd9  mov     edi, eax
0x18000ffdb  test    eax, eax
0x18000ffdd  jns     short loc_180010055
0x18000ffdf  mov     rcx, [rbp+0E8h]; this
0x18000ffe6  mov     r9d, eax; char *
0x18000ffe9  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18000fff0  mov     edx, 2F5h; void *
0x18000fff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fffa  lea     rax, ??_7PpfCommitActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::PpfCommitActivity::`vftable'
0x180010001  mov     [rsp+1E0h+var_1A0], rax
0x180010006  lea     rcx, [rsp+1E0h+var_1A0]
0x18001000b  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010010  lea     rcx, [rsp+1E0h+var_1A0]
0x180010015  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001001a  nop
0x18001001b  lea     r14, aPpfstateCommit; "PpfState::Commit"
0x180010022  mov     qword ptr [rsp+1E0h+var_1C0], r14
0x180010027  lea     r9, aLeavingHs; "Leaving %hs"
0x18001002e  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180010035  mov     edx, 89h; unsigned int
0x18001003a  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180010041  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180010046  nop
0x180010047  mov     eax, edi
0x180010049  jmp     loc_180010548
0x18001004e  lea     rbx, [r14+88h]
0x180010055  mov     rcx, rsi; this
0x180010058  call    ?Finalize@PpfTransformStore@@QEAAJXZ; PpfTransformStore::Finalize(void)
0x18001005d  mov     edi, eax
0x18001005f  test    eax, eax
0x180010061  jns     short loc_1800100D0
0x180010063  mov     rcx, [rbp+0E8h]; this
0x18001006a  mov     r9d, eax; char *
0x18001006d  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180010074  mov     edx, 2FBh; void *
0x180010079  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001007e  lea     rax, ??_7PpfCommitActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::PpfCommitActivity::`vftable'
0x180010085  mov     [rsp+1E0h+var_1A0], rax
0x18001008a  lea     rcx, [rsp+1E0h+var_1A0]
0x18001008f  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010094  lea     rcx, [rsp+1E0h+var_1A0]
0x180010099  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001009e  nop
0x18001009f  lea     r14, aPpfstateCommit; "PpfState::Commit"
0x1800100a6  mov     qword ptr [rsp+1E0h+var_1C0], r14
0x1800100ab  lea     r9, aLeavingHs; "Leaving %hs"
0x1800100b2  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800100b9  mov     edx, 89h; unsigned int
0x1800100be  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800100c5  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800100ca  nop
0x1800100cb  jmp     loc_180010047
0x1800100d0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x1800100d7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x1800100dc  test    al, al
0x1800100de  jz      loc_180010275
0x1800100e4  cmp     cs:qword_180072C40, 0
0x1800100ec  jnz     loc_1800103F4
0x1800100f2  lea     rcx, [r14+88h]; this
0x1800100f9  call    ?EnableTemporarily@PpfScheduledTask@@QEAAJXZ; PpfScheduledTask::EnableTemporarily(void)
0x1800100fe  mov     edi, eax
0x180010100  test    eax, eax
0x180010102  jns     short loc_180010171
0x180010104  mov     rcx, [rbp+0E8h]; this
0x18001010b  mov     r9d, eax; char *
0x18001010e  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180010115  mov     edx, 304h; void *
0x18001011a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001011f  lea     rax, ??_7PpfCommitActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::PpfCommitActivity::`vftable'
0x180010126  mov     [rsp+1E0h+var_1A0], rax
0x18001012b  lea     rcx, [rsp+1E0h+var_1A0]
0x180010130  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010135  lea     rcx, [rsp+1E0h+var_1A0]
0x18001013a  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001013f  nop
0x180010140  lea     r14, aPpfstateCommit; "PpfState::Commit"
0x180010147  mov     qword ptr [rsp+1E0h+var_1C0], r14
0x18001014c  lea     r9, aLeavingHs; "Leaving %hs"
0x180010153  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001015a  mov     edx, 89h; unsigned int
0x18001015f  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180010166  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001016b  nop
0x18001016c  jmp     loc_180010047
0x180010171  mov     r9, r12
0x180010174  mov     r8, cs:Data
0x18001017b  mov     edx, r13d
0x18001017e  mov     ecx, r15d
0x180010181  call    ?NotifySubscribers@@YAJIW4PPF_SUBSCRIBER_NOTIFICATION_SCENARIO@@_KPEBG@Z; NotifySubscribers(uint,PPF_SUBSCRIBER_NOTIFICATION_SCENARIO,unsigned __int64,ushort const *)
0x180010186  mov     edi, eax
0x180010188  test    eax, eax
0x18001018a  jns     loc_1800103F4
0x180010190  lea     r9, aSubscribersNot; "Subscribers notification failed, discar"...
0x180010197  lea     r14, aPpfstateCommit; "PpfState::Commit"
0x18001019e  mov     r8, r14; char *
0x1800101a1  mov     edx, 309h; unsigned int
0x1800101a6  lea     rcx, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800101ad  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800101b2  mov     rcx, rsi; this
0x1800101b5  call    ?DiscardChanges@PpfTransformStore@@QEAAJXZ; PpfTransformStore::DiscardChanges(void)
0x1800101ba  mov     rcx, [rbp+0E8h]; this
0x1800101c1  test    eax, eax
0x1800101c3  jns     short loc_1800101D9
0x1800101c5  mov     r9d, eax; char *
0x1800101c8  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800101cf  mov     edx, 30Ah; void *
0x1800101d4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800101d9  mov     r9, r12
0x1800101dc  mov     r8, cs:Data
0x1800101e3  mov     edx, 3
0x1800101e8  mov     ecx, r15d
0x1800101eb  call    ?NotifySubscribers@@YAJIW4PPF_SUBSCRIBER_NOTIFICATION_SCENARIO@@_KPEBG@Z; NotifySubscribers(uint,PPF_SUBSCRIBER_NOTIFICATION_SCENARIO,unsigned __int64,ushort const *)
0x1800101f0  mov     rcx, [rbp+0E8h]; this
0x1800101f7  test    eax, eax
0x1800101f9  jns     short loc_18001020F
0x1800101fb  mov     r9d, eax; char *
0x1800101fe  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180010205  mov     edx, 30Ch; void *
0x18001020a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001020f  mov     rcx, [rbp+0E8h]; this
0x180010216  mov     r9d, edi; char *
0x180010219  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180010220  mov     edx, 30Dh; void *
0x180010225  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001022a  lea     rax, ??_7PpfCommitActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::PpfCommitActivity::`vftable'
0x180010231  mov     [rsp+1E0h+var_1A0], rax
0x180010236  lea     rcx, [rsp+1E0h+var_1A0]
0x18001023b  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180010240  lea     rcx, [rsp+1E0h+var_1A0]
0x180010245  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001024a  nop
0x18001024b  mov     qword ptr [rsp+1E0h+var_1C0], r14
0x180010250  lea     r9, aLeavingHs; "Leaving %hs"
0x180010257  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18001025e  mov     edx, 89h; unsigned int
0x180010263  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18001026a  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18001026f  nop
0x180010270  jmp     loc_180010047
0x180010275  mov     rcx, rbx; this
0x180010278  call    ?EnableTemporarily@PpfScheduledTask@@QEAAJXZ; PpfScheduledTask::EnableTemporarily(void)
0x18001027d  mov     edi, eax
0x18001027f  test    eax, eax
0x180010281  jns     short loc_1800102F0
0x180010283  mov     rcx, [rbp+0E8h]; this
0x18001028a  mov     r9d, eax; char *
0x18001028d  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180010294  mov     edx, 314h; void *
0x180010299  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001029e  lea     rax, ??_7PpfCommitActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::PpfCommitActivity::`vftable'
0x1800102a5  mov     [rsp+1E0h+var_1A0], rax
0x1800102aa  lea     rcx, [rsp+1E0h+var_1A0]
0x1800102af  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800102b4  lea     rcx, [rsp+1E0h+var_1A0]
0x1800102b9  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800102be  nop
0x1800102bf  lea     r14, aPpfstateCommit; "PpfState::Commit"
0x1800102c6  mov     qword ptr [rsp+1E0h+var_1C0], r14
0x1800102cb  lea     r9, aLeavingHs; "Leaving %hs"
0x1800102d2  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800102d9  mov     edx, 89h; unsigned int
0x1800102de  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800102e5  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800102ea  nop
0x1800102eb  jmp     loc_180010047
0x1800102f0  mov     r9, r12
0x1800102f3  mov     r8, cs:Data
0x1800102fa  mov     edx, r13d
0x1800102fd  mov     ecx, r15d
0x180010300  call    ?NotifySubscribers@@YAJIW4PPF_SUBSCRIBER_NOTIFICATION_SCENARIO@@_KPEBG@Z; NotifySubscribers(uint,PPF_SUBSCRIBER_NOTIFICATION_SCENARIO,unsigned __int64,ushort const *)
0x180010305  mov     edi, eax
0x180010307  test    eax, eax
0x180010309  jns     loc_1800103F4
0x18001030f  lea     r9, aSubscribersNot; "Subscribers notification failed, discar"...
0x180010316  lea     r14, aPpfstateCommit; "PpfState::Commit"
0x18001031d  mov     r8, r14; char *
0x180010320  mov     edx, 319h; unsigned int
0x180010325  lea     rcx, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001032c  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180010331  mov     rcx, rsi; this
0x180010334  call    ?DiscardChanges@PpfTransformStore@@QEAAJXZ; PpfTransformStore::DiscardChanges(void)
0x180010339  mov     rcx, [rbp+0E8h]; this
0x180010340  test    eax, eax
0x180010342  jns     short loc_180010358
0x180010344  mov     r9d, eax; char *
0x180010347  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001034e  mov     edx, 31Ah; void *
0x180010353  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010358  mov     r9, r12
0x18001035b  mov     r8, cs:Data
0x180010362  mov     edx, 3
0x180010367  mov     ecx, r15d
0x18001036a  call    ?NotifySubscribers@@YAJIW4PPF_SUBSCRIBER_NOTIFICATION_SCENARIO@@_KPEBG@Z; NotifySubscribers(uint,PPF_SUBSCRIBER_NOTIFICATION_SCENARIO,unsigned __int64,ushort const *)
0x18001036f  mov     rcx, [rbp+0E8h]; this
0x180010376  test    eax, eax
0x180010378  jns     short loc_18001038E
0x18001037a  mov     r9d, eax; char *
0x18001037d  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180010384  mov     edx, 31Ch; void *
0x180010389  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001038e  mov     rcx, [rbp+0E8h]; this
0x180010395  mov     r9d, edi; char *
0x180010398  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18001039f  mov     edx, 31Dh; void *
0x1800103a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103a9  lea     rax, ??_7PpfCommitActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::PpfCommitActivity::`vftable'
0x1800103b0  mov     [rsp+1E0h+var_1A0], rax
0x1800103b5  lea     rcx, [rsp+1E0h+var_1A0]
0x1800103ba  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800103bf  lea     rcx, [rsp+1E0h+var_1A0]
0x1800103c4  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800103c9  nop
0x1800103ca  mov     qword ptr [rsp+1E0h+var_1C0], r14
0x1800103cf  lea     r9, aLeavingHs; "Leaving %hs"
0x1800103d6  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800103dd  mov     edx, 89h; unsigned int
0x1800103e2  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800103e9  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800103ee  nop
0x1800103ef  jmp     loc_180010047
0x1800103f4  mov     rcx, rsi; this
0x1800103f7  call    ?CommitTransforms@PpfTransformStore@@QEAAJXZ; PpfTransformStore::CommitTransforms(void)
0x1800103fc  mov     edi, eax
0x1800103fe  test    eax, eax
0x180010400  jns     short loc_18001046F
0x180010402  mov     rcx, [rbp+0E8h]; this
0x180010409  mov     r9d, eax; char *
0x18001040c  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x180010413  mov     edx, 322h; void *
0x180010418  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
