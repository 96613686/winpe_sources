# Rdp::Stack::Graphics::CChannelPipeline::ScheduleNextReadRequest(void)

- ea: `0x180011b5c`
- end: `0x180011c30`
- name: `?ScheduleNextReadRequest@CChannelPipeline@Graphics@Stack@Rdp@@IEAAXXZ`
- size: `212`
- prototype: `void __fastcall(Rdp::Stack::Graphics::CChannelPipeline *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010cbc`
- `0x180011c64`
- `0x180011db0`

## callees

- `0x180007b28`
- `0x18000ffa8`
- `0x180010324`
- `0x18001174c`
- `0x180011b5c`
- `0x180011ee4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Stack::Graphics::CChannelPipeline::ScheduleNextReadRequest(
        Rdp::Stack::Graphics::CChannelPipeline *this)
{
  __int64 v2; // rbx
  __int64 IoBuffer; // rax
  __int64 v4; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v6 = (-(__int64)(*((_DWORD *)this + 127) != 0) & 0x800000000000001AuLL) + 0x7FFFFFFFFFFFFFFFLL;
  Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::PopAndWait(
    (__int64)this + 88,
    &v5,
    (__int64)&v6);
  v2 = v5;
  if ( !v5 )
  {
    IoBuffer = Rdp::Stack::Graphics::CChannelPipeline::CreateReadIoBuffer((__int64)this, (__int64)&v6);
    wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::operator=(&v5, IoBuffer);
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>((__int64 *)&v6);
    v2 = v5;
  }
  v4 = *((_QWORD *)this + 61);
  *((_QWORD *)this + 61) = v4 + 1;
  *(_QWORD *)(v2 + 128) = v4;
  if ( Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartRead((__int64)this + 568) )
    v2 = 0;
  v5 = v2;
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v5);
}

```

## disassembly

```asm
0x180011b5c  mov     r11, rsp
0x180011b5f  mov     [r11+18h], rbx
0x180011b63  push    rdi
0x180011b64  sub     rsp, 20h
0x180011b68  mov     rdi, rcx
0x180011b6b  mov     eax, [rcx+1FCh]
0x180011b71  neg     eax
0x180011b73  sbb     rdx, rdx
0x180011b76  mov     rax, 800000000000001Ah
0x180011b80  and     rdx, rax
0x180011b83  mov     rax, 7FFFFFFFFFFFFFFFh
0x180011b8d  add     rdx, rax
0x180011b90  mov     [r11+10h], rdx
0x180011b94  add     rcx, 58h ; 'X'
0x180011b98  lea     r8, [r11+10h]
0x180011b9c  lea     rdx, [r11+8]
0x180011ba0  call    ?PopAndWait@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@AEBUnothrow_t@9@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::PopAndWait(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::nothrow_t const &)
0x180011ba5  nop
0x180011ba6  mov     rbx, [rsp+28h+arg_0]
0x180011bab  test    rbx, rbx
0x180011bae  jnz     short loc_180011BD9
0x180011bb0  lea     rdx, [rsp+28h+arg_8]
0x180011bb5  mov     rcx, rdi
0x180011bb8  call    ?CreateReadIoBuffer@CChannelPipeline@Graphics@Stack@Rdp@@IEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ; Rdp::Stack::Graphics::CChannelPipeline::CreateReadIoBuffer(void)
0x180011bbd  mov     rdx, rax
0x180011bc0  lea     rcx, [rsp+28h+arg_0]
0x180011bc5  call    ??4?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>::operator=(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> &&)
0x180011bca  lea     rcx, [rsp+28h+arg_8]
0x180011bcf  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180011bd4  mov     rbx, [rsp+28h+arg_0]
0x180011bd9  mov     rcx, [rdi+1E8h]
0x180011be0  lea     rax, [rcx+1]
0x180011be4  mov     [rdi+1E8h], rax
0x180011beb  mov     [rbx+80h], rcx
0x180011bf2  mov     rax, rbx
0x180011bf5  lea     rcx, [rbx+50h]
0x180011bf9  neg     rax
0x180011bfc  sbb     rdx, rdx
0x180011bff  and     rdx, rcx
0x180011c02  lea     rcx, [rdi+238h]
0x180011c09  call    ?StartRead@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA_NPEAUIoBuffer@234@@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartRead(Rdp::Stack::Driver::IoBuffer *)
0x180011c0e  xor     ecx, ecx
0x180011c10  test    al, al
0x180011c12  cmovnz  rbx, rcx
0x180011c16  mov     [rsp+28h+arg_0], rbx
0x180011c1b  lea     rcx, [rsp+28h+arg_0]
0x180011c20  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180011c25  mov     rbx, [rsp+28h+arg_10]
0x180011c2a  add     rsp, 20h
0x180011c2e  pop     rdi
0x180011c2f  retn
```
