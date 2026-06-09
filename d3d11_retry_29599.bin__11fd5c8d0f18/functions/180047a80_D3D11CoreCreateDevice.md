# D3D11CoreCreateDevice

- ea: `0x180047a80`
- end: `0x1800484b2`
- name: `D3D11CoreCreateDevice`
- size: `2610`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004a080`
- `0x1800a5d80`

## callees

- `0x18000bad0`
- `0x1800229a0`
- `0x180034550`
- `0x180047a80`
- `0x1800484b8`
- `0x1800485b4`
- `0x18004861c`
- `0x180048670`
- `0x180048f24`
- `0x180048f90`
- `0x180048fa8`
- `0x180049020`
- `0x1800490f4`
- `0x18004911c`
- `0x1800491ec`
- `0x180049310`
- `0x180049390`
- `0x180049bf8`
- `0x180059bcc`
- `0x18009d94c`
- `0x1800a463c`
- `0x1800a9d20`
- `0x1800ac5a4`
- `0x1800add68`
- `0x1800dd664`
- `0x1801cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180048431`
- `ntdll!EtwEventWrite` at `0x180048491`
- `ntdll!EtwEventWrite` at `0x180048431`
- `ntdll!EtwEventWrite` at `0x180048491`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048038`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048038`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047ff6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047ff6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047f27`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047f27`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180047cc7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800481a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180047cc7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800481a0`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180048049`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180048049`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall D3D11CoreCreateDevice(
        __int128 *a1,
        struct IUnknown *a2,
        D3D_DRIVER_TYPE a3,
        HINSTANCE a4,
        unsigned int a5,
        enum D3D_FEATURE_LEVEL *a6,
        unsigned int a7,
        int a8,
        struct ID3D11Device **a9,
        enum D3D_FEATURE_LEVEL *a10)
{
  unsigned int v13; // r15d
  enum D3D_FEATURE_LEVEL *v14; // rax
  __int64 v15; // rcx
  unsigned int v16; // eax
  unsigned __int16 CreateDeviceProperties; // si
  bool v18; // r13
  bool v19; // r9
  __int16 v20; // dx
  HMODULE v21; // rdi
  enum D3D_FEATURE_LEVEL *v22; // rbx
  signed int Device; // r15d
  int v24; // eax
  bool *v25; // rcx
  bool *v26; // r12
  bool v27; // r12
  enum D3D_FEATURE_LEVEL v28; // esi
  bool v29; // di
  unsigned int v30; // edx
  enum D3D_FEATURE_LEVEL *v31; // rbx
  struct ID3D11Device **v32; // rdi
  HANDLE CurrentProcess; // rax
  int v35; // r12d
  enum D3D_FEATURE_LEVEL *v36; // rbx
  enum D3D_FEATURE_LEVEL *v37; // r15
  __int64 v38; // r13
  int *v39; // rdi
  int *v40; // rbx
  int v41; // r15d
  enum D3D_FEATURE_LEVEL *i; // r13
  int v43; // eax
  int *v44; // rdi
  int *v45; // rbx
  int *v46; // rdi
  int *v47; // rbx
  __int16 v48; // [rsp+40h] [rbp-2F8h] BYREF
  _BYTE v49[2]; // [rsp+42h] [rbp-2F6h] BYREF
  unsigned int v50; // [rsp+44h] [rbp-2F4h]
  unsigned int v51; // [rsp+48h] [rbp-2F0h]
  __int16 v52; // [rsp+4Ch] [rbp-2ECh]
  D3D_DRIVER_TYPE v53[2]; // [rsp+50h] [rbp-2E8h] BYREF
  enum D3D_FEATURE_LEVEL *v54; // [rsp+58h] [rbp-2E0h]
  enum D3D_FEATURE_LEVEL *v55; // [rsp+60h] [rbp-2D8h] BYREF
  enum D3D_FEATURE_LEVEL *v56; // [rsp+68h] [rbp-2D0h]
  char *v57; // [rsp+70h] [rbp-2C8h]
  enum D3D_FEATURE_LEVEL *v58; // [rsp+78h] [rbp-2C0h]
  __int64 v59; // [rsp+80h] [rbp-2B8h] BYREF
  __int64 v60; // [rsp+88h] [rbp-2B0h] BYREF
  __int64 v61; // [rsp+90h] [rbp-2A8h] BYREF
  __int64 v62; // [rsp+98h] [rbp-2A0h] BYREF
  struct CCreateDeviceCache::CAdapterCache *v63; // [rsp+A0h] [rbp-298h] BYREF
  HMODULE v64; // [rsp+A8h] [rbp-290h] BYREF
  struct IUnknown *v65; // [rsp+B0h] [rbp-288h]
  unsigned __int64 v66; // [rsp+B8h] [rbp-280h] BYREF
  struct ID3D11Device **v67; // [rsp+C0h] [rbp-278h]
  struct ID3D11Device **v68; // [rsp+C8h] [rbp-270h]
  __int64 v69; // [rsp+D0h] [rbp-268h]
  __int128 v70; // [rsp+D8h] [rbp-260h] BYREF
  __int64 v71; // [rsp+E8h] [rbp-250h]
  __int128 v72; // [rsp+F0h] [rbp-248h] BYREF
  HINSTANCE v73; // [rsp+100h] [rbp-238h]
  void *v74; // [rsp+108h] [rbp-230h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+110h] [rbp-228h] BYREF
  char v76; // [rsp+118h] [rbp-220h]
  void **pExceptionObject; // [rsp+128h] [rbp-210h] BYREF
  int v78; // [rsp+130h] [rbp-208h]
  __int128 v79; // [rsp+138h] [rbp-200h]
  unsigned int DeviceFlags; // [rsp+150h] [rbp-1E8h] BYREF
  __int64 v81; // [rsp+158h] [rbp-1E0h] BYREF
  _BYTE v82[200]; // [rsp+160h] [rbp-1D8h] BYREF
  _BYTE v83[200]; // [rsp+228h] [rbp-110h] BYREF

