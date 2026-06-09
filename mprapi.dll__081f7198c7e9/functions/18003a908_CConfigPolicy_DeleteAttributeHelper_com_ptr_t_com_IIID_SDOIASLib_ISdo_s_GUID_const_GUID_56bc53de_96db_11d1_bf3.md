# CConfigPolicy::DeleteAttributeHelper(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>>,_ATTRIBUTEID)

- ea: `0x18003a908`
- end: `0x18003abcf`
- name: `?DeleteAttributeHelper@CConfigPolicy@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@V?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@W4_ATTRIBUTEID@@@Z`
- size: `711`
- prototype: `__int64 __fastcall(__int64, struct IUnknown **, _QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003d248`

## callees

- `0x18003a2a0`
- `0x18003a908`
- `0x18003e2ac`
- `0x18003f334`
- `0x180050dbc`
- `0x180050e4c`
- `0x180050e60`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003a949`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a949`
- `OLEAUT32!__imp_VariantClear` at `0x18003aa4c`
- `OLEAUT32!__imp_VariantClear` at `0x18003aa4c`

## string_xrefs

- `0x18003a9ea`: `CConfigPolicy::DeleteAttributeHelper(): Error %lx Couldn't create a new Attribute! (couldn't get IDispatch pointer)`
- `0x18003aafb`: `CConfigPolicy::DeleteAttributeHelper(): Error %lx Couldn't convert the IDispatch pointer into an ISdoCollection pointer!`
- `0x18003ab71`: `CConfigPolicy::DeleteAttributeHelper(): Error %lx Couldn't delete Attribute from the collection!`

## pseudocode

```c
__int64 __fastcall CConfigPolicy::DeleteAttributeHelper(__int64 a1, struct IUnknown **a2, _QWORD *a3, unsigned int a4)
{
  BSTR v7; // rax
  struct IUnknown *v8; // rcx
  int v9; // eax
  int Collection; // ebx
  HRESULT v11; // eax
  struct IUnknown *v13; // rcx
  struct IUnknown *v14; // rdi
  int v15; // eax
  struct IUnknown *v16; // [rsp+30h] [rbp-D0h] BYREF
  struct IUnknown *v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown **v20; // [rsp+60h] [rbp-A0h]
  _QWORD *v21; // [rsp+68h] [rbp-98h]
  VARIANTARG v22; // [rsp+70h] [rbp-90h] BYREF
  int v23; // [rsp+90h] [rbp-70h] BYREF
  char v24[2044]; // [rsp+94h] [rbp-6Ch] BYREF

  v20 = a2;
  v21 = a3;
  v7 = SysAllocString(&word_180059138);
  if ( !v7 )
    _com_issue_error(-2147024882);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)v7;
  v18 = 0;
  v17 = 0;
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v8 = (struct IUnknown *)*a3;
  v16 = v8;
  if ( v8 )
    ((void (__fastcall *)(struct IUnknown *))v8->lpVtbl->AddRef)(v8);
  v9 = CConfigPolicy::CreateAttributeObject(
         (__int64)v8,
         a4,
         (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))&v16,
         &v18,
         (__int64)&pvarg);
  Collection = v9;
  if ( v9 >= 0 )
  {
    v13 = *a2;
    v16 = v13;
    if ( v13 )
      ((void (__fastcall *)(struct IUnknown *))v13->lpVtbl->AddRef)(v13);
    Collection = GetCollection(&v16, 1024, &v17);
    if ( Collection >= 0 )
    {
      v16 = v17;
      if ( v17 )
        ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->AddRef)(v17);
      v22 = pvarg;
      Collection = RemoveObjectFromCollection(&v22, &v16);
      if ( Collection >= 0 )
      {
        v14 = *a2;
        if ( !*a2 )
          _com_issue_error(-2147467261);
        v15 = ((__int64 (__fastcall *)(struct IUnknown *))v14->lpVtbl[3].Release)(*a2);
        Collection = v15;
        if ( v15 < 0 )
          _com_issue_errorex(v15, v14, &GUID_56bc53de_96db_11d1_bf3f_000000000000);
      }
      else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
      {
        LOWORD(v23) = 0;
        FormatRRASErrorString(
          &v23,
          L"CConfigPolicy::DeleteAttributeHelper(): Error %lx Couldn't delete Attribute from the collection!",
          (unsigned int)Collection);
        goto LABEL_8;
      }
    }
    else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      LOWORD(v23) = 0;
      FormatRRASErrorString(
        &v23,
        L"CConfigPolicy::DeleteAttributeHelper(): Error %lx Couldn't convert the IDispatch pointer into an ISdoCollection pointer!",
        (unsigned int)Collection);
      goto LABEL_8;
    }
  }
  else if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
  {
    LOWORD(v23) = 0;
    FormatRRASErrorString(
      &v23,
      L"CConfigPolicy::DeleteAttributeHelper(): Error %lx Couldn't create a new Attribute! (couldn't get IDispatch pointer)",
      (unsigned int)v9);
LABEL_8:
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
      gSdoUtilEtwContext,
      xmmword_180078BA0,
      &v23);
  }
  if ( v17 )
    ((void (__fastcall *)(struct IUnknown *))v17->lpVtbl->Release)(v17);
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v11 = VariantClear(&pvarg);
  if ( v11 < 0 )
    _com_issue_error(v11);
  if ( *a2 )
    ((void (__fastcall *)(struct IUnknown *))(*a2)->lpVtbl->Release)(*a2);
  if ( *a3 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
  return (unsigned int)Collection;
}

```

