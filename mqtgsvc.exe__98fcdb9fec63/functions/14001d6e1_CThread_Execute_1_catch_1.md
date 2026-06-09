# _CThread::Execute_::_1_::catch$1

- ea: `0x14001d6e1`
- end: `0x14001d748`
- name: `_CThread::Execute_::_1_::catch$1`
- size: `103`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140007554`
- `0x14001d6e1`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14001d72f`
- `KERNEL32!SetEvent` at `0x14001d72f`

## pseudocode

```c
__int64 __fastcall CThread::Execute_::_1_::catch_1(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx

  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v2 = *(_QWORD *)(a2 + 80);
  }
  else
  {
    v2 = *(_QWORD *)(a2 + 80);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids);
  }
  SetEvent(*(HANDLE *)(v2 + 80));
  return 0;
}

```

## disassembly

```asm
0x14001d6e1  mov     [rsp+arg_8], rdx
0x14001d6e6  push    rbx
0x14001d6e7  push    rbp
0x14001d6e8  sub     rsp, 38h
0x14001d6ec  mov     rbp, rdx
0x14001d6ef  lea     rax, WPP_GLOBAL_Control
0x14001d6f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d6fd  cmp     rcx, rax
0x14001d700  jz      short loc_14001D727
0x14001d702  test    byte ptr [rcx+1Ch], 1
0x14001d706  jz      short loc_14001D727
0x14001d708  mov     edx, 13h
0x14001d70d  mov     rbx, [rbp+50h]
0x14001d711  mov     r9d, [rbx+18h]
0x14001d715  lea     r8, WPP_ebdd034966673a53bc23805b5a0fe994_Traceguids
0x14001d71c  mov     rcx, [rcx+10h]
0x14001d720  call    WPP_SF_d
0x14001d725  jmp     short loc_14001D72B
0x14001d727  mov     rbx, [rbp+50h]
0x14001d72b  mov     rcx, [rbx+50h]; hEvent
0x14001d72f  call    cs:__imp_SetEvent
0x14001d735  nop
0x14001d736  mov     rax, 0
0x14001d740  add     rsp, 38h
0x14001d744  pop     rbp
0x14001d745  pop     rbx
0x14001d746  retn
```
