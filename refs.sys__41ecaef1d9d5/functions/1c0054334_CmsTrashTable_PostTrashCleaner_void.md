# CmsTrashTable::PostTrashCleaner(void)

- ea: `0x1c0054334`
- end: `0x1c005439e`
- name: `?PostTrashCleaner@CmsTrashTable@@AEAAXXZ`
- size: `106`
- prototype: `void __fastcall(CmsTrashTable *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1c00541f4`
- `0x1c00d19cc`
- `0x1c00d1c8c`
- `0x1c00d2394`
- `0x1c00d23e8`

## callees

- `0x1c004ef58`
- `0x1c0054334`
- `0x1c006af80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c008855c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c008855c`
- `ntoskrnl!KeClearEvent` at `0x1c008859a`
- `ntoskrnl!KeClearEvent` at `0x1c008859a`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0088607`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0088607`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c00885b0`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c00885b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0054357`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0054357`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0054376`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c0054376`
- `ntoskrnl!IoTransferActivityId` at `0x1c00885c9`
- `ntoskrnl!IoTransferActivityId` at `0x1c00885e0`
- `ntoskrnl!IoTransferActivityId` at `0x1c00885c9`
- `ntoskrnl!IoTransferActivityId` at `0x1c00885e0`

## pseudocode

```c
void __fastcall CmsTrashTable::PostTrashCleaner(CmsTrashTable *this)
{
  KSPIN_LOCK *v1; // rsi
  KIRQL v3; // r14
  struct _MS_WORK_QUEUE_ITEM *PoolWithTag; // rax
  struct _MS_WORK_QUEUE_ITEM *v5; // rdi
  char *v6; // rbp
  __int64 v7; // rax
  char *v8; // rcx
  __int64 v9; // rbx

  v1 = (KSPIN_LOCK *)((char *)this + 40);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
  if ( *((_BYTE *)this + 16)
    && !*((_BYTE *)this + 17)
    && (*((CmsTrashTable **)this + 3) != (CmsTrashTable *)((char *)this + 24) || *((_BYTE *)this + 19))
    && *((_DWORD *)this + 15) < (unsigned int)dword_1C0136874
    && (!*((_BYTE *)this + 19) || !*((_BYTE *)this + 56)) )
  {
    PoolWithTag = (struct _MS_WORK_QUEUE_ITEM *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x48u, 0x6950534Du);
    v5 = PoolWithTag;
    if ( PoolWithTag )
      memset(PoolWithTag, 0, 0x48u);
    else
      v5 = 0;
    if ( v5 )
    {
      *((_QWORD *)v5 + 8) = this;
      *((_BYTE *)this + 17) = 0;
      *((_BYTE *)this + 56) = 1;
      KeClearEvent((PRKEVENT)this + 3);
      ++*((_DWORD *)this + 15);
      v6 = (char *)this + 96;
      v7 = IoSetActivityIdThread((char *)this + 96);
      v8 = (char *)this + 96;
      v9 = v7;
      IoTransferActivityId(v8, &MsActivityIdTrashTable);
      if ( v9 )
        IoTransferActivityId(v6, v9);
      MsInitializeAndQueueWorkItem(v5, (void (*)(void *))CmsTrashTable::TrashCleanerWorkerFn, v5, DelayedWorkQueue);
      IoClearActivityIdThread(v9);
    }
  }
  KeReleaseSpinLock(v1, v3);
}

