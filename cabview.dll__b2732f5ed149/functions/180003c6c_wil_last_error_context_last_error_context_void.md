# wil::last_error_context::last_error_context(void)

- ea: `0x180003c6c`
- end: `0x180003c8a`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x1800031ac`
- `0x180003228`
- `0x180005484`
- `0x180007694`
- `0x180009eec`
- `0x180009f94`
- `0x180009fe8`
- `0x18000a03c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c75`

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
0x180003c6c  push    rbx
0x180003c6e  sub     rsp, 20h
0x180003c72  mov     rbx, rcx
0x180003c75  call    cs:__imp_GetLastError
0x180003c7b  mov     [rbx+4], eax
0x180003c7e  mov     rax, rbx
0x180003c81  mov     byte ptr [rbx], 0
0x180003c84  add     rsp, 20h
0x180003c88  pop     rbx
0x180003c89  retn
```
