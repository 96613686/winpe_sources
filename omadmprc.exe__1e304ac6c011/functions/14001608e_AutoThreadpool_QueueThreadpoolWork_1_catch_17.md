# _AutoThreadpool::QueueThreadpoolWork_::_1_::catch$17

- ea: `0x14001608e`
- end: `0x1400160b4`
- name: `_AutoThreadpool::QueueThreadpoolWork_::_1_::catch$17`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140011a7c`

## pseudocode

```c
__int64 __fastcall AutoThreadpool::QueueThreadpoolWork_::_1_::catch_17(wil *a1, __int64 a2)
{
  *(_DWORD *)(a2 + 104) = wil::ResultFromCaughtException(a1);
  return 0;
}

```

## disassembly

```asm
0x14001608e  mov     [rsp+arg_8], rdx
0x140016093  push    rbp
0x140016094  sub     rsp, 20h
0x140016098  mov     rbp, rdx
0x14001609b  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x1400160a0  mov     [rbp+68h], eax
0x1400160a3  mov     rax, 0
0x1400160ad  add     rsp, 20h
0x1400160b1  pop     rbp
0x1400160b2  retn
```
