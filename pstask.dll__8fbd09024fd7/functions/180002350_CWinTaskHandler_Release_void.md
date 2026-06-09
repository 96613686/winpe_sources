# CWinTaskHandler::Release(void)

- ea: `0x180002350`
- end: `0x18000237f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002350`
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
0x180002350  push    rbx
0x180002352  sub     rsp, 20h
0x180002356  or      ebx, 0FFFFFFFFh
0x180002359  lock xadd [rcx+20h], ebx
0x18000235e  sub     ebx, 1
0x180002361  jnz     short loc_180002377
0x180002363  test    rcx, rcx
0x180002366  jz      short loc_180002377
0x180002368  mov     rdx, [rcx]
0x18000236b  mov     rax, [rdx+38h]
0x18000236f  lea     edx, [rbx+1]
0x180002372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002377  mov     eax, ebx
0x180002379  add     rsp, 20h
0x18000237d  pop     rbx
0x18000237e  retn
```
