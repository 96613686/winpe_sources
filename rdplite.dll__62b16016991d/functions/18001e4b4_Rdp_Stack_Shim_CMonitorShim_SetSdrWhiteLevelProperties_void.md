# Rdp::Stack::Shim::CMonitorShim::SetSdrWhiteLevelProperties(void)

- ea: `0x18001e4b4`
- end: `0x18001e81b`
- name: `?SetSdrWhiteLevelProperties@CMonitorShim@Shim@Stack@Rdp@@AEAAXXZ`
- size: `871`
- prototype: `void __fastcall(Rdp::Stack::Shim::CMonitorShim *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cdfc`

## callees

- `0x18000141c`
- `0x18000260c`
- `0x180007b28`
- `0x18000b130`
- `0x18000cf28`
- `0x18000d98c`
- `0x18000db64`
- `0x18001e4b4`
- `0x18002a010`

## string_xrefs

- `0x18001e79a`: `Failed to open property store`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CMonitorShim::SetSdrWhiteLevelProperties(Rdp::Stack::Shim::CMonitorShim *this)
{
  int v2; // r8d
  int v3; // r9d
  int v4; // r13d
  int v5; // r12d
  int v6; // r15d
  int v7; // r14d
  int v8; // esi
  int v9; // edi
  int v10; // ebx
  _DWORD *v11; // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, Rdp::Utils::Props **); // rbx
  unsigned int v14; // eax
  __int64 v15; // rax
  unsigned int v16; // r9d
  unsigned int v17; // eax
  char *v18; // [rsp+28h] [rbp-81h]
  char *v19; // [rsp+28h] [rbp-81h]
  char *v20; // [rsp+28h] [rbp-81h]
  __int64 v21; // [rsp+30h] [rbp-79h]
  __int64 v22; // [rsp+38h] [rbp-71h]
  __int64 v23; // [rsp+40h] [rbp-69h]
  __int64 v24; // [rsp+48h] [rbp-61h]
  __int64 v25; // [rsp+50h] [rbp-59h]
  __int64 v26; // [rsp+58h] [rbp-51h]
  int v27; // [rsp+60h] [rbp-49h]
  int v28; // [rsp+68h] [rbp-41h]
  int v29; // [rsp+70h] [rbp-39h]
  int v30; // [rsp+78h] [rbp-31h]
  int v31; // [rsp+80h] [rbp-29h]
  const char *v32; // [rsp+90h] [rbp-19h] BYREF
  Rdp::Utils::Props *v33; // [rsp+98h] [rbp-11h] BYREF
  __int128 *v34; // [rsp+A0h] [rbp-9h] BYREF
  const char *v35; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v36; // [rsp+B0h] [rbp+7h] BYREF
  const char *v37; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  int v40; // [rsp+118h] [rbp+6Fh] BYREF
  int v41; // [rsp+120h] [rbp+77h] BYREF
  __int64 v42; // [rsp+128h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v40 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 80LL))(*((_QWORD *)this + 30)) + 8);
    v41 = *(_DWORD *)(*((_QWORD *)this + 29) + 336LL);
    v42 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30));
    v32 = "SDR white level";
    v34 = &xmmword_18003CA50;
    v35 = "RdpLite";
    v36 = 0x1000000;
    v37 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)byte_180035B73,
      v2,
      v3,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v32,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v40);
  }
  v40 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 80LL))(*((_QWORD *)this + 30)) + 8);
  v41 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                           + 15);
  LODWORD(v42) = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                                    + 14);
  LODWORD(v32) = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                                    + 13);
  v4 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                          + 12);
  v5 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                          + 11);
  v6 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                          + 10);
  v7 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                          + 9);
  v8 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                          + 8);
  v9 = *(unsigned __int16 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                           + 6);
  v10 = *(unsigned __int16 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                            + 4);
  v11 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30));
  v31 = v40;
  v30 = v41;
  v29 = v42;
  v28 = (int)v32;
  v27 = v4;
  LODWORD(v26) = v5;
  LODWORD(v25) = v6;
  LODWORD(v24) = v7;
  LODWORD(v23) = v8;
  LODWORD(v22) = v9;
  LODWORD(v21) = v10;
  LODWORD(v18) = *v11;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}, SDR white level: %d",
    "Rdp::Stack::Shim::CMonitorShim::SetSdrWhiteLevelProperties",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    0x31Cu,
    v18,
    v21,
    v22,
    v23,
    v24,
    v25,
    v26,
    v27,
    v28,
    v29,
    v30,
    v31);
  v33 = 0;
  v12 = *((_QWORD *)this + 28);
  v13 = *(__int64 (__fastcall **)(__int64, Rdp::Utils::Props **))(*(_QWORD *)v12 + 24LL);
  wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(&v33);
  v14 = v13(v12, &v33);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x323,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v14,
    (int)"Failed to open property store",
    v19);
  v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 80LL))(*((_QWORD *)this + 30));
  v17 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v33,
          (struct IPropertyStore *)&PKEY_Sdr_White_Level,
          (const struct _tagpropertykey *)*(unsigned int *)(v15 + 8),
          v16);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x32A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v17,
    (int)"Failed to set PKEY_Sdr_White_Level property",
    v20);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v33);
}

