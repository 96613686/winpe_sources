# CMFPropVariant::SetElementData(ulong,void const *)

- ea: `0x18002d1a0`
- end: `0x18002da43`
- name: `?SetElementData@CMFPropVariant@@IEAAJKPEBX@Z`
- size: `2211`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, unsigned int, const void *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18002dcc0`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x18002bb30`
- `0x18002d1a0`
- `0x180121581`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d208`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d296`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d350`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d403`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d208`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d296`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d350`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002d403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d3a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d45c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d3a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d45c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d21c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d2b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d364`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d21c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d2b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d364`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d28b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d28b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d345`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d3f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d589`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d5ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d601`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::SetElementData(CMFPropVariant *this, unsigned int a2, const void *a3)
{
  unsigned __int8 *pbVal; // r15
  CallStackTracing *v7; // rbx
  CallStackContext *p_m_context; // rdi
  DWORD LastError; // esi
  CallStackContext *Value; // rax
  __int64 m_dwDepth; // rax
  __int64 v12; // rax
  CallStackTracing *v13; // rbx
  CallStackContext *v14; // rdi
  DWORD v15; // esi
  CallStackContext *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned __int16 vt; // dx
  int VarTypeSize; // esi
  CallStackTracing *v21; // rbx
  CallStackContext *v22; // rdi
  DWORD v23; // ebp
  CallStackContext *v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // eax
  CallStackTracing *v27; // rbx
  CallStackContext *v28; // rdi
  DWORD v29; // ebp
  CallStackContext *v30; // rax
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int16 v34; // dx
  __int64 v35; // rdx
  CallStackTracing *v36; // rcx
  CallStackTracing *v37; // rcx
  __int64 v38; // rax
  CallStackTracing *v39; // rcx
  CallStackTracing *v40; // rcx
  struct CallStackContext *v41; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v43; // rax
  __int64 v44; // rdx
  struct CallStackContext *v45; // rax
  struct CallStackContext *v46; // rax
  unsigned int v47; // [rsp+30h] [rbp-48h] BYREF
  size_t Size[8]; // [rsp+34h] [rbp-44h] BYREF

  LODWORD(Size[0]) = 0;
  pbVal = 0;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
  }
  v7 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    p_m_context = &CallStackTracing::s_wpInstance->m_context;
    LastError = GetLastError();
    Value = (CallStackContext *)TlsGetValue(v7->m_dwTLSIndex);
    if ( Value )
      goto LABEL_4;
    if ( !GetLastError() )
    {
      v36 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v36 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v36 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      Value = (CallStackContext *)v36->AllocateNewContext(v36);
      if ( Value )
LABEL_4:
        p_m_context = Value;
    }
    SetLastError(LastError);
    m_dwDepth = p_m_context->m_dwDepth;
    if ( (unsigned int)m_dwDepth < p_m_context->m_dwMaxDepth )
    {
      v12 = m_dwDepth;
      p_m_context->m_rgInfo[v12].m_pszFunction = "CMFPropVariant::SetElementData";
      p_m_context->m_rgInfo[v12].m_lineNumber = 2869;
    }
    ++p_m_context->m_dwDepth;
  }
  v47 = 0;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
  }
  v13 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v14 = &CallStackTracing::s_wpInstance->m_context;
    v15 = GetLastError();
    v16 = (CallStackContext *)TlsGetValue(v13->m_dwTLSIndex);
    if ( v16 )
    {
      v14 = v16;
    }
    else if ( !GetLastError() )
    {
      v37 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v37 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v37 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v38 = v37->AllocateNewContext(v37);
      if ( v38 )
        v14 = (CallStackContext *)v38;
    }
    SetLastError(v15);
    v17 = v14->m_dwDepth;
    if ( (unsigned int)v17 < v14->m_dwMaxDepth )
    {
      v18 = v17;
      v14->m_rgInfo[v18].m_pszFunction = "CMFPropVariant::GetElementDataPtr";
      v14->m_rgInfo[v18].m_lineNumber = 2903;
    }
    ++v14->m_dwDepth;
  }
  vt = this->vt;
  if ( (this->vt & 0x1000) != 0 )
  {
    if ( vt && this->decVal.Lo32 > a2 )
    {
      VarTypeSize = CMFPropVariantConvert::GetVarTypeSize(this, &v47);
      if ( VarTypeSize >= 0 )
      {
        pbVal = &this->bstrblobVal.pData[v47 * a2];
        goto LABEL_20;
      }
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
      if ( CallStackTracing::s_wpInstance->m_fEnabled )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( ThreadRelativeContext->m_result != VarTypeSize )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::GetElementDataPtr", 2951, VarTypeSize);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v35 = 189;
        goto LABEL_86;
      }
      goto LABEL_20;
    }
    VarTypeSize = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      v43 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( v43->m_result != -2147024809 )
        CallStackContext::TraceFailure(v43, "CMFPropVariant::GetElementDataPtr", 2944, -2147024809);
    }
    if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
      goto LABEL_20;
    v35 = 188;
