# Rdp::Stack::Graphics::CDvcWireEncoderWithBulkCompressor::CDvcWireEncoderWithBulkCompressor(IRDPCoreVirtualChannelEx *)

- ea: `0x18000f698`
- end: `0x18000f7aa`
- name: `??0CDvcWireEncoderWithBulkCompressor@Graphics@Stack@Rdp@@QEAA@PEAUIRDPCoreVirtualChannelEx@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(Rdp::Stack::Graphics::CDvcWireEncoderWithBulkCompressor *__hidden this, struct IRDPCoreVirtualChannelEx *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f7b0`

## callees

- `0x180004154`
- `0x180007b28`
- `0x18000cf28`
- `0x18000f5d8`
- `0x180023ac0`
- `0x180026c84`
- `0x18002a010`

## string_xrefs

- `0x18000f6fe`: `CompressRdp8__CreateInstance failed`
- `0x18000f737`: `HintCoconet__CreateInstance failed`
- `0x18000f770`: `CompressXXX->Initialize failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
struct IRdpPipeCompress **__fastcall Rdp::Stack::Graphics::CDvcWireEncoderWithBulkCompressor::CDvcWireEncoderWithBulkCompressor(
        struct IRdpPipeCompress **this,
        struct IRDPCoreVirtualChannelEx *a2)
{
  unsigned int v3; // edx
  unsigned int Instance; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  const char *v8; // [rsp+28h] [rbp-10h]
  const char *v9; // [rsp+28h] [rbp-10h]
  const char *v10; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct IRdpPipeCompressHintProvider *v12; // [rsp+50h] [rbp+18h] BYREF

  Rdp::Stack::Graphics::CDvcWireEncoder::CDvcWireEncoder((Rdp::Stack::Graphics::CDvcWireEncoder *)this, a2);
  this[6] = 0;
  this[7] = 0;
  this[8] = 0;
  memset_0(this + 9, 0, 0xBB8u);
  *((_DWORD *)this + 768) = 0;
  this[385] = 0;
  Instance = CompressRdp8__CreateInstance(this + 385, v3);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xD0,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\GrfxPipeline/DvcWireEncoder.h",
    (const char *)Instance,
    (int)"CompressRdp8__CreateInstance failed",
    v8);
  v12 = 0;
  v5 = HintCoconet__CreateInstance(&v12);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xD4,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\GrfxPipeline/DvcWireEncoder.h",
    (const char *)v5,
    (int)"HintCoconet__CreateInstance failed",
    v9);
  v6 = (*(__int64 (__fastcall **)(struct IRdpPipeCompress *, struct IRdpPipeCompressHintProvider *))(*(_QWORD *)this[385] + 24LL))(
         this[385],
         v12);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xD7,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\GrfxPipeline/DvcWireEncoder.h",
    (const char *)v6,
    (int)"CompressXXX->Initialize failed",
    v10);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v12);
  return this;
}

```

## disassembly

```asm
0x18000f698  mov     [rsp+arg_8], rbx
0x18000f69d  mov     [rsp+arg_0], rcx
0x18000f6a2  push    rdi
0x18000f6a3  sub     rsp, 30h
0x18000f6a7  mov     rdi, rcx
0x18000f6aa  call    ??0CDvcWireEncoder@Graphics@Stack@Rdp@@QEAA@PEAUIRDPCoreVirtualChannelEx@@@Z; Rdp::Stack::Graphics::CDvcWireEncoder::CDvcWireEncoder(IRDPCoreVirtualChannelEx *)
0x18000f6af  nop
0x18000f6b0  mov     qword ptr [rdi+30h], 0
0x18000f6b8  mov     qword ptr [rdi+38h], 0
0x18000f6c0  mov     qword ptr [rdi+40h], 0
0x18000f6c8  lea     rcx, [rdi+48h]; void *
0x18000f6cc  xor     edx, edx; Val
0x18000f6ce  mov     r8d, 0BB8h; Size
0x18000f6d4  call    memset_0
0x18000f6d9  mov     dword ptr [rdi+0C00h], 0
0x18000f6e3  lea     rbx, [rdi+0C08h]
0x18000f6ea  mov     qword ptr [rbx], 0
0x18000f6f1  mov     rcx, rbx; struct IRdpPipeCompress **
0x18000f6f4  call    ?CompressRdp8__CreateInstance@@YAJPEAPEAVIRdpPipeCompress@@I@Z; CompressRdp8__CreateInstance(IRdpPipeCompress * *,uint)
0x18000f6f9  mov     rcx, [rsp+38h]; this
0x18000f6fe  lea     rdx, aCompressrdp8Cr; "CompressRdp8__CreateInstance failed"
0x18000f705  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000f70a  mov     r9d, eax; char *
0x18000f70d  lea     r8, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000f714  mov     edx, 0D0h; void *
0x18000f719  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000f71e  nop
0x18000f71f  mov     [rsp+38h+arg_10], 0
0x18000f728  lea     rcx, [rsp+38h+arg_10]; struct IRdpPipeCompressHintProvider **
0x18000f72d  call    ?HintCoconet__CreateInstance@@YAJPEAPEAVIRdpPipeCompressHintProvider@@@Z; HintCoconet__CreateInstance(IRdpPipeCompressHintProvider * *)
0x18000f732  mov     rcx, [rsp+38h]; this
0x18000f737  lea     rdx, aHintcoconetCre; "HintCoconet__CreateInstance failed"
0x18000f73e  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000f743  mov     r9d, eax; char *
0x18000f746  lea     r8, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000f74d  mov     edx, 0D4h; void *
0x18000f752  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000f757  mov     rcx, [rbx]
0x18000f75a  mov     rax, [rcx]
0x18000f75d  mov     rdx, [rsp+38h+arg_10]
0x18000f762  mov     rax, [rax+18h]
0x18000f766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f76b  mov     rcx, [rsp+38h]; this
0x18000f770  lea     rdx, aCompressxxxIni; "CompressXXX->Initialize failed"
0x18000f777  mov     qword ptr [rsp+38h+var_18], rdx; int
0x18000f77c  mov     r9d, eax; char *
0x18000f77f  lea     r8, aOnecoreuapTerm_8; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18000f786  mov     edx, 0D7h; void *
0x18000f78b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000f790  nop
0x18000f791  lea     rcx, [rsp+38h+arg_10]
0x18000f796  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18000f79b  nop
0x18000f79c  mov     rax, rdi
0x18000f79f  mov     rbx, [rsp+38h+arg_8]
0x18000f7a4  add     rsp, 30h
0x18000f7a8  pop     rdi
0x18000f7a9  retn
```
