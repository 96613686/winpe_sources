# CWinTaskHandler::Release(void)

- ea: `0x18000bfd0`
- end: `0x18000bfff`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000bfd0`
- `0x18000e010`

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
0x18000bfd0  push    rbx
0x18000bfd2  sub     rsp, 20h
0x18000bfd6  or      ebx, 0FFFFFFFFh
0x18000bfd9  lock xadd [rcx+20h], ebx
0x18000bfde  sub     ebx, 1
0x18000bfe1  jnz     short loc_18000BFF7
0x18000bfe3  test    rcx, rcx
0x18000bfe6  jz      short loc_18000BFF7
0x18000bfe8  mov     rdx, [rcx]
0x18000bfeb  mov     rax, [rdx+38h]
0x18000bfef  lea     edx, [rbx+1]
0x18000bff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bff7  mov     eax, ebx
0x18000bff9  add     rsp, 20h
0x18000bffd  pop     rbx
0x18000bffe  retn
```
