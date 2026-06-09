# Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation::OnStart(void)

- ea: `0x180061b40`
- end: `0x180061e07`
- name: `?OnStart@ProvisionFromXmlDocumentOperation@NetworkOperators@Networking@Windows@@UEAAJXZ`
- size: `711`
- prototype: `HRESULT __fastcall(Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002790`
- `0x180010984`
- `0x180012748`
- `0x180012770`
- `0x180012988`
- `0x180061b40`
- `0x180063dd8`
- `0x180063ef8`
- `0x18006406c`
- `0x180067438`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061cbb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180061cbb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180061d9a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180061d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061d45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061d45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061db2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061db2`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180061d1a`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180061d1a`

## pseudocode

```c
__int64 __fastcall Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation::OnStart(
        Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation *this)
{
  int IsAppContainer; // ebx
  WPP_PROJECT_CONTROL_BLOCK *v3; // rcx
  HWND__ *_a2; // rax
  bool v5; // bl
  int Window; // eax
  HANDLE EventW; // rax
  signed int LastError; // eax
  signed int v9; // eax
  void *m_callbackReadyEvent; // rcx
  bool isCallerAppContainer; // [rsp+30h] [rbp-48h] BYREF
  HWND__ *parentWindow; // [rsp+38h] [rbp-40h] BYREF

  this->AddRef(this);
  isCallerAppContainer = 0;
  IsAppContainer = CallingApp::CallerIsAppContainer(&isCallerAppContainer);
  if ( IsAppContainer >= 0 )
  {
    if ( isCallerAppContainer )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xCu, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
        v3 = WPP_GLOBAL_Control;
      }
      _a2 = this->m_parentWindow;
      v5 = 0;
      if ( _a2 )
      {
        LODWORD(_a2) = CallerIdentity::VerifyWindowIsInCallingProcessAppContainer(this->m_parentWindow);
        v3 = WPP_GLOBAL_Control;
        v5 = (int)_a2 >= 0;
      }
      if ( v3 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v3->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_dd(v3->Control.Logger, 0x10u, WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids, v5, (int)_a2);
        v3 = WPP_GLOBAL_Control;
      }
      if ( !v5 )
      {
        if ( v3 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v3->ReserveSpace[28] & 0x10) != 0 )
          WPP_SF_(v3->Control.Logger, 0xDu, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
        parentWindow = 0;
        Window = CallingApp::GetWindow(&parentWindow);
        if ( Window < 0 )
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xEu, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids, Window);
          }
          this->m_parentWindow = 0;
        }
        else
        {
          this->m_parentWindow = parentWindow;
        }
      }
    }
    parentWindow = (HWND__ *)&this->m_callerAppId;
    if ( ExecuteAndConvertException__CallingApp::GetCallerAppId_::_2_::_lambda_1___((const CallingApp::GetCallerAppId::__l2::<lambda_1> *)&parentWindow) < 0 )
      std::wstring::_Eos(&this->m_callerAppId, 0);
    EventW = CreateEventW(0, 0, 0, 0);
    this->m_callbackReadyEvent = EventW;
    if ( EventW )
      goto LABEL_28;
    LastError = GetLastError();
    IsAppContainer = LastError;
    if ( LastError > 0 )
      IsAppContainer = (unsigned __int16)LastError | 0x80070000;
    if ( IsAppContainer >= 0 )
    {
LABEL_28:
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xFu, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
      }
      if ( TrySubmitThreadpoolCallback(
             Windows::Networking::NetworkOperators::ProvisionFromXmlDocumentOperation::ProvisionCallbackThunk,
             this,
             0) )
      {
        goto LABEL_38;
      }
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x10u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
      }
      v9 = GetLastError();
      IsAppContainer = v9;
      if ( v9 > 0 )
        IsAppContainer = (unsigned __int16)v9 | 0x80070000;
      this->Release(this);
      if ( IsAppContainer >= 0 )
      {
LABEL_38:
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x11u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids);
        }
        WaitForSingleObject(this->m_callbackReadyEvent, 0xFFFFFFFF);
        IsAppContainer = this->m_hrCallbackInit;
      }
    }
  }
  m_callbackReadyEvent = this->m_callbackReadyEvent;
  if ( m_callbackReadyEvent )
  {
    CloseHandle(m_callbackReadyEvent);
    this->m_callbackReadyEvent = 0;
  }
  if ( IsAppContainer < 0
    && WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x12u, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids, IsAppContainer);
  }
  return (unsigned int)IsAppContainer;
}

