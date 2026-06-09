# CThumbnailRequest::_CreateThumbnailImage(void)

- ea: `0x18000f40c`
- end: `0x18000f624`
- name: `?_CreateThumbnailImage@CThumbnailRequest@@AEAAXXZ`
- size: `536`
- prototype: `void __fastcall(CThumbnailRequest *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180020d80`

## callees

- `0x180001710`
- `0x18000f40c`
- `0x18000f62c`
- `0x180010af0`
- `0x180015050`
- `0x1800214dc`
- `0x180021770`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f5a7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000f5a7`
- `MFPlat!MFCreateStreamOnMFByteStream` at `0x18000f4d8`
- `MFPlat!MFCreateStreamOnMFByteStream` at `0x18000f4d8`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall CThumbnailRequest::_CreateThumbnailImage(CThumbnailRequest *this)
{
  struct IWICBitmapDecoder *v2; // r14
  const unsigned __int16 *v3; // rbx
  int ByteStreamFromUrl; // eax
  __int64 v5; // r8
  struct IWICBitmapSource *v6; // rdi
  HRESULT (__stdcall *QueryInterface)(IWICBitmapSource *, const IID *const, void **); // rbx
  HRESULT (__stdcall *GetMetadataQueryReader)(IWICBitmapDecoder *, IWICMetadataQueryReader **); // rbx
  struct IWICBitmapSource *v9; // rcx
  struct IWICBitmapDecoder *v10; // [rsp+40h] [rbp-39h] BYREF
  IStream *ppStream; // [rsp+48h] [rbp-31h] BYREF
  PROPVARIANT pvar; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v13[96]; // [rsp+70h] [rbp-9h] BYREF
  int v14; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v15; // [rsp+E8h] [rbp+6Fh] BYREF
  struct IWICBitmapSource *v16; // [rsp+F0h] [rbp+77h] BYREF
  IMFByteStream *pByteStream; // [rsp+F8h] [rbp+7Fh] BYREF

  v14 = 0;
  pByteStream = 0;
  ppStream = 0;
  v2 = 0;
  v10 = 0;
  v16 = 0;
  v15 = 0;
  v3 = (const unsigned __int16 *)*((_QWORD *)this + 8);
  CByteStreamCreator::CByteStreamCreator((CByteStreamCreator *)v13, &v14);
  ByteStreamFromUrl = v14;
  if ( v14 >= 0 )
  {
    if ( *((_DWORD *)this + 4) >= 0x3E8u
      && (*((_DWORD *)this + 5) = *((_DWORD *)this + 4) < 0x5A0u ? 720 : 1080, *((_QWORD *)this + 9))
      || !v3 )
    {
      v3 = (const unsigned __int16 *)*((_QWORD *)this + 9);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&pByteStream);
    ByteStreamFromUrl = CByteStreamCreator::GetByteStreamFromUrl(
                          (CByteStreamCreator *)v13,
                          v3,
                          v5,
                          0,
                          0xFFFFFFFF,
                          &GUID_ad4c1b00_4bf7_422f_9175_756693d9130d,
                          (void **)&pByteStream);
    if ( ByteStreamFromUrl >= 0 )
    {
      ByteStreamFromUrl = MFCreateStreamOnMFByteStream(pByteStream, &ppStream);
      if ( ByteStreamFromUrl >= 0 )
      {
        ByteStreamFromUrl = CThumbnailRequest::_DecodeThumbnailImage(this, ppStream, &v10);
        v2 = v10;
        if ( ByteStreamFromUrl >= 0 )
        {
          ByteStreamFromUrl = ((__int64 (__fastcall *)(struct IWICBitmapDecoder *, _QWORD, struct IWICBitmapSource **))v10->lpVtbl->GetFrame)(
                                v10,
                                0,
                                &v16);
          if ( ByteStreamFromUrl >= 0 )
          {
            v6 = v16;
            QueryInterface = v16->lpVtbl[1].QueryInterface;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v15);
            if ( ((int (__fastcall *)(struct IWICBitmapSource *, __int64 *))QueryInterface)(v6, &v15) >= 0
              || (GetMetadataQueryReader = v2->lpVtbl->GetMetadataQueryReader,
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v15),
                  ((int (__fastcall *)(struct IWICBitmapDecoder *, __int64 *))GetMetadataQueryReader)(v2, &v15) >= 0) )
            {
              memset(&pvar, 0, sizeof(pvar));
              if ( (*(int (__fastcall **)(__int64, const wchar_t *, PROPVARIANT *))(*(_QWORD *)v15 + 40LL))(
                     v15,
                     L"System.Photo.Orientation",
                     &pvar) >= 0 )
              {
                if ( pvar.vt == 18 )
                  *((_DWORD *)this + 7) = pvar.uiVal;
                PropVariantClear(&pvar);
              }
            }
            ByteStreamFromUrl = CThumbnailRequest::_ResizeRotateAndCreateOutput(this, v16);
          }
        }
      }
    }
  }
  *((_DWORD *)this + 6) = ByteStreamFromUrl;
  CByteStreamCreator::~CByteStreamCreator((CByteStreamCreator *)v13);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v15);
  v9 = v16;
  if ( v16 )
  {
    v16 = 0;
    ((void (__fastcall *)(struct IWICBitmapSource *))v9->lpVtbl->Release)(v9);
  }
  if ( v2 )
    ((void (__fastcall *)(struct IWICBitmapDecoder *))v2->lpVtbl->Release)(v2);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppStream);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&pByteStream);
}

```

