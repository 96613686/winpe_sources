# CleanupBitLockerReducedPcrProfileInt(void)

- ea: `0x180052728`
- end: `0x180052a4c`
- name: `?CleanupBitLockerReducedPcrProfileInt@@YAJXZ`
- size: `804`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x18001b030`
- `0x18004fe98`

## callees

- `0x180003270`
- `0x180009c64`
- `0x18000c458`
- `0x18000c5cc`
- `0x18000ca1c`
- `0x18000dfe0`
- `0x18000e260`
- `0x18001b5a0`
- `0x18001c0a0`
- `0x18002d5ec`
- `0x1800334d0`
- `0x180033ae4`
- `0x180052134`
- `0x180052728`
- `0x180053970`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800529a9`
- `ntdll!EtwEventWrite` at `0x1800529a9`

## string_xrefs

- `0x1800527d1`: `onecore\base\ngscb\pcrpf\dll\pcrpfcpp.h`
- `0x180052814`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x18005288d`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x1800528b5`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052934`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x18005287e`: `Excluded PCRs cleanup already done in this boot session`

## pseudocode

```c
__int64 CleanupBitLockerReducedPcrProfileInt(void)
{
  int v0; // eax
  char v1; // bl
  int VolatileRegBoolean; // eax
  unsigned int v3; // edi
  int v5; // eax
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // [rsp+20h] [rbp-E0h]
  bool v9; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  char v11; // [rsp+40h] [rbp-C0h]
  const char *v12; // [rsp+48h] [rbp-B8h]
  _QWORD v13[42]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v12 = "CleanupBitLockerReducedPcrProfileInt";
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "CleanupBitLockerReducedPcrProfileInt");
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v13,
    "CleanupBitLockerReducedPcrProfileActivity");
  v13[0] = &PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity::`vftable';
  PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity::StartActivity((PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity *)v13);
  v10 = 0;
  v11 = 0;
  v0 = PpfLock(&v10);
  if ( v0 >= 0 )
  {
    v1 = 1;
    v11 = 1;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpfcpp.h",
      (const char *)(unsigned int)v0,
      v8);
    v1 = v11;
  }
  v9 = 0;
  VolatileRegBoolean = PpfhGetVolatileRegBoolean(L"ExcludedPcrsResealCleanupDone", &v9);
  v3 = VolatileRegBoolean;
  if ( VolatileRegBoolean < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)(unsigned int)VolatileRegBoolean,
      v8);
    if ( v1 )
      PpfUnlock(&v10);
LABEL_7:
    v13[0] = &PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity::`vftable';
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v13);
    wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v13);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "CleanupBitLockerReducedPcrProfileInt");
    return v3;
  }
  if ( v9 )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      0x15Bu,
      "CleanupBitLockerReducedPcrProfileInt",
      "Excluded PCRs cleanup already done in this boot session");
  }
  else
  {
    v5 = CleanupBitLockerReducedPcrProfileHelper(0);
    v3 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
        (const char *)(unsigned int)v5,
        v8);
      if ( v1 )
        PpfUnlock(&v10);
      goto LABEL_7;
    }
    v6 = PpfhSetVolatileRegBoolean(L"ExcludedPcrsResealCleanupDone", 0);
    v3 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x160,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
        (const char *)(unsigned int)v6,
        v8);
      if ( v1 )
        PpfUnlock(&v10);
      goto LABEL_7;
    }
    v7 = EtwEventWrite(g_eventProvider, PCRPF_EVENT_FIRMWARE_UPDATE_FVE_RPCRP_CLEANUP, 0, 0);
    if ( v7 )
      wil::details::in1diag3::Return_Win32(
        retaddr,
        (void *)0x1AE,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\eventlog.cpp",
        (const char *)v7,
        v8);
  }
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v13);
  if ( v1 )
    PpfUnlock(&v10);
  v13[0] = &PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity::`vftable';
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v13);
  wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v13);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "CleanupBitLockerReducedPcrProfileInt");
  return 0;
}

