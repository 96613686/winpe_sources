# RxRegisterMinirdr

- ea: `0x140047ea0`
- end: `0x1400485f2`
- name: `RxRegisterMinirdr`
- size: `1874`
- prototype: `NTSTATUS __stdcall(PRDBSS_DEVICE_OBJECT *DeviceObject, PDRIVER_OBJECT DriverObject, PMINIRDR_DISPATCH MrdrDispatch, ULONG Controls, PUNICODE_STRING DeviceName, ULONG DeviceExtensionSize, ULONG DeviceType, ULONG DeviceCharacteristics)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140014d10`
- `0x140014e40`
- `0x140017280`
- `0x140017490`
- `0x1400175f0`
- `0x14001ba74`
- `0x14001bbd0`
- `0x140025c20`
- `0x140047ea0`
- `0x140048600`
- `0x140051dac`
- `0x140078f20`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400482a6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400482a6`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140048082`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140048391`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140048082`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140048391`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400480a8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140048440`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400480a8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140048440`
- `ntoskrnl!IoSizeofWorkItem` at `0x1400480da`
- `ntoskrnl!IoSizeofWorkItem` at `0x140048323`
- `ntoskrnl!IoSizeofWorkItem` at `0x1400480da`
- `ntoskrnl!IoSizeofWorkItem` at `0x140048323`
- `ntoskrnl!IoCreateDevice` at `0x14004818d`
- `ntoskrnl!IoCreateDevice` at `0x14004818d`
- `ntoskrnl!ObfReferenceObject` at `0x1400481ba`
- `ntoskrnl!ObfReferenceObject` at `0x1400481ba`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400482ce`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400482ce`
- `ntoskrnl!InitializeSListHead` at `0x1400482e5`
- `ntoskrnl!InitializeSListHead` at `0x1400482e5`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140048317`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x140048317`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x140048406`
- `ntoskrnl!RtlFindLeastSignificantBit` at `0x140048406`
- `ntoskrnl!FsRtlRegisterUncProviderEx2` at `0x14004856d`
- `ntoskrnl!FsRtlRegisterUncProviderEx2` at `0x14004856d`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140047eff`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x140047eff`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140047eec`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x140047eec`

## pseudocode

