# CWinTaskHandler::Release(void)

- ea: `0x180001c70`
- end: `0x180001ca0`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `48`
- prototype: `unsigned int __fastcall(CWinTaskHandler *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001c70`
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
0x180001c70  push    rbx
0x180001c72  sub     rsp, 20h
0x180001c76  or      ebx, 0FFFFFFFFh
0x180001c79  lock xadd [rcx+20h], ebx
0x180001c7e  sub     ebx, 1
0x180001c81  jnz     short loc_180001C97
0x180001c83  test    rcx, rcx
0x180001c86  jz      short loc_180001C97
0x180001c88  mov     rdx, [rcx]
0x180001c8b  mov     rax, [rdx+38h]
0x180001c8f  lea     edx, [rbx+1]
0x180001c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c97  mov     eax, ebx
0x180001c99  add     rsp, 20h
0x180001c9d  pop     rbx
0x180001c9e  retn
```
