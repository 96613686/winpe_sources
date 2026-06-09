# CWinTaskHandler::Release(void)

- ea: `0x1800101b0`
- end: `0x1800101df`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800101b0`
- `0x180023010`

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
0x1800101b0  push    rbx
0x1800101b2  sub     rsp, 20h
0x1800101b6  or      ebx, 0FFFFFFFFh
0x1800101b9  lock xadd [rcx+20h], ebx
0x1800101be  sub     ebx, 1
0x1800101c1  jnz     short loc_1800101D7
0x1800101c3  test    rcx, rcx
0x1800101c6  jz      short loc_1800101D7
0x1800101c8  mov     rdx, [rcx]
0x1800101cb  mov     rax, [rdx+38h]
0x1800101cf  lea     edx, [rbx+1]
0x1800101d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101d7  mov     eax, ebx
0x1800101d9  add     rsp, 20h
0x1800101dd  pop     rbx
0x1800101de  retn
```
