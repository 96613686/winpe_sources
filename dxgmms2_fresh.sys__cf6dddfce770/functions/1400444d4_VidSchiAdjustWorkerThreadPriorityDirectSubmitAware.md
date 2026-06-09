# VidSchiAdjustWorkerThreadPriorityDirectSubmitAware

- ea: `0x1400444d4`
- end: `0x140044622`
- name: `VidSchiAdjustWorkerThreadPriorityDirectSubmitAware`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001fad0`

## callees

- `0x14002d330`
- `0x1400444d4`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140044568`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400445ed`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140044568`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400445ed`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400445c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004460a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400445c6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004460a`
- `ntoskrnl!KeQueryPriorityThread` at `0x140044516`
- `ntoskrnl!KeQueryPriorityThread` at `0x140044536`
- `ntoskrnl!KeQueryPriorityThread` at `0x1400445b2`
- `ntoskrnl!KeQueryPriorityThread` at `0x140044516`
- `ntoskrnl!KeQueryPriorityThread` at `0x140044536`
- `ntoskrnl!KeQueryPriorityThread` at `0x1400445b2`
- `ntoskrnl!KeSetPriorityThread` at `0x1400445dc`
- `ntoskrnl!KeSetPriorityThread` at `0x1400445dc`

## pseudocode

```c
void __fastcall VidSchiAdjustWorkerThreadPriorityDirectSubmitAware(__int64 a1)
{
  __int64 v1; // rax
  struct _KTHREAD *CurrentThread; // rcx
  __int64 v4; // rbx
  struct _KTHREAD *v5; // rdx
  unsigned int v6; // esi
  struct _ERESOURCE *i; // rdi
  int v8; // eax
  struct _ERESOURCE *v9; // rcx
  KPRIORITY v10; // r14d

  v1 = *(_QWORD *)(a1 + 96);
  CurrentThread = KeGetCurrentThread();
  v4 = *(_QWORD *)(v1 + 24);
  v5 = *(struct _KTHREAD **)(v4 + 176);
  if ( (*(_DWORD *)(v4 + 2904) & 0x20) == 0 )
  {
    if ( CurrentThread == v5 )
      return;
    v9 = (struct _ERESOURCE *)(v4 + 1336);
    goto LABEL_16;
  }
  if ( CurrentThread != v5 )
  {
    v6 = 31;
    if ( KeQueryPriorityThread(KeGetCurrentThread()) + 1 < 31 )
      v6 = KeQueryPriorityThread(KeGetCurrentThread()) + 1;
    for ( i = (struct _ERESOURCE *)(v4 + 1336); ; ExAcquireResourceExclusiveLite(i, 1u) )
    {
LABEL_8:
      v8 = *(_DWORD *)(a1 + 788);
      if ( KeGetCurrentThread() == *(struct _KTHREAD **)(v4 + 176) )
      {
        if ( v8 )
          break;
      }
      else if ( !v8 )
      {
        break;
      }
      v10 = VidSchiComputeWorkerThreadPriority(a1, v6);
      if ( v10 == KeQueryPriorityThread(*(PKTHREAD *)(v4 + 176)) )
        break;
      ExReleaseResourceLite(i);
      KeSetPriorityThread(*(PKTHREAD *)(v4 + 176), v10);
    }
    v9 = i;
LABEL_16:
    ExReleaseResourceLite(v9);
    return;
  }
  if ( !*(_DWORD *)(a1 + 788) )
  {
    i = (struct _ERESOURCE *)(v4 + 1336);
    ExAcquireResourceExclusiveLite((PERESOURCE)(v4 + 1336), 1u);
    v6 = 16;
    goto LABEL_8;
  }
}

```

## disassembly

