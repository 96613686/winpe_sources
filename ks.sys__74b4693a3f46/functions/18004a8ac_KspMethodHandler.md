# KspMethodHandler

- ea: `0x18004a8ac`
- end: `0x18004b0d9`
- name: `KspMethodHandler`
- size: `2093`
- prototype: `__int64 __fastcall(PIRP Irp, unsigned int, struct _LIST_ENTRY *, __int64 (__fastcall *)(PIRP, _QWORD, __int64), unsigned int, __int64, unsigned int)`
- caller_count: `4`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800339a0`
- `0x180038b20`
- `0x180038b50`
- `0x180049c20`

## callees

- `0x180010794`
- `0x180019bb0`
- `0x180019c60`
- `0x180019cc0`
- `0x180019fc0`
- `0x1800337b8`
- `0x18004a8ac`
- `0x180051460`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x18004aa28`
- `ntoskrnl!ProbeForWrite` at `0x18004acab`
- `ntoskrnl!ProbeForWrite` at `0x18004aa28`
- `ntoskrnl!ProbeForWrite` at `0x18004acab`
- `ntoskrnl!ExAllocatePool2` at `0x18004aa42`
- `ntoskrnl!ExAllocatePool2` at `0x18004ad34`
- `ntoskrnl!ExAllocatePool2` at `0x18004aa42`
- `ntoskrnl!ExAllocatePool2` at `0x18004ad34`
- `ntoskrnl!ProbeForRead` at `0x18004a94f`
- `ntoskrnl!ProbeForRead` at `0x18004acc8`
- `ntoskrnl!ProbeForRead` at `0x18004a94f`
- `ntoskrnl!ProbeForRead` at `0x18004acc8`
- `ntoskrnl!MmUnlockPages` at `0x18004aee1`
- `ntoskrnl!MmUnlockPages` at `0x18004aee1`
- `ntoskrnl!MmProbeAndLockPages` at `0x18004ae1b`
- `ntoskrnl!MmProbeAndLockPages` at `0x18004ae1b`
- `ntoskrnl!IoAllocateMdl` at `0x18004ade4`
- `ntoskrnl!IoAllocateMdl` at `0x18004ade4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18004ae4f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18004af70`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18004ae4f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18004af70`
- `ntoskrnl!ExRaiseStatus` at `0x18004adfe`
- `ntoskrnl!ExRaiseStatus` at `0x18004ae6d`
- `ntoskrnl!ExRaiseStatus` at `0x18004adfe`
- `ntoskrnl!ExRaiseStatus` at `0x18004ae6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004aac1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004af12`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004aac1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004af12`
- `ntoskrnl!IoFreeMdl` at `0x18004aef1`
- `ntoskrnl!IoFreeMdl` at `0x18004aef1`

## pseudocode

