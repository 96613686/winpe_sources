# EapLm::Peer::EapMethodConfig::QueryUserBlobFromCredentialInputFields(void *,uint,ConstBuffer const &,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,TempBuffer<0> &)

- ea: `0x18001dd00`
- end: `0x18001df98`
- name: `?QueryUserBlobFromCredentialInputFields@EapMethodConfig@Peer@EapLm@@UEAAXPEAXIAEBUConstBuffer@@PEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `664`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000ec84`
- `0x1800126f8`
- `0x1800154dc`
- `0x180016400`
- `0x1800177bc`
- `0x18001b154`
- `0x18001dd00`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001dd5d`
- `ntdll!EtwEventEnabled` at `0x18001df04`
- `ntdll!EtwEventEnabled` at `0x18001dd5d`
- `ntdll!EtwEventEnabled` at `0x18001df04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_UNKNOWN **__fastcall EapLm::Peer::EapMethodConfig::QueryUserBlobFromCredentialInputFields(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6)
{
  int v8; // eax
  int v9; // eax
  _QWORD *v10; // rax
  __int64 (__fastcall *v11)(__int64, __int128 *, _QWORD, _QWORD, __int64, __int64, unsigned int *, const void **, struct _EAP_ERROR **); // rdi
  void (__fastcall *v12)(const void *); // r13
  void (__fastcall *v13)(struct _EAP_ERROR *); // r15
  __int64 v14; // rbx
  unsigned int v15; // eax
  unsigned int v16; // eax
  const wchar_t *v17; // rdx
  _UNKNOWN **result; // rax
  unsigned int v19; // [rsp+50h] [rbp-B0h] BYREF
  const void *v20; // [rsp+58h] [rbp-A8h] BYREF
  struct _EAP_ERROR *v21; // [rsp+60h] [rbp-A0h] BYREF
  __int64 *v22; // [rsp+68h] [rbp-98h]
  __int128 v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h]
  char v25[96]; // [rsp+90h] [rbp-70h] BYREF
  char v26[2048]; // [rsp+F0h] [rbp-10h] BYREF

  v22 = a4;
  v24 = a2;
  *(_QWORD *)&v23 = a1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    v8 = a5 ? *(_DWORD *)(a5 + 4) : 0;
    if ( (int)StringCchPrintfA(
                v26,
                0x800u,
                "EapPeerQueryUserBlobFromCredentialInputFields Entry:\n flags(%d), NumInputFields(%d)",
                a3,
                v8) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v26);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( a5 )
      v9 = *(_DWORD *)(a5 + 4);
    else
      v9 = 0;
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids, a3, v9);
  }
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 144), 0);
  v10 = *(_QWORD **)(a1 + 144);
  v11 = (__int64 (__fastcall *)(__int64, __int128 *, _QWORD, _QWORD, __int64, __int64, unsigned int *, const void **, struct _EAP_ERROR **))v10[27];
  v12 = (void (__fastcall *)(const void *))v10[29];
  v13 = (void (__fastcall *)(struct _EAP_ERROR *))v10[28];
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v19 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*(_QWORD *)(a6 + 8));
  v20 = *(const void **)a6;
  v14 = *v22;
  v15 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v22[1]);
  v23 = *(_OWORD *)(v23 + 16);
  v16 = v11(v24, &v23, a3, v15, v14, a5, &v19, &v20, &v21);
  if ( v16 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v25, v21, v16);
    v13(v21);
    EapHost::EapException::Throw(
      L"EapPeerQueryUserBlobFromCredentialInputFields",
      v17,
      (const struct EapHost::EapError *)v25);
  }
  TempBuffer<0>::Assign(a6, v19, v20);
  v12(v20);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v26, 0x800u, "EapPeerQueryUserBlobFromCredentialInputFields Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v26);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          17,
                          WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18001dd00  push    rbp
