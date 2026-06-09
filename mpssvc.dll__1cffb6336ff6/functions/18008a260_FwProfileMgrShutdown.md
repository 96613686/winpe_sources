# FwProfileMgrShutdown

- ea: `0x18008a260`
- end: `0x18008a388`
- name: `FwProfileMgrShutdown`
- size: `296`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180089520`

## callees

- `0x1800035c4`
- `0x180029b48`
- `0x180066564`
- `0x18006ffc8`
- `0x180085adc`
- `0x180086f00`
- `0x18008a260`
- `0x1800ac0a8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008a327`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008a33c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008a327`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008a33c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008a28c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008a28c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008a299`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008a299`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008a27c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18008a27c`
- `fwbase!FwChangeSourceSignal` at `0x18008a2e7`
- `fwbase!FwChangeSourceSignal` at `0x18008a2e7`
- `fwbase!FwRegNotifyDestroy` at `0x18008a2f4`
- `fwbase!FwRegNotifyDestroy` at `0x18008a2f4`

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
  if ( qword_180131400 )
  {
    SetThreadpoolTimer(qword_180131400, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(qword_180131400, 1);
    CloseThreadpoolTimer(qword_180131400);
    qword_180131400 = 0;
  }
  NetioUninitializeHistogram((struct _HISTOGRAM *)g_timeAddRuleHistogram, a2);
  NetioUninitializeHistogram((struct _HISTOGRAM *)g_timeSetRuleHistogram, v3);
  NetioUninitializeHistogram((struct _HISTOGRAM *)g_timeDeleteRuleHistogram, v4);
  NetioUninitializeHistogram((struct _HISTOGRAM *)g_timeEnumRuleHistogram, v5);
  NetioUninitializeHistogram((struct _HISTOGRAM *)g_timeQueryRuleHistogram, v6);
  FwCancelLock();
  FwChangeSourceSignal();
  FwRegNotifyDestroy(gFwProfileMgr[0]);
  FwUpdateALL(5);
  qword_1801313E0 = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl'::`2'::impl);
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
    FwFreeStore(v2, &qword_18012E2B8[121 * v2]);
    ++v2;
  }
  while ( v2 < 0xD );
  return memset_0(gFwProfileMgr, 0, 0x3168u);
}

```

## disassembly

```asm
0x18008a260  push    rbx
0x18008a262  sub     rsp, 20h
0x18008a266  mov     rcx, cs:qword_180131400; pti
0x18008a26d  xor     ebx, ebx
0x18008a26f  test    rcx, rcx
0x18008a272  jz      short loc_18008A2A6
0x18008a274  xor     r9d, r9d; msWindowLength
0x18008a277  xor     r8d, r8d; msPeriod
0x18008a27a  xor     edx, edx; pftDueTime
0x18008a27c  call    cs:__imp_SetThreadpoolTimer
0x18008a282  mov     rcx, cs:qword_180131400; pti
0x18008a289  lea     edx, [rbx+1]; fCancelPendingCallbacks
0x18008a28c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18008a292  mov     rcx, cs:qword_180131400; pti
0x18008a299  call    cs:__imp_CloseThreadpoolTimer
0x18008a29f  mov     cs:qword_180131400, rbx
0x18008a2a6  lea     rcx, g_timeAddRuleHistogram; struct _HISTOGRAM *
0x18008a2ad  call    ?NetioUninitializeHistogram@@YAXPEAU_HISTOGRAM@@K@Z; NetioUninitializeHistogram(_HISTOGRAM *,ulong)
0x18008a2b2  lea     rcx, g_timeSetRuleHistogram; struct _HISTOGRAM *
0x18008a2b9  call    ?NetioUninitializeHistogram@@YAXPEAU_HISTOGRAM@@K@Z; NetioUninitializeHistogram(_HISTOGRAM *,ulong)
0x18008a2be  lea     rcx, g_timeDeleteRuleHistogram; struct _HISTOGRAM *
0x18008a2c5  call    ?NetioUninitializeHistogram@@YAXPEAU_HISTOGRAM@@K@Z; NetioUninitializeHistogram(_HISTOGRAM *,ulong)
0x18008a2ca  lea     rcx, g_timeEnumRuleHistogram; struct _HISTOGRAM *
0x18008a2d1  call    ?NetioUninitializeHistogram@@YAXPEAU_HISTOGRAM@@K@Z; NetioUninitializeHistogram(_HISTOGRAM *,ulong)
0x18008a2d6  lea     rcx, g_timeQueryRuleHistogram; struct _HISTOGRAM *
0x18008a2dd  call    ?NetioUninitializeHistogram@@YAXPEAU_HISTOGRAM@@K@Z; NetioUninitializeHistogram(_HISTOGRAM *,ulong)
0x18008a2e2  call    FwCancelLock
0x18008a2e7  call    cs:__imp_FwChangeSourceSignal
0x18008a2ed  mov     rcx, cs:gFwProfileMgr
0x18008a2f4  call    cs:__imp_FwRegNotifyDestroy
0x18008a2fa  mov     ecx, 5
0x18008a2ff  call    ?FwUpdateALL@@YAJW4_tag_FW_BATCH_UPDATE_OP@@@Z; FwUpdateALL(_tag_FW_BATCH_UPDATE_OP)
0x18008a304  mov     cs:qword_1801313E0, rbx
0x18008a30b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Firewall_042024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024> `wil::Feature<__WilFeatureTraits_Feature_Firewall_042024>::GetImpl(void)'::`2'::impl
0x18008a312  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Firewall_042024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Firewall_042024>::__private_IsEnabled(void)
0x18008a317  mov     rcx, cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA; hLibModule
0x18008a31e  test    al, al
0x18008a320  jz      short loc_18008A337
0x18008a322  test    rcx, rcx
0x18008a325  jz      short loc_18008A342
0x18008a327  call    cs:__imp_FreeLibrary
0x18008a32d  mov     rcx, rbx; hLibModule
0x18008a330  mov     cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * hFwpuclntPrivate
0x18008a337  test    rcx, rcx
0x18008a33a  jz      short loc_18008A342
0x18008a33c  call    cs:__imp_FreeLibrary
0x18008a342  mov     cs:?hFwpuclntPrivate@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * hFwpuclntPrivate
0x18008a349  call    ?FwPerfMonShutdown@@YAXXZ; FwPerfMonShutdown(void)
0x18008a34e  mov     eax, ebx
0x18008a350  mov     ecx, ebx
0x18008a352  imul    rdx, rax, 3C8h
0x18008a359  lea     rax, qword_18012E2B8
0x18008a360  add     rdx, rax
0x18008a363  call    ?FwFreeStore@@YAXW4_tag_FW_STORE_TYPE@@PEAU_tag_FW_STORE@@@Z; FwFreeStore(_tag_FW_STORE_TYPE,_tag_FW_STORE *)
0x18008a368  inc     ebx
0x18008a36a  cmp     ebx, 0Dh
0x18008a36d  jb      short loc_18008A34E
0x18008a36f  xor     edx, edx; Val
0x18008a371  lea     rcx, gFwProfileMgr; void *
0x18008a378  mov     r8d, 3168h; Size
0x18008a37e  add     rsp, 20h
0x18008a382  pop     rbx
0x18008a383  jmp     memset_0
```
