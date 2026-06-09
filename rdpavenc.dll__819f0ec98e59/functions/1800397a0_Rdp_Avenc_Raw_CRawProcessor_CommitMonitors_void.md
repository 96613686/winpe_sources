# Rdp::Avenc::Raw::CRawProcessor::CommitMonitors(void)

- ea: `0x1800397a0`
- end: `0x180039aec`
- name: `?CommitMonitors@CRawProcessor@Raw@Avenc@Rdp@@UEAAJXZ`
- size: `844`
- prototype: `__int64 __fastcall(Rdp::Avenc::Raw::CRawProcessor *__hidden this)`
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
- `0x180026d7c`
- `0x18003968c`
- `0x1800397a0`
- `0x180039ff0`
- `0x18003aca4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180039994`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180039994`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800399ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800399ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003980c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039a8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003980c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039a8d`

## string_xrefs

- `0x1800398a7`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::Raw::CRawProcessor::CommitMonitors(Rdp::Avenc::Raw::CRawProcessor *this)
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
  bool v18; // r8
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
  int v33[4]; // [rsp+60h] [rbp-48h] BYREF
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
      &WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v24) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
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
      Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(
        *((Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)this + 23),
        0x1000u);
      Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::ResetGraphics(
        *((_QWORD *)this + 23),
        *((_DWORD *)this + 23),
        *((_DWORD *)this + 24),
        (__int64)(*(_QWORD *)&v33[2] - *(_QWORD *)v33) >> 4,
        *(__int64 *)v33);
      Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(
        *((Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)this + 23),
        0,
        v18);
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
        &WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids,
        v20);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xDC,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1800397a0  mov     [rsp+arg_8], rbx
