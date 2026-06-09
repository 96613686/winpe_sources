# Rdp::Stack::Shim::CMonitorShim::SetDisplayModeProperties(void)

- ea: `0x18001d954`
- end: `0x18001e00a`
- name: `?SetDisplayModeProperties@CMonitorShim@Shim@Stack@Rdp@@AEAAXXZ`
- size: `1718`
- prototype: `void __fastcall(Rdp::Stack::Shim::CMonitorShim *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cdfc`

## callees

- `0x18000141c`
- `0x1800028d4`
- `0x180007b28`
- `0x18000b130`
- `0x18000cf28`
- `0x18000d98c`
- `0x18000db64`
- `0x180013f30`
- `0x18001d954`
- `0x18002a010`

## string_xrefs

- `0x18001dd2d`: `Failed to open property store`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CMonitorShim::SetDisplayModeProperties(Rdp::Stack::Shim::CMonitorShim *this)
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
  int v17; // r9d
  unsigned int v18; // eax
  __int64 v19; // rax
  int v20; // r9d
  unsigned int v21; // eax
  __int64 v22; // rax
  unsigned int v23; // r9d
  unsigned int v24; // eax
  __int64 v25; // rax
  unsigned int v26; // r9d
  unsigned int v27; // eax
  __int64 v28; // rax
  unsigned int v29; // r9d
  unsigned int v30; // eax
  __int64 v31; // rax
  unsigned int v32; // r9d
  unsigned int v33; // eax
  __int64 v34; // rax
  unsigned int v35; // r9d
  unsigned int v36; // eax
  __int64 v37; // rax
  unsigned int v38; // r9d
  unsigned int v39; // eax
  unsigned int v40; // ebx
  __int64 v41; // rax
  unsigned int v42; // r9d
  unsigned int v43; // eax
  char *v44; // [rsp+28h] [rbp-B1h]
  char *v45; // [rsp+28h] [rbp-B1h]
  char *v46; // [rsp+28h] [rbp-B1h]
  char *v47; // [rsp+28h] [rbp-B1h]
  char *v48; // [rsp+28h] [rbp-B1h]
  char *v49; // [rsp+28h] [rbp-B1h]
  char *v50; // [rsp+28h] [rbp-B1h]
  char *v51; // [rsp+28h] [rbp-B1h]
  char *v52; // [rsp+28h] [rbp-B1h]
  char *v53; // [rsp+28h] [rbp-B1h]
  char *v54; // [rsp+28h] [rbp-B1h]
  __int64 v55; // [rsp+30h] [rbp-A9h]
  __int64 v56; // [rsp+38h] [rbp-A1h]
  __int64 v57; // [rsp+40h] [rbp-99h]
  __int64 v58; // [rsp+48h] [rbp-91h]
  __int64 v59; // [rsp+50h] [rbp-89h]
  __int64 v60; // [rsp+58h] [rbp-81h]
  __int64 v61; // [rsp+60h] [rbp-79h]
  __int64 v62; // [rsp+68h] [rbp-71h]
  __int64 v63; // [rsp+70h] [rbp-69h]
  __int64 v64; // [rsp+78h] [rbp-61h]
  __int64 v65; // [rsp+80h] [rbp-59h]
  Rdp::Utils::Props *v66; // [rsp+A0h] [rbp-39h] BYREF
  int v67; // [rsp+A8h] [rbp-31h] BYREF
  int v68; // [rsp+ACh] [rbp-2Dh] BYREF
  int v69; // [rsp+B0h] [rbp-29h] BYREF
  int v70; // [rsp+B4h] [rbp-25h] BYREF
  __int64 v71; // [rsp+B8h] [rbp-21h] BYREF
  const char *v72; // [rsp+C0h] [rbp-19h] BYREF
  __int128 *v73; // [rsp+C8h] [rbp-11h] BYREF
  const char *v74; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v75; // [rsp+D8h] [rbp-1h] BYREF
  const char *v76; // [rsp+E0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]
  int v79; // [rsp+148h] [rbp+6Fh] BYREF
  int v80; // [rsp+150h] [rbp+77h] BYREF
  int v81; // [rsp+158h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v79 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30)) + 44);
    v80 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30)) + 28);
    v81 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30)) + 20);
    v70 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30)) + 16);
    v67 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30)) + 12);
    v68 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30)) + 8);
    v69 = *(_DWORD *)(*((_QWORD *)this + 29) + 336LL);
    v71 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30));
    v72 = "Display mode";
    v73 = &xmmword_18003CA50;
    v74 = "RdpLite";
    v75 = 0x1000000;
    v76 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)byte_180035DCB,
      v2,
      v3,
      (__int64)&v76,
      (__int64)&v75,
      (__int64)&v74,
      (__int64)&v73,
      (__int64)&v72,
      (__int64)&v71,
      (__int64)&v69,
      (__int64)&v68,
      (__int64)&v67,
      (__int64)&v70,
      (__int64)&v81,
      (__int64)&v80,
      (__int64)&v79);
  }
  v79 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30)) + 44);
  v80 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30)) + 20);
  v81 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 48LL))(*((_QWORD *)this + 30)) + 16);
  v69 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                           + 15);
  v68 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                           + 14);
  v67 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
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
  LODWORD(v65) = v81;
  LODWORD(v64) = v69;
  LODWORD(v63) = v68;
  LODWORD(v62) = v67;
  LODWORD(v61) = v4;
  LODWORD(v60) = v5;
  LODWORD(v59) = v6;
  LODWORD(v58) = v7;
  LODWORD(v57) = v8;
  LODWORD(v56) = v9;
  LODWORD(v55) = v10;
  LODWORD(v44) = *v11;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}, resolution: %dx%d, color mode: %d",
    "Rdp::Stack::Shim::CMonitorShim::SetDisplayModeProperties",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    0x1DEu,
    v44,
    v55,
    v56,
    v57,
    v58,
    v59,
    v60,
    v61,
    v62,
    v63,
    v64,
    v65,
    v80,
    v79);
  v66 = 0;
  v12 = this;
  v13 = *((_QWORD *)this + 28);
  v14 = *(__int64 (__fastcall **)(__int64, Rdp::Utils::Props **))(*(_QWORD *)v13 + 24LL);
  wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(&v66);
  v15 = v14(v13, &v66);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1E5,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v15,
    (int)"Failed to open property store",
    v45);
  v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 48LL))(*((_QWORD *)v12 + 30));
  v18 = Rdp::Utils::Props::IPropertyStore_SetInt32(
          v66,
          (struct IPropertyStore *)&PKEY_Primary_Monitor_Offset_X,
          (const struct _tagpropertykey *)*(unsigned int *)(v16 + 8),
          v17);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1EF,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v18,
    (int)"Failed to set PKEY_Primary_Monitor_Offset_X property",
    v46);
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 48LL))(*((_QWORD *)v12 + 30));
  v21 = Rdp::Utils::Props::IPropertyStore_SetInt32(
          v66,
          (struct IPropertyStore *)&PKEY_Primary_Monitor_Offset_Y,
          (const struct _tagpropertykey *)*(unsigned int *)(v19 + 12),
          v20);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x1F6,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v21,
    (int)"Failed to set PKEY_Primary_Monitor_Offset_Y property",
    v47);
  v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 48LL))(*((_QWORD *)v12 + 30));
  v24 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v66,
          (struct IPropertyStore *)&PKEY_Width_In_Pixels,
          (const struct _tagpropertykey *)*(unsigned int *)(v22 + 16),
          v23);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x200,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v24,
    (int)"Failed to set PKEY_Width_In_Pixels property",
    v48);
  v25 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 48LL))(*((_QWORD *)v12 + 30));
  v27 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v66,
          (struct IPropertyStore *)&PKEY_Height_In_Pixels,
          (const struct _tagpropertykey *)*(unsigned int *)(v25 + 20),
          v26);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x207,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v27,
    (int)"Failed to set PKEY_Height_In_Pixels property",
    v49);
  v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 48LL))(*((_QWORD *)v12 + 30));
  v30 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v66,
          (struct IPropertyStore *)&PKEY_Orientation,
          (const struct _tagpropertykey *)*(unsigned int *)(v28 + 28),
          v29);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x211,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v30,
    (int)"Failed to set PKEY_Orientation property",
    v50);
  v31 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 48LL))(*((_QWORD *)v12 + 30));
  v33 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v66,
          (struct IPropertyStore *)&PKEY_RefreshRate_Numerator,
          (const struct _tagpropertykey *)*(unsigned int *)(v31 + 32),
          v32);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x21B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v33,
    (int)"Failed to set PKEY_RefreshRate_Numerator property",
    v51);
  v34 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 48LL))(*((_QWORD *)v12 + 30));
  v36 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v66,
          (struct IPropertyStore *)&PKEY_RefreshRate_Denominator,
          (const struct _tagpropertykey *)*(unsigned int *)(v34 + 36),
          v35);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x222,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v36,
    (int)"Failed to set PKEY_RefreshRate_Denominator property",
    v52);
  v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 48LL))(*((_QWORD *)v12 + 30));
  v39 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v66,
          (struct IPropertyStore *)&PKEY_VSyncFreqDivider,
          (const struct _tagpropertykey *)*(unsigned int *)(v37 + 40),
          v38);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x22C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v39,
    (int)"Failed to set PKEY_VSyncFreqDivider property",
    v53);
  v40 = 0;
  v41 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 48LL))(*((_QWORD *)v12 + 30));
  switch ( *(_DWORD *)(v41 + 44) )
  {
    case 1:
      v40 = 1;
      break;
    case 2:
      v40 = 2;
      break;
    case 3:
      v40 = 3;
      break;
  }
  v43 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v66,
          (struct IPropertyStore *)&PKEY_Color_Mode,
          (const struct _tagpropertykey *)v40,
          v42);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x236,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v43,
    (int)"Failed to set PKEY_Color_Mode property",
    v54);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v66);
}

