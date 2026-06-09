# D3D12CreateDevice

- ea: `0x180008030`
- end: `0x180008069`
- name: `D3D12CreateDevice`
- size: `57`
- prototype: `HRESULT __stdcall(IUnknown *pAdapter, D3D_FEATURE_LEVEL MinimumFeatureLevel, const IID *const riid, void **ppDevice)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008070`
- `0x180015010`

## pseudocode

```c
HRESULT __stdcall D3D12CreateDevice(
        IUnknown *pAdapter,
        D3D_FEATURE_LEVEL MinimumFeatureLevel,
        const IID *const riid,
        void **ppDevice)
{
  __int64 (__fastcall *IsCapture)(IUnknown *, _QWORD, const IID *const, void **); // rax

  IsCapture = (__int64 (__fastcall *)(IUnknown *, _QWORD, const IID *const, void **))DXCapture::IsCaptureEnabled<long (IUnknown *,enum D3D_FEATURE_LEVEL,_GUID const &,void * *)>(D3D12CreateDeviceImpl);
  return IsCapture(pAdapter, (unsigned int)MinimumFeatureLevel, riid, ppDevice);
}

```

## disassembly

```asm
0x180008030  push    rbx
0x180008032  push    rbp
0x180008033  push    rsi
0x180008034  push    rdi
0x180008035  sub     rsp, 38h
0x180008039  mov     rbp, rcx
0x18000803c  mov     rbx, r9
0x18000803f  lea     rcx, ?D3D12CreateDeviceImpl@@YAJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@Z; D3D12CreateDeviceImpl(IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *)
0x180008046  mov     rdi, r8
0x180008049  mov     esi, edx
0x18000804b  call    ??$IsCaptureEnabled@$$A6AJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@Z@DXCapture@@YAP6AJPEAUIUnknown@@W4D3D_FEATURE_LEVEL@@AEBU_GUID@@PEAPEAX@ZP6AJ0123@ZPEBD5@Z; DXCapture::IsCaptureEnabled<long (IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *)>(long (*)(IUnknown *,D3D_FEATURE_LEVEL,_GUID const &,void * *),char const *,char const *)
0x180008050  mov     r9, rbx
0x180008053  mov     r8, rdi
0x180008056  mov     edx, esi
0x180008058  mov     rcx, rbp
0x18000805b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008060  add     rsp, 38h
0x180008064  pop     rdi
0x180008065  pop     rsi
0x180008066  pop     rbp
0x180008067  pop     rbx
0x180008068  retn
```
