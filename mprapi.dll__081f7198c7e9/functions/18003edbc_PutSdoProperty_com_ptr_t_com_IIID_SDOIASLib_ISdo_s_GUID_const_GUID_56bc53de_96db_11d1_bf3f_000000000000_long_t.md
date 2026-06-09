# PutSdoProperty(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,tagVARIANT)

- ea: `0x18003edbc`
- end: `0x18003ef97`
- name: `?PutSdoProperty@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JUtagVARIANT@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(struct IUnknown **, unsigned int, const VARIANTARG *)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180039524`
- `0x180039e68`
- `0x18003a4c4`
- `0x18003daf0`

## callees

- `0x18003edbc`
- `0x180050dbc`
- `0x180050e4c`
- `0x180050e60`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003ede8`
- `OLEAUT32!__imp_VariantInit` at `0x18003ede8`
- `OLEAUT32!__imp_VariantClear` at `0x18003ef0e`
- `OLEAUT32!__imp_VariantClear` at `0x18003ef0e`
- `OLEAUT32!__imp_VariantCopy` at `0x18003edf6`
- `OLEAUT32!__imp_VariantCopy` at `0x18003edf6`

## pseudocode

```c
__int64 __fastcall PutSdoProperty(struct IUnknown **a1, unsigned int a2, const VARIANTARG *a3)
{
  HRESULT v5; // eax
  struct IUnknown *v6; // rdi
  int v7; // eax
  struct IUnknown *v8; // rsi
  unsigned int v9; // edi
  const wchar_t *v10; // rdx
  int v11; // eax
  HRESULT v12; // eax
  int v14; // [rsp+20h] [rbp-898h]
  int v15; // [rsp+20h] [rbp-898h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-888h] BYREF
  _DWORD v18[4]; // [rsp+48h] [rbp-870h] BYREF
  __int64 v19; // [rsp+58h] [rbp-860h]
  HLOCAL v20; // [rsp+60h] [rbp-858h]
  _DWORD v21[4]; // [rsp+68h] [rbp-850h] BYREF
  __int64 v22; // [rsp+78h] [rbp-840h]
  HLOCAL v23; // [rsp+80h] [rbp-838h]
  int v24; // [rsp+90h] [rbp-828h] BYREF
  _BYTE v25[2044]; // [rsp+94h] [rbp-824h] BYREF

  VariantInit(&pvarg);
  v5 = VariantCopy(&pvarg, a3);
  if ( v5 < 0 )
    _com_issue_error(v5);
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v6 = *a1;
    if ( !*a1 )
      _com_issue_error(-2147467261);
    v7 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, VARIANTARG *))v6->lpVtbl[3].QueryInterface)(
           *a1,
           a2,
           &pvarg);
    if ( v7 < 0 )
      _com_issue_errorex(v7, v6, &GUID_56bc53de_96db_11d1_bf3f_000000000000);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', (_com_error *)v18) )
    {
      v14 = v18[2];
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v20 )
        LocalFree(v20);
      __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_18003EE65);
      v9 = v14;
      if ( v14 < 0 )
      {
        if ( gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
        {
          v10 = L"SdoUtil::PutSdoProperty(): Failed with error %lx while trying to set the SDO Property's value!";
LABEL_18:
          LOWORD(v24) = 0;
          FormatRRASErrorString(&v24, v10, v9);
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gSdoUtilTemplateFunc)(
            gSdoUtilEtwContext,
            xmmword_180078BA0,
            &v24);
          goto LABEL_19;
        }
        goto LABEL_19;
      }
    }
  }
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    v8 = *a1;
    if ( !*a1 )
      _com_issue_error(-2147467261);
    v11 = ((__int64 (__fastcall *)(struct IUnknown *))v8->lpVtbl[3].Release)(*a1);
    v9 = v11;
    if ( v11 < 0 )
      _com_issue_errorex(v11, v8, &GUID_56bc53de_96db_11d1_bf3f_000000000000);
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &_com_error `RTTI Type Descriptor', (_com_error *)v21) )
    {
      v15 = v21[2];
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      if ( v23 )
        LocalFree(v23);
      __eh34_try_continuation(2, &_com_error `RTTI Type Descriptor', &loc_18003EEAC);
      v9 = v15;
      if ( v15 < 0 && gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
      {
        v10 = L"SdoUtil::PutSdoProperty(): Error while applying Property changes! %lx";
        goto LABEL_18;
      }
    }
  }
LABEL_19:
  v12 = VariantClear(&pvarg);
  if ( v12 < 0 )
    _com_issue_error(v12);
  if ( *a1 )
    ((void (__fastcall *)(struct IUnknown *))(*a1)->lpVtbl->Release)(*a1);
  return v9;
}

