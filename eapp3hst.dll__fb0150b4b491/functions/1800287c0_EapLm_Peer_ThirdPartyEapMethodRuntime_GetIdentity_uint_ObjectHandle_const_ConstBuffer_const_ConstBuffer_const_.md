# EapLm::Peer::ThirdPartyEapMethodRuntime::GetIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)

- ea: `0x1800287c0`
- end: `0x180028a51`
- name: `?GetIdentity@ThirdPartyEapMethodRuntime@Peer@EapLm@@UEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z`
- size: `657`
- prototype: `void __fastcall(EapLm::Peer::ThirdPartyEapMethodRuntime *this, __int64, const struct ObjectHandle *, __int64 *, __int64 *, __int64, void **, bool *)`
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180005894`
- `0x180006c0c`
- `0x1800126f8`
- `0x180013d10`
- `0x180013dbc`
- `0x1800151ec`
- `0x1800177bc`
- `0x180028310`
- `0x18002848c`
- `0x1800287c0`
- `0x180029464`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800289b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800289b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapLm::Peer::ThirdPartyEapMethodRuntime::GetIdentity(
        EapLm::Peer::ThirdPartyEapMethodRuntime *this,
        __int64 a2,
        const struct ObjectHandle *a3,
        __int64 *a4,
        __int64 *a5,
        __int64 a6,
        void **a7,
        bool *a8)
{
  struct IThirdPartyEapDispatcherPeerRuntime *v11; // r15
  __int64 (__fastcall *v12)(struct IThirdPartyEapDispatcherPeerRuntime *, char *, _QWORD, void *, int, __int64, int, __int64, int *, unsigned int *, void **, LPVOID *, struct _EAP_ERROR **); // r14
  __int64 v13; // rsi
  int v14; // ebx
  __int64 v15; // rdi
  int v16; // eax
  signed int v17; // ebx
  unsigned int v18; // [rsp+70h] [rbp-108h] BYREF
  int v19; // [rsp+74h] [rbp-104h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-100h] BYREF
  unsigned int v21; // [rsp+80h] [rbp-F8h]
  struct IThirdPartyEapDispatcherPeerRuntime *v22; // [rsp+88h] [rbp-F0h] BYREF
  void *v23; // [rsp+90h] [rbp-E8h] BYREF
  struct _EAP_ERROR *v24; // [rsp+98h] [rbp-E0h] BYREF
  void *v25; // [rsp+A0h] [rbp-D8h] BYREF
  struct IClassFactory *v26; // [rsp+A8h] [rbp-D0h] BYREF
  void **v27; // [rsp+B0h] [rbp-C8h]
  __int64 v28; // [rsp+B8h] [rbp-C0h]
  bool *v29; // [rsp+C0h] [rbp-B8h]
  _BYTE v30[96]; // [rsp+D0h] [rbp-A8h] BYREF

  v21 = a2;
  v28 = a6;
  v27 = a7;
  v29 = a8;
  v24 = 0;
  pv = 0;
  v23 = 0;
  v18 = 0;
  v19 = 0;
  v25 = 0;
  v22 = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dqPP(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (unsigned int)a2, *((_QWORD *)a3 + 1), a4[1], a5[1]);
  EapLm::Peer::ThirdPartyEapMethodRuntime::CreateProxy(this, &v22, (LPVOID *)&v26);
  v11 = v22;
  if ( *((_QWORD *)a3 + 1) )
    EapLm::Peer::ThirdPartyEapMethodRuntime::DupImpersonationHanle(this, v22, a3, &v25);
  v12 = *(__int64 (__fastcall **)(struct IThirdPartyEapDispatcherPeerRuntime *, char *, _QWORD, void *, int, __int64, int, __int64, int *, unsigned int *, void **, LPVOID *, struct _EAP_ERROR **))(*(_QWORD *)v11 + 32LL);
  v13 = *a5;
  v14 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a5[1]);
  v15 = *a4;
  v16 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  v17 = v12(v11, (char *)this + 16, v21, v25, v16, v15, v14, v13, &v19, &v18, &v23, &pv, &v24);
  if ( v17 < 0 )
  {
    CoTaskMemFree(pv);
    EapHost::EapError::EapError((EapHost::EapError *)v30, v24, v17);
    EapHost::EapException::Throw((const struct EapHost::EapError *)v30);
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    BasicSimpleString<wchar_t>::Assign(v27, (__int64)pv);
    CoTaskMemFree(pv);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      CoTaskMemFree(pv);
      throw;
    }
  }
  TempBuffer<0>::Assign(v28, v18, v23);
  *v29 = v19 != 0;
  if ( v26 )
  {
    ((void (__fastcall *)(struct IClassFactory *))v26->lpVtbl->Release)(v26);
    (*(void (__fastcall **)(struct IThirdPartyEapDispatcherPeerRuntime *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  com_ptr<unsigned char>::Clear(&v23);
  com_ptr<_EAP_ERROR>::Clear((LPVOID *)&v24);
}

```

