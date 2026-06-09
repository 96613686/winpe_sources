# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::SetRenderDevice(ID3D11Device *)

- ea: `0x18004a6f0`
- end: `0x18004ada0`
- name: `?SetRenderDevice@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@UEAAJPEAUID3D11Device@@@Z`
- size: `1712`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180044910`

## callees

- `0x180001008`
- `0x18000406c`
- `0x180006580`
- `0x18000e848`
- `0x18000ec04`
- `0x1800103c0`
- `0x180010bc8`
- `0x180048738`
- `0x18004a6f0`
- `0x180050758`
- `0x1800532c8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ac06`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004ac06`
- `d3d11!D3D11CreateDevice` at `0x18004a96e`
- `d3d11!D3D11CreateDevice` at `0x18004a96e`

## string_xrefs

- `0x18004ad33`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18004ad48`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18004ad72`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18004a97c`: `D3D11CreateDevice failed for Encoder Device`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::SetRenderDevice(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *))
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
  int v20; // r9d
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rdx
  Rdp::Avenc::Ic3::CDsStreamSource *v24; // rcx
  Rdp::Avenc::Ic3::CVideoSourceProvider *v25; // rcx
  int v26; // r9d
  int v27; // r8d
  int v28; // r9d
  __int64 v30; // rdx
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
  v4 = (**a2)(a2, &GUID_8ffde202_a0e7_45df_9e01_e837801b5ea0, &v35);
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
  v8 = (**a2)(a2, &GUID_05008617_fbfd_4051_a790_144884b4f6a9, &v35);
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
    v40 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncPro"
          "cessor>::SetRenderDevice";
    LODWORD(v35) = 351;
    v41 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&word_1800B15EE,
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
    if ( (int)Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CreateSharedResources(
                a1 - 80,
                (__int64 *)&v41,
                0,
                v26) >= 0 )
    {
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v41 = "OnAllocateSharedResources for textures";
        v40 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyn"
              "cProcessor>::SetRenderDevice";
        LODWORD(v35) = 393;
        v39 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&byte_1800B15AF,
          v27,
          v28,
          (__int64)&v39,
          (__int64)&v35,
          (__int64)&v40,
          (__int64)&v41);
      }
      (*(void (__fastcall **)(_QWORD, _BYTE *, __int64))(**(_QWORD **)(a1 + 360) + 24LL))(*(_QWORD *)(a1 + 360), v45, 4);
    }
    v41 = v46;
    v42 = 4;
    if ( (int)Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CreateSharedResources(
                a1 - 80,
                (__int64 *)&v41,
                1,
                v28) >= 0 )
    {
      if ( (unsigned int)dword_1800C1058 > 5 )
      {
        v41 = "OnAllocateSharedResources for fences";
        v40 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyn"
              "cProcessor>::SetRenderDevice";
        LODWORD(v35) = 405;
        v39 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)qword_1800B1510,
          v19,
          v20,
          (__int64)&v39,
          (__int64)&v35,
          (__int64)&v40,
          (__int64)&v41);
      }
      (*(void (__fastcall **)(_QWORD, _BYTE *, __int64))(**(_QWORD **)(a1 + 360) + 24LL))(*(_QWORD *)(a1 + 360), v46, 4);
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
    v39 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncPro"
          "cessor>::SetRenderDevice";
    v36 = 417;
    v44[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&byte_1800B154F,
      v19,
      v20,
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
  return 0;
}

```

## disassembly

