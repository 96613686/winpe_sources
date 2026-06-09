# SmbCeMemoryDeregisterCompleteInd

- ea: `0x140013cb0`
- end: `0x140013eec`
- name: `SmbCeMemoryDeregisterCompleteInd`
- size: `572`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x140006680`
- `0x140009360`
- `0x1400093a0`
- `0x140009fc0`
- `0x14000c030`
- `0x14000c6a0`
- `0x14000d910`
- `0x14000df60`
- `0x14000df90`
- `0x140013cb0`
- `0x140014370`
- `0x1400147b0`
- `0x1400148f0`
- `0x1400149d0`
- `0x14003e14c`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140013dbe`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013dbe`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140013d0f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140013d0f`
- `ntoskrnl!IofCompleteRequest` at `0x140013ed2`
- `ntoskrnl!IofCompleteRequest` at `0x140013ed2`
- `ntoskrnl!KeBugCheckEx` at `0x140013e75`
- `ntoskrnl!KeBugCheckEx` at `0x140013e75`
- `rdbss!RxCeUntrackTransportOpEx` at `0x140013d4c`
- `rdbss!RxCeUntrackTransportOpEx` at `0x140013d4c`
- `rdbss!RxPostToWorkerThread` at `0x140013ebc`
- `rdbss!RxPostToWorkerThread` at `0x140013ebc`

## pseudocode

```c
void __fastcall SmbCeMemoryDeregisterCompleteInd(unsigned int a1, __int64 a2)
{
  ULONG_PTR v2; // rdi
  __int64 v5; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  bool v9; // bp
  char *v10; // rdx
  IRP *v11; // rsi
  __int64 v12; // rbx
  struct _RDBSS_DEVICE_OBJECT *v13; // rbp
  __int64 v14; // rdx
  int v15; // ecx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(ULONG_PTR); // rax
  __int64 v18; // rax

  v2 = *(_QWORD *)(a2 + 56);
  v5 = *(_QWORD *)(v2 + 56);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a2, a1);
  }
  if ( (PIRP)v2 == IoGetTopLevelIrp() )
  {
    v9 = 1;
  }
  else
  {
    v9 = 0;
    if ( v5 )
      SmbCeAcquireCompoundingKeyLock(v5, v6, v7, v8);
    else
      SmbCeAcquireExchangeLock(v2);
  }
  --*(_BYTE *)(a2 + 87);
  RxCeUntrackTransportOpEx(a2 + 528, a1);
  if ( !v9 )
  {
    if ( (unsigned __int8)SmbCepCheckExchangeForDeferredAbortOrIfFinalizable(v2) )
    {
      v11 = (IRP *)SmbCepTryTurboCompleteExchangeLite(v2);
      if ( !v11 )
      {
        LOBYTE(v10) = v5 == 0;
        v9 = (unsigned int)SmbCepCompleteExchangeLiteEx((char *)v2, v10) == -1073741802;
      }
    }
    else
    {
      v11 = 0;
    }
    if ( v5 )
      SmbCeReleaseCompoundingKeyLock(v5);
    else
      SmbCeReleaseExchangeLock((PVOID)v2);
    if ( v9 )
    {
      v12 = *(_QWORD *)(v2 + 72);
      v13 = *(struct _RDBSS_DEVICE_OBJECT **)(v12 + 24);
      if ( KeGetCurrentIrql() >= 2u )
      {
        v15 = 0;
        if ( (*(_DWORD *)(v2 + 68) & 0x40000) == 0 )
          goto LABEL_26;
      }
      if ( (v16 = *(_QWORD *)(v12 + 56)) != 0
        && (v17 = *(__int64 (__fastcall **)(ULONG_PTR))(v16 + 912)) != 0
        && (v15 = v17(v2), v15 == -1069481981)
        || (v18 = *(_QWORD *)(v2 + 232),
            *(_QWORD *)(v2 + 208) = 0,
            *(_DWORD *)(v2 + 40) = 8,
            v15 = (*(__int64 (__fastcall **)(ULONG_PTR))(v18 + 32))(v2),
            v15 == -1069481981) )
      {
LABEL_26:
        if ( (*(_DWORD *)(v2 + 68) & 1) != 0 )
          KeBugCheckEx(0x27u, 0x43584D5Fu, v2, v15, 0);
        LOBYTE(v14) = 20;
        RDR_PERF_ENTER(v2 + 512, v14);
        SmbCeIncrementTeardownOpCounter(v13, v2, 7);
        RxPostToWorkerThread(
          v13,
          NormalWorkQueue,
          (PRX_WORK_QUEUE_ITEM)(v2 + 240),
          SmbCepFinalizeExchangeWorker,
          (PVOID)v2);
      }
      else
      {
        RDR_PERF_EXIT(v2 + 512);
        RDR_PERF_OUTPUT_ETW(v2 + 512);
        RDR_PERF_FREE(v2 + 512);
        SmbCeDereferenceExchange(v2);
      }
    }
    if ( v11 )
      IofCompleteRequest(v11, 1);
  }
}

```