```asm
0x1400444d4  push    rbx
0x1400444d6  push    rbp
0x1400444d7  push    rsi
0x1400444d8  push    rdi
0x1400444d9  push    r14
0x1400444db  sub     rsp, 20h
0x1400444df  mov     rax, [rcx+60h]
0x1400444e3  mov     rbp, rcx
0x1400444e6  mov     rcx, gs:188h
0x1400444ef  mov     rbx, [rax+18h]
0x1400444f3  mov     eax, [rbx+0B58h]
0x1400444f9  mov     rdx, [rbx+0B0h]
0x140044500  test    al, 20h
0x140044502  jz      loc_1400445FE
0x140044508  cmp     rcx, rdx
0x14004450b  jz      short loc_14004454E
0x14004450d  mov     rcx, gs:188h; Thread
0x140044516  call    cs:__imp_KeQueryPriorityThread
0x14004451d  nop     dword ptr [rax+rax+00h]
0x140044522  inc     eax
0x140044524  mov     esi, 1Fh
0x140044529  cmp     eax, esi
0x14004452b  jge     short loc_140044545
0x14004452d  mov     rcx, gs:188h; Thread
0x140044536  call    cs:__imp_KeQueryPriorityThread
0x14004453d  nop     dword ptr [rax+rax+00h]
0x140044542  lea     esi, [rax+1]
0x140044545  lea     rdi, [rbx+538h]
0x14004454c  jmp     short loc_140044579
0x14004454e  mov     eax, [rbp+314h]
0x140044554  test    eax, eax
0x140044556  jnz     loc_140044616
0x14004455c  lea     rdi, [rbx+538h]
0x140044563  mov     dl, 1; Wait
0x140044565  mov     rcx, rdi; Resource
0x140044568  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004456f  nop     dword ptr [rax+rax+00h]
0x140044574  mov     esi, 10h
0x140044579  mov     rax, gs:188h
0x140044582  cmp     rax, [rbx+0B0h]
0x140044589  mov     eax, [rbp+314h]
0x14004458f  jnz     short loc_14004459A
0x140044591  test    eax, eax
0x140044593  jz      short loc_14004459E
0x140044595  mov     rcx, rdi
0x140044598  jmp     short loc_14004460A
0x14004459a  test    eax, eax
0x14004459c  jz      short loc_140044595
0x14004459e  mov     edx, esi
0x1400445a0  mov     rcx, rbp
0x1400445a3  call    VidSchiComputeWorkerThreadPriority
0x1400445a8  mov     rcx, [rbx+0B0h]; Thread
0x1400445af  mov     r14d, eax
0x1400445b2  call    cs:__imp_KeQueryPriorityThread
0x1400445b9  nop     dword ptr [rax+rax+00h]
0x1400445be  cmp     r14d, eax
0x1400445c1  jz      short loc_140044595
0x1400445c3  mov     rcx, rdi; Resource
0x1400445c6  call    cs:__imp_ExReleaseResourceLite
0x1400445cd  nop     dword ptr [rax+rax+00h]
0x1400445d2  mov     rcx, [rbx+0B0h]; Thread
0x1400445d9  mov     edx, r14d; Priority
0x1400445dc  call    cs:__imp_KeSetPriorityThread
0x1400445e3  nop     dword ptr [rax+rax+00h]
0x1400445e8  mov     dl, 1; Wait
0x1400445ea  mov     rcx, rdi; Resource
0x1400445ed  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400445f4  nop     dword ptr [rax+rax+00h]
0x1400445f9  jmp     loc_140044579
0x1400445fe  cmp     rcx, rdx
0x140044601  jz      short loc_140044616
0x140044603  lea     rcx, [rbx+538h]; Resource
0x14004460a  call    cs:__imp_ExReleaseResourceLite
0x140044611  nop     dword ptr [rax+rax+00h]
0x140044616  add     rsp, 20h
0x14004461a  pop     r14
0x14004461c  pop     rdi
0x14004461d  pop     rsi
0x14004461e  pop     rbp
0x14004461f  pop     rbx
0x140044620  retn
```
