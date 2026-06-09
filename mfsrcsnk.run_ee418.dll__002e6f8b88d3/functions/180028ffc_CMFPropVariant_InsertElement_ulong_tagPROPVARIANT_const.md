# CMFPropVariant::InsertElement(ulong,tagPROPVARIANT const *)

- ea: `0x180028ffc`
- end: `0x1800297b7`
- name: `?InsertElement@CMFPropVariant@@QEAAJKPEBUtagPROPVARIANT@@@Z`
- size: `1979`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800297c0`

## callees

- `0x18000e0c0`
- `0x180010190`
- `0x18001105c`
- `0x18001303c`
- `0x1800130d0`
- `0x1800135b0`
- `0x180018b90`
- `0x180025548`
- `0x1800275f0`
- `0x180028ffc`
- `0x180071a44`
- `0x180073b14`
- `0x1801099f0`
- `0x18010a450`
- `0x1801723e0`
- `0x180173010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029289`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029407`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002943c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800294b4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029289`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029407`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002943c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029478`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800294b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029136`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029136`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002917c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029219`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002917c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029219`

## pseudocode

```c
__int64 __fastcall CMFPropVariant::InsertElement(
        struct tagPROPVARIANT *this,
        unsigned int a2,
        struct tagPROPVARIANT *a3)
{
  VARTYPE vt; // cx
  unsigned int ulVal; // r14d
  VARTYPE v7; // cx
  __int16 v8; // dx
  int VarTypeSize; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  wchar_t *v13; // rcx
  int ElementDataPtr; // ebx
  struct CallStackContext *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned int v18; // r12d
  unsigned int v19; // ebx
  char *v20; // rax
  char *v21; // r15
  const void **p_pData; // rbx
  PROPVARIANT *v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  const void *p_pvarDest; // r8
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  CallStackTracing *v39; // rcx
  __int64 v40; // rdx
  CallStackTracing *v41; // rcx
  CallStackTracing *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  wchar_t *v46; // rcx
  CallStackTracing *v47; // rax
  CallStackTracing *v48; // rax
  wchar_t *v49; // rcx
  CallStackTracing *v50; // rax
  wchar_t *v51; // rcx
  CallStackTracing *v52; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v54; // rax
  struct CallStackContext *v55; // rax
  struct CallStackContext *v56; // rax
  struct CallStackContext *v57; // rax
  struct CallStackContext *v58; // rax
  struct CallStackContext *v59; // rax
  struct CallStackContext *v60; // rax
  _BYTE v61[4]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v62; // [rsp+34h] [rbp-3Ch] BYREF
  void *v63; // [rsp+38h] [rbp-38h] BYREF
  PROPVARIANT *pvarSrc; // [rsp+40h] [rbp-30h]
  PROPVARIANT pvarDest; // [rsp+48h] [rbp-28h] BYREF

