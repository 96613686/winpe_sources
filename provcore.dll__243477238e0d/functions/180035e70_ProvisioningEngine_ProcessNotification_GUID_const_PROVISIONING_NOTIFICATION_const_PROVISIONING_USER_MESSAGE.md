# ProvisioningEngine::ProcessNotification(_GUID const *,PROVISIONING_NOTIFICATION const *,PROVISIONING_USER_MESSAGE *)

- ea: `0x180035e70`
- end: `0x180036034`
- name: `?ProcessNotification@ProvisioningEngine@@UEAAJPEBU_GUID@@PEBUPROVISIONING_NOTIFICATION@@PEAUPROVISIONING_USER_MESSAGE@@@Z`
- size: `452`
- prototype: `HRESULT __fastcall(ProvisioningEngine *this, const _GUID *InterfaceGuid, const PROVISIONING_NOTIFICATION *Notification, PROVISIONING_USER_MESSAGE *UserMessage)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180012748`
- `0x180012770`
- `0x1800347f8`
- `0x180034b04`
- `0x180035bf8`
- `0x180035e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035efc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035efc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035fca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035f56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035fca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035f27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035fa0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035f27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180035fa0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180035f35`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180035fae`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180035f35`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180035fae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProvisioningEngine::ProcessNotification(
        ProvisioningEngine *this,
        const _GUID *InterfaceGuid,
        const PROVISIONING_NOTIFICATION *Notification,
        PROVISIONING_USER_MESSAGE *UserMessage)
{
  WPP_PROJECT_CONTROL_BLOCK *v8; // rcx
  int v9; // ebx
  ProvisioningEngine *v10; // r14
  bool v11; // bl
  char v12; // di
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE v15; // rax
  DWORD v16; // eax
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (__cdecl*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection,wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t> > > lock; // [rsp+20h] [rbp-58h] BYREF
  ProvisioningEngine::ProcessNotification::__l11::<lambda_1> f; // [rsp+28h] [rbp-50h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x24u, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !InterfaceGuid || !Notification || (v9 = 0, !Notification->Text) )
    v9 = -2147024809;
  if ( !UserMessage )
  {
    v9 = -2147467261;
    goto LABEL_23;
  }
  if ( v9 < 0 )
    goto LABEL_23;
  EnterCriticalSection((LPCRITICAL_SECTION)&this->m_msgTimeWindow);
  lock.m_ptr = (_RTL_CRITICAL_SECTION *)&this->m_msgTimeWindow;
  v10 = (ProvisioningEngine *)((char *)this - 8);
  v11 = IsMessageThrottlingRequired(v10->m_msgTimeWindow._Mypair._Myval2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&lock);
  v12 = 0;
  if ( v11 )
  {
    CurrentThread = GetCurrentThread();
    if ( SetThreadPriority(CurrentThread, 0x10000) )
    {
      v12 = 1;
    }
    else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
           && (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x25u, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids, LastError);
    }
  }
  f.__this = v10;
  f.InterfaceGuid = InterfaceGuid;
  f.Notification = Notification;
  f.UserMessage = UserMessage;
  v9 = ExecuteAndConvertAnyException__ProvisioningEngine::ProcessNotification_::_11_::_lambda_1___(&f);
  if ( !v12 || (v15 = GetCurrentThread(), SetThreadPriority(v15, 0x20000)) )
  {
LABEL_22:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_23;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    return (unsigned int)v9;
  if ( (WPP_GLOBAL_Control->ReserveSpace[28] & 4) != 0 )
  {
    v16 = GetLastError();
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x26u, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids, v16);
    goto LABEL_22;
  }
LABEL_23:
  if ( v8 != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control && (v8->ReserveSpace[28] & 0x10) != 0 )
    WPP_SF_d(v8->Control.Logger, 0x27u, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180035e70  mov     [rsp+arg_8], rbx
0x180035e75  mov     [rsp+arg_10], rbp
0x180035e7a  push    rsi
0x180035e7b  push    rdi
0x180035e7c  push    r12
0x180035e7e  push    r14
0x180035e80  push    r15
0x180035e82  sub     rsp, 50h
0x180035e86  mov     r15, UserMessage
0x180035e89  mov     rsi, Notification
0x180035e8c  mov     rbp, InterfaceGuid
0x180035e8f  mov     r14, this
0x180035e92  lea     r12, WPP_GLOBAL_Control; __annotation("TMF:",
0x180035e99  mov     this, cs:WPP_GLOBAL_Control
0x180035ea0  cmp     this, r12
0x180035ea3  jz      short loc_180035EC7
0x180035ea5  test    byte ptr [this+1Ch], 10h
0x180035ea9  jz      short loc_180035EC7
0x180035eab  mov     edx, 24h ; '$'; id
0x180035eb0  lea     Notification, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids; TraceGuid
0x180035eb7  mov     this, [this+10h]; Logger
0x180035ebb  call    WPP_SF_
0x180035ec0  mov     this, cs:WPP_GLOBAL_Control
0x180035ec7  test    rbp, rbp
0x180035eca  jz      short loc_180035ED9
0x180035ecc  test    rsi, rsi
0x180035ecf  jz      short loc_180035ED9
0x180035ed1  xor     ebx, ebx
0x180035ed3  cmp     [rsi+10h], rbx
0x180035ed7  jnz     short loc_180035EDE
0x180035ed9  mov     ebx, 80070057h
0x180035ede  test    r15, r15
0x180035ee1  jnz     short loc_180035EED
0x180035ee3  mov     ebx, 80004003h
0x180035ee8  jmp     loc_180035FF6
0x180035eed  test    ebx, ebx
0x180035eef  js      loc_180035FF6
0x180035ef5  lea     rbx, [r14+48h]
0x180035ef9  mov     this, rbx; lpCriticalSection
0x180035efc  call    cs:__imp_EnterCriticalSection
0x180035f02  mov     [rsp+78h+lock.m_ptr], rbx
0x180035f07  add     r14, 0FFFFFFFFFFFFFFF8h
0x180035f0b  mov     this, [r14+48h]; msgTimeWindow
0x180035f0f  call    ?IsMessageThrottlingRequired@@YA_NAEAV?$deque@_KV?$allocator@_K@std@@@std@@@Z; IsMessageThrottlingRequired(std::deque<unsigned __int64> &)
0x180035f14  mov     bl, al
0x180035f16  lea     this, [rsp+78h+lock]; this
0x180035f1b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180035f20  xor     dil, dil
0x180035f23  test    bl, bl
0x180035f25  jz      short loc_180035F7B
0x180035f27  call    cs:__imp_GetCurrentThread
0x180035f2d  mov     this, rax; hThread
0x180035f30  mov     edx, 10000h; nPriority
0x180035f35  call    cs:__imp_SetThreadPriority
0x180035f3b  test    eax, eax
0x180035f3d  jz      short loc_180035F44
0x180035f3f  mov     dil, 1
0x180035f42  jmp     short loc_180035F7B
0x180035f44  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180035f4b  cmp     rax, r12
0x180035f4e  jz      short loc_180035F7B
0x180035f50  test    byte ptr [rax+1Ch], 4
0x180035f54  jz      short loc_180035F7B
0x180035f56  call    cs:__imp_GetLastError
0x180035f5c  mov     edx, 25h ; '%'; id
0x180035f61  mov     r9d, eax; _a1
0x180035f64  lea     Notification, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids; TraceGuid
0x180035f6b  mov     this, cs:WPP_GLOBAL_Control
0x180035f72  mov     this, [this+10h]; Logger
0x180035f76  call    WPP_SF_d
0x180035f7b  mov     [rsp+78h+f.__this], r14
0x180035f80  mov     [rsp+78h+f.InterfaceGuid], rbp
0x180035f85  mov     [rsp+78h+f.Notification], rsi
0x180035f8a  mov     [rsp+78h+f.UserMessage], r15
0x180035f8f  lea     this, [rsp+78h+f]; f
0x180035f94  call    ExecuteAndConvertAnyException__ProvisioningEngine__ProcessNotification____11____lambda_1___
0x180035f99  mov     ebx, eax
0x180035f9b  test    dil, dil
0x180035f9e  jz      short loc_180035FEF
0x180035fa0  call    cs:__imp_GetCurrentThread
0x180035fa6  mov     this, rax; hThread
0x180035fa9  mov     edx, 20000h; nPriority
0x180035fae  call    cs:__imp_SetThreadPriority
0x180035fb4  test    eax, eax
0x180035fb6  jnz     short loc_180035FEF
0x180035fb8  mov     this, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180035fbf  cmp     this, r12
0x180035fc2  jz      short loc_180036019
0x180035fc4  test    byte ptr [this+1Ch], 4
0x180035fc8  jz      short loc_180035FF6
0x180035fca  call    cs:__imp_GetLastError
0x180035fd0  mov     edx, 26h ; '&'; id
0x180035fd5  mov     r9d, eax; _a1
0x180035fd8  lea     Notification, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids; TraceGuid
0x180035fdf  mov     this, cs:WPP_GLOBAL_Control
0x180035fe6  mov     this, [this+10h]; Logger
0x180035fea  call    WPP_SF_d
0x180035fef  mov     this, cs:WPP_GLOBAL_Control
0x180035ff6  cmp     this, r12; __annotation("TMF:",
0x180035ff9  jz      short loc_180036019
0x180035ffb  test    byte ptr [this+1Ch], 10h
0x180035fff  jz      short loc_180036019
0x180036001  mov     edx, 27h ; '''; id
0x180036006  mov     r9d, ebx; _a1
0x180036009  lea     Notification, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids; TraceGuid
0x180036010  mov     this, [this+10h]; Logger
0x180036014  call    WPP_SF_d
0x180036019  mov     eax, ebx
0x18003601b  lea     r11, [rsp+78h+var_28]
0x180036020  mov     rbx, [r11+38h]
0x180036024  mov     rbp, [r11+40h]
0x180036028  mov     rsp, r11
0x18003602b  pop     r15
0x18003602d  pop     r14
0x18003602f  pop     r12
0x180036031  pop     rdi
0x180036032  pop     rsi
0x180036033  retn
```
