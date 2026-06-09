# CWinTaskHandler::Release(void)

- ea: `0x180005990`
- end: `0x1800059bf`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180005990`
- `0x180009010`

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
0x180005990  push    rbx
0x180005992  sub     rsp, 20h
0x180005996  or      ebx, 0FFFFFFFFh
0x180005999  lock xadd [rcx+20h], ebx
0x18000599e  sub     ebx, 1
0x1800059a1  jnz     short loc_1800059B7
0x1800059a3  test    rcx, rcx
0x1800059a6  jz      short loc_1800059B7
0x1800059a8  mov     rdx, [rcx]
0x1800059ab  mov     rax, [rdx+38h]
0x1800059af  lea     edx, [rbx+1]
0x1800059b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b7  mov     eax, ebx
0x1800059b9  add     rsp, 20h
0x1800059bd  pop     rbx
0x1800059be  retn
```
