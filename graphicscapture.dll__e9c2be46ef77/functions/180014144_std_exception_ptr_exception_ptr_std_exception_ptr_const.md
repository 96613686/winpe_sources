# std::exception_ptr::exception_ptr(std::exception_ptr const &)

- ea: `0x180014144`
- end: `0x18001416b`
- name: `??0exception_ptr@std@@QEAA@AEBV01@@Z`
- size: `39`
- prototype: `__int64 __fastcall(std::exception_ptr *__hidden this, const struct std::exception_ptr *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001b2b4`
- `0x18001b30c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001415c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001415c`

## pseudocode

```c
std::exception_ptr *__fastcall std::exception_ptr::exception_ptr(
        std::exception_ptr *this,
        const struct std::exception_ptr *a2)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  __ExceptionPtrCopy(this, a2);
  return this;
}

```

## disassembly

```asm
0x180014144  push    rbx
0x180014146  sub     rsp, 20h
0x18001414a  mov     rbx, rcx
0x18001414d  mov     qword ptr [rcx], 0
0x180014154  mov     qword ptr [rcx+8], 0
0x18001415c  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180014162  mov     rax, rbx
0x180014165  add     rsp, 20h
0x180014169  pop     rbx
0x18001416a  retn
```
