# wil::last_error_context::last_error_context(void)

- ea: `0x18000df30`
- end: `0x18000df4e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x18000dc48`
- `0x18000dcf0`
- `0x18000dde4`
- `0x18000e07c`
- `0x180011024`
- `0x180012fe0`
- `0x1800152e0`
- `0x180015334`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df39`

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
0x18000df30  push    rbx
0x18000df32  sub     rsp, 20h
0x18000df36  mov     rbx, rcx
0x18000df39  call    cs:__imp_GetLastError
0x18000df3f  mov     [rbx+4], eax
0x18000df42  mov     rax, rbx
0x18000df45  mov     byte ptr [rbx], 0
0x18000df48  add     rsp, 20h
0x18000df4c  pop     rbx
0x18000df4d  retn
```
