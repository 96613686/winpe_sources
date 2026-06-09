# WinrtBaseStream::openStorageFile(Windows::Storage::IStorageFile *)

- ea: `0x1013eeb7`
- end: `0x1013ef66`
- name: `?openStorageFile@WinrtBaseStream@@QAEJPAUIStorageFile@Storage@Windows@@@Z`
- size: `175`
- prototype: `HRESULT __thiscall(WinrtBaseStream *this, Windows::Storage::IStorageFile *pFile)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1013d73a`
- `0x1013d920`

## callees

- `0x10040bb4`
- `0x10067b20`
- `0x10073ac9`
- `0x100a0dd4`
- `0x100a1157`
- `0x1013eeb7`

## import_xrefs

- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1013ef21`
- `api-ms-win-shcore-stream-winrt-l1-1-0!CreateStreamOverRandomAccessStream` at `0x1013ef21`

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
0x1013eeb7  mov     edi, edi
0x1013eeb9  push    ebp
0x1013eeba  mov     ebp, esp
0x1013eebc  sub     esp, 10h
0x1013eebf  push    ebx
0x1013eec0  push    esi
0x1013eec1  mov     esi, [ebp+pFile]
0x1013eec4  xor     ebx, ebx
0x1013eec6  mov     [ebp+var_10], this
0x1013eec9  lea     this, [ebp+oper]; this
0x1013eecc  push    edi
0x1013eecd  mov     [ebp+oper.ptr_], ebx
0x1013eed0  mov     eax, [esi]
0x1013eed2  mov     [ebp+pRandAccessStream.ptr_], ebx
0x1013eed5  mov     [ebp+spStream.ptr_], ebx
0x1013eed8  mov     edi, [eax+20h]
0x1013eedb  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013eee0  lea     eax, [ebp+oper]
0x1013eee3  mov     this, edi; this
0x1013eee5  push    eax
0x1013eee6  push    ebx
0x1013eee7  push    esi
0x1013eee8  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013eeee  call    edi
0x1013eef0  mov     ebx, eax
0x1013eef2  test    ebx, ebx
0x1013eef4  js      short loc_1013EF45
0x1013eef6  lea     this, [ebp+pRandAccessStream]; this
0x1013eef9  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013eefe  mov     this, [ebp+oper.ptr_]; pOperation
0x1013ef01  lea     edx, [ebp+pRandAccessStream]; pResults
0x1013ef04  call    ??$WaitForCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@23@PAUIRandomAccessStream@Streams@Storage@3@@@YGJPAU?$IAsyncOperation@PAUIRandomAccessStream@Streams@Storage@Windows@@@Foundation@Windows@@PAPAUIRandomAccessStream@Streams@Storage@2@@Z; WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *>,Windows::Storage::Streams::IRandomAccessStream *>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IRandomAccessStream *> *,Windows::Storage::Streams::IRandomAccessStream * *)
0x1013ef09  mov     ebx, eax
0x1013ef0b  test    ebx, ebx
0x1013ef0d  js      short loc_1013EF45
0x1013ef0f  lea     eax, [ebp+spStream]
0x1013ef12  push    eax; pp
0x1013ef13  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YGPAPAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x1013ef18  push    eax
0x1013ef19  push    offset __GUID_0000000c_0000_0000_c000_000000000046
0x1013ef1e  push    [ebp+pRandAccessStream.ptr_]
0x1013ef21  call    ds:__imp__CreateStreamOverRandomAccessStream@12; CreateStreamOverRandomAccessStream(x,x,x)
0x1013ef27  mov     ebx, eax
0x1013ef29  test    ebx, ebx
0x1013ef2b  js      short loc_1013EF45
0x1013ef2d  mov     edi, [ebp+var_10]
0x1013ef30  mov     esi, [ebp+spStream.ptr_]
0x1013ef33  mov     [ebp+spStream.ptr_], 0
0x1013ef3a  lea     this, [edi+24h]; ppref
0x1013ef3d  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1013ef42  mov     [edi+24h], esi
0x1013ef45  lea     this, [ebp+spStream]; this
0x1013ef48  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013ef4d  lea     this, [ebp+pRandAccessStream]; this
0x1013ef50  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013ef55  lea     this, [ebp+oper]; this
0x1013ef58  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013ef5d  pop     edi
0x1013ef5e  pop     esi
0x1013ef5f  mov     eax, ebx
0x1013ef61  pop     ebx
0x1013ef62  leave
0x1013ef63  retn    4
```
