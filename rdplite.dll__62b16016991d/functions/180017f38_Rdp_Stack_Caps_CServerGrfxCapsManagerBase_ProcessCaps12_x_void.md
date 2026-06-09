# Rdp::Stack::Caps::CServerGrfxCapsManagerBase::ProcessCaps12_x(void)

- ea: `0x180017f38`
- end: `0x180018049`
- name: `?ProcessCaps12_x@CServerGrfxCapsManagerBase@Caps@Stack@Rdp@@AEAAXXZ`
- size: `273`
- prototype: `void __fastcall(Rdp::Stack::Caps::CServerGrfxCapsManagerBase *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017d90`

## callees

- `0x1800036f0`
- `0x18000b0ac`
- `0x18000cea4`
- `0x18000cf28`

## string_xrefs

- `0x180017fc0`: `Failed to set PKEY_EncodingDllGuid property`

## pseudocode

```c
void __fastcall Rdp::Stack::Caps::CServerGrfxCapsManagerBase::ProcessCaps12_x(
        Rdp::Stack::Caps::CServerGrfxCapsManagerBase *this)
{
  __int64 v2; // rbx
  Rdp::Utils::Props *v3; // rcx
  const struct _GUID *v4; // r9
  unsigned int v5; // eax
  Rdp::Utils::Props *v6; // rcx
  const struct _GUID *v7; // r9
  unsigned int v8; // eax
  char *v9; // [rsp+28h] [rbp-40h]
  char *v10; // [rsp+28h] [rbp-40h]
  __int128 v11; // [rsp+30h] [rbp-38h] BYREF
  struct _tagpropertykey v12; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x8F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\servergrfxcapsmanager.cpp",
    (const char *)0x8007007ALL,
    *(_DWORD *)(*((_QWORD *)this + 1) + 4LL) < 0x20u,
    (bool)"Buffer size is too small to cast to RDPGFX_CAPSDATA_VERSION12_1",
    (const char *)v11);
  v2 = *((_QWORD *)this + 1);
  v3 = (Rdp::Utils::Props *)*((_QWORD *)this + 2);
  v11 = xmmword_1800301B8;
  v11 = *(_OWORD *)(v2 + 8);
  v5 = Rdp::Utils::Props::IPropertyStore_SetCLSID(
         v3,
         (struct IPropertyStore *)&PKEY_EncodingDllGuid,
         (const struct _tagpropertykey *)&v11,
         v4);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x9D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\servergrfxcapsmanager.cpp",
    (const char *)v5,
    (int)"Failed to set PKEY_EncodingDllGuid property",
    v9);
  v6 = (Rdp::Utils::Props *)*((_QWORD *)this + 2);
  v12.fmtid = (GUID)xmmword_1800301B8;
  v12.fmtid = *(GUID *)(v2 + 24);
  v8 = Rdp::Utils::Props::IPropertyStore_SetCLSID(v6, (struct IPropertyStore *)&PKEY_EncodingScenarioGuid, &v12, v7);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xA9,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\servergrfxcapsmanager.cpp",
    (const char *)v8,
    (int)"Failed to set PKEY_EncodingScenarioGuid property",
    v10);
}

```

## disassembly

```asm
0x180017f38  mov     [rsp+arg_8], rbx
0x180017f3d  push    rdi
0x180017f3e  sub     rsp, 60h
0x180017f42  mov     rax, cs:__security_cookie
0x180017f49  xor     rax, rsp
0x180017f4c  mov     [rsp+68h+var_18], rax
0x180017f51  mov     rax, [rcx+8]
0x180017f55  lea     rdx, aBufferSizeIsTo_8; "Buffer size is too small to cast to RDP"...
0x180017f5c  mov     [rsp+68h+var_40], rdx; char *
0x180017f61  lea     r8, aOnecoreuapTerm_0; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180017f68  mov     rdi, rcx
0x180017f6b  mov     r9d, 8007007Ah; char *
0x180017f71  mov     rcx, [rsp+68h]; this
0x180017f76  mov     edx, 8Fh; void *
0x180017f7b  cmp     dword ptr [rax+4], 20h ; ' '
0x180017f7f  setb    al
0x180017f82  mov     [rsp+68h+var_48], al; char
0x180017f86  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180017f8b  movups  xmm0, cs:xmmword_1800301B8
0x180017f92  mov     rbx, [rdi+8]
0x180017f96  lea     r8, [rsp+68h+var_38]; struct _tagpropertykey *
0x180017f9b  mov     rcx, [rdi+10h]; this
0x180017f9f  lea     rdx, PKEY_EncodingDllGuid; struct IPropertyStore *
0x180017fa6  movdqu  xmmword ptr [rsp+68h+var_38.fmtid.Data1], xmm0
0x180017fac  movups  xmm0, xmmword ptr [rbx+8]
0x180017fb0  movdqu  xmmword ptr [rsp+68h+var_38.fmtid.Data1], xmm0
0x180017fb6  call    ?IPropertyStore_SetCLSID@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetCLSID(IPropertyStore *,_tagpropertykey const &,_GUID const &)
0x180017fbb  mov     rcx, [rsp+68h]; this
0x180017fc0  lea     rdx, aFailedToSetPke_5; "Failed to set PKEY_EncodingDllGuid prop"...
0x180017fc7  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180017fcc  lea     r8, aOnecoreuapTerm_0; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180017fd3  mov     edx, 9Dh; void *
0x180017fd8  mov     r9d, eax; char *
0x180017fdb  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180017fe0  movups  xmm0, cs:xmmword_1800301B8
0x180017fe7  mov     rcx, [rdi+10h]; this
0x180017feb  lea     r8, [rsp+68h+var_38.pid]; struct _tagpropertykey *
0x180017ff0  lea     rdx, PKEY_EncodingScenarioGuid; struct IPropertyStore *
0x180017ff7  movdqu  xmmword ptr [rsp+68h+var_38.pid], xmm0
0x180017ffd  movups  xmm0, xmmword ptr [rbx+18h]
0x180018001  movdqu  xmmword ptr [rsp+68h+var_38.pid], xmm0
0x180018007  call    ?IPropertyStore_SetCLSID@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEBU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_SetCLSID(IPropertyStore *,_tagpropertykey const &,_GUID const &)
0x18001800c  mov     rcx, [rsp+68h]; this
0x180018011  lea     rdx, aFailedToSetPke_24; "Failed to set PKEY_EncodingScenarioGuid"...
0x180018018  mov     qword ptr [rsp+68h+var_48], rdx; int
0x18001801d  lea     r8, aOnecoreuapTerm_0; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180018024  mov     edx, 0A9h; void *
0x180018029  mov     r9d, eax; char *
0x18001802c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180018031  mov     rcx, [rsp+68h+var_18]
0x180018036  xor     rcx, rsp; StackCookie
0x180018039  call    __security_check_cookie
0x18001803e  mov     rbx, [rsp+68h+arg_8]
0x180018043  add     rsp, 60h
0x180018047  pop     rdi
0x180018048  retn
```
