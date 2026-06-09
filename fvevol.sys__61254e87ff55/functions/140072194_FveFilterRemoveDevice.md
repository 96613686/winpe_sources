# FveFilterRemoveDevice

- ea: `0x140072194`
- end: `0x140072535`
- name: `FveFilterRemoveDevice`
- size: `929`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400932d0`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140023040`
- `0x140024234`
- `0x14002441c`
- `0x14002445c`
- `0x140024a64`
- `0x1400277dc`
- `0x14002d140`
- `0x140052b20`
- `0x140052dec`
- `0x140072194`
- `0x14007f964`
- `0x14009657c`
- `0x1400d93d0`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400724bd`
- `ntoskrnl!IofCallDriver` at `0x1400724bd`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14007228c`
- `ntoskrnl!PoUnregisterPowerSettingCallback` at `0x14007228c`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140072398`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140072398`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140072434`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140072434`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140072498`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140072498`
- `ntoskrnl!IoDetachDevice` at `0x1400724ce`
- `ntoskrnl!IoDetachDevice` at `0x1400724ce`
- `ntoskrnl!IoDeleteDevice` at `0x1400724dd`
- `ntoskrnl!IoDeleteDevice` at `0x1400724dd`
- `ntoskrnl!KeSetEvent` at `0x140072238`
- `ntoskrnl!KeSetEvent` at `0x140072238`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400722c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072320`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072375`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400723ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072404`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007244e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072478`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400722c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072320`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072375`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400723ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072404`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007244e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072478`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 150, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
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
  KeSetEvent((PRKEVENT)DeviceExtension + 196, 0, 0);
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
  v9 = (void *)*((_QWORD *)DeviceExtension + 593);
  if ( v9 )
  {
    ExFreePoolWithTag(v9, 0x30455646u);
    *((_QWORD *)DeviceExtension + 593) = 0;
  }
  *((_DWORD *)DeviceExtension + 213) &= 0x3FFFFFFFu;
  FvepReleaseDevFveLock(v21);
  FveQueueCleanup(DeviceExtension);
  v10 = (_QWORD **)(DeviceExtension + 4536);
  while ( 1 )
  {
    v11 = *v10;
    if ( *v10 == v10 )
      break;
    if ( (_QWORD **)v11[1] != v10 || (v12 = (_QWORD *)*v11, *(_QWORD **)(*v11 + 8LL) != v11) )
      __fastfail(3u);
    *v10 = v12;
    v12[1] = v10;
    --*((_DWORD *)DeviceExtension + 1140);
    ExFreePoolWithTag(v11, 0x30455646u);
  }
  *(_OWORD *)v10 = 0;
  *(_OWORD *)(DeviceExtension + 4552) = 0;
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
  v15 = (void *)*((_QWORD *)DeviceExtension + 601);
  if ( v15 )
  {
    ExFreePoolWithTag(v15, 0x30455646u);
    *((_DWORD *)DeviceExtension + 1204) = 0;
    *((_DWORD *)DeviceExtension + 1205) = -1073741802;
  }
  v16 = *(struct _NPAGED_LOOKASIDE_LIST **)(*((_QWORD *)DeviceExtension + 294) + 8LL);
  if ( v16 )
  {
    ExDeleteNPagedLookasideList(v16);
    ExFreePoolWithTag(*(PVOID *)(*((_QWORD *)DeviceExtension + 294) + 8LL), 0x30455646u);
    *(_QWORD *)(*((_QWORD *)DeviceExtension + 294) + 8LL) = 0;
  }
  v17 = (void *)*((_QWORD *)DeviceExtension + 294);
  if ( v17 )
  {
    ExFreePoolWithTag(v17, 0x30455646u);
    *((_QWORD *)DeviceExtension + 294) = 0;
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 151, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v19);
  }
  return v19;
}

