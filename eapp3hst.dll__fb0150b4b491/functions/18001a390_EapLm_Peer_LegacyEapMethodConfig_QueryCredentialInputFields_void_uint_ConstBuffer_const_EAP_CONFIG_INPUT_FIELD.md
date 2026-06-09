# EapLm::Peer::LegacyEapMethodConfig::QueryCredentialInputFields(void *,uint,ConstBuffer const &,_EAP_CONFIG_INPUT_FIELD_ARRAY *)

- ea: `0x18001a390`
- end: `0x18001a70d`
- name: `?QueryCredentialInputFields@LegacyEapMethodConfig@Peer@EapLm@@UEAAXPEAXIAEBUConstBuffer@@PEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z`
- size: `893`
- prototype: `void __fastcall(EapLm::Peer::LegacyEapMethodConfig *__hidden this, void *, unsigned int, const struct ConstBuffer *, struct _EAP_CONFIG_INPUT_FIELD_ARRAY *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x18000ccf4`
- `0x18001549c`
- `0x180016400`
- `0x180017dbc`
- `0x180018e10`
- `0x18001a390`
- `0x18001b154`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001a3de`
- `ntdll!EtwEventEnabled` at `0x18001a56c`
- `ntdll!EtwEventEnabled` at `0x18001a66c`
- `ntdll!EtwEventEnabled` at `0x18001a3de`
- `ntdll!EtwEventEnabled` at `0x18001a56c`
- `ntdll!EtwEventEnabled` at `0x18001a66c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall EapLm::Peer::LegacyEapMethodConfig::QueryCredentialInputFields(
        EapLm::DelayLoadModule **this,
        void *a2,
        unsigned int a3,
        const struct ConstBuffer *a4,
        struct _EAP_CONFIG_INPUT_FIELD_ARRAY *a5)
{
  EapLm::DelayLoadModule *v9; // rax
  __int64 (__fastcall *v10)(_QWORD, void *, _QWORD, _QWORD, int, _EAP_CONFIG_INPUT_FIELD_ARRAY *); // rsi
  void (*v11)(void); // r14
  int v12; // eax
  unsigned int v13; // edi
  struct _EAP_CONFIG_INPUT_FIELD_ARRAY v14; // xmm1
  EapLm::Peer::LegacyEapMethodConfig *v15; // rcx
  _BYTE v16[20]; // [rsp+40h] [rbp-C0h] BYREF
  int v17; // [rsp+58h] [rbp-A8h]
  _EAP_CONFIG_INPUT_FIELD_ARRAY v18; // [rsp+60h] [rbp-A0h] BYREF
  char v19[2048]; // [rsp+70h] [rbp-90h] BYREF

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v19, 0x800u, "RasEapQueryCredentialInputFields Entry:\n flags(%d)", a3) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v19);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, a3);
  EapLm::DelayLoadModule::LoadIfNeeded(this[17], 1);
  v9 = this[17];
  v10 = (__int64 (__fastcall *)(_QWORD, void *, _QWORD, _QWORD, int, _EAP_CONFIG_INPUT_FIELD_ARRAY *))*((_QWORD *)v9 + 27);
  if ( !v10 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(
        &eaphost_Context,
        (__int64)PeerFunctionNotSupported,
        "QueryCredentialInputFields");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    v16[8] = *((_BYTE *)this + 16);
    *(_DWORD *)&v16[12] = *((_DWORD *)this + 5);
    *(_DWORD *)&v16[16] = *((_DWORD *)this + 6);
    if ( v16[8] != 0xFE )
      *(_QWORD *)&v16[12] = 0;
    *(_QWORD *)v16 = &EapHost::EapMethodType::`vftable';
    v17 = *((_DWORD *)this + 7);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)v16, 0x80420020);
  }
  v11 = (void (*)(void))*((_QWORD *)v9 + 29);
  v18 = 0;
  v12 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*((_QWORD *)a4 + 1));
  v13 = v10(*((unsigned __int8 *)this + 16), a2, a3, *(_QWORD *)a4, v12, &v18);
  if ( v13 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v19, 0x800u, "RasEapQueryCredentialInputFields failed %d", v13) >= 0
      && (byte_18004AF81 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugErrorEvent, v19);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v13);
    v16[8] = *((_BYTE *)this + 16);
    *(_DWORD *)&v16[12] = *((_DWORD *)this + 5);
    *(_DWORD *)&v16[16] = *((_DWORD *)this + 6);
    if ( v16[8] != 0xFE )
      *(_QWORD *)&v16[12] = 0;
    *(_QWORD *)v16 = &EapHost::EapMethodType::`vftable';
    v17 = *((_DWORD *)this + 7);
    EapHost::EapException::Throw(v13, (const struct EapHost::EapMethodType *)v16, v13);
  }
  *(_OWORD *)v16 = 0;
  crt_ref<_EAP_CONFIG_INPUT_FIELD_ARRAY>::Assign(v16, (__int64)&v18);
  v14 = *(struct _EAP_CONFIG_INPUT_FIELD_ARRAY *)v16;
  *(_OWORD *)v16 = 0;
  *a5 = v14;
  EapLm::Peer::LegacyEapMethodConfig::FreeEAPConfigInputFieldArray(v15, &v18, v11);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v19, 0x800u, "RasEapQueryCredentialInputFields Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v19);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
  Free<HeapAllocator>((__int64)v16);
}

