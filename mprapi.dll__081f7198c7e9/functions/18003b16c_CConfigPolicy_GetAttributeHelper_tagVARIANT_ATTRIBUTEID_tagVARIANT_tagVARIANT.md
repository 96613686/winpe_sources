# CConfigPolicy::GetAttributeHelper(tagVARIANT,_ATTRIBUTEID,tagVARIANT,tagVARIANT &)

- ea: `0x18003b16c`
- end: `0x18003b504`
- name: `?GetAttributeHelper@CConfigPolicy@@AEAAJUtagVARIANT@@W4_ATTRIBUTEID@@0AEAU2@@Z`
- size: `920`
- prototype: `__int64 __fastcall(CConfigPolicy *this, struct tagVARIANT *, unsigned int, struct tagVARIANT *, VARIANTARG *pvargDest)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003af50`

## callees

- `0x18003a2a0`
- `0x18003b16c`
- `0x18003b50c`
- `0x18003bfb8`
- `0x18003e2ac`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003b1ae`
- `OLEAUT32!__imp_VariantInit` at `0x18003b1b9`
- `OLEAUT32!__imp_VariantInit` at `0x18003b1ae`
- `OLEAUT32!__imp_VariantInit` at `0x18003b1b9`
- `OLEAUT32!__imp_VariantClear` at `0x18003b4b9`
- `OLEAUT32!__imp_VariantClear` at `0x18003b4c7`
- `OLEAUT32!__imp_VariantClear` at `0x18003b4b9`
- `OLEAUT32!__imp_VariantClear` at `0x18003b4c7`
- `OLEAUT32!__imp_VariantCopy` at `0x18003b3c4`
- `OLEAUT32!__imp_VariantCopy` at `0x18003b3c4`

## string_xrefs

- `0x18003b293`: `CConfigPolicy::GetAttributeHelper(): Error %lx while trying to locate Radius Profile!`
- `0x18003b2f4`: `CConfigPolicy::GetAttributeHelper(): Error %lx Couldn't create an example Attribute!`
- `0x18003b350`: `CConfigPolicy::GetAttributeHelper(): Error %lx Couldn't convert the IDispatch pointer into an ISdoCollection pointer!`
- `0x18003b3b4`: `CConfigPolicy::GetAttributeHelper(): Error %lx Couldn't get the Attribute's value!`
- `0x18003b3e2`: `CConfigPolicy::GetAttributeHelper(): Error %lx Couldn't copy the Attribute's value!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::GetAttributeHelper(
        CConfigPolicy *this,
        struct tagVARIANT *a2,
        unsigned int a3,
        struct tagVARIANT *a4,
        VARIANTARG *pvargDest)
{
  int v8; // esi
  int PolicyAndProfile; // eax
  __int64 v10; // rcx
  unsigned int v11; // edi
  __int64 (__fastcall **v12)(_QWORD, GUID *, __int64 *); // rbx
  const wchar_t *v13; // rdx
  __int64 (__fastcall **v14)(_QWORD, GUID *, __int64 *); // rcx
  HRESULT v15; // eax
  HRESULT v16; // eax
  __int64 (__fastcall **v18)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  __int16 v19; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall **v20)(_QWORD, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  __int64 (__fastcall **v21)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall **v22)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h] BYREF
  __int64 v24; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h] BYREF
  __int64 v26; // [rsp+90h] [rbp-70h] BYREF
  VARIANTARG v27; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG pvargSrc; // [rsp+D8h] [rbp-28h] BYREF
  struct tagVARIANT v30; // [rsp+F0h] [rbp-10h] BYREF
  int v31; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v32[2044]; // [rsp+114h] [rbp+14h] BYREF

  v8 = (int)this;
  VariantInit(&pvarg);
  VariantInit(&pvargSrc);
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  v20 = 0;
  v19 = 0;
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v30 = *a4;
  v27 = *a2;
  PolicyAndProfile = CConfigPolicy::GetPolicyAndProfile(
                       v8,
                       (unsigned int)&v27,
                       3,
                       (unsigned int)&v30,
                       (__int64)&v26,
                       (__int64)&v25,
                       (__int64)&v24,
                       (__int64)&v21,
                       (__int64)&v22,
                       (__int64)&v19);
  v11 = PolicyAndProfile;
  v12 = v22;
  if ( PolicyAndProfile >= 0 )
  {
    v18 = v22;
    if ( v22 )
      (*((void (__fastcall **)(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *)))*v22 + 1))(v22);
    PolicyAndProfile = CConfigPolicy::CreateAttributeObject(v10, a3, &v18, &v23, (__int64)&pvarg);
    v11 = PolicyAndProfile;
    if ( PolicyAndProfile >= 0 )
    {
      v18 = v21;
      if ( v21 )
        (*((void (__fastcall **)(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *)))*v21 + 1))(v21);
      PolicyAndProfile = GetCollection(&v18, 1024, &v20);
      v11 = PolicyAndProfile;
      if ( PolicyAndProfile >= 0 )
      {
        v14 = v20;
        v18 = v20;
        if ( v20 )
          (*((void (__fastcall **)(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *)))*v20 + 1))(v20);
        v27 = pvarg;
        PolicyAndProfile = CConfigPolicy::GetAttributeValue(v14, &v27, &v18, &pvargSrc);
        v11 = PolicyAndProfile;
        if ( PolicyAndProfile >= 0 )
        {
          PolicyAndProfile = VariantCopy(pvargDest, &pvargSrc);
          v11 = PolicyAndProfile;
          if ( PolicyAndProfile < 0 && gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
          {
            v13 = L"CConfigPolicy::GetAttributeHelper(): Error %lx Couldn't copy the Attribute's value!";
            goto LABEL_27;
          }
        }
        else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
        {
          v13 = L"CConfigPolicy::GetAttributeHelper(): Error %lx Couldn't get the Attribute's value!";
          goto LABEL_27;
        }
      }
      else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
      {
        v13 = L"CConfigPolicy::GetAttributeHelper(): Error %lx Couldn't convert the IDispatch pointer into an ISdoCollection pointer!";
        goto LABEL_27;
      }
    }
    else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      v13 = L"CConfigPolicy::GetAttributeHelper(): Error %lx Couldn't create an example Attribute!";
      goto LABEL_27;
    }
  }
  else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    v13 = L"CConfigPolicy::GetAttributeHelper(): Error %lx while trying to locate Radius Profile!";
LABEL_27:
    LOWORD(v31) = 0;
    FormatRRASErrorString(&v31, v13, (unsigned int)PolicyAndProfile);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
      gSdoUtilEtwContext,
      xmmword_180078BA0,
      &v31);
  }
  if ( v20 )
    (*((void (__fastcall **)(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *)))*v20 + 2))(v20);
  if ( v12 )
    (*((void (__fastcall **)(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *)))*v12 + 2))(v12);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v21 )
    (*((void (__fastcall **)(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *)))*v21 + 2))(v21);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  v15 = VariantClear(&pvargSrc);
  if ( v15 < 0 )
    _com_issue_error(v15);
  v16 = VariantClear(&pvarg);
  if ( v16 < 0 )
    _com_issue_error(v16);
  return v11;
}

```

