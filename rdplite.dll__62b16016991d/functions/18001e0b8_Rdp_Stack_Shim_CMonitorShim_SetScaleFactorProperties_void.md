# Rdp::Stack::Shim::CMonitorShim::SetScaleFactorProperties(void)

- ea: `0x18001e0b8`
- end: `0x18001e4ac`
- name: `?SetScaleFactorProperties@CMonitorShim@Shim@Stack@Rdp@@AEAAXXZ`
- size: `1012`
- prototype: `void __fastcall(Rdp::Stack::Shim::CMonitorShim *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cdfc`

## callees

- `0x18000141c`
- `0x18000275c`
- `0x180007b28`
- `0x18000b130`
- `0x18000cf28`
- `0x18000d98c`
- `0x18000db64`
- `0x18001e0b8`
- `0x18002a010`

## string_xrefs

- `0x18001e3e4`: `Failed to open property store`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CMonitorShim::SetScaleFactorProperties(Rdp::Stack::Shim::CMonitorShim *this)
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
  Rdp::Stack::Shim::CMonitorShim *v12; // rsi
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, Rdp::Utils::Props **); // rbx
  unsigned int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // r9d
  unsigned int v18; // eax
  __int64 v19; // rax
  unsigned int v20; // r9d
  unsigned int v21; // eax
  char *v22; // [rsp+28h] [rbp-91h]
  char *v23; // [rsp+28h] [rbp-91h]
  char *v24; // [rsp+28h] [rbp-91h]
  char *v25; // [rsp+28h] [rbp-91h]
  __int64 v26; // [rsp+30h] [rbp-89h]
  __int64 v27; // [rsp+38h] [rbp-81h]
  __int64 v28; // [rsp+40h] [rbp-79h]
  __int64 v29; // [rsp+48h] [rbp-71h]
  __int64 v30; // [rsp+50h] [rbp-69h]
  __int64 v31; // [rsp+58h] [rbp-61h]
  __int64 v32; // [rsp+60h] [rbp-59h]
  __int64 v33; // [rsp+68h] [rbp-51h]
  int v34; // [rsp+70h] [rbp-49h]
  int v35; // [rsp+78h] [rbp-41h]
  int v36; // [rsp+80h] [rbp-39h]
  Rdp::Utils::Props *v37; // [rsp+90h] [rbp-29h] BYREF
  __int64 v38; // [rsp+98h] [rbp-21h] BYREF
  __int64 v39; // [rsp+A0h] [rbp-19h] BYREF
  const char *v40; // [rsp+A8h] [rbp-11h] BYREF
  __int128 *v41; // [rsp+B0h] [rbp-9h] BYREF
  const char *v42; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v43; // [rsp+C0h] [rbp+7h] BYREF
  const char *v44; // [rsp+C8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  int v47; // [rsp+128h] [rbp+6Fh] BYREF
  int v48; // [rsp+130h] [rbp+77h] BYREF
  int v49; // [rsp+138h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v38 = *(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 88LL))(*((_QWORD *)this + 30)) + 8);
    v47 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 56LL))(*((_QWORD *)this + 30)) + 12);
    v48 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 56LL))(*((_QWORD *)this + 30)) + 8);
    v49 = *(_DWORD *)(*((_QWORD *)this + 29) + 336LL);
    v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30));
    v40 = "Scale factor";
    v41 = &xmmword_18003CA50;
    v42 = "RdpLite";
    v43 = 0x1000000;
    v44 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)byte_180035D23,
      v2,
      v3,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v47,
      (__int64)&v38);
  }
  v47 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 56LL))(*((_QWORD *)this + 30)) + 8);
  v48 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                           + 15);
  v49 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                           + 14);
  LODWORD(v38) = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
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
  v36 = v47;
  v35 = v48;
  v34 = v49;
  LODWORD(v33) = v38;
  LODWORD(v32) = v4;
  LODWORD(v31) = v5;
  LODWORD(v30) = v6;
  LODWORD(v29) = v7;
  LODWORD(v28) = v8;
  LODWORD(v27) = v9;
  LODWORD(v26) = v10;
  LODWORD(v22) = *v11;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}, scale factor: %d",
    "Rdp::Stack::Shim::CMonitorShim::SetScaleFactorProperties",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    0x258u,
    v22,
    v26,
    v27,
    v28,
    v29,
    v30,
    v31,
    v32,
    v33,
    v34,
    v35,
    v36);
  v37 = 0;
  v12 = this;
  v13 = *((_QWORD *)this + 28);
  v14 = *(__int64 (__fastcall **)(__int64, Rdp::Utils::Props **))(*(_QWORD *)v13 + 24LL);
  wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(&v37);
  v15 = v14(v13, &v37);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x25F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v15,
    (int)"Failed to open property store",
    v23);
  v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 56LL))(*((_QWORD *)v12 + 30));
  v18 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v37,
          (struct IPropertyStore *)&PKEY_Desktop_Scale_Factor,
          (const struct _tagpropertykey *)*(unsigned int *)(v16 + 8),
          v17);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x266,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v18,
    (int)"Failed to set PKEY_Desktop_Scale_Factor property",
    v24);
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 56LL))(*((_QWORD *)v12 + 30));
  v21 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v37,
          (struct IPropertyStore *)&PKEY_Device_Scale_Factor,
          (const struct _tagpropertykey *)*(unsigned int *)(v19 + 12),
          v20);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x26D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v21,
    (int)"Failed to set PKEY_Device_Scale_Factor property",
    v25);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v37);
}

