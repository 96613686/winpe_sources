# EapLm::Peer::ThirdPartyEapMethodConfig::QueryUIBlobFromInteractiveUIInputFields(uint,uint,ConstBuffer const &,_EAP_INTERACTIVE_UI_DATA const *,TempBuffer<0> &)

- ea: `0x18001f990`
- end: `0x18001fb22`
- name: `?QueryUIBlobFromInteractiveUIInputFields@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXIIAEBUConstBuffer@@PEBU_EAP_INTERACTIVE_UI_DATA@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `402`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180005894`
- `0x180006c0c`
- `0x18000d0e8`
- `0x1800126f8`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800177bc`
- `0x18001b1dc`
- `0x18001ecf8`
- `0x18001f990`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::QueryUIBlobFromInteractiveUIInputFields(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6)
{
  LPVOID *v9; // rax
  LPVOID v10; // rsi
  __int64 (__fastcall *v11)(LPVOID, _QWORD, __int128 *, _QWORD, int, __int64, __int64, unsigned int *, void **, struct _EAP_ERROR **, void **); // rdi
  __int64 v12; // rbx
  int v13; // eax
  signed int v14; // ebx
  unsigned int v15; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v16; // [rsp+64h] [rbp-9Ch]
  void *v17; // [rsp+68h] [rbp-98h] BYREF
  struct _EAP_ERROR *v18; // [rsp+70h] [rbp-90h] BYREF
  void *v19; // [rsp+78h] [rbp-88h] BYREF
  LPVOID v20; // [rsp+80h] [rbp-80h] BYREF
  __int64 v21; // [rsp+88h] [rbp-78h]
  __int128 v22; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[96]; // [rsp+A0h] [rbp-60h] BYREF

  v16 = a3;
  v21 = a5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids, a4[1]);
  v15 = 0;
  v18 = 0;
  v17 = 0;
  v19 = 0;
  v9 = EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy((const struct _EAP_METHOD_TYPE *)a1, &v20);
  v10 = *v9;
  v11 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int128 *, _QWORD, int, __int64, __int64, unsigned int *, void **, struct _EAP_ERROR **, void **))(*(_QWORD *)*v9 + 72LL);
  v12 = *a4;
  v13 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  v22 = *(_OWORD *)(a1 + 16);
  v14 = v11(v10, a2, &v22, v16, v13, v12, v21, &v15, &v17, &v18, &v19);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v20);
  if ( v14 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v23, v18, v14);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v23);
  }
  v20 = 0;
  TempBuffer<0>::Assign(a6, v15, v17);
  com_ptr<unsigned char>::Clear(&v19);
  com_ptr<unsigned char>::Clear(&v17);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)&v18);
}

```

## disassembly

