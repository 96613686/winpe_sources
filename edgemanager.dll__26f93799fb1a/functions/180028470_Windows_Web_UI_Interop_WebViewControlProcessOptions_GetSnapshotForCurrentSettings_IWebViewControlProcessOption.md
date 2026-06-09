# Windows::Web::UI::Interop::WebViewControlProcessOptions::GetSnapshotForCurrentSettings(IWebViewControlProcessOptionsInternal * *)

- ea: `0x180028470`
- end: `0x180028597`
- name: `?GetSnapshotForCurrentSettings@WebViewControlProcessOptions@Interop@UI@Web@Windows@@UEAAXPEAPEAUIWebViewControlProcessOptionsInternal@@@Z`
- size: `295`
- prototype: `void __fastcall(Windows::Web::UI::Interop::WebViewControlProcessOptions *__hidden this, struct IWebViewControlProcessOptionsInternal **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180028470`
- `0x1800285a0`
- `0x18002865c`
- `0x180032b90`
- `0x180035b88`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800284a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800284ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002852d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800284a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800284ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002852d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800284da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028519`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028495`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800284da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028519`

## pseudocode

```c
void __fastcall Windows::Web::UI::Interop::WebViewControlProcessOptions::GetSnapshotForCurrentSettings(
        HSTRING *this,
        struct IWebViewControlProcessOptionsInternal **a2)
{
  __int64 v4; // rdi
  HSTRING *v5; // rbx
  HRESULT v6; // eax
  HRESULT v7; // eax
  HRESULT v8; // eax
  int v9; // eax
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  Microsoft::WRL::Details::Make<Windows::Web::UI::Interop::WebViewControlProcessOptions,>(&v12);
  v4 = v12;
  v5 = (HSTRING *)(v12 + 40);
  WindowsDeleteString(*(HSTRING *)(v12 + 40));
  *v5 = 0;
  v6 = WindowsDuplicateString(this[3], v5);
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocesssettings.cpp",
      (const char *)(unsigned int)v6,
      v10);
  *(_DWORD *)(v4 + 48) = *((_DWORD *)this + 8);
  WindowsDeleteString(*(HSTRING *)(v4 + 56));
  *(_QWORD *)(v4 + 56) = 0;
  v7 = WindowsDuplicateString(this[5], (HSTRING *)(v4 + 56));
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x48,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocesssettings.cpp",
      (const char *)(unsigned int)v7,
      v10);
  WindowsDeleteString(*(HSTRING *)(v4 + 64));
  *(_QWORD *)(v4 + 64) = 0;
  v8 = WindowsDuplicateString(this[6], (HSTRING *)(v4 + 64));
  if ( v8 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocesssettings.cpp",
      (const char *)(unsigned int)v8,
      v10);
  v9 = Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Web::UI::Interop::IWebViewControlProcessOptions,IWebViewControlProcessOptionsInternal>>(
         v4,
         &GUID_aab732b8_c158_4dba_b361_86d010c148a9,
         a2);
  if ( v9 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocesssettings.cpp",
      (const char *)(unsigned int)v9,
      v10);
  if ( v4 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Web::UI::Interop::IWebViewControlProcessOptions,IWebViewControlProcessOptionsInternal>::Release(v4);
}

