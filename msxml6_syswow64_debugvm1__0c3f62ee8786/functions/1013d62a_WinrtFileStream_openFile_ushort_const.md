# WinrtFileStream::openFile(ushort const *)

- ea: `0x1013d62a`
- end: `0x1013d70e`
- name: `?openFile@WinrtFileStream@@QAEJPBG@Z`
- size: `228`
- prototype: `HRESULT __thiscall(WinrtFileStream *this, const wchar_t *pwszFilename)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1013d5e0`

## callees

- `0x10067bc0`
- `0x1006b510`
- `0x10073a99`
- `0x100a096e`
- `0x100a0c87`
- `0x100a10bb`
- `0x1013d62a`
- `0x1013eda7`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d68a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d68a`

## pseudocode

```c
HRESULT __thiscall WinrtFileStream::openFile(WinrtFileStream *this, const wchar_t *pwszFilename)
{
  int v3; // esi
  Windows::Storage::IStorageFileStatics *ptr; // esi
  HRESULT (__stdcall *GetFileFromPathAsync)(Windows::Storage::IStorageFileStatics *, HSTRING__ *, Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> **); // edi
  Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics> spStorageFac; // [esp+Ch] [ebp-40h] BYREF
  Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile> spStorageFile; // [esp+10h] [ebp-3Ch] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> > oper; // [esp+14h] [ebp-38h] BYREF
  Windows::Internal::StringReference hstrFac; // [esp+18h] [ebp-34h] BYREF
  Windows::Internal::StringReference hstrFilePath; // [esp+30h] [ebp-1Ch] BYREF

  spStorageFac.ptr_ = 0;
  Windows::Internal::StringReference::StringReference(&hstrFac, (const wchar_t (*)[28])this);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>(
         hstrFac._hstring,
         (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics> >)&spStorageFac);
  if ( v3 >= 0 )
  {
    WindowsCreateStringReference(pwszFilename, wcslen(pwszFilename), &hstrFilePath._header, &hstrFilePath._hstring);
    spStorageFile.ptr_ = 0;
    oper.ptr_ = 0;
    ptr = spStorageFac.ptr_;
    GetFileFromPathAsync = spStorageFac.ptr_->GetFileFromPathAsync;
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&oper);
    v3 = ((int (__thiscall *)(HRESULT (__stdcall *)(Windows::Storage::IStorageFileStatics *, HSTRING__ *, Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> **), Windows::Storage::IStorageFileStatics *, HSTRING__ *, Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> > *))GetFileFromPathAsync)(
           GetFileFromPathAsync,
           ptr,
           hstrFilePath._hstring,
           &oper);
    if ( v3 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spStorageFile);
      v3 = WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,Windows::Storage::IStorageFile *>(
             oper.ptr_,
             &spStorageFile.ptr_);
      if ( v3 >= 0 )
        v3 = WinrtBaseStream::openStorageFile(this, spStorageFile.ptr_);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&oper);
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spStorageFile);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spStorageFac);
  return v3;
}

```

## disassembly

```asm
0x1013d62a  mov     edi, edi
0x1013d62c  push    ebp
0x1013d62d  mov     ebp, esp
0x1013d62f  sub     esp, 40h
0x1013d632  mov     eax, ___security_cookie
0x1013d637  xor     eax, ebp
0x1013d639  mov     [ebp+var_4], eax
0x1013d63c  push    ebx
0x1013d63d  push    esi
0x1013d63e  push    edi
0x1013d63f  mov     edi, [ebp+pwszFilename]
0x1013d642  mov     ebx, this
0x1013d644  push    this; wchar_t (*)[28]
0x1013d645  lea     this, [ebp+hstrFac]; this
0x1013d648  mov     [ebp+spStorageFac.ptr_], 0
0x1013d64f  call    ??$?0$0BM@@StringReference@Internal@Windows@@QAE@AAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x1013d654  mov     this, [ebp+hstrFac._hstring]; activatableClassId
0x1013d657  lea     eax, [ebp+spStorageFac]
0x1013d65a  push    eax; factory
0x1013d65b  call    ??$GetActivationFactory@V?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YGJPAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>)
0x1013d660  mov     esi, eax
0x1013d662  test    esi, esi
0x1013d664  js      loc_1013D6F3
0x1013d66a  mov     this, edi
0x1013d66c  xor     esi, esi
0x1013d66e  lea     edx, [this+2]
0x1013d671  mov     ax, [this]
0x1013d674  add     this, 2
0x1013d677  cmp     ax, si
0x1013d67a  jnz     short loc_1013D671
0x1013d67c  lea     eax, [ebp+hstrFilePath]
0x1013d67f  sub     this, edx
0x1013d681  push    eax; string
0x1013d682  lea     eax, [ebp+hstrFilePath._header]
0x1013d685  sar     this, 1
0x1013d687  push    eax; hstringHeader
0x1013d688  push    this; length
0x1013d689  push    edi; sourceString
0x1013d68a  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x1013d690  mov     [ebp+spStorageFile.ptr_], esi
0x1013d693  lea     this, [ebp+oper]; this
0x1013d696  mov     [ebp+oper.ptr_], esi
0x1013d699  mov     esi, [ebp+spStorageFac.ptr_]
0x1013d69c  mov     eax, [esi]
0x1013d69e  mov     edi, [eax+18h]
0x1013d6a1  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d6a6  lea     eax, [ebp+oper]
0x1013d6a9  mov     this, edi; this
0x1013d6ab  push    eax
0x1013d6ac  push    [ebp+hstrFilePath._hstring]
0x1013d6af  push    esi
0x1013d6b0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013d6b6  call    edi
0x1013d6b8  mov     esi, eax
0x1013d6ba  test    esi, esi
0x1013d6bc  js      short loc_1013D6E3
0x1013d6be  lea     this, [ebp+spStorageFile]; this
0x1013d6c1  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d6c6  mov     this, [ebp+oper.ptr_]; pOperation
0x1013d6c9  lea     edx, [ebp+spStorageFile]; pResults
0x1013d6cc  call    ??$WaitForCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@PAUIStorageFile@Storage@3@@@YGJPAU?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@PAPAUIStorageFile@Storage@2@@Z; WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,Windows::Storage::IStorageFile *>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,Windows::Storage::IStorageFile * *)
0x1013d6d1  mov     esi, eax
0x1013d6d3  test    esi, esi
0x1013d6d5  js      short loc_1013D6E3
0x1013d6d7  push    [ebp+spStorageFile.ptr_]; pFile
0x1013d6da  mov     this, ebx; this
0x1013d6dc  call    ?openStorageFile@WinrtBaseStream@@QAEJPAUIStorageFile@Storage@Windows@@@Z; WinrtBaseStream::openStorageFile(Windows::Storage::IStorageFile *)
0x1013d6e1  mov     esi, eax
0x1013d6e3  lea     this, [ebp+oper]; this
0x1013d6e6  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d6eb  lea     this, [ebp+spStorageFile]; this
0x1013d6ee  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d6f3  lea     this, [ebp+spStorageFac]; this
0x1013d6f6  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d6fb  mov     this, [ebp+var_4]
0x1013d6fe  mov     eax, esi
0x1013d700  pop     edi
0x1013d701  pop     esi
0x1013d702  xor     this, ebp; cookie
0x1013d704  pop     ebx
0x1013d705  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1013d70a  leave
0x1013d70b  retn    4
```
