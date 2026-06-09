# _AutoThreadpool::Initialize_::_1_::catch$7

- ea: `0x140016035`
- end: `0x140016064`
- name: `_AutoThreadpool::Initialize_::_1_::catch$7`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140011a7c`
- `0x140015438`

## pseudocode

```c
__int64 __fastcall AutoThreadpool::Initialize_::_1_::catch_7(__int64 a1, __int64 a2)
{
  wil *v3; // rcx

  AutoThreadpool::UninitializeAndWaitForPendingWorkItems(*(AutoThreadpool **)(a2 + 80));
  *(_DWORD *)(a2 + 88) = wil::ResultFromCaughtException(v3);
  return 0;
}

```

## disassembly

```asm
0x140016035  mov     [rsp+arg_8], rdx
0x14001603a  push    rbp
0x14001603b  sub     rsp, 20h
0x14001603f  mov     rbp, rdx
0x140016042  mov     rcx, [rbp+50h]; this
0x140016046  call    ?UninitializeAndWaitForPendingWorkItems@AutoThreadpool@@QEAAXXZ; AutoThreadpool::UninitializeAndWaitForPendingWorkItems(void)
0x14001604b  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x140016050  mov     [rbp+58h], eax
0x140016053  mov     rax, 0
0x14001605d  add     rsp, 20h
0x140016061  pop     rbp
0x140016062  retn
```
