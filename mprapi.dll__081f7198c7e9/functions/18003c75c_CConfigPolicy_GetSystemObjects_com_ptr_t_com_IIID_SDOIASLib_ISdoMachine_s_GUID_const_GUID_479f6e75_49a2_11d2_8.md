# CConfigPolicy::GetSystemObjects(_com_ptr_t<_com_IIID<SDOIASLib::ISdoMachine,&__s_GUID const _GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519>>,tagVARIANT,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &)

- ea: `0x18003c75c`
- end: `0x18003ca75`
- name: `?GetSystemObjects@CConfigPolicy@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UISdoMachine@SDOIASLib@@$1?_GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519@@3U__s_GUID@@B@@@@UtagVARIANT@@AEAV?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@3@Z`
- size: `793`
- prototype: `__int64 __fastcall(__int64, struct IUnknown **, const VARIANTARG *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003c278`

## callees

- `0x18003b70c`
- `0x18003c75c`
- `0x18003e2ac`
- `0x18003e498`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003c7b2`
- `OLEAUT32!__imp_VariantInit` at `0x18003c7b2`
- `OLEAUT32!__imp_VariantClear` at `0x18003ca21`
- `OLEAUT32!__imp_VariantClear` at `0x18003ca21`
- `OLEAUT32!__imp_VariantCopy` at `0x18003c7c0`
- `OLEAUT32!__imp_VariantCopy` at `0x18003c7c0`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003c811`
- `OLEAUT32!__imp_VariantChangeType` at `0x18003c811`

## string_xrefs

