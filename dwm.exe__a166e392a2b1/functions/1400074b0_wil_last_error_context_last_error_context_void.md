# wil::last_error_context::last_error_context(void)

- ea: `0x1400074b0`
- end: `0x1400074ce`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140004330`
- `0x140006b6c`
- `0x140006be8`
- `0x140007ff8`
- `0x14000baec`
- `0x14000bb94`
- `0x14000bbe8`
- `0x14000d124`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400074b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400074b9`

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
0x1400074b0  push    rbx
0x1400074b2  sub     rsp, 20h
0x1400074b6  mov     rbx, rcx
0x1400074b9  call    cs:__imp_GetLastError
0x1400074bf  mov     [rbx+4], eax
0x1400074c2  mov     rax, rbx
0x1400074c5  mov     byte ptr [rbx], 0
0x1400074c8  add     rsp, 20h
0x1400074cc  pop     rbx
0x1400074cd  retn
```
