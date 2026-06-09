# EapHost::HostPeerApis::Initialize(void)

- ea: `0x180007e88`
- end: `0x1800080f0`
- name: `?Initialize@HostPeerApis@EapHost@@SAXXZ`
- size: `616`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000daf0`

## callees

- `0x180002a90`
- `0x180003920`
- `0x180004ea4`
- `0x180007e88`
- `0x180009d00`
- `0x180009dc4`
- `0x180009dec`
- `0x18000ada8`
- `0x18001dd64`
- `0x1800226a0`
- `0x18002edf4`
- `0x18002f650`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007fd8`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007fd8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007f17`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007f17`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007fa0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007fa0`

## string_xrefs

- `0x180007fec`: `CoCreateInstance(CLSID_ContextSwitcher)`
- `0x180008024`: `CoCreateInstance(CLSID_ContextSwitcher)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void EapHost::HostPeerApis::Initialize(void)
{
  void *v0; // rbx
  HRESULT *v1; // rbx
  HRESULT v2; // eax
  EapHost::Peer::Host *v3; // rax
  __int64 v4; // rcx
  HRESULT Instance; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  _QWORD v10[2]; // [rsp+40h] [rbp-828h] BYREF
  WCHAR Buffer[1024]; // [rsp+50h] [rbp-818h] BYREF

  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids);
  }
  v0 = HeapAllocator::Alloc(1u);
  v10[0] = v0;
  if ( v0 )
    RunTimeInitializer::Start();
  else
    v0 = 0;
  EapHost::HostPeerApis::pRunTimeInit = v0;
  v1 = (HRESULT *)HeapAllocator::Alloc(4u);
  v10[0] = v1;
  if ( v1 )
  {
    v2 = CoInitializeEx(0, 0);
    *v1 = v2;
    if ( (int)(v2 + 0x80000000) >= 0 && v2 != -2147417850 )
      SystemError::ThrowHelper(L"CoInitializeEx", v2);
  }
  else
  {
    v1 = 0;
  }
  EapHost::HostPeerApis::pComInit = v1;
  v3 = (EapHost::Peer::Host *)HeapAllocator::Alloc(0xA0u);
  v10[0] = v3;
  if ( v3 )
    v3 = (EapHost::Peer::Host *)EapHost::Peer::Host::Host(v3);
  v10[0] = v3;
  std::unique_ptr<EapHost::Peer::Host>::operator=<std::default_delete<EapHost::Peer::Host>,0>(v4, v10);
  std::unique_ptr<EapHost::Peer::Host>::~unique_ptr<EapHost::Peer::Host>(v10);
  Instance = CoCreateInstance(
               &CLSID_ContextSwitcher,
               0,
               1u,
               &GUID_000001da_0000_0000_c000_000000000046,
               &EapHost::HostPeerApis::pContextCallback);
  if ( Instance < 0 )
  {
    FormatMessageW(0x1200u, 0, Instance, 0, Buffer, 0x400u, 0);
    if ( (Microsoft_Windows_EapHostEnableBits & 0x10) != 0 )
      McTemplateU0sz_EtwEventWriteTransfer(v7, v6, "CoCreateInstance(CLSID_ContextSwitcher)", Buffer);
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids,
        (unsigned int)Instance);
    }
    EapHost::EapException::Throw(L"CoCreateInstance(CLSID_ContextSwitcher)", Instance);
  }
  v8 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(struct tagComCallData *), _QWORD, GUID *, int, _QWORD))(*(_QWORD *)EapHost::HostPeerApis::pContextCallback + 24LL))(
         EapHost::HostPeerApis::pContextCallback,
         EapHost::HostPeerApis::ConnectCallback,
         0,
         &IID_IContextCallback,
         5,
         0);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids,
        (unsigned int)v8);
    }
    EapHost::EapException::Throw(L"ContextCallback(ConnectCallback)", v9);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids, (unsigned int)v8);
  }
}