## disassembly

```asm
0x18000f40c  push    rbp
0x18000f40e  push    rbx
0x18000f40f  push    rsi
0x18000f410  push    rdi
0x18000f411  push    r14
0x18000f413  lea     rbp, [rsp-37h]
0x18000f418  sub     rsp, 0B0h
0x18000f41f  mov     rsi, rcx
0x18000f422  mov     [rbp+57h+arg_0], 0
0x18000f429  mov     [rbp+57h+pByteStream], 0
0x18000f431  mov     [rbp+57h+ppStream], 0
0x18000f439  xor     r14d, r14d
0x18000f43c  mov     [rbp+57h+var_90], r14
0x18000f440  mov     [rbp+57h+arg_10], r14
0x18000f444  mov     [rbp+57h+arg_8], r14
0x18000f448  mov     rbx, [rcx+40h]
0x18000f44c  lea     rdx, [rbp+57h+arg_0]; int *
0x18000f450  lea     rcx, [rbp+57h+var_60]; this
0x18000f454  call    ??0CByteStreamCreator@@QEAA@PEAJ@Z; CByteStreamCreator::CByteStreamCreator(long *)
0x18000f459  nop
0x18000f45a  mov     eax, [rbp+57h+arg_0]
0x18000f45d  test    eax, eax
0x18000f45f  js      loc_18000F5B9
0x18000f465  cmp     dword ptr [rsi+10h], 3E8h
0x18000f46c  jb      short loc_18000F48A
0x18000f46e  cmp     dword ptr [rsi+10h], 5A0h
0x18000f475  sbb     eax, eax
0x18000f477  and     eax, 0FFFFFE98h
0x18000f47c  add     eax, 438h
0x18000f481  mov     [rsi+14h], eax
0x18000f484  cmp     [rsi+48h], r14
0x18000f488  jnz     short loc_18000F48F
0x18000f48a  test    rbx, rbx
0x18000f48d  jnz     short loc_18000F493
0x18000f48f  mov     rbx, [rsi+48h]
0x18000f493  lea     rcx, [rbp+57h+pByteStream]
0x18000f497  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000f49c  lea     rax, [rbp+57h+pByteStream]
0x18000f4a0  mov     [rsp+0D0h+var_A0], rax; void **
0x18000f4a5  lea     rax, _GUID_ad4c1b00_4bf7_422f_9175_756693d9130d
0x18000f4ac  mov     [rsp+0D0h+riid], rax; riid
0x18000f4b1  mov     [rsp+0D0h+dwTimeout], 0FFFFFFFFh; dwTimeout
0x18000f4b9  xor     r9d, r9d; unsigned __int16 *
0x18000f4bc  mov     rdx, rbx; unsigned __int16 *
0x18000f4bf  lea     rcx, [rbp+57h+var_60]; this
0x18000f4c3  call    ?GetByteStreamFromUrl@CByteStreamCreator@@QEAAJPEBG_N0KAEBU_GUID@@PEAPEAX@Z; CByteStreamCreator::GetByteStreamFromUrl(ushort const *,bool,ushort const *,ulong,_GUID const &,void * *)
0x18000f4c8  test    eax, eax
0x18000f4ca  js      loc_18000F5B9
0x18000f4d0  lea     rdx, [rbp+57h+ppStream]; ppStream
0x18000f4d4  mov     rcx, [rbp+57h+pByteStream]; pByteStream
0x18000f4d8  call    cs:__imp_MFCreateStreamOnMFByteStream
0x18000f4de  test    eax, eax
0x18000f4e0  js      loc_18000F5B9
0x18000f4e6  lea     r8, [rbp+57h+var_90]; struct IWICBitmapDecoder **
0x18000f4ea  mov     rdx, [rbp+57h+ppStream]; struct IStream *
0x18000f4ee  mov     rcx, rsi; this
0x18000f4f1  call    ?_DecodeThumbnailImage@CThumbnailRequest@@AEAAJPEAUIStream@@PEAPEAUIWICBitmapDecoder@@@Z; CThumbnailRequest::_DecodeThumbnailImage(IStream *,IWICBitmapDecoder * *)
0x18000f4f6  mov     r14, [rbp+57h+var_90]
0x18000f4fa  test    eax, eax
0x18000f4fc  js      loc_18000F5B9
0x18000f502  mov     rax, [r14]
0x18000f505  lea     r8, [rbp+57h+arg_10]
0x18000f509  xor     edx, edx
0x18000f50b  mov     rcx, r14
0x18000f50e  mov     rax, [rax+68h]
0x18000f512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f517  test    eax, eax
0x18000f519  js      loc_18000F5B9
0x18000f51f  mov     rdi, [rbp+57h+arg_10]
0x18000f523  mov     rax, [rdi]
0x18000f526  mov     rbx, [rax+40h]
0x18000f52a  lea     rcx, [rbp+57h+arg_8]
0x18000f52e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000f533  lea     rdx, [rbp+57h+arg_8]
0x18000f537  mov     rcx, rdi
0x18000f53a  mov     rax, rbx
0x18000f53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f542  test    eax, eax
0x18000f544  jns     short loc_18000F569
0x18000f546  mov     rax, [r14]
0x18000f549  mov     rbx, [rax+40h]
0x18000f54d  lea     rcx, [rbp+57h+arg_8]
0x18000f551  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000f556  lea     rdx, [rbp+57h+arg_8]
0x18000f55a  mov     rcx, r14
0x18000f55d  mov     rax, rbx
0x18000f560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f565  test    eax, eax
0x18000f567  js      short loc_18000F5AD
0x18000f569  xorps   xmm0, xmm0
0x18000f56c  xor     eax, eax
0x18000f56e  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000f572  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18000f576  mov     rcx, [rbp+57h+arg_8]
0x18000f57a  mov     rax, [rcx]
0x18000f57d  lea     r8, [rbp+57h+pvar]
0x18000f581  lea     rdx, aSystemPhotoOri; "System.Photo.Orientation"
0x18000f588  mov     rax, [rax+28h]
0x18000f58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f591  test    eax, eax
0x18000f593  js      short loc_18000F5AD
0x18000f595  cmp     word ptr [rbp+57h+pvar], 12h
0x18000f59a  jnz     short loc_18000F5A3
0x18000f59c  movzx   eax, word ptr [rbp+57h+pvar+8]
0x18000f5a0  mov     [rsi+1Ch], eax
0x18000f5a3  lea     rcx, [rbp+57h+pvar]; pvar
0x18000f5a7  call    cs:__imp_PropVariantClear
0x18000f5ad  mov     rdx, [rbp+57h+arg_10]; struct IWICBitmapSource *
0x18000f5b1  mov     rcx, rsi; this
0x18000f5b4  call    ?_ResizeRotateAndCreateOutput@CThumbnailRequest@@AEAAJPEAUIWICBitmapSource@@@Z; CThumbnailRequest::_ResizeRotateAndCreateOutput(IWICBitmapSource *)
0x18000f5b9  mov     [rsi+18h], eax
0x18000f5bc  lea     rcx, [rbp+57h+var_60]; this
0x18000f5c0  call    ??1CByteStreamCreator@@UEAA@XZ; CByteStreamCreator::~CByteStreamCreator(void)
0x18000f5c5  nop
0x18000f5c6  lea     rcx, [rbp+57h+arg_8]
0x18000f5ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000f5cf  nop
0x18000f5d0  mov     rcx, [rbp+57h+arg_10]
0x18000f5d4  test    rcx, rcx
0x18000f5d7  jz      short loc_18000F5EE
0x18000f5d9  mov     [rbp+57h+arg_10], 0
0x18000f5e1  mov     rax, [rcx]
0x18000f5e4  mov     rax, [rax+10h]
0x18000f5e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5ed  nop
0x18000f5ee  test    r14, r14
0x18000f5f1  jz      short loc_18000F603
0x18000f5f3  mov     rax, [r14]
0x18000f5f6  mov     rcx, r14
0x18000f5f9  mov     rax, [rax+10h]
0x18000f5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f602  nop
0x18000f603  lea     rcx, [rbp+57h+ppStream]
0x18000f607  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000f60c  nop
0x18000f60d  lea     rcx, [rbp+57h+pByteStream]
0x18000f611  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18000f616  add     rsp, 0B0h
0x18000f61d  pop     r14
0x18000f61f  pop     rdi
0x18000f620  pop     rsi
0x18000f621  pop     rbx
0x18000f622  pop     rbp
0x18000f623  retn
```