0x1800397a5  mov     [rsp+arg_10], rsi
0x1800397aa  push    rdi
0x1800397ab  push    r12
0x1800397ad  push    r13
0x1800397af  push    r14
0x1800397b1  push    r15
0x1800397b3  sub     rsp, 80h
0x1800397ba  mov     rbx, rcx
0x1800397bd  lea     r13, WPP_GLOBAL_Control
0x1800397c4  mov     rax, cs:WPP_GLOBAL_Control
0x1800397cb  mov     dil, 1
0x1800397ce  cmp     rax, r13
0x1800397d1  jz      short loc_1800397E4
0x1800397d3  test    [rax+1Ch], dil
0x1800397d7  jz      short loc_1800397E4
0x1800397d9  cmp     byte ptr [rax+19h], 4
0x1800397dd  jb      short loc_1800397E4
0x1800397df  mov     sil, dil
0x1800397e2  jmp     short loc_1800397E7
0x1800397e4  xor     sil, sil
0x1800397e7  lea     rax, WPP_RECORDER_INITIALIZED
0x1800397ee  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800397f5  setnz   r14b
0x1800397f9  test    sil, sil
0x1800397fc  jnz     short loc_18003980C
0x1800397fe  test    r14b, r14b
0x180039801  jnz     short loc_18003980C
0x180039803  lea     r15, WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids
0x18003980a  jmp     short loc_180039843
0x18003980c  call    cs:__imp_GetCurrentThreadId
0x180039812  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180039816  lea     r15, WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids
0x18003981d  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x180039822  mov     word ptr [rsp+0A8h+var_78], 10h; char *
0x180039829  mov     rcx, cs:WPP_GLOBAL_Control
0x180039830  mov     r9, [rcx+28h]; int
0x180039834  mov     r8b, r14b; int
0x180039837  mov     dl, sil; int
0x18003983a  mov     rcx, [rcx+10h]; int
0x18003983e  call    WPP_RECORDER_AND_TRACE_SF_D
0x180039843  cmp     byte ptr [rbx+0B0h], 0
0x18003984a  setz    al
0x18003984d  mov     rcx, [rsp+0A8h]; this
0x180039855  lea     rdx, aProcessorIsNot; "Processor is not started"
0x18003985c  mov     [rsp+0A8h+var_80], rdx; int
0x180039861  mov     byte ptr [rsp+0A8h+var_88], al; int
0x180039865  mov     r9d, 8000FFFFh; char *
0x18003986b  lea     r8, aOnecoreuapTerm_42; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180039872  mov     edx, 0B5h; void *
0x180039877  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003987c  lea     r8, [rbx+54h]; struct _tagpropertykey *
0x180039880  lea     rdx, PKEY_VirtualDesktop_Origin_X; struct IPropertyStore *
0x180039887  mov     rcx, [rbx+20h]; this
0x18003988b  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x180039890  mov     rcx, [rsp+0A8h]; this
0x180039898  lea     rdx, aFailedToRetrie_18; "Failed to retrieve PKEY_VirtualDesktop_"...
0x18003989f  mov     qword ptr [rsp+0A8h+var_88], rdx; int
0x1800398a4  mov     r9d, eax; char *
0x1800398a7  lea     rsi, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800398ae  mov     r8, rsi; unsigned int
0x1800398b1  mov     edx, 10Bh; void *
0x1800398b6  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800398bb  lea     r8, [rbx+58h]; struct _tagpropertykey *
0x1800398bf  lea     rdx, PKEY_VirtualDesktop_Origin_Y; struct IPropertyStore *
0x1800398c6  mov     rcx, [rbx+20h]; this
0x1800398ca  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x1800398cf  mov     rcx, [rsp+0A8h]; this
0x1800398d7  lea     rdx, aFailedToRetrie_2; "Failed to retrieve PKEY_VirtualDesktop_"...
0x1800398de  mov     qword ptr [rsp+0A8h+var_88], rdx; int
0x1800398e3  mov     r9d, eax; char *
0x1800398e6  mov     r8, rsi; unsigned int
0x1800398e9  mov     edx, 112h; void *
0x1800398ee  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800398f3  lea     r8, [rbx+5Ch]; struct _tagpropertykey *
0x1800398f7  lea     rdx, PKEY_VirtualDesktop_Width; struct IPropertyStore *
0x1800398fe  mov     rcx, [rbx+20h]; this
0x180039902  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180039907  mov     rcx, [rsp+0A8h]; this
0x18003990f  lea     rdx, aFailedToRetrie_15; "Failed to retrieve PKEY_VirtualDesktop_"...
0x180039916  mov     qword ptr [rsp+0A8h+var_88], rdx; int
0x18003991b  mov     r9d, eax; char *
0x18003991e  mov     r8, rsi; unsigned int
0x180039921  mov     edx, 11Ch; void *
0x180039926  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003992b  lea     r8, [rbx+60h]; struct _tagpropertykey *
0x18003992f  lea     rdx, PKEY_VirtualDesktop_Height; struct IPropertyStore *
0x180039936  mov     rcx, [rbx+20h]; this
0x18003993a  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x18003993f  mov     rcx, [rsp+0A8h]; this
0x180039947  lea     rdx, aFailedToRetrie_23; "Failed to retrieve PKEY_VirtualDesktop_"...
0x18003994e  mov     qword ptr [rsp+0A8h+var_88], rdx; int
0x180039953  mov     r9d, eax; char *
0x180039956  mov     r8, rsi; unsigned int
0x180039959  mov     edx, 123h; void *
0x18003995e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180039963  cmp     qword ptr [rbx+0B8h], 0
0x18003996b  jz      loc_180039A58
0x180039971  xorps   xmm0, xmm0
0x180039974  movdqu  xmmword ptr [rsp+0A8h+var_48], xmm0
0x18003997a  mov     [rsp+0A8h+var_38], 0
0x180039983  lea     rsi, [rbx+40h]
0x180039987  mov     [rsp+0A8h+var_58], rsi
0x18003998c  mov     [rsp+0A8h+var_50], dil
0x180039991  mov     rcx, rsi; SRWLock
0x180039994  call    cs:__imp_AcquireSRWLockShared
0x18003999a  nop
0x18003999b  mov     rcx, [rbx+38h]
0x18003999f  mov     [rsp+0A8h+arg_0], rcx
0x1800399a7  mov     rax, [rsp+0A8h+var_38]
0x1800399ac  sub     rax, qword ptr [rsp+0A8h+var_48]
0x1800399b1  sar     rax, 4
0x1800399b5  cmp     rcx, rax
0x1800399b8  jbe     short loc_1800399DF
0x1800399ba  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800399c4  cmp     rcx, rax
0x1800399c7  ja      loc_180039AE5
0x1800399cd  lea     rdx, [rsp+0A8h+arg_0]
0x1800399d5  lea     rcx, [rsp+0A8h+var_48]
0x1800399da  call    ??$_Reallocate@$0A@@?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@AEAAXAEA_K@Z; std::vector<tagRECT>::_Reallocate<0>(unsigned __int64 &)
0x1800399df  mov     rdx, [rbx+30h]
0x1800399e3  lea     r9, [rsp+0A8h+var_48]
0x1800399e8  mov     r8, rdx
0x1800399eb  mov     rdx, [rdx]
0x1800399ee  lea     rcx, [rsp+0A8h+arg_0]
0x1800399f6  call    std__transform_std___Tree_iterator_std___Tree_val_std___Tree_simple_types_std__pair__GUID_const__wil__com_ptr_t_Rdp__Avenc__RdpProg__CRdpProgMonitorContext_wil__err_exception_policy__________std__back_insert_iterator_std__vector_tagRECT_std__allocator_tagRECT_______Rdp__Avenc__RdpProg__CRdpProgProcessor__CommitMonitors____12____lambda_1___
0x1800399fb  nop
0x1800399fc  mov     rcx, rsi; SRWLock
0x1800399ff  call    cs:__imp_ReleaseSRWLockShared
0x180039a05  mov     edx, 1000h; unsigned __int64
0x180039a0a  mov     rcx, [rbx+0B8h]; this
0x180039a11  call    ?AllocatePool@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(unsigned __int64)
0x180039a16  mov     r9, qword ptr [rsp+0A8h+var_48+8]
0x180039a1b  mov     rax, qword ptr [rsp+0A8h+var_48]
0x180039a20  sub     r9, rax
0x180039a23  sar     r9, 4
0x180039a27  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x180039a2c  mov     r8d, [rbx+60h]
0x180039a30  mov     edx, [rbx+5Ch]
0x180039a33  mov     rcx, [rbx+0B8h]
0x180039a3a  call    ?ResetGraphics@?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@QEAAXIIIPEAUtagRECT@@@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::ResetGraphics(uint,uint,uint,tagRECT *)
0x180039a3f  xor     edx, edx; unsigned int
0x180039a41  mov     rcx, [rbx+0B8h]; this
0x180039a48  call    ?Flush@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAXI_N@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(uint,bool)
0x180039a4d  nop
0x180039a4e  lea     rcx, [rsp+0A8h+var_48]
0x180039a53  call    ??1?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@QEAA@XZ; std::vector<tagRECT>::~vector<tagRECT>(void)
0x180039a58  mov     rax, cs:WPP_GLOBAL_Control
0x180039a5f  cmp     rax, r13
0x180039a62  jz      short loc_180039A70
0x180039a64  test    [rax+1Ch], dil
0x180039a68  jz      short loc_180039A70
0x180039a6a  cmp     byte ptr [rax+19h], 4
0x180039a6e  jnb     short loc_180039A73
0x180039a70  xor     dil, dil
0x180039a73  lea     rax, WPP_RECORDER_INITIALIZED
0x180039a7a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180039a81  setnz   bl
0x180039a84  test    dil, dil
0x180039a87  jnz     short loc_180039A8D
0x180039a89  test    bl, bl
0x180039a8b  jz      short loc_180039ABD
0x180039a8d  call    cs:__imp_GetCurrentThreadId
0x180039a93  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180039a97  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x180039a9c  mov     word ptr [rsp+0A8h+var_78], 11h; __int16
0x180039aa3  mov     rcx, cs:WPP_GLOBAL_Control
0x180039aaa  mov     r9, [rcx+28h]; int
0x180039aae  mov     r8b, bl; int
0x180039ab1  mov     dl, dil; int
0x180039ab4  mov     rcx, [rcx+10h]; int
0x180039ab8  call    WPP_RECORDER_AND_TRACE_SF_D
0x180039abd  xor     eax, eax
0x180039abf  jmp     short loc_180039AC8
0x180039ac1  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x180039ac8  lea     r11, [rsp+0A8h+var_28]
0x180039ad0  mov     rbx, [r11+38h]
0x180039ad4  mov     rsi, [r11+40h]
0x180039ad8  mov     rsp, r11
0x180039adb  pop     r15
0x180039add  pop     r14
0x180039adf  pop     r13
0x180039ae1  pop     r12
0x180039ae3  pop     rdi
0x180039ae4  retn
0x180039ae5  call    ?_Xlength@?$vector@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@CAXXZ; std::vector<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>::_Xlength(void)
```