```

## disassembly

```asm
0x18001a390  push    rbp
0x18001a392  push    rbx
0x18001a393  push    rsi
0x18001a394  push    rdi
0x18001a395  push    r12
0x18001a397  push    r13
0x18001a399  push    r14
0x18001a39b  push    r15
0x18001a39d  lea     rbp, [rsp-788h]
0x18001a3a5  sub     rsp, 888h
0x18001a3ac  mov     rax, cs:__security_cookie
0x18001a3b3  xor     rax, rsp
0x18001a3b6  mov     [rbp+7C0h+var_50], rax
0x18001a3bd  mov     r12, r9
0x18001a3c0  mov     edi, r8d
0x18001a3c3  mov     r13, rdx
0x18001a3c6  mov     rbx, rcx
0x18001a3c9  mov     r15, [rbp+7C0h+arg_20]
0x18001a3d0  lea     rdx, DebugInfoEvent
0x18001a3d7  mov     rcx, cs:eaphost_Context
0x18001a3de  call    cs:__imp_EtwEventEnabled
0x18001a3e4  xor     r14d, r14d
0x18001a3e7  test    al, al
0x18001a3e9  jz      short loc_18001A429
0x18001a3eb  mov     r9d, edi
0x18001a3ee  lea     r8, aRaseapquerycre; "RasEapQueryCredentialInputFields Entry:"...
0x18001a3f5  mov     edx, 800h; unsigned __int64
0x18001a3fa  lea     rcx, [rsp+8C0h+var_850]; char *
0x18001a3ff  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001a404  test    eax, eax
0x18001a406  js      short loc_18001A429
0x18001a408  cmp     cs:Microsoft_Windows_EapHostEnableBits, r14b
0x18001a40f  jge     short loc_18001A429
0x18001a411  lea     r8, [rsp+8C0h+var_850]
0x18001a416  lea     rdx, DebugInfoEvent
0x18001a41d  lea     rcx, eaphost_Context
0x18001a424  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a429  lea     rax, WPP_GLOBAL_Control
0x18001a430  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a437  cmp     rcx, rax
0x18001a43a  jz      short loc_18001A45A
0x18001a43c  test    byte ptr [rcx+1Ch], 4
0x18001a440  jz      short loc_18001A45A
0x18001a442  mov     edx, 0Dh
0x18001a447  mov     r9d, edi
0x18001a44a  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001a451  mov     rcx, [rcx+10h]
0x18001a455  call    WPP_SF_d
0x18001a45a  mov     dl, 1; bool
0x18001a45c  mov     rcx, [rbx+88h]; this
0x18001a463  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001a468  mov     rax, [rbx+88h]
0x18001a46f  mov     rsi, [rax+0D8h]
0x18001a476  test    rsi, rsi
0x18001a479  jnz     loc_18001A515
0x18001a47f  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x18001a486  jz      short loc_18001A4A2
0x18001a488  lea     r8, aQuerycredentia; "QueryCredentialInputFields"
0x18001a48f  lea     rdx, PeerFunctionNotSupported
0x18001a496  lea     rcx, eaphost_Context
0x18001a49d  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4a9  lea     rax, WPP_GLOBAL_Control
0x18001a4b0  cmp     rcx, rax
0x18001a4b3  jz      short loc_18001A4D0
0x18001a4b5  test    byte ptr [rcx+1Ch], 1
0x18001a4b9  jz      short loc_18001A4D0
0x18001a4bb  mov     edx, 0Eh
0x18001a4c0  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001a4c7  mov     rcx, [rcx+10h]
0x18001a4cb  call    WPP_SF_
0x18001a4d0  mov     cl, [rbx+10h]
0x18001a4d3  mov     byte ptr [rsp+8C0h+var_880+8], cl
0x18001a4d7  mov     eax, [rbx+14h]
0x18001a4da  mov     dword ptr [rsp+8C0h+var_880+0Ch], eax
0x18001a4de  mov     eax, [rbx+18h]
0x18001a4e1  mov     [rsp+50h], eax
0x18001a4e5  cmp     cl, 0FEh
0x18001a4e8  jz      short loc_18001A4EF
0x18001a4ea  mov     qword ptr [rsp+8C0h+var_880+0Ch], r14
0x18001a4ef  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001a4f6  mov     qword ptr [rsp+8C0h+var_880], rax
0x18001a4fb  mov     eax, [rbx+1Ch]
0x18001a4fe  mov     [rsp+8C0h+var_868], eax
0x18001a502  mov     ecx, 80420020h; unsigned int
0x18001a507  mov     r8d, ecx; unsigned int
0x18001a50a  lea     rdx, [rsp+8C0h+var_880]; struct EapHost::EapMethodType *
0x18001a50f  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001a515  mov     r14, [rax+0E8h]
0x18001a51c  xorps   xmm0, xmm0
0x18001a51f  movups  xmmword ptr [rsp+8C0h+var_860.dwVersion], xmm0
0x18001a524  mov     rcx, [r12+8]
0x18001a529  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001a52e  movzx   ecx, byte ptr [rbx+10h]
0x18001a532  lea     rdx, [rsp+8C0h+var_860]
0x18001a537  mov     [rsp+8C0h+var_898], rdx
0x18001a53c  mov     [rsp+8C0h+var_8A0], eax
0x18001a540  mov     r9, [r12]
0x18001a544  mov     r8d, edi
0x18001a547  mov     rdx, r13
0x18001a54a  mov     rax, rsi
0x18001a54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a552  mov     edi, eax
0x18001a554  xor     esi, esi
0x18001a556  test    eax, eax
0x18001a558  jz      loc_18001A627
0x18001a55e  lea     rdx, DebugErrorEvent
0x18001a565  mov     rcx, cs:eaphost_Context
0x18001a56c  call    cs:__imp_EtwEventEnabled
0x18001a572  test    al, al
0x18001a574  jz      short loc_18001A5B4
0x18001a576  mov     r9d, edi
0x18001a579  lea     r8, aRaseapquerycre_1; "RasEapQueryCredentialInputFields failed"...
0x18001a580  mov     edx, 800h; unsigned __int64
0x18001a585  lea     rcx, [rsp+8C0h+var_850]; char *
0x18001a58a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001a58f  test    eax, eax
0x18001a591  js      short loc_18001A5B4
0x18001a593  test    cs:byte_18004AF81, 8
0x18001a59a  jz      short loc_18001A5B4
0x18001a59c  lea     r8, [rsp+8C0h+var_850]
0x18001a5a1  lea     rdx, DebugErrorEvent
0x18001a5a8  lea     rcx, eaphost_Context
0x18001a5af  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a5b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5bb  lea     rax, WPP_GLOBAL_Control
0x18001a5c2  cmp     rcx, rax
0x18001a5c5  jz      short loc_18001A5E5
0x18001a5c7  test    byte ptr [rcx+1Ch], 1
0x18001a5cb  jz      short loc_18001A5E5
0x18001a5cd  mov     edx, 0Fh
0x18001a5d2  mov     r9d, edi
0x18001a5d5  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001a5dc  mov     rcx, [rcx+10h]
0x18001a5e0  call    WPP_SF_d
0x18001a5e5  mov     cl, [rbx+10h]
0x18001a5e8  mov     byte ptr [rsp+8C0h+var_880+8], cl
0x18001a5ec  mov     eax, [rbx+14h]
0x18001a5ef  mov     dword ptr [rsp+8C0h+var_880+0Ch], eax
0x18001a5f3  mov     eax, [rbx+18h]
0x18001a5f6  mov     [rsp+50h], eax
0x18001a5fa  cmp     cl, 0FEh
0x18001a5fd  jz      short loc_18001A604
0x18001a5ff  mov     qword ptr [rsp+8C0h+var_880+0Ch], rsi
0x18001a604  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001a60b  mov     qword ptr [rsp+8C0h+var_880], rax
0x18001a610  mov     eax, [rbx+1Ch]
0x18001a613  mov     [rsp+8C0h+var_868], eax
0x18001a617  mov     r8d, edi; unsigned int
0x18001a61a  lea     rdx, [rsp+8C0h+var_880]; struct EapHost::EapMethodType *
0x18001a61f  mov     ecx, edi; unsigned int
0x18001a621  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001a627  xorps   xmm0, xmm0
0x18001a62a  movups  [rsp+8C0h+var_880], xmm0
0x18001a62f  lea     rdx, [rsp+8C0h+var_860]
0x18001a634  lea     rcx, [rsp+8C0h+var_880]
0x18001a639  call    ?Assign@?$crt_ref@U_EAP_CONFIG_INPUT_FIELD_ARRAY@@@@QEAAXAEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; crt_ref<_EAP_CONFIG_INPUT_FIELD_ARRAY>::Assign(_EAP_CONFIG_INPUT_FIELD_ARRAY const &)
0x18001a63e  nop
0x18001a63f  movaps  xmm1, [rsp+8C0h+var_880]
0x18001a644  xorps   xmm0, xmm0
0x18001a647  movups  [rsp+8C0h+var_880], xmm0
0x18001a64c  movdqu  xmmword ptr [r15], xmm1
0x18001a651  mov     r8, r14; unsigned int (*)(unsigned __int8 *)
0x18001a654  lea     rdx, [rsp+8C0h+var_860]; struct _EAP_CONFIG_INPUT_FIELD_ARRAY *
0x18001a659  call    ?FreeEAPConfigInputFieldArray@LegacyEapMethodConfig@Peer@EapLm@@AEAAXPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@P6AKPEAE@Z@Z; EapLm::Peer::LegacyEapMethodConfig::FreeEAPConfigInputFieldArray(_EAP_CONFIG_INPUT_FIELD_ARRAY *,ulong (*)(uchar *))
0x18001a65e  lea     rdx, DebugInfoEvent
0x18001a665  mov     rcx, cs:eaphost_Context
0x18001a66c  call    cs:__imp_EtwEventEnabled
0x18001a672  test    al, al
0x18001a674  jz      short loc_18001A6B1
0x18001a676  lea     r8, aRaseapquerycre_0; "RasEapQueryCredentialInputFields Exit"
0x18001a67d  mov     edx, 800h; unsigned __int64
0x18001a682  lea     rcx, [rsp+8C0h+var_850]; char *
0x18001a687  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001a68c  test    eax, eax
0x18001a68e  js      short loc_18001A6B1
0x18001a690  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x18001a697  jge     short loc_18001A6B1
0x18001a699  lea     r8, [rsp+8C0h+var_850]
0x18001a69e  lea     rdx, DebugInfoEvent
0x18001a6a5  lea     rcx, eaphost_Context
0x18001a6ac  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a6b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6b8  lea     rax, WPP_GLOBAL_Control
0x18001a6bf  cmp     rcx, rax
0x18001a6c2  jz      short loc_18001A6E0
0x18001a6c4  test    byte ptr [rcx+1Ch], 4
0x18001a6c8  jz      short loc_18001A6E0
0x18001a6ca  mov     edx, 10h
0x18001a6cf  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001a6d6  mov     rcx, [rcx+10h]
0x18001a6da  call    WPP_SF_
0x18001a6df  nop
0x18001a6e0  lea     rcx, [rsp+8C0h+var_880]
0x18001a6e5  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; Free<HeapAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)
0x18001a6ea  mov     rcx, [rbp+7C0h+var_50]
0x18001a6f1  xor     rcx, rsp; StackCookie
0x18001a6f4  call    __security_check_cookie
0x18001a6f9  add     rsp, 888h
0x18001a700  pop     r15
0x18001a702  pop     r14
0x18001a704  pop     r13
0x18001a706  pop     r12
0x18001a708  pop     rdi
0x18001a709  pop     rsi
0x18001a70a  pop     rbx
0x18001a70b  pop     rbp
0x18001a70c  retn
```
