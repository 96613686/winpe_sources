# CClfsContainer::ReadSector(_KEVENT *,IClfsRequestAsync *,_CLFS_IO_WORKITEM *,_CLFS_READ_BUFFER const &,ulong,unsigned __int64 const &)

- ea: `0x14006b4e8`
- end: `0x14006bc7d`
- name: `?ReadSector@CClfsContainer@@QEAAJPEAU_KEVENT@@PEAUIClfsRequestAsync@@PEAU_CLFS_IO_WORKITEM@@AEBU_CLFS_READ_BUFFER@@KAEB_K@Z`
- size: `1941`
- prototype: `__int64 __usercall@<rax>(ULONG_PTR BugCheckParameter3@<rcx>, PRKEVENT Event@<rdx>, struct IClfsRequestAsync *@<r8>, struct _CLFS_IO_WORKITEM *@<r9>, const struct _CLFS_READ_BUFFER *, unsigned int, const unsigned __int64 *)`
- caller_count: `7`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14001091c`
- `0x14003e7d4`
- `0x14003f568`
- `0x14003fb8c`
- `0x14006a3a0`
- `0x14006a520`
- `0x14006b3fc`

## callees

- `0x140008330`
- `0x14000c25c`
- `0x14000ed64`
- `0x140017f20`
- `0x14006b4e8`
- `0x14006bc84`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x14006b548`
- `ntoskrnl!ObfReferenceObject` at `0x14006bbf3`
- `ntoskrnl!ObfReferenceObject` at `0x14006b548`
- `ntoskrnl!ObfReferenceObject` at `0x14006bbf3`
- `ntoskrnl!ObfDereferenceObject` at `0x14006bb93`
- `ntoskrnl!ObfDereferenceObject` at `0x14006bba7`
- `ntoskrnl!ObfDereferenceObject` at `0x14007b641`
- `ntoskrnl!ObfDereferenceObject` at `0x14007b655`
- `ntoskrnl!ObfDereferenceObject` at `0x14006bb93`
- `ntoskrnl!ObfDereferenceObject` at `0x14006bba7`
- `ntoskrnl!ObfDereferenceObject` at `0x14007b641`
- `ntoskrnl!ObfDereferenceObject` at `0x14007b655`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006b85f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14006b85f`
- `ntoskrnl!KeClearEvent` at `0x14006bc02`
- `ntoskrnl!KeClearEvent` at `0x14006bc02`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006b559`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14006b559`
- `ntoskrnl!KeBugCheckEx` at `0x14006b8a5`
- `ntoskrnl!KeBugCheckEx` at `0x14006b8cb`
- `ntoskrnl!KeBugCheckEx` at `0x14006ba4c`
- `ntoskrnl!KeBugCheckEx` at `0x14006ba78`
- `ntoskrnl!KeBugCheckEx` at `0x14006bc25`
- `ntoskrnl!KeBugCheckEx` at `0x14007b5c2`
- `ntoskrnl!KeBugCheckEx` at `0x14006b8a5`
- `ntoskrnl!KeBugCheckEx` at `0x14006b8cb`
- `ntoskrnl!KeBugCheckEx` at `0x14006ba4c`
- `ntoskrnl!KeBugCheckEx` at `0x14006ba78`
- `ntoskrnl!KeBugCheckEx` at `0x14006bc25`
- `ntoskrnl!KeBugCheckEx` at `0x14007b5c2`
- `ntoskrnl!IoAllocateIrpEx` at `0x14006b696`
- `ntoskrnl!IoAllocateIrpEx` at `0x14006b696`
- `ntoskrnl!IoAllocateMdl` at `0x14006b74f`
- `ntoskrnl!IoAllocateMdl` at `0x14006baa5`
- `ntoskrnl!IoAllocateMdl` at `0x14006b74f`
- `ntoskrnl!IoAllocateMdl` at `0x14006baa5`
- `ntoskrnl!IoBuildPartialMdl` at `0x14006badc`
- `ntoskrnl!IoBuildPartialMdl` at `0x14006badc`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006b775`
- `ntoskrnl!MmProbeAndLockPages` at `0x14006b775`
- `ntoskrnl!IofCallDriver` at `0x14006b838`
- `ntoskrnl!IofCallDriver` at `0x14006b922`
- `ntoskrnl!IofCallDriver` at `0x14006bb2e`
- `ntoskrnl!IofCallDriver` at `0x14006b838`
- `ntoskrnl!IofCallDriver` at `0x14006b922`
- `ntoskrnl!IofCallDriver` at `0x14006bb2e`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006b87c`
- `ntoskrnl!KeGetCurrentIrql` at `0x14006b87c`
- `ntoskrnl!IoFreeIrp` at `0x14006bbe2`
- `ntoskrnl!IoFreeIrp` at `0x14007b5e4`
- `ntoskrnl!IoFreeIrp` at `0x14006bbe2`
- `ntoskrnl!IoFreeIrp` at `0x14007b5e4`
- `ntoskrnl!IoQueueWorkItem` at `0x14006bc4b`
- `ntoskrnl!IoQueueWorkItem` at `0x14007b623`
- `ntoskrnl!IoQueueWorkItem` at `0x14006bc4b`
- `ntoskrnl!IoQueueWorkItem` at `0x14007b623`

## string_xrefs

- `0x14006ba1b`: `CClfsContainer::ReadSector`

## pseudocode

```c
__int64 __fastcall CClfsContainer::ReadSector(
        PVOID *BugCheckParameter3,
        PRKEVENT Event,
        struct IClfsRequestAsync *a3,
        struct _CLFS_IO_WORKITEM *a4,
        PMDL *a5,
        unsigned int a6,
        unsigned __int64 *a7)
{
  struct IClfsRequestAsync *v8; // rdi
  __int64 Irp; // rsi
  unsigned int RawSectorSize; // r14d
  __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  BOOL v16; // r14d
  int v17; // eax
  __int64 v18; // rcx
  PMDL *v19; // r8
  PMDL v20; // rdx
  unsigned int v21; // eax
  struct _MDL *v22; // rax
  char *v23; // rcx
  __int64 v24; // rax
  NTSTATUS v25; // edi
  __int64 (__fastcall *v26)(struct _DEVICE_OBJECT *, struct _IRP *, void *); // rax
  __int64 v27; // rcx
  CSHORT MdlFlags; // ax
  __int64 v29; // r9
  struct _MDL *Mdl; // rax
  int (*v31)(struct _DEVICE_OBJECT *, struct _IRP *, void *); // rax
  __int64 v32; // rcx
  _QWORD *v33; // r8
  char v35; // [rsp+58h] [rbp-98h]
  char v36; // [rsp+60h] [rbp-90h]
  char v37; // [rsp+61h] [rbp-8Fh]
  unsigned int Length; // [rsp+64h] [rbp-8Ch]
  PDEVICE_OBJECT DeviceObject; // [rsp+70h] [rbp-80h]
  char *VirtualAddress; // [rsp+80h] [rbp-70h]
  char *VirtualAddressa; // [rsp+80h] [rbp-70h]
  __int64 v42; // [rsp+88h] [rbp-68h]
  _QWORD v43[2]; // [rsp+90h] [rbp-60h] BYREF
  struct _MDL **v44; // [rsp+A0h] [rbp-50h]
  unsigned __int64 v45; // [rsp+A8h] [rbp-48h]
  unsigned __int64 v46; // [rsp+B0h] [rbp-40h]

  v8 = a3;
  v43[0] = 0;
  v43[1] = 0;
  Irp = 0;
  v36 = 0;
  v35 = 0;
  v37 = 0;
  if ( Event )
  {
    ObfReferenceObject(Event);
    KeClearEvent(Event);
  }
  ObfReferenceObject(BugCheckParameter3[6]);
  DeviceObject = IoGetRelatedDeviceObject((PFILE_OBJECT)BugCheckParameter3[6]);
  Length = a6 << 9;
  if ( (unsigned __int64)a6 << 9 > 0xFFFFFFFF )
    goto LABEL_43;
  RawSectorSize = CClfsContainer::GetRawSectorSize((CClfsContainer *)BugCheckParameter3);
  if ( RawSectorSize - 1 > 0xFFF || (RawSectorSize & 0x1FF) != 0 || 0x1000 % RawSectorSize )
  {
    v25 = -1073741672;
    goto LABEL_44;
  }
  VirtualAddress = _CLFS_READ_BUFFER::GetAddress((_CLFS_READ_BUFFER *)a5);
  if ( !VirtualAddress )
  {
    v25 = -1073741670;
    goto LABEL_44;
  }
  v13 = RawSectorSize - 1;
  if ( ((unsigned int)v13 & Length) != 0
    || ((v14 = *a7, v45 = *a7, !RawSectorSize) ? (v15 = 0) : (v15 = ~(unsigned __int64)(unsigned int)v13 & (v14 + v13)),
        v15 != v14) )
  {
LABEL_43:
    v25 = -1073741811;
LABEL_44:
    v16 = 1;
    goto LABEL_60;
  }
  if ( (*((_DWORD *)BugCheckParameter3[6] + 20) & 2) != 0 )
    KeBugCheckEx(0xC1F5u, 0xAu, *((unsigned int *)BugCheckParameter3[6] + 20), (ULONG_PTR)BugCheckParameter3, 0);
  v46 = HIDWORD(v14);
  v16 = 1;
  if ( (v14 & 0x8000000000000000uLL) != 0LL )
  {
    v25 = -1073741811;
    goto LABEL_60;
  }
  v17 = Event != 0;
  if ( v8 )
    ++v17;
  if ( a4 )
    ++v17;
  if ( v17 != 1 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x8000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        14,
        (unsigned int)WPP_e6b4d78dd9313ac32e42f0dcea3d4c75_Traceguids,
        (unsigned int)"CClfsContainer::ReadSector",
        218,
        -1073741811);
    }
    KeBugCheckEx(0xC1F5u, 0xBu, (ULONG_PTR)Event, (ULONG_PTR)a3, (ULONG_PTR)a4);
  }
  LOBYTE(v14) = DeviceObject->StackSize;
  Irp = IoAllocateIrpEx(DeviceObject, v14, 0);
  if ( !Irp )
    goto LABEL_52;
  if ( v8 )
  {
    v25 = (*(__int64 (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)v8 + 200LL))(v8);
    if ( v25 < 0 )
      goto LABEL_60;
    v37 = 1;
    v8 = a3;
  }
  *(_QWORD *)(Irp + 192) = BugCheckParameter3[6];
  *(_QWORD *)(Irp + 152) = KeGetCurrentThread();
  *(_QWORD *)(Irp + 160) = 0;
  *(_WORD *)(Irp + 64) = 0;
  *(_BYTE *)(Irp + 68) = 0;
  *(_QWORD *)(Irp + 104) = 0;
  *(_QWORD *)(Irp + 80) = 0;
  *(_QWORD *)(Irp + 88) = 0;
  *(_QWORD *)(Irp + 96) = 0;
  v18 = *(_QWORD *)(Irp + 184);
  v42 = v18;
  *(_BYTE *)(v18 - 72) = 3;
  *(_QWORD *)(v18 - 24) = BugCheckParameter3[6];
  *(_QWORD *)(Irp + 24) = 0;
  *(_QWORD *)(Irp + 8) = 0;
  *(_QWORD *)(Irp + 112) = 0;
  *(_DWORD *)(Irp + 16) = 0;
  v19 = a5;
  v20 = a5[1];
  if ( v20 )
  {
    MdlFlags = v20->MdlFlags;
    if ( (MdlFlags & 0x16) == 0 )
      KeBugCheckEx(0xC1F5u, 0xCu, MdlFlags, (ULONG_PTR)BugCheckParameter3, 0);
    v29 = *((unsigned int *)a5 + 4);
    v44 = (struct _MDL **)(Irp + 8);
    if ( (_DWORD)v29 )
    {
      VirtualAddressa = (char *)v20->StartVa + v20->ByteOffset + v29;
      Mdl = IoAllocateMdl(VirtualAddressa, Length, 0, 0, 0);
      *v44 = Mdl;
      if ( !Mdl )
        goto LABEL_52;
      v35 = 1;
      IoBuildPartialMdl(a5[1], Mdl, VirtualAddressa, Length);
      v19 = a5;
    }
    else
    {
      *(_QWORD *)(Irp + 8) = v20;
      v35 = 0;
    }
    v23 = (char *)v19[1]->StartVa + v19[1]->ByteOffset + *((unsigned int *)v19 + 4);
    goto LABEL_25;
  }
  v21 = a6 << 9;
  if ( Length )
  {
    v22 = IoAllocateMdl(VirtualAddress, Length, 0, 1u, (PIRP)Irp);
    *(_QWORD *)(Irp + 8) = v22;
    if ( v22 )
    {
      v35 = 1;
      MmProbeAndLockPages(v22, 0, IoWriteAccess);
      v23 = (char *)(*(_QWORD *)(*(_QWORD *)(Irp + 8) + 32LL) + *(unsigned int *)(*(_QWORD *)(Irp + 8) + 44LL));
LABEL_25:
      *(_QWORD *)(Irp + 112) = v23;
      v18 = v42;
      v21 = a6 << 9;
      goto LABEL_26;
    }
LABEL_52:
    v25 = -1073741670;
    goto LABEL_60;
  }
