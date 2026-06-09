# IopInitializeBootDrivers

- ea: `0x140c60bf8`
- end: `0x140c616d3`
- name: `IopInitializeBootDrivers`
- size: `2779`
- prototype: ``
- caller_count: `1`
- callee_count: `49`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140c5c6f4`

## callees

- `0x140226190`
- `0x140226320`
- `0x1403f2d50`
- `0x140406bc0`
- `0x14043cbb0`
- `0x140455b74`
- `0x1404a13f0`
- `0x1404a1488`
- `0x1404bb69c`
- `0x1405db338`
- `0x1405dbb68`
- `0x1406d9d70`
- `0x1406daa70`
- `0x140730898`
- `0x140755a60`
- `0x14075c0c4`
- `0x140764220`
- `0x14076d3e4`
- `0x1408d2294`
- `0x1408d3940`
- `0x14095a2d0`
- `0x14096c1c0`
- `0x14097499c`
- `0x14097501c`
- `0x140975158`
- `0x1409df8c0`
- `0x140a3b768`
- `0x140a85084`
- `0x140bae410`
- `0x140bae8e0`
- `0x140c1f488`
- `0x140c5dda0`
- `0x140c5fecc`
- `0x140c60bf8`
- `0x140c631c0`
- `0x140c63cf0`
- `0x140c64e64`
- `0x140c64f10`
- `0x140c6523c`
- `0x140c65418`
- `0x140c66bc8`
- `0x140ca1eb4`
- `0x140ca2138`
- `0x140ca3444`
- `0x140ca4514`
- `0x140ca4938`
- `0x140ca787c`
- `0x140ca979c`
- `0x140ca9b70`

## import_xrefs

- `ext-ms-win-ntos-stateseparation-l1-1-1!ExpInitializeStateSeparationCreateOsRoots` at `0x140c613a6`
- `ext-ms-win-ntos-stateseparation-l1-1-1!ExpInitializeStateSeparationCreateOsRoots` at `0x140c613a6`

## string_xrefs

- `0x140c60c84`: `\Registry\Machine\System\CurrentControlSet\Policies\EarlyLaunch`
- `0x140c60cbe`: `\Registry\Machine\System\CurrentControlSet\Control\EarlyLaunch`

## pseudocode

```c
__int64 __fastcall IopInitializeBootDrivers(__int64 a1)
{
  int RegistryValue; // ebx
  __int64 result; // rax
  struct _LIST_ENTRY *v4; // rsi
  int GroupOrderIndex; // eax
  struct _LIST_ENTRY *Blink; // r8
  unsigned int v7; // r9d
  unsigned __int16 i; // dx
  __int64 v9; // rcx
  struct _LIST_ENTRY *v10; // rcx
  unsigned __int16 v11; // bx
  unsigned __int16 v12; // di
  __int64 v13; // r14
  int *v14; // rbx
  __int64 *v15; // r12
  struct _LIST_ENTRY **Pool2; // rax
  struct _LIST_ENTRY **v17; // rdi
  int v18; // ebx
  unsigned __int16 DriverTagPriority; // ax
  struct _LIST_ENTRY *v20; // r8
  struct _LIST_ENTRY *j; // rcx
  struct _LIST_ENTRY *v22; // rax
  struct _LIST_ENTRY *Flink; // rcx
  unsigned __int16 v24; // r14
  __int64 v25; // r12
  __int64 v26; // rdi
  struct _LIST_ENTRY *k; // rbx
  struct _LIST_ENTRY *v28; // r13
  struct _LIST_ENTRY *v29; // rax
  PVOID v30; // rsi
  int started; // eax
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  __int64 v35; // rcx
  __int64 v36; // rcx
  NTSTATUS v37; // edx
  unsigned __int16 m; // r15
  __int64 v39; // r13
  struct _LIST_ENTRY *v40; // rcx
  struct _LIST_ENTRY *v41; // rbx
  struct _LIST_ENTRY *v42; // rax
  struct _LIST_ENTRY *v43; // rdi
  __int64 v44; // rdx
  PVOID v45; // r14
  struct _LIST_ENTRY *v46; // rsi
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 p_Blink; // r8
  int v50; // edx
  int v51; // ecx
  int v52; // r8d
  PVOID v53; // r12
  void *dwFlags; // [rsp+20h] [rbp-E0h]
  __int64 v55; // [rsp+30h] [rbp-D0h]
  __int64 v56; // [rsp+30h] [rbp-D0h]
  HANDLE Handle; // [rsp+40h] [rbp-C0h] BYREF
  int Index; // [rsp+48h] [rbp-B8h]
  PVOID Object; // [rsp+50h] [rbp-B0h] BYREF
  int v60; // [rsp+58h] [rbp-A8h] BYREF
  int v61; // [rsp+5Ch] [rbp-A4h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h]
  __int64 v63; // [rsp+68h] [rbp-98h] BYREF
  struct _LIST_ENTRY *v64; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v65[2]; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v66; // [rsp+80h] [rbp-80h]
  PVOID v67[2]; // [rsp+88h] [rbp-78h] BYREF
  UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  __int128 v69; // [rsp+A8h] [rbp-58h] BYREF
  UNICODE_STRING String1; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v71; // [rsp+C8h] [rbp-38h] BYREF
  int v72; // [rsp+D8h] [rbp-28h]
  UNICODE_STRING String2; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t pszDest[64]; // [rsp+F0h] [rbp-10h] BYREF

  v61 = 0;
  Handle = 0;
  P = 0;
  v64 = 0;
  v63 = 0;
  v60 = 0;
  String2 = 0;
  v72 = 0;
  *(_OWORD *)v67 = 0;
  Object = 0;
  String1 = 0;
  v65[1] = 0;
  v69 = 0;
  DestinationString = 0;
  v71 = 0;
  PnpDiagnosticTrace(&KMPnPEvt_BootStart_Start, 0, 0);
  PnpDriverImageLoadPolicy = 3;
  v66 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies\\EarlyLaunch";
  v65[0] = 8388734;
  if ( (int)IopOpenRegistryKeyEx(&Handle, 0, v65, 131097) >= 0
    || (v65[0] = 8257660,
        v66 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\EarlyLaunch",
        (int)IopOpenRegistryKeyEx(&Handle, 0, v65, 131097) >= 0) )
  {
    RegistryValue = IopGetRegistryValue(Handle);
    ZwClose(Handle);
    if ( RegistryValue >= 0 )
    {
      if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) >= 4u )
        PnpDriverImageLoadPolicy = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
      ExFreePoolWithTag(P, 0);
    }
  }
  if ( PnpDriverImageLoadPolicy == 8 )
  {
    PnpDriverImageLoadPolicy = 0;
  }
  else if ( (PnpDriverImageLoadPolicy & 0xFFFFFFF8) != 0 )
  {
    PnpDriverImageLoadPolicy = 3;
  }
  PipInitializeCoreDriversAndElam(a1);
  LODWORD(v69) = 2097182;
  *((_QWORD *)&v69 + 1) = L"\\FileSystem\\RAW";
  LODWORD(v67[0]) = 0x20000;
  v67[1] = (PVOID)&word_140CABDE0;
  result = PnpInitializeBootStartDriver((unsigned int)&v69, (unsigned int)v67, (unsigned int)RawInitialize, 0, 0, 0);
  v4 = (struct _LIST_ENTRY *)Object;
  if ( !Object )
  {
    LODWORD(IopInitFailCode) = 30;
    return result;
  }
  GroupOrderIndex = (unsigned __int16)PpInitGetGroupOrderIndex(0);
  *(_DWORD *)&IoInvalidateBusRelationsWorkerLock.ApcStateFill[32] = GroupOrderIndex;
  Index = 0xFFFF;
  if ( (unsigned __int16)GroupOrderIndex == 0xFFFF )
  {
    HeadlessKernelAddLogEntry(16, 0);
    result = 3221226021LL;
    LODWORD(IopInitFailCode) = 31;
    return result;
  }
  IoInvalidateBusRelationsWorkerLock.ApcState.ApcListHead[1].Blink = (struct _LIST_ENTRY *)ExAllocatePool2(
                                                                                             256,
                                                                                             16LL
                                                                                           * (unsigned __int16)GroupOrderIndex,
                                                                                             1852403792);
  Blink = IoInvalidateBusRelationsWorkerLock.ApcState.ApcListHead[1].Blink;
  if ( !IoInvalidateBusRelationsWorkerLock.ApcState.ApcListHead[1].Blink )
  {
    HeadlessKernelAddLogEntry(17, 0);
    result = 3221225626LL;
    LODWORD(IopInitFailCode) = 32;
    return result;
  }
  v7 = *(_DWORD *)&IoInvalidateBusRelationsWorkerLock.ApcStateFill[32];
  for ( i = 0; i < v7; v10->Flink = v10 )
  {
    v9 = i++;
    v10 = &Blink[v9];
    v10->Blink = v10;
  }
  PipInitializeDriverDependentDLLs(2, a1, Blink);
  RtlInitUnicodeString(&DestinationString, L"System Reserved");
  RtlInitUnicodeString(&String2, L"Boot Bus Extender");
  v11 = 0;
  v12 = 0;
  if ( !PiInitGroupOrderTableCount )
    goto LABEL_28;
  do
  {
    v13 = 16LL * v12;
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)((char *)PiInitGroupOrderTable + v13), &DestinationString, 1u) )
      goto LABEL_24;
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)((char *)PiInitGroupOrderTable + v13), &String2, 1u) )
    {
      LOWORD(Index) = v12;
LABEL_24:
      ++v11;
    }
    if ( v11 >= 2u )
      break;
    ++v12;
  }
  while ( v12 < (unsigned __int16)PiInitGroupOrderTableCount );
  v4 = (struct _LIST_ENTRY *)Object;
