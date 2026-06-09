# CConfigPolicy::GetOrderValueHelper(tagVARIANT,tagVARIANT,long *)

- ea: `0x18003bd24`
- end: `0x18003bfb0`
- name: `?GetOrderValueHelper@CConfigPolicy@@AEAAJUtagVARIANT@@0PEAJ@Z`
- size: `652`
- prototype: `__int64 __fastcall(CConfigPolicy *__hidden this, struct tagVARIANT *__struct_ptr, struct tagVARIANT *__struct_ptr, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bb70`

## callees

- `0x18003bd24`
- `0x18003bfb8`
- `0x18003c6d0`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003bd7f`
- `OLEAUT32!__imp_VariantInit` at `0x18003bd7f`
- `OLEAUT32!__imp_VariantClear` at `0x18003be9f`
- `OLEAUT32!__imp_VariantClear` at `0x18003beeb`
- `OLEAUT32!__imp_VariantClear` at `0x18003be9f`
- `OLEAUT32!__imp_VariantClear` at `0x18003beeb`
- `OLEAUT32!__imp_VariantCopy` at `0x18003be8d`
- `OLEAUT32!__imp_VariantCopy` at `0x18003be8d`

## string_xrefs

- `0x18003be38`: `CConfigPolicy::GetOrderValueHelper(): Error %lx while trying to locate Radius Policy!`
- `0x18003bed5`: `CConfigPolicy::GetOrderValueHelper(): Received an invalid data type for the Policy's merit value!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::GetOrderValueHelper(
        CConfigPolicy *this,
        struct tagVARIANT *a2,
        struct tagVARIANT *a3,
        int *a4)
{
  int v7; // esi
  int PolicyAndProfile; // eax
  unsigned int v9; // ebx
  const wchar_t *v10; // r8
  __int64 v11; // rdx
  const VARIANTARG *Property; // rax
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // eax
  __int16 v17; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v18; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v19; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v20; // [rsp+68h] [rbp-98h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp-80h] BYREF
  VARIANTARG v24; // [rsp+A0h] [rbp-60h] BYREF
  struct tagVARIANT v25; // [rsp+C0h] [rbp-40h] BYREF
  int v26; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v27[2044]; // [rsp+E4h] [rbp-1Ch] BYREF

  v7 = (int)this;
  v22 = 0;
  v21 = 0;
  v18 = 0;
  v20 = 0;
  v19 = 0;
  v17 = 0;
  VariantInit(&pvarg);
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v25 = *a3;
  v24 = *a2;
  PolicyAndProfile = CConfigPolicy::GetPolicyAndProfile(
                       v7,
                       (unsigned int)&v24,
                       3,
                       (unsigned int)&v25,
                       (__int64)&v22,
                       (__int64)&v21,
                       (__int64)&v18,
                       (__int64)&v20,
                       (__int64)&v19,
                       (__int64)&v17);
  v9 = PolicyAndProfile;
  if ( PolicyAndProfile >= 0 )
  {
    if ( !v18 )
      _com_issue_error(-2147467261);
    Property = (const VARIANTARG *)SDOIASLib::ISdo::GetProperty(v18, &v24, 1025);
    v13 = VariantCopy(&pvarg, Property);
    if ( v13 < 0 )
      _com_issue_error(v13);
    v14 = VariantClear(&v24);
    if ( v14 < 0 )
      _com_issue_error(v14);
    if ( pvarg.vt == 3 || !pvarg.vt )
    {
      *a4 = pvarg.lVal;
    }
    else
    {
      v9 = -2147023092;
      if ( gIsSdoUtilEtwTracingAvailable )
      {
        v11 = xmmword_180078BA0;
        if ( (_QWORD)xmmword_180078BA0 )
        {
          v10 = L"CConfigPolicy::GetOrderValueHelper(): Received an invalid data type for the Policy's merit value!";
          goto LABEL_5;
        }
      }
    }
  }
  else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    LOWORD(v26) = 0;
    FormatRRASErrorString(
      &v26,
      L"CConfigPolicy::GetOrderValueHelper(): Error %lx while trying to locate Radius Policy!",
      (unsigned int)PolicyAndProfile);
    v10 = (const wchar_t *)&v26;
    v11 = xmmword_180078BA0;
LABEL_5:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gSdoUtilTemplateFunc)(
      gSdoUtilEtwContext,
      v11,
      v10);
  }
  v15 = VariantClear(&pvarg);
  if ( v15 < 0 )
    _com_issue_error(v15);
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  return v9;
}

