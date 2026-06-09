# LPA::CoreLpa::Stop(void)

- ea: `0x1800733c4`
- end: `0x180073674`
- name: `?Stop@CoreLpa@LPA@@QEAAXXZ`
- size: `688`
- prototype: `void __fastcall(LPA::CoreLpa *__hidden this)`
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180073220`
- `0x1800732e4`
- `0x1800d8390`

## callees

- `0x1800017c8`
- `0x18000df90`
- `0x18000ebf4`
- `0x1800636dc`
- `0x180065170`
- `0x180072110`
- `0x180072198`
- `0x180073044`
- `0x1800733c4`
- `0x18007367c`
- `0x1800d7e50`
- `0x1800d7e80`
- `0x1800d7eb0`
- `0x1800d7ee4`
- `0x1800daa0c`
- `0x1800dabcc`
- `0x1800dae70`
- `0x1800eaeb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007353a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007353a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073602`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180073602`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800733f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800735ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800733f4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800735ef`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180073566`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180073566`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180073598`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180073598`

## string_xrefs

- `0x180073622`: `LpaServiceCore`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LPA::CoreLpa::Stop(LPA::CoreLpa *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  int v3; // esi
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // rax
  void *v17; // rsi
  int v18; // ebx
  HANDLE *v19; // rbx
  HANDLE *v20; // rbx
  __int64 v21; // rbx
  void *v22; // rcx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  HANDLE *p_Handles; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v27[2]; // [rsp+48h] [rbp-B8h] BYREF
  const char *v28; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v29[8]; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE Handles; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v31[72]; // [rsp+A8h] [rbp-58h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v3 = 1;
  if ( *((_DWORD *)this + 4) && *((_DWORD *)this + 4) != 3 )
  {
    LPA::CoreLpa::TransitionToState(this);
    LeaveCriticalSection(v2);
    Handles = (HANDLE)-1LL;
    memset_0(v31, 0, sizeof(v31));
    p_Handles = &Handles;
    v5 = std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(v27, (char *)this + 56, v4);
    LPA::CoreLpa::EnqueueLpaHelperStop(this, v5, &p_Handles);
    v8 = std::shared_ptr<LPA::LpaHelper>::shared_ptr<LPA::LpaHelper>(v27, (char *)this + 72, v6, v7);
    LPA::CoreLpa::EnqueueLpaHelperStop(this, v8, &p_Handles);
    v10 = std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(v27, (char *)this + 88, v9);
    LPA::CoreLpa::EnqueueLpaHelperStop(this, v10, &p_Handles);
    v12 = std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(v27, (char *)this + 40, v11);
    LPA::CoreLpa::EnqueueLpaHelperStop(this, v12, &p_Handles);
    v15 = std::shared_ptr<LPA::EnterpriseManagerInterface>::shared_ptr<LPA::EnterpriseManagerInterface>(
            v27,
            (char *)this + 104,
            v13,
            v14);
    LPA::CoreLpa::EnqueueLpaHelperStop(this, v15, &p_Handles);
    v16 = *((_QWORD *)this + 22);
    if ( v16 == -1 )
    {
      v20 = p_Handles;
    }
    else
    {
      v17 = (void *)*((_QWORD *)this + 24);
      v29[0] = off_1801066E8;
      v29[1] = v16;
      v29[2] = v17;
      v29[7] = v29;
      v18 = MessageDispatcher::EnQueue(*((_QWORD *)this + 3), v29);
      `pplx::details::_MakeTToUnitFunc<web::json::value>'::`2'::_lambda_1_::~_lambda_1_(v29);
      if ( v18 < 0 )
        SetEvent(v17);
      v19 = p_Handles;
      *p_Handles = (HANDLE)*((_QWORD *)this + 24);
      v20 = v19 + 1;
    }
    if ( *((_QWORD *)this + 23) )
    {
      RtlUnsubscribeWnfNotificationWaitForCompletion();
      *((_QWORD *)this + 23) = 0;
    }
    v21 = v20 - &Handles;
    v3 = 1;
    if ( (_DWORD)v21 && WaitForMultipleObjects(v21, &Handles, 1, 0x6DDD0u) )
    {
      MessageDispatcher::CancelAndWaitForQueueComplete(*((PVOID *)this + 3));
      v3 = 0;
    }
    v22 = (void *)*((_QWORD *)this + 3);
    if ( v22 )
      MessageDispatcher::Stop(v22);
    if ( *((_BYTE *)this + 168) )
    {
      LuiApiServer::LuiApiServerDeInit((LuiApiServer *)v22);
      *((_BYTE *)this + 168) = 0;
    }
    ServiceHandler::SetEsimBusyCount(0);
    ServiceHandler::SetEsimDoingBackgroundWorkCount(0);
    ServiceHandler::SetEsimDoingEnterpriseWorkCount(0);
    ServiceHandler::SetRpcClientCount(0);
    EnterCriticalSection(v2);
    LPA::CoreLpa::TransitionToState(this);
  }
  LeaveCriticalSection(v2);
  if ( (_DWORD)CallbackContext )
  {
    LODWORD(p_Handles) = v3;
    v28 = "LPA::CoreLpa::Stop";
    v27[0] = "LpaServiceCore";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)byte_18012B095,
      v24,
      v25,
      (__int64)v27,
      (__int64)&v28,
      (__int64)&p_Handles);
  }
}

