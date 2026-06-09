# RxCommonCreate

- ea: `0x140053400`
- end: `0x14005389b`
- name: `RxCommonCreate`
- size: `1179`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x140004050`
- `0x140009b80`
- `0x14000a830`
- `0x14000d450`
- `0x14000e910`
- `0x1400105f0`
- `0x140010980`
- `0x140014e40`
- `0x140015230`
- `0x1400169b0`
- `0x140016e70`
- `0x140017280`
- `0x140018994`
- `0x140025d00`
- `0x140025d80`
- `0x140052bb0`
- `0x140053400`
- `0x1400538b0`
- `0x140054ca0`
- `0x140057660`
- `0x140058540`
- `0x140071590`

## import_xrefs

- `ntoskrnl!DbgPrint` at `0x14007c5b0`
- `ntoskrnl!DbgPrint` at `0x14007c5b0`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14007c417`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14007c417`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14007c438`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14007c460`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14007c438`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14007c460`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007c536`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007c536`
- `ntoskrnl!KeResetEvent` at `0x14007c3c3`
- `ntoskrnl!KeResetEvent` at `0x14007c3e5`
- `ntoskrnl!KeResetEvent` at `0x14007c3c3`
- `ntoskrnl!KeResetEvent` at `0x14007c3e5`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14007c550`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14007c550`
- `ntoskrnl!MmForceSectionClosed` at `0x14007c451`
- `ntoskrnl!MmForceSectionClosed` at `0x14007c451`
- `ntoskrnl!IoCancelIrp` at `0x14007c3a8`
- `ntoskrnl!IoCancelIrp` at `0x14007c3a8`

## string_xrefs

- `0x14007c589`: `DEBUG_CREATE: FO %p, RxContext %p Irp %p, DesiredAccess %x ShareAccess %x Status %x %wZ\n`

## pseudocode

```c
__int64 __fastcall RxCommonCreate(PRX_CONTEXT RxContext, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  PNON_PAGED_FCB NonPagedFcb; // rax
  PIRP v5; // r15
  PFILE_OBJECT FileObject; // rsi
  struct _LIST_ENTRY *Blink; // rcx
  UNICODE_STRING *p_FileName; // r14
  struct _FILE_OBJECT *RelatedFileObject; // r9
  __int64 result; // rax
  wchar_t *Buffer; // rcx
  int TreeConnect; // edi
  __int64 v13; // rdx
  PIRP CurrentIrp; // rcx
  PDEVICE_OBJECT v15; // rcx
  int v16; // edx
  struct _LIST_ENTRY *Flink; // rax
  char *FsContext; // rdi
  unsigned __int16 v19; // ax
  wchar_t *v20; // rax
  struct _FCB *pFcb; // r13
  IRP *TopLevelIrp; // rdi
  ULONG v23; // r8d
  const CHAR *v24; // r9
  const CHAR *v25; // [rsp+20h] [rbp-88h]
  __int64 v26; // [rsp+28h] [rbp-80h]
  __int64 v27; // [rsp+30h] [rbp-78h]
  UNICODE_STRING v28; // [rsp+60h] [rbp-48h] BYREF
  UNICODE_STRING DestinationString; // [rsp+70h] [rbp-38h] BYREF

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  NonPagedFcb = RxContext->NonPagedFcb;
  v5 = Irp;
  FileObject = CurrentStackLocation->FileObject;
  v28 = 0;
  Blink = NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
  if ( Blink )
  {
    Flink = Blink[42].Flink;
    if ( Flink )
    {
      LOBYTE(Irp) = 4;
      ((void (__fastcall *)(PRX_CONTEXT, PIRP))Flink)(RxContext, Irp);
    }
  }
  p_FileName = &FileObject->FileName;
  if ( !FileObject->FileName.Length && !FileObject->RelatedFileObject )
  {
    FileObject->FsContext2 = 0;
    FileObject->FsContext = &RxDeviceFCB;
    ++LODWORD(RxDeviceFCB.ScavengerFinalizationList.Flink);
    ++LODWORD(RxDeviceFCB.NonPaged);
    v5->IoStatus.Information = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 61, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, FileObject);
    }
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqLLLLLZ(
      WPP_GLOBAL_Control->AttachedDevice,
      CurrentStackLocation->Parameters.Create.ShareAccess,
      CurrentStackLocation->Parameters.Create.FileAttributes,
      (_DWORD)RxContext,
      (char)FileObject,
      CurrentStackLocation->Parameters.Create.Options,
      CurrentStackLocation->Flags,
      CurrentStackLocation->Parameters.Create.FileAttributes,
      CurrentStackLocation->Parameters.Create.ShareAccess,
      *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16),
      (__int64)&FileObject->FileName);
  }
  RelatedFileObject = FileObject->RelatedFileObject;
  if ( RelatedFileObject && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    FsContext = (char *)RelatedFileObject->FsContext;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        63,
        &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
        RelatedFileObject,
        RelatedFileObject->FsContext);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          64,
          &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
          FsContext + 336);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          65,
          &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
          FsContext + 360);
      }
    }
  }
  if ( (CurrentStackLocation->Flags & 4) != 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 66, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
  }
  if ( (CurrentStackLocation->Parameters.Create.Options & 0x2000) != 0 )
    return 3221225659LL;
  result = RxpInitializeCreateContext((__int64)RxContext);
  if ( (int)result >= 0 )
  {
    if ( (CurrentStackLocation->Parameters.Create.Options & 0x80u) != 0 )
    {
      TreeConnect = RxCreateTreeConnect(RxContext, (char *)v5);
      goto LABEL_25;
    }
    if ( p_FileName->Length > 2u )
    {
      Buffer = FileObject->FileName.Buffer;
      if ( Buffer[1] == 92 && *Buffer == 92 )
      {
        v19 = p_FileName->Length - 2;
        p_FileName->Length = v19;
        memmove(Buffer, Buffer + 1, v19);
        if ( p_FileName->Length > 2u )
        {
          v20 = FileObject->FileName.Buffer;
          if ( v20[1] == 92 && *v20 == 92 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
            }
            return 3221225523LL;
          }
        }
      }
    }
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          while ( 1 )
          {
            if ( p_FileName->Length
              && FileObject->FileName.Buffer[((unsigned __int64)p_FileName->Length >> 1) - 1] == 92 )
            {
              if ( (CurrentStackLocation->Parameters.Create.Options & 0x40) != 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, &WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids);
                }
                TreeConnect = -1073741773;
                goto LABEL_24;
              }
              p_FileName->Length -= 2;
              WORD1(RxContext->TrackerHistory[4].FileName) |= 2u;
            }
            TreeConnect = RxCanonicalizeNameAndObtainNetRoot(RxContext, (char *)v5, &FileObject->FileName, &v28);
            if ( TreeConnect != -1073741802 )
              goto LABEL_24;
            v13 = *((_QWORD *)RxContext->TrackerHistory[0].FileName + 4);
            if ( RxContext->NonPagedFcb != *(PNON_PAGED_FCB *)(v13 + 48) )
            {
              v5->IoStatus.Information = 1;
              TreeConnect = 260;
              goto LABEL_24;
            }
            TreeConnect = RxCheckForNetworkOpenRestrictions(RxContext, v13);
            if ( TreeConnect < 0 )
              goto LABEL_24;
            TreeConnect = RxCreateFromNetRoot(RxContext, v5, (PIRP)&v28);
            RxUpdateNetworkOpenLocationInformation(RxContext);
            if ( TreeConnect == 260 )
            {
              CurrentIrp = RxContext->CurrentIrp;
              if ( _bittest16((const signed __int16 *)&RxContext->TrackerHistory[4].FileName + 1, 0xEu) )
              {
                CurrentIrp->IoStatus.Information = 1;
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  v16 = 69;
                  goto LABEL_23;
                }
              }
              else
              {
                CurrentIrp->IoStatus.Information = 0;
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  v16 = 70;
LABEL_23:
                  WPP_SF_qZD(
                    v15->AttachedDevice,
                    v16,
                    (unsigned int)&WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids,
                    (_DWORD)v5,
                    (__int64)&FileObject->FileName,
                    4);
                }
              }