```c
__int64 __fastcall KspMethodHandler(
        PIRP Irp,
        unsigned int a2,
        struct _LIST_ENTRY *a3,
        __int64 (__fastcall *a4)(PIRP, _QWORD, __int64),
        unsigned int a5,
        __int64 a6,
        unsigned int a7)
{
  __int64 IrpCount; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  SIZE_T Options; // rdx
  SIZE_T Length; // rsi
  unsigned int v14; // ecx
  struct _IRP *MasterIrp; // rbx
  unsigned int v16; // r15d
  ULONG ULongFromUser; // eax
  int v18; // ebx
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  __int64 result; // rax
  struct _IRP *Pool2; // rax
  int v27; // r10d
  __int64 v28; // rax
  __int64 v29; // rdx
  unsigned int i; // r11d
  _QWORD *v31; // rax
  _QWORD *v32; // rsi
  unsigned __int64 v33; // r8
  _DWORD *v34; // r14
  __int64 (__fastcall *v35)(PIRP, struct _IRP *, _QWORD); // rax
  __int64 MethodItem; // rax
  __int64 v37; // r8
  int v38; // r11d
  __int64 v39; // r15
  int v40; // eax
  int v41; // edx
  int v42; // r14d
  size_t v43; // r14
  unsigned int v44; // eax
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // rdx
  char *v46; // rcx
  __int64 v47; // rdx
  size_t v48; // rcx
  struct _IRP *v49; // rax
  struct _IRP *v50; // rcx
  int v51; // eax
  struct _MDL *Mdl; // rax
  PMDL v53; // rcx
  PVOID MappedSystemVa; // r8
  int v55; // eax
  int v56; // eax
  unsigned __int64 v57; // rax
  PMDL MdlAddress; // rcx
  ULONG_PTR v60; // rcx
  _OWORD **v61; // r13
  struct _IRP *j; // rcx
  unsigned int v63; // [rsp+30h] [rbp-78h]
  unsigned int v64; // [rsp+34h] [rbp-74h]
  struct _IO_STACK_LOCATION *v65; // [rsp+40h] [rbp-68h]
  ULONG v66; // [rsp+48h] [rbp-60h]
  unsigned int Size; // [rsp+4Ch] [rbp-5Ch]
  __int128 v68; // [rsp+60h] [rbp-48h] BYREF
  __int64 v69; // [rsp+70h] [rbp-38h]

  IrpCount = 0;
  v68 = 0;
  v69 = 0;
  v64 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v65 = CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  v63 = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  v14 = (Length + 7) & 0xFFFFFFF8;
  Size = v14;
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( MasterIrp )
  {
    if ( (*(_BYTE *)(&Irp->Tail.CompletionKey + 2) & 4) == 0 )
      MasterIrp = (struct _IRP *)((char *)MasterIrp + v14);
    goto LABEL_30;
  }
  if ( (unsigned int)Options < 0x18 )
    return 3221225990LL;
  if ( v14 < (unsigned int)Length )
    return 3221225990LL;
  v16 = v14 + Options;
  if ( v14 + (unsigned int)Options < v14 )
    return 3221225990LL;
  if ( !Irp->RequestorMode )
  {
    MasterIrp = (struct _IRP *)CurrentStackLocation->Parameters.CreatePipe.Parameters;
    goto LABEL_31;
  }
  ProbeForRead(CurrentStackLocation->Parameters.CreatePipe.Parameters, Options, 1u);
  ULongFromUser = RtlReadULongFromUser(&v65->Parameters.CreatePipe.Parameters->OutboundQuota);
  v66 = ULongFromUser;
  v18 = ULongFromUser & 0x10000000;
  if ( (ULongFromUser & 0x10000000) != 0 && v63 >= 0x20 )
  {
    v64 = RtlReadULongFromUser(&v65->Parameters.CreatePipe.Parameters->DefaultTimeout);
    ULongFromUser = v66;
  }
  v19 = ULongFromUser & 0xEFFFFFFF;
  if ( v19 > 5 )
  {
    v22 = v19 - 6;
    if ( !v22 )
      goto LABEL_15;
    v23 = v22 - 1;
    if ( !v23 )
      goto LABEL_15;
    v24 = v23 - 249;
    if ( !v24 || v24 == 256 )
    {
      if ( Irp->RequestorMode )
        ProbeForWrite(Irp->UserBuffer, Length, 1u);
      Pool2 = (struct _IRP *)ExAllocatePool2(99, v16, 1886409547);
      Irp->AssociatedIrp.MasterIrp = Pool2;
      Irp->Flags |= 0x30u;
      if ( (_DWORD)Length )
        Irp->Flags |= 0x40u;
      memset(Pool2, 0, Size);
      RtlCopyFromUser((char *)Irp->AssociatedIrp.MasterIrp + Size, v65->Parameters.CreatePipe.Parameters, v63);
      MasterIrp = (struct _IRP *)((char *)Irp->AssociatedIrp.MasterIrp + Size);
      *(&MasterIrp->Flags + 1) = v66;
      Irp->Tail.Overlay.DriverContext[2] = (PVOID)v66;
      goto LABEL_16;
    }
    return 3221225485LL;
  }
  if ( v19 != 5 )
  {
    if ( v19 )
    {
      v20 = v19 - 1;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( v21 )
        {
          if ( v21 - 1 > 1 )
            return 3221225485LL;
        }
      }
    }
  }
LABEL_15:
  RtlCopyFromUser(&v68, v65->Parameters.CreatePipe.Parameters, 0x18u);
  HIDWORD(v69) = v18 | 1;
  MasterIrp = (struct _IRP *)&v68;
LABEL_16:
  LODWORD(Options) = v63;
LABEL_30:
  IrpCount = v64;
LABEL_31:
  v27 = *(&MasterIrp->Flags + 1);
  if ( (v27 & 0x10000000) != 0 )
  {
    if ( (unsigned int)Options < 0x20 )
      return 3221225990LL;
    if ( a6 )
    {
      if ( MasterIrp != (struct _IRP *)&v68 )
        IrpCount = (unsigned int)MasterIrp->AssociatedIrp.IrpCount;
      if ( (unsigned int)IrpCount >= a7 )
        return 3221225488LL;
      _mm_lfence();
      v28 = *(_QWORD *)(a6 + 8 * IrpCount);
      if ( !v28 )
        return 3221226021LL;
      a2 = *(_DWORD *)(v28 + 16);
      if ( !a2 )
        return 3221226021LL;
      a3 = *(struct _LIST_ENTRY **)(v28 + 24);
      a5 = *(_DWORD *)(v28 + 20);
    }
    v27 &= ~0x10000000u;
  }
  v29 = 40;
  if ( a5 )
    v29 = a5;
  for ( i = a2; ; --i )
  {
    if ( !i )
      goto LABEL_120;
    if ( *(struct _LIST_ENTRY **)&MasterIrp->Type == a3->Flink->Flink && MasterIrp->MdlAddress == (PMDL)a3->Flink->Blink )
      break;
    a3 = (struct _LIST_ENTRY *)((char *)a3 + 40);
  }
  if ( (v27 & 0xFFF00) == 0 )
  {
    MethodItem = FindMethodItem(a3, v29, MasterIrp->Flags);
    v39 = MethodItem;
    if ( MethodItem )
    {
      if ( Irp->AssociatedIrp.MasterIrp )
      {
        v57 = (unsigned __int64)Irp->Tail.Overlay.DriverContext[2];
        if ( (v57 & 4) != 0 && (_DWORD)Length && (v57 & 0xFFFFFFFFEFFFFFFBuLL) != 0 )
        {
          MdlAddress = Irp->MdlAddress;
          if ( !((MdlAddress->MdlFlags & 5) != 0
               ? MdlAddress->MappedSystemVa
               : MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u)) )
            return 3221225626LL;
        }
LABEL_113:
        Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = a3;
        if ( a5 )
          Irp->Tail.Overlay.DriverContext[3] = (PVOID)v39;
        if ( v65->Parameters.Create.Options >= *(_DWORD *)(v39 + 16) && (unsigned int)Length >= *(_DWORD *)(v39 + 20) )
          return (*(__int64 (__fastcall **)(PIRP, struct _IRP *))(v39 + 8))(Irp, MasterIrp);
        return 3221225507LL;
      }
      Irp->Tail.Overlay.DriverContext[2] = (PVOID)*(unsigned int *)(MethodItem + 32);
      if ( Irp->RequestorMode )
      {
        v40 = *(_DWORD *)(MethodItem + 32);
        if ( (v40 & 2) != 0 )
        {
          ProbeForWrite(Irp->UserBuffer, Length, 1u);
        }
        else if ( (v40 & 1) != 0 )
        {
          ProbeForRead(Irp->UserBuffer, Length, 1u);
        }
      }
      v41 = *(_DWORD *)(v39 + 32);
      v42 = (Length + 7) & 0xFFFFFFF8;
      if ( (v41 & 4) != 0 )
        v42 = 0;
      v43 = v63 + v42;
      if ( a4 )
      {
        if ( (_DWORD)Length && (v41 & 2) != 0 && (*(_DWORD *)(v39 + 32) & 4) == 0 )
          LOBYTE(v37) = 1;
        else
          v37 = 0;
        result = a4(Irp, (unsigned int)v43, v37);
        if ( (int)result < 0 )
          return result;
      }
      else
      {
        Irp->AssociatedIrp.MasterIrp = (struct _IRP *)ExAllocatePool2(99, v43, 1886409547);
        Irp->Flags |= 0x30u;
      }
      memset(Irp->AssociatedIrp.MasterIrp, 0, v43);
      v44 = v63;
      if ( v63 > 0x18 )
      {
        Parameters = v65->Parameters.CreatePipe.Parameters;
        v46 = (char *)Irp->AssociatedIrp.MasterIrp + v43 - v63;
        if ( Irp->RequestorMode )
          RtlCopyFromUser(v46, Parameters, v63);
        else
          RtlCopyVolatileMemory(v46, Parameters, v63);
        v44 = v63;
      }
      v47 = v44;
      v48 = v43 - v44;
      v49 = Irp->AssociatedIrp.MasterIrp;
      *(_OWORD *)((char *)&v49->Type + v48) = *(_OWORD *)&MasterIrp->Type;
      *(_QWORD *)((char *)&v49->Flags + v48) = *(_QWORD *)&MasterIrp->Flags;
      v50 = Irp->AssociatedIrp.MasterIrp;
      MasterIrp = (struct _IRP *)((char *)v50 + v43 - v47);
      v51 = *(_DWORD *)(v39 + 32);
      if ( (v51 & 4) != 0 )
      {
        if ( (v51 & 3) != 0 )
        {
          if ( (_DWORD)Length )
          {
            Mdl = IoAllocateMdl(Irp->UserBuffer, Length, 0, 1u, Irp);
            Irp->MdlAddress = Mdl;
            if ( !Mdl )
              ExRaiseStatus(-1073741670);
            MmProbeAndLockPages(Mdl, Irp->RequestorMode, (LOCK_OPERATION)((*(_DWORD *)(v39 + 32) & 3) - 1));
          }
          v53 = Irp->MdlAddress;
          if ( (v53->MdlFlags & 5) != 0 )
            MappedSystemVa = v53->MappedSystemVa;
          else
            MappedSystemVa = MmMapLockedPagesSpecifyCache(v53, 0, MmCached, 0, 0, 0x40000010u);
          if ( !MappedSystemVa )
            ExRaiseStatus(-1073741670);
        }
        goto LABEL_113;
      }
      if ( !(_DWORD)Length )
        goto LABEL_113;
      v55 = v51 - 1;
      if ( v55 )
      {
        v56 = v55 - 1;
        if ( !v56 )
        {
LABEL_101:
          if ( !a4 )
            Irp->Flags |= 0x40u;
          goto LABEL_113;
        }
        if ( v56 != 1 )
          goto LABEL_113;
      }
      memmove(v50, Irp->UserBuffer, Length);
      if ( *(_DWORD *)(v39 + 32) == 1 )
        goto LABEL_113;
      goto LABEL_101;
    }
    if ( !v38 )
    {
LABEL_120:
      if ( *(_QWORD *)&MasterIrp->Type != *(_QWORD *)&GUID_NULL.Data1
        || MasterIrp->MdlAddress != *(PMDL *)GUID_NULL.Data4 )
      {
        return 3221226032LL;
      }
      if ( MasterIrp->Flags || v27 != 256 )
        return 3221225485LL;
      if ( !(_DWORD)Length )
      {
        Irp->IoStatus.Information = 16LL * a2;
        return 2147483653LL;
      }
      if ( (_DWORD)Length == 4 )
      {
        *(_DWORD *)Irp->AssociatedIrp.MasterIrp = 16 * a2;
        goto LABEL_59;
      }
      v60 = 16LL * a2;
      if ( Length >= v60 )
      {
        Irp->IoStatus.Information = v60;
        v61 = (_OWORD **)a3 - 5 * a2;
        for ( j = Irp->AssociatedIrp.MasterIrp; a2; --a2 )
        {
          *(_OWORD *)&j->Type = **v61;
          j = (struct _IRP *)((char *)j + 16);
          v61 += 5;
        }
        return 0;
      }
      return 3221225507LL;
    }
    return 3221226021LL;
  }
  if ( v27 == 256 )
    return 0;
  if ( (unsigned int)Length < 4 )
    return 3221225507LL;
  v31 = (_QWORD *)FindMethodItem(a3, v29, MasterIrp->Flags);
  v32 = v31;
  if ( !v31 )
    return 3221226021LL;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = a3;
  if ( a5 )
    Irp->Tail.Overlay.DriverContext[3] = v31;
  v33 = -(__int64)(Irp->RequestorMode != 0) & 0xFFFFFFFFFFFFFFA8uLL;
  v34 = *(PVOID *)((char *)&Irp->UserBuffer + v33);
  v35 = (__int64 (__fastcall *)(PIRP, struct _IRP *, _QWORD))v31[3];
  if ( !v35
    || (result = v35(Irp, MasterIrp, *(PVOID *)((char *)&Irp->UserBuffer + v33)), (_DWORD)result == 263)
    || (_DWORD)result == -1073741802 )
  {
    *v34 = *((_DWORD *)v32 + 8);
LABEL_59:
    Irp->IoStatus.Information = 4;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004a8ac  mov     r11, rsp
0x18004a8af  mov     [r11+10h], rbx
0x18004a8b3  mov     [r11+18h], rsi
0x18004a8b7  mov     [r11+20h], r9
0x18004a8bb  mov     [r11+8], rcx
0x18004a8bf  push    rdi
0x18004a8c0  push    r12
0x18004a8c2  push    r13
0x18004a8c4  push    r14
0x18004a8c6  push    r15
0x18004a8c8  sub     rsp, 80h
0x18004a8cf  mov     r13, r8
0x18004a8d2  mov     r14d, edx
0x18004a8d5  mov     rdi, rcx
0x18004a8d8  xorps   xmm0, xmm0
0x18004a8db  xor     eax, eax
0x18004a8dd  movups  [rsp+0A8h+var_48], xmm0
0x18004a8e2  mov     [r11-38h], rax
0x18004a8e6  mov     [r11-70h], rax
0x18004a8ea  mov     dword ptr [rsp+0A8h+var_78+4], eax
0x18004a8ee  mov     r9, [rcx+0B8h]
0x18004a8f5  mov     [rsp+0A8h+var_68], r9
0x18004a8fa  mov     edx, [r9+10h]; Length
0x18004a8fe  mov     dword ptr [rsp+0A8h+var_78], edx
0x18004a902  mov     esi, [r9+8]
0x18004a906  lea     ecx, [rsi+7]
0x18004a909  and     ecx, 0FFFFFFF8h
0x18004a90c  mov     [rsp+0A8h+Size], ecx
0x18004a910  mov     rbx, [rdi+18h]
0x18004a914  test    rbx, rbx
0x18004a917  jnz     loc_18004AAF1
0x18004a91d  cmp     edx, 18h
0x18004a920  jb      loc_18004AB28
0x18004a926  cmp     ecx, esi
0x18004a928  jb      loc_18004AB28
0x18004a92e  lea     r15d, [rcx+rdx]
0x18004a932  cmp     r15d, ecx
0x18004a935  jb      loc_18004AB28
0x18004a93b  cmp     [rdi+40h], al
0x18004a93e  jz      loc_18004AAE0
0x18004a944  lea     r12d, [rax+1]
0x18004a948  mov     r8d, r12d; Alignment
0x18004a94b  mov     rcx, [r9+20h]; Address
0x18004a94f  call    cs:__imp_ProbeForRead
0x18004a956  nop     dword ptr [rax+rax+00h]
0x18004a95b  mov     rdx, [rsp+0A8h+var_68]
0x18004a960  mov     rcx, [rdx+20h]
0x18004a964  add     rcx, 14h
0x18004a968  call    RtlReadULongFromUser
0x18004a96d  mov     [rsp+0A8h+var_60], eax
0x18004a971  mov     ebx, eax
0x18004a973  and     ebx, 10000000h
0x18004a979  jz      short loc_18004A9A0
0x18004a97b  cmp     dword ptr [rsp+0A8h+var_78], 20h ; ' '
0x18004a980  jb      short loc_18004A9A0
0x18004a982  mov     rax, [rsp+0A8h+var_68]
0x18004a987  mov     rcx, [rax+20h]
0x18004a98b  add     rcx, 18h
0x18004a98f  call    RtlReadULongFromUser
0x18004a994  mov     dword ptr [rsp+0A8h+var_78+4], eax
0x18004a998  mov     [rsp+0A8h+var_50], eax
0x18004a99c  mov     eax, [rsp+0A8h+var_60]
0x18004a9a0  btr     eax, 1Ch
0x18004a9a4  cmp     eax, 5
0x18004a9a7  ja      short loc_18004A9F6
0x18004a9a9  jz      short loc_18004A9C3
0x18004a9ab  test    eax, eax
0x18004a9ad  jz      short loc_18004A9C3
0x18004a9af  sub     eax, r12d
0x18004a9b2  jz      short loc_18004A9C3
0x18004a9b4  sub     eax, r12d
0x18004a9b7  jz      short loc_18004A9C3
0x18004a9b9  sub     eax, r12d
0x18004a9bc  jz      short loc_18004A9C3
0x18004a9be  cmp     eax, r12d
0x18004a9c1  jnz     short loc_18004AA0E
0x18004a9c3  mov     r8d, 18h; Size
0x18004a9c9  mov     rax, [rsp+0A8h+var_68]
0x18004a9ce  mov     rdx, [rax+20h]; Src
0x18004a9d2  lea     rcx, [rsp+0A8h+var_48]; void *
0x18004a9d7  call    RtlCopyFromUser
0x18004a9dc  or      ebx, r12d
0x18004a9df  mov     [rsp+0A8h+var_34], ebx
0x18004a9e3  lea     rbx, [rsp+0A8h+var_48]
0x18004a9e8  mov     [rsp+0A8h+var_70], rbx
0x18004a9ed  mov     edx, dword ptr [rsp+0A8h+var_78]
0x18004a9f1  jmp     loc_18004AB14
0x18004a9f6  sub     eax, 6
0x18004a9f9  jz      short loc_18004A9C3
0x18004a9fb  sub     eax, r12d
0x18004a9fe  jz      short loc_18004A9C3
0x18004aa00  sub     eax, 0F9h
0x18004aa05  jz      short loc_18004AA18
0x18004aa07  cmp     eax, 100h
0x18004aa0c  jz      short loc_18004AA18
0x18004aa0e  mov     eax, 0C000000Dh
0x18004aa13  jmp     loc_18004B0BB
0x18004aa18  cmp     byte ptr [rdi+40h], 0
0x18004aa1c  jz      short loc_18004AA34
0x18004aa1e  mov     rdx, rsi; Length
0x18004aa21  mov     r8d, r12d; Alignment
0x18004aa24  mov     rcx, [rdi+70h]; Address
0x18004aa28  call    cs:__imp_ProbeForWrite
0x18004aa2f  nop     dword ptr [rax+rax+00h]
0x18004aa34  mov     edx, r15d
0x18004aa37  mov     ecx, 63h ; 'c'
0x18004aa3c  mov     r8d, 7070534Bh
0x18004aa42  call    cs:__imp_ExAllocatePool2
0x18004aa49  nop     dword ptr [rax+rax+00h]
0x18004aa4e  mov     [rdi+18h], rax
0x18004aa52  or      dword ptr [rdi+10h], 30h
0x18004aa56  mov     ecx, [rdi+10h]
0x18004aa59  test    esi, esi
0x18004aa5b  jz      short loc_18004AA63
0x18004aa5d  or      ecx, 40h
0x18004aa60  mov     [rdi+10h], ecx
0x18004aa63  mov     ebx, [rsp+0A8h+Size]
0x18004aa67  mov     r8d, ebx; Size
0x18004aa6a  xor     edx, edx; Val
0x18004aa6c  mov     rcx, rax; void *
0x18004aa6f  call    memset
0x18004aa74  mov     rcx, [rdi+18h]
0x18004aa78  add     rcx, rbx; void *
0x18004aa7b  mov     r8d, dword ptr [rsp+0A8h+var_78]; Size
0x18004aa80  mov     rax, [rsp+0A8h+var_68]
0x18004aa85  mov     rdx, [rax+20h]; Src
0x18004aa89  call    RtlCopyFromUser
0x18004aa8e  add     rbx, [rdi+18h]
0x18004aa92  mov     [rsp+0A8h+var_70], rbx
0x18004aa97  mov     eax, [rsp+0A8h+var_60]
0x18004aa9b  mov     [rbx+14h], eax
0x18004aa9e  mov     [rdi+88h], rax
0x18004aaa5  jmp     loc_18004A9ED
0x18004aaaa  mov     edi, eax
0x18004aaac  mov     rbx, [rsp+0A8h+arg_0]
0x18004aab4  cmp     qword ptr [rbx+18h], 0
0x18004aab9  jz      short loc_18004AAD9
0x18004aabb  xor     edx, edx; Tag
0x18004aabd  mov     rcx, [rbx+18h]; P
0x18004aac1  call    cs:__imp_ExFreePoolWithTag
0x18004aac8  nop     dword ptr [rax+rax+00h]
0x18004aacd  mov     qword ptr [rbx+18h], 0
0x18004aad5  and     dword ptr [rbx+10h], 0FFFFFFDFh
0x18004aad9  mov     eax, edi
0x18004aadb  jmp     loc_18004B0BB
0x18004aae0  mov     rbx, [r9+20h]
0x18004aae4  mov     [rsp+0A8h+var_70], rbx
0x18004aae9  mov     r12d, 1
0x18004aaef  jmp     short loc_18004AB18
0x18004aaf1  mov     r12d, 1
0x18004aaf7  test    byte ptr [rdi+88h], 4
0x18004aafe  jz      short loc_18004AB07
0x18004ab00  mov     [rsp+0A8h+var_70], rbx
0x18004ab05  jmp     short loc_18004AB14
0x18004ab07  mov     eax, ecx
0x18004ab09  add     rax, rbx
0x18004ab0c  mov     rbx, rax
0x18004ab0f  mov     [rsp+0A8h+var_70], rax
0x18004ab14  mov     eax, dword ptr [rsp+0A8h+var_78+4]
0x18004ab18  mov     r10d, [rbx+14h]
0x18004ab1c  bt      r10d, 1Ch
0x18004ab21  jnb     short loc_18004AB8F
0x18004ab23  cmp     edx, 20h ; ' '
0x18004ab26  jnb     short loc_18004AB32
0x18004ab28  mov     eax, 0C0000206h
0x18004ab2d  jmp     loc_18004B0BB
0x18004ab32  mov     rcx, [rsp+0A8h+arg_28]
0x18004ab3a  test    rcx, rcx
0x18004ab3d  jz      short loc_18004AB8A
0x18004ab3f  lea     rdx, [rsp+0A8h+var_48]
0x18004ab44  cmp     rbx, rdx
0x18004ab47  jz      short loc_18004AB4C
0x18004ab49  mov     eax, [rbx+18h]
0x18004ab4c  cmp     eax, [rsp+0A8h+arg_30]
0x18004ab53  jb      short loc_18004AB5F
0x18004ab55  mov     eax, 0C0000010h
0x18004ab5a  jmp     loc_18004B0BB
0x18004ab5f  lfence
0x18004ab62  mov     rax, [rcx+rax*8]
0x18004ab66  test    rax, rax
0x18004ab69  jz      loc_18004B0B6
0x18004ab6f  mov     r14d, [rax+10h]
0x18004ab73  test    r14d, r14d
0x18004ab76  jz      loc_18004B0B6
0x18004ab7c  mov     r13, [rax+18h]
0x18004ab80  mov     eax, [rax+14h]
0x18004ab83  mov     [rsp+0A8h+arg_20], eax
0x18004ab8a  btr     r10d, 1Ch
0x18004ab8f  mov     edx, 28h ; '('
0x18004ab94  mov     eax, [rsp+0A8h+arg_20]
0x18004ab9b  test    eax, eax
0x18004ab9d  cmovnz  edx, eax
0x18004aba0  mov     r11d, r14d
0x18004aba3  test    r11d, r11d
0x18004aba6  jz      loc_18004AFFD
0x18004abac  mov     rcx, [r13+0]
0x18004abb0  mov     rax, [rcx]
0x18004abb3  cmp     [rbx], rax
0x18004abb6  jnz     loc_18004AFE8
0x18004abbc  mov     rax, [rcx+8]
0x18004abc0  cmp     [rbx+8], rax
0x18004abc4  jnz     loc_18004AFE8
0x18004abca  test    r10d, 0FFF00h
0x18004abd1  jz      loc_18004AC65
0x18004abd7  cmp     r10d, 100h
0x18004abde  jz      short loc_18004AC5E
0x18004abe0  cmp     esi, 4
0x18004abe3  jb      loc_18004B06B
0x18004abe9  mov     r8d, [rbx+10h]
0x18004abed  mov     rcx, r13
0x18004abf0  call    FindMethodItem
0x18004abf5  mov     rsi, rax
0x18004abf8  test    rax, rax
0x18004abfb  jz      loc_18004B0B6
0x18004ac01  mov     [rdi+78h], r13
0x18004ac05  cmp     [rsp+0A8h+arg_20], 0
0x18004ac0d  jz      short loc_18004AC16
0x18004ac0f  mov     [rdi+90h], rax
0x18004ac16  mov     cl, [rdi+40h]
0x18004ac19  neg     cl
0x18004ac1b  sbb     r8, r8
0x18004ac1e  and     r8, 0FFFFFFFFFFFFFFA8h
0x18004ac22  mov     r14, [r8+rdi+70h]
0x18004ac27  mov     rax, [rax+18h]
0x18004ac2b  test    rax, rax
0x18004ac2e  jz      short loc_18004AC50
0x18004ac30  mov     r8, r14
0x18004ac33  mov     rdx, rbx
0x18004ac36  mov     rcx, rdi
0x18004ac39  call    _guard_dispatch_icall
0x18004ac3e  cmp     eax, 107h
0x18004ac43  jz      short loc_18004AC50
0x18004ac45  cmp     eax, 0C0000016h
0x18004ac4a  jnz     loc_18004B0BB
0x18004ac50  mov     eax, [rsi+20h]
0x18004ac53  mov     [r14], eax
0x18004ac56  mov     qword ptr [rdi+38h], 4
0x18004ac5e  xor     eax, eax
0x18004ac60  jmp     loc_18004B0BB
0x18004ac65  mov     r8d, [rbx+10h]
0x18004ac69  mov     rcx, r13
0x18004ac6c  call    FindMethodItem
0x18004ac71  mov     r15, rax
0x18004ac74  test    rax, rax
0x18004ac77  jz      loc_18004AFF4
0x18004ac7d  mov     rcx, [rdi+18h]
0x18004ac81  test    rcx, rcx
0x18004ac84  jnz     loc_18004AF31
0x18004ac8a  mov     ecx, [rax+20h]
0x18004ac8d  mov     [rdi+88h], rcx
0x18004ac94  cmp     byte ptr [rdi+40h], 0
0x18004ac98  jz      short loc_18004ACD4
0x18004ac9a  mov     eax, [rax+20h]
0x18004ac9d  test    al, 2
0x18004ac9f  jz      short loc_18004ACB9
0x18004aca1  mov     rdx, rsi; Length
0x18004aca4  mov     r8d, r12d; Alignment
0x18004aca7  mov     rcx, [rdi+70h]; Address
0x18004acab  call    cs:__imp_ProbeForWrite
0x18004acb2  nop     dword ptr [rax+rax+00h]
0x18004acb7  jmp     short loc_18004ACD4
0x18004acb9  test    r12b, al
0x18004acbc  jz      short loc_18004ACD4
0x18004acbe  mov     rdx, rsi; Length
0x18004acc1  mov     r8d, r12d; Alignment
0x18004acc4  mov     rcx, [rdi+70h]; Address
0x18004acc8  call    cs:__imp_ProbeForRead
0x18004accf  nop     dword ptr [rax+rax+00h]
0x18004acd4  mov     edx, [r15+20h]
0x18004acd8  mov     ecx, edx
0x18004acda  and     ecx, 4
0x18004acdd  mov     eax, 0
0x18004ace2  mov     r14d, [rsp+0A8h+Size]
0x18004ace7  cmovnz  r14d, eax
0x18004aceb  add     r14d, dword ptr [rsp+0A8h+var_78]
0x18004acf0  mov     rax, [rsp+0A8h+arg_18]
0x18004acf8  test    rax, rax
0x18004acfb  jz      short loc_18004AD26
0x18004acfd  test    esi, esi
0x18004acff  jz      short loc_18004AD0F
0x18004ad01  test    dl, 2
0x18004ad04  jz      short loc_18004AD0F
0x18004ad06  test    ecx, ecx
0x18004ad08  jnz     short loc_18004AD0F
0x18004ad0a  mov     r8b, r12b
0x18004ad0d  jmp     short loc_18004AD12
0x18004ad0f  xor     r8d, r8d
0x18004ad12  mov     edx, r14d
0x18004ad15  mov     rcx, rdi
0x18004ad18  call    _guard_dispatch_icall
0x18004ad1d  test    eax, eax
0x18004ad1f  jns     short loc_18004AD48
0x18004ad21  jmp     loc_18004B0BB
0x18004ad26  mov     r8d, 7070534Bh
0x18004ad2c  mov     rdx, r14
0x18004ad2f  mov     ecx, 63h ; 'c'
0x18004ad34  call    cs:__imp_ExAllocatePool2
0x18004ad3b  nop     dword ptr [rax+rax+00h]
0x18004ad40  mov     [rdi+18h], rax
0x18004ad44  or      dword ptr [rdi+10h], 30h
  ... truncated ...
```
