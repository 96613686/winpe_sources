# CWinTaskHandler::Release(void)

- ea: `0x180010c30`
- end: `0x180010c60`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `48`
- prototype: `unsigned int __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180010c30`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::Release(CWinTaskHandler *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 8);
  if ( !v1 && this )
    (*(void (__fastcall **)(CWinTaskHandler *, __int64))(*(_QWORD *)this + 56LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x180010c30  push    rbx
0x180010c32  sub     rsp, 20h
0x180010c36  or      ebx, 0FFFFFFFFh
0x180010c39  lock xadd [rcx+20h], ebx
0x180010c3e  sub     ebx, 1
0x180010c41  jnz     short loc_180010C57
0x180010c43  test    rcx, rcx
0x180010c46  jz      short loc_180010C57
0x180010c48  mov     rdx, [rcx]
0x180010c4b  mov     rax, [rdx+38h]
0x180010c4f  lea     edx, [rbx+1]
0x180010c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c57  mov     eax, ebx
0x180010c59  add     rsp, 20h
0x180010c5d  pop     rbx
0x180010c5e  retn
```
