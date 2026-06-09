# CMFPropVariant::Compare(tagPROPVARIANT const *,int *)

- ea: `0x180029230`
- end: `0x180029a20`
- name: `?Compare@CMFPropVariant@@QEBAJPEBUtagPROPVARIANT@@PEAH@Z`
- size: `2032`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, const struct tagPROPVARIANT *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180029f30`

## callees

- `0x18002146c`
- `0x1800214fc`
- `0x180024390`
- `0x180029230`
- `0x180120dd0`
- `0x180120de8`
- `0x180121575`
- `0x1801b2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029290`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002933a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029290`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002933a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029393`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800292a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002934e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800292a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002934e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002932f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002932f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800296e7`

## string_xrefs

- `0x180029270`: `CMFPropVariant::Compare`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::Compare(CMFPropVariant *this, CMFPropVariant *a2, int *a3)
{
  CallStackTracing *v6; // rbx
  CallStackContext *p_m_context; // rdi
  DWORD LastError; // r15d
  CallStackContext *Value; // rax
  __int64 m_dwDepth; // rax
  __int64 v11; // rax
  unsigned __int16 vt; // dx
  int v13; // edx
  int v14; // eax
  unsigned int v15; // ebp
  CallStackTracing *v16; // rbx
  CallStackContext *v17; // rdi
  DWORD v18; // esi
  CallStackContext *v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // eax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v24; // rdx
  unsigned __int64 Lo64; // rax
  unsigned __int64 v26; // rcx
  bool v27; // cf
  struct CallStackContext *v28; // rax
  struct CallStackContext *v29; // rax
  char cVal; // cl
  bool v31; // zf
  bool v32; // sf
  bool v33; // of
  unsigned __int8 bVal; // al
  unsigned __int8 v35; // cl
  unsigned __int16 uiVal; // ax
  unsigned __int16 v37; // cx
  struct CallStackContext *v38; // rax
  struct CallStackContext *v39; // rax
  CallStackTracing *v40; // rcx
  CallStackTracing *v41; // rcx
  __int16 iVal; // cx
  signed int lVal; // ecx
  unsigned int Lo32; // eax
  unsigned int v45; // ecx
  signed __int64 QuadPart; // rcx
  float fltVal; // xmm0_4
  float v48; // xmm1_4
  double dblVal; // xmm0_8
  double v50; // xmm1_8

  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::s_wpInstance = &stru_1801FC290;
    if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
      CallStackTracing::s_wpInstance = &stru_1801F8A30;
  }
  v6 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    p_m_context = &CallStackTracing::s_wpInstance->m_context;
    LastError = GetLastError();
    Value = (CallStackContext *)TlsGetValue(v6->m_dwTLSIndex);
    if ( Value )
      goto LABEL_4;
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
      Value = (CallStackContext *)v40->AllocateNewContext(v40);
      if ( Value )
