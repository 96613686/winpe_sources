# UlCleanupConsumer

- ea: `0x1c00a7d24`
- end: `0x1c00a8084`
- name: `UlCleanupConsumer`
- size: `864`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x1c00a7b10`

## callees

- `0x1c0003240`
- `0x1c00033b4`
- `0x1c00037c0`
- `0x1c000fc68`
- `0x1c0010ce8`
- `0x1c00115ec`
- `0x1c001b610`
- `0x1c008f21c`
- `0x1c008f3ec`
- `0x1c008f680`
- `0x1c008fe44`
- `0x1c008fffc`
- `0x1c00a7c18`
- `0x1c00a7d24`
- `0x1c00a808c`
- `0x1c00a814c`
- `0x1c00a81b8`
- `0x1c00a8420`
- `0x1c00a86ac`
- `0x1c00a8718`
- `0x1c00a8780`
- `0x1c00a87f4`
- `0x1c00a93f4`
- `0x1c00cedb4`
- `0x1c00d6070`
- `0x1c00d60c4`
- `0x1c0103720`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1c00e6c37`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x1c00e6c37`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00e6ca0`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00e6ca0`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00a7e1a`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00a7e1a`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e6d28`
- `ntoskrnl!IofCompleteRequest` at `0x1c00e6d28`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00e6cc8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00e6e67`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00e6cc8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c00e6e67`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a7dfb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00e6e23`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00a7dfb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c00e6e23`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e6cac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e6cd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e6e73`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e6cac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e6cd4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00e6e73`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a7ddf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a7e07`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00e6e0a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a7ddf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a7e07`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00e6e0a`

## pseudocode

```c
__int64 __fastcall UlCleanupConsumer(__int64 a1, __int64 a2)
{
  void *v2; // r12
  char v3; // r15
  __int64 v6; // rsi
  __int64 v7; // rdi
  __int64 ****v8; // rcx
  __int64 ***v9; // rax
  _QWORD *v10; // rcx
  __int64 *v11; // rcx
  _QWORD *v12; // rax
  __int64 result; // rax
  __int64 **v14; // rdx
  _QWORD *v15; // rdx
  _QWORD *v16; // rax
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  _QWORD *v19; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rax
  IRP *v24; // rcx
  __int64 *v25; // rax
  void (*v26)(void); // rax
  __int64 v27; // rcx
  volatile signed __int32 *v28; // rbx
  __int64 *v29; // [rsp+30h] [rbp-50h] BYREF
  __int64 **v30; // [rsp+38h] [rbp-48h]
  _QWORD v31[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD v33[2]; // [rsp+60h] [rbp-20h] BYREF
  __int128 v34; // [rsp+70h] [rbp-10h] BYREF

  v2 = 0;
  v3 = 0;
  v34 = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qq(116, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, a2);
  v6 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v7 = *(_QWORD *)(v6 + 8);
  v31[1] = v31;
  v31[0] = v31;
  v33[1] = v33;
  v33[0] = v33;
  v32[1] = v32;
  v32[0] = v32;
  v30 = &v29;
  v29 = (__int64 *)&v29;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x200000) != 0 )
    WPP_SF_qLqZ(117, a2, v6, *(_DWORD *)(v6 + 40), v7, v7 + 152);
  UxPodAttachThread(*(_QWORD *)(v7 + 320), &v34);
  *(_QWORD *)(*(_QWORD *)(a2 + 48) + 32LL) = 1886413144;
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(v7 + 328) + 3952LL, 0);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v7 + 280));
  UlpFlushPendingConsumerIo(v6, v31, v33);
  *(_BYTE *)(v6 + 5) = 1;
  UlpEnumerateCouplings(v7 + 240, 24, (unsigned int)UlpFlushWaitForDisconnects, v6, (__int64)v31);
  UlpEnumerateCouplings(v7 + 240, 24, (unsigned int)UlpFlushCouplingRequests, v6, (__int64)v32);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qq(112, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v6, &v29);
  v8 = (__int64 ****)(v6 + 104);
  while ( 1 )
  {
    v9 = *v8;
    if ( *v8 == (__int64 ***)v8 )
      break;
    if ( v9[1] != (__int64 **)v8 )
      goto LABEL_51;
    v14 = *v9;
    if ( (*v9)[1] != (__int64 *)v9 )
      goto LABEL_51;
    *v8 = (__int64 ***)v14;
    v14[1] = (__int64 *)v8;
    *v9 = 0;
    v9[1] = 0;
    *((_BYTE *)v9 + 32) = 1;
    v15 = v30;
    if ( *v30 != (__int64 *)&v29 )
      goto LABEL_51;
    v9[1] = v30;
    *v9 = &v29;
    *v15 = v9;
    v30 = (__int64 **)v9;
  }
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_(113, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_q(61, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v6);
  v16 = (_QWORD *)(v6 + 48);
  v17 = *(_QWORD *)(v6 + 48);
  if ( *(_QWORD *)(v17 + 8) != v6 + 48 || (v18 = *(_QWORD **)(v6 + 56), (_QWORD *)*v18 != v16) )
LABEL_51:
    __fastfail(3u);
  *v18 = v17;
  *(_QWORD *)(v17 + 8) = v18;
  *v16 = 0;
  *(_QWORD *)(v6 + 56) = 0;
  if ( *(_DWORD *)(v6 + 40) == 1 )
    --*(_DWORD *)(*(_QWORD *)(v6 + 8) + 272LL);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_(62, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  if ( *(_QWORD *)(v7 + 208) == v7 + 208 )
  {
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x200000) != 0 )
      WPP_SF_qZ(118, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v7, v7 + 152);
    v3 = 1;
    RtlRemoveEntryHashTable(
      (PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(v7 + 328) + 3960LL),
      (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v7 + 168),
      0);
    v19 = (_QWORD *)(v7 + 192);
    v20 = *(_QWORD *)(v7 + 192);
    if ( *(_QWORD *)(v20 + 8) != v7 + 192 )
      goto LABEL_51;
    v21 = *(_QWORD **)(v7 + 200);
    if ( (_QWORD *)*v21 != v19 )
      goto LABEL_51;
    *v21 = v20;
    *(_QWORD *)(v20 + 8) = v21;
    *v19 = 0;
    *(_QWORD *)(v7 + 200) = 0;
    UlpCleanupRequestQueueCouplings(v7);
    LOBYTE(v22) = 1;
    UlpFlushPendingRequests(v7, v33, v22);
    v2 = *(void **)(v7 + 128);
    *(_QWORD *)(v7 + 128) = 0;
    *(_DWORD *)(v7 + 224) = 4;
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v7 + 280));
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*(_QWORD *)(v7 + 328) + 3952LL, 0);
  KeLeaveCriticalRegion();
  while ( 1 )
  {
    v10 = (_QWORD *)v31[0];
    if ( (_QWORD *)v31[0] == v31 )
      break;
    if ( *(_QWORD **)(v31[0] + 8LL) != v31 )
      goto LABEL_51;
    v23 = *(_QWORD *)v31[0];
    if ( *(_QWORD *)(*(_QWORD *)v31[0] + 8LL) != v31[0] )
      goto LABEL_51;
    v31[0] = *(_QWORD *)v31[0];
    *(_QWORD *)(v23 + 8) = v31;
    *v10 = 0;
    v10[1] = 0;
    v24 = (IRP *)(v10 - 21);
    v24->IoStatus.Status = -1073741536;
    v24->IoStatus.Information = 0;
    IofCompleteRequest(v24, 0);
  }
  *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
  *(_DWORD *)(a1 + 48) = 259;
  *(_QWORD *)(v6 + 32) = a1;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_q(114, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, &v29);
  while ( 1 )
  {
    v11 = v29;
    if ( v29 == (__int64 *)&v29 )
      break;
    if ( (__int64 **)v29[1] != &v29 )
      goto LABEL_51;
    v25 = (__int64 *)*v29;
    if ( *(__int64 **)(*v29 + 8) != v29 )
      goto LABEL_51;
    v29 = (__int64 *)*v29;
    v25[1] = (__int64)&v29;
    v26 = (void (*)(void))v11[3];
    *v11 = 0;
    v11[1] = 0;
    v26();
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80) != 0 )
    WPP_SF_(115, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  UlPurgeZombieConnections(*(_QWORD *)(*(_QWORD *)(v6 + 8) + 328LL), UlPurgeConsumer, v6);
  UlFlushCacheByConsumer(v6);
  if ( v3 )
    UlFlushCacheByRequestQueue(v7);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x80) != 0 )
    WPP_SF_q(91, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v32);
  while ( 1 )
  {
    v12 = (_QWORD *)v32[0];
    if ( (_QWORD *)v32[0] == v32 )
      break;
    if ( *(_QWORD **)(v32[0] + 8LL) != v32 )
      goto LABEL_51;
    v27 = *(_QWORD *)v32[0];
    if ( *(_QWORD *)(*(_QWORD *)v32[0] + 8LL) != v32[0] )
      goto LABEL_51;
    v32[0] = *(_QWORD *)v32[0];
    *(_QWORD *)(v27 + 8) = v32;
    v28 = (volatile signed __int32 *)(v12 - 221);
    *v12 = 0;
    v12[1] = 0;
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x200000) != 0 )
      WPP_SF_q(92, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, v12 - 221);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(*((_QWORD *)v28 + 3) + 464LL, 0);
    UlCancelRequestIo(v28);
    UlErrorLog(*((_QWORD *)v28 + 3), (_DWORD)v28, (unsigned int)"Connection_Abandoned_By_ReqQueue", 32, 1, 0);
    ExReleasePushLockExclusiveEx(*((_QWORD *)v28 + 3) + 464LL, 0);
    KeLeaveCriticalRegion();
    UlCloseConnection(*((_QWORD *)v28 + 3));
    if ( _InterlockedExchangeAdd(v28 + 12, 0xFFFFFFFF) == 1 )
      UlpQueueFreeHttpRequest(v28);
  }
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_(93, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  if ( v3 )
  {
    UlpRequestQueueStateToErrorCode(4);
    UlpRejectFlushedRequests(v7);
  }
  else
  {
    UlpRedeliverFlushedRequests(v7);
  }
  if ( v3 )
  {
    if ( v2 )
      UlDeleteAutoServerSession(v2);
    UlPcwDeleteInstance(*(_QWORD *)(v7 + 328), v7, 2);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
      UlFreeRequestQueue((PVOID)v7);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6, 0xFFFFFFFF) == 1 )
    UlConsumerCleanupCompletion(v6);
  UxPodDetachThread(&v34);
  result = LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    return WPP_SF_(119, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1c00a7d24  mov     [rsp-28h+arg_0], rbx
0x1c00a7d29  mov     [rsp-28h+arg_10], rsi
0x1c00a7d2e  mov     [rsp-28h+arg_18], rdi
0x1c00a7d33  push    rbp
0x1c00a7d34  push    r12
0x1c00a7d36  push    r13
0x1c00a7d38  push    r14
0x1c00a7d3a  push    r15
0x1c00a7d3c  mov     rbp, rsp
0x1c00a7d3f  sub     rsp, 80h
0x1c00a7d46  xor     r12d, r12d
0x1c00a7d49  xorps   xmm0, xmm0
0x1c00a7d4c  xor     r15b, r15b
0x1c00a7d4f  mov     rbx, rdx
0x1c00a7d52  movups  [rbp+var_10], xmm0
0x1c00a7d56  mov     r14, rcx
0x1c00a7d59  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a7d5f  test    al, al
0x1c00a7d61  js      loc_1C00E6B0A
0x1c00a7d67  mov     rax, [rbx+30h]
0x1c00a7d6b  mov     rsi, [rax+18h]
0x1c00a7d6f  lea     rax, [rbp+var_40]
0x1c00a7d73  mov     rdi, [rsi+8]
0x1c00a7d77  mov     [rbp+var_38], rax
0x1c00a7d7b  lea     rax, [rbp+var_40]
0x1c00a7d7f  mov     [rbp+var_40], rax
0x1c00a7d83  lea     rax, [rbp+var_20]
0x1c00a7d87  mov     [rbp+var_18], rax
0x1c00a7d8b  lea     rax, [rbp+var_20]
0x1c00a7d8f  mov     [rbp+var_20], rax
0x1c00a7d93  lea     rax, [rbp+var_30]
0x1c00a7d97  mov     [rbp+var_28], rax
0x1c00a7d9b  lea     rax, [rbp+var_30]
0x1c00a7d9f  mov     [rbp+var_30], rax
0x1c00a7da3  lea     rax, [rbp+var_50]
0x1c00a7da7  mov     [rbp+var_48], rax
0x1c00a7dab  lea     rax, [rbp+var_50]
0x1c00a7daf  mov     [rbp+var_50], rax
0x1c00a7db3  test    dword ptr cs:WPP_MAIN_CB.Queue, 200000h
0x1c00a7dbd  jnz     loc_1C00E6B27
0x1c00a7dc3  mov     rcx, [rdi+140h]
0x1c00a7dca  lea     rdx, [rbp+var_10]
0x1c00a7dce  call    UxPodAttachThread
0x1c00a7dd3  mov     rax, [rbx+30h]
0x1c00a7dd7  mov     qword ptr [rax+20h], 70706158h
0x1c00a7ddf  call    cs:__imp_KeEnterCriticalRegion
0x1c00a7de6  nop     dword ptr [rax+rax+00h]
0x1c00a7deb  mov     rcx, [rdi+148h]
0x1c00a7df2  xor     edx, edx
0x1c00a7df4  add     rcx, 0F70h
0x1c00a7dfb  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c00a7e02  nop     dword ptr [rax+rax+00h]
0x1c00a7e07  call    cs:__imp_KeEnterCriticalRegion
0x1c00a7e0e  nop     dword ptr [rax+rax+00h]
0x1c00a7e13  mov     rcx, [rdi+118h]
0x1c00a7e1a  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c00a7e21  nop     dword ptr [rax+rax+00h]
0x1c00a7e26  lea     r8, [rbp+var_20]
0x1c00a7e2a  mov     rcx, rsi
0x1c00a7e2d  lea     rdx, [rbp+var_40]
0x1c00a7e31  call    UlpFlushPendingConsumerIo
0x1c00a7e36  lea     rax, [rbp+var_40]
0x1c00a7e3a  mov     byte ptr [rsi+5], 1
0x1c00a7e3e  lea     rbx, [rdi+0F0h]
0x1c00a7e45  mov     [rsp+80h+var_60], rax
0x1c00a7e4a  mov     r13d, 18h
0x1c00a7e50  lea     r8, UlpFlushWaitForDisconnects
0x1c00a7e57  mov     edx, r13d
0x1c00a7e5a  mov     rcx, rbx
0x1c00a7e5d  mov     r9, rsi
0x1c00a7e60  call    UlpEnumerateCouplings
0x1c00a7e65  lea     rax, [rbp+var_30]
0x1c00a7e69  mov     r9, rsi
0x1c00a7e6c  lea     r8, UlpFlushCouplingRequests
0x1c00a7e73  mov     [rsp+80h+var_60], rax
0x1c00a7e78  mov     edx, r13d
0x1c00a7e7b  mov     rcx, rbx
0x1c00a7e7e  call    UlpEnumerateCouplings
0x1c00a7e83  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a7e89  lea     rbx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00a7e90  test    al, al
0x1c00a7e92  js      loc_1C00E6B4F
0x1c00a7e98  lea     rcx, [rsi+68h]
0x1c00a7e9c  xor     r13d, r13d
0x1c00a7e9f  mov     rax, [rcx]
0x1c00a7ea2  cmp     rax, rcx
0x1c00a7ea5  jnz     loc_1C00E6B69
0x1c00a7eab  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a7eb1  test    al, al
0x1c00a7eb3  js      loc_1C00E6BAE
0x1c00a7eb9  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a7ebf  test    al, al
0x1c00a7ec1  js      loc_1C00E6BC1
0x1c00a7ec7  jmp     loc_1C00E6BD1
0x1c00a7ecc  mov     rcx, [rbp+var_40]
0x1c00a7ed0  lea     rax, [rbp+var_40]
0x1c00a7ed4  cmp     rcx, rax
0x1c00a7ed7  jnz     loc_1C00E6CE6
0x1c00a7edd  mov     rax, [r14+0B8h]
0x1c00a7ee4  or      byte ptr [rax+3], 1
0x1c00a7ee8  mov     dword ptr [r14+30h], 103h
0x1c00a7ef0  mov     [rsi+20h], r14
0x1c00a7ef4  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a7efa  mov     r14b, 80h
0x1c00a7efd  test    r14b, al
0x1c00a7f00  jnz     loc_1C00E6D3A
0x1c00a7f06  mov     rcx, [rbp+var_50]
0x1c00a7f0a  lea     rax, [rbp+var_50]
0x1c00a7f0e  cmp     rcx, rax
0x1c00a7f11  jnz     loc_1C00E6D51
0x1c00a7f17  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a7f1d  test    r14b, al
0x1c00a7f20  jnz     loc_1C00E6D8F
0x1c00a7f26  mov     rcx, [rsi+8]
0x1c00a7f2a  lea     rdx, UlPurgeConsumer
0x1c00a7f31  mov     r8, rsi
0x1c00a7f34  mov     rcx, [rcx+148h]
0x1c00a7f3b  call    UlPurgeZombieConnections
0x1c00a7f40  mov     rcx, rsi
0x1c00a7f43  call    UlFlushCacheByConsumer
0x1c00a7f48  test    r15b, r15b
0x1c00a7f4b  jz      short loc_1C00A7F55
0x1c00a7f4d  mov     rcx, rdi
0x1c00a7f50  call    UlFlushCacheByRequestQueue
0x1c00a7f55  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a7f5b  test    r14b, al
0x1c00a7f5e  jnz     loc_1C00E6DA2
0x1c00a7f64  lea     r14, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00a7f6b  mov     rax, [rbp+var_30]
0x1c00a7f6f  lea     rcx, [rbp+var_30]
0x1c00a7f73  cmp     rax, rcx
0x1c00a7f76  jnz     loc_1C00E6DB9
0x1c00a7f7c  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a7f82  test    al, al
0x1c00a7f84  js      loc_1C00E6EA9
0x1c00a7f8a  test    r15b, r15b
0x1c00a7f8d  jz      loc_1C00E6EBC
0x1c00a7f93  mov     ecx, 4
0x1c00a7f98  call    UlpRequestQueueStateToErrorCode
0x1c00a7f9d  mov     r9, rsi
0x1c00a7fa0  lea     rdx, [rbp+var_20]
0x1c00a7fa4  mov     r8d, eax
0x1c00a7fa7  mov     rcx, rdi; int
0x1c00a7faa  call    UlpRejectFlushedRequests
0x1c00a7faf  test    r15b, r15b
0x1c00a7fb2  jz      short loc_1C00A7FE6
0x1c00a7fb4  test    r12, r12
0x1c00a7fb7  jz      short loc_1C00A7FC1
0x1c00a7fb9  mov     rcx, r12
0x1c00a7fbc  call    UlDeleteAutoServerSession
0x1c00a7fc1  mov     rcx, [rdi+148h]
0x1c00a7fc8  mov     r8d, 2
0x1c00a7fce  mov     rdx, rdi
0x1c00a7fd1  call    UlPcwDeleteInstance
0x1c00a7fd6  or      eax, 0FFFFFFFFh
0x1c00a7fd9  lock xadd [rdi], eax
0x1c00a7fdd  cmp     eax, 1
0x1c00a7fe0  jz      loc_1C00E6ED1
0x1c00a7fe6  or      eax, 0FFFFFFFFh
0x1c00a7fe9  lock xadd [rsi], eax
0x1c00a7fed  cmp     eax, 1
0x1c00a7ff0  jnz     short loc_1C00A7FFA
0x1c00a7ff2  mov     rcx, rsi
0x1c00a7ff5  call    UlConsumerCleanupCompletion
0x1c00a7ffa  lea     rcx, [rbp+var_10]
0x1c00a7ffe  call    UxPodDetachThread
0x1c00a8003  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a8009  test    al, al
0x1c00a800b  js      loc_1C00E6EDF
0x1c00a8011  lea     r11, [rsp+80h+var_s0]
0x1c00a8019  mov     rbx, [r11+30h]
0x1c00a801d  mov     rsi, [r11+40h]
0x1c00a8021  mov     rdi, [r11+48h]
0x1c00a8025  mov     rsp, r11
0x1c00a8028  pop     r15
0x1c00a802a  pop     r14
0x1c00a802c  pop     r13
0x1c00a802e  pop     r12
0x1c00a8030  pop     rbp
0x1c00a8031  retn
0x1c00a8033  mov     [rdx], rcx
0x1c00a8036  mov     [rcx+8], rdx
0x1c00a803a  mov     [rax], r13
0x1c00a803d  mov     [rax+8], r13
0x1c00a8041  cmp     dword ptr [rsi+28h], 1
0x1c00a8045  jnz     short loc_1C00A8051
0x1c00a8047  mov     rax, [rsi+8]
0x1c00a804b  dec     dword ptr [rax+110h]
0x1c00a8051  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a8057  test    al, al
0x1c00a8059  js      loc_1C00E6BF2
0x1c00a805f  lea     rax, [rdi+0D0h]
0x1c00a8066  cmp     [rax], rax
0x1c00a8069  jnz     loc_1C00E6C99
0x1c00a806f  test    dword ptr cs:WPP_MAIN_CB.Queue, 200000h
0x1c00a8079  jnz     loc_1C00E6C05
0x1c00a807f  jmp     loc_1C00E6C1C
0x1c00e6b0a  mov     ecx, 74h ; 't'
0x1c00e6b0f  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c00e6b16  mov     r9, rbx
0x1c00e6b19  mov     r8, r14
0x1c00e6b1c  call    WPP_SF_qq
0x1c00e6b21  nop
0x1c00e6b22  jmp     loc_1C00A7D67
0x1c00e6b27  mov     r9d, [rsi+28h]
0x1c00e6b2b  lea     rax, [rdi+98h]
0x1c00e6b32  mov     [rsp+80h+var_58], rax
0x1c00e6b37  mov     ecx, 75h ; 'u'
0x1c00e6b3c  mov     r8, rsi
0x1c00e6b3f  mov     [rsp+80h+var_60], rdi
0x1c00e6b44  call    WPP_SF_qLqZ
0x1c00e6b49  nop
0x1c00e6b4a  jmp     loc_1C00A7DC3
0x1c00e6b4f  mov     ecx, 70h ; 'p'
0x1c00e6b54  lea     r9, [rbp+var_50]
0x1c00e6b58  mov     r8, rsi
0x1c00e6b5b  mov     rdx, rbx
0x1c00e6b5e  call    WPP_SF_qq
0x1c00e6b63  nop
0x1c00e6b64  jmp     loc_1C00A7E98
0x1c00e6b69  cmp     [rax+8], rcx
0x1c00e6b6d  jnz     short loc_1C00E6BEB
0x1c00e6b6f  mov     rdx, [rax]
0x1c00e6b72  cmp     [rdx+8], rax
0x1c00e6b76  jnz     short loc_1C00E6BEB
0x1c00e6b78  mov     [rcx], rdx
0x1c00e6b7b  lea     r8, [rbp+var_50]
0x1c00e6b7f  mov     [rdx+8], rcx
0x1c00e6b83  mov     [rax], r13
0x1c00e6b86  mov     [rax+8], r13
0x1c00e6b8a  mov     byte ptr [rax+20h], 1
0x1c00e6b8e  mov     rdx, [rbp+var_48]
0x1c00e6b92  cmp     [rdx], r8
0x1c00e6b95  jnz     short loc_1C00E6BEB
0x1c00e6b97  mov     [rax+8], rdx
0x1c00e6b9b  lea     r8, [rbp+var_50]
0x1c00e6b9f  mov     [rax], r8
0x1c00e6ba2  mov     [rdx], rax
0x1c00e6ba5  mov     [rbp+var_48], rax
0x1c00e6ba9  jmp     loc_1C00A7E9F
0x1c00e6bae  mov     ecx, 71h ; 'q'
0x1c00e6bb3  mov     rdx, rbx
0x1c00e6bb6  call    WPP_SF_
0x1c00e6bbb  nop
0x1c00e6bbc  jmp     loc_1C00A7EB9
0x1c00e6bc1  mov     ecx, 3Dh ; '='
0x1c00e6bc6  mov     r8, rsi
0x1c00e6bc9  mov     rdx, rbx
0x1c00e6bcc  call    WPP_SF_q
0x1c00e6bd1  lea     rax, [rsi+30h]
0x1c00e6bd5  mov     rcx, [rax]
0x1c00e6bd8  cmp     [rcx+8], rax
0x1c00e6bdc  jnz     short loc_1C00E6BEB
0x1c00e6bde  mov     rdx, [rax+8]
0x1c00e6be2  cmp     [rdx], rax
0x1c00e6be5  jz      loc_1C00A8033
0x1c00e6beb  mov     ecx, 3
0x1c00e6bf0  int     29h; Win8: RtlFailFast(ecx)
0x1c00e6bf2  mov     ecx, 3Eh ; '>'
0x1c00e6bf7  mov     rdx, rbx
0x1c00e6bfa  call    WPP_SF_
0x1c00e6bff  nop
0x1c00e6c00  jmp     loc_1C00A805F
0x1c00e6c05  lea     r9, [rdi+98h]
0x1c00e6c0c  mov     ecx, 76h ; 'v'
0x1c00e6c11  mov     r8, rdi
0x1c00e6c14  mov     rdx, rbx
0x1c00e6c17  call    WPP_SF_qZ
0x1c00e6c1c  mov     rcx, [rdi+148h]
0x1c00e6c23  lea     rdx, [rdi+0A8h]; Entry
0x1c00e6c2a  add     rcx, 0F78h; HashTable
0x1c00e6c31  xor     r8d, r8d; Context
0x1c00e6c34  mov     r15b, 1
0x1c00e6c37  call    cs:__imp_RtlRemoveEntryHashTable
0x1c00e6c3e  nop     dword ptr [rax+rax+00h]
0x1c00e6c43  lea     rax, [rdi+0C0h]
0x1c00e6c4a  mov     rdx, [rax]
0x1c00e6c4d  cmp     [rdx+8], rax
0x1c00e6c51  jnz     short loc_1C00E6BEB
0x1c00e6c53  mov     rcx, [rax+8]
0x1c00e6c57  cmp     [rcx], rax
0x1c00e6c5a  jnz     short loc_1C00E6BEB
0x1c00e6c5c  mov     [rcx], rdx
0x1c00e6c5f  mov     [rdx+8], rcx
0x1c00e6c63  mov     rcx, rdi
0x1c00e6c66  mov     [rax], r13
0x1c00e6c69  mov     [rax+8], r13
0x1c00e6c6d  call    UlpCleanupRequestQueueCouplings
0x1c00e6c72  mov     r8b, r15b
0x1c00e6c75  lea     rdx, [rbp+var_20]
0x1c00e6c79  mov     rcx, rdi
0x1c00e6c7c  call    UlpFlushPendingRequests
0x1c00e6c81  mov     r12, [rdi+80h]
0x1c00e6c88  mov     [rdi+80h], r13
0x1c00e6c8f  mov     dword ptr [rdi+0E0h], 4
0x1c00e6c99  mov     rcx, [rdi+118h]
0x1c00e6ca0  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c00e6ca7  nop     dword ptr [rax+rax+00h]
0x1c00e6cac  call    cs:__imp_KeLeaveCriticalRegion
0x1c00e6cb3  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