## disassembly

```asm
0x18003a908  push    rbp
0x18003a90a  push    rbx
0x18003a90b  push    rsi
0x18003a90c  push    rdi
0x18003a90d  push    r14
0x18003a90f  lea     rbp, [rsp-7A0h]
0x18003a917  sub     rsp, 8A0h
0x18003a91e  mov     rax, cs:__security_cookie
0x18003a925  xor     rax, rsp
0x18003a928  mov     [rbp+7C0h+var_30], rax
0x18003a92f  mov     ebx, r9d
0x18003a932  mov     r14, r8
0x18003a935  mov     rsi, rdx
0x18003a938  mov     [rsp+8C0h+var_860], rdx
0x18003a93d  mov     [rsp+8C0h+var_858], r8
0x18003a942  lea     rcx, word_180059138; psz
0x18003a949  call    cs:__imp_SysAllocString
0x18003a94f  test    rax, rax
0x18003a952  jz      loc_18003ABBC
0x18003a958  mov     ecx, 8
0x18003a95d  mov     word ptr [rsp+8C0h+pvarg], cx
0x18003a962  mov     qword ptr [rsp+8C0h+pvarg+8], rax
0x18003a967  mov     [rsp+8C0h+var_880], 0
0x18003a970  mov     [rsp+8C0h+var_888], 0
0x18003a979  xor     eax, eax
0x18003a97b  mov     [rbp+7C0h+var_830], eax
0x18003a97e  xor     edx, edx; Val
0x18003a980  mov     r8d, 7FCh; Size
0x18003a986  lea     rcx, [rbp+7C0h+var_82C]; void *
0x18003a98a  call    memset_0
0x18003a98f  mov     rcx, [r14]
0x18003a992  mov     [rsp+8C0h+var_890], rcx
0x18003a997  test    rcx, rcx
0x18003a99a  jz      short loc_18003A9A9
0x18003a99c  mov     rax, [rcx]
0x18003a99f  mov     rax, [rax+8]
0x18003a9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9a8  nop
0x18003a9a9  lea     rax, [rsp+8C0h+pvarg]
0x18003a9ae  mov     [rsp+8C0h+var_8A0], rax
0x18003a9b3  lea     r9, [rsp+8C0h+var_880]
0x18003a9b8  lea     r8, [rsp+8C0h+var_890]
0x18003a9bd  mov     edx, ebx
0x18003a9bf  call    ?CreateAttributeObject@CConfigPolicy@@AEAAJW4_ATTRIBUTEID@@V?$_com_ptr_t@V?$_com_IIID@UISdoDictionaryOld@SDOIASLib@@$1?_GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@AEAUtagVARIANT@@@Z; CConfigPolicy::CreateAttributeObject(_ATTRIBUTEID,_com_ptr_t<_com_IIID<SDOIASLib::ISdoDictionaryOld,&__s_GUID const _GUID_d432e5f4_53d8_11d2_9a3a_00c04fb998ac>>,_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>> &,tagVARIANT &)
0x18003a9c4  mov     ebx, eax
0x18003a9c6  test    eax, eax
0x18003a9c8  jns     loc_18003AAA3
0x18003a9ce  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003a9d5  jz      short loc_18003AA19
0x18003a9d7  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003a9df  jz      short loc_18003AA19
0x18003a9e1  xor     ecx, ecx
0x18003a9e3  mov     word ptr [rbp+7C0h+var_830], cx
0x18003a9e7  mov     r8d, eax
0x18003a9ea  lea     rdx, aCconfigpolicyD_1; "CConfigPolicy::DeleteAttributeHelper():"...
0x18003a9f1  lea     rcx, [rbp+7C0h+var_830]
0x18003a9f5  call    FormatRRASErrorString
0x18003a9fa  lea     r8, [rbp+7C0h+var_830]
0x18003a9fe  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003aa05  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003aa0c  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003aa13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa18  nop
0x18003aa19  mov     rcx, [rsp+8C0h+var_888]
0x18003aa1e  test    rcx, rcx
0x18003aa21  jz      short loc_18003AA30
0x18003aa23  mov     rax, [rcx]
0x18003aa26  mov     rax, [rax+10h]
0x18003aa2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa2f  nop
0x18003aa30  mov     rcx, [rsp+8C0h+var_880]
0x18003aa35  test    rcx, rcx
0x18003aa38  jz      short loc_18003AA47
0x18003aa3a  mov     rax, [rcx]
0x18003aa3d  mov     rax, [rax+10h]
0x18003aa41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa46  nop
0x18003aa47  lea     rcx, [rsp+8C0h+pvarg]; pvarg
0x18003aa4c  call    cs:__imp_VariantClear
0x18003aa52  test    eax, eax
0x18003aa54  js      loc_18003ABC7
0x18003aa5a  mov     rcx, [rsi]
0x18003aa5d  test    rcx, rcx
0x18003aa60  jz      short loc_18003AA6F
0x18003aa62  mov     rax, [rcx]
0x18003aa65  mov     rax, [rax+10h]
0x18003aa69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa6e  nop
0x18003aa6f  mov     rcx, [r14]
0x18003aa72  test    rcx, rcx
0x18003aa75  jz      short loc_18003AA84
0x18003aa77  mov     rax, [rcx]
0x18003aa7a  mov     rax, [rax+10h]
0x18003aa7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa83  nop
0x18003aa84  mov     eax, ebx
0x18003aa86  mov     rcx, [rbp+7C0h+var_30]
0x18003aa8d  xor     rcx, rsp; StackCookie
0x18003aa90  call    __security_check_cookie
0x18003aa95  add     rsp, 8A0h
0x18003aa9c  pop     r14
0x18003aa9e  pop     rdi
0x18003aa9f  pop     rsi
0x18003aaa0  pop     rbx
0x18003aaa1  pop     rbp
0x18003aaa2  retn
0x18003aaa3  mov     rcx, [rsi]
0x18003aaa6  mov     [rsp+8C0h+var_890], rcx
0x18003aaab  test    rcx, rcx
0x18003aaae  jz      short loc_18003AABD
0x18003aab0  mov     rax, [rcx]
0x18003aab3  mov     rax, [rax+8]
0x18003aab7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aabc  nop
0x18003aabd  lea     r8, [rsp+8C0h+var_888]
0x18003aac2  mov     edx, 400h
0x18003aac7  lea     rcx, [rsp+8C0h+var_890]
0x18003aacc  call    ?GetCollection@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JAEAV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z; GetCollection(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &)
0x18003aad1  mov     ebx, eax
0x18003aad3  test    eax, eax
0x18003aad5  jns     short loc_18003AB07
0x18003aad7  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003aade  jz      loc_18003AA19
0x18003aae4  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003aaec  jz      loc_18003AA19
0x18003aaf2  xor     eax, eax
0x18003aaf4  mov     word ptr [rbp+7C0h+var_830], ax
0x18003aaf8  mov     r8d, ebx
0x18003aafb  lea     rdx, aCconfigpolicyD_2; "CConfigPolicy::DeleteAttributeHelper():"...
0x18003ab02  jmp     loc_18003A9F1
0x18003ab07  mov     rcx, [rsp+8C0h+var_888]
0x18003ab0c  mov     [rsp+8C0h+var_890], rcx
0x18003ab11  test    rcx, rcx
0x18003ab14  jz      short loc_18003AB23
0x18003ab16  mov     rax, [rcx]
0x18003ab19  mov     rax, [rax+8]
0x18003ab1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab22  nop
0x18003ab23  movups  xmm0, xmmword ptr [rsp+8C0h+pvarg]
0x18003ab28  movaps  [rsp+8C0h+var_850], xmm0
0x18003ab2d  movsd   xmm1, qword ptr [rsp+8C0h+pvarg+10h]
0x18003ab33  movsd   [rbp+7C0h+var_840], xmm1
0x18003ab38  lea     rdx, [rsp+8C0h+var_890]
0x18003ab3d  lea     rcx, [rsp+8C0h+var_850]
0x18003ab42  call    ?RemoveObjectFromCollection@@YAJUtagVARIANT@@V?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z; RemoveObjectFromCollection(tagVARIANT,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>>)
0x18003ab47  mov     ebx, eax
0x18003ab49  test    eax, eax
0x18003ab4b  jns     short loc_18003AB7D
0x18003ab4d  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, 0; int gIsSdoUtilEtwTracingAvailable
0x18003ab54  jz      loc_18003AA19
0x18003ab5a  cmp     qword ptr cs:xmmword_180078BA0, 0
0x18003ab62  jz      loc_18003AA19
0x18003ab68  xor     eax, eax
0x18003ab6a  mov     word ptr [rbp+7C0h+var_830], ax
0x18003ab6e  mov     r8d, ebx
0x18003ab71  lea     rdx, aCconfigpolicyD_0; "CConfigPolicy::DeleteAttributeHelper():"...
0x18003ab78  jmp     loc_18003A9F1
0x18003ab7d  mov     rdi, [rsi]
0x18003ab80  test    rdi, rdi
0x18003ab83  jz      short loc_18003AB9F
0x18003ab85  mov     rax, [rdi]
0x18003ab88  mov     rcx, rdi
0x18003ab8b  mov     rax, [rax+58h]
0x18003ab8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab94  mov     ebx, eax
0x18003ab96  test    eax, eax
0x18003ab98  js      short loc_18003ABAA
0x18003ab9a  jmp     loc_18003AA19
0x18003ab9f  mov     ecx, 80004003h; int
0x18003aba4  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003abaa  lea     r8, _GUID_56bc53de_96db_11d1_bf3f_000000000000; struct _GUID *
0x18003abb1  mov     rdx, rdi; struct IUnknown *
0x18003abb4  mov     ecx, eax; int
0x18003abb6  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18003abbc  mov     ecx, 8007000Eh; int
0x18003abc1  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003abc7  mov     ecx, eax; int
0x18003abc9  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