LABEL_4:
        p_m_context = Value;
    }
    SetLastError(LastError);
    m_dwDepth = p_m_context->m_dwDepth;
    if ( (unsigned int)m_dwDepth < p_m_context->m_dwMaxDepth )
    {
      v11 = m_dwDepth;
      p_m_context->m_rgInfo[v11].m_pszFunction = "CMFPropVariant::Compare";
      p_m_context->m_rgInfo[v11].m_lineNumber = 1414;
    }
    ++p_m_context->m_dwDepth;
  }
  if ( this == a2 )
  {
    v15 = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::s_wpInstance = &stru_1801FC290;
      if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        CallStackTracing::s_wpInstance = &stru_1801F8A30;
    }
    if ( CallStackTracing::s_wpInstance->m_fEnabled )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( ThreadRelativeContext->m_result != -2147467261 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::Compare", 1423, -2147467261);
    }
    if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
    {
      v24 = 86;
      goto LABEL_27;
    }
  }
  else
  {
    *a3 = 0;
    vt = this->vt;
    if ( (this->vt & 0x1000) != 0 )
    {
      v15 = -1072875797;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
      if ( CallStackTracing::s_wpInstance->m_fEnabled )
      {
        v38 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( v38->m_result != -1072875797 )
          CallStackContext::TraceFailure(v38, "CMFPropVariant::Compare", 1436, -1072875797);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v24 = 87;
        goto LABEL_27;
      }
    }
    else
    {
      if ( a2->vt == vt )
      {
        v13 = vt & 0xFFF;
        if ( !v13 )
        {
LABEL_12:
          v14 = 0;
LABEL_13:
          v15 = 0;
          *a3 = v14;
          goto LABEL_14;
        }
        switch ( v13 )
        {
          case 1:
            goto LABEL_12;
          case 2:
            iVal = this->iVal;
            v33 = __OFSUB__(a2->iVal, iVal);
            v31 = a2->iVal == (unsigned __int16)iVal;
            v32 = (__int16)(a2->iVal - iVal) < 0;
            if ( a2->iVal >= iVal )
              goto LABEL_92;
            v14 = -1;
            goto LABEL_13;
          case 3:
          case 10:
          case 22:
            lVal = this->lVal;
            v33 = __OFSUB__(a2->decVal.Lo32, lVal);
            v31 = a2->decVal.Lo32 == lVal;
            v32 = (signed int)(a2->decVal.Lo32 - lVal) < 0;
            if ( (signed int)a2->decVal.Lo32 >= lVal )
              goto LABEL_92;
            v14 = -1;
            goto LABEL_13;
          case 4:
            fltVal = this->fltVal;
            v48 = a2->fltVal;
            if ( fltVal <= v48 )
              v14 = (v48 <= fltVal) - 1;
            else
              v14 = -1;
            goto LABEL_13;
          case 5:
          case 7:
            dblVal = this->dblVal;
            v50 = a2->dblVal;
            if ( dblVal <= v50 )
              v14 = (v50 <= dblVal) - 1;
            else
              v14 = -1;
            goto LABEL_13;
          case 6:
          case 20:
            QuadPart = this->hVal.QuadPart;
            v33 = __OFSUB__(a2->decVal.Lo64, QuadPart);
            v31 = a2->decVal.Lo64 == QuadPart;
            v32 = (signed __int64)(a2->decVal.Lo64 - QuadPart) < 0;
            if ( (signed __int64)a2->decVal.Lo64 >= QuadPart )
              goto LABEL_92;
            v14 = -1;
            goto LABEL_13;
          case 8:
          case 31:
            v14 = wcsicmp(a2->bstrVal, this->bstrVal);
            goto LABEL_13;
          case 9:
          case 13:
            v14 = -(this->decVal.Lo64 != a2->decVal.Lo64);
            goto LABEL_13;
          case 11:
            v14 = -(this->iVal != a2->iVal);
            goto LABEL_13;
          case 16:
            cVal = this->cVal;
            v33 = __OFSUB__(a2->cVal, cVal);
            v31 = a2->cVal == (unsigned __int8)cVal;
            v32 = (char)(a2->cVal - cVal) < 0;
            if ( a2->cVal >= cVal )
LABEL_92:
              v14 = (v32 ^ v33 | v31) - 1;
            else
              v14 = -1;
            goto LABEL_13;
          case 17:
            bVal = this->bVal;
            v35 = a2->bVal;
            v27 = bVal < v35;
            if ( bVal <= v35 )
              goto LABEL_90;
            v14 = -1;
            goto LABEL_13;
          case 18:
            uiVal = this->uiVal;
            v37 = a2->uiVal;
            v27 = uiVal < v37;
            if ( uiVal <= v37 )
              goto LABEL_90;
            v14 = -1;
            goto LABEL_13;
          case 19:
          case 23:
            Lo32 = this->decVal.Lo32;
            v45 = a2->decVal.Lo32;
            v27 = Lo32 < v45;
            if ( Lo32 <= v45 )
              goto LABEL_90;
            v14 = -1;
            goto LABEL_13;
          case 21:
            Lo64 = this->decVal.Lo64;
            v26 = a2->decVal.Lo64;
            v27 = Lo64 < v26;
            if ( Lo64 <= v26 )
              goto LABEL_90;
            v14 = -1;
            goto LABEL_13;
          case 30:
            v14 = o__stricmp_0(a2->decVal.Lo64, this->decVal.Lo64);
            goto LABEL_13;
          case 64:
            v14 = memcmp_0(&a2->intVal, &this->intVal, 8u);
            goto LABEL_13;
          case 72:
            v27 = memcmp_0(a2->puuid, this->puuid, 0x10u) != 0;
LABEL_90:
            v14 = -v27;
            goto LABEL_13;
          default:
            v15 = -1072875800;
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
            if ( CallStackTracing::s_wpInstance->m_fEnabled )
            {
              v28 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( v28->m_result != -1072875800 )
                CallStackContext::TraceFailure(v28, "CMFPropVariant::Compare", 1483, -1072875800);
            }
            if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                89,
                WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
                this,
                -1072875800);
            if ( !CallStackTracing::s_wpInstance )
            {
              CallStackTracing::s_wpInstance = &stru_1801FC290;
              if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
                CallStackTracing::s_wpInstance = &stru_1801F8A30;
            }
            if ( CallStackTracing::s_wpInstance->m_fEnabled )
            {
              v29 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
              if ( v29->m_result != -1072875800 )
                CallStackContext::TraceFailure(v29, "CMFPropVariant::Compare", 1486, -1072875800);
            }
            if ( !g_wppLevels.CTRLGUID_MF_PLATFORM )
              goto LABEL_14;
            v24 = 90;
            break;
        }
LABEL_27:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, this, v15);
        goto LABEL_14;
      }
      v15 = -1072875801;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( !stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
      }
      if ( CallStackTracing::s_wpInstance->m_fEnabled )
      {
        v39 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( v39->m_result != -1072875801 )
          CallStackContext::TraceFailure(v39, "CMFPropVariant::Compare", 1444, -1072875801);
      }
      if ( g_wppLevels.CTRLGUID_MF_PLATFORM )
      {
        v24 = 88;
        goto LABEL_27;
      }
    }
  }
