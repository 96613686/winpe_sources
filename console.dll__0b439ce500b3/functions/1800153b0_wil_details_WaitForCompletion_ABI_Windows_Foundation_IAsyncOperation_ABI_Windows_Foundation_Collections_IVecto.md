# `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate::Invoke(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,ABI::Windows::Foundation::AsyncStatus)

- ea: `0x1800153b0`
- end: `0x1800153c9`
- name: `?Invoke@CompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@UEAAJ0W4AsyncStatus@567@@Z`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800156c8`

## pseudocode

```c
__int64 __fastcall `wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>'::`2'::CompletionDelegate::Invoke(
        __int64 a1,
        void *a2,
        int a3)
{
  *(_DWORD *)(a1 + 48) = a3;
  wil::details::SetEvent(*(wil::details **)(a1 + 56), a2);
  return 0;
}

```

## disassembly

```asm
0x1800153b0  sub     rsp, 28h
0x1800153b4  mov     [rcx+30h], r8d
0x1800153b8  mov     rcx, [rcx+38h]; this
0x1800153bc  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800153c1  xor     eax, eax
0x1800153c3  add     rsp, 28h
0x1800153c7  retn
```
