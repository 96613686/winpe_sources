# CreateTlgAggregateSession

- ea: `0x14005a33c`
- end: `0x14005a46c`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14005ab08`

## callees

- `0x14000c680`
- `0x14005a33c`
- `0x14005a474`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14005a3f0`
- `ntoskrnl!KeInitializeEvent` at `0x14005a3f0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005a36a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005a3ba`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005a36a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14005a3ba`
- `ntoskrnl!ExAllocateTimer` at `0x14005a43d`
- `ntoskrnl!ExAllocateTimer` at `0x14005a43d`

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
0x14005a33c  push    rbx
0x14005a33e  push    rbp
0x14005a33f  push    rsi
0x14005a340  push    rdi
0x14005a341  sub     rsp, 28h
0x14005a345  mov     al, cl
0x14005a347  mov     dil, cl
0x14005a34a  neg     al
0x14005a34c  mov     sil, dl
0x14005a34f  mov     ebp, 178h
0x14005a354  mov     r8d, 47417254h; Tag
0x14005a35a  sbb     ecx, ecx
0x14005a35c  mov     edx, ebp; NumberOfBytes
0x14005a35e  and     ecx, 0FFFFFE01h
0x14005a364  add     ecx, 200h; PoolType
0x14005a36a  call    cs:__imp_ExAllocatePoolWithTag
0x14005a371  nop     dword ptr [rax+rax+00h]
0x14005a376  mov     rbx, rax
0x14005a379  test    rax, rax
0x14005a37c  jz      loc_14005A455
0x14005a382  mov     r8d, ebp; Size
0x14005a385  xor     edx, edx; Val
0x14005a387  mov     rcx, rax; void *
0x14005a38a  call    memset
0x14005a38f  mov     qword ptr [rbx+110h], 0
0x14005a39a  test    sil, sil
0x14005a39d  jnz     short loc_14005A3A8
0x14005a39f  test    dil, dil
0x14005a3a2  jnz     loc_14005A45F
0x14005a3a8  mov     ebp, 40h ; '@'
0x14005a3ad  mov     r8d, 47417254h; Tag
0x14005a3b3  mov     edx, ebp; NumberOfBytes
0x14005a3b5  mov     ecx, 200h; PoolType
0x14005a3ba  call    cs:__imp_ExAllocatePoolWithTag
0x14005a3c1  nop     dword ptr [rax+rax+00h]
0x14005a3c6  mov     rdi, rax
0x14005a3c9  test    rax, rax
0x14005a3cc  jz      short loc_14005A3DB
0x14005a3ce  mov     r8d, ebp; Size
0x14005a3d1  xor     edx, edx; Val
0x14005a3d3  mov     rcx, rax; void *
0x14005a3d6  call    memset
0x14005a3db  mov     [rbx+108h], rdi
0x14005a3e2  test    rdi, rdi
0x14005a3e5  jz      short loc_14005A455
0x14005a3e7  lea     rcx, [rdi+20h]; Event
0x14005a3eb  xor     r8d, r8d; State
0x14005a3ee  xor     edx, edx; Type
0x14005a3f0  call    cs:__imp_KeInitializeEvent
0x14005a3f7  nop     dword ptr [rax+rax+00h]
0x14005a3fc  mov     rax, [rbx+108h]
0x14005a403  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x14005a40a  mov     [rax+10h], rcx
0x14005a40e  mov     [rax+18h], rbx
0x14005a412  mov     qword ptr [rax], 0
0x14005a419  xor     eax, eax
0x14005a41b  mov     rcx, [rbx+108h]
0x14005a422  mov     [rcx+38h], ax
0x14005a426  test    sil, sil
0x14005a429  jz      short loc_14005A45F
0x14005a42b  mov     rdx, [rbx+108h]
0x14005a432  lea     r8d, [rax+8]
0x14005a436  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x14005a43d  call    cs:__imp_ExAllocateTimer
0x14005a444  nop     dword ptr [rax+rax+00h]
0x14005a449  mov     [rbx+168h], rax
0x14005a450  test    rax, rax
0x14005a453  jnz     short loc_14005A45F
0x14005a455  mov     rcx, rbx; P
0x14005a458  call    DestroyAggregateSession
0x14005a45d  xor     ebx, ebx
0x14005a45f  mov     rax, rbx
0x14005a462  add     rsp, 28h
0x14005a466  pop     rdi
0x14005a467  pop     rsi
0x14005a468  pop     rbp
0x14005a469  pop     rbx
0x14005a46a  retn
```
