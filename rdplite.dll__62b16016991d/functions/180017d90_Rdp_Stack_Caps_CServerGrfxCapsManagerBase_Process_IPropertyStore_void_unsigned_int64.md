# Rdp::Stack::Caps::CServerGrfxCapsManagerBase::Process(IPropertyStore *,void *,unsigned __int64)

- ea: `0x180017d90`
- end: `0x180017f32`
- name: `?Process@CServerGrfxCapsManagerBase@Caps@Stack@Rdp@@QEAAXPEAUIPropertyStore@@PEAX_K@Z`
- size: `418`
- prototype: `void __fastcall(Rdp::Stack::Caps::CServerGrfxCapsManagerBase *this, struct IPropertyStore *, void *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800103b4`

## callees

- `0x180007b28`
- `0x18000b0ac`
- `0x18000cf28`
- `0x18000db64`
- `0x180017cfc`
- `0x180017d48`
- `0x180017d90`
- `0x180017f38`
- `0x18002a010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180017e2e`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180017e2e`

## string_xrefs

- `0x180017e39`: `Failed to create property store`
- `0x180017e68`: `Failed to set PKEY_GrfxChannel_Caps_Configuration_Store property`
- `0x180017ece`: `Failed to set PKEY_EncodingDllGuid property`
- `0x180017f02`: `Failed to set PKEY_Caps_Support_Monitor_Config_Channel property`

## pseudocode

```c
void __fastcall Rdp::Stack::Caps::CServerGrfxCapsManagerBase::Process(
        Rdp::Stack::Caps::CServerGrfxCapsManagerBase *this,
        struct IPropertyStore *a2,
        void *a3,
        __int64 a4)
{
  __int64 v7; // rdi
  unsigned int v8; // eax
  unsigned int v9; // eax
  struct IPropertyStore *v10; // rdx
  struct IUnknown *v11; // r9
  unsigned int v12; // eax
  const struct _tagpropertykey *v13; // r8
  const struct _GUID *v14; // r9
  unsigned int v15; // ecx
  char v16; // di
  unsigned int v17; // eax
  unsigned int v18; // eax
  const char *v19; // [rsp+28h] [rbp-30h]
  const char *v20; // [rsp+28h] [rbp-30h]
  const char *v21; // [rsp+28h] [rbp-30h]
  const char *v22; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *ppv; // [rsp+60h] [rbp+8h] BYREF

  v7 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IPropertyStore *))a2->lpVtbl->AddRef)(a2);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = (**(__int64 (__fastcall ***)(Rdp::Stack::Caps::CServerGrfxCapsManagerBase *, void *, __int64))this)(this, a3, a4);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\servergrfxcapsmanager.cpp",
    (const char *)v8,
    (int)"Failed to parse caps advertise payload",
    v19);
  ppv = 0;
  wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(&ppv);
  v9 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x49,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\servergrfxcapsmanager.cpp",
    (const char *)v9,
    (int)"Failed to create property store",
    v20);
  v12 = Rdp::Utils::Props::IPropertyStore_SetUnknown(
          *((Rdp::Utils::Props **)this + 2),
          v10,
          (const struct _tagpropertykey *)ppv,
          v11);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x53,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\servergrfxcapsmanager.cpp",
    (const char *)v12,
    (int)"Failed to set PKEY_GrfxChannel_Caps_Configuration_Store property",
    v21);
  v15 = **((_DWORD **)this + 1);
  if ( ((v15 - 721664) & 0xFFFFFDFF) != 0 )
  {
    v16 = 0;
    if ( v15 > 0xC0100 )
    {
      v16 = 1;
      Rdp::Stack::Caps::CServerGrfxCapsManagerBase::ProcessCaps12_x(this);
    }
  }
  else
  {
    v16 = 1;
    v17 = Rdp::Utils::Props::IPropertyStore_SetCLSID(
            *((Rdp::Utils::Props **)this + 2),
            (struct IPropertyStore *)&PKEY_EncodingDllGuid,
            (const struct _tagpropertykey *)&GUID_RdpAvenc,
            v14);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\servergrfxcapsmanager.cpp",
      (const char *)v17,
      (int)"Failed to set PKEY_EncodingDllGuid property",
      v22);
  }
  LOBYTE(v13) = v16;
  v18 = Rdp::Utils::Props::IPropertyStore_SetBool(
          *((Rdp::Utils::Props **)this + 2),
          (struct IPropertyStore *)&PKEY_Caps_Support_Monitor_Config_Channel,
          v13,
          (bool)v14);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x72,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\servergrfxcapsmanager.cpp",
    (const char *)v18,
    (int)"Failed to set PKEY_Caps_Support_Monitor_Config_Channel property",
    v22);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&ppv);
}

