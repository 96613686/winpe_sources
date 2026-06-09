# MRxDAVCheckForCollapsibleOpen

- ea: `0x140012720`
- end: `0x140012775`
- name: `MRxDAVCheckForCollapsibleOpen`
- size: `85`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000163c`
- `0x140012720`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140012746`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140012746`

## pseudocode

```c
__int64 MRxDAVCheckForCollapsibleOpen()
{
  __int64 v0; // rbx
  HANDLE CurrentThreadId; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v0 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v0, 10, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId);
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x140012720  push    rbx
0x140012722  sub     rsp, 20h
0x140012726  mov     rbx, cs:WPP_GLOBAL_Control
0x14001272d  lea     rax, WPP_GLOBAL_Control
0x140012734  cmp     rbx, rax
0x140012737  jz      short loc_140012769
0x140012739  test    dword ptr [rbx+2Ch], 2000h
0x140012740  jz      short loc_140012769
0x140012742  mov     rbx, [rbx+18h]
0x140012746  call    cs:__imp_PsGetCurrentThreadId
0x14001274d  nop     dword ptr [rax+rax+00h]
0x140012752  mov     edx, 0Ah
0x140012757  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x14001275e  mov     r9, rax
0x140012761  mov     rcx, rbx
0x140012764  call    WPP_SF_q
0x140012769  mov     eax, 0C0000225h
0x14001276e  add     rsp, 20h
0x140012772  pop     rbx
0x140012773  retn
```
