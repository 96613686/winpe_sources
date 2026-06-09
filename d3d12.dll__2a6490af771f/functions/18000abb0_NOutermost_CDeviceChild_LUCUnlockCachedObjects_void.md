# NOutermost::CDeviceChild::LUCUnlockCachedObjects(void)

- ea: `0x18000abb0`
- end: `0x18000abcf`
- name: `?LUCUnlockCachedObjects@CDeviceChild@NOutermost@@UEAAXXZ`
- size: `31`
- prototype: `void __fastcall(NOutermost::CDeviceChild *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000abb0`
- `0x180015010`

## pseudocode

```c
void __fastcall NOutermost::CDeviceChild::LUCUnlockCachedObjects(NOutermost::CDeviceChild *this)
{
  __int64 v1; // rcx

  v1 = *((_QWORD *)this + 3);
  if ( v1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 120LL))(v1);
}

```

## disassembly

```asm
0x18000abb0  sub     rsp, 28h
0x18000abb4  mov     rcx, [rcx+18h]
0x18000abb8  test    rcx, rcx
0x18000abbb  jz      short loc_18000ABCA
0x18000abbd  mov     rax, [rcx]
0x18000abc0  mov     rax, [rax+78h]
0x18000abc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abc9  nop
0x18000abca  add     rsp, 28h
0x18000abce  retn
```
