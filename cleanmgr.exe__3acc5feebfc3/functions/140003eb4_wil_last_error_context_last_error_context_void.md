# wil::last_error_context::last_error_context(void)

- ea: `0x140003eb4`
- end: `0x140003ed2`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140006694`
- `0x1400066e8`
- `0x14000747c`
- `0x140008584`
- `0x140008670`
- `0x140008b28`
- `0x14000a7cc`
- `0x14000a874`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ebd`

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
0x140003eb4  push    rbx
0x140003eb6  sub     rsp, 20h
0x140003eba  mov     rbx, rcx
0x140003ebd  call    cs:__imp_GetLastError
0x140003ec3  mov     [rbx+4], eax
0x140003ec6  mov     rax, rbx
0x140003ec9  mov     byte ptr [rbx], 0
0x140003ecc  add     rsp, 20h
0x140003ed0  pop     rbx
0x140003ed1  retn
```
