# ConfigurationDataCollector::SetXml(IDataCollector *,IXMLDOMNode *,IValueMap *,ushort const *)

- ea: `0x1800482e8`
- end: `0x180048c16`
- name: `?SetXml@ConfigurationDataCollector@@SAJPEAUIDataCollector@@PEAUIXMLDOMNode@@PEAUIValueMap@@PEBG@Z`
- size: `2350`
- prototype: `static int(struct IDataCollector *, struct IXMLDOMNode *, struct IValueMap *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800a10c4`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800157bc`
- `0x1800174c0`
- `0x180026850`
- `0x1800482e8`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180048337`
- `OLEAUT32!__imp_VariantInit` at `0x180048337`
- `OLEAUT32!__imp_VariantClear` at `0x180048440`
- `OLEAUT32!__imp_VariantClear` at `0x180048526`
- `OLEAUT32!__imp_VariantClear` at `0x180048bd4`
- `OLEAUT32!__imp_VariantClear` at `0x180048440`
- `OLEAUT32!__imp_VariantClear` at `0x180048526`
- `OLEAUT32!__imp_VariantClear` at `0x180048bd4`

## string_xrefs

- `0x180048576`: `RegistryKeys`
- `0x180048540`: `RegistryKey`
- `0x1800483f2`: `ConfigurationDataCollector::SetXml`
- `0x180048a41`: `RegistryMaxRecursiveDepth`
- `0x180048a76`: `RegistryMaxRecursiveDepth`

## pseudocode

