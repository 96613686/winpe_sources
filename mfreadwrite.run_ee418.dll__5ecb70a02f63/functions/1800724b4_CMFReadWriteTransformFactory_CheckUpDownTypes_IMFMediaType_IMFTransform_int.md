# CMFReadWriteTransformFactory::CheckUpDownTypes(IMFMediaType *,IMFTransform *,int *)

- ea: `0x1800724b4`
- end: `0x180072b42`
- name: `?CheckUpDownTypes@CMFReadWriteTransformFactory@@AEAAJPEAUIMFMediaType@@PEAUIMFTransform@@PEAH@Z`
- size: `1678`
- prototype: `__int64 __fastcall(CMFReadWriteTransformFactory *__hidden this, struct IMFMediaType *, struct IMFTransform *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180071af4`

## callees

- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x180014a14`
- `0x1800252a0`
- `0x1800724b4`
- `0x180072b48`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007271a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072851`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072986`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072acf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007271a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072851`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072986`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180072acf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800726ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800726c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800727eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800726ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800726c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800727eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072802`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072a80`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800726b9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800727f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007292c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180072a75`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800726b9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800727f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007292c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180072a75`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800726da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007278c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072818`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800728be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007294d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800729eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072a96`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800726da`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007278c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072818`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800728be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18007294d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800729eb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180072a96`

## string_xrefs

- `0x1800724ec`: `CMFReadWriteTransformFactory::CheckUpDownTypes`
- `0x180072733`: `CMFReadWriteTransformFactory::CheckUpDownTypes`
- `0x180072863`: `CMFReadWriteTransformFactory::CheckUpDownTypes`
- `0x180072998`: `CMFReadWriteTransformFactory::CheckUpDownTypes`
- `0x180072ae5`: `CMFReadWriteTransformFactory::CheckUpDownTypes`

## pseudocode

