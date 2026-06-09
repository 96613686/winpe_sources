# winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)

- ea: `0x180006594`
- end: `0x1800065d1`
- name: `?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ`
- size: `61`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000359c`
- `0x180003740`
- `0x18000d740`
- `0x18000eea0`
- `0x180012444`
- `0x1800128c0`
- `0x180017990`

## callees

- `0x1800021c0`
- `0x180002754`
- `0x180003a84`
- `0x180006594`

## pseudocode

```c
void __fastcall winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(
        unsigned int **a1)
{
  unsigned int *v1; // rbx

  v1 = *a1;
  *a1 = 0;
  if ( !(unsigned int)winrt::impl::atomic_ref_count::operator--(v1) )
  {
    std::_Destroy_range<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> *>(
      v1 + 2,
      &v1[2 * v1[1] + 2]);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180006594  push    rbx
0x180006596  sub     rsp, 20h
0x18000659a  mov     rbx, [rcx]
0x18000659d  mov     qword ptr [rcx], 0
0x1800065a4  mov     rcx, rbx
0x1800065a7  call    ??Fatomic_ref_count@impl@winrt@@QEAAIXZ; winrt::impl::atomic_ref_count::operator--(void)
0x1800065ac  test    eax, eax
0x1800065ae  jnz     short loc_1800065CB
0x1800065b0  mov     eax, [rbx+4]
0x1800065b3  lea     rcx, [rbx+8]
0x1800065b7  inc     rax
0x1800065ba  lea     rdx, [rbx+rax*8]
0x1800065be  call    ??$_Destroy_range@PEAU?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@PEAU1234@@std@@YAXPEAU?$TypedEventHandler@UDirect3D11CaptureFramePool@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@QEAU1234@@Z; std::_Destroy_range<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> *>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IInspectable> * const)
0x1800065c3  mov     rcx, rbx; Block
0x1800065c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800065cb  add     rsp, 20h
0x1800065cf  pop     rbx
0x1800065d0  retn
```
