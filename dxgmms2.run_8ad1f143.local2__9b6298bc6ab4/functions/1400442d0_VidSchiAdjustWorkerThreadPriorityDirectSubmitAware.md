# VidSchiAdjustWorkerThreadPriorityDirectSubmitAware

- ea: `0x1400442d0`
- end: `0x14004441e`
- name: `VidSchiAdjustWorkerThreadPriorityDirectSubmitAware`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400229f0`

## callees

- `0x14002f610`
- `0x1400442d0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140044364`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400443e9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140044364`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400443e9`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400443c2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044406`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400443c2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044406`
- `ntoskrnl!KeQueryPriorityThread` at `0x140044312`
- `ntoskrnl!KeQueryPriorityThread` at `0x140044332`
- `ntoskrnl!KeQueryPriorityThread` at `0x1400443ae`
- `ntoskrnl!KeQueryPriorityThread` at `0x140044312`
- `ntoskrnl!KeQueryPriorityThread` at `0x140044332`
- `ntoskrnl!KeQueryPriorityThread` at `0x1400443ae`
- `ntoskrnl!KeSetPriorityThread` at `0x1400443d8`
- `ntoskrnl!KeSetPriorityThread` at `0x1400443d8`

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
0x1400442d0  push    rbx
0x1400442d2  push    rbp
0x1400442d3  push    rsi
0x1400442d4  push    rdi
0x1400442d5  push    r14
0x1400442d7  sub     rsp, 20h
0x1400442db  mov     rax, [rcx+60h]
0x1400442df  mov     rbp, rcx
0x1400442e2  mov     rcx, gs:188h
0x1400442eb  mov     rbx, [rax+18h]
0x1400442ef  mov     eax, [rbx+0B58h]
0x1400442f5  mov     rdx, [rbx+0B0h]
0x1400442fc  test    al, 20h
0x1400442fe  jz      loc_1400443FA
0x140044304  cmp     rcx, rdx
0x140044307  jz      short loc_14004434A
0x140044309  mov     rcx, gs:188h; Thread
0x140044312  call    cs:__imp_KeQueryPriorityThread
0x140044319  nop     dword ptr [rax+rax+00h]
0x14004431e  inc     eax
0x140044320  mov     esi, 1Fh
0x140044325  cmp     eax, esi
0x140044327  jge     short loc_140044341
0x140044329  mov     rcx, gs:188h; Thread
0x140044332  call    cs:__imp_KeQueryPriorityThread
0x140044339  nop     dword ptr [rax+rax+00h]
0x14004433e  lea     esi, [rax+1]
0x140044341  lea     rdi, [rbx+538h]
0x140044348  jmp     short loc_140044375
0x14004434a  mov     eax, [rbp+314h]
0x140044350  test    eax, eax
0x140044352  jnz     loc_140044412
0x140044358  lea     rdi, [rbx+538h]
0x14004435f  mov     dl, 1; Wait
0x140044361  mov     rcx, rdi; Resource
0x140044364  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14004436b  nop     dword ptr [rax+rax+00h]
0x140044370  mov     esi, 10h
0x140044375  mov     rax, gs:188h
0x14004437e  cmp     rax, [rbx+0B0h]
0x140044385  mov     eax, [rbp+314h]
0x14004438b  jnz     short loc_140044396
0x14004438d  test    eax, eax
0x14004438f  jz      short loc_14004439A
0x140044391  mov     rcx, rdi
0x140044394  jmp     short loc_140044406
0x140044396  test    eax, eax
0x140044398  jz      short loc_140044391
0x14004439a  mov     edx, esi
0x14004439c  mov     rcx, rbp
0x14004439f  call    VidSchiComputeWorkerThreadPriority
0x1400443a4  mov     rcx, [rbx+0B0h]; Thread
0x1400443ab  mov     r14d, eax
0x1400443ae  call    cs:__imp_KeQueryPriorityThread
0x1400443b5  nop     dword ptr [rax+rax+00h]
0x1400443ba  cmp     r14d, eax
0x1400443bd  jz      short loc_140044391
0x1400443bf  mov     rcx, rdi; Resource
0x1400443c2  call    cs:__imp_ExReleaseResourceLite
0x1400443c9  nop     dword ptr [rax+rax+00h]
0x1400443ce  mov     rcx, [rbx+0B0h]; Thread
0x1400443d5  mov     edx, r14d; Priority
0x1400443d8  call    cs:__imp_KeSetPriorityThread
0x1400443df  nop     dword ptr [rax+rax+00h]
0x1400443e4  mov     dl, 1; Wait
0x1400443e6  mov     rcx, rdi; Resource
0x1400443e9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400443f0  nop     dword ptr [rax+rax+00h]
0x1400443f5  jmp     loc_140044375
0x1400443fa  cmp     rcx, rdx
0x1400443fd  jz      short loc_140044412
0x1400443ff  lea     rcx, [rbx+538h]; Resource
0x140044406  call    cs:__imp_ExReleaseResourceLite
0x14004440d  nop     dword ptr [rax+rax+00h]
0x140044412  add     rsp, 20h
0x140044416  pop     r14
0x140044418  pop     rdi
0x140044419  pop     rsi
0x14004441a  pop     rbp
0x14004441b  pop     rbx
0x14004441c  retn
```