```c
__int64 __fastcall CMFReadWriteTransformFactory::CheckUpDownTypes(
        CMFReadWriteTransformFactory *this,
        struct IMFMediaType *a2,
        struct IMFTransform *a3,
        int *a4)
{
  CMFReadWriteTransformFactory *v6; // r15
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // r12d
  unsigned int v11; // r15d
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r14
  int v15; // ebx
  unsigned int i; // esi
  struct IMFMediaTypeVtbl *lpVtbl; // rax
  int v18; // eax
  CallStackTracing *v19; // rdi
  CallStackContext *v21; // rsi
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  CallStackTracing *v26; // rdi
  CallStackTracing *v27; // rax
  __int64 v28; // rax
  CallStackTracing *v29; // rsi
  CallStackTracing *v30; // rax
  __int64 v31; // rdx
  CallStackContext *v32; // r15
  DWORD v33; // r13d
  CallStackContext *v34; // rax
  __int64 v35; // rdx
  CallStackTracing *v36; // rcx
  CallStackTracing *v37; // rax
  __int64 v38; // rax
  CallStackTracing *v39; // rsi
  CallStackTracing *v40; // rax
  CMFReadWriteTransformFactory *v41; // r9
  CallStackContext *v42; // r15
  DWORD v43; // r13d
  CallStackContext *v44; // rax
  __int64 v45; // rdx
  CallStackTracing *v46; // rcx
  CallStackTracing *v47; // rax
  __int64 v48; // rax
  CallStackTracing *v49; // rsi
  CallStackTracing *v50; // rax
  CallStackContext *v51; // r15
  DWORD v52; // r13d
  CallStackContext *v53; // rax
  __int64 v54; // rdx
  CallStackTracing *v55; // rcx
  CallStackTracing *v56; // rax
  __int64 v57; // rax
  _BYTE v58[4]; // [rsp+30h] [rbp-30h] BYREF
  int v59; // [rsp+34h] [rbp-2Ch] BYREF
  __int64 v60; // [rsp+38h] [rbp-28h] BYREF
  __int128 *v61; // [rsp+40h] [rbp-20h]
  PROPVARIANT pvar; // [rsp+48h] [rbp-18h] BYREF

  v60 = 0;
  v6 = this;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v58,
    "CMFReadWriteTransformFactory::CheckUpDownTypes",
    1478);
  if ( !a2 )
  {
    v19 = CallStackTracing::s_wpInstance;
    v15 = -2147467261;
    v10 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v19 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v19 + 8) )
    {
      v21 = (CallStackTracing *)((char *)v19 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v19 + 3));
      if ( Value )
      {
        v21 = Value;
      }
      else if ( !GetLastError() )
      {
        v26 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v25, v24);
          CallStackTracing::s_wpInstance = v27;
          if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
          {
            v26 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v26 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v28 = (**(__int64 (__fastcall ***)(CallStackTracing *))v26)(v26);
        if ( v28 )
          v21 = (CallStackContext *)v28;
      }
      SetLastError(LastError);
      v6 = this;
      if ( *((_DWORD *)v21 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v21, "CMFReadWriteTransformFactory::CheckUpDownTypes", 1478, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_24;
    v31 = 130;
    goto LABEL_70;
  }
  if ( !a3 )
  {
    v29 = CallStackTracing::s_wpInstance;
    v15 = -2147467261;
    v10 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8);
      CallStackTracing::s_wpInstance = v30;
      if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
      {
        v29 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v29 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v32 = (CallStackTracing *)((char *)v29 + 208);
      v33 = GetLastError();
      v34 = (CallStackContext *)TlsGetValue(*((_DWORD *)v29 + 3));
      if ( v34 )
      {
        v32 = v34;
      }
      else if ( !GetLastError() )
      {
        v36 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35);
          CallStackTracing::s_wpInstance = v37;
          if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
          {
            v36 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v36 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v38 = (**(__int64 (__fastcall ***)(CallStackTracing *))v36)(v36);
        if ( v38 )
          v32 = (CallStackContext *)v38;
      }
      SetLastError(v33);
      if ( *((_DWORD *)v32 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v32, "CMFReadWriteTransformFactory::CheckUpDownTypes", 1479, -2147467261);
      v6 = this;
    }
    if ( !g_wppLevels )
      goto LABEL_24;
    v31 = 131;
    goto LABEL_70;
  }
  if ( !a4 )
  {
    v39 = CallStackTracing::s_wpInstance;
    v15 = -2147467261;
    v10 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v9, v8);
      CallStackTracing::s_wpInstance = v40;
      if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
      {
        v39 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v39 = (CallStackTracing *)&qword_18010C230;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
      }
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      v42 = (CallStackTracing *)((char *)v39 + 208);
      v43 = GetLastError();
      v44 = (CallStackContext *)TlsGetValue(*((_DWORD *)v39 + 3));
      if ( v44 )
      {
        v42 = v44;
      }
      else if ( !GetLastError() )
      {
        v46 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v45);
          CallStackTracing::s_wpInstance = v47;
          if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
          {
            v46 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v46 = (CallStackTracing *)&qword_18010C230;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
          }
        }
        v48 = (**(__int64 (__fastcall ***)(CallStackTracing *))v46)(v46);
        if ( v48 )
          v42 = (CallStackContext *)v48;
      }
      SetLastError(v43);
      if ( *((_DWORD *)v42 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v42, "CMFReadWriteTransformFactory::CheckUpDownTypes", 1480, -2147467261);
      v6 = this;
    }
    if ( !g_wppLevels )
      goto LABEL_24;
    v31 = 132;
LABEL_70:
    v41 = v6;
    goto LABEL_93;
  }
  v10 = 0;
  v11 = 0;
  *a4 = 0;
  while ( ((int (__fastcall *)(struct IMFTransform *, _QWORD, _QWORD, __int64 *))a3->lpVtbl->GetInputAvailableType)(
            a3,
            0,
            v11,
            &v60) >= 0 )
  {
    v14 = v60;
    if ( !v60 )
    {
      v15 = -2147467261;
      v10 = -2147467261;
LABEL_86:
      v49 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12);
        CallStackTracing::s_wpInstance = v50;
        if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
        {
          v49 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v49 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v49 + 8) )
      {
        v51 = (CallStackTracing *)((char *)v49 + 208);
        v52 = GetLastError();
        v53 = (CallStackContext *)TlsGetValue(*((_DWORD *)v49 + 3));
        if ( v53 )
        {
          v51 = v53;
        }
        else if ( !GetLastError() )
        {
          v55 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v56 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v54);
            CallStackTracing::s_wpInstance = v56;
            if ( v56 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
            {
              v55 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v55 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v57 = (**(__int64 (__fastcall ***)(CallStackTracing *))v55)(v55);
          if ( v57 )
            v51 = (CallStackContext *)v57;
        }
        SetLastError(v52);
        if ( *((_DWORD *)v51 + 499) != v15 )
          CallStackContext::TraceFailure(v51, "CMFReadWriteTransformFactory::CheckUpDownTypes", 1488, v15);
      }
      if ( !g_wppLevels )
        break;
      v41 = this;
      v31 = 133;
LABEL_93:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, &WPP_184e36c9e49b38f16c7569e0393fc250_Traceguids, v41, v15);
      break;
    }
    v15 = 0;
    *a4 = 0;
    for ( i = 0; i < 0xB; ++i )
    {
      v59 = 0;
      lpVtbl = a2->lpVtbl;
      v61 = &xmmword_18010B7B0[i];
      memset(&pvar, 0, sizeof(pvar));
      v18 = ((__int64 (__fastcall *)(struct IMFMediaType *, __int128 *, PROPVARIANT *))lpVtbl->GetItem)(a2, v61, &pvar);
      v10 = v18;
      if ( v18 != -1072875802 )
      {
        if ( v18 < 0 )
        {
          v15 = v18;
          CMFPropVariant::Clear(&pvar);
          goto LABEL_86;
        }
        v15 = (*(__int64 (__fastcall **)(__int64, __int128 *, PROPVARIANT *, int *))(*(_QWORD *)v14 + 40LL))(
                v14,
                v61,
                &pvar,
                &v59);
        if ( v15 < 0 || !v59 )
        {
          CMFPropVariant::Clear(&pvar);
          goto LABEL_15;
        }
      }
      CMFPropVariant::Clear(&pvar);
    }
    *a4 = 1;
LABEL_15:
    v10 = v15;
    if ( v15 < 0 )
      goto LABEL_86;
    if ( v60 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
      v60 = 0;
    }
    if ( !*a4 )
    {
      ++v11;
      continue;
    }
    break;
  }
LABEL_24:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v58);
  if ( v60 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
  return v10;
}

```

