# D3D11RegisterLayersAndCreateDevice(D3D11_EXTENSIONS const &,NDXGI::CUMDAdapter *,D3D_FEATURE_LEVEL,D3D_FEATURE_LEVEL,unsigned __int64,uint,ID3D11Device * *)

- ea: `0x180059bcc`
- end: `0x18005a56e`
- name: `?D3D11RegisterLayersAndCreateDevice@@YAJAEBUD3D11_EXTENSIONS@@PEAVCUMDAdapter@NDXGI@@W4D3D_FEATURE_LEVEL@@2_KIPEAPEAUID3D11Device@@@Z`
- size: `2466`
- prototype: `__int64 __fastcall(const struct D3D11_EXTENSIONS *, struct NDXGI::CUMDAdapter *, enum D3D_FEATURE_LEVEL, enum D3D_FEATURE_LEVEL, unsigned __int64, unsigned int, struct ID3D11Device **)`
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047a80`

## callees

- `0x18000bad0`
- `0x180022400`
- `0x1800229a0`
- `0x180047890`
- `0x1800484b8`
- `0x18004e694`
- `0x1800596f4`
- `0x180059bcc`
- `0x18005a574`
- `0x18005b4a8`
- `0x18005b6a4`
- `0x18005b6d0`
- `0x18005b7a0`
- `0x18005b90c`
- `0x18005ba3c`
- `0x18009d94c`
- `0x18009d98c`
- `0x1800a9d20`
- `0x1800ac684`
- `0x1800adef4`
- `0x1800b01a0`
- `0x1800b100c`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800eba98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebaa2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebaaf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebac6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebad8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebae9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebafc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebb09`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800eba98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebaa2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebaaf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebac6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebad8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebae9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebafc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ebb09`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a180`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005a180`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a493`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ebb46`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005a493`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ebb46`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180059d24`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180059d6e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180059d24`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180059d6e`
- `ext-ms-mf-pal-l2-1-0!XboxIsAsyncComputeOnlyDevice` at `0x18005a448`
- `ext-ms-mf-pal-l2-1-0!XboxIsAsyncComputeOnlyDevice` at `0x18005a448`
- `ext-ms-mf-pal-l2-1-0!XboxGetAsyncComputeD3DCreationFlag` at `0x18005a463`
- `ext-ms-mf-pal-l2-1-0!XboxGetAsyncComputeD3DCreationFlag` at `0x18005a463`

## string_xrefs

