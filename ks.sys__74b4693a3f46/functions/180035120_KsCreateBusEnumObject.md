# KsCreateBusEnumObject

- ea: `0x180035120`
- end: `0x180035788`
- name: `KsCreateBusEnumObject`
- size: `1640`
- prototype: `NTSTATUS __stdcall(PWSTR BusIdentifier, PDEVICE_OBJECT BusDeviceObject, PDEVICE_OBJECT PhysicalDeviceObject, PDEVICE_OBJECT PnpDeviceObject, const GUID *const InterfaceGuid, PWSTR ServiceRelativePath)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callees

- `0x18000ae68`
- `0x18000b11c`
- `0x18000b7bc`
- `0x18000c630`
- `0x180010de4`
- `0x180019fc0`
- `0x180035120`
- `0x18003665c`
- `0x1800631ec`
- `0x180066028`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180035413`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180035439`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800356b6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180035413`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180035439`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800356b6`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x180035360`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x180035360`
- `ntoskrnl!IoAllocateWorkItem` at `0x180035646`
- `ntoskrnl!IoAllocateWorkItem` at `0x180035662`
- `ntoskrnl!IoAllocateWorkItem` at `0x180035646`
- `ntoskrnl!IoAllocateWorkItem` at `0x180035662`
- `ntoskrnl!KeInitializeDpc` at `0x1800354d9`
- `ntoskrnl!KeInitializeDpc` at `0x18003556b`
- `ntoskrnl!KeInitializeDpc` at `0x1800354d9`
- `ntoskrnl!KeInitializeDpc` at `0x18003556b`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1800353c4`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x18003542a`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1800356a6`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1800353c4`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x18003542a`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1800356a6`
- `ntoskrnl!IoDetachDevice` at `0x1800356ec`
- `ntoskrnl!IoDetachDevice` at `0x1800356ec`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18003560d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18003560d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800355fe`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800355fe`
- `ntoskrnl!ExInitializeRundownProtection` at `0x18003550d`
- `ntoskrnl!ExInitializeRundownProtection` at `0x180035590`
- `ntoskrnl!ExInitializeRundownProtection` at `0x18003550d`
- `ntoskrnl!ExInitializeRundownProtection` at `0x180035590`
- `ntoskrnl!KeInitializeTimer` at `0x1800354bc`
- `ntoskrnl!KeInitializeTimer` at `0x18003554e`
- `ntoskrnl!KeInitializeTimer` at `0x1800354bc`
- `ntoskrnl!KeInitializeTimer` at `0x18003554e`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1800355b5`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1800355b5`
- `ntoskrnl!IoFreeWorkItem` at `0x180035704`
- `ntoskrnl!IoFreeWorkItem` at `0x180035723`
- `ntoskrnl!IoFreeWorkItem` at `0x180035704`
- `ntoskrnl!IoFreeWorkItem` at `0x180035723`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180035626`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180035626`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180035632`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180035632`
- `ntoskrnl!KeInitializeEvent` at `0x18003547e`
- `ntoskrnl!KeInitializeEvent` at `0x1800354a9`
- `ntoskrnl!KeInitializeEvent` at `0x18003553b`
- `ntoskrnl!KeInitializeEvent` at `0x18003547e`
- `ntoskrnl!KeInitializeEvent` at `0x1800354a9`
- `ntoskrnl!KeInitializeEvent` at `0x18003553b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800352fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003544e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800356cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003573b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003575a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800352fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003544e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800356cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003573b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003575a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800351e2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180035279`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800351e2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180035279`
- `HAL!KeQueryPerformanceCounter` at `0x1800355df`
- `HAL!KeQueryPerformanceCounter` at `0x1800355df`

## string_xrefs

- `0x1800352ba`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Services`

## pseudocode

