# CByteStreamCreator::GetByteStreamFromUrl(ushort const *,bool,ushort const *,ulong,_GUID const &,void * *)

- ea: `0x180010af0`
- end: `0x18001113b`
- name: `?GetByteStreamFromUrl@CByteStreamCreator@@QEAAJPEBG_N0KAEBU_GUID@@PEAPEAX@Z`
- size: `1611`
- prototype: `__int64 __fastcall(CByteStreamCreator *__hidden this, const unsigned __int16 *, bool, const unsigned __int16 *, DWORD dwTimeout, IID *riid, void **)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18000f40c`
- `0x180019298`

## callees

- `0x180001710`
- `0x180005f60`
- `0x180007840`
- `0x180007e00`
- `0x180008430`
- `0x18000a4d0`
- `0x18000ae84`
- `0x18000d990`
- `0x180010af0`
- `0x180011930`
- `0x180014a00`
- `0x180017e84`
- `0x1800198d4`
- `0x180019b84`
- `0x180030134`
- `0x1800301bc`
- `0x1800304a8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180010d8d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180010d8d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010d60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010d60`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180010ce8`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180010ce8`
- `MFPlat!MFCreateStreamOnMFByteStreamEx` at `0x18001112f`
- `MFPlat!MFCreateStreamOnMFByteStreamEx` at `0x18001112f`
- `MFPlat!MFCreateSourceResolver` at `0x180010c2b`
- `MFPlat!MFCreateSourceResolver` at `0x180010c2b`
- `MFPlat!MFStartup` at `0x180010bf7`
- `MFPlat!MFStartup` at `0x180010bf7`
- `api-ms-win-shcore-thread-l1-1-0!SHGetThreadRef` at `0x180010f83`
- `api-ms-win-shcore-thread-l1-1-0!SHGetThreadRef` at `0x180010f83`

## pseudocode

