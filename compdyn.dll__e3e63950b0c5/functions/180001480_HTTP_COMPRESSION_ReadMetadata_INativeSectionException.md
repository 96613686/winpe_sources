# HTTP_COMPRESSION::ReadMetadata(INativeSectionException * *)

- ea: `0x180001480`
- end: `0x180001864`
- name: `?ReadMetadata@HTTP_COMPRESSION@@CAJPEAPEAVINativeSectionException@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001480`
- `0x180008010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001578`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180001578`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180001566`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180001588`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180005083`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800050a0`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180001566`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180001588`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180005083`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800050a0`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800050e8`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180005128`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x1800050e8`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180005128`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180005093`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180005093`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000154f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000154f`

## string_xrefs

- `0x1800014f5`: `system.webServer/httpCompression`
- `0x180001527`: `directory`
- `0x1800015ae`: `sendCacheHeaders`
- `0x1800016f1`: `minFileSizeForComp`
- `0x1800016c1`: `noCompressionForRange`
- `0x180001661`: `noCompressionForHttp10`
- `0x180001691`: `noCompressionForProxies`
- `0x180001721`: `dynamicCompressionBufferLimit`
- `0x180001781`: `staticCompressionEnableCpuUsage`
- `0x1800017e1`: `dynamicCompressionEnableCpuUsage`
- `0x180001751`: `staticCompressionDisableCpuUsage`
- `0x1800017b1`: `dynamicCompressionDisableCpuUsage`
- `0x180001811`: `staticCompressionIgnoreHitFrequency`
- `0x1800050c4`: `cacheControlHeader`

## pseudocode

