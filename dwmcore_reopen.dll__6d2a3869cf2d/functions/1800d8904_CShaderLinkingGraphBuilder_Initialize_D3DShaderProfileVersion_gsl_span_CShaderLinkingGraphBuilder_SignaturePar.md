# CShaderLinkingGraphBuilder::Initialize(D3DShaderProfileVersion,gsl::span<CShaderLinkingGraphBuilder::SignatureParameter const,-1>)

- ea: `0x1800d8904`
- end: `0x1800d8c97`
- name: `?Initialize@CShaderLinkingGraphBuilder@@QEAAJW4D3DShaderProfileVersion@@V?$span@$$CBUSignatureParameter@CShaderLinkingGraphBuilder@@$0?0@gsl@@@Z`
- size: `915`
- prototype: `__int64 __fastcall(struct ID3D11Linker **ppLinker)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d8f2c`
- `0x1802556a0`

## callees

- `0x180049470`
- `0x180050270`
- `0x1800d2f80`
- `0x1800d32c0`
- `0x1800d8904`
- `0x1800d8ca0`
- `0x1800d9d50`
- `0x1800d9f24`
- `0x1802284b0`
- `0x180229450`
- `0x18025676c`
- `0x1802b6010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800d8c52`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800d8c52`
- `D3DCOMPILER_47!D3DCreateLinker` at `0x1800d8a61`
- `D3DCOMPILER_47!D3DCreateLinker` at `0x1800d8a61`
- `D3DCOMPILER_47!D3DCreateFunctionLinkingGraph` at `0x1800d8a8c`
- `D3DCOMPILER_47!D3DCreateFunctionLinkingGraph` at `0x1800d8a8c`

## pseudocode

```c
__int64 __fastcall CShaderLinkingGraphBuilder::Initialize(struct ID3D11Linker **ppLinker, char a2, _QWORD *a3)
{
  __int64 v3; // rsi
  SIZE_T size_of; // rax
  void *v7; // rbx
  __int64 v8; // r13
  __int64 v9; // rdi
  __int64 v10; // rbx
  int v11; // ecx
  _OWORD *v12; // rdx
  __int128 v13; // xmm2
  __int128 v14; // xmm3
  __int64 v15; // xmm0_8
  HRESULT v16; // eax
  unsigned int v17; // edi
  struct ID3D11Linker **v18; // rbx
  HRESULT v19; // eax
  struct ID3D11Linker *v20; // rdi
  HRESULT (__stdcall *UseLibrary)(ID3D11Linker *, struct ID3D11ModuleInstance *); // rbx
  int v22; // eax
  unsigned int i; // r14d
  __int64 v24; // rbx
  __int64 v25; // rcx
  __int64 v27; // [rsp+30h] [rbp-D0h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-C8h] BYREF
  void *v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  char v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+59h] [rbp-A7h]
  char v33; // [rsp+5Dh] [rbp-A3h]
  __int16 v34; // [rsp+5Eh] [rbp-A2h]
  __int64 v35; // [rsp+60h] [rbp-A0h]
  __int128 v36; // [rsp+68h] [rbp-98h]
  __int128 v37; // [rsp+78h] [rbp-88h]
  _BYTE v38[24]; // [rsp+88h] [rbp-78h]
  _OWORD v39[3]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-30h]
  _BYTE v41[16]; // [rsp+D8h] [rbp-28h] BYREF
  __int16 v42; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v43; // [rsp+F0h] [rbp-10h] BYREF
  char v44; // [rsp+F8h] [rbp-8h]
  int v45; // [rsp+F9h] [rbp-7h]
  char v46; // [rsp+FDh] [rbp-3h]

  v3 = 0;
  *((_BYTE *)ppLinker + 84) = a2;
  v29 = 0;
  *(_OWORD *)Src = 0;
  v27 = 0;
  if ( *a3 )
  {
    if ( *a3 > 0x492492492492492uLL )
      std::_Xlength_error("vector too long");
    size_of = std::_Get_size_of_n<56>(*a3);
    v7 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    memmove_0(v7, Src[0], (char *)Src[1] - (char *)Src[0]);
    std::vector<CShapeRenderTask>::_Change_array(Src, v7, 0, *a3);
  }
  v8 = a3[1];
  v9 = v8;
  v10 = v8 + 32LL * *a3;
  if ( v8 != v10 )
  {
    do
    {
      v11 = *(_DWORD *)(v9 + 28);
      v12 = Src[1];
      v36 = *(_OWORD *)(v9 + 8);
      LODWORD(v37) = *(_DWORD *)(v9 + 24);
      *(_OWORD *)&v38[8] = 0;
      *(_QWORD *)((char *)&v37 + 4) = (v11 != 1) | 0x100000000LL;
      HIDWORD(v37) = v11;
      v13 = v37;
      *(_QWORD *)v38 = 0x100000000LL;
      v14 = *(_OWORD *)v38;
      v15 = *(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)&v38[8], *(__m128d *)&v38[8]);
      v39[1] = v37;
      v39[0] = v36;
      v39[2] = *(_OWORD *)v38;
      v40 = v15;
      if ( Src[1] == v29 )
      {
        std::vector<_D3D11_PARAMETER_DESC>::_Emplace_reallocate<_D3D11_PARAMETER_DESC const &>(Src, Src[1], v39);
      }
      else
      {
        *(_OWORD *)Src[1] = v36;
        v12[1] = v13;
        v12[2] = v14;
        *((_QWORD *)v12 + 6) = v15;
        Src[1] = (char *)Src[1] + 56;
      }
      v9 += 32;
    }
    while ( v9 != v10 );
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppLinker);
  v16 = D3DCreateLinker(ppLinker);
  v17 = v16;
  if ( v16 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v16, 0x45u, 0);
  }
  else
  {
    v18 = ppLinker + 1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(ppLinker + 1);
    v19 = D3DCreateFunctionLinkingGraph(0, (struct ID3D11FunctionLinkingGraph **)ppLinker + 1);
    v17 = v19;
    if ( v19 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v19, 0x46u, 0);
    }
    else
    {
      v20 = *v18;
      UseLibrary = (*v18)->lpVtbl->UseLibrary;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
      v22 = ((__int64 (__fastcall *)(struct ID3D11Linker *, void *, __int64, __int64 *))UseLibrary)(
              v20,
              Src[0],
              0x6DB6DB6DB6DB6DB7LL * (((char *)Src[1] - (char *)Src[0]) >> 3),
              &v27);
      v17 = v22;
      if ( v22 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v22, 0x4Au, 0);
      }
      else
      {
        for ( i = 0; i < *(_DWORD *)a3; v3 = 0 )
        {
          v24 = v27;
          v30 = 0;
          v35 = 0;
          v32 = 0;
          v33 = 0;
          v34 = 0;
          if ( v27 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
            v30 = v24;
            v3 = v24;
          }
          v31 = i;
          if ( (unsigned __int64)i >= *a3 )
          {
            ((void (*)(void))`gsl::details::get_terminate_handler'::`2'::handler)();
            __debugbreak();
          }
          v43 = v3;
          v42 = *(_WORD *)(32LL * i + v8);
          if ( v3 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
          v45 = v35;
          v46 = v35;
          v44 = i;
          std::_Hash<std::_Umap_traits<enum ShaderLinkingArgument,CShaderLinkingGraphBuilder::Node,std::_Uhash_compare<enum ShaderLinkingArgument,std::hash<enum ShaderLinkingArgument>,std::equal_to<enum ShaderLinkingArgument>>,std::allocator<std::pair<enum ShaderLinkingArgument const,CShaderLinkingGraphBuilder::Node>>,0>>::emplace<std::pair<enum ShaderLinkingArgument,CShaderLinkingGraphBuilder::Node>>(
            ppLinker + 2,
            v41,
            &v42);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
          ++i;
        }
      }
    }
  }
  v25 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  if ( Src[0] )
    std::_Deallocate<16>(Src[0], 8 * ((signed __int64)((__int64)v29 - (unsigned __int64)Src[0]) >> 3));
  return v17;
}

