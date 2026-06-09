# CWinTaskHandler::Release(void)

- ea: `0x1800023c0`
- end: `0x1800023ef`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800023c0`
- `0x180004010`

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
0x1800023c0  push    rbx
0x1800023c2  sub     rsp, 20h
0x1800023c6  or      ebx, 0FFFFFFFFh
0x1800023c9  lock xadd [rcx+20h], ebx
0x1800023ce  sub     ebx, 1
0x1800023d1  jnz     short loc_1800023E7
0x1800023d3  test    rcx, rcx
0x1800023d6  jz      short loc_1800023E7
0x1800023d8  mov     rdx, [rcx]
0x1800023db  mov     rax, [rdx+38h]
0x1800023df  lea     edx, [rbx+1]
0x1800023e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023e7  mov     eax, ebx
0x1800023e9  add     rsp, 20h
0x1800023ed  pop     rbx
0x1800023ee  retn
```
