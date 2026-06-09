# EapLm::Peer::LegacyEapMethodConfig::CredentialsXml2Blob(uint,IXMLDOMDocument2 &,ConstBuffer const &,TempBuffer<0> &)

- ea: `0x1800188e0`
- end: `0x180018e08`
- name: `?CredentialsXml2Blob@LegacyEapMethodConfig@Peer@EapLm@@UEAAXIAEAUIXMLDOMDocument2@@AEBUConstBuffer@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `1320`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x180005894`
- `0x18000bf94`
- `0x18000d0e8`
- `0x1800126f8`
- `0x18001549c`
- `0x180016400`
- `0x1800188e0`
- `0x18001b154`
- `0x18002e494`
- `0x180034010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x180018932`
- `ntdll!EtwEventEnabled` at `0x180018bb5`
- `ntdll!EtwEventEnabled` at `0x180018cb6`
- `ntdll!EtwEventEnabled` at `0x180018932`
- `ntdll!EtwEventEnabled` at `0x180018bb5`
- `ntdll!EtwEventEnabled` at `0x180018cb6`

## string_xrefs

- `0x180018941`: `RasEapCreateUserPropertiesProc Entry:\n flags(%d)`
- `0x1800189e1`: `CredentialXml2Blob`
- `0x180018bc2`: `RasEapCreateUserProperties failed %d`
- `0x180018cc5`: `RasEapCreateUserPropertiesProc Exit:\n returning(%d) bytes`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::LegacyEapMethodConfig::CredentialsXml2Blob(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5)
{
  __int64 v8; // rax
  __int64 (__fastcall *v9)(_QWORD, _QWORD, _QWORD, __int64, _QWORD, int, _QWORD, _DWORD, const void **, unsigned int *); // r12
  void (__fastcall *v10)(const void *); // r13
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  unsigned int v14; // edi
  _QWORD *v15; // rdi
  int v16; // eax
  unsigned int v17; // edi
  unsigned int v19; // [rsp+60h] [rbp-8C8h] BYREF
  const void *v20; // [rsp+68h] [rbp-8C0h] BYREF
  __int64 v21; // [rsp+70h] [rbp-8B8h] BYREF
  __int64 v22; // [rsp+78h] [rbp-8B0h] BYREF
  void **v23; // [rsp+80h] [rbp-8A8h] BYREF
  char v24; // [rsp+88h] [rbp-8A0h]
  __int64 v25; // [rsp+8Ch] [rbp-89Ch]
  int v26; // [rsp+98h] [rbp-890h]
  _QWORD *v27; // [rsp+A0h] [rbp-888h]
  __int64 v28; // [rsp+A8h] [rbp-880h]
  void (__fastcall *v29)(const void *); // [rsp+B0h] [rbp-878h]
  void **v30; // [rsp+B8h] [rbp-870h]
  char v31; // [rsp+C0h] [rbp-868h]
  __int64 v32; // [rsp+C4h] [rbp-864h]
  int v33; // [rsp+D0h] [rbp-858h]
  char v34[2048]; // [rsp+E0h] [rbp-848h] BYREF

  v27 = a4;
  v28 = a5;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v34, 0x800u, "RasEapCreateUserPropertiesProc Entry:\n flags(%d)", a2) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v34);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, a2);
  EapLm::DelayLoadModule::LoadIfNeeded(*(EapLm::DelayLoadModule **)(a1 + 192), 1);
  v8 = *(_QWORD *)(a1 + 192);
  v9 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, _QWORD, int, _QWORD, _DWORD, const void **, unsigned int *))(v8 + 216);
  if ( !v9 )
  {
    if ( (Microsoft_Windows_EapHostEnableBits & 0x20) != 0 )
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, PeerFunctionNotSupported, "CredentialXml2Blob");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    v24 = *(_BYTE *)(a1 + 16);
    v25 = *(_QWORD *)(a1 + 20);
    if ( v24 != -2 )
      v25 = 0;
    v23 = &EapHost::EapMethodType::`vftable';
    v26 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(0x80420020, (const struct EapHost::EapMethodType *)&v23, 0x80420020);
  }
  v10 = *(void (__fastcall **)(const void *))(v8 + 232);
  v22 = 0;
  v31 = *(_BYTE *)(a1 + 16);
  v32 = *(_QWORD *)(a1 + 20);
  if ( v31 != -2 )
    v32 = 0;
  v30 = &EapHost::EapMethodType::`vftable';
  v33 = *(_DWORD *)(a1 + 28);
  v11 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 360LL))(a3, &v22);
  v12 = v11;
  if ( v11 < 0 || v11 == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    if ( (v12 & 0x1FFF0000) == 0x70000 )
      v12 = (unsigned __int16)v12;
    EapHost::EapException::Throw(v12, 0, 0);
  }
  v21 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 104LL))(v22, &v21);
  v14 = v13;
  if ( v13 < 0 || v13 == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids);
    if ( (v14 & 0x1FFF0000) == 0x70000 )
      v14 = (unsigned __int16)v14;
    EapHost::EapException::Throw(v14, 0, 0);
  }
  v29 = v10;
  v20 = 0;
  v19 = 0;
  v15 = v27;
  v16 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v27[1]);
  v17 = v9(*(unsigned __int8 *)(a1 + 16), a2, 0, v21, *v15, v16, 0, 0, &v20, &v19);
  if ( v17 )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
      && (int)StringCchPrintfA(v34, 0x800u, "RasEapCreateUserProperties failed %d", v17) >= 0
      && (byte_18004AF81 & 8) != 0 )
    {
      McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v34);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v17);
    v24 = *(_BYTE *)(a1 + 16);
    v25 = *(_QWORD *)(a1 + 20);
    if ( v24 != -2 )
      v25 = 0;
    v23 = &EapHost::EapMethodType::`vftable';
    v26 = *(_DWORD *)(a1 + 28);
    EapHost::EapException::Throw(v17, (const struct EapHost::EapMethodType *)&v23, v17);
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    TempBuffer<0>::Assign(v28, v19, v20);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v29(v20);
      throw;
    }
  }
  v10(v20);
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v34, 0x800u, "RasEapCreateUserPropertiesProc Exit:\n returning(%d) bytes", v19) >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v34);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids, v19);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v21);
  return ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v22);
}

```

