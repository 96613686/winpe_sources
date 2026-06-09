# wil::last_error_context::last_error_context(void)

- ea: `0x14000af00`
- end: `0x14000af1e`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b318`
- `0x14000cadc`
- `0x14000cb84`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000af09`
- `KERNEL32!GetLastError` at `0x14000af09`

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
0x14000af00  push    rbx
0x14000af02  sub     rsp, 20h
0x14000af06  mov     rbx, rcx
0x14000af09  call    cs:__imp_GetLastError
0x14000af0f  mov     [rbx+4], eax
0x14000af12  mov     rax, rbx
0x14000af15  mov     byte ptr [rbx], 0
0x14000af18  add     rsp, 20h
0x14000af1c  pop     rbx
0x14000af1d  retn
```