```

## disassembly

```asm
0x18001e4b4  mov     [rsp-8+arg_0], rcx
0x18001e4b9  push    rbp
0x18001e4ba  push    rbx
0x18001e4bb  push    rsi
0x18001e4bc  push    rdi
0x18001e4bd  push    r12
0x18001e4bf  push    r13
0x18001e4c1  push    r14
0x18001e4c3  push    r15
0x18001e4c5  lea     rbp, [rsp-1Fh]
0x18001e4ca  sub     rsp, 0C8h
0x18001e4d1  mov     rbx, rcx
0x18001e4d4  mov     eax, cs:dword_18003C058
0x18001e4da  cmp     eax, 4
0x18001e4dd  jbe     loc_18001E5D0
0x18001e4e3  mov     rdx, 470000000000h
0x18001e4ed  lea     rcx, dword_18003C058
0x18001e4f4  call    _tlgKeywordOn
0x18001e4f9  test    al, al
0x18001e4fb  jz      loc_18001E5D0
0x18001e501  mov     rcx, [rbx+0F0h]
0x18001e508  mov     rax, [rcx]
0x18001e50b  mov     rax, [rax+50h]
0x18001e50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e514  mov     ecx, [rax+8]
0x18001e517  mov     [rbp+57h+arg_8], ecx
0x18001e51a  mov     rax, [rbx+0E8h]
0x18001e521  mov     ecx, [rax+150h]
0x18001e527  mov     [rbp+57h+arg_10], ecx
0x18001e52a  mov     rcx, [rbx+0F0h]
0x18001e531  mov     rax, [rcx]
0x18001e534  mov     rax, [rax+28h]
0x18001e538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e53d  mov     [rbp+57h+arg_18], rax
0x18001e541  lea     rax, aSdrWhiteLevel; "SDR white level"
0x18001e548  mov     [rbp+57h+var_70], rax
0x18001e54c  lea     rax, xmmword_18003CA50
0x18001e553  mov     [rbp+57h+var_60], rax
0x18001e557  lea     rax, aRdplite; "RdpLite"
0x18001e55e  mov     [rbp+57h+var_58], rax
0x18001e562  mov     [rbp+57h+var_50], 1000000h
0x18001e56a  lea     rax, aCheckpoint; "Checkpoint"
0x18001e571  mov     [rbp+57h+var_48], rax
0x18001e575  lea     rax, [rbp+57h+arg_8]
0x18001e579  mov     [rsp+100h+var_A8], rax
0x18001e57e  lea     rax, [rbp+57h+arg_10]
0x18001e582  mov     [rsp+100h+var_B0], rax
0x18001e587  lea     rax, [rbp+57h+arg_18]
0x18001e58b  mov     [rsp+100h+var_B8], rax
0x18001e590  lea     rax, [rbp+57h+var_70]
0x18001e594  mov     [rsp+100h+var_C0], rax
0x18001e599  lea     rax, [rbp+57h+var_60]
0x18001e59d  mov     [rsp+100h+var_C8], rax
0x18001e5a2  lea     rax, [rbp+57h+var_58]
0x18001e5a6  mov     [rsp+100h+var_D0], rax
0x18001e5ab  lea     rax, [rbp+57h+var_50]
0x18001e5af  mov     [rsp+100h+var_D8], rax
0x18001e5b4  lea     rax, [rbp+57h+var_48]
0x18001e5b8  mov     qword ptr [rsp+100h+var_E0], rax
0x18001e5bd  lea     rdx, byte_180035B73
0x18001e5c4  lea     rcx, dword_18003C058
0x18001e5cb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001e5d0  mov     rcx, [rbx+0F0h]
0x18001e5d7  mov     rax, [rcx]
0x18001e5da  mov     rax, [rax+50h]
0x18001e5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5e3  mov     eax, [rax+8]
0x18001e5e6  mov     [rbp+57h+arg_8], eax
0x18001e5e9  mov     rcx, [rbx+0F0h]
0x18001e5f0  mov     rax, [rcx]
0x18001e5f3  mov     rax, [rax+28h]
0x18001e5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5fc  movzx   eax, byte ptr [rax+0Fh]
0x18001e600  mov     [rbp+57h+arg_10], eax
0x18001e603  mov     rcx, [rbx+0F0h]
0x18001e60a  mov     rax, [rcx]
0x18001e60d  mov     rax, [rax+28h]
0x18001e611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e616  movzx   eax, byte ptr [rax+0Eh]
0x18001e61a  mov     dword ptr [rbp+57h+arg_18], eax
0x18001e61d  mov     rcx, [rbx+0F0h]
0x18001e624  mov     rax, [rcx]
0x18001e627  mov     rax, [rax+28h]
0x18001e62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e630  movzx   eax, byte ptr [rax+0Dh]
0x18001e634  mov     dword ptr [rbp+57h+var_70], eax
0x18001e637  mov     rcx, [rbx+0F0h]
0x18001e63e  mov     rax, [rcx]
0x18001e641  mov     rax, [rax+28h]
0x18001e645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e64a  movzx   r13d, byte ptr [rax+0Ch]
0x18001e64f  mov     rcx, [rbx+0F0h]
0x18001e656  mov     rax, [rcx]
0x18001e659  mov     rax, [rax+28h]
0x18001e65d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e662  movzx   r12d, byte ptr [rax+0Bh]
0x18001e667  mov     rcx, [rbx+0F0h]
0x18001e66e  mov     rax, [rcx]
0x18001e671  mov     rax, [rax+28h]
0x18001e675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e67a  movzx   r15d, byte ptr [rax+0Ah]
0x18001e67f  mov     rcx, [rbx+0F0h]
0x18001e686  mov     rax, [rcx]
0x18001e689  mov     rax, [rax+28h]
0x18001e68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e692  movzx   r14d, byte ptr [rax+9]
0x18001e697  mov     rcx, [rbx+0F0h]
0x18001e69e  mov     rax, [rcx]
0x18001e6a1  mov     rax, [rax+28h]
0x18001e6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6aa  movzx   esi, byte ptr [rax+8]
0x18001e6ae  mov     rcx, [rbx+0F0h]
0x18001e6b5  mov     rax, [rcx]
0x18001e6b8  mov     rax, [rax+28h]
0x18001e6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6c1  movzx   edi, word ptr [rax+6]
0x18001e6c5  mov     rcx, [rbx+0F0h]
0x18001e6cc  mov     rax, [rcx]
0x18001e6cf  mov     rax, [rax+28h]
0x18001e6d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6d8  movzx   ebx, word ptr [rax+4]
0x18001e6dc  mov     rcx, [rbp+57h+arg_0]
0x18001e6e0  mov     rcx, [rcx+0F0h]
0x18001e6e7  mov     rax, [rcx]
0x18001e6ea  mov     rax, [rax+28h]
0x18001e6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f3  mov     ecx, [rbp+57h+arg_8]
0x18001e6f6  mov     [rsp+100h+var_80], ecx
0x18001e6fd  mov     ecx, [rbp+57h+arg_10]
0x18001e700  mov     [rsp+100h+var_88], ecx
0x18001e704  mov     ecx, dword ptr [rbp+57h+arg_18]
0x18001e707  mov     [rsp+100h+var_90], ecx
0x18001e70b  mov     ecx, dword ptr [rbp+57h+var_70]
0x18001e70e  mov     [rsp+100h+var_98], ecx
0x18001e712  mov     [rsp+100h+var_A0], r13d
0x18001e717  mov     dword ptr [rsp+100h+var_A8], r12d
0x18001e71c  mov     dword ptr [rsp+100h+var_B0], r15d
0x18001e721  mov     dword ptr [rsp+100h+var_B8], r14d
0x18001e726  mov     dword ptr [rsp+100h+var_C0], esi
0x18001e72a  mov     dword ptr [rsp+100h+var_C8], edi
0x18001e72e  mov     dword ptr [rsp+100h+var_D0], ebx
0x18001e732  mov     eax, [rax]
0x18001e734  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x18001e738  mov     [rsp+100h+var_E0], 31Ch; unsigned int
0x18001e740  lea     r14, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001e747  mov     r9, r14; char *
0x18001e74a  lea     r8, aRdpStackShimCm_2; "Rdp::Stack::Shim::CMonitorShim::SetSdrW"...
0x18001e751  lea     rdx, aId08lx04hx04hx_1; "Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02h"...
0x18001e758  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001e75f  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001e764  mov     [rbp+57h+var_68], 0
0x18001e76c  mov     rsi, [rbp+57h+arg_0]
0x18001e770  mov     rdi, [rsi+0E0h]
0x18001e777  mov     rax, [rdi]
0x18001e77a  mov     rbx, [rax+18h]
0x18001e77e  lea     rcx, [rbp+57h+var_68]
0x18001e782  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18001e787  lea     rdx, [rbp+57h+var_68]
0x18001e78b  mov     rcx, rdi
0x18001e78e  mov     rax, rbx
0x18001e791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e796  mov     rcx, [rbp+5Fh]; this
0x18001e79a  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x18001e7a1  mov     qword ptr [rsp+100h+var_E0], rdx; int
0x18001e7a6  mov     r9d, eax; char *
0x18001e7a9  mov     r8, r14; unsigned int
0x18001e7ac  mov     edx, 323h; void *
0x18001e7b1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001e7b6  mov     rcx, [rsi+0F0h]
0x18001e7bd  mov     rax, [rcx]
0x18001e7c0  mov     rax, [rax+50h]
0x18001e7c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7c9  mov     r8d, [rax+8]; struct _tagpropertykey *
0x18001e7cd  lea     rdx, PKEY_Sdr_White_Level; struct IPropertyStore *
0x18001e7d4  mov     rcx, [rbp+57h+var_68]; this
0x18001e7d8  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001e7dd  mov     rcx, [rbp+5Fh]; this
0x18001e7e1  lea     rdx, aFailedToSetPke_17; "Failed to set PKEY_Sdr_White_Level prop"...
0x18001e7e8  mov     qword ptr [rsp+100h+var_E0], rdx; int
0x18001e7ed  mov     r9d, eax; char *
0x18001e7f0  mov     r8, r14; unsigned int
0x18001e7f3  mov     edx, 32Ah; void *
0x18001e7f8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001e7fd  nop
0x18001e7fe  lea     rcx, [rbp+57h+var_68]
0x18001e802  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001e807  add     rsp, 0C8h
0x18001e80e  pop     r15
0x18001e810  pop     r14
0x18001e812  pop     r13
0x18001e814  pop     r12
0x18001e816  pop     rdi
0x18001e817  pop     rsi
0x18001e818  pop     rbx
0x18001e819  pop     rbp
0x18001e81a  retn
```