  v73 = a4;
  v53[0] = a3;
  v65 = a2;
  v13 = a5;
  v50 = a5;
  v54 = a6;
  v51 = a7;
  v67 = a9;
  v68 = a9;
  v14 = a10;
  v58 = a10;
  v69 = (__int64)a10;
  if ( dword_1802282A4 && (qword_180228290 & 0x2000000000000002LL) != 0 )
  {
    if ( (qword_180228298 & 0x2000000000000002LL) == qword_180228298 )
      EtwEventWrite(Direct3D11EtwProviderGuid_Context, &EventInitiatingD3D11CoreCreateDevice, 0, 0);
    v14 = v58;
  }
  v74 = &EventFinishedD3D11CoreCreateDevice;
  if ( a9 )
    *a9 = 0;
  if ( v14 )
    *v14 = 0;
  v15 = 0;
  v72 = 0u;
  v16 = 0;
  if ( a1 )
  {
    v72 = *a1;
    v16 = *((_DWORD *)a1 + 2);
    v15 = v72;
  }
  if ( v16 >= 0xFF || !v15 && v16 )
  {
    if ( dword_1802282A4
      && (qword_180228290 & 0x2000000000000002LL) != 0
      && (qword_180228298 & 0x2000000000000002LL) == qword_180228298 )
    {
      EtwEventWrite(Direct3D11EtwProviderGuid_Context, &EventFinishedD3D11CoreCreateDevice, 0, 0);
    }
    return 2147942487LL;
  }
  v60 = 0;
  if ( (a5 & 0x80u) == 0
    && InitOnceExecuteOnce(&InitOnce, CModule::InitOnceGetProcAddress, 0, &Context)
    && *(_QWORD *)Context
    && (*(unsigned int (__fastcall **)(const char *, __int64 *))Context)("ForceDebuggable", &v60)
    && v60 )
  {
    v13 = a5 | 0x40;
    v50 = a5 | 0x40;
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(
    &lpCriticalSection,
    &xmmword_18022B808);
  qword_18022B838 = 0;
  dword_18022B914 = 1;
  dword_18022B910 = 1;
  v61 = 0;
  if ( !(unsigned int)IsGetProcessUIContextInformationPresent()
    || (CurrentProcess = GetCurrentProcess(), !(unsigned int)GetProcessUIContextInformation(CurrentProcess, &v61))
    || (byte_18022B848 = 1, (_DWORD)v61 != 1) )
  {
    byte_18022B848 = 0;
  }
  DeviceFlags = FactoryFlagsFromCreateDeviceFlags(v13);
  v81 = 0;
  CCreateDeviceCache::CAdapterCache::CAdapterCache(
    (CCreateDeviceCache::CAdapterCache *)v82,
    (struct FailureData::AdapterFailureData *)&unk_18022B918);
  CCreateDeviceCache::CAdapterCache::CAdapterCache(
    (CCreateDeviceCache::CAdapterCache *)v83,
    (struct FailureData::AdapterFailureData *)&unk_18022B978);
  std::vector<CCommandList *>::vector<CCommandList *>(&v55);
  CreateDeviceProperties = GetCreateDeviceProperties(&DeviceFlags, a2, (unsigned int)a3);
  if ( !(unsigned int)EnableFeatureLevelUpgrade() )
  {
    std::vector<enum D3D_FEATURE_LEVEL>::_Insert_counted_range<enum D3D_FEATURE_LEVEL const *>(&v55, v55, v54, v51);
    goto LABEL_16;
  }
  v35 = 49408;
  v36 = v54;
  if ( !(_BYTE)CreateDeviceProperties )
  {
    v41 = 37632;
    for ( i = v54; ; ++i )
    {
      if ( i == &v36[v51] )
        goto LABEL_16;
      v43 = *i;
      if ( *(int *)i < 40960 )
        break;
      if ( v43 <= v35 )
      {
        v46 = (int *)&unk_1801F4A08;
        do
        {
          if ( *v46 == v43 )
            break;
          ++v46;
        }
        while ( v46 != (int *)&unk_1801F4A20 );
        v47 = (int *)&unk_1801F4A08;
        do
        {
          if ( *v47 == v35 )
            break;
          ++v47;
        }
        while ( v47 != (int *)&unk_1801F4A20 );
        do
        {
          if ( v56 == (enum D3D_FEATURE_LEVEL *)v57 )
            std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(&v55, v56, v47);
          else
            *v56++ = *v47;
          ++v47;
        }
        while ( v47 <= v46 );
        v35 = *v47;
LABEL_115:
        v36 = v54;
        continue;
      }
LABEL_116:
      ;
    }
    if ( v43 > v41 )
      goto LABEL_116;
    v44 = (int *)&unk_1801F49F8;
    do
    {
      if ( *v44 == v43 )
        break;
      ++v44;
    }
    while ( v44 != (int *)&unk_1801F4A04 );
    v45 = (int *)&unk_1801F49F8;
    do
    {
      if ( *v45 == v41 )
        break;
      ++v45;
    }
    while ( v45 != (int *)&unk_1801F4A04 );
    do
    {
      if ( v56 == (enum D3D_FEATURE_LEVEL *)v57 )
        std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(&v55, v56, v45);
      else
        *v56++ = *v45;
      ++v45;
    }
    while ( v45 <= v44 );
    v41 = *v45;
    goto LABEL_115;
  }
  v37 = v54;
  v38 = v51;
  while ( v37 != &v36[v38] )
  {
    if ( *v37 <= v35 )
    {
      v39 = (int *)&unk_1801F49C0;
      do
      {
        if ( *v39 == *v37 )
          break;
        ++v39;
      }
      while ( v39 != (int *)&unk_1801F49E4 );
      v40 = (int *)&unk_1801F49C0;
      do
      {
        if ( *v40 == v35 )
          break;
        ++v40;
      }
      while ( v40 != (int *)&unk_1801F49E4 );
      do
      {
        if ( v56 == (enum D3D_FEATURE_LEVEL *)v57 )
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int>(&v55, v56, v40);
        else
          *v56++ = *v40;
        ++v40;
      }
      while ( v40 <= v39 );
      v35 = *v40;
      v36 = v54;
    }
    ++v37;
  }
LABEL_16:
  std::vector<enum D3D_FEATURE_LEVEL>::operator=(&unk_18022B9F0, &v55);
  if ( Src != (void *)qword_18022B9E0 )
    qword_18022B9E0 = (__int64)Src;
  v62 = 0;
  if ( InitOnceExecuteOnce(&InitOnce, CModule::InitOnceGetProcAddress, 0, &Context) && *(_QWORD *)Context )
  {
    v18 = 1;
    if ( (*(unsigned int (__fastcall **)(const char *, __int64 *))Context)("EnableFL9Over11", &v62) )
      v18 = v62 != 0;
  }
  else
  {
    v18 = 1;
  }
  v66 = 0;
  std::vector<CCommandList *>::vector<CCommandList *>(&v70);
  v59 = 8;
  if ( (unsigned __int64)((v71 - (__int64)v70) >> 3) < 8 )
    std::vector<CCommandList *>::_Reallocate<0>(&v70, &v59);
  v20 = HIBYTE(CreateDeviceProperties);
  v52 = HIBYTE(CreateDeviceProperties);
  v21 = 0;
  v64 = 0;
  v22 = v55;
  Device = -2005270524;
LABEL_25:
  if ( v22 == v56 )
  {
LABEL_41:
    CModule::RecordJournal((CModule *)&g_Module, Device, "Failed to find DDI to drive requested feature levels", v19, 1);
  }
  else
  {
    v24 = -2005270524;
    v63 = 0;
    v48 = 256;
    v25 = v49;
    v59 = (__int64)v49;
    v26 = (bool *)&v48;
    if ( *(int *)v22 < 40960 )
    {
      if ( !v18 )
        v26 = (bool *)&v48 + 1;
      if ( !(_BYTE)v20 )
      {
        v25 = (bool *)&v48 + 1;
        v59 = (__int64)&v48 + 1;
      }
    }
    while ( v24 < 0 )
    {
      if ( v26 == v25 )
      {
        if ( v24 == -2005270523 )
        {
          Device = -2005270523;
          goto LABEL_41;
        }
        ++v22;
        LOBYTE(v20) = v52;
        goto LABEL_25;
      }
      v29 = *v26;
      v24 = CCreateDeviceCache::SelectAdapter(
              (CCreateDeviceCache *)&DeviceFlags,
              v65,
              v53[0],
              v73,
              *v22,
              (struct UniqueHMODULE *)&v64,
              *v26,
              &v63);
      if ( v24 >= 0 )
        v24 = CCreateDeviceCache::CAdapterCache::ResolveUMDAndVersion(
                v63,
                v50,
                !v29,
                (__int64)&qword_18022B838,
                (__int64)&v66);
      ++v26;
      v21 = v64;
      v25 = (bool *)v59;
    }
    v27 = 0;
    if ( v53[0] )
    {
      v27 = v53[0] == D3D_DRIVER_TYPE_WARP;
    }
    else if ( v65 )
    {
      *(_QWORD *)v53 = 0;
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, D3D_DRIVER_TYPE *))v65->lpVtbl->QueryInterface)(
             v65,
             &GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0,
             v53) >= 0 )
        v27 = IsExplicitWarpDriver(*(struct IDXGIAdapter **)v53);
      if ( *(_QWORD *)v53 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v53 + 16LL))(*(_QWORD *)v53);
    }
    v28 = InferAPIFeatureLevel(v54, v51, *v22, v27, (unsigned __int8)CreateDeviceProperties);
    if ( !v28 )
    {
      pExceptionObject = &_com_error::`vftable';
      v78 = -2005270524;
      v79 = 0;
      throw (_com_error *)&pExceptionObject;
    }
    Device = D3D11RegisterLayersAndCreateDevice(
               (const struct D3D11_EXTENSIONS *)&v72,
               qword_18022B838,
               *v22,
               v28,
               v66,
               v50,
               v67);
    if ( Device >= 0 )
    {
      if ( dword_18022B910 < 9 )
        dword_18022B914 = 9;
      dword_18022B910 = 9;
      v31 = v58;
      if ( v58 )
        *v58 = v28;
      goto LABEL_43;
    }
  }
  v31 = v58;
LABEL_43:
  if ( v21 )
    FreeLibrary(v21);
  if ( (_QWORD)v70 )
  {
    std::_Deallocate<16>(v70, (v71 - v70) & 0xFFFFFFFFFFFFFFF8uLL);
    v70 = 0;
    v71 = 0;
  }
  if ( v55 )
    std::_Deallocate<16>(v55, (v57 - (char *)v55) & 0xFFFFFFFFFFFFFFFCuLL);
  v32 = v67;
  if ( qword_18022B838 )
    NDXGI::CUMDAdapter::`scalar deleting destructor'(qword_18022B838, v30);
  qword_18022B838 = 0;
  if ( g_D3D11RegisteredLayers != *(&g_D3D11RegisteredLayers + 1) )
    *(&g_D3D11RegisteredLayers + 1) = g_D3D11RegisteredLayers;
  if ( Device < 0 )
  {
    if ( v32 )
    {
      if ( *v32 )
        ((void (__fastcall *)(struct ID3D11Device *))(*v32)->lpVtbl->Release)(*v32);
      *v32 = 0;
    }
    if ( v31 )
      *v31 = 0;
  }
  CCreateDeviceCache::CAdapterCache::~CAdapterCache((CCreateDeviceCache::CAdapterCache *)v83);
  CCreateDeviceCache::CAdapterCache::~CAdapterCache((CCreateDeviceCache::CAdapterCache *)v82);
  ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v81);
  if ( v76 )
    LeaveCriticalSection(lpCriticalSection);
  CETWEventPair::~CETWEventPair((CETWEventPair *)&v74);
  return (unsigned int)Device;
}

