# Smb2CreateShadowSrvOpen

- ea: `0x140027880`
- end: `0x140027c4a`
- name: `Smb2CreateShadowSrvOpen`
- size: `970`
- prototype: `__int64 __fastcall(char *pContext)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140005820`

## callees

- `0x140014650`
- `0x140014a00`
- `0x140027880`
- `0x14002a648`
- `0x140037240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140027bc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027bdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027c16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027c2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027bc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027bdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027c16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027c2a`
- `ntoskrnl!ExAllocatePool2` at `0x1400278ea`
- `ntoskrnl!ExAllocatePool2` at `0x14002793e`
- `ntoskrnl!ExAllocatePool2` at `0x1400278ea`
- `ntoskrnl!ExAllocatePool2` at `0x14002793e`
- `ntoskrnl!KeInitializeEvent` at `0x140027acf`
- `ntoskrnl!KeInitializeEvent` at `0x140027acf`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400278bc`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400278bc`
- `rdbss!RxDisableLocalBuffering` at `0x140027b3f`
- `rdbss!RxDisableLocalBuffering` at `0x140027b3f`
- `rdbss!RxPostToWorkerThread` at `0x140027afe`
- `rdbss!RxPostToWorkerThread` at `0x140027afe`
- `rdbss!RxWaitSync` at `0x140027a1c`
- `rdbss!RxWaitSync` at `0x140027b17`
- `rdbss!RxWaitSync` at `0x140027a1c`
- `rdbss!RxWaitSync` at `0x140027b17`
- `rdbss!RxCreateRxContext` at `0x140027962`
- `rdbss!RxCreateRxContext` at `0x140027962`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140027a87`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140027a98`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140027a87`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140027a98`

## pseudocode

