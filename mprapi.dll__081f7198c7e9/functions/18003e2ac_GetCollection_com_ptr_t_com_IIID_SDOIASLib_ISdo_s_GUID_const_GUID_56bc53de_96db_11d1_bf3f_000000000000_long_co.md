# GetCollection(_com_ptr_t<_com_IIID<SDOIASLib::ISdo,&__s_GUID const _GUID_56bc53de_96db_11d1_bf3f_000000000000>>,long,_com_ptr_t<_com_IIID<SDOIASLib::ISdoCollection,&__s_GUID const _GUID_56bc53e2_96db_11d1_bf3f_000000000000>> &)

- ea: `0x18003e2ac`
- end: `0x18003e490`
- name: `?GetCollection@@YAJV?$_com_ptr_t@V?$_com_IIID@UISdo@SDOIASLib@@$1?_GUID_56bc53de_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@JAEAV?$_com_ptr_t@V?$_com_IIID@UISdoCollection@SDOIASLib@@$1?_GUID_56bc53e2_96db_11d1_bf3f_000000000000@@3U__s_GUID@@B@@@@@Z`
- size: `484`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, _QWORD *)`
- caller_count: `5`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180038024`
- `0x180039e68`
- `0x18003a908`
- `0x18003b16c`
- `0x18003c75c`

## callees

- `0x18003c6d0`
- `0x18003e2ac`
- `0x180050dbc`
- `0x180050e4c`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003e2e8`
- `OLEAUT32!__imp_VariantInit` at `0x18003e2e8`
- `OLEAUT32!__imp_VariantClear` at `0x18003e343`
- `OLEAUT32!__imp_VariantClear` at `0x18003e42d`
- `OLEAUT32!__imp_VariantClear` at `0x18003e343`
- `OLEAUT32!__imp_VariantClear` at `0x18003e42d`
- `OLEAUT32!__imp_VariantCopy` at `0x18003e330`
- `OLEAUT32!__imp_VariantCopy` at `0x18003e330`

## pseudocode

```c
__int64 __fastcall GetCollection(_QWORD *a1, unsigned int a2, _QWORD *a3)
{
  _QWORD *v3; // rdi
  _QWORD *v5; // rsi
  _QWORD *v6; // r14
  const VARIANTARG *Property; // rax
  HRESULT v8; // eax
  HRESULT v9; // eax
  LONGLONG llVal; // rcx
  __int64 (__fastcall *v11)(LONGLONG, GUID *, _QWORD *); // r15
  int v12; // eax
  unsigned int v13; // edi
  const wchar_t *v14; // r8
  __int64 v15; // rdx
  HRESULT v16; // eax
  int v18; // [rsp+20h] [rbp-8A8h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-888h] BYREF
  _DWORD v22[4]; // [rsp+58h] [rbp-870h] BYREF
  __int64 v23; // [rsp+68h] [rbp-860h]
  HLOCAL v24; // [rsp+70h] [rbp-858h]
  VARIANTARG v25; // [rsp+78h] [rbp-850h] BYREF
  int v26; // [rsp+90h] [rbp-838h] BYREF
  char v27[2044]; // [rsp+94h] [rbp-834h] BYREF

  v3 = a3;
  v5 = a1;
  v6 = a3;
  VariantInit(&pvarg);
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    if ( !*v5 )
      _com_issue_error(-2147467261);
    Property = (const VARIANTARG *)SDOIASLib::ISdo::GetProperty(*v5, &v25, a2);
    v8 = VariantCopy(&pvarg, Property);
    if ( v8 < 0 )
      _com_issue_error(v8);
    v9 = VariantClear(&v25);
    if ( v9 < 0 )
      _com_issue_error(v9);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &_com_error `RTTI Type Descriptor', (_com_error *)v22) )
    {
      v18 = v22[2];
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      if ( v24 )
        LocalFree(v24);
      __eh34_try_continuation(0, &_com_error `RTTI Type Descriptor', &loc_18003E353);
      v5 = a1;
      if ( v18 < 0 )
        goto LABEL_15;
      v6 = a3;
      v3 = a3;
    }
  }
  llVal = pvarg.llVal;
  if ( pvarg.llVal )
  {
    v11 = **(__int64 (__fastcall ***)(LONGLONG, GUID *, _QWORD *))pvarg.llVal;
    if ( *v3 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 16LL))(*v3);
      llVal = pvarg.llVal;
    }
    *v3 = 0;
    v12 = v11(llVal, &IID_ISdoCollection, v6);
    v13 = v12;
    if ( v12 < 0 && gIsSdoUtilEtwTracingAvailable && (_QWORD)xmmword_180078BA0 )
    {
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v26,
        L"SdoUtil::GetCollection(): Failed with error %lx while trying to convert the IDispatch pointer into an ISdoCollection pointer!",
        (unsigned int)v12);
      v14 = (const wchar_t *)&v26;
      v15 = xmmword_180078BA0;
