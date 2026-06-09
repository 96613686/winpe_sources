# Rdp::Avenc::RdpProg::CRdpProgProcessor::CommitMonitors(void)

- ea: `0x180062b60`
- end: `0x180062eb0`
- name: `?CommitMonitors@CRdpProgProcessor@RdpProg@Avenc@Rdp@@UEAAJXZ`
- size: `848`
- prototype: `__int64 __fastcall(Rdp::Avenc::RdpProg::CRdpProgProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000e848`
- `0x1800126b0`
- `0x1800146bc`
- `0x180015480`
- `0x18001a810`
- `0x180021dac`
- `0x1800222d8`
- `0x180022c1c`
- `0x180022fb8`
- `0x180023ee4`
- `0x180025a10`
- `0x180026d7c`
- `0x180062b60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180062d54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180062d54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180062dbf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180062dbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062bcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062e51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062bcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062e51`

## string_xrefs

- `0x180062c67`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::RdpProg::CRdpProgProcessor::CommitMonitors(Rdp::Avenc::RdpProg::CRdpProgProcessor *this)
{
  char v2; // di
  bool v3; // si
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int *v8; // r9
  unsigned int Int32; // eax
  int *v10; // r9
  unsigned int v11; // eax
  unsigned int *v12; // r9
  unsigned int UInt32; // eax
  unsigned int *v14; // r9
  unsigned int v15; // eax
  const char *v16; // r9
  unsigned __int64 v17; // rcx
  unsigned int v18; // edx
  bool v19; // bl
  char v20; // al
  int v21; // r8d
  int v22; // edx
  __int64 result; // rax
  int v24; // [rsp+20h] [rbp-88h]
  int v25; // [rsp+20h] [rbp-88h]
  int v26; // [rsp+28h] [rbp-80h]
  char *v27; // [rsp+28h] [rbp-80h]
  char *v28; // [rsp+28h] [rbp-80h]
  char *v29; // [rsp+28h] [rbp-80h]
  char *v30; // [rsp+28h] [rbp-80h]
  int v31; // [rsp+28h] [rbp-80h]
  char *v32; // [rsp+30h] [rbp-78h]
  __int64 v33[2]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v34; // [rsp+70h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  unsigned __int64 v36; // [rsp+B0h] [rbp+8h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v24,
      v26,
      16,
      &WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v24) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v24,
      (bool)"Processor is not started",
      v32);
    Int32 = Rdp::Utils::Props::IPropertyStore_GetInt32(
              *((Rdp::Utils::Props **)this + 4),
              (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_X,
              (const struct _tagpropertykey *)((char *)this + 84),
              v8);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Int32,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Origin_X",
      v27);
    v11 = Rdp::Utils::Props::IPropertyStore_GetInt32(
            *((Rdp::Utils::Props **)this + 4),
            (struct IPropertyStore *)&PKEY_VirtualDesktop_Origin_Y,
            (const struct _tagpropertykey *)((char *)this + 88),
            v10);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)v11,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Origin_Y",
      v28);
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *((Rdp::Utils::Props **)this + 4),
               (struct IPropertyStore *)&PKEY_VirtualDesktop_Width,
               (const struct _tagpropertykey *)((char *)this + 92),
               v12);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x11C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Width property",
      v29);
    v15 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
            *((Rdp::Utils::Props **)this + 4),
            (struct IPropertyStore *)&PKEY_VirtualDesktop_Height,
            (const struct _tagpropertykey *)((char *)this + 96),
            v14);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)v15,
      (int)"Failed to retrieve PKEY_VirtualDesktop_Height property",
      v30);
    if ( *((_QWORD *)this + 23) )
    {
      *(_OWORD *)v33 = 0;
      v34 = 0;
      AcquireSRWLockShared((PSRWLOCK)this + 8);
      v17 = *((_QWORD *)this + 7);
      v36 = v17;
      if ( v17 )
      {
        if ( v17 > 0xFFFFFFFFFFFFFFFLL )
          std::vector<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>::_Xlength();
        std::vector<tagRECT>::_Reallocate<0>(v33, &v36);
      }
      std::transform_std::_Tree_iterator_std::_Tree_val_std::_Tree_simple_types_std::pair__GUID_const__wil::com_ptr_t_Rdp::Avenc::RdpProg::CRdpProgMonitorContext_wil::err_exception_policy__________std::back_insert_iterator_std::vector_tagRECT_std::allocator_tagRECT_______Rdp::Avenc::RdpProg::CRdpProgProcessor::CommitMonitors_::_12_::_lambda_1___(
        &v36,
        **((_QWORD **)this + 6),
        *((_QWORD *)this + 6),
        v33);
      ReleaseSRWLockShared((PSRWLOCK)this + 8);
      Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(
        *((Rdp::Avenc::CFcWireEncoderWithBulkUncompressed **)this + 23),
        0x1000u,
        0,
        0);
      Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::ResetGraphics(
        *((Rdp::Avenc::CFcWireEncoderWithBulkUncompressed **)this + 23),
        v33[0]);
      Rdp::Avenc::CFcWireEncoder::Flush(*((Rdp::Avenc::CFcWireEncoder **)this + 23), v18);
      std::vector<tagRECT>::~vector<tagRECT>(v33);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v19 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = GetCurrentThreadId();
      LOBYTE(v21) = v19;
      LOBYTE(v22) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        v21,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v25,
        v31,
        17,
        &WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids,
        v20);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF7,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogprocessor.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x180062b60  mov     [rsp+arg_8], rbx
