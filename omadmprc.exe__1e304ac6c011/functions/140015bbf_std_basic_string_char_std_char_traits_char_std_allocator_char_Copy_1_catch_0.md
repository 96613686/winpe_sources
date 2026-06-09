# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0

- ea: `0x140015bbf`
- end: `0x140015be4`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400023b8`
- `0x140009e60`

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
0x140015bbf  mov     [rsp+arg_8], rdx
0x140015bc4  push    rbp
0x140015bc5  sub     rsp, 20h
0x140015bc9  mov     rbp, rdx
0x140015bcc  xor     r8d, r8d
0x140015bcf  mov     dl, 1
0x140015bd1  mov     rcx, [rbp+50h]
0x140015bd5  call    ?_Tidy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_N_K@Z; std::string::_Tidy(bool,unsigned __int64)
0x140015bda  xor     edx, edx; pThrowInfo
0x140015bdc  xor     ecx, ecx; pExceptionObject
0x140015bde  call    _CxxThrowException_0
```
