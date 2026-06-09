# RxRegisterSrvOpenWithBufferingManager

- ea: `0x14000c000`
- end: `0x14000c1b2`
- name: `RxRegisterSrvOpenWithBufferingManager`
- size: `434`
- prototype: `__int64 __fastcall(PVOID Instance)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x140002120`
- `0x14000c000`
- `0x14000c660`
- `0x140016e70`
- `0x14005f110`
- `0x140074ec0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000c0f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002767a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c0f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002767a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000c08a`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000c08a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000c15e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000c15e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c171`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c171`

## pseudocode

```c
void __fastcall RxRegisterSrvOpenWithBufferingManager(_QWORD *Instance)
{
  __int64 v2; // rcx
  int v3; // edx
  __int64 pContext; // rdi
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  KIRQL v7; // al
  struct _LIST_ENTRY DiscardedRequests; // [rsp+30h] [rbp-18h] BYREF

  v2 = Instance[4];
  DiscardedRequests = 0;
  if ( (unsigned __int16)(*(_WORD *)v2 + 5087) <= 1u && !*(_BYTE *)(*(_QWORD *)(v2 + 120) + 77LL) )
  {
    v3 = *((_DWORD *)Instance + 18);
    if ( (v3 & 0x300) == 0 && (*(_DWORD *)(v2 + 156) & 0x10) == 0 )
    {
      pContext = *(_QWORD *)(*(_QWORD *)(Instance[5] + 32LL) + 32LL);
      DiscardedRequests.Blink = &DiscardedRequests;
      *((_DWORD *)Instance + 18) = v3 | 0x100;
      DiscardedRequests.Flink = &DiscardedRequests;
      ExAcquireFastMutex((PFAST_MUTEX)(pContext + 520));
      v5 = pContext
         + 16
         * ((((unsigned __int8)(*((_BYTE *)Instance + 104)
                              ^ *((_BYTE *)Instance + 112)
                              ^ ((Instance[13] ^ Instance[14]) >> 32)
                              ^ ((*((_DWORD *)Instance + 26)
                                ^ *((_DWORD *)Instance + 28)
                                ^ (unsigned int)((Instance[13] ^ Instance[14]) >> 32)) >> 16))
            ^ ((unsigned __int16)(*((_WORD *)Instance + 52)
                                ^ *((_WORD *)Instance + 56)
                                ^ ((Instance[13] ^ Instance[14]) >> 32)
                                ^ ((*((_DWORD *)Instance + 26)
                                  ^ *((_DWORD *)Instance + 28)
                                  ^ (unsigned int)((Instance[13] ^ Instance[14]) >> 32)) >> 16)) >> 8))
           & 0x8000000F)
          + 36LL);
      v6 = *(_QWORD **)(v5 + 8);
      if ( *v6 != v5 )
        __fastfail(3u);
      Instance[26] = v5;
      Instance[27] = v6;
      *v6 = Instance + 26;
      *(_QWORD *)(v5 + 8) = Instance + 26;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 33, &WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, Instance);
      }
      RxpDispatchChangeBufferingStateRequests((PVOID)pContext, Instance);
      ExReleaseFastMutex((PFAST_MUTEX)(pContext + 520));
      v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(pContext + 264));
      if ( *(_QWORD *)(pContext + 296) == pContext + 296 || *(_BYTE *)(pContext + 257) )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(pContext + 264), v7);
      }
      else
      {
        *(_BYTE *)(pContext + 257) = 1;
        KeReleaseSpinLock((PKSPIN_LOCK)(pContext + 264), v7);
        RxReference((PVOID)pContext);
        RxPostToWorkerThread(
          RxFileSystemDeviceObject,
          RealTimeWorkQueue,
          (PRX_WORK_QUEUE_ITEM)(pContext + 392),
          (PRX_WORKERTHREAD_ROUTINE)RxProcessChangeBufferingStateRequests,
          (PVOID)pContext);
      }
      RxpDiscardChangeBufferingStateRequests(&DiscardedRequests);
    }
  }
}

```

## disassembly

