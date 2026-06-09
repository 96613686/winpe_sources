# EapLm::Peer::ThirdPartyEapMethodConfig::GetMethodProperties(uint,uint,void *,ConstBuffer const &,ConstBuffer const &,_EAP_METHOD_PROPERTY_ARRAY *)

- ea: `0x18001f170`
- end: `0x18001f2e3`
- name: `?GetMethodProperties@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXIIPEAXAEBUConstBuffer@@1PEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z`
- size: `371`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodConfig *__hidden this, unsigned int, unsigned int, void *, const struct ConstBuffer *, const struct ConstBuffer *, struct _EAP_METHOD_PROPERTY_ARRAY *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180005894`
- `0x18000ce00`
- `0x18000cf78`
- `0x18000d0e8`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800177bc`
- `0x180017e54`
- `0x18001ecf8`
- `0x18001f170`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::GetMethodProperties(
        const struct _EAP_METHOD_TYPE *this,
        unsigned int a2,
        unsigned int a3,
        void *a4,
        const struct ConstBuffer *a5,
        const struct ConstBuffer *a6,
        struct _EAP_METHOD_PROPERTY_ARRAY *a7)
{
  LPVOID *Proxy; // rax
  LPVOID v9; // r15
  __int64 (__fastcall *v10)(LPVOID, _QWORD, _QWORD, const struct _EAP_METHOD_TYPE *, void *, int, __int64, int, __int64, __int128 *, struct _EAP_ERROR **); // r14
  __int64 v11; // rsi
  int v12; // ebx
  __int64 v13; // rdi
  int v14; // eax
  signed int v15; // ebx
  __int64 v16; // r8
  __int64 v17; // r9
  struct _EAP_METHOD_PROPERTY_ARRAY v18; // xmm1
  struct _EAP_ERROR *v21; // [rsp+68h] [rbp-98h] BYREF
  struct _EAP_METHOD_PROPERTY_ARRAY v22; // [rsp+70h] [rbp-90h] BYREF
  void *v23; // [rsp+80h] [rbp-80h]
  struct _EAP_METHOD_PROPERTY_ARRAY *v24; // [rsp+88h] [rbp-78h]
  __int128 v25; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-60h]
  _BYTE v27[96]; // [rsp+B0h] [rbp-50h] BYREF

  v23 = a4;
  v24 = a7;
  v25 = 0;
  v26 = 1;
  v21 = 0;
  Proxy = EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(this, (LPVOID *)&v22);
  v9 = *Proxy;
  v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, const struct _EAP_METHOD_TYPE *, void *, int, __int64, int, __int64, __int128 *, struct _EAP_ERROR **))(*(_QWORD *)*Proxy + 112LL);
  v11 = *(_QWORD *)a6;
  v12 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*((_QWORD *)a6 + 1));
  v13 = *(_QWORD *)a5;
  v14 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*((_QWORD *)a5 + 1));
  v15 = v10(v9, a2, a3, this + 1, v23, v14, v13, v12, v11, &v25, &v21);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v22);
  if ( v15 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v27, v21, v15);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v27);
  }
  v22 = 0;
  crt_ref<_EAP_METHOD_PROPERTY_ARRAY>::Assign(&v22, &v25, v16, v17);
  v18 = v22;
  v22 = 0;
  *v24 = v18;
  Free<HeapAllocator>(&v22);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)&v21);
  Free<TaskAllocator>((__int64)&v25);
}

