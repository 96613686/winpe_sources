# CWinTaskHandler::Release(void)

- ea: `0x180004ba0`
- end: `0x180004bcf`
- name: `?Release@CWinTaskHandler@@MEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(CWinTaskHandler *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004ba0`
- `0x18000a010`

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
0x180004ba0  push    rbx
0x180004ba2  sub     rsp, 20h
0x180004ba6  or      ebx, 0FFFFFFFFh
0x180004ba9  lock xadd [rcx+20h], ebx
0x180004bae  sub     ebx, 1
0x180004bb1  jnz     short loc_180004BC7
0x180004bb3  test    rcx, rcx
0x180004bb6  jz      short loc_180004BC7
0x180004bb8  mov     rdx, [rcx]
0x180004bbb  mov     rax, [rdx+38h]
0x180004bbf  lea     edx, [rbx+1]
0x180004bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bc7  mov     eax, ebx
0x180004bc9  add     rsp, 20h
0x180004bcd  pop     rbx
0x180004bce  retn
```
