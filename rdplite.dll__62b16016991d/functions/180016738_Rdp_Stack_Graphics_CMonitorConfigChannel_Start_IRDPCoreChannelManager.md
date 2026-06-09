# Rdp::Stack::Graphics::CMonitorConfigChannel::Start(IRDPCoreChannelManager *)

- ea: `0x180016738`
- end: `0x180016823`
- name: `?Start@CMonitorConfigChannel@Graphics@Stack@Rdp@@QEAAXPEAUIRDPCoreChannelManager@@@Z`
- size: `235`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CMonitorConfigChannel *__hidden this, struct IRDPCoreChannelManager *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c410`

## callees

- `0x180007b28`
- `0x18000cf28`
- `0x180015d28`
- `0x180016738`
- `0x18002a010`

## string_xrefs

- `0x180016758`: `Microsoft::Windows::RDS::MonitorConfiguration`
- `0x180016770`: `Failed to create monitor config Dvc`
- `0x18001677f`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x180016801`: `onecoreuap\termsrv\rdp_bin\win\rdplite\grfxpipeline\monitorconfigchannel.cpp`
- `0x1800167f2`: `Failed to open monitor config Dvc`

## pseudocode

```c
void __fastcall Rdp::Stack::Graphics::CMonitorConfigChannel::Start(
        Rdp::Stack::Graphics::CMonitorConfigChannel *this,
        struct IRDPCoreChannelManager *a2)
{
  __int64 v3; // rax
  unsigned int v4; // eax
  __int64 *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // eax
  const char *v9; // [rsp+28h] [rbp-10h]
  const char *v10; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v12; // [rsp+40h] [rbp+8h] BYREF
  char v13; // [rsp+48h] [rbp+10h] BYREF

  v3 = *(_QWORD *)a2;
  v12 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IRDPCoreChannelManager *, const char *, _QWORD, __int64 *))(v3 + 24))(
         a2,
         "Microsoft::Windows::RDS::MonitorConfiguration",
         0,
         &v12);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3A,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
    (const char *)v4,
    (int)"Failed to create monitor config Dvc",
    v9);
  v5 = (__int64 *)wil::com_query<IRDPCoreVirtualChannelEx,wil::com_ptr_t<IRDPCoreVirtualChannel,wil::err_exception_policy> &>(
                    &v13,
                    &v12);
  v6 = *v5;
  *v5 = 0;
  v7 = *((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = v6;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v13);
  v8 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(**((_QWORD **)this + 14) + 40LL))(
         *((_QWORD *)this + 14),
         ((unsigned __int64)this + 80) & -(__int64)(this != 0),
         0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x3F,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\monitorconfigchannel.cpp",
    (const char *)v8,
    (int)"Failed to open monitor config Dvc",
    v10);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v12);
}

```

## disassembly

```asm
0x180016738  push    rbx
0x18001673a  sub     rsp, 30h
0x18001673e  mov     r10, rdx
0x180016741  mov     rbx, rcx
0x180016744  mov     rax, [rdx]
0x180016747  mov     [rsp+38h+arg_0], 0
0x180016750  lea     r9, [rsp+38h+arg_0]
0x180016755  xor     r8d, r8d
0x180016758  lea     rdx, aMicrosoftWindo; "Microsoft::Windows::RDS::MonitorConfigu"...
0x18001675f  mov     rcx, r10
0x180016762  mov     rax, [rax+18h]
0x180016766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001676b  mov     rcx, [rsp+38h]; this
0x180016770  lea     rdx, aFailedToCreate_4; "Failed to create monitor config Dvc"
0x180016777  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18001677c  mov     r9d, eax; char *
0x18001677f  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180016786  mov     edx, 3Ah ; ':'; void *
0x18001678b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180016790  lea     rdx, [rsp+38h+arg_0]
0x180016795  lea     rcx, [rsp+38h+arg_8]
0x18001679a  call    ??$com_query@UIRDPCoreVirtualChannelEx@@AEAV?$com_ptr_t@UIRDPCoreVirtualChannel@@Uerr_exception_policy@wil@@@wil@@@wil@@YA?AV?$com_ptr_t@UIRDPCoreVirtualChannelEx@@Uerr_exception_policy@wil@@@0@AEAV?$com_ptr_t@UIRDPCoreVirtualChannel@@Uerr_exception_policy@wil@@@0@@Z; wil::com_query<IRDPCoreVirtualChannelEx,wil::com_ptr_t<IRDPCoreVirtualChannel,wil::err_exception_policy> &>(wil::com_ptr_t<IRDPCoreVirtualChannel,wil::err_exception_policy> &)
0x18001679f  mov     rdx, [rax]
0x1800167a2  mov     qword ptr [rax], 0
0x1800167a9  mov     rcx, [rbx+70h]
0x1800167ad  mov     [rbx+70h], rdx
0x1800167b1  test    rcx, rcx
0x1800167b4  jz      short loc_1800167C3
0x1800167b6  mov     rax, [rcx]
0x1800167b9  mov     rax, [rax+10h]
0x1800167bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167c2  nop
0x1800167c3  lea     rcx, [rsp+38h+arg_8]
0x1800167c8  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800167cd  mov     rcx, [rbx+70h]
0x1800167d1  mov     r9, [rcx]
0x1800167d4  lea     rax, [rbx+50h]
0x1800167d8  neg     rbx
0x1800167db  sbb     rdx, rdx
0x1800167de  and     rdx, rax
0x1800167e1  xor     r8d, r8d
0x1800167e4  mov     rax, [r9+28h]
0x1800167e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167ed  mov     rcx, [rsp+38h]; this
0x1800167f2  lea     rdx, aFailedToOpenMo; "Failed to open monitor config Dvc"
0x1800167f9  mov     qword ptr [rsp+38h+var_18], rdx; int
0x1800167fe  mov     r9d, eax; char *
0x180016801  lea     r8, aOnecoreuapTerm_22; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180016808  mov     edx, 3Fh ; '?'; void *
0x18001680d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180016812  nop
0x180016813  lea     rcx, [rsp+38h+arg_0]
0x180016818  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001681d  add     rsp, 30h
0x180016821  pop     rbx
0x180016822  retn
```
