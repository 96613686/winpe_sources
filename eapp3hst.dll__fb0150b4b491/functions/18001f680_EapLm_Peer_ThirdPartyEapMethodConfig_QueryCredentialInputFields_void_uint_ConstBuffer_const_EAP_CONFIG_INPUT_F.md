# EapLm::Peer::ThirdPartyEapMethodConfig::QueryCredentialInputFields(void *,uint,ConstBuffer const &,_EAP_CONFIG_INPUT_FIELD_ARRAY *)

- ea: `0x18001f680`
- end: `0x18001f7d0`
- name: `?QueryCredentialInputFields@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXPEAXIAEBUConstBuffer@@PEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z`
- size: `336`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodConfig *__hidden this, void *, unsigned int, const struct ConstBuffer *, struct _EAP_CONFIG_INPUT_FIELD_ARRAY *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180005894`
- `0x18000ccf4`
- `0x18000ce64`
- `0x18000d0e8`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800177bc`
- `0x180017dbc`
- `0x18001ecf8`
- `0x18001f680`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::QueryCredentialInputFields(
        const struct _EAP_METHOD_TYPE *this,
        void *a2,
        unsigned int a3,
        const struct ConstBuffer *a4,
        struct _EAP_CONFIG_INPUT_FIELD_ARRAY *a5)
{
  LPVOID *Proxy; // rax
  LPVOID v10; // rsi
  __int64 (__fastcall *v11)(LPVOID, void *, struct _EAP_METHOD_TYPE *, _QWORD, int, __int64, __int128 *, struct _EAP_ERROR **); // rdi
  __int64 v12; // rbx
  int v13; // eax
  signed int v14; // ebx
  struct _EAP_CONFIG_INPUT_FIELD_ARRAY v15; // xmm1
  struct _EAP_ERROR *v16[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _EAP_CONFIG_INPUT_FIELD_ARRAY v17; // [rsp+60h] [rbp-A0h] BYREF
  struct _EAP_CONFIG_INPUT_FIELD_ARRAY *v18; // [rsp+70h] [rbp-90h]
  __int128 v19; // [rsp+78h] [rbp-88h] BYREF
  __int64 v20; // [rsp+88h] [rbp-78h]
  struct _EAP_METHOD_TYPE v21; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v22[96]; // [rsp+A0h] [rbp-60h] BYREF

  v18 = a5;
  v16[0] = 0;
  v19 = 0;
  v20 = 1;
  Proxy = EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(this, (LPVOID *)&v17);
  v10 = *Proxy;
  v11 = *(__int64 (__fastcall **)(LPVOID, void *, struct _EAP_METHOD_TYPE *, _QWORD, int, __int64, __int128 *, struct _EAP_ERROR **))(*(_QWORD *)*Proxy + 40LL);
  v12 = *(_QWORD *)a4;
  v13 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*((_QWORD *)a4 + 1));
  v21 = this[1];
  v14 = v11(v10, a2, &v21, a3, v13, v12, &v19, v16);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v17);
  if ( v14 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v22, v16[0], v14);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v22);
  }
  v17 = 0;
  crt_ref<_EAP_CONFIG_INPUT_FIELD_ARRAY>::Assign(&v17, (__int64)&v19);
  v15 = v17;
  v17 = 0;
  *v18 = v15;
  Free<HeapAllocator>((__int64)&v17);
  Free<TaskAllocator>((__int64)&v19);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)v16);
}

