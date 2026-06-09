# PlaiWriteXmlElement(ushort const *,IXMLDOMDocument *,IXMLDOMNode *,tagVARIANT *)

- ea: `0x18003bb54`
- end: `0x18003c6ff`
- name: `?PlaiWriteXmlElement@@YAJPEBGPEAUIXMLDOMDocument@@PEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z`
- size: `2987`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IXMLDOMDocument *, struct IXMLDOMNode *, struct tagVARIANT *)`
- caller_count: `17`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180053524`
- `0x18006f06c`
- `0x180072480`
- `0x180079150`
- `0x18007aa7c`
- `0x180082c64`
- `0x1800891b0`
- `0x180095260`
- `0x180098730`
- `0x1800a19e8`
- `0x1800c0a88`
- `0x1800c8eb0`
- `0x1800cdfe0`
- `0x1800cef00`
- `0x1800d36a0`
- `0x1801039f4`
- `0x180108fb8`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180015f98`
- `0x1800182a4`
- `0x180018420`
- `0x18003bb54`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c3d8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003c3d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c3c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003c3c5`
- `OLEAUT32!__imp_VariantInit` at `0x18003bbbe`
- `OLEAUT32!__imp_VariantInit` at `0x18003bbcc`
- `OLEAUT32!__imp_VariantInit` at `0x18003bbbe`
- `OLEAUT32!__imp_VariantInit` at `0x18003bbcc`
- `OLEAUT32!__imp_VariantClear` at `0x18003bbda`
- `OLEAUT32!__imp_VariantClear` at `0x18003c2d5`
- `OLEAUT32!__imp_VariantClear` at `0x18003c2e3`
- `OLEAUT32!__imp_VariantClear` at `0x18003bbda`
- `OLEAUT32!__imp_VariantClear` at `0x18003c2d5`
- `OLEAUT32!__imp_VariantClear` at `0x18003c2e3`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003c344`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003c344`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003bdfa`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18003bdfa`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003c2ae`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18003c2ae`

## string_xrefs

- `0x18003bd7d`: `PlaiWriteXmlElement`
- `0x18003c097`: `PlaiWriteXmlElement`
- `0x18003c247`: `PlaiWriteXmlElement`
- `0x18003c512`: `PlaiWriteXmlElement`

## pseudocode