```

## disassembly

```asm
0x1c0054334  mov     rax, rsp
0x1c0054337  mov     [rax+8], rbx
0x1c005433b  mov     [rax+10h], rbp
0x1c005433f  mov     [rax+18h], rsi
0x1c0054343  mov     [rax+20h], rdi
0x1c0054347  push    r14
0x1c0054349  sub     rsp, 20h
0x1c005434d  lea     rsi, [rcx+28h]
0x1c0054351  mov     rbx, rcx
0x1c0054354  mov     rcx, rsi; SpinLock
0x1c0054357  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1c005435e  nop     dword ptr [rax+rax+00h]
0x1c0054363  cmp     byte ptr [rbx+10h], 0
0x1c0054367  mov     r14b, al
0x1c005436a  jnz     loc_1C008850E
0x1c0054370  mov     dl, r14b; NewIrql
0x1c0054373  mov     rcx, rsi; SpinLock
0x1c0054376  call    cs:__imp_KeReleaseSpinLock
0x1c005437d  nop     dword ptr [rax+rax+00h]
0x1c0054382  mov     rbx, [rsp+28h+arg_0]
0x1c0054387  mov     rbp, [rsp+28h+arg_8]
0x1c005438c  mov     rsi, [rsp+28h+arg_10]
0x1c0054391  mov     rdi, [rsp+28h+arg_18]
0x1c0054396  add     rsp, 20h
0x1c005439a  pop     r14
0x1c005439c  retn
0x1c008850e  cmp     byte ptr [rbx+11h], 0
0x1c0088512  jnz     loc_1C0054370
0x1c0088518  lea     rdx, [rbx+18h]
0x1c008851c  cmp     [rdx], rdx
0x1c008851f  jnz     short loc_1C008852B
0x1c0088521  cmp     byte ptr [rbx+13h], 0
0x1c0088525  jz      loc_1C0054370
0x1c008852b  mov     eax, cs:dword_1C0136874
0x1c0088531  cmp     [rbx+3Ch], eax
0x1c0088534  jnb     loc_1C0054370
0x1c008853a  cmp     byte ptr [rbx+13h], 0
0x1c008853e  jz      short loc_1C008854A
0x1c0088540  cmp     byte ptr [rbx+38h], 0
0x1c0088544  jnz     loc_1C0054370
0x1c008854a  mov     ebp, 48h ; 'H'
0x1c008854f  mov     r8d, 6950534Dh; Tag
0x1c0088555  mov     edx, ebp; NumberOfBytes
0x1c0088557  mov     ecx, 200h; PoolType
0x1c008855c  call    cs:__imp_ExAllocatePoolWithTag
0x1c0088563  nop     dword ptr [rax+rax+00h]
0x1c0088568  mov     rdi, rax
0x1c008856b  test    rax, rax
0x1c008856e  jz      short loc_1C008857F
0x1c0088570  mov     r8d, ebp; Size
0x1c0088573  xor     edx, edx; Val
0x1c0088575  mov     rcx, rax; void *
0x1c0088578  call    memset
0x1c008857d  jmp     short loc_1C0088581
0x1c008857f  xor     edi, edi
0x1c0088581  test    rdi, rdi
0x1c0088584  jz      loc_1C0054370
0x1c008858a  mov     [rdi+40h], rbx
0x1c008858e  lea     rcx, [rbx+48h]; Event
0x1c0088592  mov     byte ptr [rbx+11h], 0
0x1c0088596  mov     byte ptr [rbx+38h], 1
0x1c008859a  call    cs:__imp_KeClearEvent
0x1c00885a1  nop     dword ptr [rax+rax+00h]
0x1c00885a6  inc     dword ptr [rbx+3Ch]
0x1c00885a9  lea     rbp, [rbx+60h]
0x1c00885ad  mov     rcx, rbp
0x1c00885b0  call    cs:__imp_IoSetActivityIdThread
0x1c00885b7  nop     dword ptr [rax+rax+00h]
0x1c00885bc  lea     rdx, ?MsActivityIdTrashTable@@3U_GUID@@B; _GUID const MsActivityIdTrashTable
0x1c00885c3  mov     rcx, rbp
0x1c00885c6  mov     rbx, rax
0x1c00885c9  call    cs:__imp_IoTransferActivityId
0x1c00885d0  nop     dword ptr [rax+rax+00h]
0x1c00885d5  test    rbx, rbx
0x1c00885d8  jz      short loc_1C00885EC
0x1c00885da  mov     rdx, rbx
0x1c00885dd  mov     rcx, rbp
0x1c00885e0  call    cs:__imp_IoTransferActivityId
0x1c00885e7  nop     dword ptr [rax+rax+00h]
0x1c00885ec  mov     r9d, 1; enum _WORK_QUEUE_TYPE
0x1c00885f2  lea     rdx, ?TrashCleanerWorkerFn@CmsTrashTable@@CAXPEAX@Z; void (*)(void *)
0x1c00885f9  mov     r8, rdi; void *
0x1c00885fc  mov     rcx, rdi; struct _MS_WORK_QUEUE_ITEM *
0x1c00885ff  call    ?MsInitializeAndQueueWorkItem@@YAXPEAU_MS_WORK_QUEUE_ITEM@@P6AXPEAX@Z1W4_WORK_QUEUE_TYPE@@@Z; MsInitializeAndQueueWorkItem(_MS_WORK_QUEUE_ITEM *,void (*)(void *),void *,_WORK_QUEUE_TYPE)
0x1c0088604  mov     rcx, rbx
0x1c0088607  call    cs:__imp_IoClearActivityIdThread
0x1c008860e  nop     dword ptr [rax+rax+00h]
0x1c0088613  nop
0x1c0088614  jmp     loc_1C0054370
```
