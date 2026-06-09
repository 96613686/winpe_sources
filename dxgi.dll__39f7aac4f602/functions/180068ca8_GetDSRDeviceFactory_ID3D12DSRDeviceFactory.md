# GetDSRDeviceFactory(ID3D12DSRDeviceFactory * *)

- ea: `0x180068ca8`
- end: `0x180068fb7`
- name: `?GetDSRDeviceFactory@@YAJPEAPEAUID3D12DSRDeviceFactory@@@Z`
- size: `783`
- prototype: `__int64 __fastcall(struct ID3D12DSRDeviceFactory **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180068718`

## callees

- `0x1800306f4`
- `0x1800405a4`
- `0x18004c6d4`
- `0x180067d2c`
- `0x180068ca8`
- `0x180068fc0`
- `0x18006903c`
- `0x180069078`
- `0x1800697a8`
- `0x180069864`
- `0x180075fa0`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068d0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068e7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068d0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180068e7c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180068cdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x180068cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068dbb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180068e43`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x180068e43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180068db1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryA` at `0x180068db1`

## string_xrefs

- `0x180068ced`: `onecoreuap\windows\DirectX\dxg\inc\DXGIEffectCommon.h`
- `0x180068d61`: `onecoreuap\windows\DirectX\dxg\inc\DXGIEffectCommon.h`
- `0x180068de0`: `onecoreuap\windows\DirectX\dxg\inc\DXGIEffectCommon.h`
- `0x180068e5a`: `onecoreuap\windows\DirectX\dxg\inc\DXGIEffectCommon.h`
- `0x180068e99`: `onecoreuap\windows\DirectX\dxg\inc\DXGIEffectCommon.h`
- `0x180068f2a`: `onecoreuap\windows\DirectX\dxg\inc\DXGIEffectCommon.h`
- `0x180068e0c`: `\d3d12core.dll`
- `0x180068cd6`: `d3d12.dll`

## pseudocode

