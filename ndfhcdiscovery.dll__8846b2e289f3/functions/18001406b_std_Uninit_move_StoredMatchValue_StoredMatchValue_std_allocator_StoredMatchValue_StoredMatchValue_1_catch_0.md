# _std::_Uninit_move_StoredMatchValue___StoredMatchValue___std::allocator_StoredMatchValue__StoredMatchValue__::_1_::catch$0

- ea: `0x18001406b`
- end: `0x18001409b`
- name: `_std::_Uninit_move_StoredMatchValue___StoredMatchValue___std::allocator_StoredMatchValue__StoredMatchValue__::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f9c`
- `0x18000c548`
- `0x18001406b`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_StoredMatchValue___StoredMatchValue___std::allocator_StoredMatchValue__StoredMatchValue__::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 88); i != *(_QWORD *)(a2 + 80); i += 104 )
    std::_Wrap_alloc<std::allocator<StoredMatchValue>>::destroy<StoredMatchValue>(a1, i);
  throw;
}

```

## disassembly

```asm
0x18001406b  mov     [rsp+arg_8], rdx
0x180014070  push    rbx
0x180014071  push    rbp
0x180014072  sub     rsp, 28h
0x180014076  mov     rbp, rdx
0x180014079  mov     rbx, [rbp+58h]
0x18001407d  jmp     short loc_18001408B
0x18001407f  mov     rdx, rbx
0x180014082  call    ??$destroy@UStoredMatchValue@@@?$_Wrap_alloc@V?$allocator@UStoredMatchValue@@@std@@@std@@QEAAXPEAUStoredMatchValue@@@Z; std::_Wrap_alloc<std::allocator<StoredMatchValue>>::destroy<StoredMatchValue>(StoredMatchValue *)
0x180014087  add     rbx, 68h ; 'h'
0x18001408b  cmp     rbx, [rbp+50h]
0x18001408f  jnz     short loc_18001407F
0x180014091  xor     edx, edx; pThrowInfo
0x180014093  xor     ecx, ecx; pExceptionObject
0x180014095  call    _CxxThrowException_0
```
