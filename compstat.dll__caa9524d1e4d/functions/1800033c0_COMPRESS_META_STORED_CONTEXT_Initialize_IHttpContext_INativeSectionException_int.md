# COMPRESS_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *,int)

- ea: `0x1800033c0`
- end: `0x1800036c5`
- name: `?Initialize@COMPRESS_META_STORED_CONTEXT@@AEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@H@Z`
- size: `773`
- prototype: `__int64 __fastcall(COMPRESS_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001310`

## callees

- `0x1800033c0`
- `0x1800036d0`
- `0x180003de0`
- `0x180005f5e`
- `0x180009010`

## string_xrefs

- `0x1800034c3`: `doStaticCompression`
- `0x180003496`: `doDynamicCompression`
- `0x1800034f0`: `dynamicCompressionBeforeCache`
- `0x180003461`: `system.webServer/urlCompression`
- `0x180003544`: `system.webServer/httpCompression`
- `0x1800070ea`: `system.webServer/httpCompression`

## pseudocode

```c
__int64 __fastcall COMPRESS_META_STORED_CONTEXT::Initialize(
        COMPRESS_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v7)(_QWORD); // rax
  __int64 v8; // r12
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rax
  int v10; // ebx
  BOOL v11; // esi
  __int64 v13; // [rsp+40h] [rbp-38h] BYREF
  __int64 v14; // [rsp+48h] [rbp-30h] BYREF
  struct INativeConfigurationElement *v15; // [rsp+50h] [rbp-28h] BYREF
  __int64 v16; // [rsp+58h] [rbp-20h] BYREF
  wchar_t *String1; // [rsp+60h] [rbp-18h] BYREF
  __int64 v18; // [rsp+C8h] [rbp+50h] BYREF

  v3 = *(_QWORD *)a2;
  v16 = 0;
  v14 = 0;
  v15 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v13 = 0;
  v18 = 0;
  String1 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v8 = (**v7)(v7);
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v10 = (**v9)(v9, &IID_INativeConfigurationSystem, &v16);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v16 + 24LL))(
            v16,
            L"system.webServer/urlCompression",
            v8,
            &v14,
            a3,
            0);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v14 + 72LL))(
              v14,
              L"doDynamicCompression",
              (char *)this + 12,
              0,
              0);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v14 + 72LL))(
                v14,
                L"doStaticCompression",
                (char *)this + 8,
                0,
                0);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v14 + 72LL))(
                  v14,
                  L"dynamicCompressionBeforeCache",
                  (char *)this + 20,
                  0,
                  0);
          if ( v10 >= 0 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
            v14 = 0;
            if ( *((_DWORD *)this + 2) || *((_DWORD *)this + 3) )
            {
              if ( (*(int (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, struct INativeSectionException **, __int64 *))(*(_QWORD *)v16 + 24LL))(
                     v16,
                     L"system.webServer/httpCompression",
                     v8,
                     &v13,
                     a3,
                     &v18) < 0 )
              {
                if ( v18 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                  v18 = 0;
                }
                if ( *a3 )
                {
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
                  *a3 = 0;
                }
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const wchar_t *, __int64 *, struct INativeSectionException **, __int64 *))(*(_QWORD *)v16 + 24LL))(
                        v16,
                        L"system.webServer/httpCompression",
                        L"MACHINE/WEBROOT/APPHOST",
                        &v13,
                        a3,
                        &v18);
                if ( v10 < 0 )
                  goto LABEL_25;
              }
              if ( *((_DWORD *)this + 2) )
              {
                v10 = InitializeMimeTypes(v13, L"staticTypes", (char *)this + 24, (char *)this + 40);
                if ( v10 < 0 )
                  goto LABEL_25;
              }
              if ( *((_DWORD *)this + 3) )
              {
                v10 = InitializeMimeTypes(v13, L"dynamicTypes", (char *)this + 48, (char *)this + 64);
                if ( v10 < 0 )
                  goto LABEL_25;
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
              v13 = 0;
            }
            v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, struct INativeConfigurationElement **, struct INativeSectionException **, __int64 *))(*(_QWORD *)v16 + 24LL))(
                    v16,
                    L"system.webServer/staticContent",
                    v8,
                    &v15,
                    a3,
                    &v18);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v18 + 24LL))(v18, &String1);
              if ( v10 >= 0 )
              {
                v11 = wcscmp_0(String1, L"MACHINE/WEBROOT/APPHOST") == 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
                v18 = 0;
                v10 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v15 + 72LL))(
                        v15,
                        L"enableDocFooter",
                        (char *)this + 16,
                        0,
                        0);
                if ( v10 >= 0 )
                {
                  v10 = MIME_MAP::Initialize((COMPRESS_META_STORED_CONTEXT *)((char *)this + 72), v15, v11);
                  if ( v10 >= 0 )
                  {
                    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v15 + 16LL))(v15);
                    v15 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
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
LABEL_25:
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v18 = 0;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v15 + 16LL))(v15);
    v15 = 0;
  }
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v13 = 0;
  }
  if ( v14 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v14 = 0;
  }
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800033c0  push    rbp
0x1800033c2  push    rbx
0x1800033c3  push    rsi
0x1800033c4  push    rdi
0x1800033c5  push    r12
0x1800033c7  push    r13
0x1800033c9  push    r14
0x1800033cb  push    r15
0x1800033cd  mov     rbp, rsp
0x1800033d0  sub     rsp, 78h
0x1800033d4  mov     rax, [rdx]
0x1800033d7  xor     r13d, r13d
0x1800033da  mov     rdi, rcx
0x1800033dd  mov     [rbp+var_20], r13
0x1800033e1  mov     rcx, rdx
0x1800033e4  mov     [rbp+var_30], r13
0x1800033e8  mov     r15, r8
0x1800033eb  mov     [rbp+var_28], r13
0x1800033ef  mov     rax, [rax+0A0h]
0x1800033f6  mov     [rbp+var_38], r13
0x1800033fa  mov     [rbp+arg_8], r13
0x1800033fe  mov     [rbp+String1], r13
0x180003402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003407  mov     rdx, rax
0x18000340a  mov     rcx, [rax]
0x18000340d  mov     rax, [rcx]
0x180003410  mov     rcx, rdx
0x180003413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003418  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x18000341f  mov     r12, rax
0x180003422  mov     rdx, [rcx]
0x180003425  mov     rax, [rdx+38h]
0x180003429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000342e  mov     r9, rax
0x180003431  lea     r8, [rbp+var_20]
0x180003435  lea     rdx, IID_INativeConfigurationSystem
0x18000343c  mov     rcx, [rax]
0x18000343f  mov     rax, [rcx]
0x180003442  mov     rcx, r9
0x180003445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000344a  mov     ebx, eax
0x18000344c  test    eax, eax
0x18000344e  js      loc_180007107
0x180003454  mov     rcx, [rbp+var_20]
0x180003458  lea     r9, [rbp+var_30]
0x18000345c  mov     [rsp+78h+var_50], r13
0x180003461  lea     rdx, aSystemWebserve_0; "system.webServer/urlCompression"
0x180003468  mov     r8, r12
0x18000346b  mov     [rsp+78h+var_58], r15
0x180003470  mov     rax, [rcx]
0x180003473  mov     rax, [rax+18h]
0x180003477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000347c  mov     ebx, eax
0x18000347e  test    eax, eax
0x180003480  js      loc_180007107
0x180003486  mov     rcx, [rbp+var_30]
0x18000348a  lea     r8, [rdi+0Ch]
0x18000348e  xor     r9d, r9d
0x180003491  mov     [rsp+78h+var_58], r13
0x180003496  lea     rdx, aDodynamiccompr; "doDynamicCompression"
0x18000349d  mov     rax, [rcx]
0x1800034a0  mov     rax, [rax+48h]
0x1800034a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034a9  mov     ebx, eax
0x1800034ab  test    eax, eax
0x1800034ad  js      loc_180007107
0x1800034b3  mov     rcx, [rbp+var_30]
0x1800034b7  lea     r8, [rdi+8]
0x1800034bb  xor     r9d, r9d
0x1800034be  mov     [rsp+78h+var_58], r13
0x1800034c3  lea     rdx, aDostaticcompre; "doStaticCompression"
0x1800034ca  mov     rax, [rcx]
0x1800034cd  mov     rax, [rax+48h]
0x1800034d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d6  mov     ebx, eax
0x1800034d8  test    eax, eax
0x1800034da  js      loc_180007107
0x1800034e0  mov     rcx, [rbp+var_30]
0x1800034e4  lea     r8, [rdi+14h]
0x1800034e8  xor     r9d, r9d
0x1800034eb  mov     [rsp+78h+var_58], r13
0x1800034f0  lea     rdx, aDynamiccompres_3; "dynamicCompressionBeforeCache"
0x1800034f7  mov     rax, [rcx]
0x1800034fa  mov     rax, [rax+48h]
0x1800034fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003503  mov     ebx, eax
0x180003505  test    eax, eax
0x180003507  js      loc_180007107
0x18000350d  mov     rcx, [rbp+var_30]
0x180003511  mov     rax, [rcx]
0x180003514  mov     rax, [rax+10h]
0x180003518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000351d  mov     [rbp+var_30], r13
0x180003521  cmp     [rdi+8], r13d
0x180003525  jz      loc_18000708E
0x18000352b  mov     rcx, [rbp+var_20]
0x18000352f  lea     rdx, [rbp+arg_8]
0x180003533  mov     [rsp+78h+var_50], rdx
0x180003538  lea     r9, [rbp+var_38]
0x18000353c  mov     r8, r12
0x18000353f  mov     [rsp+78h+var_58], r15
0x180003544  lea     rdx, aSystemWebserve_1; "system.webServer/httpCompression"
0x18000354b  mov     rax, [rcx]
0x18000354e  mov     rax, [rax+18h]
0x180003552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003557  test    eax, eax
0x180003559  js      loc_18000709D
0x18000355f  cmp     [rdi+8], r13d
0x180003563  jz      short loc_180003587
0x180003565  mov     rcx, [rbp+var_38]
0x180003569  lea     r9, [rdi+28h]
0x18000356d  lea     r8, [rdi+18h]
0x180003571  lea     rdx, aStatictypes; "staticTypes"
0x180003578  call    InitializeMimeTypes
0x18000357d  mov     ebx, eax
0x18000357f  test    eax, eax
0x180003581  js      loc_180007107
0x180003587  cmp     [rdi+0Ch], r13d
0x18000358b  jz      short loc_1800035AF
0x18000358d  mov     rcx, [rbp+var_38]
0x180003591  lea     r9, [rdi+40h]
0x180003595  lea     r8, [rdi+30h]
0x180003599  lea     rdx, aDynamictypes; "dynamicTypes"
0x1800035a0  call    InitializeMimeTypes
0x1800035a5  mov     ebx, eax
0x1800035a7  test    eax, eax
0x1800035a9  js      loc_180007107
0x1800035af  mov     rcx, [rbp+var_38]
0x1800035b3  mov     rax, [rcx]
0x1800035b6  mov     rax, [rax+10h]
0x1800035ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035bf  mov     [rbp+var_38], r13
0x1800035c3  mov     rcx, [rbp+var_20]
0x1800035c7  lea     rdx, [rbp+arg_8]
0x1800035cb  mov     [rsp+78h+var_50], rdx
0x1800035d0  lea     r9, [rbp+var_28]
0x1800035d4  mov     r8, r12
0x1800035d7  mov     [rsp+78h+var_58], r15
0x1800035dc  lea     rdx, aSystemWebserve; "system.webServer/staticContent"
0x1800035e3  mov     rax, [rcx]
0x1800035e6  mov     rax, [rax+18h]
0x1800035ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ef  mov     ebx, eax
0x1800035f1  test    eax, eax
0x1800035f3  js      loc_180007107
0x1800035f9  mov     rcx, [rbp+arg_8]
0x1800035fd  lea     rdx, [rbp+String1]
0x180003601  mov     rax, [rcx]
0x180003604  mov     rax, [rax+18h]
0x180003608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000360d  mov     ebx, eax
0x18000360f  test    eax, eax
0x180003611  js      loc_180007107
0x180003617  mov     rcx, [rbp+String1]; String1
0x18000361b  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180003622  mov     esi, r13d
0x180003625  call    wcscmp_0
0x18000362a  test    eax, eax
0x18000362c  jnz     short loc_180003633
0x18000362e  mov     esi, 1
0x180003633  mov     rcx, [rbp+arg_8]
0x180003637  mov     rax, [rcx]
0x18000363a  mov     rax, [rax+10h]
0x18000363e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003643  mov     rcx, [rbp+var_28]
0x180003647  lea     r8, [rdi+10h]
0x18000364b  mov     [rbp+arg_8], r13
0x18000364f  lea     rdx, aEnabledocfoote; "enableDocFooter"
0x180003656  xor     r9d, r9d
0x180003659  mov     [rsp+78h+var_58], r13
0x18000365e  mov     rax, [rcx]
0x180003661  mov     rax, [rax+48h]
0x180003665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000366a  mov     ebx, eax
0x18000366c  test    eax, eax
0x18000366e  js      loc_180007107
0x180003674  mov     rdx, [rbp+var_28]; struct INativeConfigurationElement *
0x180003678  lea     rcx, [rdi+48h]; this
0x18000367c  mov     r8d, esi; int
0x18000367f  call    ?Initialize@MIME_MAP@@QEAAJPEAVINativeConfigurationElement@@H@Z; MIME_MAP::Initialize(INativeConfigurationElement *,int)
0x180003684  mov     ebx, eax
0x180003686  test    eax, eax
0x180003688  js      loc_180007107
0x18000368e  mov     rcx, [rbp+var_28]
0x180003692  mov     rax, [rcx]
0x180003695  mov     rax, [rax+10h]
0x180003699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369e  mov     rcx, [rbp+var_20]
0x1800036a2  mov     [rbp+var_28], r13
0x1800036a6  mov     rax, [rcx]
0x1800036a9  mov     rax, [rax+10h]
0x1800036ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b2  xor     eax, eax
0x1800036b4  add     rsp, 78h
0x1800036b8  pop     r15
0x1800036ba  pop     r14
0x1800036bc  pop     r13
0x1800036be  pop     r12
0x1800036c0  pop     rdi
0x1800036c1  pop     rsi
0x1800036c2  pop     rbx
0x1800036c3  pop     rbp
0x1800036c4  retn
0x18000708e  cmp     [rdi+0Ch], r13d
0x180007092  jz      loc_1800035C3
0x180007098  jmp     loc_18000352B
0x18000709d  mov     rcx, [rbp+arg_8]
0x1800070a1  test    rcx, rcx
0x1800070a4  jz      short loc_1800070B6
0x1800070a6  mov     rax, [rcx]
0x1800070a9  mov     rax, [rax+10h]
0x1800070ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070b2  mov     [rbp+arg_8], r13
0x1800070b6  mov     rcx, [r15]
0x1800070b9  test    rcx, rcx
0x1800070bc  jz      short loc_1800070CD
0x1800070be  mov     rax, [rcx]
0x1800070c1  mov     rax, [rax+10h]
0x1800070c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070ca  mov     [r15], r13
0x1800070cd  mov     rcx, [rbp+var_20]
0x1800070d1  lea     r8, [rbp+arg_8]
0x1800070d5  mov     [rsp+78h+var_50], r8
0x1800070da  lea     r9, [rbp+var_38]
0x1800070de  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x1800070e5  mov     [rsp+78h+var_58], r15
0x1800070ea  lea     rdx, aSystemWebserve_1; "system.webServer/httpCompression"
0x1800070f1  mov     rax, [rcx]
0x1800070f4  mov     rax, [rax+18h]
0x1800070f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070fd  mov     ebx, eax
0x1800070ff  test    eax, eax
0x180007101  jns     loc_18000355F
0x180007107  mov     rcx, [rbp+arg_8]
0x18000710b  test    rcx, rcx
0x18000710e  jz      short loc_180007120
0x180007110  mov     rax, [rcx]
0x180007113  mov     rax, [rax+10h]
0x180007117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000711c  mov     [rbp+arg_8], r13
0x180007120  mov     rcx, [rbp+var_28]
0x180007124  test    rcx, rcx
0x180007127  jz      short loc_180007139
0x180007129  mov     rax, [rcx]
0x18000712c  mov     rax, [rax+10h]
0x180007130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007135  mov     [rbp+var_28], r13
0x180007139  mov     rcx, [rbp+var_38]
0x18000713d  test    rcx, rcx
0x180007140  jz      short loc_180007152
0x180007142  mov     rax, [rcx]
0x180007145  mov     rax, [rax+10h]
0x180007149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000714e  mov     [rbp+var_38], r13
0x180007152  mov     rcx, [rbp+var_30]
0x180007156  test    rcx, rcx
0x180007159  jz      short loc_18000716B
0x18000715b  mov     rax, [rcx]
0x18000715e  mov     rax, [rax+10h]
0x180007162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007167  mov     [rbp+var_30], r13
0x18000716b  mov     rcx, [rbp+var_20]
0x18000716f  test    rcx, rcx
0x180007172  jz      short loc_180007180
0x180007174  mov     rax, [rcx]
0x180007177  mov     rax, [rax+10h]
0x18000717b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007180  mov     eax, ebx
0x180007182  jmp     loc_1800036B4
```
