# Rdp::Stack::Graphics::CGrfxPipeline::ProcessMonitorConfig(bool,std::vector<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO,std::allocator<Rdp::Stack::RDPLITE_MONITORCONFIG_INFO>> const &)

- ea: `0x18000b578`
- end: `0x18000b96b`
- name: `?ProcessMonitorConfig@CGrfxPipeline@Graphics@Stack@Rdp@@QEAAJ_NAEBV?$vector@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@V?$allocator@URDPLITE_MONITORCONFIG_INFO@Stack@Rdp@@@std@@@std@@@Z`
- size: `1011`
- prototype: `__int64 __fastcall(__int64, _BOOL8, const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO **)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c0f0`
- `0x180016304`

## callees

- `0x180001448`
- `0x1800014e8`
- `0x1800036f0`
- `0x18000a938`
- `0x18000acd0`
- `0x18000ad04`
- `0x18000aff0`
- `0x18000b530`
- `0x18000b578`
- `0x18000b974`
- `0x18000cf28`
- `0x18000cf70`
- `0x18000d004`
- `0x18000d070`
- `0x18000d098`
- `0x18000d6cc`
- `0x180019894`
- `0x18002a010`

## string_xrefs

- `0x18000b607`: `Failed to commit monitors`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Graphics::CGrfxPipeline::ProcessMonitorConfig(
        __int64 a1,
        _BOOL8 a2,
        const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO **a3)
{
  bool v4; // bl
  Rdp::Stack::Shim::CAdapterShim *v6; // rcx
  unsigned int *v7; // r9
  __int64 v8; // rcx
  unsigned int v9; // eax
  unsigned int UInt32; // eax
  unsigned int *v11; // r9
  unsigned int v12; // eax
  unsigned int v13; // eax
  const char *v14; // r9
  unsigned int v15; // r14d
  const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *i; // rcx
  unsigned int v17; // eax
  const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *v18; // rbx
  const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *v19; // r15
  __int64 v20; // rsi
  bool v21; // dl
  bool v22; // dl
  char v23; // al
  _DWORD *v24; // rcx
  _DWORD *v25; // rcx
  int v26; // r8d
  int v27; // r9d
  __int64 result; // rax
  const char *v29; // [rsp+28h] [rbp-B0h]
  const char *v30; // [rsp+28h] [rbp-B0h]
  const char *v31; // [rsp+28h] [rbp-B0h]
  __int64 v32; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int v33; // [rsp+38h] [rbp-A0h] BYREF
  _QWORD v34[2]; // [rsp+40h] [rbp-98h] BYREF
  char v35; // [rsp+50h] [rbp-88h]
  __int64 v36; // [rsp+58h] [rbp-80h]
  __int64 v37; // [rsp+60h] [rbp-78h]
  __int64 v38; // [rsp+68h] [rbp-70h]
  char v39[32]; // [rsp+70h] [rbp-68h] BYREF
  __int64 *v40; // [rsp+90h] [rbp-48h]
  __int64 v41; // [rsp+98h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    v4 = a2;
    v6 = *(Rdp::Stack::Shim::CAdapterShim **)(a1 + 128);
    if ( v6 )
      Rdp::Stack::Shim::CAdapterShim::ProcessMonitorConfig(v6, a2, (a3[1] - *a3) >> 4, *a3);
    LOBYTE(a2) = v4;
    (*(void (__fastcall **)(_QWORD, _BOOL8, signed __int64, const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *))(**(_QWORD **)(a1 + 120) + 48LL))(
      *(_QWORD *)(a1 + 120),
      a2,
      (a3[1] - *a3) >> 4,
      *a3);
    v8 = *(_QWORD *)(a1 + 128);
    if ( v8 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v8 + 344) + 64LL))(*(_QWORD *)(v8 + 344));
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x392,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\adaptershim.cpp",
        (const char *)v9,
        (int)"Failed to commit monitors",
        v29);
    }
    v33 = 0;
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *(Rdp::Utils::Props **)(a1 + 104),
               (struct IPropertyStore *)&PKEY_VirtualDesktop_Width,
               (const struct _tagpropertykey *)&v33,
               v7);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Width",
      v29);
    LODWORD(v32) = 0;
    v12 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
            *(Rdp::Utils::Props **)(a1 + 104),
            (struct IPropertyStore *)&PKEY_VirtualDesktop_Height,
            (const struct _tagpropertykey *)&v32,
            v11);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x30A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      (const char *)v12,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Height",
      v30);
    v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 112) + 32LL))(
            *(_QWORD *)(a1 + 112),
            v33,
            (unsigned int)v32);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x313,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
      (const char *)v13,
      (int)"OnResetInputParams failed",
      v31);
    if ( v4 || *(_BYTE *)(a1 + 173) )
      return 0;
    v35 = 4;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v34[1] = v34;
    v34[0] = v34;
    v15 = 0;
    for ( i = *a3; i != a3[1]; i = (const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *)((char *)i + 16) )
    {
      v17 = v15 + 1;
      if ( *(_DWORD *)i != 1 )
        v17 = v15;
      v15 = v17;
    }
    JsonWriter::BeginObject((JsonWriter *)v34);
    JsonWriter::WriteMemberName((JsonWriter *)v34, "desktopWidth");
    JsonWriter::WriteValue((JsonWriter *)v34, v33);
    JsonWriter::WriteMemberName((JsonWriter *)v34, "desktopHeight");
    JsonWriter::WriteValue((JsonWriter *)v34, v32);
    JsonWriter::WriteMemberName((JsonWriter *)v34, "numMonitors");
    JsonWriter::WriteValue((JsonWriter *)v34, v15);
    JsonWriter::WriteMemberName((JsonWriter *)v34, "monitorInfo");
    JsonWriter::WriteSeparator((JsonWriter *)v34);
    v35 &= ~4u;
    JsonWriter::Write((JsonWriter *)v34, 91);
    JsonWriter::PushScope((JsonWriter *)v34, 5u);
    v18 = *a3;
    v19 = a3[1];
    while ( v18 != v19 )
    {
      if ( *(_DWORD *)v18 == 1 )
      {
        v20 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v18 + 1) + 48LL))(*((_QWORD *)v18 + 1));
        JsonWriter::BeginObject((JsonWriter *)v34);
        JsonWriter::WriteMemberName((JsonWriter *)v34, "width");
        JsonWriter::WriteValue((JsonWriter *)v34, *(_DWORD *)(v20 + 16));
        JsonWriter::WriteMemberName((JsonWriter *)v34, "height");
        JsonWriter::WriteValue((JsonWriter *)v34, *(_DWORD *)(v20 + 20));
        JsonWriter::EndObject((JsonWriter *)v34, v21);
      }
      v18 = (const struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *)((char *)v18 + 16);
    }
    JsonWriter::PopScope((JsonWriter *)v34);
    JsonWriter::Write((JsonWriter *)v34, 93);
    if ( (v35 & 1) != 0 )
    {
      v23 = v35 | 0x14;
    }
    else
    {
      if ( (v35 & 2) == 0 )
      {
LABEL_23:
        JsonWriter::EndObject((JsonWriter *)v34, v22);
        JsonWriter::Write((JsonWriter *)v34, 0);
        v24 = *(_DWORD **)(wil::details::static_lazy<RdpDiagnosticsProvider>::get() + 8);
        if ( *v24 > 5u )
        {
          LODWORD(v32) = v15;
          v40 = &v32;
          v41 = 4;
          tlgWriteTransfer_EventWriteTransfer(v24, &unk_180034E98, 0, 0, 3, v39);
        }
        v25 = *(_DWORD **)(wil::details::static_lazy<RdpDiagnosticsProvider>::get() + 8);
        if ( *v25 > 5u )
        {
          v32 = v36;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (_DWORD)v25,
            (unsigned int)&byte_180034EC7,
            v26,
            v27,
            (__int64)&v32);
        }
        JsonWriter::~JsonWriter((JsonWriter *)v34);
        *(_BYTE *)(a1 + 173) = 1;
        return 0;
      }
      v23 = v35 | 0x18;
    }
    v35 = v23;
    goto LABEL_23;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x324,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18000b578  push    rbx
