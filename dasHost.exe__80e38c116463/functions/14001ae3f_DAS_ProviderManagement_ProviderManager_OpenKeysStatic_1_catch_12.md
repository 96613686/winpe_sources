# _DAS::ProviderManagement::ProviderManager::OpenKeysStatic_::_1_::catch$12

- ea: `0x14001ae3f`
- end: `0x14001ae6e`
- name: `_DAS::ProviderManagement::ProviderManager::OpenKeysStatic_::_1_::catch$12`
- size: `47`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140013734`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::OpenKeysStatic_::_1_::catch_12(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 104) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 88),
                            (void *)0x1D2,
                            a3,
                            a4);
  return 0;
}

```

## disassembly

```asm
0x14001ae3f  mov     [rsp+arg_8], rdx
0x14001ae44  push    rbp
0x14001ae45  sub     rsp, 30h
0x14001ae49  mov     rbp, rdx
0x14001ae4c  mov     rcx, [rbp+58h]; this
0x14001ae50  mov     edx, 1D2h; void *
0x14001ae55  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x14001ae5a  mov     [rbp+68h], eax
0x14001ae5d  mov     rax, 0
0x14001ae67  add     rsp, 30h
0x14001ae6b  pop     rbp
0x14001ae6c  retn
```
