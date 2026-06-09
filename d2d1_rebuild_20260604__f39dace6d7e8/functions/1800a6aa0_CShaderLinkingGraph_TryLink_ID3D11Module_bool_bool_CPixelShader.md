# CShaderLinkingGraph::TryLink(ID3D11Module *,bool,bool *,CPixelShader * *)

- ea: `0x1800a6aa0`
- end: `0x1800a77f7`
- name: `?TryLink@CShaderLinkingGraph@@IEAAJPEAUID3D11Module@@_NPEA_NPEAPEAVCPixelShader@@@Z`
- size: `3415`
- prototype: `__int64 __usercall@<rax>(CShaderLinkingGraph *__hidden this@<rcx>, struct ID3D11Module *@<rdx>, bool@<r8b>, bool *@<r9>, struct CPixelShader **)`
- caller_count: `2`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a4af0`
- `0x1800a5080`

## callees

- `0x180018ea0`
- `0x18001fd58`
- `0x1800389c0`
- `0x180092fec`
- `0x1800a6aa0`
- `0x1800a7800`
- `0x1800a7a04`
- `0x1800b3d10`
- `0x1800cce70`
- `0x1801ada30`
- `0x1801ae2d8`
- `0x1801b4294`
- `0x1801b430c`
- `0x1801b43cc`
- `0x1801cc1f0`
- `0x1801ebed0`
- `0x1801fd424`
- `0x1802172e8`
- `0x18025b100`
- `0x1802cc3c8`
- `0x1802cc628`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a7776`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a7776`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a74fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a74fe`

## pseudocode