```

## disassembly

```asm
0x140072194  push    rbx
0x140072196  push    rbp
0x140072197  push    rsi
0x140072198  push    rdi
0x140072199  push    r12
0x14007219b  push    r14
0x14007219d  sub     rsp, 0B8h
0x1400721a4  mov     rbx, [rcx+40h]
0x1400721a8  mov     rsi, rdx
0x1400721ab  mov     rbp, rcx
0x1400721ae  xor     edx, edx; Val
0x1400721b0  mov     r8d, 90h; Size
0x1400721b6  lea     rcx, [rsp+0E8h+var_C8]; void *
0x1400721bb  mov     r14, [rbx+70h]
0x1400721bf  call    memset
0x1400721c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400721cb  lea     rax, WPP_GLOBAL_Control
0x1400721d2  cmp     rcx, rax
0x1400721d5  jz      short loc_1400721F9
0x1400721d7  mov     eax, [rcx+2Ch]
0x1400721da  test    al, 40h
0x1400721dc  jz      short loc_1400721F9
0x1400721de  cmp     byte ptr [rcx+29h], 5
0x1400721e2  jb      short loc_1400721F9
0x1400721e4  mov     rcx, [rcx+18h]
0x1400721e8  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x1400721ef  mov     edx, 96h
0x1400721f4  call    WPP_SF_
0x1400721f9  mov     rcx, rbx
0x1400721fc  call    FveDisconnectVol
0x140072201  test    dword ptr [rbx+328h], 100h
0x14007220b  jz      short loc_14007222C
0x14007220d  mov     rax, [rbx+2E0h]
0x140072214  test    rax, rax
0x140072217  jz      short loc_14007222C
0x140072219  cmp     qword ptr [rax], 0
0x14007221d  jz      short loc_14007222C
0x14007221f  xor     r8d, r8d
0x140072222  xor     edx, edx
0x140072224  mov     rcx, rbx
0x140072227  call    FveEowFreeSweepStopEx
0x14007222c  lea     rcx, [rbx+1260h]; Event
0x140072233  xor     r8d, r8d; Wait
0x140072236  xor     edx, edx; Increment
0x140072238  call    cs:__imp_KeSetEvent
0x14007223f  nop     dword ptr [rax+rax+00h]
0x140072244  mov     rcx, rbx
0x140072247  call    FveQueueShutdown
0x14007224c  lea     rcx, [rbx+38h]; BugCheckParameter2
0x140072250  call    FvepReleaseRemoveLockAndWait
0x140072255  mov     rcx, rbx
0x140072258  call    FveTestRwCleanup
0x14007225d  mov     r8b, 1
0x140072260  lea     rdx, [rsp+0E8h+var_C8]
0x140072265  mov     rcx, rbx
0x140072268  call    FvepAcquireDevFveLock
0x14007226d  mov     r9d, 19h
0x140072273  mov     r8b, 1
0x140072276  xor     edx, edx
0x140072278  mov     rcx, rbx; Context
0x14007227b  call    FveCleanup
0x140072280  mov     rcx, [rbx+548h]; Handle
0x140072287  test    rcx, rcx
0x14007228a  jz      short loc_1400722AD
0x14007228c  call    cs:__imp_PoUnregisterPowerSettingCallback
0x140072293  nop     dword ptr [rax+rax+00h]
0x140072298  mov     qword ptr [rbx+548h], 0
0x1400722a3  mov     dword ptr [rbx+550h], 3
0x1400722ad  mov     rcx, [rbx+1288h]; P
0x1400722b4  mov     r12d, 30455646h
0x1400722ba  test    rcx, rcx
0x1400722bd  jz      short loc_1400722D9
0x1400722bf  mov     edx, r12d; Tag
0x1400722c2  call    cs:__imp_ExFreePoolWithTag
0x1400722c9  nop     dword ptr [rax+rax+00h]
0x1400722ce  mov     qword ptr [rbx+1288h], 0
0x1400722d9  and     dword ptr [rbx+354h], 3FFFFFFFh
0x1400722e3  lea     rcx, [rsp+0E8h+var_C8]
0x1400722e8  call    FvepReleaseDevFveLock
0x1400722ed  mov     rcx, rbx
0x1400722f0  call    FveQueueCleanup
0x1400722f5  lea     rdi, [rbx+11B8h]
0x1400722fc  mov     rcx, [rdi]; P
0x1400722ff  cmp     rcx, rdi
0x140072302  jz      short loc_140072335
0x140072304  cmp     [rcx+8], rdi
0x140072308  jnz     short loc_14007232E
0x14007230a  mov     rax, [rcx]
0x14007230d  cmp     [rax+8], rcx
0x140072311  jnz     short loc_14007232E
0x140072313  mov     [rdi], rax
0x140072316  mov     edx, r12d; Tag
0x140072319  mov     [rax+8], rdi
0x14007231d  dec     dword ptr [rdi+18h]
0x140072320  call    cs:__imp_ExFreePoolWithTag
0x140072327  nop     dword ptr [rax+rax+00h]
0x14007232c  jmp     short loc_1400722FC
0x14007232e  mov     ecx, 3
0x140072333  int     29h; Win8: RtlFailFast(ecx)
0x140072335  xorps   xmm0, xmm0
0x140072338  mov     rcx, rbx
0x14007233b  movups  xmmword ptr [rdi], xmm0
0x14007233e  movups  xmmword ptr [rdi+10h], xmm0
0x140072342  call    FvePerfDevCloseInstance
0x140072347  mov     r8, [rbx+78h]
0x14007234b  lea     rdx, FVE_PERF_VOLUME_DELETE
0x140072352  mov     rcx, rbx
0x140072355  call    FvePerfTraceDevPtr
0x14007235a  mov     rcx, [rbx+250h]; BugCheckParameter2
0x140072361  test    rcx, rcx
0x140072364  jz      short loc_14007238C
0x140072366  call    FveWorkItemCleanup
0x14007236b  mov     rcx, [rbx+250h]; P
0x140072372  mov     edx, r12d; Tag
0x140072375  call    cs:__imp_ExFreePoolWithTag
0x14007237c  nop     dword ptr [rax+rax+00h]
0x140072381  mov     qword ptr [rbx+250h], 0
0x14007238c  mov     rcx, [rbx+248h]; Lookaside
0x140072393  test    rcx, rcx
0x140072396  jz      short loc_1400723C5
0x140072398  call    cs:__imp_ExDeleteLookasideListEx
0x14007239f  nop     dword ptr [rax+rax+00h]
0x1400723a4  mov     rcx, [rbx+248h]; P
0x1400723ab  mov     edx, r12d; Tag
0x1400723ae  call    cs:__imp_ExFreePoolWithTag
0x1400723b5  nop     dword ptr [rax+rax+00h]
0x1400723ba  mov     qword ptr [rbx+248h], 0
0x1400723c5  lea     rcx, [rbx+90h]; void *
0x1400723cc  call    FveFrRangeListFree
0x1400723d1  lea     rcx, [rbx+0E8h]; void *
0x1400723d8  call    FveFrRangeListFree
0x1400723dd  lea     rcx, [rbx+140h]; void *
0x1400723e4  call    FveFrRangeListFree
0x1400723e9  lea     rcx, [rbx+198h]; void *
0x1400723f0  call    FveFrRangeListFree
0x1400723f5  mov     rcx, [rbx+12C8h]; P
0x1400723fc  test    rcx, rcx
0x1400723ff  jz      short loc_140072424
0x140072401  mov     edx, r12d; Tag
0x140072404  call    cs:__imp_ExFreePoolWithTag
0x14007240b  nop     dword ptr [rax+rax+00h]
0x140072410  mov     dword ptr [rbx+12D0h], 0
0x14007241a  mov     dword ptr [rbx+12D4h], 0C0000016h
0x140072424  mov     rax, [rbx+930h]
0x14007242b  mov     rcx, [rax+8]; Lookaside
0x14007242f  test    rcx, rcx
0x140072432  jz      short loc_140072469
0x140072434  call    cs:__imp_ExDeleteNPagedLookasideList
0x14007243b  nop     dword ptr [rax+rax+00h]
0x140072440  mov     rcx, [rbx+930h]
0x140072447  mov     edx, r12d; Tag
0x14007244a  mov     rcx, [rcx+8]; P
0x14007244e  call    cs:__imp_ExFreePoolWithTag
0x140072455  nop     dword ptr [rax+rax+00h]
0x14007245a  mov     rax, [rbx+930h]
0x140072461  mov     qword ptr [rax+8], 0
0x140072469  mov     rcx, [rbx+930h]; P
0x140072470  test    rcx, rcx
0x140072473  jz      short loc_14007248F
0x140072475  mov     edx, r12d; Tag
0x140072478  call    cs:__imp_ExFreePoolWithTag
0x14007247f  nop     dword ptr [rax+rax+00h]
0x140072484  mov     qword ptr [rbx+930h], 0
0x14007248f  mov     rcx, [rbx+68h]; RunRefCacheAware
0x140072493  test    rcx, rcx
0x140072496  jz      short loc_1400724AC
0x140072498  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14007249f  nop     dword ptr [rax+rax+00h]
0x1400724a4  mov     qword ptr [rbx+68h], 0
0x1400724ac  inc     byte ptr [rsi+43h]
0x1400724af  mov     rdx, rsi; Irp
0x1400724b2  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x1400724ba  mov     rcx, r14; DeviceObject
0x1400724bd  call    cs:__imp_IofCallDriver
0x1400724c4  nop     dword ptr [rax+rax+00h]
0x1400724c9  mov     rcx, r14; TargetDevice
0x1400724cc  mov     ebx, eax
0x1400724ce  call    cs:__imp_IoDetachDevice
0x1400724d5  nop     dword ptr [rax+rax+00h]
0x1400724da  mov     rcx, rbp; DeviceObject
0x1400724dd  call    cs:__imp_IoDeleteDevice
0x1400724e4  nop     dword ptr [rax+rax+00h]
0x1400724e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400724f0  lea     rax, WPP_GLOBAL_Control
0x1400724f7  cmp     rcx, rax
0x1400724fa  jz      short loc_140072522
0x1400724fc  mov     edx, [rcx+2Ch]
0x1400724ff  test    dl, 40h
0x140072502  jz      short loc_140072522
0x140072504  cmp     byte ptr [rcx+29h], 5
0x140072508  jb      short loc_140072522
0x14007250a  mov     rcx, [rcx+18h]
0x14007250e  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140072515  mov     edx, 97h
0x14007251a  mov     r9d, ebx
0x14007251d  call    WPP_SF_d
0x140072522  mov     eax, ebx
0x140072524  add     rsp, 0B8h
0x14007252b  pop     r14
0x14007252d  pop     r12
0x14007252f  pop     rdi
0x140072530  pop     rsi
0x140072531  pop     rbp
0x140072532  pop     rbx
0x140072533  retn
```
