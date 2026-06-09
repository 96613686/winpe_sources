# wil::last_error_context::last_error_context(void)

- ea: `0x1800074a0`
- end: `0x1800074be`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800083e4`
- `0x180009dd8`
- `0x180009ec4`
- `0x18000a504`
- `0x18000caa4`
- `0x18000cb4c`
- `0x18000cba4`
- `0x18000cbf8`
- `0x18000cc4c`
- `0x18000cca0`
- `0x18000eecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074a9`

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
0x1800074a0  push    rbx
0x1800074a2  sub     rsp, 20h
0x1800074a6  mov     rbx, rcx
0x1800074a9  call    cs:__imp_GetLastError
0x1800074af  mov     [rbx+4], eax
0x1800074b2  mov     rax, rbx
0x1800074b5  mov     byte ptr [rbx], 0
0x1800074b8  add     rsp, 20h
0x1800074bc  pop     rbx
0x1800074bd  retn
```
