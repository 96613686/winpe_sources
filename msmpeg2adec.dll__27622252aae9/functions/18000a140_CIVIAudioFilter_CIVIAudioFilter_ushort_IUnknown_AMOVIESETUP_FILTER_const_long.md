# CIVIAudioFilter::CIVIAudioFilter(ushort *,IUnknown *,_AMOVIESETUP_FILTER const *,long *)

- ea: `0x18000a140`
- end: `0x18000a73e`
- name: `??0CIVIAudioFilter@@QEAA@PEAGPEAUIUnknown@@PEBU_AMOVIESETUP_FILTER@@PEAJ@Z`
- size: `1534`
- prototype: `CIVIAudioFilter *__usercall@<rax>(CIVIAudioFilter *__hidden this@<rcx>, unsigned __int16 *@<rdx>, struct IUnknown *@<r8>, const struct _AMOVIESETUP_FILTER *@<r9>, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d2f0`

## callees

- `0x1800013a0`
- `0x1800013ac`
- `0x1800021a8`
- `0x18000a140`
- `0x1800108f0`
- `0x180013a40`
- `0x180017b20`
- `0x180017ba0`
- `0x18001c2f0`
- `0x1800205b0`
- `0x180024290`
- `0x180032f00`
- `0x18005a380`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000a5d2`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x18000a5d2`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18000a5e0`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18000a5e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a4d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a4f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a513`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a4d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a4f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a513`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a4af`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a4af`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a1bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a1d2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a32b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a38d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a434`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a44f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a1bf`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a1d2`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a32b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a38d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a434`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a44f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a3cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a3cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a39d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a39d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a6bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a6bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a6d5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a6d5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a67e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a67e`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a3b9`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000a3b9`

## string_xrefs

