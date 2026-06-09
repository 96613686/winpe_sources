# CDLNAContentDirectory::GetSearchCapabilities(ushort * *)

- ea: `0x180026da0`
- end: `0x180026f7a`
- name: `?GetSearchCapabilities@CDLNAContentDirectory@@UEAAJPEAPEAG@Z`
- size: `474`
- prototype: `__int64 __fastcall(CDLNAContentDirectory *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x18000f1f4`
- `0x180011954`
- `0x1800260e0`
- `0x180026350`
- `0x180026da0`
- `0x1800281a0`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180026ed2`
- `OLEAUT32!__imp_SysAllocString` at `0x180026ed2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026ec9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180026ec9`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CDLNAContentDirectory::GetSearchCapabilities(CDLNAContentDirectory *this, unsigned __int16 **a2)
{
  int v4; // r14d
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 v9; // rdi
  void *v10; // rax
  const OLECHAR *StringRawBuffer; // rax
  unsigned __int16 *v12; // rax
  int (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  int (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v16; // [rsp+20h] [rbp-20h] BYREF
  __int64 v17; // [rsp+28h] [rbp-18h] BYREF
  __int64 v18; // [rsp+30h] [rbp-10h] BYREF
  HSTRING string; // [rsp+70h] [rbp+30h] BYREF
  int (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp+38h] BYREF

  v4 = CDLNAContentDirectory::_EnsureServer(this);
  if ( v4 >= 0 )
  {
    v17 = 0;
    v5 = *((_QWORD *)this + 3);
    v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v17);
    v4 = v6(v5, &v17);
    if ( v4 >= 0 )
    {
      v20 = 0;
      v7 = v17;
      v8 = *(__int64 (__fastcall **)(__int64, int (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v17 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v20);
      v4 = v8(v7, &v20);
      LODWORD(string) = v4;
      if ( v4 >= 0 )
      {
        v9 = 0;
        v10 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
        v18 = (__int64)v10;
        if ( v10 )
        {
          v9 = CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>(
                 (__int64)v10,
                 (signed int *)&string);
          v18 = 0;
          v4 = (int)string;
        }
        Microsoft::WRL::Details::MakeAllocator<CThumbnailRequest>::~MakeAllocator<CThumbnailRequest>(&v18);
        v18 = v9;
        if ( !v9 )
          v4 = -2147024882;
        if ( v4 >= 0 )
        {
          v4 = CallSync<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>(
                 v20,
                 v9);
          if ( v4 >= 0 )
          {
            string = 0;
            v4 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))(*v20)[8])(
                   v20,
                   &string);
            if ( v4 >= 0 )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              v12 = SysAllocString(StringRawBuffer);
              *a2 = v12;
              if ( !v12 )
                v4 = -2147024882;
            }
            Windows::Internal::String::~String(&string);
          }
        }
        v16 = 0;
        v13 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v20;
        v14 = **v20;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v16);
        if ( v14(v13, &GUID_00000036_0000_0000_c000_000000000046, &v16) >= 0 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 80LL))(v16);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v16);
        if ( v9 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((__int64 *)&v20);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v17);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180026da0  mov     [rsp-18h+arg_0], rbx
0x180026da5  mov     [rsp-18h+arg_8], rsi
0x180026daa  push    rbp
0x180026dab  push    rdi
0x180026dac  push    r14
0x180026dae  mov     rbp, rsp
0x180026db1  sub     rsp, 40h
0x180026db5  mov     rsi, rdx
0x180026db8  mov     rdi, rcx
0x180026dbb  call    ?_EnsureServer@CDLNAContentDirectory@@IEAAJXZ; CDLNAContentDirectory::_EnsureServer(void)
0x180026dc0  mov     r14d, eax
0x180026dc3  test    eax, eax
0x180026dc5  js      loc_180026F64
0x180026dcb  mov     [rbp+var_18], 0
0x180026dd3  mov     rdi, [rdi+18h]
0x180026dd7  mov     rax, [rdi]
0x180026dda  mov     rbx, [rax+38h]
0x180026dde  lea     rcx, [rbp+var_18]
0x180026de2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180026de7  lea     rdx, [rbp+var_18]
0x180026deb  mov     rcx, rdi
0x180026dee  mov     rax, rbx
0x180026df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026df6  mov     r14d, eax
0x180026df9  test    eax, eax
0x180026dfb  js      loc_180026F5B
0x180026e01  mov     [rbp+arg_18], 0
0x180026e09  mov     rdi, [rbp+var_18]
0x180026e0d  mov     rax, [rdi]
0x180026e10  mov     rbx, [rax+30h]
0x180026e14  lea     rcx, [rbp+arg_18]
0x180026e18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180026e1d  lea     rdx, [rbp+arg_18]
0x180026e21  mov     rcx, rdi
0x180026e24  mov     rax, rbx
0x180026e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e2c  mov     r14d, eax
0x180026e2f  mov     dword ptr [rbp+string], eax
0x180026e32  test    eax, eax
0x180026e34  js      loc_180026F51
0x180026e3a  xor     edi, edi
0x180026e3c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026e43  lea     ecx, [rdi+38h]; unsigned __int64
0x180026e46  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026e4b  mov     [rbp+var_10], rax
0x180026e4f  test    rax, rax
0x180026e52  jz      short loc_180026E6F
0x180026e54  lea     rdx, [rbp+string]
0x180026e58  mov     rcx, rax
0x180026e5b  call    ??0?$CDelegateBase@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@@@QEAA@PEAJ@Z; CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>::CDelegateBase<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>(long *)
0x180026e60  mov     rdi, rax
0x180026e63  mov     [rbp+var_10], 0
0x180026e6b  mov     r14d, dword ptr [rbp+string]
0x180026e6f  lea     rcx, [rbp+var_10]
0x180026e73  call    ??1?$MakeAllocator@VCThumbnailRequest@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CThumbnailRequest>::~MakeAllocator<CThumbnailRequest>(void)
0x180026e78  mov     [rbp+var_10], rdi
0x180026e7c  mov     ebx, 8007000Eh
0x180026e81  test    rdi, rdi
0x180026e84  cmovz   r14d, ebx
0x180026e88  test    r14d, r14d
0x180026e8b  js      short loc_180026EEB
0x180026e8d  mov     rdx, rdi
0x180026e90  mov     rcx, [rbp+arg_18]
0x180026e94  call    ??$CallSync@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@PEAU?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@12@K@Z; CallSync<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *> *,ulong)
0x180026e99  mov     r14d, eax
0x180026e9c  test    eax, eax
0x180026e9e  js      short loc_180026EEB
0x180026ea0  mov     [rbp+string], 0
0x180026ea8  mov     rcx, [rbp+arg_18]
0x180026eac  mov     rax, [rcx]
0x180026eaf  lea     rdx, [rbp+string]
0x180026eb3  mov     rax, [rax+40h]
0x180026eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ebc  mov     r14d, eax
0x180026ebf  test    eax, eax
0x180026ec1  js      short loc_180026EE2
0x180026ec3  xor     edx, edx; length
0x180026ec5  mov     rcx, [rbp+string]; string
0x180026ec9  call    cs:__imp_WindowsGetStringRawBuffer
0x180026ecf  mov     rcx, rax; psz
0x180026ed2  call    cs:__imp_SysAllocString
0x180026ed8  mov     [rsi], rax
0x180026edb  test    rax, rax
0x180026ede  cmovz   r14d, ebx
0x180026ee2  lea     rcx, [rbp+string]; this
0x180026ee6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180026eeb  mov     [rbp+var_20], 0
0x180026ef3  mov     rbx, [rbp+arg_18]
0x180026ef7  mov     rax, [rbx]
0x180026efa  mov     rsi, [rax]
0x180026efd  lea     rcx, [rbp+var_20]
0x180026f01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180026f06  lea     r8, [rbp+var_20]
0x180026f0a  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180026f11  mov     rcx, rbx
0x180026f14  mov     rax, rsi
0x180026f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f1c  nop
0x180026f1d  test    eax, eax
0x180026f1f  js      short loc_180026F32
0x180026f21  mov     rcx, [rbp+var_20]
0x180026f25  mov     rax, [rcx]
0x180026f28  mov     rax, [rax+50h]
0x180026f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f31  nop
0x180026f32  lea     rcx, [rbp+var_20]
0x180026f36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180026f3b  nop
0x180026f3c  test    rdi, rdi
0x180026f3f  jz      short loc_180026F51
0x180026f41  mov     rax, [rdi]
0x180026f44  mov     rcx, rdi
0x180026f47  mov     rax, [rax+10h]
0x180026f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026f50  nop
0x180026f51  lea     rcx, [rbp+arg_18]
0x180026f55  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180026f5a  nop
0x180026f5b  lea     rcx, [rbp+var_18]
0x180026f5f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180026f64  mov     eax, r14d
0x180026f67  mov     rbx, [rsp+40h+arg_0]
0x180026f6c  mov     rsi, [rsp+40h+arg_8]
0x180026f71  add     rsp, 40h
0x180026f75  pop     r14
0x180026f77  pop     rdi
0x180026f78  pop     rbp
0x180026f79  retn
```
