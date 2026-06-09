# EapLm::Peer::EapMethodRuntime::GetIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)

- ea: `0x180016300`
- end: `0x180016653`
- name: `?GetIdentity@EapMethodRuntime@Peer@EapLm@@UEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z`
- size: `851`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002af0`
- `0x180005410`
- `0x18000a21c`
- `0x18000a24c`
- `0x18000a3e4`
- `0x180011cb8`
- `0x1800120c4`
- `0x18001296c`
- `0x1800155c8`
- `0x180016300`
- `0x1800199bc`
- `0x18001e768`
- `0x180030f54`
- `0x180039010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180016384`
- `ntdll!EtwEventEnabled` at `0x180016565`
- `ntdll!EtwEventEnabled` at `0x180016384`
- `ntdll!EtwEventEnabled` at `0x180016565`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
EapHost::Peer::Host **__fastcall EapLm::Peer::EapMethodRuntime::GetIdentity(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 *a4,
        __int64 *a5,
        __int64 a6,
        const wchar_t **a7,
        bool *a8)
{
  int v8; // r14d
  int v11; // edx
  int v12; // r8d
  EapHost::Peer::Host *v13; // rcx
  __int64 (__fastcall *v14)(_QWORD, _QWORD, __int64, _QWORD, __int64, __int64, int *, unsigned int *, const void **, __int64 *, struct _EAP_ERROR **); // r15
  __int64 v15; // rsi
  __int64 v16; // r14
  unsigned int v17; // ebx
  __int64 v18; // rdi
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 *v21; // rbx
  const wchar_t *v22; // r9
  EapHost::Peer::Host **result; // rax
  const wchar_t *v24; // rdx
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

  v8 = (int)a4;
  v33 = a4;
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
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v37);
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids, a2);
    v13 = WPP_GLOBAL_Control;
  }
  if ( *(_BYTE *)(a1 + 137) )
  {
    EapLm::Peer::BaseEapMethodRuntime::GetGenericIdentity(
      (_DWORD)v13,
      v11,
      v12,
      v8,
      (__int64)a5,
      a6,
      (__int64)a7,
      (__int64)a8);
  }
  else
  {
    v29 = 0;
    v28 = 0;
    v26 = 0;
    v30 = 0;
    v25 = 0;
    if ( v13 != (EapHost::Peer::Host *)&WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v13 + 2), 18, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
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
      EapHost::EapException::Throw(L"EapPeerGetIdentity", v24, (const struct EapHost::EapError *)v36);
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
  v21 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    v22 = (const wchar_t *)&`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
    if ( *a7 )
      v22 = *a7;
    if ( (int)StringCchPrintfA(v37, 0x800u, "EapPeerGetIdentity Exit:\n Identity(%ls)", v22) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v37);
    }
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( *a7 )
      v21 = (__int64 *)*a7;
    return (EapHost::Peer::Host **)WPP_SF_S(
                                     *((_QWORD *)WPP_GLOBAL_Control + 2),
                                     19,
                                     WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids,
                                     v21);
  }
  return result;
}

