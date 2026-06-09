# RxReconnectSrvOpen

- ea: `0x1400031a0`
- end: `0x140003407`
- name: `RxReconnectSrvOpen`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140004180`

## callees

- `0x1400031a0`
- `0x1400037e0`
- `0x140003eb0`
- `0x140025d00`
- `0x140026080`
- `0x1400623c0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000336c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000336c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140003233`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x140003233`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140003277`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140003277`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000332d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000332d`

## pseudocode

```c
__int64 __fastcall RxReconnectSrvOpen(__int64 a1)
{
  struct _RX_CONTEXT *v1; // rdi
  __int64 v3; // rbp
  __int64 (__fastcall *v4)(_QWORD, __int64); // rax
  unsigned int v5; // ebx
  struct _RDBSS_DEVICE_OBJECT *v7; // r15
  USHORT CurrentNodeNumber; // ax
  int LockArray_high; // edi
  USHORT v10; // r12
  ULONGLONG v11; // rbx
  struct _RX_CONTEXT *v12; // rax
  struct _RX_CONTEXT *v13; // r14
  LIST_ENTRY *v14; // rdi
  KIRQL v15; // al
  struct _LIST_ENTRY *Blink; // rdx
  struct _LIST_ENTRY *v17; // rax
  struct _LIST_ENTRY *v18; // rax
  __int64 (__fastcall *v19)(struct _RX_CONTEXT *, __int64); // rax

  v1 = 0;
  v3 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 392LL);
  v4 = *(__int64 (__fastcall **)(_QWORD, __int64))(v3 + 592);
  if ( !v4 )
    goto LABEL_21;
  v5 = v4(0, a1);
  if ( v5 == -1069481981 )
  {
    v7 = *(struct _RDBSS_DEVICE_OBJECT **)(*(_QWORD *)(a1 + 32) + 400LL);
    CurrentNodeNumber = KeGetCurrentNodeNumber();
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    v10 = CurrentNodeNumber;
    v11 = RxContextLookasideList.L.ListHead.Alignment + ((unsigned __int64)(unsigned int)(LockArray_high + 1) << 7);
    if ( !*(_BYTE *)(v11 + 176) )
      PplpLazyInitializeLookasideList(RxContextLookasideList.L.ListHead.Alignment, v11 + 64);
    v12 = (struct _RX_CONTEXT *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v11 + 64));
    v13 = v12;
    if ( !v12 )
      goto LABEL_19;
    memset(v12, 0, 0x78u);
    memset((char *)&v13->RdbssDbgExtension + 4, 0, 0x13Cu);
    memset(&v13->LowIoContext.ParamsFor.IoCtl.FsControlCode, 0, 0x1C4u);
    LODWORD(v13->RdbssDbgExtension) = 1;
    LOWORD(v13->LowIoContext.ParamsFor.ReadWrite.Flags) = v10;
    WORD1(v13->LowIoContext.ParamsFor.Locks.Length) = LockArray_high;
    RxInitializeContext(0, v7, 0x80000002, v13);
    v14 = &RxActiveContexts
        + 12
        * (((unsigned __int8)(WORD1(v13->LowIoContext.ParamsFor.Locks.Length)
                            % (unsigned int)RxActiveContextNodeBucketSize)
          + (unsigned __int8)RxActiveContextNodeBucketSize
          * (unsigned __int8)LOWORD(v13->LowIoContext.ParamsFor.ReadWrite.Flags))
         & 0x3F);
    v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&v14[4]);
    Blink = v14->Blink;
    if ( Blink->Flink != v14 )
      __fastfail(3u);
    v13->ContextListEntry.Flink = v14;
    v13->ContextListEntry.Blink = Blink;
    Blink->Flink = &v13->ContextListEntry;
    v14->Blink = &v13->ContextListEntry;
    KeReleaseSpinLock((PKSPIN_LOCK)&v14[4], v15);
    v17 = v13->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
    if ( v17 && (v18 = v17[41].Blink) != 0 )
    {
      ((void (__fastcall *)(struct _RX_CONTEXT *, _QWORD))v18)(v13, 0);
    }
    else
    {
LABEL_19:
      if ( !v13 )
        return (unsigned int)-1073741670;
    }
    LOWORD(v13->RealDevice) = 27;
    v1 = v13;
    v13->pFcb = *(PMRX_FCB *)(a1 + 32);
    v13->pFobx = 0;
    v13->CurrentIrp = 0;
    v13->CurrentIrpSp = 0;
    v13->pRelevantSrvOpen = (PMRX_SRV_OPEN)a1;
    v19 = *(__int64 (__fastcall **)(struct _RX_CONTEXT *, __int64))(v3 + 592);
    if ( !v19 )
      goto LABEL_21;
    v5 = v19(v13, a1);
  }
  if ( v5 == -1073741822 )
