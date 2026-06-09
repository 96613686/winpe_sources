# FREB_META_STORED_CONTEXT::Initialize(ushort const *,FREB_FAILURE_POINT *,STRU *,INativeSectionException * *)

- ea: `0x180005b28`
- end: `0x18000634b`
- name: `?Initialize@FREB_META_STORED_CONTEXT@@QEAAJPEBGPEAW4FREB_FAILURE_POINT@@PEAVSTRU@@PEAPEAVINativeSectionException@@@Z`
- size: `2083`
- prototype: `__int64 __fastcall(FREB_META_STORED_CONTEXT *this, const unsigned __int16 *, enum FREB_FAILURE_POINT *, struct STRU *, struct INativeSectionException **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180003654`
- `0x180005980`

## callees

- `0x180001008`
- `0x180005974`
- `0x180005b28`
- `0x180006354`
- `0x180007a80`
- `0x180007d28`
- `0x180007e6c`
- `0x18000b010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800061ff`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800061ff`
- `iisutil!PuDbgPrintError` at `0x18000632f`
- `iisutil!PuDbgPrintError` at `0x18000632f`

## string_xrefs

- `0x18000630b`: `Failed to initialize freb configuration\n`
- `0x180006328`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_meta_context.cxx`

## pseudocode

```c
__int64 __fastcall FREB_META_STORED_CONTEXT::Initialize(
        FREB_META_STORED_CONTEXT *this,
        const unsigned __int16 *a2,
        enum FREB_FAILURE_POINT *a3,
        struct STRU *a4,
        struct INativeSectionException **a5)
{
  int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rax
  unsigned int v10; // r14d
  __int64 v11; // rbx
  __int64 v12; // rax
  bool v13; // cf
  size_t v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rdi
  TRACE_URLS_STORED_ENTRY *v17; // rsi
  unsigned int v18; // esi
  __int64 v19; // rdi
  __int64 v20; // rsi
  unsigned int v21; // r12d
  __int64 v22; // rbx
  TRACE_AREAS_STORED_ENTRY *v23; // rax
  TRACE_AREAS_STORED_ENTRY *v24; // r14
  TRACE_AREAS_STORED_ENTRY *v25; // rdi
  unsigned int i; // edi
  __int64 v27; // rax
  __int64 v28; // r8
  int v29; // edx
  __int64 v30; // r9
  struct _GUID *v31; // rcx
  struct _GUID v32; // xmm0
  unsigned __int16 *v33; // rdx
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v36; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v37; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  __int64 v42; // [rsp+90h] [rbp-70h] BYREF
  int v43; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v44; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v45; // [rsp+A0h] [rbp-60h] BYREF
  int v46; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v47; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v48; // [rsp+ACh] [rbp-54h]
  __int64 v49; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v51; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v52; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v53; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v54; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 *v55; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v56; // [rsp+E8h] [rbp-18h] BYREF
  unsigned __int16 *v57; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v58; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 *v59; // [rsp+100h] [rbp+0h] BYREF
  struct _GUID *v60; // [rsp+108h] [rbp+8h] BYREF

  v52 = (unsigned __int16 *)&qword_18000E008;
  v42 = 0;
  v51 = 0;
  v49 = 0;
  v40 = 0;
  v38 = 0;
  v35 = 0;
  v39 = 0;
  v41 = 0;
  v50 = 0;
  v37 = 0;
  v36 = 0;
  v8 = FREB_META_STORED_CONTEXT::InitializeTraceProviderDefinitions(this, a2, a5);
  if ( (int)(v8 + 0x80000000) >= 0 && v8 != -2147023728 )
    goto LABEL_52;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v8 = (**v9)(v9, &IID_INativeConfigurationSystem, &v42);
  if ( v8 < 0 )
    goto LABEL_52;
  v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, __int64 *, struct INativeSectionException **, __int64 *))(*(_QWORD *)v42 + 24LL))(
         v42,
         L"system.webServer/tracing/traceFailedRequests",
         a2,
         &v51,
         a5,
         &v50);
  if ( v8 < 0 )
    goto LABEL_52;
  (*(void (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v50 + 24LL))(v50, &v52);
  v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 40LL))(v51, &v49);
  if ( v8 < 0 )
    goto LABEL_52;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v49 + 24LL))(v49, &v37);
  if ( v8 < 0 )
    goto LABEL_52;
  v10 = v37;
  v11 = v37;
  v12 = 224LL * v37;
  if ( !is_mul_ok(v37, 0xE0u) )
    v12 = -1;
  v13 = __CFADD__(v12, 8);
  v14 = v12 + 8;
  if ( v13 )
    v14 = -1;
  v15 = operator new(v14);
  if ( !v15 )
  {
    *((_QWORD *)this + 1) = 0;
LABEL_51:
    v8 = -2147024888;
    goto LABEL_52;
  }
  *v15 = v11;
  v16 = v15 + 1;
  v17 = (TRACE_URLS_STORED_ENTRY *)(v15 + 1);
  if ( v10 )
  {
    do
    {
      TRACE_URLS_STORED_ENTRY::TRACE_URLS_STORED_ENTRY(v17);
      v17 = (TRACE_URLS_STORED_ENTRY *)((char *)v17 + 224);
      --v11;
    }
    while ( v11 );
  }
  *((_QWORD *)this + 1) = v16;
  if ( !v16 )
    goto LABEL_51;
  v18 = 0;
  *((_DWORD *)this + 4) = v10;
  v48 = 0;
  if ( v37 )
  {
    while ( 1 )
    {
      v56 = 0;
      v59 = 0;
      v55 = 0;
      v44 = 0;
      v58 = 0;
      v57 = 0;
      v45 = 0;
      v43 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v49 + 32LL))(v49, v18, &v35);
      if ( v8 < 0 )
        break;
      v19 = *((_QWORD *)this + 1);
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v35 + 64LL))(
             v35,
             L"path",
             &v59,
             0,
             0);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v35 + 64LL))(
             v35,
             L"customActionExe",
             &v58,
             0,
             0);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v35 + 64LL))(
             v35,
             L"customActionParams",
             &v57,
             0,
             0);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v35 + 48LL))(
             v35,
             L"customActionTriggerLimit",
             &v45,
             0,
             0);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v35 + 32LL))(
             v35,
             L"failureDefinitions",
             &v38);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int64 *, _QWORD, _QWORD))(*(_QWORD *)v38 + 80LL))(
             v38,
             L"timeTaken",
             &v56,
             0,
             0);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v38 + 72LL))(
             v38,
             L"traceAllAfterTimeout",
             &v43,
             0,
             0);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v38 + 64LL))(
             v38,
             L"statusCodes",
             &v55,
             0,
             0);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *, _QWORD, _QWORD))(*(_QWORD *)v38 + 48LL))(
             v38,
             L"verbosity",
             &v44,
             0,
             0);
      if ( v8 < 0 )
        break;
      v20 = v19 + 224LL * v18;
      v8 = TRACE_URLS_STORED_ENTRY::Initialize(
             (TRACE_URLS_STORED_ENTRY *)v20,
             v59,
             v58,
             v57,
             v45,
             v56,
             v55,
             v44,
             v52,
             a3,
             v43);
      if ( v8 < 0 )
      {
        if ( *(_DWORD *)a3 == 3 )
        {
          v33 = v55;
LABEL_49:
          STRU::Copy(a4, v33);
        }
        break;
      }
      v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v35 + 32LL))(
             v35,
             L"traceAreas",
             &v41);
      if ( v8 < 0 )
        break;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      v35 = 0;
      v8 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v41 + 40LL))(v41, &v40);
      if ( v8 < 0 )
        break;
      v8 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v40 + 24))(v40, &v36);
      if ( v8 < 0 )
        break;
      v21 = v36;
      v22 = v36;
      v23 = (TRACE_AREAS_STORED_ENTRY *)operator new(saturated_mul(v36, 0x28u));
      v24 = v23;
      if ( !v23 )
      {
        *(_QWORD *)(v20 + 208) = 0;
        goto LABEL_51;
      }
      v25 = v23;
      if ( v21 )
      {
        do
        {
          TRACE_AREAS_STORED_ENTRY::TRACE_AREAS_STORED_ENTRY(v25);
          v25 = (TRACE_AREAS_STORED_ENTRY *)((char *)v25 + 40);
          --v22;
        }
        while ( v22 );
      }
      *(_DWORD *)(v20 + 216) = v21;
      *(_QWORD *)(v20 + 208) = v24;
      for ( i = 0; i < v36; v39 = 0 )
      {
        v54 = 0;
        v53 = 0;
        v46 = 0;
        v27 = *v40;
        v60 = 0;
        v47 = 0;
        v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v27 + 32))(v40, i, &v39);
        if ( v8 < 0 )
          goto LABEL_52;
        v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v39 + 64LL))(
               v39,
               L"areas",
               &v54,
               0,
               0);
        if ( v8 < 0 )
          goto LABEL_52;
        v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v39 + 64LL))(
               v39,
               L"provider",
               &v53,
               0,
               0);
        if ( v8 < 0 )
          goto LABEL_52;
        v8 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v39 + 48LL))(
               v39,
               L"verbosity",
               &v46,
               0,
               0);
        if ( v8 < 0 )
          goto LABEL_52;
        v8 = PROVIDER_DEFINITIONS_STORED_LIST::TranslateProviderNameAndAreas(
               (FREB_META_STORED_CONTEXT *)((char *)this + 24),
               v53,
               v54,
               &v60,
               &v47,
               v52,
               a3);
        if ( v8 < 0 )
        {
          if ( *(_DWORD *)a3 == 1 )
          {
            v33 = v54;
          }
          else
          {
            if ( *(_DWORD *)a3 != 2 )
              goto LABEL_52;
            v33 = v53;
          }
          goto LABEL_49;
        }
        v28 = *(_QWORD *)(v20 + 208);
        v29 = v46;
        v30 = 5LL * i;
        v31 = (struct _GUID *)(v28 + 8 * (v30 + 3));
        v32 = *v60;
        *(_DWORD *)(v28 + 8 * v30 + 8) = v47;
        *v31 = v32;
        *(_QWORD *)(v28 + 8 * v30) = v31;
        *(_DWORD *)(v28 + 8 * v30 + 12) = v29;
        *(_DWORD *)(v28 + 8 * v30 + 16) = 1;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        ++i;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
      v38 = 0;
      (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
      v40 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      v18 = v48 + 1;
      v41 = 0;
      v48 = v18;
      if ( v18 >= v37 )
        goto LABEL_41;
    }
  }
  else
  {
LABEL_41:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
    v8 = 0;
  }
LABEL_52:
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
    v40 = 0;
  }
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v51 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
  }
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    v42 = 0;
  }
  if ( v8 < 0 && (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_meta_context.cxx",
      600,
      "FREB_META_STORED_CONTEXT::Initialize",
      v8,
      "Failed to initialize freb configuration\n");
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005b28  mov     [rsp-8+arg_18], r9
0x180005b2d  push    rbp
0x180005b2e  push    rbx
0x180005b2f  push    rsi
0x180005b30  push    rdi
0x180005b31  push    r12
0x180005b33  push    r13
0x180005b35  push    r14
0x180005b37  push    r15
0x180005b39  lea     rbp, [rsp-18h]
0x180005b3e  sub     rsp, 118h
0x180005b45  mov     rsi, [rbp+50h+arg_20]
0x180005b4c  lea     rax, qword_18000E008
0x180005b53  xor     r12d, r12d
0x180005b56  mov     [rbp+50h+var_88], rax
0x180005b5a  mov     r13, r8
0x180005b5d  mov     [rbp+50h+var_C0], r12
0x180005b61  mov     r8, rsi; struct INativeSectionException **
0x180005b64  mov     [rbp+50h+var_90], r12
0x180005b68  mov     rdi, rdx
0x180005b6b  mov     [rbp+50h+var_A0], r12
0x180005b6f  mov     r15, rcx
0x180005b72  mov     [rbp+50h+var_D0], r12
0x180005b76  mov     [rsp+150h+var_E0], r12
0x180005b7b  mov     [rsp+150h+var_F0], r12
0x180005b80  mov     [rsp+150h+var_D8], r12
0x180005b85  mov     [rbp+50h+var_C8], r12
0x180005b89  mov     [rbp+50h+var_98], r12
0x180005b8d  mov     [rsp+150h+var_E4], r12d
0x180005b92  mov     [rsp+150h+var_E8], r12d
0x180005b97  call    ?InitializeTraceProviderDefinitions@FREB_META_STORED_CONTEXT@@AEAAJPEBGPEAPEAVINativeSectionException@@@Z; FREB_META_STORED_CONTEXT::InitializeTraceProviderDefinitions(ushort const *,INativeSectionException * *)
0x180005b9c  mov     ebx, eax
0x180005b9e  mov     eax, 80000000h
0x180005ba3  lea     ecx, [rbx+rax]
0x180005ba6  test    eax, ecx
0x180005ba8  jnz     short loc_180005BB6
0x180005baa  cmp     ebx, 80070490h
0x180005bb0  jnz     loc_180006210
0x180005bb6  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180005bbd  mov     rax, [rcx]
0x180005bc0  mov     rax, [rax+38h]
0x180005bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc9  mov     r9, rax
0x180005bcc  lea     r8, [rbp+50h+var_C0]
0x180005bd0  lea     rdx, IID_INativeConfigurationSystem
0x180005bd7  mov     rcx, [rax]
0x180005bda  mov     rax, [rcx]
0x180005bdd  mov     rcx, r9
0x180005be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be5  mov     ebx, eax
0x180005be7  test    eax, eax
0x180005be9  js      loc_180006210
0x180005bef  mov     rcx, [rbp+50h+var_C0]
0x180005bf3  lea     rdx, [rbp+50h+var_98]
0x180005bf7  mov     [rsp+150h+var_128], rdx
0x180005bfc  lea     r9, [rbp+50h+var_90]
0x180005c00  mov     r8, rdi
0x180005c03  mov     [rsp+150h+var_130], rsi
0x180005c08  lea     rdx, aSystemWebserve_0; "system.webServer/tracing/traceFailedReq"...
0x180005c0f  mov     rax, [rcx]
0x180005c12  mov     rax, [rax+18h]
0x180005c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c1b  mov     ebx, eax
0x180005c1d  test    eax, eax
0x180005c1f  js      loc_180006210
0x180005c25  mov     rcx, [rbp+50h+var_98]
0x180005c29  lea     rdx, [rbp+50h+var_88]
0x180005c2d  mov     rax, [rcx]
0x180005c30  mov     rax, [rax+18h]
0x180005c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c39  mov     rcx, [rbp+50h+var_90]
0x180005c3d  lea     rdx, [rbp+50h+var_A0]
0x180005c41  mov     rax, [rcx]
0x180005c44  mov     rax, [rax+28h]
0x180005c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4d  mov     ebx, eax
0x180005c4f  test    eax, eax
0x180005c51  js      loc_180006210
0x180005c57  mov     rcx, [rbp+50h+var_A0]
0x180005c5b  lea     rdx, [rsp+150h+var_E4]
0x180005c60  mov     rax, [rcx]
0x180005c63  mov     rax, [rax+18h]
0x180005c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c6c  mov     ebx, eax
0x180005c6e  test    eax, eax
0x180005c70  js      loc_180006210
0x180005c76  mov     r14d, [rsp+150h+var_E4]
0x180005c7b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005c82  mov     eax, 0E0h
0x180005c87  mov     ebx, r14d
0x180005c8a  mul     r14
0x180005c8d  cmovb   rax, rcx
0x180005c91  add     rax, 8
0x180005c95  cmovb   rax, rcx
0x180005c99  mov     rcx, rax; Size
0x180005c9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005ca1  test    rax, rax
0x180005ca4  jz      loc_180006207
0x180005caa  mov     [rax], rbx
0x180005cad  lea     rdi, [rax+8]
0x180005cb1  mov     rsi, rdi
0x180005cb4  test    r14d, r14d
0x180005cb7  jz      short loc_180005CCE
0x180005cb9  mov     rcx, rsi; this
0x180005cbc  call    ??0TRACE_URLS_STORED_ENTRY@@QEAA@XZ; TRACE_URLS_STORED_ENTRY::TRACE_URLS_STORED_ENTRY(void)
0x180005cc1  add     rsi, 0E0h
0x180005cc8  sub     rbx, 1
0x180005ccc  jnz     short loc_180005CB9
0x180005cce  mov     [r15+8], rdi
0x180005cd2  test    rdi, rdi
0x180005cd5  jz      loc_18000620B
0x180005cdb  mov     esi, r12d
0x180005cde  mov     [r15+10h], r14d
0x180005ce2  mov     [rbp+50h+var_A4], r12d
0x180005ce6  cmp     [rsp+150h+var_E4], r12d
0x180005ceb  jbe     loc_1800061B1
0x180005cf1  mov     rcx, [rbp+50h+var_A0]
0x180005cf5  lea     r8, [rsp+150h+var_F0]
0x180005cfa  mov     [rbp+50h+var_68], r12
0x180005cfe  mov     edx, esi
0x180005d00  mov     [rbp+50h+var_50], r12
0x180005d04  mov     [rbp+50h+var_70], r12
0x180005d08  mov     [rbp+50h+var_B4], r12d
0x180005d0c  mov     [rbp+50h+var_58], r12
0x180005d10  mov     [rbp+50h+var_60], r12
0x180005d14  mov     [rbp+50h+var_B0], r12d
0x180005d18  mov     [rbp+50h+var_B8], r12d
0x180005d1c  mov     rax, [rcx]
0x180005d1f  mov     rax, [rax+20h]
0x180005d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d28  mov     ebx, eax
0x180005d2a  test    eax, eax
0x180005d2c  js      loc_180006210
0x180005d32  mov     rcx, [rsp+150h+var_F0]
0x180005d37  lea     r8, [rbp+50h+var_50]
0x180005d3b  mov     rdi, [r15+8]
0x180005d3f  lea     rdx, aPath; "path"
0x180005d46  xor     r9d, r9d
0x180005d49  mov     [rsp+150h+var_130], r12
0x180005d4e  mov     rax, [rcx]
0x180005d51  mov     rax, [rax+40h]
0x180005d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d5a  mov     ebx, eax
0x180005d5c  test    eax, eax
0x180005d5e  js      loc_180006210
0x180005d64  mov     rcx, [rsp+150h+var_F0]
0x180005d69  lea     r8, [rbp+50h+var_58]
0x180005d6d  xor     r9d, r9d
0x180005d70  mov     [rsp+150h+var_130], r12
0x180005d75  lea     rdx, aCustomactionex; "customActionExe"
0x180005d7c  mov     rax, [rcx]
0x180005d7f  mov     rax, [rax+40h]
0x180005d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d88  mov     ebx, eax
0x180005d8a  test    eax, eax
0x180005d8c  js      loc_180006210
0x180005d92  mov     rcx, [rsp+150h+var_F0]
0x180005d97  lea     r8, [rbp+50h+var_60]
0x180005d9b  xor     r9d, r9d
0x180005d9e  mov     [rsp+150h+var_130], r12
0x180005da3  lea     rdx, aCustomactionpa; "customActionParams"
0x180005daa  mov     rax, [rcx]
0x180005dad  mov     rax, [rax+40h]
0x180005db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db6  mov     ebx, eax
0x180005db8  test    eax, eax
0x180005dba  js      loc_180006210
0x180005dc0  mov     rcx, [rsp+150h+var_F0]
0x180005dc5  lea     r8, [rbp+50h+var_B0]
0x180005dc9  xor     r9d, r9d
0x180005dcc  mov     [rsp+150h+var_130], r12
0x180005dd1  lea     rdx, aCustomactiontr; "customActionTriggerLimit"
0x180005dd8  mov     rax, [rcx]
0x180005ddb  mov     rax, [rax+30h]
0x180005ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005de4  mov     ebx, eax
0x180005de6  test    eax, eax
0x180005de8  js      loc_180006210
0x180005dee  mov     rcx, [rsp+150h+var_F0]
0x180005df3  lea     r8, [rsp+150h+var_E0]
0x180005df8  lea     rdx, aFailuredefinit; "failureDefinitions"
0x180005dff  mov     rax, [rcx]
0x180005e02  mov     rax, [rax+20h]
0x180005e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e0b  mov     ebx, eax
0x180005e0d  test    eax, eax
0x180005e0f  js      loc_180006210
0x180005e15  mov     rcx, [rsp+150h+var_E0]
0x180005e1a  lea     r8, [rbp+50h+var_68]
0x180005e1e  xor     r9d, r9d
0x180005e21  mov     [rsp+150h+var_130], r12
0x180005e26  lea     rdx, aTimetaken_0; "timeTaken"
0x180005e2d  mov     rax, [rcx]
0x180005e30  mov     rax, [rax+50h]
0x180005e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e39  mov     ebx, eax
0x180005e3b  test    eax, eax
0x180005e3d  js      loc_180006210
0x180005e43  mov     rcx, [rsp+150h+var_E0]
0x180005e48  lea     r8, [rbp+50h+var_B8]
0x180005e4c  xor     r9d, r9d
0x180005e4f  mov     [rsp+150h+var_130], r12
0x180005e54  lea     rdx, aTraceallaftert; "traceAllAfterTimeout"
0x180005e5b  mov     rax, [rcx]
0x180005e5e  mov     rax, [rax+48h]
0x180005e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e67  mov     ebx, eax
0x180005e69  test    eax, eax
0x180005e6b  js      loc_180006210
0x180005e71  mov     rcx, [rsp+150h+var_E0]
0x180005e76  lea     r8, [rbp+50h+var_70]
0x180005e7a  xor     r9d, r9d
0x180005e7d  mov     [rsp+150h+var_130], r12
0x180005e82  lea     rdx, aStatuscodes; "statusCodes"
0x180005e89  mov     rax, [rcx]
0x180005e8c  mov     rax, [rax+40h]
0x180005e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e95  mov     ebx, eax
0x180005e97  test    eax, eax
0x180005e99  js      loc_180006210
0x180005e9f  mov     rcx, [rsp+150h+var_E0]
0x180005ea4  lea     r8, [rbp+50h+var_B4]
0x180005ea8  xor     r9d, r9d
0x180005eab  mov     [rsp+150h+var_130], r12
0x180005eb0  lea     rdx, aVerbosity; "verbosity"
0x180005eb7  mov     rax, [rcx]
0x180005eba  mov     rax, [rax+30h]
0x180005ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec3  mov     ebx, eax
0x180005ec5  test    eax, eax
0x180005ec7  js      loc_180006210
0x180005ecd  mov     r9, [rbp+50h+var_60]; unsigned __int16 *
0x180005ed1  mov     r8, [rbp+50h+var_58]; unsigned __int16 *
0x180005ed5  mov     rdx, [rbp+50h+var_50]; unsigned __int16 *
0x180005ed9  mov     eax, esi
0x180005edb  imul    rsi, rax, 0E0h
0x180005ee2  mov     eax, [rbp+50h+var_B8]
0x180005ee5  mov     [rsp+150h+var_100], eax; int
0x180005ee9  add     rsi, rdi
0x180005eec  mov     rax, [rbp+50h+var_88]
0x180005ef0  mov     rcx, rsi; this
0x180005ef3  mov     [rsp+150h+var_108], r13; enum FREB_FAILURE_POINT *
0x180005ef8  mov     [rsp+150h+var_110], rax; unsigned __int16 *
0x180005efd  mov     eax, [rbp+50h+var_B4]
0x180005f00  mov     [rsp+150h+var_118], eax; unsigned int
0x180005f04  mov     rax, [rbp+50h+var_70]
0x180005f08  mov     [rsp+150h+var_120], rax; unsigned __int16 *
0x180005f0d  mov     rax, [rbp+50h+var_68]
0x180005f11  mov     [rsp+150h+var_128], rax; unsigned __int64
0x180005f16  mov     eax, [rbp+50h+var_B0]
0x180005f19  mov     dword ptr [rsp+150h+var_130], eax; unsigned int
0x180005f1d  call    ?Initialize@TRACE_URLS_STORED_ENTRY@@QEAAJPEBG00K_K0K0PEAW4FREB_FAILURE_POINT@@H@Z; TRACE_URLS_STORED_ENTRY::Initialize(ushort const *,ushort const *,ushort const *,ulong,unsigned __int64,ushort const *,ulong,ushort const *,FREB_FAILURE_POINT *,int)
0x180005f22  mov     ebx, eax
0x180005f24  test    eax, eax
0x180005f26  js      loc_1800061F0
0x180005f2c  mov     rcx, [rsp+150h+var_F0]
0x180005f31  lea     r8, [rbp+50h+var_C8]
0x180005f35  lea     rdx, aTraceareas; "traceAreas"
0x180005f3c  mov     rax, [rcx]
0x180005f3f  mov     rax, [rax+20h]
0x180005f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f48  mov     ebx, eax
0x180005f4a  test    eax, eax
0x180005f4c  js      loc_180006210
0x180005f52  mov     rcx, [rsp+150h+var_F0]
0x180005f57  mov     rax, [rcx]
0x180005f5a  mov     rax, [rax+10h]
0x180005f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f63  mov     rcx, [rbp+50h+var_C8]
0x180005f67  lea     rdx, [rbp+50h+var_D0]
0x180005f6b  mov     [rsp+150h+var_F0], r12
0x180005f70  mov     rax, [rcx]
0x180005f73  mov     rax, [rax+28h]
0x180005f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f7c  mov     ebx, eax
0x180005f7e  test    eax, eax
0x180005f80  js      loc_180006210
0x180005f86  mov     rcx, [rbp+50h+var_D0]
0x180005f8a  lea     rdx, [rsp+150h+var_E8]
0x180005f8f  mov     rax, [rcx]
0x180005f92  mov     rax, [rax+18h]
0x180005f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f9b  mov     ebx, eax
0x180005f9d  test    eax, eax
0x180005f9f  js      loc_180006210
0x180005fa5  mov     r12d, [rsp+150h+var_E8]
0x180005faa  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180005fb1  mov     eax, 28h ; '('
0x180005fb6  mov     ebx, r12d
0x180005fb9  mul     r12
0x180005fbc  cmovb   rax, rcx
0x180005fc0  mov     rcx, rax; Size
0x180005fc3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005fc8  mov     r14, rax
0x180005fcb  test    rax, rax
0x180005fce  jz      loc_1800061E4
0x180005fd4  mov     rdi, rax
0x180005fd7  test    r12d, r12d
0x180005fda  jz      short loc_180005FEE
0x180005fdc  mov     rcx, rdi; this
  ... truncated ...
```
