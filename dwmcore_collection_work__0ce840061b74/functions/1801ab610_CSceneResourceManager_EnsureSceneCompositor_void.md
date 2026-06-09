# CSceneResourceManager::EnsureSceneCompositor(void)

- ea: `0x1801ab610`
- end: `0x1801aba05`
- name: `?EnsureSceneCompositor@CSceneResourceManager@@AEAAJXZ`
- size: `1013`
- prototype: `__int64 __fastcall(CSceneResourceManager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010e528`

## callees

- `0x18000a254`
- `0x18000b318`
- `0x18000c6d8`
- `0x1800319cc`
- `0x180042de0`
- `0x180097f40`
- `0x1800c61b0`
- `0x1800c868c`
- `0x1801ab610`
- `0x1801d3af4`
- `0x1801e8f14`
- `0x180228490`
- `0x18022943c`
- `0x1802347c0`
- `0x180234af8`
- `0x18027b5bc`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801ab693`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801ab693`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801ab660`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801ab660`

## string_xrefs

- `0x1801ab659`: `DwmScene.dll`
- `0x1801ab68c`: `CreateDwmSceneRenderer`

## pseudocode

```c
__int64 __fastcall CSceneResourceManager::EnsureSceneCompositor(CSceneResourceManager *this)
{
  unsigned int v2; // ebx
  HMODULE *v3; // r14
  HMODULE LibraryW; // rax
  CDisplayManager *v5; // rcx
  FARPROC ProcAddress; // r12
  struct IDXGIFactory5 *v7; // r15
  unsigned int v8; // esi
  struct IDXGIFactory5Vtbl *lpVtbl; // rax
  int v10; // ebx
  CDisplayManager *v11; // rcx
  struct _LUID PrimaryAdapterLuid; // rcx
  int Device; // eax
  struct CD3DDevice **v14; // rsi
  CDeviceManager *v15; // rcx
  int DefaultDevice; // eax
  struct CD3DDevice *v17; // rax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // rcx
  _QWORD *v23; // rdx
  _QWORD *v24; // rsi
  _QWORD *i; // rdi
  __int64 v26; // rcx
  struct IUnknown *v28; // [rsp+30h] [rbp-D0h] BYREF
  CSceneResourceManager *v29; // [rsp+38h] [rbp-C8h] BYREF
  struct IDXGIFactory5 *v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v32; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  CSceneResourceManager **v35; // [rsp+68h] [rbp-98h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  char v37; // [rsp+78h] [rbp-88h]
  _BYTE v38[296]; // [rsp+90h] [rbp-70h] BYREF
  struct _LUID v39; // [rsp+1B8h] [rbp+B8h]

  v2 = 0;
  if ( *((_BYTE *)this + 80) )
    return v2;
  v3 = (HMODULE *)((char *)this + 16);
  if ( !*((_QWORD *)this + 2) )
  {
    LibraryW = LoadLibraryW(L"DwmScene.dll");
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v3,
      LibraryW);
  }
  if ( !*v3 )
  {
    *((_BYTE *)this + 80) = 1;
    return v2;
  }
  if ( *((_QWORD *)this + 3) )
    return v2;
  ProcAddress = GetProcAddress(*v3, "CreateDwmSceneRenderer");
  if ( ProcAddress )
  {
    if ( CCommonRegistryData::m_fSceneForceNonPrimaryDisplayAdapter )
    {
      v30 = 0;
      if ( (int)CDisplayManager::GetDXGIFactory(v5, &v30) >= 0 )
      {
        v7 = v30;
        v8 = 0;
        v29 = 0;
        while ( 1 )
        {
          lpVtbl = v7->lpVtbl;
          v35 = &v29;
          v36 = 0;
          v37 = 1;
          v10 = ((__int64 (__fastcall *)(struct IDXGIFactory5 *, _QWORD, __int64 *))lpVtbl->EnumAdapters1)(v7, v8, &v36);
          wil::details::out_param_t<wil::com_ptr_t<IDXGIOutput,wil::err_returncode_policy>>::~out_param_t<wil::com_ptr_t<IDXGIOutput,wil::err_returncode_policy>>(&v35);
          if ( v10 < 0 )
            break;
          memset_0(v38, 0, 0x138u);
          if ( (*(int (__fastcall **)(CSceneResourceManager *, _BYTE *))(*(_QWORD *)v29 + 80LL))(v29, v38) >= 0 )
          {
            PrimaryAdapterLuid = CDisplayManager::GetPrimaryAdapterLuid(v11);
            if ( v39.LowPart != *(_DWORD *)PrimaryAdapterLuid.LowPart
              || v39.HighPart != *(_DWORD *)(*(_QWORD *)&PrimaryAdapterLuid + 4LL) )
            {
              wil::com_ptr_t<CD3DDevice,wil::err_returncode_policy>::reset((char *)this + 32);
              Device = CDeviceManager::GetDevice(
                         (CDeviceManager *)&g_DeviceManager,
                         v39,
                         (struct CD3DDevice **)this + 4);
              v2 = Device;
              if ( Device < 0 )
              {
                MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, Device, 0x6Du, 0);
                wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v29);
                goto LABEL_22;
              }
              break;
            }
          }
          ++v8;
        }
        wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v29);
      }
      v14 = (struct CD3DDevice **)((char *)this + 32);
      if ( !*((_QWORD *)this + 4) )
      {
        v2 = -2147467259;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147467259, 0x77u, 0);
LABEL_22:
        wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v30);
        goto LABEL_40;
      }
      wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v30);
    }
    else
    {
      v14 = (struct CD3DDevice **)((char *)this + 32);
      wil::com_ptr_t<CD3DDevice,wil::err_returncode_policy>::reset((char *)this + 32);
      DefaultDevice = CDeviceManager::GetDefaultDevice(v15, (struct CD3DDevice **)this + 4);
      v2 = DefaultDevice;
      if ( DefaultDevice < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, DefaultDevice, 0x7Cu, 0);
        goto LABEL_40;
      }
    }
    v17 = *v14;
    v34 = 0;
    v32 = 0;
    v33 = 0;
    v31 = 0;
    v18 = *((_QWORD *)v17 + 68);
    v32 = __PAIR64__(
            CCommonRegistryData::Scene::ImageProcessingMinHeight,
            CCommonRegistryData::Scene::ImageProcessingMinWidth);
    v33 = __PAIR64__(
            LODWORD(CCommonRegistryData::m_flSceneImageProcessingResizeThreshold),
            CCommonRegistryData::Scene::ImageProcessingResizeGrowth);
    LODWORD(v34) = CCommonRegistryData::Scene::MsaaQualityMode;
    BYTE4(v34) = CCommonRegistryData::Scene::EnableBloom;
    BYTE5(v34) = CCommonRegistryData::Scene::EnableImageProcessing;
    BYTE6(v34) = CCommonRegistryData::Scene::ImageProcessing8bit;
    HIBYTE(v34) = CCommonRegistryData::Scene::EnableShadow;
    v31 = v18;
    v28 = 0;
    v19 = ((__int64 (__fastcall *)(__int64 *, GUID *, struct IUnknown **))ProcAddress)(
            &v31,
            &GUID_c459639d_0878_4eb7_ade9_3655c96fa73a,
            &v28);
    v2 = v19;
    if ( v19 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v19, 0x8Cu, 0);
    }
    else
    {
      v20 = *((_QWORD *)this + 3);
      *((_QWORD *)this + 3) = 0;
      if ( v20 )
        CMILRefCountBaseT<IDeviceResource,CMilObjectDeleter>::InternalRelease();
      v21 = CExternalD3DRenderer::Create(*v14, v28, (struct CExternalD3DRenderer **)this + 3);
      v2 = v21;
      if ( v21 >= 0 )
      {
        v22 = *((_QWORD *)this + 3) + 48LL;
        v29 = this;
        v23 = *(_QWORD **)(v22 + 8);
        if ( v23 == *(_QWORD **)(v22 + 16) )
        {
          std::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>::_Emplace_reallocate<Microsoft::BamoImpl::BamoPrincipalImpl * const &>(
            v22,
            v23,
            &v29);
        }
        else
        {
          *v23 = this;
          *(_QWORD *)(v22 + 8) += 8LL;
        }
        v24 = (_QWORD *)*((_QWORD *)this + 6);
        for ( i = (_QWORD *)*((_QWORD *)this + 5); i != v24; ++i )
          (**(void (__fastcall ***)(_QWORD, struct IUnknown *))*i)(*i, v28);
        wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v28);
        return v2;
      }
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v21, 0x8Eu, 0);
    }
    wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(&v28);
  }
  else
  {
    v2 = -2147418113;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147418113, 0x5Bu, 0);
  }
LABEL_40:
  *((_BYTE *)this + 80) = 1;
  v26 = *((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v26 )
    CMILRefCountBaseT<IDeviceResource,CMilObjectDeleter>::InternalRelease();
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(v3);
  return v2;
}

```

