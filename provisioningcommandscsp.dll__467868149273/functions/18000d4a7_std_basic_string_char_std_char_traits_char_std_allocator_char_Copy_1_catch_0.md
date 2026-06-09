# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x18000d4a7`
- end: `0x18000d4cc`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005d14`
- `0x18000cb69`

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
0x18000d4a7  mov     [rsp+arg_8], rdx
0x18000d4ac  push    rbp
0x18000d4ad  sub     rsp, 20h
0x18000d4b1  mov     rbp, rdx
0x18000d4b4  xor     r8d, r8d
0x18000d4b7  mov     dl, 1
0x18000d4b9  mov     rcx, [rbp+50h]
0x18000d4bd  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x18000d4c2  xor     edx, edx; pThrowInfo
0x18000d4c4  xor     ecx, ecx; pExceptionObject
0x18000d4c6  call    _CxxThrowException_0
```