```

## disassembly

```asm
0x180007e88  mov     [rsp+arg_0], rbx
0x180007e8d  push    rdi
0x180007e8e  sub     rsp, 860h
0x180007e95  mov     rax, cs:__security_cookie
0x180007e9c  xor     rax, rsp
0x180007e9f  mov     [rsp+868h+var_18], rax
0x180007ea7  lea     rdi, WPP_GLOBAL_Control
0x180007eae  mov     rcx, cs:WPP_GLOBAL_Control
0x180007eb5  cmp     rcx, rdi
0x180007eb8  jz      short loc_180007ED5
0x180007eba  test    byte ptr [rcx+1Ch], 4
0x180007ebe  jz      short loc_180007ED5
0x180007ec0  mov     edx, 0Ch
0x180007ec5  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180007ecc  mov     rcx, [rcx+10h]
0x180007ed0  call    WPP_SF_
0x180007ed5  mov     ecx, 1; unsigned __int64
0x180007eda  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180007edf  mov     rbx, rax
0x180007ee2  mov     [rsp+868h+var_828], rax
0x180007ee7  test    rax, rax
0x180007eea  jz      short loc_180007EF3
0x180007eec  call    ?Start@RunTimeInitializer@@SAXXZ; RunTimeInitializer::Start(void)
0x180007ef1  jmp     short loc_180007EF5
0x180007ef3  xor     ebx, ebx
0x180007ef5  mov     cs:?pRunTimeInit@HostPeerApis@EapHost@@0PEAVRunTimeInitializer@@EA, rbx; RunTimeInitializer * EapHost::HostPeerApis::pRunTimeInit
0x180007efc  mov     ecx, 4; unsigned __int64
0x180007f01  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180007f06  mov     rbx, rax
0x180007f09  mov     [rsp+868h+var_828], rax
0x180007f0e  test    rax, rax
0x180007f11  jz      short loc_180007F41
0x180007f13  xor     edx, edx; dwCoInit
0x180007f15  xor     ecx, ecx; pvReserved
0x180007f17  call    cs:__imp_CoInitializeEx
0x180007f1d  mov     [rbx], eax
0x180007f1f  mov     edx, 80000000h
0x180007f24  lea     ecx, [rax+rdx]
0x180007f27  test    edx, ecx
0x180007f29  jnz     short loc_180007F43
0x180007f2b  cmp     eax, 80010106h
0x180007f30  jz      short loc_180007F43
0x180007f32  mov     edx, eax; int
0x180007f34  lea     rcx, aCoinitializeex_0; "CoInitializeEx"
0x180007f3b  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x180007f41  xor     ebx, ebx
0x180007f43  mov     cs:?pComInit@HostPeerApis@EapHost@@0PEAVComInitializer@@EA, rbx; ComInitializer * EapHost::HostPeerApis::pComInit
0x180007f4a  mov     ecx, 0A0h; unsigned __int64
0x180007f4f  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180007f54  mov     [rsp+868h+var_828], rax
0x180007f59  test    rax, rax
0x180007f5c  jz      short loc_180007F67
0x180007f5e  mov     rcx, rax; this
0x180007f61  call    ??0Host@Peer@EapHost@@QEAA@XZ; EapHost::Peer::Host::Host(void)
0x180007f66  nop
0x180007f67  mov     [rsp+868h+var_828], rax
0x180007f6c  lea     rdx, [rsp+868h+var_828]
0x180007f71  call    ??$?4U?$default_delete@VHost@Peer@EapHost@@@std@@$0A@@?$unique_ptr@VHost@Peer@EapHost@@U?$default_delete@VHost@Peer@EapHost@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapHost::Peer::Host>::operator=<std::default_delete<EapHost::Peer::Host>,0>(std::unique_ptr<EapHost::Peer::Host> &&)
0x180007f76  lea     rcx, [rsp+868h+var_828]
0x180007f7b  call    ??1?$unique_ptr@VHost@Peer@EapHost@@U?$default_delete@VHost@Peer@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::Peer::Host>::~unique_ptr<EapHost::Peer::Host>(void)
0x180007f80  lea     rax, ?pContextCallback@HostPeerApis@EapHost@@0V?$CComPtr@UIContextCallback@@@ATL@@A; ATL::CComPtr<IContextCallback> EapHost::HostPeerApis::pContextCallback
0x180007f87  mov     [rsp+868h+ppv], rax; ppv
0x180007f8c  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x180007f93  xor     edx, edx; pUnkOuter
0x180007f95  lea     r8d, [rdx+1]; dwClsContext
0x180007f99  lea     rcx, CLSID_ContextSwitcher; rclsid
0x180007fa0  call    cs:__imp_CoCreateInstance
0x180007fa6  mov     ebx, eax
0x180007fa8  test    eax, eax
0x180007faa  jns     loc_180008031
0x180007fb0  mov     [rsp+868h+Arguments], 0; Arguments
0x180007fb9  mov     [rsp+868h+nSize], 400h; nSize
0x180007fc1  lea     rax, [rsp+868h+Buffer]
0x180007fc6  mov     [rsp+868h+ppv], rax; lpBuffer
0x180007fcb  xor     r9d, r9d; dwLanguageId
0x180007fce  mov     r8d, ebx; dwMessageId
0x180007fd1  xor     edx, edx; lpSource
0x180007fd3  mov     ecx, 1200h; dwFlags
0x180007fd8  call    cs:__imp_FormatMessageW
0x180007fde  test    cs:Microsoft_Windows_EapHostEnableBits, 10h
0x180007fe5  jz      short loc_180007FF8
0x180007fe7  lea     r9, [rsp+868h+Buffer]
0x180007fec  lea     r8, aCocreateinstan_0; "CoCreateInstance(CLSID_ContextSwitcher)"
0x180007ff3  call    McTemplateU0sz_EtwEventWriteTransfer
0x180007ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fff  cmp     rcx, rdi
0x180008002  jz      short loc_180008022
0x180008004  test    byte ptr [rcx+1Ch], 1
0x180008008  jz      short loc_180008022
0x18000800a  mov     edx, 0Dh
0x18000800f  mov     r9d, ebx
0x180008012  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180008019  mov     rcx, [rcx+10h]
0x18000801d  call    WPP_SF_d
0x180008022  mov     edx, ebx; unsigned int
0x180008024  lea     rcx, aCocreateinstan_1; "CoCreateInstance(CLSID_ContextSwitcher)"
0x18000802b  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x180008031  mov     rcx, cs:?pContextCallback@HostPeerApis@EapHost@@0V?$CComPtr@UIContextCallback@@@ATL@@A; ATL::CComPtr<IContextCallback> EapHost::HostPeerApis::pContextCallback
0x180008038  mov     rax, [rcx]
0x18000803b  mov     qword ptr [rsp+868h+nSize], 0
0x180008044  mov     dword ptr [rsp+868h+ppv], 5
0x18000804c  lea     r9, IID_IContextCallback
0x180008053  xor     r8d, r8d
0x180008056  lea     rdx, ?ConnectCallback@HostPeerApis@EapHost@@CAJPEAUtagComCallData@@@Z; EapHost::HostPeerApis::ConnectCallback(tagComCallData *)
0x18000805d  mov     rax, [rax+18h]
0x180008061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008066  mov     ebx, eax
0x180008068  test    eax, eax
0x18000806a  jns     short loc_1800080A5
0x18000806c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008073  cmp     rcx, rdi
0x180008076  jz      short loc_180008096
0x180008078  test    byte ptr [rcx+1Ch], 1
0x18000807c  jz      short loc_180008096
0x18000807e  mov     edx, 0Eh
0x180008083  mov     r9d, eax
0x180008086  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x18000808d  mov     rcx, [rcx+10h]
0x180008091  call    WPP_SF_d
0x180008096  mov     edx, ebx; unsigned int
0x180008098  lea     rcx, aContextcallbac; "ContextCallback(ConnectCallback)"
0x18000809f  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x1800080a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080ac  cmp     rcx, rdi
0x1800080af  jz      short loc_1800080CF
0x1800080b1  test    byte ptr [rcx+1Ch], 4
0x1800080b5  jz      short loc_1800080CF
0x1800080b7  mov     edx, 0Fh
0x1800080bc  mov     r9d, ebx
0x1800080bf  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x1800080c6  mov     rcx, [rcx+10h]
0x1800080ca  call    WPP_SF_d
0x1800080cf  mov     rcx, [rsp+868h+var_18]
0x1800080d7  xor     rcx, rsp; StackCookie
0x1800080da  call    __security_check_cookie
0x1800080df  mov     rbx, [rsp+868h+arg_0]
0x1800080e7  add     rsp, 860h
0x1800080ee  pop     rdi
0x1800080ef  retn
```
