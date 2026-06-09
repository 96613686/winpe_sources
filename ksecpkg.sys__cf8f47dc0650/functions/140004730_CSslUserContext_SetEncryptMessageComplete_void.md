# CSslUserContext::SetEncryptMessageComplete(void)

- ea: `0x140004730`
- end: `0x14000474d`
- name: `?SetEncryptMessageComplete@CSslUserContext@@QEAAJXZ`
- size: `29`
- prototype: `__int64 __fastcall(CSslUserContext *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140031100`

## callees

- `0x140010240`

## pseudocode

```c
__int64 __fastcall CSslUserContext::SetEncryptMessageComplete(CSslUserContext *this)
{
  return (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 64) + 32LL))((char *)this + 512);
}

```

## disassembly

```asm
0x140004730  sub     rsp, 28h
0x140004734  add     rcx, 200h
0x14000473b  mov     rax, [rcx]
0x14000473e  mov     rax, [rax+20h]
0x140004742  call    _guard_dispatch_icall
0x140004747  add     rsp, 28h
0x14000474b  retn
```
