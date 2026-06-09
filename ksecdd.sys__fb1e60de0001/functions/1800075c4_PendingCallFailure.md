# PendingCallFailure

- ea: `0x1800075c4`
- end: `0x180007697`
- name: `PendingCallFailure`
- size: `211`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180001fa0`
- `0x18000f900`
- `0x180027ea8`

## callees

- `0x1800075c4`
- `0x180010980`
- `0x1800266c0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x180007646`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x180007646`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x180007677`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x180007677`
- `HAL!KeQueryPerformanceCounter` at `0x18000760b`
- `HAL!KeQueryPerformanceCounter` at `0x18000760b`

## pseudocode

```c
void __fastcall PendingCallFailure(__int64 a1, struct _LIST_ENTRY *a2, unsigned int a3)
{
  struct _LIST_ENTRY *Blink; // rbp
  struct _LIST_ENTRY *Flink; // rsi
  LARGE_INTEGER PerformanceCounter; // rax
  struct _LIST_ENTRY *v8; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v9; // [rsp+38h] [rbp-30h]
  int v10; // [rsp+3Ch] [rbp-2Ch]

  if ( a1 && a2 )
  {
    Blink = a2[1].Blink;
    if ( Blink )
    {
      Flink = a2[1].Flink;
      if ( Flink )
        Flink = Flink->Flink;
      v8 = Flink;
      v10 = 0;
      v9 = a3;
      PerformanceCounter = KeQueryPerformanceCounter(0);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))Blink)(
        a2[2].Flink,
        v9,
        &v8,
        16,
        (LARGE_INTEGER)PerformanceCounter.QuadPart);
      if ( Flink )
        ExFreeToLookasideListEx(&Lookaside, Flink);
    }
    if ( !a2[1].Blink && *(_QWORD *)a1 && *(_QWORD *)(a1 + 8) )
      ExInterlockedInsertHeadList((PLIST_ENTRY)(a1 + 168), a2, (PKSPIN_LOCK)(a1 + 160));
    else
      PendingCallDelete(a2);
  }
}

```

## disassembly

```asm
0x1800075c4  test    rcx, rcx
0x1800075c7  jz      locret_180007695
0x1800075cd  push    rbx
0x1800075ce  push    rbp
0x1800075cf  push    rsi
0x1800075d0  push    rdi
0x1800075d1  sub     rsp, 48h
0x1800075d5  mov     rbx, rdx
0x1800075d8  mov     rdi, rcx
0x1800075db  test    rdx, rdx
0x1800075de  jz      loc_18000768D
0x1800075e4  mov     rbp, [rdx+18h]
0x1800075e8  test    rbp, rbp
0x1800075eb  jz      short loc_180007652
0x1800075ed  mov     rsi, [rdx+10h]
0x1800075f1  test    rsi, rsi
0x1800075f4  jz      short loc_1800075F9
0x1800075f6  mov     rsi, [rsi]
0x1800075f9  xor     eax, eax
0x1800075fb  mov     [rsp+68h+var_38], rsi
0x180007600  xor     ecx, ecx; PerformanceFrequency
0x180007602  mov     [rsp+68h+var_2C], eax
0x180007606  mov     [rsp+68h+var_30], r8d
0x18000760b  call    cs:__imp_KeQueryPerformanceCounter
0x180007612  nop     dword ptr [rax+rax+00h]
0x180007617  mov     edx, [rsp+68h+var_30]
0x18000761b  lea     r8, [rsp+68h+var_38]
0x180007620  mov     rcx, [rbx+20h]
0x180007624  mov     r9d, 10h
0x18000762a  mov     [rsp+68h+var_48], rax
0x18000762f  mov     rax, rbp
0x180007632  call    _guard_dispatch_icall
0x180007637  test    rsi, rsi
0x18000763a  jz      short loc_180007652
0x18000763c  mov     rdx, rsi; Entry
0x18000763f  lea     rcx, Lookaside; Lookaside
0x180007646  call    cs:__imp_ExFreeToLookasideListEx
0x18000764d  nop     dword ptr [rax+rax+00h]
0x180007652  cmp     qword ptr [rbx+18h], 0
0x180007657  jnz     short loc_180007685
0x180007659  cmp     qword ptr [rdi], 0
0x18000765d  jz      short loc_180007685
0x18000765f  cmp     qword ptr [rdi+8], 0
0x180007664  jz      short loc_180007685
0x180007666  lea     r8, [rdi+0A0h]; Lock
0x18000766d  mov     rdx, rbx; ListEntry
0x180007670  lea     rcx, [rdi+0A8h]; ListHead
0x180007677  call    cs:__imp_ExInterlockedInsertHeadList
0x18000767e  nop     dword ptr [rax+rax+00h]
0x180007683  jmp     short loc_18000768D
0x180007685  mov     rcx, rbx; Entry
0x180007688  call    PendingCallDelete
0x18000768d  add     rsp, 48h
0x180007691  pop     rdi
0x180007692  pop     rsi
0x180007693  pop     rbp
0x180007694  pop     rbx
0x180007695  retn
```