```c
__int64 __fastcall GetDSRDeviceFactory(struct ID3D12DSRDeviceFactory **a1)
{
  HMODULE ModuleHandleA; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  FARPROC ProcAddress; // rbx
  int v7; // eax
  unsigned int LastError; // ebx
  int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  signed int v12; // eax
  void *v13; // rax
  __int64 v14; // rax
  const CHAR *v15; // rcx
  HMODULE LibraryA; // rax
  const char *v17; // r9
  FARPROC v18; // rdx
  LPCSTR *v19; // r8
  int v20; // eax
  __int64 v21; // rdx
  int v22; // [rsp+20h] [rbp-E0h]
  int v23[2]; // [rsp+30h] [rbp-D0h] BYREF
  HMODULE v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  LPCSTR lpLibFileName[3]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v27; // [rsp+60h] [rbp-A0h]
  CHAR v28[40]; // [rsp+68h] [rbp-98h] BYREF
  CHAR Buffer[272]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  ModuleHandleA = GetModuleHandleA("d3d12.dll");
  if ( !ModuleHandleA )
  {
    v4 = 142;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\inc\\DXGIEffectCommon.h",
             v3);
  }
  ProcAddress = GetProcAddress(ModuleHandleA, "D3D12GetInterface");
  if ( !ProcAddress )
  {
    v4 = 144;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\inc\\DXGIEffectCommon.h",
             v3);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
  {
    v25 = 0;
    v9 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
           &CLSID_D3D12SDKConfiguration,
           &GUID_8aaf9303_ad25_48b9_9a57_d9c37e009d9f,
           &v25);
    LastError = v9;
    if ( v9 >= 0 )
    {
      if ( GetSystemDirectoryA(Buffer, 0x104u) )
      {
        v13 = (void *)std::string::string(v28, Buffer);
        v14 = std::string::_Append<char>(v13);
        std::string::string(lpLibFileName, v14);
        std::string::~string(v28);
        v15 = (const CHAR *)lpLibFileName;
        if ( v27 > 0xF )
          v15 = lpLibFileName[0];
        LibraryA = LoadLibraryA(v15);
        v24 = LibraryA;
        if ( LibraryA )
        {
          v18 = GetProcAddress(LibraryA, "D3D12SDKVersion");
          if ( v18 )
          {
            *(_QWORD *)v23 = 0;
            v19 = lpLibFileName;
            if ( v27 > 0xF )
              v19 = (LPCSTR *)lpLibFileName[0];
            v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPCSTR *, GUID *))(*(_QWORD *)v25 + 32LL))(
                    v25,
                    *(unsigned int *)v18,
                    v19,
                    &GUID_61f307d3_d34e_4e7c_8374_3ba4de23cccb);
            LastError = v20;
            if ( v20 >= 0 )
            {
              v20 = (*(__int64 (__fastcall **)(_QWORD, GUID *, GUID *, struct ID3D12DSRDeviceFactory **))(**(_QWORD **)v23 + 56LL))(
                      *(_QWORD *)v23,
                      &CLSID_D3D12DSRDeviceFactoryInt,
                      &GUID_f343d1a0_afe3_439f_b13d_cd87a43b70ca,
                      a1);
              LastError = v20;
              if ( v20 >= 0 )
              {
                ATL::CComPtrBase<ID2D1Effect>::~CComPtrBase<ID2D1Effect>(v23);
                wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v24);
                std::string::~string(lpLibFileName);
                ATL::CComPtrBase<ID2D1Effect>::~CComPtrBase<ID2D1Effect>(&v25);
                return 0;
              }
              v21 = 168;
            }
            else
            {
              v21 = 165;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v21,
              (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\inc\\DXGIEffectCommon.h",
              (const char *)(unsigned int)v20,
              (int)v23);
            ATL::CComPtrBase<ID2D1Effect>::~CComPtrBase<ID2D1Effect>(v23);
          }
          else
          {
            LastError = -2147467259;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xA2,
              (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\inc\\DXGIEffectCommon.h",
              (const char *)0x80004005LL,
              v22);
          }
        }
        else
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xA0,
                        (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\inc\\DXGIEffectCommon.h",
                        v17);
        }
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v24);
        std::string::~string(lpLibFileName);
LABEL_31:
        ATL::CComPtrBase<ID2D1Effect>::~CComPtrBase<ID2D1Effect>(&v25);
        return LastError;
      }
      v12 = GetLastError();
      LastError = v12;
      if ( v12 > 0 )
        LastError = (unsigned __int16)v12 | 0x80070000;
      if ( (LastError & 0x80000000) == 0 )
        goto LABEL_31;
      v10 = LastError;
      v11 = 157;
    }
    else
    {
      v10 = (unsigned int)v9;
      v11 = 154;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\inc\\DXGIEffectCommon.h",
      (const char *)v10,
      v22);
    goto LABEL_31;
  }
  v7 = ((__int64 (__fastcall *)(GUID *, GUID *, struct ID3D12DSRDeviceFactory **))ProcAddress)(
         &CLSID_D3D12DSRDeviceFactoryInt,
         &GUID_f343d1a0_afe3_439f_b13d_cd87a43b70ca,
         a1);
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecoreuap\\windows\\DirectX\\dxg\\inc\\DXGIEffectCommon.h",
      (const char *)(unsigned int)v7,
      v22);
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x180068ca8  mov     [rsp-8+arg_8], rbx
0x180068cad  mov     [rsp-8+arg_10], rdi
0x180068cb2  push    rbp
0x180068cb3  lea     rbp, [rsp-0B0h]
0x180068cbb  sub     rsp, 1B0h
0x180068cc2  mov     rax, cs:__security_cookie
0x180068cc9  xor     rax, rsp
0x180068ccc  mov     [rbp+0B0h+var_10], rax
0x180068cd3  mov     rdi, rcx
0x180068cd6  lea     rcx, aD3d12Dll; "d3d12.dll"
0x180068cdd  call    cs:__imp_GetModuleHandleA
0x180068ce3  test    rax, rax
0x180068ce6  jnz     short loc_180068D05
0x180068ce8  mov     edx, 8Eh; void *
0x180068ced  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\DirectX\\dxg\\inc"...
0x180068cf4  mov     rcx, [rbp+0B8h]; this
0x180068cfb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180068d00  jmp     loc_180068F93
0x180068d05  lea     rdx, aD3d12getinterf; "D3D12GetInterface"
0x180068d0c  mov     rcx, rax; hModule
0x180068d0f  call    cs:__imp_GetProcAddress
0x180068d15  mov     rbx, rax
0x180068d18  test    rax, rax
0x180068d1b  jnz     short loc_180068D24
0x180068d1d  mov     edx, 90h
0x180068d22  jmp     short loc_180068CED
0x180068d24  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x180068d2b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x180068d30  test    al, al
0x180068d32  mov     rax, rbx
0x180068d35  jnz     short loc_180068D77
0x180068d37  mov     r8, rdi
0x180068d3a  lea     rdx, _GUID_f343d1a0_afe3_439f_b13d_cd87a43b70ca
0x180068d41  lea     rcx, CLSID_D3D12DSRDeviceFactoryInt
0x180068d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d4d  mov     ebx, eax
0x180068d4f  test    eax, eax
0x180068d51  jns     loc_180068F91
0x180068d57  mov     rcx, [rbp+0B8h]; this
0x180068d5e  mov     r9d, eax; char *
0x180068d61  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\DirectX\\dxg\\inc"...
0x180068d68  mov     edx, 0ADh; void *
0x180068d6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068d72  jmp     loc_180068F65
0x180068d77  mov     [rsp+1B0h+var_170], 0
0x180068d80  lea     r8, [rsp+1B0h+var_170]
0x180068d85  lea     rdx, _GUID_8aaf9303_ad25_48b9_9a57_d9c37e009d9f
0x180068d8c  lea     rcx, CLSID_D3D12SDKConfiguration
0x180068d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068d98  mov     ebx, eax
0x180068d9a  test    eax, eax
0x180068d9c  jns     short loc_180068DA8
0x180068d9e  mov     r9d, eax
0x180068da1  mov     edx, 9Ah
0x180068da6  jmp     short loc_180068DE0
0x180068da8  mov     edx, 104h; uSize
0x180068dad  lea     rcx, [rbp+0B0h+Buffer]; lpBuffer
0x180068db1  call    cs:__imp_GetSystemDirectoryA
0x180068db7  test    eax, eax
0x180068db9  jnz     short loc_180068DF8
0x180068dbb  call    cs:__imp_GetLastError
0x180068dc1  mov     ebx, eax
0x180068dc3  test    eax, eax
0x180068dc5  jle     short loc_180068DD0
0x180068dc7  movzx   ebx, ax
0x180068dca  or      ebx, 80070000h
0x180068dd0  test    ebx, ebx
0x180068dd2  jns     loc_180068F5B
0x180068dd8  mov     r9d, ebx; char *
0x180068ddb  mov     edx, 9Dh; void *
0x180068de0  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\DirectX\\dxg\\inc"...
0x180068de7  mov     rcx, [rbp+0B8h]; this
0x180068dee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068df3  jmp     loc_180068F5B
0x180068df8  lea     rdx, [rbp+0B0h+Buffer]
0x180068dfc  lea     rcx, [rsp+1B0h+var_148]
0x180068e01  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180068e06  mov     r8d, 0Eh
0x180068e0c  lea     rdx, aD3d12coreDll; "\\d3d12core.dll"
0x180068e13  mov     rcx, rax; Src
0x180068e16  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x180068e1b  mov     rdx, rax
0x180068e1e  lea     rcx, [rsp+1B0h+lpLibFileName]
0x180068e23  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@$$QEAV01@@Z; std::string::string(std::string &&)
0x180068e28  lea     rcx, [rsp+1B0h+var_148]
0x180068e2d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180068e32  lea     rcx, [rsp+1B0h+lpLibFileName]
0x180068e37  cmp     [rsp+1B0h+var_150], 0Fh
0x180068e3d  cmova   rcx, [rsp+1B0h+lpLibFileName]; lpLibFileName
0x180068e43  call    cs:__imp_LoadLibraryA
0x180068e49  mov     [rsp+1B0h+var_178], rax
0x180068e4e  test    rax, rax
0x180068e51  jnz     short loc_180068E72
0x180068e53  mov     rcx, [rbp+0B8h]; this
0x180068e5a  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\DirectX\\dxg\\inc"...
0x180068e61  mov     edx, 0A0h; void *
0x180068e66  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180068e6b  mov     ebx, eax
0x180068e6d  jmp     loc_180068F47
0x180068e72  lea     rdx, aD3d12sdkversio; "D3D12SDKVersion"
0x180068e79  mov     rcx, rax; hModule
0x180068e7c  call    cs:__imp_GetProcAddress
0x180068e82  mov     rdx, rax
0x180068e85  test    rax, rax
0x180068e88  jnz     short loc_180068EAF
0x180068e8a  mov     rcx, [rbp+0B8h]; this
0x180068e91  mov     ebx, 80004005h
0x180068e96  mov     r9d, ebx; char *
0x180068e99  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\DirectX\\dxg\\inc"...
0x180068ea0  mov     edx, 0A2h; void *
0x180068ea5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068eaa  jmp     loc_180068F47
0x180068eaf  mov     qword ptr [rsp+1B0h+var_180], 0
0x180068eb8  mov     rcx, [rsp+1B0h+var_170]
0x180068ebd  mov     rax, [rcx]
0x180068ec0  lea     r8, [rsp+1B0h+lpLibFileName]
0x180068ec5  cmp     [rsp+1B0h+var_150], 0Fh
0x180068ecb  cmova   r8, [rsp+1B0h+lpLibFileName]
0x180068ed1  lea     r9, [rsp+1B0h+var_180]
0x180068ed6  mov     qword ptr [rsp+1B0h+var_190], r9; int
0x180068edb  lea     r9, _GUID_61f307d3_d34e_4e7c_8374_3ba4de23cccb
0x180068ee2  mov     edx, [rdx]
0x180068ee4  mov     rax, [rax+20h]
0x180068ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068eed  mov     ebx, eax
0x180068eef  test    eax, eax
0x180068ef1  jns     short loc_180068EFA
0x180068ef3  mov     edx, 0A5h
0x180068ef8  jmp     short loc_180068F27
0x180068efa  mov     rcx, qword ptr [rsp+1B0h+var_180]
0x180068eff  mov     rax, [rcx]
0x180068f02  mov     r9, rdi
0x180068f05  lea     r8, _GUID_f343d1a0_afe3_439f_b13d_cd87a43b70ca
0x180068f0c  lea     rdx, CLSID_D3D12DSRDeviceFactoryInt
0x180068f13  mov     rax, [rax+38h]
0x180068f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068f1c  mov     ebx, eax
0x180068f1e  test    eax, eax
0x180068f20  jns     short loc_180068F69
0x180068f22  mov     edx, 0A8h; void *
0x180068f27  mov     r9d, eax; char *
0x180068f2a  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\DirectX\\dxg\\inc"...
0x180068f31  mov     rcx, [rbp+0B8h]; this
0x180068f38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180068f3d  lea     rcx, [rsp+1B0h+var_180]
0x180068f42  call    ??1?$CComPtrBase@UID2D1Effect@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID2D1Effect>::~CComPtrBase<ID2D1Effect>(void)
0x180068f47  lea     rcx, [rsp+1B0h+var_178]
0x180068f4c  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180068f51  lea     rcx, [rsp+1B0h+lpLibFileName]
0x180068f56  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180068f5b  lea     rcx, [rsp+1B0h+var_170]
0x180068f60  call    ??1?$CComPtrBase@UID2D1Effect@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID2D1Effect>::~CComPtrBase<ID2D1Effect>(void)
0x180068f65  mov     eax, ebx
0x180068f67  jmp     short loc_180068F93
0x180068f69  lea     rcx, [rsp+1B0h+var_180]
0x180068f6e  call    ??1?$CComPtrBase@UID2D1Effect@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID2D1Effect>::~CComPtrBase<ID2D1Effect>(void)
0x180068f73  lea     rcx, [rsp+1B0h+var_178]
0x180068f78  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180068f7d  lea     rcx, [rsp+1B0h+lpLibFileName]
0x180068f82  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180068f87  lea     rcx, [rsp+1B0h+var_170]
0x180068f8c  call    ??1?$CComPtrBase@UID2D1Effect@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ID2D1Effect>::~CComPtrBase<ID2D1Effect>(void)
0x180068f91  xor     eax, eax
0x180068f93  mov     rcx, [rbp+0B0h+var_10]
0x180068f9a  xor     rcx, rsp; StackCookie
0x180068f9d  call    __security_check_cookie
0x180068fa2  lea     r11, [rsp+1B0h+var_s0]
0x180068faa  mov     rbx, [r11+18h]
0x180068fae  mov     rdi, [r11+20h]
0x180068fb2  mov     rsp, r11
0x180068fb5  pop     rbp
0x180068fb6  retn
```