- `0x18000a4a8`: `avrt.dll`
- `0x18000a4c7`: `AvRevertMmThreadCharacteristics`
- `0x18000a4e4`: `AvSetMmThreadCharacteristicsW`
- `0x18000a505`: `AvSetMmThreadPriority`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
CIVIAudioFilter *__fastcall CIVIAudioFilter::CIVIAudioFilter(
        CIVIAudioFilter *this,
        unsigned __int16 *a2,
        struct IUnknown *a3,
        const struct _AMOVIESETUP_FILTER *a4,
        int *hKey)
{
  struct IUnknown *v6; // rax
  struct _RTL_CRITICAL_SECTION *v7; // rcx
  void **v8; // rbx
  __int64 v9; // rbp
  __int64 v10; // rcx
  const unsigned __int16 *v11; // rax
  __int64 v12; // rdx
  unsigned __int64 v13; // rsi
  unsigned __int16 *v14; // rax
  int *v15; // r14
  HMODULE Library; // rax
  int v17; // eax
  unsigned int v18; // eax
  int v19; // esi
  const WCHAR *v20; // rdx
  LSTATUS Value; // ebx
  int v22; // eax
  unsigned __int16 *Type; // [rsp+78h] [rbp+10h] BYREF
  int Data; // [rsp+80h] [rbp+18h] BYREF
  const struct _AMOVIESETUP_FILTER *cbData; // [rsp+88h] [rbp+20h] BYREF

  cbData = a4;
  Type = a2;
  _InterlockedIncrement(&CBaseObject::m_cObjects);
  v6 = (struct IUnknown *)this;
  if ( a3 )
    v6 = a3;
  *((_QWORD *)this + 1) = v6;
  *((_DWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((GUID *)this + 4) = CLSID_CMPEG2AudDecoderDS;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  *((_QWORD *)this + 10) = v7;
  v8 = (void **)((char *)this + 88);
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 1;
  *((_QWORD *)this + 15) = 0;
  *((_DWORD *)this + 32) = 0;
  InitializeCriticalSection(v7);
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 176));
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = 0;
  *(_QWORD *)this = &CNamedTransformFilter::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CNamedTransformFilter::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CNamedTransformFilter::`vftable'{for `IAMovieSetup'};
  v9 = -1;
  if ( this != (CIVIAudioFilter *)-88LL )
  {
    if ( *v8 )
    {
      operator delete(*v8);
      *v8 = 0;
    }
    v10 = 0x7FFFFFFF;
    v11 = L"Microsoft DTV-DVD Audio Decoder";
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v10;
    }
    while ( v10 );
    v12 = 0x7FFFFFFF - v10;
    if ( v10 )
    {
      v13 = v12 + 1;
      v14 = (unsigned __int16 *)operator new[](saturated_mul(v12 + 1, 2u));
      *v8 = v14;
      if ( v14 )
        StringCchCopyW(v14, v13, L"Microsoft DTV-DVD Audio Decoder");
    }
  }
  cbData = (CIVIAudioFilter *)((char *)this + 232);
  *((_QWORD *)this + 29) = &CIVIAudioCodec::`vftable';
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_OWORD *)this + 22) = 0;
  *((_OWORD *)this + 23) = 0;
  *((_OWORD *)this + 24) = 0;
  *((_OWORD *)this + 25) = 0;
  *((_OWORD *)this + 26) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_DWORD *)this + 98) = 1;
  *((_DWORD *)this + 96) = 1;
  *(_OWORD *)((char *)this + 440) = 0;
  *(_OWORD *)((char *)this + 456) = 0;
  *(_OWORD *)((char *)this + 472) = 0;
  *(_OWORD *)((char *)this + 488) = 0;
  *(_OWORD *)((char *)this + 504) = 0;
  *((_QWORD *)this + 65) = 0;
  *((_DWORD *)this + 120) = 1;
  *((_DWORD *)this + 118) = 1;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 536));
  *((_QWORD *)this + 72) = 0;
  *((_DWORD *)this + 1611) = 6;
  *((_QWORD *)this + 823) = 0;
  v15 = hKey;
  if ( hKey )
  {
    CIVIAudioCodec::Init((CIVIAudioFilter *)((char *)this + 232), hKey);
    if ( !g_Conv_float2short )
      g_Conv_float2short = (void (*)(float *, int))Conv_float2short_SSE2;
    if ( this != (CIVIAudioFilter *)-256LL )
    {
      InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
      *((_DWORD *)this + 64) = EventRegister(&Microsoft_Windows_MSMPEG2ADEC, 0, 0, (PREGHANDLE)this + 33);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
    }
  }
  *(_QWORD *)this = &CIVIAudioFilter::`vftable'{for `CUnknown'};
  *((_QWORD *)this + 3) = &CIVIAudioFilter::`vftable'{for `IBaseFilter'};
  *((_QWORD *)this + 4) = &CNamedTransformFilter::`vftable'{for `IAMovieSetup'};
  *((_QWORD *)this + 29) = &CIVIAudioFilter::`vftable'{for `CIVIAudioCodec'};
  *((_QWORD *)this + 1923) = &CIVIAudioFilter::`vftable'{for `ISpecifyPropertyPages'};
  *((_QWORD *)this + 1924) = &CIVIAudioFilter::`vftable'{for `ICodecAPI'};
  *((_QWORD *)this + 1925) = &CIVIAudioFilter::`vftable'{for `IPersistStream'};
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 15408));
  *((_QWORD *)this + 1932) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 387);
  AudioRateChange::Reset((CIVIAudioFilter *)((char *)this + 15472));
  *((_QWORD *)this + 2075) = 0;
  *((_QWORD *)this + 2076) = 0;
  *((_QWORD *)this + 2154) = 0;
  *((_DWORD *)this + 4310) = 0;
  *((_QWORD *)this + 2156) = 0;
  *((_QWORD *)this + 2157) = 0;
  *((_QWORD *)this + 2158) = 0;
  *((_QWORD *)this + 2159) = 0;
  Library = LoadLibraryExW(L"avrt.dll", 0, 0x800u);
  *((_QWORD *)this + 2156) = Library;
  if ( Library )
  {
    *((_QWORD *)this + 2158) = GetProcAddress(Library, "AvRevertMmThreadCharacteristics");
    *((_QWORD *)this + 2157) = GetProcAddress(*((HMODULE *)this + 2156), "AvSetMmThreadCharacteristicsW");
    *((_QWORD *)this + 2159) = GetProcAddress(*((HMODULE *)this + 2156), "AvSetMmThreadPriority");
  }
  *((_DWORD *)this + 4320) = 0;
  *(_QWORD *)((char *)this + 17796) = 0;
  *((_QWORD *)this + 2226) = 0;
  *((_QWORD *)this + 2227) = 0;
  *((_QWORD *)this + 2228) = 0;
  *((_QWORD *)this + 2229) = &off_18008B170;
  if ( v15 )
    *v15 = 0;
  memset_0((char *)this + 17284, 0, 0x200u);
  v17 = CIVIAudioFilter::Init(this);
  if ( v17 >= 0 )
  {
    StringCchPrintfW(
      (unsigned __int16 *)this + 8320,
      0x100u,
      L"MSDTVADEC:(FILTER: %.80s)",
      L"Microsoft DTV-DVD Audio Decoder");
    if ( !(unsigned int)WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt() )
    {
      DRM_Create((void **)this + 2148);
      WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt();
    }
    *((_DWORD *)this + 4306) = 0;
    v18 = _time64(0);
    _o_srand(v18);
    hKey = 0;
    LODWORD(Type) = 0;
    LODWORD(cbData) = 0;
    if ( !lpSubKey )
    {
      do
        ++v9;
      while ( *(&xmmword_1800ADB00 + v9) );
      if ( v9 || (int)UTIL_REGGetModuleBase() >= 0 )
        lpSubKey = &xmmword_1800ADB00;
    }
    LODWORD(cbData) = 8;
    v19 = 0;
    while ( 1 )
    {
      v20 = (const WCHAR *)qword_1800ADAF0;
      if ( v19 < 2 )
        v20 = lpSubKey;
      if ( v20 )
      {
        if ( !RegOpenKeyExW((HKEY)qword_180095458[v19], v20, 0, 0x20019u, (PHKEY)&hKey) )
        {
          Value = RegQueryValueExW((HKEY)hKey, L"dolby_time_shift", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData);
          RegCloseKey((HKEY)hKey);
          if ( !Value )
            break;
        }
      }
      if ( !qword_180095458[++v19] )
        goto LABEL_44;
    }
    v22 = Data;
    *((_DWORD *)this + 1633) = Data;
    if ( v22 )
    {
      if ( !((v22 & 1) != 0 ? (unsigned int)(v22 + 10000000) <= 0x1312D00 : (unsigned int)(v22 + 48000) <= 0x17700) )
LABEL_44:
        *((_DWORD *)this + 1633) = 0;
    }
  }
  else if ( v15 )
  {
    *v15 = v17;
  }
  return this;
}

