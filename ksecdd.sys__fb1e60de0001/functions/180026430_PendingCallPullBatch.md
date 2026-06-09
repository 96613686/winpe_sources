# PendingCallPullBatch

- ea: `0x180026430`
- end: `0x1800264ed`
- name: `PendingCallPullBatch`
- size: `189`
- prototype: `PLIST_ENTRY __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f900`

## callees

- `0x180026430`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180026459`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180026498`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180026459`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x180026498`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x1800264df`
- `ntoskrnl!ExInterlockedInsertHeadList` at `0x1800264df`

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
0x180026430  push    rbx
0x180026432  push    rbp
0x180026433  push    rsi
0x180026434  push    rdi
0x180026435  sub     rsp, 28h
0x180026439  lea     rbp, [rdx+0A8h]
0x180026440  mov     qword ptr [rcx], 0
0x180026447  lea     rsi, [rdx+0A0h]
0x18002644e  mov     rdi, rcx
0x180026451  mov     rdx, rsi; Lock
0x180026454  mov     rcx, rbp; ListHead
0x180026457  xor     ebx, ebx
0x180026459  call    cs:__imp_ExInterlockedRemoveHeadList
0x180026460  nop     dword ptr [rax+rax+00h]
0x180026465  test    rax, rax
0x180026468  jz      short loc_1800264A9
0x18002646a  mov     r8, [rdi]
0x18002646d  cmp     r8, 4000h
0x180026474  jnb     short loc_1800264D6
0x180026476  mov     rcx, [rax+10h]
0x18002647a  mov     edx, [rcx+28h]
0x18002647d  add     rdx, r8
0x180026480  mov     [rdi], rdx
0x180026483  test    rbx, rbx
0x180026486  jnz     short loc_1800264B6
0x180026488  mov     rbx, rax
0x18002648b  mov     [rax+8], rax
0x18002648f  mov     [rax], rax
0x180026492  mov     rdx, rsi; Lock
0x180026495  mov     rcx, rbp; ListHead
0x180026498  call    cs:__imp_ExInterlockedRemoveHeadList
0x18002649f  nop     dword ptr [rax+rax+00h]
0x1800264a4  test    rax, rax
0x1800264a7  jnz     short loc_18002646A
0x1800264a9  mov     rax, rbx
0x1800264ac  add     rsp, 28h
0x1800264b0  pop     rdi
0x1800264b1  pop     rsi
0x1800264b2  pop     rbp
0x1800264b3  pop     rbx
0x1800264b4  retn
0x1800264b6  mov     rcx, [rbx+8]
0x1800264ba  cmp     [rcx], rbx
0x1800264bd  jz      short loc_1800264C6
0x1800264bf  mov     ecx, 3
0x1800264c4  int     29h; Win8: RtlFailFast(ecx)
0x1800264c6  mov     [rax], rbx
0x1800264c9  mov     [rax+8], rcx
0x1800264cd  mov     [rcx], rax
0x1800264d0  mov     [rbx+8], rax
0x1800264d4  jmp     short loc_180026492
0x1800264d6  mov     r8, rsi; Lock
0x1800264d9  mov     rdx, rax; ListEntry
0x1800264dc  mov     rcx, rbp; ListHead
0x1800264df  call    cs:__imp_ExInterlockedInsertHeadList
0x1800264e6  nop     dword ptr [rax+rax+00h]
0x1800264eb  jmp     short loc_1800264A9
```
