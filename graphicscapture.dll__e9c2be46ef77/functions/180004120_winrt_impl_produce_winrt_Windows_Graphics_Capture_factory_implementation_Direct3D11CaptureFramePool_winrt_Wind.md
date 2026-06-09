# winrt::impl::produce<winrt::Windows::Graphics::Capture::factory_implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics>::Create(void *,int,int,winrt::impl::struct_Windows_Graphics_SizeInt32,void * *)

- ea: `0x180004120`
- end: `0x1800041b6`
- name: `?Create@?$produce@UDirect3D11CaptureFramePool@factory_implementation@Capture@Graphics@Windows@winrt@@UIDirect3D11CaptureFramePoolStatics@3456@@impl@winrt@@UEAAHPEAXHHUstruct_Windows_Graphics_SizeInt32@23@PEAPEAX@Z`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002158`
- `0x180002dd0`
- `0x180003580`
- `0x180004120`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::produce<winrt::Windows::Graphics::Capture::factory_implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics>::Create(
        void *a1,
        __int64 a2,
        int a3,
        int a4,
        char a5,
        __int64 *a6)
{
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 result; // rax
  void *v10; // [rsp+60h] [rbp+8h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  int v12; // [rsp+70h] [rbp+18h] BYREF
  int v13; // [rsp+78h] [rbp+20h] BYREF

  v12 = a3;
  v11 = a2;
  v10 = a1;
  v7 = a6;
  *a6 = 0;
  try
  {
    v10 = operator new(0x138u);
    v8 = winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>(
           (int)v10,
           (int)&v11,
           (int)&v12,
           a4,
           (struct winrt::Windows::Graphics::SizeInt32 *)&a5,
           1,
           0);
    v10 = 0;
    *v7 = (v8 + 8) & -(__int64)(v8 != 0);
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v10);
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v13);
  }
  return result;
}

```

## disassembly

```asm
0x180004120  mov     [rsp+arg_10], r8d
0x180004125  mov     [rsp+arg_8], rdx
0x18000412a  mov     [rsp+arg_0], rcx
0x18000412f  push    rbx
0x180004130  push    rdi
0x180004131  sub     rsp, 48h
0x180004135  mov     edi, r9d
0x180004138  mov     rbx, [rsp+58h+arg_28]
0x180004140  mov     qword ptr [rbx], 0
0x180004147  mov     ecx, 138h; Size
0x18000414c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004151  mov     [rsp+58h+arg_0], rax
0x180004156  mov     [rsp+58h+var_28], 0; bool
0x18000415b  mov     [rsp+58h+var_30], 1; bool
0x180004160  lea     rcx, [rsp+58h+arg_20]
0x180004168  mov     [rsp+58h+var_38], rcx; struct winrt::Windows::Graphics::SizeInt32 *
0x18000416d  mov     r9d, edi; int
0x180004170  lea     r8, [rsp+58h+arg_10]; int
0x180004175  lea     rdx, [rsp+58h+arg_8]; int
0x18000417a  mov     rcx, rax; int
0x18000417d  call    ??0?$heap_implements@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@QEAA@AEBUIDirect3DDevice@Direct3D11@DirectX@Graphics@Windows@2@AEBW4DirectXPixelFormat@5672@HAEBUSizeInt32@672@_N3@Z; winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>(winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice const &,winrt::Windows::Graphics::DirectX::DirectXPixelFormat const &,int,winrt::Windows::Graphics::SizeInt32 const &,bool,bool)
0x180004182  nop
0x180004183  mov     [rsp+58h+arg_0], 0
0x18000418c  lea     rcx, [rax+8]
0x180004190  neg     rax
0x180004193  sbb     rax, rax
0x180004196  and     rax, rcx
0x180004199  mov     [rbx], rax
0x18000419c  lea     rcx, [rsp+58h+arg_0]
0x1800041a1  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800041a6  xor     eax, eax
0x1800041a8  jmp     short loc_1800041AE
0x1800041aa  mov     eax, [rsp+58h+arg_18]
0x1800041ae  add     rsp, 48h
0x1800041b2  pop     rdi
0x1800041b3  pop     rbx
0x1800041b4  retn
```