LABEL_28:
  v14 = *(int **)(a1 + 48);
  if ( v14 != (int *)(a1 + 48) )
  {
    do
    {
      v15 = *(__int64 **)v14;
      if ( v14[14] >= 0 )
      {
        Pool2 = (struct _LIST_ENTRY **)ExAllocatePool2(256, 48, 1852403792);
        v17 = Pool2;
        if ( Pool2 )
        {
          Pool2[1] = (struct _LIST_ENTRY *)Pool2;
          *Pool2 = (struct _LIST_ENTRY *)Pool2;
          Pool2[3] = (struct _LIST_ENTRY *)v14;
          if ( (int)IopOpenRegistryKeyEx(&Handle, 0, v14 + 8, 131097) >= 0 )
          {
            v17[4] = (struct _LIST_ENTRY *)Handle;
            v18 = (unsigned __int16)PpInitGetGroupOrderIndex(Handle);
            DriverTagPriority = PipGetDriverTagPriority(Handle);
            *((_WORD *)v17 + 22) = DriverTagPriority;
            v20 = &IoInvalidateBusRelationsWorkerLock.ApcState.ApcListHead[1].Blink[v18];
            for ( j = v20->Flink; j != v20 && WORD2(j[2].Blink) <= DriverTagPriority; j = j->Flink )
              ;
            v22 = j->Blink;
            Flink = v22->Flink;
            if ( v22->Flink->Blink != v22 )
LABEL_127:
              __fastfail(3u);
            *v17 = Flink;
            v17[1] = v22;
            Flink->Blink = (struct _LIST_ENTRY *)v17;
            v22->Flink = (struct _LIST_ENTRY *)v17;
          }
          else
          {
            ExFreePoolWithTag(v17, 0);
          }
        }
      }
      v14 = (int *)v15;
    }
    while ( v15 != (__int64 *)(a1 + 48) );
  }
  PnpNotifyEarlyLaunchStatusUpdate(1);
  v24 = 0;