## disassembly

```asm
0x1800724b4  mov     [rsp-38h+arg_10], rbx
0x1800724b9  mov     [rsp-38h+arg_8], rdx
0x1800724be  mov     [rsp-38h+arg_0], rcx
0x1800724c3  push    rbp
0x1800724c4  push    rsi
0x1800724c5  push    rdi
0x1800724c6  push    r12
0x1800724c8  push    r13
0x1800724ca  push    r14
0x1800724cc  push    r15
0x1800724ce  mov     rbp, rsp
0x1800724d1  sub     rsp, 60h
0x1800724d5  mov     r13, r8
0x1800724d8  mov     [rbp+var_28], 0
0x1800724e0  mov     rbx, rdx
0x1800724e3  mov     r15, rcx
0x1800724e6  mov     r8d, 5C6h; int
0x1800724ec  lea     rdx, aCmfreadwritetr_112; "CMFReadWriteTransformFactory::CheckUpDo"...
0x1800724f3  lea     rcx, [rbp+var_30]; this
0x1800724f7  mov     rdi, r9
0x1800724fa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800724ff  test    rbx, rbx
0x180072502  jz      loc_18007262D
0x180072508  test    r13, r13
0x18007250b  jz      loc_18007276B
0x180072511  test    rdi, rdi
0x180072514  jz      loc_18007289D
0x18007251a  xor     r12d, r12d
0x18007251d  xor     r15d, r15d
0x180072520  mov     [rdi], r12d
0x180072523  mov     rax, [r13+0]
0x180072527  lea     r9, [rbp+var_28]
0x18007252b  mov     r8d, r15d
0x18007252e  xor     edx, edx
0x180072530  mov     rcx, r13
0x180072533  mov     rax, [rax+68h]
0x180072537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007253c  test    eax, eax
0x18007253e  js      loc_180072654
0x180072544  mov     r14, [rbp+var_28]
0x180072548  test    r14, r14
0x18007254b  jz      loc_180072B35
0x180072551  xor     ebx, ebx
0x180072553  mov     dword ptr [rdi], 0
0x180072559  xor     esi, esi
0x18007255b  cmp     esi, 0Bh
0x18007255e  jnb     loc_18007268D
0x180072564  mov     r9, [rbp+arg_8]
0x180072568  lea     rcx, xmmword_18010B7B0
0x18007256f  xor     eax, eax
0x180072571  mov     [rbp+var_2C], 0
0x180072578  mov     qword ptr [rbp+pvar+10h], rax
0x18007257c  lea     r8, [rbp+pvar]
0x180072580  xorps   xmm0, xmm0
0x180072583  mov     eax, esi
0x180072585  shl     rax, 4
0x180072589  add     rcx, rax
0x18007258c  mov     rax, [r9]
0x18007258f  mov     [rbp+var_20], rcx
0x180072593  mov     rdx, rcx
0x180072596  mov     rcx, r9
0x180072599  movups  xmmword ptr [rbp+pvar], xmm0
0x18007259d  mov     rax, [rax+18h]
0x1800725a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725a6  mov     r12d, eax
0x1800725a9  cmp     eax, 0C00D36E6h
0x1800725ae  jz      short loc_1800725DF
0x1800725b0  test    eax, eax
0x1800725b2  js      loc_180072B25
0x1800725b8  mov     rax, [r14]
0x1800725bb  lea     r9, [rbp+var_2C]
0x1800725bf  mov     rdx, [rbp+var_20]
0x1800725c3  lea     r8, [rbp+pvar]
0x1800725c7  mov     rcx, r14
0x1800725ca  mov     rax, [rax+28h]
0x1800725ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725d3  mov     ebx, eax
0x1800725d5  test    eax, eax
0x1800725d7  js      short loc_1800725EF
0x1800725d9  cmp     [rbp+var_2C], 0
0x1800725dd  jz      short loc_1800725EF
0x1800725df  lea     rcx, [rbp+pvar]; pvar
0x1800725e3  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800725e8  inc     esi
0x1800725ea  jmp     loc_18007255B
0x1800725ef  lea     rcx, [rbp+pvar]; pvar
0x1800725f3  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x1800725f8  mov     r12d, ebx
0x1800725fb  test    ebx, ebx
0x1800725fd  js      loc_1800729D2
0x180072603  mov     rcx, [rbp+var_28]
0x180072607  test    rcx, rcx
0x18007260a  jz      short loc_180072620
0x18007260c  mov     rax, [rcx]
0x18007260f  mov     rax, [rax+10h]
0x180072613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072618  mov     [rbp+var_28], 0
0x180072620  cmp     dword ptr [rdi], 0
0x180072623  jnz     short loc_180072654
0x180072625  inc     r15d
0x180072628  jmp     loc_180072523
0x18007262d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072634  mov     ebx, 80004003h
0x180072639  mov     r12d, ebx
0x18007263c  test    rdi, rdi
0x18007263f  jz      short loc_180072698
0x180072641  cmp     byte ptr [rdi+8], 0
0x180072645  jnz     short loc_1800726A6
0x180072647  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007264e  jnb     loc_180072B1B
0x180072654  lea     rcx, [rbp+var_30]; this
0x180072658  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18007265d  mov     rcx, [rbp+var_28]
0x180072661  test    rcx, rcx
0x180072664  jz      short loc_180072672
0x180072666  mov     rdx, [rcx]
0x180072669  mov     rax, [rdx+10h]
0x18007266d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072672  mov     rbx, [rsp+60h+arg_10]
0x18007267a  mov     eax, r12d
0x18007267d  add     rsp, 60h
0x180072681  pop     r15
0x180072683  pop     r14
0x180072685  pop     r13
0x180072687  pop     r12
0x180072689  pop     rdi
0x18007268a  pop     rsi
0x18007268b  pop     rbp
0x18007268c  retn
0x18007268d  mov     dword ptr [rdi], 1
0x180072693  jmp     loc_1800725F8
0x180072698  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18007269d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800726a4  jmp     short loc_180072641
0x1800726a6  lea     rsi, [rdi+0D0h]
0x1800726ad  call    cs:__imp_GetLastError
0x1800726b3  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800726b6  mov     r15d, eax
0x1800726b9  call    cs:__imp_TlsGetValue
0x1800726bf  test    rax, rax
0x1800726c2  jnz     short loc_180072714
0x1800726c4  call    cs:__imp_GetLastError
0x1800726ca  test    eax, eax
0x1800726cc  jnz     short loc_180072717
0x1800726ce  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800726d5  test    rdi, rdi
0x1800726d8  jnz     short loc_1800726FD
0x1800726da  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800726e0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800726e7  mov     rcx, rax
0x1800726ea  test    rax, rax
0x1800726ed  jnz     short loc_18007274D
0x1800726ef  lea     rdi, qword_18010C230
0x1800726f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800726fd  mov     rax, [rdi]
0x180072700  mov     rcx, rdi
0x180072703  mov     rax, [rax]
0x180072706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007270b  test    rax, rax
0x18007270e  cmovnz  rsi, rax
0x180072712  jmp     short loc_180072717
0x180072714  mov     rsi, rax
0x180072717  mov     ecx, r15d; dwErrCode
0x18007271a  call    cs:__imp_SetLastError
0x180072720  mov     r15, [rbp+arg_0]
0x180072724  cmp     [rsi+7CCh], ebx
0x18007272a  jz      loc_180072647
0x180072730  mov     r9d, ebx; int
0x180072733  lea     rdx, aCmfreadwritetr_112; "CMFReadWriteTransformFactory::CheckUpDo"...
0x18007273a  mov     r8d, 5C6h; int
0x180072740  mov     rcx, rsi; this
0x180072743  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072748  jmp     loc_180072647
0x18007274d  mov     rax, [rax]
0x180072750  mov     edx, 7F0h
0x180072755  mov     rax, [rax+8]
0x180072759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007275e  test    eax, eax
0x180072760  jz      short loc_1800726EF
0x180072762  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072769  jmp     short loc_1800726FD
0x18007276b  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072772  lea     rdi, qword_18010C230
0x180072779  mov     ebx, 80004003h
0x18007277e  mov     r14d, 7F0h
0x180072784  mov     r12d, ebx
0x180072787  test    rsi, rsi
0x18007278a  jnz     short loc_1800727BB
0x18007278c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072792  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072799  mov     rcx, rax
0x18007279c  test    rax, rax
0x18007279f  jz      short loc_1800727D8
0x1800727a1  mov     rax, [rax]
0x1800727a4  mov     edx, r14d
0x1800727a7  mov     rax, [rax+8]
0x1800727ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800727b0  test    eax, eax
0x1800727b2  jz      short loc_1800727D8
0x1800727b4  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800727bb  cmp     byte ptr [rsi+8], 0
0x1800727bf  jnz     short loc_1800727E4
0x1800727c1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800727c8  jb      loc_180072654
0x1800727ce  mov     edx, 83h
0x1800727d3  jmp     loc_180072905
0x1800727d8  mov     rsi, rdi
0x1800727db  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800727e2  jmp     short loc_1800727BB
0x1800727e4  lea     r15, [rsi+0D0h]
0x1800727eb  call    cs:__imp_GetLastError
0x1800727f1  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x1800727f4  mov     r13d, eax
0x1800727f7  call    cs:__imp_TlsGetValue
0x1800727fd  test    rax, rax
0x180072800  jnz     short loc_18007284B
0x180072802  call    cs:__imp_GetLastError
0x180072808  test    eax, eax
0x18007280a  jnz     short loc_18007284E
0x18007280c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072813  test    rcx, rcx
0x180072816  jnz     short loc_180072837
0x180072818  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18007281e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180072825  mov     rcx, rax
0x180072828  test    rax, rax
0x18007282b  jnz     short loc_180072881
0x18007282d  mov     rcx, rdi
0x180072830  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180072837  mov     rax, [rcx]
0x18007283a  mov     rax, [rax]
0x18007283d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072842  test    rax, rax
0x180072845  cmovnz  r15, rax
0x180072849  jmp     short loc_18007284E
0x18007284b  mov     r15, rax
0x18007284e  mov     ecx, r13d; dwErrCode
0x180072851  call    cs:__imp_SetLastError
0x180072857  cmp     [r15+7CCh], ebx
0x18007285e  jz      short loc_180072878
0x180072860  mov     r9d, ebx; int
0x180072863  lea     rdx, aCmfreadwritetr_112; "CMFReadWriteTransformFactory::CheckUpDo"...
0x18007286a  mov     r8d, 5C7h; int
0x180072870  mov     rcx, r15; this
0x180072873  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180072878  mov     r15, [rbp+arg_0]
0x18007287c  jmp     loc_1800727C1
0x180072881  mov     rax, [rax]
0x180072884  mov     edx, r14d
0x180072887  mov     rax, [rax+8]
0x18007288b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072890  test    eax, eax
0x180072892  jz      short loc_18007282D
0x180072894  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18007289b  jmp     short loc_180072837
0x18007289d  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800728a4  lea     rdi, qword_18010C230
0x1800728ab  mov     ebx, 80004003h
0x1800728b0  mov     r14d, 7F0h
0x1800728b6  mov     r12d, ebx
0x1800728b9  test    rsi, rsi
0x1800728bc  jnz     short loc_1800728ED
0x1800728be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800728c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800728cb  mov     rcx, rax
0x1800728ce  test    rax, rax
0x1800728d1  jz      short loc_18007290D
0x1800728d3  mov     rax, [rax]
0x1800728d6  mov     edx, r14d
0x1800728d9  mov     rax, [rax+8]
0x1800728dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800728e2  test    eax, eax
0x1800728e4  jz      short loc_18007290D
0x1800728e6  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800728ed  cmp     byte ptr [rsi+8], 0
0x1800728f1  jnz     short loc_180072919
0x1800728f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800728fa  jb      loc_180072654
0x180072900  mov     edx, 84h
0x180072905  mov     r9, r15
0x180072908  jmp     loc_180072A36
0x18007290d  mov     rsi, rdi
0x180072910  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x180072917  jmp     short loc_1800728ED
0x180072919  lea     r15, [rsi+0D0h]
0x180072920  call    cs:__imp_GetLastError
0x180072926  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x180072929  mov     r13d, eax
0x18007292c  call    cs:__imp_TlsGetValue
0x180072932  test    rax, rax
0x180072935  jnz     short loc_180072980
0x180072937  call    cs:__imp_GetLastError
0x18007293d  test    eax, eax
0x18007293f  jnz     short loc_180072983
0x180072941  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180072948  test    rcx, rcx
0x18007294b  jnz     short loc_18007296C
0x18007294d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180072953  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18007295a  mov     rcx, rax
  ... truncated ...
```
