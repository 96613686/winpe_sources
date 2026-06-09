# DSSInitialize(void)

- ea: `0x18000d21c`
- end: `0x18000d3dc`
- name: `?DSSInitialize@@YAJXZ`
- size: `448`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callers

- `0x180005508`

## callees

- `0x1800041a0`
- `0x180006f78`
- `0x18000bf80`
- `0x18000c040`
- `0x18000d21c`
- `0x18000d860`
- `0x18000e2b0`
- `0x18000f300`
- `0x18000f384`
- `0x18000f468`
- `0x1800117c4`
- `0x180012e48`
- `0x180012f20`
- `0x1800135ec`
- `0x180017a68`

## string_xrefs

- `0x18000d2b8`: `SharingTokenManager::Initialize failed! hr=0x%x.`
- `0x18000d2c9`: `SharingTokenManager::Initialize`

## pseudocode

```c
__int64 DSSInitialize(void)
{
  int v0; // ebx
  __int64 v1; // rax
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  const WCHAR *v6; // rbx
  _DWORD *v7; // rsi
  DSLogger *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  DSLogger *v13; // rax
  int *v15; // rax
  int v16; // r8d
  int v17; // edx
  PMNotificationHandler *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  DSLogger *v23; // rax
  SqmHelper *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  DSLogger *v29; // rax
  __int64 v30; // [rsp+20h] [rbp-68h]
  _BYTE v31[32]; // [rsp+30h] [rbp-58h] BYREF
  int v32; // [rsp+50h] [rbp-38h]
  int v33; // [rsp+54h] [rbp-34h]
  int v34; // [rsp+58h] [rbp-30h]
  PCWSTR pszPathIn[4]; // [rsp+60h] [rbp-28h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v31);
  v33 = 1296000;
  v32 = 86400;
  v34 = 86400;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(pszPathIn);
  dword_18002B2D0 = 0;
  v0 = DSConfig::Load((DSConfig *)v31);
  if ( v0 < 0 )
    goto LABEL_8;
  v1 = tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get();
  v6 = pszPathIn[0];
  v7 = (_DWORD *)v1;
  if ( !pszPathIn[0] )
  {
    v0 = -2147024809;
LABEL_7:
    v8 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                       v3,
                       v2,
                       v4,
                       v5);
    DSLogger::LogError(
      v8,
      L"SharingTokenManager::Initialize",
      0x30u,
      L"SharingTokenManager::Initialize failed! hr=0x%x.",
      v0);
LABEL_8:
    DSSUninitialize();
    v13 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v10,
                        v9,
                        v11,
                        v12);
    LODWORD(v30) = v0;
    DSLogger::LogError(v13, L"DSSInitialize", 0x16Fu, L"hr=0x%x.", v30);
    goto LABEL_9;
  }
  if ( (int)SharingTokenDatabase::Initialize((SharingTokenDatabase *)(v1 + 8), pszPathIn[0]) < 0
    && (int)SharingTokenDatabase::Initialize((SharingTokenDatabase *)(v7 + 2), v6) < 0 )
  {
    v0 = -1055719422;
    goto LABEL_7;
  }
  *v7 = 1;
  v15 = (int *)tlx::_LazyImpl<TokenLifeManager,tlx::lazy_construct<TokenLifeManager>,tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>>>::get();
  v16 = v34;
  v17 = v33;
  *v15 = v32;
  v15[1] = v17;
  v15[2] = v16;
  tlx::_LazyImpl<TokenLifeManager,tlx::lazy_construct<TokenLifeManager>,tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>>>::get();
  v18 = (PMNotificationHandler *)tlx::_LazyImpl<PMNotificationHandler,tlx::lazy_construct<PMNotificationHandler>,tlx::static_lazy<PMNotificationHandler,0,tlx::lazy_construct<PMNotificationHandler>>>::get();
  v0 = PMNotificationHandler::Register(v18);
  if ( v0 < 0 )
    goto LABEL_8;
  v0 = RegisterExtensions();
  if ( v0 < 0 )
    goto LABEL_8;
  v23 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                      v20,
                      v19,
                      v21,
                      v22);
  DSLogger::LogInformation(v23, L"SqmHelper::Initialize", 0x29u, L"Register to global SQM session");
  *(_QWORD *)&g_hDssSqmGlobalSession.Data1 = SqmHelper::GetGlobalSession(v24);
  if ( *(_QWORD *)&g_hDssSqmGlobalSession.Data1 )
  {
    g_fWpSqmInitialized = 1;
  }
  else
  {
    v29 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v26,
                        v25,
                        v27,
                        v28);
    DSLogger::LogError(v29, L"SqmHelper::Initialize", 0x33u, L"Initialize SQM session failed (0x%x)", -2147467259);
  }
  dword_18002B2D0 = 1;
LABEL_9:
  DSConfig::~DSConfig((DSConfig *)v31);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18000d21c  mov     [rsp+arg_0], rbx
0x18000d221  mov     [rsp+arg_8], rsi
0x18000d226  push    rdi
0x18000d227  sub     rsp, 80h
0x18000d22e  lea     rcx, [rsp+88h+var_58]
0x18000d233  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000d238  mov     ecx, 15180h
0x18000d23d  mov     [rsp+88h+var_34], 13C680h
0x18000d245  mov     [rsp+88h+var_38], ecx
0x18000d249  mov     [rsp+88h+var_30], ecx
0x18000d24d  lea     rcx, [rsp+88h+pszPathIn]
0x18000d252  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18000d257  lea     rcx, [rsp+88h+var_58]; this
0x18000d25c  mov     cs:dword_18002B2D0, 0
0x18000d266  call    ?Load@DSConfig@@QEAAJXZ; DSConfig::Load(void)
0x18000d26b  mov     ebx, eax
0x18000d26d  test    eax, eax
0x18000d26f  js      short loc_18000D2D8
0x18000d271  call    ?get@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAAAEAVSharingTokenManager@@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(void)
0x18000d276  mov     rbx, [rsp+88h+pszPathIn]
0x18000d27b  mov     rsi, rax
0x18000d27e  test    rbx, rbx
0x18000d281  jnz     short loc_18000D28A
0x18000d283  mov     ebx, 80070057h
0x18000d288  jmp     short loc_18000D2B3
0x18000d28a  mov     rdx, rbx; pszPathIn
0x18000d28d  lea     rcx, [rax+8]; this
0x18000d291  call    ?Initialize@SharingTokenDatabase@@QEAAJPEBG@Z; SharingTokenDatabase::Initialize(ushort const *)
0x18000d296  test    eax, eax
0x18000d298  jns     loc_18000D323
0x18000d29e  mov     rdx, rbx; pszPathIn
0x18000d2a1  lea     rcx, [rsi+8]; this
0x18000d2a5  call    ?Initialize@SharingTokenDatabase@@QEAAJPEBG@Z; SharingTokenDatabase::Initialize(ushort const *)
0x18000d2aa  test    eax, eax
0x18000d2ac  jns     short loc_18000D323
0x18000d2ae  mov     ebx, 0C1130002h
0x18000d2b3  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d2b8  lea     r9, aSharingtokenma; "SharingTokenManager::Initialize failed!"...
0x18000d2bf  mov     [rsp+88h+var_68], ebx
0x18000d2c3  mov     r8d, 30h ; '0'; unsigned int
0x18000d2c9  lea     rdx, aSharingtokenma_2; "SharingTokenManager::Initialize"
0x18000d2d0  mov     rcx, rax; this
0x18000d2d3  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000d2d8  call    ?DSSUninitialize@@YAJXZ; DSSUninitialize(void)
0x18000d2dd  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d2e2  lea     r9, aHr0xX; "hr=0x%x."
0x18000d2e9  mov     [rsp+88h+var_68], ebx
0x18000d2ed  mov     r8d, 16Fh; unsigned int
0x18000d2f3  lea     rdx, aDssinitialize; "DSSInitialize"
0x18000d2fa  mov     rcx, rax; this
0x18000d2fd  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000d302  lea     rcx, [rsp+88h+var_58]; this
0x18000d307  call    ??1DSConfig@@QEAA@XZ; DSConfig::~DSConfig(void)
0x18000d30c  lea     r11, [rsp+88h+var_8]
0x18000d314  mov     eax, ebx
0x18000d316  mov     rbx, [r11+10h]
0x18000d31a  mov     rsi, [r11+18h]
0x18000d31e  mov     rsp, r11
0x18000d321  pop     rdi
0x18000d322  retn
0x18000d323  mov     edi, 1
0x18000d328  mov     [rsi], edi
0x18000d32a  call    ?get@?$_LazyImpl@VTokenLifeManager@@V?$lazy_construct@VTokenLifeManager@@@tlx@@V?$static_lazy@VTokenLifeManager@@$0A@V?$lazy_construct@VTokenLifeManager@@@tlx@@@3@@tlx@@QEAAAEAVTokenLifeManager@@XZ; tlx::_LazyImpl<TokenLifeManager,tlx::lazy_construct<TokenLifeManager>,tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>>>::get(void)
0x18000d32f  mov     r8d, [rsp+88h+var_30]
0x18000d334  mov     edx, [rsp+88h+var_34]
0x18000d338  mov     ecx, [rsp+88h+var_38]
0x18000d33c  mov     [rax], ecx
0x18000d33e  mov     [rax+4], edx
0x18000d341  mov     [rax+8], r8d
0x18000d345  call    ?get@?$_LazyImpl@VTokenLifeManager@@V?$lazy_construct@VTokenLifeManager@@@tlx@@V?$static_lazy@VTokenLifeManager@@$0A@V?$lazy_construct@VTokenLifeManager@@@tlx@@@3@@tlx@@QEAAAEAVTokenLifeManager@@XZ; tlx::_LazyImpl<TokenLifeManager,tlx::lazy_construct<TokenLifeManager>,tlx::static_lazy<TokenLifeManager,0,tlx::lazy_construct<TokenLifeManager>>>::get(void)
0x18000d34a  call    ?get@?$_LazyImpl@VPMNotificationHandler@@V?$lazy_construct@VPMNotificationHandler@@@tlx@@V?$static_lazy@VPMNotificationHandler@@$0A@V?$lazy_construct@VPMNotificationHandler@@@tlx@@@3@@tlx@@QEAAAEAVPMNotificationHandler@@XZ; tlx::_LazyImpl<PMNotificationHandler,tlx::lazy_construct<PMNotificationHandler>,tlx::static_lazy<PMNotificationHandler,0,tlx::lazy_construct<PMNotificationHandler>>>::get(void)
0x18000d34f  mov     rcx, rax; this
0x18000d352  call    ?Register@PMNotificationHandler@@QEAAJXZ; PMNotificationHandler::Register(void)
0x18000d357  mov     ebx, eax
0x18000d359  test    eax, eax
0x18000d35b  js      loc_18000D2D8
0x18000d361  call    RegisterExtensions
0x18000d366  mov     ebx, eax
0x18000d368  test    eax, eax
0x18000d36a  js      loc_18000D2D8
0x18000d370  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d375  lea     r9, aRegisterToGlob; "Register to global SQM session"
0x18000d37c  mov     rcx, rax; this
0x18000d37f  lea     r8d, [rdi+28h]; unsigned int
0x18000d383  lea     rdx, aSqmhelperIniti; "SqmHelper::Initialize"
0x18000d38a  call    ?LogInformation@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogInformation(ushort const *,ulong,ushort const *,...)
0x18000d38f  call    ?GetGlobalSession@SqmHelper@@YAPEAU_GUID@@XZ; SqmHelper::GetGlobalSession(void)
0x18000d394  mov     qword ptr cs:?g_hDssSqmGlobalSession@@3PEAU_GUID@@EA.Data1, rax; _GUID * g_hDssSqmGlobalSession ...
0x18000d39b  test    rax, rax
0x18000d39e  jz      short loc_18000D3A8
0x18000d3a0  mov     cs:?g_fWpSqmInitialized@@3HA, edi; int g_fWpSqmInitialized
0x18000d3a6  jmp     short loc_18000D3D1
0x18000d3a8  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d3ad  lea     r9, aInitializeSqmS; "Initialize SQM session failed (0x%x)"
0x18000d3b4  mov     [rsp+88h+var_68], 80004005h
0x18000d3bc  mov     r8d, 33h ; '3'; unsigned int
0x18000d3c2  lea     rdx, aSqmhelperIniti; "SqmHelper::Initialize"
0x18000d3c9  mov     rcx, rax; this
0x18000d3cc  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000d3d1  mov     cs:dword_18002B2D0, edi
0x18000d3d7  jmp     loc_18000D302
```