```

## disassembly

```asm
0x18001f680  push    rbp
0x18001f682  push    rbx
0x18001f683  push    rsi
0x18001f684  push    rdi
0x18001f685  push    r12
0x18001f687  push    r13
0x18001f689  push    r14
0x18001f68b  push    r15
0x18001f68d  lea     rbp, [rsp-18h]
0x18001f692  sub     rsp, 118h
0x18001f699  mov     rax, cs:__security_cookie
0x18001f6a0  xor     rax, rsp
0x18001f6a3  mov     [rbp+50h+var_50], rax
0x18001f6a7  mov     r15, r9
0x18001f6aa  mov     r12d, r8d
0x18001f6ad  mov     r13, rdx
0x18001f6b0  mov     r14, rcx
0x18001f6b3  mov     rax, [rbp+50h+arg_20]
0x18001f6ba  mov     [rsp+150h+var_E0], rax
0x18001f6bf  mov     [rsp+150h+var_100], 0
0x18001f6c8  xorps   xmm0, xmm0
0x18001f6cb  xor     eax, eax
0x18001f6cd  movups  [rsp+150h+var_D8], xmm0
0x18001f6d2  mov     [rbp+50h+var_C8], rax
0x18001f6d6  mov     byte ptr [rbp+50h+var_C8], 1
0x18001f6da  lea     rdx, [rsp+150h+var_F0]
0x18001f6df  call    ?CreateProxy@ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@XZ; EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(void)
0x18001f6e4  nop
0x18001f6e5  mov     rsi, [rax]
0x18001f6e8  mov     rax, [rsi]
0x18001f6eb  mov     rdi, [rax+28h]
0x18001f6ef  mov     rbx, [r15]
0x18001f6f2  mov     rcx, [r15+8]
0x18001f6f6  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001f6fb  movups  xmm0, xmmword ptr [r14+10h]
0x18001f700  movdqu  [rbp+50h+var_C0], xmm0
0x18001f705  lea     rcx, [rsp+150h+var_100]
0x18001f70a  mov     [rsp+150h+var_118], rcx
0x18001f70f  lea     rcx, [rsp+150h+var_D8]
0x18001f714  mov     [rsp+150h+var_120], rcx
0x18001f719  mov     [rsp+150h+var_128], rbx
0x18001f71e  mov     [rsp+150h+var_130], eax
0x18001f722  mov     r9d, r12d
0x18001f725  lea     r8, [rbp+50h+var_C0]
0x18001f729  mov     rdx, r13
0x18001f72c  mov     rcx, rsi
0x18001f72f  mov     rax, rdi
0x18001f732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f737  mov     ebx, eax
0x18001f739  lea     rcx, [rsp+150h+var_F0]
0x18001f73e  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001f743  test    ebx, ebx
0x18001f745  jns     short loc_18001F763
0x18001f747  mov     r8d, ebx; unsigned int
0x18001f74a  mov     rdx, [rsp+150h+var_100]; struct _EAP_ERROR *
0x18001f74f  lea     rcx, [rbp+50h+var_B0]; this
0x18001f753  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001f758  nop
0x18001f759  lea     rcx, [rbp+50h+var_B0]; struct EapHost::EapError *
0x18001f75d  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001f763  xorps   xmm0, xmm0
0x18001f766  movups  [rsp+150h+var_F0], xmm0
0x18001f76b  lea     rdx, [rsp+150h+var_D8]
0x18001f770  lea     rcx, [rsp+150h+var_F0]
0x18001f775  call    ?Assign@?$crt_ref@U_EAP_CONFIG_INPUT_FIELD_ARRAY@@@@QEAAXAEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; crt_ref<_EAP_CONFIG_INPUT_FIELD_ARRAY>::Assign(_EAP_CONFIG_INPUT_FIELD_ARRAY const &)
0x18001f77a  movaps  xmm1, [rsp+150h+var_F0]
0x18001f77f  xorps   xmm0, xmm0
0x18001f782  movups  [rsp+150h+var_F0], xmm0
0x18001f787  mov     rax, [rsp+150h+var_E0]
0x18001f78c  movdqu  xmmword ptr [rax], xmm1
0x18001f790  lea     rcx, [rsp+150h+var_F0]
0x18001f795  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; Free<HeapAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)
0x18001f79a  nop
0x18001f79b  lea     rcx, [rsp+150h+var_D8]
0x18001f7a0  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; Free<TaskAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)
0x18001f7a5  nop
0x18001f7a6  lea     rcx, [rsp+150h+var_100]
0x18001f7ab  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001f7b0  mov     rcx, [rbp+50h+var_50]
0x18001f7b4  xor     rcx, rsp; StackCookie
0x18001f7b7  call    __security_check_cookie
0x18001f7bc  add     rsp, 118h
0x18001f7c3  pop     r15
0x18001f7c5  pop     r14
0x18001f7c7  pop     r13
0x18001f7c9  pop     r12
0x18001f7cb  pop     rdi
0x18001f7cc  pop     rsi
0x18001f7cd  pop     rbx
0x18001f7ce  pop     rbp
0x18001f7cf  retn
```
