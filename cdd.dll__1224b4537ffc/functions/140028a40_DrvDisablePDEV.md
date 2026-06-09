# DrvDisablePDEV

- ea: `0x140028a40`
- end: `0x140029129`
- name: `DrvDisablePDEV`
- size: `1769`
- prototype: `FN_DrvDisablePDEV`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14001d980`

## callees

- `0x140002470`
- `0x14000fbb4`
- `0x1400111c0`
- `0x1400190f8`
- `0x140019278`
- `0x14001a490`
- `0x140028a40`
- `0x140029130`
- `0x140029254`
- `0x14002cf5c`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400290ed`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400290ed`
- `ntoskrnl!ObfDereferenceObject` at `0x140028e07`
- `ntoskrnl!ObfDereferenceObject` at `0x140028e07`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x140028d57`
- `ntoskrnl!DbgkWerCaptureLiveKernelDump` at `0x140028d57`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140028b9c`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140028b9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028af3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028dcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028e21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028e42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028fbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028fdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029000`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029021`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029102`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028af3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028dcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028e21`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028e42`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028f9d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028fbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028fdf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029000`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029021`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029102`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028b12`
- `ntoskrnl!KeGetCurrentIrql` at `0x140028b12`
- `ntoskrnl!DbgPrint` at `0x140028cca`
- `ntoskrnl!DbgPrint` at `0x140028cca`
- `ntoskrnl!KdDebuggerEnabled` at `0x140028cb1`
- `watchdog!WdLogSingleEntry2` at `0x140028c75`
- `watchdog!WdLogSingleEntry2` at `0x140028c75`
- `watchdog!WdLogSingleEntry1` at `0x140028a95`
- `watchdog!WdLogSingleEntry1` at `0x140028a95`
- `watchdog!WdLogNewEntry5_WdError` at `0x140028c8c`
- `watchdog!WdLogNewEntry5_WdError` at `0x140028cef`
- `watchdog!WdLogNewEntry5_WdError` at `0x140028c8c`
- `watchdog!WdLogNewEntry5_WdError` at `0x140028cef`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140028b3e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140028d8f`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140028b3e`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140028d8f`
- `watchdog!WdLogSingleEntry0` at `0x140028b27`
- `watchdog!WdLogSingleEntry0` at `0x140028cd8`
- `watchdog!WdLogSingleEntry0` at `0x140028d78`
- `watchdog!WdLogSingleEntry0` at `0x140028b27`
- `watchdog!WdLogSingleEntry0` at `0x140028cd8`
- `watchdog!WdLogSingleEntry0` at `0x140028d78`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140028aac`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140028aac`
- `WIN32K!EngDeletePalette` at `0x140028c1f`
- `WIN32K!EngDeletePalette` at `0x140028c1f`
- `WIN32K!CddEngDeleteRgn` at `0x140028e61`
- `WIN32K!CddEngDeleteRgn` at `0x140028e80`
- `WIN32K!CddEngDeleteRgn` at `0x140028e9f`
- `WIN32K!CddEngDeleteRgn` at `0x140028ebe`
- `WIN32K!CddEngDeleteRgn` at `0x140028edd`
- `WIN32K!CddEngDeleteRgn` at `0x140028efc`
- `WIN32K!CddEngDeleteRgn` at `0x140028f1b`
- `WIN32K!CddEngDeleteRgn` at `0x140028f3a`
- `WIN32K!CddEngDeleteRgn` at `0x140029040`
- `WIN32K!CddEngDeleteRgn` at `0x14002905f`
- `WIN32K!CddEngDeleteRgn` at `0x140028e61`
- `WIN32K!CddEngDeleteRgn` at `0x140028e80`
- `WIN32K!CddEngDeleteRgn` at `0x140028e9f`
- `WIN32K!CddEngDeleteRgn` at `0x140028ebe`
- `WIN32K!CddEngDeleteRgn` at `0x140028edd`
- `WIN32K!CddEngDeleteRgn` at `0x140028efc`
- `WIN32K!CddEngDeleteRgn` at `0x140028f1b`
- `WIN32K!CddEngDeleteRgn` at `0x140028f3a`
- `WIN32K!CddEngDeleteRgn` at `0x140029040`
- `WIN32K!CddEngDeleteRgn` at `0x14002905f`
- `WIN32K!EngFreeMem` at `0x140028c3b`
- `WIN32K!EngFreeMem` at `0x140029086`
- `WIN32K!EngFreeMem` at `0x140029111`
- `WIN32K!EngFreeMem` at `0x140028c3b`
- `WIN32K!EngFreeMem` at `0x140029086`
- `WIN32K!EngFreeMem` at `0x140029111`

## string_xrefs

- `0x140028cc3`: `Not all redirection bitmaps are deleted at DrvDisablePDEV`
- `0x140028d50`: `cdd.dll`

## pseudocode

```c
void __stdcall DrvDisablePDEV(DHPDEV dhpdev)
{
  void (**v2)(void); // rdi
  _QWORD *v3; // rax
  void *v4; // rcx
  int v5; // r8d
  _QWORD *v6; // rax
  CStagingPool *v7; // rdi
  CStagingPool *v8; // rsi
  HPALETTE v9; // rcx
  void *v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  __int64 i; // rdi
  void *v15; // rcx
  void (__fastcall *v16)(_QWORD); // rax
  void *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  void *v28; // rcx
  void *v29; // rcx
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  void *v37; // rcx
  __int64 v38; // rcx
  void (__fastcall *v39)(__int64, _QWORD); // rax
  __int64 v40; // rcx
  void (__fastcall *v41)(__int64, _QWORD); // rax
  struct _LOOKASIDE_LIST_EX *v42; // rcx
  __int64 v43; // [rsp+50h] [rbp-38h] BYREF
  int v44; // [rsp+58h] [rbp-30h]

  v2 = (void (**)(void))(dhpdev + 106);
  if ( *((_QWORD *)dhpdev + 95) )
  {
    (*v2)();
    *((_QWORD *)dhpdev + 95) = 0;
  }
  if ( *((_QWORD *)dhpdev + 96) )
  {
    (*v2)();
    *((_QWORD *)dhpdev + 96) = 0;
  }
  WdLogSingleEntry1(4, dhpdev);
  WdLogGlobalForLineNumber = 1349;
  v3 = (_QWORD *)WdLogNewEntry5_WdEvent();
  v3[3] = gCddImageInfo;
  v3[4] = (unsigned int)dword_14003E570;
  v3[5] = 215857758;
  WdLogGlobalForLineNumber = 1349;
  CDDPDEV::DestroyBootGraphicsRelayAnimation((CDDPDEV *)dhpdev);
  v4 = (void *)*((_QWORD *)dhpdev + 331);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    *((_QWORD *)dhpdev + 331) = 0;
  }
  if ( *((_DWORD *)dhpdev + 1370) )
  {
    if ( KeGetCurrentIrql() )
    {
      WdLogSingleEntry0(1);
      WdLogGlobalForLineNumber = 785;
      v6 = (_QWORD *)WdLogNewEntry5_WdAssertion();
      v6[3] = gCddImageInfo;
      v6[4] = (unsigned int)dword_14003E570;
      v6[5] = 215857758;
      WdLogGlobalForLineNumber = 785;
    }
    CGuardMutexEx::CGuardMutexEx((CGuardMutexEx *)&v43, *((struct CDDMUTEX **)dhpdev + 686), v5);
    *((_DWORD *)dhpdev + 912) = 1;
    CddIssueCommand(dhpdev, 13);
    if ( v44 )
      ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(v43);
    CDDPDEV::DestroyInternalBitmaps((CDDPDEV *)dhpdev);
    WorkerThreadCleanup((struct CDDPDEV *)dhpdev);
    v7 = (CStagingPool *)(dhpdev + 1376);
    v8 = (CStagingPool *)(dhpdev + 1580);
  }
  else
  {
    v7 = (CStagingPool *)(dhpdev + 1376);
    CStagingPoolBase::DestroyStagingPool((CStagingPoolBase *)(dhpdev + 1376));
    v8 = (CStagingPool *)(dhpdev + 1580);
    CStagingPoolBase::DestroyStagingPool((CStagingPoolBase *)(dhpdev + 1580));
    CHwCommandBuffer::DestroyCommandBuffer((CHwCommandBuffer *)(dhpdev + 2098));
    CHwCommandBuffer::DestroyCommandBuffer((CHwCommandBuffer *)(dhpdev + 2636));
    *((_DWORD *)dhpdev + 686) &= ~0x100u;
  }
  CStagingPool::DestroyGdiSurfaces(v7);
  CStagingPool::DestroyGdiSurfaces(v8);
  v9 = (HPALETTE)*((_QWORD *)dhpdev + 3);
  if ( v9 )
  {
    EngDeletePalette(v9);
    *((_QWORD *)dhpdev + 3) = 0;
  }
  v10 = (void *)*((_QWORD *)dhpdev + 310);
  if ( v10 )
  {
    EngFreeMem(v10);
    *((_QWORD *)dhpdev + 310) = 0;
  }
  if ( *((_DWORD *)dhpdev + 1807) || *((DHPDEV *)dhpdev + 905) != dhpdev + 1810 )
  {
    WdLogSingleEntry2(2, dhpdev, *((unsigned int *)dhpdev + 1807));
    WdLogGlobalForLineNumber = 1394;
    v11 = (_QWORD *)WdLogNewEntry5_WdError();
    v11[3] = gCddImageInfo;
    v11[4] = (unsigned int)dword_14003E570;
    v11[5] = 215857758;
    WdLogGlobalForLineNumber = 1394;
    if ( (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Not all redirection bitmaps are deleted at DrvDisablePDEV");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 1398;
      v12 = (_QWORD *)WdLogNewEntry5_WdError();
      v12[3] = gCddImageInfo;
      v12[4] = (unsigned int)dword_14003E570;
      v12[5] = 215857758;
      WdLogGlobalForLineNumber = 1398;
      __debugbreak();
    }
    if ( byte_14003E390 )
    {
      DbgkWerCaptureLiveKernelDump(L"cdd.dll", 403, 2058, dhpdev, *((unsigned int *)dhpdev + 1807), 0, 0, 0, 0);
      byte_14003E390 = 0;
    }
  }
  if ( *((_QWORD *)dhpdev + 341) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1420;
    v13 = (_QWORD *)WdLogNewEntry5_WdAssertion();
    v13[3] = gCddImageInfo;
    v13[4] = (unsigned int)dword_14003E570;
    v13[5] = 215857758;
    WdLogGlobalForLineNumber = 1420;
  }
  for ( i = 0; i != 5; ++i )
  {
    v15 = (void *)*((_QWORD *)dhpdev + i + 326);
    if ( v15 )
    {
      ExFreePoolWithTag(v15, 0);
      *((_QWORD *)dhpdev + i + 326) = 0;
    }
  }
  v16 = (void (__fastcall *)(_QWORD))*((_QWORD *)dhpdev + 9);
  if ( v16 )
    v16(*((_QWORD *)dhpdev + 6));
  v17 = (void *)*((_QWORD *)dhpdev + 92);
  if ( v17 )
    ObfDereferenceObject(v17);
  v18 = (void *)*((_QWORD *)dhpdev + 360);
  if ( v18 )
  {
    ExFreePoolWithTag(v18, 0);
    *((_QWORD *)dhpdev + 360) = 0;
  }
  v19 = (void *)*((_QWORD *)dhpdev + 686);
  if ( v19 )
  {
    ExFreePoolWithTag(v19, 0);
    *((_QWORD *)dhpdev + 686) = 0;
  }
  v20 = *((_QWORD *)dhpdev + 359);
  if ( v20 )
  {
    CddEngDeleteRgn(v20);
    *((_QWORD *)dhpdev + 359) = 0;
  }
  v21 = *((_QWORD *)dhpdev + 358);
  if ( v21 )
  {
    CddEngDeleteRgn(v21);
    *((_QWORD *)dhpdev + 358) = 0;
  }
  v22 = *((_QWORD *)dhpdev + 357);
  if ( v22 )
  {
    CddEngDeleteRgn(v22);
    *((_QWORD *)dhpdev + 357) = 0;
  }
  v23 = *((_QWORD *)dhpdev + 356);
  if ( v23 )
  {
    CddEngDeleteRgn(v23);
    *((_QWORD *)dhpdev + 356) = 0;
  }
  v24 = *((_QWORD *)dhpdev + 355);
  if ( v24 )
  {
    CddEngDeleteRgn(v24);
    *((_QWORD *)dhpdev + 355) = 0;
  }
  v25 = *((_QWORD *)dhpdev + 353);
  if ( v25 )
  {
    CddEngDeleteRgn(v25);
    *((_QWORD *)dhpdev + 353) = 0;
  }
  v26 = *((_QWORD *)dhpdev + 354);
  if ( v26 )
  {
    CddEngDeleteRgn(v26);
    *((_QWORD *)dhpdev + 354) = 0;
  }
  v27 = *((_QWORD *)dhpdev + 352);
  if ( v27 )
  {
    CddEngDeleteRgn(v27);
    *((_QWORD *)dhpdev + 352) = 0;
  }
  v28 = (void *)*((_QWORD *)dhpdev + 361);
  if ( v28 )
  {
    ExFreePoolWithTag(v28, 0);
    *((_QWORD *)dhpdev + 361) = 0;
  }
  v29 = (void *)*((_QWORD *)dhpdev + 362);
  if ( v29 )
  {
    ExFreePoolWithTag(v29, 0);
    *((_QWORD *)dhpdev + 362) = 0;
  }
  v30 = (void *)*((_QWORD *)dhpdev + 363);
  if ( v30 )
  {
    ExFreePoolWithTag(v30, 0);
    *((_QWORD *)dhpdev + 363) = 0;
  }
  v31 = (void *)*((_QWORD *)dhpdev + 364);
  if ( v31 )
  {
    ExFreePoolWithTag(v31, 0);
    *((_QWORD *)dhpdev + 364) = 0;
  }
  v32 = (void *)*((_QWORD *)dhpdev + 900);
  if ( v32 )
  {
    ExFreePoolWithTag(v32, 0);
    *((_QWORD *)dhpdev + 900) = 0;
  }
  v33 = (void *)*((_QWORD *)dhpdev + 907);
  if ( v33 )
  {
    ExFreePoolWithTag(v33, 0);
    *((_QWORD *)dhpdev + 907) = 0;
  }
  v34 = (void *)*((_QWORD *)dhpdev + 895);
  if ( v34 )
  {
    ExFreePoolWithTag(v34, 0);
    *((_QWORD *)dhpdev + 895) = 0;
  }
  v35 = *((_QWORD *)dhpdev + 350);
  if ( v35 )
  {
    CddEngDeleteRgn(v35);
    *((_QWORD *)dhpdev + 350) = 0;
  }
  v36 = *((_QWORD *)dhpdev + 351);
  if ( v36 )
  {
    CddEngDeleteRgn(v36);
    *((_QWORD *)dhpdev + 351) = 0;
  }
  vDeleteSemaphores((struct CDDPDEV *)dhpdev);
  v37 = (void *)*((_QWORD *)dhpdev + 1600);
  if ( v37 )
  {
    EngFreeMem(v37);
    *((_QWORD *)dhpdev + 1600) = 0;
  }
  v38 = *((_QWORD *)dhpdev + 311);
  if ( v38 )
  {
    v39 = (void (__fastcall *)(__int64, _QWORD))*((_QWORD *)dhpdev + 43);
    if ( v39 )
      v39(v38, *((_QWORD *)dhpdev + 312));
  }
  v40 = *((_QWORD *)dhpdev + 313);
  if ( v40 )
  {
    v41 = (void (__fastcall *)(__int64, _QWORD))*((_QWORD *)dhpdev + 43);
    if ( v41 )
      v41(v40, *((_QWORD *)dhpdev + 314));
  }
  v42 = (struct _LOOKASIDE_LIST_EX *)*((_QWORD *)dhpdev + 97);
  if ( v42 )
  {
    ExDeleteLookasideListEx(v42);
    ExFreePoolWithTag(*((PVOID *)dhpdev + 97), 0);
  }
  EngFreeMem(dhpdev);
}