## disassembly

```asm
0x1801ab610  push    rbp
0x1801ab612  push    rbx
0x1801ab613  push    rsi
0x1801ab614  push    rdi
0x1801ab615  push    r12
0x1801ab617  push    r13
0x1801ab619  push    r14
0x1801ab61b  push    r15
0x1801ab61d  lea     rbp, [rsp-0E8h]
0x1801ab625  sub     rsp, 1E8h
0x1801ab62c  mov     rax, cs:__security_cookie
0x1801ab633  xor     rax, rsp
0x1801ab636  mov     [rbp+120h+var_50], rax
0x1801ab63d  xor     r13d, r13d
0x1801ab640  mov     rdi, rcx
0x1801ab643  mov     ebx, r13d
0x1801ab646  cmp     [rcx+50h], r13b
0x1801ab64a  jnz     loc_1801AB9E0
0x1801ab650  lea     r14, [rcx+10h]
0x1801ab654  cmp     [r14], r13
0x1801ab657  jnz     short loc_1801AB671
0x1801ab659  lea     rcx, LibFileName; "DwmScene.dll"
0x1801ab660  call    cs:__imp_LoadLibraryW
0x1801ab666  mov     rdx, rax
0x1801ab669  mov     rcx, r14
0x1801ab66c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1801ab671  mov     rcx, [r14]; hModule
0x1801ab674  test    rcx, rcx
0x1801ab677  jnz     short loc_1801AB682
0x1801ab679  mov     byte ptr [rdi+50h], 1
0x1801ab67d  jmp     loc_1801AB9E0
0x1801ab682  cmp     [rdi+18h], r13
0x1801ab686  jnz     loc_1801AB9E0
0x1801ab68c  lea     rdx, aCreatedwmscene; "CreateDwmSceneRenderer"
0x1801ab693  call    cs:__imp_GetProcAddress
0x1801ab699  mov     r12, rax
0x1801ab69c  test    rax, rax
0x1801ab69f  jnz     short loc_1801AB6BB
0x1801ab6a1  mov     ebx, 8000FFFFh
0x1801ab6a6  mov     [rsp+220h+var_1F8], r13
0x1801ab6ab  mov     r9d, ebx
0x1801ab6ae  mov     [rsp+220h+var_200], 5Bh ; '['
0x1801ab6b6  jmp     loc_1801AB9B5
0x1801ab6bb  cmp     cs:?m_fSceneForceNonPrimaryDisplayAdapter@CCommonRegistryData@@0HA, r13d; int CCommonRegistryData::m_fSceneForceNonPrimaryDisplayAdapter
0x1801ab6c2  jz      loc_1801AB81F
0x1801ab6c8  lea     rdx, [rsp+220h+var_1E0]; struct IDXGIFactory5 **
0x1801ab6cd  mov     [rsp+220h+var_1E0], r13
0x1801ab6d2  call    ?GetDXGIFactory@CDisplayManager@@QEAAJPEAPEAUIDXGIFactory5@@@Z; CDisplayManager::GetDXGIFactory(IDXGIFactory5 * *)
0x1801ab6d7  test    eax, eax
0x1801ab6d9  js      loc_1801AB7D9
0x1801ab6df  mov     r15, [rsp+220h+var_1E0]
0x1801ab6e4  mov     esi, r13d
0x1801ab6e7  mov     [rsp+220h+var_1E8], r13
0x1801ab6ec  mov     rax, [r15]
0x1801ab6ef  lea     rcx, [rsp+220h+var_1E8]
0x1801ab6f4  mov     [rsp+220h+var_1B8], rcx
0x1801ab6f9  lea     r8, [rsp+220h+var_1B0]
0x1801ab6fe  mov     edx, esi
0x1801ab700  mov     [rsp+220h+var_1B0], r13
0x1801ab705  mov     rcx, r15
0x1801ab708  mov     [rsp+220h+var_1A8], 1
0x1801ab70d  mov     rax, [rax+60h]
0x1801ab711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab716  lea     rcx, [rsp+220h+var_1B8]
0x1801ab71b  mov     ebx, eax
0x1801ab71d  call    ??1?$out_param_t@V?$com_ptr_t@UIDXGIOutput@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<IDXGIOutput,wil::err_returncode_policy>>::~out_param_t<wil::com_ptr_t<IDXGIOutput,wil::err_returncode_policy>>(void)
0x1801ab722  shr     ebx, 1Fh
0x1801ab725  xor     bl, 1
0x1801ab728  jz      loc_1801AB7CF
0x1801ab72e  xor     edx, edx; Val
0x1801ab730  lea     rcx, [rbp+120h+var_190]; void *
0x1801ab734  mov     r8d, 138h; Size
0x1801ab73a  call    memset_0
0x1801ab73f  mov     rcx, [rsp+220h+var_1E8]
0x1801ab744  lea     rdx, [rbp+120h+var_190]
0x1801ab748  mov     rax, [rcx]
0x1801ab74b  mov     rax, [rax+50h]
0x1801ab74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab754  test    eax, eax
0x1801ab756  js      short loc_1801AB779
0x1801ab758  lea     rdx, [rbp+120h+var_1A0]
0x1801ab75c  call    ?GetPrimaryAdapterLuid@CDisplayManager@@QEAA?AU_LUID@@XZ; CDisplayManager::GetPrimaryAdapterLuid(void)
0x1801ab761  mov     rcx, rax
0x1801ab764  mov     eax, [rax]
0x1801ab766  cmp     [rbp+120h+var_68.LowPart], eax
0x1801ab76c  jnz     short loc_1801AB780
0x1801ab76e  mov     eax, [rcx+4]
0x1801ab771  cmp     [rbp+120h+var_68.HighPart], eax
0x1801ab777  jnz     short loc_1801AB780
0x1801ab779  inc     esi
0x1801ab77b  jmp     loc_1801AB6EC
0x1801ab780  lea     rcx, [rdi+20h]
0x1801ab784  call    ?reset@?$com_ptr_t@VCD3DDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CD3DDevice,wil::err_returncode_policy>::reset(void)
0x1801ab789  mov     rdx, qword ptr [rbp+120h+var_68.LowPart]; struct _LUID
0x1801ab790  lea     r8, [rdi+20h]; struct CD3DDevice **
0x1801ab794  lea     rcx, ?g_DeviceManager@@3VCDeviceManager@@A; this
0x1801ab79b  call    ?GetDevice@CDeviceManager@@QEAAJU_LUID@@PEAPEAVCD3DDevice@@@Z; CDeviceManager::GetDevice(_LUID,CD3DDevice * *)
0x1801ab7a0  mov     ebx, eax
0x1801ab7a2  test    eax, eax
0x1801ab7a4  jns     short loc_1801AB7CF
0x1801ab7a6  xor     edx, edx; int *
0x1801ab7a8  mov     [rsp+220h+var_1F8], r13; void *
0x1801ab7ad  mov     r9d, eax; int
0x1801ab7b0  mov     [rsp+220h+var_200], 6Dh ; 'm'; unsigned int
0x1801ab7b8  xor     r8d, r8d; unsigned int
0x1801ab7bb  lea     ecx, [rdx+14h]; unsigned int
0x1801ab7be  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801ab7c3  lea     rcx, [rsp+220h+var_1E8]
0x1801ab7c8  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801ab7cd  jmp     short loc_1801AB804
0x1801ab7cf  lea     rcx, [rsp+220h+var_1E8]
0x1801ab7d4  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801ab7d9  lea     rsi, [rdi+20h]
0x1801ab7dd  cmp     [rsi], r13
0x1801ab7e0  jnz     short loc_1801AB813
0x1801ab7e2  xor     edx, edx; int *
0x1801ab7e4  mov     [rsp+220h+var_1F8], r13; void *
0x1801ab7e9  mov     ebx, 80004005h
0x1801ab7ee  mov     [rsp+220h+var_200], 77h ; 'w'; unsigned int
0x1801ab7f6  mov     r9d, ebx; int
0x1801ab7f9  xor     r8d, r8d; unsigned int
0x1801ab7fc  lea     ecx, [rdx+14h]; unsigned int
0x1801ab7ff  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801ab804  lea     rcx, [rsp+220h+var_1E0]
0x1801ab809  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801ab80e  jmp     loc_1801AB9C2
0x1801ab813  lea     rcx, [rsp+220h+var_1E0]
0x1801ab818  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801ab81d  jmp     short loc_1801AB83D
0x1801ab81f  lea     rsi, [rdi+20h]
0x1801ab823  mov     rcx, rsi
0x1801ab826  call    ?reset@?$com_ptr_t@VCD3DDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CD3DDevice,wil::err_returncode_policy>::reset(void)
0x1801ab82b  mov     rdx, rsi; struct CD3DDevice **
0x1801ab82e  call    ?GetDefaultDevice@CDeviceManager@@QEAAJPEAPEAVCD3DDevice@@@Z; CDeviceManager::GetDefaultDevice(CD3DDevice * *)
0x1801ab833  mov     ebx, eax
0x1801ab835  test    eax, eax
0x1801ab837  js      loc_1801AB9A5
0x1801ab83d  mov     rax, [rsi]
0x1801ab840  lea     r8, [rsp+220h+var_1F0]
0x1801ab845  movss   xmm0, cs:?m_flSceneImageProcessingResizeThreshold@CCommonRegistryData@@0MA; float CCommonRegistryData::m_flSceneImageProcessingResizeThreshold
0x1801ab84d  lea     rdx, _GUID_c459639d_0878_4eb7_ade9_3655c96fa73a
0x1801ab854  mov     [rsp+220h+var_1C0], r13
0x1801ab859  mov     [rsp+220h+var_1D0], r13
0x1801ab85e  mov     [rsp+220h+var_1C8], r13
0x1801ab863  mov     [rsp+220h+var_1D8], r13
0x1801ab868  mov     rcx, [rax+220h]
0x1801ab86f  mov     eax, cs:?ImageProcessingMinWidth@Scene@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::Scene::ImageProcessingMinWidth
0x1801ab875  mov     dword ptr [rsp+220h+var_1D0], eax
0x1801ab879  mov     eax, cs:?ImageProcessingMinHeight@Scene@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::Scene::ImageProcessingMinHeight
0x1801ab87f  mov     dword ptr [rsp+220h+var_1D0+4], eax
0x1801ab883  mov     eax, cs:?ImageProcessingResizeGrowth@Scene@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::Scene::ImageProcessingResizeGrowth
0x1801ab889  mov     dword ptr [rsp+220h+var_1C8], eax
0x1801ab88d  mov     eax, cs:?MsaaQualityMode@Scene@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::Scene::MsaaQualityMode
0x1801ab893  mov     dword ptr [rsp+220h+var_1C0], eax
0x1801ab897  mov     al, cs:?EnableBloom@Scene@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B; details::CRegistryKey<bool,bool> const CCommonRegistryData::Scene::EnableBloom
0x1801ab89d  mov     byte ptr [rsp+220h+var_1C0+4], al
0x1801ab8a1  mov     al, cs:?EnableImageProcessing@Scene@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B; details::CRegistryKey<bool,bool> const CCommonRegistryData::Scene::EnableImageProcessing
0x1801ab8a7  mov     byte ptr [rsp+220h+var_1C0+5], al
0x1801ab8ab  mov     al, cs:?ImageProcessing8bit@Scene@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B; details::CRegistryKey<bool,bool> const CCommonRegistryData::Scene::ImageProcessing8bit
0x1801ab8b1  mov     byte ptr [rsp+220h+var_1C0+6], al
0x1801ab8b5  mov     al, cs:?EnableShadow@Scene@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B; details::CRegistryKey<bool,bool> const CCommonRegistryData::Scene::EnableShadow
0x1801ab8bb  mov     byte ptr [rsp+220h+var_1C0+7], al
0x1801ab8bf  mov     rax, r12
0x1801ab8c2  mov     [rsp+220h+var_1D8], rcx
0x1801ab8c7  lea     rcx, [rsp+220h+var_1D8]
0x1801ab8cc  movss   dword ptr [rsp+220h+var_1C8+4], xmm0
0x1801ab8d2  mov     [rsp+220h+var_1F0], r13
0x1801ab8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab8dc  mov     ebx, eax
0x1801ab8de  test    eax, eax
0x1801ab8e0  js      loc_1801AB97C
0x1801ab8e6  lea     rbx, [rdi+18h]
0x1801ab8ea  mov     rcx, [rbx]
0x1801ab8ed  mov     [rbx], r13
0x1801ab8f0  test    rcx, rcx
0x1801ab8f3  jz      short loc_1801AB8FA
0x1801ab8f5  call    ?InternalRelease@?$CMILRefCountBaseT@VIDeviceResource@@VCMilObjectDeleter@@@@IEAAKXZ; CMILRefCountBaseT<IDeviceResource,CMilObjectDeleter>::InternalRelease(void)
0x1801ab8fa  mov     rdx, [rsp+220h+var_1F0]; struct IUnknown *
0x1801ab8ff  mov     r8, rbx; struct CExternalD3DRenderer **
0x1801ab902  mov     rcx, [rsi]; struct CD3DDevice *
0x1801ab905  call    ?Create@CExternalD3DRenderer@@SAJPEAVCD3DDevice@@PEAUIUnknown@@PEAPEAV1@@Z; CExternalD3DRenderer::Create(CD3DDevice *,IUnknown *,CExternalD3DRenderer * *)
0x1801ab90a  mov     ebx, eax
0x1801ab90c  test    eax, eax
0x1801ab90e  js      short loc_1801AB96D
0x1801ab910  mov     rcx, [rdi+18h]
0x1801ab914  add     rcx, 30h ; '0'
0x1801ab918  mov     [rsp+220h+var_1E8], rdi
0x1801ab91d  mov     rdx, [rcx+8]
0x1801ab921  cmp     rdx, [rcx+10h]
0x1801ab925  jz      short loc_1801AB931
0x1801ab927  mov     [rdx], rdi
0x1801ab92a  add     qword ptr [rcx+8], 8
0x1801ab92f  jmp     short loc_1801AB93B
0x1801ab931  lea     r8, [rsp+220h+var_1E8]
0x1801ab936  call    ??$_Emplace_reallocate@AEBQEAVBamoPrincipalImpl@BamoImpl@Microsoft@@@?$vector@PEAVBamoPrincipalImpl@BamoImpl@Microsoft@@V?$allocator@PEAVBamoPrincipalImpl@BamoImpl@Microsoft@@@std@@@std@@AEAAPEAPEAVBamoPrincipalImpl@BamoImpl@Microsoft@@QEAPEAV234@AEBQEAV234@@Z; std::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>::_Emplace_reallocate<Microsoft::BamoImpl::BamoPrincipalImpl * const &>(Microsoft::BamoImpl::BamoPrincipalImpl * * const,Microsoft::BamoImpl::BamoPrincipalImpl * const &)
0x1801ab93b  mov     rsi, [rdi+30h]
0x1801ab93f  mov     rdi, [rdi+28h]
0x1801ab943  jmp     short loc_1801AB95C
0x1801ab945  mov     rcx, [rdi]
0x1801ab948  mov     rdx, [rsp+220h+var_1F0]
0x1801ab94d  mov     rax, [rcx]
0x1801ab950  mov     rax, [rax]
0x1801ab953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ab958  add     rdi, 8
0x1801ab95c  cmp     rdi, rsi
0x1801ab95f  jnz     short loc_1801AB945
0x1801ab961  lea     rcx, [rsp+220h+var_1F0]
0x1801ab966  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801ab96b  jmp     short loc_1801AB9E0
0x1801ab96d  mov     [rsp+220h+var_1F8], r13
0x1801ab972  mov     [rsp+220h+var_200], 8Eh
0x1801ab97a  jmp     short loc_1801AB989
0x1801ab97c  mov     [rsp+220h+var_1F8], r13; void *
0x1801ab981  mov     [rsp+220h+var_200], 8Ch; unsigned int
0x1801ab989  xor     edx, edx; int *
0x1801ab98b  mov     r9d, eax; int
0x1801ab98e  xor     r8d, r8d; unsigned int
0x1801ab991  lea     ecx, [rdx+14h]; unsigned int
0x1801ab994  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801ab999  lea     rcx, [rsp+220h+var_1F0]
0x1801ab99e  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801ab9a3  jmp     short loc_1801AB9C2
0x1801ab9a5  mov     [rsp+220h+var_1F8], r13; void *
0x1801ab9aa  mov     r9d, eax; int
0x1801ab9ad  mov     [rsp+220h+var_200], 7Ch ; '|'; unsigned int
0x1801ab9b5  xor     edx, edx; int *
0x1801ab9b7  xor     r8d, r8d; unsigned int
0x1801ab9ba  lea     ecx, [rdx+14h]; unsigned int
0x1801ab9bd  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801ab9c2  mov     byte ptr [rdi+50h], 1
0x1801ab9c6  mov     rcx, [rdi+18h]
0x1801ab9ca  mov     [rdi+18h], r13
0x1801ab9ce  test    rcx, rcx
0x1801ab9d1  jz      short loc_1801AB9D8
0x1801ab9d3  call    ?InternalRelease@?$CMILRefCountBaseT@VIDeviceResource@@VCMilObjectDeleter@@@@IEAAKXZ; CMILRefCountBaseT<IDeviceResource,CMilObjectDeleter>::InternalRelease(void)
0x1801ab9d8  mov     rcx, r14
0x1801ab9db  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(std::nullptr_t)
0x1801ab9e0  mov     eax, ebx
0x1801ab9e2  mov     rcx, [rbp+120h+var_50]
0x1801ab9e9  xor     rcx, rsp; StackCookie
0x1801ab9ec  call    __security_check_cookie
0x1801ab9f1  add     rsp, 1E8h
0x1801ab9f8  pop     r15
0x1801ab9fa  pop     r14
0x1801ab9fc  pop     r13
0x1801ab9fe  pop     r12
0x1801aba00  pop     rdi
0x1801aba01  pop     rsi
0x1801aba02  pop     rbx
0x1801aba03  pop     rbp
0x1801aba04  retn
```
