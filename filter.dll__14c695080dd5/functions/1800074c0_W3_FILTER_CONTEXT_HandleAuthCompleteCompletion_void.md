# W3_FILTER_CONTEXT::HandleAuthCompleteCompletion(void)

- ea: `0x1800074c0`
- end: `0x1800074ea`
- name: `?HandleAuthCompleteCompletion@W3_FILTER_CONTEXT@@QEAAXXZ`
- size: `42`
- prototype: `void __fastcall(W3_FILTER_CONTEXT *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800019c0`
- `0x180002a40`

## callees

- `0x18000d010`

## pseudocode

```c
void __fastcall W3_FILTER_CONTEXT::HandleAuthCompleteCompletion(W3_FILTER_CONTEXT *this)
{
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 256LL))(*((_QWORD *)this + 4));
  *((_QWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x1800074c0  push    rbx
0x1800074c2  sub     rsp, 20h
0x1800074c6  mov     rbx, rcx
0x1800074c9  mov     rcx, [rcx+20h]
0x1800074cd  mov     rax, [rcx]
0x1800074d0  mov     rax, [rax+100h]
0x1800074d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074dc  mov     qword ptr [rbx+20h], 0
0x1800074e4  add     rsp, 20h
0x1800074e8  pop     rbx
0x1800074e9  retn
```
