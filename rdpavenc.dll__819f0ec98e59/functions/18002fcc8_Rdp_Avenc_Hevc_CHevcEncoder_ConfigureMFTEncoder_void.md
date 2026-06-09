# Rdp::Avenc::Hevc::CHevcEncoder::ConfigureMFTEncoder(void)

- ea: `0x18002fcc8`
- end: `0x180030331`
- name: `?ConfigureMFTEncoder@CHevcEncoder@Hevc@Avenc@Rdp@@AEAAXXZ`
- size: `1641`
- prototype: `void __fastcall(Rdp::Avenc::Hevc::CHevcEncoder *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003131c`

## callees

- `0x180001008`
- `0x18000e848`
- `0x18000ec04`
- `0x1800275fc`
- `0x18002fcc8`
- `0x180089010`

## string_xrefs

- `0x1800302f5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18003031f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002ff74`: `codecApi->SetValue( CODECAPI_AVEncCommonRateControlMode ) failed`
- `0x18002ffd5`: `codecApi->SetValue(CODECAPI_AVEncCommonQualityVsSpeed) failed`
- `0x180030097`: `codecApi->SetValue( CODECAPI_AVEncCommonQuality ) failed`
- `0x180030155`: `codecApi->SetValue(CODECAPI_AVEncNoInputCopy) failed`
- `0x18003026d`: `Rdp::Avenc::Hevc::CHevcEncoder::ConfigureMFTEncoder`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Rdp::Avenc::Hevc::CHevcEncoder::ConfigureMFTEncoder(
        Rdp::Avenc::Hevc::CHevcEncoder *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rcx
  int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, __int64 *); // r14
  __int64 v24; // rcx
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  int v28; // r8d
  int v29; // r9d
  int v30; // [rsp+20h] [rbp-50h]
  const char *v31; // [rsp+28h] [rbp-48h]
  const char *v32; // [rsp+28h] [rbp-48h]
  const char *v33; // [rsp+28h] [rbp-48h]
  const char *v34; // [rsp+40h] [rbp-30h] BYREF
  const char *v35; // [rsp+48h] [rbp-28h] BYREF
  __int128 v36; // [rsp+50h] [rbp-20h] BYREF
  __int64 v37; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  __int64 v39; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v40; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v41; // [rsp+B0h] [rbp+40h] BYREF
  const char *v42; // [rsp+B8h] [rbp+48h] BYREF

  v36 = 0;
  v37 = 0;
  v41 = 0;
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 35);
  if ( !v5 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      a4);
  v39 = 0;
  v6 = (**v5)(v5, &GUID_2cd0bd52_bcd5_4b89_b62c_eadc0c031e7d, &v39);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v6,
      v30);
  v7 = v39;
  v8 = 0;
  v39 = 0;
  v9 = *((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = v7;
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v8 = v39;
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 35);
  v40 = 0;
  v11 = (**v10)(v10, &GUID_901db4c7_31ce_41a2_85dc_8fa0bf41b8da, &v40);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v11,
      v30);
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v40 + 24LL))(
          v40,
          &GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee) )
  {
    LOWORD(v36) = 11;
    WORD4(v36) = -1;
    v12 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v40 + 72LL))(
            v40,
            &GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee,
            &v36);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v12,
      (int)"codecApi->SetValue( CODECAPI_AVLowLatencyMode ) failed",
      v31);
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v40 + 24LL))(
          v40,
          &GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2) )
  {
    LOWORD(v36) = 19;
    DWORD2(v36) = *((unsigned __int8 *)this + 88);
    v13 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v40 + 72LL))(
            v40,
            &GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2,
            &v36);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v13,
      (int)"codecApi->SetValue( CODECAPI_AVEncVideoMaxQP ) failed",
      v31);
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v40 + 24LL))(
          v40,
          &GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886) )
  {
    LOWORD(v36) = 19;
    DWORD2(v36) = *((unsigned __int8 *)this + 89);
    v14 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v40 + 72LL))(
            v40,
            &GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886,
            &v36);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v14,
      (int)"codecApi->SetValue( CODECAPI_AVEncVideoMinQP ) failed",
      v31);
  }
  if ( *((_DWORD *)this + 26)
    && !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v40 + 24LL))(
          v40,
          &GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1) )
  {
    LOWORD(v36) = 19;
    DWORD2(v36) = *((_DWORD *)this + 26);
    v15 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v40 + 72LL))(
            v40,
            &GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1,
            &v36);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v15,
      (int)"SetValue CODECAPI_AVEncMPVGOPSize failed",
      v31);
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v40 + 24LL))(
          v40,
          &GUID_1c0608e9_370c_4710_8a58_cb6181c42423) )
  {
    LOWORD(v36) = 19;
    DWORD2(v36) = 3;
    v16 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v40 + 72LL))(
            v40,
            &GUID_1c0608e9_370c_4710_8a58_cb6181c42423,
            &v36);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x147,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v16,
      (int)"codecApi->SetValue( CODECAPI_AVEncCommonRateControlMode ) failed",
      v31);
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v40 + 24LL))(
          v40,
          &GUID_98332df8_03cd_476b_89fa_3f9e442dec9f) )
  {
    LOWORD(v36) = 19;
    DWORD2(v36) = 30;
    v17 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v40 + 72LL))(
            v40,
            &GUID_98332df8_03cd_476b_89fa_3f9e442dec9f,
            &v36);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x154,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v17,
      (int)"codecApi->SetValue(CODECAPI_AVEncCommonQualityVsSpeed) failed",
      v31);
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v40 + 24LL))(
          v40,
          &GUID_8acb8fdd_5e0c_4c66_8729_b8f629ab04fb) )
  {
    LOWORD(v36) = 19;
    DWORD2(v36) = 1;
    v18 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v40 + 72LL))(
            v40,
            &GUID_8acb8fdd_5e0c_4c66_8729_b8f629ab04fb,
            &v36);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v18,
      (int)"codecApi->SetValue( CODECAPI_AVEncVideoDirtyRectEnabled ) failed",
      v31);
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v40 + 24LL))(
          v40,
          &GUID_fcbf57a3_7ea5_4b0c_9644_69b40c39c391) )
  {
    LOWORD(v36) = 19;
    DWORD2(v36) = 100;
    v19 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v40 + 72LL))(
            v40,
            &GUID_fcbf57a3_7ea5_4b0c_9644_69b40c39c391,
            &v36);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x167,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v19,
      (int)"codecApi->SetValue( CODECAPI_AVEncCommonQuality ) failed",
      v31);
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v40 + 24LL))(
          v40,
          &GUID_d2e8e399_0623_4bf3_92a8_4d1818529ded) )
  {
    LOWORD(v36) = 19;
    DWORD2(v36) = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v40 + 72LL))(
            v40,
            &GUID_d2e8e399_0623_4bf3_92a8_4d1818529ded,
            &v36);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x173,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v20,
      (int)"codecApi->SetValue( CODECAPI_AVEnableInLoopDeblockFilter ) failed",
      v31);
  }
  if ( !(*(unsigned int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v40 + 24LL))(
          v40,
          &GUID_d2b46a2a_e8ee_4ec5_869e_449b6c62c81a) )
  {
    LOWORD(v36) = 19;
    DWORD2(v36) = 1;
    v21 = (*(__int64 (__fastcall **)(__int64, GUID *, __int128 *))(*(_QWORD *)v40 + 72LL))(
            v40,
            &GUID_d2b46a2a_e8ee_4ec5_869e_449b6c62c81a,
            &v36);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x17D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v21,
      (int)"codecApi->SetValue(CODECAPI_AVEncNoInputCopy) failed",
      v31);
  }
  v22 = *((_QWORD *)this + 35);
  v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 64LL);
  v24 = v41;
  v41 = 0;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v25 = v23(v22, &v41);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x182,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
    (const char *)v25,
    (int)"pEncoder->GetAttributes() failed",
    v31);
  v26 = (*(__int64 (__fastcall **)(__int64, const GUID *, __int64))(*(_QWORD *)v41 + 168LL))(
          v41,
          &MF_TRANSFORM_ASYNC_UNLOCK,
          1);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x185,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
    (const char *)v26,
    (int)"MF_TRANSFORM_ASYNC_UNLOCK failed",
    v32);
  if ( *((_QWORD *)this + 36) )
  {
    v27 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 35) + 184LL))(*((_QWORD *)this + 35), 2);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp",
      (const char *)v27,
      (int)"MFT_MESSAGE_SET_D3D_MANAGER failed",
      v33);
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v42 = "D3D Device Manager set on HEVC encoder MFT";
      v34 = "Rdp::Avenc::Hevc::CHevcEncoder::ConfigureMFTEncoder";
      LODWORD(v39) = 399;
      v35 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcencoder.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)qword_1800AEB30,
        v28,
        v29,
        (__int64)&v35,
        (__int64)&v39,
        (__int64)&v34,
        (__int64)&v42);
    }
  }
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
}