```c
__int64 __fastcall PlaiWriteXmlElement(
        unsigned __int16 *a1,
        struct IXMLDOMDocument *a2,
        struct IXMLDOMNode *a3,
        struct tagVARIANT *a4)
{
  const unsigned __int16 *v5; // r12
  int v9; // r8d
  unsigned __int16 *v10; // rdx
  unsigned __int16 *v11; // rax
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned int v17; // r14d
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rsi
  HRESULT v19; // eax
  unsigned __int64 v20; // rdx
  __int64 v21; // rbx
  int v22; // eax
  unsigned __int64 v23; // rdx
  int v24; // eax
  unsigned __int64 v25; // rdx
  int v26; // eax
  unsigned __int64 v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // rbx
  __int64 v30; // rbx
  int v31; // eax
  unsigned __int64 v32; // rdx
  __int64 v33; // rbx
  int v34; // eax
  unsigned __int64 v35; // rdx
  __int64 v36; // rbx
  HRESULT v38; // eax
  unsigned __int64 v39; // rdx
  __int64 v40; // rbx
  HANDLE ProcessHeap; // rax
  const unsigned __int16 *v42; // rax
  unsigned __int64 v43; // rdx
  unsigned __int64 v44; // rcx
  __int64 v45; // rbx
  int v46; // eax
  unsigned __int64 v47; // rdx
  const char *v48; // r8
  int v49; // r9d
  __int64 v50; // rbx
  int v51; // eax
  unsigned __int64 v52; // rdx
  __int64 v53; // rbx
  int v54; // eax
  unsigned __int64 v55; // rdx
  __int64 v56; // rbx
  int v57; // [rsp+70h] [rbp-90h] BYREF
  __int64 v58; // [rsp+78h] [rbp-88h] BYREF
  __int64 v59; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v60; // [rsp+88h] [rbp-78h]
  void *ppvData; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG pvargDest; // [rsp+B0h] [rbp-50h] BYREF
  const unsigned __int16 *v64; // [rsp+C8h] [rbp-38h] BYREF
  struct IXMLDOMNode *v65; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v66[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v67[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v68[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v69[64]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v70[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v71[64]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v72[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v73[64]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v74[64]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v75[64]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 v76[64]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int16 v77[64]; // [rsp+660h] [rbp+560h] BYREF
  unsigned __int16 v78[64]; // [rsp+6E0h] [rbp+5E0h] BYREF

  v65 = a3;
  v59 = 0;
  ppvData = 0;
  v60 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v5 = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  VariantInit(&pvarg);
  pvarg.llVal = 0;
  VariantInit(&pvargDest);
  pvargDest.llVal = 0;
  VariantClear(&pvarg);
  v10 = 0;
  pvarg.llVal = 0;
  if ( a1 )
  {
    v11 = PlaiAllocStringEx(a1, 0, v9);
    a1 = 0;
    pvarg.llVal = (LONGLONG)v11;
    v10 = v11;
    if ( !v11 )
    {
      v12 = (unsigned int)xmmword_180169738;
      v13 = qword_180169748;
      v14 = *(&xmmword_180169738 + 1);
      LODWORD(v58) = 0;
      v15 = -1;
      v57 = -2147024882;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v66, (unsigned int)xmmword_180169738);
        v16 = -1;
        do
          ++v16;
        while ( v66[v16] );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v57, 4, byte_180147320, 1, &v58, 4);
        v13 = qword_180169748;
        v14 = *(&xmmword_180169738 + 1);
        v12 = (unsigned int)xmmword_180169738;
      }
      LODWORD(v58) = -2147024882;
      v57 = 0;
      v17 = -2147024882;
      if ( (_DWORD)v12 && (v14 & 0x4000000000000800LL) != 0 && v13 == (v13 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v67, v12);
        do
          ++v15;
        while ( v67[v15] );
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v58, 4, byte_180147320, 1, &v57, 4);
      }
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a4->llVal;
      goto LABEL_68;
    }
  }
  pvarg.vt = 8;
  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a4->llVal;
  if ( a4->vt == 8200 )
  {
    if ( p_llVal->bstrVal == a1 )
    {
      v17 = (unsigned int)a1;
      goto LABEL_69;
    }
LABEL_20:
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a4->llVal;
    v19 = SafeArrayAccessData(a4->parray, &ppvData);
    v17 = v19;
    if ( v19 >= 0 )
    {
      while ( (unsigned int)a1 < *(_DWORD *)(p_llVal->llVal + 24) )
      {
        if ( v59 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
          v59 = 0;
        }
        v22 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, LONGLONG, __int64 *))a2->lpVtbl->createElement)(
                a2,
                pvarg.llVal,
                &v59);
        v17 = v22;
        if ( v22 < 0 )
        {
          v57 = 0;
          LODWORD(v58) = v22;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v71, v23);
            v30 = -1;
            do
              ++v30;
            while ( v71[v30] );
            goto LABEL_51;
          }
          goto LABEL_69;
        }
        v24 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v59 + 216LL))(
                v59,
                *((_QWORD *)ppvData + (unsigned int)a1));
        v17 = v24;
        if ( v24 < 0 )
        {
          v57 = 0;
          LODWORD(v58) = v24;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v70, v25);
            v29 = -1;
            do
              ++v29;
            while ( v70[v29] );
            goto LABEL_51;
          }
          goto LABEL_69;
        }
        v26 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))a3->lpVtbl->appendChild)(a3, v59, 0);
        v17 = v26;
        if ( v26 < 0 )
        {
          v57 = 0;
          LODWORD(v58) = v26;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v69, v27);
            v28 = -1;
            do
              ++v28;
            while ( v69[v28] );
            goto LABEL_51;
          }
          goto LABEL_69;
        }
        LODWORD(a1) = (_DWORD)a1 + 1;
      }
    }
    else
    {
      v57 = (int)a1;
      LODWORD(v58) = v19;
      if ( (_DWORD)xmmword_180169738 != (_DWORD)a1
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v68, v20);
        v21 = -1;
        do
          ++v21;
        while ( v68[v21] );
LABEL_51:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v58, 4, byte_180147320, 1, &v57, 4);
        goto LABEL_69;
      }
    }
    goto LABEL_69;
  }
  if ( (a4->vt & 0x2000) != 0 )
    goto LABEL_20;
  v31 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, unsigned __int16 *, __int64 *))a2->lpVtbl->createElement)(
          a2,
          v10,
          &v59);
  v17 = v31;
  if ( v31 >= 0 )
  {
    if ( a4->vt == 8 )
    {
      if ( p_llVal->bstrVal == a1 )
      {
LABEL_61:
        v34 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v65->lpVtbl->appendChild)(v65, v59, 0);
        v17 = v34;
        if ( v34 >= 0 )
          goto LABEL_68;
        v57 = (int)a1;
        LODWORD(v58) = v34;
        if ( (_DWORD)xmmword_180169738 == (_DWORD)a1
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_68;
        }
        PlaiWhoAmI(v78, v35);
        v36 = -1;
        do
          ++v36;
        while ( v78[v36] );
LABEL_67:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v58, 4, byte_180147320, 1, &v57, 4);
LABEL_68:
        v5 = v60;
        goto LABEL_69;
      }
    }
    else if ( (unsigned __int16)(a4->vt - 20) <= 1u )
    {
      ProcessHeap = GetProcessHeap();
      v42 = (const unsigned __int16 *)HeapAlloc(ProcessHeap, 0, 0x800u);
      v43 = (unsigned int)xmmword_180169738;
      v44 = qword_180169748;
      a1 = (unsigned __int16 *)v42;
      v58 = 2048;
      v60 = v42;
      v64 = v42;
      v57 = 0;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000200LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000200LL) )
      {
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ALLOC, 4, byte_180147320, 1, &v57, 4, &v64, 8);
        v44 = qword_180169748;
        v43 = (unsigned int)xmmword_180169738;
      }
      if ( !a1 )
      {
        v57 = 0;
        LODWORD(v58) = -2147024882;
        v17 = -2147024882;
        if ( !(_DWORD)v43
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || v44 != (v44 & 0x4000000000000800LL) )
        {
          goto LABEL_68;
        }
        PlaiWhoAmI(v74, v43);
        v45 = -1;
        do
          ++v45;
        while ( v74[v45] );
        goto LABEL_67;
      }
      v46 = StringCchPrintfW(a1, 0x400u, L"0x%I64x", p_llVal->llVal);
      v17 = v46;
      if ( v46 < 0 )
      {
        v57 = 0;
        LODWORD(v58) = v46;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_68;
        }
        PlaiWhoAmI(v75, v47);
        v50 = -1;
        do
          ++v50;
        while ( v75[v50] );
        goto LABEL_67;
      }
      v51 = PlaiSetVariantEx(a1, &pvargDest, v48, v49);
      LODWORD(a1) = 0;
      v17 = v51;
      if ( v51 < 0 )
      {
        v57 = 0;
        LODWORD(v58) = v51;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_68;
        }
        PlaiWhoAmI(v76, v52);
        v53 = -1;
        do
          ++v53;
        while ( v76[v53] );
        goto LABEL_67;
      }
      goto LABEL_109;
    }
    v38 = VariantChangeType(&pvargDest, a4, 4u, 8u);
    v17 = v38;
    if ( v38 < 0 )
    {
      v57 = (int)a1;
      LODWORD(v58) = v38;
      if ( (_DWORD)xmmword_180169738 == (_DWORD)a1
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_68;
      }
      PlaiWhoAmI(v73, v39);
      v40 = -1;
      do
        ++v40;
      while ( v73[v40] );
      goto LABEL_67;
    }
LABEL_109:
    v54 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v59 + 216LL))(v59, pvargDest.llVal);
    v17 = v54;
    if ( v54 < 0 )
    {
      v57 = (int)a1;
      LODWORD(v58) = v54;
      if ( (_DWORD)xmmword_180169738 == (_DWORD)a1
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_68;
      }
      PlaiWhoAmI(v77, v55);
      v56 = -1;
      do
        ++v56;
      while ( v77[v56] );
      goto LABEL_67;
    }
    goto LABEL_61;
  }
  v57 = (int)a1;
  LODWORD(v58) = v31;
  if ( (_DWORD)xmmword_180169738 != (_DWORD)a1
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v72, v32);
    v33 = -1;
    do
      ++v33;
    while ( v72[v33] );
    goto LABEL_51;
  }
LABEL_69:
  if ( ppvData )
  {
    SafeArrayUnaccessData(p_llVal->parray);
    ppvData = 0;
  }
  if ( v59 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  VariantClear(&pvargDest);
  pvargDest.llVal = 0;
  if ( v5 )
    PlaiFree(v5, 1);
  return v17;
}

```