```

## disassembly

```asm
0x18001e0b8  mov     [rsp-8+arg_0], rcx
0x18001e0bd  push    rbp
0x18001e0be  push    rbx
0x18001e0bf  push    rsi
0x18001e0c0  push    rdi
0x18001e0c1  push    r12
0x18001e0c3  push    r13
0x18001e0c5  push    r14
0x18001e0c7  push    r15
0x18001e0c9  lea     rbp, [rsp-1Fh]
0x18001e0ce  sub     rsp, 0D8h
0x18001e0d5  mov     rbx, rcx
0x18001e0d8  mov     eax, cs:dword_18003C058
0x18001e0de  cmp     eax, 4
0x18001e0e1  jbe     loc_18001E21A
0x18001e0e7  mov     rdx, 470000000000h
0x18001e0f1  lea     rcx, dword_18003C058
0x18001e0f8  call    _tlgKeywordOn
0x18001e0fd  test    al, al
0x18001e0ff  jz      loc_18001E21A
0x18001e105  mov     rcx, [rbx+0F0h]
0x18001e10c  mov     rax, [rcx]
0x18001e10f  mov     rax, [rax+58h]
0x18001e113  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e118  mov     rcx, [rax+8]
0x18001e11c  mov     [rbp+57h+var_78], rcx
0x18001e120  mov     rcx, [rbx+0F0h]
0x18001e127  mov     rax, [rcx]
0x18001e12a  mov     rax, [rax+38h]
0x18001e12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e133  mov     ecx, [rax+0Ch]
0x18001e136  mov     [rbp+57h+arg_8], ecx
0x18001e139  mov     rcx, [rbx+0F0h]
0x18001e140  mov     rax, [rcx]
0x18001e143  mov     rax, [rax+38h]
0x18001e147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e14c  mov     ecx, [rax+8]
0x18001e14f  mov     [rbp+57h+arg_10], ecx
0x18001e152  mov     rax, [rbx+0E8h]
0x18001e159  mov     ecx, [rax+150h]
0x18001e15f  mov     [rbp+57h+arg_18], ecx
0x18001e162  mov     rcx, [rbx+0F0h]
0x18001e169  mov     rax, [rcx]
0x18001e16c  mov     rax, [rax+28h]
0x18001e170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e175  mov     [rbp+57h+var_70], rax
0x18001e179  lea     rax, aScaleFactor; "Scale factor"
0x18001e180  mov     [rbp+57h+var_68], rax
0x18001e184  lea     rax, xmmword_18003CA50
0x18001e18b  mov     [rbp+57h+var_60], rax
0x18001e18f  lea     rax, aRdplite; "RdpLite"
0x18001e196  mov     [rbp+57h+var_58], rax
0x18001e19a  mov     [rbp+57h+var_50], 1000000h
0x18001e1a2  lea     rax, aCheckpoint; "Checkpoint"
0x18001e1a9  mov     [rbp+57h+var_48], rax
0x18001e1ad  lea     rax, [rbp+57h+var_78]
0x18001e1b1  mov     [rsp+110h+var_A8], rax
0x18001e1b6  lea     rax, [rbp+57h+arg_8]
0x18001e1ba  mov     [rsp+110h+var_B0], rax
0x18001e1bf  lea     rax, [rbp+57h+arg_10]
0x18001e1c3  mov     [rsp+110h+var_B8], rax
0x18001e1c8  lea     rax, [rbp+57h+arg_18]
0x18001e1cc  mov     [rsp+110h+var_C0], rax
0x18001e1d1  lea     rax, [rbp+57h+var_70]
0x18001e1d5  mov     [rsp+110h+var_C8], rax
0x18001e1da  lea     rax, [rbp+57h+var_68]
0x18001e1de  mov     [rsp+110h+var_D0], rax
0x18001e1e3  lea     rax, [rbp+57h+var_60]
0x18001e1e7  mov     [rsp+110h+var_D8], rax
0x18001e1ec  lea     rax, [rbp+57h+var_58]
0x18001e1f0  mov     [rsp+110h+var_E0], rax
0x18001e1f5  lea     rax, [rbp+57h+var_50]
0x18001e1f9  mov     [rsp+110h+var_E8], rax
0x18001e1fe  lea     rax, [rbp+57h+var_48]
0x18001e202  mov     qword ptr [rsp+110h+var_F0], rax
0x18001e207  lea     rdx, byte_180035D23
0x18001e20e  lea     rcx, dword_18003C058
0x18001e215  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001e21a  mov     rcx, [rbx+0F0h]
0x18001e221  mov     rax, [rcx]
0x18001e224  mov     rax, [rax+38h]
0x18001e228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e22d  mov     eax, [rax+8]
0x18001e230  mov     [rbp+57h+arg_8], eax
0x18001e233  mov     rcx, [rbx+0F0h]
0x18001e23a  mov     rax, [rcx]
0x18001e23d  mov     rax, [rax+28h]
0x18001e241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e246  movzx   eax, byte ptr [rax+0Fh]
0x18001e24a  mov     [rbp+57h+arg_10], eax
0x18001e24d  mov     rcx, [rbx+0F0h]
0x18001e254  mov     rax, [rcx]
0x18001e257  mov     rax, [rax+28h]
0x18001e25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e260  movzx   eax, byte ptr [rax+0Eh]
0x18001e264  mov     [rbp+57h+arg_18], eax
0x18001e267  mov     rcx, [rbx+0F0h]
0x18001e26e  mov     rax, [rcx]
0x18001e271  mov     rax, [rax+28h]
0x18001e275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e27a  movzx   eax, byte ptr [rax+0Dh]
0x18001e27e  mov     dword ptr [rbp+57h+var_78], eax
0x18001e281  mov     rcx, [rbx+0F0h]
0x18001e288  mov     rax, [rcx]
0x18001e28b  mov     rax, [rax+28h]
0x18001e28f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e294  movzx   r13d, byte ptr [rax+0Ch]
0x18001e299  mov     rcx, [rbx+0F0h]
0x18001e2a0  mov     rax, [rcx]
0x18001e2a3  mov     rax, [rax+28h]
0x18001e2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2ac  movzx   r12d, byte ptr [rax+0Bh]
0x18001e2b1  mov     rcx, [rbx+0F0h]
0x18001e2b8  mov     rax, [rcx]
0x18001e2bb  mov     rax, [rax+28h]
0x18001e2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2c4  movzx   r15d, byte ptr [rax+0Ah]
0x18001e2c9  mov     rcx, [rbx+0F0h]
0x18001e2d0  mov     rax, [rcx]
0x18001e2d3  mov     rax, [rax+28h]
0x18001e2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2dc  movzx   r14d, byte ptr [rax+9]
0x18001e2e1  mov     rcx, [rbx+0F0h]
0x18001e2e8  mov     rax, [rcx]
0x18001e2eb  mov     rax, [rax+28h]
0x18001e2ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2f4  movzx   esi, byte ptr [rax+8]
0x18001e2f8  mov     rcx, [rbx+0F0h]
0x18001e2ff  mov     rax, [rcx]
0x18001e302  mov     rax, [rax+28h]
0x18001e306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e30b  movzx   edi, word ptr [rax+6]
0x18001e30f  mov     rcx, [rbx+0F0h]
0x18001e316  mov     rax, [rcx]
0x18001e319  mov     rax, [rax+28h]
0x18001e31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e322  movzx   ebx, word ptr [rax+4]
0x18001e326  mov     rcx, [rbp+57h+arg_0]
0x18001e32a  mov     rcx, [rcx+0F0h]
0x18001e331  mov     rax, [rcx]
0x18001e334  mov     rax, [rax+28h]
0x18001e338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e33d  mov     ecx, [rbp+57h+arg_8]
0x18001e340  mov     [rsp+110h+var_90], ecx
0x18001e347  mov     ecx, [rbp+57h+arg_10]
0x18001e34a  mov     [rsp+110h+var_98], ecx
0x18001e34e  mov     ecx, [rbp+57h+arg_18]
0x18001e351  mov     [rsp+110h+var_A0], ecx
0x18001e355  mov     ecx, dword ptr [rbp+57h+var_78]
0x18001e358  mov     dword ptr [rsp+110h+var_A8], ecx
0x18001e35c  mov     dword ptr [rsp+110h+var_B0], r13d
0x18001e361  mov     dword ptr [rsp+110h+var_B8], r12d
0x18001e366  mov     dword ptr [rsp+110h+var_C0], r15d
0x18001e36b  mov     dword ptr [rsp+110h+var_C8], r14d
0x18001e370  mov     dword ptr [rsp+110h+var_D0], esi
0x18001e374  mov     dword ptr [rsp+110h+var_D8], edi
0x18001e378  mov     dword ptr [rsp+110h+var_E0], ebx
0x18001e37c  mov     eax, [rax]
0x18001e37e  mov     dword ptr [rsp+110h+var_E8], eax; char *
0x18001e382  mov     [rsp+110h+var_F0], 258h; unsigned int
0x18001e38a  lea     r14, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001e391  mov     r9, r14; char *
0x18001e394  lea     r8, aRdpStackShimCm_0; "Rdp::Stack::Shim::CMonitorShim::SetScal"...
0x18001e39b  lea     rdx, aId08lx04hx04hx_2; "Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02h"...
0x18001e3a2  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001e3a9  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001e3ae  mov     [rbp+57h+var_80], 0
0x18001e3b6  mov     rsi, [rbp+57h+arg_0]
0x18001e3ba  mov     rdi, [rsi+0E0h]
0x18001e3c1  mov     rax, [rdi]
0x18001e3c4  mov     rbx, [rax+18h]
0x18001e3c8  lea     rcx, [rbp+57h+var_80]
0x18001e3cc  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18001e3d1  lea     rdx, [rbp+57h+var_80]
0x18001e3d5  mov     rcx, rdi
0x18001e3d8  mov     rax, rbx
0x18001e3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3e0  mov     rcx, [rbp+5Fh]; this
0x18001e3e4  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x18001e3eb  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x18001e3f0  mov     r9d, eax; char *
0x18001e3f3  mov     r8, r14; unsigned int
0x18001e3f6  mov     edx, 25Fh; void *
0x18001e3fb  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001e400  mov     rcx, [rsi+0F0h]
0x18001e407  mov     rax, [rcx]
0x18001e40a  mov     rax, [rax+38h]
0x18001e40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e413  mov     r8d, [rax+8]; struct _tagpropertykey *
0x18001e417  lea     rdx, PKEY_Desktop_Scale_Factor; struct IPropertyStore *
0x18001e41e  mov     rcx, [rbp+57h+var_80]; this
0x18001e422  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001e427  mov     rcx, [rbp+5Fh]; this
0x18001e42b  lea     rdx, aFailedToSetPke_3; "Failed to set PKEY_Desktop_Scale_Factor"...
0x18001e432  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x18001e437  mov     r9d, eax; char *
0x18001e43a  mov     r8, r14; unsigned int
0x18001e43d  mov     edx, 266h; void *
0x18001e442  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001e447  mov     rcx, [rsi+0F0h]
0x18001e44e  mov     rax, [rcx]
0x18001e451  mov     rax, [rax+38h]
0x18001e455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e45a  mov     r8d, [rax+0Ch]; struct _tagpropertykey *
0x18001e45e  lea     rdx, PKEY_Device_Scale_Factor; struct IPropertyStore *
0x18001e465  mov     rcx, [rbp+57h+var_80]; this
0x18001e469  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001e46e  mov     rcx, [rbp+5Fh]; this
0x18001e472  lea     rdx, aFailedToSetPke_38; "Failed to set PKEY_Device_Scale_Factor "...
0x18001e479  mov     qword ptr [rsp+110h+var_F0], rdx; int
0x18001e47e  mov     r9d, eax; char *
0x18001e481  mov     r8, r14; unsigned int
0x18001e484  mov     edx, 26Dh; void *
0x18001e489  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001e48e  nop
0x18001e48f  lea     rcx, [rbp+57h+var_80]
0x18001e493  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001e498  add     rsp, 0D8h
0x18001e49f  pop     r15
0x18001e4a1  pop     r14
0x18001e4a3  pop     r13
0x18001e4a5  pop     r12
0x18001e4a7  pop     rdi
0x18001e4a8  pop     rsi
0x18001e4a9  pop     rbx
0x18001e4aa  pop     rbp
0x18001e4ab  retn
```
