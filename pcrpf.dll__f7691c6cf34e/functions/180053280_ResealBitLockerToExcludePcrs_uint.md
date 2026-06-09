# ResealBitLockerToExcludePcrs(uint)

- ea: `0x180053280`
- end: `0x180053891`
- name: `?ResealBitLockerToExcludePcrs@@YAJI@Z`
- size: `1553`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18004fe98`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x18001b5a0`
- `0x18001c0a0`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x18003beec`
- `0x18003fcac`
- `0x180052134`
- `0x180053010`
- `0x180053280`
- `0x180053ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053444`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005351e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800536be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005378f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053810`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053444`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005351e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053687`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800536be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005378f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053810`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800534e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005363b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800534e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005363b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800535c8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800535c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005340c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005340c`

## string_xrefs

- `0x1800532ee`: `onecore\base\ngscb\pcrpf\dll\pcrpfcpp.h`
- `0x180053370`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180053427`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180053501`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x1800536a2`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180053773`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180053332`: `BitLocker Reduced PCR Profile Cleanup Task`

## pseudocode

```c
// Hidden C++ exception states: #wind=54
__int64 __fastcall ResealBitLockerToExcludePcrs(int a1)
{
  int v1; // eax
  char v2; // di
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  LSTATUS v8; // eax
  __int64 v9; // r8
  LSTATUS v10; // eax
  __int64 v11; // r8
  int v12; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v18; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  char v20; // [rsp+68h] [rbp-98h]
  HKEY v21; // [rsp+70h] [rbp-90h] BYREF
  int v22; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v23; // [rsp+80h] [rbp-80h]
  const wchar_t *v24; // [rsp+88h] [rbp-78h]
  BYTE v25[8]; // [rsp+90h] [rbp-70h] BYREF
  const char *v26; // [rsp+98h] [rbp-68h]
  char *v27; // [rsp+A0h] [rbp-60h]
  char *v28; // [rsp+A8h] [rbp-58h]
  char v29; // [rsp+B0h] [rbp-50h]
  _BYTE v30[8]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v31[20]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]
  int v33; // [rsp+170h] [rbp+70h] BYREF
  char v34; // [rsp+178h] [rbp+78h] BYREF
  char v35; // [rsp+180h] [rbp+80h] BYREF
  int Data; // [rsp+188h] [rbp+88h] BYREF

  v33 = a1;
  v26 = "ResealBitLockerToExcludePcrs";
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "ResealBitLockerToExcludePcrs");
  v19 = 0;
  v20 = 0;
  v1 = PpfLock(&v19);
  if ( v1 >= 0 )
  {
    v2 = 1;
    v20 = 1;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpfcpp.h",
      (const char *)(unsigned int)v1,
      phkResult);
    v2 = v20;
  }
  v35 = 0;
  v34 = 0;
  v27 = &v34;
  v28 = &v35;
  v29 = 1;
  v22 = 0;
  v23 = L"BitLocker Reduced PCR Profile Cleanup Task";
  v24 = L"CleanupBitLockerReducedPcrProfile";
  PpfScheduledTask::ManageScheduledTask((PpfScheduledTask *)&v22, 1u);
  hKey = 0;
  v3 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)&hKey);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x122,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)(unsigned int)v3,
      phkResult);
    PpfSystemCcsKey::~PpfSystemCcsKey(&hKey);
    PpfScheduledTask::~PpfScheduledTask((PpfScheduledTask *)&v22);
    if ( !v34 )
      CleanupBitLockerReducedPcrProfileHelper(v35 == 0);
    if ( v2 )
      PpfUnlock(&v19);