```c
NTSTATUS __stdcall KsCreateBusEnumObject(
        PWSTR BusIdentifier,
        PDEVICE_OBJECT BusDeviceObject,
        PDEVICE_OBJECT PhysicalDeviceObject,
        PDEVICE_OBJECT PnpDeviceObject,
        const GUID *const InterfaceGuid,
        PWSTR ServiceRelativePath)
{
  __int64 *v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  unsigned int v13; // ecx
  __int64 v14; // r14
  _QWORD *PoolWithTag; // rdi
  __int64 v17; // rbx
  unsigned __int16 v18; // bx
  wchar_t *v19; // rax
  wchar_t *v20; // r14
  HRESULT v21; // eax
  NTSTATUS v22; // esi
  int v23; // edx
  int v24; // r8d
  NTSTATUS v25; // eax
  int v26; // edx
  PDEVICE_OBJECT v27; // rax
  PIO_WORKITEM WorkItem; // rax
  PIO_WORKITEM v29; // rax
  struct _IO_WORKITEM *v30; // rcx
  struct _IO_WORKITEM *v31; // rcx
  __int64 v32; // [rsp+28h] [rbp-50h]

  v9 = WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      1,
      10,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
  }
  if ( !BusIdentifier || !BusDeviceObject || !PhysicalDeviceObject )
    return -1073741811;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( BusIdentifier[v11] );
  v12 = 2LL * (unsigned int)v11;
  if ( v12 <= 0xFFFFFFFF )
  {
    v13 = v12 + 768;
    if ( v13 >= 0x300 )
    {
      v14 = v13;
      PoolWithTag = ExAllocatePoolWithTag(NonPagedPoolNx, v13, 0x64665753u);
      if ( !PoolWithTag )
        return -1073741670;
      *(_QWORD *)BusDeviceObject->DeviceExtension = PoolWithTag;
      memset(PoolWithTag, 0, 0x300u);
      if ( StringCbCopyW((STRSAFE_LPWSTR)PoolWithTag + 380, v14 - 766, BusIdentifier) < 0 )
        goto LABEL_62;
      if ( ServiceRelativePath )
      {
        v17 = -1;
        do
          ++v17;
        while ( ServiceRelativePath[v17] );
        v18 = BusDeviceObject->DriverObject->DriverExtension->ServiceKeyName.MaximumLength + 106 + 2 * v17;
      }
      else
      {
        v18 = BusDeviceObject->DriverObject->DriverExtension->ServiceKeyName.MaximumLength + 106;
      }
      v19 = (wchar_t *)ExAllocatePoolWithTag((POOL_TYPE)1025, v18, 0x72645753u);
      v20 = v19;
      if ( !ExPoolZeroingNativelySupported && v19 )
        memset(v19, 0, v18);
      PoolWithTag[43] = v20;
      if ( !v20 )
      {
LABEL_62:
        v22 = -1073741670;
        goto LABEL_63;
      }
      *((_WORD *)PoolWithTag + 169) = v18;
      if ( ServiceRelativePath )
        v21 = StringCbPrintfW(
                v20,
                v18,
                L"%s\\%s\\%s",
                L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Services",
                BusDeviceObject->DriverObject->DriverExtension->ServiceKeyName.Buffer,
                ServiceRelativePath);
      else
        v21 = StringCbPrintfW(
                v20,
                v18,
                L"%s\\%s",
                L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Services",
                BusDeviceObject->DriverObject->DriverExtension->ServiceKeyName.Buffer);
      if ( v21 < 0 )
      {
        ExFreePoolWithTag((PVOID)PoolWithTag[43], 0);
        v22 = -1073741823;
LABEL_63:
        ExFreePoolWithTag(PoolWithTag, 0);
        return v22;
      }
      do
        ++v10;
      while ( *(_WORD *)(PoolWithTag[43] + 2 * v10) );
      *((_WORD *)PoolWithTag + 168) = 2 * v10;
      if ( InterfaceGuid )
      {
        v22 = IoRegisterDeviceInterface(PhysicalDeviceObject, InterfaceGuid, 0, (PUNICODE_STRING)PoolWithTag + 5);
        if ( v22 < 0 )
        {
LABEL_39:
          if ( PoolWithTag[11] )
          {
            IoSetDeviceInterfaceState((PUNICODE_STRING)PoolWithTag + 5, 0);
            RtlFreeUnicodeString((PUNICODE_STRING)PoolWithTag + 5);
          }
          ExFreePoolWithTag((PVOID)PoolWithTag[43], 0);
          goto LABEL_63;
        }
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_S(
            WPP_GLOBAL_Control->DeviceExtension,
            v23,
            v24,
            11,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            PoolWithTag[11]);
        v25 = IoSetDeviceInterfaceState((PUNICODE_STRING)PoolWithTag + 5, 1u);
        v22 = v25;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LODWORD(v32) = v25;
          LOBYTE(v26) = 5;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v26,
            1,
            12,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            v32);
        }
        if ( v22 < 0 )
        {
          RtlFreeUnicodeString((PUNICODE_STRING)PoolWithTag + 5);
          goto LABEL_39;
        }
      }
      *((_DWORD *)PoolWithTag + 6) = 1;
      PoolWithTag[4] = 0;
      *((_DWORD *)PoolWithTag + 10) = 0;
      KeInitializeEvent((PRKEVENT)PoolWithTag + 2, SynchronizationEvent, 0);
      *((_DWORD *)PoolWithTag + 30) = 1;
      PoolWithTag[16] = 0;
      *((_DWORD *)PoolWithTag + 34) = 0;
      KeInitializeEvent((PRKEVENT)PoolWithTag + 6, SynchronizationEvent, 0);
      KeInitializeTimer((PKTIMER)PoolWithTag + 3);
      KeInitializeDpc((PRKDPC)PoolWithTag + 4, SweeperDeferredRoutine, PoolWithTag);
      PoolWithTag[14] = BusDeviceObject;
      PoolWithTag[1] = PoolWithTag;
      *PoolWithTag = PoolWithTag;
      *((_DWORD *)PoolWithTag + 4) = 1;
      PoolWithTag[12] = PhysicalDeviceObject;
      *((_DWORD *)PoolWithTag + 44) = 0;
      *((_DWORD *)PoolWithTag + 80) = 0;
      ExInitializeRundownProtection((PEX_RUNDOWN_REF)PoolWithTag + 23);
      *((_DWORD *)PoolWithTag + 124) = 1;
      PoolWithTag[63] = 0;
      *((_DWORD *)PoolWithTag + 128) = 0;
      KeInitializeEvent((PRKEVENT)(PoolWithTag + 65), SynchronizationEvent, 0);
      KeInitializeTimer((PKTIMER)(PoolWithTag + 71));
      KeInitializeDpc((PRKDPC)(PoolWithTag + 79), RescanDeferredRoutine, PoolWithTag);
      PoolWithTag[69] = 0;
      *((_DWORD *)PoolWithTag + 174) = 0;
      ExInitializeRundownProtection((PEX_RUNDOWN_REF)PoolWithTag + 70);
      if ( PnpDeviceObject )
      {
        PoolWithTag[13] = PnpDeviceObject;
      }
      else
      {
        v27 = IoAttachDeviceToDeviceStack(BusDeviceObject, PhysicalDeviceObject);
        PoolWithTag[13] = v27;
        if ( !v27 )
        {
          v22 = -1073741130;
          goto LABEL_53;
        }
        *((_DWORD *)PoolWithTag + 88) = 1;
      }
      KeQueryPerformanceCounter((PLARGE_INTEGER)PoolWithTag + 93);
      PoolWithTag[94] = 1200LL * PoolWithTag[93];
      BusDeviceObject->Flags |= 0x2000u;
      KeEnterCriticalRegion();
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(PoolWithTag + 3));
      v22 = ScanBus(BusDeviceObject);
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(PoolWithTag + 3));
      KeLeaveCriticalRegion();
      if ( v22 >= 0 )
      {
        WorkItem = IoAllocateWorkItem((PDEVICE_OBJECT)PoolWithTag[14]);
        PoolWithTag[41] = WorkItem;
        if ( WorkItem && (v29 = IoAllocateWorkItem((PDEVICE_OBJECT)PoolWithTag[14]), (PoolWithTag[88] = v29) != 0) )
        {
          v22 = RescanInitialize((__int64)PoolWithTag);
          if ( v22 >= 0 )
            return v22;
        }
        else
        {
          v22 = -1073741670;
        }
      }
LABEL_53:
      if ( PoolWithTag[11] )
      {
        IoSetDeviceInterfaceState((PUNICODE_STRING)PoolWithTag + 5, 0);
        RtlFreeUnicodeString((PUNICODE_STRING)PoolWithTag + 5);
      }
      ExFreePoolWithTag((PVOID)PoolWithTag[43], 0);
      RescanUninitialize((__int64)PoolWithTag);
      if ( *((_DWORD *)PoolWithTag + 88) )
        IoDetachDevice((PDEVICE_OBJECT)PoolWithTag[13]);
      v30 = (struct _IO_WORKITEM *)PoolWithTag[41];
      if ( v30 )
      {
        IoFreeWorkItem(v30);
        PoolWithTag[41] = 0;
      }
      v31 = (struct _IO_WORKITEM *)PoolWithTag[88];
      if ( v31 )
      {
        IoFreeWorkItem(v31);
        PoolWithTag[88] = 0;
      }
      ExFreePoolWithTag(PoolWithTag, 0);
      *(_QWORD *)BusDeviceObject->DeviceExtension = 0;
      return v22;
    }
  }
  return -1073741675;
}

```

