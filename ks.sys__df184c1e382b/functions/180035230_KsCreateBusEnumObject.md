# KsCreateBusEnumObject

- ea: `0x180035230`
- end: `0x180035898`
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
- `0x180011684`
- `0x18001a000`
- `0x180035230`
- `0x18003676c`
- `0x18006338c`
- `0x180066998`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180035523`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180035549`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800357c6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180035523`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180035549`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800357c6`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x180035470`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x180035470`
- `ntoskrnl!IoAllocateWorkItem` at `0x180035756`
- `ntoskrnl!IoAllocateWorkItem` at `0x180035772`
- `ntoskrnl!IoAllocateWorkItem` at `0x180035756`
- `ntoskrnl!IoAllocateWorkItem` at `0x180035772`
- `ntoskrnl!KeInitializeDpc` at `0x1800355e9`
- `ntoskrnl!KeInitializeDpc` at `0x18003567b`
- `ntoskrnl!KeInitializeDpc` at `0x1800355e9`
- `ntoskrnl!KeInitializeDpc` at `0x18003567b`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1800354d4`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x18003553a`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1800357b6`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1800354d4`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x18003553a`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x1800357b6`
- `ntoskrnl!IoDetachDevice` at `0x1800357fc`
- `ntoskrnl!IoDetachDevice` at `0x1800357fc`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18003571d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x18003571d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18003570e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18003570e`
- `ntoskrnl!ExInitializeRundownProtection` at `0x18003561d`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1800356a0`
- `ntoskrnl!ExInitializeRundownProtection` at `0x18003561d`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1800356a0`
- `ntoskrnl!KeInitializeTimer` at `0x1800355cc`
- `ntoskrnl!KeInitializeTimer` at `0x18003565e`
- `ntoskrnl!KeInitializeTimer` at `0x1800355cc`
- `ntoskrnl!KeInitializeTimer` at `0x18003565e`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1800356c5`
- `ntoskrnl!IoAttachDeviceToDeviceStack` at `0x1800356c5`
- `ntoskrnl!IoFreeWorkItem` at `0x180035814`
- `ntoskrnl!IoFreeWorkItem` at `0x180035833`
- `ntoskrnl!IoFreeWorkItem` at `0x180035814`
- `ntoskrnl!IoFreeWorkItem` at `0x180035833`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180035736`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180035736`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180035742`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180035742`
- `ntoskrnl!KeInitializeEvent` at `0x18003558e`
- `ntoskrnl!KeInitializeEvent` at `0x1800355b9`
- `ntoskrnl!KeInitializeEvent` at `0x18003564b`
- `ntoskrnl!KeInitializeEvent` at `0x18003558e`
- `ntoskrnl!KeInitializeEvent` at `0x1800355b9`
- `ntoskrnl!KeInitializeEvent` at `0x18003564b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003540e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003555e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800357db`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003584b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003586a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003540e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003555e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800357db`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003584b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003586a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800352f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180035389`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800352f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180035389`
- `HAL!KeQueryPerformanceCounter` at `0x1800356ef`
- `HAL!KeQueryPerformanceCounter` at `0x1800356ef`

## string_xrefs