```c
__int64 __fastcall ConfigurationDataCollector::SetXml(
        struct IDataCollector *a1,
        struct IXMLDOMNode *a2,
        struct IValueMap *a3,
        const unsigned __int16 *a4)
{
  struct IDataCollectorVtbl *lpVtbl; // rax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rax
  int *v12; // r9
  int v13; // eax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  int v35; // eax
  __int64 v36; // rax
  int v37; // eax
  int v38; // eax
  __int64 v39; // rax
  int v41; // [rsp+70h] [rbp-90h] BYREF
  int v42; // [rsp+78h] [rbp-88h] BYREF
  __int64 v43; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v45[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v46[64]; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int16 v47[64]; // [rsp+1A0h] [rbp+A0h] BYREF
  unsigned __int16 v48[64]; // [rsp+220h] [rbp+120h] BYREF
  unsigned __int16 v49[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v50[64]; // [rsp+320h] [rbp+220h] BYREF
  unsigned __int16 v51[64]; // [rsp+3A0h] [rbp+2A0h] BYREF
  unsigned __int16 v52[64]; // [rsp+420h] [rbp+320h] BYREF
  unsigned __int16 v53[64]; // [rsp+4A0h] [rbp+3A0h] BYREF
  unsigned __int16 v54[64]; // [rsp+520h] [rbp+420h] BYREF

  memset(&pvarg, 0, sizeof(pvarg));
  v43 = 0;
  VariantInit(&pvarg);
  lpVtbl = a1->lpVtbl;
  pvarg.llVal = 0;
  v9 = ((__int64 (__fastcall *)(struct IDataCollector *, GUID *, __int64 *))lpVtbl->QueryInterface)(
         a1,
         &IID_IConfigurationDataCollector,
         &v43);
  v10 = v9;
  if ( v9 < 0 )
  {
    v41 = 0;
    v42 = v9;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v45, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v45[v11] );
      v12 = &v42;
      goto LABEL_8;
    }
    goto LABEL_91;
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( (int)PlaiReadXmlElement(L"QueryNetworkAdapters", 11, a2, &pvarg) >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 344LL))(v43, pvarg.uiVal);
    if ( v13 )
    {
      v14 = PlaiAddValidation(a3, a4, L"QueryNetworkAdapters", v13);
      v10 = v14;
      if ( v14 < 0 )
      {
        v42 = 0;
        v41 = v14;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_91;
        }
        PlaiWhoAmI(v46, 0x4000000000000800uLL);
        v15 = -1;
        do
          ++v15;
        while ( v46[v15] );
        goto LABEL_17;
      }
    }
  }
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( (int)PlaiReadXmlElement(L"RegistryKey", 8200, a2, &pvarg) >= 0 )
  {
    v16 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v43 + 360LL))(v43, pvarg.llVal);
    if ( v16 )
    {
      v17 = PlaiAddValidation(a3, a4, L"RegistryKeys", v16);
      v10 = v17;
      if ( v17 < 0 )
      {
        v42 = 0;
        v41 = v17;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_91;
        }
        PlaiWhoAmI(v47, 0x4000000000000800uLL);
        v18 = -1;
        do
          ++v18;
        while ( v47[v18] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"File", 8200, a2, &pvarg) >= 0 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v43 + 312LL))(v43, pvarg.llVal);
    if ( v19 )
    {
      v20 = PlaiAddValidation(a3, a4, L"Files", v19);
      v10 = v20;
      if ( v20 < 0 )
      {
        v42 = 0;
        v41 = v20;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_91;
        }
        PlaiWhoAmI(v48, 0x4000000000000800uLL);
        v21 = -1;
        do
          ++v21;
        while ( v48[v21] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"ManagementQuery", 8200, a2, &pvarg) >= 0 )
  {
    v22 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v43 + 328LL))(v43, pvarg.llVal);
    if ( v22 )
    {
      v23 = PlaiAddValidation(a3, a4, L"ManagementQueries", v22);
      v10 = v23;
      if ( v23 < 0 )
      {
        v42 = 0;
        v41 = v23;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_91;
        }
        PlaiWhoAmI(v49, 0x4000000000000800uLL);
        v24 = -1;
        do
          ++v24;
        while ( v49[v24] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"FileMaxCount", 3, a2, &pvarg) >= 0 )
  {
    v25 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 264LL))(v43, pvarg.cyVal.Lo);
    if ( v25 )
    {
      v26 = PlaiAddValidation(a3, a4, L"FileMaxCount", v25);
      v10 = v26;
      if ( v26 < 0 )
      {
        v42 = 0;
        v41 = v26;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_91;
        }
        PlaiWhoAmI(v50, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v50[v27] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"FileMaxTotalSize", 3, a2, &pvarg) >= 0 )
  {
    v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 296LL))(v43, pvarg.cyVal.Lo);
    if ( v28 )
    {
      v29 = PlaiAddValidation(a3, a4, L"FileMaxTotalSize", v28);
      v10 = v29;
      if ( v29 < 0 )
      {
        v42 = 0;
        v41 = v29;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_91;
        }
        PlaiWhoAmI(v51, 0x4000000000000800uLL);
        v30 = -1;
        do
          ++v30;
        while ( v51[v30] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"FileMaxRecursiveDepth", 3, a2, &pvarg) >= 0 )
  {
    v31 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 280LL))(v43, pvarg.cyVal.Lo);
    if ( v31 )
    {
      v32 = PlaiAddValidation(a3, a4, L"FileMaxRecursiveDepth", v31);
      v10 = v32;
      if ( v32 < 0 )
      {
        v42 = 0;
        v41 = v32;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_91;
        }
        PlaiWhoAmI(v52, 0x4000000000000800uLL);
        v33 = -1;
        do
          ++v33;
        while ( v52[v33] );
        goto LABEL_17;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"RegistryMaxRecursiveDepth", 3, a2, &pvarg) >= 0 )
  {
    v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 376LL))(v43, pvarg.cyVal.Lo);
    if ( v34 )
    {
      v35 = PlaiAddValidation(a3, a4, L"RegistryMaxRecursiveDepth", v34);
      v10 = v35;
      if ( v35 < 0 )
      {
        v42 = 0;
        v41 = v35;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_91;
        }
        PlaiWhoAmI(v53, 0x4000000000000800uLL);
        v36 = -1;
        do
          ++v36;
        while ( v53[v36] );
LABEL_17:
        v12 = &v41;
LABEL_8:
        EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)v12);
        goto LABEL_91;
      }
    }
  }
  PlaiVariantClear(&pvarg);
  if ( (int)PlaiReadXmlElement(L"SystemStateFile", 8, a2, &pvarg) < 0
    || (v37 = (*(__int64 (__fastcall **)(__int64, LONGLONG))(*(_QWORD *)v43 + 392LL))(v43, pvarg.llVal)) == 0
    || (v38 = PlaiAddValidation(a3, a4, L"SystemStateFile", v37), v10 = v38, v38 >= 0) )
  {
    v10 = 0;
    goto LABEL_91;
  }
  v42 = 0;
  v41 = v38;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v54, 0x4000000000000800uLL);
    v39 = -1;
    do
      ++v39;
    while ( v54[v39] );
    goto LABEL_17;
  }
LABEL_91:
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  return v10;
}

```

