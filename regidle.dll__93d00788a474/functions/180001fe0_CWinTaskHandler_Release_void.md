# CWinTaskHandler::Release(void)

- ea: `0x180001fe0`
- end: `0x18000200f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001fe0`
- `0x180003010`

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
0x180001fe0  push    rbx
0x180001fe2  sub     rsp, 20h
0x180001fe6  or      ebx, 0FFFFFFFFh
0x180001fe9  lock xadd [rcx+20h], ebx
0x180001fee  sub     ebx, 1
0x180001ff1  jnz     short loc_180002007
0x180001ff3  test    rcx, rcx
0x180001ff6  jz      short loc_180002007
0x180001ff8  mov     rdx, [rcx]
0x180001ffb  mov     rax, [rdx+38h]
0x180001fff  lea     edx, [rbx+1]
0x180002002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002007  mov     eax, ebx
0x180002009  add     rsp, 20h
0x18000200d  pop     rbx
0x18000200e  retn
```
