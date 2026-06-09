# CleanupBitLockerReducedPcrProfileHelper

- ea: `0x180052134`
- end: `0x180052721`
- name: `CleanupBitLockerReducedPcrProfileHelper`
- size: `1517`
- prototype: `__int64 __fastcall(char)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180051e38`
- `0x180052728`
- `0x180053280`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x18003beec`
- `0x18003fcac`
- `0x180052134`
- `0x180053010`
- `0x180053db4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005225f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005231e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005239c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800524ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052539`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800525b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052603`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005267d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800526cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005225f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005231e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005239c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800524ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052539`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800525b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180052603`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005267d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800526cd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800522e2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800522e2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052484`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180052484`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005222c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005222c`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180052505`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180052505`

## string_xrefs

- `0x1800521b9`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052243`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052302`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052381`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052417`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x18005249e`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x18005251e`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052598`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052662`: `onecore\base\ngscb\pcrpf\fwupdate\fvereducedpcrp.cpp`
- `0x180052185`: `BitLocker Reduced PCR Profile Cleanup Task`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CleanupBitLockerReducedPcrProfileHelper(char a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  unsigned int v5; // eax
  unsigned int ValueW; // eax
  const unsigned __int16 *v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // eax
  LSTATUS v12; // eax
  int v13; // eax
  int v14; // eax
  int phkResult; // [rsp+20h] [rbp-99h]
  unsigned int phkResulta; // [rsp+20h] [rbp-99h]
  unsigned int phkResultb; // [rsp+20h] [rbp-99h]
  HKEY hKey; // [rsp+40h] [rbp-79h] BYREF
  int v19; // [rsp+48h] [rbp-71h] BYREF
  const wchar_t *v20; // [rsp+50h] [rbp-69h]
  const wchar_t *v21; // [rsp+58h] [rbp-61h]
  const char *v22; // [rsp+60h] [rbp-59h]
  _BYTE v23[8]; // [rsp+70h] [rbp-49h] BYREF
  _QWORD v24[19]; // [rsp+78h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  int pvData; // [rsp+128h] [rbp+6Fh] BYREF
  DWORD pcbData; // [rsp+130h] [rbp+77h] BYREF
  HKEY hkey; // [rsp+138h] [rbp+7Fh] BYREF

  v22 = "CleanupBitLockerReducedPcrProfileHelper";
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "CleanupBitLockerReducedPcrProfileHelper");
  v19 = 0;
  v20 = L"BitLocker Reduced PCR Profile Cleanup Task";
  v21 = L"CleanupBitLockerReducedPcrProfile";
  hKey = 0;
  v2 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)&hKey);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
      (const char *)(unsigned int)v2,
      phkResult);
    PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)&hKey);
    PpfScheduledTask::~PpfScheduledTask((PpfScheduledTask *)&v19);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "CleanupBitLockerReducedPcrProfileHelper");
    return v3;
  }
  hkey = 0;
  v5 = RegOpenKeyExW(hKey, L"Control\\PCRPF", 0, 0x2001Bu, &hkey);
  if ( v5 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xCC,
           (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
           (const char *)v5,
           phkResulta);
    if ( hkey )
      RegCloseKey(hkey);
LABEL_41:
    PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)&hKey);
    PpfScheduledTask::~PpfScheduledTask((PpfScheduledTask *)&v19);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "CleanupBitLockerReducedPcrProfileHelper");
    return v3;
  }
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(hkey, 0, L"ExcludedPcrsResealNeeded", 0x20000010u, 0, &pvData, &pcbData);
  if ( ValueW == 2 )
    goto LABEL_38;
  if ( ValueW )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xD3,
           (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
           (const char *)ValueW,
           phkResultb);
    if ( hkey )
      RegCloseKey(hkey);
    goto LABEL_41;
  }
  if ( !pvData )
  {
LABEL_38:
    v14 = PpfScheduledTask::ManageScheduledTask((PpfScheduledTask *)&v19, 0);
    v3 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD8,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
        (const char *)(unsigned int)v14,
        phkResultb);
      if ( hkey )
        RegCloseKey(hkey);
      goto LABEL_41;
    }
    if ( hkey )
      RegCloseKey(hkey);
  }
  else
  {
    v8 = NgscbDeleteDWordConfig(v7);
    v3 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDD,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
        (const char *)(unsigned int)v8,
        phkResultb);
      if ( hkey )
        RegCloseKey(hkey);
      goto LABEL_41;
    }
    if ( !a1 )
    {
      v24[0] = off_18005A470;
      v24[13] = v24;
      LOBYTE(v9) = 1;
      v10 = IterateBitLockerVolumesAndDoAction(v9, v23);
      v3 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xED,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
          (const char *)(unsigned int)v10,
          phkResultb);
        if ( hkey )
          RegCloseKey(hkey);
        goto LABEL_41;
      }
    }
    v11 = RegDeleteValueW(hkey, L"ExcludedPcrsResealNeeded");
    if ( (v11 & 0xFFFFFFFD) != 0 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xF6,
             (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
             (const char *)v11,
             phkResultb);
      if ( hkey )
        RegCloseKey(hkey);
      goto LABEL_41;
    }
    v12 = RegFlushKey(hkey);
    v3 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF7,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
        (const char *)(unsigned int)v12,
        phkResultb);
      if ( hkey )
        RegCloseKey(hkey);
      goto LABEL_41;
    }
    v13 = PpfScheduledTask::ManageScheduledTask((PpfScheduledTask *)&v19, 0);
    v3 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\fwupdate\\fvereducedpcrp.cpp",
        (const char *)(unsigned int)v13,
        phkResultb);
      if ( hkey )
        RegCloseKey(hkey);
      goto LABEL_41;
    }
    if ( hkey )
      RegCloseKey(hkey);
  }
  PpfSystemCcsKey::~PpfSystemCcsKey((PpfSystemCcsKey *)&hKey);
  PpfScheduledTask::~PpfScheduledTask((PpfScheduledTask *)&v19);
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x89u,
    "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
    "Leaving %hs",
    "CleanupBitLockerReducedPcrProfileHelper");
  return 0;
}

```

