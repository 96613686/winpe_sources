# NOutermost::CDeviceChild::LUCCompleteInitialization(void)

- ea: `0x1800054a0`
- end: `0x1800054ba`
- name: `?LUCCompleteInitialization@CDeviceChild@NOutermost@@UEAAXXZ`
- size: `26`
- prototype: `void __fastcall(NOutermost::CDeviceChild *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015010`

## pseudocode

```c
void __fastcall NOutermost::CDeviceChild::LUCCompleteInitialization(NOutermost::CDeviceChild *this)
{
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 96LL))(*((_QWORD *)this + 3));
}

```

## disassembly

```asm
0x1800054a0  sub     rsp, 28h
0x1800054a4  mov     rcx, [rcx+18h]
0x1800054a8  mov     rax, [rcx]
0x1800054ab  mov     rax, [rax+60h]
0x1800054af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054b4  nop
0x1800054b5  add     rsp, 28h
0x1800054b9  retn
```