```c
__int64 __fastcall Smb2CreateShadowSrvOpen(char *pContext)
{
  int v1; // eax
  __int64 v3; // r13
  __int64 v4; // r15
  __int64 Pool2; // rbp
  int StoredStatus; // esi
  WCHAR *v8; // r14
  PRX_CONTEXT RxContext; // rax
  struct _RX_CONTEXT *v10; // rdi
  struct _MRX_SRV_OPEN_ *v11; // rcx
  struct _RDBSS_DEVICE_OBJECT *v12; // rcx
  unsigned int v13; // edi
  __int32 v14; // esi
  __int64 v15; // rcx
  __int64 v16; // rcx
  IRP *v17; // [rsp+60h] [rbp+8h]

  v1 = *((_DWORD *)pContext + 128);
  if ( (v1 & 3) == 0 )
    return 3221225659LL;
  if ( (v1 & 0x10000) != 0 )
    return 3221225659LL;
  v3 = *((_QWORD *)pContext + 9);
  if ( *(_QWORD *)(v3 + 64) )
    return 3221225659LL;
  v4 = *((_QWORD *)pContext + 7);
  if ( !ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v4 + 8)) )
    return 3221225659LL;
  Pool2 = ExAllocatePool2(64, 88, 1834182739);
  if ( !Pool2 )
    return 3221225626LL;
  StoredStatus = -1073741670;
  v17 = (IRP *)*((_QWORD *)pContext + 5);
  if ( !v17 || (v8 = (WCHAR *)ExAllocatePool2(66, 544, 1834182739)) == 0 )
  {
LABEL_28:
    ExFreePoolWithTag((PVOID)Pool2, 0x6D536853u);
    return (unsigned int)StoredStatus;
  }
  RxContext = RxCreateRxContext(0, *((PRDBSS_DEVICE_OBJECT *)pContext + 10), 2u);
  v10 = RxContext;
  if ( !RxContext )
    goto LABEL_27;
  RxContext->pFcb = (PMRX_FCB)*((_QWORD *)pContext + 7);
  RxContext->pFobx = (PMRX_FOBX)*((_QWORD *)pContext + 8);
  v11 = (struct _MRX_SRV_OPEN_ *)*((_QWORD *)pContext + 9);
  LODWORD(RxContext->RdbssDbgExtension) |= 0x200000u;
  RxContext->pRelevantSrvOpen = v11;
  RxContext->CurrentIrp = v17;
  *((_WORD *)&RxContext->9 + 61) |= 1u;
  *((_DWORD *)&RxContext->9 + 42) = 0;
  *((_QWORD *)&RxContext->9 + 19) = 0;
  RxContext->InformationToReturn = 0;
  *((_QWORD *)&RxContext->9 + 16) = 0;
  LOBYTE(RxContext->RealDevice) = 13;
  *((_WORD *)&RxContext->9 + 60) = 6;
  *((_DWORD *)&RxContext->9 + 35) = 1310840;
  *((_BYTE *)&RxContext->9 + 176) = 0;
  *((_DWORD *)&RxContext->9 + 43) = 544;
  RxContext->Create.TransportName.Buffer = v8;
  StoredStatus = (*(__int64 (__fastcall **)(PRX_CONTEXT))(*(_QWORD *)(*((_QWORD *)pContext + 10) + 352LL) + 352LL))(RxContext);
  if ( StoredStatus == 259 )
  {
    RxWaitSync(v10);
    StoredStatus = v10->StoredStatus;
  }
  v10->CurrentIrp = 0;
  if ( !StoredStatus
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_iii(
      WPP_GLOBAL_Control->AttachedDevice,
      10,
      WPP_f3cc199661c03597963a8c8eae40d83a_Traceguids,
      *(_QWORD *)v8,
      *((_QWORD *)v8 + 1),
      *((_QWORD *)v8 + 2));
    RxDereferenceAndDeleteRxContext_Real(v10);
    goto LABEL_18;
  }
  RxDereferenceAndDeleteRxContext_Real(v10);
  if ( StoredStatus < 0 )
  {
LABEL_27:
    ExFreePoolWithTag(v8, 0x6D536853u);
    goto LABEL_28;
  }
LABEL_18:
  *(_OWORD *)(Pool2 + 64) = *(_OWORD *)v8;
  *(_QWORD *)(Pool2 + 80) = *((_QWORD *)v8 + 2);
  *(_QWORD *)(v3 + 64) = Pool2;
  KeInitializeEvent((PRKEVENT)pContext + 16, NotificationEvent, 0);
  v12 = (struct _RDBSS_DEVICE_OBJECT *)*((_QWORD *)pContext + 10);
  *((_QWORD *)pContext + 26) = Pool2;
  v13 = RxPostToWorkerThread(v12, DelayedWorkQueue, (PRX_WORK_QUEUE_ITEM)(pContext + 304), MrxSmbGetSrvHandle, pContext);
  if ( v13 || (RxWaitSync(pContext), (v13 = *((_DWORD *)pContext + 52)) != 0) )
  {
    *(_QWORD *)(v3 + 64) = 0;
    ExFreePoolWithTag((PVOID)Pool2, 0x6D536853u);
  }
  else
  {
    *(_DWORD *)(v4 + 156) |= 0x10000u;
    RxDisableLocalBuffering(v4);
    Smb2InvalidateFileInfoCacheEntry(pContext, *(_QWORD *)(*(_QWORD *)(v4 + 120) + 40LL) + 376LL);
    v14 = 0;
    v15 = *(_QWORD *)(*((_QWORD *)pContext + 7) + 288LL);
    if ( v15 )
    {
      v16 = *(_QWORD *)(v15 + 136);
      if ( v16 )
        v14 = *(_DWORD *)(v16 + 88);
    }
    Smb2InvalidateSingleFileInDirInfoCache(pContext, *(_QWORD *)(*(_QWORD *)(v4 + 120) + 40LL) + 1112LL);
    _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(*((_QWORD *)pContext + 7) + 136LL) + 84LL), v14);
  }
  ExFreePoolWithTag(v8, 0x6D536853u);
  return v13;
}

```

