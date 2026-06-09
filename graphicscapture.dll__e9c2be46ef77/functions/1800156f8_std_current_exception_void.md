# std::current_exception(void)

- ea: `0x1800156f8`
- end: `0x180015728`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180015eb4`
- `0x18001b30c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180015710`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180015710`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180015719`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180015719`

## pseudocode

```c
_QWORD *__fastcall std::current_exception(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCreate(a1);
  __ExceptionPtrCurrentException(a1);
  return a1;
}

```

## disassembly

```asm
0x1800156f8  push    rbx
0x1800156fa  sub     rsp, 20h
0x1800156fe  mov     rbx, rcx
0x180015701  mov     qword ptr [rcx], 0
0x180015708  mov     qword ptr [rcx+8], 0
0x180015710  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180015716  mov     rcx, rbx
0x180015719  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18001571f  mov     rax, rbx
0x180015722  add     rsp, 20h
0x180015726  pop     rbx
0x180015727  retn
```
