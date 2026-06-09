# CServerCertValidationCallback::ValidateServerCertificate(CBackgroundCopyFile const &,_CERT_CONTEXT const *)

- ea: `0x18000b850`
- end: `0x18000bd4d`
- name: `?ValidateServerCertificate@CServerCertValidationCallback@@EEBAJAEBVCBackgroundCopyFile@@PEBU_CERT_CONTEXT@@@Z`
- size: `1277`
- prototype: `int(CServerCertValidationCallback *__hidden this, const struct CBackgroundCopyFile *, const struct _CERT_CONTEXT *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180008618`
- `0x18000933c`
- `0x18000a5e4`
- `0x18000b850`
- `0x18000c178`
- `0x18000c40c`
- `0x18000c4b0`
- `0x180084a70`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `CRYPT32!CertSaveStore` at `0x18000b8ab`
- `CRYPT32!CertSaveStore` at `0x18000b92b`
- `CRYPT32!CertSaveStore` at `0x18000b8ab`
- `CRYPT32!CertSaveStore` at `0x18000b92b`

## string_xrefs

- `0x18000b8bd`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000b93d`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000b9a4`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000ba45`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000bb18`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`
- `0x18000bc61`: `C:\__w\1\s\src\DeliveryOptimization\dll\DownloadCallbacks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall CServerCertValidationCallback::ValidateServerCertificate(
        CServerCertValidationCallback *this,
        const struct CBackgroundCopyFile *a2,
        const struct _CERT_CONTEXT *a3)
{
  const char *v5; // r9
  const char *v7; // r9
  unsigned int LastError; // ebx
  __int64 v9; // r8
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rcx
  struct IBackgroundCopyFile *v15; // rcx
  __int64 v16; // rcx
  struct IBackgroundCopyFile *v17; // rcx
  int FileExt; // eax
  __int64 v19; // rcx
  struct IBackgroundCopyFile *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdx
  int v24; // ebx
  struct IBackgroundCopyFile *v25; // rcx
  __int64 v26; // rcx
  struct IBackgroundCopyFile *v27; // rcx
  __int64 v28; // rcx
  int pvSaveToPara; // [rsp+20h] [rbp-B8h]
  _QWORD v30[7]; // [rsp+30h] [rbp-A8h] BYREF
  _QWORD *v31; // [rsp+68h] [rbp-70h]
  const struct _CERT_CONTEXT *v32; // [rsp+70h] [rbp-68h] BYREF
  int v33[4]; // [rsp+78h] [rbp-60h] BYREF
  struct IBackgroundCopyFile *v34; // [rsp+88h] [rbp-50h] BYREF
  __int64 v35; // [rsp+90h] [rbp-48h] BYREF
  __int64 v36; // [rsp+98h] [rbp-40h] BYREF
  __int128 v37; // [rsp+A0h] [rbp-38h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v32 = a3;
  *(_OWORD *)v33 = 0;
  if ( !CertSaveStore(a3->hCertStore, 0, 1u, 2u, v33, 0) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xF8,
             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
             v5);
  v37 = 0;
  v38 = 0;
  std::vector<unsigned char>::vector<unsigned char>(&v37, (unsigned int)v33[0]);
  *(_QWORD *)&v33[2] = v37;
  if ( !CertSaveStore(v32->hCertStore, 0, 1u, 2u, v33, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xFD,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
                  v7);
    std::vector<unsigned char>::_Tidy(&v37);
    return LastError;
  }
  v35 = 0;
  v9 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IBackgroundCopyJob>>(&v35);
  v10 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(**((_QWORD **)this + 2) + 24LL))(
          *((_QWORD *)this + 2),
          &GUID_37668d37_507e_4160_9316_26306d150b12,
          v9);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
      (const char *)(unsigned int)v10,
      pvSaveToPara);
    v12 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
