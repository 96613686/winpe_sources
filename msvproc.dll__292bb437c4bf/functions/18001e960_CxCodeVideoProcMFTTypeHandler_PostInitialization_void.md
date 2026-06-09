# CxCodeVideoProcMFTTypeHandler::PostInitialization(void)

- ea: `0x18001e960`
- end: `0x18001f0c3`
- name: `?PostInitialization@CxCodeVideoProcMFTTypeHandler@@IEAAJXZ`
- size: `1891`
- prototype: `__int64 __fastcall(CxCodeVideoProcMFTTypeHandler *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e6d0`
- `0x18001e920`

## callees

- `0x180009fbc`
- `0x18000c9d0`
- `0x18000ecf0`
- `0x18001d8b0`
- `0x18001e960`
- `0x180024370`
- `0x180036268`
- `0x18003639c`
- `0x180054140`
- `0x18005b5f8`
- `0x180063bd8`
- `0x1800662b0`
- `0x1800c8484`
- `0x1800cfec0`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ebe8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ebe8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eb7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001eca7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001eca7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001eb6c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001eb6c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ecc4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ecc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001eb08`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eac7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001eac7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001eaf8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001eaf8`
- `MFPlat!MFCreateMediaType` at `0x18001ef57`
- `MFPlat!MFCreateMediaType` at `0x18001ef57`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001eb92`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001eb92`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcMFTTypeHandler::PostInitialization(CxCodeVideoProcMFTTypeHandler *this)
{
  int v2; // esi
  __int64 v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  DWORD v6; // ecx
  unsigned int VideoProcessingAlgorithm; // eax
  bool v8; // cl
  int v9; // ebx
  int v10; // r14d
  CallStackTracing *v11; // rbx
  char *v12; // rdi
  DWORD LastError; // r12d
  char *Value; // rax
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  __int64 v17; // rax
  int v18; // ebx
  __int128 v19; // xmm0
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  int ActivationFactory; // eax
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 *v28; // rbx
  _QWORD *v29; // rsi
  unsigned __int64 v30; // r14
  unsigned __int64 v31; // rdi
  __int64 v32; // rdi
  __int64 v33; // r8
  __int64 v34; // rcx
  __int128 v35; // xmm0
  __int64 v36; // rax
  unsigned int i; // r14d
  _QWORD *v38; // rax
  __int64 v39; // rcx
  unsigned int v40; // edi
  __int64 v41; // rcx
  unsigned int v42; // edi
  int v43; // eax
  __int64 v44; // rcx
  HRESULT v45; // eax
  int v46; // eax
  int v47; // eax
  unsigned int v48; // r9d
  __int64 v49; // rcx
  struct IMFAttributes *v50; // rcx
  DWORD cbData; // [rsp+30h] [rbp-39h] BYREF
  BYTE v53[4]; // [rsp+34h] [rbp-35h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-31h] BYREF
  struct IMFAttributes *v55; // [rsp+40h] [rbp-29h] BYREF
  DWORD Type[4]; // [rsp+48h] [rbp-21h] BYREF
  HSTRING_HEADER hKey; // [rsp+58h] [rbp-11h] BYREF
  HSTRING string; // [rsp+70h] [rbp+7h] BYREF

  v2 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 45) + 20LL) )
    return (unsigned int)v2;
  v3 = *((_QWORD *)this + 1);
  v55 = 0;
  if ( v3 && (*(int (__fastcall **)(__int64, struct IMFAttributes **))(*(_QWORD *)v3 + 64LL))(v3, &v55) >= 0 )
  {
    v4 = *((_QWORD *)this + 45);
    cbData = 0;
    *(_DWORD *)Data = *(_DWORD *)(v4 + 16) != 0;
    v5 = ((__int64 (__fastcall *)(struct IMFAttributes *, __int64 *, DWORD *))v55->lpVtbl->GetUINT32)(
           v55,
           MF_LOW_LATENCY,
           &cbData);
    v6 = 0;
    if ( v5 >= 0 )
      v6 = cbData;
    **((_DWORD **)this + 45) = v6;
    ((void (__fastcall *)(struct IMFAttributes *, __int64 *, BYTE *))v55->lpVtbl->GetUINT32)(v55, qword_1800DF0A8, Data);
    *(_DWORD *)(*((_QWORD *)this + 45) + 16LL) = *(_DWORD *)Data != 0;
    VideoProcessingAlgorithm = GetVideoProcessingAlgorithm(v55);
    cbData = 0;
    *(_DWORD *)(*((_QWORD *)this + 45) + 12LL) = VideoProcessingAlgorithm;
    v8 = ((int (__fastcall *)(struct IMFAttributes *, __int64 *, DWORD *))v55->lpVtbl->GetUINT32)(
           v55,
           qword_1800DF078,
           &cbData) < 0
      || cbData;
    *(_BYTE *)(*((_QWORD *)this + 45) + 28LL) = v8;
  }
  CxCodeVideoProcMFTTypeHandler::GetDebugMode(this);
  *(_DWORD *)Data = 0;
  Type[0] = 0;
  hKey.Reserved.Reserved1 = 0;
  cbData = 4;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows Media Foundation\\Platform\\XVP",
         0,
         0x20019u,
         (PHKEY)&hKey) )
  {
    goto LABEL_15;
  }
  v9 = 0;
  if ( !RegQueryValueExW((HKEY)hKey.Reserved.Reserved1, L"disableRendererEffects", 0, Type, Data, &cbData) )
    v9 = *(_DWORD *)Data;
  RegCloseKey((HKEY)hKey.Reserved.Reserved1);
  v10 = 0;
  if ( !v9 )
