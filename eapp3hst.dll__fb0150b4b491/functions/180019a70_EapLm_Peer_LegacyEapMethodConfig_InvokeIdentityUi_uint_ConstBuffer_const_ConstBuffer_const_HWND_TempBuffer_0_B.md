# EapLm::Peer::LegacyEapMethodConfig::InvokeIdentityUi(uint,ConstBuffer const &,ConstBuffer const &,HWND__ *,TempBuffer<0> &,BasicSimpleString<wchar_t> &)

- ea: `0x180019a70`
- end: `0x18001a07d`
- name: `?InvokeIdentityUi@LegacyEapMethodConfig@Peer@EapLm@@UEAAXIAEBUConstBuffer@@0PEAUHWND__@@AEAV?$TempBuffer@$0A@@@AEAV?$BasicSimpleString@_W@@@Z`
- size: `1549`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x1800126f8`
- `0x180013d10`
- `0x18001549c`
- `0x180016400`
- `0x1800177bc`
- `0x180019a70`
- `0x18001b154`
- `0x18001b21c`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180019af3`
- `ntdll!EtwEventEnabled` at `0x180019cab`
- `ntdll!EtwEventEnabled` at `0x180019fa1`
- `ntdll!EtwEventEnabled` at `0x180019af3`
- `ntdll!EtwEventEnabled` at `0x180019cab`
- `ntdll!EtwEventEnabled` at `0x180019fa1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_UNKNOWN **__fastcall EapLm::Peer::LegacyEapMethodConfig::InvokeIdentityUi(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        __int64 *a4,
        __int64 a5,
        __int64 a6,
        void **a7)
{
  void **v11; // r14
  __int64 v12; // r12
  __int64 v13; // rax
  struct _EAP_ERROR *v14; // rsi
  int v15; // ebx
  __int64 v16; // rdi
  int v17; // eax
  _QWORD *v18; // rdi
  unsigned int v19; // ebx
  __int64 v20; // rax
  __int64 (__fastcall *v21)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, unsigned int *, const void **, __int64 *, struct _EAP_ERROR **); // r14
  void (__fastcall *v22)(const void *); // r12
  __int64 v23; // rsi
  int v24; // ebx
  __int64 v25; // rdi
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // ebx
  int v29; // edx
  int v30; // r8d
  __int64 *v31; // rbx
  const wchar_t *v32; // rcx
  _UNKNOWN **result; // rax
  __int64 v34; // [rsp+38h] [rbp-960h]
  unsigned int v35; // [rsp+70h] [rbp-928h] BYREF
  const void *v36; // [rsp+78h] [rbp-920h] BYREF
  const void *v37; // [rsp+80h] [rbp-918h] BYREF
  struct _EAP_ERROR *v38; // [rsp+88h] [rbp-910h] BYREF
  unsigned int v39; // [rsp+90h] [rbp-908h]
  _QWORD *v40; // [rsp+98h] [rbp-900h]
  void (__fastcall *v41)(const void *); // [rsp+A0h] [rbp-8F8h]
  void **v42; // [rsp+A8h] [rbp-8F0h] BYREF
  char v43; // [rsp+B0h] [rbp-8E8h]
  __int64 v44; // [rsp+B4h] [rbp-8E4h]
  int v45; // [rsp+C0h] [rbp-8D8h]
  __int64 *v46; // [rsp+C8h] [rbp-8D0h]
  __int64 v47; // [rsp+D0h] [rbp-8C8h]
  __int64 v48; // [rsp+D8h] [rbp-8C0h]
  void **v49; // [rsp+E0h] [rbp-8B8h]
  _BYTE v50[96]; // [rsp+F0h] [rbp-8A8h] BYREF
  char v51[2048]; // [rsp+150h] [rbp-848h] BYREF

  v46 = a4;
  v40 = a3;
  v39 = a2;
  v11 = a7;
  v49 = a7;
  v47 = a5;
  v12 = a6;
  v48 = a6;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v51, 0x800u, "RasEapGetIdentity Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v51);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, a2);
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 176), 0);
  v35 = 0;
  v36 = 0;
  v37 = 0;
  if ( *(_BYTE *)(a1 + 257) || *(_BYTE *)(a1 + 258) )
  {
    v20 = *(_QWORD *)(a1 + 176);
    v21 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64, int, __int64, unsigned int *, const void **, __int64 *, struct _EAP_ERROR **))(v20 + 216);
    v22 = *(void (__fastcall **)(const void *))(v20 + 232);
    v41 = v22;
    v38 = 0;
    v23 = *a4;
    v24 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v46[1]);
    v25 = *a3;
    v26 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v40[1]);
    v27 = v21(a1 + 16, v39, v47, v26, v25, v24, v23, &v35, &v36, (__int64 *)&v37, &v38);
    v28 = v27;
    if ( v27 )
    {
      EapHost::EapError::EapError((EapHost::EapError *)v50, v38, v27);
      v22(v38);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v28);
      v43 = *(_BYTE *)(a1 + 16);
      v44 = *(_QWORD *)(a1 + 20);
      if ( v43 != -2 )
        v44 = 0;
      v42 = &EapHost::EapMethodType::`vftable';
      v45 = *(_DWORD *)(a1 + 28);
      EapHost::EapException::Throw(v28, (const struct EapHost::EapMethodType *)&v42, v28);
    }
    try
    {
      TempBuffer<0>::Assign(v48, v35, v36);
      v11 = v49;
      BasicSimpleString<wchar_t>::Assign(v49, (__int64)v37);
    }
    catch ( std::bad_alloc )
    {
      v41(v36);
      v41(v37);
      throw;
    }
    v22(v36);
    v22(v37);
    v12 = v48;
    v18 = v40;
  }
  else
  {
    v13 = *(_QWORD *)(a1 + 176);
    v41 = *(void (__fastcall **)(const void *))(v13 + 216);
    v14 = *(struct _EAP_ERROR **)(v13 + 232);
    v38 = v14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    v15 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v46[1]);
    v16 = *v46;
    v17 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v40[1]);
    v34 = v16;
    v18 = v40;
    v19 = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, _QWORD, int, __int64, int, const void **, unsigned int *, const void **))v41)(
            *(unsigned __int8 *)(a1 + 16),
            v47,
            v39,
            0,
            0,
            *v40,
            v17,
            v34,
            v15,
            &v36,
            &v35,
            &v37);
    if ( v19 )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
        && (int)StringCchPrintfA(v51, 0x800u, "RasEapGetIdentity failed %d", v19) >= 0
        && (byte_18004AF81 & 8) != 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugErrorEvent, v51);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v19);
      v43 = *(_BYTE *)(a1 + 16);
      v44 = *(_QWORD *)(a1 + 20);
      if ( v43 != -2 )
        v44 = 0;
      v42 = &EapHost::EapMethodType::`vftable';
      v45 = *(_DWORD *)(a1 + 28);
      EapHost::EapException::Throw(v19, (const struct EapHost::EapMethodType *)&v42, v19);
    }
    try
    {
      TempBuffer<0>::Assign(a6, v35, v36);
      BasicSimpleString<wchar_t>::Assign(a7, (__int64)v37);
    }
    catch ( std::bad_alloc )
    {
      ((void (__fastcall *)(const void *))v38)(v36);
      ((void (__fastcall *)(const void *))v38)(v37);
      throw;
    }
    ((void (__fastcall *)(const void *))v14)(v36);
    ((void (__fastcall *)(const void *))v14)(v37);
  }
  v31 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
  {
    v32 = (const wchar_t *)&`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
    if ( *v11 )
      v32 = (const wchar_t *)*v11;
    if ( (int)StringCchPrintfA(
                v51,
                0x800u,
                "RasEapGetIdentity Exit:\n"
                " conn data(%Id) bytes, user data(%Id) bytes, returned(%d) bytes data, Identity(%S) ",
                v18[1],
                *(_QWORD *)(v12 + 8),
                v35,
                v32) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v51);
    }
  }
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    if ( *v11 )
      v31 = (__int64 *)*v11;
    return (_UNKNOWN **)WPP_SF_PPdS(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v29,
                          v30,
                          v18[1],
                          *(_QWORD *)(v12 + 8),
                          v35,
                          (__int64)v31);
  }
  return result;
}

