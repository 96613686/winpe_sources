# WEBSOCKET_CONFIG::CleanupStoredContext(void)

- ea: `0x180002e10`
- end: `0x180002e3c`
- name: `?CleanupStoredContext@WEBSOCKET_CONFIG@@UEAAXXZ`
- size: `44`
- prototype: `void __fastcall(WEBSOCKET_CONFIG *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002e10`
- `0x180009010`

## pseudocode

```c
void __fastcall WEBSOCKET_CONFIG::CleanupStoredContext(WEBSOCKET_CONFIG *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      (*(void (__fastcall **)(WEBSOCKET_CONFIG *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
  }
}

```

## disassembly

```asm
0x180002e10  sub     rsp, 28h
0x180002e14  or      eax, 0FFFFFFFFh
0x180002e17  lock xadd [rcx+8], eax
0x180002e1c  cmp     eax, 1
0x180002e1f  jnz     short loc_180002E37
0x180002e21  test    rcx, rcx
0x180002e24  jz      short loc_180002E37
0x180002e26  mov     rax, [rcx]
0x180002e29  mov     edx, 1
0x180002e2e  mov     rax, [rax+8]
0x180002e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e37  add     rsp, 28h
0x180002e3b  retn
```
