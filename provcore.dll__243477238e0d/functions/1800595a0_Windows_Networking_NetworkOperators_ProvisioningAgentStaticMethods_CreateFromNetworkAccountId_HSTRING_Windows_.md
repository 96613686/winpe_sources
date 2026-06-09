# Windows::Networking::NetworkOperators::ProvisioningAgentStaticMethods::CreateFromNetworkAccountId(HSTRING__ *,Windows::Networking::NetworkOperators::IProvisioningAgent * *)

- ea: `0x1800595a0`
- end: `0x1800597df`
- name: `?CreateFromNetworkAccountId@ProvisioningAgentStaticMethods@NetworkOperators@Networking@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIProvisioningAgent@234@@Z`
- size: `575`
- prototype: `HRESULT __fastcall(Windows::Networking::NetworkOperators::ProvisioningAgentStaticMethods *this, HSTRING__ *NetworkAccountId, Windows::Networking::NetworkOperators::IProvisioningAgent **ppProvisioningAgent)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002790`
- `0x180012748`
- `0x180012770`
- `0x1800127cc`
- `0x180057f40`
- `0x1800595a0`
- `0x18005b4a4`
- `0x180060b00`
- `0x180060b94`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180059641`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180059641`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180059664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180059664`
- `MobileNetworking!NetworkAccountBindingAccessCheck` at `0x18005969f`
- `MobileNetworking!NetworkAccountBindingAccessCheck` at `0x18005969f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Networking::NetworkOperators::ProvisioningAgentStaticMethods::CreateFromNetworkAccountId(
        Windows::Networking::NetworkOperators::ProvisioningAgentStaticMethods *this,
        HSTRING NetworkAccountId,
        Windows::Networking::NetworkOperators::IProvisioningAgent **ppProvisioningAgent)
{
  WPP_PROJECT_CONTROL_BLOCK *v5; // rcx
  int v6; // ebx
  const wchar_t *StringRawBuffer; // rax
  int v8; // eax
  HRESULT v9; // edx
  const _GUID *v10; // r8
  HRESULT v11; // ebx
  Windows::Networking::NetworkOperators::ProvisioningAgent *ptr; // rbx
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  Windows::Networking::NetworkOperators::IProvisioningAgent *v14; // rax
  Windows::Networking::NetworkOperators::ProvisioningAgent *v15; // rcx
  int v17; // [rsp+20h] [rbp-40h]
  unsigned __int64 v18; // [rsp+28h] [rbp-38h]
  Windows::Networking::NetworkOperators::ProvisioningAgentStaticMethods::CreateFromNetworkAccountId::__l20::<lambda_1> f; // [rsp+30h] [rbp-30h] BYREF
  const wchar_t *pszNetworkAccountId; // [rsp+40h] [rbp-20h] BYREF
  Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::ProvisioningAgent> spProvisioningAgent; // [rsp+48h] [rbp-18h] BYREF
  Microsoft::WRL::ComPtr<Windows::Networking::NetworkOperators::IProvisioningAgent> spIProvisioningAgent; // [rsp+50h] [rbp-10h] BYREF

  spIProvisioningAgent.ptr_ = 0;
  pszNetworkAccountId = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x10u, WPP_1550942edb28334490bbc72f882435cd_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  if ( NetworkAccountId )
  {
    if ( ppProvisioningAgent )
    {
      *ppProvisioningAgent = 0;
      LODWORD(spProvisioningAgent.ptr_) = 0;
      WindowsStringHasEmbeddedNull(NetworkAccountId, (BOOL *)&spProvisioningAgent);
      if ( LODWORD(spProvisioningAgent.ptr_) )
      {
        pszNetworkAccountId = 0;
        v6 = -2147024809;
      }
      else
      {
        StringRawBuffer = WindowsGetStringRawBuffer(NetworkAccountId, 0);
        pszNetworkAccountId = StringRawBuffer;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_S(
            WPP_GLOBAL_Control->Control.Logger,
            0x11u,
            WPP_1550942edb28334490bbc72f882435cd_Traceguids,
            StringRawBuffer);
          StringRawBuffer = pszNetworkAccountId;
        }
        v8 = NetworkAccountBindingAccessCheck(StringRawBuffer);
        v11 = v8;
        if ( v8 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_S(
              WPP_GLOBAL_Control->Control.Logger,
              0x12u,
              WPP_1550942edb28334490bbc72f882435cd_Traceguids,
              pszNetworkAccountId);
          }
          spProvisioningAgent.ptr_ = 0;
          f.spProvisioningAgent = &spProvisioningAgent;
          f.pszNetworkAccountId = &pszNetworkAccountId;
          v6 = ExecuteAndConvertException__Windows::Networking::NetworkOperators::ProvisioningAgentStaticMethods::CreateFromNetworkAccountId_::_20_::_lambda_1___(&f);
          if ( v6 >= 0 )
          {
            ptr = spProvisioningAgent.ptr_;
            QueryInterface = spProvisioningAgent.ptr_->QueryInterface;
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spIProvisioningAgent);
            v6 = QueryInterface(ptr, &GUID_217700e0_8201_11df_adb9_f4ce462d9137, (void **)&spIProvisioningAgent.ptr_);
            if ( v6 >= 0 )
            {
              v14 = spIProvisioningAgent.ptr_;
              spIProvisioningAgent.ptr_ = 0;
              *ppProvisioningAgent = v14;
            }
          }
          v15 = spProvisioningAgent.ptr_;
          if ( spProvisioningAgent.ptr_ )
          {
            spProvisioningAgent.ptr_ = 0;
            v15->Release(v15);
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_ddP(WPP_GLOBAL_Control->Control.Logger, v9, v10, v8, v17, v18);
          }
          ErrorReportUtils::TransformError(v11, v9, (unsigned __int16)v10);
          v6 = -2147024891;
        }
      }
      v5 = WPP_GLOBAL_Control;
    }
    else
    {
      v6 = -2147467261;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  if ( v5 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v5->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v5->Control.Logger, 0x13u, WPP_1550942edb28334490bbc72f882435cd_Traceguids, v6);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::UI::Popups::IUICommand *>,Windows::Foundation::IAsyncOperation<Windows::UI::Popups::IUICommand *> >'::`2'::FTMEventDelegate> *)&spIProvisioningAgent);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800595a0  mov     [rsp-18h+arg_0], rbx
