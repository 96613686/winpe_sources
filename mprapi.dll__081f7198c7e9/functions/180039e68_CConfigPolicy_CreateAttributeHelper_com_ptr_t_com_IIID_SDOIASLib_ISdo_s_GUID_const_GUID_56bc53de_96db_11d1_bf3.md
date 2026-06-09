# CConfigPolicy::CreateAttributeHelper(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>>,_ATTRIBUTEID,_variant_t)

- ea: `0x180039e68`
- end: `0x18003a297`
- name: `?CreateAttributeHelper@CConfigPolicy@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@V?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@W4_ATTRIBUTEID@@V_variant_t@@@Z`
- size: `1071`
- prototype: `__int64 __fastcall(__int64, struct IUnknown **, struct IUnknown **, int, VARIANTARG *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180038f54`

## callees

- `0x180039e68`
- `0x18003a2a0`
- `0x18003dfc4`
- `0x18003e2ac`
- `0x18003edbc`
- `0x180050dbc`
- `0x180050e4c`
- `0x180050e60`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180039ec2`
- `OLEAUT32!__imp_SysAllocString` at `0x180039ec2`
- `OLEAUT32!__imp_VariantClear` at `0x18003a1e9`
- `OLEAUT32!__imp_VariantClear` at `0x18003a224`
- `OLEAUT32!__imp_VariantClear` at `0x18003a1e9`
- `OLEAUT32!__imp_VariantClear` at `0x18003a224`

## string_xrefs

- `0x180039f69`: `CConfigPolicy::CreateAttributeHelper(): Error %lx Couldn't create a new Attribute! (couldn't get IDispatch pointer)`
- `0x180039fe1`: `CConfigPolicy::CreateAttributeHelper(): Error %lx Couldn't convert the IDispatch pointer into an ISdoCollection pointer!`
- `0x18003a044`: `CConfigPolicy::CreateAttributeHelper(): Error %lx Couldn't add Attribute to the collection!`
- `0x18003a19b`: `CConfigPolicy::CreateAttributeHelper(): Error Array attributes are not supported`
- `0x18003a14e`: `CConfigPolicy::CreateAttributeHelper(): Error %lx Couldn't set the new Attribute's value!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::CreateAttributeHelper(
        __int64 a1,
        struct IUnknown **a2,
        struct IUnknown **a3,
        int a4,
        VARIANTARG *a5)
{
  BSTR v8; // rax
  struct IUnknown *v9; // rcx
  int AttributeObject; // eax
  int Collection; // edi
  const wchar_t *v12; // r8
  __int64 v13; // rdx
  struct IUnknown *v14; // rcx
  int v15; // ebx
  int v16; // ebx
  int v17; // ebx
  int v18; // ebx
  int v19; // ebx
  int v20; // ebx
  int v21; // ebx
  bool v22; // zf
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx
  int v27; // ebx
  int v28; // ebx
  int v29; // ebx
  __int128 v30; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  struct IUnknown *v32; // rbx
  int v33; // eax
  HRESULT v34; // eax
  HRESULT v35; // eax
  struct IUnknown *v37; // [rsp+38h] [rbp-D0h] BYREF
  struct IUnknown *v38; // [rsp+40h] [rbp-C8h] BYREF
  struct IUnknown *v39; // [rsp+48h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B8h] BYREF
  struct IUnknown **v41; // [rsp+68h] [rbp-A0h]
  struct IUnknown **v42; // [rsp+70h] [rbp-98h]
  VARIANTARG *v43; // [rsp+78h] [rbp-90h]
  __int128 v44; // [rsp+88h] [rbp-80h] BYREF
  IRecordInfo *v45; // [rsp+98h] [rbp-70h]
  int v46; // [rsp+A8h] [rbp-60h] BYREF
  char v47[2044]; // [rsp+ACh] [rbp-5Ch] BYREF

  v41 = a2;
  v42 = a3;
  v43 = a5;
  v8 = SysAllocString(&word_180059138);
  if ( !v8 )
    _com_issue_error(-2147024882);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)v8;
  v38 = 0;
  v39 = 0;
  v46 = 0;
  memset_0(v47, 0, sizeof(v47));
  v9 = *a3;
  v37 = v9;
  if ( v9 )
    ((void (__fastcall *)(struct IUnknown *))v9->lpVtbl->AddRef)(v9);
  AttributeObject = CConfigPolicy::CreateAttributeObject(
                      (_DWORD)v9,
                      a4,
                      (unsigned int)&v37,
                      (unsigned int)&v38,
                      (__int64)&pvarg);
  Collection = AttributeObject;
  if ( AttributeObject < 0 )
  {
    if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      LOWORD(v46) = 0;
      FormatRRASErrorString(
        &v46,
        L"CConfigPolicy::CreateAttributeHelper(): Error %lx Couldn't create a new Attribute! (couldn't get IDispatch pointer)",
        (unsigned int)AttributeObject);
LABEL_8:
      v12 = (const wchar_t *)&v46;
      v13 = xmmword_180078BA0;
LABEL_52:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gSdoUtilTemplateFunc)(
        gSdoUtilEtwContext,
        v13,
        v12);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  v14 = *a2;
  v37 = v14;
  if ( v14 )
    ((void (__fastcall *)(struct IUnknown *))v14->lpVtbl->AddRef)(v14);
  Collection = GetCollection(&v37, 1024, &v39);
  if ( Collection >= 0 )
  {
    v37 = v39;
    if ( v39 )
      ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->AddRef)(v39);
    Collection = AddObjectToCollection(pvarg.bstrVal, &v37, &v38);
    if ( Collection < 0 )
    {
      if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(
          &v46,
          L"CConfigPolicy::CreateAttributeHelper(): Error %lx Couldn't add Attribute to the collection!",
          (unsigned int)Collection);
        goto LABEL_8;
      }
      goto LABEL_53;
    }
    if ( a4 > 66 )
    {
      v23 = a4 - 67;
      if ( !v23 )
        goto LABEL_49;
      v24 = v23 - 2;
      if ( !v24 )
        goto LABEL_49;
      v25 = v24 - 12;
      if ( !v25 )
        goto LABEL_49;
      v26 = v25 - 4023;
      if ( !v26 )
        goto LABEL_49;
      v27 = v26 - 1;
      if ( !v27 )
        goto LABEL_49;
      v28 = v27 - 1;
      if ( !v28 )
        goto LABEL_49;
      v29 = v28 - 8;
      if ( !v29 )
        goto LABEL_49;
      v22 = v29 == 47;
    }
    else
    {
      if ( a4 == 66 )
        goto LABEL_49;
      v15 = a4 - 13;
      if ( !v15 )
        goto LABEL_49;
      v16 = v15 - 1;
      if ( !v16 )
        goto LABEL_49;
      v17 = v16 - 4;
      if ( !v17 )
        goto LABEL_49;
      v18 = v17 - 4;
      if ( !v18 )
        goto LABEL_49;
      v19 = v18 - 4;
      if ( !v19 )
        goto LABEL_49;
      v20 = v19 - 12;
      if ( !v20 )
        goto LABEL_49;
      v21 = v20 - 26;
      if ( !v21 )
        goto LABEL_49;
      v22 = v21 == 1;
    }
    if ( !v22 )
    {
      v30 = *(_OWORD *)&a5->vt;
      pRecInfo = a5->pRecInfo;
      v37 = v38;
      if ( v38 )
        ((void (__fastcall *)(struct IUnknown *))v38->lpVtbl->AddRef)(v38);
      v44 = v30;
      v45 = pRecInfo;
      Collection = PutSdoProperty(&v37, 1036, &v44);
      if ( Collection >= 0 )
      {
        v32 = *a2;
        if ( !*a2 )
          _com_issue_error(-2147467261);
        v33 = ((__int64 (__fastcall *)(struct IUnknown *))v32->lpVtbl[3].Release)(*a2);
        Collection = v33;
        if ( v33 < 0 )
          _com_issue_errorex(v33, v32, &GUID_56bc53de_96db_11d1_bf3f_000000000000);
      }
      else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
      {
        LOWORD(v46) = 0;
        FormatRRASErrorString(
          &v46,
          L"CConfigPolicy::CreateAttributeHelper(): Error %lx Couldn't set the new Attribute's value!",
          (unsigned int)Collection);
        goto LABEL_8;
      }
      goto LABEL_53;
    }
LABEL_49:
    Collection = -2147024809;
    if ( gIsSdoUtilEtwTracingAvailable )
    {
      v13 = xmmword_180078BA0;
      if ( (_QWORD)xmmword_180078BA0 )
      {
        v12 = L"CConfigPolicy::CreateAttributeHelper(): Error Array attributes are not supported";
        goto LABEL_52;
      }
    }
    goto LABEL_53;
  }
  if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    LOWORD(v46) = 0;
    FormatRRASErrorString(
      &v46,
      L"CConfigPolicy::CreateAttributeHelper(): Error %lx Couldn't convert the IDispatch pointer into an ISdoCollection pointer!",
      (unsigned int)Collection);
    goto LABEL_8;
  }
LABEL_53:
  if ( v39 )
    ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
  if ( v38 )
    ((void (__fastcall *)(struct IUnknown *))v38->lpVtbl->Release)(v38);
  v34 = VariantClear(&pvarg);
  if ( v34 < 0 )
    _com_issue_error(v34);
  if ( *a2 )
    ((void (__fastcall *)(struct IUnknown *))(*a2)->lpVtbl->Release)(*a2);
  if ( *a3 )
    ((void (__fastcall *)(struct IUnknown *))(*a3)->lpVtbl->Release)(*a3);
  v35 = VariantClear(a5);
  if ( v35 < 0 )
    _com_issue_error(v35);
  return (unsigned int)Collection;
}

```

