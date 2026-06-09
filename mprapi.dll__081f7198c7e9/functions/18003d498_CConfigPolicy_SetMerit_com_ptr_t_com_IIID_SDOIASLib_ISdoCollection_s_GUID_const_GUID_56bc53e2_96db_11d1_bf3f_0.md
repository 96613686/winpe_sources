# CConfigPolicy::SetMerit(_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long)

- ea: `0x18003d498`
- end: `0x18003d6a1`
- name: `?SetMerit@CConfigPolicy@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@V?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@J@Z`
- size: `521`
- prototype: `__int64 __fastcall(__int64, __int64 **, __int64 **, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180038afc`
- `0x18003cf38`
- `0x18003d83c`

## callees

- `0x1800391e4`
- `0x18003c6d0`
- `0x18003d498`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003d4dc`
- `OLEAUT32!__imp_VariantInit` at `0x18003d4dc`
- `OLEAUT32!__imp_VariantClear` at `0x18003d533`
- `OLEAUT32!__imp_VariantClear` at `0x18003d622`
- `OLEAUT32!__imp_VariantClear` at `0x18003d533`
- `OLEAUT32!__imp_VariantClear` at `0x18003d622`
- `OLEAUT32!__imp_VariantCopy` at `0x18003d520`
- `OLEAUT32!__imp_VariantCopy` at `0x18003d520`

## string_xrefs

- `0x18003d573`: `CConfigPolicy::SetMerit(): Received invalid data type for Policy's merit value!`
- `0x18003d5ee`: `CConfigPolicy::SetMerit(): Error %lx Couldn't adjust the Policy Collection's Merit ordering!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::SetMerit(__int64 a1, __int64 **a2, __int64 **a3, int a4)
{
  const VARIANTARG *Property; // rax
  HRESULT v8; // eax
  HRESULT v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  const wchar_t *v12; // r8
  LONG lVal; // ebx
  __int64 *v14; // rcx
  __int64 *v15; // rcx
  int v16; // eax
  HRESULT v17; // eax
  __int64 *v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  __int64 **v22; // [rsp+58h] [rbp-A8h]
  __int64 **v23; // [rsp+60h] [rbp-A0h]
  VARIANTARG v24; // [rsp+68h] [rbp-98h] BYREF
  int v25; // [rsp+80h] [rbp-80h] BYREF
  char v26[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v22 = a2;
  v23 = a3;
  VariantInit(&pvarg);
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  if ( !*a3 )
    _com_issue_error(-2147467261);
  Property = (const VARIANTARG *)SDOIASLib::ISdo::GetProperty(*a3, &v24, 1025);
  v8 = VariantCopy(&pvarg, Property);
  if ( v8 < 0 )
    _com_issue_error(v8);
  v9 = VariantClear(&v24);
  if ( v9 < 0 )
    _com_issue_error(v9);
  if ( pvarg.vt == 3 || !pvarg.vt )
  {
    lVal = pvarg.lVal;
    v14 = *a3;
    v20 = v14;
    if ( v14 )
      (*(void (__fastcall **)(__int64 *))(*v14 + 8))(v14);
    v15 = *a2;
    v19 = v15;
    if ( v15 )
      (*(void (__fastcall **)(__int64 *))(*v15 + 8))(v15);
    v16 = CConfigPolicy::AdjustMeritOrdering((__int64)v15, &v19, &v20, lVal, a4);
    v10 = v16;
    if ( v16 < 0 && gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      LOWORD(v25) = 0;
      FormatRRASErrorString(
        &v25,
        L"CConfigPolicy::SetMerit(): Error %lx Couldn't adjust the Policy Collection's Merit ordering!",
        (unsigned int)v16);
      v12 = (const wchar_t *)&v25;
      v11 = xmmword_180078BA0;
      goto LABEL_17;
    }
  }
  else
  {
    v10 = -2147023092;
    if ( gIsSdoUtilEtwTracingAvailable )
    {
      v11 = xmmword_180078BA0;
      if ( (_QWORD)xmmword_180078BA0 )
      {
        v12 = L"CConfigPolicy::SetMerit(): Received invalid data type for Policy's merit value!";
LABEL_17:
        ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gSdoUtilTemplateFunc)(
          gSdoUtilEtwContext,
          v11,
          v12);
      }
    }
  }
  v17 = VariantClear(&pvarg);
  if ( v17 < 0 )
    _com_issue_error(v17);
  if ( *a2 )
    (*(void (__fastcall **)(__int64 *))(**a2 + 16))(*a2);
  if ( *a3 )
    (*(void (__fastcall **)(__int64 *))(**a3 + 16))(*a3);
  return v10;
}

```