LABEL_9:
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "ResealBitLockerToExcludePcrs");
    return v4;
  }
  v18 = 0;
  v6 = RegOpenKeyExW(hKey, L"Control\\PCRPF", 0, 2u, &v18);
  if ( v6 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x124,
           (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
           (const char *)v6,
           phkResulta);
    if ( v18 )
      RegCloseKey(v18);
    PpfSystemCcsKey::~PpfSystemCcsKey(&hKey);
    PpfScheduledTask::~PpfScheduledTask((PpfScheduledTask *)&v22);
    if ( !v34 )
      CleanupBitLockerReducedPcrProfileHelper(v35 == 0);
    if ( v2 )
      PpfUnlock(&v19);
    goto LABEL_9;
  }
  Data = 1;
  v7 = RegSetValueExW(v18, L"ExcludedPcrsResealNeeded", 0, 4u, (const BYTE *)&Data, 4u);
  if ( v7 )
  {
    v4 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x127,
           (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
           (const char *)v7,
           phkResultb);
    if ( v18 )
      RegCloseKey(v18);
    PpfSystemCcsKey::~PpfSystemCcsKey(&hKey);
    PpfScheduledTask::~PpfScheduledTask((PpfScheduledTask *)&v22);
    if ( !v34 )
      CleanupBitLockerReducedPcrProfileHelper(v35 == 0);
    if ( v2 )
      PpfUnlock(&v19);
    goto LABEL_9;
  }
  *(_DWORD *)v25 = v33;
  v21 = 0;
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\BitLocker", 0, 0, 0, 2u, 0, &v21, 0);
  v4 = v8;
  if ( v8 > 0 )
    v4 = (unsigned __int16)v8 | 0x80070000;
  if ( !v4 )
    goto LABEL_33;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 305, v9, v4);
  if ( (v4 & 0x80000000) == 0 )
  {
LABEL_33:
    v10 = RegSetValueExW(v21, L"ExcludedPcrsBitmap", 0, 4u, v25, 4u);
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
    if ( v4
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 306, v11, v4);
    }
  }
  if ( v21 )
    RegCloseKey(v21);
  if ( (v4 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12A,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)v4,
      phkResultc);
    if ( v18 )
      RegCloseKey(v18);
    PpfSystemCcsKey::~PpfSystemCcsKey(&hKey);
    PpfScheduledTask::~PpfScheduledTask((PpfScheduledTask *)&v22);
    if ( !v34 )
      CleanupBitLockerReducedPcrProfileHelper(v35 == 0);
    if ( v2 )
      PpfUnlock(&v19);
    goto LABEL_9;
  }
  v31[0] = off_18005A498;
  v31[1] = &v33;
  v31[2] = &v35;
  v31[13] = v31;
  v12 = IterateBitLockerVolumesAndDoAction(0, v30);
  v4 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)(unsigned int)v12,
      phkResultc);
    if ( v18 )
      RegCloseKey(v18);
    PpfSystemCcsKey::~PpfSystemCcsKey(&hKey);
    PpfScheduledTask::~PpfScheduledTask((PpfScheduledTask *)&v22);
    if ( !v34 )
      CleanupBitLockerReducedPcrProfileHelper(v35 == 0);
    if ( v2 )
      PpfUnlock(&v19);
    goto LABEL_9;
  }
  v34 = 1;
  if ( v18 )
    RegCloseKey(v18);
  PpfSystemCcsKey::~PpfSystemCcsKey(&hKey);
  PpfScheduledTask::~PpfScheduledTask((PpfScheduledTask *)&v22);
  if ( !v34 )
    CleanupBitLockerReducedPcrProfileHelper(v35 == 0);
  if ( v2 )
    PpfUnlock(&v19);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "ResealBitLockerToExcludePcrs");
  return 0;
}

