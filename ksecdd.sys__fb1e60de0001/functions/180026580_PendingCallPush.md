# PendingCallPush

- ea: `0x180026580`
- end: `0x18002661b`
- name: `PendingCallPush`
- size: `155`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180024330`
- `0x180024910`
- `0x180025e00`

## callees

- `0x180026580`

## import_xrefs

- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x18002659c`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x18002659c`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800265df`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800265df`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x1800265d1`
- `ntoskrnl!ExInterlockedInsertTailList` at `0x1800265d1`

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
0x180026580  push    rbx
0x180026582  push    rbp
0x180026583  push    rsi
0x180026584  push    rdi
0x180026585  sub     rsp, 28h
0x180026589  mov     rdi, rcx
0x18002658c  mov     rbx, r9
0x18002658f  lea     rcx, stru_180019720; Lookaside
0x180026596  mov     rsi, r8
0x180026599  mov     rbp, rdx
0x18002659c  call    cs:__imp_ExAllocateFromLookasideListEx
0x1800265a3  nop     dword ptr [rax+rax+00h]
0x1800265a8  test    rax, rax
0x1800265ab  jz      short loc_18002660C
0x1800265ad  mov     [rax+10h], rdi
0x1800265b1  lea     r8, [rbx+0A0h]; Lock
0x1800265b8  mov     [rax+18h], rbp
0x1800265bc  lea     rcx, [rbx+0A8h]; ListHead
0x1800265c3  mov     [rax+20h], rsi
0x1800265c7  mov     rdx, rax; ListEntry
0x1800265ca  mov     qword ptr [rdi], 0
0x1800265d1  call    cs:__imp_ExInterlockedInsertTailList
0x1800265d8  nop     dword ptr [rax+rax+00h]
0x1800265dd  xor     ecx, ecx; ProcNumber
0x1800265df  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1800265e6  nop     dword ptr [rax+rax+00h]
0x1800265eb  mov     eax, eax
0x1800265ed  imul    rcx, rax, 88h
0x1800265f4  mov     rax, [rbx+138h]
0x1800265fb  lock inc qword ptr [rcx+rax]
0x180026600  xor     eax, eax
0x180026602  add     rsp, 28h
0x180026606  pop     rdi
0x180026607  pop     rsi
0x180026608  pop     rbp
0x180026609  pop     rbx
0x18002660a  retn
0x18002660c  mov     eax, 0C000009Ah
0x180026611  add     rsp, 28h
0x180026615  pop     rdi
0x180026616  pop     rsi
0x180026617  pop     rbp
0x180026618  pop     rbx
0x180026619  retn
```
