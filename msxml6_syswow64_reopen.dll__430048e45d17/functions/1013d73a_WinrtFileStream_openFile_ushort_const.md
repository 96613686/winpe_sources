# WinrtFileStream::openFile(ushort const *)

- ea: `0x1013d73a`
- end: `0x1013d81e`
- name: `?openFile@WinrtFileStream@@QAEJPBG@Z`
- size: `228`
- prototype: `HRESULT __thiscall(WinrtFileStream *this, const wchar_t *pwszFilename)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1013d6f0`

## callees

- `0x10067b20`
- `0x1006b470`
- `0x10073ac9`
- `0x100a0a2e`
- `0x100a0d47`
- `0x100a11ad`
- `0x1013d73a`
- `0x1013eeb7`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d79a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1013d79a`

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
0x1013d73a  mov     edi, edi
0x1013d73c  push    ebp
0x1013d73d  mov     ebp, esp
0x1013d73f  sub     esp, 40h
0x1013d742  mov     eax, ___security_cookie
0x1013d747  xor     eax, ebp
0x1013d749  mov     [ebp+var_4], eax
0x1013d74c  push    ebx
0x1013d74d  push    esi
0x1013d74e  push    edi
0x1013d74f  mov     edi, [ebp+pwszFilename]
0x1013d752  mov     ebx, this
0x1013d754  push    this; wchar_t (*)[28]
0x1013d755  lea     this, [ebp+hstrFac]; this
0x1013d758  mov     [ebp+spStorageFac.ptr_], 0
0x1013d75f  call    ??$?0$0BM@@StringReference@Internal@Windows@@QAE@AAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x1013d764  mov     this, [ebp+hstrFac._hstring]; activatableClassId
0x1013d767  lea     eax, [ebp+spStorageFac]
0x1013d76a  push    eax; factory
0x1013d76b  call    ??$GetActivationFactory@V?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YGJPAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>)
0x1013d770  mov     esi, eax
0x1013d772  test    esi, esi
0x1013d774  js      loc_1013D803
0x1013d77a  mov     this, edi
0x1013d77c  xor     esi, esi
0x1013d77e  lea     edx, [this+2]
0x1013d781  mov     ax, [this]
0x1013d784  add     this, 2
0x1013d787  cmp     ax, si
0x1013d78a  jnz     short loc_1013D781
0x1013d78c  lea     eax, [ebp+hstrFilePath]
0x1013d78f  sub     this, edx
0x1013d791  push    eax; string
0x1013d792  lea     eax, [ebp+hstrFilePath._header]
0x1013d795  sar     this, 1
0x1013d797  push    eax; hstringHeader
0x1013d798  push    this; length
0x1013d799  push    edi; sourceString
0x1013d79a  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x1013d7a0  mov     [ebp+spStorageFile.ptr_], esi
0x1013d7a3  lea     this, [ebp+oper]; this
0x1013d7a6  mov     [ebp+oper.ptr_], esi
0x1013d7a9  mov     esi, [ebp+spStorageFac.ptr_]
0x1013d7ac  mov     eax, [esi]
0x1013d7ae  mov     edi, [eax+18h]
0x1013d7b1  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d7b6  lea     eax, [ebp+oper]
0x1013d7b9  mov     this, edi; this
0x1013d7bb  push    eax
0x1013d7bc  push    [ebp+hstrFilePath._hstring]
0x1013d7bf  push    esi
0x1013d7c0  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1013d7c6  call    edi
0x1013d7c8  mov     esi, eax
0x1013d7ca  test    esi, esi
0x1013d7cc  js      short loc_1013D7F3
0x1013d7ce  lea     this, [ebp+spStorageFile]; this
0x1013d7d1  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d7d6  mov     this, [ebp+oper.ptr_]; pOperation
0x1013d7d9  lea     edx, [ebp+spStorageFile]; pResults
0x1013d7dc  call    ??$WaitForCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@23@PAUIStorageFile@Storage@3@@@YGJPAU?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@PAPAUIStorageFile@Storage@2@@Z; WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,Windows::Storage::IStorageFile *>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,Windows::Storage::IStorageFile * *)
0x1013d7e1  mov     esi, eax
0x1013d7e3  test    esi, esi
0x1013d7e5  js      short loc_1013D7F3
0x1013d7e7  push    [ebp+spStorageFile.ptr_]; pFile
0x1013d7ea  mov     this, ebx; this
0x1013d7ec  call    ?openStorageFile@WinrtBaseStream@@QAEJPAUIStorageFile@Storage@Windows@@@Z; WinrtBaseStream::openStorageFile(Windows::Storage::IStorageFile *)
0x1013d7f1  mov     esi, eax
0x1013d7f3  lea     this, [ebp+oper]; this
0x1013d7f6  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d7fb  lea     this, [ebp+spStorageFile]; this
0x1013d7fe  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d803  lea     this, [ebp+spStorageFac]; this
0x1013d806  call    ?InternalRelease@?$ComPtr@U?$IAsyncOperation@PAVStorageFile@Storage@Windows@@@Foundation@Windows@@@WRL@Microsoft@@IAEKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>>::InternalRelease(void)
0x1013d80b  mov     this, [ebp+var_4]
0x1013d80e  mov     eax, esi
0x1013d810  pop     edi
0x1013d811  pop     esi
0x1013d812  xor     this, ebp; cookie
0x1013d814  pop     ebx
0x1013d815  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1013d81a  leave
0x1013d81b  retn    4
```