## disassembly

```asm
0x1800188e0  push    rbx
0x1800188e2  push    rsi
0x1800188e3  push    rdi
0x1800188e4  push    r12
0x1800188e6  push    r13
0x1800188e8  push    r15
0x1800188ea  sub     rsp, 8F8h
0x1800188f1  mov     rax, cs:__security_cookie
0x1800188f8  xor     rax, rsp
0x1800188fb  mov     [rsp+928h+var_48], rax
0x180018903  mov     [rsp+928h+var_888], r9
0x18001890b  mov     rdi, r8
0x18001890e  mov     r15d, edx
0x180018911  mov     rbx, rcx
0x180018914  mov     rax, [rsp+928h+arg_20]
0x18001891c  mov     [rsp+928h+var_880], rax
0x180018924  lea     rdx, DebugInfoEvent
0x18001892b  mov     rcx, cs:eaphost_Context
0x180018932  call    cs:__imp_EtwEventEnabled
0x180018938  xor     esi, esi
0x18001893a  test    al, al
0x18001893c  jz      short loc_180018982
0x18001893e  mov     r9d, r15d
0x180018941  lea     r8, aRaseapcreateus_2; "RasEapCreateUserPropertiesProc Entry:\n"...
0x180018948  mov     edx, 800h; unsigned __int64
0x18001894d  lea     rcx, [rsp+928h+var_848]; char *
0x180018955  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001895a  test    eax, eax
0x18001895c  js      short loc_180018982
0x18001895e  cmp     cs:Microsoft_Windows_EapHostEnableBits, sil
0x180018965  jge     short loc_180018982
0x180018967  lea     r8, [rsp+928h+var_848]
0x18001896f  lea     rdx, DebugInfoEvent
0x180018976  lea     rcx, eaphost_Context
0x18001897d  call    McTemplateU0s_EtwEventWriteTransfer
0x180018982  lea     r13, WPP_GLOBAL_Control
0x180018989  mov     rcx, cs:WPP_GLOBAL_Control
0x180018990  cmp     rcx, r13
0x180018993  jz      short loc_1800189B3
0x180018995  test    byte ptr [rcx+1Ch], 4
0x180018999  jz      short loc_1800189B3
0x18001899b  mov     edx, 2Ah ; '*'
0x1800189a0  mov     r9d, r15d
0x1800189a3  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x1800189aa  mov     rcx, [rcx+10h]
0x1800189ae  call    WPP_SF_d
0x1800189b3  mov     dl, 1; bool
0x1800189b5  mov     rcx, [rbx+0C0h]; this
0x1800189bc  call    ?LoadIfNeeded@DelayLoadModule@EapLm@@QEAA_N_N@Z; EapLm::DelayLoadModule::LoadIfNeeded(bool)
0x1800189c1  mov     rax, [rbx+0C0h]
0x1800189c8  mov     r12, [rax+0D8h]
0x1800189cf  test    r12, r12
0x1800189d2  jnz     loc_180018A7C
0x1800189d8  test    cs:Microsoft_Windows_EapHostEnableBits, 20h
0x1800189df  jz      short loc_1800189FB
0x1800189e1  lea     r8, aCredentialxml2; "CredentialXml2Blob"
0x1800189e8  lea     rdx, PeerFunctionNotSupported
0x1800189ef  lea     rcx, eaphost_Context
0x1800189f6  call    McTemplateU0s_EtwEventWriteTransfer
0x1800189fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a02  cmp     rcx, r13
0x180018a05  jz      short loc_180018A22
0x180018a07  test    byte ptr [rcx+1Ch], 1
0x180018a0b  jz      short loc_180018A22
0x180018a0d  mov     edx, 2Bh ; '+'
0x180018a12  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180018a19  mov     rcx, [rcx+10h]
0x180018a1d  call    WPP_SF_
0x180018a22  mov     cl, [rbx+10h]
0x180018a25  mov     [rsp+928h+var_8A0], cl
0x180018a2c  mov     eax, [rbx+14h]
0x180018a2f  mov     dword ptr [rsp+928h+var_89C], eax
0x180018a36  mov     eax, [rbx+18h]
0x180018a39  mov     dword ptr [rsp+928h+var_89C+4], eax
0x180018a40  cmp     cl, 0FEh
0x180018a43  jz      short loc_180018A4D
0x180018a45  mov     [rsp+928h+var_89C], rsi
0x180018a4d  lea     rsi, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180018a54  mov     [rsp+928h+var_8A8], rsi
0x180018a5c  mov     eax, [rbx+1Ch]
0x180018a5f  mov     [rsp+928h+var_890], eax
0x180018a66  mov     ecx, 80420020h; unsigned int
0x180018a6b  mov     r8d, ecx; unsigned int
0x180018a6e  lea     rdx, [rsp+928h+var_8A8]; struct EapHost::EapMethodType *
0x180018a76  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180018a7c  mov     r13, [rax+0E8h]
0x180018a83  mov     [rsp+928h+var_8B0], rsi
0x180018a88  mov     cl, [rbx+10h]
0x180018a8b  mov     [rsp+928h+var_868], cl
0x180018a92  mov     eax, [rbx+14h]
0x180018a95  mov     dword ptr [rsp+928h+var_864], eax
0x180018a9c  mov     eax, [rbx+18h]
0x180018a9f  mov     dword ptr [rsp+928h+var_864+4], eax
0x180018aa6  cmp     cl, 0FEh
0x180018aa9  jz      short loc_180018AB3
0x180018aab  mov     [rsp+928h+var_864], rsi
0x180018ab3  lea     rsi, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180018aba  mov     [rsp+928h+var_870], rsi
0x180018ac2  mov     eax, [rbx+1Ch]
0x180018ac5  mov     [rsp+928h+var_858], eax
0x180018acc  mov     rax, [rdi]
0x180018acf  lea     rdx, [rsp+928h+var_8B0]
0x180018ad4  mov     rcx, rdi
0x180018ad7  mov     rax, [rax+168h]
0x180018ade  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ae3  mov     edi, eax
0x180018ae5  test    eax, eax
0x180018ae7  js      loc_180018DBC
0x180018aed  cmp     eax, 1
0x180018af0  jz      loc_180018DBC
0x180018af6  mov     [rsp+928h+var_8B8], 0
0x180018aff  mov     rcx, [rsp+928h+var_8B0]
0x180018b04  mov     rax, [rcx]
0x180018b07  lea     rdx, [rsp+928h+var_8B8]
0x180018b0c  mov     rax, [rax+68h]
0x180018b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b15  mov     edi, eax
0x180018b17  test    eax, eax
0x180018b19  js      loc_180018D70
0x180018b1f  cmp     eax, 1
0x180018b22  jz      loc_180018D70
0x180018b28  mov     [rsp+928h+var_878], r13
0x180018b30  mov     [rsp+928h+var_8C0], 0
0x180018b39  mov     [rsp+928h+var_8C8], 0
0x180018b41  mov     rdi, [rsp+928h+var_888]
0x180018b49  mov     rcx, [rdi+8]
0x180018b4d  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x180018b52  movzx   ecx, byte ptr [rbx+10h]
0x180018b56  lea     rdx, [rsp+928h+var_8C8]
0x180018b5b  mov     [rsp+928h+var_8E0], rdx
0x180018b60  lea     rdx, [rsp+928h+var_8C0]
0x180018b65  mov     [rsp+928h+var_8E8], rdx
0x180018b6a  mov     [rsp+928h+var_8F0], 0
0x180018b72  mov     [rsp+928h+var_8F8], 0
0x180018b7b  mov     [rsp+928h+var_900], eax
0x180018b7f  mov     r8, [rdi]
0x180018b82  mov     [rsp+928h+var_908], r8
0x180018b87  mov     r9, [rsp+928h+var_8B8]
0x180018b8c  xor     r8d, r8d
0x180018b8f  mov     edx, r15d
0x180018b92  mov     rax, r12
0x180018b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018b9a  mov     edi, eax
0x180018b9c  xor     r15d, r15d
0x180018b9f  test    eax, eax
0x180018ba1  jz      loc_180018C84
0x180018ba7  lea     rdx, DebugErrorEvent
0x180018bae  mov     rcx, cs:eaphost_Context
0x180018bb5  call    cs:__imp_EtwEventEnabled
0x180018bbb  test    al, al
0x180018bbd  jz      short loc_180018C03
0x180018bbf  mov     r9d, edi
0x180018bc2  lea     r8, aRaseapcreateus; "RasEapCreateUserProperties failed %d"
0x180018bc9  mov     edx, 800h; unsigned __int64
0x180018bce  lea     rcx, [rsp+928h+var_848]; char *
0x180018bd6  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180018bdb  test    eax, eax
0x180018bdd  js      short loc_180018C03
0x180018bdf  test    cs:byte_18004AF81, 8
0x180018be6  jz      short loc_180018C03
0x180018be8  lea     r8, [rsp+928h+var_848]
0x180018bf0  lea     rdx, DebugErrorEvent
0x180018bf7  lea     rcx, eaphost_Context
0x180018bfe  call    McTemplateU0s_EtwEventWriteTransfer
0x180018c03  mov     rcx, cs:WPP_GLOBAL_Control
0x180018c0a  lea     rax, WPP_GLOBAL_Control
0x180018c11  cmp     rcx, rax
0x180018c14  jz      short loc_180018C34
0x180018c16  test    byte ptr [rcx+1Ch], 1
0x180018c1a  jz      short loc_180018C34
0x180018c1c  mov     edx, 2Eh ; '.'
0x180018c21  mov     r9d, edi
0x180018c24  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180018c2b  mov     rcx, [rcx+10h]
0x180018c2f  call    WPP_SF_d
0x180018c34  mov     cl, [rbx+10h]
0x180018c37  mov     [rsp+928h+var_8A0], cl
0x180018c3e  mov     eax, [rbx+14h]
0x180018c41  mov     dword ptr [rsp+928h+var_89C], eax
0x180018c48  mov     eax, [rbx+18h]
0x180018c4b  mov     dword ptr [rsp+928h+var_89C+4], eax
0x180018c52  cmp     cl, 0FEh
0x180018c55  jz      short loc_180018C5F
0x180018c57  mov     [rsp+928h+var_89C], r15
0x180018c5f  mov     [rsp+928h+var_8A8], rsi
0x180018c67  mov     eax, [rbx+1Ch]
0x180018c6a  mov     [rsp+928h+var_890], eax
0x180018c71  mov     r8d, edi; unsigned int
0x180018c74  lea     rdx, [rsp+928h+var_8A8]; struct EapHost::EapMethodType *
0x180018c7c  mov     ecx, edi; unsigned int
0x180018c7e  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180018c84  mov     edx, [rsp+928h+var_8C8]
0x180018c88  mov     r8, [rsp+928h+var_8C0]
0x180018c8d  mov     rcx, [rsp+928h+var_880]
0x180018c95  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x180018c9a  nop
0x180018c9b  mov     rcx, [rsp+928h+var_8C0]
0x180018ca0  mov     rax, r13
0x180018ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ca8  lea     rdx, DebugInfoEvent
0x180018caf  mov     rcx, cs:eaphost_Context
0x180018cb6  call    cs:__imp_EtwEventEnabled
0x180018cbc  test    al, al
0x180018cbe  jz      short loc_180018D06
0x180018cc0  mov     r9d, [rsp+928h+var_8C8]
0x180018cc5  lea     r8, aRaseapcreateus_0; "RasEapCreateUserPropertiesProc Exit:\n "...
0x180018ccc  mov     edx, 800h; unsigned __int64
0x180018cd1  lea     rcx, [rsp+928h+var_848]; char *
0x180018cd9  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180018cde  test    eax, eax
0x180018ce0  js      short loc_180018D06
0x180018ce2  cmp     cs:Microsoft_Windows_EapHostEnableBits, r15b
0x180018ce9  jge     short loc_180018D06
0x180018ceb  lea     r8, [rsp+928h+var_848]
0x180018cf3  lea     rdx, DebugInfoEvent
0x180018cfa  lea     rcx, eaphost_Context
0x180018d01  call    McTemplateU0s_EtwEventWriteTransfer
0x180018d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d0d  lea     rax, WPP_GLOBAL_Control
0x180018d14  cmp     rcx, rax
0x180018d17  jz      short loc_180018D3A
0x180018d19  test    byte ptr [rcx+1Ch], 4
0x180018d1d  jz      short loc_180018D3A
0x180018d1f  mov     edx, 2Fh ; '/'
0x180018d24  mov     r9d, [rsp+928h+var_8C8]
0x180018d29  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180018d30  mov     rcx, [rcx+10h]
0x180018d34  call    WPP_SF_d
0x180018d39  nop
0x180018d3a  lea     rcx, [rsp+928h+var_8B8]
0x180018d3f  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180018d44  nop
0x180018d45  lea     rcx, [rsp+928h+var_8B0]
0x180018d4a  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x180018d4f  mov     rcx, [rsp+928h+var_48]
0x180018d57  xor     rcx, rsp; StackCookie
0x180018d5a  call    __security_check_cookie
0x180018d5f  add     rsp, 8F8h
0x180018d66  pop     r15
0x180018d68  pop     r13
0x180018d6a  pop     r12
0x180018d6c  pop     rdi
0x180018d6d  pop     rsi
0x180018d6e  pop     rbx
0x180018d6f  retn
0x180018d70  mov     rcx, cs:WPP_GLOBAL_Control
0x180018d77  lea     rax, WPP_GLOBAL_Control
0x180018d7e  cmp     rcx, rax
0x180018d81  jz      short loc_180018D9E
0x180018d83  test    byte ptr [rcx+1Ch], 1
0x180018d87  jz      short loc_180018D9E
0x180018d89  mov     edx, 2Dh ; '-'
0x180018d8e  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180018d95  mov     rcx, [rcx+10h]
0x180018d99  call    WPP_SF_
0x180018d9e  mov     eax, edi
0x180018da0  and     eax, 1FFF0000h
0x180018da5  cmp     eax, 70000h
0x180018daa  jnz     short loc_180018DAF
0x180018dac  movzx   edi, di
0x180018daf  xor     r8d, r8d; unsigned int
0x180018db2  xor     edx, edx; struct EapHost::EapMethodType *
0x180018db4  mov     ecx, edi; unsigned int
0x180018db6  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
0x180018dbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180018dc3  lea     rax, WPP_GLOBAL_Control
0x180018dca  cmp     rcx, rax
0x180018dcd  jz      short loc_180018DEA
0x180018dcf  test    byte ptr [rcx+1Ch], 1
0x180018dd3  jz      short loc_180018DEA
0x180018dd5  mov     edx, 2Ch ; ','
0x180018dda  lea     r8, WPP_bdd278cc4a2236a1b28ad0748f885fa3_Traceguids
0x180018de1  mov     rcx, [rcx+10h]
0x180018de5  call    WPP_SF_
0x180018dea  mov     eax, edi
0x180018dec  and     eax, 1FFF0000h
0x180018df1  cmp     eax, 70000h
0x180018df6  jnz     short loc_180018DFB
0x180018df8  movzx   edi, di
0x180018dfb  xor     r8d, r8d; unsigned int
0x180018dfe  xor     edx, edx; struct EapHost::EapMethodType *
0x180018e00  mov     ecx, edi; unsigned int
0x180018e02  call    ?Throw@EapException@EapHost@@SAXIPEBVEapMethodType@2@I@Z; EapHost::EapException::Throw(uint,EapHost::EapMethodType const *,uint)
```
