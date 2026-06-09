# FltpOpenClientPort

- ea: `0x18005f130`
- end: `0x18005f7bb`
- name: `FltpOpenClientPort`
- size: `1675`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180060110`

## callees

- `0x180009f20`
- `0x18000ff70`
- `0x180010400`
- `0x1800248e0`
- `0x180024c40`
- `0x18005f130`
- `0x18005f7d0`
- `0x18005f850`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x18005f750`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005f76e`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005f750`
- `ntoskrnl!ExReleaseFastMutex` at `0x18005f76e`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005f601`
- `ntoskrnl!ExAcquireFastMutex` at `0x18005f601`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005f6bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005f6bb`
- `ntoskrnl!ExAllocatePool2` at `0x18005f568`
- `ntoskrnl!ExAllocatePool2` at `0x18005f568`
- `ntoskrnl!KeInitializeEvent` at `0x18005f330`
- `ntoskrnl!KeInitializeEvent` at `0x18005f36e`
- `ntoskrnl!KeInitializeEvent` at `0x18005f3b9`
- `ntoskrnl!KeInitializeEvent` at `0x18005f3d5`
- `ntoskrnl!KeInitializeEvent` at `0x18005f507`
- `ntoskrnl!KeInitializeEvent` at `0x18005f330`
- `ntoskrnl!KeInitializeEvent` at `0x18005f36e`
- `ntoskrnl!KeInitializeEvent` at `0x18005f3b9`
- `ntoskrnl!KeInitializeEvent` at `0x18005f3d5`
- `ntoskrnl!KeInitializeEvent` at `0x18005f507`
- `ntoskrnl!ExGetPreviousMode` at `0x18005f21c`
- `ntoskrnl!ExGetPreviousMode` at `0x18005f21c`
- `ntoskrnl!KeInitializeSemaphore` at `0x18005f3a1`
- `ntoskrnl!KeInitializeSemaphore` at `0x18005f3a1`
- `ntoskrnl!ObfDereferenceObject` at `0x18005f4b8`
- `ntoskrnl!ObfDereferenceObject` at `0x18005f66f`
- `ntoskrnl!ObfDereferenceObject` at `0x18005f6a7`
- `ntoskrnl!ObfDereferenceObject` at `0x18005f72e`
- `ntoskrnl!ObfDereferenceObject` at `0x18005f4b8`
- `ntoskrnl!ObfDereferenceObject` at `0x18005f66f`
- `ntoskrnl!ObfDereferenceObject` at `0x18005f6a7`
- `ntoskrnl!ObfDereferenceObject` at `0x18005f72e`
- `ntoskrnl!ObfReferenceObject` at `0x18005f45b`
- `ntoskrnl!ObfReferenceObject` at `0x18005f584`
- `ntoskrnl!ObfReferenceObject` at `0x18005f45b`
- `ntoskrnl!ObfReferenceObject` at `0x18005f584`
- `ntoskrnl!ZwClose` at `0x18005f688`
- `ntoskrnl!ZwClose` at `0x18005f688`
- `ntoskrnl!ExInitializeRundownProtection` at `0x18005f305`
- `ntoskrnl!ExInitializeRundownProtection` at `0x18005f305`
- `ntoskrnl!RtlCompareMemory` at `0x18005f1cd`
- `ntoskrnl!RtlCompareMemory` at `0x18005f1cd`
- `ntoskrnl!ObCreateObject` at `0x18005f2d6`
- `ntoskrnl!ObCreateObject` at `0x18005f2d6`
- `ntoskrnl!ObInsertObject` at `0x18005f487`
- `ntoskrnl!ObInsertObject` at `0x18005f487`
- `ntoskrnl!IoIs32bitProcess` at `0x18005f18d`
- `ntoskrnl!IoIs32bitProcess` at `0x18005f1ea`
- `ntoskrnl!IoIs32bitProcess` at `0x18005f18d`
- `ntoskrnl!IoIs32bitProcess` at `0x18005f1ea`
- `ntoskrnl!ObReferenceObjectByName` at `0x18005f257`
- `ntoskrnl!ObReferenceObjectByName` at `0x18005f257`
- `ntoskrnl!IoCsqInitializeEx` at `0x18005f41e`
- `ntoskrnl!IoCsqInitializeEx` at `0x18005f41e`

