# W3_METADATA::Initialize(ushort const *,INativeConfigurationElement *,char const *,ushort,INativeSectionException * *,STRU *,IHttpTraceContext *)

- ea: `0x180032c80`
- end: `0x1800331b0`
- name: `?Initialize@W3_METADATA@@QEAAJPEBGPEAVINativeConfigurationElement@@PEBDGPEAPEAVINativeSectionException@@PEAVSTRU@@PEAVIHttpTraceContext@@@Z`
- size: `1328`
- prototype: `__int64 __fastcall(W3_METADATA *this, const unsigned __int16 *, struct INativeConfigurationElement *, const char *, unsigned __int16, struct INativeSectionException **, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c780`
- `0x18001cab0`

## callees

- `0x180032c80`
- `0x1800331b8`
- `0x180036e10`
- `0x18003775e`
- `0x180038010`

## import_xrefs

- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180033147`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18003315f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180033180`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180033147`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18003315f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180033180`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180033135`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180033135`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180032cd4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180032d92`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800330a5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180032cd4`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180032d92`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800330a5`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180033171`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x180033171`

## string_xrefs

- `0x180032dbb`: `uploadReadAheadSize`
- `0x180032ed6`: `system.webServer/security/access`
- `0x180032fdb`: `accessPolicy`
- `0x180033079`: `physicalPath`

## pseudocode

