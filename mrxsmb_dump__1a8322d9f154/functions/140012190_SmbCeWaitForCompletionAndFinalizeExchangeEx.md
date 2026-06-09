# SmbCeWaitForCompletionAndFinalizeExchangeEx

- ea: `0x140012190`
- end: `0x1400125d9`
- name: `SmbCeWaitForCompletionAndFinalizeExchangeEx`
- size: `1097`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x140006660`
- `0x140006680`
- `0x140009360`
- `0x1400093a0`
- `0x140009fc0`
- `0x14000c170`
- `0x14000c6a0`
- `0x14000d910`
- `0x14000df60`
- `0x140012190`
- `0x140014370`
- `0x1400149d0`
- `0x1400383d0`
- `0x14004a7d0`
- `0x140059dc0`
- `0x140059ea0`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012493`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012493`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001220b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012266`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400123e9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001220b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012266`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400123e9`
- `ntoskrnl!FsRtlCancellableWaitForMultipleObjects` at `0x140012241`
- `ntoskrnl!FsRtlCancellableWaitForMultipleObjects` at `0x140012241`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x140012288`
- `ntoskrnl!FsRtlCancellableWaitForSingleObject` at `0x140012288`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012505`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012505`
- `ntoskrnl!KeBugCheckEx` at `0x140012560`
- `ntoskrnl!KeBugCheckEx` at `0x140012560`
- `HAL!KeQueryPerformanceCounter` at `0x14001247d`
- `HAL!KeQueryPerformanceCounter` at `0x14001247d`
- `rdbss!RxCancelContext` at `0x1400123b0`
- `rdbss!RxCancelContext` at `0x1400123b0`
- `rdbss!RxPostToWorkerThread` at `0x1400125a7`
- `rdbss!RxPostToWorkerThread` at `0x1400125a7`

## pseudocode

```c
__int64 __fastcall SmbCeWaitForCompletionAndFinalizeExchangeEx(
        char *pContext,
        void *a2,
        void (__fastcall *a3)(__int64),
        __int64 a4)
{
  __int64 v4; // rbx
  __int64 v5; // rsi
  IRP *Irp; // rax
  __int64 v9; // rdx
  NTSTATUS v10; // ebp
  __int64 v11; // r8
  __int64 v12; // r9
  IRP *v13; // r8
  __int64 v14; // r15
  char v15; // r12
  bool v16; // cl
  char v17; // al
  __int64 v18; // rbx
  unsigned int v19; // r14d
  __int64 v20; // rbx
  struct _RDBSS_DEVICE_OBJECT *v21; // rbp
  __int64 v22; // rdx
  unsigned int v23; // esi
  __int64 v24; // rax
  __int64 (__fastcall *v25)(char *); // rax
  __int64 v26; // rax
  LARGE_INTEGER PerformanceCounter; // rbx
  KIRQL v28; // al
  int v29; // ecx
  __int64 v30; // r8
  void *v33; // [rsp+38h] [rbp-90h]
  PVOID ObjectArray[2]; // [rsp+40h] [rbp-88h] BYREF
  _OWORD v35[3]; // [rsp+50h] [rbp-78h] BYREF

  v4 = a4;
  v5 = *((_QWORD *)pContext + 6);
  v33 = a2;
  if ( (*((_DWORD *)pContext + 17) & 1) == 0 )
    __int2c();
  do
  {
    if ( a2 )
    {
      ObjectArray[1] = a2;
      ObjectArray[0] = pContext + 176;
      while ( 1 )
      {
        Irp = !v5 || KeGetCurrentIrql() ? 0LL : *(IRP **)(v5 + 40);
        v10 = FsRtlCancellableWaitForMultipleObjects(2u, ObjectArray, WaitAny, 0, 0, Irp);
        if ( v10 != 1 )
          break;
        a3(v4);
      }
    }
    else
    {
      if ( !v5 || KeGetCurrentIrql() )
        v13 = 0;
      else
        v13 = *(IRP **)(v5 + 40);
      v10 = FsRtlCancellableWaitForSingleObject(pContext + 176, 0, v13);
    }
    if ( v10 != -1073741536 && v10 != -1073741749 )
      goto LABEL_39;
    v14 = *((_QWORD *)pContext + 7);
    v15 = 1;
    v16 = v14 == 0;
    if ( v5 )
    {
      v17 = *(_BYTE *)(v5 + 32);
      if ( v17 )
      {
        if ( ((v17 - 2) & 0xEF) != 0 )
          goto LABEL_23;
        v15 = 0;
      }
      v16 = 0;
    }
LABEL_23:
    if ( v10 == -1073741749 && v16 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_d39beb3e593835eae73483c3886eb046_Traceguids, pContext);
      }
      if ( v14 )
      {
        SmbCeAcquireCompoundingKeyLock(v14, v9, v11, v12);
        memset(v35, 0, sizeof(v35));
        v18 = 0;
        v19 = SmbCepAbortCompoundedExchangesLite(v14, 3221225547LL, v35);
        if ( v19 )
        {
          do
          {
            SmbCepCompleteExchangeLite(*((_QWORD *)v35 + v18));
            v18 = (unsigned int)(v18 + 1);
          }
          while ( (unsigned int)v18 < v19 );
        }
        SmbCeReleaseCompoundingKeyLock(v14);
        v4 = a4;
      }
      else
      {
        SmbCeAcquireExchangeLock(pContext);
        if ( (unsigned __int8)SmbCepAbortExchangeLite(pContext, 3221225547LL) )
          SmbCepCompleteExchangeLiteEx(pContext, 0);
        SmbCeReleaseExchangeLock(pContext);
      }
    }
    if ( v15 && v5 )
      RxCancelContext(v5);