## disassembly

```asm
0x140027880  push    rbx
0x140027882  push    r13
0x140027884  push    r15
0x140027886  sub     rsp, 40h
0x14002788a  mov     eax, [rcx+200h]
0x140027890  mov     rbx, rcx
0x140027893  test    al, 3
0x140027895  jz      loc_140027C3A
0x14002789b  bt      eax, 10h
0x14002789f  jb      loc_140027C3A
0x1400278a5  mov     r13, [rcx+48h]
0x1400278a9  cmp     qword ptr [r13+40h], 0
0x1400278ae  jnz     loc_140027C3A
0x1400278b4  mov     r15, [rcx+38h]
0x1400278b8  mov     rcx, [r15+8]; Resource
0x1400278bc  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1400278c3  nop     dword ptr [rax+rax+00h]
0x1400278c8  test    al, al
0x1400278ca  jz      loc_140027C3A
0x1400278d0  mov     [rsp+58h+arg_8], rbp
0x1400278d5  mov     edx, 58h ; 'X'
0x1400278da  mov     ecx, 40h ; '@'
0x1400278df  mov     [rsp+58h+arg_10], rsi
0x1400278e4  mov     r8d, 6D536853h
0x1400278ea  call    cs:__imp_ExAllocatePool2
0x1400278f1  nop     dword ptr [rax+rax+00h]
0x1400278f6  mov     rbp, rax
0x1400278f9  test    rax, rax
0x1400278fc  jnz     short loc_140027908
0x1400278fe  mov     eax, 0C000009Ah
0x140027903  jmp     loc_140027BF9
0x140027908  mov     rax, [rbx+28h]
0x14002790c  mov     esi, 0C000009Ah
0x140027911  mov     [rsp+58h+arg_18], rdi
0x140027916  mov     [rsp+58h+var_20], r12
0x14002791b  mov     [rsp+58h+var_28], r14
0x140027920  mov     [rsp+58h+arg_0], rax
0x140027925  test    rax, rax
0x140027928  jz      loc_140027C22
0x14002792e  mov     edx, 220h
0x140027933  mov     ecx, 42h ; 'B'
0x140027938  mov     r8d, 6D536853h
0x14002793e  call    cs:__imp_ExAllocatePool2
0x140027945  nop     dword ptr [rax+rax+00h]
0x14002794a  mov     r14, rax
0x14002794d  test    rax, rax
0x140027950  jz      loc_140027C22
0x140027956  mov     rdx, [rbx+50h]; RxDeviceObject
0x14002795a  mov     r8d, 2; InitialContextFlags
0x140027960  xor     ecx, ecx; Irp
0x140027962  call    cs:__imp_RxCreateRxContext
0x140027969  nop     dword ptr [rax+rax+00h]
0x14002796e  mov     rdi, rax
0x140027971  test    rax, rax
0x140027974  jz      loc_140027C0E
0x14002797a  mov     rcx, [rbx+38h]
0x14002797e  mov     [rax+38h], rcx
0x140027982  mov     rcx, [rbx+40h]
0x140027986  mov     [rax+40h], rcx
0x14002798a  mov     rcx, [rbx+48h]
0x14002798e  or      dword ptr [rdi+78h], 200000h
0x140027995  mov     [rax+48h], rcx
0x140027999  mov     rax, [rsp+58h+arg_0]
0x14002799e  mov     [rdi+28h], rax
0x1400279a2  xor     eax, eax
0x1400279a4  or      word ptr [rdi+20Ah], 1
0x1400279ac  mov     [rdi+238h], eax
0x1400279b2  mov     [rdi+228h], rax
0x1400279b9  mov     [rdi+0B8h], rax
0x1400279c0  mov     [rdi+210h], rax
0x1400279c7  mov     byte ptr [rdi+20h], 0Dh
0x1400279cb  mov     word ptr [rdi+208h], 6
0x1400279d4  mov     dword ptr [rdi+21Ch], 140078h
0x1400279de  mov     byte ptr [rdi+240h], 0
0x1400279e5  mov     dword ptr [rdi+23Ch], 220h
0x1400279ef  mov     [rdi+230h], r14
0x1400279f6  mov     rax, [rbx+50h]
0x1400279fa  mov     rcx, [rax+160h]
0x140027a01  mov     rax, [rcx+160h]
0x140027a08  mov     rcx, rdi
0x140027a0b  call    _guard_dispatch_icall
0x140027a10  mov     esi, eax
0x140027a12  cmp     eax, 103h
0x140027a17  jnz     short loc_140027A2E
0x140027a19  mov     rcx, rdi
0x140027a1c  call    cs:__imp_RxWaitSync
0x140027a23  nop     dword ptr [rax+rax+00h]
0x140027a28  mov     esi, [rdi+0B0h]
0x140027a2e  mov     qword ptr [rdi+28h], 0
0x140027a36  test    esi, esi
0x140027a38  jnz     short loc_140027A95
0x140027a3a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140027a41  lea     rax, WPP_GLOBAL_Control
0x140027a48  cmp     rcx, rax
0x140027a4b  jz      short loc_140027A95
0x140027a4d  mov     eax, [rcx+2Ch]
0x140027a50  test    al, 2
0x140027a52  jz      short loc_140027A95
0x140027a54  cmp     byte ptr [rcx+29h], 2
0x140027a58  jb      short loc_140027A95
0x140027a5a  mov     rax, [r14+10h]
0x140027a5e  lea     r8, WPP_f3cc199661c03597963a8c8eae40d83a_Traceguids
0x140027a65  mov     r9, [r14]
0x140027a68  mov     edx, 0Ah
0x140027a6d  mov     rcx, [rcx+18h]
0x140027a71  mov     [rsp+58h+var_30], rax
0x140027a76  mov     rax, [r14+8]
0x140027a7a  mov     [rsp+58h+pContext], rax
0x140027a7f  call    WPP_SF_iii
0x140027a84  mov     rcx, rdi; RxContext
0x140027a87  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140027a8e  nop     dword ptr [rax+rax+00h]
0x140027a93  jmp     short loc_140027AAC
0x140027a95  mov     rcx, rdi; RxContext
0x140027a98  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140027a9f  nop     dword ptr [rax+rax+00h]
0x140027aa4  test    esi, esi
0x140027aa6  js      loc_140027C0E
0x140027aac  movups  xmm0, xmmword ptr [r14]
0x140027ab0  lea     rcx, [rbx+180h]; Event
0x140027ab7  xor     r8d, r8d; State
0x140027aba  xor     edx, edx; Type
0x140027abc  movups  xmmword ptr [rbp+40h], xmm0
0x140027ac0  movsd   xmm1, qword ptr [r14+10h]
0x140027ac6  movsd   qword ptr [rbp+50h], xmm1
0x140027acb  mov     [r13+40h], rbp
0x140027acf  call    cs:__imp_KeInitializeEvent
0x140027ad6  nop     dword ptr [rax+rax+00h]
0x140027adb  mov     rcx, [rbx+50h]; pMRxDeviceObject
0x140027adf  lea     r8, [rbx+130h]; pWorkQueueItem
0x140027ae6  lea     r9, MrxSmbGetSrvHandle; Routine
0x140027aed  mov     [rbx+0D0h], rbp
0x140027af4  mov     edx, 1; WorkQueueType
0x140027af9  mov     [rsp+58h+pContext], rbx; pContext
0x140027afe  call    cs:__imp_RxPostToWorkerThread
0x140027b05  nop     dword ptr [rax+rax+00h]
0x140027b0a  mov     edi, eax
0x140027b0c  test    eax, eax
0x140027b0e  jnz     loc_140027BB8
0x140027b14  mov     rcx, rbx
0x140027b17  call    cs:__imp_RxWaitSync
0x140027b1e  nop     dword ptr [rax+rax+00h]
0x140027b23  mov     edi, [rbx+0D0h]
0x140027b29  test    edi, edi
0x140027b2b  jnz     loc_140027BB8
0x140027b31  or      dword ptr [r15+9Ch], 10000h
0x140027b3c  mov     rcx, r15
0x140027b3f  call    cs:__imp_RxDisableLocalBuffering
0x140027b46  nop     dword ptr [rax+rax+00h]
0x140027b4b  mov     rax, [r15+78h]
0x140027b4f  mov     rcx, rbx
0x140027b52  mov     rdx, [rax+28h]
0x140027b56  add     rdx, 178h
0x140027b5d  call    Smb2InvalidateFileInfoCacheEntry
0x140027b62  mov     rax, [r15+78h]
0x140027b66  xor     esi, esi
0x140027b68  mov     rdx, [rax+28h]
0x140027b6c  mov     rax, [rbx+38h]
0x140027b70  add     rdx, 458h
0x140027b77  mov     rcx, [rax+120h]
0x140027b7e  test    rcx, rcx
0x140027b81  jz      short loc_140027BA0
0x140027b83  mov     rcx, [rcx+88h]
0x140027b8a  test    rcx, rcx
0x140027b8d  jz      short loc_140027BA0
0x140027b8f  mov     rax, [rax+88h]
0x140027b96  nop
0x140027b97  mov     esi, [rcx+58h]
0x140027b9a  nop
0x140027b9b  nop
0x140027b9c  mov     eax, [rax+54h]
0x140027b9f  nop
0x140027ba0  mov     rcx, rbx
0x140027ba3  call    Smb2InvalidateSingleFileInDirInfoCache
0x140027ba8  mov     rax, [rbx+38h]
0x140027bac  mov     rcx, [rax+88h]
0x140027bb3  xchg    esi, [rcx+54h]
0x140027bb6  jmp     short loc_140027BD4
0x140027bb8  mov     edx, 6D536853h; Tag
0x140027bbd  mov     qword ptr [r13+40h], 0
0x140027bc5  mov     rcx, rbp; P
0x140027bc8  call    cs:__imp_ExFreePoolWithTag
0x140027bcf  nop     dword ptr [rax+rax+00h]
0x140027bd4  mov     edx, 6D536853h; Tag
0x140027bd9  mov     rcx, r14; P
0x140027bdc  call    cs:__imp_ExFreePoolWithTag
0x140027be3  nop     dword ptr [rax+rax+00h]
0x140027be8  mov     eax, edi
0x140027bea  mov     r12, [rsp+58h+var_20]
0x140027bef  mov     rdi, [rsp+58h+arg_18]
0x140027bf4  mov     r14, [rsp+58h+var_28]
0x140027bf9  mov     rsi, [rsp+58h+arg_10]
0x140027bfe  mov     rbp, [rsp+58h+arg_8]
0x140027c03  add     rsp, 40h
0x140027c07  pop     r15
0x140027c09  pop     r13
0x140027c0b  pop     rbx
0x140027c0c  retn
0x140027c0e  mov     edx, 6D536853h; Tag
0x140027c13  mov     rcx, r14; P
0x140027c16  call    cs:__imp_ExFreePoolWithTag
0x140027c1d  nop     dword ptr [rax+rax+00h]
0x140027c22  mov     edx, 6D536853h; Tag
0x140027c27  mov     rcx, rbp; P
0x140027c2a  call    cs:__imp_ExFreePoolWithTag
0x140027c31  nop     dword ptr [rax+rax+00h]
0x140027c36  mov     eax, esi
0x140027c38  jmp     short loc_140027BEA
0x140027c3a  mov     eax, 0C00000BBh
0x140027c3f  add     rsp, 40h
0x140027c43  pop     r15
0x140027c45  pop     r13
0x140027c47  pop     rbx
0x140027c48  retn
```
