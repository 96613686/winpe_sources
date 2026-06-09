# EapHost::HostPeerApis::Initialize(void)

- ea: `0x1800081a0`
- end: `0x18000841b`
- name: `?Initialize@HostPeerApis@EapHost@@SAXXZ`
- size: `635`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e070`

## callees

- `0x180002af0`
- `0x1800039bc`
- `0x180004fe0`
- `0x1800081a0`
- `0x18000a154`
- `0x18000a21c`
- `0x18000a24c`
- `0x18000b248`
- `0x18001e868`
- `0x180023318`
- `0x18002fef4`
- `0x1800307e4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800082fc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800082fc`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000822f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000822f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800082be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800082be`

## string_xrefs

- `0x180008316`: `CoCreateInstance(CLSID_ContextSwitcher)`
- `0x18000834e`: `CoCreateInstance(CLSID_ContextSwitcher)`

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
0x1800081a0  mov     [rsp+arg_0], rbx
0x1800081a5  push    rdi
0x1800081a6  sub     rsp, 860h
0x1800081ad  mov     rax, cs:__security_cookie
0x1800081b4  xor     rax, rsp
0x1800081b7  mov     [rsp+868h+var_18], rax
0x1800081bf  lea     rdi, WPP_GLOBAL_Control
0x1800081c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081cd  cmp     rcx, rdi
0x1800081d0  jz      short loc_1800081ED
0x1800081d2  test    byte ptr [rcx+1Ch], 4
0x1800081d6  jz      short loc_1800081ED
0x1800081d8  mov     edx, 0Ch
0x1800081dd  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x1800081e4  mov     rcx, [rcx+10h]
0x1800081e8  call    WPP_SF_
0x1800081ed  mov     ecx, 1; unsigned __int64
0x1800081f2  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800081f7  mov     rbx, rax
0x1800081fa  mov     [rsp+868h+var_828], rax
0x1800081ff  test    rax, rax
0x180008202  jz      short loc_18000820B
0x180008204  call    ?Start@RunTimeInitializer@@SAXXZ; RunTimeInitializer::Start(void)
0x180008209  jmp     short loc_18000820D
0x18000820b  xor     ebx, ebx
0x18000820d  mov     cs:?pRunTimeInit@HostPeerApis@EapHost@@0PEAVRunTimeInitializer@@EA, rbx; RunTimeInitializer * EapHost::HostPeerApis::pRunTimeInit
0x180008214  mov     ecx, 4; unsigned __int64
0x180008219  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18000821e  mov     rbx, rax
0x180008221  mov     [rsp+868h+var_828], rax
0x180008226  test    rax, rax
0x180008229  jz      short loc_18000825F
0x18000822b  xor     edx, edx; dwCoInit
0x18000822d  xor     ecx, ecx; pvReserved
0x18000822f  call    cs:__imp_CoInitializeEx
0x180008236  nop     dword ptr [rax+rax+00h]
0x18000823b  mov     [rbx], eax
0x18000823d  mov     edx, 80000000h
0x180008242  lea     ecx, [rax+rdx]
0x180008245  test    edx, ecx
0x180008247  jnz     short loc_180008261
0x180008249  cmp     eax, 80010106h
0x18000824e  jz      short loc_180008261
0x180008250  mov     edx, eax; int
0x180008252  lea     rcx, aCoinitializeex_0; "CoInitializeEx"
0x180008259  call    ?ThrowHelper@SystemError@@CAXPEB_WJ@Z; SystemError::ThrowHelper(wchar_t const *,long)
0x18000825f  xor     ebx, ebx
0x180008261  mov     cs:?pComInit@HostPeerApis@EapHost@@0PEAVComInitializer@@EA, rbx; ComInitializer * EapHost::HostPeerApis::pComInit
0x180008268  mov     ecx, 0A0h; unsigned __int64
0x18000826d  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180008272  mov     [rsp+868h+var_828], rax
0x180008277  test    rax, rax
0x18000827a  jz      short loc_180008285
0x18000827c  mov     rcx, rax; this
0x18000827f  call    ??0Host@Peer@EapHost@@QEAA@XZ; EapHost::Peer::Host::Host(void)
0x180008284  nop
0x180008285  mov     [rsp+868h+var_828], rax
0x18000828a  lea     rdx, [rsp+868h+var_828]
0x18000828f  call    ??$?4U?$default_delete@VHost@Peer@EapHost@@@std@@$0A@@?$unique_ptr@VHost@Peer@EapHost@@U?$default_delete@VHost@Peer@EapHost@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<EapHost::Peer::Host>::operator=<std::default_delete<EapHost::Peer::Host>,0>(std::unique_ptr<EapHost::Peer::Host> &&)
0x180008294  lea     rcx, [rsp+868h+var_828]
0x180008299  call    ??1?$unique_ptr@VHost@Peer@EapHost@@U?$default_delete@VHost@Peer@EapHost@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapHost::Peer::Host>::~unique_ptr<EapHost::Peer::Host>(void)
0x18000829e  lea     rax, ?pContextCallback@HostPeerApis@EapHost@@0V?$CComPtr@UIContextCallback@@@ATL@@A; ATL::CComPtr<IContextCallback> EapHost::HostPeerApis::pContextCallback
0x1800082a5  mov     [rsp+868h+ppv], rax; ppv
0x1800082aa  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x1800082b1  xor     edx, edx; pUnkOuter
0x1800082b3  lea     r8d, [rdx+1]; dwClsContext
0x1800082b7  lea     rcx, CLSID_ContextSwitcher; rclsid
0x1800082be  call    cs:__imp_CoCreateInstance
0x1800082c5  nop     dword ptr [rax+rax+00h]
0x1800082ca  mov     ebx, eax
0x1800082cc  test    eax, eax
0x1800082ce  jns     loc_18000835B
0x1800082d4  mov     [rsp+868h+Arguments], 0; Arguments
0x1800082dd  mov     [rsp+868h+nSize], 400h; nSize
0x1800082e5  lea     rax, [rsp+868h+Buffer]
0x1800082ea  mov     [rsp+868h+ppv], rax; lpBuffer
0x1800082ef  xor     r9d, r9d; dwLanguageId
0x1800082f2  mov     r8d, ebx; dwMessageId
0x1800082f5  xor     edx, edx; lpSource
0x1800082f7  mov     ecx, 1200h; dwFlags
0x1800082fc  call    cs:__imp_FormatMessageW
0x180008303  nop     dword ptr [rax+rax+00h]
0x180008308  test    cs:Microsoft_Windows_EapHostEnableBits, 10h
0x18000830f  jz      short loc_180008322
0x180008311  lea     r9, [rsp+868h+Buffer]
0x180008316  lea     r8, aCocreateinstan_0; "CoCreateInstance(CLSID_ContextSwitcher)"
0x18000831d  call    McTemplateU0sz_EtwEventWriteTransfer
0x180008322  mov     rcx, cs:WPP_GLOBAL_Control
0x180008329  cmp     rcx, rdi
0x18000832c  jz      short loc_18000834C
0x18000832e  test    byte ptr [rcx+1Ch], 1
0x180008332  jz      short loc_18000834C
0x180008334  mov     edx, 0Dh
0x180008339  mov     r9d, ebx
0x18000833c  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180008343  mov     rcx, [rcx+10h]
0x180008347  call    WPP_SF_d
0x18000834c  mov     edx, ebx; unsigned int
0x18000834e  lea     rcx, aCocreateinstan_1; "CoCreateInstance(CLSID_ContextSwitcher)"
0x180008355  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x18000835b  mov     rcx, cs:?pContextCallback@HostPeerApis@EapHost@@0V?$CComPtr@UIContextCallback@@@ATL@@A; ATL::CComPtr<IContextCallback> EapHost::HostPeerApis::pContextCallback
0x180008362  mov     rax, [rcx]
0x180008365  mov     qword ptr [rsp+868h+nSize], 0
0x18000836e  mov     dword ptr [rsp+868h+ppv], 5
0x180008376  lea     r9, IID_IContextCallback
0x18000837d  xor     r8d, r8d
0x180008380  lea     rdx, ?ConnectCallback@HostPeerApis@EapHost@@CAJPEAUtagComCallData@@@Z; EapHost::HostPeerApis::ConnectCallback(tagComCallData *)
0x180008387  mov     rax, [rax+18h]
0x18000838b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008390  mov     ebx, eax
0x180008392  test    eax, eax
0x180008394  jns     short loc_1800083CF
0x180008396  mov     rcx, cs:WPP_GLOBAL_Control
0x18000839d  cmp     rcx, rdi
0x1800083a0  jz      short loc_1800083C0
0x1800083a2  test    byte ptr [rcx+1Ch], 1
0x1800083a6  jz      short loc_1800083C0
0x1800083a8  mov     edx, 0Eh
0x1800083ad  mov     r9d, eax
0x1800083b0  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x1800083b7  mov     rcx, [rcx+10h]
0x1800083bb  call    WPP_SF_d
0x1800083c0  mov     edx, ebx; unsigned int
0x1800083c2  lea     rcx, aContextcallbac; "ContextCallback(ConnectCallback)"
0x1800083c9  call    ?Throw@EapException@EapHost@@SAXPEB_WK@Z; EapHost::EapException::Throw(wchar_t const *,ulong)
0x1800083cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083d6  cmp     rcx, rdi
0x1800083d9  jz      short loc_1800083F9
0x1800083db  test    byte ptr [rcx+1Ch], 4
0x1800083df  jz      short loc_1800083F9
0x1800083e1  mov     edx, 0Fh
0x1800083e6  mov     r9d, ebx
0x1800083e9  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x1800083f0  mov     rcx, [rcx+10h]
0x1800083f4  call    WPP_SF_d
0x1800083f9  mov     rcx, [rsp+868h+var_18]
0x180008401  xor     rcx, rsp; StackCookie
0x180008404  call    __security_check_cookie
0x180008409  mov     rbx, [rsp+868h+arg_0]
0x180008411  add     rsp, 860h
0x180008418  pop     rdi
0x180008419  retn
```