LABEL_14:
  v16 = CallStackTracing::s_wpInstance;
  if ( CallStackTracing::s_wpInstance->m_fEnabled )
  {
    v17 = &CallStackTracing::s_wpInstance->m_context;
    v18 = GetLastError();
    v19 = (CallStackContext *)TlsGetValue(v16->m_dwTLSIndex);
    if ( v19 )
      goto LABEL_16;
    if ( !GetLastError() )
    {
      v41 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::s_wpInstance = &stru_1801FC290;
        if ( stru_1801FC290.CheckVersionMatch(&stru_1801FC290, 2032u) )
        {
          v41 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v41 = &stru_1801F8A30;
          CallStackTracing::s_wpInstance = &stru_1801F8A30;
        }
      }
      v19 = (CallStackContext *)v41->AllocateNewContext(v41);
      if ( v19 )
LABEL_16:
        v17 = v19;
    }
    SetLastError(v18);
    v20 = v17->m_dwDepth;
    if ( v20 )
    {
      v21 = v20 - 1;
      v17->m_dwDepth = v21;
      if ( !v21 )
      {
        v17->m_dwDepth = 0;
        *(_QWORD *)&v17->m_instanceId = 0;
        v17->m_result = 0;
        v17->m_sessionId = GUID_00000000_0000_0000_0000_000000000000;
        v17->m_dwErrorsInContext = 0;
        v17->m_dwThreadID = GetCurrentThreadId();
      }
    }
  }
  return v15;
}