```

## disassembly

```asm
0x180016300  push    rbp
0x180016302  push    rbx
0x180016303  push    rsi
0x180016304  push    rdi
0x180016305  push    r12
0x180016307  push    r13
0x180016309  push    r14
0x18001630b  push    r15
0x18001630d  lea     rbp, [rsp-828h]
0x180016315  sub     rsp, 928h
0x18001631c  mov     rax, cs:__security_cookie
0x180016323  xor     rax, rsp
0x180016326  mov     [rbp+860h+var_50], rax
0x18001632d  mov     r14, r9
0x180016330  mov     [rbp+860h+var_8C8], r9
0x180016334  mov     [rbp+860h+var_8D8], r8
0x180016338  mov     edi, edx
0x18001633a  mov     [rsp+960h+var_8F8], edx
0x18001633e  mov     r13, rcx
0x180016341  mov     r12, [rbp+860h+arg_30]
0x180016348  mov     r15, [rbp+860h+arg_20]
0x18001634f  mov     [rbp+860h+var_8D0], r15
0x180016353  mov     rsi, [rbp+860h+arg_28]
0x18001635a  mov     [rbp+860h+var_8C0], rsi
0x18001635e  mov     rbx, [rbp+860h+arg_38]
0x180016365  mov     [rbp+860h+var_8B8], rbx
0x180016369  xor     edx, edx
0x18001636b  mov     rcx, r12
0x18001636e  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180016373  mov     byte ptr [rbx], 0
0x180016376  lea     rdx, DebugInfoEvent
0x18001637d  mov     rcx, cs:eaphost_Context
0x180016384  call    cs:__imp_EtwEventEnabled
0x18001638b  nop     dword ptr [rax+rax+00h]
0x180016390  test    al, al
0x180016392  jz      short loc_1800163D0
0x180016394  mov     r9d, edi
0x180016397  lea     r8, aEappeergetiden_3; "EapPeerGetIdentity Entry:\n flags(%d)"
0x18001639e  mov     edx, 800h; unsigned __int64
0x1800163a3  lea     rcx, [rbp+860h+var_850]; char *
0x1800163a7  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800163ac  test    eax, eax
0x1800163ae  js      short loc_1800163D0
0x1800163b0  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800163b7  jge     short loc_1800163D0
0x1800163b9  lea     r8, [rbp+860h+var_850]
0x1800163bd  lea     rdx, DebugInfoEvent
0x1800163c4  lea     rcx, eaphost_Context
0x1800163cb  call    McTemplateU0s_EtwEventWriteTransfer
0x1800163d0  lea     rax, WPP_GLOBAL_Control
0x1800163d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163de  cmp     rcx, rax
0x1800163e1  jz      short loc_18001640F
0x1800163e3  test    byte ptr [rcx+1Ch], 4
0x1800163e7  jz      short loc_18001640F
0x1800163e9  mov     edx, 11h
0x1800163ee  mov     r9d, edi
0x1800163f1  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x1800163f8  mov     rcx, [rcx+10h]
0x1800163fc  call    WPP_SF_d
0x180016401  mov     rcx, cs:WPP_GLOBAL_Control
0x180016408  lea     rax, WPP_GLOBAL_Control
0x18001640f  xor     edi, edi
0x180016411  cmp     [r13+89h], dil
0x180016418  jz      short loc_18001643B
0x18001641a  mov     [rsp+960h+var_928], rbx
0x18001641f  mov     [rsp+960h+var_930], r12
0x180016424  mov     [rsp+960h+var_938], rsi
0x180016429  mov     [rsp+960h+var_940], r15
0x18001642e  mov     r9, r14
0x180016431  call    ?GetGenericIdentity@BaseEapMethodRuntime@Peer@EapLm@@IEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z; EapLm::Peer::BaseEapMethodRuntime::GetGenericIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)
0x180016436  jmp     loc_180016557
0x18001643b  mov     [rsp+960h+var_8E8], rdi
0x180016440  mov     [rsp+960h+var_8F0], rdi
0x180016445  mov     [rsp+960h+var_8FC], edi
0x180016449  mov     [rbp+860h+var_8E0], rdi
0x18001644d  mov     [rsp+960h+var_900], edi
0x180016451  cmp     rcx, rax
0x180016454  jz      short loc_180016471
0x180016456  test    byte ptr [rcx+1Ch], 4
0x18001645a  jz      short loc_180016471
0x18001645c  mov     edx, 12h
0x180016461  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180016468  mov     rcx, [rcx+10h]
0x18001646c  call    WPP_SF_
0x180016471  mov     r15, [r13+148h]
0x180016478  mov     rsi, [rbp+860h+var_8D8]
0x18001647c  mov     rsi, [rsi+8]
0x180016480  mov     rcx, [rbp+860h+var_8D0]
0x180016484  mov     r14, [rcx]
0x180016487  mov     rcx, [rcx+8]
0x18001648b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180016490  mov     ebx, eax
0x180016492  mov     rcx, [rbp+860h+var_8C8]
0x180016496  mov     rdi, [rcx]
0x180016499  mov     rcx, [rcx+8]
0x18001649d  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x1800164a2  lea     rcx, [rsp+960h+var_8F0]
0x1800164a7  mov     [rsp+960h+var_910], rcx
0x1800164ac  lea     rcx, [rsp+960h+var_8E8]
0x1800164b1  mov     [rsp+960h+var_918], rcx
0x1800164b6  lea     rcx, [rbp+860h+var_8E0]
0x1800164ba  mov     [rsp+960h+var_920], rcx
0x1800164bf  lea     rcx, [rsp+960h+var_900]
0x1800164c4  mov     [rsp+960h+var_928], rcx
0x1800164c9  lea     rcx, [rsp+960h+var_8FC]
0x1800164ce  mov     [rsp+960h+var_930], rcx
0x1800164d3  mov     [rsp+960h+var_938], rsi
0x1800164d8  mov     [rsp+960h+var_940], r14
0x1800164dd  mov     r9d, ebx
0x1800164e0  mov     r8, rdi
0x1800164e3  mov     edx, eax
0x1800164e5  mov     ecx, [rsp+960h+var_8F8]
0x1800164e9  mov     rax, r15
0x1800164ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164f1  xor     edi, edi
0x1800164f3  test    eax, eax
0x1800164f5  jnz     loc_18001661F
0x1800164fb  mov     rdx, [rsp+960h+var_8E8]
0x180016500  test    rdx, rdx
0x180016503  jz      short loc_18001651E
0x180016505  mov     rcx, r12
0x180016508  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x18001650d  mov     rcx, [rsp+960h+var_8E8]
0x180016512  mov     rax, [r13+1B0h]
0x180016519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001651e  mov     r8, [rbp+860h+var_8E0]
0x180016522  test    r8, r8
0x180016525  jz      short loc_18001654A
0x180016527  mov     eax, [rsp+960h+var_900]
0x18001652b  test    eax, eax
0x18001652d  jz      short loc_18001654A
0x18001652f  mov     edx, eax
0x180016531  mov     rcx, [rbp+860h+var_8C0]
0x180016535  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001653a  mov     rcx, [rbp+860h+var_8E0]
0x18001653e  mov     rax, [r13+1B0h]
0x180016545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001654a  cmp     [rsp+960h+var_8FC], edi
0x18001654e  setnz   al
0x180016551  mov     rcx, [rbp+860h+var_8B8]
0x180016555  mov     [rcx], al
0x180016557  lea     rdx, DebugInfoEvent
0x18001655e  mov     rcx, cs:eaphost_Context
0x180016565  call    cs:__imp_EtwEventEnabled
0x18001656c  nop     dword ptr [rax+rax+00h]
0x180016571  lea     rbx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x180016578  test    al, al
0x18001657a  jz      short loc_1800165C1
0x18001657c  mov     r9, rbx
0x18001657f  cmp     [r12], rdi
0x180016583  cmovnz  r9, [r12]
0x180016588  lea     r8, aEappeergetiden; "EapPeerGetIdentity Exit:\n Identity(%ls"...
0x18001658f  mov     edx, 800h; unsigned __int64
0x180016594  lea     rcx, [rbp+860h+var_850]; char *
0x180016598  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001659d  test    eax, eax
0x18001659f  js      short loc_1800165C1
0x1800165a1  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x1800165a8  jge     short loc_1800165C1
0x1800165aa  lea     r8, [rbp+860h+var_850]
0x1800165ae  lea     rdx, DebugInfoEvent
0x1800165b5  lea     rcx, eaphost_Context
0x1800165bc  call    McTemplateU0s_EtwEventWriteTransfer
0x1800165c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165c8  lea     rax, WPP_GLOBAL_Control
0x1800165cf  cmp     rcx, rax
0x1800165d2  jz      short loc_1800165FB
0x1800165d4  test    byte ptr [rcx+1Ch], 4
0x1800165d8  jz      short loc_1800165FB
0x1800165da  cmp     [r12], rdi
0x1800165de  cmovnz  rbx, [r12]
0x1800165e3  mov     edx, 13h
0x1800165e8  mov     r9, rbx
0x1800165eb  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x1800165f2  mov     rcx, [rcx+10h]
0x1800165f6  call    WPP_SF_S
0x1800165fb  mov     rcx, [rbp+860h+var_50]
0x180016602  xor     rcx, rsp; StackCookie
0x180016605  call    __security_check_cookie
0x18001660a  add     rsp, 928h
0x180016611  pop     r15
0x180016613  pop     r14
0x180016615  pop     r13
0x180016617  pop     r12
0x180016619  pop     rdi
0x18001661a  pop     rsi
0x18001661b  pop     rbx
0x18001661c  pop     rbp
0x18001661d  retn
0x18001661f  mov     r8d, eax; unsigned int
0x180016622  mov     rdx, [rsp+960h+var_8F0]; struct _EAP_ERROR *
0x180016627  lea     rcx, [rbp+860h+var_8B0]; this
0x18001662b  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180016630  nop
0x180016631  mov     rcx, [rsp+960h+var_8F0]
0x180016636  mov     rax, [r13+1A8h]
0x18001663d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016642  lea     r8, [rbp+860h+var_8B0]; struct EapHost::EapError *
0x180016646  lea     rcx, aEappeergetiden_0; "EapPeerGetIdentity"
0x18001664d  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
```