## disassembly

```asm
0x180039e68  mov     rax, rsp
0x180039e6b  push    rbp
0x180039e6c  push    rbx
0x180039e6d  push    rsi
0x180039e6e  push    rdi
0x180039e6f  push    r13
0x180039e71  push    r14
0x180039e73  push    r15
0x180039e75  lea     rbp, [rax-808h]
0x180039e7c  sub     rsp, 8D0h
0x180039e83  movaps  xmmword ptr [rax-48h], xmm6
0x180039e87  movaps  xmmword ptr [rax-58h], xmm7
0x180039e8b  mov     rax, cs:__security_cookie
0x180039e92  xor     rax, rsp
0x180039e95  mov     [rbp+800h+var_60], rax
0x180039e9c  mov     ebx, r9d
0x180039e9f  mov     r15, r8
0x180039ea2  mov     rsi, rdx
0x180039ea5  mov     [rsp+900h+var_8A0], rdx
0x180039eaa  mov     [rsp+900h+var_898], r8
0x180039eaf  mov     r14, [rbp+800h+arg_20]
0x180039eb6  mov     [rsp+900h+var_890], r14
0x180039ebb  lea     rcx, word_180059138; psz
0x180039ec2  call    cs:__imp_SysAllocString
0x180039ec8  test    rax, rax
0x180039ecb  jz      loc_18003A279
0x180039ed1  mov     r13d, 8
0x180039ed7  mov     word ptr [rsp+900h+pvarg], r13w
0x180039edd  mov     qword ptr [rsp+900h+pvarg+8], rax
0x180039ee2  mov     [rsp+900h+var_8C8], 0
0x180039eeb  mov     [rsp+900h+var_8C0], 0
0x180039ef4  xor     eax, eax
0x180039ef6  mov     [rbp+800h+var_860], eax
0x180039ef9  xor     edx, edx; Val
0x180039efb  mov     r8d, 7FCh; Size
0x180039f01  lea     rcx, [rbp+800h+var_85C]; void *
0x180039f05  call    memset_0
0x180039f0a  mov     rcx, [r15]
0x180039f0d  mov     [rsp+900h+var_8D0], rcx
0x180039f12  test    rcx, rcx
0x180039f15  jz      short loc_180039F24
0x180039f17  mov     rax, [rcx]
0x180039f1a  mov     rax, [rax+8]
0x180039f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f23  nop
0x180039f24  lea     rax, [rsp+900h+pvarg]
0x180039f29  mov     [rsp+900h+var_8E0], rax
0x180039f2e  lea     r9, [rsp+900h+var_8C8]
0x180039f33  lea     r8, [rsp+900h+var_8D0]
0x180039f38  mov     edx, ebx
0x180039f3a  call    ?CreateAttributeObject@CConfigPolicy@@AEAAJW4_ATTRIBUTEID@@V?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@AEAUtagVARIANT@@@Z; CConfigPolicy::CreateAttributeObject(_ATTRIBUTEID,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &,tagVARIANT &)
0x180039f3f  mov     edi, eax
0x180039f41  test    eax, eax
0x180039f43  jns     short loc_180039F89
0x180039f45  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x180039f4c  jz      loc_18003A1B6
0x180039f52  cmp     qword ptr cs:xmmword_180078BA0, 0
0x180039f5a  jz      loc_18003A1B6
0x180039f60  xor     ecx, ecx
0x180039f62  mov     word ptr [rbp+800h+var_860], cx
0x180039f66  mov     r8d, eax
0x180039f69  lea     rdx, aCconfigpolicyC_9; "CConfigPolicy::CreateAttributeHelper():"...
0x180039f70  lea     rcx, [rbp+800h+var_860]
0x180039f74  call    FormatRRASErrorString
0x180039f79  lea     r8, [rbp+800h+var_860]
0x180039f7d  mov     rdx, qword ptr cs:xmmword_180078BA0
0x180039f84  jmp     loc_18003A1A2
0x180039f89  mov     rcx, [rsi]
0x180039f8c  mov     [rsp+900h+var_8D0], rcx
0x180039f91  test    rcx, rcx
0x180039f94  jz      short loc_180039FA3
0x180039f96  mov     rax, [rcx]
0x180039f99  mov     rax, [rax+8]
0x180039f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039fa2  nop
0x180039fa3  lea     r8, [rsp+900h+var_8C0]
0x180039fa8  mov     edx, 400h
0x180039fad  lea     rcx, [rsp+900h+var_8D0]
0x180039fb2  call    ?GetCollection@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JAEAV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z; GetCollection(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &)
0x180039fb7  mov     edi, eax
0x180039fb9  test    eax, eax
0x180039fbb  jns     short loc_180039FEA
0x180039fbd  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x180039fc4  jz      loc_18003A1B6
0x180039fca  cmp     qword ptr cs:xmmword_180078BA0, 0
0x180039fd2  jz      loc_18003A1B6
0x180039fd8  xor     eax, eax
0x180039fda  mov     word ptr [rbp+800h+var_860], ax
0x180039fde  mov     r8d, edi
0x180039fe1  lea     rdx, aCconfigpolicyC_1; "CConfigPolicy::CreateAttributeHelper():"...
0x180039fe8  jmp     short loc_180039F70
0x180039fea  mov     rcx, [rsp+900h+var_8C0]
0x180039fef  mov     [rsp+900h+var_8D0], rcx
0x180039ff4  test    rcx, rcx
0x180039ff7  jz      short loc_18003A006
0x180039ff9  mov     rax, [rcx]
0x180039ffc  mov     rax, [rax+8]
0x18003a000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a005  nop
0x18003a006  lea     r8, [rsp+900h+var_8C8]
0x18003a00b  lea     rdx, [rsp+900h+var_8D0]
0x18003a010  mov     rcx, qword ptr [rsp+900h+pvarg+8]; unsigned __int16 *
0x18003a015  call    ?AddObjectToCollection@@YAJPEAGV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z; AddObjectToCollection(ushort *,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &)
0x18003a01a  mov     edi, eax
0x18003a01c  test    eax, eax
0x18003a01e  jns     short loc_18003A050
0x18003a020  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003a027  jz      loc_18003A1B6
0x18003a02d  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003a035  jz      loc_18003A1B6
0x18003a03b  xor     eax, eax
0x18003a03d  mov     word ptr [rbp+800h+var_860], ax
0x18003a041  mov     r8d, edi
0x18003a044  lea     rdx, aCconfigpolicyC_12; "CConfigPolicy::CreateAttributeHelper():"...
0x18003a04b  jmp     loc_180039F70
0x18003a050  cmp     ebx, 42h ; 'B'
0x18003a053  jg      short loc_18003A09F
0x18003a055  jz      loc_18003A181
0x18003a05b  sub     ebx, 0Dh
0x18003a05e  jz      loc_18003A181
0x18003a064  sub     ebx, 1
0x18003a067  jz      loc_18003A181
0x18003a06d  sub     ebx, 4
0x18003a070  jz      loc_18003A181
0x18003a076  sub     ebx, 4
0x18003a079  jz      loc_18003A181
0x18003a07f  sub     ebx, 4
0x18003a082  jz      loc_18003A181
0x18003a088  sub     ebx, 0Ch
0x18003a08b  jz      loc_18003A181
0x18003a091  sub     ebx, 1Ah
0x18003a094  jz      loc_18003A181
0x18003a09a  cmp     ebx, 1
0x18003a09d  jmp     short loc_18003A0E4
0x18003a09f  sub     ebx, 43h ; 'C'
0x18003a0a2  jz      loc_18003A181
0x18003a0a8  sub     ebx, 2
0x18003a0ab  jz      loc_18003A181
0x18003a0b1  sub     ebx, 0Ch
0x18003a0b4  jz      loc_18003A181
0x18003a0ba  sub     ebx, 0FB7h
0x18003a0c0  jz      loc_18003A181
0x18003a0c6  sub     ebx, 1
0x18003a0c9  jz      loc_18003A181
0x18003a0cf  sub     ebx, 1
0x18003a0d2  jz      loc_18003A181
0x18003a0d8  sub     ebx, r13d
0x18003a0db  jz      loc_18003A181
0x18003a0e1  cmp     ebx, 2Fh ; '/'
0x18003a0e4  jz      loc_18003A181
0x18003a0ea  movups  xmm6, xmmword ptr [r14]
0x18003a0ee  movsd   xmm7, qword ptr [r14+10h]
0x18003a0f4  mov     rcx, [rsp+900h+var_8C8]
0x18003a0f9  mov     [rsp+900h+var_8D0], rcx
0x18003a0fe  test    rcx, rcx
0x18003a101  jz      short loc_18003A110
0x18003a103  mov     rax, [rcx]
0x18003a106  mov     rax, [rax+8]
0x18003a10a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a10f  nop
0x18003a110  movaps  [rbp+800h+var_880], xmm6
0x18003a114  movsd   [rbp+800h+var_870], xmm7
0x18003a119  lea     r8, [rbp+800h+var_880]
0x18003a11d  mov     edx, 40Ch
0x18003a122  lea     rcx, [rsp+900h+var_8D0]
0x18003a127  call    ?PutSdoProperty@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JUtagVARIANT@@@Z; PutSdoProperty(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,tagVARIANT)
0x18003a12c  mov     edi, eax
0x18003a12e  test    eax, eax
0x18003a130  jns     short loc_18003A15A
0x18003a132  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003a139  jz      short loc_18003A1B6
0x18003a13b  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003a143  jz      short loc_18003A1B6
0x18003a145  xor     eax, eax
0x18003a147  mov     word ptr [rbp+800h+var_860], ax
0x18003a14b  mov     r8d, edi
0x18003a14e  lea     rdx, aCconfigpolicyC_13; "CConfigPolicy::CreateAttributeHelper():"...
0x18003a155  jmp     loc_180039F70
0x18003a15a  mov     rbx, [rsi]
0x18003a15d  test    rbx, rbx
0x18003a160  jz      loc_18003A284
0x18003a166  mov     rax, [rbx]
0x18003a169  mov     rcx, rbx
0x18003a16c  mov     rax, [rax+58h]
0x18003a170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a175  mov     edi, eax
0x18003a177  test    eax, eax
0x18003a179  js      loc_18003A267
0x18003a17f  jmp     short loc_18003A1B6
0x18003a181  mov     edi, 80070057h
0x18003a186  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003a18d  jz      short loc_18003A1B6
0x18003a18f  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003a196  test    rdx, rdx
0x18003a199  jz      short loc_18003A1B6
0x18003a19b  lea     r8, aCconfigpolicyC_7; "CConfigPolicy::CreateAttributeHelper():"...
0x18003a1a2  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003a1a9  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003a1b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1b5  nop
0x18003a1b6  mov     rcx, [rsp+900h+var_8C0]
0x18003a1bb  test    rcx, rcx
0x18003a1be  jz      short loc_18003A1CD
0x18003a1c0  mov     rax, [rcx]
0x18003a1c3  mov     rax, [rax+10h]
0x18003a1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1cc  nop
0x18003a1cd  mov     rcx, [rsp+900h+var_8C8]
0x18003a1d2  test    rcx, rcx
0x18003a1d5  jz      short loc_18003A1E4
0x18003a1d7  mov     rax, [rcx]
0x18003a1da  mov     rax, [rax+10h]
0x18003a1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a1e3  nop
0x18003a1e4  lea     rcx, [rsp+900h+pvarg]; pvarg
0x18003a1e9  call    cs:__imp_VariantClear
0x18003a1ef  test    eax, eax
0x18003a1f1  js      loc_18003A28F
0x18003a1f7  mov     rcx, [rsi]
0x18003a1fa  test    rcx, rcx
0x18003a1fd  jz      short loc_18003A20C
0x18003a1ff  mov     rax, [rcx]
0x18003a202  mov     rax, [rax+10h]
0x18003a206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a20b  nop
0x18003a20c  mov     rcx, [r15]
0x18003a20f  test    rcx, rcx
0x18003a212  jz      short loc_18003A221
0x18003a214  mov     rax, [rcx]
0x18003a217  mov     rax, [rax+10h]
0x18003a21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a220  nop
0x18003a221  mov     rcx, r14; pvarg
0x18003a224  call    cs:__imp_VariantClear
0x18003a22a  test    eax, eax
0x18003a22c  js      short loc_18003A25F
0x18003a22e  mov     eax, edi
0x18003a230  mov     rcx, [rbp+800h+var_60]
0x18003a237  xor     rcx, rsp; StackCookie
0x18003a23a  call    __security_check_cookie
0x18003a23f  lea     r11, [rsp+900h+var_30]
0x18003a247  movaps  xmm6, xmmword ptr [r11-10h]
0x18003a24c  movaps  xmm7, xmmword ptr [r11-20h]
0x18003a251  mov     rsp, r11
0x18003a254  pop     r15
0x18003a256  pop     r14
0x18003a258  pop     r13
0x18003a25a  pop     rdi
0x18003a25b  pop     rsi
0x18003a25c  pop     rbx
0x18003a25d  pop     rbp
0x18003a25e  retn
0x18003a25f  mov     ecx, eax; int
0x18003a261  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003a267  lea     r8, _GUID_56bc53de_96db_11d1_bf3f_000000000000; struct _GUID *
0x18003a26e  mov     rdx, rbx; struct IUnknown *
0x18003a271  mov     ecx, eax; int
0x18003a273  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18003a279  mov     ecx, 8007000Eh; int
0x18003a27e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003a284  mov     ecx, 80004003h; int
0x18003a289  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003a28f  mov     ecx, eax; int
0x18003a291  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