0x18000b57a  push    rsi
0x18000b57b  push    rdi
0x18000b57c  push    r14
0x18000b57e  push    r15
0x18000b580  sub     rsp, 0B0h
0x18000b587  mov     rax, cs:__security_cookie
0x18000b58e  xor     rax, rsp
0x18000b591  mov     [rsp+0D8h+var_38], rax
0x18000b599  mov     rsi, r8
0x18000b59c  mov     bl, dl
0x18000b59e  mov     rdi, rcx
0x18000b5a1  mov     rcx, [rcx+80h]; this
0x18000b5a8  test    rcx, rcx
0x18000b5ab  jz      short loc_18000B5C0
0x18000b5ad  mov     r8, [r8+8]
0x18000b5b1  sub     r8, [rsi]
0x18000b5b4  sar     r8, 4; unsigned int
0x18000b5b8  mov     r9, [rsi]; struct Rdp::Stack::RDPLITE_MONITORCONFIG_INFO *
0x18000b5bb  call    ?ProcessMonitorConfig@CAdapterShim@Shim@Stack@Rdp@@QEAAX_NIPEBURDPLITE_MONITORCONFIG_INFO@34@@Z; Rdp::Stack::Shim::CAdapterShim::ProcessMonitorConfig(bool,uint,Rdp::Stack::RDPLITE_MONITORCONFIG_INFO const *)
0x18000b5c0  mov     rcx, [rdi+78h]
0x18000b5c4  mov     rax, [rcx]
0x18000b5c7  mov     r8, [rsi+8]
0x18000b5cb  sub     r8, [rsi]
0x18000b5ce  sar     r8, 4
0x18000b5d2  mov     r9, [rsi]
0x18000b5d5  mov     dl, bl
0x18000b5d7  mov     rax, [rax+30h]
0x18000b5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5e0  mov     rcx, [rdi+80h]
0x18000b5e7  test    rcx, rcx
0x18000b5ea  jz      short loc_18000B627
0x18000b5ec  mov     rcx, [rcx+158h]
0x18000b5f3  mov     rax, [rcx]
0x18000b5f6  mov     rax, [rax+40h]
0x18000b5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5ff  mov     rcx, [rsp+0D8h]; this
0x18000b607  lea     rdx, aFailedToCommit; "Failed to commit monitors"
0x18000b60e  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x18000b613  mov     r9d, eax; char *
0x18000b616  lea     r8, aOnecoreuapTerm_25; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000b61d  mov     edx, 392h; void *
0x18000b622  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000b627  mov     dword ptr [rsp+0D8h+var_A8.fmtid.Data4], 0
0x18000b62f  lea     r8, [rsp+0D8h+var_A8.fmtid.Data4]; struct _tagpropertykey *
0x18000b634  lea     rdx, PKEY_VirtualDesktop_Width; struct IPropertyStore *
0x18000b63b  mov     rcx, [rdi+68h]; this
0x18000b63f  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x18000b644  mov     rcx, [rsp+0D8h]; this
0x18000b64c  lea     rdx, aFailedToRetrie_9; "Failed to retrieve PKEY_VirtualDesktop_"...
0x18000b653  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x18000b658  mov     r9d, eax; char *
0x18000b65b  lea     r14, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000b662  mov     r8, r14; unsigned int
0x18000b665  mov     edx, 302h; void *
0x18000b66a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000b66f  mov     [rsp+0D8h+var_A8.fmtid.Data1], 0
0x18000b677  lea     r8, [rsp+0D8h+var_A8]; struct _tagpropertykey *
0x18000b67c  lea     rdx, PKEY_VirtualDesktop_Height; struct IPropertyStore *
0x18000b683  mov     rcx, [rdi+68h]; this
0x18000b687  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x18000b68c  mov     rcx, [rsp+0D8h]; this
0x18000b694  lea     rdx, aFailedToRetrie_6; "Failed to retrieve PKEY_VirtualDesktop_"...
0x18000b69b  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x18000b6a0  mov     r9d, eax; char *
0x18000b6a3  mov     r8, r14; unsigned int
0x18000b6a6  mov     edx, 30Ah; void *
0x18000b6ab  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000b6b0  mov     rcx, [rdi+70h]
0x18000b6b4  mov     rax, [rcx]
0x18000b6b7  mov     r8d, [rsp+0D8h+var_A8.fmtid.Data1]
0x18000b6bc  mov     edx, dword ptr [rsp+0D8h+var_A8.fmtid.Data4]
0x18000b6c0  mov     rax, [rax+20h]
0x18000b6c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6c9  mov     rcx, [rsp+0D8h]; this
0x18000b6d1  lea     rdx, aOnresetinputpa; "OnResetInputParams failed"
0x18000b6d8  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x18000b6dd  mov     r9d, eax; char *
0x18000b6e0  mov     r8, r14; unsigned int
0x18000b6e3  mov     edx, 313h; void *
0x18000b6e8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000b6ed  test    bl, bl
0x18000b6ef  jnz     loc_18000B943
0x18000b6f5  cmp     [rdi+0ADh], bl
0x18000b6fb  jnz     loc_18000B943
0x18000b701  mov     [rsp+0D8h+var_88], 4
0x18000b706  mov     [rsp+0D8h+var_80], 0
0x18000b70f  mov     [rsp+0D8h+var_78], 0
0x18000b718  mov     [rsp+0D8h+var_70], 0
0x18000b721  lea     rax, [rsp+0D8h+var_A8.pid]
0x18000b726  mov     [rsp+48h], rax
0x18000b72b  lea     rax, [rsp+0D8h+var_A8.pid]
0x18000b730  mov     qword ptr [rsp+0D8h+var_A8.pid], rax
0x18000b735  xor     r14d, r14d
0x18000b738  mov     rcx, [rsi]
0x18000b73b  jmp     short loc_18000B74F
0x18000b73d  lea     eax, [r14+1]
0x18000b741  cmp     dword ptr [rcx], 1
0x18000b744  cmovnz  eax, r14d
0x18000b748  mov     r14d, eax
0x18000b74b  add     rcx, 10h
0x18000b74f  cmp     rcx, [rsi+8]
0x18000b753  jnz     short loc_18000B73D
0x18000b755  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b75a  call    ?BeginObject@JsonWriter@@QEAAXXZ; JsonWriter::BeginObject(void)
0x18000b75f  lea     rdx, aDesktopwidth; "desktopWidth"
0x18000b766  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b76b  call    ?WriteMemberName@JsonWriter@@QEAAXPEBD@Z; JsonWriter::WriteMemberName(char const *)
0x18000b770  mov     edx, dword ptr [rsp+0D8h+var_A8.fmtid.Data4]; unsigned int
0x18000b774  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b779  call    ?WriteValue@JsonWriter@@QEAAXI@Z; JsonWriter::WriteValue(uint)
0x18000b77e  lea     rdx, aDesktopheight; "desktopHeight"
0x18000b785  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b78a  call    ?WriteMemberName@JsonWriter@@QEAAXPEBD@Z; JsonWriter::WriteMemberName(char const *)
0x18000b78f  mov     edx, [rsp+0D8h+var_A8.fmtid.Data1]; unsigned int
0x18000b793  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b798  call    ?WriteValue@JsonWriter@@QEAAXI@Z; JsonWriter::WriteValue(uint)
0x18000b79d  lea     rdx, aNummonitors; "numMonitors"
0x18000b7a4  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b7a9  call    ?WriteMemberName@JsonWriter@@QEAAXPEBD@Z; JsonWriter::WriteMemberName(char const *)
0x18000b7ae  mov     edx, r14d; unsigned int
0x18000b7b1  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b7b6  call    ?WriteValue@JsonWriter@@QEAAXI@Z; JsonWriter::WriteValue(uint)
0x18000b7bb  lea     rdx, aMonitorinfo; "monitorInfo"
0x18000b7c2  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b7c7  call    ?WriteMemberName@JsonWriter@@QEAAXPEBD@Z; JsonWriter::WriteMemberName(char const *)
0x18000b7cc  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b7d1  call    ?WriteSeparator@JsonWriter@@AEAAXXZ; JsonWriter::WriteSeparator(void)
0x18000b7d6  and     [rsp+0D8h+var_88], 0FBh
0x18000b7db  mov     dl, 5Bh ; '['; char
0x18000b7dd  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b7e2  call    ?Write@JsonWriter@@AEAAXD@Z; JsonWriter::Write(char)
0x18000b7e7  mov     dl, 5; unsigned __int8
0x18000b7e9  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b7ee  call    ?PushScope@JsonWriter@@AEAAXE@Z; JsonWriter::PushScope(uchar)
0x18000b7f3  mov     rbx, [rsi]
0x18000b7f6  mov     r15, [rsi+8]
0x18000b7fa  cmp     rbx, r15
0x18000b7fd  jz      short loc_18000B86D
0x18000b7ff  cmp     dword ptr [rbx], 1
0x18000b802  jnz     short loc_18000B867
0x18000b804  mov     rcx, [rbx+8]
0x18000b808  mov     rax, [rcx]
0x18000b80b  mov     rax, [rax+30h]
0x18000b80f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b814  mov     rsi, rax
0x18000b817  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b81c  call    ?BeginObject@JsonWriter@@QEAAXXZ; JsonWriter::BeginObject(void)
0x18000b821  lea     rdx, aWidth; "width"
0x18000b828  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b82d  call    ?WriteMemberName@JsonWriter@@QEAAXPEBD@Z; JsonWriter::WriteMemberName(char const *)
0x18000b832  mov     edx, [rsi+10h]; unsigned int
0x18000b835  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b83a  call    ?WriteValue@JsonWriter@@QEAAXI@Z; JsonWriter::WriteValue(uint)
0x18000b83f  lea     rdx, aHeight; "height"
0x18000b846  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b84b  call    ?WriteMemberName@JsonWriter@@QEAAXPEBD@Z; JsonWriter::WriteMemberName(char const *)
0x18000b850  mov     edx, [rsi+14h]; unsigned int
0x18000b853  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b858  call    ?WriteValue@JsonWriter@@QEAAXI@Z; JsonWriter::WriteValue(uint)
0x18000b85d  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b862  call    ?EndObject@JsonWriter@@QEAAX_N@Z; JsonWriter::EndObject(bool)
0x18000b867  add     rbx, 10h
0x18000b86b  jmp     short loc_18000B7FA
0x18000b86d  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b872  call    ?PopScope@JsonWriter@@AEAAXXZ; JsonWriter::PopScope(void)
0x18000b877  mov     dl, 5Dh ; ']'; char
0x18000b879  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b87e  call    ?Write@JsonWriter@@AEAAXD@Z; JsonWriter::Write(char)
0x18000b883  mov     al, [rsp+0D8h+var_88]
0x18000b887  test    al, 1
0x18000b889  jz      short loc_18000B88F
0x18000b88b  or      al, 14h
0x18000b88d  jmp     short loc_18000B895
0x18000b88f  test    al, 2
0x18000b891  jz      short loc_18000B899
0x18000b893  or      al, 18h
0x18000b895  mov     [rsp+0D8h+var_88], al
0x18000b899  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b89e  call    ?EndObject@JsonWriter@@QEAAX_N@Z; JsonWriter::EndObject(bool)
0x18000b8a3  xor     edx, edx; char
0x18000b8a5  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b8aa  call    ?Write@JsonWriter@@AEAAXD@Z; JsonWriter::Write(char)
0x18000b8af  call    ?get@?$static_lazy@VRdpDiagnosticsProvider@@@details@wil@@QEAAPEAVRdpDiagnosticsProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpDiagnosticsProvider>::get(void (*)(void))
0x18000b8b4  mov     rcx, [rax+8]
0x18000b8b8  mov     eax, [rcx]
0x18000b8ba  cmp     eax, 5
0x18000b8bd  jbe     short loc_18000B901
0x18000b8bf  mov     [rsp+0D8h+var_A8.fmtid.Data1], r14d
0x18000b8c4  lea     rax, [rsp+0D8h+var_A8]
0x18000b8c9  mov     [rsp+0D8h+var_48], rax
0x18000b8d1  mov     [rsp+0D8h+var_40], 4
0x18000b8dd  lea     rax, [rsp+0D8h+var_68]
0x18000b8e2  mov     [rsp+0D8h+var_B0], rax
0x18000b8e7  mov     [rsp+0D8h+var_B8], 3
0x18000b8ef  xor     r9d, r9d
0x18000b8f2  xor     r8d, r8d
0x18000b8f5  lea     rdx, unk_180034E98
0x18000b8fc  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b901  call    ?get@?$static_lazy@VRdpDiagnosticsProvider@@@details@wil@@QEAAPEAVRdpDiagnosticsProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpDiagnosticsProvider>::get(void (*)(void))
0x18000b906  mov     rcx, [rax+8]
0x18000b90a  mov     eax, [rcx]
0x18000b90c  cmp     eax, 5
0x18000b90f  jbe     short loc_18000B932
0x18000b911  mov     rax, [rsp+0D8h+var_80]
0x18000b916  mov     qword ptr [rsp+0D8h+var_A8.fmtid.Data1], rax
0x18000b91b  lea     rax, [rsp+0D8h+var_A8]
0x18000b920  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18000b925  lea     rdx, byte_180034EC7
0x18000b92c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18000b931  nop
0x18000b932  lea     rcx, [rsp+0D8h+var_A8.pid]; this
0x18000b937  call    ??1JsonWriter@@QEAA@XZ; JsonWriter::~JsonWriter(void)
0x18000b93c  mov     byte ptr [rdi+0ADh], 1
0x18000b943  xor     eax, eax
0x18000b945  jmp     short loc_18000B94B
0x18000b947  mov     eax, [rsp+0D8h+var_A8.fmtid.Data1]
0x18000b94b  mov     rcx, [rsp+0D8h+var_38]
0x18000b953  xor     rcx, rsp; StackCookie
0x18000b956  call    __security_check_cookie
0x18000b95b  add     rsp, 0B0h
0x18000b962  pop     r15
0x18000b964  pop     r14
0x18000b966  pop     rdi
0x18000b967  pop     rsi
0x18000b968  pop     rbx
0x18000b969  retn
```
