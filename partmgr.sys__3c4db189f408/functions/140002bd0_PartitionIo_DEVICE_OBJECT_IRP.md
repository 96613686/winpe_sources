# PartitionIo(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140002bd0`
- end: `0x140002fea`
- name: `?PartitionIo@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1050`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140002b70`

## callees

- `0x140002bd0`
- `0x140002ff0`
- `0x140003530`
- `0x14000ae88`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140011c91`
- `ntoskrnl!IoFreeIrp` at `0x140011c91`
- `ntoskrnl!IoFreeMdl` at `0x140002d87`
- `ntoskrnl!IoFreeMdl` at `0x140002d87`
- `ntoskrnl!IofCallDriver` at `0x140002de1`
- `ntoskrnl!IofCallDriver` at `0x140002ef7`
- `ntoskrnl!IofCallDriver` at `0x140002de1`
- `ntoskrnl!IofCallDriver` at `0x140002ef7`
- `ntoskrnl!IofCompleteRequest` at `0x140002fd9`
- `ntoskrnl!IofCompleteRequest` at `0x140002fd9`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002e83`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002e83`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140002c1d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140002f31`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140002c1d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x140002f31`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002f1e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002f1e`

## pseudocode

```c
__int64 __fastcall PartitionIo(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  char *DeviceExtension; // r15
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v6; // rcx
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *p_ListEntry; // r12
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *v8; // rsi
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *v9; // rax
  struct _IO_STACK_LOCATION *v10; // rax
  struct _IO_STACK_LOCATION *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rbx
  unsigned __int64 Length; // rbp
  unsigned __int64 QuadPart; // rsi
  unsigned __int64 v16; // rax
  _QWORD *v17; // r14
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rax
  __int64 v22; // r8
  NTSTATUS v23; // edi
  struct _LIST_ENTRY *v24; // rax
  struct _LIST_ENTRY *v25; // rcx
  IRP *p_Blink; // rbp
  struct _MDL *v27; // rcx
  unsigned __int64 v29; // rax
  struct _LIST_ENTRY *v30; // rcx
  struct _LIST_ENTRY *Flink; // rdx
  struct _LIST_ENTRY *v32; // rax
  int v33; // ebx
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *v34; // r14
  unsigned __int64 v35; // rax
  struct _IO_STACK_LOCATION *v36; // rax
  int v37; // ecx
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-78h] BYREF
  __int128 v39; // [rsp+48h] [rbp-60h] BYREF
  __int128 v40; // [rsp+58h] [rbp-50h]
  struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *v41; // [rsp+B0h] [rbp+8h]
  struct _IO_STACK_LOCATION *v42; // [rsp+B8h] [rbp+10h]
  __int64 v43; // [rsp+C0h] [rbp+18h]
  __int64 v44; // [rsp+C0h] [rbp+18h]

  DeviceExtension = (char *)a1->DeviceExtension;
  p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a2->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v39 = 0;
  v40 = 0;
  v6 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)DeviceExtension + 50);
  v42 = CurrentStackLocation;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( ExAcquireRundownProtectionCacheAware(v6) )
  {
    p_ListEntry = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
    v8 = p_CurrentStackLocation;
    v9 = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
    v41 = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
  }
  else
  {
    v23 = 0;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 56, &LockHandle);
    if ( ExAcquireRundownProtectionCacheAware(*((PEX_RUNDOWN_REF_CACHE_AWARE *)DeviceExtension + 50)) )
    {
      v34 = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
      v8 = p_CurrentStackLocation;
    }
    else
    {
      p_CurrentStackLocation->CurrentStackLocation->Control |= 1u;
      v30 = (struct _LIST_ENTRY *)*((_QWORD *)DeviceExtension + 55);
      if ( (char *)v30->Flink != DeviceExtension + 432 )
        goto LABEL_32;
      v34 = (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)&a2->Tail.Overlay.ListEntry;
      v23 = 259;
      a2->Tail.Overlay.ListEntry.Flink = (struct _LIST_ENTRY *)(DeviceExtension + 432);
      v8 = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a2->Tail.Overlay.CurrentStackLocation;
      a2->Tail.Overlay.ListEntry.Blink = v30;
      v30->Flink = &a2->Tail.Overlay.ListEntry;
      *((_QWORD *)DeviceExtension + 55) = &a2->Tail.Overlay.ListEntry;
    }
    v41 = v34;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( v23 )
      return (unsigned int)v23;
    CurrentStackLocation = v42;
    p_ListEntry = v34;
    v9 = v34;
  }
  v9->ListEntry.Blink = &v9->ListEntry;
  v9->ListEntry.Flink = &v9->ListEntry;
  v10 = v8->CurrentStackLocation;
  *(_OWORD *)&v10[-1].MajorFunction = *(_OWORD *)&v8->CurrentStackLocation->MajorFunction;
  *(_OWORD *)&v10[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v10->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v10[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v10->Parameters.SetQuota + 6);
  v10[-1].FileObject = v10->FileObject;
  v10[-1].Control = 0;
  v11 = v8->CurrentStackLocation;
  v11[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)PartitionIoCompletion;
  v11[-1].Context = 0;
  v11[-1].Control = -32;
  if ( (ScReadNoFence((unsigned int *)DeviceExtension + 10) & 0x80u) == 0 )
  {
    *(_QWORD *)&v39 = DeviceExtension;
    v12 = DeviceExtension + 312;
    *((_QWORD *)&v39 + 1) = a2;
    v13 = (_QWORD *)*((_QWORD *)DeviceExtension + 39);
    Length = CurrentStackLocation->Parameters.Read.Length;
    QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
    while ( v13 != v12 )
    {
      v16 = v13[2];
      v17 = (_QWORD *)*v13;
      if ( v16 > QuadPart )
      {
        v29 = v16 - QuadPart;
        if ( v29 >= Length )
          break;
        v44 = (unsigned int)v29;
        v23 = PartitionOverlapCount(1, 0, (unsigned int)v29, QuadPart, (__int64)&v39);
        if ( v23 < 0 )
          goto LABEL_14;
        Length -= v44;
        QuadPart += v44;
      }
      if ( !Length )
        goto LABEL_20;
      v18 = v13[2];
      if ( v18 <= QuadPart )
      {
        v19 = QuadPart - v18;
        v20 = v13[4];
        if ( v19 < v20 )
        {
          v21 = v20 - v19;
          v22 = Length;
          if ( v21 < Length )
            v22 = v21;
          v43 = v22;
          v23 = PartitionOverlapCount(2, (__int64)v13, v22, QuadPart, (__int64)&v39);
          if ( v23 < 0 )
            goto LABEL_14;
          QuadPart += v43;
          Length -= v43;
          if ( !Length )
            goto LABEL_20;
        }
      }
      v13 = v17;
      v12 = DeviceExtension + 312;
    }
    if ( Length )
    {
      v23 = PartitionOverlapCount(3, 0, Length, QuadPart, (__int64)&v39);
      if ( v23 < 0 )
        goto LABEL_14;
      v35 = Length;
      Length = 0;
      QuadPart += v35;
    }
LABEL_20:
    v23 = PartitionOverlapCount(4, 0, Length, QuadPart, (__int64)&v39);
    if ( v23 >= 0 )
    {
      if ( (_DWORD)v40 == 1 )
      {
        a2->Tail.Overlay.CurrentStackLocation[-1].Parameters.Read.ByteOffset.QuadPart = *((_QWORD *)&v40 + 1);
        return (unsigned int)IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), a2);
      }
      v23 = PmEnumerateOverlaps(
              (struct _LIST_ENTRY *)(DeviceExtension + 312),
              v42->Parameters.Read.ByteOffset.QuadPart,
              v42->Parameters.Read.Length,
              (int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *))&PartitionOverlapIo,
              &v39);
      if ( v23 >= 0 )
      {
        --a2->Tail.Overlay.CurrentStackLocation;
        v33 = 0;
        --a2->CurrentLocation;
        v36 = a2->Tail.Overlay.CurrentStackLocation;
        a2->IoStatus.Information = 0;
        a2->IoStatus.Status = 0;
        v36->Control |= 1u;
        v37 = v40;
        a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (struct _LIST_ENTRY *)(int)v40;
        if ( !v37 )
          return 259;
        while ( 1 )
        {
          Flink = v41->ListEntry.Flink;
          if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)v41->ListEntry.Flink->Blink != p_ListEntry )
            break;
          v32 = Flink->Flink;
          if ( Flink->Flink->Blink != Flink )
            break;
          v41->ListEntry.Flink = v32;
          v32->Blink = &p_ListEntry->ListEntry;
          Flink->Blink = Flink;
          Flink->Flink = Flink;
          IofCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 2), (PIRP)&Flink[-11].Blink);
          if ( ++v33 >= (unsigned int)v40 )
            return 259;
        }