```c
__int64 __fastcall CShaderLinkingGraph::TryLink(
        CShaderLinkingGraph *this,
        struct ID3D11Module *a2,
        char a3,
        bool *a4,
        struct CPixelShader **a5)
{
  __int64 v5; // r13
  __int64 v10; // rcx
  unsigned int v12; // ebx
  __int64 *v13; // rcx
  unsigned int v14; // r12d
  struct ID3D11ModuleVtbl *lpVtbl; // rax
  int v16; // eax
  signed int v17; // edi
  __int64 (__fastcall *v18)(_QWORD, _QWORD); // r14
  _QWORD *v19; // rdi
  __int64 v20; // r14
  CShaderLinkingGraph *v21; // rcx
  int v22; // eax
  int v23; // ecx
  bool v24; // cc
  const char *v25; // r9
  int v26; // eax
  __int64 v27; // rsi
  char *v28; // r14
  __int64 v29; // rcx
  struct ID3D11Module *v30; // r12
  unsigned int v31; // edi
  int FunctionModuleNoRef; // r14d
  __int64 v33; // rdi
  char *v34; // rsi
  __int64 v35; // rcx
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdx
  int v39; // eax
  int i; // r15d
  unsigned int *v41; // rdi
  bool v42; // zf
  __int64 v43; // rcx
  char v44; // r14
  unsigned int v45; // r15d
  __int64 v46; // r13
  unsigned int m; // r12d
  int v48; // eax
  __int64 v49; // rcx
  int v50; // eax
  unsigned int v51; // r14d
  int v52; // eax
  unsigned int n; // edi
  int v54; // eax
  int v55; // r15d
  __int64 ii; // r14
  __int64 v57; // r9
  __int64 v58; // rdx
  int v59; // eax
  __int64 v60; // rax
  int v61; // eax
  signed int LastError; // eax
  __int64 v63; // rdx
  __int64 v64; // rax
  int v65; // eax
  unsigned int j; // edi
  unsigned int k; // edi
  int v68; // eax
  unsigned int v69; // r13d
  __int64 v70; // rcx
  int v71; // eax
  FARPROC ProcAddress; // rax
  __int64 v73; // rdi
  __int64 v74; // rax
  __int64 v75; // [rsp+20h] [rbp-E0h]
  struct ID3D11FunctionLinkingGraph *v76; // [rsp+40h] [rbp-C0h] BYREF
  char v77; // [rsp+48h] [rbp-B8h]
  struct ID3D11LinkingNode *v78; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v79; // [rsp+58h] [rbp-A8h]
  __int64 v80; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v81; // [rsp+68h] [rbp-98h] BYREF
  __int64 v82; // [rsp+70h] [rbp-90h] BYREF
  __int64 v83; // [rsp+78h] [rbp-88h] BYREF
  __int64 v84; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v85; // [rsp+88h] [rbp-78h] BYREF
  struct ID3D10Blob *v86; // [rsp+90h] [rbp-70h] BYREF
  HMODULE hModule; // [rsp+98h] [rbp-68h] BYREF
  __int64 v88; // [rsp+A0h] [rbp-60h] BYREF
  struct ID3D11Module *v89; // [rsp+A8h] [rbp-58h]
  __int64 v90; // [rsp+B0h] [rbp-50h]
  struct CPixelShader **v91; // [rsp+B8h] [rbp-48h]
  bool *v92; // [rsp+C0h] [rbp-40h]
  char *v93; // [rsp+D0h] [rbp-30h] BYREF
  int v94; // [rsp+D8h] [rbp-28h]
  int v95; // [rsp+DCh] [rbp-24h]
  char v96; // [rsp+E0h] [rbp-20h]
  char v97; // [rsp+E1h] [rbp-1Fh] BYREF
  char *v98; // [rsp+130h] [rbp+30h] BYREF
  int v99; // [rsp+138h] [rbp+38h]
  int v100; // [rsp+13Ch] [rbp+3Ch]
  char v101; // [rsp+140h] [rbp+40h]
  char v102; // [rsp+141h] [rbp+41h] BYREF
  _QWORD v103[8]; // [rsp+190h] [rbp+90h] BYREF
  char v104[16]; // [rsp+1D0h] [rbp+D0h] BYREF

  v5 = 0;
  *a4 = 0;
  v92 = a4;
  v89 = a2;
  *a5 = 0;
  v91 = a5;
  if ( !*((_DWORD *)this + 17) )
    return 0;
  CShaderLinkingGraph::UpdateSignature(this);
  if ( (int)CShaderLinkingGraph::FindInCache(this, this, a5) >= 0 )
  {
    *a4 = *a5 != 0;
    return 0;
  }
  v12 = *((_DWORD *)this + 17);
  v85 = v12;
  if ( (Microsoft_Windows_D2D1EnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v10, &EffectShaderLinking_Start, v12);
  v13 = (__int64 *)*((_QWORD *)this + 14);
  v14 = *((_DWORD *)this + 36);
  v79 = v14;
  v90 = *v13;
  if ( a3 )
    v5 = v13[*((_DWORD *)this + 30) - 1];
  lpVtbl = a2->lpVtbl;
  v84 = v5;
  v82 = 0;
  v16 = ((__int64 (__fastcall *)(struct ID3D11Module *, const unsigned __int16 *, __int64 *))lpVtbl->CreateInstance)(
          a2,
          &word_18037105A,
          &v82);
  v17 = v16;
  if ( v16 < 0 )
  {
    DoStackCapture(v16);
    v23 = v17;
LABEL_24:
    DoStackCapture(v23);
    goto LABEL_21;
  }
  if ( v14 )
  {
    v61 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v82 + 40LL))(v82, 0, 0, v14);
    v17 = v61;
    if ( v61 < 0
      || (v61 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v82 + 56LL))(v82, 0, 0, v14),
          v17 = v61,
          v61 < 0) )
    {
      v23 = v61;
      goto LABEL_24;
    }
  }
  v18 = (__int64 (__fastcall *)(_QWORD, _QWORD))qword_1805DB3F0;
  v76 = 0;
  if ( !qword_1805DB3F0 )
  {
    hModule = 0;
    v17 = DelayLoadedModule::Load(g_dlD3DCreateFunctionLinkingGraph, &hModule);
    if ( v17 < 0 )
      goto LABEL_19;
    ProcAddress = GetProcAddress(hModule, lpProcName);
    v18 = (__int64 (__fastcall *)(_QWORD, _QWORD))ProcAddress;
    if ( ProcAddress )
    {
      qword_1805DB3F0 = (__int64)ProcAddress;
    }
    else
    {
      LastError = GetLastError();
      v17 = LastError;
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      if ( v17 < 0 )
        goto LABEL_19;
    }
  }
  v17 = v18(0, &v76);
  if ( v17 < 0 )
  {
LABEL_19:
    DoStackCapture(v17);
LABEL_20:
    ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v76);
    goto LABEL_21;
  }
  v78 = 0;
  v19 = v103;
  v20 = 8;
  do
  {
    win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>(v19++);
    --v20;
  }
  while ( v20 );
  if ( a3 )
  {
    v63 = *(_QWORD *)(v5 + 80);
    v64 = *(_QWORD *)(v63 + 52) - *(_QWORD *)&GUID_CopyShader.Data1;
    if ( !v64 )
      v64 = *(_QWORD *)(v63 + 60) - *(_QWORD *)GUID_CopyShader.Data4;
    if ( v64 )
    {
      v22 = CShaderLinkingGraph::CreateInputNodeFromFunction(v21, (const struct CPixelShader *)v63, v76, &v78);
      v17 = v22;
      if ( v22 >= 0 )
      {
        v77 = 1;
        goto LABEL_81;
      }
LABEL_17:
      DoStackCapture(v22);
LABEL_34:
      `vector destructor iterator'(v103, 8u, 8u, ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>);
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v78);
      goto LABEL_20;
    }
  }
  v22 = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, const struct _D3D11_PARAMETER_DESC near *const *, _QWORD, struct ID3D11LinkingNode **))v76->lpVtbl->SetInputSignature)(
          v76,
          &CShaderLinkingGraph::s_linkingShaderInputSig,
          v14 + 2,
          &v78);
  v17 = v22;
  if ( v22 < 0 )
    goto LABEL_17;
  v30 = v89;
  v31 = 0;
  v77 = 0;
  while ( v31 < *((_DWORD *)this + 36) )
  {
    if ( *(_BYTE *)(*((_QWORD *)this + 17) + 40LL * v31 + 12) )
    {
      FunctionModuleNoRef = StringCchPrintfA(v104, 0x10u, "SampleInput%d", v31);
      if ( FunctionModuleNoRef < 0
        || (FunctionModuleNoRef = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, const unsigned __int16 *, struct ID3D11Module *, char *, _QWORD *))v76->lpVtbl->CallFunction)(
                                    v76,
                                    &word_18037105A,
                                    v30,
                                    v104,
                                    &v103[v31]),
            FunctionModuleNoRef < 0)
        || (FunctionModuleNoRef = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, struct ID3D11LinkingNode *, _QWORD, _QWORD, _DWORD))v76->lpVtbl->PassValue)(
                                    v76,
                                    v78,
                                    v31 + 2,
                                    v103[v31],
                                    0),
            FunctionModuleNoRef < 0) )
      {
        DoStackCapture(FunctionModuleNoRef);
        goto LABEL_107;
      }
    }
    ++v31;
  }
