# _CWiGigDAFProviderQuery::ShouldUpdate_::_1_::catch$1

- ea: `0x18001df4a`
- end: `0x18001dfb6`
- name: `_CWiGigDAFProviderQuery::ShouldUpdate_::_1_::catch$1`
- size: `108`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18001a4fc`
- `0x18001df4a`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWiGigDAFProviderQuery::ShouldUpdate_::_1_::catch_1(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  int v4; // r8d

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 80) + 8LL))(*(_QWORD *)(a2 + 80));
    WPP_SF_qs(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v4, *(_QWORD *)(a2 + 64), v3);
  }
  return 0;
}

```

## disassembly

```asm
0x18001df4a  mov     [rsp+arg_8], rdx
0x18001df4f  push    rbp
0x18001df50  sub     rsp, 30h
0x18001df54  mov     rbp, rdx
0x18001df57  lea     rcx, WPP_GLOBAL_Control
0x18001df5e  mov     rax, cs:WPP_GLOBAL_Control
0x18001df65  cmp     rax, rcx
0x18001df68  jz      short loc_18001DFA5
0x18001df6a  cmp     byte ptr [rax+19h], 1
0x18001df6e  jb      short loc_18001DFA5
0x18001df70  test    byte ptr [rax+1Ch], 1
0x18001df74  jz      short loc_18001DFA5
0x18001df76  mov     rcx, [rbp+50h]
0x18001df7a  mov     rax, [rcx]
0x18001df7d  mov     rax, [rax+8]
0x18001df81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df86  mov     edx, 1Eh
0x18001df8b  mov     [rsp+38h+var_18], rax
0x18001df90  mov     r9, [rbp+40h]
0x18001df94  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df9b  mov     rcx, [rcx+10h]
0x18001df9f  call    WPP_SF_qs
0x18001dfa4  nop
0x18001dfa5  mov     rax, 0
0x18001dfaf  add     rsp, 30h
0x18001dfb3  pop     rbp
0x18001dfb4  retn
```
