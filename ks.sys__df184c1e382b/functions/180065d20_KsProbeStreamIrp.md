# KsProbeStreamIrp

- ea: `0x180065d20`
- end: `0x1800664e2`
- name: `KsProbeStreamIrp`
- size: `1986`
- prototype: `NTSTATUS __stdcall(PIRP Irp, ULONG ProbeFlags, ULONG HeaderSize)`
- caller_count: `5`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180009c40`
- `0x180009c9c`
- `0x18000e800`
- `0x18000f854`
- `0x180017840`

## callees

- `0x180005df0`
- `0x18000ad48`
- `0x180010154`
- `0x180010804`
- `0x180019d00`
- `0x180065d20`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x180065e72`
- `ntoskrnl!ProbeForRead` at `0x180065e72`
- `ntoskrnl!ProbeForWrite` at `0x180065e50`
- `ntoskrnl!ProbeForWrite` at `0x180065e8d`
- `ntoskrnl!ProbeForWrite` at `0x180065e50`
- `ntoskrnl!ProbeForWrite` at `0x180065e8d`
- `ntoskrnl!ExAllocatePool2` at `0x180065e1f`
- `ntoskrnl!ExAllocatePool2` at `0x180065e1f`
- `ntoskrnl!MmUnlockPages` at `0x180066496`
- `ntoskrnl!MmUnlockPages` at `0x180066496`
- `ntoskrnl!MmProbeAndLockPages` at `0x18006637c`
- `ntoskrnl!MmProbeAndLockPages` at `0x18006637c`
- `ntoskrnl!IoAllocateMdl` at `0x1800660b4`
- `ntoskrnl!IoAllocateMdl` at `0x180066185`
- `ntoskrnl!IoAllocateMdl` at `0x1800661b3`
- `ntoskrnl!IoAllocateMdl` at `0x18006622f`
- `ntoskrnl!IoAllocateMdl` at `0x1800660b4`
- `ntoskrnl!IoAllocateMdl` at `0x180066185`
- `ntoskrnl!IoAllocateMdl` at `0x1800661b3`
- `ntoskrnl!IoAllocateMdl` at `0x18006622f`
- `ntoskrnl!IoFreeMdl` at `0x1800664ac`
- `ntoskrnl!IoFreeMdl` at `0x1800664ac`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800663bd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180066451`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800663bd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180066451`
- `ntoskrnl!ExRaiseStatus` at `0x180065dd6`
- `ntoskrnl!ExRaiseStatus` at `0x180065eff`
- `ntoskrnl!ExRaiseStatus` at `0x180065f26`
- `ntoskrnl!ExRaiseStatus` at `0x180065f44`
- `ntoskrnl!ExRaiseStatus` at `0x180065f6c`
- `ntoskrnl!ExRaiseStatus` at `0x180065f7d`
- `ntoskrnl!ExRaiseStatus` at `0x180065f92`
- `ntoskrnl!ExRaiseStatus` at `0x180065fac`
- `ntoskrnl!ExRaiseStatus` at `0x180065fd0`
- `ntoskrnl!ExRaiseStatus` at `0x18006603f`
- `ntoskrnl!ExRaiseStatus` at `0x180066064`
- `ntoskrnl!ExRaiseStatus` at `0x180066091`
- `ntoskrnl!ExRaiseStatus` at `0x1800660ca`
- `ntoskrnl!ExRaiseStatus` at `0x1800660e5`
- `ntoskrnl!ExRaiseStatus` at `0x1800660f6`
- `ntoskrnl!ExRaiseStatus` at `0x18006610b`
- `ntoskrnl!ExRaiseStatus` at `0x180066127`
- `ntoskrnl!ExRaiseStatus` at `0x180066155`
- `ntoskrnl!ExRaiseStatus` at `0x18006619b`
- `ntoskrnl!ExRaiseStatus` at `0x1800661c9`
- `ntoskrnl!ExRaiseStatus` at `0x1800661ed`
- `ntoskrnl!ExRaiseStatus` at `0x180066202`
- `ntoskrnl!ExRaiseStatus` at `0x180066245`
- `ntoskrnl!ExRaiseStatus` at `0x180066256`
- `ntoskrnl!ExRaiseStatus` at `0x18006626d`
- `ntoskrnl!ExRaiseStatus` at `0x180066293`
- `ntoskrnl!ExRaiseStatus` at `0x1800663d3`
- `ntoskrnl!ExRaiseStatus` at `0x180066467`
- `ntoskrnl!ExRaiseStatus` at `0x180065dd6`
- `ntoskrnl!ExRaiseStatus` at `0x180065eff`
- `ntoskrnl!ExRaiseStatus` at `0x180065f26`
- `ntoskrnl!ExRaiseStatus` at `0x180065f44`
- `ntoskrnl!ExRaiseStatus` at `0x180065f6c`
- `ntoskrnl!ExRaiseStatus` at `0x180065f7d`
- `ntoskrnl!ExRaiseStatus` at `0x180065f92`
- `ntoskrnl!ExRaiseStatus` at `0x180065fac`
- `ntoskrnl!ExRaiseStatus` at `0x180065fd0`
- `ntoskrnl!ExRaiseStatus` at `0x18006603f`
- `ntoskrnl!ExRaiseStatus` at `0x180066064`
- `ntoskrnl!ExRaiseStatus` at `0x180066091`
- `ntoskrnl!ExRaiseStatus` at `0x1800660ca`
- `ntoskrnl!ExRaiseStatus` at `0x1800660e5`
- `ntoskrnl!ExRaiseStatus` at `0x1800660f6`
- `ntoskrnl!ExRaiseStatus` at `0x18006610b`
- `ntoskrnl!ExRaiseStatus` at `0x180066127`
- `ntoskrnl!ExRaiseStatus` at `0x180066155`
- `ntoskrnl!ExRaiseStatus` at `0x18006619b`
- `ntoskrnl!ExRaiseStatus` at `0x1800661c9`
- `ntoskrnl!ExRaiseStatus` at `0x1800661ed`
- `ntoskrnl!ExRaiseStatus` at `0x180066202`
- `ntoskrnl!ExRaiseStatus` at `0x180066245`
- `ntoskrnl!ExRaiseStatus` at `0x180066256`
- `ntoskrnl!ExRaiseStatus` at `0x18006626d`
- `ntoskrnl!ExRaiseStatus` at `0x180066293`
- `ntoskrnl!ExRaiseStatus` at `0x1800663d3`
- `ntoskrnl!ExRaiseStatus` at `0x180066467`
- `ntoskrnl!ExFreePoolWithTag` at `0x180065ffb`
- `ntoskrnl!ExFreePoolWithTag` at `0x180065ffb`

