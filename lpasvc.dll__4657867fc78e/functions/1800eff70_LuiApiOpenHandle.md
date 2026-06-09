# LuiApiOpenHandle

- ea: `0x1800eff70`
- end: `0x1800f041d`
- name: `LuiApiOpenHandle`
- size: `1197`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800017c8`
- `0x18000199c`
- `0x18000df90`
- `0x18000e4e0`
- `0x18000ebf4`
- `0x1800636dc`
- `0x18006ba8c`
- `0x1800709e4`
- `0x180072878`
- `0x1800ce810`
- `0x1800cfea0`
- `0x1800ed510`
- `0x1800edc5c`
- `0x1800edddc`
- `0x1800ede84`
- `0x1800ee288`
- `0x1800eff70`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f0178`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f0178`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f015f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f015f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f033a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f033a`
- `RPCRT4!RpcRevertToSelf` at `0x1800f01d8`
- `RPCRT4!RpcRevertToSelf` at `0x1800f01d8`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800f00b1`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800f00b1`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800f008f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800f008f`
- `RPCRT4!RpcImpersonateClient` at `0x1800f00d3`
- `RPCRT4!RpcImpersonateClient` at `0x1800f00d3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f00fb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800f00fb`

## string_xrefs

- `0x1800eff97`: `LuiApiOpenHandle`
- `0x1800f0124`: `LuiApiOpenHandle`
- `0x1800f019d`: `LuiApiOpenHandle`
- `0x1800f01fc`: `LuiApiOpenHandle`
- `0x1800f026f`: `LuiApiOpenHandle`
- `0x1800f0340`: `LuiApiOpenHandle`
- `0x1800f0376`: `LuiApiOpenHandle`

## pseudocode

```c
__int64 __fastcall LuiApiOpenHandle(__int64 a1, unsigned int a2, LuiContext **a3, void **a4)
{
  LuiContext *v4; // rdi
  int v5; // r12d
  LuiContext *v9; // rax
  __int64 v10; // rax
  LuiContext *v11; // rdi
  signed int v12; // ebx
  HANDLE v13; // rsi
  RPC_STATUS v14; // eax
  RPC_STATUS v15; // eax
  RPC_STATUS v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  HANDLE CurrentThread; // rax
  CommonUtil *v21; // rcx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  RPC_STATUS v25; // eax
  signed int v26; // ecx
  int v27; // ecx
  __int64 v28; // r8
  int v29; // eax
  int v30; // r9d
  signed int LastErrorToHResultAndForceFailure; // [rsp+50h] [rbp-B0h] BYREF
  const char *v33; // [rsp+58h] [rbp-A8h] BYREF
  const char *v34; // [rsp+60h] [rbp-A0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-98h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  const char *v37; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v38; // [rsp+80h] [rbp-80h]
  std::_Ref_count_base *v39[2]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v41[56]; // [rsp+A8h] [rbp-58h] BYREF
  DWORD dwProcessId; // [rsp+E0h] [rbp-20h]

  v4 = 0;
  v5 = 0;
  TokenHandle = 0;
  *(_OWORD *)v39 = 0;
  if ( a3 && a4 )
  {
    v9 = (LuiContext *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    if ( v9 && (Binding = LuiContext::LuiContext(v9), (v4 = (LuiContext *)Binding) != 0) )
    {
      v10 = std::make_shared<void *,std::nullptr_t>(&v37, &Binding);
      std::shared_ptr<LPA::EnterpriseManager>::operator=(v39, v10);
      if ( v38 )
        std::_Ref_count_base::_Decref(v38);
      v11 = (LuiContext *)Binding;
      (*(void (__fastcall **)(RPC_BINDING_HANDLE))(*(_QWORD *)Binding + 8LL))(Binding);
      v12 = LuiContext::Initialize(v11);
      if ( v12 < 0 || (v12 = LuiContext::BindPipe(v11, a4), v12 < 0) )
      {
        (*(void (__fastcall **)(LuiContext *))(*(_QWORD *)v11 + 16LL))(v11);
        *a3 = 0;
      }
      else
      {
        v13 = 0;
        Binding = 0;
        memset_0(v41, 0, 0x70u);
        RpcCallAttributes[0] = 3;
        RpcCallAttributes[1] = 16;
        v14 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
        v12 = v14;
        if ( v14 > 0 )
          v12 = (unsigned __int16)v14 | 0x80070000;
        if ( v12 >= 0 )
        {
          v15 = RpcServerInqBindingHandle(&Binding);
          v12 = v15;
          if ( v15 > 0 )
            v12 = (unsigned __int16)v15 | 0x80070000;
          if ( v12 >= 0 )
          {
            v16 = RpcImpersonateClient(Binding);
            v12 = v16;
            if ( v16 > 0 )
              v12 = (unsigned __int16)v16 | 0x80070000;
            if ( v12 >= 0 )
            {
              v13 = OpenProcess(0x1000u, 0, dwProcessId);
              if ( !v13 && (unsigned int)CallbackContext > 3 )
              {
                LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure((CommonUtil *)(unsigned int)CallbackContext);
                v33 = "LuiApiOpenHandle";
                v34 = "LuiApiServer";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v17,
                  (unsigned int)byte_18013647B,
                  v18,
                  v19,
                  (__int64)&v34,
                  (__int64)&v33,
                  (__int64)&LastErrorToHResultAndForceFailure);
              }
              CurrentThread = GetCurrentThread();
              if ( !OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) && (unsigned int)CallbackContext > 3 )
              {
                LastErrorToHResultAndForceFailure = CommonUtil::GetLastErrorToHResultAndForceFailure(v21);
                v34 = "LuiApiOpenHandle";
                v33 = "LuiApiServer";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                  v22,
                  (unsigned int)&word_1801364BE,
                  v23,
                  v24,
                  (__int64)&v33,
                  (__int64)&v34,
                  (__int64)&LastErrorToHResultAndForceFailure);
              }
            }
          }
        }
        v25 = RpcRevertToSelf();
        v26 = v25;
        if ( v25 > 0 )
          v26 = (unsigned __int16)v25 | 0x80070000;
        if ( v26 < 0 && (unsigned int)CallbackContext > 3 )
        {
          LastErrorToHResultAndForceFailure = v26;
          v34 = "LuiApiOpenHandle";
          v33 = "LuiApiServer";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v26,
            (unsigned int)&word_1801363FE,
            (_DWORD)a3,
            (_DWORD)a4,
            (__int64)&v33,
            (__int64)&v34,
            (__int64)&LastErrorToHResultAndForceFailure);
        }
        if ( v12 >= 0 )
        {
          v12 = LPA::Lui::ValidateClient(a2, TokenHandle, v13);
          if ( v12 >= 0 )
          {
            (*(void (__fastcall **)(LuiContext *))(*(_QWORD *)v11 + 8LL))(v11);
            v29 = std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(&v37, v39, v28);
            v12 = LuiApiServer::_OnLuiApiOpenHandle(
                    *((_QWORD *)LuiApiServer::g_pLuiApiServerGlobalData + 4),
                    v29,
                    a2,
                    v30,
                    (__int64)v13);
            if ( v12 >= 0 )
              v12 = LuiContext::WaitForSyncOp(v11);
            (*(void (__fastcall **)(LuiContext *))(*(_QWORD *)v11 + 16LL))(v11);
            if ( v12 < 0 )
            {
              (*(void (__fastcall **)(LuiContext *))(*(_QWORD *)v11 + 16LL))(v11);
              v11 = 0;
              *(_QWORD *)v39[0] = 0;
            }
          }
          else if ( (unsigned int)CallbackContext > 3 )
          {
            LastErrorToHResultAndForceFailure = v12;
            v34 = "LuiApiOpenHandle";
            v33 = "LuiApiServer";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v27,
              (unsigned int)byte_18013643B,
              (_DWORD)a3,
              (_DWORD)a4,
              (__int64)&v33,
              (__int64)&v34,
              (__int64)&LastErrorToHResultAndForceFailure);
          }
        }
        *a3 = v11;
        if ( v13 )
          CloseHandle(v13);
        if ( v12 >= 0 )
          v5 = *((_DWORD *)v11 + 4);
      }
    }
    else
    {
      v12 = -2147024882;
      *a3 = v4;
    }
  }
  else
  {
    v12 = -2147024809;
    *a3 = 0;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    v37 = "LuiApiServer";
    LastErrorToHResultAndForceFailure = a2;
    LODWORD(v33) = v5;
    LODWORD(Binding) = v12;
    v34 = "LuiApiOpenHandle";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)"LuiApiOpenHandle",
      (unsigned int)word_18013636A,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v37,
      (__int64)&v34,
      (__int64)&Binding,
      (__int64)&v33,
      (__int64)&LastErrorToHResultAndForceFailure);
  }
  if ( v39[1] )
    std::_Ref_count_base::_Decref(v39[1]);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800eff70  push    rbp
