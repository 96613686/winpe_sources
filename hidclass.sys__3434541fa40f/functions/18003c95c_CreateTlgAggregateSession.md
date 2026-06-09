# CreateTlgAggregateSession

- ea: `0x18003c95c`
- end: `0x18003ca8c`
- name: `CreateTlgAggregateSession`
- size: `304`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003d128`

## callees

- `0x180028000`
- `0x18003c95c`
- `0x18003ca94`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x18003ca10`
- `ntoskrnl!KeInitializeEvent` at `0x18003ca10`
- `ntoskrnl!ExAllocateTimer` at `0x18003ca5d`
- `ntoskrnl!ExAllocateTimer` at `0x18003ca5d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003c98a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003c9da`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003c98a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003c9da`

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

  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(a1 != 0 ? PagedPool : NonPagedPoolNx), 0x178u, 0x47417254u);
  v5 = PoolWithTag;
  if ( !PoolWithTag )
    goto LABEL_9;
  memset(PoolWithTag, 0, 0x178u);
  v5[34] = 0;
  if ( a2 || !a1 )
  {
    v6 = (char *)ExAllocatePoolWithTag(NonPagedPoolNx, 0x40u, 0x47417254u);
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
0x18003c95c  push    rbx
0x18003c95e  push    rbp
0x18003c95f  push    rsi
0x18003c960  push    rdi
0x18003c961  sub     rsp, 28h
0x18003c965  mov     al, cl
0x18003c967  mov     dil, cl
0x18003c96a  neg     al
0x18003c96c  mov     sil, dl
0x18003c96f  mov     ebp, 178h
0x18003c974  mov     r8d, 47417254h; Tag
0x18003c97a  sbb     ecx, ecx
0x18003c97c  mov     edx, ebp; NumberOfBytes
0x18003c97e  and     ecx, 0FFFFFE01h
0x18003c984  add     ecx, 200h; PoolType
0x18003c98a  call    cs:__imp_ExAllocatePoolWithTag
0x18003c991  nop     dword ptr [rax+rax+00h]
0x18003c996  mov     rbx, rax
0x18003c999  test    rax, rax
0x18003c99c  jz      loc_18003CA75
0x18003c9a2  mov     r8d, ebp; Size
0x18003c9a5  xor     edx, edx; Val
0x18003c9a7  mov     rcx, rax; void *
0x18003c9aa  call    memset
0x18003c9af  mov     qword ptr [rbx+110h], 0
0x18003c9ba  test    sil, sil
0x18003c9bd  jnz     short loc_18003C9C8
0x18003c9bf  test    dil, dil
0x18003c9c2  jnz     loc_18003CA7F
0x18003c9c8  mov     ebp, 40h ; '@'
0x18003c9cd  mov     r8d, 47417254h; Tag
0x18003c9d3  mov     edx, ebp; NumberOfBytes
0x18003c9d5  mov     ecx, 200h; PoolType
0x18003c9da  call    cs:__imp_ExAllocatePoolWithTag
0x18003c9e1  nop     dword ptr [rax+rax+00h]
0x18003c9e6  mov     rdi, rax
0x18003c9e9  test    rax, rax
0x18003c9ec  jz      short loc_18003C9FB
0x18003c9ee  mov     r8d, ebp; Size
0x18003c9f1  xor     edx, edx; Val
0x18003c9f3  mov     rcx, rax; void *
0x18003c9f6  call    memset
0x18003c9fb  mov     [rbx+108h], rdi
0x18003ca02  test    rdi, rdi
0x18003ca05  jz      short loc_18003CA75
0x18003ca07  lea     rcx, [rdi+20h]; Event
0x18003ca0b  xor     r8d, r8d; State
0x18003ca0e  xor     edx, edx; Type
0x18003ca10  call    cs:__imp_KeInitializeEvent
0x18003ca17  nop     dword ptr [rax+rax+00h]
0x18003ca1c  mov     rax, [rbx+108h]
0x18003ca23  lea     rcx, ?TlgAggregateInternalFlushWorkItemRoutineKernelMode@@YAXPEAX@Z; TlgAggregateInternalFlushWorkItemRoutineKernelMode(void *)
0x18003ca2a  mov     [rax+10h], rcx
0x18003ca2e  mov     [rax+18h], rbx
0x18003ca32  mov     qword ptr [rax], 0
0x18003ca39  xor     eax, eax
0x18003ca3b  mov     rcx, [rbx+108h]
0x18003ca42  mov     [rcx+38h], ax
0x18003ca46  test    sil, sil
0x18003ca49  jz      short loc_18003CA7F
0x18003ca4b  mov     rdx, [rbx+108h]
0x18003ca52  lea     r8d, [rax+8]
0x18003ca56  lea     rcx, ?TlgAggregateInternalFlushTimerCallbackKernelMode@@YAXPEAU_EX_TIMER@@PEAX@Z; TlgAggregateInternalFlushTimerCallbackKernelMode(_EX_TIMER *,void *)
0x18003ca5d  call    cs:__imp_ExAllocateTimer
0x18003ca64  nop     dword ptr [rax+rax+00h]
0x18003ca69  mov     [rbx+168h], rax
0x18003ca70  test    rax, rax
0x18003ca73  jnz     short loc_18003CA7F
0x18003ca75  mov     rcx, rbx; P
0x18003ca78  call    DestroyAggregateSession
0x18003ca7d  xor     ebx, ebx
0x18003ca7f  mov     rax, rbx
0x18003ca82  add     rsp, 28h
0x18003ca86  pop     rdi
0x18003ca87  pop     rsi
0x18003ca88  pop     rbp
0x18003ca89  pop     rbx
0x18003ca8a  retn
```
