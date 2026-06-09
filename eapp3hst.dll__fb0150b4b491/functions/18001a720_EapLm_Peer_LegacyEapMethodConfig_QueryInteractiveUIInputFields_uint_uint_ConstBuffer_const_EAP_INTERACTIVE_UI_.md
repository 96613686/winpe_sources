# EapLm::Peer::LegacyEapMethodConfig::QueryInteractiveUIInputFields(uint,uint,ConstBuffer const &,_EAP_INTERACTIVE_UI_DATA *)

- ea: `0x18001a720`
- end: `0x18001aaa7`
- name: `?QueryInteractiveUIInputFields@LegacyEapMethodConfig@Peer@EapLm@@UEAAXIIAEBUConstBuffer@@PEAU_EAP_INTERACTIVE_UI_DATA@@@Z`
- size: `903`
- prototype: `void __fastcall(EapLm::Peer::LegacyEapMethodConfig *__hidden this, unsigned int, unsigned int, const struct ConstBuffer *, struct _EAP_INTERACTIVE_UI_DATA *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x18000cd8c`
- `0x18001549c`
- `0x180016400`
- `0x180017790`
- `0x180018eb0`
- `0x18001a720`
- `0x18001b154`
- `0x18001b1dc`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001a770`
- `ntdll!EtwEventEnabled` at `0x18001a900`
- `ntdll!EtwEventEnabled` at `0x18001aa08`
- `ntdll!EtwEventEnabled` at `0x18001a770`
- `ntdll!EtwEventEnabled` at `0x18001a900`
- `ntdll!EtwEventEnabled` at `0x18001aa08`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapLm::Peer::LegacyEapMethodConfig::QueryInteractiveUIInputFields(
        EapLm::DelayLoadModule **this,
        unsigned int a2,
        unsigned int a3,
        const struct ConstBuffer *a4,
        struct _EAP_INTERACTIVE_UI_DATA *a5)
{
  EapLm::DelayLoadModule *v8; // rax
  __int64 (__fastcall *v9)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, _EAP_INTERACTIVE_UI_DATA *); // r14
  void (*v10)(void); // r12
  __int64 v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  __int128 v14; // xmm1
  EAP_UI_DATA_FORMAT v15; // xmm2_8
  EapLm::Peer::LegacyEapMethodConfig *v16; // rcx
  _BYTE v17[24]; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+58h] [rbp-A8h]
  unsigned int v19; // [rsp+60h] [rbp-A0h]
  _EAP_INTERACTIVE_UI_DATA v20; // [rsp+68h] [rbp-98h] BYREF
  char v21[2048]; // [rsp+80h] [rbp-80h] BYREF

  v19 = a3;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v21,
              0x800u,
              "RasEapQueryInteractiveUIInputFields Entry:\n Context data(%Id) bytes",
              *((_QWORD *)a4 + 1)) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v21);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_P(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids,
      *((_QWORD *)a4 + 1));
  EapLm::DelayLoadModule::LoadIfNeeded(this[20], 1);
  v8 = this[20];
  v9 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, _EAP_INTERACTIVE_UI_DATA *))*((_QWORD *)v8 + 27);
  if ( !v9 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(
        &eaphost_Context,
        (__int64)PeerFunctionNotSupported,
        "QueryInteractiveUIInputFields");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    v17[8] = *((_BYTE *)this + 16);
    *(_DWORD *)&v17[12] = *((_DWORD *)this + 5);
    *(_DWORD *)&v17[16] = *((_DWORD *)this + 6);
    if ( v17[8] != 0xFE )
      *(_QWORD *)&v17[12] = 0;
    *(_QWORD *)v17 = &EapHost::EapMethodType::`vftable';
    v18 = *((_DWORD *)this + 7);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)v17, 0x80420020);
  }
  v10 = (void (*)(void))*((_QWORD *)v8 + 29);
  memset(&v20, 0, sizeof(v20));
  v11 = *(_QWORD *)a4;
  v12 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*((_QWORD *)a4 + 1));
  v13 = v9(*((unsigned __int8 *)this + 16), a2, v19, v12, v11, &v20);
  if ( v13 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v21, 0x800u, "EapPeerQueryInteractiveUIInputFields failed %d", v13) >= 0
      && (byte_18004AF81 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugErrorEvent, v21);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v13);
    v17[8] = *((_BYTE *)this + 16);
    *(_DWORD *)&v17[12] = *((_DWORD *)this + 5);
    *(_DWORD *)&v17[16] = *((_DWORD *)this + 6);
    if ( v17[8] != 0xFE )
      *(_QWORD *)&v17[12] = 0;
    *(_QWORD *)v17 = &EapHost::EapMethodType::`vftable';
    v18 = *((_DWORD *)this + 7);
    EapHost::EapException::Throw(v13, (const struct EapHost::EapMethodType *)v17, v13);
  }
  crt_ref<_EAP_INTERACTIVE_UI_DATA>::crt_ref<_EAP_INTERACTIVE_UI_DATA>(v17, &v20);
  v14 = *(_OWORD *)v17;
  v15.credData = *(EAP_CRED_REQ **)&v17[16];
  memset(v17, 0, sizeof(v17));
  *(_OWORD *)&a5->dwVersion = v14;
  a5->pbUiData = v15;
  EapLm::Peer::LegacyEapMethodConfig::FreeEAPInteractiveUIData(v16, &v20, v10);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v21, 0x800u, "RasEapQueryInteractiveUIInputFields Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v21);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
  Free<HeapAllocator>(v17);
}

```

