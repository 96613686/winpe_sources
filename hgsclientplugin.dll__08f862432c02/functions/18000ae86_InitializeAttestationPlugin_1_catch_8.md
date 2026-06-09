# _InitializeAttestationPlugin_::_1_::catch$8

- ea: `0x18000ae86`
- end: `0x18000aebb`
- name: `_InitializeAttestationPlugin_::_1_::catch$8`
- size: `53`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008288`

## pseudocode

```c
__int64 __fastcall InitializeAttestationPlugin_::_1_::catch_8(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 272) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 264),
                            (void *)0x51,
                            a3,
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18000ae86  mov     [rsp+arg_8], rdx
0x18000ae8b  push    rbp
0x18000ae8c  sub     rsp, 20h
0x18000ae90  mov     rbp, rdx
0x18000ae93  mov     rcx, [rbp+108h]; this
0x18000ae9a  mov     edx, 51h ; 'Q'; void *
0x18000ae9f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000aea4  mov     [rbp+110h], eax
0x18000aeaa  mov     rax, 0
0x18000aeb4  add     rsp, 20h
0x18000aeb8  pop     rbp
0x18000aeb9  retn
```