```asm
0x18001f990  push    rbp
0x18001f992  push    rbx
0x18001f993  push    rsi
0x18001f994  push    rdi
0x18001f995  push    r12
0x18001f997  push    r13
0x18001f999  push    r14
0x18001f99b  push    r15
0x18001f99d  lea     rbp, [rsp-18h]
0x18001f9a2  sub     rsp, 118h
0x18001f9a9  mov     rax, cs:__security_cookie
0x18001f9b0  xor     rax, rsp
0x18001f9b3  mov     [rbp+50h+var_50], rax
0x18001f9b7  mov     r14, r9
0x18001f9ba  mov     [rsp+150h+var_EC], r8d
0x18001f9bf  mov     r13d, edx
0x18001f9c2  mov     r12, rcx
0x18001f9c5  mov     rax, [rbp+50h+arg_20]
0x18001f9cc  mov     [rbp+50h+var_C8], rax
0x18001f9d0  mov     r15, [rbp+50h+arg_28]
0x18001f9d7  lea     rax, WPP_GLOBAL_Control
0x18001f9de  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f9e5  cmp     rcx, rax
0x18001f9e8  jz      short loc_18001FA09
0x18001f9ea  test    byte ptr [rcx+1Ch], 4
0x18001f9ee  jz      short loc_18001FA09
0x18001f9f0  mov     edx, 15h
0x18001f9f5  mov     r9, [r9+8]
0x18001f9f9  lea     r8, WPP_f8de5c7b8ba83db1c680dda639d42263_Traceguids
0x18001fa00  mov     rcx, [rcx+10h]
0x18001fa04  call    WPP_SF_P
0x18001fa09  xor     eax, eax
0x18001fa0b  mov     [rsp+150h+var_F0], eax
0x18001fa0f  mov     [rsp+150h+var_E0], rax
0x18001fa14  mov     [rsp+150h+var_E8], rax
0x18001fa19  mov     [rsp+150h+var_D8], rax
0x18001fa1e  lea     rdx, [rbp+50h+var_D0]
0x18001fa22  mov     rcx, r12
0x18001fa25  call    ?CreateProxy@ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@XZ; EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(void)
0x18001fa2a  nop
0x18001fa2b  mov     rsi, [rax]
0x18001fa2e  mov     rax, [rsi]
0x18001fa31  mov     rdi, [rax+48h]
0x18001fa35  mov     rbx, [r14]
0x18001fa38  mov     rcx, [r14+8]
0x18001fa3c  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001fa41  movups  xmm0, xmmword ptr [r12+10h]
0x18001fa47  movdqu  [rbp+50h+var_C0], xmm0
0x18001fa4c  lea     rcx, [rsp+150h+var_D8]
0x18001fa51  mov     [rsp+150h+var_100], rcx
0x18001fa56  lea     rcx, [rsp+150h+var_E0]
0x18001fa5b  mov     [rsp+150h+var_108], rcx
0x18001fa60  lea     rcx, [rsp+150h+var_E8]
0x18001fa65  mov     [rsp+150h+var_110], rcx
0x18001fa6a  lea     rcx, [rsp+150h+var_F0]
0x18001fa6f  mov     [rsp+150h+var_118], rcx
0x18001fa74  mov     rcx, [rbp+50h+var_C8]
0x18001fa78  mov     [rsp+150h+var_120], rcx
0x18001fa7d  mov     [rsp+150h+var_128], rbx
0x18001fa82  mov     [rsp+150h+var_130], eax
0x18001fa86  mov     r9d, [rsp+150h+var_EC]
0x18001fa8b  lea     r8, [rbp+50h+var_C0]
0x18001fa8f  mov     edx, r13d
0x18001fa92  mov     rcx, rsi
0x18001fa95  mov     rax, rdi
0x18001fa98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa9d  mov     ebx, eax
0x18001fa9f  lea     rcx, [rbp+50h+var_D0]
0x18001faa3  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001faa8  test    ebx, ebx
0x18001faaa  jns     short loc_18001FAC8
0x18001faac  mov     r8d, ebx; unsigned int
0x18001faaf  mov     rdx, [rsp+150h+var_E0]; struct _EAP_ERROR *
0x18001fab4  lea     rcx, [rbp+50h+var_B0]; this
0x18001fab8  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001fabd  nop
0x18001fabe  lea     rcx, [rbp+50h+var_B0]; struct EapHost::EapError *
0x18001fac2  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001fac8  mov     [rbp+50h+var_D0], 0
0x18001fad0  mov     edx, [rsp+150h+var_F0]
0x18001fad4  mov     r8, [rsp+150h+var_E8]
0x18001fad9  mov     rcx, r15
0x18001fadc  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001fae1  nop
0x18001fae2  lea     rcx, [rsp+150h+var_D8]
0x18001fae7  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18001faec  nop
0x18001faed  lea     rcx, [rsp+150h+var_E8]
0x18001faf2  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18001faf7  nop
0x18001faf8  lea     rcx, [rsp+150h+var_E0]
0x18001fafd  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001fb02  mov     rcx, [rbp+50h+var_50]
0x18001fb06  xor     rcx, rsp; StackCookie
0x18001fb09  call    __security_check_cookie
0x18001fb0e  add     rsp, 118h
0x18001fb15  pop     r15
0x18001fb17  pop     r14
0x18001fb19  pop     r13
0x18001fb1b  pop     r12
0x18001fb1d  pop     rdi
0x18001fb1e  pop     rsi
0x18001fb1f  pop     rbx
0x18001fb20  pop     rbp
0x18001fb21  retn
```
