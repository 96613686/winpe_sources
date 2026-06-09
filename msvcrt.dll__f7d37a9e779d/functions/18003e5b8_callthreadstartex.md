# _callthreadstartex

- ea: `0x18003e5b8`
- end: `0x18003e5eb`
- name: `_callthreadstartex`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003e630`

## callees

- `0x18002b2b0`
- `0x18003d710`
- `0x18003e048`
- `0x18003e600`
- `0x1800798c0`

## pseudocode

```c
void __noreturn callthreadstartex()
{
  __int64 v0; // rax
  unsigned int v1; // eax

  v0 = getptd();
  v1 = (*(__int64 (__fastcall **)(_QWORD))(v0 + 144))(*(_QWORD *)(v0 + 152));
  endthreadex(v1);
}

```

## disassembly

```asm
0x18003e5b8  sub     rsp, 28h
0x18003e5bc  call    _getptd
0x18003e5c1  nop
0x18003e5c2  mov     rcx, [rax+98h]
0x18003e5c9  mov     rax, [rax+90h]
0x18003e5d0  call    cs:__guard_dispatch_icall_fptr
0x18003e5d6  mov     ecx, eax; ReturnCode
0x18003e5d8  call    _endthreadex
0x18003e5de  mov     ecx, eax; Code
0x18003e5e0  call    _exit
0x18003e5e6  add     rsp, 28h
0x18003e5ea  retn
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