  pvarSrc = a3;
  v62 = 0;
  vt = this->vt;
  v63 = 0;
  memset(&pvarDest, 0, sizeof(pvarDest));
  if ( (vt & 0x1000) != 0 )
  {
    if ( this->vt )
    {
      ulVal = this->ulVal;
      goto LABEL_4;
    }
  }
  else if ( this->vt )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMFPropVariant::InsertElement", 1978);
    v37 = (wchar_t *)CallStackTracing::s_wpInstance;
    ElementDataPtr = -1072875796;
    if ( !CallStackTracing::s_wpInstance )
    {
      v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35, v36);
      CallStackTracing::s_wpInstance = v38;
      if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
      {
        v37 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v37 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875796 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::InsertElement", 1978, -1072875796);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v40 = 129;
    goto LABEL_41;
  }
  ulVal = 0;
LABEL_4:
  if ( this == a3 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMFPropVariant::InsertElement", 1991);
    v46 = (wchar_t *)CallStackTracing::s_wpInstance;
    ElementDataPtr = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v44, v45);
      CallStackTracing::s_wpInstance = v47;
      if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
      {
        v46 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v46 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v46 + 8) )
    {
      v54 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
      if ( *((_DWORD *)v54 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v54, "CMFPropVariant::InsertElement", 1991, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v40 = 130;
    goto LABEL_41;
  }
  v7 = a3->vt;
  if ( !a3->vt || this->vt && (v8 = this->vt & 0xFFF, v8 != 12) && (v7 & 0xFFF) != v8 || ulVal < a2 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v61, "CMFPropVariant::InsertElement", 1998);
    v39 = CallStackTracing::s_wpInstance;
    ElementDataPtr = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v39 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v39 + 8) )
    {
      v60 = CallStackTracing::GetThreadRelativeContext(v39);
      if ( *((_DWORD *)v60 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v60, "CMFPropVariant::InsertElement", 1998, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v40 = 131;
    goto LABEL_41;
  }
  if ( !this->vt )
  {
    this->lVal = 0;
    this->bstrblobVal.pData = 0;
    this->vt = v7 & 0xFFF | 0x1000;
  }
  VarTypeSize = CMFPropVariantConvert::GetVarTypeSize((const struct CMFPropVariant *)this, &v62);
  v13 = (wchar_t *)CallStackTracing::s_wpInstance;
  ElementDataPtr = VarTypeSize;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v13 + 8) )
  {
    v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
    v16 = *((unsigned int *)v15 + 497);
    if ( (unsigned int)v16 < *((_DWORD *)v15 + 498) )
    {
      v17 = 2 * v16;
      *((_QWORD *)v15 + v17) = "CMFPropVariant::InsertElement";
      *((_DWORD *)v15 + 2 * v17 + 2) = 2015;
    }
    ++*((_DWORD *)v15 + 497);
    v13 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( ElementDataPtr < 0 )
  {
    if ( !v13 )
    {
      v48 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10, v11, v12);
      CallStackTracing::s_wpInstance = v48;
      if ( v48 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
      {
        v13 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v13 + 8) )
    {
      v55 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v55 + 499) != ElementDataPtr )
        CallStackContext::TraceFailure(v55, "CMFPropVariant::InsertElement", 2015, ElementDataPtr);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v40 = 132;
    goto LABEL_41;
  }
  v18 = v62;
  v19 = v62 * (ulVal + 1);
  v20 = (char *)CoTaskMemAlloc(v19);
  v21 = v20;
  if ( !v20 )
  {
    v42 = CallStackTracing::s_wpInstance;
    ElementDataPtr = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v42 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v42 + 8) )
    {
      v56 = CallStackTracing::GetThreadRelativeContext(v42);
      if ( *((_DWORD *)v56 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v56, "CMFPropVariant::InsertElement", 2021, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v40 = 133;
    goto LABEL_41;
  }
  memset_0(v20, 0, v19);
  p_pData = (const void **)&this->bstrblobVal.pData;
  if ( a2 )
    memcpy_0(v21, *p_pData, v18 * a2);
  if ( ulVal > a2 )
  {
    p_pData = (const void **)&this->bstrblobVal.pData;
    memcpy_0(&v21[v18 * (a2 + 1)], &this->bstrblobVal.pData[v18 * a2], v18 * (ulVal - a2));
  }
  CoTaskMemFree((LPVOID)*p_pData);
  v23 = pvarSrc;
  ++this->lVal;
  *p_pData = v21;
  ElementDataPtr = CMFPropVariant::Copy(&pvarDest, v23, v24, v25);
  if ( ElementDataPtr < 0 )
  {
    v41 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v41 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v41 + 8) )
    {
      v57 = CallStackTracing::GetThreadRelativeContext(v41);
      if ( *((_DWORD *)v57 + 499) != ElementDataPtr )
        CallStackContext::TraceFailure(v57, "CMFPropVariant::InsertElement", 2068, ElementDataPtr);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v40 = 134;
    goto LABEL_41;
  }
  if ( (this->vt & 0xFFF) != 0xC )
  {
    ElementDataPtr = CMFPropVariant::GetElementDataPtr((CMFPropVariant *)&pvarDest, 0, &v63);
    if ( ElementDataPtr >= 0 )
    {
      p_pvarDest = v63;
      goto LABEL_28;
    }
    v49 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26, v27, v28);
      CallStackTracing::s_wpInstance = v50;
      if ( v50 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
      {
        v49 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v49 = &qword_1801B07E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
      }
    }
    if ( *((_BYTE *)v49 + 8) )
    {
      v58 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v49);
      if ( *((_DWORD *)v58 + 499) != ElementDataPtr )
        CallStackContext::TraceFailure(v58, "CMFPropVariant::InsertElement", 2086, ElementDataPtr);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v40 = 135;
LABEL_41:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v40,
      &WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
      this,
      ElementDataPtr);
    goto LABEL_31;
  }
  p_pvarDest = &pvarDest;
