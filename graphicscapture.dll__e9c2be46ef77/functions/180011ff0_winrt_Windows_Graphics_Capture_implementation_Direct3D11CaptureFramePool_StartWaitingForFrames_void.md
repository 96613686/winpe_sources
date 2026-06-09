# winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::StartWaitingForFrames(void)

- ea: `0x180011ff0`
- end: `0x18001217a`
- name: `?StartWaitingForFrames@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@QEAAXXZ`
- size: `394`
- prototype: `void __fastcall(winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001d7a0`

## callees

- `0x1800022f2`
- `0x180003330`
- `0x180003384`
- `0x1800033c0`
- `0x1800058c4`
- `0x180007c08`
- `0x18000eafc`
- `0x180011ff0`
- `0x1800127bc`
- `0x180012b14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012090`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180012090`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012033`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180012033`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001200b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001200b`

## string_xrefs

- `0x180012139`: `A capture was attempted when the frame pool was already closed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::StartWaitingForFrames(
        winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *this)
{
  char *v2; // rbx
  HANDLE EventW; // rax
  void *v4; // r9
  HANDLE Thread; // rax
  unsigned int *v6; // rax
  unsigned int *v7; // rax
  __int64 v8; // rbx
  unsigned int *v9; // rax
  _BYTE pExceptionObject[24]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v11[24]; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v12[32]; // [rsp+60h] [rbp-20h] BYREF
  char v13; // [rsp+A0h] [rbp+20h] BYREF
  LPVOID lpParameter; // [rsp+A8h] [rbp+28h] BYREF
  char *v15; // [rsp+B0h] [rbp+30h] BYREF

  v2 = (char *)this + 192;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v15 = v2;
  if ( *((_BYTE *)this + 305) )
  {
    v8 = winrt::impl::slim_source_location::current(v11);
    winrt::param::hstring::hstring(
      (winrt::param::hstring *)v12,
      L"A capture was attempted when the frame pool was already closed.");
    v9 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v13, -2147467259);
    winrt::hresult_error::hresult_error(pExceptionObject, *v9, v12, v8);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 264,
    EventW);
  if ( (unsigned __int64)(*((_QWORD *)this + 33) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    winrt::impl::slim_source_location::current(v11);
    v7 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v13, -2147467259);
    winrt::hresult_error::hresult_error(pExceptionObject, *v7);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  winrt::implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,winrt::cloaked<IFlipContentCallback>>::get_strong(
    this,
    &lpParameter);
  v4 = lpParameter;
  lpParameter = 0;
  Thread = CreateThread(
             0,
             0,
             winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool::PresentThread,
             v4,
             0,
             0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 256,
    Thread);
  if ( (unsigned __int64)(*((_QWORD *)this + 32) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    winrt::impl::slim_source_location::current(v11);
    v6 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v13, -2147467259);
    winrt::hresult_error::hresult_error(pExceptionObject, *v6);
    throw (winrt::hresult_error *)pExceptionObject;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
}

```

## disassembly

```asm
0x180011ff0  push    rbp
0x180011ff2  push    rbx
0x180011ff3  push    rdi
0x180011ff4  mov     rbp, rsp
0x180011ff7  sub     rsp, 80h
0x180011ffe  mov     rdi, rcx
0x180012001  lea     rbx, [rcx+0C0h]
0x180012008  mov     rcx, rbx; lpCriticalSection
0x18001200b  call    cs:__imp_EnterCriticalSection
0x180012011  mov     [rbp+arg_10], rbx
0x180012015  cmp     byte ptr [rdi+131h], 0
0x18001201c  jnz     loc_18001212D
0x180012022  lea     rbx, [rdi+108h]
0x180012029  xor     r9d, r9d; lpName
0x18001202c  xor     r8d, r8d; bInitialState
0x18001202f  xor     edx, edx; bManualReset
0x180012031  xor     ecx, ecx; lpEventAttributes
0x180012033  call    cs:__imp_CreateEventW
0x180012039  mov     rdx, rax
0x18001203c  mov     rcx, rbx
0x18001203f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180012044  mov     rax, [rbx]
0x180012047  dec     rax
0x18001204a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001204e  ja      loc_1800120F7
0x180012054  lea     rdx, [rbp+lpParameter]
0x180012058  mov     rcx, rdi
0x18001205b  call    ?get_strong@?$implements@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@U13456@UIClosable@Foundation@56@U?$cloaked@UIFlipContentCallback@@@6@@winrt@@QEAA?AU?$com_ptr@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@2@XZ; winrt::implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,winrt::cloaked<IFlipContentCallback>>::get_strong(void)
0x180012060  nop
0x180012061  mov     r9, [rbp+lpParameter]; lpParameter
0x180012065  mov     [rbp+lpParameter], 0
0x18001206d  lea     rbx, [rdi+100h]
0x180012074  mov     [rsp+80h+lpThreadId], 0; lpThreadId
0x18001207d  mov     [rsp+80h+dwCreationFlags], 0; dwCreationFlags
0x180012085  lea     r8, ?PresentThread@Direct3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@SAKPEAX@Z; lpStartAddress
0x18001208c  xor     edx, edx; dwStackSize
0x18001208e  xor     ecx, ecx; lpThreadAttributes
0x180012090  call    cs:__imp_CreateThread
0x180012096  mov     rdx, rax
0x180012099  mov     rcx, rbx
0x18001209c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800120a1  mov     rax, [rbx]
0x1800120a4  dec     rax
0x1800120a7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800120ab  ja      short loc_1800120C1
0x1800120ad  lea     rcx, [rbp+arg_10]
0x1800120b1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800120b6  add     rsp, 80h
0x1800120bd  pop     rdi
0x1800120be  pop     rbx
0x1800120bf  pop     rbp
0x1800120c0  retn
0x1800120c1  lea     rcx, [rbp+var_38]
0x1800120c5  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x1800120ca  mov     r8, rax
0x1800120cd  mov     edx, 80004005h; int
0x1800120d2  lea     rcx, [rbp+arg_0]; this
0x1800120d6  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1800120db  mov     edx, [rax]
0x1800120dd  lea     rcx, [rbp+pExceptionObject]
0x1800120e1  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800120e6  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x1800120ed  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800120f1  call    _CxxThrowException_0
0x1800120f7  lea     rcx, [rbp+var_38]
0x1800120fb  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180012100  mov     r8, rax
0x180012103  mov     edx, 80004005h; int
0x180012108  lea     rcx, [rbp+arg_0]; this
0x18001210c  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180012111  mov     edx, [rax]
0x180012113  lea     rcx, [rbp+pExceptionObject]
0x180012117  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001211c  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180012123  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180012127  call    _CxxThrowException_0
0x18001212d  lea     rcx, [rbp+var_38]
0x180012131  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180012136  mov     rbx, rax
0x180012139  lea     rdx, aACaptureWasAtt; "A capture was attempted when the frame "...
0x180012140  lea     rcx, [rbp+var_20]; this
0x180012144  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180012149  mov     edx, 80004005h; int
0x18001214e  lea     rcx, [rbp+arg_0]; this
0x180012152  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180012157  mov     r9, rbx
0x18001215a  lea     r8, [rbp+var_20]
0x18001215e  mov     edx, [rax]
0x180012160  lea     rcx, [rbp+pExceptionObject]
0x180012164  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180012169  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180012170  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180012174  call    _CxxThrowException_0
```
