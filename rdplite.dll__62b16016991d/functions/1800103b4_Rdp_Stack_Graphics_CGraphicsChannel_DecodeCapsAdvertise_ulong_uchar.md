# Rdp::Stack::Graphics::CGraphicsChannel::DecodeCapsAdvertise(ulong,uchar *)

- ea: `0x1800103b4`
- end: `0x18001055e`
- name: `?DecodeCapsAdvertise@CGraphicsChannel@Graphics@Stack@Rdp@@AEAAJKPEAE@Z`
- size: `426`
- prototype: `__int64 __fastcall(Rdp::Stack::Graphics::CGraphicsChannel *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180010a30`

## callees

- `0x18000cea4`
- `0x18000cf28`
- `0x18000edbc`
- `0x1800103b4`
- `0x180010564`
- `0x180010694`
- `0x180012934`
- `0x180017d90`

## string_xrefs

- `0x1800104e5`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`

## pseudocode

```c
__int64 __fastcall Rdp::Stack::Graphics::CGraphicsChannel::DecodeCapsAdvertise(
        Rdp::Stack::Graphics::CGraphicsChannel *this,
        unsigned int a2,
        unsigned __int8 *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rax
  __int64 v8; // r9
  __int64 v9; // r14
  _QWORD *v10; // rcx
  __int64 v11; // rsi
  _DWORD *v12; // rdi
  __int64 v13; // rdx
  unsigned int Confirm; // eax
  const char *v15; // r9
  __int64 result; // rax
  char *v17; // [rsp+28h] [rbp-30h]
  const char *v18; // [rsp+30h] [rbp-28h]
  __int64 v19; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v21; // [rsp+78h] [rbp+20h] BYREF

  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x42F,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
      (const char *)0x8007007ALL,
      a2 < 0xB,
      (bool)"Buffer size is too small for RDPGFX_CAPS_ADVERTISE payload",
      v18);
    Rdp::Stack::Caps::CServerGrfxCapsManagerBase::Process(
      (Rdp::Stack::Graphics::CGraphicsChannel *)((char *)this + 840),
      *((struct IPropertyStore **)this + 102),
      a3 + 2,
      a2 - 2);
    v6 = 0;
    v21 = 0;
    v7 = *((_QWORD *)this + 106);
    if ( v7 )
    {
      v6 = (unsigned int)(*(_DWORD *)(v7 + 4) + 8);
      v21 = v6;
      v8 = 0;
    }
    else
    {
      v8 = 2147549183LL;
    }
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x445,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
      (const char *)v8,
      (int)"Failed to get caps confirm size",
      v17);
    v9 = *((_QWORD *)this + 108);
    std::vector<unsigned char>::reserve(v9 + 8, (v6 + 4095) & 0xFFFFFFFFFFFFF000uLL);
    *(_QWORD *)(v9 + 40) = (v6 + 4095) & 0xFFFFFFFFFFFFF000uLL;
    *(_QWORD *)(v9 + 32) = 0;
    v10 = (_QWORD *)*((_QWORD *)this + 108);
    v11 = (unsigned int)(v6 + 8);
    v12 = 0;
    v13 = v10[4];
    if ( v10[5] - v13 >= (unsigned __int64)(unsigned int)v11 )
    {
      v12 = (_DWORD *)(v13 + v10[1]);
      v10[4] = v11 + v13;
    }
    LODWORD(v19) = v11;
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      (_DWORD)retaddr,
      585,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      -2147024882,
      (__int64)v12);
    *v12 = 19;
    v12[1] = v11;
    Confirm = CCapsServerImpl<Rdp::Stack::Caps::CServerGrfxCapsManagerBase>::GetConfirm(
                (char *)this + 840,
                v12 + 2,
                &v21);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x44D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
      (const char *)Confirm,
      (int)"Failed to prepare caps confirm payload",
      "Unable to ensure RDPGFX_CAPS_CONFIRM_PDU %d bytes",
      v19);
    Rdp::Stack::Graphics::CDvcWireEncoderWithBulkCompressor::Flush(*((Rdp::Stack::Graphics::CDvcWireEncoderWithBulkCompressor **)this
                                                                   + 108));
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x453,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdplite\\grfxpipeline\\channelpipeline.cpp",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x1800103b4  mov     [rsp+arg_0], rbx
0x1800103b9  mov     [rsp+arg_10], rsi
0x1800103be  push    rdi
0x1800103bf  push    r14
0x1800103c1  push    r15
0x1800103c3  sub     rsp, 40h
0x1800103c7  mov     rsi, r8
0x1800103ca  mov     edi, edx
0x1800103cc  mov     rbx, rcx
0x1800103cf  cmp     edx, 0Bh
0x1800103d2  setb    al
0x1800103d5  mov     rcx, [rsp+58h]; this
0x1800103da  lea     rdx, aBufferSizeIsTo_1; "Buffer size is too small for RDPGFX_CAP"...
0x1800103e1  mov     [rsp+58h+var_30], rdx; char *
0x1800103e6  mov     [rsp+58h+var_38], al; char
0x1800103ea  mov     r9d, 8007007Ah; char *
0x1800103f0  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x1800103f7  mov     edx, 42Fh; void *
0x1800103fc  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180010401  lea     r15, [rbx+348h]
0x180010408  lea     r9d, [rdi-2]; unsigned __int64
0x18001040c  lea     r8, [rsi+2]; void *
0x180010410  mov     rdx, [rbx+330h]; struct IPropertyStore *
0x180010417  mov     rcx, r15; this
0x18001041a  call    ?Process@CServerGrfxCapsManagerBase@Caps@Stack@Rdp@@QEAAXPEAUIPropertyStore@@PEAX_K@Z; Rdp::Stack::Caps::CServerGrfxCapsManagerBase::Process(IPropertyStore *,void *,unsigned __int64)
0x18001041f  xor     edi, edi
0x180010421  mov     [rsp+58h+arg_18], rdi
0x180010426  mov     rax, [rbx+350h]
0x18001042d  test    rax, rax
0x180010430  jnz     short loc_18001043A
0x180010432  mov     r9d, 8000FFFFh
0x180010438  jmp     short loc_180010448
0x18001043a  mov     edi, [rax+4]
0x18001043d  add     edi, 8
0x180010440  mov     [rsp+58h+arg_18], rdi
0x180010445  xor     r9d, r9d; char *
0x180010448  mov     rcx, [rsp+58h]; this
0x18001044d  lea     rax, aFailedToGetCap; "Failed to get caps confirm size"
0x180010454  mov     qword ptr [rsp+58h+var_38], rax; int
0x180010459  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x180010460  mov     edx, 445h; void *
0x180010465  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001046a  mov     r14, [rbx+360h]
0x180010471  lea     rsi, [rdi+0FFFh]
0x180010478  and     rsi, 0FFFFFFFFFFFFF000h
0x18001047f  lea     rcx, [r14+8]
0x180010483  mov     rdx, rsi
0x180010486  call    ?reserve@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::reserve(unsigned __int64)
0x18001048b  mov     [r14+28h], rsi
0x18001048f  mov     qword ptr [r14+20h], 0
0x180010497  mov     rcx, [rbx+360h]
0x18001049e  lea     esi, [rdi+8]
0x1800104a1  xor     edi, edi
0x1800104a3  mov     rdx, [rcx+20h]
0x1800104a7  mov     r8d, esi
0x1800104aa  mov     rax, [rcx+28h]
0x1800104ae  sub     rax, rdx
0x1800104b1  cmp     rax, r8
0x1800104b4  jb      short loc_1800104C5
0x1800104b6  mov     rdi, [rcx+8]
0x1800104ba  add     rdi, rdx
0x1800104bd  lea     rax, [rsi+rdx]
0x1800104c1  mov     [rcx+20h], rax
0x1800104c5  mov     rcx, [rsp+58h]
0x1800104ca  mov     [rsp+58h+var_28], esi
0x1800104ce  lea     rax, aUnableToEnsure_1; "Unable to ensure RDPGFX_CAPS_CONFIRM_PD"...
0x1800104d5  mov     [rsp+58h+var_30], rax; char *
0x1800104da  mov     qword ptr [rsp+58h+var_38], rdi
0x1800104df  mov     r9d, 8007000Eh
0x1800104e5  lea     r8, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x1800104ec  mov     edx, 249h
0x1800104f1  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x1800104f6  mov     dword ptr [rdi], 13h
0x1800104fc  mov     [rdi+4], esi
0x1800104ff  lea     rdx, [rdi+8]
0x180010503  lea     r8, [rsp+58h+arg_18]
0x180010508  mov     rcx, r15
0x18001050b  call    ?GetConfirm@?$CCapsServerImpl@VCServerGrfxCapsManagerBase@Caps@Stack@Rdp@@@@QEAAJPEAXPEA_K@Z; CCapsServerImpl<Rdp::Stack::Caps::CServerGrfxCapsManagerBase>::GetConfirm(void *,unsigned __int64 *)
0x180010510  mov     rcx, [rsp+58h]; this
0x180010515  lea     rdx, aFailedToPrepar; "Failed to prepare caps confirm payload"
0x18001051c  mov     qword ptr [rsp+58h+var_38], rdx; int
0x180010521  mov     r9d, eax; char *
0x180010524  lea     r8, aOnecoreuapTerm_12; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpl"...
0x18001052b  mov     edx, 44Dh; void *
0x180010530  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180010535  mov     rcx, [rbx+360h]; this
0x18001053c  call    ?Flush@CDvcWireEncoderWithBulkCompressor@Graphics@Stack@Rdp@@QEAAXXZ; Rdp::Stack::Graphics::CDvcWireEncoderWithBulkCompressor::Flush(void)
0x180010541  xor     eax, eax
0x180010543  jmp     short loc_180010549
0x180010545  mov     eax, [rsp+58h+arg_8]
0x180010549  mov     rbx, [rsp+58h+arg_0]
0x18001054e  mov     rsi, [rsp+58h+arg_10]
0x180010553  add     rsp, 40h
0x180010557  pop     r15
0x180010559  pop     r14
0x18001055b  pop     rdi
0x18001055c  retn
```
