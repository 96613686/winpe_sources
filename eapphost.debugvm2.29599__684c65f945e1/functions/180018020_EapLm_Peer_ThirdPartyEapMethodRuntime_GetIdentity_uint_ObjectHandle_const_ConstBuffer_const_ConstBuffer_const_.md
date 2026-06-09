# EapLm::Peer::ThirdPartyEapMethodRuntime::GetIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)

- ea: `0x180018020`
- end: `0x1800182bc`
- name: `?GetIdentity@ThirdPartyEapMethodRuntime@Peer@EapLm@@UEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z`
- size: `668`
- prototype: `__int64 __usercall@<rax>(EapLm::Peer::ThirdPartyEapMethodRuntime *this@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002a90`
- `0x180004150`
- `0x1800052c0`
- `0x180005370`
- `0x1800121ec`
- `0x180014d8c`
- `0x1800178a4`
- `0x180017b78`
- `0x180017bac`
- `0x180017d28`
- `0x180018020`
- `0x180018d20`
- `0x18001d9bc`
- `0x18002fd44`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800181ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800181ea`

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
0x180018020  mov     r11, rsp
0x180018023  push    rbx
0x180018024  push    rsi
0x180018025  push    rdi
0x180018026  push    r12
0x180018028  push    r13
0x18001802a  push    r14
0x18001802c  push    r15
0x18001802e  sub     rsp, 140h
0x180018035  mov     rax, cs:__security_cookie
0x18001803c  xor     rax, rsp
0x18001803f  mov     [rsp+178h+var_48], rax
0x180018047  mov     r12, r9
0x18001804a  mov     rbx, r8
0x18001804d  mov     [rsp+178h+var_F8], edx
0x180018054  mov     r13, rcx
0x180018057  mov     rdi, [rsp+178h+arg_20]
0x18001805f  mov     rax, [rsp+178h+arg_28]
0x180018067  mov     [rsp+178h+var_C0], rax
0x18001806f  mov     rax, [rsp+178h+arg_30]
0x180018077  mov     [rsp+178h+var_C8], rax
0x18001807f  mov     rax, [rsp+178h+arg_38]
0x180018087  mov     [rsp+178h+var_B8], rax
0x18001808f  xor     esi, esi
0x180018091  mov     [r11-0E0h], rsi
0x180018098  mov     [rsp+178h+pv], rsi
0x18001809d  mov     [r11-0E8h], rsi
0x1800180a4  mov     [rsp+178h+var_108], esi
0x1800180a8  mov     [rsp+178h+var_104], esi
0x1800180ac  mov     [r11-0D8h], rsi
0x1800180b3  mov     [r11-0F0h], rsi
0x1800180ba  mov     [r11-0D0h], rsi
0x1800180c1  lea     rax, WPP_GLOBAL_Control
0x1800180c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180cf  cmp     rcx, rax
0x1800180d2  jz      short loc_180018101
0x1800180d4  test    byte ptr [rcx+1Ch], 4
0x1800180d8  jz      short loc_180018101
0x1800180da  mov     rax, [rdi+8]
0x1800180de  mov     [rsp+178h+var_148], rax
0x1800180e3  mov     rax, [r9+8]
0x1800180e7  mov     [rsp+178h+var_150], rax
0x1800180ec  mov     rax, [r8+8]
0x1800180f0  mov     [rsp+178h+var_158], rax
0x1800180f5  mov     r9d, edx
0x1800180f8  mov     rcx, [rcx+10h]
0x1800180fc  call    WPP_SF_dqPP
0x180018101  lea     r8, [rsp+178h+var_D0]; struct IClassFactory **
0x180018109  lea     rdx, [rsp+178h+var_F0]; struct IThirdPartyEapDispatcherPeerRuntime **
0x180018111  mov     rcx, r13; this
0x180018114  call    ?CreateProxy@ThirdPartyEapMethodRuntime@Peer@EapLm@@QEAAXAEAPEAUIThirdPartyEapDispatcherPeerRuntime@@AEAPEAUIClassFactory@@@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::CreateProxy(IThirdPartyEapDispatcherPeerRuntime * &,IClassFactory * &)
0x180018119  mov     r15, [rsp+178h+var_F0]
0x180018121  cmp     [rbx+8], rsi
0x180018125  jz      short loc_18001813D
0x180018127  lea     r9, [rsp+178h+var_D8]; void **
0x18001812f  mov     r8, rbx; struct ObjectHandle *
0x180018132  mov     rdx, r15; struct IThirdPartyEapDispatcherPeerRuntime *
0x180018135  mov     rcx, r13; this
0x180018138  call    ?DupImpersonationHanle@ThirdPartyEapMethodRuntime@Peer@EapLm@@AEAAXPEAUIThirdPartyEapDispatcherPeerRuntime@@AEBVObjectHandle@@AEAPEAX@Z; EapLm::Peer::ThirdPartyEapMethodRuntime::DupImpersonationHanle(IThirdPartyEapDispatcherPeerRuntime *,ObjectHandle const &,void * &)
0x18001813d  mov     rax, [r15]
0x180018140  mov     r14, [rax+20h]
0x180018144  mov     rsi, [rdi]
0x180018147  mov     rcx, [rdi+8]
0x18001814b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180018150  mov     ebx, eax
0x180018152  mov     rdi, [r12]
0x180018156  mov     rcx, [r12+8]
0x18001815b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180018160  lea     rdx, [r13+10h]
0x180018164  lea     rcx, [rsp+178h+var_E0]
0x18001816c  mov     [rsp+178h+var_118], rcx
0x180018171  lea     rcx, [rsp+178h+pv]
0x180018176  mov     [rsp+178h+var_120], rcx
0x18001817b  lea     rcx, [rsp+178h+var_E8]
0x180018183  mov     [rsp+178h+var_128], rcx
0x180018188  lea     rcx, [rsp+178h+var_108]
0x18001818d  mov     [rsp+178h+var_130], rcx
0x180018192  lea     rcx, [rsp+178h+var_104]
0x180018197  mov     [rsp+178h+var_138], rcx
0x18001819c  mov     [rsp+178h+var_140], rsi
0x1800181a1  mov     dword ptr [rsp+178h+var_148], ebx
0x1800181a5  mov     [rsp+178h+var_150], rdi
0x1800181aa  mov     dword ptr [rsp+178h+var_158], eax
0x1800181ae  mov     r9, [rsp+178h+var_D8]
0x1800181b6  mov     r8d, [rsp+178h+var_F8]
0x1800181be  mov     rcx, r15
0x1800181c1  mov     rax, r14
0x1800181c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181c9  mov     ebx, eax
0x1800181cb  test    eax, eax
0x1800181cd  js      loc_180018283
0x1800181d3  mov     rdx, [rsp+178h+pv]
0x1800181d8  mov     rcx, [rsp+178h+var_C8]
0x1800181e0  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x1800181e5  mov     rcx, [rsp+178h+pv]; pv
0x1800181ea  call    cs:__imp_CoTaskMemFree
0x1800181f0  nop
0x1800181f1  mov     edx, [rsp+178h+var_108]
0x1800181f5  mov     r8, [rsp+178h+var_E8]
0x1800181fd  mov     rcx, [rsp+178h+var_C0]
0x180018205  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001820a  cmp     [rsp+178h+var_104], 0
0x18001820f  setnz   al
0x180018212  mov     rcx, [rsp+178h+var_B8]
0x18001821a  mov     [rcx], al
0x18001821c  mov     rcx, [rsp+178h+var_D0]
0x180018224  test    rcx, rcx
0x180018227  jz      short loc_180018245
0x180018229  mov     rax, [rcx]
0x18001822c  mov     rax, [rax+10h]
0x180018230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018235  mov     rax, [r15]
0x180018238  mov     rcx, r15
0x18001823b  mov     rax, [rax+10h]
0x18001823f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018244  nop
0x180018245  lea     rcx, [rsp+178h+var_E8]
0x18001824d  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x180018252  nop
0x180018253  lea     rcx, [rsp+178h+var_E0]
0x18001825b  call    ?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ; com_ptr<_EAP_ERROR>::Clear(void)
0x180018260  mov     rcx, [rsp+178h+var_48]
0x180018268  xor     rcx, rsp; StackCookie
0x18001826b  call    __security_check_cookie
0x180018270  add     rsp, 140h
0x180018277  pop     r15
0x180018279  pop     r14
0x18001827b  pop     r13
0x18001827d  pop     r12
0x18001827f  pop     rdi
0x180018280  pop     rsi
0x180018281  pop     rbx
0x180018282  retn
0x180018283  mov     rcx, [rsp+178h+pv]; pv
0x180018288  call    ??$Free@VTaskAllocator@@@@YAXPEA_W@Z; Free<TaskAllocator>(wchar_t *)
0x18001828d  lea     rcx, [rsp+178h+var_E0]
0x180018295  call    ??C?$unique_ptr@VEapError@EapHost@@U?$default_delete@VEapError@EapHost@@@std@@@std@@QEBAPEAVEapError@EapHost@@XZ; std::unique_ptr<EapHost::EapError>::operator->(void)
0x18001829a  mov     rdx, rax; struct _EAP_ERROR *
0x18001829d  mov     r8d, ebx; unsigned int
0x1800182a0  lea     rcx, [rsp+178h+var_A8]; this
0x1800182a8  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x1800182ad  nop
0x1800182ae  lea     rcx, [rsp+178h+var_A8]; struct EapHost::EapError *
0x1800182b6  call    ?Throw@EapException@EapHost@@SAXAEBVEapError@2@@Z; EapHost::EapException::Throw(EapHost::EapError const &)
```