- `0x18003c8e5`: `CConfigPolicy::GetSystemObjects(): Error %lx Couldn't get a Dictionary object for Attributes manipulation!`
- `0x18003c93d`: `CConfigPolicy::GetSystemObjects(): Error %lx Couldn't get a Service SDO object for the IAS Service!`
- `0x18003c993`: `CConfigPolicy::GetSystemObjects(): Error %lx Couldn't get the Policies Collection!`
- `0x18003c9e1`: `CConfigPolicy::GetSystemObjects(): Error %lx Couldn't get the Profiles Collection!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::GetSystemObjects(
        __int64 a1,
        struct IUnknown **a2,
        const VARIANTARG *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6)
{
  HRESULT v10; // eax
  __int64 v11; // rdx
  const wchar_t *v12; // r8
  int IasServiceObject; // ebx
  unsigned int v14; // esi
  unsigned int v15; // r14d
  struct IUnknown *v16; // rcx
  int DictionaryObject; // eax
  struct IUnknown *v18; // rcx
  struct IUnknown **v19; // rdi
  const wchar_t *v20; // rdx
  struct IUnknown *v21; // rcx
  struct IUnknown *v22; // rcx
  HRESULT v23; // eax
  struct IUnknown *v25; // [rsp+20h] [rbp-E0h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v27; // [rsp+40h] [rbp-C0h]
  struct IUnknown **v28; // [rsp+48h] [rbp-B8h]
  int v29; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v30[2044]; // [rsp+54h] [rbp-ACh] BYREF

  v28 = a2;
  v27 = a6;
  VariantInit(&pvarg);
  v10 = VariantCopy(&pvarg, a3);
  if ( v10 < 0 )
    _com_issue_error(v10);
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  if ( pvarg.vt != 10 && pvarg.vt != 1 )
  {
    if ( VariantChangeType(&pvarg, &pvarg, 0, 3u) < 0 )
    {
      if ( !gIsSdoUtilEtwTracingAvailable )
        goto LABEL_9;
      v11 = xmmword_180078BA0;
      if ( !(_QWORD)xmmword_180078BA0 )
        goto LABEL_9;
      v12 = L"GetSystemObjects(): Failed to convert datatype to numeric value!";
LABEL_8:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gSdoUtilTemplateFunc)(
        gSdoUtilEtwContext,
        v11,
        v12);
LABEL_9:
      IasServiceObject = -2147024809;
      goto LABEL_43;
    }
    if ( !pvarg.lVal )
    {
      v14 = 1030;
      v15 = 1031;
      goto LABEL_17;
    }
    if ( pvarg.lVal != 1 )
    {
      if ( !gIsSdoUtilEtwTracingAvailable )
        goto LABEL_9;
      v11 = xmmword_180078BA0;
      if ( !(_QWORD)xmmword_180078BA0 )
        goto LABEL_9;
      v12 = L"GetSystemObjects(): policy parameters is invalid!";
      goto LABEL_8;
    }
  }
  v14 = 1025;
  v15 = 1026;
LABEL_17:
  v16 = *a2;
  v25 = v16;
  if ( v16 )
    ((void (__fastcall *)(struct IUnknown *))v16->lpVtbl->AddRef)(v16);
  DictionaryObject = CConfigPolicy::GetDictionaryObject((__int64)v16, &v25, a4);
  IasServiceObject = DictionaryObject;
  if ( DictionaryObject >= 0 )
  {
    v18 = *a2;
    v25 = v18;
    if ( v18 )
      ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->AddRef)(v18);
    v19 = (struct IUnknown **)(a1 + 16);
    IasServiceObject = GetIasServiceObject(&v25, (__int64 *)(a1 + 16));
    if ( IasServiceObject >= 0 )
    {
      v21 = *v19;
      v25 = v21;
      if ( v21 )
        ((void (__fastcall *)(struct IUnknown *))v21->lpVtbl->AddRef)(v21);
      IasServiceObject = GetCollection(&v25, v14, a5);
      if ( IasServiceObject >= 0 )
      {
        v22 = *v19;
        v25 = v22;
        if ( v22 )
          ((void (__fastcall *)(struct IUnknown *))v22->lpVtbl->AddRef)(v22);
        IasServiceObject = GetCollection(&v25, v15, v27);
        if ( IasServiceObject >= 0 || !gIsSdoUtilEtwTracingAvailable || !(_QWORD)xmmword_180078BA0 )
          goto LABEL_43;
        v20 = L"CConfigPolicy::GetSystemObjects(): Error %lx Couldn't get the Profiles Collection!";
      }
      else
      {
        if ( !gIsSdoUtilEtwTracingAvailable || !(_QWORD)xmmword_180078BA0 )
          goto LABEL_43;
        v20 = L"CConfigPolicy::GetSystemObjects(): Error %lx Couldn't get the Policies Collection!";
      }
    }
    else
    {
      if ( !gIsSdoUtilEtwTracingAvailable || !(_QWORD)xmmword_180078BA0 )
        goto LABEL_43;
      v20 = L"CConfigPolicy::GetSystemObjects(): Error %lx Couldn't get a Service SDO object for the IAS Service!";
    }
    LOWORD(v29) = 0;
    FormatRRASErrorString(&v29, v20, (unsigned int)IasServiceObject);
    goto LABEL_42;
  }
  if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    LOWORD(v29) = 0;
    FormatRRASErrorString(
      &v29,
      L"CConfigPolicy::GetSystemObjects(): Error %lx Couldn't get a Dictionary object for Attributes manipulation!",
      (unsigned int)DictionaryObject);
LABEL_42:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
      gSdoUtilEtwContext,
      xmmword_180078BA0,
      &v29);
  }
LABEL_43:
  v23 = VariantClear(&pvarg);
  if ( v23 < 0 )
    _com_issue_error(v23);
  if ( *a2 )
    ((void (__fastcall *)(struct IUnknown *))(*a2)->lpVtbl->Release)(*a2);
  return (unsigned int)IasServiceObject;
}

```

## disassembly