```

## disassembly

```asm
0x180017d90  push    rbx
0x180017d92  push    rbp
0x180017d93  push    rsi
0x180017d94  push    rdi
0x180017d95  sub     rsp, 38h
0x180017d99  mov     rsi, r9
0x180017d9c  mov     rbp, r8
0x180017d9f  mov     rbx, rcx
0x180017da2  mov     rdi, [rcx+10h]
0x180017da6  mov     [rcx+10h], rdx
0x180017daa  test    rdx, rdx
0x180017dad  jz      short loc_180017DBE
0x180017daf  mov     rax, [rdx]
0x180017db2  mov     rcx, rdx
0x180017db5  mov     rax, [rax+8]
0x180017db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dbe  test    rdi, rdi
0x180017dc1  jz      short loc_180017DD3
0x180017dc3  mov     rax, [rdi]
0x180017dc6  mov     rcx, rdi
0x180017dc9  mov     rax, [rax+10h]
0x180017dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017dd2  nop
0x180017dd3  mov     rax, [rbx]
0x180017dd6  mov     r8, rsi
0x180017dd9  mov     rdx, rbp
0x180017ddc  mov     rcx, rbx
0x180017ddf  mov     rax, [rax]
0x180017de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017de7  mov     rcx, [rsp+58h]; this
0x180017dec  lea     rdx, aFailedToParseC; "Failed to parse caps advertise payload"
0x180017df3  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180017df8  mov     r9d, eax; char *
0x180017dfb  lea     rsi, aOnecoreuapTerm_0; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180017e02  mov     r8, rsi; unsigned int
0x180017e05  mov     edx, 3Fh ; '?'; void *
0x180017e0a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180017e0f  mov     [rsp+58h+ppv], 0
0x180017e18  lea     rcx, [rsp+58h+ppv]
0x180017e1d  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x180017e22  lea     rdx, [rsp+58h+ppv]; ppv
0x180017e27  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180017e2e  call    cs:__imp_PSCreateMemoryPropertyStore
0x180017e34  mov     rcx, [rsp+58h]; this
0x180017e39  lea     rdx, aFailedToCreate_5; "Failed to create property store"
0x180017e40  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180017e45  mov     r9d, eax; char *
0x180017e48  mov     r8, rsi; unsigned int
0x180017e4b  mov     edx, 49h ; 'I'; void *
0x180017e50  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180017e55  mov     r8, [rsp+58h+ppv]; struct _tagpropertykey *
0x180017e5a  mov     rcx, [rbx+10h]; this
0x180017e5e  call    ?IPropertyStore_SetUnknown@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAUIUnknown@@@Z; Rdp::Utils::Props::IPropertyStore_SetUnknown(IPropertyStore *,_tagpropertykey const &,IUnknown *)
0x180017e63  mov     rcx, [rsp+58h]; this
0x180017e68  lea     rdx, aFailedToSetPke; "Failed to set PKEY_GrfxChannel_Caps_Con"...
0x180017e6f  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180017e74  mov     r9d, eax; char *
0x180017e77  mov     r8, rsi; unsigned int
0x180017e7a  mov     edx, 53h ; 'S'; void *
0x180017e7f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180017e84  mov     rax, [rbx+8]
0x180017e88  mov     ecx, [rax]
0x180017e8a  lea     eax, [rcx-0B0300h]
0x180017e90  test    eax, 0FFFFFDFFh
0x180017e95  jz      short loc_180017EAF
0x180017e97  xor     dil, dil
0x180017e9a  cmp     ecx, 0C0100h
0x180017ea0  jbe     short loc_180017EEA
0x180017ea2  mov     dil, 1
0x180017ea5  mov     rcx, rbx; this
0x180017ea8  call    ?ProcessCaps12_x@CServerGrfxCapsManagerBase@Caps@Stack@Rdp@@AEAAXXZ; Rdp::Stack::Caps::CServerGrfxCapsManagerBase::ProcessCaps12_x(void)
0x180017ead  jmp     short loc_180017EEA
0x180017eaf  mov     dil, 1
0x180017eb2  lea     r8, GUID_RdpAvenc; struct _tagpropertykey *
0x180017eb9  lea     rdx, PKEY_EncodingDllGuid; struct IPropertyStore *
0x180017ec0  mov     rcx, [rbx+10h]; this
0x180017ec4  call    ?IPropertyStore_SetCLSID@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetCLSID(IPropertyStore *,_tagpropertykey const &,_GUID const &)
0x180017ec9  mov     rcx, [rsp+58h]; this
0x180017ece  lea     rdx, aFailedToSetPke_5; "Failed to set PKEY_EncodingDllGuid prop"...
0x180017ed5  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180017eda  mov     r9d, eax; char *
0x180017edd  mov     r8, rsi; unsigned int
0x180017ee0  mov     edx, 62h ; 'b'; void *
0x180017ee5  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180017eea  mov     r8b, dil; struct _tagpropertykey *
0x180017eed  lea     rdx, PKEY_Caps_Support_Monitor_Config_Channel; struct IPropertyStore *
0x180017ef4  mov     rcx, [rbx+10h]; this
0x180017ef8  call    ?IPropertyStore_SetBool@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@_N@Z; Rdp::Utils::Props::IPropertyStore_SetBool(IPropertyStore *,_tagpropertykey const &,bool)
0x180017efd  mov     rcx, [rsp+58h]; this
0x180017f02  lea     rdx, aFailedToSetPke_32; "Failed to set PKEY_Caps_Support_Monitor"...
0x180017f09  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180017f0e  mov     r9d, eax; char *
0x180017f11  mov     r8, rsi; unsigned int
0x180017f14  mov     edx, 72h ; 'r'; void *
0x180017f19  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180017f1e  nop
0x180017f1f  lea     rcx, [rsp+58h+ppv]
0x180017f24  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180017f29  add     rsp, 38h
0x180017f2d  pop     rdi
0x180017f2e  pop     rsi
0x180017f2f  pop     rbp
0x180017f30  pop     rbx
0x180017f31  retn
```
