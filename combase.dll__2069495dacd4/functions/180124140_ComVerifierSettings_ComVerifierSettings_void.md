# ComVerifierSettings::ComVerifierSettings(void)

- ea: `0x180124140`
- end: `0x18012421b`
- name: `??0ComVerifierSettings@@AEAA@XZ`
- size: `219`
- prototype: `void __fastcall(ComVerifierSettings *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180124120`

## callees

- `0x180124140`
- `0x180124224`
- `0x180124304`
- `0x1801cdd54`
- `0x1801cde34`
- `0x1801cdfbc`
- `0x180255010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18024da05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18024da05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801241dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18024da5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18024da79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18024da94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18024daaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18024daca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801241dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18024da5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18024da79`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18024da94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18024daaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18024daca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801241bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1801241bf`

## string_xrefs

- `0x1801241b8`: `verifier.dll`
- `0x18024da54`: `VerifierIsDllEntryActive`
- `0x18024da6b`: `VerifierIsCurrentThreadHoldingLocks`
- `0x18024daa1`: `VerifierDeleteFreeMemoryCallback`
- `0x18024db2f`: `ComVerifyThreadState`
- `0x18024db47`: `ComVerifyChannelState`
- `0x18024db5f`: `ComVerifyOleInitCalled`
- `0x18024db77`: `ComVerifySecurity`
- `0x18024dadd`: `ComEnableDllMainChecks`
- `0x18024daff`: `ComBreakOnAllExceptions`
- `0x18024db17`: `ComVerifyLocksOnCall`
- `0x18024dbef`: `ComVerifyGetSlowStacks`
- `0x18024dc2f`: `CheckUnrecommendedUsageFromAPC`
- `0x18024db8f`: `ComVerifyProxies`
- `0x18024dba7`: `ComVerifyClassFactory`
- `0x18024dbbf`: `ComEnableObjectTracking`
- `0x18024dbd7`: `ComEnableVTBLTracking`
- `0x18024dcaa`: `ComMaxStackTracesPerProcess`
- `0x18024dcc2`: `ComCheckPrematureStubRundown`
- `0x18024dcda`: `ComWinrtAsyncCheckPatternContract`
- `0x18024dcf2`: `ComWinrtAsyncLearningMode`
- `0x18024dc77`: `ComVerifyFatalExceptionHandlingDisabled`
- `0x18024dc92`: `ComMaxStackTracesPerThread`
- `0x18024dd0a`: `ComEnableExitProcessChecks`
- `0x18024dd2f`: `ComEnableAggressiveDllUnload`
- `0x18024dd47`: `ComEnableSecBlanketChecks`
- `0x18024dd5f`: `AggressiveDllUnloadPeriod`

## pseudocode

```c
void __fastcall ComVerifierSettings::ComVerifierSettings(ComVerifierSettings *this, bool a2)
{
  bool v2; // dl
  unsigned int v3; // edx
  const wchar_t *v4; // rcx
  unsigned int ULongFromOleKey; // eax
  HMODULE ModuleHandleW; // rax
  HMODULE v7; // rbx
  FARPROC ProcAddress; // rax
  _QWORD *pSettingsState; // rax
  bool BooleanFromImageOptionsKey; // al
  ComVerifierSettings::ComVerifierSettingsState *v11; // rcx
  ComVerifierSettings *fEnabled; // [rsp+30h] [rbp+8h] BYREF
  unsigned int ulFlags; // [rsp+38h] [rbp+10h] BYREF

  fEnabled = this;
  ComVerifierSettings::s_singleton._pSettingsState = 0;
  if ( (NtCurrentPeb()->NtGlobalFlag & 0x100) == 0 )
    goto LABEL_2;
  ModuleHandleW = GetModuleHandleW(L"verifier.dll");
  v7 = ModuleHandleW;
  if ( ModuleHandleW
    && (ProcAddress = GetProcAddress(ModuleHandleW, "VerifierQueryRuntimeFlags")) != 0
    && (LODWORD(fEnabled) = 0,
        ulFlags = 0,
        !((unsigned int (__fastcall *)(ComVerifierSettings **, unsigned int *))ProcAddress)(&fEnabled, &ulFlags))
    && (_DWORD)fEnabled
    && (ulFlags & 0x100) != 0 )
  {
    pSettingsState = HeapAlloc(g_hHeap, 0, 0x50u);
    if ( pSettingsState )
    {
      *pSettingsState = 0;
      pSettingsState[1] = 0;
      *((_DWORD *)pSettingsState + 4) = 0;
      *((_WORD *)pSettingsState + 10) = 0;
      *((_BYTE *)pSettingsState + 22) = 0;
      *((_DWORD *)pSettingsState + 6) = 10;
      *((_DWORD *)pSettingsState + 7) = 1000;
      *((_DWORD *)pSettingsState + 8) = 1000;
      pSettingsState[5] = 0;
      pSettingsState[6] = 0;
      pSettingsState[7] = 0;
      pSettingsState[8] = 0;
      pSettingsState[9] = 0;
    }
    else
    {
      pSettingsState = 0;
    }
    ComVerifierSettings::s_singleton._pSettingsState = (ComVerifierSettings::ComVerifierSettingsState *)pSettingsState;
  }
  else
  {
    pSettingsState = ComVerifierSettings::s_singleton._pSettingsState;
  }
  if ( !pSettingsState )
  {
LABEL_2:
    ComVerifierSettings::s_fPgAllocUseSystemHeap = ComVerifierSettings::ReadBooleanFromOleKey(
                                                     L"PageAllocatorUseSystemHeap",
                                                     a2);
    ComVerifierSettings::s_fPgAllocHeapIsPrivate = ComVerifierSettings::ReadBooleanFromOleKey(
                                                     L"PageAllocatorSystemHeapIsPrivate",
                                                     v2);
    ULongFromOleKey = ComVerifierSettings::ReadULongFromOleKey(v4, v3);
LABEL_3:
    ComVerifierSettings::s_dwAggressiveMTATesting = ULongFromOleKey;
    return;
  }
  ComVerifierSettings::s_singleton._pSettingsState->_pfnVerifierIsDllEntryActive = (unsigned int (__fastcall *)(void **))GetProcAddress(v7, "VerifierIsDllEntryActive");
  ComVerifierSettings::s_singleton._pSettingsState->_pfnVerifierIsCurrentThreadHoldingLocks = (unsigned int (__fastcall *)())GetProcAddress(v7, "VerifierIsCurrentThreadHoldingLocks");
  ComVerifierSettings::s_singleton._pSettingsState->_pfnVerifierAddFreeMemoryCallback = (int (__fastcall *)(int (__fastcall *)(void *, unsigned __int64, void *)))GetProcAddress(v7, "VerifierAddFreeMemoryCallback");
  ComVerifierSettings::s_singleton._pSettingsState->_pfnVerifierDeleteFreeMemoryCallback = (int (__fastcall *)(int (__fastcall *)(void *, unsigned __int64, void *)))GetProcAddress(v7, "VerifierDeleteFreeMemoryCallback");
  ComVerifierSettings::s_singleton._pSettingsState->_pfnVerifierGetPropertyValueByName = (int (__fastcall *)(const wchar_t *, const wchar_t *, void *, unsigned int *))GetProcAddress(v7, "VerifierGetPropertyValueByName");
  ComVerifierSettings::s_singleton._pSettingsState->_fCallBacksInitialized = 0;
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableDllMainChecks = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                              L"ComEnableDllMainChecks",
                                                                              1);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableBreakOnException = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                 L"ComBreakOnAllExceptions",
                                                                                 1);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableVerifyLocks = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                            L"ComVerifyLocksOnCall",
                                                                            0);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableVerifyThreadState = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                  L"ComVerifyThreadState",
                                                                                  1);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableVerifyChannelState = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                   L"ComVerifyChannelState",
                                                                                   1);
  ComVerifierSettings::s_singleton._pSettingsState->_fVerifyOleInitCalled = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                              L"ComVerifyOleInitCalled",
                                                                              1);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableVerifySecurity = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                               L"ComVerifySecurity",
                                                                               1);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableVerifyProxies = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                              L"ComVerifyProxies",
                                                                              1);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableVerifyClassFactory = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                   L"ComVerifyClassFactory",
                                                                                   1);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableObjectTracking = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                               L"ComEnableObjectTracking",
                                                                               1);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableVTBLTracking = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                             L"ComEnableVTBLTracking",
                                                                             1);
  ComVerifierSettings::s_singleton._pSettingsState->_fUseSlowStackTraces = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                             L"ComVerifyGetSlowStacks",
                                                                             0);
  ComVerifierSettings::s_fPgAllocUseSystemHeap = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                   L"PageAllocatorUseSystemHeap",
                                                   1);
  ComVerifierSettings::s_fPgAllocHeapIsPrivate = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                   L"PageAllocatorSystemHeapIsPrivate",
                                                   1);
  ComVerifierSettings::s_singleton._pSettingsState->_fCheckUnrecommendedUsageFromAPC = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                         L"CheckUnrecommendedUsageFromAPC",
                                                                                         0);
  ComVerifierSettings::s_singleton._pSettingsState->_fCheckMarshalingToUntrustedProcess = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                            L"CheckMarshalingToUntrustedProcess",
                                                                                            1);
  ComVerifierSettings::s_singleton._pSettingsState->_fCheckClassicMarshalingToUntrustedProcess = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                                   L"CheckClassicMarshalin"
                                                                                                    "gToUntrustedProcess",
                                                                                                   0);
  ComVerifierSettings::s_singleton._pSettingsState->_fVerifyFatalExceptionHandlingDisabled = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                               L"ComVerifyFatalExceptionHandlingDisabled",
                                                                                               0);
  ComVerifierSettings::s_singleton._pSettingsState->_ulMaxStackTracesPerThread = ComVerifierSettings::ReadULongFromImageOptionsKey(
                                                                                   L"ComMaxStackTracesPerThread",
                                                                                   0xAu);
  ComVerifierSettings::s_singleton._pSettingsState->_ulMaxStackTracesPerProcess = ComVerifierSettings::ReadULongFromImageOptionsKey(
                                                                                    L"ComMaxStackTracesPerProcess",
                                                                                    0x3E8u);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnablePrematureStubRundownCheck = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                          L"ComCheckPrematureStubRundown",
                                                                                          1);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableWinrtAsyncPatternContractChecks = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                                L"ComWinrtAsyncCheckPatternContract",
                                                                                                1);
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableWinrtAsyncLearningModeChecks = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                             L"ComWinrtAsyncLearningMode",
                                                                                             0);
  BooleanFromImageOptionsKey = ComVerifierSettings::ReadBooleanFromImageOptionsKey(L"ComEnableExitProcessChecks", 1);
  v11 = ComVerifierSettings::s_singleton._pSettingsState;
  ComVerifierSettings::s_singleton._pSettingsState->_fEnableExitProcessChecks = BooleanFromImageOptionsKey;
  if ( !ComVerifierSettings::ReadAvrfProperties((ComVerifierSettings *)v11) )
  {
    ComVerifierSettings::s_singleton._pSettingsState->_fEnableAggressiveDllUnload = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                      L"ComEnableAggressiveDllUnload",
                                                                                      1);
    ComVerifierSettings::s_singleton._pSettingsState->_fEnableSecBlanketChecks = ComVerifierSettings::ReadBooleanFromImageOptionsKey(
                                                                                   L"ComEnableSecBlanketChecks",
                                                                                   0);
    ComVerifierSettings::s_singleton._pSettingsState->_dwAggressiveDllUnloadPeriod = ComVerifierSettings::ReadULongFromImageOptionsKey(
                                                                                       L"AggressiveDllUnloadPeriod",
                                                                                       0x3E8u);
    if ( ComVerifierSettings::s_singleton._pSettingsState->_dwAggressiveDllUnloadPeriod - 100 > 0xE9FC )
      ComVerifierSettings::s_singleton._pSettingsState->_dwAggressiveDllUnloadPeriod = 1000;
    ULongFromOleKey = ComVerifierSettings::ReadULongFromImageOptionsKey(L"AggressiveMTATesting", 0);
    goto LABEL_3;
  }
}

