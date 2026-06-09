# DxgkMiracastStartMiracastSession

- ea: `0x140083ffc`
- end: `0x140085007`
- name: `DxgkMiracastStartMiracastSession`
- size: `4107`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callers

- `0x14020e0f0`

## callees

- `0x14002e2e0`
- `0x140040908`
- `0x14004094c`
- `0x140061b18`
- `0x1400820f0`
- `0x140082134`
- `0x1400823dc`
- `0x140083ffc`
- `0x1400851c0`
- `0x140085298`
- `0x140085360`
- `0x14008e72c`
- `0x14008ed3c`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x140190fd0`
- `0x140195374`
- `0x1402b9380`
- `0x1402b977c`
- `0x1402b9f08`
- `0x1402ba264`
- `0x140365a4c`
- `0x140366b44`
- `0x140367720`
- `0x1403c736c`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140084ef2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140084ef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084bd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084f8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084bd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084f8d`
- `ntoskrnl!ExAllocatePool2` at `0x1400841b8`
- `ntoskrnl!ExAllocatePool2` at `0x140084a2d`
- `ntoskrnl!ExAllocatePool2` at `0x1400841b8`
- `ntoskrnl!ExAllocatePool2` at `0x140084a2d`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140084762`
- `ntoskrnl!PsGetCurrentProcessSessionId` at `0x140084762`
- `ntoskrnl!ExReleaseResourceLite` at `0x140084ee6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140084ee6`
- `ntoskrnl!ObfDereferenceObject` at `0x140084f4b`
- `ntoskrnl!ObfDereferenceObject` at `0x140084f4b`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140084d8f`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140084d8f`
- `ntoskrnl!KeClearEvent` at `0x140084aab`
- `ntoskrnl!KeClearEvent` at `0x140084abf`
- `ntoskrnl!KeClearEvent` at `0x140084aab`
- `ntoskrnl!KeClearEvent` at `0x140084abf`
- `ntoskrnl!KeSetEvent` at `0x140084e45`
- `ntoskrnl!KeSetEvent` at `0x140084f3c`
- `ntoskrnl!KeSetEvent` at `0x140084e45`
- `ntoskrnl!KeSetEvent` at `0x140084f3c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140084a00`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140084d83`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140084a00`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140084d83`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400849b7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140084d4c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400849b7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140084d4c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400842dd`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400842dd`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140084eba`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140084f0b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140084eba`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140084f0b`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400842ed`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x1400842ed`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140084e9d`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140084e9d`
- `watchdog!WdLogSingleEntry2` at `0x140084331`
- `watchdog!WdLogSingleEntry2` at `0x140084331`
- `watchdog!WdLogSingleEntry1` at `0x1400840b4`
- `watchdog!WdLogSingleEntry1` at `0x1400842a9`
- `watchdog!WdLogSingleEntry1` at `0x14008436d`
- `watchdog!WdLogSingleEntry1` at `0x1400846d6`
- `watchdog!WdLogSingleEntry1` at `0x140084747`
- `watchdog!WdLogSingleEntry1` at `0x1400848d0`
- `watchdog!WdLogSingleEntry1` at `0x140084991`
- `watchdog!WdLogSingleEntry1` at `0x140084a5a`
- `watchdog!WdLogSingleEntry1` at `0x140084b9f`
- `watchdog!WdLogSingleEntry1` at `0x140084c2d`
- `watchdog!WdLogSingleEntry1` at `0x140084c60`
- `watchdog!WdLogSingleEntry1` at `0x140084c93`
- `watchdog!WdLogSingleEntry1` at `0x1400840b4`
- `watchdog!WdLogSingleEntry1` at `0x1400842a9`
- `watchdog!WdLogSingleEntry1` at `0x14008436d`
- `watchdog!WdLogSingleEntry1` at `0x1400846d6`
- `watchdog!WdLogSingleEntry1` at `0x140084747`
- `watchdog!WdLogSingleEntry1` at `0x1400848d0`
- `watchdog!WdLogSingleEntry1` at `0x140084991`
- `watchdog!WdLogSingleEntry1` at `0x140084a5a`
- `watchdog!WdLogSingleEntry1` at `0x140084b9f`
- `watchdog!WdLogSingleEntry1` at `0x140084c2d`
- `watchdog!WdLogSingleEntry1` at `0x140084c60`
- `watchdog!WdLogSingleEntry1` at `0x140084c93`

## pseudocode

```c
__int64 __fastcall DxgkMiracastStartMiracastSession(__int64 a1, struct _KEVENT *a2, int *a3)
{
  __int64 v4; // rsi
  __int128 v5; // xmm0
  __int64 v6; // r13
  __int64 DeviceContextFromName; // rdi
  int v8; // ebx
  int v9; // r15d
  int v10; // r14d
  unsigned int v11; // edx
  int v12; // ecx
  int v13; // r8d
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  unsigned int v17; // r14d
  char *Pool2; // rax
  char *v19; // r13
  char *v20; // r14
  int DisplayAdapterFdo; // eax
  __int64 v22; // rax
  void *v23; // rdx
  int v24; // ecx
  int v25; // r8d
  int v26; // eax
  int v27; // ecx
  int v28; // ecx
  int v29; // edx
  int v30; // r9d
  int v31; // edx
  int v32; // eax
  int v33; // eax
  int v34; // ecx
  int v35; // ecx
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // edx
  char v40; // al
  unsigned int v41; // ecx
  char v42; // al
  _DWORD *v43; // r13
  int v44; // eax
  __int64 v45; // rax
  int v46; // ecx
  __int64 v47; // rax
  int v48; // ecx
  __int64 v49; // rax
  int v50; // ecx
  __int64 v51; // rax
  int v52; // ecx
  MIRACAST_CHUNK_LIST *v53; // rcx
  _QWORD *v54; // rax
  MIRACAST_CHUNK_LIST *v55; // rax
  unsigned int v56; // r14d
  __int64 *v57; // r13
  unsigned int v58; // ecx
  int v59; // eax
  struct _KEVENT *v60; // r15
  int v61; // ecx
  __int128 v62; // xmm0
  int v63; // edx
  MIRACAST_CHUNK_LIST *v64; // rcx
  MIRACAST_CHUNK_LIST *v65; // rcx
  MIRACAST_CHUNK_LIST *v66; // rcx
  MIRACAST_CHUNK_LIST *v67; // rcx
  MIRACAST_CHUNK_LIST *v68; // rcx
  MIRACAST_CHUNK_LIST *v69; // rcx
  int v70; // ecx
  int v71; // r8d
  PRKEVENT v72; // rdi
  ULONG RemlockSize[2]; // [rsp+20h] [rbp-E0h]
  char v75; // [rsp+60h] [rbp-A0h]
  char v76; // [rsp+61h] [rbp-9Fh]
  char DeviceObject; // [rsp+63h] [rbp-9Dh] BYREF
  char v78; // [rsp+64h] [rbp-9Ch]
  char v79; // [rsp+65h] [rbp-9Bh]
  unsigned int v80; // [rsp+68h] [rbp-98h]
  __int128 v81; // [rsp+70h] [rbp-90h] BYREF
  int v82; // [rsp+80h] [rbp-80h]
  __int64 v83; // [rsp+88h] [rbp-78h]
  PRKEVENT Event; // [rsp+90h] [rbp-70h]
  __int64 v85; // [rsp+98h] [rbp-68h]
  void *Src; // [rsp+A0h] [rbp-60h]
  int *v87; // [rsp+A8h] [rbp-58h]
  _BYTE v88[20]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v89; // [rsp+C8h] [rbp-38h] BYREF
  __int64 (__fastcall *v90)(void *, struct DXGK_MIRACAST_CHUNK_INFO *, void *, unsigned int); // [rsp+D8h] [rbp-28h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v92[2]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v93; // [rsp+108h] [rbp+8h]
  __int128 v94; // [rsp+110h] [rbp+10h]
  __int64 v95; // [rsp+120h] [rbp+20h]
  __int64 v96; // [rsp+128h] [rbp+28h]
  int v97; // [rsp+130h] [rbp+30h]
  int v98; // [rsp+134h] [rbp+34h]
  int v99; // [rsp+138h] [rbp+38h]
  int v100; // [rsp+13Ch] [rbp+3Ch]

  v85 = a1;
  v90 = 0;
  v87 = a3;
  memset(v88, 0, sizeof(v88));
  Event = a2;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v4 = 0;
  v83 = 0;
  v5 = *(_OWORD *)(a1 + 536);
  v6 = 0;
  DeviceObject = 0;
  v81 = v5;
  Src = (void *)(a1 + 536);
  v89 = 0;
  TraceLoggingWriteMiracastStartSessionEntry(&v81);
  DeviceContextFromName = DpiMiracastGetDeviceContextFromName((PCWSTR)(a1 + 4));
  if ( !DeviceContextFromName )
  {
    v8 = -2147483642;
    v9 = 2;
    v10 = -1073741275;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 5951;
    goto LABEL_144;
  }
  LOBYTE(v80) = 0;
  v76 = 0;
  v78 = 0;
  v75 = 0;
  v79 = 0;
  if ( (int)DxgkMiracastQueryMiracastSupportInternal(v88) >= 0 && !v88[8] )
  {
    v81 = 0;
    v10 = DpiMiracastSendSyncUserModeRequest(DeviceContextFromName, 2295824);
    if ( v10 < 0 )
    {
      AcquireMiniportListMutex();
      v8 = -2147483647;
      v9 = 17;
      goto LABEL_112;
    }
  }
  AcquireMiniportListMutex();
  *(_DWORD *)(DeviceContextFromName + 788) = *(_DWORD *)(a1 + 524);
  v14 = *(_QWORD *)(DeviceContextFromName + 336);
  if ( v14 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(v14 + 2 * v4) );
  }
  v15 = *(_QWORD *)(DeviceContextFromName + 344);
  if ( v15 )
  {
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(v15 + 2 * v16) );
  }
  else
  {
    LOWORD(v16) = 0;
  }
  v82 = (unsigned __int16)v4;
  v17 = 2 * ((unsigned __int16)v4 + (unsigned __int16)v16) + 68;
  Pool2 = (char *)ExAllocatePool2(256, v17, 1953656900);
  *(_QWORD *)&v81 = Pool2;
  v19 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 2 * ((unsigned __int16)v4 + (unsigned int)(unsigned __int16)v16) + 68);
    *((_DWORD *)v19 + 1) = v17;
    *((_DWORD *)v19 + 10) = 0;
    v20 = v19 + 64;
    *((_QWORD *)v19 + 4) = 0;
    *(_DWORD *)v19 = 19;
    *((_QWORD *)v19 + 1) = 0;
    *((_OWORD *)v19 + 1) = 0;
    *((_WORD *)v19 + 30) = v4;
    *((_WORD *)v19 + 31) = v16;
    if ( (_WORD)v4 )
      memmove(v20, *(const void **)(DeviceContextFromName + 336), 2LL * (unsigned __int16)v4);
    if ( (_WORD)v16 )
      memmove(&v20[2 * (v82 + 1)], *(const void **)(DeviceContextFromName + 344), 2LL * (unsigned __int16)v16);
  }
  DisplayAdapterFdo = DpiMiracastFindDisplayAdapterFdo(*(PVOID *)(DeviceContextFromName + 184));
  v4 = v83;
  if ( DisplayAdapterFdo < 0 || !v83 )
  {
    v8 = -2147483647;
    v10 = -1073741637;
    v9 = 4;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 6061;
    v76 = 0;
    v75 = 0;
    goto LABEL_111;
  }
  v80 = 1;
  if ( *(_QWORD *)(v83 + 3368) )
  {
    v8 = -2147483647;
    v10 = -1073741637;
    v9 = 6;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 6081;
LABEL_111:
    v6 = v81;
LABEL_112:
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20000000000LL) != 0 )
      McTemplateK0qqqz_EtwWriteTransfer(
        v12,
        (unsigned int)EventMiracastStartMiracastSessionFail,
        v13,
        v9,
        v10,
        *(_DWORD *)(DeviceContextFromName + 200),
        *(_QWORD *)(DeviceContextFromName + 352));
    if ( v75 && v8 < 0 )
    {
      *(_DWORD *)(DeviceContextFromName + 416) = v8;
      *(_DWORD *)(DeviceContextFromName + 784) = v9;
      if ( v78 )
      {
        DpiMiracastDdiMiracastDestroyContext(v4, *(_QWORD *)(DeviceContextFromName + 448));
        *(_DWORD *)(DeviceContextFromName + 456) = -1;
        *(_QWORD *)(DeviceContextFromName + 448) = 0;
      }
      if ( v79 )
      {
        *(_QWORD *)(DeviceContextFromName + 472) = 0;
        KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
        *(_QWORD *)(DeviceContextFromName + 432) = 0;
        *(_QWORD *)(v4 + 3368) = 0;
        *(_QWORD *)(v4 + 3376) = 0;
        *(_QWORD *)(DeviceContextFromName + 376) = 0;
        *(_QWORD *)(DeviceContextFromName + 384) = 0;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        KeFlushQueuedDpcs();
      }
      v64 = *(MIRACAST_CHUNK_LIST **)(DeviceContextFromName + 488);
      if ( v64 )
      {
        MIRACAST_CHUNK_LIST::`scalar deleting destructor'(v64, v11);
        *(_QWORD *)(DeviceContextFromName + 488) = 0;
      }
      v65 = *(MIRACAST_CHUNK_LIST **)(v4 + 3392);
      if ( v65 )
      {
        MIRACAST_CHUNK_LIST::`scalar deleting destructor'(v65, v11);
        *(_QWORD *)(v4 + 3392) = 0;
      }
      v66 = *(MIRACAST_CHUNK_LIST **)(v4 + 3400);
      if ( v66 )
      {
        MIRACAST_CHUNK_LIST::`scalar deleting destructor'(v66, v11);
        *(_QWORD *)(v4 + 3400) = 0;
      }
      v67 = *(MIRACAST_CHUNK_LIST **)(v4 + 3408);
      if ( v67 )
      {
        MIRACAST_CHUNK_LIST::`scalar deleting destructor'(v67, v11);
        *(_QWORD *)(v4 + 3408) = 0;
      }
      v68 = *(MIRACAST_CHUNK_LIST **)(DeviceContextFromName + 504);
      if ( v68 )
      {
        MIRACAST_CHUNK_LIST::`scalar deleting destructor'(v68, v11);
        *(_QWORD *)(DeviceContextFromName + 504) = 0;
      }
      v69 = *(MIRACAST_CHUNK_LIST **)(DeviceContextFromName + 512);
      if ( v69 )
      {
        MIRACAST_CHUNK_LIST::`scalar deleting destructor'(v69, v11);
        *(_QWORD *)(DeviceContextFromName + 512) = 0;
      }
      KeSetEvent(*(PRKEVENT *)(DeviceContextFromName + 464), 0, 0);
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20000000000LL) != 0 )
        McTemplateK0qqz_EtwWriteTransfer(
          v70,
          (unsigned int)EventMiracastPerfTrackStartMiracastSessionFailed,
          v71,
          *(_DWORD *)(DeviceContextFromName + 440),
          *(_DWORD *)(DeviceContextFromName + 200),
          *(_QWORD *)(DeviceContextFromName + 352));
      TraceLoggingWriteMiracastSessionStart(DeviceContextFromName);
    }
    if ( !v76 )
      goto LABEL_138;
    goto LABEL_136;
  }
  IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v83 + 64), (PVOID)DeviceContextFromName, File, 1u, 0x20u);
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(DeviceContextFromName + 32);
  *(_QWORD *)(DeviceContextFromName + 88) = KeGetCurrentThread();
  v76 = 1;
  if ( *(_DWORD *)(DeviceContextFromName + 408) )
  {
    v8 = -2147483647;
    v10 = -1073741661;
    v9 = 6;
    WdLogSingleEntry2(2, DeviceContextFromName);
    WdLogGlobalForLineNumber = 6119;
    goto LABEL_111;
  }
  if ( !*(_QWORD *)(DeviceContextFromName + 400) )
  {
    v8 = -2147483642;
    v10 = -1073741275;
    v9 = 2;
    WdLogSingleEntry1(4);
    WdLogGlobalForLineNumber = 6141;
    goto LABEL_111;
  }
  *(_QWORD *)(DeviceContextFromName + 632) = MEMORY[0xFFFFF78000000014];
  *(_DWORD *)(DeviceContextFromName + 660) = *(_DWORD *)(DeviceContextFromName + 656);
  *(_DWORD *)(DeviceContextFromName + 656) = 0;
  *(_BYTE *)(DeviceContextFromName + 590) = 0;
  *(_DWORD *)(DeviceContextFromName + 652) = 0;
  *(_DWORD *)(DeviceContextFromName + 664) = 0;
  *(_DWORD *)(DeviceContextFromName + 672) = dword_140163338;
  v22 = v85;
  *(_QWORD *)(DeviceContextFromName + 676) = 0;
  *(_DWORD *)(DeviceContextFromName + 648) = 0;
  *(_BYTE *)(DeviceContextFromName + 591) = 0;
  *(_QWORD *)(DeviceContextFromName + 684) = 0;
  *(_QWORD *)(DeviceContextFromName + 692) = 0;
  *(_QWORD *)(DeviceContextFromName + 780) = 0;
  *(_DWORD *)(DeviceContextFromName + 788) = *(_DWORD *)(v22 + 524);
  *(_DWORD *)(DeviceContextFromName + 700) = -1;
  *(_DWORD *)(DeviceContextFromName + 704) = 0;
  memset((void *)(DeviceContextFromName + 708), 0, 0x42u);
  v23 = Src;
  *(_DWORD *)(DeviceContextFromName + 776) = 256;
  memmove((void *)(DeviceContextFromName + 112), v23, 0x10u);
  if ( ++*(_DWORD *)(DeviceContextFromName + 440) >= 0xFFFFFFFE )
    *(_DWORD *)(DeviceContextFromName + 440) = 0;
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000000000LL) != 0 )
    McTemplateK0pxzqq_EtwWriteTransfer(
      v24,
      (unsigned int)EventMiracastStartMiracastSession,
      v25,
      *(_QWORD *)(v4 + 48),
      *(_QWORD *)(DeviceContextFromName + 96),
      *(_QWORD *)(DeviceContextFromName + 152),
      *(_DWORD *)(DeviceContextFromName + 656),
      *(_DWORD *)(DeviceContextFromName + 664));
  v9 = 9;
  *(_DWORD *)(DeviceContextFromName + 192) = *(_DWORD *)(v4 + 1124);
  *(_DWORD *)(DeviceContextFromName + 196) = *(_DWORD *)(v4 + 1128);
  v26 = *(_DWORD *)(v4 + 1120);
  if ( v26 == 1 )
  {
    v27 = (*(_DWORD *)(v4 + 1124) << 16) | (unsigned __int16)*(_DWORD *)(v4 + 1128);
  }
  else if ( v26 == 2 )
  {
    v28 = *(char *)(v4 + 1128);
    if ( ((unsigned __int8)(*(_BYTE *)(v4 + 1128) - 48) <= 9u || (unsigned __int8)((v28 | 0x20) - 97) <= 5u)
      && ((v29 = *(char *)(v4 + 1129), (unsigned __int8)(*(_BYTE *)(v4 + 1129) - 48) <= 9u)
       || (unsigned __int8)((v29 | 0x20) - 97) <= 5u)
      && ((v25 = *(char *)(v4 + 1130), (unsigned __int8)(*(_BYTE *)(v4 + 1130) - 48) <= 9u)
       || (unsigned __int8)((v25 | 0x20) - 97) <= 5u)
      && ((v30 = *(char *)(v4 + 1131), (unsigned __int8)(*(_BYTE *)(v4 + 1131) - 48) <= 9u)
       || (unsigned __int8)((v30 | 0x20) - 97) <= 5u) )
    {
      if ( (unsigned __int8)(v28 - 48) > 9u )
        v32 = ((_BYTE)v28 - 7) & 0xF;
      else
        v32 = v28 - 48;
      v33 = v32 << 12;
      if ( (unsigned __int8)(v29 - 48) > 9u )
        v34 = ((_BYTE)v29 - 7) & 0xF;
      else
        v34 = v29 - 48;
      v35 = v33 | (v34 << 8);
      v36 = *(char *)(v4 + 1130);
      LOBYTE(v25) = v25 - 48;
      if ( (unsigned __int8)v25 > 9u )
        v37 = ((_BYTE)v36 - 7) & 0xF;
      else
        v37 = v36 - 48;
      v38 = v35 | (16 * v37);
      if ( (unsigned __int8)(v30 - 48) > 9u )
        v39 = ((_BYTE)v30 - 7) & 0xF;
      else
        v39 = v30 - 48;
      v31 = v38 | v39;
    }
    else
    {
      v31 = *(unsigned __int16 *)(v4 + 1130);
    }
    v40 = *(_BYTE *)(v4 + 1124);
    if ( v40 == 32 || v40 == 95 )
    {
      v42 = *(_BYTE *)(v4 + 1125);
      if ( v42 == 32 || v42 == 95 )
        v41 = *(_DWORD *)(v4 + 1124) & 0xFFFF0000;
      else
        v41 = (*(_DWORD *)(v4 + 1124) & 0xFFFFFF00) << 8;
    }
    else
    {
      v41 = *(_DWORD *)(v4 + 1124) << 16;
    }
    v27 = v31 | v41;
  }
  else
  {
    v27 = 0;
  }
  *(_DWORD *)(DeviceContextFromName + 200) = v27;
  if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20000000000LL) != 0 )
    McTemplateK0qqz_EtwWriteTransfer(
      v27,
      (unsigned int)EventMiracastPerfTrackStartMiracastSession,
      v25,
      *(_DWORD *)(DeviceContextFromName + 440),
      v27,
      *(_QWORD *)(DeviceContextFromName + 352));
  *(_BYTE *)(DeviceContextFromName + 589) = 0;
  *((_QWORD *)&v89 + 1) = DpiMiracastCbSendUserModeMessage;
  v43 = (_DWORD *)(DeviceContextFromName + 456);
  *(_QWORD *)&v89 = DeviceContextFromName;
  v90 = DpiMiracastCbReportChunkInfo;
  v10 = DpiMiracastDdiMiracastCreateContext(v4, &v89, DeviceContextFromName + 448, DeviceContextFromName + 456);
  if ( v10 < 0 )
  {
    v9 = (v10 != -1073740024) + 7;
    v8 = -(v10 != -1073740024) - 2147483646;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 6353;
    *(_QWORD *)(DeviceContextFromName + 448) = 0;
    *v43 = -1;
    v76 = v80;
    v75 = v80;
    goto LABEL_111;
  }
  v75 = 1;
  DpiMiracastEtwLogStartMiracastSessionStage(DeviceContextFromName, 0);
  v44 = *(_DWORD *)(v4 + 3360);
  v78 = 1;
  if ( *v43 != v44 )
  {
    v8 = -2147483647;
    v10 = -1073741811;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 6373;
    goto LABEL_111;
  }
  *(_DWORD *)(DeviceContextFromName + 420) = PsGetCurrentProcessSessionId();
  *(_BYTE *)(DeviceContextFromName + 588) = 0;
  *(_QWORD *)(DeviceContextFromName + 496) = 0;
  *(_WORD *)(v4 + 3384) = 0;
  *(_DWORD *)(v4 + 3388) = 0;
  v45 = operator new(24, 1265072196, 64);
  if ( v45 )
  {
    v46 = *(_DWORD *)(v4 + 3352);
    *(_DWORD *)(v45 + 16) = 0;
    *(_DWORD *)(v45 + 20) = v46;
    *(_QWORD *)(v45 + 8) = v45;
    *(_QWORD *)v45 = v45;
  }
  else
  {
    v45 = 0;
  }
  *(_QWORD *)(DeviceContextFromName + 488) = v45;
  v47 = operator new(24, 1265072196, 64);
  if ( v47 )
  {
    v48 = *(_DWORD *)(v4 + 3352);
    *(_DWORD *)(v47 + 16) = 0;
    *(_DWORD *)(v47 + 20) = v48;
    *(_QWORD *)(v47 + 8) = v47;
    *(_QWORD *)v47 = v47;
  }
  else
  {
    v47 = 0;
  }
  *(_QWORD *)(v4 + 3392) = v47;
  v49 = operator new(24, 1265072196, 64);
  if ( v49 )
  {
    v50 = *(_DWORD *)(v4 + 3352);
    *(_DWORD *)(v49 + 16) = 0;
    *(_DWORD *)(v49 + 20) = v50;
    *(_QWORD *)(v49 + 8) = v49;
    *(_QWORD *)v49 = v49;
  }
  else
  {
    v49 = 0;
  }
  *(_QWORD *)(v4 + 3400) = v49;
  v51 = operator new(24, 1265072196, 64);
  if ( v51 )
  {
    v52 = *(_DWORD *)(v4 + 3352);
    *(_DWORD *)(v51 + 16) = 0;
    *(_DWORD *)(v51 + 20) = v52;
    *(_QWORD *)(v51 + 8) = v51;
    *(_QWORD *)v51 = v51;
  }
  else
  {
    v51 = 0;
  }
  *(_QWORD *)(v4 + 3408) = v51;
  if ( !*(_QWORD *)(DeviceContextFromName + 488)
    || (v53 = *(MIRACAST_CHUNK_LIST **)(v4 + 3392)) == 0
    || !*(_QWORD *)(v4 + 3400)
    || !v51 )
  {
    v8 = -2147483647;
    v10 = -1073741801;
    v9 = 10;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 6413;
    goto LABEL_111;
  }
  if ( !MIRACAST_CHUNK_LIST::AllocateNewChunks(v53, 0x14u) )
  {
    v8 = -2147483647;
    v10 = -1073741801;
    v9 = 11;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 6426;
    goto LABEL_111;
  }
  *(_DWORD *)(v4 + 3388) = 20;
  v54 = (_QWORD *)operator new(24, 1265072196, 64);
  if ( v54 )
  {
    v54[2] = 0;
    v54[1] = v54;
    *v54 = v54;
  }
  else
  {
    v54 = 0;
  }
  *(_QWORD *)(DeviceContextFromName + 504) = v54;
  v55 = (MIRACAST_CHUNK_LIST *)operator new(24, 1265072196, 64);
  if ( v55 )
  {
    *((_QWORD *)v55 + 2) = 0;
    *((_QWORD *)v55 + 1) = v55;
    *(_QWORD *)v55 = v55;
  }
  else
  {
    v55 = 0;
  }
  *(_QWORD *)(DeviceContextFromName + 512) = v55;
  if ( !*(_QWORD *)(DeviceContextFromName + 504) || !v55 )
  {
    v8 = -2147483647;
    v10 = -1073741801;
    v9 = 10;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 6450;
    goto LABEL_111;
  }
  if ( !MIRACAST_CHUNK_LIST::AllocateNewChunks(v55, 0x14u) )
  {
    v8 = -2147483647;
    v10 = -1073741801;
    v9 = 11;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 6463;
    goto LABEL_111;
  }
  KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
  *(_QWORD *)(DeviceContextFromName + 432) = *(_QWORD *)(v4 + 24);
  *(_QWORD *)(v4 + 3368) = DeviceContextFromName;
  *(_QWORD *)(v4 + 3376) = *(_QWORD *)(DeviceContextFromName + 96);
  *(_QWORD *)(DeviceContextFromName + 376) = *(_QWORD *)(v4 + 4960);
  *(_QWORD *)(DeviceContextFromName + 384) = *(_QWORD *)(v4 + 4968);
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v56 = *(unsigned __int16 *)(v4 + 4992) + 72;
  v79 = 1;
  v57 = (__int64 *)ExAllocatePool2(256, v56, 1953656900);
  if ( !v57 )
  {
    v8 = -2147483647;
    v9 = 12;
    v10 = -1073741801;
    WdLogSingleEntry1(6);
    WdLogGlobalForLineNumber = 6514;
    goto LABEL_111;
  }
  v58 = v80;
  _InterlockedAdd((volatile signed __int32 *)(DeviceContextFromName + 24), v80);
  _InterlockedXor((volatile signed __int32 *)(DeviceContextFromName + 28), DeviceContextFromName);
  v59 = *(_DWORD *)(DeviceContextFromName + 408);
  v60 = Event;
  *(_DWORD *)(DeviceContextFromName + 408) = v80;
  *(_QWORD *)(DeviceContextFromName + 472) = v60;
  *(_DWORD *)(DeviceContextFromName + 412) = v59;
  dword_140163320 += v58;
  KeClearEvent(*(PRKEVENT *)(DeviceContextFromName + 464));
  if ( v60 )
    KeClearEvent(v60);
  memset(v57, 0, v56);
  v61 = *(_DWORD *)(DeviceContextFromName + 440);
  v62 = *(_OWORD *)(DeviceContextFromName + 112);
  *(__int64 *)((char *)v57 + 12) = *(_QWORD *)(DeviceContextFromName + 96);
  *((_DWORD *)v57 + 2) = v61;
  *v57 = DeviceContextFromName;
  *(__int64 *)((char *)v57 + 20) = *(_QWORD *)(v4 + 2696);
  *(__int64 *)((char *)v57 + 28) = *(_QWORD *)&v88[12];
  *((_DWORD *)v57 + 10) = dword_140163324;
  *((_DWORD *)v57 + 9) = v61;
  *((_BYTE *)v57 + 44) = 0;
  *((_OWORD *)v57 + 3) = v62;
  memmove(v57 + 8, *(const void **)(v4 + 5000), *(unsigned __int16 *)(v4 + 4992));
  v9 = 0;
  RemlockSize[0] = v56 - 12;
  v10 = DpiMiracastSendAsyncUserModeRequest(
          DeviceContextFromName,
          v63,
          2295812,
          (int)v57 + 12,
          *(size_t *)RemlockSize,
          0,
          0,
          (__int64)DpiMiracastStartSessionRequestCallback,
          (__int64)v57,
          (PDEVICE_OBJECT)&DeviceObject,
          DeviceContextFromName + 424);
  if ( v10 < 0 )
  {
    v8 = -2147483647;
    v9 = 13;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 6595;
    *(_DWORD *)(DeviceContextFromName + 408) = *(_DWORD *)(DeviceContextFromName + 412);
    --dword_140163320;
    if ( !DeviceObject )
    {
      ExFreePoolWithTag(v57, 0);
      DpiMiracastReleaseMiracastDeviceContext((PVOID)DeviceContextFromName);
    }
    goto LABEL_111;
  }
  *(_DWORD *)(DeviceContextFromName + 416) = 2;
  v8 = 2;
  DpiMiracastBroadcastDeviceStateChange(DeviceContextFromName);
  v6 = v81;
