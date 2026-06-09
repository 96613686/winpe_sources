# CONFIG_OBJECT::CleanupStoredContext(void)

- ea: `0x1800045c0`
- end: `0x1800045ec`
- name: `?CleanupStoredContext@CONFIG_OBJECT@@UEAAXXZ`
- size: `44`
- prototype: `void __fastcall(CONFIG_OBJECT *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800045c0`
- `0x180007010`

## pseudocode

```c
void __fastcall CONFIG_OBJECT::CleanupStoredContext(CONFIG_OBJECT *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      (*(void (__fastcall **)(CONFIG_OBJECT *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
  }
}

```

## disassembly

```asm
0x1800045c0  sub     rsp, 28h
0x1800045c4  or      eax, 0FFFFFFFFh
0x1800045c7  lock xadd [rcx+10h], eax
0x1800045cc  cmp     eax, 1
0x1800045cf  jnz     short loc_1800045E7
0x1800045d1  test    rcx, rcx
0x1800045d4  jz      short loc_1800045E7
0x1800045d6  mov     rax, [rcx]
0x1800045d9  mov     edx, 1
0x1800045de  mov     rax, [rax+8]
0x1800045e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045e7  add     rsp, 28h
0x1800045eb  retn
```
