# std::current_exception(void)

- ea: `0x1800f108c`
- end: `0x1800f10c9`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `61`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x18015f910`
- `0x18015fd80`
- `0x18015fef0`
- `0x18015ffa0`
- `0x180163940`
- `0x180166500`
- `0x180167040`
- `0x180167110`
- `0x1801681f0`
- `0x180168290`
- `0x180168390`
- `0x180168410`
- `0x180168490`
- `0x1801684f0`
- `0x180168550`
- `0x180168600`
- `0x1801687c0`
- `0x180168ce0`
- `0x180169524`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800f10b3`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800f10b3`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800f10a4`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800f10a4`

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
0x1800f108c  push    rbx
0x1800f108e  sub     rsp, 20h
0x1800f1092  mov     rbx, rcx
0x1800f1095  mov     qword ptr [rcx], 0
0x1800f109c  mov     qword ptr [rcx+8], 0
0x1800f10a4  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800f10ab  nop     dword ptr [rax+rax+00h]
0x1800f10b0  mov     rcx, rbx
0x1800f10b3  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800f10ba  nop     dword ptr [rax+rax+00h]
0x1800f10bf  mov     rax, rbx
0x1800f10c2  add     rsp, 20h
0x1800f10c6  pop     rbx
0x1800f10c7  retn
```