LABEL_81:
  v36 = *((unsigned int *)this + 17);
  v93 = &v97;
  v95 = 8;
  v94 = 0;
  v96 = 0;
  v37 = CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::Resize(
          &v93,
          v36);
  v17 = v37;
  if ( v37 < 0 )
  {
    DoStackCapture(v37);
LABEL_110:
    CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v93);
    goto LABEL_34;
  }
  v38 = *((unsigned int *)this + 17);
  v98 = &v102;
  v99 = 0;
  v101 = 0;
  v100 = 8;
  v39 = CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::Resize(
          &v98,
          v38);
  v17 = v39;
  if ( v39 < 0 )
  {
    DoStackCapture(v39);
    CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v98);
    goto LABEL_110;
  }
  for ( i = *((_DWORD *)this + 17); i; *((_QWORD *)v41 + 14) = *(_QWORD *)&v98[8 * i] )
  {
    v41 = *(unsigned int **)(*((_QWORD *)this + 14) + 8LL * (unsigned int)--i);
    FunctionModuleNoRef = StringCchPrintfA(v104, 0x10u, "mod%d", i);
    if ( FunctionModuleNoRef < 0 )
      goto LABEL_106;
    if ( !*((_QWORD *)v41 + 15) )
    {
      FunctionModuleNoRef = CTrackedShader<ID3D11PixelShader,0>::GetFunctionModuleNoRef(*((_QWORD *)v41 + 10), v41 + 30);
      if ( FunctionModuleNoRef < 0 )
        goto LABEL_106;
    }
    FunctionModuleNoRef = CTrackedShader<ID3D11PixelShader,0>::GetFunctionModuleInstance(
                            *((_QWORD *)v41 + 10),
                            v104,
                            &v93[8 * i]);
    if ( FunctionModuleNoRef < 0 )
      goto LABEL_106;
    v42 = *((_QWORD *)v41 + 12) == 0;
    v43 = *(_QWORD *)&v93[8 * i];
    *((_QWORD *)v41 + 16) = v43;
    if ( !v42 )
    {
      FunctionModuleNoRef = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v43 + 24LL))(
                              v43,
                              0,
                              0,
                              v41[1]);
      if ( FunctionModuleNoRef < 0 )
        goto LABEL_106;
    }
    if ( !v41[2]
      || (FunctionModuleNoRef = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)v41 + 16) + 40LL))(
                                  *((_QWORD *)v41 + 16),
                                  *v41,
                                  v41[3] + v79),
          FunctionModuleNoRef >= 0)
      && (FunctionModuleNoRef = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)v41 + 16)
                                                                                          + 56LL))(
                                  *((_QWORD *)v41 + 16),
                                  *v41,
                                  v41[3] + v79,
                                  v41[2]),
          FunctionModuleNoRef >= 0) )
    {
      FunctionModuleNoRef = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, char *, _QWORD, const char *, char *))v76->lpVtbl->CallFunction)(
                              v76,
                              v104,
                              *((_QWORD *)v41 + 15),
                              "D2D_func_entry",
                              &v98[8 * i]);
      if ( FunctionModuleNoRef >= 0 )
        continue;
    }
LABEL_106:
    DoStackCapture(FunctionModuleNoRef);
    CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v98);
    CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v93);