```

## disassembly

```asm
0x180052728  push    rbp
0x18005272a  push    rbx
0x18005272b  push    rdi
0x18005272c  push    r12
0x18005272e  push    r14
0x180052730  push    r15
0x180052732  lea     rbp, [rsp-0B8h]
0x18005273a  sub     rsp, 1B8h
0x180052741  mov     rax, cs:__security_cookie
0x180052748  xor     rax, rsp
0x18005274b  mov     [rbp+0E0h+var_40], rax
0x180052752  lea     r14, aCleanupbitlock_3; "CleanupBitLockerReducedPcrProfileInt"
0x180052759  mov     [rsp+1E0h+var_198], r14
0x18005275e  mov     qword ptr [rsp+1E0h+var_1C0], r14; unsigned int
0x180052763  lea     r9, aEnteringHs; "Entering %hs"
0x18005276a  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x180052771  mov     edx, 84h; unsigned int
0x180052776  lea     r15, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18005277d  mov     rcx, r15; char *
0x180052780  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180052785  nop
0x180052786  lea     rdx, aCleanupbitlock_2; "CleanupBitLockerReducedPcrProfileActivi"...
0x18005278d  lea     rcx, [rsp+1E0h+var_190]
0x180052792  call    ??0?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180052797  lea     r12, ??_7CleanupBitLockerReducedPcrProfileActivity@PpfTraceLoggingProvider@@6B@; const PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity::`vftable'
0x18005279e  mov     [rsp+1E0h+var_190], r12
0x1800527a3  lea     rcx, [rsp+1E0h+var_190]; this
0x1800527a8  call    ?StartActivity@CleanupBitLockerReducedPcrProfileActivity@PpfTraceLoggingProvider@@QEAAXXZ; PpfTraceLoggingProvider::CleanupBitLockerReducedPcrProfileActivity::StartActivity(void)
0x1800527ad  nop
0x1800527ae  xor     eax, eax
0x1800527b0  mov     [rsp+1E0h+var_1A8], rax
0x1800527b5  mov     [rsp+1E0h+var_1A0], al
0x1800527b9  lea     rcx, [rsp+1E0h+var_1A8]
0x1800527be  call    PpfLock
0x1800527c3  test    eax, eax
0x1800527c5  jns     short loc_1800527E8
0x1800527c7  mov     rcx, [rbp+0E8h]; this
0x1800527ce  mov     r9d, eax; char *
0x1800527d1  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800527d8  mov     edx, 11h; void *
0x1800527dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800527e2  mov     bl, [rsp+1E0h+var_1A0]
0x1800527e6  jmp     short loc_1800527EE
0x1800527e8  mov     bl, 1
0x1800527ea  mov     [rsp+1E0h+var_1A0], bl
0x1800527ee  mov     [rsp+1E0h+var_1B0], 0
0x1800527f3  lea     rdx, [rsp+1E0h+var_1B0]; bool *
0x1800527f8  lea     rcx, aExcludedpcrsre; "ExcludedPcrsResealCleanupDone"
0x1800527ff  call    ?PpfhGetVolatileRegBoolean@@YAJPEBGPEA_N@Z; PpfhGetVolatileRegBoolean(ushort const *,bool *)
0x180052804  mov     edi, eax
0x180052806  test    eax, eax
0x180052808  jns     short loc_180052877
0x18005280a  mov     rcx, [rbp+0E8h]; this
0x180052811  mov     r9d, eax; char *
0x180052814  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005281b  mov     edx, 158h; void *
0x180052820  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052825  nop
0x180052826  test    bl, bl
0x180052828  jz      short loc_180052835
0x18005282a  lea     rcx, [rsp+1E0h+var_1A8]
0x18005282f  call    PpfUnlock
0x180052834  nop
0x180052835  mov     [rsp+1E0h+var_190], r12
0x18005283a  lea     rcx, [rsp+1E0h+var_190]
0x18005283f  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180052844  lea     rcx, [rsp+1E0h+var_190]
0x180052849  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18005284e  nop
0x18005284f  mov     qword ptr [rsp+1E0h+var_1C0], r14
0x180052854  lea     r9, aLeavingHs; "Leaving %hs"
0x18005285b  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180052862  mov     edx, 89h; unsigned int
0x180052867  mov     rcx, r15; char *
0x18005286a  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18005286f  nop
0x180052870  mov     eax, edi
0x180052872  jmp     loc_180052A2B
0x180052877  cmp     [rsp+1E0h+var_1B0], 0
0x18005287c  jz      short loc_18005289E
0x18005287e  lea     r9, aExcludedPcrsCl; "Excluded PCRs cleanup already done in t"...
0x180052885  mov     r8, r14; char *
0x180052888  mov     edx, 15Bh; unsigned int
0x18005288d  lea     rcx, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052894  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180052899  jmp     loc_1800529D4
0x18005289e  xor     ecx, ecx
0x1800528a0  call    CleanupBitLockerReducedPcrProfileHelper
0x1800528a5  mov     edi, eax
0x1800528a7  test    eax, eax
0x1800528a9  jns     short loc_180052916
0x1800528ab  mov     rcx, [rbp+0E8h]; this
0x1800528b2  mov     r9d, eax; char *
0x1800528b5  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x1800528bc  mov     edx, 15Fh; void *
0x1800528c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800528c6  nop
0x1800528c7  test    bl, bl
0x1800528c9  jz      short loc_1800528D6
0x1800528cb  lea     rcx, [rsp+1E0h+var_1A8]
0x1800528d0  call    PpfUnlock
0x1800528d5  nop
0x1800528d6  mov     [rsp+1E0h+var_190], r12
0x1800528db  lea     rcx, [rsp+1E0h+var_190]
0x1800528e0  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800528e5  lea     rcx, [rsp+1E0h+var_190]
0x1800528ea  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800528ef  nop
0x1800528f0  mov     qword ptr [rsp+1E0h+var_1C0], r14
0x1800528f5  lea     r9, aLeavingHs; "Leaving %hs"
0x1800528fc  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180052903  mov     edx, 89h; unsigned int
0x180052908  mov     rcx, r15; char *
0x18005290b  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180052910  nop
0x180052911  jmp     loc_180052870
0x180052916  xor     edx, edx; hTransaction
0x180052918  lea     rcx, aExcludedpcrsre; "ExcludedPcrsResealCleanupDone"
0x18005291f  call    ?PpfhSetVolatileRegBoolean@@YAJPEBGPEAX@Z; PpfhSetVolatileRegBoolean(ushort const *,void *)
0x180052924  mov     edi, eax
0x180052926  test    eax, eax
0x180052928  jns     short loc_180052995
0x18005292a  mov     rcx, [rbp+0E8h]; this
0x180052931  mov     r9d, eax; char *
0x180052934  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005293b  mov     edx, 160h; void *
0x180052940  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052945  nop
0x180052946  test    bl, bl
0x180052948  jz      short loc_180052955
0x18005294a  lea     rcx, [rsp+1E0h+var_1A8]
0x18005294f  call    PpfUnlock
0x180052954  nop
0x180052955  mov     [rsp+1E0h+var_190], r12
0x18005295a  lea     rcx, [rsp+1E0h+var_190]
0x18005295f  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180052964  lea     rcx, [rsp+1E0h+var_190]
0x180052969  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x18005296e  nop
0x18005296f  mov     qword ptr [rsp+1E0h+var_1C0], r14
0x180052974  lea     r9, aLeavingHs; "Leaving %hs"
0x18005297b  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180052982  mov     edx, 89h; unsigned int
0x180052987  mov     rcx, r15; char *
0x18005298a  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18005298f  nop
0x180052990  jmp     loc_180052870
0x180052995  xor     r9d, r9d
0x180052998  xor     r8d, r8d
0x18005299b  lea     rdx, PCRPF_EVENT_FIRMWARE_UPDATE_FVE_RPCRP_CLEANUP
0x1800529a2  mov     rcx, cs:?g_eventProvider@@3_KA; unsigned __int64 g_eventProvider
0x1800529a9  call    cs:__imp_EtwEventWrite
0x1800529b0  nop     dword ptr [rax+rax+00h]
0x1800529b5  test    eax, eax
0x1800529b7  jz      short loc_1800529D4
0x1800529b9  mov     rcx, [rbp+0E8h]; this
0x1800529c0  mov     r9d, eax; char *
0x1800529c3  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800529ca  mov     edx, 1AEh; void *
0x1800529cf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800529d4  lea     rcx, [rsp+1E0h+var_190]
0x1800529d9  call    ?Stop@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800529de  nop
0x1800529df  test    bl, bl
0x1800529e1  jz      short loc_1800529EE
0x1800529e3  lea     rcx, [rsp+1E0h+var_1A8]
0x1800529e8  call    PpfUnlock
0x1800529ed  nop
0x1800529ee  mov     [rsp+1E0h+var_190], r12
0x1800529f3  lea     rcx, [rsp+1E0h+var_190]
0x1800529f8  call    ?Destroy@?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800529fd  lea     rcx, [rsp+1E0h+var_190]
0x180052a02  call    ??1?$ActivityBase@VPpfTraceLoggingProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<PpfTraceLoggingProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180052a07  nop
0x180052a08  mov     qword ptr [rsp+1E0h+var_1C0], r14
0x180052a0d  lea     r9, aLeavingHs; "Leaving %hs"
0x180052a14  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180052a1b  mov     edx, 89h; unsigned int
0x180052a20  mov     rcx, r15; char *
0x180052a23  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180052a28  nop
0x180052a29  xor     eax, eax
0x180052a2b  mov     rcx, [rbp+0E0h+var_40]
0x180052a32  xor     rcx, rsp; StackCookie
0x180052a35  call    __security_check_cookie
0x180052a3a  add     rsp, 1B8h
0x180052a41  pop     r15
0x180052a43  pop     r14
0x180052a45  pop     r12
0x180052a47  pop     rdi
0x180052a48  pop     rbx
0x180052a49  pop     rbp
0x180052a4a  retn
```