LABEL_41:
  if ( (unsigned int)v24 < *(_DWORD *)&IoInvalidateBusRelationsWorkerLock.ApcStateFill[32] )
  {
    v25 = v24;
    v26 = 0;
    for ( k = IoInvalidateBusRelationsWorkerLock.ApcState.ApcListHead[1].Blink[v25].Flink; ; k = k->Flink )
    {
      if ( k == &IoInvalidateBusRelationsWorkerLock.ApcState.ApcListHead[1].Blink[v25] )
      {
        if ( v24 == (_WORD)Index )
        {
          IopAllocateLegacyBootResources(0, 0);
          IopBootConfigsReserved = 1;
          IopAllocateBootResourcesRoutine = (__int64)IopAllocateBootResources;
        }
        ++v24;
        goto LABEL_41;
      }
      Handle = k[2].Flink;
      v28 = k[1].Blink;
      v29 = v28[3].Flink;
      HIBYTE(k[2].Blink) = 1;
      *(_QWORD *)&DestinationString.Length = v29;
      if ( (int)IopGetDriverNameFromKeyNode(Handle, (PUNICODE_STRING)v67) < 0 )
      {
        BYTE6(k[2].Blink) = 1;
        goto LABEL_61;
      }
      if ( (int)IopGetRegistryValue(Handle) >= 0 )
      {
        v30 = P;
        if ( *((_DWORD *)P + 3) )
        {
          String1.Length = *((_WORD *)P + 6);
          String1.MaximumLength = String1.Length;
          String1.Buffer = (wchar_t *)((char *)P + *((unsigned int *)P + 2));
          v26 = PipLookupGroupName(&String1);
        }
        ExFreePoolWithTag(v30, 0);
      }
      v4 = 0;
      if ( !(unsigned int)PipCheckDependencies(Handle) )
        goto LABEL_59;
      v4 = k[1].Flink;
      Object = v4;
      if ( !v4 && !BYTE6(k[2].Blink) )
      {
        started = PnpInitializeBootStartDriver(
                    (unsigned int)v67,
                    (int)v28 + 32,
                    *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 56LL),
                    *(_DWORD *)&DestinationString.Length,
                    0,
                    1);
        v4 = (struct _LIST_ENTRY *)Object;
        LODWORD(k[2].Blink) = started;
        if ( !v4 )
          goto LABEL_59;
        ObfReferenceObjectWithTag(v4, 0x746C6644u);
      }
      if ( v4 )
      {
        if ( v26 )
          ++*(_DWORD *)(v26 + 28);
        k[1].Flink = v4;
        goto LABEL_60;
      }
LABEL_59:
      BYTE6(k[2].Blink) = 1;
LABEL_60:
      ExFreePoolWithTag(v67[1], 0);
      v26 = 0;
LABEL_61:
      if ( !BYTE6(k[2].Blink) )
      {
        PnpLockDeviceActionQueue();
        PipApplyFunctionToServiceInstances(v32, (int)&v4[3].Flink[1].Blink, v33, v34, dwFlags, (__int64)v4, v55);
        PnpUnlockDeviceActionQueue();
        PnpWaitForEmptyDeviceActionQueue();
        PnpRequestDeviceAction(0, 0, 0, 0);
      }
      if ( (int)PnpWaitForEmptyDeviceEventQueue() < 0 )
      {
        HeadlessKernelAddLogEntry(18, 0);
        LODWORD(IopInitFailCode) = 33;
        return 3221226621LL;
      }
    }
  }
  PnpNotifyEarlyLaunchStatusUpdate(2);
  PipUnloadEarlyLaunchDrivers(a1);
  PnPBootDriversLoaded = 1;
  PnpRequestDeviceAction(0, 0, 0, 0);
  if ( !(unsigned int)PnpWaitForDevicesToStart() )
  {
    HeadlessKernelAddLogEntry(19, 0);
    LODWORD(IopInitFailCode) = 34;
    return 3221226621LL;
  }
  if ( (unsigned __int8)IopCallBootDriverReinitializationRoutines() && !(unsigned int)PnpWaitForDevicesToStart() )
  {
    HeadlessKernelAddLogEntry(20, 0);
    LODWORD(IopInitFailCode) = 35;
    return 3221226621LL;
  }
  if ( (int)RamdiskInitialize(0, a1, &v71) < 0 )
    goto LABEL_130;
  if ( !(unsigned int)PnpWaitForDevicesToStart() )
  {
    HeadlessKernelAddLogEntry(19, 0);
    LODWORD(IopInitFailCode) = 36;
    return 3221226621LL;
  }
  result = RamdiskInitialize(1, a1, &v71);
  if ( (int)result >= 0 )
  {
LABEL_130:
    if ( (int)VhdInitialize(a1) < 0 || (unsigned int)PnpWaitForDevicesToStart() )
    {
      IoMountBootLayer(*(_QWORD *)(*(_QWORD *)(a1 + 240) + 4392LL));
      result = IopCreateArcNames(a1);
      if ( (int)result >= 0 )
      {
        PnpBootDeviceWait(a1, 1, &IopMarkBootPartition, 0);
        PnPBootDriversInitialized = 1;
        VhdAutoAttachVirtualDisks();
        result = PipWaitCriticalDevices(a1);
        if ( (int)result >= 0 )
        {
          LOBYTE(v35) = HIDWORD(WheapPfaLock.KernelStack) != 0;
          result = ExpInitializeStateSeparationCreateOsRoots(v35);
          if ( (int)(result + 0x80000000) < 0 || (_DWORD)result == -1073741637 )
          {
            result = PiCreateDriverDataDirectoryRoot();
            if ( (int)result >= 0 )
            {
              pszDest[0] = 0;
              Index = PipHardwareConfigGetIndex(v36, &v61);
              v37 = Index;
              if ( Index >= 0 )
              {
                LODWORD(v56) = v61;
                v37 = RtlStringCchPrintfExW(pszDest, 0x40u, 0, 0, 0x800u, L"%d", v56, &Object);
                Index = v37;
              }
              for ( m = 0; (unsigned int)m < *(_DWORD *)&IoInvalidateBusRelationsWorkerLock.ApcStateFill[32]; ++m )
              {
                v39 = m;
                while ( 1 )
                {
                  v40 = &IoInvalidateBusRelationsWorkerLock.ApcState.ApcListHead[1].Blink[v39];
                  v41 = IoInvalidateBusRelationsWorkerLock.ApcState.ApcListHead[1].Blink[v39].Flink;
                  if ( v41 == &IoInvalidateBusRelationsWorkerLock.ApcState.ApcListHead[1].Blink[v39] )
                    break;
                  if ( v41->Blink != v40 )
                    goto LABEL_127;
                  v42 = v41->Flink;
                  if ( v41->Flink->Blink != v41 )
                    goto LABEL_127;
                  v40->Flink = v42;
                  v42->Blink = v40;
                  v43 = v41[1].Flink;
                  if ( v37 >= 0
                    && !BYTE6(v41[2].Blink)
                    && !v43->Blink
                    && v43[3].Flink->Blink
                    && ((__int64)v43[1].Flink & 0x408) == 0
                    && (int)IopGetRegistryValue(v41[2].Flink) >= 0 )
                  {
                    v45 = P;
                    if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) >= 4u )
                    {
                      v60 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
                      if ( !v60 )
                      {
                        v60 = 3;
                        if ( (int)PiCreateDriverRedirectedStateKey(&v43[3].Flink[1].Blink, v44, &v64) >= 0 )
                        {
                          v46 = v64;
                        }
                        else
                        {
                          v46 = v41[2].Flink;
                          v64 = v46;
                        }
                        if ( (int)PnpCtxRegCreateKey(
                                    PiPnpRtlCtx,
                                    (_DWORD)v46,
                                    (unsigned int)L"StartOverride",
                                    0,
                                    2,
                                    0,
                                    (__int64)&v63,
                                    0) >= 0 )
                        {
                          PnpCtxRegSetValue(v47, v63, pszDest, 4, &v60, 4);
                          PnpCtxRegCloseKey(v48, v63);
                          v63 = 0;
                          if ( (byte_140EDA02B & 2) != 0 )
                          {
                            p_Blink = (__int64)&v43[3].Flink[1].Blink;
                            Object = 0;
                            if ( (int)PnpUnicodeStringToWstr(&Object, 0, p_Blink) >= 0 )
                            {
                              v53 = Object;
                              if ( (byte_140EDA02B & 2) != 0 )
                                McTemplateK0dzd_EtwWriteTransfer(v51, v50, v52, v61, (__int64)Object, v60);
                              PnpUnicodeStringToWstrFree(v53, &v43[3].Flink[1].Blink);
                            }
                          }
                        }
                        if ( v46 != v41[2].Flink )
                        {
                          ZwClose(v46);
                          v64 = 0;
                        }
                      }
                    }
                    ExFreePoolWithTag(v45, 0);
                  }
                  if ( v43 )
                    ObfDereferenceObjectWithTag(v43, 0x746C6644u);
                  if ( BYTE6(v41[2].Blink) )
                    LODWORD(v41[1].Blink[3].Flink[6].Blink) |= 0x20000u;
                  ZwClose(v41[2].Flink);
                  ExFreePoolWithTag(v41, 0);
                  v37 = Index;
                }
              }
              ExFreePoolWithTag(IoInvalidateBusRelationsWorkerLock.ApcState.ApcListHead[1].Blink, 0);
              PnpUnusedBootDriversCleanedUp = 1;
              PnpDiagnosticTrace(&KMPnPEvt_BootStart_Stop, 0, 0);
              return 0;
            }
            else
            {
              LODWORD(IopInitFailCode) = 43;
            }
          }
          else
          {
            LODWORD(IopInitFailCode) = 45;
          }
        }
        else
        {
          LODWORD(IopInitFailCode) = 42;
        }
      }
      else
      {
        LODWORD(IopInitFailCode) = 39;
      }
    }
    else
    {
      HeadlessKernelAddLogEntry(19, 0);
      LODWORD(IopInitFailCode) = 37;
      return 3221226621LL;
    }
  }
  else
  {
    LODWORD(IopInitFailCode) = 46;
  }
  return result;
}

