# CWinRTContentLinkInfo::~CWinRTContentLinkInfo(void)

- ea: `0x1801e3288`
- end: `0x1801e32fb`
- name: `??1CWinRTContentLinkInfo@@UEAA@XZ`
- size: `115`
- prototype: `void __fastcall(CWinRTContentLinkInfo *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801e3450`

## callees

- `0x18006ad18`
- `0x1801e3264`
- `0x1801e3288`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e32af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e32c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e32d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e32af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e32c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801e32d9`

## pseudocode

```c
void __fastcall CWinRTContentLinkInfo::~CWinRTContentLinkInfo(CWinRTContentLinkInfo *this)
{
  HSTRING v2; // rcx
  HSTRING v3; // rcx
  HSTRING v4; // rcx

  *(_QWORD *)this = &CWinRTContentLinkInfo::`vftable'{for `Windows::UI::Text::IContentLinkInfo'};
  *((_QWORD *)this + 1) = &CWinRTContentLinkInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
  v2 = (HSTRING)*((_QWORD *)this + 5);
  if ( v2 )
    WindowsDeleteString(v2);
  v3 = (HSTRING)*((_QWORD *)this + 6);
  if ( v3 )
    WindowsDeleteString(v3);
  v4 = (HSTRING)*((_QWORD *)this + 8);
  if ( v4 )
    WindowsDeleteString(v4);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 56);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Text::IContentLinkInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Text::IContentLinkInfo>(this);
}

```

## disassembly

```asm
0x1801e3288  push    rbx
0x1801e328a  sub     rsp, 20h
0x1801e328e  lea     rax, ??_7CWinRTContentLinkInfo@@6BIContentLinkInfo@Text@UI@Windows@@@; const CWinRTContentLinkInfo::`vftable'{for `Windows::UI::Text::IContentLinkInfo'}
0x1801e3295  mov     rbx, rcx
0x1801e3298  mov     [rcx], rax
0x1801e329b  lea     rax, ??_7CWinRTContentLinkInfo@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const CWinRTContentLinkInfo::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x1801e32a2  mov     [rcx+8], rax
0x1801e32a6  mov     rcx, [rcx+28h]; string
0x1801e32aa  test    rcx, rcx
0x1801e32ad  jz      short loc_1801E32BB
0x1801e32af  call    cs:__imp_WindowsDeleteString
0x1801e32b6  nop     dword ptr [rax+rax+00h]
0x1801e32bb  mov     rcx, [rbx+30h]; string
0x1801e32bf  test    rcx, rcx
0x1801e32c2  jz      short loc_1801E32D0
0x1801e32c4  call    cs:__imp_WindowsDeleteString
0x1801e32cb  nop     dword ptr [rax+rax+00h]
0x1801e32d0  mov     rcx, [rbx+40h]; string
0x1801e32d4  test    rcx, rcx
0x1801e32d7  jz      short loc_1801E32E5
0x1801e32d9  call    cs:__imp_WindowsDeleteString
0x1801e32e0  nop     dword ptr [rax+rax+00h]
0x1801e32e5  lea     rcx, [rbx+38h]
0x1801e32e9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1801e32ee  mov     rcx, rbx
0x1801e32f1  add     rsp, 20h
0x1801e32f5  pop     rbx
0x1801e32f6  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIContentLinkInfo@Text@UI@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Text::IContentLinkInfo>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Text::IContentLinkInfo>(void)
```
