# _std::_Uninit_move_StoredHelperAttributeInfo___StoredHelperAttributeInfo___std::allocator_StoredHelperAttributeInfo__StoredHelperAttributeInfo__::_1_::catch$1

- ea: `0x180014032`
- end: `0x180014065`
- name: `_std::_Uninit_move_StoredHelperAttributeInfo___StoredHelperAttributeInfo___std::allocator_StoredHelperAttributeInfo__StoredHelperAttributeInfo__::_1_::catch$1`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f9c`
- `0x18000c538`
- `0x180014032`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_StoredHelperAttributeInfo___StoredHelperAttributeInfo___std::allocator_StoredHelperAttributeInfo__StoredHelperAttributeInfo__::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 136 )
    std::_Wrap_alloc<std::allocator<StoredHelperAttributeInfo>>::destroy<StoredHelperAttributeInfo>(a1, i);
  throw;
}

```

## disassembly

```asm
0x180014032  mov     [rsp+arg_8], rdx
0x180014037  push    rbx
0x180014038  push    rbp
0x180014039  sub     rsp, 28h
0x18001403d  mov     rbp, rdx
0x180014040  mov     rbx, [rbp+48h]
0x180014044  jmp     short loc_180014055
0x180014046  mov     rdx, rbx
0x180014049  call    ??$destroy@UStoredHelperAttributeInfo@@@?$_Wrap_alloc@V?$allocator@UStoredHelperAttributeInfo@@@std@@@std@@QEAAXPEAUStoredHelperAttributeInfo@@@Z; std::_Wrap_alloc<std::allocator<StoredHelperAttributeInfo>>::destroy<StoredHelperAttributeInfo>(StoredHelperAttributeInfo *)
0x18001404e  add     rbx, 88h
0x180014055  cmp     rbx, [rbp+40h]
0x180014059  jnz     short loc_180014046
0x18001405b  xor     edx, edx; pThrowInfo
0x18001405d  xor     ecx, ecx; pExceptionObject
0x18001405f  call    _CxxThrowException_0
```
