# CSceneResourceManager::EnsureSceneCompositor(void)

- ea: `0x1801acb70`
- end: `0x1801acf65`
- name: `?EnsureSceneCompositor@CSceneResourceManager@@AEAAJXZ`
- size: `1013`
- prototype: `__int64 __fastcall(CSceneResourceManager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012fe64`

## callees

- `0x18001eb08`
- `0x180026eac`
- `0x180050270`
- `0x180078a9c`
- `0x1800c07a0`
- `0x1800c3940`
- `0x1800c5e1c`
- `0x1801046bc`
- `0x18015a858`
- `0x1801acb70`
- `0x1801d54a4`
- `0x1802284b0`
- `0x18022945c`
- `0x1802347e0`
- `0x180234b18`
- `0x18027b5dc`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801acbf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801acbf3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801acbc0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801acbc0`

## string_xrefs

- `0x1801acbb9`: `DwmScene.dll`
- `0x1801acbec`: `CreateDwmSceneRenderer`

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
0x1801acb70  push    rbp
0x1801acb72  push    rbx
0x1801acb73  push    rsi
0x1801acb74  push    rdi
0x1801acb75  push    r12
0x1801acb77  push    r13
0x1801acb79  push    r14
0x1801acb7b  push    r15
0x1801acb7d  lea     rbp, [rsp-0E8h]
0x1801acb85  sub     rsp, 1E8h
0x1801acb8c  mov     rax, cs:__security_cookie
0x1801acb93  xor     rax, rsp
0x1801acb96  mov     [rbp+120h+var_50], rax
0x1801acb9d  xor     r13d, r13d
0x1801acba0  mov     rdi, rcx
0x1801acba3  mov     ebx, r13d
0x1801acba6  cmp     [rcx+50h], r13b
0x1801acbaa  jnz     loc_1801ACF40
0x1801acbb0  lea     r14, [rcx+10h]
0x1801acbb4  cmp     [r14], r13
0x1801acbb7  jnz     short loc_1801ACBD1
0x1801acbb9  lea     rcx, aDwmsceneDll; "DwmScene.dll"
0x1801acbc0  call    cs:__imp_LoadLibraryW
0x1801acbc6  mov     rdx, rax
0x1801acbc9  mov     rcx, r14
0x1801acbcc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1801acbd1  mov     rcx, [r14]; hModule
0x1801acbd4  test    rcx, rcx
0x1801acbd7  jnz     short loc_1801ACBE2
0x1801acbd9  mov     byte ptr [rdi+50h], 1
0x1801acbdd  jmp     loc_1801ACF40
0x1801acbe2  cmp     [rdi+18h], r13
0x1801acbe6  jnz     loc_1801ACF40
0x1801acbec  lea     rdx, aCreatedwmscene; "CreateDwmSceneRenderer"
0x1801acbf3  call    cs:__imp_GetProcAddress
0x1801acbf9  mov     r12, rax
0x1801acbfc  test    rax, rax
0x1801acbff  jnz     short loc_1801ACC1B
0x1801acc01  mov     ebx, 8000FFFFh
0x1801acc06  mov     [rsp+220h+var_1F8], r13
0x1801acc0b  mov     r9d, ebx
0x1801acc0e  mov     [rsp+220h+var_200], 5Bh ; '['
0x1801acc16  jmp     loc_1801ACF15
0x1801acc1b  cmp     cs:?m_fSceneForceNonPrimaryDisplayAdapter@CCommonRegistryData@@0HA, r13d; int CCommonRegistryData::m_fSceneForceNonPrimaryDisplayAdapter
0x1801acc22  jz      loc_1801ACD7F
0x1801acc28  lea     rdx, [rsp+220h+var_1E0]; struct IDXGIFactory5 **
0x1801acc2d  mov     [rsp+220h+var_1E0], r13
0x1801acc32  call    ?GetDXGIFactory@CDisplayManager@@QEAAJPEAPEAUIDXGIFactory5@@@Z; CDisplayManager::GetDXGIFactory(IDXGIFactory5 * *)
0x1801acc37  test    eax, eax
0x1801acc39  js      loc_1801ACD39
0x1801acc3f  mov     r15, [rsp+220h+var_1E0]
0x1801acc44  mov     esi, r13d
0x1801acc47  mov     [rsp+220h+var_1E8], r13
0x1801acc4c  mov     rax, [r15]
0x1801acc4f  lea     rcx, [rsp+220h+var_1E8]
0x1801acc54  mov     [rsp+220h+var_1B8], rcx
0x1801acc59  lea     r8, [rsp+220h+var_1B0]
0x1801acc5e  mov     edx, esi
0x1801acc60  mov     [rsp+220h+var_1B0], r13
0x1801acc65  mov     rcx, r15
0x1801acc68  mov     [rsp+220h+var_1A8], 1
0x1801acc6d  mov     rax, [rax+60h]
0x1801acc71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801acc76  lea     rcx, [rsp+220h+var_1B8]
0x1801acc7b  mov     ebx, eax
0x1801acc7d  call    ??1?$out_param_t@V?$com_ptr_t@UIDXGIOutput@@Uerr_returncode_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<IDXGIOutput,wil::err_returncode_policy>>::~out_param_t<wil::com_ptr_t<IDXGIOutput,wil::err_returncode_policy>>(void)
0x1801acc82  shr     ebx, 1Fh
0x1801acc85  xor     bl, 1
0x1801acc88  jz      loc_1801ACD2F
0x1801acc8e  xor     edx, edx; Val
0x1801acc90  lea     rcx, [rbp+120h+var_190]; void *
0x1801acc94  mov     r8d, 138h; Size
0x1801acc9a  call    memset_0
0x1801acc9f  mov     rcx, [rsp+220h+var_1E8]
0x1801acca4  lea     rdx, [rbp+120h+var_190]
0x1801acca8  mov     rax, [rcx]
0x1801accab  mov     rax, [rax+50h]
0x1801accaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801accb4  test    eax, eax
0x1801accb6  js      short loc_1801ACCD9
0x1801accb8  lea     rdx, [rbp+120h+var_1A0]
0x1801accbc  call    ?GetPrimaryAdapterLuid@CDisplayManager@@QEAA?AU_LUID@@XZ; CDisplayManager::GetPrimaryAdapterLuid(void)
0x1801accc1  mov     rcx, rax
0x1801accc4  mov     eax, [rax]
0x1801accc6  cmp     [rbp+120h+var_68.LowPart], eax
0x1801acccc  jnz     short loc_1801ACCE0
0x1801accce  mov     eax, [rcx+4]
0x1801accd1  cmp     [rbp+120h+var_68.HighPart], eax
0x1801accd7  jnz     short loc_1801ACCE0
0x1801accd9  inc     esi
0x1801accdb  jmp     loc_1801ACC4C
0x1801acce0  lea     rcx, [rdi+20h]
0x1801acce4  call    ?reset@?$com_ptr_t@VCD3DDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CD3DDevice,wil::err_returncode_policy>::reset(void)
0x1801acce9  mov     rdx, qword ptr [rbp+120h+var_68.LowPart]; struct _LUID
0x1801accf0  lea     r8, [rdi+20h]; struct CD3DDevice **
0x1801accf4  lea     rcx, ?g_DeviceManager@@3VCDeviceManager@@A; this
0x1801accfb  call    ?GetDevice@CDeviceManager@@QEAAJU_LUID@@PEAPEAVCD3DDevice@@@Z; CDeviceManager::GetDevice(_LUID,CD3DDevice * *)
0x1801acd00  mov     ebx, eax
0x1801acd02  test    eax, eax
0x1801acd04  jns     short loc_1801ACD2F
0x1801acd06  xor     edx, edx; int *
0x1801acd08  mov     [rsp+220h+var_1F8], r13; void *
0x1801acd0d  mov     r9d, eax; int
0x1801acd10  mov     [rsp+220h+var_200], 6Dh ; 'm'; unsigned int
0x1801acd18  xor     r8d, r8d; unsigned int
0x1801acd1b  lea     ecx, [rdx+14h]; unsigned int
0x1801acd1e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801acd23  lea     rcx, [rsp+220h+var_1E8]
0x1801acd28  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801acd2d  jmp     short loc_1801ACD64
0x1801acd2f  lea     rcx, [rsp+220h+var_1E8]
0x1801acd34  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801acd39  lea     rsi, [rdi+20h]
0x1801acd3d  cmp     [rsi], r13
0x1801acd40  jnz     short loc_1801ACD73
0x1801acd42  xor     edx, edx; int *
0x1801acd44  mov     [rsp+220h+var_1F8], r13; void *
0x1801acd49  mov     ebx, 80004005h
0x1801acd4e  mov     [rsp+220h+var_200], 77h ; 'w'; unsigned int
0x1801acd56  mov     r9d, ebx; int
0x1801acd59  xor     r8d, r8d; unsigned int
0x1801acd5c  lea     ecx, [rdx+14h]; unsigned int
0x1801acd5f  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801acd64  lea     rcx, [rsp+220h+var_1E0]
0x1801acd69  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801acd6e  jmp     loc_1801ACF22
0x1801acd73  lea     rcx, [rsp+220h+var_1E0]
0x1801acd78  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801acd7d  jmp     short loc_1801ACD9D
0x1801acd7f  lea     rsi, [rdi+20h]
0x1801acd83  mov     rcx, rsi
0x1801acd86  call    ?reset@?$com_ptr_t@VCD3DDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<CD3DDevice,wil::err_returncode_policy>::reset(void)
0x1801acd8b  mov     rdx, rsi; struct CD3DDevice **
0x1801acd8e  call    ?GetDefaultDevice@CDeviceManager@@QEAAJPEAPEAVCD3DDevice@@@Z; CDeviceManager::GetDefaultDevice(CD3DDevice * *)
0x1801acd93  mov     ebx, eax
0x1801acd95  test    eax, eax
0x1801acd97  js      loc_1801ACF05
0x1801acd9d  mov     rax, [rsi]
0x1801acda0  lea     r8, [rsp+220h+var_1F0]
0x1801acda5  movss   xmm0, cs:?m_flSceneImageProcessingResizeThreshold@CCommonRegistryData@@0MA; float CCommonRegistryData::m_flSceneImageProcessingResizeThreshold
0x1801acdad  lea     rdx, _GUID_c459639d_0878_4eb7_ade9_3655c96fa73a
0x1801acdb4  mov     [rsp+220h+var_1C0], r13
0x1801acdb9  mov     [rsp+220h+var_1D0], r13
0x1801acdbe  mov     [rsp+220h+var_1C8], r13
0x1801acdc3  mov     [rsp+220h+var_1D8], r13
0x1801acdc8  mov     rcx, [rax+220h]
0x1801acdcf  mov     eax, cs:?ImageProcessingMinWidth@Scene@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::Scene::ImageProcessingMinWidth
0x1801acdd5  mov     dword ptr [rsp+220h+var_1D0], eax
0x1801acdd9  mov     eax, cs:?ImageProcessingMinHeight@Scene@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::Scene::ImageProcessingMinHeight
0x1801acddf  mov     dword ptr [rsp+220h+var_1D0+4], eax
0x1801acde3  mov     eax, cs:?ImageProcessingResizeGrowth@Scene@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::Scene::ImageProcessingResizeGrowth
0x1801acde9  mov     dword ptr [rsp+220h+var_1C8], eax
0x1801acded  mov     eax, cs:?MsaaQualityMode@Scene@CCommonRegistryData@@2V?$CRegistryKey@KK@details@@B; details::CRegistryKey<ulong,ulong> const CCommonRegistryData::Scene::MsaaQualityMode
0x1801acdf3  mov     dword ptr [rsp+220h+var_1C0], eax
0x1801acdf7  mov     al, cs:?EnableBloom@Scene@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B; details::CRegistryKey<bool,bool> const CCommonRegistryData::Scene::EnableBloom
0x1801acdfd  mov     byte ptr [rsp+220h+var_1C0+4], al
0x1801ace01  mov     al, cs:?EnableImageProcessing@Scene@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B; details::CRegistryKey<bool,bool> const CCommonRegistryData::Scene::EnableImageProcessing
0x1801ace07  mov     byte ptr [rsp+220h+var_1C0+5], al
0x1801ace0b  mov     al, cs:?ImageProcessing8bit@Scene@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B; details::CRegistryKey<bool,bool> const CCommonRegistryData::Scene::ImageProcessing8bit
0x1801ace11  mov     byte ptr [rsp+220h+var_1C0+6], al
0x1801ace15  mov     al, cs:?EnableShadow@Scene@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B; details::CRegistryKey<bool,bool> const CCommonRegistryData::Scene::EnableShadow
0x1801ace1b  mov     byte ptr [rsp+220h+var_1C0+7], al
0x1801ace1f  mov     rax, r12
0x1801ace22  mov     [rsp+220h+var_1D8], rcx
0x1801ace27  lea     rcx, [rsp+220h+var_1D8]
0x1801ace2c  movss   dword ptr [rsp+220h+var_1C8+4], xmm0
0x1801ace32  mov     [rsp+220h+var_1F0], r13
0x1801ace37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ace3c  mov     ebx, eax
0x1801ace3e  test    eax, eax
0x1801ace40  js      loc_1801ACEDC
0x1801ace46  lea     rbx, [rdi+18h]
0x1801ace4a  mov     rcx, [rbx]
0x1801ace4d  mov     [rbx], r13
0x1801ace50  test    rcx, rcx
0x1801ace53  jz      short loc_1801ACE5A
0x1801ace55  call    ?InternalRelease@?$CMILRefCountBaseT@VIDeviceResource@@VCMilObjectDeleter@@@@IEAAKXZ; CMILRefCountBaseT<IDeviceResource,CMilObjectDeleter>::InternalRelease(void)
0x1801ace5a  mov     rdx, [rsp+220h+var_1F0]; struct IUnknown *
0x1801ace5f  mov     r8, rbx; struct CExternalD3DRenderer **
0x1801ace62  mov     rcx, [rsi]; struct CD3DDevice *
0x1801ace65  call    ?Create@CExternalD3DRenderer@@SAJPEAVCD3DDevice@@PEAUIUnknown@@PEAPEAV1@@Z; CExternalD3DRenderer::Create(CD3DDevice *,IUnknown *,CExternalD3DRenderer * *)
0x1801ace6a  mov     ebx, eax
0x1801ace6c  test    eax, eax
0x1801ace6e  js      short loc_1801ACECD
0x1801ace70  mov     rcx, [rdi+18h]
0x1801ace74  add     rcx, 30h ; '0'
0x1801ace78  mov     [rsp+220h+var_1E8], rdi
0x1801ace7d  mov     rdx, [rcx+8]
0x1801ace81  cmp     rdx, [rcx+10h]
0x1801ace85  jz      short loc_1801ACE91
0x1801ace87  mov     [rdx], rdi
0x1801ace8a  add     qword ptr [rcx+8], 8
0x1801ace8f  jmp     short loc_1801ACE9B
0x1801ace91  lea     r8, [rsp+220h+var_1E8]
0x1801ace96  call    ??$_Emplace_reallocate@AEBQEAVBamoPrincipalImpl@BamoImpl@Microsoft@@@?$vector@PEAVBamoPrincipalImpl@BamoImpl@Microsoft@@V?$allocator@PEAVBamoPrincipalImpl@BamoImpl@Microsoft@@@std@@@std@@AEAAPEAPEAVBamoPrincipalImpl@BamoImpl@Microsoft@@QEAPEAV234@AEBQEAV234@@Z; std::vector<Microsoft::BamoImpl::BamoPrincipalImpl *>::_Emplace_reallocate<Microsoft::BamoImpl::BamoPrincipalImpl * const &>(Microsoft::BamoImpl::BamoPrincipalImpl * * const,Microsoft::BamoImpl::BamoPrincipalImpl * const &)
0x1801ace9b  mov     rsi, [rdi+30h]
0x1801ace9f  mov     rdi, [rdi+28h]
0x1801acea3  jmp     short loc_1801ACEBC
0x1801acea5  mov     rcx, [rdi]
0x1801acea8  mov     rdx, [rsp+220h+var_1F0]
0x1801acead  mov     rax, [rcx]
0x1801aceb0  mov     rax, [rax]
0x1801aceb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aceb8  add     rdi, 8
0x1801acebc  cmp     rdi, rsi
0x1801acebf  jnz     short loc_1801ACEA5
0x1801acec1  lea     rcx, [rsp+220h+var_1F0]
0x1801acec6  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801acecb  jmp     short loc_1801ACF40
0x1801acecd  mov     [rsp+220h+var_1F8], r13
0x1801aced2  mov     [rsp+220h+var_200], 8Eh
0x1801aceda  jmp     short loc_1801ACEE9
0x1801acedc  mov     [rsp+220h+var_1F8], r13; void *
0x1801acee1  mov     [rsp+220h+var_200], 8Ch; unsigned int
0x1801acee9  xor     edx, edx; int *
0x1801aceeb  mov     r9d, eax; int
0x1801aceee  xor     r8d, r8d; unsigned int
0x1801acef1  lea     ecx, [rdx+14h]; unsigned int
0x1801acef4  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801acef9  lea     rcx, [rsp+220h+var_1F0]
0x1801acefe  call    ??1?$com_ptr_t@UID3D11Resource@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID3D11Resource,wil::err_returncode_policy>::~com_ptr_t<ID3D11Resource,wil::err_returncode_policy>(void)
0x1801acf03  jmp     short loc_1801ACF22
0x1801acf05  mov     [rsp+220h+var_1F8], r13; void *
0x1801acf0a  mov     r9d, eax; int
0x1801acf0d  mov     [rsp+220h+var_200], 7Ch ; '|'; unsigned int
0x1801acf15  xor     edx, edx; int *
0x1801acf17  xor     r8d, r8d; unsigned int
0x1801acf1a  lea     ecx, [rdx+14h]; unsigned int
0x1801acf1d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801acf22  mov     byte ptr [rdi+50h], 1
0x1801acf26  mov     rcx, [rdi+18h]
0x1801acf2a  mov     [rdi+18h], r13
0x1801acf2e  test    rcx, rcx
0x1801acf31  jz      short loc_1801ACF38
0x1801acf33  call    ?InternalRelease@?$CMILRefCountBaseT@VIDeviceResource@@VCMilObjectDeleter@@@@IEAAKXZ; CMILRefCountBaseT<IDeviceResource,CMilObjectDeleter>::InternalRelease(void)
0x1801acf38  mov     rcx, r14
0x1801acf3b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::operator=(std::nullptr_t)
0x1801acf40  mov     eax, ebx
0x1801acf42  mov     rcx, [rbp+120h+var_50]
0x1801acf49  xor     rcx, rsp; StackCookie
0x1801acf4c  call    __security_check_cookie
0x1801acf51  add     rsp, 1E8h
0x1801acf58  pop     r15
0x1801acf5a  pop     r14
0x1801acf5c  pop     r13
0x1801acf5e  pop     r12
0x1801acf60  pop     rdi
0x1801acf61  pop     rsi
0x1801acf62  pop     rbx
0x1801acf63  pop     rbp
0x1801acf64  retn
```