## disassembly

```asm
0x18003b16c  push    rbp
0x18003b16e  push    rbx
0x18003b16f  push    rsi
0x18003b170  push    rdi
0x18003b171  push    r12
0x18003b173  push    r14
0x18003b175  push    r15
0x18003b177  lea     rbp, [rsp-820h]
0x18003b17f  sub     rsp, 920h
0x18003b186  mov     rax, cs:__security_cookie
0x18003b18d  xor     rax, rsp
0x18003b190  mov     [rbp+850h+var_40], rax
0x18003b197  mov     rbx, r9
0x18003b19a  mov     r14d, r8d
0x18003b19d  mov     rdi, rdx
0x18003b1a0  mov     rsi, rcx
0x18003b1a3  mov     r15, [rbp+850h+pvargDest]
0x18003b1aa  lea     rcx, [rbp+850h+pvarg]; pvarg
0x18003b1ae  call    cs:__imp_VariantInit
0x18003b1b4  nop
0x18003b1b5  lea     rcx, [rbp+850h+pvargSrc]; pvarg
0x18003b1b9  call    cs:__imp_VariantInit
0x18003b1bf  nop
0x18003b1c0  xor     r12d, r12d
0x18003b1c3  mov     [rbp+850h+var_8C0], r12
0x18003b1c7  mov     [rbp+850h+var_8C8], r12
0x18003b1cb  mov     [rbp+850h+var_8D0], r12
0x18003b1cf  mov     [rsp+950h+var_8E8], r12
0x18003b1d4  mov     [rsp+950h+var_8D8], r12
0x18003b1d9  mov     [rsp+950h+var_8E0], r12
0x18003b1de  mov     [rsp+950h+var_8F0], r12
0x18003b1e3  mov     [rsp+950h+var_8F8], r12w
0x18003b1e9  mov     [rbp+850h+var_840], r12d
0x18003b1ed  xor     edx, edx; Val
0x18003b1ef  mov     r8d, 7FCh; Size
0x18003b1f5  lea     rcx, [rbp+850h+var_83C]; void *
0x18003b1f9  call    memset_0
0x18003b1fe  movaps  xmm0, xmmword ptr [rbx]
0x18003b201  movaps  [rbp+850h+var_860], xmm0
0x18003b205  movsd   xmm1, qword ptr [rbx+10h]
0x18003b20a  movsd   [rbp+850h+var_850], xmm1
0x18003b20f  movaps  xmm0, xmmword ptr [rdi]
0x18003b212  movaps  [rbp+850h+var_8B0], xmm0
0x18003b216  movsd   xmm1, qword ptr [rdi+10h]
0x18003b21b  movsd   [rbp+850h+var_8A0], xmm1
0x18003b220  lea     rax, [rsp+950h+var_8F8]
0x18003b225  mov     [rsp+950h+var_908], rax
0x18003b22a  lea     rax, [rsp+950h+var_8E0]
0x18003b22f  mov     [rsp+950h+var_910], rax
0x18003b234  lea     rax, [rsp+950h+var_8E8]
0x18003b239  mov     [rsp+950h+var_918], rax
0x18003b23e  lea     rax, [rbp+850h+var_8D0]
0x18003b242  mov     [rsp+950h+var_920], rax
0x18003b247  lea     rax, [rbp+850h+var_8C8]
0x18003b24b  mov     [rsp+950h+var_928], rax
0x18003b250  lea     rax, [rbp+850h+var_8C0]
0x18003b254  mov     [rsp+950h+var_930], rax
0x18003b259  lea     r9, [rbp+850h+var_860]
0x18003b25d  lea     r8d, [r12+3]
0x18003b262  lea     rdx, [rbp+850h+var_8B0]
0x18003b266  mov     rcx, rsi
0x18003b269  call    ?GetPolicyAndProfile@CConfigPolicy@@AEAAJUtagVARIANT@@K0AEAV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@1AEAV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@2AEAV?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@AEAF@Z; CConfigPolicy::GetPolicyAndProfile(tagVARIANT,ulong,tagVARIANT,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>> &,short &)
0x18003b26e  mov     edi, eax
0x18003b270  mov     rbx, [rsp+950h+var_8E0]
0x18003b275  test    eax, eax
0x18003b277  jns     short loc_18003B29F
0x18003b279  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r12d; int gIsSdoUtilEtwTracingAvailable
0x18003b280  jz      loc_18003B419
0x18003b286  cmp     qword ptr cs:xmmword_180078BA0, r12
0x18003b28d  jz      loc_18003B419
0x18003b293  lea     rdx, aCconfigpolicyG_16; "CConfigPolicy::GetAttributeHelper(): Er"...
0x18003b29a  jmp     loc_18003B3E9
0x18003b29f  mov     [rsp+950h+var_900], rbx
0x18003b2a4  test    rbx, rbx
0x18003b2a7  jz      short loc_18003B2B9
0x18003b2a9  mov     rax, [rbx]
0x18003b2ac  mov     rcx, rbx
0x18003b2af  mov     rax, [rax+8]
0x18003b2b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2b8  nop
0x18003b2b9  lea     rax, [rbp+850h+pvarg]
0x18003b2bd  mov     [rsp+950h+var_930], rax
0x18003b2c2  lea     r9, [rsp+950h+var_8D8]
0x18003b2c7  lea     r8, [rsp+950h+var_900]
0x18003b2cc  mov     edx, r14d
0x18003b2cf  call    ?CreateAttributeObject@CConfigPolicy@@AEAAJW4_ATTRIBUTEID@@V?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@AEAUtagVARIANT@@@Z; CConfigPolicy::CreateAttributeObject(_ATTRIBUTEID,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &,tagVARIANT &)
0x18003b2d4  mov     edi, eax
0x18003b2d6  test    eax, eax
0x18003b2d8  jns     short loc_18003B300
0x18003b2da  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r12d; int gIsSdoUtilEtwTracingAvailable
0x18003b2e1  jz      loc_18003B419
0x18003b2e7  cmp     qword ptr cs:xmmword_180078BA0, r12
0x18003b2ee  jz      loc_18003B419
0x18003b2f4  lea     rdx, aCconfigpolicyG_23; "CConfigPolicy::GetAttributeHelper(): Er"...
0x18003b2fb  jmp     loc_18003B3E9
0x18003b300  mov     rcx, [rsp+950h+var_8E8]
0x18003b305  mov     [rsp+950h+var_900], rcx
0x18003b30a  test    rcx, rcx
0x18003b30d  jz      short loc_18003B31C
0x18003b30f  mov     rax, [rcx]
0x18003b312  mov     rax, [rax+8]
0x18003b316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b31b  nop
0x18003b31c  lea     r8, [rsp+950h+var_8F0]
0x18003b321  mov     edx, 400h
0x18003b326  lea     rcx, [rsp+950h+var_900]
0x18003b32b  call    ?GetCollection@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JAEAV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z; GetCollection(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &)
0x18003b330  mov     edi, eax
0x18003b332  test    eax, eax
0x18003b334  jns     short loc_18003B35C
0x18003b336  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r12d; int gIsSdoUtilEtwTracingAvailable
0x18003b33d  jz      loc_18003B419
0x18003b343  cmp     qword ptr cs:xmmword_180078BA0, r12
0x18003b34a  jz      loc_18003B419
0x18003b350  lea     rdx, aCconfigpolicyG; "CConfigPolicy::GetAttributeHelper(): Er"...
0x18003b357  jmp     loc_18003B3E9
0x18003b35c  mov     rcx, [rsp+950h+var_8F0]
0x18003b361  mov     [rsp+950h+var_900], rcx
0x18003b366  test    rcx, rcx
0x18003b369  jz      short loc_18003B378
0x18003b36b  mov     rax, [rcx]
0x18003b36e  mov     rax, [rax+8]
0x18003b372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b377  nop
0x18003b378  movups  xmm0, xmmword ptr [rbp+850h+pvarg]
0x18003b37c  movaps  [rbp+850h+var_8B0], xmm0
0x18003b380  movsd   xmm1, qword ptr [rbp+850h+pvarg+10h]
0x18003b385  movsd   [rbp+850h+var_8A0], xmm1
0x18003b38a  lea     r9, [rbp+850h+pvargSrc]
0x18003b38e  lea     r8, [rsp+950h+var_900]
0x18003b393  lea     rdx, [rbp+850h+var_8B0]
0x18003b397  call    ?GetAttributeValue@CConfigPolicy@@AEAAJUtagVARIANT@@V?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@AEAU2@@Z; CConfigPolicy::GetAttributeValue(tagVARIANT,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>,tagVARIANT &)
0x18003b39c  mov     edi, eax
0x18003b39e  test    eax, eax
0x18003b3a0  jns     short loc_18003B3BD
0x18003b3a2  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r12d; int gIsSdoUtilEtwTracingAvailable
0x18003b3a9  jz      short loc_18003B419
0x18003b3ab  cmp     qword ptr cs:xmmword_180078BA0, r12
0x18003b3b2  jz      short loc_18003B419
0x18003b3b4  lea     rdx, aCconfigpolicyG_20; "CConfigPolicy::GetAttributeHelper(): Er"...
0x18003b3bb  jmp     short loc_18003B3E9
0x18003b3bd  lea     rdx, [rbp+850h+pvargSrc]; pvargSrc
0x18003b3c1  mov     rcx, r15; pvargDest
0x18003b3c4  call    cs:__imp_VariantCopy
0x18003b3ca  mov     edi, eax
0x18003b3cc  test    eax, eax
0x18003b3ce  jns     short loc_18003B419
0x18003b3d0  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r12d; int gIsSdoUtilEtwTracingAvailable
0x18003b3d7  jz      short loc_18003B419
0x18003b3d9  cmp     qword ptr cs:xmmword_180078BA0, r12
0x18003b3e0  jz      short loc_18003B419
0x18003b3e2  lea     rdx, aCconfigpolicyG_12; "CConfigPolicy::GetAttributeHelper(): Er"...
0x18003b3e9  mov     word ptr [rbp+850h+var_840], r12w
0x18003b3ee  mov     r8d, eax
0x18003b3f1  lea     rcx, [rbp+850h+var_840]
0x18003b3f5  call    FormatRRASErrorString
0x18003b3fa  lea     r8, [rbp+850h+var_840]
0x18003b3fe  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003b405  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003b40c  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003b413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b418  nop
0x18003b419  mov     rcx, [rsp+950h+var_8F0]
0x18003b41e  test    rcx, rcx
0x18003b421  jz      short loc_18003B430
0x18003b423  mov     rax, [rcx]
0x18003b426  mov     rax, [rax+10h]
0x18003b42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b42f  nop
0x18003b430  test    rbx, rbx
0x18003b433  jz      short loc_18003B445
0x18003b435  mov     rax, [rbx]
0x18003b438  mov     rcx, rbx
0x18003b43b  mov     rax, [rax+10h]
0x18003b43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b444  nop
0x18003b445  mov     rcx, [rsp+950h+var_8D8]
0x18003b44a  test    rcx, rcx
0x18003b44d  jz      short loc_18003B45C
0x18003b44f  mov     rax, [rcx]
0x18003b452  mov     rax, [rax+10h]
0x18003b456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b45b  nop
0x18003b45c  mov     rcx, [rsp+950h+var_8E8]
0x18003b461  test    rcx, rcx
0x18003b464  jz      short loc_18003B473
0x18003b466  mov     rax, [rcx]
0x18003b469  mov     rax, [rax+10h]
0x18003b46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b472  nop
0x18003b473  mov     rcx, [rbp+850h+var_8D0]
0x18003b477  test    rcx, rcx
0x18003b47a  jz      short loc_18003B489
0x18003b47c  mov     rax, [rcx]
0x18003b47f  mov     rax, [rax+10h]
0x18003b483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b488  nop
0x18003b489  mov     rcx, [rbp+850h+var_8C8]
0x18003b48d  test    rcx, rcx
0x18003b490  jz      short loc_18003B49F
0x18003b492  mov     rax, [rcx]
0x18003b495  mov     rax, [rax+10h]
0x18003b499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b49e  nop
0x18003b49f  mov     rcx, [rbp+850h+var_8C0]
0x18003b4a3  test    rcx, rcx
0x18003b4a6  jz      short loc_18003B4B5
0x18003b4a8  mov     rax, [rcx]
0x18003b4ab  mov     rax, [rax+10h]
0x18003b4af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4b4  nop
0x18003b4b5  lea     rcx, [rbp+850h+pvargSrc]; pvarg
0x18003b4b9  call    cs:__imp_VariantClear
0x18003b4bf  test    eax, eax
0x18003b4c1  js      short loc_18003B4FC
0x18003b4c3  lea     rcx, [rbp+850h+pvarg]; pvarg
0x18003b4c7  call    cs:__imp_VariantClear
0x18003b4cd  test    eax, eax
0x18003b4cf  js      short loc_18003B4F4
0x18003b4d1  mov     eax, edi
0x18003b4d3  mov     rcx, [rbp+850h+var_40]
0x18003b4da  xor     rcx, rsp; StackCookie
0x18003b4dd  call    __security_check_cookie
0x18003b4e2  add     rsp, 920h
0x18003b4e9  pop     r15
0x18003b4eb  pop     r14
0x18003b4ed  pop     r12
0x18003b4ef  pop     rdi
0x18003b4f0  pop     rsi
0x18003b4f1  pop     rbx
0x18003b4f2  pop     rbp
0x18003b4f3  retn
0x18003b4f4  mov     ecx, eax; int
0x18003b4f6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003b4fc  mov     ecx, eax; int
0x18003b4fe  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