```

## disassembly

```asm
0x18001d954  mov     [rsp-8+arg_0], rcx
0x18001d959  push    rbp
0x18001d95a  push    rbx
0x18001d95b  push    rsi
0x18001d95c  push    rdi
0x18001d95d  push    r12
0x18001d95f  push    r13
0x18001d961  push    r14
0x18001d963  push    r15
0x18001d965  lea     rbp, [rsp-1Fh]
0x18001d96a  sub     rsp, 0F8h
0x18001d971  mov     rbx, rcx
0x18001d974  mov     eax, cs:dword_18003C058
0x18001d97a  cmp     eax, 4
0x18001d97d  jbe     loc_18001DB1D
0x18001d983  mov     rdx, 470000000000h
0x18001d98d  lea     rcx, dword_18003C058
0x18001d994  call    _tlgKeywordOn
0x18001d999  test    al, al
0x18001d99b  jz      loc_18001DB1D
0x18001d9a1  mov     rcx, [rbx+0F0h]
0x18001d9a8  mov     rax, [rcx]
0x18001d9ab  mov     rax, [rax+30h]
0x18001d9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9b4  mov     ecx, [rax+2Ch]
0x18001d9b7  mov     [rbp+57h+arg_8], ecx
0x18001d9ba  mov     rcx, [rbx+0F0h]
0x18001d9c1  mov     rax, [rcx]
0x18001d9c4  mov     rax, [rax+30h]
0x18001d9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9cd  mov     ecx, [rax+1Ch]
0x18001d9d0  mov     [rbp+57h+arg_10], ecx
0x18001d9d3  mov     rcx, [rbx+0F0h]
0x18001d9da  mov     rax, [rcx]
0x18001d9dd  mov     rax, [rax+30h]
0x18001d9e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9e6  mov     ecx, [rax+14h]
0x18001d9e9  mov     [rbp+57h+arg_18], ecx
0x18001d9ec  mov     rcx, [rbx+0F0h]
0x18001d9f3  mov     rax, [rcx]
0x18001d9f6  mov     rax, [rax+30h]
0x18001d9fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9ff  mov     ecx, [rax+10h]
0x18001da02  mov     [rbp+57h+var_7C], ecx
0x18001da05  mov     rcx, [rbx+0F0h]
0x18001da0c  mov     rax, [rcx]
0x18001da0f  mov     rax, [rax+30h]
0x18001da13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da18  mov     ecx, [rax+0Ch]
0x18001da1b  mov     [rbp+57h+var_88], ecx
0x18001da1e  mov     rcx, [rbx+0F0h]
0x18001da25  mov     rax, [rcx]
0x18001da28  mov     rax, [rax+30h]
0x18001da2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da31  mov     ecx, [rax+8]
0x18001da34  mov     [rbp+57h+var_84], ecx
0x18001da37  mov     rax, [rbx+0E8h]
0x18001da3e  mov     ecx, [rax+150h]
0x18001da44  mov     [rbp+57h+var_80], ecx
0x18001da47  mov     rcx, [rbx+0F0h]
0x18001da4e  mov     rax, [rcx]
0x18001da51  mov     rax, [rax+28h]
0x18001da55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001da5a  mov     [rbp+57h+var_78], rax
0x18001da5e  lea     rax, aDisplayMode; "Display mode"
0x18001da65  mov     [rbp+57h+var_70], rax
0x18001da69  lea     rax, xmmword_18003CA50
0x18001da70  mov     [rbp+57h+var_68], rax
0x18001da74  lea     rax, aRdplite; "RdpLite"
0x18001da7b  mov     [rbp+57h+var_60], rax
0x18001da7f  mov     [rbp+57h+var_58], 1000000h
0x18001da87  lea     rax, aCheckpoint; "Checkpoint"
0x18001da8e  mov     [rbp+57h+var_50], rax
0x18001da92  lea     rax, [rbp+57h+arg_8]
0x18001da96  mov     [rsp+130h+var_B0], rax
0x18001da9e  lea     rax, [rbp+57h+arg_10]
0x18001daa2  mov     [rsp+130h+var_B8], rax
0x18001daa7  lea     rax, [rbp+57h+arg_18]
0x18001daab  mov     [rsp+130h+var_C0], rax
0x18001dab0  lea     rax, [rbp+57h+var_7C]
0x18001dab4  mov     [rsp+130h+var_C8], rax
0x18001dab9  lea     rax, [rbp+57h+var_88]
0x18001dabd  mov     [rsp+130h+var_D0], rax
0x18001dac2  lea     rax, [rbp+57h+var_84]
0x18001dac6  mov     [rsp+130h+var_D8], rax
0x18001dacb  lea     rax, [rbp+57h+var_80]
0x18001dacf  mov     [rsp+130h+var_E0], rax
0x18001dad4  lea     rax, [rbp+57h+var_78]
0x18001dad8  mov     [rsp+130h+var_E8], rax
0x18001dadd  lea     rax, [rbp+57h+var_70]
0x18001dae1  mov     [rsp+130h+var_F0], rax
0x18001dae6  lea     rax, [rbp+57h+var_68]
0x18001daea  mov     [rsp+130h+var_F8], rax
0x18001daef  lea     rax, [rbp+57h+var_60]
0x18001daf3  mov     [rsp+130h+var_100], rax
0x18001daf8  lea     rax, [rbp+57h+var_58]
0x18001dafc  mov     [rsp+130h+var_108], rax
0x18001db01  lea     rax, [rbp+57h+var_50]
0x18001db05  mov     qword ptr [rsp+130h+var_110], rax
0x18001db0a  lea     rdx, byte_180035DCB
0x18001db11  lea     rcx, dword_18003C058
0x18001db18  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@666666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001db1d  mov     rcx, [rbx+0F0h]
0x18001db24  mov     rax, [rcx]
0x18001db27  mov     rax, [rax+30h]
0x18001db2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db30  mov     eax, [rax+2Ch]
0x18001db33  mov     [rbp+57h+arg_8], eax
0x18001db36  mov     rcx, [rbx+0F0h]
0x18001db3d  mov     rax, [rcx]
0x18001db40  mov     rax, [rax+30h]
0x18001db44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db49  mov     eax, [rax+14h]
0x18001db4c  mov     [rbp+57h+arg_10], eax
0x18001db4f  mov     rcx, [rbx+0F0h]
0x18001db56  mov     rax, [rcx]
0x18001db59  mov     rax, [rax+30h]
0x18001db5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db62  mov     eax, [rax+10h]
0x18001db65  mov     [rbp+57h+arg_18], eax
0x18001db68  mov     rcx, [rbx+0F0h]
0x18001db6f  mov     rax, [rcx]
0x18001db72  mov     rax, [rax+28h]
0x18001db76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db7b  movzx   eax, byte ptr [rax+0Fh]
0x18001db7f  mov     [rbp+57h+var_80], eax
0x18001db82  mov     rcx, [rbx+0F0h]
0x18001db89  mov     rax, [rcx]
0x18001db8c  mov     rax, [rax+28h]
0x18001db90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db95  movzx   eax, byte ptr [rax+0Eh]
0x18001db99  mov     [rbp+57h+var_84], eax
0x18001db9c  mov     rcx, [rbx+0F0h]
0x18001dba3  mov     rax, [rcx]
0x18001dba6  mov     rax, [rax+28h]
0x18001dbaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbaf  movzx   eax, byte ptr [rax+0Dh]
0x18001dbb3  mov     [rbp+57h+var_88], eax
0x18001dbb6  mov     rcx, [rbx+0F0h]
0x18001dbbd  mov     rax, [rcx]
0x18001dbc0  mov     rax, [rax+28h]
0x18001dbc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbc9  movzx   r13d, byte ptr [rax+0Ch]
0x18001dbce  mov     rcx, [rbx+0F0h]
0x18001dbd5  mov     rax, [rcx]
0x18001dbd8  mov     rax, [rax+28h]
0x18001dbdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbe1  movzx   r12d, byte ptr [rax+0Bh]
0x18001dbe6  mov     rcx, [rbx+0F0h]
0x18001dbed  mov     rax, [rcx]
0x18001dbf0  mov     rax, [rax+28h]
0x18001dbf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbf9  movzx   r15d, byte ptr [rax+0Ah]
0x18001dbfe  mov     rcx, [rbx+0F0h]
0x18001dc05  mov     rax, [rcx]
0x18001dc08  mov     rax, [rax+28h]
0x18001dc0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc11  movzx   r14d, byte ptr [rax+9]
0x18001dc16  mov     rcx, [rbx+0F0h]
0x18001dc1d  mov     rax, [rcx]
0x18001dc20  mov     rax, [rax+28h]
0x18001dc24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc29  movzx   esi, byte ptr [rax+8]
0x18001dc2d  mov     rcx, [rbx+0F0h]
0x18001dc34  mov     rax, [rcx]
0x18001dc37  mov     rax, [rax+28h]
0x18001dc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc40  movzx   edi, word ptr [rax+6]
0x18001dc44  mov     rcx, [rbx+0F0h]
0x18001dc4b  mov     rax, [rcx]
0x18001dc4e  mov     rax, [rax+28h]
0x18001dc52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc57  movzx   ebx, word ptr [rax+4]
0x18001dc5b  mov     rcx, [rbp+57h+arg_0]
0x18001dc5f  mov     rcx, [rcx+0F0h]
0x18001dc66  mov     rax, [rcx]
0x18001dc69  mov     rax, [rax+28h]
0x18001dc6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc72  mov     ecx, [rbp+57h+arg_8]
0x18001dc75  mov     [rsp+130h+var_A0], ecx
0x18001dc7c  mov     ecx, [rbp+57h+arg_10]
0x18001dc7f  mov     [rsp+130h+var_A8], ecx
0x18001dc86  mov     ecx, [rbp+57h+arg_18]
0x18001dc89  mov     dword ptr [rsp+130h+var_B0], ecx
0x18001dc90  mov     ecx, [rbp+57h+var_80]
0x18001dc93  mov     dword ptr [rsp+130h+var_B8], ecx
0x18001dc97  mov     ecx, [rbp+57h+var_84]
0x18001dc9a  mov     dword ptr [rsp+130h+var_C0], ecx
0x18001dc9e  mov     ecx, [rbp+57h+var_88]
0x18001dca1  mov     dword ptr [rsp+130h+var_C8], ecx
0x18001dca5  mov     dword ptr [rsp+130h+var_D0], r13d
0x18001dcaa  mov     dword ptr [rsp+130h+var_D8], r12d
0x18001dcaf  mov     dword ptr [rsp+130h+var_E0], r15d
0x18001dcb4  mov     dword ptr [rsp+130h+var_E8], r14d
0x18001dcb9  mov     dword ptr [rsp+130h+var_F0], esi
0x18001dcbd  mov     dword ptr [rsp+130h+var_F8], edi
0x18001dcc1  mov     dword ptr [rsp+130h+var_100], ebx
0x18001dcc5  mov     eax, [rax]
0x18001dcc7  mov     dword ptr [rsp+130h+var_108], eax; char *
0x18001dccb  mov     [rsp+130h+var_110], 1DEh; unsigned int
0x18001dcd3  lea     r14, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001dcda  mov     r9, r14; char *
0x18001dcdd  lea     r8, aRdpStackShimCm_1; "Rdp::Stack::Shim::CMonitorShim::SetDisp"...
0x18001dce4  lea     rdx, aId08lx04hx04hx; "Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02h"...
0x18001dceb  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001dcf2  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001dcf7  mov     [rbp+57h+var_90], 0
0x18001dcff  mov     rsi, [rbp+57h+arg_0]
0x18001dd03  mov     rdi, [rsi+0E0h]
0x18001dd0a  mov     rax, [rdi]
0x18001dd0d  mov     rbx, [rax+18h]
0x18001dd11  lea     rcx, [rbp+57h+var_90]
0x18001dd15  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18001dd1a  lea     rdx, [rbp+57h+var_90]
0x18001dd1e  mov     rcx, rdi
0x18001dd21  mov     rax, rbx
0x18001dd24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd29  mov     rcx, [rbp+5Fh]; this
0x18001dd2d  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x18001dd34  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18001dd39  mov     r9d, eax; char *
0x18001dd3c  mov     r8, r14; unsigned int
0x18001dd3f  mov     edx, 1E5h; void *
0x18001dd44  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001dd49  mov     rcx, [rsi+0F0h]
0x18001dd50  mov     rax, [rcx]
0x18001dd53  mov     rax, [rax+30h]
0x18001dd57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd5c  mov     r8d, [rax+8]; struct _tagpropertykey *
0x18001dd60  lea     rdx, PKEY_Primary_Monitor_Offset_X; struct IPropertyStore *
0x18001dd67  mov     rcx, [rbp+57h+var_90]; this
0x18001dd6b  call    ?IPropertyStore_SetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; Rdp::Utils::Props::IPropertyStore_SetInt32(IPropertyStore *,_tagpropertykey const &,int)
0x18001dd70  mov     rcx, [rbp+5Fh]; this
0x18001dd74  lea     rdx, aFailedToSetPke_27; "Failed to set PKEY_Primary_Monitor_Offs"...
0x18001dd7b  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18001dd80  mov     r9d, eax; char *
0x18001dd83  mov     r8, r14; unsigned int
0x18001dd86  mov     edx, 1EFh; void *
0x18001dd8b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001dd90  mov     rcx, [rsi+0F0h]
0x18001dd97  mov     rax, [rcx]
0x18001dd9a  mov     rax, [rax+30h]
0x18001dd9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dda3  mov     r8d, [rax+0Ch]; struct _tagpropertykey *
0x18001dda7  lea     rdx, PKEY_Primary_Monitor_Offset_Y; struct IPropertyStore *
0x18001ddae  mov     rcx, [rbp+57h+var_90]; this
0x18001ddb2  call    ?IPropertyStore_SetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@H@Z; Rdp::Utils::Props::IPropertyStore_SetInt32(IPropertyStore *,_tagpropertykey const &,int)
0x18001ddb7  mov     rcx, [rbp+5Fh]; this
0x18001ddbb  lea     rdx, aFailedToSetPke_26; "Failed to set PKEY_Primary_Monitor_Offs"...
0x18001ddc2  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18001ddc7  mov     r9d, eax; char *
0x18001ddca  mov     r8, r14; unsigned int
0x18001ddcd  mov     edx, 1F6h; void *
0x18001ddd2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001ddd7  mov     rcx, [rsi+0F0h]
0x18001ddde  mov     rax, [rcx]
0x18001dde1  mov     rax, [rax+30h]
0x18001dde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ddea  mov     r8d, [rax+10h]; struct _tagpropertykey *
0x18001ddee  lea     rdx, PKEY_Width_In_Pixels; struct IPropertyStore *
0x18001ddf5  mov     rcx, [rbp+57h+var_90]; this
0x18001ddf9  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001ddfe  mov     rcx, [rbp+5Fh]; this
0x18001de02  lea     rdx, aFailedToSetPke_35; "Failed to set PKEY_Width_In_Pixels prop"...
0x18001de09  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18001de0e  mov     r9d, eax; char *
0x18001de11  mov     r8, r14; unsigned int
0x18001de14  mov     edx, 200h; void *
0x18001de19  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001de1e  mov     rcx, [rsi+0F0h]
0x18001de25  mov     rax, [rcx]
0x18001de28  mov     rax, [rax+30h]
0x18001de2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de31  mov     r8d, [rax+14h]; struct _tagpropertykey *
0x18001de35  lea     rdx, PKEY_Height_In_Pixels; struct IPropertyStore *
0x18001de3c  mov     rcx, [rbp+57h+var_90]; this
0x18001de40  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001de45  mov     rcx, [rbp+5Fh]; this
0x18001de49  lea     rdx, aFailedToSetPke_20; "Failed to set PKEY_Height_In_Pixels pro"...
0x18001de50  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18001de55  mov     r9d, eax; char *
0x18001de58  mov     r8, r14; unsigned int
0x18001de5b  mov     edx, 207h; void *
0x18001de60  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001de65  mov     rcx, [rsi+0F0h]
0x18001de6c  mov     rax, [rcx]
0x18001de6f  mov     rax, [rax+30h]
0x18001de73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001de78  mov     r8d, [rax+1Ch]; struct _tagpropertykey *
0x18001de7c  lea     rdx, PKEY_Orientation; struct IPropertyStore *
0x18001de83  mov     rcx, [rbp+57h+var_90]; this
0x18001de87  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001de8c  mov     rcx, [rbp+5Fh]; this
0x18001de90  lea     rdx, aFailedToSetPke_30; "Failed to set PKEY_Orientation property"
0x18001de97  mov     qword ptr [rsp+130h+var_110], rdx; int
0x18001de9c  mov     r9d, eax; char *
0x18001de9f  mov     r8, r14; unsigned int
0x18001dea2  mov     edx, 211h; void *
0x18001dea7  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001deac  mov     rcx, [rsi+0F0h]
  ... truncated ...
```
