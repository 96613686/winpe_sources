# RxUnregisterMinirdr

- ea: `0x140048600`
- end: `0x14004886c`
- name: `RxUnregisterMinirdr`
- size: `620`
- prototype: `void __stdcall(PRDBSS_DEVICE_OBJECT RxDeviceObject)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140047ea0`

## callees

- `0x140014e40`
- `0x14001bb18`
- `0x1400204a0`
- `0x140023a04`
- `0x140048600`
- `0x140050d38`
- `0x140051cec`
- `0x14005dac0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140048710`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140048710`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400487a4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400487a4`
- `ntoskrnl!ObfDereferenceObject` at `0x14004884e`
- `ntoskrnl!ObfDereferenceObject` at `0x14004884e`
- `ntoskrnl!FsRtlDeregisterUncProvider` at `0x140048696`
- `ntoskrnl!FsRtlDeregisterUncProvider` at `0x140048696`
- `ntoskrnl!IoDeleteDevice` at `0x14004883f`
- `ntoskrnl!IoDeleteDevice` at `0x14004883f`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400487e6`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400487e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048830`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048830`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400486fd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400486fd`

## pseudocode

```c
void __stdcall RxUnregisterMinirdr(PRDBSS_DEVICE_OBJECT RxDeviceObject)
{
  PRDBSS_EXPORTS RdbssExports; // rsi
  PRDBSS_DEVICE_OBJECT *MupHandle; // rdx
  PRDBSS_DEVICE_OBJECT *v4; // rcx
  int Blink_high; // eax
  BOOLEAN v6; // dl
  struct _LIST_ENTRY *Blink; // rbx

  RdbssExports = RxDeviceObject->RdbssExports;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Z(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids,
      &RxDeviceObject->Dispatch);
  }
  if ( RxDeviceObject->DeviceName.Buffer )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids,
        &RxDeviceObject->Dispatch);
    }
    FsRtlDeregisterUncProvider(RxDeviceObject->DeviceName.Buffer);
    RxDeviceObject->DeviceName.Buffer = 0;
  }
  if ( Fcb == (PFCB)RxDeviceObject )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids,
        &RxDeviceObject->Dispatch);
    }
    Fcb = 0;
  }
  RxpUninitializeMRxSiloContexts(RxDeviceObject);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
  MupHandle = (PRDBSS_DEVICE_OBJECT *)RxDeviceObject->MupHandle;
  if ( MupHandle[1] != (PRDBSS_DEVICE_OBJECT)&RxDeviceObject->MupHandle
    || (v4 = *(PRDBSS_DEVICE_OBJECT **)&RxDeviceObject->RegisterUncProvider,
        *v4 != (PRDBSS_DEVICE_OBJECT)&RxDeviceObject->MupHandle) )
  {
    __fastfail(3u);
  }
  *v4 = (PRDBSS_DEVICE_OBJECT)MupHandle;
  MupHandle[1] = (PRDBSS_DEVICE_OBJECT)v4;
  --RxContextLookasideList.L.Future[8];
  if ( (RxDeviceObject->RegistrationControls & 0x20) != 0 )
    --RxContextLookasideList.L.Future[9];
  Blink_high = HIDWORD(RxDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[29].Blink);
  if ( Blink_high != -1 )
  {
    Set |= 1LL << Blink_high;
    HIDWORD(RxDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[29].Blink) = -1;
  }
  if ( !RxContextLookasideList.L.Future[8] )
    *(_QWORD *)(*(_QWORD *)&RxContextLookasideList.L.FreeMisses + 104LL) = RxUnload;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)&RxContextLookasideList.L.AllocateEx);
  if ( (RxDeviceObject->RegistrationControls & 8) == 0 )
  {
    RxFinalizeNetTable(RxDeviceObject, v6);
    Blink = RxDeviceObject->RxNetNameTableInDeviceObject.HashBuckets[0].Blink;
    RxCancelTimerRequest(RxFileSystemDeviceObject, RxScavengerTimerRoutine, RxDeviceObject);
    ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)&Blink[10].Blink);
    LOBYTE(Blink[11].Flink) = 0;
    RxScavengerFinalizeEntries((PFCB)RxDeviceObject);
    RxFinalizePrefixTable((PRX_PREFIX_TABLE)&RxDeviceObject->FastWriteBytesRequested);
  }
  if ( (RxDeviceObject->RegistrationControls & 0x10) != 0 )
    RxFinalizePrefixTable((PRX_PREFIX_TABLE)&RxDeviceObject->pRxNetNameTable);
  RxSpinDownOutstandingAsynchronousRequests(RxDeviceObject);
  KeLeaveCriticalRegion();
  IoDeleteDevice(&RxDeviceObject->DeviceObject);
  ObfDereferenceObject(RdbssExports);
}

```

