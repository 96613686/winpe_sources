# W3_METADATA::Initialize(ushort const *,INativeConfigurationElement *,char const *,ushort,INativeSectionException * *,STRU *,IHttpTraceContext *)

- ea: `0x180030010`
- end: `0x18003050c`
- name: `?Initialize@W3_METADATA@@QEAAJPEBGPEAVINativeConfigurationElement@@PEBDGPEAPEAVINativeSectionException@@PEAVSTRU@@PEAVIHttpTraceContext@@@Z`
- size: `1276`
- prototype: `__int64 __usercall@<rax>(W3_METADATA *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, struct INativeConfigurationElement *@<r8>, const char *@<r9>, unsigned __int16, struct INativeSectionException **, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b920`
- `0x18001b330`

## callees

- `0x180030010`
- `0x180030514`
- `0x180033a40`
- `0x1800343be`
- `0x180035010`

## import_xrefs

- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800304be`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800304d0`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800304e5`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800304be`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800304d0`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x1800304e5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800304b2`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800304b2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180030064`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003011c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180030429`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180030064`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18003011c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180030429`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800304dc`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800304dc`

## string_xrefs

- `0x18003013f`: `uploadReadAheadSize`
- `0x18003025a`: `system.webServer/security/access`
- `0x18003035f`: `accessPolicy`
- `0x1800303fd`: `physicalPath`

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
0x180030010  push    rbp
0x180030012  push    rbx
0x180030013  push    rsi
0x180030014  push    rdi
0x180030015  push    r12
0x180030017  push    r13
0x180030019  push    r14
0x18003001b  push    r15
0x18003001d  lea     rbp, [rsp-7]
0x180030022  sub     rsp, 0A8h
0x180030029  xor     r13d, r13d
0x18003002c  mov     rdi, rcx
0x18003002f  add     rcx, 18h
0x180030033  mov     [rbp+3Fh+var_90], r13
0x180030037  mov     [rbp+3Fh+var_88], r13
0x18003003b  mov     r12, r9
0x18003003e  mov     [rbp+3Fh+var_78], r13
0x180030042  mov     r15, r8
0x180030045  mov     [rbp+3Fh+var_80], r13
0x180030049  mov     rsi, rdx
0x18003004c  mov     [rbp+3Fh+String1], r13
0x180030050  mov     [rbp+3Fh+var_68], r13
0x180030054  mov     [rbp+3Fh+var_60], r13
0x180030058  mov     [rbp+3Fh+var_70], r13d
0x18003005c  mov     [rbp+3Fh+arg_0], r13d
0x180030060  mov     [rbp+3Fh+var_50], r13
0x180030064  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003006a  mov     ebx, eax
0x18003006c  test    eax, eax
0x18003006e  js      loc_180030439
0x180030074  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18003007b  lea     r9, [rbp+3Fh+var_90]
0x18003007f  mov     r14, [rbp+3Fh+arg_28]
0x180030083  lea     rdx, aSystemWebserve_4; "system.webServer/serverRuntime"
0x18003008a  mov     [rsp+0E0h+var_B8], r13
0x18003008f  mov     r8, rsi
0x180030092  mov     qword ptr [rsp+0E0h+var_C0], r14
0x180030097  mov     rcx, [rax+5D8h]
0x18003009e  mov     rax, [rcx]
0x1800300a1  mov     rax, [rax+18h]
0x1800300a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300aa  mov     ebx, eax
0x1800300ac  test    eax, eax
0x1800300ae  js      loc_180030439
0x1800300b4  mov     rcx, [rbp+3Fh+var_90]
0x1800300b8  lea     r8, [rdi+0E8h]
0x1800300bf  xor     r9d, r9d
0x1800300c2  mov     qword ptr [rsp+0E0h+var_C0], r13
0x1800300c7  lea     rdx, aMaxrequestenti; "maxRequestEntityAllowed"
0x1800300ce  mov     rax, [rcx]
0x1800300d1  mov     rax, [rax+30h]
0x1800300d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300da  mov     ebx, eax
0x1800300dc  test    eax, eax
0x1800300de  js      loc_180030439
0x1800300e4  mov     rcx, [rbp+3Fh+var_90]
0x1800300e8  lea     r8, [rbp+3Fh+var_68]
0x1800300ec  xor     r9d, r9d
0x1800300ef  mov     qword ptr [rsp+0E0h+var_C0], r13
0x1800300f4  lea     rdx, aAlternatehostn; "alternateHostName"
0x1800300fb  mov     rax, [rcx]
0x1800300fe  mov     rax, [rax+40h]
0x180030102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030107  mov     ebx, eax
0x180030109  test    eax, eax
0x18003010b  js      loc_180030439
0x180030111  mov     rdx, [rbp+3Fh+var_68]
0x180030115  lea     rcx, [rdi+0B0h]
0x18003011c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180030122  mov     ebx, eax
0x180030124  test    eax, eax
0x180030126  js      loc_180030439
0x18003012c  mov     rcx, [rbp+3Fh+var_90]
0x180030130  lea     r8, [rdi+130h]
0x180030137  xor     r9d, r9d
0x18003013a  mov     qword ptr [rsp+0E0h+var_C0], r13
0x18003013f  lea     rdx, aUploadreadahea; "uploadReadAheadSize"
0x180030146  mov     rax, [rcx]
0x180030149  mov     rax, [rax+30h]
0x18003014d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030152  mov     ebx, eax
0x180030154  test    eax, eax
0x180030156  js      loc_180030439
0x18003015c  mov     rcx, [rbp+3Fh+var_90]
0x180030160  lea     r8, [rdi+134h]
0x180030167  xor     r9d, r9d
0x18003016a  mov     qword ptr [rsp+0E0h+var_C0], r13
0x18003016f  lea     rdx, aEnablenagling; "enableNagling"
0x180030176  mov     rax, [rcx]
0x180030179  mov     rax, [rax+48h]
0x18003017d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030182  mov     ebx, eax
0x180030184  test    eax, eax
0x180030186  js      loc_180030439
0x18003018c  mov     rcx, [rbp+3Fh+var_90]
0x180030190  lea     r8, [rdi+138h]
0x180030197  xor     r9d, r9d
0x18003019a  mov     qword ptr [rsp+0E0h+var_C0], r13
0x18003019f  lea     rdx, aFrequenthitthr; "frequentHitThreshold"
0x1800301a6  mov     rax, [rcx]
0x1800301a9  mov     rax, [rax+30h]
0x1800301ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301b2  mov     ebx, eax
0x1800301b4  test    eax, eax
0x1800301b6  js      loc_180030439
0x1800301bc  mov     rcx, [rbp+3Fh+var_90]
0x1800301c0  lea     r8, [rbp+3Fh+var_60]
0x1800301c4  xor     r9d, r9d
0x1800301c7  mov     qword ptr [rsp+0E0h+var_C0], r13
0x1800301cc  lea     rdx, aFrequenthittim; "frequentHitTimePeriod"
0x1800301d3  mov     rax, [rcx]
0x1800301d6  mov     rax, [rax+50h]
0x1800301da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301df  mov     ebx, eax
0x1800301e1  test    eax, eax
0x1800301e3  js      loc_180030439
0x1800301e9  mov     rcx, [rbp+3Fh+var_90]
0x1800301ed  lea     r8, [rdi+13Ch]
0x1800301f4  mov     rax, 346DC5D63886594Bh
0x1800301fe  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180030203  imul    [rbp+3Fh+var_60]
0x180030207  xor     r9d, r9d
0x18003020a  sar     rdx, 0Bh
0x18003020e  mov     rax, rdx
0x180030211  shr     rax, 3Fh
0x180030215  add     rdx, rax
0x180030218  mov     [rdi+140h], edx
0x18003021e  lea     rdx, aAuthenticatedu; "authenticatedUserOverride"
0x180030225  mov     rax, [rcx]
0x180030228  mov     rax, [rax+30h]
0x18003022c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030231  mov     ebx, eax
0x180030233  test    eax, eax
0x180030235  js      loc_180030439
0x18003023b  mov     rcx, [rbp+3Fh+var_90]
0x18003023f  mov     rax, [rcx]
0x180030242  mov     rax, [rax+10h]
0x180030246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003024b  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180030252  lea     r9, [rbp+3Fh+var_78]
0x180030256  mov     [rbp+3Fh+var_90], r13
0x18003025a  lea     rdx, aSystemWebserve; "system.webServer/security/access"
0x180030261  mov     [rsp+0E0h+var_B8], r13
0x180030266  mov     r8, rsi
0x180030269  mov     qword ptr [rsp+0E0h+var_C0], r14
0x18003026e  mov     rcx, [rax+5D8h]
0x180030275  mov     rax, [rcx]
0x180030278  mov     rax, [rax+18h]
0x18003027c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030281  mov     ebx, eax
0x180030283  test    eax, eax
0x180030285  js      loc_180030439
0x18003028b  mov     rcx, [rbp+3Fh+var_78]
0x18003028f  lea     r8, [rbp+3Fh+arg_0]
0x180030293  xor     r9d, r9d
0x180030296  mov     qword ptr [rsp+0E0h+var_C0], r13
0x18003029b  lea     rdx, aSslflags; "sslFlags"
0x1800302a2  mov     rax, [rcx]
0x1800302a5  mov     rax, [rax+30h]
0x1800302a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302ae  mov     ebx, eax
0x1800302b0  test    eax, eax
0x1800302b2  js      loc_180030439
0x1800302b8  mov     rcx, [rbp+3Fh+var_78]
0x1800302bc  mov     rax, [rcx]
0x1800302bf  mov     rax, [rax+10h]
0x1800302c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302c8  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800302cf  lea     rdx, [rbp+3Fh+var_80]
0x1800302d3  mov     [rbp+3Fh+var_78], r13
0x1800302d7  lea     r9, [rbp+3Fh+var_88]
0x1800302db  mov     [rsp+0E0h+var_B8], rdx
0x1800302e0  mov     r8, rsi
0x1800302e3  lea     rdx, aSystemWebserve_3; "system.webServer/handlers"
0x1800302ea  mov     qword ptr [rsp+0E0h+var_C0], r14
0x1800302ef  mov     rcx, [rax+5D8h]
0x1800302f6  mov     rax, [rcx]
0x1800302f9  mov     rax, [rax+18h]
0x1800302fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030302  mov     ebx, eax
0x180030304  test    eax, eax
0x180030306  js      loc_180030439
0x18003030c  mov     rcx, [rbp+3Fh+var_80]
0x180030310  lea     rdx, [rbp+3Fh+String1]
0x180030314  mov     rax, [rcx]
0x180030317  mov     rax, [rax+18h]
0x18003031b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030320  mov     ebx, eax
0x180030322  test    eax, eax
0x180030324  js      loc_180030439
0x18003032a  mov     rcx, [rbp+3Fh+String1]; String1
0x18003032e  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180030335  call    wcscmp_0
0x18003033a  mov     rcx, [rbp+3Fh+var_80]
0x18003033e  test    eax, eax
0x180030340  mov     esi, r13d
0x180030343  setz    sil
0x180030347  mov     rax, [rcx]
0x18003034a  mov     rax, [rax+10h]
0x18003034e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030353  mov     rcx, [rbp+3Fh+var_88]
0x180030357  lea     r8, [rbp+3Fh+var_70]
0x18003035b  mov     [rbp+3Fh+var_80], r13
0x18003035f  lea     rdx, aAccesspolicy; "accessPolicy"
0x180030366  xor     r9d, r9d
0x180030369  mov     qword ptr [rsp+0E0h+var_C0], r13; int
0x18003036e  mov     rax, [rcx]
0x180030371  mov     rax, [rax+30h]
0x180030375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003037a  mov     ebx, eax
0x18003037c  test    eax, eax
0x18003037e  js      loc_180030439
0x180030384  mov     eax, [rbp+3Fh+arg_0]
0x180030387  lea     rcx, [rdi+0A0h]; this
0x18003038e  or      eax, [rbp+3Fh+var_70]
0x180030391  mov     r8d, esi; int
0x180030394  mov     r9, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; struct IHttpServer *
0x18003039b  mov     r14, [rbp+3Fh+arg_38]
0x1800303a2  mov     rdx, [rbp+3Fh+var_88]; struct INativeConfigurationElement *
0x1800303a6  mov     [rdi+0ECh], eax
0x1800303ac  mov     rax, [rbp+3Fh+arg_30]
0x1800303b0  mov     [rsp+0E0h+var_98], r14; struct IHttpTraceContext *
0x1800303b5  mov     [rsp+0E0h+var_A0], rax; struct STRU *
0x1800303ba  movzx   eax, [rbp+3Fh+arg_20]
0x1800303be  mov     [rsp+0E0h+var_A8], ax; unsigned __int16
0x1800303c3  mov     rax, [r9+610h]
0x1800303ca  mov     [rsp+0E0h+var_B0], r12; char *
0x1800303cf  mov     [rsp+0E0h+var_B8], rax; struct LANG_STRING *
0x1800303d4  call    ?Initialize@META_SCRIPT_MAP@@QEAAJPEAVINativeConfigurationElement@@HPEAVIHttpServer@@HPEAVLANG_STRING@@PEBDGPEAVSTRU@@PEAVIHttpTraceContext@@@Z; META_SCRIPT_MAP::Initialize(INativeConfigurationElement *,int,IHttpServer *,int,LANG_STRING *,char const *,ushort,STRU *,IHttpTraceContext *)
0x1800303d9  mov     ebx, eax
0x1800303db  test    eax, eax
0x1800303dd  js      short loc_180030439
0x1800303df  mov     rcx, [rbp+3Fh+var_88]
0x1800303e3  mov     rax, [rcx]
0x1800303e6  mov     rax, [rax+10h]
0x1800303ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303ef  mov     rax, [r15]
0x1800303f2  lea     r8, [rbp+3Fh+var_50]
0x1800303f6  xor     r9d, r9d
0x1800303f9  mov     [rbp+3Fh+var_88], r13
0x1800303fd  lea     rdx, aPhysicalpath_0; "physicalPath"
0x180030404  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180030409  mov     rcx, r15
0x18003040c  mov     rax, [rax+40h]
0x180030410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030415  mov     ebx, eax
0x180030417  test    eax, eax
0x180030419  js      short loc_180030439
0x18003041b  mov     rdx, [rbp+3Fh+var_50]
0x18003041f  lea     rsi, [rdi+0F0h]
0x180030426  mov     rcx, rsi
0x180030429  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18003042f  mov     ebx, eax
0x180030431  test    eax, eax
0x180030433  jns     loc_1800304E2
0x180030439  mov     rcx, [rbp+3Fh+var_80]
0x18003043d  test    rcx, rcx
0x180030440  jz      short loc_180030452
0x180030442  mov     rax, [rcx]
0x180030445  mov     rax, [rax+10h]
0x180030449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003044e  mov     [rbp+3Fh+var_80], r13
0x180030452  mov     rcx, [rbp+3Fh+var_88]
0x180030456  test    rcx, rcx
0x180030459  jz      short loc_18003046B
0x18003045b  mov     rax, [rcx]
0x18003045e  mov     rax, [rax+10h]
0x180030462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030467  mov     [rbp+3Fh+var_88], r13
0x18003046b  mov     rcx, [rbp+3Fh+var_78]
0x18003046f  test    rcx, rcx
0x180030472  jz      short loc_180030484
0x180030474  mov     rax, [rcx]
0x180030477  mov     rax, [rax+10h]
0x18003047b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030480  mov     [rbp+3Fh+var_78], r13
0x180030484  mov     rcx, [rbp+3Fh+var_90]
0x180030488  test    rcx, rcx
0x18003048b  jz      short loc_180030499
0x18003048d  mov     rax, [rcx]
0x180030490  mov     rax, [rax+10h]
0x180030494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030499  mov     eax, ebx
0x18003049b  add     rsp, 0A8h
0x1800304a2  pop     r15
0x1800304a4  pop     r14
0x1800304a6  pop     r13
0x1800304a8  pop     r12
0x1800304aa  pop     rdi
0x1800304ab  pop     rsi
0x1800304ac  pop     rbx
0x1800304ad  pop     rbp
0x1800304ae  retn
0x1800304af  mov     rcx, rsi
0x1800304b2  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800304b8  mov     rcx, rsi
0x1800304bb  mov     rbx, rax
0x1800304be  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800304c4  dec     eax
0x1800304c6  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
  ... truncated ...
```
