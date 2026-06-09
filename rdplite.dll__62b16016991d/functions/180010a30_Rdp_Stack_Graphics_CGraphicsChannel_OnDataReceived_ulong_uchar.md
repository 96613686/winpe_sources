# Rdp::Stack::Graphics::CGraphicsChannel::OnDataReceived(ulong,uchar *)

- ea: `0x180010a30`
- end: `0x180010bb3`
- name: `?OnDataReceived@CGraphicsChannel@Graphics@Stack@Rdp@@EEAAJKPEAE@Z`
- size: `387`
- prototype: `__int64 __fastcall(Rdp::Stack::Graphics::CGrfxPipeline **this, unsigned int, const struct _RDPGFX_CACHE_IMPORT_OFFER_PDU *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180007b28`
- `0x18000a0e4`
- `0x18000cea4`
- `0x1800103b4`
- `0x1800106e4`
- `0x180010a30`
- `0x180011814`
- `0x180011a1c`
- `0x180011b1c`
- `0x180011fa0`
- `0x180028340`

## string_xrefs

- `0x180010b6d`: `Buffer size is too small to cast to RDPGFX_CACHE_IMPORT_OFFER_PDU`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Graphics::CGraphicsChannel::OnDataReceived(
        Rdp::Stack::Graphics::CGrfxPipeline **this,
        unsigned int a2,
        const struct _RDPGFX_CACHE_IMPORT_OFFER_PDU *a3)
{
  size_t v4; // rdi
  unsigned int v7; // ebx
  unsigned __int8 *v8; // r8
  Rdp::Stack::Graphics::CGraphicsChannel *v9; // rcx
  unsigned int v10; // r8d
  const char *v11; // r9
  Rdp::Stack::Graphics::CGraphicsChannel *v12; // rcx
  wil *v13; // rcx
  int v14; // eax
  const char *v15; // [rsp+28h] [rbp-30h]
  const char *v16; // [rsp+30h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned int v19; // [rsp+68h] [rbp+10h]
  unsigned __int64 v20; // [rsp+78h] [rbp+20h] BYREF

  v4 = a2;
  if ( a2 >= 8 )
  {
    try
    {
      v7 = 0;
      v19 = 0;
      v8 = (unsigned __int8 *)a3 + 8;
      if ( *(_WORD *)a3 == 16 )
      {
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0x39C,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
          (const char *)0x8007007ALL,
          a2 < 0x16,
          (bool)"Buffer size is too small to cast to RDPGFX_CACHE_IMPORT_OFFER_PDU",
          v16);
        Rdp::Stack::Graphics::CGraphicsChannel::ProcessCacheImportOffer(v12, a3);
      }
      else
      {
        v9 = (Rdp::Stack::Graphics::CGraphicsChannel *)(this - 10);
        if ( *(_WORD *)a3 == 18 )
        {
          v7 = Rdp::Stack::Graphics::CGraphicsChannel::DecodeCapsAdvertise(v9, a2 - 8, v8);
          v19 = v7;
        }
        else
        {
          Rdp::Stack::Graphics::CChannelPipeline::GetWriteIoBuffer(v9, &v20, v8);
          wil::details::in1diag3::Throw_HrIfMsg(
            retaddr,
            (void *)0x3AC,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
            (const char *)0x8007007ALL,
            *(_DWORD *)(v20 + 140) < (unsigned int)v4,
            (bool)"I/O buffer size if too small to hold RDPEGFX pdu",
            v16);
          memcpy_0(*(void **)(v20 + 120), a3, v4);
          if ( (unsigned __int8)Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartWrite(
                                  this + 75,
                                  (v20 + 80) & ((unsigned __int128)-(__int128)v20 >> 64)) )
          {
            v20 = 0;
          }
          else
          {
            wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
              &v16,
              v20);
            Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push((_Mtx_t)(this + 26));
          }
          wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(&v20);
        }
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x3C1, v10, v11);
      v14 = wil::ResultFromCaughtException(v13);
      Rdp::Stack::Graphics::CGrfxPipeline::Fallback(this[93], v14);
      return v19;
    }
    return v7;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x388,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
      (const char *)0x8007007ALL,
      (int)"Buffer size is too small for RDPGFX payload",
      v15);
    return 2147942522LL;
  }
}

