# wil::last_error_context::last_error_context(void)

- ea: `0x180006414`
- end: `0x180006439`
- name: `??0last_error_context@wil@@QEAA@XZ`
- size: `37`
- prototype: `__int64 __fastcall(wil::last_error_context *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004914`
- `0x180008714`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000641d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000641d`

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
0x180006414  push    rbx
0x180006416  sub     rsp, 20h
0x18000641a  mov     rbx, rcx
0x18000641d  call    cs:__imp_GetLastError
0x180006424  nop     dword ptr [rax+rax+00h]
0x180006429  mov     [rbx+4], eax
0x18000642c  mov     rax, rbx
0x18000642f  mov     byte ptr [rbx], 0
0x180006432  add     rsp, 20h
0x180006436  pop     rbx
0x180006437  retn
```
