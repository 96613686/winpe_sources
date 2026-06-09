# Rdp::Stack::Shim::CMonitorShim::SetColorimetryProperties(void)

- ea: `0x18001d09c`
- end: `0x18001d94b`
- name: `?SetColorimetryProperties@CMonitorShim@Shim@Stack@Rdp@@AEAAXXZ`
- size: `2223`
- prototype: `void __fastcall(Rdp::Stack::Shim::CMonitorShim *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cdfc`

## callees

- `0x18000141c`
- `0x180002a98`
- `0x180007b28`
- `0x18000b130`
- `0x18000cf28`
- `0x18000d98c`
- `0x18000db64`
- `0x18001d09c`
- `0x18002a010`

## string_xrefs

- `0x18001d5a1`: `Failed to open property store`

## pseudocode

```c
void __fastcall Rdp::Stack::Shim::CMonitorShim::SetColorimetryProperties(Rdp::Stack::Shim::CMonitorShim *this)
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
  __int64 v40; // rax
  unsigned int v41; // r9d
  unsigned int v42; // eax
  __int64 v43; // rax
  unsigned int v44; // r9d
  unsigned int v45; // eax
  __int64 v46; // rax
  unsigned int v47; // r9d
  unsigned int v48; // eax
  __int64 v49; // rax
  unsigned int v50; // r9d
  unsigned int v51; // ebx
  unsigned int v52; // eax
  char *v53; // [rsp+28h] [rbp-138h]
  char *v54; // [rsp+28h] [rbp-138h]
  char *v55; // [rsp+28h] [rbp-138h]
  char *v56; // [rsp+28h] [rbp-138h]
  char *v57; // [rsp+28h] [rbp-138h]
  char *v58; // [rsp+28h] [rbp-138h]
  char *v59; // [rsp+28h] [rbp-138h]
  char *v60; // [rsp+28h] [rbp-138h]
  char *v61; // [rsp+28h] [rbp-138h]
  char *v62; // [rsp+28h] [rbp-138h]
  char *v63; // [rsp+28h] [rbp-138h]
  char *v64; // [rsp+28h] [rbp-138h]
  char *v65; // [rsp+28h] [rbp-138h]
  char *v66; // [rsp+28h] [rbp-138h]
  __int64 v67; // [rsp+30h] [rbp-130h]
  __int64 v68; // [rsp+38h] [rbp-128h]
  __int64 v69; // [rsp+40h] [rbp-120h]
  __int64 v70; // [rsp+48h] [rbp-118h]
  __int64 v71; // [rsp+50h] [rbp-110h]
  __int64 v72; // [rsp+58h] [rbp-108h]
  __int64 v73; // [rsp+60h] [rbp-100h]
  __int64 v74; // [rsp+68h] [rbp-F8h]
  __int64 v75; // [rsp+70h] [rbp-F0h]
  __int64 v76; // [rsp+78h] [rbp-E8h]
  __int64 v77; // [rsp+80h] [rbp-E0h]
  Rdp::Utils::Props *v78; // [rsp+E0h] [rbp-80h] BYREF
  int v79; // [rsp+E8h] [rbp-78h] BYREF
  int v80; // [rsp+ECh] [rbp-74h] BYREF
  int v81; // [rsp+F0h] [rbp-70h] BYREF
  int v82; // [rsp+F4h] [rbp-6Ch] BYREF
  int v83; // [rsp+F8h] [rbp-68h] BYREF
  int v84; // [rsp+FCh] [rbp-64h] BYREF
  int v85; // [rsp+100h] [rbp-60h] BYREF
  int v86; // [rsp+104h] [rbp-5Ch] BYREF
  int v87; // [rsp+108h] [rbp-58h] BYREF
  int v88; // [rsp+10Ch] [rbp-54h] BYREF
  int v89; // [rsp+110h] [rbp-50h] BYREF
  int v90; // [rsp+114h] [rbp-4Ch] BYREF
  int v91; // [rsp+118h] [rbp-48h] BYREF
  int v92; // [rsp+11Ch] [rbp-44h] BYREF
  __int64 v93; // [rsp+120h] [rbp-40h] BYREF
  const char *v94; // [rsp+128h] [rbp-38h] BYREF
  __int128 *v95; // [rsp+130h] [rbp-30h] BYREF
  const char *v96; // [rsp+138h] [rbp-28h] BYREF
  __int64 v97; // [rsp+140h] [rbp-20h] BYREF
  const char *v98; // [rsp+148h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+38h]
  int v101; // [rsp+1A8h] [rbp+48h] BYREF
  int v102; // [rsp+1B0h] [rbp+50h] BYREF
  int v103; // [rsp+1B8h] [rbp+58h] BYREF

  if ( (unsigned int)dword_18003C058 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003C058, 0x470000000000LL) )
  {
    v101 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 68);
    v102 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 64);
    v103 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 60);
    v80 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 56);
    v81 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 52);
    v82 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 48);
    v83 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 44);
    v84 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 40);
    v85 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 36);
    v86 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 32);
    v87 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 28);
    v88 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 24);
    v89 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 20);
    v90 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 16);
    v91 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 12);
    v92 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 8);
    v79 = *(_DWORD *)(*((_QWORD *)this + 29) + 336LL);
    v93 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30));
    v94 = "Colorimetry";
    v95 = &xmmword_18003CA50;
    v96 = "RdpLite";
    v97 = 0x1000000;
    v98 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)word_180035BF2,
      v2,
      v3,
      (__int64)&v98,
      (__int64)&v97,
      (__int64)&v96,
      (__int64)&v95,
      (__int64)&v94,
      (__int64)&v93,
      (__int64)&v79,
      (__int64)&v92,
      (__int64)&v91,
      (__int64)&v90,
      (__int64)&v89,
      (__int64)&v88,
      (__int64)&v87,
      (__int64)&v86,
      (__int64)&v85,
      (__int64)&v84,
      (__int64)&v83,
      (__int64)&v82,
      (__int64)&v81,
      (__int64)&v80,
      (__int64)&v103,
      (__int64)&v102,
      (__int64)&v101);
  }
  v101 = *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 72LL))(*((_QWORD *)this + 30)) + 52);
  v102 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                            + 15);
  v103 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
                            + 14);
  v79 = *(unsigned __int8 *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 30) + 40LL))(*((_QWORD *)this + 30))
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
  LODWORD(v77) = v101;
  LODWORD(v76) = v102;
  LODWORD(v75) = v103;
  LODWORD(v74) = v79;
  LODWORD(v73) = v4;
  LODWORD(v72) = v5;
  LODWORD(v71) = v6;
  LODWORD(v70) = v7;
  LODWORD(v69) = v8;
  LODWORD(v68) = v9;
  LODWORD(v67) = v10;
  LODWORD(v53) = *v11;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}, colorimetry Rgb(bpc): %d",
    "Rdp::Stack::Shim::CMonitorShim::SetColorimetryProperties",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    0x2A1u,
    v53,
    v67,
    v68,
    v69,
    v70,
    v71,
    v72,
    v73,
    v74,
    v75,
    v76,
    v77);
  v78 = 0;
  v12 = this;
  v13 = *((_QWORD *)this + 28);
  v14 = *(__int64 (__fastcall **)(__int64, Rdp::Utils::Props **))(*(_QWORD *)v13 + 24LL);
  wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(&v78);
  v15 = v14(v13, &v78);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2A8,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v15,
    (int)"Failed to open property store",
    v54);
  v16 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v18 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_Red_Point_X,
          (const struct _tagpropertykey *)*(unsigned int *)(v16 + 8),
          v17);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2AF,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v18,
    (int)"Failed to set PKEY_Red_Point_X property",
    v55);
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v21 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_Red_Point_Y,
          (const struct _tagpropertykey *)*(unsigned int *)(v19 + 12),
          v20);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2B6,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v21,
    (int)"Failed to set PKEY_Red_Point_Y property",
    v56);
  v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v24 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_Green_Point_X,
          (const struct _tagpropertykey *)*(unsigned int *)(v22 + 16),
          v23);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2BD,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v24,
    (int)"Failed to set PKEY_Green_Point_X property",
    v57);
  v25 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v27 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_Green_Point_Y,
          (const struct _tagpropertykey *)*(unsigned int *)(v25 + 20),
          v26);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2C4,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v27,
    (int)"Failed to set PKEY_Green_Point_Y property",
    v58);
  v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v30 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_Blue_Point_X,
          (const struct _tagpropertykey *)*(unsigned int *)(v28 + 24),
          v29);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2CB,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v30,
    (int)"Failed to set PKEY_Blue_Point_X property",
    v59);
  v31 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v33 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_Blue_Point_Y,
          (const struct _tagpropertykey *)*(unsigned int *)(v31 + 28),
          v32);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2D2,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v33,
    (int)"Failed to set PKEY_Blue_Point_Y property",
    v60);
  v34 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v36 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_White_Point_X,
          (const struct _tagpropertykey *)*(unsigned int *)(v34 + 32),
          v35);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2D9,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v36,
    (int)"Failed to set PKEY_White_Point_X property",
    v61);
  v37 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v39 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_White_Point_Y,
          (const struct _tagpropertykey *)*(unsigned int *)(v37 + 36),
          v38);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2E0,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v39,
    (int)"Failed to set PKEY_White_Point_Y property",
    v62);
  v40 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v42 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_Min_Luminance,
          (const struct _tagpropertykey *)*(unsigned int *)(v40 + 40),
          v41);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2E7,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v42,
    (int)"Failed to set PKEY_Min_Luminance property",
    v63);
  v43 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v45 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_Max_Luminance,
          (const struct _tagpropertykey *)*(unsigned int *)(v43 + 44),
          v44);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2EE,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v45,
    (int)"Failed to set PKEY_Max_Luminance property",
    v64);
  v46 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v48 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_Max_Full_Frame_Luminance,
          (const struct _tagpropertykey *)*(unsigned int *)(v46 + 48),
          v47);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2F5,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v48,
    (int)"Failed to set PKEY_Max_Full_Frame_Luminance property",
    v65);
  v49 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v12 + 30) + 72LL))(*((_QWORD *)v12 + 30));
  v51 = (*(_BYTE *)(v49 + 68) & 1) != 0;
  if ( (*(_BYTE *)(v49 + 68) & 2) != 0 )
    v51 |= 2u;
  if ( (*(_BYTE *)(v49 + 68) & 4) != 0 )
    v51 |= 4u;
  v52 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          v78,
          (struct IPropertyStore *)&PKEY_Colorimetry_Flags,
          (const struct _tagpropertykey *)v51,
          v50);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x2FC,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\monitorshim.cpp",
    (const char *)v52,
    (int)"Failed to set PKEY_Colorimetry_Flags property",
    v66);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v78);
}

```