```

## disassembly

```asm
0x180010a30  mov     [rsp+arg_10], rbx
0x180010a35  mov     [rsp+arg_0], rcx
0x180010a3a  push    rsi
0x180010a3b  push    rdi
0x180010a3c  push    r14
0x180010a3e  sub     rsp, 40h
0x180010a42  mov     rsi, r8
0x180010a45  mov     edi, edx
0x180010a47  mov     r14, rcx
0x180010a4a  cmp     edx, 8
0x180010a4d  jnb     short loc_180010A81
0x180010a4f  mov     rcx, [rsp+58h]; this
0x180010a54  lea     rax, aBufferSizeIsTo_7; "Buffer size is too small for RDPGFX pay"...
0x180010a5b  mov     qword ptr [rsp+58h+var_38], rax; int
0x180010a60  mov     r9d, 8007007Ah; char *
0x180010a66  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180010a6d  mov     edx, 388h; void *
0x180010a72  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180010a77  mov     eax, 8007007Ah
0x180010a7c  jmp     loc_180010BA5
0x180010a81  xor     ebx, ebx
0x180010a83  mov     [rsp+58h+arg_8], ebx
0x180010a87  add     r8, 8; unsigned __int8 *
0x180010a8b  lea     edx, [rdi-8]; unsigned int
0x180010a8e  cmp     word ptr [rsi], 10h
0x180010a92  jz      loc_180010B62
0x180010a98  add     rcx, 0FFFFFFFFFFFFFFB0h; this
0x180010a9c  cmp     word ptr [rsi], 12h
0x180010aa0  jz      loc_180010B55
0x180010aa6  lea     rdx, [rsp+58h+arg_18]
0x180010aab  call    ?GetWriteIoBuffer@CChannelPipeline@Graphics@Stack@Rdp@@IEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ; Rdp::Stack::Graphics::CChannelPipeline::GetWriteIoBuffer(void)
0x180010ab0  nop
0x180010ab1  mov     rax, [rsp+58h+arg_18]
0x180010ab6  cmp     [rax+8Ch], edi
0x180010abc  setb    al
0x180010abf  mov     rcx, [rsp+58h]; this
0x180010ac4  lea     rdx, aIOBufferSizeIf; "I/O buffer size if too small to hold RD"...
0x180010acb  mov     qword ptr [rsp+58h+var_30], rdx; bool
0x180010ad0  mov     [rsp+58h+var_38], al; char
0x180010ad4  mov     r9d, 8007007Ah; char *
0x180010ada  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180010ae1  mov     edx, 3ACh; void *
0x180010ae6  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180010aeb  mov     r8, rdi; Size
0x180010aee  mov     rdx, rsi; Src
0x180010af1  mov     rcx, [rsp+58h+arg_18]
0x180010af6  mov     rcx, [rcx+78h]; void *
0x180010afa  call    memcpy_0
0x180010aff  mov     rax, [rsp+58h+arg_18]
0x180010b04  lea     rcx, [rax+50h]
0x180010b08  neg     rax
0x180010b0b  sbb     rdx, rdx
0x180010b0e  and     rdx, rcx
0x180010b11  lea     rcx, [r14+258h]
0x180010b18  call    ?StartWrite@?$CFileChannel@VCCompletionPortIo@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAA_NPEAUIoBuffer@234@@Z; Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CCompletionPortIo>::StartWrite(Rdp::Stack::Driver::IoBuffer *)
0x180010b1d  test    al, al
0x180010b1f  jz      short loc_180010B28
0x180010b21  mov     [rsp+58h+arg_18], rbx
0x180010b26  jmp     short loc_180010B49
0x180010b28  mov     rdx, [rsp+58h+arg_18]
0x180010b2d  lea     rcx, [rsp+58h+var_28]
0x180010b32  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180010b37  lea     rcx, [r14+0D0h]; _Mtx_t
0x180010b3e  lea     rdx, [rsp+58h+var_28]
0x180010b43  call    ?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)
0x180010b48  nop
0x180010b49  lea     rcx, [rsp+58h+arg_18]
0x180010b4e  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180010b53  jmp     short loc_180010B9D
0x180010b55  call    ?DecodeCapsAdvertise@CGraphicsChannel@Graphics@Stack@Rdp@@AEAAJKPEAE@Z; Rdp::Stack::Graphics::CGraphicsChannel::DecodeCapsAdvertise(ulong,uchar *)
0x180010b5a  mov     ebx, eax
0x180010b5c  mov     [rsp+58h+arg_8], eax
0x180010b60  jmp     short loc_180010B9D
0x180010b62  cmp     edi, 16h
0x180010b65  setb    al
0x180010b68  mov     rcx, [rsp+58h]; this
0x180010b6d  lea     rdx, aBufferSizeIsTo_11; "Buffer size is too small to cast to RDP"...
0x180010b74  mov     qword ptr [rsp+58h+var_30], rdx; bool
0x180010b79  mov     [rsp+58h+var_38], al; char
0x180010b7d  mov     r9d, 8007007Ah; char *
0x180010b83  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180010b8a  mov     edx, 39Ch; void *
0x180010b8f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180010b94  mov     rdx, rsi; struct _RDPGFX_CACHE_IMPORT_OFFER_PDU *
0x180010b97  call    ?ProcessCacheImportOffer@CGraphicsChannel@Graphics@Stack@Rdp@@AEAAXPEBU_RDPGFX_CACHE_IMPORT_OFFER_PDU@@@Z; Rdp::Stack::Graphics::CGraphicsChannel::ProcessCacheImportOffer(_RDPGFX_CACHE_IMPORT_OFFER_PDU const *)
0x180010b9c  nop
0x180010b9d  jmp     short loc_180010BA3
0x180010b9f  mov     ebx, [rsp+58h+arg_8]
0x180010ba3  mov     eax, ebx
0x180010ba5  mov     rbx, [rsp+58h+arg_10]
0x180010baa  add     rsp, 40h
0x180010bae  pop     r14
0x180010bb0  pop     rdi
0x180010bb1  pop     rsi
0x180010bb2  retn
```
