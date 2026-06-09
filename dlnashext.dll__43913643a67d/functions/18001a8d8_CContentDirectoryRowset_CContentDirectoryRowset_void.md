# CContentDirectoryRowset::~CContentDirectoryRowset(void)

- ea: `0x18001a8d8`
- end: `0x18001a9ae`
- name: `??1CContentDirectoryRowset@@UEAA@XZ`
- size: `214`
- prototype: `void __fastcall(CContentDirectoryRowset *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001aca0`

## callees

- `0x180001710`
- `0x1800097c0`
- `0x18000a724`
- `0x18000ab48`
- `0x180011978`
- `0x18001a810`
- `0x18001c6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a90d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a90d`

## pseudocode

```c
void __fastcall CContentDirectoryRowset::~CContentDirectoryRowset(CContentDirectoryRowset *this)
{
  *(_QWORD *)this = &CContentDirectoryRowset::`vftable'{for `IRowsetInfo'};
  *((_QWORD *)this + 1) = &CContentDirectoryRowset::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IGetRow,Microsoft::WRL::MixIn<CContentDirectoryRowset,CRowsetNotImpl,1>>'};
  *((_QWORD *)this + 3) = &CContentDirectoryRowset::`vftable';
  CContentDirectoryRowset::_CancelReuqest(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 304));
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 416);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 408);
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>::~ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>((char *)this + 400);
  Windows::Internal::String::~String((CContentDirectoryRowset *)((char *)this + 392));
  CCdsItemSorterAndPropertyMapper::~CCdsItemSorterAndPropertyMapper((CContentDirectoryRowset *)((char *)this + 352));
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>::~ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,unsigned int>>((char *)this + 344);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 296);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 288);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((char *)this + 272);
  `eh vector destructor iterator'(
    (char *)this + 72,
    0x28u,
    5u,
    (void (*)(void *))CContentDirectoryRowset::CACHED_RESULT_PAGE::~CACHED_RESULT_PAGE);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease((char *)this + 64);
  *((_DWORD *)this + 5) = -1073741823;
}

```

## disassembly

```asm
0x18001a8d8  push    rbx
0x18001a8da  sub     rsp, 20h
0x18001a8de  mov     rbx, rcx
0x18001a8e1  lea     rax, ??_7CContentDirectoryRowset@@6BIRowsetInfo@@@; const CContentDirectoryRowset::`vftable'{for `IRowsetInfo'}
0x18001a8e8  mov     [rcx], rax
0x18001a8eb  lea     rax, ??_7CContentDirectoryRowset@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIGetRow@@U?$MixIn@VCContentDirectoryRowset@@VCRowsetNotImpl@@$00@23@@Details@WRL@Microsoft@@@; const CContentDirectoryRowset::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IGetRow,Microsoft::WRL::MixIn<CContentDirectoryRowset,CRowsetNotImpl,1>>'}
0x18001a8f2  mov     [rcx+8], rax
0x18001a8f6  lea     rax, ??_7CContentDirectoryRowset@@6B@; const CContentDirectoryRowset::`vftable'
0x18001a8fd  mov     [rcx+18h], rax
0x18001a901  call    ?_CancelReuqest@CContentDirectoryRowset@@AEAAJXZ; CContentDirectoryRowset::_CancelReuqest(void)
0x18001a906  lea     rcx, [rbx+130h]; lpCriticalSection
0x18001a90d  call    cs:__imp_DeleteCriticalSection
0x18001a913  lea     rcx, [rbx+1A0h]
0x18001a91a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001a91f  lea     rcx, [rbx+198h]
0x18001a926  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001a92b  lea     rcx, [rbx+190h]
0x18001a932  call    ??1?$ComPtr@U?$IAsyncOperationWithProgress@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>>::~ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>>(void)
0x18001a937  lea     rcx, [rbx+188h]; this
0x18001a93e  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001a943  lea     rcx, [rbx+160h]; this
0x18001a94a  call    ??1CCdsItemSorterAndPropertyMapper@@QEAA@XZ; CCdsItemSorterAndPropertyMapper::~CCdsItemSorterAndPropertyMapper(void)
0x18001a94f  lea     rcx, [rbx+158h]
0x18001a956  call    ??1?$ComPtr@U?$IAsyncOperationWithProgress@PEAUIContentRequest@Internal@Streaming@Media@Windows@@I@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>>::~ComPtr<Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Streaming::Internal::IContentRequest *,uint>>(void)
0x18001a95b  lea     rcx, [rbx+128h]
0x18001a962  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001a967  lea     rcx, [rbx+120h]
0x18001a96e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001a973  lea     rcx, [rbx+110h]
0x18001a97a  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18001a97f  lea     rcx, [rbx+48h]; void *
0x18001a983  lea     r9, ??1CACHED_RESULT_PAGE@CContentDirectoryRowset@@QEAA@XZ; void (*)(void *)
0x18001a98a  mov     edx, 28h ; '('; unsigned __int64
0x18001a98f  lea     r8d, [rdx-23h]; unsigned __int64
0x18001a993  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001a998  lea     rcx, [rbx+40h]
0x18001a99c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001a9a1  mov     dword ptr [rbx+14h], 0C0000001h
0x18001a9a8  add     rsp, 20h
0x18001a9ac  pop     rbx
0x18001a9ad  retn
```
