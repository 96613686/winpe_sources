# EapLm::Peer::ThirdPartyEapMethodConfig::QueryUserBlobFromCredentialInputFields(void *,uint,ConstBuffer const &,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,TempBuffer<0> &)

- ea: `0x18001fb30`
- end: `0x18001fc98`
- name: `?QueryUserBlobFromCredentialInputFields@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXPEAXIAEBUConstBuffer@@PEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180005894`
- `0x1800067cc`
- `0x180006c0c`
- `0x18000d0e8`
- `0x1800126f8`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800177bc`
- `0x18001ecf8`
- `0x18001fb30`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::QueryUserBlobFromCredentialInputFields(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6)
{
  unsigned int v9; // eax
  LPVOID *v10; // rax
  LPVOID v11; // rsi
  __int64 (__fastcall *v12)(LPVOID, __int64, __int128 *, _QWORD, int, __int64, __int64, unsigned int *, void **, struct _EAP_ERROR **); // rdi
  __int64 v13; // rbx
  int v14; // eax
  signed int v15; // ebx
  unsigned int v16; // [rsp+60h] [rbp-A0h] BYREF
  void *v17; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v18; // [rsp+70h] [rbp-90h]
  struct _EAP_ERROR *v19; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v20; // [rsp+80h] [rbp-80h] BYREF
  __int64 v21; // [rsp+88h] [rbp-78h]
  __int128 v22; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[96]; // [rsp+A0h] [rbp-60h] BYREF

  v18 = a3;
  v21 = a5;
  v16 = 0;
  v17 = 0;
  v19 = 0;
  v9 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*(_QWORD *)(a6 + 8));
  v16 = v9;
  if ( v9 )
    com_ptr<unsigned char>::Assign(&v17, *(void **)a6, v9);
  v10 = EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy((const struct _EAP_METHOD_TYPE *)a1, &v20);
  v11 = *v10;
  v12 = *(__int64 (__fastcall **)(LPVOID, __int64, __int128 *, _QWORD, int, __int64, __int64, unsigned int *, void **, struct _EAP_ERROR **))(*(_QWORD *)*v10 + 48LL);
  v13 = *a4;
  v14 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  v22 = *(_OWORD *)(a1 + 16);
  v15 = v12(v11, a2, &v22, v18, v14, v13, v21, &v16, &v17, &v19);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v20);
  if ( v15 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v23, v19, v15);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v23);
  }
  v20 = 0;
  TempBuffer<0>::Assign(a6, v16, v17);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)&v19);
  com_ptr<unsigned char>::Clear(&v17);
}

```

## disassembly

