# CMFPropVariant::Copy(tagPROPVARIANT const *)

- ea: `0x1800275f0`
- end: `0x180027ca4`
- name: `?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z`
- size: `1716`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)`
- caller_count: `17`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180024720`
- `0x180026f50`
- `0x180028ffc`
- `0x18006036c`
- `0x180062b30`
- `0x1800688f0`
- `0x180070e10`
- `0x1800721bc`
- `0x180081860`
- `0x1800984b0`
- `0x1800a8760`
- `0x1800b17a8`
- `0x1800b3640`
- `0x1800d6770`
- `0x1800df3e0`
- `0x1800e0460`
- `0x180108f80`

## callees

- `0x180010190`
- `0x18001303c`
- `0x1800275f0`
- `0x180071a44`
- `0x180073b14`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027656`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800276d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027656`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800276d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800276b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027777`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800276b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027746`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027777`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027717`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027717`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027642`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800276bd`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180027642`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800276bd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800277d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002781b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002785b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002789b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800278cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027919`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800277d6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002781b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002785b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002789b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800278cd`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027919`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027ae5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027ae5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002768e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18002768e`

## string_xrefs

- `0x180027623`: `CMFPropVariant::Copy`
- `0x1800279cd`: `CMFPropVariant::Copy`
- `0x180027bc4`: `CMFPropVariant::Copy`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Copy(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc, __int64 a3, __int64 a4)
{
  CallStackTracing *v6; // rbx
  char *v7; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdx
  CallStackTracing *v13; // rcx
  HRESULT v14; // esi
  __int64 v15; // r8
  __int64 v16; // r9
  CallStackTracing *v17; // rbx
  GUID *v18; // rdi
  DWORD v19; // ebp
  GUID *v20; // rax
  int v21; // eax
  int v22; // eax
  CallStackTracing *v24; // rcx
  __int64 v25; // rax
  CallStackTracing *v26; // rcx
  __int64 v27; // rax
  CallStackTracing *v28; // rax
  CallStackTracing *v29; // rax
  CallStackTracing *v30; // rax
  CallStackTracing *v31; // rax
  CallStackTracing *v32; // rax
  CallStackTracing *v33; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v35; // rax
  struct CallStackContext *v36; // rax
  struct CallStackContext *v37; // rax
  struct CallStackContext *v38; // rax
  struct CallStackContext *v39; // rax
  __int64 v40; // rdx
  BYTE *v41; // rax
  BYTE *v42; // rbx
  BYTE *pData; // rdi
  unsigned int i; // r15d
  void *v45; // rax
  __int64 v46; // rdx

  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v6 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v7 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v6 + 3));
    if ( Value )
    {
      v7 = Value;
    }
    else if ( !GetLastError() )
    {
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v24 = CallStackTracing::s_wpInstance;
      }
      v25 = (**(__int64 (__fastcall ***)(CallStackTracing *))v24)(v24);
      if ( v25 )
        v7 = (char *)v25;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v7[8 * v11] = "CMFPropVariant::Copy";
      *(_DWORD *)&v7[8 * v11 + 8] = 181;
    }
    ++*((_DWORD *)v7 + 497);
  }
  if ( pvarDest == pvarSrc )
  {
    v14 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(pvarDest, pvarSrc, a3, a4);
      CallStackTracing::s_wpInstance = v28;
      if ( !v28 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::Copy", 190, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_11;
    v40 = 15;
LABEL_91:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvarDest, v14);
    goto LABEL_11;
  }
  v14 = PropVariantCopy(pvarDest, pvarSrc);
  if ( v14 >= 0 )
    goto LABEL_11;
  if ( pvarSrc->vt != 4161 )
  {
    v14 = -1072875800;
    if ( !CallStackTracing::s_wpInstance )
    {
      v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12, v15, v16);
      CallStackTracing::s_wpInstance = v29;
      v13 = v29;
      if ( !v29 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v35 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v35 + 499) != -1072875800 )
        CallStackContext::TraceFailure(v35, "CMFPropVariant::Copy", 241, -1072875800);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        pvarDest,
        -1072875800);