```

## disassembly

```asm
0x1800733c4  push    rbp
0x1800733c6  push    rbx
0x1800733c7  push    rsi
0x1800733c8  push    rdi
0x1800733c9  push    r12
0x1800733cb  push    r14
0x1800733cd  lea     rbp, [rsp-8]
0x1800733d2  sub     rsp, 108h
0x1800733d9  mov     rax, cs:__security_cookie
0x1800733e0  xor     rax, rsp
0x1800733e3  mov     [rbp+30h+var_40], rax
0x1800733e7  mov     rdi, rcx
0x1800733ea  lea     r14, [rcx+80h]
0x1800733f1  mov     rcx, r14; lpCriticalSection
0x1800733f4  call    cs:__imp_EnterCriticalSection
0x1800733fa  mov     r12d, 1
0x180073400  mov     esi, r12d
0x180073403  cmp     dword ptr [rdi+10h], 0
0x180073407  jz      loc_1800735FF
0x18007340d  lea     edx, [r12+2]
0x180073412  cmp     [rdi+10h], edx
0x180073415  jz      loc_1800735FF
0x18007341b  mov     rcx, rdi
0x18007341e  call    ?TransitionToState@CoreLpa@LPA@@AEAAXW4RUNNING_STATE@@@Z; LPA::CoreLpa::TransitionToState(RUNNING_STATE)
0x180073423  mov     rcx, r14; lpCriticalSection
0x180073426  call    cs:__imp_LeaveCriticalSection
0x18007342c  mov     [rbp+30h+Handles], 0FFFFFFFFFFFFFFFFh
0x180073434  xor     edx, edx; Val
0x180073436  lea     r8d, [r12+47h]; Size
0x18007343b  lea     rcx, [rbp+30h+var_88]; void *
0x18007343f  call    memset_0
0x180073444  lea     rax, [rbp+30h+Handles]
0x180073448  mov     [rsp+130h+var_F0], rax
0x18007344d  lea     rdx, [rdi+38h]
0x180073451  lea     rcx, [rsp+130h+var_E8]
0x180073456  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x18007345b  lea     r8, [rsp+130h+var_F0]
0x180073460  mov     rdx, rax
0x180073463  mov     rcx, rdi
0x180073466  call    ?EnqueueLpaHelperStop@CoreLpa@LPA@@AEAAXV?$shared_ptr@ULpaHelper@LPA@@@std@@PEAPEAPEAX@Z; LPA::CoreLpa::EnqueueLpaHelperStop(std::shared_ptr<LPA::LpaHelper>,void * * *)
0x18007346b  lea     rdx, [rdi+48h]
0x18007346f  lea     rcx, [rsp+130h+var_E8]
0x180073474  call    ??$?0VEsimManager@LPA@@$0A@@?$shared_ptr@ULpaHelper@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::shared_ptr<LPA::LpaHelper>::shared_ptr<LPA::LpaHelper>(std::shared_ptr<LPA::EsimManager> const &)
0x180073479  lea     r8, [rsp+130h+var_F0]
0x18007347e  mov     rdx, rax
0x180073481  mov     rcx, rdi
0x180073484  call    ?EnqueueLpaHelperStop@CoreLpa@LPA@@AEAAXV?$shared_ptr@ULpaHelper@LPA@@@std@@PEAPEAPEAX@Z; LPA::CoreLpa::EnqueueLpaHelperStop(std::shared_ptr<LPA::LpaHelper>,void * * *)
0x180073489  lea     rdx, [rdi+58h]
0x18007348d  lea     rcx, [rsp+130h+var_E8]
0x180073492  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x180073497  lea     r8, [rsp+130h+var_F0]
0x18007349c  mov     rdx, rax
0x18007349f  mov     rcx, rdi
0x1800734a2  call    ?EnqueueLpaHelperStop@CoreLpa@LPA@@AEAAXV?$shared_ptr@ULpaHelper@LPA@@@std@@PEAPEAPEAX@Z; LPA::CoreLpa::EnqueueLpaHelperStop(std::shared_ptr<LPA::LpaHelper>,void * * *)
0x1800734a7  lea     rdx, [rdi+28h]
0x1800734ab  lea     rcx, [rsp+130h+var_E8]
0x1800734b0  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x1800734b5  lea     r8, [rsp+130h+var_F0]
0x1800734ba  mov     rdx, rax
0x1800734bd  mov     rcx, rdi
0x1800734c0  call    ?EnqueueLpaHelperStop@CoreLpa@LPA@@AEAAXV?$shared_ptr@ULpaHelper@LPA@@@std@@PEAPEAPEAX@Z; LPA::CoreLpa::EnqueueLpaHelperStop(std::shared_ptr<LPA::LpaHelper>,void * * *)
0x1800734c5  lea     rdx, [rdi+68h]
0x1800734c9  lea     rcx, [rsp+130h+var_E8]
0x1800734ce  call    ??$?0VEnterpriseManager@LPA@@$0A@@?$shared_ptr@UEnterpriseManagerInterface@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEnterpriseManager@LPA@@@1@@Z; std::shared_ptr<LPA::EnterpriseManagerInterface>::shared_ptr<LPA::EnterpriseManagerInterface>(std::shared_ptr<LPA::EnterpriseManager> const &)
0x1800734d3  lea     r8, [rsp+130h+var_F0]
0x1800734d8  mov     rdx, rax
0x1800734db  mov     rcx, rdi
0x1800734de  call    ?EnqueueLpaHelperStop@CoreLpa@LPA@@AEAAXV?$shared_ptr@ULpaHelper@LPA@@@std@@PEAPEAPEAX@Z; LPA::CoreLpa::EnqueueLpaHelperStop(std::shared_ptr<LPA::LpaHelper>,void * * *)
0x1800734e3  mov     rax, [rdi+0B0h]
0x1800734ea  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800734ee  jz      short loc_180073555
0x1800734f0  mov     rsi, [rdi+0C0h]
0x1800734f7  lea     rcx, off_1801066E8
0x1800734fe  mov     [rsp+130h+var_D0], rcx
0x180073503  mov     [rsp+130h+var_C8], rax
0x180073508  mov     [rsp+130h+var_C0], rsi
0x18007350d  lea     rax, [rsp+130h+var_D0]
0x180073512  mov     [rbp+30h+var_98], rax
0x180073516  lea     rdx, [rsp+130h+var_D0]
0x18007351b  mov     rcx, [rdi+18h]
0x18007351f  call    ?EnQueue@MessageDispatcher@@QEAAJ$$QEAV?$function@$$A6AXXZ@std@@@Z; MessageDispatcher::EnQueue(std::function<void (void)> &&)
0x180073524  mov     ebx, eax
0x180073526  lea     rcx, [rsp+130h+var_D0]
0x18007352b  call    ??1_lambda_1_@?1???$_MakeTToUnitFunc@Vvalue@json@web@@@details@pplx@@YA?AV?$function@$$A6AEVvalue@json@web@@@Z@std@@AEBV?$function@$$A6AXVvalue@json@web@@@Z@4@@Z@QEAA@XZ; `pplx::details::_MakeTToUnitFunc<web::json::value>(std::function<void (web::json::value)> const &)'::`2'::_lambda_1_::~_lambda_1_(void)
0x180073530  shr     ebx, 1Fh
0x180073533  test    bl, bl
0x180073535  jz      short loc_180073540
0x180073537  mov     rcx, rsi; hEvent
0x18007353a  call    cs:__imp_SetEvent
0x180073540  mov     rax, [rdi+0C0h]
0x180073547  mov     rbx, [rsp+130h+var_F0]
0x18007354c  mov     [rbx], rax
0x18007354f  add     rbx, 8
0x180073553  jmp     short loc_18007355A
0x180073555  mov     rbx, [rsp+130h+var_F0]
0x18007355a  mov     rcx, [rdi+0B8h]
0x180073561  test    rcx, rcx
0x180073564  jz      short loc_180073577
0x180073566  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18007356c  mov     qword ptr [rdi+0B8h], 0
0x180073577  lea     rax, [rbp+30h+Handles]
0x18007357b  sub     rbx, rax
0x18007357e  sar     rbx, 3
0x180073582  mov     esi, r12d
0x180073585  test    ebx, ebx
0x180073587  jz      short loc_1800735AD
0x180073589  mov     r9d, 6DDD0h; dwMilliseconds
0x18007358f  mov     r8d, r12d; bWaitAll
0x180073592  lea     rdx, [rbp+30h+Handles]; lpHandles
0x180073596  mov     ecx, ebx; nCount
0x180073598  call    cs:__imp_WaitForMultipleObjects
0x18007359e  test    eax, eax
0x1800735a0  jz      short loc_1800735AD
0x1800735a2  mov     rcx, [rdi+18h]; pv
0x1800735a6  call    ?CancelAndWaitForQueueComplete@MessageDispatcher@@QEAAJXZ; MessageDispatcher::CancelAndWaitForQueueComplete(void)
0x1800735ab  xor     esi, esi
0x1800735ad  mov     rcx, [rdi+18h]; pvCleanupContext
0x1800735b1  test    rcx, rcx
0x1800735b4  jz      short loc_1800735BB
0x1800735b6  call    ?Stop@MessageDispatcher@@QEAAXXZ; MessageDispatcher::Stop(void)
0x1800735bb  cmp     byte ptr [rdi+0A8h], 0
0x1800735c2  jz      short loc_1800735D0
0x1800735c4  call    ?LuiApiServerDeInit@LuiApiServer@@YAXXZ; LuiApiServer::LuiApiServerDeInit(void)
0x1800735c9  mov     byte ptr [rdi+0A8h], 0
0x1800735d0  xor     ecx, ecx; unsigned __int64
0x1800735d2  call    ?SetEsimBusyCount@ServiceHandler@@SAX_K@Z; ServiceHandler::SetEsimBusyCount(unsigned __int64)
0x1800735d7  xor     ecx, ecx; unsigned __int64
0x1800735d9  call    ?SetEsimDoingBackgroundWorkCount@ServiceHandler@@SAX_K@Z; ServiceHandler::SetEsimDoingBackgroundWorkCount(unsigned __int64)
0x1800735de  xor     ecx, ecx; unsigned __int64
0x1800735e0  call    ?SetEsimDoingEnterpriseWorkCount@ServiceHandler@@SAX_K@Z; ServiceHandler::SetEsimDoingEnterpriseWorkCount(unsigned __int64)
0x1800735e5  xor     ecx, ecx; unsigned __int64
0x1800735e7  call    ?SetRpcClientCount@ServiceHandler@@SAX_K@Z; ServiceHandler::SetRpcClientCount(unsigned __int64)
0x1800735ec  mov     rcx, r14; lpCriticalSection
0x1800735ef  call    cs:__imp_EnterCriticalSection
0x1800735f5  xor     edx, edx
0x1800735f7  mov     rcx, rdi
0x1800735fa  call    ?TransitionToState@CoreLpa@LPA@@AEAAXW4RUNNING_STATE@@@Z; LPA::CoreLpa::TransitionToState(RUNNING_STATE)
0x1800735ff  mov     rcx, r14; lpCriticalSection
0x180073602  call    cs:__imp_LeaveCriticalSection
0x180073608  mov     eax, cs:CallbackContext
0x18007360e  test    eax, eax
0x180073610  jz      short loc_180073658
0x180073612  mov     dword ptr [rsp+130h+var_F0], esi
0x180073616  lea     rax, aLpaCorelpaStop; "LPA::CoreLpa::Stop"
0x18007361d  mov     [rsp+130h+var_D8], rax
0x180073622  lea     rax, aLpaservicecore; "LpaServiceCore"
0x180073629  mov     [rsp+130h+var_E8], rax
0x18007362e  lea     rax, [rsp+130h+var_F0]
0x180073633  mov     [rsp+130h+var_100], rax
0x180073638  lea     rax, [rsp+130h+var_D8]
0x18007363d  mov     [rsp+130h+var_108], rax
0x180073642  lea     rax, [rsp+130h+var_E8]
0x180073647  mov     [rsp+130h+var_110], rax
0x18007364c  lea     rdx, byte_18012B095
0x180073653  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180073658  mov     rcx, [rbp+30h+var_40]
0x18007365c  xor     rcx, rsp; StackCookie
0x18007365f  call    __security_check_cookie
0x180073664  add     rsp, 108h
0x18007366b  pop     r14
0x18007366d  pop     r12
0x18007366f  pop     rdi
0x180073670  pop     rsi
0x180073671  pop     rbx
0x180073672  pop     rbp
0x180073673  retn
```
