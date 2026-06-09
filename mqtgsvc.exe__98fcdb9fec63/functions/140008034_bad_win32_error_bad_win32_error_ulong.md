# bad_win32_error::bad_win32_error(ulong)

- ea: `0x140008034`
- end: `0x140008063`
- name: `??0bad_win32_error@@QEAA@K@Z`
- size: `47`
- prototype: `bad_win32_error *__fastcall(bad_win32_error *this, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x14000858c`
- `0x140008c44`
- `0x140008f50`
- `0x14000a6dc`
- `0x14000ab14`
- `0x14000b180`
- `0x14000d00c`
- `0x14000d110`
- `0x14000e570`
- `0x14000e768`
- `0x14000eb04`
- `0x14001c668`
- `0x14001c700`

## callees

- `0x140007fd0`

## pseudocode

```c
bad_win32_error *__fastcall bad_win32_error::bad_win32_error(bad_win32_error *this, int a2)
{
  bad_api::bad_api(this);
  *((_DWORD *)this + 6) = a2;
  *(_QWORD *)this = &bad_win32_error::`vftable';
  return this;
}

```

## disassembly

```asm
0x140008034  mov     [rsp+arg_0], rbx
0x140008039  push    rdi
0x14000803a  sub     rsp, 20h
0x14000803e  mov     ebx, edx
0x140008040  mov     rdi, rcx
0x140008043  call    ??0bad_api@@QEAA@XZ; bad_api::bad_api(void)
0x140008048  lea     rax, ??_7bad_win32_error@@6B@; const bad_win32_error::`vftable'
0x14000804f  mov     [rdi+18h], ebx
0x140008052  mov     rbx, [rsp+28h+arg_0]
0x140008057  mov     [rdi], rax
0x14000805a  mov     rax, rdi
0x14000805d  add     rsp, 20h
0x140008061  pop     rdi
0x140008062  retn
```
