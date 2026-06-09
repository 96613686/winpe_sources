# FullscreenWatchdogThreadWorker

- ea: `0x18001de80`
- end: `0x18001e3ee`
- name: `FullscreenWatchdogThreadWorker`
- size: `1390`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007b54`
- `0x180014750`
- `0x18001960c`
- `0x18001a6d4`
- `0x18001b4f8`
- `0x18001d480`
- `0x18001de80`
- `0x18001eb40`
- `0x180021eec`
- `0x18002b390`
- `0x18002dbe8`
- `0x180037d60`
- `0x180050784`
- `0x18006ec58`
- `0x180075fa0`
- `0x1800cb010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001e344`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001e344`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001df79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001df79`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18001e0d9`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18001e0d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e0f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e0f6`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageA` at `0x18001e19d`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageA` at `0x18001e19d`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x18001e18f`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x18001e18f`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageA` at `0x18001dfb7`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageA` at `0x18001dfb7`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorA` at `0x18001dee7`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorA` at `0x18001dee7`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExA` at `0x18001df58`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExA` at `0x18001df58`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18001e2df`
- `ext-ms-win-ntuser-window-l1-1-0!SetWindowPos` at `0x18001e2df`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassA` at `0x18001df1d`
- `ext-ms-win-ntuser-windowclass-l1-1-0!RegisterClassA` at `0x18001df1d`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconA` at `0x18001ded5`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconA` at `0x18001ded5`

## string_xrefs

- `0x18001df06`: `DXGIWatchdogThreadWindow`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall FullscreenWatchdogThreadWorker(PVOID Parameter)
{
  CLazyModule *v1; // rax
  _QWORD *v2; // rbx
  _QWORD *v3; // rax
  _QWORD *v4; // rbx
  CDXGISwapChain *v5; // rdi
  int v6; // eax
  __int64 v7; // rdi
  _QWORD **v8; // rcx
  _QWORD *v9; // rcx
  _QWORD *v10; // rbx
  _QWORD **v11; // rcx
  _QWORD *v12; // rcx
  _QWORD *v13; // rbx
  __int64 v15; // r12
  __int64 v16; // rdi
  unsigned int KMTHandle; // eax
  _QWORD *v18; // rbx
  __int64 v19; // r13
  __int64 size_of; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  CDXGISwapChain *v23; // rbx
  __int128 v24; // [rsp+60h] [rbp-178h] BYREF
  __int64 v25; // [rsp+70h] [rbp-168h] BYREF
  struct IUnknown *v26; // [rsp+78h] [rbp-160h] BYREF
  int v27; // [rsp+80h] [rbp-158h] BYREF
  int v28; // [rsp+84h] [rbp-154h] BYREF
  CDXGISwapChain *v29; // [rsp+88h] [rbp-150h] BYREF
  __int128 v30; // [rsp+90h] [rbp-148h] BYREF
  _QWORD *v31; // [rsp+A0h] [rbp-138h]
  __int128 *v32; // [rsp+A8h] [rbp-130h] BYREF
  __int64 v33; // [rsp+B0h] [rbp-128h]
  _DWORD v34[2]; // [rsp+B8h] [rbp-120h] BYREF
  int *v35; // [rsp+C0h] [rbp-118h]
  int *v36; // [rsp+C8h] [rbp-110h]
  __int64 v37; // [rsp+D0h] [rbp-108h]
  WNDCLASSA WndClass; // [rsp+E0h] [rbp-F8h] BYREF
  tagMSG Msg; // [rsp+130h] [rbp-A8h] BYREF
  _BYTE v40[16]; // [rsp+160h] [rbp-78h] BYREF
  char v41; // [rsp+170h] [rbp-68h] BYREF

  *(_QWORD *)&WndClass.style = 0;
  WndClass.lpfnWndProc = (WNDPROC)WatchdogThreadWindowProc;
  *(_QWORD *)&WndClass.cbClsExtra = 0;
  WndClass.hInstance = 0;
  WndClass.hIcon = LoadIconA(0, (LPCSTR)0x7F00);
  WndClass.hCursor = LoadCursorA(0, (LPCSTR)0x7F00);
  *(__m128i *)&WndClass.hbrBackground = _mm_load_si128((const __m128i *)&_xmm);
  WndClass.lpszClassName = "DXGIWatchdogThreadWindow";
  RegisterClassA(&WndClass);
  qword_1801099F8 = (__int64)CreateWindowExA(
                               0,
                               "DXGIWatchdogThreadWindow",
                               "DXGIWatchdogThreadWindow",
                               0x80000000,
                               0,
                               0,
                               10,
                               10,
                               0,
                               0,
                               0,
                               0);
  while ( WaitForSingleObject(hObject, 0x1F4u) )
  {
    memset(&Msg, 0, sizeof(Msg));
    while ( PeekMessageA(&Msg, 0, 0, 0, 1u) )
    {
      TranslateMessage(&Msg);
      DispatchMessageA(&Msg);
    }
    v30 = 0;
    std::list<CDXGISwapChain *>::_Alloc_sentinel_and_proxy(&v30);
    ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(v40, &CriticalSection);
    v1 = xmmword_180109A10;
    if ( xmmword_180109A10 )
    {
      v2 = (_QWORD *)*((_QWORD *)xmmword_180109A10 + 6);
      while ( 1 )
      {
        v2 = (_QWORD *)*v2;
        if ( v2 == *((_QWORD **)v1 + 6) )
          break;
        v7 = v2[2];
        if ( TryEnterCriticalSection((LPCRITICAL_SECTION)(v7 + 136)) )
        {
          CDXGIFactory::GetListOfNotPresentingFullscreenSwapChains(v7, &v30);
          LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 136));
        }
        v1 = xmmword_180109A10;
      }
    }
    ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v40);
    v24 = 0;
    std::list<CDXGISwapChain *>::_Alloc_sentinel_and_proxy(&v24);
    v3 = (_QWORD *)v30;
    v4 = *(_QWORD **)v30;
    while ( 1 )
    {
      v31 = v4;
      if ( v4 == v3 )
        break;
      v29 = (CDXGISwapChain *)v4[2];
      v5 = v29;
      SPresentArgsCore<CDXGISwapChainWrapper>::SPresentArgsCore<CDXGISwapChainWrapper>(
        (unsigned int)&v41,
        (unsigned int)&v29,
        0,
        1,
        0);
      v6 = CDXGISwapChain::PresentImpl(v5, 0, 0, 0);
      if ( v6 == 142213121 || v6 == -2005270523 )
      {
        v29 = v5;
        (*(void (__fastcall **)(CDXGISwapChain *))(*(_QWORD *)v5 + 8LL))(v5);
        try
        {
          if ( *((_QWORD *)&v24 + 1) == 0xAAAAAAAAAAAAAAALL )
            std::_Xlength_error("list too long");
          v19 = v24;
          v32 = &v24;
          v33 = 0;
          size_of = std::_Get_size_of_n<24>(1);
          v21 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
          v21[2] = v5;
          ++*((_QWORD *)&v24 + 1);
          v22 = *(_QWORD **)(v19 + 8);
          *v21 = v19;
          v21[1] = v22;
          v33 = 0;
          *(_QWORD *)(v19 + 8) = v21;
          *v22 = v21;
          std::_Alloc_construct_ptr<std::allocator<std::_List_node<CDXGISwapChain *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<CDXGISwapChain *,void *>>>(&v32);
        }
        catch ( std::bad_alloc )
        {
          v23 = v29;
          (*(void (__fastcall **)(_QWORD *))(**((_QWORD **)v29 + 18) + 32LL))(*((_QWORD **)v29 + 18));
          (*(void (__fastcall **)(CDXGISwapChain *))(*(_QWORD *)v23 + 16LL))(v23);
          v4 = v31;
        }
      }
      else
      {
        (*(void (__fastcall **)(_QWORD *))(**((_QWORD **)v5 + 18) + 32LL))(*((_QWORD **)v5 + 18));
      }
      v4 = (_QWORD *)*v4;
      v3 = (_QWORD *)v30;
    }
    v8 = (_QWORD **)v24;
    if ( *((_QWORD *)&v24 + 1) )
    {
      v18 = *(_QWORD **)v24;
      while ( v18 != v8 )
      {
        v15 = v18[2];
        if ( HIBYTE(dword_180109BA6) )
          CDXGISwapChain::DestroyFocusProxyWindow((CDXGISwapChain *)v18[2]);
        v26 = 0;
        v25 = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, struct IUnknown **))(*(_QWORD *)v15 + 56LL))(
               v15,
               &IID_IDXGIDevice,
               &v26) >= 0
          && v26 )
        {
          ((void (__fastcall *)(struct IUnknown *, __int64 *))v26->lpVtbl[2].AddRef)(v26, &v25);
          v16 = v25;
          KMTHandle = RetrieveKMTHandle(v26);
          v27 = 0;
          v28 = *(_DWORD *)(*(_QWORD *)(v15 + 2128) + 256LL);
          v34[1] = 0;
          v37 = 1;
          v34[0] = KMTHandle;
          v35 = &v27;
          v36 = &v28;
          (*(void (__fastcall **)(_DWORD *))(v16 + 248))(v34);
          _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 2204), 1, 0);
          SetWindowPos(*(HWND *)(v15 + 336), (HWND)0xFFFFFFFFFFFFFFFELL, 0, 0, 0, 0, 0x4013u);
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v15 + 144) + 32LL))(*(_QWORD *)(v15 + 144));
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
        v18 = (_QWORD *)*v18;
        v8 = (_QWORD **)v24;
      }
    }
    *v8[1] = 0;
    v9 = *v8;
    if ( v9 )
    {
      do
      {
        v10 = (_QWORD *)*v9;
        std::_Deallocate<16>(v9, 24);
        v9 = v10;
      }
      while ( v10 );
    }
    std::_Deallocate<16>(v24, 24);
    v11 = (_QWORD **)v30;
    **(_QWORD **)(v30 + 8) = 0;
    v12 = *v11;
    if ( v12 )
    {
      do
      {
        v13 = (_QWORD *)*v12;
        std::_Deallocate<16>(v12, 24);
        v12 = v13;
      }
      while ( v13 );
    }
    std::_Deallocate<16>(v30, 24);
  }
  return 0;
}

```