LABEL_24:
              if ( byte_14003314D )
              {
                if ( TreeConnect != -1
                  && TreeConnect == RxDebugCreate
                  && (dword_140033144 & *((_DWORD *)&RxContext->9 + 28)) == dword_140033144
                  && (RxContext->Create.PipeReadMode & dword_140033148) == dword_140033148 )
                {
                  DestinationString = 0;
                  RtlInitUnicodeString(&DestinationString, &word_14003314E);
                  if ( FsRtlIsNameInExpression(&DestinationString, &FileObject->FileName, 1u, 0) )
                  {
                    if ( TreeConnect >= 0 && TreeConnect != 260 )
                    {
                      LOBYTE(RxContext->pFcb[1].UncleanCount) = 1;
                      BYTE4(RxContext->pFobx[1].Context) = 1;
                    }
                    LODWORD(v27) = TreeConnect;
                    LODWORD(v26) = RxContext->Create.PipeReadMode;
                    LODWORD(v25) = *((_DWORD *)&RxContext->9 + 28);
                    DbgPrint(
                      "DEBUG_CREATE: FO %p, RxContext %p Irp %p, DesiredAccess %x ShareAccess %x Status %x %wZ\n",
                      FileObject,
                      RxContext,
                      v5,
                      v25,
                      v26,
                      v27,
                      &FileObject->FileName);
                    if ( byte_14003314C )
                      __debugbreak();
                  }
                }
              }
