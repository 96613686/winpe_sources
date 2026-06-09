# EapLm::Peer::EapMethodConfig::QueryCredentialInputFields(void *,uint,ConstBuffer const &,_EAP_CONFIG_INPUT_FIELD_ARRAY *)

- ea: `0x18001d370`
- end: `0x18001d693`
- name: `?QueryCredentialInputFields@EapMethodConfig@Peer@EapLm@@UEAAXPEAXIAEBUConstBuffer@@PEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z`
- size: `803`
- prototype: `void __fastcall(EapLm::Peer::EapMethodConfig *__hidden this, void *, unsigned int, const struct ConstBuffer *, struct _EAP_CONFIG_INPUT_FIELD_ARRAY *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x18000ccf4`
- `0x18001549c`
- `0x1800154dc`
- `0x180016400`
- `0x1800177bc`
- `0x180017dbc`
- `0x180018e10`
- `0x18001b154`
- `0x18001d370`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001d3be`
- `ntdll!EtwEventEnabled` at `0x18001d5ec`
- `ntdll!EtwEventEnabled` at `0x18001d3be`
- `ntdll!EtwEventEnabled` at `0x18001d5ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::Peer::EapMethodConfig::QueryCredentialInputFields(
        EapLm::DelayLoadModule **this,
        void *a2,
        unsigned int a3,
        const struct ConstBuffer *a4,
        struct _EAP_CONFIG_INPUT_FIELD_ARRAY *a5)
{
  EapLm::DelayLoadModule *v8; // rax
  __int64 (__fastcall *v9)(_QWORD, __int128 *, _QWORD, _QWORD, __int64, struct _EAP_CONFIG_INPUT_FIELD_ARRAY *, struct _EAP_ERROR **); // r14
  void (*v10)(void); // r12
  void (__fastcall *v11)(struct _EAP_ERROR *); // r15
  __int64 v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // eax
  const wchar_t *v15; // rdx
  EapLm::Peer::LegacyEapMethodConfig *v16; // rcx
  struct _EAP_CONFIG_INPUT_FIELD_ARRAY v17; // xmm1
  void (*v18)(void); // r8
  struct _EAP_ERROR *v19; // [rsp+40h] [rbp-8F8h] BYREF
  _BYTE v20[20]; // [rsp+50h] [rbp-8E8h] BYREF
  int v21; // [rsp+68h] [rbp-8D0h]
  __int128 v22; // [rsp+70h] [rbp-8C8h] BYREF
  struct _EAP_CONFIG_INPUT_FIELD_ARRAY v23; // [rsp+80h] [rbp-8B8h] BYREF
  char v24[96]; // [rsp+90h] [rbp-8A8h] BYREF
  char v25[2048]; // [rsp+F0h] [rbp-848h] BYREF
  const Exception *v26; // [rsp+8F0h] [rbp-48h] BYREF

