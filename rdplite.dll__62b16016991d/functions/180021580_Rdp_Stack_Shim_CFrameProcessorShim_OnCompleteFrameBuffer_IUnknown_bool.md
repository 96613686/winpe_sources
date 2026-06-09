# Rdp::Stack::Shim::CFrameProcessorShim::OnCompleteFrameBuffer(IUnknown *,bool)

- ea: `0x180021580`
- end: `0x180021638`
- name: `?OnCompleteFrameBuffer@CFrameProcessorShim@Shim@Stack@Rdp@@EEAAJPEAUIUnknown@@_N@Z`
- size: `184`
- prototype: `__int64 __fastcall(Rdp::Stack::Shim::CFrameProcessorShim *__hidden this, struct IUnknown *, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007b28`
- `0x18001971c`
- `0x18001fd18`
- `0x180021580`
- `0x1800220b0`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Stack::Shim::CFrameProcessorShim::OnCompleteFrameBuffer(
        Rdp::Stack::Shim::CFrameProcessorShim *this,
        struct IUnknown *a2)
{
  _QWORD *v3; // rcx
  void *v4; // rdi
  void *v5; // rsi
  __int64 v6; // rdx
  Rdp::Stack::Shim::CAdapterShim *v7; // r14
  __int64 v8; // rbx
  const struct _GUID *v9; // rax
  const char *v10; // r9
  __int64 result; // rax
  __int64 (__fastcall ***v12[7])(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v14; // [rsp+70h] [rbp+8h] BYREF

  v3 = (_QWORD *)((char *)this + 56);
  try
  {
    Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::ReleaseFrame(v3, v12, (__int64)a2);
    wil::com_query<Rdp::Avenc::IGpuFence,wil::com_ptr_t<IUnknown,wil::err_exception_policy> &>(&v14, v12);
    v4 = v12[1];
    v5 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
    if ( *((_BYTE *)this + 224) )
    {
      v6 = *((_QWORD *)this + 26);
      v7 = *(Rdp::Stack::Shim::CAdapterShim **)(v6 + 232);
      v8 = *((_QWORD *)this + 25);
      v9 = (const struct _GUID *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 240) + 40LL))(*(_QWORD *)(v6 + 240));
      Rdp::Stack::Shim::CAdapterShim::OnReleaseResource(v7, v9, v8, v4, v5);
    }
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v14);
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>((__int64 *)v12);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x259,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\encodingshim\\frameprocessorshim.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x180021580  push    rbx
0x180021582  push    rsi
0x180021583  push    rdi
0x180021584  push    r14
0x180021586  sub     rsp, 48h
0x18002158a  mov     rbx, rcx
0x18002158d  add     rcx, 38h ; '8'
0x180021591  mov     r8, rdx
0x180021594  lea     rdx, [rsp+68h+var_38]
0x180021599  call    ?ReleaseFrame@AsyncFrameBufferPool@CFrameProcessorShim@Shim@Stack@Rdp@@QEAA?AU?$pair@V?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@PEAX@std@@PEAUIUnknown@@@Z; Rdp::Stack::Shim::CFrameProcessorShim::AsyncFrameBufferPool::ReleaseFrame(IUnknown *)
0x18002159e  nop
0x18002159f  lea     rdx, [rsp+68h+var_38]
0x1800215a4  lea     rcx, [rsp+68h+arg_0]
0x1800215a9  call    ??$com_query@UIGpuFence@Avenc@Rdp@@AEAV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@@wil@@YA?AV?$com_ptr_t@UIGpuFence@Avenc@Rdp@@Uerr_exception_policy@wil@@@0@AEAV?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@0@@Z; wil::com_query<Rdp::Avenc::IGpuFence,wil::com_ptr_t<IUnknown,wil::err_exception_policy> &>(wil::com_ptr_t<IUnknown,wil::err_exception_policy> &)
0x1800215ae  nop
0x1800215af  mov     rdi, [rsp+68h+var_30]
0x1800215b4  mov     rcx, [rsp+68h+arg_0]
0x1800215b9  mov     rax, [rcx]
0x1800215bc  mov     rax, [rax+18h]
0x1800215c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215c5  mov     rsi, rax
0x1800215c8  cmp     byte ptr [rbx+0E0h], 0
0x1800215cf  jz      short loc_180021610
0x1800215d1  mov     rdx, [rbx+0D0h]
0x1800215d8  mov     r14, [rdx+0E8h]
0x1800215df  mov     rbx, [rbx+0C8h]
0x1800215e6  mov     rcx, [rdx+0F0h]
0x1800215ed  mov     rdx, [rcx]
0x1800215f0  mov     rax, [rdx+28h]
0x1800215f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215f9  mov     [rsp+68h+var_48], rsi; void *
0x1800215fe  mov     r9, rdi; void *
0x180021601  mov     r8, rbx; unsigned __int64
0x180021604  mov     rdx, rax; struct _GUID *
0x180021607  mov     rcx, r14; this
0x18002160a  call    ?OnReleaseResource@CAdapterShim@Shim@Stack@Rdp@@QEAAXAEBU_GUID@@_KPEAX2@Z; Rdp::Stack::Shim::CAdapterShim::OnReleaseResource(_GUID const &,unsigned __int64,void *,void *)
0x18002160f  nop
0x180021610  lea     rcx, [rsp+68h+arg_0]
0x180021615  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18002161a  nop
0x18002161b  lea     rcx, [rsp+68h+var_38]
0x180021620  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180021625  xor     eax, eax
0x180021627  jmp     short loc_18002162D
0x180021629  mov     eax, dword ptr [rsp+68h+arg_0]
0x18002162d  add     rsp, 48h
0x180021631  pop     r14
0x180021633  pop     rdi
0x180021634  pop     rsi
0x180021635  pop     rbx
0x180021636  retn
```
