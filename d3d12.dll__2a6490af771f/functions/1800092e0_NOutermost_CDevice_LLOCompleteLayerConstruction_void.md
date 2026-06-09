# NOutermost::CDevice::LLOCompleteLayerConstruction(void)

- ea: `0x1800092e0`
- end: `0x1800092fa`
- name: `?LLOCompleteLayerConstruction@CDevice@NOutermost@@UEAAJXZ`
- size: `26`
- prototype: `__int64 __fastcall(NOutermost::CDevice *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
__int64 __fastcall NOutermost::CDevice::LLOCompleteLayerConstruction(NOutermost::CDevice *this)
{
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 48LL))(*((_QWORD *)this + 12));
}

```

## disassembly

```asm
0x1800092e0  sub     rsp, 28h
0x1800092e4  mov     rcx, [rcx+60h]
0x1800092e8  mov     rax, [rcx]
0x1800092eb  mov     rax, [rax+30h]
0x1800092ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092f4  nop
0x1800092f5  add     rsp, 28h
0x1800092f9  retn
```
