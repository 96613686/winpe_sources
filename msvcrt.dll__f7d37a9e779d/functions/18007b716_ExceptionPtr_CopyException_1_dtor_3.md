# ___ExceptionPtr::_CopyException_::_1_::dtor$3

- ea: `0x18007b716`
- end: `0x18007b73f`
- name: `___ExceptionPtr::_CopyException_::_1_::dtor$3`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180017b5c`
- `0x18007b716`

## pseudocode

```c
__int64 __fastcall __ExceptionPtr::_CopyException_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::shared_ptr<__ExceptionPtr>::~shared_ptr<__ExceptionPtr>(*(_QWORD *)(a2 + 224));
  }
  return result;
}

```

## disassembly

```asm
0x18007b716  push    rbp
0x18007b718  sub     rsp, 20h
0x18007b71c  mov     rbp, rdx
0x18007b71f  mov     eax, [rbp+20h]
0x18007b722  and     eax, 1
0x18007b725  test    eax, eax
0x18007b727  jz      short loc_18007B739
0x18007b729  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18007b72d  mov     rcx, [rbp+0E0h]
0x18007b734  call    ??1?$shared_ptr@V__ExceptionPtr@@@std@@QEAA@XZ; std::shared_ptr<__ExceptionPtr>::~shared_ptr<__ExceptionPtr>(void)
0x18007b739  add     rsp, 20h
0x18007b73d  pop     rbp
0x18007b73e  retn
```