LABEL_21:
    v5 = 0;
  if ( v1 )
    RxDereferenceAndDeleteRxContext_Real(v1);
  if ( v5 == 259 )
    __int2c();
  return v5;
}

```

## disassembly

```asm
0x1400031a0  mov     [rsp+arg_8], rbx
0x1400031a5  mov     [rsp+arg_10], rbp
0x1400031aa  push    rsi
0x1400031ab  push    rdi
0x1400031ac  push    r12
0x1400031ae  push    r14
0x1400031b0  push    r15
0x1400031b2  sub     rsp, 20h
0x1400031b6  mov     rax, [rcx+20h]
0x1400031ba  xor     edi, edi
0x1400031bc  mov     rsi, rcx
0x1400031bf  mov     rbp, [rax+188h]
0x1400031c6  mov     rax, [rbp+250h]
0x1400031cd  test    rax, rax
0x1400031d0  jz      loc_1400033F9
0x1400031d6  mov     rdx, rcx
0x1400031d9  xor     ecx, ecx
0x1400031db  call    _guard_dispatch_icall
0x1400031e0  mov     ebx, eax
0x1400031e2  cmp     eax, 0C0410003h
0x1400031e7  jz      short loc_140003228
0x1400031e9  cmp     ebx, 0C0000002h
0x1400031ef  jz      loc_1400033F9
0x1400031f5  test    rdi, rdi
0x1400031f8  jz      short loc_140003202
0x1400031fa  mov     rcx, rdi; RxContext
0x1400031fd  call    RxDereferenceAndDeleteRxContext_Real
0x140003202  cmp     ebx, 103h
0x140003208  jz      loc_140003400
0x14000320e  mov     rbp, [rsp+48h+arg_10]
0x140003213  mov     eax, ebx
0x140003215  mov     rbx, [rsp+48h+arg_8]
0x14000321a  add     rsp, 20h
0x14000321e  pop     r15
0x140003220  pop     r14
0x140003222  pop     r12
0x140003224  pop     rdi
0x140003225  pop     rsi
0x140003226  retn
0x140003228  mov     rax, [rsi+20h]
0x14000322c  mov     r15, [rax+190h]
0x140003233  call    cs:__imp_KeGetCurrentNodeNumber
0x14000323a  nop     dword ptr [rax+rax+00h]
0x14000323f  mov     edi, gs:1A4h
0x140003247  movzx   r12d, ax
0x14000324b  mov     r8, qword ptr cs:RxContextLookasideList.L
0x140003252  lea     ebx, [rdi+1]
0x140003255  shl     rbx, 7
0x140003259  add     rbx, r8
0x14000325c  movzx   ecx, byte ptr [rbx+0B0h]
0x140003263  test    cl, cl
0x140003265  jnz     short loc_140003273
0x140003267  lea     rdx, [rbx+40h]
0x14000326b  mov     rcx, r8
0x14000326e  call    PplpLazyInitializeLookasideList
0x140003273  lea     rcx, [rbx+40h]; Lookaside
0x140003277  call    cs:__imp_ExAllocateFromLookasideListEx
0x14000327e  nop     dword ptr [rax+rax+00h]
0x140003283  mov     r14, rax
0x140003286  test    rax, rax
0x140003289  jz      loc_1400033EA
0x14000328f  xor     edx, edx; Val
0x140003291  mov     r8d, 78h ; 'x'; Size
0x140003297  mov     rcx, rax; void *
0x14000329a  call    memset
0x14000329f  lea     rcx, [r14+7Ch]; void *
0x1400032a3  xor     edx, edx; Val
0x1400032a5  mov     r8d, 13Ch; Size
0x1400032ab  call    memset
0x1400032b0  lea     rcx, [r14+1BCh]; void *
0x1400032b7  xor     edx, edx; Val
0x1400032b9  mov     r8d, 1C4h; Size
0x1400032bf  call    memset
0x1400032c4  mov     r9, r14; RxContext
0x1400032c7  mov     dword ptr [r14+78h], 1
0x1400032cf  mov     r8d, 80000002h; InitialContextFlags
0x1400032d5  mov     [r14+1B8h], r12w
0x1400032dd  mov     rdx, r15; RxDeviceObject
0x1400032e0  mov     [r14+1BAh], di
0x1400032e8  xor     ecx, ecx; Irp
0x1400032ea  call    RxInitializeContext
0x1400032ef  movzx   eax, word ptr [r14+1BAh]
0x1400032f7  lea     r15, RxActiveContexts
0x1400032fe  movzx   r8d, word ptr [r14+1B8h]
0x140003306  xor     edx, edx
0x140003308  div     cs:RxActiveContextNodeBucketSize
0x14000330e  imul    r8d, cs:RxActiveContextNodeBucketSize
0x140003316  lea     eax, [rdx+r8]
0x14000331a  and     eax, 3Fh
0x14000331d  lea     rbx, [rax+rax*2]
0x140003321  shl     rbx, 6
0x140003325  lea     rdi, [rbx+r15]
0x140003329  lea     rcx, [rdi+40h]; SpinLock
0x14000332d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003334  nop     dword ptr [rax+rax+00h]
0x140003339  mov     rdx, [rbx+r15+8]
0x14000333e  lea     rcx, [rbx+r15]
0x140003342  movzx   r8d, al
0x140003346  cmp     [rdx], rcx
0x140003349  jz      short loc_140003352
0x14000334b  mov     ecx, 3
0x140003350  int     29h; Win8: RtlFailFast(ecx)
0x140003352  lea     rax, [r14+8]
0x140003356  mov     [rax], rcx
0x140003359  mov     [rax+8], rdx
0x14000335d  mov     [rdx], rax
0x140003360  movzx   edx, r8b; NewIrql
0x140003364  mov     [rcx+8], rax
0x140003368  lea     rcx, [rdi+40h]; SpinLock
0x14000336c  call    cs:__imp_KeReleaseSpinLock
0x140003373  nop     dword ptr [rax+rax+00h]
0x140003378  mov     rax, [r14+50h]
0x14000337c  mov     rax, [rax+160h]
0x140003383  test    rax, rax
0x140003386  jz      short loc_1400033EA
0x140003388  mov     rax, [rax+298h]
0x14000338f  test    rax, rax
0x140003392  jz      short loc_1400033EA
0x140003394  xor     edx, edx
0x140003396  mov     rcx, r14
0x140003399  call    _guard_dispatch_icall
0x14000339e  mov     word ptr [r14+20h], 1Bh
0x1400033a5  mov     rdi, r14
0x1400033a8  mov     rax, [rsi+20h]
0x1400033ac  mov     [r14+38h], rax
0x1400033b0  mov     qword ptr [r14+40h], 0
0x1400033b8  mov     qword ptr [r14+28h], 0
0x1400033c0  mov     qword ptr [r14+30h], 0
0x1400033c8  mov     [r14+48h], rsi
0x1400033cc  mov     rax, [rbp+250h]
0x1400033d3  test    rax, rax
0x1400033d6  jz      short loc_1400033F9
0x1400033d8  mov     rdx, rsi
0x1400033db  mov     rcx, r14
0x1400033de  call    _guard_dispatch_icall
0x1400033e3  mov     ebx, eax
0x1400033e5  jmp     loc_1400031E9
0x1400033ea  test    r14, r14
0x1400033ed  jnz     short loc_14000339E
0x1400033ef  mov     ebx, 0C000009Ah
0x1400033f4  jmp     loc_14000320E
0x1400033f9  xor     ebx, ebx
0x1400033fb  jmp     loc_1400031F5
0x140003400  int     2Ch; Windows NT - assertion failure
0x140003402  jmp     loc_14000320E
```
