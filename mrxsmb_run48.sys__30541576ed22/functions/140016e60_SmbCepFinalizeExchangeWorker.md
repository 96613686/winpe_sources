# SmbCepFinalizeExchangeWorker

- ea: `0x140016e60`
- end: `0x140017137`
- name: `SmbCepFinalizeExchangeWorker`
- size: `727`
- prototype: `void __stdcall(PVOID Context)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140004938`
- `0x1400093a0`
- `0x140009fc0`
- `0x14000d910`
- `0x140014370`
- `0x1400148f0`
- `0x1400149d0`
- `0x140016e60`
- `0x14001c0f0`
- `0x140037fa4`
- `0x140059ea0`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016e87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016ef7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016f6a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016e87`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016ef7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140016f6a`
- `ntoskrnl!KeGetCurrentIrql` at `0x140016ff6`
- `ntoskrnl!KeGetCurrentIrql` at `0x140016ff6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016f1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016fc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016f1d`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016fc4`
- `ntoskrnl!KeBugCheckEx` at `0x1400170c2`
- `ntoskrnl!KeBugCheckEx` at `0x1400170c2`
- `HAL!KeQueryPerformanceCounter` at `0x140016f54`
- `HAL!KeQueryPerformanceCounter` at `0x140016f54`
- `rdbss!RxPostToWorkerThread` at `0x14001710e`
- `rdbss!RxPostToWorkerThread` at `0x14001710e`

## pseudocode

```c
void __fastcall SmbCepFinalizeExchangeWorker(char *Context)
{
  __int64 v2; // rbx
  __int64 v3; // r14
  KSPIN_LOCK *v4; // rbx
  signed __int32 v5; // r8d
  __int64 v6; // rcx
  char *v7; // rsi
  LARGE_INTEGER PerformanceCounter; // rbx
  KIRQL v9; // al
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rbx
  struct _RDBSS_DEVICE_OBJECT *v14; // rsi
  __int64 v15; // rdx
  int v16; // ecx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(char *); // rax
  __int64 v19; // rax

  v2 = *((_QWORD *)Context + 7);
  v3 = *(_QWORD *)(*((_QWORD *)Context + 9) + 24LL);
  if ( v2 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 4));
    *(_BYTE *)(v2 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 8));
    v4 = (KSPIN_LOCK *)(Context + 24);
  }
  else
  {
    v5 = _InterlockedIncrement((volatile signed __int32 *)Context + 1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        &WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
        Context,
        v5 - 1,
        v5);
    }
    v4 = (KSPIN_LOCK *)(Context + 24);
    Context[32] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 3);
  }
  v6 = *((_QWORD *)Context + 7);
  if ( v6 )
  {
    SmbCeReleaseCompoundingKeyLock(v6);
  }
  else
  {
    KeReleaseSpinLock(v4, Context[32]);
    SmbCeDereferenceExchange((unsigned __int64)Context);
  }
  if ( byte_14007D25F )
  {
    v7 = Context + 512;
    if ( Context[1011] == 1 )
    {
      PerformanceCounter = KeQueryPerformanceCounter(0);
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 114);
      v10 = (unsigned __int8)Context[1014];
      if ( (unsigned __int8)v10 < 0x2Au && (_BYTE)v10 != 21 )
      {
        v11 = *((_QWORD *)Context + 110);
        if ( PerformanceCounter.QuadPart > v11 )
          _InterlockedAdd64((volatile signed __int64 *)&v7[8 * v10 + 16], PerformanceCounter.QuadPart - v11);
        _InterlockedIncrement16((volatile signed __int16 *)&v7[2 * v10 + 412]);
      }
      Context[1014] = 21;
      *((LARGE_INTEGER *)Context + 110) = PerformanceCounter;
      KeReleaseSpinLock((PKSPIN_LOCK)Context + 114, v9);
      if ( byte_1400712C4 < 0 )
        McTemplateK0t_EtwWriteTransfer(v12, &Smb2PerfWorkTransition, Context + 512, 21);
    }
  }
  v13 = *((_QWORD *)Context + 9);
  v14 = *(struct _RDBSS_DEVICE_OBJECT **)(v13 + 24);
  if ( KeGetCurrentIrql() >= 2u )
  {
    v16 = 0;
    if ( (*((_DWORD *)Context + 17) & 0x40000) == 0 )
      goto LABEL_29;
  }
  if ( (v17 = *(_QWORD *)(v13 + 56)) != 0
    && (v18 = *(__int64 (__fastcall **)(char *))(v17 + 912)) != 0
    && (v16 = v18(Context), v16 == -1069481981)
    || (v19 = *((_QWORD *)Context + 29),
        *((_QWORD *)Context + 26) = 0,
        *((_DWORD *)Context + 10) = 8,
        v16 = (*(__int64 (__fastcall **)(char *))(v19 + 32))(Context),
        v16 == -1069481981) )
  {
LABEL_29:
    if ( (*((_DWORD *)Context + 17) & 1) != 0 )
      KeBugCheckEx(0x27u, 0x43584D5Fu, (ULONG_PTR)Context, v16, 0);
    LOBYTE(v15) = 20;
    RDR_PERF_ENTER(Context + 512, v15);
    SmbCeIncrementTeardownOpCounter(v14, Context, 7);
    RxPostToWorkerThread(v14, NormalWorkQueue, (PRX_WORK_QUEUE_ITEM)Context + 6, SmbCepFinalizeExchangeWorker, Context);
  }
  else
  {
    RDR_PERF_EXIT(Context + 512);
    RDR_PERF_OUTPUT_ETW(Context + 512);
    if ( Context[1011] == 1 )
      memset(Context + 512, 0, 0x1F8u);
    SmbCeDereferenceExchange((unsigned __int64)Context);
  }
  SmbCeDecrementTeardownOpCounterAndUnblockWaiters(v3, Context, 7);
}