```

## disassembly

```asm
0x140c60bf8  push    rbp
0x140c60bfa  push    rbx
0x140c60bfb  push    rsi
0x140c60bfc  push    rdi
0x140c60bfd  push    r12
0x140c60bff  push    r13
0x140c60c01  push    r14
0x140c60c03  push    r15
0x140c60c05  lea     rbp, [rsp-88h]
0x140c60c0d  sub     rsp, 188h
0x140c60c14  mov     rax, cs:__security_cookie
0x140c60c1b  xor     rax, rsp
0x140c60c1e  mov     [rbp+0C0h+var_50], rax
0x140c60c22  xor     r12d, r12d
0x140c60c25  xorps   xmm0, xmm0
0x140c60c28  xorps   xmm1, xmm1
0x140c60c2b  mov     [rsp+1C0h+var_164], r12d
0x140c60c30  mov     r15, rcx
0x140c60c33  mov     [rsp+1C0h+Handle], r12
0x140c60c38  xor     eax, eax
0x140c60c3a  mov     [rsp+1C0h+P], r12
0x140c60c3f  lea     rcx, KMPnPEvt_BootStart_Start; EventDescriptor
0x140c60c46  mov     [rsp+1C0h+var_150], r12
0x140c60c4b  xor     r8d, r8d; UserData
0x140c60c4e  mov     [rsp+1C0h+var_158], r12
0x140c60c53  xor     edx, edx; UserDataCount
0x140c60c55  mov     [rsp+1C0h+var_168], r12d
0x140c60c5a  movups  xmmword ptr [rbp+0C0h+String2.Length], xmm0
0x140c60c5e  mov     [rbp+0C0h+var_E8], eax
0x140c60c61  movups  xmmword ptr [rbp+0C0h+var_138], xmm1
0x140c60c65  mov     [rsp+1C0h+Object], r12
0x140c60c6a  movups  xmmword ptr [rbp+0C0h+String1.Length], xmm0
0x140c60c6e  movups  [rsp+1C0h+var_148], xmm0
0x140c60c73  movups  [rbp+0C0h+var_118], xmm1
0x140c60c77  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x140c60c7b  movups  [rbp+0C0h+var_F8], xmm1
0x140c60c7f  call    PnpDiagnosticTrace
0x140c60c84  lea     rax, aRegistryMachin_96; "\\Registry\\Machine\\System\\CurrentCon"...
0x140c60c8b  mov     cs:PnpDriverImageLoadPolicy, 3
0x140c60c95  mov     edi, 20019h
0x140c60c9a  mov     qword ptr [rbp+0C0h+var_148+8], rax
0x140c60c9e  mov     r9d, edi
0x140c60ca1  mov     dword ptr [rsp+1C0h+var_148], 80007Eh
0x140c60ca9  lea     r8, [rsp+1C0h+var_148]
0x140c60cae  xor     edx, edx
0x140c60cb0  lea     rcx, [rsp+1C0h+Handle]
0x140c60cb5  call    IopOpenRegistryKeyEx
0x140c60cba  test    eax, eax
0x140c60cbc  jns     short loc_140C60CE9
0x140c60cbe  lea     rax, aRegistryMachin_94; "\\Registry\\Machine\\System\\CurrentCon"...
0x140c60cc5  mov     dword ptr [rsp+1C0h+var_148], 7E007Ch
0x140c60ccd  mov     r9d, edi
0x140c60cd0  mov     qword ptr [rbp+0C0h+var_148+8], rax
0x140c60cd4  lea     r8, [rsp+1C0h+var_148]
0x140c60cd9  xor     edx, edx
0x140c60cdb  lea     rcx, [rsp+1C0h+Handle]
0x140c60ce0  call    IopOpenRegistryKeyEx
0x140c60ce5  test    eax, eax
0x140c60ce7  js      short loc_140C60D3D
0x140c60ce9  mov     rcx, [rsp+1C0h+Handle]; KeyHandle
0x140c60cee  lea     r9, [rsp+1C0h+P]
0x140c60cf3  xor     r8d, r8d
0x140c60cf6  lea     rdx, aDriverloadpoli; "DriverLoadPolicy"
0x140c60cfd  call    IopGetRegistryValue
0x140c60d02  mov     rcx, [rsp+1C0h+Handle]; Handle
0x140c60d07  mov     ebx, eax
0x140c60d09  call    ZwClose
0x140c60d0e  test    ebx, ebx
0x140c60d10  js      short loc_140C60D3D
0x140c60d12  mov     r8, [rsp+1C0h+P]
0x140c60d17  cmp     dword ptr [r8+4], 4
0x140c60d1c  jnz     short loc_140C60D33
0x140c60d1e  cmp     dword ptr [r8+0Ch], 4
0x140c60d23  jb      short loc_140C60D33
0x140c60d25  mov     eax, [r8+8]
0x140c60d29  mov     ecx, [rax+r8]
0x140c60d2d  mov     cs:PnpDriverImageLoadPolicy, ecx
0x140c60d33  xor     edx, edx; Tag
0x140c60d35  mov     rcx, r8; P
0x140c60d38  call    ExFreePoolWithTag
0x140c60d3d  mov     eax, cs:PnpDriverImageLoadPolicy
0x140c60d43  cmp     eax, 8
0x140c60d46  jnz     short loc_140C60D51
0x140c60d48  mov     cs:PnpDriverImageLoadPolicy, r12d
0x140c60d4f  jmp     short loc_140C60D62
0x140c60d51  test    eax, 0FFFFFFF8h
0x140c60d56  jz      short loc_140C60D62
0x140c60d58  mov     cs:PnpDriverImageLoadPolicy, 3
0x140c60d62  mov     rcx, r15
0x140c60d65  call    PipInitializeCoreDriversAndElam
0x140c60d6a  lea     rax, aFilesystemRaw; "\\FileSystem\\RAW"
0x140c60d71  mov     dword ptr [rbp+0C0h+var_118], 20001Eh
0x140c60d78  mov     qword ptr [rbp+0C0h+var_118+8], rax
0x140c60d7c  lea     r8, RawInitialize
0x140c60d83  lea     rax, word_140CABDE0
0x140c60d8a  mov     dword ptr [rbp+0C0h+var_138], 20000h
0x140c60d91  mov     [rbp+0C0h+var_138+8], rax
0x140c60d95  lea     rdx, [rbp+0C0h+var_138]
0x140c60d99  mov     edi, 20h ; ' '
0x140c60d9e  lea     rax, [rsp+1C0h+Object]
0x140c60da3  mov     [rsp+1C0h+var_188], rax
0x140c60da8  lea     rcx, [rbp+0C0h+var_118]
0x140c60dac  mov     dword ptr [rsp+1C0h+pszFormat], r12d
0x140c60db1  xor     r9d, r9d
0x140c60db4  mov     [rsp+1C0h+dwFlags], r12d
0x140c60db9  lea     ebx, [rdi-2]
0x140c60dbc  lea     r14d, [rdi-1Eh]
0x140c60dc0  call    PnpInitializeBootStartDriver
0x140c60dc5  mov     rsi, [rsp+1C0h+Object]
0x140c60dca  mov     [rsp+1C0h+Object], rsi
0x140c60dcf  test    rsi, rsi
0x140c60dd2  jnz     short loc_140C60DDF
0x140c60dd4  mov     cs:IopInitFailCode, ebx
0x140c60dda  jmp     loc_140C616AB
0x140c60ddf  xor     ecx, ecx
0x140c60de1  call    PpInitGetGroupOrderIndex
0x140c60de6  movzx   eax, ax
0x140c60de9  mov     r13d, 0FFFFh
0x140c60def  mov     dword ptr cs:IoInvalidateBusRelationsWorkerLock.___u25+20h, eax
0x140c60df5  mov     [rsp+1C0h+var_178], r13d
0x140c60dfa  cmp     eax, r13d
0x140c60dfd  jnz     short loc_140C60E1D
0x140c60dff  xor     edx, edx
0x140c60e01  lea     ecx, [rdx+10h]
0x140c60e04  call    HeadlessKernelAddLogEntry
0x140c60e09  mov     eax, 0C0000225h
0x140c60e0e  mov     cs:IopInitFailCode, 1Fh
0x140c60e18  jmp     loc_140C616AB
0x140c60e1d  mov     rdx, rax
0x140c60e20  mov     ecx, 100h
0x140c60e25  shl     rdx, 4
0x140c60e29  mov     r8d, 6E697050h
0x140c60e2f  call    ExAllocatePool2
0x140c60e34  mov     qword ptr cs:IoInvalidateBusRelationsWorkerLock.___u25+18h, rax
0x140c60e3b  mov     r8, rax
0x140c60e3e  test    rax, rax
0x140c60e41  jnz     short loc_140C60E5D
0x140c60e43  xor     edx, edx
0x140c60e45  lea     ecx, [rax+11h]
0x140c60e48  call    HeadlessKernelAddLogEntry
0x140c60e4d  mov     eax, 0C000009Ah
0x140c60e52  mov     cs:IopInitFailCode, edi
0x140c60e58  jmp     loc_140C616AB
0x140c60e5d  mov     r9d, dword ptr cs:IoInvalidateBusRelationsWorkerLock.___u25+20h
0x140c60e64  mov     edx, r12d
0x140c60e67  mov     r13d, 1
0x140c60e6d  test    r9d, r9d
0x140c60e70  jz      short loc_140C60E8F
0x140c60e72  movzx   ecx, dx
0x140c60e75  add     dx, r13w
0x140c60e79  shl     rcx, 4
0x140c60e7d  add     rcx, r8
0x140c60e80  movzx   eax, dx
0x140c60e83  mov     [rcx+8], rcx
0x140c60e87  mov     [rcx], rcx
0x140c60e8a  cmp     eax, r9d
0x140c60e8d  jb      short loc_140C60E72
0x140c60e8f  mov     rdx, r15
0x140c60e92  mov     ecx, r14d
0x140c60e95  call    PipInitializeDriverDependentDLLs
0x140c60e9a  lea     rdx, aSystemReserved; "System Reserved"
0x140c60ea1  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x140c60ea5  call    RtlInitUnicodeString
0x140c60eaa  lea     rdx, aBootBusExtende; "Boot Bus Extender"
0x140c60eb1  lea     rcx, [rbp+0C0h+String2]; DestinationString
0x140c60eb5  call    RtlInitUnicodeString
0x140c60eba  cmp     r12w, cs:PiInitGroupOrderTableCount
0x140c60ec2  mov     ebx, r12d
0x140c60ec5  mov     edi, r12d
0x140c60ec8  jnb     short loc_140C60F29
0x140c60eca  mov     esi, r14d
0x140c60ecd  mov     rcx, cs:PiInitGroupOrderTable
0x140c60ed4  lea     rdx, [rbp+0C0h+DestinationString]; String2
0x140c60ed8  movzx   r14d, di
0x140c60edc  mov     r8b, r13b; CaseInSensitive
0x140c60edf  shl     r14, 4
0x140c60ee3  add     rcx, r14; String1
0x140c60ee6  call    RtlCompareUnicodeString
0x140c60eeb  test    eax, eax
0x140c60eed  jz      short loc_140C60F0E
0x140c60eef  mov     rcx, cs:PiInitGroupOrderTable
0x140c60ef6  lea     rdx, [rbp+0C0h+String2]; String2
0x140c60efa  add     rcx, r14; String1
0x140c60efd  mov     r8b, r13b; CaseInSensitive
0x140c60f00  call    RtlCompareUnicodeString
0x140c60f05  test    eax, eax
0x140c60f07  jnz     short loc_140C60F12
0x140c60f09  mov     word ptr [rsp+1C0h+var_178], di
0x140c60f0e  add     bx, r13w
0x140c60f12  cmp     bx, si
0x140c60f15  jnb     short loc_140C60F24
0x140c60f17  add     di, r13w
0x140c60f1b  cmp     di, cs:PiInitGroupOrderTableCount
0x140c60f22  jb      short loc_140C60ECD
0x140c60f24  mov     rsi, [rsp+1C0h+Object]
0x140c60f29  lea     r14, [r15+30h]
0x140c60f2d  mov     rbx, [r14]
0x140c60f30  cmp     rbx, r14
0x140c60f33  jz      loc_140C6100B
0x140c60f39  cmp     dword ptr [rbx+38h], 0
0x140c60f3d  mov     r12, [rbx]
0x140c60f40  jl      loc_140C60FFC
0x140c60f46  mov     edx, 30h ; '0'
0x140c60f4b  mov     ecx, 100h
0x140c60f50  mov     r8d, 6E697050h
0x140c60f56  call    ExAllocatePool2
0x140c60f5b  mov     rdi, rax
0x140c60f5e  test    rax, rax
0x140c60f61  jz      loc_140C60FFC
0x140c60f67  mov     [rax+8], rax
0x140c60f6b  lea     r8, [rbx+20h]
0x140c60f6f  mov     [rax], rax
0x140c60f72  lea     rcx, [rsp+1C0h+Handle]
0x140c60f77  xor     edx, edx
0x140c60f79  mov     [rax+18h], rbx
0x140c60f7d  mov     r9d, 20019h
0x140c60f83  call    IopOpenRegistryKeyEx
0x140c60f88  test    eax, eax
0x140c60f8a  jns     short loc_140C60F98
0x140c60f8c  xor     edx, edx; Tag
0x140c60f8e  mov     rcx, rdi; P
0x140c60f91  call    ExFreePoolWithTag
0x140c60f96  jmp     short loc_140C60FFC
0x140c60f98  mov     rax, [rsp+1C0h+Handle]
0x140c60f9d  mov     [rdi+20h], rax
0x140c60fa1  mov     rcx, [rsp+1C0h+Handle]
0x140c60fa6  call    PpInitGetGroupOrderIndex
0x140c60fab  mov     rcx, [rsp+1C0h+Handle]; KeyHandle
0x140c60fb0  movzx   ebx, ax
0x140c60fb3  call    PipGetDriverTagPriority
0x140c60fb8  mov     r8d, ebx
0x140c60fbb  mov     [rdi+2Ch], ax
0x140c60fbf  shl     r8, 4
0x140c60fc3  add     r8, qword ptr cs:IoInvalidateBusRelationsWorkerLock.___u25+18h
0x140c60fca  mov     rcx, [r8]
0x140c60fcd  jmp     short loc_140C60FD8
0x140c60fcf  cmp     [rcx+2Ch], ax
0x140c60fd3  ja      short loc_140C60FDD
0x140c60fd5  mov     rcx, [rcx]
0x140c60fd8  cmp     rcx, r8
0x140c60fdb  jnz     short loc_140C60FCF
0x140c60fdd  mov     rax, [rcx+8]
0x140c60fe1  mov     rcx, [rax]
0x140c60fe4  cmp     [rcx+8], rax
0x140c60fe8  jnz     loc_140C616CC
0x140c60fee  mov     [rdi], rcx
0x140c60ff1  mov     [rdi+8], rax
0x140c60ff5  mov     [rcx+8], rdi
0x140c60ff9  mov     [rax], rdi
0x140c60ffc  mov     rbx, r12
0x140c60fff  cmp     r12, r14
0x140c61002  jnz     loc_140C60F39
0x140c61008  xor     r12d, r12d
0x140c6100b  mov     ecx, r13d
0x140c6100e  call    PnpNotifyEarlyLaunchStatusUpdate
0x140c61013  mov     r14d, r12d
0x140c61016  movzx   eax, r14w
0x140c6101a  cmp     eax, dword ptr cs:IoInvalidateBusRelationsWorkerLock.___u25+20h
0x140c61020  jnb     loc_140C61225
0x140c61026  mov     rax, qword ptr cs:IoInvalidateBusRelationsWorkerLock.___u25+18h
0x140c6102d  movzx   r12d, r14w
0x140c61031  shl     r12, 4
0x140c61035  xor     edi, edi
0x140c61037  mov     rbx, [r12+rax]
0x140c6103b  mov     rcx, qword ptr cs:IoInvalidateBusRelationsWorkerLock.___u25+18h
0x140c61042  add     rcx, r12
0x140c61045  cmp     rbx, rcx
0x140c61048  jz      loc_140C611D8
0x140c6104e  mov     rax, [rbx+20h]
0x140c61052  lea     rdx, [rbp+0C0h+var_138]; Destination
0x140c61056  mov     [rsp+1C0h+Handle], rax
0x140c6105b  mov     r13, [rbx+18h]
0x140c6105f  mov     rax, [r13+30h]
0x140c61063  mov     byte ptr [rbx+2Fh], 1
0x140c61067  mov     rcx, [rsp+1C0h+Handle]; KeyHandle
0x140c6106c  mov     qword ptr [rbp+0C0h+DestinationString.Length], rax
0x140c61070  call    IopGetDriverNameFromKeyNode
0x140c61075  test    eax, eax
0x140c61077  jns     short loc_140C61088
0x140c61079  mov     r13d, 1
0x140c6107f  mov     [rbx+2Eh], r13b
0x140c61083  jmp     loc_140C61180
0x140c61088  mov     rcx, [rsp+1C0h+Handle]; KeyHandle
0x140c6108d  lea     r9, [rsp+1C0h+P]
0x140c61092  xor     r8d, r8d
0x140c61095  lea     rdx, aGroup_0; "Group"
0x140c6109c  call    IopGetRegistryValue
0x140c610a1  test    eax, eax
0x140c610a3  js      short loc_140C610E0
0x140c610a5  mov     rsi, [rsp+1C0h+P]
0x140c610aa  cmp     [rsi+0Ch], edi
0x140c610ad  jz      short loc_140C610D6
0x140c610af  movzx   eax, word ptr [rsi+0Ch]
0x140c610b3  lea     rcx, [rbp+0C0h+String1]; String1
0x140c610b7  mov     [rbp+0C0h+String1.Length], ax
0x140c610bb  mov     edx, 1
0x140c610c0  mov     [rbp+0C0h+String1.MaximumLength], ax
0x140c610c4  mov     eax, [rsi+8]
0x140c610c7  add     rax, rsi
0x140c610ca  mov     [rbp+0C0h+String1.Buffer], rax
  ... truncated ...
```
