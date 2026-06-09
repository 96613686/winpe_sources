# RxAttemptTurboIo

- ea: `0x140012880`
- end: `0x14001304c`
- name: `RxAttemptTurboIo`
- size: `1996`
- prototype: `__int64 __fastcall(PIRP)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x1400037e0`
- `0x140012130`
- `0x140012880`
- `0x140016e70`
- `0x140017a8c`
- `0x140020038`
- `0x140020244`
- `0x140025d00`

## import_xrefs

- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x140012c1f`
- `ntoskrnl!FsRtlCheckLockForReadAccess` at `0x140012c1f`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x140012e48`
- `ntoskrnl!FsRtlCheckLockForWriteAccess` at `0x140012e48`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012998`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012b60`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012d37`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012de2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012998`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012b60`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012d37`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012de2`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400128a6`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1400128a6`
- `ntoskrnl!KeClearEvent` at `0x140012a15`
- `ntoskrnl!KeClearEvent` at `0x140012a15`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001296c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012d0f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001296c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012d0f`

## pseudocode

```c
__int64 __fastcall RxAttemptTurboIo(PIRP a1)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r14
  PFILE_OBJECT FileObject; // r15
  char *FsContext; // r13
  unsigned int v5; // ebx
  __int64 CurrentNodeNumber; // r12
  __int64 v7; // rsi
  UCHAR MajorFunction; // cl
  ULONG Flags; // eax
  KIRQL v10; // al
  _QWORD *v11; // rdx
  KIRQL v12; // r8
  volatile signed __int32 *v13; // r12
  PRX_CONTEXT v14; // r12
  __int64 v15; // rdx
  __int64 v16; // r8
  struct _LIST_ENTRY *v17; // rcx
  struct _LIST_ENTRY *Flink; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  volatile signed __int32 *v21; // r8
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *v23; // rax
  LONGLONG v24; // rdx
  __int64 v25; // rdx
  struct _LIST_ENTRY *v26; // rcx
  struct _LIST_ENTRY *v27; // rax
  KIRQL v28; // al
  _QWORD *v29; // rdx
  KIRQL v30; // r8
  volatile signed __int32 *v31; // r12
  __int64 v32; // rax
  LONGLONG v33; // rdx
  __int64 v34; // rdx
  struct _LIST_ENTRY *v35; // rcx
  struct _LIST_ENTRY *v36; // rax
  int v37; // r9d
  int v38; // r11d
  int v39; // r10d
  __int16 RealDevice_low; // [rsp+28h] [rbp-80h]
  PRX_CONTEXT RxContext; // [rsp+B0h] [rbp+8h]
  PKSPIN_LOCK SpinLock; // [rsp+B8h] [rbp+10h]
  PKSPIN_LOCK SpinLocka; // [rsp+B8h] [rbp+10h]

  CurrentStackLocation = a1->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  FsContext = (char *)FileObject->FsContext;
  v5 = -1069481982;
  CurrentNodeNumber = KeGetCurrentNodeNumber();
  v7 = *(_QWORD *)(*((_QWORD *)FsContext + 38) + 328LL);
  if ( !v7
    || !*(_BYTE *)(v7 + 24)
    || *(_DWORD *)(v7 + 28)
    || *(PFILE_OBJECT *)v7 != FileObject
    || (MajorFunction = CurrentStackLocation->MajorFunction,
        (unsigned __int8)(CurrentStackLocation->MajorFunction - 3) > 1u)
    || CurrentStackLocation->MinorFunction
    || (Flags = a1->Flags, (Flags & 1) == 0)
    || CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart <= 0
    || (Flags & 0x46) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return v5;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
      goto LABEL_89;
    v37 = 1;
    if ( v7 && *(PFILE_OBJECT *)v7 == FileObject )
    {
      v38 = 1;
    }
    else
    {
      v38 = 0;
      if ( !v7 )
        goto LABEL_85;
    }
    if ( *(_DWORD *)(v7 + 28) )
    {
      v39 = 1;
LABEL_86:
      if ( *(_BYTE *)(v7 + 24) )
      {
LABEL_88:
        WPP_SF_qddddddddd(
          WPP_GLOBAL_Control->AttachedDevice,
          v7 != 0,
          a1->Flags & 1,
          a1,
          a1->Flags & 1,
          CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart > 0,
          (a1->Flags & 0x46) == 0,
          v7 != 0,
          v37,
          v39,
          v38,
          (unsigned __int8)(CurrentStackLocation->MajorFunction - 3) <= 1u,
          CurrentStackLocation->MinorFunction == 0);
        goto LABEL_89;
      }
LABEL_87:
      v37 = 0;
      goto LABEL_88;
    }
LABEL_85:
    v39 = 0;
    if ( !v7 )
      goto LABEL_87;
    goto LABEL_86;
  }
  RxContext = 0;
  if ( MajorFunction == 3 )
  {
    v5 = LockBufferForTurboIo(a1, IoWriteAccess, CurrentStackLocation->Parameters.Read.Length);
    if ( (v5 & 0x80000000) != 0 )
      return v5;
    SpinLock = *(PKSPIN_LOCK *)(v7 + 8 * CurrentNodeNumber + 32);
    v10 = KeAcquireSpinLockRaiseToDpc(SpinLock);
    v11 = SpinLock + 2;
    v12 = v10;
    v13 = (volatile signed __int32 *)SpinLock[2];
    if ( v13 == (volatile signed __int32 *)(SpinLock + 2) )
    {
      KeReleaseSpinLock(SpinLock, v10);
LABEL_14:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_d414fc76462934e262300deaf9706329_Traceguids, a1);
      }
      v14 = RxContext;
      goto LABEL_19;
    }
    if ( *((_QWORD **)v13 + 1) == v11 )
    {
      v19 = *(_QWORD *)v13;
      if ( *(volatile signed __int32 **)(*(_QWORD *)v13 + 8LL) == v13 )
      {
        *v11 = v19;
        *(_QWORD *)(v19 + 8) = v11;
        *((_QWORD *)v13 + 1) = v13;
        *(_QWORD *)v13 = v13;
        --*((_DWORD *)SpinLock + 2);
        RxContext = (PRX_CONTEXT)(v13 - 92);
        _InterlockedIncrement(v13 - 91);
        *((_DWORD *)v13 - 62) &= 0xBEF7FFFF;
        KeReleaseSpinLock(SpinLock, v12);
        v21 = v13 - 92;
        if ( v13 != (volatile signed __int32 *)368 && !*(_QWORD *)&RxContext->TrackerHistory[9].AcquireRelease )
        {
          Blink = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
          if ( Blink )
          {
            v23 = Blink[41].Blink;
            if ( v23 )
            {
              LOBYTE(v20) = 36;
              ((void (__fastcall *)(PRX_CONTEXT, __int64))v23)(RxContext, v20);
              v21 = v13 - 92;
            }
          }
        }
        if ( !v13 )
          goto LABEL_14;
        if ( *(PFILE_OBJECT *)v7 == FileObject
          && (!FileObject->SectionObjectPointer->DataSectionObject || (FsContext[256] & 5) == 0) )
        {
          if ( *(_BYTE *)(v7 + 24) )
          {
            if ( !*(_DWORD *)(v7 + 28) )
            {
              v24 = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart
                  + CurrentStackLocation->Parameters.Read.Length;
              if ( v24 <= *((_QWORD *)FsContext + 4) && v24 <= *((_QWORD *)FsContext + 5) )
              {
                if ( FsRtlCheckLockForReadAccess((PFILE_LOCK)(FsContext + 536), a1) )
                {
                  v14 = (PRX_CONTEXT)(v13 - 92);
                  *((_QWORD *)&RxContext->9 + 18) = a1->MdlAddress;
                  RxContext->Create.TransportName.Buffer = (wchar_t *)CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
                  *((_DWORD *)&RxContext->9 + 42) = CurrentStackLocation->Parameters.Read.Length;
                  *((_DWORD *)&RxContext->9 + 43) = CurrentStackLocation->Parameters.Create.Options;
                  if ( !*(_QWORD *)&RxContext->TrackerHistory[9].AcquireRelease )
                  {
                    v26 = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
                    if ( v26 )
                    {
                      v27 = v26[41].Blink;
                      if ( v27 )
                      {
                        LOBYTE(v25) = 36;
                        ((void (__fastcall *)(PRX_CONTEXT, __int64))v27)(RxContext, v25);
                      }
                    }
                  }
                  goto LABEL_19;
                }
                v21 = v13 - 92;
              }
            }
          }
        }
        _InterlockedOr(v21 + 32, 2u);
        (**(void (__fastcall ***)(volatile signed __int32 *, _QWORD))(v7 + 16))(v21, 0);
        RxDereferenceAndDeleteRxContext_Real(RxContext);
        return v5;
      }
    }
LABEL_75:
    __fastfail(3u);
  }
  if ( MajorFunction != 4 )
    goto LABEL_89;
  v5 = LockBufferForTurboIo(a1, IoReadAccess, CurrentStackLocation->Parameters.Read.Length);
  if ( (v5 & 0x80000000) != 0 )
    return v5;
  SpinLocka = *(PKSPIN_LOCK *)(v7 + 8 * CurrentNodeNumber + 32);
  v28 = KeAcquireSpinLockRaiseToDpc(SpinLocka);
  v29 = SpinLocka + 4;
  v30 = v28;
  v31 = (volatile signed __int32 *)SpinLocka[4];
  if ( v31 == (volatile signed __int32 *)(SpinLocka + 4) )
  {
    KeReleaseSpinLock(SpinLocka, v28);
LABEL_56:
    v14 = RxContext;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_d414fc76462934e262300deaf9706329_Traceguids, a1);
    }
    goto LABEL_19;
  }
  if ( *((_QWORD **)v31 + 1) != v29 )
    goto LABEL_75;
  v32 = *(_QWORD *)v31;
  if ( *(volatile signed __int32 **)(*(_QWORD *)v31 + 8LL) != v31 )
    goto LABEL_75;
  *v29 = v32;
  *(_QWORD *)(v32 + 8) = v29;
  *((_QWORD *)v31 + 1) = v31;
  *(_QWORD *)v31 = v31;
  --*((_DWORD *)SpinLocka + 2);
  RxContext = (PRX_CONTEXT)(v31 - 92);
  _InterlockedIncrement(v31 - 91);
  *((_DWORD *)v31 - 62) &= 0xBEF7FFFF;
  KeReleaseSpinLock(SpinLocka, v30);
  if ( !v31 )
    goto LABEL_56;
  if ( *(PFILE_OBJECT *)v7 != FileObject
    || FileObject->SectionObjectPointer->DataSectionObject
    || !*(_BYTE *)(v7 + 24)
    || *(_DWORD *)(v7 + 28)
    || (v33 = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart + CurrentStackLocation->Parameters.Read.Length,
        v33 > *((_QWORD *)FsContext + 4))
    || v33 > *((_QWORD *)FsContext + 5)
    || !FsRtlCheckLockForWriteAccess((PFILE_LOCK)(FsContext + 536), a1) )
  {
    _InterlockedOr((volatile signed __int32 *)&RxContext->ScavengerEntry, 2u);
    (**(void (__fastcall ***)(PRX_CONTEXT, _QWORD))(v7 + 16))(RxContext, 0);
    RxDereferenceAndDeleteRxContext_Real(RxContext);
    return v5;
  }
  v14 = (PRX_CONTEXT)(v31 - 92);
  *((_QWORD *)&RxContext->9 + 18) = a1->MdlAddress;
  RxContext->Create.TransportName.Buffer = (wchar_t *)CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
  *((_DWORD *)&RxContext->9 + 42) = CurrentStackLocation->Parameters.Read.Length;
  *((_DWORD *)&RxContext->9 + 43) = CurrentStackLocation->Parameters.Create.Options;
  if ( !*(_QWORD *)&RxContext->TrackerHistory[9].AcquireRelease )
  {
    v35 = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
    if ( v35 )
    {
      v36 = v35[41].Blink;
      if ( v36 )
      {
        LOBYTE(v34) = 37;
        ((void (__fastcall *)(PRX_CONTEXT, __int64))v36)(RxContext, v34);
      }
    }
  }
LABEL_19:
  if ( v14 )
  {
    a1->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    v14->InformationToReturn = 0;
    v14->StoredStatus = 0;
    v14->Create.NtCreateParameters.AllocationSize.LowPart = 0;
    KeClearEvent((PRKEVENT)&v14->PrefixClaim.NetRootType);
    *(_QWORD *)&v14->MajorFunction = MEMORY[0xFFFFF78000000008];
    v14->OriginalThread = KeGetCurrentThread();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      RealDevice_low = LOBYTE(v14->RealDevice);
      WPP_SF_qqhqqqqL(
        WPP_GLOBAL_Control->AttachedDevice,
        LOBYTE(v14->RealDevice),
        v16,
        v14->NonPagedFcb,
        a1,
        RealDevice_low,
        v14,
        FileObject,
        v14->pFobx,
        v14->pFcb,
        v14->RdbssDbgExtension);
    }
    v17 = v14->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
    if ( v17 )
    {
      Flink = v17[42].Flink;
      if ( Flink )
      {
        LOBYTE(v15) = 38;
        ((void (__fastcall *)(PRX_CONTEXT, __int64))Flink)(v14, v15);
      }
    }
    v5 = (**(__int64 (__fastcall ***)(PRX_CONTEXT, PIRP))(v7 + 16))(v14, a1);
    if ( v5 != 259 )
    {
      CurrentStackLocation->Control &= ~1u;
      _InterlockedOr((volatile signed __int32 *)&v14->ScavengerEntry, 2u);
      (**(void (__fastcall ***)(PRX_CONTEXT, _QWORD))(v7 + 16))(v14, 0);
    }
    RxDereferenceAndDeleteRxContext_Real(v14);
    return v5;
  }
LABEL_89:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 27, &WPP_d414fc76462934e262300deaf9706329_Traceguids, a1);
  }
  return v5;
}

```

