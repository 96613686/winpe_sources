# AutoThreadpool::ThreadpoolWorkItemCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x140015400`
- end: `0x14001542f`
- name: `?ThreadpoolWorkItemCallback@AutoThreadpool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `47`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x140017010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140015423`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AutoThreadpool::ThreadpoolWorkItemCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD *Context,
        PTP_WORK Work)
{
  ((void (__fastcall *)(_QWORD, _QWORD *, PTP_WORK))*Context)(Context[1], Context, Work);
  operator delete(Context);
}

```

## disassembly

```asm
0x140015400  push    rbx
0x140015402  sub     rsp, 20h
0x140015406  mov     rbx, rdx
0x140015409  mov     [rsp+28h+arg_8], rdx
0x14001540e  mov     rcx, [rdx+8]
0x140015412  mov     rax, [rdx]
0x140015415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001541a  nop
0x14001541b  mov     rcx, rbx
0x14001541e  add     rsp, 20h
0x140015422  pop     rbx
0x140015423  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