```

## disassembly

```asm
0x18001f170  push    rbp
0x18001f172  push    rbx
0x18001f173  push    rsi
0x18001f174  push    rdi
0x18001f175  push    r12
0x18001f177  push    r13
0x18001f179  push    r14
0x18001f17b  push    r15
0x18001f17d  lea     rbp, [rsp-28h]
0x18001f182  sub     rsp, 128h
0x18001f189  mov     rax, cs:__security_cookie
0x18001f190  xor     rax, rsp
0x18001f193  mov     [rbp+60h+var_50], rax
0x18001f197  mov     [rbp+60h+var_E0], r9
0x18001f19b  mov     [rsp+160h+var_100], r8d
0x18001f1a0  mov     [rsp+160h+var_FC], edx
0x18001f1a4  mov     r13, rcx
0x18001f1a7  mov     r12, [rbp+60h+arg_20]
0x18001f1ae  mov     rbx, [rbp+60h+arg_28]
0x18001f1b5  mov     rax, [rbp+60h+arg_30]
0x18001f1bc  mov     [rbp+60h+var_D8], rax
0x18001f1c0  xorps   xmm0, xmm0
0x18001f1c3  xor     eax, eax
0x18001f1c5  movups  [rbp+60h+var_D0], xmm0
0x18001f1c9  mov     [rbp+60h+var_C0], rax
0x18001f1cd  mov     byte ptr [rbp+60h+var_C0], 1
0x18001f1d1  mov     [rsp+160h+var_F8], rax
0x18001f1d6  lea     rdx, [rsp+160h+var_F0]
0x18001f1db  call    ?CreateProxy@ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@XZ; EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(void)
0x18001f1e0  nop
0x18001f1e1  mov     r15, [rax]
0x18001f1e4  mov     rax, [r15]
0x18001f1e7  mov     r14, [rax+70h]
0x18001f1eb  mov     rsi, [rbx]
0x18001f1ee  mov     rcx, [rbx+8]
0x18001f1f2  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001f1f7  mov     ebx, eax
0x18001f1f9  mov     rdi, [r12]
0x18001f1fd  mov     rcx, [r12+8]
0x18001f202  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001f207  lea     r9, [r13+10h]
0x18001f20b  lea     rcx, [rsp+160h+var_F8]
0x18001f210  mov     [rsp+160h+var_110], rcx
0x18001f215  lea     rcx, [rbp+60h+var_D0]
0x18001f219  mov     [rsp+160h+var_118], rcx
0x18001f21e  mov     [rsp+160h+var_120], rsi
0x18001f223  mov     [rsp+160h+var_128], ebx
0x18001f227  mov     [rsp+160h+var_130], rdi
0x18001f22c  mov     [rsp+160h+var_138], eax
0x18001f230  mov     rax, [rbp+60h+var_E0]
0x18001f234  mov     [rsp+160h+var_140], rax
0x18001f239  mov     r8d, [rsp+160h+var_100]
0x18001f23e  mov     edx, [rsp+160h+var_FC]
0x18001f242  mov     rcx, r15
0x18001f245  mov     rax, r14
0x18001f248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f24d  mov     ebx, eax
0x18001f24f  lea     rcx, [rsp+160h+var_F0]
0x18001f254  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001f259  test    ebx, ebx
0x18001f25b  jns     short loc_18001F279
0x18001f25d  mov     r8d, ebx; unsigned int
0x18001f260  mov     rdx, [rsp+160h+var_F8]; struct _EAP_ERROR *
0x18001f265  lea     rcx, [rbp+60h+var_B0]; this
0x18001f269  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001f26e  nop
0x18001f26f  lea     rcx, [rbp+60h+var_B0]; struct EapHost::EapError *
0x18001f273  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001f279  xorps   xmm0, xmm0
0x18001f27c  movups  [rsp+160h+var_F0], xmm0
0x18001f281  lea     rdx, [rbp+60h+var_D0]
0x18001f285  lea     rcx, [rsp+160h+var_F0]
0x18001f28a  call    ?Assign@?$crt_ref@U_EAP_METHOD_PROPERTY_ARRAY@@@@QEAAXAEBU_EAP_METHOD_PROPERTY_ARRAY@@@Z; crt_ref<_EAP_METHOD_PROPERTY_ARRAY>::Assign(_EAP_METHOD_PROPERTY_ARRAY const &)
0x18001f28f  movaps  xmm1, [rsp+160h+var_F0]
0x18001f294  xorps   xmm0, xmm0
0x18001f297  movups  [rsp+160h+var_F0], xmm0
0x18001f29c  mov     rax, [rbp+60h+var_D8]
0x18001f2a0  movdqu  xmmword ptr [rax], xmm1
0x18001f2a4  lea     rcx, [rsp+160h+var_F0]
0x18001f2a9  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z; Free<HeapAllocator>(_EAP_METHOD_PROPERTY_ARRAY &)
0x18001f2ae  nop
0x18001f2af  lea     rcx, [rsp+160h+var_F8]
0x18001f2b4  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001f2b9  nop
0x18001f2ba  lea     rcx, [rbp+60h+var_D0]
0x18001f2be  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_PROPERTY_ARRAY@@@Z; Free<TaskAllocator>(_EAP_METHOD_PROPERTY_ARRAY &)
0x18001f2c3  mov     rcx, [rbp+60h+var_50]
0x18001f2c7  xor     rcx, rsp; StackCookie
0x18001f2ca  call    __security_check_cookie
0x18001f2cf  add     rsp, 128h
0x18001f2d6  pop     r15
0x18001f2d8  pop     r14
0x18001f2da  pop     r13
0x18001f2dc  pop     r12
0x18001f2de  pop     rdi
0x18001f2df  pop     rsi
0x18001f2e0  pop     rbx
0x18001f2e1  pop     rbp
0x18001f2e2  retn
```