```

## disassembly

```asm
0x1800d8904  mov     [rsp-8+arg_8], rbx
0x1800d8909  push    rbp
0x1800d890a  push    rsi
0x1800d890b  push    rdi
0x1800d890c  push    r12
0x1800d890e  push    r13
0x1800d8910  push    r14
0x1800d8912  push    r15
0x1800d8914  lea     rbp, [rsp-10h]
0x1800d8919  sub     rsp, 110h
0x1800d8920  mov     rax, cs:__security_cookie
0x1800d8927  xor     rax, rsp
0x1800d892a  mov     [rbp+40h+var_40], rax
0x1800d892e  xor     esi, esi
0x1800d8930  mov     [rcx+54h], dl
0x1800d8933  xorps   xmm0, xmm0
0x1800d8936  mov     r12, r8
0x1800d8939  mov     r15, rcx
0x1800d893c  mov     [rsp+140h+var_F8], rsi
0x1800d8941  movdqu  xmmword ptr [rsp+140h+Src], xmm0
0x1800d8947  mov     [rsp+140h+var_110], rsi
0x1800d894c  cmp     [r8], rsi
0x1800d894f  jbe     short loc_1800D89A0
0x1800d8951  mov     rax, 492492492492492h
0x1800d895b  cmp     [r8], rax
0x1800d895e  ja      loc_1800D8C4B
0x1800d8964  mov     rcx, [r8]
0x1800d8967  call    ??$_Get_size_of_n@$0DI@@std@@YA_K_K@Z; std::_Get_size_of_n<56>(unsigned __int64)
0x1800d896c  mov     rcx, rax; dwBytes
0x1800d896f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800d8974  mov     rdx, [rsp+140h+Src]; Src
0x1800d8979  mov     rcx, rax; void *
0x1800d897c  mov     r8, [rsp+140h+Src+8]
0x1800d8981  mov     rbx, rax
0x1800d8984  sub     r8, rdx; Size
0x1800d8987  call    memmove_0
0x1800d898c  mov     r9, [r12]
0x1800d8990  lea     rcx, [rsp+140h+Src]
0x1800d8995  xor     r8d, r8d
0x1800d8998  mov     rdx, rbx
0x1800d899b  call    ?_Change_array@?$vector@VCShapeRenderTask@@V?$allocator@VCShapeRenderTask@@@std@@@std@@AEAAXQEAVCShapeRenderTask@@_K1@Z; std::vector<CShapeRenderTask>::_Change_array(CShapeRenderTask * const,unsigned __int64,unsigned __int64)
0x1800d89a0  mov     r13, [r12+8]
0x1800d89a5  mov     rbx, [r12]
0x1800d89a9  mov     rdi, r13
0x1800d89ac  shl     rbx, 5
0x1800d89b0  add     rbx, r13
0x1800d89b3  cmp     r13, rbx
0x1800d89b6  jz      loc_1800D8A56
0x1800d89bc  mov     rax, [rdi+8]
0x1800d89c0  xorps   xmm0, xmm0
0x1800d89c3  mov     ecx, [rdi+1Ch]
0x1800d89c6  cmp     ecx, 1
0x1800d89c9  mov     rdx, [rsp+140h+Src+8]
0x1800d89ce  mov     qword ptr [rsp+140h+var_D8], rax
0x1800d89d3  mov     rax, [rdi+10h]
0x1800d89d7  mov     qword ptr [rsp+140h+var_D8+8], rax
0x1800d89dc  mov     eax, [rdi+18h]
0x1800d89df  movups  xmm1, [rsp+140h+var_D8]
0x1800d89e4  mov     dword ptr [rsp+140h+var_C8], eax
0x1800d89e8  mov     eax, esi
0x1800d89ea  setnz   al
0x1800d89ed  mov     dword ptr [rbp+40h+var_C8+8], 1
0x1800d89f4  movdqu  xmmword ptr [rbp+40h+var_B8+8], xmm0
0x1800d89f9  mov     dword ptr [rsp+140h+var_C8+4], eax
0x1800d89fd  mov     dword ptr [rbp+40h+var_C8+0Ch], ecx
0x1800d8a00  movups  xmm2, [rsp+140h+var_C8]
0x1800d8a05  mov     dword ptr [rbp+40h+var_B8], esi
0x1800d8a08  mov     dword ptr [rbp+40h+var_B8+4], 1
0x1800d8a0f  movups  xmm3, xmmword ptr [rbp+40h+var_B8]
0x1800d8a13  unpckhpd xmm0, xmm0
0x1800d8a17  movups  [rbp+40h+var_90], xmm2
0x1800d8a1b  movups  [rbp+40h+var_A0], xmm1
0x1800d8a1f  movups  [rbp+40h+var_80], xmm3
0x1800d8a23  movsd   [rbp+40h+var_70], xmm0
0x1800d8a28  cmp     rdx, [rsp+140h+var_F8]
0x1800d8a2d  jz      loc_1800D8C59
0x1800d8a33  movups  xmmword ptr [rdx], xmm1
0x1800d8a36  movups  xmmword ptr [rdx+10h], xmm2
0x1800d8a3a  movups  xmmword ptr [rdx+20h], xmm3
0x1800d8a3e  movsd   qword ptr [rdx+30h], xmm0
0x1800d8a43  add     [rsp+140h+Src+8], 38h ; '8'
0x1800d8a49  add     rdi, 20h ; ' '
0x1800d8a4d  cmp     rdi, rbx
0x1800d8a50  jnz     loc_1800D89BC
0x1800d8a56  mov     rcx, r15
0x1800d8a59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d8a5e  mov     rcx, r15; ppLinker
0x1800d8a61  call    cs:__imp_D3DCreateLinker
0x1800d8a67  mov     edi, eax
0x1800d8a69  mov     r14, 6DB6DB6DB6DB6DB7h
0x1800d8a73  test    eax, eax
0x1800d8a75  js      loc_1800D8C29
0x1800d8a7b  lea     rbx, [r15+8]
0x1800d8a7f  mov     rcx, rbx
0x1800d8a82  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d8a87  mov     rdx, rbx; ppFunctionLinkingGraph
0x1800d8a8a  xor     ecx, ecx; uFlags
0x1800d8a8c  call    cs:__imp_D3DCreateFunctionLinkingGraph
0x1800d8a92  mov     edi, eax
0x1800d8a94  test    eax, eax
0x1800d8a96  js      loc_1800D8C88
0x1800d8a9c  mov     rdi, [rbx]
0x1800d8a9f  lea     rcx, [rsp+140h+var_110]
0x1800d8aa4  mov     rax, [rdi]
0x1800d8aa7  mov     rbx, [rax+20h]
0x1800d8aab  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d8ab0  mov     rdx, [rsp+140h+Src]
0x1800d8ab5  lea     r9, [rsp+140h+var_110]
0x1800d8aba  mov     r8, [rsp+140h+Src+8]
0x1800d8abf  mov     rcx, rdi
0x1800d8ac2  sub     r8, rdx
0x1800d8ac5  mov     rax, rbx
0x1800d8ac8  sar     r8, 3
0x1800d8acc  imul    r8, r14
0x1800d8ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8ad5  mov     edi, eax
0x1800d8ad7  test    eax, eax
0x1800d8ad9  js      loc_1800D8C79
0x1800d8adf  mov     r14d, esi
0x1800d8ae2  cmp     [r12], esi
0x1800d8ae6  jbe     loc_1800D8BB8
0x1800d8aec  mov     rbx, [rsp+140h+var_110]
0x1800d8af1  xor     eax, eax
0x1800d8af3  mov     [rsp+140h+var_F0], rsi
0x1800d8af8  mov     [rsp+140h+var_E0], rax
0x1800d8afd  mov     [rsp+140h+var_E7], eax
0x1800d8b01  mov     [rsp+140h+var_E3], al
0x1800d8b05  mov     [rsp+140h+var_E2], ax
0x1800d8b0a  cmp     rsi, rbx
0x1800d8b0d  jz      short loc_1800D8B3F
0x1800d8b0f  test    rbx, rbx
0x1800d8b12  jz      short loc_1800D8B23
0x1800d8b14  mov     rax, [rbx]
0x1800d8b17  mov     rcx, rbx
0x1800d8b1a  mov     rax, [rax+8]
0x1800d8b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8b23  mov     rcx, rsi
0x1800d8b26  mov     [rsp+140h+var_F0], rbx
0x1800d8b2b  mov     rsi, rbx
0x1800d8b2e  test    rcx, rcx
0x1800d8b31  jz      short loc_1800D8B3F
0x1800d8b33  mov     rax, [rcx]
0x1800d8b36  mov     rax, [rax+10h]
0x1800d8b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8b3f  mov     eax, r14d
0x1800d8b42  mov     [rsp+140h+var_E8], r14b
0x1800d8b47  cmp     rax, [r12]
0x1800d8b4b  jnb     loc_1800D8C6C
0x1800d8b51  shl     rax, 5
0x1800d8b55  mov     [rbp+40h+var_50], rsi
0x1800d8b59  movzx   eax, word ptr [rax+r13]
0x1800d8b5e  mov     [rbp+40h+var_58], ax
0x1800d8b62  test    rsi, rsi
0x1800d8b65  jz      short loc_1800D8B76
0x1800d8b67  mov     rax, [rsi]
0x1800d8b6a  mov     rcx, rsi
0x1800d8b6d  mov     rax, [rax+8]
0x1800d8b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8b76  mov     rax, [rsp+140h+var_E0]
0x1800d8b7b  lea     r8, [rbp+40h+var_58]
0x1800d8b7f  lea     rdx, [rbp+40h+var_68]
0x1800d8b83  mov     [rbp+40h+var_47], eax
0x1800d8b86  lea     rcx, [r15+10h]
0x1800d8b8a  mov     [rbp+40h+var_43], al
0x1800d8b8d  mov     [rbp+40h+var_48], r14b
0x1800d8b91  call    ??$emplace@U?$pair@W4ShaderLinkingArgument@@UNode@CShaderLinkingGraphBuilder@@@std@@@?$_Hash@V?$_Umap_traits@W4ShaderLinkingArgument@@UNode@CShaderLinkingGraphBuilder@@V?$_Uhash_compare@W4ShaderLinkingArgument@@U?$hash@W4ShaderLinkingArgument@@@std@@U?$equal_to@W4ShaderLinkingArgument@@@3@@std@@V?$allocator@U?$pair@$$CBW4ShaderLinkingArgument@@UNode@CShaderLinkingGraphBuilder@@@std@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4ShaderLinkingArgument@@UNode@CShaderLinkingGraphBuilder@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@W4ShaderLinkingArgument@@UNode@CShaderLinkingGraphBuilder@@@1@@Z; std::_Hash<std::_Umap_traits<ShaderLinkingArgument,CShaderLinkingGraphBuilder::Node,std::_Uhash_compare<ShaderLinkingArgument,std::hash<ShaderLinkingArgument>,std::equal_to<ShaderLinkingArgument>>,std::allocator<std::pair<ShaderLinkingArgument const,CShaderLinkingGraphBuilder::Node>>,0>>::emplace<std::pair<ShaderLinkingArgument,CShaderLinkingGraphBuilder::Node>>(std::pair<ShaderLinkingArgument,CShaderLinkingGraphBuilder::Node> &&)
0x1800d8b96  lea     rcx, [rbp+40h+var_50]
0x1800d8b9a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d8b9f  lea     rcx, [rsp+140h+var_F0]
0x1800d8ba4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d8ba9  inc     r14d
0x1800d8bac  xor     esi, esi
0x1800d8bae  cmp     r14d, [r12]
0x1800d8bb2  jb      loc_1800D8AEC
0x1800d8bb8  mov     r14, 6DB6DB6DB6DB6DB7h
0x1800d8bc2  mov     rcx, [rsp+140h+var_110]
0x1800d8bc7  test    rcx, rcx
0x1800d8bca  jz      short loc_1800D8BDD
0x1800d8bcc  mov     [rsp+140h+var_110], rsi
0x1800d8bd1  mov     rax, [rcx]
0x1800d8bd4  mov     rax, [rax+10h]
0x1800d8bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8bdd  mov     rcx, [rsp+140h+Src]
0x1800d8be2  test    rcx, rcx
0x1800d8be5  jz      short loc_1800D8C00
0x1800d8be7  mov     rax, [rsp+140h+var_F8]
0x1800d8bec  sub     rax, rcx
0x1800d8bef  sar     rax, 3
0x1800d8bf3  imul    rax, r14
0x1800d8bf7  imul    rdx, rax, 38h ; '8'
0x1800d8bfb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800d8c00  mov     eax, edi
0x1800d8c02  mov     rcx, [rbp+40h+var_40]
0x1800d8c06  xor     rcx, rsp; StackCookie
0x1800d8c09  call    __security_check_cookie
0x1800d8c0e  mov     rbx, [rsp+140h+arg_8]
0x1800d8c16  add     rsp, 110h
0x1800d8c1d  pop     r15
0x1800d8c1f  pop     r14
0x1800d8c21  pop     r13
0x1800d8c23  pop     r12
0x1800d8c25  pop     rdi
0x1800d8c26  pop     rsi
0x1800d8c27  pop     rbp
0x1800d8c28  retn
0x1800d8c29  mov     [rsp+140h+var_118], rsi; void *
0x1800d8c2e  mov     [rsp+140h+var_120], 45h ; 'E'; unsigned int
0x1800d8c36  xor     edx, edx; int *
0x1800d8c38  mov     r9d, eax; int
0x1800d8c3b  xor     r8d, r8d; unsigned int
0x1800d8c3e  lea     ecx, [rdx+14h]; unsigned int
0x1800d8c41  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800d8c46  jmp     loc_1800D8BC2
0x1800d8c4b  lea     rcx, aVectorTooLong; "vector too long"
0x1800d8c52  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800d8c59  lea     r8, [rbp+40h+var_A0]
0x1800d8c5d  lea     rcx, [rsp+140h+Src]
0x1800d8c62  call    ??$_Emplace_reallocate@AEBU_D3D11_PARAMETER_DESC@@@?$vector@U_D3D11_PARAMETER_DESC@@V?$allocator@U_D3D11_PARAMETER_DESC@@@std@@@std@@AEAAPEAU_D3D11_PARAMETER_DESC@@QEAU2@AEBU2@@Z; std::vector<_D3D11_PARAMETER_DESC>::_Emplace_reallocate<_D3D11_PARAMETER_DESC const &>(_D3D11_PARAMETER_DESC * const,_D3D11_PARAMETER_DESC const &)
0x1800d8c67  jmp     loc_1800D8A49
0x1800d8c6c  mov     rax, cs:?handler@?1??get_terminate_handler@details@gsl@@YAAEAP6AXXZXZ@4P6AXXZEA; void (*`gsl::details::get_terminate_handler(void)'::`2'::handler)(void)
0x1800d8c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8c78  int     3; Trap to Debugger
0x1800d8c79  mov     [rsp+140h+var_118], rsi
0x1800d8c7e  mov     [rsp+140h+var_120], 4Ah ; 'J'
0x1800d8c86  jmp     short loc_1800D8C36
0x1800d8c88  mov     [rsp+140h+var_118], rsi
0x1800d8c8d  mov     [rsp+140h+var_120], 46h ; 'F'
0x1800d8c95  jmp     short loc_1800D8C36
```