LABEL_86:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v35,
      WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
      this,
      VarTypeSize);
    goto LABEL_20;
  }
  if ( !a2 )
  {
    VarTypeSize = 0;
    v34 = vt & 0xFFF;
    if ( v34 == 12 || v34 == 72 )
      pbVal = this->pbVal;
    else
      pbVal = &this->bVal;
    goto LABEL_20;
  }
  VarTypeSize = -2147024809;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
  }
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v41 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( v41->m_result != -2147024809 )
      CallStackContext::TraceFailure(v41, "CMFPropVariant::GetElementDataPtr", 2911, -2147024809);
  }
  if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
  {
    v35 = 187;
    goto LABEL_86;
  }
LABEL_20:
  v21 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v22 = &CallStackTracing::s_wpInstance->m_context;
    v23 = GetLastError();
    v24 = (CallStackContext *)TlsGetValue(v21->m_dwTLSIndex);
    if ( v24 )
      goto LABEL_22;
    if ( !GetLastError() )
    {
      v39 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v39 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v24 = (CallStackContext *)v39->AllocateNewContext(v39);
      if ( v24 )
LABEL_22:
        v22 = v24;
    }
    SetLastError(v23);
    v25 = v22->m_dwDepth;
    if ( v25 )
    {
      v26 = v25 - 1;
      v22->m_dwDepth = v26;
      if ( !v26 )
      {
        v22->m_dwDepth = 0;
        *(_QWORD *)&v22->m_instanceId = 0;
        v22->m_result = 0;
        v22->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
        v22->m_dwErrorsInContext = 0;
        v22->m_dwThreadID = GetCurrentThreadId();
      }
    }
  }
  if ( VarTypeSize < 0 )
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      v45 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( v45->m_result != VarTypeSize )
        CallStackContext::TraceFailure(v45, "CMFPropVariant::SetElementData", 2877, VarTypeSize);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v44 = 184;
LABEL_113:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v44,
        WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
        this,
        VarTypeSize);
    }
  }
  else
  {
    VarTypeSize = CMFPropVariantConvert::GetVarTypeSize(this, (unsigned int *)Size);
    if ( VarTypeSize >= 0 )
    {
      memcpy_0(pbVal, a3, LODWORD(Size[0]));
      goto LABEL_29;
    }
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      v46 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( v46->m_result != VarTypeSize )
        CallStackContext::TraceFailure(v46, "CMFPropVariant::SetElementData", 2883, VarTypeSize);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v44 = 185;
      goto LABEL_113;
    }
  }
LABEL_29:
  v27 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v28 = &CallStackTracing::s_wpInstance->m_context;
    v29 = GetLastError();
    v30 = (CallStackContext *)TlsGetValue(v27->m_dwTLSIndex);
    if ( v30 )
      goto LABEL_31;
    if ( !GetLastError() )
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v40 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v30 = (CallStackContext *)v40->AllocateNewContext(v40);
      if ( v30 )
LABEL_31:
        v28 = v30;
    }
    SetLastError(v29);
    v31 = v28->m_dwDepth;
    if ( v31 )
    {
      v32 = v31 - 1;
      v28->m_dwDepth = v32;
      if ( !v32 )
      {
        v28->m_dwDepth = 0;
        *(_QWORD *)&v28->m_instanceId = 0;
        v28->m_result = 0;
        v28->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
        v28->m_dwErrorsInContext = 0;
        v28->m_dwThreadID = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)VarTypeSize;
}