```

## disassembly

```asm
0x140016e60  push    rbx
0x140016e62  push    rbp
0x140016e63  push    rsi
0x140016e64  push    rdi
0x140016e65  push    r14
0x140016e67  sub     rsp, 30h
0x140016e6b  mov     rax, [rcx+48h]
0x140016e6f  mov     rdi, rcx
0x140016e72  mov     rbx, [rcx+38h]
0x140016e76  mov     r14, [rax+18h]
0x140016e7a  test    rbx, rbx
0x140016e7d  jz      short loc_140016E9C
0x140016e7f  lock inc dword ptr [rbx+4]
0x140016e83  lea     rcx, [rbx+8]; SpinLock
0x140016e87  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016e8e  nop     dword ptr [rax+rax+00h]
0x140016e93  mov     [rbx+10h], al
0x140016e96  lea     rbx, [rdi+18h]
0x140016e9a  jmp     short loc_140016F06
0x140016e9c  mov     r8d, 1
0x140016ea2  lock xadd [rcx+4], r8d
0x140016ea8  inc     r8d
0x140016eab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140016eb2  lea     rax, WPP_GLOBAL_Control
0x140016eb9  cmp     rcx, rax
0x140016ebc  jz      short loc_140016EF0
0x140016ebe  mov     eax, [rcx+2Ch]
0x140016ec1  test    al, 10h
0x140016ec3  jz      short loc_140016EF0
0x140016ec5  cmp     byte ptr [rcx+29h], 4
0x140016ec9  jb      short loc_140016EF0
0x140016ecb  mov     rcx, [rcx+18h]
0x140016ecf  lea     eax, [r8-1]
0x140016ed3  mov     [rsp+58h+var_30], r8d
0x140016ed8  mov     edx, 21h ; '!'
0x140016edd  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x140016ee4  mov     dword ptr [rsp+58h+BugCheckParameter4], eax
0x140016ee8  mov     r9, rdi
0x140016eeb  call    WPP_SF_qDD
0x140016ef0  lea     rbx, [rdi+18h]
0x140016ef4  mov     rcx, rbx; SpinLock
0x140016ef7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016efe  nop     dword ptr [rax+rax+00h]
0x140016f03  mov     [rdi+20h], al
0x140016f06  mov     rcx, [rdi+38h]
0x140016f0a  test    rcx, rcx
0x140016f0d  jz      short loc_140016F16
0x140016f0f  call    SmbCeReleaseCompoundingKeyLock
0x140016f14  jmp     short loc_140016F31
0x140016f16  movzx   edx, byte ptr [rdi+20h]; NewIrql
0x140016f1a  mov     rcx, rbx; SpinLock
0x140016f1d  call    cs:__imp_KeReleaseSpinLock
0x140016f24  nop     dword ptr [rax+rax+00h]
0x140016f29  mov     rcx, rdi; pContext
0x140016f2c  call    SmbCeDereferenceExchange
0x140016f31  cmp     cs:byte_14007D25F, 0
0x140016f38  jz      loc_140016FEE
0x140016f3e  cmp     byte ptr [rdi+3F3h], 1
0x140016f45  lea     rsi, [rdi+200h]
0x140016f4c  jnz     loc_140016FEE
0x140016f52  xor     ecx, ecx; PerformanceFrequency
0x140016f54  call    cs:__imp_KeQueryPerformanceCounter
0x140016f5b  nop     dword ptr [rax+rax+00h]
0x140016f60  lea     rcx, [rsi+190h]; SpinLock
0x140016f67  mov     rbx, rax
0x140016f6a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016f71  nop     dword ptr [rax+rax+00h]
0x140016f76  movzx   r9d, byte ptr [rsi+1F6h]
0x140016f7e  cmp     r9b, 2Ah ; '*'
0x140016f82  jnb     short loc_140016FAC
0x140016f84  cmp     r9b, 15h
0x140016f88  jz      short loc_140016FAC
0x140016f8a  mov     rdx, [rsi+170h]
0x140016f91  cmp     rbx, rdx
0x140016f94  jle     short loc_140016FA2
0x140016f96  mov     r8, rbx
0x140016f99  sub     r8, rdx
0x140016f9c  lock add [rsi+r9*8+10h], r8
0x140016fa2  lock inc word ptr [rsi+r9*2+19Ch]
0x140016fac  movzx   edx, al; NewIrql
0x140016faf  mov     byte ptr [rsi+1F6h], 15h
0x140016fb6  lea     rcx, [rsi+190h]; SpinLock
0x140016fbd  mov     [rsi+170h], rbx
0x140016fc4  call    cs:__imp_KeReleaseSpinLock
0x140016fcb  nop     dword ptr [rax+rax+00h]
0x140016fd0  cmp     cs:byte_1400712C4, 0
0x140016fd7  jge     short loc_140016FEE
0x140016fd9  mov     r9d, 15h
0x140016fdf  lea     rdx, Smb2PerfWorkTransition
0x140016fe6  mov     r8, rsi
0x140016fe9  call    McTemplateK0t_EtwWriteTransfer
0x140016fee  mov     rbx, [rdi+48h]
0x140016ff2  mov     rsi, [rbx+18h]
0x140016ff6  call    cs:__imp_KeGetCurrentIrql
0x140016ffd  nop     dword ptr [rax+rax+00h]
0x140017002  xor     ebp, ebp
0x140017004  cmp     al, 2
0x140017006  jb      short loc_140017017
0x140017008  mov     eax, [rdi+44h]
0x14001700b  mov     ecx, ebp
0x14001700d  bt      eax, 12h
0x140017011  jnb     loc_1400170A6
0x140017017  mov     rax, [rbx+38h]
0x14001701b  test    rax, rax
0x14001701e  jz      short loc_14001703D
0x140017020  mov     rax, [rax+390h]
0x140017027  test    rax, rax
0x14001702a  jz      short loc_14001703D
0x14001702c  mov     rcx, rdi
0x14001702f  call    _guard_dispatch_icall
0x140017034  mov     ecx, eax
0x140017036  cmp     eax, 0C0410003h
0x14001703b  jz      short loc_1400170A6
0x14001703d  mov     rax, [rdi+0E8h]
0x140017044  mov     rcx, rdi
0x140017047  mov     [rdi+0D0h], rbp
0x14001704e  mov     dword ptr [rdi+28h], 8
0x140017055  mov     rax, [rax+20h]
0x140017059  call    _guard_dispatch_icall
0x14001705e  mov     ecx, eax
0x140017060  cmp     eax, 0C0410003h
0x140017065  jz      short loc_1400170A6
0x140017067  lea     rcx, [rdi+200h]
0x14001706e  call    RDR_PERF_EXIT
0x140017073  lea     rcx, [rdi+200h]
0x14001707a  call    RDR_PERF_OUTPUT_ETW
0x14001707f  cmp     byte ptr [rdi+3F3h], 1
0x140017086  jnz     short loc_14001709C
0x140017088  xor     edx, edx; Val
0x14001708a  lea     rcx, [rdi+200h]; void *
0x140017091  mov     r8d, 1F8h; Size
0x140017097  call    memset
0x14001709c  mov     rcx, rdi; pContext
0x14001709f  call    SmbCeDereferenceExchange
0x1400170a4  jmp     short loc_14001711A
0x1400170a6  mov     eax, [rdi+44h]
0x1400170a9  test    al, 1
0x1400170ab  jz      short loc_1400170CF
0x1400170ad  movsxd  r9, ecx; BugCheckParameter3
0x1400170b0  mov     r8, rdi; BugCheckParameter2
0x1400170b3  mov     ecx, 27h ; '''; BugCheckCode
0x1400170b8  mov     [rsp+58h+BugCheckParameter4], rbp; BugCheckParameter4
0x1400170bd  mov     edx, 43584D5Fh; BugCheckParameter1
0x1400170c2  call    cs:__imp_KeBugCheckEx
0x1400170cf  lea     rcx, [rdi+200h]
0x1400170d6  mov     dl, 14h
0x1400170d8  call    RDR_PERF_ENTER
0x1400170dd  mov     r9, [rsp+58h]
0x1400170e2  mov     r8d, 7
0x1400170e8  mov     rdx, rdi
0x1400170eb  mov     rcx, rsi
0x1400170ee  call    SmbCeIncrementTeardownOpCounter
0x1400170f3  lea     r8, [rdi+0F0h]; pWorkQueueItem
0x1400170fa  mov     [rsp+58h+BugCheckParameter4], rdi; pContext
0x1400170ff  lea     r9, SmbCepFinalizeExchangeWorker; Routine
0x140017106  mov     edx, 3; WorkQueueType
0x14001710b  mov     rcx, rsi; pMRxDeviceObject
0x14001710e  call    cs:__imp_RxPostToWorkerThread
0x140017115  nop     dword ptr [rax+rax+00h]
0x14001711a  mov     r8d, 7
0x140017120  mov     rdx, rdi
0x140017123  mov     rcx, r14
0x140017126  call    SmbCeDecrementTeardownOpCounterAndUnblockWaiters
0x14001712b  add     rsp, 30h
0x14001712f  pop     r14
0x140017131  pop     rdi
0x140017132  pop     rsi
0x140017133  pop     rbp
0x140017134  pop     rbx
0x140017135  retn
```
