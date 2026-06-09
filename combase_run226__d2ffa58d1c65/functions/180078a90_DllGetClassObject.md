# DllGetClassObject

- ea: `0x180078a90`
- end: `0x180078e80`
- name: `DllGetClassObject`
- size: `1008`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801d4b00`
- `0x1801d4ba0`
- `0x1801d4be0`

## callees

- `0x18000b408`
- `0x18003a8bc`
- `0x180078a90`
- `0x180078e88`
- `0x180078ea8`
- `0x180078f64`
- `0x180078fbc`
- `0x180078ff4`
- `0x18019a654`
- `0x18019bc8c`
- `0x18019bff8`
- `0x18019c91c`
- `0x1802135dd`
- `0x180250040`
- `0x180255010`

## import_xrefs

- `RPCRT4!NdrDllGetClassObject` at `0x180078acd`
- `RPCRT4!NdrDllGetClassObject` at `0x180078acd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078bcb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078c3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078d4f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078bcb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078c3f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180078d4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078b29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078b29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078b40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078dd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078e40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078b40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078dd1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078e40`
- `ext-ms-win-com-ole32-l1-1-0!Ole32DllGetClassObject` at `0x180078d30`
- `ext-ms-win-com-ole32-l1-1-0!Ole32DllGetClassObject` at `0x180078d30`
- `ext-ms-win-com-coml2-l1-1-1!Coml2DllGetClassObject` at `0x180078cf0`
- `ext-ms-win-com-coml2-l1-1-1!Coml2DllGetClassObject` at `0x180078cf0`

## string_xrefs

- `0x180078b58`: `onecore\com\combase\winrt\metadatamarshaling\metadatainstance\createinstance.cpp`
- `0x180078dba`: `onecore\com\combase\winrt\metadatamarshaling\metadatainstance\createinstance.cpp`
- `0x180078de6`: `onecore\com\combase\winrt\metadatamarshaling\metadatainstance\createinstance.cpp`
- `0x180078e29`: `onecore\com\combase\winrt\metadatamarshaling\metadatainstance\createinstance.cpp`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  int ClassObject; // ebx
  HRESULT v7; // edi
  int v8; // ebx
  unsigned int i; // ebp
  const _GUID *pclsid; // rdx
  CStdClassFactory *v11; // rax
  __int64 (__fastcall ***v12)(_QWORD, const IID *const, LPVOID *); // rax
  __int64 (__fastcall ***v13)(_QWORD, const IID *const, LPVOID *); // rdi
  CPipePSFactory *v15; // rax
  __int64 (__fastcall ***v16)(_QWORD, const IID *const, LPVOID *); // rax
  __int64 (__fastcall ***v17)(_QWORD, const IID *const, LPVOID *); // r14
  HRESULT v18; // eax
  IMetaDataImport2 *v19; // rcx
  WinRT::Metadata::Marshaling::TypeCache *v20; // rax
  WinRT::Metadata::Marshaling::TypeCache *v21; // rbx
  ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::Allocation_StandardDeleteSelfLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::MixinBase<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer> > > > *ptr; // rcx
  HRESULT v23; // eax
  unsigned int v24; // edx
  IMetaDataImport2 *v25; // rcx
  void (*Release)(void); // rax
  void *retaddr; // [rsp+58h] [rbp+0h]
  Microsoft::WRL::ComPtr<IMetaDataImport2> v28; // [rsp+78h] [rbp+20h] BYREF

  ClassObject = NdrDllGetClassObject(
                  rclsid,
                  riid,
                  ppv,
                  (const ProxyFileInfo **)aProxyFileList,
                  &CLSID_PSOlePrx32,
                  &gPFactory);
  if ( ClassObject >= 0 )
    return ClassObject;
  v7 = -2147024882;
  if ( !memcmp_0(rclsid, &CLSID_PipePSFactory, 0x10u) )
  {
    v15 = (CPipePSFactory *)HeapAlloc(g_hHeap, 0, 0x10u);
    if ( v15 )
    {
      CPipePSFactory::CPipePSFactory(v15);
      v17 = v16;
      if ( v16 )
      {
        ClassObject = (**v16)(v16, riid, ppv);
        Release = (void (*)(void))(*v17)[2];
LABEL_44:
        Release();
        goto LABEL_7;
      }
    }
    *ppv = 0;
LABEL_47:
    ClassObject = -2147024882;
    goto LABEL_7;
  }
  if ( memcmp_0(rclsid, &CLSID_MetadataPSFactory, 0x10u) )
    goto LABEL_8;
  *ppv = 0;
  EnterCriticalSection(&typeCacheLock.cs_);
  if ( spTypeCache.ptr_ )
    goto LABEL_5;
  v20 = (WinRT::Metadata::Marshaling::TypeCache *)HeapAlloc(g_hHeap, 0, 0x48u);
  v21 = v20;
  if ( v20 )
  {
    memset_0(v20, 0, sizeof(WinRT::Metadata::Marshaling::TypeCache));
    WinRT::Metadata::Marshaling::TypeCache::TypeCache(v21);
    if ( v20 )
      _InterlockedIncrement((volatile signed __int32 *)&v20->_cReferences);
  }
  ptr = (ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::Allocation_StandardDeleteSelfLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::MixinBase<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer> > > > *)spTypeCache.ptr_;
  spTypeCache.ptr_ = v20;
  if ( ptr )
  {
    ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::Allocation_StandardDeleteSelfLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::MixinBase<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(ptr);
    v20 = spTypeCache.ptr_;
  }
  if ( !v20 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x36u,
      "onecore\\com\\combase\\winrt\\metadatamarshaling\\metadatainstance\\createinstance.cpp",
      -2147024882);
    LeaveCriticalSection(&typeCacheLock.cs_);
    goto LABEL_47;
  }
  v23 = WinRT::Metadata::Marshaling::TypeCache::Initialize(v20);
  ClassObject = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x37u,
      "onecore\\com\\combase\\winrt\\metadatamarshaling\\metadatainstance\\createinstance.cpp",
      v23);
    LeaveCriticalSection(&typeCacheLock.cs_);
    goto LABEL_7;
  }
LABEL_5:
  LeaveCriticalSection(&typeCacheLock.cs_);
  if ( !IsRoGetMetaDataFilePresent() )
  {
    ClassObject = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x3Au,
      "onecore\\com\\combase\\winrt\\metadatamarshaling\\metadatainstance\\createinstance.cpp",
      -2147467263);
    goto LABEL_7;
  }
  v28.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  v18 = Microsoft::WRL::Details::MakeAndInitialize<WinRT::Metadata::Marshaling::CMetadataProxyStubFactory<WinRT::Metadata::Marshaling::MetadataFormatStringDataSource<WinRT::Metadata::Marshaling::DefaultMetadataFormatStringSourceHelper>>,IPSFactoryBuffer,ObjectLibrary::ReferencedPtr<WinRT::Metadata::Marshaling::TypeCache> &>(
          (IPSFactoryBuffer **)&v28,
          &spTypeCache);
  ClassObject = v18;
  if ( v18 < 0 )
  {
    v24 = 61;
    goto LABEL_42;
  }
  v18 = v28.ptr_->QueryInterface(v28.ptr_, riid, ppv);
  ClassObject = v18;
  if ( v18 < 0 )
  {
    v24 = 62;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v24,
      "onecore\\com\\combase\\winrt\\metadatamarshaling\\metadatainstance\\createinstance.cpp",
      v18);
    v25 = v28.ptr_;
    if ( !v28.ptr_ )
      goto LABEL_7;
    v28.ptr_ = 0;
    Release = (void (*)(void))v25->Release;
    goto LABEL_44;
  }
  v19 = v28.ptr_;
  if ( v28.ptr_ )
  {
    v28.ptr_ = 0;
    v19->Release(v19);
  }
  ClassObject = 0;
LABEL_7:
  if ( ClassObject >= 0 )
    return ClassObject;
LABEL_8:
  v8 = -2147221231;
  for ( i = 0; ; ++i )
  {
    pclsid = gInternalClassObjects[i].pclsid;
    if ( !pclsid )
      break;
    if ( pclsid->Data1 == rclsid->Data1
      && *(_DWORD *)&pclsid->Data2 == *(_DWORD *)&rclsid->Data2
      && *(_DWORD *)pclsid->Data4 == *(_DWORD *)rclsid->Data4
      && *(_DWORD *)&pclsid->Data4[4] == *(_DWORD *)&rclsid->Data4[4] )
    {
      v11 = (CStdClassFactory *)HeapAlloc(g_hHeap, 0, 0x10u);
      if ( !v11 )
        goto LABEL_28;
      v8 = -2147024882;
      CStdClassFactory::CStdClassFactory(v11, i);
      v13 = v12;
      if ( v12 )
      {
        v8 = (**v12)(v12, riid, ppv);
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const IID *const, LPVOID *)))(*v13)[2])(v13);
      }
      break;
    }
  }
  v7 = v8;
  if ( v8 >= 0 )
    return v7;
LABEL_28:
  if ( !IsComl2DllGetClassObjectPresent() || (v7 = Coml2DllGetClassObject(rclsid, riid, ppv), v7 < 0) )
  {
    if ( !memcmp_0(rclsid, &CLSID_ATHostActivator, 0x10u) )
    {
      return -2147221164;
    }
    else if ( IsOle32DllGetClassObjectPresent() )
    {
      return Ole32DllGetClassObject(rclsid, riid, ppv);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180078a90  mov     r11, rsp
0x180078a93  mov     [r11+8], rbx
0x180078a97  mov     [r11+10h], rbp
0x180078a9b  push    rsi
0x180078a9c  push    rdi
0x180078a9d  push    r12
0x180078a9f  push    r14
0x180078aa1  push    r15
0x180078aa3  sub     rsp, 30h
0x180078aa7  lea     rax, gPFactory
0x180078aae  mov     r15, ppv
0x180078ab1  mov     [r11-30h], rax
0x180078ab5  lea     r9, aProxyFileList; pProxyFileList
0x180078abc  lea     rax, CLSID_PSOlePrx32
0x180078ac3  mov     r12, iid
0x180078ac6  mov     [r11-38h], rax
0x180078aca  mov     rsi, clsid
0x180078acd  call    cs:__imp_NdrDllGetClassObject
0x180078ad3  mov     ebx, eax
0x180078ad5  test    eax, eax
0x180078ad7  jns     loc_180078E79
0x180078add  mov     r14d, 10h
0x180078ae3  lea     iid, CLSID_PipePSFactory; Buf2
0x180078aea  mov     r8d, r14d; Size
0x180078aed  mov     clsid, rsi; Buf1
0x180078af0  call    memcmp_0
0x180078af5  mov     edi, 8007000Eh
0x180078afa  mov     r8d, r14d; Size
0x180078afd  test    eax, eax
0x180078aff  jz      loc_180078C36
0x180078b05  lea     iid, CLSID_MetadataPSFactory; Buf2
0x180078b0c  mov     clsid, rsi; Buf1
0x180078b0f  call    memcmp_0
0x180078b14  test    eax, eax
0x180078b16  jnz     short loc_180078B7F
0x180078b18  lea     rbp, ?typeCacheLock@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection typeCacheLock
0x180078b1f  mov     qword ptr [r15], 0
0x180078b26  mov     clsid, rbp; lpCriticalSection
0x180078b29  call    cs:__imp_EnterCriticalSection
0x180078b2f  cmp     cs:?spTypeCache@@3V?$ReferencedPtr@VTypeCache@Marshaling@Metadata@WinRT@@@ObjectLibrary@@A.ptr_, 0; ObjectLibrary::ReferencedPtr<WinRT::Metadata::Marshaling::TypeCache> spTypeCache ...
0x180078b37  jz      loc_180078D3D
0x180078b3d  mov     clsid, rbp; lpCriticalSection
0x180078b40  call    cs:__imp_LeaveCriticalSection
0x180078b46  call    IsRoGetMetaDataFilePresent
0x180078b4b  test    al, al
0x180078b4d  jnz     loc_180078C6A
0x180078b53  mov     clsid, [rsp+58h]; callerReturnAddress
0x180078b58  lea     ppv, aOnecoreComComb_39; "onecore\\com\\combase\\winrt\\metadatam"...
0x180078b5f  mov     ebx, 80004001h
0x180078b64  mov     edx, 3Ah ; ':'; lineNumber
0x180078b69  mov     r9d, ebx; hr
0x180078b6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078b71  test    ebx, ebx
0x180078b73  jns     loc_180078E79
0x180078b79  mov     r14d, 10h
0x180078b7f  mov     ebx, 80040111h
0x180078b84  xor     ebp, ebp
0x180078b86  movsxd  rax, ebp
0x180078b89  lea     iid, gInternalClassObjects
0x180078b90  lea     clsid, [rax+rax*2]
0x180078b94  mov     iid, [iid+clsid*8]
0x180078b98  test    iid, iid
0x180078b9b  jz      short loc_180078C13
0x180078b9d  mov     eax, [rsi]
0x180078b9f  cmp     [iid], eax
0x180078ba1  jz      short loc_180078BA7
0x180078ba3  inc     ebp
0x180078ba5  jmp     short loc_180078B86
0x180078ba7  mov     eax, [rsi+4]
0x180078baa  cmp     [iid+4], eax
0x180078bad  jnz     short loc_180078BA3
0x180078baf  mov     eax, [rsi+8]
0x180078bb2  cmp     [iid+8], eax
0x180078bb5  jnz     short loc_180078BA3
0x180078bb7  mov     eax, [rsi+0Ch]
0x180078bba  cmp     [iid+0Ch], eax
0x180078bbd  jnz     short loc_180078BA3
0x180078bbf  mov     clsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x180078bc6  mov     ppv, r14; dwBytes
0x180078bc9  xor     edx, edx; dwFlags
0x180078bcb  call    cs:__imp_HeapAlloc
0x180078bd1  test    rax, rax
0x180078bd4  jz      loc_180078CDE
0x180078bda  mov     edx, ebp; dwIndex
0x180078bdc  mov     clsid, rax; this
0x180078bdf  mov     ebx, edi
0x180078be1  call    ??0CStdClassFactory@@QEAA@K@Z; CStdClassFactory::CStdClassFactory(ulong)
0x180078be6  mov     rdi, rax
0x180078be9  test    rax, rax
0x180078bec  jz      short loc_180078C13
0x180078bee  mov     clsid, [rax]
0x180078bf1  mov     ppv, r15
0x180078bf4  mov     iid, r12
0x180078bf7  mov     rax, [clsid]
0x180078bfa  mov     clsid, rdi
0x180078bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c02  mov     clsid, [rdi]
0x180078c05  mov     ebx, eax
0x180078c07  mov     rax, [clsid+10h]
0x180078c0b  mov     clsid, rdi
0x180078c0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078c13  mov     edi, ebx
0x180078c15  test    ebx, ebx
0x180078c17  js      loc_180078CDE
0x180078c1d  mov     rbx, [rsp+58h+arg_0]
0x180078c22  mov     eax, edi
0x180078c24  mov     rbp, [rsp+58h+arg_8]
0x180078c29  add     rsp, 30h
0x180078c2d  pop     r15
0x180078c2f  pop     r14
0x180078c31  pop     r12
0x180078c33  pop     rdi
0x180078c34  pop     rsi
0x180078c35  retn
0x180078c36  mov     clsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x180078c3d  xor     edx, edx; dwFlags
0x180078c3f  call    cs:__imp_HeapAlloc
0x180078c45  test    rax, rax
0x180078c48  jz      short loc_180078C5E
0x180078c4a  mov     clsid, rax; this
0x180078c4d  call    ??0CPipePSFactory@@QEAA@XZ; CPipePSFactory::CPipePSFactory(void)
0x180078c52  mov     r14, rax
0x180078c55  test    rax, rax
0x180078c58  jnz     loc_180078E57
0x180078c5e  mov     qword ptr [r15], 0
0x180078c65  jmp     loc_180078E46
0x180078c6a  lea     clsid, [rsp+58h+arg_18]; this
0x180078c6f  mov     [rsp+58h+arg_18.ptr_], 0
0x180078c78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180078c7d  lea     iid, ?spTypeCache@@3V?$ReferencedPtr@VTypeCache@Marshaling@Metadata@WinRT@@@ObjectLibrary@@A; <args_0>
0x180078c84  lea     clsid, [rsp+58h+arg_18]; result
0x180078c89  call    ??$MakeAndInitialize@V?$CMetadataProxyStubFactory@U?$MetadataFormatStringDataSource@UDefaultMetadataFormatStringSourceHelper@Marshaling@Metadata@WinRT@@@Marshaling@Metadata@WinRT@@@Marshaling@Metadata@WinRT@@UIPSFactoryBuffer@@AEAV?$ReferencedPtr@VTypeCache@Marshaling@Metadata@WinRT@@@ObjectLibrary@@@Details@WRL@Microsoft@@YAJPEAPEAUIPSFactoryBuffer@@AEAV?$ReferencedPtr@VTypeCache@Marshaling@Metadata@WinRT@@@ObjectLibrary@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WinRT::Metadata::Marshaling::CMetadataProxyStubFactory<WinRT::Metadata::Marshaling::MetadataFormatStringDataSource<WinRT::Metadata::Marshaling::DefaultMetadataFormatStringSourceHelper>>,IPSFactoryBuffer,ObjectLibrary::ReferencedPtr<WinRT::Metadata::Marshaling::TypeCache> &>(IPSFactoryBuffer * *,ObjectLibrary::ReferencedPtr<WinRT::Metadata::Marshaling::TypeCache> &)
0x180078c8e  mov     ebx, eax
0x180078c90  test    eax, eax
0x180078c92  js      loc_180078E1D
0x180078c98  mov     clsid, [rsp+58h+arg_18.ptr_]
0x180078c9d  mov     ppv, r15
0x180078ca0  mov     iid, r12
0x180078ca3  mov     rax, [clsid]
0x180078ca6  mov     rax, [rax]
0x180078ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078cae  mov     ebx, eax
0x180078cb0  test    eax, eax
0x180078cb2  js      loc_180078DDC
0x180078cb8  mov     clsid, [rsp+58h+arg_18.ptr_]
0x180078cbd  test    clsid, clsid
0x180078cc0  jz      short loc_180078CD7
0x180078cc2  mov     [rsp+58h+arg_18.ptr_], 0
0x180078ccb  mov     rax, [clsid]
0x180078cce  mov     rax, [rax+10h]
0x180078cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078cd7  xor     ebx, ebx
0x180078cd9  jmp     loc_180078B71
0x180078cde  call    IsComl2DllGetClassObjectPresent
0x180078ce3  test    al, al
0x180078ce5  jz      short loc_180078D00
0x180078ce7  mov     ppv, r15
0x180078cea  mov     iid, r12
0x180078ced  mov     clsid, rsi
0x180078cf0  call    cs:__imp_Coml2DllGetClassObject
0x180078cf6  mov     edi, eax
0x180078cf8  test    eax, eax
0x180078cfa  jns     loc_180078C1D
0x180078d00  mov     ppv, r14; Size
0x180078d03  lea     iid, CLSID_ATHostActivator; Buf2
0x180078d0a  mov     clsid, rsi; Buf1
0x180078d0d  call    memcmp_0
0x180078d12  test    eax, eax
0x180078d14  jz      loc_180078E4D
0x180078d1a  call    IsOle32DllGetClassObjectPresent
0x180078d1f  test    al, al
0x180078d21  jz      loc_180078C1D
0x180078d27  mov     ppv, r15
0x180078d2a  mov     iid, r12
0x180078d2d  mov     clsid, rsi
0x180078d30  call    cs:__imp_Ole32DllGetClassObject
0x180078d36  mov     edi, eax
0x180078d38  jmp     loc_180078C1D
0x180078d3d  mov     clsid, cs:?g_hHeap@@3QEAXEA; hHeap
0x180078d44  mov     r14d, 48h ; 'H'
0x180078d4a  mov     r8d, r14d; dwBytes
0x180078d4d  xor     edx, edx; dwFlags
0x180078d4f  call    cs:__imp_HeapAlloc
0x180078d55  mov     rbx, rax
0x180078d58  test    rax, rax
0x180078d5b  jz      short loc_180078D7B
0x180078d5d  mov     r8d, r14d; Size
0x180078d60  xor     edx, edx; Val
0x180078d62  mov     clsid, rax; void *
0x180078d65  call    memset_0
0x180078d6a  mov     clsid, rbx; this
0x180078d6d  call    ??0TypeCache@Marshaling@Metadata@WinRT@@QEAA@XZ; WinRT::Metadata::Marshaling::TypeCache::TypeCache(void)
0x180078d72  test    rax, rax
0x180078d75  jz      short loc_180078D7B
0x180078d77  lock inc dword ptr [rax+8]
0x180078d7b  mov     clsid, cs:?spTypeCache@@3V?$ReferencedPtr@VTypeCache@Marshaling@Metadata@WinRT@@@ObjectLibrary@@A.ptr_; this
0x180078d82  mov     cs:?spTypeCache@@3V?$ReferencedPtr@VTypeCache@Marshaling@Metadata@WinRT@@@ObjectLibrary@@A.ptr_, rax; ObjectLibrary::ReferencedPtr<WinRT::Metadata::Marshaling::TypeCache> spTypeCache ...
0x180078d89  test    clsid, clsid
0x180078d8c  jz      short loc_180078D9A
0x180078d8e  call    ?Release@?$AddComReferenceCounting_StandardReferenceCountingLayer@VMetadataType@Marshaling@Metadata@WinRT@@V?$AddComReferenceCounting_ReferenceCountLayer@VMetadataType@Marshaling@Metadata@WinRT@@V?$Allocation_StandardDeleteSelfLayer@VMetadataType@Marshaling@Metadata@WinRT@@V?$MixinBase@VMetadataType@Marshaling@Metadata@WinRT@@VMixins_NilBaseForwarderLayer@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@@Details@ObjectLibrary@@QEAAKXZ; ObjectLibrary::Details::AddComReferenceCounting_StandardReferenceCountingLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::AddComReferenceCounting_ReferenceCountLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::Allocation_StandardDeleteSelfLayer<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::MixinBase<WinRT::Metadata::Marshaling::MetadataType,ObjectLibrary::Details::Mixins_NilBaseForwarderLayer>>>>::Release(void)
0x180078d93  mov     rax, cs:?spTypeCache@@3V?$ReferencedPtr@VTypeCache@Marshaling@Metadata@WinRT@@@ObjectLibrary@@A.ptr_; ObjectLibrary::ReferencedPtr<WinRT::Metadata::Marshaling::TypeCache> spTypeCache ...
0x180078d9a  test    rax, rax
0x180078d9d  jz      loc_180078E24
0x180078da3  mov     clsid, rax; this
0x180078da6  call    ?Initialize@TypeCache@Marshaling@Metadata@WinRT@@QEAAJXZ; WinRT::Metadata::Marshaling::TypeCache::Initialize(void)
0x180078dab  mov     ebx, eax
0x180078dad  test    eax, eax
0x180078daf  jns     loc_180078B3D
0x180078db5  mov     clsid, [rsp+58h]; callerReturnAddress
0x180078dba  lea     ppv, aOnecoreComComb_39; "onecore\\com\\combase\\winrt\\metadatam"...
0x180078dc1  mov     r9d, eax; hr
0x180078dc4  mov     edx, 37h ; '7'; lineNumber
0x180078dc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078dce  mov     clsid, rbp; lpCriticalSection
0x180078dd1  call    cs:__imp_LeaveCriticalSection
0x180078dd7  jmp     loc_180078B71
0x180078ddc  mov     edx, 3Eh ; '>'; lineNumber
0x180078de1  mov     clsid, [rsp+58h]; callerReturnAddress
0x180078de6  lea     ppv, aOnecoreComComb_39; "onecore\\com\\combase\\winrt\\metadatam"...
0x180078ded  mov     r9d, eax; hr
0x180078df0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078df5  mov     clsid, [rsp+58h+arg_18.ptr_]
0x180078dfa  test    clsid, clsid
0x180078dfd  jz      loc_180078B71
0x180078e03  mov     [rsp+58h+arg_18.ptr_], 0
0x180078e0c  mov     rax, [clsid]
0x180078e0f  mov     rax, [rax+10h]
0x180078e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e18  jmp     loc_180078B71
0x180078e1d  mov     edx, 3Dh ; '='
0x180078e22  jmp     short loc_180078DE1
0x180078e24  mov     clsid, [rsp+58h]; callerReturnAddress
0x180078e29  lea     ppv, aOnecoreComComb_39; "onecore\\com\\combase\\winrt\\metadatam"...
0x180078e30  mov     r9d, edi; hr
0x180078e33  mov     edx, 36h ; '6'; lineNumber
0x180078e38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078e3d  mov     clsid, rbp; lpCriticalSection
0x180078e40  call    cs:__imp_LeaveCriticalSection
0x180078e46  mov     ebx, edi
0x180078e48  jmp     loc_180078B71
0x180078e4d  mov     edi, 80040154h
0x180078e52  jmp     loc_180078C1D
0x180078e57  mov     clsid, [rax]
0x180078e5a  mov     ppv, r15
0x180078e5d  mov     iid, r12
0x180078e60  mov     rax, [clsid]
0x180078e63  mov     clsid, r14
0x180078e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e6b  mov     clsid, [r14]
0x180078e6e  mov     ebx, eax
0x180078e70  mov     rax, [clsid+10h]
0x180078e74  mov     clsid, r14
0x180078e77  jmp     short loc_180078E13
0x180078e79  mov     edi, ebx
0x180078e7b  jmp     loc_180078C1D
```
