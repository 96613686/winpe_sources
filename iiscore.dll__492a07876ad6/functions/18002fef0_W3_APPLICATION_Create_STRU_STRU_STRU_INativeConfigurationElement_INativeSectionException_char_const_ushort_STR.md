# W3_APPLICATION::Create(STRU &,STRU &,STRU &,INativeConfigurationElement *,INativeSectionException * *,char const *,ushort,STRU *,IHttpTraceContext *)

- ea: `0x18002fef0`
- end: `0x1800306a6`
- name: `?Create@W3_APPLICATION@@QEAAJAEAVSTRU@@00PEAVINativeConfigurationElement@@PEAPEAVINativeSectionException@@PEBDGPEAV2@PEAVIHttpTraceContext@@@Z`
- size: `1974`
- prototype: `int __fastcall(W3_APPLICATION *this, struct STRU *, struct STRU *, struct STRU *, struct INativeConfigurationElement *, struct INativeSectionException **, const char *, unsigned __int16, struct STRU *, struct IHttpTraceContext *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180030738`

## callees

- `0x180009030`
- `0x18001ab30`
- `0x18002136c`
- `0x18002fdb0`
- `0x18002fef0`
- `0x180031054`
- `0x180033310`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002ff99`
- `msvcrt!_wcsicmp` at `0x180030366`
- `msvcrt!_wcsicmp` at `0x18002ff99`
- `msvcrt!_wcsicmp` at `0x180030366`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180030342`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180030342`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180030695`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180030695`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003001c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180030103`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800305a7`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18003001c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180030103`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800305a7`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180030456`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180030549`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180030456`
- `iisutil!?GetString@LANG_STRING@@QEAAJPEBDKIPEAPEBGPEAK@Z` at `0x180030549`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002ffb7`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002ffd2`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002fff0`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002ffb7`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002ffd2`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18002fff0`
- `iisutil!SAFE_snwprintf` at `0x180030478`
- `iisutil!SAFE_snwprintf` at `0x180030570`
- `iisutil!SAFE_snwprintf` at `0x180030478`
- `iisutil!SAFE_snwprintf` at `0x180030570`

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
0x18002fef0  mov     [rsp-8+arg_8], rdx
0x18002fef5  push    rbp
0x18002fef6  push    rbx
0x18002fef7  push    rsi
0x18002fef8  push    rdi
0x18002fef9  push    r12
0x18002fefb  push    r13
0x18002fefd  push    r14
0x18002feff  push    r15
0x18002ff01  lea     rbp, [rsp-7]
0x18002ff06  sub     rsp, 0B8h
0x18002ff0d  xor     r13d, r13d
0x18002ff10  mov     rsi, rcx
0x18002ff13  mov     rcx, [rbp+3Fh+arg_20]
0x18002ff17  mov     rdi, r9
0x18002ff1a  mov     rbx, r8
0x18002ff1d  mov     [rbp+3Fh+var_A0], r13
0x18002ff21  mov     r15, rdx
0x18002ff24  mov     [rbp+3Fh+var_88], r13
0x18002ff28  xor     r9d, r9d
0x18002ff2b  mov     [rbp+3Fh+var_78], r13
0x18002ff2f  mov     rax, [rcx]
0x18002ff32  lea     r8, [rbp+3Fh+String1]
0x18002ff36  lea     rdx, aApplicationpoo; "applicationPool"
0x18002ff3d  mov     [rbp+3Fh+var_90], r13
0x18002ff41  mov     [rbp+3Fh+var_A8], r13
0x18002ff45  mov     [rbp+3Fh+String2], r13
0x18002ff49  mov     rax, [rax+40h]
0x18002ff4d  mov     [rbp+3Fh+var_60], r13
0x18002ff51  mov     [rbp+3Fh+var_80], r13
0x18002ff55  mov     [rbp+3Fh+var_70], r13d
0x18002ff59  mov     [rbp+3Fh+String1], r13
0x18002ff5d  mov     [rbp+3Fh+var_6C], r13d
0x18002ff61  mov     [rbp+3Fh+var_B0], r13d
0x18002ff65  mov     [rbp+3Fh+var_68], r13d
0x18002ff69  mov     [rbp+3Fh+var_58], r13
0x18002ff6d  mov     [rsp+0F0h+var_D0], r13
0x18002ff72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff77  test    eax, eax
0x18002ff79  js      loc_1800304E6
0x18002ff7f  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18002ff86  mov     rax, [rcx]
0x18002ff89  mov     rax, [rax+8]
0x18002ff8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff92  mov     rcx, [rbp+3Fh+String1]; String1
0x18002ff96  mov     rdx, rax; String2
0x18002ff99  call    cs:__imp__wcsicmp
0x18002ffa0  nop     dword ptr [rax+rax+00h]
0x18002ffa5  lea     rcx, [rsi+20h]
0x18002ffa9  mov     rdx, r15
0x18002ffac  test    eax, eax
0x18002ffae  setz    al
0x18002ffb1  mov     [rsi+0D9h], al
0x18002ffb7  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002ffbe  nop     dword ptr [rax+rax+00h]
0x18002ffc3  test    eax, eax
0x18002ffc5  js      loc_1800304E6
0x18002ffcb  lea     rcx, [rsi+58h]
0x18002ffcf  mov     rdx, rbx
0x18002ffd2  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002ffd9  nop     dword ptr [rax+rax+00h]
0x18002ffde  test    eax, eax
0x18002ffe0  js      loc_1800304E6
0x18002ffe6  lea     rcx, [rsi+90h]
0x18002ffed  mov     rdx, rdi
0x18002fff0  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x18002fff7  nop     dword ptr [rax+rax+00h]
0x18002fffc  test    eax, eax
0x18002fffe  js      loc_1800304E6
0x180030004  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18003000b  mov     rcx, r15
0x18003000e  mov     rdi, [rax+5D8h]
0x180030015  mov     rax, [rdi]
0x180030018  mov     rbx, [rax+18h]
0x18003001c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180030023  nop     dword ptr [rax+rax+00h]
0x180030028  mov     r12, [rbp+3Fh+arg_28]
0x18003002c  lea     r9, [rbp+3Fh+var_A0]
0x180030030  mov     r8, rax
0x180030033  mov     qword ptr [rsp+0F0h+var_C8], r13
0x180030038  mov     rax, rbx
0x18003003b  mov     [rsp+0F0h+var_D0], r12
0x180030040  lea     rdx, aSystemWebserve_4; "system.webServer/serverRuntime"
0x180030047  mov     rcx, rdi
0x18003004a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003004f  mov     ebx, eax
0x180030051  test    eax, eax
0x180030053  js      loc_180030484
0x180030059  mov     rcx, [rbp+3Fh+var_A0]
0x18003005d  lea     r8, [rbp+3Fh+var_B0]
0x180030061  xor     r9d, r9d
0x180030064  mov     [rsp+0F0h+var_D0], r13
0x180030069  lea     rdx, aEnabled; "enabled"
0x180030070  mov     rax, [rcx]
0x180030073  mov     rax, [rax+48h]
0x180030077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003007c  mov     ebx, eax
0x18003007e  test    eax, eax
0x180030080  js      loc_180030484
0x180030086  cmp     [rbp+3Fh+var_B0], r13d
0x18003008a  mov     rcx, [rbp+3Fh+var_A0]
0x18003008e  setnz   al
0x180030091  mov     [rsi+0D8h], al
0x180030097  test    al, al
0x180030099  mov     rax, [rcx]
0x18003009c  jnz     short loc_1800300AE
0x18003009e  mov     rax, [rax+10h]
0x1800300a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300a7  xor     eax, eax
0x1800300a9  jmp     loc_1800304E6
0x1800300ae  mov     rax, [rax+30h]
0x1800300b2  lea     r8, [rsi+0D0h]
0x1800300b9  xor     r9d, r9d
0x1800300bc  mov     [rsp+0F0h+var_D0], r13
0x1800300c1  lea     rdx, aAppconcurrentr; "appConcurrentRequestLimit"
0x1800300c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300cd  mov     ebx, eax
0x1800300cf  test    eax, eax
0x1800300d1  js      loc_180030484
0x1800300d7  mov     rcx, [rbp+3Fh+var_A0]
0x1800300db  mov     rax, [rcx]
0x1800300de  mov     rax, [rax+10h]
0x1800300e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300e7  mov     rax, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800300ee  mov     rcx, r15
0x1800300f1  mov     [rbp+3Fh+var_A0], r13
0x1800300f5  mov     rdi, [rax+5D8h]
0x1800300fc  mov     rax, [rdi]
0x1800300ff  mov     rbx, [rax+18h]
0x180030103  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18003010a  nop     dword ptr [rax+rax+00h]
0x18003010f  mov     qword ptr [rsp+0F0h+var_C8], r13
0x180030114  lea     r9, [rbp+3Fh+var_88]
0x180030118  mov     r8, rax
0x18003011b  mov     [rsp+0F0h+var_D0], r12
0x180030120  mov     rax, rbx
0x180030123  lea     rdx, aSystemWebserve_0; "system.webServer/modules"
0x18003012a  mov     rcx, rdi
0x18003012d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030132  mov     ebx, eax
0x180030134  test    eax, eax
0x180030136  js      loc_180030484
0x18003013c  mov     rcx, [rbp+3Fh+var_88]
0x180030140  lea     r8, [rbp+3Fh+var_B0]
0x180030144  xor     r9d, r9d
0x180030147  mov     [rsp+0F0h+var_D0], r13
0x18003014c  lea     rdx, aRunallmanagedm; "runAllManagedModulesForAllRequests"
0x180030153  mov     rax, [rcx]
0x180030156  mov     rax, [rax+48h]
0x18003015a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003015f  mov     ebx, eax
0x180030161  test    eax, eax
0x180030163  js      loc_180030484
0x180030169  cmp     [rbp+3Fh+var_B0], r13d
0x18003016d  lea     r8, [rbp+3Fh+var_B0]
0x180030171  mov     rcx, [rbp+3Fh+var_88]
0x180030175  lea     rdx, aRunmanagedmodu; "runManagedModulesForWebDavRequests"
0x18003017c  setnz   al
0x18003017f  mov     [rsp+0F0h+var_D0], r13
0x180030184  mov     [rsi+0DCh], al
0x18003018a  xor     r9d, r9d
0x18003018d  mov     rax, [rcx]
0x180030190  mov     rax, [rax+48h]
0x180030194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030199  mov     ebx, eax
0x18003019b  test    eax, eax
0x18003019d  js      loc_180030484
0x1800301a3  cmp     [rbp+3Fh+var_B0], r13d
0x1800301a7  lea     rdx, [rbp+3Fh+var_90]
0x1800301ab  mov     rcx, [rbp+3Fh+var_88]
0x1800301af  setnz   al
0x1800301b2  mov     [rsi+0DDh], al
0x1800301b8  mov     rax, [rcx]
0x1800301bb  mov     rax, [rax+28h]
0x1800301bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301c4  mov     rcx, [rbp+3Fh+var_88]
0x1800301c8  mov     ebx, eax
0x1800301ca  mov     rax, [rcx]
0x1800301cd  mov     rax, [rax+10h]
0x1800301d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301d6  mov     [rbp+3Fh+var_88], r13
0x1800301da  test    ebx, ebx
0x1800301dc  js      loc_180030484
0x1800301e2  mov     rcx, [rbp+3Fh+var_90]
0x1800301e6  lea     rdx, [rbp+3Fh+var_70]
0x1800301ea  mov     rax, [rcx]
0x1800301ed  mov     rax, [rax+18h]
0x1800301f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301f6  mov     ebx, eax
0x1800301f8  test    eax, eax
0x1800301fa  js      loc_180030484
0x180030200  mov     r14d, r13d
0x180030203  mov     rcx, [rbp+3Fh+var_90]
0x180030207  mov     rax, [rcx]
0x18003020a  cmp     r14d, [rbp+3Fh+var_70]
0x18003020e  jnb     loc_180030581
0x180030214  mov     rax, [rax+20h]
0x180030218  lea     r8, [rbp+3Fh+var_A8]
0x18003021c  mov     edx, r14d
0x18003021f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030224  mov     ebx, eax
0x180030226  test    eax, eax
0x180030228  js      loc_180030484
0x18003022e  mov     rcx, [rbp+3Fh+var_A8]
0x180030232  lea     r8, [rbp+3Fh+String2]
0x180030236  xor     r9d, r9d
0x180030239  mov     [rsp+0F0h+var_D0], r13
0x18003023e  lea     rdx, aName_0; "name"
0x180030245  mov     rax, [rcx]
0x180030248  mov     rax, [rax+40h]
0x18003024c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030251  mov     ebx, eax
0x180030253  test    eax, eax
0x180030255  js      loc_180030484
0x18003025b  mov     rcx, [rbp+3Fh+var_A8]
0x18003025f  lea     r8, [rbp+3Fh+var_60]
0x180030263  xor     r9d, r9d
0x180030266  mov     [rsp+0F0h+var_D0], r13
0x18003026b  lea     rdx, aType; "type"
0x180030272  mov     rax, [rcx]
0x180030275  mov     rax, [rax+40h]
0x180030279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003027e  mov     ebx, eax
0x180030280  test    eax, eax
0x180030282  js      loc_180030484
0x180030288  mov     rcx, [rbp+3Fh+var_A8]
0x18003028c  lea     r8, [rbp+3Fh+var_80]
0x180030290  xor     r9d, r9d
0x180030293  mov     [rsp+0F0h+var_D0], r13
0x180030298  lea     rdx, aPrecondition; "preCondition"
0x18003029f  mov     rax, [rcx]
0x1800302a2  mov     rax, [rax+40h]
0x1800302a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302ab  mov     ebx, eax
0x1800302ad  test    eax, eax
0x1800302af  js      loc_180030484
0x1800302b5  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800302bc  lea     r8, [rbp+3Fh+var_6C]
0x1800302c0  mov     rdx, [rbp+3Fh+var_80]
0x1800302c4  mov     rax, [rcx]
0x1800302c7  mov     rax, [rax+0B0h]
0x1800302ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302d3  cmp     [rbp+3Fh+var_6C], r13d
0x1800302d7  jnz     loc_180030512
0x1800302dd  test    eax, eax
0x1800302df  jnz     short loc_180030314
0x1800302e1  mov     rcx, [rbp+3Fh+arg_48]
0x1800302e8  lea     r8d, [rax+4]
0x1800302ec  xor     edx, edx
0x1800302ee  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x1800302f3  test    eax, eax
0x1800302f5  jz      loc_180030403
0x1800302fb  mov     r9, [rbp+3Fh+var_80]; unsigned __int16 *
0x1800302ff  mov     r8, [rbp+3Fh+String2]; unsigned __int16 *
0x180030303  mov     rcx, [rbp+3Fh+arg_48]; struct IHttpTraceContext *
0x18003030a  call    ?RaiseEvent@MODULE_PRECONDITION_NOT_MATCH@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@PEBG2@Z; IISGeneralEvents::MODULE_PRECONDITION_NOT_MATCH::RaiseEvent(IHttpTraceContext *,_GUID const *,ushort const *,ushort const *)
0x18003030f  jmp     loc_180030403
0x180030314  mov     rax, [rbp+3Fh+var_60]
0x180030318  mov     rbx, r13
0x18003031b  cmp     [rax], r13w
0x18003031f  jnz     short loc_180030381
0x180030321  mov     r15, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180030328  xor     edi, edi
0x18003032a  mov     r13, [rbp+3Fh+String2]
0x18003032e  cmp     edi, [r15+260h]
0x180030335  jnb     loc_18003041F
0x18003033b  lea     rcx, [r15+230h]
0x180030342  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180030349  nop     dword ptr [rax+rax+00h]
0x18003034e  mov     rbx, [rax+rdi*8]
0x180030352  mov     rcx, rbx
0x180030355  mov     rax, [rbx]
0x180030358  mov     rax, [rax]
0x18003035b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030360  mov     rcx, rax; String1
0x180030363  mov     rdx, r13; String2
0x180030366  call    cs:__imp__wcsicmp
0x18003036d  nop     dword ptr [rax+rax+00h]
0x180030372  test    eax, eax
0x180030374  jz      short loc_18003037A
0x180030376  inc     edi
0x180030378  jmp     short loc_18003032E
0x18003037a  lock inc dword ptr [rbx+0Ch]
0x18003037e  xor     r13d, r13d
0x180030381  mov     ecx, 28h ; '('; Size
0x180030386  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003038b  mov     rdi, rax
0x18003038e  test    rax, rax
0x180030391  jz      loc_180030508
0x180030397  mov     qword ptr [rax], 444D5041h
0x18003039e  mov     ecx, r13d
0x1800303a1  mov     [rax+8], r13
0x1800303a5  test    rbx, rbx
0x1800303a8  mov     [rax+10h], r13
0x1800303ac  mov     [rax+18h], r13
0x1800303b0  setz    cl
0x1800303b3  mov     [rax+20h], r13
0x1800303b7  mov     r9, [rbp+3Fh+var_80]; unsigned __int16 *
0x1800303bb  mov     r8, [rbp+3Fh+var_60]; unsigned __int16 *
0x1800303bf  mov     rdx, [rbp+3Fh+String2]; unsigned __int16 *
  ... truncated ...
```
