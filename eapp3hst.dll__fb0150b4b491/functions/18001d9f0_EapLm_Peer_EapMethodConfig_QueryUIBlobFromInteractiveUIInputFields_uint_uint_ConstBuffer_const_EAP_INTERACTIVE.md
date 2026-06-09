# EapLm::Peer::EapMethodConfig::QueryUIBlobFromInteractiveUIInputFields(uint,uint,ConstBuffer const &,_EAP_INTERACTIVE_UI_DATA const *,TempBuffer<0> &)

- ea: `0x18001d9f0`
- end: `0x18001dcf0`
- name: `?QueryUIBlobFromInteractiveUIInputFields@EapMethodConfig@Peer@EapLm@@UEAAXIIAEBUConstBuffer@@PEBU_EAP_INTERACTIVE_UI_DATA@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `768`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x1800126f8`
- `0x18001549c`
- `0x1800154dc`
- `0x180016400`
- `0x1800177bc`
- `0x18001b154`
- `0x18001d9f0`
- `0x18001e008`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001da4e`
- `ntdll!EtwEventEnabled` at `0x18001dc5c`
- `ntdll!EtwEventEnabled` at `0x18001da4e`
- `ntdll!EtwEventEnabled` at `0x18001dc5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_UNKNOWN **__fastcall EapLm::Peer::EapMethodConfig::QueryUIBlobFromInteractiveUIInputFields(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v10; // r8
  _QWORD *v11; // rax
  __int64 (__fastcall *v12)(_QWORD, _QWORD, _QWORD, __int64, __int64, unsigned int *, const void **, struct _EAP_ERROR **, _QWORD); // r15
  void (__fastcall *v13)(const void *); // r13
  void (__fastcall *v14)(struct _EAP_ERROR *); // r12
  __int64 v15; // rbx
  unsigned int v16; // eax
  unsigned int v17; // eax
  const wchar_t *v18; // rdx
  _UNKNOWN **result; // rax
  unsigned int v20; // [rsp+50h] [rbp-B0h] BYREF
  struct _EAP_ERROR *v21; // [rsp+58h] [rbp-A8h] BYREF
  const void *v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h]
  __int64 v24; // [rsp+70h] [rbp-90h]
  void **v25; // [rsp+78h] [rbp-88h] BYREF
  char v26; // [rsp+80h] [rbp-80h]
  __int64 v27; // [rsp+84h] [rbp-7Ch]
  int v28; // [rsp+90h] [rbp-70h]
  char v29[96]; // [rsp+A0h] [rbp-60h] BYREF
  char v30[2048]; // [rsp+100h] [rbp+0h] BYREF

  v23 = a5;
  v24 = a6;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v30,
              0x800u,
              "EapPeerQueryUIBlobFromInteractiveUIInputFields Entry:\n version(%d), flags(%d), Context data (%Id) bytes",
              a2,
              a3,
              a4[1]) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v30);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_ddP(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v10, a2, a3, a4[1]);
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 168), 1);
  v11 = *(_QWORD **)(a1 + 168);
  v12 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64, __int64, unsigned int *, const void **, struct _EAP_ERROR **, _QWORD))v11[27];
  if ( !v12 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(
        &eaphost_Context,
        (__int64)PeerFunctionNotSupported,
        "QueryUIBlobFromInteractiveUIInputFields");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
    v26 = *(_BYTE *)(a1 + 16);
    v27 = *(_QWORD *)(a1 + 20);
    if ( v26 != -2 )
      v27 = 0;
    v25 = &EapHost::EapMethodType::`vftable';
    v28 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)&v25, 0x80420020);
  }
  v13 = (void (__fastcall *)(const void *))v11[29];
  v14 = (void (__fastcall *)(struct _EAP_ERROR *))v11[28];
  v20 = 0;
  v22 = 0;
  v21 = 0;
  v15 = *a4;
  v16 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(a4[1]);
  v17 = v12(a2, a3, v16, v15, v23, &v20, &v22, &v21, 0);
  if ( v17 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v29, v21, v17);
    v14(v21);
    EapHost::EapException::Throw(L"EapPeerQueryInteractiveUIInputFields", v18, (const struct EapHost::EapError *)v29);
  }
  TempBuffer<0>::Assign(v24, v20, v22);
  v13(v22);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v30, 0x800u, "EapPeerQueryUIBlobFromInteractiveUIInputFields Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v30);
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    return (_UNKNOWN **)WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          27,
                          WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
  return result;
}

```

## disassembly

```asm
0x18001d9f0  push    rbp
0x18001d9f2  push    rbx
0x18001d9f3  push    rsi
0x18001d9f4  push    rdi
0x18001d9f5  push    r12
0x18001d9f7  push    r13
0x18001d9f9  push    r14
0x18001d9fb  push    r15
0x18001d9fd  lea     rbp, [rsp-818h]
0x18001da05  sub     rsp, 918h
0x18001da0c  mov     rax, cs:__security_cookie
0x18001da13  xor     rax, rsp
0x18001da16  mov     [rbp+850h+var_50], rax
0x18001da1d  mov     rdi, r9
0x18001da20  mov     r14d, r8d
0x18001da23  mov     esi, edx
0x18001da25  mov     rbx, rcx
0x18001da28  mov     rax, [rbp+850h+arg_20]
0x18001da2f  mov     [rsp+950h+var_8E8], rax
0x18001da34  mov     rax, [rbp+850h+arg_28]
0x18001da3b  mov     [rsp+950h+var_8E0], rax
0x18001da40  lea     rdx, DebugInfoEvent
0x18001da47  mov     rcx, cs:eaphost_Context
0x18001da4e  call    cs:__imp_EtwEventEnabled
0x18001da54  xor     r12d, r12d
0x18001da57  test    al, al
0x18001da59  jz      short loc_18001DAA5
0x18001da5b  mov     rax, [rdi+8]
0x18001da5f  mov     [rsp+950h+var_928], rax
0x18001da64  mov     dword ptr [rsp+950h+var_930], r14d
0x18001da69  mov     r9d, esi
0x18001da6c  lea     r8, aEappeerqueryui_1; "EapPeerQueryUIBlobFromInteractiveUIInpu"...
0x18001da73  mov     edx, 800h; unsigned __int64
0x18001da78  lea     rcx, [rbp+850h+var_850]; char *
0x18001da7c  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001da81  test    eax, eax
0x18001da83  js      short loc_18001DAA5
0x18001da85  cmp     cs:Microsoft_Windows_EapHostEnableBits, r12b
0x18001da8c  jge     short loc_18001DAA5
0x18001da8e  lea     r8, [rbp+850h+var_850]
0x18001da92  lea     rdx, DebugInfoEvent
0x18001da99  lea     rcx, eaphost_Context
0x18001daa0  call    McTemplateU0s_EtwEventWriteTransfer
0x18001daa5  lea     r13, WPP_GLOBAL_Control
0x18001daac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dab3  cmp     rcx, r13
0x18001dab6  jz      short loc_18001DADD
0x18001dab8  test    byte ptr [rcx+1Ch], 4
0x18001dabc  jz      short loc_18001DADD
0x18001dabe  mov     edx, 19h
0x18001dac3  mov     rax, [rdi+8]
0x18001dac7  mov     [rsp+950h+var_928], rax
0x18001dacc  mov     dword ptr [rsp+950h+var_930], r14d
0x18001dad1  mov     r9d, esi
0x18001dad4  mov     rcx, [rcx+10h]
0x18001dad8  call    WPP_SF_ddP
0x18001dadd  mov     dl, 1; bool
0x18001dadf  mov     rcx, [rbx+0A8h]; this
0x18001dae6  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001daeb  mov     rax, [rbx+0A8h]
0x18001daf2  mov     r15, [rax+0D8h]
0x18001daf9  test    r15, r15
0x18001dafc  jnz     loc_18001DB8C
0x18001db02  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x18001db09  jz      short loc_18001DB25
0x18001db0b  lea     r8, aQueryuiblobfro; "QueryUIBlobFromInteractiveUIInputFields"
0x18001db12  lea     rdx, PeerFunctionNotSupported
0x18001db19  lea     rcx, eaphost_Context
0x18001db20  call    McTemplateU0s_EtwEventWriteTransfer
0x18001db25  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db2c  cmp     rcx, r13
0x18001db2f  jz      short loc_18001DB4C
0x18001db31  test    byte ptr [rcx+1Ch], 1
0x18001db35  jz      short loc_18001DB4C
0x18001db37  mov     edx, 1Ah
0x18001db3c  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001db43  mov     rcx, [rcx+10h]
0x18001db47  call    WPP_SF_
0x18001db4c  mov     cl, [rbx+10h]
0x18001db4f  mov     [rbp+850h+var_8D0], cl
0x18001db52  mov     eax, [rbx+14h]
0x18001db55  mov     dword ptr [rbp+850h+var_8CC], eax
0x18001db58  mov     eax, [rbx+18h]
0x18001db5b  mov     dword ptr [rbp+850h+var_8CC+4], eax
0x18001db5e  cmp     cl, 0FEh
0x18001db61  jz      short loc_18001DB67
0x18001db63  mov     [rbp+850h+var_8CC], r12
0x18001db67  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001db6e  mov     [rsp+950h+var_8D8], rax
0x18001db73  mov     eax, [rbx+1Ch]
0x18001db76  mov     [rbp+850h+var_8C0], eax
0x18001db79  mov     ecx, 80420020h; unsigned int
0x18001db7e  mov     r8d, ecx; unsigned int
0x18001db81  lea     rdx, [rsp+950h+var_8D8]; struct EapHost::EapMethodType *
0x18001db86  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001db8c  mov     r13, [rax+0E8h]
0x18001db93  mov     r12, [rax+0E0h]
0x18001db9a  xor     eax, eax
0x18001db9c  mov     [rsp+950h+var_900], eax
0x18001dba0  mov     [rsp+950h+var_8F0], rax
0x18001dba5  mov     [rsp+950h+var_8F8], rax
0x18001dbaa  mov     rbx, [rdi]
0x18001dbad  mov     rcx, [rdi+8]
0x18001dbb1  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001dbb6  mov     [rsp+950h+var_910], 0
0x18001dbbf  lea     rcx, [rsp+950h+var_8F8]
0x18001dbc4  mov     [rsp+950h+var_918], rcx
0x18001dbc9  lea     rcx, [rsp+950h+var_8F0]
0x18001dbce  mov     [rsp+950h+var_920], rcx
0x18001dbd3  lea     rcx, [rsp+950h+var_900]
0x18001dbd8  mov     [rsp+950h+var_928], rcx
0x18001dbdd  mov     rcx, [rsp+950h+var_8E8]
0x18001dbe2  mov     [rsp+950h+var_930], rcx
0x18001dbe7  mov     r9, rbx
0x18001dbea  mov     r8d, eax
0x18001dbed  mov     edx, r14d
0x18001dbf0  mov     ecx, esi
0x18001dbf2  mov     rax, r15
0x18001dbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbfa  test    eax, eax
0x18001dbfc  jz      short loc_18001DC2E
0x18001dbfe  mov     r8d, eax; unsigned int
0x18001dc01  mov     rdx, [rsp+950h+var_8F8]; struct _EAP_ERROR *
0x18001dc06  lea     rcx, [rbp+850h+var_8B0]; this
0x18001dc0a  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001dc0f  nop
0x18001dc10  mov     rcx, [rsp+950h+var_8F8]
0x18001dc15  mov     rax, r12
0x18001dc18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc1d  lea     r8, [rbp+850h+var_8B0]; struct EapHost::EapError *
0x18001dc21  lea     rcx, aEappeerqueryin_0; "EapPeerQueryInteractiveUIInputFields"
0x18001dc28  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001dc2e  mov     edx, [rsp+950h+var_900]
0x18001dc32  mov     r8, [rsp+950h+var_8F0]
0x18001dc37  mov     rcx, [rsp+950h+var_8E0]
0x18001dc3c  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001dc41  mov     rcx, [rsp+950h+var_8F0]
0x18001dc46  mov     rax, r13
0x18001dc49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc4e  lea     rdx, DebugInfoEvent
0x18001dc55  mov     rcx, cs:eaphost_Context
0x18001dc5c  call    cs:__imp_EtwEventEnabled
0x18001dc62  test    al, al
0x18001dc64  jz      short loc_18001DC9F
0x18001dc66  lea     r8, aEappeerqueryui_0; "EapPeerQueryUIBlobFromInteractiveUIInpu"...
0x18001dc6d  mov     edx, 800h; unsigned __int64
0x18001dc72  lea     rcx, [rbp+850h+var_850]; char *
0x18001dc76  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001dc7b  test    eax, eax
0x18001dc7d  js      short loc_18001DC9F
0x18001dc7f  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001dc86  jge     short loc_18001DC9F
0x18001dc88  lea     r8, [rbp+850h+var_850]
0x18001dc8c  lea     rdx, DebugInfoEvent
0x18001dc93  lea     rcx, eaphost_Context
0x18001dc9a  call    McTemplateU0s_EtwEventWriteTransfer
0x18001dc9f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dca6  lea     rax, WPP_GLOBAL_Control
0x18001dcad  cmp     rcx, rax
0x18001dcb0  jz      short loc_18001DCCD
0x18001dcb2  test    byte ptr [rcx+1Ch], 4
0x18001dcb6  jz      short loc_18001DCCD
0x18001dcb8  mov     edx, 1Bh
0x18001dcbd  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001dcc4  mov     rcx, [rcx+10h]
0x18001dcc8  call    WPP_SF_
0x18001dccd  mov     rcx, [rbp+850h+var_50]
0x18001dcd4  xor     rcx, rsp; StackCookie
0x18001dcd7  call    __security_check_cookie
0x18001dcdc  add     rsp, 918h
0x18001dce3  pop     r15
0x18001dce5  pop     r14
0x18001dce7  pop     r13
0x18001dce9  pop     r12
0x18001dceb  pop     rdi
0x18001dcec  pop     rsi
0x18001dced  pop     rbx
0x18001dcee  pop     rbp
0x18001dcef  retn
```
