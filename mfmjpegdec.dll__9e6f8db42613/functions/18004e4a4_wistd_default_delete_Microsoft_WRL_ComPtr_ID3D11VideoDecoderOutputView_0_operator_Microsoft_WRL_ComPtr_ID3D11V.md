# wistd::default_delete<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView> [0]>::operator()<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView>>(Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView> *)

- ea: `0x18004e4a4`
- end: `0x18004e4e6`
- name: `??$?RV?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@@?$default_delete@$$BY0A@V?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@@wistd@@QEBAXPEAV?$ComPtr@UID3D11VideoDecoderOutputView@@@WRL@Microsoft@@@Z`
- size: `66`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004ee8c`
- `0x180050550`
- `0x180052320`

## callees

- `0x180024de0`
- `0x18003a558`
- `0x18004e4a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wistd::default_delete<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView> [0]>::operator()<Microsoft::WRL::ComPtr<ID3D11VideoDecoderOutputView>>(
        __int64 a1,
        char *a2)
{
  char *v2; // rbx

  if ( a2 )
  {
    v2 = a2 - 8;
    `eh vector destructor iterator'(
      a2,
      8u,
      *((_QWORD *)a2 - 1),
      (void (*)(void *))Microsoft::WRL::ComPtr<ID3D11VideoDevice2>::~ComPtr<ID3D11VideoDevice2>);
    operator delete[](v2, 8LL * *(_QWORD *)v2 + 8);
  }
}

```

## disassembly

```asm
0x18004e4a4  test    rdx, rdx
0x18004e4a7  jz      short locret_18004E4E5
0x18004e4a9  push    rbx
0x18004e4aa  sub     rsp, 20h
0x18004e4ae  mov     rax, rdx
0x18004e4b1  lea     rbx, [rdx-8]
0x18004e4b5  lea     r9, ??1?$ComPtr@UID3D11VideoDevice2@@@WRL@Microsoft@@QEAA@XZ; void (*)(void *)
0x18004e4bc  mov     r8, [rbx]; unsigned __int64
0x18004e4bf  mov     edx, 8; unsigned __int64
0x18004e4c4  mov     rcx, rax; void *
0x18004e4c7  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18004e4cc  mov     rdx, [rbx]
0x18004e4cf  lea     rdx, ds:8[rdx*8]; unsigned __int64
0x18004e4d7  mov     rcx, rbx; void *
0x18004e4da  call    ??_V@YAXPEAX_K@Z; operator delete[](void *,unsigned __int64)
0x18004e4df  nop
0x18004e4e0  add     rsp, 20h
0x18004e4e4  pop     rbx
0x18004e4e5  retn
```
