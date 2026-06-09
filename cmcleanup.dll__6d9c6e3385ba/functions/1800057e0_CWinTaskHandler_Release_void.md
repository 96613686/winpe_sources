# CWinTaskHandler::Release(void)

- ea: `0x1800057e0`
- end: `0x18000580f`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x1800057e0`
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
0x1800057e0  push    rbx
0x1800057e2  sub     rsp, 20h
0x1800057e6  or      ebx, 0FFFFFFFFh
0x1800057e9  lock xadd [rcx+20h], ebx
0x1800057ee  sub     ebx, 1
0x1800057f1  jnz     short loc_180005807
0x1800057f3  test    rcx, rcx
0x1800057f6  jz      short loc_180005807
0x1800057f8  mov     rdx, [rcx]
0x1800057fb  mov     rax, [rdx+38h]
0x1800057ff  lea     edx, [rbx+1]
0x180005802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005807  mov     eax, ebx
0x180005809  add     rsp, 20h
0x18000580d  pop     rbx
0x18000580e  retn
```
