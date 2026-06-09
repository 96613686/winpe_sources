# _GetInitiationIDFromKeyPath_::_1_::catch$4

- ea: `0x140015d9f`
- end: `0x140015dc5`
- name: `_GetInitiationIDFromKeyPath_::_1_::catch$4`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140011a7c`

## pseudocode

```c
__int64 __fastcall GetInitiationIDFromKeyPath_::_1_::catch_4(wil *a1, __int64 a2)
{
  *(_DWORD *)(a2 + 32) = wil::ResultFromCaughtException(a1);
  return 0;
}

```

## disassembly

```asm
0x140015d9f  mov     [rsp+arg_8], rdx
0x140015da4  push    rbp
0x140015da5  sub     rsp, 20h
0x140015da9  mov     rbp, rdx
0x140015dac  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x140015db1  mov     [rbp+20h], eax
0x140015db4  mov     rax, 0
0x140015dbe  add     rsp, 20h
0x140015dc2  pop     rbp
0x140015dc3  retn
```
