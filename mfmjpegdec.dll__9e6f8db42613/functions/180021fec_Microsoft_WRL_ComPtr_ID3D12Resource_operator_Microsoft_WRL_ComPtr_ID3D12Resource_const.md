# Microsoft::WRL::ComPtr<ID3D12Resource>::operator=(Microsoft::WRL::ComPtr<ID3D12Resource> const &)

- ea: `0x180021fec`
- end: `0x180022033`
- name: `??4?$ComPtr@UID3D12Resource@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z`
- size: `71`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180021f6c`
- `0x180055210`
- `0x180055284`
- `0x18005a5bc`
- `0x18005af70`
- `0x18005f7b0`
- `0x18006d338`
- `0x18006d784`

## callees

- `0x180020598`
- `0x180021fec`
- `0x18004a0f8`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::ComPtr<ID3D12Resource>::operator=(__int64 *a1, __int64 *a2)
{
  __int64 v2; // rdi
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a2;
  if ( *a1 != *a2 )
  {
    v5 = *a2;
    Microsoft::WRL::ComPtr<ID3D12Resource>::InternalAddRef(&v5);
    v5 = *a1;
    *a1 = v2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x180021fec  mov     [rsp+arg_8], rbx
0x180021ff1  push    rdi
0x180021ff2  sub     rsp, 20h
0x180021ff6  mov     rdi, [rdx]
0x180021ff9  mov     rbx, rcx
0x180021ffc  cmp     [rcx], rdi
0x180021fff  jz      short loc_180022025
0x180022001  lea     rcx, [rsp+28h+arg_0]
0x180022006  mov     [rsp+28h+arg_0], rdi
0x18002200b  call    ?InternalAddRef@?$ComPtr@UID3D12Resource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ID3D12Resource>::InternalAddRef(void)
0x180022010  mov     rax, [rbx]
0x180022013  lea     rcx, [rsp+28h+arg_0]
0x180022018  mov     [rsp+28h+arg_0], rax
0x18002201d  mov     [rbx], rdi
0x180022020  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022025  mov     rax, rbx
0x180022028  mov     rbx, [rsp+28h+arg_8]
0x18002202d  add     rsp, 20h
0x180022031  pop     rdi
0x180022032  retn
```
