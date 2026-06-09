# CMFPropVariant::Copy(tagPROPVARIANT const *)

- ea: `0x180013110`
- end: `0x180013835`
- name: `?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z`
- size: `1829`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)`
- caller_count: `17`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180010140`
- `0x180012a3c`
- `0x180014bf0`
- `0x180060ea0`
- `0x1800638a0`
- `0x180069870`
- `0x180076a70`
- `0x180077d58`
- `0x1800862b0`
- `0x18009da30`
- `0x1800ad900`
- `0x1800b6db0`
- `0x1800b8d80`
- `0x1800dc9ac`
- `0x1800e5a90`
- `0x1800e6bb0`
- `0x180110440`

## callees

- `0x180005cf4`
- `0x180013110`
- `0x18001c6c0`
- `0x180077708`
- `0x180079680`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013219`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013182`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013219`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001329b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800131ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001329b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013265`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013265`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013168`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800131ff`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180013168`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800131ff`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013337`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013382`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800133c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001340e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013446`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013498`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013337`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013382`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800133c8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001340e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013446`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013498`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001363a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013670`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001363a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013670`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800131c0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800131c0`

## string_xrefs

- `0x180013143`: `CMFPropVariant::Copy`
- `0x180013552`: `CMFPropVariant::Copy`
- `0x180013755`: `CMFPropVariant::Copy`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Copy(PROPVARIANT *pvarDest, PROPVARIANT *pvarSrc)
{
  CallStackTracing *v4; // rbx
  char *v5; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdx
  CallStackTracing *v11; // rcx
  HRESULT v12; // esi
  CallStackTracing *v13; // rbx
  GUID *v14; // rdi
  DWORD v15; // ebp
  GUID *v16; // rax
  int v17; // eax
  int v18; // eax
  CallStackTracing *v20; // rcx
  __int64 v21; // rax
  CallStackTracing *v22; // rcx
  __int64 v23; // rax
  CallStackTracing *v24; // rax
  CallStackTracing *v25; // rax
  CallStackTracing *v26; // rax
  CallStackTracing *v27; // rax
  CallStackTracing *v28; // rax
  CallStackTracing *v29; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v31; // rax
  struct CallStackContext *v32; // rax
  struct CallStackContext *v33; // rax
  struct CallStackContext *v34; // rax
  struct CallStackContext *v35; // rax
  __int64 v36; // rdx
  BYTE *v37; // rax
  BYTE *v38; // rbx
  BYTE *pData; // rdi
  unsigned int i; // r15d
  void *v41; // rax
  __int64 v42; // rdx

  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v4 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v5 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v20 = CallStackTracing::s_wpInstance;
      }
      v21 = (**(__int64 (__fastcall ***)(CallStackTracing *))v20)(v20);
      if ( v21 )
        v5 = (char *)v21;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[8 * v9] = "CMFPropVariant::Copy";
      *(_DWORD *)&v5[8 * v9 + 8] = 181;
    }
    ++*((_DWORD *)v5 + 497);
  }
  if ( pvarDest == pvarSrc )
  {
    v12 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(pvarDest, pvarSrc);
      CallStackTracing::s_wpInstance = v24;
      if ( !v24 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::Copy", 190, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_11;
    v36 = 15;
LABEL_91:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v36, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, pvarDest, v12);
    goto LABEL_11;
  }
  v12 = PropVariantCopy(pvarDest, pvarSrc);
  if ( v12 >= 0 )
    goto LABEL_11;
  if ( pvarSrc->vt != 4161 )
  {
    v12 = -1072875800;
    if ( !CallStackTracing::s_wpInstance )
    {
      v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v10);
      CallStackTracing::s_wpInstance = v25;
      v11 = v25;
      if ( !v25 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v31 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v31 + 499) != -1072875800 )
        CallStackContext::TraceFailure(v31, "CMFPropVariant::Copy", 241, -1072875800);
    }
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        pvarDest,
        -1072875800);
