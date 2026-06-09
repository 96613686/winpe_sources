# Windows::Media::Protection::EMEStoreObjectDllManager::~EMEStoreObjectDllManager(void)

- ea: `0x180154250`
- end: `0x1801542df`
- name: `??1EMEStoreObjectDllManager@Protection@Media@Windows@@UEAA@XZ`
- size: `143`
- prototype: `void __fastcall(Windows::Media::Protection::EMEStoreObjectDllManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801543b0`

## callees

- `0x180004870`
- `0x1800144ac`
- `0x180154198`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801542cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1801542cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154284`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801542a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154284`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180154296`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801542a8`

## pseudocode

```c
void __fastcall Windows::Media::Protection::EMEStoreObjectDllManager::~EMEStoreObjectDllManager(
        Windows::Media::Protection::EMEStoreObjectDllManager *this)
{
  *(_QWORD *)this = &Windows::Media::Protection::EMEStoreObjectDllManager::`vftable'{for `Windows::Media::Protection::IEMEStoreObjectDllManager'};
  *((_QWORD *)this + 1) = &Windows::Media::Protection::EMEStoreObjectDllManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
  WindowsDeleteString(*((HSTRING *)this + 14));
  *((_QWORD *)this + 14) = 0;
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  WindowsDeleteString(*((HSTRING *)this + 12));
  *((_QWORD *)this + 12) = 0;
  WindowsDeleteString(*((HSTRING *)this + 11));
  *((_QWORD *)this + 11) = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)this + 10);
  Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease((char *)this + 72);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Media::Protection::IEMEStoreObjectDllManager>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Media::Protection::IEMEStoreObjectDllManager>(this);
}

```

## disassembly

```asm
0x180154250  push    rbx
0x180154252  sub     rsp, 20h
0x180154256  lea     rax, ??_7EMEStoreObjectDllManager@Protection@Media@Windows@@6BIEMEStoreObjectDllManager@123@@; const Windows::Media::Protection::EMEStoreObjectDllManager::`vftable'{for `Windows::Media::Protection::IEMEStoreObjectDllManager'}
0x18015425d  mov     rbx, rcx
0x180154260  mov     [rcx], rax
0x180154263  lea     rax, ??_7EMEStoreObjectDllManager@Protection@Media@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const Windows::Media::Protection::EMEStoreObjectDllManager::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x18015426a  mov     [rcx+8], rax
0x18015426e  mov     rcx, [rcx+70h]; string
0x180154272  call    cs:__imp_WindowsDeleteString
0x180154278  mov     qword ptr [rbx+70h], 0
0x180154280  mov     rcx, [rbx+68h]; string
0x180154284  call    cs:__imp_WindowsDeleteString
0x18015428a  mov     qword ptr [rbx+68h], 0
0x180154292  mov     rcx, [rbx+60h]; string
0x180154296  call    cs:__imp_WindowsDeleteString
0x18015429c  mov     qword ptr [rbx+60h], 0
0x1801542a4  mov     rcx, [rbx+58h]; string
0x1801542a8  call    cs:__imp_WindowsDeleteString
0x1801542ae  lea     rcx, [rbx+50h]
0x1801542b2  mov     qword ptr [rbx+58h], 0
0x1801542ba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801542bf  lea     rcx, [rbx+48h]
0x1801542c3  call    ?InternalRelease@?$ComPtr@VCMFInprocLifetimeAssociation@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CMFInprocLifetimeAssociation>::InternalRelease(void)
0x1801542c8  lea     rcx, [rbx+20h]; lpCriticalSection
0x1801542cc  call    cs:__imp_DeleteCriticalSection
0x1801542d2  mov     rcx, rbx
0x1801542d5  add     rsp, 20h
0x1801542d9  pop     rbx
0x1801542da  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIEMEStoreObjectDllManager@Protection@Media@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Media::Protection::IEMEStoreObjectDllManager>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Media::Protection::IEMEStoreObjectDllManager>(void)
```
