# wil::last_error_context::last_error_context(void)

- ea: `0x180003640`
- end: `0x18000365e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `wil::last_error_context *__fastcall(wil::last_error_context *this)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180003354`
- `0x1800033fc`
- `0x1800034f4`
- `0x18000378c`
- `0x180006164`
- `0x180009e80`
- `0x180009ed4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003649`

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
0x180003640  push    rbx
0x180003642  sub     rsp, 20h
0x180003646  mov     rbx, rcx
0x180003649  call    cs:__imp_GetLastError
0x18000364f  mov     [rbx+4], eax
0x180003652  mov     rax, rbx
0x180003655  mov     byte ptr [rbx], 0
0x180003658  add     rsp, 20h
0x18000365c  pop     rbx
0x18000365d  retn
```
