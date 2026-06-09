# BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,1>::CreateBias(IRpcOptions *,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *> *)

- ea: `0x1800827b0`
- end: `0x180082835`
- name: `?CreateBias@?$BiasHelper@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@$00@@SA?AV?$AutoStubBias@U?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@23@@@PEAUIRpcOptions@@PEAU?$IAsyncOperation@PEAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAUIRandomAccessStream@Streams@Storage@Windows@@@56@@Z`
- size: `133`
- prototype: `__int64 __fastcall(LPSTREAM *ppstm)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180058010`

## callees

- `0x18000892c`
- `0x1800827b0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800827e7`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800827e7`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180082815`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x180082815`

## pseudocode

```c
LPSTREAM *__fastcall BiasHelper<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,1>::CreateBias(
        LPSTREAM *ppstm,
        __int64 a2,
        IUnknown *a3,
        __int64 a4)
{
  HRESULT StreamOnHGlobal; // eax

  *ppstm = 0;
  *((_DWORD *)ppstm + 2) = 0;
  if ( a2 && a4 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(ppstm);
    StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, ppstm);
    *((_DWORD *)ppstm + 2) = StreamOnHGlobal;
    if ( StreamOnHGlobal >= 0 )
      *((_DWORD *)ppstm + 2) = CoMarshalInterface(*ppstm, &GUID_00000000_0000_0000_c000_000000000046, a3, 0, 0, 1u);
  }
  else
  {
    *((_DWORD *)ppstm + 2) = -2147467262;
  }
  return ppstm;
}

```

## disassembly

```asm
0x1800827b0  mov     [rsp+arg_0], rbx
0x1800827b5  push    rdi
0x1800827b6  sub     rsp, 30h
0x1800827ba  mov     qword ptr [rcx], 0
0x1800827c1  mov     rdi, r8
0x1800827c4  mov     dword ptr [rcx+8], 0
0x1800827cb  mov     rbx, rcx
0x1800827ce  test    rdx, rdx
0x1800827d1  jz      short loc_180082820
0x1800827d3  test    r9, r9
0x1800827d6  jz      short loc_180082820
0x1800827d8  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x1800827dd  mov     r8, rbx; ppstm
0x1800827e0  mov     edx, 1; fDeleteOnRelease
0x1800827e5  xor     ecx, ecx; hGlobal
0x1800827e7  call    cs:__imp_CreateStreamOnHGlobal
0x1800827ed  mov     [rbx+8], eax
0x1800827f0  test    eax, eax
0x1800827f2  js      short loc_180082827
0x1800827f4  mov     rcx, [rbx]; pStm
0x1800827f7  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800827fe  mov     [rsp+38h+mshlflags], 1; mshlflags
0x180082806  xor     r9d, r9d; dwDestContext
0x180082809  mov     r8, rdi; pUnk
0x18008280c  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x180082815  call    cs:__imp_CoMarshalInterface
0x18008281b  mov     [rbx+8], eax
0x18008281e  jmp     short loc_180082827
0x180082820  mov     dword ptr [rcx+8], 80004002h
0x180082827  mov     rax, rbx
0x18008282a  mov     rbx, [rsp+38h+arg_0]
0x18008282f  add     rsp, 30h
0x180082833  pop     rdi
0x180082834  retn
```
