# Rdp::Stack::Driver::CDriverControl3::ProcessMonitorConfig(bool,uint,Rdp::Stack::RDPLITE_MONITORCONFIG_INFO const *)

- ea: `0x180014570`
- end: `0x180014d88`
- name: `?ProcessMonitorConfig@CDriverControl3@Driver@Stack@Rdp@@UEAAJ_NIPEBURDPLITE_MONITORCONFIG_INFO@34@@Z`
- size: `2072`
- prototype: `__int64 __fastcall(Rdp::Stack::Driver::CDriverControl3 *this, unsigned __int8, unsigned int, const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config`

## callees

- `0x18000208c`
- `0x180002198`
- `0x1800036f0`
- `0x180004154`
- `0x18000b130`
- `0x18000cea4`
- `0x18000cf28`
- `0x18000ee04`
- `0x180012144`
- `0x180012cac`
- `0x1800130dc`
- `0x1800134f8`
- `0x1800135a0`
- `0x180013b20`
- `0x180013b5c`
- `0x180013c34`
- `0x180013da4`
- `0x180013f30`
- `0x180014054`
- `0x180014570`
- `0x180028340`
- `0x18002a010`

## string_xrefs

- `0x1800145ba`: `ProcessMonitorConfig`
- `0x1800145c6`: `Rdp::Stack::Driver::CDriverControl3::ProcessMonitorConfig`
- `0x18001462d`: `Rdp::Stack::Driver::CDriverControl3::ProcessMonitorConfig`
- `0x180014bf7`: `Failed to send RDPIDD_OPCODE_TYPE_SET_MONITOR_CONFIGURATION`
- `0x180014c23`: `Size of the output buffer does not match size of RDPIDD_OUT_SET_MONITOR_CONFIGURATION`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Driver::CDriverControl3::ProcessMonitorConfig(
        Rdp::Stack::Driver::CDriverControl3 *this,
        unsigned __int8 a2,
        unsigned int a3,
        const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *a4)
{
  const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *v4; // r14
  __int64 v5; // rbx
  int v6; // r13d
  unsigned int v7; // eax
  const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *v8; // rsi
  const char *v9; // rcx
  int v10; // edi
  int v11; // ebx
  unsigned int v12; // ebx
  char *Pointer; // rdi
  struct IPropertyStore *v14; // rdx
  struct _LUID *v15; // r9
  int v16; // r8d
  int v17; // r9d
  char *v18; // rbx
  int v19; // r15d
  unsigned int v20; // edi
  int v21; // edx
  __int64 v22; // rdx
  const struct _RDPCFG_MONITORCONFIG_DISPLAY_MODE *v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  const struct _RDPCFG_MONITORCONFIG_COLORIMETRY *v26; // rax
  __int64 v27; // rax
  _DWORD *v28; // rax
  unsigned int v29; // eax
  unsigned int j; // esi
  _DWORD *v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  _DWORD *v39; // rax
  size_t v40; // r8
  int v41; // edx
  int v42; // edx
  ULONG_PTR InternalHigh; // rsi
  unsigned int v44; // eax
  int v45; // r9d
  unsigned int v46; // eax
  int v47; // r9d
  unsigned int v48; // eax
  unsigned int v49; // r9d
  unsigned int v50; // eax
  unsigned int v51; // r9d
  unsigned int v52; // eax
  const char *v54; // [rsp+28h] [rbp-E0h]
  const char *v55; // [rsp+28h] [rbp-E0h]
  const char *v56; // [rsp+28h] [rbp-E0h]
  const char *v57; // [rsp+28h] [rbp-E0h]
  const char *v58; // [rsp+28h] [rbp-E0h]
  const char *v59; // [rsp+30h] [rbp-D8h]
  struct _OVERLAPPED *v60; // [rsp+38h] [rbp-D0h]
  int v61; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int v62; // [rsp+54h] [rbp-B4h] BYREF
  DWORD v63; // [rsp+58h] [rbp-B0h] BYREF
  const char *i; // [rsp+60h] [rbp-A8h] BYREF
  const char *v65; // [rsp+68h] [rbp-A0h] BYREF
  struct _OVERLAPPED v66; // [rsp+70h] [rbp-98h] BYREF
  __int128 v67; // [rsp+90h] [rbp-78h] BYREF
  __int128 v68; // [rsp+A0h] [rbp-68h]
  __int64 v69; // [rsp+B0h] [rbp-58h]
  void *v70; // [rsp+B8h] [rbp-50h]
  struct _tagpropertykey *v71[2]; // [rsp+C0h] [rbp-48h] BYREF
  struct _tagpropertykey *v72; // [rsp+D0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v66.InternalHigh = (ULONG_PTR)this;
  if ( (unsigned int)dword_18003C058 > 5 )
  {
    v62 = a3;
    i = "ProcessMonitorConfig";
    v65 = "Rdp::Stack::Driver::CDriverControl3::ProcessMonitorConfig";
    v61 = 406;
    v66.Internal = (ULONG_PTR)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&word_180035236,
      a3,
      (_DWORD)a4,
      (__int64)&v66,
      (__int64)&v61,
      (__int64)&v65,
      (__int64)&i,
      (__int64)&v62);
  }
  v67 = 0;
  v68 = 0;
  v69 = 0;
  std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(&v67);
  v7 = 24;
  v8 = v4;
  v9 = (char *)v4 + 16 * v5;
  for ( i = v9; ; v9 = i )
  {
    v62 = v7;
    if ( v8 == (const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *)v9 )
      break;
    v10 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 1) + 32LL))(*((_QWORD *)v8 + 1));
    v61 = 24;
    v11 = 24;
    if ( (v10 & 2) != 0 )
    {
      v61 = 72;
      v11 = 72;
    }
    if ( (v10 & 4) != 0 )
    {
      v11 += 16;
      v61 = v11;
    }
    if ( (v10 & 8) != 0 )
    {
      v11 += 16;
      v61 = v11;
    }
    if ( (v10 & 0x10) != 0 )
    {
      v11 += 76;
      v61 = v11;
    }
    if ( (v10 & 0x20) != 0 )
    {
      v11 += 12;
      v61 = v11;
    }
    if ( (v10 & 0x80u) != 0 )
    {
      v11 += 32;
      v61 = v11;
    }
    if ( (v10 & 1) != 0 )
    {
      v11 += 44 * (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 1) + 96LL))(*((_QWORD *)v8 + 1));
      v61 = v11;
    }
    if ( (v10 & 0x40) != 0 )
    {
      v11 += *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 1) + 112LL))(*((_QWORD *)v8 + 1));
      v61 = v11;
    }
    std::deque<unsigned int>::_Emplace_back_internal<unsigned int const &>(&v67, &v61);
    v7 = v11 + v62;
    v8 = (const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *)((char *)v8 + 16);
  }
  v12 = v7;
  std::make_unique<unsigned char [0],0>(&v66.Offset, v7);
  Pointer = (char *)v66.Pointer;
  v70 = v66.Pointer;
  memset_0(v66.Pointer, 0, v12);
  *((_DWORD *)Pointer + 2) = 10;
  *(_DWORD *)Pointer = v62;
  *((_DWORD *)Pointer + 3) = v6;
  if ( !(_BYTE)v6
    && (int)Rdp::Utils::Props::IPropertyStore_GetLuid(
              *(Rdp::Utils::Props **)(v66.InternalHigh + 8),
              v14,
              (const struct _tagpropertykey *)(Pointer + 16),
              v15) < 0
    && (unsigned int)dword_18003C058 > 3 )
  {
    v66.Internal = (ULONG_PTR)"Preferred render adapter is not specified";
    v65 = "Rdp::Stack::Driver::CDriverControl3::ProcessMonitorConfig";
    v61 = 481;
    v66.hEvent = (HANDLE)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)&dword_18003C058,
      (unsigned int)&byte_1800351FF,
      v16,
      v17,
      (__int64)&v66.hEvent,
      (__int64)&v61,
      (__int64)&v65,
      (__int64)&v66);
  }
  v18 = Pointer + 24;
  while ( v4 != (const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *)i )
  {
    v19 = *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 32LL))(*((_QWORD *)v4 + 1));
    v20 = 24;
    *(_DWORD *)v18 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v67 + 1) + 8 * ((v68 - 1) & (*((_QWORD *)&v68 + 1) >> 2)))
                               + 4LL * (BYTE8(v68) & 3));
    if ( --v69 )
      ++*((_QWORD *)&v68 + 1);
    else
      *((_QWORD *)&v68 + 1) = 0;
    v21 = 0;
    switch ( *(_DWORD *)v4 )
    {
      case 1:
        v21 = 1;
        break;
      case 2:
        v21 = 2;
        break;
      case 3:
        v21 = 3;
        break;
    }
    *((_DWORD *)v18 + 1) = v21;
    v22 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 40LL))(*((_QWORD *)v4 + 1));
    *((_DWORD *)v18 + 2) = *(_DWORD *)v22;
    *((_WORD *)v18 + 6) = *(_WORD *)(v22 + 4);
    *((_WORD *)v18 + 7) = *(_WORD *)(v22 + 6);
    v18[16] = *(_BYTE *)(v22 + 8);
    v18[17] = *(_BYTE *)(v22 + 9);
    v18[18] = *(_BYTE *)(v22 + 10);
    v18[19] = *(_BYTE *)(v22 + 11);
    v18[20] = *(_BYTE *)(v22 + 12);
    v18[21] = *(_BYTE *)(v22 + 13);
    v18[22] = *(_BYTE *)(v22 + 14);
    v18[23] = *(_BYTE *)(v22 + 15);
    if ( (v19 & 2) != 0 )
    {
      v23 = (const struct _RDPCFG_MONITORCONFIG_DISPLAY_MODE *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1)
                                                                                                 + 48LL))(*((_QWORD *)v4 + 1));
      Rdp::Stack::Driver::CDriverControl3::ConvertDisplayMode((struct _RDP_MONITORCONFIG_DISPLAY_MODE *)(v18 + 24), v23);
      v20 = 72;
    }
    if ( (v19 & 4) != 0 )
    {
      v24 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 56LL))(*((_QWORD *)v4 + 1));
      *(_DWORD *)&v18[v20] = 16;
      *(_DWORD *)&v18[v20 + 4] = 3;
      *(_DWORD *)&v18[v20 + 8] = *(_DWORD *)(v24 + 8);
      *(_DWORD *)&v18[v20 + 12] = *(_DWORD *)(v24 + 12);
      v20 += 16;
    }
    if ( (v19 & 8) != 0 )
    {
      v25 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 64LL))(*((_QWORD *)v4 + 1));
      *(_DWORD *)&v18[v20] = 16;
      *(_DWORD *)&v18[v20 + 4] = 4;
      *(_DWORD *)&v18[v20 + 8] = *(_DWORD *)(v25 + 8);
      *(_DWORD *)&v18[v20 + 12] = *(_DWORD *)(v25 + 12);
      v20 += 16;
    }
    if ( (v19 & 0x10) != 0 )
    {
      v26 = (const struct _RDPCFG_MONITORCONFIG_COLORIMETRY *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1)
                                                                                                + 72LL))(*((_QWORD *)v4 + 1));
      Rdp::Stack::Driver::CDriverControl3::ConvertColorimetry((struct _RDP_MONITORCONFIG_COLORIMETRY *)&v18[v20], v26);
      v20 += 76;
    }
    if ( (v19 & 0x20) != 0 )
    {
      v27 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 80LL))(*((_QWORD *)v4 + 1));
      *(_DWORD *)&v18[v20] = 12;
      *(_DWORD *)&v18[v20 + 4] = 6;
      *(_DWORD *)&v18[v20 + 8] = *(_DWORD *)(v27 + 8);
      v20 += 12;
    }
    if ( (v19 & 0x80u) != 0 )
    {
      v28 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 88LL))(*((_QWORD *)v4 + 1));
      *(_DWORD *)&v18[v20] = 32;
      *(_DWORD *)&v18[v20 + 4] = 8;
      *(_DWORD *)&v18[v20 + 8] = v28[2];
      *(_DWORD *)&v18[v20 + 12] = v28[3];
      *(_DWORD *)&v18[v20 + 16] = v28[4];
      *(_DWORD *)&v18[v20 + 20] = v28[5];
      *(_DWORD *)&v18[v20 + 24] = v28[6];
      *(_DWORD *)&v18[v20 + 28] = v28[7];
      v20 += 32;
    }
    if ( (v19 & 1) != 0 )
    {
      v29 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 96LL))(*((_QWORD *)v4 + 1));
      v61 = v29;
      for ( j = 0; j < v29; ++j )
      {
        v31 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)v4 + 1) + 104LL))(
                          *((_QWORD *)v4 + 1),
                          j);
        *(_DWORD *)&v18[v20] = 44;
        *(_DWORD *)&v18[v20 + 4] = 1;
        *(_DWORD *)&v18[v20 + 8] = v31[2];
        *(_DWORD *)&v18[v20 + 12] = v31[3];
        *(_DWORD *)&v18[v20 + 16] = v31[4];
        *(_DWORD *)&v18[v20 + 20] = v31[5];
        *(_DWORD *)&v18[v20 + 24] = v31[6];
        *(_DWORD *)&v18[v20 + 28] = Rdp::Stack::Driver::CDriverControl3::ConvertBpcFlags(v31 + 7, v32, v31);
        *(_DWORD *)&v18[v20 + 32] = Rdp::Stack::Driver::CDriverControl3::ConvertBpcFlags(v33 + 32, v34, v33);
        *(_DWORD *)&v18[v20 + 36] = Rdp::Stack::Driver::CDriverControl3::ConvertBpcFlags(v35 + 36, v36, v35);
        *(_DWORD *)&v18[v20 + 40] = Rdp::Stack::Driver::CDriverControl3::ConvertBpcFlags(v37 + 40, v38, v37);
        v20 += 44;
        v29 = v61;
      }
    }
    if ( (v19 & 0x40) != 0 )
    {
      v39 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 1) + 112LL))(*((_QWORD *)v4 + 1));
      v40 = (unsigned int)(*v39 - 12);
      *(_DWORD *)&v18[v20] = *v39;
      *(_DWORD *)&v18[v20 + 4] = 7;
      v41 = v39[2];
      if ( v41 )
      {
        v42 = v41 - 1;
        if ( !v42 )
        {
          *(_DWORD *)&v18[v20 + 8] = 1;
          goto LABEL_60;
        }
        if ( v42 == 1 )
        {
          *(_DWORD *)&v18[v20 + 8] = 2;
LABEL_60:
          memcpy_0(&v18[v20 + 12], v39 + 3, v40);
          v20 += *(_DWORD *)&v18[v20];
          goto LABEL_61;
        }
      }
      *(_DWORD *)&v18[v20 + 8] = 0;
      goto LABEL_60;
    }
