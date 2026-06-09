# CWinTaskHandler::Release(void)

- ea: `0x180003070`
- end: `0x18000309f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `unsigned int __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003070`
- `0x18000b010`

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
0x180003070  push    rbx
0x180003072  sub     rsp, 20h
0x180003076  or      ebx, 0FFFFFFFFh
0x180003079  lock xadd [rcx+20h], ebx
0x18000307e  sub     ebx, 1
0x180003081  jnz     short loc_180003097
0x180003083  test    rcx, rcx
0x180003086  jz      short loc_180003097
0x180003088  mov     rdx, [rcx]
0x18000308b  mov     rax, [rdx+38h]
0x18000308f  lea     edx, [rbx+1]
0x180003092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003097  mov     eax, ebx
0x180003099  add     rsp, 20h
0x18000309d  pop     rbx
0x18000309e  retn
```