LABEL_32:
        __fastfail(3u);
      }
    }
LABEL_14:
    p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a2->Tail.Overlay.CurrentStackLocation;
    goto LABEL_15;
  }
  v23 = -1073741810;
LABEL_15:
  while ( 1 )
  {
    v24 = v41->ListEntry.Flink;
    if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)v41->ListEntry.Flink == v41 )
      break;
    if ( (struct _IRP::$::$2AD798E65616C4F7304824DBFA27E419::$665C8370128C04AB892B069E6FB086E8 *)v24->Blink != v41 )
      goto LABEL_32;
    v25 = v24->Flink;
    if ( v24->Flink->Blink != v24 )
      goto LABEL_32;
    v41->ListEntry.Flink = v25;
    p_Blink = (IRP *)&v24[-11].Blink;
    v25->Blink = &v41->ListEntry;
    v27 = (struct _MDL *)v24[-10].Flink;
    if ( v27 )
      IoFreeMdl(v27);
    IoFreeIrp(p_Blink);
  }
  --a2->CurrentLocation;
  --p_CurrentStackLocation->CurrentStackLocation;
  a2->IoStatus.Information = 0;
  a2->IoStatus.Status = v23;
  IofCompleteRequest(a2, 0);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x140002bd0  mov     [rsp+arg_18], rbx
