# UlCopyRequestQueueCounters

- ea: `0x1c00296fc`
- end: `0x1c002987e`
- name: `UlCopyRequestQueueCounters`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1c0146288`

## callees

- `0x1c00296fc`
- `0x1c008f3ec`
- `0x1c008f680`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c00297d0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c00297d0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c00297a4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c00297a4`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00297ef`
- `ntoskrnl!ExReleaseCacheAwarePushLockSharedEx` at `0x1c00297ef`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c0029770`
- `ntoskrnl!ExAcquireCacheAwarePushLockSharedEx` at `0x1c0029770`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00297fb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00297fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c002975b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c002975b`

## pseudocode

```c
__int64 __fastcall UlCopyRequestQueueCounters(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rbx
  int v5; // r15d
  unsigned __int16 v6; // r14
  __int64 i; // r12
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 result; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-38h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qq(245, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, a2);
  v4 = 0x7FFFFFFFFFFFFFFFLL;
  v5 = 0;
  KeEnterCriticalRegion();
  v6 = 0;
  for ( i = ExAcquireCacheAwarePushLockSharedEx(a1[35], 0); v6 < (unsigned __int16)UlNumberOfLanes; ++v6 )
  {
    v8 = *(_QWORD *)(a1[36] + 8LL * v6);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v8, &LockHandle);
    v5 += *(_DWORD *)(v8 + 72);
    v9 = *(_QWORD *)(v8 + 40);
    if ( v9 != v8 + 40 && *(_QWORD *)(v9 + 72) < v4 )
      v4 = *(_QWORD *)(v9 + 72);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  ExReleaseCacheAwarePushLockSharedEx(i, 0);
  KeLeaveCriticalRegion();
  *(_QWORD *)(a2 + 16) = a1[12];
  *(_QWORD *)(a2 + 24) = a1[13];
  *(_QWORD *)(a2 + 32) = a1[14];
  *(_QWORD *)(a2 + 8) = v4;
  *(_DWORD *)(a2 + 4) = v5;
  *(_QWORD *)(a2 + 40) = MEMORY[0xFFFFF78000000014];
  *(_QWORD *)(a2 + 48) = 10000000;
  result = LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    return WPP_SF_q(246, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a2);
  return result;
}

```

## disassembly

```asm
0x1c00296fc  mov     r11, rsp
0x1c00296ff  mov     [r11+8], rbx
0x1c0029703  mov     [r11+10h], rbp
0x1c0029707  mov     [r11+18h], rsi
0x1c002970b  mov     [r11+20h], rdi
0x1c002970f  push    r12
0x1c0029711  push    r14
0x1c0029713  push    r15
0x1c0029715  sub     rsp, 40h
0x1c0029719  xorps   xmm0, xmm0
0x1c002971c  xor     eax, eax
0x1c002971e  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x1c0029723  mov     [r11-28h], rax
0x1c0029727  mov     rsi, rdx
0x1c002972a  mov     rbp, rcx
0x1c002972d  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0029733  test    al, al
0x1c0029735  jns     short loc_1C002974E
0x1c0029737  mov     r9, rdx
0x1c002973a  mov     ecx, 0F5h
0x1c002973f  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0029746  mov     r8, rbp
0x1c0029749  call    WPP_SF_qq
0x1c002974e  mov     rbx, 7FFFFFFFFFFFFFFFh
0x1c0029758  xor     r15d, r15d
0x1c002975b  call    cs:__imp_KeEnterCriticalRegion
0x1c0029762  nop     dword ptr [rax+rax+00h]
0x1c0029767  mov     rcx, [rbp+118h]
0x1c002976e  xor     edx, edx
0x1c0029770  call    cs:__imp_ExAcquireCacheAwarePushLockSharedEx
0x1c0029777  nop     dword ptr [rax+rax+00h]
0x1c002977c  cmp     r15w, cs:UlNumberOfLanes
0x1c0029784  movzx   r14d, r15w
0x1c0029788  mov     r12, rax
0x1c002978b  jnb     short loc_1C00297EA
0x1c002978d  mov     rcx, [rbp+120h]
0x1c0029794  movzx   edx, r14w
0x1c0029798  mov     rdi, [rcx+rdx*8]
0x1c002979c  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x1c00297a1  mov     rcx, rdi; SpinLock
0x1c00297a4  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c00297ab  nop     dword ptr [rax+rax+00h]
0x1c00297b0  add     r15d, [rdi+48h]
0x1c00297b4  lea     rax, [rdi+28h]
0x1c00297b8  mov     rcx, [rax]
0x1c00297bb  cmp     rcx, rax
0x1c00297be  jz      short loc_1C00297CB
0x1c00297c0  mov     rax, [rcx+48h]
0x1c00297c4  cmp     rax, rbx
0x1c00297c7  cmovl   rbx, rax
0x1c00297cb  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x1c00297d0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1c00297d7  nop     dword ptr [rax+rax+00h]
0x1c00297dc  inc     r14w
0x1c00297e0  cmp     r14w, cs:UlNumberOfLanes
0x1c00297e8  jb      short loc_1C002978D
0x1c00297ea  xor     edx, edx
0x1c00297ec  mov     rcx, r12
0x1c00297ef  call    cs:__imp_ExReleaseCacheAwarePushLockSharedEx
0x1c00297f6  nop     dword ptr [rax+rax+00h]
0x1c00297fb  call    cs:__imp_KeLeaveCriticalRegion
0x1c0029802  nop     dword ptr [rax+rax+00h]
0x1c0029807  mov     rax, [rbp+60h]
0x1c002980b  mov     [rsi+10h], rax
0x1c002980f  mov     rax, [rbp+68h]
0x1c0029813  mov     [rsi+18h], rax
0x1c0029817  mov     rax, [rbp+70h]
0x1c002981b  mov     [rsi+20h], rax
0x1c002981f  mov     rax, 0FFFFF78000000014h
0x1c0029829  mov     [rsi+8], rbx
0x1c002982d  mov     [rsi+4], r15d
0x1c0029831  mov     rax, [rax]
0x1c0029834  mov     [rsi+28h], rax
0x1c0029838  mov     qword ptr [rsi+30h], 989680h
0x1c0029840  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0029846  test    al, al
0x1c0029848  jns     short loc_1C002985E
0x1c002984a  mov     ecx, 0F6h
0x1c002984f  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0029856  mov     r8, rsi
0x1c0029859  call    WPP_SF_q
0x1c002985e  mov     rbx, [rsp+58h+arg_0]
0x1c0029863  mov     rbp, [rsp+58h+arg_8]
0x1c0029868  mov     rsi, [rsp+58h+arg_10]
0x1c002986d  mov     rdi, [rsp+58h+arg_18]
0x1c0029872  add     rsp, 40h
0x1c0029876  pop     r15
0x1c0029878  pop     r14
0x1c002987a  pop     r12
0x1c002987c  retn
```