LABEL_136:
  *(_QWORD *)(DeviceContextFromName + 88) = 0;
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(DeviceContextFromName + 32);
  if ( v8 < 0 )
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 64), (PVOID)DeviceContextFromName, 0x20u);
LABEL_138:
  if ( (_BYTE)v80 )
  {
    if ( *(_BYTE *)(v4 + 484) )
      DpiEnableD3Requests(*(_QWORD *)(v4 + 24));
    ExReleaseResourceLite(*(PERESOURCE *)(v4 + 168));
    KeLeaveCriticalRegion();
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v4 + 64), (PVOID)v4, 0x20u);
  }
  if ( v8 >= 0 )
  {
    ReleaseMiniportListMutex();
    goto LABEL_147;
  }
  DpiMiracastReleaseMiracastDeviceContext((PVOID)DeviceContextFromName);
  ReleaseMiniportListMutex();
LABEL_144:
  v72 = Event;
  if ( Event )
  {
    KeSetEvent(Event, 0, 0);
    ObfDereferenceObject(v72);
  }
LABEL_147:
  *v87 = v10;
  if ( v6 )
  {
    *(_DWORD *)(v6 + 48) = v10;
    *(_DWORD *)(v6 + 52) = v8;
    *(_DWORD *)(v6 + 56) = v9;
    DxgkWriteDiagEntry((struct _DXGK_DIAG_HEADER *)v6, 0x200000000uLL);
    ExFreePoolWithTag((PVOID)v6, 0);
  }
  else
  {
    v96 = 0;
    v92[0] = 6;
    v93 = 0;
    v94 = 0;
    v92[1] = 64;
    v95 = 0;
    v97 = 69;
    v98 = v10;
    v99 = v8;
    v100 = v9;
    DxgkWriteDiagEntry((struct _DXGK_DIAG_HEADER *)v92, 0x200000000uLL);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140083ffc  mov     [rsp-8+arg_18], rbx
0x140084001  push    rbp
0x140084002  push    rsi
0x140084003  push    rdi
0x140084004  push    r12
0x140084006  push    r13
0x140084008  push    r14
0x14008400a  push    r15
0x14008400c  lea     rbp, [rsp-50h]
0x140084011  sub     rsp, 150h
0x140084018  mov     rax, cs:__security_cookie
0x14008401f  xor     rax, rsp
0x140084022  mov     [rbp+80h+var_40], rax
0x140084026  xor     eax, eax
0x140084028  mov     [rbp+80h+var_E8], rcx
0x14008402c  xor     r15d, r15d
0x14008402f  mov     [rbp+80h+var_C0], eax
0x140084032  xorps   xmm0, xmm0
0x140084035  mov     [rbp+80h+var_A8], rax
0x140084039  mov     qword ptr [rbp+80h+LockHandle.OldIrql], rax
0x14008403d  mov     rbx, rcx
0x140084040  lea     rax, [rcx+218h]
0x140084047  mov     [rbp+80h+var_D8], r8
0x14008404b  movups  [rbp+80h+var_D0], xmm0
0x14008404f  lea     rcx, [rsp+180h+var_110]
0x140084054  mov     [rbp+80h+Event], rdx
0x140084058  movups  xmmword ptr [rbp+80h+LockHandle.LockQueue.Next], xmm0
0x14008405c  mov     esi, r15d
0x14008405f  mov     [rbp+80h+var_F8], r15
0x140084063  movups  xmm0, xmmword ptr [rax]
0x140084066  mov     [rsp+180h+var_11E], r15b
0x14008406b  mov     r13d, r15d
0x14008406e  xorps   xmm1, xmm1
0x140084071  mov     [rsp+180h+var_11D], r15b
0x140084076  movdqu  [rsp+180h+var_110], xmm0
0x14008407c  mov     [rbp+80h+Src], rax
0x140084080  movups  [rbp+80h+var_B8], xmm1
0x140084084  call    TraceLoggingWriteMiracastStartSessionEntry
0x140084089  lea     rcx, [rbx+4]; SourceString
0x14008408d  call    DpiMiracastGetDeviceContextFromName
0x140084092  mov     rdi, rax
0x140084095  test    rax, rax
0x140084098  jnz     short loc_1400840D2
0x14008409a  lea     r12d, [r15+2]
0x14008409e  mov     rbx, 0FFFFFFFF80000006h
0x1400840a5  mov     r15d, r12d
0x1400840a8  mov     r14d, 0C0000225h
0x1400840ae  mov     rdx, rbx
0x1400840b1  mov     ecx, r12d
0x1400840b4  call    cs:__imp_WdLogSingleEntry1
0x1400840bb  nop     dword ptr [rax+rax+00h]
0x1400840c0  xor     r12d, r12d
0x1400840c3  mov     cs:WdLogGlobalForLineNumber, 173Fh
0x1400840cd  jmp     loc_140084F2B
0x1400840d2  lea     rcx, [rbp+80h+var_D0]
0x1400840d6  mov     byte ptr [rsp+180h+var_118], r15b
0x1400840db  mov     [rsp+180h+var_11F], r15b
0x1400840e0  mov     [rsp+180h+var_11C], r15b
0x1400840e5  mov     [rsp+180h+var_120], r15b
0x1400840ea  mov     [rsp+180h+var_11B], r15b
0x1400840ef  call    DxgkMiracastQueryMiracastSupportInternal
0x1400840f4  mov     r12d, 2
0x1400840fa  test    eax, eax
0x1400840fc  js      short loc_140084148
0x1400840fe  cmp     byte ptr [rbp+80h+var_D0+8], r15b
0x140084102  jnz     short loc_140084148
0x140084104  lea     rax, [rsp+180h+var_110]
0x140084109  xorps   xmm0, xmm0
0x14008410c  mov     qword ptr [rsp+180h+var_150], rax
0x140084111  mov     edx, 230810h
0x140084116  mov     dword ptr [rsp+180h+var_158], r15d
0x14008411b  mov     rcx, rdi
0x14008411e  mov     qword ptr [rsp+180h+RemlockSize], r15
0x140084123  movups  [rsp+180h+var_110], xmm0
0x140084128  call    DpiMiracastSendSyncUserModeRequest
0x14008412d  mov     r14d, eax
0x140084130  test    eax, eax
0x140084132  jns     short loc_140084148
0x140084134  call    ?AcquireMiniportListMutex@@YAXXZ
0x140084139  mov     ebx, 80000001h
0x14008413e  lea     r15d, [r12+0Fh]
0x140084143  jmp     loc_140084CB8
0x140084148  call    ?AcquireMiniportListMutex@@YAXXZ
0x14008414d  mov     eax, [rbx+20Ch]
0x140084153  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140084157  mov     [rdi+314h], eax
0x14008415d  mov     rax, [rdi+150h]
0x140084164  test    rax, rax
0x140084167  jz      short loc_140084176
0x140084169  mov     rsi, rcx
0x14008416c  inc     rsi
0x14008416f  cmp     [rax+rsi*2], r15w
0x140084174  jnz     short loc_14008416C
0x140084176  mov     rax, [rdi+158h]
0x14008417d  test    rax, rax
0x140084180  jz      short loc_140084191
0x140084182  mov     rbx, rcx
0x140084185  inc     rbx
0x140084188  cmp     [rax+rbx*2], r15w
0x14008418d  jnz     short loc_140084185
0x14008418f  jmp     short loc_140084194
0x140084191  mov     ebx, r15d
0x140084194  movzx   ecx, si
0x140084197  mov     r8d, 74727044h
0x14008419d  movzx   eax, bx
0x1400841a0  add     eax, ecx
0x1400841a2  mov     [rbp+80h+var_100], ecx
0x1400841a5  mov     ecx, 100h
0x1400841aa  lea     r14d, ds:44h[rax*2]
0x1400841b2  mov     edx, r14d
0x1400841b5  mov     r15d, r14d
0x1400841b8  call    cs:__imp_ExAllocatePool2
0x1400841bf  nop     dword ptr [rax+rax+00h]
0x1400841c4  mov     qword ptr [rsp+180h+var_110], rax
0x1400841c9  mov     r13, rax
0x1400841cc  test    rax, rax
0x1400841cf  jz      short loc_14008424F
0x1400841d1  mov     r8d, r15d; Size
0x1400841d4  xor     edx, edx; Val
0x1400841d6  mov     rcx, rax; void *
0x1400841d9  call    memset
0x1400841de  mov     [r13+4], r14d
0x1400841e2  xor     eax, eax
0x1400841e4  mov     [r13+28h], eax
0x1400841e8  lea     r14, [r13+40h]
0x1400841ec  mov     [r13+20h], rax
0x1400841f0  xorps   xmm0, xmm0
0x1400841f3  mov     dword ptr [r13+0], 13h
0x1400841fb  mov     [r13+8], rax
0x1400841ff  movups  xmmword ptr [r13+10h], xmm0
0x140084204  mov     [r13+3Ch], si
0x140084209  mov     [r13+3Eh], bx
0x14008420e  xor     r13d, r13d
0x140084211  test    si, si
0x140084214  jz      short loc_14008422C
0x140084216  mov     rdx, [rdi+150h]; Src
0x14008421d  mov     rcx, r14; void *
0x140084220  movzx   r8d, si
0x140084224  add     r8, r8; Size
0x140084227  call    memmove
0x14008422c  test    bx, bx
0x14008422f  jz      short loc_140084252
0x140084231  mov     eax, [rbp+80h+var_100]
0x140084234  mov     rdx, [rdi+158h]; Src
0x14008423b  movzx   r8d, bx
0x14008423f  add     r8, r8; Size
0x140084242  inc     eax
0x140084244  lea     rcx, [r14+rax*2]; void *
0x140084248  call    memmove
0x14008424d  jmp     short loc_140084252
0x14008424f  xor     r13d, r13d
0x140084252  mov     rcx, [rdi+0B8h]; Object
0x140084259  lea     r8, [rsp+180h+var_11E]
0x14008425e  lea     rdx, [rbp+80h+var_F8]
0x140084262  call    DpiMiracastFindDisplayAdapterFdo
0x140084267  mov     rsi, [rbp+80h+var_F8]
0x14008426b  test    eax, eax
0x14008426d  js      loc_140084C78
0x140084273  test    rsi, rsi
0x140084276  jz      loc_140084C78
0x14008427c  mov     ebx, 1
0x140084281  mov     [rsp+180h+var_118], ebx
0x140084285  cmp     [rsi+0D28h], r13
0x14008428c  jz      short loc_1400842C4
0x14008428e  mov     ebx, 80000001h
0x140084293  mov     rdx, 0FFFFFFFF80000001h
0x14008429a  mov     r14d, 0C00000BBh
0x1400842a0  mov     r15d, 6
0x1400842a6  mov     ecx, r12d
0x1400842a9  call    cs:__imp_WdLogSingleEntry1
0x1400842b0  nop     dword ptr [rax+rax+00h]
0x1400842b5  mov     cs:WdLogGlobalForLineNumber, 17C1h
0x1400842bf  jmp     loc_140084CB3
0x1400842c4  lea     rcx, [rsi+40h]; RemoveLock
0x1400842c8  mov     [rsp+180h+RemlockSize], 20h ; ' '; RemlockSize
0x1400842d0  mov     r9d, ebx; Line
0x1400842d3  lea     r8, File; File
0x1400842da  mov     rdx, rdi; Tag
0x1400842dd  call    cs:__imp_IoAcquireRemoveLockEx
0x1400842e4  nop     dword ptr [rax+rax+00h]
0x1400842e9  lea     rcx, [rdi+20h]
0x1400842ed  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x1400842f4  nop     dword ptr [rax+rax+00h]
0x1400842f9  mov     rax, gs:188h
0x140084302  mov     [rdi+58h], rax
0x140084306  mov     [rsp+180h+var_11F], bl
0x14008430a  cmp     [rdi+198h], r13d
0x140084311  jz      short loc_14008434C
0x140084313  mov     ebx, 80000001h
0x140084318  mov     r14d, 0C00000A3h
0x14008431e  mov     r15d, 6
0x140084324  mov     r8, 0FFFFFFFF80000001h
0x14008432b  mov     rdx, rdi
0x14008432e  mov     ecx, r12d
0x140084331  call    cs:__imp_WdLogSingleEntry2
0x140084338  nop     dword ptr [rax+rax+00h]
0x14008433d  mov     cs:WdLogGlobalForLineNumber, 17E7h
0x140084347  jmp     loc_140084CB3
0x14008434c  cmp     [rdi+190h], r13
0x140084353  jnz     short loc_140084388
0x140084355  mov     rbx, 0FFFFFFFF80000006h
0x14008435c  mov     r14d, 0C0000225h
0x140084362  mov     r15d, r12d
0x140084365  mov     rdx, rdi
0x140084368  mov     ecx, 4
0x14008436d  call    cs:__imp_WdLogSingleEntry1
0x140084374  nop     dword ptr [rax+rax+00h]
0x140084379  mov     cs:WdLogGlobalForLineNumber, 17FDh
0x140084383  jmp     loc_140084CB3
0x140084388  mov     rax, ds:0FFFFF78000000014h
0x140084392  lea     rcx, [rdi+2C4h]; void *
0x140084399  mov     [rdi+278h], rax
0x1400843a0  xor     edx, edx; Val
0x1400843a2  mov     eax, [rdi+290h]
0x1400843a8  mov     [rdi+294h], eax
0x1400843ae  mov     [rdi+290h], r13d
0x1400843b5  mov     [rdi+24Eh], r13b
0x1400843bc  lea     r8d, [rdx+42h]; Size
0x1400843c0  mov     [rdi+28Ch], r13d
0x1400843c7  mov     [rdi+298h], r13d
0x1400843ce  mov     eax, cs:dword_140163338
0x1400843d4  mov     [rdi+2A0h], eax
0x1400843da  mov     rax, [rbp+80h+var_E8]
0x1400843de  mov     qword ptr [rdi+2A4h], 0
0x1400843e9  mov     [rdi+288h], r13d
0x1400843f0  mov     [rdi+24Fh], r13b
0x1400843f7  mov     qword ptr [rdi+2ACh], 0
0x140084402  mov     qword ptr [rdi+2B4h], 0
0x14008440d  mov     qword ptr [rdi+30Ch], 0
0x140084418  mov     eax, [rax+20Ch]
0x14008441e  mov     [rdi+314h], eax
0x140084424  mov     dword ptr [rdi+2BCh], 0FFFFFFFFh
0x14008442e  mov     [rdi+2C0h], r13d
0x140084435  call    memset
0x14008443a  mov     rdx, [rbp+80h+Src]; Src
0x14008443e  lea     rcx, [rdi+70h]; void *
0x140084442  mov     r8d, 10h; Size
0x140084448  mov     dword ptr [rdi+308h], 100h
0x140084452  call    memmove
0x140084457  add     [rdi+1B8h], ebx
0x14008445d  cmp     dword ptr [rdi+1B8h], 0FFFFFFFEh
0x140084464  jb      short loc_14008446D
0x140084466  mov     [rdi+1B8h], r13d
0x14008446d  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+5, bl
0x140084473  jz      short loc_1400844AE
0x140084475  mov     eax, [rdi+298h]
0x14008447b  lea     rdx, EventMiracastStartMiracastSession
0x140084482  mov     r9, [rsi+30h]
0x140084486  mov     dword ptr [rsp+180h+var_148], eax
0x14008448a  mov     eax, [rdi+290h]
0x140084490  mov     [rsp+180h+var_150], eax
0x140084494  mov     rax, [rdi+98h]
0x14008449b  mov     [rsp+180h+var_158], rax
0x1400844a0  mov     rax, [rdi+60h]
0x1400844a4  mov     qword ptr [rsp+180h+RemlockSize], rax
0x1400844a9  call    McTemplateK0pxzqq_EtwWriteTransfer
0x1400844ae  mov     eax, [rsi+464h]
0x1400844b4  mov     r15d, 9
0x1400844ba  mov     [rdi+0C0h], eax
0x1400844c0  mov     eax, [rsi+468h]
0x1400844c6  mov     [rdi+0C4h], eax
0x1400844cc  mov     eax, [rsi+460h]
0x1400844d2  cmp     eax, ebx
0x1400844d4  jnz     short loc_1400844EF
0x1400844d6  mov     eax, [rsi+468h]
0x1400844dc  movzx   ecx, ax
0x1400844df  mov     eax, [rsi+464h]
0x1400844e5  shl     eax, 10h
0x1400844e8  or      ecx, eax
0x1400844ea  jmp     loc_140084634
0x1400844ef  cmp     eax, r12d
0x1400844f2  jnz     loc_140084631
0x1400844f8  movsx   ecx, byte ptr [rsi+468h]
0x1400844ff  mov     r10b, 30h ; '0'
0x140084502  mov     al, cl
0x140084504  mov     r11b, 61h ; 'a'
0x140084507  sub     al, r10b
0x14008450a  mov     r14b, 5
0x14008450d  cmp     al, r15b
0x140084510  jbe     short loc_14008451E
0x140084512  mov     al, cl
0x140084514  or      al, 20h
0x140084516  sub     al, r11b
0x140084519  cmp     al, r14b
0x14008451c  ja      short loc_14008457B
0x14008451e  movsx   edx, byte ptr [rsi+469h]
0x140084525  mov     al, dl
0x140084527  sub     al, r10b
0x14008452a  cmp     al, r15b
0x14008452d  jbe     short loc_14008453B
0x14008452f  mov     al, dl
0x140084531  or      al, 20h
0x140084533  sub     al, r11b
0x140084536  cmp     al, r14b
0x140084539  ja      short loc_14008457B
0x14008453b  movsx   r8d, byte ptr [rsi+46Ah]
0x140084543  mov     al, r8b
0x140084546  sub     al, r10b
0x140084549  cmp     al, r15b
0x14008454c  jbe     short loc_14008455B
  ... truncated ...
```