- `0x18005a21c`: `D3D11_3SDKLayers.dll`
- `0x1800ebb3c`: `D3D11TranslateCreateDevice`
- `0x1800eba91`: `D3D11CreateDevice: Flags (0x`
- `0x1800ebaa8`: `) were specified which require the D3D11 SDK Layers for Windows 10, but they are not present on the system.\nThese flags must be removed, or the Windows 10 SDK must be installed.\n`
- `0x1800ebad1`: `D3D11_CREATE_DEVICE_DEBUG`
- `0x1800ebaf5`: `D3D11_CREATE_DEVICE_DEBUGGABLE`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall D3D11RegisterLayersAndCreateDevice(
        const struct D3D11_EXTENSIONS *a1,
        struct NDXGI::CUMDAdapter *a2,
        enum D3D_FEATURE_LEVEL a3,
        enum D3D_FEATURE_LEVEL a4,
        unsigned __int64 a5,
        unsigned int a6,
        struct ID3D11Device **a7)
{
  struct ID3D11Device **v8; // r13
  int v9; // eax
  HMODULE v10; // rbx
  unsigned int v11; // r12d
  unsigned int v12; // edi
  __int64 v13; // r9
  bool v14; // zf
  __int64 v15; // rdi
  __int64 v16; // r9
  __int128 v17; // rax
  unsigned __int64 v18; // r14
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // r12
  unsigned __int64 v21; // r13
  unsigned int v22; // r15d
  _DWORD *v23; // rsi
  unsigned __int64 v24; // rcx
  __int64 v25; // r8
  unsigned __int64 v26; // rax
  __int64 v27; // rdi
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rax
  __int64 v30; // rcx
  int v31; // r14d
  unsigned __int64 v32; // rdx
  __int64 v33; // rdi
  __int64 v34; // rsi
  __int64 v35; // rdi
  __int64 v36; // rdi
  unsigned __int64 v37; // rcx
  unsigned __int64 v38; // r8
  __int64 v39; // rdi
  _BYTE *v40; // r10
  char *v41; // rcx
  _DWORD *v42; // r8
  int LayeredDevice; // eax
  __int64 v45; // rdi
  __int64 v46; // rcx
  int v47; // r14d
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // rax
  unsigned __int64 v50; // rcx
  unsigned __int64 v51; // rcx
  unsigned __int64 v52; // rax
  unsigned __int64 v53; // rdx
  int v54; // eax
  __int64 v55; // rdi
  unsigned __int64 v56; // rdx
  unsigned __int64 v57; // rax
  unsigned __int64 v58; // rcx
  __int64 (*ProcAddress)(void); // r15
  bool v60; // r9
  FARPROC v61; // rsi
  _DWORD *v62; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD *v63; // [rsp+38h] [rbp-C8h]
  __int64 v64; // [rsp+40h] [rbp-C0h]
  __int128 v65; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v66; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v67; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v68; // [rsp+70h] [rbp-90h] BYREF
  __int64 v69; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v70; // [rsp+80h] [rbp-80h] BYREF
  enum D3D_FEATURE_LEVEL v71; // [rsp+88h] [rbp-78h]
  enum D3D_FEATURE_LEVEL v72; // [rsp+8Ch] [rbp-74h]
  __int64 v73; // [rsp+90h] [rbp-70h] BYREF
  HMODULE v74; // [rsp+98h] [rbp-68h]
  struct ID3D11Device **v75; // [rsp+A0h] [rbp-60h]
  _QWORD v76[5]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v77; // [rsp+D0h] [rbp-30h]
  enum D3D_FEATURE_LEVEL v78; // [rsp+D4h] [rbp-2Ch]
  enum D3D_FEATURE_LEVEL v79; // [rsp+D8h] [rbp-28h]
  int v80; // [rsp+DCh] [rbp-24h]
  char v81[16]; // [rsp+E0h] [rbp-20h] BYREF
  wchar_t pszDest[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v83; // [rsp+F8h] [rbp-8h]

  v72 = a4;
  v71 = a3;
  v8 = a7;
  v75 = a7;
  if ( dword_18022B910 < 7 )
    dword_18022B914 = 7;
  dword_18022B910 = 7;
  std::vector<CCommandList *>::vector<CCommandList *>(&v62);
  std::vector<CCommandList *>::vector<CCommandList *>(&v65);
  v68 = (unsigned int)(*((_DWORD *)a1 + 2) + 10);
  if ( v68 > (v64 - (__int64)v62) >> 2 )
    std::vector<unsigned int>::_Reallocate<1>(&v62, &v68);
  v68 = (unsigned int)(*((_DWORD *)a1 + 2) + 10);
  if ( v68 > (v66 - (__int64)v65) >> 2 )
    std::vector<unsigned int>::_Reallocate<1>(&v65, &v68);
  v9 = D3D11CoreRegisterLayers(&unk_1801DA490, 3);
  ThrowFailure(v9);
  std::vector<unsigned int>::_Insert_counted_range<unsigned int const *>(
    &v65,
    *((_QWORD *)&v65 + 1),
    *(_QWORD *)a1,
    *((unsigned int *)a1 + 2));
  LODWORD(v67) = -1;
  if ( *((_QWORD *)&v65 + 1) == v66 )
  {
    std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(&v65, *((_QWORD *)&v65 + 1), &v67);
  }
  else
  {
    **((_DWORD **)&v65 + 1) = -1;
    *((_QWORD *)&v65 + 1) += 4LL;
  }
  v10 = 0;
  v68 = 0;
  v74 = 0;
  v11 = a6;
  v12 = a6 & 0x37FFE656;
  if ( (unsigned __int8)IsXboxIsAsyncComputeOnlyDevicePresent()
    && (unsigned int)XboxIsAsyncComputeOnlyDevice(a6)
    && (unsigned __int8)IsXboxIsAsyncComputeOnlyDevicePresent() )
  {
    v12 &= ~(unsigned int)XboxGetAsyncComputeD3DCreationFlag();
  }
  v69 = 0;
  if ( (a6 & 0x80u) != 0 )
  {
    v14 = v12 == 0;
  }
  else
  {
    if ( v12
      || InitOnceExecuteOnce(&InitOnce, CModule::InitOnceGetProcAddress, 0, &Context)
      && *(_QWORD *)Context
      && (*(unsigned int (__fastcall **)(const char *, __int64 *))Context)("RequireSDKLayers", &v69)
      && v69 )
    {
      goto LABEL_75;
    }
    if ( !InitOnceExecuteOnce(&InitOnce, CModule::InitOnceGetProcAddress, 0, &Context)
      || !*(_QWORD *)Context
      || !(*(unsigned int (__fastcall **)(const char *, __int64 *))Context)("EnableDriverVerifier", &v69) )
    {
      goto LABEL_20;
    }
    v14 = v69 == 0;
  }
  if ( v14 )
    goto LABEL_20;
LABEL_75:
  v10 = CModule::SDKLoadLibraryW((CModule *)&g_Module, L"D3D11_3SDKLayers.dll");
  v68 = (unsigned __int64)v10;
  v74 = v10;
  if ( !v10 )
  {
    if ( !v12 )
      goto LABEL_20;
    StringCbPrintfW(pszDest, 0x12u, L"%x", v12);
    OutputDebugStringW(L"D3D11CreateDevice: Flags (0x");
    OutputDebugStringW(pszDest);
    OutputDebugStringW(
      L") were specified which require the D3D11 SDK Layers for Windows 10, but they are not present on the system.\n"
       "These flags must be removed, or the Windows 10 SDK must be installed.\n");
    if ( (a6 & 2) == 0 && (a6 & 0x40) == 0 )
      goto LABEL_124;
    OutputDebugStringW(L"Flags include: ");
    if ( (a6 & 2) != 0 )
    {
      OutputDebugStringW(L"D3D11_CREATE_DEVICE_DEBUG");
      if ( (a6 & 0x40) != 0 )
      {
        OutputDebugStringW(L" | ");
LABEL_122:
        OutputDebugStringW(L"D3D11_CREATE_DEVICE_DEBUGGABLE");
      }
    }
    else if ( (a6 & 0x40) != 0 )
    {
      goto LABEL_122;
    }
    OutputDebugStringW(L"\n");
LABEL_124:
    CModule::RecordJournal(
      (CModule *)&g_Module,
      0x887A002D,
      "Application requested debug layers but it was not available.",
      v60,
      1);
    ThrowFailure(-2005270483);
  }
  ProcAddress = GetProcAddress(v10, "D3D11RegisterLayers");
  if ( !ProcAddress )
    ThrowFailure(-2147467259);
  v61 = GetProcAddress(v10, "D3D11TranslateCreateDevice");
  if ( !v61 )
    ThrowFailure(-2147467259);
  v51 = (v64 - (__int64)v62) >> 2;
  v45 = (__int64)v63;
  v52 = v63 - v62;
  if ( v51 < v52 )
  {
    v45 = (__int64)&v62[v51];
    goto LABEL_82;
  }
  if ( v51 > v52 )
  {
    v45 = (__int64)&v63[v51 - v52];
    v46 = (__int64)v63;
    goto LABEL_81;
  }
  while ( 1 )
  {
    v67 = (v45 - (__int64)v62) >> 2;
    v47 = ((__int64 (__fastcall *)(_QWORD, unsigned __int64 *))v61)(a6, &v67);
    if ( v47 != -2147024774 )
      break;
    v48 = (v64 - (__int64)v62) >> 2;
    v49 = 2 * v48;
    v45 = (__int64)v63;
    v50 = v63 - v62;
    if ( 2 * v48 < v50 )
    {
      v45 = (__int64)&v62[2 * v48];
      goto LABEL_82;
    }
    if ( 2 * v48 > v50 )
    {
      if ( v49 <= v48 )
      {
        v45 = (__int64)&v63[v49 - v50];
        v46 = (__int64)v63;
LABEL_81:
        std::_Zero_range<unsigned __int64 *>(v46, v45);
LABEL_82:
        v63 = (_DWORD *)v45;
        continue;
      }
      std::vector<unsigned int>::_Resize_reallocate<std::_Value_init_tag>(&v62, 2 * v48, v62);
      v45 = (__int64)v63;
    }
  }
  v53 = v63 - v62;
  if ( v67 >= v53 )
  {
    if ( v67 > v53 )
    {
      if ( v67 > (v64 - (__int64)v62) >> 2 )
      {
        std::vector<unsigned int>::_Resize_reallocate<std::_Value_init_tag>(&v62, v67, v62);
      }
      else
      {
        v55 = (__int64)&v63[v67 - v53];
        std::_Zero_range<unsigned __int64 *>(v63, v55);
        v63 = (_DWORD *)v55;
      }
    }
  }
  else
  {
    v63 = &v62[v67];
  }
  ThrowFailure(v47);
  std::vector<unsigned int>::insert<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned int>>>,0>(
    (unsigned int)&v65,
    (unsigned int)&v73,
    DWORD2(v65),
    (_DWORD)v62,
    (__int64)v63);
  v54 = ProcAddress();
  ThrowFailure(v54);
LABEL_20:
  LOBYTE(v13) = 0;
  std::_Sort_unchecked<unsigned int *,std::less<void>>(
    v65,
    *((_QWORD *)&v65 + 1),
    (__int64)(*((_QWORD *)&v65 + 1) - v65) >> 2,
    v13);
  v15 = *((_QWORD *)&v65 + 1);
  std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned int>>>,std::equal_to<void>>(
    &v70,
    v65,
    *((_QWORD *)&v65 + 1));
  *((_QWORD *)&v17 + 1) = *((_QWORD *)&v65 + 1);
  if ( v70 != v15 )
  {
    *((_QWORD *)&v17 + 1) = std::_Copy_memmove<_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *>(
                              v15,
                              *((_QWORD *)&v65 + 1),
                              v70);
    *((_QWORD *)&v65 + 1) = *((_QWORD *)&v17 + 1);
  }
  v18 = 0;
  v70 = 0;
  *(_QWORD *)&v17 = v65;
  v19 = (__int64)(*((_QWORD *)&v17 + 1) - v65) >> 2;
  if ( v19 )
  {
    do
    {
      v20 = v19;
      v21 = v18;
      if ( v18 < v19 )
      {
        do
        {
          v22 = *(_DWORD *)(v17 + 4 * v21);
          v23 = g_D3D11RegisteredLayers;
          v24 = ((_BYTE *)*(&g_D3D11RegisteredLayers + 1) - (_BYTE *)g_D3D11RegisteredLayers) >> 5;
          while ( (__int64)v24 > 0 )
          {
            v25 = 8 * (v24 >> 1);
            if ( v23[v25] < v22 )
            {
              v23 = (_DWORD *)((char *)v23 + v25 * 4 + 32);
              v24 += -1LL - (v24 >> 1);
            }
            else
            {
              v24 >>= 1;
            }
          }
          if ( v23 == *(&g_D3D11RegisteredLayers + 1) || *v23 != v22 )
            ThrowFailure(-2147024809);
          v26 = (v64 - (__int64)v62) >> 2;
          v27 = (__int64)v63;
          v28 = v63 - v62;
          if ( v26 < v28 )
          {
            v27 = (__int64)&v62[v26];
          }
          else
          {
            if ( v26 <= v28 )
              goto LABEL_36;
            v29 = v26 - v28;
            v30 = (__int64)v63;
LABEL_34:
            v27 += 4 * v29;
            std::_Zero_range<unsigned __int64 *>(v30, v27);
          }
LABEL_35:
          v63 = (_DWORD *)v27;
LABEL_36:
          while ( 1 )
          {
            v67 = (v27 - (__int64)v62) >> 2;
            v31 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int64 *))v23 + 1))(v22, &v67);
            if ( v31 != -2147024774 )
              break;
            v56 = (v64 - (__int64)v62) >> 2;
            v57 = 2 * v56;
            v27 = (__int64)v63;
            v58 = v63 - v62;
            if ( 2 * v56 < v58 )
            {
              v27 = (__int64)&v62[2 * v56];
              goto LABEL_35;
            }
            if ( 2 * v56 > v58 )
            {
              if ( v57 <= v56 )
              {
                v29 = v57 - v58;
                v30 = (__int64)v63;
                goto LABEL_34;
              }
              std::vector<unsigned int>::_Resize_reallocate<std::_Value_init_tag>(&v62, 2 * v56, v62);
              v27 = (__int64)v63;
            }
          }
          v32 = v63 - v62;
          if ( v67 < v32 )
          {
            v63 = &v62[v67];
          }
          else if ( v67 > v32 )
          {
            if ( v67 > (v64 - (__int64)v62) >> 2 )
            {
              std::vector<unsigned int>::_Resize_reallocate<std::_Value_init_tag>(&v62, v67, v62);
            }
            else
            {
              v33 = (__int64)&v63[v67 - v32];
              std::_Zero_range<unsigned __int64 *>(v63, v33);
              v63 = (_DWORD *)v33;
            }
          }
          ThrowFailure(v31);
          std::vector<unsigned int>::_Insert_counted_range<unsigned int const *>(
            &v65,
            *((_QWORD *)&v65 + 1),
            v62,
            v63 - v62);
          ++v21;
          *(_QWORD *)&v17 = v65;
        }
        while ( v21 < v20 );
        *((_QWORD *)&v17 + 1) = *((_QWORD *)&v65 + 1);
        v18 = v70;
      }
      v34 = 4 * v20;
      LOBYTE(v16) = 0;
      std::_Sort_unchecked<unsigned int *,std::less<void>>(
        v17 + 4 * v20,
        *((_QWORD *)&v17 + 1),
        (__int64)(*((_QWORD *)&v17 + 1) - v17 - 4 * v20) >> 2,
        v16);
      v35 = *((_QWORD *)&v65 + 1);
      std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned int>>>,std::equal_to<void>>(
        &v73,
        4 * v20 + v65,
        *((_QWORD *)&v65 + 1));
      if ( v73 != v35 )
        *((_QWORD *)&v65 + 1) = std::_Copy_memmove<_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *>(
                                  v35,
                                  *((_QWORD *)&v65 + 1),
                                  v73);
      std::inplace_merge<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned int>>>>(
        v65,
        v65 + 4 * v18,
        v65 + v34);
      v36 = *((_QWORD *)&v65 + 1);
      *(_QWORD *)pszDest = v65;
      v83 = v65 + v34;
      *(_QWORD *)&v17 = std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned int>>>,in_sorted_range<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<unsigned int>>>>>(
                          v81,
                          v34 + v65,
                          *((_QWORD *)&v65 + 1),
                          pszDest);
      *((_QWORD *)&v17 + 1) = *((_QWORD *)&v65 + 1);
      if ( *(_QWORD *)v17 != v36 )
      {
        *((_QWORD *)&v17 + 1) = std::_Copy_memmove<_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 const *,_D3DKMT_MULTIPLANE_OVERLAY_ATTRIBUTES3 *>(
                                  v36,
                                  *((_QWORD *)&v65 + 1),
                                  *(_QWORD *)v17);
        *((_QWORD *)&v65 + 1) = *((_QWORD *)&v17 + 1);
      }
      v18 = v20;
      v70 = v20;
      *(_QWORD *)&v17 = v65;
      v19 = (__int64)(*((_QWORD *)&v17 + 1) - v65) >> 2;
    }
    while ( v20 != v19 );
    v10 = (HMODULE)v68;
    v11 = a6;
    v8 = v75;
  }
  v37 = (__int64)(*((_QWORD *)&v17 + 1) - v17) >> 2;
  v38 = v63 - v62;
  if ( v37 < v38 )
  {
    v63 = &v62[v37];
  }
  else if ( v37 > v38 )
  {
    if ( v37 > (v64 - (__int64)v62) >> 2 )
    {
      std::vector<unsigned int>::_Resize_reallocate<std::_Value_init_tag>(&v62, v37, v38);
    }
    else
    {
      v39 = (__int64)&v63[v37 - v38];
      std::_Zero_range<unsigned __int64 *>(v63, v39);
      v63 = (_DWORD *)v39;
    }
    v17 = v65;
  }
  v40 = g_D3D11RegisteredLayers;
  v41 = (char *)g_D3D11RegisteredLayers;
  v42 = v62;
  while ( (_QWORD)v17 != *((_QWORD *)&v17 + 1) )
  {
    while ( *(_DWORD *)v41 != *(_DWORD *)v17 )
      v41 += 32;
    *v42 = (v41 - v40) >> 5;
    v41 += 32;
    *(_QWORD *)&v17 = v17 + 4;
    ++v42;
  }
  if ( v8 )
  {
    v80 = 0;
    v76[0] = 0;
    v76[1] = 0;
    v76[2] = v65;
    v76[3] = v62;
    v76[4] = a5;
    v77 = v11;
    v78 = v71;
    v79 = v72;
    if ( dword_18022B910 < 8 )
      dword_18022B914 = 8;
    dword_18022B910 = 8;
    LayeredDevice = D3D11CoreCreateLayeredDevice(
                      (unsigned int)v76,
                      56,
                      0,
                      (unsigned int)&GUID_db6f6ddb_ac77_4e88_8253_819df9bbf140,
                      (__int64)v8);
    if ( LayeredDevice == -2147467262 )
      LayeredDevice = -2005270524;
    ThrowFailure(LayeredDevice);
    v10 = 0;
  }
  if ( v10 )
    FreeLibrary(v10);
  if ( (_QWORD)v65 )
  {
    std::_Deallocate<16>(v65, (v66 - v65) & 0xFFFFFFFFFFFFFFFCuLL);
    v65 = 0;
    v66 = 0;
  }
  if ( v62 )
    std::_Deallocate<16>(v62, (v64 - (_QWORD)v62) & 0xFFFFFFFFFFFFFFFCuLL);
  return v8 == 0;
}

