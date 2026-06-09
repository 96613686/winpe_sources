# PendingCallPush

- ea: `0x180026530`
- end: `0x1800265cb`
- name: `PendingCallPush`
- size: `155`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800242e0`
- `0x1800248c0`
- `0x180025db0`

## callees

- `0x180026530`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x18002654c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x18002654c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18002658f`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18002658f`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x180026581`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x180026581`

## pseudocode

```c
__int64 __fastcall PendingCallPush(struct _LIST_ENTRY *a1, struct _LIST_ENTRY *a2, struct _LIST_ENTRY *a3, __int64 a4)
{
  struct _LIST_ENTRY *v8; // rax

  v8 = (struct _LIST_ENTRY *)ExAllocateFromLookasideListEx(&stru_180019720);
  if ( !v8 )
    return 3221225626LL;
  v8[1].Flink = a1;
  v8[1].Blink = a2;
  v8[2].Flink = a3;
  a1->Flink = 0;
  ExInterlockedInsertTailList((PLIST_ENTRY)(a4 + 168), v8, (PKSPIN_LOCK)(a4 + 160));
  _InterlockedIncrement64((volatile signed __int64 *)(136LL * KeGetCurrentProcessorNumberEx(0) + *(_QWORD *)(a4 + 312)));
  return 0;
}

```

## disassembly

```asm
0x180026530  push    rbx
0x180026532  push    rbp
0x180026533  push    rsi
0x180026534  push    rdi
0x180026535  sub     rsp, 28h
0x180026539  mov     rdi, rcx
0x18002653c  mov     rbx, r9
0x18002653f  lea     rcx, stru_180019720; Lookaside
0x180026546  mov     rsi, r8
0x180026549  mov     rbp, rdx
0x18002654c  call    cs:__imp_ExAllocateFromLookasideListEx
0x180026553  nop     dword ptr [rax+rax+00h]
0x180026558  test    rax, rax
0x18002655b  jz      short loc_1800265BC
0x18002655d  mov     [rax+10h], rdi
0x180026561  lea     r8, [rbx+0A0h]; Lock
0x180026568  mov     [rax+18h], rbp
0x18002656c  lea     rcx, [rbx+0A8h]; ListHead
0x180026573  mov     [rax+20h], rsi
0x180026577  mov     rdx, rax; ListEntry
0x18002657a  mov     qword ptr [rdi], 0
0x180026581  call    cs:__imp_ExInterlockedInsertTailList
0x180026588  nop     dword ptr [rax+rax+00h]
0x18002658d  xor     ecx, ecx; ProcNumber
0x18002658f  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x180026596  nop     dword ptr [rax+rax+00h]
0x18002659b  mov     eax, eax
0x18002659d  imul    rcx, rax, 88h
0x1800265a4  mov     rax, [rbx+138h]
0x1800265ab  lock inc qword ptr [rcx+rax]
0x1800265b0  xor     eax, eax
0x1800265b2  add     rsp, 28h
0x1800265b6  pop     rdi
0x1800265b7  pop     rsi
0x1800265b8  pop     rbp
0x1800265b9  pop     rbx
0x1800265ba  retn
0x1800265bc  mov     eax, 0C000009Ah
0x1800265c1  add     rsp, 28h
0x1800265c5  pop     rdi
0x1800265c6  pop     rsi
0x1800265c7  pop     rbp
0x1800265c8  pop     rbx
0x1800265c9  retn
```
