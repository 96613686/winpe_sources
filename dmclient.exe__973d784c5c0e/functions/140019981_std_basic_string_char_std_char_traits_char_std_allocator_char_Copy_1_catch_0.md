# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x140019981`
- end: `0x1400199a6`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400027bc`
- `0x14000c010`

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
0x140019981  mov     [rsp+arg_8], rdx
0x140019986  push    rbp
0x140019987  sub     rsp, 20h
0x14001998b  mov     rbp, rdx
0x14001998e  xor     r8d, r8d
0x140019991  mov     dl, 1
0x140019993  mov     rcx, [rbp+50h]
0x140019997  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x14001999c  xor     edx, edx; pThrowInfo
0x14001999e  xor     ecx, ecx; pExceptionObject
0x1400199a0  call    _CxxThrowException_0
```
