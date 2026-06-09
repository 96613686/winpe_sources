# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::SetRenderDevice(ID3D11Device *)

- ea: `0x18004a030`
- end: `0x18004a6e0`
- name: `?SetRenderDevice@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@UEAAJPEAUID3D11Device@@@Z`
- size: `1712`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180044900`

## callees

- `0x180001008`
- `0x18000406c`
- `0x180006580`
- `0x18000e848`
- `0x18000ec04`
- `0x1800103c0`
- `0x180010bc8`
- `0x180047f44`
- `0x18004a030`
- `0x180050758`
- `0x1800532c8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a546`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a546`
- `d3d11!D3D11CreateDevice` at `0x18004a2ae`
- `d3d11!D3D11CreateDevice` at `0x18004a2ae`

## string_xrefs

- `0x18004a673`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18004a688`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18004a6b2`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18004a2bc`: `D3D11CreateDevice failed for Encoder Device`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::SetRenderDevice(
        __int64 a1,
        __int64 (***a2)(void))
{
  int v4; // eax
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, IDXGIAdapter **); // rsi
  IDXGIAdapter *v11; // rcx
  int v12; // eax
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rdx
  ID3D11Device *v16; // rcx
  unsigned int v17; // eax
  int v18; // eax
  int v19; // r8d
  const char *v20; // r9
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  Rdp::Avenc::Ic3::CDsStreamSource *v24; // rcx
  Rdp::Avenc::Ic3::CVideoSourceProvider *v25; // rcx
  int v26; // r9d
  int v27; // r8d
  int v28; // r9d
  __int64 v30; // rdx
  __int64 result; // rax
  int pFeatureLevels; // [rsp+20h] [rbp-1C8h]
  int pFeatureLevelsa; // [rsp+20h] [rbp-1C8h]
  const char *FeatureLevels; // [rsp+28h] [rbp-1C0h]
  __int64 v35; // [rsp+60h] [rbp-188h] BYREF
  int v36; // [rsp+68h] [rbp-180h] BYREF
  int v37; // [rsp+6Ch] [rbp-17Ch] BYREF
  ID3D11Device *ppDevice; // [rsp+70h] [rbp-178h] BYREF
  const char *v39; // [rsp+78h] [rbp-170h] BYREF
  const char *v40; // [rsp+80h] [rbp-168h] BYREF
  const char *v41; // [rsp+88h] [rbp-160h] BYREF
  __int64 v42; // [rsp+90h] [rbp-158h]
  IDXGIAdapter *pAdapter; // [rsp+98h] [rbp-150h] BYREF
  _QWORD v44[2]; // [rsp+A0h] [rbp-148h] BYREF
  _BYTE v45[128]; // [rsp+B0h] [rbp-138h] BYREF
  _BYTE v46[128]; // [rsp+130h] [rbp-B8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v35 = 0;
  try
  {
    v4 = (**a2)();
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v4,
        pFeatureLevels);
    v5 = v35;
    v6 = 0;
    v35 = 0;
    v7 = *(_QWORD *)(a1 + 104);
    *(_QWORD *)(a1 + 104) = v5;
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      v6 = v35;
    }
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    pAdapter = 0;
    v35 = 0;
    v8 = ((__int64 (__fastcall *)(__int64 (***)(void), GUID *, __int64 *))**a2)(
           a2,
           &GUID_05008617_fbfd_4051_a790_144884b4f6a9,
           &v35);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v8,
        pFeatureLevels);
    v9 = v35;
    v10 = *(__int64 (__fastcall **)(__int64, IDXGIAdapter **))(*(_QWORD *)v35 + 56LL);
    v11 = pAdapter;
    pAdapter = 0;
    if ( v11 )
      ((void (__fastcall *)(IDXGIAdapter *, struct IDXGIAdapterVtbl *))v11->lpVtbl->Release)(v11, v11->lpVtbl);
    v12 = v10(v9, &pAdapter);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x156,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
        (const char *)(unsigned int)v12,
        pFeatureLevels);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    ppDevice = 0;
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v15 = *(_QWORD *)(a1 + 96);
      v44[0] = v15 + 112;
      v36 = *(_DWORD *)(*(_QWORD *)(v15 + 104) + 136LL);
      v37 = *(_DWORD *)(v15 + 128);
      v39 = "Creating encoder device";
      v40 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncP"
            "rocessor>::SetRenderDevice";
      LODWORD(v35) = 351;
      v41 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&dword_1800B1124,
        v13,
        v14,
        (__int64)&v41,
        (__int64)&v35,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)v44);
    }
    v16 = ppDevice;
    ppDevice = 0;
    if ( v16 )
      ((void (__fastcall *)(ID3D11Device *))v16->lpVtbl->Release)(v16);
    v17 = D3D11CreateDevice(pAdapter, D3D_DRIVER_TYPE_UNKNOWN, 0, 0x800u, 0, 0, 7u, &ppDevice, 0, 0);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x16C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
      (const char *)v17,
      (int)"D3D11CreateDevice failed for Encoder Device",
      FeatureLevels);
    v35 = 0;
    v18 = ((__int64 (__fastcall *)(ID3D11Device *, GUID *, __int64 *))ppDevice->lpVtbl->QueryInterface)(
            ppDevice,
            &GUID_8ffde202_a0e7_45df_9e01_e837801b5ea0,
            &v35);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v18,
        pFeatureLevelsa);
    v21 = v35;
    v22 = 0;
    v35 = 0;
    v23 = *(_QWORD *)(a1 + 112);
    *(_QWORD *)(a1 + 112) = v21;
    if ( v23 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v22 = v35;
    }
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v24 = *(Rdp::Avenc::Ic3::CDsStreamSource **)(a1 + 128);
    if ( v24 )
    {
      Rdp::Avenc::Ic3::CDsStreamSource::SetEncodeDevice(v24, ppDevice);
    }
    else
    {
      v25 = *(Rdp::Avenc::Ic3::CVideoSourceProvider **)(a1 + 136);
      if ( v25 )
        Rdp::Avenc::Ic3::CVideoSourceProvider::NotifyD3D11Device(v25, ppDevice);
    }
    if ( *(_QWORD *)(a1 + 360) )
    {
      v44[0] = a1 + 16;
      if ( (unsigned int)mtx_do_lock(a1 + 16) )
        std::_Throw_Cpp_error(5);
      if ( *(_DWORD *)(a1 + 92) == 0x7FFFFFFF )
      {
        *(_DWORD *)(a1 + 92) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      v41 = v45;
      v42 = 4;
      if ( (int)Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CreateSharedResources(
                  a1 - 80,
                  (__int64 *)&v41,
                  0,
                  v26) >= 0 )
      {
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v41 = "OnAllocateSharedResources for textures";
          v40 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAs"
                "yncProcessor>::SetRenderDevice";
          LODWORD(v35) = 393;
          v39 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&byte_1800B1067,
            v27,
            v28,
            (__int64)&v39,
            (__int64)&v35,
            (__int64)&v40,
            (__int64)&v41);
        }
        (*(void (__fastcall **)(_QWORD, _BYTE *, __int64))(**(_QWORD **)(a1 + 360) + 24LL))(
          *(_QWORD *)(a1 + 360),
          v45,
          4);
      }
      v41 = v46;
      v42 = 4;
      if ( (int)Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CreateSharedResources(
                  a1 - 80,
                  (__int64 *)&v41,
                  1,
                  v28) >= 0 )
      {
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v41 = "OnAllocateSharedResources for fences";
          v40 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAs"
                "yncProcessor>::SetRenderDevice";
          LODWORD(v35) = 405;
          v39 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&word_1800B10A6,
            v19,
            (_DWORD)v20,
            (__int64)&v39,
            (__int64)&v35,
            (__int64)&v40,
            (__int64)&v41);
        }
        (*(void (__fastcall **)(_QWORD, _BYTE *, __int64))(**(_QWORD **)(a1 + 360) + 24LL))(
          *(_QWORD *)(a1 + 360),
          v46,
          4);
      }
      if ( (*(_DWORD *)(a1 + 92))-- == 1 )
      {
        *(_DWORD *)(a1 + 88) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
      }
    }
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v30 = *(_QWORD *)(a1 + 96);
      v41 = (const char *)(v30 + 112);
      LODWORD(v35) = *(_DWORD *)(*(_QWORD *)(v30 + 104) + 136LL);
      v37 = *(_DWORD *)(v30 + 128);
      v40 = "Creating encoder device - done";
      v39 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::ICpuFrameAsyncP"
            "rocessor>::SetRenderDevice";
      v36 = 417;
      v44[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800B0F82,
        v19,
        (_DWORD)v20,
        (__int64)v44,
        (__int64)&v36,
        (__int64)&v39,
        (__int64)&v40,
        (__int64)&v37,
        (__int64)&v35,
        (__int64)&v41);
    }
    if ( ppDevice )
      ((void (__fastcall *)(ID3D11Device *))ppDevice->lpVtbl->Release)(ppDevice);
    if ( pAdapter )
      ((void (__fastcall *)(IDXGIAdapter *))pAdapter->lpVtbl->Release)(pAdapter);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1A6,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x18004a030  mov     [rsp+arg_10], rbx
0x18004a035  mov     [rsp+arg_18], rsi
0x18004a03a  push    rdi
0x18004a03b  push    r12
0x18004a03d  push    r13
0x18004a03f  push    r14
0x18004a041  push    r15
0x18004a043  sub     rsp, 1C0h
0x18004a04a  mov     rax, cs:__security_cookie
0x18004a051  xor     rax, rsp
0x18004a054  mov     [rsp+1E8h+var_38], rax
0x18004a05c  mov     rbx, rdx
0x18004a05f  mov     rdi, rcx
0x18004a062  xor     r12d, r12d
0x18004a065  mov     [rsp+1E8h+var_188], r12
0x18004a06a  mov     rax, [rdx]
0x18004a06d  lea     r8, [rsp+1E8h+var_188]
0x18004a072  lea     rdx, _GUID_8ffde202_a0e7_45df_9e01_e837801b5ea0
0x18004a079  mov     rcx, rbx
0x18004a07c  mov     rax, [rax]
0x18004a07f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a084  mov     rcx, [rsp+1E8h]; this
0x18004a08c  test    eax, eax
0x18004a08e  js      loc_18004A670
0x18004a094  mov     rax, [rsp+1E8h+var_188]
0x18004a099  mov     rcx, r12
0x18004a09c  mov     [rsp+1E8h+var_188], rcx
0x18004a0a1  mov     rdx, [rdi+68h]
0x18004a0a5  mov     [rdi+68h], rax
0x18004a0a9  test    rdx, rdx
0x18004a0ac  jz      short loc_18004A0C2
0x18004a0ae  mov     rax, [rdx]
0x18004a0b1  mov     rcx, rdx
0x18004a0b4  mov     rax, [rax+10h]
0x18004a0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0bd  mov     rcx, [rsp+1E8h+var_188]
0x18004a0c2  test    rcx, rcx
0x18004a0c5  jz      short loc_18004A0D4
0x18004a0c7  mov     rax, [rcx]
0x18004a0ca  mov     rax, [rax+10h]
0x18004a0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0d3  nop
0x18004a0d4  mov     [rsp+1E8h+pAdapter], r12
0x18004a0dc  mov     [rsp+1E8h+var_188], r12
0x18004a0e1  mov     rax, [rbx]
0x18004a0e4  lea     r8, [rsp+1E8h+var_188]
0x18004a0e9  lea     rdx, _GUID_05008617_fbfd_4051_a790_144884b4f6a9
0x18004a0f0  mov     rcx, rbx
0x18004a0f3  mov     rax, [rax]
0x18004a0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0fb  mov     rcx, [rsp+1E8h]; this
0x18004a103  test    eax, eax
0x18004a105  js      loc_18004A685
0x18004a10b  mov     rbx, [rsp+1E8h+var_188]
0x18004a110  mov     rax, [rbx]
0x18004a113  mov     rsi, [rax+38h]
0x18004a117  mov     rcx, [rsp+1E8h+pAdapter]
0x18004a11f  mov     [rsp+1E8h+pAdapter], r12
0x18004a127  test    rcx, rcx
0x18004a12a  jz      short loc_18004A139
0x18004a12c  mov     rdx, [rcx]
0x18004a12f  mov     rax, [rdx+10h]
0x18004a133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a138  nop
0x18004a139  lea     rdx, [rsp+1E8h+pAdapter]
0x18004a141  mov     rcx, rbx
0x18004a144  mov     rax, rsi
0x18004a147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a14c  mov     rcx, [rsp+1E8h]; this
0x18004a154  test    eax, eax
0x18004a156  js      loc_18004A69A
0x18004a15c  mov     rcx, [rsp+1E8h+var_188]
0x18004a161  test    rcx, rcx
0x18004a164  jz      short loc_18004A173
0x18004a166  mov     rax, [rcx]
0x18004a169  mov     rax, [rax+10h]
0x18004a16d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a172  nop
0x18004a173  mov     [rsp+1E8h+var_178], r12
0x18004a178  mov     eax, cs:dword_1800C1058
0x18004a17e  mov     r13d, 4
0x18004a184  cmp     eax, r13d
0x18004a187  jbe     loc_18004A24B
0x18004a18d  mov     rdx, [rdi+60h]
0x18004a191  lea     rax, [rdx+70h]
0x18004a195  mov     [rsp+1E8h+var_148], rax
0x18004a19d  mov     rax, [rdx+68h]
0x18004a1a1  mov     ecx, [rax+88h]
0x18004a1a7  mov     [rsp+1E8h+var_180], ecx
0x18004a1ab  mov     eax, [rdx+80h]
0x18004a1b1  mov     [rsp+1E8h+var_17C], eax
0x18004a1b5  lea     rax, aCreatingEncode_0; "Creating encoder device"
0x18004a1bc  mov     [rsp+1E8h+var_170], rax
0x18004a1c1  lea     r15, aRdpAvencIc3Cic_16; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004a1c8  mov     [rsp+1E8h+var_168], r15
0x18004a1d0  mov     dword ptr [rsp+1E8h+var_188], 15Fh
0x18004a1d8  lea     rsi, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004a1df  mov     [rsp+1E8h+var_160], rsi
0x18004a1e7  lea     rax, [rsp+1E8h+var_148]
0x18004a1ef  mov     [rsp+1E8h+var_198], rax
0x18004a1f4  lea     rax, [rsp+1E8h+var_180]
0x18004a1f9  mov     [rsp+1E8h+ppImmediateContext], rax
0x18004a1fe  lea     rax, [rsp+1E8h+var_17C]
0x18004a203  mov     [rsp+1E8h+pFeatureLevel], rax
0x18004a208  lea     rax, [rsp+1E8h+var_170]
0x18004a20d  mov     [rsp+1E8h+ppDevice], rax
0x18004a212  lea     rax, [rsp+1E8h+var_168]
0x18004a21a  mov     qword ptr [rsp+1E8h+SDKVersion], rax
0x18004a21f  lea     rax, [rsp+1E8h+var_188]
0x18004a224  mov     qword ptr [rsp+1E8h+FeatureLevels], rax
0x18004a229  lea     rax, [rsp+1E8h+var_160]
0x18004a231  mov     [rsp+1E8h+pFeatureLevels], rax
0x18004a236  lea     rdx, dword_1800B1124
0x18004a23d  lea     rcx, dword_1800C1058
0x18004a244  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004a249  jmp     short loc_18004A259
0x18004a24b  lea     rsi, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004a252  lea     r15, aRdpAvencIc3Cic_16; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004a259  mov     rcx, [rsp+1E8h+var_178]
0x18004a25e  mov     [rsp+1E8h+var_178], r12
0x18004a263  test    rcx, rcx
0x18004a266  jz      short loc_18004A275
0x18004a268  mov     rax, [rcx]
0x18004a26b  mov     rax, [rax+10h]
0x18004a26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a274  nop
0x18004a275  mov     [rsp+1E8h+ppImmediateContext], r12; ppImmediateContext
0x18004a27a  mov     [rsp+1E8h+pFeatureLevel], r12; pFeatureLevel
0x18004a27f  lea     rax, [rsp+1E8h+var_178]
0x18004a284  mov     [rsp+1E8h+ppDevice], rax; ppDevice
0x18004a289  mov     [rsp+1E8h+SDKVersion], 7; SDKVersion
0x18004a291  mov     [rsp+1E8h+FeatureLevels], r12d; char *
0x18004a296  mov     [rsp+1E8h+pFeatureLevels], r12; pFeatureLevels
0x18004a29b  mov     r9d, 800h; Flags
0x18004a2a1  xor     r8d, r8d; Software
0x18004a2a4  xor     edx, edx; DriverType
0x18004a2a6  mov     rcx, [rsp+1E8h+pAdapter]; pAdapter
0x18004a2ae  call    cs:__imp_D3D11CreateDevice
0x18004a2b4  mov     rcx, [rsp+1E8h]; this
0x18004a2bc  lea     r8, aD3d11createdev; "D3D11CreateDevice failed for Encoder De"...
0x18004a2c3  mov     [rsp+1E8h+pFeatureLevels], r8; int
0x18004a2c8  mov     r9d, eax; char *
0x18004a2cb  mov     r8, rsi; unsigned int
0x18004a2ce  mov     edx, 16Ch; void *
0x18004a2d3  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004a2d8  mov     rcx, [rsp+1E8h+var_178]
0x18004a2dd  mov     [rsp+1E8h+var_188], r12
0x18004a2e2  mov     rax, [rcx]
0x18004a2e5  lea     r8, [rsp+1E8h+var_188]
0x18004a2ea  lea     rdx, _GUID_8ffde202_a0e7_45df_9e01_e837801b5ea0
0x18004a2f1  mov     rax, [rax]
0x18004a2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a2f9  mov     rcx, [rsp+1E8h]; this
0x18004a301  test    eax, eax
0x18004a303  js      loc_18004A6AF
0x18004a309  mov     rax, [rsp+1E8h+var_188]
0x18004a30e  mov     rcx, r12
0x18004a311  mov     [rsp+1E8h+var_188], rcx
0x18004a316  mov     rdx, [rdi+70h]
0x18004a31a  mov     [rdi+70h], rax
0x18004a31e  test    rdx, rdx
0x18004a321  jz      short loc_18004A337
0x18004a323  mov     rax, [rdx]
0x18004a326  mov     rcx, rdx
0x18004a329  mov     rax, [rax+10h]
0x18004a32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a332  mov     rcx, [rsp+1E8h+var_188]
0x18004a337  test    rcx, rcx
0x18004a33a  jz      short loc_18004A349
0x18004a33c  mov     rax, [rcx]
0x18004a33f  mov     rax, [rax+10h]
0x18004a343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a348  nop
0x18004a349  mov     rcx, [rdi+80h]; this
0x18004a350  test    rcx, rcx
0x18004a353  jz      short loc_18004A361
0x18004a355  mov     rdx, [rsp+1E8h+var_178]; struct ID3D11Device *
0x18004a35a  call    ?SetEncodeDevice@CDsStreamSource@Ic3@Avenc@Rdp@@QEAAJPEAUID3D11Device@@@Z; Rdp::Avenc::Ic3::CDsStreamSource::SetEncodeDevice(ID3D11Device *)
0x18004a35f  jmp     short loc_18004A377
0x18004a361  mov     rcx, [rdi+88h]; this
0x18004a368  test    rcx, rcx
0x18004a36b  jz      short loc_18004A377
0x18004a36d  mov     rdx, [rsp+1E8h+var_178]; struct ID3D11Device *
0x18004a372  call    ?NotifyD3D11Device@CVideoSourceProvider@Ic3@Avenc@Rdp@@QEAAXPEAUID3D11Device@@@Z; Rdp::Avenc::Ic3::CVideoSourceProvider::NotifyD3D11Device(ID3D11Device *)
0x18004a377  cmp     [rdi+168h], r12
0x18004a37e  jz      loc_18004A54C
0x18004a384  lea     rbx, [rdi+10h]
0x18004a388  mov     [rsp+1E8h+var_148], rbx
0x18004a390  mov     rcx, rbx
0x18004a393  call    mtx_do_lock
0x18004a398  test    eax, eax
0x18004a39a  jnz     loc_18004A6C3
0x18004a3a0  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18004a3a7  jz      loc_18004A6CD
0x18004a3ad  lea     rax, [rsp+1E8h+var_138]
0x18004a3b5  mov     [rsp+1E8h+var_160], rax
0x18004a3bd  mov     [rsp+1E8h+var_158], r13
0x18004a3c5  xor     r8d, r8d
0x18004a3c8  lea     rdx, [rsp+1E8h+var_160]
0x18004a3d0  lea     rcx, [rdi-50h]
0x18004a3d4  call    ?CreateSharedResources@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAJ$$QEAV?$span@UAVENC_SHARED_RESOURCE@Avenc@Rdp@@$0?0@std@@W4AVENC_RESOURCE_TYPE@34@@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CreateSharedResources(std::span<Rdp::Avenc::AVENC_SHARED_RESOURCE,-1> &&,Rdp::Avenc::AVENC_RESOURCE_TYPE)
0x18004a3d9  test    eax, eax
0x18004a3db  js      loc_18004A46F
0x18004a3e1  mov     eax, cs:dword_1800C1058
0x18004a3e7  cmp     eax, 5
0x18004a3ea  jbe     short loc_18004A451
0x18004a3ec  lea     rax, aOnallocateshar; "OnAllocateSharedResources for textures"
0x18004a3f3  mov     [rsp+1E8h+var_160], rax
0x18004a3fb  mov     [rsp+1E8h+var_168], r15
0x18004a403  mov     dword ptr [rsp+1E8h+var_188], 189h
0x18004a40b  mov     [rsp+1E8h+var_170], rsi
0x18004a410  lea     rax, [rsp+1E8h+var_160]
0x18004a418  mov     [rsp+1E8h+ppDevice], rax
0x18004a41d  lea     rax, [rsp+1E8h+var_168]
0x18004a425  mov     qword ptr [rsp+1E8h+SDKVersion], rax
0x18004a42a  lea     rax, [rsp+1E8h+var_188]
0x18004a42f  mov     qword ptr [rsp+1E8h+FeatureLevels], rax
0x18004a434  lea     rax, [rsp+1E8h+var_170]
0x18004a439  mov     [rsp+1E8h+pFeatureLevels], rax
0x18004a43e  lea     rdx, byte_1800B1067
0x18004a445  lea     rcx, dword_1800C1058
0x18004a44c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18004a451  mov     rcx, [rdi+168h]
0x18004a458  mov     rax, [rcx]
0x18004a45b  mov     r8d, r13d
0x18004a45e  lea     rdx, [rsp+1E8h+var_138]
0x18004a466  mov     rax, [rax+18h]
0x18004a46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a46f  lea     rax, [rsp+1E8h+var_B8]
0x18004a477  mov     [rsp+1E8h+var_160], rax
0x18004a47f  mov     [rsp+1E8h+var_158], r13
0x18004a487  mov     r8d, 1
0x18004a48d  lea     rdx, [rsp+1E8h+var_160]
0x18004a495  lea     rcx, [rdi-50h]
0x18004a499  call    ?CreateSharedResources@?$CIc3FrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UICpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAJ$$QEAV?$span@UAVENC_SHARED_RESOURCE@Avenc@Rdp@@$0?0@std@@W4AVENC_RESOURCE_TYPE@34@@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::ICpuFrameAsyncProcessor>::CreateSharedResources(std::span<Rdp::Avenc::AVENC_SHARED_RESOURCE,-1> &&,Rdp::Avenc::AVENC_RESOURCE_TYPE)
0x18004a49e  test    eax, eax
0x18004a4a0  js      loc_18004A535
0x18004a4a6  mov     eax, cs:dword_1800C1058
0x18004a4ac  cmp     eax, 5
0x18004a4af  jbe     short loc_18004A516
0x18004a4b1  lea     rax, aOnallocateshar_0; "OnAllocateSharedResources for fences"
0x18004a4b8  mov     [rsp+1E8h+var_160], rax
0x18004a4c0  mov     [rsp+1E8h+var_168], r15
0x18004a4c8  mov     dword ptr [rsp+1E8h+var_188], 195h
0x18004a4d0  mov     [rsp+1E8h+var_170], rsi
0x18004a4d5  lea     rax, [rsp+1E8h+var_160]
0x18004a4dd  mov     [rsp+1E8h+ppDevice], rax
0x18004a4e2  lea     rax, [rsp+1E8h+var_168]
0x18004a4ea  mov     qword ptr [rsp+1E8h+SDKVersion], rax
0x18004a4ef  lea     rax, [rsp+1E8h+var_188]
0x18004a4f4  mov     qword ptr [rsp+1E8h+FeatureLevels], rax
0x18004a4f9  lea     rax, [rsp+1E8h+var_170]
0x18004a4fe  mov     [rsp+1E8h+pFeatureLevels], rax
0x18004a503  lea     rdx, word_1800B10A6
0x18004a50a  lea     rcx, dword_1800C1058
0x18004a511  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18004a516  mov     rcx, [rdi+168h]
0x18004a51d  mov     rax, [rcx]
0x18004a520  mov     r8d, r13d
0x18004a523  lea     rdx, [rsp+1E8h+var_B8]
0x18004a52b  mov     rax, [rax+18h]
0x18004a52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a534  nop
0x18004a535  sub     dword ptr [rbx+4Ch], 1
0x18004a539  jnz     short loc_18004A54C
0x18004a53b  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x18004a542  lea     rcx, [rbx+10h]; SRWLock
0x18004a546  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a54c  mov     eax, cs:dword_1800C1058
0x18004a552  cmp     eax, 5
0x18004a555  jbe     loc_18004A60A
0x18004a55b  mov     rdx, [rdi+60h]
0x18004a55f  lea     rax, [rdx+70h]
0x18004a563  mov     [rsp+1E8h+var_160], rax
0x18004a56b  mov     rax, [rdx+68h]
0x18004a56f  mov     ecx, [rax+88h]
0x18004a575  mov     dword ptr [rsp+1E8h+var_188], ecx
0x18004a579  mov     eax, [rdx+80h]
0x18004a57f  mov     [rsp+1E8h+var_17C], eax
0x18004a583  lea     rax, aCreatingEncode; "Creating encoder device - done"
0x18004a58a  mov     [rsp+1E8h+var_168], rax
0x18004a592  mov     [rsp+1E8h+var_170], r15
0x18004a597  mov     [rsp+1E8h+var_180], 1A1h
0x18004a59f  mov     [rsp+1E8h+var_148], rsi
0x18004a5a7  lea     rax, [rsp+1E8h+var_160]
0x18004a5af  mov     [rsp+1E8h+var_198], rax
0x18004a5b4  lea     rax, [rsp+1E8h+var_188]
0x18004a5b9  mov     [rsp+1E8h+ppImmediateContext], rax
0x18004a5be  lea     rax, [rsp+1E8h+var_17C]
0x18004a5c3  mov     [rsp+1E8h+pFeatureLevel], rax
0x18004a5c8  lea     rax, [rsp+1E8h+var_168]
0x18004a5d0  mov     [rsp+1E8h+ppDevice], rax
0x18004a5d5  lea     rax, [rsp+1E8h+var_170]
0x18004a5da  mov     qword ptr [rsp+1E8h+SDKVersion], rax
0x18004a5df  lea     rax, [rsp+1E8h+var_180]
0x18004a5e4  mov     qword ptr [rsp+1E8h+FeatureLevels], rax
0x18004a5e9  lea     rax, [rsp+1E8h+var_148]
0x18004a5f1  mov     [rsp+1E8h+pFeatureLevels], rax
0x18004a5f6  lea     rdx, word_1800B0F82
0x18004a5fd  lea     rcx, dword_1800C1058
  ... truncated ...
```
