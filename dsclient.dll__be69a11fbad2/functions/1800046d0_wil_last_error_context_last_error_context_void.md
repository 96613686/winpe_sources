# wil::last_error_context::last_error_context(void)

- ea: `0x1800046d0`
- end: `0x1800046ee`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180005248`
- `0x180006bb0`
- `0x18000705c`
- `0x180008d14`
- `0x180008dbc`
- `0x180008e10`
- `0x180008e64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046d9`

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
0x1800046d0  push    rbx
0x1800046d2  sub     rsp, 20h
0x1800046d6  mov     rbx, rcx
0x1800046d9  call    cs:__imp_GetLastError
0x1800046df  mov     [rbx+4], eax
0x1800046e2  mov     rax, rbx
0x1800046e5  mov     byte ptr [rbx], 0
0x1800046e8  add     rsp, 20h
0x1800046ec  pop     rbx
0x1800046ed  retn
```
