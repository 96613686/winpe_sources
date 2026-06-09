# std::current_exception(void)

- ea: `0x1800271b0`
- end: `0x1800271ed`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `61`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800449f0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800271c8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800271c8`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800271d7`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800271d7`

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
0x1800271b0  push    rbx
0x1800271b2  sub     rsp, 20h
0x1800271b6  mov     rbx, rcx
0x1800271b9  mov     qword ptr [rcx], 0
0x1800271c0  mov     qword ptr [rcx+8], 0
0x1800271c8  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800271cf  nop     dword ptr [rax+rax+00h]
0x1800271d4  mov     rcx, rbx
0x1800271d7  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800271de  nop     dword ptr [rax+rax+00h]
0x1800271e3  mov     rax, rbx
0x1800271e6  add     rsp, 20h
0x1800271ea  pop     rbx
0x1800271eb  retn
```