LABEL_39:
    a2 = v33;
  }
  while ( v10 );
  v20 = *((_QWORD *)pContext + 9);
  v21 = *(struct _RDBSS_DEVICE_OBJECT **)(v20 + 24);
  if ( KeGetCurrentIrql() >= 2u )
  {
    v23 = 0;
    if ( (*((_DWORD *)pContext + 17) & 0x40000) == 0 )
      goto LABEL_58;
  }
  if ( (v24 = *(_QWORD *)(v20 + 56)) != 0
    && (v25 = *(__int64 (__fastcall **)(char *))(v24 + 912)) != 0
    && (v23 = v25(pContext), v23 == -1069481981)
    || (v26 = *((_QWORD *)pContext + 29),
        *((_QWORD *)pContext + 26) = 0,
        *((_DWORD *)pContext + 10) = 8,
        v23 = (*(__int64 (__fastcall **)(char *))(v26 + 32))(pContext),
        v23 == -1069481981) )
  {
LABEL_58:
    if ( (*((_DWORD *)pContext + 17) & 1) != 0 )
      KeBugCheckEx(0x27u, 0x43584D5Fu, (ULONG_PTR)pContext, (int)v23, 0);
    LOBYTE(v22) = 20;
    RDR_PERF_ENTER(pContext + 512, v22);
    SmbCeIncrementTeardownOpCounter(v21, pContext, 7);
    RxPostToWorkerThread(
      v21,
      NormalWorkQueue,
      (PRX_WORK_QUEUE_ITEM)pContext + 6,
      SmbCepFinalizeExchangeWorker,
      pContext);
    return 259;
  }
  else
  {
    if ( byte_14007D25F && pContext[1011] == 1 )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v28 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)pContext + 114);
      v29 = (unsigned __int8)pContext[1014];
      if ( (unsigned __int8)v29 < 0x2Au )
      {
        v30 = *((_QWORD *)pContext + 110);
        if ( PerformanceCounter.QuadPart > v30 )
          _InterlockedAdd64(
            (volatile signed __int64 *)&pContext[8 * (unsigned __int8)pContext[1014] + 528],
            PerformanceCounter.QuadPart - v30);
        _InterlockedIncrement16((volatile signed __int16 *)&pContext[2 * v29 + 924]);
      }
      pContext[1014] = -1;
      if ( *((_WORD *)pContext + 504) == 0xE300 )
        PerformanceCounter.QuadPart -= *((_QWORD *)pContext + 88);
      *((_QWORD *)pContext + 108) = PerformanceCounter.QuadPart - *((_QWORD *)pContext + 109);
      KeReleaseSpinLock((PKSPIN_LOCK)pContext + 114, v28);
    }
    RDR_PERF_OUTPUT_ETW(pContext + 512);
    if ( pContext[1011] == 1 )
      memset(pContext + 512, 0, 0x1F8u);
    SmbCeDereferenceExchange((unsigned __int64)pContext);
  }
  return v23;
}