0x18001dd02  push    rbx
0x18001dd03  push    rsi
0x18001dd04  push    rdi
0x18001dd05  push    r12
0x18001dd07  push    r13
0x18001dd09  push    r14
0x18001dd0b  push    r15
0x18001dd0d  lea     rbp, [rsp-808h]
0x18001dd15  sub     rsp, 908h
0x18001dd1c  mov     rax, cs:__security_cookie
0x18001dd23  xor     rax, rsp
0x18001dd26  mov     [rbp+840h+var_50], rax
0x18001dd2d  mov     [rsp+940h+var_8D8], r9
0x18001dd32  mov     r14d, r8d
0x18001dd35  mov     [rbp+840h+var_8C0], rdx
0x18001dd39  mov     rbx, rcx
0x18001dd3c  mov     qword ptr [rsp+940h+var_8D0], rcx
0x18001dd41  mov     rsi, [rbp+840h+arg_20]
0x18001dd48  mov     r12, [rbp+840h+arg_28]
0x18001dd4f  lea     rdx, DebugInfoEvent
0x18001dd56  mov     rcx, cs:eaphost_Context
0x18001dd5d  call    cs:__imp_EtwEventEnabled
0x18001dd63  test    al, al
0x18001dd65  jz      short loc_18001DDB3
0x18001dd67  test    rsi, rsi
0x18001dd6a  jz      short loc_18001DD71
0x18001dd6c  mov     eax, [rsi+4]
0x18001dd6f  jmp     short loc_18001DD73
0x18001dd71  xor     eax, eax
0x18001dd73  mov     dword ptr [rsp+940h+var_920], eax
0x18001dd77  mov     r9d, r14d
0x18001dd7a  lea     r8, aEappeerqueryus; "EapPeerQueryUserBlobFromCredentialInput"...
0x18001dd81  mov     edx, 800h; unsigned __int64
0x18001dd86  lea     rcx, [rbp+840h+var_850]; char *
0x18001dd8a  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001dd8f  test    eax, eax
0x18001dd91  js      short loc_18001DDB3
0x18001dd93  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001dd9a  jge     short loc_18001DDB3
0x18001dd9c  lea     r8, [rbp+840h+var_850]
0x18001dda0  lea     rdx, DebugInfoEvent
0x18001dda7  lea     rcx, eaphost_Context
0x18001ddae  call    McTemplateU0s_EtwEventWriteTransfer
0x18001ddb3  lea     rax, WPP_GLOBAL_Control
0x18001ddba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ddc1  cmp     rcx, rax
0x18001ddc4  jz      short loc_18001DDF4
0x18001ddc6  test    byte ptr [rcx+1Ch], 4
0x18001ddca  jz      short loc_18001DDF4
0x18001ddcc  test    rsi, rsi
0x18001ddcf  jz      short loc_18001DDD6
0x18001ddd1  mov     eax, [rsi+4]
0x18001ddd4  jmp     short loc_18001DDD8
0x18001ddd6  xor     eax, eax
0x18001ddd8  mov     edx, 10h
0x18001dddd  mov     dword ptr [rsp+940h+var_920], eax
0x18001dde1  mov     r9d, r14d
0x18001dde4  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001ddeb  mov     rcx, [rcx+10h]
0x18001ddef  call    WPP_SF_dd
0x18001ddf4  xor     edx, edx; bool
0x18001ddf6  mov     rcx, [rbx+90h]; this
0x18001ddfd  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001de02  mov     rax, [rbx+90h]
0x18001de09  mov     rdi, [rax+0D8h]
0x18001de10  mov     r13, [rax+0E8h]
0x18001de17  mov     r15, [rax+0E0h]
0x18001de1e  xor     eax, eax
0x18001de20  mov     [rsp+940h+var_8F0], eax
0x18001de24  mov     [rsp+940h+var_8E8], rax
0x18001de29  mov     [rsp+940h+var_8E0], rax
0x18001de2e  mov     rcx, [r12+8]
0x18001de33  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001de38  mov     [rsp+940h+var_8F0], eax
0x18001de3c  mov     rax, [r12]
0x18001de40  mov     [rsp+940h+var_8E8], rax
0x18001de45  mov     rax, [rsp+940h+var_8D8]
0x18001de4a  mov     rbx, [rax]
0x18001de4d  mov     rcx, [rax+8]
0x18001de51  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001de56  mov     rcx, qword ptr [rsp+940h+var_8D0]
0x18001de5b  movups  xmm0, xmmword ptr [rcx+10h]
0x18001de5f  movdqu  [rsp+940h+var_8D0], xmm0
0x18001de65  lea     rcx, [rsp+940h+var_8E0]
0x18001de6a  mov     [rsp+940h+var_900], rcx
0x18001de6f  lea     rcx, [rsp+940h+var_8E8]
0x18001de74  mov     [rsp+940h+var_908], rcx
0x18001de79  lea     rcx, [rsp+940h+var_8F0]
0x18001de7e  mov     [rsp+940h+var_910], rcx
0x18001de83  mov     [rsp+940h+var_918], rsi
0x18001de88  mov     [rsp+940h+var_920], rbx
0x18001de8d  mov     r9d, eax
0x18001de90  mov     r8d, r14d
0x18001de93  lea     rdx, [rsp+940h+var_8D0]
0x18001de98  mov     rcx, [rbp+840h+var_8C0]
0x18001de9c  mov     rax, rdi
0x18001de9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dea4  test    eax, eax
0x18001dea6  jz      short loc_18001DED8
0x18001dea8  mov     r8d, eax; unsigned int
0x18001deab  mov     rdx, [rsp+940h+var_8E0]; struct _EAP_ERROR *
0x18001deb0  lea     rcx, [rbp+840h+var_8B0]; this
0x18001deb4  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001deb9  nop
0x18001deba  mov     rcx, [rsp+940h+var_8E0]
0x18001debf  mov     rax, r15
0x18001dec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dec7  lea     r8, [rbp+840h+var_8B0]; struct EapHost::EapError *
0x18001decb  lea     rcx, aEappeerqueryus_0; "EapPeerQueryUserBlobFromCredentialInput"...
0x18001ded2  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001ded8  mov     edx, [rsp+940h+var_8F0]
0x18001dedc  mov     r8, [rsp+940h+var_8E8]
0x18001dee1  mov     rcx, r12
0x18001dee4  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001dee9  mov     rcx, [rsp+940h+var_8E8]
0x18001deee  mov     rax, r13
0x18001def1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001def6  lea     rdx, DebugInfoEvent
0x18001defd  mov     rcx, cs:eaphost_Context
0x18001df04  call    cs:__imp_EtwEventEnabled
0x18001df0a  test    al, al
0x18001df0c  jz      short loc_18001DF47
0x18001df0e  lea     r8, aEappeerqueryus_1; "EapPeerQueryUserBlobFromCredentialInput"...
0x18001df15  mov     edx, 800h; unsigned __int64
0x18001df1a  lea     rcx, [rbp+840h+var_850]; char *
0x18001df1e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001df23  test    eax, eax
0x18001df25  js      short loc_18001DF47
0x18001df27  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001df2e  jge     short loc_18001DF47
0x18001df30  lea     r8, [rbp+840h+var_850]
0x18001df34  lea     rdx, DebugInfoEvent
0x18001df3b  lea     rcx, eaphost_Context
0x18001df42  call    McTemplateU0s_EtwEventWriteTransfer
0x18001df47  mov     rcx, cs:WPP_GLOBAL_Control
0x18001df4e  lea     rax, WPP_GLOBAL_Control
0x18001df55  cmp     rcx, rax
0x18001df58  jz      short loc_18001DF75
0x18001df5a  test    byte ptr [rcx+1Ch], 4
0x18001df5e  jz      short loc_18001DF75
0x18001df60  mov     edx, 11h
0x18001df65  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001df6c  mov     rcx, [rcx+10h]
0x18001df70  call    WPP_SF_
0x18001df75  mov     rcx, [rbp+840h+var_50]
0x18001df7c  xor     rcx, rsp; StackCookie
0x18001df7f  call    __security_check_cookie
0x18001df84  add     rsp, 908h
0x18001df8b  pop     r15
0x18001df8d  pop     r14
0x18001df8f  pop     r13
0x18001df91  pop     r12
0x18001df93  pop     rdi
0x18001df94  pop     rsi
0x18001df95  pop     rbx
0x18001df96  pop     rbp
0x18001df97  retn
```
