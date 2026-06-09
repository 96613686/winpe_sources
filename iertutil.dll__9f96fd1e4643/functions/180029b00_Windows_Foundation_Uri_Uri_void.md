# Windows::Foundation::Uri::~Uri(void)

- ea: `0x180029b00`
- end: `0x180029c6f`
- name: `??1Uri@Foundation@Windows@@UEAA@XZ`
- size: `367`
- prototype: `void __fastcall(Windows::Foundation::Uri *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180029a10`

## callees

- `0x180026834`
- `0x180029b00`
- `0x18005b910`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029c0f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180029c0f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029ba7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029be8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029c02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029b9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029ba7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029be8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029bf5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029c02`

## pseudocode

```c
void __fastcall Windows::Foundation::Uri::~Uri(Windows::Foundation::Uri *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &Windows::Foundation::Uri::`vftable'{for `Windows::Foundation::IUriRuntimeClass'};
  *((_QWORD *)this + 1) = &Windows::Foundation::Uri::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IUriRuntimeClassWithAbsoluteCanonicalUri,Windows::Foundation::IStringable,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &Windows::Foundation::Uri::`vftable'{for `Windows::Foundation::IUriRuntimeClassWithAbsoluteCanonicalUri'};
  *((_QWORD *)this + 3) = &Windows::Foundation::Uri::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IStringable,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &Windows::Foundation::Uri::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>'};
  *((_QWORD *)this + 5) = &Windows::Foundation::Uri::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  WindowsDeleteString(*((HSTRING *)this + 13));
  WindowsDeleteString(*((HSTRING *)this + 14));
  WindowsDeleteString(*((HSTRING *)this + 15));
  WindowsDeleteString(*((HSTRING *)this + 16));
  WindowsDeleteString(*((HSTRING *)this + 17));
  WindowsDeleteString(*((HSTRING *)this + 18));
  WindowsDeleteString(*((HSTRING *)this + 19));
  WindowsDeleteString(*((HSTRING *)this + 20));
  WindowsDeleteString(*((HSTRING *)this + 21));
  WindowsDeleteString(*((HSTRING *)this + 22));
  WindowsDeleteString(*((HSTRING *)this + 23));
  WindowsDeleteString(*((HSTRING *)this + 24));
  WindowsDeleteString(*((HSTRING *)this + 25));
  WindowsDeleteString(*((HSTRING *)this + 26));
  WindowsDeleteString(*((HSTRING *)this + 27));
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 6);
  v2 = *((_QWORD *)this + 12);
  if ( v2 )
  {
    *((_QWORD *)this + 12) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  v3 = *((_QWORD *)this + 11);
  if ( v3 )
  {
    *((_QWORD *)this + 11) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *((_QWORD *)this + 10);
  if ( v4 < 0 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(2 * v4);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 64);
}

```

## disassembly

```asm
0x180029b00  mov     [rsp+arg_0], rbx
0x180029b05  push    rdi
0x180029b06  sub     rsp, 20h
0x180029b0a  lea     rax, ??_7Uri@Foundation@Windows@@6BIUriRuntimeClass@12@@; const Windows::Foundation::Uri::`vftable'{for `Windows::Foundation::IUriRuntimeClass'}
0x180029b11  mov     rbx, rcx
0x180029b14  mov     [rcx], rax
0x180029b17  lea     rax, ??_7Uri@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIUriRuntimeClassWithAbsoluteCanonicalUri@Foundation@Windows@@UIStringable@67@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Foundation::Uri::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::IUriRuntimeClassWithAbsoluteCanonicalUri,Windows::Foundation::IStringable,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>'}
0x180029b1e  mov     [rcx+8], rax
0x180029b22  lea     rax, ??_7Uri@Foundation@Windows@@6BIUriRuntimeClassWithAbsoluteCanonicalUri@12@@; const Windows::Foundation::Uri::`vftable'{for `Windows::Foundation::IUriRuntimeClassWithAbsoluteCanonicalUri'}
0x180029b29  mov     [rcx+10h], rax
0x180029b2d  lea     rax, ??_7Uri@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIStringable@Foundation@Windows@@U?$CloakedIid@UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const Windows::Foundation::Uri::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::IStringable,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>,Microsoft::WRL::FtmBase>'}
0x180029b34  mov     [rcx+18h], rax
0x180029b38  lea     rax, ??_7Uri@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIValueMarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::Foundation::Uri::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Marshaling::Internal::IValueMarshalByPropertySet>'}
0x180029b3f  mov     [rcx+20h], rax
0x180029b43  lea     rax, ??_7Uri@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Foundation::Uri::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180029b4a  mov     [rcx+28h], rax
0x180029b4e  mov     rcx, [rcx+68h]; string
0x180029b52  call    cs:__imp_WindowsDeleteString
0x180029b58  mov     rcx, [rbx+70h]; string
0x180029b5c  call    cs:__imp_WindowsDeleteString
0x180029b62  mov     rcx, [rbx+78h]; string
0x180029b66  call    cs:__imp_WindowsDeleteString
0x180029b6c  mov     rcx, [rbx+80h]; string
0x180029b73  call    cs:__imp_WindowsDeleteString
0x180029b79  mov     rcx, [rbx+88h]; string
0x180029b80  call    cs:__imp_WindowsDeleteString
0x180029b86  mov     rcx, [rbx+90h]; string
0x180029b8d  call    cs:__imp_WindowsDeleteString
0x180029b93  mov     rcx, [rbx+98h]; string
0x180029b9a  call    cs:__imp_WindowsDeleteString
0x180029ba0  mov     rcx, [rbx+0A0h]; string
0x180029ba7  call    cs:__imp_WindowsDeleteString
0x180029bad  mov     rcx, [rbx+0A8h]; string
0x180029bb4  call    cs:__imp_WindowsDeleteString
0x180029bba  mov     rcx, [rbx+0B0h]; string
0x180029bc1  call    cs:__imp_WindowsDeleteString
0x180029bc7  mov     rcx, [rbx+0B8h]; string
0x180029bce  call    cs:__imp_WindowsDeleteString
0x180029bd4  mov     rcx, [rbx+0C0h]; string
0x180029bdb  call    cs:__imp_WindowsDeleteString
0x180029be1  mov     rcx, [rbx+0C8h]; string
0x180029be8  call    cs:__imp_WindowsDeleteString
0x180029bee  mov     rcx, [rbx+0D0h]; string
0x180029bf5  call    cs:__imp_WindowsDeleteString
0x180029bfb  mov     rcx, [rbx+0D8h]; string
0x180029c02  call    cs:__imp_WindowsDeleteString
0x180029c08  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x180029c0f  call    cs:__imp_DeleteCriticalSection
0x180029c15  mov     rcx, [rbx+60h]
0x180029c19  xor     edi, edi
0x180029c1b  test    rcx, rcx
0x180029c1e  jz      short loc_180029C30
0x180029c20  mov     [rbx+60h], rdi
0x180029c24  mov     rax, [rcx]
0x180029c27  mov     rax, [rax+10h]
0x180029c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c30  mov     rcx, [rbx+58h]
0x180029c34  test    rcx, rcx
0x180029c37  jz      short loc_180029C49
0x180029c39  mov     [rbx+58h], rdi
0x180029c3d  mov     rax, [rcx]
0x180029c40  mov     rax, [rax+10h]
0x180029c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c49  mov     rcx, [rbx+50h]
0x180029c4d  test    rcx, rcx
0x180029c50  js      short loc_180029C65
0x180029c52  lea     rcx, [rbx+40h]
0x180029c56  mov     rbx, [rsp+28h+arg_0]
0x180029c5b  add     rsp, 20h
0x180029c5f  pop     rdi
0x180029c60  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029c65  add     rcx, rcx
0x180029c68  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180029c6d  jmp     short loc_180029C52
```
