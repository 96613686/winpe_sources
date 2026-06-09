# CreateTlgAggregateSession

- ea: `0x140054504`
- end: `0x140054634`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140054878`

## callees

- `0x1400375c0`
- `0x140054504`
- `0x14005463c`

## import_xrefs

- `ntoskrnl!ExAllocateTimer` at `0x140054605`
- `ntoskrnl!ExAllocateTimer` at `0x140054605`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140054532`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140054582`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140054532`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140054582`
- `ntoskrnl!KeInitializeEvent` at `0x1400545b8`
- `ntoskrnl!KeInitializeEvent` at `0x1400545b8`

## pseudocode

```c
_QWORD *__fastcall CreateTlgAggregateSession(char a1, char a2)
{
  _QWORD *PoolWithTag; // rax
  _QWORD *v5; // rbx
  char *v6; // rax
  char *v7; // rdi
  _QWORD *v8; // rax
  __int64 Timer; // rax

  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(a1 != 0 ? PagedPool : 512), 0x178u, 0x47417254u);
  v5 = PoolWithTag;
  if ( !PoolWithTag )
    goto LABEL_9;
  memset(PoolWithTag, 0, 0x178u);
  v5[34] = 0;
  if ( a2 || !a1 )
  {
    v6 = (char *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x40u, 0x47417254u);
    v7 = v6;
    if ( v6 )
      memset(v6, 0, 0x40u);
    v5[33] = v7;
    if ( !v7 )
      goto LABEL_9;
    KeInitializeEvent((PRKEVENT)(v7 + 32), NotificationEvent, 0);
    v8 = (_QWORD *)v5[33];
    v8[2] = TlgAggregateInternalFlushWorkItemRoutineKernelMode;
    v8[3] = v5;
    *v8 = 0;
    *(_WORD *)(v5[33] + 56LL) = 0;
    if ( a2 )
    {
      Timer = ExAllocateTimer(TlgAggregateInternalFlushTimerCallbackKernelMode, v5[33], 8);
      v5[45] = Timer;
      if ( !Timer )
      {
LABEL_9:
        DestroyAggregateSession(v5);
        return 0;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140054504  push    rbx
0x140054506  push    rbp
0x140054507  push    rsi
0x140054508  push    rdi
0x140054509  sub     rsp, 28h
0x14005450d  mov     al, cl
0x14005450f  mov     dil, cl
0x140054512  neg     al
0x140054514  mov     sil, dl
0x140054517  mov     ebp, 178h
0x14005451c  mov     r8d, 47417254h; Tag
0x140054522  sbb     ecx, ecx
0x140054524  mov     edx, ebp; NumberOfBytes
0x140054526  and     ecx, 0FFFFFE01h
0x14005452c  add     ecx, 200h; PoolType
0x140054532  call    cs:__imp_ExAllocatePoolWithTag
0x140054539  nop     dword ptr [rax+rax+00h]
0x14005453e  mov     rbx, rax
0x140054541  test    rax, rax
0x140054544  jz      loc_14005461D
0x14005454a  mov     r8d, ebp; Size
0x14005454d  xor     edx, edx; Val
0x14005454f  mov     rcx, rax; void *
0x140054552  call    memset
0x140054557  mov     qword ptr [rbx+110h], 0
0x140054562  test    sil, sil
0x140054565  jnz     short loc_140054570
0x140054567  test    dil, dil
0x14005456a  jnz     loc_140054627
0x140054570  mov     ebp, 40h ; '@'
0x140054575  mov     r8d, 47417254h; Tag
0x14005457b  mov     edx, ebp; NumberOfBytes
0x14005457d  mov     ecx, 200h; PoolType
0x140054582  call    cs:__imp_ExAllocatePoolWithTag
0x140054589  nop     dword ptr [rax+rax+00h]
0x14005458e  mov     rdi, rax
0x140054591  test    rax, rax
0x140054594  jz      short loc_1400545A3
0x140054596  mov     r8d, ebp; Size
0x140054599  xor     edx, edx; Val
0x14005459b  mov     rcx, rax; void *
0x14005459e  call    memset
0x1400545a3  mov     [rbx+108h], rdi
0x1400545aa  test    rdi, rdi
0x1400545ad  jz      short loc_14005461D
0x1400545af  lea     rcx, [rdi+20h]; Event
0x1400545b3  xor     r8d, r8d; State
0x1400545b6  xor     edx, edx; Type
0x1400545b8  call    cs:__imp_KeInitializeEvent
0x1400545bf  nop     dword ptr [rax+rax+00h]
0x1400545c4  mov     rax, [rbx+108h]
0x1400545cb  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x1400545d2  mov     [rax+10h], rcx
0x1400545d6  mov     [rax+18h], rbx
0x1400545da  mov     qword ptr [rax], 0
0x1400545e1  xor     eax, eax
0x1400545e3  mov     rcx, [rbx+108h]
0x1400545ea  mov     [rcx+38h], ax
0x1400545ee  test    sil, sil
0x1400545f1  jz      short loc_140054627
0x1400545f3  mov     rdx, [rbx+108h]
0x1400545fa  lea     r8d, [rax+8]
0x1400545fe  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x140054605  call    cs:__imp_ExAllocateTimer
0x14005460c  nop     dword ptr [rax+rax+00h]
0x140054611  mov     [rbx+168h], rax
0x140054618  test    rax, rax
0x14005461b  jnz     short loc_140054627
0x14005461d  mov     rcx, rbx; P
0x140054620  call    DestroyAggregateSession
0x140054625  xor     ebx, ebx
0x140054627  mov     rax, rbx
0x14005462a  add     rsp, 28h
0x14005462e  pop     rdi
0x14005462f  pop     rsi
0x140054630  pop     rbp
0x140054631  pop     rbx
0x140054632  retn
```