```asm
0x18003c75c  push    rbp
0x18003c75e  push    rbx
0x18003c75f  push    rsi
0x18003c760  push    rdi
0x18003c761  push    r12
0x18003c763  push    r13
0x18003c765  push    r14
0x18003c767  push    r15
0x18003c769  lea     rbp, [rsp-768h]
0x18003c771  sub     rsp, 868h
0x18003c778  mov     rax, cs:__security_cookie
0x18003c77f  xor     rax, rsp
0x18003c782  mov     [rbp+7A0h+var_50], rax
0x18003c789  mov     rdi, r9
0x18003c78c  mov     rbx, r8
0x18003c78f  mov     r15, rdx
0x18003c792  mov     r13, rcx
0x18003c795  mov     [rsp+8A0h+var_858], rdx
0x18003c79a  mov     r12, [rbp+7A0h+arg_20]
0x18003c7a1  mov     rax, [rbp+7A0h+arg_28]
0x18003c7a8  mov     [rsp+8A0h+var_860], rax
0x18003c7ad  lea     rcx, [rsp+8A0h+pvarg]; pvarg
0x18003c7b2  call    cs:__imp_VariantInit
0x18003c7b8  mov     rdx, rbx; pvargSrc
0x18003c7bb  lea     rcx, [rsp+8A0h+pvarg]; pvargDest
0x18003c7c0  call    cs:__imp_VariantCopy
0x18003c7c6  test    eax, eax
0x18003c7c8  js      loc_18003CA6D
0x18003c7ce  xor     eax, eax
0x18003c7d0  mov     [rsp+8A0h+var_850], eax
0x18003c7d4  xor     edx, edx; Val
0x18003c7d6  mov     r8d, 7FCh; Size
0x18003c7dc  lea     rcx, [rsp+8A0h+var_84C]; void *
0x18003c7e1  call    memset_0
0x18003c7e6  cmp     word ptr [rsp+8A0h+pvarg], 0Ah
0x18003c7ec  jz      loc_18003C88A
0x18003c7f2  cmp     word ptr [rsp+8A0h+pvarg], 1
0x18003c7f8  jz      loc_18003C88A
0x18003c7fe  mov     r9d, 3; vt
0x18003c804  xor     r8d, r8d; wFlags
0x18003c807  lea     rdx, [rsp+8A0h+pvarg]; pvarSrc
0x18003c80c  lea     rcx, [rsp+8A0h+pvarg]; pvargDest
0x18003c811  call    cs:__imp_VariantChangeType
0x18003c817  test    eax, eax
0x18003c819  jns     short loc_18003C854
0x18003c81b  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003c822  jz      short loc_18003C84A
0x18003c824  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003c82b  test    rdx, rdx
0x18003c82e  jz      short loc_18003C84A
0x18003c830  lea     r8, aGetsystemobjec; "GetSystemObjects(): Failed to convert d"...
0x18003c837  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003c83e  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003c845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c84a  mov     ebx, 80070057h
0x18003c84f  jmp     loc_18003CA1C
0x18003c854  mov     ecx, dword ptr [rsp+8A0h+pvarg+8]
0x18003c858  test    ecx, ecx
0x18003c85a  jz      short loc_18003C87F
0x18003c85c  cmp     ecx, 1
0x18003c85f  jz      short loc_18003C88A
0x18003c861  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003c868  jz      short loc_18003C84A
0x18003c86a  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003c871  test    rdx, rdx
0x18003c874  jz      short loc_18003C84A
0x18003c876  lea     r8, aGetsystemobjec_0; "GetSystemObjects(): policy parameters i"...
0x18003c87d  jmp     short loc_18003C837
0x18003c87f  mov     esi, 406h
0x18003c884  lea     r14d, [rsi+1]
0x18003c888  jmp     short loc_18003C893
0x18003c88a  mov     esi, 401h
0x18003c88f  lea     r14d, [rsi+1]
0x18003c893  mov     rcx, [r15]
0x18003c896  mov     [rsp+8A0h+var_880], rcx
0x18003c89b  test    rcx, rcx
0x18003c89e  jz      short loc_18003C8AD
0x18003c8a0  mov     rax, [rcx]
0x18003c8a3  mov     rax, [rax+8]
0x18003c8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8ac  nop
0x18003c8ad  mov     r8, rdi
0x18003c8b0  lea     rdx, [rsp+8A0h+var_880]
0x18003c8b5  call    ?GetDictionaryObject@CConfigPolicy@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UISdoMachine@SDOIASLib@@$1?_GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@@Z; CConfigPolicy::GetDictionaryObject(_com_ptr_t<_com_IIID<SDOIASLib::ISdoMachine,&__s_GUID const _GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>> &)
0x18003c8ba  mov     ebx, eax
0x18003c8bc  test    eax, eax
0x18003c8be  jns     short loc_18003C8F1
0x18003c8c0  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003c8c7  jz      loc_18003CA1C
0x18003c8cd  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003c8d5  jz      loc_18003CA1C
0x18003c8db  xor     ecx, ecx
0x18003c8dd  mov     word ptr [rsp+8A0h+var_850], cx
0x18003c8e2  mov     r8d, eax
0x18003c8e5  lea     rdx, aCconfigpolicyG_13; "CConfigPolicy::GetSystemObjects(): Erro"...
0x18003c8ec  jmp     loc_18003C9F2
0x18003c8f1  mov     rcx, [r15]
0x18003c8f4  mov     [rsp+8A0h+var_880], rcx
0x18003c8f9  test    rcx, rcx
0x18003c8fc  jz      short loc_18003C90B
0x18003c8fe  mov     rax, [rcx]
0x18003c901  mov     rax, [rax+8]
0x18003c905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c90a  nop
0x18003c90b  lea     rdi, [r13+10h]
0x18003c90f  mov     rdx, rdi
0x18003c912  lea     rcx, [rsp+8A0h+var_880]
0x18003c917  call    ?GetIasServiceObject@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdoMachine@SDOIASLib@@$1?_GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z; GetIasServiceObject(_com_ptr_t<_com_IIID<SDOIASLib::ISdoMachine,&__s_GUID const _GUID_479f6e75_49a2_11d2_8eca_00c04fc2f519>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &)
0x18003c91c  mov     ebx, eax
0x18003c91e  test    eax, eax
0x18003c920  jns     short loc_18003C949
0x18003c922  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003c929  jz      loc_18003CA1C
0x18003c92f  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003c937  jz      loc_18003CA1C
0x18003c93d  lea     rdx, aCconfigpolicyG_18; "CConfigPolicy::GetSystemObjects(): Erro"...
0x18003c944  jmp     loc_18003C9E8
0x18003c949  mov     rcx, [rdi]
0x18003c94c  mov     [rsp+8A0h+var_880], rcx
0x18003c951  test    rcx, rcx
0x18003c954  jz      short loc_18003C963
0x18003c956  mov     rax, [rcx]
0x18003c959  mov     rax, [rax+8]
0x18003c95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c962  nop
0x18003c963  mov     r8, r12
0x18003c966  mov     edx, esi
0x18003c968  lea     rcx, [rsp+8A0h+var_880]
0x18003c96d  call    ?GetCollection@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JAEAV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z; GetCollection(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &)
0x18003c972  mov     ebx, eax
0x18003c974  test    eax, eax
0x18003c976  jns     short loc_18003C99C
0x18003c978  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003c97f  jz      loc_18003CA1C
0x18003c985  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003c98d  jz      loc_18003CA1C
0x18003c993  lea     rdx, aCconfigpolicyG_22; "CConfigPolicy::GetSystemObjects(): Erro"...
0x18003c99a  jmp     short loc_18003C9E8
0x18003c99c  mov     rcx, [rdi]
0x18003c99f  mov     [rsp+8A0h+var_880], rcx
0x18003c9a4  test    rcx, rcx
0x18003c9a7  jz      short loc_18003C9B6
0x18003c9a9  mov     rax, [rcx]
0x18003c9ac  mov     rax, [rax+8]
0x18003c9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9b5  nop
0x18003c9b6  mov     r8, [rsp+8A0h+var_860]
0x18003c9bb  mov     edx, r14d
0x18003c9be  lea     rcx, [rsp+8A0h+var_880]
0x18003c9c3  call    ?GetCollection@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JAEAV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z; GetCollection(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &)
0x18003c9c8  mov     ebx, eax
0x18003c9ca  test    eax, eax
0x18003c9cc  jns     short loc_18003CA1C
0x18003c9ce  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003c9d5  jz      short loc_18003CA1C
0x18003c9d7  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003c9df  jz      short loc_18003CA1C
0x18003c9e1  lea     rdx, aCconfigpolicyG_1; "CConfigPolicy::GetSystemObjects(): Erro"...
0x18003c9e8  xor     eax, eax
0x18003c9ea  mov     word ptr [rsp+8A0h+var_850], ax
0x18003c9ef  mov     r8d, ebx
0x18003c9f2  lea     rcx, [rsp+8A0h+var_850]
0x18003c9f7  call    FormatRRASErrorString
0x18003c9fc  lea     r8, [rsp+8A0h+var_850]
0x18003ca01  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003ca08  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003ca0f  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003ca16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca1b  nop
0x18003ca1c  lea     rcx, [rsp+8A0h+pvarg]; pvarg
0x18003ca21  call    cs:__imp_VariantClear
0x18003ca27  test    eax, eax
0x18003ca29  js      short loc_18003CA65
0x18003ca2b  mov     rcx, [r15]
0x18003ca2e  test    rcx, rcx
0x18003ca31  jz      short loc_18003CA40
0x18003ca33  mov     rax, [rcx]
0x18003ca36  mov     rax, [rax+10h]
0x18003ca3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca3f  nop
0x18003ca40  mov     eax, ebx
0x18003ca42  mov     rcx, [rbp+7A0h+var_50]
0x18003ca49  xor     rcx, rsp; StackCookie
0x18003ca4c  call    __security_check_cookie
0x18003ca51  add     rsp, 868h
0x18003ca58  pop     r15
0x18003ca5a  pop     r14
0x18003ca5c  pop     r13
0x18003ca5e  pop     r12
0x18003ca60  pop     rdi
0x18003ca61  pop     rsi
0x18003ca62  pop     rbx
0x18003ca63  pop     rbp
0x18003ca64  retn
0x18003ca65  mov     ecx, eax; int
0x18003ca67  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003ca6d  mov     ecx, eax; int
0x18003ca6f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