```asm
0x14000c000  push    rbx
0x14000c002  sub     rsp, 40h
0x14000c006  mov     rbx, rcx
0x14000c009  xorps   xmm0, xmm0
0x14000c00c  mov     rcx, [rcx+20h]
0x14000c010  mov     eax, 13DFh
0x14000c015  movups  xmmword ptr [rsp+48h+DiscardedRequests.Flink], xmm0
0x14000c01a  add     ax, [rcx]
0x14000c01d  cmp     ax, 1
0x14000c021  ja      loc_14000C111
0x14000c027  mov     rax, [rcx+78h]
0x14000c02b  cmp     byte ptr [rax+4Dh], 0
0x14000c02f  jnz     loc_14000C111
0x14000c035  mov     edx, [rbx+48h]
0x14000c038  test    edx, 300h
0x14000c03e  jnz     loc_14000C111
0x14000c044  mov     eax, [rcx+9Ch]
0x14000c04a  test    al, 10h
0x14000c04c  jnz     loc_14000C111
0x14000c052  mov     rax, [rbx+28h]
0x14000c056  bts     edx, 8
0x14000c05a  mov     [rsp+48h+arg_0], rsi
0x14000c05f  mov     [rsp+48h+arg_8], rdi
0x14000c064  mov     rcx, [rax+20h]
0x14000c068  lea     rax, [rsp+48h+DiscardedRequests]
0x14000c06d  mov     rdi, [rcx+20h]
0x14000c071  mov     [rsp+48h+DiscardedRequests.Blink], rax
0x14000c076  lea     rax, [rsp+48h+DiscardedRequests]
0x14000c07b  mov     [rbx+48h], edx
0x14000c07e  mov     [rsp+48h+DiscardedRequests.Flink], rax
0x14000c083  lea     rcx, [rdi+208h]; FastMutex
0x14000c08a  call    cs:__imp_ExAcquireFastMutex
0x14000c091  nop     dword ptr [rax+rax+00h]
0x14000c096  mov     rcx, [rbx+70h]
0x14000c09a  xor     rcx, [rbx+68h]
0x14000c09e  mov     rdx, rcx
0x14000c0a1  shr     rdx, 20h
0x14000c0a5  xor     edx, ecx
0x14000c0a7  mov     eax, edx
0x14000c0a9  shr     eax, 10h
0x14000c0ac  xor     ax, dx
0x14000c0af  movzx   ecx, ax
0x14000c0b2  mov     eax, ecx
0x14000c0b4  movzx   ecx, cl
0x14000c0b7  shr     eax, 8
0x14000c0ba  xor     eax, ecx
0x14000c0bc  and     eax, 8000000Fh
0x14000c0c1  jge     short loc_14000C0CA
0x14000c0c3  dec     eax
0x14000c0c5  or      eax, 0FFFFFFF0h
0x14000c0c8  inc     eax
0x14000c0ca  mov     edx, eax
0x14000c0cc  add     rdx, 24h ; '$'
0x14000c0d0  shl     rdx, 4
0x14000c0d4  add     rdx, rdi
0x14000c0d7  mov     rcx, [rdx+8]
0x14000c0db  cmp     [rcx], rdx
0x14000c0de  jz      short loc_14000C118
0x14000c0e0  mov     ecx, 3
0x14000c0e5  int     29h; Win8: RtlFailFast(ecx)
0x14000c0e7  movzx   edx, al; NewIrql
0x14000c0ea  lea     rcx, [rdi+108h]; SpinLock
0x14000c0f1  call    cs:__imp_KeReleaseSpinLock
0x14000c0f8  nop     dword ptr [rax+rax+00h]
0x14000c0fd  lea     rcx, [rsp+48h+DiscardedRequests]; DiscardedRequests
0x14000c102  call    RxpDiscardChangeBufferingStateRequests
0x14000c107  mov     rsi, [rsp+48h+arg_0]
0x14000c10c  mov     rdi, [rsp+48h+arg_8]
0x14000c111  add     rsp, 40h
0x14000c115  pop     rbx
0x14000c116  retn
0x14000c118  lea     rax, [rbx+0D0h]
0x14000c11f  mov     [rax], rdx
0x14000c122  mov     [rax+8], rcx
0x14000c126  mov     [rcx], rax
0x14000c129  mov     [rdx+8], rax
0x14000c12d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c134  lea     rax, WPP_GLOBAL_Control
0x14000c13b  cmp     rcx, rax
0x14000c13e  jz      short loc_14000C147
0x14000c140  mov     eax, [rcx+2Ch]
0x14000c143  test    al, 40h
0x14000c145  jnz     short loc_14000C192
0x14000c147  lea     r8, [rsp+48h+DiscardedRequests]
0x14000c14c  mov     rdx, rbx; Instance
0x14000c14f  mov     rcx, rdi; pContext
0x14000c152  call    RxpDispatchChangeBufferingStateRequests
0x14000c157  lea     rcx, [rdi+208h]; FastMutex
0x14000c15e  call    cs:__imp_ExReleaseFastMutex
0x14000c165  nop     dword ptr [rax+rax+00h]
0x14000c16a  lea     rcx, [rdi+108h]; SpinLock
0x14000c171  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c178  nop     dword ptr [rax+rax+00h]
0x14000c17d  lea     rdx, [rdi+128h]
0x14000c184  cmp     [rdx], rdx
0x14000c187  jz      loc_14000C0E7
0x14000c18d  jmp     loc_14002765C
0x14000c192  cmp     byte ptr [rcx+29h], 2
0x14000c196  jb      short loc_14000C147
0x14000c198  mov     rcx, [rcx+18h]
0x14000c19c  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x14000c1a3  mov     edx, 21h ; '!'
0x14000c1a8  mov     r9, rbx
0x14000c1ab  call    WPP_SF_q
0x14000c1b0  jmp     short loc_14000C147
0x14002765c  cmp     byte ptr [rdi+101h], 0
0x140027663  jnz     loc_14000C0E7
0x140027669  movzx   edx, al; NewIrql
0x14002766c  mov     byte ptr [rdi+101h], 1
0x140027673  lea     rcx, [rdi+108h]; SpinLock
0x14002767a  call    cs:__imp_KeReleaseSpinLock
0x140027681  nop     dword ptr [rax+rax+00h]
0x140027686  mov     rcx, rdi; Instance
0x140027689  call    RxReference
0x14002768e  mov     rcx, cs:RxFileSystemDeviceObject; pMRxDeviceObject
0x140027695  lea     r8, [rdi+188h]; pWorkQueueItem
0x14002769c  lea     r9, RxProcessChangeBufferingStateRequests; Routine
0x1400276a3  mov     [rsp+48h+pContext], rdi; pContext
0x1400276a8  mov     edx, 5; WorkQueueType
0x1400276ad  call    RxPostToWorkerThread
0x1400276b2  nop
0x1400276b3  jmp     loc_14000C0FD
```
