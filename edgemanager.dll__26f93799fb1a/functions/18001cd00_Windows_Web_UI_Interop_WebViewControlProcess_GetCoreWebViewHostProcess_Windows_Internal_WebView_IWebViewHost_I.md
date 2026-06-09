# Windows::Web::UI::Interop::WebViewControlProcess::GetCoreWebViewHostProcess(Windows::Internal::WebView::IWebViewHost *,ICoreWebViewHostProcess * *)

- ea: `0x18001cd00`
- end: `0x18001cf97`
- name: `?GetCoreWebViewHostProcess@WebViewControlProcess@Interop@UI@Web@Windows@@UEAAJPEAUIWebViewHost@WebView@Internal@5@PEAPEAUICoreWebViewHostProcess@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(Windows::Web::UI::Interop::WebViewControlProcess *__hidden this, struct Windows::Internal::WebView::IWebViewHost *, struct ICoreWebViewHostProcess **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180007430`
- `0x18000b0ec`
- `0x1800154cc`
- `0x18001cd00`
- `0x18001d80c`
- `0x180035b88`
- `0x180052370`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cdb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cdb7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001cf5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Web::UI::Interop::WebViewControlProcess::GetCoreWebViewHostProcess(
        Windows::Web::UI::Interop::WebViewControlProcess *this,
        struct Windows::Internal::WebView::IWebViewHost *a2,
        struct ICoreWebViewHostProcess **a3)
{
  int v6; // eax
  int v7; // eax
  FailFastHelpers *v8; // rbx
  _QWORD *v10; // rsi
  __int64 v11; // rdi
  unsigned int (__fastcall *v12)(__int64, HSTRING *); // rbx
  int v13; // edx
  __int64 v14; // rdx
  int v15; // edx
  int v16; // eax
  unsigned __int64 v17; // r9
  unsigned int (__fastcall ***v18)(_QWORD, _QWORD, _QWORD); // rbx
  unsigned int (__fastcall *v19)(_QWORD, GUID *, char *); // rdi
  int v20; // edx
  int v21; // [rsp+20h] [rbp-40h]
  HSTRING string[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  unsigned int v24; // [rsp+90h] [rbp+30h] BYREF
  unsigned int (__fastcall ***v25)(_QWORD, GUID *, char *); // [rsp+A8h] [rbp+48h] BYREF

  v6 = Windows::Web::UI::Interop::WebViewControlProcess::ThreadAffinityGuard((Windows::Web::UI::Interop::WebViewControlProcess *)((char *)this - 16));
  if ( v6 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocess.cpp",
      (const char *)(unsigned int)v6,
      v21);
  v7 = Windows::Web::UI::Interop::WebViewControlProcess::EnsureProcessNotTerminated(this);
  LODWORD(v8) = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x178,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocess.cpp",
      (const char *)(unsigned int)v7,
      v21);
    return (unsigned int)v8;
  }
  v10 = (_QWORD *)((char *)this + 64);
  if ( !*((_QWORD *)this + 8) )
  {
    memset(string, 0, 24);
    v24 = 0;
    v25 = 0;
    v11 = *((_QWORD *)this + 9);
    v12 = *(unsigned int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 56LL);
    WindowsDeleteString(0);
    string[0] = 0;
    v8 = (FailFastHelpers *)v12(v11, string);
    if ( FailFastHelpers::IsRpcDisconnectError(v8, v13) )
    {
      if ( (int)v8 < 0 )
      {
        v14 = 386;
        goto LABEL_24;
      }
    }
    else if ( (int)v8 < 0 )
    {
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x182,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocess.cpp",
        (const char *)(unsigned int)v8,
        v21);
    }
    LODWORD(v8) = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 9) + 72LL))(
                    *((_QWORD *)this + 9),
                    &v24);
    if ( FailFastHelpers::IsRpcDisconnectError((FailFastHelpers *)(unsigned int)v8, v15) )
    {
      if ( (int)v8 < 0 )
      {
        v14 = 387;
        goto LABEL_24;
      }
    }
    else if ( (int)v8 < 0 )
    {
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x183,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocess.cpp",
        (const char *)(unsigned int)v8,
        v21);
    }
    v8 = *(FailFastHelpers **)(*(_QWORD *)a2 + 56LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    v21 = 0;
    v16 = ((__int64 (__fastcall *)(struct Windows::Internal::WebView::IWebViewHost *, HSTRING, _QWORD, _QWORD))v8)(
            a2,
            string[0],
            v24,
            0);
    LODWORD(v8) = v16;
    if ( v16 < 0 )
    {
      v17 = (unsigned int)v16;
      v14 = 393;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocess.cpp",
        (const char *)v17,
        v21);
      WindowsDeleteString(0);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      WindowsDeleteString(0);
      WindowsDeleteString(string[0]);
      return (unsigned int)v8;
    }
    v18 = (unsigned int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v25;
    v19 = **v25;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 64);
    v8 = (FailFastHelpers *)v19(v18, &GUID_bd012f46_3b89_467b_af40_dea6539c1f25, (char *)this + 64);
    if ( !FailFastHelpers::IsRpcDisconnectError(v8, v20) )
    {
      if ( (int)v8 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x18A,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\webviewcontrol\\win32webviewhostprocess.cpp",
          (const char *)(unsigned int)v8,
          0);
      goto LABEL_26;
    }
    if ( (int)v8 >= 0 )
    {
LABEL_26:
      WindowsDeleteString(0);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      WindowsDeleteString(0);
      WindowsDeleteString(string[0]);
      goto LABEL_27;
    }
    v14 = 394;