```

## disassembly

```asm
0x180053280  mov     [rsp-8+arg_0], ecx
0x180053284  push    rbp
0x180053285  push    rbx
0x180053286  push    rsi
0x180053287  push    rdi
0x180053288  push    r13
0x18005328a  push    r15
0x18005328c  lea     rbp, [rsp-38h]
0x180053291  sub     rsp, 138h
0x180053298  lea     r13, aResealbitlocke; "ResealBitLockerToExcludePcrs"
0x18005329f  mov     [rbp+60h+var_C8], r13
0x1800532a3  mov     [rsp+160h+phkResult], r13; int
0x1800532a8  lea     r9, aEnteringHs; "Entering %hs"
0x1800532af  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x1800532b6  mov     edx, 84h; unsigned int
0x1800532bb  lea     r15, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x1800532c2  mov     rcx, r15; char *
0x1800532c5  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800532ca  nop
0x1800532cb  xor     eax, eax
0x1800532cd  mov     [rsp+160h+var_100], rax
0x1800532d2  xor     esi, esi
0x1800532d4  mov     [rsp+160h+var_F8], sil
0x1800532d9  lea     rcx, [rsp+160h+var_100]
0x1800532de  call    PpfLock
0x1800532e3  test    eax, eax
0x1800532e5  jns     short loc_180053304
0x1800532e7  mov     rcx, [rbp+68h]; this
0x1800532eb  mov     r9d, eax; char *
0x1800532ee  lea     r8, aOnecoreBaseNgs_10; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800532f5  lea     edx, [rsi+11h]; void *
0x1800532f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800532fd  mov     dil, [rsp+160h+var_F8]
0x180053302  jmp     short loc_18005330C
0x180053304  mov     dil, 1
0x180053307  mov     [rsp+160h+var_F8], dil
0x18005330c  mov     [rbp+60h+arg_10], sil
0x180053313  mov     [rbp+60h+arg_8], sil
0x180053317  lea     rax, [rbp+60h+arg_8]
0x18005331b  mov     [rbp+60h+var_C0], rax
0x18005331f  lea     rax, [rbp+60h+arg_10]
0x180053326  mov     [rbp+60h+var_B8], rax
0x18005332a  mov     [rbp+60h+var_B0], 1
0x18005332e  mov     [rsp+160h+var_E8], esi
0x180053332  lea     rax, aBitlockerReduc_0; "BitLocker Reduced PCR Profile Cleanup T"...
0x180053339  mov     [rbp+60h+var_E0], rax
0x18005333d  lea     rax, aCleanupbitlock_1; "CleanupBitLockerReducedPcrProfile"
0x180053344  mov     [rbp+60h+var_D8], rax
0x180053348  mov     dl, 1; bool
0x18005334a  lea     rcx, [rsp+160h+var_E8]; this
0x18005334f  call    ?ManageScheduledTask@PpfScheduledTask@@QEAAJ_N@Z; PpfScheduledTask::ManageScheduledTask(bool)
0x180053354  mov     [rsp+160h+hKey], rsi
0x180053359  lea     rcx, [rsp+160h+hKey]; this
0x18005335e  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x180053363  mov     ebx, eax
0x180053365  test    eax, eax
0x180053367  jns     short loc_1800533E6
0x180053369  mov     rcx, [rbp+68h]; this
0x18005336d  mov     r9d, eax; char *
0x180053370  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180053377  mov     edx, 122h; void *
0x18005337c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053381  nop
0x180053382  lea     rcx, [rsp+160h+hKey]; this
0x180053387  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x18005338c  nop
0x18005338d  lea     rcx, [rsp+160h+var_E8]; this
0x180053392  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x180053397  nop
0x180053398  cmp     [rbp+60h+arg_8], sil
0x18005339c  jnz     short loc_1800533AE
0x18005339e  cmp     [rbp+60h+arg_10], sil
0x1800533a5  setz    cl
0x1800533a8  call    CleanupBitLockerReducedPcrProfileHelper
0x1800533ad  nop
0x1800533ae  test    dil, dil
0x1800533b1  jz      short loc_1800533BE
0x1800533b3  lea     rcx, [rsp+160h+var_100]
0x1800533b8  call    PpfUnlock
0x1800533bd  nop
0x1800533be  mov     [rsp+160h+phkResult], r13
0x1800533c3  lea     r9, aLeavingHs; "Leaving %hs"
0x1800533ca  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800533d1  mov     edx, 89h; unsigned int
0x1800533d6  mov     rcx, r15; char *
0x1800533d9  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800533de  nop
0x1800533df  mov     eax, ebx
0x1800533e1  jmp     loc_180053880
0x1800533e6  mov     [rsp+160h+var_108], rsi
0x1800533eb  lea     rax, [rsp+160h+var_108]
0x1800533f0  mov     [rsp+160h+phkResult], rax; unsigned int
0x1800533f5  mov     ebx, 2
0x1800533fa  mov     r9d, ebx; samDesired
0x1800533fd  xor     r8d, r8d; ulOptions
0x180053400  lea     rdx, aControlPcrpf; "Control\\PCRPF"
0x180053407  mov     rcx, [rsp+160h+hKey]; hKey
0x18005340c  call    cs:__imp_RegOpenKeyExW
0x180053413  nop     dword ptr [rax+rax+00h]
0x180053418  test    eax, eax
0x18005341a  jz      loc_1800534B3
0x180053420  mov     rcx, [rbp+68h]; this
0x180053424  mov     r9d, eax; char *
0x180053427  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005342e  mov     edx, 124h; void *
0x180053433  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180053438  mov     ebx, eax
0x18005343a  mov     rcx, [rsp+160h+var_108]; hKey
0x18005343f  test    rcx, rcx
0x180053442  jz      short loc_180053451
0x180053444  call    cs:__imp_RegCloseKey
0x18005344b  nop     dword ptr [rax+rax+00h]
0x180053450  nop
0x180053451  lea     rcx, [rsp+160h+hKey]; this
0x180053456  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x18005345b  nop
0x18005345c  lea     rcx, [rsp+160h+var_E8]; this
0x180053461  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x180053466  nop
0x180053467  cmp     [rbp+60h+arg_8], sil
0x18005346b  jnz     short loc_18005347D
0x18005346d  cmp     [rbp+60h+arg_10], sil
0x180053474  setz    cl
0x180053477  call    CleanupBitLockerReducedPcrProfileHelper
0x18005347c  nop
0x18005347d  test    dil, dil
0x180053480  jz      short loc_18005348D
0x180053482  lea     rcx, [rsp+160h+var_100]
0x180053487  call    PpfUnlock
0x18005348c  nop
0x18005348d  mov     [rsp+160h+phkResult], r13
0x180053492  lea     r9, aLeavingHs; "Leaving %hs"
0x180053499  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800534a0  mov     edx, 89h; unsigned int
0x1800534a5  mov     rcx, r15; char *
0x1800534a8  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800534ad  nop
0x1800534ae  jmp     loc_1800533DF
0x1800534b3  mov     [rbp+60h+Data], 1
0x1800534bd  mov     [rsp+160h+cbData], 4; cbData
0x1800534c5  lea     rax, [rbp+60h+Data]
0x1800534cc  mov     [rsp+160h+phkResult], rax; unsigned int
0x1800534d1  mov     r9d, 4; dwType
0x1800534d7  xor     r8d, r8d; Reserved
0x1800534da  lea     rdx, aExcludedpcrsre_0; "ExcludedPcrsResealNeeded"
0x1800534e1  mov     rcx, [rsp+160h+var_108]; hKey
0x1800534e6  call    cs:__imp_RegSetValueExW
0x1800534ed  nop     dword ptr [rax+rax+00h]
0x1800534f2  test    eax, eax
0x1800534f4  jz      loc_18005358D
0x1800534fa  mov     rcx, [rbp+68h]; this
0x1800534fe  mov     r9d, eax; char *
0x180053501  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180053508  mov     edx, 127h; void *
0x18005350d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180053512  mov     ebx, eax
0x180053514  mov     rcx, [rsp+160h+var_108]; hKey
0x180053519  test    rcx, rcx
0x18005351c  jz      short loc_18005352B
0x18005351e  call    cs:__imp_RegCloseKey
0x180053525  nop     dword ptr [rax+rax+00h]
0x18005352a  nop
0x18005352b  lea     rcx, [rsp+160h+hKey]; this
0x180053530  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180053535  nop
0x180053536  lea     rcx, [rsp+160h+var_E8]; this
0x18005353b  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x180053540  nop
0x180053541  cmp     [rbp+60h+arg_8], sil
0x180053545  jnz     short loc_180053557
0x180053547  cmp     [rbp+60h+arg_10], sil
0x18005354e  setz    cl
0x180053551  call    CleanupBitLockerReducedPcrProfileHelper
0x180053556  nop
0x180053557  test    dil, dil
0x18005355a  jz      short loc_180053567
0x18005355c  lea     rcx, [rsp+160h+var_100]
0x180053561  call    PpfUnlock
0x180053566  nop
0x180053567  mov     [rsp+160h+phkResult], r13
0x18005356c  lea     r9, aLeavingHs; "Leaving %hs"
0x180053573  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18005357a  mov     edx, 89h; unsigned int
0x18005357f  mov     rcx, r15; char *
0x180053582  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180053587  nop
0x180053588  jmp     loc_1800533DF
0x18005358d  mov     eax, [rbp+60h+arg_0]
0x180053590  mov     dword ptr [rbp+60h+var_D0], eax
0x180053593  mov     [rsp+160h+var_F0], rsi
0x180053598  mov     [rsp+160h+lpdwDisposition], rsi; lpdwDisposition
0x18005359d  lea     rax, [rsp+160h+var_F0]
0x1800535a2  mov     [rsp+160h+var_128], rax; phkResult
0x1800535a7  mov     [rsp+160h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x1800535ac  mov     [rsp+160h+cbData], ebx; samDesired
0x1800535b0  mov     dword ptr [rsp+160h+phkResult], esi; dwOptions
0x1800535b4  xor     r9d, r9d; lpClass
0x1800535b7  xor     r8d, r8d; Reserved
0x1800535ba  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Control\\Bit"...
0x1800535c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800535c8  call    cs:__imp_RegCreateKeyExW
0x1800535cf  nop     dword ptr [rax+rax+00h]
0x1800535d4  mov     ebx, eax
0x1800535d6  test    eax, eax
0x1800535d8  jle     short loc_1800535E3
0x1800535da  movzx   ebx, ax
0x1800535dd  or      ebx, 80070000h
0x1800535e3  lea     r15, WPP_GLOBAL_Control
0x1800535ea  test    ebx, ebx
0x1800535ec  jz      short loc_180053615
0x1800535ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800535f5  cmp     rcx, r15
0x1800535f8  jz      short loc_180053611
0x1800535fa  test    byte ptr [rcx+1Ch], 40h
0x1800535fe  jz      short loc_180053611
0x180053600  mov     edx, 131h
0x180053605  mov     r9d, ebx
0x180053608  mov     rcx, [rcx+10h]
0x18005360c  call    WPP_SF_d
0x180053611  test    ebx, ebx
0x180053613  js      short loc_18005367D
0x180053615  mov     [rsp+160h+cbData], 4; cbData
0x18005361d  lea     rax, [rbp+60h+var_D0]
0x180053621  mov     [rsp+160h+phkResult], rax; int
0x180053626  mov     r9d, 4; dwType
0x18005362c  xor     r8d, r8d; Reserved
0x18005362f  lea     rdx, aExcludedpcrsbi; "ExcludedPcrsBitmap"
0x180053636  mov     rcx, [rsp+160h+var_F0]; hKey
0x18005363b  call    cs:__imp_RegSetValueExW
0x180053642  nop     dword ptr [rax+rax+00h]
0x180053647  mov     ebx, eax
0x180053649  test    eax, eax
0x18005364b  jle     short loc_180053656
0x18005364d  movzx   ebx, ax
0x180053650  or      ebx, 80070000h
0x180053656  test    ebx, ebx
0x180053658  jz      short loc_18005367D
0x18005365a  mov     rcx, cs:WPP_GLOBAL_Control
0x180053661  cmp     rcx, r15
0x180053664  jz      short loc_18005367D
0x180053666  test    byte ptr [rcx+1Ch], 40h
0x18005366a  jz      short loc_18005367D
0x18005366c  mov     edx, 132h
0x180053671  mov     r9d, ebx
0x180053674  mov     rcx, [rcx+10h]
0x180053678  call    WPP_SF_d
0x18005367d  mov     rcx, [rsp+160h+var_F0]; hKey
0x180053682  test    rcx, rcx
0x180053685  jz      short loc_180053693
0x180053687  call    cs:__imp_RegCloseKey
0x18005368e  nop     dword ptr [rax+rax+00h]
0x180053693  test    ebx, ebx
0x180053695  jns     loc_180053731
0x18005369b  mov     rcx, [rbp+68h]; this
0x18005369f  mov     r9d, ebx; char *
0x1800536a2  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x1800536a9  mov     edx, 12Ah; void *
0x1800536ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800536b3  nop
0x1800536b4  mov     rcx, [rsp+160h+var_108]; hKey
0x1800536b9  test    rcx, rcx
0x1800536bc  jz      short loc_1800536CB
0x1800536be  call    cs:__imp_RegCloseKey
0x1800536c5  nop     dword ptr [rax+rax+00h]
0x1800536ca  nop
0x1800536cb  lea     rcx, [rsp+160h+hKey]; this
0x1800536d0  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x1800536d5  nop
0x1800536d6  lea     rcx, [rsp+160h+var_E8]; this
0x1800536db  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x1800536e0  nop
0x1800536e1  cmp     [rbp+60h+arg_8], sil
0x1800536e5  jnz     short loc_1800536F7
0x1800536e7  cmp     [rbp+60h+arg_10], sil
0x1800536ee  setz    cl
0x1800536f1  call    CleanupBitLockerReducedPcrProfileHelper
0x1800536f6  nop
0x1800536f7  test    dil, dil
0x1800536fa  jz      short loc_180053707
0x1800536fc  lea     rcx, [rsp+160h+var_100]
0x180053701  call    PpfUnlock
0x180053706  nop
0x180053707  mov     [rsp+160h+phkResult], r13
0x18005370c  lea     r9, aLeavingHs; "Leaving %hs"
0x180053713  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18005371a  mov     edx, 89h; unsigned int
0x18005371f  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180053726  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18005372b  nop
0x18005372c  jmp     loc_1800533DF
0x180053731  lea     rax, off_18005A498
0x180053738  mov     [rbp+60h+var_A0], rax
0x18005373c  lea     rax, [rbp+60h+arg_0]
0x180053740  mov     [rbp+60h+var_98], rax
0x180053744  lea     rax, [rbp+60h+arg_10]
0x18005374b  mov     [rbp+60h+var_90], rax
0x18005374f  lea     rax, [rbp+60h+var_A0]
0x180053753  mov     [rbp+60h+var_38], rax
0x180053757  lea     rdx, [rbp+60h+var_A8]
0x18005375b  xor     ecx, ecx
  ... truncated ...
```