LABEL_27:
    std::vector<unsigned char>::_Tidy(&v37);
    return v11;
  }
  v34 = 0;
  if ( (int)CBackgroundCopyFile::GetFileExt(a2, &v34) < 0 )
  {
    v36 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 40LL))(v35, &v36);
    v11 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x107,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
        (const char *)(unsigned int)v13,
        pvSaveToPara);
      v14 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      v15 = v34;
      if ( v34 )
      {
        v34 = 0;
        ((void (__fastcall *)(struct IBackgroundCopyFile *))v15->lpVtbl->Release)(v15);
      }
      v16 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      goto LABEL_27;
    }
    v17 = v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(struct IBackgroundCopyFile *))v17->lpVtbl->Release)(v17);
    }
    FileExt = CBackgroundCopyFile::GetFileExt(a2, &v34);
    v11 = FileExt;
    if ( FileExt < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x108,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
        (const char *)(unsigned int)FileExt,
        pvSaveToPara);
      v19 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v20 = v34;
      if ( v34 )
      {
        v34 = 0;
        ((void (__fastcall *)(struct IBackgroundCopyFile *))v20->lpVtbl->Release)(v20);
      }
      v21 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      goto LABEL_27;
    }
    v22 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
  }
  v30[0] = std::J$$V::Z::_Func_impl_no_alloc<`CServerCertValidationCallback::ValidateServerCertificate'::`39'::_lambda_1_,unsigned char,unsigned char,long near & volatile,CBackgroundCopyFile const &,_CERT_CONTEXT const *>::`vftable';
  v30[1] = this;
  v30[2] = &v35;
  v30[3] = &v34;
  v30[4] = &v32;
  v30[5] = v33;
  v31 = v30;
  v24 = docli::CComTimeout::MakeComCall(
          v30,
          "_spCallback->ValidateServerCertificate( spJob.Get(), spFileExt.Get(), pCertCtxt->cbCertEncoded, pCertCtxt->pbC"
          "ertEncoded, pCertCtxt->dwCertEncodingType, storeData.cbData, storeData.pbData)",
          "CServerCertValidationCallback::ValidateServerCertificate",
          274);
  if ( v31 )
  {
    LOBYTE(v23) = v31 != v30;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v31 + 32LL))(v31, v23);
  }
  if ( v24 >= 0 )
  {
    v27 = v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(struct IBackgroundCopyFile *))v27->lpVtbl->Release)(v27);
    }
    v28 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    std::vector<unsigned char>::_Tidy(&v37);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x112,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\DownloadCallbacks.cpp",
      (const char *)(unsigned int)v24,
      pvSaveToPara);
    v25 = v34;
    if ( v34 )
    {
      v34 = 0;
      ((void (__fastcall *)(struct IBackgroundCopyFile *))v25->lpVtbl->Release)(v25);
    }
    v26 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    std::vector<unsigned char>::_Tidy(&v37);
    return (unsigned int)v24;
  }
}

