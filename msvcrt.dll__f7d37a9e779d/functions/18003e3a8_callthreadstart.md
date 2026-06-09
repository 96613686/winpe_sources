# _callthreadstart

- ea: `0x18003e3a8`
- end: `0x18003e3d9`
- name: `_callthreadstart`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003e420`

## callees

- `0x18002b2b0`
- `0x18003d710`
- `0x18003e048`
- `0x18003e3e0`
- `0x1800798c0`

## pseudocode

```c
void __noreturn callthreadstart()
{
  __int64 v0; // rax

  v0 = getptd();
  (*(void (__fastcall **)(_QWORD))(v0 + 144))(*(_QWORD *)(v0 + 152));
  endthread();
}

```

## disassembly

```asm
0x18003e3a8  sub     rsp, 28h
0x18003e3ac  call    _getptd
0x18003e3b1  nop
0x18003e3b2  mov     rcx, [rax+98h]
0x18003e3b9  mov     rax, [rax+90h]
0x18003e3c0  call    cs:__guard_dispatch_icall_fptr
0x18003e3c6  call    _endthread
0x18003e3cc  mov     ecx, eax; Code
0x18003e3ce  call    _exit
0x18003e3d4  add     rsp, 28h
0x18003e3d8  retn
0x18007bdf3  push    rbp
0x18007bdf5  sub     rsp, 20h
0x18007bdf9  mov     rbp, rdx
0x18007bdfc  mov     rdx, rcx
0x18007bdff  mov     rcx, [rcx]
0x18007be02  mov     ecx, [rcx]
0x18007be04  call    _XcptFilter
0x18007be09  nop
0x18007be0a  add     rsp, 20h
0x18007be0e  pop     rbp
0x18007be0f  retn
```
