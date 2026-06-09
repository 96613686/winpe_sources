# wistd::unique_ptr<Microsoft::WRL::ComPtr<ID3D11Buffer> [0],wistd::default_delete<Microsoft::WRL::ComPtr<ID3D11Buffer> [0]>>::reset(std::nullptr_t)

- ea: `0x180052320`
- end: `0x18005233d`
- name: `?reset@?$unique_ptr@$$BY0A@V?$ComPtr@UID3D11Buffer@@@WRL@Microsoft@@U?$default_delete@$$BY0A@V?$ComPtr@UID3D11Buffer@@@WRL@Microsoft@@@wistd@@@wistd@@QEAAX$$T@Z`
- size: `29`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004ed70`
- `0x18004ed7c`
- `0x18004ee8c`
- `0x180050550`
- `0x1800519f4`

## callees

- `0x18004e4a4`
- `0x180052320`

## pseudocode

```c
__int64 __fastcall wistd::unique_ptr<Microsoft::WRL::ComPtr<ID3D11Buffer> [0],wistd::default_delete<Microsoft::WRL::ComPtr<ID3D11Buffer> [0]>>::reset(
        __int64 *a1)
{
  __int64 v1; // rdx
  __int64 result; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    return wistd::default_delete<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView> [0]>::operator()<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView>>();
  return result;
}

```

## disassembly

```asm
0x180052320  sub     rsp, 28h
0x180052324  mov     rdx, [rcx]
0x180052327  mov     qword ptr [rcx], 0
0x18005232e  test    rdx, rdx
0x180052331  jz      short loc_180052338
0x180052333  call    ??$?RV?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@@?$default_delete@$$BY0A@V?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@@wistd@@QEBAXPEAV?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@@Z; wistd::default_delete<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView> [0]>::operator()<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView>>(Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView> *)
0x180052338  add     rsp, 28h
0x18005233c  retn
```