```c
NTSTATUS __stdcall RxRegisterMinirdr(
        PRDBSS_DEVICE_OBJECT *DeviceObject,
        PDRIVER_OBJECT DriverObject,
        PMINIRDR_DISPATCH MrdrDispatch,
        ULONG Controls,
        PUNICODE_STRING DeviceName,
        ULONG DeviceExtensionSize,
        ULONG DeviceType,
        ULONG DeviceCharacteristics)
{
  ULONG RecommendedSharedDataAlignment; // ebx
  ULONG MaximumProcessorCount; // eax
  int v12; // edi
  PDEVICE_OBJECT v13; // rcx
  int v14; // edx
  struct _DEVICE_OBJECT *v15; // r10
  NTSTATUS v16; // ebx
  NTSTATUS result; // eax
  char v18; // r9
  unsigned __int64 v19; // rcx
  unsigned int v20; // r13d
  ULONG v21; // ebx
  unsigned int v22; // eax
  unsigned int v23; // ecx
  ULONG v24; // eax
  ULONG v25; // edx
  UNICODE_STRING *v26; // r8
  _QWORD *v27; // rcx
  PDEVICE_OBJECT v28; // rax
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rdx
  ULONG *p_SortKey; // rax
  PDEVICE_OBJECT v33; // r9
  unsigned __int64 v34; // rbx
  unsigned int v35; // edi
  struct _SLIST_ENTRY *i; // rbx
  ULONG v37; // eax
  PVPB **v38; // rcx
  PVPB *p_Vpb; // rax
  ULONG v40; // edi
  CCHAR LeastSignificantBit; // al
  __int64 j; // rdx
  PDRIVER_OBJECT v43; // r8
  struct _RX_PREFIX_TABLE *p_Blink; // rcx
  int v45; // ecx
  int v46; // r8d
  int v47; // eax
  int v48; // eax
  PDEVICE_OBJECT v49; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v50; // [rsp+58h] [rbp-31h]
  PDRIVER_OBJECT DriverObjecta; // [rsp+60h] [rbp-29h]
  PRDBSS_DEVICE_OBJECT *v52; // [rsp+68h] [rbp-21h]
  _BYTE v53[12]; // [rsp+70h] [rbp-19h] BYREF

  *(_QWORD *)v53 = MrdrDispatch;
  DriverObjecta = DriverObject;
  v52 = DeviceObject;
  v49 = 0;
  RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment();
  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  if ( MaximumProcessorCount <= 1 )
    v12 = 8;
  else
    v12 = RecommendedSharedDataAlignment * (MaximumProcessorCount + 1);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids, DeviceName);
  }
  v16 = 0;
  if ( !(unsigned __int8)RxIsRdbssLoadedAsDriver(v13, 2) )
    return -1073741573;
  if ( !*(_QWORD *)&RxContextLookasideList.L.FreeMisses )
    return -1073741823;
  if ( (Controls & 0x10) != 0 && (Controls & 0x1000) != 0 )
  {
    if ( WPP_GLOBAL_Control != v15
      && ((unsigned __int8)HIDWORD(WPP_GLOBAL_Control->Timer) & (unsigned __int8)v14) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= (unsigned __int8)v14 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids);
    }
    return -1073741811;
  }
  if ( MrdrDispatch->NodeByteSize < 0x2D8u )
  {
    LOBYTE(v14) = 0;
    v18 = 1;
    goto LABEL_23;
  }
  if ( MrdrDispatch->MRxFlags != 8 )
  {
    v18 = 0;
    LOBYTE(v14) = 1;
LABEL_23:
    if ( WPP_GLOBAL_Control != v15 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_ZcDDcDD(
        WPP_GLOBAL_Control->AttachedDevice,
        v14,
        (_DWORD)WPP_GLOBAL_Control,
        (_DWORD)DeviceName,
        v18 != 0 ? 89 : 78);
    return -1073741735;
  }
  if ( !v52 || (Controls & 0x10) != 0 && Fcb )
  {
    if ( WPP_GLOBAL_Control != v15
      && ((unsigned __int8)HIDWORD(WPP_GLOBAL_Control->Timer) & (unsigned __int8)v14) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= (unsigned __int8)v14 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids);
    }
    return -1073741436;
  }
  else
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
    if ( (Controls & 0x10) != 0 && RxContextLookasideList.L.Future[9] )
      v16 = -1073741584;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
    if ( v16 )
      return v16;
    result = RxRegisterForFsFilterCallbacks(DriverObjecta);
    if ( result < 0 )
      return result;
    if ( DeviceExtensionSize > 0xFFFFFFF7 )
      return -1073741675;
    v19 = ((IoSizeofWorkItem() + 15) & 0xFFFFFFF0) * (unsigned __int64)(unsigned int)FspPerDeviceThreshold;
    if ( v19 > 0xFFFFFFFF )
      return -1073741675;
    v20 = v19 + 16;
    if ( (int)v19 + 16 < (unsigned int)v19 )
      return -1073741675;
    v21 = (DeviceExtensionSize + 7) & 0xFFFFFFF8;
    v22 = ((DeviceName->MaximumLength + 7) & 0xFFFFFFF8) + 976;
    v23 = v22 + v21;
    if ( v22 + v21 < v22 )
      return -1073741675;
    v24 = v23 + v20;
    if ( v23 + v20 < v23 )
      return -1073741675;
    v25 = v12 + 32 + v24;
    v50 = v12 + 32;
    if ( v25 < v24 )
      return -1073741675;
    v26 = 0;
    if ( (Controls & 1) != 0 )
      v26 = DeviceName;
    result = IoCreateDevice(DriverObjecta, v25, v26, DeviceType, DeviceCharacteristics, 0, &v49);
    if ( !result )
    {
      v49[1].DriverObject = (struct _DRIVER_OBJECT *)RxFileSystemDeviceObject;
      ObfReferenceObject(RxFileSystemDeviceObject);
      v27 = v52;
      *(_QWORD *)&v49[3].ActiveThreadCount = 0;
      *(_QWORD *)(*(_QWORD *)&RxContextLookasideList.L.FreeMisses + 104LL) = 0;
      v28 = v49;
      *v27 = v49;
      v28[1].NextDevice = *(struct _DEVICE_OBJECT **)v53;
      *(_DWORD *)&v49[1].Type = Controls;
      *(UNICODE_STRING *)&v49[1].AttachedDevice = *DeviceName;
      LOBYTE(v49[1].Flags) = !(Controls & 1);
      BYTE1(v49[1].Flags) = (Controls & 2) == 0;
      if ( v49[3].DeviceLock.Header.WaitListHead.Blink )
        __int2c();
      v29 = v21;
      v30 = v50;
      v31 = v50;
      v49[3].DeviceLock.Header.WaitListHead.Blink = (struct _LIST_ENTRY *)((char *)&v49[3].SectorSize + v29 + v20);
      RfsInitializeRundownProtectionCacheAwareEx(v49[3].DeviceLock.Header.WaitListHead.Blink, v31);
      WORD1(v49[1].AttachedDevice) = DeviceName->MaximumLength;
      LOWORD(v49[1].AttachedDevice) = 0;
      v49[1].CurrentIrp = (struct _IRP *)((char *)v49[3].DeviceLock.Header.WaitListHead.Blink + v30);
      RtlCopyUnicodeString((PUNICODE_STRING)&v49[1].AttachedDevice, DeviceName);
      p_SortKey = &v49[1].Queue.Wcb.WaitQueueEntry.SortKey;
      v49[1].Queue.Wcb.DeviceRoutine = (PDRIVER_CONTROL)&v49[1].Queue.Wcb.NumberOfChannels;
      *(_QWORD *)p_SortKey = p_SortKey;
      KeInitializeSpinLock((PKSPIN_LOCK)&v49[1].Queue);
      InitializeSListHead((PSLIST_HEADER)&v49[1].Queue.Wcb.DeviceContext);
      v33 = v49;
      v34 = (unsigned __int64)&v49[3].DeviceObjectExtension + v29 + 7;
      v35 = 0;
      for ( i = (struct _SLIST_ENTRY *)(v34 & 0xFFFFFFFFFFFFFFF0uLL);
            v35 < FspPerDeviceThreshold;
            i = (struct _SLIST_ENTRY *)(((unsigned __int64)&i->Next + v37 + 15) & 0xFFFFFFFFFFFFFFF0uLL) )
      {
        ExpInterlockedPushEntrySList((PSLIST_HEADER)&v33[1].Queue.Wcb.DeviceContext, i);
        v37 = IoSizeofWorkItem();
        v33 = v49;
        ++v35;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          (unsigned int)WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids,
          (_DWORD)v33,
          (__int64)DeviceName);
      }
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
      v38 = *(PVPB ***)&RxContextLookasideList.L.Future[6];
      if ( **(NPAGED_LOOKASIDE_LIST ***)&RxContextLookasideList.L.Future[6] != (NPAGED_LOOKASIDE_LIST *)&RxContextLookasideList.L.Future[4] )
        __fastfail(3u);
      p_Vpb = &v49[1].Vpb;
      v49[1].Vpb = (PVPB)&RxContextLookasideList.L.Future[4];
      p_Vpb[1] = (PVPB)v38;
      *v38 = p_Vpb;
      ++RxContextLookasideList.L.Future[8];
      *(_QWORD *)&RxContextLookasideList.L.Future[6] = p_Vpb;
      v40 = Controls & 0x20;
      if ( (Controls & 0x20) != 0 )
        ++RxContextLookasideList.L.Future[9];
      HIDWORD(v49[3].DeviceLock.Header.WaitListHead.Flink) = -1;
      if ( (Controls & 0x2000) != 0 )
      {
        LeastSignificantBit = RtlFindLeastSignificantBit(Set);
        if ( LeastSignificantBit != -1 )
        {
          Set &= ~(1LL << LeastSignificantBit);
          HIDWORD(v49[3].DeviceLock.Header.WaitListHead.Flink) = LeastSignificantBit;
        }
      }
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
      if ( (Controls & 4) == 0 )
      {
        v43 = DriverObjecta;
        for ( j = 0; j != 27; ++j )
          v43->MajorFunction[j] = *(PDRIVER_DISPATCH *)(*(_QWORD *)&RxContextLookasideList.L.FreeMisses + 8 * j + 112);
        v43->FastIoDispatch = *(PFAST_IO_DISPATCH *)(*(_QWORD *)&RxContextLookasideList.L.FreeMisses + 80LL);
      }
      if ( (Controls & 8) == 0 )
      {
        p_Blink = (struct _RX_PREFIX_TABLE *)&v49[1].DeviceQueue.DeviceListHead.Blink;
        v49[1].DeviceQueue.DeviceListHead.Flink = (struct _LIST_ENTRY *)&v49[1].DeviceQueue.DeviceListHead.Blink;
        RxInitializePrefixTable(p_Blink, j, (BOOLEAN)v43);
        *(_QWORD *)&v49[2].DeviceQueue.Type = (char *)v49 + 840;
        RxInitializeRdbssScavenger(*(_QWORD *)&v49[2].DeviceQueue.Type);
      }
      if ( (Controls & 0x10) != 0 )
        RxInitializePrefixTable((PRX_PREFIX_TABLE)&v49[2], j, (BOOLEAN)v43);
      v16 = 0;
      v49[1].Queue.Wcb.CurrentIrp = 0;
      if ( (Controls & 1) == 0 )
      {
        *(_QWORD *)&v53[4] = 0;
        v45 = 0;
        *(_DWORD *)v53 = 33619980;
        if ( (Controls & 0x20) != 0 )
          v45 = 2;
        *(_DWORD *)&v53[4] = v45;
        v46 = v40 != 0 ? 2 : 0;
        v47 = v46 | 1;
        if ( BYTE1(v49[1].Flags) )
        {
          v45 = v46 | 1;
          *(_DWORD *)&v53[4] = v46 | 1;
        }
        else
        {
          v47 = v40 != 0 ? 2 : 0;
        }
        if ( (Controls & 0x200) != 0 )
        {
          v45 = v47 | 4;
          *(_DWORD *)&v53[4] = v47 | 4;
        }
        v48 = *(_DWORD *)&v53[8];
        if ( (Controls & 0x1000) != 0 )
          v48 = 7;
        *(_DWORD *)&v53[8] = v48;
        if ( (Controls & 0x2000) != 0 )
          *(_DWORD *)&v53[4] = v45 | 8;
        v16 = FsRtlRegisterUncProviderEx2(&v49[1].AttachedDevice, v49, v53, &v49[1].Timer);
        if ( v16 < 0 )
          RxUnregisterMinirdr((PRDBSS_DEVICE_OBJECT)v49);
      }
      return v16;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140047ea0  mov     [rsp-8+arg_10], rbx
0x140047ea5  push    rbp
0x140047ea6  push    rsi
0x140047ea7  push    rdi
0x140047ea8  push    r12
0x140047eaa  push    r13
0x140047eac  push    r14
0x140047eae  push    r15
0x140047eb0  lea     rbp, [rsp-7]
0x140047eb5  sub     rsp, 90h
0x140047ebc  mov     rax, cs:__security_cookie
0x140047ec3  xor     rax, rsp
0x140047ec6  mov     [rbp+37h+var_40], rax
0x140047eca  mov     r14, [rbp+37h+DeviceName]
0x140047ece  mov     esi, r9d
0x140047ed1  mov     r12d, [rbp+37h+DeviceExtensionSize]
0x140047ed5  mov     r13, r8
0x140047ed8  mov     [rbp+37h+var_50], r8
0x140047edc  mov     [rbp+37h+DriverObject], rdx
0x140047ee0  mov     [rbp+37h+var_58], rcx
0x140047ee4  mov     [rbp+37h+var_70], 0
0x140047eec  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x140047ef3  nop     dword ptr [rax+rax+00h]
0x140047ef8  mov     ecx, 0FFFFh; GroupNumber
0x140047efd  mov     ebx, eax
0x140047eff  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x140047f06  nop     dword ptr [rax+rax+00h]
0x140047f0b  cmp     eax, 1
0x140047f0e  jbe     short loc_140047F18
0x140047f10  lea     edi, [rax+1]
0x140047f13  imul    edi, ebx
0x140047f16  jmp     short loc_140047F1D
0x140047f18  mov     edi, 8
0x140047f1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140047f24  lea     r10, WPP_GLOBAL_Control
0x140047f2b  mov     edx, 2
0x140047f30  cmp     rcx, r10
0x140047f33  jz      short loc_140047F66
0x140047f35  mov     eax, [rcx+2Ch]
0x140047f38  test    dl, al
0x140047f3a  jz      short loc_140047F66
0x140047f3c  cmp     byte ptr [rcx+29h], 4
0x140047f40  jb      short loc_140047F66
0x140047f42  mov     rcx, [rcx+18h]
0x140047f46  lea     r8, WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids
0x140047f4d  mov     edx, 0Ah
0x140047f52  mov     r9, r14
0x140047f55  call    WPP_SF_Z
0x140047f5a  mov     edx, 2
0x140047f5f  lea     r10, WPP_GLOBAL_Control
0x140047f66  call    RxIsRdbssLoadedAsDriver
0x140047f6b  xor     ebx, ebx
0x140047f6d  test    al, al
0x140047f6f  jnz     short loc_140047F7B
0x140047f71  mov     eax, 0C00000FBh
0x140047f76  jmp     loc_1400485CA
0x140047f7b  cmp     qword ptr cs:RxContextLookasideList.L.20h, rbx
0x140047f82  jnz     short loc_140047F8E
0x140047f84  mov     eax, 0C0000001h
0x140047f89  jmp     loc_1400485CA
0x140047f8e  mov     r15d, esi
0x140047f91  and     r15d, 10h
0x140047f95  jz      short loc_140047FD4
0x140047f97  bt      esi, 0Ch
0x140047f9b  jnb     short loc_140047FD4
0x140047f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140047fa4  cmp     rcx, r10
0x140047fa7  jz      short loc_140047FCA
0x140047fa9  mov     eax, [rcx+2Ch]
0x140047fac  test    dl, al
0x140047fae  jz      short loc_140047FCA
0x140047fb0  cmp     [rcx+29h], dl
0x140047fb3  jb      short loc_140047FCA
0x140047fb5  mov     rcx, [rcx+18h]
0x140047fb9  lea     r8, WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids
0x140047fc0  mov     edx, 0Bh
0x140047fc5  call    WPP_SF_
0x140047fca  mov     eax, 0C000000Dh
0x140047fcf  jmp     loc_1400485CA
0x140047fd4  movsx   r11d, word ptr [r13+2]
0x140047fd9  mov     eax, 2D8h
0x140047fde  cmp     r11w, ax
0x140047fe2  jnb     short loc_140047FEB
0x140047fe4  mov     dl, bl
0x140047fe6  mov     r9b, 1
0x140047fe9  jmp     short loc_140047FF7
0x140047feb  cmp     dword ptr [r13+4], 8
0x140047ff0  jz      short loc_14004805F
0x140047ff2  mov     r9b, bl
0x140047ff5  mov     dl, 1
0x140047ff7  mov     r8, cs:WPP_GLOBAL_Control
0x140047ffe  cmp     r8, r10
0x140048001  jz      short loc_140048055
0x140048003  mov     eax, [r8+2Ch]
0x140048007  test    al, 1
0x140048009  jz      short loc_140048055
0x14004800b  cmp     byte ptr [r8+29h], 1
0x140048010  jb      short loc_140048055
0x140048012  test    r9b, r9b
0x140048015  jnz     short loc_140048029
0x140048017  mov     ecx, [r13+4]
0x14004801b  test    dl, dl
0x14004801d  jz      short loc_140048024
0x14004801f  mov     r10b, 59h ; 'Y'
0x140048022  jmp     short loc_14004802E
0x140048024  mov     r10b, 4Eh ; 'N'
0x140048027  jmp     short loc_14004802E
0x140048029  mov     r10b, 3Fh ; '?'
0x14004802c  mov     ecx, ebx
0x14004802e  mov     [rsp+0C0h+var_78], ecx
0x140048032  neg     r9b
0x140048035  mov     rcx, [r8+18h]
0x140048039  mov     r9, r14
0x14004803c  sbb     al, al
0x14004803e  mov     [rsp+0C0h+var_88], r10b
0x140048043  and     al, 0Bh
0x140048045  mov     dword ptr [rsp+0C0h+DeviceObject], r11d
0x14004804a  add     al, 4Eh ; 'N'
0x14004804c  mov     byte ptr [rsp+0C0h+var_A0], al
0x140048050  call    WPP_SF_ZcDDcDD
0x140048055  mov     eax, 0C0000059h
0x14004805a  jmp     loc_1400485CA
0x14004805f  cmp     [rbp+37h+var_58], rbx
0x140048063  jz      loc_140048598
0x140048069  test    r15d, r15d
0x14004806c  jz      short loc_14004807B
0x14004806e  cmp     cs:Fcb, rbx
0x140048075  jnz     loc_140048598
0x14004807b  lea     rcx, RxContextLookasideList.L.30h; FastMutex
0x140048082  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140048089  nop     dword ptr [rax+rax+00h]
0x14004808e  test    r15d, r15d
0x140048091  jz      short loc_1400480A1
0x140048093  cmp     dword ptr cs:RxContextLookasideList.L+7Ch, ebx
0x140048099  mov     eax, 0C00000F0h
0x14004809e  cmovnz  ebx, eax
0x1400480a1  lea     rcx, RxContextLookasideList.L.30h; FastMutex
0x1400480a8  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400480af  nop     dword ptr [rax+rax+00h]
0x1400480b4  test    ebx, ebx
0x1400480b6  jz      short loc_1400480BF
0x1400480b8  mov     eax, ebx
0x1400480ba  jmp     loc_1400485CA
0x1400480bf  mov     rcx, [rbp+37h+DriverObject]; FilterDriverObject
0x1400480c3  call    RxRegisterForFsFilterCallbacks
0x1400480c8  test    eax, eax
0x1400480ca  js      loc_1400485CA
0x1400480d0  cmp     r12d, 0FFFFFFF7h
0x1400480d4  ja      loc_140048591
0x1400480da  call    cs:__imp_IoSizeofWorkItem
0x1400480e1  nop     dword ptr [rax+rax+00h]
0x1400480e6  add     eax, 0Fh
0x1400480e9  mov     ecx, 0FFFFFFF0h
0x1400480ee  and     rax, rcx
0x1400480f1  mov     ecx, cs:FspPerDeviceThreshold
0x1400480f7  imul    rcx, rax
0x1400480fb  mov     eax, 0FFFFFFFFh
0x140048100  cmp     rcx, rax
0x140048103  ja      loc_140048591
0x140048109  lea     r13d, [rcx+10h]
0x14004810d  cmp     r13d, ecx
0x140048110  jb      loc_140048591
0x140048116  movzx   eax, word ptr [r14+2]
0x14004811b  lea     ebx, [r12+7]
0x140048120  add     eax, 7
0x140048123  mov     ecx, 0FFFFFFF8h
0x140048128  and     eax, ecx
0x14004812a  and     ebx, ecx
0x14004812c  add     eax, 3D0h
0x140048131  lea     ecx, [rax+rbx]
0x140048134  cmp     ecx, eax
0x140048136  jb      loc_140048591
0x14004813c  lea     eax, [rcx+r13]
0x140048140  cmp     eax, ecx
0x140048142  jb      loc_140048591
0x140048148  lea     ecx, [rdi+20h]
0x14004814b  lea     edx, [rcx+rax]; DeviceExtensionSize
0x14004814e  mov     [rbp+37h+var_68], ecx
0x140048151  cmp     edx, eax
0x140048153  jb      loc_140048591
0x140048159  mov     r9d, [rbp+37h+DeviceType]; DeviceType
0x14004815d  lea     rax, [rbp+37h+var_70]
0x140048161  mov     rcx, [rbp+37h+DriverObject]; DriverObject
0x140048165  mov     edi, 0
0x14004816a  mov     [rsp+0C0h+DeviceObject], rax; DeviceObject
0x14004816f  mov     r12b, sil
0x140048172  mov     eax, [rbp+37h+DeviceCharacteristics]
0x140048175  and     r12b, 1
0x140048179  xor     r12b, 1
0x14004817d  mov     [rsp+0C0h+Exclusive], dil; Exclusive
0x140048182  mov     r8d, edi
0x140048185  mov     [rsp+0C0h+var_A0], eax; DeviceCharacteristics
0x140048189  cmovz   r8, r14; DeviceName
0x14004818d  call    cs:__imp_IoCreateDevice
0x140048194  nop     dword ptr [rax+rax+00h]
0x140048199  test    eax, eax
0x14004819b  jnz     loc_1400485CA
0x1400481a1  mov     rcx, [rbp+37h+var_70]
0x1400481a5  mov     rax, cs:RxFileSystemDeviceObject
0x1400481ac  mov     [rcx+158h], rax
0x1400481b3  mov     rcx, cs:RxFileSystemDeviceObject; Object
0x1400481ba  call    cs:__imp_ObfReferenceObject
0x1400481c1  nop     dword ptr [rax+rax+00h]
0x1400481c6  mov     rax, [rbp+37h+var_70]
0x1400481ca  mov     rcx, [rbp+37h+var_58]
0x1400481ce  mov     [rax+4F8h], rdi
0x1400481d5  mov     rax, qword ptr cs:RxContextLookasideList.L.20h
0x1400481dc  mov     [rax+68h], rdi
0x1400481e0  mov     rax, [rbp+37h+var_70]
0x1400481e4  mov     [rcx], rax
0x1400481e7  mov     rcx, [rbp+37h+var_50]
0x1400481eb  mov     [rax+160h], rcx
0x1400481f2  mov     ecx, esi
0x1400481f4  mov     rax, [rbp+37h+var_70]
0x1400481f8  shr     ecx, 1
0x1400481fa  not     cl
0x1400481fc  and     cl, 1
0x1400481ff  mov     [rax+150h], esi
0x140048205  mov     rax, [rbp+37h+var_70]
0x140048209  movups  xmm0, xmmword ptr [r14]
0x14004820d  movdqu  xmmword ptr [rax+168h], xmm0
0x140048215  mov     rax, [rbp+37h+var_70]
0x140048219  mov     [rax+180h], r12b
0x140048220  mov     rax, [rbp+37h+var_70]
0x140048224  mov     [rax+181h], cl
0x14004822a  mov     rcx, [rbp+37h+var_70]
0x14004822e  cmp     [rcx+518h], rdi
0x140048235  jz      short loc_140048239
0x140048237  int     2Ch; Windows NT - assertion failure
0x140048239  mov     edi, ebx
0x14004823b  mov     ebx, [rbp+37h+var_68]
0x14004823e  mov     eax, r13d
0x140048241  mov     edx, ebx
0x140048243  add     rax, 520h
0x140048249  add     rax, rdi
0x14004824c  add     rax, rcx
0x14004824f  mov     [rcx+518h], rax
0x140048256  mov     rcx, [rbp+37h+var_70]
0x14004825a  mov     rcx, [rcx+518h]
0x140048261  call    RfsInitializeRundownProtectionCacheAwareEx
0x140048266  movzx   ecx, word ptr [r14+2]
0x14004826b  mov     rax, [rbp+37h+var_70]
0x14004826f  mov     [rax+16Ah], cx
0x140048276  xor     ecx, ecx
0x140048278  mov     rax, [rbp+37h+var_70]
0x14004827c  mov     [rax+168h], cx
0x140048283  mov     rdx, [rbp+37h+var_70]
0x140048287  mov     rcx, [rdx+518h]
0x14004828e  add     rcx, rbx
0x140048291  mov     [rdx+170h], rcx
0x140048298  mov     rdx, r14; SourceString
0x14004829b  mov     rcx, [rbp+37h+var_70]
0x14004829f  add     rcx, 168h; DestinationString
0x1400482a6  call    cs:__imp_RtlCopyUnicodeString
0x1400482ad  nop     dword ptr [rax+rax+00h]
0x1400482b2  mov     rax, [rbp+37h+var_70]
0x1400482b6  add     rax, 1B0h
0x1400482bc  mov     [rax+8], rax
0x1400482c0  mov     [rax], rax
0x1400482c3  mov     rcx, [rbp+37h+var_70]
0x1400482c7  add     rcx, 1A0h; SpinLock
0x1400482ce  call    cs:__imp_KeInitializeSpinLock
0x1400482d5  nop     dword ptr [rax+rax+00h]
0x1400482da  mov     rcx, [rbp+37h+var_70]
0x1400482de  add     rcx, 1C0h; SListHead
0x1400482e5  call    cs:__imp_InitializeSListHead
0x1400482ec  nop     dword ptr [rax+rax+00h]
0x1400482f1  mov     r9, [rbp+37h+var_70]
0x1400482f5  lea     rbx, [r9+52Fh]
0x1400482fc  add     rbx, rdi
0x1400482ff  xor     edi, edi
0x140048301  and     rbx, 0FFFFFFFFFFFFFFF0h
0x140048305  cmp     cs:FspPerDeviceThreshold, edi
0x14004830b  jbe     short loc_14004834A
0x14004830d  lea     rcx, [r9+1C0h]; ListHead
0x140048314  mov     rdx, rbx; ListEntry
0x140048317  call    cs:__imp_ExpInterlockedPushEntrySList
0x14004831e  nop     dword ptr [rax+rax+00h]
0x140048323  call    cs:__imp_IoSizeofWorkItem
0x14004832a  nop     dword ptr [rax+rax+00h]
0x14004832f  mov     r9, [rbp+37h+var_70]
0x140048333  inc     edi
0x140048335  mov     eax, eax
0x140048337  add     rax, 0Fh
0x14004833b  add     rbx, rax
0x14004833e  and     rbx, 0FFFFFFFFFFFFFFF0h
0x140048342  cmp     edi, cs:FspPerDeviceThreshold
0x140048348  jb      short loc_14004830D
0x14004834a  mov     rcx, cs:WPP_GLOBAL_Control
0x140048351  lea     rax, WPP_GLOBAL_Control
0x140048358  mov     r13d, 2
0x14004835e  cmp     rcx, rax
0x140048361  jz      short loc_14004838A
0x140048363  mov     eax, [rcx+2Ch]
0x140048366  test    r13b, al
0x140048369  jz      short loc_14004838A
0x14004836b  cmp     [rcx+29h], r13b
0x14004836f  jb      short loc_14004838A
0x140048371  mov     rcx, [rcx+18h]
0x140048375  lea     edx, [r13+0Ch]
  ... truncated ...
```