LABEL_25:
              if ( TreeConnect == -1069481983 )
                RxpPrepareCreateContextForReuse(RxContext);
              return (unsigned int)TreeConnect;
            }
            if ( TreeConnect != -1073741738 )
              break;
            if ( (BYTE5(RxContext->TrackerHistory[4].FileName) & 1) == 0
              || ((__int64)RxContext->pFcb[1].Header.FileContextSupportPointer & 2) == 0 )
            {
              goto LABEL_24;
            }
            RxpPrepareCreateContextForReuse(RxContext);
          }
          if ( TreeConnect != -1073740747 )
            break;
          if ( (BYTE5(RxContext->TrackerHistory[4].FileName) & 3) != 3 )
            goto LABEL_24;
          pFcb = (struct _FCB *)RxContext->pFcb;
          TopLevelIrp = IoGetTopLevelIrp();
          RxpReferenceNetFcb(pFcb);
          RxpPrepareCreateContextForReuse(RxContext);
          IoSetTopLevelIrp(0);
          MmForceSectionClosed((PSECTION_OBJECT_POINTERS)&pFcb->RxDeviceObject->DriverObject, 1u);
          IoSetTopLevelIrp(TopLevelIrp);
          _RxAcquireFcb(pFcb, 0, 1u, 0, v25, v26);
          if ( !RxpDereferenceAndFinalizeNetFcb(pFcb, 0, 0, 0) )
            _RxReleaseFcb(0, (PMRX_FCB)&pFcb->Header, v23, v24, (ULONG)v25);
        }
        if ( TreeConnect == 871 )
          break;
LABEL_45:
        if ( TreeConnect != -1073741802 )
          goto LABEL_24;
      }
      RxpPrepareCreateContextForReuse(RxContext);
      TreeConnect = RxCancellableWaitSync(RxContext);
      if ( TreeConnect < 0 )
      {
        IoCancelIrp(v5);
        RxWaitSync(RxContext);
        KeResetEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType);
        CurrentStackLocation->Control &= ~1u;
        goto LABEL_45;
      }
      TreeConnect = RxContext->StoredStatus;
      KeResetEvent((PRKEVENT)&RxContext->PrefixClaim.NetRootType);
      CurrentStackLocation->Control &= ~1u;
      if ( TreeConnect < 0 )
        goto LABEL_45;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140053400  push    rbx