  *(_QWORD *)&v22 = a4;
  *(_QWORD *)v20 = a2;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v25, 0x800u, "EapPeerQueryCredentialInputFields Entry:\n flags(%d)", a3) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v25);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids, a3);
  EapLm::DelayLoadModule::LoadIfNeeded(this[17], 1);
  v8 = this[17];
  v9 = (__int64 (__fastcall *)(_QWORD, __int128 *, _QWORD, _QWORD, __int64, struct _EAP_CONFIG_INPUT_FIELD_ARRAY *, struct _EAP_ERROR **))*((_QWORD *)v8 + 27);
  if ( !v9 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(
        &eaphost_Context,
        (__int64)PeerFunctionNotSupported,
        "QueryCredentialInputFields");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
    v20[8] = *((_BYTE *)this + 16);
    *(_DWORD *)&v20[12] = *((_DWORD *)this + 5);
    *(_DWORD *)&v20[16] = *((_DWORD *)this + 6);
    if ( v20[8] != 0xFE )
      *(_QWORD *)&v20[12] = 0;
    *(_QWORD *)v20 = &EapHost::EapMethodType::`vftable';
    v21 = *((_DWORD *)this + 7);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)v20, 0x80420020);
  }
  v10 = (void (*)(void))*((_QWORD *)v8 + 29);
  v11 = (void (__fastcall *)(struct _EAP_ERROR *))*((_QWORD *)v8 + 28);
  v23 = 0;
  v19 = 0;
  v12 = *(_QWORD *)a4;
  v13 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*(_QWORD *)(v22 + 8));
  v22 = *((_OWORD *)this + 1);
  v14 = v9(*(_QWORD *)v20, &v22, a3, v13, v12, &v23, &v19);
  if ( v14 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v24, v19, v14);
    v11(v19);
    EapHost::EapException::Throw(L"EapPeerQueryCredentialInputFields", v15, (const struct EapHost::EapError *)v24);
  }
  *(_OWORD *)v20 = 0;
  try
  {
    crt_ref<_EAP_CONFIG_INPUT_FIELD_ARRAY>::Assign(v20, (__int64)&v23);
    v17 = *(struct _EAP_CONFIG_INPUT_FIELD_ARRAY *)v20;
    *(_OWORD *)v20 = 0;
    *a5 = v17;
    v18 = v10;
  }
  catch ( const Exception *v26 )
  {
    Free<HeapAllocator>((__int64)v20);
    throw;
  }
  EapLm::Peer::LegacyEapMethodConfig::FreeEAPConfigInputFieldArray(v16, &v23, v18);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v25, 0x800u, "EapPeerQueryCredentialInputFields Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v25);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
  Free<HeapAllocator>((__int64)v20);
}

```

## disassembly

```asm
0x18001d370  push    rbx
0x18001d372  push    rsi
0x18001d373  push    rdi
0x18001d374  push    r12
0x18001d376  push    r13
0x18001d378  push    r14
0x18001d37a  push    r15
0x18001d37c  sub     rsp, 900h
0x18001d383  mov     rax, cs:__security_cookie
0x18001d38a  xor     rax, rsp
0x18001d38d  mov     [rsp+938h+var_40], rax
0x18001d395  mov     rbx, r9
0x18001d398  mov     qword ptr [rsp+938h+var_8C8], rbx
0x18001d39d  mov     esi, r8d
0x18001d3a0  mov     qword ptr [rsp+938h+var_8E8], rdx
0x18001d3a5  mov     rdi, rcx
0x18001d3a8  mov     r13, [rsp+938h+arg_20]
0x18001d3b0  lea     rdx, DebugInfoEvent
0x18001d3b7  mov     rcx, cs:eaphost_Context
0x18001d3be  call    cs:__imp_EtwEventEnabled
0x18001d3c4  xor     r15d, r15d
0x18001d3c7  test    al, al
0x18001d3c9  jz      short loc_18001D40F
0x18001d3cb  mov     r9d, esi
0x18001d3ce  lea     r8, aEappeerquerycr_0; "EapPeerQueryCredentialInputFields Entry"...
0x18001d3d5  mov     edx, 800h; unsigned __int64
0x18001d3da  lea     rcx, [rsp+938h+var_848]; char *
0x18001d3e2  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001d3e7  test    eax, eax
0x18001d3e9  js      short loc_18001D40F
0x18001d3eb  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x18001d3f2  jge     short loc_18001D40F
0x18001d3f4  lea     r8, [rsp+938h+var_848]
0x18001d3fc  lea     rdx, DebugInfoEvent
0x18001d403  lea     rcx, eaphost_Context
0x18001d40a  call    McTemplateU0s_EtwEventWriteTransfer
0x18001d40f  lea     r12, WPP_GLOBAL_Control
0x18001d416  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d41d  cmp     rcx, r12
0x18001d420  jz      short loc_18001D440
0x18001d422  test    byte ptr [rcx+1Ch], 4
0x18001d426  jz      short loc_18001D440
0x18001d428  mov     edx, 0Dh
0x18001d42d  mov     r9d, esi
0x18001d430  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001d437  mov     rcx, [rcx+10h]
0x18001d43b  call    WPP_SF_d
0x18001d440  mov     dl, 1; bool
0x18001d442  mov     rcx, [rdi+88h]; this
0x18001d449  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001d44e  mov     rax, [rdi+88h]
0x18001d455  mov     r14, [rax+0D8h]
0x18001d45c  test    r14, r14
0x18001d45f  jnz     loc_18001D4F4
0x18001d465  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x18001d46c  jz      short loc_18001D488
0x18001d46e  lea     r8, aQuerycredentia; "QueryCredentialInputFields"
0x18001d475  lea     rdx, PeerFunctionNotSupported
0x18001d47c  lea     rcx, eaphost_Context
0x18001d483  call    McTemplateU0s_EtwEventWriteTransfer
0x18001d488  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d48f  cmp     rcx, r12
0x18001d492  jz      short loc_18001D4AF
0x18001d494  test    byte ptr [rcx+1Ch], 1
0x18001d498  jz      short loc_18001D4AF
0x18001d49a  mov     edx, 0Eh
0x18001d49f  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001d4a6  mov     rcx, [rcx+10h]
0x18001d4aa  call    WPP_SF_
0x18001d4af  mov     cl, [rdi+10h]
0x18001d4b2  mov     byte ptr [rsp+938h+var_8E8+8], cl
0x18001d4b6  mov     eax, [rdi+14h]
0x18001d4b9  mov     dword ptr [rsp+938h+var_8E8+0Ch], eax
0x18001d4bd  mov     eax, [rdi+18h]
0x18001d4c0  mov     [rsp+60h], eax
0x18001d4c4  cmp     cl, 0FEh
0x18001d4c7  jz      short loc_18001D4CE
0x18001d4c9  mov     qword ptr [rsp+938h+var_8E8+0Ch], r15
0x18001d4ce  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001d4d5  mov     qword ptr [rsp+938h+var_8E8], rax
0x18001d4da  mov     eax, [rdi+1Ch]
0x18001d4dd  mov     [rsp+938h+var_8D0], eax
0x18001d4e1  mov     ecx, 80420020h; unsigned int
0x18001d4e6  mov     r8d, ecx; unsigned int
0x18001d4e9  lea     rdx, [rsp+938h+var_8E8]; struct EapHost::EapMethodType *
0x18001d4ee  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001d4f4  mov     r12, [rax+0E8h]
0x18001d4fb  mov     r15, [rax+0E0h]
0x18001d502  xorps   xmm0, xmm0
0x18001d505  movups  xmmword ptr [rsp+938h+var_8B8.dwVersion], xmm0
0x18001d50d  mov     [rsp+938h+var_8F8], 0
0x18001d516  mov     rbx, [rbx]
0x18001d519  mov     rcx, qword ptr [rsp+938h+var_8C8]
0x18001d51e  mov     rcx, [rcx+8]
0x18001d522  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001d527  movups  xmm0, xmmword ptr [rdi+10h]
0x18001d52b  movdqu  [rsp+938h+var_8C8], xmm0
0x18001d531  lea     rcx, [rsp+938h+var_8F8]
0x18001d536  mov     [rsp+938h+var_908], rcx
0x18001d53b  lea     rcx, [rsp+938h+var_8B8]
0x18001d543  mov     [rsp+938h+var_910], rcx
0x18001d548  mov     [rsp+938h+var_918], rbx
0x18001d54d  mov     r9d, eax
0x18001d550  mov     r8d, esi
0x18001d553  lea     rdx, [rsp+938h+var_8C8]
0x18001d558  mov     rcx, qword ptr [rsp+938h+var_8E8]
0x18001d55d  mov     rax, r14
0x18001d560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d565  test    eax, eax
0x18001d567  jz      short loc_18001D5A1
0x18001d569  mov     r8d, eax; unsigned int
0x18001d56c  mov     rdx, [rsp+938h+var_8F8]; struct _EAP_ERROR *
0x18001d571  lea     rcx, [rsp+938h+var_8A8]; this
0x18001d579  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001d57e  nop
0x18001d57f  mov     rcx, [rsp+938h+var_8F8]
0x18001d584  mov     rax, r15
0x18001d587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d58c  lea     r8, [rsp+938h+var_8A8]; struct EapHost::EapError *
0x18001d594  lea     rcx, aEappeerquerycr_1; "EapPeerQueryCredentialInputFields"
0x18001d59b  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001d5a1  xorps   xmm0, xmm0
0x18001d5a4  movups  [rsp+938h+var_8E8], xmm0
0x18001d5a9  lea     rdx, [rsp+938h+var_8B8]
0x18001d5b1  lea     rcx, [rsp+938h+var_8E8]
0x18001d5b6  call    ?Assign@?$crt_ref@U_EAP_CONFIG_INPUT_FIELD_ARRAY@@@@QEAAXAEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; crt_ref<_EAP_CONFIG_INPUT_FIELD_ARRAY>::Assign(_EAP_CONFIG_INPUT_FIELD_ARRAY const &)
0x18001d5bb  movaps  xmm1, [rsp+938h+var_8E8]
0x18001d5c0  xorps   xmm0, xmm0
0x18001d5c3  movups  [rsp+938h+var_8E8], xmm0
0x18001d5c8  movdqu  xmmword ptr [r13+0], xmm1
0x18001d5ce  mov     r8, r12; unsigned int (*)(unsigned __int8 *)
0x18001d5d1  lea     rdx, [rsp+938h+var_8B8]; struct _EAP_CONFIG_INPUT_FIELD_ARRAY *
0x18001d5d9  call    ?FreeEAPConfigInputFieldArray@LegacyEapMethodConfig@Peer@EapLm@@AEAAXPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@P6AKPEAE@Z@Z; EapLm::Peer::LegacyEapMethodConfig::FreeEAPConfigInputFieldArray(_EAP_CONFIG_INPUT_FIELD_ARRAY *,ulong (*)(uchar *))
0x18001d5de  lea     rdx, DebugInfoEvent
0x18001d5e5  mov     rcx, cs:eaphost_Context
0x18001d5ec  call    cs:__imp_EtwEventEnabled
0x18001d5f2  test    al, al
0x18001d5f4  jz      short loc_18001D637
0x18001d5f6  lea     r8, aEappeerquerycr; "EapPeerQueryCredentialInputFields Exit"
0x18001d5fd  mov     edx, 800h; unsigned __int64
0x18001d602  lea     rcx, [rsp+938h+var_848]; char *
0x18001d60a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001d60f  test    eax, eax
0x18001d611  js      short loc_18001D637
0x18001d613  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001d61a  jge     short loc_18001D637
0x18001d61c  lea     r8, [rsp+938h+var_848]
0x18001d624  lea     rdx, DebugInfoEvent
0x18001d62b  lea     rcx, eaphost_Context
0x18001d632  call    McTemplateU0s_EtwEventWriteTransfer
0x18001d637  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d63e  lea     rax, WPP_GLOBAL_Control
0x18001d645  cmp     rcx, rax
0x18001d648  jz      short loc_18001D666
0x18001d64a  test    byte ptr [rcx+1Ch], 4
0x18001d64e  jz      short loc_18001D666
0x18001d650  mov     edx, 0Fh
0x18001d655  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001d65c  mov     rcx, [rcx+10h]
0x18001d660  call    WPP_SF_
0x18001d665  nop
0x18001d666  lea     rcx, [rsp+938h+var_8E8]
0x18001d66b  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; Free<HeapAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)
0x18001d670  mov     rcx, [rsp+938h+var_40]
0x18001d678  xor     rcx, rsp; StackCookie
0x18001d67b  call    __security_check_cookie
0x18001d680  add     rsp, 900h
0x18001d687  pop     r15
0x18001d689  pop     r14
0x18001d68b  pop     r13
0x18001d68d  pop     r12
0x18001d68f  pop     rdi
0x18001d690  pop     rsi
0x18001d691  pop     rbx
0x18001d692  retn
```
