# RxQueryDirectory

- ea: `0x140068570`
- end: `0x140068e7b`
- name: `RxQueryDirectory`
- size: `2315`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, PMRX_FCB MrxFcb)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140068330`

## callees

- `0x140007ca0`
- `0x140009b80`
- `0x140014d10`
- `0x140014e40`
- `0x140016d40`
- `0x140016e20`
- `0x140016e70`
- `0x140017280`
- `0x140017370`
- `0x140018ac4`
- `0x140018b28`
- `0x140025d00`
- `0x140025d80`
- `0x140057660`
- `0x140068070`
- `0x140068570`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140068956`
- `ntoskrnl!ExAllocatePool2` at `0x140068956`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140068934`
- `ntoskrnl!FsRtlDoesNameContainWildCards` at `0x140068934`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140068750`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140068750`
- `ntoskrnl!RtlCompareMemory` at `0x140068a22`
- `ntoskrnl!RtlCompareMemory` at `0x140068a22`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140068813`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140068813`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068b4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068bc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068b4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140068bc8`

## string_xrefs

- `0x14007b255`: `RxQueryDirectory`

## pseudocode

```c
__int64 __fastcall RxQueryDirectory(PRX_CONTEXT RxContext, PIRP Irp, struct _FCB *MrxFcb, __int64 a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  UNICODE_STRING *FileName; // r14
  ULONG LowPart; // r8d
  unsigned __int8 v11; // r12
  ULONG Length; // r12d
  unsigned int v14; // eax
  ULONG Timer_high; // r8d
  const CHAR *v16; // r9
  __int64 v17; // rsi
  char v18; // cl
  void *v19; // rcx
  PMDL MdlAddress; // rcx
  PVOID MappedSystemVa; // rsi
  void *Pool2; // rcx
  const void **v23; // rdx
  char v24; // al
  __int64 Flags; // rdx
  __int64 v26; // r8
  char v27; // al
  const CHAR *BugCheckOnFailure; // [rsp+20h] [rbp-58h]
  ULONG BugCheckOnFailurea; // [rsp+20h] [rbp-58h]
  ULONG Priority; // [rsp+28h] [rbp-50h]
  void *v31; // [rsp+38h] [rbp-40h]
  char v32; // [rsp+88h] [rbp+10h]
  wchar_t **p_Buffer; // [rsp+88h] [rbp+10h]
  ULONG v34; // [rsp+98h] [rbp+20h]

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileName = CurrentStackLocation->Parameters.QueryDirectory.FileName;
  LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  v34 = LowPart;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v11 = 89;
  }
  else
  {
    v11 = 89;
    v24 = 89;
    if ( ((__int64)RxContext->RdbssDbgExtension & 2) == 0 )
      v24 = 78;
    LOBYTE(BugCheckOnFailure) = v24;
    WPP_SF_qc(WPP_GLOBAL_Control->AttachedDevice, 14, &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids, Irp);
    LowPart = v34;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids,
      CurrentStackLocation->Parameters.Read.Length);
    LowPart = v34;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      (unsigned int)&WPP_ac55395600da34284848d4e5839e1eb6_Traceguids,
      (_DWORD)FileName,
      (__int64)FileName);
    LowPart = v34;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids, LowPart);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      18,
      &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids,
      CurrentStackLocation->Parameters.Create.EaLength);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids, Irp->UserBuffer);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    Flags = CurrentStackLocation->Flags;
    v26 = 89;
    if ( (Flags & 4) == 0 )
      v26 = 78;
    v27 = 89;
    if ( (Flags & 2) == 0 )
      v27 = 78;
    if ( (Flags & 1) == 0 )
      v11 = 78;
    LOBYTE(Priority) = v26;
    LOBYTE(BugCheckOnFailure) = v27;
    WPP_SF_ccc(WPP_GLOBAL_Control->AttachedDevice, Flags, v26, v11);
  }
  if ( !a4 )
    return 3221225523LL;
  if ( FileName && (FileName->Length & 1) != 0 )
    return 3221225485LL;
  if ( *(_BYTE *)(*((_QWORD *)&MrxFcb->1 + 15) + 77LL) )
    return 3221225488LL;
  Length = CurrentStackLocation->Parameters.Read.Length;
  *((_DWORD *)&RxContext->9 + 28) = CurrentStackLocation->Parameters.Create.EaLength;
  *((_BYTE *)&RxContext->9 + 116) = CurrentStackLocation->Flags & 1;
  *((_BYTE *)&RxContext->9 + 117) = (CurrentStackLocation->Flags & 2) != 0;
  *((_BYTE *)&RxContext->9 + 118) = (CurrentStackLocation->Flags & 4) != 0;
  *((_BYTE *)&RxContext->9 + 119) = *(_QWORD *)(a4 + 88) == 0;
  v14 = _RxAcquireFcb(MrxFcb, RxContext, 1u, 0, BugCheckOnFailure, Priority);
  v17 = v14;
  if ( v14 )
  {
    if ( v14 == -1073741739 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids);
      }
      LODWORD(v17) = RxFsdPostRequest(RxContext);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          22,
          &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids,
          (unsigned int)v17);
        v18 = 0;
        goto LABEL_102;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      BugCheckOnFailurea = v14;
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids, MrxFcb);
    }
    v18 = 0;
    goto LABEL_102;
  }
  v18 = 1;
  if ( (*((_DWORD *)&MrxFcb->1 + 39) & 0x80u) == 0 )
  {
    if ( !FileName || FileName->Length == (_WORD)v14 )
      v32 = v14;
    else
      v32 = 1;
    if ( *((_BYTE *)&RxContext->9 + 118) == (_BYTE)v14 && *((_BYTE *)&RxContext->9 + 116) != (_BYTE)v14 )
      *((_DWORD *)&RxContext->9 + 28) = v14;
    if ( *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 38) == (_BYTE)v14 )
    {
      SeCaptureSubjectContext((PSECURITY_SUBJECT_CONTEXT)((char *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory
                                                        + 40));
      *((_BYTE *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 38) = 1;
    }
    if ( *((_BYTE *)&RxContext->9 + 119) == (_BYTE)v17 && (!v32 || *((_BYTE *)&RxContext->9 + 116) == (_BYTE)v17) )
      goto LABEL_34;
    if ( v32 && (FileName->Length != 2 || *FileName->Buffer != 42) )
    {
      if ( FileName->Length != 24 )
      {
        p_Buffer = &FileName->Buffer;
        goto LABEL_54;
      }
      p_Buffer = &FileName->Buffer;
      if ( RtlCompareMemory(FileName->Buffer, Rx8QMdot3QM, 0x18u) != 24 )
      {
LABEL_54:
        *(_BYTE *)(a4 + 145) = FsRtlDoesNameContainWildCards(FileName);
        Pool2 = (void *)ExAllocatePool2(258, FileName->Length, 1934456914);
        v31 = Pool2;
        if ( Pool2 )
        {
          if ( *(_QWORD *)(a4 + 88) )
          {
            if ( (*(_DWORD *)(a4 + 72) & 0x20000) != 0 )
            {
              ExFreePoolWithTag(*(PVOID *)(a4 + 88), 0);
              *(_QWORD *)(a4 + 88) = v17;
              *(_DWORD *)(a4 + 72) &= ~0x20000u;
              v23 = (const void **)&FileName->Buffer;
              Pool2 = v31;
            }
            else
            {
              v23 = (const void **)&FileName->Buffer;
            }
          }
          else
          {
            v23 = (const void **)p_Buffer;
          }
          *(_QWORD *)(a4 + 88) = Pool2;
          *(_WORD *)(a4 + 80) = FileName->Length;
          *(_WORD *)(a4 + 82) = FileName->Length;
          memmove(Pool2, *v23, FileName->Length);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids, a4 + 80);
          }
          *(_DWORD *)(a4 + 72) |= 0x20000u;
        }
        else
        {
          LODWORD(v17) = -1073741670;
        }
LABEL_34:
        Timer_high = 2;
        if ( (_DWORD)v17 )
        {
          v18 = 1;
        }
        else
        {
          *((_BYTE *)&RxContext->9 + 120) = *(_BYTE *)(a4 + 145);
          RxLockUserBuffer(RxContext, Irp, IoModifyAccess, Length);
          RxContext->LowIoContext.ParamsFor.Locks.Flags = v34;
          MdlAddress = Irp->MdlAddress;
          if ( MdlAddress )
          {
            if ( (MdlAddress->MdlFlags & 5) != 0 )
              MappedSystemVa = MdlAddress->MappedSystemVa;
            else
              MappedSystemVa = MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
          }
          else
          {
            MappedSystemVa = Irp->UserBuffer;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (Timer_high & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                16,
                &WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids,
                MappedSystemVa);
          }
          RxContext->LowIoContext.ParamsFor.ReadWrite.ByteOffset = (RXVBO)MappedSystemVa;
          *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8) = Length;
          if ( MappedSystemVa )
          {
            if ( *(_QWORD *)(RxContext->pFcb[2].Header.ValidDataLength.QuadPart + 192) )
            {
              if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) != 0 )
              {
                LODWORD(v17) = -1073741536;
              }
              else
              {
                *(_OWORD *)&RxContext->MRxContext[2] = 0;
                *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
                RxContext->ResumeRoutine = 0;
                LODWORD(v17) = (*(__int64 (__fastcall **)(PRX_CONTEXT))(RxContext->pFcb[2].Header.ValidDataLength.QuadPart
                                                                      + 192))(RxContext);
              }
            }
            else
            {
              LODWORD(v17) = -1073741822;
            }
            if ( BYTE3(RxContext->RealDevice) )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids);
              }
              LODWORD(v17) = RxFsdPostRequest(RxContext);
              v18 = 1;
            }
            else
            {
              Irp->IoStatus.Information = Length
                                        - *((_DWORD *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory + 8);
              v18 = 1;
            }
          }
          else
          {
            LODWORD(v17) = -1073741811;
            if ( Irp->MdlAddress )
              LODWORD(v17) = -1073741670;
            v18 = 1;
          }
        }
        goto LABEL_102;
      }
    }
    *(_BYTE *)(a4 + 145) = 1;
    v19 = *(void **)(a4 + 88);
    if ( v19 && (*(_DWORD *)(a4 + 72) & 0x20000) != 0 )
    {
      ExFreePoolWithTag(v19, 0);
      *(_QWORD *)(a4 + 88) = v17;
      *(_DWORD *)(a4 + 72) &= ~0x20000u;
    }
    *(_QWORD *)(a4 + 88) = &RxStarForTemplate;
    *(_DWORD *)(a4 + 80) = 131074;
    goto LABEL_34;
  }
  LODWORD(v17) = -1073741528;
LABEL_102:
  if ( v18 )
    _RxReleaseFcb(RxContext, (PMRX_FCB)&MrxFcb->Header, Timer_high, v16, BugCheckOnFailurea);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      26,
      &WPP_ac55395600da34284848d4e5839e1eb6_Traceguids,
      (unsigned int)v17);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140068570  mov     [rsp+arg_10], r8
0x140068575  mov     [rsp+arg_0], rcx
0x14006857a  push    rbx
0x14006857b  push    rsi
0x14006857c  push    rdi
0x14006857d  push    r12
0x14006857f  push    r13
0x140068581  push    r14
0x140068583  push    r15
0x140068585  sub     rsp, 40h
0x140068589  mov     r15, r9
0x14006858c  mov     rdi, r8
0x14006858f  mov     r13, rdx
0x140068592  mov     rbx, rcx
0x140068595  mov     rsi, [rdx+0B8h]
0x14006859c  mov     r14, [rsi+10h]
0x1400685a0  mov     r8d, [rsi+18h]
0x1400685a4  mov     [rsp+78h+arg_18], r8d
0x1400685ac  lea     rdx, WPP_GLOBAL_Control
0x1400685b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400685ba  cmp     rcx, rdx
0x1400685bd  jz      short loc_1400685CA
0x1400685bf  mov     eax, [rcx+2Ch]
0x1400685c2  test    al, 2
0x1400685c4  jnz     loc_140068C90
0x1400685ca  mov     r12d, 59h ; 'Y'
0x1400685d0  mov     r9d, 4Eh ; 'N'
0x1400685d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400685dd  cmp     rcx, rdx
0x1400685e0  jz      short loc_1400685ED
0x1400685e2  mov     eax, [rcx+2Ch]
0x1400685e5  test    al, 2
0x1400685e7  jnz     loc_140068CE0
0x1400685ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400685f4  cmp     rcx, rdx
0x1400685f7  jz      short loc_140068604
0x1400685f9  mov     eax, [rcx+2Ch]
0x1400685fc  test    al, 2
0x1400685fe  jnz     loc_140068D1D
0x140068604  mov     rcx, cs:WPP_GLOBAL_Control
0x14006860b  cmp     rcx, rdx
0x14006860e  jz      short loc_14006861B
0x140068610  mov     eax, [rcx+2Ch]
0x140068613  test    al, 2
0x140068615  jnz     loc_140068D5E
0x14006861b  mov     rcx, cs:WPP_GLOBAL_Control
0x140068622  cmp     rcx, rdx
0x140068625  jz      short loc_140068632
0x140068627  mov     eax, [rcx+2Ch]
0x14006862a  test    al, 2
0x14006862c  jnz     loc_140068D92
0x140068632  mov     rcx, cs:WPP_GLOBAL_Control
0x140068639  cmp     rcx, rdx
0x14006863c  jz      short loc_140068649
0x14006863e  mov     eax, [rcx+2Ch]
0x140068641  test    al, 2
0x140068643  jnz     loc_140068DC7
0x140068649  mov     rcx, cs:WPP_GLOBAL_Control
0x140068650  cmp     rcx, rdx
0x140068653  jz      short loc_140068660
0x140068655  mov     eax, [rcx+2Ch]
0x140068658  test    al, 2
0x14006865a  jnz     loc_140068DFC
0x140068660  test    r15, r15
0x140068663  jz      loc_140068E40
0x140068669  test    r14, r14
0x14006866c  jz      short loc_140068678
0x14006866e  test    byte ptr [r14], 1
0x140068672  jnz     loc_140068E4A
0x140068678  mov     rax, [rdi+78h]
0x14006867c  cmp     byte ptr [rax+4Dh], 0
0x140068680  jz      short loc_140068698
0x140068682  mov     eax, 0C0000010h
0x140068687  add     rsp, 40h
0x14006868b  pop     r15
0x14006868d  pop     r14
0x14006868f  pop     r13
0x140068691  pop     r12
0x140068693  pop     rdi
0x140068694  pop     rsi
0x140068695  pop     rbx
0x140068696  retn
0x140068698  mov     [rsp+78h+var_48], 0
0x14006869d  mov     r12d, [rsi+8]
0x1400686a1  mov     eax, [rsi+20h]
0x1400686a4  mov     [rbx+200h], eax
0x1400686aa  movzx   eax, byte ptr [rsi+2]
0x1400686ae  and     al, 1
0x1400686b0  mov     [rbx+204h], al
0x1400686b6  movzx   eax, byte ptr [rsi+2]
0x1400686ba  shr     al, 1
0x1400686bc  and     al, 1
0x1400686be  mov     [rbx+205h], al
0x1400686c4  movzx   eax, byte ptr [rsi+2]
0x1400686c8  shr     al, 2
0x1400686cb  and     al, 1
0x1400686cd  mov     [rbx+206h], al
0x1400686d3  cmp     qword ptr [r15+58h], 0
0x1400686d8  setz    al
0x1400686db  mov     [rbx+207h], al
0x1400686e1  xor     r9d, r9d; LineNumber
0x1400686e4  mov     r8d, 1; Mode
0x1400686ea  mov     rdx, rbx; RxContext
0x1400686ed  mov     rcx, rdi; Fcb
0x1400686f0  call    __RxAcquireFcb
0x1400686f5  mov     esi, eax
0x1400686f7  test    eax, eax
0x1400686f9  jnz     loc_140068A59
0x1400686ff  mov     cl, 1
0x140068701  mov     [rsp+78h+var_48], cl
0x140068705  mov     eax, [rdi+9Ch]
0x14006870b  test    al, al
0x14006870d  js      loc_140068B1F
0x140068713  mov     [rsp+78h+var_44], esi
0x140068717  test    r14, r14
0x14006871a  jnz     loc_1400688F7
0x140068720  mov     byte ptr [rsp+78h+arg_8], sil
0x140068728  cmp     [rbx+206h], sil
0x14006872f  jnz     short loc_140068740
0x140068731  cmp     [rbx+204h], sil
0x140068738  jz      short loc_140068740
0x14006873a  mov     [rbx+200h], esi
0x140068740  cmp     [rbx+1DEh], sil
0x140068747  jnz     short loc_140068763
0x140068749  lea     rcx, [rbx+1E0h]; SubjectContext
0x140068750  call    cs:__imp_SeCaptureSubjectContext
0x140068757  nop     dword ptr [rax+rax+00h]
0x14006875c  mov     byte ptr [rbx+1DEh], 1
0x140068763  movzx   eax, byte ptr [rsp+78h+arg_8]
0x14006876b  cmp     [rbx+207h], sil
0x140068772  jz      loc_1400688DD
0x140068778  test    al, al
0x14006877a  jnz     loc_14006890D
0x140068780  mov     byte ptr [r15+91h], 1
0x140068788  mov     rcx, [r15+58h]; P
0x14006878c  test    rcx, rcx
0x14006878f  jnz     loc_140068BB8
0x140068795  lea     rax, RxStarForTemplate
0x14006879c  mov     [r15+58h], rax
0x1400687a0  mov     dword ptr [r15+50h], 20002h
0x1400687a8  mov     r14d, 0C000009Ah
0x1400687ae  mov     r8d, 2; Operation
0x1400687b4  test    esi, esi
0x1400687b6  jnz     loc_1400689D5
0x1400687bc  movzx   eax, byte ptr [r15+91h]
0x1400687c4  mov     [rbx+208h], al
0x1400687ca  mov     r9d, r12d; BufferLength
0x1400687cd  mov     rdx, r13; Irp
0x1400687d0  mov     rcx, rbx; RxContext
0x1400687d3  call    RxLockUserBuffer
0x1400687d8  mov     eax, [rsp+78h+arg_18]
0x1400687df  mov     [rbx+1C0h], eax
0x1400687e5  mov     rcx, [r13+8]; MemoryDescriptorList
0x1400687e9  test    rcx, rcx
0x1400687ec  jz      loc_1400689E6
0x1400687f2  test    byte ptr [rcx+0Ah], 5
0x1400687f6  jnz     loc_1400689FD
0x1400687fc  mov     [rsp+78h+Priority], 40000010h; Priority
0x140068804  mov     [rsp+78h+BugCheckOnFailure], esi; SerialNumber
0x140068808  xor     r9d, r9d; RequestedAddress
0x14006880b  xor     edx, edx; AccessMode
0x14006880d  mov     r8d, 1; CacheType
0x140068813  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006881a  nop     dword ptr [rax+rax+00h]
0x14006881f  mov     rsi, rax
0x140068822  mov     rcx, cs:WPP_GLOBAL_Control
0x140068829  lea     r15, WPP_GLOBAL_Control
0x140068830  cmp     rcx, r15
0x140068833  jz      short loc_140068843
0x140068835  mov     r8d, [rcx+2Ch]
0x140068839  test    r8b, 2
0x14006883d  jnz     loc_140068BE5
0x140068843  mov     [rbx+1C8h], rsi
0x14006884a  mov     [rbx+1D8h], r12d
0x140068851  test    rsi, rsi
0x140068854  jz      loc_140068A3D
0x14006885a  mov     rax, [rbx+38h]
0x14006885e  mov     rcx, [rax+188h]
0x140068865  cmp     qword ptr [rcx+0C0h], 0
0x14006886d  jz      loc_1400689EF
0x140068873  mov     eax, [rbx+80h]
0x140068879  test    al, 2
0x14006887b  jnz     loc_140068C0C
0x140068881  xorps   xmm0, xmm0
0x140068884  xor     eax, eax
0x140068886  movups  xmmword ptr [rbx+0D0h], xmm0
0x14006888d  movups  xmmword ptr [rbx+0E0h], xmm0
0x140068894  mov     [rbx+0F0h], rax
0x14006889b  mov     rax, [rbx+38h]
0x14006889f  mov     rcx, [rax+188h]
0x1400688a6  mov     rax, [rcx+0C0h]
0x1400688ad  mov     rcx, rbx
0x1400688b0  call    _guard_dispatch_icall
0x1400688b5  mov     esi, eax
0x1400688b7  mov     [rsp+78h+var_44], eax
0x1400688bb  cmp     byte ptr [rbx+23h], 0
0x1400688bf  jnz     loc_140068C16
0x1400688c5  sub     r12d, [rbx+1D8h]
0x1400688cc  mov     eax, r12d
0x1400688cf  mov     [r13+38h], rax
0x1400688d3  movzx   ecx, [rsp+78h+var_48]
0x1400688d8  jmp     loc_140068C57
0x1400688dd  test    al, al
0x1400688df  jz      loc_1400687A8
0x1400688e5  cmp     [rbx+204h], sil
0x1400688ec  jz      loc_1400687A8
0x1400688f2  jmp     loc_140068778
0x1400688f7  cmp     [r14], si
0x1400688fb  jz      loc_140068720
0x140068901  mov     byte ptr [rsp+78h+arg_8], cl
0x140068908  jmp     loc_140068728
0x14006890d  movzx   edx, word ptr [r14]
0x140068911  lea     rcx, [r14+8]
0x140068915  cmp     dx, 2
0x140068919  jz      loc_140068B2D
0x14006891f  cmp     dx, 18h
0x140068923  jz      loc_140068A06
0x140068929  mov     [rsp+78h+arg_8], rcx
0x140068931  mov     rcx, r14; Name
0x140068934  call    cs:__imp_FsRtlDoesNameContainWildCards
0x14006893b  nop     dword ptr [rax+rax+00h]
0x140068940  mov     [r15+91h], al
0x140068947  movzx   edx, word ptr [r14]
0x14006894b  mov     ecx, 102h
0x140068950  mov     r8d, 734D7852h
0x140068956  call    cs:__imp_ExAllocatePool2
0x14006895d  nop     dword ptr [rax+rax+00h]
0x140068962  mov     rcx, rax; void *
0x140068965  mov     [rsp+78h+var_40], rax
0x14006896a  test    rax, rax
0x14006896d  jz      loc_140068BA5
0x140068973  mov     rax, [r15+58h]
0x140068977  test    rax, rax
0x14006897a  jnz     loc_140068B3F
0x140068980  mov     rdx, [rsp+78h+arg_8]
0x140068988  mov     [r15+58h], rcx
0x14006898c  movzx   eax, word ptr [r14]
0x140068990  mov     [r15+50h], ax
0x140068995  movzx   eax, word ptr [r14]
0x140068999  mov     [r15+52h], ax
0x14006899e  movzx   r8d, word ptr [r14]; Size
0x1400689a2  mov     rdx, [rdx]; Src
0x1400689a5  call    memmove
0x1400689aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400689b1  lea     rax, WPP_GLOBAL_Control
0x1400689b8  cmp     rcx, rax
0x1400689bb  jz      short loc_1400689C8
0x1400689bd  mov     eax, [rcx+2Ch]
0x1400689c0  test    al, 2
0x1400689c2  jnz     loc_140068B7D
0x1400689c8  or      dword ptr [r15+48h], 20000h
0x1400689d0  jmp     loc_1400687A8
0x1400689d5  movzx   ecx, [rsp+78h+var_48]
0x1400689da  lea     r15, WPP_GLOBAL_Control
0x1400689e1  jmp     loc_140068C57
0x1400689e6  mov     rsi, [r13+70h]
0x1400689ea  jmp     loc_140068822
0x1400689ef  mov     esi, 0C0000002h
0x1400689f4  mov     [rsp+78h+var_44], esi
0x1400689f8  jmp     loc_1400688BB
0x1400689fd  mov     rsi, [rcx+18h]
0x140068a01  jmp     loc_140068822
0x140068a06  lea     rax, [r14+8]
0x140068a0a  mov     [rsp+78h+arg_8], rax
0x140068a12  mov     r8d, 18h; Length
0x140068a18  lea     rdx, Rx8QMdot3QM; ">>>>>>>>.>>>"
0x140068a1f  mov     rcx, [rax]; Source1
0x140068a22  call    cs:__imp_RtlCompareMemory
0x140068a29  nop     dword ptr [rax+rax+00h]
0x140068a2e  cmp     rax, 18h
0x140068a32  jz      loc_140068780
0x140068a38  jmp     loc_140068931
0x140068a3d  mov     esi, 0C000000Dh
0x140068a42  cmp     qword ptr [r13+8], 0
0x140068a47  cmovnz  esi, r14d
0x140068a4b  mov     [rsp+78h+var_44], esi
0x140068a4f  movzx   ecx, [rsp+78h+var_48]
0x140068a54  jmp     loc_140068C57
0x140068a59  cmp     esi, 0C0000055h
0x140068a5f  jnz     short loc_140068ADC
0x140068a61  mov     rcx, cs:WPP_GLOBAL_Control
0x140068a68  lea     r15, WPP_GLOBAL_Control
0x140068a6f  cmp     rcx, r15
0x140068a72  jz      short loc_140068A96
0x140068a74  mov     eax, [rcx+2Ch]
0x140068a77  test    al, 2
0x140068a79  jz      short loc_140068A96
0x140068a7b  cmp     byte ptr [rcx+29h], 4
0x140068a7f  jb      short loc_140068A96
0x140068a81  mov     edx, 15h
0x140068a86  lea     r8, WPP_ac55395600da34284848d4e5839e1eb6_Traceguids
0x140068a8d  mov     rcx, [rcx+18h]
0x140068a91  call    WPP_SF_
0x140068a96  mov     rcx, rbx; RxContext
0x140068a99  call    RxFsdPostRequest
0x140068a9e  mov     esi, eax
0x140068aa0  mov     [rsp+78h+var_44], eax
0x140068aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140068aab  cmp     rcx, r15
0x140068aae  jz      short loc_140068B18
  ... truncated ...
```
