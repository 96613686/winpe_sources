# _HvSysConfigTimer::Initialize_::_1_::catch$13

- ea: `0x18000966f`
- end: `0x180009695`
- name: `_HvSysConfigTimer::Initialize_::_1_::catch$13`
- size: `38`
- prototype: `__int64 __fastcall(wil *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800078e8`

## pseudocode

```c
__int64 __fastcall HvSysConfigTimer::Initialize_::_1_::catch_13(wil *a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = wil::ResultFromCaughtException(a1);
  return 0;
}

```

## disassembly

```asm
0x18000966f  mov     [rsp+arg_8], rdx
0x180009674  push    rbp
0x180009675  sub     rsp, 30h
0x180009679  mov     rbp, rdx
0x18000967c  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180009681  mov     [rbp+30h], eax
0x180009684  mov     rax, 0
0x18000968e  add     rsp, 30h
0x180009692  pop     rbp
0x180009693  retn
```
