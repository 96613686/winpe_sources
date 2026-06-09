# CConfigPolicy::AddVariantAttributeHelper(tagVARIANT,_ATTRIBUTEID,tagVARIANT,tagVARIANT)

- ea: `0x180038f54`
- end: `0x1800391dc`
- name: `?AddVariantAttributeHelper@CConfigPolicy@@AEAAJUtagVARIANT@@W4_ATTRIBUTEID@@00@Z`
- size: `648`
- prototype: `__int64 __fastcall(CConfigPolicy *this, struct tagVARIANT *, int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800384d0`
- `0x180038db0`

## callees

- `0x180038f54`
- `0x180039e68`
- `0x18003bfb8`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180039087`
- `OLEAUT32!__imp_VariantInit` at `0x180039087`
- `OLEAUT32!__imp_VariantCopy` at `0x180039094`
- `OLEAUT32!__imp_VariantCopy` at `0x180039094`

## string_xrefs

- `0x180039077`: `CConfigPolicy::AddVariantAttribute(): Error %lx while trying to locate Radius Policy!`
- `0x180039115`: `CConfigPolicy::AddVariantAttribute(): Error %lx Couldn't create requested Attribute!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::AddVariantAttributeHelper(
        CConfigPolicy *this,
        struct tagVARIANT *a2,
        int a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *a5)
{
  int v8; // esi
  int PolicyAndProfile; // eax
  int v10; // edi
  __int64 v11; // rbx
  HRESULT v12; // eax
  int v13; // ecx
  __int16 v15; // [rsp+50h] [rbp-B0h] BYREF
  int v16[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+60h] [rbp-A0h] BYREF
  int v18[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v19; // [rsp+70h] [rbp-90h] BYREF
  __int64 v20; // [rsp+78h] [rbp-88h] BYREF
  __int64 v21; // [rsp+80h] [rbp-80h] BYREF
  __int64 v22; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  struct tagVARIANT v24; // [rsp+B0h] [rbp-50h] BYREF
  int v25; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v26[2044]; // [rsp+D4h] [rbp-2Ch] BYREF

  v8 = (int)this;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  v17 = 0;
  v19 = 0;
  v15 = 0;
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  pvarg = *a5;
  v24 = *a2;
  PolicyAndProfile = CConfigPolicy::GetPolicyAndProfile(
                       v8,
                       (unsigned int)&v24,
                       3,
                       (unsigned int)&pvarg,
                       (__int64)&v22,
                       (__int64)&v21,
                       (__int64)&v20,
                       (__int64)&v17,
                       (__int64)&v19,
                       (__int64)&v15);
  v10 = PolicyAndProfile;
  v11 = v19;
  if ( PolicyAndProfile >= 0 )
  {
    VariantInit(&pvarg);
    v12 = VariantCopy(&pvarg, a4);
    if ( v12 < 0 )
      _com_issue_error(v12);
    *(_QWORD *)v18 = v11;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    v13 = v17;
    *(_QWORD *)v16 = v17;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    v10 = CConfigPolicy::CreateAttributeHelper(v13, (int)v16, (int)v18, a3, &pvarg);
    if ( v10 < 0 && gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      LOWORD(v25) = 0;
      FormatRRASErrorString(
        &v25,
        L"CConfigPolicy::AddVariantAttribute(): Error %lx Couldn't create requested Attribute!",
        (unsigned int)v10);
      goto LABEL_14;
    }
  }
  else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    LOWORD(v25) = 0;
    FormatRRASErrorString(
      &v25,
      L"CConfigPolicy::AddVariantAttribute(): Error %lx while trying to locate Radius Policy!",
      (unsigned int)PolicyAndProfile);
LABEL_14:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
      gSdoUtilEtwContext,
      xmmword_180078BA0,
      &v25);
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180038f54  push    rbp
0x180038f56  push    rbx
0x180038f57  push    rsi
0x180038f58  push    rdi
0x180038f59  push    r14
0x180038f5b  push    r15
0x180038f5d  lea     rbp, [rsp-7E8h]
0x180038f65  sub     rsp, 8E8h
0x180038f6c  mov     rax, cs:__security_cookie
0x180038f73  xor     rax, rsp
0x180038f76  mov     [rbp+810h+var_40], rax
0x180038f7d  mov     r14, r9
0x180038f80  mov     r15d, r8d
0x180038f83  mov     rdi, rdx
0x180038f86  mov     rsi, rcx
0x180038f89  mov     rbx, [rbp+810h+arg_20]
0x180038f90  mov     [rbp+810h+var_888], 0
0x180038f98  mov     [rbp+810h+var_890], 0
0x180038fa0  mov     [rsp+910h+var_898], 0
0x180038fa9  mov     [rsp+910h+var_8B0], 0
0x180038fb2  mov     [rsp+910h+var_8A0], 0
0x180038fbb  xor     eax, eax
0x180038fbd  mov     [rsp+910h+var_8C0], ax
0x180038fc2  mov     [rbp+810h+var_840], eax
0x180038fc5  xor     edx, edx; Val
0x180038fc7  mov     r8d, 7FCh; Size
0x180038fcd  lea     rcx, [rbp+810h+var_83C]; void *
0x180038fd1  call    memset_0
0x180038fd6  movaps  xmm0, xmmword ptr [rbx]
0x180038fd9  movaps  xmmword ptr [rbp+810h+pvarg], xmm0
0x180038fdd  movsd   xmm1, qword ptr [rbx+10h]
0x180038fe2  movsd   qword ptr [rbp+810h+pvarg+10h], xmm1
0x180038fe7  movaps  xmm0, xmmword ptr [rdi]
0x180038fea  movaps  [rbp+810h+var_860], xmm0
0x180038fee  movsd   xmm1, qword ptr [rdi+10h]
0x180038ff3  movsd   [rbp+810h+var_850], xmm1
0x180038ff8  lea     rax, [rsp+910h+var_8C0]
0x180038ffd  mov     [rsp+910h+var_8C8], rax
0x180039002  lea     rax, [rsp+910h+var_8A0]
0x180039007  mov     [rsp+910h+var_8D0], rax
0x18003900c  lea     rax, [rsp+910h+var_8B0]
0x180039011  mov     [rsp+910h+var_8D8], rax
0x180039016  lea     rax, [rsp+910h+var_898]
0x18003901b  mov     [rsp+910h+var_8E0], rax
0x180039020  lea     rax, [rbp+810h+var_890]
0x180039024  mov     [rsp+910h+var_8E8], rax
0x180039029  lea     rax, [rbp+810h+var_888]
0x18003902d  mov     [rsp+910h+var_8F0], rax
0x180039032  lea     r9, [rbp+810h+pvarg]
0x180039036  mov     r8d, 3
0x18003903c  lea     rdx, [rbp+810h+var_860]
0x180039040  mov     rcx, rsi
0x180039043  call    ?GetPolicyAndProfile@CConfigPolicy@@AEAAJUtagVARIANT@@K0AEAV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@1AEAV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@2AEAV?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@AEAF@Z; CConfigPolicy::GetPolicyAndProfile(tagVARIANT,ulong,tagVARIANT,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>> &,short &)
0x180039048  mov     edi, eax
0x18003904a  mov     rbx, [rsp+910h+var_8A0]
0x18003904f  test    eax, eax
0x180039051  jns     short loc_180039083
0x180039053  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003905a  jz      loc_180039144
0x180039060  cmp     qword ptr cs:xmmword_180078BA0, 0
0x180039068  jz      loc_180039144
0x18003906e  xor     ecx, ecx
0x180039070  mov     word ptr [rbp+810h+var_840], cx
0x180039074  mov     r8d, eax
0x180039077  lea     rdx, aCconfigpolicyA_15; "CConfigPolicy::AddVariantAttribute(): E"...
0x18003907e  jmp     loc_18003911C
0x180039083  lea     rcx, [rbp+810h+pvarg]; pvarg
0x180039087  call    cs:__imp_VariantInit
0x18003908d  mov     rdx, r14; pvargSrc
0x180039090  lea     rcx, [rbp+810h+pvarg]; pvargDest
0x180039094  call    cs:__imp_VariantCopy
0x18003909a  test    eax, eax
0x18003909c  js      loc_1800391D4
0x1800390a2  mov     qword ptr [rsp+910h+var_8A8], rbx
0x1800390a7  test    rbx, rbx
0x1800390aa  jz      short loc_1800390BC
0x1800390ac  mov     rax, [rbx]
0x1800390af  mov     rcx, rbx
0x1800390b2  mov     rax, [rax+8]
0x1800390b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390bb  nop
0x1800390bc  mov     rcx, [rsp+910h+var_8B0]
0x1800390c1  mov     qword ptr [rsp+910h+var_8B8], rcx
0x1800390c6  test    rcx, rcx
0x1800390c9  jz      short loc_1800390D8
0x1800390cb  mov     rax, [rcx]
0x1800390ce  mov     rax, [rax+8]
0x1800390d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800390d7  nop
0x1800390d8  lea     rax, [rbp+810h+pvarg]
0x1800390dc  mov     [rsp+910h+var_8F0], rax; VARIANTARG *
0x1800390e1  mov     r9d, r15d; int
0x1800390e4  lea     r8, [rsp+910h+var_8A8]; int
0x1800390e9  lea     rdx, [rsp+910h+var_8B8]; int
0x1800390ee  call    ?CreateAttributeHelper@CConfigPolicy@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@V?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@W4_ATTRIBUTEID@@V_variant_t@@@Z; CConfigPolicy::CreateAttributeHelper(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>>,_ATTRIBUTEID,_variant_t)
0x1800390f3  mov     edi, eax
0x1800390f5  test    eax, eax
0x1800390f7  jns     short loc_180039144
0x1800390f9  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x180039100  jz      short loc_180039144
0x180039102  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003910a  jz      short loc_180039144
0x18003910c  xor     eax, eax
0x18003910e  mov     word ptr [rbp+810h+var_840], ax
0x180039112  mov     r8d, edi
0x180039115  lea     rdx, aCconfigpolicyA_8; "CConfigPolicy::AddVariantAttribute(): E"...
0x18003911c  lea     rcx, [rbp+810h+var_840]
0x180039120  call    FormatRRASErrorString
0x180039125  lea     r8, [rbp+810h+var_840]
0x180039129  mov     rdx, qword ptr cs:xmmword_180078BA0
0x180039130  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x180039137  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003913e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039143  nop
0x180039144  test    rbx, rbx
0x180039147  jz      short loc_180039159
0x180039149  mov     rax, [rbx]
0x18003914c  mov     rcx, rbx
0x18003914f  mov     rax, [rax+10h]
0x180039153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039158  nop
0x180039159  mov     rcx, [rsp+910h+var_8B0]
0x18003915e  test    rcx, rcx
0x180039161  jz      short loc_180039170
0x180039163  mov     rax, [rcx]
0x180039166  mov     rax, [rax+10h]
0x18003916a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003916f  nop
0x180039170  mov     rcx, [rsp+910h+var_898]
0x180039175  test    rcx, rcx
0x180039178  jz      short loc_180039187
0x18003917a  mov     rax, [rcx]
0x18003917d  mov     rax, [rax+10h]
0x180039181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039186  nop
0x180039187  mov     rcx, [rbp+810h+var_890]
0x18003918b  test    rcx, rcx
0x18003918e  jz      short loc_18003919D
0x180039190  mov     rax, [rcx]
0x180039193  mov     rax, [rax+10h]
0x180039197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003919c  nop
0x18003919d  mov     rcx, [rbp+810h+var_888]
0x1800391a1  test    rcx, rcx
0x1800391a4  jz      short loc_1800391B3
0x1800391a6  mov     rax, [rcx]
0x1800391a9  mov     rax, [rax+10h]
0x1800391ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391b2  nop
0x1800391b3  mov     eax, edi
0x1800391b5  mov     rcx, [rbp+810h+var_40]
0x1800391bc  xor     rcx, rsp; StackCookie
0x1800391bf  call    __security_check_cookie
0x1800391c4  add     rsp, 8E8h
0x1800391cb  pop     r15
0x1800391cd  pop     r14
0x1800391cf  pop     rdi
0x1800391d0  pop     rsi
0x1800391d1  pop     rbx
0x1800391d2  pop     rbp
0x1800391d3  retn
0x1800391d4  mov     ecx, eax; int
0x1800391d6  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
