# wistd::exchange<std::exception_ptr,std::exception_ptr>(std::exception_ptr &,std::exception_ptr &&)

- ea: `0x1800423f4`
- end: `0x180042440`
- name: `??$exchange@Vexception_ptr@std@@V12@@wistd@@YA?AVexception_ptr@std@@AEAV12@$$QEAV12@@Z`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18004f554`
- `0x18004f6ac`
- `0x18004f7d4`
- `0x18004f8fc`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180042427`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180042427`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004241b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004241b`

## pseudocode

```c
_QWORD *__fastcall wistd::exchange<std::exception_ptr,std::exception_ptr>(_QWORD *a1, void *a2, const void *a3)
{
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCopy(a1, a2);
  __ExceptionPtrAssign(a2, a3);
  return a1;
}

```

## disassembly

```asm
0x1800423f4  mov     [rsp+arg_0], rbx
0x1800423f9  mov     [rsp+arg_8], rsi
0x1800423fe  push    rdi
0x1800423ff  sub     rsp, 20h
0x180042403  mov     rbx, r8
0x180042406  mov     qword ptr [rcx], 0
0x18004240d  mov     rdi, rdx
0x180042410  mov     qword ptr [rcx+8], 0
0x180042418  mov     rsi, rcx
0x18004241b  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180042421  mov     rdx, rbx
0x180042424  mov     rcx, rdi
0x180042427  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18004242d  mov     rbx, [rsp+28h+arg_0]
0x180042432  mov     rax, rsi
0x180042435  mov     rsi, [rsp+28h+arg_8]
0x18004243a  add     rsp, 20h
0x18004243e  pop     rdi
0x18004243f  retn
```