0x180062b65  mov     [rsp+arg_10], rsi
0x180062b6a  push    rdi
0x180062b6b  push    r12
0x180062b6d  push    r13
0x180062b6f  push    r14
0x180062b71  push    r15
0x180062b73  sub     rsp, 80h
0x180062b7a  mov     rbx, rcx
0x180062b7d  lea     r13, WPP_GLOBAL_Control
0x180062b84  mov     rax, cs:WPP_GLOBAL_Control
0x180062b8b  mov     dil, 1
0x180062b8e  cmp     rax, r13
0x180062b91  jz      short loc_180062BA4
0x180062b93  test    [rax+1Ch], dil
0x180062b97  jz      short loc_180062BA4
0x180062b99  cmp     byte ptr [rax+19h], 4
0x180062b9d  jb      short loc_180062BA4
0x180062b9f  mov     sil, dil
0x180062ba2  jmp     short loc_180062BA7
0x180062ba4  xor     sil, sil
0x180062ba7  lea     rax, WPP_RECORDER_INITIALIZED
0x180062bae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180062bb5  setnz   r14b
0x180062bb9  test    sil, sil
0x180062bbc  jnz     short loc_180062BCC
0x180062bbe  test    r14b, r14b
0x180062bc1  jnz     short loc_180062BCC
0x180062bc3  lea     r15, WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids
0x180062bca  jmp     short loc_180062C03
0x180062bcc  call    cs:__imp_GetCurrentThreadId
0x180062bd2  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180062bd6  lea     r15, WPP_6cd37b947aa232b475ac322cdbaf3e27_Traceguids
0x180062bdd  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x180062be2  mov     word ptr [rsp+0A8h+var_78], 10h; char *
0x180062be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180062bf0  mov     r9, [rcx+28h]; int
0x180062bf4  mov     r8b, r14b; int
0x180062bf7  mov     dl, sil; int
0x180062bfa  mov     rcx, [rcx+10h]; int
0x180062bfe  call    WPP_RECORDER_AND_TRACE_SF_D
0x180062c03  cmp     byte ptr [rbx+0B0h], 0
0x180062c0a  setz    al
0x180062c0d  mov     rcx, [rsp+0A8h]; this
0x180062c15  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180062c1c  mov     [rsp+0A8h+var_80], rdx; int
0x180062c21  mov     byte ptr [rsp+0A8h+var_88], al; int
0x180062c25  mov     r9d, 8000FFFFh; char *
0x180062c2b  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180062c32  mov     edx, 0CAh; void *
0x180062c37  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180062c3c  lea     r8, [rbx+54h]; struct _tagpropertykey *
0x180062c40  lea     rdx, PKEY_VirtualDesktop_Origin_X; struct IPropertyStore *
0x180062c47  mov     rcx, [rbx+20h]; this
0x180062c4b  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x180062c50  mov     rcx, [rsp+0A8h]; this
0x180062c58  lea     rdx, aFailedToRetrie_18; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180062c5f  mov     [rsp+0A8h+var_88], rdx; int
0x180062c64  mov     r9d, eax; char *
0x180062c67  lea     rsi, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180062c6e  mov     r8, rsi; unsigned int
0x180062c71  mov     edx, 10Bh; void *
0x180062c76  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180062c7b  lea     r8, [rbx+58h]; struct _tagpropertykey *
0x180062c7f  lea     rdx, PKEY_VirtualDesktop_Origin_Y; struct IPropertyStore *
0x180062c86  mov     rcx, [rbx+20h]; this
0x180062c8a  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x180062c8f  mov     rcx, [rsp+0A8h]; this
0x180062c97  lea     rdx, aFailedToRetrie_2; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180062c9e  mov     [rsp+0A8h+var_88], rdx; int
0x180062ca3  mov     r9d, eax; char *
0x180062ca6  mov     r8, rsi; unsigned int
0x180062ca9  mov     edx, 112h; void *
0x180062cae  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180062cb3  lea     r8, [rbx+5Ch]; struct _tagpropertykey *
0x180062cb7  lea     rdx, PKEY_VirtualDesktop_Width; struct IPropertyStore *
0x180062cbe  mov     rcx, [rbx+20h]; this
0x180062cc2  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180062cc7  mov     rcx, [rsp+0A8h]; this
0x180062ccf  lea     rdx, aFailedToRetrie_15; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180062cd6  mov     [rsp+0A8h+var_88], rdx; int
0x180062cdb  mov     r9d, eax; char *
0x180062cde  mov     r8, rsi; unsigned int
0x180062ce1  mov     edx, 11Ch; void *
0x180062ce6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180062ceb  lea     r8, [rbx+60h]; struct _tagpropertykey *
0x180062cef  lea     rdx, PKEY_VirtualDesktop_Height; struct IPropertyStore *
0x180062cf6  mov     rcx, [rbx+20h]; this
0x180062cfa  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180062cff  mov     rcx, [rsp+0A8h]; this
0x180062d07  lea     rdx, aFailedToRetrie_23; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180062d0e  mov     [rsp+0A8h+var_88], rdx; int
0x180062d13  mov     r9d, eax; char *
0x180062d16  mov     r8, rsi; unsigned int
0x180062d19  mov     edx, 123h; void *
0x180062d1e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180062d23  cmp     qword ptr [rbx+0B8h], 0
0x180062d2b  jz      loc_180062E1C
0x180062d31  xorps   xmm0, xmm0
0x180062d34  movdqu  xmmword ptr [rsp+0A8h+var_48], xmm0
0x180062d3a  mov     [rsp+0A8h+var_38], 0
0x180062d43  lea     rsi, [rbx+40h]
0x180062d47  mov     [rsp+0A8h+var_58], rsi
0x180062d4c  mov     [rsp+0A8h+var_50], dil
0x180062d51  mov     rcx, rsi; SRWLock
0x180062d54  call    cs:__imp_AcquireSRWLockShared
0x180062d5a  nop
0x180062d5b  mov     rcx, [rbx+38h]
0x180062d5f  mov     [rsp+0A8h+arg_0], rcx
0x180062d67  mov     rax, [rsp+0A8h+var_38]
0x180062d6c  sub     rax, [rsp+0A8h+var_48]
0x180062d71  sar     rax, 4
0x180062d75  cmp     rcx, rax
0x180062d78  jbe     short loc_180062D9F
0x180062d7a  mov     rax, 0FFFFFFFFFFFFFFFh
0x180062d84  cmp     rcx, rax
0x180062d87  ja      loc_180062EA9
0x180062d8d  lea     rdx, [rsp+0A8h+arg_0]
0x180062d95  lea     rcx, [rsp+0A8h+var_48]
0x180062d9a  call    ??$_Reallocate@$0A@@?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@AEAAXAEA_K@Z; std::vector<tagRECT>::_Reallocate<0>(unsigned __int64 &)
0x180062d9f  mov     rdx, [rbx+30h]
0x180062da3  lea     r9, [rsp+0A8h+var_48]
0x180062da8  mov     r8, rdx
0x180062dab  mov     rdx, [rdx]
0x180062dae  lea     rcx, [rsp+0A8h+arg_0]
0x180062db6  call    std__transform_std___Tree_iterator_std___Tree_val_std___Tree_simple_types_std__pair__GUID_const__wil__com_ptr_t_Rdp__Avenc__RdpProg__CRdpProgMonitorContext_wil__err_exception_policy__________std__back_insert_iterator_std__vector_tagRECT_std__allocator_tagRECT_______Rdp__Avenc__RdpProg__CRdpProgProcessor__CommitMonitors____12____lambda_1___
0x180062dbb  nop
0x180062dbc  mov     rcx, rsi; SRWLock
0x180062dbf  call    cs:__imp_ReleaseSRWLockShared
0x180062dc5  xor     r9d, r9d; unsigned __int64
0x180062dc8  xor     r8d, r8d; unsigned int
0x180062dcb  mov     edx, 1000h; unsigned __int64
0x180062dd0  mov     rcx, [rbx+0B8h]; this
0x180062dd7  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x180062ddc  mov     r9, [rsp+0A8h+var_48+8]
0x180062de1  mov     rax, [rsp+0A8h+var_48]
0x180062de6  sub     r9, rax
0x180062de9  sar     r9, 4
0x180062ded  mov     [rsp+0A8h+var_88], rax; int
0x180062df2  mov     r8d, [rbx+60h]
0x180062df6  mov     edx, [rbx+5Ch]
0x180062df9  mov     rcx, [rbx+0B8h]; this
0x180062e00  call    ?ResetGraphics@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAXIIIPEAUtagRECT@@@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::ResetGraphics(uint,uint,uint,tagRECT *)
0x180062e05  mov     rcx, [rbx+0B8h]; this
0x180062e0c  call    ?Flush@CFcWireEncoder@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::CFcWireEncoder::Flush(uint)
0x180062e11  nop
0x180062e12  lea     rcx, [rsp+0A8h+var_48]
0x180062e17  call    ??1?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@QEAA@XZ; std::vector<tagRECT>::~vector<tagRECT>(void)
0x180062e1c  mov     rax, cs:WPP_GLOBAL_Control
0x180062e23  cmp     rax, r13
0x180062e26  jz      short loc_180062E34
0x180062e28  test    [rax+1Ch], dil
0x180062e2c  jz      short loc_180062E34
0x180062e2e  cmp     byte ptr [rax+19h], 4
0x180062e32  jnb     short loc_180062E37
0x180062e34  xor     dil, dil
0x180062e37  lea     rax, WPP_RECORDER_INITIALIZED
0x180062e3e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180062e45  setnz   bl
0x180062e48  test    dil, dil
0x180062e4b  jnz     short loc_180062E51
0x180062e4d  test    bl, bl
0x180062e4f  jz      short loc_180062E81
0x180062e51  call    cs:__imp_GetCurrentThreadId
0x180062e57  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180062e5b  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x180062e60  mov     word ptr [rsp+0A8h+var_78], 11h; __int16
0x180062e67  mov     rcx, cs:WPP_GLOBAL_Control
0x180062e6e  mov     r9, [rcx+28h]; int
0x180062e72  mov     r8b, bl; int
0x180062e75  mov     dl, dil; int
0x180062e78  mov     rcx, [rcx+10h]; int
0x180062e7c  call    WPP_RECORDER_AND_TRACE_SF_D
0x180062e81  xor     eax, eax
0x180062e83  jmp     short loc_180062E8C
0x180062e85  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x180062e8c  lea     r11, [rsp+0A8h+var_28]
0x180062e94  mov     rbx, [r11+38h]
0x180062e98  mov     rsi, [r11+40h]
0x180062e9c  mov     rsp, r11
0x180062e9f  pop     r15
0x180062ea1  pop     r14
0x180062ea3  pop     r13
0x180062ea5  pop     r12
0x180062ea7  pop     rdi
0x180062ea8  retn
0x180062ea9  call    ?_Xlength@?$vector@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@CAXXZ; std::vector<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>::_Xlength(void)
```
