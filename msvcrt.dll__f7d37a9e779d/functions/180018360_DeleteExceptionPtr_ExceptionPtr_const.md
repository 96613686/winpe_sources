# _DeleteExceptionPtr(__ExceptionPtr * const)

- ea: `0x180018360`
- end: `0x18001837b`
- name: `?_DeleteExceptionPtr@@YAXQEAV__ExceptionPtr@@@Z`
- size: `27`
- prototype: `void __fastcall(struct __ExceptionPtr *const)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180017bb8`
- `0x18001d300`

## pseudocode

```c
void __fastcall _DeleteExceptionPtr(struct __ExceptionPtr *const a1)
{
  __ExceptionPtr::~__ExceptionPtr(a1);
  free(a1);
}

```

## disassembly

```asm
0x180018360  push    rbx
0x180018362  sub     rsp, 20h
0x180018366  mov     rbx, rcx
0x180018369  call    ??1__ExceptionPtr@@QEAA@XZ
0x18001836e  mov     rcx, rbx
0x180018371  add     rsp, 20h
0x180018375  pop     rbx
0x180018376  jmp     free
```
