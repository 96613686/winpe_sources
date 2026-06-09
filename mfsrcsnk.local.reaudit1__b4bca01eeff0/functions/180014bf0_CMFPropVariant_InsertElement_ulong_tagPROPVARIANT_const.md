# CMFPropVariant::InsertElement(ulong,tagPROPVARIANT const *)

- ea: `0x180014bf0`
- end: `0x1800153dc`
- name: `?InsertElement@CMFPropVariant@@QEAAJKPEBUtagPROPVARIANT@@@Z`
- size: `2028`
- prototype: `__int64 __fastcall(CMFPropVariant *__hidden this, unsigned int, const struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180015410`

## callees

- `0x180005cf4`
- `0x180010fc4`
- `0x180013110`
- `0x180014bf0`
- `0x180018d60`
- `0x180019264`
- `0x180019800`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180077708`
- `0x180079680`
- `0x180110ed0`
- `0x180111960`
- `0x18017b740`
- `0x18017c010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014e90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015014`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001504f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015091`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800150d3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014e90`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015014`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001504f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015091`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800150d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014d2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014d2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014d76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014e19`

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
  wchar_t *v11; // rcx
  int ElementDataPtr; // ebx
  struct CallStackContext *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  unsigned int v16; // r12d
  unsigned int v17; // ebx
  char *v18; // rax
  char *v19; // r15
  const void **p_pData; // rbx
  PROPVARIANT *v21; // rdx
  __int64 v22; // rdx
  const void *p_pvarDest; // r8
  __int64 v24; // rdx
  __int64 v26; // rdx
  wchar_t *v27; // rcx
  CallStackTracing *v28; // rax
  CallStackTracing *v29; // rcx
  __int64 v30; // rdx
  CallStackTracing *v31; // rcx
  CallStackTracing *v32; // rcx
  __int64 v33; // rdx
  wchar_t *v34; // rcx
  CallStackTracing *v35; // rax
  CallStackTracing *v36; // rax
  wchar_t *v37; // rcx
  CallStackTracing *v38; // rax
  wchar_t *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v42; // rax
  struct CallStackContext *v43; // rax
  struct CallStackContext *v44; // rax
  struct CallStackContext *v45; // rax
  struct CallStackContext *v46; // rax
  struct CallStackContext *v47; // rax
  struct CallStackContext *v48; // rax
  _BYTE v49[4]; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v50; // [rsp+34h] [rbp-3Ch] BYREF
  void *v51; // [rsp+38h] [rbp-38h] BYREF
  PROPVARIANT *pvarSrc; // [rsp+40h] [rbp-30h]
  PROPVARIANT pvarDest; // [rsp+48h] [rbp-28h] BYREF

  pvarSrc = a3;
  v50 = 0;
  vt = this->vt;
  v51 = 0;
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
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v49, "CMFPropVariant::InsertElement", 1978);
    v27 = (wchar_t *)CallStackTracing::s_wpInstance;
    ElementDataPtr = -1072875796;
    if ( !CallStackTracing::s_wpInstance )
    {
      v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v26);
      CallStackTracing::s_wpInstance = v28;
      if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
      {
        v27 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v27 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v27 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875796 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMFPropVariant::InsertElement", 1978, -1072875796);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v30 = 129;
    goto LABEL_41;
  }
  ulVal = 0;
