# NlmHost::RpcClient::RefreshRpcBinding(void)

- ea: `0x180089740`
- end: `0x180089922`
- name: `?RefreshRpcBinding@RpcClient@NlmHost@@AEAAXXZ`
- size: `482`
- prototype: `void __fastcall(NlmHost::RpcClient *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005e0a4`
- `0x18012fff0`

## callees

- `0x18000e190`
- `0x180013748`
- `0x180043488`
- `0x180043e80`
- `0x18004fb18`
- `0x18005085c`
- `0x180051b78`
- `0x18006d154`
- `0x180089740`
- `0x180089928`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008976d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008976d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800898fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800898fb`
- `RPCRT4!RpcEpResolveBinding` at `0x180089862`
- `RPCRT4!RpcEpResolveBinding` at `0x180089862`
- `RPCRT4!RpcBindingSetOption` at `0x180089894`
- `RPCRT4!RpcBindingSetOption` at `0x180089894`
- `RPCRT4!RpcBindingFree` at `0x180089819`
- `RPCRT4!RpcBindingFree` at `0x180089819`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180089838`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180089838`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800897dc`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800897dc`

## string_xrefs

- `0x1800897ed`: `onecore\net\netprofiles\service\src\hostrpc\lib\nlmhostrpcclient.cpp`
- `0x180089849`: `onecore\net\netprofiles\service\src\hostrpc\lib\nlmhostrpcclient.cpp`
- `0x180089873`: `onecore\net\netprofiles\service\src\hostrpc\lib\nlmhostrpcclient.cpp`
- `0x1800898a5`: `onecore\net\netprofiles\service\src\hostrpc\lib\nlmhostrpcclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall NlmHost::RpcClient::RefreshRpcBinding(NlmHost::RpcClient *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  _QWORD *v3; // rax
  unsigned __int16 *v4; // r9
  unsigned __int16 *v5; // r8
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rax
  unsigned int Options; // [rsp+20h] [rbp-50h]
  _BYTE v12[8]; // [rsp+30h] [rbp-40h] BYREF
  std::_Ref_count_base *v13; // [rsp+38h] [rbp-38h]
  struct _RTL_CRITICAL_SECTION *v14; // [rsp+40h] [rbp-30h]
  RPC_BINDING_HANDLE hBinding; // [rsp+50h] [rbp-20h] BYREF
  RPC_WSTR StringBinding; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 72);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v14 = v2;
  v3 = (_QWORD *)*((_QWORD *)this + 14);
  if ( !v3 || !*v3 )
  {
    StringBinding = 0;
    hBinding = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringBinding,
      0);
    v4 = (unsigned __int16 *)((char *)this + 40);
    if ( *((_QWORD *)this + 8) > 7u )
      v4 = *(unsigned __int16 **)v4;
    v5 = (unsigned __int16 *)((char *)this + 8);
    if ( *((_QWORD *)this + 4) > 7u )
      v5 = *(unsigned __int16 **)v5;
    v6 = RpcStringBindingComposeW(0, L"ncacn_hvsocket", v5, v4, 0, &StringBinding);
    if ( v6 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\hostrpc\\lib\\nlmhostrpcclient.cpp",
        (const char *)v6,
        Options);
    hBinding = 0;
    v7 = RpcBindingFromStringBindingW(StringBinding, &hBinding);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\hostrpc\\lib\\nlmhostrpcclient.cpp",
        (const char *)v7,
        Options);
    v8 = RpcEpResolveBinding(hBinding, *(RPC_IF_HANDLE *)this);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\hostrpc\\lib\\nlmhostrpcclient.cpp",
        (const char *)v8,
        Options);
    v9 = RpcBindingSetOption(hBinding, 0xCu, 0x1388u);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\hostrpc\\lib\\nlmhostrpcclient.cpp",
        (const char *)v9,
        Options);
    v10 = std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
            v12,
            &hBinding);
    std::shared_ptr<KryptonManagement::Container>::operator=((char *)this + 112, v10);
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hBinding);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringBinding);
  }
  if ( v2 )
    LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180089740  mov     [rsp-18h+arg_8], rbx
