# Rdp::Stack::Graphics::CChannelPipeline::CreateReadIoBuffer(void)

- ea: `0x180010324`
- end: `0x1800103ac`
- name: `?CreateReadIoBuffer@CChannelPipeline@Graphics@Stack@Rdp@@IEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f39c`
- `0x180011048`
- `0x180011b5c`

## callees

- `0x180003714`
- `0x18000a0e4`
- `0x18000cea4`
- `0x18000f908`

## string_xrefs

- `0x180010348`: `Read I/O buffer pool exceeded maximum capacity`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Stack::Graphics::CChannelPipeline::CreateReadIoBuffer(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  const char *v6; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  Rdp::Stack::Driver::CIoBuffer *v8; // [rsp+58h] [rbp+10h]

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x87,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\GrfxPipeline/ChannelPipeline.h",
    (const char *)0x8007000ELL,
    *(_DWORD *)(a1 + 508) == 0,
    (bool)"Read I/O buffer pool exceeded maximum capacity",
    v6);
  --*(_DWORD *)(a1 + 508);
  v8 = (Rdp::Stack::Driver::CIoBuffer *)operator new(0x98u);
  v4 = Rdp::Stack::Driver::CIoBuffer::CIoBuffer(v8, *(_DWORD *)(a1 + 496));
  wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
    a2,
    v4);
  return a2;
}

```

## disassembly

```asm
0x180010324  mov     [rsp+arg_0], rbx
0x180010329  mov     [rsp+arg_8], rdx
0x18001032e  push    rdi
0x18001032f  sub     rsp, 40h
0x180010333  mov     rdi, rdx
0x180010336  mov     rbx, rcx
0x180010339  cmp     dword ptr [rcx+1FCh], 0
0x180010340  setz    al
0x180010343  mov     rcx, [rsp+48h]; this
0x180010348  lea     rdx, aReadIOBufferPo; "Read I/O buffer pool exceeded maximum c"...
0x18001034f  mov     qword ptr [rsp+48h+var_20], rdx; bool
0x180010354  mov     [rsp+48h+var_28], al; char
0x180010358  mov     r9d, 8007000Eh; char *
0x18001035e  lea     r8, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180010365  mov     edx, 87h; void *
0x18001036a  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001036f  dec     dword ptr [rbx+1FCh]
0x180010375  mov     ecx, 98h; Size
0x18001037a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001037f  mov     [rsp+48h+arg_8], rax
0x180010384  mov     edx, [rbx+1F0h]; unsigned int
0x18001038a  mov     rcx, rax; this
0x18001038d  call    ??0CIoBuffer@Driver@Stack@Rdp@@QEAA@I@Z; Rdp::Stack::Driver::CIoBuffer::CIoBuffer(uint)
0x180010392  nop
0x180010393  mov     rdx, rax
0x180010396  mov     rcx, rdi
0x180010399  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18001039e  mov     rax, rdi
0x1800103a1  mov     rbx, [rsp+48h+arg_0]
0x1800103a6  add     rsp, 40h
0x1800103aa  pop     rdi
0x1800103ab  retn
```
