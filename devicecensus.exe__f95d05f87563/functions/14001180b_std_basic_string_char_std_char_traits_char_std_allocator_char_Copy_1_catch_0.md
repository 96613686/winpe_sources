# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x14001180b`
- end: `0x140011830`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001fcc`
- `0x14000305c`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::string::_Tidy(*(_QWORD *)(v2 + 96), a2, 0);
  throw;
}

```

## disassembly

```asm
0x14001180b  mov     [rsp+arg_8], rdx
0x140011810  push    rbp
0x140011811  sub     rsp, 20h
0x140011815  mov     rbp, rdx
0x140011818  xor     r8d, r8d
0x14001181b  mov     dl, 1
0x14001181d  mov     rcx, [rbp+60h]
0x140011821  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140011826  xor     edx, edx; pThrowInfo
0x140011828  xor     ecx, ecx; pExceptionObject
0x14001182a  call    _CxxThrowException_0
```
