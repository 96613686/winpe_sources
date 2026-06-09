# FwProfileMgrShutdown

- ea: `0x18008ea20`
- end: `0x18008eb72`
- name: `FwProfileMgrShutdown`
- size: `338`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18008dc90`

## callees

- `0x180003754`
- `0x18002d340`
- `0x18006a8a8`
- `0x180073488`
- `0x180089e5c`
- `0x18008b4a4`
- `0x18008ea20`
- `0x1800b25e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008eb05`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008eb20`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008eb05`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008eb20`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008ea52`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008ea52`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008ea65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008ea65`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008ea3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008ea3c`
- `fwbase!FwChangeSourceSignal` at `0x18008eab9`
- `fwbase!FwChangeSourceSignal` at `0x18008eab9`
- `fwbase!FwRegNotifyDestroy` at `0x18008eacc`
- `fwbase!FwRegNotifyDestroy` at `0x18008eacc`

## pseudocode

```c
void *__fastcall FwProfileMgrShutdown(__int64 a1, unsigned int a2)
{
  unsigned int v2; // ebx
  unsigned int v3; // edx
  unsigned int v4; // edx
  unsigned int v5; // edx
  unsigned int v6; // edx
  char IsEnabled; // al
  HMODULE v8; // rcx

  v2 = 0;
  if ( qword_1801375C0 )
  {
    SetThreadpoolTimer(qword_1801375C0, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(qword_1801375C0, 1);
    CloseThreadpoolTimer(qword_1801375C0);
    qword_1801375C0 = 0;
  }
  NetioUninitializeHistogram((struct _HISTOGRAM *)g_timeAddRuleHistogram, a2);
  NetioUninitializeHistogram((struct _HISTOGRAM *)&g_timeSetRuleHistogram, v3);
  NetioUninitializeHistogram((struct _HISTOGRAM *)g_timeDeleteRuleHistogram, v4);
  NetioUninitializeHistogram((struct _HISTOGRAM *)g_timeEnumRuleHistogram, v5);
  NetioUninitializeHistogram((struct _HISTOGRAM *)g_timeQueryRuleHistogram, v6);
  FwCancelLock();
  FwChangeSourceSignal();
  FwRegNotifyDestroy(gFwProfileMgr[0]);
  FwUpdateALL(5);
  qword_1801375A0 = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
  v8 = hFwpuclntPrivate;
  if ( IsEnabled )
  {
    if ( !hFwpuclntPrivate )
      goto LABEL_8;
    FreeLibrary(hFwpuclntPrivate);
    v8 = 0;
    hFwpuclntPrivate = 0;
  }
  if ( v8 )
    FreeLibrary(v8);
LABEL_8:
  hFwpuclntPrivate = 0;
  FwPerfMonShutdown();
  do
  {
    FwFreeStore(v2, &qword_180134478[121 * v2]);
    ++v2;
  }
  while ( v2 < 0xD );
  return memset_0(gFwProfileMgr, 0, 0x3168u);
}

```

## disassembly