0x180089745  mov     [rsp-18h+arg_10], rsi
0x18008974a  push    rbp
0x18008974b  push    rdi
0x18008974c  push    r14
0x18008974e  mov     rbp, rsp
0x180089751  sub     rsp, 70h
0x180089755  mov     rax, cs:__security_cookie
0x18008975c  xor     rax, rsp
0x18008975f  mov     [rbp+var_10], rax
0x180089763  mov     rbx, rcx
0x180089766  lea     rdi, [rcx+48h]
0x18008976a  mov     rcx, rdi; lpCriticalSection
0x18008976d  call    cs:__imp_EnterCriticalSection
0x180089773  mov     [rbp+var_30], rdi
0x180089777  mov     rax, [rbx+70h]
0x18008977b  test    rax, rax
0x18008977e  jz      short loc_18008978A
0x180089780  cmp     qword ptr [rax], 0
0x180089784  jnz     loc_1800898F3
0x18008978a  mov     [rbp+var_18], 0
0x180089792  mov     [rbp+hBinding], 0
0x18008979a  xor     edx, edx
0x18008979c  lea     rcx, [rbp+var_18]
0x1800897a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800897a5  lea     r9, [rbx+28h]
0x1800897a9  cmp     qword ptr [r9+18h], 7
0x1800897ae  jbe     short loc_1800897B3
0x1800897b0  mov     r9, [r9]; Endpoint
0x1800897b3  lea     r8, [rbx+8]
0x1800897b7  cmp     qword ptr [r8+18h], 7
0x1800897bc  jbe     short loc_1800897C1
0x1800897be  mov     r8, [r8]; NetworkAddr
0x1800897c1  lea     rax, [rbp+var_18]
0x1800897c5  mov     [rsp+70h+StringBinding], rax; StringBinding
0x1800897ca  mov     [rsp+70h+Options], 0; unsigned int
0x1800897d3  mov     rdx, cs:ProtSeq; ProtSeq
0x1800897da  xor     ecx, ecx; ObjUuid
0x1800897dc  call    cs:__imp_RpcStringBindingComposeW
0x1800897e2  mov     rcx, [rbp+18h]; this
0x1800897e6  test    eax, eax
0x1800897e8  jz      short loc_1800897FF
0x1800897ea  mov     r9d, eax; char *
0x1800897ed  lea     r8, aOnecoreNetNetp_43; "onecore\\net\\netprofiles\\service\\src"...
0x1800897f4  mov     edx, 2Ah ; '*'; void *
0x1800897f9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800897ff  mov     rsi, [rbp+hBinding]
0x180089803  test    rsi, rsi
0x180089806  jz      short loc_180089828
0x180089808  lea     rcx, [rbp+var_40]; this
0x18008980c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180089811  mov     [rbp+Binding], rsi
0x180089815  lea     rcx, [rbp+Binding]; Binding
0x180089819  call    cs:__imp_RpcBindingFree
0x18008981f  lea     rcx, [rbp+var_40]; this
0x180089823  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180089828  mov     [rbp+hBinding], 0
0x180089830  lea     rdx, [rbp+hBinding]; Binding
0x180089834  mov     rcx, [rbp+var_18]; StringBinding
0x180089838  call    cs:__imp_RpcBindingFromStringBindingW
0x18008983e  mov     rcx, [rbp+18h]; this
0x180089842  test    eax, eax
0x180089844  jz      short loc_18008985B
0x180089846  mov     r9d, eax; char *
0x180089849  lea     r8, aOnecoreNetNetp_43; "onecore\\net\\netprofiles\\service\\src"...
0x180089850  mov     edx, 2Ch ; ','; void *
0x180089855  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18008985b  mov     rdx, [rbx]; IfSpec
0x18008985e  mov     rcx, [rbp+hBinding]; Binding
0x180089862  call    cs:__imp_RpcEpResolveBinding
0x180089868  mov     rcx, [rbp+18h]; this
0x18008986c  test    eax, eax
0x18008986e  jz      short loc_180089885
0x180089870  mov     r9d, eax; char *
0x180089873  lea     r8, aOnecoreNetNetp_43; "onecore\\net\\netprofiles\\service\\src"...
0x18008987a  mov     edx, 2Eh ; '.'; void *
0x18008987f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180089885  mov     edx, 0Ch; option
0x18008988a  mov     r8d, 1388h; optionValue
0x180089890  mov     rcx, [rbp+hBinding]; hBinding
0x180089894  call    cs:__imp_RpcBindingSetOption
0x18008989a  mov     rcx, [rbp+18h]; this
0x18008989e  test    eax, eax
0x1800898a0  jz      short loc_1800898B7
0x1800898a2  mov     r9d, eax; char *
0x1800898a5  lea     r8, aOnecoreNetNetp_43; "onecore\\net\\netprofiles\\service\\src"...
0x1800898ac  mov     edx, 30h ; '0'; void *
0x1800898b1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800898b7  lea     rdx, [rbp+hBinding]
0x1800898bb  lea     rcx, [rbp+var_40]
0x1800898bf  call    ??$make_shared@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V12@@std@@YA?AV?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@0@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; std::make_shared<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1800898c4  mov     rdx, rax
0x1800898c7  lea     rcx, [rbx+70h]
0x1800898cb  call    ??4?$shared_ptr@VContainer@KryptonManagement@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<KryptonManagement::Container>::operator=(std::shared_ptr<KryptonManagement::Container> &&)
0x1800898d0  mov     rcx, [rbp+var_38]; this
0x1800898d4  test    rcx, rcx
0x1800898d7  jz      short loc_1800898DF
0x1800898d9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800898de  nop
0x1800898df  lea     rcx, [rbp+hBinding]
0x1800898e3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?WpRpcBindingFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::WpRpcBindingFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800898e8  nop
0x1800898e9  lea     rcx, [rbp+var_18]
0x1800898ed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800898f2  nop
0x1800898f3  test    rdi, rdi
0x1800898f6  jz      short loc_180089901
0x1800898f8  mov     rcx, rdi; lpCriticalSection
0x1800898fb  call    cs:__imp_LeaveCriticalSection
0x180089901  mov     rcx, [rbp+var_10]
0x180089905  xor     rcx, rsp; StackCookie
0x180089908  call    __security_check_cookie
0x18008990d  lea     r11, [rsp+70h+var_s0]
0x180089912  mov     rbx, [r11+28h]
0x180089916  mov     rsi, [r11+30h]
0x18008991a  mov     rsp, r11
0x18008991d  pop     r14
0x18008991f  pop     rdi
0x180089920  pop     rbp
0x180089921  retn
```