## disassembly

```asm
0x18003bb54  push    rbp
0x18003bb56  push    rbx
0x18003bb57  push    rsi
0x18003bb58  push    rdi
0x18003bb59  push    r12
0x18003bb5b  push    r13
0x18003bb5d  push    r14
0x18003bb5f  push    r15
0x18003bb61  lea     rbp, [rsp-678h]
0x18003bb69  sub     rsp, 778h
0x18003bb70  mov     rax, cs:__security_cookie
0x18003bb77  xor     rax, rsp
0x18003bb7a  mov     [rbp+6B0h+var_50], rax
0x18003bb81  xor     esi, esi
0x18003bb83  mov     [rbp+6B0h+var_6E0], r8
0x18003bb87  xor     eax, eax
0x18003bb89  mov     [rbp+6B0h+var_730], rsi
0x18003bb8d  mov     rbx, rcx
0x18003bb90  mov     qword ptr [rbp+6B0h+pvarg+10h], rax
0x18003bb94  xorps   xmm0, xmm0
0x18003bb97  mov     qword ptr [rbp+6B0h+pvargDest+10h], rax
0x18003bb9b  xorps   xmm1, xmm1
0x18003bb9e  mov     [rbp+6B0h+ppvData], rsi
0x18003bba2  lea     rcx, [rbp+6B0h+pvarg]; pvarg
0x18003bba6  mov     [rbp+6B0h+var_728], rsi
0x18003bbaa  movups  xmmword ptr [rbp+6B0h+pvarg], xmm0
0x18003bbae  mov     r12d, esi
0x18003bbb1  mov     r13, r9
0x18003bbb4  movups  xmmword ptr [rbp+6B0h+pvargDest], xmm1
0x18003bbb8  mov     r15, r8
0x18003bbbb  mov     rdi, rdx
0x18003bbbe  call    cs:__imp_VariantInit
0x18003bbc4  lea     rcx, [rbp+6B0h+pvargDest]; pvarg
0x18003bbc8  mov     qword ptr [rbp+6B0h+pvarg+8], rsi
0x18003bbcc  call    cs:__imp_VariantInit
0x18003bbd2  lea     rcx, [rbp+6B0h+pvarg]; pvarg
0x18003bbd6  mov     qword ptr [rbp+6B0h+pvargDest+8], rsi
0x18003bbda  call    cs:__imp_VariantClear
0x18003bbe0  mov     edx, esi; char *
0x18003bbe2  mov     qword ptr [rbp+6B0h+pvarg+8], rdx
0x18003bbe6  test    rbx, rbx
0x18003bbe9  jz      loc_18003BDB9
0x18003bbef  mov     rcx, rbx; unsigned __int16 *
0x18003bbf2  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18003bbf7  xor     ebx, ebx
0x18003bbf9  mov     qword ptr [rbp+6B0h+pvarg+8], rax
0x18003bbfd  mov     rdx, rax
0x18003bc00  test    rax, rax
0x18003bc03  jnz     loc_18003BDB9
0x18003bc09  mov     edx, dword ptr cs:xmmword_180169738; unsigned __int64
0x18003bc0f  lea     r15d, [rsi+4]
0x18003bc13  mov     rcx, cs:qword_180169748
0x18003bc1a  lea     rsi, byte_180147320
0x18003bc21  mov     r8, qword ptr cs:xmmword_180169738+8
0x18003bc28  xor     r14d, r14d
0x18003bc2b  mov     dword ptr [rsp+7B0h+var_738], ebx
0x18003bc2f  mov     r12d, 8007000Eh
0x18003bc35  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003bc39  mov     [rsp+7B0h+var_740], r12d
0x18003bc3e  mov     rdi, 4000000000000800h
0x18003bc48  test    edx, edx
0x18003bc4a  jz      loc_18003BCFF
0x18003bc50  test    rdi, r8
0x18003bc53  jz      loc_18003BCFF
0x18003bc59  mov     rax, rcx
0x18003bc5c  and     rax, rdi
0x18003bc5f  cmp     rcx, rax
0x18003bc62  jnz     loc_18003BCFF
0x18003bc68  lea     rcx, [rbp+6B0h+var_6D0]; unsigned __int16 *
0x18003bc6c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18003bc71  lea     rcx, [rbp+6B0h+var_6D0]
0x18003bc75  mov     rax, rbx
0x18003bc78  inc     rax
0x18003bc7b  cmp     [rcx+rax*2], r14w
0x18003bc80  jnz     short loc_18003BC78
0x18003bc82  lea     ecx, [rax+rax]
0x18003bc85  add     rcx, 2
0x18003bc89  lea     rax, [rbp+6B0h+var_6D0]
0x18003bc8d  mov     [rsp+7B0h+var_750], rcx
0x18003bc92  lea     r9, [rsp+7B0h+var_740]
0x18003bc97  mov     [rsp+7B0h+var_758], rax
0x18003bc9c  lea     rdx, PLA_EVENT_ERROR
0x18003bca3  mov     [rsp+7B0h+var_760], 11h
0x18003bcac  lea     rax, aPlaisetvariant; "PlaiSetVariantEx"
0x18003bcb3  mov     [rsp+7B0h+var_768], rax
0x18003bcb8  mov     ecx, 1
0x18003bcbd  mov     [rsp+7B0h+var_770], r15
0x18003bcc2  lea     rax, [rsp+7B0h+var_738]
0x18003bcc7  mov     [rsp+7B0h+var_778], rax
0x18003bccc  mov     [rsp+7B0h+var_780], rcx
0x18003bcd1  lea     r8d, [rcx+4]
0x18003bcd5  mov     [rsp+7B0h+var_788], rsi
0x18003bcda  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18003bce1  mov     [rsp+7B0h+var_790], r15
0x18003bce6  call    EventingWriteEvent
0x18003bceb  mov     rcx, cs:qword_180169748
0x18003bcf2  mov     r8, qword ptr cs:xmmword_180169738+8
0x18003bcf9  mov     edx, dword ptr cs:xmmword_180169738; unsigned __int64
0x18003bcff  xor     eax, eax
0x18003bd01  mov     dword ptr [rsp+7B0h+var_738], r12d
0x18003bd06  mov     [rsp+7B0h+var_740], eax
0x18003bd0a  mov     r14d, r12d
0x18003bd0d  test    edx, edx
0x18003bd0f  jz      loc_18003BDB0
0x18003bd15  test    rdi, r8
0x18003bd18  jz      loc_18003BDB0
0x18003bd1e  mov     rax, rcx
0x18003bd21  and     rax, rdi
0x18003bd24  cmp     rcx, rax
0x18003bd27  jnz     loc_18003BDB0
0x18003bd2d  lea     rcx, [rbp+6B0h+var_650]; unsigned __int16 *
0x18003bd31  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18003bd36  lea     rcx, [rbp+6B0h+var_650]
0x18003bd3a  xor     eax, eax
0x18003bd3c  inc     rbx
0x18003bd3f  cmp     [rcx+rbx*2], ax
0x18003bd43  jnz     short loc_18003BD3C
0x18003bd45  lea     rax, [rbp+6B0h+var_650]
0x18003bd49  mov     r8d, 5
0x18003bd4f  lea     ecx, [rbx+rbx]
0x18003bd52  add     rcx, 2
0x18003bd56  lea     r9, [rsp+7B0h+var_738]
0x18003bd5b  mov     [rsp+7B0h+var_750], rcx
0x18003bd60  lea     rdx, PLA_EVENT_ERROR
0x18003bd67  mov     [rsp+7B0h+var_758], rax
0x18003bd6c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18003bd73  mov     eax, 14h
0x18003bd78  mov     [rsp+7B0h+var_760], rax
0x18003bd7d  lea     rax, aPlaiwritexmlel; "PlaiWriteXmlElement"
0x18003bd84  mov     [rsp+7B0h+var_768], rax
0x18003bd89  lea     rax, [rsp+7B0h+var_740]
0x18003bd8e  mov     [rsp+7B0h+var_770], r15
0x18003bd93  mov     [rsp+7B0h+var_778], rax
0x18003bd98  mov     [rsp+7B0h+var_780], 1
0x18003bda1  mov     [rsp+7B0h+var_788], rsi
0x18003bda6  mov     [rsp+7B0h+var_790], r15
0x18003bdab  call    EventingWriteEvent
0x18003bdb0  lea     rsi, [r13+8]
0x18003bdb4  jmp     loc_18003C29F
0x18003bdb9  mov     eax, 8
0x18003bdbe  mov     word ptr [rbp+6B0h+pvarg], ax
0x18003bdc2  mov     eax, 2008h
0x18003bdc7  lea     rsi, [r13+8]
0x18003bdcb  cmp     [r13+0], ax
0x18003bdd0  jnz     short loc_18003BDDF
0x18003bdd2  cmp     [rsi], rbx
0x18003bdd5  jnz     short loc_18003BDEF
0x18003bdd7  mov     r14d, ebx
0x18003bdda  jmp     loc_18003C2A3
0x18003bddf  mov     eax, 2000h
0x18003bde4  test    [r13+0], ax
0x18003bde9  jz      loc_18003C0D6
0x18003bdef  lea     rsi, [r13+8]
0x18003bdf3  mov     rcx, [rsi]; psa
0x18003bdf6  lea     rdx, [rbp+6B0h+ppvData]; ppvData
0x18003bdfa  call    cs:__imp_SafeArrayAccessData
0x18003be00  mov     r14d, eax
0x18003be03  test    eax, eax
0x18003be05  jns     short loc_18003BE77
0x18003be07  cmp     dword ptr cs:xmmword_180169738, ebx
0x18003be0d  mov     [rsp+7B0h+var_740], ebx
0x18003be11  mov     dword ptr [rsp+7B0h+var_738], eax
0x18003be15  jz      loc_18003C2A3
0x18003be1b  mov     rdi, 4000000000000800h
0x18003be25  test    qword ptr cs:xmmword_180169738+8, rdi
0x18003be2c  jz      loc_18003C2A3
0x18003be32  mov     rax, cs:qword_180169748
0x18003be39  and     rax, rdi
0x18003be3c  cmp     cs:qword_180169748, rax
0x18003be43  jnz     loc_18003C2A3
0x18003be49  lea     rcx, [rbp+6B0h+var_5D0]; unsigned __int16 *
0x18003be50  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18003be55  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003be59  lea     rcx, [rbp+6B0h+var_5D0]
0x18003be60  xor     eax, eax
0x18003be62  inc     rbx
0x18003be65  cmp     [rcx+rbx*2], ax
0x18003be69  jnz     short loc_18003BE62
0x18003be6b  lea     rax, [rbp+6B0h+var_5D0]
0x18003be72  jmp     loc_18003C05F
0x18003be77  xor     r13d, r13d
0x18003be7a  mov     rax, [rsi]
0x18003be7d  cmp     ebx, [rax+18h]
0x18003be80  jnb     loc_18003C2A3
0x18003be86  mov     rcx, [rbp+6B0h+var_730]
0x18003be8a  test    rcx, rcx
0x18003be8d  jz      short loc_18003BE9F
0x18003be8f  mov     rax, [rcx]
0x18003be92  mov     rax, [rax+10h]
0x18003be96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be9b  mov     [rbp+6B0h+var_730], r13
0x18003be9f  mov     rax, [rdi]
0x18003bea2  lea     r8, [rbp+6B0h+var_730]
0x18003bea6  mov     rdx, qword ptr [rbp+6B0h+pvarg+8]
0x18003beaa  mov     rcx, rdi
0x18003bead  mov     rax, [rax+178h]
0x18003beb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003beb9  mov     r14d, eax
0x18003bebc  test    eax, eax
0x18003bebe  js      loc_18003BFF3
0x18003bec4  mov     rcx, [rbp+6B0h+var_730]
0x18003bec8  mov     rdx, [rbp+6B0h+ppvData]
0x18003becc  mov     r8d, ebx
0x18003becf  mov     rax, [rcx]
0x18003bed2  mov     rdx, [rdx+r8*8]
0x18003bed6  mov     rax, [rax+0D8h]
0x18003bedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bee2  mov     r14d, eax
0x18003bee5  test    eax, eax
0x18003bee7  js      loc_18003BF85
0x18003beed  mov     rax, [r15]
0x18003bef0  xor     r8d, r8d
0x18003bef3  mov     rdx, [rbp+6B0h+var_730]
0x18003bef7  mov     rcx, r15
0x18003befa  mov     rax, [rax+0A8h]
0x18003bf01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf06  mov     r14d, eax
0x18003bf09  test    eax, eax
0x18003bf0b  js      short loc_18003BF14
0x18003bf0d  inc     ebx
0x18003bf0f  jmp     loc_18003BE7A
0x18003bf14  cmp     dword ptr cs:xmmword_180169738, r13d
0x18003bf1b  mov     [rsp+7B0h+var_740], r13d
0x18003bf20  mov     dword ptr [rsp+7B0h+var_738], eax
0x18003bf24  jz      loc_18003C2A3
0x18003bf2a  mov     rdi, 4000000000000800h
0x18003bf34  test    qword ptr cs:xmmword_180169738+8, rdi
0x18003bf3b  jz      loc_18003C2A3
0x18003bf41  mov     rax, cs:qword_180169748
0x18003bf48  and     rax, rdi
0x18003bf4b  cmp     cs:qword_180169748, rax
0x18003bf52  jnz     loc_18003C2A3
0x18003bf58  lea     rcx, [rbp+6B0h+var_550]; unsigned __int16 *
0x18003bf5f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18003bf64  lea     rax, [rbp+6B0h+var_550]
0x18003bf6b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003bf6f  inc     rbx
0x18003bf72  cmp     [rax+rbx*2], r13w
0x18003bf77  jnz     short loc_18003BF6F
0x18003bf79  lea     rax, [rbp+6B0h+var_550]
0x18003bf80  jmp     loc_18003C05F
0x18003bf85  cmp     dword ptr cs:xmmword_180169738, r13d
0x18003bf8c  mov     [rsp+7B0h+var_740], r13d
0x18003bf91  mov     dword ptr [rsp+7B0h+var_738], eax
0x18003bf95  jz      loc_18003C2A3
0x18003bf9b  mov     rdi, 4000000000000800h
0x18003bfa5  test    qword ptr cs:xmmword_180169738+8, rdi
0x18003bfac  jz      loc_18003C2A3
0x18003bfb2  mov     rax, cs:qword_180169748
0x18003bfb9  and     rax, rdi
0x18003bfbc  cmp     cs:qword_180169748, rax
0x18003bfc3  jnz     loc_18003C2A3
0x18003bfc9  lea     rcx, [rbp+6B0h+var_4D0]; unsigned __int16 *
0x18003bfd0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18003bfd5  lea     rax, [rbp+6B0h+var_4D0]
0x18003bfdc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003bfe0  inc     rbx
0x18003bfe3  cmp     [rax+rbx*2], r13w
0x18003bfe8  jnz     short loc_18003BFE0
0x18003bfea  lea     rax, [rbp+6B0h+var_4D0]
0x18003bff1  jmp     short loc_18003C05F
0x18003bff3  cmp     dword ptr cs:xmmword_180169738, r13d
0x18003bffa  mov     [rsp+7B0h+var_740], r13d
0x18003bfff  mov     dword ptr [rsp+7B0h+var_738], eax
0x18003c003  jz      loc_18003C2A3
0x18003c009  mov     rdi, 4000000000000800h
0x18003c013  test    qword ptr cs:xmmword_180169738+8, rdi
0x18003c01a  jz      loc_18003C2A3
0x18003c020  mov     rax, cs:qword_180169748
0x18003c027  and     rax, rdi
0x18003c02a  cmp     cs:qword_180169748, rax
0x18003c031  jnz     loc_18003C2A3
0x18003c037  lea     rcx, [rbp+6B0h+var_450]; unsigned __int16 *
0x18003c03e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18003c043  lea     rax, [rbp+6B0h+var_450]
0x18003c04a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003c04e  inc     rbx
0x18003c051  cmp     [rax+rbx*2], r13w
0x18003c056  jnz     short loc_18003C04E
0x18003c058  lea     rax, [rbp+6B0h+var_450]
0x18003c05f  mov     r15d, 4
0x18003c065  lea     ecx, [rbx+rbx]
0x18003c068  add     rcx, 2
0x18003c06c  lea     r9, [rsp+7B0h+var_738]
0x18003c071  mov     [rsp+7B0h+var_750], rcx
0x18003c076  lea     rdx, PLA_EVENT_ERROR
0x18003c07d  mov     [rsp+7B0h+var_758], rax
0x18003c082  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18003c089  mov     eax, 14h
0x18003c08e  lea     r8d, [r15+1]
0x18003c092  mov     [rsp+7B0h+var_760], rax
0x18003c097  lea     rax, aPlaiwritexmlel; "PlaiWriteXmlElement"
0x18003c09e  mov     [rsp+7B0h+var_768], rax
0x18003c0a3  lea     rax, [rsp+7B0h+var_740]
0x18003c0a8  mov     [rsp+7B0h+var_770], r15
0x18003c0ad  mov     [rsp+7B0h+var_778], rax
0x18003c0b2  lea     rax, byte_180147320
0x18003c0b9  mov     [rsp+7B0h+var_780], 1
0x18003c0c2  mov     [rsp+7B0h+var_788], rax
0x18003c0c7  mov     [rsp+7B0h+var_790], r15
  ... truncated ...
```