LABEL_107:
    `vector destructor iterator'(v103, 8u, 8u, ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>);
    ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v78);
    ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v76);
    v17 = FunctionModuleNoRef;
    goto LABEL_21;
  }
  v44 = v77;
  v45 = 0;
  v46 = v84;
  if ( v77 )
  {
    for ( j = 0; j < *(_DWORD *)(*(_QWORD *)(v46 + 80) + 104LL); ++j )
    {
      LODWORD(v75) = j;
      v65 = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, struct ID3D11LinkingNode *, _QWORD, _QWORD, __int64))v76->lpVtbl->PassValue)(
              v76,
              v78,
              j,
              *(_QWORD *)(v46 + 112),
              v75);
      FunctionModuleNoRef = v65;
      if ( v65 < 0 )
      {
        DoStackCapture(v65);
        CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v98);
        CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v93);
        goto LABEL_107;
      }
    }
    for ( k = 0; k < *(_DWORD *)(v46 + 8) + *(_DWORD *)v46; ++k )
    {
      FunctionModuleNoRef = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(v46 + 128) + 40LL))(
                              *(_QWORD *)(v46 + 128),
                              k,
                              k,
                              1);
      if ( FunctionModuleNoRef < 0 )
        goto LABEL_106;
      FunctionModuleNoRef = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(v46 + 128) + 56LL))(
                              *(_QWORD *)(v46 + 128),
                              k,
                              k,
                              1);
      if ( FunctionModuleNoRef < 0 )
        goto LABEL_106;
    }
    v44 = v77;
  }
  for ( m = 0; ; ++m )
  {
    if ( m >= *((_DWORD *)this + 17) )
    {
      v81 = 0;
      v48 = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, const struct _D3D11_PARAMETER_DESC near *const *, __int64, __int64 *))v76->lpVtbl->SetOutputSignature)(
              v76,
              &CShaderLinkingGraph::s_linkingShaderOutputSig,
              1,
              &v81);
      v17 = v48;
      if ( v48 < 0
        || (LODWORD(v75) = 0,
            v48 = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, _QWORD, __int64, __int64, __int64))v76->lpVtbl->PassValue)(
                    v76,
                    *(_QWORD *)(v90 + 112),
                    0xFFFFFFFFLL,
                    v81,
                    v75),
            v17 = v48,
            v48 < 0) )
      {
        DoStackCapture(v48);
      }
      else
      {
        v80 = 0;
        hModule = 0;
        v17 = DelayLoadedProc<long (*)(ID3D11Linker * *),DefaultHRESULTConverter>::EnsureLoaded(v49, &hModule);
        if ( v17 < 0 || (v17 = ((__int64 (__fastcall *)(__int64 *))hModule)(&v80), v17 < 0) )
        {
          DoStackCapture(v17);
        }
        else
        {
          v83 = 0;
          v50 = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, __int64 *, _QWORD))v76->lpVtbl->CreateModuleInstance)(
                  v76,
                  &v83,
                  0);
          v51 = v50;
          if ( v50 < 0 )
          {
            DoStackCapture(v50);
            if ( v83 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
            if ( v80 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
            if ( v81 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
            CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v98);
            CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v93);
            v33 = 8;
            v34 = v104;
            do
            {
              v34 -= 8;
              ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(v34);
              --v33;
            }
            while ( v33 );
            if ( v78 )
              ((void (__fastcall *)(struct ID3D11LinkingNode *))v78->lpVtbl->Release)(v78);
            if ( v76 )
              ((void (__fastcall *)(struct ID3D11FunctionLinkingGraph *))v76->lpVtbl->Release)(v76);
            v35 = v82;
            if ( v82 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
            if ( (Microsoft_Windows_D2D1EnableBits & 2) != 0 )
              McTemplateU0q_EventWriteTransfer(v35, &EffectShaderLinking_Stop, v12);
            return v51;
          }
          v52 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v80 + 32LL))(v80, v82);
          v17 = v52;
          if ( v52 >= 0 )
          {
            for ( n = 0; n < *((_DWORD *)this + 17); ++n )
            {
              v54 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v80 + 32LL))(
                      v80,
                      *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 14) + 8LL * n) + 128LL));
              FunctionModuleNoRef = v54;
              if ( v54 < 0 )
              {
                DoStackCapture(v54);
                ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v83);
                ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v80);
                ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v81);
                goto LABEL_114;
              }
            }
            v24 = *((_DWORD *)this + 24) < 40960;
            v25 = "ps_4_0";
            v86 = 0;
            if ( v24 )
              v25 = "ps_4_0_level_9_1";
            v88 = 0;
            if ( (*(int (__fastcall **)(__int64, __int64, const char *, const char *, _DWORD, struct ID3D10Blob **, __int64 *))(*(_QWORD *)v80 + 24LL))(
                   v80,
                   v83,
                   "main",
                   v25,
                   0,
                   &v86,
                   &v88) < 0 )
            {
              v70 = *((_QWORD *)this + 24);
              v84 = 0;
              v71 = CHash<CLinkedShaderSignature,CRefCountPtr<CPixelShader>,CLinkedShaderSignatureTraits,CDefaultTraits<CRefCountPtr<CPixelShader>>>::Add<CLinkedShaderSignature,ATL::CComPtr<CPixelShader>>(
                      v70,
                      this,
                      &v84);
              v17 = v71;
              if ( v71 < 0 )
                DoStackCapture(v71);
              ATL::CComPtr<CPixelShader>::~CComPtr<CPixelShader>(&v84);
            }
            else
            {
              v26 = CShaderLinkingGraph::AddToCache(this, this, v86, v91);
              v17 = v26;
              if ( v26 < 0 )
              {
                DoStackCapture(v26);
                if ( v88 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v88 + 16LL))(v88);
                if ( v86 )
                  ((void (__fastcall *)(struct ID3D10Blob *))v86->lpVtbl->Release)(v86);
                if ( v83 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
                if ( v80 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
                if ( v81 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
                CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v98);
                CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v93);
                v27 = 8;
                v28 = v104;
                do
                {
                  v28 -= 8;
                  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(v28);
                  --v27;
                }
                while ( v27 );
                if ( v78 )
                  ((void (__fastcall *)(struct ID3D11LinkingNode *))v78->lpVtbl->Release)(v78);
                if ( v76 )
                  ((void (__fastcall *)(struct ID3D11FunctionLinkingGraph *))v76->lpVtbl->Release)(v76);
                v29 = v82;
                if ( v82 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v82 + 16LL))(v82);
                if ( (Microsoft_Windows_D2D1EnableBits & 2) != 0 )
                  McTemplateU0q_EventWriteTransfer(v29, &EffectShaderLinking_Stop, v12);
                return (unsigned int)v17;
              }
              *v92 = 1;
            }
            ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v88);
            ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v86);
            goto LABEL_31;
          }
          DoStackCapture(v52);
LABEL_31:
          ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v83);
        }
        ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v80);
      }
      ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v81);
      CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v98);
      CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v93);
      goto LABEL_34;
    }
    v73 = *(_QWORD *)(*((_QWORD *)this + 14) + 8LL * m);
    if ( v73 != v46 || !v44 )
      break;
LABEL_168:
    ;
  }
  if ( *(_DWORD *)v73 )
    v45 = *(_DWORD *)(*(_QWORD *)(v73 + 80) + 124LL);
  v60 = *(_QWORD *)(v73 + 80);
  v79 = v45;
  if ( *(int *)(v60 + 116) >= 0 )
  {
    LODWORD(v75) = *(_DWORD *)(v60 + 116);
    v68 = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, struct ID3D11LinkingNode *, __int64, _QWORD, __int64))v76->lpVtbl->PassValue)(
            v76,
            v78,
            1,
            *(_QWORD *)(v73 + 112),
            v75);
    FunctionModuleNoRef = v68;
    if ( v68 < 0 )
    {
      DoStackCapture(v68);
LABEL_114:
      CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v98);
      CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v93);
      goto LABEL_107;
    }
  }
  for ( ii = 0; ; ii = (unsigned int)(ii + 1) )
  {
    if ( (unsigned int)ii >= *(_DWORD *)v73 )
    {
      v46 = v84;
      v45 = 0;
      v44 = v77;
      goto LABEL_168;
    }
    LODWORD(v75) = ii + v45;
    v57 = *(_QWORD *)(v73 + 112);
    v58 = *(_QWORD *)(*(_QWORD *)(v73 + 48) + 8 * ii);
    if ( v58 )
    {
      v59 = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, _QWORD, __int64, __int64, __int64))v76->lpVtbl->PassValue)(
              v76,
              *(_QWORD *)(v58 + 112),
              0xFFFFFFFFLL,
              v57,
              v75);
      goto LABEL_116;
    }
    v74 = *(_QWORD *)(v73 + 24);
    if ( !*(_BYTE *)(*(_QWORD *)(v73 + 80) + 8 * ii + 128) )
      break;
    v59 = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, _QWORD, __int64, __int64, __int64))v76->lpVtbl->PassValue)(
            v76,
            v103[*(unsigned int *)(v74 + 4 * ii)],
            0xFFFFFFFFLL,
            v57,
            v75);
LABEL_116:
    v55 = v59;
    if ( v59 < 0 )
      goto LABEL_117;
    v45 = v79;
  }
  v69 = *(_DWORD *)(v74 + 4 * ii);
  v55 = ((__int64 (__fastcall *)(struct ID3D11FunctionLinkingGraph *, struct ID3D11LinkingNode *, _QWORD))v76->lpVtbl->PassValue)(
          v76,
          v78,
          v69 + 2);
  if ( v55 >= 0 )
  {
    v55 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, __int64))(**(_QWORD **)(v73 + 128) + 40LL))(
            *(_QWORD *)(v73 + 128),
            v69,
            (unsigned int)ii,
            1,
            v75);
    if ( v55 >= 0 )
    {
      v59 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(v73 + 128) + 56LL))(
              *(_QWORD *)(v73 + 128),
              v69,
              (unsigned int)ii,
              1);
      goto LABEL_116;
    }
  }
LABEL_117:
  DoStackCapture(v55);
  CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v98);
  CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(&v93);
  `vector destructor iterator'(v103, 8u, 8u, ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>);
  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v78);
  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v76);
  v17 = v55;
