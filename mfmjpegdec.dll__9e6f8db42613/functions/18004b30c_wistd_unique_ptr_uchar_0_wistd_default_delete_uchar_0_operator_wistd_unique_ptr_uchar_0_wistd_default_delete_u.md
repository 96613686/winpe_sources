# wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)

- ea: `0x18004b30c`
- end: `0x18004b338`
- name: `??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z`
- size: `44`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180049e90`
- `0x18004bd00`
- `0x18004c424`
- `0x1800513a0`
- `0x180054e08`

## callees

- `0x1800245f0`
- `0x18004b30c`

## pseudocode

```c
void **__fastcall wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(
        void **a1,
        const struct std::nothrow_t *a2)
{
  void *v2; // rax
  void *v4; // rcx

  v2 = *(void **)a2;
  *(_QWORD *)a2 = 0;
  v4 = *a1;
  *a1 = v2;
  if ( v4 )
    operator delete(v4, a2);
  return a1;
}

```

## disassembly

```asm
0x18004b30c  push    rbx
0x18004b30e  sub     rsp, 20h
0x18004b312  mov     rax, [rdx]
0x18004b315  mov     rbx, rcx
0x18004b318  mov     qword ptr [rdx], 0
0x18004b31f  mov     rcx, [rcx]; void *
0x18004b322  mov     [rbx], rax
0x18004b325  test    rcx, rcx
0x18004b328  jz      short loc_18004B32F
0x18004b32a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004b32f  mov     rax, rbx
0x18004b332  add     rsp, 20h
0x18004b336  pop     rbx
0x18004b337  retn
```