LABEL_4:
  if ( this == a3 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v49, "CMFPropVariant::InsertElement", 1991);
    v34 = (wchar_t *)CallStackTracing::s_wpInstance;
    ElementDataPtr = -2147467261;
    if ( !CallStackTracing::s_wpInstance )
    {
      v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v33);
      CallStackTracing::s_wpInstance = v35;
      if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      {
        v34 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v34 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v34 + 8) )
    {
      v42 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v34);
      if ( *((_DWORD *)v42 + 499) != -2147467261 )
        CallStackContext::TraceFailure(v42, "CMFPropVariant::InsertElement", 1991, -2147467261);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v30 = 130;
    goto LABEL_41;
  }
  v7 = a3->vt;
  if ( !a3->vt || this->vt && (v8 = this->vt & 0xFFF, v8 != 12) && (v7 & 0xFFF) != v8 || ulVal < a2 )
  {
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v49, "CMFPropVariant::InsertElement", 1998);
    v29 = CallStackTracing::s_wpInstance;
    ElementDataPtr = -2147024809;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v29 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v29 + 8) )
    {
      v48 = CallStackTracing::GetThreadRelativeContext(v29);
      if ( *((_DWORD *)v48 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v48, "CMFPropVariant::InsertElement", 1998, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v30 = 131;
    goto LABEL_41;
  }
  if ( !this->vt )
  {
    this->lVal = 0;
    this->bstrblobVal.pData = 0;
    this->vt = v7 & 0xFFF | 0x1000;
  }
  VarTypeSize = CMFPropVariantConvert::GetVarTypeSize((const struct CMFPropVariant *)this, &v50);
  v11 = (wchar_t *)CallStackTracing::s_wpInstance;
  ElementDataPtr = VarTypeSize;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v13 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    v14 = *((unsigned int *)v13 + 497);
    if ( (unsigned int)v14 < *((_DWORD *)v13 + 498) )
    {
      v15 = 2 * v14;
      *((_QWORD *)v13 + v15) = "CMFPropVariant::InsertElement";
      *((_DWORD *)v13 + 2 * v15 + 2) = 2015;
    }
    ++*((_DWORD *)v13 + 497);
    v11 = (wchar_t *)CallStackTracing::s_wpInstance;
  }
  if ( ElementDataPtr < 0 )
  {
    if ( !v11 )
    {
      v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v10);
      CallStackTracing::s_wpInstance = v36;
      if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
      {
        v11 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v43 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v43 + 499) != ElementDataPtr )
        CallStackContext::TraceFailure(v43, "CMFPropVariant::InsertElement", 2015, ElementDataPtr);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v30 = 132;
    goto LABEL_41;
  }
  v16 = v50;
  v17 = v50 * (ulVal + 1);
  v18 = (char *)CoTaskMemAlloc(v17);
  v19 = v18;
  if ( !v18 )
  {
    v32 = CallStackTracing::s_wpInstance;
    ElementDataPtr = -2147024882;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v32 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v32 + 8) )
    {
      v44 = CallStackTracing::GetThreadRelativeContext(v32);
      if ( *((_DWORD *)v44 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v44, "CMFPropVariant::InsertElement", 2021, -2147024882);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v30 = 133;
    goto LABEL_41;
  }
  memset_0(v18, 0, v17);
  p_pData = (const void **)&this->bstrblobVal.pData;
  if ( a2 )
    memcpy_0(v19, *p_pData, v16 * a2);
  if ( ulVal > a2 )
  {
    p_pData = (const void **)&this->bstrblobVal.pData;
    memcpy_0(&v19[v16 * (a2 + 1)], &this->bstrblobVal.pData[v16 * a2], v16 * (ulVal - a2));
  }
  CoTaskMemFree((LPVOID)*p_pData);
  v21 = pvarSrc;
  ++this->lVal;
  *p_pData = v19;
  ElementDataPtr = CMFPropVariant::Copy(&pvarDest, v21);
  if ( ElementDataPtr < 0 )
  {
    v31 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v31 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v31 + 8) )
    {
      v45 = CallStackTracing::GetThreadRelativeContext(v31);
      if ( *((_DWORD *)v45 + 499) != ElementDataPtr )
        CallStackContext::TraceFailure(v45, "CMFPropVariant::InsertElement", 2068, ElementDataPtr);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v30 = 134;
    goto LABEL_41;
  }
  if ( (this->vt & 0xFFF) != 0xC )
  {
    ElementDataPtr = CMFPropVariant::GetElementDataPtr((CMFPropVariant *)&pvarDest, 0, &v51);
    if ( ElementDataPtr >= 0 )
    {
      p_pvarDest = v51;
      goto LABEL_28;
    }
    v37 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22);
      CallStackTracing::s_wpInstance = v38;
      if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
      {
        v37 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v37 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v37 + 8) )
    {
      v46 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v37);
      if ( *((_DWORD *)v46 + 499) != ElementDataPtr )
        CallStackContext::TraceFailure(v46, "CMFPropVariant::InsertElement", 2086, ElementDataPtr);
    }
    if ( !g_wppLevels )
      goto LABEL_31;
    v30 = 135;