## disassembly

```asm
0x18003d498  mov     [rsp-8+arg_0], rbx
0x18003d49d  push    rbp
0x18003d49e  push    rsi
0x18003d49f  push    rdi
0x18003d4a0  push    r14
0x18003d4a2  push    r15
0x18003d4a4  lea     rbp, [rsp-790h]
0x18003d4ac  sub     rsp, 890h
0x18003d4b3  mov     rax, cs:__security_cookie
0x18003d4ba  xor     rax, rsp
0x18003d4bd  mov     [rbp+7B0h+var_30], rax
0x18003d4c4  mov     r14d, r9d
0x18003d4c7  mov     rdi, r8
0x18003d4ca  mov     rsi, rdx
0x18003d4cd  mov     [rsp+8B0h+var_858], rdx
0x18003d4d2  mov     [rsp+8B0h+var_850], r8
0x18003d4d7  lea     rcx, [rsp+8B0h+pvarg]; pvarg
0x18003d4dc  call    cs:__imp_VariantInit
0x18003d4e2  nop
0x18003d4e3  xor     r15d, r15d
0x18003d4e6  mov     [rbp+7B0h+var_830], r15d
0x18003d4ea  xor     edx, edx; Val
0x18003d4ec  mov     r8d, 7FCh; Size
0x18003d4f2  lea     rcx, [rbp+7B0h+var_82C]; void *
0x18003d4f6  call    memset_0
0x18003d4fb  mov     rcx, [rdi]
0x18003d4fe  test    rcx, rcx
0x18003d501  jz      loc_18003D686
0x18003d507  mov     r8d, 401h
0x18003d50d  lea     rdx, [rsp+8B0h+var_848]
0x18003d512  call    ?GetProperty@ISdo@SDOIASLib@@QEAA?AV_variant_t@@J@Z; SDOIASLib::ISdo::GetProperty(long)
0x18003d517  nop
0x18003d518  mov     rdx, rax; pvargSrc
0x18003d51b  lea     rcx, [rsp+8B0h+pvarg]; pvargDest
0x18003d520  call    cs:__imp_VariantCopy
0x18003d526  test    eax, eax
0x18003d528  js      loc_18003D691
0x18003d52e  lea     rcx, [rsp+8B0h+var_848]; pvarg
0x18003d533  call    cs:__imp_VariantClear
0x18003d539  test    eax, eax
0x18003d53b  js      loc_18003D699
0x18003d541  movzx   eax, word ptr [rsp+8B0h+pvarg]
0x18003d546  cmp     ax, 3
0x18003d54a  jz      short loc_18003D57F
0x18003d54c  test    ax, ax
0x18003d54f  jz      short loc_18003D57F
0x18003d551  mov     ebx, 8007070Ch
0x18003d556  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r15d; int gIsSdoUtilEtwTracingAvailable
0x18003d55d  jz      loc_18003D61D
0x18003d563  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003d56a  test    rdx, rdx
0x18003d56d  jz      loc_18003D61D
0x18003d573  lea     r8, aCconfigpolicyS_0; "CConfigPolicy::SetMerit(): Received inv"...
0x18003d57a  jmp     loc_18003D609
0x18003d57f  mov     ebx, dword ptr [rsp+8B0h+pvarg+8]
0x18003d583  mov     rcx, [rdi]
0x18003d586  mov     [rsp+8B0h+var_878], rcx
0x18003d58b  test    rcx, rcx
0x18003d58e  jz      short loc_18003D59D
0x18003d590  mov     rax, [rcx]
0x18003d593  mov     rax, [rax+8]
0x18003d597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d59c  nop
0x18003d59d  mov     rcx, [rsi]
0x18003d5a0  mov     [rsp+8B0h+var_880], rcx
0x18003d5a5  test    rcx, rcx
0x18003d5a8  jz      short loc_18003D5B7
0x18003d5aa  mov     rax, [rcx]
0x18003d5ad  mov     rax, [rax+8]
0x18003d5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5b6  nop
0x18003d5b7  mov     [rsp+8B0h+var_890], r14d
0x18003d5bc  mov     r9d, ebx
0x18003d5bf  lea     r8, [rsp+8B0h+var_878]
0x18003d5c4  lea     rdx, [rsp+8B0h+var_880]
0x18003d5c9  call    ?AdjustMeritOrdering@CConfigPolicy@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@V?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JJ@Z; CConfigPolicy::AdjustMeritOrdering(_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,long)
0x18003d5ce  mov     ebx, eax
0x18003d5d0  test    eax, eax
0x18003d5d2  jns     short loc_18003D61D
0x18003d5d4  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, r15d; int gIsSdoUtilEtwTracingAvailable
0x18003d5db  jz      short loc_18003D61D
0x18003d5dd  cmp     qword ptr cs:xmmword_180078BA0, r15
0x18003d5e4  jz      short loc_18003D61D
0x18003d5e6  mov     word ptr [rbp+7B0h+var_830], r15w
0x18003d5eb  mov     r8d, eax
0x18003d5ee  lea     rdx, aCconfigpolicyS; "CConfigPolicy::SetMerit(): Error %lx Co"...
0x18003d5f5  lea     rcx, [rbp+7B0h+var_830]
0x18003d5f9  call    FormatRRASErrorString
0x18003d5fe  lea     r8, [rbp+7B0h+var_830]
0x18003d602  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003d609  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003d610  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003d617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d61c  nop
0x18003d61d  lea     rcx, [rsp+8B0h+pvarg]; pvarg
0x18003d622  call    cs:__imp_VariantClear
0x18003d628  test    eax, eax
0x18003d62a  js      short loc_18003D67E
0x18003d62c  mov     rcx, [rsi]
0x18003d62f  test    rcx, rcx
0x18003d632  jz      short loc_18003D641
0x18003d634  mov     rax, [rcx]
0x18003d637  mov     rax, [rax+10h]
0x18003d63b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d640  nop
0x18003d641  mov     rcx, [rdi]
0x18003d644  test    rcx, rcx
0x18003d647  jz      short loc_18003D656
0x18003d649  mov     rax, [rcx]
0x18003d64c  mov     rax, [rax+10h]
0x18003d650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d655  nop
0x18003d656  mov     eax, ebx
0x18003d658  mov     rcx, [rbp+7B0h+var_30]
0x18003d65f  xor     rcx, rsp; StackCookie
0x18003d662  call    __security_check_cookie
0x18003d667  mov     rbx, [rsp+8B0h+arg_0]
0x18003d66f  add     rsp, 890h
0x18003d676  pop     r15
0x18003d678  pop     r14
0x18003d67a  pop     rdi
0x18003d67b  pop     rsi
0x18003d67c  pop     rbp
0x18003d67d  retn
0x18003d67e  mov     ecx, eax; int
0x18003d680  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003d686  mov     ecx, 80004003h; int
0x18003d68b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003d691  mov     ecx, eax; int
0x18003d693  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003d699  mov     ecx, eax; int
0x18003d69b  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
