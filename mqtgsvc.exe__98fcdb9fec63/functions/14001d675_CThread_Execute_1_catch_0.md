# _CThread::Execute_::_1_::catch$0

- ea: `0x14001d675`
- end: `0x14001d6db`
- name: `_CThread::Execute_::_1_::catch$0`
- size: `102`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140007d68`
- `0x14001d675`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14001d6c2`
- `KERNEL32!SetEvent` at `0x14001d6c2`

## pseudocode

```c
__int64 __fastcall CThread::Execute_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx

  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v3 = *(_QWORD *)(a2 + 80);
  }
  else
  {
    v3 = *(_QWORD *)(a2 + 80);
    WPP_SF_dD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(unsigned int *)(*(_QWORD *)(a2 + 48) + 8LL),
      a3,
      *(unsigned int *)(v3 + 24),
      *(_DWORD *)(*(_QWORD *)(a2 + 48) + 8LL));
  }
  SetEvent(*(HANDLE *)(v3 + 80));
  return 0;
}

```

## disassembly

```asm
0x14001d675  mov     [rsp+arg_8], rdx
0x14001d67a  push    rbx
0x14001d67b  push    rbp
0x14001d67c  sub     rsp, 38h
0x14001d680  mov     rbp, rdx
0x14001d683  lea     rax, WPP_GLOBAL_Control
0x14001d68a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d691  cmp     rcx, rax
0x14001d694  jz      short loc_14001D6BA
0x14001d696  test    byte ptr [rcx+1Ch], 1
0x14001d69a  jz      short loc_14001D6BA
0x14001d69c  mov     rax, [rbp+30h]
0x14001d6a0  mov     edx, [rax+8]
0x14001d6a3  mov     [rsp+48h+var_28], edx
0x14001d6a7  mov     rbx, [rbp+50h]
0x14001d6ab  mov     r9d, [rbx+18h]
0x14001d6af  mov     rcx, [rcx+10h]
0x14001d6b3  call    WPP_SF_dD
0x14001d6b8  jmp     short loc_14001D6BE
0x14001d6ba  mov     rbx, [rbp+50h]
0x14001d6be  mov     rcx, [rbx+50h]; hEvent
0x14001d6c2  call    cs:__imp_SetEvent
0x14001d6c8  nop
0x14001d6c9  mov     rax, 0
0x14001d6d3  add     rsp, 38h
0x14001d6d7  pop     rbp
0x14001d6d8  pop     rbx
0x14001d6d9  retn
```