```

## disassembly

```asm
0x180028470  push    rbx
0x180028472  push    rbp
0x180028473  push    rsi
0x180028474  push    rdi
0x180028475  sub     rsp, 28h
0x180028479  mov     rsi, rcx
0x18002847c  mov     rbp, rdx
0x18002847f  lea     rcx, [rsp+48h+arg_0]
0x180028484  call    ??$Make@VWebViewControlProcessOptions@Interop@UI@Web@Windows@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWebViewControlProcessOptions@Interop@UI@Web@Windows@@@12@XZ; Microsoft::WRL::Details::Make<Windows::Web::UI::Interop::WebViewControlProcessOptions,>(void)
0x180028489  mov     rdi, [rsp+48h+arg_0]
0x18002848e  lea     rbx, [rdi+28h]
0x180028492  mov     rcx, [rbx]; string
0x180028495  call    cs:__imp_WindowsDeleteString
0x18002849b  mov     qword ptr [rbx], 0
0x1800284a2  mov     rdx, rbx; newString
0x1800284a5  mov     rcx, [rsi+18h]; string
0x1800284a9  call    cs:__imp_WindowsDuplicateString
0x1800284af  test    eax, eax
0x1800284b1  jns     short loc_1800284CD
0x1800284b3  mov     rcx, [rsp+48h]; this
0x1800284b8  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x1800284bf  mov     r9d, eax; char *
0x1800284c2  mov     edx, 46h ; 'F'; void *
0x1800284c7  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800284cd  mov     eax, [rsi+20h]
0x1800284d0  lea     rbx, [rdi+38h]
0x1800284d4  mov     [rdi+30h], eax
0x1800284d7  mov     rcx, [rbx]; string
0x1800284da  call    cs:__imp_WindowsDeleteString
0x1800284e0  mov     qword ptr [rbx], 0
0x1800284e7  mov     rdx, rbx; newString
0x1800284ea  mov     rcx, [rsi+28h]; string
0x1800284ee  call    cs:__imp_WindowsDuplicateString
0x1800284f4  test    eax, eax
0x1800284f6  jns     short loc_180028512
0x1800284f8  mov     rcx, [rsp+48h]; this
0x1800284fd  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180028504  mov     r9d, eax; char *
0x180028507  mov     edx, 48h ; 'H'; void *
0x18002850c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180028512  lea     rbx, [rdi+40h]
0x180028516  mov     rcx, [rbx]; string
0x180028519  call    cs:__imp_WindowsDeleteString
0x18002851f  mov     qword ptr [rbx], 0
0x180028526  mov     rdx, rbx; newString
0x180028529  mov     rcx, [rsi+30h]; string
0x18002852d  call    cs:__imp_WindowsDuplicateString
0x180028533  test    eax, eax
0x180028535  jns     short loc_180028551
0x180028537  mov     rcx, [rsp+48h]; this
0x18002853c  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180028543  mov     r9d, eax; char *
0x180028546  mov     edx, 49h ; 'I'; void *
0x18002854b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180028551  mov     r8, rbp
0x180028554  lea     rdx, _GUID_aab732b8_c158_4dba_b361_86d010c148a9
0x18002855b  mov     rcx, rdi
0x18002855e  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIWebViewControlProcessOptions@Interop@UI@Web@Windows@@UIWebViewControlProcessOptionsInternal@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIWebViewControlProcessOptions@Interop@UI@Web@Windows@@UIWebViewControlProcessOptionsInternal@@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<1>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Web::UI::Interop::IWebViewControlProcessOptions,IWebViewControlProcessOptionsInternal>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Web::UI::Interop::IWebViewControlProcessOptions,IWebViewControlProcessOptionsInternal> *,_GUID const &,void * *)
0x180028563  test    eax, eax
0x180028565  jns     short loc_180028581
0x180028567  mov     rcx, [rsp+48h]; this
0x18002856c  lea     r8, aOnecoreuapInet_9; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180028573  mov     r9d, eax; char *
0x180028576  mov     edx, 4Bh ; 'K'; void *
0x18002857b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180028581  test    rdi, rdi
0x180028584  jz      short loc_18002858E
0x180028586  mov     rcx, rdi
0x180028589  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIWebViewControlProcessOptions@Interop@UI@Web@Windows@@UIWebViewControlProcessOptionsInternal@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Web::UI::Interop::IWebViewControlProcessOptions,IWebViewControlProcessOptionsInternal>::Release(void)
0x18002858e  add     rsp, 28h
0x180028592  pop     rdi
0x180028593  pop     rsi
0x180028594  pop     rbp
0x180028595  pop     rbx
0x180028596  retn
```