0x140002bd5  push    rbp
0x140002bd6  push    rsi
0x140002bd7  push    rdi
0x140002bd8  push    r12
0x140002bda  push    r13
0x140002bdc  push    r14
0x140002bde  push    r15
0x140002be0  sub     rsp, 70h
0x140002be4  mov     r15, [rcx+40h]
0x140002be8  lea     rbx, [rdx+0B8h]
0x140002bef  mov     rdi, [rbx]
0x140002bf2  xorps   xmm0, xmm0
0x140002bf5  movups  [rsp+0A8h+var_60], xmm0
0x140002bfa  xor     eax, eax
0x140002bfc  mov     r13, rdx
0x140002bff  movups  [rsp+0A8h+var_50], xmm0
0x140002c04  mov     rcx, [r15+190h]; RunRefCacheAware
0x140002c0b  mov     [rsp+0A8h+arg_8], rdi
0x140002c13  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x140002c18  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x140002c1d  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140002c24  nop     dword ptr [rax+rax+00h]
0x140002c29  test    al, al
0x140002c2b  jz      loc_140002F10
0x140002c31  lea     r12, [r13+0A8h]
0x140002c38  mov     rsi, rbx
0x140002c3b  mov     rax, r12
0x140002c3e  mov     [rsp+0A8h+arg_0], r12
0x140002c46  mov     [rax+8], rax
0x140002c4a  lea     rcx, ?PartitionIoCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; PartitionIoCompletion(_DEVICE_OBJECT *,_IRP *,void *)
0x140002c51  mov     [rax], rax
0x140002c54  mov     rax, [rsi]
0x140002c57  movups  xmm0, xmmword ptr [rax]
0x140002c5a  movups  xmmword ptr [rax-48h], xmm0
0x140002c5e  movups  xmm1, xmmword ptr [rax+10h]
0x140002c62  movups  xmmword ptr [rax-38h], xmm1
0x140002c66  movups  xmm0, xmmword ptr [rax+20h]
0x140002c6a  movups  xmmword ptr [rax-28h], xmm0
0x140002c6e  movsd   xmm1, qword ptr [rax+30h]
0x140002c73  movsd   qword ptr [rax-18h], xmm1
0x140002c78  mov     byte ptr [rax-45h], 0
0x140002c7c  mov     rax, [rsi]
0x140002c7f  mov     [rax-10h], rcx
0x140002c83  lea     rcx, [r15+28h]; unsigned int *
0x140002c87  mov     qword ptr [rax-8], 0
0x140002c8f  mov     byte ptr [rax-45h], 0E0h
0x140002c93  call    ?ScReadNoFence@@YAKPEAK@Z; ScReadNoFence(ulong *)
0x140002c98  test    al, al
0x140002c9a  js      loc_140002F7A
0x140002ca0  mov     qword ptr [rsp+0A8h+var_60], r15
0x140002ca5  lea     rax, [r15+138h]
0x140002cac  mov     qword ptr [rsp+0A8h+var_60+8], r13
0x140002cb1  mov     rbx, [rax]
0x140002cb4  mov     ebp, [rdi+8]
0x140002cb7  mov     rsi, [rdi+18h]
0x140002cbb  cmp     rbx, rax
0x140002cbe  jz      loc_140002F84
0x140002cc4  mov     rax, [rbx+10h]
0x140002cc8  mov     r14, [rbx]
0x140002ccb  cmp     rax, rsi
0x140002cce  ja      loc_140002E0A
0x140002cd4  test    rbp, rbp
0x140002cd7  jz      loc_140002D99
0x140002cdd  mov     rax, [rbx+10h]
0x140002ce1  cmp     rax, rsi
0x140002ce4  jbe     short loc_140002CF2
0x140002ce6  mov     rbx, r14
0x140002ce9  lea     rax, [r15+138h]
0x140002cf0  jmp     short loc_140002CBB
0x140002cf2  mov     rcx, rsi
0x140002cf5  sub     rcx, rax
0x140002cf8  mov     rax, [rbx+20h]
0x140002cfc  cmp     rcx, rax
0x140002cff  jnb     short loc_140002CE6
0x140002d01  sub     rax, rcx
0x140002d04  mov     r8, rbp
0x140002d07  cmp     rax, rbp
0x140002d0a  mov     r9, rsi
0x140002d0d  mov     rdx, rbx
0x140002d10  mov     ecx, 2
0x140002d15  cmovb   r8, rax
0x140002d19  lea     rax, [rsp+0A8h+var_60]
0x140002d1e  mov     [rsp+0A8h+var_88], rax
0x140002d23  mov     [rsp+0A8h+arg_10], r8
0x140002d2b  call    ?PartitionOverlapCount@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z; PartitionOverlapCount(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *)
0x140002d30  mov     edi, eax
0x140002d32  test    eax, eax
0x140002d34  jns     loc_140002E5B
0x140002d3a  lea     rbx, [r13+0B8h]
0x140002d41  mov     rsi, [rsp+0A8h+arg_0]
0x140002d49  mov     rax, [rsi]
0x140002d4c  cmp     rax, rsi
0x140002d4f  jz      loc_140002FC0
0x140002d55  cmp     [rax+8], rsi
0x140002d59  jnz     loc_140002EC5
0x140002d5f  mov     rcx, [rax]
0x140002d62  cmp     [rcx+8], rax
0x140002d66  jnz     loc_140002EC5
0x140002d6c  mov     [rsi], rcx
0x140002d6f  lea     rbp, [rax-0A8h]
0x140002d76  mov     [rcx+8], rsi
0x140002d7a  mov     rcx, [rbp+8]; Mdl
0x140002d7e  test    rcx, rcx
0x140002d81  jz      loc_140011C8E
0x140002d87  call    cs:__imp_IoFreeMdl
0x140002d8e  nop     dword ptr [rax+rax+00h]
0x140002d93  nop
0x140002d94  jmp     loc_140011C8E
0x140002d99  lea     rax, [rsp+0A8h+var_60]
0x140002d9e  mov     r9, rsi
0x140002da1  mov     r8, rbp
0x140002da4  mov     [rsp+0A8h+var_88], rax
0x140002da9  xor     edx, edx
0x140002dab  mov     ecx, 4
0x140002db0  call    ?PartitionOverlapCount@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z; PartitionOverlapCount(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *)
0x140002db5  mov     edi, eax
0x140002db7  test    eax, eax
0x140002db9  js      loc_140002D3A
0x140002dbf  cmp     dword ptr [rsp+0A8h+var_50], 1
0x140002dc4  jnz     loc_140011C14
0x140002dca  mov     rdx, [r13+0B8h]
0x140002dd1  mov     rax, qword ptr [rsp+0A8h+var_50+8]
0x140002dd6  mov     [rdx-30h], rax
0x140002dda  mov     rdx, r13; Irp
0x140002ddd  mov     rcx, [r15+10h]; DeviceObject
0x140002de1  call    cs:__imp_IofCallDriver
0x140002de8  nop     dword ptr [rax+rax+00h]
0x140002ded  mov     edi, eax
0x140002def  mov     rbx, [rsp+0A8h+arg_18]
0x140002df7  mov     eax, edi
0x140002df9  add     rsp, 70h
0x140002dfd  pop     r15
0x140002dff  pop     r14
0x140002e01  pop     r13
0x140002e03  pop     r12
0x140002e05  pop     rdi
0x140002e06  pop     rsi
0x140002e07  pop     rbp
0x140002e08  retn
0x140002e0a  sub     rax, rsi
0x140002e0d  cmp     rax, rbp
0x140002e10  jnb     loc_140002F84
0x140002e16  lea     rcx, [rsp+0A8h+var_60]
0x140002e1b  mov     eax, eax
0x140002e1d  mov     [rsp+0A8h+var_88], rcx
0x140002e22  mov     r9, rsi
0x140002e25  mov     ecx, 1
0x140002e2a  mov     [rsp+0A8h+arg_10], rax
0x140002e32  mov     r8d, eax
0x140002e35  xor     edx, edx
0x140002e37  call    ?PartitionOverlapCount@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z; PartitionOverlapCount(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *)
0x140002e3c  mov     edi, eax
0x140002e3e  test    eax, eax
0x140002e40  js      loc_140002D3A
0x140002e46  sub     rbp, [rsp+0A8h+arg_10]
0x140002e4e  add     rsi, [rsp+0A8h+arg_10]
0x140002e56  jmp     loc_140002CD4
0x140002e5b  add     rsi, [rsp+0A8h+arg_10]
0x140002e63  sub     rbp, [rsp+0A8h+arg_10]
0x140002e6b  jnz     loc_140002CE6
0x140002e71  jmp     loc_140002D99
0x140002e76  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140002e7b  mov     [rsp+0A8h+arg_0], r14
0x140002e83  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002e8a  nop     dword ptr [rax+rax+00h]
0x140002e8f  test    edi, edi
0x140002e91  jnz     loc_140002DEF
0x140002e97  mov     rdi, [rsp+0A8h+arg_8]
0x140002e9f  mov     r12, r14
0x140002ea2  mov     rax, r14
0x140002ea5  jmp     loc_140002C46
0x140002eaa  mov     rax, [rbx]
0x140002ead  or      byte ptr [rax+3], 1
0x140002eb1  lea     rax, [r15+1B0h]
0x140002eb8  mov     rcx, [rax+8]
0x140002ebc  cmp     [rcx], rax
0x140002ebf  jz      loc_140002F54
0x140002ec5  mov     ecx, 3
0x140002eca  int     29h; Win8: RtlFailFast(ecx)
0x140002ecc  mov     rdx, [rsi]
0x140002ecf  cmp     [rdx+8], r12
0x140002ed3  jnz     short loc_140002EC5
0x140002ed5  mov     rax, [rdx]
0x140002ed8  cmp     [rax+8], rdx
0x140002edc  jnz     short loc_140002EC5
0x140002ede  mov     [rsi], rax
0x140002ee1  mov     [rax+8], r12
0x140002ee5  mov     [rdx+8], rdx
0x140002ee9  mov     [rdx], rdx
0x140002eec  add     rdx, 0FFFFFFFFFFFFFF58h; Irp
0x140002ef3  mov     rcx, [r15+10h]; DeviceObject
0x140002ef7  call    cs:__imp_IofCallDriver
0x140002efe  nop     dword ptr [rax+rax+00h]
0x140002f03  inc     ebx
0x140002f05  cmp     ebx, dword ptr [rsp+0A8h+var_50]
0x140002f09  jb      short loc_140002ECC
0x140002f0b  jmp     loc_140011CA3
0x140002f10  lea     rcx, [r15+1C0h]; SpinLock
0x140002f17  xor     edi, edi
0x140002f19  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x140002f1e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002f25  nop     dword ptr [rax+rax+00h]
0x140002f2a  mov     rcx, [r15+190h]; RunRefCacheAware
0x140002f31  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x140002f38  nop     dword ptr [rax+rax+00h]
0x140002f3d  test    al, al
0x140002f3f  jz      loc_140002EAA
0x140002f45  lea     r14, [r13+0A8h]
0x140002f4c  mov     rsi, rbx
0x140002f4f  jmp     loc_140002E76
0x140002f54  lea     r14, [r13+0A8h]
0x140002f5b  mov     edi, 103h
0x140002f60  mov     [r14], rax
0x140002f63  lea     rsi, [r13+0B8h]
0x140002f6a  mov     [r14+8], rcx
0x140002f6e  mov     [rcx], r14
0x140002f71  mov     [rax+8], r14
0x140002f75  jmp     loc_140002E76
0x140002f7a  mov     edi, 0C000000Eh
0x140002f7f  jmp     loc_140002D41
0x140002f84  test    rbp, rbp
0x140002f87  jz      loc_140002D99
0x140002f8d  lea     rax, [rsp+0A8h+var_60]
0x140002f92  mov     r9, rsi
0x140002f95  mov     r8, rbp
0x140002f98  mov     [rsp+0A8h+var_88], rax
0x140002f9d  xor     edx, edx
0x140002f9f  mov     ecx, 3
0x140002fa4  call    ?PartitionOverlapCount@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z; PartitionOverlapCount(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *)
0x140002fa9  mov     edi, eax
0x140002fab  test    eax, eax
0x140002fad  js      loc_140002D3A
0x140002fb3  mov     rax, rbp
0x140002fb6  xor     ebp, ebp
0x140002fb8  add     rsi, rax
0x140002fbb  jmp     loc_140002D99
0x140002fc0  dec     byte ptr [r13+43h]
0x140002fc4  xor     edx, edx; PriorityBoost
0x140002fc6  add     qword ptr [rbx], 0FFFFFFFFFFFFFFB8h
0x140002fca  mov     rcx, r13; Irp
0x140002fcd  mov     qword ptr [r13+38h], 0
0x140002fd5  mov     [r13+30h], edi
0x140002fd9  call    cs:__imp_IofCompleteRequest
0x140002fe0  nop     dword ptr [rax+rax+00h]
0x140002fe5  jmp     loc_140002DEF
0x140011c14  mov     rdx, [rsp+0A8h+arg_8]
0x140011c1c  lea     rax, [rsp+0A8h+var_60]
0x140011c21  lea     r9, ?PartitionOverlapIo@@YAJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@_K2PEAX@Z; int (__high *)(enum _PM_OVERLAP_TYPE, struct _PM_PATCH *, unsigned __int64, unsigned __int64, void *)
0x140011c28  mov     [rsp+0A8h+var_88], rax; void *
0x140011c2d  lea     rcx, [r15+138h]; struct _LIST_ENTRY *
0x140011c34  mov     r8d, [rdx+8]; unsigned __int64
0x140011c38  mov     rdx, [rdx+18h]; unsigned __int64
0x140011c3c  call    ?PmEnumerateOverlaps@@YAJPEAU_LIST_ENTRY@@_K1P6AJW4_PM_OVERLAP_TYPE@@PEAU_PM_PATCH@@11PEAX@Z4@Z; PmEnumerateOverlaps(_LIST_ENTRY *,unsigned __int64,unsigned __int64,long (*)(_PM_OVERLAP_TYPE,_PM_PATCH *,unsigned __int64,unsigned __int64,void *),void *)
0x140011c41  mov     edi, eax
0x140011c43  test    eax, eax
0x140011c45  js      loc_140002D3A
0x140011c4b  add     qword ptr [r13+0B8h], 0FFFFFFFFFFFFFFB8h
0x140011c53  xor     ebx, ebx
0x140011c55  dec     byte ptr [r13+43h]
0x140011c59  mov     rax, [r13+0B8h]
0x140011c60  mov     qword ptr [r13+38h], 0
0x140011c68  mov     dword ptr [r13+30h], 0
0x140011c70  or      byte ptr [rax+3], 1
0x140011c74  movsxd  rcx, dword ptr [rsp+0A8h+var_50]
0x140011c79  mov     [r13+78h], rcx
0x140011c7d  test    ecx, ecx
0x140011c7f  jz      short loc_140011CA3
0x140011c81  mov     rsi, [rsp+0A8h+arg_0]
0x140011c89  jmp     loc_140002ECC
0x140011c8e  mov     rcx, rbp; Irp
0x140011c91  call    cs:__imp_IoFreeIrp
0x140011c98  nop     dword ptr [rax+rax+00h]
0x140011c9d  nop
0x140011c9e  jmp     loc_140002D49
0x140011ca3  mov     edi, 103h
0x140011ca8  jmp     loc_140002DEF
```