```c
__int64 __fastcall CByteStreamCreator::GetByteStreamFromUrl(
        CByteStreamCreator *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        DWORD dwTimeout,
        IID *riid,
        void **a7)
{
  unsigned int v8; // r14d
  __int64 v9; // rdi
  char *v10; // rax
  _BYTE *v11; // rsi
  __int64 v12; // rcx
  HRESULT v13; // eax
  CByteStreamCreator *v14; // r12
  IMFSourceResolver **v15; // r13
  char *v16; // rax
  __int64 v17; // rcx
  bool v18; // dl
  CByteStreamCreator *v19; // rcx
  IMFSourceResolver *v20; // r14
  _QWORD *v21; // r12
  HRESULT (__stdcall *BeginCreateObjectFromURL)(IMFSourceResolver *, LPCWSTR, DWORD, IPropertyStore *, IUnknown **, IMFAsyncCallback *, IUnknown *); // rbx
  HRESULT v23; // eax
  CByteStreamCreator *v24; // r15
  unsigned int v25; // ebx
  IMFSourceResolver *v27; // r14
  HRESULT (__stdcall *EndCreateObjectFromURL)(IMFSourceResolver *, IMFAsyncResult *, MF_OBJECT_TYPE *, IUnknown **); // rbx
  __int64 (__fastcall ***v29)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v30)(_QWORD, GUID *, __int64 *); // r14
  unsigned __int16 *v31; // rbx
  HSTRING v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 (__fastcall ***v37)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v38)(_QWORD, GUID *, DWORD *); // r14
  HRESULT v39; // [rsp+40h] [rbp-A1h] BYREF
  DWORD dwindex[2]; // [rsp+48h] [rbp-99h] BYREF
  __int64 v41; // [rsp+50h] [rbp-91h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, DWORD *); // [rsp+58h] [rbp-89h] BYREF
  void *ppv; // [rsp+60h] [rbp-81h] BYREF
  IUnknown *ppunk; // [rsp+68h] [rbp-79h] BYREF
  int v45; // [rsp+70h] [rbp-71h] BYREF
  __int64 v46; // [rsp+78h] [rbp-69h] BYREF
  __int64 v47; // [rsp+80h] [rbp-61h] BYREF
  const unsigned __int16 *v48; // [rsp+88h] [rbp-59h]
  void **v49; // [rsp+90h] [rbp-51h]
  CByteStreamCreator *v50; // [rsp+98h] [rbp-49h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+A0h] [rbp-41h] BYREF
  char v52; // [rsp+A8h] [rbp-39h]
  unsigned __int16 *v53; // [rsp+B0h] [rbp-31h]
  char v54; // [rsp+B8h] [rbp-29h] BYREF
  char v55; // [rsp+C0h] [rbp-21h] BYREF
  DlnaUrlHelpers *v56; // [rsp+C8h] [rbp-19h] BYREF

  LOBYTE(a3) = 1;
  v48 = a2;
  v50 = this;
  v53 = a4;
  v49 = a7;
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(
    &lpCriticalSection,
    (char *)this + 24,
    a3);
  v8 = 2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b72d5975d57d3328bd140cddf4326449_Traceguids);
  v9 = 0;
  v39 = 0;
  v41 = 0;
  ppunk = 0;
  *a7 = 0;
  v42 = 0;
  ppv = 0;
  v45 = 2;
  v10 = (char *)Microsoft::WRL::Details::Make<CAutoMF,>(&v46);
  v11 = 0;
  if ( &v54 != v10 )
  {
    v11 = *(_BYTE **)v10;
    *(_QWORD *)v10 = 0;
  }
  v12 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( !v11 )
  {
    v39 = -2147024882;
    goto LABEL_35;
  }
  v13 = 0;
  if ( v11[16] || (v13 = MFStartup(0x20070u, 0), v13 < 0) )
  {
    v39 = v13;
    if ( v13 < 0 )
      goto LABEL_35;
  }
  else
  {
    v11[16] = 1;
    v39 = v13;
  }
  v14 = v50;
  v15 = (IMFSourceResolver **)((char *)v50 + 8);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)v50 + 8);
  v39 = MFCreateSourceResolver(v15);
  if ( v39 >= 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b72d5975d57d3328bd140cddf4326449_Traceguids, a2);
    }
    *(_QWORD *)dwindex = &v39;
    v16 = (char *)Microsoft::WRL::Details::Make<WaitAsyncCallback,long *>(&v47, dwindex);
    if ( &v55 != v16 )
    {
      v9 = *(_QWORD *)v16;
      *(_QWORD *)v16 = 0;
    }
    v17 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    if ( v9 )
    {
      if ( v39 >= 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
        v39 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
        if ( v39 >= 0 )
        {
          v39 = CByteStreamCreator::_PopulateSourceResolverProperties(v19, v18, (struct IPropertyStore *)ppv);
          if ( v39 >= 0 )
          {
            v20 = *v15;
            v21 = (_QWORD *)((char *)v14 + 16);
            BeginCreateObjectFromURL = (*v15)->lpVtbl->BeginCreateObjectFromURL;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v21);
            v39 = ((__int64 (__fastcall *)(IMFSourceResolver *, const unsigned __int16 *, __int64, void *, _QWORD *, __int64, _QWORD))BeginCreateObjectFromURL)(
                    v20,
                    v48,
                    65554,
                    ppv,
                    v21,
                    v9,
                    0);
            if ( v39 >= 0 )
            {
              LeaveCriticalSection(lpCriticalSection);
              v52 = 0;
              dwindex[0] = 0;
              v23 = CoWaitForMultipleHandles(0x18u, dwTimeout, 1u, (LPHANDLE)(v9 + 24), dwindex);
              if ( v23 == -2147417835 )
                v23 = -2147023436;
              v39 = v23;
              ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&lpCriticalSection);
              if ( v39 == -2147023436 )
              {
                if ( *v21 )
                {
                  ((void (__fastcall *)(IMFSourceResolver *))(*v15)->lpVtbl->CancelObjectCreation)(*v15);
                  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v21);
                }
              }
              else
              {
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v21);
                v27 = *v15;
                EndCreateObjectFromURL = (*v15)->lpVtbl->EndCreateObjectFromURL;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
                v39 = ((__int64 (__fastcall *)(IMFSourceResolver *, _QWORD, int *, __int64 (__fastcall ****)(_QWORD, GUID *, DWORD *)))EndCreateObjectFromURL)(
                        v27,
                        *(_QWORD *)(v9 + 16),
                        &v45,
                        &v42);
                if ( v39 >= 0 )
                {
                  v29 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
                  v30 = (__int64 (__fastcall *)(_QWORD, GUID *, __int64 *))**v42;
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v41);
                  v39 = v30(v29, &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3, &v41);
                  if ( v39 >= 0 )
                  {
                    v39 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v41 + 168LL))(
                            v41,
                            MF_BYTESTREAM_PROXY,
                            1);
                    if ( v39 >= 0 )
                    {
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunk);
                      if ( SHGetThreadRef(&ppunk) < 0
                        || (v39 = (*(__int64 (__fastcall **)(__int64, __int64 *, IUnknown *))(*(_QWORD *)v41 + 216LL))(
                                    v41,
                                    MF_PRIVATE_THREAD_REF_COUNT,
                                    ppunk),
                            v39 >= 0) )
                      {
                        v39 = (*(__int64 (__fastcall **)(__int64, __int64 *, _BYTE *))(*(_QWORD *)v41 + 216LL))(
                                v41,
                                MF_PRIVATE_MFSTARTUP,
                                v11);
                        if ( v39 >= 0 )
                        {
                          v39 = (*(__int64 (__fastcall **)(__int64, __int64 *, const unsigned __int16 *))(*(_QWORD *)v41 + 200LL))(
                                  v41,
                                  MF_BYTESTREAM_URL,
                                  v48);
                          if ( v39 >= 0 )
                          {
                            v31 = v53;
                            if ( v53 )
                            {
                              Windows::Internal::StringReference::_ConstructorHelper(
                                (Windows::Internal::StringReference *)&v56,
                                v53);
                              if ( DlnaUrlHelpers::IsDlnaPlaySingleUrl(v56, v32) )
                                (*(void (__fastcall **)(__int64, __int64 *, unsigned __int16 *))(*(_QWORD *)v41 + 200LL))(
                                  v41,
                                  MF_BYTESTREAM_DLNAPLAYSINGLE_URL,
                                  v31);
                            }
                            v33 = *(_QWORD *)&GUID_0000000c_0000_0000_c000_000000000046.Data1 - *(_QWORD *)&riid->Data1;
                            if ( *(_QWORD *)&GUID_0000000c_0000_0000_c000_000000000046.Data1 == *(_QWORD *)&riid->Data1 )
                              v33 = *(_QWORD *)GUID_0000000c_0000_0000_c000_000000000046.Data4 - *(_QWORD *)riid->Data4;
                            if ( !v33 )
                              goto LABEL_72;
                            v34 = *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1 - *(_QWORD *)&riid->Data1;
                            if ( *(_QWORD *)&GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data1 == *(_QWORD *)&riid->Data1 )
                              v34 = *(_QWORD *)GUID_905a0fe1_bc53_11df_8c49_001e4fc686da.Data4 - *(_QWORD *)riid->Data4;
                            if ( !v34 )
                              goto LABEL_72;
                            v35 = *(_QWORD *)&GUID_cc254827_4b3d_438f_9232_10c76bc7e038.Data1 - *(_QWORD *)&riid->Data1;
                            if ( *(_QWORD *)&GUID_cc254827_4b3d_438f_9232_10c76bc7e038.Data1 == *(_QWORD *)&riid->Data1 )
                              v35 = *(_QWORD *)GUID_cc254827_4b3d_438f_9232_10c76bc7e038.Data4 - *(_QWORD *)riid->Data4;
                            if ( !v35 )
                              goto LABEL_72;
                            v36 = *(_QWORD *)&GUID_905a0fe2_bc53_11df_8c49_001e4fc686da.Data1 - *(_QWORD *)&riid->Data1;
                            if ( *(_QWORD *)&GUID_905a0fe2_bc53_11df_8c49_001e4fc686da.Data1 == *(_QWORD *)&riid->Data1 )
                              v36 = *(_QWORD *)GUID_905a0fe2_bc53_11df_8c49_001e4fc686da.Data4 - *(_QWORD *)riid->Data4;
                            if ( v36 )
                            {
                              v39 = Microsoft::WRL::ComPtr<IUnknown>::CopyTo(&v42, riid, v49);
                            }
                            else
                            {
LABEL_72:
                              v37 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
                              *(_QWORD *)dwindex = 0;
                              v38 = **v42;
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(dwindex);
                              v39 = v38(v37, &GUID_ad4c1b00_4bf7_422f_9175_756693d9130d, dwindex);
                              if ( v39 >= 0 )
                                v39 = MFCreateStreamOnMFByteStreamEx(*(IMFByteStream **)dwindex, riid, v49);
                              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(dwindex);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
            v8 = 2;
          }
        }
      }
    }
    else
    {
      v39 = -2147024882;
    }
  }
LABEL_35:
  v24 = v50;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)v50 + 8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)v24 + 16);
  if ( v9 )
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(v9 + 16);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    goto LABEL_43;
  v25 = v39;
  if ( v39 >= 0 )
    v8 = 5;
  if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v8 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_b72d5975d57d3328bd140cddf4326449_Traceguids,
      (unsigned int)v39);
LABEL_43:
    v25 = v39;
  }
  if ( v11 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v11 + 16LL))(v11);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunk);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v41);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&lpCriticalSection);
  return v25;
}

```

