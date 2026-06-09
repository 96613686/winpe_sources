# Microsoft::WRL::ComPtr<ID3D12Resource>::InternalAddRef(void)

- ea: `0x18004a0f8`
- end: `0x18004a116`
- name: `?InternalAddRef@?$ComPtr@UID3D12Resource@@@WRL@Microsoft@@IEBAXXZ`
- size: `30`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021fec`
- `0x18004892c`
- `0x180052ae0`
- `0x1800587e4`
- `0x18005af70`
- `0x18005d000`
- `0x18005f7b0`
- `0x18006b3c8`

## callees

- `0x18004a0f8`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<ID3D12Resource>::InternalAddRef(__int64 *a1)
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
0x18004a0f8  sub     rsp, 28h
0x18004a0fc  mov     rcx, [rcx]
0x18004a0ff  test    rcx, rcx
0x18004a102  jz      short loc_18004A111
0x18004a104  mov     rax, [rcx]
0x18004a107  mov     rax, [rax+8]
0x18004a10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a110  nop
0x18004a111  add     rsp, 28h
0x18004a115  retn
```
