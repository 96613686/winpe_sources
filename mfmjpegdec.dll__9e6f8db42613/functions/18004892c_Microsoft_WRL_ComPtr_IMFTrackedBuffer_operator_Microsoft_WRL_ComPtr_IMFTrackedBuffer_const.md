# Microsoft::WRL::ComPtr<IMFTrackedBuffer>::operator=(Microsoft::WRL::ComPtr<IMFTrackedBuffer> const &)

- ea: `0x18004892c`
- end: `0x180048973`
- name: `??4?$ComPtr@UIMFTrackedBuffer@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z`
- size: `71`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800483f8`
- `0x18004e4ec`

## callees

- `0x18004892c`
- `0x18004a0f8`
- `0x18004a11c`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::ComPtr<IMFTrackedBuffer>::operator=(__int64 *a1, __int64 *a2)
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
    Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18004892c  mov     [rsp+arg_8], rbx
0x180048931  push    rdi
0x180048932  sub     rsp, 20h
0x180048936  mov     rdi, [rdx]
0x180048939  mov     rbx, rcx
0x18004893c  cmp     [rcx], rdi
0x18004893f  jz      short loc_180048965
0x180048941  lea     rcx, [rsp+28h+arg_0]
0x180048946  mov     [rsp+28h+arg_0], rdi
0x18004894b  call    ?InternalAddRef@?$ComPtr@UID3D12Resource@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ID3D12Resource>::InternalAddRef(void)
0x180048950  mov     rax, [rbx]
0x180048953  lea     rcx, [rsp+28h+arg_0]
0x180048958  mov     [rsp+28h+arg_0], rax
0x18004895d  mov     [rbx], rdi
0x180048960  call    ?InternalRelease@?$ComPtr@UIDXGIAdapter4@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDXGIAdapter4>::InternalRelease(void)
0x180048965  mov     rax, rbx
0x180048968  mov     rbx, [rsp+28h+arg_8]
0x18004896d  add     rsp, 20h
0x180048971  pop     rdi
0x180048972  retn
```
