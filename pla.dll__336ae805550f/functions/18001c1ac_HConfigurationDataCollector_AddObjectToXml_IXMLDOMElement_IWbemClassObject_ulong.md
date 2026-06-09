# HConfigurationDataCollector::AddObjectToXml(IXMLDOMElement *,IWbemClassObject *,ulong)

- ea: `0x18001c1ac`
- end: `0x18001cbd8`
- name: `?AddObjectToXml@HConfigurationDataCollector@@AEAAJPEAUIXMLDOMElement@@PEAUIWbemClassObject@@K@Z`
- size: `2604`
- prototype: `__int64 __fastcall(HConfigurationDataCollector *__hidden this, struct IXMLDOMElement *, struct IWbemClassObject *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001c1ac`
- `0x18004cb4c`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180018420`
- `0x1800198b0`
- `0x18001b4fc`
- `0x18001c1ac`
- `0x18001cbe0`
- `0x18001d17c`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001c4f2`
- `msvcrt!_wcsicmp` at `0x18001c4f2`
- `OLEAUT32!__imp_VariantInit` at `0x18001c210`
- `OLEAUT32!__imp_VariantInit` at `0x18001c210`
- `OLEAUT32!__imp_VariantClear` at `0x18001c340`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb4f`
- `OLEAUT32!__imp_VariantClear` at `0x18001c340`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb4f`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001c4a5`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001c4a5`

## string_xrefs

- `0x18001c62b`: `HConfigurationDataCollector::AddObjectToXml`
- `0x18001c85b`: `HConfigurationDataCollector::AddObjectToXml`
- `0x18001cb02`: `HConfigurationDataCollector::AddObjectToXml`
- `0x18001c4eb`: `__RELPATH`
- `0x18001c9d6`: `managementObjectsRelativePath`

## pseudocode