```

## disassembly

```asm
0x18003bd24  push    rbp
0x18003bd26  push    rbx
0x18003bd27  push    rsi
0x18003bd28  push    rdi
0x18003bd29  push    r14
0x18003bd2b  push    r15
0x18003bd2d  lea     rbp, [rsp-7F8h]
0x18003bd35  sub     rsp, 8F8h
0x18003bd3c  mov     rax, cs:__security_cookie
0x18003bd43  xor     rax, rsp
0x18003bd46  mov     [rbp+820h+var_40], rax
0x18003bd4d  mov     r14, r9
0x18003bd50  mov     rbx, r8
0x18003bd53  mov     rdi, rdx
0x18003bd56  mov     rsi, rcx
0x18003bd59  xor     r15d, r15d
0x18003bd5c  mov     [rsp+920h+var_8A8], r15
0x18003bd61  mov     [rsp+920h+var_8B0], r15
0x18003bd66  mov     [rsp+920h+var_8C8], r15
0x18003bd6b  mov     [rsp+920h+var_8B8], r15
0x18003bd70  mov     [rsp+920h+var_8C0], r15
0x18003bd75  mov     [rsp+920h+var_8D0], r15w
0x18003bd7b  lea     rcx, [rbp+820h+pvarg]; pvarg
0x18003bd7f  call    cs:__imp_VariantInit
0x18003bd85  nop
0x18003bd86  mov     [rbp+820h+var_840], r15d
0x18003bd8a  xor     edx, edx; Val
0x18003bd8c  mov     r8d, 7FCh; Size
0x18003bd92  lea     rcx, [rbp+820h+var_83C]; void *
0x18003bd96  call    memset_0
0x18003bd9b  movaps  xmm0, xmmword ptr [rbx]
0x18003bd9e  movaps  [rbp+820h+var_860], xmm0
0x18003bda2  movsd   xmm1, qword ptr [rbx+10h]
0x18003bda7  movsd   [rbp+820h+var_850], xmm1
0x18003bdac  movaps  xmm0, xmmword ptr [rdi]
0x18003bdaf  movaps  xmmword ptr [rbp+820h+var_880], xmm0
0x18003bdb3  movsd   xmm1, qword ptr [rdi+10h]
0x18003bdb8  movsd   qword ptr [rbp+820h+var_880+10h], xmm1
0x18003bdbd  lea     rax, [rsp+920h+var_8D0]
0x18003bdc2  mov     [rsp+920h+var_8D8], rax
0x18003bdc7  lea     rax, [rsp+920h+var_8C0]
0x18003bdcc  mov     [rsp+920h+var_8E0], rax
0x18003bdd1  lea     rax, [rsp+920h+var_8B8]
0x18003bdd6  mov     [rsp+920h+var_8E8], rax
0x18003bddb  lea     rax, [rsp+920h+var_8C8]
0x18003bde0  mov     [rsp+920h+var_8F0], rax
0x18003bde5  lea     rax, [rsp+920h+var_8B0]
0x18003bdea  mov     [rsp+920h+var_8F8], rax
0x18003bdef  lea     rax, [rsp+920h+var_8A8]
0x18003bdf4  mov     [rsp+920h+var_900], rax
0x18003bdf9  lea     r9, [rbp+820h+var_860]
0x18003bdfd  lea     edi, [r15+3]
0x18003be01  mov     r8d, edi
0x18003be04  lea     rdx, [rbp+820h+var_880]
0x18003be08  mov     rcx, rsi
0x18003be0b  call    ?GetPolicyAndProfile@CConfigPolicy@@AEAAJUtagVARIANT@@K0AEAV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@1AEAV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@2AEAV?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@AEAF@Z; CConfigPolicy::GetPolicyAndProfile(tagVARIANT,ulong,tagVARIANT,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>> &,short &)
0x18003be10  mov     ebx, eax
0x18003be12  test    eax, eax
0x18003be14  jns     short loc_18003BE68
0x18003be16  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r15d; int gIsSdoUtilEtwTracingAvailable
0x18003be1d  jz      loc_18003BEE7
0x18003be23  cmp     qword ptr cs:xmmword_180078BA0, r15
0x18003be2a  jz      loc_18003BEE7
0x18003be30  mov     word ptr [rbp+820h+var_840], r15w
0x18003be35  mov     r8d, eax
0x18003be38  lea     rdx, aCconfigpolicyG_21; "CConfigPolicy::GetOrderValueHelper(): E"...
0x18003be3f  lea     rcx, [rbp+820h+var_840]
0x18003be43  call    FormatRRASErrorString
0x18003be48  lea     r8, [rbp+820h+var_840]
0x18003be4c  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003be53  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003be5a  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003be61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003be66  jmp     short loc_18003BEE7
0x18003be68  mov     rcx, [rsp+920h+var_8C8]
0x18003be6d  test    rcx, rcx
0x18003be70  jz      loc_18003BF95
0x18003be76  mov     r8d, 401h
0x18003be7c  lea     rdx, [rbp+820h+var_880]
0x18003be80  call    ?GetProperty@ISdo@SDOIASLib@@QEAA?AV_variant_t@@J@Z; SDOIASLib::ISdo::GetProperty(long)
0x18003be85  nop
0x18003be86  mov     rdx, rax; pvargSrc
0x18003be89  lea     rcx, [rbp+820h+pvarg]; pvargDest
0x18003be8d  call    cs:__imp_VariantCopy
0x18003be93  test    eax, eax
0x18003be95  js      loc_18003BFA0
0x18003be9b  lea     rcx, [rbp+820h+var_880]; pvarg
0x18003be9f  call    cs:__imp_VariantClear
0x18003bea5  test    eax, eax
0x18003bea7  js      loc_18003BFA8
0x18003bead  movzx   eax, word ptr [rbp+820h+pvarg]
0x18003beb1  cmp     ax, di
0x18003beb4  jz      short loc_18003BEE1
0x18003beb6  test    ax, ax
0x18003beb9  jz      short loc_18003BEE1
0x18003bebb  mov     ebx, 8007070Ch
0x18003bec0  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r15d; int gIsSdoUtilEtwTracingAvailable
0x18003bec7  jz      short loc_18003BEE7
0x18003bec9  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003bed0  test    rdx, rdx
0x18003bed3  jz      short loc_18003BEE7
0x18003bed5  lea     r8, aCconfigpolicyG_0; "CConfigPolicy::GetOrderValueHelper(): R"...
0x18003bedc  jmp     loc_18003BE53
0x18003bee1  mov     eax, dword ptr [rbp+820h+pvarg+8]
0x18003bee4  mov     [r14], eax
0x18003bee7  lea     rcx, [rbp+820h+pvarg]; pvarg
0x18003beeb  call    cs:__imp_VariantClear
0x18003bef1  test    eax, eax
0x18003bef3  js      loc_18003BF8D
0x18003bef9  mov     rcx, [rsp+920h+var_8C0]
0x18003befe  test    rcx, rcx
0x18003bf01  jz      short loc_18003BF10
0x18003bf03  mov     rax, [rcx]
0x18003bf06  mov     rax, [rax+10h]
0x18003bf0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf0f  nop
0x18003bf10  mov     rcx, [rsp+920h+var_8B8]
0x18003bf15  test    rcx, rcx
0x18003bf18  jz      short loc_18003BF27
0x18003bf1a  mov     rax, [rcx]
0x18003bf1d  mov     rax, [rax+10h]
0x18003bf21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf26  nop
0x18003bf27  mov     rcx, [rsp+920h+var_8C8]
0x18003bf2c  test    rcx, rcx
0x18003bf2f  jz      short loc_18003BF3E
0x18003bf31  mov     rax, [rcx]
0x18003bf34  mov     rax, [rax+10h]
0x18003bf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf3d  nop
0x18003bf3e  mov     rcx, [rsp+920h+var_8B0]
0x18003bf43  test    rcx, rcx
0x18003bf46  jz      short loc_18003BF55
0x18003bf48  mov     rax, [rcx]
0x18003bf4b  mov     rax, [rax+10h]
0x18003bf4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf54  nop
0x18003bf55  mov     rcx, [rsp+920h+var_8A8]
0x18003bf5a  test    rcx, rcx
0x18003bf5d  jz      short loc_18003BF6C
0x18003bf5f  mov     rax, [rcx]
0x18003bf62  mov     rax, [rax+10h]
0x18003bf66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf6b  nop
0x18003bf6c  mov     eax, ebx
0x18003bf6e  mov     rcx, [rbp+820h+var_40]
0x18003bf75  xor     rcx, rsp; StackCookie
0x18003bf78  call    __security_check_cookie
0x18003bf7d  add     rsp, 8F8h
0x18003bf84  pop     r15
0x18003bf86  pop     r14
0x18003bf88  pop     rdi
0x18003bf89  pop     rsi
0x18003bf8a  pop     rbx
0x18003bf8b  pop     rbp
0x18003bf8c  retn
0x18003bf8d  mov     ecx, eax; int
0x18003bf8f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003bf95  mov     ecx, 80004003h; int
0x18003bf9a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003bfa0  mov     ecx, eax; int
0x18003bfa2  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003bfa8  mov     ecx, eax; int
0x18003bfaa  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