## disassembly

```asm
0x180035120  mov     [rsp+arg_18], r9
0x180035125  push    rbx
0x180035126  push    rbp
0x180035127  push    rsi
0x180035128  push    rdi
0x180035129  push    r12
0x18003512b  push    r13
0x18003512d  push    r14
0x18003512f  push    r15
0x180035131  sub     rsp, 38h
0x180035135  mov     r13, r8
0x180035138  mov     rbp, rdx
0x18003513b  mov     rbx, rcx
0x18003513e  lea     rax, WPP_RECORDER_INITIALIZED
0x180035145  xor     r15d, r15d
0x180035148  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003514f  lea     rdx, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180035156  jz      short loc_18003517E
0x180035158  mov     rcx, cs:WPP_GLOBAL_Control
0x18003515f  cmp     [rcx+48h], r15w
0x180035164  jz      short loc_18003517E
0x180035166  mov     rcx, [rcx+40h]
0x18003516a  lea     r9d, [r15+0Ah]
0x18003516e  mov     [rsp+78h+var_58], rdx
0x180035173  lea     r8d, [r15+1]
0x180035177  mov     dl, 5
0x180035179  call    WPP_RECORDER_SF_
0x18003517e  test    rbx, rbx
0x180035181  jz      loc_180035771
0x180035187  test    rbp, rbp
0x18003518a  jz      loc_180035771
0x180035190  test    r13, r13
0x180035193  jz      loc_180035771
0x180035199  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003519d  mov     rax, rsi
0x1800351a0  inc     rax
0x1800351a3  cmp     [rbx+rax*2], r15w
0x1800351a8  jnz     short loc_1800351A0
0x1800351aa  mov     ecx, eax
0x1800351ac  mov     eax, 0FFFFFFFFh
0x1800351b1  add     rcx, rcx
0x1800351b4  cmp     rcx, rax
0x1800351b7  ja      loc_18003576A
0x1800351bd  add     ecx, 300h
0x1800351c3  mov     r12d, 300h
0x1800351c9  cmp     ecx, r12d
0x1800351cc  jb      loc_18003576A
0x1800351d2  mov     r14d, ecx
0x1800351d5  mov     r8d, 64665753h; Tag
0x1800351db  mov     edx, ecx; NumberOfBytes
0x1800351dd  mov     ecx, 200h; PoolType
0x1800351e2  call    cs:__imp_ExAllocatePoolWithTag
0x1800351e9  nop     dword ptr [rax+rax+00h]
0x1800351ee  mov     rdi, rax
0x1800351f1  test    rax, rax
0x1800351f4  jnz     short loc_180035200
0x1800351f6  mov     eax, 0C000009Ah
0x1800351fb  jmp     loc_180035776
0x180035200  mov     rax, [rbp+40h]
0x180035204  mov     r8, r12; Size
0x180035207  xor     edx, edx; Val
0x180035209  mov     rcx, rdi; void *
0x18003520c  mov     [rax], rdi
0x18003520f  call    memset
0x180035214  lea     rdx, [r14-2FEh]; cbDest
0x18003521b  mov     r8, rbx; pszSrc
0x18003521e  lea     rcx, [rdi+2F8h]; pszDest
0x180035225  call    StringCbCopyW
0x18003522a  test    eax, eax
0x18003522c  js      loc_180035750
0x180035232  mov     rax, [rbp+8]
0x180035236  mov     r12, [rsp+78h+ServiceRelativePath]
0x18003523e  mov     rcx, [rax+30h]
0x180035242  movzx   eax, word ptr [rcx+1Ah]
0x180035246  add     ax, 6Ah ; 'j'
0x18003524a  test    r12, r12
0x18003524d  jz      short loc_180035264
0x18003524f  mov     rbx, rsi
0x180035252  inc     rbx
0x180035255  cmp     [r12+rbx*2], r15w
0x18003525a  jnz     short loc_180035252
0x18003525c  add     bx, bx
0x18003525f  add     bx, ax
0x180035262  jmp     short loc_180035267
0x180035264  movzx   ebx, ax
0x180035267  movzx   r15d, bx
0x18003526b  mov     r8d, 72645753h; Tag
0x180035271  mov     edx, r15d; NumberOfBytes
0x180035274  mov     ecx, 401h; PoolType
0x180035279  call    cs:__imp_ExAllocatePoolWithTag
0x180035280  nop     dword ptr [rax+rax+00h]
0x180035285  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18003528c  mov     r14, rax
0x18003528f  jnz     short loc_1800352A3
0x180035291  test    rax, rax
0x180035294  jz      short loc_1800352A3
0x180035296  mov     r8d, r15d; Size
0x180035299  xor     edx, edx; Val
0x18003529b  mov     rcx, rax; void *
0x18003529e  call    memset
0x1800352a3  mov     [rdi+158h], r14
0x1800352aa  test    r14, r14
0x1800352ad  jz      loc_180035750
0x1800352b3  mov     [rdi+152h], bx
0x1800352ba  lea     r9, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1800352c1  mov     rax, [rbp+8]
0x1800352c5  mov     rdx, r15; cbDest
0x1800352c8  mov     rcx, r14; pszDest
0x1800352cb  mov     rax, [rax+30h]
0x1800352cf  mov     rax, [rax+20h]
0x1800352d3  test    r12, r12
0x1800352d6  jz      short loc_180035314
0x1800352d8  mov     [rsp+78h+var_50], r12
0x1800352dd  lea     r8, aSSS; "%s\\%s\\%s"
0x1800352e4  mov     [rsp+78h+var_58], rax
0x1800352e9  call    StringCbPrintfW
0x1800352ee  xor     r15d, r15d
0x1800352f1  test    eax, eax
0x1800352f3  jns     short loc_180035327
0x1800352f5  mov     rcx, [rdi+158h]; P
0x1800352fc  xor     edx, edx; Tag
0x1800352fe  call    cs:__imp_ExFreePoolWithTag
0x180035305  nop     dword ptr [rax+rax+00h]
0x18003530a  mov     esi, 0C0000001h
0x18003530f  jmp     loc_180035755
0x180035314  lea     r8, aSS; "%s\\%s"
0x18003531b  mov     [rsp+78h+var_58], rax
0x180035320  call    StringCbPrintfW
0x180035325  jmp     short loc_1800352EE
0x180035327  mov     rax, [rdi+158h]
0x18003532e  inc     rsi
0x180035331  cmp     [rax+rsi*2], r15w
0x180035336  jnz     short loc_18003532E
0x180035338  mov     rdx, [rsp+78h+InterfaceGuid]; InterfaceClassGuid
0x180035340  add     si, si
0x180035343  mov     [rdi+150h], si
0x18003534a  test    rdx, rdx
0x18003534d  jz      loc_18003545F
0x180035353  lea     rbx, [rdi+50h]
0x180035357  xor     r8d, r8d; ReferenceString
0x18003535a  mov     r9, rbx; SymbolicLinkName
0x18003535d  mov     rcx, r13; PhysicalDeviceObject
0x180035360  call    cs:__imp_IoRegisterDeviceInterface
0x180035367  nop     dword ptr [rax+rax+00h]
0x18003536c  mov     esi, eax
0x18003536e  test    eax, eax
0x180035370  js      loc_18003541F
0x180035376  lea     r14, WPP_RECORDER_INITIALIZED
0x18003537d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180035384  jz      short loc_1800353B8
0x180035386  mov     rcx, cs:WPP_GLOBAL_Control
0x18003538d  cmp     [rcx+48h], r15w
0x180035392  jz      short loc_1800353B8
0x180035394  mov     rax, [rdi+58h]
0x180035398  mov     r9d, 0Bh
0x18003539e  mov     rcx, [rcx+40h]
0x1800353a2  mov     [rsp+78h+var_50], rax
0x1800353a7  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x1800353ae  mov     [rsp+78h+var_58], rax
0x1800353b3  call    WPP_RECORDER_SF_S
0x1800353b8  mov     r12d, 1
0x1800353be  mov     rcx, rbx; SymbolicLinkName
0x1800353c1  mov     dl, r12b; Enable
0x1800353c4  call    cs:__imp_IoSetDeviceInterfaceState
0x1800353cb  nop     dword ptr [rax+rax+00h]
0x1800353d0  mov     esi, eax
0x1800353d2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800353d9  jz      short loc_18003540C
0x1800353db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800353e2  cmp     [rcx+48h], r15w
0x1800353e7  jz      short loc_18003540C
0x1800353e9  mov     rcx, [rcx+40h]
0x1800353ed  lea     r9d, [r12+0Bh]
0x1800353f2  mov     dword ptr [rsp+78h+var_50], eax
0x1800353f6  mov     r8d, r12d
0x1800353f9  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180035400  mov     dl, 5
0x180035402  mov     [rsp+78h+var_58], rax
0x180035407  call    WPP_RECORDER_SF_D
0x18003540c  test    esi, esi
0x18003540e  jns     short loc_180035465
0x180035410  mov     rcx, rbx; UnicodeString
0x180035413  call    cs:__imp_RtlFreeUnicodeString
0x18003541a  nop     dword ptr [rax+rax+00h]
0x18003541f  cmp     [rdi+58h], r15
0x180035423  jz      short loc_180035445
0x180035425  xor     edx, edx; Enable
0x180035427  mov     rcx, rbx; SymbolicLinkName
0x18003542a  call    cs:__imp_IoSetDeviceInterfaceState
0x180035431  nop     dword ptr [rax+rax+00h]
0x180035436  mov     rcx, rbx; UnicodeString
0x180035439  call    cs:__imp_RtlFreeUnicodeString
0x180035440  nop     dword ptr [rax+rax+00h]
0x180035445  mov     rcx, [rdi+158h]; P
0x18003544c  xor     edx, edx; Tag
0x18003544e  call    cs:__imp_ExFreePoolWithTag
0x180035455  nop     dword ptr [rax+rax+00h]
0x18003545a  jmp     loc_180035755
0x18003545f  mov     r12d, 1
0x180035465  lea     r14, [rdi+18h]
0x180035469  xor     r8d, r8d; State
0x18003546c  lea     rcx, [r14+18h]; Event
0x180035470  mov     [r14], r12d
0x180035473  mov     edx, r12d; Type
0x180035476  mov     [r14+8], r15
0x18003547a  mov     [r14+10h], r15d
0x18003547e  call    cs:__imp_KeInitializeEvent
0x180035485  nop     dword ptr [rax+rax+00h]
0x18003548a  lea     rcx, [rdi+90h]; Event
0x180035491  mov     [rdi+78h], r12d
0x180035495  xor     r8d, r8d; State
0x180035498  mov     [rdi+80h], r15
0x18003549f  mov     edx, r12d; Type
0x1800354a2  mov     [rdi+88h], r15d
0x1800354a9  call    cs:__imp_KeInitializeEvent
0x1800354b0  nop     dword ptr [rax+rax+00h]
0x1800354b5  lea     rcx, [rdi+0C0h]; Timer
0x1800354bc  call    cs:__imp_KeInitializeTimer
0x1800354c3  nop     dword ptr [rax+rax+00h]
0x1800354c8  lea     rcx, [rdi+100h]; Dpc
0x1800354cf  mov     r8, rdi; DeferredContext
0x1800354d2  lea     rdx, SweeperDeferredRoutine; DeferredRoutine
0x1800354d9  call    cs:__imp_KeInitializeDpc
0x1800354e0  nop     dword ptr [rax+rax+00h]
0x1800354e5  mov     [rdi+70h], rbp
0x1800354e9  lea     rcx, [rdi+0B8h]; RunRef
0x1800354f0  mov     [rdi+8], rdi
0x1800354f4  mov     [rdi], rdi
0x1800354f7  mov     [rdi+10h], r12d
0x1800354fb  mov     [rdi+60h], r13
0x1800354ff  mov     [rdi+0B0h], r15d
0x180035506  mov     [rdi+140h], r15d
0x18003550d  call    cs:__imp_ExInitializeRundownProtection
0x180035514  nop     dword ptr [rax+rax+00h]
0x180035519  lea     rcx, [rdi+208h]; Event
0x180035520  mov     [rdi+1F0h], r12d
0x180035527  xor     r8d, r8d; State
0x18003552a  mov     [rdi+1F8h], r15
0x180035531  mov     edx, r12d; Type
0x180035534  mov     [rdi+200h], r15d
0x18003553b  call    cs:__imp_KeInitializeEvent
0x180035542  nop     dword ptr [rax+rax+00h]
0x180035547  lea     rcx, [rdi+238h]; Timer
0x18003554e  call    cs:__imp_KeInitializeTimer
0x180035555  nop     dword ptr [rax+rax+00h]
0x18003555a  lea     rcx, [rdi+278h]; Dpc
0x180035561  mov     r8, rdi; DeferredContext
0x180035564  lea     rdx, RescanDeferredRoutine; DeferredRoutine
0x18003556b  call    cs:__imp_KeInitializeDpc
0x180035572  nop     dword ptr [rax+rax+00h]
0x180035577  mov     qword ptr [rdi+228h], 0
0x180035582  lea     rcx, [rdi+230h]; RunRef
0x180035589  mov     [rdi+2B8h], r15d
0x180035590  call    cs:__imp_ExInitializeRundownProtection
0x180035597  nop     dword ptr [rax+rax+00h]
0x18003559c  mov     rax, [rsp+78h+arg_18]
0x1800355a4  test    rax, rax
0x1800355a7  jz      short loc_1800355AF
0x1800355a9  mov     [rdi+68h], rax
0x1800355ad  jmp     short loc_1800355D5
0x1800355af  mov     rdx, r13; TargetDevice
0x1800355b2  mov     rcx, rbp; SourceDevice
0x1800355b5  call    cs:__imp_IoAttachDeviceToDeviceStack
0x1800355bc  nop     dword ptr [rax+rax+00h]
0x1800355c1  mov     [rdi+68h], rax
0x1800355c5  test    rax, rax
0x1800355c8  jz      loc_180035695
0x1800355ce  mov     [rdi+160h], r12d
0x1800355d5  lea     rbx, [rdi+2E8h]
0x1800355dc  mov     rcx, rbx; PerformanceFrequency
0x1800355df  call    cs:__imp_KeQueryPerformanceCounter
0x1800355e6  nop     dword ptr [rax+rax+00h]
0x1800355eb  imul    rax, [rbx], 4B0h
0x1800355f2  mov     [rdi+2F0h], rax
0x1800355f9  bts     dword ptr [rbp+30h], 0Dh
0x1800355fe  call    cs:__imp_KeEnterCriticalRegion
0x180035605  nop     dword ptr [rax+rax+00h]
0x18003560a  mov     rcx, r14; FastMutex
0x18003560d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x180035614  nop     dword ptr [rax+rax+00h]
0x180035619  mov     rcx, rbp
0x18003561c  call    ScanBus
0x180035621  mov     rcx, r14; FastMutex
0x180035624  mov     esi, eax
0x180035626  call    cs:__imp_ExReleaseFastMutexUnsafe
0x18003562d  nop     dword ptr [rax+rax+00h]
0x180035632  call    cs:__imp_KeLeaveCriticalRegion
0x180035639  nop     dword ptr [rax+rax+00h]
0x18003563e  test    esi, esi
0x180035640  js      short loc_18003569A
0x180035642  mov     rcx, [rdi+70h]; DeviceObject
0x180035646  call    cs:__imp_IoAllocateWorkItem
0x18003564d  nop     dword ptr [rax+rax+00h]
0x180035652  mov     [rdi+148h], rax
0x180035659  test    rax, rax
0x18003565c  jz      short loc_18003567A
0x18003565e  mov     rcx, [rdi+70h]; DeviceObject
0x180035662  call    cs:__imp_IoAllocateWorkItem
0x180035669  nop     dword ptr [rax+rax+00h]
0x18003566e  mov     [rdi+2C0h], rax
  ... truncated ...
```
