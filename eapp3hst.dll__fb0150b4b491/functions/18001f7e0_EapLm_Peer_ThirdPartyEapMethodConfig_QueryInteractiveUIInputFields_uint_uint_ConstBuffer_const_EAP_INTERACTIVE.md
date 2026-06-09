# EapLm::Peer::ThirdPartyEapMethodConfig::QueryInteractiveUIInputFields(uint,uint,ConstBuffer const &,_EAP_INTERACTIVE_UI_DATA *)

- ea: `0x18001f7e0`
- end: `0x18001f981`
- name: `?QueryInteractiveUIInputFields@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXIIAEBUConstBuffer@@PEAU_EAP_INTERACTIVE_UI_DATA@@@Z`
- size: `417`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodConfig *__hidden this, unsigned int, unsigned int, const struct ConstBuffer *, struct _EAP_INTERACTIVE_UI_DATA *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180005894`
- `0x180006c0c`
- `0x18000cd8c`
- `0x18000cf00`
- `0x18000d0e8`
- `0x180013dbc`
- `0x1800151ec`
- `0x180017790`
- `0x1800177bc`
- `0x18001b1dc`
- `0x18001ecf8`
- `0x18001f7e0`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::QueryInteractiveUIInputFields(
        const struct _EAP_METHOD_TYPE *this,
        unsigned int a2,
        unsigned int a3,
        const struct ConstBuffer *a4,
        struct _EAP_INTERACTIVE_UI_DATA *a5)
{
  LPVOID *v8; // rax
  LPVOID v9; // rsi
  __int64 (__fastcall *v10)(LPVOID, _QWORD, struct _EAP_METHOD_TYPE *, _QWORD, int, __int64, __int128 *, struct _EAP_ERROR **, void **); // rdi
  __int64 v11; // rbx
  int v12; // eax
  signed int v13; // ebx
  struct _EAP_METHOD_TYPE v14; // xmm1
  EAP_UI_DATA_FORMAT v15; // xmm2_8
  struct _EAP_ERROR *v17; // [rsp+58h] [rbp-A8h] BYREF
  void *v18[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _EAP_METHOD_TYPE v19; // [rsp+70h] [rbp-90h] BYREF
  EAP_UI_DATA_FORMAT v20; // [rsp+80h] [rbp-80h]
  LPVOID v21; // [rsp+90h] [rbp-70h] BYREF
  __int128 v22; // [rsp+98h] [rbp-68h] BYREF
  __int128 v23; // [rsp+A8h] [rbp-58h]
  _BYTE v24[96]; // [rsp+C0h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_P(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids,
      *((_QWORD *)a4 + 1));
  v17 = 0;
  v22 = 0;
  v23 = 0;
  BYTE8(v23) = 1;
  v18[0] = 0;
  v8 = EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(this, &v21);
  v9 = *v8;
  v10 = *(__int64 (__fastcall **)(LPVOID, _QWORD, struct _EAP_METHOD_TYPE *, _QWORD, int, __int64, __int128 *, struct _EAP_ERROR **, void **))(*(_QWORD *)*v8 + 64LL);
  v11 = *(_QWORD *)a4;
  v12 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*((_QWORD *)a4 + 1));
  v19 = this[1];
  v13 = v10(v9, a2, &v19, a3, v12, v11, &v22, &v17, v18);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v21);
  if ( v13 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v24, v17, v13);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v24);
  }
  crt_ref<_EAP_INTERACTIVE_UI_DATA>::crt_ref<_EAP_INTERACTIVE_UI_DATA>(&v19, &v22);
  v14 = v19;
  v15.credData = v20.credData;
  v19 = 0;
  v20.credData = 0;
  *(struct _EAP_METHOD_TYPE *)&a5->dwVersion = v14;
  a5->pbUiData = v15;
  Free<HeapAllocator>(&v19);
  com_ptr<unsigned char>::Clear(v18);
  Free<TaskAllocator>((__int64)&v22);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)&v17);
}

```

## disassembly

