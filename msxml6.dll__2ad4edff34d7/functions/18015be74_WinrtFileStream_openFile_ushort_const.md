# WinrtFileStream::openFile(ushort const *)

- ea: `0x18015be74`
- end: `0x18015bfb1`
- name: `?openFile@WinrtFileStream@@QEAAJPEBG@Z`
- size: `317`
- prototype: `__int64 __fastcall(WinrtFileStream *this, const wchar_t *pwszFilename)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18015be10`

## callees

- `0x180071640`
- `0x1800730a4`
- `0x1800cada0`
- `0x1800eb51c`
- `0x1800eb764`
- `0x1800ebb94`
- `0x18015be74`
- `0x18015d7b0`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015bef7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18015bef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015bf0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18015bf0b`

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
0x18015be74  mov     [rsp-8+arg_10], rbx
0x18015be79  mov     [rsp-8+arg_18], rsi
0x18015be7e  push    rbp
0x18015be7f  push    rdi
0x18015be80  push    r14
0x18015be82  lea     rbp, [rsp-47h]
0x18015be87  sub     rsp, 90h
0x18015be8e  mov     rax, cs:__security_cookie
0x18015be95  xor     rax, rsp
0x18015be98  mov     [rbp+57h+var_20], rax
0x18015be9c  mov     rsi, this
0x18015be9f  xor     r14d, r14d
0x18015bea2  lea     this, [rbp+57h+hstrFac]; this
0x18015bea6  mov     [rbp+57h+spStorageFac.ptr_], r14
0x18015beaa  mov     rdi, pwszFilename
0x18015bead  call    ??$?0$0BM@@StringReference@Internal@Windows@@QEAA@AEAY0BM@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[28])
0x18015beb2  mov     this, [rbp+57h+hstrFac._hstring]; activatableClassId
0x18015beb6  lea     pwszFilename, [rbp+57h+spStorageFac]; factory
0x18015beba  call    ??$GetActivationFactory@V?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>)
0x18015bebf  mov     ebx, eax
0x18015bec1  test    eax, eax
0x18015bec3  js      loc_18015BF82
0x18015bec9  mov     [rbp+57h+puResult], r14d
0x18015becd  or      this, 0FFFFFFFFFFFFFFFFh
0x18015bed1  inc     this; ullOperand
0x18015bed4  cmp     [rdi+this*2], r14w
0x18015bed9  jnz     short loc_18015BED1
0x18015bedb  lea     pwszFilename, [rbp+57h+puResult]; puResult
0x18015bedf  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18015bee4  test    eax, eax
0x18015bee6  jns     short loc_18015BEFD
0x18015bee8  xor     r9d, r9d; lpArguments
0x18015beeb  xor     r8d, r8d; nNumberOfArguments
0x18015beee  mov     ecx, 0C000000Dh; dwExceptionCode
0x18015bef3  lea     edx, [r9+1]; dwExceptionFlags
0x18015bef7  call    cs:__imp_RaiseException
0x18015befd  mov     edx, [rbp+57h+puResult]; length
0x18015bf00  lea     r9, [rbp+57h+hstrFilePath]; string
0x18015bf04  lea     r8, [rbp+57h+hstrFilePath._header]; hstringHeader
0x18015bf08  mov     this, rdi; sourceString
0x18015bf0b  call    cs:__imp_WindowsCreateStringReference
0x18015bf11  mov     rdi, [rbp+57h+spStorageFac.ptr_]
0x18015bf15  lea     this, [rbp+57h+oper]; this
0x18015bf19  mov     [rbp+57h+spStorageFile.ptr_], r14
0x18015bf1d  mov     [rbp+57h+oper.ptr_], r14
0x18015bf21  mov     rax, [rdi]
0x18015bf24  mov     rbx, [rax+30h]
0x18015bf28  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015bf2d  mov     pwszFilename, [rbp+57h+hstrFilePath._hstring]
0x18015bf31  lea     r8, [rbp+57h+oper]
0x18015bf35  mov     this, rdi
0x18015bf38  mov     rax, rbx
0x18015bf3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015bf40  mov     ebx, eax
0x18015bf42  test    eax, eax
0x18015bf44  js      short loc_18015BF70
0x18015bf46  lea     this, [rbp+57h+spStorageFile]; this
0x18015bf4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015bf4f  mov     this, [rbp+57h+oper.ptr_]; pOperation
0x18015bf53  lea     pwszFilename, [rbp+57h+spStorageFile]; pResults
0x18015bf57  call    ??$WaitForCompletionAndGetResults@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@23@PEAUIStorageFile@Storage@3@@@YAJPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@PEAPEAUIStorageFile@Storage@2@@Z; WaitForCompletionAndGetResults<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *>,Windows::Storage::IStorageFile *>(Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> *,Windows::Storage::IStorageFile * *)
0x18015bf5c  mov     ebx, eax
0x18015bf5e  test    eax, eax
0x18015bf60  js      short loc_18015BF70
0x18015bf62  mov     pwszFilename, [rbp+57h+spStorageFile.ptr_]; pFile
0x18015bf66  mov     this, rsi; this
0x18015bf69  call    ?openStorageFile@WinrtBaseStream@@QEAAJPEAUIStorageFile@Storage@Windows@@@Z; WinrtBaseStream::openStorageFile(Windows::Storage::IStorageFile *)
0x18015bf6e  mov     ebx, eax
0x18015bf70  lea     this, [rbp+57h+oper]; this
0x18015bf74  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015bf79  lea     this, [rbp+57h+spStorageFile]; this
0x18015bf7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015bf82  lea     this, [rbp+57h+spStorageFac]; this
0x18015bf86  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18015bf8b  mov     eax, ebx
0x18015bf8d  mov     this, [rbp+57h+var_20]
0x18015bf91  xor     this, rsp; StackCookie
0x18015bf94  call    __security_check_cookie
0x18015bf99  lea     r11, [rsp+0A0h+var_10]
0x18015bfa1  mov     rbx, [r11+30h]
0x18015bfa5  mov     rsi, [r11+38h]
0x18015bfa9  mov     rsp, r11
0x18015bfac  pop     r14
0x18015bfae  pop     rdi
0x18015bfaf  pop     rbp
0x18015bfb0  retn
```