## disassembly

```asm
0x140013cb0  push    rbx
0x140013cb2  push    rbp
0x140013cb3  push    rsi
0x140013cb4  push    rdi
0x140013cb5  push    r14
0x140013cb7  push    r15
0x140013cb9  sub     rsp, 38h
0x140013cbd  mov     rdi, [rdx+38h]
0x140013cc1  mov     rsi, rdx
0x140013cc4  mov     r14d, ecx
0x140013cc7  mov     rbx, [rdi+38h]
0x140013ccb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013cd2  lea     rax, WPP_GLOBAL_Control
0x140013cd9  test    rbx, rbx
0x140013cdc  setz    r15b
0x140013ce0  cmp     rcx, rax
0x140013ce3  jz      short loc_140013D0F
0x140013ce5  mov     eax, [rcx+2Ch]
0x140013ce8  test    al, 10h
0x140013cea  jz      short loc_140013D0F
0x140013cec  cmp     byte ptr [rcx+29h], 4
0x140013cf0  jb      short loc_140013D0F
0x140013cf2  mov     rcx, [rcx+18h]
0x140013cf6  lea     r8, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids
0x140013cfd  mov     edx, 1Eh
0x140013d02  mov     dword ptr [rsp+68h+BugCheckParameter4], r14d
0x140013d07  mov     r9, rsi
0x140013d0a  call    WPP_SF_qD
0x140013d0f  call    cs:__imp_IoGetTopLevelIrp
0x140013d16  nop     dword ptr [rax+rax+00h]
0x140013d1b  cmp     rdi, rax
0x140013d1e  jnz     short loc_140013D25
0x140013d20  mov     bpl, 1
0x140013d23  jmp     short loc_140013D3F
0x140013d25  xor     bpl, bpl
0x140013d28  test    rbx, rbx
0x140013d2b  jz      short loc_140013D37
0x140013d2d  mov     rcx, rbx
0x140013d30  call    SmbCeAcquireCompoundingKeyLock
0x140013d35  jmp     short loc_140013D3F
0x140013d37  mov     rcx, rdi
0x140013d3a  call    SmbCeAcquireExchangeLock
0x140013d3f  dec     byte ptr [rsi+57h]
0x140013d42  lea     rcx, [rsi+210h]
0x140013d49  mov     edx, r14d
0x140013d4c  call    cs:__imp_RxCeUntrackTransportOpEx
0x140013d53  nop     dword ptr [rax+rax+00h]
0x140013d58  test    bpl, bpl
0x140013d5b  jnz     loc_140013EDE
0x140013d61  mov     rcx, rdi
0x140013d64  call    SmbCepCheckExchangeForDeferredAbortOrIfFinalizable
0x140013d69  test    al, al
0x140013d6b  jz      short loc_140013D94
0x140013d6d  mov     rcx, rdi
0x140013d70  call    SmbCepTryTurboCompleteExchangeLite
0x140013d75  mov     rsi, rax
0x140013d78  test    rax, rax
0x140013d7b  jnz     short loc_140013D96
0x140013d7d  mov     dl, r15b
0x140013d80  mov     rcx, rdi; pContext
0x140013d83  call    SmbCepCompleteExchangeLiteEx
0x140013d88  cmp     eax, 0C0000016h
0x140013d8d  jnz     short loc_140013D96
0x140013d8f  mov     bpl, 1
0x140013d92  jmp     short loc_140013D96
0x140013d94  xor     esi, esi
0x140013d96  test    rbx, rbx
0x140013d99  jz      short loc_140013DA5
0x140013d9b  mov     rcx, rbx
0x140013d9e  call    SmbCeReleaseCompoundingKeyLock
0x140013da3  jmp     short loc_140013DAD
0x140013da5  mov     rcx, rdi
0x140013da8  call    SmbCeReleaseExchangeLock
0x140013dad  test    bpl, bpl
0x140013db0  jz      loc_140013EC8
0x140013db6  mov     rbx, [rdi+48h]
0x140013dba  mov     rbp, [rbx+18h]
0x140013dbe  call    cs:__imp_KeGetCurrentIrql
0x140013dc5  nop     dword ptr [rax+rax+00h]
0x140013dca  cmp     al, 2
0x140013dcc  jb      short loc_140013DD9
0x140013dce  mov     eax, [rdi+44h]
0x140013dd1  xor     ecx, ecx
0x140013dd3  bt      eax, 12h
0x140013dd7  jnb     short loc_140013E55
0x140013dd9  mov     rax, [rbx+38h]
0x140013ddd  mov     ebx, 0C0410003h
0x140013de2  test    rax, rax
0x140013de5  jz      short loc_140013E01
0x140013de7  mov     rax, [rax+390h]
0x140013dee  test    rax, rax
0x140013df1  jz      short loc_140013E01
0x140013df3  mov     rcx, rdi
0x140013df6  call    _guard_dispatch_icall
0x140013dfb  mov     ecx, eax
0x140013dfd  cmp     eax, ebx
0x140013dff  jz      short loc_140013E55
0x140013e01  mov     rax, [rdi+0E8h]
0x140013e08  mov     rcx, rdi
0x140013e0b  mov     qword ptr [rdi+0D0h], 0
0x140013e16  mov     dword ptr [rdi+28h], 8
0x140013e1d  mov     rax, [rax+20h]
0x140013e21  call    _guard_dispatch_icall
0x140013e26  mov     ecx, eax
0x140013e28  cmp     eax, ebx
0x140013e2a  jz      short loc_140013E55
0x140013e2c  lea     rbx, [rdi+200h]
0x140013e33  mov     rcx, rbx
0x140013e36  call    RDR_PERF_EXIT
0x140013e3b  mov     rcx, rbx
0x140013e3e  call    RDR_PERF_OUTPUT_ETW
0x140013e43  mov     rcx, rbx
0x140013e46  call    RDR_PERF_FREE
0x140013e4b  mov     rcx, rdi; pContext
0x140013e4e  call    SmbCeDereferenceExchange
0x140013e53  jmp     short loc_140013EC8
0x140013e55  mov     eax, [rdi+44h]
0x140013e58  test    al, 1
0x140013e5a  jz      short loc_140013E82
0x140013e5c  movsxd  r9, ecx; BugCheckParameter3
0x140013e5f  mov     r8, rdi; BugCheckParameter2
0x140013e62  mov     ecx, 27h ; '''; BugCheckCode
0x140013e67  mov     [rsp+68h+BugCheckParameter4], 0; BugCheckParameter4
0x140013e70  mov     edx, 43584D5Fh; BugCheckParameter1
0x140013e75  call    cs:__imp_KeBugCheckEx
0x140013e82  lea     rcx, [rdi+200h]
0x140013e89  mov     dl, 14h
0x140013e8b  call    RDR_PERF_ENTER
0x140013e90  mov     r8d, 7
0x140013e96  mov     rdx, rdi
0x140013e99  mov     rcx, rbp
0x140013e9c  call    SmbCeIncrementTeardownOpCounter
0x140013ea1  lea     r8, [rdi+0F0h]; pWorkQueueItem
0x140013ea8  mov     [rsp+68h+BugCheckParameter4], rdi; pContext
0x140013ead  lea     r9, SmbCepFinalizeExchangeWorker; Routine
0x140013eb4  mov     edx, 3; WorkQueueType
0x140013eb9  mov     rcx, rbp; pMRxDeviceObject
0x140013ebc  call    cs:__imp_RxPostToWorkerThread
0x140013ec3  nop     dword ptr [rax+rax+00h]
0x140013ec8  test    rsi, rsi
0x140013ecb  jz      short loc_140013EDE
0x140013ecd  mov     dl, 1; PriorityBoost
0x140013ecf  mov     rcx, rsi; Irp
0x140013ed2  call    cs:__imp_IofCompleteRequest
0x140013ed9  nop     dword ptr [rax+rax+00h]
0x140013ede  add     rsp, 38h
0x140013ee2  pop     r15
0x140013ee4  pop     r14
0x140013ee6  pop     rdi
0x140013ee7  pop     rsi
0x140013ee8  pop     rbp
0x140013ee9  pop     rbx
0x140013eea  retn
```