```

## disassembly

```asm
0x180047a80  push    rbx
0x180047a82  push    rsi
0x180047a83  push    rdi
0x180047a84  push    r12
0x180047a86  push    r13
0x180047a88  push    r14
0x180047a8a  push    r15
0x180047a8c  sub     rsp, 300h
0x180047a93  mov     rax, cs:__security_cookie
0x180047a9a  xor     rax, rsp
0x180047a9d  mov     [rsp+338h+var_48], rax
0x180047aa5  mov     [rsp+338h+var_238], r9
0x180047aad  mov     r12d, r8d
0x180047ab0  mov     [rsp+338h+var_2E8], r8d
0x180047ab5  mov     r13, rdx
0x180047ab8  mov     [rsp+338h+var_288], rdx
0x180047ac0  mov     rdi, rcx
0x180047ac3  mov     r15d, [rsp+338h+arg_20]
0x180047acb  mov     [rsp+338h+var_2F4], r15d
0x180047ad0  mov     rax, [rsp+338h+arg_28]
0x180047ad8  mov     [rsp+338h+var_2E0], rax
0x180047add  mov     eax, [rsp+338h+arg_30]
0x180047ae4  mov     [rsp+338h+var_2F0], eax
0x180047ae8  mov     rsi, [rsp+338h+arg_40]
0x180047af0  mov     [rsp+338h+var_278], rsi
0x180047af8  mov     [rsp+338h+var_270], rsi
0x180047b00  mov     rax, [rsp+338h+arg_48]
0x180047b08  mov     [rsp+338h+var_2C0], rax
0x180047b0d  mov     [rsp+338h+var_268], rax
0x180047b15  xor     r14d, r14d
0x180047b18  mov     rbx, 2000000000000002h
0x180047b22  cmp     cs:dword_1802282A4, r14d
0x180047b29  jz      short loc_180047B38
0x180047b2b  test    cs:qword_180228290, rbx
0x180047b32  jnz     loc_18004840A
0x180047b38  lea     r10, EventFinishedD3D11CoreCreateDevice
0x180047b3f  mov     [rsp+338h+var_230], r10
0x180047b47  test    rsi, rsi
0x180047b4a  jz      short loc_180047B4F
0x180047b4c  mov     [rsi], r14
0x180047b4f  test    rax, rax
0x180047b52  jz      short loc_180047B57
0x180047b54  mov     [rax], r14d
0x180047b57  mov     rcx, r14
0x180047b5a  mov     qword ptr [rsp+338h+var_248], rcx
0x180047b62  mov     eax, r14d
0x180047b65  mov     dword ptr [rsp+338h+var_248+8], eax
0x180047b6c  xor     edx, edx
0x180047b6e  mov     dword ptr [rsp+338h+var_248+0Ch], edx
0x180047b75  test    rdi, rdi
0x180047b78  jz      short loc_180047B8D
0x180047b7a  movups  xmm1, xmmword ptr [rdi]
0x180047b7d  movups  [rsp+338h+var_248], xmm1
0x180047b85  mov     eax, [rdi+8]
0x180047b88  movq    rcx, xmm1
0x180047b8d  cmp     eax, 0FFh
0x180047b92  jnb     loc_1800480C4
0x180047b98  test    rcx, rcx
0x180047b9b  jz      loc_1800480BC
0x180047ba1  mov     [rsp+338h+var_2B0], r14
0x180047ba9  test    r15b, r15b
0x180047bac  jns     loc_180048188
0x180047bb2  lea     rdx, xmmword_18022B808
0x180047bb9  lea     rcx, [rsp+338h+lpCriticalSection]
0x180047bc1  call    ??0?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@AEAVCComCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComCriticalSection>::CComCritSecLock<ATL::CComCriticalSection>(ATL::CComCriticalSection &,bool)
0x180047bc6  nop
0x180047bc7  mov     cs:qword_18022B838, r14
0x180047bce  mov     ebx, 1
0x180047bd3  mov     cs:dword_18022B914, ebx
0x180047bd9  mov     cs:dword_18022B910, ebx
0x180047bdf  mov     [rsp+338h+var_2A8], r14
0x180047be7  call    IsGetProcessUIContextInformationPresent
0x180047bec  test    eax, eax
0x180047bee  jnz     loc_180048038
0x180047bf4  mov     cs:byte_18022B848, r14b
0x180047bfb  mov     ecx, r15d; unsigned int
0x180047bfe  call    ?FactoryFlagsFromCreateDeviceFlags@@YAII@Z; FactoryFlagsFromCreateDeviceFlags(uint)
0x180047c03  mov     [rsp+338h+var_1E8], eax
0x180047c0a  mov     [rsp+338h+var_1E0], r14
0x180047c12  lea     rdx, unk_18022B918; struct FailureData::AdapterFailureData *
0x180047c19  lea     rcx, [rsp+338h+var_1D8]; this
0x180047c21  call    ??0CAdapterCache@CCreateDeviceCache@@QEAA@AEAUAdapterFailureData@FailureData@@@Z; CCreateDeviceCache::CAdapterCache::CAdapterCache(FailureData::AdapterFailureData &)
0x180047c26  lea     rdx, unk_18022B978; struct FailureData::AdapterFailureData *
0x180047c2d  lea     rcx, [rsp+338h+var_110]; this
0x180047c35  call    ??0CAdapterCache@CCreateDeviceCache@@QEAA@AEAUAdapterFailureData@FailureData@@@Z; CCreateDeviceCache::CAdapterCache::CAdapterCache(FailureData::AdapterFailureData &)
0x180047c3a  nop
0x180047c3b  lea     rcx, [rsp+338h+var_2D8]; void *
0x180047c40  call    ??0?$vector@PEAVCCommandList@@V?$allocator@PEAVCCommandList@@@std@@@std@@QEAA@XZ; std::vector<CCommandList *>::vector<CCommandList *>(void)
0x180047c45  nop
0x180047c46  mov     r8d, r12d
0x180047c49  mov     rdx, r13
0x180047c4c  lea     rcx, [rsp+338h+var_1E8]
0x180047c54  call    ?GetCreateDeviceProperties@@YA?AUCreateDeviceProperties@@PEAVCCreateDeviceCache@@PEAUIUnknown@@W4D3D_DRIVER_TYPE@@@Z; GetCreateDeviceProperties(CCreateDeviceCache *,IUnknown *,D3D_DRIVER_TYPE)
0x180047c59  movzx   esi, ax
0x180047c5c  call    ?EnableFeatureLevelUpgrade@@YAHXZ; EnableFeatureLevelUpgrade(void)
0x180047c61  test    eax, eax
0x180047c63  jnz     loc_1800480E4
0x180047c69  mov     r9d, [rsp+338h+var_2F0]
0x180047c6e  mov     r8, [rsp+338h+var_2E0]
0x180047c73  mov     rdx, [rsp+338h+var_2D8]
0x180047c78  lea     rcx, [rsp+338h+var_2D8]
0x180047c7d  call    ??$_Insert_counted_range@PEBW4D3D_FEATURE_LEVEL@@@?$vector@W4D3D_FEATURE_LEVEL@@V?$allocator@W4D3D_FEATURE_LEVEL@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@W4D3D_FEATURE_LEVEL@@@std@@@std@@@1@PEBW4D3D_FEATURE_LEVEL@@_K@Z; std::vector<D3D_FEATURE_LEVEL>::_Insert_counted_range<D3D_FEATURE_LEVEL const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<D3D_FEATURE_LEVEL>>>,D3D_FEATURE_LEVEL const *,unsigned __int64)
0x180047c82  lea     rdx, [rsp+338h+var_2D8]
0x180047c87  lea     rcx, unk_18022B9F0
0x180047c8e  call    ??4?$vector@W4D3D_FEATURE_LEVEL@@V?$allocator@W4D3D_FEATURE_LEVEL@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<D3D_FEATURE_LEVEL>::operator=(std::vector<D3D_FEATURE_LEVEL> const &)
0x180047c93  mov     rax, cs:Src
0x180047c9a  cmp     rax, cs:qword_18022B9E0
0x180047ca1  jnz     loc_180048203
0x180047ca7  mov     [rsp+338h+var_2A0], r14
0x180047caf  lea     r9, Context; Context
0x180047cb6  xor     r8d, r8d; Parameter
0x180047cb9  lea     rdx, ?InitOnceGetProcAddress@CModule@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180047cc0  lea     rcx, InitOnce; InitOnce
0x180047cc7  call    cs:__imp_InitOnceExecuteOnce
0x180047ccd  test    eax, eax
0x180047ccf  jz      loc_180048030
0x180047cd5  mov     rax, cs:Context
0x180047cdc  cmp     [rax], r14
0x180047cdf  jz      loc_180048030
0x180047ce5  lea     rdx, [rsp+338h+var_2A0]
0x180047ced  lea     rcx, aEnablefl9over1; "EnableFL9Over11"
0x180047cf4  mov     rax, [rax]
0x180047cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047cfc  mov     r13b, bl
0x180047cff  test    eax, eax
0x180047d01  jnz     loc_1800483D3
0x180047d07  mov     [rsp+338h+var_280], r14
0x180047d0f  lea     rcx, [rsp+338h+var_260]; void *
0x180047d17  call    ??0?$vector@PEAVCCommandList@@V?$allocator@PEAVCCommandList@@@std@@@std@@QEAA@XZ; std::vector<CCommandList *>::vector<CCommandList *>(void)
0x180047d1c  nop
0x180047d1d  mov     [rsp+338h+var_2B8], 8
0x180047d29  mov     rax, [rsp+338h+var_250]
0x180047d31  sub     rax, qword ptr [rsp+338h+var_260]
0x180047d39  sar     rax, 3
0x180047d3d  cmp     rax, 8
0x180047d41  jnb     short loc_180047D58
0x180047d43  lea     rdx, [rsp+338h+var_2B8]
0x180047d4b  lea     rcx, [rsp+338h+var_260]
0x180047d53  call    ??$_Reallocate@$0A@@?$vector@PEAVCCommandList@@V?$allocator@PEAVCCommandList@@@std@@@std@@AEAAXAEA_K@Z; std::vector<CCommandList *>::_Reallocate<0>(unsigned __int64 &)
0x180047d58  movzx   edx, si
0x180047d5b  shr     dx, 8
0x180047d5f  mov     [rsp+338h+var_2EC], dx
0x180047d64  mov     rdi, r14
0x180047d67  mov     [rsp+338h+var_290], r14
0x180047d6f  mov     rbx, [rsp+338h+var_2D8]
0x180047d74  mov     r15d, 887A0004h
0x180047d7a  cmp     rbx, [rsp+338h+var_2D0]
0x180047d7f  jz      loc_180047EFF
0x180047d85  mov     eax, r15d
0x180047d88  mov     [rsp+338h+var_298], r14
0x180047d90  mov     [rsp+338h+var_2F8], 100h
0x180047d97  lea     rcx, [rsp+338h+var_2F6]
0x180047d9c  mov     [rsp+338h+var_2B8], rcx
0x180047da4  lea     r12, [rsp+338h+var_2F8]
0x180047da9  cmp     dword ptr [rbx], 0A000h
0x180047daf  jl      loc_1800483E4
0x180047db5  mov     edx, 1
0x180047dba  test    eax, eax
0x180047dbc  js      loc_180047E80
0x180047dc2  movzx   r12d, r14b
0x180047dc6  mov     eax, [rsp+338h+var_2E8]
0x180047dca  test    eax, eax
0x180047dcc  jnz     loc_18004820F
0x180047dd2  mov     rcx, [rsp+338h+var_288]
0x180047dda  test    rcx, rcx
0x180047ddd  jz      short loc_180047E23
0x180047ddf  mov     qword ptr [rsp+338h+var_2E8], r14
0x180047de4  mov     rax, [rcx]
0x180047de7  lea     r8, [rsp+338h+var_2E8]
0x180047dec  lea     rdx, _GUID_2411e7e1_12ac_4ccf_bd14_9798e8534dc0
0x180047df3  mov     rax, [rax]
0x180047df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047dfb  test    eax, eax
0x180047dfd  js      short loc_180047E0C
0x180047dff  mov     rcx, qword ptr [rsp+338h+var_2E8]; struct IDXGIAdapter *
0x180047e04  call    ?IsExplicitWarpDriver@@YA_NPEAUIDXGIAdapter@@@Z; IsExplicitWarpDriver(IDXGIAdapter *)
0x180047e09  mov     r12b, al
0x180047e0c  mov     rcx, qword ptr [rsp+338h+var_2E8]
0x180047e11  test    rcx, rcx
0x180047e14  jz      short loc_180047E23
0x180047e16  mov     rax, [rcx]
0x180047e19  mov     rax, [rax+10h]
0x180047e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047e22  nop
0x180047e23  movzx   eax, sil
0x180047e27  mov     [rsp+338h+var_318], eax; int
0x180047e2b  mov     r9b, r12b; bool
0x180047e2e  mov     r8d, [rbx]; enum D3D_FEATURE_LEVEL
0x180047e31  mov     edx, [rsp+338h+var_2F0]; unsigned int
0x180047e35  mov     rcx, [rsp+338h+var_2E0]; enum D3D_FEATURE_LEVEL *
0x180047e3a  call    ?InferAPIFeatureLevel@@YA?AW4D3D_FEATURE_LEVEL@@PEBW41@IW41@_NH@Z; InferAPIFeatureLevel(D3D_FEATURE_LEVEL const *,uint,D3D_FEATURE_LEVEL,bool,int)
0x180047e3f  mov     esi, eax
0x180047e41  test    eax, eax
0x180047e43  jnz     loc_18004821B
0x180047e49  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180047e50  mov     [rsp+338h+pExceptionObject], rax
0x180047e58  mov     [rsp+338h+var_208], r15d
0x180047e60  xorps   xmm0, xmm0
0x180047e63  movdqu  [rsp+338h+var_200], xmm0
0x180047e6c  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180047e73  lea     rcx, [rsp+338h+pExceptionObject]; pExceptionObject
0x180047e7b  call    _CxxThrowException_0
0x180047e80  cmp     r12, rcx
0x180047e83  jz      loc_18004828E
0x180047e89  mov     dil, [r12]
0x180047e8d  lea     rax, [rsp+338h+var_298]
0x180047e95  mov     [rsp+338h+var_300], rax; struct CCreateDeviceCache::CAdapterCache **
0x180047e9a  mov     byte ptr [rsp+338h+var_308], dil; bool
0x180047e9f  lea     rax, [rsp+338h+var_290]
0x180047ea7  mov     [rsp+338h+var_310], rax; struct UniqueHMODULE *
0x180047eac  mov     eax, [rbx]
0x180047eae  mov     [rsp+338h+var_318], eax; enum D3D_FEATURE_LEVEL
0x180047eb2  mov     r9, [rsp+338h+var_238]; HINSTANCE
0x180047eba  mov     r8d, [rsp+338h+var_2E8]; enum D3D_DRIVER_TYPE
0x180047ebf  mov     rdx, [rsp+338h+var_288]; struct IUnknown *
0x180047ec7  lea     rcx, [rsp+338h+var_1E8]; this
0x180047ecf  call    ?SelectAdapter@CCreateDeviceCache@@QEAAJPEAUIUnknown@@W4D3D_DRIVER_TYPE@@PEAUHINSTANCE__@@W4D3D_FEATURE_LEVEL@@AEAVUniqueHMODULE@@_NPEAPEAVCAdapterCache@1@@Z; CCreateDeviceCache::SelectAdapter(IUnknown *,D3D_DRIVER_TYPE,HINSTANCE__ *,D3D_FEATURE_LEVEL,UniqueHMODULE &,bool,CCreateDeviceCache::CAdapterCache * *)
0x180047ed4  test    eax, eax
0x180047ed6  jns     loc_18004806F
0x180047edc  mov     edx, 1
0x180047ee1  add     r12, rdx
0x180047ee4  mov     rdi, [rsp+338h+var_290]
0x180047eec  mov     rcx, [rsp+338h+var_2B8]
0x180047ef4  jmp     loc_180047DBA
0x180047ef9  mov     r15d, 887A0005h
0x180047eff  mov     byte ptr [rsp+338h+var_318], 1; bool
0x180047f04  lea     r8, aFailedToFindDd; "Failed to find DDI to drive requested f"...
0x180047f0b  mov     edx, r15d; unsigned int
0x180047f0e  lea     rcx, ?g_Module@@3VCModule@@A; this
0x180047f15  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x180047f1a  mov     rbx, [rsp+338h+var_2C0]
0x180047f1f  test    rdi, rdi
0x180047f22  jz      short loc_180047F2E
0x180047f24  mov     rcx, rdi; hLibModule
0x180047f27  call    cs:__imp_FreeLibrary
0x180047f2d  nop
0x180047f2e  mov     rcx, qword ptr [rsp+338h+var_260]
0x180047f36  test    rcx, rcx
0x180047f39  jz      short loc_180047F63
0x180047f3b  mov     rdx, [rsp+338h+var_250]
0x180047f43  sub     rdx, rcx
0x180047f46  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180047f4a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180047f4f  xorps   xmm0, xmm0
0x180047f52  movdqu  [rsp+338h+var_260], xmm0
0x180047f5b  mov     [rsp+338h+var_250], r14
0x180047f63  mov     rcx, [rsp+338h+var_2D8]
0x180047f68  test    rcx, rcx
0x180047f6b  jz      short loc_180047F7F
0x180047f6d  mov     rdx, [rsp+338h+var_2C8]
0x180047f72  sub     rdx, rcx
0x180047f75  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180047f79  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180047f7e  nop
0x180047f7f  mov     rdi, [rsp+338h+var_278]
0x180047f87  mov     rcx, cs:qword_18022B838; this
0x180047f8e  test    rcx, rcx
0x180047f91  jz      short loc_180047F98
0x180047f93  call    ??_GCUMDAdapter@NDXGI@@QEAAPEAXI@Z; NDXGI::CUMDAdapter::`scalar deleting destructor'(uint)
0x180047f98  mov     cs:qword_18022B838, r14
0x180047f9f  mov     rax, qword ptr cs:?g_D3D11RegisteredLayers@@3V?$vector@UTD3D11LayerRegistration@@V?$allocator@UTD3D11LayerRegistration@@@std@@@std@@A; std::vector<TD3D11LayerRegistration> g_D3D11RegisteredLayers
0x180047fa6  cmp     rax, qword ptr cs:?g_D3D11RegisteredLayers@@3V?$vector@UTD3D11LayerRegistration@@V?$allocator@UTD3D11LayerRegistration@@@std@@@std@@A+8; std::vector<TD3D11LayerRegistration> g_D3D11RegisteredLayers
0x180047fad  jnz     loc_1800484A6
0x180047fb3  test    r15d, r15d
0x180047fb6  js      loc_1800482A7
0x180047fbc  lea     rcx, [rsp+338h+var_110]; this
0x180047fc4  call    ??1CAdapterCache@CCreateDeviceCache@@QEAA@XZ; CCreateDeviceCache::CAdapterCache::~CAdapterCache(void)
0x180047fc9  lea     rcx, [rsp+338h+var_1D8]; this
0x180047fd1  call    ??1CAdapterCache@CCreateDeviceCache@@QEAA@XZ; CCreateDeviceCache::CAdapterCache::~CAdapterCache(void)
0x180047fd6  lea     rcx, [rsp+338h+var_1E0]
0x180047fde  call    ??1?$CComPtrBase@UIDXGIFactory4@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(void)
0x180047fe3  nop
0x180047fe4  cmp     [rsp+338h+var_220], r14b
0x180047fec  jz      short loc_180047FFD
0x180047fee  mov     rcx, [rsp+338h+lpCriticalSection]; lpCriticalSection
0x180047ff6  call    cs:__imp_LeaveCriticalSection
0x180047ffc  nop
0x180047ffd  lea     rcx, [rsp+338h+var_230]; this
0x180048005  call    ??1CETWEventPair@@QEAA@XZ; CETWEventPair::~CETWEventPair(void)
0x18004800a  mov     eax, r15d
0x18004800d  mov     rcx, [rsp+338h+var_48]
0x180048015  xor     rcx, rsp; StackCookie
0x180048018  call    __security_check_cookie
0x18004801d  add     rsp, 300h
0x180048024  pop     r15
0x180048026  pop     r14
0x180048028  pop     r13
0x18004802a  pop     r12
0x18004802c  pop     rdi
0x18004802d  pop     rsi
0x18004802e  pop     rbx
0x18004802f  retn
0x180048030  mov     r13b, bl
0x180048033  jmp     loc_180047D07
0x180048038  call    cs:__imp_GetCurrentProcess
0x18004803e  mov     rcx, rax
0x180048041  lea     rdx, [rsp+338h+var_2A8]
0x180048049  call    cs:__imp_GetProcessUIContextInformation
0x18004804f  test    eax, eax
0x180048051  jz      loc_180047BF4
  ... truncated ...
```