```

## disassembly

```asm
0x180059bcc  mov     [rsp-8+arg_8], rbx
0x180059bd1  push    rbp
0x180059bd2  push    rsi
0x180059bd3  push    rdi
0x180059bd4  push    r12
0x180059bd6  push    r13
0x180059bd8  push    r14
0x180059bda  push    r15
0x180059bdc  lea     rbp, [rsp-20h]
0x180059be1  sub     rsp, 120h
0x180059be8  mov     rax, cs:__security_cookie
0x180059bef  xor     rax, rsp
0x180059bf2  mov     [rbp+50h+var_40], rax
0x180059bf6  mov     [rbp+50h+var_C4], r9d
0x180059bfa  mov     [rbp+50h+var_C8], r8d
0x180059bfe  mov     rbx, rcx
0x180059c01  mov     r13, [rbp+50h+arg_30]
0x180059c08  mov     [rbp+50h+var_B0], r13
0x180059c0c  mov     eax, 7
0x180059c11  cmp     cs:dword_18022B910, eax
0x180059c17  jl      loc_18005A279
0x180059c1d  mov     cs:dword_18022B910, eax
0x180059c23  lea     rcx, [rsp+150h+var_120]; void *
0x180059c28  call    ??0?$vector@PEAVCCommandList@@V?$allocator@PEAVCCommandList@@@std@@@std@@QEAA@XZ; std::vector<CCommandList *>::vector<CCommandList *>(void)
0x180059c2d  nop
0x180059c2e  lea     rcx, [rsp+150h+var_100]; void *
0x180059c33  call    ??0?$vector@PEAVCCommandList@@V?$allocator@PEAVCCommandList@@@std@@@std@@QEAA@XZ; std::vector<CCommandList *>::vector<CCommandList *>(void)
0x180059c38  nop
0x180059c39  mov     ecx, [rbx+8]
0x180059c3c  add     ecx, 0Ah
0x180059c3f  mov     [rsp+150h+var_E0], rcx
0x180059c44  mov     rax, [rsp+150h+var_110]
0x180059c49  sub     rax, [rsp+150h+var_120]
0x180059c4e  sar     rax, 2
0x180059c52  cmp     rcx, rax
0x180059c55  ja      loc_18005A251
0x180059c5b  mov     ecx, [rbx+8]
0x180059c5e  add     ecx, 0Ah
0x180059c61  mov     [rsp+150h+var_E0], rcx
0x180059c66  mov     rax, [rsp+150h+var_F0]
0x180059c6b  sub     rax, qword ptr [rsp+150h+var_100]
0x180059c70  sar     rax, 2
0x180059c74  cmp     rcx, rax
0x180059c77  ja      loc_18005A265
0x180059c7d  mov     edx, 3
0x180059c82  lea     rcx, unk_1801DA490
0x180059c89  call    D3D11CoreRegisterLayers
0x180059c8e  mov     ecx, eax; int
0x180059c90  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180059c95  mov     r9d, [rbx+8]
0x180059c99  mov     r8, [rbx]
0x180059c9c  mov     rdx, qword ptr [rsp+150h+var_100+8]
0x180059ca1  lea     rcx, [rsp+150h+var_100]
0x180059ca6  call    ??$_Insert_counted_range@PEBI@?$vector@IV?$allocator@I@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@1@PEBI_K@Z; std::vector<uint>::_Insert_counted_range<uint const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uint>>>,uint const *,unsigned __int64)
0x180059cab  or      eax, 0FFFFFFFFh
0x180059cae  mov     dword ptr [rsp+150h+var_E8], eax
0x180059cb2  mov     rdx, qword ptr [rsp+150h+var_100+8]
0x180059cb7  cmp     rdx, [rsp+150h+var_F0]
0x180059cbc  jz      loc_18005A431
0x180059cc2  mov     [rdx], eax
0x180059cc4  add     qword ptr [rsp+150h+var_100+8], 4
0x180059cca  xor     r15d, r15d
0x180059ccd  mov     ebx, r15d
0x180059cd0  mov     [rsp+150h+var_E0], rbx
0x180059cd5  mov     [rbp+50h+var_B8], rbx
0x180059cd9  mov     r12d, [rbp+50h+arg_28]
0x180059ce0  mov     edi, r12d
0x180059ce3  and     edi, 37FFE656h
0x180059ce9  call    IsXboxIsAsyncComputeOnlyDevicePresent
0x180059cee  test    al, al
0x180059cf0  jnz     loc_18005A445
0x180059cf6  mov     [rsp+150h+var_D8], r15
0x180059cfb  test    r12b, r12b
0x180059cfe  js      loc_18005A482
0x180059d04  test    edi, edi
0x180059d06  jnz     loc_18005A21C
0x180059d0c  lea     r9, Context; Context
0x180059d13  xor     r8d, r8d; Parameter
0x180059d16  lea     rdx, ?InitOnceGetProcAddress@CModule@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180059d1d  lea     rcx, InitOnce; InitOnce
0x180059d24  call    cs:__imp_InitOnceExecuteOnce
0x180059d2a  test    eax, eax
0x180059d2c  jz      short loc_180059D56
0x180059d2e  mov     rax, cs:Context
0x180059d35  mov     rax, [rax]
0x180059d38  test    rax, rax
0x180059d3b  jz      short loc_180059D56
0x180059d3d  lea     rdx, [rsp+150h+var_D8]
0x180059d42  lea     rcx, aRequiresdklaye; "RequireSDKLayers"
0x180059d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d4e  test    eax, eax
0x180059d50  jnz     loc_18005A472
0x180059d56  lea     r9, Context; Context
0x180059d5d  xor     r8d, r8d; Parameter
0x180059d60  lea     rdx, ?InitOnceGetProcAddress@CModule@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180059d67  lea     rcx, InitOnce; InitOnce
0x180059d6e  call    cs:__imp_InitOnceExecuteOnce
0x180059d74  test    eax, eax
0x180059d76  jz      short loc_180059DA7
0x180059d78  mov     rax, cs:Context
0x180059d7f  mov     rax, [rax]
0x180059d82  test    rax, rax
0x180059d85  jz      short loc_180059DA7
0x180059d87  lea     rdx, [rsp+150h+var_D8]
0x180059d8c  lea     rcx, aEnabledriverve; "EnableDriverVerifier"
0x180059d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d98  test    eax, eax
0x180059d9a  jz      short loc_180059DA7
0x180059d9c  cmp     [rsp+150h+var_D8], r15
0x180059da1  jnz     loc_18005A21C
0x180059da7  mov     rdx, qword ptr [rsp+150h+var_100+8]
0x180059dac  mov     rcx, qword ptr [rsp+150h+var_100]
0x180059db1  mov     r9b, r15b
0x180059db4  mov     r8, rdx
0x180059db7  sub     r8, rcx
0x180059dba  sar     r8, 2
0x180059dbe  call    ??$_Sort_unchecked@PEAIU?$less@X@std@@@std@@YAXPEAI0_JU?$less@X@0@@Z; std::_Sort_unchecked<uint *,std::less<void>>(uint *,uint *,__int64,std::less<void>)
0x180059dc3  mov     rdi, qword ptr [rsp+150h+var_100+8]
0x180059dc8  mov     r8, rdi
0x180059dcb  mov     rdx, qword ptr [rsp+150h+var_100]
0x180059dd0  lea     rcx, [rbp+50h+var_D0]
0x180059dd4  call    ??$unique@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@std@@U?$equal_to@X@2@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@0@V10@0U?$equal_to@X@0@@Z; std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,std::equal_to<void>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,std::equal_to<void>)
0x180059dd9  mov     r8, [rbp+50h+var_D0]
0x180059ddd  mov     rdx, qword ptr [rsp+150h+var_100+8]
0x180059de2  cmp     r8, rdi
0x180059de5  jnz     loc_18005A4E0
0x180059deb  mov     r14, r15
0x180059dee  mov     [rbp+50h+var_D0], r15
0x180059df2  mov     rcx, rdx
0x180059df5  mov     rax, qword ptr [rsp+150h+var_100]
0x180059dfa  sub     rcx, rax
0x180059dfd  sar     rcx, 2
0x180059e01  test    rcx, rcx
0x180059e04  jz      loc_18005A043
0x180059e0a  mov     bl, r14b
0x180059e0d  mov     r12, rcx
0x180059e10  mov     r13, r14
0x180059e13  cmp     r14, rcx
0x180059e16  jnb     loc_180059F81
0x180059e1c  mov     r15d, [rax+r13*4]
0x180059e20  mov     rsi, qword ptr cs:?g_D3D11RegisteredLayers@@3V?$vector@UTD3D11LayerRegistration@@V?$allocator@UTD3D11LayerRegistration@@@std@@@std@@A; std::vector<TD3D11LayerRegistration> g_D3D11RegisteredLayers
0x180059e27  mov     r9, qword ptr cs:?g_D3D11RegisteredLayers@@3V?$vector@UTD3D11LayerRegistration@@V?$allocator@UTD3D11LayerRegistration@@@std@@@std@@A+8; std::vector<TD3D11LayerRegistration> g_D3D11RegisteredLayers
0x180059e2e  mov     rcx, r9
0x180059e31  sub     rcx, rsi
0x180059e34  sar     rcx, 5
0x180059e38  jmp     short loc_180059E4B
0x180059e3a  add     rsi, 20h ; ' '
0x180059e3e  add     rsi, r8
0x180059e41  or      rax, 0FFFFFFFFFFFFFFFFh
0x180059e45  sub     rax, rdx
0x180059e48  add     rcx, rax
0x180059e4b  test    rcx, rcx
0x180059e4e  jle     short loc_180059E68
0x180059e50  mov     rdx, rcx
0x180059e53  shr     rdx, 1
0x180059e56  mov     r8, rdx
0x180059e59  shl     r8, 5
0x180059e5d  cmp     [r8+rsi], r15d
0x180059e61  jb      short loc_180059E3A
0x180059e63  mov     rcx, rdx
0x180059e66  jmp     short loc_180059E4B
0x180059e68  cmp     rsi, r9
0x180059e6b  jz      loc_18005A4F5
0x180059e71  cmp     [rsi], r15d
0x180059e74  jnz     loc_18005A4F5
0x180059e7a  mov     rdx, [rsp+150h+var_120]
0x180059e7f  mov     rax, [rsp+150h+var_110]
0x180059e84  sub     rax, rdx
0x180059e87  sar     rax, 2
0x180059e8b  mov     rdi, [rsp+150h+var_118]
0x180059e90  mov     r8, rdi
0x180059e93  mov     rcx, rdi
0x180059e96  sub     rcx, rdx
0x180059e99  sar     rcx, 2
0x180059e9d  cmp     rax, rcx
0x180059ea0  jb      loc_18005A0CB
0x180059ea6  jbe     short loc_180059EBF
0x180059ea8  sub     rax, rcx
0x180059eab  mov     rcx, rdi
0x180059eae  lea     rdi, [rdi+rax*4]
0x180059eb2  mov     rdx, rdi
0x180059eb5  call    ??$_Zero_range@PEA_K@std@@YAPEA_KQEA_K0@Z; std::_Zero_range<unsigned __int64 *>(unsigned __int64 * const,unsigned __int64 * const)
0x180059eba  mov     [rsp+150h+var_118], rdi
0x180059ebf  mov     r8, [rsp+150h+var_120]
0x180059ec4  sub     rdi, r8
0x180059ec7  sar     rdi, 2
0x180059ecb  mov     [rsp+150h+var_E8], rdi
0x180059ed0  lea     rdx, [rsp+150h+var_E8]
0x180059ed5  mov     ecx, r15d
0x180059ed8  mov     rax, [rsi+8]
0x180059edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059ee1  mov     r14d, eax
0x180059ee4  mov     r8, [rsp+150h+var_120]
0x180059ee9  cmp     eax, 8007007Ah
0x180059eee  jz      loc_18005A3E7
0x180059ef4  mov     rcx, [rsp+150h+var_E8]
0x180059ef9  mov     r9, [rsp+150h+var_118]
0x180059efe  mov     rdx, r9
0x180059f01  sub     rdx, r8
0x180059f04  sar     rdx, 2
0x180059f08  cmp     rcx, rdx
0x180059f0b  jb      loc_18005A0D4
0x180059f11  jbe     short loc_180059F3F
0x180059f13  mov     rax, [rsp+150h+var_110]
0x180059f18  sub     rax, r8
0x180059f1b  sar     rax, 2
0x180059f1f  cmp     rcx, rax
0x180059f22  ja      loc_18005A51B
0x180059f28  sub     rcx, rdx
0x180059f2b  lea     rdi, [r9+rcx*4]
0x180059f2f  mov     rdx, rdi
0x180059f32  mov     rcx, r9
0x180059f35  call    ??$_Zero_range@PEA_K@std@@YAPEA_KQEA_K0@Z; std::_Zero_range<unsigned __int64 *>(unsigned __int64 * const,unsigned __int64 * const)
0x180059f3a  mov     [rsp+150h+var_118], rdi
0x180059f3f  mov     ecx, r14d; int
0x180059f42  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x180059f47  mov     r8, [rsp+150h+var_120]
0x180059f4c  mov     r9, [rsp+150h+var_118]
0x180059f51  sub     r9, r8
0x180059f54  sar     r9, 2
0x180059f58  mov     rdx, qword ptr [rsp+150h+var_100+8]
0x180059f5d  lea     rcx, [rsp+150h+var_100]
0x180059f62  call    ??$_Insert_counted_range@PEBI@?$vector@IV?$allocator@I@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@1@PEBI_K@Z; std::vector<uint>::_Insert_counted_range<uint const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uint>>>,uint const *,unsigned __int64)
0x180059f67  inc     r13
0x180059f6a  mov     rax, qword ptr [rsp+150h+var_100]
0x180059f6f  cmp     r13, r12
0x180059f72  jb      loc_180059E1C
0x180059f78  mov     rdx, qword ptr [rsp+150h+var_100+8]
0x180059f7d  mov     r14, [rbp+50h+var_D0]
0x180059f81  lea     rsi, ds:0[r12*4]
0x180059f89  mov     r8, rdx
0x180059f8c  sub     r8, rax
0x180059f8f  sub     r8, rsi
0x180059f92  sar     r8, 2
0x180059f96  lea     rcx, [rax+rsi]
0x180059f9a  mov     r9b, bl
0x180059f9d  call    ??$_Sort_unchecked@PEAIU?$less@X@std@@@std@@YAXPEAI0_JU?$less@X@0@@Z; std::_Sort_unchecked<uint *,std::less<void>>(uint *,uint *,__int64,std::less<void>)
0x180059fa2  mov     rdi, qword ptr [rsp+150h+var_100+8]
0x180059fa7  mov     rdx, qword ptr [rsp+150h+var_100]
0x180059fac  add     rdx, rsi
0x180059faf  mov     r8, rdi
0x180059fb2  lea     rcx, [rbp+50h+var_C0]
0x180059fb6  call    ??$unique@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@std@@U?$equal_to@X@2@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@0@V10@0U?$equal_to@X@0@@Z; std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,std::equal_to<void>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,std::equal_to<void>)
0x180059fbb  mov     r8, [rbp+50h+var_C0]
0x180059fbf  cmp     r8, rdi
0x180059fc2  jnz     loc_18005A52D
0x180059fc8  mov     rcx, qword ptr [rsp+150h+var_100]
0x180059fcd  lea     r8, [rcx+rsi]
0x180059fd1  lea     rdx, [rcx+r14*4]
0x180059fd5  call    ??$inplace_merge@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@std@@@std@@YAXV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@0@00@Z; std::inplace_merge<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>)
0x180059fda  mov     rdi, qword ptr [rsp+150h+var_100+8]
0x180059fdf  mov     rdx, qword ptr [rsp+150h+var_100]
0x180059fe4  mov     qword ptr [rbp+50h+pszDest], rdx
0x180059fe8  lea     rax, [rdx+rsi]
0x180059fec  mov     [rbp+50h+var_58], rax
0x180059ff0  add     rdx, rsi
0x180059ff3  lea     r9, [rbp+50h+pszDest]
0x180059ff7  mov     r8, rdi
0x180059ffa  lea     rcx, [rbp+50h+var_70]
0x180059ffe  call    ??$remove_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@std@@U?$in_sorted_range@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@std@@@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@0@V10@V10@U?$in_sorted_range@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@std@@@@@Z; std::remove_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,in_sorted_range<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>>>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>,in_sorted_range<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<uint>>>>)
0x18005a003  mov     rdx, qword ptr [rsp+150h+var_100+8]
0x18005a008  cmp     [rax], rdi
0x18005a00b  jnz     loc_18005A544
0x18005a011  mov     r14, r12
0x18005a014  mov     [rbp+50h+var_D0], r12
0x18005a018  mov     rcx, rdx
0x18005a01b  mov     rax, qword ptr [rsp+150h+var_100]
0x18005a020  sub     rcx, rax
0x18005a023  sar     rcx, 2
0x18005a027  cmp     r12, rcx
0x18005a02a  jnz     loc_180059E0D
0x18005a030  mov     rbx, [rsp+150h+var_E0]
0x18005a035  mov     r12d, [rbp+50h+arg_28]
0x18005a03c  mov     r13, [rbp+50h+var_B0]
0x18005a040  xor     r15d, r15d
0x18005a043  mov     rcx, rdx
0x18005a046  sub     rcx, rax
0x18005a049  sar     rcx, 2
0x18005a04d  mov     r9, [rsp+150h+var_120]
0x18005a052  mov     r10, [rsp+150h+var_118]
0x18005a057  mov     r8, r10
0x18005a05a  sub     r8, r9
0x18005a05d  sar     r8, 2
0x18005a061  cmp     rcx, r8
0x18005a064  jb      loc_18005A20E
0x18005a06a  jbe     short loc_18005A0A2
0x18005a06c  mov     rax, [rsp+150h+var_110]
0x18005a071  sub     rax, r9
0x18005a074  sar     rax, 2
0x18005a078  cmp     rcx, rax
0x18005a07b  ja      loc_18005A55C
0x18005a081  sub     rcx, r8
0x18005a084  lea     rdi, [r10+rcx*4]
0x18005a088  mov     rdx, rdi
0x18005a08b  mov     rcx, r10
0x18005a08e  call    ??$_Zero_range@PEA_K@std@@YAPEA_KQEA_K0@Z; std::_Zero_range<unsigned __int64 *>(unsigned __int64 * const,unsigned __int64 * const)
0x18005a093  mov     [rsp+150h+var_118], rdi
0x18005a098  mov     rax, qword ptr [rsp+150h+var_100]
0x18005a09d  mov     rdx, qword ptr [rsp+150h+var_100+8]
0x18005a0a2  mov     r10, qword ptr cs:?g_D3D11RegisteredLayers@@3V?$vector@UTD3D11LayerRegistration@@V?$allocator@UTD3D11LayerRegistration@@@std@@@std@@A; std::vector<TD3D11LayerRegistration> g_D3D11RegisteredLayers
  ... truncated ...
```
