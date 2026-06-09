# std::current_exception(void)

- ea: `0x1800c1338`
- end: `0x1800c1368`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x1800f2fd0`
- `0x1800f30a0`
- `0x1800f3190`
- `0x1800f3260`
- `0x1800f4800`
- `0x1800f4950`
- `0x1800f5b50`
- `0x1800f5c10`
- `0x1800f5d50`
- `0x1800f5dd0`
- `0x1800f5e70`
- `0x1800f5ef0`
- `0x1800f5f50`
- `0x1800f6000`
- `0x1800f6200`
- `0x1800f6750`
- `0x1800fa452`
- `0x1800fa4fe`
- `0x1800fa5aa`
- `0x1800fc0b6`
- `0x1800fc108`
- `0x1800fc354`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800c1359`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800c1359`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800c1350`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800c1350`

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
0x1800c1338  push    rbx
0x1800c133a  sub     rsp, 20h
0x1800c133e  mov     rbx, rcx
0x1800c1341  mov     qword ptr [rcx], 0
0x1800c1348  mov     qword ptr [rcx+8], 0
0x1800c1350  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800c1356  mov     rcx, rbx
0x1800c1359  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800c135f  mov     rax, rbx
0x1800c1362  add     rsp, 20h
0x1800c1366  pop     rbx
0x1800c1367  retn
```