```

## disassembly

```asm
0x140012190  push    rbx
0x140012192  push    rbp
0x140012193  push    rsi
0x140012194  push    rdi
0x140012195  push    r14
0x140012197  sub     rsp, 0A0h
0x14001219e  mov     rax, cs:__security_cookie
0x1400121a5  xor     rax, rsp
0x1400121a8  mov     [rsp+0C8h+var_48], rax
0x1400121b0  mov     eax, [rcx+44h]
0x1400121b3  mov     rbx, r9
0x1400121b6  mov     rsi, [rcx+30h]
0x1400121ba  mov     rdi, rcx
0x1400121bd  mov     [rsp+0C8h+var_30], r13
0x1400121c5  mov     r13, r8
0x1400121c8  mov     [rsp+0C8h+var_98], rbx
0x1400121cd  mov     [rsp+0C8h+var_90], rdx
0x1400121d2  test    al, 1
0x1400121d4  jnz     short loc_1400121D8
0x1400121d6  int     2Ch; Windows NT - assertion failure
0x1400121d8  mov     [rsp+0C8h+arg_8], r12
0x1400121e0  xor     r14d, r14d
0x1400121e3  mov     [rsp+0C8h+var_38], r15
0x1400121eb  nop     dword ptr [rax+rax+00h]
0x1400121f0  test    rdx, rdx
0x1400121f3  jz      short loc_140012261
0x1400121f5  lea     rax, [rdi+0B0h]
0x1400121fc  mov     [rsp+0C8h+var_80], rdx
0x140012201  mov     [rsp+0C8h+ObjectArray], rax
0x140012206  test    rsi, rsi
0x140012209  jz      short loc_140012221
0x14001220b  call    cs:__imp_KeGetCurrentIrql
0x140012212  nop     dword ptr [rax+rax+00h]
0x140012217  cmp     al, 1
0x140012219  jnb     short loc_140012221
0x14001221b  mov     rax, [rsi+28h]
0x14001221f  jmp     short loc_140012224
0x140012221  mov     rax, r14
0x140012224  mov     [rsp+0C8h+Irp], rax; Irp
0x140012229  lea     rdx, [rsp+0C8h+ObjectArray]; ObjectArray
0x14001222e  xor     r9d, r9d; Timeout
0x140012231  mov     [rsp+0C8h+WaitBlockArray], r14; WaitBlockArray
0x140012236  mov     r8d, 1; WaitType
0x14001223c  mov     ecx, 2; Count
0x140012241  call    cs:__imp_FsRtlCancellableWaitForMultipleObjects
0x140012248  nop     dword ptr [rax+rax+00h]
0x14001224d  mov     ebp, eax
0x14001224f  cmp     eax, 1
0x140012252  jnz     short loc_140012296
0x140012254  mov     rcx, rbx
0x140012257  mov     rax, r13
0x14001225a  call    _guard_dispatch_icall
0x14001225f  jmp     short loc_140012206
0x140012261  test    rsi, rsi
0x140012264  jz      short loc_14001227C
0x140012266  call    cs:__imp_KeGetCurrentIrql
0x14001226d  nop     dword ptr [rax+rax+00h]
0x140012272  cmp     al, 1
0x140012274  jnb     short loc_14001227C
0x140012276  mov     r8, [rsi+28h]
0x14001227a  jmp     short loc_14001227F
0x14001227c  mov     r8, r14; Irp
0x14001227f  lea     rcx, [rdi+0B0h]; Object
0x140012286  xor     edx, edx; Timeout
0x140012288  call    cs:__imp_FsRtlCancellableWaitForSingleObject
0x14001228f  nop     dword ptr [rax+rax+00h]
0x140012294  mov     ebp, eax
0x140012296  cmp     ebp, 0C0000120h
0x14001229c  jz      short loc_1400122AA
0x14001229e  cmp     ebp, 0C000004Bh
0x1400122a4  jnz     loc_1400123BC
0x1400122aa  mov     r15, [rdi+38h]
0x1400122ae  mov     r12b, 1
0x1400122b1  test    r15, r15
0x1400122b4  setz    cl
0x1400122b7  test    rsi, rsi
0x1400122ba  jz      short loc_1400122CF
0x1400122bc  movzx   eax, byte ptr [rsi+20h]
0x1400122c0  test    al, al
0x1400122c2  jz      short loc_1400122CD
0x1400122c4  sub     al, 2
0x1400122c6  test    al, 0EFh
0x1400122c8  jnz     short loc_1400122CF
0x1400122ca  xor     r12b, r12b
0x1400122cd  xor     cl, cl
0x1400122cf  cmp     ebp, 0C000004Bh
0x1400122d5  jnz     loc_1400123A3
0x1400122db  test    cl, cl
0x1400122dd  jz      loc_1400123A3
0x1400122e3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400122ea  lea     rax, WPP_GLOBAL_Control
0x1400122f1  cmp     rcx, rax
0x1400122f4  jz      short loc_14001231B
0x1400122f6  mov     eax, [rcx+2Ch]
0x1400122f9  test    al, 1
0x1400122fb  jz      short loc_14001231B
0x1400122fd  cmp     byte ptr [rcx+29h], 1
0x140012301  jb      short loc_14001231B
0x140012303  mov     rcx, [rcx+18h]
0x140012307  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x14001230e  mov     edx, 20h ; ' '
0x140012313  mov     r9, rdi
0x140012316  call    WPP_SF_q
0x14001231b  test    r15, r15
0x14001231e  jz      short loc_140012378
0x140012320  mov     rcx, r15
0x140012323  call    SmbCeAcquireCompoundingKeyLock
0x140012328  xorps   xmm0, xmm0
0x14001232b  lea     r8, [rsp+0C8h+var_78]
0x140012330  mov     edx, 0C000004Bh
0x140012335  mov     rcx, r15
0x140012338  movups  [rsp+0C8h+var_78], xmm0
0x14001233d  movups  [rsp+0C8h+var_68], xmm0
0x140012342  movups  [rsp+0C8h+var_58], xmm0
0x140012347  call    SmbCepAbortCompoundedExchangesLite
0x14001234c  xor     ebx, ebx
0x14001234e  mov     r14d, eax
0x140012351  test    eax, eax
0x140012353  jz      short loc_140012366
0x140012355  mov     rcx, qword ptr [rsp+rbx*8+0C8h+var_78]
0x14001235a  call    SmbCepCompleteExchangeLite
0x14001235f  inc     ebx
0x140012361  cmp     ebx, r14d
0x140012364  jb      short loc_140012355
0x140012366  mov     rcx, r15
0x140012369  call    SmbCeReleaseCompoundingKeyLock
0x14001236e  mov     rbx, [rsp+0C8h+var_98]
0x140012373  xor     r14d, r14d
0x140012376  jmp     short loc_1400123A3
0x140012378  mov     rcx, rdi
0x14001237b  call    SmbCeAcquireExchangeLock
0x140012380  mov     edx, 0C000004Bh
0x140012385  mov     rcx, rdi
0x140012388  call    SmbCepAbortExchangeLite
0x14001238d  test    al, al
0x14001238f  jz      short loc_14001239B
0x140012391  xor     edx, edx
0x140012393  mov     rcx, rdi; pContext
0x140012396  call    SmbCepCompleteExchangeLiteEx
0x14001239b  mov     rcx, rdi
0x14001239e  call    SmbCeReleaseExchangeLock
0x1400123a3  test    r12b, r12b
0x1400123a6  jz      short loc_1400123BC
0x1400123a8  test    rsi, rsi
0x1400123ab  jz      short loc_1400123BC
0x1400123ad  mov     rcx, rsi
0x1400123b0  call    cs:__imp_RxCancelContext
0x1400123b7  nop     dword ptr [rax+rax+00h]
0x1400123bc  mov     rdx, [rsp+0C8h+var_90]
0x1400123c1  test    ebp, ebp
0x1400123c3  jnz     loc_1400121F0
0x1400123c9  mov     rbx, [rdi+48h]
0x1400123cd  mov     r15, [rsp+0C8h+var_38]
0x1400123d5  mov     r13, [rsp+0C8h+var_30]
0x1400123dd  mov     r12, [rsp+0C8h+arg_8]
0x1400123e5  mov     rbp, [rbx+18h]
0x1400123e9  call    cs:__imp_KeGetCurrentIrql
0x1400123f0  nop     dword ptr [rax+rax+00h]
0x1400123f5  cmp     al, 2
0x1400123f7  jb      short loc_140012409
0x1400123f9  mov     eax, [rdi+44h]
0x1400123fc  mov     esi, r14d
0x1400123ff  bt      eax, 12h
0x140012403  jnb     loc_140012544
0x140012409  mov     rax, [rbx+38h]
0x14001240d  test    rax, rax
0x140012410  jz      short loc_140012433
0x140012412  mov     rax, [rax+390h]
0x140012419  test    rax, rax
0x14001241c  jz      short loc_140012433
0x14001241e  mov     rcx, rdi
0x140012421  call    _guard_dispatch_icall
0x140012426  mov     esi, eax
0x140012428  cmp     eax, 0C0410003h
0x14001242d  jz      loc_140012544
0x140012433  mov     rax, [rdi+0E8h]
0x14001243a  mov     rcx, rdi
0x14001243d  mov     [rdi+0D0h], r14
0x140012444  mov     dword ptr [rdi+28h], 8
0x14001244b  mov     rax, [rax+20h]
0x14001244f  call    _guard_dispatch_icall
0x140012454  mov     esi, eax
0x140012456  cmp     eax, 0C0410003h
0x14001245b  jz      loc_140012544
0x140012461  cmp     cs:byte_14007D25F, 0
0x140012468  jz      loc_140012511
0x14001246e  cmp     byte ptr [rdi+3F3h], 1
0x140012475  jnz     loc_140012511
0x14001247b  xor     ecx, ecx; PerformanceFrequency
0x14001247d  call    cs:__imp_KeQueryPerformanceCounter
0x140012484  nop     dword ptr [rax+rax+00h]
0x140012489  lea     rcx, [rdi+390h]; SpinLock
0x140012490  mov     rbx, rax
0x140012493  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001249a  nop     dword ptr [rax+rax+00h]
0x14001249f  movzx   ecx, byte ptr [rdi+3F6h]
0x1400124a6  cmp     cl, 2Ah ; '*'
0x1400124a9  jnb     short loc_1400124D1
0x1400124ab  mov     r8, [rdi+370h]
0x1400124b2  mov     edx, ecx
0x1400124b4  cmp     rbx, r8
0x1400124b7  jle     short loc_1400124C8
0x1400124b9  mov     rcx, rbx
0x1400124bc  sub     rcx, r8
0x1400124bf  lock add [rdi+rdx*8+210h], rcx
0x1400124c8  lock inc word ptr [rdi+rdx*2+39Ch]
0x1400124d1  mov     ecx, 0E300h
0x1400124d6  mov     byte ptr [rdi+3F6h], 0FFh
0x1400124dd  cmp     [rdi+3F0h], cx
0x1400124e4  jnz     short loc_1400124ED
0x1400124e6  sub     rbx, [rdi+2C0h]
0x1400124ed  sub     rbx, [rdi+368h]
0x1400124f4  lea     rcx, [rdi+390h]; SpinLock
0x1400124fb  movzx   edx, al; NewIrql
0x1400124fe  mov     [rdi+360h], rbx
0x140012505  call    cs:__imp_KeReleaseSpinLock
0x14001250c  nop     dword ptr [rax+rax+00h]
0x140012511  lea     rcx, [rdi+200h]
0x140012518  call    RDR_PERF_OUTPUT_ETW
0x14001251d  cmp     byte ptr [rdi+3F3h], 1
0x140012524  jnz     short loc_14001253A
0x140012526  xor     edx, edx; Val
0x140012528  lea     rcx, [rdi+200h]; void *
0x14001252f  mov     r8d, 1F8h; Size
0x140012535  call    memset
0x14001253a  mov     rcx, rdi; pContext
0x14001253d  call    SmbCeDereferenceExchange
0x140012542  jmp     short loc_1400125B8
0x140012544  mov     eax, [rdi+44h]
0x140012547  test    al, 1
0x140012549  jz      short loc_14001256D
0x14001254b  movsxd  r9, esi; BugCheckParameter3
0x14001254e  mov     r8, rdi; BugCheckParameter2
0x140012551  mov     edx, 43584D5Fh; BugCheckParameter1
0x140012556  mov     [rsp+0C8h+WaitBlockArray], r14; BugCheckParameter4
0x14001255b  mov     ecx, 27h ; '''; BugCheckCode
0x140012560  call    cs:__imp_KeBugCheckEx
0x14001256d  lea     rcx, [rdi+200h]
0x140012574  mov     dl, 14h
0x140012576  call    RDR_PERF_ENTER
0x14001257b  mov     r8d, 7
0x140012581  mov     rdx, rdi
0x140012584  mov     rcx, rbp
0x140012587  call    SmbCeIncrementTeardownOpCounter
0x14001258c  lea     r8, [rdi+0F0h]; pWorkQueueItem
0x140012593  mov     [rsp+0C8h+WaitBlockArray], rdi; pContext
0x140012598  lea     r9, SmbCepFinalizeExchangeWorker; Routine
0x14001259f  mov     edx, 3; WorkQueueType
0x1400125a4  mov     rcx, rbp; pMRxDeviceObject
0x1400125a7  call    cs:__imp_RxPostToWorkerThread
0x1400125ae  nop     dword ptr [rax+rax+00h]
0x1400125b3  mov     esi, 103h
0x1400125b8  mov     eax, esi
0x1400125ba  mov     rcx, [rsp+0C8h+var_48]
0x1400125c2  xor     rcx, rsp; StackCookie
0x1400125c5  call    __security_check_cookie
0x1400125ca  add     rsp, 0A0h
0x1400125d1  pop     r14
0x1400125d3  pop     rdi
0x1400125d4  pop     rsi
0x1400125d5  pop     rbp
0x1400125d6  pop     rbx
0x1400125d7  retn
```
