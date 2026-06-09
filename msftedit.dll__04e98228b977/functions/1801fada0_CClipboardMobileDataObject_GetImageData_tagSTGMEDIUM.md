# CClipboardMobileDataObject::GetImageData(tagSTGMEDIUM *)

- ea: `0x1801fada0`
- end: `0x1801faf7e`
- name: `?GetImageData@CClipboardMobileDataObject@@EEAAJPEAUtagSTGMEDIUM@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(CClipboardMobileDataObject *__hidden this, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18006ad18`
- `0x1801fa5ec`
- `0x1801fa6e0`
- `0x1801fada0`
- `0x1801fb230`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1801fadd1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1801fadd1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1801faeb1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1801faeb1`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1801faee4`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1801faee4`

## pseudocode

```c
__int64 __fastcall CClipboardMobileDataObject::GetImageData(CClipboardMobileDataObject *this, struct tagSTGMEDIUM *a2)
{
  unsigned int v4; // ebx
  __int64 *v5; // rax
  __int64 v6; // rsi
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64 *); // rbx
  HBITMAP v9; // rcx
  _QWORD v11[2]; // [rsp+20h] [rbp-20h] BYREF
  HANDLE hHandle; // [rsp+30h] [rbp-10h] BYREF
  __int64 v13; // [rsp+38h] [rbp-8h] BYREF
  __int64 v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+78h] [rbp+38h] BYREF

  hHandle = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( hHandle )
  {
    v15 = 0;
    v11[0] = &hHandle;
    v14 = 0;
    v11[1] = &v15;
    v5 = (__int64 *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::IAsyncOperationCompletedHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Storage::Streams::RandomAccessStreamReference___Windows::Storage::Streams::IRandomAccessStreamReference_____::___Windows::Foundation::IAsyncOperation_Windows::Storage::Streams::RandomAccessStreamReference______enum_ABI::Windows::Foundation::AsyncStatus__::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::IAsyncOperationCompletedHandler_Windows::Storage::Streams::RandomAccessStreamReference____Microsoft::WRL::FtmBase___lambda_16e0273f19fb73502069197bcb9f3657_____1_Windows::Foundation::IAsyncOperation_Windows::Storage::Streams::RandomAccessStreamReference______enum_ABI::Windows::Foundation::AsyncStatus___lambda_16e0273f19fb73502069197bcb9f3657____(
                      &v13,
                      v11);
    v6 = *v5;
    *v5 = 0;
    if ( v13 )
    {
      v13 = 0;
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>>::Release();
    }
    if ( v6 )
    {
      v7 = *((_QWORD *)this + 1);
      v8 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v7 + 144LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      v4 = v8(v7, &v14);
      if ( v4 || (v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 48LL))(v14, v6)) != 0 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      }
      else
      {
        WaitForSingleObjectEx(hHandle, 0xFFFFFFFF, 0);
        if ( v15 )
        {
          v11[0] = 0;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v11);
          CreateStreamOverRandomAccessStream(v15, &GUID_0000000c_0000_0000_c000_000000000046, v11);
          v9 = (HBITMAP)v11[0];
          if ( v11[0] )
          {
            a2->tymed = 4;
            a2->hBitmap = v9;
            (*(void (__fastcall **)(HBITMAP))(*(_QWORD *)v9 + 8LL))(v9);
          }
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v11);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        v4 = 0;
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
      v4 = -2147467259;
    }
  }
  else
  {
    v4 = -2147418113;
  }
  CEventWrapper::~CEventWrapper((CEventWrapper *)&hHandle);
  return v4;
}