LABEL_45:
    if ( !CallStackTracing::s_wpInstance )
    {
      v33 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12, v15, v16);
      CallStackTracing::s_wpInstance = v33;
      if ( !v33 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v33 + 8LL))(v33, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v39 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v39 + 499) != v14 )
        CallStackContext::TraceFailure(v39, "CMFPropVariant::Copy", 247, v14);
    }
    if ( !g_wppLevels )
      goto LABEL_11;
    v40 = 20;
    goto LABEL_91;
  }
  pvarDest->vt = 4161;
  pvarDest->lVal = pvarSrc->lVal;
  v41 = (BYTE *)CoTaskMemAlloc(16LL * pvarSrc->ulVal);
  pvarDest->bstrblobVal.pData = v41;
  v42 = v41;
  if ( !v41 )
  {
    v14 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12, v15, v16);
      CallStackTracing::s_wpInstance = v30;
      v13 = v30;
      if ( !v30 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v36 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v36 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v36, "CMFPropVariant::Copy", 224, -2147024882);
    }
    if ( g_wppLevels )
    {
      v46 = 16;
LABEL_86:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v46,
        &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        pvarDest,
        -2147024882);
    }
    goto LABEL_45;
  }
  pData = pvarSrc->bstrblobVal.pData;
  v14 = 0;
  for ( i = 0; pvarSrc->lVal > i; ++i )
  {
    *(_DWORD *)v42 = *(_DWORD *)pData;
    v45 = CoTaskMemAlloc(*(unsigned int *)pData);
    *((_QWORD *)v42 + 1) = v45;
    if ( !v45 )
    {
      v14 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12, v15, v16);
        CallStackTracing::s_wpInstance = v31;
        v13 = v31;
        if ( !v31 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v37 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v37 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v37, "CMFPropVariant::Copy", 231, -2147024882);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -2147024882);
      if ( !CallStackTracing::s_wpInstance )
      {
        v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v13, v12, v15, v16);
        CallStackTracing::s_wpInstance = v32;
        v13 = v32;
        if ( !v32 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v38 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v38, "CMFPropVariant::Copy", 236, -2147024882);
      }
      if ( g_wppLevels )
      {
        v46 = 18;
        goto LABEL_86;
      }
      goto LABEL_45;
    }
    memcpy_0(v45, *((const void **)pData + 1), *(unsigned int *)pData);
    v42 += 16;
    pData += 16;
  }
