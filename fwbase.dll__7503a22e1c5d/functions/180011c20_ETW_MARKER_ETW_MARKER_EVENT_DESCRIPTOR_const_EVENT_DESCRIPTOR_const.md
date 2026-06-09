# _ETW_MARKER::_ETW_MARKER(_EVENT_DESCRIPTOR const *,_EVENT_DESCRIPTOR const *)

- ea: `0x180011c20`
- end: `0x180011c5b`
- name: `??0_ETW_MARKER@@QEAA@PEBU_EVENT_DESCRIPTOR@@0@Z`
- size: `59`
- prototype: `_ETW_MARKER *__fastcall(_ETW_MARKER *__hidden this, const struct _EVENT_DESCRIPTOR *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18002c420`
- `0x18002c560`
- `0x18002c6a0`
- `0x18002c840`
- `0x18002c980`
- `0x18002cac0`
- `0x18002cc00`
- `0x18002cd20`

## callees

- `0x180011c20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180011c53`
- `ntdll!EtwEventWrite` at `0x180011c53`

## pseudocode

```c
_ETW_MARKER *__fastcall _ETW_MARKER::_ETW_MARKER(
        _ETW_MARKER *this,
        const struct _EVENT_DESCRIPTOR *a2,
        const struct _EVENT_DESCRIPTOR *a3)
{
  if ( g_Provider )
    EtwEventWrite(g_Provider, a2, 0, 0);
  *(_QWORD *)this = a3;
  return this;
}

```

## disassembly

```asm
0x180011c20  mov     [rsp+arg_0], rbx
0x180011c25  push    rdi
0x180011c26  sub     rsp, 20h
0x180011c2a  mov     rbx, rcx
0x180011c2d  mov     rdi, r8
0x180011c30  mov     rcx, cs:g_Provider
0x180011c37  test    rcx, rcx
0x180011c3a  jnz     short loc_180011C4D
0x180011c3c  mov     [rbx], rdi
0x180011c3f  mov     rax, rbx
0x180011c42  mov     rbx, [rsp+28h+arg_0]
0x180011c47  add     rsp, 20h
0x180011c4b  pop     rdi
0x180011c4c  retn
0x180011c4d  xor     r9d, r9d
0x180011c50  xor     r8d, r8d
0x180011c53  call    cs:__imp_EtwEventWrite
0x180011c59  jmp     short loc_180011C3C
```
