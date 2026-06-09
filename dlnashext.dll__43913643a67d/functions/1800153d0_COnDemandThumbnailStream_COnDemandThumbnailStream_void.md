# COnDemandThumbnailStream::~COnDemandThumbnailStream(void)

- ea: `0x1800153d0`
- end: `0x180015435`
- name: `??1COnDemandThumbnailStream@@MEAA@XZ`
- size: `101`
- prototype: `void __fastcall(COnDemandThumbnailStream *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800155f0`

## callees

- `0x180001710`
- `0x180006c10`
- `0x1800153d0`
- `0x1800173a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800153f6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800153f6`

## pseudocode

```c
void __fastcall COnDemandThumbnailStream::~COnDemandThumbnailStream(COnDemandThumbnailStream *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &COnDemandThumbnailStream::`vftable'{for `IStream'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
  {
    *((_QWORD *)this + 7) = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IThumbnailProvider,IThumbnailStreamProvider>::Release(v2);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 48);
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>((char *)this + 8);
}

```

## disassembly

```asm
0x1800153d0  mov     [rsp+arg_0], rbx
0x1800153d5  push    rdi
0x1800153d6  sub     rsp, 20h
0x1800153da  lea     rax, ??_7COnDemandThumbnailStream@@6BIStream@@@; const COnDemandThumbnailStream::`vftable'{for `IStream'}
0x1800153e1  mov     rbx, rcx
0x1800153e4  mov     [rcx], rax
0x1800153e7  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIStream@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IStream,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800153ee  mov     [rcx+8], rax
0x1800153f2  add     rcx, 40h ; '@'; lpCriticalSection
0x1800153f6  call    cs:__imp_DeleteCriticalSection
0x1800153fc  mov     rcx, [rbx+38h]
0x180015400  test    rcx, rcx
0x180015403  jz      short loc_180015412
0x180015405  mov     qword ptr [rbx+38h], 0
0x18001540d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIThumbnailProvider@@UIThumbnailStreamProvider@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IThumbnailProvider,IThumbnailStreamProvider>::Release(void)
0x180015412  lea     rcx, [rbx+30h]
0x180015416  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001541b  lea     rcx, [rbx+8]
0x18001541f  mov     dword ptr [rbx+2Ch], 0C0000001h
0x180015426  mov     rbx, [rsp+28h+arg_0]
0x18001542b  add     rsp, 20h
0x18001542f  pop     rdi
0x180015430  jmp     ??1?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>::~ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>(void)
```