0x1800eff72  push    rbx
0x1800eff73  push    rsi
0x1800eff74  push    rdi
0x1800eff75  push    r12
0x1800eff77  push    r14
0x1800eff79  push    r15
0x1800eff7b  lea     rbp, [rsp-30h]
0x1800eff80  sub     rsp, 130h
0x1800eff87  mov     rax, cs:__security_cookie
0x1800eff8e  xor     rax, rsp
0x1800eff91  mov     [rbp+60h+var_40], rax
0x1800eff95  xor     edi, edi
0x1800eff97  lea     rcx, aLuiapiopenhand; "LuiApiOpenHandle"
0x1800eff9e  xor     r12d, r12d
0x1800effa1  mov     [rsp+160h+TokenHandle], rdi
0x1800effa6  xorps   xmm0, xmm0
0x1800effa9  mov     r15d, edx
0x1800effac  lea     rdx, aLuiapiserver; "LuiApiServer"
0x1800effb3  mov     rsi, r9
0x1800effb6  mov     r14, r8
0x1800effb9  movdqu  xmmword ptr [rbp+60h+var_D8], xmm0
0x1800effbe  test    r8, r8
0x1800effc1  jz      loc_1800F0386
0x1800effc7  test    r9, r9
0x1800effca  jz      loc_1800F0386
0x1800effd0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800effd7  lea     ecx, [rdi+30h]; unsigned __int64
0x1800effda  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800effdf  test    rax, rax
0x1800effe2  jz      loc_1800F036E
0x1800effe8  mov     rcx, rax; this
0x1800effeb  call    ??0LuiContext@@QEAA@XZ; LuiContext::LuiContext(void)
0x1800efff0  mov     [rsp+160h+Binding], rax
0x1800efff5  mov     rdi, rax
0x1800efff8  test    rax, rax
0x1800efffb  jz      loc_1800F036E
0x1800f0001  lea     rdx, [rsp+160h+Binding]
0x1800f0006  lea     rcx, [rsp+160h+var_E8]
0x1800f000b  call    ??$make_shared@PEAX$$T@std@@YA?AV?$shared_ptr@PEAX@0@$$QEA$$T@Z
0x1800f0010  mov     rdx, rax
0x1800f0013  lea     rcx, [rbp+60h+var_D8]
0x1800f0017  call    ??4?$shared_ptr@VEnterpriseManager@LPA@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<LPA::EnterpriseManager>::operator=(std::shared_ptr<LPA::EnterpriseManager> &&)
0x1800f001c  mov     rcx, [rbp+60h+var_E0]; this
0x1800f0020  test    rcx, rcx
0x1800f0023  jz      short loc_1800F002A
0x1800f0025  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f002a  mov     rdi, [rsp+160h+Binding]
0x1800f002f  mov     rcx, rdi
0x1800f0032  mov     rax, [rdi]
0x1800f0035  mov     rax, [rax+8]
0x1800f0039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f003e  mov     rcx, rdi; this
0x1800f0041  call    ?Initialize@LuiContext@@QEAAJXZ; LuiContext::Initialize(void)
0x1800f0046  mov     ebx, eax
0x1800f0048  test    eax, eax
0x1800f004a  js      loc_1800F0358
0x1800f0050  mov     rdx, rsi; void **
0x1800f0053  mov     rcx, rdi; this
0x1800f0056  call    ?BindPipe@LuiContext@@QEAAJAEAPEAX@Z; LuiContext::BindPipe(void * &)
0x1800f005b  mov     ebx, eax
0x1800f005d  test    eax, eax
0x1800f005f  js      loc_1800F0358
0x1800f0065  xor     esi, esi
0x1800f0067  lea     rcx, [rbp+60h+var_B8]; void *
0x1800f006b  xor     edx, edx; Val
0x1800f006d  mov     [rsp+160h+Binding], rsi
0x1800f0072  lea     r8d, [rsi+70h]; Size
0x1800f0076  call    memset_0
0x1800f007b  lea     rdx, [rbp+60h+RpcCallAttributes]; RpcCallAttributes
0x1800f007f  mov     [rbp+60h+RpcCallAttributes], 3
0x1800f0086  xor     ecx, ecx; ClientBinding
0x1800f0088  mov     [rbp+60h+var_BC], 10h
0x1800f008f  call    cs:__imp_RpcServerInqCallAttributesW
0x1800f0095  mov     ebx, eax
0x1800f0097  test    eax, eax
0x1800f0099  jle     short loc_1800F00A4
0x1800f009b  movzx   ebx, ax
0x1800f009e  or      ebx, 80070000h
0x1800f00a4  test    ebx, ebx
0x1800f00a6  js      loc_1800F01D8
0x1800f00ac  lea     rcx, [rsp+160h+Binding]; Binding
0x1800f00b1  call    cs:__imp_RpcServerInqBindingHandle
0x1800f00b7  mov     ebx, eax
0x1800f00b9  test    eax, eax
0x1800f00bb  jle     short loc_1800F00C6
0x1800f00bd  movzx   ebx, ax
0x1800f00c0  or      ebx, 80070000h
0x1800f00c6  test    ebx, ebx
0x1800f00c8  js      loc_1800F01D8
0x1800f00ce  mov     rcx, [rsp+160h+Binding]; BindingHandle
0x1800f00d3  call    cs:__imp_RpcImpersonateClient
0x1800f00d9  mov     ebx, eax
0x1800f00db  test    eax, eax
0x1800f00dd  jle     short loc_1800F00E8
0x1800f00df  movzx   ebx, ax
0x1800f00e2  or      ebx, 80070000h
0x1800f00e8  test    ebx, ebx
0x1800f00ea  js      loc_1800F01D8
0x1800f00f0  mov     r8d, [rbp+60h+dwProcessId]; dwProcessId
0x1800f00f4  xor     edx, edx; bInheritHandle
0x1800f00f6  mov     ecx, 1000h; dwDesiredAccess
0x1800f00fb  call    cs:__imp_OpenProcess
0x1800f0101  mov     rsi, rax
0x1800f0104  test    rax, rax
0x1800f0107  jnz     short loc_1800F015F
0x1800f0109  mov     ecx, cs:CallbackContext; this
0x1800f010f  cmp     ecx, 3
0x1800f0112  jbe     short loc_1800F015F
0x1800f0114  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800f0119  mov     [rsp+160h+var_110], eax
0x1800f011d  lea     rdx, byte_18013647B
0x1800f0124  lea     rax, aLuiapiopenhand; "LuiApiOpenHandle"
0x1800f012b  mov     [rsp+160h+var_108], rax
0x1800f0130  lea     rax, aLuiapiserver; "LuiApiServer"
0x1800f0137  mov     [rsp+160h+var_100], rax
0x1800f013c  lea     rax, [rsp+160h+var_110]
0x1800f0141  mov     [rsp+160h+var_130], rax
0x1800f0146  lea     rax, [rsp+160h+var_108]
0x1800f014b  mov     [rsp+160h+var_138], rax
0x1800f0150  lea     rax, [rsp+160h+var_100]
0x1800f0155  mov     [rsp+160h+var_140], rax
0x1800f015a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800f015f  call    cs:__imp_GetCurrentThread
0x1800f0165  lea     r9, [rsp+160h+TokenHandle]; TokenHandle
0x1800f016a  mov     edx, 2000Ch; DesiredAccess
0x1800f016f  mov     rcx, rax; ThreadHandle
0x1800f0172  mov     r8d, 1; OpenAsSelf
0x1800f0178  call    cs:__imp_OpenThreadToken
0x1800f017e  test    eax, eax
0x1800f0180  jnz     short loc_1800F01D8
0x1800f0182  mov     eax, cs:CallbackContext
0x1800f0188  cmp     eax, 3
0x1800f018b  jbe     short loc_1800F01D8
0x1800f018d  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800f0192  mov     [rsp+160h+var_110], eax
0x1800f0196  lea     rdx, word_1801364BE
0x1800f019d  lea     rax, aLuiapiopenhand; "LuiApiOpenHandle"
0x1800f01a4  mov     [rsp+160h+var_100], rax
0x1800f01a9  lea     rax, aLuiapiserver; "LuiApiServer"
0x1800f01b0  mov     [rsp+160h+var_108], rax
0x1800f01b5  lea     rax, [rsp+160h+var_110]
0x1800f01ba  mov     [rsp+160h+var_130], rax
0x1800f01bf  lea     rax, [rsp+160h+var_100]
0x1800f01c4  mov     [rsp+160h+var_138], rax
0x1800f01c9  lea     rax, [rsp+160h+var_108]
0x1800f01ce  mov     [rsp+160h+var_140], rax
0x1800f01d3  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800f01d8  call    cs:__imp_RpcRevertToSelf
0x1800f01de  mov     ecx, eax
0x1800f01e0  test    eax, eax
0x1800f01e2  jle     short loc_1800F01ED
0x1800f01e4  movzx   ecx, ax
0x1800f01e7  or      ecx, 80070000h
0x1800f01ed  test    ecx, ecx
0x1800f01ef  jns     short loc_1800F0242
0x1800f01f1  mov     eax, cs:CallbackContext
0x1800f01f7  cmp     eax, 3
0x1800f01fa  jbe     short loc_1800F0242
0x1800f01fc  lea     rax, aLuiapiopenhand; "LuiApiOpenHandle"
0x1800f0203  mov     [rsp+160h+var_110], ecx
0x1800f0207  mov     [rsp+160h+var_100], rax
0x1800f020c  lea     rdx, word_1801363FE
0x1800f0213  lea     rax, aLuiapiserver; "LuiApiServer"
0x1800f021a  mov     [rsp+160h+var_108], rax
0x1800f021f  lea     rax, [rsp+160h+var_110]
0x1800f0224  mov     [rsp+160h+var_130], rax
0x1800f0229  lea     rax, [rsp+160h+var_100]
0x1800f022e  mov     [rsp+160h+var_138], rax
0x1800f0233  lea     rax, [rsp+160h+var_108]
0x1800f0238  mov     [rsp+160h+var_140], rax
0x1800f023d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800f0242  test    ebx, ebx
0x1800f0244  js      loc_1800F032F
0x1800f024a  mov     rdx, [rsp+160h+TokenHandle]
0x1800f024f  mov     r8, rsi
0x1800f0252  mov     ecx, r15d
0x1800f0255  call    ?ValidateClient@Lui@LPA@@SAJW4LPALUICLIENTMODE@@PEAX1@Z; LPA::Lui::ValidateClient(LPALUICLIENTMODE,void *,void *)
0x1800f025a  mov     ebx, eax
0x1800f025c  test    eax, eax
0x1800f025e  jns     short loc_1800F02B7
0x1800f0260  mov     eax, cs:CallbackContext
0x1800f0266  cmp     eax, 3
0x1800f0269  jbe     loc_1800F032F
0x1800f026f  lea     rax, aLuiapiopenhand; "LuiApiOpenHandle"
0x1800f0276  mov     [rsp+160h+var_110], ebx
0x1800f027a  mov     [rsp+160h+var_100], rax
0x1800f027f  lea     rdx, byte_18013643B
0x1800f0286  lea     rax, aLuiapiserver; "LuiApiServer"
0x1800f028d  mov     [rsp+160h+var_108], rax
0x1800f0292  lea     rax, [rsp+160h+var_110]
0x1800f0297  mov     [rsp+160h+var_130], rax
0x1800f029c  lea     rax, [rsp+160h+var_100]
0x1800f02a1  mov     [rsp+160h+var_138], rax
0x1800f02a6  lea     rax, [rsp+160h+var_108]
0x1800f02ab  mov     [rsp+160h+var_140], rax
0x1800f02b0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800f02b5  jmp     short loc_1800F032F
0x1800f02b7  mov     rax, [rdi]
0x1800f02ba  mov     rcx, rdi
0x1800f02bd  mov     rax, [rax+8]
0x1800f02c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f02c6  mov     r9, [rsp+160h+TokenHandle]
0x1800f02cb  lea     rdx, [rbp+60h+var_D8]
0x1800f02cf  lea     rcx, [rsp+160h+var_E8]
0x1800f02d4  call    ??0?$shared_ptr@VWnfMessage@LPA@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LPA::WnfMessage>::shared_ptr<LPA::WnfMessage>(std::shared_ptr<LPA::WnfMessage> const &)
0x1800f02d9  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800f02e0  mov     r8d, r15d
0x1800f02e3  mov     rdx, rax
0x1800f02e6  mov     [rsp+160h+var_140], rsi
0x1800f02eb  mov     rcx, [rcx+20h]
0x1800f02ef  call    ?_OnLuiApiOpenHandle@LuiApiServer@@YAJPEAXV?$shared_ptr@PEAX@std@@W4LPALUICLIENTMODE@@00@Z; LuiApiServer::_OnLuiApiOpenHandle(void *,std::shared_ptr<void *>,LPALUICLIENTMODE,void *,void *)
0x1800f02f4  mov     ebx, eax
0x1800f02f6  test    eax, eax
0x1800f02f8  js      short loc_1800F0304
0x1800f02fa  mov     rcx, rdi; this
0x1800f02fd  call    ?WaitForSyncOp@LuiContext@@QEAAJXZ; LuiContext::WaitForSyncOp(void)
0x1800f0302  mov     ebx, eax
0x1800f0304  mov     rax, [rdi]
0x1800f0307  mov     rcx, rdi
0x1800f030a  mov     rax, [rax+10h]
0x1800f030e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0313  test    ebx, ebx
0x1800f0315  jns     short loc_1800F032F
0x1800f0317  mov     rax, [rdi]
0x1800f031a  mov     rcx, rdi
0x1800f031d  mov     rax, [rax+10h]
0x1800f0321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0326  mov     rax, [rbp+60h+var_D8]
0x1800f032a  xor     edi, edi
0x1800f032c  mov     [rax], rdi
0x1800f032f  mov     [r14], rdi
0x1800f0332  test    rsi, rsi
0x1800f0335  jz      short loc_1800F0340
0x1800f0337  mov     rcx, rsi; hObject
0x1800f033a  call    cs:__imp_CloseHandle
0x1800f0340  lea     rcx, aLuiapiopenhand; "LuiApiOpenHandle"
0x1800f0347  lea     rdx, aLuiapiserver; "LuiApiServer"
0x1800f034e  test    ebx, ebx
0x1800f0350  js      short loc_1800F038E
0x1800f0352  mov     r12d, [rdi+10h]
0x1800f0356  jmp     short loc_1800F038E
0x1800f0358  mov     rax, [rdi]
0x1800f035b  mov     rcx, rdi
0x1800f035e  mov     rax, [rax+10h]
0x1800f0362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0367  xor     eax, eax
0x1800f0369  mov     [r14], rax
0x1800f036c  jmp     short loc_1800F0376
0x1800f036e  mov     ebx, 8007000Eh
0x1800f0373  mov     [r14], rdi
0x1800f0376  lea     rcx, aLuiapiopenhand; "LuiApiOpenHandle"
0x1800f037d  lea     rdx, aLuiapiserver; "LuiApiServer"
0x1800f0384  jmp     short loc_1800F038E
0x1800f0386  mov     ebx, 80070057h
0x1800f038b  mov     [r8], rdi
0x1800f038e  mov     eax, cs:CallbackContext
0x1800f0394  cmp     eax, 4
0x1800f0397  jbe     short loc_1800F03EF
0x1800f0399  lea     rax, [rsp+160h+var_110]
0x1800f039e  mov     [rsp+160h+var_E8], rdx
0x1800f03a3  mov     [rsp+160h+var_120], rax
0x1800f03a8  lea     rdx, word_18013636A
0x1800f03af  lea     rax, [rsp+160h+var_108]
0x1800f03b4  mov     [rsp+160h+var_110], r15d
0x1800f03b9  mov     [rsp+160h+var_128], rax
0x1800f03be  lea     rax, [rsp+160h+Binding]
0x1800f03c3  mov     [rsp+160h+var_130], rax
0x1800f03c8  lea     rax, [rsp+160h+var_100]
0x1800f03cd  mov     [rsp+160h+var_138], rax
0x1800f03d2  lea     rax, [rsp+160h+var_E8]
0x1800f03d7  mov     [rsp+160h+var_140], rax
0x1800f03dc  mov     dword ptr [rsp+160h+var_108], r12d
0x1800f03e1  mov     dword ptr [rsp+160h+Binding], ebx
0x1800f03e5  mov     [rsp+160h+var_100], rcx
0x1800f03ea  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800f03ef  mov     rcx, [rbp+60h+var_D8+8]; this
0x1800f03f3  test    rcx, rcx
0x1800f03f6  jz      short loc_1800F03FD
0x1800f03f8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800f03fd  mov     eax, ebx
0x1800f03ff  mov     rcx, [rbp+60h+var_40]
0x1800f0403  xor     rcx, rsp; StackCookie
0x1800f0406  call    __security_check_cookie
0x1800f040b  add     rsp, 130h
0x1800f0412  pop     r15
0x1800f0414  pop     r14
0x1800f0416  pop     r12
0x1800f0418  pop     rdi
0x1800f0419  pop     rsi
0x1800f041a  pop     rbx
0x1800f041b  pop     rbp
0x1800f041c  retn
```