LABEL_21:
  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v82);
  EventClass_EffectShaderLinking::~EventClass_EffectShaderLinking((EventClass_EffectShaderLinking *)&v85);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800a6aa0  mov     [rsp-8+arg_10], rbx
0x1800a6aa5  push    rbp
0x1800a6aa6  push    rsi
0x1800a6aa7  push    rdi
0x1800a6aa8  push    r12
0x1800a6aaa  push    r13
0x1800a6aac  push    r14
0x1800a6aae  push    r15
0x1800a6ab0  lea     rbp, [rsp-0F0h]
0x1800a6ab8  sub     rsp, 1F0h
0x1800a6abf  mov     rax, cs:__security_cookie
0x1800a6ac6  xor     rax, rsp
0x1800a6ac9  mov     [rbp+120h+var_40], rax
0x1800a6ad0  mov     rbx, [rbp+120h+arg_20]
0x1800a6ad7  xor     r13d, r13d
0x1800a6ada  mov     [r9], r13b
0x1800a6add  mov     r14, r9
0x1800a6ae0  mov     [rbp+120h+var_160], r9
0x1800a6ae4  mov     r15b, r8b
0x1800a6ae7  mov     rdi, rdx
0x1800a6aea  mov     [rbp+120h+var_178], rdx
0x1800a6aee  mov     [rbx], r13
0x1800a6af1  mov     rsi, rcx
0x1800a6af4  mov     [rbp+120h+var_168], rbx
0x1800a6af8  cmp     [rcx+44h], r13d
0x1800a6afc  jz      short loc_1800A6B1E
0x1800a6afe  call    ?UpdateSignature@CShaderLinkingGraph@@IEAAJXZ; CShaderLinkingGraph::UpdateSignature(void)
0x1800a6b03  mov     r8, rbx; struct CPixelShader **
0x1800a6b06  mov     rdx, rsi; struct CLinkedShaderSignature *
0x1800a6b09  mov     rcx, rsi; this
0x1800a6b0c  call    ?FindInCache@CShaderLinkingGraph@@IEBAJAEBVCLinkedShaderSignature@@PEAPEAVCPixelShader@@@Z; CShaderLinkingGraph::FindInCache(CLinkedShaderSignature const &,CPixelShader * *)
0x1800a6b11  test    eax, eax
0x1800a6b13  js      short loc_1800A6B4A
0x1800a6b15  cmp     [rbx], r13
0x1800a6b18  setnz   al
0x1800a6b1b  mov     [r14], al
0x1800a6b1e  xor     eax, eax
0x1800a6b20  mov     rcx, [rbp+120h+var_40]
0x1800a6b27  xor     rcx, rsp; StackCookie
0x1800a6b2a  call    __security_check_cookie
0x1800a6b2f  mov     rbx, [rsp+220h+arg_10]
0x1800a6b37  add     rsp, 1F0h
0x1800a6b3e  pop     r15
0x1800a6b40  pop     r14
0x1800a6b42  pop     r13
0x1800a6b44  pop     r12
0x1800a6b46  pop     rdi
0x1800a6b47  pop     rsi
0x1800a6b48  pop     rbp
0x1800a6b49  retn
0x1800a6b4a  test    byte ptr cs:Microsoft_Windows_D2D1EnableBits, 2
0x1800a6b51  mov     ebx, [rsi+44h]
0x1800a6b54  mov     [rbp+120h+var_198], ebx
0x1800a6b57  jnz     loc_1800A7735
0x1800a6b5d  mov     rcx, [rsi+70h]
0x1800a6b61  mov     r12d, [rsi+90h]
0x1800a6b68  mov     [rsp+220h+var_1C8], r12d
0x1800a6b6d  mov     rax, [rcx]
0x1800a6b70  mov     [rbp+120h+var_170], rax
0x1800a6b74  test    r15b, r15b
0x1800a6b77  jnz     loc_1800A6C56
0x1800a6b7d  mov     rax, [rdi]
0x1800a6b80  lea     r8, [rsp+220h+var_1B0]
0x1800a6b85  lea     rdx, word_18037105A
0x1800a6b8c  mov     [rbp+120h+var_1A0], r13
0x1800a6b90  mov     rcx, rdi
0x1800a6b93  mov     [rsp+220h+var_1B0], 0
0x1800a6b9c  mov     rax, [rax+18h]
0x1800a6ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6ba5  mov     edi, eax
0x1800a6ba7  test    eax, eax
0x1800a6ba9  js      loc_1800A6C97
0x1800a6baf  test    r12d, r12d
0x1800a6bb2  jnz     loc_1800A74B5
0x1800a6bb8  mov     r14, cs:qword_1805DB3F0
0x1800a6bbf  mov     [rsp+220h+var_1E0], 0
0x1800a6bc8  test    r14, r14
0x1800a6bcb  jz      loc_1800A7749
0x1800a6bd1  lea     rdx, [rsp+220h+var_1E0]
0x1800a6bd6  xor     ecx, ecx
0x1800a6bd8  mov     rax, r14
0x1800a6bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6be0  mov     edi, eax
0x1800a6be2  test    eax, eax
0x1800a6be4  js      loc_1800A6C6C
0x1800a6bea  mov     [rsp+220h+var_1D0], 0
0x1800a6bf3  lea     rdi, [rbp+120h+var_90]
0x1800a6bfa  mov     r14d, 8
0x1800a6c00  mov     rcx, rdi; void *
0x1800a6c03  call    ??0?$unique_object@PEAVCHwVertexBufferWriter@@@win_scope@@QEAA@XZ; win_scope::unique_object<CHwVertexBufferWriter *>::unique_object<CHwVertexBufferWriter *>(void)
0x1800a6c08  add     rdi, 8
0x1800a6c0c  sub     r14, 1
0x1800a6c10  jnz     short loc_1800A6C00
0x1800a6c12  test    r15b, r15b
0x1800a6c15  jnz     loc_1800A751C
0x1800a6c1b  xor     r13d, r13d
0x1800a6c1e  mov     rcx, [rsp+220h+var_1E0]
0x1800a6c23  lea     r8d, [r12+2]
0x1800a6c28  lea     r9, [rsp+220h+var_1D0]
0x1800a6c2d  lea     rdx, ?s_linkingShaderInputSig@CShaderLinkingGraph@@0QBU_D3D11_PARAMETER_DESC@@B; _D3D11_PARAMETER_DESC const near * const CShaderLinkingGraph::s_linkingShaderInputSig
0x1800a6c34  mov     rax, [rcx]
0x1800a6c37  mov     rax, [rax+20h]
0x1800a6c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6c40  mov     edi, eax
0x1800a6c42  test    eax, eax
0x1800a6c44  jns     loc_1800A6E98
0x1800a6c4a  mov     ecx, eax; int
0x1800a6c4c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a6c51  jmp     loc_1800A6D66
0x1800a6c56  mov     eax, [rsi+78h]
0x1800a6c59  dec     eax
0x1800a6c5b  mov     r13, [rcx+rax*8]
0x1800a6c5f  jmp     loc_1800A6B7D
0x1800a6c64  test    edi, edi
0x1800a6c66  jns     loc_1800A6BD1
0x1800a6c6c  mov     ecx, edi; int
0x1800a6c6e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a6c73  lea     rcx, [rsp+220h+var_1E0]; void *
0x1800a6c78  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800a6c7d  lea     rcx, [rsp+220h+var_1B0]; void *
0x1800a6c82  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800a6c87  lea     rcx, [rbp+120h+var_198]; this
0x1800a6c8b  call    ??1EventClass_EffectShaderLinking@@QEAA@XZ; EventClass_EffectShaderLinking::~EventClass_EffectShaderLinking(void)
0x1800a6c90  mov     eax, edi
0x1800a6c92  jmp     loc_1800A6B20
0x1800a6c97  mov     ecx, edi; int
0x1800a6c99  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a6c9e  mov     ecx, edi; int
0x1800a6ca0  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a6ca5  jmp     short loc_1800A6C7D
0x1800a6ca7  mov     rcx, [rsp+220h+var_1C0]
0x1800a6cac  lea     rdx, aPs40Level91; "ps_4_0_level_9_1"
0x1800a6cb3  cmp     dword ptr [rsi+60h], 0A000h
0x1800a6cba  lea     r9, aPs40; "ps_4_0"
0x1800a6cc1  mov     [rbp+120h+var_190], r15
0x1800a6cc5  lea     r8, aMain; "main"
0x1800a6ccc  cmovl   r9, rdx
0x1800a6cd0  mov     [rbp+120h+var_180], r15
0x1800a6cd4  mov     rax, [rcx]
0x1800a6cd7  lea     rdx, [rbp+120h+var_180]
0x1800a6cdb  mov     [rsp+220h+var_1F0], rdx
0x1800a6ce0  lea     rdx, [rbp+120h+var_190]
0x1800a6ce4  mov     [rsp+220h+var_1F8], rdx
0x1800a6ce9  mov     rdx, [rsp+220h+var_1A8]
0x1800a6cee  mov     rax, [rax+18h]
0x1800a6cf2  mov     dword ptr [rsp+220h+var_200], r15d
0x1800a6cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6cfc  mov     rdx, rsi; struct CLinkedShaderSignature *
0x1800a6cff  test    eax, eax
0x1800a6d01  js      loc_1800A7706
0x1800a6d07  mov     r9, [rbp+120h+var_168]; struct CPixelShader **
0x1800a6d0b  mov     rcx, rsi; this
0x1800a6d0e  mov     r8, [rbp+120h+var_190]; struct ID3D10Blob *
0x1800a6d12  call    ?AddToCache@CShaderLinkingGraph@@IEAAJAEBVCLinkedShaderSignature@@PEAUID3D10Blob@@PEAPEAVCPixelShader@@@Z; CShaderLinkingGraph::AddToCache(CLinkedShaderSignature const &,ID3D10Blob *,CPixelShader * *)
0x1800a6d17  mov     edi, eax
0x1800a6d19  test    eax, eax
0x1800a6d1b  js      short loc_1800A6D92
0x1800a6d1d  mov     rax, [rbp+120h+var_160]
0x1800a6d21  mov     byte ptr [rax], 1
0x1800a6d24  lea     rcx, [rbp+120h+var_180]; void *
0x1800a6d28  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800a6d2d  lea     rcx, [rbp+120h+var_190]; void *
0x1800a6d31  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800a6d36  lea     rcx, [rsp+220h+var_1A8]; void *
0x1800a6d3b  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800a6d40  lea     rcx, [rsp+220h+var_1C0]; void *
0x1800a6d45  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800a6d4a  lea     rcx, [rsp+220h+var_1B8]; void *
0x1800a6d4f  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800a6d54  lea     rcx, [rbp+120h+var_F0]
0x1800a6d58  call    ??1?$CArray@V?$CComPtr@UID3D11ModuleInstance@@@ATL@@V?$CDefaultTraits@V?$CComPtr@UID3D11ModuleInstance@@@ATL@@@@V?$CInitialAllocAllocator@$0EA@VCDefaultAllocator@@@@@@QEAA@XZ; CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(void)
0x1800a6d5d  lea     rcx, [rbp+120h+var_150]
0x1800a6d61  call    ??1?$CArray@V?$CComPtr@UID3D11ModuleInstance@@@ATL@@V?$CDefaultTraits@V?$CComPtr@UID3D11ModuleInstance@@@ATL@@@@V?$CInitialAllocAllocator@$0EA@VCDefaultAllocator@@@@@@QEAA@XZ; CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(void)
0x1800a6d66  mov     eax, 8
0x1800a6d6b  mov     r8d, eax; unsigned __int64
0x1800a6d6e  mov     edx, eax; unsigned __int64
0x1800a6d70  lea     r9, ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; void (*)(void *)
0x1800a6d77  lea     rcx, [rbp+120h+var_90]; void *
0x1800a6d7e  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800a6d83  lea     rcx, [rsp+220h+var_1D0]; void *
0x1800a6d88  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800a6d8d  jmp     loc_1800A6C73
0x1800a6d92  mov     ecx, edi; int
0x1800a6d94  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a6d99  mov     rcx, [rbp+120h+var_180]
0x1800a6d9d  test    rcx, rcx
0x1800a6da0  jz      short loc_1800A6DAE
0x1800a6da2  mov     rax, [rcx]
0x1800a6da5  mov     rax, [rax+10h]
0x1800a6da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6dae  mov     rcx, [rbp+120h+var_190]
0x1800a6db2  test    rcx, rcx
0x1800a6db5  jz      short loc_1800A6DC3
0x1800a6db7  mov     rax, [rcx]
0x1800a6dba  mov     rax, [rax+10h]
0x1800a6dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6dc3  mov     rcx, [rsp+220h+var_1A8]
0x1800a6dc8  test    rcx, rcx
0x1800a6dcb  jz      short loc_1800A6DD9
0x1800a6dcd  mov     rax, [rcx]
0x1800a6dd0  mov     rax, [rax+10h]
0x1800a6dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6dd9  mov     rcx, [rsp+220h+var_1C0]
0x1800a6dde  test    rcx, rcx
0x1800a6de1  jz      short loc_1800A6DEF
0x1800a6de3  mov     rax, [rcx]
0x1800a6de6  mov     rax, [rax+10h]
0x1800a6dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6def  mov     rcx, [rsp+220h+var_1B8]
0x1800a6df4  test    rcx, rcx
0x1800a6df7  jz      short loc_1800A6E05
0x1800a6df9  mov     rax, [rcx]
0x1800a6dfc  mov     rax, [rax+10h]
0x1800a6e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e05  lea     rcx, [rbp+120h+var_F0]
0x1800a6e09  call    ??1?$CArray@V?$CComPtr@UID3D11ModuleInstance@@@ATL@@V?$CDefaultTraits@V?$CComPtr@UID3D11ModuleInstance@@@ATL@@@@V?$CInitialAllocAllocator@$0EA@VCDefaultAllocator@@@@@@QEAA@XZ; CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(void)
0x1800a6e0e  lea     rcx, [rbp+120h+var_150]
0x1800a6e12  call    ??1?$CArray@V?$CComPtr@UID3D11ModuleInstance@@@ATL@@V?$CDefaultTraits@V?$CComPtr@UID3D11ModuleInstance@@@ATL@@@@V?$CInitialAllocAllocator@$0EA@VCDefaultAllocator@@@@@@QEAA@XZ; CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>::~CArray<ATL::CComPtr<ID3D11ModuleInstance>,CDefaultTraits<ATL::CComPtr<ID3D11ModuleInstance>>,CInitialAllocAllocator<64,CDefaultAllocator>>(void)
0x1800a6e17  mov     esi, 8
0x1800a6e1c  lea     r14, [rbp+120h+var_50]
0x1800a6e23  sub     r14, 8
0x1800a6e27  mov     rcx, r14; void *
0x1800a6e2a  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800a6e2f  sub     rsi, 1
0x1800a6e33  jnz     short loc_1800A6E23
0x1800a6e35  mov     rcx, [rsp+220h+var_1D0]
0x1800a6e3a  test    rcx, rcx
0x1800a6e3d  jz      short loc_1800A6E4B
0x1800a6e3f  mov     rax, [rcx]
0x1800a6e42  mov     rax, [rax+10h]
0x1800a6e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e4b  mov     rcx, [rsp+220h+var_1E0]
0x1800a6e50  test    rcx, rcx
0x1800a6e53  jz      short loc_1800A6E61
0x1800a6e55  mov     rax, [rcx]
0x1800a6e58  mov     rax, [rax+10h]
0x1800a6e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e61  mov     rcx, [rsp+220h+var_1B0]
0x1800a6e66  test    rcx, rcx
0x1800a6e69  jz      short loc_1800A6E77
0x1800a6e6b  mov     rax, [rcx]
0x1800a6e6e  mov     rax, [rax+10h]
0x1800a6e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6e77  test    byte ptr cs:Microsoft_Windows_D2D1EnableBits, 2
0x1800a6e7e  jz      loc_1800A6C90
0x1800a6e84  mov     r8d, ebx
0x1800a6e87  lea     rdx, EffectShaderLinking_Stop
0x1800a6e8e  call    McTemplateU0q_EventWriteTransfer
0x1800a6e93  jmp     loc_1800A6C90
0x1800a6e98  mov     r12, [rbp+120h+var_178]
0x1800a6e9c  mov     edi, r13d
0x1800a6e9f  mov     [rsp+220h+var_1D8], r13b
0x1800a6ea4  cmp     edi, [rsi+90h]
0x1800a6eaa  jnb     loc_1800A704F
0x1800a6eb0  mov     rax, [rsi+88h]
0x1800a6eb7  mov     r15d, edi
0x1800a6eba  lea     rcx, [r15+r15*4]
0x1800a6ebe  cmp     [rax+rcx*8+0Ch], r13b
0x1800a6ec3  jz      loc_1800A6F59
0x1800a6ec9  mov     r9d, edi
0x1800a6ecc  lea     r8, aSampleinputD; "SampleInput%d"
0x1800a6ed3  mov     edx, 10h; unsigned __int64
0x1800a6ed8  lea     rcx, [rbp+120h+var_50]; char *
0x1800a6edf  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800a6ee4  mov     r14d, eax
0x1800a6ee7  test    eax, eax
0x1800a6ee9  js      loc_1800A748F
0x1800a6eef  mov     rcx, [rsp+220h+var_1E0]
0x1800a6ef4  lea     rax, [rbp+120h+var_90]
0x1800a6efb  lea     r15, [rax+r15*8]
0x1800a6eff  mov     r8, r12
0x1800a6f02  lea     r9, [rbp+120h+var_50]
0x1800a6f09  mov     [rsp+220h+var_200], r15
0x1800a6f0e  lea     rdx, word_18037105A
0x1800a6f15  mov     rax, [rcx]
0x1800a6f18  mov     rax, [rax+30h]
0x1800a6f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6f21  mov     r14d, eax
0x1800a6f24  test    eax, eax
0x1800a6f26  js      loc_1800A748F
0x1800a6f2c  mov     rcx, [rsp+220h+var_1E0]
0x1800a6f31  lea     r8d, [rdi+2]
0x1800a6f35  mov     r9, [r15]
0x1800a6f38  mov     rdx, [rsp+220h+var_1D0]
0x1800a6f3d  mov     dword ptr [rsp+220h+var_200], r13d
0x1800a6f42  mov     rax, [rcx]
0x1800a6f45  mov     rax, [rax+38h]
0x1800a6f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6f4e  mov     r14d, eax
0x1800a6f51  test    eax, eax
0x1800a6f53  js      loc_1800A748F
0x1800a6f59  inc     edi
0x1800a6f5b  jmp     loc_1800A6EA4
0x1800a6f60  mov     ecx, r14d; int
0x1800a6f63  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800a6f68  mov     rcx, [rsp+220h+var_1A8]
0x1800a6f6d  test    rcx, rcx
0x1800a6f70  jz      short loc_1800A6F7E
0x1800a6f72  mov     rax, [rcx]
0x1800a6f75  mov     rax, [rax+10h]
  ... truncated ...
```