## disassembly

```asm
0x18001d09c  mov     [rsp-8+arg_0], rcx
0x18001d0a1  push    rbp
0x18001d0a2  push    rbx
0x18001d0a3  push    rsi
0x18001d0a4  push    rdi
0x18001d0a5  push    r12
0x18001d0a7  push    r13
0x18001d0a9  push    r14
0x18001d0ab  push    r15
0x18001d0ad  lea     rbp, [rsp+8]
0x18001d0b2  sub     rsp, 158h
0x18001d0b9  mov     rbx, rcx
0x18001d0bc  mov     eax, cs:dword_18003C058
0x18001d0c2  cmp     eax, 4
0x18001d0c5  jbe     loc_18001D3D7
0x18001d0cb  mov     rdx, 470000000000h
0x18001d0d5  lea     rcx, dword_18003C058
0x18001d0dc  call    _tlgKeywordOn
0x18001d0e1  test    al, al
0x18001d0e3  jz      loc_18001D3D7
0x18001d0e9  mov     rcx, [rbx+0F0h]
0x18001d0f0  mov     rax, [rcx]
0x18001d0f3  mov     rax, [rax+48h]
0x18001d0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0fc  mov     ecx, [rax+44h]
0x18001d0ff  mov     [rbp+30h+arg_8], ecx
0x18001d102  mov     rcx, [rbx+0F0h]
0x18001d109  mov     rax, [rcx]
0x18001d10c  mov     rax, [rax+48h]
0x18001d110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d115  mov     ecx, [rax+40h]
0x18001d118  mov     [rbp+30h+arg_10], ecx
0x18001d11b  mov     rcx, [rbx+0F0h]
0x18001d122  mov     rax, [rcx]
0x18001d125  mov     rax, [rax+48h]
0x18001d129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d12e  mov     ecx, [rax+3Ch]
0x18001d131  mov     [rbp+30h+arg_18], ecx
0x18001d134  mov     rcx, [rbx+0F0h]
0x18001d13b  mov     rax, [rcx]
0x18001d13e  mov     rax, [rax+48h]
0x18001d142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d147  mov     ecx, [rax+38h]
0x18001d14a  mov     [rbp+30h+var_A4], ecx
0x18001d14d  mov     rcx, [rbx+0F0h]
0x18001d154  mov     rax, [rcx]
0x18001d157  mov     rax, [rax+48h]
0x18001d15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d160  mov     ecx, [rax+34h]
0x18001d163  mov     [rbp+30h+var_A0], ecx
0x18001d166  mov     rcx, [rbx+0F0h]
0x18001d16d  mov     rax, [rcx]
0x18001d170  mov     rax, [rax+48h]
0x18001d174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d179  mov     ecx, [rax+30h]
0x18001d17c  mov     [rbp+30h+var_9C], ecx
0x18001d17f  mov     rcx, [rbx+0F0h]
0x18001d186  mov     rax, [rcx]
0x18001d189  mov     rax, [rax+48h]
0x18001d18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d192  mov     ecx, [rax+2Ch]
0x18001d195  mov     [rbp+30h+var_98], ecx
0x18001d198  mov     rcx, [rbx+0F0h]
0x18001d19f  mov     rax, [rcx]
0x18001d1a2  mov     rax, [rax+48h]
0x18001d1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1ab  mov     ecx, [rax+28h]
0x18001d1ae  mov     [rbp+30h+var_94], ecx
0x18001d1b1  mov     rcx, [rbx+0F0h]
0x18001d1b8  mov     rax, [rcx]
0x18001d1bb  mov     rax, [rax+48h]
0x18001d1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1c4  mov     ecx, [rax+24h]
0x18001d1c7  mov     [rbp+30h+var_90], ecx
0x18001d1ca  mov     rcx, [rbx+0F0h]
0x18001d1d1  mov     rax, [rcx]
0x18001d1d4  mov     rax, [rax+48h]
0x18001d1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1dd  mov     ecx, [rax+20h]
0x18001d1e0  mov     [rbp+30h+var_8C], ecx
0x18001d1e3  mov     rcx, [rbx+0F0h]
0x18001d1ea  mov     rax, [rcx]
0x18001d1ed  mov     rax, [rax+48h]
0x18001d1f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1f6  mov     ecx, [rax+1Ch]
0x18001d1f9  mov     [rbp+30h+var_88], ecx
0x18001d1fc  mov     rcx, [rbx+0F0h]
0x18001d203  mov     rax, [rcx]
0x18001d206  mov     rax, [rax+48h]
0x18001d20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d20f  mov     ecx, [rax+18h]
0x18001d212  mov     [rbp+30h+var_84], ecx
0x18001d215  mov     rcx, [rbx+0F0h]
0x18001d21c  mov     rax, [rcx]
0x18001d21f  mov     rax, [rax+48h]
0x18001d223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d228  mov     ecx, [rax+14h]
0x18001d22b  mov     [rbp+30h+var_80], ecx
0x18001d22e  mov     rcx, [rbx+0F0h]
0x18001d235  mov     rax, [rcx]
0x18001d238  mov     rax, [rax+48h]
0x18001d23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d241  mov     ecx, [rax+10h]
0x18001d244  mov     [rbp+30h+var_7C], ecx
0x18001d247  mov     rcx, [rbx+0F0h]
0x18001d24e  mov     rax, [rcx]
0x18001d251  mov     rax, [rax+48h]
0x18001d255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d25a  mov     ecx, [rax+0Ch]
0x18001d25d  mov     [rbp+30h+var_78], ecx
0x18001d260  mov     rcx, [rbx+0F0h]
0x18001d267  mov     rax, [rcx]
0x18001d26a  mov     rax, [rax+48h]
0x18001d26e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d273  mov     ecx, [rax+8]
0x18001d276  mov     [rbp+30h+var_74], ecx
0x18001d279  mov     rax, [rbx+0E8h]
0x18001d280  mov     ecx, [rax+150h]
0x18001d286  mov     [rbp+30h+var_A8], ecx
0x18001d289  mov     rcx, [rbx+0F0h]
0x18001d290  mov     rax, [rcx]
0x18001d293  mov     rax, [rax+28h]
0x18001d297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d29c  mov     [rbp+30h+var_70], rax
0x18001d2a0  lea     rax, aColorimetry; "Colorimetry"
0x18001d2a7  mov     [rbp+30h+var_68], rax
0x18001d2ab  lea     rax, xmmword_18003CA50
0x18001d2b2  mov     [rbp+30h+var_60], rax
0x18001d2b6  lea     rax, aRdplite; "RdpLite"
0x18001d2bd  mov     [rbp+30h+var_58], rax
0x18001d2c1  mov     [rbp+30h+var_50], 1000000h
0x18001d2c9  lea     rax, aCheckpoint; "Checkpoint"
0x18001d2d0  mov     [rbp+30h+var_48], rax
0x18001d2d4  lea     rax, [rbp+30h+arg_8]
0x18001d2d8  mov     [rsp+190h+var_C0], rax
0x18001d2e0  lea     rax, [rbp+30h+arg_10]
0x18001d2e4  mov     [rsp+190h+var_C8], rax
0x18001d2ec  lea     rax, [rbp+30h+arg_18]
0x18001d2f0  mov     [rsp+190h+var_D0], rax
0x18001d2f8  lea     rax, [rbp+30h+var_A4]
0x18001d2fc  mov     [rsp+190h+var_D8], rax
0x18001d304  lea     rax, [rbp+30h+var_A0]
0x18001d308  mov     [rsp+190h+var_E0], rax
0x18001d310  lea     rax, [rbp+30h+var_9C]
0x18001d314  mov     [rsp+190h+var_E8], rax
0x18001d31c  lea     rax, [rbp+30h+var_98]
0x18001d320  mov     [rsp+190h+var_F0], rax
0x18001d328  lea     rax, [rbp+30h+var_94]
0x18001d32c  mov     [rsp+190h+var_F8], rax
0x18001d334  lea     rax, [rbp+30h+var_90]
0x18001d338  mov     [rsp+190h+var_100], rax
0x18001d340  lea     rax, [rbp+30h+var_8C]
0x18001d344  mov     [rsp+190h+var_108], rax
0x18001d34c  lea     rax, [rbp+30h+var_88]
0x18001d350  mov     [rsp+190h+var_110], rax
0x18001d358  lea     rax, [rbp+30h+var_84]
0x18001d35c  mov     [rsp+190h+var_118], rax
0x18001d361  lea     rax, [rbp+30h+var_80]
0x18001d365  mov     [rsp+190h+var_120], rax
0x18001d36a  lea     rax, [rbp+30h+var_7C]
0x18001d36e  mov     [rsp+190h+var_128], rax
0x18001d373  lea     rax, [rbp+30h+var_78]
0x18001d377  mov     [rsp+190h+var_130], rax
0x18001d37c  lea     rax, [rbp+30h+var_74]
0x18001d380  mov     [rsp+190h+var_138], rax
0x18001d385  lea     rax, [rbp+30h+var_A8]
0x18001d389  mov     [rsp+190h+var_140], rax
0x18001d38e  lea     rax, [rbp+30h+var_70]
0x18001d392  mov     [rsp+190h+var_148], rax
0x18001d397  lea     rax, [rbp+30h+var_68]
0x18001d39b  mov     [rsp+190h+var_150], rax
0x18001d3a0  lea     rax, [rbp+30h+var_60]
0x18001d3a4  mov     [rsp+190h+var_158], rax
0x18001d3a9  lea     rax, [rbp+30h+var_58]
0x18001d3ad  mov     [rsp+190h+var_160], rax
0x18001d3b2  lea     rax, [rbp+30h+var_50]
0x18001d3b6  mov     [rsp+190h+var_168], rax
0x18001d3bb  lea     rax, [rbp+30h+var_48]
0x18001d3bf  mov     qword ptr [rsp+190h+var_170], rax
0x18001d3c4  lea     rdx, word_180035BF2
0x18001d3cb  lea     rcx, dword_18003C058
0x18001d3d2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@6666666666666666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001d3d7  mov     rcx, [rbx+0F0h]
0x18001d3de  mov     rax, [rcx]
0x18001d3e1  mov     rax, [rax+48h]
0x18001d3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d3ea  mov     eax, [rax+34h]
0x18001d3ed  mov     [rbp+30h+arg_8], eax
0x18001d3f0  mov     rcx, [rbx+0F0h]
0x18001d3f7  mov     rax, [rcx]
0x18001d3fa  mov     rax, [rax+28h]
0x18001d3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d403  movzx   eax, byte ptr [rax+0Fh]
0x18001d407  mov     [rbp+30h+arg_10], eax
0x18001d40a  mov     rcx, [rbx+0F0h]
0x18001d411  mov     rax, [rcx]
0x18001d414  mov     rax, [rax+28h]
0x18001d418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d41d  movzx   eax, byte ptr [rax+0Eh]
0x18001d421  mov     [rbp+30h+arg_18], eax
0x18001d424  mov     rcx, [rbx+0F0h]
0x18001d42b  mov     rax, [rcx]
0x18001d42e  mov     rax, [rax+28h]
0x18001d432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d437  movzx   eax, byte ptr [rax+0Dh]
0x18001d43b  mov     [rbp+30h+var_A8], eax
0x18001d43e  mov     rcx, [rbx+0F0h]
0x18001d445  mov     rax, [rcx]
0x18001d448  mov     rax, [rax+28h]
0x18001d44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d451  movzx   r13d, byte ptr [rax+0Ch]
0x18001d456  mov     rcx, [rbx+0F0h]
0x18001d45d  mov     rax, [rcx]
0x18001d460  mov     rax, [rax+28h]
0x18001d464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d469  movzx   r12d, byte ptr [rax+0Bh]
0x18001d46e  mov     rcx, [rbx+0F0h]
0x18001d475  mov     rax, [rcx]
0x18001d478  mov     rax, [rax+28h]
0x18001d47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d481  movzx   r15d, byte ptr [rax+0Ah]
0x18001d486  mov     rcx, [rbx+0F0h]
0x18001d48d  mov     rax, [rcx]
0x18001d490  mov     rax, [rax+28h]
0x18001d494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d499  movzx   r14d, byte ptr [rax+9]
0x18001d49e  mov     rcx, [rbx+0F0h]
0x18001d4a5  mov     rax, [rcx]
0x18001d4a8  mov     rax, [rax+28h]
0x18001d4ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4b1  movzx   esi, byte ptr [rax+8]
0x18001d4b5  mov     rcx, [rbx+0F0h]
0x18001d4bc  mov     rax, [rcx]
0x18001d4bf  mov     rax, [rax+28h]
0x18001d4c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4c8  movzx   edi, word ptr [rax+6]
0x18001d4cc  mov     rcx, [rbx+0F0h]
0x18001d4d3  mov     rax, [rcx]
0x18001d4d6  mov     rax, [rax+28h]
0x18001d4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4df  movzx   ebx, word ptr [rax+4]
0x18001d4e3  mov     rcx, [rbp+30h+arg_0]
0x18001d4e7  mov     rcx, [rcx+0F0h]
0x18001d4ee  mov     rax, [rcx]
0x18001d4f1  mov     rax, [rax+28h]
0x18001d4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4fa  mov     ecx, [rbp+30h+arg_8]
0x18001d4fd  mov     dword ptr [rsp+190h+var_110], ecx
0x18001d504  mov     ecx, [rbp+30h+arg_10]
0x18001d507  mov     dword ptr [rsp+190h+var_118], ecx
0x18001d50b  mov     ecx, [rbp+30h+arg_18]
0x18001d50e  mov     dword ptr [rsp+190h+var_120], ecx
0x18001d512  mov     ecx, [rbp+30h+var_A8]
0x18001d515  mov     dword ptr [rsp+190h+var_128], ecx
0x18001d519  mov     dword ptr [rsp+190h+var_130], r13d
0x18001d51e  mov     dword ptr [rsp+190h+var_138], r12d
0x18001d523  mov     dword ptr [rsp+190h+var_140], r15d
0x18001d528  mov     dword ptr [rsp+190h+var_148], r14d
0x18001d52d  mov     dword ptr [rsp+190h+var_150], esi
0x18001d531  mov     dword ptr [rsp+190h+var_158], edi
0x18001d535  mov     dword ptr [rsp+190h+var_160], ebx
0x18001d539  mov     eax, [rax]
0x18001d53b  mov     dword ptr [rsp+190h+var_168], eax; char *
0x18001d53f  mov     [rsp+190h+var_170], 2A1h; unsigned int
0x18001d547  lea     r14, aOnecoreuapTerm_18; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001d54e  mov     r9, r14; char *
0x18001d551  lea     r8, aRdpStackShimCm_3; "Rdp::Stack::Shim::CMonitorShim::SetColo"...
0x18001d558  lea     rdx, aId08lx04hx04hx_0; "Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02h"...
0x18001d55f  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001d566  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001d56b  mov     [rbp+30h+var_B0], 0
0x18001d573  mov     rsi, [rbp+30h+arg_0]
0x18001d577  mov     rdi, [rsi+0E0h]
0x18001d57e  mov     rax, [rdi]
0x18001d581  mov     rbx, [rax+18h]
0x18001d585  lea     rcx, [rbp+30h+var_B0]
0x18001d589  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18001d58e  lea     rdx, [rbp+30h+var_B0]
0x18001d592  mov     rcx, rdi
0x18001d595  mov     rax, rbx
0x18001d598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d59d  mov     rcx, [rbp+38h]; this
0x18001d5a1  lea     rdx, aFailedToOpenPr; "Failed to open property store"
0x18001d5a8  mov     qword ptr [rsp+190h+var_170], rdx; int
0x18001d5ad  mov     r9d, eax; char *
0x18001d5b0  mov     r8, r14; unsigned int
0x18001d5b3  mov     edx, 2A8h; void *
0x18001d5b8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001d5bd  mov     rcx, [rsi+0F0h]
0x18001d5c4  mov     rax, [rcx]
0x18001d5c7  mov     rax, [rax+48h]
0x18001d5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5d0  mov     r8d, [rax+8]; struct _tagpropertykey *
0x18001d5d4  lea     rdx, PKEY_Red_Point_X; struct IPropertyStore *
0x18001d5db  mov     rcx, [rbp+30h+var_B0]; this
0x18001d5df  call    ?IPropertyStore_SetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@I@Z; Rdp::Utils::Props::IPropertyStore_SetUInt32(IPropertyStore *,_tagpropertykey const &,uint)
0x18001d5e4  mov     rcx, [rbp+38h]; this
0x18001d5e8  lea     rdx, aFailedToSetPke_25; "Failed to set PKEY_Red_Point_X property"
0x18001d5ef  mov     qword ptr [rsp+190h+var_170], rdx; int
0x18001d5f4  mov     r9d, eax; char *
  ... truncated ...
```