## disassembly

```asm
0x180052134  push    rbp
0x180052136  push    rbx
0x180052137  push    rdi
0x180052138  push    r14
0x18005213a  push    r15
0x18005213c  lea     rbp, [rsp-37h]
0x180052141  sub     rsp, 0F0h
0x180052148  mov     dil, cl
0x18005214b  lea     r14, aCleanupbitlock_0; "CleanupBitLockerReducedPcrProfileHelper"
0x180052152  mov     [rbp+57h+var_B0], r14
0x180052156  mov     [rsp+110h+phkResult], r14; int
0x18005215b  lea     r9, aEnteringHs; "Entering %hs"
0x180052162  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x180052169  mov     edx, 84h; unsigned int
0x18005216e  lea     r15, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180052175  mov     rcx, r15; char *
0x180052178  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18005217d  nop
0x18005217e  mov     [rbp+57h+var_C8], 0
0x180052185  lea     rax, aBitlockerReduc_0; "BitLocker Reduced PCR Profile Cleanup T"...
0x18005218c  mov     [rbp+57h+var_C0], rax
0x180052190  lea     rax, aCleanupbitlock_1; "CleanupBitLockerReducedPcrProfile"
0x180052197  mov     [rbp+57h+var_B8], rax
0x18005219b  mov     [rbp+57h+hKey], 0
0x1800521a3  lea     rcx, [rbp+57h+hKey]; this
0x1800521a7  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x1800521ac  mov     ebx, eax
0x1800521ae  test    eax, eax
0x1800521b0  jns     short loc_180052207
0x1800521b2  mov     rcx, [rbp+5Fh]; this
0x1800521b6  mov     r9d, eax; char *
0x1800521b9  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x1800521c0  mov     edx, 0CAh; void *
0x1800521c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800521ca  nop
0x1800521cb  lea     rcx, [rbp+57h+hKey]; this
0x1800521cf  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x1800521d4  nop
0x1800521d5  lea     rcx, [rbp+57h+var_C8]; this
0x1800521d9  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x1800521de  nop
0x1800521df  mov     [rsp+110h+phkResult], r14
0x1800521e4  lea     r9, aLeavingHs; "Leaving %hs"
0x1800521eb  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800521f2  mov     edx, 89h; unsigned int
0x1800521f7  mov     rcx, r15; char *
0x1800521fa  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800521ff  nop
0x180052200  mov     eax, ebx
0x180052202  jmp     loc_180052711
0x180052207  mov     [rbp+57h+hkey], 0
0x18005220f  lea     rax, [rbp+57h+hkey]
0x180052213  mov     [rsp+110h+phkResult], rax; unsigned int
0x180052218  mov     r9d, 2001Bh; samDesired
0x18005221e  xor     r8d, r8d; ulOptions
0x180052221  lea     rdx, aControlPcrpf; "Control\\PCRPF"
0x180052228  mov     rcx, [rbp+57h+hKey]; hKey
0x18005222c  call    cs:__imp_RegOpenKeyExW
0x180052233  nop     dword ptr [rax+rax+00h]
0x180052238  test    eax, eax
0x18005223a  jz      short loc_1800522A6
0x18005223c  mov     rcx, [rbp+5Fh]; this
0x180052240  mov     r9d, eax; char *
0x180052243  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005224a  mov     edx, 0CCh; void *
0x18005224f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180052254  mov     ebx, eax
0x180052256  mov     rcx, [rbp+57h+hkey]; hKey
0x18005225a  test    rcx, rcx
0x18005225d  jz      short loc_18005226C
0x18005225f  call    cs:__imp_RegCloseKey
0x180052266  nop     dword ptr [rax+rax+00h]
0x18005226b  nop
0x18005226c  lea     rcx, [rbp+57h+hKey]; this
0x180052270  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180052275  nop
0x180052276  lea     rcx, [rbp+57h+var_C8]; this
0x18005227a  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x18005227f  nop
0x180052280  mov     [rsp+110h+phkResult], r14
0x180052285  lea     r9, aLeavingHs; "Leaving %hs"
0x18005228c  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180052293  mov     edx, 89h; unsigned int
0x180052298  mov     rcx, r15; char *
0x18005229b  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800522a0  nop
0x1800522a1  jmp     loc_180052200
0x1800522a6  mov     [rbp+57h+arg_8], 0
0x1800522ad  mov     [rbp+57h+arg_10], 4
0x1800522b4  lea     rax, [rbp+57h+arg_10]
0x1800522b8  mov     [rsp+110h+pcbData], rax; pcbData
0x1800522bd  lea     rax, [rbp+57h+arg_8]
0x1800522c1  mov     [rsp+110h+pvData], rax; pvData
0x1800522c6  mov     [rsp+110h+phkResult], 0; int
0x1800522cf  mov     r9d, 20000010h; dwFlags
0x1800522d5  lea     r8, aExcludedpcrsre_0; "ExcludedPcrsResealNeeded"
0x1800522dc  xor     edx, edx; lpSubKey
0x1800522de  mov     rcx, [rbp+57h+hkey]; hkey
0x1800522e2  call    cs:__imp_RegGetValueW
0x1800522e9  nop     dword ptr [rax+rax+00h]
0x1800522ee  cmp     eax, 2
0x1800522f1  jz      loc_18005264A
0x1800522f7  test    eax, eax
0x1800522f9  jz      short loc_180052365
0x1800522fb  mov     rcx, [rbp+5Fh]; this
0x1800522ff  mov     r9d, eax; char *
0x180052302  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052309  mov     edx, 0D3h; void *
0x18005230e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180052313  mov     ebx, eax
0x180052315  mov     rcx, [rbp+57h+hkey]; hKey
0x180052319  test    rcx, rcx
0x18005231c  jz      short loc_18005232B
0x18005231e  call    cs:__imp_RegCloseKey
0x180052325  nop     dword ptr [rax+rax+00h]
0x18005232a  nop
0x18005232b  lea     rcx, [rbp+57h+hKey]; this
0x18005232f  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180052334  nop
0x180052335  lea     rcx, [rbp+57h+var_C8]; this
0x180052339  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x18005233e  nop
0x18005233f  mov     [rsp+110h+phkResult], r14
0x180052344  lea     r9, aLeavingHs; "Leaving %hs"
0x18005234b  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180052352  mov     edx, 89h; unsigned int
0x180052357  mov     rcx, r15; char *
0x18005235a  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18005235f  nop
0x180052360  jmp     loc_180052200
0x180052365  cmp     [rbp+57h+arg_8], 0
0x180052369  jz      loc_18005264A
0x18005236f  call    ?NgscbDeleteDWordConfig@@YAJPEBG@Z; NgscbDeleteDWordConfig(ushort const *)
0x180052374  mov     ebx, eax
0x180052376  test    eax, eax
0x180052378  jns     short loc_1800523E3
0x18005237a  mov     rcx, [rbp+5Fh]; this
0x18005237e  mov     r9d, eax; char *
0x180052381  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052388  mov     edx, 0DDh; void *
0x18005238d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052392  nop
0x180052393  mov     rcx, [rbp+57h+hkey]; hKey
0x180052397  test    rcx, rcx
0x18005239a  jz      short loc_1800523A9
0x18005239c  call    cs:__imp_RegCloseKey
0x1800523a3  nop     dword ptr [rax+rax+00h]
0x1800523a8  nop
0x1800523a9  lea     rcx, [rbp+57h+hKey]; this
0x1800523ad  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x1800523b2  nop
0x1800523b3  lea     rcx, [rbp+57h+var_C8]; this
0x1800523b7  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x1800523bc  nop
0x1800523bd  mov     [rsp+110h+phkResult], r14
0x1800523c2  lea     r9, aLeavingHs; "Leaving %hs"
0x1800523c9  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800523d0  mov     edx, 89h; unsigned int
0x1800523d5  mov     rcx, r15; char *
0x1800523d8  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800523dd  nop
0x1800523de  jmp     loc_180052200
0x1800523e3  test    dil, dil
0x1800523e6  jnz     loc_180052479
0x1800523ec  lea     rax, off_18005A470
0x1800523f3  mov     [rbp+57h+var_98], rax
0x1800523f7  lea     rax, [rbp+57h+var_98]
0x1800523fb  mov     [rbp+57h+var_30], rax
0x1800523ff  lea     rdx, [rbp+57h+var_A0]
0x180052403  mov     cl, 1
0x180052405  call    IterateBitLockerVolumesAndDoAction
0x18005240a  mov     ebx, eax
0x18005240c  test    eax, eax
0x18005240e  jns     short loc_180052479
0x180052410  mov     rcx, [rbp+5Fh]; this
0x180052414  mov     r9d, eax; char *
0x180052417  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005241e  mov     edx, 0EDh; void *
0x180052423  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052428  nop
0x180052429  mov     rcx, [rbp+57h+hkey]; hKey
0x18005242d  test    rcx, rcx
0x180052430  jz      short loc_18005243F
0x180052432  call    cs:__imp_RegCloseKey
0x180052439  nop     dword ptr [rax+rax+00h]
0x18005243e  nop
0x18005243f  lea     rcx, [rbp+57h+hKey]; this
0x180052443  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x180052448  nop
0x180052449  lea     rcx, [rbp+57h+var_C8]; this
0x18005244d  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x180052452  nop
0x180052453  mov     [rsp+110h+phkResult], r14
0x180052458  lea     r9, aLeavingHs; "Leaving %hs"
0x18005245f  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180052466  mov     edx, 89h; unsigned int
0x18005246b  mov     rcx, r15; char *
0x18005246e  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180052473  nop
0x180052474  jmp     loc_180052200
0x180052479  lea     rdx, aExcludedpcrsre_0; "ExcludedPcrsResealNeeded"
0x180052480  mov     rcx, [rbp+57h+hkey]; hKey
0x180052484  call    cs:__imp_RegDeleteValueW
0x18005248b  nop     dword ptr [rax+rax+00h]
0x180052490  test    eax, 0FFFFFFFDh
0x180052495  jz      short loc_180052501
0x180052497  mov     rcx, [rbp+5Fh]; this
0x18005249b  mov     r9d, eax; char *
0x18005249e  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x1800524a5  mov     edx, 0F6h; void *
0x1800524aa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800524af  mov     ebx, eax
0x1800524b1  mov     rcx, [rbp+57h+hkey]; hKey
0x1800524b5  test    rcx, rcx
0x1800524b8  jz      short loc_1800524C7
0x1800524ba  call    cs:__imp_RegCloseKey
0x1800524c1  nop     dword ptr [rax+rax+00h]
0x1800524c6  nop
0x1800524c7  lea     rcx, [rbp+57h+hKey]; this
0x1800524cb  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x1800524d0  nop
0x1800524d1  lea     rcx, [rbp+57h+var_C8]; this
0x1800524d5  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x1800524da  nop
0x1800524db  mov     [rsp+110h+phkResult], r14
0x1800524e0  lea     r9, aLeavingHs; "Leaving %hs"
0x1800524e7  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800524ee  mov     edx, 89h; unsigned int
0x1800524f3  mov     rcx, r15; char *
0x1800524f6  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800524fb  nop
0x1800524fc  jmp     loc_180052200
0x180052501  mov     rcx, [rbp+57h+hkey]; hKey
0x180052505  call    cs:__imp_RegFlushKey
0x18005250c  nop     dword ptr [rax+rax+00h]
0x180052511  mov     ebx, eax
0x180052513  test    eax, eax
0x180052515  jns     short loc_180052580
0x180052517  mov     rcx, [rbp+5Fh]; this
0x18005251b  mov     r9d, eax; char *
0x18005251e  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x180052525  mov     edx, 0F7h; void *
0x18005252a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005252f  nop
0x180052530  mov     rcx, [rbp+57h+hkey]; hKey
0x180052534  test    rcx, rcx
0x180052537  jz      short loc_180052546
0x180052539  call    cs:__imp_RegCloseKey
0x180052540  nop     dword ptr [rax+rax+00h]
0x180052545  nop
0x180052546  lea     rcx, [rbp+57h+hKey]; this
0x18005254a  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x18005254f  nop
0x180052550  lea     rcx, [rbp+57h+var_C8]; this
0x180052554  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x180052559  nop
0x18005255a  mov     [rsp+110h+phkResult], r14
0x18005255f  lea     r9, aLeavingHs; "Leaving %hs"
0x180052566  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x18005256d  mov     edx, 89h; unsigned int
0x180052572  mov     rcx, r15; char *
0x180052575  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x18005257a  nop
0x18005257b  jmp     loc_180052200
0x180052580  xor     edx, edx; bool
0x180052582  lea     rcx, [rbp+57h+var_C8]; this
0x180052586  call    ?ManageScheduledTask@PpfScheduledTask@@QEAAJ_N@Z; PpfScheduledTask::ManageScheduledTask(bool)
0x18005258b  mov     ebx, eax
0x18005258d  test    eax, eax
0x18005258f  jns     short loc_1800525FA
0x180052591  mov     rcx, [rbp+5Fh]; this
0x180052595  mov     r9d, eax; char *
0x180052598  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\pcrpf\\fwupdate\\"...
0x18005259f  mov     edx, 0FAh; void *
0x1800525a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800525a9  nop
0x1800525aa  mov     rcx, [rbp+57h+hkey]; hKey
0x1800525ae  test    rcx, rcx
0x1800525b1  jz      short loc_1800525C0
0x1800525b3  call    cs:__imp_RegCloseKey
0x1800525ba  nop     dword ptr [rax+rax+00h]
0x1800525bf  nop
0x1800525c0  lea     rcx, [rbp+57h+hKey]; this
0x1800525c4  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x1800525c9  nop
0x1800525ca  lea     rcx, [rbp+57h+var_C8]; this
0x1800525ce  call    ??1PpfScheduledTask@@QEAA@XZ; PpfScheduledTask::~PpfScheduledTask(void)
0x1800525d3  nop
0x1800525d4  mov     [rsp+110h+phkResult], r14
0x1800525d9  lea     r9, aLeavingHs; "Leaving %hs"
0x1800525e0  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x1800525e7  mov     edx, 89h; unsigned int
0x1800525ec  mov     rcx, r15; char *
0x1800525ef  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x1800525f4  nop
0x1800525f5  jmp     loc_180052200
0x1800525fa  mov     rcx, [rbp+57h+hkey]; hKey
0x1800525fe  test    rcx, rcx
0x180052601  jz      short loc_180052610
0x180052603  call    cs:__imp_RegCloseKey
  ... truncated ...
```
