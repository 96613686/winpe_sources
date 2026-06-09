# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x140019a72`
- end: `0x140019a97`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400027bc`
- `0x140010090`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 80), a2, 0);
  throw;
}

```

## disassembly

```asm
0x140019a72  mov     [rsp+arg_8], rdx
0x140019a77  push    rbp
0x140019a78  sub     rsp, 20h
0x140019a7c  mov     rbp, rdx
0x140019a7f  xor     r8d, r8d
0x140019a82  mov     dl, 1
0x140019a84  mov     rcx, [rbp+50h]
0x140019a88  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140019a8d  xor     edx, edx; pThrowInfo
0x140019a8f  xor     ecx, ecx; pExceptionObject
0x140019a91  call    _CxxThrowException_0
```
