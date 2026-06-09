# Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(void)

- ea: `0x18000d7c8`
- end: `0x18000d7e6`
- name: `?InternalAddRef@?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@IEBAXXZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c9e0`
- `0x18000cc3c`
- `0x18000d82c`
- `0x18000da64`
- `0x18000de50`
- `0x18000e450`

## callees

- `0x18000d7c8`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 8LL))(v1);
  return result;
}

```

## disassembly

```asm
0x18000d7c8  sub     rsp, 28h
0x18000d7cc  mov     rcx, [rcx]
0x18000d7cf  test    rcx, rcx
0x18000d7d2  jz      short loc_18000D7E1
0x18000d7d4  mov     rax, [rcx]
0x18000d7d7  mov     rax, [rax+8]
0x18000d7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7e0  nop
0x18000d7e1  add     rsp, 28h
0x18000d7e5  retn
```
