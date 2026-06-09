# CWinTaskHandler::Release(void)

- ea: `0x180002560`
- end: `0x18000258f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180002560`
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
0x180002560  push    rbx
0x180002562  sub     rsp, 20h
0x180002566  or      ebx, 0FFFFFFFFh
0x180002569  lock xadd [rcx+20h], ebx
0x18000256e  sub     ebx, 1
0x180002571  jnz     short loc_180002587
0x180002573  test    rcx, rcx
0x180002576  jz      short loc_180002587
0x180002578  mov     rdx, [rcx]
0x18000257b  mov     rax, [rdx+38h]
0x18000257f  lea     edx, [rbx+1]
0x180002582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002587  mov     eax, ebx
0x180002589  add     rsp, 20h
0x18000258d  pop     rbx
0x18000258e  retn
```
