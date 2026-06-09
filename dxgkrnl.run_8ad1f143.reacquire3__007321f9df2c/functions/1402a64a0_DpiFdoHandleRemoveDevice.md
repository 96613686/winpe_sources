# DpiFdoHandleRemoveDevice

- ea: `0x1402a64a0`
- end: `0x1402a68ef`
- name: `DpiFdoHandleRemoveDevice`
- size: `1103`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, loader_planting`

## callees

- `0x1400406a8`
- `0x1400406ec`
- `0x14004790c`
- `0x1400554d4`
- `0x14008c358`
- `0x1400a01e0`
- `0x1400a0540`
- `0x140197644`
- `0x1401cae84`
- `0x1402a64a0`
- `0x1402a72e0`
- `0x1402ab508`
- `0x1402bc6f4`
- `0x1402bd824`
- `0x1402bdf90`
- `0x140306044`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1402a663a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6682`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a66a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a66db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a663a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a6682`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a66a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402a66db`
- `ntoskrnl!IoFreeWorkItem` at `0x1402a6741`
- `ntoskrnl!IoFreeWorkItem` at `0x1402a6741`
- `ntoskrnl!ExDeleteResourceLite` at `0x1402a6620`
- `ntoskrnl!ExDeleteResourceLite` at `0x1402a6620`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a681c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a682f`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a681c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402a682f`
- `ntoskrnl!IofCallDriver` at `0x1402a686c`
- `ntoskrnl!IofCallDriver` at `0x1402a686c`
- `ntoskrnl!IoDeleteDevice` at `0x1402a68cc`
- `ntoskrnl!IoDeleteDevice` at `0x1402a68cc`
- `ntoskrnl!KeSetEvent` at `0x1402a6847`
- `ntoskrnl!KeSetEvent` at `0x1402a6847`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a65df`
- `ntoskrnl!KeWaitForSingleObject` at `0x1402a65df`
- `ntoskrnl!KeReleaseMutex` at `0x1402a66fc`
- `ntoskrnl!KeReleaseMutex` at `0x1402a66fc`
- `ntoskrnl!IoDetachDevice` at `0x1402a68bd`
- `ntoskrnl!IoDetachDevice` at `0x1402a68bd`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1402a654b`
- `ntoskrnl!IoReleaseRemoveLockAndWaitEx` at `0x1402a654b`
- `watchdog!WdLogSingleEntry1` at `0x1402a64d7`
- `watchdog!WdLogSingleEntry1` at `0x1402a64d7`

## pseudocode

