# UlpSetRequestQueueLengthLimit

- ea: `0x1c0029ee4`
- end: `0x1c002a023`
- name: `UlpSetRequestQueueLengthLimit`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1c0101ab0`

## callees

- `0x1c0029ee4`
- `0x1c008f21c`
- `0x1c008f570`
- `0x1c0090124`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0029fb5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1c0029fb5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0029f99`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1c0029f99`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0029fd4`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c0029fd4`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0029f73`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c0029f73`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0029fe0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0029fe0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0029f60`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0029f60`

## pseudocode

```c
__int64 __fastcall UlpSetRequestQueueLengthLimit(__int64 a1, unsigned int a2)
{
  unsigned int v4; // r14d
  unsigned __int16 i; // bp
  __int64 v6; // rbx
  __int64 result; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qD(128, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, a1, a2);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x200000) != 0 )
    WPP_SF_qZLH(a1, a2, a1, a1 + 152, a2);
  v4 = a2 / (unsigned __int16)UlNumberOfLanes;
  KeEnterCriticalRegion();
  ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 280));
  for ( i = 0; i < (unsigned __int16)UlNumberOfLanes; ++i )
  {
    v6 = *(_QWORD *)(*(_QWORD *)(a1 + 288) + 8LL * i);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v6, &LockHandle);
    *(_DWORD *)(v6 + 96) = a2;
    *(_DWORD *)(v6 + 100) = v4;
    *(_DWORD *)(v6 + 104) = v4;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(a1 + 280));
  KeLeaveCriticalRegion();
  result = LODWORD(WPP_MAIN_CB.Queue.ListEntry.Flink);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    return WPP_SF_(130, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1c0029ee4  mov     r11, rsp
0x1c0029ee7  mov     [r11+8], rbx
0x1c0029eeb  mov     [r11+10h], rbp
0x1c0029eef  mov     [r11+18h], rsi
0x1c0029ef3  mov     [r11+20h], rdi
0x1c0029ef7  push    r14
0x1c0029ef9  sub     rsp, 50h
0x1c0029efd  xorps   xmm0, xmm0
0x1c0029f00  xor     eax, eax
0x1c0029f02  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x1c0029f07  mov     [r11-18h], rax
0x1c0029f0b  mov     esi, edx
0x1c0029f0d  mov     rdi, rcx
0x1c0029f10  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0029f16  test    al, al
0x1c0029f18  jns     short loc_1C0029F31
0x1c0029f1a  mov     r9d, edx
0x1c0029f1d  mov     ecx, 80h
0x1c0029f22  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0029f29  mov     r8, rdi
0x1c0029f2c  call    WPP_SF_qD
0x1c0029f31  test    dword ptr cs:WPP_MAIN_CB.Queue, 200000h
0x1c0029f3b  jz      short loc_1C0029F50
0x1c0029f3d  lea     r9, [rdi+98h]
0x1c0029f44  mov     [rsp+58h+var_38], esi
0x1c0029f48  mov     r8, rdi
0x1c0029f4b  call    WPP_SF_qZLH
0x1c0029f50  movzx   ecx, cs:UlNumberOfLanes
0x1c0029f57  xor     edx, edx
0x1c0029f59  mov     eax, esi
0x1c0029f5b  div     ecx
0x1c0029f5d  mov     r14d, eax
0x1c0029f60  call    cs:__imp_KeEnterCriticalRegion
0x1c0029f67  nop     dword ptr [rax+rax+00h]
0x1c0029f6c  mov     rcx, [rdi+118h]
0x1c0029f73  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c0029f7a  nop     dword ptr [rax+rax+00h]
0x1c0029f7f  xor     ebp, ebp
0x1c0029f81  jmp     short loc_1C0029FC4
0x1c0029f83  mov     rax, [rdi+120h]
0x1c0029f8a  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x1c0029f8f  movzx   ecx, bp
0x1c0029f92  mov     rbx, [rax+rcx*8]
0x1c0029f96  mov     rcx, rbx; SpinLock
0x1c0029f99  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1c0029fa0  nop     dword ptr [rax+rax+00h]
0x1c0029fa5  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x1c0029faa  mov     [rbx+60h], esi
0x1c0029fad  mov     [rbx+64h], r14d
0x1c0029fb1  mov     [rbx+68h], r14d
0x1c0029fb5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1c0029fbc  nop     dword ptr [rax+rax+00h]
0x1c0029fc1  inc     bp
0x1c0029fc4  cmp     bp, cs:UlNumberOfLanes
0x1c0029fcb  jb      short loc_1C0029F83
0x1c0029fcd  mov     rcx, [rdi+118h]
0x1c0029fd4  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c0029fdb  nop     dword ptr [rax+rax+00h]
0x1c0029fe0  call    cs:__imp_KeLeaveCriticalRegion
0x1c0029fe7  nop     dword ptr [rax+rax+00h]
0x1c0029fec  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0029ff2  test    al, al
0x1c0029ff4  jns     short loc_1C002A007
0x1c0029ff6  mov     ecx, 82h
0x1c0029ffb  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c002a002  call    WPP_SF_
0x1c002a007  mov     rbx, [rsp+58h+arg_0]
0x1c002a00c  mov     rbp, [rsp+58h+arg_8]
0x1c002a011  mov     rsi, [rsp+58h+arg_10]
0x1c002a016  mov     rdi, [rsp+58h+arg_18]
0x1c002a01b  add     rsp, 50h
0x1c002a01f  pop     r14
0x1c002a021  retn
```