LABEL_45:
    if ( !CallStackTracing::s_wpInstance )
    {
      v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v10);
      CallStackTracing::s_wpInstance = v29;
      if ( !v29 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v35 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v35 + 499) != v12 )
        CallStackContext::TraceFailure(v35, "CMFPropVariant::Copy", 247, v12);
    }
    if ( !g_wppLevels )
      goto LABEL_11;
    v36 = 20;
    goto LABEL_91;
  }
  pvarDest->vt = 4161;
  pvarDest->lVal = pvarSrc->lVal;
  v37 = (BYTE *)CoTaskMemAlloc(16LL * pvarSrc->ulVal);
  pvarDest->bstrblobVal.pData = v37;
  v38 = v37;
  if ( !v37 )
  {
    v12 = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v10);
      CallStackTracing::s_wpInstance = v26;
      v11 = v26;
      if ( !v26 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v32 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v32 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v32, "CMFPropVariant::Copy", 224, -2147024882);
    }
    if ( g_wppLevels )
    {
      v42 = 16;
LABEL_86:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v42,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        pvarDest,
        -2147024882);
    }
    goto LABEL_45;
  }
  pData = pvarSrc->bstrblobVal.pData;
  v12 = 0;
  for ( i = 0; pvarSrc->lVal > i; ++i )
  {
    *(_DWORD *)v38 = *(_DWORD *)pData;
    v41 = CoTaskMemAlloc(*(unsigned int *)pData);
    *((_QWORD *)v38 + 1) = v41;
    if ( !v41 )
    {
      v12 = -2147024882;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v10);
        CallStackTracing::s_wpInstance = v27;
        v11 = v27;
        if ( !v27 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v33 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v33, "CMFPropVariant::Copy", 231, -2147024882);
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
          pvarDest,
          -2147024882);
      if ( !CallStackTracing::s_wpInstance )
      {
        v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v11, v10);
        CallStackTracing::s_wpInstance = v28;
        v11 = v28;
        if ( !v28 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)v34 + 499) != -2147024882 )
          CallStackContext::TraceFailure(v34, "CMFPropVariant::Copy", 236, -2147024882);
      }
      if ( g_wppLevels )
      {
        v42 = 18;
        goto LABEL_86;
      }
      goto LABEL_45;
    }
    memcpy_0(v41, *((const void **)pData + 1), *(unsigned int *)pData);
    v38 += 16;
    pData += 16;
  }
