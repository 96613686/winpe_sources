# winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)

- ea: `0x180006610`
- end: `0x180006633`
- name: `?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ`
- size: `35`
- prototype: ``
- caller_count: `39`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002794`
- `0x1800035b8`
- `0x180003740`
- `0x18000d7f4`
- `0x18000e3f0`
- `0x18000ece0`
- `0x18000ed18`
- `0x18000eee4`
- `0x18000f254`
- `0x18000f51c`
- `0x18000f670`
- `0x18000fa88`
- `0x18000fb98`
- `0x18000fcb8`
- `0x180011128`
- `0x180011dec`
- `0x180014e50`
- `0x1800175a8`
- `0x180017954`
- `0x180017990`
- `0x180017c44`
- `0x180018340`
- `0x180018540`
- `0x180018790`
- `0x1800189e0`
- `0x180018c30`
- `0x180018d8c`
- `0x180019d50`
- `0x18001cc30`
- `0x18001efbc`
- `0x18001f3f8`
- `0x18001f8b8`
- `0x18001f968`
- `0x18002271c`
- `0x180023870`
- `0x180024298`
- `0x180024940`
- `0x180024c34`
- `0x180024e74`

## callees

- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(__int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x180006610  sub     rsp, 28h
0x180006614  mov     rdx, [rcx]
0x180006617  mov     qword ptr [rcx], 0
0x18000661e  mov     rax, [rdx]
0x180006621  mov     rcx, rdx
0x180006624  mov     rax, [rax+10h]
0x180006628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000662d  nop
0x18000662e  add     rsp, 28h
0x180006632  retn
```