```

## disassembly

```asm
0x18000a140  mov     [rsp+cbData], r9
0x18000a145  mov     [rsp+Type], rdx
0x18000a14a  mov     [rsp+arg_0], rcx
0x18000a14f  push    rbx
0x18000a150  push    rbp
0x18000a151  push    rsi
0x18000a152  push    rdi
0x18000a153  push    r12
0x18000a155  push    r14
0x18000a157  push    r15
0x18000a159  sub     rsp, 30h
0x18000a15d  mov     rdi, rcx
0x18000a160  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18000a167  mov     rax, rcx
0x18000a16a  test    r8, r8
0x18000a16d  cmovnz  rax, r8
0x18000a171  mov     [rcx+8], rax
0x18000a175  xor     r12d, r12d
0x18000a178  mov     [rcx+10h], r12d
0x18000a17c  mov     [rcx+28h], r12d
0x18000a180  mov     [rcx+30h], r12
0x18000a184  mov     [rcx+38h], r12
0x18000a188  movups  xmm0, xmmword ptr cs:CLSID_CMPEG2AudDecoderDS.Data1
0x18000a18f  movups  xmmword ptr [rcx+40h], xmm0
0x18000a193  add     rcx, 88h; lpCriticalSection
0x18000a19a  mov     [rdi+50h], rcx
0x18000a19e  lea     rbx, [rdi+58h]
0x18000a1a2  mov     [rbx], r12
0x18000a1a5  mov     [rdi+60h], r12
0x18000a1a9  mov     [rdi+68h], r12
0x18000a1ad  mov     dword ptr [rdi+70h], 1
0x18000a1b4  mov     [rdi+78h], r12
0x18000a1b8  mov     [rdi+80h], r12d
0x18000a1bf  call    cs:__imp_InitializeCriticalSection
0x18000a1c6  nop     dword ptr [rax+rax+00h]
0x18000a1cb  lea     rcx, [rdi+0B0h]; lpCriticalSection
0x18000a1d2  call    cs:__imp_InitializeCriticalSection
0x18000a1d9  nop     dword ptr [rax+rax+00h]
0x18000a1de  mov     [rdi+0D8h], r12
0x18000a1e5  mov     [rdi+0E0h], r12
0x18000a1ec  lea     rax, ??_7CNamedTransformFilter@@6BCUnknown@@@; const CNamedTransformFilter::`vftable'{for `CUnknown'}
0x18000a1f3  mov     [rdi], rax
0x18000a1f6  lea     rax, ??_7CNamedTransformFilter@@6BIBaseFilter@@@; const CNamedTransformFilter::`vftable'{for `IBaseFilter'}
0x18000a1fd  mov     [rdi+18h], rax
0x18000a201  lea     rax, ??_7CNamedTransformFilter@@6BIAMovieSetup@@@; const CNamedTransformFilter::`vftable'{for `IAMovieSetup'}
0x18000a208  mov     [rdi+20h], rax
0x18000a20c  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x18000a213  test    rbx, rbx
0x18000a216  jz      short loc_18000A285
0x18000a218  mov     rcx, [rbx]; Block
0x18000a21b  test    rcx, rcx
0x18000a21e  jz      short loc_18000A228
0x18000a220  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a225  mov     [rbx], r12
0x18000a228  mov     edx, 7FFFFFFFh
0x18000a22d  mov     ecx, edx
0x18000a22f  lea     rax, aMicrosoftDtvDv; "Microsoft DTV-DVD Audio Decoder"
0x18000a236  cmp     [rax], r12w
0x18000a23a  jz      short loc_18000A246
0x18000a23c  add     rax, 2
0x18000a240  sub     rcx, 1
0x18000a244  jnz     short loc_18000A236
0x18000a246  sub     rdx, rcx
0x18000a249  test    rcx, rcx
0x18000a24c  cmovz   rdx, r12
0x18000a250  jz      short loc_18000A285
0x18000a252  lea     rsi, [rdx+1]
0x18000a256  mov     eax, 2
0x18000a25b  mul     rsi
0x18000a25e  cmovb   rax, rbp
0x18000a262  mov     rcx, rax; unsigned __int64
0x18000a265  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000a26a  mov     [rbx], rax
0x18000a26d  test    rax, rax
0x18000a270  jz      short loc_18000A285
0x18000a272  lea     r8, aMicrosoftDtvDv; "Microsoft DTV-DVD Audio Decoder"
0x18000a279  mov     rdx, rsi; unsigned __int64
0x18000a27c  mov     rcx, rax; unsigned __int16 *
0x18000a27f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a284  nop
0x18000a285  lea     rsi, [rdi+0E8h]
0x18000a28c  mov     [rsp+68h+cbData], rsi
0x18000a294  lea     rax, ??_7CIVIAudioCodec@@6B@; const CIVIAudioCodec::`vftable'
0x18000a29b  mov     [rsi], rax
0x18000a29e  mov     [rsi+50h], r12
0x18000a2a2  mov     [rsi+70h], r12
0x18000a2a6  xorps   xmm0, xmm0
0x18000a2a9  xor     eax, eax
0x18000a2ab  movups  xmmword ptr [rsi+78h], xmm0
0x18000a2af  movups  xmmword ptr [rsi+88h], xmm0
0x18000a2b6  movups  xmmword ptr [rsi+98h], xmm0
0x18000a2bd  movups  xmmword ptr [rsi+0A8h], xmm0
0x18000a2c4  movups  xmmword ptr [rsi+0B8h], xmm0
0x18000a2cb  mov     [rsi+0C8h], rax
0x18000a2d2  mov     dword ptr [rsi+0A0h], 1
0x18000a2dc  mov     dword ptr [rsi+98h], 1
0x18000a2e6  movups  xmmword ptr [rsi+0D0h], xmm0
0x18000a2ed  movups  xmmword ptr [rsi+0E0h], xmm0
0x18000a2f4  movups  xmmword ptr [rsi+0F0h], xmm0
0x18000a2fb  movups  xmmword ptr [rsi+100h], xmm0
0x18000a302  movups  xmmword ptr [rsi+110h], xmm0
0x18000a309  mov     [rsi+120h], rax
0x18000a310  mov     dword ptr [rsi+0F8h], 1
0x18000a31a  mov     dword ptr [rsi+0F0h], 1
0x18000a324  lea     rcx, [rsi+130h]; lpCriticalSection
0x18000a32b  call    cs:__imp_InitializeCriticalSection
0x18000a332  nop     dword ptr [rax+rax+00h]
0x18000a337  nop
0x18000a338  mov     [rsi+158h], r12
0x18000a33f  mov     dword ptr [rsi+1844h], 6
0x18000a349  mov     [rsi+18D0h], r12
0x18000a350  mov     r14, [rsp+68h+hKey]
0x18000a358  test    r14, r14
0x18000a35b  jz      short loc_18000A3D9
0x18000a35d  mov     rdx, r14; int *
0x18000a360  mov     rcx, rsi; this
0x18000a363  call    ?Init@CIVIAudioCodec@@QEAAXPEAJ@Z; CIVIAudioCodec::Init(long *)
0x18000a368  cmp     cs:?g_Conv_float2short@@3P6AXPEAMH@ZEA, 0; void (*g_Conv_float2short)(float *,int)
0x18000a370  jnz     short loc_18000A380
0x18000a372  lea     rax, ?Conv_float2short_SSE2@@YAXPEAMH@Z; Conv_float2short_SSE2(float *,int)
0x18000a379  mov     cs:?g_Conv_float2short@@3P6AXPEAMH@ZEA, rax; void (*g_Conv_float2short)(float *,int)
0x18000a380  lea     r15, [rsi+18h]
0x18000a384  test    r15, r15
0x18000a387  jz      short loc_18000A3D9
0x18000a389  lea     rcx, [r15+10h]; lpCriticalSection
0x18000a38d  call    cs:__imp_InitializeCriticalSection
0x18000a394  nop     dword ptr [rax+rax+00h]
0x18000a399  lea     rcx, [r15+10h]; lpCriticalSection
0x18000a39d  call    cs:__imp_EnterCriticalSection
0x18000a3a4  nop     dword ptr [rax+rax+00h]
0x18000a3a9  lea     r9, [r15+8]; RegHandle
0x18000a3ad  xor     r8d, r8d; CallbackContext
0x18000a3b0  xor     edx, edx; EnableCallback
0x18000a3b2  lea     rcx, Microsoft_Windows_MSMPEG2ADEC; ProviderId
0x18000a3b9  call    cs:__imp_EventRegister
0x18000a3c0  nop     dword ptr [rax+rax+00h]
0x18000a3c5  mov     [r15], eax
0x18000a3c8  lea     rcx, [r15+10h]; lpCriticalSection
0x18000a3cc  call    cs:__imp_LeaveCriticalSection
0x18000a3d3  nop     dword ptr [rax+rax+00h]
0x18000a3d8  nop
0x18000a3d9  lea     rax, ??_7CIVIAudioFilter@@6BCUnknown@@@; const CIVIAudioFilter::`vftable'{for `CUnknown'}
0x18000a3e0  mov     [rdi], rax
0x18000a3e3  lea     rax, ??_7CIVIAudioFilter@@6BIBaseFilter@@@; const CIVIAudioFilter::`vftable'{for `IBaseFilter'}
0x18000a3ea  mov     [rdi+18h], rax
0x18000a3ee  lea     rax, ??_7CNamedTransformFilter@@6BIAMovieSetup@@@; const CNamedTransformFilter::`vftable'{for `IAMovieSetup'}
0x18000a3f5  mov     [rdi+20h], rax
0x18000a3f9  lea     rax, ??_7CIVIAudioFilter@@6BCIVIAudioCodec@@@; const CIVIAudioFilter::`vftable'{for `CIVIAudioCodec'}
0x18000a400  mov     [rsi], rax
0x18000a403  lea     rax, ??_7CIVIAudioFilter@@6BISpecifyPropertyPages@@@; const CIVIAudioFilter::`vftable'{for `ISpecifyPropertyPages'}
0x18000a40a  mov     [rdi+3C18h], rax
0x18000a411  lea     rax, ??_7CIVIAudioFilter@@6BICodecAPI@@@; const CIVIAudioFilter::`vftable'{for `ICodecAPI'}
0x18000a418  mov     [rdi+3C20h], rax
0x18000a41f  lea     rax, ??_7CIVIAudioFilter@@6BIPersistStream@@@; const CIVIAudioFilter::`vftable'{for `IPersistStream'}
0x18000a426  mov     [rdi+3C28h], rax
0x18000a42d  lea     rcx, [rdi+3C30h]; lpCriticalSection
0x18000a434  call    cs:__imp_InitializeCriticalSection
0x18000a43b  nop     dword ptr [rax+rax+00h]
0x18000a440  nop
0x18000a441  mov     [rdi+3C60h], r12
0x18000a448  lea     rcx, [rdi+3C78h]; lpCriticalSection
0x18000a44f  call    cs:__imp_InitializeCriticalSection
0x18000a456  nop     dword ptr [rax+rax+00h]
0x18000a45b  lea     rcx, [rdi+3C70h]; this
0x18000a462  call    ?Reset@AudioRateChange@@QEAAXXZ; AudioRateChange::Reset(void)
0x18000a467  nop
0x18000a468  mov     [rdi+40D8h], r12
0x18000a46f  mov     [rdi+40E0h], r12
0x18000a476  mov     [rdi+4350h], r12
0x18000a47d  mov     [rdi+4358h], r12d
0x18000a484  mov     [rdi+4360h], r12
0x18000a48b  mov     [rdi+4368h], r12
0x18000a492  mov     [rdi+4370h], r12
0x18000a499  mov     [rdi+4378h], r12
0x18000a4a0  xor     edx, edx; hFile
0x18000a4a2  mov     r8d, 800h; dwFlags
0x18000a4a8  lea     rcx, LibFileName; "avrt.dll"
0x18000a4af  call    cs:__imp_LoadLibraryExW
0x18000a4b6  nop     dword ptr [rax+rax+00h]
0x18000a4bb  mov     [rdi+4360h], rax
0x18000a4c2  test    rax, rax
0x18000a4c5  jz      short loc_18000A526
0x18000a4c7  lea     rdx, ProcName; "AvRevertMmThreadCharacteristics"
0x18000a4ce  mov     rcx, rax; hModule
0x18000a4d1  call    cs:__imp_GetProcAddress
0x18000a4d8  nop     dword ptr [rax+rax+00h]
0x18000a4dd  mov     [rdi+4370h], rax
0x18000a4e4  lea     rdx, aAvsetmmthreadc; "AvSetMmThreadCharacteristicsW"
0x18000a4eb  mov     rcx, [rdi+4360h]; hModule
0x18000a4f2  call    cs:__imp_GetProcAddress
0x18000a4f9  nop     dword ptr [rax+rax+00h]
0x18000a4fe  mov     [rdi+4368h], rax
0x18000a505  lea     rdx, aAvsetmmthreadp; "AvSetMmThreadPriority"
0x18000a50c  mov     rcx, [rdi+4360h]; hModule
0x18000a513  call    cs:__imp_GetProcAddress
0x18000a51a  nop     dword ptr [rax+rax+00h]
0x18000a51f  mov     [rdi+4378h], rax
0x18000a526  mov     [rdi+4380h], r12d
0x18000a52d  mov     [rdi+4584h], r12
0x18000a534  mov     [rdi+4590h], r12
0x18000a53b  mov     [rdi+4598h], r12
0x18000a542  mov     [rdi+45A0h], r12
0x18000a549  lea     rax, off_18008B170
0x18000a550  mov     [rdi+45A8h], rax
0x18000a557  test    r14, r14
0x18000a55a  jz      short loc_18000A55F
0x18000a55c  mov     [r14], r12d
0x18000a55f  lea     rcx, [rdi+4384h]; void *
0x18000a566  xor     edx, edx; Val
0x18000a568  mov     r8d, 200h; Size
0x18000a56e  call    memset_0
0x18000a573  mov     rcx, rdi; this
0x18000a576  call    ?Init@CIVIAudioFilter@@QEAAJXZ; CIVIAudioFilter::Init(void)
0x18000a57b  test    eax, eax
0x18000a57d  jns     short loc_18000A590
0x18000a57f  test    r14, r14
0x18000a582  jz      loc_18000A72B
0x18000a588  mov     [r14], eax
0x18000a58b  jmp     loc_18000A72B
0x18000a590  lea     rcx, [rdi+4100h]; unsigned __int16 *
0x18000a597  lea     r9, aMicrosoftDtvDv; "Microsoft DTV-DVD Audio Decoder"
0x18000a59e  lea     r8, aMsdtvadecFilte; "MSDTVADEC:(FILTER: %.80s)"
0x18000a5a5  mov     edx, 100h; unsigned __int64
0x18000a5aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a5af  call    ?Decrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_3@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_3@2@@Z; WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Decrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3 *)
0x18000a5b4  test    eax, eax
0x18000a5b6  jnz     short loc_18000A5C9
0x18000a5b8  lea     rcx, [rdi+4320h]; void **
0x18000a5bf  call    ?DRM_Create@@YAJPEAPEAX@Z; DRM_Create(void * *)
0x18000a5c4  call    ?Encrypt@?$CEncryption@$01V?$CCipherFeistel64@$0A@$0GD@$0FH@$0OH@$0BF@$0LC@$0LB@$0BN@$0N@$0DK@$0FJ@$0ID@$0BB@$0LD@$0OK@$0FA@$0BD@$0LL@$0MF@$0MH@$02$0EA@$0JO@$01$01$0PL@$0GM@$0KE@$0P@$0LK@$0EI@$0NL@$0BC@$09$0CK@$0LM@$0BO@$0GO@$0HK@$0DC@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$00$0BKGBKNDEJDGFEBEE@@2@UENCRYPTED_SEGMENT_DATA_CONST_3@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_3@5@@WarbirdRuntime@@SAJPEAUENCRYPTED_SEGMENT_DATA_CONST_3@2@PEAUENCRYPTED_SEGMENT_DATA_READ_WRITE_3@2@@Z; WarbirdRuntime::CEncryption<2,WarbirdCrypto::CCipherFeistel64<0,99,87,231,21,178,177,29,13,58,89,131,17,179,234,80,19,187,197,199,3,64,158,2,2,251,108,164,15,186,72,219,18,10,42,188,30,110,122,50>,WarbirdCrypto::CHashFunctionSCP<1,0,1,1900990959049851204>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3>::Encrypt(WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_3 *,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_3 *)
0x18000a5c9  mov     [rdi+4348h], r12d
0x18000a5d0  xor     ecx, ecx; Time
0x18000a5d2  call    cs:__imp__time64
0x18000a5d9  nop     dword ptr [rax+rax+00h]
0x18000a5de  mov     ecx, eax
0x18000a5e0  call    cs:__imp__o_srand
0x18000a5e7  nop     dword ptr [rax+rax+00h]
0x18000a5ec  mov     [rsp+68h+hKey], r12
0x18000a5f4  mov     dword ptr [rsp+68h+Type], r12d
0x18000a5f9  mov     dword ptr [rsp+68h+cbData], r12d
0x18000a601  cmp     cs:lpSubKey, 0
0x18000a609  jnz     short loc_18000A631
0x18000a60b  lea     rbx, xmmword_1800ADB00
0x18000a612  inc     rbp
0x18000a615  cmp     word ptr [rbx+rbp*2], 0
0x18000a61a  jnz     short loc_18000A612
0x18000a61c  test    rbp, rbp
0x18000a61f  jnz     short loc_18000A62A
0x18000a621  call    ?UTIL_REGGetModuleBase@@YAHW4ERegModule@@PEAG_K_N@Z; UTIL_REGGetModuleBase(ERegModule,ushort *,unsigned __int64,bool)
0x18000a626  test    eax, eax
0x18000a628  js      short loc_18000A631
0x18000a62a  mov     cs:lpSubKey, rbx
0x18000a631  mov     dword ptr [rsp+68h+cbData], 8
0x18000a63c  mov     esi, r12d
0x18000a63f  lea     r14, qword_180095458
0x18000a646  mov     rdx, cs:qword_1800ADAF0
0x18000a64d  cmp     esi, 2
0x18000a650  cmovl   rdx, cs:lpSubKey; lpSubKey
0x18000a658  test    rdx, rdx
0x18000a65b  jz      loc_18000A6E5
0x18000a661  movsxd  rcx, esi
0x18000a664  lea     rax, [rsp+68h+hKey]
0x18000a66c  mov     [rsp+68h+phkResult], rax; phkResult
0x18000a671  mov     r9d, 20019h; samDesired
0x18000a677  xor     r8d, r8d; ulOptions
0x18000a67a  mov     rcx, [r14+rcx*8]; hKey
0x18000a67e  call    cs:__imp_RegOpenKeyExW
0x18000a685  nop     dword ptr [rax+rax+00h]
0x18000a68a  test    eax, eax
0x18000a68c  jnz     short loc_18000A6E5
0x18000a68e  lea     rax, [rsp+68h+cbData]
0x18000a696  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18000a69b  lea     rax, [rsp+68h+Data]
0x18000a6a3  mov     [rsp+68h+phkResult], rax; lpData
0x18000a6a8  lea     r9, [rsp+68h+Type]; lpType
0x18000a6ad  xor     r8d, r8d; lpReserved
0x18000a6b0  lea     rdx, ValueName; "dolby_time_shift"
0x18000a6b7  mov     rcx, [rsp+68h+hKey]; hKey
0x18000a6bf  call    cs:__imp_RegQueryValueExW
0x18000a6c6  nop     dword ptr [rax+rax+00h]
0x18000a6cb  mov     ebx, eax
0x18000a6cd  mov     rcx, [rsp+68h+hKey]; hKey
0x18000a6d5  call    cs:__imp_RegCloseKey
0x18000a6dc  nop     dword ptr [rax+rax+00h]
0x18000a6e1  test    ebx, ebx
0x18000a6e3  jz      short loc_18000A6F7
0x18000a6e5  inc     esi
0x18000a6e7  movsxd  rax, esi
0x18000a6ea  cmp     qword ptr [r14+rax*8], 0
0x18000a6ef  jnz     loc_18000A646
0x18000a6f5  jmp     short loc_18000A724
0x18000a6f7  mov     eax, [rsp+68h+Data]
0x18000a6fe  mov     [rdi+1984h], eax
0x18000a704  test    eax, eax
0x18000a706  jz      short loc_18000A72B
0x18000a708  test    al, 1
0x18000a70a  jz      short loc_18000A718
0x18000a70c  add     eax, 989680h
0x18000a711  cmp     eax, 1312D00h
0x18000a716  jmp     short loc_18000A722
  ... truncated ...
```
