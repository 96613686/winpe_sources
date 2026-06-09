# winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureAccess::RequestAccessAsync$_ResumeCoro$1

- ea: `0x18001bc90`
- end: `0x18001be60`
- name: `winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureAccess::RequestAccessAsync$_ResumeCoro$1`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18001bedc`

## callees

- `0x18000214c`
- `0x1800022f2`
- `0x180003580`
- `0x1800058c4`
- `0x1800075cc`
- `0x18000fa68`
- `0x180014174`
- `0x1800142f0`
- `0x180014368`
- `0x1800154fc`
- `0x18001b414`
- `0x18001bc90`
- `0x18001be68`
- `0x18001bf88`

## string_xrefs

- `0x18001bd12`: `onecoreuap\windows\dwm\capture\api\lib\graphicscaptureaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureAccess::RequestAccessAsync__ResumeCoro_1(
        __int64 a1)
{
  _WORD *v2; // rsi
  int v3; // ecx
  unsigned int v4; // eax
  int v5; // eax
  __int64 v6; // rax
  const struct winrt::impl::slim_source_location *v7; // rax
  int v8; // [rsp+20h] [rbp-48h]
  _BYTE pExceptionObject[64]; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  LOWORD(v8) = *(_WORD *)(a1 + 8);
  switch ( (__int16)v8 )
  {
    case -1:
    case 1:
    case 3:
      goto LABEL_13;
    case 2:
      v3 = *(_DWORD *)(a1 + 100);
      if ( v3 )
      {
        if ( v3 != 1 )
        {
          v4 = wil::verify_hresult<long>(2147549183LL);
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0xD,
            (unsigned int)"onecoreuap\\windows\\dwm\\capture\\api\\lib\\graphicscaptureaccess.cpp",
            (const char *)v4,
            v8);
        }
        v5 = 0;
      }
      else
      {
        v5 = 1;
      }
      *(_DWORD *)(a1 + 12) = v5;
      v6 = winrt::Windows::Graphics::Capture::Server::CaptureServerAccess::RequestAccessAsync((const enum winrt::Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind *)(a1 + 16));
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        v7 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 64);
        winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v7);
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *(_QWORD *)(a1 + 24) = 0;
      *(_QWORD *)(a1 + 32) = v6;
      *(_QWORD *)(a1 + 40) = 0;
      *(_BYTE *)(a1 + 48) = 1;
      *v2 = 4;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type>(
                              a1 + 24,
                              a1) )
        return;
      goto LABEL_12;
    case 4:
LABEL_12:
      *(_DWORD *)(a1 - 8) = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::await_resume(a1 + 24);
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>(a1 + 24);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(a1 + 16);
      *(_QWORD *)(a1 + 56) = a1 - 112;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::final_suspend_awaiter::await_suspend() )
        goto LABEL_13;
      return;
    case 5:
      winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>(a1 + 24);
      winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(a1 + 16);
LABEL_13:
      winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>(a1 - 112);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112), 0xE0u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18001bc90  mov     [rsp+arg_18], rbx
