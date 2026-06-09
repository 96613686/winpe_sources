# KspMethodHandler

- ea: `0x18004a960`
- end: `0x18004b20f`
- name: `KspMethodHandler`
- size: `2223`
- prototype: `__int64 __fastcall(PIRP Irp, unsigned int, struct _LIST_ENTRY *, __int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), unsigned int, __int64, unsigned int)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800339a0`
- `0x180038c30`
- `0x180038c60`
- `0x180049c20`

## callees

- `0x180010154`
- `0x180010804`
- `0x180019c00`
- `0x180019cb0`
- `0x180019d00`
- `0x18001a000`
- `0x1800337b8`
- `0x18004a960`
- `0x180051600`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x18004aa06`
- `ntoskrnl!ProbeForRead` at `0x18004add5`
- `ntoskrnl!ProbeForRead` at `0x18004aa06`
- `ntoskrnl!ProbeForRead` at `0x18004add5`
- `ntoskrnl!ProbeForWrite` at `0x18004aaf4`
- `ntoskrnl!ProbeForWrite` at `0x18004adb6`
- `ntoskrnl!ProbeForWrite` at `0x18004aaf4`
- `ntoskrnl!ProbeForWrite` at `0x18004adb6`
- `ntoskrnl!ExAllocatePool2` at `0x18004ab0d`
- `ntoskrnl!ExAllocatePool2` at `0x18004ae42`
- `ntoskrnl!ExAllocatePool2` at `0x18004ab0d`
- `ntoskrnl!ExAllocatePool2` at `0x18004ae42`
- `ntoskrnl!MmUnlockPages` at `0x18004b014`
- `ntoskrnl!MmUnlockPages` at `0x18004b014`
- `ntoskrnl!MmProbeAndLockPages` at `0x18004af4f`
- `ntoskrnl!MmProbeAndLockPages` at `0x18004af4f`
- `ntoskrnl!IoAllocateMdl` at `0x18004af18`
- `ntoskrnl!IoAllocateMdl` at `0x18004af18`
- `ntoskrnl!IoFreeMdl` at `0x18004b024`
- `ntoskrnl!IoFreeMdl` at `0x18004b024`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18004af84`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18004b0a5`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18004af84`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18004b0a5`
- `ntoskrnl!ExRaiseStatus` at `0x18004af32`
- `ntoskrnl!ExRaiseStatus` at `0x18004afa2`
- `ntoskrnl!ExRaiseStatus` at `0x18004af32`
- `ntoskrnl!ExRaiseStatus` at `0x18004afa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004abcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004b045`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004abcb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004b045`

## pseudocode

