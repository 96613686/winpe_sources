# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x14000a90c`
- end: `0x14000a931`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400064f0`
- `0x14000a21a`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::string::_Tidy(*(_QWORD *)(v2 + 80), a2, 0);
  throw;
}

```

## disassembly

```asm
0x14000a90c  mov     [rsp+arg_8], rdx
0x14000a911  push    rbp
0x14000a912  sub     rsp, 20h
0x14000a916  mov     rbp, rdx
0x14000a919  xor     r8d, r8d
0x14000a91c  mov     dl, 1
0x14000a91e  mov     rcx, [rbp+50h]
0x14000a922  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14000a927  xor     edx, edx; pThrowInfo
0x14000a929  xor     ecx, ecx; pExceptionObject
0x14000a92b  call    _CxxThrowException_0
```