```

## disassembly

```asm
0x18003edbc  push    rbx
0x18003edbe  push    rsi
0x18003edbf  push    rdi
0x18003edc0  sub     rsp, 8A0h
0x18003edc7  mov     rax, cs:__security_cookie
0x18003edce  xor     rax, rsp
0x18003edd1  mov     [rsp+8B8h+var_28], rax
0x18003edd9  mov     rbx, r8
0x18003eddc  mov     esi, edx
0x18003edde  mov     [rsp+8B8h+var_890], rcx
0x18003ede3  lea     rcx, [rsp+8B8h+pvarg]; pvarg
0x18003ede8  call    cs:__imp_VariantInit
0x18003edee  mov     rdx, rbx; pvargSrc
0x18003edf1  lea     rcx, [rsp+8B8h+pvarg]; pvargDest
0x18003edf6  call    cs:__imp_VariantCopy
0x18003edfc  xor     ebx, ebx
0x18003edfe  test    eax, eax
0x18003ee00  js      loc_18003EF4F
0x18003ee06  mov     [rsp+8B8h+var_828], ebx
0x18003ee0d  xor     edx, edx; Val
0x18003ee0f  mov     r8d, 7FCh; Size
0x18003ee15  lea     rcx, [rsp+8B8h+var_824]; void *
0x18003ee1d  call    memset_0
0x18003ee22  nop
0x18003ee23  mov     rax, [rsp+8B8h+var_890]
0x18003ee28  mov     rdi, [rax]
0x18003ee2b  test    rdi, rdi
0x18003ee2e  jz      loc_18003EF57
0x18003ee34  mov     rax, [rdi]
0x18003ee37  lea     r8, [rsp+8B8h+pvarg]
0x18003ee3c  mov     edx, esi
0x18003ee3e  mov     rcx, rdi
0x18003ee41  mov     rax, [rax+48h]
0x18003ee45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee4a  test    eax, eax
0x18003ee4c  js      loc_18003EF61
0x18003ee52  mov     rax, [rsp+8B8h+var_890]
0x18003ee57  mov     rsi, [rax]
0x18003ee5a  test    rsi, rsi
0x18003ee5d  jz      loc_18003EF73
0x18003ee63  jmp     short loc_18003EE91
0x18003ee65  mov     edi, [rsp+8B8h+var_898]
0x18003ee69  xor     ebx, ebx
0x18003ee6b  test    edi, edi
0x18003ee6d  jns     short loc_18003EE52
0x18003ee6f  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, ebx; int gIsSdoUtilEtwTracingAvailable
0x18003ee75  jz      loc_18003EF09
0x18003ee7b  cmp     qword ptr cs:xmmword_180078BA0, rbx
0x18003ee82  jz      loc_18003EF09
0x18003ee88  lea     rdx, aSdoutilPutsdop; "SdoUtil::PutSdoProperty(): Failed with "...
0x18003ee8f  jmp     short loc_18003EECE
0x18003ee91  mov     rax, [rsi]
0x18003ee94  mov     rcx, rsi
0x18003ee97  mov     rax, [rax+58h]
0x18003ee9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eea0  mov     edi, eax
0x18003eea2  test    eax, eax
0x18003eea4  js      loc_18003EF7D
0x18003eeaa  jmp     short loc_18003EF09
0x18003eeac  mov     edi, [rsp+8B8h+var_898]
0x18003eeb0  xor     ebx, ebx
0x18003eeb2  test    edi, edi
0x18003eeb4  jns     short loc_18003EF09
0x18003eeb6  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, ebx; int gIsSdoUtilEtwTracingAvailable
0x18003eebc  jz      short loc_18003EF09
0x18003eebe  cmp     qword ptr cs:xmmword_180078BA0, rbx
0x18003eec5  jz      short loc_18003EF09
0x18003eec7  lea     rdx, aSdoutilPutsdop_0; "SdoUtil::PutSdoProperty(): Error while "...
0x18003eece  mov     word ptr [rsp+8B8h+var_828], bx
0x18003eed6  mov     r8d, edi
0x18003eed9  lea     rcx, [rsp+8B8h+var_828]
0x18003eee1  call    FormatRRASErrorString
0x18003eee6  lea     r8, [rsp+8B8h+var_828]
0x18003eeee  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003eef5  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003eefc  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003ef03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef08  nop
0x18003ef09  lea     rcx, [rsp+8B8h+pvarg]; pvarg
0x18003ef0e  call    cs:__imp_VariantClear
0x18003ef14  test    eax, eax
0x18003ef16  js      short loc_18003EF8F
0x18003ef18  mov     rcx, [rsp+8B8h+var_890]
0x18003ef1d  mov     rcx, [rcx]
0x18003ef20  test    rcx, rcx
0x18003ef23  jz      short loc_18003EF32
0x18003ef25  mov     rdx, [rcx]
0x18003ef28  mov     rax, [rdx+10h]
0x18003ef2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef31  nop
0x18003ef32  mov     eax, edi
0x18003ef34  mov     rcx, [rsp+8B8h+var_28]
0x18003ef3c  xor     rcx, rsp; StackCookie
0x18003ef3f  call    __security_check_cookie
0x18003ef44  add     rsp, 8A0h
0x18003ef4b  pop     rdi
0x18003ef4c  pop     rsi
0x18003ef4d  pop     rbx
0x18003ef4e  retn
0x18003ef4f  mov     ecx, eax; int
0x18003ef51  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003ef57  mov     ecx, 80004003h; int
0x18003ef5c  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003ef61  lea     r8, _GUID_56bc53de_96db_11d1_bf3f_000000000000; struct _GUID *
0x18003ef68  mov     rdx, rdi; struct IUnknown *
0x18003ef6b  mov     ecx, eax; int
0x18003ef6d  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18003ef73  mov     ecx, 80004003h; int
0x18003ef78  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003ef7d  lea     r8, _GUID_56bc53de_96db_11d1_bf3f_000000000000; struct _GUID *
0x18003ef84  mov     rdx, rsi; struct IUnknown *
0x18003ef87  mov     ecx, eax; int
0x18003ef89  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x18003ef8f  mov     ecx, eax; int
0x18003ef91  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
