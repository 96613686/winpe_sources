# CCmstpLua::Release(void)

- ea: `0x1800021b0`
- end: `0x1800021df`
- name: `?Release@CCmstpLua@@UEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CCmstpLua *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800021b0`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CCmstpLua::Release(CCmstpLua *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
    (*(void (__fastcall **)(CCmstpLua *, __int64))(*(_QWORD *)this + 48LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x1800021b0  push    rbx
0x1800021b2  sub     rsp, 20h
0x1800021b6  or      ebx, 0FFFFFFFFh
0x1800021b9  lock xadd [rcx+8], ebx
0x1800021be  sub     ebx, 1
0x1800021c1  jnz     short loc_1800021D7
0x1800021c3  test    rcx, rcx
0x1800021c6  jz      short loc_1800021D7
0x1800021c8  mov     rdx, [rcx]
0x1800021cb  mov     rax, [rdx+30h]
0x1800021cf  lea     edx, [rbx+1]
0x1800021d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021d7  mov     eax, ebx
0x1800021d9  add     rsp, 20h
0x1800021dd  pop     rbx
0x1800021de  retn
```
