# Rdp::Stack::Graphics::CGrfxPipeline::SerializeConfigPropertyStore(void)

- ea: `0x18000bef0`
- end: `0x18000c009`
- name: `?SerializeConfigPropertyStore@CGrfxPipeline@Graphics@Stack@Rdp@@AEAAXXZ`
- size: `281`
- prototype: `void __fastcall(struct IPropertyStore **this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000c410`

## callees

- `0x180007b28`
- `0x18000aedc`
- `0x18000b1bc`
- `0x18000cf28`
- `0x18000db64`
- `0x18002a010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000bf18`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000bf18`

## string_xrefs

- `0x18000bf23`: `Failed to create configuration property store`
- `0x18000bf5d`: `Failed to copy PKEY_ProtocolName property`
- `0x18000bf97`: `Failed to copy PKEY_ConnectionId property`
- `0x18000bfd8`: `Failed to serialize configuration property store`

## pseudocode

```c
void __fastcall Rdp::Stack::Graphics::CGrfxPipeline::SerializeConfigPropertyStore(struct IPropertyStore **this)
{
  unsigned int v2; // eax
  const struct _tagpropertykey *v3; // r9
  unsigned int v4; // eax
  const struct _tagpropertykey *v5; // r9
  unsigned int v6; // eax
  unsigned int v7; // eax
  const char *v8; // [rsp+28h] [rbp-10h]
  const char *v9; // [rsp+28h] [rbp-10h]
  const char *v10; // [rsp+28h] [rbp-10h]
  const char *v11; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *ppv; // [rsp+40h] [rbp+8h] BYREF

  ppv = 0;
  wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(&ppv);
  v2 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x22B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
    (const char *)v2,
    (int)"Failed to create configuration property store",
    v8);
  v4 = Rdp::Utils::Props::IPropertyStore_Copy(
         (Rdp::Utils::Props *)ppv,
         this[13],
         (struct IPropertyStore *)&PKEY_ProtocolName,
         v3);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x232,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
    (const char *)v4,
    (int)"Failed to copy PKEY_ProtocolName property",
    v9);
  v6 = Rdp::Utils::Props::IPropertyStore_Copy(
         (Rdp::Utils::Props *)ppv,
         this[13],
         (struct IPropertyStore *)&PKEY_ConnectionId,
         v5);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x239,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
    (const char *)v6,
    (int)"Failed to copy PKEY_ConnectionId property",
    v10);
  v7 = ((__int64 (__fastcall *)(struct IPropertyStore *, GUID *, void *))this[15]->lpVtbl->Commit)(
         this[15],
         &GUID_ConfigPropStore,
         ppv);
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x23F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\grfxpipeline.cpp",
    (const char *)v7,
    (int)"Failed to serialize configuration property store",
    v11);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&ppv);
}

```

## disassembly

```asm
0x18000bef0  push    rbx
0x18000bef2  sub     rsp, 30h
0x18000bef6  mov     rbx, rcx
0x18000bef9  mov     [rsp+38h+ppv], 0
0x18000bf02  lea     rcx, [rsp+38h+ppv]
0x18000bf07  call    ?reset@?$com_ptr_t@UIRDPCoreChannelManager@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IRDPCoreChannelManager,wil::err_exception_policy>::reset(void)
0x18000bf0c  lea     rdx, [rsp+38h+ppv]; ppv
0x18000bf11  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000bf18  call    cs:__imp_PSCreateMemoryPropertyStore
0x18000bf1e  mov     rcx, [rsp+38h]; this
0x18000bf23  lea     rdx, aFailedToCreate_3; "Failed to create configuration property"...
0x18000bf2a  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000bf2f  mov     r9d, eax; char *
0x18000bf32  lea     r8, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000bf39  mov     edx, 22Bh; void *
0x18000bf3e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000bf43  lea     r8, PKEY_ProtocolName; struct IPropertyStore *
0x18000bf4a  mov     rdx, [rbx+68h]; struct IPropertyStore *
0x18000bf4e  mov     rcx, [rsp+38h+ppv]; this
0x18000bf53  call    ?IPropertyStore_Copy@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@0AEBU_tagpropertykey@@@Z; Rdp::Utils::Props::IPropertyStore_Copy(IPropertyStore *,IPropertyStore *,_tagpropertykey const &)
0x18000bf58  mov     rcx, [rsp+38h]; this
0x18000bf5d  lea     rdx, aFailedToCopyPk; "Failed to copy PKEY_ProtocolName proper"...
0x18000bf64  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000bf69  mov     r9d, eax; char *
0x18000bf6c  lea     r8, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000bf73  mov     edx, 232h; void *
0x18000bf78  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000bf7d  lea     r8, PKEY_ConnectionId; struct IPropertyStore *
0x18000bf84  mov     rdx, [rbx+68h]; struct IPropertyStore *
0x18000bf88  mov     rcx, [rsp+38h+ppv]; this
0x18000bf8d  call    ?IPropertyStore_Copy@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@0AEBU_tagpropertykey@@@Z; Rdp::Utils::Props::IPropertyStore_Copy(IPropertyStore *,IPropertyStore *,_tagpropertykey const &)
0x18000bf92  mov     rcx, [rsp+38h]; this
0x18000bf97  lea     rdx, aFailedToCopyPk_0; "Failed to copy PKEY_ConnectionId proper"...
0x18000bf9e  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000bfa3  mov     r9d, eax; char *
0x18000bfa6  lea     r8, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000bfad  mov     edx, 239h; void *
0x18000bfb2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000bfb7  mov     rcx, [rbx+78h]
0x18000bfbb  mov     rax, [rcx]
0x18000bfbe  mov     r8, [rsp+38h+ppv]
0x18000bfc3  lea     rdx, GUID_ConfigPropStore
0x18000bfca  mov     rax, [rax+38h]
0x18000bfce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfd3  mov     rcx, [rsp+38h]; this
0x18000bfd8  lea     rdx, aFailedToSerial; "Failed to serialize configuration prope"...
0x18000bfdf  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000bfe4  mov     r9d, eax; char *
0x18000bfe7  lea     r8, aOnecoreuapTerm_5; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000bfee  mov     edx, 23Fh; void *
0x18000bff3  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000bff8  nop
0x18000bff9  lea     rcx, [rsp+38h+ppv]
0x18000bffe  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18000c003  add     rsp, 30h
0x18000c007  pop     rbx
0x18000c008  retn
```
