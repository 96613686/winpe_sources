# winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::ContentUpdated(IFlipPropertySet *,IUnknown *)

- ea: `0x18000f430`
- end: `0x18000f4b5`
- name: `?ContentUpdated@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@UEAAJPEAUIFlipPropertySet@@PEAUIUnknown@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *__hidden this, struct IFlipPropertySet *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18000b18c`
- `0x18000f430`
- `0x18000f670`
- `0x1800127bc`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::ContentUpdated(
        winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *this,
        struct IFlipPropertySet *a2,
        struct IUnknown *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  if ( a3 )
  {
    winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::EnqueueCaptureFrame(this, a2, a3);
    if ( *((_QWORD *)this + 12) )
    {
      if ( *((_QWORD *)this + 7) )
      {
        winrt::implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,winrt::cloaked<IFlipContentCallback>>::get_strong(
          this,
          &v9);
        v4 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(), __int64, __int64))(**((_QWORD **)this + 7)
                                                                                           + 152LL))(
               *((_QWORD *)this + 7),
               lambda_b062f1349c06dc49e5a0d27a2f8cf01f_::_lambda_invoker_cdecl_,
               v9,
               3);
        v5 = v4;
        if ( v4 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1BD,
            (unsigned int)"onecoreuap\\windows\\dwm\\capture\\api\\lib\\direct3d11captureframepool.cpp",
            (const char *)(unsigned int)v4,
            v7);
          return v5;
        }
      }
      else
      {
        *((_BYTE *)this + 306) = 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f430  push    rbx
0x18000f432  sub     rsp, 30h
0x18000f436  mov     rbx, rcx
0x18000f439  test    r8, r8
0x18000f43c  jz      short loc_18000F4AD
0x18000f43e  call    ?EnqueueCaptureFrame@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXPEAUIFlipPropertySet@@PEAUIUnknown@@@Z; winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::EnqueueCaptureFrame(IFlipPropertySet *,IUnknown *)
0x18000f443  cmp     qword ptr [rbx+60h], 0
0x18000f448  jz      short loc_18000F4AD
0x18000f44a  cmp     qword ptr [rbx+38h], 0
0x18000f44f  jz      short loc_18000F4A6
0x18000f451  lea     rdx, [rsp+38h+arg_10]
0x18000f456  mov     rcx, rbx
0x18000f459  call    ?get_strong@?$implements@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@U13456@UIClosable@Foundation@56@U?$cloaked@UIFlipContentCallback@@@6@@winrt@@QEAA?AU?$com_ptr@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,winrt::cloaked<IFlipContentCallback>>::get_strong(void)
0x18000f45e  mov     rcx, [rbx+38h]
0x18000f462  lea     rdx, _lambda_b062f1349c06dc49e5a0d27a2f8cf01f____lambda_invoker_cdecl_
0x18000f469  mov     r8, [rsp+38h+arg_10]
0x18000f46e  mov     r9d, 3
0x18000f474  mov     rax, [rcx]
0x18000f477  mov     rax, [rax+98h]
0x18000f47e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f483  mov     ebx, eax
0x18000f485  test    eax, eax
0x18000f487  jns     short loc_18000F4AD
0x18000f489  mov     rcx, [rsp+38h]; this
0x18000f48e  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\dwm\\capture\\api"...
0x18000f495  mov     r9d, eax; char *
0x18000f498  mov     edx, 1BDh; void *
0x18000f49d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f4a2  mov     eax, ebx
0x18000f4a4  jmp     short loc_18000F4AF
0x18000f4a6  mov     byte ptr [rbx+132h], 1
0x18000f4ad  xor     eax, eax
0x18000f4af  add     rsp, 30h
0x18000f4b3  pop     rbx
0x18000f4b4  retn
```
