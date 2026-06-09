# EapLm::Peer::EapMethodRuntime::GetIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)

- ea: `0x180026310`
- end: `0x180026652`
- name: `?GetIdentity@EapMethodRuntime@Peer@EapLm@@UEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z`
- size: `834`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64 *, __int64, void **, bool *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x1800126f8`
- `0x180013d10`
- `0x1800154dc`
- `0x180016400`
- `0x1800165a4`
- `0x1800177bc`
- `0x18001b154`
- `0x180026310`
- `0x1800296fc`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180026394`
- `ntdll!EtwEventEnabled` at `0x18002659f`
- `ntdll!EtwEventEnabled` at `0x180026394`
- `ntdll!EtwEventEnabled` at `0x18002659f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_UNKNOWN **__fastcall EapLm::Peer::EapMethodRuntime::GetIdentity(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        __int64 a6,
        void **a7,
        bool *a8)
{
  __int64 v11; // rdx
  __int64 v12; // r8
  _QWORD *v13; // rcx
  __int64 (__fastcall *v14)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64, int *, unsigned int *, const void **, __int64 *, struct _EAP_ERROR **); // r15
  __int64 v15; // rsi
  __int64 v16; // r14
  unsigned int v17; // ebx
  __int64 v18; // rdi
  unsigned int v19; // eax
  unsigned int v20; // eax
  const wchar_t *v21; // rdx
  __int64 *v22; // rbx
  const wchar_t *v23; // r9
  _UNKNOWN **result; // rax
  unsigned int v25; // [rsp+60h] [rbp-A0h] BYREF
  int v26; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v27; // [rsp+68h] [rbp-98h]
  struct _EAP_ERROR *v28; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h] BYREF
  const void *v30; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+88h] [rbp-78h]
  __int64 *v32; // [rsp+90h] [rbp-70h]
  __int64 *v33; // [rsp+98h] [rbp-68h]
  __int64 v34; // [rsp+A0h] [rbp-60h]
  bool *v35; // [rsp+A8h] [rbp-58h]
  char v36[96]; // [rsp+B0h] [rbp-50h] BYREF
  char v37[2048]; // [rsp+110h] [rbp+10h] BYREF

  v33 = (__int64 *)a4;
  v31 = a3;
  v27 = a2;
  v32 = a5;
  v34 = a6;
  v35 = a8;
  BasicSimpleString<wchar_t>::Assign(a7, 0);
  *a8 = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v37, 0x800u, "EapPeerGetIdentity Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v37);
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids, a2);
    v13 = WPP_GLOBAL_Control;
  }
  if ( *(_BYTE *)(a1 + 137) )
  {
    EapLm::Peer::BaseEapMethodRuntime::GetGenericIdentity((__int64)v13, v11, v12, a4, (__int64)a5, a6, a7, a8);
  }
  else
  {
    v29 = 0;
    v28 = 0;
    v26 = 0;
    v30 = 0;
    v25 = 0;
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
      WPP_SF_(v13[2], 18, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
    v14 = *(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64, int *, unsigned int *, const void **, __int64 *, struct _EAP_ERROR **))(a1 + 328);
    v15 = *(_QWORD *)(v31 + 8);
    v16 = *v32;
    v17 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v32[1]);
    v18 = *v33;
    v19 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v33[1]);
    v20 = v14(v27, v19, v18, v17, v16, v15, &v26, &v25, &v30, &v29, &v28);
    if ( v20 )
    {
      EapHost::EapError::EapError((EapHost::EapError *)v36, v28, v20);
      (*(void (__fastcall **)(struct _EAP_ERROR *))(a1 + 424))(v28);
      EapHost::EapException::Throw(L"EapPeerGetIdentity", v21, (const struct EapHost::EapError *)v36);
    }
    if ( v29 )
    {
      BasicSimpleString<wchar_t>::Assign(a7, v29);
      (*(void (__fastcall **)(__int64))(a1 + 432))(v29);
    }
    if ( v30 && v25 )
    {
      TempBuffer<0>::Assign(v34, v25, v30);
      (*(void (__fastcall **)(const void *))(a1 + 432))(v30);
    }
    *v35 = v26 != 0;
  }
  v22 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    v23 = (const wchar_t *)&`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
    if ( *a7 )
      v23 = (const wchar_t *)*a7;
    if ( (int)StringCchPrintfA(v37, 0x800u, "EapPeerGetIdentity Exit:\n Identity(%ls)", v23) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v37);
    }
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( *a7 )
      v22 = (__int64 *)*a7;
    return (_UNKNOWN **)WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          19,
                          WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids,
                          v22);
  }
  return result;
}