```asm
0x18001fb30  push    rbp
0x18001fb32  push    rbx
0x18001fb33  push    rsi
0x18001fb34  push    rdi
0x18001fb35  push    r12
0x18001fb37  push    r13
0x18001fb39  push    r14
0x18001fb3b  push    r15
0x18001fb3d  lea     rbp, [rsp-18h]
0x18001fb42  sub     rsp, 118h
0x18001fb49  mov     rax, cs:__security_cookie
0x18001fb50  xor     rax, rsp
0x18001fb53  mov     [rbp+50h+var_50], rax
0x18001fb57  mov     r12, r9
0x18001fb5a  mov     [rsp+150h+var_E0], r8d
0x18001fb5f  mov     r13, rdx
0x18001fb62  mov     r15, rcx
0x18001fb65  mov     rax, [rbp+50h+arg_20]
0x18001fb6c  mov     [rbp+50h+var_C8], rax
0x18001fb70  mov     r14, [rbp+50h+arg_28]
0x18001fb77  xor     ebx, ebx
0x18001fb79  mov     [rsp+150h+var_F0], ebx
0x18001fb7d  mov     [rsp+150h+var_E8], rbx
0x18001fb82  mov     [rsp+150h+var_D8], rbx
0x18001fb87  mov     rcx, [r14+8]
0x18001fb8b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001fb90  mov     [rsp+150h+var_F0], eax
0x18001fb94  test    eax, eax
0x18001fb96  jz      short loc_18001FBA8
0x18001fb98  mov     r8d, eax
0x18001fb9b  mov     rdx, [r14]
0x18001fb9e  lea     rcx, [rsp+150h+var_E8]
0x18001fba3  call    ?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z; com_ptr<uchar>::Assign(uchar const *,unsigned __int64)
0x18001fba8  lea     rdx, [rbp+50h+var_D0]
0x18001fbac  mov     rcx, r15
0x18001fbaf  call    ?CreateProxy@ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@XZ; EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(void)
0x18001fbb4  nop
0x18001fbb5  mov     rsi, [rax]
0x18001fbb8  mov     rax, [rsi]
0x18001fbbb  mov     rdi, [rax+30h]
0x18001fbbf  mov     rbx, [r12]
0x18001fbc3  mov     rcx, [r12+8]
0x18001fbc8  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001fbcd  movups  xmm0, xmmword ptr [r15+10h]
0x18001fbd2  movdqu  [rbp+50h+var_C0], xmm0
0x18001fbd7  lea     rcx, [rsp+150h+var_D8]
0x18001fbdc  mov     [rsp+150h+var_108], rcx
0x18001fbe1  lea     rcx, [rsp+150h+var_E8]
0x18001fbe6  mov     [rsp+150h+var_110], rcx
0x18001fbeb  lea     rcx, [rsp+150h+var_F0]
0x18001fbf0  mov     [rsp+150h+var_118], rcx
0x18001fbf5  mov     rcx, [rbp+50h+var_C8]
0x18001fbf9  mov     [rsp+150h+var_120], rcx
0x18001fbfe  mov     [rsp+150h+var_128], rbx
0x18001fc03  mov     [rsp+150h+var_130], eax
0x18001fc07  mov     r9d, [rsp+150h+var_E0]
0x18001fc0c  lea     r8, [rbp+50h+var_C0]
0x18001fc10  mov     rdx, r13
0x18001fc13  mov     rcx, rsi
0x18001fc16  mov     rax, rdi
0x18001fc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc1e  mov     ebx, eax
0x18001fc20  lea     rcx, [rbp+50h+var_D0]
0x18001fc24  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001fc29  test    ebx, ebx
0x18001fc2b  jns     short loc_18001FC49
0x18001fc2d  mov     r8d, ebx; unsigned int
0x18001fc30  mov     rdx, [rsp+150h+var_D8]; struct _EAP_ERROR *
0x18001fc35  lea     rcx, [rbp+50h+var_B0]; this
0x18001fc39  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001fc3e  nop
0x18001fc3f  lea     rcx, [rbp+50h+var_B0]; struct EapHost::EapError *
0x18001fc43  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001fc49  mov     [rbp+50h+var_D0], 0
0x18001fc51  mov     edx, [rsp+150h+var_F0]
0x18001fc55  mov     r8, [rsp+150h+var_E8]
0x18001fc5a  mov     rcx, r14
0x18001fc5d  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001fc62  nop
0x18001fc63  lea     rcx, [rsp+150h+var_D8]
0x18001fc68  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001fc6d  nop
0x18001fc6e  lea     rcx, [rsp+150h+var_E8]
0x18001fc73  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18001fc78  mov     rcx, [rbp+50h+var_50]
0x18001fc7c  xor     rcx, rsp; StackCookie
0x18001fc7f  call    __security_check_cookie
0x18001fc84  add     rsp, 118h
0x18001fc8b  pop     r15
0x18001fc8d  pop     r14
0x18001fc8f  pop     r13
0x18001fc91  pop     r12
0x18001fc93  pop     rdi
0x18001fc94  pop     rsi
0x18001fc95  pop     rbx
0x18001fc96  pop     rbp
0x18001fc97  retn
```