## pseudocode

```c
NTSTATUS __stdcall KsProbeStreamIrp(PIRP Irp, ULONG ProbeFlags, ULONG HeaderSize)
{
  __int16 v4; // r13
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  int v7; // r14d
  struct _IRP *v8; // rdi
  unsigned int i; // esi
  unsigned int v10; // ecx
  SIZE_T Length; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  PVOID UserBuffer; // rdx
  struct _IRP *MasterIrp; // rcx
  struct _IRP *v15; // rcx
  __int64 v16; // rdx
  unsigned int Flink_high; // eax
  ULONG v19; // eax
  ULONG Flink; // edx
  NTSTATUS Status; // ecx
  ULONG v22; // edx
  struct _LIST_ENTRY *Blink; // r10
  PMDL MdlAddress; // rax
  PVOID v25; // rcx
  ULONG v26; // edx
  __int64 v27; // rax
  PMDL v28; // rdi
  __int64 v29; // rcx
  __int64 v30; // r8
  PKSPIN PinFromIrp; // r15
  PMDL j; // rax
  unsigned int v33; // esi
  __int64 Id; // r9
  PMDL k; // rdi
  PVOID v36; // rax
  PVOID MappedSystemVa; // rax
  struct _IRP *v38; // [rsp+50h] [rbp-38h]
  LOCK_OPERATION Operation; // [rsp+A8h] [rbp+20h]

  v4 = ProbeFlags;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v7 = 0;
  if ( !Irp->AssociatedIrp.MasterIrp )
  {
    if ( Irp->RequestorMode )
    {
      Length = CurrentStackLocation->Parameters.Read.Length;
      if ( !(_DWORD)Length
        || HeaderSize && (unsigned int)Length % HeaderSize && ((ProbeFlags & 0x80u) == 0 || (_DWORD)Length != 56) )
      {
        return -1073741306;
      }
      Irp->AssociatedIrp.MasterIrp = (struct _IRP *)ExAllocatePool2(
                                                      99,
                                                      CurrentStackLocation->Parameters.Read.Length,
                                                      1752388427);
      Irp->Flags |= 0x30u;
      if ( (v4 & 1) != 0 )
      {
        if ( (v4 & 0x200) != 0 )
        {
          ProbeForWrite(Irp->UserBuffer, Length, 1u);
        }
        else if ( !(unsigned int)Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline() )
        {
          ProbeForRead(Irp->UserBuffer, Length, 1u);
        }
      }
      else
      {
        ProbeForWrite(Irp->UserBuffer, Length, 1u);
        Irp->Flags |= 0x40u;
      }
      IsEnabledDeviceUsageNoInline = Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline();
      UserBuffer = Irp->UserBuffer;
      MasterIrp = Irp->AssociatedIrp.MasterIrp;
      if ( IsEnabledDeviceUsageNoInline )
        RtlCopyFromUser(MasterIrp, UserBuffer, Length);
      else
        memmove(MasterIrp, UserBuffer, Length);
      if ( (v4 & 0x10) == 0 )
      {
        v15 = Irp->AssociatedIrp.MasterIrp;
        while ( (_DWORD)Length )
        {
          v16 = *(unsigned int *)&v15->Type;
          if ( HeaderSize )
          {
            if ( (_DWORD)v16 != HeaderSize && (v15->IoStatus.Status & 8) == 0 || (unsigned int)v16 < 0x38 )
              ExRaiseStatus(-1073741306);
          }
          else if ( (unsigned int)v16 < 0x38 || (v16 & 7) != 0 )
          {
            ExRaiseStatus(-1073741306);
          }
          if ( (unsigned int)Length < (unsigned int)v16 )
            ExRaiseStatus(-1073741306);
          Flink_high = HIDWORD(v15->ThreadListEntry.Flink);
          if ( (v4 & 1) != 0 )
          {
            if ( Flink_high > LODWORD(v15->ThreadListEntry.Flink) )
              ExRaiseStatus(-1073741306);
            if ( (v15->IoStatus.Status & 8) != 0 )
            {
              if ( (_DWORD)Length != 56 || v15 != Irp->AssociatedIrp.MasterIrp )
                ExRaiseStatus(-1073741306);
              if ( (v4 & 0x80u) == 0 )
                ExRaiseStatus(-1073741811);
              break;
            }
          }
          else
          {
            if ( Flink_high )
              ExRaiseStatus(-1073741306);
            if ( (v15->IoStatus.Status & 0xFFFBF3FF) != 0 )
              ExRaiseStatus(-1073741811);
          }
          v15 = (struct _IRP *)((char *)v15 + v16);
          LODWORD(Length) = Length - v16;
        }
      }
      v7 = 0;
    }
    else
    {
      Irp->AssociatedIrp.MasterIrp = (struct _IRP *)Irp->UserBuffer;
    }
  }
  if ( (v4 & 0x10) != 0 )
  {
    if ( !Irp->MdlAddress )
    {
      v8 = Irp->AssociatedIrp.MasterIrp;
      for ( i = CurrentStackLocation->Parameters.Read.Length; i; i -= v27 )
      {
        v10 = *(_DWORD *)&v8->Type;
        if ( HeaderSize )
        {
          if ( v10 != HeaderSize && (v8->IoStatus.Status & 8) == 0 || v10 < 0x38 )
            ExRaiseStatus(-1073741306);
        }
        else if ( v10 < 0x38 || (v10 & 7) != 0 )
        {
          ExRaiseStatus(-1073741306);
        }
        if ( i < v10 )
          ExRaiseStatus(-1073741306);
        v19 = HIDWORD(v8->ThreadListEntry.Flink);
        if ( (v4 & 1) != 0 )
        {
          Flink = (ULONG)v8->ThreadListEntry.Flink;
          if ( v19 > Flink )
            ExRaiseStatus(-1073741306);
          Status = v8->IoStatus.Status;
          if ( (Status & 8) != 0 )
          {
            if ( i != 56 || v8 != Irp->AssociatedIrp.MasterIrp )
              ExRaiseStatus(-1073741306);
            if ( (v4 & 0x80u) == 0 )
              ExRaiseStatus(-1073741811);
            if ( Flink )
            {
              if ( !IoAllocateMdl(v8->ThreadListEntry.Blink, Flink, 0, 1u, Irp) )
                ExRaiseStatus(-1073741670);
              if ( (v8->IoStatus.Status & 0x1000) != 0 )
                ExRaiseStatus(-1073741306);
            }
            break;
          }
        }
        else
        {
          if ( v19 )
            ExRaiseStatus(-1073741306);
          Status = v8->IoStatus.Status;
          if ( (Status & 0xFFFA23FF) != 0 )
            ExRaiseStatus(-1073741811);
        }
        v22 = (ULONG)v8->ThreadListEntry.Flink;
        if ( v22 )
        {
          Blink = v8->ThreadListEntry.Blink;
          if ( (v8->IoStatus.Status & 0x18000) != 0 && !Blink )
            ExRaiseStatus(-1073741811);
          MdlAddress = Irp->MdlAddress;
          if ( (Status & 0x18000) == 0x18000 )
          {
            if ( !IoAllocateMdl(0, 0x1000u, MdlAddress != 0, 1u, Irp) )
              ExRaiseStatus(-1073741670);
          }
          else if ( !IoAllocateMdl(Blink, v22, MdlAddress != 0, 1u, Irp) )
          {
            ExRaiseStatus(-1073741670);
          }
          if ( (v8->IoStatus.Status & 0x1000) != 0 )
          {
            if ( i < 0xA0 )
              ExRaiseStatus(-1073741306);
            if ( *(_DWORD *)&v8->Type < 0xA0u )
              ExRaiseStatus(-1073741306);
            v25 = v8->Tail.Overlay.DriverContext[2];
            if ( !v25 || (v26 = *((_DWORD *)&v8->Tail.CompletionKey + 2)) == 0 )
              ExRaiseStatus(-1073741811);
            if ( !IoAllocateMdl(v25, v26, 1u, 1u, Irp) )
              ExRaiseStatus(-1073741670);
          }
        }
        else if ( (v8->IoStatus.Status & 0x1000) != 0 )
        {
          ExRaiseStatus(-1073741811);
        }
        v27 = *(unsigned int *)&v8->Type;
        v8 = (struct _IRP *)((char *)v8 + v27);
      }
    }
    if ( (v4 & 0x20) != 0 )
    {
      v28 = Irp->MdlAddress;
      if ( v28 )
      {
        if ( (v28->MdlFlags & 6) != 0 )
        {
          if ( (v4 & 0x40) != 0 )
          {
            while ( v28 )
            {
              v28->MdlFlags |= 0x2000u;
              if ( (v28->MdlFlags & 5) != 0 )
                MappedSystemVa = v28->MappedSystemVa;
              else
                MappedSystemVa = MmMapLockedPagesSpecifyCache(v28, 0, MmCached, 0, 0, 0x40000010u);
              if ( !MappedSystemVa )
                ExRaiseStatus(-1073741670);
              v28 = v28->Next;
            }
          }
        }
        else
        {
          v38 = Irp->AssociatedIrp.MasterIrp;
          PinFromIrp = KsGetPinFromIrp(Irp);
          if ( (v4 & 1) == 0 || (Operation = IoReadAccess, (v4 & 0x200) != 0) )
            Operation = IoWriteAccess;
          for ( j = Irp->MdlAddress; j; j = j->Next )
            v7 += j->ByteCount;
          v33 = -1;
          if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 2) != 0 )
          {
            if ( PinFromIrp )
              Id = PinFromIrp->Id;
            else
              Id = 0xFFFFFFFFLL;
            McTemplateK0dq_EtwWriteTransfer(v29, KS_IoProbeandLock_Start, v30, Id, v7);
          }
          for ( k = Irp->MdlAddress; k; k = k->Next )
          {
            if ( k->StartVa || (v38->IoStatus.Status & 0x10000) == 0 )
            {
              MmProbeAndLockPages(k, Irp->RequestorMode, Operation);
              if ( (v4 & 0x40) != 0 )
              {
                k->MdlFlags |= 0x2000u;
                if ( (k->MdlFlags & 5) != 0 )
                  v36 = k->MappedSystemVa;
                else
                  v36 = MmMapLockedPagesSpecifyCache(k, 0, MmCached, 0, 0, 0x40000010u);
                if ( !v36 )
                  ExRaiseStatus(-1073741670);
              }
            }
          }
          if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 2) != 0 )
          {
            if ( PinFromIrp )
              v33 = PinFromIrp->Id;
            McTemplateK0dq_EtwWriteTransfer(v29, KS_IoProbeandLock_End, v30, v33, v7);
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180065d20  mov     [rsp+arg_8], rbx
0x180065d25  mov     [rsp+arg_10], rsi
0x180065d2a  mov     [rsp+arg_0], rcx
0x180065d2f  push    rdi
0x180065d30  push    r12
0x180065d32  push    r13
0x180065d34  push    r14
0x180065d36  push    r15
0x180065d38  sub     rsp, 60h
0x180065d3c  mov     r12d, r8d
0x180065d3f  mov     r13d, edx
0x180065d42  mov     rbx, rcx
0x180065d45  mov     r15, [rcx+0B8h]
0x180065d4c  xor     r14d, r14d
0x180065d4f  cmp     [rcx+18h], r14
0x180065d53  jnz     short loc_180065D67
0x180065d55  cmp     [rcx+40h], r14b
0x180065d59  jnz     loc_180065DE3
0x180065d5f  mov     rax, [rcx+70h]
0x180065d63  mov     [rcx+18h], rax
0x180065d67  test    r13b, 10h
0x180065d6b  jz      loc_1800664C5
0x180065d71  mov     [rsp+88h+var_58], r14d
0x180065d76  cmp     [rbx+8], r14
0x180065d7a  jnz     loc_18006629F
0x180065d80  mov     [rsp+88h+var_54], r14d
0x180065d85  mov     [rsp+88h+var_40], r14
0x180065d8a  mov     [rsp+88h+var_58], 1
0x180065d92  mov     rdi, [rbx+18h]
0x180065d96  mov     [rsp+88h+var_40], rdi
0x180065d9b  mov     esi, [r15+8]
0x180065d9f  mov     [rsp+88h+var_54], esi
0x180065da3  mov     r15d, 1000h
0x180065da9  test    esi, esi
0x180065dab  jz      loc_1800662A4
0x180065db1  mov     ecx, [rdi]
0x180065db3  test    r12d, r12d
0x180065db6  jz      loc_180066024
0x180065dbc  cmp     ecx, r12d
0x180065dbf  jz      short loc_180065DC8
0x180065dc1  mov     eax, [rdi+30h]
0x180065dc4  test    al, 8
0x180065dc6  jz      short loc_180065DD1
0x180065dc8  cmp     ecx, 38h ; '8'
0x180065dcb  jnb     loc_180066036
0x180065dd1  mov     ecx, 0C0000206h; Status
0x180065dd6  call    cs:__imp_ExRaiseStatus
0x180065de3  mov     edi, [r15+8]
0x180065de7  test    edi, edi
0x180065de9  jz      loc_18006601A
0x180065def  test    r12d, r12d
0x180065df2  jz      short loc_180065E11
0x180065df4  xor     edx, edx
0x180065df6  mov     eax, edi
0x180065df8  div     r12d
0x180065dfb  test    edx, edx
0x180065dfd  jz      short loc_180065E11
0x180065dff  test    r13b, r13b
0x180065e02  jns     loc_18006601A
0x180065e08  cmp     edi, 38h ; '8'
0x180065e0b  jnz     loc_18006601A
0x180065e11  mov     r8d, 6873534Bh
0x180065e17  mov     rdx, rdi
0x180065e1a  mov     ecx, 63h ; 'c'
0x180065e1f  call    cs:__imp_ExAllocatePool2
0x180065e26  nop     dword ptr [rax+rax+00h]
0x180065e2b  mov     [rbx+18h], rax
0x180065e2f  or      dword ptr [rbx+10h], 30h
0x180065e33  mov     r14d, r13d
0x180065e36  and     r14d, 1
0x180065e3a  jz      short loc_180065E80
0x180065e3c  bt      r13d, 9
0x180065e41  jnb     short loc_180065E5E
0x180065e43  mov     r8d, 1; Alignment
0x180065e49  mov     rdx, rdi; Length
0x180065e4c  mov     rcx, [rbx+70h]; Address
0x180065e50  call    cs:__imp_ProbeForWrite
0x180065e57  nop     dword ptr [rax+rax+00h]
0x180065e5c  jmp     short loc_180065E9D
0x180065e5e  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x180065e63  test    eax, eax
0x180065e65  jnz     short loc_180065E9D
0x180065e67  lea     r8d, [rax+1]; Alignment
0x180065e6b  mov     rdx, rdi; Length
0x180065e6e  mov     rcx, [rbx+70h]; Address
0x180065e72  call    cs:__imp_ProbeForRead
0x180065e79  nop     dword ptr [rax+rax+00h]
0x180065e7e  jmp     short loc_180065E9D
0x180065e80  mov     r8d, 1; Alignment
0x180065e86  mov     rdx, rdi; Length
0x180065e89  mov     rcx, [rbx+70h]; Address
0x180065e8d  call    cs:__imp_ProbeForWrite
0x180065e94  nop     dword ptr [rax+rax+00h]
0x180065e99  or      dword ptr [rbx+10h], 40h
0x180065e9d  call    Feature_Servicing_KS_UMA__private_IsEnabledDeviceUsageNoInline
0x180065ea2  mov     rdx, [rbx+70h]; Src
0x180065ea6  mov     rcx, [rbx+18h]; void *
0x180065eaa  mov     r8, rdi; Size
0x180065ead  test    eax, eax
0x180065eaf  jz      short loc_180065EB8
0x180065eb1  call    RtlCopyFromUser
0x180065eb6  jmp     short loc_180065EBD
0x180065eb8  call    memmove
0x180065ebd  nop
0x180065ebe  test    r13b, 10h
0x180065ec2  jnz     loc_180065FDC
0x180065ec8  mov     [rsp+88h+var_48], 0
0x180065ed1  mov     rcx, [rbx+18h]
0x180065ed5  mov     [rsp+88h+var_48], rcx
0x180065eda  test    edi, edi
0x180065edc  jz      loc_180065FDC
0x180065ee2  mov     edx, [rcx]
0x180065ee4  test    r12d, r12d
0x180065ee7  jz      short loc_180065F0B
0x180065ee9  cmp     edx, r12d
0x180065eec  jz      short loc_180065EF5
0x180065eee  mov     eax, [rcx+30h]
0x180065ef1  test    al, 8
0x180065ef3  jz      short loc_180065EFA
0x180065ef5  cmp     edx, 38h ; '8'
0x180065ef8  jnb     short loc_180065F1D
0x180065efa  mov     ecx, 0C0000206h; Status
0x180065eff  call    cs:__imp_ExRaiseStatus
0x180065f0b  cmp     edx, 38h ; '8'
0x180065f0e  jb      loc_180065FCB
0x180065f14  test    dl, 7
0x180065f17  jnz     loc_180065FCB
0x180065f1d  cmp     edi, edx
0x180065f1f  jnb     short loc_180065F32
0x180065f21  mov     ecx, 0C0000206h; Status
0x180065f26  call    cs:__imp_ExRaiseStatus
0x180065f32  mov     eax, [rcx+24h]
0x180065f35  test    r14d, r14d
0x180065f38  jz      short loc_180065F89
0x180065f3a  cmp     eax, [rcx+20h]
0x180065f3d  jbe     short loc_180065F50
0x180065f3f  mov     ecx, 0C0000206h; Status
0x180065f44  call    cs:__imp_ExRaiseStatus
0x180065f50  mov     eax, [rcx+30h]
0x180065f53  test    al, 8
0x180065f55  jz      short loc_180065FB8
0x180065f57  cmp     edi, 38h ; '8'
0x180065f5a  jnz     short loc_180065F78
0x180065f5c  cmp     rcx, [rbx+18h]
0x180065f60  jnz     short loc_180065F78
0x180065f62  test    r13b, r13b
0x180065f65  js      short loc_180065FDC
0x180065f67  mov     ecx, 0C000000Dh; Status
0x180065f6c  call    cs:__imp_ExRaiseStatus
0x180065f78  mov     ecx, 0C0000206h; Status
0x180065f7d  call    cs:__imp_ExRaiseStatus
0x180065f89  test    eax, eax
0x180065f8b  jz      short loc_180065F9E
0x180065f8d  mov     ecx, 0C0000206h; Status
0x180065f92  call    cs:__imp_ExRaiseStatus
0x180065f9e  test    dword ptr [rcx+30h], 0FFFBF3FFh
0x180065fa5  jz      short loc_180065FB8
0x180065fa7  mov     ecx, 0C000000Dh; Status
0x180065fac  call    cs:__imp_ExRaiseStatus
0x180065fb8  add     rcx, rdx
0x180065fbb  mov     [rsp+88h+var_48], rcx
0x180065fc0  sub     edi, edx
0x180065fc2  mov     [rsp+88h+var_4C], edi
0x180065fc6  jmp     loc_180065EDA
0x180065fcb  mov     ecx, 0C0000206h; Status
0x180065fd0  call    cs:__imp_ExRaiseStatus
0x180065fdc  xor     r14d, r14d
0x180065fdf  jmp     loc_180065D67
0x180065fe4  mov     edi, eax
0x180065fe6  mov     rbx, [rsp+88h+arg_0]
0x180065fee  cmp     qword ptr [rbx+18h], 0
0x180065ff3  jz      short loc_180066013
0x180065ff5  xor     edx, edx; Tag
0x180065ff7  mov     rcx, [rbx+18h]; P
0x180065ffb  call    cs:__imp_ExFreePoolWithTag
0x180066002  nop     dword ptr [rax+rax+00h]
0x180066007  mov     qword ptr [rbx+18h], 0
0x18006600f  and     dword ptr [rbx+10h], 0FFFFFFDFh
0x180066013  mov     eax, edi
0x180066015  jmp     loc_1800664C7
0x18006601a  mov     eax, 0C0000206h
0x18006601f  jmp     loc_1800664C7
0x180066024  cmp     ecx, 38h ; '8'
0x180066027  jb      loc_18006628E
0x18006602d  test    cl, 7
0x180066030  jnz     loc_18006628E
0x180066036  cmp     esi, ecx
0x180066038  jnb     short loc_18006604B
0x18006603a  mov     ecx, 0C0000206h; Status
0x18006603f  call    cs:__imp_ExRaiseStatus
0x18006604b  mov     eax, [rdi+24h]
0x18006604e  test    r13b, 1
0x180066052  jz      loc_180066102
0x180066058  mov     edx, [rdi+20h]; Length
0x18006605b  cmp     eax, edx
0x18006605d  jbe     short loc_180066070
0x18006605f  mov     ecx, 0C0000206h; Status
0x180066064  call    cs:__imp_ExRaiseStatus
0x180066070  mov     ecx, [rdi+30h]
0x180066073  test    cl, 8
0x180066076  jz      loc_180066133
0x18006607c  cmp     esi, 38h ; '8'
0x18006607f  jnz     short loc_1800660F1
0x180066081  cmp     rdi, [rbx+18h]
0x180066085  jnz     short loc_1800660F1
0x180066087  test    r13b, r13b
0x18006608a  js      short loc_18006609D
0x18006608c  mov     ecx, 0C000000Dh; Status
0x180066091  call    cs:__imp_ExRaiseStatus
0x18006609d  test    edx, edx
0x18006609f  jz      loc_1800662A4
0x1800660a5  mov     [rsp+88h+Irp], rbx; Irp
0x1800660aa  mov     r9b, 1; ChargeQuota
0x1800660ad  xor     r8d, r8d; SecondaryBuffer
0x1800660b0  mov     rcx, [rdi+28h]; VirtualAddress
0x1800660b4  call    cs:__imp_IoAllocateMdl
0x1800660bb  nop     dword ptr [rax+rax+00h]
0x1800660c0  test    rax, rax
0x1800660c3  jnz     short loc_1800660D6
0x1800660c5  mov     ecx, 0C000009Ah; Status
0x1800660ca  call    cs:__imp_ExRaiseStatus
0x1800660d6  test    [rdi+30h], r15d
0x1800660da  jz      loc_1800662A4
0x1800660e0  mov     ecx, 0C0000206h; Status
0x1800660e5  call    cs:__imp_ExRaiseStatus
0x1800660f1  mov     ecx, 0C0000206h; Status
0x1800660f6  call    cs:__imp_ExRaiseStatus
0x180066102  test    eax, eax
0x180066104  jz      short loc_180066117
0x180066106  mov     ecx, 0C0000206h; Status
0x18006610b  call    cs:__imp_ExRaiseStatus
0x180066117  mov     ecx, [rdi+30h]
0x18006611a  test    ecx, 0FFFA23FFh
0x180066120  jz      short loc_180066133
0x180066122  mov     ecx, 0C000000Dh; Status
0x180066127  call    cs:__imp_ExRaiseStatus
0x180066133  mov     edx, [rdi+20h]; Length
0x180066136  test    edx, edx
0x180066138  jz      loc_180066262
0x18006613e  mov     r10, [rdi+28h]
0x180066142  test    dword ptr [rdi+30h], 18000h
0x180066149  jz      short loc_180066161
0x18006614b  test    r10, r10
0x18006614e  jnz     short loc_180066161
0x180066150  mov     ecx, 0C000000Dh; Status
0x180066155  call    cs:__imp_ExRaiseStatus
0x180066161  mov     rax, [rbx+8]
0x180066165  and     ecx, 18000h
0x18006616b  mov     [rsp+88h+Irp], rbx; Irp
0x180066170  mov     r9b, 1; ChargeQuota
0x180066173  cmp     ecx, 18000h
0x180066179  jz      short loc_1800661A7
0x18006617b  test    rax, rax
0x18006617e  setnz   r8b; SecondaryBuffer
0x180066182  mov     rcx, r10; VirtualAddress
0x180066185  call    cs:__imp_IoAllocateMdl
0x18006618c  nop     dword ptr [rax+rax+00h]
0x180066191  test    rax, rax
0x180066194  jnz     short loc_1800661D5
0x180066196  mov     ecx, 0C000009Ah; Status
0x18006619b  call    cs:__imp_ExRaiseStatus
0x1800661a7  test    rax, rax
0x1800661aa  setnz   r8b; SecondaryBuffer
0x1800661ae  mov     edx, r15d; Length
0x1800661b1  xor     ecx, ecx; VirtualAddress
0x1800661b3  call    cs:__imp_IoAllocateMdl
0x1800661ba  nop     dword ptr [rax+rax+00h]
0x1800661bf  test    rax, rax
0x1800661c2  jnz     short loc_1800661D5
0x1800661c4  mov     ecx, 0C000009Ah; Status
0x1800661c9  call    cs:__imp_ExRaiseStatus
0x1800661d5  test    [rdi+30h], r15d
0x1800661d9  jz      loc_180066279
0x1800661df  mov     eax, 0A0h
0x1800661e4  cmp     esi, eax
0x1800661e6  jnb     short loc_1800661F9
0x1800661e8  mov     ecx, 0C0000206h; Status
0x1800661ed  call    cs:__imp_ExRaiseStatus
0x1800661f9  cmp     [rdi], eax
0x1800661fb  jnb     short loc_18006620E
0x1800661fd  mov     ecx, 0C0000206h; Status
0x180066202  call    cs:__imp_ExRaiseStatus
0x18006620e  mov     rcx, [rdi+88h]; VirtualAddress
0x180066215  test    rcx, rcx
0x180066218  jz      short loc_180066251
0x18006621a  mov     edx, [rdi+80h]; Length
0x180066220  test    edx, edx
0x180066222  jz      short loc_180066251
0x180066224  mov     [rsp+88h+Irp], rbx; Irp
0x180066229  mov     r9b, 1; ChargeQuota
0x18006622c  mov     r8b, r9b; SecondaryBuffer
0x18006622f  call    cs:__imp_IoAllocateMdl
0x180066236  nop     dword ptr [rax+rax+00h]
0x18006623b  test    rax, rax
0x18006623e  jnz     short loc_180066279
0x180066240  mov     ecx, 0C000009Ah; Status
0x180066245  call    cs:__imp_ExRaiseStatus
0x180066251  mov     ecx, 0C000000Dh; Status
0x180066256  call    cs:__imp_ExRaiseStatus
0x180066262  test    [rdi+30h], r15d
  ... truncated ...
```