```

## disassembly

```asm
0x1801fada0  mov     [rsp-18h+arg_0], rbx
0x1801fada5  mov     [rsp-18h+arg_8], rsi
0x1801fadaa  push    rbp
0x1801fadab  push    rdi
0x1801fadac  push    r14
0x1801fadae  mov     rbp, rsp
0x1801fadb1  sub     rsp, 40h
0x1801fadb5  mov     r14, rdx
0x1801fadb8  mov     [rbp+hHandle], 0
0x1801fadc0  xor     edx, edx; lpName
0x1801fadc2  mov     rdi, rcx
0x1801fadc5  xor     ecx, ecx; lpEventAttributes
0x1801fadc7  mov     r9d, 1F0003h; dwDesiredAccess
0x1801fadcd  lea     r8d, [rdx+1]; dwFlags
0x1801fadd1  call    cs:__imp_CreateEventExW
0x1801fadd8  nop     dword ptr [rax+rax+00h]
0x1801faddd  mov     [rbp+hHandle], rax
0x1801fade1  test    rax, rax
0x1801fade4  jnz     short loc_1801FADF0
0x1801fade6  mov     ebx, 8000FFFFh
0x1801fadeb  jmp     loc_1801FAF5F
0x1801fadf0  lea     rax, [rbp+hHandle]
0x1801fadf4  mov     [rbp+arg_18], 0
0x1801fadfc  mov     [rbp+var_20], rax
0x1801fae00  lea     rdx, [rbp+var_20]
0x1801fae04  lea     rax, [rbp+arg_18]
0x1801fae08  mov     [rbp+arg_10], 0
0x1801fae10  lea     rcx, [rbp+var_8]
0x1801fae14  mov     [rbp+var_18], rax
0x1801fae18  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__IAsyncOperationCompletedHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Storage__Streams__RandomAccessStreamReference___Windows__Storage__Streams__IRandomAccessStreamReference__________Windows__Foundation__IAsyncOperation_Windows__Storage__Streams__RandomAccessStreamReference______enum_ABI__Windows__Foundation__AsyncStatus____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__IAsyncOperationCompletedHandler_Windows__Storage__Streams__RandomAccessStreamReference____Microsoft__WRL__FtmBase___lambda_16e0273f19fb73502069197bcb9f3657_____1_Windows__Foundation__IAsyncOperation_Windows__Storage__Streams__RandomAccessStreamReference______enum_ABI__Windows__Foundation__AsyncStatus___lambda_16e0273f19fb73502069197bcb9f3657____
0x1801fae1d  mov     rsi, [rax]
0x1801fae20  mov     qword ptr [rax], 0
0x1801fae27  mov     rcx, [rbp+var_8]
0x1801fae2b  test    rcx, rcx
0x1801fae2e  jz      short loc_1801FAE3D
0x1801fae30  mov     [rbp+var_8], 0
0x1801fae38  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VFtmBase@23@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::FtmBase>>::Release(void)
0x1801fae3d  lea     rcx, [rbp+arg_10]
0x1801fae41  test    rsi, rsi
0x1801fae44  jnz     short loc_1801FAE5E
0x1801fae46  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fae4b  lea     rcx, [rbp+arg_18]
0x1801fae4f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fae54  mov     ebx, 80004005h
0x1801fae59  jmp     loc_1801FAF5F
0x1801fae5e  mov     rdi, [rdi+8]
0x1801fae62  mov     rax, [rdi]
0x1801fae65  mov     rbx, [rax+90h]
0x1801fae6c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801fae71  lea     rdx, [rbp+arg_10]
0x1801fae75  mov     rcx, rdi
0x1801fae78  mov     rax, rbx
0x1801fae7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fae80  mov     ebx, eax
0x1801fae82  test    eax, eax
0x1801fae84  jnz     loc_1801FAF3E
0x1801fae8a  mov     rcx, [rbp+arg_10]
0x1801fae8e  mov     rdx, rsi
0x1801fae91  mov     rax, [rcx]
0x1801fae94  mov     rax, [rax+30h]
0x1801fae98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fae9d  mov     ebx, eax
0x1801fae9f  test    eax, eax
0x1801faea1  jnz     loc_1801FAF3E
0x1801faea7  mov     rcx, [rbp+hHandle]; hHandle
0x1801faeab  xor     r8d, r8d; bAlertable
0x1801faeae  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1801faeb1  call    cs:__imp_WaitForSingleObjectEx
0x1801faeb8  nop     dword ptr [rax+rax+00h]
0x1801faebd  cmp     [rbp+arg_18], 0
0x1801faec2  jz      short loc_1801FAF19
0x1801faec4  lea     rcx, [rbp+var_20]
0x1801faec8  mov     [rbp+var_20], 0
0x1801faed0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801faed5  mov     rcx, [rbp+arg_18]
0x1801faed9  lea     r8, [rbp+var_20]
0x1801faedd  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x1801faee4  call    cs:__imp_CreateStreamOverRandomAccessStream
0x1801faeeb  nop     dword ptr [rax+rax+00h]
0x1801faef0  mov     rcx, [rbp+var_20]
0x1801faef4  test    rcx, rcx
0x1801faef7  jz      short loc_1801FAF10
0x1801faef9  mov     dword ptr [r14], 4
0x1801faf00  mov     [r14+8], rcx
0x1801faf04  mov     rax, [rcx]
0x1801faf07  mov     rax, [rax+8]
0x1801faf0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801faf10  lea     rcx, [rbp+var_20]
0x1801faf14  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801faf19  mov     rax, [rsi]
0x1801faf1c  mov     rcx, rsi
0x1801faf1f  mov     rax, [rax+10h]
0x1801faf23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801faf28  lea     rcx, [rbp+arg_10]
0x1801faf2c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801faf31  lea     rcx, [rbp+arg_18]
0x1801faf35  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801faf3a  xor     ebx, ebx
0x1801faf3c  jmp     short loc_1801FAF5F
0x1801faf3e  mov     rax, [rsi]
0x1801faf41  mov     rcx, rsi
0x1801faf44  mov     rax, [rax+10h]
0x1801faf48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801faf4d  lea     rcx, [rbp+arg_10]
0x1801faf51  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801faf56  lea     rcx, [rbp+arg_18]
0x1801faf5a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801faf5f  lea     rcx, [rbp+hHandle]; this
0x1801faf63  call    ??1CEventWrapper@@QEAA@XZ; CEventWrapper::~CEventWrapper(void)
0x1801faf68  mov     rsi, [rsp+40h+arg_8]
0x1801faf6d  mov     eax, ebx
0x1801faf6f  mov     rbx, [rsp+40h+arg_0]
0x1801faf74  add     rsp, 40h
0x1801faf78  pop     r14
0x1801faf7a  pop     rdi
0x1801faf7b  pop     rbp
0x1801faf7c  retn
```