## disassembly

```asm
0x180010af0  mov     [rsp-8+arg_10], rbx
0x180010af5  push    rbp
0x180010af6  push    rsi
0x180010af7  push    rdi
0x180010af8  push    r12
0x180010afa  push    r13
0x180010afc  push    r14
0x180010afe  push    r15
0x180010b00  lea     rbp, [rsp-0Fh]
0x180010b05  sub     rsp, 0F0h
0x180010b0c  mov     rax, cs:__security_cookie
0x180010b13  xor     rax, rsp
0x180010b16  mov     [rbp+3Fh+var_38], rax
0x180010b1a  mov     rsi, [rbp+3Fh+arg_30]
0x180010b1e  mov     rbx, rdx
0x180010b21  mov     r15, [rbp+3Fh+riid]
0x180010b25  mov     r8b, 1
0x180010b28  mov     [rbp+3Fh+var_98], rdx
0x180010b2c  lea     rdx, [rcx+18h]
0x180010b30  mov     [rbp+3Fh+var_88], rcx
0x180010b34  lea     rcx, [rbp+3Fh+lpCriticalSection]
0x180010b38  mov     [rbp+3Fh+var_70], r9
0x180010b3c  mov     [rbp+3Fh+var_90], rsi
0x180010b40  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x180010b45  mov     rcx, cs:WPP_GLOBAL_Control
0x180010b4c  lea     r12, WPP_GLOBAL_Control
0x180010b53  mov     r14d, 2
0x180010b59  cmp     rcx, r12
0x180010b5c  jz      short loc_180010B78
0x180010b5e  test    [rcx+1Ch], r14b
0x180010b62  jz      short loc_180010B78
0x180010b64  mov     rcx, [rcx+10h]
0x180010b68  lea     edx, [r14+8]
0x180010b6c  lea     r8, WPP_b72d5975d57d3328bd140cddf4326449_Traceguids
0x180010b73  call    WPP_SF_
0x180010b78  xor     edi, edi
0x180010b7a  mov     [rsp+120h+var_E0], 0
0x180010b82  lea     rcx, [rbp+3Fh+var_A8]
0x180010b86  mov     [rsp+120h+var_D0], rdi
0x180010b8b  mov     [rbp+3Fh+ppunk], rdi
0x180010b8f  mov     [rsi], rdi
0x180010b92  mov     [rsp+120h+var_C8], 0
0x180010b9b  mov     [rsp+120h+ppv], 0
0x180010ba4  mov     [rbp+3Fh+var_B0], r14d
0x180010ba8  call    ??$Make@VCAutoMF@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAutoMF@@@12@XZ; Microsoft::WRL::Details::Make<CAutoMF,>(void)
0x180010bad  lea     rcx, [rbp+3Fh+var_68]
0x180010bb1  xor     esi, esi
0x180010bb3  cmp     rcx, rax
0x180010bb6  jz      short loc_180010BBE
0x180010bb8  mov     rsi, [rax]
0x180010bbb  mov     [rax], rdi
0x180010bbe  mov     rcx, [rbp+3Fh+var_A8]
0x180010bc2  test    rcx, rcx
0x180010bc5  jz      short loc_180010BD7
0x180010bc7  mov     [rbp+3Fh+var_A8], rdi
0x180010bcb  mov     rax, [rcx]
0x180010bce  mov     rax, [rax+10h]
0x180010bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bd7  test    rsi, rsi
0x180010bda  jnz     short loc_180010BE9
0x180010bdc  mov     [rsp+120h+var_E0], 8007000Eh
0x180010be4  jmp     loc_180010DE5
0x180010be9  xor     eax, eax
0x180010beb  cmp     [rsi+10h], al
0x180010bee  jnz     short loc_180010C0B
0x180010bf0  xor     edx, edx; dwFlags
0x180010bf2  mov     ecx, 20070h; Version
0x180010bf7  call    cs:__imp_MFStartup
0x180010bfd  test    eax, eax
0x180010bff  js      short loc_180010C0B
0x180010c01  mov     byte ptr [rsi+10h], 1
0x180010c05  mov     [rsp+120h+var_E0], eax
0x180010c09  jmp     short loc_180010C17
0x180010c0b  mov     [rsp+120h+var_E0], eax
0x180010c0f  test    eax, eax
0x180010c11  js      loc_180010DE5
0x180010c17  mov     r12, [rbp+3Fh+var_88]
0x180010c1b  lea     r13, [r12+8]
0x180010c20  mov     rcx, r13
0x180010c23  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010c28  mov     rcx, r13; ppISourceResolver
0x180010c2b  call    cs:__imp_MFCreateSourceResolver
0x180010c31  mov     [rsp+120h+var_E0], eax
0x180010c35  test    eax, eax
0x180010c37  js      loc_180010DDE
0x180010c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c44  lea     rax, WPP_GLOBAL_Control
0x180010c4b  cmp     rcx, rax
0x180010c4e  jz      short loc_180010C74
0x180010c50  test    byte ptr [rcx+1Ch], 40h
0x180010c54  jz      short loc_180010C74
0x180010c56  cmp     byte ptr [rcx+19h], 4
0x180010c5a  jb      short loc_180010C74
0x180010c5c  mov     rcx, [rcx+10h]
0x180010c60  lea     r8, WPP_b72d5975d57d3328bd140cddf4326449_Traceguids
0x180010c67  mov     edx, 0Bh
0x180010c6c  mov     r9, rbx
0x180010c6f  call    WPP_SF_S
0x180010c74  lea     rax, [rsp+120h+var_E0]
0x180010c79  lea     rdx, [rsp+120h+dwindex]
0x180010c7e  mov     qword ptr [rsp+120h+dwindex], rax
0x180010c83  lea     rcx, [rbp+3Fh+var_A0]
0x180010c87  call    ??$Make@VWaitAsyncCallback@@PEAJ@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWaitAsyncCallback@@@12@$$QEAPEAJ@Z; Microsoft::WRL::Details::Make<WaitAsyncCallback,long *>(long * &&)
0x180010c8c  lea     rcx, [rbp+3Fh+var_60]
0x180010c90  xor     ebx, ebx
0x180010c92  cmp     rcx, rax
0x180010c95  jz      short loc_180010C9D
0x180010c97  mov     rdi, [rax]
0x180010c9a  mov     [rax], rbx
0x180010c9d  mov     rcx, [rbp+3Fh+var_A0]
0x180010ca1  test    rcx, rcx
0x180010ca4  jz      short loc_180010CB6
0x180010ca6  mov     [rbp+3Fh+var_A0], rbx
0x180010caa  mov     rax, [rcx]
0x180010cad  mov     rax, [rax+10h]
0x180010cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cb6  test    rdi, rdi
0x180010cb9  jnz     short loc_180010CC8
0x180010cbb  mov     [rsp+120h+var_E0], 8007000Eh
0x180010cc3  jmp     loc_180010DDE
0x180010cc8  cmp     [rsp+120h+var_E0], ebx
0x180010ccc  jl      loc_180010DDE
0x180010cd2  lea     rcx, [rsp+120h+ppv]
0x180010cd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010cdc  lea     rdx, [rsp+120h+ppv]; ppv
0x180010ce1  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180010ce8  call    cs:__imp_PSCreateMemoryPropertyStore
0x180010cee  mov     [rsp+120h+var_E0], eax
0x180010cf2  test    eax, eax
0x180010cf4  js      loc_180010DDE
0x180010cfa  mov     r8, [rsp+120h+ppv]; struct IPropertyStore *
0x180010cff  call    ?_PopulateSourceResolverProperties@CByteStreamCreator@@AEAAJ_NPEAUIPropertyStore@@@Z; CByteStreamCreator::_PopulateSourceResolverProperties(bool,IPropertyStore *)
0x180010d04  mov     [rsp+120h+var_E0], eax
0x180010d08  test    eax, eax
0x180010d0a  js      loc_180010DDE
0x180010d10  mov     r14, [r13+0]
0x180010d14  add     r12, 10h
0x180010d18  mov     rcx, r12
0x180010d1b  mov     rax, [r14]
0x180010d1e  mov     rbx, [rax+28h]
0x180010d22  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010d27  mov     r9, [rsp+120h+ppv]
0x180010d2c  mov     r8d, 10012h
0x180010d32  mov     rdx, [rbp+3Fh+var_98]
0x180010d36  mov     rcx, r14
0x180010d39  mov     [rsp+120h+var_F0], 0
0x180010d42  mov     rax, rbx
0x180010d45  mov     [rsp+120h+var_F8], rdi
0x180010d4a  mov     [rsp+120h+lpdwindex], r12
0x180010d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d54  mov     [rsp+120h+var_E0], eax
0x180010d58  test    eax, eax
0x180010d5a  js      short loc_180010DD8
0x180010d5c  mov     rcx, [rbp+3Fh+lpCriticalSection]; lpCriticalSection
0x180010d60  call    cs:__imp_LeaveCriticalSection
0x180010d66  mov     edx, [rbp+3Fh+dwTimeout]; dwTimeout
0x180010d69  lea     rax, [rsp+120h+dwindex]
0x180010d6e  mov     r8d, 1; cHandles
0x180010d74  mov     [rbp+3Fh+var_78], 0
0x180010d78  lea     r9, [rdi+18h]; pHandles
0x180010d7c  mov     [rsp+120h+dwindex], 0
0x180010d84  mov     [rsp+120h+lpdwindex], rax; lpdwindex
0x180010d89  lea     ecx, [r8+17h]; dwFlags
0x180010d8d  call    cs:__imp_CoWaitForMultipleHandles
0x180010d93  mov     ebx, 800705B4h
0x180010d98  lea     rcx, [rbp+3Fh+lpCriticalSection]
0x180010d9c  cmp     eax, 80010115h
0x180010da1  cmovz   eax, ebx
0x180010da4  mov     [rsp+120h+var_E0], eax
0x180010da8  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180010dad  cmp     [rsp+120h+var_E0], ebx
0x180010db1  jnz     loc_180010ED0
0x180010db7  mov     rdx, [r12]
0x180010dbb  test    rdx, rdx
0x180010dbe  jz      short loc_180010DD8
0x180010dc0  mov     rcx, [r13+0]
0x180010dc4  mov     rax, [rcx]
0x180010dc7  mov     rax, [rax+48h]
0x180010dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dd0  mov     rcx, r12
0x180010dd3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010dd8  mov     r14d, 2
0x180010dde  lea     r12, WPP_GLOBAL_Control
0x180010de5  mov     r15, [rbp+3Fh+var_88]
0x180010de9  lea     rcx, [r15+8]
0x180010ded  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010df2  lea     rcx, [r15+10h]
0x180010df6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010dfb  test    rdi, rdi
0x180010dfe  jz      short loc_180010E09
0x180010e00  lea     rcx, [rdi+10h]
0x180010e04  call    ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
0x180010e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e10  cmp     rcx, r12
0x180010e13  jz      short loc_180010E4B
0x180010e15  test    [rcx+1Ch], r14b
0x180010e19  jz      short loc_180010E4B
0x180010e1b  mov     ebx, [rsp+120h+var_E0]
0x180010e1f  mov     eax, 5
0x180010e24  test    ebx, ebx
0x180010e26  cmovns  r14d, eax
0x180010e2a  movzx   eax, byte ptr [rcx+19h]
0x180010e2e  cmp     eax, r14d
0x180010e31  jb      short loc_180010E4F
0x180010e33  mov     rcx, [rcx+10h]
0x180010e37  lea     r8, WPP_b72d5975d57d3328bd140cddf4326449_Traceguids
0x180010e3e  mov     edx, 0Ch
0x180010e43  mov     r9d, ebx
0x180010e46  call    WPP_SF_d
0x180010e4b  mov     ebx, [rsp+120h+var_E0]
0x180010e4f  test    rsi, rsi
0x180010e52  jz      short loc_180010E63
0x180010e54  mov     rax, [rsi]
0x180010e57  mov     rcx, rsi
0x180010e5a  mov     rax, [rax+10h]
0x180010e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e63  lea     rcx, [rbp+3Fh+ppunk]
0x180010e67  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010e6c  lea     rcx, [rsp+120h+var_D0]
0x180010e71  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010e76  test    rdi, rdi
0x180010e79  jz      short loc_180010E8A
0x180010e7b  mov     rcx, [rdi]
0x180010e7e  mov     rax, [rcx+10h]
0x180010e82  mov     rcx, rdi
0x180010e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e8a  lea     rcx, [rsp+120h+ppv]
0x180010e8f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010e94  lea     rcx, [rsp+120h+var_C8]
0x180010e99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010e9e  lea     rcx, [rbp+3Fh+lpCriticalSection]
0x180010ea2  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180010ea7  mov     eax, ebx
0x180010ea9  mov     rcx, [rbp+3Fh+var_38]
0x180010ead  xor     rcx, rsp; StackCookie
0x180010eb0  call    __security_check_cookie
0x180010eb5  mov     rbx, [rsp+120h+arg_10]
0x180010ebd  add     rsp, 0F0h
0x180010ec4  pop     r15
0x180010ec6  pop     r14
0x180010ec8  pop     r13
0x180010eca  pop     r12
0x180010ecc  pop     rdi
0x180010ecd  pop     rsi
0x180010ece  pop     rbp
0x180010ecf  retn
0x180010ed0  mov     rcx, r12
0x180010ed3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010ed8  mov     r14, [r13+0]
0x180010edc  lea     rcx, [rsp+120h+var_C8]
0x180010ee1  mov     rax, [r14]
0x180010ee4  mov     rbx, [rax+30h]
0x180010ee8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010eed  mov     rdx, [rdi+10h]
0x180010ef1  lea     r9, [rsp+120h+var_C8]
0x180010ef6  lea     r8, [rbp+3Fh+var_B0]
0x180010efa  mov     rcx, r14
0x180010efd  mov     rax, rbx
0x180010f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f05  mov     [rsp+120h+var_E0], eax
0x180010f09  test    eax, eax
0x180010f0b  js      loc_180010DD8
0x180010f11  mov     rbx, [rsp+120h+var_C8]
0x180010f16  lea     rcx, [rsp+120h+var_D0]
0x180010f1b  mov     rax, [rbx]
0x180010f1e  mov     r14, [rax]
0x180010f21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180010f26  lea     r8, [rsp+120h+var_D0]
0x180010f2b  mov     rcx, rbx
0x180010f2e  lea     rdx, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x180010f35  mov     rax, r14
0x180010f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f3d  mov     [rsp+120h+var_E0], eax
0x180010f41  test    eax, eax
0x180010f43  js      loc_180010DD8
0x180010f49  mov     rcx, [rsp+120h+var_D0]
0x180010f4e  lea     rdx, MF_BYTESTREAM_PROXY
0x180010f55  mov     r8d, 1
0x180010f5b  mov     rax, [rcx]
0x180010f5e  mov     rax, [rax+0A8h]
0x180010f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f6a  mov     [rsp+120h+var_E0], eax
0x180010f6e  test    eax, eax
0x180010f70  js      loc_180010DD8
0x180010f76  lea     rcx, [rbp+3Fh+ppunk]
0x180010f7a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180010f7f  lea     rcx, [rbp+3Fh+ppunk]; ppunk
0x180010f83  call    cs:__imp_SHGetThreadRef
0x180010f89  test    eax, eax
0x180010f8b  js      short loc_180010FB8
0x180010f8d  mov     rcx, [rsp+120h+var_D0]
0x180010f92  lea     rdx, MF_PRIVATE_THREAD_REF_COUNT
0x180010f99  mov     r8, [rbp+3Fh+ppunk]
0x180010f9d  mov     rax, [rcx]
0x180010fa0  mov     rax, [rax+0D8h]
0x180010fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fac  mov     [rsp+120h+var_E0], eax
0x180010fb0  test    eax, eax
0x180010fb2  js      loc_180010DD8
0x180010fb8  mov     rcx, [rsp+120h+var_D0]
  ... truncated ...
```