## disassembly

```asm
0x140012880  mov     [rsp+arg_10], rbx
0x140012885  push    rbp
0x140012886  push    rsi
0x140012887  push    rdi
0x140012888  push    r12
0x14001288a  push    r13
0x14001288c  push    r14
0x14001288e  push    r15
0x140012890  sub     rsp, 70h
0x140012894  mov     r14, [rcx+0B8h]
0x14001289b  mov     rbp, rcx
0x14001289e  mov     r15, [r14+30h]
0x1400128a2  mov     r13, [r15+18h]
0x1400128a6  call    cs:__imp_KeGetCurrentNodeNumber
0x1400128ad  nop     dword ptr [rax+rax+00h]
0x1400128b2  mov     rdx, [r13+130h]
0x1400128b9  mov     ebx, 0C0410002h
0x1400128be  movzx   r12d, ax
0x1400128c2  mov     rsi, [rdx+148h]
0x1400128c9  test    rsi, rsi
0x1400128cc  jz      loc_140012F08
0x1400128d2  cmp     byte ptr [rsi+18h], 0
0x1400128d6  jz      loc_140012F08
0x1400128dc  cmp     dword ptr [rsi+1Ch], 0
0x1400128e0  jnz     loc_140012F08
0x1400128e6  cmp     [rsi], r15
0x1400128e9  jnz     loc_140012F08
0x1400128ef  movzx   ecx, byte ptr [r14]
0x1400128f3  lea     eax, [rcx-3]
0x1400128f6  cmp     al, 1
0x1400128f8  ja      loc_140012F08
0x1400128fe  cmp     byte ptr [r14+1], 0
0x140012903  jnz     loc_140012F08
0x140012909  mov     eax, [rbp+10h]
0x14001290c  test    al, 1
0x14001290e  jz      loc_140012F08
0x140012914  cmp     qword ptr [r14+18h], 0
0x140012919  jle     loc_140012F08
0x14001291f  test    al, 46h
0x140012921  jnz     loc_140012F08
0x140012927  xor     edi, edi
0x140012929  mov     [rsp+0A8h+RxContext], rdi
0x140012931  lea     rdi, WPP_GLOBAL_Control
0x140012938  cmp     cl, 3
0x14001293b  jnz     loc_140012CDE
0x140012941  mov     r8d, [r14+8]; int
0x140012945  mov     edx, 1; Operation
0x14001294a  mov     rcx, rbp; PIRP
0x14001294d  call    LockBufferForTurboIo
0x140012952  mov     ebx, eax
0x140012954  test    eax, eax
0x140012956  js      loc_140013031
0x14001295c  mov     r12, [rsi+r12*8+20h]
0x140012961  mov     rcx, r12; SpinLock
0x140012964  mov     [rsp+0A8h+SpinLock], r12
0x14001296c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012973  nop     dword ptr [rax+rax+00h]
0x140012978  lea     rdx, [r12+10h]
0x14001297d  movzx   r8d, al
0x140012981  mov     r12, [rdx]
0x140012984  cmp     r12, rdx
0x140012987  jnz     loc_140012B0D
0x14001298d  mov     rcx, [rsp+0A8h+SpinLock]; SpinLock
0x140012995  movzx   edx, al; NewIrql
0x140012998  call    cs:__imp_KeReleaseSpinLock
0x14001299f  nop     dword ptr [rax+rax+00h]
0x1400129a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400129ab  cmp     rcx, rdi
0x1400129ae  jz      short loc_1400129D7
0x1400129b0  test    dword ptr [rcx+2Ch], 4000h
0x1400129b7  jz      short loc_1400129D7
0x1400129b9  cmp     byte ptr [rcx+29h], 1
0x1400129bd  jb      short loc_1400129D7
0x1400129bf  mov     rcx, [rcx+18h]
0x1400129c3  lea     r8, WPP_d414fc76462934e262300deaf9706329_Traceguids
0x1400129ca  mov     edx, 17h
0x1400129cf  mov     r9, rbp
0x1400129d2  call    WPP_SF_q
0x1400129d7  mov     r12, [rsp+0A8h+RxContext]
0x1400129df  test    r12, r12
0x1400129e2  jz      loc_140012FF5
0x1400129e8  mov     rax, [rbp+0B8h]
0x1400129ef  lea     rcx, [r12+180h]; Event
0x1400129f7  or      byte ptr [rax+3], 1
0x1400129fb  xor     eax, eax
0x1400129fd  mov     [r12+0B8h], rax
0x140012a05  mov     [r12+0B0h], eax
0x140012a0d  mov     [r12+198h], eax
0x140012a15  call    cs:__imp_KeClearEvent
0x140012a1c  nop     dword ptr [rax+rax+00h]
0x140012a21  mov     rax, ds:0FFFFF78000000008h
0x140012a2b  mov     [r12+18h], rax
0x140012a30  mov     rax, gs:188h
0x140012a39  mov     [r12+60h], rax
0x140012a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a45  cmp     rcx, rdi
0x140012a48  jz      short loc_140012A9E
0x140012a4a  test    dword ptr [rcx+2Ch], 4000h
0x140012a51  jz      short loc_140012A9E
0x140012a53  cmp     byte ptr [rcx+29h], 2
0x140012a57  jb      short loc_140012A9E
0x140012a59  mov     eax, [r12+78h]
0x140012a5e  movzx   edx, byte ptr [r12+20h]
0x140012a64  mov     r9, [r12+50h]
0x140012a69  mov     rcx, [rcx+18h]
0x140012a6d  mov     [rsp+0A8h+var_58], eax
0x140012a71  mov     rax, [r12+38h]
0x140012a76  mov     [rsp+0A8h+var_60], rax
0x140012a7b  mov     rax, [r12+40h]
0x140012a80  mov     [rsp+0A8h+var_68], rax
0x140012a85  mov     [rsp+0A8h+var_70], r15
0x140012a8a  mov     [rsp+0A8h+var_78], r12
0x140012a8f  mov     [rsp+0A8h+var_80], dx
0x140012a94  mov     [rsp+0A8h+var_88], rbp
0x140012a99  call    WPP_SF_qqhqqqqL
0x140012a9e  mov     rax, [r12+50h]
0x140012aa3  mov     rcx, [rax+160h]
0x140012aaa  test    rcx, rcx
0x140012aad  jz      short loc_140012AC5
0x140012aaf  mov     rax, [rcx+2A0h]
0x140012ab6  test    rax, rax
0x140012ab9  jz      short loc_140012AC5
0x140012abb  mov     dl, 26h ; '&'
0x140012abd  mov     rcx, r12
0x140012ac0  call    _guard_dispatch_icall
0x140012ac5  mov     rax, [rsi+10h]
0x140012ac9  mov     rdx, rbp
0x140012acc  mov     rcx, r12
0x140012acf  mov     rax, [rax]
0x140012ad2  call    _guard_dispatch_icall
0x140012ad7  mov     ebx, eax
0x140012ad9  cmp     eax, 103h
0x140012ade  jz      short loc_140012B00
0x140012ae0  and     byte ptr [r14+3], 0FEh
0x140012ae5  lock or dword ptr [r12+80h], 2
0x140012aef  mov     rax, [rsi+10h]
0x140012af3  xor     edx, edx
0x140012af5  mov     rcx, r12
0x140012af8  mov     rax, [rax]
0x140012afb  call    _guard_dispatch_icall
0x140012b00  mov     rcx, r12; RxContext
0x140012b03  call    RxDereferenceAndDeleteRxContext_Real
0x140012b08  jmp     loc_140013031
0x140012b0d  cmp     [r12+8], rdx
0x140012b12  jnz     loc_140012F01
0x140012b18  mov     rax, [r12]
0x140012b1c  cmp     [rax+8], r12
0x140012b20  jnz     loc_140012F01
0x140012b26  mov     rcx, [rsp+0A8h+SpinLock]; SpinLock
0x140012b2e  mov     [rdx], rax
0x140012b31  mov     [rax+8], rdx
0x140012b35  lea     rax, [r12-170h]
0x140012b3d  mov     [r12+8], r12
0x140012b42  mov     [r12], r12
0x140012b46  dec     dword ptr [rcx+8]
0x140012b49  mov     [rsp+0A8h+RxContext], rax
0x140012b51  lock inc dword ptr [rax+4]
0x140012b55  and     dword ptr [rax+78h], 0BEF7FFFFh
0x140012b5c  movzx   edx, r8b; NewIrql
0x140012b60  call    cs:__imp_KeReleaseSpinLock
0x140012b67  nop     dword ptr [rax+rax+00h]
0x140012b6c  mov     r8, [rsp+0A8h+RxContext]
0x140012b74  test    r8, r8
0x140012b77  jz      short loc_140012BB3
0x140012b79  cmp     qword ptr [r8+358h], 0
0x140012b81  jnz     short loc_140012BB3
0x140012b83  mov     rax, [r8+50h]
0x140012b87  mov     rcx, [rax+160h]
0x140012b8e  test    rcx, rcx
0x140012b91  jz      short loc_140012BB3
0x140012b93  mov     rax, [rcx+298h]
0x140012b9a  test    rax, rax
0x140012b9d  jz      short loc_140012BB3
0x140012b9f  mov     dl, 24h ; '$'
0x140012ba1  mov     rcx, r8
0x140012ba4  call    _guard_dispatch_icall
0x140012ba9  mov     r8, [rsp+0A8h+RxContext]
0x140012bb1  jmp     short loc_140012BBB
0x140012bb3  mov     [rsp+0A8h+RxContext], r8
0x140012bbb  test    r12, r12
0x140012bbe  jz      loc_1400129A4
0x140012bc4  cmp     [rsi], r15
0x140012bc7  jnz     loc_140012CB2
0x140012bcd  mov     rax, [r15+28h]
0x140012bd1  cmp     qword ptr [rax], 0
0x140012bd5  jz      short loc_140012BE5
0x140012bd7  test    byte ptr [r13+100h], 5
0x140012bdf  jnz     loc_140012CB2
0x140012be5  cmp     byte ptr [rsi+18h], 0
0x140012be9  jz      loc_140012CB2
0x140012bef  cmp     dword ptr [rsi+1Ch], 0
0x140012bf3  jnz     loc_140012CB2
0x140012bf9  mov     edx, [r14+8]
0x140012bfd  add     rdx, [r14+18h]
0x140012c01  cmp     rdx, [r13+20h]
0x140012c05  jg      loc_140012CB2
0x140012c0b  cmp     rdx, [r13+28h]
0x140012c0f  jg      loc_140012CB2
0x140012c15  lea     rcx, [r13+218h]; FileLock
0x140012c1c  mov     rdx, rbp; Irp
0x140012c1f  call    cs:__imp_FsRtlCheckLockForReadAccess
0x140012c26  nop     dword ptr [rax+rax+00h]
0x140012c2b  test    al, al
0x140012c2d  jz      short loc_140012CAA
0x140012c2f  mov     r12, [rsp+0A8h+RxContext]
0x140012c37  mov     rax, [rbp+8]
0x140012c3b  mov     [r12+220h], rax
0x140012c43  mov     rax, [r14+18h]
0x140012c47  mov     [r12+230h], rax
0x140012c4f  mov     eax, [r14+8]
0x140012c53  mov     [r12+238h], eax
0x140012c5b  mov     eax, [r14+10h]
0x140012c5f  mov     [r12+23Ch], eax
0x140012c67  cmp     qword ptr [r12+358h], 0
0x140012c70  jnz     loc_1400129DF
0x140012c76  mov     rax, [r12+50h]
0x140012c7b  mov     rcx, [rax+160h]
0x140012c82  test    rcx, rcx
0x140012c85  jz      loc_1400129DF
0x140012c8b  mov     rax, [rcx+298h]
0x140012c92  test    rax, rax
0x140012c95  jz      loc_1400129DF
0x140012c9b  mov     dl, 24h ; '$'
0x140012c9d  mov     rcx, r12
0x140012ca0  call    _guard_dispatch_icall
0x140012ca5  jmp     loc_1400129DF
0x140012caa  mov     r8, [rsp+0A8h+RxContext]
0x140012cb2  lock or dword ptr [r8+80h], 2
0x140012cbb  mov     rax, [rsi+10h]
0x140012cbf  xor     edx, edx
0x140012cc1  mov     rcx, r8
0x140012cc4  mov     rax, [rax]
0x140012cc7  call    _guard_dispatch_icall
0x140012ccc  mov     rcx, [rsp+0A8h+RxContext]; RxContext
0x140012cd4  call    RxDereferenceAndDeleteRxContext_Real
0x140012cd9  jmp     loc_140013031
0x140012cde  cmp     cl, 4
0x140012ce1  jnz     loc_140012FF5
0x140012ce7  mov     r8d, [r14+8]; int
0x140012ceb  xor     edx, edx; Operation
0x140012ced  mov     rcx, rbp; PIRP
0x140012cf0  call    LockBufferForTurboIo
0x140012cf5  mov     ebx, eax
0x140012cf7  test    eax, eax
0x140012cf9  js      loc_140013031
0x140012cff  mov     r12, [rsi+r12*8+20h]
0x140012d04  mov     rcx, r12; SpinLock
0x140012d07  mov     [rsp+0A8h+SpinLock], r12
0x140012d0f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012d16  nop     dword ptr [rax+rax+00h]
0x140012d1b  lea     rdx, [r12+20h]
0x140012d20  movzx   r8d, al
0x140012d24  mov     r12, [rdx]
0x140012d27  cmp     r12, rdx
0x140012d2a  jnz     short loc_140012D8F
0x140012d2c  mov     rcx, [rsp+0A8h+SpinLock]; SpinLock
0x140012d34  movzx   edx, al; NewIrql
0x140012d37  call    cs:__imp_KeReleaseSpinLock
0x140012d3e  nop     dword ptr [rax+rax+00h]
0x140012d43  mov     r12, [rsp+0A8h+RxContext]
0x140012d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012d52  cmp     rcx, rdi
0x140012d55  jz      loc_1400129DF
0x140012d5b  test    dword ptr [rcx+2Ch], 4000h
0x140012d62  jz      loc_1400129DF
0x140012d68  cmp     byte ptr [rcx+29h], 1
0x140012d6c  jb      loc_1400129DF
0x140012d72  mov     rcx, [rcx+18h]
0x140012d76  lea     r8, WPP_d414fc76462934e262300deaf9706329_Traceguids
0x140012d7d  mov     edx, 18h
0x140012d82  mov     r9, rbp
0x140012d85  call    WPP_SF_q
0x140012d8a  jmp     loc_1400129DF
0x140012d8f  cmp     [r12+8], rdx
0x140012d94  jnz     loc_140012F01
0x140012d9a  mov     rax, [r12]
0x140012d9e  cmp     [rax+8], r12
0x140012da2  jnz     loc_140012F01
0x140012da8  mov     rcx, [rsp+0A8h+SpinLock]; SpinLock
0x140012db0  mov     [rdx], rax
0x140012db3  mov     [rax+8], rdx
0x140012db7  lea     rax, [r12-170h]
0x140012dbf  mov     [r12+8], r12
0x140012dc4  mov     [r12], r12
0x140012dc8  dec     dword ptr [rcx+8]
0x140012dcb  mov     [rsp+0A8h+RxContext], rax
0x140012dd3  lock inc dword ptr [rax+4]
0x140012dd7  and     dword ptr [rax+78h], 0BEF7FFFFh
0x140012dde  movzx   edx, r8b; NewIrql
0x140012de2  call    cs:__imp_KeReleaseSpinLock
0x140012de9  nop     dword ptr [rax+rax+00h]
0x140012dee  test    r12, r12
0x140012df1  jz      loc_140012D43
0x140012df7  cmp     [rsi], r15
0x140012dfa  jnz     loc_140012ED3
0x140012e00  mov     rax, [r15+28h]
0x140012e04  cmp     qword ptr [rax], 0
0x140012e08  jnz     loc_140012ED3
0x140012e0e  cmp     byte ptr [rsi+18h], 0
0x140012e12  jz      loc_140012ED3
  ... truncated ...
```