- `0x1800353ca`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Services`

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
  int v22; // esi
  int v23; // edx
  int v24; // r8d
  NTSTATUS v25; // eax
  int v26; // edx
  PDEVICE_OBJECT v27; // rax
  PIO_WORKITEM WorkItem; // rax
  PIO_WORKITEM v29; // rax
  struct _IO_WORKITEM *v30; // rcx
  struct _IO_WORKITEM *v31; // rcx

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
          LOBYTE(v26) = 5;
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            v26,
            1,
            12,
            (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
            v25);
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
      KeInitializeDpc((PRKDPC)PoolWithTag + 4, (PKDEFERRED_ROUTINE)SweeperDeferredRoutine, PoolWithTag);
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
      KeInitializeDpc((PRKDPC)(PoolWithTag + 79), (PKDEFERRED_ROUTINE)RescanDeferredRoutine, PoolWithTag);
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
          v22 = RescanInitialize(PoolWithTag);
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
      RescanUninitialize(PoolWithTag);
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
0x180035230  mov     [rsp+arg_18], r9
0x180035235  push    rbx
0x180035236  push    rbp
0x180035237  push    rsi
0x180035238  push    rdi
0x180035239  push    r12
0x18003523b  push    r13
0x18003523d  push    r14
0x18003523f  push    r15
0x180035241  sub     rsp, 38h
0x180035245  mov     r13, r8
0x180035248  mov     rbp, rdx
0x18003524b  mov     rbx, rcx
0x18003524e  lea     rax, WPP_RECORDER_INITIALIZED
0x180035255  xor     r15d, r15d
0x180035258  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003525f  lea     rdx, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180035266  jz      short loc_18003528E
0x180035268  mov     rcx, cs:WPP_GLOBAL_Control
0x18003526f  cmp     [rcx+48h], r15w
0x180035274  jz      short loc_18003528E
0x180035276  mov     rcx, [rcx+40h]
0x18003527a  lea     r9d, [r15+0Ah]
0x18003527e  mov     [rsp+78h+var_58], rdx
0x180035283  lea     r8d, [r15+1]
0x180035287  mov     dl, 5
0x180035289  call    WPP_RECORDER_SF_
0x18003528e  test    rbx, rbx
0x180035291  jz      loc_180035881
0x180035297  test    rbp, rbp
0x18003529a  jz      loc_180035881
0x1800352a0  test    r13, r13
0x1800352a3  jz      loc_180035881
0x1800352a9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800352ad  mov     rax, rsi
0x1800352b0  inc     rax
0x1800352b3  cmp     [rbx+rax*2], r15w
0x1800352b8  jnz     short loc_1800352B0
0x1800352ba  mov     ecx, eax
0x1800352bc  mov     eax, 0FFFFFFFFh
0x1800352c1  add     rcx, rcx
0x1800352c4  cmp     rcx, rax
0x1800352c7  ja      loc_18003587A
0x1800352cd  add     ecx, 300h
0x1800352d3  mov     r12d, 300h
0x1800352d9  cmp     ecx, r12d
0x1800352dc  jb      loc_18003587A
0x1800352e2  mov     r14d, ecx
0x1800352e5  mov     r8d, 64665753h; Tag
0x1800352eb  mov     edx, ecx; NumberOfBytes
0x1800352ed  mov     ecx, 200h; PoolType
0x1800352f2  call    cs:__imp_ExAllocatePoolWithTag
0x1800352f9  nop     dword ptr [rax+rax+00h]
0x1800352fe  mov     rdi, rax
0x180035301  test    rax, rax
0x180035304  jnz     short loc_180035310
0x180035306  mov     eax, 0C000009Ah
0x18003530b  jmp     loc_180035886
0x180035310  mov     rax, [rbp+40h]
0x180035314  mov     r8, r12; Size
0x180035317  xor     edx, edx; Val
0x180035319  mov     rcx, rdi; void *
0x18003531c  mov     [rax], rdi
0x18003531f  call    memset
0x180035324  lea     rdx, [r14-2FEh]; cbDest
0x18003532b  mov     r8, rbx; pszSrc
0x18003532e  lea     rcx, [rdi+2F8h]; pszDest
0x180035335  call    StringCbCopyW
0x18003533a  test    eax, eax
0x18003533c  js      loc_180035860
0x180035342  mov     rax, [rbp+8]
0x180035346  mov     r12, [rsp+78h+ServiceRelativePath]
0x18003534e  mov     rcx, [rax+30h]
0x180035352  movzx   eax, word ptr [rcx+1Ah]
0x180035356  add     ax, 6Ah ; 'j'
0x18003535a  test    r12, r12
0x18003535d  jz      short loc_180035374
0x18003535f  mov     rbx, rsi
0x180035362  inc     rbx
0x180035365  cmp     [r12+rbx*2], r15w
0x18003536a  jnz     short loc_180035362
0x18003536c  add     bx, bx
0x18003536f  add     bx, ax
0x180035372  jmp     short loc_180035377
0x180035374  movzx   ebx, ax
0x180035377  movzx   r15d, bx
0x18003537b  mov     r8d, 72645753h; Tag
0x180035381  mov     edx, r15d; NumberOfBytes
0x180035384  mov     ecx, 401h; PoolType
0x180035389  call    cs:__imp_ExAllocatePoolWithTag
0x180035390  nop     dword ptr [rax+rax+00h]
0x180035395  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18003539c  mov     r14, rax
0x18003539f  jnz     short loc_1800353B3
0x1800353a1  test    rax, rax
0x1800353a4  jz      short loc_1800353B3
0x1800353a6  mov     r8d, r15d; Size
0x1800353a9  xor     edx, edx; Val
0x1800353ab  mov     rcx, rax; void *
0x1800353ae  call    memset
0x1800353b3  mov     [rdi+158h], r14
0x1800353ba  test    r14, r14
0x1800353bd  jz      loc_180035860
0x1800353c3  mov     [rdi+152h], bx
0x1800353ca  lea     r9, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x1800353d1  mov     rax, [rbp+8]
0x1800353d5  mov     rdx, r15; cbDest
0x1800353d8  mov     rcx, r14; pszDest
0x1800353db  mov     rax, [rax+30h]
0x1800353df  mov     rax, [rax+20h]
0x1800353e3  test    r12, r12
0x1800353e6  jz      short loc_180035424
0x1800353e8  mov     [rsp+78h+var_50], r12
0x1800353ed  lea     r8, aSSS; "%s\\%s\\%s"
0x1800353f4  mov     [rsp+78h+var_58], rax
0x1800353f9  call    StringCbPrintfW
0x1800353fe  xor     r15d, r15d
0x180035401  test    eax, eax
0x180035403  jns     short loc_180035437
0x180035405  mov     rcx, [rdi+158h]; P
0x18003540c  xor     edx, edx; Tag
0x18003540e  call    cs:__imp_ExFreePoolWithTag
0x180035415  nop     dword ptr [rax+rax+00h]
0x18003541a  mov     esi, 0C0000001h
0x18003541f  jmp     loc_180035865
0x180035424  lea     r8, aSS; "%s\\%s"
0x18003542b  mov     [rsp+78h+var_58], rax
0x180035430  call    StringCbPrintfW
0x180035435  jmp     short loc_1800353FE
0x180035437  mov     rax, [rdi+158h]
0x18003543e  inc     rsi
0x180035441  cmp     [rax+rsi*2], r15w
0x180035446  jnz     short loc_18003543E
0x180035448  mov     rdx, [rsp+78h+InterfaceGuid]; InterfaceClassGuid
0x180035450  add     si, si
0x180035453  mov     [rdi+150h], si
0x18003545a  test    rdx, rdx
0x18003545d  jz      loc_18003556F
0x180035463  lea     rbx, [rdi+50h]
0x180035467  xor     r8d, r8d; ReferenceString
0x18003546a  mov     r9, rbx; SymbolicLinkName
0x18003546d  mov     rcx, r13; PhysicalDeviceObject
0x180035470  call    cs:__imp_IoRegisterDeviceInterface
0x180035477  nop     dword ptr [rax+rax+00h]
0x18003547c  mov     esi, eax
0x18003547e  test    eax, eax
0x180035480  js      loc_18003552F
0x180035486  lea     r14, WPP_RECORDER_INITIALIZED
0x18003548d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180035494  jz      short loc_1800354C8
0x180035496  mov     rcx, cs:WPP_GLOBAL_Control
0x18003549d  cmp     [rcx+48h], r15w
0x1800354a2  jz      short loc_1800354C8
0x1800354a4  mov     rax, [rdi+58h]
0x1800354a8  mov     r9d, 0Bh
0x1800354ae  mov     rcx, [rcx+40h]
0x1800354b2  mov     [rsp+78h+var_50], rax
0x1800354b7  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x1800354be  mov     [rsp+78h+var_58], rax
0x1800354c3  call    WPP_RECORDER_SF_S
0x1800354c8  mov     r12d, 1
0x1800354ce  mov     rcx, rbx; SymbolicLinkName
0x1800354d1  mov     dl, r12b; Enable
0x1800354d4  call    cs:__imp_IoSetDeviceInterfaceState
0x1800354db  nop     dword ptr [rax+rax+00h]
0x1800354e0  mov     esi, eax
0x1800354e2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800354e9  jz      short loc_18003551C
0x1800354eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800354f2  cmp     [rcx+48h], r15w
0x1800354f7  jz      short loc_18003551C
0x1800354f9  mov     rcx, [rcx+40h]
0x1800354fd  lea     r9d, [r12+0Bh]
0x180035502  mov     dword ptr [rsp+78h+var_50], eax
0x180035506  mov     r8d, r12d
0x180035509  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180035510  mov     dl, 5
0x180035512  mov     [rsp+78h+var_58], rax
0x180035517  call    WPP_RECORDER_SF_D
0x18003551c  test    esi, esi
0x18003551e  jns     short loc_180035575
0x180035520  mov     rcx, rbx; UnicodeString
0x180035523  call    cs:__imp_RtlFreeUnicodeString
0x18003552a  nop     dword ptr [rax+rax+00h]
0x18003552f  cmp     [rdi+58h], r15
0x180035533  jz      short loc_180035555
0x180035535  xor     edx, edx; Enable
0x180035537  mov     rcx, rbx; SymbolicLinkName
0x18003553a  call    cs:__imp_IoSetDeviceInterfaceState
0x180035541  nop     dword ptr [rax+rax+00h]
0x180035546  mov     rcx, rbx; UnicodeString
0x180035549  call    cs:__imp_RtlFreeUnicodeString
0x180035550  nop     dword ptr [rax+rax+00h]
0x180035555  mov     rcx, [rdi+158h]; P
0x18003555c  xor     edx, edx; Tag
0x18003555e  call    cs:__imp_ExFreePoolWithTag
0x180035565  nop     dword ptr [rax+rax+00h]
0x18003556a  jmp     loc_180035865
0x18003556f  mov     r12d, 1
0x180035575  lea     r14, [rdi+18h]
0x180035579  xor     r8d, r8d; State
0x18003557c  lea     rcx, [r14+18h]; Event
0x180035580  mov     [r14], r12d
0x180035583  mov     edx, r12d; Type
0x180035586  mov     [r14+8], r15
0x18003558a  mov     [r14+10h], r15d
0x18003558e  call    cs:__imp_KeInitializeEvent
0x180035595  nop     dword ptr [rax+rax+00h]
0x18003559a  lea     rcx, [rdi+90h]; Event
0x1800355a1  mov     [rdi+78h], r12d
0x1800355a5  xor     r8d, r8d; State
0x1800355a8  mov     [rdi+80h], r15
0x1800355af  mov     edx, r12d; Type
0x1800355b2  mov     [rdi+88h], r15d
0x1800355b9  call    cs:__imp_KeInitializeEvent
0x1800355c0  nop     dword ptr [rax+rax+00h]
0x1800355c5  lea     rcx, [rdi+0C0h]; Timer
0x1800355cc  call    cs:__imp_KeInitializeTimer
0x1800355d3  nop     dword ptr [rax+rax+00h]
0x1800355d8  lea     rcx, [rdi+100h]; Dpc
0x1800355df  mov     r8, rdi; DeferredContext
0x1800355e2  lea     rdx, SweeperDeferredRoutine; DeferredRoutine
0x1800355e9  call    cs:__imp_KeInitializeDpc
0x1800355f0  nop     dword ptr [rax+rax+00h]
0x1800355f5  mov     [rdi+70h], rbp
0x1800355f9  lea     rcx, [rdi+0B8h]; RunRef
0x180035600  mov     [rdi+8], rdi
0x180035604  mov     [rdi], rdi
0x180035607  mov     [rdi+10h], r12d
0x18003560b  mov     [rdi+60h], r13
0x18003560f  mov     [rdi+0B0h], r15d
0x180035616  mov     [rdi+140h], r15d
0x18003561d  call    cs:__imp_ExInitializeRundownProtection
0x180035624  nop     dword ptr [rax+rax+00h]
0x180035629  lea     rcx, [rdi+208h]; Event
0x180035630  mov     [rdi+1F0h], r12d
0x180035637  xor     r8d, r8d; State
0x18003563a  mov     [rdi+1F8h], r15
0x180035641  mov     edx, r12d; Type
0x180035644  mov     [rdi+200h], r15d
0x18003564b  call    cs:__imp_KeInitializeEvent
0x180035652  nop     dword ptr [rax+rax+00h]
0x180035657  lea     rcx, [rdi+238h]; Timer
0x18003565e  call    cs:__imp_KeInitializeTimer
0x180035665  nop     dword ptr [rax+rax+00h]
0x18003566a  lea     rcx, [rdi+278h]; Dpc
0x180035671  mov     r8, rdi; DeferredContext
0x180035674  lea     rdx, RescanDeferredRoutine; DeferredRoutine
0x18003567b  call    cs:__imp_KeInitializeDpc
0x180035682  nop     dword ptr [rax+rax+00h]
0x180035687  mov     qword ptr [rdi+228h], 0
0x180035692  lea     rcx, [rdi+230h]; RunRef
0x180035699  mov     [rdi+2B8h], r15d
0x1800356a0  call    cs:__imp_ExInitializeRundownProtection
0x1800356a7  nop     dword ptr [rax+rax+00h]
0x1800356ac  mov     rax, [rsp+78h+arg_18]
0x1800356b4  test    rax, rax
0x1800356b7  jz      short loc_1800356BF
0x1800356b9  mov     [rdi+68h], rax
0x1800356bd  jmp     short loc_1800356E5
0x1800356bf  mov     rdx, r13; TargetDevice
0x1800356c2  mov     rcx, rbp; SourceDevice
0x1800356c5  call    cs:__imp_IoAttachDeviceToDeviceStack
0x1800356cc  nop     dword ptr [rax+rax+00h]
0x1800356d1  mov     [rdi+68h], rax
0x1800356d5  test    rax, rax
0x1800356d8  jz      loc_1800357A5
0x1800356de  mov     [rdi+160h], r12d
0x1800356e5  lea     rbx, [rdi+2E8h]
0x1800356ec  mov     rcx, rbx; PerformanceFrequency
0x1800356ef  call    cs:__imp_KeQueryPerformanceCounter
0x1800356f6  nop     dword ptr [rax+rax+00h]
0x1800356fb  imul    rax, [rbx], 4B0h
0x180035702  mov     [rdi+2F0h], rax
0x180035709  bts     dword ptr [rbp+30h], 0Dh
0x18003570e  call    cs:__imp_KeEnterCriticalRegion
0x180035715  nop     dword ptr [rax+rax+00h]
0x18003571a  mov     rcx, r14; FastMutex
0x18003571d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x180035724  nop     dword ptr [rax+rax+00h]
0x180035729  mov     rcx, rbp
0x18003572c  call    ScanBus
0x180035731  mov     rcx, r14; FastMutex
0x180035734  mov     esi, eax
0x180035736  call    cs:__imp_ExReleaseFastMutexUnsafe
0x18003573d  nop     dword ptr [rax+rax+00h]
0x180035742  call    cs:__imp_KeLeaveCriticalRegion
0x180035749  nop     dword ptr [rax+rax+00h]
0x18003574e  test    esi, esi
0x180035750  js      short loc_1800357AA
0x180035752  mov     rcx, [rdi+70h]; DeviceObject
0x180035756  call    cs:__imp_IoAllocateWorkItem
0x18003575d  nop     dword ptr [rax+rax+00h]
0x180035762  mov     [rdi+148h], rax
0x180035769  test    rax, rax
0x18003576c  jz      short loc_18003578A
0x18003576e  mov     rcx, [rdi+70h]; DeviceObject
0x180035772  call    cs:__imp_IoAllocateWorkItem
0x180035779  nop     dword ptr [rax+rax+00h]
0x18003577e  mov     [rdi+2C0h], rax
  ... truncated ...
```
