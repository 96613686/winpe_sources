# Rdp::Stack::Graphics::CGraphicsChannel::OnMetricsUpdate(ulong,ulong,unsigned __int64)

- ea: `0x180011490`
- end: `0x180011567`
- name: `?OnMetricsUpdate@CGraphicsChannel@Graphics@Stack@Rdp@@EEAAJKK_K@Z`
- size: `215`
- prototype: `__int64 __fastcall(Rdp::Stack::Graphics::CGraphicsChannel *__hidden this, unsigned int, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180007b28`
- `0x18000a0e4`
- `0x1800106e4`
- `0x180011490`
- `0x180011a1c`
- `0x180011cf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Stack::Graphics::CGraphicsChannel::OnMetricsUpdate(
        Rdp::Stack::Graphics::CGraphicsChannel *this,
        int a2,
        int a3,
        __int64 a4)
{
  char *v8; // rcx
  _DWORD *v9; // rax
  __int64 v10; // rcx
  const char *v11; // r9
  __int64 v13[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v15; // [rsp+50h] [rbp+8h] BYREF

  v8 = (char *)this - 80;
  v9 = (_DWORD *)((char *)this + 796);
  if ( *((_DWORD *)v8 + 218) != a2 || *v9 != a3 )
  {
    try
    {
      *((_DWORD *)this + 198) = a2;
      *v9 = a3;
      Rdp::Stack::Graphics::CChannelPipeline::GetWriteIoBuffer((__int64)v8, &v15);
      v10 = *(_QWORD *)(v15 + 120);
      *(_DWORD *)(v10 + 8) = 7;
      *(_QWORD *)v10 = 28;
      *(_DWORD *)(v10 + 12) = a2;
      *(_DWORD *)(v10 + 16) = a3;
      *(_QWORD *)(v10 + 20) = a4;
      if ( (unsigned __int8)Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartControl(
                              (char *)this + 600,
                              (v15 + 80) & ((unsigned __int128)-(__int128)(unsigned __int64)v15 >> 64)) )
      {
        v15 = 0;
      }
      else
      {
        wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
          v13,
          v15);
        Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(
          (RTL_CONDITION_VARIABLE *)this + 26,
          v13);
      }
      wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v15);
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x40E,
                             (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
                             v11);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180011490  mov     [rsp+arg_10], rbx
0x180011495  push    rsi
0x180011496  push    rdi
0x180011497  push    r14
0x180011499  sub     rsp, 30h
0x18001149d  mov     r14, r9
0x1800114a0  mov     edi, r8d
0x1800114a3  mov     esi, edx
0x1800114a5  mov     rbx, rcx
0x1800114a8  add     rcx, 0FFFFFFFFFFFFFFB0h
0x1800114ac  lea     rax, [rbx+31Ch]
0x1800114b3  cmp     [rcx+368h], edx
0x1800114b9  jnz     short loc_1800114C4
0x1800114bb  cmp     [rax], r8d
0x1800114be  jz      loc_180011550
0x1800114c4  mov     [rbx+318h], esi
0x1800114ca  mov     [rax], edi
0x1800114cc  lea     rdx, [rsp+48h+arg_0]
0x1800114d1  call    ?GetWriteIoBuffer@CChannelPipeline@Graphics@Stack@Rdp@@IEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ; Rdp::Stack::Graphics::CChannelPipeline::GetWriteIoBuffer(void)
0x1800114d6  nop
0x1800114d7  mov     rax, [rsp+48h+arg_0]
0x1800114dc  mov     rcx, [rax+78h]
0x1800114e0  mov     dword ptr [rcx+8], 7
0x1800114e7  mov     qword ptr [rcx], 1Ch
0x1800114ee  mov     [rcx+0Ch], esi
0x1800114f1  mov     [rcx+10h], edi
0x1800114f4  mov     [rcx+14h], r14
0x1800114f8  mov     rax, [rsp+48h+arg_0]
0x1800114fd  lea     rcx, [rax+50h]
0x180011501  neg     rax
0x180011504  sbb     rdx, rdx
0x180011507  and     rdx, rcx
0x18001150a  lea     rcx, [rbx+258h]
0x180011511  call    ?StartControl@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA_NPEAUIoBuffer@234@@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartControl(Rdp::Stack::Driver::IoBuffer *)
0x180011516  test    al, al
0x180011518  jz      short loc_180011525
0x18001151a  mov     [rsp+48h+arg_0], 0
0x180011523  jmp     short loc_180011546
0x180011525  mov     rdx, [rsp+48h+arg_0]
0x18001152a  lea     rcx, [rsp+48h+var_28]
0x18001152f  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180011534  lea     rcx, [rbx+0D0h]; _Mtx_t
0x18001153b  lea     rdx, [rsp+48h+var_28]
0x180011540  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x180011545  nop
0x180011546  lea     rcx, [rsp+48h+arg_0]
0x18001154b  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180011550  xor     eax, eax
0x180011552  jmp     short loc_180011558
0x180011554  mov     eax, [rsp+48h+arg_8]
0x180011558  mov     rbx, [rsp+48h+arg_10]
0x18001155d  add     rsp, 30h
0x180011561  pop     r14
0x180011563  pop     rdi
0x180011564  pop     rsi
0x180011565  retn
```