```c
__int64 __fastcall DpiFdoHandleRemoveDevice(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  char *DeviceExtension; // rbx
  __int64 v5; // r14
  int v6; // eax
  __int64 v7; // rcx
  _QWORD *v8; // rcx
  PVOID *v9; // rax
  __int64 v10; // rcx
  void *v11; // rcx
  _DWORD *v12; // rcx
  _DWORD *v13; // rcx
  void *v14; // rcx
  int v15; // eax
  struct _IO_WORKITEM *v16; // rcx
  void (__fastcall *v17)(_QWORD); // rax
  void (__fastcall *v18)(_QWORD); // rax
  void (__fastcall *v19)(_QWORD); // rax
  void (__fastcall *v20)(_QWORD); // rax
  unsigned int v21; // ebp
  PVOID v22; // rsi
  struct SYSMM_ADAPTER *v23; // rcx

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  v5 = *((_QWORD *)DeviceExtension + 5);
  AcquireMiniportListMutex();
  if ( (PDEVICE_OBJECT)qword_14015F078 == DeviceObject )
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 6967;
    qword_14015F078 = 0;
  }
  ReleaseMiniportListMutex();
  if ( DeviceExtension && *((_DWORD *)DeviceExtension + 4) == 1953656900 )
  {
    if ( (unsigned int)(*((_DWORD *)DeviceExtension + 5) - 2) <= 1
      && (unsigned int)(*((_DWORD *)DeviceExtension + 60) - 1) <= 1 )
    {
      DpiFdoHandleStopDevice(DeviceObject, Irp);
    }
    if ( *((_DWORD *)DeviceExtension + 4) == 1953656900 && *((_DWORD *)DeviceExtension + 5) == 2 )
      DpiPdoDestroyPendingPdoObjects(DeviceObject);
  }
  IoReleaseRemoveLockAndWaitEx((PIO_REMOVE_LOCK)DeviceExtension + 2, Irp, 0x20u);
  if ( DeviceExtension && *((_DWORD *)DeviceExtension + 4) == 1953656900 && *((_DWORD *)DeviceExtension + 5) == 2 )
    DpiFdoRemoveChildDescriptors(DeviceObject);
  *(_DWORD *)&DeviceExtension[4 * (*((_DWORD *)DeviceExtension + 69) & 7) + 244] = *((_DWORD *)DeviceExtension + 60);
  v6 = *((_DWORD *)DeviceExtension + 59);
  ++*((_DWORD *)DeviceExtension + 69);
  *((_DWORD *)DeviceExtension + 60) = v6;
  *((_DWORD *)DeviceExtension + 59) = 7;
  AcquireMiniportListMutex();
  if ( (unsigned __int8)DpiFdoIsPostDevice(DeviceObject) )
    qword_14015F080 = 0;
  if ( (unsigned __int8)DpiFdoIsMsBddAnchoredDevice(v7) )
    qword_14015F128 = 0;
  ReleaseMiniportListMutex();
  KeWaitForSingleObject((PVOID)(v5 + 72), Executive, 0, 0, 0);
  v8 = *(_QWORD **)DeviceExtension;
  if ( *(char **)(*(_QWORD *)DeviceExtension + 8LL) != DeviceExtension
    || (v9 = (PVOID *)*((_QWORD *)DeviceExtension + 1), *v9 != DeviceExtension) )
  {
    __fastfail(3u);
  }
  *v9 = v8;
  v8[1] = v9;
  --*(_DWORD *)(v5 + 128);
  v10 = *((_QWORD *)DeviceExtension + 21);
  if ( *(_DWORD *)(v10 + 104) == 1 )
  {
    ExDeleteResourceLite((PERESOURCE)v10);
    v11 = (void *)*((_QWORD *)DeviceExtension + 21);
    if ( v11 )
    {
      ExFreePoolWithTag(v11, 0);
      *((_QWORD *)DeviceExtension + 21) = 0;
    }
  }
  if ( DeviceExtension
    && *((_DWORD *)DeviceExtension + 4) == 1953656900
    && (unsigned int)(*((_DWORD *)DeviceExtension + 5) - 2) <= 1 )
  {
    v12 = (_DWORD *)*((_QWORD *)DeviceExtension + 185);
    if ( v12[2] == 1 && v12 )
    {
      ExFreePoolWithTag(v12, 0);
      *((_QWORD *)DeviceExtension + 185) = 0;
    }
    v13 = (_DWORD *)*((_QWORD *)DeviceExtension + 186);
    if ( v13[2] == 1 && v13 )
    {
      ExFreePoolWithTag(v13, 0);
      *((_QWORD *)DeviceExtension + 186) = 0;
    }
    if ( *((_DWORD *)DeviceExtension + 126) )
      DpiLdaUnLinkDeviceFromChain(DeviceObject);
    v14 = (void *)*((_QWORD *)DeviceExtension + 139);
    if ( v14 )
    {
      ExFreePoolWithTag(v14, 0);
      *((_QWORD *)DeviceExtension + 139) = 0;
    }
    DpiCheckSpbResourceLeakage(DeviceExtension);
  }
  KeReleaseMutex((PRKMUTEX)(v5 + 72), 0);
  if ( DeviceExtension && *((_DWORD *)DeviceExtension + 4) == 1953656900 )
  {
    v15 = *((_DWORD *)DeviceExtension + 5);
    if ( v15 == 2 )
    {
      DpiFdoResetFdo(DeviceObject);
    }
    else if ( v15 != 3 )
    {
      goto LABEL_57;
    }
    v16 = (struct _IO_WORKITEM *)*((_QWORD *)DeviceExtension + 346);
    if ( v16 )
    {
      IoFreeWorkItem(v16);
      *((_QWORD *)DeviceExtension + 346) = 0;
    }
    if ( DeviceExtension[1157] == 1 )
      DpiAcpiUnregisterAcpiCallbacks(DeviceObject);
    v17 = (void (__fastcall *)(_QWORD))*((_QWORD *)DeviceExtension + 73);
    if ( v17 )
    {
      v17(*((_QWORD *)DeviceExtension + 71));
      memset(DeviceExtension + 560, 0, 0x40u);
    }
    v18 = (void (__fastcall *)(_QWORD))*((_QWORD *)DeviceExtension + 81);
    if ( v18 )
    {
      v18(*((_QWORD *)DeviceExtension + 79));
      *((_OWORD *)DeviceExtension + 39) = 0;
      *((_OWORD *)DeviceExtension + 40) = 0;
      *((_OWORD *)DeviceExtension + 41) = 0;
    }
    v19 = (void (__fastcall *)(_QWORD))*((_QWORD *)DeviceExtension + 87);
    if ( v19 )
    {
      v19(*((_QWORD *)DeviceExtension + 85));
      memset(DeviceExtension + 672, 0, 0xB8u);
    }
    v20 = (void (__fastcall *)(_QWORD))*((_QWORD *)DeviceExtension + 110);
    if ( v20 )
    {
      v20(*((_QWORD *)DeviceExtension + 108));
      memset(DeviceExtension + 856, 0, 0x58u);
    }
    RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 32);
    RtlFreeUnicodeString((PUNICODE_STRING)DeviceExtension + 33);
    KeSetEvent((PRKEVENT)(DeviceExtension + 1288), 0, 0);
  }
LABEL_57:
  ++Irp->CurrentLocation;
  ++Irp->Tail.Overlay.CurrentStackLocation;
  Irp->IoStatus.Status = 0;
  v21 = IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 20), Irp);
  DpiDxgkDdiRemoveDevice(v5, *((_QWORD *)DeviceExtension + 6));
  if ( DeviceExtension )
  {
    if ( *((_DWORD *)DeviceExtension + 4) == 1953656900 && *((_DWORD *)DeviceExtension + 5) == 2 )
    {
      v22 = DeviceObject->DeviceExtension;
      v23 = (struct SYSMM_ADAPTER *)*((_QWORD *)v22 + 728);
      if ( v23 )
      {
        SysMmDestroyAdapter(v23);
        *((_QWORD *)v22 + 728) = 0;
      }
    }
  }
  IoDetachDevice(*((PDEVICE_OBJECT *)DeviceExtension + 20));
  IoDeleteDevice(DeviceObject);
  return v21;
}

```