LABEL_28:
  ElementDataPtr = CMFPropVariant::SetElementData((CMFPropVariant *)this, a2, p_pvarDest);
  if ( ElementDataPtr >= 0 )
  {
    if ( pvarDest.vt != 72 || (this->vt & 0xFFF) == 0xC )
      memset(&pvarDest, 0, sizeof(pvarDest));
    goto LABEL_31;
  }
  v51 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
    CallStackTracing::s_wpInstance = v52;
    if ( v52 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
    {
      v51 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v51 = &qword_1801B07E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
    }
  }
  if ( *((_BYTE *)v51 + 8) )
  {
    v59 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v51);
    if ( *((_DWORD *)v59 + 499) != ElementDataPtr )
      CallStackContext::TraceFailure(v59, "CMFPropVariant::InsertElement", 2093, ElementDataPtr);
  }
  if ( g_wppLevels )
  {
    v40 = 136;
    goto LABEL_41;
  }
LABEL_31:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v61);
  CoTaskMemFree(0);
  CMFPropVariant::Clear((CMFPropVariant *)&pvarDest);
  return (unsigned int)ElementDataPtr;
}

```

## disassembly

```asm
0x180028ffc  mov     [rsp-38h+arg_18], rbx
0x180029001  push    rbp
0x180029002  push    rsi
0x180029003  push    rdi
0x180029004  push    r12
0x180029006  push    r13
0x180029008  push    r14
0x18002900a  push    r15
0x18002900c  mov     rbp, rsp
0x18002900f  sub     rsp, 70h
0x180029013  mov     rax, cs:__security_cookie
0x18002901a  xor     rax, rsp
0x18002901d  mov     [rbp+var_10], rax
0x180029021  xor     r15d, r15d
0x180029024  mov     [rbp+pvarSrc], r8
0x180029028  mov     rdi, rcx
0x18002902b  mov     [rbp+var_3C], r15d
0x18002902f  movzx   ecx, word ptr [rcx]
0x180029032  xor     eax, eax
0x180029034  mov     r10d, 1000h
0x18002903a  mov     [rbp+var_38], r15
0x18002903e  and     cx, r10w
0x180029042  mov     qword ptr [rbp+pvarDest+10h], rax
0x180029046  xorps   xmm0, xmm0
0x180029049  mov     r13d, edx
0x18002904c  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180029050  cmp     r15w, cx
0x180029054  jz      loc_18002924E
0x18002905a  cmp     r15w, [rdi]
0x18002905e  jz      loc_1800293A0
0x180029064  mov     r14d, [rdi+8]
0x180029068  cmp     rdi, r8
0x18002906b  jz      loc_1800293D6
0x180029071  movzx   ecx, word ptr [r8]
0x180029075  cmp     r15w, cx
0x180029079  jz      loc_1800292C6
0x18002907f  mov     r8d, 0FFFh
0x180029085  mov     r9d, 0Ch
0x18002908b  cmp     r15w, [rdi]
0x18002908f  jz      short loc_1800290AE
0x180029091  movzx   edx, word ptr [rdi]
0x180029094  and     dx, r8w
0x180029098  cmp     r9w, dx
0x18002909c  jz      short loc_1800290AE
0x18002909e  movzx   eax, cx
0x1800290a1  and     ax, r8w
0x1800290a5  cmp     ax, dx
0x1800290a8  jnz     loc_1800292C6
0x1800290ae  cmp     r14d, r13d
0x1800290b1  jb      loc_1800292C6
0x1800290b7  cmp     r15w, [rdi]
0x1800290bb  jz      loc_1800296A6
0x1800290c1  lea     rdx, [rbp+var_3C]; unsigned int *
0x1800290c5  mov     rcx, rdi; struct CMFPropVariant *
0x1800290c8  call    ?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z; CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)
0x1800290cd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800290d4  mov     ebx, eax
0x1800290d6  test    rcx, rcx
0x1800290d9  jz      loc_1800292B5
0x1800290df  lea     rsi, aCmfpropvariant_13; "CMFPropVariant::InsertElement"
0x1800290e6  mov     r12d, 7DFh
0x1800290ec  cmp     [rcx+8], r15b
0x1800290f0  jz      short loc_18002911E
0x1800290f2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800290f7  mov     ecx, [rax+7C4h]
0x1800290fd  cmp     ecx, [rax+7C8h]
0x180029103  jnb     short loc_180029111
0x180029105  add     rcx, rcx
0x180029108  mov     [rax+rcx*8], rsi
0x18002910c  mov     [rax+rcx*8+8], r12d
0x180029111  inc     dword ptr [rax+7C4h]
0x180029117  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002911e  test    ebx, ebx
0x180029120  js      loc_180029433
0x180029126  mov     r12d, [rbp+var_3C]
0x18002912a  lea     eax, [r14+1]
0x18002912e  imul    eax, r12d
0x180029132  mov     ecx, eax; cb
0x180029134  mov     ebx, eax
0x180029136  call    cs:__imp_CoTaskMemAlloc
0x18002913c  mov     r15, rax
0x18002913f  test    rax, rax
0x180029142  jz      loc_18002936E
0x180029148  mov     r8d, ebx; Size
0x18002914b  xor     edx, edx; Val
0x18002914d  mov     rcx, rax; void *
0x180029150  call    memset_0
0x180029155  lea     rbx, [rdi+10h]
0x180029159  test    r13d, r13d
0x18002915c  jz      short loc_180029170
0x18002915e  mov     rdx, [rbx]; Src
0x180029161  mov     r8d, r13d
0x180029164  imul    r8d, r12d; Size
0x180029168  mov     rcx, r15; void *
0x18002916b  call    memcpy_0
0x180029170  cmp     r14d, r13d
0x180029173  ja      loc_1800296FF
0x180029179  mov     rcx, [rbx]; pv
0x18002917c  call    cs:__imp_CoTaskMemFree
0x180029182  mov     rdx, [rbp+pvarSrc]; pvarSrc
0x180029186  lea     rcx, [rbp+pvarDest]; pvarDest
0x18002918a  inc     dword ptr [rdi+8]
0x18002918d  xor     r14d, r14d
0x180029190  mov     [rbx], r15
0x180029193  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180029198  mov     ebx, eax
0x18002919a  test    eax, eax
0x18002919c  js      loc_180029336
0x1800291a2  movzx   eax, word ptr [rdi]
0x1800291a5  lea     r12d, [r14+0Ch]
0x1800291a9  mov     r15d, 0FFFh
0x1800291af  and     ax, r15w
0x1800291b3  cmp     r12w, ax
0x1800291b7  jz      loc_18002972C
0x1800291bd  lea     r8, [rbp+var_38]; void **
0x1800291c1  xor     edx, edx; unsigned int
0x1800291c3  lea     rcx, [rbp+pvarDest]; this
0x1800291c7  call    ?GetElementDataPtr@CMFPropVariant@@IEBAJKPEAPEAX@Z; CMFPropVariant::GetElementDataPtr(ulong,void * *)
0x1800291cc  mov     ebx, eax
0x1800291ce  test    eax, eax
0x1800291d0  js      loc_180029468
0x1800291d6  mov     r8, [rbp+var_38]; void *
0x1800291da  mov     edx, r13d; unsigned int
0x1800291dd  mov     rcx, rdi; this
0x1800291e0  call    ?SetElementData@CMFPropVariant@@IEAAJKPEBX@Z; CMFPropVariant::SetElementData(ulong,void const *)
0x1800291e5  mov     ebx, eax
0x1800291e7  test    eax, eax
0x1800291e9  js      loc_1800294A4
0x1800291ef  movzx   eax, word ptr [rdi]
0x1800291f2  and     ax, r15w
0x1800291f6  cmp     word ptr [rbp+pvarDest], 48h ; 'H'
0x1800291fb  jz      loc_1800293A8
0x180029201  xorps   xmm0, xmm0
0x180029204  xor     eax, eax
0x180029206  movups  xmmword ptr [rbp+pvarDest], xmm0
0x18002920a  mov     qword ptr [rbp+pvarDest+10h], rax
0x18002920e  lea     rcx, [rbp+var_40]; this
0x180029212  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180029217  xor     ecx, ecx; pv
0x180029219  call    cs:__imp_CoTaskMemFree
0x18002921f  lea     rcx, [rbp+pvarDest]; this
0x180029223  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180029228  mov     eax, ebx
0x18002922a  mov     rcx, [rbp+var_10]
0x18002922e  xor     rcx, rsp; StackCookie
0x180029231  call    __security_check_cookie
0x180029236  mov     rbx, [rsp+70h+arg_18]
0x18002923e  add     rsp, 70h
0x180029242  pop     r15
0x180029244  pop     r14
0x180029246  pop     r13
0x180029248  pop     r12
0x18002924a  pop     rdi
0x18002924b  pop     rsi
0x18002924c  pop     rbp
0x18002924d  retn
0x18002924e  cmp     r15w, [rdi]
0x180029252  jz      loc_1800293A0
0x180029258  mov     r14d, 7BAh
0x18002925e  lea     rsi, aCmfpropvariant_13; "CMFPropVariant::InsertElement"
0x180029265  mov     r8d, r14d; int
0x180029268  lea     rcx, [rbp+var_40]; this
0x18002926c  mov     rdx, rsi; char *
0x18002926f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180029274  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002927b  mov     ebx, 0C00D36ECh
0x180029280  test    rcx, rcx
0x180029283  jnz     loc_180029644
0x180029289  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002928f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180029296  mov     rcx, rax
0x180029299  test    rax, rax
0x18002929c  jnz     loc_180029624
0x1800292a2  lea     rcx, qword_1801B07E0
0x1800292a9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800292b0  jmp     loc_180029644
0x1800292b5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800292ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800292c1  jmp     loc_1800290DF
0x1800292c6  mov     r14d, 7CEh
0x1800292cc  lea     rsi, aCmfpropvariant_13; "CMFPropVariant::InsertElement"
0x1800292d3  mov     r8d, r14d; int
0x1800292d6  lea     rcx, [rbp+var_40]; this
0x1800292da  mov     rdx, rsi; char *
0x1800292dd  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800292e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800292e9  mov     ebx, 80070057h
0x1800292ee  test    rcx, rcx
0x1800292f1  jz      loc_1800293C5
0x1800292f7  cmp     [rcx+8], r15b
0x1800292fb  jnz     loc_1800295FD
0x180029301  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029308  jb      loc_18002920E
0x18002930e  mov     edx, 83h
0x180029313  mov     rcx, cs:WPP_GLOBAL_Control
0x18002931a  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180029321  mov     r9, rdi
0x180029324  mov     [rsp+70h+var_50], ebx
0x180029328  mov     rcx, [rcx+10h]
0x18002932c  call    WPP_SF_qD
0x180029331  jmp     loc_18002920E
0x180029336  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18002933d  test    rcx, rcx
0x180029340  jz      short loc_180029360
0x180029342  cmp     [rcx+8], r14b
0x180029346  jnz     loc_18002957F
0x18002934c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029353  jb      loc_18002920E
0x180029359  mov     edx, 86h
0x18002935e  jmp     short loc_180029313
0x180029360  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180029365  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002936c  jmp     short loc_180029342
0x18002936e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180029375  mov     ebx, 8007000Eh
0x18002937a  test    rcx, rcx
0x18002937d  jz      short loc_1800293B7
0x18002937f  cmp     byte ptr [rcx+8], 0
0x180029383  jnz     loc_180029555
0x180029389  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029390  jb      loc_18002920E
0x180029396  mov     edx, 85h
0x18002939b  jmp     loc_180029313
0x1800293a0  mov     r14d, r15d
0x1800293a3  jmp     loc_180029068
0x1800293a8  cmp     r12w, ax
0x1800293ac  jz      loc_180029201
0x1800293b2  jmp     loc_18002920E
0x1800293b7  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800293bc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800293c3  jmp     short loc_18002937F
0x1800293c5  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800293ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800293d1  jmp     loc_1800292F7
0x1800293d6  mov     r14d, 7C7h
0x1800293dc  lea     rsi, aCmfpropvariant_13; "CMFPropVariant::InsertElement"
0x1800293e3  mov     r8d, r14d; int
0x1800293e6  lea     rcx, [rbp+var_40]; this
0x1800293ea  mov     rdx, rsi; char *
0x1800293ed  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800293f2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800293f9  mov     ebx, 80004003h
0x1800293fe  test    rcx, rcx
0x180029401  jnz     loc_180029685
0x180029407  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002940d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180029414  mov     rcx, rax
0x180029417  test    rax, rax
0x18002941a  jnz     loc_180029665
0x180029420  lea     rcx, qword_1801B07E0
0x180029427  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002942e  jmp     loc_180029685
0x180029433  test    rcx, rcx
0x180029436  jnz     loc_1800296DE
0x18002943c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180029442  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180029449  mov     rcx, rax
0x18002944c  test    rax, rax
0x18002944f  jnz     loc_1800296BE
0x180029455  lea     rcx, qword_1801B07E0
0x18002945c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180029463  jmp     loc_1800296DE
0x180029468  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002946f  test    rcx, rcx
0x180029472  jnz     loc_180029755
0x180029478  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002947e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180029485  mov     rcx, rax
0x180029488  test    rax, rax
0x18002948b  jnz     loc_180029735
0x180029491  lea     rcx, qword_1801B07E0
0x180029498  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002949f  jmp     loc_180029755
0x1800294a4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800294ab  test    rcx, rcx
0x1800294ae  jnz     loc_180029796
0x1800294b4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800294ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800294c1  mov     rcx, rax
0x1800294c4  test    rax, rax
0x1800294c7  jnz     loc_180029776
0x1800294cd  lea     rcx, qword_1801B07E0
0x1800294d4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800294db  jmp     loc_180029796
0x1800294e0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800294e5  cmp     [rax+7CCh], ebx
0x1800294eb  jz      loc_18002964E
0x1800294f1  mov     r9d, ebx; int
0x1800294f4  mov     r8d, r14d; int
0x1800294f7  mov     rdx, rsi; char *
0x1800294fa  mov     rcx, rax; this
0x1800294fd  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180029502  jmp     loc_18002964E
0x180029507  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002950c  cmp     [rax+7CCh], ebx
0x180029512  jz      loc_18002968F
0x180029518  mov     r9d, ebx; int
0x18002951b  mov     r8d, r14d; int
0x18002951e  mov     rdx, rsi; char *
0x180029521  mov     rcx, rax; this
  ... truncated ...
```
