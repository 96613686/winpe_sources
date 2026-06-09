# IopInitializeBootDrivers

- ea: `0x140c65ec8`
- end: `0x140c669a3`
- name: `IopInitializeBootDrivers`
- size: `2779`
- prototype: ``
- caller_count: `1`
- callee_count: `49`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140c619c4`

## callees

- `0x140215d30`
- `0x140215ec0`
- `0x140403380`
- `0x14041e400`
- `0x140451de0`
- `0x1404671c4`
- `0x1404af400`
- `0x1404af498`
- `0x1404cb57c`
- `0x1405e1f18`
- `0x1405e2748`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x14073505c`
- `0x140759ee0`
- `0x140760534`
- `0x140768690`
- `0x140771854`
- `0x140877eb8`
- `0x14087852c`
- `0x140878bac`
- `0x140907074`
- `0x140908720`
- `0x140983ef0`
- `0x1409e5ea0`
- `0x140a420e8`
- `0x140a4b070`
- `0x140a8ba44`
- `0x140bb1410`
- `0x140bb19f0`
- `0x140c22488`
- `0x140c63070`
- `0x140c6519c`
- `0x140c65ec8`
- `0x140c68490`
- `0x140c68fc0`
- `0x140c6a134`
- `0x140c6a1e0`
- `0x140c6a50c`
- `0x140c6a6e8`
- `0x140c6be98`
- `0x140ca4a04`
- `0x140ca4c88`
- `0x140ca5f94`
- `0x140ca7064`
- `0x140ca7488`
- `0x140caa3cc`
- `0x140cac2ec`
- `0x140cac9d0`

## import_xrefs

- `ext-ms-win-ntos-stateseparation-l1-1-1!ExpInitializeStateSeparationCreateOsRoots` at `0x140c66676`
- `ext-ms-win-ntos-stateseparation-l1-1-1!ExpInitializeStateSeparationCreateOsRoots` at `0x140c66676`

## string_xrefs

- `0x140c65f54`: `\Registry\Machine\System\CurrentControlSet\Policies\EarlyLaunch`
- `0x140c65f8e`: `\Registry\Machine\System\CurrentControlSet\Control\EarlyLaunch`

## pseudocode

