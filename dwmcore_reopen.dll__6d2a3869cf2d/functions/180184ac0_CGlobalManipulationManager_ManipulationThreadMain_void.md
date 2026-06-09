# CGlobalManipulationManager::ManipulationThreadMain(void)

- ea: `0x180184ac0`
- end: `0x180184d01`
- name: `?ManipulationThreadMain@CGlobalManipulationManager@@EEAAJXZ`
- size: `577`
- prototype: `__int64 __fastcall(CGlobalManipulationManager *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180049470`
- `0x180131dc0`
- `0x180184ac0`
- `0x180184d10`
- `0x180184d8c`
- `0x180204120`
- `0x1802284b0`
- `0x1802297e0`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180184b4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180184b6f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180184b4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180184b6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180184b3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180184b5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180184b3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180184b5b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180184c91`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180184c91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180184b96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180184b96`
- `CoreMessaging!CoreUICreateEx` at `0x180184b1c`
- `CoreMessaging!CoreUICreateEx` at `0x180184b1c`
- `ext-ms-win-compositor-hosting-l1-2-0!RegisterManipulationThread` at `0x180184b8c`
- `ext-ms-win-compositor-hosting-l1-2-0!RegisterManipulationThread` at `0x180184b8c`

## pseudocode

```c
__int64 __fastcall CGlobalManipulationManager::ManipulationThreadMain(
        CGlobalManipulationManager *this,
        __int64 a2,
        __int64 a3)
{
  struct IMessageSession **v4; // rdi
  int v5; // eax
  __int64 v6; // r8
  signed int LastError; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  _BYTE v13[16]; // [rsp+30h] [rbp-28h] BYREF
  void *retaddr; // [rsp+58h] [rbp+0h]

  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x4000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      &MANIPULATION_THREAD_STARTUP,
      a3,
      1,
      v13);
  v4 = (struct IMessageSession **)((char *)this + 24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
  v5 = CoreUICreateEx(1, (char *)this + 24);
  if ( v5 < 0 )
    ModuleFailFastForHRESULT(v5, retaddr);
  EnterCriticalSection(&stru_1803B9968);
  byte_1803B9964 = 0;
  LeaveCriticalSection(&stru_1803B9968);
  EnterCriticalSection(&stru_1803B9928);
  byte_1803B9924 = 0;
  LeaveCriticalSection(&stru_1803B9928);
  if ( (unsigned __int8)IsRegisterManipulationThreadPresent() )
  {
    if ( !(unsigned int)RegisterManipulationThread(CManipulationManager::ManipulationThreadCallback, this) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2003304445;
      ModuleFailFastForHRESULT(LastError, retaddr);
    }
    CGlobalManipulationManager::UpdateMMCSSTask(this);
    v8 = CManipulationManager::SetupMessageCallThreadInfo(
           this,
           *v4,
           (int (*)(void *, const void *, int))CManipulationManager::s_ManipulationThreadEndpointProc,
           (CGlobalManipulationManager *)((char *)this + 32));
    if ( v8 < 0 )
      ModuleFailFastForHRESULT(v8, retaddr);
    v9 = (*(__int64 (__fastcall **)(struct IMessageSession *, HANDLE, __int64 (__fastcall *)(), CGlobalManipulationManager *))(*(_QWORD *)*v4 + 272LL))(
           *v4,
           hEvent,
           CGlobalManipulationManager::ManipulationThreadMain_::_25_::_lambda_1_::_lambda_invoker_cdecl_,
           this);
    if ( v9 < 0 )
      ModuleFailFastForHRESULT(v9, retaddr);
    v10 = (*(__int64 (__fastcall **)(struct IMessageSession *, void * near *, __int64 (__fastcall *)(), CGlobalManipulationManager *))(*(_QWORD *)*v4 + 272LL))(
            *v4,
            CManipulationManager::s_rghWaitEvents,
            CGlobalManipulationManager::ManipulationThreadMain_::_30_::_lambda_2_::_lambda_invoker_cdecl_,
            this);
    if ( v10 < 0 )
      ModuleFailFastForHRESULT(v10, retaddr);
    v11 = (*(__int64 (__fastcall **)(struct IMessageSession *, HANDLE, __int64 (__fastcall *)(), CGlobalManipulationManager *))(*(_QWORD *)*v4 + 272LL))(
            *v4,
            qword_1803BB140,
            CGlobalManipulationManager::ManipulationThreadMain_::_35_::_lambda_3_::_lambda_invoker_cdecl_,
            this);
    if ( v11 < 0 )
      ModuleFailFastForHRESULT(v11, retaddr);
    SetEvent(CManipulationManager::s_hManipThreadInitializedWaitEvent);
    (*(void (__fastcall **)(struct IMessageSession *))(*(_QWORD *)*v4 + 232LL))(*v4);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
  }
  CManipulationManager::s_dwManipulationThreadId = 0;
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x4000) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      &MANIPULATION_THREAD_CLEANUP,
      v6,
      1,
      v13);
  return 0;
}

```