## disassembly

```asm
0x18001a720  push    rbp
0x18001a722  push    rbx
0x18001a723  push    rsi
0x18001a724  push    rdi
0x18001a725  push    r12
0x18001a727  push    r13
0x18001a729  push    r14
0x18001a72b  push    r15
0x18001a72d  lea     rbp, [rsp-798h]
0x18001a735  sub     rsp, 898h
0x18001a73c  mov     rax, cs:__security_cookie
0x18001a743  xor     rax, rsp
0x18001a746  mov     [rbp+7D0h+var_50], rax
0x18001a74d  mov     rsi, r9
0x18001a750  mov     [rsp+8D0h+var_870], r8d
0x18001a755  mov     r13d, edx
0x18001a758  mov     rdi, rcx
0x18001a75b  mov     r15, [rbp+7D0h+arg_20]
0x18001a762  lea     rdx, DebugInfoEvent
0x18001a769  mov     rcx, cs:eaphost_Context
0x18001a770  call    cs:__imp_EtwEventEnabled
0x18001a776  xor     ebx, ebx
0x18001a778  test    al, al
0x18001a77a  jz      short loc_18001A7B8
0x18001a77c  mov     r9, [rsi+8]
0x18001a780  lea     r8, aRaseapqueryint_0; "RasEapQueryInteractiveUIInputFields Ent"...
0x18001a787  mov     edx, 800h; unsigned __int64
0x18001a78c  lea     rcx, [rbp+7D0h+var_850]; char *
0x18001a790  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001a795  test    eax, eax
0x18001a797  js      short loc_18001A7B8
0x18001a799  cmp     cs:Microsoft_Windows_EapHostEnableBits, bl
0x18001a79f  jge     short loc_18001A7B8
0x18001a7a1  lea     r8, [rbp+7D0h+var_850]
0x18001a7a5  lea     rdx, DebugInfoEvent
0x18001a7ac  lea     rcx, eaphost_Context
0x18001a7b3  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a7b8  lea     r12, WPP_GLOBAL_Control
0x18001a7bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7c6  cmp     rcx, r12
0x18001a7c9  jz      short loc_18001A7EA
0x18001a7cb  test    byte ptr [rcx+1Ch], 4
0x18001a7cf  jz      short loc_18001A7EA
0x18001a7d1  mov     edx, 1Ch
0x18001a7d6  mov     r9, [rsi+8]
0x18001a7da  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001a7e1  mov     rcx, [rcx+10h]
0x18001a7e5  call    WPP_SF_P
0x18001a7ea  mov     dl, 1; bool
0x18001a7ec  mov     rcx, [rdi+0A0h]; this
0x18001a7f3  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001a7f8  mov     rax, [rdi+0A0h]
0x18001a7ff  mov     r14, [rax+0D8h]
0x18001a806  test    r14, r14
0x18001a809  jnz     loc_18001A89E
0x18001a80f  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x18001a816  jz      short loc_18001A832
0x18001a818  lea     r8, aQueryinteracti; "QueryInteractiveUIInputFields"
0x18001a81f  lea     rdx, PeerFunctionNotSupported
0x18001a826  lea     rcx, eaphost_Context
0x18001a82d  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a832  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a839  cmp     rcx, r12
0x18001a83c  jz      short loc_18001A859
0x18001a83e  test    byte ptr [rcx+1Ch], 1
0x18001a842  jz      short loc_18001A859
0x18001a844  mov     edx, 1Dh
0x18001a849  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001a850  mov     rcx, [rcx+10h]
0x18001a854  call    WPP_SF_
0x18001a859  mov     cl, [rdi+10h]
0x18001a85c  mov     byte ptr [rsp+8D0h+var_890+8], cl
0x18001a860  mov     eax, [rdi+14h]
0x18001a863  mov     dword ptr [rsp+8D0h+var_890+0Ch], eax
0x18001a867  mov     eax, [rdi+18h]
0x18001a86a  mov     dword ptr [rsp+8D0h+var_880], eax
0x18001a86e  cmp     cl, 0FEh
0x18001a871  jz      short loc_18001A878
0x18001a873  mov     qword ptr [rsp+8D0h+var_890+0Ch], rbx
0x18001a878  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001a87f  mov     qword ptr [rsp+8D0h+var_890], rax
0x18001a884  mov     eax, [rdi+1Ch]
0x18001a887  mov     [rsp+8D0h+var_878], eax
0x18001a88b  mov     ecx, 80420020h; unsigned int
0x18001a890  mov     r8d, ecx; unsigned int
0x18001a893  lea     rdx, [rsp+8D0h+var_890]; struct EapHost::EapMethodType *
0x18001a898  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001a89e  mov     r12, [rax+0E8h]
0x18001a8a5  xorps   xmm0, xmm0
0x18001a8a8  xor     eax, eax
0x18001a8aa  movups  xmmword ptr [rsp+8D0h+var_868.dwVersion], xmm0
0x18001a8af  mov     qword ptr [rsp+8D0h+var_868.pbUiData], rax
0x18001a8b4  mov     rbx, [rsi]
0x18001a8b7  mov     rcx, [rsi+8]
0x18001a8bb  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001a8c0  movzx   ecx, byte ptr [rdi+10h]
0x18001a8c4  lea     rdx, [rsp+8D0h+var_868]
0x18001a8c9  mov     [rsp+8D0h+var_8A8], rdx
0x18001a8ce  mov     [rsp+8D0h+var_8B0], rbx
0x18001a8d3  mov     r9d, eax
0x18001a8d6  mov     r8d, [rsp+8D0h+var_870]
0x18001a8db  mov     edx, r13d
0x18001a8de  mov     rax, r14
0x18001a8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8e6  mov     ebx, eax
0x18001a8e8  xor     esi, esi
0x18001a8ea  test    eax, eax
0x18001a8ec  jz      loc_18001A9B9
0x18001a8f2  lea     rdx, DebugErrorEvent
0x18001a8f9  mov     rcx, cs:eaphost_Context
0x18001a900  call    cs:__imp_EtwEventEnabled
0x18001a906  test    al, al
0x18001a908  jz      short loc_18001A946
0x18001a90a  mov     r9d, ebx
0x18001a90d  lea     r8, aEappeerqueryin_1; "EapPeerQueryInteractiveUIInputFields fa"...
0x18001a914  mov     edx, 800h; unsigned __int64
0x18001a919  lea     rcx, [rbp+7D0h+var_850]; char *
0x18001a91d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001a922  test    eax, eax
0x18001a924  js      short loc_18001A946
0x18001a926  test    cs:byte_18004AF81, 8
0x18001a92d  jz      short loc_18001A946
0x18001a92f  lea     r8, [rbp+7D0h+var_850]
0x18001a933  lea     rdx, DebugErrorEvent
0x18001a93a  lea     rcx, eaphost_Context
0x18001a941  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a946  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a94d  lea     rax, WPP_GLOBAL_Control
0x18001a954  cmp     rcx, rax
0x18001a957  jz      short loc_18001A977
0x18001a959  test    byte ptr [rcx+1Ch], 1
0x18001a95d  jz      short loc_18001A977
0x18001a95f  mov     edx, 1Eh
0x18001a964  mov     r9d, ebx
0x18001a967  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001a96e  mov     rcx, [rcx+10h]
0x18001a972  call    WPP_SF_d
0x18001a977  mov     cl, [rdi+10h]
0x18001a97a  mov     byte ptr [rsp+8D0h+var_890+8], cl
0x18001a97e  mov     eax, [rdi+14h]
0x18001a981  mov     dword ptr [rsp+8D0h+var_890+0Ch], eax
0x18001a985  mov     eax, [rdi+18h]
0x18001a988  mov     dword ptr [rsp+8D0h+var_880], eax
0x18001a98c  cmp     cl, 0FEh
0x18001a98f  jz      short loc_18001A996
0x18001a991  mov     qword ptr [rsp+8D0h+var_890+0Ch], rsi
0x18001a996  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001a99d  mov     qword ptr [rsp+8D0h+var_890], rax
0x18001a9a2  mov     eax, [rdi+1Ch]
0x18001a9a5  mov     [rsp+8D0h+var_878], eax
0x18001a9a9  mov     r8d, ebx; unsigned int
0x18001a9ac  lea     rdx, [rsp+8D0h+var_890]; struct EapHost::EapMethodType *
0x18001a9b1  mov     ecx, ebx; unsigned int
0x18001a9b3  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001a9b9  lea     rdx, [rsp+8D0h+var_868]
0x18001a9be  lea     rcx, [rsp+8D0h+var_890]
0x18001a9c3  call    ??0?$crt_ref@U_EAP_INTERACTIVE_UI_DATA@@@@QEAA@AEBU_EAP_INTERACTIVE_UI_DATA@@@Z; crt_ref<_EAP_INTERACTIVE_UI_DATA>::crt_ref<_EAP_INTERACTIVE_UI_DATA>(_EAP_INTERACTIVE_UI_DATA const &)
0x18001a9c8  nop
0x18001a9c9  movups  xmm1, [rsp+8D0h+var_890]
0x18001a9ce  movsd   xmm2, [rsp+8D0h+var_880]
0x18001a9d4  xorps   xmm0, xmm0
0x18001a9d7  xor     eax, eax
0x18001a9d9  movups  [rsp+8D0h+var_890], xmm0
0x18001a9de  mov     [rsp+8D0h+var_880], rax
0x18001a9e3  movups  xmmword ptr [r15], xmm1
0x18001a9e7  movsd   qword ptr [r15+10h], xmm2
0x18001a9ed  mov     r8, r12; unsigned int (*)(unsigned __int8 *)
0x18001a9f0  lea     rdx, [rsp+8D0h+var_868]; struct _EAP_INTERACTIVE_UI_DATA *
0x18001a9f5  call    ?FreeEAPInteractiveUIData@LegacyEapMethodConfig@Peer@EapLm@@AEAAXPEAU_EAP_INTERACTIVE_UI_DATA@@P6AKPEAE@Z@Z; EapLm::Peer::LegacyEapMethodConfig::FreeEAPInteractiveUIData(_EAP_INTERACTIVE_UI_DATA *,ulong (*)(uchar *))
0x18001a9fa  lea     rdx, DebugInfoEvent
0x18001aa01  mov     rcx, cs:eaphost_Context
0x18001aa08  call    cs:__imp_EtwEventEnabled
0x18001aa0e  test    al, al
0x18001aa10  jz      short loc_18001AA4B
0x18001aa12  lea     r8, aRaseapqueryint; "RasEapQueryInteractiveUIInputFields Exi"...
0x18001aa19  mov     edx, 800h; unsigned __int64
0x18001aa1e  lea     rcx, [rbp+7D0h+var_850]; char *
0x18001aa22  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001aa27  test    eax, eax
0x18001aa29  js      short loc_18001AA4B
0x18001aa2b  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x18001aa32  jge     short loc_18001AA4B
0x18001aa34  lea     r8, [rbp+7D0h+var_850]
0x18001aa38  lea     rdx, DebugInfoEvent
0x18001aa3f  lea     rcx, eaphost_Context
0x18001aa46  call    McTemplateU0s_EtwEventWriteTransfer
0x18001aa4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa52  lea     rax, WPP_GLOBAL_Control
0x18001aa59  cmp     rcx, rax
0x18001aa5c  jz      short loc_18001AA7A
0x18001aa5e  test    byte ptr [rcx+1Ch], 4
0x18001aa62  jz      short loc_18001AA7A
0x18001aa64  mov     edx, 1Fh
0x18001aa69  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001aa70  mov     rcx, [rcx+10h]
0x18001aa74  call    WPP_SF_
0x18001aa79  nop
0x18001aa7a  lea     rcx, [rsp+8D0h+var_890]
0x18001aa7f  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_INTERACTIVE_UI_DATA@@@Z; Free<HeapAllocator>(_EAP_INTERACTIVE_UI_DATA &)
0x18001aa84  mov     rcx, [rbp+7D0h+var_50]
0x18001aa8b  xor     rcx, rsp; StackCookie
0x18001aa8e  call    __security_check_cookie
0x18001aa93  add     rsp, 898h
0x18001aa9a  pop     r15
0x18001aa9c  pop     r14
0x18001aa9e  pop     r13
0x18001aaa0  pop     r12
0x18001aaa2  pop     rdi
0x18001aaa3  pop     rsi
0x18001aaa4  pop     rbx
0x18001aaa5  pop     rbp
0x18001aaa6  retn
```