## disassembly

```asm
0x1800287c0  mov     r11, rsp
0x1800287c3  push    rbx
0x1800287c4  push    rsi
0x1800287c5  push    rdi
0x1800287c6  push    r12
0x1800287c8  push    r13
0x1800287ca  push    r14
0x1800287cc  push    r15
0x1800287ce  sub     rsp, 140h
0x1800287d5  mov     rax, cs:__security_cookie
0x1800287dc  xor     rax, rsp
0x1800287df  mov     [rsp+178h+var_48], rax
0x1800287e7  mov     r12, r9
0x1800287ea  mov     rbx, r8
0x1800287ed  mov     [rsp+178h+var_F8], edx
0x1800287f4  mov     r13, rcx
0x1800287f7  mov     rdi, [rsp+178h+arg_20]
0x1800287ff  mov     rax, [rsp+178h+arg_28]
0x180028807  mov     [rsp+178h+var_C0], rax
0x18002880f  mov     rax, [rsp+178h+arg_30]
0x180028817  mov     [rsp+178h+var_C8], rax
0x18002881f  mov     rax, [rsp+178h+arg_38]
0x180028827  mov     [rsp+178h+var_B8], rax
0x18002882f  xor     esi, esi
0x180028831  mov     [r11-0E0h], rsi
0x180028838  mov     [rsp+178h+pv], rsi
0x18002883d  mov     [r11-0E8h], rsi
0x180028844  mov     [rsp+178h+var_108], esi
0x180028848  mov     [rsp+178h+var_104], esi
0x18002884c  mov     [r11-0D8h], rsi
0x180028853  mov     [r11-0F0h], rsi
0x18002885a  mov     [r11-0D0h], rsi
0x180028861  lea     rax, WPP_GLOBAL_Control
0x180028868  mov     rcx, cs:WPP_GLOBAL_Control
0x18002886f  cmp     rcx, rax
0x180028872  jz      short loc_1800288A1
0x180028874  test    byte ptr [rcx+1Ch], 4
0x180028878  jz      short loc_1800288A1
0x18002887a  mov     rax, [rdi+8]
0x18002887e  mov     [rsp+178h+var_148], rax
0x180028883  mov     rax, [r9+8]
0x180028887  mov     [rsp+178h+var_150], rax
0x18002888c  mov     rax, [r8+8]
0x180028890  mov     [rsp+178h+var_158], rax
0x180028895  mov     r9d, edx
0x180028898  mov     rcx, [rcx+10h]
0x18002889c  call    WPP_SF_dqPP
0x1800288a1  lea     r8, [rsp+178h+var_D0]; struct IClassFactory **
0x1800288a9  lea     rdx, [rsp+178h+var_F0]; struct IThirdPartyEapDispatcherPeerRuntime **
0x1800288b1  mov     rcx, r13; this
0x1800288b4  call    ?CreateProxy@ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAAXAEAPEAUIThirdPartyEapDispatcherPeerRuntime@@AEAPEAUIClassFactory@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::CreateProxy(IThirdPartyEapDispatcherPeerRuntime * &,IClassFactory * &)
0x1800288b9  mov     r15, [rsp+178h+var_F0]
0x1800288c1  cmp     [rbx+8], rsi
0x1800288c5  jz      short loc_1800288DD
0x1800288c7  lea     r9, [rsp+178h+var_D8]; void **
0x1800288cf  mov     r8, rbx; struct ObjectHandle *
0x1800288d2  mov     rdx, r15; struct IThirdPartyEapDispatcherPeerRuntime *
0x1800288d5  mov     rcx, r13; this
0x1800288d8  call    ?DupImpersonationHanle@ThirdPartyEapMethodRuntime@Peer@EapLm@@AEAAXPEAUIThirdPartyEapDispatcherPeerRuntime@@AEBVObjectHandle@@AEAPEAX@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::DupImpersonationHanle(IThirdPartyEapDispatcherPeerRuntime *,ObjectHandle const &,void * &)
0x1800288dd  mov     rax, [r15]
0x1800288e0  mov     r14, [rax+20h]
0x1800288e4  mov     rsi, [rdi]
0x1800288e7  mov     rcx, [rdi+8]
0x1800288eb  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800288f0  mov     ebx, eax
0x1800288f2  mov     rdi, [r12]
0x1800288f6  mov     rcx, [r12+8]
0x1800288fb  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180028900  lea     rdx, [r13+10h]
0x180028904  lea     rcx, [rsp+178h+var_E0]
0x18002890c  mov     [rsp+178h+var_118], rcx
0x180028911  lea     rcx, [rsp+178h+pv]
0x180028916  mov     [rsp+178h+var_120], rcx
0x18002891b  lea     rcx, [rsp+178h+var_E8]
0x180028923  mov     [rsp+178h+var_128], rcx
0x180028928  lea     rcx, [rsp+178h+var_108]
0x18002892d  mov     [rsp+178h+var_130], rcx
0x180028932  lea     rcx, [rsp+178h+var_104]
0x180028937  mov     [rsp+178h+var_138], rcx
0x18002893c  mov     [rsp+178h+var_140], rsi
0x180028941  mov     dword ptr [rsp+178h+var_148], ebx
0x180028945  mov     [rsp+178h+var_150], rdi
0x18002894a  mov     dword ptr [rsp+178h+var_158], eax
0x18002894e  mov     r9, [rsp+178h+var_D8]
0x180028956  mov     r8d, [rsp+178h+var_F8]
0x18002895e  mov     rcx, r15
0x180028961  mov     rax, r14
0x180028964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028969  mov     ebx, eax
0x18002896b  test    eax, eax
0x18002896d  jns     short loc_1800289A1
0x18002896f  mov     rcx, [rsp+178h+pv]; pv
0x180028974  call    cs:__imp_CoTaskMemFree
0x18002897a  mov     r8d, ebx; unsigned int
0x18002897d  mov     rdx, [rsp+178h+var_E0]; struct _EAP_ERROR *
0x180028985  lea     rcx, [rsp+178h+var_A8]; this
0x18002898d  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180028992  nop
0x180028993  lea     rcx, [rsp+178h+var_A8]; struct EapHost::EapError *
0x18002899b  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
0x1800289a1  mov     rdx, [rsp+178h+pv]
0x1800289a6  mov     rcx, [rsp+178h+var_C8]
0x1800289ae  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x1800289b3  mov     rcx, [rsp+178h+pv]; pv
0x1800289b8  call    cs:__imp_CoTaskMemFree
0x1800289be  nop
0x1800289bf  mov     edx, [rsp+178h+var_108]
0x1800289c3  mov     r8, [rsp+178h+var_E8]
0x1800289cb  mov     rcx, [rsp+178h+var_C0]
0x1800289d3  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x1800289d8  cmp     [rsp+178h+var_104], 0
0x1800289dd  setnz   al
0x1800289e0  mov     rcx, [rsp+178h+var_B8]
0x1800289e8  mov     [rcx], al
0x1800289ea  mov     rcx, [rsp+178h+var_D0]
0x1800289f2  test    rcx, rcx
0x1800289f5  jz      short loc_180028A13
0x1800289f7  mov     rax, [rcx]
0x1800289fa  mov     rax, [rax+10h]
0x1800289fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a03  mov     rax, [r15]
0x180028a06  mov     rcx, r15
0x180028a09  mov     rax, [rax+10h]
0x180028a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a12  nop
0x180028a13  lea     rcx, [rsp+178h+var_E8]
0x180028a1b  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x180028a20  nop
0x180028a21  lea     rcx, [rsp+178h+var_E0]
0x180028a29  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x180028a2e  mov     rcx, [rsp+178h+var_48]
0x180028a36  xor     rcx, rsp; StackCookie
0x180028a39  call    __security_check_cookie
0x180028a3e  add     rsp, 140h
0x180028a45  pop     r15
0x180028a47  pop     r14
0x180028a49  pop     r13
0x180028a4b  pop     r12
0x180028a4d  pop     rdi
0x180028a4e  pop     rsi
0x180028a4f  pop     rbx
0x180028a50  retn
```