## pseudocode

```c
__int64 __fastcall FltpOpenClientPort(__int64 a1, IRP *a2)
{
  unsigned __int16 *v2; // r13
  struct _IRP *MasterIrp; // rbx
  __int64 FltCcb; // rsi
  BOOLEAN v7; // al
  unsigned __int16 v8; // cx
  PMDL *p_MdlAddress; // r15
  LIST_ENTRY *p_ThreadListEntry; // r12
  bool v11; // zf
  unsigned int v12; // eax
  unsigned int Flink_low; // edi
  unsigned __int64 inserted; // rbx
  signed __int32 v15; // edx
  char *v16; // rcx
  void **Pool2; // r15
  struct _FAST_MUTEX *v18; // r14
  struct _FAST_MUTEX *v19; // rdi
  struct _FAST_MUTEX **Owner; // rcx
  KPROCESSOR_MODE CsqReleaseLock; // [rsp+28h] [rbp-58h]
  _BYTE v23[48]; // [rsp+50h] [rbp-30h] BYREF
  PVOID v24; // [rsp+C0h] [rbp+40h] BYREF
  PVOID Object; // [rsp+D0h] [rbp+50h] BYREF
  void *Handle; // [rsp+D8h] [rbp+58h] BYREF

  v2 = 0;
  v24 = 0;
  Object = 0;
  Handle = 0;
  memset(v23, 0, 44);
  if ( *(_WORD *)(a1 + 88) || (MasterIrp = a2->AssociatedIrp.MasterIrp) == 0 )
  {
    LODWORD(inserted) = -1073741790;
    return (unsigned int)inserted;
  }
  FltCcb = 0;
  v7 = IoIs32bitProcess(a2);
  v8 = *(&MasterIrp->Size + 2);
  if ( v7 )
  {
    if ( v8 < 0x10u )
    {
      LODWORD(inserted) = -1073741790;
      goto LABEL_29;
    }
  }
  else if ( v8 < 0x18u )
  {
    LODWORD(inserted) = -1073741790;
    goto LABEL_29;
  }
  if ( *((_BYTE *)&MasterIrp->Size + 3) == 7 )
  {
    p_MdlAddress = &MasterIrp->MdlAddress;
    if ( RtlCompareMemory(&MasterIrp->MdlAddress, "FLTPORT", 7u) == 7 )
    {
      p_ThreadListEntry = &MasterIrp->ThreadListEntry;
      v11 = IoIs32bitProcess(a2) == 0;
      v12 = *(&MasterIrp->Size + 2);
      if ( v11 )
      {
        Flink_low = LOWORD(p_ThreadListEntry->Flink);
        if ( Flink_low + 24 > v12 )
        {
          LODWORD(inserted) = -1073741790;
          goto LABEL_29;
        }
        inserted = *(_QWORD *)&MasterIrp->Flags;
        p_ThreadListEntry = (LIST_ENTRY *)(p_MdlAddress + 4);
      }
      else
      {
        Flink_low = LOWORD(MasterIrp->AssociatedIrp.MasterIrp);
        if ( Flink_low + 16 > v12 )
        {
          LODWORD(inserted) = -1073741790;
          goto LABEL_29;
        }
        inserted = *(&MasterIrp->Flags + 1);
      }
      if ( Flink_low )
        v2 = (unsigned __int16 *)p_ThreadListEntry;
      CsqReleaseLock = ExGetPreviousMode();
      LODWORD(inserted) = ObReferenceObjectByName(inserted, 0, 0, 2031617, qword_18003EF28, CsqReleaseLock, 0, &Object);
      if ( (inserted & 0x80000000) != 0LL )
      {
        Object = 0;
      }
      else
      {
        v15 = *((_DWORD *)Object + 18);
        if ( _InterlockedIncrement((volatile signed __int32 *)Object + 17) > v15 )
        {
          LODWORD(inserted) = -1073741242;
        }
        else
        {
          *(_DWORD *)v23 = 48;
          *(_QWORD *)&v23[8] = 0;
          *(_DWORD *)&v23[24] = 512;
          *(_QWORD *)&v23[16] = 0;
          *(_OWORD *)&v23[32] = 0;
          LODWORD(inserted) = ObCreateObject(0, qword_18003EF30, v23, 0, 0, 344, 0, 0, &v24);
          if ( (inserted & 0x80000000) != 0LL )
          {
            v24 = 0;
          }
          else
          {
            memset(v24, 0, 0x158u);
            ExInitializeRundownProtection((PEX_RUNDOWN_REF)v24 + 4);
            v16 = (char *)v24;
            *((_DWORD *)v24 + 10) = 1;
            *((_QWORD *)v16 + 6) = 0;
            *((_DWORD *)v16 + 14) = 0;
            KeInitializeEvent((PRKEVENT)(v16 + 64), SynchronizationEvent, 0);
            inserted = (unsigned __int64)v24;
            *((_DWORD *)v24 + 58) = 0;
            *(_DWORD *)(inserted + 160) = 1;
            *(_QWORD *)(inserted + 168) = 0;
            *(_DWORD *)(inserted + 176) = 0;
            KeInitializeEvent((PRKEVENT)(inserted + 184), SynchronizationEvent, 0);
            *(_QWORD *)(inserted + 224) = inserted + 216;
            *(_QWORD *)(inserted + 216) = inserted + 216;
            *(_DWORD *)(inserted + 240) = -1;
            KeInitializeSemaphore((PRKSEMAPHORE)(inserted + 248), 0, 0x7FFFFFFF);
            KeInitializeEvent((PRKEVENT)(inserted + 280), NotificationEvent, 0);
            KeInitializeEvent((PRKEVENT)v24 + 13, NotificationEvent, 0);
            LODWORD(inserted) = IoCsqInitializeEx(
                                  (PIO_CSQ)(inserted + 96),
                                  FltpAddMessageWaiter,
                                  FltpRemoveMessageWaiter,
                                  FltpGetNextMessageWaiter,
                                  FltpAcquireMessageWaiterLock,
                                  FltpReleaseMessageWaiterLock,
                                  FltpCancelMessageWaiter);
            if ( (int)FltpDbgStatus((unsigned int)inserted, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 1052, 0) < 0 )
              goto LABEL_37;
            *((_QWORD *)v24 + 2) = Object;
            ObfReferenceObject(Object);
            inserted = (unsigned int)ObInsertObject(v24, 0, 0x1F0001u, 1u, 0, &Handle);
            if ( (int)FltpDbgStatus(inserted, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 1088, 0) < 0 )
            {
              v24 = 0;
              goto LABEL_37;
            }
            ObfDereferenceObject(Object);
            Object = 0;
            FltCcb = FltpAllocateFltCcb(61709, 0);
            if ( FltCcb )
            {
              *(_QWORD *)(FltCcb + 8) = v24;
              *(_DWORD *)(FltCcb + 88) = 0;
              *(_DWORD *)(FltCcb + 16) = 1;
              *(_QWORD *)(FltCcb + 24) = 0;
              *(_DWORD *)(FltCcb + 32) = 0;
              KeInitializeEvent((PRKEVENT)(FltCcb + 40), SynchronizationEvent, 0);
              *(_QWORD *)(FltCcb + 80) = FltCcb + 72;
              *(_QWORD *)(FltCcb + 72) = FltCcb + 72;
              inserted = (unsigned int)FltObjectReference(*(PVOID *)(*((_QWORD *)v24 + 2) + 48LL));
              if ( (int)FltpDbgStatus(inserted, "minkernel\\fs\\filtermgr\\filter\\messagesup.c", 1140, 3223060491LL) >= 0 )
              {
                Pool2 = (void **)ExAllocatePool2(64, 16, 1885556038);
                if ( Pool2 )
                {
                  ObfReferenceObject(v24);
                  *Pool2 = Handle;
                  Pool2[1] = v24;
                  LODWORD(inserted) = (*(__int64 (__fastcall **)(void **, _QWORD, unsigned __int16 *, _QWORD, char *))(*((_QWORD *)v24 + 2) + 16LL))(
                                        Pool2,
                                        *(_QWORD *)(*((_QWORD *)v24 + 2) + 56LL),
                                        v2,
                                        Flink_low,
                                        (char *)v24 + 24);
                  if ( (int)FltpDbgStatus(
                              (unsigned int)inserted,
                              "minkernel\\fs\\filtermgr\\filter\\messagesup.c",
                              1163,
                              0) < 0 )
                  {
                    ObfDereferenceObject(v24);
                    ExFreePoolWithTag(Pool2, 0x70634D46u);
                  }
                  else
                  {
                    *(_QWORD *)(a1 + 32) = FltCcb;
                    v18 = (struct _FAST_MUTEX *)v24;
                    v19 = (struct _FAST_MUTEX *)(*(_QWORD *)(*((_QWORD *)v24 + 2) + 48LL) + 608LL);
                    ExAcquireFastMutex(v19);
                    if ( (v19[1].Contention & 1) != 0 )
                    {
                      ExReleaseFastMutex(v19);
                    }
                    else
                    {
                      v19[1].Contention += 2;
                      Owner = (struct _FAST_MUTEX **)v19[1].Owner;
                      if ( *Owner != &v19[1] )
                        __fastfail(3u);
                      v18->Owner = Owner;
                      *(_QWORD *)&v18->Count = v19 + 1;
                      *Owner = v18;
                      v19[1].Owner = v18;
                      ExReleaseFastMutex(v19);
                    }
                  }
                }
                else
                {
                  LODWORD(inserted) = -1073741670;
                }
                FltObjectDereference(*(PVOID *)(*((_QWORD *)v24 + 2) + 48LL));
              }
LABEL_37:
              if ( (inserted & 0x80000000) == 0LL )
                return (unsigned int)inserted;
              goto LABEL_29;
            }
            LODWORD(inserted) = -1073741670;
          }
        }
      }
    }
    else
    {
      LODWORD(inserted) = -1073741790;
    }
  }
  else
  {
    LODWORD(inserted) = -1073741790;
  }
LABEL_29:
  if ( v24 )
    ObfDereferenceObject(v24);
  if ( Handle )
  {
    ZwClose(Handle);
  }
  else if ( Object )
  {
    _InterlockedDecrement((volatile signed __int32 *)Object + 17);
    ObfDereferenceObject(Object);
  }
  if ( FltCcb )
    FltpFreeFltCcb((PVOID)FltCcb);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x18005f130  mov     [rsp-38h+arg_8], rbx
0x18005f135  push    rbp
0x18005f136  push    rsi
0x18005f137  push    rdi
0x18005f138  push    r12
0x18005f13a  push    r13
0x18005f13c  push    r14
0x18005f13e  push    r15
0x18005f140  mov     rbp, rsp
0x18005f143  sub     rsp, 80h
0x18005f14a  xor     r13d, r13d
0x18005f14d  xorps   xmm0, xmm0
0x18005f150  xor     eax, eax
0x18005f152  mov     [rbp+arg_0], r13
0x18005f156  mov     rdi, rdx
0x18005f159  mov     r14, rcx
0x18005f15c  movups  [rbp+var_20], xmm0
0x18005f160  mov     [rbp+Object], r13
0x18005f164  movups  [rbp+var_20+0Ch], xmm0
0x18005f168  mov     [rbp+Handle], r13
0x18005f16c  movups  [rbp+var_30], xmm0
0x18005f170  cmp     [rcx+58h], ax
0x18005f174  ja      loc_18005F77F
0x18005f17a  mov     rbx, [rdx+18h]
0x18005f17e  test    rbx, rbx
0x18005f181  jz      loc_18005F77F
0x18005f187  mov     rcx, rdx; Irp
0x18005f18a  mov     esi, r13d
0x18005f18d  call    cs:__imp_IoIs32bitProcess
0x18005f194  nop     dword ptr [rax+rax+00h]
0x18005f199  movzx   ecx, word ptr [rbx+6]
0x18005f19d  test    al, al
0x18005f19f  jz      loc_18005F650
0x18005f1a5  cmp     cx, 10h
0x18005f1a9  jb      loc_18005F661
0x18005f1af  cmp     byte ptr [rbx+5], 7
0x18005f1b3  jnz     loc_18005F761
0x18005f1b9  lea     r15, [rbx+8]
0x18005f1bd  mov     r8d, 7; Length
0x18005f1c3  mov     rcx, r15; Source1
0x18005f1c6  lea     rdx, aFltport; "FLTPORT"
0x18005f1cd  call    cs:__imp_RtlCompareMemory
0x18005f1d4  nop     dword ptr [rax+rax+00h]
0x18005f1d9  cmp     rax, 7
0x18005f1dd  jnz     loc_18005F789
0x18005f1e3  mov     rcx, rdi; Irp
0x18005f1e6  lea     r12, [r15+18h]
0x18005f1ea  call    cs:__imp_IoIs32bitProcess
0x18005f1f1  nop     dword ptr [rax+rax+00h]
0x18005f1f6  test    al, al
0x18005f1f8  movzx   eax, word ptr [rbx+6]
0x18005f1fc  jz      loc_18005F633
0x18005f202  movzx   edi, word ptr [r15+10h]
0x18005f207  lea     ecx, [rdi+10h]
0x18005f20a  cmp     ecx, eax
0x18005f20c  ja      loc_18005F793
0x18005f212  mov     ebx, [r15+0Ch]
0x18005f216  test    edi, edi
0x18005f218  cmovnz  r13, r12
0x18005f21c  call    cs:__imp_ExGetPreviousMode
0x18005f223  nop     dword ptr [rax+rax+00h]
0x18005f228  lea     rcx, [rbp+Object]
0x18005f22c  xor     r15d, r15d
0x18005f22f  mov     [rsp+80h+var_48], rcx
0x18005f234  mov     r9d, 1F0001h
0x18005f23a  mov     [rsp+80h+CsqCompleteCanceledIrp], r15
0x18005f23f  xor     r8d, r8d
0x18005f242  mov     byte ptr [rsp+80h+CsqReleaseLock], al
0x18005f246  xor     edx, edx
0x18005f248  mov     rax, cs:qword_18003EF28
0x18005f24f  mov     rcx, rbx
0x18005f252  mov     [rsp+80h+CsqAcquireLock], rax
0x18005f257  call    cs:__imp_ObReferenceObjectByName
0x18005f25e  nop     dword ptr [rax+rax+00h]
0x18005f263  mov     ebx, eax
0x18005f265  test    eax, eax
0x18005f267  js      loc_18005F6FA
0x18005f26d  mov     rcx, [rbp+Object]
0x18005f271  mov     eax, 1
0x18005f276  mov     edx, [rcx+48h]
0x18005f279  lock xadd [rcx+44h], eax
0x18005f27e  inc     eax
0x18005f280  cmp     eax, edx
0x18005f282  jg      loc_18005F7A7
0x18005f288  mov     rdx, cs:qword_18003EF30
0x18005f28f  lea     rax, [rbp+arg_0]
0x18005f293  mov     [rsp+80h+var_40], rax
0x18005f298  lea     r8, [rbp+var_30]
0x18005f29c  mov     dword ptr [rsp+80h+var_48], r15d
0x18005f2a1  xorps   xmm0, xmm0
0x18005f2a4  mov     dword ptr [rsp+80h+CsqCompleteCanceledIrp], r15d
0x18005f2a9  xor     r9d, r9d
0x18005f2ac  mov     dword ptr [rsp+80h+CsqReleaseLock], 158h
0x18005f2b4  xor     ecx, ecx
0x18005f2b6  mov     [rsp+80h+CsqAcquireLock], r15
0x18005f2bb  mov     dword ptr [rbp+var_30], 30h ; '0'
0x18005f2c2  mov     qword ptr [rbp+var_30+8], r15
0x18005f2c6  mov     dword ptr [rbp+var_20+8], 200h
0x18005f2cd  mov     qword ptr [rbp+var_20], r15
0x18005f2d1  movdqu  [rbp+var_10], xmm0
0x18005f2d6  call    cs:__imp_ObCreateObject
0x18005f2dd  nop     dword ptr [rax+rax+00h]
0x18005f2e2  mov     ebx, eax
0x18005f2e4  test    eax, eax
0x18005f2e6  js      loc_18005F703
0x18005f2ec  mov     rcx, [rbp+arg_0]; void *
0x18005f2f0  xor     edx, edx; Val
0x18005f2f2  mov     r8d, 158h; Size
0x18005f2f8  call    memset
0x18005f2fd  mov     rcx, [rbp+arg_0]
0x18005f301  add     rcx, 20h ; ' '; RunRef
0x18005f305  call    cs:__imp_ExInitializeRundownProtection
0x18005f30c  nop     dword ptr [rax+rax+00h]
0x18005f311  mov     rcx, [rbp+arg_0]
0x18005f315  xor     r8d, r8d; State
0x18005f318  mov     edx, 1; Type
0x18005f31d  mov     dword ptr [rcx+28h], 1
0x18005f324  mov     [rcx+30h], r15
0x18005f328  mov     [rcx+38h], r15d
0x18005f32c  add     rcx, 40h ; '@'; Event
0x18005f330  call    cs:__imp_KeInitializeEvent
0x18005f337  nop     dword ptr [rax+rax+00h]
0x18005f33c  mov     rbx, [rbp+arg_0]
0x18005f340  xor     r8d, r8d; State
0x18005f343  mov     edx, 1; Type
0x18005f348  mov     [rbx+0E8h], r15d
0x18005f34f  lea     rcx, [rbx+0B8h]; Event
0x18005f356  mov     dword ptr [rbx+0A0h], 1
0x18005f360  mov     [rbx+0A8h], r15
0x18005f367  mov     [rbx+0B0h], r15d
0x18005f36e  call    cs:__imp_KeInitializeEvent
0x18005f375  nop     dword ptr [rax+rax+00h]
0x18005f37a  lea     rax, [rbx+0D8h]
0x18005f381  xor     edx, edx; Count
0x18005f383  mov     [rax+8], rax
0x18005f387  lea     rcx, [rbx+0F8h]; Semaphore
0x18005f38e  mov     [rax], rax
0x18005f391  mov     r8d, 7FFFFFFFh; Limit
0x18005f397  mov     dword ptr [rbx+0F0h], 0FFFFFFFFh
0x18005f3a1  call    cs:__imp_KeInitializeSemaphore
0x18005f3a8  nop     dword ptr [rax+rax+00h]
0x18005f3ad  lea     rcx, [rbx+118h]; Event
0x18005f3b4  xor     r8d, r8d; State
0x18005f3b7  xor     edx, edx; Type
0x18005f3b9  call    cs:__imp_KeInitializeEvent
0x18005f3c0  nop     dword ptr [rax+rax+00h]
0x18005f3c5  mov     rcx, [rbp+arg_0]
0x18005f3c9  xor     r8d, r8d; State
0x18005f3cc  add     rcx, 138h; Event
0x18005f3d3  xor     edx, edx; Type
0x18005f3d5  call    cs:__imp_KeInitializeEvent
0x18005f3dc  nop     dword ptr [rax+rax+00h]
0x18005f3e1  lea     rax, FltpCancelMessageWaiter
0x18005f3e8  mov     [rsp+80h+CsqCompleteCanceledIrp], rax; CsqCompleteCanceledIrp
0x18005f3ed  lea     r9, FltpGetNextMessageWaiter; CsqPeekNextIrp
0x18005f3f4  lea     rax, FltpReleaseMessageWaiterLock
0x18005f3fb  mov     [rsp+80h+CsqReleaseLock], rax; CsqReleaseLock
0x18005f400  lea     r8, FltpRemoveMessageWaiter; CsqRemoveIrp
0x18005f407  lea     rax, FltpAcquireMessageWaiterLock
0x18005f40e  lea     rdx, FltpAddMessageWaiter; CsqInsertIrp
0x18005f415  mov     [rsp+80h+CsqAcquireLock], rax; CsqAcquireLock
0x18005f41a  lea     rcx, [rbx+60h]; Csq
0x18005f41e  call    cs:__imp_IoCsqInitializeEx
0x18005f425  nop     dword ptr [rax+rax+00h]
0x18005f42a  mov     r8d, 41Ch
0x18005f430  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18005f437  mov     ecx, eax
0x18005f439  xor     r9d, r9d
0x18005f43c  mov     ebx, eax
0x18005f43e  call    FltpDbgStatus
0x18005f443  test    eax, eax
0x18005f445  js      loc_18005F6D8
0x18005f44b  mov     rcx, [rbp+arg_0]
0x18005f44f  mov     rax, [rbp+Object]
0x18005f453  mov     [rcx+10h], rax
0x18005f457  mov     rcx, [rbp+Object]; Object
0x18005f45b  call    cs:__imp_ObfReferenceObject
0x18005f462  nop     dword ptr [rax+rax+00h]
0x18005f467  mov     rcx, [rbp+arg_0]; Object
0x18005f46b  lea     rax, [rbp+Handle]
0x18005f46f  mov     [rsp+80h+CsqReleaseLock], rax; Handle
0x18005f474  xor     edx, edx; PassedAccessState
0x18005f476  mov     r9d, 1; ObjectPointerBias
0x18005f47c  mov     [rsp+80h+CsqAcquireLock], r15; NewObject
0x18005f481  mov     r8d, 1F0001h; DesiredAccess
0x18005f487  call    cs:__imp_ObInsertObject
0x18005f48e  nop     dword ptr [rax+rax+00h]
0x18005f493  mov     r8d, 440h
0x18005f499  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18005f4a0  mov     ecx, eax
0x18005f4a2  xor     r9d, r9d
0x18005f4a5  mov     ebx, eax
0x18005f4a7  call    FltpDbgStatus
0x18005f4ac  test    eax, eax
0x18005f4ae  js      loc_18005F70C
0x18005f4b4  mov     rcx, [rbp+Object]; Object
0x18005f4b8  call    cs:__imp_ObfDereferenceObject
0x18005f4bf  nop     dword ptr [rax+rax+00h]
0x18005f4c4  xor     edx, edx
0x18005f4c6  mov     [rbp+Object], r15
0x18005f4ca  mov     ecx, 0F10Dh
0x18005f4cf  call    FltpAllocateFltCcb
0x18005f4d4  mov     rsi, rax
0x18005f4d7  test    rax, rax
0x18005f4da  jz      loc_18005F7B1
0x18005f4e0  mov     rax, [rbp+arg_0]
0x18005f4e4  lea     rcx, [rsi+28h]; Event
0x18005f4e8  mov     [rsi+8], rax
0x18005f4ec  xor     r8d, r8d; State
0x18005f4ef  mov     [rsi+58h], r15d
0x18005f4f3  mov     edx, 1; Type
0x18005f4f8  mov     dword ptr [rsi+10h], 1
0x18005f4ff  mov     [rsi+18h], r15
0x18005f503  mov     [rsi+20h], r15d
0x18005f507  call    cs:__imp_KeInitializeEvent
0x18005f50e  nop     dword ptr [rax+rax+00h]
0x18005f513  lea     rax, [rsi+48h]
0x18005f517  mov     [rax+8], rax
0x18005f51b  mov     [rax], rax
0x18005f51e  mov     rax, [rbp+arg_0]
0x18005f522  mov     rcx, [rax+10h]
0x18005f526  mov     rcx, [rcx+30h]; FltObject
0x18005f52a  call    FltObjectReference
0x18005f52f  mov     r8d, 474h
0x18005f535  mov     [rsp+80h+CsqAcquireLock], r15
0x18005f53a  mov     r9d, 0C01C000Bh
0x18005f540  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18005f547  mov     ecx, eax
0x18005f549  mov     ebx, eax
0x18005f54b  call    FltpDbgStatus
0x18005f550  test    eax, eax
0x18005f552  js      loc_18005F6D8
0x18005f558  mov     edx, 10h
0x18005f55d  mov     ecx, 40h ; '@'
0x18005f562  mov     r8d, 70634D46h
0x18005f568  call    cs:__imp_ExAllocatePool2
0x18005f56f  nop     dword ptr [rax+rax+00h]
0x18005f574  mov     r15, rax
0x18005f577  test    rax, rax
0x18005f57a  jz      loc_18005F712
0x18005f580  mov     rcx, [rbp+arg_0]; Object
0x18005f584  call    cs:__imp_ObfReferenceObject
0x18005f58b  nop     dword ptr [rax+rax+00h]
0x18005f590  mov     rcx, [rbp+Handle]
0x18005f594  mov     r9d, edi
0x18005f597  mov     [r15], rcx
0x18005f59a  mov     r8, r13
0x18005f59d  mov     rcx, [rbp+arg_0]
0x18005f5a1  mov     [r15+8], rcx
0x18005f5a5  mov     rcx, [rbp+arg_0]
0x18005f5a9  mov     rdx, [rcx+10h]
0x18005f5ad  add     rcx, 18h
0x18005f5b1  mov     [rsp+80h+CsqAcquireLock], rcx
0x18005f5b6  mov     rcx, r15
0x18005f5b9  mov     rax, [rdx+10h]
0x18005f5bd  mov     rdx, [rdx+38h]
0x18005f5c1  call    _guard_dispatch_icall
0x18005f5c6  mov     r8d, 48Bh
0x18005f5cc  lea     rdx, aMinkernelFsFil_23; "minkernel\\fs\\filtermgr\\filter\\messa"...
0x18005f5d3  xor     r9d, r9d
0x18005f5d6  mov     ecx, eax
0x18005f5d8  mov     ebx, eax
0x18005f5da  call    FltpDbgStatus
0x18005f5df  test    eax, eax
0x18005f5e1  js      loc_18005F6A3
0x18005f5e7  mov     [r14+20h], rsi
0x18005f5eb  mov     r14, [rbp+arg_0]
0x18005f5ef  mov     rax, [r14+10h]
0x18005f5f3  mov     rdi, [rax+30h]
0x18005f5f7  add     rdi, 260h
0x18005f5fe  mov     rcx, rdi; FastMutex
0x18005f601  call    cs:__imp_ExAcquireFastMutex
0x18005f608  nop     dword ptr [rax+rax+00h]
0x18005f60d  test    byte ptr [rdi+48h], 1
0x18005f611  jnz     loc_18005F76B
0x18005f617  add     dword ptr [rdi+48h], 2
0x18005f61b  lea     rax, [rdi+38h]
0x18005f61f  mov     rcx, [rax+8]
0x18005f623  cmp     [rcx], rax
0x18005f626  jz      loc_18005F73F
0x18005f62c  mov     ecx, 3
0x18005f631  int     29h; Win8: RtlFailFast(ecx)
0x18005f633  movzx   edi, word ptr [r12]
0x18005f638  lea     ecx, [rdi+18h]
0x18005f63b  cmp     ecx, eax
0x18005f63d  ja      loc_18005F79D
0x18005f643  mov     rbx, [r15+8]
0x18005f647  lea     r12, [r15+20h]
0x18005f64b  jmp     loc_18005F216
0x18005f650  cmp     cx, 18h
0x18005f654  jnb     loc_18005F1AF
0x18005f65a  mov     ebx, 0C0000022h
0x18005f65f  jmp     short loc_18005F666
0x18005f661  mov     ebx, 0C0000022h
0x18005f666  mov     rcx, [rbp+arg_0]; Object
0x18005f66a  test    rcx, rcx
0x18005f66d  jz      short loc_18005F67B
0x18005f66f  call    cs:__imp_ObfDereferenceObject
0x18005f676  nop     dword ptr [rax+rax+00h]
0x18005f67b  mov     rcx, [rbp+Handle]; Handle
  ... truncated ...
```