LABEL_18:
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, __int64, const wchar_t *))gSdoUtilTemplateFunc)(
        gSdoUtilEtwContext,
        v15,
        v14);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
LABEL_15:
  v13 = -2147467261;
  if ( gIsSdoUtilEtwTracingAvailable )
  {
    v15 = xmmword_180078BA0;
    if ( (_QWORD)xmmword_180078BA0 )
    {
      v14 = L"SdoUtil::GetCollection(): Received a NULL pointer for the Collection's dispatch pointer!";
      goto LABEL_18;
    }
  }
LABEL_19:
  v16 = VariantClear(&pvarg);
  if ( v16 < 0 )
    _com_issue_error(v16);
  if ( *v5 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
  return v13;
}

```

## disassembly

```asm
0x18003e2ac  push    rbx
0x18003e2ae  push    rsi
0x18003e2af  push    rdi
0x18003e2b0  push    r14
0x18003e2b2  push    r15
0x18003e2b4  sub     rsp, 8A0h
0x18003e2bb  mov     rax, cs:__security_cookie
0x18003e2c2  xor     rax, rsp
0x18003e2c5  mov     [rsp+8C8h+var_38], rax
0x18003e2cd  mov     rdi, r8
0x18003e2d0  mov     r15d, edx
0x18003e2d3  mov     rsi, rcx
0x18003e2d6  mov     [rsp+8C8h+var_8A0], rcx
0x18003e2db  mov     r14, r8
0x18003e2de  mov     [rsp+8C8h+var_898], r8
0x18003e2e3  lea     rcx, [rsp+8C8h+pvarg]; pvarg
0x18003e2e8  call    cs:__imp_VariantInit
0x18003e2ee  nop
0x18003e2ef  xor     ebx, ebx
0x18003e2f1  mov     [rsp+8C8h+var_838], ebx
0x18003e2f8  xor     edx, edx; Val
0x18003e2fa  mov     r8d, 7FCh; Size
0x18003e300  lea     rcx, [rsp+8C8h+var_834]; void *
0x18003e308  call    memset_0
0x18003e30d  nop
0x18003e30e  cmp     [rsi], rbx
0x18003e311  jz      loc_18003E46D
0x18003e317  mov     r8d, r15d
0x18003e31a  lea     rdx, [rsp+8C8h+var_850]
0x18003e31f  mov     rcx, [rsi]
0x18003e322  call    ?GetProperty@ISdo@SDOIASLib@@QEAA?AV_variant_t@@J@Z; SDOIASLib::ISdo::GetProperty(long)
0x18003e327  nop
0x18003e328  mov     rdx, rax; pvargSrc
0x18003e32b  lea     rcx, [rsp+8C8h+pvarg]; pvargDest
0x18003e330  call    cs:__imp_VariantCopy
0x18003e336  test    eax, eax
0x18003e338  js      loc_18003E478
0x18003e33e  lea     rcx, [rsp+8C8h+var_850]; pvarg
0x18003e343  call    cs:__imp_VariantClear
0x18003e349  test    eax, eax
0x18003e34b  js      loc_18003E480
0x18003e351  jmp     short loc_18003E36C
0x18003e353  xor     ebx, ebx
0x18003e355  mov     rsi, [rsp+8C8h+var_8A0]
0x18003e35a  cmp     [rsp+8C8h+var_8A8], ebx
0x18003e35e  jl      loc_18003E3F4
0x18003e364  mov     r14, [rsp+8C8h+var_898]
0x18003e369  mov     rdi, r14
0x18003e36c  mov     rcx, qword ptr [rsp+8C8h+pvarg+8]
0x18003e371  test    rcx, rcx
0x18003e374  jz      short loc_18003E3F4
0x18003e376  mov     rax, [rcx]
0x18003e379  mov     r15, [rax]
0x18003e37c  mov     rdx, [rdi]
0x18003e37f  test    rdx, rdx
0x18003e382  jz      short loc_18003E398
0x18003e384  mov     rax, [rdx]
0x18003e387  mov     rcx, rdx
0x18003e38a  mov     rax, [rax+10h]
0x18003e38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e393  mov     rcx, qword ptr [rsp+8C8h+pvarg+8]
0x18003e398  mov     [rdi], rbx
0x18003e39b  mov     r8, r14
0x18003e39e  lea     rdx, IID_ISdoCollection
0x18003e3a5  mov     rax, r15
0x18003e3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e3ad  mov     edi, eax
0x18003e3af  test    eax, eax
0x18003e3b1  jns     short loc_18003E428
0x18003e3b3  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, ebx; int gIsSdoUtilEtwTracingAvailable
0x18003e3b9  jz      short loc_18003E428
0x18003e3bb  cmp     qword ptr cs:xmmword_180078BA0, rbx
0x18003e3c2  jz      short loc_18003E428
0x18003e3c4  mov     word ptr [rsp+8C8h+var_838], bx
0x18003e3cc  mov     r8d, eax
0x18003e3cf  lea     rdx, aSdoutilGetcoll_2; "SdoUtil::GetCollection(): Failed with e"...
0x18003e3d6  lea     rcx, [rsp+8C8h+var_838]
0x18003e3de  call    FormatRRASErrorString
0x18003e3e3  lea     r8, [rsp+8C8h+var_838]
0x18003e3eb  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003e3f2  jmp     short loc_18003E414
0x18003e3f4  mov     edi, 80004003h
0x18003e3f9  cmp     cs:?gIsSdoUtilEtwTracingAvailable@@3HA, ebx; int gIsSdoUtilEtwTracingAvailable
0x18003e3ff  jz      short loc_18003E428
0x18003e401  mov     rdx, qword ptr cs:xmmword_180078BA0
0x18003e408  test    rdx, rdx
0x18003e40b  jz      short loc_18003E428
0x18003e40d  lea     r8, aSdoutilGetcoll_1; "SdoUtil::GetCollection(): Received a NU"...
0x18003e414  mov     rcx, cs:?gSdoUtilEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gSdoUtilEtwContext
0x18003e41b  mov     rax, cs:?gSdoUtilTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gSdoUtilTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18003e422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e427  nop
0x18003e428  lea     rcx, [rsp+8C8h+pvarg]; pvarg
0x18003e42d  call    cs:__imp_VariantClear
0x18003e433  test    eax, eax
0x18003e435  js      short loc_18003E488
0x18003e437  mov     rcx, [rsi]
0x18003e43a  test    rcx, rcx
0x18003e43d  jz      short loc_18003E44C
0x18003e43f  mov     rax, [rcx]
0x18003e442  mov     rax, [rax+10h]
0x18003e446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e44b  nop
0x18003e44c  mov     eax, edi
0x18003e44e  mov     rcx, [rsp+8C8h+var_38]
0x18003e456  xor     rcx, rsp; StackCookie
0x18003e459  call    __security_check_cookie
0x18003e45e  add     rsp, 8A0h
0x18003e465  pop     r15
0x18003e467  pop     r14
0x18003e469  pop     rdi
0x18003e46a  pop     rsi
0x18003e46b  pop     rbx
0x18003e46c  retn
0x18003e46d  mov     ecx, 80004003h; int
0x18003e472  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003e478  mov     ecx, eax; int
0x18003e47a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003e480  mov     ecx, eax; int
0x18003e482  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003e488  mov     ecx, eax; int
0x18003e48a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