LABEL_61:
    v18 += v20;
    v4 = (const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *)((char *)v4 + 16);
  }
  v63 = 0;
  *(_OWORD *)v71 = 0;
  LODWORD(v72) = 0;
  InternalHigh = v66.InternalHigh;
  v44 = Rdp::Stack::Driver::CDriverControl3::InternalDeviceIoControl(
          *(void **)(v66.InternalHigh + 48),
          0x80000044,
          v70,
          v62,
          v71,
          0x14u,
          &v63,
          v60);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x260,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)v44,
    (int)"Failed to send RDPIDD_OPCODE_TYPE_SET_MONITOR_CONFIGURATION",
    v54);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x266,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)0x80004005LL,
    v63 != 20,
    (bool)"Size of the output buffer does not match size of RDPIDD_OUT_SET_MONITOR_CONFIGURATION",
    v59);
  v46 = Rdp::Utils::Props::IPropertyStore_SetInt32(
          *(Rdp::Utils::Props **)(InternalHigh + 8),
          (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_X,
          (const struct _tagpropertykey *)HIDWORD(v71[0]),
          v45);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x270,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)v46,
    (int)"Failed to set PKEY_VirtualDesktop_Origin_X",
    v55);
  v48 = Rdp::Utils::Props::IPropertyStore_SetInt32(
          *(Rdp::Utils::Props **)(InternalHigh + 8),
          (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_Y,
          (const struct _tagpropertykey *)LODWORD(v71[1]),
          v47);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x277,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)v48,
    (int)"Failed to set PKEY_VirtualDesktop_Origin_Y",
    v56);
  v50 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          *(Rdp::Utils::Props **)(InternalHigh + 8),
          (struct IPropertyStore *)&PKEY_VirtualDesktop_Width,
          (const struct _tagpropertykey *)HIDWORD(v71[1]),
          v49);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x27E,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)v50,
    (int)"Failed to set PKEY_VirtualDesktop_Width",
    v57);
  v52 = Rdp::Utils::Props::IPropertyStore_SetUInt32(
          *(Rdp::Utils::Props **)(InternalHigh + 8),
          (struct IPropertyStore *)&PKEY_VirtualDesktop_Height,
          (const struct _tagpropertykey *)(unsigned int)v72,
          v51);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x285,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\drivercontrol.cpp",
    (const char *)v52,
    (int)"Failed to set PKEY_VirtualDesktop_Height",
    v58);
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v66.Offset);
  std::deque<unsigned int>::~deque<unsigned int>(&v67);
  return 0;
}

