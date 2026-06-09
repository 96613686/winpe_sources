# __RxAcquireFcb

- ea: `0x140057660`
- end: `0x140057a72`
- name: `__RxAcquireFcb`
- size: `1042`
- prototype: `NTSTATUS __stdcall(PFCB Fcb, PRX_CONTEXT RxContext, ULONG Mode, ULONG LineNumber, PCSTR FileName, ULONG SerialNumber)`
- caller_count: `50`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001b70`
- `0x140004ac0`
- `0x140008220`
- `0x140008910`
- `0x140008f60`
- `0x14000d7c0`
- `0x14000e400`
- `0x14000fcf0`
- `0x1400146a0`
- `0x140019aac`
- `0x14001a14c`
- `0x14001a834`
- `0x14001aa54`
- `0x14001abb8`
- `0x140024cf0`
- `0x140045030`
- `0x140045410`
- `0x1400466c0`
- `0x14004698c`
- `0x140046c48`
- `0x140047970`
- `0x14004a710`
- `0x14004aeb4`
- `0x14004b370`
- `0x14004d330`
- `0x14004dd60`
- `0x14004def0`
- `0x14004eb28`
- `0x140050910`
- `0x140053400`
- `0x1400538b0`
- `0x140054ca0`
- `0x140055950`
- `0x140056510`
- `0x140058540`
- `0x14005e2b0`
- `0x14005e810`
- `0x1400649a0`
- `0x140066390`
- `0x140068570`
- `0x140068e90`
- `0x14006a520`
- `0x14006c5c0`
- `0x14006f9e0`
- `0x140070f80`
- `0x1400737a0`
- `0x140074310`
- `0x140074600`
- `0x140077390`
- `0x140078050`

## callees

- `0x14000bbf0`
- `0x14000d630`
- `0x140012320`
- `0x140016e20`
- `0x140016ec0`
- `0x140017040`
- `0x140017280`
- `0x14001e3b0`
- `0x14001e608`
- `0x140057660`
- `0x140065690`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140057744`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140057744`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007adf3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14007adf3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005782b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14005782b`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14007cba4`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x14007cba4`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14007caee`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14007caee`
- `ntoskrnl!ExGetExclusiveWaiterCount` at `0x14007cb43`
- `ntoskrnl!ExGetExclusiveWaiterCount` at `0x14007cb43`
- `ntoskrnl!ExAcquireSharedWaitForExclusive` at `0x14005796c`
- `ntoskrnl!ExAcquireSharedWaitForExclusive` at `0x14005796c`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14007cb80`
- `ntoskrnl!ExAcquireSharedStarveExclusive` at `0x14007cb80`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
NTSTATUS __stdcall _RxAcquireFcb(
        PFCB Fcb,
        PRX_CONTEXT RxContext,
        ULONG Mode,
        ULONG LineNumber,
        PCSTR FileName,
        ULONG SerialNumber)
{
  char v6; // di
  PFCB v8; // r15
  unsigned int v9; // esi
  char v10; // r13
  bool v11; // r14
  BOOLEAN v12; // di
  USHORT *v13; // r12
  BOOLEAN v14; // r14
  PIRP CurrentIrp; // rdx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  PFILE_OBJECT FileObject; // r8
  PMRX_FOBX pFobx; // rcx
  _DWORD *Context2; // rcx
  UCHAR MajorFunction; // cl
  struct _FILE_OBJECT *RelatedFileObject; // rax
  ULONG v23; // r12d
  __int64 v24; // [rsp+20h] [rbp-68h]
  ULONG v25; // [rsp+40h] [rbp-48h]
  unsigned __int8 v26; // [rsp+98h] [rbp+10h]
  ULONG v27; // [rsp+A0h] [rbp+18h]

  v27 = Mode;
  v6 = LineNumber;
  v8 = Fcb;
  v9 = 0;
  v25 = 0;
  v10 = 0;
  v26 = 0;
  v11 = (unsigned __int64)RxContext > 0xFFFFFFFFFFFFFFFDuLL;
  if ( LODWORD(Fcb->RxDeviceObject->DeviceLock.Header.WaitListHead.Blink) )
  {
    if ( ExIsResourceAcquiredSharedLite(Fcb->Header.Resource)
      || v11
      || !(unsigned __int8)RxIsSafeToProcessBufferingStateChange(RxContext, v8) )
    {
      goto LABEL_76;
    }
    v26 = 1;
    v23 = v27;
    v25 = v27;
    *(_QWORD *)&Mode = 1;
    v27 = 1;
    if ( v25 == 1 )
      goto LABEL_2;
    if ( !ExGetExclusiveWaiterCount(v8->Header.Resource) )
    {
LABEL_76:
      *(_QWORD *)&Mode = v27;
    }
    else
    {
      *(_QWORD *)&Mode = v23;
      v27 = v23;
      v26 = 0;
    }
  }
LABEL_2:
  if ( v11 )
  {
    v12 = &RxContext->NodeByteSize == 0;
  }
  else if ( RxContext )
  {
    v10 = 1;
    v12 = ((__int64)RxContext->RdbssDbgExtension & 2) != 0;
    _m_prefetchw(&RxContext->ScavengerEntry);
    Fcb = (PFCB)LODWORD(RxContext->ScavengerEntry.List.Flink);
    if ( (_InterlockedXor((volatile signed __int32 *)&RxContext->ScavengerEntry, 0) & 2) != 0 )
      v9 = -1073741536;
  }
  else
  {
    v12 = v6 == 0;
  }
  if ( !v9 )
  {
    v13 = 0;
    if ( RxContext && !v11 )
      v13 = &RxContext->LowIoContext.Flags + 1;
    v9 = -1073741739;
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
    {
      HIDWORD(v24) = HIDWORD(v8);
      McTemplateK0ppq_EtwWriteTransfer(Fcb, RxFcbResourceRequest, v13, RxContext);
      *(_QWORD *)&Mode = v27;
    }
    switch ( Mode )
    {
      case 1u:
        RxPurgeTurboIoCache(v8, 1);
        v14 = ExAcquireResourceExclusiveLite(v8->Header.Resource, v12);
        HIDWORD(v8->FcbTableEntry.HashLinks.Blink) = MEMORY[0xFFFFF78000000008] / 0x2710uLL;
        RxUnsuspendTurboIo(v8);
        break;
      case 2u:
        v14 = ExAcquireResourceSharedLite(v8->Header.Resource, v12);
        break;
      case 3u:
        v14 = ExAcquireSharedWaitForExclusive(v8->Header.Resource, v12);
        break;
      case 4u:
        v14 = ExAcquireSharedStarveExclusive(v8->Header.Resource, v12);
        break;
      default:
        v14 = 0;
        break;
    }
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
      McTemplateK0pp_EtwWriteTransfer(Fcb, RxFcbResourceCompletion, v13, RxContext, v8);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      LODWORD(v24) = v27;
      WPP_SF_dddd(WPP_GLOBAL_Control->AttachedDevice, v14, *(_QWORD *)&Mode, v12, v24, v14, v26);
    }
    if ( v14 )
    {
      v9 = 0;
      if ( v26 )
      {
        if ( LODWORD(v8->RxDeviceObject->DeviceLock.Header.WaitListHead.Blink) )
          RxProcessFcbChangeBufferingStateRequestInternal(v8);
        if ( v25 != 1 )
          ExConvertExclusiveToSharedLite(v8->Header.Resource);
      }
      if ( v10 )
      {
        if ( ((__int64)RxContext->RdbssDbgExtension & 0x400000) == 0 )
        {
          CurrentIrp = RxContext->CurrentIrp;
          if ( CurrentIrp )
          {
            CurrentStackLocation = CurrentIrp->Tail.Overlay.CurrentStackLocation;
            FileObject = CurrentStackLocation->FileObject;
            if ( FileObject )
            {
              pFobx = RxContext->pFobx;
              if ( pFobx )
              {
                Context2 = pFobx->Context2;
                if ( Context2 )
                {
                  if ( ((LOBYTE(RxContext->RealDevice) - 2) & 0xEF) != 0 && (Context2[18] & 0x10) != 0 )
                    RxRaiseStatus(RxContext, 3221225685LL);
                  if ( ((LOBYTE(RxContext->RealDevice) - 2) & 0xEF) != 0 && (Context2[18] & 0x20) != 0 )
                    RxRaiseStatus(RxContext, 3221225763LL);
                }
              }
              if ( !LOBYTE(RxContext->RealDevice) )
              {
                RelatedFileObject = FileObject->RelatedFileObject;
                if ( RelatedFileObject )
                {
                  if ( (*((_DWORD *)RelatedFileObject->FsContext + 39) & 1) != 0 )
                    RxRaiseStatus(RxContext, 3221225558LL);
                }
              }
              if ( (FileObject->Flags & 0x4000) != 0 && (CurrentIrp->Flags & 2) == 0 )
              {
                MajorFunction = CurrentStackLocation->MajorFunction;
                if ( (((CurrentStackLocation->MajorFunction - 2) & 0xEB) != 0 || MajorFunction == 22)
                  && (MajorFunction != 13 || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1311632)
                  && MajorFunction != 5
                  && MajorFunction != 20
                  && ((unsigned __int8)(MajorFunction - 3) > 1u || (CurrentStackLocation->MinorFunction & 4) == 0) )
                {
                  RxRaiseStatus(RxContext, 3221225768LL);
                }
              }
            }
          }
        }
      }
    }
  }
  if ( RxContext && v10 && !v9 )
    LOBYTE(RxContext->Flags) = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x140057660  mov     [rsp+arg_10], r8d
0x140057665  mov     [rsp+arg_0], rcx
0x14005766a  push    rbx
0x14005766b  push    rsi
0x14005766c  push    rdi
0x14005766d  push    r12
0x14005766f  push    r13
0x140057671  push    r14
0x140057673  push    r15
0x140057675  sub     rsp, 50h
0x140057679  movzx   edi, r9b
0x14005767d  mov     rbx, rdx
0x140057680  mov     r15, rcx
0x140057683  xor     esi, esi
0x140057685  xor     r12d, r12d
0x140057688  mov     [rsp+88h+var_48], r12d
0x14005768d  xor     r13b, r13b
0x140057690  mov     [rsp+88h+arg_8], sil
0x140057698  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x14005769c  jbe     loc_140057957
0x1400576a2  mov     r14b, 1
0x1400576a5  mov     rax, [rcx+130h]
0x1400576ac  cmp     [rax+128h], esi
0x1400576b2  jnz     loc_14007CAEA
0x1400576b8  test    r14b, r14b
0x1400576bb  jnz     loc_14005794A
0x1400576c1  test    rbx, rbx
0x1400576c4  jz      loc_14005793E
0x1400576ca  mov     r13b, 1
0x1400576cd  mov     edi, [rbx+78h]
0x1400576d0  shr     edi, 1
0x1400576d2  and     dil, r13b
0x1400576d5  prefetchw byte ptr [rbx+80h]
0x1400576dc  mov     eax, [rbx+80h]
0x1400576e2  mov     ecx, eax
0x1400576e4  xor     ecx, esi
0x1400576e6  lock cmpxchg [rbx+80h], ecx
0x1400576ee  jnz     short loc_1400576E2
0x1400576f0  test    al, 2
0x1400576f2  jnz     loc_1400579D2
0x1400576f8  test    esi, esi
0x1400576fa  jnz     loc_140057981
0x140057700  xor     r12d, r12d
0x140057703  test    rbx, rbx
0x140057706  jz      short loc_140057714
0x140057708  test    r14b, r14b
0x14005770b  jnz     short loc_140057714
0x14005770d  lea     r12, [rbx+19Ch]
0x140057714  mov     esi, 0C0000055h
0x140057719  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x140057720  jnz     loc_14005798D
0x140057726  cmp     r8d, 1
0x14005772a  jnz     loc_140057817
0x140057730  movzx   edx, r8b
0x140057734  mov     rcx, r15
0x140057737  call    RxPurgeTurboIoCache
0x14005773c  movzx   edx, dil; Wait
0x140057740  mov     rcx, [r15+8]; Resource
0x140057744  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14005774b  nop     dword ptr [rax+rax+00h]
0x140057750  movzx   r14d, al
0x140057754  mov     rcx, 0FFFFF78000000008h
0x14005775e  mov     rcx, [rcx]
0x140057761  mov     rax, 346DC5D63886594Bh
0x14005776b  mul     rcx
0x14005776e  shr     rdx, 0Bh
0x140057772  mov     [r15+104h], edx
0x140057779  mov     rcx, r15
0x14005777c  call    RxUnsuspendTurboIo
0x140057781  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x140057788  jnz     loc_1400579B6
0x14005778e  lea     r12, WPP_GLOBAL_Control
0x140057795  mov     rcx, cs:WPP_GLOBAL_Control
0x14005779c  cmp     rcx, r12
0x14005779f  jz      short loc_1400577AE
0x1400577a1  test    dword ptr [rcx+2Ch], 100h
0x1400577a8  jnz     loc_1400579ED
0x1400577ae  test    r14b, r14b
0x1400577b1  jz      short loc_1400577D6
0x1400577b3  xor     esi, esi
0x1400577b5  cmp     [rsp+88h+arg_8], sil
0x1400577bd  jnz     loc_140057A28
0x1400577c3  test    r14b, r14b
0x1400577c6  jz      short loc_1400577D6
0x1400577c8  test    r13b, r13b
0x1400577cb  jz      short loc_1400577D6
0x1400577cd  test    dword ptr [rbx+78h], 400000h
0x1400577d4  jz      short loc_140057840
0x1400577d6  test    rbx, rbx
0x1400577d9  jz      short loc_1400577EB
0x1400577db  test    r13b, r13b
0x1400577de  jz      short loc_1400577EB
0x1400577e0  test    esi, esi
0x1400577e2  jnz     short loc_1400577EB
0x1400577e4  mov     byte ptr [rbx+0A8h], 1
0x1400577eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400577f2  cmp     rcx, r12
0x1400577f5  jz      short loc_140057804
0x1400577f7  test    dword ptr [rcx+2Ch], 100h
0x1400577fe  jnz     loc_140057A4B
0x140057804  mov     eax, esi
0x140057806  add     rsp, 50h
0x14005780a  pop     r15
0x14005780c  pop     r14
0x14005780e  pop     r13
0x140057810  pop     r12
0x140057812  pop     rdi
0x140057813  pop     rsi
0x140057814  pop     rbx
0x140057815  retn
0x140057817  mov     eax, r8d
0x14005781a  sub     eax, 2
0x14005781d  jnz     loc_14005795F
0x140057823  movzx   edx, dil; Wait
0x140057827  mov     rcx, [r15+8]; Resource
0x14005782b  call    cs:__imp_ExAcquireResourceSharedLite
0x140057832  nop     dword ptr [rax+rax+00h]
0x140057837  movzx   r14d, al
0x14005783b  jmp     loc_140057781
0x140057840  mov     rdx, [rbx+28h]
0x140057844  test    rdx, rdx
0x140057847  jz      loc_140057939
0x14005784d  mov     r9, [rdx+0B8h]
0x140057854  mov     r8, [r9+30h]
0x140057858  test    r8, r8
0x14005785b  jz      loc_140057939
0x140057861  mov     rcx, [rbx+40h]
0x140057865  test    rcx, rcx
0x140057868  jz      short loc_1400578B6
0x14005786a  mov     rcx, [rcx+20h]
0x14005786e  test    rcx, rcx
0x140057871  jz      short loc_1400578B6
0x140057873  movzx   eax, byte ptr [rbx+20h]
0x140057877  sub     al, 2
0x140057879  test    al, 0EFh
0x14005787b  jz      short loc_140057892
0x14005787d  mov     eax, [rcx+48h]
0x140057880  test    al, 10h
0x140057882  jz      short loc_140057892
0x140057884  mov     edx, 0C00000D5h
0x140057889  mov     rcx, rbx
0x14005788c  call    RxRaiseStatus
0x140057892  test    rcx, rcx
0x140057895  jz      short loc_1400578B6
0x140057897  movzx   eax, byte ptr [rbx+20h]
0x14005789b  sub     al, 2
0x14005789d  test    al, 0EFh
0x14005789f  jz      short loc_1400578B6
0x1400578a1  mov     eax, [rcx+48h]
0x1400578a4  test    al, 20h
0x1400578a6  jz      short loc_1400578B6
0x1400578a8  mov     edx, 0C0000123h
0x1400578ad  mov     rcx, rbx
0x1400578b0  call    RxRaiseStatus
0x1400578b6  cmp     byte ptr [rbx+20h], 0
0x1400578ba  jz      short loc_140057913
0x1400578bc  test    dword ptr [r8+50h], 4000h
0x1400578c4  jz      short loc_140057939
0x1400578c6  mov     eax, [rdx+10h]
0x1400578c9  test    al, 2
0x1400578cb  jnz     short loc_140057939
0x1400578cd  movzx   ecx, byte ptr [r9]
0x1400578d1  lea     eax, [rcx-2]
0x1400578d4  test    al, 0EBh
0x1400578d6  jnz     short loc_1400578DD
0x1400578d8  cmp     cl, 16h
0x1400578db  jnz     short loc_140057939
0x1400578dd  cmp     cl, 0Dh
0x1400578e0  jnz     short loc_1400578EC
0x1400578e2  cmp     dword ptr [r9+18h], 140390h
0x1400578ea  jz      short loc_140057939
0x1400578ec  cmp     cl, 5
0x1400578ef  jz      short loc_140057939
0x1400578f1  cmp     cl, 14h
0x1400578f4  jz      short loc_140057939
0x1400578f6  sub     cl, 3
0x1400578f9  cmp     cl, 1
0x1400578fc  ja      short loc_140057905
0x1400578fe  test    byte ptr [r9+1], 4
0x140057903  jnz     short loc_140057939
0x140057905  mov     edx, 0C0000128h
0x14005790a  mov     rcx, rbx
0x14005790d  call    RxRaiseStatus
0x140057913  mov     rax, [r8+40h]
0x140057917  test    rax, rax
0x14005791a  jz      short loc_1400578BC
0x14005791c  mov     rax, [rax+18h]
0x140057920  mov     ecx, [rax+9Ch]
0x140057926  test    cl, 1
0x140057929  jz      short loc_1400578BC
0x14005792b  mov     edx, 0C0000056h
0x140057930  mov     rcx, rbx
0x140057933  call    RxRaiseStatus
0x140057939  jmp     loc_1400577D6
0x14005793e  test    dil, dil
0x140057941  setz    dil
0x140057945  jmp     loc_1400576F8
0x14005794a  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x14005794e  setz    dil
0x140057952  jmp     loc_1400576F8
0x140057957  xor     r14b, r14b
0x14005795a  jmp     loc_1400576A5
0x14005795f  sub     eax, 1
0x140057962  jnz     short loc_1400579DC
0x140057964  movzx   edx, dil; Wait
0x140057968  mov     rcx, [r15+8]; Resource
0x14005796c  call    cs:__imp_ExAcquireSharedWaitForExclusive
0x140057973  nop     dword ptr [rax+rax+00h]
0x140057978  movzx   r14d, al
0x14005797c  jmp     loc_140057781
0x140057981  lea     r12, WPP_GLOBAL_Control
0x140057988  jmp     loc_1400577D6
0x14005798d  mov     [rsp+88h+var_60], r8d
0x140057992  mov     [rsp+88h+var_68], r15
0x140057997  mov     r9, rbx
0x14005799a  mov     r8, r12
0x14005799d  lea     rdx, RxFcbResourceRequest
0x1400579a4  call    McTemplateK0ppq_EtwWriteTransfer
0x1400579a9  mov     r8d, [rsp+88h+arg_10]
0x1400579b1  jmp     loc_140057726
0x1400579b6  mov     [rsp+88h+var_68], r15
0x1400579bb  mov     r9, rbx
0x1400579be  mov     r8, r12
0x1400579c1  lea     rdx, RxFcbResourceCompletion
0x1400579c8  call    McTemplateK0pp_EtwWriteTransfer
0x1400579cd  jmp     loc_14005778E
0x1400579d2  mov     esi, 0C0000120h
0x1400579d7  jmp     loc_1400576F8
0x1400579dc  cmp     eax, 1
0x1400579df  jz      loc_14007CB78
0x1400579e5  xor     r14b, r14b
0x1400579e8  jmp     loc_140057781
0x1400579ed  cmp     byte ptr [rcx+29h], 4
0x1400579f1  jb      loc_1400577AE
0x1400579f7  movzx   eax, [rsp+88h+arg_8]
0x1400579ff  movzx   edx, r14b
0x140057a03  movzx   r9d, dil
0x140057a07  mov     [rsp+88h+var_58], eax
0x140057a0b  mov     [rsp+88h+var_60], edx
0x140057a0f  mov     eax, [rsp+88h+arg_10]
0x140057a16  mov     dword ptr [rsp+88h+var_68], eax
0x140057a1a  mov     rcx, [rcx+18h]
0x140057a1e  call    WPP_SF_dddd
0x140057a23  jmp     loc_1400577AE
0x140057a28  mov     rax, [r15+130h]
0x140057a2f  cmp     [rax+128h], esi
0x140057a35  jz      loc_14007CB95
0x140057a3b  xor     edx, edx
0x140057a3d  mov     rcx, r15; Instance
0x140057a40  call    RxProcessFcbChangeBufferingStateRequestInternal
0x140057a45  nop
0x140057a46  jmp     loc_14007CB95
0x140057a4b  cmp     byte ptr [rcx+29h], 4
0x140057a4f  jb      loc_140057804
0x140057a55  mov     edx, 0Ch
0x140057a5a  mov     r9d, esi
0x140057a5d  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140057a64  mov     rcx, [rcx+18h]
0x140057a68  call    WPP_SF_d
0x140057a6d  jmp     loc_140057804
0x14007ada0  push    rbp
0x14007ada2  sub     rsp, 40h
0x14007ada6  mov     rbp, rdx
0x14007ada9  movzx   eax, cl
0x14007adac  test    cl, cl
0x14007adae  jz      short loc_14007AE00
0x14007adb0  lea     rax, WPP_GLOBAL_Control
0x14007adb7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007adbe  cmp     rcx, rax
0x14007adc1  jz      short loc_14007ADE8
0x14007adc3  mov     eax, [rcx+2Ch]
0x14007adc6  bt      eax, 8
0x14007adca  jnb     short loc_14007ADE8
0x14007adcc  cmp     byte ptr [rcx+29h], 2
0x14007add0  jb      short loc_14007ADE8
0x14007add2  mov     edx, 0Bh
0x14007add7  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x14007adde  mov     rcx, [rcx+18h]
0x14007ade2  call    WPP_SF_
0x14007ade7  nop
0x14007ade8  mov     rcx, [rbp+90h]
0x14007adef  mov     rcx, [rcx+8]; Resource
0x14007adf3  call    cs:__imp_ExReleaseResourceLite
0x14007adfa  nop     dword ptr [rax+rax+00h]
0x14007adff  nop
0x14007ae00  add     rsp, 40h
0x14007ae04  pop     rbp
0x14007ae05  retn
0x14007caea  mov     rcx, [rcx+8]; Resource
0x14007caee  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14007caf5  nop     dword ptr [rax+rax+00h]
0x14007cafa  test    eax, eax
0x14007cafc  jnz     short loc_14007CB6B
0x14007cafe  test    r14b, r14b
0x14007cb01  jnz     short loc_14007CB6B
0x14007cb03  mov     rdx, r15
0x14007cb06  mov     rcx, rbx
0x14007cb09  call    RxIsSafeToProcessBufferingStateChange
0x14007cb0e  test    al, al
0x14007cb10  jz      short loc_14007CB6B
  ... truncated ...
```