```

## disassembly

```asm
0x180061b40  push    rbx
0x180061b42  push    rdi
0x180061b43  push    r14
0x180061b45  push    r15
0x180061b47  sub     rsp, 58h
0x180061b4b  mov     rax, cs:__security_cookie
0x180061b52  xor     rax, rsp
0x180061b55  mov     [rsp+78h+var_38], rax
0x180061b5a  mov     rax, [this]
0x180061b5d  mov     rdi, this
0x180061b60  mov     rax, [rax+8]
0x180061b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061b69  lea     this, [rsp+78h+isCallerAppContainer]; IsCallerAppContainer
0x180061b6e  mov     [rsp+78h+isCallerAppContainer], 0
0x180061b73  call    ?CallerIsAppContainer@CallingApp@@YAJAEA_N@Z; CallingApp::CallerIsAppContainer(bool &)
0x180061b78  lea     r14, WPP_GLOBAL_Control
0x180061b7f  mov     ebx, eax
0x180061b81  lea     r15, WPP_7f56b8631f363c4b3499dccd96f8c152_Traceguids
0x180061b88  test    eax, eax
0x180061b8a  js      loc_180061DA6
0x180061b90  cmp     [rsp+78h+isCallerAppContainer], 0
0x180061b95  jz      loc_180061C8D
0x180061b9b  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180061ba2  cmp     this, r14
0x180061ba5  jz      short loc_180061BC5
0x180061ba7  test    byte ptr [this+1Ch], 10h
0x180061bab  jz      short loc_180061BC5
0x180061bad  mov     this, [this+10h]; Logger
0x180061bb1  mov     edx, 0Ch; id
0x180061bb6  mov     r8, r15; TraceGuid
0x180061bb9  call    WPP_SF_
0x180061bbe  mov     this, cs:WPP_GLOBAL_Control
0x180061bc5  mov     rax, [rdi+0A8h]
0x180061bcc  xor     bl, bl
0x180061bce  test    rax, rax
0x180061bd1  jz      short loc_180061BE8
0x180061bd3  mov     this, rax; hwnd
0x180061bd6  call    ?VerifyWindowIsInCallingProcessAppContainer@CallerIdentity@@YAJPEAUHWND__@@@Z; CallerIdentity::VerifyWindowIsInCallingProcessAppContainer(HWND__ *)
0x180061bdb  mov     this, cs:WPP_GLOBAL_Control
0x180061be2  test    eax, eax
0x180061be4  js      short loc_180061BE8
0x180061be6  mov     bl, 1
0x180061be8  cmp     this, r14; __annotation("TMF:",
0x180061beb  jz      short loc_180061C17
0x180061bed  test    byte ptr [this+1Ch], 10h
0x180061bf1  jz      short loc_180061C17
0x180061bf3  mov     this, [this+10h]; Logger
0x180061bf7  lea     r8, WPP_23c62c4a87f335c33f4b82b787c27e30_Traceguids; TraceGuid
0x180061bfe  movzx   r9d, bl; _a1
0x180061c02  mov     edx, 10h; id
0x180061c07  mov     [rsp+78h+_a2], eax; _a2
0x180061c0b  call    WPP_SF_dd
0x180061c10  mov     this, cs:WPP_GLOBAL_Control
0x180061c17  test    bl, bl
0x180061c19  jnz     short loc_180061C8D
0x180061c1b  cmp     this, r14; __annotation("TMF:",
0x180061c1e  jz      short loc_180061C37
0x180061c20  test    byte ptr [this+1Ch], 10h
0x180061c24  jz      short loc_180061C37
0x180061c26  mov     this, [this+10h]; Logger
0x180061c2a  mov     edx, 0Dh; id
0x180061c2f  mov     r8, r15; TraceGuid
0x180061c32  call    WPP_SF_
0x180061c37  lea     this, [rsp+78h+parentWindow]; pwnd
0x180061c3c  mov     [rsp+78h+parentWindow], 0
0x180061c45  call    ?GetWindow@CallingApp@@YAJPEAPEAUHWND__@@@Z; CallingApp::GetWindow(HWND__ * *)
0x180061c4a  test    eax, eax
0x180061c4c  js      short loc_180061C5C
0x180061c4e  mov     rax, [rsp+78h+parentWindow]
0x180061c53  mov     [rdi+0A8h], rax
0x180061c5a  jmp     short loc_180061C8D
0x180061c5c  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180061c63  cmp     this, r14
0x180061c66  jz      short loc_180061C82
0x180061c68  test    byte ptr [this+1Ch], 10h
0x180061c6c  jz      short loc_180061C82
0x180061c6e  mov     this, [this+10h]; Logger
0x180061c72  mov     edx, 0Eh; id
0x180061c77  mov     r9d, eax; _a1
0x180061c7a  mov     r8, r15; TraceGuid
0x180061c7d  call    WPP_SF_d
0x180061c82  mov     qword ptr [rdi+0A8h], 0
0x180061c8d  lea     rbx, [rdi+0C0h]
0x180061c94  lea     this, [rsp+78h+parentWindow]; f
0x180061c99  mov     [rsp+78h+parentWindow], rbx
0x180061c9e  call    ExecuteAndConvertException__CallingApp__GetCallerAppId____2____lambda_1___
0x180061ca3  test    eax, eax
0x180061ca5  jns     short loc_180061CB1
0x180061ca7  xor     edx, edx; _New_size
0x180061ca9  mov     this, rbx; this
0x180061cac  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x180061cb1  xor     r9d, r9d; lpName
0x180061cb4  xor     r8d, r8d; bInitialState
0x180061cb7  xor     edx, edx; bManualReset
0x180061cb9  xor     ecx, ecx; lpEventAttributes
0x180061cbb  call    cs:__imp_CreateEventW
0x180061cc1  mov     [rdi+0B0h], rax
0x180061cc8  test    rax, rax
0x180061ccb  jnz     short loc_180061CEA
0x180061ccd  call    cs:__imp_GetLastError
0x180061cd3  mov     ebx, eax
0x180061cd5  test    eax, eax
0x180061cd7  jle     short loc_180061CE2
0x180061cd9  movzx   ebx, ax
0x180061cdc  or      ebx, 80070000h
0x180061ce2  test    ebx, ebx
0x180061ce4  js      loc_180061DA6
0x180061cea  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180061cf1  cmp     this, r14
0x180061cf4  jz      short loc_180061D0D
0x180061cf6  test    byte ptr [this+1Ch], 10h
0x180061cfa  jz      short loc_180061D0D
0x180061cfc  mov     this, [this+10h]; Logger
0x180061d00  mov     edx, 0Fh; id
0x180061d05  mov     r8, r15; TraceGuid
0x180061d08  call    WPP_SF_
0x180061d0d  xor     r8d, r8d; pcbe
0x180061d10  lea     this, ?ProvisionCallbackThunk@ProvisionFromXmlDocumentOperation@NetworkOperators@Networking@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x180061d17  mov     rdx, rdi; pv
0x180061d1a  call    cs:__imp_TrySubmitThreadpoolCallback
0x180061d20  test    eax, eax
0x180061d22  jnz     short loc_180061D6D
0x180061d24  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180061d2b  cmp     this, r14
0x180061d2e  jz      short loc_180061D45
0x180061d30  test    byte ptr [this+1Ch], 2
0x180061d34  jz      short loc_180061D45
0x180061d36  mov     this, [this+10h]; Logger
0x180061d3a  lea     edx, [rax+10h]; id
0x180061d3d  mov     r8, r15; TraceGuid
0x180061d40  call    WPP_SF_
0x180061d45  call    cs:__imp_GetLastError
0x180061d4b  mov     ebx, eax
0x180061d4d  test    eax, eax
0x180061d4f  jle     short loc_180061D5A
0x180061d51  movzx   ebx, ax
0x180061d54  or      ebx, 80070000h
0x180061d5a  mov     rax, [rdi]
0x180061d5d  mov     this, rdi
0x180061d60  mov     rax, [rax+10h]
0x180061d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061d69  test    ebx, ebx
0x180061d6b  js      short loc_180061DA6
0x180061d6d  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180061d74  cmp     this, r14
0x180061d77  jz      short loc_180061D90
0x180061d79  test    byte ptr [this+1Ch], 10h
0x180061d7d  jz      short loc_180061D90
0x180061d7f  mov     this, [this+10h]; Logger
0x180061d83  mov     edx, 11h; id
0x180061d88  mov     r8, r15; TraceGuid
0x180061d8b  call    WPP_SF_
0x180061d90  mov     this, [rdi+0B0h]; hHandle
0x180061d97  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180061d9a  call    cs:__imp_WaitForSingleObject
0x180061da0  mov     ebx, [rdi+0B8h]
0x180061da6  mov     this, [rdi+0B0h]; hObject
0x180061dad  test    this, this
0x180061db0  jz      short loc_180061DC3
0x180061db2  call    cs:__imp_CloseHandle
0x180061db8  mov     qword ptr [rdi+0B0h], 0
0x180061dc3  test    ebx, ebx
0x180061dc5  jns     short loc_180061DED
0x180061dc7  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180061dce  cmp     this, r14
0x180061dd1  jz      short loc_180061DED
0x180061dd3  test    byte ptr [this+1Ch], 2
0x180061dd7  jz      short loc_180061DED
0x180061dd9  mov     this, [this+10h]; Logger
0x180061ddd  mov     edx, 12h; id
0x180061de2  mov     r9d, ebx; _a1
0x180061de5  mov     r8, r15; TraceGuid
0x180061de8  call    WPP_SF_d
0x180061ded  mov     eax, ebx
0x180061def  mov     this, [rsp+78h+var_38]
0x180061df4  xor     this, rsp; StackCookie
0x180061df7  call    __security_check_cookie
0x180061dfc  add     rsp, 58h
0x180061e00  pop     r15
0x180061e02  pop     r14
0x180061e04  pop     rdi
0x180061e05  pop     rbx
0x180061e06  retn
```
