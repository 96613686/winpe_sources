# KsecddLsaStateRef::~KsecddLsaStateRef(void)

- ea: `0x180001cf0`
- end: `0x180001d97`
- name: `??1KsecddLsaStateRef@@QEAA@XZ`
- size: `167`
- prototype: `void __fastcall(KsecddLsaStateRef *__hidden this)`
- caller_count: `46`
- callee_count: `2`
- tags: ``

## callers

- `0x180001230`
- `0x180001478`
- `0x18000150c`
- `0x1800017c4`
- `0x1800018f8`
- `0x180001ae4`
- `0x1800021bc`
- `0x180004e7c`
- `0x180005160`
- `0x1800053e0`
- `0x180005718`
- `0x180005b58`
- `0x180005cf0`
- `0x180005e94`
- `0x18000ba98`
- `0x18000bcbc`
- `0x18000bf50`
- `0x18000c1f0`
- `0x18000d01c`
- `0x18000d2f0`
- `0x18000dad4`
- `0x18000f4ec`
- `0x180021a40`
- `0x180021b68`
- `0x18002267c`
- `0x1800230d0`
- `0x180024330`
- `0x180024910`
- `0x1800250e0`
- `0x180025220`
- `0x180025c20`
- `0x180025e00`
- `0x180026fb8`
- `0x180029008`
- `0x1800290c4`
- `0x180029180`
- `0x18002923c`
- `0x1800294a0`
- `0x180029570`
- `0x180029690`
- `0x1800297f0`
- `0x1800298e0`
- `0x180029aa0`
- `0x180029ba0`
- `0x180029c90`
- `0x180029d80`

## callees

- `0x180001cf0`
- `0x1800280f0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180001d2e`
- `ntoskrnl!KeGetCurrentIrql` at `0x180001d2e`
- `ntoskrnl!ExQueueWorkItem` at `0x180001d6a`
- `ntoskrnl!ExQueueWorkItem` at `0x180001d6a`

## pseudocode

```c
void __fastcall KsecddLsaStateRef::~KsecddLsaStateRef(KsecddLsaStateRef *this)
{
  __int64 v1; // rbx
  signed __int64 v3; // rax
  bool v4; // cc
  signed __int64 v5; // rax

  v1 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    v3 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v1 + 520), 0xFFFFFFFFFFFFFFFFuLL);
    v4 = v3 <= 1;
    v5 = v3 - 1;
    if ( v4 )
    {
      if ( v5 )
        __fastfail(0xEu);
      if ( KeGetCurrentIrql() )
      {
        *(_QWORD *)(v1 + 512) = v1;
        *(_QWORD *)(v1 + 504) = CleanKsecddLsaState;
        *(_QWORD *)(v1 + 488) = 0;
        ExQueueWorkItem((PWORK_QUEUE_ITEM)(v1 + 488), DelayedWorkQueue);
        *(_QWORD *)this = 0;
        return;
      }
      CleanKsecddLsaState((struct _KSECDDLSASTATE *)v1);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180001cf0  mov     [rsp+arg_0], rbx
0x180001cf5  push    rdi
0x180001cf6  sub     rsp, 20h
0x180001cfa  mov     rbx, [rcx]
0x180001cfd  mov     rdi, rcx
0x180001d00  test    rbx, rbx
0x180001d03  jz      short loc_180001D22
0x180001d05  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180001d0c  lock xadd [rbx+208h], rax
0x180001d15  sub     rax, 1
0x180001d19  jle     short loc_180001D89
0x180001d1b  mov     qword ptr [rdi], 0
0x180001d22  mov     rbx, [rsp+28h+arg_0]
0x180001d27  add     rsp, 20h
0x180001d2b  pop     rdi
0x180001d2c  retn
0x180001d2e  call    cs:__imp_KeGetCurrentIrql
0x180001d35  nop     dword ptr [rax+rax+00h]
0x180001d3a  test    al, al
0x180001d3c  jnz     short loc_180001D48
0x180001d3e  mov     rcx, rbx; struct _KSECDDLSASTATE *
0x180001d41  call    CleanKsecddLsaState
0x180001d46  jmp     short loc_180001D1B
0x180001d48  lea     rcx, [rbx+1E8h]; WorkItem
0x180001d4f  mov     edx, 1; QueueType
0x180001d54  lea     rax, CleanKsecddLsaState
0x180001d5b  mov     [rcx+18h], rbx
0x180001d5f  mov     [rcx+10h], rax
0x180001d63  mov     qword ptr [rcx], 0
0x180001d6a  call    cs:__imp_ExQueueWorkItem
0x180001d71  nop     dword ptr [rax+rax+00h]
0x180001d76  mov     rbx, [rsp+28h+arg_0]
0x180001d7b  mov     qword ptr [rdi], 0
0x180001d82  add     rsp, 20h
0x180001d86  pop     rdi
0x180001d87  retn
0x180001d89  test    rax, rax
0x180001d8c  jz      short loc_180001D2E
0x180001d8e  mov     ecx, 0Eh
0x180001d93  int     29h; Win8: RtlFailFast(ecx)
0x180001d95  jmp     short loc_180001D1B
```