```

## disassembly

```asm
0x18002d1a0  mov     [rsp+arg_18], rbx
0x18002d1a5  push    rbp
0x18002d1a6  push    rsi
0x18002d1a7  push    rdi
0x18002d1a8  push    r12
0x18002d1aa  push    r13
0x18002d1ac  push    r14
0x18002d1ae  push    r15
0x18002d1b0  sub     rsp, 40h
0x18002d1b4  xor     r13d, r13d
0x18002d1b7  lea     rsi, stru_1801F8A30
0x18002d1be  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d1c5  lea     rdi, stru_1801FC290
0x18002d1cc  mov     r12, r8
0x18002d1cf  mov     dword ptr [rsp+78h+Size], r13d
0x18002d1d4  mov     ebp, edx
0x18002d1d6  mov     r14, rcx
0x18002d1d9  mov     r15d, r13d
0x18002d1dc  jz      loc_18002D4B2
0x18002d1e2  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d1e9  lea     rcx, aCmfpropvariant_4; "CMFPropVariant::SetElementData"
0x18002d1f0  cmp     [rbx+8], r13b
0x18002d1f4  jz      short loc_18002D25A
0x18002d1f6  lea     rdi, [rbx+0D0h]
0x18002d1fd  call    cs:__imp_GetLastError
0x18002d203  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002d206  mov     esi, eax
0x18002d208  call    cs:__imp_TlsGetValue
0x18002d20e  test    rax, rax
0x18002d211  jz      loc_18002D552
0x18002d217  mov     rdi, rax
0x18002d21a  mov     ecx, esi; dwErrCode
0x18002d21c  call    cs:__imp_SetLastError
0x18002d222  mov     eax, [rdi+7C4h]
0x18002d228  lea     rcx, aCmfpropvariant_4; "CMFPropVariant::SetElementData"
0x18002d22f  lea     rsi, stru_1801F8A30
0x18002d236  cmp     eax, [rdi+7C8h]
0x18002d23c  jnb     short loc_18002D24D
0x18002d23e  add     rax, rax
0x18002d241  mov     [rdi+rax*8], rcx
0x18002d245  mov     dword ptr [rdi+rax*8+8], 0B35h
0x18002d24d  inc     dword ptr [rdi+7C4h]
0x18002d253  lea     rdi, stru_1801FC290
0x18002d25a  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d261  mov     [rsp+78h+var_48], r13d
0x18002d266  jz      loc_18002D4E5
0x18002d26c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d273  lea     rcx, aCmfpropvariant; "CMFPropVariant::GetElementDataPtr"
0x18002d27a  cmp     [rbx+8], r13b
0x18002d27e  jz      loc_18002D706
0x18002d284  lea     rdi, [rbx+0D0h]
0x18002d28b  call    cs:__imp_GetLastError
0x18002d291  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002d294  mov     esi, eax
0x18002d296  call    cs:__imp_TlsGetValue
0x18002d29c  test    rax, rax
0x18002d29f  jz      loc_18002D589
0x18002d2a5  mov     rdi, rax
0x18002d2a8  lea     rbx, stru_1801FC290
0x18002d2af  mov     ecx, esi; dwErrCode
0x18002d2b1  call    cs:__imp_SetLastError
0x18002d2b7  mov     eax, [rdi+7C4h]
0x18002d2bd  lea     rcx, aCmfpropvariant; "CMFPropVariant::GetElementDataPtr"
0x18002d2c4  cmp     eax, [rdi+7C8h]
0x18002d2ca  jnb     short loc_18002D2DB
0x18002d2cc  add     rax, rax
0x18002d2cf  mov     [rdi+rax*8], rcx
0x18002d2d3  mov     dword ptr [rdi+rax*8+8], 0B57h
0x18002d2db  inc     dword ptr [rdi+7C4h]
0x18002d2e1  movzx   edx, word ptr [r14]
0x18002d2e5  mov     eax, 1000h
0x18002d2ea  movzx   ecx, dx
0x18002d2ed  and     cx, ax
0x18002d2f0  cmp     r13w, cx
0x18002d2f4  jz      loc_18002D482
0x18002d2fa  cmp     r13w, dx
0x18002d2fe  jz      loc_18002D79E
0x18002d304  cmp     [r14+8], ebp
0x18002d308  jbe     loc_18002D79E
0x18002d30e  lea     rdx, [rsp+78h+var_48]; unsigned int *
0x18002d313  mov     rcx, r14; struct CMFPropVariant *
0x18002d316  call    ?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z; CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)
0x18002d31b  mov     esi, eax
0x18002d31d  test    eax, eax
0x18002d31f  js      loc_18002D854
0x18002d325  imul    ebp, [rsp+78h+var_48]
0x18002d32a  mov     r15d, ebp
0x18002d32d  add     r15, [r14+10h]
0x18002d331  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d338  cmp     [rbx+8], r13b
0x18002d33c  jz      short loc_18002D3B5
0x18002d33e  lea     rdi, [rbx+0D0h]
0x18002d345  call    cs:__imp_GetLastError
0x18002d34b  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002d34e  mov     ebp, eax
0x18002d350  call    cs:__imp_TlsGetValue
0x18002d356  test    rax, rax
0x18002d359  jz      loc_18002D5CA
0x18002d35f  mov     rdi, rax
0x18002d362  mov     ecx, ebp; dwErrCode
0x18002d364  call    cs:__imp_SetLastError
0x18002d36a  mov     eax, [rdi+7C4h]
0x18002d370  test    eax, eax
0x18002d372  jz      short loc_18002D3B5
0x18002d374  sub     eax, 1
0x18002d377  mov     [rdi+7C4h], eax
0x18002d37d  jnz     short loc_18002D3B5
0x18002d37f  mov     [rdi+7C4h], r13d
0x18002d386  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002d38d  mov     [rdi+7E0h], r13
0x18002d394  mov     [rdi+7CCh], r13d
0x18002d39b  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002d3a2  mov     [rdi+7E8h], r13d
0x18002d3a9  call    cs:__imp_GetCurrentThreadId
0x18002d3af  mov     [rdi+7C0h], eax
0x18002d3b5  test    esi, esi
0x18002d3b7  js      loc_18002D90D
0x18002d3bd  lea     rdx, [rsp+78h+Size]; unsigned int *
0x18002d3c2  mov     rcx, r14; struct CMFPropVariant *
0x18002d3c5  call    ?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z; CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)
0x18002d3ca  mov     esi, eax
0x18002d3cc  test    eax, eax
0x18002d3ce  js      loc_18002D999
0x18002d3d4  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x18002d3d9  mov     rdx, r12; Src
0x18002d3dc  mov     rcx, r15; void *
0x18002d3df  call    memcpy_0
0x18002d3e4  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d3eb  cmp     [rbx+8], r13b
0x18002d3ef  jz      short loc_18002D468
0x18002d3f1  lea     rdi, [rbx+0D0h]
0x18002d3f8  call    cs:__imp_GetLastError
0x18002d3fe  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002d401  mov     ebp, eax
0x18002d403  call    cs:__imp_TlsGetValue
0x18002d409  test    rax, rax
0x18002d40c  jz      loc_18002D601
0x18002d412  mov     rdi, rax
0x18002d415  mov     ecx, ebp; dwErrCode
0x18002d417  call    cs:__imp_SetLastError
0x18002d41d  mov     eax, [rdi+7C4h]
0x18002d423  test    eax, eax
0x18002d425  jz      short loc_18002D468
0x18002d427  sub     eax, 1
0x18002d42a  mov     [rdi+7C4h], eax
0x18002d430  jnz     short loc_18002D468
0x18002d432  mov     [rdi+7C4h], r13d
0x18002d439  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002d440  mov     [rdi+7E0h], r13
0x18002d447  mov     [rdi+7CCh], r13d
0x18002d44e  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002d455  mov     [rdi+7E8h], r13d
0x18002d45c  call    cs:__imp_GetCurrentThreadId
0x18002d462  mov     [rdi+7C0h], eax
0x18002d468  mov     rbx, [rsp+78h+arg_18]
0x18002d470  mov     eax, esi
0x18002d472  add     rsp, 40h
0x18002d476  pop     r15
0x18002d478  pop     r14
0x18002d47a  pop     r13
0x18002d47c  pop     r12
0x18002d47e  pop     rdi
0x18002d47f  pop     rsi
0x18002d480  pop     rbp
0x18002d481  retn
0x18002d482  test    ebp, ebp
0x18002d484  jnz     loc_18002D518
0x18002d48a  mov     eax, 0FFFh
0x18002d48f  mov     esi, r13d
0x18002d492  and     dx, ax
0x18002d495  cmp     dx, 0Ch
0x18002d499  jz      loc_18002D638
0x18002d49f  cmp     dx, 48h ; 'H'
0x18002d4a3  jz      loc_18002D638
0x18002d4a9  lea     r15, [r14+8]
0x18002d4ad  jmp     loc_18002D331
0x18002d4b2  mov     rax, cs:stru_1801FC290.__vftable
0x18002d4b9  mov     edx, 7F0h
0x18002d4be  mov     rcx, rdi
0x18002d4c1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d4c8  mov     rax, [rax+8]
0x18002d4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d4d1  test    eax, eax
0x18002d4d3  jnz     loc_18002D1E2
0x18002d4d9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d4e0  jmp     loc_18002D1E2
0x18002d4e5  mov     rax, cs:stru_1801FC290.__vftable
0x18002d4ec  mov     edx, 7F0h
0x18002d4f1  mov     rcx, rdi
0x18002d4f4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d4fb  mov     rax, [rax+8]
0x18002d4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d504  test    eax, eax
0x18002d506  jnz     loc_18002D26C
0x18002d50c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rsi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d513  jmp     loc_18002D26C
0x18002d518  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d51f  mov     esi, 80070057h
0x18002d524  jz      loc_18002D641
0x18002d52a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d531  cmp     [rbx+8], r13b
0x18002d535  jnz     loc_18002D823
0x18002d53b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002d542  jb      loc_18002D331
0x18002d548  mov     edx, 0BBh
0x18002d54d  jmp     loc_18002D800
0x18002d552  call    cs:__imp_GetLastError
0x18002d558  test    eax, eax
0x18002d55a  jnz     loc_18002D21A
0x18002d560  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d567  test    rcx, rcx
0x18002d56a  jz      loc_18002D67B
0x18002d570  mov     rax, [rcx]
0x18002d573  mov     rax, [rax]
0x18002d576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d57b  test    rax, rax
0x18002d57e  jnz     loc_18002D217
0x18002d584  jmp     loc_18002D21A
0x18002d589  call    cs:__imp_GetLastError
0x18002d58f  test    eax, eax
0x18002d591  jnz     loc_18002D2A8
0x18002d597  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d59e  lea     rbx, stru_1801FC290
0x18002d5a5  test    rcx, rcx
0x18002d5a8  jz      loc_18002D6B8
0x18002d5ae  mov     rax, [rcx]
0x18002d5b1  mov     rax, [rax]
0x18002d5b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5b9  test    rax, rax
0x18002d5bc  jz      loc_18002D2AF
0x18002d5c2  mov     rdi, rax
0x18002d5c5  jmp     loc_18002D2AF
0x18002d5ca  call    cs:__imp_GetLastError
0x18002d5d0  test    eax, eax
0x18002d5d2  jnz     loc_18002D362
0x18002d5d8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d5df  test    rcx, rcx
0x18002d5e2  jz      loc_18002D712
0x18002d5e8  mov     rax, [rcx]
0x18002d5eb  mov     rax, [rax]
0x18002d5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5f3  test    rax, rax
0x18002d5f6  jnz     loc_18002D35F
0x18002d5fc  jmp     loc_18002D362
0x18002d601  call    cs:__imp_GetLastError
0x18002d607  test    eax, eax
0x18002d609  jnz     loc_18002D415
0x18002d60f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d616  test    rcx, rcx
0x18002d619  jz      loc_18002D74C
0x18002d61f  mov     rax, [rcx]
0x18002d622  mov     rax, [rax]
0x18002d625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d62a  test    rax, rax
0x18002d62d  jnz     loc_18002D412
0x18002d633  jmp     loc_18002D415
0x18002d638  mov     r15, [r14+8]
0x18002d63c  jmp     loc_18002D331
0x18002d641  mov     rax, cs:stru_1801FC290.__vftable
0x18002d648  mov     edx, 7F0h
0x18002d64d  mov     rcx, rbx
0x18002d650  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d657  mov     rax, [rax+8]
0x18002d65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d660  test    eax, eax
0x18002d662  jnz     loc_18002D52A
0x18002d668  lea     rax, stru_1801F8A30
0x18002d66f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d676  jmp     loc_18002D52A
0x18002d67b  mov     rax, cs:stru_1801FC290.__vftable
0x18002d682  lea     rbx, stru_1801FC290
0x18002d689  mov     edx, 7F0h
0x18002d68e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d695  mov     rcx, rbx
0x18002d698  mov     rax, [rax+8]
0x18002d69c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6a1  test    eax, eax
0x18002d6a3  jnz     short loc_18002D6EE
0x18002d6a5  lea     rcx, stru_1801F8A30
0x18002d6ac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d6b3  jmp     loc_18002D570
0x18002d6b8  mov     rax, cs:stru_1801FC290.__vftable
0x18002d6bf  mov     edx, 7F0h
0x18002d6c4  mov     rcx, rbx
0x18002d6c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d6ce  mov     rax, [rax+8]
0x18002d6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6d7  test    eax, eax
0x18002d6d9  jnz     short loc_18002D6FA
0x18002d6db  lea     rcx, stru_1801F8A30
0x18002d6e2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d6e9  jmp     loc_18002D5AE
0x18002d6ee  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d6f5  jmp     loc_18002D570
0x18002d6fa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002d701  jmp     loc_18002D5AE
0x18002d706  lea     rbx, stru_1801FC290
0x18002d70d  jmp     loc_18002D2E1
0x18002d712  mov     rax, cs:stru_1801FC290.__vftable
0x18002d719  lea     rcx, stru_1801FC290
  ... truncated ...
```
