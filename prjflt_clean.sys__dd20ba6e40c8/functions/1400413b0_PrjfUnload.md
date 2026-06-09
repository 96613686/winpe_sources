# PrjfUnload

- ea: `0x1400413b0`
- end: `0x14004161f`
- name: `PrjfUnload`
- size: `623`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1400099c8`
- `0x140009a00`
- `0x14000d128`
- `0x140036f5c`
- `0x1400413b0`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004159b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14004159b`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400415d2`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400415d2`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400415f5`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400415f5`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400414f0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041503`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041516`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041529`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14004153c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14004154f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041562`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041575`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041588`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400414f0`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041503`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041516`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041529`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14004153c`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14004154f`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041562`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041575`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140041588`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400413e8`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004147d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400413e8`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004147d`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400413bf`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400413bf`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x1400414c0`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x1400414dd`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x1400414c0`
- `FLTMGR!FltDeleteExtraCreateParameterLookasideList` at `0x1400414dd`
- `FLTMGR!FltUnregisterFilter` at `0x1400414a3`
- `FLTMGR!FltUnregisterFilter` at `0x1400414a3`
- `FLTMGR!FltCloseCommunicationPort` at `0x140041490`
- `FLTMGR!FltCloseCommunicationPort` at `0x140041490`

## pseudocode

```c
__int64 __fastcall PrjfUnload(char a1)
{
  int v2; // edx
  int v3; // r8d
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8

  ExAcquireFastMutex(&FastMutex);
  if ( !dword_14001A584 || (a1 & 1) != 0 )
  {
    byte_14001A580 = 1;
    ExReleaseFastMutex(&FastMutex);
    FltCloseCommunicationPort(ServerPort);
    FltUnregisterFilter(Globals);
    FltDeleteExtraCreateParameterLookasideList(Globals, &unk_14001A640, 0);
    FltDeleteExtraCreateParameterLookasideList(Globals, &unk_14001A5C0, 0);
    ExDeletePagedLookasideList(&stru_14001A6C0);
    ExDeletePagedLookasideList(&stru_14001A740);
    ExDeletePagedLookasideList(&Lookaside);
    ExDeletePagedLookasideList(&stru_14001A840);
    ExDeletePagedLookasideList(&stru_14001A8C0);
    ExDeletePagedLookasideList(&stru_14001A940);
    ExDeletePagedLookasideList(&stru_14001A9C0);
    ExDeletePagedLookasideList(&stru_14001AA40);
    ExDeletePagedLookasideList(&stru_14001AAC0);
    ExDeleteNPagedLookasideList(&stru_14001AB40);
    if ( (Microsoft_Windows_ProjFS_FilterEnableBits & 2) != 0 )
      McTemplateK0_EtwWriteTransfer(v5, &ProjFsUnloadSuccessful);
    McGenEventUnregister_EtwUnregister();
    PrjfTelemetryAndTracingCleanup(v7, v6, v8);
    if ( g_wil_details_featureChangeNotification )
    {
      RtlUnregisterFeatureConfigurationChangeNotification();
      g_wil_details_featureChangeNotification = 0;
    }
    if ( g_wil_details_featureUsageProvider )
    {
      RtlUnregisterFeatureUsageProvider();
      g_wil_details_featureUsageProvider = 0;
    }
    g_wil_details_isFeatureStagingInitialized = 0;
    return 0;
  }
  else
  {
    ExReleaseFastMutex(&FastMutex);
    if ( (BYTE2(xmmword_14001A3E0) & 1) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = BYTE2(xmmword_14001A3E0) & 1;
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        1040,
        v2,
        v3,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        4,
        16,
        38,
        (__int64)&WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\prjflt.c",
        97,
        187);
    }
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x1400413b0  push    rbx
0x1400413b2  sub     rsp, 60h
0x1400413b6  mov     ebx, ecx
0x1400413b8  lea     rcx, FastMutex; FastMutex
0x1400413bf  call    cs:__imp_ExAcquireFastMutex
0x1400413c6  nop     dword ptr [rax+rax+00h]
0x1400413cb  cmp     cs:dword_14001A584, 0
0x1400413d2  jz      loc_14004146F
0x1400413d8  test    bl, 1
0x1400413db  jnz     loc_14004146F
0x1400413e1  lea     rcx, FastMutex; FastMutex
0x1400413e8  call    cs:__imp_ExReleaseFastMutex
0x1400413ef  nop     dword ptr [rax+rax+00h]
0x1400413f4  mov     dl, byte ptr cs:xmmword_14001A3E0+2
0x1400413fa  lea     rax, WPP_RECORDER_INITIALIZED
0x140041401  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140041408  mov     ebx, 0C00000BBh
0x14004140d  setnz   r8b
0x140041411  and     dl, 1
0x140041414  jnz     short loc_14004141B
0x140041416  test    r8b, r8b
0x140041419  jz      short loc_140041468
0x14004141b  mov     [rsp+68h+var_18], ebx
0x14004141f  lea     r9, aOnecoreBaseFsG_0; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140041426  mov     [rsp+68h+var_20], 661h
0x14004142e  mov     ecx, 410h
0x140041433  mov     [rsp+68h+var_28], r9
0x140041438  lea     r9, WPP_623eb7f766e03f44c574d6181df1dc88_Traceguids
0x14004143f  mov     [rsp+68h+var_30], r9
0x140041444  mov     r9, cs:WPP_GLOBAL_Control
0x14004144b  mov     [rsp+68h+var_38], 26h ; '&'
0x140041452  mov     [rsp+68h+var_40], 10h
0x14004145a  mov     [rsp+68h+var_48], 4
0x14004145f  mov     r9, [r9+40h]
0x140041463  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140041468  mov     eax, ebx
0x14004146a  jmp     loc_140041618
0x14004146f  lea     rcx, FastMutex; FastMutex
0x140041476  mov     cs:byte_14001A580, 1
0x14004147d  call    cs:__imp_ExReleaseFastMutex
0x140041484  nop     dword ptr [rax+rax+00h]
0x140041489  mov     rcx, cs:ServerPort; ServerPort
0x140041490  call    cs:__imp_FltCloseCommunicationPort
0x140041497  nop     dword ptr [rax+rax+00h]
0x14004149c  mov     rcx, cs:Globals; Filter
0x1400414a3  call    cs:__imp_FltUnregisterFilter
0x1400414aa  nop     dword ptr [rax+rax+00h]
0x1400414af  mov     rcx, cs:Globals; Filter
0x1400414b6  lea     rdx, unk_14001A640; Lookaside
0x1400414bd  xor     r8d, r8d; Flags
0x1400414c0  call    cs:__imp_FltDeleteExtraCreateParameterLookasideList
0x1400414c7  nop     dword ptr [rax+rax+00h]
0x1400414cc  mov     rcx, cs:Globals; Filter
0x1400414d3  lea     rdx, unk_14001A5C0; Lookaside
0x1400414da  xor     r8d, r8d; Flags
0x1400414dd  call    cs:__imp_FltDeleteExtraCreateParameterLookasideList
0x1400414e4  nop     dword ptr [rax+rax+00h]
0x1400414e9  lea     rcx, stru_14001A6C0; Lookaside
0x1400414f0  call    cs:__imp_ExDeletePagedLookasideList
0x1400414f7  nop     dword ptr [rax+rax+00h]
0x1400414fc  lea     rcx, stru_14001A740; Lookaside
0x140041503  call    cs:__imp_ExDeletePagedLookasideList
0x14004150a  nop     dword ptr [rax+rax+00h]
0x14004150f  lea     rcx, Lookaside; Lookaside
0x140041516  call    cs:__imp_ExDeletePagedLookasideList
0x14004151d  nop     dword ptr [rax+rax+00h]
0x140041522  lea     rcx, stru_14001A840; Lookaside
0x140041529  call    cs:__imp_ExDeletePagedLookasideList
0x140041530  nop     dword ptr [rax+rax+00h]
0x140041535  lea     rcx, stru_14001A8C0; Lookaside
0x14004153c  call    cs:__imp_ExDeletePagedLookasideList
0x140041543  nop     dword ptr [rax+rax+00h]
0x140041548  lea     rcx, stru_14001A940; Lookaside
0x14004154f  call    cs:__imp_ExDeletePagedLookasideList
0x140041556  nop     dword ptr [rax+rax+00h]
0x14004155b  lea     rcx, stru_14001A9C0; Lookaside
0x140041562  call    cs:__imp_ExDeletePagedLookasideList
0x140041569  nop     dword ptr [rax+rax+00h]
0x14004156e  lea     rcx, stru_14001AA40; Lookaside
0x140041575  call    cs:__imp_ExDeletePagedLookasideList
0x14004157c  nop     dword ptr [rax+rax+00h]
0x140041581  lea     rcx, stru_14001AAC0; Lookaside
0x140041588  call    cs:__imp_ExDeletePagedLookasideList
0x14004158f  nop     dword ptr [rax+rax+00h]
0x140041594  lea     rcx, stru_14001AB40; Lookaside
0x14004159b  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400415a2  nop     dword ptr [rax+rax+00h]
0x1400415a7  test    cs:Microsoft_Windows_ProjFS_FilterEnableBits, 2
0x1400415ae  jz      short loc_1400415BC
0x1400415b0  lea     rdx, ProjFsUnloadSuccessful
0x1400415b7  call    McTemplateK0_EtwWriteTransfer
0x1400415bc  call    McGenEventUnregister_EtwUnregister
0x1400415c1  call    PrjfTelemetryAndTracingCleanup
0x1400415c6  mov     rcx, cs:g_wil_details_featureChangeNotification
0x1400415cd  test    rcx, rcx
0x1400415d0  jz      short loc_1400415E9
0x1400415d2  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400415d9  nop     dword ptr [rax+rax+00h]
0x1400415de  mov     cs:g_wil_details_featureChangeNotification, 0
0x1400415e9  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400415f0  test    rcx, rcx
0x1400415f3  jz      short loc_14004160C
0x1400415f5  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400415fc  nop     dword ptr [rax+rax+00h]
0x140041601  mov     cs:g_wil_details_featureUsageProvider, 0
0x14004160c  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x140041616  xor     eax, eax
0x140041618  add     rsp, 60h
0x14004161c  pop     rbx
0x14004161d  retn
```
