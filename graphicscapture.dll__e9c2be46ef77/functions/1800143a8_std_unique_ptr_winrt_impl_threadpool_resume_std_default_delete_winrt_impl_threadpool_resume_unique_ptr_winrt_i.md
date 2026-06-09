# std::unique_ptr<winrt::impl::threadpool_resume,std::default_delete<winrt::impl::threadpool_resume>>::~unique_ptr<winrt::impl::threadpool_resume,std::default_delete<winrt::impl::threadpool_resume>>(void)

- ea: `0x1800143a8`
- end: `0x1800143d7`
- name: `??1?$unique_ptr@Uthreadpool_resume@impl@winrt@@U?$default_delete@Uthreadpool_resume@impl@winrt@@@std@@@std@@QEAA@XZ`
- size: `47`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015730`
- `0x180015c30`
- `0x1800267aa`

## callees

- `0x18000214c`
- `0x1800065f0`
- `0x1800143a8`

## pseudocode

```c
void __fastcall std::unique_ptr<winrt::impl::threadpool_resume>::~unique_ptr<winrt::impl::threadpool_resume>(
        __int64 **a1)
{
  __int64 *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    if ( *v1 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800143a8  push    rbx
0x1800143aa  sub     rsp, 20h
0x1800143ae  mov     rbx, [rcx]
0x1800143b1  test    rbx, rbx
0x1800143b4  jz      short loc_1800143D1
0x1800143b6  cmp     qword ptr [rbx], 0
0x1800143ba  jz      short loc_1800143C4
0x1800143bc  mov     rcx, rbx
0x1800143bf  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x1800143c4  mov     edx, 18h; unsigned __int64
0x1800143c9  mov     rcx, rbx; void *
0x1800143cc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800143d1  add     rsp, 20h
0x1800143d5  pop     rbx
0x1800143d6  retn
```
