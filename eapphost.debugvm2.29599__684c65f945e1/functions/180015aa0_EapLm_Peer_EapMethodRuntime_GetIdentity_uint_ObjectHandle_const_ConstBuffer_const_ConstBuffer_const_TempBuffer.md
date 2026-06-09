# EapLm::Peer::EapMethodRuntime::GetIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)

- ea: `0x180015aa0`
- end: `0x180015de6`
- name: `?GetIdentity@EapMethodRuntime@Peer@EapLm@@UEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z`
- size: `838`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a90`
- `0x1800052c0`
- `0x180009dc4`
- `0x180009dec`
- `0x180009f70`
- `0x180011578`
- `0x180011958`
- `0x1800121ec`
- `0x180014d8c`
- `0x180015aa0`
- `0x180018ffc`
- `0x18001dc64`
- `0x18002fd44`
- `0x180038010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180015b24`
- `ntdll!EtwEventEnabled` at `0x180015cff`
- `ntdll!EtwEventEnabled` at `0x180015b24`
- `ntdll!EtwEventEnabled` at `0x180015cff`

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
0x180015aa0  push    rbp
0x180015aa2  push    rbx
0x180015aa3  push    rsi
0x180015aa4  push    rdi
0x180015aa5  push    r12
0x180015aa7  push    r13
0x180015aa9  push    r14
0x180015aab  push    r15
0x180015aad  lea     rbp, [rsp-828h]
0x180015ab5  sub     rsp, 928h
0x180015abc  mov     rax, cs:__security_cookie
0x180015ac3  xor     rax, rsp
0x180015ac6  mov     [rbp+860h+var_50], rax
0x180015acd  mov     r14, r9
0x180015ad0  mov     [rbp+860h+var_8C8], r9
0x180015ad4  mov     [rbp+860h+var_8D8], r8
0x180015ad8  mov     edi, edx
0x180015ada  mov     [rsp+960h+var_8F8], edx
0x180015ade  mov     r13, rcx
0x180015ae1  mov     r12, [rbp+860h+arg_30]
0x180015ae8  mov     r15, [rbp+860h+arg_20]
0x180015aef  mov     [rbp+860h+var_8D0], r15
0x180015af3  mov     rsi, [rbp+860h+arg_28]
0x180015afa  mov     [rbp+860h+var_8C0], rsi
0x180015afe  mov     rbx, [rbp+860h+arg_38]
0x180015b05  mov     [rbp+860h+var_8B8], rbx
0x180015b09  xor     edx, edx
0x180015b0b  mov     rcx, r12
0x180015b0e  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180015b13  mov     byte ptr [rbx], 0
0x180015b16  lea     rdx, DebugInfoEvent
0x180015b1d  mov     rcx, cs:eaphost_Context
0x180015b24  call    cs:__imp_EtwEventEnabled
0x180015b2a  test    al, al
0x180015b2c  jz      short loc_180015B6A
0x180015b2e  mov     r9d, edi
0x180015b31  lea     r8, aEappeergetiden_3; "EapPeerGetIdentity Entry:\n flags(%d)"
0x180015b38  mov     edx, 800h; unsigned __int64
0x180015b3d  lea     rcx, [rbp+860h+var_850]; char *
0x180015b41  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180015b46  test    eax, eax
0x180015b48  js      short loc_180015B6A
0x180015b4a  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180015b51  jge     short loc_180015B6A
0x180015b53  lea     r8, [rbp+860h+var_850]
0x180015b57  lea     rdx, DebugInfoEvent
0x180015b5e  lea     rcx, eaphost_Context
0x180015b65  call    McTemplateU0s_EtwEventWriteTransfer
0x180015b6a  lea     rax, WPP_GLOBAL_Control
0x180015b71  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b78  cmp     rcx, rax
0x180015b7b  jz      short loc_180015BA9
0x180015b7d  test    byte ptr [rcx+1Ch], 4
0x180015b81  jz      short loc_180015BA9
0x180015b83  mov     edx, 11h
0x180015b88  mov     r9d, edi
0x180015b8b  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180015b92  mov     rcx, [rcx+10h]
0x180015b96  call    WPP_SF_d
0x180015b9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ba2  lea     rax, WPP_GLOBAL_Control
0x180015ba9  xor     edi, edi
0x180015bab  cmp     [r13+89h], dil
0x180015bb2  jz      short loc_180015BD5
0x180015bb4  mov     [rsp+960h+var_928], rbx
0x180015bb9  mov     [rsp+960h+var_930], r12
0x180015bbe  mov     [rsp+960h+var_938], rsi
0x180015bc3  mov     [rsp+960h+var_940], r15
0x180015bc8  mov     r9, r14
0x180015bcb  call    ?GetGenericIdentity@BaseEapMethodRuntime@Peer@EapLm@@IEAAXIAEBVObjectHandle@@AEBUConstBuffer@@1AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@AEA_N@Z; EapLm::Peer::BaseEapMethodRuntime::GetGenericIdentity(uint,ObjectHandle const &,ConstBuffer const &,ConstBuffer const &,TempBuffer<0> &,BasicSimpleString<wchar_t> &,bool &)
0x180015bd0  jmp     loc_180015CF1
0x180015bd5  mov     [rsp+960h+var_8E8], rdi
0x180015bda  mov     [rsp+960h+var_8F0], rdi
0x180015bdf  mov     [rsp+960h+var_8FC], edi
0x180015be3  mov     [rbp+860h+var_8E0], rdi
0x180015be7  mov     [rsp+960h+var_900], edi
0x180015beb  cmp     rcx, rax
0x180015bee  jz      short loc_180015C0B
0x180015bf0  test    byte ptr [rcx+1Ch], 4
0x180015bf4  jz      short loc_180015C0B
0x180015bf6  mov     edx, 12h
0x180015bfb  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180015c02  mov     rcx, [rcx+10h]
0x180015c06  call    WPP_SF_
0x180015c0b  mov     r15, [r13+148h]
0x180015c12  mov     rsi, [rbp+860h+var_8D8]
0x180015c16  mov     rsi, [rsi+8]
0x180015c1a  mov     rcx, [rbp+860h+var_8D0]
0x180015c1e  mov     r14, [rcx]
0x180015c21  mov     rcx, [rcx+8]
0x180015c25  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180015c2a  mov     ebx, eax
0x180015c2c  mov     rcx, [rbp+860h+var_8C8]
0x180015c30  mov     rdi, [rcx]
0x180015c33  mov     rcx, [rcx+8]
0x180015c37  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180015c3c  lea     rcx, [rsp+960h+var_8F0]
0x180015c41  mov     [rsp+960h+var_910], rcx
0x180015c46  lea     rcx, [rsp+960h+var_8E8]
0x180015c4b  mov     [rsp+960h+var_918], rcx
0x180015c50  lea     rcx, [rbp+860h+var_8E0]
0x180015c54  mov     [rsp+960h+var_920], rcx
0x180015c59  lea     rcx, [rsp+960h+var_900]
0x180015c5e  mov     [rsp+960h+var_928], rcx
0x180015c63  lea     rcx, [rsp+960h+var_8FC]
0x180015c68  mov     [rsp+960h+var_930], rcx
0x180015c6d  mov     [rsp+960h+var_938], rsi
0x180015c72  mov     [rsp+960h+var_940], r14
0x180015c77  mov     r9d, ebx
0x180015c7a  mov     r8, rdi
0x180015c7d  mov     edx, eax
0x180015c7f  mov     ecx, [rsp+960h+var_8F8]
0x180015c83  mov     rax, r15
0x180015c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c8b  xor     edi, edi
0x180015c8d  test    eax, eax
0x180015c8f  jnz     loc_180015DB2
0x180015c95  mov     rdx, [rsp+960h+var_8E8]
0x180015c9a  test    rdx, rdx
0x180015c9d  jz      short loc_180015CB8
0x180015c9f  mov     rcx, r12
0x180015ca2  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180015ca7  mov     rcx, [rsp+960h+var_8E8]
0x180015cac  mov     rax, [r13+1B0h]
0x180015cb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015cb8  mov     r8, [rbp+860h+var_8E0]
0x180015cbc  test    r8, r8
0x180015cbf  jz      short loc_180015CE4
0x180015cc1  mov     eax, [rsp+960h+var_900]
0x180015cc5  test    eax, eax
0x180015cc7  jz      short loc_180015CE4
0x180015cc9  mov     edx, eax
0x180015ccb  mov     rcx, [rbp+860h+var_8C0]
0x180015ccf  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180015cd4  mov     rcx, [rbp+860h+var_8E0]
0x180015cd8  mov     rax, [r13+1B0h]
0x180015cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ce4  cmp     [rsp+960h+var_8FC], edi
0x180015ce8  setnz   al
0x180015ceb  mov     rcx, [rbp+860h+var_8B8]
0x180015cef  mov     [rcx], al
0x180015cf1  lea     rdx, DebugInfoEvent
0x180015cf8  mov     rcx, cs:eaphost_Context
0x180015cff  call    cs:__imp_EtwEventEnabled
0x180015d05  lea     rbx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x180015d0c  test    al, al
0x180015d0e  jz      short loc_180015D55
0x180015d10  mov     r9, rbx
0x180015d13  cmp     [r12], rdi
0x180015d17  cmovnz  r9, [r12]
0x180015d1c  lea     r8, aEappeergetiden; "EapPeerGetIdentity Exit:\n Identity(%ls"...
0x180015d23  mov     edx, 800h; unsigned __int64
0x180015d28  lea     rcx, [rbp+860h+var_850]; char *
0x180015d2c  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180015d31  test    eax, eax
0x180015d33  js      short loc_180015D55
0x180015d35  cmp     cs:Microsoft_Windows_EapHostEnableBits, dil
0x180015d3c  jge     short loc_180015D55
0x180015d3e  lea     r8, [rbp+860h+var_850]
0x180015d42  lea     rdx, DebugInfoEvent
0x180015d49  lea     rcx, eaphost_Context
0x180015d50  call    McTemplateU0s_EtwEventWriteTransfer
0x180015d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d5c  lea     rax, WPP_GLOBAL_Control
0x180015d63  cmp     rcx, rax
0x180015d66  jz      short loc_180015D8F
0x180015d68  test    byte ptr [rcx+1Ch], 4
0x180015d6c  jz      short loc_180015D8F
0x180015d6e  cmp     [r12], rdi
0x180015d72  cmovnz  rbx, [r12]
0x180015d77  mov     edx, 13h
0x180015d7c  mov     r9, rbx
0x180015d7f  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x180015d86  mov     rcx, [rcx+10h]
0x180015d8a  call    WPP_SF_S
0x180015d8f  mov     rcx, [rbp+860h+var_50]
0x180015d96  xor     rcx, rsp; StackCookie
0x180015d99  call    __security_check_cookie
0x180015d9e  add     rsp, 928h
0x180015da5  pop     r15
0x180015da7  pop     r14
0x180015da9  pop     r13
0x180015dab  pop     r12
0x180015dad  pop     rdi
0x180015dae  pop     rsi
0x180015daf  pop     rbx
0x180015db0  pop     rbp
0x180015db1  retn
0x180015db2  mov     r8d, eax; unsigned int
0x180015db5  mov     rdx, [rsp+960h+var_8F0]; struct _EAP_ERROR *
0x180015dba  lea     rcx, [rbp+860h+var_8B0]; this
0x180015dbe  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180015dc3  nop
0x180015dc4  mov     rcx, [rsp+960h+var_8F0]
0x180015dc9  mov     rax, [r13+1A8h]
0x180015dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dd5  lea     r8, [rbp+860h+var_8B0]; struct EapHost::EapError *
0x180015dd9  lea     rcx, aEappeergetiden_0; "EapPeerGetIdentity"
0x180015de0  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
```
