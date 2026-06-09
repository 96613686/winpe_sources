# EapLm::Peer::LegacyEapMethodConfig::QueryUserBlobFromCredentialInputFields(void *,uint,ConstBuffer const &,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,TempBuffer<0> &)

- ea: `0x18001ae60`
- end: `0x18001b14e`
- name: `?QueryUserBlobFromCredentialInputFields@LegacyEapMethodConfig@Peer@EapLm@@UEAAXPEAXIAEBUConstBuffer@@PEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `750`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x1800126f8`
- `0x18001549c`
- `0x180016400`
- `0x18001ae60`
- `0x18001b154`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001aeba`
- `ntdll!EtwEventEnabled` at `0x18001afd6`
- `ntdll!EtwEventEnabled` at `0x18001b0ba`
- `ntdll!EtwEventEnabled` at `0x18001aeba`
- `ntdll!EtwEventEnabled` at `0x18001afd6`
- `ntdll!EtwEventEnabled` at `0x18001b0ba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall EapLm::Peer::LegacyEapMethodConfig::QueryUserBlobFromCredentialInputFields(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v10; // rax
  __int64 (__fastcall *v11)(_QWORD, __int64, _QWORD, _QWORD, int, __int64, const void **, unsigned int *); // rbx
  void (__fastcall *v12)(const void *); // r15
  int v13; // eax
  unsigned int v14; // ebx
  _UNKNOWN **result; // rax
  unsigned int v16; // [rsp+50h] [rbp-B0h] BYREF
  const void *v17; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h]
  void **v19; // [rsp+68h] [rbp-98h] BYREF
  char v20; // [rsp+70h] [rbp-90h]
  __int64 v21; // [rsp+74h] [rbp-8Ch]
  int v22; // [rsp+80h] [rbp-80h]
  char v23[2048]; // [rsp+90h] [rbp-70h] BYREF

  v18 = a5;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v23, 0x800u, "RasEapQueryUserBlobFromCredentialInputFields Entry:\n flags(%d)", a3) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v23);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, a3);
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 144), 0);
  v10 = *(_QWORD *)(a1 + 144);
  v11 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, int, __int64, const void **, unsigned int *))(v10 + 216);
  v12 = *(void (__fastcall **)(const void *))(v10 + 232);
  v16 = 0;
  v17 = 0;
  v16 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*(_QWORD *)(a6 + 8));
  v17 = *(const void **)a6;
  v13 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  v14 = v11(*(unsigned __int8 *)(a1 + 16), a2, a3, *a4, v13, v18, &v17, &v16);
  if ( v14 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v23, 0x800u, "RasEapQueryUserBlobFromCredentialInputFields failed %d", v14) >= 0
      && (byte_18004AF81 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugErrorEvent, v23);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v14);
    v20 = *(_BYTE *)(a1 + 16);
    v21 = *(_QWORD *)(a1 + 20);
    if ( v20 != -2 )
      v21 = 0;
    v19 = &EapHost::EapMethodType::`vftable';
    v22 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(v14, (const struct EapHost::EapMethodType *)&v19, v14);
  }
  TempBuffer<0>::Assign(a6, v16, v17);
  v12(v17);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v23, 0x800u, "RasEapQueryUserBlobFromCredentialInputFields Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v23);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          19,
                          WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18001ae60  push    rbp
0x18001ae62  push    rbx
0x18001ae63  push    rsi
0x18001ae64  push    rdi
0x18001ae65  push    r12
0x18001ae67  push    r13
0x18001ae69  push    r14
0x18001ae6b  push    r15
0x18001ae6d  lea     rbp, [rsp-7A8h]
0x18001ae75  sub     rsp, 8A8h
0x18001ae7c  mov     rax, cs:__security_cookie
0x18001ae83  xor     rax, rsp
0x18001ae86  mov     [rbp+7E0h+var_50], rax
0x18001ae8d  mov     r12, r9
0x18001ae90  mov     esi, r8d
0x18001ae93  mov     r13, rdx
0x18001ae96  mov     rdi, rcx
0x18001ae99  mov     rax, [rbp+7E0h+arg_20]
0x18001aea0  mov     [rsp+8E0h+var_880], rax
0x18001aea5  mov     r14, [rbp+7E0h+arg_28]
0x18001aeac  lea     rdx, DebugInfoEvent
0x18001aeb3  mov     rcx, cs:eaphost_Context
0x18001aeba  call    cs:__imp_EtwEventEnabled
0x18001aec0  test    al, al
0x18001aec2  jz      short loc_18001AF00
0x18001aec4  mov     r9d, esi
0x18001aec7  lea     r8, aRaseapqueryuse_1; "RasEapQueryUserBlobFromCredentialInputF"...
0x18001aece  mov     edx, 800h; unsigned __int64
0x18001aed3  lea     rcx, [rbp+7E0h+var_850]; char *
0x18001aed7  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001aedc  test    eax, eax
0x18001aede  js      short loc_18001AF00
0x18001aee0  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001aee7  jge     short loc_18001AF00
0x18001aee9  lea     r8, [rbp+7E0h+var_850]
0x18001aeed  lea     rdx, DebugInfoEvent
0x18001aef4  lea     rcx, eaphost_Context
0x18001aefb  call    McTemplateU0s_EtwEventWriteTransfer
0x18001af00  lea     rax, WPP_GLOBAL_Control
0x18001af07  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af0e  cmp     rcx, rax
0x18001af11  jz      short loc_18001AF31
0x18001af13  test    byte ptr [rcx+1Ch], 4
0x18001af17  jz      short loc_18001AF31
0x18001af19  mov     edx, 11h
0x18001af1e  mov     r9d, esi
0x18001af21  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001af28  mov     rcx, [rcx+10h]
0x18001af2c  call    WPP_SF_d
0x18001af31  xor     edx, edx; bool
0x18001af33  mov     rcx, [rdi+90h]; this
0x18001af3a  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001af3f  mov     rax, [rdi+90h]
0x18001af46  mov     rbx, [rax+0D8h]
0x18001af4d  mov     r15, [rax+0E8h]
0x18001af54  mov     [rsp+8E0h+var_890], 0
0x18001af5c  mov     [rsp+8E0h+var_888], 0
0x18001af65  mov     rcx, [r14+8]
0x18001af69  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001af6e  mov     [rsp+8E0h+var_890], eax
0x18001af72  mov     rax, [r14]
0x18001af75  mov     [rsp+8E0h+var_888], rax
0x18001af7a  mov     rcx, [r12+8]
0x18001af7f  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001af84  movzx   ecx, byte ptr [rdi+10h]
0x18001af88  lea     rdx, [rsp+8E0h+var_890]
0x18001af8d  mov     [rsp+8E0h+var_8A8], rdx
0x18001af92  lea     rdx, [rsp+8E0h+var_888]
0x18001af97  mov     [rsp+8E0h+var_8B0], rdx
0x18001af9c  mov     rdx, [rsp+8E0h+var_880]
0x18001afa1  mov     [rsp+8E0h+var_8B8], rdx
0x18001afa6  mov     [rsp+8E0h+var_8C0], eax
0x18001afaa  mov     r9, [r12]
0x18001afae  mov     r8d, esi
0x18001afb1  mov     rdx, r13
0x18001afb4  mov     rax, rbx
0x18001afb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afbc  mov     ebx, eax
0x18001afbe  xor     esi, esi
0x18001afc0  test    eax, eax
0x18001afc2  jz      loc_18001B08E
0x18001afc8  lea     rdx, DebugErrorEvent
0x18001afcf  mov     rcx, cs:eaphost_Context
0x18001afd6  call    cs:__imp_EtwEventEnabled
0x18001afdc  test    al, al
0x18001afde  jz      short loc_18001B01C
0x18001afe0  mov     r9d, ebx
0x18001afe3  lea     r8, aRaseapqueryuse_2; "RasEapQueryUserBlobFromCredentialInputF"...
0x18001afea  mov     edx, 800h; unsigned __int64
0x18001afef  lea     rcx, [rbp+7E0h+var_850]; char *
0x18001aff3  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001aff8  test    eax, eax
0x18001affa  js      short loc_18001B01C
0x18001affc  test    cs:byte_18004AF81, 8
0x18001b003  jz      short loc_18001B01C
0x18001b005  lea     r8, [rbp+7E0h+var_850]
0x18001b009  lea     rdx, DebugErrorEvent
0x18001b010  lea     rcx, eaphost_Context
0x18001b017  call    McTemplateU0s_EtwEventWriteTransfer
0x18001b01c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b023  lea     rax, WPP_GLOBAL_Control
0x18001b02a  cmp     rcx, rax
0x18001b02d  jz      short loc_18001B04D
0x18001b02f  test    byte ptr [rcx+1Ch], 1
0x18001b033  jz      short loc_18001B04D
0x18001b035  mov     edx, 12h
0x18001b03a  mov     r9d, ebx
0x18001b03d  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001b044  mov     rcx, [rcx+10h]
0x18001b048  call    WPP_SF_d
0x18001b04d  mov     cl, [rdi+10h]
0x18001b050  mov     [rsp+8E0h+var_870], cl
0x18001b054  mov     eax, [rdi+14h]
0x18001b057  mov     dword ptr [rsp+8E0h+var_86C], eax
0x18001b05b  mov     eax, [rdi+18h]
0x18001b05e  mov     dword ptr [rsp+8E0h+var_86C+4], eax
0x18001b062  cmp     cl, 0FEh
0x18001b065  jz      short loc_18001B06C
0x18001b067  mov     [rsp+8E0h+var_86C], rsi
0x18001b06c  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001b073  mov     [rsp+8E0h+var_878], rax
0x18001b078  mov     eax, [rdi+1Ch]
0x18001b07b  mov     [rbp+7E0h+var_860], eax
0x18001b07e  mov     r8d, ebx; unsigned int
0x18001b081  lea     rdx, [rsp+8E0h+var_878]; struct EapHost::EapMethodType *
0x18001b086  mov     ecx, ebx; unsigned int
0x18001b088  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001b08e  mov     edx, [rsp+8E0h+var_890]
0x18001b092  mov     r8, [rsp+8E0h+var_888]
0x18001b097  mov     rcx, r14
0x18001b09a  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001b09f  mov     rcx, [rsp+8E0h+var_888]
0x18001b0a4  mov     rax, r15
0x18001b0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b0ac  lea     rdx, DebugInfoEvent
0x18001b0b3  mov     rcx, cs:eaphost_Context
0x18001b0ba  call    cs:__imp_EtwEventEnabled
0x18001b0c0  test    al, al
0x18001b0c2  jz      short loc_18001B0FD
0x18001b0c4  lea     r8, aRaseapqueryuse; "RasEapQueryUserBlobFromCredentialInputF"...
0x18001b0cb  mov     edx, 800h; unsigned __int64
0x18001b0d0  lea     rcx, [rbp+7E0h+var_850]; char *
0x18001b0d4  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001b0d9  test    eax, eax
0x18001b0db  js      short loc_18001B0FD
0x18001b0dd  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x18001b0e4  jge     short loc_18001B0FD
0x18001b0e6  lea     r8, [rbp+7E0h+var_850]
0x18001b0ea  lea     rdx, DebugInfoEvent
0x18001b0f1  lea     rcx, eaphost_Context
0x18001b0f8  call    McTemplateU0s_EtwEventWriteTransfer
0x18001b0fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b104  lea     rax, WPP_GLOBAL_Control
0x18001b10b  cmp     rcx, rax
0x18001b10e  jz      short loc_18001B12B
0x18001b110  test    byte ptr [rcx+1Ch], 4
0x18001b114  jz      short loc_18001B12B
0x18001b116  mov     edx, 13h
0x18001b11b  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x18001b122  mov     rcx, [rcx+10h]
0x18001b126  call    WPP_SF_
0x18001b12b  mov     rcx, [rbp+7E0h+var_50]
0x18001b132  xor     rcx, rsp; StackCookie
0x18001b135  call    __security_check_cookie
0x18001b13a  add     rsp, 8A8h
0x18001b141  pop     r15
0x18001b143  pop     r14
0x18001b145  pop     r13
0x18001b147  pop     r12
0x18001b149  pop     rdi
0x18001b14a  pop     rsi
0x18001b14b  pop     rbx
0x18001b14c  pop     rbp
0x18001b14d  retn
```