```

## disassembly

```asm
0x18000b850  mov     [rsp+arg_18], rbx
0x18000b855  push    rsi
0x18000b856  push    rdi
0x18000b857  push    r14
0x18000b859  sub     rsp, 0C0h
0x18000b860  mov     rax, cs:__security_cookie
0x18000b867  xor     rax, rsp
0x18000b86a  mov     [rsp+0D8h+var_20], rax
0x18000b872  mov     rax, r8
0x18000b875  mov     rdi, rdx
0x18000b878  mov     rsi, rcx
0x18000b87b  mov     [rsp+0D8h+var_68], rax
0x18000b880  xorps   xmm0, xmm0
0x18000b883  movups  xmmword ptr [rsp+0D8h+var_60], xmm0
0x18000b888  xor     r14d, r14d
0x18000b88b  mov     [rsp+0D8h+dwFlags], r14d; dwFlags
0x18000b890  lea     rcx, [rsp+0D8h+var_60]
0x18000b895  mov     [rsp+0D8h+pvSaveToPara], rcx; pvSaveToPara
0x18000b89a  lea     ebx, [r14+2]
0x18000b89e  mov     r9d, ebx; dwSaveTo
0x18000b8a1  xor     edx, edx; dwEncodingType
0x18000b8a3  lea     r8d, [r14+1]; dwSaveAs
0x18000b8a7  mov     rcx, [rax+20h]; hCertStore
0x18000b8ab  call    cs:__imp_CertSaveStore
0x18000b8b1  test    eax, eax
0x18000b8b3  jnz     short loc_18000B8D3
0x18000b8b5  mov     rcx, [rsp+0D8h]; this
0x18000b8bd  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000b8c4  mov     edx, 0F8h; void *
0x18000b8c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b8ce  jmp     loc_18000BD28
0x18000b8d3  xorps   xmm0, xmm0
0x18000b8d6  xor     eax, eax
0x18000b8d8  movups  [rsp+0D8h+var_38], xmm0
0x18000b8e0  mov     [rsp+0D8h+var_28], rax
0x18000b8e8  mov     edx, [rsp+0D8h+var_60]
0x18000b8ec  lea     rcx, [rsp+0D8h+var_38]
0x18000b8f4  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18000b8f9  nop
0x18000b8fa  mov     rax, qword ptr [rsp+0D8h+var_38]
0x18000b902  mov     qword ptr [rsp+0D8h+var_60+8], rax
0x18000b90a  mov     [rsp+0D8h+dwFlags], r14d; dwFlags
0x18000b90f  lea     rax, [rsp+0D8h+var_60]
0x18000b914  mov     [rsp+0D8h+pvSaveToPara], rax; int
0x18000b919  mov     r9d, ebx; dwSaveTo
0x18000b91c  xor     edx, edx; dwEncodingType
0x18000b91e  lea     r8d, [rdx+1]; dwSaveAs
0x18000b922  mov     rcx, [rsp+0D8h+var_68]
0x18000b927  mov     rcx, [rcx+20h]; hCertStore
0x18000b92b  call    cs:__imp_CertSaveStore
0x18000b931  test    eax, eax
0x18000b933  jnz     short loc_18000B964
0x18000b935  mov     rcx, [rsp+0D8h]; this
0x18000b93d  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000b944  mov     edx, 0FDh; void *
0x18000b949  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b94e  mov     ebx, eax
0x18000b950  lea     rcx, [rsp+0D8h+var_38]
0x18000b958  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000b95d  mov     eax, ebx
0x18000b95f  jmp     loc_18000BD28
0x18000b964  mov     [rsp+0D8h+var_48], r14
0x18000b96c  lea     rcx, [rsp+0D8h+var_48]
0x18000b974  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIBackgroundCopyJob@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIBackgroundCopyJob@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IBackgroundCopyJob>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IBackgroundCopyJob>>)
0x18000b979  mov     r8, rax
0x18000b97c  mov     rcx, [rsi+10h]
0x18000b980  mov     rdx, [rcx]
0x18000b983  mov     rax, [rdx+18h]
0x18000b987  lea     rdx, _GUID_37668d37_507e_4160_9316_26306d150b12
0x18000b98e  call    _guard_dispatch_icall
0x18000b993  mov     ebx, eax
0x18000b995  test    eax, eax
0x18000b997  jns     short loc_18000B9EC
0x18000b999  mov     rcx, [rsp+0D8h]; this
0x18000b9a1  mov     r9d, eax; char *
0x18000b9a4  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000b9ab  mov     edx, 101h; void *
0x18000b9b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b9b5  nop
0x18000b9b6  mov     rcx, [rsp+0D8h+var_48]
0x18000b9be  test    rcx, rcx
0x18000b9c1  jz      short loc_18000B9D8
0x18000b9c3  mov     [rsp+0D8h+var_48], r14
0x18000b9cb  mov     rax, [rcx]
0x18000b9ce  mov     rax, [rax+10h]
0x18000b9d2  call    _guard_dispatch_icall
0x18000b9d7  nop
0x18000b9d8  lea     rcx, [rsp+0D8h+var_38]
0x18000b9e0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000b9e5  mov     eax, ebx
0x18000b9e7  jmp     loc_18000BD28
0x18000b9ec  mov     [rsp+0D8h+var_50], r14
0x18000b9f4  lea     rdx, [rsp+0D8h+var_50]; struct IBackgroundCopyFile **
0x18000b9fc  mov     rcx, rdi; this
0x18000b9ff  call    ?GetFileExt@CBackgroundCopyFile@@QEBAJPEAPEAUIBackgroundCopyFile@@@Z; CBackgroundCopyFile::GetFileExt(IBackgroundCopyFile * *)
0x18000ba04  test    eax, eax
0x18000ba06  jns     loc_18000BBC6
0x18000ba0c  mov     [rsp+0D8h+var_40], r14
0x18000ba14  mov     rcx, [rsp+0D8h+var_48]
0x18000ba1c  mov     rax, [rcx]
0x18000ba1f  lea     rdx, [rsp+0D8h+var_40]
0x18000ba27  mov     rax, [rax+28h]
0x18000ba2b  call    _guard_dispatch_icall
0x18000ba30  mov     ebx, eax
0x18000ba32  test    eax, eax
0x18000ba34  jns     loc_18000BAD1
0x18000ba3a  mov     rcx, [rsp+0D8h]; this
0x18000ba42  mov     r9d, eax; char *
0x18000ba45  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000ba4c  mov     edx, 107h; void *
0x18000ba51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba56  nop
0x18000ba57  mov     rcx, [rsp+0D8h+var_40]
0x18000ba5f  test    rcx, rcx
0x18000ba62  jz      short loc_18000BA79
0x18000ba64  mov     [rsp+0D8h+var_40], r14
0x18000ba6c  mov     rax, [rcx]
0x18000ba6f  mov     rax, [rax+10h]
0x18000ba73  call    _guard_dispatch_icall
0x18000ba78  nop
0x18000ba79  mov     rcx, [rsp+0D8h+var_50]
0x18000ba81  test    rcx, rcx
0x18000ba84  jz      short loc_18000BA9B
0x18000ba86  mov     [rsp+0D8h+var_50], r14
0x18000ba8e  mov     rax, [rcx]
0x18000ba91  mov     rax, [rax+10h]
0x18000ba95  call    _guard_dispatch_icall
0x18000ba9a  nop
0x18000ba9b  mov     rcx, [rsp+0D8h+var_48]
0x18000baa3  test    rcx, rcx
0x18000baa6  jz      short loc_18000BABD
0x18000baa8  mov     [rsp+0D8h+var_48], r14
0x18000bab0  mov     rax, [rcx]
0x18000bab3  mov     rax, [rax+10h]
0x18000bab7  call    _guard_dispatch_icall
0x18000babc  nop
0x18000babd  lea     rcx, [rsp+0D8h+var_38]
0x18000bac5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000baca  mov     eax, ebx
0x18000bacc  jmp     loc_18000BD28
0x18000bad1  mov     rcx, [rsp+0D8h+var_50]
0x18000bad9  test    rcx, rcx
0x18000badc  jz      short loc_18000BAF3
0x18000bade  mov     [rsp+0D8h+var_50], r14
0x18000bae6  mov     rax, [rcx]
0x18000bae9  mov     rax, [rax+10h]
0x18000baed  call    _guard_dispatch_icall
0x18000baf2  nop
0x18000baf3  lea     rdx, [rsp+0D8h+var_50]; struct IBackgroundCopyFile **
0x18000bafb  mov     rcx, rdi; this
0x18000bafe  call    ?GetFileExt@CBackgroundCopyFile@@QEBAJPEAPEAUIBackgroundCopyFile@@@Z; CBackgroundCopyFile::GetFileExt(IBackgroundCopyFile * *)
0x18000bb03  mov     ebx, eax
0x18000bb05  test    eax, eax
0x18000bb07  jns     loc_18000BBA4
0x18000bb0d  mov     rcx, [rsp+0D8h]; this
0x18000bb15  mov     r9d, eax; char *
0x18000bb18  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000bb1f  mov     edx, 108h; void *
0x18000bb24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bb29  nop
0x18000bb2a  mov     rcx, [rsp+0D8h+var_40]
0x18000bb32  test    rcx, rcx
0x18000bb35  jz      short loc_18000BB4C
0x18000bb37  mov     [rsp+0D8h+var_40], r14
0x18000bb3f  mov     rax, [rcx]
0x18000bb42  mov     rax, [rax+10h]
0x18000bb46  call    _guard_dispatch_icall
0x18000bb4b  nop
0x18000bb4c  mov     rcx, [rsp+0D8h+var_50]
0x18000bb54  test    rcx, rcx
0x18000bb57  jz      short loc_18000BB6E
0x18000bb59  mov     [rsp+0D8h+var_50], r14
0x18000bb61  mov     rax, [rcx]
0x18000bb64  mov     rax, [rax+10h]
0x18000bb68  call    _guard_dispatch_icall
0x18000bb6d  nop
0x18000bb6e  mov     rcx, [rsp+0D8h+var_48]
0x18000bb76  test    rcx, rcx
0x18000bb79  jz      short loc_18000BB90
0x18000bb7b  mov     [rsp+0D8h+var_48], r14
0x18000bb83  mov     rax, [rcx]
0x18000bb86  mov     rax, [rax+10h]
0x18000bb8a  call    _guard_dispatch_icall
0x18000bb8f  nop
0x18000bb90  lea     rcx, [rsp+0D8h+var_38]
0x18000bb98  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000bb9d  mov     eax, ebx
0x18000bb9f  jmp     loc_18000BD28
0x18000bba4  mov     rcx, [rsp+0D8h+var_40]
0x18000bbac  test    rcx, rcx
0x18000bbaf  jz      short loc_18000BBC6
0x18000bbb1  mov     [rsp+0D8h+var_40], r14
0x18000bbb9  mov     rax, [rcx]
0x18000bbbc  mov     rax, [rax+10h]
0x18000bbc0  call    _guard_dispatch_icall
0x18000bbc5  nop
0x18000bbc6  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?CH@??ValidateServerCertificate@CServerCertValidationCallback@@EEBAJAEBVCBackgroundCopyFile@@PEBU_CERT_CONTEXT@@@Z@J$$V@std@@6B@; const std::_Func_impl_no_alloc<`CServerCertValidationCallback::ValidateServerCertificate(CBackgroundCopyFile const &,_CERT_CONTEXT const *)'::`39'::_lambda_1_,long,>::`vftable'
0x18000bbcd  mov     [rsp+0D8h+var_A8], rax
0x18000bbd2  mov     [rsp+0D8h+var_A0], rsi
0x18000bbd7  lea     rax, [rsp+0D8h+var_48]
0x18000bbdf  mov     [rsp+0D8h+var_98], rax
0x18000bbe4  lea     rax, [rsp+0D8h+var_50]
0x18000bbec  mov     [rsp+0D8h+var_90], rax
0x18000bbf1  lea     rax, [rsp+0D8h+var_68]
0x18000bbf6  mov     [rsp+0D8h+var_88], rax
0x18000bbfb  lea     rax, [rsp+0D8h+var_60]
0x18000bc00  mov     [rsp+0D8h+var_80], rax
0x18000bc05  lea     rax, [rsp+0D8h+var_A8]
0x18000bc0a  mov     [rsp+0D8h+var_70], rax
0x18000bc0f  mov     edi, 112h
0x18000bc14  mov     r9d, edi
0x18000bc17  lea     r8, aCservercertval_0; "CServerCertValidationCallback::Validate"...
0x18000bc1e  lea     rdx, aSpcallbackVali; "_spCallback->ValidateServerCertificate("...
0x18000bc25  lea     rcx, [rsp+0D8h+var_A8]
0x18000bc2a  call    ?MakeComCall@CComTimeout@docli@@SAJAEBV?$function@$$A6AJXZ@std@@PEBD1II@Z; docli::CComTimeout::MakeComCall(std::function<long (void)> const &,char const *,char const *,uint,uint)
0x18000bc2f  mov     ebx, eax
0x18000bc31  mov     rcx, [rsp+0D8h+var_70]
0x18000bc36  test    rcx, rcx
0x18000bc39  jz      short loc_18000BC52
0x18000bc3b  lea     rax, [rsp+0D8h+var_A8]
0x18000bc40  cmp     rcx, rax
0x18000bc43  setnz   dl
0x18000bc46  mov     r8, [rcx]
0x18000bc49  mov     rax, [r8+20h]
0x18000bc4d  call    _guard_dispatch_icall
0x18000bc52  test    ebx, ebx
0x18000bc54  jns     short loc_18000BCC5
0x18000bc56  mov     rcx, [rsp+0D8h]; this
0x18000bc5e  mov     r9d, ebx; char *
0x18000bc61  lea     r8, aCW1SSrcDeliver_97; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18000bc68  mov     edx, edi; void *
0x18000bc6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc6f  nop
0x18000bc70  mov     rcx, [rsp+0D8h+var_50]
0x18000bc78  test    rcx, rcx
0x18000bc7b  jz      short loc_18000BC92
0x18000bc7d  mov     [rsp+0D8h+var_50], r14
0x18000bc85  mov     rax, [rcx]
0x18000bc88  mov     rax, [rax+10h]
0x18000bc8c  call    _guard_dispatch_icall
0x18000bc91  nop
0x18000bc92  mov     rcx, [rsp+0D8h+var_48]
0x18000bc9a  test    rcx, rcx
0x18000bc9d  jz      short loc_18000BCB4
0x18000bc9f  mov     [rsp+0D8h+var_48], r14
0x18000bca7  mov     rax, [rcx]
0x18000bcaa  mov     rax, [rax+10h]
0x18000bcae  call    _guard_dispatch_icall
0x18000bcb3  nop
0x18000bcb4  lea     rcx, [rsp+0D8h+var_38]
0x18000bcbc  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000bcc1  mov     eax, ebx
0x18000bcc3  jmp     short loc_18000BD28
0x18000bcc5  mov     rcx, [rsp+0D8h+var_50]
0x18000bccd  test    rcx, rcx
0x18000bcd0  jz      short loc_18000BCE7
0x18000bcd2  mov     [rsp+0D8h+var_50], r14
0x18000bcda  mov     rax, [rcx]
0x18000bcdd  mov     rax, [rax+10h]
0x18000bce1  call    _guard_dispatch_icall
0x18000bce6  nop
0x18000bce7  mov     rcx, [rsp+0D8h+var_48]
0x18000bcef  test    rcx, rcx
0x18000bcf2  jz      short loc_18000BD09
0x18000bcf4  mov     [rsp+0D8h+var_48], r14
0x18000bcfc  mov     rax, [rcx]
0x18000bcff  mov     rax, [rax+10h]
0x18000bd03  call    _guard_dispatch_icall
0x18000bd08  nop
0x18000bd09  lea     rcx, [rsp+0D8h+var_38]
0x18000bd11  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000bd16  xor     eax, eax
0x18000bd18  jmp     short loc_18000BD28
0x18000bd1a  mov     eax, 8007000Eh
0x18000bd1f  jmp     short loc_18000BD28
0x18000bd21  mov     eax, dword ptr [rsp+0D8h+var_50]
0x18000bd28  mov     rcx, [rsp+0D8h+var_20]
0x18000bd30  xor     rcx, rsp; StackCookie
0x18000bd33  call    __security_check_cookie
0x18000bd38  mov     rbx, [rsp+0D8h+arg_18]
0x18000bd40  add     rsp, 0C0h
0x18000bd47  pop     r14
0x18000bd49  pop     rdi
0x18000bd4a  pop     rsi
0x18000bd4b  retn
```
