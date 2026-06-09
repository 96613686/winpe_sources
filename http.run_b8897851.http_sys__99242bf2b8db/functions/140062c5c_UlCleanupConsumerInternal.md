# UlCleanupConsumerInternal

- ea: `0x140062c5c`
- end: `0x14006310a`
- name: `UlCleanupConsumerInternal`
- size: `1198`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x140062af0`

## callees

- `0x14000a350`
- `0x140025918`
- `0x140041798`
- `0x140060dfc`
- `0x140060e24`
- `0x14006124c`
- `0x140061d50`
- `0x140062c5c`
- `0x1400710bc`
- `0x140071698`
- `0x140071790`
- `0x14009622c`
- `0x1400a033c`
- `0x1400a0988`
- `0x1400a1828`
- `0x1400a19d8`
- `0x1400a38cc`
- `0x1400a9694`
- `0x1400b3e00`
- `0x1400d72fc`
- `0x1401c3f58`
- `0x1401c3f78`
- `0x1401c575c`
- `0x1401da5a4`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140062f0e`
- `ntoskrnl!IofCompleteRequest` at `0x140062f0e`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140062e7b`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140063026`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140062e7b`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x140063026`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140062e24`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140062e24`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140062d14`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140063003`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140062d14`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x140063003`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140062e87`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140062eaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140063032`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140062e87`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140062eaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140063032`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140062ea3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140062ea3`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140062cf5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140062cf5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062cd9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062d01`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062ff0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062cd9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062d01`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140062ff0`

## pseudocode

