# Windows::Web::UI::Interop::WebViewControlProcessOptions::~WebViewControlProcessOptions(void)

- ea: `0x18004eaa8`
- end: `0x18004eb14`
- name: `??1WebViewControlProcessOptions@Interop@UI@Web@Windows@@EEAA@XZ`
- size: `108`
- prototype: `void __fastcall(Windows::Web::UI::Interop::WebViewControlProcessOptions *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004eb20`

## callees

- `0x1800159a0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ead5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eaf9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ead5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eae7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004eaf9`

## pseudocode

```c
void __fastcall Windows::Web::UI::Interop::WebViewControlProcessOptions::~WebViewControlProcessOptions(
        Windows::Web::UI::Interop::WebViewControlProcessOptions *this)
{
  *(_QWORD *)this = &Windows::Web::UI::Interop::WebViewControlProcessOptions::`vftable';
  *((_QWORD *)this + 1) = &Windows::Web::UI::Interop::WebViewControlProcessOptions::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Web::UI::Interop::WebViewControlProcessOptions::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWebViewControlProcessOptionsInternal>'};
  WindowsDeleteString(*((HSTRING *)this + 8));
  *((_QWORD *)this + 8) = 0;
  WindowsDeleteString(*((HSTRING *)this + 7));
  *((_QWORD *)this + 7) = 0;
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Web::UI::IWebViewControlPermissionRequest,IWebViewControlPermissionRequestInternal>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Web::UI::IWebViewControlPermissionRequest,IWebViewControlPermissionRequestInternal>(this);
}

```

## disassembly

```asm
0x18004eaa8  push    rbx
0x18004eaaa  sub     rsp, 20h
0x18004eaae  lea     rax, ??_7WebViewControlProcessOptions@Interop@UI@Web@Windows@@6B@; const Windows::Web::UI::Interop::WebViewControlProcessOptions::`vftable'
0x18004eab5  mov     rbx, rcx
0x18004eab8  mov     [rcx], rax
0x18004eabb  lea     rax, ??_7WebViewControlProcessOptions@Interop@UI@Web@Windows@@6BIWeakReferenceSource@@@; const Windows::Web::UI::Interop::WebViewControlProcessOptions::`vftable'{for `IWeakReferenceSource'}
0x18004eac2  mov     [rcx+8], rax
0x18004eac6  lea     rax, ??_7WebViewControlProcessOptions@Interop@UI@Web@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWebViewControlProcessOptionsInternal@@@Details@WRL@Microsoft@@@; const Windows::Web::UI::Interop::WebViewControlProcessOptions::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWebViewControlProcessOptionsInternal>'}
0x18004eacd  mov     [rcx+10h], rax
0x18004ead1  mov     rcx, [rcx+40h]; string
0x18004ead5  call    cs:__imp_WindowsDeleteString
0x18004eadb  mov     qword ptr [rbx+40h], 0
0x18004eae3  mov     rcx, [rbx+38h]; string
0x18004eae7  call    cs:__imp_WindowsDeleteString
0x18004eaed  mov     qword ptr [rbx+38h], 0
0x18004eaf5  mov     rcx, [rbx+28h]; string
0x18004eaf9  call    cs:__imp_WindowsDeleteString
0x18004eaff  mov     rcx, rbx
0x18004eb02  mov     qword ptr [rbx+28h], 0
0x18004eb0a  add     rsp, 20h
0x18004eb0e  pop     rbx
0x18004eb0f  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIWebViewControlPermissionRequest@UI@Web@Windows@@UIWebViewControlPermissionRequestInternal@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Web::UI::IWebViewControlPermissionRequest,IWebViewControlPermissionRequestInternal>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Web::UI::IWebViewControlPermissionRequest,IWebViewControlPermissionRequestInternal>(void)
```
