# CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::Release(void)

- ea: `0x1800057c0`
- end: `0x1800057ef`
- name: `?Release@?$CWinTaskClassFactoryT@VCMapsUpdateTaskHandler@@$00@@UEAAKXZ`
- size: `47`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800057c0`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CWinTaskClassFactoryT<CMapsUpdateTaskHandler,1>::Release(volatile signed __int32 *a1)
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
0x1800057c0  push    rbx
0x1800057c2  sub     rsp, 20h
0x1800057c6  or      ebx, 0FFFFFFFFh
0x1800057c9  lock xadd [rcx+8], ebx
0x1800057ce  sub     ebx, 1
0x1800057d1  jnz     short loc_1800057E7
0x1800057d3  test    rcx, rcx
0x1800057d6  jz      short loc_1800057E7
0x1800057d8  mov     rdx, [rcx]
0x1800057db  mov     rax, [rdx+28h]
0x1800057df  lea     edx, [rbx+1]
0x1800057e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057e7  mov     eax, ebx
0x1800057e9  add     rsp, 20h
0x1800057ed  pop     rbx
0x1800057ee  retn
```