```c
__int64 __fastcall IopInitializeBootDrivers(__int64 a1)
{
  int RegistryValue; // ebx
  __int64 result; // rax
  _QWORD *v4; // rsi
  int GroupOrderIndex; // eax
  char *v6; // r8
  unsigned int v7; // r9d
  unsigned __int16 i; // dx
  __int64 v9; // rcx
  char *v10; // rcx
  unsigned __int16 v11; // bx
  unsigned __int16 v12; // di
  __int64 v13; // r14
  int *v14; // rbx
  __int64 *v15; // r12
  _QWORD *Pool2; // rax
  _QWORD *v17; // rdi
  unsigned int v18; // ebx
  unsigned __int16 DriverTagPriority; // ax
  __int64 **v20; // r8
  __int64 *j; // rcx
  __int64 *v22; // rax
  __int64 v23; // rcx
  unsigned __int16 v24; // r14
  __int64 v25; // r12
  __int64 v26; // rdi
  _QWORD *k; // rbx
  __int64 v28; // r13
  __int64 v29; // rax
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
  _QWORD *v40; // rcx
  __int64 *v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rdi
  __int64 v44; // rdx
  PVOID v45; // r14
  void *v46; // rsi
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // r8
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
  int v60; // [rsp+58h] [rbp-A8h]
  int v61; // [rsp+5Ch] [rbp-A4h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h]
  __int64 v63; // [rsp+68h] [rbp-98h] BYREF
  void *v64; // [rsp+70h] [rbp-90h] BYREF
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
  v67[1] = (PVOID)&word_140CAE7A0;
  result = PnpInitializeBootStartDriver((unsigned int)&v69, (unsigned int)v67, (unsigned int)RawInitialize, 0, 0, 0);
  v4 = Object;
  if ( !Object )
  {
    LODWORD(IopInitFailCode) = 30;
    return result;
  }
  GroupOrderIndex = (unsigned __int16)PpInitGetGroupOrderIndex(0);
  IopGroupIndex = GroupOrderIndex;
  Index = 0xFFFF;
  if ( (unsigned __int16)GroupOrderIndex == 0xFFFF )
  {
    HeadlessKernelAddLogEntry(16, 0);
    result = 3221226021LL;
    LODWORD(IopInitFailCode) = 31;
    return result;
  }
  IopGroupTable = (PVOID)ExAllocatePool2(256, 16LL * (unsigned __int16)GroupOrderIndex, 0x6E697050u);
  v6 = (char *)IopGroupTable;
  if ( !IopGroupTable )
  {
    HeadlessKernelAddLogEntry(17, 0);
    result = 3221225626LL;
    LODWORD(IopInitFailCode) = 32;
    return result;
  }
  v7 = IopGroupIndex;
  for ( i = 0; i < v7; *(_QWORD *)v10 = v10 )
  {
    v9 = i++;
    v10 = &v6[16 * v9];
    *((_QWORD *)v10 + 1) = v10;
  }
  PipInitializeDriverDependentDLLs(2, a1, v6);
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
  v4 = Object;
LABEL_28:
  v14 = *(int **)(a1 + 48);
  if ( v14 != (int *)(a1 + 48) )
  {
    do
    {
      v15 = *(__int64 **)v14;
      if ( v14[14] >= 0 )
      {
        Pool2 = (_QWORD *)ExAllocatePool2(256, 48, 0x6E697050u);
        v17 = Pool2;
        if ( Pool2 )
        {
          Pool2[1] = Pool2;
          *Pool2 = Pool2;
          Pool2[3] = v14;
          if ( (int)IopOpenRegistryKeyEx(&Handle, 0, v14 + 8, 131097) >= 0 )
          {
            v17[4] = Handle;
            v18 = (unsigned __int16)PpInitGetGroupOrderIndex(Handle);
            DriverTagPriority = PipGetDriverTagPriority(Handle);
            *((_WORD *)v17 + 22) = DriverTagPriority;
            v20 = (__int64 **)((char *)IopGroupTable + 16 * v18);
            for ( j = *v20; j != (__int64 *)v20 && *((_WORD *)j + 22) <= DriverTagPriority; j = (__int64 *)*j )
              ;
            v22 = (__int64 *)j[1];
            v23 = *v22;
            if ( *(__int64 **)(*v22 + 8) != v22 )
LABEL_127:
              __fastfail(3u);
            *v17 = v23;
            v17[1] = v22;
            *(_QWORD *)(v23 + 8) = v17;
            *v22 = (__int64)v17;
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
  if ( v24 < (unsigned int)IopGroupIndex )
  {
    v25 = 16LL * v24;
    v26 = 0;
    for ( k = *(_QWORD **)((char *)IopGroupTable + v25); ; k = (_QWORD *)*k )
    {
      if ( k == (_QWORD *)((char *)IopGroupTable + v25) )
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
      Handle = (HANDLE)k[4];
      v28 = k[3];
      v29 = *(_QWORD *)(v28 + 48);
      *((_BYTE *)k + 47) = 1;
      *(_QWORD *)&DestinationString.Length = v29;
      if ( (int)IopGetDriverNameFromKeyNode(Handle, (PUNICODE_STRING)v67) < 0 )
      {
        *((_BYTE *)k + 46) = 1;
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
      v4 = (_QWORD *)k[2];
      Object = v4;
      if ( !v4 && !*((_BYTE *)k + 46) )
      {
        started = PnpInitializeBootStartDriver(
                    (unsigned int)v67,
                    (int)v28 + 32,
                    *(_QWORD *)(*(_QWORD *)&DestinationString.Length + 56LL),
                    *(_DWORD *)&DestinationString.Length,
                    0,
                    1);
        v4 = Object;
        *((_DWORD *)k + 10) = started;
        if ( !v4 )
          goto LABEL_59;
        ObfReferenceObjectWithTag(v4, 0x746C6644u);
      }
      if ( v4 )
      {
        if ( v26 )
          ++*(_DWORD *)(v26 + 28);
        k[2] = v4;
        goto LABEL_60;
      }
LABEL_59:
      *((_BYTE *)k + 46) = 1;
LABEL_60:
      ExFreePoolWithTag(v67[1], 0);
      v26 = 0;
LABEL_61:
      if ( !*((_BYTE *)k + 46) )
      {
        PnpLockDeviceActionQueue();
        PipApplyFunctionToServiceInstances(v32, v4[6] + 24, v33, v34, dwFlags, (__int64)v4, v55);
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
          LOBYTE(v35) = CmStateSeparationEnabled != 0;
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
              for ( m = 0; m < (unsigned int)IopGroupIndex; ++m )
              {
                v39 = 16LL * m;
                while ( 1 )
                {
                  v40 = (char *)IopGroupTable + v39;
                  v41 = *(__int64 **)((char *)IopGroupTable + v39);
                  if ( v41 == (__int64 *)((char *)IopGroupTable + v39) )
                    break;
                  if ( (_QWORD *)v41[1] != v40 )
                    goto LABEL_127;
                  v42 = *v41;
                  if ( *(__int64 **)(*v41 + 8) != v41 )
                    goto LABEL_127;
                  *v40 = v42;
                  *(_QWORD *)(v42 + 8) = v40;
                  v43 = v41[2];
                  if ( v37 >= 0
                    && !*((_BYTE *)v41 + 46)
                    && !*(_QWORD *)(v43 + 8)
                    && *(_QWORD *)(*(_QWORD *)(v43 + 48) + 8LL)
                    && (*(_DWORD *)(v43 + 16) & 0x408) == 0
                    && (int)IopGetRegistryValue((HANDLE)v41[4]) >= 0 )
                  {
                    v45 = P;
                    if ( *((_DWORD *)P + 1) == 4 && *((_DWORD *)P + 3) >= 4u )
                    {
                      v60 = *(_DWORD *)((char *)P + *((unsigned int *)P + 2));
                      if ( !v60 )
                      {
                        v60 = 3;
                        if ( (int)PiCreateDriverRedirectedStateKey(*(_QWORD *)(v43 + 48) + 24LL, v44, &v64) >= 0 )
                        {
                          v46 = v64;
                        }
                        else
                        {
                          v46 = (void *)v41[4];
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
                          PnpCtxRegSetValue(v47, v63, pszDest);
                          PnpCtxRegCloseKey(v48, v63);
                          v63 = 0;
                          if ( (byte_140ED9FEB & 2) != 0 )
                          {
                            v49 = *(_QWORD *)(v43 + 48) + 24LL;
                            Object = 0;
                            if ( (int)PnpUnicodeStringToWstr(&Object, 0, v49) >= 0 )
                            {
                              v53 = Object;
                              if ( (byte_140ED9FEB & 2) != 0 )
                                McTemplateK0dzd_EtwWriteTransfer(v51, v50, v52, v61, (__int64)Object, v60);
                              PnpUnicodeStringToWstrFree(v53, *(_QWORD *)(v43 + 48) + 24LL);
                            }
                          }
                        }
                        if ( v46 != (void *)v41[4] )
                        {
                          ZwClose(v46);
                          v64 = 0;
                        }
                      }
                    }
                    ExFreePoolWithTag(v45, 0);
                  }
                  if ( v43 )
                    ObfDereferenceObjectWithTag((PVOID)v43, 0x746C6644u);
                  if ( *((_BYTE *)v41 + 46) )
                    *(_DWORD *)(*(_QWORD *)(v41[3] + 48) + 104LL) |= 0x20000u;
                  ZwClose((HANDLE)v41[4]);
                  ExFreePoolWithTag(v41, 0);
                  v37 = Index;
                }
              }
              ExFreePoolWithTag(IopGroupTable, 0);
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
0x140c65ec8  push    rbp
0x140c65eca  push    rbx
0x140c65ecb  push    rsi
0x140c65ecc  push    rdi
0x140c65ecd  push    r12
0x140c65ecf  push    r13
0x140c65ed1  push    r14
0x140c65ed3  push    r15
0x140c65ed5  lea     rbp, [rsp-88h]
0x140c65edd  sub     rsp, 188h
0x140c65ee4  mov     rax, cs:__security_cookie
0x140c65eeb  xor     rax, rsp
0x140c65eee  mov     [rbp+0C0h+var_50], rax
0x140c65ef2  xor     r12d, r12d
0x140c65ef5  xorps   xmm0, xmm0
0x140c65ef8  xorps   xmm1, xmm1
0x140c65efb  mov     [rsp+1C0h+var_164], r12d
0x140c65f00  mov     r15, rcx
0x140c65f03  mov     [rsp+1C0h+Handle], r12
0x140c65f08  xor     eax, eax
0x140c65f0a  mov     [rsp+1C0h+P], r12
0x140c65f0f  lea     rcx, KMPnPEvt_BootStart_Start; EventDescriptor
0x140c65f16  mov     [rsp+1C0h+var_150], r12
0x140c65f1b  xor     r8d, r8d; UserData
0x140c65f1e  mov     [rsp+1C0h+var_158], r12
0x140c65f23  xor     edx, edx; UserDataCount
0x140c65f25  mov     [rsp+1C0h+var_168], r12d
0x140c65f2a  movups  xmmword ptr [rbp+0C0h+String2.Length], xmm0
0x140c65f2e  mov     [rbp+0C0h+var_E8], eax
0x140c65f31  movups  xmmword ptr [rbp+0C0h+var_138], xmm1
0x140c65f35  mov     [rsp+1C0h+Object], r12
0x140c65f3a  movups  xmmword ptr [rbp+0C0h+String1.Length], xmm0
0x140c65f3e  movups  [rsp+1C0h+var_148], xmm0
0x140c65f43  movups  [rbp+0C0h+var_118], xmm1
0x140c65f47  movups  xmmword ptr [rbp+0C0h+DestinationString.Length], xmm0
0x140c65f4b  movups  [rbp+0C0h+var_F8], xmm1
0x140c65f4f  call    PnpDiagnosticTrace
0x140c65f54  lea     rax, aRegistryMachin_96; "\\Registry\\Machine\\System\\CurrentCon"...
0x140c65f5b  mov     cs:PnpDriverImageLoadPolicy, 3
0x140c65f65  mov     edi, 20019h
0x140c65f6a  mov     qword ptr [rbp+0C0h+var_148+8], rax
0x140c65f6e  mov     r9d, edi
0x140c65f71  mov     dword ptr [rsp+1C0h+var_148], 80007Eh
0x140c65f79  lea     r8, [rsp+1C0h+var_148]
0x140c65f7e  xor     edx, edx
0x140c65f80  lea     rcx, [rsp+1C0h+Handle]
0x140c65f85  call    IopOpenRegistryKeyEx
0x140c65f8a  test    eax, eax
0x140c65f8c  jns     short loc_140C65FB9
0x140c65f8e  lea     rax, aRegistryMachin_94; "\\Registry\\Machine\\System\\CurrentCon"...
0x140c65f95  mov     dword ptr [rsp+1C0h+var_148], 7E007Ch
0x140c65f9d  mov     r9d, edi
0x140c65fa0  mov     qword ptr [rbp+0C0h+var_148+8], rax
0x140c65fa4  lea     r8, [rsp+1C0h+var_148]
0x140c65fa9  xor     edx, edx
0x140c65fab  lea     rcx, [rsp+1C0h+Handle]
0x140c65fb0  call    IopOpenRegistryKeyEx
0x140c65fb5  test    eax, eax
0x140c65fb7  js      short loc_140C6600D
0x140c65fb9  mov     rcx, [rsp+1C0h+Handle]; KeyHandle
0x140c65fbe  lea     r9, [rsp+1C0h+P]
0x140c65fc3  xor     r8d, r8d
0x140c65fc6  lea     rdx, aDriverloadpoli; "DriverLoadPolicy"
0x140c65fcd  call    IopGetRegistryValue
0x140c65fd2  mov     rcx, [rsp+1C0h+Handle]; Handle
0x140c65fd7  mov     ebx, eax
0x140c65fd9  call    ZwClose
0x140c65fde  test    ebx, ebx
0x140c65fe0  js      short loc_140C6600D
0x140c65fe2  mov     r8, [rsp+1C0h+P]
0x140c65fe7  cmp     dword ptr [r8+4], 4
0x140c65fec  jnz     short loc_140C66003
0x140c65fee  cmp     dword ptr [r8+0Ch], 4
0x140c65ff3  jb      short loc_140C66003
0x140c65ff5  mov     eax, [r8+8]
0x140c65ff9  mov     ecx, [rax+r8]
0x140c65ffd  mov     cs:PnpDriverImageLoadPolicy, ecx
0x140c66003  xor     edx, edx; Tag
0x140c66005  mov     rcx, r8; P
0x140c66008  call    ExFreePoolWithTag
0x140c6600d  mov     eax, cs:PnpDriverImageLoadPolicy
0x140c66013  cmp     eax, 8
0x140c66016  jnz     short loc_140C66021
0x140c66018  mov     cs:PnpDriverImageLoadPolicy, r12d
0x140c6601f  jmp     short loc_140C66032
0x140c66021  test    eax, 0FFFFFFF8h
0x140c66026  jz      short loc_140C66032
0x140c66028  mov     cs:PnpDriverImageLoadPolicy, 3
0x140c66032  mov     rcx, r15
0x140c66035  call    PipInitializeCoreDriversAndElam
0x140c6603a  lea     rax, aFilesystemRaw; "\\FileSystem\\RAW"
0x140c66041  mov     dword ptr [rbp+0C0h+var_118], 20001Eh
0x140c66048  mov     qword ptr [rbp+0C0h+var_118+8], rax
0x140c6604c  lea     r8, RawInitialize
0x140c66053  lea     rax, word_140CAE7A0
0x140c6605a  mov     dword ptr [rbp+0C0h+var_138], 20000h
0x140c66061  mov     [rbp+0C0h+var_138+8], rax
0x140c66065  lea     rdx, [rbp+0C0h+var_138]
0x140c66069  mov     edi, 20h ; ' '
0x140c6606e  lea     rax, [rsp+1C0h+Object]
0x140c66073  mov     [rsp+1C0h+var_188], rax
0x140c66078  lea     rcx, [rbp+0C0h+var_118]
0x140c6607c  mov     dword ptr [rsp+1C0h+pszFormat], r12d
0x140c66081  xor     r9d, r9d
0x140c66084  mov     [rsp+1C0h+dwFlags], r12d
0x140c66089  lea     ebx, [rdi-2]
0x140c6608c  lea     r14d, [rdi-1Eh]
0x140c66090  call    PnpInitializeBootStartDriver
0x140c66095  mov     rsi, [rsp+1C0h+Object]
0x140c6609a  mov     [rsp+1C0h+Object], rsi
0x140c6609f  test    rsi, rsi
0x140c660a2  jnz     short loc_140C660AF
0x140c660a4  mov     cs:IopInitFailCode, ebx
0x140c660aa  jmp     loc_140C6697B
0x140c660af  xor     ecx, ecx
0x140c660b1  call    PpInitGetGroupOrderIndex
0x140c660b6  movzx   eax, ax
0x140c660b9  mov     r13d, 0FFFFh
0x140c660bf  mov     cs:IopGroupIndex, eax
0x140c660c5  mov     [rsp+1C0h+var_178], r13d
0x140c660ca  cmp     eax, r13d
0x140c660cd  jnz     short loc_140C660ED
0x140c660cf  xor     edx, edx
0x140c660d1  lea     ecx, [rdx+10h]
0x140c660d4  call    HeadlessKernelAddLogEntry
0x140c660d9  mov     eax, 0C0000225h
0x140c660de  mov     cs:IopInitFailCode, 1Fh
0x140c660e8  jmp     loc_140C6697B
0x140c660ed  mov     rdx, rax
0x140c660f0  mov     ecx, 100h
0x140c660f5  shl     rdx, 4
0x140c660f9  mov     r8d, 6E697050h
0x140c660ff  call    ExAllocatePool2
0x140c66104  mov     cs:IopGroupTable, rax
0x140c6610b  mov     r8, rax
0x140c6610e  test    rax, rax
0x140c66111  jnz     short loc_140C6612D
0x140c66113  xor     edx, edx
0x140c66115  lea     ecx, [rax+11h]
0x140c66118  call    HeadlessKernelAddLogEntry
0x140c6611d  mov     eax, 0C000009Ah
0x140c66122  mov     cs:IopInitFailCode, edi
0x140c66128  jmp     loc_140C6697B
0x140c6612d  mov     r9d, cs:IopGroupIndex
0x140c66134  mov     edx, r12d
0x140c66137  mov     r13d, 1
0x140c6613d  test    r9d, r9d
0x140c66140  jz      short loc_140C6615F
0x140c66142  movzx   ecx, dx
0x140c66145  add     dx, r13w
0x140c66149  shl     rcx, 4
0x140c6614d  add     rcx, r8
0x140c66150  movzx   eax, dx
0x140c66153  mov     [rcx+8], rcx
0x140c66157  mov     [rcx], rcx
0x140c6615a  cmp     eax, r9d
0x140c6615d  jb      short loc_140C66142
0x140c6615f  mov     rdx, r15
0x140c66162  mov     ecx, r14d
0x140c66165  call    PipInitializeDriverDependentDLLs
0x140c6616a  lea     rdx, aSystemReserved; "System Reserved"
0x140c66171  lea     rcx, [rbp+0C0h+DestinationString]; DestinationString
0x140c66175  call    RtlInitUnicodeString
0x140c6617a  lea     rdx, aBootBusExtende; "Boot Bus Extender"
0x140c66181  lea     rcx, [rbp+0C0h+String2]; DestinationString
0x140c66185  call    RtlInitUnicodeString
0x140c6618a  cmp     r12w, cs:PiInitGroupOrderTableCount
0x140c66192  mov     ebx, r12d
0x140c66195  mov     edi, r12d
0x140c66198  jnb     short loc_140C661F9
0x140c6619a  mov     esi, r14d
0x140c6619d  mov     rcx, cs:PiInitGroupOrderTable
0x140c661a4  lea     rdx, [rbp+0C0h+DestinationString]; String2
0x140c661a8  movzx   r14d, di
0x140c661ac  mov     r8b, r13b; CaseInSensitive
0x140c661af  shl     r14, 4
0x140c661b3  add     rcx, r14; String1
0x140c661b6  call    RtlCompareUnicodeString
0x140c661bb  test    eax, eax
0x140c661bd  jz      short loc_140C661DE
0x140c661bf  mov     rcx, cs:PiInitGroupOrderTable
0x140c661c6  lea     rdx, [rbp+0C0h+String2]; String2
0x140c661ca  add     rcx, r14; String1
0x140c661cd  mov     r8b, r13b; CaseInSensitive
0x140c661d0  call    RtlCompareUnicodeString
0x140c661d5  test    eax, eax
0x140c661d7  jnz     short loc_140C661E2
0x140c661d9  mov     word ptr [rsp+1C0h+var_178], di
0x140c661de  add     bx, r13w
0x140c661e2  cmp     bx, si
0x140c661e5  jnb     short loc_140C661F4
0x140c661e7  add     di, r13w
0x140c661eb  cmp     di, cs:PiInitGroupOrderTableCount
0x140c661f2  jb      short loc_140C6619D
0x140c661f4  mov     rsi, [rsp+1C0h+Object]
0x140c661f9  lea     r14, [r15+30h]
0x140c661fd  mov     rbx, [r14]
0x140c66200  cmp     rbx, r14
0x140c66203  jz      loc_140C662DB
0x140c66209  cmp     dword ptr [rbx+38h], 0
0x140c6620d  mov     r12, [rbx]
0x140c66210  jl      loc_140C662CC
0x140c66216  mov     edx, 30h ; '0'
0x140c6621b  mov     ecx, 100h
0x140c66220  mov     r8d, 6E697050h
0x140c66226  call    ExAllocatePool2
0x140c6622b  mov     rdi, rax
0x140c6622e  test    rax, rax
0x140c66231  jz      loc_140C662CC
0x140c66237  mov     [rax+8], rax
0x140c6623b  lea     r8, [rbx+20h]
0x140c6623f  mov     [rax], rax
0x140c66242  lea     rcx, [rsp+1C0h+Handle]
0x140c66247  xor     edx, edx
0x140c66249  mov     [rax+18h], rbx
0x140c6624d  mov     r9d, 20019h
0x140c66253  call    IopOpenRegistryKeyEx
0x140c66258  test    eax, eax
0x140c6625a  jns     short loc_140C66268
0x140c6625c  xor     edx, edx; Tag
0x140c6625e  mov     rcx, rdi; P
0x140c66261  call    ExFreePoolWithTag
0x140c66266  jmp     short loc_140C662CC
0x140c66268  mov     rax, [rsp+1C0h+Handle]
0x140c6626d  mov     [rdi+20h], rax
0x140c66271  mov     rcx, [rsp+1C0h+Handle]
0x140c66276  call    PpInitGetGroupOrderIndex
0x140c6627b  mov     rcx, [rsp+1C0h+Handle]; KeyHandle
0x140c66280  movzx   ebx, ax
0x140c66283  call    PipGetDriverTagPriority
0x140c66288  mov     r8d, ebx
0x140c6628b  mov     [rdi+2Ch], ax
0x140c6628f  shl     r8, 4
0x140c66293  add     r8, cs:IopGroupTable
0x140c6629a  mov     rcx, [r8]
0x140c6629d  jmp     short loc_140C662A8
0x140c6629f  cmp     [rcx+2Ch], ax
0x140c662a3  ja      short loc_140C662AD
0x140c662a5  mov     rcx, [rcx]
0x140c662a8  cmp     rcx, r8
0x140c662ab  jnz     short loc_140C6629F
0x140c662ad  mov     rax, [rcx+8]
0x140c662b1  mov     rcx, [rax]
0x140c662b4  cmp     [rcx+8], rax
0x140c662b8  jnz     loc_140C6699C
0x140c662be  mov     [rdi], rcx
0x140c662c1  mov     [rdi+8], rax
0x140c662c5  mov     [rcx+8], rdi
0x140c662c9  mov     [rax], rdi
0x140c662cc  mov     rbx, r12
0x140c662cf  cmp     r12, r14
0x140c662d2  jnz     loc_140C66209
0x140c662d8  xor     r12d, r12d
0x140c662db  mov     ecx, r13d
0x140c662de  call    PnpNotifyEarlyLaunchStatusUpdate
0x140c662e3  mov     r14d, r12d
0x140c662e6  movzx   eax, r14w
0x140c662ea  cmp     eax, cs:IopGroupIndex
0x140c662f0  jnb     loc_140C664F5
0x140c662f6  mov     rax, cs:IopGroupTable
0x140c662fd  movzx   r12d, r14w
0x140c66301  shl     r12, 4
0x140c66305  xor     edi, edi
0x140c66307  mov     rbx, [r12+rax]
0x140c6630b  mov     rcx, cs:IopGroupTable
0x140c66312  add     rcx, r12
0x140c66315  cmp     rbx, rcx
0x140c66318  jz      loc_140C664A8
0x140c6631e  mov     rax, [rbx+20h]
0x140c66322  lea     rdx, [rbp+0C0h+var_138]; Destination
0x140c66326  mov     [rsp+1C0h+Handle], rax
0x140c6632b  mov     r13, [rbx+18h]
0x140c6632f  mov     rax, [r13+30h]
0x140c66333  mov     byte ptr [rbx+2Fh], 1
0x140c66337  mov     rcx, [rsp+1C0h+Handle]; KeyHandle
0x140c6633c  mov     qword ptr [rbp+0C0h+DestinationString.Length], rax
0x140c66340  call    IopGetDriverNameFromKeyNode
0x140c66345  test    eax, eax
0x140c66347  jns     short loc_140C66358
0x140c66349  mov     r13d, 1
0x140c6634f  mov     [rbx+2Eh], r13b
0x140c66353  jmp     loc_140C66450
0x140c66358  mov     rcx, [rsp+1C0h+Handle]; KeyHandle
0x140c6635d  lea     r9, [rsp+1C0h+P]
0x140c66362  xor     r8d, r8d
0x140c66365  lea     rdx, aGroup_0; "Group"
0x140c6636c  call    IopGetRegistryValue
0x140c66371  test    eax, eax
0x140c66373  js      short loc_140C663B0
0x140c66375  mov     rsi, [rsp+1C0h+P]
0x140c6637a  cmp     [rsi+0Ch], edi
0x140c6637d  jz      short loc_140C663A6
0x140c6637f  movzx   eax, word ptr [rsi+0Ch]
0x140c66383  lea     rcx, [rbp+0C0h+String1]; String1
0x140c66387  mov     [rbp+0C0h+String1.Length], ax
0x140c6638b  mov     edx, 1
0x140c66390  mov     [rbp+0C0h+String1.MaximumLength], ax
0x140c66394  mov     eax, [rsi+8]
0x140c66397  add     rax, rsi
0x140c6639a  mov     [rbp+0C0h+String1.Buffer], rax
  ... truncated ...
```