```c
__int64 __fastcall KspMethodHandler(
        PIRP Irp,
        unsigned int a2,
        struct _LIST_ENTRY *a3,
        __int64 (__fastcall *a4)(_QWORD, _QWORD, _QWORD),
        unsigned int a5,
        __int64 a6,
        unsigned int a7)
{
  struct _LIST_ENTRY *v7; // r12
  __int64 IrpCount; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  unsigned int Options; // ecx
  SIZE_T Length; // r14
  unsigned int v14; // r13d
  struct _IRP *MasterIrp; // rdi
  unsigned int v16; // edi
  size_t v17; // r13
  int IsEnabledDeviceUsageNoInline; // eax
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rcx
  ULONG ULongFromUser; // esi
  ULONG LowPart; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // eax
  PNAMED_PIPE_CREATE_PARAMETERS v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  __int64 result; // rax
  struct _IRP *Pool2; // rax
  int v32; // eax
  PNAMED_PIPE_CREATE_PARAMETERS v33; // rdx
  char *v34; // rcx
  int v35; // r10d
  __int64 v36; // rax
  __int64 v37; // rdx
  unsigned int i; // r11d
  _QWORD *v39; // rax
  _QWORD *v40; // rsi
  unsigned __int64 v41; // r8
  _DWORD *v42; // r14
  __int64 (__fastcall *v43)(PIRP, struct _IRP *, _QWORD); // rax
  __int64 MethodItem; // rax
  __int64 v45; // r8
  int v46; // r11d
  __int64 v47; // rsi
  int v48; // eax
  int v49; // edx
  size_t v50; // r15
  __int64 (__fastcall *v51)(_QWORD, _QWORD, _QWORD); // r13
  unsigned int v52; // eax
  int v53; // eax
  char *v54; // rcx
  PNAMED_PIPE_CREATE_PARAMETERS v55; // rdx
  __int64 v56; // rcx
  char *v57; // rax
  int v58; // eax
  struct _MDL *Mdl; // rax
  PMDL v60; // rcx
  PVOID MappedSystemVa; // r8
  int v62; // eax
  int v63; // eax
  unsigned __int64 v64; // rax
  PMDL MdlAddress; // rcx
  ULONG_PTR v67; // rcx
  _OWORD **v68; // r12
  struct _IRP *j; // rcx
  unsigned int v70; // [rsp+30h] [rbp-88h]
  ULONG v71; // [rsp+34h] [rbp-84h]
  struct _IO_STACK_LOCATION *v72; // [rsp+40h] [rbp-78h]
  unsigned int Size; // [rsp+48h] [rbp-70h]
  __int128 v74; // [rsp+60h] [rbp-58h] BYREF
  __int64 v75; // [rsp+70h] [rbp-48h]
  struct _LIST_ENTRY *v76; // [rsp+D0h] [rbp+18h]

  v76 = a3;
  v7 = a3;
  IrpCount = 0;
  v74 = 0;
  v75 = 0;
  v71 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v72 = CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  v70 = Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v14 = (Length + 7) & 0xFFFFFFF8;
  Size = v14;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( MasterIrp )
  {
    if ( (*(_BYTE *)(&Irp->Tail.CompletionKey + 2) & 4) == 0 )
      MasterIrp = (struct _IRP *)((char *)MasterIrp + v14);
    goto LABEL_41;
  }
  if ( Options < 0x18 )
    return 3221225990LL;
  if ( v14 < (unsigned int)Length )
    return 3221225990LL;
  v16 = Options + v14;
  if ( Options + v14 < v14 )
    return 3221225990LL;
  if ( !Irp->RequestorMode )
  {
    MasterIrp = (struct _IRP *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
    goto LABEL_42;
  }
  v17 = Options;
  ProbeForRead(CurrentStackLocation->Parameters.CreatePipe.Parameters, Options, 1u);
  IsEnabledDeviceUsageNoInline = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  if ( IsEnabledDeviceUsageNoInline )
  {
    ULongFromUser = RtlReadULongFromUser(&Parameters->OutboundQuota);
    if ( (ULongFromUser & 0x10000000) != 0 && (unsigned int)v17 >= 0x20 )
    {
      LowPart = RtlReadULongFromUser(&v72->Parameters.CreatePipe.Parameters->DefaultTimeout);
LABEL_13:
      v71 = LowPart;
    }
  }
  else
  {
    ULongFromUser = Parameters->OutboundQuota;
    if ( (ULongFromUser & 0x10000000) != 0 && (unsigned int)v17 >= 0x20 )
    {
      LowPart = Parameters->DefaultTimeout.LowPart;
      goto LABEL_13;
    }
  }
  v22 = ULongFromUser & 0xEFFFFFFF;
  if ( (ULongFromUser & 0xEFFFFFFF) <= 5 )
  {
    if ( (ULongFromUser & 0xEFFFFFFF) == 5 )
      goto LABEL_20;
    if ( !v22 )
      goto LABEL_20;
    v23 = v22 - 1;
    if ( !v23 )
      goto LABEL_20;
    v24 = v23 - 1;
    if ( !v24 || v24 - 1 <= 1 )
      goto LABEL_20;
    return 3221225485LL;
  }
  v27 = v22 - 6;
  if ( v27 )
  {
    v28 = v27 - 1;
    if ( v28 )
    {
      v29 = v28 - 249;
      if ( !v29 || v29 == 256 )
      {
        if ( Irp->RequestorMode )
          ProbeForWrite(Irp->UserBuffer, Length, 1u);
        Pool2 = (struct _IRP *)ExAllocatePool2(99, v16, 1886409547);
        Irp->AssociatedIrp.MasterIrp = Pool2;
        Irp->Flags |= 0x30u;
        if ( (_DWORD)Length )
          Irp->Flags |= 0x40u;
        memset(Pool2, 0, Size);
        v32 = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
        v33 = v72->Parameters.CreatePipe.Parameters;
        v34 = (char *)Irp->AssociatedIrp.MasterIrp + Size;
        if ( v32 )
          RtlCopyFromUser(v34, v33, v17);
        else
          memmove(v34, v33, v17);
        MasterIrp = (struct _IRP *)((char *)Irp->AssociatedIrp.MasterIrp + Size);
        *(&MasterIrp->Flags + 1) = ULongFromUser;
        Irp->Tail.Overlay.DriverContext[2] = (PVOID)ULongFromUser;
        goto LABEL_37;
      }
      return 3221225485LL;
    }
  }
LABEL_20:
  v25 = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
  v26 = v72->Parameters.CreatePipe.Parameters;
  if ( v25 )
  {
    RtlCopyFromUser(&v74, v72->Parameters.CreatePipe.Parameters, 0x18u);
  }
  else
  {
    v74 = *(_OWORD *)&v26->NamedPipeType;
    v75 = *(_QWORD *)&v26->InboundQuota;
  }
  HIDWORD(v75) = ULongFromUser & 0x10000000 | 1;
  MasterIrp = (struct _IRP *)&v74;
LABEL_37:
  v14 = (Length + 7) & 0xFFFFFFF8;
  Options = v70;
LABEL_41:
  IrpCount = v71;
LABEL_42:
  v35 = *(&MasterIrp->Flags + 1);
  if ( (v35 & 0x10000000) != 0 )
  {
    if ( Options < 0x20 )
      return 3221225990LL;
    if ( a6 )
    {
      if ( MasterIrp != (struct _IRP *)&v74 )
        IrpCount = (unsigned int)MasterIrp->AssociatedIrp.IrpCount;
      if ( (unsigned int)IrpCount >= a7 )
        return 3221225488LL;
      _mm_lfence();
      v36 = *(_QWORD *)(a6 + 8 * IrpCount);
      if ( !v36 )
        return 3221226021LL;
      a2 = *(_DWORD *)(v36 + 16);
      if ( !a2 )
        return 3221226021LL;
      v7 = *(struct _LIST_ENTRY **)(v36 + 24);
      v76 = v7;
      a5 = *(_DWORD *)(v36 + 20);
    }
    v35 &= ~0x10000000u;
  }
  v37 = 40;
  if ( a5 )
    v37 = a5;
  for ( i = a2; ; --i )
  {
    if ( !i )
      goto LABEL_133;
    if ( *(struct _LIST_ENTRY **)&MasterIrp->Type == v7->Flink->Flink && MasterIrp->MdlAddress == (PMDL)v7->Flink->Blink )
      break;
    v7 = (struct _LIST_ENTRY *)((char *)v7 + 40);
    v76 = v7;
  }
  if ( (v35 & 0xFFF00) == 0 )
  {
    MethodItem = FindMethodItem(v7, v37, MasterIrp->Flags, a4);
    v47 = MethodItem;
    if ( MethodItem )
    {
      if ( Irp->AssociatedIrp.MasterIrp )
      {
        v64 = (unsigned __int64)Irp->Tail.Overlay.DriverContext[2];
        if ( (v64 & 4) != 0 && (_DWORD)Length && (v64 & 0xFFFFFFFFEFFFFFFBuLL) != 0 )
        {
          MdlAddress = Irp->MdlAddress;
          if ( !((MdlAddress->MdlFlags & 5) != 0
               ? MdlAddress->MappedSystemVa
               : MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u)) )
            return 3221225626LL;
        }
LABEL_126:
        Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = v7;
        if ( a5 )
          Irp->Tail.Overlay.DriverContext[3] = (PVOID)v47;
        if ( v72->Parameters.Create.Options >= *(_DWORD *)(v47 + 16) && (unsigned int)Length >= *(_DWORD *)(v47 + 20) )
          return (*(__int64 (__fastcall **)(PIRP, struct _IRP *))(v47 + 8))(Irp, MasterIrp);
        return 3221225507LL;
      }
      Irp->Tail.Overlay.DriverContext[2] = (PVOID)*(unsigned int *)(MethodItem + 32);
      if ( Irp->RequestorMode )
      {
        v48 = *(_DWORD *)(MethodItem + 32);
        if ( (v48 & 2) != 0 )
        {
          ProbeForWrite(Irp->UserBuffer, Length, 1u);
        }
        else if ( (v48 & 1) != 0 )
        {
          ProbeForRead(Irp->UserBuffer, Length, 1u);
        }
      }
      v49 = *(_DWORD *)(v47 + 32);
      if ( (v49 & 4) != 0 )
        v14 = 0;
      v50 = v14 + v70;
      v51 = a4;
      if ( a4 )
      {
        if ( (_DWORD)Length && (v49 & 2) != 0 && (*(_DWORD *)(v47 + 32) & 4) == 0 )
          LOBYTE(v45) = 1;
        else
          v45 = 0;
        result = a4(Irp, (unsigned int)v50, v45);
        if ( (int)result < 0 )
          return result;
      }
      else
      {
        Irp->AssociatedIrp.MasterIrp = (struct _IRP *)ExAllocatePool2(99, v50, 1886409547);
        Irp->Flags |= 0x30u;
      }
      memset(Irp->AssociatedIrp.MasterIrp, 0, v50);
      v52 = v70;
      if ( v70 > 0x18 )
      {
        v53 = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
        v54 = (char *)Irp->AssociatedIrp.MasterIrp + v50 - v70;
        v55 = v72->Parameters.CreatePipe.Parameters;
        if ( v53 )
        {
          if ( Irp->RequestorMode )
            RtlCopyFromUser(v54, v55, v70);
          else
            RtlCopyVolatileMemory(v54, v55, v70);
        }
        else
        {
          memmove(v54, v55, v70);
        }
        v7 = v76;
        v52 = v70;
        v51 = a4;
      }
      v56 = v52;
      v57 = (char *)Irp->AssociatedIrp.MasterIrp - v52;
      *(_OWORD *)&v57[v50] = *(_OWORD *)&MasterIrp->Type;
      *(_QWORD *)&v57[v50 + 16] = *(_QWORD *)&MasterIrp->Flags;
      MasterIrp = (struct _IRP *)((char *)Irp->AssociatedIrp.MasterIrp + v50 - v56);
      v58 = *(_DWORD *)(v47 + 32);
      if ( (v58 & 4) != 0 )
      {
        if ( (v58 & 3) != 0 )
        {
          if ( (_DWORD)Length )
          {
            Mdl = IoAllocateMdl(Irp->UserBuffer, Length, 0, 1u, Irp);
            Irp->MdlAddress = Mdl;
            if ( !Mdl )
              ExRaiseStatus(-1073741670);
            MmProbeAndLockPages(Mdl, Irp->RequestorMode, (LOCK_OPERATION)((*(_DWORD *)(v47 + 32) & 3) - 1));
          }
          v60 = Irp->MdlAddress;
          if ( (v60->MdlFlags & 5) != 0 )
            MappedSystemVa = v60->MappedSystemVa;
          else
            MappedSystemVa = MmMapLockedPagesSpecifyCache(v60, 0, MmCached, 0, 0, 0x40000010u);
          if ( !MappedSystemVa )
            ExRaiseStatus(-1073741670);
        }
        goto LABEL_126;
      }
      if ( !(_DWORD)Length )
        goto LABEL_126;
      v62 = v58 - 1;
      if ( v62 )
      {
        v63 = v62 - 1;
        if ( !v63 )
        {
LABEL_114:
          if ( !v51 )
            Irp->Flags |= 0x40u;
          goto LABEL_126;
        }
        if ( v63 != 1 )
          goto LABEL_126;
      }
      memmove(Irp->AssociatedIrp.MasterIrp, Irp->UserBuffer, Length);
      if ( *(_DWORD *)(v47 + 32) == 1 )
        goto LABEL_126;
      goto LABEL_114;
    }
    if ( !v46 )
    {
LABEL_133:
      if ( *(_QWORD *)&MasterIrp->Type != *(_QWORD *)&GUID_NULL.Data1
        || MasterIrp->MdlAddress != *(PMDL *)GUID_NULL.Data4 )
      {
        return 3221226032LL;
      }
      if ( MasterIrp->Flags || v35 != 256 )
        return 3221225485LL;
      if ( !(_DWORD)Length )
      {
        Irp->IoStatus.Information = 16LL * a2;
        return 2147483653LL;
      }
      if ( (_DWORD)Length == 4 )
      {
        *(_DWORD *)Irp->AssociatedIrp.MasterIrp = 16 * a2;
        goto LABEL_70;
      }
      v67 = 16LL * a2;
      if ( Length >= v67 )
      {
        Irp->IoStatus.Information = v67;
        v68 = (_OWORD **)v7 - 5 * a2;
        for ( j = Irp->AssociatedIrp.MasterIrp; a2; --a2 )
        {
          *(_OWORD *)&j->Type = **v68;
          j = (struct _IRP *)((char *)j + 16);
          v68 += 5;
        }
        return 0;
      }
      return 3221225507LL;
    }
    return 3221226021LL;
  }
  if ( v35 == 256 )
    return 0;
  if ( (unsigned int)Length < 4 )
    return 3221225507LL;
  v39 = (_QWORD *)FindMethodItem(v7, v37, MasterIrp->Flags, a4);
  v40 = v39;
  if ( !v39 )
    return 3221226021LL;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = v7;
  if ( a5 )
    Irp->Tail.Overlay.DriverContext[3] = v39;
  v41 = -(__int64)(Irp->RequestorMode != 0) & 0xFFFFFFFFFFFFFFA8uLL;
  v42 = *(PVOID *)((char *)&Irp->UserBuffer + v41);
  v43 = (__int64 (__fastcall *)(PIRP, struct _IRP *, _QWORD))v39[3];
  if ( !v43
    || (result = v43(Irp, MasterIrp, *(PVOID *)((char *)&Irp->UserBuffer + v41)), (_DWORD)result == -1073741802)
    || (_DWORD)result == 263 )
  {
    *v42 = *((_DWORD *)v40 + 8);
LABEL_70:
    Irp->IoStatus.Information = 4;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004a960  mov     r11, rsp
0x18004a963  mov     [r11+20h], r9
0x18004a967  mov     [r11+18h], r8
0x18004a96b  mov     [r11+8], rcx
0x18004a96f  push    rbx
0x18004a970  push    rsi
0x18004a971  push    rdi
0x18004a972  push    r12
0x18004a974  push    r13
0x18004a976  push    r14
0x18004a978  push    r15
0x18004a97a  sub     rsp, 80h
0x18004a981  mov     r12, r8
0x18004a984  mov     r15d, edx
0x18004a987  mov     rbx, rcx
0x18004a98a  xorps   xmm0, xmm0
0x18004a98d  xor     eax, eax
0x18004a98f  movups  [rsp+0B8h+var_58], xmm0
0x18004a994  mov     [r11-48h], rax
0x18004a998  mov     [r11-80h], rax
0x18004a99c  mov     dword ptr [rsp+0B8h+var_88+4], eax
0x18004a9a0  mov     rsi, [rcx+0B8h]
0x18004a9a7  mov     [rsp+0B8h+var_78], rsi
0x18004a9ac  mov     ecx, [rsi+10h]
0x18004a9af  mov     dword ptr [rsp+0B8h+var_88], ecx
0x18004a9b3  mov     r14d, [rsi+8]
0x18004a9b7  lea     r13d, [r14+7]
0x18004a9bb  and     r13d, 0FFFFFFF8h
0x18004a9bf  mov     dword ptr [rsp+0B8h+Size], r13d
0x18004a9c4  mov     rdi, [rbx+18h]
0x18004a9c8  test    rdi, rdi
0x18004a9cb  jnz     loc_18004ABF5
0x18004a9d1  cmp     ecx, 18h
0x18004a9d4  jb      loc_18004AC27
0x18004a9da  cmp     r13d, r14d
0x18004a9dd  jb      loc_18004AC27
0x18004a9e3  lea     edi, [rcx+r13]
0x18004a9e7  cmp     edi, r13d
0x18004a9ea  jb      loc_18004AC27
0x18004a9f0  cmp     [rbx+40h], al
0x18004a9f3  jz      loc_18004ABEA
0x18004a9f9  mov     r13d, ecx
0x18004a9fc  lea     r8d, [rax+1]; Alignment
0x18004aa00  mov     edx, ecx; Length
0x18004aa02  mov     rcx, [rsi+20h]; Address
0x18004aa06  call    cs:__imp_ProbeForRead
0x18004aa0d  nop     dword ptr [rax+rax+00h]
0x18004aa12  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18004aa17  mov     rcx, [rsi+20h]
0x18004aa1b  test    eax, eax
0x18004aa1d  jz      short loc_18004AA4E
0x18004aa1f  add     rcx, 14h
0x18004aa23  call    RtlReadULongFromUser
0x18004aa28  mov     esi, eax
0x18004aa2a  mov     dword ptr [rsp+0B8h+Size+4], eax
0x18004aa2e  bt      eax, 1Ch
0x18004aa32  jnb     short loc_18004AA6C
0x18004aa34  cmp     r13d, 20h ; ' '
0x18004aa38  jb      short loc_18004AA6C
0x18004aa3a  mov     rax, [rsp+0B8h+var_78]
0x18004aa3f  mov     rcx, [rax+20h]
0x18004aa43  add     rcx, 18h
0x18004aa47  call    RtlReadULongFromUser
0x18004aa4c  jmp     short loc_18004AA64
0x18004aa4e  mov     esi, [rcx+14h]
0x18004aa51  mov     dword ptr [rsp+0B8h+Size+4], esi
0x18004aa55  bt      esi, 1Ch
0x18004aa59  jnb     short loc_18004AA6C
0x18004aa5b  cmp     r13d, 20h ; ' '
0x18004aa5f  jb      short loc_18004AA6C
0x18004aa61  mov     eax, [rcx+18h]
0x18004aa64  mov     [rsp+0B8h+var_68], eax
0x18004aa68  mov     dword ptr [rsp+0B8h+var_88+4], eax
0x18004aa6c  mov     eax, esi
0x18004aa6e  btr     eax, 1Ch
0x18004aa72  cmp     eax, 5
0x18004aa75  ja      short loc_18004AABF
0x18004aa77  jz      short loc_18004AA91
0x18004aa79  test    eax, eax
0x18004aa7b  jz      short loc_18004AA91
0x18004aa7d  sub     eax, 1
0x18004aa80  jz      short loc_18004AA91
0x18004aa82  sub     eax, 1
0x18004aa85  jz      short loc_18004AA91
0x18004aa87  sub     eax, 1
0x18004aa8a  jz      short loc_18004AA91
0x18004aa8c  cmp     eax, 1
0x18004aa8f  jnz     short loc_18004AAD7
0x18004aa91  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18004aa96  mov     rcx, [rsp+0B8h+var_78]
0x18004aa9b  mov     rcx, [rcx+20h]
0x18004aa9f  test    eax, eax
0x18004aaa1  jz      loc_18004AB7F
0x18004aaa7  mov     r8d, 18h; Size
0x18004aaad  mov     rdx, rcx; Src
0x18004aab0  lea     rcx, [rsp+0B8h+var_58]; void *
0x18004aab5  call    RtlCopyFromUser
0x18004aaba  jmp     loc_18004AB92
0x18004aabf  sub     eax, 6
0x18004aac2  jz      short loc_18004AA91
0x18004aac4  sub     eax, 1
0x18004aac7  jz      short loc_18004AA91
0x18004aac9  sub     eax, 0F9h
0x18004aace  jz      short loc_18004AAE1
0x18004aad0  cmp     eax, 100h
0x18004aad5  jz      short loc_18004AAE1
0x18004aad7  mov     eax, 0C000000Dh
0x18004aadc  jmp     loc_18004B1FB
0x18004aae1  cmp     byte ptr [rbx+40h], 0
0x18004aae5  jz      short loc_18004AB00
0x18004aae7  mov     rdx, r14; Length
0x18004aaea  mov     r8d, 1; Alignment
0x18004aaf0  mov     rcx, [rbx+70h]; Address
0x18004aaf4  call    cs:__imp_ProbeForWrite
0x18004aafb  nop     dword ptr [rax+rax+00h]
0x18004ab00  mov     edx, edi
0x18004ab02  mov     ecx, 63h ; 'c'
0x18004ab07  mov     r8d, 7070534Bh
0x18004ab0d  call    cs:__imp_ExAllocatePool2
0x18004ab14  nop     dword ptr [rax+rax+00h]
0x18004ab19  mov     [rbx+18h], rax
0x18004ab1d  or      dword ptr [rbx+10h], 30h
0x18004ab21  mov     ecx, [rbx+10h]
0x18004ab24  test    r14d, r14d
0x18004ab27  jz      short loc_18004AB2F
0x18004ab29  or      ecx, 40h
0x18004ab2c  mov     [rbx+10h], ecx
0x18004ab2f  mov     edi, dword ptr [rsp+0B8h+Size]
0x18004ab33  mov     r8d, edi; Size
0x18004ab36  xor     edx, edx; Val
0x18004ab38  mov     rcx, rax; void *
0x18004ab3b  call    memset
0x18004ab40  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x18004ab45  mov     rcx, [rsp+0B8h+var_78]
0x18004ab4a  mov     rdx, [rcx+20h]; Src
0x18004ab4e  mov     rcx, [rbx+18h]
0x18004ab52  add     rcx, rdi; void *
0x18004ab55  mov     r8, r13; Size
0x18004ab58  test    eax, eax
0x18004ab5a  jz      short loc_18004AB63
0x18004ab5c  call    RtlCopyFromUser
0x18004ab61  jmp     short loc_18004AB68
0x18004ab63  call    memmove
0x18004ab68  add     rdi, [rbx+18h]
0x18004ab6c  mov     [rsp+0B8h+var_80], rdi
0x18004ab71  mov     [rdi+14h], esi
0x18004ab74  mov     eax, esi
0x18004ab76  mov     [rbx+88h], rax
0x18004ab7d  jmp     short loc_18004ABA9
0x18004ab7f  movups  xmm0, xmmword ptr [rcx]
0x18004ab82  movups  [rsp+0B8h+var_58], xmm0
0x18004ab87  movsd   xmm1, qword ptr [rcx+10h]
0x18004ab8c  movsd   [rsp+0B8h+var_48], xmm1
0x18004ab92  and     esi, 10000000h
0x18004ab98  or      esi, 1
0x18004ab9b  mov     dword ptr [rsp+0B8h+var_48+4], esi
0x18004ab9f  lea     rdi, [rsp+0B8h+var_58]
0x18004aba4  mov     [rsp+0B8h+var_80], rdi
0x18004aba9  mov     r13d, dword ptr [rsp+0B8h+Size]
0x18004abae  mov     ecx, dword ptr [rsp+0B8h+var_88]
0x18004abb2  jmp     short loc_18004AC13
0x18004abb4  mov     edi, eax
0x18004abb6  mov     rbx, [rsp+0B8h+arg_0]
0x18004abbe  cmp     qword ptr [rbx+18h], 0
0x18004abc3  jz      short loc_18004ABE3
0x18004abc5  xor     edx, edx; Tag
0x18004abc7  mov     rcx, [rbx+18h]; P
0x18004abcb  call    cs:__imp_ExFreePoolWithTag
0x18004abd2  nop     dword ptr [rax+rax+00h]
0x18004abd7  mov     qword ptr [rbx+18h], 0
0x18004abdf  and     dword ptr [rbx+10h], 0FFFFFFDFh
0x18004abe3  mov     eax, edi
0x18004abe5  jmp     loc_18004B1FB
0x18004abea  mov     rdi, [rsi+20h]
0x18004abee  mov     [rsp+0B8h+var_80], rdi
0x18004abf3  jmp     short loc_18004AC17
0x18004abf5  test    byte ptr [rbx+88h], 4
0x18004abfc  jz      short loc_18004AC05
0x18004abfe  mov     [rsp+0B8h+var_80], rdi
0x18004ac03  jmp     short loc_18004AC13
0x18004ac05  mov     eax, r13d
0x18004ac08  add     rax, rdi
0x18004ac0b  mov     rdi, rax
0x18004ac0e  mov     [rsp+0B8h+var_80], rax
0x18004ac13  mov     eax, dword ptr [rsp+0B8h+var_88+4]
0x18004ac17  mov     r10d, [rdi+14h]
0x18004ac1b  bt      r10d, 1Ch
0x18004ac20  jnb     short loc_18004AC96
0x18004ac22  cmp     ecx, 20h ; ' '
0x18004ac25  jnb     short loc_18004AC31
0x18004ac27  mov     eax, 0C0000206h
0x18004ac2c  jmp     loc_18004B1FB
0x18004ac31  mov     rcx, [rsp+0B8h+arg_28]
0x18004ac39  test    rcx, rcx
0x18004ac3c  jz      short loc_18004AC91
0x18004ac3e  lea     rdx, [rsp+0B8h+var_58]
0x18004ac43  cmp     rdi, rdx
0x18004ac46  jz      short loc_18004AC4B
0x18004ac48  mov     eax, [rdi+18h]
0x18004ac4b  cmp     eax, [rsp+0B8h+arg_30]
0x18004ac52  jb      short loc_18004AC5E
0x18004ac54  mov     eax, 0C0000010h
0x18004ac59  jmp     loc_18004B1FB
0x18004ac5e  lfence
0x18004ac61  mov     rax, [rcx+rax*8]
0x18004ac65  test    rax, rax
0x18004ac68  jz      loc_18004B1F6
0x18004ac6e  mov     r15d, [rax+10h]
0x18004ac72  test    r15d, r15d
0x18004ac75  jz      loc_18004B1F6
0x18004ac7b  mov     r12, [rax+18h]
0x18004ac7f  mov     [rsp+0B8h+arg_10], r12
0x18004ac87  mov     eax, [rax+14h]
0x18004ac8a  mov     [rsp+0B8h+arg_20], eax
0x18004ac91  btr     r10d, 1Ch
0x18004ac96  mov     edx, 28h ; '('
0x18004ac9b  mov     eax, [rsp+0B8h+arg_20]
0x18004aca2  test    eax, eax
0x18004aca4  cmovnz  edx, eax
0x18004aca7  mov     r11d, r15d
0x18004acaa  test    r11d, r11d
0x18004acad  jz      loc_18004B13A
0x18004acb3  mov     rcx, [r12]
0x18004acb7  mov     rax, [rcx]
0x18004acba  cmp     [rdi], rax
0x18004acbd  jnz     loc_18004B11D
0x18004acc3  mov     rax, [rcx+8]
0x18004acc7  cmp     [rdi+8], rax
0x18004accb  jnz     loc_18004B11D
0x18004acd1  test    r10d, 0FFF00h
0x18004acd8  jz      loc_18004AD6D
0x18004acde  cmp     r10d, 100h
0x18004ace5  jz      short loc_18004AD66
0x18004ace7  cmp     r14d, 4
0x18004aceb  jb      loc_18004B1AA
0x18004acf1  mov     r8d, [rdi+10h]
0x18004acf5  mov     rcx, r12
0x18004acf8  call    FindMethodItem
0x18004acfd  mov     rsi, rax
0x18004ad00  test    rax, rax
0x18004ad03  jz      loc_18004B1F6
0x18004ad09  mov     [rbx+78h], r12
0x18004ad0d  cmp     [rsp+0B8h+arg_20], 0
0x18004ad15  jz      short loc_18004AD1E
0x18004ad17  mov     [rbx+90h], rax
0x18004ad1e  mov     cl, [rbx+40h]
0x18004ad21  neg     cl
0x18004ad23  sbb     r8, r8
0x18004ad26  and     r8, 0FFFFFFFFFFFFFFA8h
0x18004ad2a  mov     r14, [r8+rbx+70h]
0x18004ad2f  mov     rax, [rax+18h]
0x18004ad33  test    rax, rax
0x18004ad36  jz      short loc_18004AD58
0x18004ad38  mov     r8, r14
0x18004ad3b  mov     rdx, rdi
0x18004ad3e  mov     rcx, rbx
0x18004ad41  call    _guard_dispatch_icall
0x18004ad46  cmp     eax, 0C0000016h
0x18004ad4b  jz      short loc_18004AD58
0x18004ad4d  cmp     eax, 107h
0x18004ad52  jnz     loc_18004B1FB
0x18004ad58  mov     eax, [rsi+20h]
0x18004ad5b  mov     [r14], eax
0x18004ad5e  mov     qword ptr [rbx+38h], 4
0x18004ad66  xor     eax, eax
0x18004ad68  jmp     loc_18004B1FB
0x18004ad6d  mov     r8d, [rdi+10h]
0x18004ad71  mov     rcx, r12
0x18004ad74  call    FindMethodItem
0x18004ad79  mov     rsi, rax
0x18004ad7c  test    rax, rax
0x18004ad7f  jz      loc_18004B131
0x18004ad85  mov     rcx, [rbx+18h]
0x18004ad89  test    rcx, rcx
0x18004ad8c  jnz     loc_18004B064
0x18004ad92  mov     ecx, [rax+20h]
0x18004ad95  mov     [rbx+88h], rcx
0x18004ad9c  cmp     byte ptr [rbx+40h], 0
0x18004ada0  jz      short loc_18004ADE1
0x18004ada2  mov     eax, [rax+20h]
0x18004ada5  test    al, 2
0x18004ada7  jz      short loc_18004ADC4
0x18004ada9  mov     rdx, r14; Length
0x18004adac  mov     r8d, 1; Alignment
0x18004adb2  mov     rcx, [rbx+70h]; Address
0x18004adb6  call    cs:__imp_ProbeForWrite
0x18004adbd  nop     dword ptr [rax+rax+00h]
0x18004adc2  jmp     short loc_18004ADE1
0x18004adc4  test    al, 1
0x18004adc6  jz      short loc_18004ADE1
0x18004adc8  mov     rdx, r14; Length
0x18004adcb  mov     r8d, 1; Alignment
0x18004add1  mov     rcx, [rbx+70h]; Address
0x18004add5  call    cs:__imp_ProbeForRead
0x18004addc  nop     dword ptr [rax+rax+00h]
0x18004ade1  mov     edx, [rsi+20h]
0x18004ade4  mov     ecx, edx
0x18004ade6  and     ecx, 4
0x18004ade9  mov     eax, 0
0x18004adee  cmovnz  r13d, eax
  ... truncated ...
```
