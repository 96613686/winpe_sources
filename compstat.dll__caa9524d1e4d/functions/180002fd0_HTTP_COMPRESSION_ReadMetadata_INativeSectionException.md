# HTTP_COMPRESSION::ReadMetadata(INativeSectionException * *)

- ea: `0x180002fd0`
- end: `0x1800033b4`
- name: `?ReadMetadata@HTTP_COMPRESSION@@CAJPEAPEAVINativeSectionException@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002bb0`

## callees

- `0x180002fd0`
- `0x180009010`

## import_xrefs

- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180006fb3`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180006fb3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800030c8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800030c8`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180007008`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180007048`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180007008`
- `iisutil!?CopyW@STRA@@QEAAJPEBG@Z` at `0x180007048`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800030b6`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800030d8`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180006fa3`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180006fc0`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800030b6`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800030d8`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180006fa3`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180006fc0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000309f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000309f`

## string_xrefs

- `0x180003077`: `directory`
- `0x1800030fe`: `sendCacheHeaders`
- `0x180003241`: `minFileSizeForComp`
- `0x180003211`: `noCompressionForRange`
- `0x1800031b1`: `noCompressionForHttp10`
- `0x1800031e1`: `noCompressionForProxies`
- `0x180003271`: `dynamicCompressionBufferLimit`
- `0x1800032d1`: `staticCompressionEnableCpuUsage`
- `0x180003045`: `system.webServer/httpCompression`
- `0x180003331`: `dynamicCompressionEnableCpuUsage`
- `0x1800032a1`: `staticCompressionDisableCpuUsage`
- `0x180003301`: `dynamicCompressionDisableCpuUsage`
- `0x180003361`: `staticCompressionIgnoreHitFrequency`
- `0x180006fe4`: `cacheControlHeader`

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
0x180002fd0  mov     [rsp-18h+arg_0], rbx
0x180002fd5  push    rbp
0x180002fd6  push    rsi
0x180002fd7  push    rdi
0x180002fd8  mov     rbp, rsp
0x180002fdb  sub     rsp, 60h
0x180002fdf  xor     esi, esi
0x180002fe1  mov     rdi, rcx
0x180002fe4  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002feb  mov     [rbp+arg_18], rsi
0x180002fef  mov     [rbp+arg_10], rsi
0x180002ff3  mov     [rbp+var_20], rsi
0x180002ff7  mov     rax, [rcx]
0x180002ffa  mov     [rbp+var_18], rsi
0x180002ffe  mov     [rbp+var_10], rsi
0x180003002  mov     rax, [rax+38h]
0x180003006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000300b  mov     r9, rax
0x18000300e  lea     r8, [rbp+arg_18]
0x180003012  lea     rdx, IID_INativeConfigurationSystem
0x180003019  mov     rcx, [rax]
0x18000301c  mov     rax, [rcx]
0x18000301f  mov     rcx, r9
0x180003022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003027  mov     ebx, eax
0x180003029  test    eax, eax
0x18000302b  js      loc_180007058
0x180003031  mov     rcx, [rbp+arg_18]
0x180003035  lea     r9, [rbp+arg_10]
0x180003039  mov     [rsp+60h+var_38], rsi
0x18000303e  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180003045  lea     rdx, aSystemWebserve_1; "system.webServer/httpCompression"
0x18000304c  mov     [rsp+60h+var_40], rdi
0x180003051  mov     rax, [rcx]
0x180003054  mov     rax, [rax+18h]
0x180003058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000305d  mov     ebx, eax
0x18000305f  test    eax, eax
0x180003061  js      loc_180007058
0x180003067  mov     rcx, [rbp+arg_10]
0x18000306b  lea     r8, [rbp+var_20]
0x18000306f  xor     r9d, r9d
0x180003072  mov     [rsp+60h+var_40], rsi
0x180003077  lea     rdx, aDirectory; "directory"
0x18000307e  mov     rax, [rcx]
0x180003081  mov     rax, [rax+40h]
0x180003085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000308a  mov     ebx, eax
0x18000308c  test    eax, eax
0x18000308e  js      loc_180007058
0x180003094  mov     rdx, [rbp+var_20]
0x180003098  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x18000309f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800030a5  mov     ebx, eax
0x1800030a7  test    eax, eax
0x1800030a9  js      loc_180007058
0x1800030af  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x1800030b6  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800030bc  cmp     eax, 1
0x1800030bf  jbe     short loc_1800030EB
0x1800030c1  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x1800030c8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800030ce  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x1800030d5  mov     rbx, rax
0x1800030d8  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800030de  dec     eax
0x1800030e0  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x1800030e5  jz      loc_180006F9C
0x1800030eb  mov     rcx, [rbp+arg_10]
0x1800030ef  lea     r8, ?sm_fSendCacheHeaders@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fSendCacheHeaders
0x1800030f6  xor     r9d, r9d
0x1800030f9  mov     [rsp+60h+var_40], rsi
0x1800030fe  lea     rdx, aSendcacheheade; "sendCacheHeaders"
0x180003105  mov     rax, [rcx]
0x180003108  mov     rax, [rax+48h]
0x18000310c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003111  mov     ebx, eax
0x180003113  test    eax, eax
0x180003115  js      loc_180007058
0x18000311b  cmp     cs:?sm_fSendCacheHeaders@HTTP_COMPRESSION@@0HA, esi; int HTTP_COMPRESSION::sm_fSendCacheHeaders
0x180003121  jnz     loc_180006FD4
0x180003127  mov     rcx, [rbp+arg_10]
0x18000312b  lea     r8, ?sm_fDoDiskSpaceLimiting@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fDoDiskSpaceLimiting
0x180003132  xor     r9d, r9d
0x180003135  mov     [rsp+60h+var_40], rsi
0x18000313a  lea     rdx, aDodiskspacelim; "doDiskSpaceLimiting"
0x180003141  mov     rax, [rcx]
0x180003144  mov     rax, [rax+48h]
0x180003148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000314d  mov     ebx, eax
0x18000314f  test    eax, eax
0x180003151  js      loc_180007058
0x180003157  cmp     cs:?sm_fDoDiskSpaceLimiting@HTTP_COMPRESSION@@0HA, esi; int HTTP_COMPRESSION::sm_fDoDiskSpaceLimiting
0x18000315d  jz      short loc_18000319E
0x18000315f  mov     rcx, [rbp+arg_10]
0x180003163  lea     r8, [rbp+arg_8]
0x180003167  mov     [rbp+arg_8], esi
0x18000316a  lea     rdx, aMaxdiskspaceus; "maxDiskSpaceUsage"
0x180003171  xor     r9d, r9d
0x180003174  mov     [rsp+60h+var_40], rsi
0x180003179  mov     rax, [rcx]
0x18000317c  mov     rax, [rax+30h]
0x180003180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003185  mov     ebx, eax
0x180003187  test    eax, eax
0x180003189  js      loc_180007058
0x18000318f  movsxd  rax, [rbp+arg_8]
0x180003193  shl     rax, 14h
0x180003197  mov     cs:?sm_dwMaxDiskSpaceUsage@HTTP_COMPRESSION@@0_KA, rax; unsigned __int64 HTTP_COMPRESSION::sm_dwMaxDiskSpaceUsage
0x18000319e  mov     rcx, [rbp+arg_10]
0x1800031a2  lea     r8, ?sm_fNoCompressionForHttp10@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fNoCompressionForHttp10
0x1800031a9  xor     r9d, r9d
0x1800031ac  mov     [rsp+60h+var_40], rsi
0x1800031b1  lea     rdx, aNocompressionf; "noCompressionForHttp10"
0x1800031b8  mov     rax, [rcx]
0x1800031bb  mov     rax, [rax+48h]
0x1800031bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031c4  mov     ebx, eax
0x1800031c6  test    eax, eax
0x1800031c8  js      loc_180007058
0x1800031ce  mov     rcx, [rbp+arg_10]
0x1800031d2  lea     r8, ?sm_fNoCompressionForProxies@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fNoCompressionForProxies
0x1800031d9  xor     r9d, r9d
0x1800031dc  mov     [rsp+60h+var_40], rsi
0x1800031e1  lea     rdx, aNocompressionf_0; "noCompressionForProxies"
0x1800031e8  mov     rax, [rcx]
0x1800031eb  mov     rax, [rax+48h]
0x1800031ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031f4  mov     ebx, eax
0x1800031f6  test    eax, eax
0x1800031f8  js      loc_180007058
0x1800031fe  mov     rcx, [rbp+arg_10]
0x180003202  lea     r8, ?sm_fNoCompressionForRange@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fNoCompressionForRange
0x180003209  xor     r9d, r9d
0x18000320c  mov     [rsp+60h+var_40], rsi
0x180003211  lea     rdx, aNocompressionf_1; "noCompressionForRange"
0x180003218  mov     rax, [rcx]
0x18000321b  mov     rax, [rax+48h]
0x18000321f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003224  mov     ebx, eax
0x180003226  test    eax, eax
0x180003228  js      loc_180007058
0x18000322e  mov     rcx, [rbp+arg_10]
0x180003232  lea     r8, ?sm_dwMinFileSizeForCompression@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwMinFileSizeForCompression
0x180003239  xor     r9d, r9d
0x18000323c  mov     [rsp+60h+var_40], rsi
0x180003241  lea     rdx, aMinfilesizefor; "minFileSizeForComp"
0x180003248  mov     rax, [rcx]
0x18000324b  mov     rax, [rax+30h]
0x18000324f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003254  mov     ebx, eax
0x180003256  test    eax, eax
0x180003258  js      loc_180007058
0x18000325e  mov     rcx, [rbp+arg_10]
0x180003262  lea     r8, ?sm_dwDynamicCompressionBufferLimit@HTTP_COMPRESSION@@0KA; ulong HTTP_COMPRESSION::sm_dwDynamicCompressionBufferLimit
0x180003269  xor     r9d, r9d
0x18000326c  mov     [rsp+60h+var_40], rsi
0x180003271  lea     rdx, aDynamiccompres; "dynamicCompressionBufferLimit"
0x180003278  mov     rax, [rcx]
0x18000327b  mov     rax, [rax+30h]
0x18000327f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003284  mov     ebx, eax
0x180003286  test    eax, eax
0x180003288  js      loc_180007058
0x18000328e  mov     rcx, [rbp+arg_10]
0x180003292  lea     r8, ?sm_dwStaticCompressionHighWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwStaticCompressionHighWaterMark
0x180003299  xor     r9d, r9d
0x18000329c  mov     [rsp+60h+var_40], rsi
0x1800032a1  lea     rdx, aStaticcompress_1; "staticCompressionDisableCpuUsage"
0x1800032a8  mov     rax, [rcx]
0x1800032ab  mov     rax, [rax+30h]
0x1800032af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032b4  mov     ebx, eax
0x1800032b6  test    eax, eax
0x1800032b8  js      loc_180007058
0x1800032be  mov     rcx, [rbp+arg_10]
0x1800032c2  lea     r8, ?sm_dwStaticCompressionLowWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwStaticCompressionLowWaterMark
0x1800032c9  xor     r9d, r9d
0x1800032cc  mov     [rsp+60h+var_40], rsi
0x1800032d1  lea     rdx, aStaticcompress_0; "staticCompressionEnableCpuUsage"
0x1800032d8  mov     rax, [rcx]
0x1800032db  mov     rax, [rax+30h]
0x1800032df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032e4  mov     ebx, eax
0x1800032e6  test    eax, eax
0x1800032e8  js      loc_180007058
0x1800032ee  mov     rcx, [rbp+arg_10]
0x1800032f2  lea     r8, ?sm_dwDynamicCompressionHighWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwDynamicCompressionHighWaterMark
0x1800032f9  xor     r9d, r9d
0x1800032fc  mov     [rsp+60h+var_40], rsi
0x180003301  lea     rdx, aDynamiccompres_2; "dynamicCompressionDisableCpuUsage"
0x180003308  mov     rax, [rcx]
0x18000330b  mov     rax, [rax+30h]
0x18000330f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003314  mov     ebx, eax
0x180003316  test    eax, eax
0x180003318  js      loc_180007058
0x18000331e  mov     rcx, [rbp+arg_10]
0x180003322  lea     r8, ?sm_dwDynamicCompressionLowWaterMark@HTTP_COMPRESSION@@0JA; long HTTP_COMPRESSION::sm_dwDynamicCompressionLowWaterMark
0x180003329  xor     r9d, r9d
0x18000332c  mov     [rsp+60h+var_40], rsi
0x180003331  lea     rdx, aDynamiccompres_0; "dynamicCompressionEnableCpuUsage"
0x180003338  mov     rax, [rcx]
0x18000333b  mov     rax, [rax+30h]
0x18000333f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003344  mov     ebx, eax
0x180003346  test    eax, eax
0x180003348  js      loc_180007058
0x18000334e  mov     rcx, [rbp+arg_10]
0x180003352  lea     r8, ?sm_fStaticCompressionIgnoreHitFrequency@HTTP_COMPRESSION@@0HA; int HTTP_COMPRESSION::sm_fStaticCompressionIgnoreHitFrequency
0x180003359  xor     r9d, r9d
0x18000335c  mov     [rsp+60h+var_40], rsi
0x180003361  lea     rdx, aStaticcompress_2; "staticCompressionIgnoreHitFrequency"
0x180003368  mov     rax, [rcx]
0x18000336b  mov     rax, [rax+48h]
0x18000336f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003374  mov     ebx, eax
0x180003376  test    eax, eax
0x180003378  js      loc_180007058
0x18000337e  mov     rcx, [rbp+arg_10]
0x180003382  mov     rax, [rcx]
0x180003385  mov     rax, [rax+10h]
0x180003389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000338e  mov     rcx, [rbp+arg_18]
0x180003392  mov     [rbp+arg_10], rsi
0x180003396  mov     rax, [rcx]
0x180003399  mov     rax, [rax+10h]
0x18000339d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033a2  xor     eax, eax
0x1800033a4  mov     rbx, [rsp+60h+arg_0]
0x1800033ac  add     rsp, 60h
0x1800033b0  pop     rdi
0x1800033b1  pop     rsi
0x1800033b2  pop     rbp
0x1800033b3  retn
0x180006f9c  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180006fa3  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180006fa9  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180006fb0  lea     edx, [rax-1]
0x180006fb3  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180006fb9  mov     rcx, cs:?sm_pstrCompressionDirectory@HTTP_COMPRESSION@@0PEAVSTRU@@EA; STRU * HTTP_COMPRESSION::sm_pstrCompressionDirectory
0x180006fc0  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x180006fc6  cmp     eax, 1
0x180006fc9  ja      loc_1800030C1
0x180006fcf  jmp     loc_1800030EB
0x180006fd4  mov     rcx, [rbp+arg_10]
0x180006fd8  lea     r8, [rbp+var_18]
0x180006fdc  xor     r9d, r9d
0x180006fdf  mov     [rsp+60h+var_40], rsi
0x180006fe4  lea     rdx, aCachecontrolhe; "cacheControlHeader"
0x180006feb  mov     rax, [rcx]
0x180006fee  mov     rax, [rax+40h]
0x180006ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ff7  mov     ebx, eax
0x180006ff9  test    eax, eax
0x180006ffb  js      short loc_180007058
0x180006ffd  mov     rdx, [rbp+var_18]
0x180007001  mov     rcx, cs:?sm_pstrCacheControlHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrCacheControlHeader
0x180007008  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000700e  mov     ebx, eax
0x180007010  test    eax, eax
0x180007012  js      short loc_180007058
0x180007014  mov     rcx, [rbp+arg_10]
0x180007018  lea     r8, [rbp+var_10]
0x18000701c  xor     r9d, r9d
0x18000701f  mov     [rsp+60h+var_40], rsi
0x180007024  lea     rdx, aExpiresheader; "expiresHeader"
0x18000702b  mov     rax, [rcx]
0x18000702e  mov     rax, [rax+40h]
0x180007032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007037  mov     ebx, eax
0x180007039  test    eax, eax
0x18000703b  js      short loc_180007058
0x18000703d  mov     rdx, [rbp+var_10]
0x180007041  mov     rcx, cs:?sm_pstrExpiresHeader@HTTP_COMPRESSION@@0PEAVSTRA@@EA; STRA * HTTP_COMPRESSION::sm_pstrExpiresHeader
0x180007048  call    cs:__imp_?CopyW@STRA@@QEAAJPEBG@Z; STRA::CopyW(ushort const *)
0x18000704e  mov     ebx, eax
0x180007050  test    eax, eax
0x180007052  jns     loc_180003127
0x180007058  mov     rcx, [rbp+arg_10]
0x18000705c  test    rcx, rcx
0x18000705f  jz      short loc_180007071
0x180007061  mov     rax, [rcx]
0x180007064  mov     rax, [rax+10h]
0x180007068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000706d  mov     [rbp+arg_10], rsi
0x180007071  mov     rcx, [rbp+arg_18]
0x180007075  test    rcx, rcx
0x180007078  jz      short loc_180007086
0x18000707a  mov     rax, [rcx]
0x18000707d  mov     rax, [rax+10h]
0x180007081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007086  mov     eax, ebx
0x180007088  jmp     loc_1800033A4
```