## disassembly

```asm
0x140048600  push    rbx
0x140048602  push    rsi
0x140048603  push    rdi
0x140048604  push    r15
0x140048606  sub     rsp, 28h
0x14004860a  mov     rsi, [rcx+158h]
0x140048611  mov     rdi, rcx
0x140048614  mov     rcx, cs:WPP_GLOBAL_Control
0x14004861b  lea     r15, WPP_GLOBAL_Control
0x140048622  mov     bl, 4
0x140048624  cmp     rcx, r15
0x140048627  jz      short loc_140048651
0x140048629  mov     eax, [rcx+2Ch]
0x14004862c  test    al, 2
0x14004862e  jz      short loc_140048651
0x140048630  cmp     [rcx+29h], bl
0x140048633  jb      short loc_140048651
0x140048635  mov     rcx, [rcx+18h]
0x140048639  lea     r9, [rdi+168h]
0x140048640  mov     edx, 11h
0x140048645  lea     r8, WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids
0x14004864c  call    WPP_SF_Z
0x140048651  cmp     qword ptr [rdi+178h], 0
0x140048659  jz      short loc_1400486AD
0x14004865b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048662  cmp     rcx, r15
0x140048665  jz      short loc_14004868F
0x140048667  mov     eax, [rcx+2Ch]
0x14004866a  test    al, 2
0x14004866c  jz      short loc_14004868F
0x14004866e  cmp     [rcx+29h], bl
0x140048671  jb      short loc_14004868F
0x140048673  mov     rcx, [rcx+18h]
0x140048677  lea     r9, [rdi+168h]
0x14004867e  mov     edx, 12h
0x140048683  lea     r8, WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids
0x14004868a  call    WPP_SF_Z
0x14004868f  mov     rcx, [rdi+178h]; Handle
0x140048696  call    cs:__imp_FsRtlDeregisterUncProvider
0x14004869d  nop     dword ptr [rax+rax+00h]
0x1400486a2  mov     qword ptr [rdi+178h], 0
0x1400486ad  cmp     cs:Fcb, rdi
0x1400486b4  jnz     short loc_1400486F5
0x1400486b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400486bd  cmp     rcx, r15
0x1400486c0  jz      short loc_1400486EA
0x1400486c2  mov     eax, [rcx+2Ch]
0x1400486c5  test    al, 2
0x1400486c7  jz      short loc_1400486EA
0x1400486c9  cmp     [rcx+29h], bl
0x1400486cc  jb      short loc_1400486EA
0x1400486ce  mov     rcx, [rcx+18h]
0x1400486d2  lea     r9, [rdi+168h]
0x1400486d9  mov     edx, 13h
0x1400486de  lea     r8, WPP_c5c6f4c415ea350ec3990f376a5f54b9_Traceguids
0x1400486e5  call    WPP_SF_Z
0x1400486ea  mov     cs:Fcb, 0
0x1400486f5  mov     rcx, rdi
0x1400486f8  call    RxpUninitializeMRxSiloContexts
0x1400486fd  call    cs:__imp_KeEnterCriticalRegion
0x140048704  nop     dword ptr [rax+rax+00h]
0x140048709  lea     rcx, RxContextLookasideList.L.30h; FastMutex
0x140048710  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140048717  nop     dword ptr [rax+rax+00h]
0x14004871c  lea     rax, [rdi+188h]
0x140048723  mov     rdx, [rax]
0x140048726  cmp     [rdx+8], rax
0x14004872a  jnz     loc_140048865
0x140048730  mov     rcx, [rax+8]
0x140048734  cmp     [rcx], rax
0x140048737  jnz     loc_140048865
0x14004873d  mov     [rcx], rdx
0x140048740  mov     [rdx+8], rcx
0x140048744  dec     dword ptr cs:RxContextLookasideList.L+78h
0x14004874a  mov     eax, [rdi+150h]
0x140048750  test    al, 20h
0x140048752  jz      short loc_14004875A
0x140048754  dec     dword ptr cs:RxContextLookasideList.L+7Ch
0x14004875a  mov     eax, [rdi+514h]
0x140048760  or      r8d, 0FFFFFFFFh
0x140048764  cmp     eax, r8d
0x140048767  jz      short loc_140048782
0x140048769  mov     rdx, cs:Set
0x140048770  bts     rdx, rax
0x140048774  mov     cs:Set, rdx
0x14004877b  mov     [rdi+514h], r8d
0x140048782  cmp     dword ptr cs:RxContextLookasideList.L+78h, 0
0x140048789  jnz     short loc_14004879D
0x14004878b  mov     rax, qword ptr cs:RxContextLookasideList.L.20h
0x140048792  lea     rdx, RxUnload
0x140048799  mov     [rax+68h], rdx
0x14004879d  lea     rcx, RxContextLookasideList.L.30h; FastMutex
0x1400487a4  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400487ab  nop     dword ptr [rax+rax+00h]
0x1400487b0  mov     eax, [rdi+150h]
0x1400487b6  test    al, 8
0x1400487b8  jnz     short loc_140048812
0x1400487ba  mov     rcx, rdi; RxDeviceObject
0x1400487bd  call    RxFinalizeNetTable
0x1400487c2  mov     rcx, cs:RxFileSystemDeviceObject; pDeviceObject
0x1400487c9  lea     rdx, RxScavengerTimerRoutine; Routine
0x1400487d0  mov     rbx, [rdi+340h]
0x1400487d7  mov     r8, rdi; pContext
0x1400487da  call    RxCancelTimerRequest
0x1400487df  lea     rcx, [rbx+0A8h]; RunRef
0x1400487e6  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400487ed  nop     dword ptr [rax+rax+00h]
0x1400487f2  mov     edx, 7Fh
0x1400487f7  mov     byte ptr [rbx+0B0h], 0
0x1400487fe  mov     rcx, rdi; Fcb
0x140048801  call    RxScavengerFinalizeEntries
0x140048806  lea     rcx, [rdi+200h]; ThisTable
0x14004880d  call    RxFinalizePrefixTable
0x140048812  mov     eax, [rdi+150h]
0x140048818  test    al, 10h
0x14004881a  jz      short loc_140048828
0x14004881c  lea     rcx, [rdi+2A0h]; ThisTable
0x140048823  call    RxFinalizePrefixTable
0x140048828  mov     rcx, rdi; RxDeviceObject
0x14004882b  call    RxSpinDownOutstandingAsynchronousRequests
0x140048830  call    cs:__imp_KeLeaveCriticalRegion
0x140048837  nop     dword ptr [rax+rax+00h]
0x14004883c  mov     rcx, rdi; DeviceObject
0x14004883f  call    cs:__imp_IoDeleteDevice
0x140048846  nop     dword ptr [rax+rax+00h]
0x14004884b  mov     rcx, rsi; Object
0x14004884e  call    cs:__imp_ObfDereferenceObject
0x140048855  nop     dword ptr [rax+rax+00h]
0x14004885a  add     rsp, 28h
0x14004885e  pop     r15
0x140048860  pop     rdi
0x140048861  pop     rsi
0x140048862  pop     rbx
0x140048863  retn
0x140048865  mov     ecx, 3
0x14004886a  int     29h; Win8: RtlFailFast(ecx)
```