0x1800595a5  mov     [rsp-18h+arg_8], rsi
0x1800595aa  push    rbp
0x1800595ab  push    rdi
0x1800595ac  push    r12
0x1800595ae  mov     rbp, rsp
0x1800595b1  sub     rsp, 60h
0x1800595b5  mov     rax, cs:__security_cookie
0x1800595bc  xor     rax, rsp
0x1800595bf  mov     [rbp+var_8], rax
0x1800595c3  mov     rsi, ppProvisioningAgent
0x1800595c6  mov     rbx, NetworkAccountId
0x1800595c9  mov     [rbp+spIProvisioningAgent.ptr_], 0
0x1800595d1  mov     [rbp+pszNetworkAccountId], 0
0x1800595d9  lea     r12, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800595e0  mov     this, cs:WPP_GLOBAL_Control
0x1800595e7  cmp     this, r12
0x1800595ea  jz      short loc_18005960E
0x1800595ec  test    byte ptr [this+1Ch], 10h
0x1800595f0  jz      short loc_18005960E
0x1800595f2  mov     edx, 10h; id
0x1800595f7  lea     ppProvisioningAgent, WPP_1550942edb28334490bbc72f882435cd_Traceguids; TraceGuid
0x1800595fe  mov     this, [this+10h]; Logger
0x180059602  call    WPP_SF_
0x180059607  mov     this, cs:WPP_GLOBAL_Control
0x18005960e  test    rbx, rbx
0x180059611  jnz     short loc_18005961D
0x180059613  mov     ebx, 80070057h
0x180059618  jmp     loc_18005978F
0x18005961d  test    rsi, rsi
0x180059620  jnz     short loc_18005962C
0x180059622  mov     ebx, 80004003h
0x180059627  jmp     loc_18005978F
0x18005962c  mov     qword ptr [rsi], 0
0x180059633  mov     dword ptr [rbp+spProvisioningAgent.ptr_], 0
0x18005963a  lea     NetworkAccountId, [rbp+spProvisioningAgent]; hasEmbedNull
0x18005963e  mov     this, rbx; string
0x180059641  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180059647  cmp     dword ptr [rbp+spProvisioningAgent.ptr_], 0
0x18005964b  jz      short loc_18005965F
0x18005964d  mov     [rbp+pszNetworkAccountId], 0
0x180059655  mov     ebx, 80070057h
0x18005965a  jmp     loc_180059788
0x18005965f  xor     edx, edx; length
0x180059661  mov     this, rbx; string
0x180059664  call    cs:__imp_WindowsGetStringRawBuffer
0x18005966a  mov     [rbp+pszNetworkAccountId], rax
0x18005966e  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180059675  cmp     this, r12
0x180059678  jz      short loc_18005969C
0x18005967a  test    byte ptr [this+1Ch], 10h
0x18005967e  jz      short loc_18005969C
0x180059680  mov     edx, 11h; id
0x180059685  mov     r9, rax; _a1
0x180059688  lea     ppProvisioningAgent, WPP_1550942edb28334490bbc72f882435cd_Traceguids; TraceGuid
0x18005968f  mov     this, [this+10h]; Logger
0x180059693  call    WPP_SF_S
0x180059698  mov     rax, [rbp+pszNetworkAccountId]
0x18005969c  mov     this, rax
0x18005969f  call    cs:__imp_NetworkAccountBindingAccessCheck
0x1800596a5  mov     ebx, eax
0x1800596a7  test    eax, eax
0x1800596a9  jns     short loc_1800596DA
0x1800596ab  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800596b2  cmp     this, r12
0x1800596b5  jz      short loc_1800596C9
0x1800596b7  test    byte ptr [this+1Ch], 10h
0x1800596bb  jz      short loc_1800596C9
0x1800596bd  mov     r9d, eax; id
0x1800596c0  mov     this, [this+10h]; Logger
0x1800596c4  call    WPP_SF_ddP
0x1800596c9  mov     ecx, ebx; oldHr
0x1800596cb  call    ?TransformError@ErrorReportUtils@@YAXJJG@Z; ErrorReportUtils::TransformError(long,long,ushort)
0x1800596d0  mov     ebx, 80070005h
0x1800596d5  jmp     loc_180059788
0x1800596da  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800596e1  cmp     this, r12
0x1800596e4  jz      short loc_180059705
0x1800596e6  test    byte ptr [this+1Ch], 10h
0x1800596ea  jz      short loc_180059705
0x1800596ec  mov     edx, 12h; id
0x1800596f1  mov     r9, [rbp+pszNetworkAccountId]; _a1
0x1800596f5  lea     ppProvisioningAgent, WPP_1550942edb28334490bbc72f882435cd_Traceguids; TraceGuid
0x1800596fc  mov     this, [this+10h]; Logger
0x180059700  call    WPP_SF_S
0x180059705  mov     [rbp+spProvisioningAgent.ptr_], 0
0x18005970d  lea     rax, [rbp+spProvisioningAgent]
0x180059711  mov     [rbp+f.spProvisioningAgent], rax
0x180059715  lea     rax, [rbp+pszNetworkAccountId]
0x180059719  mov     [rbp+f.pszNetworkAccountId], rax
0x18005971d  lea     this, [rbp+f]; f
0x180059721  call    ExecuteAndConvertException__Windows__Networking__NetworkOperators__ProvisioningAgentStaticMethods__CreateFromNetworkAccountId____20____lambda_1___
0x180059726  mov     ebx, eax
0x180059728  test    eax, eax
0x18005972a  js      short loc_18005976A
0x18005972c  mov     rbx, [rbp+spProvisioningAgent.ptr_]
0x180059730  mov     rax, [rbx]
0x180059733  mov     rdi, [rax]
0x180059736  lea     this, [rbp+spIProvisioningAgent]; this
0x18005973a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005973f  lea     ppProvisioningAgent, [rbp+spIProvisioningAgent]
0x180059743  lea     NetworkAccountId, _GUID_217700e0_8201_11df_adb9_f4ce462d9137
0x18005974a  mov     this, rbx
0x18005974d  mov     rax, rdi
0x180059750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059755  mov     ebx, eax
0x180059757  test    eax, eax
0x180059759  js      short loc_18005976A
0x18005975b  mov     rax, [rbp+spIProvisioningAgent.ptr_]
0x18005975f  mov     [rbp+spIProvisioningAgent.ptr_], 0
0x180059767  mov     [rsi], rax
0x18005976a  mov     this, [rbp+spProvisioningAgent.ptr_]
0x18005976e  test    this, this
0x180059771  jz      short loc_180059788
0x180059773  mov     [rbp+spProvisioningAgent.ptr_], 0
0x18005977b  mov     rax, [this]
0x18005977e  mov     rax, [rax+10h]
0x180059782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059787  nop
0x180059788  mov     this, cs:WPP_GLOBAL_Control
0x18005978f  cmp     this, r12; __annotation("TMF:",
0x180059792  jz      short loc_1800597B3
0x180059794  test    byte ptr [this+1Ch], 10h
0x180059798  jz      short loc_1800597B3
0x18005979a  mov     edx, 13h; id
0x18005979f  mov     r9d, ebx; _a1
0x1800597a2  lea     ppProvisioningAgent, WPP_1550942edb28334490bbc72f882435cd_Traceguids; TraceGuid
0x1800597a9  mov     this, [this+10h]; Logger
0x1800597ad  call    WPP_SF_d
0x1800597b2  nop
0x1800597b3  lea     this, [rbp+spIProvisioningAgent]; this
0x1800597b7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800597bc  mov     eax, ebx
0x1800597be  mov     this, [rbp+var_8]
0x1800597c2  xor     this, rsp; StackCookie
0x1800597c5  call    __security_check_cookie
0x1800597ca  lea     r11, [rsp+60h+var_s0]
0x1800597cf  mov     rbx, [r11+20h]
0x1800597d3  mov     rsi, [r11+28h]
0x1800597d7  mov     rsp, r11
0x1800597da  pop     r12
0x1800597dc  pop     rdi
0x1800597dd  pop     rbp
0x1800597de  retn
```