```

## disassembly

```asm
0x180014570  mov     [rsp+arg_8], rbx
0x180014575  mov     [rsp+arg_10], rsi
0x18001457a  push    rdi
0x18001457b  push    r12
0x18001457d  push    r13
0x18001457f  push    r14
0x180014581  push    r15
0x180014583  sub     rsp, 0E0h
0x18001458a  mov     rax, cs:__security_cookie
0x180014591  xor     rax, rsp
0x180014594  mov     [rsp+108h+var_30], rax
0x18001459c  mov     r14, r9
0x18001459f  mov     ebx, r8d
0x1800145a2  movzx   r13d, dl
0x1800145a6  mov     [rsp+108h+var_98.InternalHigh], rcx
0x1800145ab  mov     eax, cs:dword_18003C058
0x1800145b1  cmp     eax, 5
0x1800145b4  jbe     short loc_18001462D
0x1800145b6  mov     [rsp+108h+var_B4], ebx
0x1800145ba  lea     rax, aProcessmonitor; "ProcessMonitorConfig"
0x1800145c1  mov     [rsp+108h+var_A8], rax
0x1800145c6  lea     r15, aRdpStackDriver; "Rdp::Stack::Driver::CDriverControl3::Pr"...
0x1800145cd  mov     [rsp+108h+var_A0], r15
0x1800145d2  mov     [rsp+108h+var_B8], 196h
0x1800145da  lea     r12, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800145e1  mov     [rsp+108h+var_98.Internal], r12
0x1800145e6  lea     rax, [rsp+108h+var_B4]
0x1800145eb  mov     [rsp+108h+var_C8], rax
0x1800145f0  lea     rax, [rsp+108h+var_A8]
0x1800145f5  mov     [rsp+108h+var_D0], rax
0x1800145fa  lea     rax, [rsp+108h+var_A0]
0x1800145ff  mov     [rsp+108h+var_D8], rax
0x180014604  lea     rax, [rsp+108h+var_B8]
0x180014609  mov     qword ptr [rsp+108h+var_E0], rax
0x18001460e  lea     rax, [rsp+108h+var_98]
0x180014613  mov     [rsp+108h+var_E8], rax
0x180014618  lea     rdx, word_180035236
0x18001461f  lea     rcx, dword_18003C058
0x180014626  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18001462b  jmp     short loc_18001463B
0x18001462d  lea     r15, aRdpStackDriver; "Rdp::Stack::Driver::CDriverControl3::Pr"...
0x180014634  lea     r12, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001463b  xorps   xmm0, xmm0
0x18001463e  movdqu  [rsp+108h+var_78], xmm0
0x180014647  xorps   xmm1, xmm1
0x18001464a  movdqu  [rsp+108h+var_68], xmm1
0x180014653  mov     [rsp+108h+var_58], 0
0x18001465f  lea     rcx, [rsp+108h+var_78]
0x180014667  call    ??$_Alloc_proxy@V?$allocator@U_Container_proxy@std@@@std@@@_Container_base12@std@@QEAAX$$QEAV?$allocator@U_Container_proxy@std@@@1@@Z; std::_Container_base12::_Alloc_proxy<std::allocator<std::_Container_proxy>>(std::allocator<std::_Container_proxy> &&)
0x18001466c  nop
0x18001466d  mov     eax, 18h
0x180014672  mov     rsi, r14
0x180014675  add     rbx, rbx
0x180014678  lea     rcx, [r14+rbx*8]
0x18001467c  mov     [rsp+108h+var_A8], rcx
0x180014681  mov     [rsp+108h+var_B4], eax
0x180014685  cmp     rsi, rcx
0x180014688  jz      loc_18001475B
0x18001468e  mov     rcx, [rsi+8]
0x180014692  mov     rax, [rcx]
0x180014695  mov     rax, [rax+20h]
0x180014699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001469e  mov     edi, [rax]
0x1800146a0  mov     eax, 18h
0x1800146a5  mov     [rsp+108h+var_B8], eax
0x1800146a9  mov     ebx, eax
0x1800146ab  test    dil, 2
0x1800146af  jz      short loc_1800146BA
0x1800146b1  lea     eax, [rbx+30h]
0x1800146b4  mov     [rsp+108h+var_B8], eax
0x1800146b8  mov     ebx, eax
0x1800146ba  test    dil, 4
0x1800146be  jz      short loc_1800146C7
0x1800146c0  add     ebx, 10h
0x1800146c3  mov     [rsp+108h+var_B8], ebx
0x1800146c7  test    dil, 8
0x1800146cb  jz      short loc_1800146D4
0x1800146cd  add     ebx, 10h
0x1800146d0  mov     [rsp+108h+var_B8], ebx
0x1800146d4  test    dil, 10h
0x1800146d8  jz      short loc_1800146E1
0x1800146da  add     ebx, 4Ch ; 'L'
0x1800146dd  mov     [rsp+108h+var_B8], ebx
0x1800146e1  test    dil, 20h
0x1800146e5  jz      short loc_1800146EE
0x1800146e7  add     ebx, 0Ch
0x1800146ea  mov     [rsp+108h+var_B8], ebx
0x1800146ee  test    dil, dil
0x1800146f1  jns     short loc_1800146FA
0x1800146f3  add     ebx, 20h ; ' '
0x1800146f6  mov     [rsp+108h+var_B8], ebx
0x1800146fa  test    dil, 1
0x1800146fe  jz      short loc_180014719
0x180014700  mov     rcx, [rsi+8]
0x180014704  mov     rax, [rcx]
0x180014707  mov     rax, [rax+60h]
0x18001470b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014710  imul    eax, 2Ch ; ','
0x180014713  add     ebx, eax
0x180014715  mov     [rsp+108h+var_B8], ebx
0x180014719  test    dil, 40h
0x18001471d  jz      short loc_180014735
0x18001471f  mov     rcx, [rsi+8]
0x180014723  mov     rax, [rcx]
0x180014726  mov     rax, [rax+70h]
0x18001472a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001472f  add     ebx, [rax]
0x180014731  mov     [rsp+108h+var_B8], ebx
0x180014735  lea     rdx, [rsp+108h+var_B8]
0x18001473a  lea     rcx, [rsp+108h+var_78]
0x180014742  call    ??$_Emplace_back_internal@AEBI@?$deque@IV?$allocator@I@std@@@std@@AEAAXAEBI@Z; std::deque<uint>::_Emplace_back_internal<uint const &>(uint const &)
0x180014747  mov     eax, [rsp+108h+var_B4]
0x18001474b  add     eax, ebx
0x18001474d  add     rsi, 10h
0x180014751  mov     rcx, [rsp+108h+var_A8]
0x180014756  jmp     loc_180014681
0x18001475b  mov     ebx, eax
0x18001475d  mov     edx, eax
0x18001475f  lea     rcx, [rsp+108h+var_98.10h]
0x180014767  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x18001476c  nop
0x18001476d  mov     rdi, qword ptr [rsp+108h+var_98.10h]
0x180014775  mov     [rsp+108h+var_50], rdi
0x18001477d  mov     r8d, ebx; Size
0x180014780  xor     edx, edx; Val
0x180014782  mov     rcx, rdi; void *
0x180014785  call    memset_0
0x18001478a  mov     dword ptr [rdi+8], 0Ah
0x180014791  mov     eax, [rsp+108h+var_B4]
0x180014795  mov     [rdi], eax
0x180014797  mov     [rdi+0Ch], r13d
0x18001479b  test    r13b, r13b
0x18001479e  jnz     loc_180014824
0x1800147a4  lea     r8, [rdi+10h]; struct _tagpropertykey *
0x1800147a8  mov     rsi, [rsp+108h+var_98.InternalHigh]
0x1800147ad  mov     rcx, [rsi+8]; this
0x1800147b1  call    ?IPropertyStore_GetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetLuid(IPropertyStore *,_tagpropertykey const &,_LUID *)
0x1800147b6  test    eax, eax
0x1800147b8  jns     short loc_180014824
0x1800147ba  mov     eax, cs:dword_18003C058
0x1800147c0  cmp     eax, 3
0x1800147c3  jbe     short loc_180014824
0x1800147c5  lea     rax, aPreferredRende; "Preferred render adapter is not specifi"...
0x1800147cc  mov     [rsp+108h+var_98.Internal], rax
0x1800147d1  mov     [rsp+108h+var_A0], r15
0x1800147d6  mov     [rsp+108h+var_B8], 1E1h
0x1800147de  mov     [rsp+108h+var_98.hEvent], r12
0x1800147e6  lea     rax, [rsp+108h+var_98]
0x1800147eb  mov     [rsp+108h+var_D0], rax; struct _OVERLAPPED *
0x1800147f0  lea     rax, [rsp+108h+var_A0]
0x1800147f5  mov     [rsp+108h+var_D8], rax
0x1800147fa  lea     rax, [rsp+108h+var_B8]
0x1800147ff  mov     qword ptr [rsp+108h+var_E0], rax
0x180014804  lea     rax, [rsp+108h+var_98.hEvent]
0x18001480c  mov     [rsp+108h+var_E8], rax
0x180014811  lea     rdx, byte_1800351FF
0x180014818  lea     rcx, dword_18003C058
0x18001481f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180014824  lea     rbx, [rdi+18h]
0x180014828  cmp     r14, [rsp+108h+var_A8]
0x18001482d  jz      loc_180014B94
0x180014833  mov     rcx, [r14+8]
0x180014837  mov     rax, [rcx]
0x18001483a  mov     rax, [rax+20h]
0x18001483e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014843  mov     r15d, [rax]
0x180014846  mov     edi, 18h
0x18001484b  mov     rdx, qword ptr [rsp+108h+var_68+8]
0x180014853  mov     rcx, rdx
0x180014856  shr     rcx, 2
0x18001485a  mov     rax, qword ptr [rsp+108h+var_68]
0x180014862  dec     rax
0x180014865  and     rcx, rax
0x180014868  and     edx, 3
0x18001486b  mov     rax, qword ptr [rsp+108h+var_78+8]
0x180014873  mov     rcx, [rax+rcx*8]
0x180014877  mov     eax, [rcx+rdx*4]
0x18001487a  mov     [rbx], eax
0x18001487c  sub     [rsp+108h+var_58], 1
0x180014885  jnz     short loc_180014895
0x180014887  mov     qword ptr [rsp+108h+var_68+8], 0
0x180014893  jmp     short loc_18001489D
0x180014895  inc     qword ptr [rsp+108h+var_68+8]
0x18001489d  xor     edx, edx
0x18001489f  mov     ecx, [r14]
0x1800148a2  sub     ecx, 1
0x1800148a5  jz      short loc_1800148BD
0x1800148a7  sub     ecx, 1
0x1800148aa  jz      short loc_1800148B6
0x1800148ac  cmp     ecx, 1
0x1800148af  jnz     short loc_1800148C2
0x1800148b1  lea     edx, [rcx+2]
0x1800148b4  jmp     short loc_1800148C2
0x1800148b6  mov     edx, 2
0x1800148bb  jmp     short loc_1800148C2
0x1800148bd  mov     edx, 1
0x1800148c2  mov     [rbx+4], edx
0x1800148c5  mov     rcx, [r14+8]
0x1800148c9  mov     rax, [rcx]
0x1800148cc  mov     rax, [rax+28h]
0x1800148d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148d5  mov     rdx, rax
0x1800148d8  mov     ecx, [rax]
0x1800148da  mov     [rbx+8], ecx
0x1800148dd  movzx   ecx, word ptr [rax+4]
0x1800148e1  mov     [rbx+0Ch], cx
0x1800148e5  movzx   ecx, word ptr [rax+6]
0x1800148e9  mov     [rbx+0Eh], cx
0x1800148ed  mov     cl, [rax+8]
0x1800148f0  mov     [rbx+10h], cl
0x1800148f3  mov     cl, [rax+9]
0x1800148f6  mov     [rbx+11h], cl
0x1800148f9  mov     cl, [rax+0Ah]
0x1800148fc  mov     [rbx+12h], cl
0x1800148ff  mov     al, [rax+0Bh]
0x180014902  mov     [rbx+13h], al
0x180014905  mov     al, [rdx+0Ch]
0x180014908  mov     [rbx+14h], al
0x18001490b  mov     al, [rdx+0Dh]
0x18001490e  mov     [rbx+15h], al
0x180014911  mov     al, [rdx+0Eh]
0x180014914  mov     [rbx+16h], al
0x180014917  mov     al, [rdx+0Fh]
0x18001491a  mov     [rbx+17h], al
0x18001491d  test    r15b, 2
0x180014921  jz      short loc_180014944
0x180014923  mov     rcx, [r14+8]
0x180014927  mov     rax, [rcx]
0x18001492a  mov     rax, [rax+30h]
0x18001492e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014933  lea     rcx, [rbx+18h]; struct _RDP_MONITORCONFIG_DISPLAY_MODE *
0x180014937  mov     rdx, rax; struct _RDPCFG_MONITORCONFIG_DISPLAY_MODE *
0x18001493a  call    ?ConvertDisplayMode@CDriverControl3@Driver@Stack@Rdp@@CAXPEAU_RDP_MONITORCONFIG_DISPLAY_MODE@@AEBU_RDPCFG_MONITORCONFIG_DISPLAY_MODE@@@Z; Rdp::Stack::Driver::CDriverControl3::ConvertDisplayMode(_RDP_MONITORCONFIG_DISPLAY_MODE *,_RDPCFG_MONITORCONFIG_DISPLAY_MODE const &)
0x18001493f  mov     edi, 48h ; 'H'
0x180014944  test    r15b, 4
0x180014948  jz      short loc_18001497C
0x18001494a  mov     esi, edi
0x18001494c  mov     rcx, [r14+8]
0x180014950  mov     rax, [rcx]
0x180014953  mov     rax, [rax+38h]
0x180014957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001495c  mov     dword ptr [rsi+rbx], 10h
0x180014963  mov     dword ptr [rsi+rbx+4], 3
0x18001496b  mov     ecx, [rax+8]
0x18001496e  mov     [rsi+rbx+8], ecx
0x180014972  mov     eax, [rax+0Ch]
0x180014975  mov     [rsi+rbx+0Ch], eax
0x180014979  add     edi, 10h
0x18001497c  test    r15b, 8
0x180014980  jz      short loc_1800149B4
0x180014982  mov     rcx, [r14+8]
0x180014986  mov     rax, [rcx]
0x180014989  mov     rax, [rax+40h]
0x18001498d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014992  mov     edx, edi
0x180014994  mov     dword ptr [rdx+rbx], 10h
0x18001499b  mov     dword ptr [rdx+rbx+4], 4
0x1800149a3  mov     ecx, [rax+8]
0x1800149a6  mov     [rdx+rbx+8], ecx
0x1800149aa  mov     eax, [rax+0Ch]
0x1800149ad  mov     [rdx+rbx+0Ch], eax
0x1800149b1  add     edi, 10h
0x1800149b4  test    r15b, 10h
0x1800149b8  jz      short loc_1800149DA
0x1800149ba  mov     rcx, [r14+8]
0x1800149be  mov     rax, [rcx]
0x1800149c1  mov     rax, [rax+48h]
0x1800149c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149ca  mov     ecx, edi
0x1800149cc  add     rcx, rbx; struct _RDP_MONITORCONFIG_COLORIMETRY *
0x1800149cf  mov     rdx, rax; struct _RDPCFG_MONITORCONFIG_COLORIMETRY *
0x1800149d2  call    ?ConvertColorimetry@CDriverControl3@Driver@Stack@Rdp@@CAXPEAU_RDP_MONITORCONFIG_COLORIMETRY@@AEBU_RDPCFG_MONITORCONFIG_COLORIMETRY@@@Z; Rdp::Stack::Driver::CDriverControl3::ConvertColorimetry(_RDP_MONITORCONFIG_COLORIMETRY *,_RDPCFG_MONITORCONFIG_COLORIMETRY const &)
0x1800149d7  add     edi, 4Ch ; 'L'
0x1800149da  test    r15b, 20h
0x1800149de  jz      short loc_180014A0B
0x1800149e0  mov     rcx, [r14+8]
0x1800149e4  mov     rax, [rcx]
0x1800149e7  mov     rax, [rax+50h]
0x1800149eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149f0  mov     ecx, edi
0x1800149f2  mov     dword ptr [rcx+rbx], 0Ch
0x1800149f9  mov     dword ptr [rcx+rbx+4], 6
0x180014a01  mov     eax, [rax+8]
0x180014a04  mov     [rcx+rbx+8], eax
0x180014a08  add     edi, 0Ch
0x180014a0b  test    r15b, r15b
0x180014a0e  jns     short loc_180014A5E
0x180014a10  mov     esi, edi
0x180014a12  mov     rcx, [r14+8]
0x180014a16  mov     rax, [rcx]
0x180014a19  mov     rax, [rax+58h]
0x180014a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a22  mov     dword ptr [rsi+rbx], 20h ; ' '
0x180014a29  mov     dword ptr [rsi+rbx+4], 8
0x180014a31  mov     ecx, [rax+8]
0x180014a34  mov     [rsi+rbx+8], ecx
0x180014a38  mov     ecx, [rax+0Ch]
0x180014a3b  mov     [rsi+rbx+0Ch], ecx
0x180014a3f  mov     ecx, [rax+10h]
0x180014a42  mov     [rsi+rbx+10h], ecx
  ... truncated ...
```