LABEL_24:
    v17 = (unsigned int)v8;
    goto LABEL_25;
  }
LABEL_27:
  if ( *v10 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  *a3 = (struct ICoreWebViewHostProcess *)*v10;
  return 0;
}

```

## disassembly

```asm
0x18001cd00  mov     [rsp-28h+arg_8], rbx
0x18001cd05  mov     [rsp-28h+arg_10], rsi
0x18001cd0a  push    rbp
0x18001cd0b  push    rdi
0x18001cd0c  push    r12
0x18001cd0e  push    r14
0x18001cd10  push    r15
0x18001cd12  mov     rbp, rsp
0x18001cd15  sub     rsp, 60h
0x18001cd19  mov     r15, r8
0x18001cd1c  mov     r12, rdx
0x18001cd1f  mov     r14, rcx
0x18001cd22  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x18001cd26  call    ?ThreadAffinityGuard@WebViewControlProcess@Interop@UI@Web@Windows@@AEAAJXZ; Windows::Web::UI::Interop::WebViewControlProcess::ThreadAffinityGuard(void)
0x18001cd2b  mov     rcx, [rbp+28h]; this
0x18001cd2f  test    eax, eax
0x18001cd31  jns     short loc_18001CD48
0x18001cd33  mov     r9d, eax; char *
0x18001cd36  lea     r8, aOnecoreuapInet_28; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001cd3d  mov     edx, 177h; void *
0x18001cd42  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001cd48  mov     rcx, r14; this
0x18001cd4b  call    ?EnsureProcessNotTerminated@WebViewControlProcess@Interop@UI@Web@Windows@@UEAAJXZ; Windows::Web::UI::Interop::WebViewControlProcess::EnsureProcessNotTerminated(void)
0x18001cd50  mov     ebx, eax
0x18001cd52  test    eax, eax
0x18001cd54  jns     short loc_18001CD75
0x18001cd56  mov     rcx, [rbp+28h]; this
0x18001cd5a  mov     r9d, eax; char *
0x18001cd5d  lea     r8, aOnecoreuapInet_28; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001cd64  mov     edx, 178h; void *
0x18001cd69  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cd6e  mov     eax, ebx
0x18001cd70  jmp     loc_18001CF7E
0x18001cd75  lea     rsi, [r14+40h]
0x18001cd79  cmp     qword ptr [rsi], 0
0x18001cd7d  jnz     loc_18001CF61
0x18001cd83  mov     [rbp+string], 0
0x18001cd8b  mov     [rbp+arg_0], 0
0x18001cd92  mov     [rbp+var_18], 0
0x18001cd9a  mov     [rbp+arg_18], 0
0x18001cda2  mov     [rbp+var_10], 0
0x18001cdaa  mov     rdi, [r14+48h]
0x18001cdae  mov     rax, [rdi]
0x18001cdb1  mov     rbx, [rax+38h]
0x18001cdb5  xor     ecx, ecx; string
0x18001cdb7  call    cs:__imp_WindowsDeleteString
0x18001cdbd  mov     [rbp+string], 0
0x18001cdc5  lea     rdx, [rbp+string]
0x18001cdc9  mov     rcx, rdi
0x18001cdcc  mov     rax, rbx
0x18001cdcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cdd4  mov     ebx, eax
0x18001cdd6  mov     ecx, eax; this
0x18001cdd8  call    ?IsRpcDisconnectError@FailFastHelpers@@YA_NJ@Z; FailFastHelpers::IsRpcDisconnectError(long)
0x18001cddd  test    al, al
0x18001cddf  jnz     short loc_18001CDFE
0x18001cde1  mov     rcx, [rbp+28h]; this
0x18001cde5  test    ebx, ebx
0x18001cde7  jns     short loc_18001CE0C
0x18001cde9  mov     r9d, ebx; char *
0x18001cdec  lea     r8, aOnecoreuapInet_28; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001cdf3  mov     edx, 182h; void *
0x18001cdf8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001cdfe  test    ebx, ebx
0x18001ce00  jns     short loc_18001CE0C
0x18001ce02  mov     edx, 182h
0x18001ce07  jmp     loc_18001CEFB
0x18001ce0c  mov     rcx, [r14+48h]
0x18001ce10  mov     rax, [rcx]
0x18001ce13  lea     rdx, [rbp+arg_0]
0x18001ce17  mov     rax, [rax+48h]
0x18001ce1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce20  mov     ebx, eax
0x18001ce22  mov     ecx, eax; this
0x18001ce24  call    ?IsRpcDisconnectError@FailFastHelpers@@YA_NJ@Z; FailFastHelpers::IsRpcDisconnectError(long)
0x18001ce29  test    al, al
0x18001ce2b  jnz     short loc_18001CE4A
0x18001ce2d  mov     rcx, [rbp+28h]; this
0x18001ce31  test    ebx, ebx
0x18001ce33  jns     short loc_18001CE58
0x18001ce35  mov     r9d, ebx; char *
0x18001ce38  lea     r8, aOnecoreuapInet_28; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001ce3f  mov     edx, 183h; void *
0x18001ce44  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001ce4a  test    ebx, ebx
0x18001ce4c  jns     short loc_18001CE58
0x18001ce4e  mov     edx, 183h
0x18001ce53  jmp     loc_18001CEFB
0x18001ce58  mov     rax, [r12]
0x18001ce5c  mov     rbx, [rax+38h]
0x18001ce60  lea     rcx, [rbp+arg_18]
0x18001ce64  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001ce69  lea     rax, [rbp+arg_18]
0x18001ce6d  mov     [rsp+60h+var_38], rax
0x18001ce72  mov     qword ptr [rsp+60h+var_40], 0; int
0x18001ce7b  xor     r9d, r9d
0x18001ce7e  mov     r8d, [rbp+arg_0]
0x18001ce82  mov     rdx, [rbp+string]
0x18001ce86  mov     rcx, r12
0x18001ce89  mov     rax, rbx
0x18001ce8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce91  mov     ebx, eax
0x18001ce93  test    eax, eax
0x18001ce95  jns     short loc_18001CEA1
0x18001ce97  mov     r9d, eax
0x18001ce9a  mov     edx, 189h
0x18001ce9f  jmp     short loc_18001CEFE
0x18001cea1  mov     rbx, [rbp+arg_18]
0x18001cea5  mov     rax, [rbx]
0x18001cea8  mov     rdi, [rax]
0x18001ceab  mov     rcx, rsi
0x18001ceae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001ceb3  mov     r8, rsi
0x18001ceb6  lea     rdx, _GUID_bd012f46_3b89_467b_af40_dea6539c1f25
0x18001cebd  mov     rcx, rbx
0x18001cec0  mov     rax, rdi
0x18001cec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cec8  mov     ebx, eax
0x18001ceca  mov     ecx, eax; this
0x18001cecc  call    ?IsRpcDisconnectError@FailFastHelpers@@YA_NJ@Z; FailFastHelpers::IsRpcDisconnectError(long)
0x18001ced1  test    al, al
0x18001ced3  jnz     short loc_18001CEF2
0x18001ced5  mov     rcx, [rbp+28h]; this
0x18001ced9  test    ebx, ebx
0x18001cedb  jns     short loc_18001CF3A
0x18001cedd  mov     r9d, ebx; char *
0x18001cee0  lea     r8, aOnecoreuapInet_28; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001cee7  mov     edx, 18Ah; void *
0x18001ceec  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001cef2  test    ebx, ebx
0x18001cef4  jns     short loc_18001CF3A
0x18001cef6  mov     edx, 18Ah; void *
0x18001cefb  mov     r9d, ebx; char *
0x18001cefe  lea     r8, aOnecoreuapInet_28; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x18001cf05  mov     rcx, [rbp+28h]; this
0x18001cf09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cf0e  nop
0x18001cf0f  xor     ecx, ecx; string
0x18001cf11  call    cs:__imp_WindowsDeleteString
0x18001cf17  nop
0x18001cf18  lea     rcx, [rbp+arg_18]
0x18001cf1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001cf21  nop
0x18001cf22  xor     ecx, ecx; string
0x18001cf24  call    cs:__imp_WindowsDeleteString
0x18001cf2a  nop
0x18001cf2b  mov     rcx, [rbp+string]; string
0x18001cf2f  call    cs:__imp_WindowsDeleteString
0x18001cf35  jmp     loc_18001CD6E
0x18001cf3a  xor     ecx, ecx; string
0x18001cf3c  call    cs:__imp_WindowsDeleteString
0x18001cf42  nop
0x18001cf43  lea     rcx, [rbp+arg_18]
0x18001cf47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001cf4c  nop
0x18001cf4d  xor     ecx, ecx; string
0x18001cf4f  call    cs:__imp_WindowsDeleteString
0x18001cf55  nop
0x18001cf56  mov     rcx, [rbp+string]; string
0x18001cf5a  call    cs:__imp_WindowsDeleteString
0x18001cf60  nop
0x18001cf61  mov     rcx, [rsi]
0x18001cf64  test    rcx, rcx
0x18001cf67  jz      short loc_18001CF76
0x18001cf69  mov     rax, [rcx]
0x18001cf6c  mov     rax, [rax+8]
0x18001cf70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf75  nop
0x18001cf76  mov     rax, [rsi]
0x18001cf79  mov     [r15], rax
0x18001cf7c  xor     eax, eax
0x18001cf7e  lea     r11, [rsp+60h+var_s0]
0x18001cf83  mov     rbx, [r11+38h]
0x18001cf87  mov     rsi, [r11+40h]
0x18001cf8b  mov     rsp, r11
0x18001cf8e  pop     r15
0x18001cf90  pop     r14
0x18001cf92  pop     r12
0x18001cf94  pop     rdi
0x18001cf95  pop     rbp
0x18001cf96  retn
```
