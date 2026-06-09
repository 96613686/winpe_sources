# std::_Ref_count_del_alloc<__ExceptionPtr,void (*)(__ExceptionPtr *),_DebugMallocator<int>>::_Delete_this(void)

- ea: `0x1800183c0`
- end: `0x1800183e4`
- name: `?_Delete_this@?$_Ref_count_del_alloc@V__ExceptionPtr@@P6AXPEAV1@@ZV?$_DebugMallocator@H@@@std@@EEAAXXZ`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18001d300`
- `0x18007d020`

## pseudocode

```c
void __fastcall std::_Ref_count_del_alloc<__ExceptionPtr,void (*)(__ExceptionPtr *),_DebugMallocator<int>>::_Delete_this(
        void *a1)
{
  (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)a1 + 16LL))(a1, 0);
  free(a1);
}

```

## disassembly

```asm
0x1800183c0  push    rbx
0x1800183c2  sub     rsp, 20h
0x1800183c6  mov     rax, [rcx]
0x1800183c9  xor     edx, edx
0x1800183cb  mov     rbx, rcx
0x1800183ce  mov     rax, [rax+10h]
0x1800183d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183d7  mov     rcx, rbx
0x1800183da  add     rsp, 20h
0x1800183de  pop     rbx
0x1800183df  jmp     free
```
