# wil::last_error_context::last_error_context(void)

- ea: `0x1800065d0`
- end: `0x1800065ee`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800033c8`
- `0x18000789c`
- `0x180008558`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800065d9`

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
0x1800065d0  push    rbx
0x1800065d2  sub     rsp, 20h
0x1800065d6  mov     rbx, rcx
0x1800065d9  call    cs:__imp_GetLastError
0x1800065df  mov     [rbx+4], eax
0x1800065e2  mov     rax, rbx
0x1800065e5  mov     byte ptr [rbx], 0
0x1800065e8  add     rsp, 20h
0x1800065ec  pop     rbx
0x1800065ed  retn
```
