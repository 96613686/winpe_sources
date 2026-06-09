# KsProbeStreamIrp

- ea: `0x180066360`
- end: `0x180066b06`
- name: `KsProbeStreamIrp`
- size: `1958`
- prototype: `NTSTATUS __stdcall(PIRP Irp, ULONG ProbeFlags, ULONG HeaderSize)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009c40`
- `0x180009c9c`
- `0x18000f170`
- `0x18000f840`
- `0x1800177f0`

## callees

- `0x180005df0`
- `0x18000ad48`
- `0x180010794`
- `0x180066360`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x18006649c`
- `ntoskrnl!ProbeForWrite` at `0x1800664b7`
- `ntoskrnl!ProbeForWrite` at `0x18006649c`
- `ntoskrnl!ProbeForWrite` at `0x1800664b7`
- `ntoskrnl!ExAllocatePool2` at `0x18006646b`
- `ntoskrnl!ExAllocatePool2` at `0x18006646b`
- `ntoskrnl!MmUnlockPages` at `0x180066aba`
- `ntoskrnl!MmUnlockPages` at `0x180066aba`
- `ntoskrnl!MmProbeAndLockPages` at `0x180066996`
- `ntoskrnl!MmProbeAndLockPages` at `0x180066996`
- `ntoskrnl!IoAllocateMdl` at `0x1800666cb`
- `ntoskrnl!IoAllocateMdl` at `0x18006679b`
- `ntoskrnl!IoAllocateMdl` at `0x1800667c9`
- `ntoskrnl!IoAllocateMdl` at `0x180066845`
- `ntoskrnl!IoAllocateMdl` at `0x1800666cb`
- `ntoskrnl!IoAllocateMdl` at `0x18006679b`
- `ntoskrnl!IoAllocateMdl` at `0x1800667c9`
- `ntoskrnl!IoAllocateMdl` at `0x180066845`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800669d7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180066a75`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1800669d7`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180066a75`
- `ntoskrnl!ExRaiseStatus` at `0x180066422`
- `ntoskrnl!ExRaiseStatus` at `0x180066519`
- `ntoskrnl!ExRaiseStatus` at `0x180066540`
- `ntoskrnl!ExRaiseStatus` at `0x18006655e`
- `ntoskrnl!ExRaiseStatus` at `0x180066586`
- `ntoskrnl!ExRaiseStatus` at `0x180066597`
- `ntoskrnl!ExRaiseStatus` at `0x1800665ac`
- `ntoskrnl!ExRaiseStatus` at `0x1800665c6`
- `ntoskrnl!ExRaiseStatus` at `0x1800665ea`
- `ntoskrnl!ExRaiseStatus` at `0x180066656`
- `ntoskrnl!ExRaiseStatus` at `0x18006667b`
- `ntoskrnl!ExRaiseStatus` at `0x1800666a8`
- `ntoskrnl!ExRaiseStatus` at `0x1800666e1`
- `ntoskrnl!ExRaiseStatus` at `0x1800666fc`
- `ntoskrnl!ExRaiseStatus` at `0x18006670d`
- `ntoskrnl!ExRaiseStatus` at `0x180066722`
- `ntoskrnl!ExRaiseStatus` at `0x18006673e`
- `ntoskrnl!ExRaiseStatus` at `0x18006676c`
- `ntoskrnl!ExRaiseStatus` at `0x1800667b1`
- `ntoskrnl!ExRaiseStatus` at `0x1800667df`
- `ntoskrnl!ExRaiseStatus` at `0x180066803`
- `ntoskrnl!ExRaiseStatus` at `0x180066818`
- `ntoskrnl!ExRaiseStatus` at `0x18006685b`
- `ntoskrnl!ExRaiseStatus` at `0x18006686c`
- `ntoskrnl!ExRaiseStatus` at `0x180066883`
- `ntoskrnl!ExRaiseStatus` at `0x1800668a9`
- `ntoskrnl!ExRaiseStatus` at `0x1800669ed`
- `ntoskrnl!ExRaiseStatus` at `0x180066a8b`
- `ntoskrnl!ExRaiseStatus` at `0x180066422`
- `ntoskrnl!ExRaiseStatus` at `0x180066519`
- `ntoskrnl!ExRaiseStatus` at `0x180066540`
- `ntoskrnl!ExRaiseStatus` at `0x18006655e`
- `ntoskrnl!ExRaiseStatus` at `0x180066586`
- `ntoskrnl!ExRaiseStatus` at `0x180066597`
- `ntoskrnl!ExRaiseStatus` at `0x1800665ac`
- `ntoskrnl!ExRaiseStatus` at `0x1800665c6`
- `ntoskrnl!ExRaiseStatus` at `0x1800665ea`
- `ntoskrnl!ExRaiseStatus` at `0x180066656`
- `ntoskrnl!ExRaiseStatus` at `0x18006667b`
- `ntoskrnl!ExRaiseStatus` at `0x1800666a8`
- `ntoskrnl!ExRaiseStatus` at `0x1800666e1`
- `ntoskrnl!ExRaiseStatus` at `0x1800666fc`
- `ntoskrnl!ExRaiseStatus` at `0x18006670d`
- `ntoskrnl!ExRaiseStatus` at `0x180066722`
- `ntoskrnl!ExRaiseStatus` at `0x18006673e`
- `ntoskrnl!ExRaiseStatus` at `0x18006676c`
- `ntoskrnl!ExRaiseStatus` at `0x1800667b1`
- `ntoskrnl!ExRaiseStatus` at `0x1800667df`
- `ntoskrnl!ExRaiseStatus` at `0x180066803`
- `ntoskrnl!ExRaiseStatus` at `0x180066818`
- `ntoskrnl!ExRaiseStatus` at `0x18006685b`
- `ntoskrnl!ExRaiseStatus` at `0x18006686c`
- `ntoskrnl!ExRaiseStatus` at `0x180066883`
- `ntoskrnl!ExRaiseStatus` at `0x1800668a9`
- `ntoskrnl!ExRaiseStatus` at `0x1800669ed`
- `ntoskrnl!ExRaiseStatus` at `0x180066a8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066612`
- `ntoskrnl!ExFreePoolWithTag` at `0x180066612`
- `ntoskrnl!IoFreeMdl` at `0x180066ad0`
- `ntoskrnl!IoFreeMdl` at `0x180066ad0`

