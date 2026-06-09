# CMediaServerCollectionChangeListener::~CMediaServerCollectionChangeListener(void)

- ea: `0x1800227c0`
- end: `0x1800228c0`
- name: `??1CMediaServerCollectionChangeListener@@UEAA@XZ`
- size: `256`
- prototype: `void __fastcall(CMediaServerCollectionChangeListener *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800229e0`

## callees

- `0x180001710`
- `0x180003828`
- `0x180006c10`
- `0x1800094d0`
- `0x180009f50`
- `0x18000a150`
- `0x180019b84`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002286f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800228a1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002286f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800228a1`

## pseudocode

```c
void __fastcall CMediaServerCollectionChangeListener::~CMediaServerCollectionChangeListener(
        CMediaServerCollectionChangeListener *this)
{
  char *v2; // rsi
  unsigned int v3; // edx
  CMediaServerCollectionChangeListener::ServerRegistrationState *v4; // rcx
  __int64 v5; // r9
  __int64 StartPosition; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &CMediaServerCollectionChangeListener::`vftable'{for `Windows::Media::Streaming::IConnectionStatusHandler'};
  v2 = (char *)this + 136;
  *((_QWORD *)this + 1) = &CMediaServerCollectionChangeListener::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  StartPosition = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CMediaServerCollectionChangeListener::ServerRegistrationState *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CMediaServerCollectionChangeListener::ServerRegistrationState *>>::GetStartPosition((char *)this + 136);
  while ( StartPosition )
  {
    v4 = *(CMediaServerCollectionChangeListener::ServerRegistrationState **)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CMediaServerCollectionChangeListener::ServerRegistrationState *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CMediaServerCollectionChangeListener::ServerRegistrationState *>>::GetNextValue(
                                                                              v2,
                                                                              &StartPosition);
    if ( v4 )
      CMediaServerCollectionChangeListener::ServerRegistrationState::`scalar deleting destructor'(v4, v3);
  }
  v5 = *((unsigned int *)this + 60);
  if ( (_DWORD)v5
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids, v5);
  }
  *((_QWORD *)this + 31) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 248);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 224);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 208);
  ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CMediaServerCollectionChangeListener::ServerRegistrationState *,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CMediaServerCollectionChangeListener::ServerRegistrationState *>>::RemoveAll(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>((char *)this + 8);
}

```

## disassembly

```asm
0x1800227c0  push    rbx
0x1800227c2  push    rsi
0x1800227c3  push    rdi
0x1800227c4  push    r14
0x1800227c6  sub     rsp, 28h
0x1800227ca  lea     rax, ??_7CMediaServerCollectionChangeListener@@6BIConnectionStatusHandler@Streaming@Media@Windows@@@; const CMediaServerCollectionChangeListener::`vftable'{for `Windows::Media::Streaming::IConnectionStatusHandler'}
0x1800227d1  mov     rdi, rcx
0x1800227d4  mov     [rcx], rax
0x1800227d7  lea     rsi, [rcx+88h]
0x1800227de  lea     rax, ??_7CMediaServerCollectionChangeListener@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const CMediaServerCollectionChangeListener::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800227e5  mov     [rcx+8], rax
0x1800227e9  mov     rcx, rsi
0x1800227ec  call    ?GetStartPosition@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUServerRegistrationState@CMediaServerCollectionChangeListener@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAUServerRegistrationState@CMediaServerCollectionChangeListener@@@2@@ATL@@QEBAPEAU__POSITION@@XZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CMediaServerCollectionChangeListener::ServerRegistrationState *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CMediaServerCollectionChangeListener::ServerRegistrationState *>>::GetStartPosition(void)
0x1800227f1  mov     [rsp+48h+arg_0], rax
0x1800227f6  test    rax, rax
0x1800227f9  jz      short loc_18002281D
0x1800227fb  lea     rdx, [rsp+48h+arg_0]
0x180022800  mov     rcx, rsi
0x180022803  call    ?GetNextValue@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUServerRegistrationState@CMediaServerCollectionChangeListener@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAUServerRegistrationState@CMediaServerCollectionChangeListener@@@2@@ATL@@QEAAAEAPEAUServerRegistrationState@CMediaServerCollectionChangeListener@@AEAPEAU__POSITION@@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CMediaServerCollectionChangeListener::ServerRegistrationState *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CMediaServerCollectionChangeListener::ServerRegistrationState *>>::GetNextValue(__POSITION * &)
0x180022808  mov     rcx, [rax]; this
0x18002280b  test    rcx, rcx
0x18002280e  jz      short loc_180022815
0x180022810  call    ??_GServerRegistrationState@CMediaServerCollectionChangeListener@@QEAAPEAXI@Z; CMediaServerCollectionChangeListener::ServerRegistrationState::`scalar deleting destructor'(uint)
0x180022815  cmp     [rsp+48h+arg_0], 0
0x18002281b  jnz     short loc_1800227FB
0x18002281d  mov     r9d, [rdi+0F0h]
0x180022824  test    r9d, r9d
0x180022827  jz      short loc_18002285D
0x180022829  mov     rcx, cs:WPP_GLOBAL_Control
0x180022830  lea     rax, WPP_GLOBAL_Control
0x180022837  cmp     rcx, rax
0x18002283a  jz      short loc_18002285D
0x18002283c  test    byte ptr [rcx+1Ch], 40h
0x180022840  jz      short loc_18002285D
0x180022842  cmp     byte ptr [rcx+19h], 4
0x180022846  jb      short loc_18002285D
0x180022848  mov     rcx, [rcx+10h]
0x18002284c  lea     r8, WPP_843f9b73b5843d1b8d7c57834cd63f0f_Traceguids
0x180022853  mov     edx, 0Ah
0x180022858  call    WPP_SF_d
0x18002285d  lea     rbx, [rdi+0F8h]
0x180022864  lea     rcx, [rdi+60h]; lpCriticalSection
0x180022868  mov     qword ptr [rbx], 0
0x18002286f  call    cs:__imp_DeleteCriticalSection
0x180022875  mov     rcx, rbx
0x180022878  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002287d  lea     rcx, [rdi+0E0h]
0x180022884  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180022889  lea     rcx, [rdi+0D0h]
0x180022890  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180022895  mov     rcx, rsi
0x180022898  call    ?RemoveAll@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUServerRegistrationState@CMediaServerCollectionChangeListener@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@PEAUServerRegistrationState@CMediaServerCollectionChangeListener@@@2@@ATL@@QEAAXXZ; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CMediaServerCollectionChangeListener::ServerRegistrationState *,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CMediaServerCollectionChangeListener::ServerRegistrationState *>>::RemoveAll(void)
0x18002289d  lea     rcx, [rdi+30h]; lpCriticalSection
0x1800228a1  call    cs:__imp_DeleteCriticalSection
0x1800228a7  lea     rcx, [rdi+8]
0x1800228ab  mov     dword ptr [rdi+2Ch], 0C0000001h
0x1800228b2  add     rsp, 28h
0x1800228b6  pop     r14
0x1800228b8  pop     rdi
0x1800228b9  pop     rsi
0x1800228ba  pop     rbx
0x1800228bb  jmp     ??1?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
```
