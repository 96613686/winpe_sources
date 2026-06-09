# `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::`scalar deleting destructor'(uint)

- ea: `0x1800152b0`
- end: `0x1800152e5`
- name: `??_GCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001980`
- `0x18001517c`
- `0x1800152b0`

## pseudocode

```c
void *__fastcall `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>'::`2'::CompletionDelegate::`scalar deleting destructor'(
        void *a1,
        char a2)
{
  `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>'::`2'::CompletionDelegate::~CompletionDelegate((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800152b0  mov     [rsp+arg_0], rbx
0x1800152b5  push    rdi
0x1800152b6  sub     rsp, 20h
0x1800152ba  mov     ebx, edx
0x1800152bc  mov     rdi, rcx
0x1800152bf  call    ??1CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAA@XZ; `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::~CompletionDelegate(void)
0x1800152c4  test    bl, 1
0x1800152c7  jz      short loc_1800152D6
0x1800152c9  mov     edx, 40h ; '@'; unsigned __int64
0x1800152ce  mov     rcx, rdi; void *
0x1800152d1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800152d6  mov     rbx, [rsp+28h+arg_0]
0x1800152db  mov     rax, rdi
0x1800152de  add     rsp, 20h
0x1800152e2  pop     rdi
0x1800152e3  retn
```
