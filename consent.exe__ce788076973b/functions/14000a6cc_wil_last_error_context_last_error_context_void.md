# wil::last_error_context::last_error_context(void)

- ea: `0x14000a6cc`
- end: `0x14000a6ea`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14000d6e4`
- `0x14000e504`
- `0x14000e8b0`
- `0x14000ec00`
- `0x14001373c`
- `0x140019b34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a6d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a6d5`

## pseudocode

```c
wil::last_error_context *__fastcall wil::last_error_context::last_error_context(wil::last_error_context *this)
{
  wil::last_error_context *result; // rax

  *((_DWORD *)this + 1) = GetLastError();
  result = this;
  *(_BYTE *)this = 0;
  return result;
}

```

## disassembly

```asm
0x14000a6cc  push    rbx
0x14000a6ce  sub     rsp, 20h
0x14000a6d2  mov     rbx, rcx
0x14000a6d5  call    cs:__imp_GetLastError
0x14000a6db  mov     [rbx+4], eax
0x14000a6de  mov     rax, rbx
0x14000a6e1  mov     byte ptr [rbx], 0
0x14000a6e4  add     rsp, 20h
0x14000a6e8  pop     rbx
0x14000a6e9  retn
```
