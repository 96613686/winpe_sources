# _std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch$0

- ea: `0x14001d27a`
- end: `0x14001d29f`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001cc6`
- `0x140004f2c`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::string::_Tidy(*(_QWORD *)(a2 + 80), 1, 0);
  throw;
}

```

## disassembly

```asm
0x14001d27a  mov     [rsp+arg_8], rdx
0x14001d27f  push    rbp
0x14001d280  sub     rsp, 20h
0x14001d284  mov     rbp, rdx
0x14001d287  xor     r8d, r8d
0x14001d28a  mov     dl, 1
0x14001d28c  mov     rcx, [rbp+50h]
0x14001d290  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14001d295  xor     edx, edx; pThrowInfo
0x14001d297  xor     ecx, ecx; pExceptionObject
0x14001d299  call    _CxxThrowException_0
```