## disassembly

```asm
0x1402a64a0  push    rbx
0x1402a64a2  push    rbp
0x1402a64a3  push    rsi
0x1402a64a4  push    rdi
0x1402a64a5  push    r14
0x1402a64a7  push    r15
0x1402a64a9  sub     rsp, 38h
0x1402a64ad  mov     rbx, [rcx+40h]
0x1402a64b1  mov     rbp, rdx
0x1402a64b4  mov     rdi, rcx
0x1402a64b7  mov     r14, [rbx+28h]
0x1402a64bb  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x1402a64c0  xor     r15d, r15d
0x1402a64c3  cmp     cs:qword_14015F078, rdi
0x1402a64ca  jnz     short loc_1402A64F4
0x1402a64cc  mov     rdx, 0FFFFFFFFC00000BBh
0x1402a64d3  lea     ecx, [r15+2]
0x1402a64d7  call    cs:__imp_WdLogSingleEntry1
0x1402a64de  nop     dword ptr [rax+rax+00h]
0x1402a64e3  mov     cs:WdLogGlobalForLineNumber, 1B37h
0x1402a64ed  mov     cs:qword_14015F078, r15
0x1402a64f4  call    ?ReleaseMiniportListMutex@@YAXXZ; ReleaseMiniportListMutex(void)
0x1402a64f9  mov     esi, 74727044h
0x1402a64fe  test    rbx, rbx
0x1402a6501  jz      short loc_1402A653E
0x1402a6503  cmp     [rbx+10h], esi
0x1402a6506  jnz     short loc_1402A653E
0x1402a6508  mov     eax, [rbx+14h]
0x1402a650b  sub     eax, 2
0x1402a650e  cmp     eax, 1
0x1402a6511  ja      short loc_1402A652B
0x1402a6513  mov     eax, [rbx+0F0h]
0x1402a6519  dec     eax
0x1402a651b  cmp     eax, 1
0x1402a651e  ja      short loc_1402A652B
0x1402a6520  mov     rdx, rbp
0x1402a6523  mov     rcx, rdi
0x1402a6526  call    DpiFdoHandleStopDevice
0x1402a652b  cmp     [rbx+10h], esi
0x1402a652e  jnz     short loc_1402A653E
0x1402a6530  cmp     dword ptr [rbx+14h], 2
0x1402a6534  jnz     short loc_1402A653E
0x1402a6536  mov     rcx, rdi
0x1402a6539  call    DpiPdoDestroyPendingPdoObjects
0x1402a653e  lea     rcx, [rbx+40h]; RemoveLock
0x1402a6542  mov     r8d, 20h ; ' '; RemlockSize
0x1402a6548  mov     rdx, rbp; Tag
0x1402a654b  call    cs:__imp_IoReleaseRemoveLockAndWaitEx
0x1402a6552  nop     dword ptr [rax+rax+00h]
0x1402a6557  test    rbx, rbx
0x1402a655a  jz      short loc_1402A656F
0x1402a655c  cmp     [rbx+10h], esi
0x1402a655f  jnz     short loc_1402A656F
0x1402a6561  cmp     dword ptr [rbx+14h], 2
0x1402a6565  jnz     short loc_1402A656F
0x1402a6567  mov     rcx, rdi
0x1402a656a  call    DpiFdoRemoveChildDescriptors
0x1402a656f  mov     ecx, [rbx+114h]
0x1402a6575  mov     eax, [rbx+0F0h]
0x1402a657b  and     ecx, 7
0x1402a657e  mov     [rbx+rcx*4+0F4h], eax
0x1402a6585  mov     eax, [rbx+0ECh]
0x1402a658b  inc     dword ptr [rbx+114h]
0x1402a6591  mov     [rbx+0F0h], eax
0x1402a6597  mov     dword ptr [rbx+0ECh], 7
0x1402a65a1  call    ?AcquireMiniportListMutex@@YAXXZ; AcquireMiniportListMutex(void)
0x1402a65a6  mov     rcx, rdi
0x1402a65a9  call    DpiFdoIsPostDevice
0x1402a65ae  test    al, al
0x1402a65b0  jz      short loc_1402A65B9
0x1402a65b2  mov     cs:qword_14015F080, r15
0x1402a65b9  call    DpiFdoIsMsBddAnchoredDevice
0x1402a65be  test    al, al
0x1402a65c0  jz      short loc_1402A65C9
0x1402a65c2  mov     cs:qword_14015F128, r15
0x1402a65c9  call    ?ReleaseMiniportListMutex@@YAXXZ; ReleaseMiniportListMutex(void)
0x1402a65ce  xor     r9d, r9d; Alertable
0x1402a65d1  mov     [rsp+68h+Timeout], r15; Timeout
0x1402a65d6  xor     r8d, r8d; WaitMode
0x1402a65d9  lea     rcx, [r14+48h]; Object
0x1402a65dd  xor     edx, edx; WaitReason
0x1402a65df  call    cs:__imp_KeWaitForSingleObject
0x1402a65e6  nop     dword ptr [rax+rax+00h]
0x1402a65eb  mov     rcx, [rbx]
0x1402a65ee  cmp     [rcx+8], rbx
0x1402a65f2  jnz     loc_1402A68E8
0x1402a65f8  mov     rax, [rbx+8]
0x1402a65fc  cmp     [rax], rbx
0x1402a65ff  jnz     loc_1402A68E8
0x1402a6605  mov     [rax], rcx
0x1402a6608  mov     [rcx+8], rax
0x1402a660c  dec     dword ptr [r14+80h]
0x1402a6613  mov     rcx, [rbx+0A8h]; Resource
0x1402a661a  cmp     dword ptr [rcx+68h], 1
0x1402a661e  jnz     short loc_1402A664D
0x1402a6620  call    cs:__imp_ExDeleteResourceLite
0x1402a6627  nop     dword ptr [rax+rax+00h]
0x1402a662c  mov     rcx, [rbx+0A8h]; P
0x1402a6633  test    rcx, rcx
0x1402a6636  jz      short loc_1402A664D
0x1402a6638  xor     edx, edx; Tag
0x1402a663a  call    cs:__imp_ExFreePoolWithTag
0x1402a6641  nop     dword ptr [rax+rax+00h]
0x1402a6646  mov     [rbx+0A8h], r15
0x1402a664d  test    rbx, rbx
0x1402a6650  jz      loc_1402A66F6
0x1402a6656  cmp     [rbx+10h], esi
0x1402a6659  jnz     loc_1402A66F6
0x1402a665f  mov     eax, [rbx+14h]
0x1402a6662  sub     eax, 2
0x1402a6665  cmp     eax, 1
0x1402a6668  ja      loc_1402A66F6
0x1402a666e  mov     rcx, [rbx+5C8h]; P
0x1402a6675  cmp     dword ptr [rcx+8], 1
0x1402a6679  jnz     short loc_1402A6695
0x1402a667b  test    rcx, rcx
0x1402a667e  jz      short loc_1402A6695
0x1402a6680  xor     edx, edx; Tag
0x1402a6682  call    cs:__imp_ExFreePoolWithTag
0x1402a6689  nop     dword ptr [rax+rax+00h]
0x1402a668e  mov     [rbx+5C8h], r15
0x1402a6695  mov     rcx, [rbx+5D0h]; P
0x1402a669c  cmp     dword ptr [rcx+8], 1
0x1402a66a0  jnz     short loc_1402A66BC
0x1402a66a2  test    rcx, rcx
0x1402a66a5  jz      short loc_1402A66BC
0x1402a66a7  xor     edx, edx; Tag
0x1402a66a9  call    cs:__imp_ExFreePoolWithTag
0x1402a66b0  nop     dword ptr [rax+rax+00h]
0x1402a66b5  mov     [rbx+5D0h], r15
0x1402a66bc  cmp     [rbx+1F8h], r15d
0x1402a66c3  jz      short loc_1402A66CD
0x1402a66c5  mov     rcx, rdi
0x1402a66c8  call    DpiLdaUnLinkDeviceFromChain
0x1402a66cd  mov     rcx, [rbx+458h]; P
0x1402a66d4  test    rcx, rcx
0x1402a66d7  jz      short loc_1402A66EE
0x1402a66d9  xor     edx, edx; Tag
0x1402a66db  call    cs:__imp_ExFreePoolWithTag
0x1402a66e2  nop     dword ptr [rax+rax+00h]
0x1402a66e7  mov     [rbx+458h], r15
0x1402a66ee  mov     rcx, rbx
0x1402a66f1  call    DpiCheckSpbResourceLeakage
0x1402a66f6  xor     edx, edx; Wait
0x1402a66f8  lea     rcx, [r14+48h]; Mutex
0x1402a66fc  call    cs:__imp_KeReleaseMutex
0x1402a6703  nop     dword ptr [rax+rax+00h]
0x1402a6708  test    rbx, rbx
0x1402a670b  jz      loc_1402A6853
0x1402a6711  cmp     [rbx+10h], esi
0x1402a6714  jnz     loc_1402A6853
0x1402a671a  mov     eax, [rbx+14h]
0x1402a671d  cmp     eax, 2
0x1402a6720  jz      short loc_1402A672D
0x1402a6722  cmp     eax, 3
0x1402a6725  jnz     loc_1402A6853
0x1402a672b  jmp     short loc_1402A6735
0x1402a672d  mov     rcx, rdi
0x1402a6730  call    DpiFdoResetFdo
0x1402a6735  mov     rcx, [rbx+0AD0h]; IoWorkItem
0x1402a673c  test    rcx, rcx
0x1402a673f  jz      short loc_1402A6754
0x1402a6741  call    cs:__imp_IoFreeWorkItem
0x1402a6748  nop     dword ptr [rax+rax+00h]
0x1402a674d  mov     [rbx+0AD0h], r15
0x1402a6754  cmp     byte ptr [rbx+485h], 1
0x1402a675b  jnz     short loc_1402A6765
0x1402a675d  mov     rcx, rdi
0x1402a6760  call    DpiAcpiUnregisterAcpiCallbacks
0x1402a6765  lea     rsi, [rbx+230h]
0x1402a676c  mov     rax, [rsi+18h]
0x1402a6770  test    rax, rax
0x1402a6773  jz      short loc_1402A678F
0x1402a6775  mov     rcx, [rbx+238h]
0x1402a677c  call    _guard_dispatch_icall
0x1402a6781  xor     edx, edx; Val
0x1402a6783  mov     rcx, rsi; void *
0x1402a6786  lea     r8d, [rdx+40h]; Size
0x1402a678a  call    memset
0x1402a678f  mov     rax, [rbx+288h]
0x1402a6796  test    rax, rax
0x1402a6799  jz      short loc_1402A67BF
0x1402a679b  mov     rcx, [rbx+278h]
0x1402a67a2  call    _guard_dispatch_icall
0x1402a67a7  xorps   xmm0, xmm0
0x1402a67aa  movups  xmmword ptr [rbx+270h], xmm0
0x1402a67b1  movups  xmmword ptr [rbx+280h], xmm0
0x1402a67b8  movups  xmmword ptr [rbx+290h], xmm0
0x1402a67bf  lea     rsi, [rbx+2A0h]
0x1402a67c6  mov     rax, [rsi+18h]
0x1402a67ca  test    rax, rax
0x1402a67cd  jz      short loc_1402A67EB
0x1402a67cf  mov     rcx, [rbx+2A8h]
0x1402a67d6  call    _guard_dispatch_icall
0x1402a67db  xor     edx, edx; Val
0x1402a67dd  mov     r8d, 0B8h; Size
0x1402a67e3  mov     rcx, rsi; void *
0x1402a67e6  call    memset
0x1402a67eb  lea     rsi, [rbx+358h]
0x1402a67f2  mov     rax, [rsi+18h]
0x1402a67f6  test    rax, rax
0x1402a67f9  jz      short loc_1402A6815
0x1402a67fb  mov     rcx, [rbx+360h]
0x1402a6802  call    _guard_dispatch_icall
0x1402a6807  xor     edx, edx; Val
0x1402a6809  mov     rcx, rsi; void *
0x1402a680c  lea     r8d, [rdx+58h]; Size
0x1402a6810  call    memset
0x1402a6815  lea     rcx, [rbx+200h]; UnicodeString
0x1402a681c  call    cs:__imp_RtlFreeUnicodeString
0x1402a6823  nop     dword ptr [rax+rax+00h]
0x1402a6828  lea     rcx, [rbx+210h]; UnicodeString
0x1402a682f  call    cs:__imp_RtlFreeUnicodeString
0x1402a6836  nop     dword ptr [rax+rax+00h]
0x1402a683b  lea     rcx, [rbx+508h]; Event
0x1402a6842  xor     r8d, r8d; Wait
0x1402a6845  xor     edx, edx; Increment
0x1402a6847  call    cs:__imp_KeSetEvent
0x1402a684e  nop     dword ptr [rax+rax+00h]
0x1402a6853  inc     byte ptr [rbp+43h]
0x1402a6856  mov     rdx, rbp; Irp
0x1402a6859  add     qword ptr [rbp+0B8h], 48h ; 'H'
0x1402a6861  mov     [rbp+30h], r15d
0x1402a6865  mov     rcx, [rbx+0A0h]; DeviceObject
0x1402a686c  call    cs:__imp_IofCallDriver
0x1402a6873  nop     dword ptr [rax+rax+00h]
0x1402a6878  mov     rdx, [rbx+30h]
0x1402a687c  mov     rcx, r14
0x1402a687f  mov     ebp, eax
0x1402a6881  call    DpiDxgkDdiRemoveDevice
0x1402a6886  test    rbx, rbx
0x1402a6889  jz      short loc_1402A68B6
0x1402a688b  cmp     dword ptr [rbx+10h], 74727044h
0x1402a6892  jnz     short loc_1402A68B6
0x1402a6894  cmp     dword ptr [rbx+14h], 2
0x1402a6898  jnz     short loc_1402A68B6
0x1402a689a  mov     rsi, [rdi+40h]
0x1402a689e  mov     rcx, [rsi+16C0h]; struct SYSMM_ADAPTER *
0x1402a68a5  test    rcx, rcx
0x1402a68a8  jz      short loc_1402A68B6
0x1402a68aa  call    ?SysMmDestroyAdapter@@YAXPEAUSYSMM_ADAPTER@@@Z; SysMmDestroyAdapter(SYSMM_ADAPTER *)
0x1402a68af  mov     [rsi+16C0h], r15
0x1402a68b6  mov     rcx, [rbx+0A0h]; TargetDevice
0x1402a68bd  call    cs:__imp_IoDetachDevice
0x1402a68c4  nop     dword ptr [rax+rax+00h]
0x1402a68c9  mov     rcx, rdi; DeviceObject
0x1402a68cc  call    cs:__imp_IoDeleteDevice
0x1402a68d3  nop     dword ptr [rax+rax+00h]
0x1402a68d8  mov     eax, ebp
0x1402a68da  add     rsp, 38h
0x1402a68de  pop     r15
0x1402a68e0  pop     r14
0x1402a68e2  pop     rdi
0x1402a68e3  pop     rsi
0x1402a68e4  pop     rbp
0x1402a68e5  pop     rbx
0x1402a68e6  retn
0x1402a68e8  mov     ecx, 3
0x1402a68ed  int     29h; Win8: RtlFailFast(ecx)
```
