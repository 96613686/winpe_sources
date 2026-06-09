# COMP_FILE_CONTEXT::CleanupStoredContext(void)

- ea: `0x180001ec0`
- end: `0x180001efd`
- name: `?CleanupStoredContext@COMP_FILE_CONTEXT@@UEAAXXZ`
- size: `61`
- prototype: `void __fastcall(COMP_FILE_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001ec0`
- `0x1800054a0`
- `0x180009010`

## pseudocode

```c
void __fastcall COMP_FILE_CONTEXT::CleanupStoredContext(COMP_FILE_CONTEXT *this)
{
  if ( this )
  {
    *(_QWORD *)this = &COMP_FILE_CONTEXT::`vftable';
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
    operator delete(this);
  }
}

```

## disassembly

```asm
0x180001ec0  test    rcx, rcx
0x180001ec3  jz      short locret_180001EFC
0x180001ec5  push    rbx
0x180001ec6  sub     rsp, 20h
0x180001eca  lea     rax, ??_7COMP_FILE_CONTEXT@@6B@; const COMP_FILE_CONTEXT::`vftable'
0x180001ed1  mov     rbx, rcx
0x180001ed4  mov     [rcx], rax
0x180001ed7  mov     rcx, [rcx+10h]
0x180001edb  mov     rax, [rcx]
0x180001ede  mov     rax, [rax+10h]
0x180001ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ee7  mov     rcx, rbx; Block
0x180001eea  mov     qword ptr [rbx+10h], 0
0x180001ef2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001ef7  add     rsp, 20h
0x180001efb  pop     rbx
0x180001efc  retn
```
