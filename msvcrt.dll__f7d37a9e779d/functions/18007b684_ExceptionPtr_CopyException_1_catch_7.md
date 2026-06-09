# ___ExceptionPtr::_CopyException_::_1_::catch$7

- ea: `0x18007b684`
- end: `0x18007b6c7`
- name: `___ExceptionPtr::_CopyException_::_1_::catch$7`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000aec0`
- `0x180017ee0`
- `0x180017fec`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall __ExceptionPtr::_CopyException_::_1_::catch_7(__int64 a1, __int64 a2)
{
  __ExceptionPtr::_BadAllocException(*(_QWORD *)(a2 + 224));
  *(_QWORD *)(a2 + 160) = &std::bad_alloc::`vftable';
  exception::~exception((exception *)(a2 + 160));
  return &loc_1800181A8;
}

```

## disassembly

```asm
0x18007b684  mov     [rsp+arg_8], rdx
0x18007b689  push    rbp
0x18007b68a  sub     rsp, 20h
0x18007b68e  mov     rbp, rdx
0x18007b691  mov     rcx, [rbp+0E0h]
0x18007b698  call    ?_BadAllocException@__ExceptionPtr@@SA?AV?$shared_ptr@V__ExceptionPtr@@@std@@XZ; __ExceptionPtr::_BadAllocException(void)
0x18007b69d  nop
0x18007b69e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18007b6a5  mov     [rbp+0A0h], rax
0x18007b6ac  lea     rcx, [rbp+0A0h]; this
0x18007b6b3  call    ??1exception@@UEAA@XZ; exception::~exception(void)
0x18007b6b8  nop
0x18007b6b9  lea     rax, loc_1800181A8
0x18007b6c0  add     rsp, 20h
0x18007b6c4  pop     rbp
0x18007b6c5  retn
```