## pseudocode

```c
NTSTATUS __stdcall KsProbeStreamIrp(PIRP Irp, ULONG ProbeFlags, ULONG HeaderSize)
{
  __int16 v4; // r13
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  PMDL *p_MdlAddress; // r14
  struct _IRP *v8; // rbx
  unsigned int i; // esi
  unsigned int v10; // ecx
  SIZE_T Length; // rbx
  struct _IRP *MasterIrp; // rcx
  __int64 v13; // rdx
  unsigned int Flink_high; // eax
  ULONG v16; // eax
  ULONG Flink; // edx
  NTSTATUS Status; // ecx
  ULONG v19; // edx
  struct _LIST_ENTRY *Blink; // r10
  PMDL v21; // rax
  PVOID v22; // rcx
  ULONG v23; // edx
  __int64 v24; // rax
  PMDL *v25; // rsi
  struct _MDL *v26; // rbx
  int v27; // r14d
  __int64 v28; // r8
  PKSPIN PinFromIrp; // r15
  int v30; // ecx
  _BOOL8 v31; // rdx
  PMDL j; // rcx
  unsigned int v33; // esi
  __int64 Id; // r9
  PMDL MdlAddress; // rbx
  PVOID v36; // rax
  PVOID MappedSystemVa; // rax
  struct _IRP *v38; // [rsp+50h] [rbp-38h]
  BOOL v39; // [rsp+A8h] [rbp+20h]

  v4 = ProbeFlags;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
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
          ProbeForWrite(Irp->UserBuffer, Length, 1u);
      }
      else
      {
        ProbeForWrite(Irp->UserBuffer, Length, 1u);
        Irp->Flags |= 0x40u;
      }
      RtlCopyFromUser(Irp->AssociatedIrp.MasterIrp, Irp->UserBuffer, Length);
      if ( (v4 & 0x10) == 0 )
      {
        MasterIrp = Irp->AssociatedIrp.MasterIrp;
        while ( (_DWORD)Length )
        {
          v13 = *(unsigned int *)&MasterIrp->Type;
          if ( HeaderSize )
          {
            if ( (_DWORD)v13 != HeaderSize && (MasterIrp->IoStatus.Status & 8) == 0 || (unsigned int)v13 < 0x38 )
              ExRaiseStatus(-1073741306);
          }
          else if ( (unsigned int)v13 < 0x38 || (v13 & 7) != 0 )
          {
            ExRaiseStatus(-1073741306);
          }
          if ( (unsigned int)Length < (unsigned int)v13 )
            ExRaiseStatus(-1073741306);
          Flink_high = HIDWORD(MasterIrp->ThreadListEntry.Flink);
          if ( (v4 & 1) != 0 )
          {
            if ( Flink_high > LODWORD(MasterIrp->ThreadListEntry.Flink) )
              ExRaiseStatus(-1073741306);
            if ( (MasterIrp->IoStatus.Status & 8) != 0 )
            {
              if ( (_DWORD)Length != 56 || MasterIrp != Irp->AssociatedIrp.MasterIrp )
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
            if ( (MasterIrp->IoStatus.Status & 0xFFFBF3FF) != 0 )
              ExRaiseStatus(-1073741811);
          }
          MasterIrp = (struct _IRP *)((char *)MasterIrp + v13);
          LODWORD(Length) = Length - v13;
        }
      }
    }
    else
    {
      Irp->AssociatedIrp.MasterIrp = (struct _IRP *)Irp->UserBuffer;
    }
  }
  if ( (v4 & 0x10) != 0 )
  {
    p_MdlAddress = &Irp->MdlAddress;
    if ( Irp->MdlAddress )
    {
      v25 = &Irp->MdlAddress;
    }
    else
    {
      v8 = Irp->AssociatedIrp.MasterIrp;
      for ( i = CurrentStackLocation->Parameters.Read.Length; i; i -= v24 )
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
        v16 = HIDWORD(v8->ThreadListEntry.Flink);
        if ( (v4 & 1) != 0 )
        {
          Flink = (ULONG)v8->ThreadListEntry.Flink;
          if ( v16 > Flink )
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
          if ( v16 )
            ExRaiseStatus(-1073741306);
          Status = v8->IoStatus.Status;
          if ( (Status & 0xFFFA23FF) != 0 )
            ExRaiseStatus(-1073741811);
        }
        v19 = (ULONG)v8->ThreadListEntry.Flink;
        if ( v19 )
        {
          Blink = v8->ThreadListEntry.Blink;
          if ( (v8->IoStatus.Status & 0x18000) != 0 && !Blink )
            ExRaiseStatus(-1073741811);
          v21 = *p_MdlAddress;
          if ( (Status & 0x18000) == 0x18000 )
          {
            if ( !IoAllocateMdl(0, 0x1000u, v21 != 0, 1u, Irp) )
              ExRaiseStatus(-1073741670);
          }
          else if ( !IoAllocateMdl(Blink, v19, v21 != 0, 1u, Irp) )
          {
            ExRaiseStatus(-1073741670);
          }
          if ( (v8->IoStatus.Status & 0x1000) != 0 )
          {
            if ( i < 0xA0 )
              ExRaiseStatus(-1073741306);
            if ( *(_DWORD *)&v8->Type < 0xA0u )
              ExRaiseStatus(-1073741306);
            v22 = v8->Tail.Overlay.DriverContext[2];
            if ( !v22 || (v23 = *((_DWORD *)&v8->Tail.CompletionKey + 2)) == 0 )
              ExRaiseStatus(-1073741811);
            if ( !IoAllocateMdl(v22, v23, 1u, 1u, Irp) )
              ExRaiseStatus(-1073741670);
          }
        }
        else if ( (v8->IoStatus.Status & 0x1000) != 0 )
        {
          ExRaiseStatus(-1073741811);
        }
        v24 = *(unsigned int *)&v8->Type;
        v8 = (struct _IRP *)((char *)v8 + v24);
      }
      v25 = &Irp->MdlAddress;
    }
    if ( (v4 & 0x20) != 0 )
    {
      v26 = *p_MdlAddress;
      if ( *p_MdlAddress )
      {
        if ( (v26->MdlFlags & 6) != 0 )
        {
          if ( (v4 & 0x40) != 0 )
          {
            while ( v26 )
            {
              v26->MdlFlags |= 0x2000u;
              if ( (v26->MdlFlags & 5) != 0 )
                MappedSystemVa = v26->MappedSystemVa;
              else
                MappedSystemVa = MmMapLockedPagesSpecifyCache(v26, 0, MmCached, 0, 0, 0x40000010u);
              if ( !MappedSystemVa )
                ExRaiseStatus(-1073741670);
              v26 = v26->Next;
            }
          }
        }
        else
        {
          v38 = Irp->AssociatedIrp.MasterIrp;
          v27 = 0;
          PinFromIrp = KsGetPinFromIrp(Irp);
          v30 = v4 & 0x201;
          v31 = v30 != 1;
          v39 = v30 != 1;
          for ( j = *v25; j; j = j->Next )
            v27 += j->ByteCount;
          v33 = -1;
          if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 2) != 0 )
          {
            if ( PinFromIrp )
              Id = PinFromIrp->Id;
            else
              Id = 0xFFFFFFFFLL;
            McTemplateK0dq_EtwWriteTransfer(0, KS_IoProbeandLock_Start, v28, Id, v27);
            LODWORD(v31) = v39;
          }
          MdlAddress = Irp->MdlAddress;
          while ( MdlAddress )
          {
            if ( MdlAddress->StartVa || (v38->IoStatus.Status & 0x10000) == 0 )
            {
              MmProbeAndLockPages(MdlAddress, Irp->RequestorMode, (LOCK_OPERATION)v31);
              if ( (v4 & 0x40) != 0 )
              {
                MdlAddress->MdlFlags |= 0x2000u;
                if ( (MdlAddress->MdlFlags & 5) != 0 )
                  v36 = MdlAddress->MappedSystemVa;
                else
                  v36 = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
                if ( !v36 )
                  ExRaiseStatus(-1073741670);
              }
            }
            MdlAddress = MdlAddress->Next;
            LODWORD(v31) = v39;
          }
          if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 2) != 0 )
          {
            if ( PinFromIrp )
              v33 = PinFromIrp->Id;
            McTemplateK0dq_EtwWriteTransfer(j, KS_IoProbeandLock_End, v28, v33, v27);
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
0x180066360  mov     [rsp+arg_8], rbx
0x180066365  mov     [rsp+arg_10], rsi
0x18006636a  mov     [rsp+arg_0], rcx
0x18006636f  push    rdi
0x180066370  push    r12
0x180066372  push    r13
0x180066374  push    r14
0x180066376  push    r15
0x180066378  sub     rsp, 60h
0x18006637c  mov     r12d, r8d
0x18006637f  mov     r13d, edx
0x180066382  mov     rdi, rcx
0x180066385  mov     r15, [rcx+0B8h]
0x18006638c  cmp     qword ptr [rcx+18h], 0
0x180066391  jnz     short loc_1800663A5
0x180066393  cmp     byte ptr [rcx+40h], 0
0x180066397  jnz     loc_18006642F
0x18006639d  mov     rax, [rcx+70h]
0x1800663a1  mov     [rcx+18h], rax
0x1800663a5  test    r13b, 10h
0x1800663a9  jz      loc_180066AE9
0x1800663af  mov     [rsp+88h+var_58], 0
0x1800663b7  lea     r14, [rdi+8]
0x1800663bb  cmp     qword ptr [r14], 0
0x1800663bf  jnz     loc_1800668BB
0x1800663c5  mov     [rsp+88h+var_54], 0
0x1800663cd  mov     [rsp+88h+var_40], 0
0x1800663d6  mov     [rsp+88h+var_58], 1
0x1800663de  mov     rbx, [rdi+18h]
0x1800663e2  mov     [rsp+88h+var_40], rbx
0x1800663e7  mov     esi, [r15+8]
0x1800663eb  mov     [rsp+88h+var_54], esi
0x1800663ef  mov     r15d, 1000h
0x1800663f5  test    esi, esi
0x1800663f7  jz      loc_1800668B5
0x1800663fd  mov     ecx, [rbx]
0x1800663ff  test    r12d, r12d
0x180066402  jz      loc_18006663B
0x180066408  cmp     ecx, r12d
0x18006640b  jz      short loc_180066414
0x18006640d  mov     eax, [rbx+30h]
0x180066410  test    al, 8
0x180066412  jz      short loc_18006641D
0x180066414  cmp     ecx, 38h ; '8'
0x180066417  jnb     loc_18006664D
0x18006641d  mov     ecx, 0C0000206h; Status
0x180066422  call    cs:__imp_ExRaiseStatus
0x18006642f  mov     ebx, [r15+8]
0x180066433  test    ebx, ebx
0x180066435  jz      loc_180066631
0x18006643b  test    r12d, r12d
0x18006643e  jz      short loc_18006645D
0x180066440  xor     edx, edx
0x180066442  mov     eax, ebx
0x180066444  div     r12d
0x180066447  test    edx, edx
0x180066449  jz      short loc_18006645D
0x18006644b  test    r13b, r13b
0x18006644e  jns     loc_180066631
0x180066454  cmp     ebx, 38h ; '8'
0x180066457  jnz     loc_180066631
0x18006645d  mov     r8d, 6873534Bh
0x180066463  mov     rdx, rbx
0x180066466  mov     ecx, 63h ; 'c'
0x18006646b  call    cs:__imp_ExAllocatePool2
0x180066472  nop     dword ptr [rax+rax+00h]
0x180066477  mov     [rdi+18h], rax
0x18006647b  or      dword ptr [rdi+10h], 30h
0x18006647f  mov     r14d, r13d
0x180066482  and     r14d, 1
0x180066486  jz      short loc_1800664AA
0x180066488  bt      r13d, 9
0x18006648d  jnb     short loc_1800664C7
0x18006648f  mov     r8d, 1; Alignment
0x180066495  mov     rdx, rbx; Length
0x180066498  mov     rcx, [rdi+70h]; Address
0x18006649c  call    cs:__imp_ProbeForWrite
0x1800664a3  nop     dword ptr [rax+rax+00h]
0x1800664a8  jmp     short loc_1800664C7
0x1800664aa  mov     r8d, 1; Alignment
0x1800664b0  mov     rdx, rbx; Length
0x1800664b3  mov     rcx, [rdi+70h]; Address
0x1800664b7  call    cs:__imp_ProbeForWrite
0x1800664be  nop     dword ptr [rax+rax+00h]
0x1800664c3  or      dword ptr [rdi+10h], 40h
0x1800664c7  mov     r8, rbx; Size
0x1800664ca  mov     rdx, [rdi+70h]; Src
0x1800664ce  mov     rcx, [rdi+18h]; void *
0x1800664d2  call    RtlCopyFromUser
0x1800664d7  nop
0x1800664d8  test    r13b, 10h
0x1800664dc  jnz     loc_1800665F6
0x1800664e2  mov     [rsp+88h+var_48], 0
0x1800664eb  mov     rcx, [rdi+18h]
0x1800664ef  mov     [rsp+88h+var_48], rcx
0x1800664f4  test    ebx, ebx
0x1800664f6  jz      loc_1800665F6
0x1800664fc  mov     edx, [rcx]
0x1800664fe  test    r12d, r12d
0x180066501  jz      short loc_180066525
0x180066503  cmp     edx, r12d
0x180066506  jz      short loc_18006650F
0x180066508  mov     eax, [rcx+30h]
0x18006650b  test    al, 8
0x18006650d  jz      short loc_180066514
0x18006650f  cmp     edx, 38h ; '8'
0x180066512  jnb     short loc_180066537
0x180066514  mov     ecx, 0C0000206h; Status
0x180066519  call    cs:__imp_ExRaiseStatus
0x180066525  cmp     edx, 38h ; '8'
0x180066528  jb      loc_1800665E5
0x18006652e  test    dl, 7
0x180066531  jnz     loc_1800665E5
0x180066537  cmp     ebx, edx
0x180066539  jnb     short loc_18006654C
0x18006653b  mov     ecx, 0C0000206h; Status
0x180066540  call    cs:__imp_ExRaiseStatus
0x18006654c  mov     eax, [rcx+24h]
0x18006654f  test    r14d, r14d
0x180066552  jz      short loc_1800665A3
0x180066554  cmp     eax, [rcx+20h]
0x180066557  jbe     short loc_18006656A
0x180066559  mov     ecx, 0C0000206h; Status
0x18006655e  call    cs:__imp_ExRaiseStatus
0x18006656a  mov     eax, [rcx+30h]
0x18006656d  test    al, 8
0x18006656f  jz      short loc_1800665D2
0x180066571  cmp     ebx, 38h ; '8'
0x180066574  jnz     short loc_180066592
0x180066576  cmp     rcx, [rdi+18h]
0x18006657a  jnz     short loc_180066592
0x18006657c  test    r13b, r13b
0x18006657f  js      short loc_1800665F6
0x180066581  mov     ecx, 0C000000Dh; Status
0x180066586  call    cs:__imp_ExRaiseStatus
0x180066592  mov     ecx, 0C0000206h; Status
0x180066597  call    cs:__imp_ExRaiseStatus
0x1800665a3  test    eax, eax
0x1800665a5  jz      short loc_1800665B8
0x1800665a7  mov     ecx, 0C0000206h; Status
0x1800665ac  call    cs:__imp_ExRaiseStatus
0x1800665b8  test    dword ptr [rcx+30h], 0FFFBF3FFh
0x1800665bf  jz      short loc_1800665D2
0x1800665c1  mov     ecx, 0C000000Dh; Status
0x1800665c6  call    cs:__imp_ExRaiseStatus
0x1800665d2  add     rcx, rdx
0x1800665d5  mov     [rsp+88h+var_48], rcx
0x1800665da  sub     ebx, edx
0x1800665dc  mov     [rsp+88h+var_4C], ebx
0x1800665e0  jmp     loc_1800664F4
0x1800665e5  mov     ecx, 0C0000206h; Status
0x1800665ea  call    cs:__imp_ExRaiseStatus
0x1800665f6  jmp     loc_1800663A5
0x1800665fb  mov     edi, eax
0x1800665fd  mov     rbx, [rsp+88h+arg_0]
0x180066605  cmp     qword ptr [rbx+18h], 0
0x18006660a  jz      short loc_18006662A
0x18006660c  xor     edx, edx; Tag
0x18006660e  mov     rcx, [rbx+18h]; P
0x180066612  call    cs:__imp_ExFreePoolWithTag
0x180066619  nop     dword ptr [rax+rax+00h]
0x18006661e  mov     qword ptr [rbx+18h], 0
0x180066626  and     dword ptr [rbx+10h], 0FFFFFFDFh
0x18006662a  mov     eax, edi
0x18006662c  jmp     loc_180066AEB
0x180066631  mov     eax, 0C0000206h
0x180066636  jmp     loc_180066AEB
0x18006663b  cmp     ecx, 38h ; '8'
0x18006663e  jb      loc_1800668A4
0x180066644  test    cl, 7
0x180066647  jnz     loc_1800668A4
0x18006664d  cmp     esi, ecx
0x18006664f  jnb     short loc_180066662
0x180066651  mov     ecx, 0C0000206h; Status
0x180066656  call    cs:__imp_ExRaiseStatus
0x180066662  mov     eax, [rbx+24h]
0x180066665  test    r13b, 1
0x180066669  jz      loc_180066719
0x18006666f  mov     edx, [rbx+20h]; Length
0x180066672  cmp     eax, edx
0x180066674  jbe     short loc_180066687
0x180066676  mov     ecx, 0C0000206h; Status
0x18006667b  call    cs:__imp_ExRaiseStatus
0x180066687  mov     ecx, [rbx+30h]
0x18006668a  test    cl, 8
0x18006668d  jz      loc_18006674A
0x180066693  cmp     esi, 38h ; '8'
0x180066696  jnz     short loc_180066708
0x180066698  cmp     rbx, [rdi+18h]
0x18006669c  jnz     short loc_180066708
0x18006669e  test    r13b, r13b
0x1800666a1  js      short loc_1800666B4
0x1800666a3  mov     ecx, 0C000000Dh; Status
0x1800666a8  call    cs:__imp_ExRaiseStatus
0x1800666b4  test    edx, edx
0x1800666b6  jz      loc_1800668B5
0x1800666bc  mov     [rsp+88h+Irp], rdi; Irp
0x1800666c1  mov     r9b, 1; ChargeQuota
0x1800666c4  xor     r8d, r8d; SecondaryBuffer
0x1800666c7  mov     rcx, [rbx+28h]; VirtualAddress
0x1800666cb  call    cs:__imp_IoAllocateMdl
0x1800666d2  nop     dword ptr [rax+rax+00h]
0x1800666d7  test    rax, rax
0x1800666da  jnz     short loc_1800666ED
0x1800666dc  mov     ecx, 0C000009Ah; Status
0x1800666e1  call    cs:__imp_ExRaiseStatus
0x1800666ed  test    [rbx+30h], r15d
0x1800666f1  jz      loc_1800668B5
0x1800666f7  mov     ecx, 0C0000206h; Status
0x1800666fc  call    cs:__imp_ExRaiseStatus
0x180066708  mov     ecx, 0C0000206h; Status
0x18006670d  call    cs:__imp_ExRaiseStatus
0x180066719  test    eax, eax
0x18006671b  jz      short loc_18006672E
0x18006671d  mov     ecx, 0C0000206h; Status
0x180066722  call    cs:__imp_ExRaiseStatus
0x18006672e  mov     ecx, [rbx+30h]
0x180066731  test    ecx, 0FFFA23FFh
0x180066737  jz      short loc_18006674A
0x180066739  mov     ecx, 0C000000Dh; Status
0x18006673e  call    cs:__imp_ExRaiseStatus
0x18006674a  mov     edx, [rbx+20h]; Length
0x18006674d  test    edx, edx
0x18006674f  jz      loc_180066878
0x180066755  mov     r10, [rbx+28h]
0x180066759  test    dword ptr [rbx+30h], 18000h
0x180066760  jz      short loc_180066778
0x180066762  test    r10, r10
0x180066765  jnz     short loc_180066778
0x180066767  mov     ecx, 0C000000Dh; Status
0x18006676c  call    cs:__imp_ExRaiseStatus
0x180066778  mov     rax, [r14]
0x18006677b  and     ecx, 18000h
0x180066781  mov     [rsp+88h+Irp], rdi; Irp
0x180066786  mov     r9b, 1; ChargeQuota
0x180066789  cmp     ecx, 18000h
0x18006678f  jz      short loc_1800667BD
0x180066791  test    rax, rax
0x180066794  setnz   r8b; SecondaryBuffer
0x180066798  mov     rcx, r10; VirtualAddress
0x18006679b  call    cs:__imp_IoAllocateMdl
0x1800667a2  nop     dword ptr [rax+rax+00h]
0x1800667a7  test    rax, rax
0x1800667aa  jnz     short loc_1800667EB
0x1800667ac  mov     ecx, 0C000009Ah; Status
0x1800667b1  call    cs:__imp_ExRaiseStatus
0x1800667bd  test    rax, rax
0x1800667c0  setnz   r8b; SecondaryBuffer
0x1800667c4  mov     edx, r15d; Length
0x1800667c7  xor     ecx, ecx; VirtualAddress
0x1800667c9  call    cs:__imp_IoAllocateMdl
0x1800667d0  nop     dword ptr [rax+rax+00h]
0x1800667d5  test    rax, rax
0x1800667d8  jnz     short loc_1800667EB
0x1800667da  mov     ecx, 0C000009Ah; Status
0x1800667df  call    cs:__imp_ExRaiseStatus
0x1800667eb  test    [rbx+30h], r15d
0x1800667ef  jz      loc_18006688F
0x1800667f5  mov     eax, 0A0h
0x1800667fa  cmp     esi, eax
0x1800667fc  jnb     short loc_18006680F
0x1800667fe  mov     ecx, 0C0000206h; Status
0x180066803  call    cs:__imp_ExRaiseStatus
0x18006680f  cmp     [rbx], eax
0x180066811  jnb     short loc_180066824
0x180066813  mov     ecx, 0C0000206h; Status
0x180066818  call    cs:__imp_ExRaiseStatus
0x180066824  mov     rcx, [rbx+88h]; VirtualAddress
0x18006682b  test    rcx, rcx
0x18006682e  jz      short loc_180066867
0x180066830  mov     edx, [rbx+80h]; Length
0x180066836  test    edx, edx
0x180066838  jz      short loc_180066867
0x18006683a  mov     [rsp+88h+Irp], rdi; Irp
0x18006683f  mov     r9b, 1; ChargeQuota
0x180066842  mov     r8b, r9b; SecondaryBuffer
0x180066845  call    cs:__imp_IoAllocateMdl
0x18006684c  nop     dword ptr [rax+rax+00h]
0x180066851  test    rax, rax
0x180066854  jnz     short loc_18006688F
0x180066856  mov     ecx, 0C000009Ah; Status
0x18006685b  call    cs:__imp_ExRaiseStatus
0x180066867  mov     ecx, 0C000000Dh; Status
0x18006686c  call    cs:__imp_ExRaiseStatus
0x180066878  test    [rbx+30h], r15d
0x18006687c  jz      short loc_18006688F
0x18006687e  mov     ecx, 0C000000Dh; Status
0x180066883  call    cs:__imp_ExRaiseStatus
0x18006688f  mov     eax, [rbx]
0x180066891  add     rbx, rax
0x180066894  mov     [rsp+88h+var_40], rbx
0x180066899  sub     esi, eax
0x18006689b  mov     [rsp+88h+var_54], esi
0x18006689f  jmp     loc_1800663F5
0x1800668a4  mov     ecx, 0C0000206h; Status
0x1800668a9  call    cs:__imp_ExRaiseStatus
0x1800668b5  lea     rsi, [rdi+8]
0x1800668b9  jmp     short loc_1800668C6
0x1800668bb  mov     [rsp+88h+var_58], 0
0x1800668c3  mov     rsi, r14
  ... truncated ...
```
