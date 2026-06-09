# TOKEN_ENTRY::DereferenceCacheData(void)

- ea: `0x180010ca0`
- end: `0x180010ccc`
- name: `?DereferenceCacheData@TOKEN_ENTRY@@UEAAXXZ`
- size: `44`
- prototype: `void __fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180010ca0`
- `0x180013010`

## pseudocode

```c
void __fastcall TOKEN_ENTRY::DereferenceCacheData(TOKEN_ENTRY *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 3, 0xFFFFFFFF) == 1 )
  {
    if ( this )
      (*(void (__fastcall **)(TOKEN_ENTRY *, __int64))(*(_QWORD *)this + 80LL))(this, 1);
  }
}

```

## disassembly

```asm
0x180010ca0  sub     rsp, 28h
0x180010ca4  or      eax, 0FFFFFFFFh
0x180010ca7  lock xadd [rcx+0Ch], eax
0x180010cac  cmp     eax, 1
0x180010caf  jnz     short loc_180010CC7
0x180010cb1  test    rcx, rcx
0x180010cb4  jz      short loc_180010CC7
0x180010cb6  mov     rax, [rcx]
0x180010cb9  mov     edx, 1
0x180010cbe  mov     rax, [rax+50h]
0x180010cc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cc7  add     rsp, 28h
0x180010ccb  retn
```
