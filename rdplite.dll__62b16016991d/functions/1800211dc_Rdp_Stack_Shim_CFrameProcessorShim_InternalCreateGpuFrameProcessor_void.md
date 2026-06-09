# Rdp::Stack::Shim::CFrameProcessorShim::InternalCreateGpuFrameProcessor(void)

- ea: `0x1800211dc`
- end: `0x1800212c3`
- name: `?InternalCreateGpuFrameProcessor@CFrameProcessorShim@Shim@Stack@Rdp@@AEAA?AV?$com_ptr_t@UIFrameProcessor1@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800224e4`

## callees

- `0x180007b28`
- `0x18000cf28`
- `0x18001fcc0`
- `0x1800211dc`
- `0x18002a010`

## string_xrefs

- `0x180021229`: `Failed to create Gpu frame processor`

## pseudocode

```c
_QWORD *__fastcall Rdp::Stack::Shim::CFrameProcessorShim::InternalCreateGpuFrameProcessor(__int64 a1, _QWORD *a2)
{
  __int64 *v4; // rcx
  __int64 v5; // rax
  unsigned int v6; // eax
  __int64 v7; // rax
  const char *v9; // [rsp+28h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  void (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF

  v11 = 0;
  v4 = *(__int64 **)(*(_QWORD *)(a1 + 296) + 224LL);
  v5 = *v4;
  v11 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v5 + 48))(v4, &v11, 0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x9B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
    (const char *)v6,
    (int)"Failed to create Gpu frame processor",
    v9);
  v12 = 0;
  (**v11)(v11, &GUID_8c63637c_6495_4510_857a_56ecf16a21fd, &v12);
  v7 = v12;
  if ( v12 )
  {
    *(_BYTE *)(a1 + 314) = 1;
    v12 = 0;
    *a2 = v7;
  }
  else
  {
    *(_BYTE *)(a1 + 314) = 0;
    wil::com_query<Rdp::Avenc::IFrameProcessor1,wil::com_ptr_t<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy> &>(
      a2,
      &v11);
  }
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v12);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v11);
  return a2;
}

```

## disassembly

```asm
0x1800211dc  mov     [rsp-8+arg_8], rbx
0x1800211e1  mov     [rsp-8+arg_18], rdi
0x1800211e6  push    rbp
0x1800211e7  mov     rbp, rsp
0x1800211ea  sub     rsp, 40h
0x1800211ee  mov     rbx, rdx
0x1800211f1  mov     rdi, rcx
0x1800211f4  mov     [rbp+arg_0], 0
0x1800211fc  mov     rax, [rcx+128h]
0x180021203  mov     rcx, [rax+0E0h]
0x18002120a  mov     rax, [rcx]
0x18002120d  mov     [rbp+arg_0], 0
0x180021215  xor     r8d, r8d
0x180021218  lea     rdx, [rbp+arg_0]
0x18002121c  mov     rax, [rax+30h]
0x180021220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021225  mov     rcx, [rbp+8]; this
0x180021229  lea     rdx, aFailedToCreate_1; "Failed to create Gpu frame processor"
0x180021230  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180021235  mov     r9d, eax; char *
0x180021238  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18002123f  mov     edx, 9Bh; void *
0x180021244  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180021249  mov     rcx, [rbp+arg_0]
0x18002124d  mov     [rbp+arg_10], 0
0x180021255  mov     rax, [rcx]
0x180021258  lea     r8, [rbp+arg_10]
0x18002125c  lea     rdx, _GUID_8c63637c_6495_4510_857a_56ecf16a21fd
0x180021263  mov     rax, [rax]
0x180021266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002126b  nop
0x18002126c  mov     rax, [rbp+arg_10]
0x180021270  test    rax, rax
0x180021273  jz      short loc_180021289
0x180021275  mov     byte ptr [rdi+13Ah], 1
0x18002127c  mov     [rbp+arg_10], 0
0x180021284  mov     [rbx], rax
0x180021287  jmp     short loc_18002129D
0x180021289  mov     byte ptr [rdi+13Ah], 0
0x180021290  lea     rdx, [rbp+arg_0]
0x180021294  mov     rcx, rbx
0x180021297  call    ??$com_query@UIFrameProcessor1@Avenc@Rdp@@AEAV?$com_ptr_t@UICpuFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@wil@@YA?AV?$com_ptr_t@UIFrameProcessor1@Avenc@Rdp@@Uerr_exception_policy@wil@@@0@AEAV?$com_ptr_t@UICpuFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@0@@Z; wil::com_query<Rdp::Avenc::IFrameProcessor1,wil::com_ptr_t<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy> &>(wil::com_ptr_t<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy> &)
0x18002129c  nop
0x18002129d  lea     rcx, [rbp+arg_10]
0x1800212a1  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800212a6  nop
0x1800212a7  lea     rcx, [rbp+arg_0]
0x1800212ab  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800212b0  mov     rax, rbx
0x1800212b3  mov     rbx, [rsp+40h+arg_8]
0x1800212b8  mov     rdi, [rsp+40h+arg_18]
0x1800212bd  add     rsp, 40h
0x1800212c1  pop     rbp
0x1800212c2  retn
```
