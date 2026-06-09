# Rdp::Stack::Shim::CFrameProcessorShim::InternalCreateCpuFrameProcessor(void)

- ea: `0x1800210ec`
- end: `0x1800211d3`
- name: `?InternalCreateCpuFrameProcessor@CFrameProcessorShim@Shim@Stack@Rdp@@AEAA?AV?$com_ptr_t@UIFrameProcessor1@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ`
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
- `0x1800210ec`
- `0x18002a010`

## string_xrefs

- `0x180021139`: `Failed to create Cpu frame processor`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall Rdp::Stack::Shim::CFrameProcessorShim::InternalCreateCpuFrameProcessor(__int64 a1, _QWORD *a2)
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
  v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(v5 + 56))(v4, &v11, 0);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xC1,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
    (const char *)v6,
    (int)"Failed to create Cpu frame processor",
    v9);
  v12 = 0;
  (**v11)(v11, &GUID_08cc0257_9444_40c8_85b1_1498bd6fcdfb, &v12);
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
0x1800210ec  mov     [rsp-8+arg_8], rbx
0x1800210f1  mov     [rsp-8+arg_18], rdi
0x1800210f6  push    rbp
0x1800210f7  mov     rbp, rsp
0x1800210fa  sub     rsp, 40h
0x1800210fe  mov     rbx, rdx
0x180021101  mov     rdi, rcx
0x180021104  mov     [rbp+arg_0], 0
0x18002110c  mov     rax, [rcx+128h]
0x180021113  mov     rcx, [rax+0E0h]
0x18002111a  mov     rax, [rcx]
0x18002111d  mov     [rbp+arg_0], 0
0x180021125  xor     r8d, r8d
0x180021128  lea     rdx, [rbp+arg_0]
0x18002112c  mov     rax, [rax+38h]
0x180021130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021135  mov     rcx, [rbp+8]; this
0x180021139  lea     rdx, aFailedToCreate_2; "Failed to create Cpu frame processor"
0x180021140  mov     qword ptr [rsp+40h+var_20], rdx; int
0x180021145  mov     r9d, eax; char *
0x180021148  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18002114f  mov     edx, 0C1h; void *
0x180021154  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180021159  mov     rcx, [rbp+arg_0]
0x18002115d  mov     [rbp+arg_10], 0
0x180021165  mov     rax, [rcx]
0x180021168  lea     r8, [rbp+arg_10]
0x18002116c  lea     rdx, _GUID_08cc0257_9444_40c8_85b1_1498bd6fcdfb
0x180021173  mov     rax, [rax]
0x180021176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002117b  nop
0x18002117c  mov     rax, [rbp+arg_10]
0x180021180  test    rax, rax
0x180021183  jz      short loc_180021199
0x180021185  mov     byte ptr [rdi+13Ah], 1
0x18002118c  mov     [rbp+arg_10], 0
0x180021194  mov     [rbx], rax
0x180021197  jmp     short loc_1800211AD
0x180021199  mov     byte ptr [rdi+13Ah], 0
0x1800211a0  lea     rdx, [rbp+arg_0]
0x1800211a4  mov     rcx, rbx
0x1800211a7  call    ??$com_query@UIFrameProcessor1@Avenc@Rdp@@AEAV?$com_ptr_t@UICpuFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@wil@@YA?AV?$com_ptr_t@UIFrameProcessor1@Avenc@Rdp@@Uerr_exception_policy@wil@@@0@AEAV?$com_ptr_t@UICpuFrameProcessor@Avenc@Rdp@@Uerr_exception_policy@wil@@@0@@Z; wil::com_query<Rdp::Avenc::IFrameProcessor1,wil::com_ptr_t<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy> &>(wil::com_ptr_t<Rdp::Avenc::ICpuFrameProcessor,wil::err_exception_policy> &)
0x1800211ac  nop
0x1800211ad  lea     rcx, [rbp+arg_10]
0x1800211b1  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800211b6  nop
0x1800211b7  lea     rcx, [rbp+arg_0]
0x1800211bb  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800211c0  mov     rax, rbx
0x1800211c3  mov     rbx, [rsp+40h+arg_8]
0x1800211c8  mov     rdi, [rsp+40h+arg_18]
0x1800211cd  add     rsp, 40h
0x1800211d1  pop     rbp
0x1800211d2  retn
```