```

## disassembly

```asm
0x180029230  mov     [rsp+arg_18], rbx
0x180029235  push    rbp
0x180029236  push    rsi
0x180029237  push    rdi
0x180029238  push    r12
0x18002923a  push    r13
0x18002923c  push    r14
0x18002923e  push    r15
0x180029240  sub     rsp, 30h
0x180029244  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18002924c  lea     rdi, stru_1801F8A30
0x180029253  mov     rsi, r8
0x180029256  lea     r13, stru_1801FC290
0x18002925d  mov     rbp, rdx
0x180029260  mov     r14, rcx
0x180029263  jz      loc_180029431
0x180029269  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029270  lea     r12, aCmfpropvariant_2; "CMFPropVariant::Compare"
0x180029277  cmp     byte ptr [rbx+8], 0
0x18002927b  jz      short loc_1800292D5
0x18002927d  lea     rdi, [rbx+0D0h]
0x180029284  call    cs:__imp_GetLastError
0x18002928a  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002928d  mov     r15d, eax
0x180029290  call    cs:__imp_TlsGetValue
0x180029296  test    rax, rax
0x180029299  jz      loc_1800296B0
0x18002929f  mov     rdi, rax
0x1800292a2  mov     ecx, r15d; dwErrCode
0x1800292a5  call    cs:__imp_SetLastError
0x1800292ab  mov     eax, [rdi+7C4h]
0x1800292b1  cmp     eax, [rdi+7C8h]
0x1800292b7  jnb     short loc_1800292C8
0x1800292b9  add     rax, rax
0x1800292bc  mov     [rdi+rax*8], r12
0x1800292c0  mov     dword ptr [rdi+rax*8+8], 586h
0x1800292c8  inc     dword ptr [rdi+7C4h]
0x1800292ce  lea     rdi, stru_1801F8A30
0x1800292d5  xor     r15d, r15d
0x1800292d8  cmp     r14, rbp
0x1800292db  jz      loc_1800293B9
0x1800292e1  mov     [rsi], r15d
0x1800292e4  mov     eax, 1000h
0x1800292e9  movzx   edx, word ptr [r14]
0x1800292ed  movzx   ecx, dx
0x1800292f0  and     cx, ax
0x1800292f3  cmp     r15w, cx
0x1800292f7  jnz     loc_1800295B7
0x1800292fd  cmp     [rbp+0], dx
0x180029301  jnz     loc_180029611
0x180029307  and     edx, 0FFFh
0x18002930d  jnz     loc_180029464
0x180029313  mov     eax, r15d; jumptable 0000000180029487 case 1
0x180029316  mov     ebp, r15d
0x180029319  mov     [rsi], eax
0x18002931b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029322  cmp     [rbx+8], r15b
0x180029326  jz      short loc_18002939F
0x180029328  lea     rdi, [rbx+0D0h]
0x18002932f  call    cs:__imp_GetLastError
0x180029335  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180029338  mov     esi, eax
0x18002933a  call    cs:__imp_TlsGetValue
0x180029340  test    rax, rax
0x180029343  jz      loc_1800296E7
0x180029349  mov     rdi, rax
0x18002934c  mov     ecx, esi; dwErrCode
0x18002934e  call    cs:__imp_SetLastError
0x180029354  mov     eax, [rdi+7C4h]
0x18002935a  test    eax, eax
0x18002935c  jz      short loc_18002939F
0x18002935e  sub     eax, 1
0x180029361  mov     [rdi+7C4h], eax
0x180029367  jnz     short loc_18002939F
0x180029369  mov     [rdi+7C4h], r15d
0x180029370  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180029377  mov     [rdi+7E0h], r15
0x18002937e  mov     [rdi+7CCh], r15d
0x180029385  movups  xmmword ptr [rdi+7D0h], xmm0
0x18002938c  mov     [rdi+7E8h], r15d
0x180029393  call    cs:__imp_GetCurrentThreadId
0x180029399  mov     [rdi+7C0h], eax
0x18002939f  mov     rbx, [rsp+68h+arg_18]
0x1800293a7  mov     eax, ebp
0x1800293a9  add     rsp, 30h
0x1800293ad  pop     r15
0x1800293af  pop     r14
0x1800293b1  pop     r13
0x1800293b3  pop     r12
0x1800293b5  pop     rdi
0x1800293b6  pop     rsi
0x1800293b7  pop     rbp
0x1800293b8  retn
0x1800293b9  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x1800293c0  mov     ebp, 80004003h
0x1800293c5  jz      loc_18002967D
0x1800293cb  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800293d2  cmp     [rbx+8], r15b
0x1800293d6  jz      short loc_1800293FC
0x1800293d8  mov     rcx, rbx; this
0x1800293db  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800293e0  cmp     [rax+7CCh], ebp
0x1800293e6  jz      short loc_1800293FC
0x1800293e8  mov     r9d, ebp; int
0x1800293eb  mov     r8d, 58Fh; int
0x1800293f1  mov     rdx, r12; char *
0x1800293f4  mov     rcx, rax; this
0x1800293f7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800293fc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029403  jb      loc_18002931B
0x180029409  mov     edx, 56h ; 'V'
0x18002940e  mov     rcx, cs:WPP_GLOBAL_Control
0x180029415  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x18002941c  mov     r9, r14
0x18002941f  mov     [rsp+68h+var_48], ebp
0x180029423  mov     rcx, [rcx+10h]
0x180029427  call    WPP_SF_qD
0x18002942c  jmp     loc_18002931B
0x180029431  mov     rax, cs:stru_1801FC290.__vftable
0x180029438  mov     edx, 7F0h
0x18002943d  mov     rcx, r13
0x180029440  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180029447  mov     rax, [rax+8]
0x18002944b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029450  test    eax, eax
0x180029452  jnz     loc_180029269
0x180029458  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002945f  jmp     loc_180029269
0x180029464  dec     edx; switch 72 cases
0x180029466  cmp     edx, 47h
0x180029469  ja      short def_180029487; jumptable 0000000180029487 default case, cases 12,14,15,24-29,32-63,65-71
0x18002946b  movsxd  rax, edx
0x18002946e  lea     rdx, __ImageBase
0x180029475  movzx   eax, ds:(byte_1800299D8 - 180000000h)[rdx+rax]
0x18002947d  mov     ecx, ds:(jpt_180029487 - 180000000h)[rdx+rax*4]
0x180029484  add     rcx, rdx
0x180029487  jmp     rcx; switch jump
0x180029489  mov     rax, [r14+8]; jumptable 0000000180029487 case 21
0x18002948d  mov     rcx, [rbp+8]
0x180029491  cmp     rax, rcx
0x180029494  jbe     loc_180029895
0x18002949a  mov     eax, 0FFFFFFFFh
0x18002949f  jmp     loc_180029316
0x1800294a4  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; jumptable 0000000180029487 default case, cases 12,14,15,24-29,32-63,65-71
0x1800294ab  mov     ebp, 0C00D36E8h
0x1800294b0  jz      loc_18002971E
0x1800294b6  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800294bd  cmp     [rbx+8], r15b
0x1800294c1  jz      short loc_1800294E7
0x1800294c3  mov     rcx, rbx; this
0x1800294c6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800294cb  cmp     [rax+7CCh], ebp
0x1800294d1  jz      short loc_1800294E7
0x1800294d3  mov     r9d, ebp; int
0x1800294d6  mov     r8d, 5CBh; int
0x1800294dc  mov     rdx, r12; char *
0x1800294df  mov     rcx, rax; this
0x1800294e2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800294e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800294ee  jb      short loc_180029513
0x1800294f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800294f7  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x1800294fe  mov     edx, 59h ; 'Y'
0x180029503  mov     [rsp+68h+var_48], ebp
0x180029507  mov     r9, r14
0x18002950a  mov     rcx, [rcx+10h]
0x18002950e  call    WPP_SF_qD
0x180029513  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x18002951a  jz      loc_180029751
0x180029520  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029527  cmp     [rbx+8], r15b
0x18002952b  jz      short loc_180029551
0x18002952d  mov     rcx, rbx; this
0x180029530  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180029535  cmp     [rax+7CCh], ebp
0x18002953b  jz      short loc_180029551
0x18002953d  mov     r9d, ebp; int
0x180029540  mov     r8d, 5CEh; int
0x180029546  mov     rdx, r12; char *
0x180029549  mov     rcx, rax; this
0x18002954c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180029551  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029558  jb      loc_18002931B
0x18002955e  mov     edx, 5Ah ; 'Z'
0x180029563  jmp     loc_18002940E
0x180029568  movzx   ecx, byte ptr [r14+8]; jumptable 0000000180029487 case 16
0x18002956d  cmp     [rbp+8], cl
0x180029570  jge     loc_1800298AF
0x180029576  mov     eax, 0FFFFFFFFh
0x18002957b  jmp     loc_180029316
0x180029580  movzx   eax, byte ptr [r14+8]; jumptable 0000000180029487 case 17
0x180029585  movzx   ecx, byte ptr [rbp+8]
0x180029589  cmp     al, cl
0x18002958b  jbe     loc_180029895
0x180029591  mov     eax, 0FFFFFFFFh
0x180029596  jmp     loc_180029316
0x18002959b  movzx   eax, word ptr [r14+8]; jumptable 0000000180029487 case 18
0x1800295a0  movzx   ecx, word ptr [rbp+8]
0x1800295a4  cmp     ax, cx
0x1800295a7  jbe     loc_180029895
0x1800295ad  mov     eax, 0FFFFFFFFh
0x1800295b2  jmp     loc_180029316
0x1800295b7  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x1800295be  mov     ebp, 0C00D36EBh
0x1800295c3  jz      loc_180029784
0x1800295c9  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800295d0  cmp     [rbx+8], r15b
0x1800295d4  jz      short loc_1800295FA
0x1800295d6  mov     rcx, rbx; this
0x1800295d9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800295de  cmp     [rax+7CCh], ebp
0x1800295e4  jz      short loc_1800295FA
0x1800295e6  mov     r9d, ebp; int
0x1800295e9  mov     r8d, 59Ch; int
0x1800295ef  mov     rdx, r12; char *
0x1800295f2  mov     rcx, rax; this
0x1800295f5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800295fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029601  jb      loc_18002931B
0x180029607  mov     edx, 57h ; 'W'
0x18002960c  jmp     loc_18002940E
0x180029611  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r15; CallStackTracing * CallStackTracing::s_wpInstance
0x180029618  mov     ebp, 0C00D36E7h
0x18002961d  jz      loc_1800297B7
0x180029623  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002962a  cmp     [rbx+8], r15b
0x18002962e  jz      short loc_180029654
0x180029630  mov     rcx, rbx; this
0x180029633  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180029638  cmp     [rax+7CCh], ebp
0x18002963e  jz      short loc_180029654
0x180029640  mov     r9d, ebp; int
0x180029643  mov     r8d, 5A4h; int
0x180029649  mov     rdx, r12; char *
0x18002964c  mov     rcx, rax; this
0x18002964f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180029654  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002965b  jb      loc_18002931B
0x180029661  mov     edx, 58h ; 'X'
0x180029666  jmp     loc_18002940E
0x18002966b  mov     rdx, [r14+8]; jumptable 0000000180029487 case 30
0x18002966f  mov     rcx, [rbp+8]
0x180029673  call    _o__stricmp_0
0x180029678  jmp     loc_180029316
0x18002967d  mov     rax, cs:stru_1801FC290.__vftable
0x180029684  mov     edx, 7F0h
0x180029689  mov     rcx, r13
0x18002968c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180029693  mov     rax, [rax+8]
0x180029697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002969c  test    eax, eax
0x18002969e  jnz     loc_1800293CB
0x1800296a4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800296ab  jmp     loc_1800293CB
0x1800296b0  call    cs:__imp_GetLastError
0x1800296b6  test    eax, eax
0x1800296b8  jnz     loc_1800292A2
0x1800296be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800296c5  test    rcx, rcx
0x1800296c8  jz      loc_1800297EA
0x1800296ce  mov     rax, [rcx]
0x1800296d1  mov     rax, [rax]
0x1800296d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296d9  test    rax, rax
0x1800296dc  jnz     loc_18002929F
0x1800296e2  jmp     loc_1800292A2
0x1800296e7  call    cs:__imp_GetLastError
0x1800296ed  test    eax, eax
0x1800296ef  jnz     loc_18002934C
0x1800296f5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800296fc  test    rcx, rcx
0x1800296ff  jz      loc_180029820
0x180029705  mov     rax, [rcx]
0x180029708  mov     rax, [rax]
0x18002970b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029710  test    rax, rax
0x180029713  jnz     loc_180029349
0x180029719  jmp     loc_18002934C
0x18002971e  mov     rax, cs:stru_1801FC290.__vftable
0x180029725  mov     edx, 7F0h
0x18002972a  mov     rcx, r13
0x18002972d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180029734  mov     rax, [rax+8]
0x180029738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002973d  test    eax, eax
0x18002973f  jnz     loc_1800294B6
0x180029745  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002974c  jmp     loc_1800294B6
0x180029751  mov     rax, cs:stru_1801FC290.__vftable
0x180029758  mov     edx, 7F0h
0x18002975d  mov     rcx, r13
0x180029760  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180029767  mov     rax, [rax+8]
0x18002976b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029770  test    eax, eax
0x180029772  jnz     loc_180029520
0x180029778  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x18002977f  jmp     loc_180029520
0x180029784  mov     rax, cs:stru_1801FC290.__vftable
0x18002978b  mov     edx, 7F0h
  ... truncated ...
```
