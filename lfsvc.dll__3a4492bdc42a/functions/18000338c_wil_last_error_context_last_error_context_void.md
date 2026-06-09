# wil::last_error_context::last_error_context(void)

- ea: `0x18000338c`
- end: `0x1800033aa`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c7c`
- `0x180003098`
- `0x180003140`
- `0x18000321c`
- `0x1800033b0`
- `0x180006854`
- `0x18000a09c`
- `0x18000a0f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003395`

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
0x18000338c  push    rbx
0x18000338e  sub     rsp, 20h
0x180003392  mov     rbx, rcx
0x180003395  call    cs:__imp_GetLastError
0x18000339b  mov     [rbx+4], eax
0x18000339e  mov     rax, rbx
0x1800033a1  mov     byte ptr [rbx], 0
0x1800033a4  add     rsp, 20h
0x1800033a8  pop     rbx
0x1800033a9  retn
```