LABEL_11:
  v17 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v18 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v19 = GetLastError();
    v20 = (GUID *)TlsGetValue(*((_DWORD *)v17 + 3));
    if ( v20 )
    {
      v18 = v20;
    }
    else if ( !GetLastError() )
    {
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v26 = CallStackTracing::s_wpInstance;
      }
      v27 = (**(__int64 (__fastcall ***)(CallStackTracing *))v26)(v26);
      if ( v27 )
        v18 = (GUID *)v27;
    }
    SetLastError(v19);
    v21 = *(_DWORD *)&v18[124].Data2;
    if ( v21 )
    {
      v22 = v21 - 1;
      *(_DWORD *)&v18[124].Data2 = v22;
      if ( !v22 )
      {
        *(_DWORD *)&v18[124].Data2 = 0;
        *(_QWORD *)&v18[126].Data1 = 0;
        *(_DWORD *)&v18[124].Data4[4] = 0;
        v18[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v18[126].Data4 = 0;
        v18[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800275f0  mov     [rsp+arg_10], rbx
0x1800275f5  mov     [rsp+arg_18], rbp
0x1800275fa  push    rsi
0x1800275fb  push    rdi
0x1800275fc  push    r13
0x1800275fe  push    r14
0x180027600  push    r15
0x180027602  sub     rsp, 30h
0x180027606  xor     r13d, r13d
0x180027609  mov     rbp, rdx
0x18002760c  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180027613  mov     r14, rcx
0x180027616  jz      loc_18002773C
0x18002761c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027623  lea     r15, aCmfpropvariant_18; "CMFPropVariant::Copy"
0x18002762a  cmp     [rbx+8], r13b
0x18002762e  jz      short loc_18002767F
0x180027630  lea     rdi, [rbx+0D0h]
0x180027637  call    cs:__imp_GetLastError
0x18002763d  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180027640  mov     esi, eax
0x180027642  call    cs:__imp_TlsGetValue
0x180027648  test    rax, rax
0x18002764b  jz      loc_180027746
0x180027651  mov     rdi, rax
0x180027654  mov     ecx, esi; dwErrCode
0x180027656  call    cs:__imp_SetLastError
0x18002765c  mov     eax, [rdi+7C4h]
0x180027662  cmp     eax, [rdi+7C8h]
0x180027668  jnb     short loc_180027679
0x18002766a  add     rax, rax
0x18002766d  mov     [rdi+rax*8], r15
0x180027671  mov     dword ptr [rdi+rax*8+8], 0B5h
0x180027679  inc     dword ptr [rdi+7C4h]
0x18002767f  cmp     r14, rbp
0x180027682  jz      loc_1800277C4
0x180027688  mov     rdx, rbp; pvarSrc
0x18002768b  mov     rcx, r14; pvarDest
0x18002768e  call    cs:__imp_PropVariantCopy
0x180027694  mov     esi, eax
0x180027696  test    eax, eax
0x180027698  js      loc_180027A94
0x18002769e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800276a5  cmp     [rbx+8], r13b
0x1800276a9  jz      short loc_180027723
0x1800276ab  lea     rdi, [rbx+0D0h]
0x1800276b2  call    cs:__imp_GetLastError
0x1800276b8  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800276bb  mov     ebp, eax
0x1800276bd  call    cs:__imp_TlsGetValue
0x1800276c3  test    rax, rax
0x1800276c6  jz      loc_180027777
0x1800276cc  mov     rdi, rax
0x1800276cf  mov     ecx, ebp; dwErrCode
0x1800276d1  call    cs:__imp_SetLastError
0x1800276d7  mov     eax, [rdi+7C4h]
0x1800276dd  test    eax, eax
0x1800276df  jz      short loc_180027723
0x1800276e1  sub     eax, 1
0x1800276e4  mov     [rdi+7C4h], eax
0x1800276ea  jnz     short loc_180027723
0x1800276ec  mov     [rdi+7C4h], r13d
0x1800276f3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800276fa  mov     [rdi+7E0h], r13
0x180027701  mov     [rdi+7CCh], r13d
0x180027708  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180027710  mov     [rdi+7E8h], r13d
0x180027717  call    cs:__imp_GetCurrentThreadId
0x18002771d  mov     [rdi+7C0h], eax
0x180027723  mov     rbx, [rsp+58h+arg_10]
0x180027728  mov     eax, esi
0x18002772a  mov     rbp, [rsp+58h+arg_18]
0x18002772f  add     rsp, 30h
0x180027733  pop     r15
0x180027735  pop     r14
0x180027737  pop     r13
0x180027739  pop     rdi
0x18002773a  pop     rsi
0x18002773b  retn
0x18002773c  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180027741  jmp     loc_18002761C
0x180027746  call    cs:__imp_GetLastError
0x18002774c  test    eax, eax
0x18002774e  jnz     loc_180027654
0x180027754  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002775b  test    rcx, rcx
0x18002775e  jz      short loc_1800277A8
0x180027760  mov     rax, [rcx]
0x180027763  mov     rax, [rax]
0x180027766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002776b  test    rax, rax
0x18002776e  cmovnz  rdi, rax
0x180027772  jmp     loc_180027654
0x180027777  call    cs:__imp_GetLastError
0x18002777d  test    eax, eax
0x18002777f  jnz     loc_1800276CF
0x180027785  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002778c  test    rcx, rcx
0x18002778f  jz      short loc_1800277B6
0x180027791  mov     rax, [rcx]
0x180027794  mov     rax, [rax]
0x180027797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002779c  test    rax, rax
0x18002779f  cmovnz  rdi, rax
0x1800277a3  jmp     loc_1800276CF
0x1800277a8  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800277ad  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800277b4  jmp     short loc_180027760
0x1800277b6  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800277bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800277c2  jmp     short loc_180027791
0x1800277c4  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x1800277cb  mov     esi, 80004003h
0x1800277d0  jnz     loc_180027A6C
0x1800277d6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800277dc  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800277e3  mov     rcx, rax
0x1800277e6  test    rax, rax
0x1800277e9  jnz     loc_180027A53
0x1800277ef  lea     rbp, qword_1801B07E0
0x1800277f6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x1800277fd  jmp     loc_180027A6C
0x180027802  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180027809  lea     rbp, qword_1801B07E0
0x180027810  mov     esi, 0C00D36E8h
0x180027815  jnz     loc_180027B2D
0x18002781b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027821  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027828  mov     rcx, rax
0x18002782b  test    rax, rax
0x18002782e  jnz     loc_180027B14
0x180027834  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002783b  jmp     loc_180027B2D
0x180027840  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180027847  lea     rbp, qword_1801B07E0
0x18002784e  mov     edi, 8007000Eh
0x180027853  mov     esi, edi
0x180027855  jnz     loc_180027B72
0x18002785b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027861  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027868  mov     rcx, rax
0x18002786b  test    rax, rax
0x18002786e  jnz     loc_180027B59
0x180027874  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18002787b  jmp     loc_180027B72
0x180027880  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180027887  lea     rbp, qword_1801B07E0
0x18002788e  mov     edi, 8007000Eh
0x180027893  mov     esi, edi
0x180027895  jnz     loc_180027BB3
0x18002789b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800278a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800278a8  mov     rcx, rax
0x1800278ab  test    rax, rax
0x1800278ae  jnz     loc_180027B9A
0x1800278b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x1800278bb  jmp     loc_180027BB3
0x1800278c0  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x1800278c7  jnz     loc_180027C19
0x1800278cd  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800278d3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800278da  mov     rcx, rax
0x1800278dd  test    rax, rax
0x1800278e0  jnz     loc_180027C00
0x1800278e6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x1800278ed  jmp     loc_180027C19
0x1800278f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800278f9  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180027900  mov     r9, r14
0x180027903  mov     rcx, [rcx+10h]
0x180027907  call    WPP_SF_qD
0x18002790c  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180027913  jnz     loc_180027C5E
0x180027919  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002791f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027926  mov     rcx, rax
0x180027929  test    rax, rax
0x18002792c  jnz     loc_180027C45
0x180027932  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x180027939  jmp     loc_180027C5E
0x18002793e  mov     rcx, rbx; this
0x180027941  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027946  cmp     [rax+7CCh], esi
0x18002794c  jz      loc_180027A7D
0x180027952  mov     r9d, esi; int
0x180027955  mov     r8d, 0BEh; int
0x18002795b  mov     rdx, r15; char *
0x18002795e  mov     rcx, rax; this
0x180027961  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027966  jmp     loc_180027A7D
0x18002796b  mov     rcx, rbx; this
0x18002796e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027973  cmp     [rax+7CCh], esi
0x180027979  jz      loc_180027B3E
0x18002797f  mov     r9d, esi; int
0x180027982  mov     r8d, 0F1h; int
0x180027988  mov     rdx, r15; char *
0x18002798b  mov     rcx, rax; this
0x18002798e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027993  jmp     loc_180027B3E
0x180027998  mov     rcx, rbx; this
0x18002799b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800279a0  cmp     [rax+7CCh], edi
0x1800279a6  jz      loc_180027B83
0x1800279ac  mov     r9d, edi; int
0x1800279af  mov     r8d, 0E0h; int
0x1800279b5  mov     rdx, r15; char *
0x1800279b8  mov     rcx, rax; this
0x1800279bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800279c0  jmp     loc_180027B83
0x1800279c5  mov     rcx, rbx; this
0x1800279c8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800279cd  lea     r15, aCmfpropvariant_18; "CMFPropVariant::Copy"
0x1800279d4  cmp     [rax+7CCh], edi
0x1800279da  jz      loc_180027BCB
0x1800279e0  mov     r9d, edi; int
0x1800279e3  mov     r8d, 0E7h; int
0x1800279e9  mov     rdx, r15; char *
0x1800279ec  mov     rcx, rax; this
0x1800279ef  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800279f4  jmp     loc_180027BCB
0x1800279f9  mov     rcx, rbx; this
0x1800279fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027a01  cmp     [rax+7CCh], edi
0x180027a07  jz      loc_180027C2A
0x180027a0d  mov     r9d, edi; int
0x180027a10  mov     r8d, 0ECh; int
0x180027a16  mov     rdx, r15; char *
0x180027a19  mov     rcx, rax; this
0x180027a1c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027a21  jmp     loc_180027C2A
0x180027a26  mov     rcx, rbx; this
0x180027a29  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027a2e  cmp     [rax+7CCh], esi
0x180027a34  jz      loc_180027C6F
0x180027a3a  mov     r9d, esi; int
0x180027a3d  mov     r8d, 0F7h; int
0x180027a43  mov     rdx, r15; char *
0x180027a46  mov     rcx, rax; this
0x180027a49  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027a4e  jmp     loc_180027C6F
0x180027a53  mov     rax, [rax]
0x180027a56  mov     edx, 7F0h
0x180027a5b  mov     rax, [rax+8]
0x180027a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a64  test    eax, eax
0x180027a66  jz      loc_1800277EF
0x180027a6c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027a73  cmp     [rbx+8], r13b
0x180027a77  jnz     loc_18002793E
0x180027a7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027a84  jb      loc_18002769E
0x180027a8a  mov     edx, 0Fh
0x180027a8f  jmp     loc_180027C81
0x180027a94  mov     eax, 1041h
0x180027a99  cmp     [rbp+0], ax
0x180027a9d  jnz     loc_180027802
0x180027aa3  mov     [r14], ax
0x180027aa7  mov     eax, [rbp+8]
0x180027aaa  mov     [r14+8], eax
0x180027aae  mov     ecx, [rbp+8]
0x180027ab1  shl     rcx, 4; cb
0x180027ab5  call    cs:__imp_CoTaskMemAlloc
0x180027abb  mov     [r14+10h], rax
0x180027abf  mov     rbx, rax
0x180027ac2  test    rax, rax
0x180027ac5  jz      loc_180027840
0x180027acb  mov     rdi, [rbp+10h]
0x180027acf  mov     esi, r13d
0x180027ad2  mov     r15d, r13d
0x180027ad5  cmp     [rbp+8], r15d
0x180027ad9  jbe     loc_18002769E
0x180027adf  mov     eax, [rdi]
0x180027ae1  mov     [rbx], eax
0x180027ae3  mov     ecx, [rdi]; cb
0x180027ae5  call    cs:__imp_CoTaskMemAlloc
0x180027aeb  mov     [rbx+8], rax
0x180027aef  test    rax, rax
0x180027af2  jz      loc_180027880
0x180027af8  mov     r8d, [rdi]; Size
0x180027afb  mov     rcx, rax; void *
0x180027afe  mov     rdx, [rdi+8]; Src
0x180027b02  call    memcpy_0
0x180027b07  add     rbx, 10h
0x180027b0b  add     rdi, 10h
0x180027b0f  inc     r15d
0x180027b12  jmp     short loc_180027AD5
0x180027b14  mov     rax, [rax]
0x180027b17  mov     edx, 7F0h
0x180027b1c  mov     rax, [rax+8]
0x180027b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b25  test    eax, eax
0x180027b27  jz      loc_180027834
0x180027b2d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027b34  cmp     [rbx+8], r13b
0x180027b38  jnz     loc_18002796B
0x180027b3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027b45  jb      loc_18002790C
0x180027b4b  mov     edx, 13h
0x180027b50  mov     [rsp+58h+var_38], esi
  ... truncated ...
```
