# CDebugTargetClientThreadManager::ClientBrokerAdapterThreadProc(void *)

- ea: `0x180071e40`
- end: `0x1800720cb`
- name: `?ClientBrokerAdapterThreadProc@CDebugTargetClientThreadManager@@SAJPEAX@Z`
- size: `651`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180007810`
- `0x18000b0ec`
- `0x180019fdc`
- `0x18001b178`
- `0x1800250d8`
- `0x18002b530`
- `0x180037b5c`
- `0x18003dec4`
- `0x180071b94`
- `0x180071e40`
- `0x180072238`
- `0x180072498`
- `0x18007288c`
- `0x180072904`
- `0x180085010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180071e8c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180071e8c`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x180071ec5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x180071ec5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18007205d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x18007205d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x180072053`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x180072053`
- `OLEAUT32!__imp_SysFreeString` at `0x18007203e`
- `OLEAUT32!__imp_SysFreeString` at `0x180072047`
- `OLEAUT32!__imp_SysFreeString` at `0x18007203e`
- `OLEAUT32!__imp_SysFreeString` at `0x180072047`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180071e96`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180072070`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180071e96`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180072070`

## string_xrefs

- `0x180071ea4`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`
- `0x180071eed`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`
- `0x18007207e`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`
- `0x18007209b`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDebugTargetClientThreadManager::ClientBrokerAdapterThreadProc(HANDLE *Parameter)
{
  const char *v2; // r9
  int v3; // r15d
  int MessageW; // eax
  OLECHAR *wParam; // rsi
  struct CDebugTargetClientBrokerAdapterImpl *v6; // rax
  CDebugTargetClientBrokerAdapterImpl *v7; // rax
  struct CDebugTargetClientBrokerAdapterImpl *v8; // r14
  LPARAM v9; // rbx
  unsigned __int16 *lParam; // rbx
  CDebugTargetClientBrokerAdapterImpl *v11; // rax
  const char *v12; // r9
  const char *wRemoveMsg; // [rsp+20h] [rbp-59h]
  const char *v15; // [rsp+28h] [rbp-51h]
  struct tagMSG Msg; // [rsp+30h] [rbp-49h] BYREF
  HANDLE v17; // [rsp+60h] [rbp-19h] BYREF
  __int64 v18; // [rsp+68h] [rbp-11h] BYREF
  char v19[8]; // [rsp+70h] [rbp-9h] BYREF
  _BYTE v20[32]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  memset(&Msg, 0, sizeof(Msg));
  PeekMessageW(&Msg, 0, 0x400u, 0x400u, 0);
  if ( !SetEvent(Parameter[1]) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientbrokeradapter.cpp",
      v2);
  v3 = 0;
  do
  {
    MessageW = GetMessageW(&Msg, 0, 0, 0);
    if ( !MessageW )
      break;
    wil::details::in1diag3::FailFast_IfMsg(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientbrokeradapter.cpp",
      (const char *)(MessageW == -1),
      (bool)"GetMessage failed",
      v15);
    if ( Msg.hwnd )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
    else
    {
      if ( Msg.message - 1025 > 5 )
        wil::details::in1diag3::FailFast_UnexpectedMsg(
          retaddr,
          (void *)0x92,
          (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientb"
                        "rokeradapter.cpp",
          "Invalid message Id",
          wRemoveMsg);
      wParam = (OLECHAR *)Msg.wParam;
      switch ( Msg.message )
      {
        case 0x401u:
          lParam = (unsigned __int16 *)Msg.lParam;
          v11 = CDebugTargetClientThreadManager::EnsureDebugTargetClient(
                  (CDebugTargetClientThreadManager *)Parameter,
                  (const unsigned __int16 *)Msg.wParam);
          CDebugTargetClientBrokerAdapterImpl::PostMessageW(v11, lParam);
          SysFreeString(lParam);
          break;
        case 0x402u:
          v8 = CDebugTargetClientThreadManager::EnsureDebugTargetClient(
                 (CDebugTargetClientThreadManager *)Parameter,
                 (const unsigned __int16 *)Msg.wParam);
          v9 = Msg.lParam;
          if ( *((_QWORD *)v8 + 6) != Msg.lParam )
          {
            if ( Msg.lParam )
              (*(void (__fastcall **)(LPARAM))(*(_QWORD *)Msg.lParam + 8LL))(Msg.lParam);
            v18 = *((_QWORD *)v8 + 6);
            *((_QWORD *)v8 + 6) = v9;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
          }
          (*(void (__fastcall **)(LPARAM))(*(_QWORD *)v9 + 16LL))(v9);
          break;
        case 0x403u:
          std::wstring::wstring(v20);
          std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>,0>>::find(
            Parameter + 3,
            &v17,
            v20);
          if ( v17 != Parameter[4] )
            std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>,0>(
              Parameter + 3,
              v19);
          std::wstring::_Tidy_deallocate(v20);
          v3 = Msg.lParam;
          break;
        case 0x404u:
          v7 = CDebugTargetClientThreadManager::EnsureDebugTargetClient(
                 (CDebugTargetClientThreadManager *)Parameter,
                 (const unsigned __int16 *)Msg.wParam);
          CDebugTargetClientBrokerAdapterImpl::Close(v7);
          break;
        case 0x405u:
          v6 = CDebugTargetClientThreadManager::EnsureDebugTargetClient(
                 (CDebugTargetClientThreadManager *)Parameter,
                 (const unsigned __int16 *)Msg.wParam);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)v6 + 48);
          break;
        case 0x406u:
          std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>,0>>::clear(Parameter + 3);
          break;
      }
      SysFreeString(wParam);
    }
  }
  while ( !v3 );
  if ( !SetEvent(Parameter[2]) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xC9,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientbrokeradapter.cpp",
      v12);
  return 0;
}