LABEL_41:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v30,
      WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
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
  v39 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24);
    CallStackTracing::s_wpInstance = v40;
    if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
    {
      v39 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v39 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v39 + 8) )
  {
    v47 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
    if ( *((_DWORD *)v47 + 499) != ElementDataPtr )
      CallStackContext::TraceFailure(v47, "CMFPropVariant::InsertElement", 2093, ElementDataPtr);
  }
  if ( g_wppLevels )
  {
    v30 = 136;
    goto LABEL_41;
  }
LABEL_31:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v49);
  CoTaskMemFree(0);
  CMFPropVariant::Clear(&pvarDest);
  return (unsigned int)ElementDataPtr;
}

```

## disassembly

```asm
0x180014bf0  mov     [rsp-38h+arg_18], rbx
0x180014bf5  push    rbp
0x180014bf6  push    rsi
0x180014bf7  push    rdi
0x180014bf8  push    r12
0x180014bfa  push    r13
0x180014bfc  push    r14
0x180014bfe  push    r15
0x180014c00  mov     rbp, rsp
0x180014c03  sub     rsp, 70h
0x180014c07  mov     rax, cs:__security_cookie
0x180014c0e  xor     rax, rsp
0x180014c11  mov     [rbp+var_10], rax
0x180014c15  xor     r15d, r15d
0x180014c18  mov     [rbp+pvarSrc], r8
0x180014c1c  mov     rdi, rcx
0x180014c1f  mov     [rbp+var_3C], r15d
0x180014c23  movzx   ecx, word ptr [rcx]
0x180014c26  xor     eax, eax
0x180014c28  mov     r10d, 1000h
0x180014c2e  mov     [rbp+var_38], r15
0x180014c32  and     cx, r10w
0x180014c36  mov     qword ptr [rbp+pvarDest+10h], rax
0x180014c3a  xorps   xmm0, xmm0
0x180014c3d  mov     r13d, edx
0x180014c40  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180014c44  cmp     r15w, cx
0x180014c48  jz      loc_180014E55
0x180014c4e  cmp     r15w, [rdi]
0x180014c52  jz      loc_180014FAD
0x180014c58  mov     r14d, [rdi+8]
0x180014c5c  cmp     rdi, r8
0x180014c5f  jz      loc_180014FE3
0x180014c65  movzx   ecx, word ptr [r8]
0x180014c69  cmp     r15w, cx
0x180014c6d  jz      loc_180014ED3
0x180014c73  mov     r8d, 0FFFh
0x180014c79  mov     r9d, 0Ch
0x180014c7f  cmp     r15w, [rdi]
0x180014c83  jz      short loc_180014CA2
0x180014c85  movzx   edx, word ptr [rdi]
0x180014c88  and     dx, r8w
0x180014c8c  cmp     r9w, dx
0x180014c90  jz      short loc_180014CA2
0x180014c92  movzx   eax, cx
0x180014c95  and     ax, r8w
0x180014c99  cmp     ax, dx
0x180014c9c  jnz     loc_180014ED3
0x180014ca2  cmp     r14d, r13d
0x180014ca5  jb      loc_180014ED3
0x180014cab  cmp     r15w, [rdi]
0x180014caf  jz      loc_1800152CB
0x180014cb5  lea     rdx, [rbp+var_3C]; unsigned int *
0x180014cb9  mov     rcx, rdi; struct CMFPropVariant *
0x180014cbc  call    ?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z; CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)
0x180014cc1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180014cc8  mov     ebx, eax
0x180014cca  test    rcx, rcx
0x180014ccd  jz      loc_180014EC2
0x180014cd3  lea     rsi, aCmfpropvariant_13; "CMFPropVariant::InsertElement"
0x180014cda  mov     r12d, 7DFh
0x180014ce0  cmp     [rcx+8], r15b
0x180014ce4  jz      short loc_180014D12
0x180014ce6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180014ceb  mov     ecx, [rax+7C4h]
0x180014cf1  cmp     ecx, [rax+7C8h]
0x180014cf7  jnb     short loc_180014D05
0x180014cf9  add     rcx, rcx
0x180014cfc  mov     [rax+rcx*8], rsi
0x180014d00  mov     [rax+rcx*8+8], r12d
0x180014d05  inc     dword ptr [rax+7C4h]
0x180014d0b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014d12  test    ebx, ebx
0x180014d14  js      loc_180015046
0x180014d1a  mov     r12d, [rbp+var_3C]
0x180014d1e  lea     eax, [r14+1]
0x180014d22  imul    eax, r12d
0x180014d26  mov     ecx, eax; cb
0x180014d28  mov     ebx, eax
0x180014d2a  call    cs:__imp_CoTaskMemAlloc
0x180014d31  nop     dword ptr [rax+rax+00h]
0x180014d36  mov     r15, rax
0x180014d39  test    rax, rax
0x180014d3c  jz      loc_180014F7B
0x180014d42  mov     r8d, ebx; Size
0x180014d45  xor     edx, edx; Val
0x180014d47  mov     rcx, rax; void *
0x180014d4a  call    memset_0
0x180014d4f  lea     rbx, [rdi+10h]
0x180014d53  test    r13d, r13d
0x180014d56  jz      short loc_180014D6A
0x180014d58  mov     rdx, [rbx]; Src
0x180014d5b  mov     r8d, r13d
0x180014d5e  imul    r8d, r12d; Size
0x180014d62  mov     rcx, r15; void *
0x180014d65  call    memcpy_0
0x180014d6a  cmp     r14d, r13d
0x180014d6d  ja      loc_180015324
0x180014d73  mov     rcx, [rbx]; pv
0x180014d76  call    cs:__imp_CoTaskMemFree
0x180014d7d  nop     dword ptr [rax+rax+00h]
0x180014d82  mov     rdx, [rbp+pvarSrc]; pvarSrc
0x180014d86  lea     rcx, [rbp+pvarDest]; pvarDest
0x180014d8a  inc     dword ptr [rdi+8]
0x180014d8d  xor     r14d, r14d
0x180014d90  mov     [rbx], r15
0x180014d93  call    ?Copy@CMFPropVariant@@QEAAJPEBUtagPROPVARIANT@@@Z; CMFPropVariant::Copy(tagPROPVARIANT const *)
0x180014d98  mov     ebx, eax
0x180014d9a  test    eax, eax
0x180014d9c  js      loc_180014F43
0x180014da2  movzx   eax, word ptr [rdi]
0x180014da5  lea     r12d, [r14+0Ch]
0x180014da9  mov     r15d, 0FFFh
0x180014daf  and     ax, r15w
0x180014db3  cmp     r12w, ax
0x180014db7  jz      loc_180015351
0x180014dbd  lea     r8, [rbp+var_38]; void **
0x180014dc1  xor     edx, edx; unsigned int
0x180014dc3  lea     rcx, [rbp+pvarDest]; this
0x180014dc7  call    ?GetElementDataPtr@CMFPropVariant@@IEBAJKPEAPEAX@Z; CMFPropVariant::GetElementDataPtr(ulong,void * *)
0x180014dcc  mov     ebx, eax
0x180014dce  test    eax, eax
0x180014dd0  js      loc_180015081
0x180014dd6  mov     r8, [rbp+var_38]; void *
0x180014dda  mov     edx, r13d; unsigned int
0x180014ddd  mov     rcx, rdi; this
0x180014de0  call    ?SetElementData@CMFPropVariant@@IEAAJKPEBX@Z; CMFPropVariant::SetElementData(ulong,void const *)
0x180014de5  mov     ebx, eax
0x180014de7  test    eax, eax
0x180014de9  js      loc_1800150C3
0x180014def  movzx   eax, word ptr [rdi]
0x180014df2  and     ax, r15w
0x180014df6  cmp     word ptr [rbp+pvarDest], 48h ; 'H'
0x180014dfb  jz      loc_180014FB5
0x180014e01  xorps   xmm0, xmm0
0x180014e04  xor     eax, eax
0x180014e06  movups  xmmword ptr [rbp+pvarDest], xmm0
0x180014e0a  mov     qword ptr [rbp+pvarDest+10h], rax
0x180014e0e  lea     rcx, [rbp+var_40]; this
0x180014e12  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180014e17  xor     ecx, ecx; pv
0x180014e19  call    cs:__imp_CoTaskMemFree
0x180014e20  nop     dword ptr [rax+rax+00h]
0x180014e25  lea     rcx, [rbp+pvarDest]; pvar
0x180014e29  call    ?Clear@CMFPropVariant@@QEAAJXZ; CMFPropVariant::Clear(void)
0x180014e2e  mov     eax, ebx
0x180014e30  mov     rcx, [rbp+var_10]
0x180014e34  xor     rcx, rsp; StackCookie
0x180014e37  call    __security_check_cookie
0x180014e3c  mov     rbx, [rsp+70h+arg_18]
0x180014e44  add     rsp, 70h
0x180014e48  pop     r15
0x180014e4a  pop     r14
0x180014e4c  pop     r13
0x180014e4e  pop     r12
0x180014e50  pop     rdi
0x180014e51  pop     rsi
0x180014e52  pop     rbp
0x180014e53  retn
0x180014e55  cmp     r15w, [rdi]
0x180014e59  jz      loc_180014FAD
0x180014e5f  mov     r14d, 7BAh
0x180014e65  lea     rsi, aCmfpropvariant_13; "CMFPropVariant::InsertElement"
0x180014e6c  mov     r8d, r14d; int
0x180014e6f  lea     rcx, [rbp+var_40]; this
0x180014e73  mov     rdx, rsi; char *
0x180014e76  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180014e7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014e82  mov     ebx, 0C00D36ECh
0x180014e87  test    rcx, rcx
0x180014e8a  jnz     loc_180015269
0x180014e90  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014e97  nop     dword ptr [rax+rax+00h]
0x180014e9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014ea3  mov     rcx, rax
0x180014ea6  test    rax, rax
0x180014ea9  jnz     loc_180015249
0x180014eaf  lea     rcx, qword_1801B97E0
0x180014eb6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180014ebd  jmp     loc_180015269
0x180014ec2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180014ec7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014ece  jmp     loc_180014CD3
0x180014ed3  mov     r14d, 7CEh
0x180014ed9  lea     rsi, aCmfpropvariant_13; "CMFPropVariant::InsertElement"
0x180014ee0  mov     r8d, r14d; int
0x180014ee3  lea     rcx, [rbp+var_40]; this
0x180014ee7  mov     rdx, rsi; char *
0x180014eea  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180014eef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180014ef6  mov     ebx, 80070057h
0x180014efb  test    rcx, rcx
0x180014efe  jz      loc_180014FD2
0x180014f04  cmp     [rcx+8], r15b
0x180014f08  jnz     loc_180015222
0x180014f0e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014f15  jb      loc_180014E0E
0x180014f1b  mov     edx, 83h
0x180014f20  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f27  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180014f2e  mov     r9, rdi
0x180014f31  mov     [rsp+70h+var_50], ebx
0x180014f35  mov     rcx, [rcx+10h]
0x180014f39  call    WPP_SF_qD
0x180014f3e  jmp     loc_180014E0E
0x180014f43  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180014f4a  test    rcx, rcx
0x180014f4d  jz      short loc_180014F6D
0x180014f4f  cmp     [rcx+8], r14b
0x180014f53  jnz     loc_1800151A4
0x180014f59  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014f60  jb      loc_180014E0E
0x180014f66  mov     edx, 86h
0x180014f6b  jmp     short loc_180014F20
0x180014f6d  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180014f72  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014f79  jmp     short loc_180014F4F
0x180014f7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180014f82  mov     ebx, 8007000Eh
0x180014f87  test    rcx, rcx
0x180014f8a  jz      short loc_180014FC4
0x180014f8c  cmp     byte ptr [rcx+8], 0
0x180014f90  jnz     loc_18001517A
0x180014f96  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014f9d  jb      loc_180014E0E
0x180014fa3  mov     edx, 85h
0x180014fa8  jmp     loc_180014F20
0x180014fad  mov     r14d, r15d
0x180014fb0  jmp     loc_180014C5C
0x180014fb5  cmp     r12w, ax
0x180014fb9  jz      loc_180014E01
0x180014fbf  jmp     loc_180014E0E
0x180014fc4  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180014fc9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014fd0  jmp     short loc_180014F8C
0x180014fd2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180014fd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014fde  jmp     loc_180014F04
0x180014fe3  mov     r14d, 7C7h
0x180014fe9  lea     rsi, aCmfpropvariant_13; "CMFPropVariant::InsertElement"
0x180014ff0  mov     r8d, r14d; int
0x180014ff3  lea     rcx, [rbp+var_40]; this
0x180014ff7  mov     rdx, rsi; char *
0x180014ffa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180014fff  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015006  mov     ebx, 80004003h
0x18001500b  test    rcx, rcx
0x18001500e  jnz     loc_1800152AA
0x180015014  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001501b  nop     dword ptr [rax+rax+00h]
0x180015020  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015027  mov     rcx, rax
0x18001502a  test    rax, rax
0x18001502d  jnz     loc_18001528A
0x180015033  lea     rcx, qword_1801B97E0
0x18001503a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015041  jmp     loc_1800152AA
0x180015046  test    rcx, rcx
0x180015049  jnz     loc_180015303
0x18001504f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015056  nop     dword ptr [rax+rax+00h]
0x18001505b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180015062  mov     rcx, rax
0x180015065  test    rax, rax
0x180015068  jnz     loc_1800152E3
0x18001506e  lea     rcx, qword_1801B97E0
0x180015075  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001507c  jmp     loc_180015303
0x180015081  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015088  test    rcx, rcx
0x18001508b  jnz     loc_18001537A
0x180015091  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180015098  nop     dword ptr [rax+rax+00h]
0x18001509d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800150a4  mov     rcx, rax
0x1800150a7  test    rax, rax
0x1800150aa  jnz     loc_18001535A
0x1800150b0  lea     rcx, qword_1801B97E0
0x1800150b7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800150be  jmp     loc_18001537A
0x1800150c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800150ca  test    rcx, rcx
0x1800150cd  jnz     loc_1800153BB
0x1800150d3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800150da  nop     dword ptr [rax+rax+00h]
0x1800150df  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800150e6  mov     rcx, rax
0x1800150e9  test    rax, rax
0x1800150ec  jnz     loc_18001539B
0x1800150f2  lea     rcx, qword_1801B97E0
0x1800150f9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180015100  jmp     loc_1800153BB
0x180015105  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001510a  cmp     [rax+7CCh], ebx
0x180015110  jz      loc_180015273
0x180015116  mov     r9d, ebx; int
0x180015119  mov     r8d, r14d; int
0x18001511c  mov     rdx, rsi; char *
0x18001511f  mov     rcx, rax; this
0x180015122  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
  ... truncated ...
```
