# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureAccess::RequestAccessAsync(winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind)

- ea: `0x18001bedc`
- end: `0x18001bf80`
- name: `?RequestAccessAsync@GraphicsCaptureAccess@implementation@Capture@Graphics@Windows@winrt@@SA?AU?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@56@W4GraphicsCaptureAccessKind@3456@@Z`
- size: `164`
- prototype: `__int64 __fastcall(winrt::Windows::Foundation::IUnknown *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800055a0`

## callees

- `0x180001f78`
- `0x180002158`
- `0x180003580`
- `0x180012588`
- `0x18001b8a4`
- `0x18001bc90`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
winrt::Windows::Foundation::IUnknown *__fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureAccess::RequestAccessAsync(
        winrt::Windows::Foundation::IUnknown *this,
        int a2)
{
  _DWORD *v4; // rax
  __int64 v5; // rdi
  __int64 v7; // [rsp+68h] [rbp+20h] BYREF

  v4 = operator new(0xE0u);
  v5 = (__int64)(v4 + 28);
  v4[53] = a2;
  *((_QWORD *)v4 + 14) = winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureAccess::RequestAccessAsync__ResumeCoro_1;
  v4[30] = 65538;
  memset_0(v4, 0, 0x70u);
  std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type::promise_type(v5 - 112);
  *(_QWORD *)this = v5 - 96;
  winrt::Windows::Foundation::IUnknown::add_ref(this);
  v7 = 0;
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v7);
  *(_BYTE *)(v5 + 96) = 0;
  winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureAccess::RequestAccessAsync__ResumeCoro_1(v5);
  return this;
}

```

## disassembly

```asm
0x18001bedc  mov     [rsp+arg_8], rbx
0x18001bee1  mov     [rsp+arg_0], rcx
0x18001bee6  push    rbp
0x18001bee7  push    rsi
0x18001bee8  push    rdi
0x18001bee9  sub     rsp, 30h
0x18001beed  mov     ebx, edx
0x18001beef  mov     rsi, rcx
0x18001bef2  mov     ebp, 60h ; '`'
0x18001bef7  lea     rcx, [rbp+80h]; Size
0x18001befe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bf03  mov     [rsp+48h+arg_10], rax
0x18001bf08  lea     r8d, [rbp+10h]; Size
0x18001bf0c  lea     rdi, [r8+rax]
0x18001bf10  mov     [rsp+48h+arg_10], rdi
0x18001bf15  mov     [rdi+rbp+4], ebx
0x18001bf19  lea     rax, winrt__Windows__Graphics__Capture__implementation__GraphicsCaptureAccess__RequestAccessAsync$_ResumeCoro$1
0x18001bf20  mov     [rdi], rax
0x18001bf23  mov     dword ptr [rdi+8], 10002h
0x18001bf2a  xor     edx, edx; Val
0x18001bf2c  lea     rcx, [rdi-70h]; void *
0x18001bf30  call    memset_0
0x18001bf35  lea     rcx, [rdi-70h]
0x18001bf39  call    ??0promise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@QEAA@XZ; std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type::promise_type(void)
0x18001bf3e  nop
0x18001bf3f  lea     rax, [rdi-60h]
0x18001bf43  mov     [rsi], rax
0x18001bf46  mov     rcx, rsi; this
0x18001bf49  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x18001bf4e  mov     [rsp+48h+arg_18], 0
0x18001bf57  lea     rcx, [rsp+48h+arg_18]
0x18001bf5c  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001bf61  nop
0x18001bf62  xor     eax, eax
0x18001bf64  mov     [rdi+rbp], al
0x18001bf67  mov     rcx, rdi
0x18001bf6a  call    winrt__Windows__Graphics__Capture__implementation__GraphicsCaptureAccess__RequestAccessAsync$_ResumeCoro$1
0x18001bf6f  nop
0x18001bf70  mov     rax, rsi
0x18001bf73  mov     rbx, [rsp+48h+arg_8]
0x18001bf78  add     rsp, 30h
0x18001bf7c  pop     rdi
0x18001bf7d  pop     rsi
0x18001bf7e  pop     rbp
0x18001bf7f  retn
```