0x18001bc95  mov     [rsp+arg_0], rcx
0x18001bc9a  push    rsi
0x18001bc9b  push    rdi
0x18001bc9c  push    r14
0x18001bc9e  sub     rsp, 50h
0x18001bca2  mov     rbx, [rsp+68h+arg_0]
0x18001bca7  mov     [rsp+68h+arg_8], rbx
0x18001bcac  lea     rsi, [rbx+8]
0x18001bcb0  mov     [rsp+68h+arg_10], rsi
0x18001bcb8  movzx   eax, word ptr [rsi]
0x18001bcbb  mov     word ptr [rsp+68h+var_48], ax; int
0x18001bcc0  mov     r14d, 1
0x18001bcc6  add     ax, r14w
0x18001bcca  cmp     ax, 6; switch 7 cases
0x18001bcce  ja      def_18001BCE9; jumptable 000000018001BCE9 default case, case 1
0x18001bcd4  movsx   rax, ax
0x18001bcd8  lea     rdx, cs:180000000h
0x18001bcdf  mov     ecx, ds:(jpt_18001BCE9 - 180000000h)[rdx+rax*4]
0x18001bce6  add     rcx, rdx
0x18001bce9  jmp     rcx; switch jump
0x18001bceb  xor     edi, edi; jumptable 000000018001BCE9 case 4
0x18001bced  jmp     loc_18001BE12
0x18001bcf2  mov     ecx, [rbx+64h]; jumptable 000000018001BCE9 case 3
0x18001bcf5  xor     edi, edi
0x18001bcf7  test    ecx, ecx
0x18001bcf9  jz      short loc_18001BD26
0x18001bcfb  cmp     ecx, 1
0x18001bcfe  jz      short loc_18001BD22
0x18001bd00  mov     ecx, 8000FFFFh
0x18001bd05  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001bd0a  mov     r9d, eax; char *
0x18001bd0d  mov     rcx, [rsp+68h]; this
0x18001bd12  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\dwm\\capture\\api"...
0x18001bd19  lea     edx, [rdi+0Dh]; void *
0x18001bd1c  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18001bd22  mov     eax, edi
0x18001bd24  jmp     short loc_18001BD29
0x18001bd26  mov     eax, r14d
0x18001bd29  lea     rdx, [rbx+0Ch]
0x18001bd2d  mov     [rdx], eax
0x18001bd2f  lea     rcx, [rbx+10h]; enum winrt::Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind *
0x18001bd33  call    ?RequestAccessAsync@CaptureServerAccess@Server@Capture@Graphics@Windows@winrt@@SA@AEBW4CaptureServerAccessRequestKind@23456@@Z; winrt::Windows::Graphics::Capture::Server::CaptureServerAccess::RequestAccessAsync(winrt::Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind const &)
0x18001bd38  nop
0x18001bd39  mov     ecx, [rbx-10h]
0x18001bd3c  nop
0x18001bd3d  cmp     ecx, 2
0x18001bd40  jnz     short loc_18001BD69
0x18001bd42  lea     rcx, [rbx+40h]
0x18001bd46  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001bd4b  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001bd4e  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18001bd53  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18001bd58  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001bd5f  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001bd64  call    _CxxThrowException_0
0x18001bd69  lea     rcx, [rbx+18h]
0x18001bd6d  mov     [rcx], rdi
0x18001bd70  mov     [rbx+20h], rax
0x18001bd74  mov     [rbx+28h], rdi
0x18001bd78  mov     [rbx+30h], r14b
0x18001bd7c  mov     eax, 4
0x18001bd81  mov     [rsi], ax
0x18001bd84  mov     rdx, rbx
0x18001bd87  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@@?$await_adapter@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@@experimental@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::await_suspend<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type>(std::experimental::coroutine_handle<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type>)
0x18001bd8c  test    al, al
0x18001bd8e  jz      short loc_18001BDAF
0x18001bd90  jmp     loc_18001BE32
0x18001bd95  lea     rcx, [rbx+18h]; jumptable 000000018001BCE9 case 6
0x18001bd99  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>(void)
0x18001bd9e  nop
0x18001bd9f  lea     rcx, [rbx+10h]
0x18001bda3  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001bda8  nop
0x18001bda9  xor     edi, edi
0x18001bdab  jmp     short loc_18001BE12
0x18001bdad  xor     edi, edi; jumptable 000000018001BCE9 case 5
0x18001bdaf  lea     rcx, [rbx+18h]
0x18001bdb3  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::await_resume(void)
0x18001bdb8  mov     [rbx-8], eax
0x18001bdbb  lea     rcx, [rbx+18h]
0x18001bdbf  call    ??1?$cancellable_awaiter@U?$await_adapter@U?$IAsyncOperation@UCapturableItem@Server@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@@winrt@@QEAA@XZ; winrt::cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>::~cancellable_awaiter<winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::Server::CapturableItem>,1>>(void)
0x18001bdc4  nop
0x18001bdc5  lea     rcx, [rbx+10h]
0x18001bdc9  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18001bdce  nop
0x18001bdcf  mov     rdx, rbx
0x18001bdd2  mov     rax, 0FFFFFFFFFFFFFF90h
0x18001bdd9  jmp     short loc_18001BDF6
0x18001bddb  mov     rdx, [rsp+68h+arg_8]
0x18001bde0  mov     rax, 0FFFFFFFFFFFFFF90h
0x18001bde7  xor     edi, edi
0x18001bde9  mov     rbx, [rsp+68h+arg_0]
0x18001bdee  mov     rsi, [rsp+68h+arg_10]
0x18001bdf6  lea     rcx, [rbx+38h]
0x18001bdfa  add     rax, rdx
0x18001bdfd  mov     [rcx], rax
0x18001be00  xor     eax, eax
0x18001be02  mov     [rsi], ax
0x18001be05  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x18001be0a  test    al, al
0x18001be0c  jz      short loc_18001BE12
0x18001be0e  jmp     short loc_18001BE32
0x18001be10  xor     edi, edi; jumptable 000000018001BCE9 cases 0,2
0x18001be12  lea     rcx, [rbx-70h]
0x18001be16  call    ??1?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@PEAUGraphicsCapturePicker@implementation@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@UGraphicsCaptureItem@Capture@Graphics@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@UEAA@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,winrt::Windows::Graphics::Capture::implementation::GraphicsCapturePicker *>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Graphics::Capture::GraphicsCaptureItem>,void>(void)
0x18001be1b  cmp     [rbx+0Ah], di
0x18001be1f  jz      short loc_18001BE32
0x18001be21  mov     edx, 0E0h; unsigned __int64
0x18001be26  lea     rcx, [rbx-70h]; void *
0x18001be2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001be2f  jmp     short loc_18001BE32
0x18001be31  int     3; Trap to Debugger
0x18001be32  mov     rbx, [rsp+68h+arg_18]
0x18001be3a  add     rsp, 50h
0x18001be3e  pop     r14
0x18001be40  pop     rdi
0x18001be41  pop     rsi
0x18001be42  retn
```
