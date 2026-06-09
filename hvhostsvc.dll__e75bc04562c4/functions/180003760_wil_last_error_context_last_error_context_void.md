# wil::last_error_context::last_error_context(void)

- ea: `0x180003760`
- end: `0x18000377e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000525c`
- `0x1800060e0`
- `0x180008058`
- `0x18000808c`
- `0x180008afc`
- `0x180008c58`
- `0x180008e1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003769`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003769`

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
0x180003760  push    rbx
0x180003762  sub     rsp, 20h
0x180003766  mov     rbx, rcx
0x180003769  call    cs:__imp_GetLastError
0x18000376f  mov     [rbx+4], eax
0x180003772  mov     rax, rbx
0x180003775  mov     byte ptr [rbx], 0
0x180003778  add     rsp, 20h
0x18000377c  pop     rbx
0x18000377d  retn
```
