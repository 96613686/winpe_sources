# CWinTaskClassFactoryT<CRegIdleHandler,1>::Release(void)

- ea: `0x180001fa0`
- end: `0x180001fcf`
- name: `?Release@?$CWinTaskClassFactoryT@VCRegIdleHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180001fa0`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CRegIdleHandler,1>::Release(volatile signed __int32 *a1)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement(a1 + 2);
  if ( !v1 && a1 )
    (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
  return v1;
}

```

## disassembly

```asm
0x180001fa0  push    rbx
0x180001fa2  sub     rsp, 20h
0x180001fa6  or      ebx, 0FFFFFFFFh
0x180001fa9  lock xadd [rcx+8], ebx
0x180001fae  sub     ebx, 1
0x180001fb1  jnz     short loc_180001FC7
0x180001fb3  test    rcx, rcx
0x180001fb6  jz      short loc_180001FC7
0x180001fb8  mov     rdx, [rcx]
0x180001fbb  mov     rax, [rdx+28h]
0x180001fbf  lea     edx, [rbx+1]
0x180001fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001fc7  mov     eax, ebx
0x180001fc9  add     rsp, 20h
0x180001fcd  pop     rbx
0x180001fce  retn
```