LABEL_11:
  v13 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v14 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v15 = GetLastError();
    v16 = (GUID *)TlsGetValue(*((_DWORD *)v13 + 3));
    if ( v16 )
    {
      v14 = v16;
    }
    else if ( !GetLastError() )
    {
      v22 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v22 = CallStackTracing::s_wpInstance;
      }
      v23 = (**(__int64 (__fastcall ***)(CallStackTracing *))v22)(v22);
      if ( v23 )
        v14 = (GUID *)v23;
    }
    SetLastError(v15);
    v17 = *(_DWORD *)&v14[124].Data2;
    if ( v17 )
    {
      v18 = v17 - 1;
      *(_DWORD *)&v14[124].Data2 = v18;
      if ( !v18 )
      {
        *(_DWORD *)&v14[124].Data2 = 0;
        *(_QWORD *)&v14[126].Data1 = 0;
        *(_DWORD *)&v14[124].Data4[4] = 0;
        v14[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v14[126].Data4 = 0;
        v14[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180013110  mov     [rsp+arg_10], rbx
0x180013115  mov     [rsp+arg_18], rbp
0x18001311a  push    rsi
0x18001311b  push    rdi
0x18001311c  push    r13
0x18001311e  push    r14
0x180013120  push    r15
0x180013122  sub     rsp, 30h
0x180013126  xor     r13d, r13d
0x180013129  mov     rbp, rdx
0x18001312c  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180013133  mov     r14, rcx
0x180013136  jz      loc_180013291
0x18001313c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013143  lea     r15, aCmfpropvariant_18; "CMFPropVariant::Copy"
0x18001314a  cmp     [rbx+8], r13b
0x18001314e  jz      short loc_1800131B1
0x180013150  lea     rdi, [rbx+0D0h]
0x180013157  call    cs:__imp_GetLastError
0x18001315e  nop     dword ptr [rax+rax+00h]
0x180013163  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180013166  mov     esi, eax
0x180013168  call    cs:__imp_TlsGetValue
0x18001316f  nop     dword ptr [rax+rax+00h]
0x180013174  test    rax, rax
0x180013177  jz      loc_18001329B
0x18001317d  mov     rdi, rax
0x180013180  mov     ecx, esi; dwErrCode
0x180013182  call    cs:__imp_SetLastError
0x180013189  nop     dword ptr [rax+rax+00h]
0x18001318e  mov     eax, [rdi+7C4h]
0x180013194  cmp     eax, [rdi+7C8h]
0x18001319a  jnb     short loc_1800131AB
0x18001319c  add     rax, rax
0x18001319f  mov     [rdi+rax*8], r15
0x1800131a3  mov     dword ptr [rdi+rax*8+8], 0B5h
0x1800131ab  inc     dword ptr [rdi+7C4h]
0x1800131b1  cmp     r14, rbp
0x1800131b4  jz      loc_180013325
0x1800131ba  mov     rdx, rbp; pvarSrc
0x1800131bd  mov     rcx, r14; pvarDest
0x1800131c0  call    cs:__imp_PropVariantCopy
0x1800131c7  nop     dword ptr [rax+rax+00h]
0x1800131cc  mov     esi, eax
0x1800131ce  test    eax, eax
0x1800131d0  js      loc_180013619
0x1800131d6  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800131dd  cmp     [rbx+8], r13b
0x1800131e1  jz      loc_180013277
0x1800131e7  lea     rdi, [rbx+0D0h]
0x1800131ee  call    cs:__imp_GetLastError
0x1800131f5  nop     dword ptr [rax+rax+00h]
0x1800131fa  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800131fd  mov     ebp, eax
0x1800131ff  call    cs:__imp_TlsGetValue
0x180013206  nop     dword ptr [rax+rax+00h]
0x18001320b  test    rax, rax
0x18001320e  jz      loc_1800132D2
0x180013214  mov     rdi, rax
0x180013217  mov     ecx, ebp; dwErrCode
0x180013219  call    cs:__imp_SetLastError
0x180013220  nop     dword ptr [rax+rax+00h]
0x180013225  mov     eax, [rdi+7C4h]
0x18001322b  test    eax, eax
0x18001322d  jz      short loc_180013277
0x18001322f  sub     eax, 1
0x180013232  mov     [rdi+7C4h], eax
0x180013238  jnz     short loc_180013277
0x18001323a  mov     [rdi+7C4h], r13d
0x180013241  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180013248  mov     [rdi+7E0h], r13
0x18001324f  mov     [rdi+7CCh], r13d
0x180013256  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001325e  mov     [rdi+7E8h], r13d
0x180013265  call    cs:__imp_GetCurrentThreadId
0x18001326c  nop     dword ptr [rax+rax+00h]
0x180013271  mov     [rdi+7C0h], eax
0x180013277  mov     rbx, [rsp+58h+arg_10]
0x18001327c  mov     eax, esi
0x18001327e  mov     rbp, [rsp+58h+arg_18]
0x180013283  add     rsp, 30h
0x180013287  pop     r15
0x180013289  pop     r14
0x18001328b  pop     r13
0x18001328d  pop     rdi
0x18001328e  pop     rsi
0x18001328f  retn
0x180013291  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180013296  jmp     loc_18001313C
0x18001329b  call    cs:__imp_GetLastError
0x1800132a2  nop     dword ptr [rax+rax+00h]
0x1800132a7  test    eax, eax
0x1800132a9  jnz     loc_180013180
0x1800132af  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800132b6  test    rcx, rcx
0x1800132b9  jz      short loc_180013309
0x1800132bb  mov     rax, [rcx]
0x1800132be  mov     rax, [rax]
0x1800132c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132c6  test    rax, rax
0x1800132c9  cmovnz  rdi, rax
0x1800132cd  jmp     loc_180013180
0x1800132d2  call    cs:__imp_GetLastError
0x1800132d9  nop     dword ptr [rax+rax+00h]
0x1800132de  test    eax, eax
0x1800132e0  jnz     loc_180013217
0x1800132e6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800132ed  test    rcx, rcx
0x1800132f0  jz      short loc_180013317
0x1800132f2  mov     rax, [rcx]
0x1800132f5  mov     rax, [rax]
0x1800132f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132fd  test    rax, rax
0x180013300  cmovnz  rdi, rax
0x180013304  jmp     loc_180013217
0x180013309  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001330e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013315  jmp     short loc_1800132BB
0x180013317  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001331c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013323  jmp     short loc_1800132F2
0x180013325  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18001332c  mov     esi, 80004003h
0x180013331  jnz     loc_1800135F1
0x180013337  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001333e  nop     dword ptr [rax+rax+00h]
0x180013343  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001334a  mov     rcx, rax
0x18001334d  test    rax, rax
0x180013350  jnz     loc_1800135D8
0x180013356  lea     rbp, qword_1801B97E0
0x18001335d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x180013364  jmp     loc_1800135F1
0x180013369  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180013370  lea     rbp, qword_1801B97E0
0x180013377  mov     esi, 0C00D36E8h
0x18001337c  jnz     loc_1800136BE
0x180013382  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013389  nop     dword ptr [rax+rax+00h]
0x18001338e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013395  mov     rcx, rax
0x180013398  test    rax, rax
0x18001339b  jnz     loc_1800136A5
0x1800133a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x1800133a8  jmp     loc_1800136BE
0x1800133ad  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x1800133b4  lea     rbp, qword_1801B97E0
0x1800133bb  mov     edi, 8007000Eh
0x1800133c0  mov     esi, edi
0x1800133c2  jnz     loc_180013703
0x1800133c8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800133cf  nop     dword ptr [rax+rax+00h]
0x1800133d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800133db  mov     rcx, rax
0x1800133de  test    rax, rax
0x1800133e1  jnz     loc_1800136EA
0x1800133e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x1800133ee  jmp     loc_180013703
0x1800133f3  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x1800133fa  lea     rbp, qword_1801B97E0
0x180013401  mov     edi, 8007000Eh
0x180013406  mov     esi, edi
0x180013408  jnz     loc_180013744
0x18001340e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013415  nop     dword ptr [rax+rax+00h]
0x18001341a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013421  mov     rcx, rax
0x180013424  test    rax, rax
0x180013427  jnz     loc_18001372B
0x18001342d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x180013434  jmp     loc_180013744
0x180013439  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180013440  jnz     loc_1800137AA
0x180013446  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001344d  nop     dword ptr [rax+rax+00h]
0x180013452  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013459  mov     rcx, rax
0x18001345c  test    rax, rax
0x18001345f  jnz     loc_180013791
0x180013465  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x18001346c  jmp     loc_1800137AA
0x180013471  mov     rcx, cs:WPP_GLOBAL_Control
0x180013478  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18001347f  mov     r9, r14
0x180013482  mov     rcx, [rcx+10h]
0x180013486  call    WPP_SF_qD
0x18001348b  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180013492  jnz     loc_1800137EF
0x180013498  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001349f  nop     dword ptr [rax+rax+00h]
0x1800134a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800134ab  mov     rcx, rax
0x1800134ae  test    rax, rax
0x1800134b1  jnz     loc_1800137D6
0x1800134b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbp; CallStackTracing * CallStackTracing::s_wpInstance
0x1800134be  jmp     loc_1800137EF
0x1800134c3  mov     rcx, rbx; this
0x1800134c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800134cb  cmp     [rax+7CCh], esi
0x1800134d1  jz      loc_180013602
0x1800134d7  mov     r9d, esi; int
0x1800134da  mov     r8d, 0BEh; int
0x1800134e0  mov     rdx, r15; char *
0x1800134e3  mov     rcx, rax; this
0x1800134e6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800134eb  jmp     loc_180013602
0x1800134f0  mov     rcx, rbx; this
0x1800134f3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800134f8  cmp     [rax+7CCh], esi
0x1800134fe  jz      loc_1800136CF
0x180013504  mov     r9d, esi; int
0x180013507  mov     r8d, 0F1h; int
0x18001350d  mov     rdx, r15; char *
0x180013510  mov     rcx, rax; this
0x180013513  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013518  jmp     loc_1800136CF
0x18001351d  mov     rcx, rbx; this
0x180013520  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013525  cmp     [rax+7CCh], edi
0x18001352b  jz      loc_180013714
0x180013531  mov     r9d, edi; int
0x180013534  mov     r8d, 0E0h; int
0x18001353a  mov     rdx, r15; char *
0x18001353d  mov     rcx, rax; this
0x180013540  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013545  jmp     loc_180013714
0x18001354a  mov     rcx, rbx; this
0x18001354d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013552  lea     r15, aCmfpropvariant_18; "CMFPropVariant::Copy"
0x180013559  cmp     [rax+7CCh], edi
0x18001355f  jz      loc_18001375C
0x180013565  mov     r9d, edi; int
0x180013568  mov     r8d, 0E7h; int
0x18001356e  mov     rdx, r15; char *
0x180013571  mov     rcx, rax; this
0x180013574  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013579  jmp     loc_18001375C
0x18001357e  mov     rcx, rbx; this
0x180013581  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013586  cmp     [rax+7CCh], edi
0x18001358c  jz      loc_1800137BB
0x180013592  mov     r9d, edi; int
0x180013595  mov     r8d, 0ECh; int
0x18001359b  mov     rdx, r15; char *
0x18001359e  mov     rcx, rax; this
0x1800135a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800135a6  jmp     loc_1800137BB
0x1800135ab  mov     rcx, rbx; this
0x1800135ae  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800135b3  cmp     [rax+7CCh], esi
0x1800135b9  jz      loc_180013800
0x1800135bf  mov     r9d, esi; int
0x1800135c2  mov     r8d, 0F7h; int
0x1800135c8  mov     rdx, r15; char *
0x1800135cb  mov     rcx, rax; this
0x1800135ce  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800135d3  jmp     loc_180013800
0x1800135d8  mov     rax, [rax]
0x1800135db  mov     edx, 7F0h
0x1800135e0  mov     rax, [rax+8]
0x1800135e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135e9  test    eax, eax
0x1800135eb  jz      loc_180013356
0x1800135f1  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800135f8  cmp     [rbx+8], r13b
0x1800135fc  jnz     loc_1800134C3
0x180013602  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180013609  jb      loc_1800131D6
0x18001360f  mov     edx, 0Fh
0x180013614  jmp     loc_180013812
0x180013619  mov     eax, 1041h
0x18001361e  cmp     [rbp+0], ax
0x180013622  jnz     loc_180013369
0x180013628  mov     [r14], ax
0x18001362c  mov     eax, [rbp+8]
0x18001362f  mov     [r14+8], eax
0x180013633  mov     ecx, [rbp+8]
0x180013636  shl     rcx, 4; cb
0x18001363a  call    cs:__imp_CoTaskMemAlloc
0x180013641  nop     dword ptr [rax+rax+00h]
0x180013646  mov     [r14+10h], rax
0x18001364a  mov     rbx, rax
0x18001364d  test    rax, rax
0x180013650  jz      loc_1800133AD
0x180013656  mov     rdi, [rbp+10h]
0x18001365a  mov     esi, r13d
0x18001365d  mov     r15d, r13d
0x180013660  cmp     [rbp+8], r15d
0x180013664  jbe     loc_1800131D6
0x18001366a  mov     eax, [rdi]
0x18001366c  mov     [rbx], eax
0x18001366e  mov     ecx, [rdi]; cb
0x180013670  call    cs:__imp_CoTaskMemAlloc
0x180013677  nop     dword ptr [rax+rax+00h]
0x18001367c  mov     [rbx+8], rax
0x180013680  test    rax, rax
0x180013683  jz      loc_1800133F3
0x180013689  mov     r8d, [rdi]; Size
0x18001368c  mov     rcx, rax; void *
0x18001368f  mov     rdx, [rdi+8]; Src
  ... truncated ...
```