LABEL_15:
    v10 = 1;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v53,
    "CxCodeVideoProcMFTTypeHandler::PostInitialization",
    7973);
  v11 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 48) )
  {
    v12 = (char *)CallStackTracing::s_wpInstance + 208;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      LastError = GetLastError();
      Value = (char *)TlsGetValue(*((_DWORD *)v11 + 3));
      if ( Value )
      {
        v12 = Value;
      }
      else if ( !GetLastError() )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        v17 = (*(__int64 (__fastcall **)(__int64 *))*v15)(v15);
        if ( v17 )
          v12 = (char *)v17;
      }
      SetLastError(LastError);
    }
    v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 296LL))(*((_QWORD *)this + 48));
    v19 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, HSTRING_HEADER *))(**((_QWORD **)this + 48) + 280LL))(
                       *((_QWORD *)this + 48),
                       &hKey);
    *((_DWORD *)v12 + 504) = v18;
    *((_OWORD *)v12 + 125) = v19;
  }
  if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
    WPP_SF_qdd(
      *((_QWORD *)WPP_GLOBAL_Control + 42),
      381,
      &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids,
      this,
      *(_DWORD *)(*((_QWORD *)this + 45) + 24LL),
      v10);
  if ( v10 && *(_DWORD *)(*((_QWORD *)this + 45) + 4LL) )
  {
    cbData = 0;
    *(_QWORD *)Type = 0;
    string = 0;
    v20 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &hKey, &string);
    if ( v20 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
      JUMPOUT(0x18001F0C2LL);
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, Type);
    v24 = *(__int64 **)Type;
    v2 = ActivationFactory;
    if ( ActivationFactory < 0 )
      goto LABEL_37;
    *(_QWORD *)Data = 0;
    v2 =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{232,{flat}}(*(_QWORD *)Type, Data);
    if ( v2 < 0 )
    {
      v26 = *(_QWORD *)Data;
      if ( *(_QWORD *)Data )
      {
        *(_QWORD *)Data = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      v24 = *(__int64 **)Type;
LABEL_37:
      if ( !v24 )
        goto LABEL_87;
      *(_QWORD *)Type = 0;
      v25 = *v24;
      goto LABEL_86;
    }
    v27 = *(_QWORD *)Type;
    v28 = *(__int64 **)Data;
    *(_QWORD *)Data = 0;
    if ( *(_QWORD *)Type )
    {
      *(_QWORD *)Type = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v2 = AvaliableInputTypesWithExtension(v28);
    if ( v2 )
    {
      if ( v28 )
        (*(void (__fastcall **)(__int64 *))(*v28 + 16))(v28);
      goto LABEL_87;
    }
    v2 = (*(__int64 (__fastcall **)(__int64 *, DWORD *))(*v28 + 56))(v28, &cbData);
    if ( v2 || !cbData )
    {
LABEL_84:
      if ( !v28 )
        goto LABEL_87;
      v25 = *v28;
      v24 = v28;
LABEL_86:
      (*(void (__fastcall **)(__int64 *))(v25 + 16))(v24);
LABEL_87:
      if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 42), 382, &WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids, this, v2);
      goto LABEL_89;
    }
    v29 = (_QWORD *)*((_QWORD *)this + 2);
    *(_OWORD *)&hKey.Reserved.Reserved1 = 0u;
    v30 = (__int64)(v29[1] - *v29) >> 4;
    v31 = (unsigned int)v30 + cbData;
    if ( v31 > v30 )
    {
      if ( !(unsigned __int8)utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::reserve(
                               v29,
                               (unsigned int)v30 + cbData) )
        goto LABEL_58;
      v33 = v29[1];
      v34 = 0;
      if ( v31 != v30 )
      {
        v35 = *(_OWORD *)&hKey.Reserved.Reserved1;
        do
        {
          v36 = v34++;
          *(_OWORD *)(v33 + 16 * v36) = v35;
        }
        while ( v34 != v31 - v30 );
      }
      v32 = *v29 + 16 * v31;
    }
    else
    {
      v32 = *v29 + 16 * v31;
    }
    v29[1] = v32;
