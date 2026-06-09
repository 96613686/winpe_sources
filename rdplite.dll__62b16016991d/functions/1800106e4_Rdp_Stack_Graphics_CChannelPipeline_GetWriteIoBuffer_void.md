# Rdp::Stack::Graphics::CChannelPipeline::GetWriteIoBuffer(void)

- ea: `0x1800106e4`
- end: `0x1800107b4`
- name: `?GetWriteIoBuffer@CChannelPipeline@Graphics@Stack@Rdp@@IEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010a30`
- `0x180011490`

## callees

- `0x180003714`
- `0x180007b28`
- `0x18000a0e4`
- `0x18000f908`
- `0x1800106e4`
- `0x18001174c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall Rdp::Stack::Graphics::CChannelPipeline::GetWriteIoBuffer(__int64 a1, __int64 *a2)
{
  signed __int32 v4; // esi
  __int64 v5; // rax
  __int64 v6; // rax
  Rdp::Stack::Driver::CIoBuffer *v8; // [rsp+50h] [rbp+8h] BYREF
  __int64 v9; // [rsp+60h] [rbp+18h] BYREF

  while ( 1 )
  {
    v4 = *(_DWORD *)(a1 + 524);
    v8 = (Rdp::Stack::Driver::CIoBuffer *)((-(__int64)(v4 != 0) & 0x8000000000000033uLL) + 0x7FFFFFFFFFFFFFFFLL);
    Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::PopAndWait(
      a1 + 288,
      &v9,
      (__int64)&v8);
    v5 = v9;
    if ( v9 )
      break;
    if ( v4 && v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 524), v4 - 1, v4) )
    {
      v8 = (Rdp::Stack::Driver::CIoBuffer *)operator new(0x98u);
      v6 = Rdp::Stack::Driver::CIoBuffer::CIoBuffer(v8, *(_DWORD *)(a1 + 512));
      wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
        a2,
        v6);
      goto LABEL_7;
    }
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v9);
  }
  v9 = 0;
  *a2 = v5;
LABEL_7:
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v9);
  return a2;
}

```

## disassembly

```asm
0x1800106e4  mov     [rsp+arg_8], rbx
0x1800106e9  push    rbp
0x1800106ea  push    rsi
0x1800106eb  push    rdi
0x1800106ec  sub     rsp, 30h
0x1800106f0  mov     rbx, rdx
0x1800106f3  mov     rdi, rcx
0x1800106f6  mov     esi, [rdi+20Ch]
0x1800106fc  nop
0x1800106fd  mov     eax, esi
0x1800106ff  neg     eax
0x180010701  sbb     rdx, rdx
0x180010704  mov     rax, 8000000000000033h
0x18001070e  and     rdx, rax
0x180010711  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001071b  add     rdx, rax
0x18001071e  mov     [rsp+48h+arg_0], rdx
0x180010723  lea     r8, [rsp+48h+arg_0]
0x180010728  lea     rdx, [rsp+48h+arg_10]
0x18001072d  lea     rcx, [rdi+120h]
0x180010734  call    ?PopAndWait@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@AEBUnothrow_t@9@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::PopAndWait(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::nothrow_t const &)
0x180010739  nop
0x18001073a  mov     rax, [rsp+48h+arg_10]
0x18001073f  test    rax, rax
0x180010742  jnz     short loc_18001078E
0x180010744  test    esi, esi
0x180010746  jz      short loc_180010757
0x180010748  lea     ecx, [rsi-1]
0x18001074b  mov     eax, esi
0x18001074d  lock cmpxchg [rdi+20Ch], ecx
0x180010755  jz      short loc_180010763
0x180010757  lea     rcx, [rsp+48h+arg_10]
0x18001075c  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180010761  jmp     short loc_1800106F6
0x180010763  mov     ecx, 98h; Size
0x180010768  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001076d  mov     [rsp+48h+arg_0], rax
0x180010772  mov     edx, [rdi+200h]; unsigned int
0x180010778  mov     rcx, rax; this
0x18001077b  call    ??0CIoBuffer@Driver@Stack@Rdp@@QEAA@I@Z; Rdp::Stack::Driver::CIoBuffer::CIoBuffer(uint)
0x180010780  nop
0x180010781  mov     rdx, rax
0x180010784  mov     rcx, rbx
0x180010787  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18001078c  jmp     short loc_18001079A
0x18001078e  mov     [rsp+48h+arg_10], 0
0x180010797  mov     [rbx], rax
0x18001079a  lea     rcx, [rsp+48h+arg_10]
0x18001079f  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800107a4  mov     rax, rbx
0x1800107a7  mov     rbx, [rsp+48h+arg_8]
0x1800107ac  add     rsp, 30h
0x1800107b0  pop     rdi
0x1800107b1  pop     rsi
0x1800107b2  pop     rbp
0x1800107b3  retn
```
