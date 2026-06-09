# NOutermost::CDeviceChild::LUCLockCachedObjects(void)

- ea: `0x180004b20`
- end: `0x180004b3f`
- name: `?LUCLockCachedObjects@CDeviceChild@NOutermost@@UEAAXXZ`
- size: `31`
- prototype: `void __fastcall(NOutermost::CDeviceChild *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004b20`
- `0x180015010`

## pseudocode

```c
void __fastcall NOutermost::CDeviceChild::LUCLockCachedObjects(NOutermost::CDeviceChild *this)
{
  __int64 v1; // rcx

  v1 = *((_QWORD *)this + 3);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 112LL))(v1);
}

```

## disassembly

```asm
0x180004b20  sub     rsp, 28h
0x180004b24  mov     rcx, [rcx+18h]
0x180004b28  test    rcx, rcx
0x180004b2b  jz      short loc_180004B3A
0x180004b2d  mov     rax, [rcx]
0x180004b30  mov     rax, [rax+70h]
0x180004b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b39  nop
0x180004b3a  add     rsp, 28h
0x180004b3e  retn
```
