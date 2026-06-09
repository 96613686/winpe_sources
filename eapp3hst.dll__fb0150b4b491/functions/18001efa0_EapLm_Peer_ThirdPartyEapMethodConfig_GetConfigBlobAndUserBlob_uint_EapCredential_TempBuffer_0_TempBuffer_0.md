# EapLm::Peer::ThirdPartyEapMethodConfig::GetConfigBlobAndUserBlob(uint,_EapCredential,TempBuffer<0> &,TempBuffer<0> &)

- ea: `0x18001efa0`
- end: `0x18001f103`
- name: `?GetConfigBlobAndUserBlob@ThirdPartyEapMethodConfig@Peer@EapLm@@UEAAXIU_EapCredential@@AEAV?$TempBuffer@$0A@@@1@Z`
- size: `355`
- prototype: `void __fastcall(__int64, unsigned int, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180006c0c`
- `0x18000d0e8`
- `0x1800126f8`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800177bc`
- `0x18001ecf8`
- `0x18001efa0`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapLm::Peer::ThirdPartyEapMethodConfig::GetConfigBlobAndUserBlob(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  LPVOID v9; // rcx
  signed int v10; // ebx
  unsigned int v11; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v12; // [rsp+54h] [rbp-ACh] BYREF
  struct _EAP_ERROR *v13; // [rsp+58h] [rbp-A8h] BYREF
  void *v14; // [rsp+60h] [rbp-A0h] BYREF
  void *v15; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v16[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v17; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v18[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-50h]
  _BYTE v20[96]; // [rsp+C0h] [rbp-40h] BYREF

  v11 = 0;
  v15 = 0;
  v12 = 0;
  v14 = 0;
  v13 = 0;
  v9 = *EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy((const struct _EAP_METHOD_TYPE *)a1, v16);
  v18[0] = *(_OWORD *)a3;
  v18[1] = *(_OWORD *)(a3 + 16);
  v19 = *(_QWORD *)(a3 + 32);
  v17 = *(_OWORD *)(a1 + 16);
  v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int128 *, _OWORD *, unsigned int *, void **, unsigned int *, void **, struct _EAP_ERROR **))(*(_QWORD *)v9 + 120LL))(
          v9,
          a2,
          &v17,
          v18,
          &v11,
          &v15,
          &v12,
          &v14,
          &v13);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)v16);
  if ( v10 < 0 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v20, v13, v10);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v20);
  }
  TempBuffer<0>::Assign(a4, v11, v15);
  TempBuffer<0>::Assign(a5, v12, v14);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)&v13);
  com_ptr<unsigned char>::Clear(&v14);
  com_ptr<unsigned char>::Clear(&v15);
}

```

## disassembly

```asm
0x18001efa0  push    rbp
0x18001efa2  push    rbx
0x18001efa3  push    rsi
0x18001efa4  push    rdi
0x18001efa5  push    r14
0x18001efa7  push    r15
0x18001efa9  lea     rbp, [rsp-38h]
0x18001efae  sub     rsp, 138h
0x18001efb5  mov     rax, cs:__security_cookie
0x18001efbc  xor     rax, rsp
0x18001efbf  mov     [rbp+60h+var_40], rax
0x18001efc3  mov     r14, r9
0x18001efc6  mov     rdi, r8
0x18001efc9  mov     esi, edx
0x18001efcb  mov     rbx, rcx
0x18001efce  mov     r15, [rbp+60h+arg_20]
0x18001efd5  mov     [rsp+160h+var_110], 0
0x18001efdd  mov     [rsp+160h+var_F8], 0
0x18001efe6  mov     [rsp+160h+var_10C], 0
0x18001efee  mov     [rsp+160h+var_100], 0
0x18001eff7  mov     [rsp+160h+var_108], 0
0x18001f000  lea     rdx, [rsp+160h+var_F0]
0x18001f005  call    ?CreateProxy@ThirdPartyEapMethodConfig@Peer@EapLm@@QEAA?AV?$CComPtr@UIThirdPartyEapDispatcherPeerConfig@@@ATL@@XZ; EapLm::Peer::ThirdPartyEapMethodConfig::CreateProxy(void)
0x18001f00a  nop
0x18001f00b  mov     rcx, [rax]
0x18001f00e  movups  xmm0, xmmword ptr [rdi]
0x18001f011  movaps  [rbp+60h+var_D0], xmm0
0x18001f015  movups  xmm1, xmmword ptr [rdi+10h]
0x18001f019  movaps  [rbp+60h+var_C0], xmm1
0x18001f01d  movsd   xmm0, qword ptr [rdi+20h]
0x18001f022  movsd   [rbp+60h+var_B0], xmm0
0x18001f027  movups  xmm1, xmmword ptr [rbx+10h]
0x18001f02b  movdqu  [rbp+60h+var_E0], xmm1
0x18001f030  mov     rax, [rcx]
0x18001f033  lea     rdx, [rsp+160h+var_108]
0x18001f038  mov     [rsp+160h+var_120], rdx
0x18001f03d  lea     rdx, [rsp+160h+var_100]
0x18001f042  mov     [rsp+160h+var_128], rdx
0x18001f047  lea     rdx, [rsp+160h+var_10C]
0x18001f04c  mov     [rsp+160h+var_130], rdx
0x18001f051  lea     rdx, [rsp+160h+var_F8]
0x18001f056  mov     [rsp+160h+var_138], rdx
0x18001f05b  lea     rdx, [rsp+160h+var_110]
0x18001f060  mov     [rsp+160h+var_140], rdx
0x18001f065  lea     r9, [rbp+60h+var_D0]
0x18001f069  lea     r8, [rbp+60h+var_E0]
0x18001f06d  mov     edx, esi
0x18001f06f  mov     rax, [rax+78h]
0x18001f073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f078  mov     ebx, eax
0x18001f07a  lea     rcx, [rsp+160h+var_F0]
0x18001f07f  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18001f084  test    ebx, ebx
0x18001f086  jns     short loc_18001F0A4
0x18001f088  mov     r8d, ebx; unsigned int
0x18001f08b  mov     rdx, [rsp+160h+var_108]; struct _EAP_ERROR *
0x18001f090  lea     rcx, [rbp+60h+var_A0]; this
0x18001f094  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001f099  nop
0x18001f09a  lea     rcx, [rbp+60h+var_A0]; struct EapHost::EapError *
0x18001f09e  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x18001f0a4  mov     edx, [rsp+160h+var_110]
0x18001f0a8  mov     r8, [rsp+160h+var_F8]
0x18001f0ad  mov     rcx, r14
0x18001f0b0  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001f0b5  mov     edx, [rsp+160h+var_10C]
0x18001f0b9  mov     r8, [rsp+160h+var_100]
0x18001f0be  mov     rcx, r15
0x18001f0c1  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001f0c6  nop
0x18001f0c7  lea     rcx, [rsp+160h+var_108]
0x18001f0cc  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x18001f0d1  nop
0x18001f0d2  lea     rcx, [rsp+160h+var_100]
0x18001f0d7  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18001f0dc  nop
0x18001f0dd  lea     rcx, [rsp+160h+var_F8]
0x18001f0e2  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18001f0e7  mov     rcx, [rbp+60h+var_40]
0x18001f0eb  xor     rcx, rsp; StackCookie
0x18001f0ee  call    __security_check_cookie
0x18001f0f3  add     rsp, 138h
0x18001f0fa  pop     r15
0x18001f0fc  pop     r14
0x18001f0fe  pop     rdi
0x18001f0ff  pop     rsi
0x18001f100  pop     rbx
0x18001f101  pop     rbp
0x18001f102  retn
```