```c
__int64 __fastcall W3_METADATA::Initialize(
        W3_METADATA *this,
        const unsigned __int16 *a2,
        struct INativeConfigurationElement *a3,
        const char *a4,
        unsigned __int16 a5,
        struct INativeSectionException **a6,
        struct STRU *a7,
        struct IHttpTraceContext *a8)
{
  int v12; // ebx
  struct INativeSectionException **v13; // r14
  __int64 v14; // rcx
  BOOL v15; // esi
  W3_SERVER *v16; // r9
  struct IHttpTraceContext *v17; // r14
  struct INativeConfigurationElement *v18; // rdx
  __int64 v19; // rax
  unsigned __int16 *Str; // rbx
  unsigned int CCH; // eax
  __int64 v23; // [rsp+50h] [rbp-51h] BYREF
  struct INativeConfigurationElement *v24; // [rsp+58h] [rbp-49h] BYREF
  __int64 v25; // [rsp+60h] [rbp-41h] BYREF
  __int64 v26; // [rsp+68h] [rbp-39h] BYREF
  int v27; // [rsp+70h] [rbp-31h] BYREF
  const unsigned __int16 *v28; // [rsp+78h] [rbp-29h] BYREF
  __int64 v29; // [rsp+80h] [rbp-21h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-19h] BYREF
  const unsigned __int16 *v31; // [rsp+90h] [rbp-11h] BYREF
  int v32; // [rsp+F0h] [rbp+4Fh] BYREF

  v23 = 0;
  v24 = 0;
  v26 = 0;
  v25 = 0;
  String1 = 0;
  v28 = 0;
  v29 = 0;
  v27 = 0;
  v32 = 0;
  v31 = 0;
  v12 = STRU::Copy((W3_METADATA *)((char *)this + 24), a2);
  if ( v12 >= 0 )
  {
    v13 = a6;
    v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const unsigned __int16 *, __int64 *, struct INativeSectionException **, _QWORD))(**((_QWORD **)g_pW3Server + 187) + 24LL))(
            *((_QWORD *)g_pW3Server + 187),
            L"system.webServer/serverRuntime",
            a2,
            &v23,
            a6,
            0);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v23 + 48LL))(
              v23,
              L"maxRequestEntityAllowed",
              (char *)this + 232,
              0,
              0);
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v23 + 64LL))(
                v23,
                L"alternateHostName",
                &v28,
                0,
                0);
        if ( v12 >= 0 )
        {
          v12 = STRU::Copy((W3_METADATA *)((char *)this + 176), v28);
          if ( v12 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v23 + 48LL))(
                    v23,
                    L"uploadReadAheadSize",
                    (char *)this + 304,
                    0,
                    0);
            if ( v12 >= 0 )
            {
              v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v23 + 72LL))(
                      v23,
                      L"enableNagling",
                      (char *)this + 308,
                      0,
                      0);
              if ( v12 >= 0 )
              {
                v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v23 + 48LL))(
                        v23,
                        L"frequentHitThreshold",
                        (char *)this + 312,
                        0,
                        0);
                if ( v12 >= 0 )
                {
                  v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v23 + 80LL))(
                          v23,
                          L"frequentHitTimePeriod",
                          &v29,
                          0,
                          0);
                  if ( v12 >= 0 )
                  {
                    v14 = v23;
                    *((_DWORD *)this + 80) = (int)v29 / 10000;
                    v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v14 + 48LL))(
                            v14,
                            L"authenticatedUserOverride",
                            (char *)this + 316,
                            0,
                            0);
                    if ( v12 >= 0 )
                    {
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                      v23 = 0;
                      v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const unsigned __int16 *, __int64 *, struct INativeSectionException **, _QWORD))(**((_QWORD **)g_pW3Server + 187) + 24LL))(
                              *((_QWORD *)g_pW3Server + 187),
                              L"system.webServer/security/access",
                              a2,
                              &v26,
                              v13,
                              0);
                      if ( v12 >= 0 )
                      {
                        v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v26 + 48LL))(
                                v26,
                                L"sslFlags",
                                &v32,
                                0,
                                0);
                        if ( v12 >= 0 )
                        {
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
                          v26 = 0;
                          v12 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, const unsigned __int16 *, struct INativeConfigurationElement **, struct INativeSectionException **, __int64 *))(**((_QWORD **)g_pW3Server + 187) + 24LL))(
                                  *((_QWORD *)g_pW3Server + 187),
                                  L"system.webServer/handlers",
                                  a2,
                                  &v24,
                                  v13,
                                  &v25);
                          if ( v12 >= 0 )
                          {
                            v12 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v25 + 24LL))(
                                    v25,
                                    &String1);
                            if ( v12 >= 0 )
                            {
                              v15 = wcscmp_0(String1, L"MACHINE/WEBROOT/APPHOST") == 0;
                              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
                              v25 = 0;
                              v12 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, int *, _QWORD))(*(_QWORD *)v24 + 48LL))(
                                      v24,
                                      L"accessPolicy",
                                      &v27,
                                      0);
                              if ( v12 >= 0 )
                              {
                                v16 = g_pW3Server;
                                v17 = a8;
                                v18 = v24;
                                *((_DWORD *)this + 59) = v27 | v32;
                                v12 = META_SCRIPT_MAP::Initialize(
                                        (W3_METADATA *)((char *)this + 160),
                                        v18,
                                        v15,
                                        v16,
                                        0,
                                        *((struct LANG_STRING **)v16 + 194),
                                        a4,
                                        a5,
                                        a7,
                                        v17);
                                if ( v12 >= 0 )
                                {
                                  (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v24 + 16LL))(v24);
                                  v19 = *(_QWORD *)a3;
                                  v24 = 0;
                                  v12 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(v19 + 64))(
                                          a3,
                                          L"physicalPath",
                                          &v31,
                                          0,
                                          0);
                                  if ( v12 >= 0 )
                                  {
                                    v12 = STRU::Copy((W3_METADATA *)((char *)this + 240), v31);
                                    if ( v12 >= 0 )
                                    {
                                      while ( STRU::QueryCCH((W3_METADATA *)((char *)this + 240)) > 3 )
                                      {
                                        Str = STRU::QueryStr((W3_METADATA *)((char *)this + 240));
                                        if ( Str[STRU::QueryCCH((W3_METADATA *)((char *)this + 240)) - 1] != 92 )
                                          break;
                                        CCH = STRU::QueryCCH((W3_METADATA *)((char *)this + 240));
                                        STRU::SetLen((W3_METADATA *)((char *)this + 240), CCH - 1);
                                      }
                                      v12 = W3_METADATA::InitializeVirtualDirectoryUser(this, a3, v17);
                                      if ( v12 >= 0 )
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
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v24 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180032c80  push    rbp
0x180032c82  push    rbx
0x180032c83  push    rsi
0x180032c84  push    rdi
0x180032c85  push    r12
0x180032c87  push    r13
0x180032c89  push    r14
0x180032c8b  push    r15
0x180032c8d  lea     rbp, [rsp-7]
0x180032c92  sub     rsp, 0A8h
0x180032c99  xor     r13d, r13d
0x180032c9c  mov     rdi, rcx
0x180032c9f  add     rcx, 18h
0x180032ca3  mov     [rbp+3Fh+var_90], r13
0x180032ca7  mov     [rbp+3Fh+var_88], r13
0x180032cab  mov     r12, r9
0x180032cae  mov     [rbp+3Fh+var_78], r13
0x180032cb2  mov     r15, r8
0x180032cb5  mov     [rbp+3Fh+var_80], r13
0x180032cb9  mov     rsi, rdx
0x180032cbc  mov     [rbp+3Fh+String1], r13
0x180032cc0  mov     [rbp+3Fh+var_68], r13
0x180032cc4  mov     [rbp+3Fh+var_60], r13
0x180032cc8  mov     [rbp+3Fh+var_70], r13d
0x180032ccc  mov     [rbp+3Fh+arg_0], r13d
0x180032cd0  mov     [rbp+3Fh+var_50], r13
0x180032cd4  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180032cdb  nop     dword ptr [rax+rax+00h]
0x180032ce0  mov     ebx, eax
0x180032ce2  test    eax, eax
0x180032ce4  js      loc_1800330BB
0x180032cea  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180032cf1  lea     r9, [rbp+3Fh+var_90]
0x180032cf5  mov     r14, [rbp+3Fh+arg_28]
0x180032cf9  lea     rdx, aSystemWebserve_4; "system.webServer/serverRuntime"
0x180032d00  mov     [rsp+0E0h+var_B8], r13
0x180032d05  mov     r8, rsi
0x180032d08  mov     qword ptr [rsp+0E0h+var_C0], r14
0x180032d0d  mov     rcx, [rax+5D8h]
0x180032d14  mov     rax, [rcx]
0x180032d17  mov     rax, [rax+18h]
0x180032d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d20  mov     ebx, eax
0x180032d22  test    eax, eax
0x180032d24  js      loc_1800330BB
0x180032d2a  mov     rcx, [rbp+3Fh+var_90]
0x180032d2e  lea     r8, [rdi+0E8h]
0x180032d35  xor     r9d, r9d
0x180032d38  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180032d3d  lea     rdx, aMaxrequestenti; "maxRequestEntityAllowed"
0x180032d44  mov     rax, [rcx]
0x180032d47  mov     rax, [rax+30h]
0x180032d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d50  mov     ebx, eax
0x180032d52  test    eax, eax
0x180032d54  js      loc_1800330BB
0x180032d5a  mov     rcx, [rbp+3Fh+var_90]
0x180032d5e  lea     r8, [rbp+3Fh+var_68]
0x180032d62  xor     r9d, r9d
0x180032d65  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180032d6a  lea     rdx, aAlternatehostn; "alternateHostName"
0x180032d71  mov     rax, [rcx]
0x180032d74  mov     rax, [rax+40h]
0x180032d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d7d  mov     ebx, eax
0x180032d7f  test    eax, eax
0x180032d81  js      loc_1800330BB
0x180032d87  mov     rdx, [rbp+3Fh+var_68]
0x180032d8b  lea     rcx, [rdi+0B0h]
0x180032d92  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180032d99  nop     dword ptr [rax+rax+00h]
0x180032d9e  mov     ebx, eax
0x180032da0  test    eax, eax
0x180032da2  js      loc_1800330BB
0x180032da8  mov     rcx, [rbp+3Fh+var_90]
0x180032dac  lea     r8, [rdi+130h]
0x180032db3  xor     r9d, r9d
0x180032db6  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180032dbb  lea     rdx, aUploadreadahea; "uploadReadAheadSize"
0x180032dc2  mov     rax, [rcx]
0x180032dc5  mov     rax, [rax+30h]
0x180032dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dce  mov     ebx, eax
0x180032dd0  test    eax, eax
0x180032dd2  js      loc_1800330BB
0x180032dd8  mov     rcx, [rbp+3Fh+var_90]
0x180032ddc  lea     r8, [rdi+134h]
0x180032de3  xor     r9d, r9d
0x180032de6  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180032deb  lea     rdx, aEnablenagling; "enableNagling"
0x180032df2  mov     rax, [rcx]
0x180032df5  mov     rax, [rax+48h]
0x180032df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dfe  mov     ebx, eax
0x180032e00  test    eax, eax
0x180032e02  js      loc_1800330BB
0x180032e08  mov     rcx, [rbp+3Fh+var_90]
0x180032e0c  lea     r8, [rdi+138h]
0x180032e13  xor     r9d, r9d
0x180032e16  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180032e1b  lea     rdx, aFrequenthitthr; "frequentHitThreshold"
0x180032e22  mov     rax, [rcx]
0x180032e25  mov     rax, [rax+30h]
0x180032e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e2e  mov     ebx, eax
0x180032e30  test    eax, eax
0x180032e32  js      loc_1800330BB
0x180032e38  mov     rcx, [rbp+3Fh+var_90]
0x180032e3c  lea     r8, [rbp+3Fh+var_60]
0x180032e40  xor     r9d, r9d
0x180032e43  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180032e48  lea     rdx, aFrequenthittim; "frequentHitTimePeriod"
0x180032e4f  mov     rax, [rcx]
0x180032e52  mov     rax, [rax+50h]
0x180032e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e5b  mov     ebx, eax
0x180032e5d  test    eax, eax
0x180032e5f  js      loc_1800330BB
0x180032e65  mov     rcx, [rbp+3Fh+var_90]
0x180032e69  lea     r8, [rdi+13Ch]
0x180032e70  mov     rax, 346DC5D63886594Bh
0x180032e7a  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180032e7f  imul    [rbp+3Fh+var_60]
0x180032e83  xor     r9d, r9d
0x180032e86  sar     rdx, 0Bh
0x180032e8a  mov     rax, rdx
0x180032e8d  shr     rax, 3Fh
0x180032e91  add     rdx, rax
0x180032e94  mov     [rdi+140h], edx
0x180032e9a  lea     rdx, aAuthenticatedu; "authenticatedUserOverride"
0x180032ea1  mov     rax, [rcx]
0x180032ea4  mov     rax, [rax+30h]
0x180032ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ead  mov     ebx, eax
0x180032eaf  test    eax, eax
0x180032eb1  js      loc_1800330BB
0x180032eb7  mov     rcx, [rbp+3Fh+var_90]
0x180032ebb  mov     rax, [rcx]
0x180032ebe  mov     rax, [rax+10h]
0x180032ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ec7  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180032ece  lea     r9, [rbp+3Fh+var_78]
0x180032ed2  mov     [rbp+3Fh+var_90], r13
0x180032ed6  lea     rdx, aSystemWebserve; "system.webServer/security/access"
0x180032edd  mov     [rsp+0E0h+var_B8], r13
0x180032ee2  mov     r8, rsi
0x180032ee5  mov     qword ptr [rsp+0E0h+var_C0], r14
0x180032eea  mov     rcx, [rax+5D8h]
0x180032ef1  mov     rax, [rcx]
0x180032ef4  mov     rax, [rax+18h]
0x180032ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032efd  mov     ebx, eax
0x180032eff  test    eax, eax
0x180032f01  js      loc_1800330BB
0x180032f07  mov     rcx, [rbp+3Fh+var_78]
0x180032f0b  lea     r8, [rbp+3Fh+arg_0]
0x180032f0f  xor     r9d, r9d
0x180032f12  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180032f17  lea     rdx, aSslflags; "sslFlags"
0x180032f1e  mov     rax, [rcx]
0x180032f21  mov     rax, [rax+30h]
0x180032f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f2a  mov     ebx, eax
0x180032f2c  test    eax, eax
0x180032f2e  js      loc_1800330BB
0x180032f34  mov     rcx, [rbp+3Fh+var_78]
0x180032f38  mov     rax, [rcx]
0x180032f3b  mov     rax, [rax+10h]
0x180032f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f44  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180032f4b  lea     rdx, [rbp+3Fh+var_80]
0x180032f4f  mov     [rbp+3Fh+var_78], r13
0x180032f53  lea     r9, [rbp+3Fh+var_88]
0x180032f57  mov     [rsp+0E0h+var_B8], rdx
0x180032f5c  mov     r8, rsi
0x180032f5f  lea     rdx, aSystemWebserve_3; "system.webServer/handlers"
0x180032f66  mov     qword ptr [rsp+0E0h+var_C0], r14
0x180032f6b  mov     rcx, [rax+5D8h]
0x180032f72  mov     rax, [rcx]
0x180032f75  mov     rax, [rax+18h]
0x180032f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f7e  mov     ebx, eax
0x180032f80  test    eax, eax
0x180032f82  js      loc_1800330BB
0x180032f88  mov     rcx, [rbp+3Fh+var_80]
0x180032f8c  lea     rdx, [rbp+3Fh+String1]
0x180032f90  mov     rax, [rcx]
0x180032f93  mov     rax, [rax+18h]
0x180032f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f9c  mov     ebx, eax
0x180032f9e  test    eax, eax
0x180032fa0  js      loc_1800330BB
0x180032fa6  mov     rcx, [rbp+3Fh+String1]; String1
0x180032faa  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180032fb1  call    wcscmp_0
0x180032fb6  mov     rcx, [rbp+3Fh+var_80]
0x180032fba  test    eax, eax
0x180032fbc  mov     esi, r13d
0x180032fbf  setz    sil
0x180032fc3  mov     rax, [rcx]
0x180032fc6  mov     rax, [rax+10h]
0x180032fca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032fcf  mov     rcx, [rbp+3Fh+var_88]
0x180032fd3  lea     r8, [rbp+3Fh+var_70]
0x180032fd7  mov     [rbp+3Fh+var_80], r13
0x180032fdb  lea     rdx, aAccesspolicy; "accessPolicy"
0x180032fe2  xor     r9d, r9d
0x180032fe5  mov     qword ptr [rsp+0E0h+var_C0], r13; int
0x180032fea  mov     rax, [rcx]
0x180032fed  mov     rax, [rax+30h]
0x180032ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ff6  mov     ebx, eax
0x180032ff8  test    eax, eax
0x180032ffa  js      loc_1800330BB
0x180033000  mov     eax, [rbp+3Fh+arg_0]
0x180033003  lea     rcx, [rdi+0A0h]; this
0x18003300a  or      eax, [rbp+3Fh+var_70]
0x18003300d  mov     r8d, esi; int
0x180033010  mov     r9, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; struct IHttpServer *
0x180033017  mov     r14, [rbp+3Fh+arg_38]
0x18003301e  mov     rdx, [rbp+3Fh+var_88]; struct INativeConfigurationElement *
0x180033022  mov     [rdi+0ECh], eax
0x180033028  mov     rax, [rbp+3Fh+arg_30]
0x18003302c  mov     [rsp+0E0h+var_98], r14; struct IHttpTraceContext *
0x180033031  mov     [rsp+0E0h+var_A0], rax; struct STRU *
0x180033036  movzx   eax, [rbp+3Fh+arg_20]
0x18003303a  mov     [rsp+0E0h+var_A8], ax; unsigned __int16
0x18003303f  mov     rax, [r9+610h]
0x180033046  mov     [rsp+0E0h+var_B0], r12; char *
0x18003304b  mov     [rsp+0E0h+var_B8], rax; struct LANG_STRING *
0x180033050  call    ?Initialize@META_SCRIPT_MAP@@QEAAJPEAVINativeConfigurationElement@@HPEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z; META_SCRIPT_MAP::Initialize(INativeConfigurationElement *,int,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)
0x180033055  mov     ebx, eax
0x180033057  test    eax, eax
0x180033059  js      short loc_1800330BB
0x18003305b  mov     rcx, [rbp+3Fh+var_88]
0x18003305f  mov     rax, [rcx]
0x180033062  mov     rax, [rax+10h]
0x180033066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003306b  mov     rax, [r15]
0x18003306e  lea     r8, [rbp+3Fh+var_50]
0x180033072  xor     r9d, r9d
0x180033075  mov     [rbp+3Fh+var_88], r13
0x180033079  lea     rdx, aPhysicalpath_0; "physicalPath"
0x180033080  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180033085  mov     rcx, r15
0x180033088  mov     rax, [rax+40h]
0x18003308c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033091  mov     ebx, eax
0x180033093  test    eax, eax
0x180033095  js      short loc_1800330BB
0x180033097  mov     rdx, [rbp+3Fh+var_50]
0x18003309b  lea     rsi, [rdi+0F0h]
0x1800330a2  mov     rcx, rsi
0x1800330a5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800330ac  nop     dword ptr [rax+rax+00h]
0x1800330b1  mov     ebx, eax
0x1800330b3  test    eax, eax
0x1800330b5  jns     loc_18003317D
0x1800330bb  mov     rcx, [rbp+3Fh+var_80]
0x1800330bf  test    rcx, rcx
0x1800330c2  jz      short loc_1800330D4
0x1800330c4  mov     rax, [rcx]
0x1800330c7  mov     rax, [rax+10h]
0x1800330cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330d0  mov     [rbp+3Fh+var_80], r13
0x1800330d4  mov     rcx, [rbp+3Fh+var_88]
0x1800330d8  test    rcx, rcx
0x1800330db  jz      short loc_1800330ED
0x1800330dd  mov     rax, [rcx]
0x1800330e0  mov     rax, [rax+10h]
0x1800330e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330e9  mov     [rbp+3Fh+var_88], r13
0x1800330ed  mov     rcx, [rbp+3Fh+var_78]
0x1800330f1  test    rcx, rcx
0x1800330f4  jz      short loc_180033106
0x1800330f6  mov     rax, [rcx]
0x1800330f9  mov     rax, [rax+10h]
0x1800330fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033102  mov     [rbp+3Fh+var_78], r13
0x180033106  mov     rcx, [rbp+3Fh+var_90]
0x18003310a  test    rcx, rcx
0x18003310d  jz      short loc_18003311B
0x18003310f  mov     rax, [rcx]
0x180033112  mov     rax, [rax+10h]
0x180033116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003311b  mov     eax, ebx
0x18003311d  add     rsp, 0A8h
0x180033124  pop     r15
0x180033126  pop     r14
0x180033128  pop     r13
0x18003312a  pop     r12
0x18003312c  pop     rdi
0x18003312d  pop     rsi
0x18003312e  pop     rbx
0x18003312f  pop     rbp
0x180033130  retn
0x180033132  mov     rcx, rsi
0x180033135  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18003313c  nop     dword ptr [rax+rax+00h]
0x180033141  mov     rcx, rsi
  ... truncated ...
```
