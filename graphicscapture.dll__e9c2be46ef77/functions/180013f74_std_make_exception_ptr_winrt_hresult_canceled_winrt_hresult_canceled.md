# std::make_exception_ptr<winrt::hresult_canceled>(winrt::hresult_canceled)

- ea: `0x180013f74`
- end: `0x180013fbc`
- name: `??$make_exception_ptr@Uhresult_canceled@winrt@@@std@@YA?AVexception_ptr@0@Uhresult_canceled@winrt@@@Z`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001473c`

## callees

- `0x18000399c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180013fa0`
- `msvcp_win!?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z` at `0x180013fa0`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180013f8d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180013f8d`

## pseudocode

```c
_QWORD *__fastcall std::make_exception_ptr<winrt::hresult_canceled>(_QWORD *a1, void *a2)
{
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCreate(a1);
  __ExceptionPtrCopyException(a1, a2, &TI2_AUhresult_canceled_winrt__);
  winrt::hresult_error::~hresult_error((winrt::hresult_error *)a2);
  return a1;
}

```

## disassembly

```asm
0x180013f74  mov     [rsp+arg_8], rbx
0x180013f79  push    rdi
0x180013f7a  sub     rsp, 20h
0x180013f7e  xor     eax, eax
0x180013f80  mov     rbx, rdx
0x180013f83  mov     [rcx], rax
0x180013f86  mov     rdi, rcx
0x180013f89  mov     [rcx+8], rax
0x180013f8d  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180013f93  lea     r8, _TI2?AUhresult_canceled@winrt@@; throw info for 'struct winrt::hresult_canceled'
0x180013f9a  mov     rdx, rbx
0x180013f9d  mov     rcx, rdi
0x180013fa0  call    cs:__imp_?__ExceptionPtrCopyException@@YAXPEAXPEBX1@Z; __ExceptionPtrCopyException(void *,void const *,void const *)
0x180013fa6  mov     rcx, rbx; this
0x180013fa9  call    ??1hresult_error@winrt@@QEAA@XZ; winrt::hresult_error::~hresult_error(void)
0x180013fae  mov     rbx, [rsp+28h+arg_8]
0x180013fb3  mov     rax, rdi
0x180013fb6  add     rsp, 20h
0x180013fba  pop     rdi
0x180013fbb  retn
```
