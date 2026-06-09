# CscStorepLowIoReadWriteFileIrpEx

- ea: `0x140006a00`
- end: `0x140007220`
- name: `CscStorepLowIoReadWriteFileIrpEx`
- size: `2080`
- prototype: `__int64 __fastcall(PFILE_OBJECT FileObject, unsigned __int8, char, __int64, unsigned int, ULONG Length, void *, __int64, unsigned int *)`
- caller_count: `6`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140005980`
- `0x1400062a0`
- `0x1400065e0`
- `0x140006870`
- `0x1400074bc`
- `0x1400164e0`

## callees

- `0x140006a00`
- `0x14000c5f8`
- `0x140018930`
- `0x14001a494`
- `0x14001ac1c`
- `0x14002a298`
- `0x14002f010`
- `0x14002f0f0`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140006cb7`
- `ntoskrnl!KeInitializeEvent` at `0x140007053`
- `ntoskrnl!KeInitializeEvent` at `0x140006cb7`
- `ntoskrnl!KeInitializeEvent` at `0x140007053`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140006d02`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140006d02`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006e4e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140006e4e`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140006fa0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140006fa0`
- `ntoskrnl!IoAllocateMdl` at `0x140006b59`
- `ntoskrnl!IoAllocateMdl` at `0x140006b59`
- `ntoskrnl!IoFreeMdl` at `0x140006e96`
- `ntoskrnl!IoFreeMdl` at `0x140006e96`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140006d6a`
- `ntoskrnl!KeAreAllApcsDisabled` at `0x140006d6a`
- `ntoskrnl!IoFreeIrp` at `0x140006eae`
- `ntoskrnl!IoFreeIrp` at `0x140006eae`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x1400070a4`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x1400070d4`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x1400070a4`
- `ntoskrnl!KeSetKernelStackSwapEnable` at `0x1400070d4`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140006f4a`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140006f4a`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140006ce7`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140006ce7`
- `ntoskrnl!IoAllocateIrpEx` at `0x140006b1e`
- `ntoskrnl!IoAllocateIrpEx` at `0x140006b1e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006d13`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006e25`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006d13`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140006e25`
- `ntoskrnl!IoSetIoPriorityHint` at `0x140006c84`
- `ntoskrnl!IoSetIoPriorityHint` at `0x140006c84`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x140006c6a`
- `ntoskrnl!IoRetrievePriorityInfo` at `0x140006c6a`
- `ntoskrnl!MmProbeAndLockPages` at `0x140006b97`
- `ntoskrnl!MmProbeAndLockPages` at `0x140006b97`
- `ntoskrnl!IoGetStackLimits` at `0x140006de3`
- `ntoskrnl!IoGetStackLimits` at `0x140006de3`
- `ntoskrnl!MmUnlockPages` at `0x140006e87`
- `ntoskrnl!MmUnlockPages` at `0x140006e87`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140006af9`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x140006af9`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoReadWriteFileIrpEx(
        PFILE_OBJECT FileObject,
        unsigned __int8 a2,
        char a3,
        __int64 a4,
        unsigned int a5,
        ULONG Length,
        void *a7,
        __int64 a8,
        unsigned int *a9)
{
  __int64 v10; // r8
  __int64 v12; // r15
  __int64 Irp; // rbx
  unsigned int v14; // r13d
  char v15; // dl
  unsigned int v16; // r12d
  PDEVICE_OBJECT RelatedDeviceObject; // r13
  struct _MDL *Mdl; // rax
  __int64 v19; // rdi
  struct _MDL *v20; // r12
  NTSTATUS Blink; // edi
  IRP *TopLevelIrp; // rsi
  BOOLEAN v23; // di
  int v24; // r15d
  NTSTATUS v26; // eax
  BOOLEAN v27; // r15
  __int64 v28; // rcx
  __int64 v29; // rdx
  char v30; // al
  char v31; // [rsp+60h] [rbp-138h]
  PVOID VirtualAddress; // [rsp+70h] [rbp-128h] BYREF
  struct _MDL *v35; // [rsp+78h] [rbp-120h]
  PIRP v36; // [rsp+80h] [rbp-118h]
  __int64 v37; // [rsp+88h] [rbp-110h]
  unsigned __int64 HighLimit; // [rsp+90h] [rbp-108h] BYREF
  unsigned int *v39; // [rsp+98h] [rbp-100h]
  struct _KEVENT Event; // [rsp+A0h] [rbp-F8h] BYREF
  __int128 CurrentThread; // [rsp+C0h] [rbp-D8h] BYREF
  __int128 v42; // [rsp+D0h] [rbp-C8h]
  __int128 v43; // [rsp+E0h] [rbp-B8h]
  __int128 v44; // [rsp+F0h] [rbp-A8h]
  __int128 v45; // [rsp+100h] [rbp-98h]
  __int128 v46; // [rsp+110h] [rbp-88h]
  __int128 v47; // [rsp+120h] [rbp-78h]
  __int128 v48; // [rsp+130h] [rbp-68h]
  __int128 v49; // [rsp+140h] [rbp-58h]
  struct _KEVENT PriorityInfo; // [rsp+150h] [rbp-48h] BYREF

  v37 = a4;
  v10 = a2;
  VirtualAddress = a7;
  v12 = a8;
  v39 = a9;
  Irp = 0;
  v14 = 0;
  memset(&Event, 0, sizeof(Event));
  v35 = 0;
  v15 = 0;
  v31 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    v29 = 89;
    v30 = 89;
    LODWORD(v36) = 78;
    if ( !a3 )
      v30 = (char)v36;
    if ( !(_BYTE)v10 )
      v29 = (unsigned int)v36;
    v16 = a5;
    WPP_SF_qcciDDqqq(
      WPP_GLOBAL_Control->AttachedDevice,
      v29,
      v10,
      FileObject,
      (_BYTE)v29,
      v30,
      a4,
      a5,
      Length,
      a7,
      a8,
      a9);
    a4 = v37;
    v15 = 0;
  }
  else
  {
    v16 = a5;
  }
  if ( FileObject )
  {
    if ( v16 )
    {
      if ( Length )
      {
        if ( Length < v16 )
        {
          Blink = -1073741811;
          v24 = 1350;
          v20 = 0;
        }
        else
        {
          if ( a4 >= 0 )
          {
            RelatedDeviceObject = IoGetRelatedDeviceObject(FileObject);
            if ( (RelatedDeviceObject->Flags & 4) != 0 )
            {
              Blink = -1073741808;
              v24 = 1366;
              v20 = 0;
              v14 = 0;
            }
            else
            {
              Irp = IoAllocateIrpEx(RelatedDeviceObject, (unsigned __int8)RelatedDeviceObject->StackSize, 0);
              v36 = (PIRP)Irp;
              if ( Irp )
              {
                if ( !a8 )
                {
                  Mdl = IoAllocateMdl(VirtualAddress, Length, 0, 0, 0);
                  v35 = Mdl;
                  *(_QWORD *)&PriorityInfo.Header.Lock = Mdl;
                  if ( !Mdl )
                  {
                    Blink = -1073741670;
                    v24 = 1414;
                    v20 = 0;
                    v14 = 0;
                    goto LABEL_32;
                  }
                  if ( a3 )
                  {
                    MmBuildMdlForNonPagedPool(Mdl);
                  }
                  else
                  {
                    MmProbeAndLockPages(Mdl, 0, (LOCK_OPERATION)(a2 == 0));
                    v31 = 1;
                  }
                }
                *(_QWORD *)(Irp + 192) = FileObject;
                *(_QWORD *)(Irp + 152) = KeGetCurrentThread();
                v19 = *(_QWORD *)(Irp + 184);
                *(_BYTE *)(v19 - 72) = (a2 != 0) + 3;
                *(_QWORD *)(v19 - 24) = FileObject;
                *(_DWORD *)(v19 - 64) = v16;
                *(_QWORD *)(v19 - 48) = v37;
                *(_DWORD *)(v19 - 56) = 0;
                *(_BYTE *)(Irp + 64) = 0;
                *(_QWORD *)(Irp + 112) = VirtualAddress;
                v20 = v35;
                if ( !a8 )
                  v12 = (__int64)v35;
                *(_QWORD *)(Irp + 8) = v12;
                PriorityInfo.Header.LockNV = 16;
                *(_QWORD *)&PriorityInfo.Header.SignalState = 0xFFFF;
                HIDWORD(PriorityInfo.Header.WaitListHead.Flink) = 2;
                if ( IoRetrievePriorityInfo(0, 0, KeGetCurrentThread(), (PIO_PRIORITY_INFO)&PriorityInfo) >= 0 )
                  IoSetIoPriorityHint((PIRP)Irp, SHIDWORD(PriorityInfo.Header.WaitListHead.Flink));
                if ( (FileObject->Flags & 8) != 0 )
                  *(_DWORD *)(Irp + 16) |= 1u;
                if ( a2 && (FileObject->Flags & 0x10) != 0 )
                  *(_BYTE *)(v19 - 70) |= 4u;
                KeInitializeEvent(&Event, NotificationEvent, 0);
                Blink = IoSetCompletionRoutineEx(
                          RelatedDeviceObject,
                          (PIRP)Irp,
                          CscStorepLowIoIrpCompletionRoutine,
                          &Event,
                          1u,
                          1u,
                          1u);
                if ( Blink >= 0 )
                {
                  TopLevelIrp = IoGetTopLevelIrp();
                  IoSetTopLevelIrp(0);
                  CurrentThread = 0;
                  v42 = 0;
                  v43 = 0;
                  v44 = 0;
                  v45 = 0;
                  v46 = 0;
                  v47 = 0;
                  v48 = 0;
                  v49 = 0;
                  v23 = KeAreAllApcsDisabled();
                  if ( v23
                    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
                  {
                    WPP_SF_qD(
                      WPP_GLOBAL_Control->AttachedDevice,
                      19,
                      WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
                      Irp,
                      a2);
                  }
                  *((_QWORD *)&v43 + 1) = RelatedDeviceObject;
                  *(_QWORD *)&v44 = Irp;
                  BYTE8(v44) = a2;
                  if ( v23 )
                  {
                    memset(&PriorityInfo, 0, sizeof(PriorityInfo));
                    KeInitializeEvent(&PriorityInfo, NotificationEvent, 0);
                    CurrentThread = (unsigned __int64)KeGetCurrentThread();
                    *(_QWORD *)&v42 = CscStorepLowIoReadWriteFilePostedRoutine;
                    DWORD2(v42) = -1;
                    *(_QWORD *)&v43 = &PriorityInfo;
                    v27 = KeSetKernelStackSwapEnable(0);
                    Blink = CscStorepLowIoPostWorkItemAndWait(v28, &CurrentThread, &PriorityInfo);
                    if ( v27 )
                      KeSetKernelStackSwapEnable(v27);
                    if ( Blink >= 0 )
                      Blink = DWORD2(v42);
                    goto LABEL_27;
                  }
                  PriorityInfo.Header.WaitListHead.Blink = 0;
                  PriorityInfo.Header.WaitListHead.Flink = (struct _LIST_ENTRY *)&CurrentThread;
                  *(_QWORD *)&PriorityInfo.Header.Lock = CscStorepLowIoReadWriteFilePostedRoutine;
                  HighLimit = 0;
                  VirtualAddress = 0;
                  IoGetStackLimits((PULONG_PTR)&VirtualAddress, &HighLimit);
                  if ( (char *)&HighLimit - (_BYTE *)VirtualAddress < (unsigned __int64)(unsigned int)dword_14003BD20 )
                  {
                    v26 = KeExpandKernelStackAndCalloutEx(CscStorepLowIoPost_Callout, &PriorityInfo, 0x6000u, 0, 0);
                    if ( v26 >= 0 )
                    {
                      Blink = (NTSTATUS)PriorityInfo.Header.WaitListHead.Blink;
                      goto LABEL_27;
                    }
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        11,
                        WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
                        (unsigned int)v26);
                    }
                  }
                  Blink = (*(__int64 (__fastcall **)(struct _LIST_ENTRY *))&PriorityInfo.Header.Lock)(PriorityInfo.Header.WaitListHead.Flink);
LABEL_27:
                  IoSetTopLevelIrp(TopLevelIrp);
                  if ( Blink == 259 )
                  {
                    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
                    Blink = *(_DWORD *)(Irp + 48);
                  }
                  if ( (Blink & 0xC0000000) == 0xC0000000 )
                    v14 = 0;
                  else
                    v14 = *(_DWORD *)(Irp + 56);
                  v24 = 0;
                  goto LABEL_32;
                }
                v24 = 1522;
                v14 = 0;
              }
              else
              {
                Blink = -1073741670;
                v24 = 1378;
                v20 = 0;
                v14 = 0;
              }
            }
LABEL_32:
            v15 = v31;
            goto LABEL_33;
          }
          Blink = -1073741811;
          v24 = 1356;
          v20 = 0;
        }
      }
      else
      {
        Blink = -1073741811;
        v24 = 1344;
        v20 = 0;
      }
    }
    else
    {
      Blink = -1073741811;
      v24 = 1338;
      v20 = 0;
    }
  }
  else
  {
    Blink = -1073741811;
    v24 = 1332;
    v20 = 0;
  }