```c
__int64 __fastcall HConfigurationDataCollector::AddObjectToXml(
        HConfigurationDataCollector *this,
        struct IXMLDOMElement *a2,
        struct IWbemClassObject *a3,
        unsigned int a4)
{
  struct IXMLDOMElement *v5; // rsi
  unsigned __int16 *v6; // r12
  struct IXMLDOMDocument *v10; // rcx
  int v11; // eax
  int v12; // ebx
  __int64 v13; // rax
  int *v14; // r9
  int *v15; // rcx
  int v16; // eax
  __int64 v17; // rax
  struct IWbemClassObjectVtbl *lpVtbl; // rax
  int v19; // eax
  struct IXMLDOMElement *v20; // rdi
  int v21; // eax
  int v22; // eax
  const unsigned __int16 *bstrVal; // rdi
  const char *v24; // rdx
  int v25; // r8d
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  const char *v34; // rdx
  int v35; // r8d
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  int v40; // [rsp+70h] [rbp-90h] BYREF
  int v41; // [rsp+78h] [rbp-88h] BYREF
  struct IXMLDOMElement *v42; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *String1; // [rsp+88h] [rbp-78h] BYREF
  int v44; // [rsp+90h] [rbp-70h] BYREF
  struct IXMLDOMElement *v45; // [rsp+98h] [rbp-68h] BYREF
  struct IWbemClassObject *v46; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 v48[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v49[64]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v50[64]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int16 v51[64]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int16 v52[64]; // [rsp+2C0h] [rbp+1C0h] BYREF
  unsigned __int16 v53[64]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v54[64]; // [rsp+3C0h] [rbp+2C0h] BYREF
  unsigned __int16 v55[64]; // [rsp+440h] [rbp+340h] BYREF
  unsigned __int16 v56[64]; // [rsp+4C0h] [rbp+3C0h] BYREF
  unsigned __int16 v57[64]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v58[64]; // [rsp+5C0h] [rbp+4C0h] BYREF
  unsigned __int16 v59[64]; // [rsp+640h] [rbp+540h] BYREF

  String1 = 0;
  v42 = 0;
  v45 = 0;
  v5 = 0;
  v46 = 0;
  v6 = 0;
  v44 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v10 = (struct IXMLDOMDocument *)*((_QWORD *)this + 32);
  pvarg.llVal = 0;
  v11 = PlaiAddItemToReport(v10, a2, &v42);
  v12 = v11;
  if ( v11 < 0 )
  {
    v40 = 0;
    v41 = v11;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_103;
    }
    PlaiWhoAmI(v48, 0x4000000000000800uLL);
    v13 = -1;
    do
      ++v13;
    while ( v48[v13] );
    v14 = &v41;
    v15 = &v40;
LABEL_102:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v14, 4, byte_180147320, 1, v15, 4);
LABEL_103:
    v20 = v42;
    goto LABEL_104;
  }
  v16 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD))a3->lpVtbl->BeginEnumeration)(a3, 0);
  v12 = v16;
  if ( v16 < 0 )
  {
    v41 = 0;
    v40 = v16;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_103;
    }
    PlaiWhoAmI(v49, 0x4000000000000800uLL);
    v17 = -1;
    do
      ++v17;
    while ( v49[v17] );
    goto LABEL_101;
  }
  while ( 1 )
  {
    PlaiFreeString(String1);
    String1 = 0;
    VariantClear(&pvarg);
    lpVtbl = a3->lpVtbl;
    pvarg.llVal = 0;
    v19 = ((__int64 (__fastcall *)(struct IWbemClassObject *, _QWORD, wchar_t **, VARIANTARG *, _QWORD, int *))lpVtbl->Next)(
            a3,
            0,
            &String1,
            &pvarg,
            0,
            &v44);
    v12 = v19;
    if ( v19 < 0 )
    {
      v41 = 0;
      v40 = v19;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_103;
      }
      PlaiWhoAmI(v59, 0x4000000000000800uLL);
      v38 = -1;
      do
        ++v38;
      while ( v59[v38] );
      goto LABEL_101;
    }
    if ( v19 == 262149 )
    {
      v32 = ((__int64 (__fastcall *)(struct IWbemClassObject *))a3->lpVtbl->EndEnumeration)(a3);
      v12 = v32;
      if ( v32 >= 0 )
      {
        if ( v6 || (PlaiFreeString(0), (v6 = PlaiAllocStringEx(L"#UNKNOWN#", v34, v35)) != 0) )
        {
          v20 = v42;
          v12 = PlaiAddDataToReportItem(
                  *((struct IXMLDOMDocument **)this + 32),
                  v42,
                  L"managementObjectsRelativePath",
                  v6);
          if ( v12 >= 0 )
            goto LABEL_104;
          v41 = 0;
          v40 = v12;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_104;
          }
          PlaiWhoAmI(v58, 0x4000000000000800uLL);
          v37 = -1;
          do
            ++v37;
          while ( v58[v37] );
LABEL_48:
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v40, 4, byte_180147320, 1, &v41, 4);
          goto LABEL_104;
        }
        v12 = -2147024882;
        v40 = -2147024882;
        v41 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_103;
        }
        PlaiWhoAmI(v57, 0x4000000000000800uLL);
        v36 = -1;
        do
          ++v36;
        while ( v57[v36] );
      }
      else
      {
        v41 = 0;
        v40 = v32;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_103;
        }
        PlaiWhoAmI(v56, 0x4000000000000800uLL);
        v33 = -1;
        do
          ++v33;
        while ( v56[v33] );
      }
LABEL_101:
      v14 = &v40;
      v15 = &v41;
      goto LABEL_102;
    }
    if ( v5 )
    {
      ((void (__fastcall *)(struct IXMLDOMElement *))v5->lpVtbl->Release)(v5);
      v45 = 0;
    }
    v20 = v42;
    v21 = PlaiAddItemToReport(*((struct IXMLDOMDocument **)this + 32), v42, &v45);
    v12 = v21;
    if ( v21 < 0 )
      break;
    v5 = v45;
    if ( v44 == 64 )
    {
      v12 = PlaiSetXmlAttribute(*((struct IXMLDOMDocument **)this + 32), v45, L"visible", L"false");
      if ( v12 < 0 )
      {
        v41 = 0;
        v40 = v12;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_104;
        }
        PlaiWhoAmI(v50, 0x4000000000000800uLL);
        v27 = -1;
        do
          ++v27;
        while ( v50[v27] );
        goto LABEL_48;
      }
    }
    v22 = PlaiAddDataToReportItem(*((struct IXMLDOMDocument **)this + 32), v5, L"managementObjectsProperty", String1);
    v12 = v22;
    if ( v22 < 0 )
    {
      v41 = 0;
      v40 = v22;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_104;
      }
      PlaiWhoAmI(v54, 0x4000000000000800uLL);
      v30 = -1;
      do
        ++v30;
      while ( v54[v30] );
      goto LABEL_48;
    }
    if ( pvarg.vt == 13 && a4 <= 2 )
    {
      if ( v46 )
      {
        ((void (__fastcall *)(struct IWbemClassObject *, _QWORD))v46->lpVtbl->Release)(v46, 0);
        v46 = 0;
      }
      if ( (**(int (__fastcall ***)(LONGLONG, GUID *, struct IWbemClassObject **))pvarg.llVal)(
             pvarg.llVal,
             &IID_IWbemClassObject,
             &v46) < 0 )
      {
        bstrVal = L"#UNKNOWN";
        goto LABEL_33;
      }
      v12 = HConfigurationDataCollector::AddObjectToXml(this, v5, v46, a4 + 1);
      if ( v12 < 0 )
      {
        v41 = 0;
        v40 = v12;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_104;
        }
        PlaiWhoAmI(v51, 0x4000000000000800uLL);
        v28 = -1;
        do
          ++v28;
        while ( v51[v28] );
        goto LABEL_48;
      }
      bstrVal = L"#Child object#";
    }
    else
    {
      bstrVal = L"#UNKNOWN#";
      if ( VariantChangeType(&pvarg, &pvarg, 0, 8u) >= 0 )
        bstrVal = pvarg.bstrVal;
    }
LABEL_33:
    v12 = PlaiAddDataToReportItem(*((struct IXMLDOMDocument **)this + 32), v5, L"managementObjectsValue", bstrVal);
    if ( v12 < 0 )
    {
      v41 = 0;
      v40 = v12;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_103;
      }
      PlaiWhoAmI(v53, 0x4000000000000800uLL);
      v29 = -1;
      do
        ++v29;
      while ( v53[v29] );
      goto LABEL_101;
    }
    if ( !v6 && !_wcsicmp(String1, L"__RELPATH") )
    {
      PlaiFreeString(0);
      v6 = PlaiAllocStringEx(bstrVal, v24, v25);
      if ( !v6 )
      {
        v12 = -2147024882;
        v40 = -2147024882;
        v41 = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_103;
        }
        PlaiWhoAmI(v52, 0x4000000000000800uLL);
        v26 = -1;
        do
          ++v26;
        while ( v52[v26] );
        goto LABEL_101;
      }
    }
  }
  v41 = 0;
  v40 = v21;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v55, 0x4000000000000800uLL);
    v31 = -1;
    do
      ++v31;
    while ( v55[v31] );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v40, 4, byte_180147320, 1, &v41, 4);
  }
  v5 = v45;
LABEL_104:
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  PlaiFreeString(String1);
  String1 = 0;
  PlaiFreeString(v6);
  if ( v5 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v5->lpVtbl->Release)(v5);
  if ( v20 )
    ((void (__fastcall *)(struct IXMLDOMElement *))v20->lpVtbl->Release)(v20);
  if ( v46 )
    ((void (__fastcall *)(struct IWbemClassObject *))v46->lpVtbl->Release)(v46);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001c1ac  push    rbp
0x18001c1ae  push    rbx
0x18001c1af  push    rsi
0x18001c1b0  push    rdi
0x18001c1b1  push    r12
0x18001c1b3  push    r13
0x18001c1b5  push    r14
0x18001c1b7  push    r15
0x18001c1b9  lea     rbp, [rsp-5D8h]
0x18001c1c1  sub     rsp, 6D8h
0x18001c1c8  mov     rax, cs:__security_cookie
0x18001c1cf  xor     rax, rsp
0x18001c1d2  mov     [rbp+610h+var_50], rax
0x18001c1d9  xor     edi, edi
0x18001c1db  mov     r14, rcx
0x18001c1de  xorps   xmm0, xmm0
0x18001c1e1  mov     [rbp+610h+String1], rdi
0x18001c1e5  xor     eax, eax
0x18001c1e7  mov     [rbp+610h+var_690], rdi
0x18001c1eb  lea     rcx, [rbp+610h+pvarg]; pvarg
0x18001c1ef  mov     [rbp+610h+var_678], rdi
0x18001c1f3  mov     esi, edi
0x18001c1f5  mov     [rbp+610h+var_670], rdi
0x18001c1f9  mov     r12d, edi
0x18001c1fc  mov     [rbp+610h+var_680], edi
0x18001c1ff  movups  xmmword ptr [rbp+610h+pvarg], xmm0
0x18001c203  mov     qword ptr [rbp+610h+pvarg+10h], rax
0x18001c207  mov     r13d, r9d
0x18001c20a  mov     r15, r8
0x18001c20d  mov     rbx, rdx
0x18001c210  call    cs:__imp_VariantInit
0x18001c216  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x18001c21d  lea     r8, [rbp+610h+var_690]; struct IXMLDOMElement **
0x18001c221  mov     rdx, rbx; struct IXMLDOMElement *
0x18001c224  mov     qword ptr [rbp+610h+pvarg+8], rdi
0x18001c228  call    ?PlaiAddItemToReport@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEAPEAU2@@Z; PlaiAddItemToReport(IXMLDOMDocument *,IXMLDOMElement *,IXMLDOMElement * *)
0x18001c22d  mov     ebx, eax
0x18001c22f  test    eax, eax
0x18001c231  jns     short loc_18001C2AE
0x18001c233  cmp     dword ptr cs:xmmword_180169738, edi
0x18001c239  mov     [rsp+710h+var_6A0], edi
0x18001c23d  mov     [rsp+710h+var_698], eax
0x18001c241  jz      loc_18001CB47
0x18001c247  mov     rdx, 4000000000000800h; unsigned __int64
0x18001c251  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001c258  jz      loc_18001CB47
0x18001c25e  mov     rax, cs:qword_180169748
0x18001c265  and     rax, rdx
0x18001c268  cmp     cs:qword_180169748, rax
0x18001c26f  jnz     loc_18001CB47
0x18001c275  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x18001c279  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001c27e  lea     rcx, [rbp+610h+var_650]
0x18001c282  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c286  inc     rax
0x18001c289  cmp     [rcx+rax*2], di
0x18001c28d  jnz     short loc_18001C286
0x18001c28f  lea     ecx, [rax+rax]
0x18001c292  add     rcx, 2
0x18001c296  lea     rax, [rbp+610h+var_650]
0x18001c29a  mov     [rsp+710h+var_6B0], rcx
0x18001c29f  lea     r9, [rsp+710h+var_698]
0x18001c2a4  lea     rcx, [rsp+710h+var_6A0]
0x18001c2a9  jmp     loc_18001CAED
0x18001c2ae  mov     rax, [r15]
0x18001c2b1  xor     edx, edx
0x18001c2b3  mov     rcx, r15
0x18001c2b6  mov     rax, [rax+40h]
0x18001c2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2bf  mov     ebx, eax
0x18001c2c1  test    eax, eax
0x18001c2c3  jns     short loc_18001C32F
0x18001c2c5  cmp     dword ptr cs:xmmword_180169738, edi
0x18001c2cb  mov     [rsp+710h+var_698], edi
0x18001c2cf  mov     [rsp+710h+var_6A0], eax
0x18001c2d3  jz      loc_18001CB47
0x18001c2d9  mov     rdx, 4000000000000800h; unsigned __int64
0x18001c2e3  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001c2ea  jz      loc_18001CB47
0x18001c2f0  mov     rax, cs:qword_180169748
0x18001c2f7  and     rax, rdx
0x18001c2fa  cmp     cs:qword_180169748, rax
0x18001c301  jnz     loc_18001CB47
0x18001c307  lea     rcx, [rbp+610h+var_5D0]; unsigned __int16 *
0x18001c30b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001c310  lea     rcx, [rbp+610h+var_5D0]
0x18001c314  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c318  inc     rax
0x18001c31b  cmp     [rcx+rax*2], di
0x18001c31f  jnz     short loc_18001C318
0x18001c321  lea     ecx, [rax+rax]
0x18001c324  lea     rax, [rbp+610h+var_5D0]
0x18001c328  jmp     loc_18001CADA
0x18001c32d  xor     edi, edi
0x18001c32f  mov     rcx, [rbp+610h+String1]; bstrString
0x18001c333  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x18001c338  lea     rcx, [rbp+610h+pvarg]; pvarg
0x18001c33c  mov     [rbp+610h+String1], rdi
0x18001c340  call    cs:__imp_VariantClear
0x18001c346  mov     rax, [r15]
0x18001c349  lea     rcx, [rbp+610h+var_680]
0x18001c34d  mov     [rsp+710h+var_6E8], rcx
0x18001c352  lea     r9, [rbp+610h+pvarg]
0x18001c356  lea     r8, [rbp+610h+String1]
0x18001c35a  mov     qword ptr [rbp+610h+pvarg+8], rdi
0x18001c35e  xor     edx, edx
0x18001c360  mov     [rsp+710h+var_6F0], rdi
0x18001c365  mov     rax, [rax+48h]
0x18001c369  mov     rcx, r15
0x18001c36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c371  mov     ebx, eax
0x18001c373  test    eax, eax
0x18001c375  js      loc_18001CA6E
0x18001c37b  cmp     eax, 40005h
0x18001c380  jz      loc_18001C8B0
0x18001c386  test    rsi, rsi
0x18001c389  jz      short loc_18001C39E
0x18001c38b  mov     rax, [rsi]
0x18001c38e  mov     rcx, rsi
0x18001c391  mov     rax, [rax+10h]
0x18001c395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c39a  mov     [rbp+610h+var_678], rdi
0x18001c39e  mov     rdi, [rbp+610h+var_690]
0x18001c3a2  lea     r8, [rbp+610h+var_678]; struct IXMLDOMElement **
0x18001c3a6  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x18001c3ad  mov     rdx, rdi; struct IXMLDOMElement *
0x18001c3b0  call    ?PlaiAddItemToReport@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEAPEAU2@@Z; PlaiAddItemToReport(IXMLDOMDocument *,IXMLDOMElement *,IXMLDOMElement * *)
0x18001c3b5  xor     esi, esi
0x18001c3b7  mov     ebx, eax
0x18001c3b9  test    eax, eax
0x18001c3bb  js      loc_18001C7CE
0x18001c3c1  cmp     [rbp+610h+var_680], 40h ; '@'
0x18001c3c5  mov     rsi, [rbp+610h+var_678]
0x18001c3c9  jnz     short loc_18001C3F4
0x18001c3cb  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x18001c3d2  lea     r9, aFalse; "false"
0x18001c3d9  lea     r8, aVisible; "visible"
0x18001c3e0  mov     rdx, rsi; struct IXMLDOMElement *
0x18001c3e3  call    ?PlaiSetXmlAttribute@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiSetXmlAttribute(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001c3e8  mov     ebx, eax
0x18001c3ea  xor     eax, eax
0x18001c3ec  test    ebx, ebx
0x18001c3ee  js      loc_18001C595
0x18001c3f4  mov     r9, [rbp+610h+String1]; unsigned __int16 *
0x18001c3f8  lea     r8, aManagementobje_2; "managementObjectsProperty"
0x18001c3ff  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x18001c406  mov     rdx, rsi; struct IXMLDOMElement *
0x18001c409  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001c40e  xor     edx, edx
0x18001c410  mov     ebx, eax
0x18001c412  test    eax, eax
0x18001c414  js      loc_18001C75B
0x18001c41a  lea     eax, [rdx+0Dh]
0x18001c41d  cmp     ax, word ptr [rbp+610h+pvarg]
0x18001c421  jnz     short loc_18001C495
0x18001c423  cmp     r13d, 2
0x18001c427  ja      short loc_18001C495
0x18001c429  mov     rcx, [rbp+610h+var_670]
0x18001c42d  test    rcx, rcx
0x18001c430  jz      short loc_18001C446
0x18001c432  mov     rax, [rcx]
0x18001c435  mov     rax, [rax+10h]
0x18001c439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c43e  mov     [rbp+610h+var_670], 0
0x18001c446  mov     rcx, qword ptr [rbp+610h+pvarg+8]
0x18001c44a  lea     r8, [rbp+610h+var_670]
0x18001c44e  lea     rdx, IID_IWbemClassObject
0x18001c455  mov     rax, [rcx]
0x18001c458  mov     rax, [rax]
0x18001c45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c460  test    eax, eax
0x18001c462  jns     short loc_18001C46D
0x18001c464  lea     rdi, aUnknown_0; "#UNKNOWN"
0x18001c46b  jmp     short loc_18001C4B9
0x18001c46d  mov     r8, [rbp+610h+var_670]; struct IWbemClassObject *
0x18001c471  lea     r9d, [r13+1]; unsigned int
0x18001c475  mov     rdx, rsi; struct IXMLDOMElement *
0x18001c478  mov     rcx, r14; this
0x18001c47b  call    ?AddObjectToXml@HConfigurationDataCollector@@AEAAJPEAUIXMLDOMElement@@PEAUIWbemClassObject@@K@Z; HConfigurationDataCollector::AddObjectToXml(IXMLDOMElement *,IWbemClassObject *,ulong)
0x18001c480  mov     ebx, eax
0x18001c482  xor     eax, eax
0x18001c484  test    ebx, ebx
0x18001c486  js      loc_18001C675
0x18001c48c  lea     rdi, aChildObject; "#Child object#"
0x18001c493  jmp     short loc_18001C4B9
0x18001c495  mov     r9w, 8; vt
0x18001c49a  lea     rdx, [rbp+610h+pvarg]; pvarSrc
0x18001c49e  xor     r8d, r8d; wFlags
0x18001c4a1  lea     rcx, [rbp+610h+pvarg]; pvargDest
0x18001c4a5  call    cs:__imp_VariantChangeType
0x18001c4ab  test    eax, eax
0x18001c4ad  lea     rdi, aUnknown; "#UNKNOWN#"
0x18001c4b4  cmovns  rdi, qword ptr [rbp+610h+pvarg+8]
0x18001c4b9  mov     rcx, [r14+100h]; struct IXMLDOMDocument *
0x18001c4c0  lea     r8, aManagementobje_3; "managementObjectsValue"
0x18001c4c7  mov     r9, rdi; unsigned __int16 *
0x18001c4ca  mov     rdx, rsi; struct IXMLDOMElement *
0x18001c4cd  call    ?PlaiAddDataToReportItem@@YAJPEAUIXMLDOMDocument@@PEAUIXMLDOMElement@@PEBG2@Z; PlaiAddDataToReportItem(IXMLDOMDocument *,IXMLDOMElement *,ushort const *,ushort const *)
0x18001c4d2  mov     ebx, eax
0x18001c4d4  xor     eax, eax
0x18001c4d6  test    ebx, ebx
0x18001c4d8  js      loc_18001C6E8
0x18001c4de  test    r12, r12
0x18001c4e1  jnz     loc_18001C32D
0x18001c4e7  mov     rcx, [rbp+610h+String1]; String1
0x18001c4eb  lea     rdx, aRelpath; "__RELPATH"
0x18001c4f2  call    cs:__imp__wcsicmp
0x18001c4f8  xor     ecx, ecx; bstrString
0x18001c4fa  test    eax, eax
0x18001c4fc  jnz     loc_18001C32D
0x18001c502  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x18001c507  mov     rcx, rdi; unsigned __int16 *
0x18001c50a  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18001c50f  xor     edi, edi
0x18001c511  mov     r12, rax
0x18001c514  test    rax, rax
0x18001c517  jnz     loc_18001C32F
0x18001c51d  cmp     dword ptr cs:xmmword_180169738, edi
0x18001c523  mov     eax, 8007000Eh
0x18001c528  mov     ebx, eax
0x18001c52a  mov     [rsp+710h+var_6A0], eax
0x18001c52e  mov     [rsp+710h+var_698], edi
0x18001c532  jz      loc_18001CB47
0x18001c538  mov     rdx, 4000000000000800h; unsigned __int64
0x18001c542  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001c549  jz      loc_18001CB47
0x18001c54f  mov     rax, cs:qword_180169748
0x18001c556  and     rax, rdx
0x18001c559  cmp     cs:qword_180169748, rax
0x18001c560  jnz     loc_18001CB47
0x18001c566  lea     rcx, [rbp+610h+var_450]; unsigned __int16 *
0x18001c56d  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001c572  lea     rcx, [rbp+610h+var_450]
0x18001c579  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c57d  inc     rax
0x18001c580  cmp     [rcx+rax*2], di
0x18001c584  jnz     short loc_18001C57D
0x18001c586  lea     ecx, [rax+rax]
0x18001c589  lea     rax, [rbp+610h+var_450]
0x18001c590  jmp     loc_18001CADA
0x18001c595  cmp     dword ptr cs:xmmword_180169738, eax
0x18001c59b  mov     [rsp+710h+var_698], eax
0x18001c59f  mov     [rsp+710h+var_6A0], ebx
0x18001c5a3  jz      loc_18001CB4B
0x18001c5a9  mov     rdx, 4000000000000800h; unsigned __int64
0x18001c5b3  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001c5ba  jz      loc_18001CB4B
0x18001c5c0  mov     rax, cs:qword_180169748
0x18001c5c7  and     rax, rdx
0x18001c5ca  cmp     cs:qword_180169748, rax
0x18001c5d1  jnz     loc_18001CB4B
0x18001c5d7  lea     rcx, [rbp+610h+var_550]; unsigned __int16 *
0x18001c5de  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001c5e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c5e7  lea     rdx, [rbp+610h+var_550]
0x18001c5ee  xor     ecx, ecx
0x18001c5f0  inc     rax
0x18001c5f3  cmp     [rdx+rax*2], cx
0x18001c5f7  jnz     short loc_18001C5F0
0x18001c5f9  lea     ecx, [rax+rax]
0x18001c5fc  lea     rax, [rbp+610h+var_550]
0x18001c603  add     rcx, 2
0x18001c607  lea     r9, [rsp+710h+var_6A0]
0x18001c60c  mov     [rsp+710h+var_6B0], rcx
0x18001c611  lea     rdx, PLA_EVENT_ERROR
0x18001c618  mov     [rsp+710h+var_6B8], rax
0x18001c61d  lea     rcx, [rsp+710h+var_698]
0x18001c622  mov     [rsp+710h+var_6C0], 2Ch ; ','
0x18001c62b  lea     rax, aHconfiguration_10; "HConfigurationDataCollector::AddObjectT"...
0x18001c632  mov     [rsp+710h+var_6C8], rax
0x18001c637  mov     eax, 4
0x18001c63c  mov     [rsp+710h+var_6D0], rax
0x18001c641  mov     [rsp+710h+var_6D8], rcx
0x18001c646  lea     rcx, byte_180147320
0x18001c64d  mov     [rsp+710h+var_6E0], 1
0x18001c656  mov     [rsp+710h+var_6E8], rcx
0x18001c65b  lea     r8d, [rax+1]
0x18001c65f  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18001c666  mov     [rsp+710h+var_6F0], rax
0x18001c66b  call    EventingWriteEvent
0x18001c670  jmp     loc_18001CB4B
0x18001c675  cmp     dword ptr cs:xmmword_180169738, eax
0x18001c67b  mov     [rsp+710h+var_698], eax
0x18001c67f  mov     [rsp+710h+var_6A0], ebx
0x18001c683  jz      loc_18001CB4B
0x18001c689  mov     rdx, 4000000000000800h; unsigned __int64
0x18001c693  test    qword ptr cs:xmmword_180169738+8, rdx
0x18001c69a  jz      loc_18001CB4B
0x18001c6a0  mov     rax, cs:qword_180169748
0x18001c6a7  and     rax, rdx
0x18001c6aa  cmp     cs:qword_180169748, rax
0x18001c6b1  jnz     loc_18001CB4B
0x18001c6b7  lea     rcx, [rbp+610h+var_4D0]; unsigned __int16 *
0x18001c6be  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18001c6c3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c6c7  lea     rdx, [rbp+610h+var_4D0]
0x18001c6ce  xor     ecx, ecx
0x18001c6d0  inc     rax
0x18001c6d3  cmp     [rdx+rax*2], cx
0x18001c6d7  jnz     short loc_18001C6D0
  ... truncated ...
```