```

## disassembly

```asm
0x180071e40  push    rbp
0x180071e42  push    rbx
0x180071e43  push    rsi
0x180071e44  push    rdi
0x180071e45  push    r14
0x180071e47  push    r15
0x180071e49  lea     rbp, [rsp-2Fh]
0x180071e4e  sub     rsp, 0A8h
0x180071e55  mov     rax, cs:__security_cookie
0x180071e5c  xor     rax, rsp
0x180071e5f  mov     [rbp+57h+var_38], rax
0x180071e63  mov     rdi, rcx
0x180071e66  xorps   xmm0, xmm0
0x180071e69  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x180071e6d  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x180071e71  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x180071e75  mov     [rsp+0D0h+wRemoveMsg], 0; wRemoveMsg
0x180071e7d  mov     r8d, 400h; wMsgFilterMin
0x180071e83  mov     r9d, r8d; wMsgFilterMax
0x180071e86  xor     edx, edx; hWnd
0x180071e88  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180071e8c  call    cs:__imp_PeekMessageW
0x180071e92  mov     rcx, [rdi+8]; hEvent
0x180071e96  call    cs:__imp_SetEvent
0x180071e9c  mov     rcx, [rbp+5Fh]; this
0x180071ea0  test    eax, eax
0x180071ea2  jnz     short loc_180071EB6
0x180071ea4  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180071eab  mov     edx, 89h; void *
0x180071eb0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180071eb6  xor     r15d, r15d
0x180071eb9  xor     r9d, r9d; wMsgFilterMax
0x180071ebc  xor     r8d, r8d; wMsgFilterMin
0x180071ebf  xor     edx, edx; hWnd
0x180071ec1  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180071ec5  call    cs:__imp_GetMessageW
0x180071ecb  test    eax, eax
0x180071ecd  jz      loc_18007206C
0x180071ed3  cmp     eax, 0FFFFFFFFh
0x180071ed6  setz    al
0x180071ed9  mov     rcx, [rbp+5Fh]; this
0x180071edd  lea     rdx, aGetmessageFail; "GetMessage failed"
0x180071ee4  mov     qword ptr [rsp+0D0h+wRemoveMsg], rdx; char *
0x180071ee9  movzx   r9d, al; char *
0x180071eed  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180071ef4  mov     edx, 8Dh; void *
0x180071ef9  call    ?FailFast_IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::FailFast_IfMsg(void *,uint,char const *,bool,char const *,...)
0x180071efe  cmp     [rbp+57h+Msg.hwnd], 0
0x180071f03  jnz     loc_18007204F
0x180071f09  mov     ecx, [rbp+57h+Msg.message]
0x180071f0c  lea     eax, [rcx-401h]
0x180071f12  cmp     eax, 5
0x180071f15  ja      loc_180072090
0x180071f1b  mov     rsi, [rbp+57h+Msg.wParam]
0x180071f1f  sub     ecx, 401h
0x180071f25  jz      loc_180072021
0x180071f2b  sub     ecx, 1
0x180071f2e  jz      loc_180071FCE
0x180071f34  sub     ecx, 1
0x180071f37  jz      short loc_180071F8B
0x180071f39  sub     ecx, 1
0x180071f3c  jz      short loc_180071F73
0x180071f3e  sub     ecx, 1
0x180071f41  jz      short loc_180071F5A
0x180071f43  cmp     ecx, 1
0x180071f46  jnz     loc_180072044
0x180071f4c  lea     rcx, [rdi+18h]
0x180071f50  call    ?clear@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>,0>>::clear(void)
0x180071f55  jmp     loc_180072044
0x180071f5a  mov     rdx, rsi; unsigned __int16 *
0x180071f5d  mov     rcx, rdi; this
0x180071f60  call    ?EnsureDebugTargetClient@CDebugTargetClientThreadManager@@AEAAPEAVCDebugTargetClientBrokerAdapterImpl@@PEBG@Z; CDebugTargetClientThreadManager::EnsureDebugTargetClient(ushort const *)
0x180071f65  lea     rcx, [rax+30h]
0x180071f69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180071f6e  jmp     loc_180072044
0x180071f73  mov     rdx, rsi; unsigned __int16 *
0x180071f76  mov     rcx, rdi; this
0x180071f79  call    ?EnsureDebugTargetClient@CDebugTargetClientThreadManager@@AEAAPEAVCDebugTargetClientBrokerAdapterImpl@@PEBG@Z; CDebugTargetClientThreadManager::EnsureDebugTargetClient(ushort const *)
0x180071f7e  mov     rcx, rax; this
0x180071f81  call    ?Close@CDebugTargetClientBrokerAdapterImpl@@QEAAXXZ; CDebugTargetClientBrokerAdapterImpl::Close(void)
0x180071f86  jmp     loc_180072044
0x180071f8b  mov     rdx, rsi
0x180071f8e  lea     rcx, [rbp+57h+var_58]
0x180071f92  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180071f97  lea     r8, [rbp+57h+var_58]
0x180071f9b  lea     rdx, [rbp+57h+var_70]
0x180071f9f  lea     rcx, [rdi+18h]
0x180071fa3  call    ?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>,0>>::find(std::wstring const &)
0x180071fa8  mov     r8, [rbp+57h+var_70]
0x180071fac  cmp     r8, [rdi+20h]
0x180071fb0  jz      short loc_180071FBF
0x180071fb2  lea     rdx, [rbp+57h+var_60]
0x180071fb6  lea     rcx, [rdi+18h]
0x180071fba  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<std::wstring,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>)
0x180071fbf  lea     rcx, [rbp+57h+var_58]
0x180071fc3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180071fc8  mov     r15d, dword ptr [rbp+57h+Msg.lParam]
0x180071fcc  jmp     short loc_180072044
0x180071fce  mov     rdx, rsi; unsigned __int16 *
0x180071fd1  mov     rcx, rdi; this
0x180071fd4  call    ?EnsureDebugTargetClient@CDebugTargetClientThreadManager@@AEAAPEAVCDebugTargetClientBrokerAdapterImpl@@PEBG@Z; CDebugTargetClientThreadManager::EnsureDebugTargetClient(ushort const *)
0x180071fd9  mov     r14, rax
0x180071fdc  mov     rbx, [rbp+57h+Msg.lParam]
0x180071fe0  cmp     [rax+30h], rbx
0x180071fe4  jz      short loc_180072010
0x180071fe6  test    rbx, rbx
0x180071fe9  jz      short loc_180071FFB
0x180071feb  mov     rcx, [rbx]
0x180071fee  mov     rax, [rcx+8]
0x180071ff2  mov     rcx, rbx
0x180071ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071ffa  nop
0x180071ffb  mov     rax, [r14+30h]
0x180071fff  mov     [rbp+57h+var_68], rax
0x180072003  mov     [r14+30h], rbx
0x180072007  lea     rcx, [rbp+57h+var_68]
0x18007200b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072010  mov     rax, [rbx]
0x180072013  mov     rcx, rbx
0x180072016  mov     rax, [rax+10h]
0x18007201a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007201f  jmp     short loc_180072044
0x180072021  mov     rbx, [rbp+57h+Msg.lParam]
0x180072025  mov     rdx, rsi; unsigned __int16 *
0x180072028  mov     rcx, rdi; this
0x18007202b  call    ?EnsureDebugTargetClient@CDebugTargetClientThreadManager@@AEAAPEAVCDebugTargetClientBrokerAdapterImpl@@PEBG@Z; CDebugTargetClientThreadManager::EnsureDebugTargetClient(ushort const *)
0x180072030  mov     rdx, rbx; unsigned __int16 *
0x180072033  mov     rcx, rax; this
0x180072036  call    ?PostMessageW@CDebugTargetClientBrokerAdapterImpl@@QEAAXPEAG@Z; CDebugTargetClientBrokerAdapterImpl::PostMessageW(ushort *)
0x18007203b  mov     rcx, rbx; bstrString
0x18007203e  call    cs:__imp_SysFreeString
0x180072044  mov     rcx, rsi; bstrString
0x180072047  call    cs:__imp_SysFreeString
0x18007204d  jmp     short loc_180072063
0x18007204f  lea     rcx, [rbp+57h+Msg]; lpMsg
0x180072053  call    cs:__imp_TranslateMessage
0x180072059  lea     rcx, [rbp+57h+Msg]; lpMsg
0x18007205d  call    cs:__imp_DispatchMessageW
0x180072063  test    r15d, r15d
0x180072066  jz      loc_180071EB9
0x18007206c  mov     rcx, [rdi+10h]; hEvent
0x180072070  call    cs:__imp_SetEvent
0x180072076  test    eax, eax
0x180072078  jnz     short loc_1800720AD
0x18007207a  mov     rcx, [rbp+5Fh]; this
0x18007207e  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180072085  mov     edx, 0C9h; void *
0x18007208a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180072090  mov     rcx, [rbp+5Fh]; this
0x180072094  lea     r9, aInvalidMessage; "Invalid message Id"
0x18007209b  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800720a2  mov     edx, 92h; void *
0x1800720a7  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x1800720ad  xor     eax, eax
0x1800720af  mov     rcx, [rbp+57h+var_38]
0x1800720b3  xor     rcx, rsp; StackCookie
0x1800720b6  call    __security_check_cookie
0x1800720bb  add     rsp, 0A8h
0x1800720c2  pop     r15
0x1800720c4  pop     r14
0x1800720c6  pop     rdi
0x1800720c7  pop     rsi
0x1800720c8  pop     rbx
0x1800720c9  pop     rbp
0x1800720ca  retn
```
