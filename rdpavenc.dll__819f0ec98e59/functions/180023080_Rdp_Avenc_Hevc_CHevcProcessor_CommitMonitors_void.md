# Rdp::Avenc::Hevc::CHevcProcessor::CommitMonitors(void)

- ea: `0x180023080`
- end: `0x1800233d0`
- name: `?CommitMonitors@CHevcProcessor@Hevc@Avenc@Rdp@@UEAAJXZ`
- size: `848`
- prototype: `__int64 __fastcall(Rdp::Avenc::Hevc::CHevcProcessor *__hidden this)`
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
- `0x180023080`
- `0x180023ee4`
- `0x180025a10`
- `0x180026d7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023274`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180023274`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800232df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800232df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800230ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023371`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800230ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023371`

## string_xrefs

- `0x180023187`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::Hevc::CHevcProcessor::CommitMonitors(Rdp::Avenc::Hevc::CHevcProcessor *this)
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
      &WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v24) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
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
        &WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids,
        v20);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x112,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x180023080  mov     [rsp+arg_8], rbx
0x180023085  mov     [rsp+arg_10], rsi
0x18002308a  push    rdi
0x18002308b  push    r12
0x18002308d  push    r13
0x18002308f  push    r14
0x180023091  push    r15
0x180023093  sub     rsp, 80h
0x18002309a  mov     rbx, rcx
0x18002309d  lea     r13, WPP_GLOBAL_Control
0x1800230a4  mov     rax, cs:WPP_GLOBAL_Control
0x1800230ab  mov     dil, 1
0x1800230ae  cmp     rax, r13
0x1800230b1  jz      short loc_1800230C4
0x1800230b3  test    [rax+1Ch], dil
0x1800230b7  jz      short loc_1800230C4
0x1800230b9  cmp     byte ptr [rax+19h], 4
0x1800230bd  jb      short loc_1800230C4
0x1800230bf  mov     sil, dil
0x1800230c2  jmp     short loc_1800230C7
0x1800230c4  xor     sil, sil
0x1800230c7  lea     rax, WPP_RECORDER_INITIALIZED
0x1800230ce  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800230d5  setnz   r14b
0x1800230d9  test    sil, sil
0x1800230dc  jnz     short loc_1800230EC
0x1800230de  test    r14b, r14b
0x1800230e1  jnz     short loc_1800230EC
0x1800230e3  lea     r15, WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids
0x1800230ea  jmp     short loc_180023123
0x1800230ec  call    cs:__imp_GetCurrentThreadId
0x1800230f2  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x1800230f6  lea     r15, WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids
0x1800230fd  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x180023102  mov     word ptr [rsp+0A8h+var_78], 10h; char *
0x180023109  mov     rcx, cs:WPP_GLOBAL_Control
0x180023110  mov     r9, [rcx+28h]; int
0x180023114  mov     r8b, r14b; int
0x180023117  mov     dl, sil; int
0x18002311a  mov     rcx, [rcx+10h]; int
0x18002311e  call    WPP_RECORDER_AND_TRACE_SF_D
0x180023123  cmp     byte ptr [rbx+0B0h], 0
0x18002312a  setz    al
0x18002312d  mov     rcx, [rsp+0A8h]; this
0x180023135  lea     rdx, aProcessorIsNot; "Processor is not started"
0x18002313c  mov     [rsp+0A8h+var_80], rdx; int
0x180023141  mov     byte ptr [rsp+0A8h+var_88], al; int
0x180023145  mov     r9d, 8000FFFFh; char *
0x18002314b  lea     r8, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180023152  mov     edx, 0E5h; void *
0x180023157  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002315c  lea     r8, [rbx+54h]; struct _tagpropertykey *
0x180023160  lea     rdx, PKEY_VirtualDesktop_Origin_X; struct IPropertyStore *
0x180023167  mov     rcx, [rbx+20h]; this
0x18002316b  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x180023170  mov     rcx, [rsp+0A8h]; this
0x180023178  lea     rdx, aFailedToRetrie_18; "Failed to retrieve PKEY_VirtualDesktop_"...
0x18002317f  mov     [rsp+0A8h+var_88], rdx; int
0x180023184  mov     r9d, eax; char *
0x180023187  lea     rsi, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002318e  mov     r8, rsi; unsigned int
0x180023191  mov     edx, 10Bh; void *
0x180023196  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002319b  lea     r8, [rbx+58h]; struct _tagpropertykey *
0x18002319f  lea     rdx, PKEY_VirtualDesktop_Origin_Y; struct IPropertyStore *
0x1800231a6  mov     rcx, [rbx+20h]; this
0x1800231aa  call    ?IPropertyStore_GetInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAH@Z; Rdp::Utils::Props::IPropertyStore_GetInt32(IPropertyStore *,_tagpropertykey const &,int *)
0x1800231af  mov     rcx, [rsp+0A8h]; this
0x1800231b7  lea     rdx, aFailedToRetrie_2; "Failed to retrieve PKEY_VirtualDesktop_"...
0x1800231be  mov     [rsp+0A8h+var_88], rdx; int
0x1800231c3  mov     r9d, eax; char *
0x1800231c6  mov     r8, rsi; unsigned int
0x1800231c9  mov     edx, 112h; void *
0x1800231ce  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800231d3  lea     r8, [rbx+5Ch]; struct _tagpropertykey *
0x1800231d7  lea     rdx, PKEY_VirtualDesktop_Width; struct IPropertyStore *
0x1800231de  mov     rcx, [rbx+20h]; this
0x1800231e2  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x1800231e7  mov     rcx, [rsp+0A8h]; this
0x1800231ef  lea     rdx, aFailedToRetrie_15; "Failed to retrieve PKEY_VirtualDesktop_"...
0x1800231f6  mov     [rsp+0A8h+var_88], rdx; int
0x1800231fb  mov     r9d, eax; char *
0x1800231fe  mov     r8, rsi; unsigned int
0x180023201  mov     edx, 11Ch; void *
0x180023206  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002320b  lea     r8, [rbx+60h]; struct _tagpropertykey *
0x18002320f  lea     rdx, PKEY_VirtualDesktop_Height; struct IPropertyStore *
0x180023216  mov     rcx, [rbx+20h]; this
0x18002321a  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x18002321f  mov     rcx, [rsp+0A8h]; this
0x180023227  lea     rdx, aFailedToRetrie_23; "Failed to retrieve PKEY_VirtualDesktop_"...
0x18002322e  mov     [rsp+0A8h+var_88], rdx; int
0x180023233  mov     r9d, eax; char *
0x180023236  mov     r8, rsi; unsigned int
0x180023239  mov     edx, 123h; void *
0x18002323e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180023243  cmp     qword ptr [rbx+0B8h], 0
0x18002324b  jz      loc_18002333C
0x180023251  xorps   xmm0, xmm0
0x180023254  movdqu  xmmword ptr [rsp+0A8h+var_48], xmm0
0x18002325a  mov     [rsp+0A8h+var_38], 0
0x180023263  lea     rsi, [rbx+40h]
0x180023267  mov     [rsp+0A8h+var_58], rsi
0x18002326c  mov     [rsp+0A8h+var_50], dil
0x180023271  mov     rcx, rsi; SRWLock
0x180023274  call    cs:__imp_AcquireSRWLockShared
0x18002327a  nop
0x18002327b  mov     rcx, [rbx+38h]
0x18002327f  mov     [rsp+0A8h+arg_0], rcx
0x180023287  mov     rax, [rsp+0A8h+var_38]
0x18002328c  sub     rax, [rsp+0A8h+var_48]
0x180023291  sar     rax, 4
0x180023295  cmp     rcx, rax
0x180023298  jbe     short loc_1800232BF
0x18002329a  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800232a4  cmp     rcx, rax
0x1800232a7  ja      loc_1800233C9
0x1800232ad  lea     rdx, [rsp+0A8h+arg_0]
0x1800232b5  lea     rcx, [rsp+0A8h+var_48]
0x1800232ba  call    ??$_Reallocate@$0A@@?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@AEAAXAEA_K@Z; std::vector<tagRECT>::_Reallocate<0>(unsigned __int64 &)
0x1800232bf  mov     rdx, [rbx+30h]
0x1800232c3  lea     r9, [rsp+0A8h+var_48]
0x1800232c8  mov     r8, rdx
0x1800232cb  mov     rdx, [rdx]
0x1800232ce  lea     rcx, [rsp+0A8h+arg_0]
0x1800232d6  call    std__transform_std___Tree_iterator_std___Tree_val_std___Tree_simple_types_std__pair__GUID_const__wil__com_ptr_t_Rdp__Avenc__RdpProg__CRdpProgMonitorContext_wil__err_exception_policy__________std__back_insert_iterator_std__vector_tagRECT_std__allocator_tagRECT_______Rdp__Avenc__RdpProg__CRdpProgProcessor__CommitMonitors____12____lambda_1___
0x1800232db  nop
0x1800232dc  mov     rcx, rsi; SRWLock
0x1800232df  call    cs:__imp_ReleaseSRWLockShared
0x1800232e5  xor     r9d, r9d; unsigned __int64
0x1800232e8  xor     r8d, r8d; unsigned int
0x1800232eb  mov     edx, 1000h; unsigned __int64
0x1800232f0  mov     rcx, [rbx+0B8h]; this
0x1800232f7  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x1800232fc  mov     r9, [rsp+0A8h+var_48+8]
0x180023301  mov     rax, [rsp+0A8h+var_48]
0x180023306  sub     r9, rax
0x180023309  sar     r9, 4
0x18002330d  mov     [rsp+0A8h+var_88], rax; int
0x180023312  mov     r8d, [rbx+60h]
0x180023316  mov     edx, [rbx+5Ch]
0x180023319  mov     rcx, [rbx+0B8h]; this
0x180023320  call    ?ResetGraphics@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAXIIIPEAUtagRECT@@@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::ResetGraphics(uint,uint,uint,tagRECT *)
0x180023325  mov     rcx, [rbx+0B8h]; this
0x18002332c  call    ?Flush@CFcWireEncoder@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::CFcWireEncoder::Flush(uint)
0x180023331  nop
0x180023332  lea     rcx, [rsp+0A8h+var_48]
0x180023337  call    ??1?$vector@UtagRECT@@V?$allocator@UtagRECT@@@std@@@std@@QEAA@XZ; std::vector<tagRECT>::~vector<tagRECT>(void)
0x18002333c  mov     rax, cs:WPP_GLOBAL_Control
0x180023343  cmp     rax, r13
0x180023346  jz      short loc_180023354
0x180023348  test    [rax+1Ch], dil
0x18002334c  jz      short loc_180023354
0x18002334e  cmp     byte ptr [rax+19h], 4
0x180023352  jnb     short loc_180023357
0x180023354  xor     dil, dil
0x180023357  lea     rax, WPP_RECORDER_INITIALIZED
0x18002335e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180023365  setnz   bl
0x180023368  test    dil, dil
0x18002336b  jnz     short loc_180023371
0x18002336d  test    bl, bl
0x18002336f  jz      short loc_1800233A1
0x180023371  call    cs:__imp_GetCurrentThreadId
0x180023377  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x18002337b  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x180023380  mov     word ptr [rsp+0A8h+var_78], 11h; __int16
0x180023387  mov     rcx, cs:WPP_GLOBAL_Control
0x18002338e  mov     r9, [rcx+28h]; int
0x180023392  mov     r8b, bl; int
0x180023395  mov     dl, dil; int
0x180023398  mov     rcx, [rcx+10h]; int
0x18002339c  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800233a1  xor     eax, eax
0x1800233a3  jmp     short loc_1800233AC
0x1800233a5  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x1800233ac  lea     r11, [rsp+0A8h+var_28]
0x1800233b4  mov     rbx, [r11+38h]
0x1800233b8  mov     rsi, [r11+40h]
0x1800233bc  mov     rsp, r11
0x1800233bf  pop     r15
0x1800233c1  pop     r14
0x1800233c3  pop     r13
0x1800233c5  pop     r12
0x1800233c7  pop     rdi
0x1800233c8  retn
0x1800233c9  call    ?_Xlength@?$vector@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIStreamFormat@nanocom@ds@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@CAXXZ; std::vector<wil::com_ptr_t<ds::nanocom::IStreamFormat,wil::err_exception_policy>>::_Xlength(void)
```
