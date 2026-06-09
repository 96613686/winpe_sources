# MRxDAVForcedClose

- ea: `0x140014570`
- end: `0x1400145c5`
- name: `MRxDAVForcedClose`
- size: `85`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000163c`
- `0x140014570`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140014596`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140014596`

## pseudocode

```c
__int64 MRxDAVForcedClose()
{
  __int64 v0; // rbx
  HANDLE CurrentThreadId; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v0 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v0, 98, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId);
  }
  return 3221225474LL;
}

```

## disassembly

```asm
0x140014570  push    rbx
0x140014572  sub     rsp, 20h
0x140014576  mov     rbx, cs:WPP_GLOBAL_Control
0x14001457d  lea     rax, WPP_GLOBAL_Control
0x140014584  cmp     rbx, rax
0x140014587  jz      short loc_1400145B9
0x140014589  test    dword ptr [rbx+2Ch], 4000h
0x140014590  jz      short loc_1400145B9
0x140014592  mov     rbx, [rbx+18h]
0x140014596  call    cs:__imp_PsGetCurrentThreadId
0x14001459d  nop     dword ptr [rax+rax+00h]
0x1400145a2  mov     edx, 62h ; 'b'
0x1400145a7  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x1400145ae  mov     r9, rax
0x1400145b1  mov     rcx, rbx
0x1400145b4  call    WPP_SF_q
0x1400145b9  mov     eax, 0C0000002h
0x1400145be  add     rsp, 20h
0x1400145c2  pop     rbx
0x1400145c3  retn
```
