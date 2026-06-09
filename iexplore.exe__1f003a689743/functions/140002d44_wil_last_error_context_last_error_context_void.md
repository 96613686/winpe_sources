# wil::last_error_context::last_error_context(void)

- ea: `0x140002d44`
- end: `0x140002d62`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000486c`
- `0x1400053e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140002d4d`
- `KERNEL32!GetLastError` at `0x140002d4d`

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
0x140002d44  push    rbx
0x140002d46  sub     rsp, 20h
0x140002d4a  mov     rbx, rcx
0x140002d4d  call    cs:__imp_GetLastError
0x140002d53  mov     [rbx+4], eax
0x140002d56  mov     rax, rbx
0x140002d59  mov     byte ptr [rbx], 0
0x140002d5c  add     rsp, 20h
0x140002d60  pop     rbx
0x140002d61  retn
```
