# WebRuntime::DevToolsProtocolVersion::~DevToolsProtocolVersion(void)

- ea: `0x180071418`
- end: `0x180071488`
- name: `??1DevToolsProtocolVersion@WebRuntime@@UEAA@XZ`
- size: `112`
- prototype: `void __fastcall(WebRuntime::DevToolsProtocolVersion *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180071490`

## callees

- `0x180011028`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071425`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071437`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071449`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007145b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007146d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071425`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071437`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071449`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007145b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007146d`

## pseudocode

```c
void __fastcall WebRuntime::DevToolsProtocolVersion::~DevToolsProtocolVersion(HSTRING *this)
{
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
  WindowsDeleteString(this[4]);
  this[4] = 0;
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::ApplicationModel::Core::IFrameworkViewSource>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::ApplicationModel::Core::IFrameworkViewSource>(this);
}

```

## disassembly

```asm
0x180071418  push    rbx
0x18007141a  sub     rsp, 20h
0x18007141e  mov     rbx, rcx
0x180071421  mov     rcx, [rcx+40h]; string
0x180071425  call    cs:__imp_WindowsDeleteString
0x18007142b  mov     qword ptr [rbx+40h], 0
0x180071433  mov     rcx, [rbx+38h]; string
0x180071437  call    cs:__imp_WindowsDeleteString
0x18007143d  mov     qword ptr [rbx+38h], 0
0x180071445  mov     rcx, [rbx+30h]; string
0x180071449  call    cs:__imp_WindowsDeleteString
0x18007144f  mov     qword ptr [rbx+30h], 0
0x180071457  mov     rcx, [rbx+28h]; string
0x18007145b  call    cs:__imp_WindowsDeleteString
0x180071461  mov     qword ptr [rbx+28h], 0
0x180071469  mov     rcx, [rbx+20h]; string
0x18007146d  call    cs:__imp_WindowsDeleteString
0x180071473  mov     rcx, rbx
0x180071476  mov     qword ptr [rbx+20h], 0
0x18007147e  add     rsp, 20h
0x180071482  pop     rbx
0x180071483  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIFrameworkViewSource@Core@ApplicationModel@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::ApplicationModel::Core::IFrameworkViewSource>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::ApplicationModel::Core::IFrameworkViewSource>(void)
```
