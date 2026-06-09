# Rdp::Stack::Graphics::CMonitorConfigChannel::GetVirtualDesktopInfo(_RDPCFG_2DRECTANGLE &)

- ea: `0x180015dcc`
- end: `0x180015f07`
- name: `?GetVirtualDesktopInfo@CMonitorConfigChannel@Graphics@Stack@Rdp@@AEAAJAEAU_RDPCFG_2DRECTANGLE@@@Z`
- size: `315`
- prototype: `int(Rdp::Stack::Graphics::CMonitorConfigChannel *__hidden this, struct _RDPCFG_2DRECTANGLE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180016304`

## callees

- `0x18000aff0`
- `0x18000cf28`
- `0x180015dcc`
- `0x180015f10`

## string_xrefs

- `0x180015e17`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x180015e51`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x180015e8b`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x180015ec5`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Graphics::CMonitorConfigChannel::GetVirtualDesktopInfo(
        Rdp::Utils::Props **this,
        struct _RDPCFG_2DRECTANGLE *a2,
        __int64 a3,
        int *a4)
{
  unsigned int Int32; // eax
  int *v7; // r9
  unsigned int v8; // eax
  unsigned int *v9; // r9
  unsigned int UInt32; // eax
  unsigned int *v11; // r9
  unsigned int v12; // eax
  const char *v13; // r9
  unsigned int Data1; // ecx
  DWORD pid; // edx
  int v16; // r8d
  __int64 result; // rax
  const char *v18; // [rsp+28h] [rbp-20h]
  const char *v19; // [rsp+28h] [rbp-20h]
  const char *v20; // [rsp+28h] [rbp-20h]
  const char *v21; // [rsp+28h] [rbp-20h]
  struct _tagpropertykey v22; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _tagpropertykey v24; // [rsp+50h] [rbp+8h] BYREF
  int v25; // [rsp+68h] [rbp+20h] BYREF

  v22.fmtid.Data1 = 0;
  v24.fmtid.Data1 = 0;
  v24.pid = 0;
  v25 = 0;
  Int32 = Rdp::Utils::Props::IPropertyStore_GetInt32(
            this[13],
            (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_X,
            &v22,
            a4);
  try
  {
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
      (const char *)Int32,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Origin_X",
      v18);
    v8 = Rdp::Utils::Props::IPropertyStore_GetInt32(
           this[13],
           (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_Y,
           &v24,
           v7);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
      (const char *)v8,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Origin_Y",
      v19);
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               this[13],
               (struct IPropertyStore *)&PKEY_VirtualDesktop_Width,
               (const struct _tagpropertykey *)&v24.pid,
               v9);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Width",
      v20);
    v12 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
            this[13],
            (struct IPropertyStore *)&PKEY_VirtualDesktop_Height,
            (const struct _tagpropertykey *)&v25,
            v11);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x1A8,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
      (const char *)v12,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Height",
      v21);
    Data1 = v24.fmtid.Data1;
    pid = v24.pid;
    v16 = v25;
    *(_DWORD *)a2 = v22.fmtid.Data1;
    *((_DWORD *)a2 + 1) = Data1;
    *((_DWORD *)a2 + 2) = pid;
    *((_DWORD *)a2 + 3) = v16;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1B1,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180015dcc  mov     qword ptr [rsp+arg_0.fmtid.Data4], rbx
0x180015dd1  push    rdi
0x180015dd2  sub     rsp, 40h
0x180015dd6  mov     rbx, rdx
0x180015dd9  mov     rdi, rcx
0x180015ddc  xor     eax, eax
0x180015dde  mov     [rsp+48h+var_18.fmtid.Data1], eax
0x180015de2  mov     [rsp+48h+arg_0.fmtid.Data1], eax
0x180015de6  mov     [rsp+48h+arg_0.pid], eax
0x180015dea  mov     [rsp+48h+arg_18], eax
0x180015dee  lea     r8, [rsp+48h+var_18]; struct _tagpropertykey *
0x180015df3  lea     rdx, PKEY_VirtualDesktop_Origin_X; struct IPropertyStore *
0x180015dfa  mov     rcx, [rcx+68h]; this
0x180015dfe  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x180015e03  mov     rcx, [rsp+48h]; this
0x180015e08  lea     rdx, aFailedToRetrie_11; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180015e0f  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180015e14  mov     r9d, eax; char *
0x180015e17  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180015e1e  mov     edx, 193h; void *
0x180015e23  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015e28  lea     r8, [rsp+48h+arg_0]; struct _tagpropertykey *
0x180015e2d  lea     rdx, PKEY_VirtualDesktop_Origin_Y; struct IPropertyStore *
0x180015e34  mov     rcx, [rdi+68h]; this
0x180015e38  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x180015e3d  mov     rcx, [rsp+48h]; this
0x180015e42  lea     rdx, aFailedToRetrie_1; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180015e49  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180015e4e  mov     r9d, eax; char *
0x180015e51  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180015e58  mov     edx, 19Ah; void *
0x180015e5d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015e62  lea     r8, [rsp+48h+arg_0.pid]; struct _tagpropertykey *
0x180015e67  lea     rdx, PKEY_VirtualDesktop_Width; struct IPropertyStore *
0x180015e6e  mov     rcx, [rdi+68h]; this
0x180015e72  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180015e77  mov     rcx, [rsp+48h]; this
0x180015e7c  lea     rdx, aFailedToRetrie_9; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180015e83  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180015e88  mov     r9d, eax; char *
0x180015e8b  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180015e92  mov     edx, 1A1h; void *
0x180015e97  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015e9c  lea     r8, [rsp+48h+arg_18]; struct _tagpropertykey *
0x180015ea1  lea     rdx, PKEY_VirtualDesktop_Height; struct IPropertyStore *
0x180015ea8  mov     rcx, [rdi+68h]; this
0x180015eac  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180015eb1  mov     rcx, [rsp+48h]; this
0x180015eb6  lea     rdx, aFailedToRetrie_6; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180015ebd  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180015ec2  mov     r9d, eax; char *
0x180015ec5  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180015ecc  mov     edx, 1A8h; void *
0x180015ed1  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180015ed6  mov     ecx, [rsp+48h+arg_0.fmtid.Data1]
0x180015eda  mov     edx, [rsp+48h+arg_0.pid]
0x180015ede  mov     r8d, [rsp+48h+arg_18]
0x180015ee3  mov     eax, [rsp+48h+var_18.fmtid.Data1]
0x180015ee7  mov     [rbx], eax
0x180015ee9  mov     [rbx+4], ecx
0x180015eec  mov     [rbx+8], edx
0x180015eef  mov     [rbx+0Ch], r8d
0x180015ef3  xor     eax, eax
0x180015ef5  jmp     short loc_180015EFB
0x180015ef7  mov     eax, [rsp+48h+arg_0.fmtid.Data1]
0x180015efb  mov     rbx, qword ptr [rsp+48h+arg_0.fmtid.Data4]
0x180015f00  add     rsp, 40h
0x180015f04  pop     rdi
0x180015f05  retn
```
