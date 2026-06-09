# winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)

- ea: `0x18001df18`
- end: `0x18001df4a`
- name: `?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UGraphicsCaptureSession@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18001c7e4`
- `0x18001c888`

## callees

- `0x1800021c0`
- `0x180003a84`
- `0x18001c800`
- `0x18001df18`

## pseudocode

```c
void __fastcall winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(
        void **a1)
{
  void *v1; // rbx

  v1 = *a1;
  *a1 = 0;
  if ( !(unsigned int)winrt::impl::atomic_ref_count::operator--(v1) )
  {
    winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Foundation::IInspectable>>::~event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Foundation::IInspectable>>(v1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18001df18  push    rbx
0x18001df1a  sub     rsp, 20h
0x18001df1e  mov     rbx, [rcx]
0x18001df21  mov     qword ptr [rcx], 0
0x18001df28  mov     rcx, rbx
0x18001df2b  call    ??Fatomic_ref_count@impl@winrt@@QEAAIXZ; winrt::impl::atomic_ref_count::operator--(void)
0x18001df30  test    eax, eax
0x18001df32  jnz     short loc_18001DF44
0x18001df34  mov     rcx, rbx
0x18001df37  call    ??1?$event_array@U?$TypedEventHandler@UGraphicsCaptureSession@Capture@Graphics@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@QEAA@XZ; winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Foundation::IInspectable>>::~event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::Graphics::Capture::GraphicsCaptureSession,winrt::Windows::Foundation::IInspectable>>(void)
0x18001df3c  mov     rcx, rbx; Block
0x18001df3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001df44  add     rsp, 20h
0x18001df48  pop     rbx
0x18001df49  retn
```