```

## disassembly

```asm
0x140028a40  push    rbx
0x140028a42  push    rbp
0x140028a43  push    rsi
0x140028a44  push    rdi
0x140028a45  push    r15
0x140028a47  sub     rsp, 60h
0x140028a4b  mov     rbx, rcx
0x140028a4e  xor     ebp, ebp
0x140028a50  mov     rcx, [rcx+2F8h]
0x140028a57  lea     rdi, [rbx+1A8h]
0x140028a5e  test    rcx, rcx
0x140028a61  jz      short loc_140028A72
0x140028a63  mov     rax, [rdi]
0x140028a66  call    _guard_dispatch_icall
0x140028a6b  mov     [rbx+2F8h], rbp
0x140028a72  mov     rcx, [rbx+300h]
0x140028a79  test    rcx, rcx
0x140028a7c  jz      short loc_140028A8D
0x140028a7e  mov     rax, [rdi]
0x140028a81  call    _guard_dispatch_icall
0x140028a86  mov     [rbx+300h], rbp
0x140028a8d  mov     rdx, rbx
0x140028a90  mov     ecx, 4
0x140028a95  call    cs:__imp_WdLogSingleEntry1
0x140028a9c  nop     dword ptr [rax+rax+00h]
0x140028aa1  mov     edi, 545h
0x140028aa6  mov     cs:WdLogGlobalForLineNumber, edi
0x140028aac  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140028ab3  nop     dword ptr [rax+rax+00h]
0x140028ab8  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140028abf  mov     r15d, 0CDDBA5Eh
0x140028ac5  mov     [rax+18h], rcx
0x140028ac9  mov     ecx, cs:dword_14003E570
0x140028acf  mov     [rax+20h], rcx
0x140028ad3  mov     rcx, rbx; this
0x140028ad6  mov     [rax+28h], r15
0x140028ada  mov     cs:WdLogGlobalForLineNumber, edi
0x140028ae0  call    ?DestroyBootGraphicsRelayAnimation@CDDPDEV@@QEAAXXZ; CDDPDEV::DestroyBootGraphicsRelayAnimation(void)
0x140028ae5  mov     rcx, [rbx+0A58h]; P
0x140028aec  test    rcx, rcx
0x140028aef  jz      short loc_140028B06
0x140028af1  xor     edx, edx; Tag
0x140028af3  call    cs:__imp_ExFreePoolWithTag
0x140028afa  nop     dword ptr [rax+rax+00h]
0x140028aff  mov     [rbx+0A58h], rbp
0x140028b06  cmp     [rbx+1568h], ebp
0x140028b0c  jz      loc_140028BC8
0x140028b12  call    cs:__imp_KeGetCurrentIrql
0x140028b19  nop     dword ptr [rax+rax+00h]
0x140028b1e  test    al, al
0x140028b20  jz      short loc_140028B69
0x140028b22  mov     ecx, 1
0x140028b27  call    cs:__imp_WdLogSingleEntry0
0x140028b2e  nop     dword ptr [rax+rax+00h]
0x140028b33  mov     edi, 311h
0x140028b38  mov     cs:WdLogGlobalForLineNumber, edi
0x140028b3e  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140028b45  nop     dword ptr [rax+rax+00h]
0x140028b4a  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140028b51  mov     [rax+18h], rcx
0x140028b55  mov     ecx, cs:dword_14003E570
0x140028b5b  mov     [rax+20h], rcx
0x140028b5f  mov     [rax+28h], r15
0x140028b63  mov     cs:WdLogGlobalForLineNumber, edi
0x140028b69  mov     rdx, [rbx+1570h]; struct CDDMUTEX *
0x140028b70  lea     rcx, [rsp+88h+var_38]; this
0x140028b75  call    ??0CGuardMutexEx@@QEAA@PEAVCDDMUTEX@@H@Z; CGuardMutexEx::CGuardMutexEx(CDDMUTEX *,int)
0x140028b7a  mov     edx, 0Dh
0x140028b7f  mov     dword ptr [rbx+0E40h], 1
0x140028b89  mov     rcx, rbx
0x140028b8c  call    ?CddIssueCommand@@YAJPEAUCDDPDEV@@W4_WORKERTHREAD_COMMAND@@@Z; CddIssueCommand(CDDPDEV *,_WORKERTHREAD_COMMAND)
0x140028b91  cmp     [rsp+88h+var_30], ebp
0x140028b95  jz      short loc_140028BA8
0x140028b97  mov     rcx, [rsp+88h+var_38]
0x140028b9c  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140028ba3  nop     dword ptr [rax+rax+00h]
0x140028ba8  mov     rcx, rbx; this
0x140028bab  call    ?DestroyInternalBitmaps@CDDPDEV@@QEAAXXZ; CDDPDEV::DestroyInternalBitmaps(void)
0x140028bb0  mov     rcx, rbx; struct CDDPDEV *
0x140028bb3  call    ?WorkerThreadCleanup@@YAXPEAUCDDPDEV@@@Z; WorkerThreadCleanup(CDDPDEV *)
0x140028bb8  lea     rdi, [rbx+1580h]
0x140028bbf  lea     rsi, [rbx+18B0h]
0x140028bc6  jmp     short loc_140028C06
0x140028bc8  lea     rdi, [rbx+1580h]
0x140028bcf  mov     rcx, rdi; this
0x140028bd2  call    ?DestroyStagingPool@CStagingPoolBase@@QEAAXXZ; CStagingPoolBase::DestroyStagingPool(void)
0x140028bd7  lea     rsi, [rbx+18B0h]
0x140028bde  mov     rcx, rsi; this
0x140028be1  call    ?DestroyStagingPool@CStagingPoolBase@@QEAAXXZ; CStagingPoolBase::DestroyStagingPool(void)
0x140028be6  lea     rcx, [rbx+20C8h]; this
0x140028bed  call    ?DestroyCommandBuffer@CHwCommandBuffer@@QEAAXXZ; CHwCommandBuffer::DestroyCommandBuffer(void)
0x140028bf2  lea     rcx, [rbx+2930h]; this
0x140028bf9  call    ?DestroyCommandBuffer@CHwCommandBuffer@@QEAAXXZ; CHwCommandBuffer::DestroyCommandBuffer(void)
0x140028bfe  btr     dword ptr [rbx+0AB8h], 8
0x140028c06  mov     rcx, rdi; this
0x140028c09  call    ?DestroyGdiSurfaces@CStagingPool@@QEAAXXZ; CStagingPool::DestroyGdiSurfaces(void)
0x140028c0e  mov     rcx, rsi; this
0x140028c11  call    ?DestroyGdiSurfaces@CStagingPool@@QEAAXXZ; CStagingPool::DestroyGdiSurfaces(void)
0x140028c16  mov     rcx, [rbx+18h]; hpal
0x140028c1a  test    rcx, rcx
0x140028c1d  jz      short loc_140028C2F
0x140028c1f  call    cs:__imp_EngDeletePalette
0x140028c26  nop     dword ptr [rax+rax+00h]
0x140028c2b  mov     [rbx+18h], rbp
0x140028c2f  mov     rcx, [rbx+9B0h]; pv
0x140028c36  test    rcx, rcx
0x140028c39  jz      short loc_140028C4E
0x140028c3b  call    cs:__imp_EngFreeMem
0x140028c42  nop     dword ptr [rax+rax+00h]
0x140028c47  mov     [rbx+9B0h], rbp
0x140028c4e  mov     ecx, [rbx+1C3Ch]
0x140028c54  test    ecx, ecx
0x140028c56  jnz     short loc_140028C68
0x140028c58  lea     rax, [rbx+1C48h]
0x140028c5f  cmp     [rax], rax
0x140028c62  jz      loc_140028D6A
0x140028c68  mov     r8, rcx
0x140028c6b  mov     esi, 2
0x140028c70  mov     ecx, esi
0x140028c72  mov     rdx, rbx
0x140028c75  call    cs:__imp_WdLogSingleEntry2
0x140028c7c  nop     dword ptr [rax+rax+00h]
0x140028c81  mov     edi, 572h
0x140028c86  mov     cs:WdLogGlobalForLineNumber, edi
0x140028c8c  call    cs:__imp_WdLogNewEntry5_WdError
0x140028c93  nop     dword ptr [rax+rax+00h]
0x140028c98  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140028c9f  mov     [rax+18h], rdx
0x140028ca3  mov     edx, cs:dword_14003E570
0x140028ca9  mov     [rax+20h], rdx
0x140028cad  mov     [rax+28h], r15
0x140028cb1  mov     rax, cs:KdDebuggerEnabled
0x140028cb8  mov     cs:WdLogGlobalForLineNumber, edi
0x140028cbe  cmp     [rax], bpl
0x140028cc1  jz      short loc_140028D1B
0x140028cc3  lea     rcx, aNotAllRedirect; "Not all redirection bitmaps are deleted"...
0x140028cca  call    cs:__imp_DbgPrint
0x140028cd1  nop     dword ptr [rax+rax+00h]
0x140028cd6  mov     ecx, esi
0x140028cd8  call    cs:__imp_WdLogSingleEntry0
0x140028cdf  nop     dword ptr [rax+rax+00h]
0x140028ce4  mov     edi, 576h
0x140028ce9  mov     cs:WdLogGlobalForLineNumber, edi
0x140028cef  call    cs:__imp_WdLogNewEntry5_WdError
0x140028cf6  nop     dword ptr [rax+rax+00h]
0x140028cfb  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140028d02  mov     [rax+18h], rcx
0x140028d06  mov     ecx, cs:dword_14003E570
0x140028d0c  mov     [rax+20h], rcx
0x140028d10  mov     [rax+28h], r15
0x140028d14  mov     cs:WdLogGlobalForLineNumber, edi
0x140028d1a  int     3; Trap to Debugger
0x140028d1b  cmp     cs:byte_14003E390, bpl
0x140028d22  jz      short loc_140028D6A
0x140028d24  mov     ecx, [rbx+1C3Ch]
0x140028d2a  mov     r9, rbx
0x140028d2d  mov     [rsp+88h+var_48], ebp
0x140028d31  mov     edx, 193h
0x140028d36  mov     [rsp+88h+var_50], rbp
0x140028d3b  mov     r8d, 80Ah
0x140028d41  mov     [rsp+88h+var_58], rbp
0x140028d46  mov     [rsp+88h+var_60], rbp
0x140028d4b  mov     [rsp+88h+var_68], rcx
0x140028d50  lea     rcx, aCddDll; "cdd.dll"
0x140028d57  call    cs:__imp_DbgkWerCaptureLiveKernelDump
0x140028d5e  nop     dword ptr [rax+rax+00h]
0x140028d63  mov     cs:byte_14003E390, bpl
0x140028d6a  cmp     [rbx+0AA8h], rbp
0x140028d71  jz      short loc_140028DBA
0x140028d73  mov     ecx, 1
0x140028d78  call    cs:__imp_WdLogSingleEntry0
0x140028d7f  nop     dword ptr [rax+rax+00h]
0x140028d84  mov     edi, 58Ch
0x140028d89  mov     cs:WdLogGlobalForLineNumber, edi
0x140028d8f  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140028d96  nop     dword ptr [rax+rax+00h]
0x140028d9b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140028da2  mov     [rax+18h], rcx
0x140028da6  mov     ecx, cs:dword_14003E570
0x140028dac  mov     [rax+20h], rcx
0x140028db0  mov     [rax+28h], r15
0x140028db4  mov     cs:WdLogGlobalForLineNumber, edi
0x140028dba  mov     rdi, rbp
0x140028dbd  mov     rcx, [rbx+rdi*8+0A30h]; P
0x140028dc5  test    rcx, rcx
0x140028dc8  jz      short loc_140028DE0
0x140028dca  xor     edx, edx; Tag
0x140028dcc  call    cs:__imp_ExFreePoolWithTag
0x140028dd3  nop     dword ptr [rax+rax+00h]
0x140028dd8  mov     [rbx+rdi*8+0A30h], rbp
0x140028de0  inc     rdi
0x140028de3  cmp     rdi, 5
0x140028de7  jnz     short loc_140028DBD
0x140028de9  mov     rax, [rbx+48h]
0x140028ded  test    rax, rax
0x140028df0  jz      short loc_140028DFB
0x140028df2  mov     rcx, [rbx+30h]
0x140028df6  call    _guard_dispatch_icall
0x140028dfb  mov     rcx, [rbx+2E0h]; Object
0x140028e02  test    rcx, rcx
0x140028e05  jz      short loc_140028E13
0x140028e07  call    cs:__imp_ObfDereferenceObject
0x140028e0e  nop     dword ptr [rax+rax+00h]
0x140028e13  mov     rcx, [rbx+0B40h]; P
0x140028e1a  test    rcx, rcx
0x140028e1d  jz      short loc_140028E34
0x140028e1f  xor     edx, edx; Tag
0x140028e21  call    cs:__imp_ExFreePoolWithTag
0x140028e28  nop     dword ptr [rax+rax+00h]
0x140028e2d  mov     [rbx+0B40h], rbp
0x140028e34  mov     rcx, [rbx+1570h]; P
0x140028e3b  test    rcx, rcx
0x140028e3e  jz      short loc_140028E55
0x140028e40  xor     edx, edx; Tag
0x140028e42  call    cs:__imp_ExFreePoolWithTag
0x140028e49  nop     dword ptr [rax+rax+00h]
0x140028e4e  mov     [rbx+1570h], rbp
0x140028e55  mov     rcx, [rbx+0B38h]
0x140028e5c  test    rcx, rcx
0x140028e5f  jz      short loc_140028E74
0x140028e61  call    cs:__imp_CddEngDeleteRgn
0x140028e68  nop     dword ptr [rax+rax+00h]
0x140028e6d  mov     [rbx+0B38h], rbp
0x140028e74  mov     rcx, [rbx+0B30h]
0x140028e7b  test    rcx, rcx
0x140028e7e  jz      short loc_140028E93
0x140028e80  call    cs:__imp_CddEngDeleteRgn
0x140028e87  nop     dword ptr [rax+rax+00h]
0x140028e8c  mov     [rbx+0B30h], rbp
0x140028e93  mov     rcx, [rbx+0B28h]
0x140028e9a  test    rcx, rcx
0x140028e9d  jz      short loc_140028EB2
0x140028e9f  call    cs:__imp_CddEngDeleteRgn
0x140028ea6  nop     dword ptr [rax+rax+00h]
0x140028eab  mov     [rbx+0B28h], rbp
0x140028eb2  mov     rcx, [rbx+0B20h]
0x140028eb9  test    rcx, rcx
0x140028ebc  jz      short loc_140028ED1
0x140028ebe  call    cs:__imp_CddEngDeleteRgn
0x140028ec5  nop     dword ptr [rax+rax+00h]
0x140028eca  mov     [rbx+0B20h], rbp
0x140028ed1  mov     rcx, [rbx+0B18h]
0x140028ed8  test    rcx, rcx
0x140028edb  jz      short loc_140028EF0
0x140028edd  call    cs:__imp_CddEngDeleteRgn
0x140028ee4  nop     dword ptr [rax+rax+00h]
0x140028ee9  mov     [rbx+0B18h], rbp
0x140028ef0  mov     rcx, [rbx+0B08h]
0x140028ef7  test    rcx, rcx
0x140028efa  jz      short loc_140028F0F
0x140028efc  call    cs:__imp_CddEngDeleteRgn
0x140028f03  nop     dword ptr [rax+rax+00h]
0x140028f08  mov     [rbx+0B08h], rbp
0x140028f0f  mov     rcx, [rbx+0B10h]
0x140028f16  test    rcx, rcx
0x140028f19  jz      short loc_140028F2E
0x140028f1b  call    cs:__imp_CddEngDeleteRgn
0x140028f22  nop     dword ptr [rax+rax+00h]
0x140028f27  mov     [rbx+0B10h], rbp
0x140028f2e  mov     rcx, [rbx+0B00h]
0x140028f35  test    rcx, rcx
0x140028f38  jz      short loc_140028F4D
0x140028f3a  call    cs:__imp_CddEngDeleteRgn
0x140028f41  nop     dword ptr [rax+rax+00h]
0x140028f46  mov     [rbx+0B00h], rbp
0x140028f4d  mov     rcx, [rbx+0B48h]; P
0x140028f54  test    rcx, rcx
0x140028f57  jz      short loc_140028F6E
0x140028f59  xor     edx, edx; Tag
0x140028f5b  call    cs:__imp_ExFreePoolWithTag
0x140028f62  nop     dword ptr [rax+rax+00h]
0x140028f67  mov     [rbx+0B48h], rbp
0x140028f6e  mov     rcx, [rbx+0B50h]; P
0x140028f75  test    rcx, rcx
0x140028f78  jz      short loc_140028F8F
0x140028f7a  xor     edx, edx; Tag
0x140028f7c  call    cs:__imp_ExFreePoolWithTag
0x140028f83  nop     dword ptr [rax+rax+00h]
0x140028f88  mov     [rbx+0B50h], rbp
0x140028f8f  mov     rcx, [rbx+0B58h]; P
0x140028f96  test    rcx, rcx
0x140028f99  jz      short loc_140028FB0
0x140028f9b  xor     edx, edx; Tag
0x140028f9d  call    cs:__imp_ExFreePoolWithTag
0x140028fa4  nop     dword ptr [rax+rax+00h]
0x140028fa9  mov     [rbx+0B58h], rbp
0x140028fb0  mov     rcx, [rbx+0B60h]; P
0x140028fb7  test    rcx, rcx
0x140028fba  jz      short loc_140028FD1
0x140028fbc  xor     edx, edx; Tag
0x140028fbe  call    cs:__imp_ExFreePoolWithTag
0x140028fc5  nop     dword ptr [rax+rax+00h]
0x140028fca  mov     [rbx+0B60h], rbp
0x140028fd1  mov     rcx, [rbx+1C20h]; P
0x140028fd8  test    rcx, rcx
0x140028fdb  jz      short loc_140028FF2
0x140028fdd  xor     edx, edx; Tag
0x140028fdf  call    cs:__imp_ExFreePoolWithTag
0x140028fe6  nop     dword ptr [rax+rax+00h]
0x140028feb  mov     [rbx+1C20h], rbp
  ... truncated ...
```