```asm
0x18001f7e0  push    rbp
0x18001f7e2  push    rbx
0x18001f7e3  push    rsi
0x18001f7e4  push    rdi
0x18001f7e5  push    r12
0x18001f7e7  push    r13
0x18001f7e9  push    r14
0x18001f7eb  push    r15
0x18001f7ed  lea     rbp, [rsp-38h]
0x18001f7f2  sub     rsp, 138h
0x18001f7f9  mov     rax, cs:__security_cookie
0x18001f800  xor     rax, rsp
0x18001f803  mov     [rbp+70h+var_50], rax
0x18001f807  mov     r15, r9
0x18001f80a  mov     [rsp+170h+var_120], r8d
0x18001f80f  mov     r13d, edx
0x18001f812  mov     r12, rcx
0x18001f815  mov     r14, [rbp+70h+arg_20]
0x18001f81c  lea     rax, WPP_GLOBAL_Control
0x18001f823  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f82a  cmp     rcx, rax
0x18001f82d  jz      short loc_18001F84E
0x18001f82f  test    byte ptr [rcx+1Ch], 4
0x18001f833  jz      short loc_18001F84E
0x18001f835  mov     edx, 14h
0x18001f83a  mov     r9, [r9+8]
0x18001f83e  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001f845  mov     rcx, [rcx+10h]
0x18001f849  call    WPP_SF_P
0x18001f84e  mov     [rsp+170h+var_118], 0
0x18001f857  xorps   xmm0, xmm0
0x18001f85a  movups  [rbp+70h+var_D8], xmm0
0x18001f85e  movups  [rbp+70h+var_C8], xmm0
0x18001f862  mov     byte ptr [rbp+70h+var_C8+8], 1
0x18001f866  mov     [rsp+170h+var_110], 0
0x18001f86f  lea     rdx, [rbp+70h+var_E0]
0x18001f873  mov     rcx, r12
0x18001f876  call    ?CreateProxy@ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@XZ; EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(void)
0x18001f87b  nop
0x18001f87c  mov     rsi, [rax]
0x18001f87f  mov     rax, [rsi]
0x18001f882  mov     rdi, [rax+40h]
0x18001f886  mov     rbx, [r15]
0x18001f889  mov     rcx, [r15+8]
0x18001f88d  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001f892  movups  xmm0, xmmword ptr [r12+10h]
0x18001f898  movdqu  [rsp+170h+var_100], xmm0
0x18001f89e  lea     rcx, [rsp+170h+var_110]
0x18001f8a3  mov     [rsp+170h+var_130], rcx
0x18001f8a8  lea     rcx, [rsp+170h+var_118]
0x18001f8ad  mov     [rsp+170h+var_138], rcx
0x18001f8b2  lea     rcx, [rbp+70h+var_D8]
0x18001f8b6  mov     [rsp+170h+var_140], rcx
0x18001f8bb  mov     [rsp+170h+var_148], rbx
0x18001f8c0  mov     [rsp+170h+var_150], eax
0x18001f8c4  mov     r9d, [rsp+170h+var_120]
0x18001f8c9  lea     r8, [rsp+170h+var_100]
0x18001f8ce  mov     edx, r13d
0x18001f8d1  mov     rcx, rsi
0x18001f8d4  mov     rax, rdi
0x18001f8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8dc  mov     ebx, eax
0x18001f8de  lea     rcx, [rbp+70h+var_E0]
0x18001f8e2  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001f8e7  test    ebx, ebx
0x18001f8e9  jns     short loc_18001F907
0x18001f8eb  mov     r8d, ebx; unsigned int
0x18001f8ee  mov     rdx, [rsp+170h+var_118]; struct _EAP_ERROR *
0x18001f8f3  lea     rcx, [rbp+70h+var_B0]; this
0x18001f8f7  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001f8fc  nop
0x18001f8fd  lea     rcx, [rbp+70h+var_B0]; struct EapHost::EapError *
0x18001f901  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001f907  lea     rdx, [rbp+70h+var_D8]
0x18001f90b  lea     rcx, [rsp+170h+var_100]
0x18001f910  call    ??0?$crt_ref@U_EAP_INTERACTIVE_UI_DATA@@@@QEAA@AEBU_EAP_INTERACTIVE_UI_DATA@@@Z; crt_ref<_EAP_INTERACTIVE_UI_DATA>::crt_ref<_EAP_INTERACTIVE_UI_DATA>(_EAP_INTERACTIVE_UI_DATA const &)
0x18001f915  movups  xmm1, [rsp+170h+var_100]
0x18001f91a  movsd   xmm2, [rbp+70h+var_F0]
0x18001f91f  xorps   xmm0, xmm0
0x18001f922  xor     eax, eax
0x18001f924  movups  [rsp+170h+var_100], xmm0
0x18001f929  mov     [rbp+70h+var_F0], rax
0x18001f92d  movups  xmmword ptr [r14], xmm1
0x18001f931  movsd   qword ptr [r14+10h], xmm2
0x18001f937  lea     rcx, [rsp+170h+var_100]
0x18001f93c  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_INTERACTIVE_UI_DATA@@@Z; Free<HeapAllocator>(_EAP_INTERACTIVE_UI_DATA &)
0x18001f941  nop
0x18001f942  lea     rcx, [rsp+170h+var_110]
0x18001f947  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18001f94c  nop
0x18001f94d  lea     rcx, [rbp+70h+var_D8]
0x18001f951  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_INTERACTIVE_UI_DATA@@@Z; Free<TaskAllocator>(_EAP_INTERACTIVE_UI_DATA &)
0x18001f956  nop
0x18001f957  lea     rcx, [rsp+170h+var_118]
0x18001f95c  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001f961  mov     rcx, [rbp+70h+var_50]
0x18001f965  xor     rcx, rsp; StackCookie
0x18001f968  call    __security_check_cookie
0x18001f96d  add     rsp, 138h
0x18001f974  pop     r15
0x18001f976  pop     r14
0x18001f978  pop     r13
0x18001f97a  pop     r12
0x18001f97c  pop     rdi
0x18001f97d  pop     rsi
0x18001f97e  pop     rbx
0x18001f97f  pop     rbp
0x18001f980  retn
```