LABEL_26:
  *(_DWORD *)(Irp + 16) |= 0x101u;
  *(_DWORD *)(v18 - 64) = v21;
  *(_DWORD *)(v18 - 56) = 0;
  *(_DWORD *)(v18 - 48) = v45;
  *(_DWORD *)(v18 - 44) = v46;
  if ( v8 )
  {
    (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)v8 + 16LL))(v8);
    v26 = CClfsContainer::IoAsyncReadRequestCompletion;
    if ( v35 )
      v26 = CClfsContainer::IoAsyncReadRequestCompletionFreeMdls;
    v27 = *(_QWORD *)(Irp + 184);
    *(_QWORD *)(v27 - 16) = v26;
    *(_QWORD *)(v27 - 8) = v8;
    *(_BYTE *)(v27 - 69) = 0;
    *(_BYTE *)(v27 - 69) = 64;
    *(_BYTE *)(v27 - 69) = -64;
    *(_BYTE *)(v27 - 69) = -32;
    v25 = IofCallDriver(DeviceObject, (PIRP)Irp);
  }
  else if ( a4 )
  {
    v31 = CClfsContainer::IoAsyncReadWorkItemCompletion;
    if ( v35 )
      v31 = (int (*)(struct _DEVICE_OBJECT *, struct _IRP *, void *))CClfsContainer::IoAsyncReadWorkItemCompletionFreeMdls;
    v32 = *(_QWORD *)(Irp + 184);
    *(_QWORD *)(v32 - 16) = v31;
    *(_QWORD *)(v32 - 8) = a4;
    *(_BYTE *)(v32 - 69) = 0;
    *(_BYTE *)(v32 - 69) = 64;
    *(_BYTE *)(v32 - 69) = -64;
    *(_BYTE *)(v32 - 69) = -32;
    IofCallDriver(DeviceObject, (PIRP)Irp);
    v25 = 259;
  }
  else
  {
    *(_DWORD *)(Irp + 16) |= 4u;
    *(_QWORD *)(Irp + 72) = v43;
    v24 = *(_QWORD *)(Irp + 184);
    *(_QWORD *)(v24 - 16) = CClfsContainer::CompleteFsdRequest;
    *(_QWORD *)(v24 - 8) = Event;
    *(_BYTE *)(v24 - 69) = 0;
    *(_BYTE *)(v24 - 69) = 64;
    *(_BYTE *)(v24 - 69) = -64;
    *(_BYTE *)(v24 - 69) = -32;
    if ( IofCallDriver(DeviceObject, (PIRP)Irp) == 259 )
      KeWaitForSingleObject(Event, Executive, 0, 0, 0);
    v25 = v43[0];
  }
  v36 = 1;
  if ( KeGetCurrentIrql() >= 2u )
    KeBugCheckEx(0xC1F5u, 0xDu, v25, (ULONG_PTR)BugCheckParameter3, 0);
