# FveFilterRemoveDevice

- ea: `0x1400701c4`
- end: `0x140070565`
- name: `FveFilterRemoveDevice`
- size: `929`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140091220`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x140023234`
- `0x14002341c`
- `0x14002345c`
- `0x140023a64`
- `0x1400267dc`
- `0x14002c140`
- `0x140050b20`
- `0x140050dec`
- `0x1400701c4`
- `0x14007d8c4`
- `0x1400944cc`
- `0x1400d3750`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400704ed`
- `ntoskrnl!IofCallDriver` at `0x1400704ed`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400703c8`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x1400703c8`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140070464`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140070464`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400704c8`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400704c8`
- `ntoskrnl!IoDetachDevice` at `0x1400704fe`
- `ntoskrnl!IoDetachDevice` at `0x1400704fe`
- `ntoskrnl!IoDeleteDevice` at `0x14007050d`
- `ntoskrnl!IoDeleteDevice` at `0x14007050d`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1400702bc`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x1400702bc`
- `ntoskrnl!KeSetEvent` at `0x140070268`
- `ntoskrnl!KeSetEvent` at `0x140070268`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400702f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070350`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400703a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400703de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070434`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007047e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400704a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400702f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070350`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400703a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400703de`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070434`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007047e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400704a8`

## pseudocode

```c
__int64 __fastcall FveFilterRemoveDevice(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char *DeviceExtension; // rbx
  struct _DEVICE_OBJECT *v5; // r14
  _QWORD *v6; // rax
  __int64 v7; // r8
  void *v8; // rcx
  void *v9; // rcx
  _QWORD **v10; // rdi
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  ULONG_PTR v13; // rcx
  struct _LOOKASIDE_LIST_EX *v14; // rcx
  void *v15; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v16; // rcx
  void *v17; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v18; // rcx
  unsigned int v19; // ebx
  _BYTE v21[200]; // [rsp+20h] [rbp-C8h] BYREF

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v5 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 14);
  memset(v21, 0, 0x90u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 152, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids);
  }
  FveDisconnectVol(DeviceExtension);
  if ( (*((_DWORD *)DeviceExtension + 202) & 0x100) != 0 )
  {
    v6 = (_QWORD *)*((_QWORD *)DeviceExtension + 92);
    if ( v6 )
    {
      if ( *v6 )
        FveEowFreeSweepStopEx(DeviceExtension, 0, 0);
    }
  }
  KeSetEvent((PRKEVENT)(DeviceExtension + 4688), 0, 0);
  FveQueueShutdown(DeviceExtension);
  FvepReleaseRemoveLockAndWait((ULONG_PTR)(DeviceExtension + 56));
  FveTestRwCleanup(DeviceExtension);
  LOBYTE(v7) = 1;
  FvepAcquireDevFveLock(DeviceExtension, v21, v7);
  FveCleanup(DeviceExtension);
  v8 = (void *)*((_QWORD *)DeviceExtension + 169);
  if ( v8 )
  {
    PoUnregisterPowerSettingCallback(v8);
    *((_QWORD *)DeviceExtension + 169) = 0;
    *((_DWORD *)DeviceExtension + 340) = 3;
  }
  v9 = (void *)*((_QWORD *)DeviceExtension + 591);
  if ( v9 )
  {
    ExFreePoolWithTag(v9, 0x30455646u);
    *((_QWORD *)DeviceExtension + 591) = 0;
  }
  *((_DWORD *)DeviceExtension + 213) &= 0x3FFFFFFFu;
  FvepReleaseDevFveLock(v21);
  FveQueueCleanup(DeviceExtension);
  v10 = (_QWORD **)(DeviceExtension + 4520);
  while ( 1 )
  {
    v11 = *v10;
    if ( *v10 == v10 )
      break;
    if ( (_QWORD **)v11[1] != v10 || (v12 = (_QWORD *)*v11, *(_QWORD **)(*v11 + 8LL) != v11) )
      __fastfail(3u);
    *v10 = v12;
    v12[1] = v10;
    --*((_DWORD *)DeviceExtension + 1136);
    ExFreePoolWithTag(v11, 0x30455646u);
  }
  *(_OWORD *)v10 = 0;
  *(_OWORD *)(DeviceExtension + 4536) = 0;
  FvePerfDevCloseInstance(DeviceExtension);
  FvePerfTraceDevPtr(DeviceExtension, FVE_PERF_VOLUME_DELETE, *((_QWORD *)DeviceExtension + 15));
  v13 = *((_QWORD *)DeviceExtension + 74);
  if ( v13 )
  {
    FveWorkItemCleanup(v13);
    ExFreePoolWithTag(*((PVOID *)DeviceExtension + 74), 0x30455646u);
    *((_QWORD *)DeviceExtension + 74) = 0;
  }
  v14 = (struct _LOOKASIDE_LIST_EX *)*((_QWORD *)DeviceExtension + 73);
  if ( v14 )
  {
    ExDeleteLookasideListEx(v14);
    ExFreePoolWithTag(*((PVOID *)DeviceExtension + 73), 0x30455646u);
    *((_QWORD *)DeviceExtension + 73) = 0;
  }
  FveFrRangeListFree(DeviceExtension + 144);
  FveFrRangeListFree(DeviceExtension + 232);
  FveFrRangeListFree(DeviceExtension + 320);
  FveFrRangeListFree(DeviceExtension + 408);
  v15 = (void *)*((_QWORD *)DeviceExtension + 599);
  if ( v15 )
  {
    ExFreePoolWithTag(v15, 0x30455646u);
    *((_DWORD *)DeviceExtension + 1200) = 0;
    *((_DWORD *)DeviceExtension + 1201) = -1073741802;
  }
  v16 = *(struct _NPAGED_LOOKASIDE_LIST **)(*((_QWORD *)DeviceExtension + 292) + 8LL);
  if ( v16 )
  {
    ExDeleteNPagedLookasideList(v16);
    ExFreePoolWithTag(*(PVOID *)(*((_QWORD *)DeviceExtension + 292) + 8LL), 0x30455646u);
    *(_QWORD *)(*((_QWORD *)DeviceExtension + 292) + 8LL) = 0;
  }
  v17 = (void *)*((_QWORD *)DeviceExtension + 292);
  if ( v17 )
  {
    ExFreePoolWithTag(v17, 0x30455646u);
    *((_QWORD *)DeviceExtension + 292) = 0;
  }
  v18 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)DeviceExtension + 13);
  if ( v18 )
  {
    ExFreeCacheAwareRundownProtection(v18);
    *((_QWORD *)DeviceExtension + 13) = 0;
  }
  ++Irp->CurrentLocation;
  ++Irp->Tail.Overlay.CurrentStackLocation;
  v19 = IofCallDriver(v5, Irp);
  IoDetachDevice(v5);
  IoDeleteDevice(DeviceObject);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 153, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids, v19);
  }
  return v19;
}

