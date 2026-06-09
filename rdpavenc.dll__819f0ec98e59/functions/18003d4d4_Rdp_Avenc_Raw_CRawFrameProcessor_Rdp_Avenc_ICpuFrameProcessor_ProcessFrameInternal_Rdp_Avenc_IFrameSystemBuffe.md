# Rdp::Avenc::Raw::CRawFrameProcessor<Rdp::Avenc::ICpuFrameProcessor>::ProcessFrameInternal<Rdp::Avenc::IFrameSystemBuffer>(Rdp::Avenc::IFrameSystemBuffer &,bool *)

- ea: `0x18003d4d4`
- end: `0x18003de41`
- name: `??$ProcessFrameInternal@UIFrameSystemBuffer@Avenc@Rdp@@@?$CRawFrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@@Raw@Avenc@Rdp@@IEAAJAEAUIFrameSystemBuffer@23@PEA_N@Z`
- size: `2413`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18003cf00`

## callees

- `0x1800032cc`
- `0x180006580`
- `0x1800080cc`
- `0x18000a1b4`
- `0x18000e848`
- `0x1800103c0`
- `0x180010bc8`
- `0x18001143c`
- `0x1800199cc`
- `0x18002a828`
- `0x18002df60`
- `0x18003968c`
- `0x180039ff0`
- `0x18003d4d4`
- `0x180082e90`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d854`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003d854`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003d8a9`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18003d8a9`

## string_xrefs

- `0x18003d5c2`: `Failed to get moves and dirties`
- `0x18003de10`: `onecoreuap\termsrv\rdp_bin\win\common/inc/GraphicsUtils.h`
- `0x18003d75a`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18003d98c`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18003dbe6`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall Rdp::Avenc::Raw::CRawFrameProcessor<Rdp::Avenc::ICpuFrameProcessor>::ProcessFrameInternal<Rdp::Avenc::IFrameSystemBuffer>(
        __int64 a1,
        __int64 a2,
        const char *a3)
{
  unsigned int v7; // r12d
  __int64 v8; // r14
  _DWORD *v9; // rsi
  int v10; // eax
  int v11; // r8d
  _DWORD *v12; // rdx
  _DWORD *v13; // r9
  int v14; // ecx
  int v15; // eax
  unsigned int v16; // ecx
  __int64 v17; // r14
  _DWORD *v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rdx
  unsigned int v21; // r13d
  __int128 v22; // xmm6
  __int64 v23; // rax
  _DWORD *v24; // r14
  __int64 v25; // r14
  _QWORD *v26; // rcx
  __int64 v27; // r13
  __int64 v28; // rdx
  unsigned int v29; // ecx
  int v30; // eax
  __int64 v31; // r13
  char *v32; // r13
  _QWORD *v33; // rcx
  FILETIME v34; // rdx
  __int64 v35; // r8
  size_t v36; // r14
  unsigned int i; // eax
  _QWORD *v38; // rcx
  FILETIME v39; // r9
  __int64 v40; // r8
  __int64 v41; // r14
  _DWORD *v42; // rsi
  __int64 v43; // rcx
  bool v44; // r8
  const char *v45; // r14
  int v46; // eax
  __int64 v47; // rdx
  int v48; // r8d
  int v49; // r9d
  unsigned int v50; // eax
  int v51; // edx
  int v52; // [rsp+20h] [rbp-148h]
  char *v53; // [rsp+28h] [rbp-140h]
  char *v54; // [rsp+28h] [rbp-140h]
  unsigned int Size; // [rsp+90h] [rbp-D8h] BYREF
  int Size_4; // [rsp+94h] [rbp-D4h] BYREF
  FILETIME FileTime; // [rsp+98h] [rbp-D0h] BYREF
  unsigned int v58; // [rsp+A0h] [rbp-C8h] BYREF
  unsigned int v59; // [rsp+A4h] [rbp-C4h] BYREF
  int v60; // [rsp+A8h] [rbp-C0h]
  unsigned int v61; // [rsp+ACh] [rbp-BCh]
  _QWORD v62[2]; // [rsp+B0h] [rbp-B8h] BYREF
  const char *v63; // [rsp+C0h] [rbp-A8h] BYREF
  const char *v64; // [rsp+C8h] [rbp-A0h] BYREF
  const char *v65; // [rsp+D0h] [rbp-98h] BYREF
  const char *v66; // [rsp+D8h] [rbp-90h] BYREF
  _DWORD *v67; // [rsp+E0h] [rbp-88h] BYREF
  _DWORD *v68; // [rsp+E8h] [rbp-80h]
  __int64 v69; // [rsp+F0h] [rbp-78h]
  __int64 *v70; // [rsp+F8h] [rbp-70h]
  _DWORD *v71; // [rsp+100h] [rbp-68h]
  struct _SYSTEMTIME SystemTime; // [rsp+108h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]

  v63 = a3;
  v64 = (const char *)a1;
  v65 = (const char *)a1;
  v69 = a2;
  v66 = a3;
  if ( a3 )
  {
    v7 = 0;
    v59 = 0;
    v58 = 0;
    v67 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 40LL))(a2);
    v61 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _DWORD **, unsigned int *))(*(_QWORD *)a2 + 136LL))(
            a2,
            0,
            0,
            &v67,
            &v58);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawframeprocessor.cpp",
      (const char *)v61,
      (int)"Failed to get moves and dirties",
      v53);
    v8 = v58;
    v9 = v67;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 48LL))(a2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 56LL))(a2);
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 176LL))(a2);
    if ( v10 == 10 )
    {
      v11 = 8;
    }
    else
    {
      if ( v10 != 87 )
      {
        v50 = wil::verify_hresult<long>(2147942487LL);
        LODWORD(v54) = v51;
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x89,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/GraphicsUtils.h",
          (const char *)v50,
          (int)"Unsupported DXGI_FORMAT: %d",
          v54);
      }
      v11 = 4;
    }
    v60 = v11;
    v12 = v9;
    v13 = &v9[4 * v8];
    v71 = v13;
    if ( v9 == v13 )
      goto LABEL_44;
    do
    {
      v14 = (v12[2] - *v12) * (v12[3] - v12[1]);
      v15 = v14 * v11;
      v16 = v7 + v14;
      if ( !v15 )
        v16 = v7;
      v7 = v16;
      v12 += 4;
    }
    while ( v12 != v13 );
    v59 = v16;
    if ( !v16 )
    {
LABEL_44:
      *a3 = 0;
      return 0;
    }
    else
    {
      Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(
        *(Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)(a1 + 104),
        ((v16 * v11 + 4095) & 0xFFFFF000) + 4096);
      v17 = *(_QWORD *)(a1 + 104);
      v70 = (__int64 *)(a1 + 88);
      v62[0] = *(_QWORD *)(a1 + 88);
      FileTime = (FILETIME)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 128LL))(a2);
      Size_4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
      v18 = 0;
      v68 = 0;
      v19 = *(_QWORD *)(v17 + 32);
      if ( (unsigned __int64)(*(_QWORD *)(v17 + 40) - v19) >= 0x10 )
      {
        v18 = (_DWORD *)(v19 + *(_QWORD *)(v17 + 8));
        v68 = v18;
        *(_QWORD *)(v17 + 32) = v19 + 16;
      }
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        383,
        "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
        2147942414LL,
        v18,
        "Unable to ensure RDPGFX_START_FRAME_PDU_SIZE");
      Size = 0;
      *(_QWORD *)&SystemTime.wYear = Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::m_Lock;
      if ( (unsigned int)mtx_do_lock(Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::m_Lock) )
        std::_Throw_Cpp_error(5);
      if ( dword_1800C191C == 0x7FFFFFFF )
      {
        dword_1800C191C = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      v20 = Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::g_FrameId % 0xFFFFFFFF;
      v21 = Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::g_FrameId / 0xFFFFFFFF
          + Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::g_FrameId
          + 1;
      Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::g_FrameId = v21;
      Size = v21;
      if ( (unsigned __int64)qword_1800C1E30 > 0x2000 )
      {
        std::_Hash<std::_Umap_traits<unsigned int,Rdp::Protocol::EgfxFrameIdMap,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,Rdp::Protocol::EgfxFrameIdMap>>,0>>::clear(
          &Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::m_FrameLookup,
          v20);
        v21 = Size;
      }
      v22 = *(_OWORD *)(v62[0] + 120LL);
      v23 = *(_QWORD *)std::_Hash<std::_Umap_traits<unsigned int,Rdp::Protocol::EgfxFrameIdMap,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,Rdp::Protocol::EgfxFrameIdMap>>,0>>::_Try_emplace<unsigned int const &,>(
                         &Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::m_FrameLookup,
                         v62,
                         &Size);
      *(_DWORD *)(v23 + 20) = v21;
      *(_DWORD *)(v23 + 24) = Size_4;
      *(_OWORD *)(v23 + 28) = v22;
      *(_DWORD *)(v17 + 3072) = Size;
      if ( !--dword_1800C191C )
      {
        dword_1800C1918 = -1;
        ReleaseSRWLockExclusive(&stru_1800C18E0);
      }
      v24 = v68;
      *v68 = 11;
      v24[1] = 16;
      SystemTime = 0;
      FileTimeToSystemTime(&FileTime, &SystemTime);
      v24[2] = SystemTime.wMilliseconds
             | ((SystemTime.wSecond | ((SystemTime.wMinute | (SystemTime.wHour << 6)) << 6)) << 10);
      v24[3] = Size;
      while ( v9 != v71 )
      {
        LODWORD(v62[0]) = v9[3] - v9[1];
        v25 = (unsigned int)(v60 * (v9[2] - *v9));
        Size = LODWORD(v62[0]) * v60 * (v9[2] - *v9);
        if ( Size )
        {
          v26 = *(_QWORD **)(a1 + 104);
          Size_4 = *(_DWORD *)(*(_QWORD *)(a1 + 88) + 136LL);
          v27 = 0;
          v28 = v26[4];
          if ( (unsigned __int64)(v26[5] - v28) >= 0x19 )
          {
            v27 = v28 + v26[1];
            v26[4] = v28 + 25;
          }
          wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
            retaddr,
            445,
            "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
            2147942414LL,
            v27,
            "Unable to ensure RDPGFX_WIRE_TO_SURFACE_PDU_1 %d bytes",
            25);
          *(_DWORD *)v27 = 1;
          v29 = Size;
          *(_DWORD *)(v27 + 4) = Size + 25;
          *(_WORD *)(v27 + 8) = Size_4;
          *(_WORD *)(v27 + 10) = 0;
          *(_BYTE *)(v27 + 12) = 33;
          *(_WORD *)(v27 + 13) = *(_WORD *)v9;
          *(_WORD *)(v27 + 15) = *((_WORD *)v9 + 2);
          *(_WORD *)(v27 + 17) = *((_WORD *)v9 + 4);
          *(_WORD *)(v27 + 19) = *((_WORD *)v9 + 6);
          *(_DWORD *)(v27 + 21) = v29;
          v30 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 152LL))(a2);
          v31 = (unsigned int)(v9[1] * v30 + *v9 * v60);
          v32 = (char *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 184LL))(a2) + v31);
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a2 + 152LL))(a2) == (_DWORD)v25 )
          {
            v33 = *(_QWORD **)(a1 + 104);
            v34 = 0;
            FileTime = 0;
            v35 = v33[4];
            v36 = Size;
            if ( v33[5] - v35 >= (unsigned __int64)Size )
            {
              v34 = (FILETIME)(v35 + v33[1]);
              FileTime = v34;
              v33[4] = Size + v35;
            }
            ((void (*)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, const char *, ...))wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>)(
              retaddr,
              852,
              "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\inc\\FcWireEncoder.h",
              2147942414LL,
              v34,
              "Unable to ensure %zu bytes",
              v36);
            memcpy_0(*(void **)&FileTime, v32, v36);
          }
          else
          {
            for ( i = 0; ; i = Size + 1 )
            {
              Size = i;
              if ( i >= LODWORD(v62[0]) )
                break;
              v38 = *(_QWORD **)(a1 + 104);
              v39 = 0;
              FileTime = 0;
              v40 = v38[4];
              if ( v38[5] - v40 >= (unsigned __int64)(unsigned int)v25 )
              {
                v39 = (FILETIME)(v40 + v38[1]);
                FileTime = v39;
                v38[4] = v40 + v25;
              }
              ((void (*)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, const char *, ...))wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>)(
                retaddr,
                852,
                "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\inc\\FcWireEncoder.h",
                2147942414LL,
                v39,
                "Unable to ensure %zu bytes",
                (unsigned int)v25);
              memcpy_0(*(void **)&FileTime, v32, (unsigned int)v25);
              v32 += (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)a2 + 152LL))(a2);
            }
          }
        }
        v9 += 4;
      }
      v41 = *(_QWORD *)(a1 + 104);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
      v42 = 0;
      v43 = *(_QWORD *)(v41 + 32);
      if ( (unsigned __int64)(*(_QWORD *)(v41 + 40) - v43) >= 0xC )
      {
        v42 = (_DWORD *)(v43 + *(_QWORD *)(v41 + 8));
        *(_QWORD *)(v41 + 32) = v43 + 12;
      }
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        420,
        "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
        2147942414LL,
        v42,
        "Unable to ensure RDPGFX_END_FRAME_PDU_SIZE");
      *v42 = 12;
      v42[1] = 12;
      v42[2] = *(_DWORD *)(v41 + 3072);
      Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(
        *(Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)(a1 + 104),
        0x64u,
        v44);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 64LL))(a2);
      v45 = v63;
      v46 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 112LL))(a2, 1, v7, 0);
      if ( v46 < 0 && (unsigned int)dword_1800C1058 > 2 )
      {
        LODWORD(v62[0]) = v46;
        Size_4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
        v47 = *v70;
        v59 = *(_DWORD *)(*(_QWORD *)(*v70 + 112) + 160LL);
        v66 = (const char *)(v47 + 120);
        v65 = "Failed to report frame statistics";
        v64 = "Rdp::Avenc::Raw::CRawFrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor>::ProcessFrameInternal";
        v58 = 353;
        v63 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawframeprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)word_1800AFB62,
          v48,
          v49,
          (__int64)&v63,
          (__int64)&v58,
          (__int64)&v64,
          (__int64)&v65,
          (__int64)&v66,
          (__int64)&v59,
          (__int64)&Size_4,
          (__int64)v62);
      }
      *v45 = 0;
      return v61;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawframeprocessor.cpp",
      (const char *)0x80004003LL,
      v52);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18003d4d4  mov     rax, rsp
0x18003d4d7  push    rbx
0x18003d4d8  push    rsi
0x18003d4d9  push    rdi
0x18003d4da  push    r12
0x18003d4dc  push    r13
0x18003d4de  push    r14
0x18003d4e0  push    r15
0x18003d4e2  sub     rsp, 130h
0x18003d4e9  movaps  xmmword ptr [rax-48h], xmm6
0x18003d4ed  mov     rax, cs:__security_cookie
0x18003d4f4  xor     rax, rsp
0x18003d4f7  mov     [rsp+168h+var_50], rax
0x18003d4ff  mov     r13, r8
0x18003d502  mov     [rsp+168h+var_A8], r8
0x18003d50a  mov     rbx, rdx
0x18003d50d  mov     r15, rcx
0x18003d510  mov     [rsp+168h+var_A0], rcx
0x18003d518  mov     [rsp+168h+var_98], rcx
0x18003d520  mov     [rsp+168h+var_78], rdx
0x18003d528  mov     [rsp+168h+var_90], r8
0x18003d530  xor     edi, edi
0x18003d532  test    r8, r8
0x18003d535  jnz     short loc_18003D55F
0x18003d537  mov     rcx, [rsp+168h]; this
0x18003d53f  mov     ebx, 80004003h
0x18003d544  mov     r9d, ebx; char *
0x18003d547  lea     r8, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003d54e  mov     edx, 0B9h; void *
0x18003d553  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d558  mov     eax, ebx
0x18003d55a  jmp     loc_18003DDC0
0x18003d55f  mov     r12d, edi
0x18003d562  mov     [rsp+168h+var_C4], edi
0x18003d569  mov     [rsp+168h+var_C8], edi
0x18003d570  mov     [rsp+168h+var_88], rdi
0x18003d578  mov     rax, [rdx]
0x18003d57b  mov     rcx, rbx
0x18003d57e  mov     rax, [rax+28h]
0x18003d582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d587  mov     rax, [rbx]
0x18003d58a  lea     rcx, [rsp+168h+var_C8]
0x18003d592  mov     qword ptr [rsp+168h+var_148], rcx
0x18003d597  lea     r9, [rsp+168h+var_88]
0x18003d59f  xor     r8d, r8d
0x18003d5a2  xor     edx, edx
0x18003d5a4  mov     rcx, rbx
0x18003d5a7  mov     rax, [rax+88h]
0x18003d5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5b3  mov     [rsp+168h+var_BC], eax
0x18003d5ba  mov     rcx, [rsp+168h]; this
0x18003d5c2  lea     rdx, aFailedToGetMov; "Failed to get moves and dirties"
0x18003d5c9  mov     qword ptr [rsp+168h+var_148], rdx; int
0x18003d5ce  mov     r9d, eax; char *
0x18003d5d1  lea     r8, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003d5d8  mov     edx, 0D2h; void *
0x18003d5dd  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003d5e2  mov     r14d, [rsp+168h+var_C8]
0x18003d5ea  mov     rsi, [rsp+168h+var_88]
0x18003d5f2  mov     rax, [rbx]
0x18003d5f5  mov     rcx, rbx
0x18003d5f8  mov     rax, [rax+30h]
0x18003d5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d601  mov     rax, [rbx]
0x18003d604  mov     rcx, rbx
0x18003d607  mov     rax, [rax+38h]
0x18003d60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d610  mov     rax, [rbx]
0x18003d613  mov     rcx, rbx
0x18003d616  mov     rax, [rax+0B0h]
0x18003d61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d622  mov     edx, eax
0x18003d624  cmp     eax, 0Ah
0x18003d627  jz      short loc_18003D63A
0x18003d629  cmp     eax, 57h ; 'W'
0x18003d62c  jnz     loc_18003DDEB
0x18003d632  mov     r8d, 4
0x18003d638  jmp     short loc_18003D640
0x18003d63a  mov     r8d, 8
0x18003d640  mov     [rsp+168h+var_C0], r8d
0x18003d648  mov     rdx, rsi
0x18003d64b  add     r14, r14
0x18003d64e  lea     r9, [rsi+r14*8]
0x18003d652  mov     [rsp+168h+var_68], r9
0x18003d65a  cmp     rsi, r9
0x18003d65d  jz      loc_18003DC38
0x18003d663  mov     ecx, [rdx+0Ch]
0x18003d666  sub     ecx, [rdx+4]
0x18003d669  mov     eax, [rdx+8]
0x18003d66c  sub     eax, [rdx]
0x18003d66e  imul    ecx, eax
0x18003d671  mov     eax, r8d
0x18003d674  imul    eax, ecx
0x18003d677  add     ecx, r12d
0x18003d67a  test    eax, eax
0x18003d67c  cmovz   ecx, r12d
0x18003d680  mov     r12d, ecx
0x18003d683  add     rdx, 10h
0x18003d687  cmp     rdx, r9
0x18003d68a  jnz     short loc_18003D663
0x18003d68c  mov     [rsp+168h+var_C4], ecx
0x18003d693  test    ecx, ecx
0x18003d695  jz      loc_18003DC38
0x18003d69b  mov     edx, r8d
0x18003d69e  imul    edx, r12d
0x18003d6a2  add     edx, 0FFFh
0x18003d6a8  and     edx, 0FFFFF000h
0x18003d6ae  add     edx, 1000h; unsigned __int64
0x18003d6b4  mov     rcx, [r15+68h]; this
0x18003d6b8  call    ?AllocatePool@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(unsigned __int64)
0x18003d6bd  mov     r14, [r15+68h]
0x18003d6c1  lea     rax, [r15+58h]
0x18003d6c5  mov     [rsp+168h+var_70], rax
0x18003d6cd  mov     rax, [rax]
0x18003d6d0  mov     [rsp+168h+var_B8], rax
0x18003d6d8  mov     rax, [rbx]
0x18003d6db  mov     rcx, rbx
0x18003d6de  mov     rax, [rax+80h]
0x18003d6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6ea  mov     qword ptr [rsp+168h+FileTime.dwLowDateTime], rax
0x18003d6f2  mov     rcx, [rbx]
0x18003d6f5  mov     rax, [rcx+78h]
0x18003d6f9  mov     rcx, rbx
0x18003d6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d701  mov     dword ptr [rsp+168h+Size+4], eax
0x18003d708  mov     r8, rdi
0x18003d70b  mov     [rsp+168h+var_80], rdi
0x18003d713  mov     rdx, [r14+20h]
0x18003d717  mov     rcx, [r14+28h]
0x18003d71b  sub     rcx, rdx
0x18003d71e  cmp     rcx, 10h
0x18003d722  jb      short loc_18003D73B
0x18003d724  mov     r8, [r14+8]
0x18003d728  add     r8, rdx
0x18003d72b  mov     [rsp+168h+var_80], r8
0x18003d733  lea     rcx, [rdx+10h]
0x18003d737  mov     [r14+20h], rcx
0x18003d73b  mov     rcx, [rsp+168h]
0x18003d743  lea     rax, aUnableToEnsure_13; "Unable to ensure RDPGFX_START_FRAME_PDU"...
0x18003d74a  mov     [rsp+168h+var_140], rax
0x18003d74f  mov     qword ptr [rsp+168h+var_148], r8
0x18003d754  mov     r9d, 8007000Eh
0x18003d75a  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18003d761  mov     edx, 17Fh
0x18003d766  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003d76b  mov     dword ptr [rsp+168h+Size], edi
0x18003d772  lea     rcx, ?m_Lock@?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@0Vmutex@std@@A; std::mutex Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::m_Lock
0x18003d779  mov     qword ptr [rsp+168h+SystemTime.wYear], rcx
0x18003d781  call    mtx_do_lock
0x18003d786  test    eax, eax
0x18003d788  jnz     loc_18003DE21
0x18003d78e  cmp     cs:dword_1800C191C, 7FFFFFFFh
0x18003d798  jz      loc_18003DE2B
0x18003d79e  xor     edx, edx
0x18003d7a0  mov     ecx, cs:?g_FrameId@?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@0IA; uint Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::g_FrameId
0x18003d7a6  mov     eax, ecx
0x18003d7a8  or      r8d, 0FFFFFFFFh
0x18003d7ac  div     r8d
0x18003d7af  lea     r13d, [rcx+1]
0x18003d7b3  add     r13d, eax
0x18003d7b6  mov     cs:?g_FrameId@?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@0IA, r13d; uint Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::g_FrameId
0x18003d7bd  mov     dword ptr [rsp+168h+Size], r13d
0x18003d7c5  cmp     cs:qword_1800C1E30, 2000h
0x18003d7d0  jbe     short loc_18003D7E6
0x18003d7d2  lea     rcx, ?m_FrameLookup@?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@0V?$unordered_map@IUEgfxFrameIdMap@Protocol@Rdp@@U?$hash@I@std@@U?$equal_to@I@5@V?$allocator@U?$pair@$$CBIUEgfxFrameIdMap@Protocol@Rdp@@@std@@@5@@std@@A; std::unordered_map<uint,Rdp::Protocol::EgfxFrameIdMap> Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::m_FrameLookup
0x18003d7d9  call    ?clear@?$_Hash@V?$_Umap_traits@IUEgfxFrameIdMap@Protocol@Rdp@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUEgfxFrameIdMap@Protocol@Rdp@@@std@@@5@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<uint,Rdp::Protocol::EgfxFrameIdMap,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,Rdp::Protocol::EgfxFrameIdMap>>,0>>::clear(void)
0x18003d7de  mov     r13d, dword ptr [rsp+168h+Size]
0x18003d7e6  mov     rax, [rsp+168h+var_B8]
0x18003d7ee  movups  xmm6, xmmword ptr [rax+78h]
0x18003d7f2  lea     r8, [rsp+168h+Size]
0x18003d7fa  lea     rdx, [rsp+168h+var_B8]
0x18003d802  lea     rcx, ?m_FrameLookup@?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@0V?$unordered_map@IUEgfxFrameIdMap@Protocol@Rdp@@U?$hash@I@std@@U?$equal_to@I@5@V?$allocator@U?$pair@$$CBIUEgfxFrameIdMap@Protocol@Rdp@@@std@@@5@@std@@A; std::unordered_map<uint,Rdp::Protocol::EgfxFrameIdMap> Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::m_FrameLookup
0x18003d809  call    ??$_Try_emplace@AEBI$$V@?$_Hash@V?$_Umap_traits@IUEgfxFrameIdMap@Protocol@Rdp@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@std@@V?$allocator@U?$pair@$$CBIUEgfxFrameIdMap@Protocol@Rdp@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBIUEgfxFrameIdMap@Protocol@Rdp@@@std@@PEAX@std@@_N@1@AEBI@Z; std::_Hash<std::_Umap_traits<uint,Rdp::Protocol::EgfxFrameIdMap,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,Rdp::Protocol::EgfxFrameIdMap>>,0>>::_Try_emplace<uint const &,>(uint const &)
0x18003d80e  mov     rax, [rax]
0x18003d811  mov     [rax+14h], r13d
0x18003d815  mov     ecx, dword ptr [rsp+168h+Size+4]
0x18003d81c  mov     [rax+18h], ecx
0x18003d81f  movdqu  xmmword ptr [rax+1Ch], xmm6
0x18003d824  mov     eax, dword ptr [rsp+168h+Size]
0x18003d82b  mov     [r14+0C00h], eax
0x18003d832  mov     eax, cs:dword_1800C191C
0x18003d838  sub     eax, 1
0x18003d83b  mov     cs:dword_1800C191C, eax
0x18003d841  jnz     short loc_18003D85A
0x18003d843  mov     cs:dword_1800C1918, 0FFFFFFFFh
0x18003d84d  lea     rcx, stru_1800C18E0; SRWLock
0x18003d854  call    cs:__imp_ReleaseSRWLockExclusive
0x18003d85a  mov     r14, [rsp+168h+var_80]
0x18003d862  mov     dword ptr [r14], 0Bh
0x18003d869  mov     dword ptr [r14+4], 10h
0x18003d871  xorps   xmm0, xmm0
0x18003d874  movups  xmmword ptr [rsp+168h+SystemTime.wYear], xmm0
0x18003d87c  mov     eax, [rsp+168h+FileTime.dwHighDateTime]
0x18003d883  mov     rcx, qword ptr [rsp+168h+FileTime.dwLowDateTime]
0x18003d88b  mov     [rsp+168h+FileTime.dwLowDateTime], ecx
0x18003d892  mov     [rsp+168h+FileTime.dwHighDateTime], eax
0x18003d899  lea     rdx, [rsp+168h+SystemTime]; lpSystemTime
0x18003d8a1  lea     rcx, [rsp+168h+FileTime]; lpFileTime
0x18003d8a9  call    cs:__imp_FileTimeToSystemTime
0x18003d8af  movzx   ecx, [rsp+168h+SystemTime.wHour]
0x18003d8b7  shl     ecx, 6
0x18003d8ba  movzx   eax, [rsp+168h+SystemTime.wMinute]
0x18003d8c2  or      ecx, eax
0x18003d8c4  shl     ecx, 6
0x18003d8c7  movzx   eax, [rsp+168h+SystemTime.wSecond]
0x18003d8cf  or      ecx, eax
0x18003d8d1  shl     ecx, 0Ah
0x18003d8d4  movzx   eax, [rsp+168h+SystemTime.wMilliseconds]
0x18003d8dc  or      ecx, eax
0x18003d8de  mov     [r14+8], ecx
0x18003d8e2  mov     eax, dword ptr [rsp+168h+Size]
0x18003d8e9  mov     [r14+0Ch], eax
0x18003d8ed  cmp     rsi, [rsp+168h+var_68]
0x18003d8f5  jz      loc_18003DB8C
0x18003d8fb  mov     ecx, [rsi+0Ch]
0x18003d8fe  sub     ecx, [rsi+4]
0x18003d901  mov     dword ptr [rsp+168h+var_B8], ecx
0x18003d908  mov     r14d, [rsi+8]
0x18003d90c  sub     r14d, [rsi]
0x18003d90f  imul    r14d, [rsp+168h+var_C0]
0x18003d918  mov     eax, r14d
0x18003d91b  imul    eax, ecx
0x18003d91e  mov     dword ptr [rsp+168h+Size], eax
0x18003d925  test    eax, eax
0x18003d927  jz      loc_18003DACB
0x18003d92d  mov     rcx, [r15+68h]
0x18003d931  mov     rax, [r15+58h]
0x18003d935  mov     eax, [rax+88h]
0x18003d93b  mov     dword ptr [rsp+168h+Size+4], eax
0x18003d942  mov     r13, rdi
0x18003d945  mov     rdx, [rcx+20h]
0x18003d949  mov     rax, [rcx+28h]
0x18003d94d  sub     rax, rdx
0x18003d950  cmp     rax, 19h
0x18003d954  jb      short loc_18003D965
0x18003d956  mov     r13, [rcx+8]
0x18003d95a  add     r13, rdx
0x18003d95d  lea     rax, [rdx+19h]
0x18003d961  mov     [rcx+20h], rax
0x18003d965  mov     rcx, [rsp+168h]
0x18003d96d  mov     dword ptr [rsp+168h+var_138], 19h
0x18003d975  lea     rax, aUnableToEnsure_7; "Unable to ensure RDPGFX_WIRE_TO_SURFACE"...
0x18003d97c  mov     [rsp+168h+var_140], rax
0x18003d981  mov     qword ptr [rsp+168h+var_148], r13
0x18003d986  mov     r9d, 8007000Eh
0x18003d98c  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18003d993  mov     edx, 1BDh
0x18003d998  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003d99d  mov     dword ptr [r13+0], 1
0x18003d9a5  mov     ecx, dword ptr [rsp+168h+Size]
0x18003d9ac  lea     eax, [rcx+19h]
0x18003d9af  mov     [r13+4], eax
0x18003d9b3  mov     eax, dword ptr [rsp+168h+Size+4]
0x18003d9ba  mov     [r13+8], ax
0x18003d9bf  mov     [r13+0Ah], di
0x18003d9c4  mov     byte ptr [r13+0Ch], 21h ; '!'
0x18003d9c9  movzx   eax, word ptr [rsi]
0x18003d9cc  mov     [r13+0Dh], ax
0x18003d9d1  movzx   eax, word ptr [rsi+4]
0x18003d9d5  mov     [r13+0Fh], ax
0x18003d9da  movzx   eax, word ptr [rsi+8]
0x18003d9de  mov     [r13+11h], ax
0x18003d9e3  movzx   eax, word ptr [rsi+0Ch]
0x18003d9e7  mov     [r13+13h], ax
0x18003d9ec  mov     [r13+15h], ecx
0x18003d9f0  mov     rax, [rbx]
0x18003d9f3  mov     rcx, rbx
0x18003d9f6  mov     rax, [rax+98h]
0x18003d9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da02  imul    eax, [rsi+4]
0x18003da06  mov     r13d, [rsp+168h+var_C0]
0x18003da0e  imul    r13d, [rsi]
0x18003da12  add     r13d, eax
0x18003da15  mov     rax, [rbx]
0x18003da18  mov     rcx, rbx
0x18003da1b  mov     rax, [rax+0B8h]
0x18003da22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da27  add     r13, rax
0x18003da2a  mov     rax, [rbx]
0x18003da2d  mov     rcx, rbx
0x18003da30  mov     rax, [rax+98h]
0x18003da37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da3c  cmp     eax, r14d
0x18003da3f  jnz     loc_18003DAD4
0x18003da45  mov     rcx, [r15+68h]
0x18003da49  mov     rdx, rdi
0x18003da4c  mov     qword ptr [rsp+168h+FileTime.dwLowDateTime], rdx
0x18003da54  mov     r8, [rcx+20h]
0x18003da58  mov     r14d, dword ptr [rsp+168h+Size]
0x18003da60  mov     rax, [rcx+28h]
0x18003da64  sub     rax, r8
0x18003da67  cmp     rax, r14
0x18003da6a  jb      short loc_18003DA83
0x18003da6c  mov     rdx, [rcx+8]
0x18003da70  add     rdx, r8
0x18003da73  mov     qword ptr [rsp+168h+FileTime.dwLowDateTime], rdx
0x18003da7b  lea     rax, [r14+r8]
0x18003da7f  mov     [rcx+20h], rax
0x18003da83  mov     rcx, [rsp+168h]
0x18003da8b  mov     [rsp+168h+var_138], r14
  ... truncated ...
```