```asm
0x18004a6f0  mov     [rsp+arg_10], rbx
0x18004a6f5  mov     [rsp+arg_18], rsi
0x18004a6fa  push    rdi
0x18004a6fb  push    r12
0x18004a6fd  push    r13
0x18004a6ff  push    r14
0x18004a701  push    r15
0x18004a703  sub     rsp, 1C0h
0x18004a70a  mov     rax, cs:__security_cookie
0x18004a711  xor     rax, rsp
0x18004a714  mov     [rsp+1E8h+var_38], rax
0x18004a71c  mov     rbx, rdx
0x18004a71f  mov     rdi, rcx
0x18004a722  xor     r12d, r12d
0x18004a725  mov     [rsp+1E8h+var_188], r12
0x18004a72a  mov     rax, [rdx]
0x18004a72d  lea     r8, [rsp+1E8h+var_188]
0x18004a732  lea     rdx, _GUID_8ffde202_a0e7_45df_9e01_e837801b5ea0
0x18004a739  mov     rcx, rbx
0x18004a73c  mov     rax, [rax]
0x18004a73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a744  mov     rcx, [rsp+1E8h]; this
0x18004a74c  test    eax, eax
0x18004a74e  js      loc_18004AD30
0x18004a754  mov     rax, [rsp+1E8h+var_188]
0x18004a759  mov     rcx, r12
0x18004a75c  mov     [rsp+1E8h+var_188], rcx
0x18004a761  mov     rdx, [rdi+68h]
0x18004a765  mov     [rdi+68h], rax
0x18004a769  test    rdx, rdx
0x18004a76c  jz      short loc_18004A782
0x18004a76e  mov     rax, [rdx]
0x18004a771  mov     rcx, rdx
0x18004a774  mov     rax, [rax+10h]
0x18004a778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a77d  mov     rcx, [rsp+1E8h+var_188]
0x18004a782  test    rcx, rcx
0x18004a785  jz      short loc_18004A794
0x18004a787  mov     rax, [rcx]
0x18004a78a  mov     rax, [rax+10h]
0x18004a78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a793  nop
0x18004a794  mov     [rsp+1E8h+pAdapter], r12
0x18004a79c  mov     [rsp+1E8h+var_188], r12
0x18004a7a1  mov     rax, [rbx]
0x18004a7a4  lea     r8, [rsp+1E8h+var_188]
0x18004a7a9  lea     rdx, _GUID_05008617_fbfd_4051_a790_144884b4f6a9
0x18004a7b0  mov     rcx, rbx
0x18004a7b3  mov     rax, [rax]
0x18004a7b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7bb  mov     rcx, [rsp+1E8h]; this
0x18004a7c3  test    eax, eax
0x18004a7c5  js      loc_18004AD45
0x18004a7cb  mov     rbx, [rsp+1E8h+var_188]
0x18004a7d0  mov     rax, [rbx]
0x18004a7d3  mov     rsi, [rax+38h]
0x18004a7d7  mov     rcx, [rsp+1E8h+pAdapter]
0x18004a7df  mov     [rsp+1E8h+pAdapter], r12
0x18004a7e7  test    rcx, rcx
0x18004a7ea  jz      short loc_18004A7F9
0x18004a7ec  mov     rdx, [rcx]
0x18004a7ef  mov     rax, [rdx+10h]
0x18004a7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7f8  nop
0x18004a7f9  lea     rdx, [rsp+1E8h+pAdapter]
0x18004a801  mov     rcx, rbx
0x18004a804  mov     rax, rsi
0x18004a807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a80c  mov     rcx, [rsp+1E8h]; this
0x18004a814  test    eax, eax
0x18004a816  js      loc_18004AD5A
0x18004a81c  mov     rcx, [rsp+1E8h+var_188]
0x18004a821  test    rcx, rcx
0x18004a824  jz      short loc_18004A833
0x18004a826  mov     rax, [rcx]
0x18004a829  mov     rax, [rax+10h]
0x18004a82d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a832  nop
0x18004a833  mov     [rsp+1E8h+var_178], r12
0x18004a838  mov     eax, cs:dword_1800C1058
0x18004a83e  mov     r13d, 4
0x18004a844  cmp     eax, r13d
0x18004a847  jbe     loc_18004A90B
0x18004a84d  mov     rdx, [rdi+60h]
0x18004a851  lea     rax, [rdx+70h]
0x18004a855  mov     [rsp+1E8h+var_148], rax
0x18004a85d  mov     rax, [rdx+68h]
0x18004a861  mov     ecx, [rax+88h]
0x18004a867  mov     [rsp+1E8h+var_180], ecx
0x18004a86b  mov     eax, [rdx+80h]
0x18004a871  mov     [rsp+1E8h+var_17C], eax
0x18004a875  lea     rax, aCreatingEncode_0; "Creating encoder device"
0x18004a87c  mov     [rsp+1E8h+var_170], rax
0x18004a881  lea     r15, aRdpAvencIc3Cic_15; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004a888  mov     [rsp+1E8h+var_168], r15
0x18004a890  mov     dword ptr [rsp+1E8h+var_188], 15Fh
0x18004a898  lea     rsi, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004a89f  mov     [rsp+1E8h+var_160], rsi
0x18004a8a7  lea     rax, [rsp+1E8h+var_148]
0x18004a8af  mov     [rsp+1E8h+var_198], rax
0x18004a8b4  lea     rax, [rsp+1E8h+var_180]
0x18004a8b9  mov     [rsp+1E8h+ppImmediateContext], rax
0x18004a8be  lea     rax, [rsp+1E8h+var_17C]
0x18004a8c3  mov     [rsp+1E8h+pFeatureLevel], rax
0x18004a8c8  lea     rax, [rsp+1E8h+var_170]
0x18004a8cd  mov     [rsp+1E8h+ppDevice], rax
0x18004a8d2  lea     rax, [rsp+1E8h+var_168]
0x18004a8da  mov     qword ptr [rsp+1E8h+SDKVersion], rax
0x18004a8df  lea     rax, [rsp+1E8h+var_188]
0x18004a8e4  mov     qword ptr [rsp+1E8h+FeatureLevels], rax
0x18004a8e9  lea     rax, [rsp+1E8h+var_160]
0x18004a8f1  mov     [rsp+1E8h+pFeatureLevels], rax
0x18004a8f6  lea     rdx, word_1800B15EE
0x18004a8fd  lea     rcx, dword_1800C1058
0x18004a904  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004a909  jmp     short loc_18004A919
0x18004a90b  lea     rsi, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004a912  lea     r15, aRdpAvencIc3Cic_15; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004a919  mov     rcx, [rsp+1E8h+var_178]
0x18004a91e  mov     [rsp+1E8h+var_178], r12
0x18004a923  test    rcx, rcx
0x18004a926  jz      short loc_18004A935
0x18004a928  mov     rax, [rcx]
0x18004a92b  mov     rax, [rax+10h]
0x18004a92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a934  nop
0x18004a935  mov     [rsp+1E8h+ppImmediateContext], r12; ppImmediateContext
0x18004a93a  mov     [rsp+1E8h+pFeatureLevel], r12; pFeatureLevel
0x18004a93f  lea     rax, [rsp+1E8h+var_178]
0x18004a944  mov     [rsp+1E8h+ppDevice], rax; ppDevice
0x18004a949  mov     [rsp+1E8h+SDKVersion], 7; SDKVersion
0x18004a951  mov     [rsp+1E8h+FeatureLevels], r12d; char *
0x18004a956  mov     [rsp+1E8h+pFeatureLevels], r12; pFeatureLevels
0x18004a95b  mov     r9d, 800h; Flags
0x18004a961  xor     r8d, r8d; Software
0x18004a964  xor     edx, edx; DriverType
0x18004a966  mov     rcx, [rsp+1E8h+pAdapter]; pAdapter
0x18004a96e  call    cs:__imp_D3D11CreateDevice
0x18004a974  mov     rcx, [rsp+1E8h]; this
0x18004a97c  lea     r8, aD3d11createdev; "D3D11CreateDevice failed for Encoder De"...
0x18004a983  mov     [rsp+1E8h+pFeatureLevels], r8; int
0x18004a988  mov     r9d, eax; char *
0x18004a98b  mov     r8, rsi; unsigned int
0x18004a98e  mov     edx, 16Ch; void *
0x18004a993  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004a998  mov     rcx, [rsp+1E8h+var_178]
0x18004a99d  mov     [rsp+1E8h+var_188], r12
0x18004a9a2  mov     rax, [rcx]
0x18004a9a5  lea     r8, [rsp+1E8h+var_188]
0x18004a9aa  lea     rdx, _GUID_8ffde202_a0e7_45df_9e01_e837801b5ea0
0x18004a9b1  mov     rax, [rax]
0x18004a9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9b9  mov     rcx, [rsp+1E8h]; this
0x18004a9c1  test    eax, eax
0x18004a9c3  js      loc_18004AD6F
0x18004a9c9  mov     rax, [rsp+1E8h+var_188]
0x18004a9ce  mov     rcx, r12
0x18004a9d1  mov     [rsp+1E8h+var_188], rcx
0x18004a9d6  mov     rdx, [rdi+70h]
0x18004a9da  mov     [rdi+70h], rax
0x18004a9de  test    rdx, rdx
0x18004a9e1  jz      short loc_18004A9F7
0x18004a9e3  mov     rax, [rdx]
0x18004a9e6  mov     rcx, rdx
0x18004a9e9  mov     rax, [rax+10h]
0x18004a9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9f2  mov     rcx, [rsp+1E8h+var_188]
0x18004a9f7  test    rcx, rcx
0x18004a9fa  jz      short loc_18004AA09
0x18004a9fc  mov     rax, [rcx]
0x18004a9ff  mov     rax, [rax+10h]
0x18004aa03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa08  nop
0x18004aa09  mov     rcx, [rdi+80h]; this
0x18004aa10  test    rcx, rcx
0x18004aa13  jz      short loc_18004AA21
0x18004aa15  mov     rdx, [rsp+1E8h+var_178]; struct ID3D11Device *
0x18004aa1a  call    ?SetEncodeDevice@CDsStreamSource@Ic3@Avenc@Rdp@@QEAAJPEAUID3D11Device@@@Z; Rdp::Avenc::Ic3::CDsStreamSource::SetEncodeDevice(ID3D11Device *)
0x18004aa1f  jmp     short loc_18004AA37
0x18004aa21  mov     rcx, [rdi+88h]; this
0x18004aa28  test    rcx, rcx
0x18004aa2b  jz      short loc_18004AA37
0x18004aa2d  mov     rdx, [rsp+1E8h+var_178]; struct ID3D11Device *
0x18004aa32  call    ?NotifyD3D11Device@CVideoSourceProvider@Ic3@Avenc@Rdp@@QEAAXPEAUID3D11Device@@@Z; Rdp::Avenc::Ic3::CVideoSourceProvider::NotifyD3D11Device(ID3D11Device *)
0x18004aa37  cmp     [rdi+168h], r12
0x18004aa3e  jz      loc_18004AC0C
0x18004aa44  lea     rbx, [rdi+10h]
0x18004aa48  mov     [rsp+1E8h+var_148], rbx
0x18004aa50  mov     rcx, rbx
0x18004aa53  call    mtx_do_lock
0x18004aa58  test    eax, eax
0x18004aa5a  jnz     loc_18004AD83
0x18004aa60  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18004aa67  jz      loc_18004AD8D
0x18004aa6d  lea     rax, [rsp+1E8h+var_138]
0x18004aa75  mov     [rsp+1E8h+var_160], rax
0x18004aa7d  mov     [rsp+1E8h+var_158], r13
0x18004aa85  xor     r8d, r8d
0x18004aa88  lea     rdx, [rsp+1E8h+var_160]
0x18004aa90  lea     rcx, [rdi-50h]
0x18004aa94  call    ?CreateSharedResources@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAJ$$QEAV?$span@UAVENC_SHARED_RESOURCE@Avenc@Rdp@@$0?0@std@@W4AVENC_RESOURCE_TYPE@34@@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CreateSharedResources(std::span<Rdp::Avenc::AVENC_SHARED_RESOURCE,-1> &&,Rdp::Avenc::AVENC_RESOURCE_TYPE)
0x18004aa99  test    eax, eax
0x18004aa9b  js      loc_18004AB2F
0x18004aaa1  mov     eax, cs:dword_1800C1058
0x18004aaa7  cmp     eax, 5
0x18004aaaa  jbe     short loc_18004AB11
0x18004aaac  lea     rax, aOnallocateshar; "OnAllocateSharedResources for textures"
0x18004aab3  mov     [rsp+1E8h+var_160], rax
0x18004aabb  mov     [rsp+1E8h+var_168], r15
0x18004aac3  mov     dword ptr [rsp+1E8h+var_188], 189h
0x18004aacb  mov     [rsp+1E8h+var_170], rsi
0x18004aad0  lea     rax, [rsp+1E8h+var_160]
0x18004aad8  mov     [rsp+1E8h+ppDevice], rax
0x18004aadd  lea     rax, [rsp+1E8h+var_168]
0x18004aae5  mov     qword ptr [rsp+1E8h+SDKVersion], rax
0x18004aaea  lea     rax, [rsp+1E8h+var_188]
0x18004aaef  mov     qword ptr [rsp+1E8h+FeatureLevels], rax
0x18004aaf4  lea     rax, [rsp+1E8h+var_170]
0x18004aaf9  mov     [rsp+1E8h+pFeatureLevels], rax
0x18004aafe  lea     rdx, byte_1800B15AF
0x18004ab05  lea     rcx, dword_1800C1058
0x18004ab0c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18004ab11  mov     rcx, [rdi+168h]
0x18004ab18  mov     rax, [rcx]
0x18004ab1b  mov     r8d, r13d
0x18004ab1e  lea     rdx, [rsp+1E8h+var_138]
0x18004ab26  mov     rax, [rax+18h]
0x18004ab2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab2f  lea     rax, [rsp+1E8h+var_B8]
0x18004ab37  mov     [rsp+1E8h+var_160], rax
0x18004ab3f  mov     [rsp+1E8h+var_158], r13
0x18004ab47  mov     r8d, 1
0x18004ab4d  lea     rdx, [rsp+1E8h+var_160]
0x18004ab55  lea     rcx, [rdi-50h]
0x18004ab59  call    ?CreateSharedResources@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@IEAAJ$$QEAV?$span@UAVENC_SHARED_RESOURCE@Avenc@Rdp@@$0?0@std@@W4AVENC_RESOURCE_TYPE@34@@Z; Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::CreateSharedResources(std::span<Rdp::Avenc::AVENC_SHARED_RESOURCE,-1> &&,Rdp::Avenc::AVENC_RESOURCE_TYPE)
0x18004ab5e  test    eax, eax
0x18004ab60  js      loc_18004ABF5
0x18004ab66  mov     eax, cs:dword_1800C1058
0x18004ab6c  cmp     eax, 5
0x18004ab6f  jbe     short loc_18004ABD6
0x18004ab71  lea     rax, aOnallocateshar_0; "OnAllocateSharedResources for fences"
0x18004ab78  mov     [rsp+1E8h+var_160], rax
0x18004ab80  mov     [rsp+1E8h+var_168], r15
0x18004ab88  mov     dword ptr [rsp+1E8h+var_188], 195h
0x18004ab90  mov     [rsp+1E8h+var_170], rsi
0x18004ab95  lea     rax, [rsp+1E8h+var_160]
0x18004ab9d  mov     [rsp+1E8h+ppDevice], rax
0x18004aba2  lea     rax, [rsp+1E8h+var_168]
0x18004abaa  mov     qword ptr [rsp+1E8h+SDKVersion], rax
0x18004abaf  lea     rax, [rsp+1E8h+var_188]
0x18004abb4  mov     qword ptr [rsp+1E8h+FeatureLevels], rax
0x18004abb9  lea     rax, [rsp+1E8h+var_170]
0x18004abbe  mov     [rsp+1E8h+pFeatureLevels], rax
0x18004abc3  lea     rdx, qword_1800B1510
0x18004abca  lea     rcx, dword_1800C1058
0x18004abd1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18004abd6  mov     rcx, [rdi+168h]
0x18004abdd  mov     rax, [rcx]
0x18004abe0  mov     r8d, r13d
0x18004abe3  lea     rdx, [rsp+1E8h+var_B8]
0x18004abeb  mov     rax, [rax+18h]
0x18004abef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004abf4  nop
0x18004abf5  sub     dword ptr [rbx+4Ch], 1
0x18004abf9  jnz     short loc_18004AC0C
0x18004abfb  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x18004ac02  lea     rcx, [rbx+10h]; SRWLock
0x18004ac06  call    cs:__imp_ReleaseSRWLockExclusive
0x18004ac0c  mov     eax, cs:dword_1800C1058
0x18004ac12  cmp     eax, 5
0x18004ac15  jbe     loc_18004ACCA
0x18004ac1b  mov     rdx, [rdi+60h]
0x18004ac1f  lea     rax, [rdx+70h]
0x18004ac23  mov     [rsp+1E8h+var_160], rax
0x18004ac2b  mov     rax, [rdx+68h]
0x18004ac2f  mov     ecx, [rax+88h]
0x18004ac35  mov     dword ptr [rsp+1E8h+var_188], ecx
0x18004ac39  mov     eax, [rdx+80h]
0x18004ac3f  mov     [rsp+1E8h+var_17C], eax
0x18004ac43  lea     rax, aCreatingEncode; "Creating encoder device - done"
0x18004ac4a  mov     [rsp+1E8h+var_168], rax
0x18004ac52  mov     [rsp+1E8h+var_170], r15
0x18004ac57  mov     [rsp+1E8h+var_180], 1A1h
0x18004ac5f  mov     [rsp+1E8h+var_148], rsi
0x18004ac67  lea     rax, [rsp+1E8h+var_160]
0x18004ac6f  mov     [rsp+1E8h+var_198], rax
0x18004ac74  lea     rax, [rsp+1E8h+var_188]
0x18004ac79  mov     [rsp+1E8h+ppImmediateContext], rax
0x18004ac7e  lea     rax, [rsp+1E8h+var_17C]
0x18004ac83  mov     [rsp+1E8h+pFeatureLevel], rax
0x18004ac88  lea     rax, [rsp+1E8h+var_168]
0x18004ac90  mov     [rsp+1E8h+ppDevice], rax
0x18004ac95  lea     rax, [rsp+1E8h+var_170]
0x18004ac9a  mov     qword ptr [rsp+1E8h+SDKVersion], rax
0x18004ac9f  lea     rax, [rsp+1E8h+var_180]
0x18004aca4  mov     qword ptr [rsp+1E8h+FeatureLevels], rax
0x18004aca9  lea     rax, [rsp+1E8h+var_148]
0x18004acb1  mov     [rsp+1E8h+pFeatureLevels], rax
0x18004acb6  lea     rdx, byte_1800B154F
0x18004acbd  lea     rcx, dword_1800C1058
  ... truncated ...
```