## disassembly

```asm
0x180184ac0  mov     [rsp+arg_8], rbx
0x180184ac5  push    rdi
0x180184ac6  sub     rsp, 50h
0x180184aca  mov     rax, cs:__security_cookie
0x180184ad1  xor     rax, rsp
0x180184ad4  mov     [rsp+58h+var_18], rax
0x180184ad9  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 40h
0x180184ae0  mov     rbx, rcx
0x180184ae3  jz      short loc_180184B08
0x180184ae5  lea     rax, [rsp+58h+var_28]
0x180184aea  mov     r9d, 1
0x180184af0  lea     rdx, MANIPULATION_THREAD_STARTUP
0x180184af7  mov     [rsp+58h+var_38], rax
0x180184afc  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180184b03  call    McGenEventWrite_EventWriteTransfer
0x180184b08  lea     rdi, [rbx+18h]
0x180184b0c  mov     rcx, rdi
0x180184b0f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180184b14  mov     rdx, rdi
0x180184b17  mov     ecx, 1
0x180184b1c  call    cs:__imp_CoreUICreateEx
0x180184b22  test    eax, eax
0x180184b24  jns     short loc_180184B33
0x180184b26  mov     rdx, [rsp+58h]; void *
0x180184b2b  mov     ecx, eax; int
0x180184b2d  call    ModuleFailFastForHRESULT
0x180184b33  lea     rcx, stru_1803B9968; lpCriticalSection
0x180184b3a  call    cs:__imp_EnterCriticalSection
0x180184b40  lea     rcx, stru_1803B9968; lpCriticalSection
0x180184b47  mov     cs:byte_1803B9964, 0
0x180184b4e  call    cs:__imp_LeaveCriticalSection
0x180184b54  lea     rcx, stru_1803B9928; lpCriticalSection
0x180184b5b  call    cs:__imp_EnterCriticalSection
0x180184b61  lea     rcx, stru_1803B9928; lpCriticalSection
0x180184b68  mov     cs:byte_1803B9924, 0
0x180184b6f  call    cs:__imp_LeaveCriticalSection
0x180184b75  call    IsRegisterManipulationThreadPresent
0x180184b7a  test    al, al
0x180184b7c  jz      loc_180184CB1
0x180184b82  mov     rdx, rbx
0x180184b85  lea     rcx, ?ManipulationThreadCallback@CManipulationManager@@SAHPEAU_MIT_INPUT_INTEROP_MESSAGE@@PEAX@Z; CManipulationManager::ManipulationThreadCallback(_MIT_INPUT_INTEROP_MESSAGE *,void *)
0x180184b8c  call    cs:__imp_RegisterManipulationThread
0x180184b92  test    eax, eax
0x180184b94  jnz     short loc_180184BBF
0x180184b96  call    cs:__imp_GetLastError
0x180184b9c  test    eax, eax
0x180184b9e  jle     short loc_180184BA8
0x180184ba0  movzx   eax, ax
0x180184ba3  or      eax, 80070000h
0x180184ba8  mov     rdx, [rsp+58h]; void *
0x180184bad  mov     ecx, 88980003h
0x180184bb2  test    eax, eax
0x180184bb4  cmovns  eax, ecx
0x180184bb7  mov     ecx, eax; int
0x180184bb9  call    ModuleFailFastForHRESULT
0x180184bbf  mov     rcx, rbx; this
0x180184bc2  call    ?UpdateMMCSSTask@CGlobalManipulationManager@@UEAAJXZ; CGlobalManipulationManager::UpdateMMCSSTask(void)
0x180184bc7  mov     rdx, [rdi]; struct IMessageSession *
0x180184bca  lea     r9, [rbx+20h]; struct CManipulationManager::MessageCallThreadInfo *
0x180184bce  lea     r8, ?s_ManipulationThreadEndpointProc@CManipulationManager@@KAJPEAXPEBXH@Z; int (*)(void *, const void *, int)
0x180184bd5  mov     rcx, rbx; this
0x180184bd8  call    ?SetupMessageCallThreadInfo@CManipulationManager@@IEAAJPEAUIMessageSession@@P6AJPEAXPEBXH@ZPEAUMessageCallThreadInfo@1@@Z; CManipulationManager::SetupMessageCallThreadInfo(IMessageSession *,long (*)(void *,void const *,int),CManipulationManager::MessageCallThreadInfo *)
0x180184bdd  test    eax, eax
0x180184bdf  jns     short loc_180184BEE
0x180184be1  mov     rdx, [rsp+58h]; void *
0x180184be6  mov     ecx, eax; int
0x180184be8  call    ModuleFailFastForHRESULT
0x180184bee  mov     rcx, [rdi]
0x180184bf1  lea     r8, _CGlobalManipulationManager__ManipulationThreadMain____25____lambda_1____lambda_invoker_cdecl_
0x180184bf8  mov     rdx, cs:hEvent
0x180184bff  mov     r9, rbx
0x180184c02  mov     rax, [rcx]
0x180184c05  mov     rax, [rax+110h]
0x180184c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184c11  test    eax, eax
0x180184c13  jns     short loc_180184C22
0x180184c15  mov     rdx, [rsp+58h]; void *
0x180184c1a  mov     ecx, eax; int
0x180184c1c  call    ModuleFailFastForHRESULT
0x180184c22  mov     rcx, [rdi]
0x180184c25  lea     r8, _CGlobalManipulationManager__ManipulationThreadMain____30____lambda_2____lambda_invoker_cdecl_
0x180184c2c  mov     rdx, cs:?s_rghWaitEvents@CManipulationManager@@1PAPEAXA; void * near * CManipulationManager::s_rghWaitEvents
0x180184c33  mov     r9, rbx
0x180184c36  mov     rax, [rcx]
0x180184c39  mov     rax, [rax+110h]
0x180184c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184c45  test    eax, eax
0x180184c47  jns     short loc_180184C56
0x180184c49  mov     rdx, [rsp+58h]; void *
0x180184c4e  mov     ecx, eax; int
0x180184c50  call    ModuleFailFastForHRESULT
0x180184c56  mov     rcx, [rdi]
0x180184c59  lea     r8, _CGlobalManipulationManager__ManipulationThreadMain____35____lambda_3____lambda_invoker_cdecl_
0x180184c60  mov     rdx, cs:qword_1803BB140
0x180184c67  mov     r9, rbx
0x180184c6a  mov     rax, [rcx]
0x180184c6d  mov     rax, [rax+110h]
0x180184c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184c79  test    eax, eax
0x180184c7b  jns     short loc_180184C8A
0x180184c7d  mov     rdx, [rsp+58h]; void *
0x180184c82  mov     ecx, eax; int
0x180184c84  call    ModuleFailFastForHRESULT
0x180184c8a  mov     rcx, cs:?s_hManipThreadInitializedWaitEvent@CManipulationManager@@1PEAXEA; hEvent
0x180184c91  call    cs:__imp_SetEvent
0x180184c97  mov     rcx, [rdi]
0x180184c9a  mov     rax, [rcx]
0x180184c9d  mov     rax, [rax+0E8h]
0x180184ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180184ca9  mov     rcx, rdi
0x180184cac  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180184cb1  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits+1, 40h
0x180184cb8  mov     cs:?s_dwManipulationThreadId@CManipulationManager@@1KA, 0; ulong CManipulationManager::s_dwManipulationThreadId
0x180184cc2  jz      short loc_180184CE7
0x180184cc4  lea     rax, [rsp+58h+var_28]
0x180184cc9  mov     r9d, 1
0x180184ccf  lea     rdx, MANIPULATION_THREAD_CLEANUP
0x180184cd6  mov     [rsp+58h+var_38], rax
0x180184cdb  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x180184ce2  call    McGenEventWrite_EventWriteTransfer
0x180184ce7  xor     eax, eax
0x180184ce9  mov     rcx, [rsp+58h+var_18]
0x180184cee  xor     rcx, rsp; StackCookie
0x180184cf1  call    __security_check_cookie
0x180184cf6  mov     rbx, [rsp+58h+arg_8]
0x180184cfb  add     rsp, 50h
0x180184cff  pop     rdi
0x180184d00  retn
```