0x140053402  push    rbp
0x140053403  push    rsi
0x140053404  push    r14
0x140053406  push    r15
0x140053408  sub     rsp, 80h
0x14005340f  mov     rbp, [rdx+0B8h]
0x140053416  xorps   xmm0, xmm0
0x140053419  mov     rax, [rcx+50h]
0x14005341d  mov     rbx, rcx
0x140053420  mov     r15, rdx
0x140053423  mov     rsi, [rbp+30h]
0x140053427  movups  [rsp+0A8h+var_48], xmm0
0x14005342c  mov     rcx, [rax+160h]
0x140053433  test    rcx, rcx
0x140053436  jnz     loc_140053604
0x14005343c  cmp     word ptr [rsi+58h], 0
0x140053441  lea     r14, [rsi+58h]
0x140053445  mov     [rsp+0A8h+arg_8], r12
0x14005344d  jz      loc_140053623
0x140053453  mov     rcx, cs:WPP_GLOBAL_Control
0x14005345a  lea     r12, WPP_GLOBAL_Control
0x140053461  cmp     rcx, r12
0x140053464  jz      short loc_140053471
0x140053466  mov     eax, [rcx+2Ch]
0x140053469  test    al, 4
0x14005346b  jnz     loc_14007C2A4
0x140053471  mov     r9, [rsi+40h]
0x140053475  mov     [rsp+0A8h+arg_0], rdi
0x14005347d  test    r9, r9
0x140053480  jnz     loc_140053673
0x140053486  test    byte ptr [rbp+2], 4
0x14005348a  jnz     loc_1400537BC
0x140053490  test    dword ptr [rbp+10h], 2000h
0x140053497  jnz     loc_1400537FB
0x14005349d  mov     rcx, rbx
0x1400534a0  call    RxpInitializeCreateContext
0x1400534a5  test    eax, eax
0x1400534a7  js      loc_1400535E4
0x1400534ad  mov     eax, [rbp+10h]
0x1400534b0  test    al, al
0x1400534b2  js      loc_140053713
0x1400534b8  movzx   eax, word ptr [r14]
0x1400534bc  cmp     ax, 2
0x1400534c0  jbe     short loc_1400534D5
0x1400534c2  mov     rcx, [rsi+60h]; void *
0x1400534c6  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1400534cb  lea     rdx, [rcx+2]; Src
0x1400534cf  jz      loc_14007C2F8
0x1400534d5  mov     [rsp+0A8h+arg_10], r13
0x1400534dd  movzx   edx, word ptr [r14]
0x1400534e1  test    dx, dx
0x1400534e4  jz      short loc_1400534FB
0x1400534e6  mov     rax, [rsi+60h]
0x1400534ea  mov     ecx, edx
0x1400534ec  shr     rcx, 1
0x1400534ef  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400534f5  jz      loc_1400536F3
0x1400534fb  lea     r9, [rsp+0A8h+var_48]
0x140053500  mov     r8, r14
0x140053503  mov     rdx, r15; Irp
0x140053506  mov     rcx, rbx; RxContext
0x140053509  call    RxCanonicalizeNameAndObtainNetRoot
0x14005350e  mov     edi, eax
0x140053510  cmp     eax, 0C0000016h
0x140053515  jnz     loc_1400535C1
0x14005351b  mov     rax, [rbx+288h]
0x140053522  mov     rdx, [rax+20h]
0x140053526  mov     rax, [rdx+30h]
0x14005352a  cmp     [rbx+50h], rax
0x14005352e  jnz     loc_14005387C
0x140053534  mov     rcx, rbx
0x140053537  call    RxCheckForNetworkOpenRestrictions
0x14005353c  mov     edi, eax
0x14005353e  test    eax, eax
0x140053540  js      short loc_1400535C1
0x140053542  lea     r8, [rsp+0A8h+var_48]; PIRP
0x140053547  mov     rdx, r15; Irp
0x14005354a  mov     rcx, rbx; RxContext
0x14005354d  call    RxCreateFromNetRoot
0x140053552  mov     rcx, rbx
0x140053555  mov     edi, eax
0x140053557  call    RxUpdateNetworkOpenLocationInformation
0x14005355c  cmp     edi, 104h
0x140053562  jnz     loc_14007C36F
0x140053568  bt      word ptr [rbx+2EAh], 0Eh
0x140053571  mov     rcx, [rbx+28h]
0x140053575  jb      loc_140053845
0x14005357b  mov     qword ptr [rcx+38h], 0
0x140053583  mov     rcx, cs:WPP_GLOBAL_Control
0x14005358a  cmp     rcx, r12
0x14005358d  jz      short loc_1400535C1
0x14005358f  mov     eax, [rcx+2Ch]
0x140053592  test    al, 8
0x140053594  jz      short loc_1400535C1
0x140053596  cmp     byte ptr [rcx+29h], 4
0x14005359a  jb      short loc_1400535C1
0x14005359c  mov     edx, 46h ; 'F'
0x1400535a1  mov     rcx, [rcx+18h]
0x1400535a5  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x1400535ac  mov     dword ptr [rsp+0A8h+var_80], 104h
0x1400535b4  mov     r9, r15
0x1400535b7  mov     [rsp+0A8h+var_88], r14
0x1400535bc  call    WPP_SF_qZD
0x1400535c1  cmp     cs:byte_14003314D, 0
0x1400535c8  mov     r13, [rsp+0A8h+arg_10]
0x1400535d0  jnz     loc_14007C4DD
0x1400535d6  cmp     edi, 0C0410001h
0x1400535dc  jz      loc_14005388E
0x1400535e2  mov     eax, edi
0x1400535e4  mov     rdi, [rsp+0A8h+arg_0]
0x1400535ec  mov     r12, [rsp+0A8h+arg_8]
0x1400535f4  add     rsp, 80h
0x1400535fb  pop     r15
0x1400535fd  pop     r14
0x1400535ff  pop     rsi
0x140053600  pop     rbp
0x140053601  pop     rbx
0x140053602  retn
0x140053604  mov     rax, [rcx+2A0h]
0x14005360b  test    rax, rax
0x14005360e  jz      loc_14005343C
0x140053614  mov     dl, 4
0x140053616  mov     rcx, rbx
0x140053619  call    _guard_dispatch_icall
0x14005361e  jmp     loc_14005343C
0x140053623  cmp     qword ptr [rsi+40h], 0
0x140053628  jnz     loc_140053453
0x14005362e  mov     qword ptr [rsi+20h], 0
0x140053636  lea     rax, RxDeviceFCB
0x14005363d  mov     [rsi+18h], rax
0x140053641  inc     dword ptr cs:RxDeviceFCB.ScavengerFinalizationList.Flink
0x140053647  inc     dword ptr cs:RxDeviceFCB.NonPaged
0x14005364d  mov     qword ptr [r15+38h], 1
0x140053655  mov     rcx, cs:WPP_GLOBAL_Control
0x14005365c  lea     r12, WPP_GLOBAL_Control
0x140053663  cmp     rcx, r12
0x140053666  jnz     loc_140053736
0x14005366c  xor     eax, eax
0x14005366e  jmp     loc_1400535EC
0x140053673  mov     rcx, cs:WPP_GLOBAL_Control
0x14005367a  cmp     rcx, r12
0x14005367d  jz      loc_140053486
0x140053683  mov     eax, [rcx+2Ch]
0x140053686  mov     rdi, [r9+18h]
0x14005368a  test    al, 8
0x14005368c  jnz     loc_140053768
0x140053692  mov     rcx, cs:WPP_GLOBAL_Control
0x140053699  cmp     rcx, r12
0x14005369c  jz      loc_140053486
0x1400536a2  mov     eax, [rcx+2Ch]
0x1400536a5  test    al, 8
0x1400536a7  jnz     loc_140053791
0x1400536ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400536b4  cmp     rcx, r12
0x1400536b7  jz      loc_140053486
0x1400536bd  mov     eax, [rcx+2Ch]
0x1400536c0  test    al, 8
0x1400536c2  jz      loc_140053486
0x1400536c8  cmp     byte ptr [rcx+29h], 2
0x1400536cc  jb      loc_140053486
0x1400536d2  mov     rcx, [rcx+18h]
0x1400536d6  lea     r9, [rdi+168h]
0x1400536dd  mov     edx, 41h ; 'A'
0x1400536e2  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x1400536e9  call    WPP_SF_Z
0x1400536ee  jmp     loc_140053486
0x1400536f3  mov     eax, [rbp+10h]
0x1400536f6  test    al, 40h
0x1400536f8  jnz     loc_140053805
0x1400536fe  sub     dx, 2
0x140053702  mov     [r14], dx
0x140053706  or      word ptr [rbx+2EAh], 2
0x14005370e  jmp     loc_1400534FB
0x140053713  mov     rdx, r15; Irp
0x140053716  mov     rcx, rbx; RxContext
0x140053719  call    RxCreateTreeConnect
0x14005371e  mov     edi, eax
0x140053720  jmp     loc_1400535D6
0x140053725  cmp     edi, 0C0000016h
0x14005372b  jz      loc_1400534DD
0x140053731  jmp     loc_1400535C1
0x140053736  mov     eax, [rcx+2Ch]
0x140053739  test    al, 8
0x14005373b  jz      loc_14005366C
0x140053741  cmp     byte ptr [rcx+29h], 4
0x140053745  jb      loc_14005366C
0x14005374b  mov     rcx, [rcx+18h]
0x14005374f  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x140053756  mov     edx, 3Dh ; '='
0x14005375b  mov     r9, rsi
0x14005375e  call    WPP_SF_q
0x140053763  jmp     loc_14005366C
0x140053768  cmp     byte ptr [rcx+29h], 2
0x14005376c  jb      loc_140053692
0x140053772  mov     rcx, [rcx+18h]
0x140053776  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x14005377d  mov     edx, 3Fh ; '?'
0x140053782  mov     [rsp+0A8h+var_88], rdi
0x140053787  call    WPP_SF_qq
0x14005378c  jmp     loc_140053692
0x140053791  cmp     byte ptr [rcx+29h], 2
0x140053795  jb      loc_1400536AD
0x14005379b  mov     rcx, [rcx+18h]
0x14005379f  lea     r9, [rdi+150h]
0x1400537a6  mov     edx, 40h ; '@'
0x1400537ab  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x1400537b2  call    WPP_SF_Z
0x1400537b7  jmp     loc_1400536AD
0x1400537bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400537c3  cmp     rcx, r12
0x1400537c6  jz      loc_140053490
0x1400537cc  mov     eax, [rcx+2Ch]
0x1400537cf  test    al, 8
0x1400537d1  jz      loc_140053490
0x1400537d7  cmp     byte ptr [rcx+29h], 2
0x1400537db  jb      loc_140053490
0x1400537e1  mov     rcx, [rcx+18h]
0x1400537e5  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x1400537ec  mov     edx, 42h ; 'B'
0x1400537f1  call    WPP_SF_
0x1400537f6  jmp     loc_140053490
0x1400537fb  mov     eax, 0C00000BBh
0x140053800  jmp     loc_1400535E4
0x140053805  mov     rcx, cs:WPP_GLOBAL_Control
0x14005380c  cmp     rcx, r12
0x14005380f  jz      loc_14007C4D3
0x140053815  mov     eax, [rcx+2Ch]
0x140053818  test    al, 8
0x14005381a  jz      loc_14007C4D3
0x140053820  cmp     byte ptr [rcx+29h], 4
0x140053824  jb      loc_14007C4D3
0x14005382a  mov     rcx, [rcx+18h]
0x14005382e  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x140053835  mov     edx, 44h ; 'D'
0x14005383a  call    WPP_SF_
0x14005383f  nop
0x140053840  jmp     loc_14007C4D3
0x140053845  mov     qword ptr [rcx+38h], 1
0x14005384d  mov     rcx, cs:WPP_GLOBAL_Control
0x140053854  cmp     rcx, r12
0x140053857  jz      loc_1400535C1
0x14005385d  mov     eax, [rcx+2Ch]
0x140053860  test    al, 8
0x140053862  jz      loc_1400535C1
0x140053868  cmp     byte ptr [rcx+29h], 4
0x14005386c  jb      loc_1400535C1
0x140053872  mov     edx, 45h ; 'E'
0x140053877  jmp     loc_1400535A1
0x14005387c  mov     qword ptr [r15+38h], 1
0x140053884  mov     edi, 104h
0x140053889  jmp     loc_1400535C1
0x14005388e  mov     rcx, rbx; RxContext
0x140053891  call    RxpPrepareCreateContextForReuse
0x140053896  jmp     loc_1400535E2
0x14007c2a4  cmp     byte ptr [rcx+29h], 2
0x14007c2a8  jb      loc_140053471
0x14007c2ae  movzx   r9d, byte ptr [rbp+2]
0x14007c2b3  mov     rax, [rbp+8]
0x14007c2b7  movzx   edx, word ptr [rbp+1Ah]
0x14007c2bb  movzx   r8d, word ptr [rbp+18h]
0x14007c2c0  mov     rcx, [rcx+18h]
0x14007c2c4  mov     eax, [rax+10h]
0x14007c2c7  mov     [rsp+0A8h+var_58], r14
0x14007c2cc  mov     [rsp+0A8h+var_60], eax
0x14007c2d0  mov     eax, [rbp+10h]
0x14007c2d3  mov     [rsp+0A8h+var_68], edx
0x14007c2d7  mov     dword ptr [rsp+0A8h+var_70], r8d
0x14007c2dc  mov     dword ptr [rsp+0A8h+var_78], r9d
0x14007c2e1  mov     r9, rbx
0x14007c2e4  mov     dword ptr [rsp+0A8h+var_80], eax
0x14007c2e8  mov     [rsp+0A8h+var_88], rsi
0x14007c2ed  call    WPP_SF_qqLLLLLZ
0x14007c2f2  nop
0x14007c2f3  jmp     loc_140053471
0x14007c2f8  cmp     word ptr [rcx], 5Ch ; '\'
0x14007c2fc  jnz     loc_1400534D5
0x14007c302  sub     ax, 2
0x14007c306  movzx   r8d, ax; Size
0x14007c30a  mov     [r14], r8w
0x14007c30e  call    memmove
0x14007c313  cmp     word ptr [r14], 2
0x14007c318  jbe     loc_1400534D5
0x14007c31e  mov     rax, [rsi+60h]
0x14007c322  cmp     word ptr [rax+2], 5Ch ; '\'
0x14007c327  jnz     loc_1400534D5
0x14007c32d  cmp     word ptr [rax], 5Ch ; '\'
0x14007c331  jnz     loc_1400534D5
0x14007c337  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c33e  cmp     rcx, r12
0x14007c341  jz      short loc_14007C365
0x14007c343  mov     eax, [rcx+2Ch]
0x14007c346  test    al, 8
0x14007c348  jz      short loc_14007C365
0x14007c34a  cmp     byte ptr [rcx+29h], 4
0x14007c34e  jb      short loc_14007C365
0x14007c350  mov     rcx, [rcx+18h]
0x14007c354  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x14007c35b  mov     edx, 43h ; 'C'
0x14007c360  call    WPP_SF_
  ... truncated ...
```
