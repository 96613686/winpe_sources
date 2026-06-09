# winrt::impl::produce<winrt::Windows::Graphics::Capture::factory_implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics2>::CreateFreeThreaded(void *,int,int,winrt::impl::struct_Windows_Graphics_SizeInt32,void * *)

- ea: `0x180004210`
- end: `0x1800042a6`
- name: `?CreateFreeThreaded@?$produce@UDirect3D11CaptureFramePool@factory_implementation@Capture@Graphics@Windows@winrt@@UIDirect3D11CaptureFramePoolStatics2@3456@@impl@winrt@@UEAAHPEAXHHUstruct_Windows_Graphics_SizeInt32@23@PEAPEAX@Z`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002158`
- `0x180002dd0`
- `0x180003580`
- `0x180004210`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::Windows::Graphics::Capture::factory_implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::IDirect3D11CaptureFramePoolStatics2>::CreateFreeThreaded(
        void *a1,
        __int64 a2,
        int a3,
        int a4,
        char a5,
        __int64 *a6)
{
  __int64 *v7; // rbx
  __int64 v8; // rax
  void *v10; // [rsp+60h] [rbp+8h] BYREF
  __int64 v11; // [rsp+68h] [rbp+10h] BYREF
  int v12; // [rsp+70h] [rbp+18h] BYREF

  v12 = a3;
  v11 = a2;
  v10 = a1;
  v7 = a6;
  *a6 = 0;
  v10 = operator new(0x138u);
  v8 = winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>(
         (int)v10,
         (int)&v11,
         (int)&v12,
         a4,
         (struct winrt::Windows::Graphics::SizeInt32 *)&a5,
         0,
         0);
  v10 = 0;
  *v7 = (v8 + 8) & -(__int64)(v8 != 0);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v10);
  return 0;
}

```

## disassembly

```asm
0x180004210  mov     [rsp+arg_10], r8d
0x180004215  mov     [rsp+arg_8], rdx
0x18000421a  mov     [rsp+arg_0], rcx
0x18000421f  push    rbx
0x180004220  push    rdi
0x180004221  sub     rsp, 48h
0x180004225  mov     edi, r9d
0x180004228  mov     rbx, [rsp+58h+arg_28]
0x180004230  mov     qword ptr [rbx], 0
0x180004237  mov     ecx, 138h; Size
0x18000423c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004241  mov     [rsp+58h+arg_0], rax
0x180004246  mov     [rsp+58h+var_28], 0; bool
0x18000424b  mov     [rsp+58h+var_30], 0; bool
0x180004250  lea     rcx, [rsp+58h+arg_20]
0x180004258  mov     [rsp+58h+var_38], rcx; struct winrt::Windows::Graphics::SizeInt32 *
0x18000425d  mov     r9d, edi; int
0x180004260  lea     r8, [rsp+58h+arg_10]; int
0x180004265  lea     rdx, [rsp+58h+arg_8]; int
0x18000426a  mov     rcx, rax; int
0x18000426d  call    ??0?$heap_implements@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@impl@winrt@@QEAA@AEBUIDirect3DDevice@Direct3D11@DirectX@Graphics@Windows@2@AEBW4DirectXPixelFormat@5672@HAEBUSizeInt32@672@_N3@Z; winrt::impl::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::heap_implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>(winrt::Windows::Graphics::DirectX::Direct3D11::IDirect3DDevice const &,winrt::Windows::Graphics::DirectX::DirectXPixelFormat const &,int,winrt::Windows::Graphics::SizeInt32 const &,bool,bool)
0x180004272  nop
0x180004273  mov     [rsp+58h+arg_0], 0
0x18000427c  lea     rcx, [rax+8]
0x180004280  neg     rax
0x180004283  sbb     rax, rax
0x180004286  and     rax, rcx
0x180004289  mov     [rbx], rax
0x18000428c  lea     rcx, [rsp+58h+arg_0]
0x180004291  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180004296  xor     eax, eax
0x180004298  jmp     short loc_18000429E
0x18000429a  mov     eax, [rsp+58h+arg_18]
0x18000429e  add     rsp, 48h
0x1800042a2  pop     rdi
0x1800042a3  pop     rbx
0x1800042a4  retn
```