LABEL_58:
    for ( i = 0; i < 0x24; ++i )
    {
      v38 = (_QWORD *)*((_QWORD *)this + 2);
      *(_OWORD *)Type = 0;
      v39 = *(_QWORD *)(*v38 + 16LL * i);
      v2 = (*(__int64 (__fastcall **)(__int64, const GUID *, DWORD *))(*(_QWORD *)v39 + 80LL))(
             v39,
             &MF_MT_SUBTYPE,
             Type);
      if ( v2 )
        break;
      v40 = 0;
      if ( cbData )
      {
        while ( 1 )
        {
          *(_OWORD *)&hKey.Reserved.Reserved1 = 0;
          if ( (*(int (__fastcall **)(__int64 *, _QWORD, HSTRING_HEADER *))(*v28 + 48))(v28, v40, &hKey) >= 0
            && !memcmp_0(Type, &hKey, 0x10u) )
          {
            break;
          }
          if ( ++v40 >= cbData )
            goto LABEL_68;
        }
        v41 = *(_QWORD *)(**((_QWORD **)this + 2) + 16LL * i);
        v2 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v41 + 168LL))(
               v41,
               &XVP_RENDER_EXTENSION_TYPE,
               1);
        if ( !v2 )
        {
          v2 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v28 + 96))(v28, v40);
          if ( !v2 )
            v2 = (*(__int64 (__fastcall **)(__int64 *, DWORD *))(*v28 + 56))(v28, &cbData);
        }
      }
LABEL_68:
      ;
    }
    v42 = 0;
    if ( cbData )
    {
      while ( 1 )
      {
        *(_QWORD *)Type = 0;
        *(_OWORD *)&hKey.Reserved.Reserved1 = 0;
        v43 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HSTRING_HEADER *))(*v28 + 48))(v28, v42, &hKey);
        v44 = *(_QWORD *)Type;
        v2 = v43;
        if ( v43 )
          break;
        if ( *(_QWORD *)Type )
        {
          *(_QWORD *)Type = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        }
        v45 = MFCreateMediaType((IMFMediaType **)Type);
        v44 = *(_QWORD *)Type;
        v2 = v45;
        if ( v45 )
          break;
        v46 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, const GUID *))(**(_QWORD **)Type + 192LL))(
                *(_QWORD *)Type,
                &MF_MT_MAJOR_TYPE,
                &MFMediaType_Video);
        v44 = *(_QWORD *)Type;
        v2 = v46;
        if ( v46 )
          break;
        v47 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, HSTRING_HEADER *))(**(_QWORD **)Type + 192LL))(
                *(_QWORD *)Type,
                &MF_MT_SUBTYPE,
                &hKey);
        v44 = *(_QWORD *)Type;
        v2 = v47;
        if ( v47 )
          break;
        v2 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(**(_QWORD **)Type + 168LL))(
               *(_QWORD *)Type,
               &XVP_RENDER_EXTENSION_TYPE,
               1);
        if ( v2 )
        {
          v44 = *(_QWORD *)Type;
          break;
        }
        CMFTMultiStreamTypeHandler::SetAvailableInputType(this, v42 + 36, *(struct IMFMediaType **)Type, v48);
        v49 = *(_QWORD *)Type;
        if ( *(_QWORD *)Type )
        {
          *(_QWORD *)Type = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
        if ( ++v42 >= cbData )
          goto LABEL_84;
      }
      if ( v44 )
      {
        *(_QWORD *)Type = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      }
    }
    goto LABEL_84;
  }