LABEL_60:
  if ( Event || !v36 )
  {
    if ( Irp )
    {
      v33 = *(_QWORD **)(Irp + 8);
      if ( v33 )
        v16 = *v33 == 0;
      if ( !v16 )
        KeBugCheckEx(0xC1F5u, 0xEu, (ULONG_PTR)v33, (ULONG_PTR)BugCheckParameter3, 0);
      if ( v35 )
      {
        ClfsFreeIrpAndMdls((PIRP)Irp);
      }
      else
      {
        *(_QWORD *)(Irp + 8) = 0;
        IoFreeIrp((PIRP)Irp);
      }
    }
    if ( a4 )
    {
      *((_DWORD *)a4 + 10) = v25;
      *((_QWORD *)a4 + 6) = 0;
      IoQueueWorkItem(*(PIO_WORKITEM *)a4, CClfsContainer::WorkRoutine, CriticalWorkQueue, a4);
      v25 = 259;
    }
    ObfDereferenceObject(BugCheckParameter3[6]);
    if ( Event )
      ObfDereferenceObject(Event);
    if ( v37 )
      (*(void (__fastcall **)(struct IClfsRequestAsync *))(*(_QWORD *)a3 + 208LL))(a3);
  }
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x14006b4e8  mov     r11, rsp
0x14006b4eb  mov     [r11+20h], r9
0x14006b4ef  mov     [r11+18h], r8
0x14006b4f3  mov     [r11+10h], rdx
0x14006b4f7  mov     [r11+8], rcx
0x14006b4fb  push    rbx
0x14006b4fc  push    rsi
0x14006b4fd  push    rdi
0x14006b4fe  push    r12
0x14006b500  push    r13
0x14006b502  push    r14
0x14006b504  push    r15
0x14006b506  sub     rsp, 90h
0x14006b50d  mov     r13, r9
0x14006b510  mov     rdi, r8
0x14006b513  mov     r12, rdx
0x14006b516  mov     r15, rcx
0x14006b519  xor     ebx, ebx
0x14006b51b  mov     [r11-60h], rbx
0x14006b51f  xor     eax, eax
0x14006b521  mov     [r11-58h], rbx
0x14006b525  mov     esi, ebx
0x14006b527  mov     [r11-78h], rbx
0x14006b52b  mov     [rsp+0C8h+var_94], ebx
0x14006b52f  mov     [rsp+0C8h+var_90], bl
0x14006b533  mov     [rsp+0C8h+var_98], bl
0x14006b537  mov     [rsp+0C8h+var_8F], bl
0x14006b53b  test    rdx, rdx
0x14006b53e  jnz     loc_14006BBF0
0x14006b544  mov     rcx, [r15+30h]; Object
0x14006b548  call    cs:__imp_ObfReferenceObject
0x14006b54f  nop     dword ptr [rax+rax+00h]
0x14006b554  nop
0x14006b555  mov     rcx, [r15+30h]; FileObject
0x14006b559  call    cs:__imp_IoGetRelatedDeviceObject
0x14006b560  nop     dword ptr [rax+rax+00h]
0x14006b565  mov     [rsp+0C8h+DeviceObject], rax
0x14006b56a  mov     ecx, [rsp+0C8h+arg_28]
0x14006b571  shl     rcx, 9
0x14006b575  mov     edx, 0FFFFFFFFh
0x14006b57a  cmp     rcx, rdx
0x14006b57d  mov     [rsp+0C8h+Length], ecx
0x14006b581  jbe     short loc_14006B587
0x14006b583  mov     [rsp+0C8h+Length], edx
0x14006b587  cmp     rdx, rcx
0x14006b58a  sbb     eax, eax
0x14006b58c  and     eax, 0C0000095h
0x14006b591  mov     [rsp+0C8h+var_94], eax
0x14006b595  cmp     rcx, rdx
0x14006b598  ja      loc_14006B9AB
0x14006b59e  mov     rcx, r15; this
0x14006b5a1  call    ?GetRawSectorSize@CClfsContainer@@QEAAKXZ; CClfsContainer::GetRawSectorSize(void)
0x14006b5a6  mov     r14d, eax
0x14006b5a9  dec     eax
0x14006b5ab  cmp     eax, 0FFFh
0x14006b5b0  ja      loc_14006BB48
0x14006b5b6  test    r14d, 1FFh
0x14006b5bd  jnz     loc_14006BB48
0x14006b5c3  xor     edx, edx
0x14006b5c5  mov     eax, 1000h
0x14006b5ca  div     r14d
0x14006b5cd  test    edx, edx
0x14006b5cf  jnz     loc_14006BB48
0x14006b5d5  mov     rcx, [rsp+0C8h+arg_20]; this
0x14006b5dd  call    ?GetAddress@_CLFS_READ_BUFFER@@QEBAPEAEXZ; _CLFS_READ_BUFFER::GetAddress(void)
0x14006b5e2  mov     [rsp+0C8h+VirtualAddress], rax
0x14006b5e7  test    rax, rax
0x14006b5ea  jz      loc_14006B9C7
0x14006b5f0  lea     ecx, [r14-1]
0x14006b5f4  mov     eax, [rsp+0C8h+Length]
0x14006b5f8  test    eax, ecx
0x14006b5fa  jnz     loc_14006B9AB
0x14006b600  mov     rax, [rsp+0C8h+arg_30]
0x14006b608  mov     rdx, [rax]
0x14006b60b  mov     [rsp+0C8h+var_48], rdx
0x14006b613  test    r14d, r14d
0x14006b616  jz      loc_14006B9BF
0x14006b61c  mov     eax, ecx
0x14006b61e  add     rcx, rdx
0x14006b621  not     rax
0x14006b624  and     rcx, rax
0x14006b627  cmp     rcx, rdx
0x14006b62a  jnz     loc_14006B9AB
0x14006b630  mov     rax, [r15+30h]
0x14006b634  mov     ecx, [rax+50h]
0x14006b637  test    cl, 2
0x14006b63a  jnz     loc_14006B8B1
0x14006b640  mov     rax, rdx
0x14006b643  shr     rax, 20h
0x14006b647  mov     [rsp+0C8h+var_40], rax
0x14006b64f  mov     r14d, 1
0x14006b655  test    eax, eax
0x14006b657  js      loc_14006B9CE
0x14006b65d  mov     eax, ebx
0x14006b65f  test    r12, r12
0x14006b662  cmovnz  eax, r14d
0x14006b666  mov     [rsp+0C8h+var_88], eax
0x14006b66a  test    rdi, rdi
0x14006b66d  jz      short loc_14006B676
0x14006b66f  add     eax, r14d
0x14006b672  mov     [rsp+0C8h+var_88], eax
0x14006b676  test    r13, r13
0x14006b679  jnz     loc_14006B9D5
0x14006b67f  cmp     eax, r14d
0x14006b682  jnz     loc_14006B9E1
0x14006b688  xor     r8d, r8d
0x14006b68b  mov     rax, [rsp+0C8h+DeviceObject]
0x14006b690  mov     dl, [rax+4Ch]
0x14006b693  mov     rcx, rax
0x14006b696  call    cs:__imp_IoAllocateIrpEx
0x14006b69d  nop     dword ptr [rax+rax+00h]
0x14006b6a2  mov     rsi, rax
0x14006b6a5  mov     [rsp+0C8h+var_78], rax
0x14006b6aa  test    rax, rax
0x14006b6ad  jz      loc_14006BA58
0x14006b6b3  test    rdi, rdi
0x14006b6b6  jnz     loc_14006B939
0x14006b6bc  mov     rax, [r15+30h]
0x14006b6c0  mov     [rsi+0C0h], rax
0x14006b6c7  mov     rax, gs:188h
0x14006b6d0  mov     [rsi+98h], rax
0x14006b6d7  mov     [rsi+0A0h], rbx
0x14006b6de  mov     [rsi+40h], bx
0x14006b6e2  mov     [rsi+44h], bl
0x14006b6e5  mov     [rsi+68h], rbx
0x14006b6e9  mov     [rsi+50h], rbx
0x14006b6ed  mov     [rsi+58h], rbx
0x14006b6f1  mov     [rsi+60h], rbx
0x14006b6f5  mov     rcx, [rsi+0B8h]
0x14006b6fc  mov     [rsp+0C8h+var_68], rcx
0x14006b701  mov     byte ptr [rcx-48h], 3
0x14006b705  mov     rax, [r15+30h]
0x14006b709  mov     [rcx-18h], rax
0x14006b70d  mov     [rsi+18h], rbx
0x14006b711  mov     [rsi+8], rbx
0x14006b715  mov     [rsi+70h], rbx
0x14006b719  mov     [rsi+10h], ebx
0x14006b71c  mov     r8, [rsp+0C8h+arg_20]
0x14006b724  mov     rdx, [r8+8]
0x14006b728  test    rdx, rdx
0x14006b72b  jnz     loc_14006B96B
0x14006b731  mov     eax, [rsp+0C8h+Length]
0x14006b735  test    eax, eax
0x14006b737  jz      loc_14006B7C9
0x14006b73d  mov     [rsp+0C8h+Irp], rsi; Irp
0x14006b742  mov     r9b, r14b; ChargeQuota
0x14006b745  xor     r8d, r8d; SecondaryBuffer
0x14006b748  mov     edx, eax; Length
0x14006b74a  mov     rcx, [rsp+0C8h+VirtualAddress]; VirtualAddress
0x14006b74f  call    cs:__imp_IoAllocateMdl
0x14006b756  nop     dword ptr [rax+rax+00h]
0x14006b75b  mov     [rsi+8], rax
0x14006b75f  test    rax, rax
0x14006b762  jz      loc_14006BA58
0x14006b768  mov     [rsp+0C8h+var_98], r14b
0x14006b76d  mov     r8d, r14d; Operation
0x14006b770  xor     edx, edx; AccessMode
0x14006b772  mov     rcx, rax; MemoryDescriptorList
0x14006b775  call    cs:__imp_MmProbeAndLockPages
0x14006b77c  nop     dword ptr [rax+rax+00h]
0x14006b781  jmp     short loc_14006B7B1
0x14006b783  mov     edi, eax
0x14006b785  mov     [rsp+0C8h+var_94], eax
0x14006b789  xor     ebx, ebx
0x14006b78b  lea     r14d, [rbx+1]
0x14006b78f  mov     r15, [rsp+0C8h+arg_0]
0x14006b797  mov     r13, [rsp+0C8h+Context]
0x14006b79f  mov     r12, [rsp+0C8h+Object]
0x14006b7a7  mov     rsi, [rsp+0C8h+var_78]
0x14006b7ac  jmp     loc_14006BB52
0x14006b7b1  mov     rax, [rsi+8]
0x14006b7b5  mov     ecx, [rax+2Ch]
0x14006b7b8  add     rcx, [rax+20h]
0x14006b7bc  mov     [rsi+70h], rcx
0x14006b7c0  mov     rcx, [rsp+0C8h+var_68]
0x14006b7c5  mov     eax, [rsp+0C8h+Length]
0x14006b7c9  or      dword ptr [rsi+10h], 101h
0x14006b7d0  mov     [rcx-40h], eax
0x14006b7d3  mov     [rcx-38h], ebx
0x14006b7d6  mov     rax, [rsp+0C8h+var_48]
0x14006b7de  mov     [rcx-30h], eax
0x14006b7e1  mov     rax, [rsp+0C8h+var_40]
0x14006b7e9  mov     [rcx-2Ch], eax
0x14006b7ec  test    rdi, rdi
0x14006b7ef  jnz     loc_14006B8D7
0x14006b7f5  mov     rdx, rsi; Irp
0x14006b7f8  test    r13, r13
0x14006b7fb  jnz     loc_14006BAF5
0x14006b801  or      dword ptr [rsi+10h], 4
0x14006b805  lea     rax, [rsp+0C8h+var_60]
0x14006b80a  mov     [rsi+48h], rax
0x14006b80e  mov     rax, [rsi+0B8h]
0x14006b815  lea     rcx, ?CompleteFsdRequest@CClfsContainer@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; CClfsContainer::CompleteFsdRequest(_DEVICE_OBJECT *,_IRP *,void *)
0x14006b81c  mov     [rax-10h], rcx
0x14006b820  mov     [rax-8], r12
0x14006b824  mov     [rax-45h], bl
0x14006b827  mov     byte ptr [rax-45h], 40h ; '@'
0x14006b82b  mov     byte ptr [rax-45h], 0C0h
0x14006b82f  mov     byte ptr [rax-45h], 0E0h
0x14006b833  mov     rcx, [rsp+0C8h+DeviceObject]; DeviceObject
0x14006b838  call    cs:__imp_IofCallDriver
0x14006b83f  nop     dword ptr [rax+rax+00h]
0x14006b844  mov     [rsp+0C8h+var_94], eax
0x14006b848  cmp     eax, 103h
0x14006b84d  jnz     short loc_14006B86F
0x14006b84f  mov     [rsp+0C8h+Irp], rbx; Timeout
0x14006b854  xor     r9d, r9d; Alertable
0x14006b857  xor     r8d, r8d; WaitMode
0x14006b85a  xor     edx, edx; WaitReason
0x14006b85c  mov     rcx, r12; Object
0x14006b85f  call    cs:__imp_KeWaitForSingleObject
0x14006b866  nop     dword ptr [rax+rax+00h]
0x14006b86b  mov     [rsp+0C8h+var_94], eax
0x14006b86f  mov     edi, [rsp+0C8h+var_60]
0x14006b873  mov     [rsp+0C8h+var_94], edi
0x14006b877  mov     [rsp+0C8h+var_90], r14b
0x14006b87c  call    cs:__imp_KeGetCurrentIrql
0x14006b883  nop     dword ptr [rax+rax+00h]
0x14006b888  cmp     al, 2
0x14006b88a  jb      loc_14006BB52
0x14006b890  movsxd  r8, edi; BugCheckParameter2
0x14006b893  mov     [rsp+0C8h+Irp], rbx; BugCheckParameter4
0x14006b898  mov     r9, r15; BugCheckParameter3
0x14006b89b  mov     edx, 0Dh; BugCheckParameter1
0x14006b8a0  mov     ecx, 0C1F5h; BugCheckCode
0x14006b8a5  call    cs:__imp_KeBugCheckEx
0x14006b8b1  mov     rax, [r15+30h]
0x14006b8b5  mov     r8d, [rax+50h]; BugCheckParameter2
0x14006b8b9  mov     [rsp+0C8h+Irp], rbx; BugCheckParameter4
0x14006b8be  mov     r9, r15; BugCheckParameter3
0x14006b8c1  mov     edx, 0Ah; BugCheckParameter1
0x14006b8c6  mov     ecx, 0C1F5h; BugCheckCode
0x14006b8cb  call    cs:__imp_KeBugCheckEx
0x14006b8d7  mov     rax, [rdi]
0x14006b8da  mov     rax, [rax+10h]
0x14006b8de  mov     rcx, rdi
0x14006b8e1  call    _guard_dispatch_icall
0x14006b8e6  lea     rax, ?IoAsyncReadRequestCompletion@CClfsContainer@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; CClfsContainer::IoAsyncReadRequestCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x14006b8ed  lea     rcx, ?IoAsyncReadRequestCompletionFreeMdls@CClfsContainer@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; CClfsContainer::IoAsyncReadRequestCompletionFreeMdls(_DEVICE_OBJECT *,_IRP *,void *)
0x14006b8f4  cmp     [rsp+0C8h+var_98], bl
0x14006b8f8  cmovnz  rax, rcx
0x14006b8fc  mov     rcx, [rsi+0B8h]
0x14006b903  mov     [rcx-10h], rax
0x14006b907  mov     [rcx-8], rdi
0x14006b90b  mov     [rcx-45h], bl
0x14006b90e  mov     byte ptr [rcx-45h], 40h ; '@'
0x14006b912  mov     byte ptr [rcx-45h], 0C0h
0x14006b916  mov     byte ptr [rcx-45h], 0E0h
0x14006b91a  mov     rdx, rsi; Irp
0x14006b91d  mov     rcx, [rsp+0C8h+DeviceObject]; DeviceObject
0x14006b922  call    cs:__imp_IofCallDriver
0x14006b929  nop     dword ptr [rax+rax+00h]
0x14006b92e  mov     edi, eax
0x14006b930  mov     [rsp+0C8h+var_94], eax
0x14006b934  jmp     loc_14006B877
0x14006b939  mov     rax, [rdi]
0x14006b93c  mov     rax, [rax+0C8h]
0x14006b943  mov     rcx, rdi
0x14006b946  call    _guard_dispatch_icall
0x14006b94b  mov     edi, eax
0x14006b94d  mov     [rsp+0C8h+var_94], eax
0x14006b951  test    eax, eax
0x14006b953  js      loc_14006BB52
0x14006b959  mov     [rsp+0C8h+var_8F], r14b
0x14006b95e  mov     rdi, [rsp+0C8h+BugCheckParameter3]
0x14006b966  jmp     loc_14006B6BC
0x14006b96b  movzx   eax, word ptr [rdx+0Ah]
0x14006b96f  test    al, 16h
0x14006b971  jz      loc_14006BA62
0x14006b977  mov     r9d, [r8+10h]
0x14006b97b  lea     rax, [rsi+8]
0x14006b97f  mov     [rsp+0C8h+var_50], rax
0x14006b984  test    r9d, r9d
0x14006b987  jnz     loc_14006BA84
0x14006b98d  mov     [rax], rdx
0x14006b990  mov     [rsp+0C8h+var_98], bl
0x14006b994  mov     rax, [r8+8]
0x14006b998  mov     ecx, [rax+2Ch]
0x14006b99b  add     rcx, [rax+20h]
0x14006b99f  mov     eax, [r8+10h]
0x14006b9a3  add     rcx, rax
0x14006b9a6  jmp     loc_14006B7BC
0x14006b9ab  mov     edi, 0C000000Dh
0x14006b9b0  mov     r14d, 1
0x14006b9b6  mov     [rsp+0C8h+var_94], edi
0x14006b9ba  jmp     loc_14006BB52
0x14006b9bf  mov     rcx, rbx
0x14006b9c2  jmp     loc_14006B627
0x14006b9c7  mov     edi, 0C000009Ah
0x14006b9cc  jmp     short loc_14006B9B0
0x14006b9ce  mov     edi, 0C000000Dh
0x14006b9d3  jmp     short loc_14006B9B6
0x14006b9d5  add     eax, r14d
0x14006b9d8  mov     [rsp+0C8h+var_88], eax
0x14006b9dc  jmp     loc_14006B67F
0x14006b9e1  mov     edi, 0C000000Dh
0x14006b9e6  mov     [rsp+0C8h+var_94], edi
0x14006b9ea  lea     rax, WPP_GLOBAL_Control
0x14006b9f1  mov     rcx, cs:WPP_GLOBAL_Control
0x14006b9f8  cmp     rcx, rax
  ... truncated ...
```