LABEL_33:
  if ( v20 )
  {
    if ( v15 )
      MmUnlockPages(*(PMDL *)(Irp + 8));
    IoFreeMdl(v20);
  }
  if ( Irp )
  {
    *(_QWORD *)(Irp + 8) = 0;
    IoFreeIrp((PIRP)Irp);
  }
  *v39 = v14;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_0d06f681978d342119bb40210e69c50f_Traceguids, v14, Blink, v24);
  return (unsigned int)Blink;
}

```

## disassembly

```asm
0x140006a00  mov     [rsp+arg_10], rbx
0x140006a05  mov     [rsp+arg_18], rsi
0x140006a0a  push    rdi
0x140006a0b  push    r12
0x140006a0d  push    r13
0x140006a0f  push    r14
0x140006a11  push    r15
0x140006a13  sub     rsp, 170h
0x140006a1a  mov     rax, cs:__security_cookie
0x140006a21  xor     rax, rsp
0x140006a24  mov     [rsp+198h+var_30], rax
0x140006a2c  mov     [rsp+198h+var_110], r9
0x140006a34  movzx   r11d, r8b
0x140006a38  mov     [rsp+198h+var_130], r8b
0x140006a3d  movzx   r8d, dl
0x140006a41  mov     [rsp+198h+var_137], dl
0x140006a45  mov     rsi, rcx
0x140006a48  mov     edi, [rsp+198h+Length]
0x140006a4f  mov     r10, [rsp+198h+arg_30]
0x140006a57  mov     [rsp+198h+VirtualAddress], r10
0x140006a5c  mov     r15, [rsp+198h+arg_38]
0x140006a64  mov     r12, [rsp+198h+arg_40]
0x140006a6c  mov     [rsp+198h+var_100], r12
0x140006a74  xor     r14d, r14d
0x140006a77  mov     ebx, r14d
0x140006a7a  mov     r13d, r14d
0x140006a7d  mov     [rsp+198h+var_134], r14d
0x140006a82  xorps   xmm0, xmm0
0x140006a85  xor     eax, eax
0x140006a87  movups  xmmword ptr [rsp+198h+Event.Header], xmm0
0x140006a8f  mov     [rsp+198h+Event.Header.WaitListHead.Blink], rax
0x140006a97  mov     [rsp+198h+var_120], r14
0x140006a9c  xor     dl, dl
0x140006a9e  mov     [rsp+198h+var_138], dl
0x140006aa2  lea     rax, WPP_GLOBAL_Control
0x140006aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ab0  cmp     rcx, rax
0x140006ab3  jz      short loc_140006AC2
0x140006ab5  test    dword ptr [rcx+2Ch], 40000h
0x140006abc  jnz     loc_1400070F4
0x140006ac2  mov     r12d, [rsp+198h+arg_20]
0x140006aca  test    rsi, rsi
0x140006acd  jz      loc_140006F0C
0x140006ad3  test    r12d, r12d
0x140006ad6  jz      loc_140007167
0x140006adc  test    edi, edi
0x140006ade  jz      loc_14000717A
0x140006ae4  cmp     edi, r12d
0x140006ae7  jb      loc_14000718D
0x140006aed  test    r9, r9
0x140006af0  js      loc_1400071A0
0x140006af6  mov     rcx, rsi; FileObject
0x140006af9  call    cs:__imp_IoGetRelatedDeviceObject
0x140006b00  nop     dword ptr [rax+rax+00h]
0x140006b05  mov     r13, rax
0x140006b08  mov     eax, [rax+30h]
0x140006b0b  test    al, 4
0x140006b0d  jnz     loc_14000701B
0x140006b13  xor     r8d, r8d
0x140006b16  movzx   edx, byte ptr [r13+4Ch]
0x140006b1b  mov     rcx, r13
0x140006b1e  call    cs:__imp_IoAllocateIrpEx
0x140006b25  nop     dword ptr [rax+rax+00h]
0x140006b2a  mov     rbx, rax
0x140006b2d  mov     [rsp+198h+var_118], rax
0x140006b35  test    rax, rax
0x140006b38  jz      loc_1400071B3
0x140006b3e  test    r15, r15
0x140006b41  jnz     loc_140006BD2
0x140006b47  mov     [rsp+198h+Irp], r14; Irp
0x140006b4c  xor     r9d, r9d; ChargeQuota
0x140006b4f  xor     r8d, r8d; SecondaryBuffer
0x140006b52  mov     edx, edi; Length
0x140006b54  mov     rcx, [rsp+198h+VirtualAddress]; VirtualAddress
0x140006b59  call    cs:__imp_IoAllocateMdl
0x140006b60  nop     dword ptr [rax+rax+00h]
0x140006b65  mov     [rsp+198h+var_120], rax
0x140006b6a  mov     qword ptr [rsp+198h+PriorityInfo.Size], rax
0x140006b72  test    rax, rax
0x140006b75  jz      loc_1400071C9
0x140006b7b  cmp     [rsp+198h+var_130], r14b
0x140006b80  jnz     loc_140006F9D
0x140006b86  mov     r8d, r14d
0x140006b89  cmp     [rsp+198h+var_137], r14b
0x140006b8e  setz    r8b; Operation
0x140006b92  xor     edx, edx; AccessMode
0x140006b94  mov     rcx, rax; MemoryDescriptorList
0x140006b97  call    cs:__imp_MmProbeAndLockPages
0x140006b9e  nop     dword ptr [rax+rax+00h]
0x140006ba3  mov     [rsp+198h+var_138], 1
0x140006ba8  jmp     short loc_140006BD2
0x140006baa  mov     edi, eax
0x140006bac  mov     r15d, 599h
0x140006bb2  xor     r14d, r14d
0x140006bb5  mov     rbx, [rsp+198h+var_118]
0x140006bbd  mov     r13d, r14d
0x140006bc0  mov     r12, qword ptr [rsp+198h+PriorityInfo.Size]
0x140006bc8  movzx   edx, [rsp+198h+var_138]
0x140006bcd  jmp     loc_140006E7A
0x140006bd2  mov     [rbx+0C0h], rsi
0x140006bd9  mov     rax, gs:188h
0x140006be2  mov     [rbx+98h], rax
0x140006be9  mov     rdi, [rbx+0B8h]
0x140006bf0  cmp     [rsp+198h+var_137], 0
0x140006bf5  setnz   al
0x140006bf8  add     al, 3
0x140006bfa  mov     [rdi-48h], al
0x140006bfd  mov     [rdi-18h], rsi
0x140006c01  mov     [rdi-40h], r12d
0x140006c05  mov     rax, [rsp+198h+var_110]
0x140006c0d  mov     [rdi-30h], rax
0x140006c11  mov     [rdi-38h], r14d
0x140006c15  mov     byte ptr [rbx+40h], 0
0x140006c19  mov     rax, [rsp+198h+VirtualAddress]
0x140006c1e  mov     [rbx+70h], rax
0x140006c22  mov     r12, [rsp+198h+var_120]
0x140006c27  test    r15, r15
0x140006c2a  jnz     short loc_140006C2F
0x140006c2c  mov     r15, r12
0x140006c2f  mov     [rbx+8], r15
0x140006c33  mov     [rsp+198h+PriorityInfo.Size], 10h
0x140006c3e  mov     qword ptr [rsp+198h+PriorityInfo.ThreadPriority], 0FFFFh
0x140006c4a  mov     [rsp+198h+PriorityInfo.IoPriority], 2
0x140006c55  mov     r8, gs:188h; Thread
0x140006c5e  lea     r9, [rsp+198h+PriorityInfo]; PriorityInfo
0x140006c66  xor     edx, edx; FileObject
0x140006c68  xor     ecx, ecx; Irp
0x140006c6a  call    cs:__imp_IoRetrievePriorityInfo
0x140006c71  nop     dword ptr [rax+rax+00h]
0x140006c76  test    eax, eax
0x140006c78  js      short loc_140006C90
0x140006c7a  mov     edx, [rsp+198h+PriorityInfo.IoPriority]; PriorityHint
0x140006c81  mov     rcx, rbx; Irp
0x140006c84  call    cs:__imp_IoSetIoPriorityHint
0x140006c8b  nop     dword ptr [rax+rax+00h]
0x140006c90  mov     eax, [rsi+50h]
0x140006c93  test    al, 8
0x140006c95  jz      short loc_140006C9B
0x140006c97  or      dword ptr [rbx+10h], 1
0x140006c9b  movzx   r15d, [rsp+198h+var_137]
0x140006ca1  test    r15b, r15b
0x140006ca4  jnz     loc_140006FC1
0x140006caa  xor     r8d, r8d; State
0x140006cad  xor     edx, edx; Type
0x140006caf  lea     rcx, [rsp+198h+Event]; Event
0x140006cb7  call    cs:__imp_KeInitializeEvent
0x140006cbe  nop     dword ptr [rax+rax+00h]
0x140006cc3  mov     [rsp+198h+InvokeOnCancel], 1; InvokeOnCancel
0x140006cc8  mov     [rsp+198h+InvokeOnError], 1; InvokeOnError
0x140006ccd  mov     byte ptr [rsp+198h+Irp], 1; InvokeOnSuccess
0x140006cd2  lea     r9, [rsp+198h+Event]; Context
0x140006cda  lea     r8, CscStorepLowIoIrpCompletionRoutine; CompletionRoutine
0x140006ce1  mov     rdx, rbx; Irp
0x140006ce4  mov     rcx, r13; DeviceObject
0x140006ce7  call    cs:__imp_IoSetCompletionRoutineEx
0x140006cee  nop     dword ptr [rax+rax+00h]
0x140006cf3  mov     edi, eax
0x140006cf5  test    eax, eax
0x140006cf7  js      loc_140006FB1
0x140006cfd  mov     [rsp+198h+var_134], r14d
0x140006d02  call    cs:__imp_IoGetTopLevelIrp
0x140006d09  nop     dword ptr [rax+rax+00h]
0x140006d0e  mov     rsi, rax
0x140006d11  xor     ecx, ecx; Irp
0x140006d13  call    cs:__imp_IoSetTopLevelIrp
0x140006d1a  nop     dword ptr [rax+rax+00h]
0x140006d1f  xorps   xmm0, xmm0
0x140006d22  movups  [rsp+198h+var_D8], xmm0
0x140006d2a  movups  [rsp+198h+var_C8], xmm0
0x140006d32  movups  [rsp+198h+var_B8], xmm0
0x140006d3a  movups  [rsp+198h+var_A8], xmm0
0x140006d42  movups  [rsp+198h+var_98], xmm0
0x140006d4a  movups  [rsp+198h+var_88], xmm0
0x140006d52  movups  [rsp+198h+var_78], xmm0
0x140006d5a  movups  [rsp+198h+var_68], xmm0
0x140006d62  movups  [rsp+198h+var_58], xmm0
0x140006d6a  call    cs:__imp_KeAreAllApcsDisabled
0x140006d71  nop     dword ptr [rax+rax+00h]
0x140006d76  movzx   edi, al
0x140006d79  test    al, al
0x140006d7b  jnz     loc_140006FD5
0x140006d81  mov     qword ptr [rsp+198h+var_B8+8], r13
0x140006d89  mov     qword ptr [rsp+198h+var_A8], rbx
0x140006d91  mov     byte ptr [rsp+198h+var_A8+8], r15b
0x140006d99  test    dil, dil
0x140006d9c  jnz     loc_140007031
0x140006da2  mov     [rsp+198h+var_38], r14
0x140006daa  lea     rax, [rsp+198h+var_D8]
0x140006db2  mov     qword ptr [rsp+198h+PriorityInfo.PagePriority], rax
0x140006dba  lea     rax, CscStorepLowIoReadWriteFilePostedRoutine
0x140006dc1  mov     qword ptr [rsp+198h+PriorityInfo.Size], rax
0x140006dc9  mov     [rsp+198h+HighLimit], r14
0x140006dd1  mov     [rsp+198h+VirtualAddress], r14
0x140006dd6  lea     rdx, [rsp+198h+HighLimit]; HighLimit
0x140006dde  lea     rcx, [rsp+198h+VirtualAddress]; LowLimit
0x140006de3  call    cs:__imp_IoGetStackLimits
0x140006dea  nop     dword ptr [rax+rax+00h]
0x140006def  lea     rcx, [rsp+198h+HighLimit]
0x140006df7  sub     rcx, [rsp+198h+VirtualAddress]
0x140006dfc  mov     eax, cs:dword_14003BD20
0x140006e02  cmp     rcx, rax
0x140006e05  jb      loc_140006F2D
0x140006e0b  mov     rcx, qword ptr [rsp+198h+PriorityInfo.PagePriority]
0x140006e13  mov     rax, qword ptr [rsp+198h+PriorityInfo.Size]
0x140006e1b  call    _guard_dispatch_icall
0x140006e20  mov     edi, eax
0x140006e22  mov     rcx, rsi; Irp
0x140006e25  call    cs:__imp_IoSetTopLevelIrp
0x140006e2c  nop     dword ptr [rax+rax+00h]
0x140006e31  cmp     edi, 103h
0x140006e37  jnz     short loc_140006E5D
0x140006e39  mov     [rsp+198h+Irp], r14; Timeout
0x140006e3e  xor     r9d, r9d; Alertable
0x140006e41  xor     r8d, r8d; WaitMode
0x140006e44  xor     edx, edx; WaitReason
0x140006e46  lea     rcx, [rsp+198h+Event]; Object
0x140006e4e  call    cs:__imp_KeWaitForSingleObject
0x140006e55  nop     dword ptr [rax+rax+00h]
0x140006e5a  mov     edi, [rbx+30h]
0x140006e5d  mov     eax, edi
0x140006e5f  and     eax, 0C0000000h
0x140006e64  cmp     eax, 0C0000000h
0x140006e69  jnz     loc_140006F1F
0x140006e6f  mov     r13d, r14d
0x140006e72  mov     r15d, r14d
0x140006e75  movzx   edx, [rsp+198h+var_138]
0x140006e7a  test    r12, r12
0x140006e7d  jz      short loc_140006EA2
0x140006e7f  test    dl, dl
0x140006e81  jz      short loc_140006E93
0x140006e83  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140006e87  call    cs:__imp_MmUnlockPages
0x140006e8e  nop     dword ptr [rax+rax+00h]
0x140006e93  mov     rcx, r12; Mdl
0x140006e96  call    cs:__imp_IoFreeMdl
0x140006e9d  nop     dword ptr [rax+rax+00h]
0x140006ea2  test    rbx, rbx
0x140006ea5  jz      short loc_140006EBA
0x140006ea7  mov     [rbx+8], r14
0x140006eab  mov     rcx, rbx; Irp
0x140006eae  call    cs:__imp_IoFreeIrp
0x140006eb5  nop     dword ptr [rax+rax+00h]
0x140006eba  mov     rax, [rsp+198h+var_100]
0x140006ec2  mov     [rax], r13d
0x140006ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x140006ecc  lea     rax, WPP_GLOBAL_Control
0x140006ed3  cmp     rcx, rax
0x140006ed6  jnz     loc_140006F6A
0x140006edc  mov     eax, edi
0x140006ede  mov     rcx, [rsp+198h+var_30]
0x140006ee6  xor     rcx, rsp; StackCookie
0x140006ee9  call    __security_check_cookie
0x140006eee  lea     r11, [rsp+198h+var_28]
0x140006ef6  mov     rbx, [r11+40h]
0x140006efa  mov     rsi, [r11+48h]
0x140006efe  mov     rsp, r11
0x140006f01  pop     r15
0x140006f03  pop     r14
0x140006f05  pop     r13
0x140006f07  pop     r12
0x140006f09  pop     rdi
0x140006f0a  retn
0x140006f0c  mov     edi, 0C000000Dh
0x140006f11  mov     r15d, 534h
0x140006f17  mov     r12, r14
0x140006f1a  jmp     loc_140006E7A
0x140006f1f  mov     r13d, [rbx+38h]
0x140006f23  mov     r15d, [rsp+198h+var_134]
0x140006f28  jmp     loc_140006E75
0x140006f2d  mov     [rsp+198h+Irp], r14; Context
0x140006f32  xor     r9d, r9d; Wait
0x140006f35  mov     r8d, 6000h; Size
0x140006f3b  lea     rdx, [rsp+198h+PriorityInfo]; Parameter
0x140006f43  lea     rcx, CscStorepLowIoPost_Callout; Callout
0x140006f4a  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140006f51  nop     dword ptr [rax+rax+00h]
0x140006f56  test    eax, eax
0x140006f58  js      loc_1400071DF
0x140006f5e  mov     edi, dword ptr [rsp+198h+var_38]
0x140006f65  jmp     loc_140006E22
0x140006f6a  test    dword ptr [rcx+2Ch], 40000h
0x140006f71  jz      loc_140006EDC
0x140006f77  mov     edx, 15h
0x140006f7c  mov     dword ptr [rsp+198h+InvokeOnError], r15d
0x140006f81  mov     dword ptr [rsp+198h+Irp], edi
0x140006f85  mov     r9d, r13d
0x140006f88  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x140006f8f  mov     rcx, [rcx+18h]
0x140006f93  call    WPP_SF_DDd
0x140006f98  jmp     loc_140006EDC
0x140006f9d  mov     rcx, rax; MemoryDescriptorList
0x140006fa0  call    cs:__imp_MmBuildMdlForNonPagedPool
0x140006fa7  nop     dword ptr [rax+rax+00h]
0x140006fac  jmp     loc_140006BD2
0x140006fb1  mov     r15d, 5F2h
0x140006fb7  mov     r13d, [rsp+198h+var_134]
0x140006fbc  jmp     loc_140006E75
0x140006fc1  mov     eax, [rsi+50h]
0x140006fc4  test    al, 10h
0x140006fc6  jz      loc_140006CAA
  ... truncated ...
```
