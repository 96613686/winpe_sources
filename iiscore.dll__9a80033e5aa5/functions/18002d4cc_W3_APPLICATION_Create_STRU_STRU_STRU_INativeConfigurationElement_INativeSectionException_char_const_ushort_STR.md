# W3_APPLICATION::Create(STRU &,STRU &,STRU &,INativeConfigurationElement *,INativeSectionException * *,char const *,ushort,STRU *,IHttpTraceContext *)

- ea: `0x18002d4cc`
- end: `0x18002dc2a`
- name: `?Create@W3_APPLICATION@@QEAAJAEAVSTRU@@00PEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@PEBDGPEAV2@PEAVIHttpTraceContext@@@Z`
- size: `1886`
- prototype: `__int64 __fastcall(W3_APPLICATION *__hidden this, struct STRU *, struct STRU *, struct STRU *, struct INativeConfigurationElement *, struct INativeSectionException **, const char *, unsigned __int16, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x18002dcb8`

## callees

- `0x180008930`
- `0x180019558`
- `0x18001f774`
- `0x18002d3a0`
- `0x18002d4cc`
- `0x18002e494`
- `0x18003066c`
- `0x180035010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002d575`
- `msvcrt!_wcsicmp` at `0x18002d918`
- `msvcrt!_wcsicmp` at `0x18002d575`
- `msvcrt!_wcsicmp` at `0x18002d918`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002d8fa`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002d8fa`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002dc1f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18002dc1f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002d5e0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002d6c1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002db37`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002d5e0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002d6c1`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18002db37`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x18002da02`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x18002dae5`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x18002da02`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x18002dae5`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002d58d`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002d5a2`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002d5ba`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002d58d`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002d5a2`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002d5ba`
- `iisutil!SAFE_snwprintf` at `0x18002da1e`
- `iisutil!SAFE_snwprintf` at `0x18002db06`
- `iisutil!SAFE_snwprintf` at `0x18002da1e`
- `iisutil!SAFE_snwprintf` at `0x18002db06`

## pseudocode

```c
int __fastcall W3_APPLICATION::Create(
        W3_APPLICATION *this,
        struct STRU *a2,
        struct STRU *a3,
        struct STRU *a4,
        struct INativeConfigurationElement *a5,
        struct INativeSectionException **a6,
        const char *a7,
        unsigned __int16 a8,
        struct STRU *a9,
        struct IHttpTraceContext *a10)
{
  __int64 v14; // rax
  __int64 (__fastcall *v15)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD); // rax
  int result; // eax
  const wchar_t *v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, const wchar_t *, unsigned __int16 *, __int64 **, struct INativeSectionException **, _QWORD); // rbx
  unsigned __int16 *Str; // rax
  int appended; // ebx
  __int64 *v22; // rcx
  bool v23; // al
  bool v24; // zf
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, struct INativeSectionException **, _QWORD); // rbx
  unsigned __int16 *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned int i; // r14d
  __int64 v32; // rax
  int v33; // eax
  const struct _GUID *v34; // rdx
  volatile signed __int32 *v35; // rbx
  W3_SERVER *v36; // r15
  __int64 v37; // rdi
  wchar_t *v38; // r13
  const wchar_t *v39; // rax
  APPLICATION_MODULE *v40; // rax
  APPLICATION_MODULE *v41; // rdi
  unsigned int v42; // edx
  __int64 v43; // rdi
  __int64 (__fastcall *v44)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, struct INativeSectionException **, _QWORD); // rbx
  unsigned __int16 *v45; // rax
  int v46; // eax
  __int64 v47; // rcx
  __int64 v48; // rcx
  int v49; // [rsp+40h] [rbp-71h] BYREF
  __int64 v50; // [rsp+48h] [rbp-69h] BYREF
  __int64 *v51; // [rsp+50h] [rbp-61h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp-59h] BYREF
  __int64 *v53; // [rsp+60h] [rbp-51h] BYREF
  __int64 v54; // [rsp+68h] [rbp-49h] BYREF
  unsigned __int16 *v55; // [rsp+70h] [rbp-41h] BYREF
  __int64 v56; // [rsp+78h] [rbp-39h] BYREF
  unsigned int v57; // [rsp+80h] [rbp-31h] BYREF
  int v58; // [rsp+84h] [rbp-2Dh] BYREF
  unsigned int v59; // [rsp+88h] [rbp-29h] BYREF
  unsigned __int16 *v60; // [rsp+90h] [rbp-21h] BYREF
  const unsigned __int16 *v61; // [rsp+98h] [rbp-19h] BYREF
  wchar_t *String1; // [rsp+A0h] [rbp-11h] BYREF

  v51 = 0;
  v54 = 0;
  v56 = 0;
  v14 = *(_QWORD *)a5;
  v53 = 0;
  v50 = 0;
  String2 = 0;
  v15 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, const wchar_t *, wchar_t **, _QWORD, _QWORD))(v14 + 64);
  v60 = 0;
  v55 = 0;
  v57 = 0;
  String1 = 0;
  v58 = 0;
  v49 = 0;
  v59 = 0;
  v61 = 0;
  result = v15(a5, L"applicationPool", &String1, 0, 0);
  if ( result < 0 )
    return result;
  v17 = (const wchar_t *)(*(__int64 (__fastcall **)(W3_SERVER *))(*(_QWORD *)g_pW3Server + 8LL))(g_pW3Server);
  *((_BYTE *)this + 217) = _wcsicmp(String1, v17) == 0;
  result = STRU::Copy((W3_APPLICATION *)((char *)this + 32), a2);
  if ( result < 0 )
    return result;
  result = STRU::Copy((W3_APPLICATION *)((char *)this + 88), a3);
  if ( result < 0 )
    return result;
  result = STRU::Copy((W3_APPLICATION *)((char *)this + 144), a4);
  if ( result < 0 )
    return result;
  v18 = *((_QWORD *)g_pW3Server + 187);
  v19 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, __int64 **, struct INativeSectionException **, _QWORD))(*(_QWORD *)v18 + 24LL);
  Str = STRU::QueryStr(a2);
  appended = v19(v18, L"system.webServer/serverRuntime", Str, &v51, a6, 0);
  if ( appended < 0 )
    goto LABEL_39;
  appended = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, int *, _QWORD, _QWORD))(*v51 + 72))(
               v51,
               L"enabled",
               &v49,
               0,
               0);
  if ( appended < 0 )
    goto LABEL_39;
  v22 = v51;
  v23 = v49 != 0;
  *((_BYTE *)this + 216) = v49 != 0;
  v24 = !v23;
  v25 = *v22;
  if ( v24 )
  {
    (*(void (**)(void))(v25 + 16))();
    return 0;
  }
  appended = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, char *, _QWORD, _QWORD))(v25 + 48))(
               v22,
               L"appConcurrentRequestLimit",
               (char *)this + 208,
               0,
               0);
  if ( appended < 0 )
    goto LABEL_39;
  (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
  v51 = 0;
  v26 = *((_QWORD *)g_pW3Server + 187);
  v27 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v26 + 24LL);
  v28 = STRU::QueryStr(a2);
  appended = v27(v26, L"system.webServer/modules", v28, &v54, a6, 0);
  if ( appended < 0 )
    goto LABEL_39;
  appended = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v54 + 72LL))(
               v54,
               L"runAllManagedModulesForAllRequests",
               &v49,
               0,
               0);
  if ( appended < 0 )
    goto LABEL_39;
  v29 = v54;
  *((_BYTE *)this + 220) = v49 != 0;
  appended = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v29 + 72LL))(
               v29,
               L"runManagedModulesForWebDavRequests",
               &v49,
               0,
               0);
  if ( appended < 0 )
    goto LABEL_39;
  v30 = v54;
  *((_BYTE *)this + 221) = v49 != 0;
  appended = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v30 + 40LL))(v30, &v53);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
  v54 = 0;
  if ( appended < 0 )
    goto LABEL_39;
  appended = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v53 + 24))(v53, &v57);
  if ( appended < 0 )
    goto LABEL_39;
  for ( i = 0; ; ++i )
  {
    v32 = *v53;
    if ( i >= v57 )
    {
      (*(void (**)(void))(v32 + 16))();
      v53 = 0;
      v43 = *((_QWORD *)g_pW3Server + 187);
      v44 = *(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 *, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)v43 + 24LL);
      v45 = STRU::QueryStr(a2);
      v46 = v44(v43, L"system.webServer/applicationInitialization", v45, &v56, a6, 0);
      appended = v46;
      if ( v46 < 0 )
      {
        if ( v46 != -2147023728 )
          goto LABEL_39;
        if ( *a6 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a6 + 16LL))(*a6);
          *a6 = 0;
        }
      }
      else
      {
        appended = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v56 + 72LL))(
                     v56,
                     L"skipManagedModules",
                     &v49,
                     0,
                     0);
        if ( appended < 0 )
          goto LABEL_39;
        v47 = v56;
        *((_BYTE *)this + 222) = v49 != 0;
        appended = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v47 + 72LL))(
                     v47,
                     L"doAppInitAfterRestart",
                     &v49,
                     0,
                     0);
        if ( appended < 0 )
          goto LABEL_39;
        v48 = v56;
        *((_BYTE *)this + 223) = v49 != 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        v56 = 0;
      }
      CReaderWriterLock3::WriteLock((W3_APPLICATION *)((char *)this + 200));
      return 0;
    }
    appended = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v32 + 32))(v53, i, &v50);
    if ( appended < 0 )
      goto LABEL_39;
    appended = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v50 + 64LL))(
                 v50,
                 L"name",
                 &String2,
                 0,
                 0);
    if ( appended < 0 )
      goto LABEL_39;
    appended = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v50 + 64LL))(
                 v50,
                 L"type",
                 &v60,
                 0,
                 0);
    if ( appended < 0 )
      goto LABEL_39;
    appended = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v50 + 64LL))(
                 v50,
                 L"preCondition",
                 &v55,
                 0,
                 0);
    if ( appended < 0 )
      goto LABEL_39;
    v33 = (*(__int64 (__fastcall **)(W3_SERVER *, unsigned __int16 *, int *))(*(_QWORD *)g_pW3Server + 176LL))(
            g_pW3Server,
            v55,
            &v58);
    if ( v58 )
    {
      appended = -2147024883;
      if ( (int)LANG_STRING::GetString(*((LANG_STRING **)g_pW3Server + 194), a7, a8, 0x31FDu, &v61, &v59) >= 0 )
        SAFE_snwprintf(a9, v61, String2, v55);
      goto LABEL_39;
    }
    if ( !v33 )
    {
      if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled(a10, 0, 4) )
        IISGeneralEvents::MODULE_PRECONDITION_NOT_MATCH::RaiseEvent(a10, v34, String2, v55);
      goto LABEL_36;
    }
    v35 = 0;
    if ( !*v60 )
      break;