```c
__int64 __fastcall HTTP_COMPRESSION::ReadMetadata(struct INativeSectionException **a1)
{
  __int64 v2; // rax
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rax
  int v4; // ebx
  unsigned __int16 *Str; // rbx
  unsigned int CCH; // eax
  const unsigned __int16 *v8; // [rsp+40h] [rbp-20h] BYREF
  const unsigned __int16 *v9; // [rsp+48h] [rbp-18h] BYREF
  const unsigned __int16 *v10; // [rsp+50h] [rbp-10h] BYREF
  int v11; // [rsp+88h] [rbp+28h] BYREF
  __int64 v12; // [rsp+90h] [rbp+30h] BYREF
  __int64 v13; // [rsp+98h] [rbp+38h] BYREF

  v13 = 0;
  v12 = 0;
  v8 = 0;
  v2 = *(_QWORD *)g_pGlobalInfo;
  v9 = 0;
  v10 = 0;
  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(v2 + 56))(g_pGlobalInfo);
  v4 = (**v3)(v3, &IID_INativeConfigurationSystem, &v13);
  if ( v4 < 0 )
    goto LABEL_30;
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v13 + 24LL))(
         v13,
         L"system.webServer/httpCompression",
         L"MACHINE/WEBROOT/APPHOST",
         &v12,
         a1,
         0);
  if ( v4 < 0 )
    goto LABEL_30;
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v12 + 64LL))(
         v12,
         L"directory",
         &v8,
         0,
         0);
  if ( v4 < 0 )
    goto LABEL_30;
  v4 = STRU::Copy((STRU *)HTTP_COMPRESSION::sm_pstrCompressionDirectory, v8);
  if ( v4 < 0 )
    goto LABEL_30;
  while ( STRU::QueryCCH((STRU *)HTTP_COMPRESSION::sm_pstrCompressionDirectory) > 1 )
  {
    Str = STRU::QueryStr((STRU *)HTTP_COMPRESSION::sm_pstrCompressionDirectory);
    if ( Str[STRU::QueryCCH((STRU *)HTTP_COMPRESSION::sm_pstrCompressionDirectory) - 1] != 92 )
      break;
    CCH = STRU::QueryCCH((STRU *)HTTP_COMPRESSION::sm_pstrCompressionDirectory);
    STRU::SetLen((STRU *)HTTP_COMPRESSION::sm_pstrCompressionDirectory, CCH - 1);
  }
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 72LL))(
         v12,
         L"sendCacheHeaders",
         &HTTP_COMPRESSION::sm_fSendCacheHeaders,
         0,
         0);
  if ( v4 < 0 )
    goto LABEL_30;
  if ( HTTP_COMPRESSION::sm_fSendCacheHeaders )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v12 + 64LL))(
           v12,
           L"cacheControlHeader",
           &v9,
           0,
           0);
    if ( v4 < 0 )
      goto LABEL_30;
    v4 = STRA::CopyW((STRA *)HTTP_COMPRESSION::sm_pstrCacheControlHeader, v9);
    if ( v4 < 0 )
      goto LABEL_30;
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v12 + 64LL))(
           v12,
           L"expiresHeader",
           &v10,
           0,
           0);
    if ( v4 < 0 )
      goto LABEL_30;
    v4 = STRA::CopyW((STRA *)HTTP_COMPRESSION::sm_pstrExpiresHeader, v10);
    if ( v4 < 0 )
      goto LABEL_30;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 72LL))(
         v12,
         L"doDiskSpaceLimiting",
         &HTTP_COMPRESSION::sm_fDoDiskSpaceLimiting,
         0,
         0);
  if ( v4 < 0 )
    goto LABEL_30;
  if ( HTTP_COMPRESSION::sm_fDoDiskSpaceLimiting )
  {
    v11 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
           v12,
           L"maxDiskSpaceUsage",
           &v11,
           0,
           0);
    if ( v4 < 0 )
      goto LABEL_30;
    HTTP_COMPRESSION::sm_dwMaxDiskSpaceUsage = (__int64)v11 << 20;
  }
  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 72LL))(
         v12,
         L"noCompressionForHttp10",
         &HTTP_COMPRESSION::sm_fNoCompressionForHttp10,
         0,
         0);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 72LL))(
           v12,
           L"noCompressionForProxies",
           &HTTP_COMPRESSION::sm_fNoCompressionForProxies,
           0,
           0);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 72LL))(
             v12,
             L"noCompressionForRange",
             &HTTP_COMPRESSION::sm_fNoCompressionForRange,
             0,
             0);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
               v12,
               L"minFileSizeForComp",
               &HTTP_COMPRESSION::sm_dwMinFileSizeForCompression,
               0,
               0);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
                 v12,
                 L"dynamicCompressionBufferLimit",
                 &HTTP_COMPRESSION::sm_dwDynamicCompressionBufferLimit,
                 0,
                 0);
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
                   v12,
                   L"staticCompressionDisableCpuUsage",
                   &HTTP_COMPRESSION::sm_dwStaticCompressionHighWaterMark,
                   0,
                   0);
            if ( v4 >= 0 )
            {
              v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
                     v12,
                     L"staticCompressionEnableCpuUsage",
                     &HTTP_COMPRESSION::sm_dwStaticCompressionLowWaterMark,
                     0,
                     0);
              if ( v4 >= 0 )
              {
                v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
                       v12,
                       L"dynamicCompressionDisableCpuUsage",
                       &HTTP_COMPRESSION::sm_dwDynamicCompressionHighWaterMark,
                       0,
                       0);
                if ( v4 >= 0 )
                {
                  v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 48LL))(
                         v12,
                         L"dynamicCompressionEnableCpuUsage",
                         &HTTP_COMPRESSION::sm_dwDynamicCompressionLowWaterMark,
                         0,
                         0);
                  if ( v4 >= 0 )
                  {
                    v4 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v12 + 72LL))(
                           v12,
                           L"staticCompressionIgnoreHitFrequency",
                           &HTTP_COMPRESSION::sm_fStaticCompressionIgnoreHitFrequency,
                           0,
                           0);
                    if ( v4 >= 0 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
                      v12 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
                      return 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_30:
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v12 = 0;
  }
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180001480  mov     [rsp-18h+arg_0], rbx
0x180001485  push    rbp
0x180001486  push    rsi
0x180001487  push    rdi
0x180001488  mov     rbp, rsp
0x18000148b  sub     rsp, 60h
0x18000148f  xor     esi, esi
0x180001491  mov     rdi, rcx
0x180001494  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000149b  mov     [rbp+arg_18], rsi
0x18000149f  mov     [rbp+arg_10], rsi
0x1800014a3  mov     [rbp+var_20], rsi
0x1800014a7  mov     rax, [rcx]
0x1800014aa  mov     [rbp+var_18], rsi
0x1800014ae  mov     [rbp+var_10], rsi
0x1800014b2  mov     rax, [rax+38h]
0x1800014b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014bb  mov     r9, rax
0x1800014be  lea     r8, [rbp+arg_18]
0x1800014c2  lea     rdx, IID_INativeConfigurationSystem
0x1800014c9  mov     rcx, [rax]
0x1800014cc  mov     rax, [rcx]
0x1800014cf  mov     rcx, r9
0x1800014d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014d7  mov     ebx, eax
0x1800014d9  test    eax, eax
0x1800014db  js      loc_180005138
0x1800014e1  mov     rcx, [rbp+arg_18]
0x1800014e5  lea     r9, [rbp+arg_10]
0x1800014e9  mov     [rsp+60h+var_38], rsi
0x1800014ee  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800014f5  lea     rdx, aSystemWebserve_0; "system.webServer/httpCompression"
0x1800014fc  mov     [rsp+60h+var_40], rdi
0x180001501  mov     rax, [rcx]
0x180001504  mov     rax, [rax+18h]
0x180001508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000150d  mov     ebx, eax
0x18000150f  test    eax, eax
0x180001511  js      loc_180005138
0x180001517  mov     rcx, [rbp+arg_10]
0x18000151b  lea     r8, [rbp+var_20]
0x18000151f  xor     r9d, r9d
0x180001522  mov     [rsp+60h+var_40], rsi
0x180001527  lea     rdx, aDirectory; "directory"
0x18000152e  mov     rax, [rcx]
0x180001531  mov     rax, [rax+40h]
0x180001535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000153a  mov     ebx, eax
0x18000153c  test    eax, eax
0x18000153e  js      loc_180005138
0x180001544  mov     rdx, [rbp+var_20]
0x180001548  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x18000154f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180001555  mov     ebx, eax
0x180001557  test    eax, eax
0x180001559  js      loc_180005138
0x18000155f  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180001566  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000156c  cmp     eax, 1
0x18000156f  jbe     short loc_18000159B
0x180001571  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180001578  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000157e  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180001585  mov     rbx, rax
0x180001588  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000158e  dec     eax
0x180001590  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x180001595  jz      loc_18000507C
0x18000159b  mov     rcx, [rbp+arg_10]
0x18000159f  lea     r8, ?sm_fSendCacheHeaders@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fSendCacheHeaders
0x1800015a6  xor     r9d, r9d
0x1800015a9  mov     [rsp+60h+var_40], rsi
0x1800015ae  lea     rdx, aSendcacheheade; "sendCacheHeaders"
0x1800015b5  mov     rax, [rcx]
0x1800015b8  mov     rax, [rax+48h]
0x1800015bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015c1  mov     ebx, eax
0x1800015c3  test    eax, eax
0x1800015c5  js      loc_180005138
0x1800015cb  cmp     cs:?sm_fSendCacheHeaders@HTTP_COMPRESSION@@0HA, esi; int HTTP_COMPRESSION::sm_fSendCacheHeaders
0x1800015d1  jnz     loc_1800050B4
0x1800015d7  mov     rcx, [rbp+arg_10]
0x1800015db  lea     r8, ?sm_fDoDiskSpaceLimiting@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fDoDiskSpaceLimiting
0x1800015e2  xor     r9d, r9d
0x1800015e5  mov     [rsp+60h+var_40], rsi
0x1800015ea  lea     rdx, aDodiskspacelim; "doDiskSpaceLimiting"
0x1800015f1  mov     rax, [rcx]
0x1800015f4  mov     rax, [rax+48h]
0x1800015f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015fd  mov     ebx, eax
0x1800015ff  test    eax, eax
0x180001601  js      loc_180005138
0x180001607  cmp     cs:?sm_fDoDiskSpaceLimiting@HTTP_COMPRESSION@@0HA, esi; int HTTP_COMPRESSION::sm_fDoDiskSpaceLimiting
0x18000160d  jz      short loc_18000164E
0x18000160f  mov     rcx, [rbp+arg_10]
0x180001613  lea     r8, [rbp+arg_8]
0x180001617  mov     [rbp+arg_8], esi
0x18000161a  lea     rdx, aMaxdiskspaceus; "maxDiskSpaceUsage"
0x180001621  xor     r9d, r9d
0x180001624  mov     [rsp+60h+var_40], rsi
0x180001629  mov     rax, [rcx]
0x18000162c  mov     rax, [rax+30h]
0x180001630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001635  mov     ebx, eax
0x180001637  test    eax, eax
0x180001639  js      loc_180005138
0x18000163f  movsxd  rax, [rbp+arg_8]
0x180001643  shl     rax, 14h
0x180001647  mov     cs:?sm_dwMaxDiskSpaceUsage@HTTP_COMPRESSION@@0_KA, rax; unsigned __int64 HTTP_COMPRESSION::sm_dwMaxDiskSpaceUsage
0x18000164e  mov     rcx, [rbp+arg_10]
0x180001652  lea     r8, ?sm_fNoCompressionForHttp10@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fNoCompressionForHttp10
0x180001659  xor     r9d, r9d
0x18000165c  mov     [rsp+60h+var_40], rsi
0x180001661  lea     rdx, aNocompressionf; "noCompressionForHttp10"
0x180001668  mov     rax, [rcx]
0x18000166b  mov     rax, [rax+48h]
0x18000166f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001674  mov     ebx, eax
0x180001676  test    eax, eax
0x180001678  js      loc_180005138
0x18000167e  mov     rcx, [rbp+arg_10]
0x180001682  lea     r8, ?sm_fNoCompressionForProxies@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fNoCompressionForProxies
0x180001689  xor     r9d, r9d
0x18000168c  mov     [rsp+60h+var_40], rsi
0x180001691  lea     rdx, aNocompressionf_0; "noCompressionForProxies"
0x180001698  mov     rax, [rcx]
0x18000169b  mov     rax, [rax+48h]
0x18000169f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016a4  mov     ebx, eax
0x1800016a6  test    eax, eax
0x1800016a8  js      loc_180005138
0x1800016ae  mov     rcx, [rbp+arg_10]
0x1800016b2  lea     r8, ?sm_fNoCompressionForRange@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fNoCompressionForRange
0x1800016b9  xor     r9d, r9d
0x1800016bc  mov     [rsp+60h+var_40], rsi
0x1800016c1  lea     rdx, aNocompressionf_1; "noCompressionForRange"
0x1800016c8  mov     rax, [rcx]
0x1800016cb  mov     rax, [rax+48h]
0x1800016cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800016d4  mov     ebx, eax
0x1800016d6  test    eax, eax
0x1800016d8  js      loc_180005138
0x1800016de  mov     rcx, [rbp+arg_10]
0x1800016e2  lea     r8, ?sm_dwMinFileSizeForCompression@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwMinFileSizeForCompression
0x1800016e9  xor     r9d, r9d
0x1800016ec  mov     [rsp+60h+var_40], rsi
0x1800016f1  lea     rdx, aMinfilesizefor; "minFileSizeForComp"
0x1800016f8  mov     rax, [rcx]
0x1800016fb  mov     rax, [rax+30h]
0x1800016ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001704  mov     ebx, eax
0x180001706  test    eax, eax
0x180001708  js      loc_180005138
0x18000170e  mov     rcx, [rbp+arg_10]
0x180001712  lea     r8, ?sm_dwDynamicCompressionBufferLimit@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwDynamicCompressionBufferLimit
0x180001719  xor     r9d, r9d
0x18000171c  mov     [rsp+60h+var_40], rsi
0x180001721  lea     rdx, aDynamiccompres; "dynamicCompressionBufferLimit"
0x180001728  mov     rax, [rcx]
0x18000172b  mov     rax, [rax+30h]
0x18000172f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001734  mov     ebx, eax
0x180001736  test    eax, eax
0x180001738  js      loc_180005138
0x18000173e  mov     rcx, [rbp+arg_10]
0x180001742  lea     r8, ?sm_dwStaticCompressionHighWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwStaticCompressionHighWaterMark
0x180001749  xor     r9d, r9d
0x18000174c  mov     [rsp+60h+var_40], rsi
0x180001751  lea     rdx, aStaticcompress_1; "staticCompressionDisableCpuUsage"
0x180001758  mov     rax, [rcx]
0x18000175b  mov     rax, [rax+30h]
0x18000175f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001764  mov     ebx, eax
0x180001766  test    eax, eax
0x180001768  js      loc_180005138
0x18000176e  mov     rcx, [rbp+arg_10]
0x180001772  lea     r8, ?sm_dwStaticCompressionLowWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwStaticCompressionLowWaterMark
0x180001779  xor     r9d, r9d
0x18000177c  mov     [rsp+60h+var_40], rsi
0x180001781  lea     rdx, aStaticcompress_0; "staticCompressionEnableCpuUsage"
0x180001788  mov     rax, [rcx]
0x18000178b  mov     rax, [rax+30h]
0x18000178f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001794  mov     ebx, eax
0x180001796  test    eax, eax
0x180001798  js      loc_180005138
0x18000179e  mov     rcx, [rbp+arg_10]
0x1800017a2  lea     r8, ?sm_dwDynamicCompressionHighWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwDynamicCompressionHighWaterMark
0x1800017a9  xor     r9d, r9d
0x1800017ac  mov     [rsp+60h+var_40], rsi
0x1800017b1  lea     rdx, aDynamiccompres_2; "dynamicCompressionDisableCpuUsage"
0x1800017b8  mov     rax, [rcx]
0x1800017bb  mov     rax, [rax+30h]
0x1800017bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017c4  mov     ebx, eax
0x1800017c6  test    eax, eax
0x1800017c8  js      loc_180005138
0x1800017ce  mov     rcx, [rbp+arg_10]
0x1800017d2  lea     r8, ?sm_dwDynamicCompressionLowWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwDynamicCompressionLowWaterMark
0x1800017d9  xor     r9d, r9d
0x1800017dc  mov     [rsp+60h+var_40], rsi
0x1800017e1  lea     rdx, aDynamiccompres_0; "dynamicCompressionEnableCpuUsage"
0x1800017e8  mov     rax, [rcx]
0x1800017eb  mov     rax, [rax+30h]
0x1800017ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017f4  mov     ebx, eax
0x1800017f6  test    eax, eax
0x1800017f8  js      loc_180005138
0x1800017fe  mov     rcx, [rbp+arg_10]
0x180001802  lea     r8, ?sm_fStaticCompressionIgnoreHitFrequency@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fStaticCompressionIgnoreHitFrequency
0x180001809  xor     r9d, r9d
0x18000180c  mov     [rsp+60h+var_40], rsi
0x180001811  lea     rdx, aStaticcompress_2; "staticCompressionIgnoreHitFrequency"
0x180001818  mov     rax, [rcx]
0x18000181b  mov     rax, [rax+48h]
0x18000181f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001824  mov     ebx, eax
0x180001826  test    eax, eax
0x180001828  js      loc_180005138
0x18000182e  mov     rcx, [rbp+arg_10]
0x180001832  mov     rax, [rcx]
0x180001835  mov     rax, [rax+10h]
0x180001839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000183e  mov     rcx, [rbp+arg_18]
0x180001842  mov     [rbp+arg_10], rsi
0x180001846  mov     rax, [rcx]
0x180001849  mov     rax, [rax+10h]
0x18000184d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001852  xor     eax, eax
0x180001854  mov     rbx, [rsp+60h+arg_0]
0x18000185c  add     rsp, 60h
0x180001860  pop     rdi
0x180001861  pop     rsi
0x180001862  pop     rbp
0x180001863  retn
0x18000507c  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180005083  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180005089  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180005090  lea     edx, [rax-1]
0x180005093  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180005099  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x1800050a0  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800050a6  cmp     eax, 1
0x1800050a9  ja      loc_180001571
0x1800050af  jmp     loc_18000159B
0x1800050b4  mov     rcx, [rbp+arg_10]
0x1800050b8  lea     r8, [rbp+var_18]
0x1800050bc  xor     r9d, r9d
0x1800050bf  mov     [rsp+60h+var_40], rsi
0x1800050c4  lea     rdx, aCachecontrolhe; "cacheControlHeader"
0x1800050cb  mov     rax, [rcx]
0x1800050ce  mov     rax, [rax+40h]
0x1800050d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d7  mov     ebx, eax
0x1800050d9  test    eax, eax
0x1800050db  js      short loc_180005138
0x1800050dd  mov     rdx, [rbp+var_18]
0x1800050e1  mov     rcx, cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x1800050e8  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x1800050ee  mov     ebx, eax
0x1800050f0  test    eax, eax
0x1800050f2  js      short loc_180005138
0x1800050f4  mov     rcx, [rbp+arg_10]
0x1800050f8  lea     r8, [rbp+var_10]
0x1800050fc  xor     r9d, r9d
0x1800050ff  mov     [rsp+60h+var_40], rsi
0x180005104  lea     rdx, aExpiresheader; "expiresHeader"
0x18000510b  mov     rax, [rcx]
0x18000510e  mov     rax, [rax+40h]
0x180005112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005117  mov     ebx, eax
0x180005119  test    eax, eax
0x18000511b  js      short loc_180005138
0x18000511d  mov     rdx, [rbp+var_10]
0x180005121  mov     rcx, cs:?sm_pstrExpiresHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrExpiresHeader
0x180005128  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000512e  mov     ebx, eax
0x180005130  test    eax, eax
0x180005132  jns     loc_1800015D7
0x180005138  mov     rcx, [rbp+arg_10]
0x18000513c  test    rcx, rcx
0x18000513f  jz      short loc_180005151
0x180005141  mov     rax, [rcx]
0x180005144  mov     rax, [rax+10h]
0x180005148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000514d  mov     [rbp+arg_10], rsi
0x180005151  mov     rcx, [rbp+arg_18]
0x180005155  test    rcx, rcx
0x180005158  jz      short loc_180005166
0x18000515a  mov     rax, [rcx]
0x18000515d  mov     rax, [rax+10h]
0x180005161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005166  mov     eax, ebx
0x180005168  jmp     loc_180001854
```