## disassembly

```asm
0x18001de80  mov     r11, rsp
0x18001de83  push    rbx
0x18001de84  push    rsi
0x18001de85  push    rdi
0x18001de86  push    r12
0x18001de88  push    r13
0x18001de8a  push    r14
0x18001de8c  push    r15
0x18001de8e  sub     rsp, 1A0h
0x18001de95  mov     rax, cs:__security_cookie
0x18001de9c  xor     rax, rsp
0x18001de9f  mov     [rsp+1D8h+var_40], rax
0x18001dea7  xor     esi, esi
0x18001dea9  mov     [r11-0F8h], rsi
0x18001deb0  lea     rax, ?WatchdogThreadWindowProc@@YA_JPEAUHWND__@@I_K_J@Z; WatchdogThreadWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001deb7  mov     [r11-0F0h], rax
0x18001debe  mov     [r11-0E8h], rsi
0x18001dec5  mov     [r11-0E0h], rsi
0x18001decc  mov     ebx, 7F00h
0x18001ded1  mov     edx, ebx; lpIconName
0x18001ded3  xor     ecx, ecx; hInstance
0x18001ded5  call    cs:__imp_LoadIconA
0x18001dedb  mov     [rsp+1D8h+WndClass.hIcon], rax
0x18001dee3  mov     edx, ebx; lpCursorName
0x18001dee5  xor     ecx, ecx; hInstance
0x18001dee7  call    cs:__imp_LoadCursorA
0x18001deed  mov     [rsp+1D8h+WndClass.hCursor], rax
0x18001def5  movdqa  xmm0, cs:__xmm@00000000000000000000000000000004
0x18001defd  movdqa  xmmword ptr [rsp+1D8h+WndClass.hbrBackground], xmm0
0x18001df06  lea     rbx, WindowName; "DXGIWatchdogThreadWindow"
0x18001df0d  mov     [rsp+1D8h+WndClass.lpszClassName], rbx
0x18001df15  lea     rcx, [rsp+1D8h+WndClass]; lpWndClass
0x18001df1d  call    cs:__imp_RegisterClassA
0x18001df23  mov     [rsp+1D8h+lpParam], rsi; lpParam
0x18001df28  mov     [rsp+1D8h+hInstance], rsi; hInstance
0x18001df2d  mov     [rsp+1D8h+hMenu], rsi; hMenu
0x18001df32  mov     [rsp+1D8h+hWndParent], rsi; hWndParent
0x18001df37  lea     eax, [rsi+0Ah]
0x18001df3a  mov     [rsp+1D8h+nHeight], eax; nHeight
0x18001df3e  mov     [rsp+1D8h+nWidth], eax; nWidth
0x18001df42  mov     [rsp+1D8h+Y], esi; Y
0x18001df46  mov     [rsp+1D8h+X], esi; X
0x18001df4a  mov     r9d, 80000000h; dwStyle
0x18001df50  mov     r8, rbx; lpWindowName
0x18001df53  mov     rdx, rbx; lpClassName
0x18001df56  xor     ecx, ecx; dwExStyle
0x18001df58  call    cs:__imp_CreateWindowExA
0x18001df5e  mov     cs:qword_1801099F8, rax
0x18001df65  lea     r14d, [rsi+1]
0x18001df69  lea     r15d, [rsi+18h]
0x18001df6d  mov     edx, 1F4h; dwMilliseconds
0x18001df72  mov     rcx, cs:hObject; hHandle
0x18001df79  call    cs:__imp_WaitForSingleObject
0x18001df7f  test    eax, eax
0x18001df81  jz      loc_18001E1A8
0x18001df87  xorps   xmm0, xmm0
0x18001df8a  movups  xmmword ptr [rsp+1D8h+Msg.hwnd], xmm0
0x18001df92  movups  xmmword ptr [rsp+1D8h+Msg.wParam], xmm0
0x18001df9a  movups  xmmword ptr [rsp+1D8h+Msg.time], xmm0
0x18001dfa2  mov     [rsp+1D8h+X], r14d; wRemoveMsg
0x18001dfa7  xor     r9d, r9d; wMsgFilterMax
0x18001dfaa  xor     r8d, r8d; wMsgFilterMin
0x18001dfad  xor     edx, edx; hWnd
0x18001dfaf  lea     rcx, [rsp+1D8h+Msg]; lpMsg
0x18001dfb7  call    cs:__imp_PeekMessageA
0x18001dfbd  test    eax, eax
0x18001dfbf  jnz     loc_18001E187
0x18001dfc5  xorps   xmm0, xmm0
0x18001dfc8  movdqu  [rsp+1D8h+var_148], xmm0
0x18001dfd1  lea     rcx, [rsp+1D8h+var_148]
0x18001dfd9  call    ?_Alloc_sentinel_and_proxy@?$list@PEAVCDXGISwapChain@@V?$allocator@PEAVCDXGISwapChain@@@std@@@std@@AEAAXXZ; std::list<CDXGISwapChain *>::_Alloc_sentinel_and_proxy(void)
0x18001dfde  nop
0x18001dfdf  lea     rdx, CriticalSection
0x18001dfe6  lea     rcx, [rsp+1D8h+var_78]
0x18001dfee  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x18001dff3  nop
0x18001dff4  mov     rax, qword ptr cs:xmmword_180109A10
0x18001dffb  test    rax, rax
0x18001dffe  jz      short loc_18001E011
0x18001e000  mov     rbx, [rax+30h]
0x18001e004  mov     rbx, [rbx]
0x18001e007  cmp     rbx, [rax+30h]
0x18001e00b  jnz     loc_18001E0CB
0x18001e011  lea     rcx, [rsp+1D8h+var_78]
0x18001e019  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001e01e  xorps   xmm0, xmm0
0x18001e021  movdqu  [rsp+1D8h+var_178], xmm0
0x18001e027  lea     rcx, [rsp+1D8h+var_178]
0x18001e02c  call    ?_Alloc_sentinel_and_proxy@?$list@PEAVCDXGISwapChain@@V?$allocator@PEAVCDXGISwapChain@@@std@@@std@@AEAAXXZ; std::list<CDXGISwapChain *>::_Alloc_sentinel_and_proxy(void)
0x18001e031  nop
0x18001e032  mov     rax, qword ptr [rsp+1D8h+var_148]
0x18001e03a  mov     rbx, [rax]
0x18001e03d  mov     [rsp+1D8h+var_138], rbx
0x18001e045  cmp     rbx, rax
0x18001e048  jz      loc_18001E108
0x18001e04e  mov     rdi, [rbx+10h]
0x18001e052  mov     [rsp+1D8h+var_150], rdi
0x18001e05a  mov     [rsp+1D8h+X], esi
0x18001e05e  mov     r9d, r14d
0x18001e061  xor     r8d, r8d
0x18001e064  lea     rdx, [rsp+1D8h+var_150]
0x18001e06c  lea     rcx, [rsp+1D8h+var_68]
0x18001e074  call    ??0?$SPresentArgsCore@UCDXGISwapChainWrapper@@@@QEAA@PEAUCDXGISwapChainWrapper@@W4EPresentEntryPoint@@USPresentFlags@@I@Z; SPresentArgsCore<CDXGISwapChainWrapper>::SPresentArgsCore<CDXGISwapChainWrapper>(CDXGISwapChainWrapper *,EPresentEntryPoint,SPresentFlags,uint)
0x18001e079  mov     qword ptr [rsp+1D8h+nWidth], rsi; __int64
0x18001e07e  mov     qword ptr [rsp+1D8h+Y], rsi; __int64
0x18001e083  mov     [rsp+1D8h+X], esi; int
0x18001e087  xor     r9d, r9d
0x18001e08a  xor     r8d, r8d
0x18001e08d  lea     rdx, [rsp+1D8h+var_68]
0x18001e095  mov     rcx, rdi; this
0x18001e098  call    ?PresentImpl@CDXGISwapChain@@QEAAJPEBU?$SPresentArgsCore@UCDXGISwapChainWrapper@@@@IPEBUtagRECT@@IPEBUDXGI_SCROLL_RECT@@PEAUIDXGIResource@@@Z; CDXGISwapChain::PresentImpl(SPresentArgsCore<CDXGISwapChainWrapper> const *,uint,tagRECT const *,uint,DXGI_SCROLL_RECT const *,IDXGIResource *)
0x18001e09d  cmp     eax, 87A0001h
0x18001e0a2  jz      loc_18001E3AF
0x18001e0a8  cmp     eax, 887A0005h
0x18001e0ad  jz      loc_18001E3AF
0x18001e0b3  mov     rcx, [rdi+90h]
0x18001e0ba  mov     rax, [rcx]
0x18001e0bd  mov     rax, [rax+20h]
0x18001e0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0c6  jmp     loc_18001E3DD
0x18001e0cb  mov     rdi, [rbx+10h]
0x18001e0cf  lea     r12, [rdi+88h]
0x18001e0d6  mov     rcx, r12; lpCriticalSection
0x18001e0d9  call    cs:__imp_TryEnterCriticalSection
0x18001e0df  test    eax, eax
0x18001e0e1  jz      short loc_18001E0FC
0x18001e0e3  lea     rdx, [rsp+1D8h+var_148]
0x18001e0eb  mov     rcx, rdi
0x18001e0ee  call    ?GetListOfNotPresentingFullscreenSwapChains@CDXGIFactory@@QEAAXPEAV?$list@PEAVCDXGISwapChain@@V?$allocator@PEAVCDXGISwapChain@@@std@@@std@@@Z; CDXGIFactory::GetListOfNotPresentingFullscreenSwapChains(std::list<CDXGISwapChain *> *)
0x18001e0f3  mov     rcx, r12; lpCriticalSection
0x18001e0f6  call    cs:__imp_LeaveCriticalSection
0x18001e0fc  mov     rax, qword ptr cs:xmmword_180109A10
0x18001e103  jmp     loc_18001E004
0x18001e108  mov     rcx, qword ptr [rsp+1D8h+var_178]
0x18001e10d  cmp     qword ptr [rsp+1D8h+var_178+8], rsi
0x18001e112  jnz     loc_18001E3A7
0x18001e118  mov     rax, [rcx+8]
0x18001e11c  mov     [rax], rsi
0x18001e11f  mov     rcx, [rcx]
0x18001e122  test    rcx, rcx
0x18001e125  jz      short loc_18001E13A
0x18001e127  mov     rbx, [rcx]
0x18001e12a  mov     rdx, r15
0x18001e12d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e132  mov     rcx, rbx
0x18001e135  test    rbx, rbx
0x18001e138  jnz     short loc_18001E127
0x18001e13a  mov     rdx, r15
0x18001e13d  mov     rcx, qword ptr [rsp+1D8h+var_178]
0x18001e142  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e147  nop
0x18001e148  mov     rcx, qword ptr [rsp+1D8h+var_148]
0x18001e150  mov     rax, [rcx+8]
0x18001e154  mov     [rax], rsi
0x18001e157  mov     rcx, [rcx]
0x18001e15a  test    rcx, rcx
0x18001e15d  jz      short loc_18001E172
0x18001e15f  mov     rbx, [rcx]
0x18001e162  mov     rdx, r15
0x18001e165  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e16a  mov     rcx, rbx
0x18001e16d  test    rbx, rbx
0x18001e170  jnz     short loc_18001E15F
0x18001e172  mov     rdx, r15
0x18001e175  mov     rcx, qword ptr [rsp+1D8h+var_148]
0x18001e17d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001e182  jmp     loc_18001DF6D
0x18001e187  lea     rcx, [rsp+1D8h+Msg]; lpMsg
0x18001e18f  call    cs:__imp_TranslateMessage
0x18001e195  lea     rcx, [rsp+1D8h+Msg]; lpMsg
0x18001e19d  call    cs:__imp_DispatchMessageA
0x18001e1a3  jmp     loc_18001DFA2
0x18001e1a8  xor     eax, eax
0x18001e1aa  mov     rcx, [rsp+1D8h+var_40]
0x18001e1b2  xor     rcx, rsp; StackCookie
0x18001e1b5  call    __security_check_cookie
0x18001e1ba  add     rsp, 1A0h
0x18001e1c1  pop     r15
0x18001e1c3  pop     r14
0x18001e1c5  pop     r13
0x18001e1c7  pop     r12
0x18001e1c9  pop     rdi
0x18001e1ca  pop     rsi
0x18001e1cb  pop     rbx
0x18001e1cc  retn
0x18001e1cd  cmp     rbx, rcx
0x18001e1d0  jz      loc_18001E118
0x18001e1d6  mov     r12, [rbx+10h]
0x18001e1da  cmp     byte ptr cs:dword_180109BA6+3, sil
0x18001e1e1  jz      short loc_18001E1EB
0x18001e1e3  mov     rcx, r12; this
0x18001e1e6  call    ?DestroyFocusProxyWindow@CDXGISwapChain@@QEAAXXZ; CDXGISwapChain::DestroyFocusProxyWindow(void)
0x18001e1eb  mov     [rsp+1D8h+var_160], rsi
0x18001e1f0  mov     [rsp+1D8h+var_168], rsi
0x18001e1f5  mov     rax, [r12]
0x18001e1f9  lea     r8, [rsp+1D8h+var_160]
0x18001e1fe  lea     rdx, IID_IDXGIDevice
0x18001e205  mov     rcx, r12
0x18001e208  mov     rax, [rax+38h]
0x18001e20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e211  test    eax, eax
0x18001e213  js      loc_18001E30A
0x18001e219  mov     rcx, [rsp+1D8h+var_160]
0x18001e21e  test    rcx, rcx
0x18001e221  jz      loc_18001E30A
0x18001e227  mov     rax, [rcx]
0x18001e22a  lea     rdx, [rsp+1D8h+var_168]
0x18001e22f  mov     rax, [rax+38h]
0x18001e233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e238  mov     rdi, [rsp+1D8h+var_168]
0x18001e23d  mov     rcx, [rsp+1D8h+var_160]; struct IUnknown *
0x18001e242  call    ?RetrieveKMTHandle@@YAIPEAUIUnknown@@@Z; RetrieveKMTHandle(IUnknown *)
0x18001e247  mov     [rsp+1D8h+var_158], esi
0x18001e24e  mov     rcx, [r12+850h]
0x18001e256  mov     edx, [rcx+100h]
0x18001e25c  mov     [rsp+1D8h+var_154], edx
0x18001e263  mov     [rsp+1D8h+var_11C], esi
0x18001e26a  mov     [rsp+1D8h+var_108], 1
0x18001e276  mov     [rsp+1D8h+var_120], eax
0x18001e27d  lea     rax, [rsp+1D8h+var_158]
0x18001e285  mov     [rsp+1D8h+var_118], rax
0x18001e28d  lea     rax, [rsp+1D8h+var_154]
0x18001e295  mov     [rsp+1D8h+var_110], rax
0x18001e29d  lea     rcx, [rsp+1D8h+var_120]
0x18001e2a5  mov     rax, [rdi+0F8h]
0x18001e2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2b1  xor     eax, eax
0x18001e2b3  lock cmpxchg [r12+89Ch], r14d
0x18001e2bd  mov     [rsp+1D8h+nWidth], 4013h; uFlags
0x18001e2c5  mov     [rsp+1D8h+Y], esi; cy
0x18001e2c9  mov     [rsp+1D8h+X], esi; cx
0x18001e2cd  xor     r9d, r9d; Y
0x18001e2d0  xor     r8d, r8d; X
0x18001e2d3  lea     rdx, [r9-2]; hWndInsertAfter
0x18001e2d7  mov     rcx, [r12+150h]; hWnd
0x18001e2df  call    cs:__imp_SetWindowPos
0x18001e2e5  mov     rcx, [r12+90h]
0x18001e2ed  mov     rax, [rcx]
0x18001e2f0  mov     rax, [rax+20h]
0x18001e2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2f9  mov     rax, [r12]
0x18001e2fd  mov     rcx, r12
0x18001e300  mov     rax, [rax+10h]
0x18001e304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e309  nop
0x18001e30a  lea     rcx, [rsp+1D8h+var_168]
0x18001e30f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e314  nop
0x18001e315  lea     rcx, [rsp+1D8h+var_160]
0x18001e31a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e31f  mov     rbx, [rbx]
0x18001e322  mov     rcx, qword ptr [rsp+1D8h+var_178]
0x18001e327  jmp     loc_18001E1CD
0x18001e32c  mov     rax, 0AAAAAAAAAAAAAAAh
0x18001e336  cmp     qword ptr [rsp+1D8h+var_178+8], rax
0x18001e33b  jnz     short loc_18001E34A
0x18001e33d  lea     rcx, aListTooLong; "list too long"
0x18001e344  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001e34a  mov     r13, qword ptr [rsp+1D8h+var_178]
0x18001e34f  lea     rax, [rsp+1D8h+var_178]
0x18001e354  mov     [rsp+1D8h+var_130], rax
0x18001e35c  mov     [rsp+1D8h+var_128], rsi
0x18001e364  mov     rcx, r14
0x18001e367  call    ??$_Get_size_of_n@$0BI@@std@@YA_K_K@Z; std::_Get_size_of_n<24>(unsigned __int64)
0x18001e36c  mov     rcx, rax
0x18001e36f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001e374  mov     [rax+10h], rdi
0x18001e378  add     qword ptr [rsp+1D8h+var_178+8], r14
0x18001e37d  mov     rcx, [r13+8]
0x18001e381  mov     [rax], r13
0x18001e384  mov     [rax+8], rcx
0x18001e388  mov     [rsp+1D8h+var_128], rsi
0x18001e390  mov     [r13+8], rax
0x18001e394  mov     [rcx], rax
0x18001e397  lea     rcx, [rsp+1D8h+var_130]
0x18001e39f  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAVCDXGISwapChain@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<CDXGISwapChain *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<CDXGISwapChain *,void *>>>(void)
0x18001e3a4  nop
0x18001e3a5  jmp     short loc_18001E3DD
0x18001e3a7  mov     rbx, [rcx]
0x18001e3aa  jmp     loc_18001E1CD
0x18001e3af  mov     [rsp+1D8h+var_150], rdi
0x18001e3b7  mov     rax, [rdi]
0x18001e3ba  mov     rcx, rdi
0x18001e3bd  mov     rax, [rax+8]
0x18001e3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3c6  jmp     loc_18001E32C
0x18001e3cb  xor     esi, esi
0x18001e3cd  lea     r14d, [rsi+1]
0x18001e3d1  lea     r15d, [rsi+18h]
0x18001e3d5  mov     rbx, [rsp+1D8h+var_138]
0x18001e3dd  mov     rbx, [rbx]
0x18001e3e0  mov     rax, qword ptr [rsp+1D8h+var_148]
0x18001e3e8  jmp     loc_18001E03D
```