## disassembly

```asm
0x1800482e8  push    rbp
0x1800482ea  push    rbx
0x1800482eb  push    rsi
0x1800482ec  push    rdi
0x1800482ed  push    r12
0x1800482ef  push    r14
0x1800482f1  push    r15
0x1800482f3  lea     rbp, [rsp-4B0h]
0x1800482fb  sub     rsp, 5B0h
0x180048302  mov     rax, cs:__security_cookie
0x180048309  xor     rax, rsp
0x18004830c  mov     [rbp+4E0h+var_40], rax
0x180048313  mov     rbx, rcx
0x180048316  xorps   xmm0, xmm0
0x180048319  xor     eax, eax
0x18004831b  lea     rcx, [rbp+4E0h+pvarg]; pvarg
0x18004831f  xor     r15d, r15d
0x180048322  mov     qword ptr [rbp+4E0h+pvarg+10h], rax
0x180048326  movups  xmmword ptr [rbp+4E0h+pvarg], xmm0
0x18004832a  mov     [rbp+4E0h+var_560], r15
0x18004832e  mov     r14, r9
0x180048331  mov     rsi, r8
0x180048334  mov     rdi, rdx
0x180048337  call    cs:__imp_VariantInit
0x18004833d  mov     rax, [rbx]
0x180048340  lea     r8, [rbp+4E0h+var_560]
0x180048344  lea     rdx, IID_IConfigurationDataCollector
0x18004834b  mov     qword ptr [rbp+4E0h+pvarg+8], r15
0x18004834f  mov     rcx, rbx
0x180048352  mov     rax, [rax]
0x180048355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004835a  mov     ebx, eax
0x18004835c  test    eax, eax
0x18004835e  jns     loc_18004843C
0x180048364  cmp     dword ptr cs:xmmword_180169738, r15d
0x18004836b  mov     [rsp+5E0h+var_570], r15d
0x180048370  mov     [rsp+5E0h+var_568], eax
0x180048374  jz      loc_180048BD0
0x18004837a  mov     rdx, 4000000000000800h; unsigned __int64
0x180048384  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004838b  jz      loc_180048BD0
0x180048391  mov     rax, cs:qword_180169748
0x180048398  and     rax, rdx
0x18004839b  cmp     cs:qword_180169748, rax
0x1800483a2  jnz     loc_180048BD0
0x1800483a8  lea     rcx, [rbp+4E0h+var_540]; unsigned __int16 *
0x1800483ac  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800483b1  lea     rcx, [rbp+4E0h+var_540]
0x1800483b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800483b9  inc     rax
0x1800483bc  cmp     [rcx+rax*2], r15w
0x1800483c1  jnz     short loc_1800483B9
0x1800483c3  lea     ecx, [rax+rax]
0x1800483c6  add     rcx, 2
0x1800483ca  lea     rax, [rbp+4E0h+var_540]
0x1800483ce  mov     [rsp+5E0h+var_580], rcx
0x1800483d3  lea     r9, [rsp+5E0h+var_568]
0x1800483d8  lea     rcx, [rsp+5E0h+var_570]
0x1800483dd  mov     [rsp+5E0h+var_588], rax
0x1800483e2  lea     rdx, PLA_EVENT_ERROR
0x1800483e9  mov     [rsp+5E0h+var_590], 23h ; '#'
0x1800483f2  lea     rax, aConfigurationd_18; "ConfigurationDataCollector::SetXml"
0x1800483f9  mov     [rsp+5E0h+var_598], rax
0x1800483fe  mov     eax, 4
0x180048403  mov     [rsp+5E0h+var_5A0], rax
0x180048408  mov     [rsp+5E0h+var_5A8], rcx
0x18004840d  lea     rcx, qword_180147320
0x180048414  mov     [rsp+5E0h+var_5B0], 1
0x18004841d  mov     [rsp+5E0h+var_5B8], rcx
0x180048422  lea     r8d, [rax+1]
0x180048426  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004842d  mov     [rsp+5E0h+var_5C0], rax
0x180048432  call    EventingWriteEvent
0x180048437  jmp     loc_180048BD0
0x18004843c  lea     rcx, [rbp+4E0h+pvarg]; pvarg
0x180048440  call    cs:__imp_VariantClear
0x180048446  mov     edx, 0Bh; unsigned __int16
0x18004844b  mov     qword ptr [rbp+4E0h+pvarg+8], r15
0x18004844f  lea     r9, [rbp+4E0h+pvarg]; struct tagVARIANT *
0x180048453  mov     r8, rdi; struct IXMLDOMNode *
0x180048456  lea     rcx, aQuerynetworkad; "QueryNetworkAdapters"
0x18004845d  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x180048462  test    eax, eax
0x180048464  js      loc_180048522
0x18004846a  mov     rcx, [rbp+4E0h+var_560]
0x18004846e  movzx   edx, word ptr [rbp+4E0h+pvarg+8]
0x180048472  mov     rax, [rcx]
0x180048475  mov     rax, [rax+158h]
0x18004847c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048481  test    eax, eax
0x180048483  jz      loc_180048522
0x180048489  mov     r9d, eax; int
0x18004848c  lea     r8, aQuerynetworkad; "QueryNetworkAdapters"
0x180048493  mov     rdx, r14; unsigned __int16 *
0x180048496  mov     rcx, rsi; struct IValueMap *
0x180048499  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x18004849e  mov     ebx, eax
0x1800484a0  test    eax, eax
0x1800484a2  jns     short loc_180048522
0x1800484a4  cmp     dword ptr cs:xmmword_180169738, r15d
0x1800484ab  mov     [rsp+5E0h+var_568], r15d
0x1800484b0  mov     [rsp+5E0h+var_570], eax
0x1800484b4  jz      loc_180048BD0
0x1800484ba  mov     rdx, 4000000000000800h; unsigned __int64
0x1800484c4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800484cb  jz      loc_180048BD0
0x1800484d1  mov     rax, cs:qword_180169748
0x1800484d8  and     rax, rdx
0x1800484db  cmp     cs:qword_180169748, rax
0x1800484e2  jnz     loc_180048BD0
0x1800484e8  lea     rcx, [rbp+4E0h+var_4C0]; unsigned __int16 *
0x1800484ec  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800484f1  lea     rcx, [rbp+4E0h+var_4C0]
0x1800484f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800484f9  inc     rax
0x1800484fc  cmp     [rcx+rax*2], r15w
0x180048501  jnz     short loc_1800484F9
0x180048503  lea     ecx, [rax+rax]
0x180048506  lea     rax, [rbp+4E0h+var_4C0]
0x18004850a  add     rcx, 2
0x18004850e  lea     r9, [rsp+5E0h+var_570]
0x180048513  mov     [rsp+5E0h+var_580], rcx
0x180048518  lea     rcx, [rsp+5E0h+var_568]
0x18004851d  jmp     loc_1800483DD
0x180048522  lea     rcx, [rbp+4E0h+pvarg]; pvarg
0x180048526  call    cs:__imp_VariantClear
0x18004852c  mov     r12d, 2008h
0x180048532  mov     qword ptr [rbp+4E0h+pvarg+8], r15
0x180048536  mov     edx, r12d; unsigned __int16
0x180048539  lea     r9, [rbp+4E0h+pvarg]; struct tagVARIANT *
0x18004853d  mov     r8, rdi; struct IXMLDOMNode *
0x180048540  lea     rcx, aRegistrykey; "RegistryKey"
0x180048547  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x18004854c  test    eax, eax
0x18004854e  js      loc_180048602
0x180048554  mov     rcx, [rbp+4E0h+var_560]
0x180048558  mov     rdx, qword ptr [rbp+4E0h+pvarg+8]
0x18004855c  mov     rax, [rcx]
0x18004855f  mov     rax, [rax+168h]
0x180048566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004856b  test    eax, eax
0x18004856d  jz      loc_180048602
0x180048573  mov     r9d, eax; int
0x180048576  lea     r8, aRegistrykeys_0; "RegistryKeys"
0x18004857d  mov     rdx, r14; unsigned __int16 *
0x180048580  mov     rcx, rsi; struct IValueMap *
0x180048583  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x180048588  mov     ebx, eax
0x18004858a  test    eax, eax
0x18004858c  jns     short loc_180048602
0x18004858e  cmp     dword ptr cs:xmmword_180169738, r15d
0x180048595  mov     [rsp+5E0h+var_568], r15d
0x18004859a  mov     [rsp+5E0h+var_570], eax
0x18004859e  jz      loc_180048BD0
0x1800485a4  mov     rdx, 4000000000000800h; unsigned __int64
0x1800485ae  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800485b5  jz      loc_180048BD0
0x1800485bb  mov     rax, cs:qword_180169748
0x1800485c2  and     rax, rdx
0x1800485c5  cmp     cs:qword_180169748, rax
0x1800485cc  jnz     loc_180048BD0
0x1800485d2  lea     rcx, [rbp+4E0h+var_440]; unsigned __int16 *
0x1800485d9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800485de  lea     rcx, [rbp+4E0h+var_440]
0x1800485e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800485e9  inc     rax
0x1800485ec  cmp     [rcx+rax*2], r15w
0x1800485f1  jnz     short loc_1800485E9
0x1800485f3  lea     ecx, [rax+rax]
0x1800485f6  lea     rax, [rbp+4E0h+var_440]
0x1800485fd  jmp     loc_18004850A
0x180048602  lea     rcx, [rbp+4E0h+pvarg]; struct tagVARIANT *
0x180048606  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x18004860b  mov     edx, r12d; unsigned __int16
0x18004860e  lea     r9, [rbp+4E0h+pvarg]; struct tagVARIANT *
0x180048612  mov     r8, rdi; struct IXMLDOMNode *
0x180048615  lea     rcx, aFile_0; "File"
0x18004861c  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x180048621  test    eax, eax
0x180048623  js      loc_1800486D7
0x180048629  mov     rcx, [rbp+4E0h+var_560]
0x18004862d  mov     rdx, qword ptr [rbp+4E0h+pvarg+8]
0x180048631  mov     rax, [rcx]
0x180048634  mov     rax, [rax+138h]
0x18004863b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048640  test    eax, eax
0x180048642  jz      loc_1800486D7
0x180048648  mov     r9d, eax; int
0x18004864b  lea     r8, aFiles; "Files"
0x180048652  mov     rdx, r14; unsigned __int16 *
0x180048655  mov     rcx, rsi; struct IValueMap *
0x180048658  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x18004865d  mov     ebx, eax
0x18004865f  test    eax, eax
0x180048661  jns     short loc_1800486D7
0x180048663  cmp     dword ptr cs:xmmword_180169738, r15d
0x18004866a  mov     [rsp+5E0h+var_568], r15d
0x18004866f  mov     [rsp+5E0h+var_570], eax
0x180048673  jz      loc_180048BD0
0x180048679  mov     rdx, 4000000000000800h; unsigned __int64
0x180048683  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004868a  jz      loc_180048BD0
0x180048690  mov     rax, cs:qword_180169748
0x180048697  and     rax, rdx
0x18004869a  cmp     cs:qword_180169748, rax
0x1800486a1  jnz     loc_180048BD0
0x1800486a7  lea     rcx, [rbp+4E0h+var_3C0]; unsigned __int16 *
0x1800486ae  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800486b3  lea     rcx, [rbp+4E0h+var_3C0]
0x1800486ba  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800486be  inc     rax
0x1800486c1  cmp     [rcx+rax*2], r15w
0x1800486c6  jnz     short loc_1800486BE
0x1800486c8  lea     ecx, [rax+rax]
0x1800486cb  lea     rax, [rbp+4E0h+var_3C0]
0x1800486d2  jmp     loc_18004850A
0x1800486d7  lea     rcx, [rbp+4E0h+pvarg]; struct tagVARIANT *
0x1800486db  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800486e0  mov     edx, r12d; unsigned __int16
0x1800486e3  lea     r9, [rbp+4E0h+pvarg]; struct tagVARIANT *
0x1800486e7  mov     r8, rdi; struct IXMLDOMNode *
0x1800486ea  lea     rcx, aManagementquer; "ManagementQuery"
0x1800486f1  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x1800486f6  test    eax, eax
0x1800486f8  js      loc_1800487AC
0x1800486fe  mov     rcx, [rbp+4E0h+var_560]
0x180048702  mov     rdx, qword ptr [rbp+4E0h+pvarg+8]
0x180048706  mov     rax, [rcx]
0x180048709  mov     rax, [rax+148h]
0x180048710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048715  test    eax, eax
0x180048717  jz      loc_1800487AC
0x18004871d  mov     r9d, eax; int
0x180048720  lea     r8, aManagementquer_0; "ManagementQueries"
0x180048727  mov     rdx, r14; unsigned __int16 *
0x18004872a  mov     rcx, rsi; struct IValueMap *
0x18004872d  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x180048732  mov     ebx, eax
0x180048734  test    eax, eax
0x180048736  jns     short loc_1800487AC
0x180048738  cmp     dword ptr cs:xmmword_180169738, r15d
0x18004873f  mov     [rsp+5E0h+var_568], r15d
0x180048744  mov     [rsp+5E0h+var_570], eax
0x180048748  jz      loc_180048BD0
0x18004874e  mov     rdx, 4000000000000800h; unsigned __int64
0x180048758  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004875f  jz      loc_180048BD0
0x180048765  mov     rax, cs:qword_180169748
0x18004876c  and     rax, rdx
0x18004876f  cmp     cs:qword_180169748, rax
0x180048776  jnz     loc_180048BD0
0x18004877c  lea     rcx, [rbp+4E0h+var_340]; unsigned __int16 *
0x180048783  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180048788  lea     rcx, [rbp+4E0h+var_340]
0x18004878f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180048793  inc     rax
0x180048796  cmp     [rcx+rax*2], r15w
0x18004879b  jnz     short loc_180048793
0x18004879d  lea     ecx, [rax+rax]
0x1800487a0  lea     rax, [rbp+4E0h+var_340]
0x1800487a7  jmp     loc_18004850A
0x1800487ac  lea     rcx, [rbp+4E0h+pvarg]; struct tagVARIANT *
0x1800487b0  call    ?PlaiVariantClear@@YAJPEAUtagVARIANT@@@Z; PlaiVariantClear(tagVARIANT *)
0x1800487b5  mov     r12d, 3
0x1800487bb  lea     r9, [rbp+4E0h+pvarg]; struct tagVARIANT *
0x1800487bf  mov     edx, r12d; unsigned __int16
0x1800487c2  lea     rcx, aFilemaxcount; "FileMaxCount"
0x1800487c9  mov     r8, rdi; struct IXMLDOMNode *
0x1800487cc  call    ?PlaiReadXmlElement@@YAJPEBGGPEAUIXMLDOMNode@@PEAUtagVARIANT@@@Z; PlaiReadXmlElement(ushort const *,ushort,IXMLDOMNode *,tagVARIANT *)
0x1800487d1  test    eax, eax
0x1800487d3  js      loc_180048886
0x1800487d9  mov     rcx, [rbp+4E0h+var_560]
0x1800487dd  mov     edx, dword ptr [rbp+4E0h+pvarg+8]
0x1800487e0  mov     rax, [rcx]
0x1800487e3  mov     rax, [rax+108h]
0x1800487ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800487ef  test    eax, eax
0x1800487f1  jz      loc_180048886
0x1800487f7  mov     r9d, eax; int
0x1800487fa  lea     r8, aFilemaxcount; "FileMaxCount"
0x180048801  mov     rdx, r14; unsigned __int16 *
0x180048804  mov     rcx, rsi; struct IValueMap *
0x180048807  call    ?PlaiAddValidation@@YAJPEAUIValueMap@@PEBG1J@Z; PlaiAddValidation(IValueMap *,ushort const *,ushort const *,long)
0x18004880c  mov     ebx, eax
0x18004880e  test    eax, eax
0x180048810  jns     short loc_180048886
0x180048812  cmp     dword ptr cs:xmmword_180169738, r15d
0x180048819  mov     [rsp+5E0h+var_568], r15d
0x18004881e  mov     [rsp+5E0h+var_570], eax
0x180048822  jz      loc_180048BD0
0x180048828  mov     rdx, 4000000000000800h; unsigned __int64
0x180048832  test    qword ptr cs:xmmword_180169738+8, rdx
0x180048839  jz      loc_180048BD0
0x18004883f  mov     rax, cs:qword_180169748
0x180048846  and     rax, rdx
0x180048849  cmp     cs:qword_180169748, rax
0x180048850  jnz     loc_180048BD0
0x180048856  lea     rcx, [rbp+4E0h+var_2C0]; unsigned __int16 *
0x18004885d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180048862  lea     rcx, [rbp+4E0h+var_2C0]
  ... truncated ...
```