```

## disassembly

```asm
0x180026310  push    rbp
0x180026312  push    rbx
0x180026313  push    rsi
0x180026314  push    rdi
0x180026315  push    r12
0x180026317  push    r13
0x180026319  push    r14
0x18002631b  push    r15
0x18002631d  lea     rbp, [rsp-828h]
0x180026325  sub     rsp, 928h
0x18002632c  mov     rax, cs:__security_cookie
0x180026333  xor     rax, rsp
0x180026336  mov     [rbp+860h+var_50], rax
0x18002633d  mov     r14, r9
0x180026340  mov     [rbp+860h+var_8C8], r9
0x180026344  mov     [rbp+860h+var_8D8], r8
0x180026348  mov     edi, edx
0x18002634a  mov     [rsp+960h+var_8F8], edx
0x18002634e  mov     r13, rcx
0x180026351  mov     r12, [rbp+860h+arg_30]
0x180026358  mov     r15, [rbp+860h+arg_20]
0x18002635f  mov     [rbp+860h+var_8D0], r15
0x180026363  mov     rsi, [rbp+860h+arg_28]
0x18002636a  mov     [rbp+860h+var_8C0], rsi
0x18002636e  mov     rbx, [rbp+860h+arg_38]
0x180026375  mov     [rbp+860h+var_8B8], rbx
0x180026379  xor     edx, edx
0x18002637b  mov     rcx, r12
0x18002637e  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180026383  mov     byte ptr [rbx], 0
0x180026386  lea     rdx, DebugInfoEvent
0x18002638d  mov     rcx, cs:eaphost_Context
0x180026394  call    cs:__imp_EtwEventEnabled
0x18002639a  test    al, al
0x18002639c  jz      short loc_1800263DA
0x18002639e  mov     r9d, edi
0x1800263a1  lea     r8, aEappeergetiden_4; "EapPeerGetIdentity Entry:\n flags(%d)"
0x1800263a8  mov     edx, 800h; unsigned __int64
0x1800263ad  lea     rcx, [rbp+860h+var_850]; char *
0x1800263b1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800263b6  test    eax, eax
0x1800263b8  js      short loc_1800263DA
0x1800263ba  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800263c1  jge     short loc_1800263DA
0x1800263c3  lea     r8, [rbp+860h+var_850]
0x1800263c7  lea     rdx, DebugInfoEvent
0x1800263ce  lea     rcx, eaphost_Context
0x1800263d5  call    McTemplateU0s_EtwEventWriteTransfer
0x1800263da  lea     rax, WPP_GLOBAL_Control
0x1800263e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263e8  cmp     rcx, rax
0x1800263eb  jz      short loc_180026419
0x1800263ed  test    byte ptr [rcx+1Ch], 4
0x1800263f1  jz      short loc_180026419
0x1800263f3  mov     edx, 11h
0x1800263f8  mov     r9d, edi
0x1800263fb  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180026402  mov     rcx, [rcx+10h]
0x180026406  call    WPP_SF_d
0x18002640b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026412  lea     rax, WPP_GLOBAL_Control
0x180026419  xor     edi, edi
0x18002641b  cmp     [r13+89h], dil
0x180026422  jz      short loc_180026445
0x180026424  mov     [rsp+960h+var_928], rbx
0x180026429  mov     [rsp+960h+var_930], r12
0x18002642e  mov     [rsp+960h+var_938], rsi
0x180026433  mov     [rsp+960h+var_940], r15
0x180026438  mov     r9, r14
0x18002643b  call    ?GetGenericIdentity@BaseEapMethodRuntime@Peer@EapLm@@IEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z; EapLm::Peer::BaseEapMethodRuntime::GetGenericIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)
0x180026440  jmp     loc_180026591
0x180026445  mov     [rsp+960h+var_8E8], rdi
0x18002644a  mov     [rsp+960h+var_8F0], rdi
0x18002644f  mov     [rsp+960h+var_8FC], edi
0x180026453  mov     [rbp+860h+var_8E0], rdi
0x180026457  mov     [rsp+960h+var_900], edi
0x18002645b  cmp     rcx, rax
0x18002645e  jz      short loc_18002647B
0x180026460  test    byte ptr [rcx+1Ch], 4
0x180026464  jz      short loc_18002647B
0x180026466  mov     edx, 12h
0x18002646b  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180026472  mov     rcx, [rcx+10h]
0x180026476  call    WPP_SF_
0x18002647b  mov     r15, [r13+148h]
0x180026482  mov     rsi, [rbp+860h+var_8D8]
0x180026486  mov     rsi, [rsi+8]
0x18002648a  mov     rcx, [rbp+860h+var_8D0]
0x18002648e  mov     r14, [rcx]
0x180026491  mov     rcx, [rcx+8]
0x180026495  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18002649a  mov     ebx, eax
0x18002649c  mov     rcx, [rbp+860h+var_8C8]
0x1800264a0  mov     rdi, [rcx]
0x1800264a3  mov     rcx, [rcx+8]
0x1800264a7  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800264ac  lea     rcx, [rsp+960h+var_8F0]
0x1800264b1  mov     [rsp+960h+var_910], rcx
0x1800264b6  lea     rcx, [rsp+960h+var_8E8]
0x1800264bb  mov     [rsp+960h+var_918], rcx
0x1800264c0  lea     rcx, [rbp+860h+var_8E0]
0x1800264c4  mov     [rsp+960h+var_920], rcx
0x1800264c9  lea     rcx, [rsp+960h+var_900]
0x1800264ce  mov     [rsp+960h+var_928], rcx
0x1800264d3  lea     rcx, [rsp+960h+var_8FC]
0x1800264d8  mov     [rsp+960h+var_930], rcx
0x1800264dd  mov     [rsp+960h+var_938], rsi
0x1800264e2  mov     [rsp+960h+var_940], r14
0x1800264e7  mov     r9d, ebx
0x1800264ea  mov     r8, rdi
0x1800264ed  mov     edx, eax
0x1800264ef  mov     ecx, [rsp+960h+var_8F8]
0x1800264f3  mov     rax, r15
0x1800264f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264fb  xor     edi, edi
0x1800264fd  test    eax, eax
0x1800264ff  jz      short loc_180026535
0x180026501  mov     r8d, eax; unsigned int
0x180026504  mov     rdx, [rsp+960h+var_8F0]; struct _EAP_ERROR *
0x180026509  lea     rcx, [rbp+860h+var_8B0]; this
0x18002650d  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180026512  nop
0x180026513  mov     rcx, [rsp+960h+var_8F0]
0x180026518  mov     rax, [r13+1A8h]
0x18002651f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026524  lea     r8, [rbp+860h+var_8B0]; struct EapHost::EapError *
0x180026528  lea     rcx, aEappeergetiden_1; "EapPeerGetIdentity"
0x18002652f  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x180026535  mov     rdx, [rsp+960h+var_8E8]
0x18002653a  test    rdx, rdx
0x18002653d  jz      short loc_180026558
0x18002653f  mov     rcx, r12
0x180026542  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180026547  mov     rcx, [rsp+960h+var_8E8]
0x18002654c  mov     rax, [r13+1B0h]
0x180026553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026558  mov     r8, [rbp+860h+var_8E0]
0x18002655c  test    r8, r8
0x18002655f  jz      short loc_180026584
0x180026561  mov     eax, [rsp+960h+var_900]
0x180026565  test    eax, eax
0x180026567  jz      short loc_180026584
0x180026569  mov     edx, eax
0x18002656b  mov     rcx, [rbp+860h+var_8C0]
0x18002656f  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180026574  mov     rcx, [rbp+860h+var_8E0]
0x180026578  mov     rax, [r13+1B0h]
0x18002657f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026584  cmp     [rsp+960h+var_8FC], edi
0x180026588  setnz   al
0x18002658b  mov     rcx, [rbp+860h+var_8B8]
0x18002658f  mov     [rcx], al
0x180026591  lea     rdx, DebugInfoEvent
0x180026598  mov     rcx, cs:eaphost_Context
0x18002659f  call    cs:__imp_EtwEventEnabled
0x1800265a5  lea     rbx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x1800265ac  test    al, al
0x1800265ae  jz      short loc_1800265F5
0x1800265b0  mov     r9, rbx
0x1800265b3  cmp     [r12], rdi
0x1800265b7  cmovnz  r9, [r12]
0x1800265bc  lea     r8, aEappeergetiden_0; "EapPeerGetIdentity Exit:\n Identity(%ls"...
0x1800265c3  mov     edx, 800h; unsigned __int64
0x1800265c8  lea     rcx, [rbp+860h+var_850]; char *
0x1800265cc  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800265d1  test    eax, eax
0x1800265d3  js      short loc_1800265F5
0x1800265d5  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800265dc  jge     short loc_1800265F5
0x1800265de  lea     r8, [rbp+860h+var_850]
0x1800265e2  lea     rdx, DebugInfoEvent
0x1800265e9  lea     rcx, eaphost_Context
0x1800265f0  call    McTemplateU0s_EtwEventWriteTransfer
0x1800265f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800265fc  lea     rax, WPP_GLOBAL_Control
0x180026603  cmp     rcx, rax
0x180026606  jz      short loc_18002662F
0x180026608  test    byte ptr [rcx+1Ch], 4
0x18002660c  jz      short loc_18002662F
0x18002660e  cmp     [r12], rdi
0x180026612  cmovnz  rbx, [r12]
0x180026617  mov     edx, 13h
0x18002661c  mov     r9, rbx
0x18002661f  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180026626  mov     rcx, [rcx+10h]
0x18002662a  call    WPP_SF_S
0x18002662f  mov     rcx, [rbp+860h+var_50]
0x180026636  xor     rcx, rsp; StackCookie
0x180026639  call    __security_check_cookie
0x18002663e  add     rsp, 928h
0x180026645  pop     r15
0x180026647  pop     r14
0x180026649  pop     r13
0x18002664b  pop     r12
0x18002664d  pop     rdi
0x18002664e  pop     rsi
0x18002664f  pop     rbx
0x180026650  pop     rbp
0x180026651  retn
```