LABEL_32:
    v40 = (APPLICATION_MODULE *)operator new(0x28u);
    v41 = v40;
    if ( !v40 )
    {
      appended = -2147024888;
      goto LABEL_39;
    }
    *(_QWORD *)v40 = 1145917505;
    *((_QWORD *)v40 + 1) = 0;
    *((_QWORD *)v40 + 2) = 0;
    *((_QWORD *)v40 + 3) = 0;
    *((_QWORD *)v40 + 4) = 0;
    appended = APPLICATION_MODULE::Create(v40, String2, v60, v55, (struct VIRTUAL_MODULE *)v35, v35 == 0);
    if ( appended < 0
      || (appended = APPLICATION_MODULE_LIST::AppendModule((W3_APPLICATION *)((char *)this + 224), v41), appended < 0) )
    {
      APPLICATION_MODULE::`scalar deleting destructor'(v41, v42);
      goto LABEL_39;
    }
    String2 = 0;
    v60 = 0;
    v55 = 0;
LABEL_36:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  v36 = g_pW3Server;
  v37 = 0;
  v38 = String2;
  while ( (unsigned int)v37 < *((_DWORD *)v36 + 152) )
  {
    v35 = (volatile signed __int32 *)*((_QWORD *)BUFFER::QueryPtr((W3_SERVER *)((char *)v36 + 560)) + v37);
    v39 = (const wchar_t *)(**(__int64 (__fastcall ***)(volatile signed __int32 *))v35)(v35);
    if ( !_wcsicmp(v39, v38) )
    {
      _InterlockedIncrement(v35 + 3);
      goto LABEL_32;
    }
    v37 = (unsigned int)(v37 + 1);
  }
  appended = -2147024894;
  if ( (int)LANG_STRING::GetString(*((LANG_STRING **)g_pW3Server + 194), a7, a8, 0x31FBu, &v61, &v59) >= 0 )
    SAFE_snwprintf(a9, v61, String2);
LABEL_39:
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  if ( v53 )
  {
    (*(void (__fastcall **)(__int64 *))(*v53 + 16))(v53);
    v53 = 0;
  }
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    v51 = 0;
  }
  if ( v56 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
  return appended;
}

```

## disassembly

```asm
0x18002d4cc  mov     [rsp-8+arg_8], rdx
0x18002d4d1  push    rbp
0x18002d4d2  push    rbx
0x18002d4d3  push    rsi
0x18002d4d4  push    rdi
0x18002d4d5  push    r12
0x18002d4d7  push    r13
0x18002d4d9  push    r14
0x18002d4db  push    r15
0x18002d4dd  lea     rbp, [rsp-7]
0x18002d4e2  sub     rsp, 0B8h
0x18002d4e9  xor     r13d, r13d
0x18002d4ec  mov     rsi, rcx
0x18002d4ef  mov     rcx, [rbp+3Fh+arg_20]
0x18002d4f3  mov     rdi, r9
0x18002d4f6  mov     rbx, r8
0x18002d4f9  mov     [rbp+3Fh+var_A0], r13
0x18002d4fd  mov     r15, rdx
0x18002d500  mov     [rbp+3Fh+var_88], r13
0x18002d504  xor     r9d, r9d
0x18002d507  mov     [rbp+3Fh+var_78], r13
0x18002d50b  mov     rax, [rcx]
0x18002d50e  lea     r8, [rbp+3Fh+String1]
0x18002d512  lea     rdx, aApplicationpoo; "applicationPool"
0x18002d519  mov     [rbp+3Fh+var_90], r13
0x18002d51d  mov     [rbp+3Fh+var_A8], r13
0x18002d521  mov     [rbp+3Fh+String2], r13
0x18002d525  mov     rax, [rax+40h]
0x18002d529  mov     [rbp+3Fh+var_60], r13
0x18002d52d  mov     [rbp+3Fh+var_80], r13
0x18002d531  mov     [rbp+3Fh+var_70], r13d
0x18002d535  mov     [rbp+3Fh+String1], r13
0x18002d539  mov     [rbp+3Fh+var_6C], r13d
0x18002d53d  mov     [rbp+3Fh+var_B0], r13d
0x18002d541  mov     [rbp+3Fh+var_68], r13d
0x18002d545  mov     [rbp+3Fh+var_58], r13
0x18002d549  mov     [rsp+0F0h+var_D0], r13
0x18002d54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d553  test    eax, eax
0x18002d555  js      loc_18002DA86
0x18002d55b  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002d562  mov     rax, [rcx]
0x18002d565  mov     rax, [rax+8]
0x18002d569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d56e  mov     rcx, [rbp+3Fh+String1]; String1
0x18002d572  mov     rdx, rax; String2
0x18002d575  call    cs:__imp__wcsicmp
0x18002d57b  lea     rcx, [rsi+20h]
0x18002d57f  mov     rdx, r15
0x18002d582  test    eax, eax
0x18002d584  setz    al
0x18002d587  mov     [rsi+0D9h], al
0x18002d58d  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002d593  test    eax, eax
0x18002d595  js      loc_18002DA86
0x18002d59b  lea     rcx, [rsi+58h]
0x18002d59f  mov     rdx, rbx
0x18002d5a2  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002d5a8  test    eax, eax
0x18002d5aa  js      loc_18002DA86
0x18002d5b0  lea     rcx, [rsi+90h]
0x18002d5b7  mov     rdx, rdi
0x18002d5ba  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002d5c0  test    eax, eax
0x18002d5c2  js      loc_18002DA86
0x18002d5c8  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002d5cf  mov     rcx, r15
0x18002d5d2  mov     rdi, [rax+5D8h]
0x18002d5d9  mov     rax, [rdi]
0x18002d5dc  mov     rbx, [rax+18h]
0x18002d5e0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002d5e6  mov     r12, [rbp+3Fh+arg_28]
0x18002d5ea  lea     r9, [rbp+3Fh+var_A0]
0x18002d5ee  mov     r8, rax
0x18002d5f1  mov     qword ptr [rsp+0F0h+var_C8], r13
0x18002d5f6  mov     rax, rbx
0x18002d5f9  mov     [rsp+0F0h+var_D0], r12
0x18002d5fe  lea     rdx, aSystemWebserve_4; "system.webServer/serverRuntime"
0x18002d605  mov     rcx, rdi
0x18002d608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d60d  mov     ebx, eax
0x18002d60f  test    eax, eax
0x18002d611  js      loc_18002DA24
0x18002d617  mov     rcx, [rbp+3Fh+var_A0]
0x18002d61b  lea     r8, [rbp+3Fh+var_B0]
0x18002d61f  xor     r9d, r9d
0x18002d622  mov     [rsp+0F0h+var_D0], r13
0x18002d627  lea     rdx, aEnabled; "enabled"
0x18002d62e  mov     rax, [rcx]
0x18002d631  mov     rax, [rax+48h]
0x18002d635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d63a  mov     ebx, eax
0x18002d63c  test    eax, eax
0x18002d63e  js      loc_18002DA24
0x18002d644  cmp     [rbp+3Fh+var_B0], r13d
0x18002d648  mov     rcx, [rbp+3Fh+var_A0]
0x18002d64c  setnz   al
0x18002d64f  mov     [rsi+0D8h], al
0x18002d655  test    al, al
0x18002d657  mov     rax, [rcx]
0x18002d65a  jnz     short loc_18002D66C
0x18002d65c  mov     rax, [rax+10h]
0x18002d660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d665  xor     eax, eax
0x18002d667  jmp     loc_18002DA86
0x18002d66c  mov     rax, [rax+30h]
0x18002d670  lea     r8, [rsi+0D0h]
0x18002d677  xor     r9d, r9d
0x18002d67a  mov     [rsp+0F0h+var_D0], r13
0x18002d67f  lea     rdx, aAppconcurrentr; "appConcurrentRequestLimit"
0x18002d686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d68b  mov     ebx, eax
0x18002d68d  test    eax, eax
0x18002d68f  js      loc_18002DA24
0x18002d695  mov     rcx, [rbp+3Fh+var_A0]
0x18002d699  mov     rax, [rcx]
0x18002d69c  mov     rax, [rax+10h]
0x18002d6a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6a5  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002d6ac  mov     rcx, r15
0x18002d6af  mov     [rbp+3Fh+var_A0], r13
0x18002d6b3  mov     rdi, [rax+5D8h]
0x18002d6ba  mov     rax, [rdi]
0x18002d6bd  mov     rbx, [rax+18h]
0x18002d6c1  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18002d6c7  mov     qword ptr [rsp+0F0h+var_C8], r13
0x18002d6cc  lea     r9, [rbp+3Fh+var_88]
0x18002d6d0  mov     r8, rax
0x18002d6d3  mov     [rsp+0F0h+var_D0], r12
0x18002d6d8  mov     rax, rbx
0x18002d6db  lea     rdx, aSystemWebserve_0; "system.webServer/modules"
0x18002d6e2  mov     rcx, rdi
0x18002d6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6ea  mov     ebx, eax
0x18002d6ec  test    eax, eax
0x18002d6ee  js      loc_18002DA24
0x18002d6f4  mov     rcx, [rbp+3Fh+var_88]
0x18002d6f8  lea     r8, [rbp+3Fh+var_B0]
0x18002d6fc  xor     r9d, r9d
0x18002d6ff  mov     [rsp+0F0h+var_D0], r13
0x18002d704  lea     rdx, aRunallmanagedm; "runAllManagedModulesForAllRequests"
0x18002d70b  mov     rax, [rcx]
0x18002d70e  mov     rax, [rax+48h]
0x18002d712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d717  mov     ebx, eax
0x18002d719  test    eax, eax
0x18002d71b  js      loc_18002DA24
0x18002d721  cmp     [rbp+3Fh+var_B0], r13d
0x18002d725  lea     r8, [rbp+3Fh+var_B0]
0x18002d729  mov     rcx, [rbp+3Fh+var_88]
0x18002d72d  lea     rdx, aRunmanagedmodu; "runManagedModulesForWebDavRequests"
0x18002d734  setnz   al
0x18002d737  mov     [rsp+0F0h+var_D0], r13
0x18002d73c  mov     [rsi+0DCh], al
0x18002d742  xor     r9d, r9d
0x18002d745  mov     rax, [rcx]
0x18002d748  mov     rax, [rax+48h]
0x18002d74c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d751  mov     ebx, eax
0x18002d753  test    eax, eax
0x18002d755  js      loc_18002DA24
0x18002d75b  cmp     [rbp+3Fh+var_B0], r13d
0x18002d75f  lea     rdx, [rbp+3Fh+var_90]
0x18002d763  mov     rcx, [rbp+3Fh+var_88]
0x18002d767  setnz   al
0x18002d76a  mov     [rsi+0DDh], al
0x18002d770  mov     rax, [rcx]
0x18002d773  mov     rax, [rax+28h]
0x18002d777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d77c  mov     rcx, [rbp+3Fh+var_88]
0x18002d780  mov     ebx, eax
0x18002d782  mov     rax, [rcx]
0x18002d785  mov     rax, [rax+10h]
0x18002d789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d78e  mov     [rbp+3Fh+var_88], r13
0x18002d792  test    ebx, ebx
0x18002d794  js      loc_18002DA24
0x18002d79a  mov     rcx, [rbp+3Fh+var_90]
0x18002d79e  lea     rdx, [rbp+3Fh+var_70]
0x18002d7a2  mov     rax, [rcx]
0x18002d7a5  mov     rax, [rax+18h]
0x18002d7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7ae  mov     ebx, eax
0x18002d7b0  test    eax, eax
0x18002d7b2  js      loc_18002DA24
0x18002d7b8  mov     r14d, r13d
0x18002d7bb  mov     rcx, [rbp+3Fh+var_90]
0x18002d7bf  mov     rax, [rcx]
0x18002d7c2  cmp     r14d, [rbp+3Fh+var_70]
0x18002d7c6  jnb     loc_18002DB11
0x18002d7cc  mov     rax, [rax+20h]
0x18002d7d0  lea     r8, [rbp+3Fh+var_A8]
0x18002d7d4  mov     edx, r14d
0x18002d7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d7dc  mov     ebx, eax
0x18002d7de  test    eax, eax
0x18002d7e0  js      loc_18002DA24
0x18002d7e6  mov     rcx, [rbp+3Fh+var_A8]
0x18002d7ea  lea     r8, [rbp+3Fh+String2]
0x18002d7ee  xor     r9d, r9d
0x18002d7f1  mov     [rsp+0F0h+var_D0], r13
0x18002d7f6  lea     rdx, aName_0; "name"
0x18002d7fd  mov     rax, [rcx]
0x18002d800  mov     rax, [rax+40h]
0x18002d804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d809  mov     ebx, eax
0x18002d80b  test    eax, eax
0x18002d80d  js      loc_18002DA24
0x18002d813  mov     rcx, [rbp+3Fh+var_A8]
0x18002d817  lea     r8, [rbp+3Fh+var_60]
0x18002d81b  xor     r9d, r9d
0x18002d81e  mov     [rsp+0F0h+var_D0], r13
0x18002d823  lea     rdx, aType; "type"
0x18002d82a  mov     rax, [rcx]
0x18002d82d  mov     rax, [rax+40h]
0x18002d831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d836  mov     ebx, eax
0x18002d838  test    eax, eax
0x18002d83a  js      loc_18002DA24
0x18002d840  mov     rcx, [rbp+3Fh+var_A8]
0x18002d844  lea     r8, [rbp+3Fh+var_80]
0x18002d848  xor     r9d, r9d
0x18002d84b  mov     [rsp+0F0h+var_D0], r13
0x18002d850  lea     rdx, aPrecondition; "preCondition"
0x18002d857  mov     rax, [rcx]
0x18002d85a  mov     rax, [rax+40h]
0x18002d85e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d863  mov     ebx, eax
0x18002d865  test    eax, eax
0x18002d867  js      loc_18002DA24
0x18002d86d  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002d874  lea     r8, [rbp+3Fh+var_6C]
0x18002d878  mov     rdx, [rbp+3Fh+var_80]
0x18002d87c  mov     rax, [rcx]
0x18002d87f  mov     rax, [rax+0B0h]
0x18002d886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d88b  cmp     [rbp+3Fh+var_6C], r13d
0x18002d88f  jnz     loc_18002DAAE
0x18002d895  test    eax, eax
0x18002d897  jnz     short loc_18002D8CC
0x18002d899  mov     rcx, [rbp+3Fh+arg_48]
0x18002d8a0  lea     r8d, [rax+4]
0x18002d8a4  xor     edx, edx
0x18002d8a6  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x18002d8ab  test    eax, eax
0x18002d8ad  jz      loc_18002D9AF
0x18002d8b3  mov     r9, [rbp+3Fh+var_80]; unsigned __int16 *
0x18002d8b7  mov     r8, [rbp+3Fh+String2]; unsigned __int16 *
0x18002d8bb  mov     rcx, [rbp+3Fh+arg_48]; struct IHttpTraceContext *
0x18002d8c2  call    ?RaiseEvent@MODULE_PRECONDITION_NOT_MATCH@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2@Z; IISGeneralEvents::MODULE_PRECONDITION_NOT_MATCH::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *)
0x18002d8c7  jmp     loc_18002D9AF
0x18002d8cc  mov     rax, [rbp+3Fh+var_60]
0x18002d8d0  mov     rbx, r13
0x18002d8d3  cmp     [rax], r13w
0x18002d8d7  jnz     short loc_18002D92D
0x18002d8d9  mov     r15, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002d8e0  xor     edi, edi
0x18002d8e2  mov     r13, [rbp+3Fh+String2]
0x18002d8e6  cmp     edi, [r15+260h]
0x18002d8ed  jnb     loc_18002D9CB
0x18002d8f3  lea     rcx, [r15+230h]
0x18002d8fa  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18002d900  mov     rbx, [rax+rdi*8]
0x18002d904  mov     rcx, rbx
0x18002d907  mov     rax, [rbx]
0x18002d90a  mov     rax, [rax]
0x18002d90d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d912  mov     rcx, rax; String1
0x18002d915  mov     rdx, r13; String2
0x18002d918  call    cs:__imp__wcsicmp
0x18002d91e  test    eax, eax
0x18002d920  jz      short loc_18002D926
0x18002d922  inc     edi
0x18002d924  jmp     short loc_18002D8E6
0x18002d926  lock inc dword ptr [rbx+0Ch]
0x18002d92a  xor     r13d, r13d
0x18002d92d  mov     ecx, 28h ; '('; Size
0x18002d932  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d937  mov     rdi, rax
0x18002d93a  test    rax, rax
0x18002d93d  jz      loc_18002DAA4
0x18002d943  mov     qword ptr [rax], 444D5041h
0x18002d94a  mov     ecx, r13d
0x18002d94d  mov     [rax+8], r13
0x18002d951  test    rbx, rbx
0x18002d954  mov     [rax+10h], r13
0x18002d958  mov     [rax+18h], r13
0x18002d95c  setz    cl
0x18002d95f  mov     [rax+20h], r13
0x18002d963  mov     r9, [rbp+3Fh+var_80]; unsigned __int16 *
0x18002d967  mov     r8, [rbp+3Fh+var_60]; unsigned __int16 *
0x18002d96b  mov     rdx, [rbp+3Fh+String2]; unsigned __int16 *
0x18002d96f  mov     [rsp+0F0h+var_C8], ecx; int
0x18002d973  mov     rcx, rax; this
0x18002d976  mov     [rsp+0F0h+var_D0], rbx; struct VIRTUAL_MODULE *
0x18002d97b  call    ?Create@APPLICATION_MODULE@@QEAAJPEBG00PEAVVIRTUAL_MODULE@@H@Z; APPLICATION_MODULE::Create(ushort const *,ushort const *,ushort const *,VIRTUAL_MODULE *,int)
0x18002d980  mov     ebx, eax
0x18002d982  test    eax, eax
0x18002d984  js      loc_18002DA9A
0x18002d98a  lea     rcx, [rsi+0E0h]; this
  ... truncated ...
```