```asm
0x18008ea20  push    rbx
0x18008ea22  sub     rsp, 20h
0x18008ea26  mov     rcx, cs:qword_1801375C0; pti
0x18008ea2d  xor     ebx, ebx
0x18008ea2f  test    rcx, rcx
0x18008ea32  jz      short loc_18008EA78
0x18008ea34  xor     r9d, r9d; msWindowLength
0x18008ea37  xor     r8d, r8d; msPeriod
0x18008ea3a  xor     edx, edx; pftDueTime
0x18008ea3c  call    cs:__imp_SetThreadpoolTimer
0x18008ea43  nop     dword ptr [rax+rax+00h]
0x18008ea48  mov     rcx, cs:qword_1801375C0; pti
0x18008ea4f  lea     edx, [rbx+1]; fCancelPendingCallbacks
0x18008ea52  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18008ea59  nop     dword ptr [rax+rax+00h]
0x18008ea5e  mov     rcx, cs:qword_1801375C0; pti
0x18008ea65  call    cs:__imp_CloseThreadpoolTimer
0x18008ea6c  nop     dword ptr [rax+rax+00h]
0x18008ea71  mov     cs:qword_1801375C0, rbx
0x18008ea78  lea     rcx, g_timeAddRuleHistogram; struct _HISTOGRAM *
0x18008ea7f  call    ?NetioUninitializeHistogram@@YAXPEAU_HISTOGRAM@@K@Z; NetioUninitializeHistogram(_HISTOGRAM *,ulong)
0x18008ea84  lea     rcx, g_timeSetRuleHistogram; struct _HISTOGRAM *
0x18008ea8b  call    ?NetioUninitializeHistogram@@YAXPEAU_HISTOGRAM@@K@Z; NetioUninitializeHistogram(_HISTOGRAM *,ulong)
0x18008ea90  lea     rcx, g_timeDeleteRuleHistogram; struct _HISTOGRAM *
0x18008ea97  call    ?NetioUninitializeHistogram@@YAXPEAU_HISTOGRAM@@K@Z; NetioUninitializeHistogram(_HISTOGRAM *,ulong)
0x18008ea9c  lea     rcx, g_timeEnumRuleHistogram; struct _HISTOGRAM *
0x18008eaa3  call    ?NetioUninitializeHistogram@@YAXPEAU_HISTOGRAM@@K@Z; NetioUninitializeHistogram(_HISTOGRAM *,ulong)
0x18008eaa8  lea     rcx, g_timeQueryRuleHistogram; struct _HISTOGRAM *
0x18008eaaf  call    ?NetioUninitializeHistogram@@YAXPEAU_HISTOGRAM@@K@Z; NetioUninitializeHistogram(_HISTOGRAM *,ulong)
0x18008eab4  call    FwCancelLock
0x18008eab9  call    cs:__imp_FwChangeSourceSignal
0x18008eac0  nop     dword ptr [rax+rax+00h]
0x18008eac5  mov     rcx, cs:gFwProfileMgr
0x18008eacc  call    cs:__imp_FwRegNotifyDestroy
0x18008ead3  nop     dword ptr [rax+rax+00h]
0x18008ead8  mov     ecx, 5
0x18008eadd  call    ?FwUpdateALL@@YAJW4_tag_FW_BATCH_UPDATE_OP@@@Z; FwUpdateALL(_tag_FW_BATCH_UPDATE_OP)
0x18008eae2  mov     cs:qword_1801375A0, rbx
0x18008eae9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18008eaf0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18008eaf5  mov     rcx, cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA; hLibModule
0x18008eafc  test    al, al
0x18008eafe  jz      short loc_18008EB1B
0x18008eb00  test    rcx, rcx
0x18008eb03  jz      short loc_18008EB2C
0x18008eb05  call    cs:__imp_FreeLibrary
0x18008eb0c  nop     dword ptr [rax+rax+00h]
0x18008eb11  mov     rcx, rbx; hLibModule
0x18008eb14  mov     cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * hFwpuclntPrivate
0x18008eb1b  test    rcx, rcx
0x18008eb1e  jz      short loc_18008EB2C
0x18008eb20  call    cs:__imp_FreeLibrary
0x18008eb27  nop     dword ptr [rax+rax+00h]
0x18008eb2c  mov     cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * hFwpuclntPrivate
0x18008eb33  call    ?FwPerfMonShutdown@@YAXXZ; FwPerfMonShutdown(void)
0x18008eb38  mov     eax, ebx
0x18008eb3a  mov     ecx, ebx
0x18008eb3c  imul    rdx, rax, 3C8h
0x18008eb43  lea     rax, qword_180134478
0x18008eb4a  add     rdx, rax
0x18008eb4d  call    ?FwFreeStore@@YAXW4_tag_FW_STORE_TYPE@@PEAU_tag_FW_STORE@@@Z; FwFreeStore(_tag_FW_STORE_TYPE,_tag_FW_STORE *)
0x18008eb52  inc     ebx
0x18008eb54  cmp     ebx, 0Dh
0x18008eb57  jb      short loc_18008EB38
0x18008eb59  xor     edx, edx; Val
0x18008eb5b  lea     rcx, gFwProfileMgr; void *
0x18008eb62  mov     r8d, 3168h; Size
0x18008eb68  add     rsp, 20h
0x18008eb6c  pop     rbx
0x18008eb6d  jmp     memset_0
```
