# PendingCallPullBatch

- ea: `0x1800263e0`
- end: `0x18002649d`
- name: `PendingCallPullBatch`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f898`

## callees

- `0x1800263e0`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180026409`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180026448`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180026409`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180026448`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x18002648f`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x18002648f`

## pseudocode

```c
PLIST_ENTRY __fastcall PendingCallPullBatch(_QWORD *a1, __int64 a2)
{
  struct _LIST_ENTRY *v2; // rbp
  KSPIN_LOCK *v3; // rsi
  PLIST_ENTRY v5; // rbx
  PLIST_ENTRY v6; // rax
  struct _LIST_ENTRY *Blink; // rcx

  v2 = (struct _LIST_ENTRY *)(a2 + 168);
  *a1 = 0;
  v3 = (KSPIN_LOCK *)(a2 + 160);
  v5 = 0;
  v6 = ExInterlockedRemoveHeadList((PLIST_ENTRY)(a2 + 168), (PKSPIN_LOCK)(a2 + 160));
  if ( v6 )
  {
    while ( *a1 < 0x4000u )
    {
      *a1 += LODWORD(v6[1].Flink[2].Blink);
      if ( v5 )
      {
        Blink = v5->Blink;
        if ( Blink->Flink != v5 )
          __fastfail(3u);
        v6->Flink = v5;
        v6->Blink = Blink;
        Blink->Flink = v6;
        v5->Blink = v6;
      }
      else
      {
        v5 = v6;
        v6->Blink = v6;
        v6->Flink = v6;
      }
      v6 = ExInterlockedRemoveHeadList(v2, v3);
      if ( !v6 )
        return v5;
    }
    ExInterlockedInsertHeadList(v2, v6, v3);
  }
  return v5;
}

```

## disassembly

```asm
0x1800263e0  push    rbx
0x1800263e2  push    rbp
0x1800263e3  push    rsi
0x1800263e4  push    rdi
0x1800263e5  sub     rsp, 28h
0x1800263e9  lea     rbp, [rdx+0A8h]
0x1800263f0  mov     qword ptr [rcx], 0
0x1800263f7  lea     rsi, [rdx+0A0h]
0x1800263fe  mov     rdi, rcx
0x180026401  mov     rdx, rsi; Lock
0x180026404  mov     rcx, rbp; ListHead
0x180026407  xor     ebx, ebx
0x180026409  call    cs:__imp_ExInterlockedRemoveHeadList
0x180026410  nop     dword ptr [rax+rax+00h]
0x180026415  test    rax, rax
0x180026418  jz      short loc_180026459
0x18002641a  mov     r8, [rdi]
0x18002641d  cmp     r8, 4000h
0x180026424  jnb     short loc_180026486
0x180026426  mov     rcx, [rax+10h]
0x18002642a  mov     edx, [rcx+28h]
0x18002642d  add     rdx, r8
0x180026430  mov     [rdi], rdx
0x180026433  test    rbx, rbx
0x180026436  jnz     short loc_180026466
0x180026438  mov     rbx, rax
0x18002643b  mov     [rax+8], rax
0x18002643f  mov     [rax], rax
0x180026442  mov     rdx, rsi; Lock
0x180026445  mov     rcx, rbp; ListHead
0x180026448  call    cs:__imp_ExInterlockedRemoveHeadList
0x18002644f  nop     dword ptr [rax+rax+00h]
0x180026454  test    rax, rax
0x180026457  jnz     short loc_18002641A
0x180026459  mov     rax, rbx
0x18002645c  add     rsp, 28h
0x180026460  pop     rdi
0x180026461  pop     rsi
0x180026462  pop     rbp
0x180026463  pop     rbx
0x180026464  retn
0x180026466  mov     rcx, [rbx+8]
0x18002646a  cmp     [rcx], rbx
0x18002646d  jz      short loc_180026476
0x18002646f  mov     ecx, 3
0x180026474  int     29h; Win8: RtlFailFast(ecx)
0x180026476  mov     [rax], rbx
0x180026479  mov     [rax+8], rcx
0x18002647d  mov     [rcx], rax
0x180026480  mov     [rbx+8], rax
0x180026484  jmp     short loc_180026442
0x180026486  mov     r8, rsi; Lock
0x180026489  mov     rdx, rax; ListEntry
0x18002648c  mov     rcx, rbp; ListHead
0x18002648f  call    cs:__imp_ExInterlockedInsertHeadList
0x180026496  nop     dword ptr [rax+rax+00h]
0x18002649b  jmp     short loc_180026459
```