```

## disassembly

```asm
0x18002fcc8  push    rbp
0x18002fcca  push    rbx
0x18002fccb  push    rsi
0x18002fccc  push    rdi
0x18002fccd  push    r14
0x18002fccf  mov     rbp, rsp
0x18002fcd2  sub     rsp, 70h
0x18002fcd6  mov     rdi, rcx
0x18002fcd9  xorps   xmm0, xmm0
0x18002fcdc  xor     eax, eax
0x18002fcde  movups  [rbp+var_20], xmm0
0x18002fce2  mov     [rbp+var_10], rax
0x18002fce6  mov     [rbp+arg_10], rax
0x18002fcea  mov     rax, [rbp+28h]
0x18002fcee  mov     rcx, [rcx+118h]
0x18002fcf5  test    rcx, rcx
0x18002fcf8  jz      loc_180030307
0x18002fcfe  mov     [rbp+arg_0], 0
0x18002fd06  mov     rax, [rcx]
0x18002fd09  lea     r8, [rbp+arg_0]
0x18002fd0d  lea     rdx, _GUID_2cd0bd52_bcd5_4b89_b62c_eadc0c031e7d
0x18002fd14  mov     rax, [rax]
0x18002fd17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd1c  mov     rcx, [rbp+28h]; this
0x18002fd20  test    eax, eax
0x18002fd22  js      loc_18003031C
0x18002fd28  mov     rax, [rbp+arg_0]
0x18002fd2c  xor     ecx, ecx
0x18002fd2e  mov     [rbp+arg_0], rcx
0x18002fd32  mov     rdx, [rdi+40h]
0x18002fd36  mov     [rdi+40h], rax
0x18002fd3a  test    rdx, rdx
0x18002fd3d  jz      short loc_18002FD52
0x18002fd3f  mov     rax, [rdx]
0x18002fd42  mov     rcx, rdx
0x18002fd45  mov     rax, [rax+10h]
0x18002fd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd4e  mov     rcx, [rbp+arg_0]
0x18002fd52  test    rcx, rcx
0x18002fd55  jz      short loc_18002FD64
0x18002fd57  mov     rax, [rcx]
0x18002fd5a  mov     rax, [rax+10h]
0x18002fd5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd63  nop
0x18002fd64  mov     rcx, [rdi+118h]
0x18002fd6b  mov     [rbp+arg_8], 0
0x18002fd73  mov     rax, [rcx]
0x18002fd76  lea     r8, [rbp+arg_8]
0x18002fd7a  lea     rdx, _GUID_901db4c7_31ce_41a2_85dc_8fa0bf41b8da
0x18002fd81  mov     rax, [rax]
0x18002fd84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd89  mov     rcx, [rbp+28h]; this
0x18002fd8d  test    eax, eax
0x18002fd8f  js      loc_1800302F2
0x18002fd95  mov     rcx, [rbp+arg_8]
0x18002fd99  mov     rax, [rcx]
0x18002fd9c  lea     rdx, _GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee
0x18002fda3  mov     rax, [rax+18h]
0x18002fda7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdac  lea     rbx, aOnecoreuapTerm_32; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002fdb3  test    eax, eax
0x18002fdb5  jnz     short loc_18002FE02
0x18002fdb7  mov     eax, 0Bh
0x18002fdbc  mov     word ptr [rbp+var_20], ax
0x18002fdc0  or      eax, 0FFFFFFFFh
0x18002fdc3  mov     word ptr [rbp+var_20+8], ax
0x18002fdc7  mov     rcx, [rbp+arg_8]
0x18002fdcb  mov     rax, [rcx]
0x18002fdce  lea     r8, [rbp+var_20]
0x18002fdd2  lea     rdx, _GUID_9c27891a_ed7a_40e1_88e8_b22727a024ee
0x18002fdd9  mov     rax, [rax+48h]
0x18002fddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fde2  mov     rcx, [rbp+28h]; this
0x18002fde6  lea     rdx, aCodecapiSetval_4; "codecApi->SetValue( CODECAPI_AVLowLaten"...
0x18002fded  mov     qword ptr [rsp+70h+var_50], rdx; int
0x18002fdf2  mov     r9d, eax; char *
0x18002fdf5  mov     r8, rbx; unsigned int
0x18002fdf8  mov     edx, 123h; void *
0x18002fdfd  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002fe02  mov     rcx, [rbp+arg_8]
0x18002fe06  mov     rax, [rcx]
0x18002fe09  lea     rdx, _GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2
0x18002fe10  mov     rax, [rax+18h]
0x18002fe14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe19  mov     esi, 13h
0x18002fe1e  test    eax, eax
0x18002fe20  jnz     short loc_18002FE68
0x18002fe22  mov     word ptr [rbp+var_20], si
0x18002fe26  movzx   eax, byte ptr [rdi+58h]
0x18002fe2a  mov     dword ptr [rbp+var_20+8], eax
0x18002fe2d  mov     rcx, [rbp+arg_8]
0x18002fe31  mov     rax, [rcx]
0x18002fe34  lea     r8, [rbp+var_20]
0x18002fe38  lea     rdx, _GUID_3daf6f66_a6a7_45e0_a8e5_f2743f46a3a2
0x18002fe3f  mov     rax, [rax+48h]
0x18002fe43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe48  mov     rcx, [rbp+28h]; this
0x18002fe4c  lea     rdx, aCodecapiSetval_1; "codecApi->SetValue( CODECAPI_AVEncVideo"...
0x18002fe53  mov     qword ptr [rsp+70h+var_50], rdx; int
0x18002fe58  mov     r9d, eax; char *
0x18002fe5b  mov     r8, rbx; unsigned int
0x18002fe5e  mov     edx, 12Ch; void *
0x18002fe63  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002fe68  mov     rcx, [rbp+arg_8]
0x18002fe6c  mov     rax, [rcx]
0x18002fe6f  lea     rdx, _GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886
0x18002fe76  mov     rax, [rax+18h]
0x18002fe7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe7f  test    eax, eax
0x18002fe81  jnz     short loc_18002FEC9
0x18002fe83  mov     word ptr [rbp+var_20], si
0x18002fe87  movzx   eax, byte ptr [rdi+59h]
0x18002fe8b  mov     dword ptr [rbp+var_20+8], eax
0x18002fe8e  mov     rcx, [rbp+arg_8]
0x18002fe92  mov     rax, [rcx]
0x18002fe95  lea     r8, [rbp+var_20]
0x18002fe99  lea     rdx, _GUID_0ee22c6a_a37c_4568_b5f1_9d4c2b3ab886
0x18002fea0  mov     rax, [rax+48h]
0x18002fea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fea9  mov     rcx, [rbp+28h]; this
0x18002fead  lea     rdx, aCodecapiSetval_7; "codecApi->SetValue( CODECAPI_AVEncVideo"...
0x18002feb4  mov     qword ptr [rsp+70h+var_50], rdx; int
0x18002feb9  mov     r9d, eax; char *
0x18002febc  mov     r8, rbx; unsigned int
0x18002febf  mov     edx, 135h; void *
0x18002fec4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002fec9  cmp     dword ptr [rdi+68h], 0
0x18002fecd  jz      short loc_18002FF2F
0x18002fecf  mov     rcx, [rbp+arg_8]
0x18002fed3  mov     rax, [rcx]
0x18002fed6  lea     rdx, _GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1
0x18002fedd  mov     rax, [rax+18h]
0x18002fee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fee6  test    eax, eax
0x18002fee8  jnz     short loc_18002FF2F
0x18002feea  mov     word ptr [rbp+var_20], si
0x18002feee  mov     eax, [rdi+68h]
0x18002fef1  mov     dword ptr [rbp+var_20+8], eax
0x18002fef4  mov     rcx, [rbp+arg_8]
0x18002fef8  mov     rax, [rcx]
0x18002fefb  lea     r8, [rbp+var_20]
0x18002feff  lea     rdx, _GUID_95f31b26_95a4_41aa_9303_246a7fc6eef1
0x18002ff06  mov     rax, [rax+48h]
0x18002ff0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff0f  mov     rcx, [rbp+28h]; this
0x18002ff13  lea     rdx, aSetvalueCodeca; "SetValue CODECAPI_AVEncMPVGOPSize faile"...
0x18002ff1a  mov     qword ptr [rsp+70h+var_50], rdx; int
0x18002ff1f  mov     r9d, eax; char *
0x18002ff22  mov     r8, rbx; unsigned int
0x18002ff25  mov     edx, 13Dh; void *
0x18002ff2a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ff2f  mov     rcx, [rbp+arg_8]
0x18002ff33  mov     rax, [rcx]
0x18002ff36  lea     rdx, _GUID_1c0608e9_370c_4710_8a58_cb6181c42423
0x18002ff3d  mov     rax, [rax+18h]
0x18002ff41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff46  test    eax, eax
0x18002ff48  jnz     short loc_18002FF90
0x18002ff4a  mov     word ptr [rbp+var_20], si
0x18002ff4e  mov     dword ptr [rbp+var_20+8], 3
0x18002ff55  mov     rcx, [rbp+arg_8]
0x18002ff59  mov     rax, [rcx]
0x18002ff5c  lea     r8, [rbp+var_20]
0x18002ff60  lea     rdx, _GUID_1c0608e9_370c_4710_8a58_cb6181c42423
0x18002ff67  mov     rax, [rax+48h]
0x18002ff6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff70  mov     rcx, [rbp+28h]; this
0x18002ff74  lea     rdx, aCodecapiSetval_2; "codecApi->SetValue( CODECAPI_AVEncCommo"...
0x18002ff7b  mov     qword ptr [rsp+70h+var_50], rdx; int
0x18002ff80  mov     r9d, eax; char *
0x18002ff83  mov     r8, rbx; unsigned int
0x18002ff86  mov     edx, 147h; void *
0x18002ff8b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002ff90  mov     rcx, [rbp+arg_8]
0x18002ff94  mov     rax, [rcx]
0x18002ff97  lea     rdx, _GUID_98332df8_03cd_476b_89fa_3f9e442dec9f
0x18002ff9e  mov     rax, [rax+18h]
0x18002ffa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffa7  test    eax, eax
0x18002ffa9  jnz     short loc_18002FFF1
0x18002ffab  mov     word ptr [rbp+var_20], si
0x18002ffaf  mov     dword ptr [rbp+var_20+8], 1Eh
0x18002ffb6  mov     rcx, [rbp+arg_8]
0x18002ffba  mov     rax, [rcx]
0x18002ffbd  lea     r8, [rbp+var_20]
0x18002ffc1  lea     rdx, _GUID_98332df8_03cd_476b_89fa_3f9e442dec9f
0x18002ffc8  mov     rax, [rax+48h]
0x18002ffcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffd1  mov     rcx, [rbp+28h]; this
0x18002ffd5  lea     rdx, aCodecapiSetval; "codecApi->SetValue(CODECAPI_AVEncCommon"...
0x18002ffdc  mov     qword ptr [rsp+70h+var_50], rdx; int
0x18002ffe1  mov     r9d, eax; char *
0x18002ffe4  mov     r8, rbx; unsigned int
0x18002ffe7  mov     edx, 154h; void *
0x18002ffec  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002fff1  mov     rcx, [rbp+arg_8]
0x18002fff5  mov     rax, [rcx]
0x18002fff8  lea     rdx, _GUID_8acb8fdd_5e0c_4c66_8729_b8f629ab04fb
0x18002ffff  mov     rax, [rax+18h]
0x180030003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030008  test    eax, eax
0x18003000a  jnz     short loc_180030052
0x18003000c  mov     word ptr [rbp+var_20], si
0x180030010  mov     dword ptr [rbp+var_20+8], 1
0x180030017  mov     rcx, [rbp+arg_8]
0x18003001b  mov     rax, [rcx]
0x18003001e  lea     r8, [rbp+var_20]
0x180030022  lea     rdx, _GUID_8acb8fdd_5e0c_4c66_8729_b8f629ab04fb
0x180030029  mov     rax, [rax+48h]
0x18003002d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030032  mov     rcx, [rbp+28h]; this
0x180030036  lea     rdx, aCodecapiSetval_5; "codecApi->SetValue( CODECAPI_AVEncVideo"...
0x18003003d  mov     qword ptr [rsp+70h+var_50], rdx; int
0x180030042  mov     r9d, eax; char *
0x180030045  mov     r8, rbx; unsigned int
0x180030048  mov     edx, 15Dh; void *
0x18003004d  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180030052  mov     rcx, [rbp+arg_8]
0x180030056  mov     rax, [rcx]
0x180030059  lea     rdx, _GUID_fcbf57a3_7ea5_4b0c_9644_69b40c39c391
0x180030060  mov     rax, [rax+18h]
0x180030064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030069  test    eax, eax
0x18003006b  jnz     short loc_1800300B3
0x18003006d  mov     word ptr [rbp+var_20], si
0x180030071  mov     dword ptr [rbp+var_20+8], 64h ; 'd'
0x180030078  mov     rcx, [rbp+arg_8]
0x18003007c  mov     rax, [rcx]
0x18003007f  lea     r8, [rbp+var_20]
0x180030083  lea     rdx, _GUID_fcbf57a3_7ea5_4b0c_9644_69b40c39c391
0x18003008a  mov     rax, [rax+48h]
0x18003008e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030093  mov     rcx, [rbp+28h]; this
0x180030097  lea     rdx, aCodecapiSetval_6; "codecApi->SetValue( CODECAPI_AVEncCommo"...
0x18003009e  mov     qword ptr [rsp+70h+var_50], rdx; int
0x1800300a3  mov     r9d, eax; char *
0x1800300a6  mov     r8, rbx; unsigned int
0x1800300a9  mov     edx, 167h; void *
0x1800300ae  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800300b3  mov     rcx, [rbp+arg_8]
0x1800300b7  mov     rax, [rcx]
0x1800300ba  lea     rdx, _GUID_d2e8e399_0623_4bf3_92a8_4d1818529ded
0x1800300c1  mov     rax, [rax+18h]
0x1800300c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300ca  test    eax, eax
0x1800300cc  jnz     short loc_180030110
0x1800300ce  mov     word ptr [rbp+var_20], si
0x1800300d2  mov     dword ptr [rbp+var_20+8], eax
0x1800300d5  mov     rcx, [rbp+arg_8]
0x1800300d9  mov     rax, [rcx]
0x1800300dc  lea     r8, [rbp+var_20]
0x1800300e0  lea     rdx, _GUID_d2e8e399_0623_4bf3_92a8_4d1818529ded
0x1800300e7  mov     rax, [rax+48h]
0x1800300eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300f0  mov     rcx, [rbp+28h]; this
0x1800300f4  lea     rdx, aCodecapiSetval_3; "codecApi->SetValue( CODECAPI_AVEnableIn"...
0x1800300fb  mov     qword ptr [rsp+70h+var_50], rdx; int
0x180030100  mov     r9d, eax; char *
0x180030103  mov     r8, rbx; unsigned int
0x180030106  mov     edx, 173h; void *
0x18003010b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180030110  mov     rcx, [rbp+arg_8]
0x180030114  mov     rax, [rcx]
0x180030117  lea     rdx, _GUID_d2b46a2a_e8ee_4ec5_869e_449b6c62c81a
0x18003011e  mov     rax, [rax+18h]
0x180030122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030127  test    eax, eax
0x180030129  jnz     short loc_180030171
0x18003012b  mov     word ptr [rbp+var_20], si
0x18003012f  mov     dword ptr [rbp+var_20+8], 1
0x180030136  mov     rcx, [rbp+arg_8]
0x18003013a  mov     rax, [rcx]
0x18003013d  lea     r8, [rbp+var_20]
0x180030141  lea     rdx, _GUID_d2b46a2a_e8ee_4ec5_869e_449b6c62c81a
0x180030148  mov     rax, [rax+48h]
0x18003014c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030151  mov     rcx, [rbp+28h]; this
0x180030155  lea     rdx, aCodecapiSetval_0; "codecApi->SetValue(CODECAPI_AVEncNoInpu"...
0x18003015c  mov     qword ptr [rsp+70h+var_50], rdx; int
0x180030161  mov     r9d, eax; char *
0x180030164  mov     r8, rbx; unsigned int
0x180030167  mov     edx, 17Dh; void *
0x18003016c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180030171  mov     rsi, [rdi+118h]
0x180030178  mov     rax, [rsi]
0x18003017b  mov     r14, [rax+40h]
0x18003017f  mov     rcx, [rbp+arg_10]
0x180030183  mov     [rbp+arg_10], 0
0x18003018b  test    rcx, rcx
0x18003018e  jz      short loc_18003019D
0x180030190  mov     rdx, [rcx]
0x180030193  mov     rax, [rdx+10h]
0x180030197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003019c  nop
0x18003019d  lea     rdx, [rbp+arg_10]
0x1800301a1  mov     rcx, rsi
0x1800301a4  mov     rax, r14
0x1800301a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301ac  mov     rcx, [rbp+28h]; this
0x1800301b0  lea     rdx, aPencoderGetatt; "pEncoder->GetAttributes() failed"
  ... truncated ...
```