LABEL_89:
  *(_DWORD *)(*((_QWORD *)this + 45) + 20LL) = 1;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v53);
  v50 = v55;
  if ( v55 )
  {
    v55 = 0;
    ((void (__fastcall *)(struct IMFAttributes *))v50->lpVtbl->Release)(v50);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001e960  push    rbp
0x18001e962  push    rbx
0x18001e963  push    rsi
0x18001e964  push    rdi
0x18001e965  push    r12
0x18001e967  push    r13
0x18001e969  push    r14
0x18001e96b  push    r15
0x18001e96d  lea     rbp, [rsp-1Fh]
0x18001e972  sub     rsp, 88h
0x18001e979  mov     rax, cs:__security_cookie
0x18001e980  xor     rax, rsp
0x18001e983  mov     [rbp+57h+var_48], rax
0x18001e987  mov     rax, [rcx+168h]
0x18001e98e  xor     r13d, r13d
0x18001e991  mov     r15, rcx
0x18001e994  mov     esi, r13d
0x18001e997  cmp     [rax+14h], r13d
0x18001e99b  jnz     loc_18001F099
0x18001e9a1  mov     rcx, [rcx+8]
0x18001e9a5  mov     [rbp+57h+var_80], r13
0x18001e9a9  test    rcx, rcx
0x18001e9ac  jz      loc_18001EA8C
0x18001e9b2  mov     rax, [rcx]
0x18001e9b5  lea     rdx, [rbp+57h+var_80]
0x18001e9b9  mov     rax, [rax+40h]
0x18001e9bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9c2  test    eax, eax
0x18001e9c4  js      loc_18001EA8C
0x18001e9ca  mov     rax, [r15+168h]
0x18001e9d1  lea     r8, [rbp+57h+cbData]
0x18001e9d5  mov     ecx, r13d
0x18001e9d8  mov     [rbp+57h+cbData], r13d
0x18001e9dc  lea     rdx, MF_LOW_LATENCY
0x18001e9e3  cmp     [rax+10h], r13d
0x18001e9e7  setnz   cl
0x18001e9ea  mov     dword ptr [rbp+57h+Data], ecx
0x18001e9ed  mov     rcx, [rbp+57h+var_80]
0x18001e9f1  mov     rax, [rcx]
0x18001e9f4  mov     rax, [rax+38h]
0x18001e9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9fd  mov     ecx, r13d
0x18001ea00  test    eax, eax
0x18001ea02  js      short loc_18001EA07
0x18001ea04  mov     ecx, [rbp+57h+cbData]
0x18001ea07  mov     rax, [r15+168h]
0x18001ea0e  lea     r8, [rbp+57h+Data]
0x18001ea12  lea     rdx, qword_1800DF0A8
0x18001ea19  mov     [rax], ecx
0x18001ea1b  mov     rcx, [rbp+57h+var_80]
0x18001ea1f  mov     rax, [rcx]
0x18001ea22  mov     rax, [rax+38h]
0x18001ea26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea2b  cmp     dword ptr [rbp+57h+Data], r13d
0x18001ea2f  mov     ecx, r13d
0x18001ea32  mov     rax, [r15+168h]
0x18001ea39  setnbe  cl
0x18001ea3c  mov     [rax+10h], ecx
0x18001ea3f  mov     rcx, [rbp+57h+var_80]; struct IMFAttributes *
0x18001ea43  call    ?GetVideoProcessingAlgorithm@@YAIPEAUIMFAttributes@@@Z; GetVideoProcessingAlgorithm(IMFAttributes *)
0x18001ea48  mov     ecx, eax
0x18001ea4a  mov     [rbp+57h+cbData], r13d
0x18001ea4e  mov     rax, [r15+168h]
0x18001ea55  lea     r8, [rbp+57h+cbData]
0x18001ea59  lea     rdx, qword_1800DF078
0x18001ea60  mov     [rax+0Ch], ecx
0x18001ea63  mov     rcx, [rbp+57h+var_80]
0x18001ea67  mov     rax, [rcx]
0x18001ea6a  mov     rax, [rax+38h]
0x18001ea6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea73  test    eax, eax
0x18001ea75  js      short loc_18001EA80
0x18001ea77  cmp     [rbp+57h+cbData], esi
0x18001ea7a  jnz     short loc_18001EA80
0x18001ea7c  xor     ecx, ecx
0x18001ea7e  jmp     short loc_18001EA82
0x18001ea80  mov     cl, 1
0x18001ea82  mov     rax, [r15+168h]
0x18001ea89  mov     [rax+1Ch], cl
0x18001ea8c  mov     rcx, r15; this
0x18001ea8f  call    ?GetDebugMode@CxCodeVideoProcMFTTypeHandler@@IEAAXXZ; CxCodeVideoProcMFTTypeHandler::GetDebugMode(void)
0x18001ea94  lea     rax, [rbp+57h+hKey]
0x18001ea98  mov     dword ptr [rbp+57h+Data], r13d
0x18001ea9c  mov     r9d, 20019h; samDesired
0x18001eaa2  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18001eaa7  xor     r8d, r8d; ulOptions
0x18001eaaa  mov     [rbp+57h+Type], r13d
0x18001eaae  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows Media Foun"...
0x18001eab5  mov     qword ptr [rbp+57h+hKey], r13
0x18001eab9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001eac0  mov     [rbp+57h+cbData], 4
0x18001eac7  call    cs:__imp_RegOpenKeyExW
0x18001eacd  test    eax, eax
0x18001eacf  jnz     short loc_18001EB15
0x18001ead1  mov     rcx, qword ptr [rbp+57h+hKey]; hKey
0x18001ead5  lea     rax, [rbp+57h+cbData]
0x18001ead9  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18001eade  lea     r9, [rbp+57h+Type]; lpType
0x18001eae2  lea     rax, [rbp+57h+Data]
0x18001eae6  xor     r8d, r8d; lpReserved
0x18001eae9  lea     rdx, aDisablerendere; "disableRendererEffects"
0x18001eaf0  mov     [rsp+0C0h+phkResult], rax; lpData
0x18001eaf5  mov     ebx, r13d
0x18001eaf8  call    cs:__imp_RegQueryValueExW
0x18001eafe  mov     rcx, qword ptr [rbp+57h+hKey]; hKey
0x18001eb02  test    eax, eax
0x18001eb04  cmovz   ebx, dword ptr [rbp+57h+Data]
0x18001eb08  call    cs:__imp_RegCloseKey
0x18001eb0e  mov     r14d, r13d
0x18001eb11  test    ebx, ebx
0x18001eb13  jnz     short loc_18001EB1B
0x18001eb15  mov     r14d, 1
0x18001eb1b  mov     r8d, 1F25h; int
0x18001eb21  lea     rdx, aCxcodevideopro_126; "CxCodeVideoProcMFTTypeHandler::PostInit"...
0x18001eb28  lea     rcx, [rbp+57h+var_8C]; this
0x18001eb2c  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001eb31  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001eb38  cmp     [rbx+8], sil
0x18001eb3c  jz      loc_18001EC30
0x18001eb42  cmp     [r15+180h], rsi
0x18001eb49  jz      loc_18001EC30
0x18001eb4f  lea     rdi, [rbx+0D0h]
0x18001eb56  cmp     [rbx+8], sil
0x18001eb5a  jz      loc_18001EBEE
0x18001eb60  call    cs:__imp_GetLastError
0x18001eb66  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001eb69  mov     r12d, eax
0x18001eb6c  call    cs:__imp_TlsGetValue
0x18001eb72  test    rax, rax
0x18001eb75  jz      short loc_18001EB7C
0x18001eb77  mov     rdi, rax
0x18001eb7a  jmp     short loc_18001EBE5
0x18001eb7c  call    cs:__imp_GetLastError
0x18001eb82  test    eax, eax
0x18001eb84  jnz     short loc_18001EBE5
0x18001eb86  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001eb8d  test    rcx, rcx
0x18001eb90  jnz     short loc_18001EBD3
0x18001eb92  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001eb98  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001eb9f  mov     rcx, rax
0x18001eba2  test    rax, rax
0x18001eba5  jz      short loc_18001EBC5
0x18001eba7  mov     rax, [rax]
0x18001ebaa  mov     edx, 7F0h
0x18001ebaf  mov     rax, [rax+8]
0x18001ebb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebb8  test    eax, eax
0x18001ebba  jz      short loc_18001EBC5
0x18001ebbc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ebc3  jmp     short loc_18001EBD3
0x18001ebc5  lea     rcx, qword_180153440
0x18001ebcc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ebd3  mov     rax, [rcx]
0x18001ebd6  mov     rax, [rax]
0x18001ebd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebde  test    rax, rax
0x18001ebe1  cmovnz  rdi, rax
0x18001ebe5  mov     ecx, r12d; dwErrCode
0x18001ebe8  call    cs:__imp_SetLastError
0x18001ebee  mov     rcx, [r15+180h]
0x18001ebf5  mov     rax, [rcx]
0x18001ebf8  mov     rax, [rax+128h]
0x18001ebff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec04  mov     rcx, [r15+180h]
0x18001ec0b  lea     rdx, [rbp+57h+hKey]
0x18001ec0f  mov     ebx, eax
0x18001ec11  mov     rax, [rcx]
0x18001ec14  mov     rax, [rax+118h]
0x18001ec1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec20  movups  xmm0, xmmword ptr [rax]
0x18001ec23  mov     [rdi+7E0h], ebx
0x18001ec29  movups  xmmword ptr [rdi+7D0h], xmm0
0x18001ec30  cmp     cs:byte_180153DE0, 20h ; ' '
0x18001ec37  jb      short loc_18001EC6E
0x18001ec39  mov     rax, [r15+168h]
0x18001ec40  lea     r8, WPP_9573e9da59bf3a1b291a40830b73dec1_Traceguids
0x18001ec47  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec4e  mov     edx, 17Dh
0x18001ec53  mov     dword ptr [rsp+0C0h+lpcbData], r14d
0x18001ec58  mov     r9, r15
0x18001ec5b  mov     eax, [rax+18h]
0x18001ec5e  mov     rcx, [rcx+150h]
0x18001ec65  mov     dword ptr [rsp+0C0h+phkResult], eax
0x18001ec69  call    WPP_SF_qdd
0x18001ec6e  test    r14d, r14d
0x18001ec71  jz      loc_18001F069
0x18001ec77  mov     rax, [r15+168h]
0x18001ec7e  cmp     [rax+4], esi
0x18001ec81  jz      loc_18001F069
0x18001ec87  lea     r9, [rbp+57h+string]; string
0x18001ec8b  mov     [rbp+57h+cbData], r13d
0x18001ec8f  lea     r8, [rbp+57h+hKey]; hstringHeader
0x18001ec93  mov     qword ptr [rbp+57h+Type], r13
0x18001ec97  mov     edx, 2Ch ; ','; length
0x18001ec9c  mov     [rbp+57h+string], r13
0x18001eca0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18001eca7  call    cs:__imp_WindowsCreateStringReference
0x18001ecad  test    eax, eax
0x18001ecaf  js      loc_18001F0BB
0x18001ecb5  mov     rcx, [rbp+57h+string]
0x18001ecb9  lea     r8, [rbp+57h+Type]
0x18001ecbd  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18001ecc4  call    cs:__imp_RoGetActivationFactory
0x18001ecca  mov     rcx, qword ptr [rbp+57h+Type]
0x18001ecce  mov     esi, eax
0x18001ecd0  test    eax, eax
0x18001ecd2  jns     short loc_18001ECE9
0x18001ecd4  test    rcx, rcx
0x18001ecd7  jz      loc_18001F03A
0x18001ecdd  mov     qword ptr [rbp+57h+Type], r13
0x18001ece1  mov     rax, [rcx]
0x18001ece4  jmp     loc_18001F031
0x18001ece9  lea     rdx, [rbp+57h+Data]
0x18001eced  mov     qword ptr [rbp+57h+Data], r13
0x18001ecf1  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BOI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{232,{flat}}
0x18001ecf6  mov     esi, eax
0x18001ecf8  test    eax, eax
0x18001ecfa  jns     short loc_18001ED1B
0x18001ecfc  mov     rcx, qword ptr [rbp+57h+Data]
0x18001ed00  test    rcx, rcx
0x18001ed03  jz      short loc_18001ED15
0x18001ed05  mov     qword ptr [rbp+57h+Data], r13
0x18001ed09  mov     rax, [rcx]
0x18001ed0c  mov     rax, [rax+10h]
0x18001ed10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed15  mov     rcx, qword ptr [rbp+57h+Type]
0x18001ed19  jmp     short loc_18001ECD4
0x18001ed1b  mov     rcx, qword ptr [rbp+57h+Type]
0x18001ed1f  mov     rbx, qword ptr [rbp+57h+Data]
0x18001ed23  mov     qword ptr [rbp+57h+Data], r13
0x18001ed27  test    rcx, rcx
0x18001ed2a  jz      short loc_18001ED3C
0x18001ed2c  mov     qword ptr [rbp+57h+Type], r13
0x18001ed30  mov     rax, [rcx]
0x18001ed33  mov     rax, [rax+10h]
0x18001ed37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed3c  mov     rcx, rbx
0x18001ed3f  call    ?AvaliableInputTypesWithExtension@@YAJPEAU?$IVector@U_GUID@@@Collections@Foundation@Windows@@@Z; AvaliableInputTypesWithExtension(Windows::Foundation::Collections::IVector<_GUID> *)
0x18001ed44  mov     esi, eax
0x18001ed46  test    eax, eax
0x18001ed48  jz      short loc_18001ED62
0x18001ed4a  test    rbx, rbx
0x18001ed4d  jz      loc_18001F03A
0x18001ed53  mov     rcx, [rbx]
0x18001ed56  mov     rax, [rcx+10h]
0x18001ed5a  mov     rcx, rbx
0x18001ed5d  jmp     loc_18001F035
0x18001ed62  mov     rax, [rbx]
0x18001ed65  lea     rdx, [rbp+57h+cbData]
0x18001ed69  mov     rcx, rbx
0x18001ed6c  mov     rax, [rax+38h]
0x18001ed70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed75  mov     esi, eax
0x18001ed77  test    eax, eax
0x18001ed79  jnz     loc_18001F026
0x18001ed7f  mov     eax, [rbp+57h+cbData]
0x18001ed82  test    eax, eax
0x18001ed84  jz      loc_18001F026
0x18001ed8a  mov     rsi, [r15+10h]
0x18001ed8e  mov     qword ptr [rbp+57h+hKey], r13
0x18001ed92  mov     qword ptr [rbp+57h+hKey+8], r13
0x18001ed96  mov     rcx, [rsi]
0x18001ed99  mov     r14, [rsi+8]
0x18001ed9d  sub     r14, rcx
0x18001eda0  sar     r14, 4
0x18001eda4  lea     edi, [r14+rax]
0x18001eda8  cmp     rdi, r14
0x18001edab  ja      short loc_18001EDB6
0x18001edad  shl     rdi, 4
0x18001edb1  add     rdi, rcx
0x18001edb4  jmp     short loc_18001EDFA
0x18001edb6  mov     rdx, rdi
0x18001edb9  mov     rcx, rsi
0x18001edbc  call    ?reserve@?$vector@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@V?$allocator@U_MFTSB_TYPE_INFO@CMFTMultiStreamTypeHandler@@@utl@@@utl@@QEAA_N_K@Z; utl::vector<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO,utl::allocator<CMFTMultiStreamTypeHandler::_MFTSB_TYPE_INFO>>::reserve(unsigned __int64)
0x18001edc1  test    al, al
0x18001edc3  jz      short loc_18001EDFE
0x18001edc5  mov     r8, [rsi+8]
0x18001edc9  mov     rdx, rdi
0x18001edcc  mov     rcx, r13
0x18001edcf  sub     rdx, r14
0x18001edd2  jz      short loc_18001EDF3
0x18001edd4  movups  xmm0, xmmword ptr [rbp+57h+hKey]
0x18001edd8  nop     dword ptr [rax+rax+00000000h]
0x18001ede0  mov     rax, rcx
0x18001ede3  inc     rcx
0x18001ede6  add     rax, rax
0x18001ede9  movups  xmmword ptr [r8+rax*8], xmm0
0x18001edee  cmp     rcx, rdx
0x18001edf1  jnz     short loc_18001EDE0
0x18001edf3  shl     rdi, 4
0x18001edf7  add     rdi, [rsi]
0x18001edfa  mov     [rsi+8], rdi
0x18001edfe  mov     r14d, r13d
0x18001ee01  mov     rax, [r15+10h]
0x18001ee05  lea     r8, [rbp+57h+Type]
0x18001ee09  xorps   xmm0, xmm0
0x18001ee0c  mov     r12d, r14d
0x18001ee0f  movups  xmmword ptr [rbp+57h+Type], xmm0
0x18001ee13  add     r12, r12
  ... truncated ...
```