```

## disassembly

```asm
0x180124140  mov     [rsp+arg_10], rbx
0x180124145  mov     [rsp+arg_18], rsi
0x18012414a  mov     [rsp+fEnabled], rcx
0x18012414f  push    rdi
0x180124150  sub     rsp, 20h
0x180124154  xor     edi, edi
0x180124156  mov     cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState, rdi; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18012415d  mov     rax, gs:60h
0x180124166  test    dword ptr [rax+0BCh], 100h
0x180124170  jnz     short loc_1801241B8
0x180124172  lea     rcx, aPageallocatoru; "PageAllocatorUseSystemHeap"
0x180124179  call    ?ReadBooleanFromOleKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromOleKey(ushort const *,bool)
0x18012417e  lea     rcx, aPageallocators; "PageAllocatorSystemHeapIsPrivate"
0x180124185  mov     cs:?s_fPgAllocUseSystemHeap@ComVerifierSettings@@0_NA, al; bool ComVerifierSettings::s_fPgAllocUseSystemHeap
0x18012418b  call    ?ReadBooleanFromOleKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromOleKey(ushort const *,bool)
0x180124190  mov     cs:?s_fPgAllocHeapIsPrivate@ComVerifierSettings@@0_NA, al; bool ComVerifierSettings::s_fPgAllocHeapIsPrivate
0x180124196  call    ?ReadULongFromOleKey@ComVerifierSettings@@CAKPEBGK@Z; ComVerifierSettings::ReadULongFromOleKey(ushort const *,ulong)
0x18012419b  mov     cs:?s_dwAggressiveMTATesting@ComVerifierSettings@@0KA, eax; ulong ComVerifierSettings::s_dwAggressiveMTATesting
0x1801241a1  mov     rbx, [rsp+28h+arg_10]
0x1801241a6  lea     rax, ?s_singleton@ComVerifierSettings@@0V1@A; ComVerifierSettings ComVerifierSettings::s_singleton
0x1801241ad  mov     rsi, [rsp+28h+arg_18]
0x1801241b2  add     rsp, 20h
0x1801241b6  pop     rdi
0x1801241b7  retn
0x1801241b8  lea     rcx, aVerifierDll; "verifier.dll"
0x1801241bf  call    cs:__imp_GetModuleHandleW
0x1801241c5  mov     rbx, rax
0x1801241c8  mov     esi, 3E8h
0x1801241cd  test    rax, rax
0x1801241d0  jz      short loc_180124206
0x1801241d2  lea     rdx, aVerifierqueryr; "VerifierQueryRuntimeFlags"
0x1801241d9  mov     rcx, rax; hModule
0x1801241dc  call    cs:__imp_GetProcAddress
0x1801241e2  test    rax, rax
0x1801241e5  jz      short loc_180124206
0x1801241e7  lea     rdx, [rsp+28h+ulFlags]
0x1801241ec  mov     dword ptr [rsp+28h+fEnabled], edi
0x1801241f0  lea     rcx, [rsp+28h+fEnabled]
0x1801241f5  mov     [rsp+28h+ulFlags], edi
0x1801241f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801241fe  test    eax, eax
0x180124200  jz      loc_18024D9E0
0x180124206  mov     rax, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18012420d  test    rax, rax
0x180124210  jz      loc_180124172
0x180124216  jmp     loc_18024DA54
0x18024d9e0  cmp     dword ptr [rsp+28h+fEnabled], edi
0x18024d9e4  jz      loc_180124206
0x18024d9ea  test    [rsp+28h+ulFlags], 100h
0x18024d9f2  jz      loc_180124206
0x18024d9f8  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18024d9ff  xor     edx, edx; dwFlags
0x18024da01  lea     r8d, [rdx+50h]; dwBytes
0x18024da05  call    cs:__imp_HeapAlloc
0x18024da0b  test    rax, rax
0x18024da0e  jz      short loc_18024DA45
0x18024da10  mov     [rax], rdi
0x18024da13  mov     [rax+8], rdi
0x18024da17  mov     [rax+10h], edi
0x18024da1a  mov     [rax+14h], di
0x18024da1e  mov     [rax+16h], dil
0x18024da22  mov     dword ptr [rax+18h], 0Ah
0x18024da29  mov     [rax+1Ch], esi
0x18024da2c  mov     [rax+20h], esi
0x18024da2f  mov     [rax+28h], rdi
0x18024da33  mov     [rax+30h], rdi
0x18024da37  mov     [rax+38h], rdi
0x18024da3b  mov     [rax+40h], rdi
0x18024da3f  mov     [rax+48h], rdi
0x18024da43  jmp     short loc_18024DA48
0x18024da45  mov     rax, rdi
0x18024da48  mov     cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState, rax; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024da4f  jmp     loc_18012420D
0x18024da54  lea     rdx, aVerifierisdlle; "VerifierIsDllEntryActive"
0x18024da5b  mov     rcx, rbx; hModule
0x18024da5e  call    cs:__imp_GetProcAddress
0x18024da64  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024da6b  lea     rdx, aVerifieriscurr; "VerifierIsCurrentThreadHoldingLocks"
0x18024da72  mov     [rcx+28h], rax
0x18024da76  mov     rcx, rbx; hModule
0x18024da79  call    cs:__imp_GetProcAddress
0x18024da7f  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024da86  lea     rdx, aVerifieraddfre; "VerifierAddFreeMemoryCallback"
0x18024da8d  mov     [rcx+30h], rax
0x18024da91  mov     rcx, rbx; hModule
0x18024da94  call    cs:__imp_GetProcAddress
0x18024da9a  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024daa1  lea     rdx, aVerifierdelete; "VerifierDeleteFreeMemoryCallback"
0x18024daa8  mov     [rcx+38h], rax
0x18024daac  mov     rcx, rbx; hModule
0x18024daaf  call    cs:__imp_GetProcAddress
0x18024dab5  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dabc  lea     rdx, aVerifiergetpro; "VerifierGetPropertyValueByName"
0x18024dac3  mov     [rcx+40h], rax
0x18024dac7  mov     rcx, rbx; hModule
0x18024daca  call    cs:__imp_GetProcAddress
0x18024dad0  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dad7  mov     dl, 1; fDefault
0x18024dad9  mov     [rcx+48h], rax
0x18024dadd  lea     rcx, aComenabledllma; "ComEnableDllMainChecks"
0x18024dae4  mov     rax, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024daeb  mov     [rax], dil
0x18024daee  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024daf3  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dafa  mov     dl, 1; fDefault
0x18024dafc  mov     [rcx+1], al
0x18024daff  lea     rcx, aCombreakonalle; "ComBreakOnAllExceptions"
0x18024db06  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024db0b  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024db12  xor     edx, edx; fDefault
0x18024db14  mov     [rcx+2], al
0x18024db17  lea     rcx, aComverifylocks; "ComVerifyLocksOnCall"
0x18024db1e  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024db23  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024db2a  mov     dl, 1; fDefault
0x18024db2c  mov     [rcx+3], al
0x18024db2f  lea     rcx, aComverifythrea; "ComVerifyThreadState"
0x18024db36  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024db3b  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024db42  mov     dl, 1; fDefault
0x18024db44  mov     [rcx+4], al
0x18024db47  lea     rcx, aComverifychann; "ComVerifyChannelState"
0x18024db4e  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024db53  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024db5a  mov     dl, 1; fDefault
0x18024db5c  mov     [rcx+5], al
0x18024db5f  lea     rcx, aComverifyolein; "ComVerifyOleInitCalled"
0x18024db66  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024db6b  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024db72  mov     dl, 1; fDefault
0x18024db74  mov     [rcx+6], al
0x18024db77  lea     rcx, aComverifysecur; "ComVerifySecurity"
0x18024db7e  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024db83  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024db8a  mov     dl, 1; fDefault
0x18024db8c  mov     [rcx+7], al
0x18024db8f  lea     rcx, aComverifyproxi; "ComVerifyProxies"
0x18024db96  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024db9b  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dba2  mov     dl, 1; fDefault
0x18024dba4  mov     [rcx+8], al
0x18024dba7  lea     rcx, aComverifyclass; "ComVerifyClassFactory"
0x18024dbae  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dbb3  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dbba  mov     dl, 1; fDefault
0x18024dbbc  mov     [rcx+9], al
0x18024dbbf  lea     rcx, aComenableobjec; "ComEnableObjectTracking"
0x18024dbc6  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dbcb  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dbd2  mov     dl, 1; fDefault
0x18024dbd4  mov     [rcx+0Ah], al
0x18024dbd7  lea     rcx, aComenablevtblt; "ComEnableVTBLTracking"
0x18024dbde  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dbe3  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dbea  mov     [rcx+0Bh], al
0x18024dbed  xor     edx, edx; fDefault
0x18024dbef  lea     rcx, aComverifygetsl; "ComVerifyGetSlowStacks"
0x18024dbf6  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dbfb  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dc02  mov     dl, 1; fDefault
0x18024dc04  mov     [rcx+11h], al
0x18024dc07  lea     rcx, aPageallocatoru; "PageAllocatorUseSystemHeap"
0x18024dc0e  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dc13  mov     dl, 1; fDefault
0x18024dc15  mov     cs:?s_fPgAllocUseSystemHeap@ComVerifierSettings@@0_NA, al; bool ComVerifierSettings::s_fPgAllocUseSystemHeap
0x18024dc1b  lea     rcx, aPageallocators; "PageAllocatorSystemHeapIsPrivate"
0x18024dc22  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dc27  xor     edx, edx; fDefault
0x18024dc29  mov     cs:?s_fPgAllocHeapIsPrivate@ComVerifierSettings@@0_NA, al; bool ComVerifierSettings::s_fPgAllocHeapIsPrivate
0x18024dc2f  lea     rcx, aCheckunrecomme; "CheckUnrecommendedUsageFromAPC"
0x18024dc36  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dc3b  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dc42  mov     dl, 1; fDefault
0x18024dc44  mov     [rcx+12h], al
0x18024dc47  lea     rcx, aCheckmarshalin; "CheckMarshalingToUntrustedProcess"
0x18024dc4e  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dc53  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dc5a  xor     edx, edx; fDefault
0x18024dc5c  mov     [rcx+13h], al
0x18024dc5f  lea     rcx, aCheckclassicma; "CheckClassicMarshalingToUntrustedProces"...
0x18024dc66  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dc6b  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dc72  xor     edx, edx; fDefault
0x18024dc74  mov     [rcx+14h], al
0x18024dc77  lea     rcx, aComverifyfatal; "ComVerifyFatalExceptionHandlingDisabled"
0x18024dc7e  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dc83  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dc8a  mov     edx, 0Ah; ulDefault
0x18024dc8f  mov     [rcx+15h], al
0x18024dc92  lea     rcx, aCommaxstacktra; "ComMaxStackTracesPerThread"
0x18024dc99  call    ?ReadULongFromImageOptionsKey@ComVerifierSettings@@CAKPEBGK@Z; ComVerifierSettings::ReadULongFromImageOptionsKey(ushort const *,ulong)
0x18024dc9e  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dca5  mov     edx, esi; ulDefault
0x18024dca7  mov     [rcx+18h], eax
0x18024dcaa  lea     rcx, aCommaxstacktra_0; "ComMaxStackTracesPerProcess"
0x18024dcb1  call    ?ReadULongFromImageOptionsKey@ComVerifierSettings@@CAKPEBGK@Z; ComVerifierSettings::ReadULongFromImageOptionsKey(ushort const *,ulong)
0x18024dcb6  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dcbd  mov     dl, 1; fDefault
0x18024dcbf  mov     [rcx+1Ch], eax
0x18024dcc2  lea     rcx, aComcheckpremat; "ComCheckPrematureStubRundown"
0x18024dcc9  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dcce  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dcd5  mov     dl, 1; fDefault
0x18024dcd7  mov     [rcx+0Eh], al
0x18024dcda  lea     rcx, aComwinrtasyncc; "ComWinrtAsyncCheckPatternContract"
0x18024dce1  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dce6  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dced  xor     edx, edx; fDefault
0x18024dcef  mov     [rcx+0Fh], al
0x18024dcf2  lea     rcx, aComwinrtasyncl; "ComWinrtAsyncLearningMode"
0x18024dcf9  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dcfe  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dd05  mov     dl, 1; fDefault
0x18024dd07  mov     [rcx+10h], al
0x18024dd0a  lea     rcx, aComenableexitp; "ComEnableExitProcessChecks"
0x18024dd11  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dd16  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; this
0x18024dd1d  mov     [rcx+16h], al
0x18024dd20  call    ?ReadAvrfProperties@ComVerifierSettings@@AEAA_NXZ; ComVerifierSettings::ReadAvrfProperties(void)
0x18024dd25  test    al, al
0x18024dd27  jnz     loc_1801241A1
0x18024dd2d  mov     dl, 1; fDefault
0x18024dd2f  lea     rcx, aComenableaggre; "ComEnableAggressiveDllUnload"
0x18024dd36  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dd3b  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dd42  xor     edx, edx; fDefault
0x18024dd44  mov     [rcx+0Dh], al
0x18024dd47  lea     rcx, aComenablesecbl; "ComEnableSecBlanketChecks"
0x18024dd4e  call    ?ReadBooleanFromImageOptionsKey@ComVerifierSettings@@CA_NPEBG_N@Z; ComVerifierSettings::ReadBooleanFromImageOptionsKey(ushort const *,bool)
0x18024dd53  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dd5a  mov     edx, esi; ulDefault
0x18024dd5c  mov     [rcx+0Ch], al
0x18024dd5f  lea     rcx, aAggressivedllu; "AggressiveDllUnloadPeriod"
0x18024dd66  call    ?ReadULongFromImageOptionsKey@ComVerifierSettings@@CAKPEBGK@Z; ComVerifierSettings::ReadULongFromImageOptionsKey(ushort const *,ulong)
0x18024dd6b  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dd72  mov     [rcx+20h], eax
0x18024dd75  mov     rcx, cs:?s_singleton@ComVerifierSettings@@0V1@A._pSettingsState; ComVerifierSettings ComVerifierSettings::s_singleton ...
0x18024dd7c  mov     eax, [rcx+20h]
0x18024dd7f  sub     eax, 64h ; 'd'
0x18024dd82  cmp     eax, 0E9FCh
0x18024dd87  jbe     short loc_18024DD8C
0x18024dd89  mov     [rcx+20h], esi
0x18024dd8c  xor     edx, edx; ulDefault
0x18024dd8e  lea     rcx, aAggressivemtat; "AggressiveMTATesting"
0x18024dd95  call    ?ReadULongFromImageOptionsKey@ComVerifierSettings@@CAKPEBGK@Z; ComVerifierSettings::ReadULongFromImageOptionsKey(ushort const *,ulong)
0x18024dd9a  nop
0x18024dd9b  jmp     loc_18012419B
```
