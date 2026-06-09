# D3D12CreateAdditionalDevice(IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *)

- ea: `0x18000e940`
- end: `0x18000e979`
- name: `?D3D12CreateAdditionalDevice@@YAJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@Z`
- size: `57`
- prototype: `__int64 __fastcall(struct IUnknown *, enum D3D_FEATURE_LEVEL, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008070`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall D3D12CreateAdditionalDevice(struct IUnknown *a1, __int64 a2, const struct _GUID *a3, void **a4)
{
  unsigned int v7; // esi
  FARPROC v8; // rax

  v7 = a2;
  v8 = DXCapture::IsCaptureEnabled<long (IUnknown *,enum D3D_FEATURE_LEVEL,_GUID const &,void * *)>(
         (__int64)D3D12CreateAdditionalDeviceImpl,
         a2,
         (__int64)a3);
  return ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, const struct _GUID *, void **))v8)(a1, v7, a3, a4);
}

```

## disassembly

```asm
0x18000e940  push    rbx
0x18000e942  push    rbp
0x18000e943  push    rsi
0x18000e944  push    rdi
0x18000e945  sub     rsp, 38h
0x18000e949  mov     rbp, rcx
0x18000e94c  mov     rbx, r9
0x18000e94f  lea     rcx, ?D3D12CreateAdditionalDeviceImpl@@YAJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@Z; D3D12CreateAdditionalDeviceImpl(IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *)
0x18000e956  mov     rdi, r8
0x18000e959  mov     esi, edx
0x18000e95b  call    ??$IsCaptureEnabled@$$A6AJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@Z@DXCapture@@YAP6AJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@ZP6AJ0123@ZPEBD5@Z; DXCapture::IsCaptureEnabled<long (IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *)>(long (*)(IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *),char const *,char const *)
0x18000e960  mov     r9, rbx
0x18000e963  mov     r8, rdi
0x18000e966  mov     edx, esi
0x18000e968  mov     rcx, rbp
0x18000e96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e970  add     rsp, 38h
0x18000e974  pop     rdi
0x18000e975  pop     rsi
0x18000e976  pop     rbp
0x18000e977  pop     rbx
0x18000e978  retn
```
