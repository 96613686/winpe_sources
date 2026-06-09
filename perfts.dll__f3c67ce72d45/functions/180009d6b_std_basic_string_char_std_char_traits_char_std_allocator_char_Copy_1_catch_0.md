# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x180009d6b`
- end: `0x180009d90`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002088`
- `0x1800027ec`

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
0x180009d6b  mov     [rsp+arg_8], rdx
0x180009d70  push    rbp
0x180009d71  sub     rsp, 20h
0x180009d75  mov     rbp, rdx
0x180009d78  xor     r8d, r8d
0x180009d7b  mov     dl, 1
0x180009d7d  mov     rcx, [rbp+60h]
0x180009d81  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x180009d86  xor     edx, edx; pThrowInfo
0x180009d88  xor     ecx, ecx; pExceptionObject
0x180009d8a  call    _CxxThrowException_0
```
