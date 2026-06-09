# MRxDAVTruncate

- ea: `0x140016cd0`
- end: `0x140016d25`
- name: `MRxDAVTruncate`
- size: `85`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000163c`
- `0x140016cd0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140016cf6`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140016cf6`

## pseudocode

```c
__int64 MRxDAVTruncate()
{
  __int64 v0; // rbx
  HANDLE CurrentThreadId; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v0 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_q(v0, 97, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids, CurrentThreadId);
  }
  return 3221225474LL;
}

```

## disassembly

```asm
0x140016cd0  push    rbx
0x140016cd2  sub     rsp, 20h
0x140016cd6  mov     rbx, cs:WPP_GLOBAL_Control
0x140016cdd  lea     rax, WPP_GLOBAL_Control
0x140016ce4  cmp     rbx, rax
0x140016ce7  jz      short loc_140016D19
0x140016ce9  test    dword ptr [rbx+2Ch], 2000h
0x140016cf0  jz      short loc_140016D19
0x140016cf2  mov     rbx, [rbx+18h]
0x140016cf6  call    cs:__imp_PsGetCurrentThreadId
0x140016cfd  nop     dword ptr [rax+rax+00h]
0x140016d02  mov     edx, 61h ; 'a'
0x140016d07  lea     r8, WPP_d37f3b85fd70300967c551fc1b4b0e40_Traceguids
0x140016d0e  mov     r9, rax
0x140016d11  mov     rcx, rbx
0x140016d14  call    WPP_SF_q
0x140016d19  mov     eax, 0C0000002h
0x140016d1e  add     rsp, 20h
0x140016d22  pop     rbx
0x140016d23  retn
```
