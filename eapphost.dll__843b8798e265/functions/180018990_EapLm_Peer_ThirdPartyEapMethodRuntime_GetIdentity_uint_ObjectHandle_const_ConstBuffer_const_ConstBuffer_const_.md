# EapLm::Peer::ThirdPartyEapMethodRuntime::GetIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)

- ea: `0x180018990`
- end: `0x180018c33`
- name: `?GetIdentity@ThirdPartyEapMethodRuntime@Peer@EapLm@@UEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z`
- size: `675`
- prototype: `__int64 __usercall@<rax>(EapLm::Peer::ThirdPartyEapMethodRuntime *this@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002af0`
- `0x1800042a0`
- `0x180005410`
- `0x1800054c4`
- `0x18001296c`
- `0x1800155c8`
- `0x1800181bc`
- `0x180018498`
- `0x1800184d4`
- `0x180018664`
- `0x180018990`
- `0x1800196cc`
- `0x18001e4ac`
- `0x180030f54`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018b5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::GetIdentity(
        EapLm::Peer::ThirdPartyEapMethodRuntime *this,
        __int64 a2,
        const struct ObjectHandle *a3,
        __int64 *a4,
        __int64 *a5,
        __int64 a6,
        __int64 a7,
        bool *a8)
{
  struct IThirdPartyEapDispatcherPeerRuntime *v11; // r15
  __int64 (__fastcall *v12)(struct IThirdPartyEapDispatcherPeerRuntime *, char *, _QWORD, void *, int, __int64, int, __int64, int *, unsigned int *, __int64 *, LPVOID *, __int64 *); // r14
  __int64 v13; // rsi
  int v14; // ebx
  __int64 v15; // rdi
  int v16; // eax
  signed int v17; // ebx
  const struct _EAP_ERROR *v19; // rdx
  unsigned int v20; // [rsp+70h] [rbp-108h] BYREF
  int v21; // [rsp+74h] [rbp-104h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-100h] BYREF
  unsigned int v23; // [rsp+80h] [rbp-F8h]
  struct IThirdPartyEapDispatcherPeerRuntime *v24; // [rsp+88h] [rbp-F0h] BYREF
  __int64 v25; // [rsp+90h] [rbp-E8h] BYREF
  __int64 v26; // [rsp+98h] [rbp-E0h] BYREF
  void *v27; // [rsp+A0h] [rbp-D8h] BYREF
  struct IClassFactory *v28; // [rsp+A8h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-C8h]
  __int64 v30; // [rsp+B8h] [rbp-C0h]
  bool *v31; // [rsp+C0h] [rbp-B8h]
  _BYTE v32[96]; // [rsp+D0h] [rbp-A8h] BYREF

  v23 = a2;
  v30 = a6;
  v29 = a7;
  v31 = a8;
  v26 = 0;
  pv = 0;
  v25 = 0;
  v20 = 0;
  v21 = 0;
  v27 = 0;
  v24 = 0;
  v28 = 0;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dqPP(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a2, *((_QWORD *)a3 + 1), a4[1], a5[1]);
  }
  EapLm::Peer::ThirdPartyEapMethodRuntime::CreateProxy(this, &v24, &v28);
  v11 = v24;
  if ( *((_QWORD *)a3 + 1) )
    EapLm::Peer::ThirdPartyEapMethodRuntime::DupImpersonationHanle(this, v24, a3, &v27);
  v12 = *(__int64 (__fastcall **)(struct IThirdPartyEapDispatcherPeerRuntime *, char *, _QWORD, void *, int, __int64, int, __int64, int *, unsigned int *, __int64 *, LPVOID *, __int64 *))(*(_QWORD *)v11 + 32LL);
  v13 = *a5;
  v14 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a5[1]);
  v15 = *a4;
  v16 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  v17 = v12(v11, (char *)this + 16, v23, v27, v16, v15, v14, v13, &v21, &v20, &v25, &pv, &v26);
  if ( v17 < 0 )
  {
    Free<TaskAllocator>(pv);
    v19 = (const struct _EAP_ERROR *)std::unique_ptr<EapHost::EapError>::operator->(&v26);
    EapHost::EapError::EapError((EapHost::EapError *)v32, v19, v17);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v32);
  }
  try
  {
    BasicSimpleString<wchar_t>::Assign(v29, pv);
    CoTaskMemFree(pv);
  }
  catch ( std::bad_alloc )
  {
    Free<TaskAllocator>(pv);
    throw;
  }
  TempBuffer<0>::Assign(v30, v20);
  *v31 = v21 != 0;
  if ( v28 )
  {
    ((void (__fastcall *)(struct IClassFactory *))v28->lpVtbl->Release)(v28);
    (*(void (__fastcall **)(struct IThirdPartyEapDispatcherPeerRuntime *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  com_ptr<unsigned char>::Clear(&v25);
  return com_ptr<_EAP_ERROR>::Clear(&v26);
}

```

## disassembly

```asm
0x180018990  mov     r11, rsp
0x180018993  push    rbx
0x180018994  push    rsi
0x180018995  push    rdi
0x180018996  push    r12
0x180018998  push    r13
0x18001899a  push    r14
0x18001899c  push    r15
0x18001899e  sub     rsp, 140h
0x1800189a5  mov     rax, cs:__security_cookie
0x1800189ac  xor     rax, rsp
0x1800189af  mov     [rsp+178h+var_48], rax
0x1800189b7  mov     r12, r9
0x1800189ba  mov     rbx, r8
0x1800189bd  mov     [rsp+178h+var_F8], edx
0x1800189c4  mov     r13, rcx
0x1800189c7  mov     rdi, [rsp+178h+arg_20]
0x1800189cf  mov     rax, [rsp+178h+arg_28]
0x1800189d7  mov     [rsp+178h+var_C0], rax
0x1800189df  mov     rax, [rsp+178h+arg_30]
0x1800189e7  mov     [rsp+178h+var_C8], rax
0x1800189ef  mov     rax, [rsp+178h+arg_38]
0x1800189f7  mov     [rsp+178h+var_B8], rax
0x1800189ff  xor     esi, esi
0x180018a01  mov     [r11-0E0h], rsi
0x180018a08  mov     [rsp+178h+pv], rsi
0x180018a0d  mov     [r11-0E8h], rsi
0x180018a14  mov     [rsp+178h+var_108], esi
0x180018a18  mov     [rsp+178h+var_104], esi
0x180018a1c  mov     [r11-0D8h], rsi
0x180018a23  mov     [r11-0F0h], rsi
0x180018a2a  mov     [r11-0D0h], rsi
0x180018a31  lea     rax, WPP_GLOBAL_Control
0x180018a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a3f  cmp     rcx, rax
0x180018a42  jz      short loc_180018A71
0x180018a44  test    byte ptr [rcx+1Ch], 4
0x180018a48  jz      short loc_180018A71
0x180018a4a  mov     rax, [rdi+8]
0x180018a4e  mov     [rsp+178h+var_148], rax
0x180018a53  mov     rax, [r9+8]
0x180018a57  mov     [rsp+178h+var_150], rax
0x180018a5c  mov     rax, [r8+8]
0x180018a60  mov     [rsp+178h+var_158], rax
0x180018a65  mov     r9d, edx
0x180018a68  mov     rcx, [rcx+10h]
0x180018a6c  call    WPP_SF_dqPP
0x180018a71  lea     r8, [rsp+178h+var_D0]; struct IClassFactory **
0x180018a79  lea     rdx, [rsp+178h+var_F0]; struct IThirdPartyEapDispatcherPeerRuntime **
0x180018a81  mov     rcx, r13; this
0x180018a84  call    ?CreateProxy@ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAAXAEAPEAUIThirdPartyEapDispatcherPeerRuntime@@AEAPEAUIClassFactory@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::CreateProxy(IThirdPartyEapDispatcherPeerRuntime * &,IClassFactory * &)
0x180018a89  mov     r15, [rsp+178h+var_F0]
0x180018a91  cmp     [rbx+8], rsi
0x180018a95  jz      short loc_180018AAD
0x180018a97  lea     r9, [rsp+178h+var_D8]; void **
0x180018a9f  mov     r8, rbx; struct ObjectHandle *
0x180018aa2  mov     rdx, r15; struct IThirdPartyEapDispatcherPeerRuntime *
0x180018aa5  mov     rcx, r13; this
0x180018aa8  call    ?DupImpersonationHanle@ThirdPartyEapMethodRuntime@Peer@EapLm@@AEAAXPEAUIThirdPartyEapDispatcherPeerRuntime@@AEBVObjectHandle@@AEAPEAX@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::DupImpersonationHanle(IThirdPartyEapDispatcherPeerRuntime *,ObjectHandle const &,void * &)
0x180018aad  mov     rax, [r15]
0x180018ab0  mov     r14, [rax+20h]
0x180018ab4  mov     rsi, [rdi]
0x180018ab7  mov     rcx, [rdi+8]
0x180018abb  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180018ac0  mov     ebx, eax
0x180018ac2  mov     rdi, [r12]
0x180018ac6  mov     rcx, [r12+8]
0x180018acb  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180018ad0  lea     rdx, [r13+10h]
0x180018ad4  lea     rcx, [rsp+178h+var_E0]
0x180018adc  mov     [rsp+178h+var_118], rcx
0x180018ae1  lea     rcx, [rsp+178h+pv]
0x180018ae6  mov     [rsp+178h+var_120], rcx
0x180018aeb  lea     rcx, [rsp+178h+var_E8]
0x180018af3  mov     [rsp+178h+var_128], rcx
0x180018af8  lea     rcx, [rsp+178h+var_108]
0x180018afd  mov     [rsp+178h+var_130], rcx
0x180018b02  lea     rcx, [rsp+178h+var_104]
0x180018b07  mov     [rsp+178h+var_138], rcx
0x180018b0c  mov     [rsp+178h+var_140], rsi
0x180018b11  mov     dword ptr [rsp+178h+var_148], ebx
0x180018b15  mov     [rsp+178h+var_150], rdi
0x180018b1a  mov     dword ptr [rsp+178h+var_158], eax
0x180018b1e  mov     r9, [rsp+178h+var_D8]
0x180018b26  mov     r8d, [rsp+178h+var_F8]
0x180018b2e  mov     rcx, r15
0x180018b31  mov     rax, r14
0x180018b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b39  mov     ebx, eax
0x180018b3b  test    eax, eax
0x180018b3d  js      loc_180018BFA
0x180018b43  mov     rdx, [rsp+178h+pv]
0x180018b48  mov     rcx, [rsp+178h+var_C8]
0x180018b50  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180018b55  mov     rcx, [rsp+178h+pv]; pv
0x180018b5a  call    cs:__imp_CoTaskMemFree
0x180018b61  nop     dword ptr [rax+rax+00h]
0x180018b66  nop
0x180018b67  mov     edx, [rsp+178h+var_108]
0x180018b6b  mov     r8, [rsp+178h+var_E8]
0x180018b73  mov     rcx, [rsp+178h+var_C0]
0x180018b7b  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180018b80  cmp     [rsp+178h+var_104], 0
0x180018b85  setnz   al
0x180018b88  mov     rcx, [rsp+178h+var_B8]
0x180018b90  mov     [rcx], al
0x180018b92  mov     rcx, [rsp+178h+var_D0]
0x180018b9a  test    rcx, rcx
0x180018b9d  jz      short loc_180018BBB
0x180018b9f  mov     rax, [rcx]
0x180018ba2  mov     rax, [rax+10h]
0x180018ba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bab  mov     rax, [r15]
0x180018bae  mov     rcx, r15
0x180018bb1  mov     rax, [rax+10h]
0x180018bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bba  nop
0x180018bbb  lea     rcx, [rsp+178h+var_E8]
0x180018bc3  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x180018bc8  nop
0x180018bc9  lea     rcx, [rsp+178h+var_E0]
0x180018bd1  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x180018bd6  mov     rcx, [rsp+178h+var_48]
0x180018bde  xor     rcx, rsp; StackCookie
0x180018be1  call    __security_check_cookie
0x180018be6  add     rsp, 140h
0x180018bed  pop     r15
0x180018bef  pop     r14
0x180018bf1  pop     r13
0x180018bf3  pop     r12
0x180018bf5  pop     rdi
0x180018bf6  pop     rsi
0x180018bf7  pop     rbx
0x180018bf8  retn
0x180018bfa  mov     rcx, [rsp+178h+pv]; pv
0x180018bff  call    ??$Free@VTaskAllocator@@@@YAXPEA_W@Z; Free<TaskAllocator>(wchar_t *)
0x180018c04  lea     rcx, [rsp+178h+var_E0]
0x180018c0c  call    ??C?$unique_ptr@VEapError@EapHost@@U?$default_delete@VEapError@EapHost@@@std@@@std@@QEBAPEAVEapError@EapHost@@XZ; std::unique_ptr<EapHost::EapError>::operator->(void)
0x180018c11  mov     rdx, rax; struct _EAP_ERROR *
0x180018c14  mov     r8d, ebx; unsigned int
0x180018c17  lea     rcx, [rsp+178h+var_A8]; this
0x180018c1f  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180018c24  nop
0x180018c25  lea     rcx, [rsp+178h+var_A8]; struct EapHost::EapError *
0x180018c2d  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
```
