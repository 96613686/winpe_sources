# EapLm::Peer::EapMethodConfig::QueryInteractiveUIInputFields(uint,uint,ConstBuffer const &,_EAP_INTERACTIVE_UI_DATA *)

- ea: `0x18001d6a0`
- end: `0x18001d9e2`
- name: `?QueryInteractiveUIInputFields@EapMethodConfig@Peer@EapLm@@UEAAXIIAEBUConstBuffer@@PEAU_EAP_INTERACTIVE_UI_DATA@@@Z`
- size: `834`
- prototype: `void __fastcall(EapLm::Peer::EapMethodConfig *__hidden this, unsigned int, unsigned int, const struct ConstBuffer *, struct _EAP_INTERACTIVE_UI_DATA *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000cd8c`
- `0x18001549c`
- `0x1800154dc`
- `0x180016400`
- `0x1800177bc`
- `0x180017e04`
- `0x18001b154`
- `0x18001c3c4`
- `0x18001d6a0`
- `0x18001e008`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001d6e6`
- `ntdll!EtwEventEnabled` at `0x18001d93b`
- `ntdll!EtwEventEnabled` at `0x18001d6e6`
- `ntdll!EtwEventEnabled` at `0x18001d93b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::Peer::EapMethodConfig::QueryInteractiveUIInputFields(
        EapLm::DelayLoadModule **this,
        unsigned int a2,
        unsigned int a3,
        const struct ConstBuffer *a4,
        struct _EAP_INTERACTIVE_UI_DATA *a5)
{
  __int64 v9; // r8
  EapLm::DelayLoadModule *v10; // rax
  __int64 (__fastcall *v11)(_QWORD, _QWORD, _QWORD, __int64, struct _EAP_INTERACTIVE_UI_DATA *, struct _EAP_ERROR **, _QWORD); // r15
  void (__fastcall *v12)(struct _EAP_ERROR *); // r13
  __int64 v13; // rbx
  unsigned int v14; // eax
  unsigned int v15; // eax
  const wchar_t *v16; // rdx
  EapLm::Peer::EapMethodConfig *v17; // rcx
  __int128 v18; // xmm1
  EAP_UI_DATA_FORMAT v19; // xmm2_8
  void (*v20)(void); // r8
  _BYTE v21[24]; // [rsp+40h] [rbp-8F8h] BYREF
  int v22; // [rsp+58h] [rbp-8E0h]
  struct _EAP_ERROR *v23; // [rsp+60h] [rbp-8D8h] BYREF
  void (*v24)(unsigned __int8 *); // [rsp+68h] [rbp-8D0h]
  struct _EAP_INTERACTIVE_UI_DATA v25; // [rsp+70h] [rbp-8C8h] BYREF
  char v26[96]; // [rsp+90h] [rbp-8A8h] BYREF
  char v27[2048]; // [rsp+F0h] [rbp-848h] BYREF
  const Exception *v28; // [rsp+8F0h] [rbp-48h] BYREF

  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(
              v27,
              0x800u,
              "EapPeerQueryInteractiveUIInputFields Entry:\n version(%d), flags(%d), Context data(%Id) bytes",
              a2,
              a3,
              *((_QWORD *)a4 + 1)) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v27);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_ddP(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v9, a2, a3, *((_QWORD *)a4 + 1));
  EapLm::DelayLoadModule::LoadIfNeeded(this[20], 1);
  v10 = this[20];
  v11 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64, struct _EAP_INTERACTIVE_UI_DATA *, struct _EAP_ERROR **, _QWORD))*((_QWORD *)v10 + 27);
  if ( !v11 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(
        &eaphost_Context,
        (__int64)PeerFunctionNotSupported,
        "QueryInteractiveUIInputFields");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
    v21[8] = *((_BYTE *)this + 16);
    *(_DWORD *)&v21[12] = *((_DWORD *)this + 5);
    *(_DWORD *)&v21[16] = *((_DWORD *)this + 6);
    if ( v21[8] != 0xFE )
      *(_QWORD *)&v21[12] = 0;
    *(_QWORD *)v21 = &EapHost::EapMethodType::`vftable';
    v22 = *((_DWORD *)this + 7);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)v21, 0x80420020);
  }
  v24 = (void (*)(unsigned __int8 *))*((_QWORD *)v10 + 29);
  v12 = (void (__fastcall *)(struct _EAP_ERROR *))*((_QWORD *)v10 + 28);
  memset(&v25, 0, sizeof(v25));
  v23 = 0;
  v13 = *(_QWORD *)a4;
  v14 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(*((_QWORD *)a4 + 1));
  v15 = v11(a2, a3, v14, v13, &v25, &v23, 0);
  if ( v15 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v26, v23, v15);
    v12(v23);
    EapHost::EapException::Throw(L"EapPeerQueryInteractiveUIInputFields", v16, (const struct EapHost::EapError *)v26);
  }
  memset(v21, 0, sizeof(v21));
  try
  {
    crt_ref<_EAP_INTERACTIVE_UI_DATA>::Assign();
    v18 = *(_OWORD *)v21;
    v19.credData = *(EAP_CRED_REQ **)&v21[16];
    memset(v21, 0, sizeof(v21));
    *(_OWORD *)&a5->dwVersion = v18;
    a5->pbUiData = v19;
    v20 = (void (*)(void))v24;
  }
  catch ( const Exception *v28 )
  {
    Free<HeapAllocator>(v21);
    throw;
  }
  EapLm::Peer::EapMethodConfig::FreeEAPInteractiveUIData(v17, &v25, v20);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v27, 0x800u, "EapPeerQueryInteractiveUIInputFields Exit") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v27);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids);
  Free<HeapAllocator>(v21);
}

```

## disassembly

```asm
0x18001d6a0  push    rbx
0x18001d6a2  push    rsi
0x18001d6a3  push    rdi
0x18001d6a4  push    r12
0x18001d6a6  push    r13
0x18001d6a8  push    r14
0x18001d6aa  push    r15
0x18001d6ac  sub     rsp, 900h
0x18001d6b3  mov     rax, cs:__security_cookie
0x18001d6ba  xor     rax, rsp
0x18001d6bd  mov     [rsp+938h+var_40], rax
0x18001d6c5  mov     rdi, r9
0x18001d6c8  mov     r14d, r8d
0x18001d6cb  mov     esi, edx
0x18001d6cd  mov     rbx, rcx
0x18001d6d0  mov     r12, [rsp+938h+arg_20]
0x18001d6d8  lea     rdx, DebugInfoEvent
0x18001d6df  mov     rcx, cs:eaphost_Context
0x18001d6e6  call    cs:__imp_EtwEventEnabled
0x18001d6ec  xor     r13d, r13d
0x18001d6ef  test    al, al
0x18001d6f1  jz      short loc_18001D745
0x18001d6f3  mov     rax, [rdi+8]
0x18001d6f7  mov     [rsp+938h+var_910], rax
0x18001d6fc  mov     dword ptr [rsp+938h+var_918], r14d
0x18001d701  mov     r9d, esi
0x18001d704  lea     r8, aEappeerqueryin; "EapPeerQueryInteractiveUIInputFields En"...
0x18001d70b  mov     edx, 800h; unsigned __int64
0x18001d710  lea     rcx, [rsp+938h+var_848]; char *
0x18001d718  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001d71d  test    eax, eax
0x18001d71f  js      short loc_18001D745
0x18001d721  cmp     cs:Microsoft_Windows_EapHostEnableBits, r13b
0x18001d728  jge     short loc_18001D745
0x18001d72a  lea     r8, [rsp+938h+var_848]
0x18001d732  lea     rdx, DebugInfoEvent
0x18001d739  lea     rcx, eaphost_Context
0x18001d740  call    McTemplateU0s_EtwEventWriteTransfer
0x18001d745  lea     rax, WPP_GLOBAL_Control
0x18001d74c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d753  cmp     rcx, rax
0x18001d756  jz      short loc_18001D77D
0x18001d758  test    byte ptr [rcx+1Ch], 4
0x18001d75c  jz      short loc_18001D77D
0x18001d75e  mov     edx, 16h
0x18001d763  mov     rax, [rdi+8]
0x18001d767  mov     [rsp+938h+var_910], rax
0x18001d76c  mov     dword ptr [rsp+938h+var_918], r14d
0x18001d771  mov     r9d, esi
0x18001d774  mov     rcx, [rcx+10h]
0x18001d778  call    WPP_SF_ddP
0x18001d77d  mov     dl, 1; bool
0x18001d77f  mov     rcx, [rbx+0A0h]; this
0x18001d786  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x18001d78b  mov     rax, [rbx+0A0h]
0x18001d792  mov     r15, [rax+0D8h]
0x18001d799  test    r15, r15
0x18001d79c  jnz     loc_18001D838
0x18001d7a2  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x18001d7a9  jz      short loc_18001D7C5
0x18001d7ab  lea     r8, aQueryinteracti; "QueryInteractiveUIInputFields"
0x18001d7b2  lea     rdx, PeerFunctionNotSupported
0x18001d7b9  lea     rcx, eaphost_Context
0x18001d7c0  call    McTemplateU0s_EtwEventWriteTransfer
0x18001d7c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d7cc  lea     rax, WPP_GLOBAL_Control
0x18001d7d3  cmp     rcx, rax
0x18001d7d6  jz      short loc_18001D7F3
0x18001d7d8  test    byte ptr [rcx+1Ch], 1
0x18001d7dc  jz      short loc_18001D7F3
0x18001d7de  mov     edx, 17h
0x18001d7e3  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001d7ea  mov     rcx, [rcx+10h]
0x18001d7ee  call    WPP_SF_
0x18001d7f3  mov     cl, [rbx+10h]
0x18001d7f6  mov     byte ptr [rsp+938h+var_8F8+8], cl
0x18001d7fa  mov     eax, [rbx+14h]
0x18001d7fd  mov     dword ptr [rsp+938h+var_8F8+0Ch], eax
0x18001d801  mov     eax, [rbx+18h]
0x18001d804  mov     dword ptr [rsp+938h+var_8E8], eax
0x18001d808  cmp     cl, 0FEh
0x18001d80b  jz      short loc_18001D812
0x18001d80d  mov     qword ptr [rsp+938h+var_8F8+0Ch], r13
0x18001d812  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18001d819  mov     qword ptr [rsp+938h+var_8F8], rax
0x18001d81e  mov     eax, [rbx+1Ch]
0x18001d821  mov     [rsp+938h+var_8E0], eax
0x18001d825  mov     ecx, 80420020h; unsigned int
0x18001d82a  mov     r8d, ecx; unsigned int
0x18001d82d  lea     rdx, [rsp+938h+var_8F8]; struct EapHost::EapMethodType *
0x18001d832  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x18001d838  mov     rcx, [rax+0E8h]
0x18001d83f  mov     [rsp+938h+var_8D0], rcx
0x18001d844  mov     r13, [rax+0E0h]
0x18001d84b  xorps   xmm0, xmm0
0x18001d84e  xor     eax, eax
0x18001d850  movups  xmmword ptr [rsp+938h+var_8C8.dwVersion], xmm0
0x18001d855  mov     qword ptr [rsp+938h+var_8C8.pbUiData], rax
0x18001d85d  mov     [rsp+938h+var_8D8], rax
0x18001d862  mov     rbx, [rdi]
0x18001d865  mov     rcx, [rdi+8]
0x18001d869  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18001d86e  mov     [rsp+938h+var_908], 0
0x18001d877  lea     rcx, [rsp+938h+var_8D8]
0x18001d87c  mov     [rsp+938h+var_910], rcx
0x18001d881  lea     rcx, [rsp+938h+var_8C8]
0x18001d886  mov     [rsp+938h+var_918], rcx
0x18001d88b  mov     r9, rbx
0x18001d88e  mov     r8d, eax
0x18001d891  mov     edx, r14d
0x18001d894  mov     ecx, esi
0x18001d896  mov     rax, r15
0x18001d899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d89e  test    eax, eax
0x18001d8a0  jz      short loc_18001D8DA
0x18001d8a2  mov     r8d, eax; unsigned int
0x18001d8a5  mov     rdx, [rsp+938h+var_8D8]; struct _EAP_ERROR *
0x18001d8aa  lea     rcx, [rsp+938h+var_8A8]; this
0x18001d8b2  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x18001d8b7  nop
0x18001d8b8  mov     rcx, [rsp+938h+var_8D8]
0x18001d8bd  mov     rax, r13
0x18001d8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8c5  lea     r8, [rsp+938h+var_8A8]; struct EapHost::EapError *
0x18001d8cd  lea     rcx, aEappeerqueryin_0; "EapPeerQueryInteractiveUIInputFields"
0x18001d8d4  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x18001d8da  xorps   xmm0, xmm0
0x18001d8dd  xor     eax, eax
0x18001d8df  movups  [rsp+938h+var_8F8], xmm0
0x18001d8e4  mov     [rsp+938h+var_8E8], rax
0x18001d8e9  lea     rdx, [rsp+938h+var_8C8]
0x18001d8ee  lea     rcx, [rsp+938h+var_8F8]
0x18001d8f3  call    ?Assign@?$crt_ref@U_EAP_INTERACTIVE_UI_DATA@@@@QEAAXAEBU_EAP_INTERACTIVE_UI_DATA@@@Z; crt_ref<_EAP_INTERACTIVE_UI_DATA>::Assign(_EAP_INTERACTIVE_UI_DATA const &)
0x18001d8f8  movups  xmm1, [rsp+938h+var_8F8]
0x18001d8fd  movsd   xmm2, [rsp+938h+var_8E8]
0x18001d903  xorps   xmm0, xmm0
0x18001d906  xor     eax, eax
0x18001d908  movups  [rsp+938h+var_8F8], xmm0
0x18001d90d  mov     [rsp+938h+var_8E8], rax
0x18001d912  movups  xmmword ptr [r12], xmm1
0x18001d917  movsd   qword ptr [r12+10h], xmm2
0x18001d91e  mov     r8, [rsp+938h+var_8D0]; void (*)(unsigned __int8 *)
0x18001d923  lea     rdx, [rsp+938h+var_8C8]; struct _EAP_INTERACTIVE_UI_DATA *
0x18001d928  call    ?FreeEAPInteractiveUIData@EapMethodConfig@Peer@EapLm@@AEAAXPEAU_EAP_INTERACTIVE_UI_DATA@@P6AXPEAE@Z@Z; EapLm::Peer::EapMethodConfig::FreeEAPInteractiveUIData(_EAP_INTERACTIVE_UI_DATA *,void (*)(uchar *))
0x18001d92d  lea     rdx, DebugInfoEvent
0x18001d934  mov     rcx, cs:eaphost_Context
0x18001d93b  call    cs:__imp_EtwEventEnabled
0x18001d941  test    al, al
0x18001d943  jz      short loc_18001D986
0x18001d945  lea     r8, aEappeerqueryin_2; "EapPeerQueryInteractiveUIInputFields Ex"...
0x18001d94c  mov     edx, 800h; unsigned __int64
0x18001d951  lea     rcx, [rsp+938h+var_848]; char *
0x18001d959  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001d95e  test    eax, eax
0x18001d960  js      short loc_18001D986
0x18001d962  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x18001d969  jge     short loc_18001D986
0x18001d96b  lea     r8, [rsp+938h+var_848]
0x18001d973  lea     rdx, DebugInfoEvent
0x18001d97a  lea     rcx, eaphost_Context
0x18001d981  call    McTemplateU0s_EtwEventWriteTransfer
0x18001d986  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d98d  lea     rax, WPP_GLOBAL_Control
0x18001d994  cmp     rcx, rax
0x18001d997  jz      short loc_18001D9B5
0x18001d999  test    byte ptr [rcx+1Ch], 4
0x18001d99d  jz      short loc_18001D9B5
0x18001d99f  mov     edx, 18h
0x18001d9a4  lea     r8, WPP_9ba580f1d72d3d62eca54ade7486219a_Traceguids
0x18001d9ab  mov     rcx, [rcx+10h]
0x18001d9af  call    WPP_SF_
0x18001d9b4  nop
0x18001d9b5  lea     rcx, [rsp+938h+var_8F8]
0x18001d9ba  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_INTERACTIVE_UI_DATA@@@Z; Free<HeapAllocator>(_EAP_INTERACTIVE_UI_DATA &)
0x18001d9bf  mov     rcx, [rsp+938h+var_40]
0x18001d9c7  xor     rcx, rsp; StackCookie
0x18001d9ca  call    __security_check_cookie
0x18001d9cf  add     rsp, 900h
0x18001d9d6  pop     r15
0x18001d9d8  pop     r14
0x18001d9da  pop     r13
0x18001d9dc  pop     r12
0x18001d9de  pop     rdi
0x18001d9df  pop     rsi
0x18001d9e0  pop     rbx
0x18001d9e1  retn
```