```c
__int64 __fastcall UlCleanupConsumerInternal(__int64 a1, ULONG_PTR a2, ULONG_PTR a3)
{
  __int64 i; // r14
  __int64 *j; // rax
  void *v8; // r14
  char v9; // r12
  char v10; // bl
  __int64 v11; // r8
  _QWORD *v12; // rcx
  __int64 v13; // rax
  IRP *v14; // rcx
  char v15; // bl
  int v16; // eax
  __int64 result; // rax
  _QWORD v18[2]; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v19[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v21[2]; // [rsp+60h] [rbp-10h] BYREF

  v19[0] = v19;
  v19[1] = v19;
  v21[0] = v21;
  v21[1] = v21;
  v18[0] = v18;
  v18[1] = v18;
  v20[0] = v20;
  v20[1] = v20;
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    WPP_SF_q(1032, 123, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a1);
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(*(_QWORD *)(a2 + 328) + 4144LL, 0);
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a2 + 280));
  UlpFlushPendingConsumerIo(a3);
  *(_BYTE *)(a3 + 5) = 1;
  for ( i = 0; (unsigned int)i < (unsigned __int16)UlNumberOfLanes; i = (unsigned int)(i + 1) )
  {
    UlpEnumerateCouplings(
      *(_QWORD *)(*(_QWORD *)(a2 + 264) + 8 * i),
      40,
      (unsigned int)UlpFlushWaitForDisconnects,
      a3,
      (__int64)v18);
    UlpEnumerateCouplings(
      *(_QWORD *)(*(_QWORD *)(a2 + 264) + 8 * i),
      40,
      (unsigned int)UlpFlushCouplingRequests,
      a3,
      (__int64)v21);
  }
  UlpFlushConsumerCallbacks(a3, v20);
  UlpAttemptDetachFromRequestQueue(a3);
  for ( j = *(__int64 **)(a2 + 216); j != (__int64 *)(a2 + 216); j = (__int64 *)*j )
  {
    if ( !*((_BYTE *)j + 96) )
    {
      v8 = 0;
      v9 = 0;
      v10 = 0;
      goto LABEL_13;
    }
  }
  v10 = 1;
  if ( (BYTE2(xmmword_1401A2CA0) & 0x40) != 0 )
    WPP_SF_qZ(1046, 124, (unsigned int)WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, a2, a2 + 160);
  RtlRemoveEntryHashTable(
    (PRTL_DYNAMIC_HASH_TABLE)(*(_QWORD *)(a2 + 328) + 4152LL),
    (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(a2 + 176),
    0);
  *(_BYTE *)(a2 + 338) = 1;
  v9 = UlpAttemptRequestQueueCleanup(a2);
  UlpCleanupRequestQueueCouplings(a2);
  LOBYTE(v11) = 1;
  UlpFlushPendingRequests(a2, v19, v11);
  v8 = *(void **)(a2 + 136);
  *(_QWORD *)(a2 + 136) = 0;
  *(_DWORD *)(a2 + 248) = 4;
LABEL_13:
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a2 + 280));
  KeLeaveCriticalRegion();
  ExReleasePushLockExclusiveEx(*(_QWORD *)(a2 + 328) + 4144LL, 0);
  KeLeaveCriticalRegion();
  while ( 1 )
  {
    v12 = (_QWORD *)v18[0];
    if ( (_QWORD *)v18[0] == v18 )
      break;
    if ( *(_QWORD **)(v18[0] + 8LL) != v18 || (v13 = *(_QWORD *)v18[0], *(_QWORD *)(*(_QWORD *)v18[0] + 8LL) != v18[0]) )
      __fastfail(3u);
    v18[0] = *(_QWORD *)v18[0];
    *(_QWORD *)(v13 + 8) = v18;
    *v12 = 0;
    v12[1] = 0;
    v14 = (IRP *)(v12 - 21);
    v14->IoStatus.Status = -1073741536;
    v14->IoStatus.Information = 0;
    IofCompleteRequest(v14, 0);
  }
  *(_BYTE *)(*(_QWORD *)(a1 + 184) + 3LL) |= 1u;
  *(_DWORD *)(a1 + 48) = 259;
  *(_QWORD *)(a3 + 32) = a1;
  UlpInvokeFlushedConsumerCallbacks(v20);
  UlPurgeZombieConnections(*(_QWORD *)(a3 + 136), UlPurgeConsumer, a3);
  UlFlushCacheByConsumer(a3);
  if ( v10 )
    UlFlushCacheByRequestQueue(*(_QWORD *)(a3 + 136), a2);
  UlpAbortFlushedRequests(v21);
  if ( v10 )
  {
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_d(1032, 137, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, 4);
    if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
      WPP_SF_d(1032, 138, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids, 24);
    UlpRejectFlushedRequests(a2, v19, 24, a3);
    v15 = 0;
    if ( v8 )
      UlDeleteAutoServerSession(v8);
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a2 + 280));
    if ( !*(_BYTE *)(a2 + 336) )
    {
      v15 = 1;
      *(_BYTE *)(a2 + 336) = 1;
    }
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a2 + 280));
    KeLeaveCriticalRegion();
    if ( v15 )
      UlPcwDeleteInstance(*(_QWORD *)(a2 + 328), a2, 2);
  }
  else
  {
    UlpRedeliverFlushedRequests(a2, v19, a3);
  }
  if ( v9 )
  {
    v16 = _InterlockedDecrement((volatile signed __int32 *)a2);
    if ( UxDebugCheckRefcount && v16 <= -1 )
      UlBugCheckEx(3u, a2, 1u, v16);
    if ( !v16 )
      UlFreeRequestQueue((PVOID)a2);
  }
  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)a3);
  if ( UxDebugCheckRefcount && (int)result <= -1 )
    UlBugCheckEx(3u, a3, 1u, (int)result);
  if ( !(_DWORD)result )
    result = UlConsumerCleanupCompletion(a3);
  if ( (BYTE1(xmmword_1401A2CA0) & 1) != 0 )
    return WPP_SF_(1032, 125, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140062c5c  push    rbp
0x140062c5e  push    rbx
0x140062c5f  push    rsi
0x140062c60  push    rdi
0x140062c61  push    r12
0x140062c63  push    r14
0x140062c65  push    r15
0x140062c67  mov     rbp, rsp
0x140062c6a  sub     rsp, 70h
0x140062c6e  lea     rax, [rbp+var_30]
0x140062c72  mov     rsi, r8
0x140062c75  mov     [rbp+var_30], rax
0x140062c79  mov     rdi, rdx
0x140062c7c  lea     rax, [rbp+var_30]
0x140062c80  mov     r15, rcx
0x140062c83  mov     [rbp+var_28], rax
0x140062c87  lea     rax, [rbp+var_10]
0x140062c8b  mov     [rbp+var_10], rax
0x140062c8f  lea     rax, [rbp+var_10]
0x140062c93  mov     [rbp+var_8], rax
0x140062c97  lea     rax, [rbp+var_40]
0x140062c9b  mov     [rbp+var_40], rax
0x140062c9f  lea     rax, [rbp+var_40]
0x140062ca3  mov     [rbp+var_38], rax
0x140062ca7  lea     rax, [rbp+var_20]
0x140062cab  mov     [rbp+var_20], rax
0x140062caf  lea     rax, [rbp+var_20]
0x140062cb3  mov     [rbp+var_18], rax
0x140062cb7  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140062cbe  jz      short loc_140062CD9
0x140062cc0  mov     edx, 7Bh ; '{'
0x140062cc5  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140062ccc  mov     ecx, 408h
0x140062cd1  mov     r9, r15
0x140062cd4  call    WPP_SF_q
0x140062cd9  call    cs:__imp_KeEnterCriticalRegion
0x140062ce0  nop     dword ptr [rax+rax+00h]
0x140062ce5  mov     rcx, [rdi+148h]
0x140062cec  xor     edx, edx
0x140062cee  add     rcx, 1030h
0x140062cf5  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140062cfc  nop     dword ptr [rax+rax+00h]
0x140062d01  call    cs:__imp_KeEnterCriticalRegion
0x140062d08  nop     dword ptr [rax+rax+00h]
0x140062d0d  mov     rcx, [rdi+118h]
0x140062d14  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x140062d1b  nop     dword ptr [rax+rax+00h]
0x140062d20  lea     r8, [rbp+var_30]
0x140062d24  mov     rcx, rsi; BugCheckParameter2
0x140062d27  lea     rdx, [rbp+var_40]
0x140062d2b  call    UlpFlushPendingConsumerIo
0x140062d30  xor     eax, eax
0x140062d32  mov     byte ptr [rsi+5], 1
0x140062d36  xor     r14d, r14d
0x140062d39  cmp     ax, cs:UlNumberOfLanes
0x140062d40  jnb     short loc_140062DA1
0x140062d42  lea     r12d, [r14+28h]
0x140062d46  mov     rcx, [rdi+108h]
0x140062d4d  lea     rax, [rbp+var_40]
0x140062d51  mov     r9, rsi
0x140062d54  mov     [rsp+70h+var_50], rax
0x140062d59  lea     r8, UlpFlushWaitForDisconnects
0x140062d60  mov     rdx, r12
0x140062d63  mov     rcx, [rcx+r14*8]
0x140062d67  call    UlpEnumerateCouplings
0x140062d6c  mov     rcx, [rdi+108h]
0x140062d73  lea     rax, [rbp+var_10]
0x140062d77  mov     r9, rsi
0x140062d7a  mov     [rsp+70h+var_50], rax
0x140062d7f  lea     r8, UlpFlushCouplingRequests
0x140062d86  mov     rdx, r12
0x140062d89  mov     rcx, [rcx+r14*8]
0x140062d8d  call    UlpEnumerateCouplings
0x140062d92  movzx   eax, cs:UlNumberOfLanes
0x140062d99  inc     r14d
0x140062d9c  cmp     r14d, eax
0x140062d9f  jb      short loc_140062D46
0x140062da1  lea     rdx, [rbp+var_20]
0x140062da5  mov     rcx, rsi
0x140062da8  call    UlpFlushConsumerCallbacks
0x140062dad  mov     rcx, rsi
0x140062db0  call    UlpAttemptDetachFromRequestQueue
0x140062db5  lea     rcx, [rdi+0D8h]
0x140062dbc  mov     rax, [rcx]
0x140062dbf  cmp     rax, rcx
0x140062dc2  jz      short loc_140062DDC
0x140062dc4  cmp     byte ptr [rax+60h], 0
0x140062dc8  jz      short loc_140062DCF
0x140062dca  mov     rax, [rax]
0x140062dcd  jmp     short loc_140062DBF
0x140062dcf  xor     r14d, r14d
0x140062dd2  xor     r12b, r12b
0x140062dd5  xor     bl, bl
0x140062dd7  jmp     loc_140062E74
0x140062ddc  mov     bl, 1
0x140062dde  test    byte ptr cs:xmmword_1401A2CA0+2, 40h
0x140062de5  jz      short loc_140062E0C
0x140062de7  lea     rax, [rdi+0A0h]
0x140062dee  mov     edx, 7Ch ; '|'
0x140062df3  mov     ecx, 416h
0x140062df8  mov     [rsp+70h+var_50], rax
0x140062dfd  mov     r9, rdi
0x140062e00  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140062e07  call    WPP_SF_qZ
0x140062e0c  mov     rcx, [rdi+148h]
0x140062e13  lea     rdx, [rdi+0B0h]; Entry
0x140062e1a  add     rcx, 1038h; HashTable
0x140062e21  xor     r8d, r8d; Context
0x140062e24  call    cs:__imp_RtlRemoveEntryHashTable
0x140062e2b  nop     dword ptr [rax+rax+00h]
0x140062e30  mov     rcx, rdi
0x140062e33  mov     [rdi+152h], bl
0x140062e39  call    UlpAttemptRequestQueueCleanup
0x140062e3e  mov     rcx, rdi
0x140062e41  mov     r12b, al
0x140062e44  call    UlpCleanupRequestQueueCouplings
0x140062e49  mov     r8b, bl
0x140062e4c  lea     rdx, [rbp+var_30]
0x140062e50  mov     rcx, rdi
0x140062e53  call    UlpFlushPendingRequests
0x140062e58  mov     r14, [rdi+88h]
0x140062e5f  mov     qword ptr [rdi+88h], 0
0x140062e6a  mov     dword ptr [rdi+0F8h], 4
0x140062e74  mov     rcx, [rdi+118h]
0x140062e7b  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x140062e82  nop     dword ptr [rax+rax+00h]
0x140062e87  call    cs:__imp_KeLeaveCriticalRegion
0x140062e8e  nop     dword ptr [rax+rax+00h]
0x140062e93  mov     rcx, [rdi+148h]
0x140062e9a  xor     edx, edx
0x140062e9c  add     rcx, 1030h
0x140062ea3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140062eaa  nop     dword ptr [rax+rax+00h]
0x140062eaf  call    cs:__imp_KeLeaveCriticalRegion
0x140062eb6  nop     dword ptr [rax+rax+00h]
0x140062ebb  mov     rcx, [rbp+var_40]
0x140062ebf  lea     rax, [rbp+var_40]
0x140062ec3  cmp     rcx, rax
0x140062ec6  jz      short loc_140062F23
0x140062ec8  lea     rax, [rbp+var_40]
0x140062ecc  cmp     [rcx+8], rax
0x140062ed0  jnz     short loc_140062F1C
0x140062ed2  mov     rax, [rcx]
0x140062ed5  cmp     [rax+8], rcx
0x140062ed9  jnz     short loc_140062F1C
0x140062edb  mov     [rbp+var_40], rax
0x140062edf  lea     rdx, [rbp+var_40]
0x140062ee3  mov     [rax+8], rdx
0x140062ee7  xor     edx, edx; PriorityBoost
0x140062ee9  mov     qword ptr [rcx], 0
0x140062ef0  mov     qword ptr [rcx+8], 0
0x140062ef8  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x140062eff  mov     dword ptr [rcx+30h], 0C0000120h
0x140062f06  mov     qword ptr [rcx+38h], 0
0x140062f0e  call    cs:__imp_IofCompleteRequest
0x140062f15  nop     dword ptr [rax+rax+00h]
0x140062f1a  jmp     short loc_140062EBB
0x140062f1c  mov     ecx, 3
0x140062f21  int     29h; Win8: RtlFailFast(ecx)
0x140062f23  mov     rax, [r15+0B8h]
0x140062f2a  lea     rcx, [rbp+var_20]
0x140062f2e  or      byte ptr [rax+3], 1
0x140062f32  mov     dword ptr [r15+30h], 103h
0x140062f3a  mov     [rsi+20h], r15
0x140062f3e  call    UlpInvokeFlushedConsumerCallbacks
0x140062f43  mov     rcx, [rsi+88h]
0x140062f4a  lea     rdx, UlPurgeConsumer
0x140062f51  mov     r8, rsi
0x140062f54  call    UlPurgeZombieConnections
0x140062f59  mov     rcx, rsi
0x140062f5c  call    UlFlushCacheByConsumer
0x140062f61  test    bl, bl
0x140062f63  jz      short loc_140062F74
0x140062f65  mov     rcx, [rsi+88h]
0x140062f6c  mov     rdx, rdi
0x140062f6f  call    UlFlushCacheByRequestQueue
0x140062f74  lea     rcx, [rbp+var_10]
0x140062f78  call    UlpAbortFlushedRequests
0x140062f7d  test    bl, bl
0x140062f7f  jz      loc_140063059
0x140062f85  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140062f8c  jz      short loc_140062FAA
0x140062f8e  mov     edx, 89h
0x140062f93  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140062f9a  mov     ecx, 408h
0x140062f9f  mov     r9d, 4
0x140062fa5  call    WPP_SF_d
0x140062faa  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x140062fb1  mov     ebx, 18h
0x140062fb6  jz      short loc_140062FCF
0x140062fb8  lea     edx, [rbx+72h]
0x140062fbb  mov     ecx, 408h
0x140062fc0  mov     r9d, ebx
0x140062fc3  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x140062fca  call    WPP_SF_d
0x140062fcf  mov     r9, rsi
0x140062fd2  lea     rdx, [rbp+var_30]
0x140062fd6  mov     r8d, ebx
0x140062fd9  mov     rcx, rdi
0x140062fdc  call    UlpRejectFlushedRequests
0x140062fe1  xor     bl, bl
0x140062fe3  test    r14, r14
0x140062fe6  jz      short loc_140062FF0
0x140062fe8  mov     rcx, r14
0x140062feb  call    UlDeleteAutoServerSession
0x140062ff0  call    cs:__imp_KeEnterCriticalRegion
0x140062ff7  nop     dword ptr [rax+rax+00h]
0x140062ffc  mov     rcx, [rdi+118h]
0x140063003  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x14006300a  nop     dword ptr [rax+rax+00h]
0x14006300f  cmp     [rdi+150h], bl
0x140063015  jnz     short loc_14006301F
0x140063017  mov     bl, 1
0x140063019  mov     [rdi+150h], bl
0x14006301f  mov     rcx, [rdi+118h]
0x140063026  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x14006302d  nop     dword ptr [rax+rax+00h]
0x140063032  call    cs:__imp_KeLeaveCriticalRegion
0x140063039  nop     dword ptr [rax+rax+00h]
0x14006303e  test    bl, bl
0x140063040  jz      short loc_140063068
0x140063042  mov     rcx, [rdi+148h]
0x140063049  mov     r8d, 2
0x14006304f  mov     rdx, rdi
0x140063052  call    UlPcwDeleteInstance
0x140063057  jmp     short loc_140063068
0x140063059  mov     r8, rsi
0x14006305c  lea     rdx, [rbp+var_30]
0x140063060  mov     rcx, rdi
0x140063063  call    UlpRedeliverFlushedRequests
0x140063068  or      ebx, 0FFFFFFFFh
0x14006306b  test    r12b, r12b
0x14006306e  jz      short loc_1400630A4
0x140063070  mov     eax, ebx
0x140063072  lock xadd [rdi], eax
0x140063076  add     eax, ebx
0x140063078  cmp     cs:UxDebugCheckRefcount, 0
0x14006307f  jz      short loc_140063098
0x140063081  cmp     eax, ebx
0x140063083  jg      short loc_140063098
0x140063085  movsxd  r9, eax; BugCheckParameter4
0x140063088  lea     r8d, [rbx+2]; BugCheckParameter3
0x14006308c  mov     rdx, rdi; BugCheckParameter2
0x14006308f  lea     ecx, [rbx+4]; BugCheckParameter1
0x140063092  call    UlBugCheckEx
0x140063098  test    eax, eax
0x14006309a  jnz     short loc_1400630A4
0x14006309c  mov     rcx, rdi; P
0x14006309f  call    UlFreeRequestQueue
0x1400630a4  mov     eax, ebx
0x1400630a6  lock xadd [rsi], eax
0x1400630aa  add     eax, ebx
0x1400630ac  cmp     cs:UxDebugCheckRefcount, 0
0x1400630b3  jz      short loc_1400630CF
0x1400630b5  cmp     eax, ebx
0x1400630b7  jg      short loc_1400630CF
0x1400630b9  mov     r8d, 1; BugCheckParameter3
0x1400630bf  movsxd  r9, eax; BugCheckParameter4
0x1400630c2  mov     rdx, rsi; BugCheckParameter2
0x1400630c5  lea     ecx, [r8+2]; BugCheckParameter1
0x1400630c9  call    UlBugCheckEx
0x1400630cf  test    eax, eax
0x1400630d1  jnz     short loc_1400630DB
0x1400630d3  mov     rcx, rsi
0x1400630d6  call    UlConsumerCleanupCompletion
0x1400630db  test    byte ptr cs:xmmword_1401A2CA0+1, 1
0x1400630e2  jz      short loc_1400630FA
0x1400630e4  mov     edx, 7Dh ; '}'
0x1400630e9  lea     r8, WPP_1911597aeee73f2bcf560a2021118daf_Traceguids
0x1400630f0  mov     ecx, 408h
0x1400630f5  call    WPP_SF_
0x1400630fa  add     rsp, 70h
0x1400630fe  pop     r15
0x140063100  pop     r14
0x140063102  pop     r12
0x140063104  pop     rdi
0x140063105  pop     rsi
0x140063106  pop     rbx
0x140063107  pop     rbp
0x140063108  retn
```
