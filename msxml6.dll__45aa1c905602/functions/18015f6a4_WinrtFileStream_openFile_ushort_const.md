# WinrtFileStream::openFile(ushort const *)

- ea: `0x18015f6a4`
- end: `0x18015f7ee`
- name: `?openFile@WinrtFileStream@@QEAAJPEBG@Z`
- size: `330`
- prototype: `HRESULT __fastcall(WinrtFileStream *this, const wchar_t *pwszFilename)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18015f640`

## callees

- `0x18006f2d4`
- `0x1800719e4`
- `0x1800cc6c0`
- `0x1800ed6dc`
- `0x1800ed94c`
- `0x1800edd98`
- `0x18015f6a4`
- `0x1801610e0`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015f727`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015f727`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015f741`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015f741`

## pseudocode

```c
__int64 __fastcall WinrtFileStream::openFile(WinrtFileStream *this, const wchar_t *pwszFilename)
{
  int v4; // ebx
  unsigned __int64 v5; // rcx
  Windows::Storage::IStorageFileStatics *ptr; // rdi
  HRESULT (__fastcall *GetFileFromPathAsync)(Windows::Storage::IStorageFileStatics *, HSTRING__ *, Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> **); // rbx
  unsigned int puResult; // [rsp+20h] [rbp-29h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> > oper; // [rsp+28h] [rbp-21h] BYREF
  Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile> spStorageFile; // [rsp+30h] [rbp-19h] BYREF
  Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics> spStorageFac; // [rsp+38h] [rbp-11h] BYREF
  Windows::Internal::StringReference hstrFilePath; // [rsp+40h] [rbp-9h] BYREF
  Windows::Internal::StringReference hstrFac; // [rsp+60h] [rbp+17h] BYREF

  spStorageFac.ptr_ = 0;
  Windows::Internal::StringReference::StringReference(&hstrFac, (const wchar_t (*)[28])pwszFilename);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>(
         hstrFac._hstring,
         (Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics> >)&spStorageFac);
  if ( v4 >= 0 )
  {
    puResult = 0;
    v5 = -1;
    do
      ++v5;
    while ( pwszFilename[v5] );
    if ( ULongLongToUInt(v5, &puResult) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(pwszFilename, puResult, &hstrFilePath._header, &hstrFilePath._hstring);
    ptr = spStorageFac.ptr_;
    spStorageFile.ptr_ = 0;
    oper.ptr_ = 0;
    GetFileFromPathAsync = spStorageFac.ptr_->GetFileFromPathAsync;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&oper);
    v4 = GetFileFromPathAsync(ptr, hstrFilePath._hstring, &oper.ptr_);
    if ( v4 >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spStorageFile);
      v4 = WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,Windows::Storage::IStorageFile *>(
             oper.ptr_,
             &spStorageFile.ptr_);
      if ( v4 >= 0 )
        v4 = WinrtBaseStream::openStorageFile(this, spStorageFile.ptr_);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&oper);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spStorageFile);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory> *)&spStorageFac);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18015f6a4  mov     [rsp-8+arg_10], rbx
0x18015f6a9  mov     [rsp-8+arg_18], rsi
0x18015f6ae  push    rbp
0x18015f6af  push    rdi
0x18015f6b0  push    r14
0x18015f6b2  lea     rbp, [rsp-47h]
0x18015f6b7  sub     rsp, 90h
0x18015f6be  mov     rax, cs:__security_cookie
0x18015f6c5  xor     rax, rsp
0x18015f6c8  mov     [rbp+57h+var_20], rax
0x18015f6cc  mov     rsi, this
0x18015f6cf  xor     r14d, r14d
0x18015f6d2  lea     this, [rbp+57h+hstrFac]; this
0x18015f6d6  mov     [rbp+57h+spStorageFac.ptr_], r14
0x18015f6da  mov     rdi, pwszFilename
0x18015f6dd  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x18015f6e2  mov     this, [rbp+57h+hstrFac._hstring]; activatableClassId
0x18015f6e6  lea     pwszFilename, [rbp+57h+spStorageFac]; factory
0x18015f6ea  call    ??$GetActivationFactory@V?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>)
0x18015f6ef  mov     ebx, eax
0x18015f6f1  test    eax, eax
0x18015f6f3  js      loc_18015F7BE
0x18015f6f9  mov     [rbp+57h+puResult], r14d
0x18015f6fd  or      this, 0FFFFFFFFFFFFFFFFh
0x18015f701  inc     this; ullOperand
0x18015f704  cmp     [rdi+this*2], r14w
0x18015f709  jnz     short loc_18015F701
0x18015f70b  lea     pwszFilename, [rbp+57h+puResult]; puResult
0x18015f70f  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18015f714  test    eax, eax
0x18015f716  jns     short loc_18015F733
0x18015f718  xor     r9d, r9d; lpArguments
0x18015f71b  xor     r8d, r8d; nNumberOfArguments
0x18015f71e  mov     ecx, 0C000000Dh; dwExceptionCode
0x18015f723  lea     edx, [r9+1]; dwExceptionFlags
0x18015f727  call    cs:__imp_RaiseException
0x18015f72e  nop     dword ptr [rax+rax+00h]
0x18015f733  mov     edx, [rbp+57h+puResult]; length
0x18015f736  lea     r9, [rbp+57h+hstrFilePath]; string
0x18015f73a  lea     r8, [rbp+57h+hstrFilePath._header]; hstringHeader
0x18015f73e  mov     this, rdi; sourceString
0x18015f741  call    cs:__imp_WindowsCreateStringReference
0x18015f748  nop     dword ptr [rax+rax+00h]
0x18015f74d  mov     rdi, [rbp+57h+spStorageFac.ptr_]
0x18015f751  lea     this, [rbp+57h+oper]; this
0x18015f755  mov     [rbp+57h+spStorageFile.ptr_], r14
0x18015f759  mov     [rbp+57h+oper.ptr_], r14
0x18015f75d  mov     rax, [rdi]
0x18015f760  mov     rbx, [rax+30h]
0x18015f764  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015f769  mov     pwszFilename, [rbp+57h+hstrFilePath._hstring]
0x18015f76d  lea     r8, [rbp+57h+oper]
0x18015f771  mov     this, rdi
0x18015f774  mov     rax, rbx
0x18015f777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015f77c  mov     ebx, eax
0x18015f77e  test    eax, eax
0x18015f780  js      short loc_18015F7AC
0x18015f782  lea     this, [rbp+57h+spStorageFile]; this
0x18015f786  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015f78b  mov     this, [rbp+57h+oper.ptr_]; pOperation
0x18015f78f  lea     pwszFilename, [rbp+57h+spStorageFile]; pResults
0x18015f793  call    ??$WaitForCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@PEAUIStorageFile@Storage@3@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@PEAPEAUIStorageFile@Storage@2@@Z; WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,Windows::Storage::IStorageFile *>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,Windows::Storage::IStorageFile * *)
0x18015f798  mov     ebx, eax
0x18015f79a  test    eax, eax
0x18015f79c  js      short loc_18015F7AC
0x18015f79e  mov     pwszFilename, [rbp+57h+spStorageFile.ptr_]; pFile
0x18015f7a2  mov     this, rsi; this
0x18015f7a5  call    ?openStorageFile@WinrtBaseStream@@QEAAJPEAUIStorageFile@Storage@Windows@@@Z; WinrtBaseStream::openStorageFile(Windows::Storage::IStorageFile *)
0x18015f7aa  mov     ebx, eax
0x18015f7ac  lea     this, [rbp+57h+oper]; this
0x18015f7b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015f7b5  lea     this, [rbp+57h+spStorageFile]; this
0x18015f7b9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015f7be  lea     this, [rbp+57h+spStorageFac]; this
0x18015f7c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015f7c7  mov     eax, ebx
0x18015f7c9  mov     this, [rbp+57h+var_20]
0x18015f7cd  xor     this, rsp; StackCookie
0x18015f7d0  call    __security_check_cookie
0x18015f7d5  lea     r11, [rsp+0A0h+var_10]
0x18015f7dd  mov     rbx, [r11+30h]
0x18015f7e1  mov     rsi, [r11+38h]
0x18015f7e5  mov     rsp, r11
0x18015f7e8  pop     r14
0x18015f7ea  pop     rdi
0x18015f7eb  pop     rbp
0x18015f7ec  retn
```
