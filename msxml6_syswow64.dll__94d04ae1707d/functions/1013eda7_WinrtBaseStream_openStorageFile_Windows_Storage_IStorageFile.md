# WinrtBaseStream::openStorageFile(Windows::Storage::IStorageFile *)

- ea: `0x1013eda7`
- end: `0x1013ee56`
- name: `?openStorageFile@WinrtBaseStream@@QAEJPAUIStorageFile@Storage@Windows@@@Z`
- size: `175`
- prototype: `HRESULT __thiscall(WinrtBaseStream *this, Windows::Storage::IStorageFile *pFile)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1013d62a`
- `0x1013d810`

## callees

- `0x10040c44`
- `0x10067bc0`
- `0x10073a99`
- `0x100a0d14`
- `0x100a1065`
- `0x1013eda7`

## import_xrefs

- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1013ee11`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1013ee11`

## pseudocode

```c
HRESULT __thiscall WinrtBaseStream::openStorageFile(WinrtBaseStream *this, Windows::Storage::IStorageFile *pFile)
{
  Windows::Storage::IStorageFile_vtbl *v2; // eax
  HRESULT (__stdcall *OpenAsync)(Windows::Storage::IStorageFile *, Windows::Storage::FileAccessMode, Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> **); // edi
  int StreamOverRandomAccessStream; // ebx
  void **v5; // eax
  IStream *ptr; // esi
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> > oper; // [esp+10h] [ebp-Ch] BYREF
  Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream> pRandAccessStream; // [esp+14h] [ebp-8h] BYREF
  Microsoft::WRL::ComPtr<IStream> spStream; // [esp+18h] [ebp-4h] BYREF

  oper.ptr_ = 0;
  v2 = pFile->__vftable;
  pRandAccessStream.ptr_ = 0;
  spStream.ptr_ = 0;
  OpenAsync = v2->OpenAsync;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&oper);
  StreamOverRandomAccessStream = ((int (__thiscall *)(HRESULT (__stdcall *)(Windows::Storage::IStorageFile *, Windows::Storage::FileAccessMode, Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> **), Windows::Storage::IStorageFile *, _DWORD, Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> > *))OpenAsync)(
                                   OpenAsync,
                                   pFile,
                                   0,
                                   &oper);
  if ( StreamOverRandomAccessStream >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pRandAccessStream);
    StreamOverRandomAccessStream = WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Storage::Streams::IRandomAccessStream *>(
                                     oper.ptr_,
                                     &pRandAccessStream.ptr_);
    if ( StreamOverRandomAccessStream >= 0 )
    {
      v5 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>((Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IStream> >)&spStream);
      StreamOverRandomAccessStream = CreateStreamOverRandomAccessStream(
                                       pRandAccessStream.ptr_,
                                       &_GUID_0000000c_0000_0000_c000_000000000046,
                                       v5);
      if ( StreamOverRandomAccessStream >= 0 )
      {
        ptr = spStream.ptr_;
        spStream.ptr_ = 0;
        release(&this->_pStream._p);
        this->_pStream._p = ptr;
      }
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spStream);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&pRandAccessStream);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&oper);
  return StreamOverRandomAccessStream;
}

```

## disassembly

```asm
0x1013eda7  mov     edi, edi
0x1013eda9  push    ebp
0x1013edaa  mov     ebp, esp
0x1013edac  sub     esp, 10h
0x1013edaf  push    ebx
0x1013edb0  push    esi
0x1013edb1  mov     esi, [ebp+pFile]
0x1013edb4  xor     ebx, ebx
0x1013edb6  mov     [ebp+var_10], this
0x1013edb9  lea     this, [ebp+oper]; this
0x1013edbc  push    edi
0x1013edbd  mov     [ebp+oper.ptr_], ebx
0x1013edc0  mov     eax, [esi]
0x1013edc2  mov     [ebp+pRandAccessStream.ptr_], ebx
0x1013edc5  mov     [ebp+spStream.ptr_], ebx
0x1013edc8  mov     edi, [eax+20h]
0x1013edcb  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013edd0  lea     eax, [ebp+oper]
0x1013edd3  mov     this, edi; this
0x1013edd5  push    eax
0x1013edd6  push    ebx
0x1013edd7  push    esi
0x1013edd8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013edde  call    edi
0x1013ede0  mov     ebx, eax
0x1013ede2  test    ebx, ebx
0x1013ede4  js      short loc_1013EE35
0x1013ede6  lea     this, [ebp+pRandAccessStream]; this
0x1013ede9  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013edee  mov     this, [ebp+oper.ptr_]; pOperation
0x1013edf1  lea     edx, [ebp+pRandAccessStream]; pResults
0x1013edf4  call    ??$WaitForCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@PAUIRandomAccessStream@Streams@Storage@3@@@YGJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@PAPAUIRandomAccessStream@Streams@Storage@2@@Z; WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Storage::Streams::IRandomAccessStream *>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Windows::Storage::Streams::IRandomAccessStream * *)
0x1013edf9  mov     ebx, eax
0x1013edfb  test    ebx, ebx
0x1013edfd  js      short loc_1013EE35
0x1013edff  lea     eax, [ebp+spStream]
0x1013ee02  push    eax; pp
0x1013ee03  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YGPAPAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1013ee08  push    eax
0x1013ee09  push    offset __GUID_0000000c_0000_0000_c000_000000000046
0x1013ee0e  push    [ebp+pRandAccessStream.ptr_]
0x1013ee11  call    ds:__imp__CreateStreamOverRandomAccessStream@12; CreateStreamOverRandomAccessStream(x,x,x)
0x1013ee17  mov     ebx, eax
0x1013ee19  test    ebx, ebx
0x1013ee1b  js      short loc_1013EE35
0x1013ee1d  mov     edi, [ebp+var_10]
0x1013ee20  mov     esi, [ebp+spStream.ptr_]
0x1013ee23  mov     [ebp+spStream.ptr_], 0
0x1013ee2a  lea     this, [edi+24h]; ppref
0x1013ee2d  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1013ee32  mov     [edi+24h], esi
0x1013ee35  lea     this, [ebp+spStream]; this
0x1013ee38  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013ee3d  lea     this, [ebp+pRandAccessStream]; this
0x1013ee40  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013ee45  lea     this, [ebp+oper]; this
0x1013ee48  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013ee4d  pop     edi
0x1013ee4e  pop     esi
0x1013ee4f  mov     eax, ebx
0x1013ee51  pop     ebx
0x1013ee52  leave
0x1013ee53  retn    4
```
