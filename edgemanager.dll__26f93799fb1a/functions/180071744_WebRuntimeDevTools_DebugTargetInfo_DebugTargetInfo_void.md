# WebRuntimeDevTools::DebugTargetInfo::~DebugTargetInfo(void)

- ea: `0x180071744`
- end: `0x1800717a2`
- name: `??1DebugTargetInfo@WebRuntimeDevTools@@UEAA@XZ`
- size: `94`
- prototype: `void __fastcall(WebRuntimeDevTools::DebugTargetInfo *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800717b0`

## callees

- `0x180011028`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071763`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071787`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071751`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071763`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180071787`

## pseudocode

```c
void __fastcall WebRuntimeDevTools::DebugTargetInfo::~DebugTargetInfo(HSTRING *this)
{
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
0x180071744  push    rbx
0x180071746  sub     rsp, 20h
0x18007174a  mov     rbx, rcx
0x18007174d  mov     rcx, [rcx+38h]; string
0x180071751  call    cs:__imp_WindowsDeleteString
0x180071757  mov     qword ptr [rbx+38h], 0
0x18007175f  mov     rcx, [rbx+30h]; string
0x180071763  call    cs:__imp_WindowsDeleteString
0x180071769  mov     qword ptr [rbx+30h], 0
0x180071771  mov     rcx, [rbx+28h]; string
0x180071775  call    cs:__imp_WindowsDeleteString
0x18007177b  mov     qword ptr [rbx+28h], 0
0x180071783  mov     rcx, [rbx+20h]; string
0x180071787  call    cs:__imp_WindowsDeleteString
0x18007178d  mov     rcx, rbx
0x180071790  mov     qword ptr [rbx+20h], 0
0x180071798  add     rsp, 20h
0x18007179c  pop     rbx
0x18007179d  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIFrameworkViewSource@Core@ApplicationModel@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::ApplicationModel::Core::IFrameworkViewSource>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::ApplicationModel::Core::IFrameworkViewSource>(void)
```