```

## disassembly

```asm
0x1400701c4  push    rbx
0x1400701c6  push    rbp
0x1400701c7  push    rsi
0x1400701c8  push    rdi
0x1400701c9  push    r12
0x1400701cb  push    r14
0x1400701cd  sub     rsp, 0B8h
0x1400701d4  mov     rbx, [rcx+40h]
0x1400701d8  mov     rsi, rdx
0x1400701db  mov     rbp, rcx
0x1400701de  xor     edx, edx; Val
0x1400701e0  mov     r8d, 90h; Size
0x1400701e6  lea     rcx, [rsp+0E8h+var_C8]; void *
0x1400701eb  mov     r14, [rbx+70h]
0x1400701ef  call    memset
0x1400701f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400701fb  lea     rax, WPP_GLOBAL_Control
0x140070202  cmp     rcx, rax
0x140070205  jz      short loc_140070229
0x140070207  mov     eax, [rcx+2Ch]
0x14007020a  test    al, 40h
0x14007020c  jz      short loc_140070229
0x14007020e  cmp     byte ptr [rcx+29h], 5
0x140070212  jb      short loc_140070229
0x140070214  mov     rcx, [rcx+18h]
0x140070218  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x14007021f  mov     edx, 98h
0x140070224  call    WPP_SF_
0x140070229  mov     rcx, rbx
0x14007022c  call    FveDisconnectVol
0x140070231  test    dword ptr [rbx+328h], 100h
0x14007023b  jz      short loc_14007025C
0x14007023d  mov     rax, [rbx+2E0h]
0x140070244  test    rax, rax
0x140070247  jz      short loc_14007025C
0x140070249  cmp     qword ptr [rax], 0
0x14007024d  jz      short loc_14007025C
0x14007024f  xor     r8d, r8d
0x140070252  xor     edx, edx
0x140070254  mov     rcx, rbx
0x140070257  call    FveEowFreeSweepStopEx
0x14007025c  lea     rcx, [rbx+1250h]; Event
0x140070263  xor     r8d, r8d; Wait
0x140070266  xor     edx, edx; Increment
0x140070268  call    cs:__imp_KeSetEvent
0x14007026f  nop     dword ptr [rax+rax+00h]
0x140070274  mov     rcx, rbx
0x140070277  call    FveQueueShutdown
0x14007027c  lea     rcx, [rbx+38h]; BugCheckParameter2
0x140070280  call    FvepReleaseRemoveLockAndWait
0x140070285  mov     rcx, rbx
0x140070288  call    FveTestRwCleanup
0x14007028d  mov     r8b, 1
0x140070290  lea     rdx, [rsp+0E8h+var_C8]
0x140070295  mov     rcx, rbx
0x140070298  call    FvepAcquireDevFveLock
0x14007029d  mov     r9d, 19h
0x1400702a3  mov     r8b, 1
0x1400702a6  xor     edx, edx
0x1400702a8  mov     rcx, rbx; Context
0x1400702ab  call    FveCleanup
0x1400702b0  mov     rcx, [rbx+548h]; Handle
0x1400702b7  test    rcx, rcx
0x1400702ba  jz      short loc_1400702DD
0x1400702bc  call    cs:__imp_PoUnregisterPowerSettingCallback
0x1400702c3  nop     dword ptr [rax+rax+00h]
0x1400702c8  mov     qword ptr [rbx+548h], 0
0x1400702d3  mov     dword ptr [rbx+550h], 3
0x1400702dd  mov     rcx, [rbx+1278h]; P
0x1400702e4  mov     r12d, 30455646h
0x1400702ea  test    rcx, rcx
0x1400702ed  jz      short loc_140070309
0x1400702ef  mov     edx, r12d; Tag
0x1400702f2  call    cs:__imp_ExFreePoolWithTag
0x1400702f9  nop     dword ptr [rax+rax+00h]
0x1400702fe  mov     qword ptr [rbx+1278h], 0
0x140070309  and     dword ptr [rbx+354h], 3FFFFFFFh
0x140070313  lea     rcx, [rsp+0E8h+var_C8]
0x140070318  call    FvepReleaseDevFveLock
0x14007031d  mov     rcx, rbx
0x140070320  call    FveQueueCleanup
0x140070325  lea     rdi, [rbx+11A8h]
0x14007032c  mov     rcx, [rdi]; P
0x14007032f  cmp     rcx, rdi
0x140070332  jz      short loc_140070365
0x140070334  cmp     [rcx+8], rdi
0x140070338  jnz     short loc_14007035E
0x14007033a  mov     rax, [rcx]
0x14007033d  cmp     [rax+8], rcx
0x140070341  jnz     short loc_14007035E
0x140070343  mov     [rdi], rax
0x140070346  mov     edx, r12d; Tag
0x140070349  mov     [rax+8], rdi
0x14007034d  dec     dword ptr [rdi+18h]
0x140070350  call    cs:__imp_ExFreePoolWithTag
0x140070357  nop     dword ptr [rax+rax+00h]
0x14007035c  jmp     short loc_14007032C
0x14007035e  mov     ecx, 3
0x140070363  int     29h; Win8: RtlFailFast(ecx)
0x140070365  xorps   xmm0, xmm0
0x140070368  mov     rcx, rbx
0x14007036b  movups  xmmword ptr [rdi], xmm0
0x14007036e  movups  xmmword ptr [rdi+10h], xmm0
0x140070372  call    FvePerfDevCloseInstance
0x140070377  mov     r8, [rbx+78h]
0x14007037b  lea     rdx, FVE_PERF_VOLUME_DELETE
0x140070382  mov     rcx, rbx
0x140070385  call    FvePerfTraceDevPtr
0x14007038a  mov     rcx, [rbx+250h]; BugCheckParameter2
0x140070391  test    rcx, rcx
0x140070394  jz      short loc_1400703BC
0x140070396  call    FveWorkItemCleanup
0x14007039b  mov     rcx, [rbx+250h]; P
0x1400703a2  mov     edx, r12d; Tag
0x1400703a5  call    cs:__imp_ExFreePoolWithTag
0x1400703ac  nop     dword ptr [rax+rax+00h]
0x1400703b1  mov     qword ptr [rbx+250h], 0
0x1400703bc  mov     rcx, [rbx+248h]; Lookaside
0x1400703c3  test    rcx, rcx
0x1400703c6  jz      short loc_1400703F5
0x1400703c8  call    cs:__imp_ExDeleteLookasideListEx
0x1400703cf  nop     dword ptr [rax+rax+00h]
0x1400703d4  mov     rcx, [rbx+248h]; P
0x1400703db  mov     edx, r12d; Tag
0x1400703de  call    cs:__imp_ExFreePoolWithTag
0x1400703e5  nop     dword ptr [rax+rax+00h]
0x1400703ea  mov     qword ptr [rbx+248h], 0
0x1400703f5  lea     rcx, [rbx+90h]; void *
0x1400703fc  call    FveFrRangeListFree
0x140070401  lea     rcx, [rbx+0E8h]; void *
0x140070408  call    FveFrRangeListFree
0x14007040d  lea     rcx, [rbx+140h]; void *
0x140070414  call    FveFrRangeListFree
0x140070419  lea     rcx, [rbx+198h]; void *
0x140070420  call    FveFrRangeListFree
0x140070425  mov     rcx, [rbx+12B8h]; P
0x14007042c  test    rcx, rcx
0x14007042f  jz      short loc_140070454
0x140070431  mov     edx, r12d; Tag
0x140070434  call    cs:__imp_ExFreePoolWithTag
0x14007043b  nop     dword ptr [rax+rax+00h]
0x140070440  mov     dword ptr [rbx+12C0h], 0
0x14007044a  mov     dword ptr [rbx+12C4h], 0C0000016h
0x140070454  mov     rax, [rbx+920h]
0x14007045b  mov     rcx, [rax+8]; Lookaside
0x14007045f  test    rcx, rcx
0x140070462  jz      short loc_140070499
0x140070464  call    cs:__imp_ExDeleteNPagedLookasideList
0x14007046b  nop     dword ptr [rax+rax+00h]
0x140070470  mov     rcx, [rbx+920h]
0x140070477  mov     edx, r12d; Tag
0x14007047a  mov     rcx, [rcx+8]; P
0x14007047e  call    cs:__imp_ExFreePoolWithTag
0x140070485  nop     dword ptr [rax+rax+00h]
0x14007048a  mov     rax, [rbx+920h]
0x140070491  mov     qword ptr [rax+8], 0
0x140070499  mov     rcx, [rbx+920h]; P
0x1400704a0  test    rcx, rcx
0x1400704a3  jz      short loc_1400704BF
0x1400704a5  mov     edx, r12d; Tag
0x1400704a8  call    cs:__imp_ExFreePoolWithTag
0x1400704af  nop     dword ptr [rax+rax+00h]
0x1400704b4  mov     qword ptr [rbx+920h], 0
0x1400704bf  mov     rcx, [rbx+68h]; RunRefCacheAware
0x1400704c3  test    rcx, rcx
0x1400704c6  jz      short loc_1400704DC
0x1400704c8  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400704cf  nop     dword ptr [rax+rax+00h]
0x1400704d4  mov     qword ptr [rbx+68h], 0
0x1400704dc  inc     byte ptr [rsi+43h]
0x1400704df  mov     rdx, rsi; Irp
0x1400704e2  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x1400704ea  mov     rcx, r14; DeviceObject
0x1400704ed  call    cs:__imp_IofCallDriver
0x1400704f4  nop     dword ptr [rax+rax+00h]
0x1400704f9  mov     rcx, r14; TargetDevice
0x1400704fc  mov     ebx, eax
0x1400704fe  call    cs:__imp_IoDetachDevice
0x140070505  nop     dword ptr [rax+rax+00h]
0x14007050a  mov     rcx, rbp; DeviceObject
0x14007050d  call    cs:__imp_IoDeleteDevice
0x140070514  nop     dword ptr [rax+rax+00h]
0x140070519  mov     rcx, cs:WPP_GLOBAL_Control
0x140070520  lea     rax, WPP_GLOBAL_Control
0x140070527  cmp     rcx, rax
0x14007052a  jz      short loc_140070552
0x14007052c  mov     edx, [rcx+2Ch]
0x14007052f  test    dl, 40h
0x140070532  jz      short loc_140070552
0x140070534  cmp     byte ptr [rcx+29h], 5
0x140070538  jb      short loc_140070552
0x14007053a  mov     rcx, [rcx+18h]
0x14007053e  lea     r8, WPP_b4b9d8ac9d1830ce077ccb64ddccb5ed_Traceguids
0x140070545  mov     edx, 99h
0x14007054a  mov     r9d, ebx
0x14007054d  call    WPP_SF_d
0x140070552  mov     eax, ebx
0x140070554  add     rsp, 0B8h
0x14007055b  pop     r14
0x14007055d  pop     r12
0x14007055f  pop     rdi
0x140070560  pop     rsi
0x140070561  pop     rbp
0x140070562  pop     rbx
0x140070563  retn
```