```

## disassembly

```asm
0x180019a70  push    rbx
0x180019a72  push    rsi
0x180019a73  push    rdi
0x180019a74  push    r12
0x180019a76  push    r14
0x180019a78  push    r15
0x180019a7a  sub     rsp, 968h
0x180019a81  mov     rax, cs:__security_cookie
0x180019a88  xor     rax, rsp
0x180019a8b  mov     [rsp+998h+var_48], rax
0x180019a93  mov     rsi, r9
0x180019a96  mov     [rsp+998h+var_8D0], r9
0x180019a9e  mov     rdi, r8
0x180019aa1  mov     [rsp+998h+var_900], r8
0x180019aa9  mov     ebx, edx
0x180019aab  mov     [rsp+998h+var_908], edx
0x180019ab2  mov     r15, rcx
0x180019ab5  mov     r14, [rsp+998h+arg_30]
0x180019abd  mov     [rsp+998h+var_8B8], r14
0x180019ac5  mov     rax, [rsp+998h+arg_20]
0x180019acd  mov     [rsp+998h+var_8C8], rax
0x180019ad5  mov     r12, [rsp+998h+arg_28]
0x180019add  mov     [rsp+998h+var_8C0], r12
0x180019ae5  lea     rdx, DebugInfoEvent
0x180019aec  mov     rcx, cs:eaphost_Context
0x180019af3  call    cs:__imp_EtwEventEnabled
0x180019af9  test    al, al
0x180019afb  jz      short loc_180019B41
0x180019afd  mov     r9d, ebx
0x180019b00  lea     r8, aRaseapgetident_0; "RasEapGetIdentity Entry:\n flags(%d)"
0x180019b07  mov     edx, 800h; unsigned __int64
0x180019b0c  lea     rcx, [rsp+998h+var_848]; char *
0x180019b14  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180019b19  test    eax, eax
0x180019b1b  js      short loc_180019B41
0x180019b1d  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x180019b24  jge     short loc_180019B41
0x180019b26  lea     r8, [rsp+998h+var_848]
0x180019b2e  lea     rdx, DebugInfoEvent
0x180019b35  lea     rcx, eaphost_Context
0x180019b3c  call    McTemplateU0s_EtwEventWriteTransfer
0x180019b41  lea     rax, WPP_GLOBAL_Control
0x180019b48  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b4f  cmp     rcx, rax
0x180019b52  jz      short loc_180019B72
0x180019b54  test    byte ptr [rcx+1Ch], 4
0x180019b58  jz      short loc_180019B72
0x180019b5a  mov     edx, 14h
0x180019b5f  mov     r9d, ebx
0x180019b62  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180019b69  mov     rcx, [rcx+10h]
0x180019b6d  call    WPP_SF_d
0x180019b72  xor     edx, edx; bool
0x180019b74  mov     rcx, [r15+0B0h]; this
0x180019b7b  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x180019b80  xor     ecx, ecx
0x180019b82  mov     [rsp+998h+var_928], ecx
0x180019b86  mov     [rsp+998h+var_920], rcx
0x180019b8b  mov     [rsp+998h+var_918], rcx
0x180019b93  cmp     [r15+101h], cl
0x180019b9a  jnz     loc_180019DCF
0x180019ba0  cmp     [r15+102h], cl
0x180019ba7  jnz     loc_180019DCF
0x180019bad  mov     rax, [r15+0B0h]
0x180019bb4  mov     rcx, [rax+0D8h]
0x180019bbb  mov     [rsp+998h+var_8F8], rcx
0x180019bc3  mov     rsi, [rax+0E8h]
0x180019bca  mov     [rsp+998h+var_910], rsi
0x180019bd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bd9  lea     rax, WPP_GLOBAL_Control
0x180019be0  cmp     rcx, rax
0x180019be3  jz      short loc_180019C00
0x180019be5  test    byte ptr [rcx+1Ch], 4
0x180019be9  jz      short loc_180019C00
0x180019beb  mov     edx, 16h
0x180019bf0  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180019bf7  mov     rcx, [rcx+10h]
0x180019bfb  call    WPP_SF_
0x180019c00  mov     rdi, [rsp+998h+var_8D0]
0x180019c08  mov     rcx, [rdi+8]
0x180019c0c  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180019c11  mov     ebx, eax
0x180019c13  mov     rdi, [rdi]
0x180019c16  mov     rcx, [rsp+998h+var_900]
0x180019c1e  mov     rcx, [rcx+8]
0x180019c22  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180019c27  movzx   ecx, byte ptr [r15+10h]
0x180019c2c  lea     rdx, [rsp+998h+var_918]
0x180019c34  mov     [rsp+998h+var_940], rdx
0x180019c39  lea     rdx, [rsp+998h+var_928]
0x180019c3e  mov     [rsp+998h+var_948], rdx
0x180019c43  lea     rdx, [rsp+998h+var_920]
0x180019c48  mov     [rsp+998h+var_950], rdx
0x180019c4d  mov     dword ptr [rsp+998h+var_958], ebx
0x180019c51  mov     [rsp+998h+var_960], rdi
0x180019c56  mov     dword ptr [rsp+998h+var_968], eax
0x180019c5a  mov     rdi, [rsp+998h+var_900]
0x180019c62  mov     r9, [rdi]
0x180019c65  mov     [rsp+998h+var_970], r9
0x180019c6a  mov     [rsp+998h+var_978], 0
0x180019c73  xor     r9d, r9d
0x180019c76  mov     r8d, [rsp+998h+var_908]
0x180019c7e  mov     rdx, [rsp+998h+var_8C8]
0x180019c86  mov     rax, [rsp+998h+var_8F8]
0x180019c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c93  mov     ebx, eax
0x180019c95  test    eax, eax
0x180019c97  jz      loc_180019D89
0x180019c9d  lea     rdx, DebugErrorEvent
0x180019ca4  mov     rcx, cs:eaphost_Context
0x180019cab  call    cs:__imp_EtwEventEnabled
0x180019cb1  test    al, al
0x180019cb3  jz      short loc_180019CF9
0x180019cb5  mov     r9d, ebx
0x180019cb8  lea     r8, aRaseapgetident_4; "RasEapGetIdentity failed %d"
0x180019cbf  mov     edx, 800h; unsigned __int64
0x180019cc4  lea     rcx, [rsp+998h+var_848]; char *
0x180019ccc  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180019cd1  test    eax, eax
0x180019cd3  js      short loc_180019CF9
0x180019cd5  test    cs:byte_18004AF81, 8
0x180019cdc  jz      short loc_180019CF9
0x180019cde  lea     r8, [rsp+998h+var_848]
0x180019ce6  lea     rdx, DebugErrorEvent
0x180019ced  lea     rcx, eaphost_Context
0x180019cf4  call    McTemplateU0s_EtwEventWriteTransfer
0x180019cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d00  lea     rax, WPP_GLOBAL_Control
0x180019d07  cmp     rcx, rax
0x180019d0a  jz      short loc_180019D2A
0x180019d0c  test    byte ptr [rcx+1Ch], 1
0x180019d10  jz      short loc_180019D2A
0x180019d12  mov     edx, 17h
0x180019d17  mov     r9d, ebx
0x180019d1a  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180019d21  mov     rcx, [rcx+10h]
0x180019d25  call    WPP_SF_d
0x180019d2a  mov     cl, [r15+10h]
0x180019d2e  mov     [rsp+998h+var_8E8], cl
0x180019d35  mov     eax, [r15+14h]
0x180019d39  mov     dword ptr [rsp+998h+var_8E4], eax
0x180019d40  mov     eax, [r15+18h]
0x180019d44  mov     dword ptr [rsp+998h+var_8E4+4], eax
0x180019d4b  cmp     cl, 0FEh
0x180019d4e  jz      short loc_180019D5C
0x180019d50  mov     [rsp+998h+var_8E4], 0
0x180019d5c  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180019d63  mov     [rsp+998h+var_8F0], rax
0x180019d6b  mov     eax, [r15+1Ch]
0x180019d6f  mov     [rsp+998h+var_8D8], eax
0x180019d76  mov     r8d, ebx; unsigned int
0x180019d79  lea     rdx, [rsp+998h+var_8F0]; struct EapHost::EapMethodType *
0x180019d81  mov     ecx, ebx; unsigned int
0x180019d83  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180019d89  mov     edx, [rsp+998h+var_928]
0x180019d8d  mov     r8, [rsp+998h+var_920]
0x180019d92  mov     rcx, r12
0x180019d95  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180019d9a  mov     rdx, [rsp+998h+var_918]
0x180019da2  mov     rcx, r14
0x180019da5  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180019daa  nop
0x180019dab  mov     rcx, [rsp+998h+var_920]
0x180019db0  mov     rax, rsi
0x180019db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019db8  mov     rcx, [rsp+998h+var_918]
0x180019dc0  mov     rax, rsi
0x180019dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dc8  xor     esi, esi
0x180019dca  jmp     loc_180019F93
0x180019dcf  mov     rax, [r15+0B0h]
0x180019dd6  mov     r14, [rax+0D8h]
0x180019ddd  mov     r12, [rax+0E8h]
0x180019de4  mov     [rsp+998h+var_8F8], r12
0x180019dec  mov     [rsp+998h+var_910], rcx
0x180019df4  mov     rsi, [rsi]
0x180019df7  mov     rcx, [rsp+998h+var_8D0]
0x180019dff  mov     rcx, [rcx+8]
0x180019e03  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180019e08  mov     ebx, eax
0x180019e0a  mov     rdi, [rdi]
0x180019e0d  mov     rcx, [rsp+998h+var_900]
0x180019e15  mov     rcx, [rcx+8]
0x180019e19  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180019e1e  lea     rcx, [rsp+998h+var_910]
0x180019e26  mov     [rsp+998h+var_948], rcx
0x180019e2b  lea     rcx, [rsp+998h+var_918]
0x180019e33  mov     [rsp+998h+var_950], rcx
0x180019e38  lea     rcx, [rsp+998h+var_920]
0x180019e3d  mov     [rsp+998h+var_958], rcx
0x180019e42  lea     rcx, [rsp+998h+var_928]
0x180019e47  mov     [rsp+998h+var_960], rcx
0x180019e4c  mov     [rsp+998h+var_968], rsi
0x180019e51  mov     dword ptr [rsp+998h+var_970], ebx
0x180019e55  mov     [rsp+998h+var_978], rdi
0x180019e5a  mov     r9d, eax
0x180019e5d  mov     r8, [rsp+998h+var_8C8]
0x180019e65  mov     edx, [rsp+998h+var_908]
0x180019e6c  lea     rcx, [r15+10h]
0x180019e70  mov     rax, r14
0x180019e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e78  mov     ebx, eax
0x180019e7a  xor     esi, esi
0x180019e7c  test    eax, eax
0x180019e7e  jz      loc_180019F37
0x180019e84  mov     r8d, eax; unsigned int
0x180019e87  mov     rdx, [rsp+998h+var_910]; struct _EAP_ERROR *
0x180019e8f  lea     rcx, [rsp+998h+var_8A8]; this
0x180019e97  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180019e9c  nop
0x180019e9d  mov     rcx, [rsp+998h+var_910]
0x180019ea5  mov     rax, r12
0x180019ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180019eb4  lea     rax, WPP_GLOBAL_Control
0x180019ebb  cmp     rcx, rax
0x180019ebe  jz      short loc_180019EDC
0x180019ec0  test    byte ptr [rcx+1Ch], 1
0x180019ec4  jz      short loc_180019EDC
0x180019ec6  lea     edx, [rsi+15h]
0x180019ec9  mov     r9d, ebx
0x180019ecc  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180019ed3  mov     rcx, [rcx+10h]
0x180019ed7  call    WPP_SF_d
0x180019edc  mov     cl, [r15+10h]
0x180019ee0  mov     [rsp+998h+var_8E8], cl
0x180019ee7  mov     eax, [r15+14h]
0x180019eeb  mov     dword ptr [rsp+998h+var_8E4], eax
0x180019ef2  mov     eax, [r15+18h]
0x180019ef6  mov     dword ptr [rsp+998h+var_8E4+4], eax
0x180019efd  cmp     cl, 0FEh
0x180019f00  jz      short loc_180019F0A
0x180019f02  mov     [rsp+998h+var_8E4], rsi
0x180019f0a  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180019f11  mov     [rsp+998h+var_8F0], rax
0x180019f19  mov     eax, [r15+1Ch]
0x180019f1d  mov     [rsp+998h+var_8D8], eax
0x180019f24  mov     r8d, ebx; unsigned int
0x180019f27  lea     rdx, [rsp+998h+var_8F0]; struct EapHost::EapMethodType *
0x180019f2f  mov     ecx, ebx; unsigned int
0x180019f31  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180019f37  mov     edx, [rsp+998h+var_928]
0x180019f3b  mov     r8, [rsp+998h+var_920]
0x180019f40  mov     rcx, [rsp+998h+var_8C0]
0x180019f48  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180019f4d  mov     rdx, [rsp+998h+var_918]
0x180019f55  mov     r14, [rsp+998h+var_8B8]
0x180019f5d  mov     rcx, r14
0x180019f60  call    ?Assign@?$BasicSimpleString@_W@@QEAAXPEB_W@Z; BasicSimpleString<wchar_t>::Assign(wchar_t const *)
0x180019f65  nop
0x180019f66  mov     rcx, [rsp+998h+var_920]
0x180019f6b  mov     rax, r12
0x180019f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f73  mov     rcx, [rsp+998h+var_918]
0x180019f7b  mov     rax, r12
0x180019f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f83  mov     r12, [rsp+998h+var_8C0]
0x180019f8b  mov     rdi, [rsp+998h+var_900]
0x180019f93  lea     rdx, DebugInfoEvent
0x180019f9a  mov     rcx, cs:eaphost_Context
0x180019fa1  call    cs:__imp_EtwEventEnabled
0x180019fa7  lea     rbx, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x180019fae  test    al, al
0x180019fb0  jz      short loc_18001A018
0x180019fb2  mov     rcx, rbx
0x180019fb5  cmp     [r14], rsi
0x180019fb8  cmovnz  rcx, [r14]
0x180019fbc  mov     eax, [rsp+998h+var_928]
0x180019fc0  mov     [rsp+998h+var_968], rcx
0x180019fc5  mov     dword ptr [rsp+998h+var_970], eax
0x180019fc9  mov     rax, [r12+8]
0x180019fce  mov     [rsp+998h+var_978], rax
0x180019fd3  mov     r9, [rdi+8]
0x180019fd7  lea     r8, aRaseapgetident; "RasEapGetIdentity Exit:\n conn data(%Id"...
0x180019fde  mov     edx, 800h; unsigned __int64
0x180019fe3  lea     rcx, [rsp+998h+var_848]; char *
0x180019feb  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180019ff0  test    eax, eax
0x180019ff2  js      short loc_18001A018
0x180019ff4  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x180019ffb  jge     short loc_18001A018
0x180019ffd  lea     r8, [rsp+998h+var_848]
0x18001a005  lea     rdx, DebugInfoEvent
0x18001a00c  lea     rcx, eaphost_Context
0x18001a013  call    McTemplateU0s_EtwEventWriteTransfer
0x18001a018  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a01f  lea     rax, WPP_GLOBAL_Control
0x18001a026  cmp     rcx, rax
0x18001a029  jz      short loc_18001A05C
0x18001a02b  test    byte ptr [rcx+1Ch], 4
0x18001a02f  jz      short loc_18001A05C
0x18001a031  cmp     [r14], rsi
0x18001a034  cmovnz  rbx, [r14]
0x18001a038  mov     [rsp+998h+var_968], rbx
0x18001a03d  mov     eax, [rsp+998h+var_928]
0x18001a041  mov     dword ptr [rsp+998h+var_970], eax
0x18001a045  mov     rax, [r12+8]
0x18001a04a  mov     [rsp+998h+var_978], rax
0x18001a04f  mov     r9, [rdi+8]
0x18001a053  mov     rcx, [rcx+10h]
  ... truncated ...
```
