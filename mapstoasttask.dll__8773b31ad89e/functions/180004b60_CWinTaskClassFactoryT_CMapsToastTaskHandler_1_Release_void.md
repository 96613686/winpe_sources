# CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::Release(void)

- ea: `0x180004b60`
- end: `0x180004b8f`
- name: `?Release@?$CWinTaskClassFactoryT@VCMapsToastTaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004b60`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMapsToastTaskHandler,1>::Release(volatile signed __int32 *a1)
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
0x180004b60  push    rbx
0x180004b62  sub     rsp, 20h
0x180004b66  or      ebx, 0FFFFFFFFh
0x180004b69  lock xadd [rcx+8], ebx
0x180004b6e  sub     ebx, 1
0x180004b71  jnz     short loc_180004B87
0x180004b73  test    rcx, rcx
0x180004b76  jz      short loc_180004B87
0x180004b78  mov     rdx, [rcx]
0x180004b7b  mov     rax, [rdx+28h]
0x180004b7f  lea     edx, [rbx+1]
0x180004b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b87  mov     eax, ebx
0x180004b89  add     rsp, 20h
0x180004b8d  pop     rbx
0x180004b8e  retn
```
