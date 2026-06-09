# _std::_Uninit_move_GUIDVarInfo___GUIDVarInfo___std::allocator_GUIDVarInfo__GUIDVarInfo__::_1_::catch$1

- ea: `0x180013ffc`
- end: `0x18001402c`
- name: `_std::_Uninit_move_GUIDVarInfo___GUIDVarInfo___std::allocator_GUIDVarInfo__GUIDVarInfo__::_1_::catch$1`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f9c`
- `0x18000c528`
- `0x180013ffc`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_GUIDVarInfo___GUIDVarInfo___std::allocator_GUIDVarInfo__GUIDVarInfo__::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 80 )
    std::_Wrap_alloc<std::allocator<GUIDVarInfo>>::destroy<GUIDVarInfo>(a1, i);
  throw;
}

```

## disassembly

```asm
0x180013ffc  mov     [rsp+arg_8], rdx
0x180014001  push    rbx
0x180014002  push    rbp
0x180014003  sub     rsp, 28h
0x180014007  mov     rbp, rdx
0x18001400a  mov     rbx, [rbp+48h]
0x18001400e  jmp     short loc_18001401C
0x180014010  mov     rdx, rbx
0x180014013  call    ??$destroy@UGUIDVarInfo@@@?$_Wrap_alloc@V?$allocator@UGUIDVarInfo@@@std@@@std@@QEAAXPEAUGUIDVarInfo@@@Z; std::_Wrap_alloc<std::allocator<GUIDVarInfo>>::destroy<GUIDVarInfo>(GUIDVarInfo *)
0x180014018  add     rbx, 50h ; 'P'
0x18001401c  cmp     rbx, [rbp+40h]
0x180014020  jnz     short loc_180014010
0x180014022  xor     edx, edx; pThrowInfo
0x180014024  xor     ecx, ecx; pExceptionObject
0x180014026  call    _CxxThrowException_0
```
