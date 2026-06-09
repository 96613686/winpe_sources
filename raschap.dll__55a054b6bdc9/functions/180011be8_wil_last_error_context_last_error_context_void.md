# wil::last_error_context::last_error_context(void)

- ea: `0x180011be8`
- end: `0x180011c06`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fae4`
- `0x18000fc7c`
- `0x18000fd30`
- `0x1800117f8`
- `0x180011934`
- `0x180011abc`
- `0x180011c0c`
- `0x18001fb50`
- `0x180022f0c`
- `0x180022f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bf1`

## pseudocode

```c
wil::last_error_context *__fastcall wil::last_error_context::last_error_context(wil::last_error_context *this)
{
  DWORD LastError; // eax

  LastError = GetLastError();
  *(_BYTE *)this = 0;
  *((_DWORD *)this + 1) = LastError;
  return this;
}

```

## disassembly

```asm
0x180011be8  push    rbx
0x180011bea  sub     rsp, 20h
0x180011bee  mov     rbx, rcx
0x180011bf1  call    cs:__imp_GetLastError
0x180011bf7  mov     byte ptr [rbx], 0
0x180011bfa  mov     [rbx+4], eax
0x180011bfd  mov     rax, rbx
0x180011c00  add     rsp, 20h
0x180011c04  pop     rbx
0x180011c05  retn
```
